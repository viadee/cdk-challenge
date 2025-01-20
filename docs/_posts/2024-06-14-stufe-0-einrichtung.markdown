---
layout: default
title:  "Stufe 0: Einrichtung AWS-Account und CDK"
date:   2024-06-14 10:24:28 +0200
permalink: /einrichtung/
---

Nutzt den bereitgestellten AWS Account und logged euch ein:

[https://975050296970.signin.aws.amazon.com/console](https://975050296970.signin.aws.amazon.com/console)


Erzeugt und speichert Euren `ACCESS_KEY` und `SECRET_KEY` über die AWS UI:

``` 
viadee-cloudland24-cdk-challenge @ 9750-5029-6970 > 
Sicherheitsanmeldeinformationen > 
Zugriffschlüssel erstellen > 
Befehlszeilenschnittstelle (CLI)
```

Login per AWS CLI mit den erzeugten Keys in der Region `eu-central-1`:

```bash
aws configure
```

Prüft den erfolgreichen Login per:

```
aws sts get-caller-identity
```

Überlegt Euch einen Teamnamen und und erzeugt ein Verzeichnis per `mkdir -p <team_name>`. 
Wechselt in dieses Verzeichnis und erzeugt ein neues CDK Projekt in Eurer Wahlsprache (z.B. `java`, `typescript`, `go`):

```bash
cdk init --language <LANG>
```

Im erzeugten Projekt befindet sich auskommentierter Code zum Erzeugen einer SQS Queue. Aktiviert den Code und erzeugt euren CDK Stack:

```bash
cdk deploy
```

Öffnet AWS CloudFormation und prüft, dass dort Eure Queue angelegt wurde: 

[https://eu-central-1.console.aws.amazon.com/cloudformation](https://eu-central-1.console.aws.amazon.com/cloudformation)

Sprecht uns an, zeigt uns Eure Ergebnisse und wir zeigen Euch den Weg zu Level 1.

(Optional) Bereinigt die erzeugte Infrastruktur:

```bash
cdk destroy
```