---
title: Getting Started
category: Backend
order: 1
---

>If you get confused at any point, please [message us in Slack](http://softwaredaily.herokuapp.com/)!

_Docker makes this project easier to work with. But if you don’t know [how to use Docker](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-getting-started), and you want to get started fast, that’s OK too._

### Installation ###

***If you don’t want to use Docker***
1. [Pull the repo](https://github.com/SoftwareEngineeringDaily/software-engineering-daily-api)
2. [Install and run a local redis client](https://redis.io/topics/quickstart)
3. [Install and run a local mongo client](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/)
4. _cp .env.example .env_

In env file 
1. set _RACCOON_REDIS_URL_=localhost. 
2. set _MONGO_HOST_TEST=mongodb://localhost/express-mongoose-es6-rest-api-development-test_ and _NODE_ENV_=test if setting up _TEST_ environemnt.
3. set _MONGO_HOST=mongodb://localhost/express-mongoose-es6-rest-api-development_ and _NODE_ENV=development_ if setting up _DEVELOPMENT_ environemnt.


### Get Running ###

1. [Download some Mongo data to use locally](https://www.dropbox.com/sh/5o1193iesmiul9v/AADKLQgkZBlQzjHk6mBBnp6Da?dl=0) and unzip

Populate the database by running _mongorestore --db  sed-test sed-test-db_

2. Install and run the node project.

>npm install (or yarn install)

>npm start (or yarn start)

_(Then check package.json for other builds)_

### Test the Backend ###

1. use curl or Postman to make requests
2. Use RoboMongo to see the data in the database

>If you want to connect frontend to backend locally, [swap the comments here](https://github.com/SoftwareEngineeringDaily/sedaily-front-end/blob/master/src/store/actions/config.js).

### Getting Started with SE Daily using Docker

1. _cp .env.docker_example .env_
2. Run _docker-compose up_

> To get used to the codebase, it might help to solve an [issue with the "good first issue" label](https://github.com/SoftwareEngineeringDaily/software-engineering-daily-api/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22).
