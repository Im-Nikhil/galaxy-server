# Netflix OSS on Heroku Demo

This project demonstrates the use of Netflix OSS with Spring Cloud on Heroku.

## Quickstart

[![Deploy to Heroku](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)

## Production Deployment

First, [create a Heroku account](http://dashboard.heroku.com)
and then [download and install the Heroku toolbelt](http://toolbelt.heroku.com).

Then clone this project and move into it.

```
$ git clone git@github.com:kissaten/heroku-eureka-demo.git
$ cd heroku-eureka-demo/
```

Next, create an application by running this command:

````sh-session
$ heroku create
Creating fast-beach-5250... done, stack is cedar-14
https://fast-beach-5250.herokuapp.com/ | https://git.heroku.com/fast-beach-5250.git
Git remote heroku added
```

Now you'll need to create a configation variable to set the default user's
password. Run this command, btu substitue a unique password for `<PASSWORD>`:

```
$ heroku config:set EUREKA_USER_PASSWORD=<PASSWORD>
```

You're ready to deploy. There two methods you can use: Git deployment, and
Maven deployment. The former compiles the application remotely, while the latter
uses locally compiled aritfacts and pushes them to Heroku.

### Deploying with Git

With you're application prepared (as describe above), simply run this command to
deploy:

```
$ git push heroku master
```

Your code will be pushed to the remote Git repository, and the Maven process
will execute on the Heroku servers.

### Deploying with Maven

With you're application prepared, simply run this command to
deploy (but replace `<appname>`  with the name of the application you created):

```
$ mvn -Dheroku.appName=<appname> heroku:deploy
```

## Viewing Your Application

When your chosen deployment method is finished, run this command to view
your application:

```
$ heroku open
```

The browser will prompt you for credentials. Enter "user" for the username,
and the unique password you set as a configuration variable.

## Further Reading

+  [Spring Cloud Netflix documentation](http://projects.spring.io/spring-cloud/spring-cloud.html#_spring_cloud_netflix)
+  [Netflix Eureka](https://github.com/netflix/eureka)
