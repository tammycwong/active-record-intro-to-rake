require 'pry'
#creates task dependency 
#Rake task to run before migrate task is run
task :environment do
  require_relative './config/environment'
end

#define, describe, namespace rake tasks
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
  #migrating database tables using rake task
  #&applying SQL statements to alter database
  namespace :db do
    desc 'migrate changes to your database'
    task :migrate => :environment do
      Student.create_table
    end
  # define rake task that executes code in file
    desc 'seed the database with some dummy data'
    task :seed do
    require_relative './db/seeds.rb'
  end

  end
#starts up Pry console. dependent on environment
#so Studen and database connection load first
  desc 'drop into the Pry console'
  task :console => :environment do
  Pry.start
end
