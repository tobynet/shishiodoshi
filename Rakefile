require 'travis'
require 'yaml'

task :default => :travis_restart

desc 'call travis to build restart'
task :travis_restart do
  Travis.access_token = ENV['TRAVIS_TOKEN']
  builds = Travis::Repository.find_all(owner_name: Travis::User.current.login)
  builds.each.with_index do |build, index|
    puts "Travis Build restart(#{index+1}/#{builds.size}): #{build.slug}##{build.last_build_number}"
    build.last_build.restart
  end
end
