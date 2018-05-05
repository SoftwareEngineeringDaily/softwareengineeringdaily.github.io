---
title: Getting Started
category: Monitoring
order: 1
---

### Installation and Running ###
You can either run InfluxDB locally or using Docker

***Locally***
1. [Pull the repo](https://github.com/SoftwareEngineeringDaily/sedaily-devops)
2. [Install and run a local InfluxDB client](https://github.com/influxdata/influxdb)
3. _cp env.local_example .env_
4. _npm install_
5. _npm start_

***Using Docker***
1. [Pull the repo](https://github.com/SoftwareEngineeringDaily/sedaily-devops)
2. _cp env.docker_example .env_
3. _docker-compose up_

_(Check package.json for other builds)_

### Testing the Backend ###

1. use curl or Postman to make requests
2. visit [http://localhost:3000/api/v1/docs](http://localhost:3000/api/v1/docs) to see the API documentation


> To get used to the codebase, it might help to solve an [issue with the "good first issue" label](https://github.com/SoftwareEngineeringDaily/sedaily-devops/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22).
