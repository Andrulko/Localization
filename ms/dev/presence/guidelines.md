---
title: Guidelines
description: Peraturan yang kesemua pembangun Presence perlu ikut untuk membolehkan Presence mereka ditambah.
published: true
date: 2020-12-06T19:43:05.270Z
tags:
editor: markdown
dateCreated: 2020-06-11T18:04:45.733Z
---

# Guidelines

Apabila menerbitkan Presence ke GitHub ini, anda perlu mengikut set garis panduan. To some, these strict rules may seem harsh. However, the implementation of these rulesets will keep us and the users from running into any issues.

# Creation

Peraturan am pembangunan Presence adalah seperti berikut:

- Presence **mestilah** berkait dengan laman sesawang dipilih.
- Presence **tidak boleh** dibuat untuk laman sesawang haram. (for e.g., stressors, drug marketing, child pornography, etc.)
- The file structure must be clean and managed, do not include files which are not specified. (for e.g., vscode and git folders, image and text files, etc.)
- You need to have a proper file structure, drafts are **not** allowed.
- Presence untuk laman sesawang dengan (TLD `.onion`) atau laman sesawang dengan domain/hos percuma (sbg. cth., `.TK` [semua domain percuma Freenom], `.RF`, `GD`, dll) adalah **tidak** dibenarkan, pengecualian boleh dibuat sekiranya terdapat bukti bahawa mereka bayar untuk domain tersebut.
- The domain of the presence must be at least 2 months old.
- Presence yang mensasarkan halaman pelayar dalaman (seperti Chrome Web Store, `chrome://`, halaman `about:`, dll) **tidak** dibenarkan kerana mereka perlukan bendera uji kaji untuk dibolehkan di pihak pengguna dan mampu menyebabkan kerosakan pada pelayar mereka.
- Presence dengan sokongan hanya untuk subdomain tunggal **tidak** akan dibenarkan, kerana ia akan tampak rosak untuk halaman lain (seperti halaman utama), pengecualian boleh dibuat untuk halaman polisi dan perhubungan (kandungan yang tidak kerap digunakan) atau laman di mana kandungan lainnya tidak mempunyai kaitan. (for e.g., wikia pages)
- Presence untuk radio dalam talian hanya dibenarkan sekiranya radio tersebut mempunyai sekurang-kurangnya 100 pendengar mingguan dan 15 pendengar serempak.
- Presence kualiti rendah (atau yang mana dengan konteks kecil) adalah **tidak** dibenarkan (sbg. cth., hanya menunjukkan logo dan tulisan tetapi tidak mengubahnya lagi.)
- Penyertaan folder `dist`, fail `presence.ts`, fail `iframe.ts`, dan fail `metadata.json` adalah diwajibkan supaya hasilnya nanti serupa seperti apa yang diwakilkan dalam skema berikut:

```bash
presence
├── dist
│   ├── metadata.json
│   └── presence.js
├── presence.ts
└── tsconfig.json
```

or if you're using a `iframe.ts` file:

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

> Untuk kemudahan para pembangun Presence kami, kami telah sediakan skema yang anda boleh gunakan untuk mengesahkan kewibawaan fail `metadata` anda. This is entirely optional and is not required during the review process. 
> 
> {.is-info}

> It is highly recommended that you organize your `metadata` file in the format shown below, and you must have grammatically correct service names, descriptions, tags, and setting fields. Anything not organized to specifications will **not** be permitted. 
> 
> {.is-warning}

> Presence untuk laman sesawang yang mempunyai kandungan dewasa **mesti** mempunyai tag `nsfw`, dan logo/lakaran kecil berkaitan **tidak** boleh mengandungi kandungan sebegini. 
> 
> {.is-warning}

Setiap Presence mempunyai fail pemerihal dipanggil `metadata.json`, metadata tersebut mempunyai piawaian ketat dan contoh fail ini boleh dilihat di bawah:

```json
{
  "$schema": "https://schemas.premid.app/metadata/1.0",
  "author": {
    "name": "USER",
    "id": "ID"
  },
  "contributors": [
    {
      "name": "USER",
      "id": "ID"
    }
  ],
  "service": "SERVICE",
  "altnames": ["SERVICE"],
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

> Sekiranya sesuatu medan disenaraikan sebagai pilihan dalam [pendokumenan](https://docs.premid.app/en/dev/presence/metadata) dan Presence anda menggunakan nilai lalai untuknya, jangan sertakannya dalam fail `metadata`. (sbg. cth., sebuah Presence tanpa sokongan iframe tidak perlukan medan `iframe`.) 
> 
> {.is-warning}

> All images in the `metadata` file must be hosted on `i.imgur.com`. Using content hosted on the website is **not** permitted as they can change the paths and files unwillingly. 
> 
> {.is-warning}

A list of fields and their rules are listed below:

### **`$schema`**

- The schema _key_ **must** include a dollar sign at the beginning of it, this will signal your text editor that you want to validate your JSON file against a model. _As stated earlier, you do not need to include a schema, but if you include it you must take this into account._

### **`author`**

- The ID _value_ **must** be your Discord snowflake ID. You can get it by enabling [developer mode](https://support.discord.com/hc/en-us/articles/206346498-Where-can-I-find-my-User-Server-Message-ID-). _Tolong **jangan** kelirukan yang ini dengan ID aplikasi anda, yang hanya digunakan untuk Presence anda._

### **`contributors`**

- **Jangan** tambah diri sendiri sebagai penyumbang, dan jangan tambah orang lain sebagai penyumbang melainkan mereka telah membantu dalam ciptaan Presence.

### **`service`**

- Nama perkhidmatan **mestilah** sama dengan nama direktori Presence tersebut. Sebagai contoh, jika Presence berada di `/websites/Y/YouTube/`, maka nama perkhidmatannya mestilah `YouTube`.
- You **cannot** use the url as the service name unless the website uses the url as its official name. If the name is not descriptive and can be considered vague, using the url is **required**. (for e.g., `YouTube` is permitted because that is the official name and is descriptive, while `youtube.com` is not. `Top` is a non-descriptive name, so using the url `top.gg` is **required**.)

### **`altnames`**

- **Hanya** gunakan ini dalam senario di mana laman sesawang menggunakan beberapa nama rasmi berlainan (spt. Pokémon and 포켓몬스터) atau untuk memudahkan pencarian Presence tanpa menggunakan aksara istimewa (spt. Pokémon dan Pokemon). *Shortened* versions of service names go under `tags`.

### **`keterangan`**

- **Semua** Presence **mesti** mempunyai keterangan bahasa Inggeris tanpa mengira bahasa keutamaan laman sesawang.
- Do **not** try and translate the description yourself unless you know that language, translators will modify your `metadata.json` and change the descriptions if necessary.

### **`url`**

- The url **must** be a string if the website only uses one domain. If the website uses multiple, make this an array and specify each one.
- Do **not** include protocols in the url (for e.g., `http` or `https`), and do not include query parameters in the url (for e.g., `www.google.com/search?gws_rd=ssl` which should be `www.google.com`)

### **`version`**

- Always make sure the version number follows [semantic versioning standards](https://semver.org), which translates to the following scheme: `<NEW-FEATURE>.<HUGE-BUGFIX>.<SMALL-BUGFIX-OR-METADATA-CHANGES>`. Anything else like `1.0.0.1`, `1.0`, `1`, `1.0.0-BETA` or changing `1.0.0` to `2.0.0` on a bug fix/small change is **not** permitted.
- The version **must** always start at `1.0.0` unless told otherwise, other versions will **not** be permitted.

### **`logo`**

- The logo **must** be a square image with a `1:1` aspect ratio.
- The image is **required** to have a minimum resolution of `512x512` pixels. You can upsize the imagine using a tool like [waifu2x](http://waifu2x.udp.jp/).

### **`thumbnail`**

- The thumbnail **should** preferably be a [wide promotional card](https://i.imgur.com/3QfIc5v.jpg) or a [screenshot](https://i.imgur.com/OAcBmwW.png) if the first is **not** available.

### **`color`**

- The color **must** be a hexadecimal value between `#000000` and `#FFFFFF`.
- The color string **must** be prepended with a hash symbol.

### **`tags`**

- **Semua** Presence mesti mempunyai sekurang-kurangnya _sebuah_ tag.
- Tags must **not** include any spaces, slashes, single/double quotation marks, Unicode characters, and should always be lowercase.
- Tag **sepatutnya** menyertakan nama perkhidmatan alternatif untuk memudahkan carian (sbg. cth., jika Presence untuk Amazon menyertakan sokongan AWS, ia perlu ada tag seperti `amazon-web-services` dan `aws`)
- Anda **perlu** tambah tag `NSFW` sekiranya Presence tersebut adalah untuk laman sesawang dewasa (NSFW 18+).

### **`category`**

- Kategori **mestilah** di kalangan kategori yang disenaraikan dalam [pendokumenan](https://docs.premid.app/en/dev/presence/metadata#presence-categories).
- Presence mestilah menggunakan kategori yang serasi dengan kandungan laman sesawang. (for e.g., don't use `anime` when the website isn't related to anime).

### **`regExp`** <br /> **`iFrameRegExp`**

- Regular expressions **must** be valid. Sila uji ungkapan anda menggunakan alatan yang disenaraikan dalam [pendokumenan](https://docs.premid.app/en/dev/presence/metadata#testing).

### **`settings`**

- If you decide to make a format string (for e.g., `%song% by %artist%`), you must have the variables surrounded by a percent sign on either side. Variables like `%var`, `var%`, or `%%var%%` and anything in between are **not** permitted for the sake of standardization.
- The name of settings must **not** be in all capital letters. For example, names such as `SHOW BROWSING STATUS` will **not** be permitted; however, names such as `Show Browsing Status` or `Show browsing status` are permitted.

## [**presence.ts**](https://docs.premid.app/en/dev/presence/class)

> The code you write **must** be _well-written_ and **must** be _readable_ and all strings must be grammatically correct (grammar errors on websites can be ignored). 
> 
> {.is-warning}

> Setiap Presence perlu ikut set peraturan lin yang ketat yang akan diperiksa semasa proses semakan. A couple of recommendations can be seen below. - [TypeScript Plugin Recommendations for Strict Type Checking](https://github.com/typescript-eslint/typescript-eslint/tree/master/packages/eslint-plugin/docs/rules) - [ESlint Recommendations](https://eslint.org/docs/rules) 
> 
> {.is-info}

Ini senarai peraturan yang perlu diikut semasa menulis fail `presence.ts` anda:

- **Sentiasa** isytihar tika baharu kelas `Presence` sebelum isytihar pembolehubah lain untuk mengelakkan isu terpencil yang mampu berlaku; ini bukan keperluan mengikut reka cipta jadi ia mungkin dialihkan pada masa hadapan.
- **Jangan** guna fungsi sendiri apabila [varian natif telah wujud](https://docs.premid.app/dev/presence#files-explained); ini untuk memastikan pembaikian di peringkat sambungan akan turut dikenakan pada Presence anda. You're free to use whatever you need if you do not find them listed in the docs.
- Anda **dilarang** mengekod Presence untuk sesuatu laman tanpa menambah sokongan bahasa utamanya (sbg. cth., Presence untuk YouTube dikodkan dengan sokongan untuk bahasa Portugis dan bahasa Jepun, tanpa bahasa Inggeris itu sendiri.)
- The `smallImageKey` and `smallImageText` fields are intended to provide additional/secondary context (such as `playing/paused` for video sites, `browsing` for regular sites, and other cases) not to promote Discord profiles or anything unrelated to PreMiD.
- You are **not** allowed to access `localStorage`.
- When accessing cookies for stored data, please prefix the key with `PMD_`.
- Anda hanya boleh lakukan permintaan HTTP/HTTPS ke `premid.app` atau API laman sesawang Presence. If you are using external domains, you will be required to explain why it is necessary.
- **Jangan** tetapkan medan dalam objek data Presence sebagai tak tertakrif setelah ianya diisytiharkan, sebaliknya gunakanlah kata kunci `delete`. (for e.g., use `delete data.startTimestamp` instead of `data.startTimestamp = undefined`)
- Anda **tidak** dibenarkan untuk menulis Presence yang mengubah kefungsian laman sesawang yang berkaitan. This includes the addition, deletion, or modification of DOM elements.

## [**tsconfig.json**](https://docs.premid.app/en/dev/presence/tsconfig)

> **Jangan** tulis fail `tsconfig.json` anda sendiri, gunakan apa yang telah disediakan dalam [pendokumenan](https://docs.premid.app/en/dev/presence/tsconfig). 
> 
> {.is-warning}

# Modification

> Anda **mesti** ubah versi dalam **metadata** kepada nilai lebih tinggi daripada versi sebelumnya apabila membuat perubahan kepada fail **presence.ts**, **iframe.ts** atau **metadata.json**. 
> 
> {.is-warning}

Dalam sesetengah keadaan, Presence mungkin berkelakuan luar jangkaan atau diubah secara kecil untuk meningkatkan kefungsian mereka. Ini senarai peraturan yang anda **mesti** ikuti ketika mengubahsuai Presence.

- Anda **tidak** dibenarkan untuk menulis semula sesebuah Presence atau mengubah penulisnya. Sekiranya penulis Presence telah diharamkan daripada pelayan rasmi atau masih belum membuat perubahan di dalam sebulan, anda boleh hubungi penyemak untuk tanya sama ada anda boleh menulis semula Presence tersebut.
- Jika anda mengubah suai sesebuah Presence dan mengubah sekurang-kurangnya **satu suku** daripada pangkalan kod Presence tersebut, anda dibenarkan menambah diri sendiri sebagai penyumbang. Hubungi penyemak untuk maklumat lanjut mengenai perkara ini.   - Jika anda mengubah suai sesebuah Presence dan mengubah sekurang-kurangnya **satu suku** daripada pangkalan kod Presence tersebut, anda dibenarkan menambah diri sendiri sebagai penyumbang. Contact a reviewer for more information about this subject.
-  Anyone may provide hotfixes to fix bugs; however, do **not** to make changes that are **not** required. Valid modifications include general fixes (code and typos), additions (descriptions and tags), missing files, etc. Do **not** change images if they are not outdated and are in specifications.

# Verification

> **All** code contributed to the store will be licensed under the `Mozilla Public License 2.0`. 
> 
> {.is-info}

> If you need to contact someone, please use our official Discord server. All reviewers will have the `Reviewer` role on their profile. 
> 
> {.is-info}

> Please keep in mind that the reviewers work voluntarily and manage other repositories in addition to this one, your pull request may not get reviewed until hours or even days after it has been created. 
> 
> {.is-warning}

> **Always** have an up-to-date fork before creating your pull request. This will help limit false positives from the checks. 
> 
> {.is-warning}

Proses paling penting dalam pembangunan Presence adalah untuk memasukkan Presence anda ke dalam kedai. Ini dilakukan dengan membuat [permintaan tarikan](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request) di GitHub pada repositori `PreMiD/Presences`. Penyemak kami akan sahkan Presence anda mengikut piawaian dan akan memasukkannya ke dalam kedai.

<div>
  <h2 style="font-size: 2rem; margin-bottom: 0;">Penyemak Presence</h2>
  <a href="https://github.com/Bas950"><img src="https://github.com/Bas950.png?size=2048" width="48px" style="max-width:100%; border-radius: 50%;"/></a>
  <a href="https://github.com/Timeraa"><img src="https://github.com/Timeraa.png?size=2048" width="48px" style="max-width:100%; border-radius: 50%;"/></a>
  <a href="https://github.com/ririxichan"><img src="https://github.com/ririxichan.png?size=2048" width="48px" style="max-width:100%; border-radius: 50%;"/></a>
  <br />
</div>

## `Restrictions`

Kesalahan berulang seperti pelanggaran garis panduan, penspaman permintaan tarikan, ancaman, atau perlakuan tidak sesuai akan mengharamkan anda daripada mencipta Presence.

In this scenerio, the following changes will occur:

- Presence di bawah pengurusan anda akan dipindahkan ke bot PreMiD atau pengguna lain (ikut kepurusan penyemak). ID aplikasi untuk setiap Presence akan dicipta semula di bawah nama pemilik baharu.
- Kesemua isu dan permintaan tarikan anda (penciptaan Presence, penyumbangan Presence, dll) yang dicipta setelah pengharaman akan ditutup dengan segera.
- Semua tiket yang dicipta di bawah nama anda berkaitan pembangunan Presence akan dipadam.


## `Reviewing`

A few things you should know after opening a pull request:

- It takes 2 reviewers to merge a pull request.
- If a pull request is inactive for a period of 14 days, it will be promptly closed.
- All checks **must** be passed in order to merge.
- ⚠️ Anda **mesti** berikan tangkapan layar baharu, tidak tersunting (diambil oleh anda sendiri) yang menunjukkan perbandingan profil anda dan laman sesawang untuk membuktikan Presence anda berfungsi. _You are allowed to stitch screenshots together for viewing pleasure._ This applies for both creation and modification.
- ⚠️ Anda juga **perlu** sertakan tangkapan layar tetapan Presence di dalam sambungan sekiranya dibekalkan. An example can be seen [here](https://imgur.com/a/OD3sj5R).

## `Checks`

![Checks](https://i.imgur.com/BCDZQe9.png)

Ketika ini, sesebuah Presence melalui dua (2) peringkat semakan yang berlainan. Kesemua semakan ini membantu penyemak untuk menentukan sama ada Presence anda sesuai untuk dikerahkan.

- `Codacy` is a bot that checks for code quality. If you ever receive errors for new issues, you are **required** to fix them.
- `Schema Validation` will scan your `metadata.json` file for any errors (for e.g., missing fields, invalid value types, etc.). If you ever see any new issues, you are also **required** to fix those. Adding a schema field to your `metadata.json` file will allow your text editor (if supported) to show you these errors during development.

## `Additional Rules`

- **Sentiasa** pastikan anda mulakan Presence anda dalam folder yang sesuai, sekiranya namanya bermula dengan _sebarang_ huruf Rumi maka ia mestilah berada di bawah padanan abjadnya (sbg. cth., `D/dアニメストア` atau `G/Google`). Any other Unicode/non-Latin characters **must** be under the `#` folder (for e.g., `#/巴哈姆特`) and numbers under the `0-9` folder (for e.g., `0-9/4anime`).

Setelah mematuhi kesemua garis panduan dengan ulasan dan semakan yang wajar, Presence anda akan dicantumkan dengan kedai.

# Contributions

`Revision 2` of the guidelines was written and was contributed to by the following individuals:

<div>
<a href="https://github.com/Alanexei"><img src="https://github.com/Alanexei.png?size=2048" width="48px" style="max-width:100%; border-radius: 50%;"/></a>
</div>

`Revision 1` diselenggara oleh insan berikut:

<div>
<a href="https://github.com/Alanexei"><img src="https://github.com/Alanexei.png?size=2048" width="48px" style="max-width:100%; border-radius: 50%;"/></a>
<a href="https://github.com/Bas950"><img src="https://github.com/Bas950.png?size=2048" width="48px" style="max-width:100%; border-radius: 50%;"/></a>
<a href="https://github.com/doomlerd"><img src="https://github.com/doomlerd.png?size=2048" width="48px" style="max-width:100%; border-radius: 50%;"/></a>
</div>
