require 'rake'
require 'spec'
require 'cucumber'

require 'cucumber/rake/task'
require 'spec/rake/spectask'

spec_files = Rake::FileList["spec/**/*_spec.rb"]

desc "Run specs"
Spec::Rake::SpecTask.new do |t|
  t.spec_files = spec_files
  t.spec_opts = ["-c"]
end

Cucumber::Rake::Task.new(:features) do |t|
  t.cucumber_opts = "features --format progress"
end

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gemspec|
    gemspec.name        = "ruby-warrior"
    gemspec.summary     = "Game written in Ruby for learning Ruby and artificial intelligence."
    gemspec.email       = "ryan@railscasts.com"
    gemspec.homepage    = "http://github.com/ryanb/ruby-warrior"
    gemspec.authors     = ["Ryan Bates"]
  end
rescue LoadError
  puts "Jeweler not available. Install it with: sudo gem install technicalpickles-jeweler -s http://gems.github.com"
end

task :default => [:spec, :features]
