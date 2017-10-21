---
title: Helpful Tips
category: Backend
order: 1
---

If you are already running mongo locally make sure to stop it if you want to interface with the docker mongo database using something like [RoboMongo](https://robomongo.org/)

*Helpful commands if using brew:*
>brew services list
>brew services stop mongodb
>brew services start mongodb

A few other helpful tips for docker are that you can see which containers are running and ssh into them:
>docker container ls

Since we are running a command when docker starts you need to create a new bash shell when you ssh:

>sudo docker exec -i -t CONTAINER_ID_HERE  /bin/bash

To start the server do this inside of the backend repo:

>docker-compose up

To shut it down use:

>docker-compose down

To run another configuration for docker use:

>docker-compose -f  docker.alt.yml  up

Note for running the tests (?):
docker-compose.test.yml NEEDS to have docker-compose up before or redis wont be available
Also note your database gets cleared on docker down:
Your .env file will differ if running inside docker vs locally.  Change redis to be ‘localhost’ and mongo ip to also be localhost.

** Sample Post You can use to populate your DB (remove id for multiple entries): **

>{
    "_id" : ObjectId("59dcec425aa447d81ed0f05f"),
    "date" : ISODate("2017-09-10T15:50:03.543Z"),
    "score" : 33.0,
    "categories" : [
        1082,
        99
    ],
    "content" : {
        "protected" : false,
        "rendered" : ""
    },
    "title" : {
        "rendered" : "Bitcoin Segwit with Jordan Clifford --- Original"
    },
    "featuredImage" : "http://softwareengineeringdaily.com/wp-content/uploads/2017/10/BitcoinSegwit.jpg",
    "link" : "https://softwareengineeringdaily.com/2017/10/10/bitcoin-segwit-with-jordan-clifford/",
    "mp3" : "http://traffic.libsyn.com/sedaily/BlocksizeDebate.mp3"
}
