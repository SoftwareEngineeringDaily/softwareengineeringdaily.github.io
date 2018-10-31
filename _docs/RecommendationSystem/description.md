---
title: Description
category: Recommendation System
order: 1
---

The goal of the Software Daily feed is to provide content about software that is relevant to user interests. Imagine a Facebook or LinkedIn feed where all the content is related to software and technology. This document outlines a high level strategy for implementing the Software Daily Feed System 2.0. The scope of this document is to describe the backend. Once we have a good feed algorithm, SED will invest more capital into building nice interfaces to serve it (web, Android, and iOS client improvements). Creating a good feed in Software Daily requires us to have a high volume of content and user data and then matching users to content.

### Ingesting Content

Our current 1.0 feed is generated from the “related links”. The disadvantage of related links is that they are manually added. 

We need to get content from Hacker News. We will periodically pull from the HN API to get the top 100 stories, except the ones we have already pulled. We should store urls of these stories in a document store, such as Google Cloud BigTable. When we pull content into BigTable, we should label it “unclassified”.

Whenever we pull urls into our content database, we should enrich it with images, keywords, and metadata from the article. That way we can serve rich FeedItems like you see in other news feeds.

Hacker News is a good place to start because it has a great API. Future sources of content: newsletters, Hacker Noon, Dev.to, Pocket

<img src="/images/feed_contentIngester.png" title="Content Ingester" alt="Content Ingester">


### Classifying Content

In order to recommend content to users, we need to classify the content. Stories that are related to security, or ReactJS, or Kubernetes should be labeled as such. There are many ways to build a classifier. We could use Diffbot or Google APIs. We can periodically get all “unclassified” documents from BigTable and run them through our ContentClassifier. 

After a piece of content is classified, it will have a vector associated with it. Perhaps something like:
{“security”: .63, “Kubernetes”: .73, “Bitcoin” : .22}

We should also run the transcripts of our episodes through the same classification system, so that our podcast episodes are classified.

<img src="/images/feed_content_classification.png" title="Content Classification" alt="Content Classification">


### User Data
In order to match users with classified content, we need to infer the interests of our users. We do this by:

1. Logging the episodes that our users listen to
1. Logging the content that our readers read
1. Using the classifications of that content to build a PreferenceSet for each user

A user PreferenceSet might look like:
{“JavaScript”: .89, “cryptocurrencies”: .2, “management”: .83}

We build a PreferenceSet for a user by taking the average of vectors from articles/podcasts they consume. The result should be a vector of preferences and a number between 0 and 1 for each preference.

This represents phase 2 of the PreferenceBuilder. For phase 1, in order to develop a minimum viable product, we will initially build a user survey and build a user PreferenceSet from that.


<img src="/images/feed_preferenceSet.png" title="Preference Set" alt="Preference Set">


### Assembling a Feed

Once we have a PreferenceSet for a user, we can start customizing a feed for that user. The steps for constructing a feed will look something like this:
Take the user’s PreferenceSet (a vector)
Get 200 random documents from BigTable (and the classification vectors of each); these are the “CandidateDocuments”
Remove from the CandidateDocuments all the articles that the user has already read
Sort the 200 CandidateDocuments by their vector similarity to the UserPreference vector
Those 200 CandidateDocuments are the resulting news feed for the user.

<img src="/images/feed_feedAssembly.png" title="Feed Assembly" alt="Feed Assembly">


