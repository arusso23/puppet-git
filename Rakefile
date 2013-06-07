require 'rake'

begin
  require 'rspec/core/rake_task'
  require 'puppet-lint/tasks/puppet-lint'
  PuppetLint.configuration.ignore_paths = ["pkg/**/*.pp","spec/**/*.pp"]
rescue LoadError
  require 'rubygems'
  retry
end

RSpec::Core::RakeTask.new(:spec) do |t|
  t.pattern = 'spec/*/*_spec.rb'
end

task :default => [:spec, :lint]
