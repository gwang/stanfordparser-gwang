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
Jeweler::Tasks.new do |gem|
  # gem is a Gem::Specification... see http://docs.rubygems.org/read/chapter/20 for more options
  gem.name = "stanfordparser"
  gem.homepage = "http://github.com/gwang/stanfordparser"
  gem.license = "MIT"
  gem.summary = "This is a Ruby wrapper for the Stanford Natural Language Parser."
  gem.description = "It is based on the original work done by Bill McNeal (version 2.2.0 in 2008). Since there Stanford Parser has advanced with new version while the wrapper development stalled. With this updated version, two major improvements are implemented: a) now compatible with newer version of Stanford Parser (tested with version 1.6.5). b) With added features."
  gem.email = "mywanggou@gmail.com"
  gem.authors = ["Gang Wang"]
  # dependencies defined in Gemfile
  gem.files = Dir.glob('lib/*.rb')
  gem.files.include Dir.glob('test/*.rb')	
  gem.files.include Dir.glob('examples/*.rb')
end
Jeweler::RubygemsDotOrgTasks.new

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/test_*.rb'
  test.verbose = true
end

require 'rcov/rcovtask'
Rcov::RcovTask.new do |test|
  test.libs << 'test'
  test.pattern = 'test/**/test_*.rb'
  test.verbose = true
  test.rcov_opts << '--exclude "gems/*"'
end

task :default => :test

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "stanfordparser-gwang #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
