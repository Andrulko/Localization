---
title: Strana bez názvu
description: Malilinký pomocník pre TypeScript
published: true
date: 2020-01-18T20:33:00.222Z
tags:
---

# Konfigurácia TypeScriptu

## Úvod

Keď ste si stiahli a rozbalili pracovnú plochu, uvidíte súbor nazývaný sa `tsconfig.js` v koreni a v priečinkoch prítomnosti, tento súbor je určený na konfigurovanie **TypeScript** spracovávateľa. Je už dopredu nakonfigurovaný pre vás, takže nemusíte sa obávať.

Chceme vám len popísať niektoré nastavenia ktoré by ste mali vedieť.

## Konfigurácia Koreňa

V koreni konfiguračného súboru uvidíte niečo takéto podobné.

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

| Vlastnosť           | Popis                                                                                            |
|:------------------- |:------------------------------------------------------------------------------------------------ |
| **compilerOptions** | Používaný na konfiguráciu kompiliera, väčšina vlastností sa nachádza tu.                         |
| module              | Môžete si prečítať viacej o tom [tu](https://www.typescriptlang.org/docs/handbook/modules.html). |
| target              | Definuje verziu JavaScriptu ktorú kompilujete.                                                   |
| removeComments      | Odstránenie komentárov z už kompilovaných súborov.                                               |
| **exclude**         | Tu môžete definovať priečinky ktoré chcete vylúčiť z budúcej kompilácie.                         |

## Konfigurácia Prítomnosti

```javascript
{
  "extends": "../tsconfig.json",
  "compilerOptions": {
    "outDir": "./dist/"
  }
```

| Vlastnosť           | Popis                                                                                            |
|:------------------- |:------------------------------------------------------------------------------------------------ |
| **extends**         | Používa sa na rozšírenie základného súboru `tsconfig` na rôzne úlohy.                            |
| **compilerOptions** | Pozrite [**Koreň Konfigurácie**](/dev/presence/tsconfig#root-configuration) pre viac informácii. |
| outDir              | Definuje výstupný adresár pre kompilované súbory.                                                |