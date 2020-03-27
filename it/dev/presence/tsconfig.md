---
title: Pagina senza titolo
description: Un piccolo aiuto per TypeScript
published: vero
date: 2020-02-12T22:15:34.451Z
tags:
---

# Configurazione TypeScript

## Introduzione

Quando hai scaricato e disimballato lo spazio di lavoro, vedrai un file chiamato `tsconfig. s` nelle cartelle root e presenza, questo file viene utilizzato per configurare il compilatore **TypeScript**. È già configurato per te, quindi non preoccuparti di questo.

Vogliamo solo descrivere alcune impostazioni che dovresti sapere.

## Configurazione Root

Nel file di configurazione root vedrai qualcosa di simile.

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

| ProprietÃ           | Descrizione                                                                                     |
|:------------------- |:----------------------------------------------------------------------------------------------- |
| **compilerOptions** | Utilizzato per configurare il compilatore, la maggior parte delle proprietà si trova qui.       |
| Modulo              | Puoi leggere di più su questo [qui](https://www.typescriptlang.org/docs/handbook/modules.html). |
| target              | Definisce la versione JavaScript che stai compilando.                                           |
| rimuoviCommenti     | Rimozione commenti dai file compilati.                                                          |
| **escludi**         | Qui puoi definire le cartelle che vuoi escludere dalla compilazione futura.                     |

## Configurazione Presenza

```javascript
{
  "extends": "../tsconfig.json",
  "compilerOptions": {
    "outDir": "./dist/"
  }
}
```

| ProprietÃ           | Descrizione                                                                                          |
|:------------------- |:---------------------------------------------------------------------------------------------------- |
| **estende**         | Utilizzato per estendere il file base `tsconfig` per varie attività.                                 |
| **compilerOptions** | Vedi [**Configurazione Root**](/dev/presence/tsconfig#root-configuration) per maggiori informazioni. |
| outDir              | Definisce la directory di output per i file compilati.                                               |