---
title: Metadata.json
description: Obsahuje základní údaje o přítomnosti
published: true
date: 2020-01-19T23:42:34.658Z
tags:
---

# Metadata.json

Pokud chcete publikovat přítomnost v obchodě a nahrát jej prostřednictvím rozšíření, měli byste vytvořit `metadata. syn` soubor ve složce `presence.js`.

Příklad tohoto souboru je uveden níže.

```javascript
{
  "author": {
    "name": "USER",
    "id": "ID"
  },
  "přispěvatelé": [{
    "name": "USER",
    "id": "ID"
  }],
  "service": "SERVICE",
  "description": {
    "c": "DESCRIPTION"
  },
  "url": "URL",
  "regregExp": "REGEXP",
  "iFrameRegExp": "REGEXP",
  "verze": "VERSION",
  "logo": "URL",
  "thumbnail": "URL",
  "color": "#45A8FC",
  "tags": ["KATEGORI", "TAG"],
  "Kategorie": "KATEGORI",
  "iframe": false
}
```

## Pochopení metadata.json

Tento příklad se zdá opravdu zvláštní, že? Nebojte se, není tak těžké pochopit, k čemu je každá proměnná.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Proměnná</th>
      <th style="text-align:left">Popis</th>
      <th style="text-align:left">Typ</th>
      <th style="text-align:left">Nepovinné</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>autor</b>
      </td>
      <td style="text-align:left">Mělo by obsahovat objekt s <code>názvem</code> a <code>id</code> vývojáře přítomnosti. Jméno je tvé Discord uživatelské jméno bez identifikátoru (#0000). Uživatelské <code>id</code> lze zkopírovat z Discordu povolením módu vývojáře
        a kliknutím pravým tlačítkem myši na tvůj profil.</td>
      <td style="text-align:left"><code>Objekt</code>
      </td>
      <td style="text-align:left"><code>Ne</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>přispěvatelé</b>
      </td>
      <td style="text-align:left">Mělo by obsahovat objekt s <code>názvem</code> a <code>id</code> vývojáře přítomnosti. Jméno je tvé Discord uživatelské jméno bez identifikátoru (#0000). Uživatele <code>id</code> lze zkopírovat z Discordu povolením módu vývojáře
        a kliknutím pravým tlačítkem myši na tvůj profil.</td>
      <td style="text-align:left"><code>Pole&lt;Object&gt;</code>
      </td>
      <td style="text-align:left"><code>Ano</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>služba</b>
      </td>
      <td style="text-align:left">Název služby, kterou tato přítomnost podporuje.</td>
      <td style="text-align:left"><code>Řetězec</code>
      </td>
      <td style="text-align:left"><code>Ne</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>popis</b>
      </td>
      <td style="text-align:left">Malý popis přítomnosti, můžete použít popis služby
        , pokud nemáte nápady. Tvůj popis musí obsahovat hodnoty klíčů označující jazyk a popis v tomto konkrétním jazyce. Vytvářejte popisy s jazyky <i>, které znáte</i>, naši překladatelé budou provádět změny ve vašem souboru metadat.</td>
      <td style="text-align:left"><code>Objekt</code>
      </td>
      <td style="text-align:left"><code>Ne</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>URL</b>
      </td>
      <td style="text-align:left">Adresa URL služby.<br><b>Příklad:</b><code>vk. om</code><br>
        <b>Tato adresa URL musí odpovídat URL webu, protože bude použita k detekci, kde je nebo není tato stránka k vložení skriptu.</b>
      </td>
      <td style="text-align:left"><code>Řetězec, pole&lt;String&gt;</code>
      </td>
      <td style="text-align:left"><code>Ne</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>regExp</b>
      </td>
      <td style="text-align:left">Regulární výraz řetězec používaný pro odpovídající URL adresy.</td>
      <td style="text-align:left"><code>Řetězec</code>
      </td>
      <td style="text-align:left"><code>Ano</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>verze</b>
      </td>
      <td style="text-align:left">Verze vaší přítomnosti.</td>
      <td style="text-align:left"><code>Řetězec</code>
      </td>
      <td style="text-align:left"><code>Ne</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>logo</b>
      </td>
      <td style="text-align:left">Odkaz na službu&apos; s logotypem.</td>
      <td style="text-align:left"><code>Řetězec</code>
      </td>
      <td style="text-align:left"><code>Ne</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>náhled</b>
      </td>
      <td style="text-align:left">Odkaz na náhled vašeho stavu.</td>
      <td style="text-align:left"><code>Řetězec</code>
      </td>
      <td style="text-align:left"><code>Ne</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>barva</b>
      </td>
      <td style="text-align:left"><code>#HEX</code> hodnota. Doporučujeme použít primární barvu služby
        , kterou vaše přítomnost podporuje.</td>
      <td style="text-align:left"><code>Řetězec</code>
      </td>
      <td style="text-align:left"><code>Ne</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>štítky</b>
      </td>
      <td style="text-align:left">Pole se značkami, které pomohou uživatelům vyhledat vaši přítomnost na webu.</td>
      <td
      style="text-align:left"><code>Řetězec, pole&lt;String&gt;</code>
        </td>
      <td style="text-align:left"><code>Ne</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Kategorie</b>
      </td>
      <td style="text-align:left">Řetězec používaný k reprezentaci kategorie, pod kterou přítomnost spadá.</td>
      <td style="text-align:left"><code>Řetězec</code>
      </td>
      <td style="text-align:left"><code>Ne</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>iframe</b>
      </td>
      <td style="text-align:left">Určuje, zda jsou použity <code>iFrames</code></td>
      <td style="text-align:left"><code>Boolean</code>
      </td>
      <td style="text-align:left"><code>Ano</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>iFrameRegExp</b>
      </td>
      <td style="text-align:left">Regulární selektor, který vybere iframy, do kterých se má vložit.</td>
      <td style="text-align:left"><code>Řetězec</code>
      </td>
      <td style="text-align:left"><code>Ano</code>
      </td>
    </tr>
  </tbody>
</table>

## Řádné výrazy

Pokud se chcete naučit regulární výrazy, zde je několik webových stránek.

### Učení

• [RegexOne](https://regexone.com/) • [Informace o regulárních výrazech](https://www.regular-expressions.info/tutorial.html)

### Testování

• [Regexr](https://regexr.com/) • [Regex101](https://regex101.com/)

## Kategorie přítomnosti

Při zjišťování přítomnosti musíte specifikovat kategorii, do které přítomnost spadá. Toto je sestavený seznam kategorií, které můžete použít.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Kategorie</th>
      <th style="text-align:left">Jméno</th>
      <th style="text-align:left">Popis</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>anime</b></td>
      <td style="text-align:left"><b>Anime</b></td>
      <td style="text-align:left">Cokoli se týká anime, od fór až po platformy pro video streamování.</td>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>hry</b></td>
    <td style="text-align:left"><b>Hry</b></td>
      <td style="text-align:left">Jakékoli webové stránky, které mají obsah související s hrou, jako je <code>Kahoot</code> nebo <code>Skribbl.io</code></td>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>hudba</b></td>
    <td style="text-align:left"><b>Hudba</b></td>
      <td style="text-align:left">Toto jsou webové stránky, které nabízejí hudební obsah, ať už se jedná o streamování nebo stahování.</td>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>sociální sítě</b></td>
        <td style="text-align:left"><b>Sociální sítě</b></td>
      <td style="text-align:left">Internetové stránky, které se používají pro vytváření a sdílení obsahu nebo pro účast v jiných formách sociálních sítí.</td>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>videa</b></td>
        <td style="text-align:left"><b>Videa & Streamy</b></td>
      <td style="text-align:left">Internetové stránky, které slouží k poskytování videí a streamů.</td>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>ostatní</b></td>
    <td style="text-align:left"><b>Ostatní</b></td>
      <td style="text-align:left">Cokoliv, co nespadá do konkrétní kategorie uvedené výše.</td>
      </td>
    </tr>
  </tbody>
</table>