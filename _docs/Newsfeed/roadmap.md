---
title: Roadmap
category: Newsfeed
order: 3
---

### Improved design

The design of the feed will be [more visually appealing](https://github.com/SoftwareEngineeringDaily/sedaily-front-end/issues/113).

### Personalization

Each user should have a personalized feed. For the first version of this, we will:
1. [Associate links with tags](https://github.com/SoftwareEngineeringDaily/sedaily-feed-service/issues/7)
2. [Model the tag interests of each user](https://github.com/SoftwareEngineeringDaily/sedaily-feed-service/issues/8)
3. Modify the feed builder to prioritize links that fit the interests of users

### Continuous Updates

The current system updates every 10 minutes, and recalculates the user's entire new feed. We need to build a more continuous system.

This will be assisted by the [sedaily-event-stream](https://github.com/SoftwareEngineeringDaily/sedaily-event-stream).
