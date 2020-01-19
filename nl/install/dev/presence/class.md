---
title: Presence Klasse
description: De belangrijkste klasse voor elke PreMiD presence
published: true
date: 2019-10-06T23:18:10.415Z
tags:
---

# Presence Klasse

## Introductie

De `Presence` klasse is erg handig omdat deze over basismethoden beschikt die we nodig hebben om presence te creëren.

 Wanneer u een klasse aanmaakt, dient u de eigenschap `clientId` te specificeren.

```typescript
let presence = new Presence({
    clientId: "514271496134389561" // Voorbeeld clientId
});
```

Er zijn twee eigenschappen beschikbaar voor `Presence` class.

#### `clientId`

`clientId` eigenschap moet worden verstrekt om uw presence te laten werken, omdat het uw applicatie id gebruikt om het logo en de assets weer te geven.

Je kunt het op je [applicatiepagina](https://discordapp.com/developers/applications) krijgen.

#### `mediaKeys`

Deze eigenschap vertelt onze app om sleutels te registreren voor mediaknoppen en stelt ons in staat `MediaKeys` event te gebruiken voor de `Presence` class.

Deze eigenschap is niet vereist, maar als je de mediaknoppen wilt inschakelen, moet je hem instellen op `true`.

**Alle mediaKey events zijn tijdelijk uitgeschakeld!**

```typescript
let presence = new Presence({
    clientId: "514271496134389561",
    mediaKeys: true // Staat gebruikers toe om media keys te gebruiken
});
```

## Methodes

### `setActivity(presenceData, Boolean)`

Stelt uw profielactiviteit in volgens de verstrekte gegevens.

De eerste parameter vereist een `presenceData` interface om alle informatie te krijgen die je wilt weergeven in je profiel.

Tweede parameter definieert wanneer presence iets afspeelt of niet. Gebruik altijd `true` als u timestamps verstrekt in `presenceData`.

### `clearActivity()`

Wist je huidige activiteit, de keybinds en de titel van het vak.

### `setTrayTitle(String)`

> Deze methode werkt alleen op Mac OS. 
> 
> {.is-warning}

Stelt de systeemtitel in op de menubalk.

### `getStrings(object)`

Maakt het mogelijk om vertaalde teksten van de extensie te krijgen. U moet `Object` opgeven met sleutels die de sleutel voor teksten zijn, `keyValue` is de waarde van de tekst. U kunt sommige teksten vinden met dit eindpunt: `https://api.premid.app/v2/langFIle/extension/en`

```typescript
// Retourneert `Playing` en `Paused` strings
// uit extensie.
strings = await presence.getStrings({
    play: "presence.playback.playing",
    pause: "presence.playback.paused"
});
```

### `getPageLetiable(String)`

Retourneert een variabele van de website als deze bestaat.

```typescript
var pageVar = getPageLetiable('.pageVar');
console.log(pageVar); // Dit zal de "Variabele content" loggen
```

## `presenceData` Interface

De `presenceData` interface wordt aanbevolen om te gebruiken wanneer u de `setActivity()` methode gebruikt.

Dit scherm volgt variabelen, ze zijn allemaal optioneel.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Variabele</th>
      <th style="text-align:left">Beschrijving</th>
      <th style="text-align:left">Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">details</td>
      <td style="text-align:left">De eerste regel in uw presence, meestal gebruikt als header.</td>
      <td style="text-align:left"><code>String</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">state</td>
      <td style="text-align:left">Tweede regel in uw presence.</td>
      <td style="text-align:left"><code>String</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">startTimestamp</td>
      <td style="text-align:left">Definieert de huidige tijd.<br>
        Wordt gebruikt als je wilt weergeven hoeveel <code>uur:minuten:seconden</code> er over is.
          <br>Je moet je tijd omzetten in <code>timestamp</code> anders krijg je een verkeerde
          aftelling.
      </td>
      <td style="text-align:left"><code>Number</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">endTimestamp</td>
      <td style="text-align:left">Definieert de volledige duur.
        <br>Gebruikt als je wilt laten zien hoeveel <code>uren:minuten:seconden</code> er over is.
          <br>Je moet je tijd omzetten in <code>timestamp</code> anders krijg je een verkeerde
          aftelling.
      </td>
      <td style="text-align:left"><code>Number</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">largeImageKey</td>
      <td style="text-align:left">Definieert het logo voor de presence.</td>
      <td style="text-align:left"><code>String</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">smallImageKey</td>
      <td style="text-align:left">Definieert het kleine pictogram naast presence&apos;s logo.</td>
      <td style="text-align:left"><code>String</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">smallImageText</td>
      <td style="text-align:left">Definieert de tekst die wordt getoond aan de gebruiker wanneer hij over de kleine
        pictogram beweegt.</td>
      <td style="text-align:left"><code>String</code>
      </td>
    </tr>
  </tbody>
</table>

```typescript
var presenceData: presenceData = {
    details: "Mijn titel",
    state: "Mijn beschrijving",
    largeImageKey: "service_logo",
    smallImageKey: "small_service_icon",
    smallImageText: "Je hebt me bekeken, en wat nu?" ,
    startTimestamp: 1564444631188,
    endTimestamp: 1564444634734
};
```

## Events

Events stellen je in staat om wijzigingen of oproepen die zijn gemaakt te detecteren en te verwerken. Je kunt je abonneren op event met behulp van `on` methode.

```typescript
presence.on("UpdateData", async () => {
    // Doe iets wanneer data wordt bijgewerkt.
});
```

Er zijn een paar Events beschikbaar:

#### `UpdateData`

Dit evenement wordt afgevuurd elke keer dat de presence wordt bijgewerkt.

#### `MediaKeys` (uitgeschakeld)

Schiet af wanneer de gebruiker gebruik maakt van mediaknoppen op zijn toetsenbord, [klik hier](/dev/presence/class#mediakeys) voor meer informatie over mediaknoppen.

#### `iFrameData`

Wordt afgevuurd wanneer gegevens worden ontvangen uit iFrame script.