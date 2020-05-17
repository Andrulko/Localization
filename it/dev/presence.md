---
title: Sviluppo Presence
description:
published: vero
date: 2020-05-17T14:23:17.252Z
tags:
---

> Tutte le presenze sono ora memorizzate qui: https://github.com/PreMiD/Presences 
> 
> {.is-info}

La versione `2.x` introduce il [negozio di presenze](https://premid.app/store). Gli utenti ora hanno la possibilità di aggiungere e rimuovere manualmente le loro presenze preferite tramite l'interfaccia utente del [sito web](https://premid.app/).

# Linee guida
> Se lo fai **NON** seguire le linee guida, un `Presence Verifier` richiederà le opportune modifiche, o dovrà chiuderlo in determinate circostanze. 
> 
> {.is-warning}

> Quando si fanno richieste di pull per l'aggiunta o la modifica di presenze esistenti, si **NECESSARIO** includere uno screenshot. Tuttavia, le modifiche di un Presence's `metadata.json` o `tsconfig.json` file fare **NON** richiedono uno screenshot. _Lo screenshot **DEVE** essere caricato direttamente su GitHub con la richiesta di pull, essegui <strong x-ir"1">NON</strong> utilizzare siti di condivisione di immagini di terze parti. _ 
> 
> {.is-warning}

Quando pubblichiamo Presenze su questo GitHub, ti richiediamo di seguire un insieme di linee guida. Per alcuni, queste regole severe possono sembrare dure. Tuttavia, l'attuazione di queste regole impedirà a noi e agli utenti di affrontare qualsiasi questione.

## Creazione
> Il codice scritto DEVE essere <em x-id"3">ben scritto</em> e DEVE essere <em x-id"3">leggibile</em>. `DeepScan` su GitHub segnalerà problemi di qualità al `Presence Verification Team`. Ti raccomandiamo di aggiorne il tuo fork quando fai richieste di pull, questo aiuterà a limitare i falsi positivi. 
> 
> {.is-warning}

- La pull request <strong x-id "1">DEVE</strong> é completa, é necessario avere una struttura di file appropriata, le bozze sono **NON** consentite. Compreso il file `presence.ts`, file `tsconfig.json` `dist` cartella, `presence.js` file, e `metada.json` file, che è rappresentato nello schema di esempio seguente:
```bash
siti web
├── {type}
    ├── presence
        ├── dist
        ├── metadata.json
        ├── presence.js
        ├── presence.ts
        ├── tsconfig.json
```
o se stai utilizzando `iframe`:
```bash
siti web
└── {type}
    └── presence
        ├── dist
        │   ├── metadata.json
        │   ├── presence.js
        │   └── iframe.js
        ├── presence.ts
        ├── iframe.ts
        └── tsconfig.json
```
- {type} sta per: Da A a Z, "#" per presenze di inizio non alfabetico e "0-9" per presenze che iniziano con i numeri.
<br>
Prima di iniziare a lavorare sulla tua presenza, tieni in mente il seguente elenco.
- La presenza **DEVONO** essere correlata al sito che hai scelto.
- La presenza **NON DEVE** essere di siti illegali. Tra questi, lo stressor, la droga, la pornografia infantile, eccetera.
- I metadati di Presence **DEVE** hanno contenuti ben scritti, inclusi titoli e descrizioni validi.
- The media you include ( icon/thumbnail ) **MUST** be related to the site and should be understandable in terms of size and quality.
- La struttura del file <strong x-id='"1">DEVONO</strong> essere pulita e gestita, <strong x-id="1">NON</strong> ha file casuali che non forniscono nulla alla funzione di Presence.</li>
<li>La presenza <strong x-id="1">NON DEVE</strong> essere di siti illegali. Queste includono informazioni private, impatto negativa sul comportamento del sito, ecc.</li>
<li>Se si progetta una Presence per un sito che cambia in futuro e di conseguenza potenzialmente rompendo la tua Presence, tu <strong x-id="1">SONO</strong> sei responsabile di aggiornarla per funzionare come previsto. Se non lo corregi <strong x-id="1">NON</strong> entro sette giorni, gli altri sviluppatori di. Presence sono autorizzati a <strong x-id="1">OVERWRITE</strong> per conformarsi alle modifiche.</li>
<li>La presenza <strong x-id="1">DEVONO</strong> essere testata prima di pubblicare per confermare che tutto funzioni come previsto.</li>
<li>La tua presenza <strong x-id="1">DEVE</strong> ha immagini e descrizioni SFW indipendentemente dal fatto che sia NSFW o no. Se la tua Presence riguarda un sito NSFW, aggiungi il tag <code>nsfw</code> ai tuoi metadati.</li>
<li>La tua presenza <strong x-id="1">NON</strong> manipolare lo spazio di archiviazione locale sul browser.</li>
<li>La tua Presence puo utilizzare i cookie per memorizzare i dati, devi anteporre tutti a <code>pmd_</code>.</li>
<li>Il nome di Presence <strong x-id"1">DEVE</strong> essere il nome della directory di Presence. Ad esempio, une Presence denominata <code>Google Docs</code> deve avere una directory di <code>/Google Docs/</code>. ( Dovresti includere tutti gli spazi, i periodi, le virgole e qualsiasi altro carattere speciale. )</li>
</ul>

<h2 spaces-before="0">Modifica</h2>

<blockquote spaces-before="0">
  <p spaces-before="0">DEVI modificare la versione nei metadi <strong x-id="1">metadata</strong> per essere un valore piu alto rispetto alla versione precedente quando effetui modifiche alla presenza <strong x-id'="1">presence.ts</strong>**presence.js</strong o **metadata.json**. </p>
{.is-warning}</blockquote>

In alcune situazioni, le Presence possono comportarsi in modo inaspettato o potrebbero utilizzare alcuni piccoli cambiamenti per miglioarne la funzionalità. Ecco un elenco compilato che **DEVI** seguire per modificare le Presenze.

- **NON** sei autorizzato a riscrivere una Presenza o a cambiare il suo autore. Se l'autore della Presenza è stato bannato dal server ufficiale o non ha apportato le modifiche richieste in sette giorni, puoi contattare un `Verificatore di Presenze` per vedere se è possibile riscrivere la Presenza di tua scelta.
- Chiunque può fornire hotfix per correggere i bug; Tuttavia, prova a **NON** apportare modifiche al codice che **NON** hanno bisogno di essere corrette. Le modifiche valide sono, ma **NON** limitate a, _percorsi mancanti_, _errori_, _immagini mancanti_, ecc.
- Se fai delle modifiche ad una Presenza e cambi almeno un **QUARTO** del codice base di riferimento della Presenza, ti è permesso aggiungere te stesso come collaboratore. Contatta un `Verificatore di Presenze` per ulteriori informazioni su questo argomento.
- Make sure the modifications are useful. These may include fixes ( code and typos ), additions ( descriptions and tags ), etc. Do **NOT** change images if they are not outdated and have a decent resolution.
- Confirm that your changes work before publishing. Do **NOT** create pull requests without knowing the outcome of your changes.
- When you make changes to a presence, modify the `presence.ts` file and compile it, do not make changes to the `presence.js` file directly.

# Verifica

> ⚠️ **Warning**: Presence developers are now required to use `TypeScript`, the option for `JavaScript` presences has been completely removed. 
> 
> {.is-warning}

> **Confirm** that your presence's [metadata](https://docs.premid.app/en/dev/presence/metadata) is valid and has all of the necessary fields before making a pull request. If your metadata contains an optional variable that is set to the default value, remove it ( Presence Verifiers will request you to remove them ). 
> 
> {.is-warning}

> If you need to contact someone, please use our official Discord server. All `Presence Verifiers` will have a unique role in their profile.

For your Presence to reach the stores, it **MUST** go through a process on GitHub to confirm that it works as expected. These are a few things to look out for when making your pull request.

1. It takes two verifiers to confirm that your Presence is up to standards. If you happen to get change requests, make the proper effort to fix it, or it will **NOT** be added.
2. If we request changes and your pull request exceeds **7 days of inactivity** without making the necessary ones, we'll be forced to close it.
3. You are allowed to take screenshots of changes made with the help of another user, and you are allowed to stitch screenshots for viewing pleasure. ( e.g., its author in case you can't access it for any reason ).
4. If it is an update or patch, the screenshot **MUST** show the new additions working, **NOT** any old features from previous pull requests.
5. The provided screenshots should be real, **NOT** edited.
6. Qualsiasi codice contribuito che viene unito a questo repository sarà concesso in licenza sotto **Mozilla Public License 2.0**.
7. Presences for free domains or hosts ( e.g., .TK, [all free Freenom domains], .RF.GD, etc ) are **NOT** allowed at all, exceptions can be made if a proof is presented showing that they paid for the domain.
8. The `smallImageKey` and `smallImageText` fields are intended to provide additional/secondary context (such as "playing"/"paused" for video sites, "browsing" for regular sites, and other cases) not to promote Discord profiles or anything unrelated to PreMiD.
9. The requirements for logos are 1:1 (Square) in 512px, thumbnails, however, should either be [wide promotional cards](https://i.imgur.com/3QfIc5v.jpg) or simply [screenshots](https://i.imgur.com/OAcBmwW.png) if the first is **NOT** available.
10. Presences should at least have one tag. Tags must **NOT** include any spaces, slashes, single/double quotation marks, Unicode characters, and should always be lowercase.
11. The `url` field **MUST NOT** include `http://` or `https://`, neither the parameters ( e.g. a Presence for `https://www.google.com/search?gws_rd=ssl` will only have `www.google.com` in the `url` field ).
12. Descriptions and tags should always be in an array, even when it's only one element. The `url` field, however, should only be a string if it's one domain.
13. Tags should be used as alternate names whenever possible, and shortened versions must be included as well ( e.g., if an Amazon Presence had included AWS support, it would have its tags like "amazon-web-services" and "aws" ).
14. Unstable sites that constantly change APIs/domains, randomize HTML elements, or just still being in heavy development are not allowed and will be removed from the store.
15. The logo and thumbnail on your Presence **MUST** either be `i.imgur.com`, from a CDN that **YOU** own, or from a CDN that gives you permission to **CHANGE** image files.
16. Verifiers will check if the Presence contains an `__awaiter` function at the beginning of the code ( which comes from an earlier version of ECMAScript ), and in addition to that, make sure the `UpdateData` event used is similar to this:

```ts
presence.on("UpdateData", async () => {
  /*...*/
  // Always use await when using async in the event
  data.smallImageText = (await strings).playing;
  /*...*/
});
```

It should **NOT** be this:

```ts
presence.on("UpdateData", () => __awaiter(this, void 0, void 0, function* () {
  /*...*/
  // Never use yield
  data.smallImageText = (yield strings).playing;
  /*...*/
});
```

17.  When **Deepscan** throws a lot of errors ( and it will ), it is mostly an issue with your branch being outdated, always update your GitHub fork before making a Pull Request.
18. If your Presence is new, it **MUST** start with version `1.0.0`, any other version will **NOT** be permitted.
19. Low-quality Presences ( or ones with one context ) are **NOT** allowed ( e.g., only showing the logo and some text but never changing again ).
20. **NEVER** use custom functions when [native variants are available](https://docs.premid.app/dev/presence#files-explained); this makes sure fixes on the extension level also apply to your Presences, you're free to use whatever you need if you do not find them listed in the docs.
21. Declare the Presence const **BEFORE** everything to avoid such rare issues that may occur; this is not a requirement by design so it could be removed in the future.
22. Presences that target internal browser pages ( like Chrome Web Store, `chrome://`, `about:` pages, etc ) are **NOT** allowed as they require an _experimental flag_ to be enabled on the user's end and could potentially cause damage to their browsers.
23. It is **FORBIDDEN** to code Presences for a site without adding support to its main language (e.g., a YouTube Presence coded with support for Portuguese and Japanese, but not English itself).
24. Always make sure the version number follows [semantic versioning standards](https://semver.org), which translates to the following scheme : `<NEW-FEATURE>.<HUGE-BUGFIX>.<SMALL-BUGFIX-OR-METADATA-CHANGES>`. anything else like `1.0.0.1`, `1.0`, `1`, `1.0.0-BETA` or changing `1.0.0` to `2.0.0` on a bug fix/small change is **NOT** permitted.
25. Declare the presence variable before anything, ( can cause some users issues that can be prevented ).
26. Do **NOT** edit the `tsconfig.json` file, use exactly what is specified on the [documentation](https://docs.premid.app/en/dev/presence/tsconfig#presence-configuration).
27. Presences with support only for a single subdomain will **NOT** be permitted, as they may seem broken for other pages ( like the homepage ), exceptions can be made for policy and contact pages ( content that isn't used much ) or sites where the other content is unrelated ( e.g wikia pages ).
28. All presences **MUST**  include an English description, including websites that aren't natively English.
29. Presences for the Tor network's websites (.ONION TLDs) are **NOT** allowed at all.
30. Always make sure to start your Presence in the most appropriate folder, if its name starts with any Latin letter then it must be under its alphabetical match ( e.g. `D/dアニメストア` or `G/Google` ). Any other Unicode/non-Latin characters **MUST** be under the "#" folder ( e.g. `#/巴哈姆特` ) and numbers under the "0-9" folder ( e.g. `0-9/4anime` ).

After meeting all of the guidelines and having your Presence reviewed at least twice, your Presence will be merged with the store.

# Structure
All presence are coded in [TypeScript](https://www.typescriptlang.org/). [TypeScript](https://www.typescriptlang.org/) has some extra spicy type definitions over JavaScript, so fixing and identifying bugs is way easier.

## Installazione
1. Installa [Git](https://git-scm.com/).
2. Installa [Nodo](https://nodejs.org/en/) (viene fornito con [npm](https://www.npmjs.com/)).
3. Install [TypeScript](https://www.typescriptlang.org/index.html#download-links) (open a terminal and `npm install -g typescript`).

## Clonando il progetto
1. Open a terminal and type `git clone https://github.com/PreMiD/Presences`.
2. Scegli una cartella a tua scelta.
3. Aprilo con l'editor di codice.

## Creazione di cartelle e file

1. Create a folder with the **name** (not an URL) of the service you want to support.
2. Create a `presence.ts` and a `tsconfig.json` file inside.
3. Create a folder named `dist` inside.
4. Create a `metadata.json` file inside the `dist` folder.

## Riempimento nel file tsconfig.json
Per favore, inserisci il seguente codice all'interno del file `tsconfig.json`.
```javascript
{
  "extends": "../../../tsconfig.json",
  "compilerOptions": {
    "outDir": "./dist/"
  }
}
```
Per ulteriori informazioni sulla configurazione di TypeScript, clicca [qui](/dev/presence/tsconfig).

## Compilazione nel file metadata.json
Abbiamo creato un `metadata.json` creatore di file per i pigroni [qui](https://eggsy.codes/projects/premid/mdcreator). It's still suggested to read this through so you know how it works.

```javascript
{
  "author": {
    "name": "USER",
    "id": "ID"
  },
  "contributors": [{
    "name": "USER",
    "id": "ID"
  }],
  "service": "SERVICE",
  "description": {
    "en": "DESCRIPTION"
  },
  "url": "URL",
  "version": "VERSION",
  "logo": "URL",
  "thumbnail": "URL",
  "color": "#HEX000",
  "tags": ["TAG1", "TAG2"],
  "category": "CATEGORY",
  "regExp": "REGEXP",
  "iFrameRegExp": "REGEXP",
  "iframe": false,
  "settings": [
        { 
            "id": "ID",
            "title": "DISPLAY TITLE",
            "icon": "FONTAWESOME FREE ICON",
            "value": true
        },
        {
            "id": "ID",
            "if": {
                "ID": true
            },
            "title": "DISPLAY TITLE",
            "icon": "FONTAWESOME FREE ICON",
            "value": "\"%song%\" by %artist%",
            "placeholder": "use %song% or %artist%"
        },
        {
            "id": "ID",
            "title": "DISPLAY TITLE",
            "icon": "FONTAWESOME FREE ICON",
            "value": 0,
            "values": ["1", "2", "etc."]
        }
    ]
}
```

Copia il codice qui sopra e inseriscilo nel file `metadata.json`. You now need to edit values of the properties. Please note that the following properties are optional to have in your `metadata.json` file, if you do not plan on using them you need to remove them.
- `collaboratori`
- `regExp`
- `iframe`
- `iFrameRegExp`
- `impostazioni`

**Clarifying some value presets:**
<table>
  <thead>
    <tr>
      <th style="text-align:left">Variabile</th>
      <th style="text-align:left">Descrizione</th>
      <th style="text-align:left">Tipo</th>
      <th style="text-align:left">Opzionale</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>autore</b>
      </td>
      <td style="text-align:left">Dovrebbe contenere un oggetto con <code>nome</code> e <code>id</code> dello sviluppatore presenza. Il nome utente di Discord è senza identificatore(#0000). L'id utente <code></code> può essere copiato da Discord abilitando la modalità
        dello sviluppatore e facendo click destro sul tuo profilo.</td>
      <td style="text-align:left"><code>Oggetto</code>
      </td>
      <td style="text-align:left"><code>No</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>collaboratori</b>
      </td>
      <td style="text-align:left">Dovrebbe contenere un oggetto con <code>nome</code> e <code>id</code> dello sviluppatore presenza. Il nome utente di Discord è senza identificatore(#0000). L'id utente <code></code> può essere copiato da Discord abilitando la modalità
        dello sviluppatore e facendo click destro sul tuo profilo.</td>
      <td style="text-align:left"><code>Schieramento&lt;Object&gt;</code>
      </td>
      <td style="text-align:left"><code>sì</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>servizio</b>
      </td>
      <td style="text-align:left">Il titolo del servizio che supporta questa presenza. <br>(Must be the same name as the folder where everything is in)</td>
      <td style="text-align:left"><code>Stringa</code>
      </td>
      <td style="text-align:left"><code>No</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>descrizione</b>
      </td>
      <td style="text-align:left">Breve descrizione della presenza, puoi usare la descrizione del servizio
        se non hai idee. La tua descrizione deve avere valori di coppia chiave che indicano la lingua, e la descrizione in quella specifica lingua. Crea descrizioni con le lingue <i>che conosci</i>, i nostri traduttori modificheranno il file di metadati.</td>
      <td style="text-align:left"><code>Oggetto</code>
      </td>
      <td style="text-align:left"><code>No</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Url</b>
      </td>
      <td style="text-align:left">URL of the service.<br><b>Example:</b><code>vk.com</code><br>
        <b>This URL must match the URL of the website as it will detect whether or not this is the website to inject the script to.</b><br> Do <b>NOT</b> add <code>https://</code> or <code>http://</code> inside of the URL nor a slash at the end:
<code>https://premid.app/</code> -> <code>premid.app</code><br>
<b>Note</b>: Some URLs may have <code>www.</code> or something else in front of their domain. Do <b>NOT</b> forget to add it!<br>
You can add multiple URLs by doing the following:<br>
<code>["URL1", "URL2", "ETC."]</code><br>
You could also use regExp also known as Regex for this task, explaned further below.
      </td>
      <td style="text-align:left"><code>Stringa, Schieramento&lt;String&gt;</code>
      </td>
      <td style="text-align:left"><code>No</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>regExp</b>
      </td>
      <td style="text-align:left">A regular expression string used to match urls.<br>
      regExp or also known as Regex, can be used if a website has multiple subdomains.<br>
You could use the following regExp for that:<br>
<code>([a-z0-9]+)[.]domain[.]TLD"</code><br>
TLD standing for Top Level Domain for axample: .com .net<br> 
<code>([a-z0-9]+)</code> means anything from a to z and from 0 to 9.<br>
        You can test your regExp at <a href="https://regex101.com/">Regex101</a></td>
      <td style="text-align:left"><code>Stringa</code>
      </td>
      <td style="text-align:left"><code>sì</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>versione</b>
      </td>
      <td style="text-align:left">Versione della sua presenza.</td>
      <td style="text-align:left"><code>Stringa</code>
      </td>
      <td style="text-align:left"><code>No</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>logo</b>
      </td>
      <td style="text-align:left">Link al servizio&apos;s logotype.</td>
      <td style="text-align:left"><code>Stringa</code>
      </td>
      <td style="text-align:left"><code>No</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>thumbnail</b>
      </td>
      <td style="text-align:left">Link alla tua miniatura di presenza.</td>
      <td style="text-align:left"><code>Stringa</code>
      </td>
      <td style="text-align:left"><code>No</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>colore</b>
      </td>
      <td style="text-align:left">Valore <code>#HEX</code>. Consigliamo di utilizzare un colore primario del servizio
        che la vostra presenza supporta.</td>
      <td style="text-align:left"><code>Stringa</code>
      </td>
      <td style="text-align:left"><code>No</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>tag</b>
      </td>
      <td style="text-align:left">Array con i tag, aiuteranno gli utenti a cercare la tua presenza sul sito.</td>
      <td
      style="text-align:left"><code>Stringa, Schieramento&lt;String&gt;</code>
        </td>
      <td style="text-align:left"><code>No</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Categoria</b>
      </td>
      <td style="text-align:left">Una stringa utilizzata per rappresentare la categoria sotto la quale la presenza cade See the valid catergories <a href="https://docs.premid.app/dev/presence/metadata#presence-categories">here</a>.</td>
      <td style="text-align:left"><code>Stringa</code>
      </td>
      <td style="text-align:left"><code>No</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>iframe</b>
      </td>
      <td style="text-align:left">Definisce se <code>iFrame</code> sono usati</td>
      <td style="text-align:left"><code>Boolean</code>
      </td>
      <td style="text-align:left"><code>sì</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>iFrameRegExp</b>
      </td>
      <td style="text-align:left">Un selettore di espressione regolare che seleziona gli iframe da inserire. See regExp for more info.</td>
      <td style="text-align:left"><code>Stringa</code>
      </td>
      <td style="text-align:left"><code>sì</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>impostazioni</b>
      </td>
      <td style="text-align:left">An array of settings the user can change.<br>
      Read more about presence settings <a href="https://docs.premid.app/dev/presence/metadata#presence-settings">here</a>.</td>
      <td style="text-align:left"><code>Schieramento&lt;Object&gt;</code>
      </td>
      <td style="text-align:left"><code>sì</code>
      </td>
    </tr>
  </tbody>
</table>

Abbiamo creato un `metadata.json` creatore di file per i pigroni [qui](https://eggsy.codes/projects/premid/mdcreator).

## Guida introduttiva

```javascript
var presence = new Presence({
    clientId: "000000000000000000" //The client ID of the Application created at https://discordapp.com/developers/applications
}),

strings = presence.getStrings({
    play: "presence.playback.playing",
    pause: "presence.playback.paused"
    //You can use this to get translated strings
});

/*

function myOutsideHeavyLiftingFunction(){
    //Grab and process all your data here

    // element grabs //
    // api calls //
    // variable sets //
}

setInterval(10000, myOutsideHeavyLiftingFunction); 
//Run the function seperate from the UpdateData event every 10 seconds to get and set the variables which UpdateData picks up

*/


presence.on("UpdateData", async () => {
    /*UpdateData is always firing, and therefore should be used as your refresh cycle, or `tick`. This is called several times a second where possible.

    It is recommended to set up another function outside of this event function which will change variable values and do the heavy lifting if you call data from an API.*/

    var presenceData: presenceData = {
        largeImageKey: "key", /*The key (file name) of the Large Image on the presence. These are uploaded and named in the Rich Presence section of your application, called Art Assets*/
        smallImageKey: "key", /*The key (file name) of the Large Image on the presence. These are uploaded and named in the Rich Presence section of your application, called Art Assets*/
        smallImageText: "Some hover text", //The text which is displayed when hovering over the small image
        details: "Browsing Page Name", //The upper section of the presence text
        state: "Reading section A", //The lower section of the presence text
        startTimestamp: 1577232000, //The unix epoch timestamp for when to start counting from
        endTimestamp: 1577151472000 //If you want to show Time Left instead of Elapsed, this is the unix epoch timestamp at which the timer ends
    }; /*Optionally you can set a largeImageKey here and change the rest as variable subproperties, for example presenceSata.type = "blahblah"; type examples: details, state, etc.*/

    if (presenceData.details == null) {
        //This will fire if you do not set presence details
        presence.setTrayTitle(); //Clears the tray title for mac users
        presence.setActivity(); /*Update the presence with no data, therefore clearing it and making the large image the Discord Application icon, and the text the Discord Application name*/
    } else {
        //This will fire if you set presence details
        presence.setActivity(presenceData); //Update the presence with all the values from the presenceData object
    }
});
```
You can copy this into your `presence.ts` file and edit the values. Setting all the values is done inside of the updataData event.

For examples we suggest to look at the code of presences like: 1337x or 9GAG.

For more information about the Presence class click [here](/dev/presence/class).

## Impossibile ottenere alcuni dati?!

A lot of websites are using [iframes](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) ([Inlineframes](https://en.wikipedia.org/wiki/HTML_element#Frames)). These html tags can contain multiple sources such as videos. But they're not relevant every time. Some are hidden or just not actively used. Check if you can extract, the information you need, without them before you do unnecessary work.

1. Check for them in your browsers console (be sure that you are on the **Elements** tab).
2. Search (<kbd>CTRL</kbd>+<kbd>F</kbd> (Windows) or <kbd>CMD</kbd>+<kbd>F</kbd> (MacOS)).
3. Execute `document.querySelectorAll("iframe")`.

If you find that your data is in a iFrame you need to do the following:
1. Create a `iframe.ts` file.
2. Set iFrame to `true` in your metadata file.
3. Filling in your iFrame file.
```javascript
var iframe = new iFrame();
iframe.on("UpdateData", async () => {
  /*
  Get all the data you need out of the iFrame save them in variables
  and then sent them using iframe.send
  */
  iframe.send({ //sending data
    video: video,
    time: video.duration
  }); 
});
```
4. Making your presence file receive data from the iFrame file.
```javascript
presence.on("iFrameData", data => {
  iFrameVideo = data.video;
  currentTime = data.time;
});
```
**Note:** This needs to be placed outside of the updateData event.
## Compilazione
Open a console in your folder and type `tsc -w` to compile the `presence.ts` into the `/dist` folder.

# Loading the presence
1. Open the popup and hold the <kbd>Shift</kbd> button on your keyboard.
2. **Load Presence** will appear in the Presences section.
3. Click on it while you are still holding the <kbd>Shift</kbd> button.
4. Select the /dist folder of your presence.

# Some helpful things
## Hot-reloading
The website you are developing on is automatically reloading every time you save a file in your folder.

## Debugging
- You can put `console.log("Test");` between your code and see if your browser console gives you that output. If yes then go on and try again after the next function. If not then there is an error above.
- If that doesn't help you either then ask a presence developer on our [Discord server](https://discord.gg/WvfVZ8T) for help.

# Files explained
- [Classe Presenza](/dev/presence/class)
- [Classe iFrame](/dev/presence/iframe)
- [Metadata File](/dev/presence/metadata)
- [Configurazione TypeScript](/dev/presence/tsconfig)
{.links-list}
