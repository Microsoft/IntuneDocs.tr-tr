---
title: Android Kurumsal cihaz ayarları Microsoft Intune - Azure | Microsoft Docs
description: Android Enterprise veya Android for Work cihazlarında, kopyalama ve yapıştırma, bildirimleri gösterme, uygulama izinleri, veri paylaşımı, parola uzunluğu, oturum açma hatalarında oturum açmak, kilidi açmak, parolaları yeniden kullanmak ve Bluetooth 'u etkinleştirmek dahil olmak üzere cihazdaki ayarları kısıtlayın iş kişilerinin paylaşılması. Tek bir uygulama veya birden çok uygulama çalıştırmak için cihazları adanmış bir cihaz bilgi noktası olarak yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/04/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7d9c385ff8c08f9f1df00a081bca1f61a2a5015a
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74832559"
---
# <a name="android-enterprise-device-settings-to-allow-or-restrict-features-using-intune"></a>İzin vermek veya Intune kullanarak özellikleri kısıtlamak için android Kurumsal cihaz ayarları

Bu makalede, listeler ve Android Kurumsal cihazlarda denetleyebileceğiniz farklı ayarlar açıklanır. Mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak bu ayarları, özelliklere izin vermek veya devre dışı bırakmak, uygulamaları adanmış cihazlarda çalıştırmak, güvenliği denetlemek ve daha fazlasını yapmak için kullanın.

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz yapılandırma profili oluşturma](device-restrictions-configure.md).

## <a name="device-owner-only"></a>Yalnızca cihaz sahibi

Bu ayarlar, Intune 'un Android kurumsal tam olarak yönetilen veya adanmış cihazlar gibi tüm cihazı denetlediği Android kurumsal kayıt türleri için geçerlidir.

### <a name="general-settings"></a>Genel ayarlar

- **Ekran Yakalama**: seçin **blok** cihazın ekran veya ekran görüntüleri önlemek için. Ayrıca güvenli bir video çıkışına sahip olmayan görüntü cihazlarında gösterilen içeriği engeller. **Yapılandırılmamış** kullanıcının ekran içeriğini resim olarak yakalamasına izin verir.
- **Kamera**: seçin **blok** için cihaz kameranızı erişimi engellemek için. **Gerekli değil** cihazın kamerasını erişmesini sağlar.
- **Varsayılan izin ilkesi**: Bu ayar, çalışma zamanı izin istekleri için varsayılan izin ilkesini tanımlar. Olası değerler şöyledir:
  - **Cihaz varsayılanı**: Cihazın varsayılan ayarını kullanın.
  - **İstem**: Kullanıcıdan izni onaylaması istenir.
  - **Otomatik olarak izin ver**: İzinler otomatik olarak verilir.
  - **Otomatik olarak reddet**: İzinler otomatik reddedilir.
- **Tarih ve saat değişikliklerini**: seçin **blok** kullanıcıların el ile tarih ve saat ayarından önlemek için. **Yapılandırılmamış** ayarlanmış tarih ve saat için kullanıcıların cihazda izin verir.
- **Birim değişiklikleri**: **Engelle** , kullanıcıların cihazın birimini değiştirmesini önler ve ana birimi de kapatır. **Yapılandırılmamış** cihazda birim ayarlarını kullanımına izin verir.
- **Fabrika sıfırlaması**: seçin **blok** sıfırlama seçeneği cihazın Ayarları'nda kullanıcıların Fabrika kullanmasını önlemek için. **Yapılandırılmamış** Bu ayar cihazda kullanmasına olanak tanır.
- **Güvenli önyükleme**: Kullanıcıların cihazı güvenli moda önyüklemesini önlemek için **Engelle** olarak ayarlayın. **Yapılandırılmamış** kullanıcılar güvenli modda cihazın yeniden başlatılmasına izin verir.
- **Durum çubuğu**: seçin **blok** durum çubuğu, bildirimler ve hızlı ayarlar dahil olmak üzere erişimi engellemek için. **Yapılandırılmamış** kullanıcıların durum çubuğuna erişimi sağlar.
- **Veri Hizmetleri**: seçin **blok** hücresel ağ üzerinde veri dolaşımını önlemek için. **Yapılandırılmamış** cihaz hücresel ağ kullanırken veri dolaşımına izin verir.
- **Wi-Fi ayar değişiklikleri**: seçin **blok** kullanıcıların cihaz sahibi tarafından oluşturulan Wi-Fi ayarları değiştirmesini önlemek için. Kullanıcılar kendi Wi-Fi yapılandırmalarını oluşturabilir. **Yapılandırılmamış** kullanıcıların cihazda Wi-Fi ayarlarını değiştirmesine olanak tanır.
- **Wi-Fi erişim noktası yapılandırması**: seçin **blok** kullanıcıların oluşturma veya herhangi bir Wi-Fi yapılandırması değiştirmesini önlemek için. **Yapılandırılmamış** kullanıcıların cihazda Wi-Fi ayarlarını değiştirmesine olanak tanır.
- **Bluetooth yapılandırma**: seçin **blok** kullanıcıların cihazda Bluetooth yapılandırmasını önlemek için. **Yapılandırılmamış** cihazda Bluetooth'un kullanımına izin verir.
- **İnternet paylaşımı ve erişimi noktalarına**: seçin **blok** taşınabilir etkin noktalarına internet paylaşımı ve erişimi önlemek için. **Yapılandırılmamış** internet paylaşımı ve taşınabilir noktalarına erişim sağlar.
- **USB depolamasını**: seçin **izin** cihazdaki USB depolama erişim için. **Yapılandırılmamış** USB depolama alanına erişimini engeller.
- **USB dosya aktarımı**: seçin **blok** önlemek için USB üzerinden dosyaları aktarma. **Yapılandırılmamış** dosyaları aktarma sağlar.
- **Dış medya**: seçin **blok** kullanarak veya CİHAZDAN Dış medya bağlanma önlemek için. **Yapılandırılmamış** Dış medya cihazda izin verir.
- **NFC kullanarak verileri ışın**: seçin **blok** yakın alan iletişimi (NFC) teknolojisini kullanarak ışını veri uygulamalardan önlemek için. **Yapılandırılmamış** cihazlar arasında veri paylaşımı için NFC kullanımına izin verir.
- **Hata ayıklama özellikleri**: seçin **izin** kullanıcıların cihazda hata ayıklama özelliklerini kullanın. **Yapılandırılmamış** kullanıcıların cihazda hata ayıklama özelliklerini kullanmasını önler.
- **Mikrofon Ayarlama**: seçin **blok** mikrofonun sesinin açılmasını ve mikrofon ses kullanıcıların önlemek için. **Yapılandırılmamış** kullanma ve cihazda mikrofon ses ayarlamak izin verir.
- **Fabrika ayarlarına sıfırlama koruması e-postaları**: seçin **Google hesabı e-posta adresleri**. Bunu temizlendikten sonra cihazın kilidini açmak cihaz yöneticilerinin e-posta adreslerini girin. E-posta adresi gibi bir noktalı virgül ile ayırın mutlaka `admin1@gmail.com;admin2@gmail.com`. E-posta değil girdiyseniz, fabrika ayarlarına geri yüklendikten sonra herkes cihazın kilidini açabilirsiniz. Bu e-postalar yalnızca, Kurtarma menüsünü kullanarak Fabrika Sıfırlaması çalıştırma gibi kullanıcı olmayan bir fabrika sıfırlaması çalıştırıldığında geçerlidir.
- **Ağ kaçış noktası**: seçin **etkinleştirme** ağ kaçış tarama özelliğini etkinleştirmek kullanıcılara izin vermek için. Cihaz önyüklendiğinde bir ağ bağlantısı olmayan yaptıysanız, kaçış noktası geçici olarak bir ağa bağlayın ve cihaz ilkesini yenilemek sorar. Bu ilke uygulandıktan sonra geçici ağ unutulur ve cihaz önyüklemeye devam eder. Bu özellik, cihazları ağa bağlanır:
  - Son ilkede uygun bir ağ yok.
  - Cihaz uygulama kilidi görev modunda önyüklenir.
  - Kullanıcı cihaz ayarları ulaşamıyor.

  **Yapılandırılmamış** kullanıcıların cihazdaki ağ kaçış tarama özelliği kapatmasını engeller.

- **Sistem Güncelleştirmesi**: cihaz havadan güncelleştirmeler nasıl işlediğini tanımlamak için bir seçenek belirleyin:
  - **Cihaz Varsayılanı**: Cihazın varsayılan ayarını kullanın.
  - **Otomatik**: Güncelleştirmeler, kullanıcı etkileşimi olmadan otomatik olarak yüklenir. Bu ilkeyi seçmek, bekleyen tüm güncelleştirmeleri hemen yükler.
  - **Erteleme**: Güncelleştirmeler 30 gün boyunca ertelenir. 30 günün sonunda, Android güncelleştirmeyi yüklemek için kullanıcıya sorar. Cihaz üreticilerin veya taşıyıcıların önemli güvenli güncelleştirmelerinin ertelenmesini engellemek (muaf tutmak) mümkündür. Muaf tutulan bir güncelleştirme cihazda kullanıcıya bir sistem bildirimi gösterir.
  - **Bakım penceresi**: Güncelleştirmeleri Intune'da ayarladığınız bir günlük bakım penceresi içinde otomatik olarak yükler. Yükleme 30 gün boyunca her gün çalışır ve yeterli alan veya pil düzeyleri varsa başarısız olabilir. 30 gün sonra kullanıcıyı uygulamayı yüklemek için Android ister. Bu pencere ayrıca Oynatma uygulamalarının güncelleştirmelerini yüklemek için de kullanılır. Tek uygulamayla ayrılmış cihaz ön plan uygulamaları güncelleştirilemeyebilir, kiosks gibi adanmış cihazlar için bu seçeneği kullanın.

- **Bildirim pencereleri**: **devre dışı**olarak ayarlandığında, Tolar, gelen çağrılar, giden çağrılar, sistem uyarıları ve sistem hataları gibi pencere bildirimleri cihazda gösterilmez. **Yapılandırılmadı**olarak ayarlandığında, varsayılan işletim sistemi kullanılır ve bu da bildirimleri göstermek olabilir.
- **İlk kullanım Ipuçlarını atla**: **Etkinleştir** , öğreticilerde adım adım geçen uygulamalardan veya uygulamanın başladığı bir ipuçlarına ilişkin önerileri gizler veya atlar. **Yapılandırılmadı**olarak ayarlandığında, işletim sistemi varsayılanı kullanılır ve bu, uygulama başladığında bu önerileri gösterebilir.

### <a name="system-security-settings"></a>Sistem güvenliği ayarları

- **Uygulamalarda tehdit taraması**: **gerektir** (varsayılan), uygulamaları yüklenmeden önce ve sonra taraması için Google Play koruma sağlar. Tehdit algılarsa, uygulamayı cihazdan kaldırmak için kullanıcıyı uyarabilir. **Yapılandırılmadı** , uygulamaları taramak Için Google Play koruma sağlamaz veya çalıştırılmaz.

### <a name="dedicated-device-settings"></a>Adanmış cihaz ayarları

Adanmış cihazlarınızda bilgi noktası stili bir deneyim yapılandırmak için bu ayarları kullanın. Bir cihazı tek bir uygulamayı çalıştıracak şekilde yapılandırabilir veya birçok uygulama çalıştırabilirsiniz. Cihaz bilgi noktası moduyla ayarlandığında, yalnızca eklediğiniz uygulamalar kullanılabilir. Bu ayarlar Android kurumsal adanmış cihazlara uygulanır. Android kurumsal tam yönetilen cihazlara uygulanmaz.

**Bilgi noktası modu**: cihazın bir uygulama çalıştırmasını veya birden çok uygulamayı çalıştırmasını seçin.

- **Tek uygulama**: kullanıcılar cihazdaki tek bir uygulamaya yalnızca erişebilir. Cihaz başlatıldığında, yalnızca belirli uygulamayı başlatır. Kullanıcılar yeni uygulamalar açamaz veya çalışan uygulamayı değiştiremez.

  - **Yönetilen bir uygulama seçin**: listeden yönetilen Google Play uygulamasını seçin.

    Ardından, listelenen tüm uygulamalar yoksa [bazı Android uygulamaları ekleme](../apps/apps-add-android-for-work.md) cihaza. [Uygulamayı adanmış cihazlarınız için oluşturulan cihaz grubuna atadığınızdan](../apps/apps-deploy.md)emin olun.

  > [!IMPORTANT]
  > Tek uygulama bilgi noktası modu kullanılırken, çevirici/telefon uygulamaları düzgün çalışmayabilir. 
  
- **Çoklu uygulama**: kullanıcılar cihazdaki sınırlı bir uygulama kümesine erişebilir. Cihaz başlatıldığında, yalnızca eklediğiniz uygulamalar başlatın. Ayrıca, kullanıcılar açabilir bazı web bağlantıları da ekleyebilirsiniz. İlkenin geçerli olduğu kullanıcı giriş ekranında simgeleri için izin verilen uygulamalar görürsünüz.

  > [!IMPORTANT]
  > Çok uygulamayla ayrılmış cihazlarda, Google Play [yönetilen giriş ekranı uygulamasının](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise) şu **olması gerekir**:
  >   - [Bir istemci uygulaması olarak eklenen](../apps/apps-add-android-for-work.md) ıntune
  >   - Adanmış cihazlarınız için oluşturulan [cihaz grubuna atandı](../apps/apps-deploy.md)
  >
  > **Giriş ekranı yönetilen** uygulama yapılandırma profilinde de olması için gerekli değildir, ancak bir istemci uygulaması olarak eklenmesi için gereklidir. **Yönetilen giriş ekranı** uygulaması bir istemci uygulaması olarak eklendiğinde, yapılandırma profiline eklediğiniz diğer uygulamalar **yönetilen giriş ekranı** uygulamasında simgeler olarak gösterilir.
  >
  > Birden çok uygulama bilgi noktası modu kullanılırken, çevirici/telefon uygulamaları düzgün çalışmayabilir. 

  - **Ekle**: listeden uygulamalarınızı seçin.

    Varsa **giriş ekranı yönetilen** uygulama listelenmez, ardından [Google Play'den ekleme](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise). Uygulamayı adanmış cihazlarınız için oluşturulan cihaz grubuna [atadığınızdan](../apps/apps-deploy.md) emin olun.

    Ayrıca diğer ekleyebilirsiniz [Android uygulamaları](../apps/apps-add-android-for-work.md) ve [web uygulamaları](../apps/web-app.md) cihazla kuruluşunuz tarafından oluşturulmuş. [Uygulamayı adanmış cihazlarınız için oluşturulan cihaz grubuna atadığınızdan](../apps/apps-deploy.md)emin olun.

  - **Sanal giriş düğmesi**: kullanıcıların uygulamalar arasında geçiş yapabilmesi Için kullanıcıları yönetilen giriş ekranına döndüren bir yazılım tuşu düğmesi. Seçenekleriniz şunlardır:

    - **Yapılandırılmadı** (varsayılan): Giriş düğmesi gösterilmez. Kullanıcıların, uygulamalar arasında geçiş yapmak için geri düğmesini kullanmaları gerekir.
    - **Yukarı çek**: bir giriş düğmesi, bir kullanıcının cihazda ne zaman yüzümü gösterdiğini gösterir.
    - **Kayan**: cihazda kalıcı, kayan bir giriş düğmesi gösterir.

  - **Bilgi noktası modu bırakın**: seçin **etkinleştirme** yöneticilerin bilgi noktası modu cihaz güncelleştirmek için geçici olarak duraklatmak sağlamak için. Bu özelliği kullanmak için yönetici:
  
    1. **Çıkış bilgi noktası** düğmesi gösterilene kadar geri düğmesini seçmeye devam eder. 
    2. **Bilgi noktası çıkış** düğmesini seçer ve **bilgi noktası modu kod** PIN 'ini girer.
    3. İşiniz bittiğinde, **yönetilen giriş ekranı** uygulamasını seçin. Bu adım, cihazı çoklu uygulama bilgi noktası moduna relocks.

      **Yapılandırılmadı**olarak ayarlandığında, Yöneticiler bilgi noktası modunu duraklatabilir. Yönetici geri düğmesini seçip, **bilgi noktası çıkışı** düğmesini seçerse bir ileti geçiş kodunun gerekli olduğunu belirtir.

    - **Bilgi noktası modu kod**: girin 4-6 basamaklı sayısal PIN. Yönetici bu PIN'i geçici olarak bilgi noktası modu duraklatmak için kullanır.

  - **Özel URL arka planı ayarla**: adanmış cihazda arka plan ekranını özelleştirmek IÇIN bir URL girin.

    > [!NOTE]
    > Çoğu durumda, en az aşağıdaki boyutlardaki görüntülerle başlamasını öneririz:
    >
    > - Telefon: 1080x1920 px
    > - Tablet: 1920x1080 px
    >
    > En iyi deneyim ve ayrıntılı Ayrıntılar için, görüntüleme belirtimlerine cihaz başına görüntü varlıkları oluşturulması önerilir.
    >
    > Modern görüntüler, daha yüksek piksel yoğunluklarını ve eşdeğer 2K/4K tanım görüntülerini görüntüleyebilir.

  - **Wi-Fi yapılandırması**: **Etkinleştir** ayarı, yönetilen giriş ekranında Wi-Fi denetimini gösterir ve son kullanıcıların cihazı farklı WiFi ağlarına bağlanmasına izin verir. Bu özelliği etkinleştirmek Ayrıca cihaz konumunu da etkinleştirir. **Yapılandırılmamış** (varsayılan), yönetilen giriş ekranında Wi-Fi denetimini göstermez. Kullanıcıların, yönetilen giriş ekranını kullanırken Wi-Fi ağlarına bağlanmasını engeller.

  - **Bluetooth yapılandırması**: **Etkinleştir** ayarı, yönetilen giriş ekranında Bluetooth denetimini gösterir ve son kullanıcıların cihazları Bluetooth üzerinden eşleştirmesine izin verir. Bu özelliği etkinleştirmek Ayrıca cihaz konumunu da etkinleştirir. **Yapılandırılmadı** (varsayılan), yönetilen giriş ekranında Bluetooth denetimini göstermez. Yönetilen giriş ekranını kullanırken kullanıcıların Bluetooth ve eşleme cihazlarını yapılandırmalarını engeller.

  - **El feneri erişimi**: **Enable** , yönetilen giriş ekranında el feneri denetimini gösterir ve son kullanıcıların el feneri 'i açmasına veya kapatılmasına izin verir. **Yapılandırılmadı** (varsayılan), yönetilen giriş ekranında el feneri denetimini göstermez. Yönetilen giriş ekranını kullanırken kullanıcıların el feneri kullanmasını engeller.

  - **Media Volume Control**: **Enable** ayarı, yönetilen giriş ekranında medya birimi denetimini gösterir ve son kullanıcıların bir kaydırıcı kullanarak cihazın medya birimini ayarlamasına olanak tanır. **Yapılandırılmadı** (varsayılan), yönetilen giriş ekranında medya birimi denetimini göstermez. Kullanıcıların, donanım düğmeleri onu desteklemediği sürece, yönetilen giriş ekranını kullanırken cihazın medya hacmini değiştirmesini engeller. 

  - **Ekran koruyucu modu**: **Etkinleştir** , cihaz kilitlendiğinde veya zaman aşımına uğrarsa yönetilen giriş ekranında bir ekran koruyucu gösterir. **Yapılandırılmadı** (varsayılan), yönetilen giriş ekranında bir ekran koruyucu göstermez.

    Etkinleştirildiğinde, şunları da yapılandırın:

    - **Özel ekran koruyucu görüntüsünü ayarla**: özel bir PNG, jpg, JPEG, GIF, BMP, WEBP veya ııMAGE URL 'sini girin. Örneğin şunu girin:

      - `http://www.contoso.com/image.jpg`
      - `www.contoso.com/image.bmp`
      - `https://www.contoso.com/image.webp`

      Bir URL girmezseniz, varsayılan bir görüntü varsa cihazın varsayılan görüntüsü kullanılır.
      
      > [!TIP]
      > Bit eşlemde açılabilir herhangi bir dosya kaynağı URL 'SI desteklenir.

    - **Cihazın ekranı kapatmadan önce ekran koruyucuyu gösterdiği saniye sayısı**: cihazın ekran koruyucuyu ne kadar süreyle gösterdüğüne seçin. 0-9999999 saniye arasında bir değer girin. Varsayılan değer `0` saniyedir. Boş bırakıldığında veya sıfır (`0`) olarak ayarlandığında, Kullanıcı cihazla etkileşime gelinceye kadar ekran koruyucusu etkin olur.
    - **Ekran koruyucuyu göstermeden önce cihazın etkin olmadığı saniye sayısı**: ekran koruyucuyu göstermeden önce cihazın ne kadar süreyle boşta kalacağını seçin. 1-9999999 saniye arasında bir değer girin. Varsayılan değer `30` saniyedir. Sıfırdan büyük bir sayı girmeniz gerekir (`0`).
    - **Ekran koruyucuyu başlatmadan önce medyayı Algıla**: cihazda ses veya video yürütülıyorsa, **Etkinleştir** (varsayılan) ekran koruyucuyu göstermez. **Yapılandırılmadı** , ses veya video oynatılsa bile ekran koruyucuyu gösterir.

### <a name="device-password-settings"></a>Cihaz parola ayarları

- **Kilit ekranını devre dışı bırak**: kullanıcıların cihazda keyguard kilit ekranı özelliğini kullanmalarını engellemek Için **devre dışı bırak** ' ı seçin. **Yapılandırılmamış** tuş korumasını özelliklerine izin verir.
- **Devre dışı kilit ekranı özellikleri**: cihazda keyguard etkinleştirildiğinde, hangi özelliklerin devre dışı bırakılacağını seçin. Örneğin, **güvenli kamera** işaretlendiğinde kamera özelliği cihazda devre dışı bırakılır. Denetlenmeyen tüm özellikler cihazda etkinleştirilir.

  Bu özellikler, cihaz kilitlendiğinde kullanıcılar tarafından kullanılabilir. Kullanıcılar işaretli özellikleri göremez veya erişemez.

- **Gerekli parola türü**: Cihaz için gerekli parola türünü tanımlayın. Seçenekleriniz şunlardır:
  - **Cihaz varsayılanı**
  - **Parola gerekli, kısıtlama yok**
  - **Zayıf biyometrik**: [güçlü ve zayıf Biyometri](https://android-developers.googleblog.com/2018/06/better-biometrics-in-android-p.html) (Android 'in Web sitesini açar)
  - **Sayısal**: parola yalnızca sayı olmalıdır, örneğin `123456789`. Kullanıcının girmesi gereken **parolanın uzunluk alt sınırını** girin (4 ile 16 karakter arasında).
  - **Sayısal karmaşık**: "1111" veya "1234" gibi yinelenen veya ardışık numaralara izin verilmiyor. Kullanıcının girmesi gereken **parolanın uzunluk alt sınırını** girin (4 ile 16 karakter arasında).
  - **Alfabetik**: alfabedeki harfler gereklidir. Rakamlar ve simgeler zorunlu tutulmaz. Kullanıcının girmesi gereken **parolanın uzunluk alt sınırını** girin (4 ile 16 karakter arasında).
  - **Alfasayısal**: büyük harfler, küçük harfler ve sayısal karakterler içerir. Kullanıcının girmesi gereken **parolanın uzunluk alt sınırını** girin (4 ile 16 karakter arasında).
  - **Simgelerle alfasayısal**: büyük harfler, küçük harfler, sayısal karakterler, noktalama işaretleri ve semboller içerir. Şunları da girin:

    - **Minimum parola uzunluğu**: parolanın, 4 ile 16 karakter arasında olması gereken minimum uzunluğu girin.
    - **Gerekli karakter sayısı**: parolanın, 0 ile 16 karakter arasında olması gereken karakter sayısını girin.
    - **Gereken küçük harfli karakter sayısı**: parolanın, 0 ile 16 karakter arasında olması gereken küçük harfli karakter sayısını girin.
    - **Gerekli olan büyük harfli karakter sayısı**: parolanın, 0 ile 16 karakter arasında olması gereken büyük harfli karakter sayısını girin.
    - **Gerekli harf olmayan karakter sayısı**: parolanın, 0 ile 16 karakter arasında olması gereken harf olmayan karakter sayısını (alfabedeki harfler dışında bir şey) girin.
    - **Gerekli sayısal karakter sayısı**: parolanın 0 ile 16 karakter arasında olması gereken sayısal karakter sayısını (`1`, `2`, `3`vb.) girin.
    - **Gerekli simge karakter sayısı**: parolanın 0 ile 16 karakter arasında olması gereken simge karakterlerinin (`&`, `#`, `%`vb.) sayısını girin.

- **Parolanın süresi dolana kadar geçen gün sayısı**: cihaz parolasının değiştirilmesi gereken gün sayısını, 1-365 arasında girin. Örneğin parolanın 60 gün sonra değiştirilmesi için `60` girin. Parola geçerlilik süresi dolduğunda kullanıcıların yeni bir parola oluşturması istenir.
- **Kullanıcının bir parolayı yeniden kullanabilmesi için gereken parola sayısı**: 1-24 arasında yeniden kullanılamayacak son parola sayısını girin. Son kullanıcının daha önce kullanılmış parolalar oluşturmasını önlemek için bu ayarı kullanın.
- **Cihaz silinmeden önceki oturum açma hatalarının sayısı**: cihaz temizlenmeden önce izin verilen başarısız oturum açma işlemlerinin sayısını (4-11) girin.

### <a name="power-settings"></a>Güç ayarları

- **Kilit süresi ekranı**: bir kullanıcının cihaz kilitlenmeden önce ayarlayabilen en uzun süreyi girin. Örneğin, bu ayarı **10 dakika**olarak ayarlarsanız, kullanıcılar süreyi 15 saniye ila 10 dakikaya ayarlayabilir. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya denetlemez.

- **Cihaz prize takılıyken ekran açık**: Cihaz prize takılıyken hangi güç kaynaklarının ekranın açık kalmasına neden olacağını seçin.

### <a name="users-and-accounts-settings"></a>Kullanıcılar ve Hesaplar ayarları

- **Yeni kullanıcı ekle**: Kullanıcıların yeni kullanıcı eklemesini önlemek için **Engelle** olarak ayarlayın. Her kullanıcının cihazda özel giriş ekranları, hesaplar, uygulamalar ve ayarlar için kişisel bir alanı vardır. **Yapılandırılmadı** (varsayılan), kullanıcıların cihaza diğer kullanıcıları eklemesine izin verir.
- **Kullanıcı kaldırma**: Kullanıcıların kullanıcı kaldırmasını önlemek için **Engelle** olarak ayarlayın. **Yapılandırılmadı** (varsayılan), kullanıcıların cihazdan diğer kullanıcıları kaldırmasına izin verir.
- **Hesap değişiklikleri** (yalnızca adanmış cihazlar): kullanıcıların hesapları değiştirmesini engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan), kullanıcıların cihazdaki kullanıcı hesaplarını güncelleştirmesine izin verir.

  > [!NOTE]
  > Bu ayar cihaz sahibi (tam yönetilen) cihazlarda kabul edilemez. Bu ayarı yapılandırırsanız, ayar yok sayılır ve herhangi bir etkisi yoktur.

- **Kişisel Google hesapları**: **Block** , kullanıcıların kişisel Google hesabını cihaza eklemesini engeller. **Yapılandırılmadı** (varsayılan), kullanıcıların kişisel Google hesabını eklemesine izin verir.

### <a name="applications"></a>Uygulamalar

- **Bilinmeyen kaynaklardan yüklemeye Izin ver**: kullanıcıların **Bilinmeyen kaynakları**açıp kullanabilmesi için **izin ver** ' i seçin. Bu ayar, uygulamaların Google Play Store dışındaki kaynaklar da dahil olmak üzere bilinmeyen kaynaklardan yüklenmesine izin verir. **Yapılandırılmamış** kullanıcıların açılmasını engeller **bilinmeyen kaynaklar**.
- **Google Play Store 'daki tüm uygulamalara erişime Izin ver**: **izin ver**olarak ayarlandığında, kullanıcılar Google Play deposundaki tüm uygulamalara erişim sağlar. [Istemci uygulamalarında](../apps/apps-add-android-for-work.md)yönetici blokları olan uygulamalara erişim almaz. **Yapılandırılmadı** , kullanıcıları yalnızca yöneticinin kullanılabilir Google Play depolama alanı veya [istemci uygulamalarında](../apps/apps-add-android-for-work.md)gerekli uygulamalar üzerinde yaptığı uygulamalara erişmesine zorlar.
- **Otomatik uygulama güncelleştirmeleri**: Otomatik Güncelleştirmeler yüklü olduğunda seçin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı**
  - **Kullanıcı Seçimi**
  - **hiçbir zaman**
  - **Wi-Fi yalnızca**
  - **Her zaman**

### <a name="connectivity"></a>Bağlantı

- **Her Zaman Açık VPN**: Bir VPN istemcisini VPN'ye otomatik olarak bağlanmak ve yeniden bağlanmak üzere ayarlamak için **Etkinleştir**'i seçin. Her Zaman Açık VPN bağlantıları; kullanıcı cihazı kilitlediğinde, cihaz yeniden başlatıldığında veya kablosuz ağ değiştiğinde bağlı durumda kalır veya hemen bağlanır. 

  Her zaman açık VPN'yi tüm VPN istemcilerinde devre dışı bırakmak için **Yapılandırılmadı**'yı seçin.

  > [!IMPORTANT]
  > Bir cihaza yalnızca bir tane Her Zaman Açık VPN ilkesi dağıttığınızdan emin olun. Bir cihaza birden çok Her Zaman Açık VPN ilkesi dağıtma desteklenmez.

- **VPN istemcisi**: Her Zaman Açık'ı destekleyen bir VPN istemcisini seçin. Seçenekleriniz şunlardır:
  - Cisco AnyConnect
  - F5 Access
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Özel
    - **Paket kimliği**: Google Play mağazasına uygulamanın paket kimliğini girin. Örneğin Play mağazasındaki uygulamanın URL'si `https://play.google.com/store/details?id=com.contosovpn.android.prod` ise, paket kimliği `com.contosovpn.android.prod` olur.

  > [!IMPORTANT]
  > - Seçtiğiniz VPN istemcisinin cihaza yüklenmesi ve cihazın uygulama başına VPN iş profillerini desteklemesi gerekir. Aksi takdirde bir hata oluşur. 
  > - VPN istemci uygulamasını yine de **Yönetilen Google Play Mağazası**'nda onaylamanız, uygulamayı Intune ile eşitlemeniz ve cihaza dağıtmanız gerekir. Bu yapıldıktan sonra uygulama kullanıcının iş profiline yüklenir.
  > - Bilinen sorunlar vardır uygulama başına VPN Android 3.0.4 için F5'e erişim ile kullanırken. Bkz: [Android 3.0.4 için F5'e erişim için F5'ın sürüm notları](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android) daha fazla bilgi için.

- **Kilitleme modu**: tüm ağ trafiğinin VPN tüneli kullanmasını zorlamak için **Etkinleştir** ' i seçin. VPN'e bir bağlantı oluşturulmazsa, cihazın ağ erişimi olmaz.

  Trafiğin VPN tünelinden veya mobil ağdan akmasına izin vermek için **Yapılandırılmadı**'yı seçin.

- **Önerilen küresel ara sunucu**: cihazlara genel bir proxy eklemek için **Etkinleştir** ' i seçin. Etkinleştirildiğinde, HTTP ve HTTPS trafiği, cihazdaki bazı uygulamalar dahil olmak üzere girdiğiniz proxy 'yi kullanır. Bu proxy yalnızca bir önerimiz. Bazı uygulamalar proxy kullanmaz. **Yapılandırılmadı** (varsayılan) önerilen küresel ara sunucu eklemez.

  Bu özellik hakkında daha fazla bilgi için bkz. [setRecommendedGlobalProxy](https://developer.android.com/reference/android/app/admin/DevicePolicyManager.html#setRecommendedGlobalProxy(android.content.ComponentName,%20android.net.ProxyInfo)) (bir Android sitesi açar).

  Etkinleştirildiğinde, proxy **türünü** de girin. Seçenekleriniz şunlardır:

  - **Doğrudan**: proxy sunucu ayrıntılarını el ile girmek için bu seçeneği belirleyin, örneğin:
    - **Ana bilgisayar**: proxy sunucunuzun ana bilgisayar adını veya IP adresini girin. Örneğin `proxy.contoso.com` veya `127.0.0.1` girin.
    - **Bağlantı noktası numarası**: proxy sunucusu tarafından kullanılan TCP bağlantı noktası numarasını girin. Örneğin, şunu girin: `8080`.
    - **Dışlanan konaklar**: proxy 'yi kullanmayan konak ADLARıNıN veya IP adreslerinin bir listesini girin. Bu liste, boşluk olmadan bir yıldız işareti (`*`) joker karakteri ve noktalı virgülle (`;`) ayrılmış birden çok Konağı içerebilir. Örneğin, şunu girin: `127.0.0.1;web.contoso.com;*.microsoft.com`.

  - **Proxy otomatik yapılandırma**: bir proxy otomatik yapılandırma betiğine **Pac URL 'sini** girin. Örneğin, şunu girin: `https://proxy.contoso.com/proxy.pac`.

    PAC dosyaları hakkında daha fazla bilgi için bkz. [proxy otomatik yapılandırma (PAC) dosyası](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (Microsoft dışı bir site açar).

## <a name="work-profile-only"></a>Yalnızca iş profili

Bu ayarlar, Intune 'un yalnızca bir kişisel veya kendi cihazındaki (BYOD) Android kurumsal Iş profili kaydı gibi Iş profilini denetlediği Android kurumsal kayıt türleri için geçerlidir.

### <a name="work-profile-settings"></a>İş profili ayarları

#### <a name="general"></a>Genel

- **İş ve Kişisel Profiller arasında kopyalama ve yapıştırma**: seçin **blok** Kopyala ve Yapıştır iş ve kişisel uygulamalar arasında önlemek için. **Yapılandırılmamış** kullanıcıların kişisel profildeki uygulamalarla kopyalama ve yapıştırma kullanarak veri paylaşmasına izin verir 
- **İş ve Kişisel Profiller arasında veri paylaşımı**: iş profilindeki uygulamalar kişisel profildeki uygulamalarla paylaşıp seçin. Örneğin, uygulamalar içindeki paylaşma eylemler gibi denetleyebilirsiniz **Paylaş...** seçeneği gibi uygulamalardaki paylaşma eylemlerini denetler. Bu ayar, kopyala/yapıştır pano davranışında geçerli değildir. Paylaşım Seçenekleriniz şunlardır:
  - **Cihaz varsayılanı**: cihaz, Android sürümüne bağlı olarak farklılık gösteren varsayılan paylaşım davranışıdır. Kişisel profilden iş profiline paylaşmaya varsayılan olarak izin verilir. Buna karşın iş profilinden kişisel profile paylaşma varsayılan olarak engellenir. Bu ayar, iş profilinden kişisel profile veri paylaşılmasını önler. Sürüm 6.0 ve üzerini çalıştıran cihazlarda Google kişisel profilden iş profiline paylaşımı engellemez.
  - **İş profilindeki uygulamalar kişisel profilden gelen paylaşım isteklerini işleyebilir**: Kişisel profilden iş profiline paylaşıma izin veren yerleşik Android özelliğini etkinleştirir. Etkinleştirildiğinde, kişisel profildeki bir uygulamadan gelen bir paylaşım isteği, iş profilindeki uygulamalarla paylaşım kullanabilir. Bu ayar, 6.0 öncesi sürümleri çalıştıran Android cihazlarının varsayılan davranışıdır.
  - **Sınırlar arasında tüm paylaşımları engelle**: iş ve kişisel profiller arasında paylaşmayı engeller.
  - **Paylaşımda kısıtlama yok**: iş profili sınırları genelinde her iki yönde paylaşımı mümkün değildir. Bu ayarı seçtiğinizde, iş profilinizdeki uygulamalar kişisel profildeki rozetsiz uygulamalar ile veri paylaşabilir. Bu ayar iş profilindeki yönetilen uygulamaların cihazın yönetilmeyen kısmındaki uygulamalarla paylaşmasına izin verir. Bu nedenle bu ayarı dikkatli kullanın.

- **Cihaz kilitliyken iş profili bildirimleri**: cihaz kilitliyken iş profilindeki uygulamalar verileri bildirimleri görüntüleyebilirsiniz olup olmadığını denetler. **Blok** verileri göstermez. **Yapılandırılmamış** verileri gösterir.
- **Varsayılan uygulama izinleri**: İş profilindeki tüm uygulamalar için varsayılan izin ilkesini ayarlar. Android 6 ile başlayarak, kullanıcıdan, belirli uygulamalar açıldığında bunlar için gereken bazı izinleri vermesi istenir. Bu ilke ayarı, kullanıcıdan iş profilindeki tüm uygulamalar için izin istenip istenmeyeceğini belirlemenize olanak tanır. Örneğin, iş profiline konum erişimi gerektiren bir uygulama atarsınız. Normalde bu uygulama kullanıcıdan konum erişimini onaylamasını veya reddetmesini ister. Bu ilkeyi istem kullanmadan otomatik olarak izinler vermek, izin vermeyi reddetmek veya kararı kullanıcıya bırakmak için kullanabilirsiniz. Aşağıdakilerden birini seçin:
  - **Cihaz varsayılanı**
  - **Sor**
  - **Otomatik olarak izin ver**
  - **Otomatik olarak reddet**

  Ayrıca tek tek uygulamalara izinler vermek için bir Uygulama Yapılandırma ilkesi de kullanabilirsiniz (**İstemci Uygulamaları** > **Uygulama yapılandırma ilkeleri**).

- **Hesap ekleme ve kaldırma**: seçin **blok** son kullanıcıların, el ile eklemek veya iş profilinde hesaplarının kaldırılmasını önlemek için. Örneğin, Gmail uygulamasını bir Android iş profiline dağıttığınızda, son kullanıcıların bu iş profiline hesap eklemesini veya buradan kaldırmasını engelleyebilirsiniz. **Yapılandırılmamış** iş profilinde hesap ekleme sağlar.  

- **Bluetooth ile kişi paylaşımı**: Bluetooth kullanarak eşleştirilmiş bir cihazdan, örneğin araba, iş kişilerine erişime izin verir. Bu ayar varsayılan olarak yapılandırılmamıştır ve iş profili kişileri gösterilmez. Bu paylaşıma izin verip iş profili kişilerini görüntülemek için **Etkinleştir**’i seçin. Bu ayar, Android OS v6.0 ve üzeri sürümlerde Android iş profili cihazları için geçerlidir. Bu ayarı etkinleştirmek, bazı Bluetooth cihazlarının ilk bağlantı sırasında iş kişilerini önbelleğe almasına izin verebilir. İlk eşleme/eşitleme sonrasına bunu devre dışı bırakmak ise Bluetooth cihazından iş kişilerini kaldırmayabilir.

- **Ekran Yakalama**: seçin **blok** iş profili olan cihazlarda ekran veya ekran görüntüleri önlemek için. Ayrıca güvenli bir video çıkışına sahip olmayan görüntü cihazlarında gösterilen içeriği engeller. **Yapılandırılmamış** ekran görüntüleri alma sağlar.

- **Kişisel profilde iş kişisi arayan kimliğini görüntüleme**: etkinleştirildiğinde (**yapılandırılmadı**), iş kişisi arayan ayrıntıları kişisel profilde görüntülenir. Ayarlandığında **blok**, iş kişisi arayan numarası kişisel profilde görüntülenmez. Android işletim sistemi v6.0 ve daha yeni sürümlerde geçerlidir.

- **Kişisel profilden iş kişilerini arayın**: seçin **blok** kullanıcılar, kişisel profildeki uygulamalar iş kişileri arama yapmasını önlemek için. **Gerekli değil** iş kişilerini Kişisel profildeki arama sağlar.

- **Kamera**: seçin **blok** iş profili olan cihazda kamerayı erişimi engellemek için. Kişisel taraftaki kamera, bu ayardan etkilenmez. **Gerekli değil** iş profilinde kameraya erişim sağlar.

- **İş profili uygulamalarından Pencere öğelerinin oluşturulmasına Izin ver**: **Etkinleştir** ayarı, son kullanıcıların ana ekranda uygulamalar tarafından sunulan pencere öğelerini almasına izin verir. **Yapılandırılmadı** (varsayılan) ayarı, bu özelliği devre dışı bırakır.

  Örneğin, Outlook kullanıcılarınızın iş profillerine yüklendi. **Etkin**olarak ayarlandığında, kullanıcılar gündem pencere öğesini cihaz giriş ekranına yerleştirebilir.

#### <a name="work-profile-password"></a>İş profili parolası

- **İş Profili Parolası Gerektir**: İş profilinin etkinleştirildiği Android 7.0 ve üzerine uygulanır. Seçin **gerektiren** yalnızca iş profilindeki uygulamalar için geçerli bir geçiş kodu ilkesi girmek için. Varsayılan olarak, son kullanıcı birbirinden ayrı tanımlanmış iki PIN kullanabilir veya PIN’leri iki PIN'den daha güçlü olanın altında birleştirmeyi seçebilir. **Yapılandırılmamış** iş uygulamaları, parola girmeden kullanmasına izin verir.
- **En düşük parola uzunluğu**: Kullanıcı parolalarında olması gereken en düşük rakam veya karakter sayısını **4**-**16** arasından belirtin.
- **İş profili kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı**: İş profili kilitlenmeden önce geçmesi gereken süreyi seçin. Daha sonra kullanıcının kimlik bilgilerini girerek tekrar erişim kazanması gerekir.
- **Cihaz silinmeden önceki oturum açma hatası sayısı**: İş profili cihazdan silinmeden önce girilebilecek hatalı parola sayısını girin.
- **Parola kullanım süresi sonu (gün)** : Son kullanıcı parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını girin (**1**-**255** arası).
- **Gerekli parola türü**: Cihazda ayarlanması gereken parola türünü seçin. Aşağıdakilerden birini seçin:
  - **Cihaz varsayılanı**
  - **Düşük güvenlik biyometriği**
  - **Gerekli**
  - **En az sayısal**
  - **Sayısal karmaşık**: '1111' veya '1234' gibi yinelenen veya ardışık numaralara izin verilmez
  - **En az alfabetik**
  - **En az alfasayısal**
  - **En az simgeler ile alfasayısal**
- **Önceki parolaların yeniden kullanılmasını engelle**: Eski bir parolanın yeniden kullanılabilmesi için kullanılmış olması gereken yeni parola sayısını girin (**1**-**24** arası).
- **Parmak iziyle kilit açma**: seçin **blok** son kullanıcılar cihazın kilidini açmak için cihazın parmak izi tarayıcısını kullanmasını önlemek için. **Yapılandırılmamış** kullanıcıların cihazların iş profilindeki bir parmak izi ile kilit açma olanak sağlar.
- **Akıllı kilit ve diğer güven aracıları**: seçin **blok** ayarlaması kilit ekranı ayarları uyumlu cihazlarda akıllı kilit veya diğer güven aracılarının önlemek için. Güven aracısı olarak da bilinen bu özellik, cihaz güvenilir bir konumdayken cihaz kilidi ekran parolasını devre dışı bırakmanıza veya atlamanıza izin verir. Örneğin cihaz belirli bir Bluetooth cihazına bağlıyken ya da bir NFC etiketinin yakınındayken iş profili parolasını atlama. Bu ayarı, kullanıcıların Akıllı Kilit'i yapılandırmasını önlemek için kullanın.

### <a name="device-password"></a>Cihaz parolası

Bu parola ayarlar, bir iş profili kullanan cihazlardaki kişisel profiller için geçerlidir.

- **En düşük parola uzunluğu**: Kullanıcı parolalarında olması gereken en düşük rakam veya karakter sayısını **4**-**14** arasından belirtin.
- **Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı**: Etkin olmayan bir cihaz otomatik olarak kilitlenmeden önce geçmesi gereken süreyi seçin
- **Cihaz silinmeden önceki oturum açma hatası sayısı**: Tüm veriler cihazdan silinmeden önce girilebilecek hatalı parola sayısını girin
- **Parola kullanım süresi sonu (gün)** : Son kullanıcı parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını girin (**1**-**255** arası)
- **Gerekli parola türü**: Cihazda ayarlanması gereken parola türünü seçin. Aşağıdakilerden birini seçin:
  - **Cihaz varsayılanı**
  - **Düşük güvenlik biyometriği**
  - **Gerekli**
  - **En az sayısal**
  - **Sayısal karmaşık**: '1111' veya '1234' gibi yinelenen veya ardışık numaralara izin verilmez
  - **En az alfabetik**
  - **En az alfasayısal**
  - **En az simgeler ile alfasayısal**
- **Önceki parolaların yeniden kullanılmasını engelle**: Eski bir parolanın yeniden kullanılabilmesi için kullanılmış olması gereken yeni parola sayısını girin (**1**-**24** arası).
- **Parmak iziyle kilit açma**: seçin **blok** son kullanıcı, cihazın kilidini açmak için cihazın parmak izi tarayıcısını kullanmasını önlemek için. **Yapılandırılmadı** ayarı, kullanıcının cihaz kilidini parmak izi kullanarak açmasını sağlar.
- **Akıllı kilit ve diğer güven aracıları**: seçin **blok** ayarlaması kilit ekranı ayarları uyumlu cihazlarda akıllı kilit veya diğer güven aracılarının önlemek için. Güven aracısı olarak da bilinen bu özellik, cihaz güvenilir bir konumdayken cihaz kilidi ekran parolasını devre dışı bırakmanıza veya atlamanıza izin verir. Örneğin cihaz belirli bir Bluetooth cihazına bağlıyken ya da bir NFC etiketinin yakınındayken iş profili parolasını atlama. Bu ayarı, kullanıcıların Akıllı Kilit'i yapılandırmasını önlemek için kullanın.

### <a name="system-security"></a>Sistem güvenliği

- **Uygulamalarda tehdit taraması**: **gerektiren** , zorlar **uygulamaları doğrula** iş ve kişisel profiller için seçeneği etkinleştirilmiştir.

   > [!Note]
   > Bu ayar yalnızca Android 8 (Oreo) ve üzeri cihazlar için geçerlidir.

- **Kişisel profilde bilinmeyen kaynaklardan uygulama yüklemelerini engelleyin**: tasarım, Android kurumsal iş profili cihazları Play Store dışındaki kaynaklardan uygulama yükleyemez. Doğası gereği, iş profili cihazlarının çift profil olması amaçlanmıştır:

  - MDM kullanılarak yönetilen bir iş profili.
  - MDM yönetiminden yalıtılmış bir kişisel profil.

  Bu ayar, yöneticilerin bilinmeyen kaynaklardan uygulama yüklemelerinin daha fazla denetimine erişmesini sağlar. **Yapılandırılmadı** (varsayılan), kişisel profilde bilinmeyen kaynaklardan uygulama yüklemelerine izin verir. **Block** , kişisel profildeki Play Store dışındaki kaynaklardan uygulama yüklemelerinin yapılmasını engeller.

### <a name="connectivity"></a>Bağlantı

- **Her Zaman Açık VPN**: Bir VPN istemcisini VPN'ye otomatik olarak bağlanmak ve yeniden bağlanmak üzere ayarlamak için **Etkinleştir**'i seçin. Her Zaman Açık VPN bağlantıları; kullanıcı cihazı kilitlediğinde, cihaz yeniden başlatıldığında veya kablosuz ağ değiştiğinde bağlı durumda kalır veya hemen bağlanır. 

  Her zaman açık VPN'yi tüm VPN istemcilerinde devre dışı bırakmak için **Yapılandırılmadı**'yı seçin.

  > [!IMPORTANT]
  > Bir cihaza yalnızca bir tane Her Zaman Açık VPN ilkesi dağıttığınızdan emin olun. Bir cihaza birden çok Her Zaman Açık VPN ilkesi dağıtma desteklenmez.

- **VPN istemcisi**: Her Zaman Açık'ı destekleyen bir VPN istemcisini seçin. Seçenekleriniz şunlardır:
  - Cisco AnyConnect
  - F5 Access
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Özel
    - **Paket kimliği**: Google Play mağazasına uygulamanın paket kimliğini girin. Örneğin Play mağazasındaki uygulamanın URL'si `https://play.google.com/store/details?id=com.contosovpn.android.prod` ise, paket kimliği `com.contosovpn.android.prod` olur.

  > [!IMPORTANT]
  > - Seçtiğiniz VPN istemcisinin cihaza yüklenmesi ve cihazın uygulama başına VPN iş profillerini desteklemesi gerekir. Aksi takdirde bir hata oluşur. 
  > - VPN istemci uygulamasını yine de **Yönetilen Google Play Mağazası**'nda onaylamanız, uygulamayı Intune ile eşitlemeniz ve cihaza dağıtmanız gerekir. Bu yapıldıktan sonra uygulama kullanıcının iş profiline yüklenir.
  > - Bilinen sorunlar vardır uygulama başına VPN Android 3.0.4 için F5'e erişim ile kullanırken. Bkz: [Android 3.0.4 için F5'e erişim için F5'ın sürüm notları](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android) daha fazla bilgi için.

- **Kilitleme modu**: tüm ağ trafiğinin VPN tüneli kullanmasını zorlamak için **Etkinleştir** ' i seçin. VPN'e bir bağlantı oluşturulmazsa, cihazın ağ erişimi olmaz.

  Trafiğin VPN tünelinden veya mobil ağdan akmasına izin vermek için **Yapılandırılmadı**'yı seçin.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).

Ayrıca, [Android](device-restrictions-android.md#kiosk) ve [Windows 10](kiosk-settings.md) cihazları için adanmış cihaz bilgi noktası profilleri oluşturabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz:

[Microsoft Intune Android kurumsal cihazlarını yapılandırma ve sorunlarını giderme](https://support.microsoft.com/help/4476974)
