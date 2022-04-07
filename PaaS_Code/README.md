# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

My URL: https://damp-mountain-85806.herokuapp.com/

##Install the pre-requisites
1.Download Heroku CLI from: https://devcenter.heroku.com/articles/heroku-cli

2.Download Ruby version 2.6.9 for Windows from: https://www.ruby-lang.org/en/downloads/

3.Download RubyMine from: https://www.jetbrains.com/ruby/download/#section=windows
1. Make sure when installing to configure PATH(Restart needed) otherwise you're going to have a abad time...

##Configure RubyMine
1.Open RubyMine and click File->Settings

2.Click Languages and Frameworks->Ruby SDK And Gems

3.Click the + Icon and select Ruby 2.6.9-p207 then select it by clicking the Radio button

4.Once list populates, click apply and exit the Settings.

##Managing The Code
I made a new github repository just in case I made any changes that messed up the code. Github Desktop helps revert changes
1.Open Github Desktop and create new repository called: PaaS_Assignment

2.Push To Origin

3.Unzip code into repository source file

4.Commit changes and push to origin

1. Now any changes you make that mess up the code can be reverted by discarding changes in GitHub Desktop

5.Open terminal and `cd PaaS_Code` to get to proper directory for deployment

1. To verify proper directory type`ls` and the following should be listed:

```azure
d-----        2022-04-06  10:48 AM                .idea
d-----        2022-04-06   9:37 AM                app
d-----        2022-04-07   5:54 PM                bin
d-----        2022-04-07   5:54 PM                config
d-----        2022-04-07   5:54 PM                db
d-----        2022-04-06   9:37 AM                lib
d-----        2022-04-07   5:54 PM                log
d-----        2022-04-07   5:54 PM                public
d-----        2022-04-07   5:54 PM                spec
d-----        2022-04-07   5:54 PM                tmp
d-----        2022-04-07   5:54 PM                vendor
-a----        2022-04-07   5:54 PM            571 .gitignore
-a----        2022-04-07   5:54 PM             22 .rspec
-a----        2022-04-07   5:54 PM             11 .ruby-gemset
-a----        2022-04-07   5:54 PM              9 .ruby-version
-a----        2022-04-07   5:54 PM            161 config.ru
-a----        2022-04-07   5:54 PM            890 docker-compose.yml
-a----        2022-04-07   5:54 PM            977 Dockerfile
-a----        2022-04-07   5:54 PM          31459 erd.pdf
-a----        2022-04-07   6:11 PM           2623 Gemfile
-a----        2022-04-07   5:54 PM           9153 Gemfile.lock
-a----        2022-04-07   5:54 PM           1557 Guardfile
-a----        2022-04-07   5:54 PM             69 package.json
-a----        2022-04-07   5:54 PM            258 Rakefile
-a----        2022-04-07   7:22 PM           1658 README.md

```
6.In Gemfile, underneath where it says: `source 'https://rubygems.org'`, add `ruby '2.6.9'`, without this code, an error will be thrown during deployment

7.In Terminal type `bundle install` to update Gemfile.lock

##Dealing with Heroku
1.Start by going to: https://dashboard.heroku.com and creating an account
1. Be sure to verify the account

2.Back in RubyMine terminal type: `heroku login`, you should see a prompt asking you to hit a key to go to browser login, hit any key

3.You should now be redirected to the browser where if you're still logged in to heroku you should just have to click Log In and it will tell you to go back to the IDE

4.In Terminal type the following commands:

1. `git init`
2. `git add .`
3. `git commit -m "init"`

5.Create a Heroku app with the following command in terminal: `heroku create`

6.Push the git commit to heroku with: `git push heroku master`

1.  After this command succeeds it will give you a URL your app is deployed to, in my case it's: https://damp-mountain-85806.herokuapp.com/

7.If previous command succeeded as it should, migrate the heroku database with: `heroku run rake db:migrate`

8.To seed the database: `heroku run rake db:seed`

9.That's it, you're done, to view the new site visit the link given to you after the heroku push to master and you should see a login page

1. Create an account with a username and password
2. Login and now you should see 50 articles, each with 10 comments