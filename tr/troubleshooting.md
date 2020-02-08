---
title: Sorun Giderme
description: Karşılaştığınız hatayı çözebilmek için her şey
published: true
date: 2020-01-19T23:42:09.728Z
tags:
---

> Uzantıyı **ve** uygulamanın yüklü olduğundan emin olun! 
> 
> {.is-warning}

### Sayfayı yenileyin
İster yenileme butonuna tıklayın, isterseniz de klavyenizden <kbd>CTRL+R/F5</kbd> (Windows)/<kbd>CMD+R</kbd> (macOS) tuşlarına basın.

### Tarayıcınızı yeniden başlatın
<kbd>Alt</kbd>+<kbd>F4</kbd> (Windows) ya da <kbd>CMD</kbd>+<kbd>Q</kbd> (MacOS) tuşlarını kullanarak tarayıcınızı kapatın. Kapattıktan sonra elle yeniden açmanız gerekiyor elbette.

### Ayarlardaki Oyun Etkinliği'nin açık olduğuna emin olun
**Kullanıcı Ayarları** > **Oyun Etkinliği** ![gameactivity_edited.png](/gameactivity_edited.png)

### PreMiD Uygulamasını Yeniden Başlatın
![quit.png](/quit.png) PreMiD uygulamasını yeniden başlatmak bazen sorununuzu çözebilir.

### Discord'u yeniden başlatın
İsterseniz el ile yeniden başlatın, isterseniz de klavyenizi kullanarak şu tuş kombinasyonlarını uygulayın: <kbd>CTRL+R</kbd> (Windows) / <kbd>CMD+R</kbd> (MacOS)

### Discord'un yönetici olarak çalışmadığından emin olun
Bu işlem çok önemlidir. Eğer Discord'u yönetici olarak çalıştırırsanız Discord RPC çalışmayacaktır.

### Bilgisayarınızda çalışan bir antivirüs programı veya güvenlik duvarı olup olmadığını kontrol edin
Bazen antivirüs programlarınız veya güvenlik duvarınız yerel ağınızda sunucu oluşturan/yöneten veya sadece interneti kullanmaya çalışan uygulamaları kısıtlayabilir. Uygulamamız ve eklentimiz arasında veri alışverişi yapabilmek için yerel ağınızda oluşturulmuş bir sunucu kullanmamız gerekiyor, eğer bu yetkiyi uygulamaya vermezseniz, PreMiD'i kullanamazsınız.

### Eklentilerinizi devre dışı bırakın
Tüm eklentileri devre dışı bırakıp eklentimizin çalışıp çalışmadığını kontrol edin. Eğer çalışıyorsa, birer birer devre dışı bıraktığınız eklentileri tekrar aktifleştirin ve hangisinin PreMiD'i bozduğunu bulmaya çalışın.

### Bilgisayarınızı yeniden başlatın
Bir bilgisayarın nasıl yeniden başlatılacağını bildiğinizi umuyoruz.

### PreMiD'i yeniden yükleyin
Bazen dosyalarda bir sorun olabiliyor... Kurulum için gerekli adımları [buradan](/install) öğrenebilirsiniz.

### Manuel kaldırma
Windows:   `C:\Users\USER\Program Files (x86)\`` konumuna girin ve PreMiD klasörünü silin`. MacOS: `~/users/USER/~Library/ApplicationSupport/ konumuna girin ve PreMiD klasörünü silin`.

### Ubuntu/Debian tabanlı dağıtımlarda
Eğer Discord'u Snapcraft üzerinden indirdiyseniz, RPC özellikleri çalışmayacaktır. Bunu çözebilmek için `sudo snap remove discord` kodu ile Snapcraft üzerinden yüklenen Discord'u silmeli ve [buradaki](https://discordapp.com/api/download?platform=linux) (veya [buradaki](https://discordapp.com/api/canary/download?platform=linux)) adresten Discord'un Linux dosyasını indirmeli, ardından yükleme konumuna (bu genellikle `$HOME/Downloads` olur) girerek `sudo dpkg -i discord-*.deb` kodu ile sisteminize yüklemelisiniz.

### Bunların hiçbiri sorununuzu çözmediyse
[#support](https://discord.gg/PreMiD) kanalından bir destek kaydı oluşturmayı deneyin.