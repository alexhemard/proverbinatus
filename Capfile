require "rvm/capistrano"
require "bundler/capistrano"

load 'deploy'

default_run_options[:pty] = true

set :application, "proverbinatus"
server "proverbinatus.com", :app, :web, :primary => true

set :scm, :git
set :repository, "git@github.com:csampson/proverbinatus.git"
set :ssh_options, { :forward_agent => true }

set :user, "deploy"
set :use_sudo, false
set :deploy_to, "/var/www/proverbinatus.com"

set :branch, "master"
set :deploy_via, :remote_cache

set :bundle_without,  [:development]

before "deploy:restart", "bundle:install"

