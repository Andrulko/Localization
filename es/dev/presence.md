---
title: Desarrollo de Presencias
description:
published: true
date: 2020-05-21T15:59:59.864Z
tags:
---

> Todas las presencias ahora se almacenan aquí: https://github.com/PreMiD/Presences 
> 
> {.is-info}

La versión `2.x` introduce la [tienda de presencias](https://premid.app/store). Los usuarios ahora tienen la capacidad de añadir y eliminar manualmente sus presencias favoritas a través de la interfaz de usuario del sitio web [](https://premid.app/).

# Directrices
> Si **NO** sigue las normas, un `Verificador de Presencias` solicitará los cambios adecuados, o tendrá que cerrarlo bajo ciertas circunstancias. 
> 
> {.is-warning}

> Cuando solicites un Pull Request para añadir o modificar presencias existentes, **DEBES** incluir una captura de pantalla. Sin embargo, las modificaciones en los archivos `metadata.json` o `tsconfig.json` **NOT** requieren una captura de pantalla. _Tu captura de pantalla **DEBE** ser subida directamente a GitHub mediante Pull Request, **NO** utilice sitios para compartir imágenes de terceros_ 
> 
> {.is-warning}

Cuando publiques presencias en GitHub, debes seguir un conjunto de reglas. Para algunos, estas reglas estrictas pueden parecer duras. Sin embargo, la implementación de estas reglas nos impedirá a nosotros y a los usuarios encontrarnos con cualquier problema.

## Creación
> El código que escribas DEBE estar *bien escrito* y DEBE ser *legible*. `DeepScan` en GitHub reportará problemas de calidad de código al `Equipo de Verificación de Presencias`. Recomendamos que su fork esté actualizado al solicitar un Pull Request, esto limitará falsos positivos. 
> 
> {.is-warning}

- El pull request **DEBE** estar completo, necesita tener una estructura de archivos adecuada, los borradores **NO** están permitidos. Incluyendo la carpeta `dist`, el archivo `presence.ts`, el archivo `tsconfig.json`, el archivo `presence.js` y el archivo `metadata.json`, como es representado en el siguiente esquema de ejemplo:
```bash
websites
└── {type}
    └── presence
        ├── dist
        │   ├── metadata.json
        │   └── presence.js
        ├── presence.ts
        └── tsconfig.json
```
o si utilizas `iframe`:
```bash
websites
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
- {type} standing for: A to Z, "#" for non alphabetic starting presences and "0-9" for presences starting with numbers.
<br>
Antes de empezar a trabajar en su presencia, tenga en cuenta la siguiente lista.
- La presencia **DEBE** estar relacionada con el sitio web que ha elegido.
- La presencia **NO DEBE** ser de ningún sitio web ilegal. Estos incluyen páginas estresantes, sustancias ilegales, pornografía infantil, etc.
- Los metadatos de una presencia **DEBEN** tener un formato correcto, incluyendo títulos válidos y descripciones.
- Los archivos que incluyas (Iconos/miniaturas) **DEBEN** estar relacionados con el sitio y debe ser correctos en términos de tamaño y calidad.
- La estructura de archivos **DEBE** ser limpia y controlada, **NO** debe haber archivos aleatorios que no proporcionen nada a la función de la presencia.
- La presencia **NO DEBE** tener intenciones maliciosas. Estas incluyen robo/filtración de información privada, afectar negativamente al comportamiento del sitio web, etc.
- Si diseña una presencia para un sitio que cambia en el futuro y como resultado, potencialmente rompe su presencia, usted **ES** responsable de actualizarlo para que funcione como se esperaba. Si **NO** se arreglase en un plazo de 7 días, otros desarrolladores de presencias pueden **CORREGIR** su presencia para incluir los cambios necesarios.
- La presencia **DEBE** ser probada antes de publicarse para confirmar que todo funciona como se esperaba.
- Su presencia **DEBE** tener imágenes y descripciones SFW independientemente de si es NSFW o no. Si su presencia es acerca de un sitio web con contenido NSFW, por favor agregue la etiqueta `nsfw` en sus metadatos.
- Su presencia **NO PUEDE** manipular el almacenamiento local del navegador.
- Tu presencia puede usar cookies para almacenar datos, tienes que prefijarlas todas con `pmd_`.
- El nombre de tu presencia **DEBE** ser el nombre del directorio que usa la presencia. Por ejemplo, una presencia llamada `Google Docs` debe tener el directorio de `/Google Docs/`. ( Debes incluir todos los espacios, períodos, comas y cualquier otro carácter especial. )

## Modificación
> DEBES actualizar la versión en los **metadatos** a un valor mayor al de la versión anterior cuando hagas cambios en cualquiera de los archivos **presence.ts**/**presence.js** o **metadata.json**. 
> 
> {.is-warning}

En algunas situaciones, las presencias pueden comportarse inesperadamente o podrían realizarse cambios menores para mejorar su funcionalidad. Aquí hay una lista de situaciones que usted **DEBE** tener en cuenta al modificar una presencia.

- Usted **NO** tiene permitido reescribir una presencia o cambiar su autor. Si la el autor de la Presencia fue baneado del servidor oficial o no hizo los requeridos cambios en un periodo de siete (7) días, puedes contactar con un `Presence Verifier` para ver si puedes reescribir la Presencia.
- Cualquiera puede proporcionar hotfixes para corregir errores; sin embargo, prueba **NO** para hacer cambios en el código que **NO** necesitan ser corregidos. Valid modifications are, but **NOT** limited to, _missing paths_, _typos_, _missing images_, etc.
- Si haces modificaciones a una presencia y cambias al menos un **UN CUARTO** del código base de la misma, puedes añadirte como colaborador. Póngase en contacto con un `Verificador de Presencias` para más información sobre este tema.
- Asegúrese de que las modificaciones son útiles. Estos pueden incluir correcciones (De código o tipográficas), añadidos (Descripciones y etiquetas), etc. No cambien las imágenes a menos de que estén desactualizadas y tengan una mala resolución.
- Confirme que los cambios funcionan antes de publicar. Do **NOT** create pull requests without knowing the outcome of your changes.
- When you make changes to a presence, modify the `presence.ts` file and compile it, do not make changes to the `presence.js` file directly.

# Verificación

> ⚠️ **Warning**: Presence developers are now required to use `TypeScript`, the option for `JavaScript` presences has been completely removed. 
> 
> {.is-warning}

> **Confirm** that your presence's [metadata](https://docs.premid.app/en/dev/presence/metadata) is valid and has all of the necessary fields before making a pull request. If your metadata contains an optional variable that is set to the default value, remove it ( Presence Verifiers will request you to remove them ). 
> 
> {.is-warning}

> Si necesitas contactar con alguien, por favor usa nuestro servidor oficial de Discord. All `Presence Verifiers` will have a unique role in their profile.

For your Presence to reach the stores, it **MUST** go through a process on GitHub to confirm that it works as expected. Estas son algunas cosas a tener en cuenta al enviar un Pull Request.

1. It takes two verifiers to confirm that your Presence is up to standards. If you happen to get change requests, make the proper effort to fix it, or it will **NOT** be added.
2. Si se solicitan cambios y su Pull Request excede **7 días de inactividad** sin llevarlos a cabo, nos veremos obligados a cerrar dicho Pull Request.
3. You are allowed to take screenshots of changes made with the help of another user, and you are allowed to stitch screenshots for viewing pleasure. ( e.g., its author in case you can't access it for any reason ).
4. If it is an update or patch, the screenshot **MUST** show the new additions working, **NOT** any old features from previous pull requests.
5. The provided screenshots should be real, **NOT** edited.
6. Cualquier código aportado que se fusiona en este repositorio será licenciado bajo la **Mozilla Public License 2.0**.
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

## Instalación
1. Install [Git](https://git-scm.com/).
2. Instala [Nodo](https://nodejs.org/en/) (viene con [npm](https://www.npmjs.com/)).
3. Install [TypeScript](https://www.typescriptlang.org/index.html#download-links) (open a terminal and `npm install -g typescript`).

## Clonando el proyecto
1. Open a terminal and type `git clone https://github.com/PreMiD/Presences`.
2. Elija una carpeta de su elección.
3. Ábrelo en tu editor de código.

## Creando carpetas y archivos

1. Create a folder with the **name** (not an URL) of the service you want to support.
2. Create a `presence.ts` and a `tsconfig.json` file inside.
3. Cree una carpeta llamada `dist` en su interior.
4. Cree un archivo `metadata.json` dentro de la carpeta `dist`.

## Rellenar el archivo tsconfig.json
Por favor, introduzca el siguiente código dentro del archivo `tsconfig.json`.
```javascript
{
  "extends": "../../../tsconfig.json",
  "compilerOptions": {
    "outDir": "./dist/"
  }
}
```
To learn more about TypeScript configuration click [here](/dev/presence/tsconfig).

## Rellenar el archivo metadata.json
We've made a `metadata.json` file creator for the lazy peeps [here](https://eggsy.codes/projects/premid/mdcreator). It's still suggested to read this through so you know how it works.

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

Please copy the code above and put it in your `metadata.json` file. You now need to edit values of the properties. Please note that the following properties are optional to have in your `metadata.json` file, if you do not plan on using them you need to remove them.
- `contribuidores`
- `regExp`
- `iframe`
- `iFrameRegExp`
- `ajustes`

**Clarifying some value presets:**
<table>
  <thead>
    <tr>
      <th style="text-align:left">Variable</th>
      <th style="text-align:left">Descripción</th>
      <th style="text-align:left">Tipo</th>
      <th style="text-align:left">Opcional</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>autor</b>
      </td>
      <td style="text-align:left">Debe contener un objeto con <code>nombre</code> y <code>id</code> del desarrollador de presencia. Nombre es tu nombre de usuario de Discord sin el identificador(#0000). El usuario <code>id</code> puede copiarse de Discord habilitando el modo
        del desarrollador y haciendo clic derecho en tu perfil.</td>
      <td style="text-align:left"><code>Objeto</code>
      </td>
      <td style="text-align:left"><code>Nu</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>contribuidores</b>
      </td>
      <td style="text-align:left">Debe contener un objeto con <code>nombre</code> y <code>id</code> del desarrollador de presencia. Nombre es tu nombre de usuario de Discord sin el identificador(#0000). El usuario <code>id</code> puede copiarse de Discord habilitando el modo
        del desarrollador y haciendo clic derecho en tu perfil.</td>
      <td style="text-align:left"><code>Arreglo&lt;Object&gt;</code>
      </td>
      <td style="text-align:left"><code>Sí</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>servicio</b>
      </td>
      <td style="text-align:left">El título del servicio que soporta esta presencia. <br>(Must be the same name as the folder where everything is in)</td>
      <td style="text-align:left"><code>String</code>
      </td>
      <td style="text-align:left"><code>Nu</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>descripción</b>
      </td>
      <td style="text-align:left">Una pequeña descripción de la presencia, puedes usar la descripción del servicio
        si estás fuera de las ideas. Su descripción debe tener valores de par clave que indiquen el idioma, y la descripción en ese idioma específico. Haz descripciones con los idiomas <i>que conoces</i>, nuestros traductores harán cambios en tu archivo de metadatas.</td>
      <td style="text-align:left"><code>Objeto</code>
      </td>
      <td style="text-align:left"><code>Nu</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>url</b>
      </td>
      <td style="text-align:left">URL of the service.<br><b>Example:</b><code>vk.com</code><br>
        <b>This URL must match the URL of the website as it will detect whether or not this is the website to inject the script to.</b><br> Do <b>NOT</b> add <code>https://</code> or <code>http://</code> inside of the URL nor a slash at the end:
<code>https://premid.app/</code> -> <code>premid.app</code><br>
<b>Note</b>: Some URLs may have <code>www.</code> or something else in front of their domain. Do <b>NOT</b> forget to add it!<br>
You can add multiple URLs by doing the following:<br>
<code>["URL1", "URL2", "ETC."]</code><br>
You could also use regExp also known as Regex for this task, explaned further below.
      </td>
      <td style="text-align:left"><code>Cadena, array&lt;String&gt;</code>
      </td>
      <td style="text-align:left"><code>Nu</code>
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
        You can get a quick starter by watching this <a href="https://youtu.be/sXQxhojSdZM">video</a><br>
        You can test your regExp at <a href="https://regex101.com/">Regex101</a>
      </td>
      <td style="text-align:left"><code>String</code>
      </td>
      <td style="text-align:left"><code>Sí</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>versión</b>
      </td>
      <td style="text-align:left">Versión de su presencia.</td>
      <td style="text-align:left"><code>String</code>
      </td>
      <td style="text-align:left"><code>Nu</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>logotipo</b>
      </td>
      <td style="text-align:left">Enlace al tipo de logotipo de servicio&apos;s.</td>
      <td style="text-align:left"><code>String</code>
      </td>
      <td style="text-align:left"><code>Nu</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>thumbnail</b>
      </td>
      <td style="text-align:left">Enlace a su presencia.</td>
      <td style="text-align:left"><code>String</code>
      </td>
      <td style="text-align:left"><code>Nu</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>color</b>
      </td>
      <td style="text-align:left"><code>valor #HEX</code>. Recomendamos usar un color primario del servicio
        que tu presencia soporta.</td>
      <td style="text-align:left"><code>String</code>
      </td>
      <td style="text-align:left"><code>Nu</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>etiquetas</b>
      </td>
      <td style="text-align:left">Array con etiquetas, ayudarán a los usuarios a buscar su presencia en el sitio web.</td>
      <td
      style="text-align:left"><code>Cadena, array&lt;String&gt;</code>
        </td>
      <td style="text-align:left"><code>Nu</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>categoría</b>
      </td>
      <td style="text-align:left">Una cadena utilizada para representar la categoría bajo la que cae la presencia. See the valid catergories <a href="https://docs.premid.app/dev/presence/metadata#presence-categories">here</a>.</td>
      <td style="text-align:left"><code>String</code>
      </td>
      <td style="text-align:left"><code>Nu</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>iframe</b>
      </td>
      <td style="text-align:left">Define si se utilizan <code>iFrames</code></td>
      <td style="text-align:left"><code>Boolean</code>
      </td>
      <td style="text-align:left"><code>Sí</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>iFrameRegExp</b>
      </td>
      <td style="text-align:left">Un selector de expresiones regulares que selecciona iframes a inyectar. See regExp for more info.</td>
      <td style="text-align:left"><code>String</code>
      </td>
      <td style="text-align:left"><code>Sí</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>ajustes</b>
      </td>
      <td style="text-align:left">An array of settings the user can change.<br>
      Read more about presence settings <a href="https://docs.premid.app/dev/presence/metadata#presence-settings">here</a>.</td>
      <td style="text-align:left"><code>Arreglo&lt;Object&gt;</code>
      </td>
      <td style="text-align:left"><code>Sí</code>
      </td>
    </tr>
  </tbody>
</table>

We've made a `metadata.json` file creator for the lazy peeps [here](https://eggsy.codes/projects/premid/mdcreator).

## Comenzando

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

## ¡No puedes obtener ciertos datos?!

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
## Compilando
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
- [Clase de presencia](/dev/presence/class)
- [Clase iFrame](/dev/presence/iframe)
- [Metadata File](/dev/presence/metadata)
- [Configuración de TypeScript](/dev/presence/tsconfig)
{.links-list}
