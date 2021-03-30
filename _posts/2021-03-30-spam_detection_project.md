---
layout: post
title: Spam Detection
subtitle: cs6998 Cloud Computing and Big Data Project 3
tags: [full-stack, aws services, web app, cs6998]

---

We implemented a machine learning model to predict whether a message is spam or not. Furthermore, we created a system that upon receipt of an email message, it will automatically flag it as spam or not, based on the prediction obtained from the machine learning model.

Try it out! Send any message to 6998hw3service@junyang.site. You will get a response message with a predicted result that classified your message as a spam or a ham. 



In this web app, I used so many AWS services!

- Train machine learning models on **SageMaker**
- Build the email auto receiver and sender on **SES**
- Store received emails on **S3** and trigger a Lambda function that extracts the body of the email and uses the prediction endpoint to predict if the email is spam or not.
- Create a AWS CloudFormation template for the stacks
- Deploy my code using CodePipeline



Such a fun and bittersweet process! (It only takes me 2 days since I find a great teammate now!)