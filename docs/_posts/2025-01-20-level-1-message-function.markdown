---
layout: default
title:  "Level 1: Deployment of the Message-App as a Lambda-Function"
date:   2025-01-20 00:00:00 +0200
permalink: /message-function/
---

Use the provided container image of the Message-App and deploy it as a Lambda-Function.
The application should be callable through the AWS UI.

Notices:
- Use your project name as a prefix for the name of the Lambda-Function.
- Set the value `ARM_64` for `architecture` of your function.
- Registry / Image: `975050296970.dkr.ecr.eu-central-1.amazonaws.com/cdk-challenge-message-receiver:latest`
- ECR Registry-Name: `cdk-challenge-message-receiver`.
- We recommend to create an Repository-Construct in your CDK project to create the Lambda with the Image.
- Testing: Click on "Test" on your Function and send a SQS-Event (Template-Name: `sqs-receive-message`).