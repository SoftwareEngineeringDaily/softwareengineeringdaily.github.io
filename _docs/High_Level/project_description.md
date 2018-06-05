---
title: Project Overview
category: High Level
order: 1
---

The Software Engineering Daily ecosystem comprises a [REST API](https://software-enginnering-daily-api.herokuapp.com/api/docs/), [Vue.js website](https://www.softwaredaily.com/), [iOS application](https://itunes.apple.com/us/app/software-engineering-daily-podcast-app/id1253734426?mt=8), [Android application](https://play.google.com/store/apps/details?id=com.koalatea.thehollidayinn.softwareengineeringdaily), a miner responsible for populating the database, and a logging and analytics application among a few others.

One of the most important components of the ecosystem is the [Wordpress site](https://softwareengineeringdaily.com/) that is the source of all data for the SE Daily ecosystem. Before there were any of the Software Engineering Daily [open source projects](https://github.com/SoftwareEngineeringDaily), there was the Software Engineering Daily wordpress site. When Jeff and the SE Daily team publish a new episode of the podcast, they create a new post on the Wordpress CMS containing the episode description and the audio links.

The REST API serves as the backend for the Android, iOS, and Vue.js web front end. Its MongoDB database is populated when the sedaily-miner scrapes the Software Engineering [Wordpress API](https://softwareengineeringdaily.com/wp-json) and inputs the resulting data into MongoDB.

See the [high level architecture](/High_Level/architecture/) for more information.
