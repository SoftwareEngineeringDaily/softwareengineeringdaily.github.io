---
title: Application Architecture
category: High Level
order: 2
---

The SE Daily ecosystem is comprised of the following  components: Wordpress site, Node.js REST API, Mongo database, iOS app, Android app, Vue.js front end, devops project platform, and the data miner. For more information on any of the projects see the menu.


### Wordpress Site

The Wordpress site [softwareengineeringdaily.com](https://softwareengineeringdaily.com/) is the source of data used by the SE Daily API and associated clients. When new episodes of the podcast are published, a new post on the Wordpress CMS is created containing the episode description and the audio links.

### Data Miner

The [sedaily-miner](https://github.com/SoftwareEngineeringDaily/sedaily-miner) project runs on Heroku. Its periodically scheduled cron job runs to scrape data from the [Wordpress API](https://softwareengineeringdaily.com/wp-json) and input it into the staging and production MongoDB instance. The MongoDB instance is the database that the REST API connects to and also runs on Heroku.

Contributors will have to run the miner locally against a local MongoDB instance in order to have data for the API to serve. Alternatively, contributors can pull and run a pre-mined [Docker image](https://hub.docker.com/r/softwaredaily/sedaily-mongo/). Use the `docker-compose.yml` file found in the web front end and API projects for reference.

<img src="/images/wordpress_miner.png" title="Wordpress Data Miner" alt="Wordpress Data Miner">

### Mongo Database

The Mongo database runs in production and staging as a Heroku add-on to the REST API application. Data is mined from the Wordpress site to MongoDB and transformed to suit the needs of the client applications.

### Node.js REST API

The REST API allows authenticated iOS, Android, and Vue.js web front end clients to connect and get necessary data.

<img src="/images/rest_api.png" title="Wordpress Data Miner" alt="Wordpress Data Miner">

### iOS, Android, Vue.js and Web Frontend

Used in conjunction with the REST API, these are the clients for the Software Daily platform. The Web frontend is hosted on Heroku.

### Devops Platform

The devops platform is an event processing infrastructure server allowing clients of Software Daily to send events such as episode plays, user registrations, and errors originating from the REST API. Data is streamed to an InfluxDB instance and then displayed using Grafana. The Node.js API responsible for ingesting events is hosted on Heroku while the InfluxDB and Grafana instances are hosted on an AWS EC2 instance.
