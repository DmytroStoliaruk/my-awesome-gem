# frozen_string_literal: true

require "yaml"
require "json"

require "bundler/gem_tasks"
require "rspec/core/rake_task"
require "standard/rake"

require "yaml_to_json_fastify"

YamlToJsonFastify.configure do |config|
  config.exclude_patterns = []
end

RSpec::Core::RakeTask.new(:spec)

task :prep_build do
  YamlToJsonFastify::Base.convert("/Users/user/GitHub/Rails/my-awesome-gem/devise.uk.yml", false)
end

task build: :prep_build

task default: %i[spec standard]
