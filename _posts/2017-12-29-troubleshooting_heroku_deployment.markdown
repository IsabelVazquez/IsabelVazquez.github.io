---
layout: post
title:      "Troubleshooting Heroku Deployment"
date:       2017-12-30 00:18:11 +0000
permalink:  troubleshooting_heroku_deployment
---


I deployed a Rails backend and a React frontend to Heroku, but they were not corresponding as intended. When I signed up a user on the frontend, I got a 500 error. However, checking the database with the commands below, I saw that users were created. The Rails backend must not be giving back the correct JSON response. 

```
$ heroku pg:psql
database=> SELECT * FROM users;
```

In order to see the issue in real time, I entered the following in the Heroku CLI `heroku logs --tail`. I then logged in a user through my React frontend to see where my production backend broke. The issue ended up being that while my ENV variables were configured on Heroku (e.g. heroku config:set AUTH_KEY=1234), I had an uninitialized constant Auth class for JWT authentication. 

When I entered `heroku run rails console` and `Auth`, I saw the same uninitialized error. However, when I ran `rails console ` on my local backend, Auth was initialized. Auth was added from my lib/ directory to the Rails auto path in development but not production. I ended up moving the Auth.rb file from the lib/ directory to the app/ directory as all app/ code is automatically loaded by Rails. 

Although there was other troubleshooting prior to deploying on Heroku, I highly recommend popping the production hood through **heroku logs --tail** and **heroku pg:psql**.
