---
title: How It Works
category: Newsfeed
order: 2
---
The current system is very simple.

1. Users add "related links" to episodes ([shown here](http://www.softwaredaily.com/#/post/5a01cb36e7d98f052ceac1d2)).
2. Every 10 minutes, the [sedaily-feed-service](https://github.com/SoftwareEngineeringDaily/sedaily-feed-service) runs. It does 2 things: [adds images to the related links](https://github.com/SoftwareEngineeringDaily/sedaily-feed-service/blob/master/relatedlinks-add-images.js) and [generates a new feed for every user](https://github.com/SoftwareEngineeringDaily/sedaily-feed-service/blob/master/index.js).

The current feed is the same for everyone.
