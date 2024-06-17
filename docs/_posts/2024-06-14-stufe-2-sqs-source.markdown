---
layout: post
title:  "Stufe 3: SQS-Queue als Source für die Lambda-Function"
date:   2024-06-14 10:24:28 +0200
permalink: /webhook/
---

Die Message-Lambda soll mit Nachrichten aus der SQS Queue, die Ihr bei der Einrichtung angelegt habt, gestartet werden.
Hierfür bietet CDK mit Event Sources die Möglichkeit die Queue mit der Function zu verknüpfen.

Hinweise:
- Denkt immernoch daran Eure Ressourcen mit Eurem Teamnamen vorne weg zu benennen.
- Stellt die Queue bereit, falls Ihr das bei der Einrichtung versäumt habt.
- Überprüft, dass die Lambda-Function die SQS-Queue als Source darstellt.
- Stellt Nachrichten in die Eure Queue ein, um zu prüfen, ob die Lambda-Function aufgerufen wird.


```bash
aws lambda list-functions
aws lambda list-event-source-mappings --function-name <function-name>
```