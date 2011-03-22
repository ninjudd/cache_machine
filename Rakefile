require 'rake'
require 'rake/testtask'
require 'rake/rdoctask'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |s|
    s.name = "cache_machine"
    s.summary = %Q{A Rails engine for quick, convenient caching.}
    s.email = "code@justinbalthrop.com"
    s.homepage = "http://github.com/ninjudd/cache_machine"
    s.description = "A Rails engine for quick, convenient caching."
    s.authors = ["Justin Balthrop"]
    s.add_dependency('memcache', '>= 1.0.0')
    s.add_dependency('cache_version', '>= 0.9.4')
    s.add_dependency('record_cache', '>= 0.9.12')
    s.add_dependency('method_cache', '>= 0.6.3')
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler not available. Install it with: sudo gem install technicalpickles-jeweler -s http://gems.github.com"
end

Rake::TestTask.new do |t|
  t.libs << 'lib'
  t.pattern = 'test/**/*_test.rb'
  t.verbose = false
end

Rake::RDocTask.new do |rdoc|
  rdoc.rdoc_dir = 'rdoc'
  rdoc.title    = 'record_cache'
  rdoc.options << '--line-numbers' << '--inline-source'
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end

begin
  require 'rcov/rcovtask'
  Rcov::RcovTask.new do |t|
    t.libs << 'test'
    t.test_files = FileList['test/**/*_test.rb']
    t.verbose = true
  end
rescue LoadError
end

task :default => :test
