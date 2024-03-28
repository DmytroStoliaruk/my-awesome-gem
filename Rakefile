# frozen_string_literal: true

# it is necessary for local version of yaml_to_json_fastify gem
$LOAD_PATH.unshift(File.expand_path('/Users/user/GitHub/Rails/yaml-to-json-fastify/lib', __dir__))

require "bundler/gem_tasks"
require "rspec/core/rake_task"
require "standard/rake"

require "yaml"
require "json"
require "yaml_to_json_fastify"
require_relative "lib/my/awesome/gem"

YamlToJsonFastify.configure do |config|
  config.exclude_patterns = ["devise.*", "some_file.yml"]
end

RSpec::Core::RakeTask.new(:spec)

task :prep_build do
  # convert all files exclude exclude_patterns
  # YamlToJsonFastify::Base.convert  
  
  # read formatted data depends on enviroment
  # use RAKE_ENV=development rake build for convert files in development
  # use RAKE_ENV=production rake build for convert files in production
  YamlToJsonFastify::Base.load_formatted_data("en.uk.yml")
end

task build: :prep_build

task default: %i[spec standard]

