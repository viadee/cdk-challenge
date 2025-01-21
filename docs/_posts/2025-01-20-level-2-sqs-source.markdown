---
layout: default
title:  "Level 2: SQS-Queue as Source for the Lambda-Function"
date:   2024-06-14 10:24:28 +0200
permalink: /sqs-source/
---

The Lambda should receive the message of the SQS queue, which has been created at the beginning.
CDK provides Event Sources to connect the queue with the function.

Notes:
- Keep using your project name as the prefix for the resource names.
- Deploy the Queue, if you missed that at the beginning.
- Use the AWS UI to check that the SQS Queue is the source for the Lambda-Function.
- Send a message to the Queue and check that the function has been called. 
- Use the follwing commands to check the event source of your function. 


```bash
aws lambda list-functions
aws lambda list-event-source-mappings --function-name <function-name>
```