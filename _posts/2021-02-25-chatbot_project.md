---
layout: post
title: Dining Concierge chatbot
subtitle: cs6998 Cloud Computing and Big Data Project 1
cover-img: /assets/img/chatbot.JPG
thumbnail-img: /assets/img/chatbot.JPG
tags: [aws services, web app, cs6998]
---

Customer Service is a core service for a lot of businesses around the world and it is getting disrupted at the moment by Natural Language Processing-powered applications. 

Dining Concierge chatbot is a server-less, microservice-driven web application. It sends you restaurant suggestions given a set of preferences that you provide the chatbot with through conversation.

Try it out! [here](https://fyfserena.github.io/cloud-hw1-starter/chat.html)

In this web app, I used so many AWS services!

- Store my front-end files at AWS S3 
- Build the APIs at API Gateway
- Write the logics in Lambda functions
- Build and train the chatbot using Amazon Lex
- Scrape and parse data from Yelp
- Store and search data within DynamoDB and Elasticsearch
- Push the information collected from the user to an SQS 
- Set a CloudWatch event trigger to pull the data from SQS
- Send recommendation information to user's phone via SMSmessages
- Most importantly, IAM!!! (tons of permission policies need to set😫)

While building this web app, I familiar myself with

Cross-Origin Resource Sharing concept, parsing html, json format, node.js, *AWS* Command Line, NoSQL database,...

Such a fun and bittersweet process!
