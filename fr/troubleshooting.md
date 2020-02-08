---
title: Dépannage
description: Tout pour résoudre votre problème
published: vrai
date: 2020-01-19T23:42:09.728Z
tags:
---

> Assurez-vous d'avoir l'extension **et** l'application installée! 
> 
> {.is-warning}

### Recharger la page
Vous pouvez aussi appuyer sur <kbd>Strg+R</kbd>/<kbd>F5</kbd> (Windows) ou <kbd>CMD+R</kbd> (MacOS) sur votre clavier au lieu de rechercher le bouton de rafraîchissement.

### Redémarrez votre navigateur
<kbd>Alt</kbd>+<kbd>F4</kbd> (Windows) ou <kbd>CMD</kbd>+<kbd>Q</kbd> (MacOS) fait également un bon travail. (Vous devez redémarrer votre navigateur de toute évidence.)

### Assurez-vous d'avoir activé l'activité de jeu Discord dans les paramètres
**Paramètres utilisateur** > **Activité de jeu** ![gameactivity_edited.png](/gameactivity_edited.png)

### Redémarrer PreMiD (Application)
![quit.png](/quit.png) Vous devez redémarrer PreMiD par la suite.

### Recharger/redémarrer Discord
Appuyez sur <kbd>Strg+R</kbd> (Windows) ou <kbd>CMD+R</kbd> (MacOS) sur votre clavier ou redémarrez Discord manuellement.

### Assurez-vous que Discord ne fonctionne PAS en tant qu'administrateur
Vraiment important. Le RPC Discord ne fonctionnera pas si vous exécutez Discord en tant qu'administrateur.

### Vérifiez si vous avez un antivirus ou un pare-feu en cours d'exécution sur votre ordinateur
Parfois, les programmes antivirus et les pare-feu bloquent les applications qui créent/hébergent des serveurs ou se connectent simplement à Internet. Nous utilisons un serveur local pour recevoir et passer des données entre notre application et l'extension, donc si vous bloquez la capacité de l'application à passer des données, vous ne serez probablement pas en mesure d'utiliser PreMiD.

### Désactiver vos addons
Désactivez toutes vos extensions et voyez si cela fonctionne. Si oui, essayez d'activer vos addons pas à pas et dites-nous quel addon a cassé PreMiD.

### Redémarrage de votre ordinateur
J'espère que vous savez comment redémarrer un ordinateur.

### Réinstallation de PreMiD
Parfois, il y a quelque chose qui ne va pas avec les fichiers... Les tutoriels pour l'installation peuvent être trouvés [ici](/install).

### Suppression manuelle
Windows:    `C:\Users\USER\Program Files (x86)\`` et supprimez le dossier`PreMiD`.
MacOS :`~/users/USER/~Library/Application Support/`et supprimez le dossier`PreMiD``.

### Sur les distributions basées sur Ubuntu/Debian
Si vous avez téléchargé Discord via Snapcraft, RPC ne fonctionnera pas. Vous devez désinstaller la version de Snapcraft en exécutant `sudo snap remove discord` sur un terminal, télécharger la [version Linux de Discord](https://discordapp.com/api/download?platform=linux) ([ou Discord Canary](https://discordapp.com/api/canary/download?platform=linux)), puis naviguant dans le répertoire vers lequel vous avez téléchargé Discord (généralement `$HOME/Downloads`), puis l'installation du paquet en utilisant `sudo dpkg -i discord-*. eb`.

### Cela n'a pas résolu mon problème
Veuillez ouvrir un ticket dans [#support](https://discord.gg/PreMiD).