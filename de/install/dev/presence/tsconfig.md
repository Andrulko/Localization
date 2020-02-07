---
title: Unbenannte Seite
description: Ein kleiner Helfer für TypeScript
published: true
date: 2020-01-19T23:42:36.260Z
tags:
---

# TypeScript-Konfiguration

## Einführung

Wenn Sie den Arbeitsbereich heruntergeladen und entpackt haben, wird eine Datei mit dem Namen `tsconfig.js` im Stammverzeichnis und in den Anwesenheitsordnern angezeigt. Diese Datei wird zum Konfigurieren des **TypeScript** Compilers verwendet. Es ist bereits für Sie konfiguriert, machen Sie sich also keine Sorgen.

Wir wollen nur einige Einstellungen beschreiben, die Sie kennen sollten.

## Root-Konfiguration

In der Root-Konfigurationsdatei sehen Sie so etwas.

```javascript
{
  "compilerOptions": {
    "module": "commonjs",
    "target": "es6",
    "removeComments": true
  },
  "exclude": ["node_modules"]
}
```

| Eigentum            | Beschreibung                                                                                              |
|:------------------- |:--------------------------------------------------------------------------------------------------------- |
| **compilerOptions** | Die meisten Eigenschaften, die zur Konfiguration des Compilers verwendet werden, befinden sich hier.      |
| Modul               | Mehr über diese [hier lesen](https://www.typescriptlang.org/docs/handbook/modules.html).                  |
| Ziel                | Definiert die zu kompilierende JavaScript-Version.                                                        |
| removeComments      | Kommentare aus kompilierten Dateien entfernen.                                                            |
| **ausschließen**    | Hier können Sie die Ordner definieren, die Sie von der zukünftigen Zusammenstellung ausschließen möchten. |

## Anwesenheitskonfiguration

```javascript
{
  "extended": "../tsconfig.json",
  "compilerOptions": {
    "outDir": "./dist/"
  }
}
```

| Eigentum            | Beschreibung                                                                                                |
|:------------------- |:----------------------------------------------------------------------------------------------------------- |
| **erweitert**       | Wird zum Erweitern der Datei base `tsconfig` für verschiedene Aufgaben verwendet.                           |
| **compilerOptions** | Weitere Informationen finden Sie unter [**Root-Konfiguration**](/dev/presence/tsconfig#root-configuration). |
| outDir              | Definiert das Ausgabeverzeichnis für kompilierte Dateien.                                                   |