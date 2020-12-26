---
title: إصلاح الاخطاء
description: كل شيء لحل مشكلتك
published: صحيح
date: 2020-12-15T20:00:08.631Z
tags:
editor: markdown
dateCreated: 2020-06-11T18:03:54.865Z
---

> تأكد من أن لديك الملحق **و** التطبيق مثبتين! 
> 
> {.is-warning}

### هل تستخدم تطبيق ديسكورد؟
**لا يعمل** PreMiD على إصدار ديسكورد للمتصفح، يجب عليك تحميل التطبيق [هنا](https://discord.com/download).

### هل تستخدم presence مع الإعدادات؟
تتأثر العديد من حالات التواجد (بما في ذلك ` Twitch `و SoundCloud</code>) بمشكلة الملحق. تؤدي هذه المشكلة إلى عدم التقاط الامتداد للقيم الافتراضية للإعدادات بشكل صحيح.

لحل هذه المشكلة ، كل ما عليك فعله هو تبديل الإعدادات الموجودة في الاعلى: ![presencesettings.gif](/presencesettings.gif)

### Reload the page
يمكنك الضغط على <kbd>CTRL+R</kbd>/<kbd>F5</kbd> (ويندوز) أو <kbd>CMD+R</kbd> (MacOS) على لوحة المفاتيح أيضا بدلا من البحث عن زر التحديث.

### Restart your browser
<kbd>Alt</kbd>+<kbd>F4</kbd> (Windows) or <kbd>CMD</kbd>+<kbd>Q</kbd> (MacOS) does a good job too. (You have to start your browser again obviously.)

### Make sure that you have enabled Discord Game Activity in settings
**User Settings** > **Game Activity** ![gameactivity_edited.png](/gameactivity_edited.png)

### Restart PreMiD (Application)
![quit.png](/quit.png) You have to restart PreMiD afterwards.

### Reload/restart Discord
Press <kbd>CTRL+R</kbd> (Windows) or <kbd>CMD+R</kbd> (MacOS) on your keyboard or restart Discord manually.

### Be sure Discord is running NOT as administrator
Really important. Discord RPC will not work if you run Discord as an administrator.

### Check if you have antivirus or firewall running on your computer
Sometimes antivirus programs and firewalls are blocking applications which are creating/hosting servers or just connecting to the internet. We are using a local server to receive and pass data between our app and extension, so if you will block app's ability to pass data you probably will not be able to use PreMiD.

### Disable your addons
Disable all your addons and see if it works. If yes, try to enable your addons step-by-step and tell us which addon broke PreMiD.

### Restarting your computer
I hope you know how to restart a computer.

### Reinstalling PreMiD
Sometimes there is something wrong with the files... Tutorials for the installation can be found [here](/install).

### Manual removal
Windows:    `C:\Users\USER\AppData\Roaming\`` and delete the folder`PreMiD`.
MacOS:`~/users/USER/~Library/Application Support/`and delete the folder`PreMiD``.

### On Ubuntu/Debian based distros
If you have downloaded Discord through Snapcraft, RPC will not work. You have to uninstall the Snapcraft version by executing `sudo snap remove discord` on a terminal, download [Discord's Linux build](https://discordapp.com/api/download?platform=linux) ([or Discord Canary](https://discordapp.com/api/canary/download?platform=linux)), then navigating to the directory you downloaded Discord to (usually `$HOME/Downloads`), then installing the package using `sudo dpkg -i discord-*.deb`.

### McAfee detected PreMiD as virus (Windows)
This is a false positive from McAfee and we have reported the issue to them, for now you can exclude PreMiD from the scan by doing the following steps:

> If you do not feel confident taking these steps, feel free to make a ticket in [#support](https://discord.premid.app/) and one of our Support Agents will be able to help you out! 
> 
> {.is-warning}

1. Open the McAfee application and click the settings icon in the top right. <img src="https://i.imgur.com/rPLZn6c.png" width="500px" style="max-width:100%;" />
2. Click "Quarantined Items" (Second from the top).
3. Expand it, and click the `>` icon before an item with the name "settings.dat".
4. Make sure the path includes "AppData\Local\Temp\PreMiD", if so select it and press restore. <img src="https://i.imgur.com/9nvHmiI.png" width="500px" style="max-width:100%;" />
5. After it is restored you can close the "Quarantined Items" popup, then press the settings icon again in the top right.
6. Click "Real-Time Scanning" (Third from the top).
7. Expand it and click "Add file".
8. Type "%appdata%" in the URL bar of the file manager and press Enter. <img src="https://i.imgur.com/2bchwLe.png" width="500px" style="max-width:100%;" />
9. Open the "PreMiD" folder and select the "PreMiD.exe" file and click open. <img src="https://i.imgur.com/aHOyv3V.png" width="500px" style="max-width:100%;" />
10. McAfee should now ignore our file, just launch our application and you should be good to go.

### That has not solved my problem
Please open a ticket in [#support](https://discord.premid.app/).