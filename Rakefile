# encoding: utf-8

require 'rubygems'
require 'bundler'
begin
  Bundler.setup(:default, :development)
rescue Bundler::BundlerError => e
  $stderr.puts e.message
  $stderr.puts "Run `bundle install` to install missing gems"
  exit e.status_code
end
require 'rake'

require 'jeweler'
require './lib/profile'
Jeweler::Tasks.new do |gem|
  gem.name = "profile"
  gem.homepage = "http://github.com/4pcbr/profile"
  gem.license = "MIT"
  gem.summary = %Q{Define profiled object data set}
  gem.description = %Q{This tool helps you to define multiple data sets, which you can use later in data profiling}
  gem.email = "i4pcbr@gmail.com"
  gem.authors = ["4pcbr"]
  gem.add_dependency "active_support", ">= 2.3.5"
  gem.version = Profile::Version::STRING
end
Jeweler::RubygemsDotOrgTasks.new

require 'rspec/core'
require 'rspec/core/rake_task'
RSpec::Core::RakeTask.new(:spec) do |spec|
  spec.pattern = FileList['spec/**/*_spec.rb']
end

RSpec::Core::RakeTask.new(:rcov) do |spec|
  spec.pattern = 'spec/**/*_spec.rb'
  spec.rcov = true
end

task :default => :spec

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "profile #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end