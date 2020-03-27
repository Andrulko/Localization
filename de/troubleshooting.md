---
title: Problemlösung
description: Alles, um dein Problem zu lösen
published: true
date: 2020-02-12T22:06:22.754Z
tags: 
---

> Stelle sicher, dass du die Erweiterung **und** die Anwendung installiert hast! 
> 
> {.is-warning}

### Die Seite neu laden
Sie können <kbd>Strg+R</kbd>/<kbd>F5</kbd> (Windows) oder <kbd>CMD+R</kbd> (MacOS) auch auf Ihrer Tastatur drücken, anstatt nach dem Aktualisieren-Button zu suchen.

### Browserneustart
<kbd>Alt</kbd>+<kbd>F4</kbd> (Windows) oder <kbd>CMD</kbd>+<kbd>Q</kbd> (MacOS) leisten ebenfalls gute Arbeit. (Du musst deinen Browser natürlich erneut starten.)

### Stelle sicher, dass du die Discord Spielaktivität in den Einstellungen aktiviert hast
**Benutzereinstellungen** > **Spielaktivität** ![gameactivity_edited.png](/gameactivity_edited.png)

### PreMiD (Anwendung) neustarten
![quit.png](/quit.png) Du musst PreMiD danach neu starten.

### Discord neu laden/neustarten
Drücke <kbd>Strg+R</kbd> (Windows) oder <kbd>CMD+R</kbd> (MacOS) auf deiner Tastatur oder starte Discord manuell neu.

### Stelle sicher, dass Discord NICHT als Administrator läuft
Sehr wichtig. Discord RPC wird nicht funktionieren, wenn du Discord als Administrator ausführst.

### Überprüfe, ob Antivirus oder Firewall auf deinem Computer läuft
Manchmal blockieren Antivirenprogramme und Firewalls Anwendungen, die Server erstellen/hosten oder einfach nur eine Verbindung zum Internet herstellen. Wir verwenden einen lokalen Server, um Daten zwischen unserer App und der Erweiterung zu erhalten und weiterzugeben, Wenn du also die Funktion der App blockierst, Daten zu übergeben, wirst du wahrscheinlich nicht in der Lage sein, PreMiD zu verwenden.

### Deaktiviere deine Addons
Deaktiviere alle deine Addons und überprüfe, ob es funktioniert. Wenn ja, versuche Schritt für Schritt deine Addons zu reaktivieren und teilen uns mit, welches Addon PreMiD behindert hat.

### Computer neustarten
Wir hoffen, dass du weißt wie du deinen Computer neustartest.

### PreMiD neu installieren
Manchmal stimmt etwas nicht mit den Dateien... Anleitungen für die Installation findest du [hier](/install).

### Manuelles Löschen
Windows:    `C:\Users\USER\Program Files (x86)\`` und lösche den Ordner `PreMiD`.
MacOS:`~/users/USER/~Library/Application Support/`und lösche den Ordner` PreMiD``.

### Auf Ubuntu/Debian basierten Distributionen
Wenn du Discord über Snapcraft heruntergeladen hast, wird Discords RPC nicht funktionieren. Du musst die Snapcraft Version deinstallieren, indem du `sudo snap remove discord` auf einem Terminal eingibst, lade als nächstes [Discords Linux Build](https://discordapp.com/api/download?platform=linux) herunter ([oder Discord Canary](https://discordapp.com/api/canary/download?platform=linux)), navigiere dann zu dem Verzeichnis, in welchem du Discord heruntergeladen hast (üblicherweise `$HOME/Downloads`), installiere dann das Paket mit `sudo dpkg -i discord-*.deb`.

### Das hat mein Problem nicht gelöst
Bitte öffne ein Ticket unter [#support](https://discord.gg/PreMiD).