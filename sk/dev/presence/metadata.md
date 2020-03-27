---
title: Metadata.json
description: Obsahuje základné údaje o Prítomnosti
published: true
date: 2020-02-22T23:18:54.250Z
tags:
---

# Metadata.json

Ak chcete zverejniť prítomnosť v obchode a načítať ju prostredníctvom rozšírenia, mali by ste vytvoriť `metadata.json` súbor vo vašom `presence.js` priečinku.

Príklad tohto súboru je uvedený nižšie.

```javascript
{
  "author": {
    "name": "UŽÍVATEĽ",
    "id": "ID"
  },
  "contributors": [{
    "name": "UŽÍVATEĽ",
    "id": "ID "
  }],
  " service ":"SLUŽBA",
  " description ": {
    " sk ":" POPIS "
  },
  " url ":" URL ",
  " regExp ":" REGEXP ",
  "iFrameRegExp": "REGEXP",
  "version": "VERZIA",
  "logo": "URL",
  "thumbnail": "URL",
  "color": "# 45A8FC",
  "tags": ["KATEGÓRIA", "ŠTÍTKA"],
  "category": "KATEGÓRIA",
  "iframe": false
}
```

## Porozumenie metadata.jsonu

Ten príklad vyzerá naozaj čudne, hm? Nerobte si starosti nie je to také ťažké pochopiť pre čo sú jednotlivé premenné.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Premenná</th>
      <th style="text-align:left">Popis</th>
      <th style="text-align:left">Typ</th>
      <th style="text-align:left">Nepovinné</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>autor</b>
      </td>
      <td style="text-align:left">Mal by obsahovať Objekt s <code>menom</code> a <code>id</code> vývojára prítomnosti. Meno je vaše Discord užívateľské meno bez identifikátoru(#0000). Užívateľské <code>id</code> možno skopírovať z Discordu povolením mód vývojára         a kliknutím pravým tlačítkom na váš profil.</td>
      <td style="text-align:left"><code>Objekt</code>
      </td>
      <td style="text-align:left"><code>Nie</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>prispievatelia</b>
      </td>
      <td style="text-align:left">Mal by obsahovať Objekt s <code>menom</code> a <code>id</code> vývojára prítomnosti. Meno je vaše Discord užívateľské meno bez identifikátoru(#0000). Užívateľské <code>id</code> možno skopírovať z Discordu povolením mód vývojára         a kliknutím pravým tlačítkom na váš profil.</td>
      <td style="text-align:left"><code>Poradie&lt;Objekt&gt;</code>
      </td>
      <td style="text-align:left"><code>Áno</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>služba</b>
      </td>
      <td style="text-align:left">Názov služby ktorú táto prítomnosť podporuje.</td>
      <td style="text-align:left"><code>Reťazec</code>
      </td>
      <td style="text-align:left"><code>Nie</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>popis</b>
      </td>
      <td style="text-align:left">Malý popis prítomnosti, môžete použiť popis služby        ak nemáte žiadne nápady. Váš popis musí mať hodnoty párov kľúčov ktoré označujú jazyk, a popis v tom konkrétnom jazyku. Urobte popisy s jazykmi <i>ktoré poznáte</i>, naši prekladatelia ich zmenia vo vašich metadata súborov. View the category for presence languages for a list. </td>
      <td style="text-align:left"><code>Objekt</code>
      </td>
      <td style="text-align:left"><code>Nie</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>url</b>
      </td>
      <td style="text-align:left">URL of the service.<br><b>Example:</b><code>vk.com</code><br>
        <b>This url must match the url of the website as it will be used to detect wherever or not this is the website to inject the script to. This may only be used as an array when there are more than one urls.</b>
      </td>
      <td style="text-align:left"><code>Reťazec, Poradie&lt;String&gt;</code>
      </td>
      <td style="text-align:left"><code>Nie</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>regExp</b>
      </td>
      <td style="text-align:left">Reťazec regulárneho výrazu používaný na zhodovanie adries url.</td>
      <td style="text-align:left"><code>Reťazec</code>
      </td>
      <td style="text-align:left"><code>Áno</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>verzia</b>
      </td>
      <td style="text-align:left">Verzia vašej prítomnosti.</td>
      <td style="text-align:left"><code>Reťazec</code>
      </td>
      <td style="text-align:left"><code>Nie</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>logo</b>
      </td>
      <td style="text-align:left">Odkaz na službu&apos; s logotypom.</td>
      <td style="text-align:left"><code>Reťazec</code>
      </td>
      <td style="text-align:left"><code>Nie</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>náhľad</b>
      </td>
      <td style="text-align:left">Odkaz na náhľad vašej prítomnosti.</td>
      <td style="text-align:left"><code>Reťazec</code>
      </td>
      <td style="text-align:left"><code>Nie</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>farba</b>
      </td>
      <td style="text-align:left"><code>#HEX</code> hodnota. Odporúčame vám používať primárnu farbu služby        ktorá vaša prítomnosť podporuje.</td>
      <td style="text-align:left"><code>Reťazec</code>
      </td>
      <td style="text-align:left"><code>Nie</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>štítky</b>
      </td>
      <td style="text-align:left">Pole so značkami, pomôže používateľom vyhľadávať vašu prítomnosť na webovej stránke.</td>
      <td
      style="text-align:left"><code>Reťazec, Poradie&lt;String&gt;</code>
        </td>
      <td style="text-align:left"><code>Nie</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>kategória</b>
      </td>
      <td style="text-align:left">Reťazec použitý na označenie kategórie do ktorej patrí.</td>
      <td style="text-align:left"><code>Reťazec</code>
      </td>
      <td style="text-align:left"><code>Nie</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>iframe</b>
      </td>
      <td style="text-align:left">Určuje či je použitý <code>iFrames</code></td>
      <td style="text-align:left"><code>Boolean</code>
      </td>
      <td style="text-align:left"><code>Áno</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>iFrameRegExp</b>
      </td>
      <td style="text-align:left">Selektor regulárneho výrazu ktorý vyberá prvky iframe do ktorých sa má vložiť.</td>
      <td style="text-align:left"><code>Reťazec</code>
      </td>
      <td style="text-align:left"><code>Áno</code>
      </td>
    </tr>
  </tbody>
</table>

## Regulárny Výraz

Ak sa chcete naučiť regulárne výrazy, tu je niekoľko webových stránok.

#### Učenie

• [RegexOne](https://regexone.com/) • [Regular Expressions Info](https://www.regular-expressions.info/tutorial.html)

#### Testovanie

• [Regexr](https://regexr.com/) • [Regex101](https://regex101.com/)

## Presence languages

PreMiD is a polygot service, meaning there are a multitude of languages involved to connect users around the globe. A full list of languages can be found with this [API endpoint](https://api.premid.app/v2/langFile/list).

## Kategórie prítomností

Ak vytvárate prítomnosť, musíte uviesť kategóriu do ktorej táto prítomnosť patrí. Toto je zostavený zoznam kategórií ktoré môžete použiť.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Kategória</th>
      <th style="text-align:left">Názov</th>
      <th style="text-align:left">Popis</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>anime</b></td>
      <td style="text-align:left"><b>Anime</b></td>
      <td style="text-align:left">Čokoľvek sa týka anime, od forúmov až po platformy na streamovanie videa.</td>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>games</b></td>
    <td style="text-align:left"><b>Hry</b></td>
      <td style="text-align:left">Akákoľvek webová stránka ktorá má obsah súvisiaci s hrami, ako napríklad <code>Kahoot</code> alebo <code>Skribbl.io</code></td>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>music</b></td>
    <td style="text-align:left"><b>Hudba</b></td>
      <td style="text-align:left">Toto sú webové stránky ktoré ponúkajú hudobný obsah, či už ide o streamovanie alebo sťahovanie.</td>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>socials</b></td>
        <td style="text-align:left"><b>Sociálne siete</b></td>
      <td style="text-align:left">Webové stránky ktoré sa používajú na vytváranie a zdieľanie obsahu alebo na účasť na iných formách sociálnych sietí.</td>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>videos</b></td>
        <td style="text-align:left"><b>Videá & Streamy</b></td>
      <td style="text-align:left">Webové stránky ktoré slúžia na poskytovanie videí a streamov.</td>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>other</b></td>
    <td style="text-align:left"><b>Ostatné</b></td>
      <td style="text-align:left">Čokoľvek čo nespadá do špecifickej kategórie uvedenej vyššie.</td>
      </td>
    </tr>
  </tbody>
</table>