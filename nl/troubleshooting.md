---
title: Probleemoplossen
description: Alles om je probleem op te lossen
published: true
date: 2020-02-12T22:10:02.170Z
tags: 
---

> Zorg ervoor dat de extensie **en** de applicatie geïnstalleerd is! 
> 
> {.is-warning}

### Pagina herladen
U kunt ook op <kbd>Strg+R</kbd>/<kbd>F5</kbd> (Windows) of <kbd>CMD+R</kbd> (MacOS) op het toetsenbord drukken in plaats van te zoeken naar de refresh knop.

### Herstart uw browser
<kbd>ALT</kbd>+<kbd>F4</kbd> (Windows) of <kbd>CMD</kbd>+<kbd>Q</kbd> (MacOS) doet ook goed werk. (Je moet je browser weer opstarten.)

### Zorg ervoor dat Discord spel activiteit is ingeschakeld in de instellingen
**Gebruikersinstellingen** > **Spelactiviteit** ![gameactivity_edited.png](/gameactivity_edited.png)

### PreMiD herstarten (Applicatie)
![quit.png](/quit.png) U moet PreMiD daarna opnieuw starten.

### Discord herladen/herstarten
Druk op <kbd>Strg+R</kbd> (Windows) of <kbd>CMD+R</kbd> (MacOS) op je toetsenbord of start Discord handmatig opnieuw op.

### Zorg ervoor dat Discord NIET als administrator wordt uitgevoerd
Echt belangrijk! Discord RPC zal niet werken als je Discord als administrator gebruikt.

### Controleer of u antivirus of firewall draait op uw computer
Soms blokkeren antivirusprogramma's en firewalls toepassingen die maken/hosting servers maken of alleen verbinding maken met het internet. We gebruiken een lokale server voor het ontvangen en doorgeven van gegevens tussen onze app en extensie, dus als u de mogelijkheid van een app blokkeert om gegevens door te geven zal u waarschijnlijk PreMiD niet kunnen gebruiken.

### Uw addons uitschakelen
Schakel al uw addons uit en kijk of het werkt. Zo ja, probeer uw addons stap voor stap in te schakelen en vertel ons welke addon PreMiD defect maakt.

### Uw computer wordt opnieuw opstarten
Ik hoop dat u weet hoe u een computer opnieuw moet starten.

### PreMiD opnieuw installeren
Soms is er iets mis met de bestanden... Handleidingen voor de installatie kunnen [hier](/install) gevonden worden.

### Handmatige verwijdering
Windows:    `C:\Users\USER\Program Files (x86)\`` en verwijder de map `PreMiD`.
MacOS:`~/users/USER/~Library/Application Support/` en verwijder de map `PreMiD``.

### Op Ubuntu/Debian gebaseerde distro's
Als je Discord hebt gedownload via Snapcraft, zal RPC niet werken. Je moet de Snapcraft versie verwijderen door `sudo snap remove discord` uit te voeren op een terminal, download [Discord's Linux build](https://discordapp.com/api/download?platform=linux) ([of Discord Canary](https://discordapp.com/api/canary/download?platform=linux)), navigeer vervolgens naar de map die je Discord gedownload hebt naar (meestal `$HOME/Downloads`), daarna het installeren van het pakket met behulp van `sudo dpkg -i discord-*. eb`.

### Dat heeft mijn probleem niet opgelost
Open een ticket in [#support](https://discord.gg/PreMiD).