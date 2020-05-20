---
title: Třída přítomnosti
description: Hlavní třída pro každou přítomnost PreMiD
published: true
date: 2020-05-20T00:15:59.349Z
tags:
---

# Třída přítomnosti

## Úvod

Třída `Presence` je velmi užitečná, protože má základní metody, které potřebujeme k vytvoření přítomnosti.

 Při vytváření třídy musíte zadat `klientské Id`.

```typescript
let presence = new Presence({
    clientId: "514271496134389561" // Example clientId
});
```

Jsou k dispozici dvě vlastnosti pro `Presence` třídu.

#### `clientId`

Musí být poskytnuta vlastnost `klientských Id` , aby vaše přítomnost fungovala, protože používá ID vaší aplikace k zobrazení jejího loga a majetku.

Můžete to získat na stránce [aplikací](https://discordapp.com/developers/applications).

## Metody

### `getActivity()`

Returns a `presenceData` object of what the presence is displaying.

### `setActivity(presenceData, Boolean)`

Nastaví vaši aktivitu profilu podle zadaných dat.

První parametr vyžaduje rozhraní `přítomnostiData` pro získání všech informací, které chcete zobrazit ve vašem profilu.

Druhý parametr definuje, když přítomnost něco hraje nebo ne. Vždy používejte `tru` pokud poskytnete časové značky v `přítomnostiData`.

### `clearActivity()`

Vymaže vaši aktuální aktivitu, klávesové zkratky a název lišty.

### `setTrayTitle(String)`

> Tato metoda funguje pouze na Mac OS. 
> 
> {.is-warning}

Sets the tray title on the Menubar.

### `getStrings(Object)`

Allows you to get translated strings from extension. You must provide `Object` with keys being the key for string, `keyValue` is the string value. You can find the some of the strings using this endpoint: `https://api.premid.app/v2/langFIle/extension/en`

```typescript
// Returns `Playing` and `Paused` strings
// from extension.
strings = await presence.getStrings({
    play: "presence.playback.playing",
    pause: "presence.playback.paused"
});
```

### `getPageletiable(String)`

Returns a variable from the website if it exists.

```typescript
var pageVar = getPageletiable('.pageVar');
console.log(pageVar); // This will log the "Variable content"
```

### `getExtensionVersion(Boolean)`
Returns version of the extension the user is using.
```typescript
getExtensionVersion(onlyNumeric?: boolean): řetězec | number;

var numeric = presence.getExtensionVersion();
konzola. og(numeric); // Will log 210
var version = presence.getExtensionVersion(false);
console.log(version); // Will log 2.1.0
```

### `getSetting(String)`
Returns value of setting.
```typescript
var setting = await presence.getSetting("pdexID"); //Replace pdexID with the id of the setting
console.log(setting); // This will log the value of the setting
```

### `hideSetting(String)`
Hides given setting.
```typescript
presence.hideSetting("pdexID"); //Replace pdexID with the id of the setting
```

### `showSetting(String)`
Shows given setting (Only works if the setting was already hidden).
```typescript
presence.showSetting("pdexID"); //Replace pdexID with the id of the setting
```

## `přítomnostiData` Rozhraní

The `presenceData` interface is recommended to use when you are using the `setActivity()` method.

This interface has following variables, all of them are optional.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Proměnná</th>
      <th style="text-align:left">Popis</th>
      <th style="text-align:left">Typ</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Podrobnosti</td>
      <td style="text-align:left">První řádek v přítomnosti, obvykle používaný jako záhlaví.</td>
      <td style="text-align:left"><code>Řetězec</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">stav</td>
      <td style="text-align:left">Druhá linie v přítomnosti.</td>
      <td style="text-align:left"><code>Řetězec</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">startTimestamp</td>
      <td style="text-align:left">Definuje aktuální čas.<br>
        Používá se, pokud chcete zobrazit, kolik <code>hodin:minut:sekund</code> zbývá.
          <br>Musíte převést svůj čas na <code>časové razítko</code> nebo dostanete špatný
          odpočítávání.
      </td>
      <td style="text-align:left"><code>Číslo</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">endTimestamp</td>
      <td style="text-align:left">Definuje celou dobu trvání.
        <br>Používá se, pokud chcete zobrazit kolik <code>hodin:minut:sekund</code> zbývá.
          <br>Musíte převést svůj čas na <code>časové razítko</code> nebo dostanete špatný
          odpočítávání.
      </td>
      <td style="text-align:left"><code>Číslo</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">largeImageKey</td>
      <td style="text-align:left">Definuje logo pro přítomnost.</td>
      <td style="text-align:left"><code>Řetězec</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">smallImageKey</td>
      <td style="text-align:left">Určuje malou ikonu vedle loga&apos;s.</td>
      <td style="text-align:left"><code>Řetězec</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Malý obrázek</td>
      <td style="text-align:left">Definuje text, který se zobrazí uživateli, když se dotkne malé ikony
.</td>
      <td style="text-align:left"><code>Řetězec</code>
      </td>
    </tr>
  </tbody>
</table>

```typescript
var presenceData: presenceData = {
    details: "My title",
    state: "My description",
    largeImageKey: "service_logo",
    smallImageKey: "small_service_icon",
    smallImageText: "You hovered me, and what now?",
    startTimestamp: 1564444631188,
    endTimestamp: 1564444634734
};
```

## Události

Events allow you to detect and handle some changes or calls that were made. You can subscribe to events using the `on` method.

```typescript
presence.on("UpdateData", async () => {
    // Do something when data gets updated.
});
```

There are few events available:

#### `UpdateData`

This event is fired every time the presence is being updated.

#### `iFrameData`

Fired when data is received from iFrame script.
