---
layout: post
title:  "Stufe 1: TODO-App Deployment Google Cloud Run"
date:   2024-06-14 10:24:28 +0200
permalink: /todo-app/
---

Nutzt ein bereitgestelltes Container Image mit einer TODO-App und deploye sie auf Google Cloud Run.
Die Applikation soll danach im öffentlichen Internet über einen Web-Browser aufrufbar sein.

Hinweise:
- Port im Container: 8080.
- Region: `europe-west3`
- Vergebt einen Service name, der mit Eurem Team Namen beginnt.
- Registry / Image: `europe-west3-docker.pkg.dev/viadee-pulumi-training/demo-app/quarkus-todo-app:1.0`