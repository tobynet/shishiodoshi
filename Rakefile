require 'travis'

task :default => :travis_restart

desc 'call travis to build restart'
task :travis_restart do
  Travis.access_token = ENV['TRAVIS_TOKEN']
  build = Travis::Repository.find(ENV['TRAVIS_BUILD'])
  build.last_build.restart
end
