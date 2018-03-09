---
layout: post
title:      "Deployment Considerations"
date:       2018-03-09 18:20:15 +0000
permalink:  deployment_considerations
---


As my Vineyard Companion App's front-end styling is steadily nearing completion the foremost thought in my mind is how to deploy the project so it may be used as a demo. Many coders have mentioned Heroku, a Cloud Application Platform to do this. The reason being that Heroku supports a number of languages during app deployment. 

What to keep in mind when deploying a Sinatra or Rails app is to utilize Postgres instead SQLite to handle your data. This is because SQLite is not considered for Production grade databases as opposed to Postgres. Here are a few steps to make the transition to Postgres if you already have SQLite established in your app:

1- Remove SQLite from your Gemfile

```
gem 'sqlite3'
```

2- Replace with the Postgres Gem

```
gem 'pg'
```

3- Run 'Bundle Install'

4-  Convert your config/database.yml or environment.rb file and change the adapter from

```
adapter: sqlite3
```

to

```
adapter: postgresql
```

5- Change the database: to a custom name for example:

```
database: my_database
```

6- Once the pg gem is installed and migrated your config/database.yml / envrironemnt.rb file you will need to create your database and run any pre existing migrations against it:

```
rake db:create
rake db:migrate
```

Pushing to Heroku using Rails a development grade postgres will be connected to your app automatically.
In the instance of an app being run other than Rails you need to run:

```
heroku addons:create heroku-postgresql
```

**If there is an error make sure to check the Gemfile.lock  to make sure sqlite3 isn't in there, otherwise remove it and bundle install again


I look forward to deploying my app soon to bring vineyard/wine enthusiasts a sensible solution to paper reviews. Be sure to follow my github to look for future updates [Vineyard Companion](https://github.com/SarahCyrDesign/vineyard_companion)

