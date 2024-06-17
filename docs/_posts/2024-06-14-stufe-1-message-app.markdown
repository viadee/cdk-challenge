---
layout: post
title:  "Stufe 1: Message-App Deployment als Lambda-Function"
date:   2024-06-14 10:24:28 +0200
permalink: /message-app/
---

Nutzt ein bereitgestelltes Container Image mit einer Message-App und deploye sie als Lambda-Function.
Die Applikation soll dann direkt als Lambda in der AWS GUI aufrufbar sein: 

Hinweise:
- Gebt der Lambda Function einen Namen, der mit Eurem Team Namen beginnt.
- Registry / Image: `975050296970.dkr.ecr.eu-central-1.amazonaws.com/cdk-challenge-message-receiver:latest`
- ECR Registry-Name: `cdk-challenge-message-receiver`
- Wir empfehlen Euch ein Repository-Construct in eurem CDK-Project anzulegen, damit ihr die Lambda erzeugen könnt
- Zum Testen klickt bei Eurer Function auf Test und sendet ein SQS-Event (Vorlage: `sqs-receive-message`)