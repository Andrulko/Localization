---
title: Indicaciones
description: Reglas que todos los desarrolladores de Presencias deben seguir para que su Presencia sea añadida.
published: verdadero
date: 2020-07-18T20:27:50.274Z
tags:
editor: markdown
---

# Indicaciones

Cuando publiques presencias en GitHub, debes seguir un conjunto de reglas. Para algunos, estás reglas pueden parecer estrictas. Sin embargo, estas reglas nos evitarán encontrarnos a nosotros y a los usuarios con algún tipo de problema.

# Creación

Las reglas generales del desarrollo de una Presencia son las siguientes:

- Las Presencias **deben** estar relacionadas con el sitio web que has elegido.
- Las Presencias **no pueden** ser para sitios ilegales. (Por ejemplo: Stressors, marketing de drogas, pornografía infantil, etc.)
- La estructura de los archivos debe ser limpia y gestionada, no incluyas archivos que no estén especificados. (Por ejemplo: Vscode y capetas git, imágenes y archivos de texto, etc.)
- Necesitas tener una estructura de archivo adecuada, los borradores **no** están permitidos.
- Presencias para sitios web con (`.onion ` TLDs) o sitios web con dominios gratuitos/ hosts gratuitos (por ejemplo, `.TK ` [todos los dominios Freenom gratuitos], `.RF </ 0>, <code> GD `, etc.) ** no ** están permitidos, se pueden hacer excepciones si se presenta una prueba que demuestre que pagaron por el dominio.
- La presencia de páginas de navegador internas de destino (como Chrome Web Store, `chrome://`, páginas `about:`, etc.) **no** están permitidas ya que requieren que se habilite un indicador experimental en el extremo del usuario y podría causar daños a sus navegadores.
- Las presencias con soporte para un solo subdominio **no** se permitirán, ya que pueden parecer rotas para otras páginas (como la página de inicio), se pueden hacer excepciones para la política y las paginas de contacto (contenido que no se usa con frecuencia) o sitios donde el otro contenido no este relacionado. (por ejemplo, paginas de wikia)
- Las presencias de baja calidad (o las que tienen poco contexto) ** no ** están permitidas (por ejemplo, mostrar solo un logotipo y texto pero nunca volver a cambiarlo)
- Incluyendo la carpeta `dist`, los archivos `presence.ts`, `iframe.ts` y `metadata.json` son obligatorios para que el resultado sea lo que se representa en el siguiente esquema:

```bash
presence
├── dist
│   ├── metadata.json
│   └── presence.js
├── presence.ts
└── tsconfig.json
```

o si estas usando un archivo `iframe.ts`:

```bash
presence
├── dist
│   ├── metadata.json
│   ├── presence.js
│   └── iframe.js
├── presence.ts
├── iframe.ts
└── tsconfig.json
```

## [**metadata.json**](https://docs.premid.app/en/dev/presence/metadata)

> Para la conveniencia de nuestros desarrolladores de presencias, hemos proporcionado un esquema que puedes usar para validar la integridad de tu archivo `metadata`. Esto es completamente opcional y no es requerido durante el proceso de revisión. 
> 
> {.is-info}

> Es altamente recomendado que organices tu archivo `metadata` en el formato mostrado abajo, y debes tener nombres de servicio, descripciones, etiquetas y campos de ajustes gramaticalmente correctos. Cualquier cosa que no esté organizada según las especificaciones, **no** será permitida. 
> 
> {.is-warning}

> Presencias de sitios web que tienen contenido explícito **deben** tener la etiqueta `nsfw` y el logo y etiqueta **no** deben contener contenido explícito. 
> 
> {.is-warning}

Cada presencia tiene un archivo para describirla llamado `metadata.json`, el metadata tiene un estándar estricto y un ejemplo de este archivo se puede ver abajo:

```json
{
  "$schema": "https://schemas.premid.app/metadata/1.0",
  "author": {
    "name": "USUARIO",
    "id": "ID"
  },
  "contributors": [{
    "name": "USUARIO",
    "id": "ID"
  }],
  "service": "SERVICIO",
  "description": {
    "en": "DESCRIPCIÓN"
  },
  "url": "URL",
  "version": "VERSIÓN",
  "logo": "URL",
  "thumbnail": "URL",
  "color": "#HEX000",
  "tags": ["ETIQUETA1", "ETIQUETA2"],
  "category": "CATEGORÍA",
  "regExp": "EXPRESIÓN REGULAR",
  "iFrameRegExp": "EXPRESIÓN REGULAR",
  "iframe": false,
  "settings": [
        { 
            "id": "ID",
            "title": "TÍTULO PARA MOSTRAR",
            "icon": "ICONO DE FONTAWESOME GRATIS",
            "value": true
        },
        {
            "id": "ID",
            "if": {
                "ID": true
            },
            "title": "TÍTULO PARA MOSTRAR",
            "icon": "ICONO DE FONTAWESOME GRATIS",
            "value": "\"%song%\" por %artist%",
            "placeholder": "usa %song% o %artist%"
        },
        {
            "id": "ID",
            "title": "TÍTULO PARA MOSTRAR",
            "icon": "ICONO DE FONTAWESOME GRATIS",
            "value": 0,
            "values": ["1", "2", "etc."]
        }
    ]
}
    }
  ]
}
```

> Si un campo está estipulado como opcional en la [documentación](https://docs.premid.app/en/dev/presence/metadata) y tu presencia usa el valor por defecto para ella, no la incluyas en el archivo `metadata`. (por ejemplo, una presencia sin soporte para iframe no debe contener el campo `iframe`.) 
> 
> {.is-warning}

> Todas las imágenes en el archivo `metadata` deben estar guardadas en `i.imgur.com` o en un CDN el cual te de permiso para poder **editar** imágenes. Contenido alojado en el sitio web en sí ** no** está permitido, puesto que pueden cambiar su ubicación sin querer. 
> 
> {.is-warning}

Una lista de los campos y sus reglas están listadas abajo:

### **`$schema`**

- La _llave_ del esquema **debe** incluir un signo de dolar al inicio, esto indicará a su editor de texto que tu quieres validar tu archivo JSON contra un modelo. _Tal y como se ha dicho anteriormente, no necesitas incluir un esquema, pero en caso de que lo hagas, debes tomar esto en cuenta._

### **`autor`**

- El _valor_ de la ID **debe** ser el snowflake de tu ID de Discord. Puedes obtenerlo activando el [modo de desarrollador](https://support.discord.com/hc/en-us/articles/206346498-Where-can-I-find-my-User-Server-Message-ID-). _Por favor **no** confundas esto con la ID de la aplicación, la cual es solo para tu presence._

### **`contribuidores`**

- **No** te agregues ni a ti, ni a nadie más como contribuidores al menos que hayan ayudado con la presence.

### **`servicio`**

- El nombre del servicio **debe** ser el nombre de la ubicación de la presencia. Por ejemplo, si la presencia esta ubicada en `/websites/Y/YouTube/`, el nombre del servicio debe ser `YouTube`.

### **`altnames`**

- **Solo** use esto en el caso que el sitio web aparezca bajo distintos nombres (e.j. Pokémon ó 포켓몬스터) para buscar mas fácil la presencia sin usar caracteres especiales (e.j. Pokémon ó Pokemon). Versiones *acortadas* del servicio aparecerán como `etiquetas`.

### **`descripción`**

- **Todas** las presences **requieren** una descripción en Inglés sin importar el idioma preferido del sitio web.
- **No** intentes traducir la descripción por tu cuenta a menos que conozcas el idioma, traductores modificaran tu `metadata.json.` y cambiaran la descripción de ser necesario.

### **`url`**

- La url **debe** ser un "string" si el sitio web solo usa un dominio. Si el sitio web usa múltiples, usa un array y especifica cada una.
- **No** incluya protocolos en la url (por ej.`http` ó `https`, y no incluya parámetros "query" en la url (por ej.,`www.google.com/search?gws_rd=ssl` devería ser `www.google.com`)

### **`versión`**

- Siempre asegúrese de que el número de versión sigue [los estándares semánticos de versionado](https://semver.org), que se traducen al siguiente esquema: `<NEW-FEATURE>.<HUGE-BUGFIX>.<SMALL-BUGFIX-OR-METADATA-CHANGES>`. Cualquier cosa como `1.0.0.1`, `1.0`, `1`, `1.0.0-BETA` o cambiando `1.0.0` a `2.0.0` en una corrección de errores/cambio pequeño **no** está permitido.
- La versión **debe** empezar siempre con `1.0.0` a menos que se diga lo contrario, otras versiones **no** serán permitidas.

### **`logotipo`**

- El logo **debe** ser una imagen cuadrada con una relación de aspecto `1:1`.
- La imagen **requiere** una resolución mínima de `512x512` píxeles. Puedes aumentar el tamaño de la imagen usando una herramienta como [waifu2x](http://waifu2x.udp.jp/).

### **`thumbnail`**

- La miniatura **debería** ser preferiblemente una [tarjeta promocional amplia](https://i.imgur.com/3QfIc5v.jpg) o una [captura de pantalla](https://i.imgur.com/OAcBmwW.png) si la primera **no** está disponible.

### **`color`**

- El color **debe** ser un valor hexadecimal entre `#000000` y `#FFFFFF`.
- La cadena de color **debe** estar precedida por un hashtag.

### **`etiquetas`**

- **Todas** las presencias requieren por lo menos _una_ etiqueta.
- Las etiquetas **no** deben tener espacios, slashes, comillas simples o dobles, caracteres Unicode y siempre deberían ser en minúscula.
- Las etiquetas **deberían** incluir preferiblemente nombres de servicio alternativos para hacer su búsqueda mas fácil ( por ejemplo, si una presencia Amazon hubiese incluido soporte para AWS, debería tener sus etiquetas como `amazon-web-services` y `aws`)
- Estás **obligado** a añadir una etiqueta `NSFW` si la presencia es para un sitio web NSFW.

### **`categoría`**

- La categoría **debe** ser una de las siguientes listadas en la [documentación](https://docs.premid.app/en/dev/presence/metadata#presence-categories).
- The presence must use a category that matches the content of the website. (for e.g., don't use `anime` when the website isn't related to anime).

### **`regExp`** <br /> **`iFrameRegExp`**

- Las expresiones regulares **deben** ser válidas. Por favor pruebe sus expresiones con las herramientas listadas en la [documentación](https://docs.premid.app/en/dev/presence/metadata#testing).

### **`ajustes`**

- Si decide crear una cadena de formato (p.e. `%song% por %artist%`), debe tener las variables rodeadas por un signo de porcentaje en cualquiera de los lados. Variables como `%var`, `var%`, o `%%var%%` y todo lo que esté entre intermedios **no** está permitido por el bien de la estandarización.
- The name of settings must **not** be in all capital letters. For example, names such as `SHOW BROWSING STATUS` will **not** be permitted; however, names such as `Show Browsing Status` or `Show browsing status` are permitted.

## [**presence.ts**](https://docs.premid.app/en/dev/presence/class)

> El código que escribas **debe** estar _bien escrito_ y **debe** ser _entendible_ y todas las palabras deben ser gramaticalemente correctas (errores gramaticales de páginas wen pueden ser ignoradas). 
> 
> {.is-warning}

Aquí hay una lista de las reglas que debes seguir al escribir tu archivo `presence.ts`:

- **Siempre** declare una nueva instancia de la clase `Presence` antes de cualquier otra variable para evitar problemas raros que puedan ocurrir; no es un requisito por diseño para que pueda ser eliminado en el futuro.
- **Nunca** utilice funciones personalizadas cuando [variantes nativas estén disponibles](https://docs.premid.app/dev/presence#files-explained); esto asegura que las correcciones en el nivel de extensión también se aplican a sus presencias. Eres libre de usar lo que sea que necesites, si no los encuentras listados en la documentación.
- Está **prohibido** escribir presencias para un sitio sin añadir soporte para su idioma de origen (por ejemplo, una presencia de YouTube escrita con soporte solo para Portugués y Japonés, pero no para Ingés.)
- Los campos `smallImageKey` y `smallImageText` están destinados a proporcionar contexto adicional/secundario (como `reproducir/pausado` para sitios de vídeo, `navegando` para sitios normales, y otros casos) no para promover perfiles de Discord ni nada que no esté relacionado con PreMiD.
- **No** estás autorizado para acceder a `localStorage`.
- Al acceder a las cookies de los datos almacenados, por favor prefije la clave con `PMD_`.
- You may only make HTTP/HTTPS requests to `premid.app` or the presence website API. Si está utilizando dominios externos, tendrá que explicar por qué son necesarios.

## [**tsconfig.json**](https://docs.premid.app/en/dev/presence/tsconfig)

> **No** escribas tu propio `tsconfig.json`, usa el proporcionado en la [documentación](https://docs.premid.app/en/dev/presence/tsconfig). 
> 
> {.is-warning}

# Modificación

> **Debes** cambiar la versión en **metadata.json** a un valor mayor de la versión anterior cuando hagas cambios en los archivos **presence.ts**, **iframe.ts** o**metadata.json**. 
> 
> {.is-warning}

En algunas situaciones, las presencias pueden comportarse inesperadamente o podrían realizarse cambios menores para mejorar su funcionalidad. Aquí hay una lista de situaciones que usted **debe** tener en cuenta al modificar presencias.

- Usted **no** tiene permitido reescribir una presencia o cambiar su autor. Si la el autor de la Presencia fue baneado del servidor oficial o no ha hecho los cambios requeridos en un periodo de un mes, puedes contactar con un verificador de presencias para ver si puedes reescribir la Presencia.
- Cualquiera puede proporcionar parches rápidos (hotfixes) para corregir errores; sin embargo, intente **no** hacer cambios en el código que **no** necesitan ser corregidos. Las modificaciones válidas puedes ser, pero **no** están limitadas a _rutas faltantes_, _errores tipográficos_, _imágenes faltantes_, etc.
- Si haces modificaciones a una presencia que afecten al menos a un **un cuarto** del código base de la misma, tienes permitido añadirte como colaborador. Póngase en contacto con un verificador para más información sobre este tema.
- Asegúrese de que las modificaciones son útiles. Estos pueden incluir correcciones (de código o tipográficas), añadidos (descripciones y etiquetas), etc. **No** cambie las imágenes si no están desactualizadas y están en especificaciones.

# Verificación

> Si necesitas contactar con alguien, por favor usa nuestro servidor oficial de Discord. Todos los verificadores tienen el rol `Presence Verifier` en su perfil. 
> 
> {.is-info}

> **Todo** código contribuido será bajo la licencia `Mozilla Public License 2.0`. 
> 
> {.is-info}

> Ten **siempre** un fork actualizado antes de crear el pull request. Esto facilitará falsos positivos de `DeepScan`. 
> 
> {.is-warning}

El proceso más importante de desarrollo de una presencia es publicar tu presencia en la tienda. Esto se hace haciendo un [pull request](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request) en GitHub en el repositorio `PreMiD/Presences`. Nuestros verificadores confirmarán que su presencia está a la altura de los estándares y será colocada en la tienda.

<div>
  <h2 style="font-size: 2rem; margin-bottom: 0;">Verificadores</h2>
  <a href="https://github.com/Alanexei"><img src="https://github.com/Alanexei.png?size=2048" width="48px" style="max-width:100%; border-radius: 50%;"/></a>
  <a href="https://github.com/Bas950"><img src="https://github.com/Bas950.png?size=2048" width="48px" style="max-width:100%; border-radius: 50%;"/></a>
  <a href="https://github.com/doomlerd"><img src="https://github.com/doomlerd.png?size=2048" width="48px" style="max-width:100%; border-radius: 50%;"/></a>
  <a href="https://github.com/frozaum"><img src="https://github.com/frozaum.png?size=2048" width="48px" style="max-width:100%; border-radius: 50%;"/></a>
  <a href="https://github.com/TheDropX"><img src="https://github.com/TheDropX.png?size=2048" width="48px" style="max-width:100%; border-radius: 50%;"/></a>
  <br />
</div>

## `Revisiones`

Algunas cosas que deberías saber después de abrir una solicitud de pull request:

- Se necesitan 2 revisores para combinar un pull request.
- Si un pull request está inactivo durante un período de 7 días, será cerrado inmediatamente.
- Todas las verificaciones **deben pasar** para combinar.
- ⚠️Tú **debes** proporcionar, nuevas capturas de pantalla sin alterar (tomadas por ti) mostrando una comparación lado a lado de tu perfil y el sitio web para demostrar que tu presencia funciona. _Se le permite unir capturas de pantalla para el disfrute visual_ Esto se aplica tanto para la creación como para la modificación.
- ⚠️ You are also **required** to include screenshots of the presence settings in the extension if supplied. An example can be seen [here](https://imgur.com/a/OD3sj5R).

## `Verificaciones`

![Verificaciones](https://i.imgur.com/bk0A1iY.png)

Actualmente, una presencia pasa por 2 etapas separadas de comprobaciones. Todos estos controles ayudan a que los verificadores determinen si su presencia es adecuada para su implementación.

- `DeepScan` es un bot que comprueba la calidad del código. Si alguna vez recibes errores para nuevos problemas, eres **requerido** para corregirlos.
- `Schema Validation` escaneará su archivo `metadata.json` en busca de cualquier error (por ejemplo, campos faltantes, tipos de valor no válidos, etc.). Si alguna vez recibes errores para nuevos problemas, eres **requerido** para corregirlos. Añadir un campo de esquema a su archivo `metadata.json` permitirá a su editor de texto (si es compatible) mostrar estos errores durante el desarrollo.

## `Reglas adicionales`

- **Siempre** asegúrese de iniciar su presencia en la carpeta más apropiada, si su nombre comienza con _cualquier_ letra latina entonces debe estar bajo su coincidencia alfabética (p. ej. `D/dアニメストア` o `G/Google`). Cualquier otro carácter Unicode/no latino **debe** estar bajo la carpeta `#` (por ejemplo, `#/巴哈姆特.`) y números bajo la carpeta `0-9` (por ejemplo, `0-9/4anime`).

Después de cumplir con todas las directrices con las revisiones y comprobaciones adecuadas, su presencia se fusionará con la tienda.

# Contribuidores

La `revisión 2` de las indicaciones fue escrita y contribuida por los siguientes individuos:

<div>
<a href="https://github.com/Alanexei"><img src="https://github.com/Alanexei.png?size=2048" width="48px" style="max-width:100%; border-radius: 50%;"/></a>
</div>

La `revisión 1` fue mantenida por los siguientes individuos:

<div>
<a href="https://github.com/Alanexei"><img src="https://github.com/Alanexei.png?size=2048" width="48px" style="max-width:100%; border-radius: 50%;"/></a>
<a href="https://github.com/Bas950"><img src="https://github.com/Bas950.png?size=2048" width="48px" style="max-width:100%; border-radius: 50%;"/></a>
<a href="https://github.com/doomlerd"><img src="https://github.com/doomlerd.png?size=2048" width="48px" style="max-width:100%; border-radius: 50%;"/></a>
</div>
