---
title: Microsoft Intune - Azure'da iOS cihaz kısıtlama ayarları Ekle | Microsoft Docs
titleSuffix: ''
description: Ekleme, yapılandırma, veya iOS cihazların parola gereksinimlerini ayarlayın, kilit ekranı kontrol, yerleşik uygulamaları kullanın, kısıtlanmış veya onaylı uygulamalar ekleme, bluetooth cihazların işlemek, yeniden işlenmek üzere buluta bağlayın ve depolama ayarlarını oluşturun, bilgi noktası modu etkinleştirin ve etki alanları eklemek ve Kullanıcıların Microsoft Intune Safari web tarayıcısı ile nasıl etkileşim denetler.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: a677742c5d2f876c0714f13c4f62d059ced98584
ms.sourcegitcommit: ecd6aebe50b1440a282dfdda771e37fbb8750d42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2018
ms.locfileid: "52728982"
---
# <a name="ios-device-restrictions-settings-list-in-microsoft-intune"></a>iOS cihaz kısıtlama ayarları Intune listesinde

Bu makale, listeler ve iOS cihazlar için yapılandırabileceğiniz tüm cihaz kısıtlama ayarları açıklar. Bu ayarları bir cihaz yapılandırma profili eklendiğinde ve sonra atanan veya iOS cihazlarınızı Microsoft Intune kullanarak dağıtılmış.

## <a name="general"></a>Genel

- **Kullanım verilerini paylaş**: seçin **blok** cihazın Apple'a tanılama ve kullanım verileri göndermesini önlemek için. **Yapılandırılmamış** gönderilmek üzere bu verileri sağlar.
  - **Tanılama verilerinin gönderimine**: **blok** kullanıcının tanılama gönderiminde ve uygulama analizi ayarlarında değiştirmesini engeller **tanılama ve kullanım** (cihaz ayarları). Bu ayarı kullanabilmeniz için cihazın denetimli modda (iOS 9.3.2+) olmalıdır. **Yapılandırılmamış** bu cihaz ayarlarını değiştirmesine izin verir.
- **Ekran Yakalama**: seçin **blok** cihazın ekran veya ekran görüntüleri önlemek için. **Yapılandırılmamış** kullanıcının ekran içeriğini resim olarak yakalamasına izin verir.
  - **(Yalnızca denetimli) Classroom uygulamasıyla ekranı uzaktan izlemesine**: seçin **blok** Classroom uygulamasının ekranı cihazda uzaktan görüntülemesini engellemek için. Bu ayarı kullanabilmeniz için cihazın denetimli modda (iOS 9.3 ve üzeri) olmalıdır. **Yapılandırılmamış** ekranını görüntülemek Apple Classroom uygulamasını sağlar.
  - **İstem olmadan ekranı izleme (yalnızca denetimli) tarafından**: varsa kümesine **izin**, Öğretmenler sessizce öğrencilerin bilgisi olmadan Classroom uygulamasını kullanarak, öğrencilerin iOS cihazlarının ekranını inceleyin. Classroom uygulaması kullanılarak otomatik olarak bir sınıfa kaydolan Öğrenci cihazları izni o kursun öğretmenine. **Yapılandırılmamış** bu özellik engeller.
- **Güvenilmeyen TLS sertifikaları**: seçin **blok** cihazda güvenilmeyen Aktarım Katmanı Güvenliği (TLS) sertifikalarını önlemek için. **Yapılandırılmamış** TLS sertifikalarına izin verir.
- **Kurumsal uygulama güveni**: seçin **blok** kaldırmak için **güven Kurumsal Geliştirici** ayarları düğmesi > Genel > profiller ve cihazda cihaz yönetimi. **Yapılandırılmamış** kullanıcının uygulama Mağazası'ndan indirilen olmayan uygulamalara güvenmeyi seçmesine olanak sağlar.
- **Hesap değişikliği (yalnızca denetimli)**: ayarlandığında **blok**, kullanıcının iOS ayarları uygulamasından cihaza özgü ayarları güncelleştirilemiyor. Örneğin, kullanıcı olamaz yeni cihaz hesapları oluşturma veya kullanıcı adı ve parola ile değiştirin. **Yapılandırılmamış** kullanıcıların bu ayarlarını değiştirmesine olanak sağlar.
  Bu özellik, posta, kişiler, takvim, Twitter ve daha fazla gibi iOS ayarları uygulamasından erişilebilen ayarlar için de geçerlidir. Bu özellik, Microsoft Outlook uygulaması gibi iOS ayarları uygulamasından yapılandırılabilir olmayan hesap ayarları ile uygulamalar için geçerli değildir.
- **(Yalnızca denetimli) cihaz ayarlarında kısıtlamaları etkinleştirme**: seçin **blok** kullanıcıların, cihaz ayarlarında kısıtlamaları etkinleştirmesini önlemek için. **Yapılandırılmamış** kullanıcının cihazda cihaz kısıtlamalarını (ebeveyn denetimleri gibi) yapılandırmasına izin verir.
- **Silme (yalnızca denetimli) cihazda tüm içeriği ve ayarları seçeneğini kullanın**: seçin **blok** nedenle kullanıcılar silme tüm içerik ve ayarları (yalnızca denetimli) cihaz seçeneğini kullanamazsınız. **Yapılandırılmamış** kullanıcılara bu ayarlara erişim sağlar.
- **Cihaz adının değiştirilmesi (yalnızca denetimli)**: seçin **blok** cihaz adı değiştirilemez. **Yapılandırılmamış** kullanıcının cihazın adını değiştirmesine izin verir.
- **Bildirim ayarlarının değiştirilmesi (yalnızca denetimli)**: seçin **blok** bildirim ayarları değiştirilemez. **Yapılandırılmamış** kullanıcının cihazın bildirim ayarlarını değiştirmesine izin verir.
- **Duvar kağıdı değişikliği (yalnızca denetimli)**: **blok** duvar kağıdı değişmesini önler. **Yapılandırılmamış** kullanıcının cihazın duvar kağıdını değiştirmesine izin verir.
- **Kurumsal uygulama güven ayarlarının değiştirilmesi (yalnızca denetimli)**: **blok** kullanıcının denetimli cihazlarda Kurumsal uygulama güven ayarlarını değiştirmesini engeller. **Yapılandırılmamış** uygulama Mağazası'ndan indirilen olmayan uygulamalara güvenmeyi izin verir.
- **Yapılandırma profilindeki değişiklikler (yalnızca denetimli)**: **blok** cihaz yapılandırma profili değişiklikleri engeller. **Yapılandırılmamış** kullanıcının yapılandırma profilleri yüklemesine izin verir.
- **Etkinleştirme kilidi (yalnızca denetimli)**: seçin **izin** etkinleştirme Kilidi'ni etkinleştirmek için iOS cihazlarının denetimli. Etkinleştirme kilidi, bir kaybolan veya çalınan cihazın yeniden etkinleştirilmesini zorlaştırır.
- **Engelle (yalnızca denetimli) uygulama kaldırma**: seçin **blok** kullanıcılar uygulamaları kaldırmasını önlemek için. **Yapılandırılmamış** kullanıcıların CİHAZDAN uygulamalarının kaldırılmasına olanak tanır.
- **Blokları USB kısıtlı modu (yalnızca denetimli)**: seçin **blok** denetimli cihazlarda USB kısıtlı modu devre dışı bırakmak için. USB kısıtlı modu için bir saatten fazla kilitli olan bir cihaz ile veri değişimi gelen USB Donatılar engeller. **Yapılandırılmamış** USB kısıtlı modu sağlar.
- **Otomatik tarih ve saat (yalnızca denetimli) zorlamak**: **gerektiren** zorlar denetimli cihazların tarih ve saat otomatik olarak ayarlanır. Cihaz cep telefonu bağlantılarına sahiptir veya konum Hizmetleri ile Wi-Fi etkin olduğundan cihazın saat dilimini güncelleştirilir.
- **İstek bırakın (yalnızca denetimli) boyunca sınıfta kurs izni Öğrenciler gerektiren**: **gerektiren** bırakmak Öğretmen Classroom uygulamadan izin istemek kullanarak bir yönetilmeyen kursta kayıtlı öğrencilerin zorlar Kursu. İOS 11.3 + yalnızca kullanılabilir. **Yapılandırılmamış** Öğrenci izin istemek için zorlamaz.
- **Havadan PKI güncelleştirmelere izin**: **izin** , kullanıcıların cihazlarını bir bilgisayara bağlanmadan yazılım güncelleştirmeleri almasına olanak sağlar.
- **İzleme sınırı ad**: seçin **sınırı** cihaz reklam tanımlayıcısı devre dışı bırakmak için. **Yapılandırılmamış** etkin tutar.
- **(Yalnızca denetimli) blok VPN oluşturma**: **blok** kullanıcıların VPN yapılandırma ayarlarını oluşturmasını engeller. **Yapılandırılmamış** cihazda VPN oluşturmalarını sağlar.

## <a name="configurations-requiring-supervision"></a>Denetim gerektiren yapılandırmalar

iOS denetimli modu yalnızca Apple Aygıt Kayıt Programı üzerinden ilk cihaz kurulumu sırasında veya Apple Configurator kullanılarak etkinleştirilebilir. Denetimli mod etkinleştirildikten sonra, Intune şu işlevleri kullanarak bir cihazı yapılandırabilir:

- Uygulama Kilidi (Tek Uygulama Modu) 
- Genel HTTP Proxy’si 
- Etkinleştirme Kilidini Atlama 
- Otonom Tek Uygulama Modu 
- Web İçeriği Filtresi 
- Arka plan ve kilit ekranı ayarlama 
- Uygulamaları Sessiz Gönderme 
- Her Zaman Açık VPN 
- Yönetilen uygulama yüklemesine özel olarak izin verme 
- iBookstore 
- iMessages 
- Oyun Merkezi 
- AirDrop 
- AirPlay 
- Konak eşleştirme 
- Bulut Eşitleme 
- Spotlight arama 
- İletim 
- Cihaz silme 
- Kısıtlamalar kullanıcı arabirimi 
- Kullanıcı arabirimine göre yapılandırma profili yüklemesi 
- News 
- Klavye kısayolları 
- Geçiş kodu değişiklikleri 
- Cihaz adı değişiklikleri 
- Otomatik uygulama indirme 
- Kurumsal uygulama güvenine yapılan değişiklikler 
- Apple Music 
- Posta bırakma 
- Apple Watch ile eşleştirme 

> [!NOTE]
> Apple, 2019’da bazı ayarların yalnızca denetimli hale geleceğini doğruladı. Apple’ın bu ayarları yalnızca denetimli moduna aktarmasını beklemek yerine ayarları kullanırken, bu durumu göz önünde bulundurmanızı öneririz:
> - Son kullanıcılar tarafından uygulama yükleme
> - Uygulama kaldırma
> - FaceTime
> - Safari
> - iTunes
> - Müstehcen içerik
> - iCloud belgeleri ve verileri
> - Çok oyunculu oyun
> - Oyun merkezi arkadaşları ekleyin
> - Siri

## <a name="password"></a>Parola

- **Parola**: son kullanıcının cihaza erişmek için parola girmesini zorunlu tutun. Yapılandırılmamış bir parola girmeden cihaz erişmesine olanak tanır.
  - **Basit parolalar**: seçin **blok** daha karmaşık bir parola gerektirme. **Yapılandırılmamış** gibi basit parolalara izin verir `0000` ve `1234`.
  - **Gerekli parola türü**: kuruluşunuz gerekli parola türünü seçin. Seçenekleriniz şunlardır:
    - **Cihaz varsayılanı**
    - **Sayısal**
    - **Alfasayısal**
  - **Paroladaki alfasayısal olmayan karakter sayısı**: sembol karakterlerinin sayısını girin `#` veya `@`, eklenmesi gereken parola.
  - **Minimum parola uzunluğu**: gerekir girin (4-14 karakter arasında) bir kullanıcı alt sınırını girin.
  - **Cihaz silinmeden önceki oturum açma hatası sayısı**: (1-11 arasında) cihaz temizlenmeden önce izin başarısız oturum açma işlemlerinin sayısını girin.
  - **Parola istenmeden önce ekran kilitlendikten sonra en fazla dakika**<sup>1</sup>: kullanıcı parolasını yeniden girmeden önce cihazın ne kadar süreyle boşta kalır girin. Girdiğiniz zaman ne şu anda cihazda ayarlı olan süreden uzunsa cihaz girdiğiniz zaman yok sayar. İOS 8.0 ve daha yeni cihazlarda desteklenir.
  - **Ekran kilitlenmeden işlem yapılmayan dakika**<sup>1</sup>: ekran kilitlenmeden kadar cihazda izin verilen işlem yapılmayan dakika sayısı girin. Girdiğiniz zaman ne şu anda cihazda ayarlı olan süreden uzunsa cihaz girdiğiniz zaman yok sayar.
  - **Parola süresinin sonu (gün)**: cihaz parolasının değiştirilmesi gerekmeden önce geçen gün sayısını girin.
  - **Önceki parolaların yeniden kullanılmasını engelle**: eski bir parola yeniden kullanılana kadar kullanılması gereken yeni parola sayısını girin.
  - **Parmak iziyle kilit açma**: seçin **blok** cihazın kilidini açmak için parmak izi'ni kullanarak önlemek için. **Yapılandırılmamış** parmak izi kullanarak cihaz kilidini açmak kullanıcının sağlar.
- **Geçiş kodu değişikliği (yalnızca denetimli)**: seçin **blok** eklenen veya kaldırılan değiştirilmesini geçiş kodunu durdurmak için. Bu özellik engellendikten sonra geçiş kodu kısıtlamalarına yapılan denetimli cihazlarda dikkate alınmaz. **Yapılandırılmamış** eklenmesine, değiştirilmesine veya kaldırılması geçiş kodlarını sağlar.
  - **Parmak izi değişikliği (yalnızca denetimli)**: **blok** değiştirme, ekleme veya kaldırma Touchıd parmak izlerini kullanıcının durdurur. **Yapılandırılmamış** kullanıcı güncelleştirme Touchıd parmak izlerini cihazda izin verir.
- **Blok parola otomatik doldurma (yalnızca denetimli)**: seçin **blok** İos'ta parola otomatik doldurma özelliğinin kullanılmasını önlemek için. Seçme **blok** aynı zamanda şunları yapar:
  - Kullanıcılar, Safari veya herhangi bir uygulama kaydedilmiş bir parola kullanmayı sorulmaz.
  - Otomatik güçlü parolalar devre dışıdır ve kullanıcıların güçlü parolalar önerilen değildir.

  **Yapılandırılmamış** bu özellikleri sağlar.

- **(Yalnızca denetimli) parola yakınlık isteklerini engellemek**: seçin **blok** cihazın yakın cihazlardan parola istemeyen şekilde. **Yapılandırılmamış** bu parola istekleri sağlar.
- **Engelle (yalnızca denetimli) parola paylaşımı**: **blok** engeller parolaları Airdrop'a kullanarak cihazlar arasında paylaşma. **Yapılandırılmamış** paylaşılması parola sağlar.

<sup>1</sup>yapılandırdığınızda **ekran kilitlenmeden, işlem yapılmayan en fazla dakika** ve **dakika ekran kilitlendikten sonra parola istenmeden önce** ayarlarını sırayla uygulayarak. Örneğin, her iki ayarın değeri ayarlarsanız **5** dakika, beş dakika sonra otomatik olarak ekran kapatır ve cihaz kilitli bir ek sonra beş dakika. Ancak, kullanıcı ekranı el ile kapatırsa ikinci ayar hemen uygulanır. Aynı örnekte, kullanıcı ekranı kapattıktan dakikanın sonunda beş dakika sonra cihazı kilitler.

## <a name="locked-screen-experience"></a>Kilit Ekranı Deneyimi

- **Cihaz kilitliyken denetim merkezi erişimi**: seçin **blok** cihaz kilitliyken denetim merkezi uygulamasına erişimi engellemek için. **Yapılandırılmamış** kullanıcıların cihaz kilitliyken denetim merkezi uygulamasına erişmesine izin verir.
- **Cihaz kilitliyken bildirimler**: **blok** cihaz kilitliyken bildirimler için erişimi engeller. **Yapılandırılmamış** cihazın kilidini açmadan bildirimler erişime izin verir.
- **Cihaz kilitliyken bildirimler Cüzdan**: **blok** cihaz kilitli olduğunda Cüzdan uygulamaya erişimi engeller. **Yapılandırılmamış** cihaz kilitliyken kullanıcının Cüzdan uygulamasına erişmesine izin verir.
- **Cihaz kilitliyken bugün görünümü**: **blok** cihaz kilitliyken Bugün görünümüne erişimi engeller. **Yapılandırılmamış** cihaz kilitliyken kullanıcının Bugün görünümünü görmesine izin verir.

## <a name="app-store-doc-viewing-gaming"></a>Uygulama Mağazası, Belge Görüntüleme, Oyun

- **App Store'da**: **blok** denetimli cihazlarda uygulama mağazasına erişimi engeller. **Yapılandırılmamış** erişim sağlar.
  - **Uygulamaları App Store (yalnızca denetimli) yükleme**: seçin **blok** için cihaz giriş ekranından app store'u engelleyebilir. Son kullanıcılar, uygulamaları yüklemek için iTunes’u veya Apple Configurator aracını kullanmaya devam edebilir. **Yapılandırılmamış** giriş ekranına app Store'dan sağlar.
  - **Otomatik uygulama indirme (yalnızca denetimli)**: seçin **blok** diğer cihazlarda satın alınan uygulamaların otomatik yüklenmesini engellemek için. Bu, mevcut uygulamaların güncelleştirilmesini etkilemez. **Yapılandırılmamış** cihaza yüklemek için diğer iOS cihazlarda satın alınan uygulamalar sağlar.
- **Uygulama mağazasına erişim için parola**: **gerektiren** kullanıcı kullanıcının uygulama mağazasını ziyaret etmeden önce parola girmelerini isteyin. **Yapılandırılmamış** parola girmeden app Store'a erişim sağlar.
- **Uygulama içi satın almalar**: seçin **blok** Mağaza'dan uygulama içi Satınalmalar önlemek için. **Yapılandırılmamış** çalışan bir uygulama içinde depolama satın alımlarına izin verir.
- **Müstehcen iTunes müziği, podcast'i veya haber içeriği (yalnızca denetimli)**: seçin **blok** müstehcen iTunes müziği, podcast'i veya haber içeriği önlemek için. **Yapılandırılmamış** cihazın mağazadaki yetişkinlere yönelik olarak derecelendirilmiş içeriğe erişmesine izin verir.
- **İBook mağazasından 'Erotik'olarak işaretlenmiş içerik indirme**: seçin **blok** durakları kullanıcıların iBook mağazasından erotik olarak etiketlenmiş medya yüklenmesini önlemek için. **Yapılandırılmamış** kullanıcının "Erotik" kategorisindeki kitapları indirmesine izin verir.
- **Yönetilmeyen uygulamalarda Kurumsal belgeleri görüntüleme**: **blok** yönetilmeyen uygulamalarda Kurumsal olmayan belgeleri görüntüleme engeller. **Yapılandırılmamış** Kurumsal belgelerin tüm uygulamalarda görüntülenmesine izin verir. Örneğin, kullanıcıların OneDrive uygulamasından Dropbox'a dosya kaydetmesini gelen engellemek istiyorsunuz. Bu ayarın olarak **blok**. Cihaz İlkesi (örneğin, bir yeniden başlatma sonrasında) aldıktan sonra artık sağlayan kaydediliyor.
- **Kurumsal olmayan belgeleri Kurumsal uygulamalarda görüntüleme**: **blok** Kurumsal olmayan belgeleri Kurumsal uygulamalarda görüntüleme engeller. **Yapılandırılmamış** tüm belgelerin şirketin yönetilen uygulamalarında görüntülenmesine izin verir.
- **Airdrop'u yönetilmeyen hedef olarak değerlendir**: **gerektiren** Airdrop'u yönetilmeyen bir bırakma hedefi olarak kabul edilmesi için zorlar. Bu, yönetilen uygulamaların Airdrop kullanarak verileri göndermesini durdurur. 
- **(Yalnızca denetimli) Game Center arkadaşlarını eklemeye**: **blok** Game Center arkadaşlarını eklemeye gelen kullanıcıların engeller. **Yapılandırılmamış** Game Center'da arkadaş eklemesine izin verir.
- **Game Center (yalnızca denetimli)**: **blok** Game Center uygulamasının kullanımını. **Yapılandırılmamış** cihazda Game Center uygulamasının kullanımına izin verir.
- **Çok oyunculu oyunlar (yalnızca denetimli)**: seçin **blok** çok oyunculu oyunlara önlemek için. **Yapılandırılmamış** cihazda çok oyunculu oyunlar oynamasına izin verir.
- **Derecelendirme bölgesi**: izin verilen indirmeleri için kullanmak istediğiniz derecelendirme bölgesini seçin. İçin izin verilen derecelendirmeleri seçin **filmler** ve **TV programları**.
- **Uygulamaları**: kullanıcılar indirebilir veya seçebilirsiniz uygulamalar izin verilen yaş derecelendirmesini seçin **tüm uygulamalara izin ver**.

## <a name="built-in-apps"></a>Yerleşik Uygulamalar

- **Kamera**: seçin **blok** için cihaz kameranızı erişimi engellemek için. **Yapılandırılmamış** cihazın kamerasını erişmesini sağlar.
  - **FaceTime**: **blok** FaceTime uygulamaya erişimini önlemek için. **Yapılandırılmamış** cihazda FaceTime uygulamasının erişmesine izin verir.
- **Siri**: **blok** Siri için erişimi engeller. **Yapılandırılmamış** cihazda Siri ses yardımcısının kullanımına izin verir.
  - **Cihaz kilitliyken Siri**: seçin **blok** cihaz kilitliyken Siri için erişimi engellemek için. **Yapılandırılmamış** kilitli olduğu zaman cihazda Siri ses yardımcısının kullanımına izin verir.
  - **Siri küfür filtresi (yalnızca denetimli)**: **gerektiren** Siri'nin küfürlü dil dikte etmesini veya konuşmasını engeller.
  - **(Yalnızca denetimli) internet'ten kullanıcı tarafından oluşturulan içeriğin Siri**: **blok** Siri'nin soruları yanıtlamak için Web sitelerine erişmesini engeller. **Yapılandırılmamış** Siri'nin kullanıcı tarafından oluşturulan içeriği internet'ten erişmesine izin verir.
- **Apple News (yalnızca denetimli)**: seçin **blok** Apple News uygulamasının cihazda erişimi engellemek için. **Yapılandırılmamış** Apple News uygulamasının kullanımına izin verir.
- **iBooks Mağazası (yalnızca denetimli)**: **blok** için iBooks mağazasına erişimi engeller. **Yapılandırılmamış** kullanıcıların göz atıp kitap iBooks Mağazası'ndan satın olanak tanır.
- **(Yalnızca denetimli) cihazdaki mesajlar uygulaması**: seçin **blok** kullanıcıların cihazda mesajlar uygulamasının kullanamazlar. **Yapılandırılmamış** göndermek ve metin iletileri okumak için mesajlar uygulamasının kullanımına izin verir.
- **Podcast'ler (yalnızca denetimli)**: **blok** pod yayını uygulamasının kullanarak kullanıcıları engeller. **Yapılandırılmamış** pod yayını uygulamasının kullanımına izin verir.
- **Music hizmeti (yalnızca denetimli)**: **blok** Music uygulaması Klasik moda döner ve Music hizmeti devre dışı bırakır. **Yapılandırılmamış** Apple Music uygulamasının kullanımına izin verir.
- **iTunes Radio hizmeti (yalnızca denetimli)**: **blok** kullanıcılar iTunes Radio uygulamasının kullanmasını önler. **Yapılandırılmamış** iTunes Radio uygulamasının kullanımına izin verir.
- **(Yalnızca denetimli) Find My Friends uygulama ayarlarında yapılan değişiklikler**: **blok** Find My Friends uygulama ayarlarında değişiklik önler. **Yapılandırılmamış** kullanıcının Find My Friends uygulamasının ayarlarını değiştirmesine izin verir.
- **Spotlight aramasının (yalnızca denetimli) internet'ten sonuç döndürmesine izin**: **blok** Spotlight Internet aramasının herhangi bir sonuç döndürmesini durdurur. **Yapılandırılmamış** Spotlight arama, arama sonuçları sağlamak için Internet'e bağlanmasına izin verir.
- **Engelle (yalnızca denetimli) cihaz sistem uygulamalardan kaldırılmasını**: seçme **blok** sistemi uygulamaları CİHAZDAN kaldırma özelliği devre dışı bırakır. **Yapılandırılmamış** kullanıcıların sistemi uygulamalarının kaldırılmasına olanak tanır.

## <a name="restricted-apps"></a>Kısıtlı uygulamalar

Kısıtlı uygulamalar listesinde, aşağıdaki listelerden birini yapılandırabilirsiniz:

- **Yasak uygulamalar**: cihazda yüklü istemediğiniz Intune tarafından yönetilmeyen uygulamaların listesi. Bir kullanıcı bu listeden bir uygulama yüklerse, Intune tarafından bildirim alırsınız.
- **Onaylı uygulamalar**: kullanıcıların yüklemesine izin verilen uygulamalar listesi. Uyumlu kalmak için kullanıcılar diğer uygulamaları yüklememelidir. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir. Bir kullanıcı bu listeden bir uygulama yüklerse, Intune tarafından bildirim alırsınız.

Bu listelerden uygulamaları eklemek, şunları yapabilirsiniz:

- **Ekleme** iTunes App depolamak istediğiniz uygulamanın URL'si. Örneğin, Microsoft Çalışma klasörleri uygulamasını eklemek için girin `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`.

  Bir uygulamanın URL'sini bulmak için iTunes App Store açın ve uygulamayı arayın. Örneğin, arama `Microsoft Remote Desktop` veya `Microsoft Word`. Uygulamayı seçin ve URL'yi kopyalayın.

  Ayrıca uygulamayı bulmak için iTunes kullanabilir ve ardından **bağlantıyı Kopyala** görev uygulama URL'sini alabilirsiniz.

- URL'si dahil olmak üzere uygulama ayrıntılarını içeren bir CSV dosyasını içeri aktarın. Kullanım <app url>, <app name>, <app publisher> biçimi. Veya aynı biçimdeki kısıtlı uygulama listesi içeren mevcut bir listeyi dışarı aktarın.

> [!IMPORTANT]
> Kısıtlı uygulama ayarlarını kullanan cihaz profilleri kullanıcı gruplarına atanmalıdır.

## <a name="show-or-hide-apps-supervised-only"></a>Uygulamaları gösterme veya gizleme (yalnızca denetimli)

Gösterme veya gizleme uygulamalar listesinde aşağıdaki listelerden birini iOS 9.3 veya üzeri çalıştıran denetimli cihazlarda yapılandırabilirsiniz.

- **Gizli uygulamalar**: kullanıcılardan gizlenen uygulamaların listesini girin. Kullanıcılar görüntüleyemez veya bu uygulamaları açın.
- **Görünür uygulamalar**: ve başlatabileceği uygulamaların kullanıcıların görüntüleyebileceği listesini girin. Başka hiçbir uygulama görüntülenemez veya başlatılamaz.

Bu listelerden uygulamaları eklemek, şunları yapabilirsiniz:

- **Ekleme** iTunes App depolamak istediğiniz uygulamanın URL'si. Örneğin, Microsoft Çalışma klasörleri uygulamasını eklemek için girin `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`.

  Bir uygulamanın URL'sini bulmak için iTunes App Store açın ve uygulamayı arayın. Örneğin, arama `Microsoft Remote Desktop` veya `Microsoft Word`. Uygulamayı seçin ve URL'yi kopyalayın.

  Ayrıca uygulamayı bulmak için iTunes kullanabilir ve ardından **bağlantıyı Kopyala** görev uygulama URL'sini alabilirsiniz.

- URL'si dahil olmak üzere uygulama ayrıntılarını içeren bir CSV dosyasını içeri aktarın. Kullanım <app url>, <app name>, <app publisher> biçimi. Veya aynı biçimdeki kısıtlı uygulama listesi içeren mevcut bir listeyi dışarı aktarın.

## <a name="wireless"></a>Kablosuz

- **Veri dolaşımı**: seçin **blok** hücresel ağ üzerinde veri dolaşımını önlemek için. **Yapılandırılmamış** cihaz hücresel ağ kullanırken veri dolaşımına izin verir.
- **Dolaşım sırasında genel arka planda getirme**: **blok** hücresel ağ üzerinde Dolaşım sırasında genel arka planda getirme özelliğini kullanarak engeller. **Yapılandırılmamış** cihazın bir cep telefonu şebekesinde dolaşımdayken e-posta gibi verileri getirme izin verir.
- **Sesli arama**: seçin **blok** kullanıcıların cihazda sesli arama özelliğini kullanmasını önlemek için. **Yapılandırılmamış** cihazda sesle sağlar.
- **Ses dolaşımı**: seçin **blok** ses telefonu şebekesinde dolaşımı önlemek için. **Yapılandırılmamış** ses cihaz hücresel ağ kullanırken dolaşımına izin verir.
- **Uygulama hücresel veri kullanım ayarlarında (yalnızca denetimli) yapılan değişiklikler**: seçin **blok** uygulama hücresel veri kullanımı ayarlarında yapılan değişiklikleri önlemek için. **Yapılandırılmamış** kullanıcının hangi uygulamaların hücresel veri kullanma izin denetlemesine olanak sağlar.
- **Kişisel etkin nokta**: **blok** cihazın kişisel etkin nokta kullanılmasını engeller. Bu ayar, bazı operatörler ile uyumlu olmayabilir. **Yapılandırılmamış** bu özelliği sağlar.
- **(Yalnızca denetimli) yapılandırma profilleri kullanarak yalnızca Wi-Fi ağlarına Katıl**: **gerektiren** cihaz, yalnızca Intune yapılandırma profilleri aracılığıyla kurulan Wi-Fi ağlarını kullanmaya zorlar. **Yapılandırılmamış** cihazın diğer Wi-Fi ağlarını kullanmaya izin verir.
- **Hücresel kullanım kuralları (yalnızca yönetilen uygulamalar)**: hücresel ağa bağlıyken yönetilen uygulamaların türleri kullanabileceği veri tanımlayın. Seçenekleriniz şunlardır:
  - **Hücresel veri kullanımını engelleme**: engellemek için hücresel veri kullanarak **tüm yönetilen uygulamalar** veya **belirli uygulamalar seçebilirsiniz**.
  - **Dolaşım sırasında hücresel veri kullanımını engelleme**: Dolaşım sırasında hücresel veri kullanarak Block **tüm yönetilen uygulamalar** veya **belirli uygulamalar seçebilirsiniz**.

## <a name="connected-devices"></a>Bağlı Cihazlar

- **AirDrop (yalnızca denetimli)**: **blok** Airdrop'a cihazda kullanarak engeller. **Yapılandırılmamış** yakındaki cihazlarla içerik değişimi için AirDrop özelliğinin kullanımına izin verir.
- **Apple Watch eşleştirme (yalnızca denetimli)**: **blok** bir Apple Watch ile eşleştirme engeller. **Yapılandırılmamış** cihazın bir Apple Watch ile eşleşmesine izin verir.
- **Eşleştirilmiş Apple Watch için bilek algılama**: **gerektiren** bir eşleştirilmiş Apple Watch için bilek algılama kullanmaya zorlar. Bunu değil takılmadığında gerektiğinde, Apple Watch bildirim görüntülenmez. 
- **Bluetooth değişikliği (yalnızca denetimli)**: **blok** son kullanıcının cihazda Bluetooth ayarlarını değiştirmesini engeller. **Yapılandırılmamış** bu ayarları değiştirmesine izin verir.
- **Konak bir iOS cihazının eşleştirilebildiği (yalnızca denetimli) cihazları denetlemek için eşleştirme**: **yapılandırılmadı** bir iOS cihazının eşleştirilebildiği hangi cihazların yöneticinin denetlemesi için konak eşleştirmeye izin verir. **Blok** eşlenebileceği engeller.
- **Giden AirPlay istekleri parola gerektiren**: **gerektiren** kullanıcının diğer Apple cihazlarına içerik akışı sağlamak üzere airplay'i bir eşleştirme parolası. **Yapılandırılmamış** kullanıcının bir parola girmeden AirPlay kullanarak içerik akışı sağlar.
- **Engelle (yalnızca denetimli) AirPrint**: seçin **blok** cihazda AirPrint özelliğini kullanarak önlemek için. **Yapılandırılmamış** AirPrint kullanmasına izin verir.
  - **Blok depolama AirPrint kimlik bilgileri (yalnızca denetimli) anahtarlıktaki**: **blok** kullanıcı adı ve parola cihazda Anahtarlık depolama kullanarak engeller. **Yapılandırılmamış** Anahtarlık uygulamada AirPrint kullanıcı adı ve parola depolama sağlar.
  - **(Yalnızca denetimli) için AirPrint güvenli TLS sertifika gerektiren**: **gerektiren** TLS yazdırma iletişim için güvenilen sertifikalar kullanmak için cihazın zorlar.
  - **AirPrint yazıcıları (yalnızca denetimli) iBeacon bulunmasını engelleyin**: **blok** kimlik avı ağ trafiği için kötü amaçlı AirPrint Bluetooth işaretleri engeller. **Yapılandırılmamış** AirPrint yazıcıları cihazda reklam sağlar.

## <a name="keyboard-and-dictionary"></a>Klavye ve Sözlük

- **Sözcük tanımı arama (yalnızca denetimli)**: **blok** kullanıcının bir word vurgulama ve sonra cihazdaki tanımı bakarak engeller. **Yapılandırılmamış** tanım arama özelliğini erişmesini sağlar.
- **Klavyeler (yalnızca denetimli)**: **yapılandırılmadı** tahmin eden klavyelere sözcükleri öneren kullanıcı kullanmayı isteyebileceğiniz izin verir. **Blok** bu özellik engeller.
- **Otomatik Düzeltme (yalnızca denetimli)**: **yapılandırılmadı** cihazın yanlış yazılan sözcükleri otomatik olarak düzeltmek izin verir. **Blok** otomatik düzeltme engel olur.
- **Klavye yazım denetimi (yalnızca denetimli)**: **yapılandırılmadı** yazım cihazda kullanımına izin verir. **Blok** yazım denetimcisine izin verir.
- **Klavye kısayolları (yalnızca denetimli)**: **yapılandırılmadı** cihazda klavye kısayollarını kullanarak sağlar. **Blok** klavye kısayollarını kullanarak kullanıcının durdurur.
- **Dikte (yalnızca denetimli)**: **blok** kullanıcının sesli metin girmek için giriş yapmasını durdurur. **Yapılandırılmamış** kullanıcının dikte girişini kullanmasını sağlar.

## <a name="cloud-and-storage"></a>Bulut ve Depolama

- **İcloud'a yedekle**: **yapılandırılmadı** kullanıcının cihazı İcloud'a yedeklemesine izin verir. **Blok** kullanıcının cihazı İcloud'a yedeklemeyi engeller.
- **Belge eşitleme (yalnızca denetimli) icloud**: **yapılandırılmadı** iCloud depolama alanınızda belge ve anahtar-değer eşitlemesine izin verir. **Blok** iCloud belgeleri ve verileri eşitlenmesini önler.
- **İcloud'a fotoğraf akışı eşitlemesi**: **yapılandırılmadı** etkinleştirme olanağı **My fotoğraf Stream** cihazlarında İcloud'a eşitlenmesine ve tüm kullanıcı aygıtları üzerinde fotoğraf kullanılabilir. **Blok** İcloud'a fotoğraf akışı eşitlemesi engeller.
- **Şifreli yedekleme**: **gerektiren** böylece cihaz yedeklemelerinin şifrelenmesini gerekir.
- **iCloud fotoğraf arşivi**: kümesine **blok** fotoğraflar ve videoları bulutta depolamasını için iCloud fotoğraf Arşivi'ni kullanarak devre dışı bırakmak için. İCloud fotoğraf Arşivi ' cihaza tamamen indirilmeyen tüm fotoğraflar CİHAZDAN kaldırılır. **Yapılandırılmamış** iCloud fotoğraf kitaplığının kullanımına izin verir.
- **Yönetilen uygulamaları bulutla eşitleme**: **yapılandırılmadı** Intune yöneten uygulamalarınızı kullanıcının iCloud hesabıyla veri eşitlemesine izin verir. **Blok** bu veri eşitleme İcloud'a engeller.
- **Paylaşılan fotoğraf akışı**: seçin **blok** devre dışı bırakmak için **iCloud fotoğraf paylaşma** cihazda. **Yapılandırılmamış** paylaşılan fotoğraf akışını sağlar.
- **Etkinlik devamlılığı**: **yapılandırılmadı** kullanıcıların, başka bir iOS veya macOS cihazda (Handoff) bir iOS cihazında başladığınız bir çalışmayı devam etmesini sağlar. **Blok** bu iletim engeller.
- **İCloud anahtar zinciri eşitlenmesinin engellenip**: seçin **blok** icloud Anahtarlıkta depolanan eşitleme kimlik bilgileri devre dışı bırakmak için. **Yapılandırılmamış** kullanıcıların bu kimlik bilgilerini eşitleme sağlar.
- **Blok Kurumsal kitap yedekleme**: seçin **blok** kullanıcılar Kurumsal defterlerini yedeklemesini engellemek için. **Yapılandırılmamış** bu defterlerini yedeklemesine izin verir.
- **Engelle (Notlar ve vurgular) Kurumsal kitabı meta verileri eşitleme**: **blok** eşitleme notları engeller ve kurumsal kitaplarda vurgular. **Yapılandırılmamış** eşitlemeye izin verir.

## <a name="autonomous-single-app-mode-supervised-only"></a>Otonom tek uygulama modu (yalnızca denetimli)

İOS cihazlarını belirli uygulamaları otonom tek uygulama modunda çalışacak şekilde yapılandırmak için bu ayarları kullanın. Bu modda yapılandırılır ve uygulama çalıştırıldığında cihaz kilitli. Ayrıca, bu uygulama yalnızca çalıştırabilirsiniz. Örneğin, kullanıcıların cihazda sınav olanak sağlayan bir uygulama ekleyin. Uygulama eylemleri tamamlandığında veya bu ilkeyi kaldırdığınızda cihaz normal durumuna döner.

Uygulama eklemek için şunları yapabilirsiniz:

- Girin **uygulama adı** ve **uygulama paket kimliği**seçip **Ekle**. [Yerleşik iOS uygulamaları için paket kimliği başvurusu](#bundle-id-reference-for-built-in-ios-apps) (Bu makalede) kimlikleri ile bazı uygulamaları içerir.
- **İçeri aktarma** uygulama adları ve bunların paket kimliklerinin listesini içeren bir CSV dosyası. Veya, **dışarı** uygulamaları içeren mevcut bir listesi.

## <a name="kiosk-supervised-only"></a>Bilgi noktası (yalnızca denetimli)

- **Bilgi noktası modunda çalıştırmak için uygulama**: bilgi noktası modunda çalıştırmak istediğiniz uygulamaları seçin. Seçenekleriniz şunlardır: 
  - **App Store**: bir uygulamanın iTunes uygulama mağazası URL'sini girin
  - **Yönetilen uygulama**: Intune'a eklediğiniz bir uygulama seçin
  - **Yerleşik uygulama**: girin [paket Kimliğini](#bundle-id-reference-for-built-in-ios-apps) yerleşik uygulama

- **Yardımcı dokunma**: **gerektiren** Yardımlı dokunma erişilebilirlik ayarını cihazda olabilir. Bu özellik ile kullanıcıların ekran kendileri için zor olabilecek hareketlerini yardımcı olur. **Yapılandırılmamış** değil çalıştırın veya bilgi noktası modunda bu özelliği etkinleştirin.
- **Renkleri ters çevir**: **gerektiren** görme bozukluğu olan kullanıcılara ekran değiştirebilmeniz için renkleri ters çevir erişilebilirlik ayarını. **Yapılandırılmamış** değil çalıştırın veya bilgi noktası modunda bu özelliği etkinleştirin.
- **Mono Ses**: **gerektiren** Mono Ses erişilebilirlik ayarını cihazda olabilir. **Yapılandırılmamış** değil çalıştırın veya bilgi noktası modunda bu özelliği etkinleştirin.
- **VoiceOver**: **gerektiren** VoiceOver erişilebilirlik ayarını ekranındaki metin sesli okumak için cihazda olabilir. **Yapılandırılmamış** değil çalıştırın veya bilgi noktası modunda bu özelliği etkinleştirin.
- **Yakınlaştırma**: **gerektiren** yakınlaştırma ayarını olması cihazda dokunmatik ekranda yakınlaştırmak için kullanıcıların izin vermek için. **Yapılandırılmamış** değil çalıştırın veya bilgi noktası modunda bu özelliği etkinleştirin.
- **Otomatik kilit**: **izin** cihazda otomatik kilitlemeyi. **Yapılandırılmamış** bu özelliği devre dışı bırakır.
- **Açma/kapama**: **izin** cihazda ses düğmesi (sessiz) geçin. **Yapılandırılmamış** bu özelliği devre dışı bırakır.
- **Ekran döndürme**: **izin** kullanıcı cihazı döndürdüğünde ekran yönünü değiştirmeyi. **Yapılandırılmamış** bu özelliği devre dışı bırakır.
- **Ekran Uyku düğmesi**: seçin **izin** uykudan Uyanma düğmesini cihazda devre dışı bırakmak için. **Yapılandırılmamış** bu özellik sağlar.
- **Touch**: **blok** cihazda dokunmatik ekranı devre dışı bırakır. **Yapılandırılmamış** dokunmatik ekranı kullanmasına izin verir.
- **Ses düzeyi düğmelerine**: **izin** cihazdaki ses düğmelerini kullanarak. **Yapılandırılmamış** ses düğmelerini devre dışı bırakır.
- **Yardımlı dokunma denetimi**: **izin** kullanıcıların yardımcı dokunma işlevini kullanın. **Yapılandırılmamış** bu özelliği devre dışı bırakır.
- **Renkleri tersine çevirme denetimi**: **izin** renkleri ayarlamalar kullanıcıların renkleri ters çevirme işlevini ayarlamasına izin vermek için. **Yapılandırılmamış** bu özelliği devre dışı bırakır.
- **Seçilen metinde konuşma**: **izin** seçimi seslendir erişilebilirlik ayarını cihazda olabilir. Bu özellik, sesli kullanıcının seçtiği metni okur. **Yapılandırılmamış** bu özelliği devre dışı bırakır.
- **VoiceOver denetimi**: **izin** voiceover değişiklikleri kullanıcıların ne kadar hızlı ekrandaki metin yüksek sesle okumak gibi VoiceOver işlevini güncelleştirin. **Yapılandırılmamış** voiceover değişiklik önler.
- **Yakınlaştırma Denetimi**: **izin** kullanıcı tarafından değişiklikler yakınlaştırma. **Yapılandırılmamış** yakınlaştırma değişiklik önler.

> [!NOTE]
> Bir iOS cihazını bilgi noktası modunda yapılandırabilmek için, önce Apple Configurator aracını veya Apple Cihaz Kayıt Programı’nı kullanarak cihazı denetimli moda almanız gerekir. Apple Configurator aracını kullanarak Apple'nın kılavuzuna bakın.
> Girdiğiniz iOS uygulaması siz profil atadıktan sonra yüklü değilse, cihaz yeniden başlatılana kadar cihaz bilgi noktası modu enter değil.

## <a name="bundle-id-reference-for-built-in-ios-apps"></a>Yerleşik iOS uygulamaları için Paket Kimliği başvurusu

Bu liste, bazı yaygın yerleşik iOS uygulamalarının paket kimliğini gösterir. Diğer uygulamaların paket kimliğini bulmak için yazılım satıcınıza başvurun.

| Paket Kimliği                   | Uygulama Adı     | Yayımcı |
|-----------------------------|--------------|-----------|
| com.apple.AppStore          | Uygulama Mağazası    | Apple     |
| com.apple.calculator        | Hesap Makinesi   | Apple     |
| com.apple.mobilecal         | Takvim     | Apple     |
| com.apple.camera            | Kamera       | Apple     |
| com.apple.mobiletimer       | Saat        | Apple     |
| com.apple.compass           | Pusula      | Apple     |
| com.apple.MobileAddressBook | Kişiler     | Apple     |
| com.apple.facetime          | FaceTime     | Apple     |
| com.apple.mobileme.fmf1     | Arkadaşları Bul | Apple     |
| com.apple.mobileme.fmip1    | iPhone’u Bul  | Apple     |
| com.apple.gamecenter        | Oyun Merkezi  | Apple     |
| com.apple.mobilegarageband  | GarageBand   | Apple     |
| com.apple.Health            | Sistem Durumu       | Apple     |
| com.apple.iBooks            | iBooks       | Apple     |
| com.apple.MobileStore       | iTunes Store | Apple     |
| com.apple.itunesu           | iTunes U     | Apple     |
| com.apple.Keynote           | Keynote      | Apple     |
| com.apple.mobilemail        | Mail         | Apple     |
| com.apple.Maps              | Harita         | Apple     |
| com.apple.MobileSMS         | İletiler     | Apple     |
| com.apple.Music             | Müzik        | Apple     |
| com.apple.news              | News         | Apple     |
| com.apple.mobilenotes       | Notlar        | Apple     |
| com.apple.Numbers           | Sayılar      | Apple     |
| com.apple.Pages             | Pages        | Apple     |
| com.apple.Photo-Booth       | Photo Booth  | Apple     |
| com.apple.mobileslideshow   | Fotoğraflar       | Apple     |
| com.apple.podcasts          | Podcast’ler     | Apple     |
| com.apple.reminders         | Anımsatıcılar    | Apple     |
| com.apple.MobileSafari      | Safari       | Apple     |
| com.apple.Preferences       | Ayarlar     | Apple     |
| com.apple.stocks            | Borsa       | Apple     |
| com.apple.tips              | İpuçları         | Apple     |
| com.apple.videos            | Videolar       | Apple     |
| com.apple.VoiceMemos        | Sesli Notlar   | Apple     |
| com.apple.Passbook          | Wallet       | Apple     |
| com.apple.Bridge            | Watch        | Apple     |
| com.apple.weather           | Hava Durumu      | Apple     |

## <a name="safari"></a>Safari

- **Safari (yalnızca denetimli)**: **blok** cihazda Safari tarayıcısı kullanılarak. **Yapılandırılmamış** Safari tarayıcısı kullanmasına olanak tanır.
- **Otomatik doldurma**: **blok** cihazda Safari otomatik doldurma özelliğini devre dışı bırakır. **Yapılandırılmamış** kullanıcıların web tarayıcısında otomatik tamamlama ayarlarını değiştirmesine olanak tanır.
- **Tanımlama bilgilerini**: tanımlama bilgilerinin cihazda nasıl işleneceğini seçin. Seçenekleriniz şunlardır:
  - İzin Ver
  - Tüm tanımlama bilgilerini engelle
  - Ziyaret edilen web sitelerinin tanımlama bilgilerine izin ver
  - Geçerli web sitesinden tanımlama bilgilerine izin ver
- **JavaScript**: **blok** tarayıcıda Java betiğinin cihazda çalışmasını engeller. **Yapılandırılmamış** Java betiklerini sağlar.
- **Dolandırıcılık uyarıları**: **gerektiren** sahtekarlık uyarılarına cihazdaki web tarayıcısının gösterilecek. **Yapılandırılmamış** bu özelliği devre dışı bırakır.
- **Açılır pencereler**: **blok** web tarayıcısında açılır pencere engelleyicisini devre dışı bırakmak için. **Yapılandırılmamış** açılır pencere engelleyicisine izin verir.

## <a name="domains"></a>Domains

### <a name="unmarked-email-domains"></a>İşaretsiz e-posta etki alanları

İçinde **e-posta etki alanı URL'si**, listeye bir veya daha fazla URL ekleyin. Son kullanıcılar, girdiğiniz etki alanı dışındaki bir etki alanından e-posta aldığınızda, e-posta işaretlenmiş iOS Mail uygulamasında güvenilmeyen olarak.

### <a name="managed-web-domains"></a>Yönetilen web etki alanları

İçinde **Web etki alanı URL'si**, listeye bir veya daha fazla URL ekleyin. Belgeler, girdiğiniz etki alanlarından indirildiğinde bunlar yönetilen kabul. Bu ayar yalnızca Safari tarayıcısı kullanılarak indirilen belgeler için geçerlidir.

### <a name="safari-password-autofill-domains"></a>Safari parola otomatik doldurma etki alanları

İçinde **etki alanı URL'si**, listeye bir veya daha fazla URL ekleyin. Kullanıcılar yalnızca bu listedeki URL’lerdeki parolaları kaydedebilir. Bu ayar yalnızca Safari tarayıcısı ve denetimli moddaki iOS 9.3 ve üzeri cihazlar için geçerlidir. Herhangi bir URL belirtmezseniz, parolalar tüm web sitelerinden kaydedilebilir.

## <a name="next-steps"></a>Sonraki adımlar

[Profil atama](device-profile-assign.md) ve [atamanın durumunu izlemenize](device-profile-monitor.md) durumu.
