#!/usr/bin/env rake
begin
  require 'bundler/setup'
rescue LoadError
  puts 'You must `gem install bundler` and `bundle install` to run rake tasks'
end
begin
  require 'rdoc/task'
rescue LoadError
  require 'rdoc/rdoc'
  require 'rake/rdoctask'
  RDoc::Task = Rake::RDocTask
end

RDoc::Task.new(:rdoc) do |rdoc|
  rdoc.rdoc_dir = 'rdoc'
  rdoc.title    = 'ActsAsElibriProduct'
  rdoc.options << '--line-numbers'
  rdoc.rdoc_files.include('README.rdoc')
  rdoc.rdoc_files.include('lib/**/*.rb')
end




Bundler::GemHelper.install_tasks

desc "Running specs"
task :spec do |t|
  exec "cd spec/dummy && bundle exec rake db:create:all && bundle exec rake db:migrate && bundle exec rake db:test:prepare && cd .. && bundle exec rspec acts_as_elibri_product_spec.rb.rb"
end

task :default => ["spec"]
