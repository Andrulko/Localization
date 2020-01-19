---
title: iFrame Class
description:
published: vero
date: 2020-01-18T20:32:55.147Z
tags:
---

# iFrame Class
> Il sistema iframe con PreMiD è problematico e può avere un comportamento inaspettato, utilizzare con attenzione. 
> 
> {.is-danger}

## Introduzione

In alcuni scenari, la tua presence può avere bisogno di accedere ad elementi posizionati dentro `iframe`.

Il codice che scrivi dentro il tuo file `iframe.ts` verrà iniettato in ogni iframe della pagina.

Come le presence, gli `iframe` hanno le loro classi progettate per aggiornare i dati automaticamente.

```typescript
let iframe = new iFrame();

iframe.on("UpdateData", async () => {
    // Il codice va qui...
});
```

## Metodi

### `send(Object)`
Manda dati alla presence. Usare questo metodo permetterà alla presence di lanciare un evento `iFrameData`.

### `getUrl(String)`
Ritorna l'URL dell'`iframe`.

## Eventi
Negli `iframe` gli eventi funzionano similmente a come funzionano nella classe della `Presence`.

```typescript
iframe.on("UpdateData", async () => {
    // Il codice va qui...
});
```

Qui c'è una lista di tutti gli eventi:

#### `UpdateData`

Questo evento è lanciato ogni volta che un iframe viene aggiornato.

#### `MediaKeys` (disabilitato)

Lanciato quando un utente utilizza i tasti media sulla sua tastiera, [clicca qua](/dev/presence/class#mediakeys) per ottenere più informazioni riguardo i tasti media.