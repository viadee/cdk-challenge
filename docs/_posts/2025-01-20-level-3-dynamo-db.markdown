---
layout: default
title:  "Level 3: Connect the Message-Function with a Dynamo-DB"
date:   2025-01-20 00:00:00 +0200
permalink: /dynamo-db/
---

Deploy the Message-Function (of level 1) with a Dynamo-DB to persist the messages.

Notes:
- It is possible to keep using the same Image for the function. But you have to provide a environment varibale and a policy, to persist the data.
- Deploy a Dynamo-DB with CDK:
  - Create a Partition-Key with the name `id` of type `String`.
  - Create a Table (with your project name as a prefix).
  - Set the `removalPolicy` for the table to `DESTROY`. This configuration ensures that your Stack is reproducible.
- Connect the database to your Message-Function.
  - Set the environment variable `DYNAMODB_TABLE_NAME` to `<YOUR_TABLE_NAME>`.
  - Add a new policy to the Lambda-Function. Use the <i>Action</i> `dynamodb:PutItem` with the <i>Effect</i> `ALLOW` with a reference to your Table-resource.
- Check the AWS UI if the messages are persisted.

Please note: The creation of the Table and Partition-Key needs a few seconds. A great opportunity for some pizza 🍕 
