rspec2db: RSpec DB Formatter
============================

Database Formatter enables writing RSpec test results into a database

- Install postgres database 

- git clone this (rspec) repository

- gem build rspec2db.gemspec from "rspec" directory (to build the rspec2db gem)

- bundle install (to make sure you have the required gems)

- if bundle failed on pg gem instalation, try to use one of the following commands:
```
Mac OS X - gem install pg -v '0.14.1' -- --with-pg-config=#{PG_CONFIG_PATH} (e.g. /Applications/Postgres.app/Contents/Versions/9.3/bin/pg_config)
Note: If this does not work, try with: ARCHFLAGS="-arch x86_64" gem install pg -v '0.14.1'
Ubuntu - apt-get install libpq-dev before running gem install pg -v '0.14.1'
```

- gem install rspec2db-#{VERSION}.gem to install rspec2db gem (e.g. gem install rspec2db-0.1.3.gem)

- check rspec2db.yml (/rspec/config) configuration (db connection)

- create database if it does not already exist (it must match with database property specified in rspec2db.yml)

- execute rspec_db.rb (/rspec/config) to create tables and relations in the database (e.g.ruby rspec_db.rb)

- install rspec gem (e.g. sudo gem install rspec -v 2.13.0)

- initialize your RSpec project (e.g. rspec --init), if you don't have one already

- copy /rspec/config/rspec2db.yml to your rspec project (e.g. ./config/rspec2db.yml)

- check that .rspec file contains following:
```
--require rspec2db
--format Rspec2db
--options ./config/rspec2db.yml #--options with location to rspec2db.yml relative to .rspec file
```

- run RSpec tests using the rspec command (from the location where .rspec file exist, to be able to pick up parameters defined in .rspec) (e.g. rspec spec/spec_spec.rb)
