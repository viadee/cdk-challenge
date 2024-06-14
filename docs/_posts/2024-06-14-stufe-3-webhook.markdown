---
layout: post
title:  "Stufe 3: Function als Endpunkt für den TODO-App Webhook"
date:   2024-06-14 10:24:28 +0200
permalink: /webhook/
---

Die TODO-APP aus dem letzten level bietet einen HTTP-Webhook an.
Hierfür gilt es mit einer GCP Cloud Function einen Endpunkt bereitszustellen.

Hinweise:
- Denkt immernoch daran Eure Ressourcen mit Eurem Team Namen vorne weg zubenennen.
- Deployt eine Google Cloud Function, die den HTTP-Request-Body des Aufrufs mit `console.log` ins Log schreibt und mit dem HTTP-Status-Code 200 antwortet.
- Bei Nutzung von `gcp.cloudfunctions.HttpCallbackFunction` könnt Ihr den Quelltext der Funktion direkt in den Pulumi-Code einbetten.
- Konfiguriert die TODO-App so, dass die neue Funktion bei jeder Aktion an einem TODO-Element aufgerufen wird.
    - Nutzt hierzu die Umgebungsvariable `QUARKUS_REST_CLIENT_WEBHOOK_URL`.
- Überprüft, dass die Aktionen nun ins Log der Funktion geschrieben werden:


```bash
gcloud functions list
gcloud functions logs read <function-name>
```