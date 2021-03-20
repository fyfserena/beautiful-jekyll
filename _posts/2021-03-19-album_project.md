---
layout: post
title: Intelligent Album
subtitle: cs6998 Cloud Computing and Big Data Project 2
cover-img: /assets/img/album.JPG
tags: [full-stack, aws services, web app, cs6998]

---

A photo album web application, that can be searched using natural language through both text and voice by using Lex, ElasticSearch, and Rekognition services to create an intelligent search layer to query your photos for people, objects, actions, landmarks and more. 

Try it out! [here](http://cs6998-hw2-frontend.s3-website-us-west-2.amazonaws.com/)

You can:

1. Visit your photo album application using the S3 hosted URL.
2. Search photos using natural language via voice and text.
3. See relevant results (ex. If you searched for a animal, you should be able to see photos with animals in them) based on what you searched.
4. Upload new photos (with or without custom labels) and see them appear in the search results.



In this web app, I used so many AWS services!

- Store my front-end files and uploaded photos at AWS S3 
- Build the upload and search APIs at API Gateway
- Write the logics in Lambda functions
- Build and train the bot using Amazon Lex
- Detect labels on Rekognition 
- Store and search data within and Elasticsearch
- Deploy my code using CodePipeline
- Create a AWS CloudFormation template for the stack

While building this web app, I familiarized myself with

CodePipeline, CloudFormation, Angular framework, REST API.

Such a fun and bittersweet process! (It only takes me 5 days! hw1 took me 2 weeks...)
