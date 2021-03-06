# frozen_string_literal: true

source 'https://rubygems.org/'

git_source :github do |repo|
  "https://github.com/#{repo}.git"
end

ruby '2.6.5'

# Return early if this file is parsed by the Bundler plugin DSL.
# This won't let us access dependencies in common-gems.
return if is_a?(Bundler::Plugin::DSL)

gem 'rails', '~> 6.0.2'

# Load common gems
%w(
  rails
  redis
).each do |m|
  eval_gemfile File.join('common-gems', m, 'Gemfile')
end

gem 'dotenv-rails',                             '~> 2.7'
gem 'envkey',                                   '~> 1.0', '!= 1.2.6', require: false # v1.2.6 breaks loading env vars in test env
gem 'gems',                                     '~> 1.2', require: false
gem 'git',                                      '~> 1.5'
gem 'rails_bootstrap_navbar',                   '~> 3.0'
gem 'sidekiq',                                  '~> 5.0'

group :development do
  gem 'spring',                                 '~> 2.0'
  gem 'spring-watcher-listen',                  '~> 2.0'
end
