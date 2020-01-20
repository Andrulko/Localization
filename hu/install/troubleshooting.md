---
title: Hibaelhárítás
description: Minden ami megoldja a problémát
published: true
date: 2020-01-18T20:32:24.820Z
tags:
---

> Győződj meg arról, hogy a bővítmény **és** az alkalmazás is egyaránt telepítésre került! 
> 
> {.is-warning}

### Frissítsd az oldalt
Az oldalt frissítheted a <kbd>Strg+R</kbd>/<kbd>F5</kbd> (Windows) vagy a <kbd>CMD+R</kbd> (MacOS) gombok lenyomásával a billentyűzeten vagy megkeresheted a frissítés gombot is.

### Indítsd újra a böngészőt
<kbd>Alt</kbd>+<kbd>F4</kbd> (Windows) vagy a <kbd>CMD</kbd>+<kbd>Q</kbd> (MacOS) hasznos lehet ebben az esetben is. (Nyilvánvalóan, megint el kell indítanod a böngészőt.)

### Győződj meg arról, hogy engedélyezve vannak a Discord Játék tevékenységek a beállításokban
**Felhasználói beállítások** > **Játék tevékenység** ![gameactivity_edited.png](/gameactivity_edited.png)

### Indítsd újra a PreMiD alkalmazást
![quit.png](/quit.png) You have to restart PreMiD afterwards.

### Indítsd újra a Discord alkalmazást
A Discord kézi újraindításához nyomd meg a <kbd>Strg+R</kbd> (Windows) vagy a <kbd>CMD+R</kbd> (MacOS) gombokat a billentyűzeten.

### Győződj meg arról, hogy a Discord nem rendszergazdai jogokkal fut
Nagyon fontos. A Discord RCP nem fog futni, ha a Discord rendszergazda jogokkal fut.

### Check if you have antivirus or firewall running on your computer
Sometimes antivirus programs and firewalls are blocking applications which are creating/hosting servers or just connecting to the internet. We are using a local server to receive and pass data between our app and extension, so if you will block app's ability to pass data you probably will not be able to use PreMiD.

### Tiltsd le a bővítményeket
Tilts le minden bővítményt és ellenőrizd, hogy működik-e. Ha igen, próbáld meg -lépésről-lépésre- a bővítményeket engedélyezni és írd meg nekünk, hogy melyik bővítmény blokkolta a PreMiD-et a működésben.

### Indítsd újra a számítógépet
Azt remélem azért tudod, hogy hogyan kell egy számítógépet újraindítani.

### Telepítsd újra a PreMiD alkalmazást
Sometimes there is something wrong with the files... Tutorials for the installation can be found [here](/install).

### Kézi eltávolítás
Windows:    `C:\Users\USER\Program Files (x86)\`` and delete the folder`PreMiD`.
MacOS:`~/users/USER/~Library/Application Support/`and delete the folder`PreMiD``.

### On Ubuntu/Debian based distros
If you have downloaded Discord through Snapcraft, RPC will not work. You have to uninstall the Snapcraft version by executing `sudo snap remove discord` on a terminal, download [Discord's Linux build](https://discordapp.com/api/download?platform=linux) ([or Discord Canary](https://discordapp.com/api/canary/download?platform=linux)), then navigating to the directory you downloaded Discord to (usually `$HOME/Downloads`), then installing the package using `sudo dpkg -i discord-*.deb`.

### Ez nem oldotta meg a problémát
Please open a ticket in [#support](https://discord.gg/PreMiD).