---
title: Application Architecture
category: High Level
order: 2
---

The SE Daily ecosystem is comprised of the following  components: Wordpress site, Node.js REST API, Mongo database, iOS app, Android app, Vue.js front end, devops project platform, and the data miner.



### Wordpress Site

The Wordpress site [softwareengineeringdaily.com](https://softwareengineeringdaily.com/) is the source of data used by the SE Daily API and associated clients. When new episodes of the podcast are published, a new post on the Wordpress CMS is created containing the episode description and the audio links.

### Data Miner

The [sedaily-miner](https://github.com/SoftwareEngineeringDaily/sedaily-miner) project runs on Heroku. Its periodically scheduled cron job runs to scrape data from the [Wordpress API](https://softwareengineeringdaily.com/wp-json) and input it into the staging and production MongoDB instance. The MongoDB instance is the database that the REST API reads from and also runs on Heroku.

Contributors will have to run the miner locally against a local MongoDB instance in order to have data for the API to serve. Alternatively, contributors can pull and run a pre-mined [Docker image](https://hub.docker.com/r/softwaredaily/sedaily-mongo/).

<img src="/images/high_level.png" alt="Open Source Guide logo">

### Mongo Database

### Node.js REST API

### iOS Application 

### Android Application

### Vue.js Website

### Devops Platform

