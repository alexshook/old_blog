---
layout: post
title: "Rspec 1.x for Rails 2"
date: 2015-07-23 18:00:14 -0400
comments: true
categories: rails
published: false
---

Nothing against Minitest, but I've been a fan of Factory Girl since I got more serious about testing with Rspec.

I believe 1.3.x is the last available minor version for Rspec 1.x.

Gemfile:
gem "rspec", "1.3.0"
gem "rspec-rails", "1.3.2”

or plugin if you prefer that.

Once you have your gems or plugins, run this:

ruby script/generate rspec

I told it to overwrite the file. It’s a safe bet if you don’t actually have any tests. (Well I think there are some Rails built-in, but I could never get those to work).

  exists lib/tasks
  create lib/tasks/rspec.rake
  create script/autospec
overwrite script/spec? (enter "h" for help) [Ynaqdh] Y
  force script/spec
  create spec
  create spec/rcov.opts
  create spec/spec.opts
  create spec/spec_helper.rb

Run script/generate --help if you want to verify that all your rspec generators got where they were supposed to.

The command to run tests is not rspec. it’s also not bundle exec rspec, bundle exec spec, or spec. it’s rake spec, and if it runs and produces no output, you’re in the clear.

If if runs and tell you your test database creation is totally messed up, run a migration and un mess it up. Table columns with varchar(0) will probably fail. (I don’t even know how those got in there).

now to figure out the syntax…
https://www.relishapp.com/rspec/rspec-rails/docs/upgrade/from-1x-to-2x

http://rspec.info/blog/2012/06/rspecs-new-expectation-syntax/


this would not have been possible without these links:
the rspec-rails 1.x repo for rails 2 - https://github.com/dchelimsky/rspec-rails
general rspec info (though mostly rails 3 i think) - https://github.com/dchelimsky/rspec/wiki/config.gem-%28for-Rails%29
basic spec wiki - https://github.com/dchelimsky/rspec/wiki/rails
how i figured out you are supposed to call it with spec and not rspec - http://stackoverflow.com/questions/6215571/no-such-file-to-load-rspec-matchers-rspec-rails-shoulda-cucumber-factory


