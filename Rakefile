#namespace is a naming convention to group similar rakes together. In this case, they are both greetings (or whatever we define it as)
namespace :greeting do
  desc 'outputs hello to the terminal'
  task :hello do
    puts "hello from Rake!"
  end

  desc 'outputs hola to the terminal'
  task :hola do 
    puts "hola de Rake!"
  end
end

#we need to give our task access to the environment where migrate can have access to our Student class and database. 
namespace :db do
  #we need to first create that connection to :enviroment
  task :environment do
    require_relative './config/environment'
  end
  
  desc 'migrate changes to your database'
  task :migrate => :environment do #this creates a task dependency
    Student.create_table
  end

  desc 'seed the database with some dummy data'
  task :seed do 
    require_relative './db/seeds.rb'
  end
  #we can test if we have successfully migrated and seeded our database
end

desc 'drop into the Pry console'
task :console => :environment do
  Pry.start
end



