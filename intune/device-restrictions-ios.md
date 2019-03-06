---
title: iOS cihaz ayarları Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
description: İOS cihazları ayarı parola gereksinimleri dahil olmak üzere kısıtlamanıza, kilit ekranı kontrol, yerleşik uygulamaları kullanın, kısıtlanmış veya onaylı uygulamalar ekleme, bluetooth cihazların işlemek, yeniden işlenmek üzere buluta bağlayın ve depolama ayarları oluşturabilir veya yapılandırabilirsiniz veya ekleyin, bilgi noktası modu etkinleştirmek için etki alanları ve kullanıcıların Microsoft Intune Safari web tarayıcısı ile nasıl etkileşim denetimi ekleyin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/06/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 47d309fceb66b616e224ae102ba1f9fd7f48329b
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57394725"
---
# <a name="ios-device-settings-to-allow-or-restrict-features-using-intune"></a>izin vermek veya Intune kullanarak özellikleri kısıtlamak için iOS cihaz ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makalede, listeler ve iOS cihazlarında denetleyebileceğiniz farklı ayarlar açıklanır. Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, izin veya özellikleri devre dışı bırakabilir, parola kuralları, izin veya belirli uygulamalar ve daha fazlasını sınırlamak için bu ayarları kullanın.

Bu ayarlar, ıntune'da cihaz yapılandırma profili eklenir ve ardından atanan veya iOS cihazlarınıza dağıtılmış.

## <a name="before-you-begin"></a>Başlamadan önce

[Cihaz kısıtlamalarını yapılandırma profili oluşturma](device-restrictions-configure.md#create-the-profile).

## <a name="general"></a>Genel

- **Kullanım verilerini paylaş**: Seçin **blok** cihazın Apple'a tanılama ve kullanım verileri göndermesini önlemek için. **Yapılandırılmamış** (varsayılan) bu veriler gönderilmesini sağlar.
  - **Tanılama gönderimi ayarlarının değiştirilmesi (yalnızca denetimli)**: **Blok** kullanıcının tanılama gönderiminde ve uygulama analizi ayarlarında değiştirmesini engeller **tanılama ve kullanım** (cihaz ayarları). **Yapılandırılmamış** (varsayılan), bu cihaz ayarlarını değiştirmesine izin verir.

    Bu özellik şu platformlarda geçerlidir:  
    - iOS 9.3.2 ve üstü

- **Ekran Yakalama**: Seçin **blok** ekran görüntüleri veya ekran önlemek için cihazda yakalar. **Yapılandırılmamış** (varsayılan), kullanıcının ekran içeriğini resim olarak yakalamasına olanak sağlar.
  - **(Yalnızca denetimli) Classroom uygulamasıyla ekranı uzaktan izlemesine**: Seçin **blok** Classroom uygulamasının ekranı cihazda uzaktan görüntülemesini engellemek için. **Yapılandırılmamış** (varsayılan) ekranını görüntülemek Apple Classroom uygulamasını sağlar.

    Bu özellik şu platformlarda geçerlidir:  
    - iOS 9.3 ve üzeri

  - **İstem olmadan ekranı izleme (yalnızca denetimli) tarafından**: Varsa kümesine **izin**, Öğretmenler sessizce öğrencilerinin bilgisi olmadan Classroom uygulamasını kullanarak, öğrencilerin iOS cihazlarının ekranını inceleyin. Classroom uygulaması kullanılarak otomatik olarak bir sınıfa kaydolan Öğrenci cihazları izni o kursun öğretmenine. **Yapılandırılmamış** (varsayılan), bu özellik engeller.
- **Güvenilmeyen TLS sertifikaları**: Seçin **blok** cihazda güvenilmeyen Aktarım Katmanı Güvenliği (TLS) sertifikalarını önlemek için. **Yapılandırılmamış** (varsayılan), TLS sertifikalarına izin verir.
- **Kurumsal uygulama güveni**: Seçin **blok** kaldırmak için **Kurumsal geliştiriciye güven** ayarları düğmesi > Genel > profiller ve cihazda cihaz yönetimi. **Yapılandırılmamış** (varsayılan), kullanıcının uygulama Mağazası'ndan indirilen olmayan uygulamalara güvenmeyi seçmesine olanak sağlar.
- **Hesap değişikliği (yalnızca denetimli)**: Ayarlandığında **blok**, kullanıcının iOS ayarları uygulamasından cihaza özgü ayarları güncelleştirilemiyor. Örneğin, kullanıcı olamaz yeni cihaz hesapları oluşturma veya kullanıcı adı ve parola ile değiştirin. **Yapılandırılmamış** (varsayılan), bu ayarları değiştirmek kullanıcıların sağlar.

  Bu özellik, posta, kişiler, takvim, Twitter ve daha fazla gibi iOS ayarları uygulamasından erişilebilen ayarlar için de geçerlidir. Bu özellik, Microsoft Outlook uygulaması gibi iOS ayarları uygulamasından yapılandırılabilir olmayan hesap ayarları ile uygulamalar için geçerli değildir.
- **Ekran zaman (yalnızca denetimli)**: Seçin **blok** kullanıcıların kendi kısıtlamaları (cihaz ayarları) ekran zamanında ayarlama özelliğinden önlemek için. **Yapılandırılmamış** cihazda cihaz kısıtlamalarını (ebeveyn denetimleri veya içerik ve gizlilik kısıtlamaları gibi) yapılandırma kullanıcıya izin verir.

  Bu ayar adlandırıldı **cihaz ayarlarında kısıtlamaları etkinleştirme**. Bu değişikliğin etkisini:  
  
  - iOS 11.4.1 ve önceki sürümleri: **Blok** son kullanıcıların cihaz ayarlarında kısıtlamaları kendi ayarından engeller. Bu aynı şeydir; ve son kullanıcılar için herhangi bir değişiklik yok.
  - iOS 12.0 ve daha sonra: **Blok** son kullanıcılar kendi önlenmiş **ekran zaman** cihaz ayarlarında (Ayarlar > Genel > Ekran zaman), içerik ve gizlilik kısıtlamaları da dahil olmak üzere. İOS 12.0 yükseltilmiş cihazları görmezsiniz Cihaz ayarlarında kısıtlamaları sekmesinde artık (Ayarlar > Genel > cihaz Yönetimi > Yönetim profili > kısıtlamaları). Bu ayarlar **ekran zaman**.
  
- **Silme tüm içerik ve ayarlar seçeneğini (yalnızca denetimli) cihazda**: Seçin **blok** nedenle kullanıcılar silme tüm içerik ve ayarları (yalnızca denetimli) cihaz seçeneğini kullanamazsınız. **Yapılandırılmamış** (varsayılan) bu ayarlara erişimi kullanıcılar verir.
- **Cihaz adının değiştirilmesi (yalnızca denetimli)**: Seçin **blok** cihaz adı değiştirilemez. **Yapılandırılmamış** (varsayılan), kullanıcının cihazın adını değiştirmesine izin verir.
- **Bildirim ayarlarının değiştirilmesi (yalnızca denetimli)**: Seçin **blok** bildirim ayarları değiştirilemez. **Yapılandırılmamış** (varsayılan), kullanıcının cihazın bildirim ayarlarını değiştirmesine izin verir.
- **Duvar kağıdı değişikliği (yalnızca denetimli)**: **Blok** duvar kağıdı değişmesini önler. **Yapılandırılmamış** (varsayılan), kullanıcının cihazın duvar kağıdını değiştirmesine izin verir.
- **Kurumsal uygulama güven ayarlarının değiştirilmesi (yalnızca denetimli)**: **Blok** kullanıcının denetimli cihazlarda Kurumsal uygulama güven ayarlarını değiştirmesini engeller. **Yapılandırılmamış** (varsayılan), uygulama Mağazası'ndan indirilen olmayan uygulamaları güvenmesini sağlar.
- **Yapılandırma profilindeki değişiklikler (yalnızca denetimli)**: **Blok** cihaz yapılandırma profili değişiklikleri engeller. **Yapılandırılmamış** (varsayılan), kullanıcının yapılandırma profilleri yüklemesine izin verir.
- **Etkinleştirme kilidi (yalnızca denetimli)**: Seçin **izin** etkinleştirme Kilidi'ni etkinleştirmek için iOS cihazlarının denetimli. Etkinleştirme kilidi, bir kaybolan veya çalınan cihazın yeniden etkinleştirilmesini zorlaştırır.
- **Engelle (yalnızca denetimli) uygulama kaldırma**: Seçin **blok** kullanıcılar uygulamaları kaldırmasını önlemek için. **Yapılandırılmamış** (varsayılan), kullanıcıların CİHAZDAN uygulamaları kaldırmak sağlar.
- **Blokları USB kısıtlı modu (yalnızca denetimli)**: Seçin **blok** denetimli cihazlarda USB kısıtlı modu devre dışı bırakmak için. USB kısıtlı modu için bir saatten fazla kilitli olan bir cihaz ile veri değişimi gelen USB Donatılar engeller. **Yapılandırılmamış** (varsayılan), USB kısıtlı modda izin verir.
- **Otomatik tarih ve saat (yalnızca denetimli) zorla**: **Gerekli** zorlar denetimli cihazların tarih ve saat otomatik olarak ayarlanır. Cihaz cep telefonu bağlantılarına sahiptir veya konum Hizmetleri ile Wi-Fi etkin olduğundan cihazın saat dilimini güncelleştirilir.
- **İstek bırakın (yalnızca denetimli) boyunca sınıfta kurs izni Öğrenciler gerektiren**: **Gerekli** kursu bırakmak Öğretmen Classroom uygulamadan izin istemek kullanarak bir yönetilmeyen kursta kayıtlı öğrencilerin zorlar. **Yapılandırılmamış** (varsayılan), izin istemek için Öğrenci zorla değil.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11,3 ve üzeri

- **Bir uygulamaya kilitleyip (yalnızca denetimli) sormadan cihazı kilitlemek sınıf izin**: **Etkinleştirme** uygulamaları kilitlemek veya Öğrenci sormadan Classroom uygulamasını kullanarak cihazı kilitlemek Öğretmen sağlar. Erişim Öğretmen belirtilen uygulamaların yalnızca uygulamaları anlamına gelir kilitleme cihaz kullanabilirsiniz. **Yapılandırılmamış** (varsayılan), uygulamaları veya Öğrenci sormadan Classroom uygulamasını kullanarak cihazlarını kilitlemelerini Öğretmenler engeller. 

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11.0 ve sonraki

- **(Yalnızca denetimli) sormadan Classroom sınıfları otomatik olarak birleştirme**: **Etkinleştirme** Classroom uygulamasında Öğretmen sormadan bir sınıfı katılmak öğrencilerin otomatik olarak sağlar. **Yapılandırılmamış** (varsayılan), Öğretmen Classroom uygulamasında bir sınıfı katılmak öğrencilerin istediğiniz ister.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11.0 ve sonraki

- **Havadan PKI güncelleştirmelere izin ver**: **İzin** , kullanıcıların cihazlarını bir bilgisayara bağlanmadan yazılım güncelleştirmeleri almasına olanak sağlar.
- **İzleme sınırı ad**: Seçin **sınırı** cihaz reklam tanımlayıcısı devre dışı bırakmak için. **Yapılandırılmamış** (varsayılan) etkin tutar.
- **(Yalnızca denetimli) blok VPN oluşturma**: **Blok** kullanıcıların VPN yapılandırma ayarlarını oluşturmasını engeller. **Yapılandırılmamış** (varsayılan), kullanıcıların cihazda VPN oluşturan olanak tanır.
- **(Yalnızca denetimli) Esım ayarlarını değiştirme**: **Blok** kullanıcıların cihazda Esım için hücresel planı ekleyerek veya çıkararak engeller. **Yapılandırılmamış** (varsayılan), bu ayarları değiştirmek kullanıcıların sağlar.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 12,1 ve üzeri

- **(Yalnızca denetimli) yazılım güncelleştirmelerinin erteleneceği**: Ayarlandığında **yapılandırılmadı** (varsayılan), yazılım güncelleştirmeleri gösterilir cihazda gibi Apple onları serbest bırakır. Bir iOS güncelleştirme Apple tarafından belirli bir tarihte yayımlanan, örneğin, daha sonra bu güncelleştirmeyi doğal olarak yayın tarihindeki cihazda gösterilir.

  **Etkinleştirme** 0-90 güne ait cihazlarda yazılım güncelleştirmeleri gösterilirken gecikme sağlar. Bu ayar, güncelleştirmeler veya yüklü olmayan denetlemez. 

  - **Yazılım güncelleştirmelerini görünürlüğünü gecikme**: 0-90 gün arasında bir değer girin. Gecikme süresi dolduğunda kullanıcılar gecikme tetiklendiğinde erken kullanılabilir işletim sistemi sürümüne güncelleştirmek için bildirim alın.

    Örneğin, iOS 12.a edinilebilir **1 Ocak**, ve **gecikme görünürlük** ayarlanır **5 gün**, ardından iOS 12.a son kullanıcı cihazlarında kullanılabilir bir güncelleştirme olarak göremiyorsanız. Üzerinde **altıncı gün** sürümünden güncelleştirmesi kullanıma sunuldu ve son kullanıcılar da yükleyebilirsiniz.

    Bu ayar için geçerlidir:  
    - iOS 11,3 ve üzeri

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
> Apple, belirli ayarları yalnızca denetimli 2019 içinde taşımak onayladı. Bu ayarları yalnızca denetimli geçirmek Apple için beklemek yerine kullanırken bu göz önünde bulundurarak öneririz:
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

## <a name="password"></a>istemcisiyle yönetilen bir cihaz için)

- **Parola**: **Gerekli** son kullanıcının cihaza erişmek için bir parola girin. **Yapılandırılmamış** kullanıcıları parola girmeye gerek kalmadan cihazınıza erişim hakkı verir.
  - **Basit parolalar**: Seçin **blok** daha karmaşık bir parola gerektirme. **Yapılandırılmamış** gibi basit parolalara izin verir `0000` ve `1234`.
  - **Gerekli parola türü**: Kuruluşunuzda gerekli parola türünü seçin. Seçenekleriniz şunlardır:
    - **Cihaz varsayılanı**
    - **Sayısal**
    - **Alfasayısal**
  - **Paroladaki alfasayısal olmayan karakter sayısı**: Sembol karakterlerinin sayısını girin `#` veya `@`, eklenmesi gereken parola.
  - **Minimum parola uzunluğu**: (4-14 karakter arasında) bir kullanıcının girmesi alt sınırını girin.
  - **Cihaz silinmeden önceki oturum açma hatası sayısı**: (1-11 arasında) cihaz temizlenmeden önce izin başarısız oturum açma işlemlerinin sayısını girin.
  - **Parola istenmeden önce ekran kilitlendikten sonra en fazla dakika**<sup>1</sup>: Kullanıcı parolasını yeniden girmeden önce cihazın ne kadar süreyle boşta kalır girin. Girdiğiniz zaman ne şu anda cihazda ayarlı olan süreden uzunsa cihaz girdiğiniz zaman yok sayar. İOS 8.0 ve daha yeni cihazlarda desteklenir.
  - **Ekran kilitlenmeden işlem yapılmayan dakika**<sup>1</sup>: Ekran kilitlenmeden kadar cihazda izin verilen işlem yapılmayan dakika sayısı girin. Girdiğiniz zaman ne şu anda cihazda ayarlı olan süreden uzunsa cihaz girdiğiniz zaman yok sayar.
  - **Parola süresinin sonu (gün)**: Cihaz parolasının değiştirilmesi gerekmeden önce geçen gün sayısını girin.
  - **Önceki parolaların yeniden kullanılmasını engelle**: Eski bir parola yeniden kullanılana kadar kullanılması gereken yeni parola sayısını girin.
  - **Parmak iziyle kilit açma**: Seçin **blok** cihazın kilidini açmak için parmak izi'ni kullanarak önlemek için. **Yapılandırılmamış** parmak izi kullanarak cihaz kilidini açmak kullanıcının sağlar.
- **Geçiş kodu değişikliği (yalnızca denetimli)**: Seçin **blok** eklenen veya kaldırılan değiştirilmesini geçiş kodunu durdurmak için. Bu özellik engellendikten sonra geçiş kodu kısıtlamalarına yapılan denetimli cihazlarda dikkate alınmaz. **Yapılandırılmamış** (varsayılan) eklenmesine, değiştirilmesine veya kaldırılması geçiş kodlarını sağlar.

  - **Parmak izi değişikliği (yalnızca denetimli)**: **Blok** değiştirme, ekleme veya kaldırma Touchıd parmak izlerini kullanıcının durdurur. **Yapılandırılmamış** (varsayılan) cihazda Touchıd parmak izlerini kullanıcı güncelleştirme sağlar.

- **Blok parola otomatik doldurma (yalnızca denetimli)**: Seçin **blok** İos'ta parola otomatik doldurma özelliğinin kullanılmasını önlemek için. Seçme **blok** aynı zamanda şunları yapar:

  - Kullanıcılar, Safari veya herhangi bir uygulama kaydedilmiş bir parola kullanmayı sorulmaz.
  - Otomatik güçlü parolalar devre dışıdır ve kullanıcıların güçlü parolalar önerilen değildir.

  **Yapılandırılmamış** (varsayılan), bu özellikleri sağlar.

- **(Yalnızca denetimli) parola yakınlık isteklerini engellemek**: Seçin **blok** cihazın yakın cihazlardan parola istemeyen şekilde. **Yapılandırılmamış** (varsayılan) Bu parola istekleri sağlar.
- **Engelle (yalnızca denetimli) parola paylaşımı**: **Blok** engeller parolaları Airdrop'a kullanarak cihazlar arasında paylaşma. **Yapılandırılmamış** (varsayılan), paylaşılan parola sağlar.
- **Parola veya kredi kartı bilgileri (yalnızca denetimli) otomatik doldurma için Touch ID veya Face ID kimlik doğrulaması gerektiren**: Ayarlandığında **gerektiren**, kullanıcıların kimlik doğrulaması yapması Touchıd veya Faceıd önce parolaları kullanmanızı veya kredi kartı bilgileri, Safari ve diğer uygulamalarda doldurulmuş otomatik olabilir. **Yapılandırılmamış** (varsayılan), kullanıcıların bu özelliği cihaz ayarlarını denetlemek sağlar.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11.0 ve sonraki

<sup>1</sup>yapılandırdığınızda **ekran kilitlenmeden, işlem yapılmayan en fazla dakika** ve **dakika ekran kilitlendikten sonra parola istenmeden önce** ayarlarını sırayla uygulayarak. Örneğin, her iki ayarın değeri ayarlarsanız **5** dakika, beş dakika sonra otomatik olarak ekran kapatır ve cihaz kilitli bir ek sonra beş dakika. Ancak, kullanıcı ekranı el ile kapatırsa ikinci ayar hemen uygulanır. Aynı örnekte, kullanıcı ekranı kapattıktan dakikanın sonunda beş dakika sonra cihazı kilitler.

## <a name="locked-screen-experience"></a>Kilit Ekranı Deneyimi

- **Cihaz kilitliyken denetim merkezi erişimi**: Seçin **blok** cihaz kilitliyken denetim merkezi uygulamasına erişimi engellemek için. **Yapılandırılmamış** kullanıcıların cihaz kilitliyken denetim merkezi uygulamasına erişmesine izin verir.
- **Cihaz kilitliyken bildirimler**: **Blok** cihaz kilitliyken bildirimler için erişimi engeller. **Yapılandırılmamış** cihazın kilidini açmadan bildirimler erişime izin verir.
- **Cihaz kilitliyken bildirimler Cüzdan**: **Blok** cihaz kilitli olduğunda Cüzdan uygulamaya erişimi engeller. **Yapılandırılmamış** cihaz kilitliyken kullanıcının Cüzdan uygulamasına erişmesine izin verir.
- **Cihaz kilitliyken bugün görünümü**: **Blok** cihaz kilitliyken Bugün görünümüne erişimi engeller. **Yapılandırılmamış** cihaz kilitliyken kullanıcının Bugün görünümünü görmesine izin verir.

## <a name="app-store-doc-viewing-gaming"></a>Uygulama Mağazası, Belge Görüntüleme, Oyun

- **App Store'da**: **Blok** denetimli cihazlarda uygulama mağazasına erişimi engeller. **Yapılandırılmamış** erişim sağlar.
  - **Uygulamaları App Store (yalnızca denetimli) yükleme**: Seçin **blok** için cihaz giriş ekranından app store'u engelleyebilir. Son kullanıcılar, uygulamaları yüklemek için iTunes’u veya Apple Configurator aracını kullanmaya devam edebilir. **Yapılandırılmamış** giriş ekranına app Store'dan sağlar.
  - **Otomatik uygulama indirme (yalnızca denetimli)**: Seçin **blok** diğer cihazlarda satın alınan uygulamaların otomatik yüklenmesini engellemek için. Bu, mevcut uygulamaların güncelleştirilmesini etkilemez. **Yapılandırılmamış** cihaza yüklemek için diğer iOS cihazlarda satın alınan uygulamalar sağlar.
- **Uygulama mağazasına erişim için parola**: **Gerekli** kullanıcı kullanıcının uygulama mağazasını ziyaret etmeden önce parola girmelerini isteyin. **Yapılandırılmamış** parola girmeden app Store'a erişim sağlar.
- **Uygulama içi satın almalar**: Seçin **blok** Mağaza'dan uygulama içi Satınalmalar önlemek için. **Yapılandırılmamış** çalışan bir uygulama içinde depolama satın alımlarına izin verir.
- **Müstehcen iTunes müziği, podcast'i veya haber içeriği (yalnızca denetimli)**: Seçin **blok** müstehcen iTunes müziği, podcast'i veya haber içeriği önlemek için. **Yapılandırılmamış** cihazın mağazadaki yetişkinlere yönelik olarak derecelendirilmiş içeriğe erişmesine izin verir.
- **İBook mağazasından 'Erotik'olarak işaretlenmiş içerik indirme**: Seçin **blok** durakları kullanıcıların iBook mağazasından erotik olarak etiketlenmiş medya yüklenmesini önlemek için. **Yapılandırılmamış** kullanıcının "Erotik" kategorisindeki kitapları indirmesine izin verir.
- **Yönetilmeyen uygulamalarda Kurumsal belgeleri görüntüleme**: **Blok** yönetilmeyen uygulamalarda Kurumsal olmayan belgeleri görüntüleme engeller. **Yapılandırılmamış** Kurumsal belgelerin tüm uygulamalarda görüntülenmesine izin verir. Örneğin, kullanıcıların OneDrive uygulamasından Dropbox'a dosya kaydetmesini gelen engellemek istiyorsunuz. Bu ayarın olarak **blok**. Cihaz İlkesi (örneğin, bir yeniden başlatma sonrasında) aldıktan sonra artık sağlayan kaydediliyor.
  - **Yönetilen uygulamaların kişiler yazma yönetilmeyen kişiler hesaplarına izin ver**: Ayarlandığında **izin**, kullanıcılar ekleyebilir veya iş ve kurumsal kişiler, cihazda yerleşik kişiler uygulamasına dahil olmak üzere herhangi bir kişinin Outlook kişi bilgilerini eşitlemek. Ayarlandığında **yapılandırılmadı**, kullanıcılar, cihazda yerleşik kişiler uygulamasına Outlook kişilerini eklenemiyor.
  
    Bu ayarı kullanmak için ayarlanmış **yönetilmeyen uygulamalarda Kurumsal belgeleri görüntüleme** ayarını **blok**.
  
- **Kurumsal olmayan belgeleri Kurumsal uygulamalarda görüntüleme**: **Blok** Kurumsal olmayan belgeleri Kurumsal uygulamalarda görüntüleme engeller. **Yapılandırılmamış** tüm belgelerin şirketin yönetilen uygulamalarında görüntülenmesine izin verir.
  - **Yönetilmeyen uygulamalarda yönetilen kişiler hesaplarından okumaya izin ver**: Ayarlandığında **izin**, kullanıcıların herhangi bir kişinin iContacts uygulama kişi bilgilerini Outlook'a ekleyebilirsiniz. **Yapılandırılmamış** okunurken de dahil olmak üzere kaldırma çoğaltmaları, cihazda yerleşik kişiler uygulamasından engeller.
  
    Bu ayarı kullanmak için ayarlanmış **Kurumsal olmayan belgeleri Kurumsal uygulamalarda görüntüleme** ayarını **blok**.
  
- **Airdrop'u yönetilmeyen hedef olarak değerlendir**: **Gerekli** Airdrop'u yönetilmeyen bir bırakma hedefi olarak kabul edilmesi için zorlar. Bu, yönetilen uygulamaların Airdrop kullanarak verileri göndermesini durdurur. 
- **(Yalnızca denetimli) Game Center arkadaşlarını eklemeye**: **Blok** Game Center arkadaşlarını eklemeye gelen kullanıcıların engeller. **Yapılandırılmamış** Game Center'da arkadaş eklemesine izin verir.
- **Game Center (yalnızca denetimli)**: **Blok** Game Center uygulamasının kullanımını. **Yapılandırılmamış** cihazda Game Center uygulamasının kullanımına izin verir.
- **Çok oyunculu oyunlar (yalnızca denetimli)**: Seçin **blok** çok oyunculu oyunlara önlemek için. **Yapılandırılmamış** cihazda çok oyunculu oyunlar oynamasına izin verir.
- **Derecelendirme bölgesi**: İzin verilen indirmeleri için kullanmak istediğiniz derecelendirme bölgesini seçin. İçin izin verilen derecelendirmeleri seçin **filmler** ve **TV programları**.
- **Uygulamaları**: Kullanıcılar indirebilir veya seçebilirsiniz uygulamalar izin verilen yaş derecelendirmesini seçin **tüm uygulamalara izin ver**.

## <a name="built-in-apps"></a>Yerleşik Uygulamalar

- **Kamera**: Seçin **blok** için cihaz kameranızı erişimi engellemek için. **Yapılandırılmamış** cihazın kamerasını erişmesini sağlar.
  - **FaceTime**: **Blok** FaceTime uygulamaya erişimini önlemek için. **Yapılandırılmamış** cihazda FaceTime uygulamasının erişmesine izin verir.
- **Siri**: **Blok** Siri için erişimi engeller. **Yapılandırılmamış** cihazda Siri ses yardımcısının kullanımına izin verir.
  - **Cihaz kilitliyken Siri**: Seçin **blok** cihaz kilitliyken Siri için erişimi engellemek için. **Yapılandırılmamış** kilitli olduğu zaman cihazda Siri ses yardımcısının kullanımına izin verir.
  - **Siri küfür filtresi (yalnızca denetimli)**: **Gerekli** Siri'nin küfürlü dil dikte etmesini veya konuşmasını engeller.
  - **(Yalnızca denetimli) internet'ten kullanıcı tarafından oluşturulan içeriğin Siri**: **Blok** Siri'nin soruları yanıtlamak için Web sitelerine erişmesini engeller. **Yapılandırılmamış** Siri'nin kullanıcı tarafından oluşturulan içeriği internet'ten erişmesine izin verir.
- **Apple News (yalnızca denetimli)**: Seçin **blok** Apple News uygulamasının cihazda erişimi engellemek için. **Yapılandırılmamış** Apple News uygulamasının kullanımına izin verir.
- **iBooks Mağazası (yalnızca denetimli)**: **Blok** için iBooks mağazasına erişimi engeller. **Yapılandırılmamış** kullanıcıların göz atıp kitap iBooks Mağazası'ndan satın olanak tanır.
- **(Yalnızca denetimli) cihazdaki mesajlar uygulaması**: Seçin **blok** kullanıcıların cihazda mesajlar uygulamasının kullanamazlar. **Yapılandırılmamış** göndermek ve metin iletileri okumak için mesajlar uygulamasının kullanımına izin verir.
- **Podcast'ler (yalnızca denetimli)**: **Blok** pod yayını uygulamasının kullanarak kullanıcıları engeller. **Yapılandırılmamış** pod yayını uygulamasının kullanımına izin verir.
- **Music hizmeti (yalnızca denetimli)**: **Blok** Music uygulaması Klasik moda döner ve Music hizmeti devre dışı bırakır. **Yapılandırılmamış** Apple Music uygulamasının kullanımına izin verir.
- **iTunes Radio hizmeti (yalnızca denetimli)**: **Blok** kullanıcılar iTunes Radio uygulamasının kullanmasını önler. **Yapılandırılmamış** iTunes Radio uygulamasının kullanımına izin verir.
- **(Yalnızca denetimli) Find My Friends uygulama ayarlarında yapılan değişiklikler**: **Blok** Find My Friends uygulama ayarlarında değişiklik önler. **Yapılandırılmamış** kullanıcının Find My Friends uygulamasının ayarlarını değiştirmesine izin verir.
- **Spotlight aramasının (yalnızca denetimli) internet'ten sonuç döndürmesine izin**: **Blok** Spotlight Internet aramasının herhangi bir sonuç döndürmesini durdurur. **Yapılandırılmamış** Spotlight arama, arama sonuçları sağlamak için Internet'e bağlanmasına izin verir.
- **Engelle (yalnızca denetimli) cihaz sistem uygulamalardan kaldırılmasını**: Seçme **blok** sistemi uygulamaları CİHAZDAN kaldırma özelliği devre dışı bırakır. **Yapılandırılmamış** kullanıcıların sistemi uygulamalarının kaldırılmasına olanak tanır.

#### <a name="safari"></a>Safari

- **Safari**: **Blok** cihazda Safari tarayıcısı kullanılarak. **Yapılandırılmamış** Safari tarayıcısı kullanmasına olanak tanır.
- **Otomatik doldurmaya**: **Blok** cihazda Safari otomatik doldurma özelliğini devre dışı bırakır. **Yapılandırılmamış** kullanıcıların web tarayıcısında otomatik tamamlama ayarlarını değiştirmesine olanak tanır.
- **Tanımlama bilgilerini**: Tanımlama bilgilerinin cihazda nasıl işleneceğini seçin. Seçenekleriniz şunlardır:
  - İzin Ver
  - Tüm tanımlama bilgilerini engelle
  - Ziyaret edilen web sitelerinin tanımlama bilgilerine izin ver
  - Geçerli web sitesinden tanımlama bilgilerine izin ver
- **JavaScript**: **Blok** tarayıcıda Java betiğinin cihazda çalışmasını engeller. **Yapılandırılmamış** Java betiklerini sağlar.
- **Dolandırıcılık uyarıları**: **Gerekli** sahtekarlık uyarılarına cihazdaki web tarayıcısının gösterilecek. **Yapılandırılmamış** bu özelliği devre dışı bırakır.
- **Açılır pencereler**: **Blok** web tarayıcısında açılır pencere engelleyicisini devre dışı bırakmak için. **Yapılandırılmamış** açılır pencere engelleyicisine izin verir.

## <a name="restricted-apps"></a>Kısıtlı uygulamalar

Kısıtlı uygulamalar listesinde, aşağıdaki listelerden birini yapılandırabilirsiniz:

- **Yasak uygulamalar**: Cihazda yüklü istemediğiniz Intune tarafından yönetilmeyen uygulamaların listesi. Bir kullanıcı bu listeden bir uygulama yüklerse, Intune tarafından bildirim alırsınız.
- **Onaylı uygulamalar**: Kullanıcıların yüklemesine izin verilen uygulamaların bir listesi. Uyumlu kalmak için kullanıcılar diğer uygulamaları yüklememelidir. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir. Bir kullanıcı bu listeden bir uygulama yüklerse, Intune tarafından bildirim alırsınız.

Bu listelerden uygulamaları eklemek, şunları yapabilirsiniz:

- **Ekleme** iTunes App depolamak istediğiniz uygulamanın URL'si. Örneğin, Microsoft Çalışma klasörleri uygulamasını eklemek için girin `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`.

  Bir uygulamanın URL'sini bulmak için iTunes App Store açın ve uygulamayı arayın. Örneğin, arama `Microsoft Remote Desktop` veya `Microsoft Word`. Uygulamayı seçin ve URL'yi kopyalayın.

  Ayrıca uygulamayı bulmak için iTunes kullanabilir ve ardından **bağlantıyı Kopyala** görev uygulama URL'sini alabilirsiniz.

- URL'si dahil olmak üzere uygulama ayrıntılarını içeren bir CSV dosyasını içeri aktarın. `<app url>, <app name>, <app publisher>` biçimini kullanın. Veya aynı biçimdeki kısıtlı uygulama listesi içeren mevcut bir listeyi dışarı aktarın.

> [!IMPORTANT]
> Kısıtlı uygulama ayarlarını kullanan cihaz profilleri kullanıcı gruplarına atanmalıdır.

## <a name="show-or-hide-apps-supervised-only"></a>Uygulamaları gösterme veya gizleme (yalnızca denetimli)

Gösterme veya gizleme uygulamalar listesinde aşağıdaki listelerden birini iOS 9.3 veya üzeri çalıştıran denetimli cihazlarda yapılandırabilirsiniz.

- **Gizli uygulamalar**: Kullanıcılardan gizlenen uygulamaların listesini girin. Kullanıcılar görüntüleyemez veya bu uygulamaları açın.
- **Görünür uygulamalar**: Kullanıcıların görüntüleyebileceği ve başlatabileceği uygulamaların listesini girin. Başka hiçbir uygulama görüntülenemez veya başlatılamaz.

Bu listelerden uygulamaları eklemek, şunları yapabilirsiniz:

- **Ekleme** iTunes App depolamak istediğiniz uygulamanın URL'si. Örneğin, Microsoft Çalışma klasörleri uygulamasını eklemek için girin `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`.

  Bir uygulamanın URL'sini bulmak için iTunes App Store açın ve uygulamayı arayın. Örneğin, arama `Microsoft Remote Desktop` veya `Microsoft Word`. Uygulamayı seçin ve URL'yi kopyalayın.

  Ayrıca uygulamayı bulmak için iTunes kullanabilir ve ardından **bağlantıyı Kopyala** görev uygulama URL'sini alabilirsiniz.

- URL'si dahil olmak üzere uygulama ayrıntılarını içeren bir CSV dosyasını içeri aktarın. `<app url>, <app name>, <app publisher>` biçimini kullanın. Veya aynı biçimdeki kısıtlı uygulama listesi içeren mevcut bir listeyi dışarı aktarın.

## <a name="wireless"></a>Kablosuz

- **Veri dolaşımı**: Seçin **blok** hücresel ağ üzerinde veri dolaşımını önlemek için. **Yapılandırılmamış** (varsayılan), cihaz hücresel ağ kullanırken veri dolaşımına izin verir.
- **Dolaşım sırasında genel arka planda getirme**: **Blok** hücresel ağ üzerinde Dolaşım sırasında genel arka planda getirme özelliğini kullanarak engeller. **Yapılandırılmamış** (varsayılan), cihazın bir cep telefonu şebekesinde dolaşımdayken e-posta gibi verileri getirmek izin verir.
- **Sesli arama**: Seçin **blok** kullanıcıların cihazda sesli arama özelliğini kullanmasını önlemek için. **Yapılandırılmamış** (varsayılan), cihazda sesle izin verir.
- **Ses dolaşımı**: Seçin **blok** ses telefonu şebekesinde dolaşımı önlemek için. **Yapılandırılmamış** (varsayılan) ses cihaz hücresel ağ kullanırken dolaşımına izin verir.
- **Uygulama hücresel veri kullanım ayarlarında (yalnızca denetimli) yapılan değişiklikler**: Seçin **blok** uygulama hücresel veri kullanımı ayarlarında yapılan değişiklikleri önlemek için. **Yapılandırılmamış** (varsayılan), kullanıcının hangi uygulamaların hücresel veri kullanma izin denetlemesine olanak sağlar.
- **(Yalnızca denetimli) hücresel planı ayarlarında yapılan değişiklikler**: **Blok** kullanıcılar hücresel plandaki tüm ayarlarını değiştirmesini engeller. **Yapılandırılmamış** (varsayılan), kullanıcıların değişiklik yapmasına izin verir.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11.0 ve sonraki

- **Kişisel etkin nokta**: **Blok** cihazın kişisel etkin nokta kullanılmasını engeller. Bu ayar, bazı operatörler ile uyumlu olmayabilir. **Yapılandırılmamış** (varsayılan), bu özelliği sağlar.
- **(Yalnızca denetimli) yapılandırma profilleri kullanarak yalnızca Wi-Fi ağlarına Katıl**: **Gerekli** cihaz, yalnızca Intune yapılandırma profilleri aracılığıyla kurulan Wi-Fi ağlarını kullanmaya zorlar. **Yapılandırılmamış** (varsayılan) diğer Wi-Fi ağlarına kullanmasına izin verir.
- **Hücresel kullanım kuralları (yalnızca yönetilen uygulamalar)**: Hücresel ağa bağlıyken yönetilen uygulamalar türleri kullanabilirsiniz verileri tanımlar. Seçenekleriniz şunlardır:
  - **Hücresel veri kullanımını engelleme**: Engellemek için hücresel veri kullanarak **tüm yönetilen uygulamalar** veya **belirli uygulamalar seçebilirsiniz**.
  - **Dolaşım sırasında hücresel veri kullanımını engelleme**: Dolaşım sırasında hücresel veri kullanarak block **tüm yönetilen uygulamalar** veya **belirli uygulamalar seçebilirsiniz**.

## <a name="connected-devices"></a>Bağlı Cihazlar

- **AirDrop (yalnızca denetimli)**: **Blok** Airdrop'a cihazda kullanarak engeller. **Yapılandırılmamış** (varsayılan), yakındaki cihazlarla içerik değişimi için AirDrop özelliğinin kullanılmasını sağlar.
- **Apple Watch eşleştirme (yalnızca denetimli)**: **Blok** bir Apple Watch ile eşleştirme engeller. **Yapılandırılmamış** (varsayılan), cihazın bir Apple Watch ile eşleşmesine izin verir.
- **Eşleştirilmiş Apple Watch için bilek algılama**: **Gerekli** bir eşleştirilmiş Apple Watch için bilek algılama kullanmaya zorlar. Bunu değil takılmadığında gerektiğinde, Apple Watch bildirim görüntülenmez. 
- **Bluetooth değişikliği (yalnızca denetimli)**: **Blok** son kullanıcının cihazda Bluetooth ayarlarını değiştirmesini engeller. **Yapılandırılmamış** (varsayılan), bu ayarları değiştirmek kullanıcının sağlar.
- **Bir iOS cihazının eşleştirilebildiği (yalnızca denetimli) cihazları denetlemek için konak eşleştirmeye**: **Yapılandırılmamış** (varsayılan) bir iOS cihazının eşleştirilebildiği hangi cihazların yöneticinin denetlemesi için konak eşleştirmeye izin verir. **Blok** eşlenebileceği engeller.
- **Giden AirPlay istekleri parola gerektiren**: **Gerekli** kullanıcının diğer Apple cihazlarına içerik akışı sağlamak üzere airplay'i bir eşleştirme parolası. **Yapılandırılmamış** (varsayılan), kullanıcının bir parola girmeden AirPlay kullanarak içerik akışı sağlar.
- **Engelle (yalnızca denetimli) AirPrint**: Seçin **blok** cihazda AirPrint özelliğini kullanarak önlemek için. **Yapılandırılmamış** (varsayılan) AirPrint kullanmasına izin verir.
  - **Blok depolama AirPrint kimlik bilgileri (yalnızca denetimli) anahtarlıktaki**: **Blok** kullanıcı adı ve parola cihazda Anahtarlık depolama kullanarak engeller. **Yapılandırılmamış** (varsayılan), anahtar zinciri uygulamada AirPrint kullanıcı adı ve parola depolama sağlar.
  - **(Yalnızca denetimli) için AirPrint güvenli TLS sertifika gerektiren**: **Gerekli** TLS yazdırma iletişim için güvenilen sertifikalar kullanmak için cihazın zorlar.
  - **AirPrint yazıcıları (yalnızca denetimli) iBeacon bulunmasını engelleyin**: **Blok** kimlik avı ağ trafiği için kötü amaçlı AirPrint Bluetooth işaretleri engeller. **Yapılandırılmamış** (varsayılan), cihaz üzerinde AirPrint yazıcıları reklam sağlar.
- **Engelleme ayarını ayarlama yeni cihazlar (yalnızca denetimli)**: **Blok** yakında yeni cihazlar Kurulum istemini devre dışı bırakır. **Yapılandırılmamış** (varsayılan) istemleri için yakında diğer Apple cihazlarına bağlanmasına izin verir.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11.0 ve sonraki

## <a name="keyboard-and-dictionary"></a>Klavye ve Sözlük

- **Sözcük tanımı arama (yalnızca denetimli)**: **Blok** kullanıcının bir word vurgulama ve sonra cihazdaki tanımı bakarak engeller. **Yapılandırılmamış** tanım arama özelliğini erişmesini sağlar.
- **Klavyeler (yalnızca denetimli)**: **Yapılandırılmamış** tahmin eden klavyelere sözcükleri öneren kullanıcı kullanmayı isteyebileceğiniz izin verir. **Blok** bu özellik engeller.
- **Otomatik Düzeltme (yalnızca denetimli)**: **Yapılandırılmamış** cihazın yanlış yazılan sözcükleri otomatik olarak düzeltmek izin verir. **Blok** otomatik düzeltme engel olur.
- **Klavye yazım denetimi (yalnızca denetimli)**: **Yapılandırılmamış** yazım cihazda kullanımına izin verir. **Blok** yazım denetimcisine izin verir.
- **Klavye kısayolları (yalnızca denetimli)**: **Yapılandırılmamış** cihazda klavye kısayollarını kullanarak sağlar. **Blok** klavye kısayollarını kullanarak kullanıcının durdurur.
- **Dikte (yalnızca denetimli)**: **Blok** kullanıcının sesli metin girmek için giriş yapmasını durdurur. **Yapılandırılmamış** kullanıcının dikte girişini kullanmasını sağlar.

## <a name="cloud-and-storage"></a>Bulut ve Depolama

- **İcloud'a yedekle**: **Yapılandırılmamış** kullanıcının cihazı İcloud'a yedeklemesine izin verir. **Blok** kullanıcının cihazı İcloud'a yedeklemeyi engeller.
- **Belge eşitleme (yalnızca denetimli) icloud**: **Yapılandırılmamış** iCloud depolama alanınızda belge ve anahtar-değer eşitlemesine izin verir. **Blok** iCloud belgeleri ve verileri eşitlenmesini önler.
- **İcloud'a fotoğraf akışı eşitlemesi**: **Yapılandırılmamış** etkinleştirme olanağı **My fotoğraf Stream** cihazlarında İcloud'a eşitlenmesine ve tüm kullanıcı aygıtları üzerinde fotoğraf kullanılabilir. **Blok** İcloud'a fotoğraf akışı eşitlemesi engeller.
- **Şifreli yedekleme**: **Gerekli** böylece cihaz yedeklemelerinin şifrelenmesini gerekir.
- **iCloud fotoğraf arşivi**: Kümesine **blok** fotoğraflar ve videoları bulutta depolamasını için iCloud fotoğraf Arşivi'ni kullanarak devre dışı bırakmak için. İCloud fotoğraf Arşivi ' cihaza tamamen indirilmeyen tüm fotoğraflar CİHAZDAN kaldırılır. **Yapılandırılmamış** iCloud fotoğraf kitaplığının kullanımına izin verir.
- **Yönetilen uygulamaları bulutla eşitleme**: **Yapılandırılmamış** Intune yöneten uygulamalarınızı kullanıcının iCloud hesabıyla veri eşitlemesine izin verir. **Blok** bu veri eşitleme İcloud'a engeller.
- **Paylaşılan fotoğraf akışı**: Seçin **blok** devre dışı bırakmak için **iCloud fotoğraf paylaşma** cihazda. **Yapılandırılmamış** paylaşılan fotoğraf akışını sağlar.
- **Etkinlik devamlılığı**: **Yapılandırılmamış** kullanıcıların, başka bir iOS veya macOS cihazda (Handoff) bir iOS cihazında başladığınız bir çalışmayı devam etmesini sağlar. **Blok** bu iletim engeller.
- **İCloud anahtar zinciri eşitlenmesinin engellenip**: Seçin **blok** icloud Anahtarlıkta depolanan eşitleme kimlik bilgileri devre dışı bırakmak için. **Yapılandırılmamış** kullanıcıların bu kimlik bilgilerini eşitleme sağlar.
- **Block Kurumsal kitap yedekleme**: Seçin **blok** kullanıcılar Kurumsal defterlerini yedeklemesini engellemek için. **Yapılandırılmamış** bu defterlerini yedeklemesine izin verir.
- **Engelle (Notlar ve vurgular) Kurumsal kitabı meta verileri eşitleme**: **Blok** eşitleme notları engeller ve kurumsal kitaplarda vurgular. **Yapılandırılmamış** eşitlemeye izin verir.

## <a name="autonomous-single-app-mode-supervised-only"></a>Otonom tek uygulama modu (yalnızca denetimli)

İOS cihazlarını belirli uygulamaları otonom tek uygulama modunda çalışacak şekilde yapılandırmak için bu ayarları kullanın. Bu modda yapılandırılır ve uygulama çalıştırıldığında cihaz kilitli. Ayrıca, bu uygulama yalnızca çalıştırabilirsiniz. Örneğin, kullanıcıların cihazda sınav olanak sağlayan bir uygulama ekleyin. Uygulama eylemleri tamamlandığında veya bu ilkeyi kaldırdığınızda cihaz normal durumuna döner.

Uygulama eklemek için şunları yapabilirsiniz:

- Girin **uygulama adı** ve **uygulama paket kimliği**seçip **Ekle**. [Yerleşik iOS uygulamaları için paket kimliği başvurusu](#bundle-id-reference-for-built-in-ios-apps) (Bu makalede) kimlikleri ile bazı uygulamaları içerir.
- **İçeri aktarma** uygulama adları ve bunların paket kimliklerinin listesini içeren bir CSV dosyası. Veya, **dışarı** uygulamaları içeren mevcut bir listesi.

## <a name="kiosk-supervised-only"></a>Bilgi noktası (yalnızca denetimli)

- **Bilgi noktası modunda çalıştırmak için uygulama**: Bilgi noktası modunda çalıştırmak istediğiniz uygulamaları seçin. Seçenekleriniz şunlardır: 
  - **App Store**: Bir uygulamanın iTunes uygulama mağazası URL'sini girin
  - **Yönetilen uygulama**: Intune'a eklediğiniz bir uygulama seçin
  - **Yerleşik uygulama**: Girin [paket Kimliğini](#bundle-id-reference-for-built-in-ios-apps) yerleşik uygulama

- **Yardımcı dokunma**: **Gerekli** Yardımlı dokunma erişilebilirlik ayarını cihazda olabilir. Bu özellik ile kullanıcıların ekran kendileri için zor olabilecek hareketlerini yardımcı olur. **Yapılandırılmamış** değil çalıştırın veya bilgi noktası modunda bu özelliği etkinleştirin.
- **Renkleri ters çevir**: **Gerekli** görme bozukluğu olan kullanıcılara ekran değiştirebilmeniz için renkleri ters çevir erişilebilirlik ayarını. **Yapılandırılmamış** değil çalıştırın veya bilgi noktası modunda bu özelliği etkinleştirin.
- **Mono Ses**: **Gerekli** Mono Ses erişilebilirlik ayarını cihazda olabilir. **Yapılandırılmamış** değil çalıştırın veya bilgi noktası modunda bu özelliği etkinleştirin.
- **VoiceOver**: **Gerekli** VoiceOver erişilebilirlik ayarını ekranındaki metin sesli okumak için cihazda olabilir. **Yapılandırılmamış** değil çalıştırın veya bilgi noktası modunda bu özelliği etkinleştirin.
- **Yakınlaştırma**: **Gerekli** yakınlaştırma ayarını olması cihazda dokunmatik ekranda yakınlaştırmak için kullanıcıların izin vermek için. **Yapılandırılmamış** değil çalıştırın veya bilgi noktası modunda bu özelliği etkinleştirin.
- **Otomatik kilit**: **İzin** cihazda otomatik kilitlemeyi. **Yapılandırılmamış** bu özelliği devre dışı bırakır.
- **Açma/kapama**: **İzin** cihazda ses düğmesi (sessiz) geçin. **Yapılandırılmamış** bu özelliği devre dışı bırakır.
- **Ekran döndürme**: **İzin** kullanıcı cihazı döndürdüğünde ekran yönünü değiştirmeyi. **Yapılandırılmamış** bu özelliği devre dışı bırakır.
- **Ekran Uyku düğmesi**: Seçin **izin** uykudan Uyanma düğmesini cihazda devre dışı bırakmak için. **Yapılandırılmamış** bu özellik sağlar.
- **Touch**: **Blok** cihazda dokunmatik ekranı devre dışı bırakır. **Yapılandırılmamış** dokunmatik ekranı kullanmasına izin verir.
- **Ses düzeyi düğmelerine**: **İzin** cihazdaki ses düğmelerini kullanarak. **Yapılandırılmamış** ses düğmelerini devre dışı bırakır.
- **Yardımlı dokunma denetimi**: **İzin** kullanıcıların yardımcı dokunma işlevini kullanın. **Yapılandırılmamış** bu özelliği devre dışı bırakır.
- **Renkleri tersine çevirme denetimi**: **İzin** kullanıcıların renkleri ters çevirme işlevini ayarlamasına izin vermek için renk değişiklikleri ters çevir. **Yapılandırılmamış** bu özelliği devre dışı bırakır.
- **Seçili metin üzerine konuşmak**: **İzin** seçimi seslendir erişilebilirlik ayarını cihazda olabilir. Bu özellik, sesli kullanıcının seçtiği metni okur. **Yapılandırılmamış** bu özelliği devre dışı bırakır.
- **VoiceOver denetimi**: **İzin** voiceover değişiklikleri kullanıcıların ne kadar hızlı ekrandaki metin yüksek sesle okumak gibi VoiceOver işlevini güncelleştirin. **Yapılandırılmamış** voiceover değişiklik önler.
- **Yakınlaştırma Denetimi**: **İzin** kullanıcı tarafından değişiklikler yakınlaştırma. **Yapılandırılmamış** yakınlaştırma değişiklik önler.

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
| com.apple.DocumentsApp      | Dosyalar        | Apple     |
| com.apple.mobileme.fmf1     | Arkadaşları Bul | Apple     |
| com.apple.mobileme.fmip1    | iPhone’u Bul  | Apple     |
| com.apple.gamecenter        | Oyun Merkezi  | Apple     |
| com.apple.mobilegarageband  | GarageBand   | Apple     |
| com.apple.Health            | Durum       | Apple     |
| com.apple.Home              | Ana Sayfası         | Apple     |
| com.apple.iBooks            | iBooks       | Apple     |
| com.apple.iMovie            | iMovie       | Apple     |
| com.apple.itunesconnect.mobile | iTunes Connect | Apple |
| com.apple.MobileStore       | iTunes Store | Apple     |
| com.apple.itunesu           | iTunes U     | Apple     |
| com.apple.Keynote           | Keynote      | Apple     |
| com.apple.mobilemail        | Mail         | Apple     |
| com.apple.Maps              | Haritalar         | Apple     |
| com.apple.MobileSMS         | İletiler     | Apple     |
| com.apple.Music             | Müzik        | Apple     |
| com.apple.news              | News         | Apple     |
| com.apple.mobilenotes       | Notlar        | Apple     |
| com.apple.Numbers           | Sayılar      | Apple     |
| com.apple.Pages             | Sayfaları        | Apple     |
| com.apple.Photo-Booth       | Photo Booth  | Apple     |
| com.apple.mobileslideshow   | Fotoğraflar       | Apple     |
| com.apple.podcasts          | Podcast’ler     | Apple     |
| com.apple.reminders         | Anımsatıcılar    | Apple     |
| com.apple.mobilesafari      | Safari       | Apple     |
| com.apple.Preferences       | Ayarlar     | Apple     |
| com.apple.SiriViewService   | Siri         | Apple     |
| com.apple.stocks            | Borsa       | Apple     |
| com.apple.tips              | İpuçları         | Apple     |
| com.apple.TV                | TV           | Apple     |
| com.apple.videos            | Videolar       | Apple     |
| com.apple.VoiceMemos        | Sesli Notlar   | Apple     |
| com.apple.Passbook          | Wallet       | Apple     |
| com.apple.Bridge            | İzleme        | Apple     |
| com.apple.weather           | Hava durumu      | Apple     |

## <a name="domains"></a>Etki Alanları

### <a name="unmarked-email-domains"></a>İşaretsiz e-posta etki alanları

İçinde **e-posta etki alanı URL'si**, listeye bir veya daha fazla URL ekleyin. Son kullanıcılar, girdiğiniz etki alanı dışındaki bir etki alanından e-posta aldığınızda, e-posta işaretlenmiş iOS Mail uygulamasında güvenilmeyen olarak.

### <a name="managed-web-domains"></a>Yönetilen web etki alanları

İçinde **Web etki alanı URL'si**, listeye bir veya daha fazla URL ekleyin. Belgeler, girdiğiniz etki alanlarından indirildiğinde bunlar yönetilen kabul. Bu ayar yalnızca Safari tarayıcısı kullanılarak indirilen belgeler için geçerlidir.

### <a name="safari-password-autofill-domains"></a>Safari parola otomatik doldurma etki alanları

İçinde **etki alanı URL'si**, listeye bir veya daha fazla URL ekleyin. Kullanıcılar yalnızca bu listedeki URL’lerdeki parolaları kaydedebilir. Bu ayar yalnızca Safari tarayıcısı ve denetimli moddaki iOS 9.3 ve üzeri cihazlar için geçerlidir. Herhangi bir URL belirtmezseniz, parolalar tüm web sitelerinden kaydedilebilir.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).

Üzerinde cihaz özelliklerini ve ayarlarını da kısıtlayabilirsiniz [macOS](device-restrictions-macos.md) cihazlar.
