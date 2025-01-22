---
layout: default
title:  "Level 0: Setup AWS-Account and CDK"
date:   2025-01-20 00:00:00 +0200
permalink: /setup/
---

Use the provided credentials and login to AWS:

[https://975050296970.signin.aws.amazon.com/console](https://975050296970.signin.aws.amazon.com/console)


Create and save your `ACCESS_KEY` and `SECRET_KEY` through the AWS UI:


``` 
viadee-cdk-challenge @ 9750-5029-6970 > 
Security credentials > 
Create access key > 
Command Line Interface (CLI)
```

Use the created keys to login to the region `eu-central-1`:

```bash
aws configure
```

Check if the login was successfully:

```
aws sts get-caller-identity
```

Think about an unique project name and create a folder with `mkdir -p <project_name>`.
Go to the directory and create a CDK projekt in your language of choice (e.g. `java`, `typescript`, `go`).


```bash
cdk init --language <LANG>
```

In your project should be commented code to create a SQS Queue. Activate the code and create your CDK stack:

```bash
cdk deploy
```

Open AWS CloudFormation und check the created queue:

[https://eu-central-1.console.aws.amazon.com/cloudformation](https://eu-central-1.console.aws.amazon.com/cloudformation)

If you completed the level, talk to the tutor. He will provide you the link to the next challenge.

(Optional) Clean up the created infrastructure:

```bash
cdk destroy
```

<br>
<br>
<hr>

<b>Side Note</b>: If the commented queue is not available in your project, this is how it looks like in `typescript`:

```
    import * as sqs from 'aws-cdk-lib/aws-sqs';
    ...
    //example resource
    const queue = new sqs.Queue(this, 'ExampleProjectQueue', {
        visibilityTimeout: cdk.Duration.seconds(300)
    });
    ...
```

Adapt it to your programming language of choice and add it to the stack. You will need the Queue later on.