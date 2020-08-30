---
title: Risoluzione problemi
description: Tutto per risolvere il tuo problema
published: vero
date: 2020-08-29T21:41:02.545Z
tags:
editor: markdown
---

> Assicurati di avere l'estensione **e** l'applicazione installata! 
> 
> {.is-warning}

### Stai usando una presenza con le impostazioni?
Molte presenze (tra cui `Twitch` e `SoundCloud`) sono affette da un problema di estensione. Questo problema fa sì che l'estensione non controlli correttamente i valori predefiniti delle impostazioni.

Per risolvere questo problema, tutto quello che devi fare è attivare/disattivare l'impostazione in cima: ![presencesettings.gif](/presencesettings.gif)

### Ricarica la pagina
Puoi anche premere <kbd>CTRL+R</kbd>/<kbd>F5</kbd> (Windows) o <kbd>CMD+R</kbd> (MacOS) sulla tua tastiera invece di cercare il pulsante di aggiornamento.

### Riavvia il browser
<kbd>Alt</kbd>+<kbd>F4</kbd> (Windows) o <kbd>CMD</kbd>+<kbd>Q</kbd> (MacOS) fa anche un buon lavoro. (È necessario riavviare il browser di nuovo, ovviamente.,)

### Assicurati di aver abilitato l'attività di gioco Discord nelle impostazioni
**Impostazioni utente** > **Attività di gioco** ![gameactivity_edited.png](/gameactivity_edited.png)

### Riavvia PreMiD (Applicazione)
![quit.png](/quit.png) È necessario riavviare PreMiD in seguito.

### Ricarica/riavvia Discord
Premi <kbd>CTRL+R</kbd> (Windows) o <kbd>CMD+R</kbd> (MacOS) sulla tua tastiera o riavvia Discord manualmente.

### Assicurati che Discord NON sia in esecuzione come amministratore
Davvero importante. Discord RPC non funzionerà se si esegue Discord come amministratore.

### Controlla se hai antivirus o firewall in esecuzione sul tuo computer
A volte programmi antivirus e firewall bloccano le applicazioni che stanno creando/hostando server o semplicemente che si connettono ad Internet. We are using a local server to receive and pass data between our app and extension, so if you will block app's ability to pass data you probably will not be able to use PreMiD.

### Disabilita i tuoi addons
Disabilita tutti i tuoi addons e scopri se funziona. Se sì, prova ad abilitare i tuoi addons passo dopo passo e dirci quale addon ha corrotto PreMiD.

### Riavvio del computer
Spero che tu sappia riavviare un computer.

### Reinstallazione PreMiD
A volte c'è qualcosa di sbagliato con i file... I tutorial per l'installazione possono essere trovati [qui](/install).

### Rimozione manuale
Windows:    `C:\Users\USER\AppData\Roaming\`` ed elimina la cartella`PreMiD`.
MacOS:`~/users/USER/~Library/Application Support/`ed elimina la cartella`PreMiD``.

### Sulle distribuzioni basate su Ubuntu/Debian
Se hai scaricato Discord attraverso Snapcraft, RPC non funzionerà. Devi disinstallare la versione di Snapcraft eseguendo `sudo snap remove discord` su un terminale, scarica [Discord Linux build](https://discordapp.com/api/download?platform=linux) ([o Discord Canary](https://discordapp.com/api/canary/download?platform=linux)), poi navigando nella directory scaricata su Discord (solitamente `$HOME/Downloads`), poi installando il pacchetto utilizzando `sudo dpkg -i discord-*.deb`.

### McAfee ha rilevato PreMiD come virus (Windows)
Questo è un falso positivo da McAfee e abbiamo riferito loro il problema, per ora è possibile escludere PreMiD dalla scansione facendo i seguenti passaggi:

> Se non ti senti sicuro di eseguire questi passaggi, sentiti libero di creare un ticket in [#support](https://discord.gg/WvfVZ8T) e uno dei nostri agenti di supporto sarà in grado di aiutarti! 
> 
> {.is-warning}

1. Apri l'applicazione McAfee e clicca sull'icona delle impostazioni in alto a destra. <img src="https://i.imgur.com/rPLZn6c.png" width="500px" style="max-width:100%;" />
2. Fare clic su "Elementi in quarantena" (Secondo dall'alto).
3. Espandilo, e clicca sull'icona `>` prima di un elemento con il nome "settings.dat".
4. Assicurati che il percorso includa "AppData\Local\Temp\PreMiD", se così selezionalo e premi su ripristino. <img src="https://i.imgur.com/9nvHmiI.png" width="500px" style="max-width:100%;" />
5. Dopo che è stato ripristinato è possibile chiudere il popup "Elementi in quarantena", quindi premere nuovamente l'icona delle impostazioni in alto a destra.
6. Fare clic su "Scansione in tempo reale" (Terzo dall'alto).
7. Espandilo e clicca su "Aggiungi file".
8. Digita "%appdata%" nella barra degli URL del file manager e premi Invio. <img src="https://i.imgur.com/2bchwLe.png" width="500px" style="max-width:100%;" />
9. Apri la cartella "PreMiD" e seleziona il file "PreMiD.exe" e clicca su apri. <img src="https://i.imgur.com/aHOyv3V.png" width="500px" style="max-width:100%;" />
10. McAfee ora dovrebbe ignorare il nostro file, basta avviare la nostra applicazione e dovrebbe andare tutto bene.

### Questo non ha risolto il mio problema
Si prega di aprire un ticket in [#supporto](https://discord.premid.app/).