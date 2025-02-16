---
layout: default
title:  "Stufe 3: Message-Function mit Dynamo-DB"
date:   2024-06-14 10:24:28 +0200
permalink: /de/dynamo-db/
---

Deployed die Message-Function aus Level-1 mit einer Dynamo-DB zur persistenten Datenhaltung.

Hinweise:
- Ihr könnt das gleiche Image für die Function verwenden. Allerdings müsst ihr eine Umgebungsvariable und Policy hinzufügen, damit die Daten gespeichert werden. 

- Deployed eine Dynamo-DB mittels CDK:
    - Erzeugt einen Partition-Key mit dem Namen `id` vom Typ `String`.
    - Erzeugt eine Tabelle mit Eurem Teamnamen vorne weg.
    - Setzt die `removalPolicy` für die Tabelle auf `DESTROY`, damit Euer Stack reproduzierbar gebaut werden kann.
- Bindet die Datenbank an die Message-Function an.
    - Setzt die Umgebungsvariable in `DYNAMODB_TABLE_NAME`: `<EUER_TABELLEN_NAME>`
    - Fügt der Lambda-Function eine Policy mit der Action `dynamodb:PutItem` und dem Effect `ALLOW` auf die Table-Resource hinzu.
- Überprüft, dass Message-Einträge in der DB persistiert werden.

Achtung: Die Instanzierung der Tabelle und des Partition-Keys braucht etwas Zeit. Eine gute Gelegenheit, um sich zum Beispiel mit etwas zu trinken zu versorgen.