---
title: Android Kurumsal cihaz ayarları Microsoft Intune - Azure | Microsoft Docs
description: Android Kurumsal veya Android for Work cihazlar, cihazın ayarlarını kısıtlamak, dahil olmak üzere kopyalama ve yapıştırma, bildirimleri, uygulama izinleri, veri paylaşımı, parola uzunluğu, Göster başarısız oturum açma, yeniden parolalar, kilidini açmak için parmak izi'ni kullanın ve bluetooth etkinleştir Work kişileriyle paylaşma. Cihazları tek bir uygulama ya da birden fazla uygulama çalıştırmak için adanmış cihaz bilgi noktası yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/05/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: fc91fc685c28beff38dc395dd83b60e99343af57
ms.sourcegitcommit: 2545ffb75b8d9290718d3a67acdcbea2f279090f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2019
ms.locfileid: "67263690"
---
# <a name="android-enterprise-device-settings-to-allow-or-restrict-features-using-intune"></a>İzin vermek veya Intune kullanarak özellikleri kısıtlamak için android Kurumsal cihaz ayarları

Bu makalede, listeler ve Android Kurumsal cihazlarda denetleyebileceğiniz farklı ayarlar açıklanır. Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, izin vermek veya özellikleri, çalışma uygulamaları ayrılmış cihazları, güvenlik denetimi ve daha fazlası devre dışı bırakmak için bu ayarları kullanın.

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz yapılandırma profili oluşturma](device-restrictions-configure.md).

## <a name="device-owner-only"></a>Yalnızca cihaz sahibi

### <a name="general-settings"></a>Genel ayarlar

- **Ekran yakalama**: Cihazda ekran görüntülerini veya ekran yakalamalarını önlemek için **Engelle**'yi seçin. Ayrıca güvenli bir video çıkışına sahip olmayan görüntü cihazlarında gösterilen içeriği engeller. **Yapılandırılmamış** kullanıcının ekran içeriğini resim olarak yakalamasına izin verir.
- **Kamera**: Cihazdaki kameraya erişim sağlanmasını engellemek için **Engelle**'yi seçin. **Gerekli değil** cihazın kamerasını erişmesini sağlar.
- **Varsayılan izin ilkesini**: Bu ayar, çalışma zamanı izinleri istekleri için varsayılan izin ilkesini tanımlar. Olası değerler şöyledir:
  - **Cihaz varsayılanı**: Cihazın varsayılan ayarı kullanın.
  - **Komut İstemi**: Kullanıcının izni onaylamanız istenir.
  - **Otomatik olarak izin ver**: İzinler otomatik olarak verilir.
  - **Otomatik olarak Reddet**: İzinleri otomatik olarak reddedilir.
- **Tarih ve saat değişikliklerini**: Seçin **blok** kullanıcıların el ile tarih ve saat ayarından önlemek için. **Yapılandırılmamış** ayarlanmış tarih ve saat için kullanıcıların cihazda izin verir.
- **Birim değişiklikleri**: Seçin **blok** kullanıcıların cihazın toplu değiştirmesini önlemek için. **Yapılandırılmamış** cihazda birim ayarlarını kullanımına izin verir.
- **Fabrika sıfırlaması**: Seçin **blok** sıfırlama seçeneği cihazın Ayarları'nda kullanıcıların Fabrika kullanmasını önlemek için. **Yapılandırılmamış** Bu ayar cihazda kullanmasına olanak tanır.
- **Güvenli Önyükleme**: Seçin **blok** kullanıcıların cihaz Modu'nda yeniden başlatılmasını önlemek için. **Yapılandırılmamış** kullanıcılar güvenli modda cihazın yeniden başlatılmasına izin verir.
- **Durum çubuğu**: Seçin **blok** durum çubuğu, bildirimler ve hızlı ayarlar dahil olmak üzere erişimi engellemek için. **Yapılandırılmamış** kullanıcıların durum çubuğuna erişimi sağlar.
- **Veri Hizmetleri**: Cep telefonu şebekesi üzerinden veri dolaşımını önlemek için **Engelle**'yi seçin. **Yapılandırılmamış** cihaz hücresel ağ kullanırken veri dolaşımına izin verir.
- **Wi-Fi ayar değişiklikleri**: Seçin **blok** kullanıcıların cihaz sahibi tarafından oluşturulan Wi-Fi ayarları değiştirmesini önlemek için. Kullanıcılar kendi Wi-Fi yapılandırmalarını oluşturabilir. **Yapılandırılmamış** kullanıcıların cihazda Wi-Fi ayarlarını değiştirmesine olanak tanır.
- **Wi-Fi erişim noktası yapılandırması**: Seçin **blok** kullanıcıların oluşturma veya herhangi bir Wi-Fi yapılandırması değiştirmesini önlemek için. **Yapılandırılmamış** kullanıcıların cihazda Wi-Fi ayarlarını değiştirmesine olanak tanır.
- **Bluetooth yapılandırma**: Seçin **blok** kullanıcıların cihazda Bluetooth yapılandırmasını önlemek için. **Yapılandırılmamış** cihazda Bluetooth'un kullanımına izin verir.
- **İnternet paylaşımı ve erişimi noktalarına**: Seçin **blok** taşınabilir etkin noktalarına internet paylaşımı ve erişimi önlemek için. **Yapılandırılmamış** internet paylaşımı ve taşınabilir noktalarına erişim sağlar.
- **USB depolamasını**: Seçin **izin** cihazdaki USB depolama erişim için. **Yapılandırılmamış** USB depolama alanına erişimini engeller.
- **USB dosya aktarımı**: Seçin **blok** önlemek için USB üzerinden dosyaları aktarma. **Yapılandırılmamış** dosyaları aktarma sağlar.
- **Dış medya**: Seçin **blok** kullanarak veya CİHAZDAN Dış medya bağlanma önlemek için. **Yapılandırılmamış** Dış medya cihazda izin verir.
- **NFC kullanarak verileri ışın**: Seçin **blok** yakın alan iletişimi (NFC) teknolojisini kullanarak ışını veri uygulamalardan önlemek için. **Yapılandırılmamış** cihazlar arasında veri paylaşımı için NFC kullanımına izin verir.
- **Hata ayıklama özellikleri**: Seçin **izin** kullanıcıların cihazda hata ayıklama özelliklerini kullanın. **Yapılandırılmamış** kullanıcıların cihazda hata ayıklama özelliklerini kullanmasını önler.
- **Mikrofon Ayarlama**: Seçin **blok** mikrofonun sesinin açılmasını ve mikrofon ses kullanıcıların önlemek için. **Yapılandırılmamış** kullanma ve cihazda mikrofon ses ayarlamak izin verir.
- **Fabrika ayarlarına sıfırlama koruması e-postaları**: Seçin **Google hesabı e-posta adresleri**. Bunu temizlendikten sonra cihazın kilidini açmak cihaz yöneticilerinin e-posta adreslerini girin. E-posta adresi gibi bir noktalı virgül ile ayırın mutlaka `admin1@gmail.com;admin2@gmail.com`. E-posta değil girdiyseniz, fabrika ayarlarına geri yüklendikten sonra herkes cihazın kilidini açabilirsiniz. Bu e-postaları, yalnızca kullanıcı olmayan Fabrika sıfırlaması çalıştığı zaman kurtarma menüsünü kullanarak bir Fabrika sıfırlaması çalışıyor gibi uygulanır.
- **Ağ kaçış noktası**: Seçin **etkinleştirme** ağ kaçış tarama özelliğini etkinleştirmek kullanıcılara izin vermek için. Cihaz önyüklendiğinde bir ağ bağlantısı olmayan yaptıysanız, kaçış noktası geçici olarak bir ağa bağlayın ve cihaz ilkesini yenilemek sorar. Bu ilke uygulandıktan sonra geçici ağ unutulur ve cihaz önyüklemeye devam eder. Bu özellik, cihazları ağa bağlanır:
  - Son ilkede uygun bir ağ yok.
  - Cihaz uygulama kilidi görev modunda önyüklenir.
  - Kullanıcı cihaz ayarları ulaşamıyor.

  **Yapılandırılmamış** kullanıcıların cihazdaki ağ kaçış tarama özelliği kapatmasını engeller.

- **Sistem Güncelleştirmesi**: Cihaz havadan güncelleştirmeler nasıl işlediğini tanımlamak için bir seçenek belirleyin:
  - **Cihaz varsayılanı**: Cihazın varsayılan ayarı kullanın.
  - **Otomatik**: Güncelleştirmeler, kullanıcı etkileşimi olmadan otomatik olarak yüklenir. Bu ilkeyi seçmek, bekleyen tüm güncelleştirmeleri hemen yükler.
  - **Ertelenen**: Güncelleştirmeleri 30 gün boyunca Ertelenen. 30 günün sonunda, Android güncelleştirmeyi yüklemek için kullanıcıya sorar. Cihaz üreticilerin veya taşıyıcıların önemli güvenli güncelleştirmelerinin ertelenmesini engellemek (muaf tutmak) mümkündür. Muaf tutulan bir güncelleştirme cihazda kullanıcıya bir sistem bildirimi gösterir. 
  - **Bakım penceresi**: Intune ile ayarlanan günlük bakım penceresi sırasında güncelleştirmeleri otomatik olarak yükler. Yükleme 30 gün boyunca her gün çalışır ve yeterli alan veya pil düzeyleri varsa başarısız olabilir. 30 gün sonra kullanıcıyı uygulamayı yüklemek için Android ister. Bu pencere ayrıca Oynatma uygulamalarının güncelleştirmelerini yüklemek için de kullanılır. Tek uygulama adanmış cihaz ön plan uygulamaları güncelleştirilebilir gibi gibi bilgi noktaları, adanmış cihazlar için bu seçeneği kullanın.

- **Bildirim windows**: Ayarlandığında **devre dışı**, pencere bildirimleri toasts, gelen çağrıları, giden çağrıları, sistem uyarıları ve sistem hataları dahil olmak üzere, cihazda gösterilmez. Ayarlandığında **yapılandırılmadı**, işletim sistemi varsayılan, olabilecek bildirimleri göstermek için kullanılır.
- **Atla ipuçları lk**: Seçin **etkinleştirme** gizleme veya uygulamalardan eğitimlerle adım veya uygulama başlatıldığında tanıtım açıklanmıyorsa okumak için öneriler atlayın. Ayarlandığında **yapılandırılmadı**, işletim sistemi varsayılan, olabilecek uygulama başlatıldığında bu önerileri göstermek için kullanılır.

### <a name="system-security-settings"></a>Sistem güvenliği ayarları

- **Uygulamalarda tehdit taraması**: **Gerekli** (varsayılan), Google Play uygulamaları önce ve bunlar yüklendikten sonra taramak koruması sağlar. Tehdit tespit ederse, kullanıcı uygulamayı CİHAZDAN kaldırmak için uyar. **Yapılandırılmamış** değil etkinleştirin veya Google Play uygulamaları için Koruması'nı çalıştırın.

### <a name="dedicated-device-settings"></a>Özel cihaz ayarları

Bilgi noktası stili deneyimi adanmış cihazlarınızı yapılandırmak için bu ayarları kullanın. Bir uygulamayı çalıştırmak için bir cihazı yapılandırın veya birçok uygulaması çalıştırın. Yalnızca eklediğiniz uygulamalar bir cihaz bilgi noktası modu ile ayarlandığında kullanılabilir. Bu ayarları Android ayrılmış Kurumsal cihazlar için geçerlidir. Bunlar, tam olarak yönetilen Android Enterprise cihazlar için geçerli değildir.

**Bilgi noktası modu**: Cihaz çalışırken bir veya birden fazla uygulama çalıştıran seçin.

- **Tek uygulama**: Kullanıcılar yalnızca tek bir uygulama cihazda erişebilir. Cihaz başlatıldığında, yalnızca belirli uygulamayı başlatır. Kullanıcılar yeni uygulamalar açamaz veya çalışan uygulamayı değiştiremez.

  **Adımları**
  1. Seçin **bir yönetilen uygulama seçin**, yönetilen Google Play uygulaması listeden seçin. 

      Ardından, listelenen tüm uygulamalar yoksa [bazı Android uygulamaları ekleme](apps-add-android-for-work.md) cihaza. Mutlaka [adanmış cihazlarınız için oluşturduğunuz cihaz grubuna uygulama atamak](apps-deploy.md).

  2. Seçin **Tamam** > **Tamam** seçerek uygulamayı ekleyin.

- **Çoklu uygulama**: Cihazdaki uygulamalar sınırlı sayıda kullanıcıları erişebilir. Cihaz başlatıldığında, yalnızca eklediğiniz uygulamalar başlatın. Ayrıca, kullanıcılar açabilir bazı web bağlantıları da ekleyebilirsiniz. İlkenin geçerli olduğu kullanıcı giriş ekranında simgeleri için izin verilen uygulamalar görürsünüz.

  > [!IMPORTANT]
  > Cihazlar, çoklu uygulama için ayrılmış [giriş ekranı yönetilen uygulama](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise) Google play'den **olmalıdır**:
  >   - [Bir istemci uygulaması olarak eklenen](apps-add-android-for-work.md) ıntune
  >   - [Cihaz grubuna atanmış](apps-deploy.md) adanmış cihazlarınız için oluşturuldu
  > 
  > **Giriş ekranı yönetilen** uygulama yapılandırma profilinde de olması için gerekli değildir, ancak bir istemci uygulaması olarak eklenmesi için gereklidir. Zaman **giriş ekranı yönetilen** uygulama, bir istemci uygulaması olarak eklenir, simgeler olarak gösterilir yapılandırma profilinde de eklediğiniz diğer tüm uygulamalar **giriş ekranı yönetilen** uygulama. 
  >
  > Çoklu uygulama bilgi noktası modu giriş ekranı yönetilen kullanırken Çevirici/phone uygulamalarını düzgün çalışmayabilir. 

  - Seçin **Ekle**ve uygulamalarınızı listeden seçin.

    Varsa **giriş ekranı yönetilen** uygulama listelenmez, ardından [Google Play'den ekleme](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise). Mutlaka [uygulamayı atamak](apps-deploy.md) adanmış cihazlarınız için oluşturduğunuz cihaz grubuna.

    Ayrıca diğer ekleyebilirsiniz [Android uygulamaları](apps-add-android-for-work.md) ve [web uygulamaları](web-app.md) cihazla kuruluşunuz tarafından oluşturulmuş. Mutlaka [adanmış cihazlarınız için oluşturduğunuz cihaz grubuna uygulama atamak](apps-deploy.md).

  - **Sanal giriş düğmesi**: Seçin **etkinleştirme** adanmış cihazda giriş düğmesi gösterilecek. Kullanıcıların uygulamalar arasında kolayca geçiş yapabilirsiniz için bu onay kutusu seçildiğinde, cihazın giriş ekranına kullanıcı döndürür. Bazı Android cihazlarda, kullanıcıların giriş düğmesini göster ekranda yukarı a doğru çekin gerekebilir. **Devre dışı** kullanıcılar, uygulamalar arasında geçiş yapmak için geri düğmesini kullanmalısınız bir giriş düğmesi göstermez.
  - **Bilgi noktası modu bırakın**: Seçin **etkinleştirme** yöneticilerin bilgi noktası modu cihaz güncelleştirmek için geçici olarak duraklatmak sağlamak için. Yönetici bu özelliği kullanmak için: 
  
    1. "Çıkış noktası" düğmesini gösterilen kadar geri düğmesini seçmek devam eder. 
    2. Düğmesini seçer ve girer **bırakın bilgi noktası modu kodu** PIN.
    3. Değişiklikleriniz bittiğinde seçin **giriş ekranı yönetilen** uygulama. Bu adım, cihazı çoklu uygulama bilgi noktası moduna relocks. 

    **Devre dışı** bilgi noktası modu duraklatma özelliği vermez. Yönetici geri düğmesini seçmek devam eder ve devre dışı "Çıkış noktası" düğmesini seçerse bir ileti bir geçiş kodu gerekli olduğunu belirtir.

    - **Bilgi noktası modu kod**: 4-6 basamaklı girin sayısal PIN. Yönetici bu PIN'i geçici olarak bilgi noktası modu duraklatmak için kullanır.

  - **Özel URL arka plan ayarlamak**: Adanmış cihazda arka plan ekranı özelleştirmek için bir URL girin.
    
    > [!NOTE]
    > Çoğu durumda, görüntülerin ile en az aşağıdaki boyutları başlamanızı öneririz:
    >
    > - Telefonu: 1080 x 1920 piksel
    > - Tablet: 1920 x 1080 piksel
    >    
    > En iyi deneyimi ve NET Ayrıntılar için cihaz görüntüsü Görüntü belirtimlerine varlıklar oluşturulması önerilir.
    >
    > Daha yüksek piksel densities sahip ve eşdeğer 2 K/4 K tanımı görüntüleri modern görüntüler.
  - **Wi-Fi yapılandırma**: Seçin **etkinleştirme** son kullanıcıların cihaz farklı WiFi ağına bağlanmasına izin vermek için. Bu özellik etkinleştirildiğinde cihazın konum kapatır. **Yapılandırılmamış** (varsayılan) kullanıcılar yönetilen giriş ekranında sırada (kilit görev modu) olarak WiFi ağlarına bağlanmasını engeller.

    Daha açık [kilit görev modu](https://developer.android.com/work/dpc/dedicated-devices/lock-task-mode) (Android web sitesini açar).

  - **Bluetooth yapılandırma**: Seçin **etkinleştirme** cihazda Bluetooth izin verin ve Bluetooth üzerinden çifti cihazları son kullanıcılara izin verin. Bu özellik etkinleştirildiğinde cihazın konum kapatır. **Yapılandırılmamış** (varsayılan), kullanıcıların Bluetooth yapılandırma ve yönetilen giriş ekranındayken (kilit görev modu) cihazları çiftini engeller. 

    Daha açık [kilit görev modu](https://developer.android.com/work/dpc/dedicated-devices/lock-task-mode) (Android web sitesini açar).

### <a name="device-password-settings"></a>Cihaz parola ayarları

- **Kilit ekranında devre dışı**: Seçin **devre dışı** kullanıcıların cihazda tuş korumasını kilit ekranı özelliğini kullanmasını önlemek için. **Yapılandırılmamış** tuş korumasını özelliklerine izin verir.
- **Kilit ekranı özellikleri devre dışı**: Tuş korumasını cihazda etkinleştirildiğinde, devre dışı bırakmak için hangi Özellikler'i seçin. Örneğin, **güvenli kamera** denetlenir cihazda kamera özelliği devre dışı. Cihazda işaretli herhangi bir özelliği etkinleştirilir.

  Cihaz kilitliyken, bu özellikler kullanıcılar için kullanılabilir. Kullanıcılar bakın veya denetlenir özelliklerine erişimi olmaz.

- **Gerekli parola türü**: Cihaz için gerekli parola türünü tanımlayın. Seçenekleriniz şunlardır:
  - **Cihaz varsayılanı**
  - **Parola gerekli, kısıtlama yok**
  - **Zayıf biyometrik**: [Güçlü ile zayıf biyometrik arasındaki farklar](https://android-developers.googleblog.com/2018/06/better-biometrics-in-android-p.html) (Android web sitesinde açılır)
  - **Sayısal**: Parola yalnızca sayı olmalıdır, örneğin: `123456789`. Kullanıcının girmesi gereken **parolanın uzunluk alt sınırını** girin (4 ile 16 karakter arasında).
  - **Sayısal karmaşıklık**: Yinelenen veya ardışık sayılara (örneğin "1111" veya "1234") izin verilmez. Kullanıcının girmesi gereken **parolanın uzunluk alt sınırını** girin (4 ile 16 karakter arasında).
  - **Alfabetik**: Alfabedeki harflerin kullanılması gerekir. Rakamlar ve simgeler zorunlu tutulmaz. Kullanıcının girmesi gereken **parolanın uzunluk alt sınırını** girin (4 ile 16 karakter arasında).
  - **Alfasayısal**: Büyük harfler, küçük harfler ve sayısal karakterleri içerir. Kullanıcının girmesi gereken **parolanın uzunluk alt sınırını** girin (4 ile 16 karakter arasında).
  - **Simgelerle alfasayısal**: Büyük harfler, küçük harfler, sayısal karakterler, noktalama işaretleri ve simgeleri içerir. Şunları da girin:

    - **Minimum parola uzunluğu**: Parola uzunluğu alt sınırını girin (4 ile 16 karakter arasında).
    - **Gereken karakter sayısı**: Parolada bulunması gereken karakter sayısını girin (0 ile 16 karakter arasında).
    - **Gereken küçük harf karakter sayısı**: Parolada bulunması gereken küçük harf karakteri sayısını girin (0 ile 16 karakter arasında).
    - **Gereken büyük harf karakter sayısı**: Parolada bulunması gereken büyük harf karakteri sayısını girin (0 ile 16 karakter arasında).
    - **Gereken harf dışı karakter sayısı**: Parolada bulunması gereken harf dışı karakter sayısını (alfabedeki harflerin dışındaki karakterler, 0 ile 16 karakter arasında) girin.
    - **Gereken sayısal karakter sayısı**: Parolada bulunması gereken sayısal karakter sayısını (`1`, `2`, `3` gibi, 0 ile 16 karakter arasında) girin.
    - **Gereken simge karakter sayısı**: Parolada bulunması gereken simge karakter sayısını (`&`, `#`, `%` gibi, 0 ile 16 karakter arasında) girin.

- **Parola süresinin dolmasına kalan gün sayısı**: Cihaz parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını (1 ile 365 arasında) girin. Örneğin parolanın 60 gün sonra değiştirilmesi için `60` girin. Parola geçerlilik süresi dolduğunda kullanıcıların yeni bir parola oluşturması istenir.
- **Kullanıcı önce gerekli olan parolalardan kaç tanesinin resuse bir parola için**: Yeniden kullanılamayacak parolalar için 1 ile 24 arasında bir sayı girin. Son kullanıcının daha önce kullanılmış parolalar oluşturmasını önlemek için bu ayarı kullanın.
- **Cihaz silinmeden önceki oturum açma hatası sayısı**: Cihaz temizlenmeden önce izin başarısız oturum açma işlemleri, 4-11 arasında bir sayı girin.

### <a name="power-settings"></a>Güç ayarları

- **Ekranın kilitlenmesine kadar geçecek süre**: Cihaz kilitlenmeden önce gereken boş süre miktarını ayarlayın.
- **Cihaz takılıyken ekranından**: Cihazın ekran açık kalmasını prize takılı durumlar hangi güç kaynakları neden seçin.

### <a name="users-and-accounts-settings"></a>Kullanıcılar ve Hesaplar ayarları

- **Yeni kullanıcı ekleme**: Seçin **blok** kullanıcılar yeni kullanıcı eklemesini engellemek için. Her kullanıcının cihazda özel giriş ekranları, hesaplar, uygulamalar ve ayarlar için kişisel bir alanı vardır. **Yapılandırılmamış** kullanıcıların diğer kullanıcıların cihaza eklemesini sağlar.
- **Kullanıcı kaldırma**: Seçin **blok** kullanıcıları kullanıcılar kaldırmasını önlemek için. **Yapılandırılmamış** CİHAZDAN diğer kullanıcıları kaldırma olanağı sağlar.
- **Hesap değişiklikleri**: Seçin **blok** kullanıcı hesapları değiştirmesini önlemek için. **Yapılandırılmamış** kullanıcıların cihazda kullanıcı hesaplarını güncelleştirmek sağlar.

### <a name="applications"></a>Uygulamalar

- **Bilinmeyen kaynaklardan yüklemeye izin ver**: Seçin **izin** kullanıcılar açabilir **bilinmeyen kaynaklar**. Bu ayar, uygulamalar Google Play Store dışındaki kaynaklardan da dahil olmak üzere bilinmeyen kaynaklardan yükleme sağlar. **Yapılandırılmamış** kullanıcıların açılmasını engeller **bilinmeyen kaynaklar**.
- **Tüm uygulamalar Google Play mağazasına erişmesine izin vermek**: Ayarlandığında **izin**, kullanıcıların Google Play Mağazası'nda tüm uygulamalara erişimi alın. Yönetici engeller, uygulamalara erişim elde etmezsiniz [istemci uygulamaları](apps-add-android-for-work.md). **Yapılandırılmamış** yalnızca yönetici yapar kullanılabilir Google Play mağazası uygulamaları veya gerekli uygulamaları erişmek için kullanıcıların zorlar [istemci uygulamaları](apps-add-android-for-work.md).
- **Otomatik uygulama güncelleştirmeleri**: Otomatik Güncelleştirmeler yüklü olduğunda seçin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı**
  - **Kullanıcı Seçimi**
  - **hiçbir zaman**
  - **Wi-Fi yalnızca**
  - **Her zaman**

### <a name="connectivity"></a>Bağlantı

- **Her zaman açık VPN**: Seçin **etkinleştirme** otomatik olarak bağlanın ve VPN yeniden bağlanmak için bir VPN istemcisi ayarlamak için. Her Zaman Açık VPN bağlantıları; kullanıcı cihazı kilitlediğinde, cihaz yeniden başlatıldığında veya kablosuz ağ değiştiğinde bağlı durumda kalır veya hemen bağlanır. 

  Her zaman açık VPN'yi tüm VPN istemcilerinde devre dışı bırakmak için **Yapılandırılmadı**'yı seçin.

  > [!IMPORTANT]
  > Bir cihaza yalnızca bir tane Her Zaman Açık VPN ilkesi dağıttığınızdan emin olun. Bir cihaza birden çok Her Zaman Açık VPN ilkesi dağıtma desteklenmez.

- **VPN istemcisi**: AlwaysOn destekleyen bir VPN İstemcisi'ni seçin. Seçenekleriniz şunlardır:
  - Cisco AnyConnect
  - F5 Access
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Özel
    - **Paket kimliği**: Google Play Store'da uygulamanın paket Kimliğini girin. Örneğin Play mağazasındaki uygulamanın URL'si `https://play.google.com/store/details?id=com.contosovpn.android.prod` ise, paket kimliği `com.contosovpn.android.prod` olur.

  > [!IMPORTANT]
  >  - Seçtiğiniz VPN istemcisinin cihaza yüklenmesi ve cihazın uygulama başına VPN iş profillerini desteklemesi gerekir. Aksi takdirde bir hata oluşur. 
  >  - VPN istemci uygulamasını yine de **Yönetilen Google Play Mağazası**'nda onaylamanız, uygulamayı Intune ile eşitlemeniz ve cihaza dağıtmanız gerekir. Bu yapıldıktan sonra uygulama kullanıcının iş profiline yüklenir.
  >  - Bilinen sorunlar vardır uygulama başına VPN Android 3.0.4 için F5'e erişim ile kullanırken. Bkz: [Android 3.0.4 için F5'e erişim için F5'ın sürüm notları](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android) daha fazla bilgi için.

- **Kilit modunda**: Seçin **etkinleştirme** tüm ağ trafiğini VPN tünelini kullanmasını zorunlu kılmak için. VPN'e bir bağlantı oluşturulmazsa, cihazın ağ erişimi olmaz.

  Trafiğin VPN tünelinden veya mobil ağdan akmasına izin vermek için **Yapılandırılmadı**'yı seçin.

## <a name="work-profile-only"></a>Yalnızca iş profili 

### <a name="work-profile-settings"></a>İş profili ayarları

#### <a name="general"></a>Genel

- **İş ve Kişisel Profiller arasında kopyalama ve yapıştırma**: Seçin **blok** Kopyala ve Yapıştır iş ve kişisel uygulamalar arasında önlemek için. **Yapılandırılmamış** kullanıcıların kişisel profildeki uygulamalarla kopyalama ve yapıştırma kullanarak veri paylaşmasına izin verir 
- **İş ve Kişisel Profiller arasında veri paylaşımı**: İş profilindeki uygulamalar kişisel profildeki uygulamalarla paylaşıp seçin. Örneğin, uygulamalar içindeki paylaşma eylemler gibi denetleyebilirsiniz **Paylaş...** seçeneği gibi uygulamalardaki paylaşma eylemlerini denetler. Bu ayar, kopyala/yapıştır pano davranışında geçerli değildir. Paylaşım Seçenekleriniz şunlardır:
  - **Varsayılan paylaşım kısıtlamaları**: Varsayılan Paylaşım davranışıdır cihazın Android sürümüne göre değişir. Kişisel profilden iş profiline paylaşmaya varsayılan olarak izin verilir. Buna karşın iş profilinden kişisel profile paylaşma varsayılan olarak engellenir. Bu ayar, iş profilinden kişisel profile veri paylaşılmasını önler. Sürüm 6.0 ve üzerini çalıştıran cihazlarda Google kişisel profilden iş profiline paylaşımı engellemez.
  - **İş profilindeki uygulamalar kişisel profilden gelen paylaşım isteklerini işleyebilir**: Kişisel profilden iş profiline paylaşıma izin veren yerleşik Android özelliğini etkinleştirir. Etkinleştirildiğinde, kişisel profildeki bir uygulamadan gelen bir paylaşım isteği, iş profilindeki uygulamalarla paylaşım kullanabilir. Bu ayar, 6.0 öncesi sürümleri çalıştıran Android cihazlarının varsayılan davranışıdır.
  - **Sınırlar arası paylaşıma izin**: İş profili sınırının ötesinde her iki yönde paylaşımı etkinleştirir. Bu ayarı seçtiğinizde, iş profilinizdeki uygulamalar kişisel profildeki rozetsiz uygulamalar ile veri paylaşabilir. Bu ayar iş profilindeki yönetilen uygulamaların cihazın yönetilmeyen kısmındaki uygulamalarla paylaşmasına izin verir. Bu nedenle bu ayarı dikkatli kullanın.

- **Cihaz kilitliyken iş profili bildirimlerini**: Cihaz kilitliyken iş profilindeki uygulamalar verileri bildirimleri görüntüleyebilirsiniz olup olmadığını denetler. **Blok** verileri göstermez. **Yapılandırılmamış** verileri gösterir.
- **Varsayılan uygulama izinleri**: İş profilindeki tüm uygulamalar için varsayılan izin ilkesini ayarlar. Android 6 ile başlayarak, kullanıcıdan, belirli uygulamalar açıldığında bunlar için gereken bazı izinleri vermesi istenir. Bu ilke ayarı, kullanıcıdan iş profilindeki tüm uygulamalar için izin istenip istenmeyeceğini belirlemenize olanak tanır. Örneğin, iş profiline konum erişimi gerektiren bir uygulama atarsınız. Normalde bu uygulama kullanıcıdan konum erişimini onaylamasını veya reddetmesini ister. Bu ilkeyi istem kullanmadan otomatik olarak izinler vermek, izin vermeyi reddetmek veya kararı kullanıcıya bırakmak için kullanabilirsiniz. Aşağıdakilerden birini seçin:
  - **Cihaz varsayılanı**
  - **Sor**
  - **Otomatik olarak izin ver**
  - **Otomatik olarak reddet**

  Ayrıca tek tek uygulamalara izinler vermek için bir Uygulama Yapılandırma ilkesi de kullanabilirsiniz (**İstemci Uygulamaları** > **Uygulama yapılandırma ilkeleri**).

- **Hesap ekleme ve kaldırma**: Seçin **blok** son kullanıcıların, el ile eklemek veya iş profilinde hesaplarının kaldırılmasını önlemek için. Örneğin, Gmail uygulamasını bir Android iş profiline dağıttığınızda, son kullanıcıların bu iş profiline hesap eklemesini veya buradan kaldırmasını engelleyebilirsiniz. **Yapılandırılmamış** iş profilinde hesap ekleme sağlar.  

- **Bluetooth ile kişi paylaşımı**: Kişileri, Bluetooth kullanarak eşleştirilmiş bir araba gibi başka bir CİHAZDAN çalışma erişimi etkinleştirir. Bu ayar varsayılan olarak yapılandırılmamıştır ve iş profili kişileri gösterilmez. Bu paylaşıma izin verip iş profili kişilerini görüntülemek için **Etkinleştir**’i seçin. Bu ayar, Android OS v6.0 ve üzeri sürümlerde Android iş profili cihazları için geçerlidir. Bu ayarı etkinleştirmek, bazı Bluetooth cihazlarının ilk bağlantı sırasında iş kişilerini önbelleğe almasına izin verebilir. İlk eşleme/eşitleme sonrasına bunu devre dışı bırakmak ise Bluetooth cihazından iş kişilerini kaldırmayabilir.

- **Ekran yakalama**: Seçin **blok** ekran görüntüleri veya ekran önlemek için cihazın iş profilindeki yakalar. Ayrıca güvenli bir video çıkışına sahip olmayan görüntü cihazlarında gösterilen içeriği engeller. **Yapılandırılmamış** ekran görüntüleri alma sağlar.

- **Kişisel profilde iş kişisi arayan kimliğini görüntüleme**: Etkin olduğunda (**yapılandırılmadı**), iş kişisi arayan ayrıntıları kişisel profilde görüntülenir. Ayarlandığında **blok**, iş kişisi arayan numarası kişisel profilde görüntülenmez. Android işletim sistemi v6.0 ve daha yeni sürümlerde geçerlidir.

- **Kişisel profilden iş kişilerini arayın**: Seçin **blok** kullanıcılar, kişisel profildeki uygulamalar iş kişileri arama yapmasını önlemek için. **Gerekli değil** iş kişilerini Kişisel profildeki arama sağlar.

- **Kamera**: Seçin **blok** iş profili olan cihazda kamerayı erişimi engellemek için. Kişisel taraftaki kamera, bu ayardan etkilenmez. **Gerekli değil** iş profilinde kameraya erişim sağlar.

#### <a name="work-profile-password"></a>İş profili parolası

- **İş profili parolası gerektir**: İş profilinin etkinleştirildiği Android 7.0 ve üzeri sürümlerde geçerlidir. Seçin **gerektiren** yalnızca iş profilindeki uygulamalar için geçerli bir geçiş kodu ilkesi girmek için. Varsayılan olarak, son kullanıcı birbirinden ayrı tanımlanmış iki PIN kullanabilir veya PIN’leri iki PIN'den daha güçlü olanın altında birleştirmeyi seçebilir. **Yapılandırılmamış** iş uygulamaları, parola girmeden kullanmasına izin verir.
- **Minimum parola uzunluğu**: En az bir kullanıcı parolasının sahip olması gerekir, karakter sayısını girin gelen **4**-**16**.
- **Kilitlenmesine kadar iş profili kilitlenmeden önce**: İş profili kilitlenmeden önce geçen süreyi seçin. Daha sonra kullanıcının kimlik bilgilerini girerek tekrar erişim kazanması gerekir.
- **Cihaz silinmeden önceki oturum açma hatası sayısı**: İş profili temizlenmeden önce hatalı bir parolanın CİHAZDAN girilebilir sayısını girin.
- **Parola zaman aşımı (gün sayısı)** : Bir son kullanıcının parolası değiştirilene kadar geçecek gün sayısını girin (gelen **1**-**255**).
- **Gerekli parola türü**: Cihazda ayarlanması gereken parola türünü seçin. Aşağıdakilerden birini seçin:
  - **Cihaz varsayılanı**
  - **Düşük güvenlik biyometriği**
  - **Gerekli**
  - **En az sayısal**
  - **Sayısal karmaşıklık**: '1111' veya '1234' gibi yinelenen veya ardışık numaralara izin verilmez
  - **En az alfabetik**
  - **En az alfasayısal**
  - **En az simgeler ile alfasayısal**
- **Önceki parolaların yeniden kullanılmasını engelleme**: Eski bir parolanın yeniden kullanılabilmesi, kullanılması gereken yeni parola sayısını girin (gelen **1**-**24**).
- **Parmak izi ile kilit açma**: Seçin **blok** son kullanıcılar cihazın kilidini açmak için cihazın parmak izi tarayıcısını kullanmasını önlemek için. **Yapılandırılmamış** kullanıcıların cihazların iş profilindeki bir parmak izi ile kilit açma olanak sağlar.
- **Akıllı kilit ve diğer güven aracıları**: Seçin **blok** ayarlaması kilit ekranı ayarları uyumlu cihazlarda akıllı kilit veya diğer güven aracılarının önlemek için. Bazen bir güven aracısı olarak da bilinen bu özelliği devre dışı bırakın veya cihaz güvenilir bir konumda, cihazın kilitleme ekranı parolasını atlamanıza izin verir. Örneğin cihaz belirli bir Bluetooth cihazına bağlıyken ya da bir NFC etiketinin yakınındayken iş profili parolasını atlama. Bu ayarı, kullanıcıların Akıllı Kilit'i yapılandırmasını önlemek için kullanın.

### <a name="device-password"></a>Cihaz parolası

Bu parola ayarlar, bir iş profili kullanan cihazlardaki kişisel profiller için geçerlidir.

- **Minimum parola uzunluğu**: En az bir kullanıcı parolasının sahip olması gerekir, karakter sayısını girin gelen **4**-**14**.
- **Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı**: Etkin olmayan bir cihaz otomatik olarak kilitlenmeden önce geçen süreyi seçin
- **Cihaz silinmeden önceki oturum açma hatası sayısı**: Kaç kez CİHAZDAN tüm verileri silinmeden önce yanlış parola girilebileceğini sayısını girin
- **Parola zaman aşımı (gün sayısı)** : Bir son kullanıcının parolası değiştirilene kadar geçecek gün sayısını girin (gelen **1**-**255**)
- **Gerekli parola türü**: Cihazda ayarlanması gereken parola türünü seçin. Aşağıdakilerden birini seçin:
  - **Cihaz varsayılanı**
  - **Düşük güvenlik biyometriği**
  - **Gerekli**
  - **En az sayısal**
  - **Sayısal karmaşıklık**: '1111' veya '1234' gibi yinelenen veya ardışık numaralara izin verilmez
  - **En az alfabetik**
  - **En az alfasayısal**
  - **En az simgeler ile alfasayısal**
- **Önceki parolaların yeniden kullanılmasını engelleme**: Eski bir parolanın yeniden kullanılabilmesi, kullanılması gereken yeni parola sayısını girin (gelen **1**-**24**).
- **Parmak izi ile kilit açma**: Seçin **blok** son kullanıcı, cihazın kilidini açmak için cihazın parmak izi tarayıcısını kullanmasını önlemek için. **Yapılandırılmamış** parmak izi kullanarak cihaz kilidini açmak kullanıcının sağlar.
- **Akıllı kilit ve diğer güven aracıları**: Seçin **blok** ayarlaması kilit ekranı ayarları uyumlu cihazlarda akıllı kilit veya diğer güven aracılarının önlemek için. Bazen bir güven aracısı olarak da bilinen bu özelliği devre dışı bırakın veya cihaz güvenilir bir konumda, cihazın kilitleme ekranı parolasını atlamanıza izin verir. Örneğin cihaz belirli bir Bluetooth cihazına bağlıyken ya da bir NFC etiketinin yakınındayken iş profili parolasını atlama. Bu ayarı, kullanıcıların Akıllı Kilit'i yapılandırmasını önlemek için kullanın.

### <a name="system-security"></a>Sistem güvenliği

- **Uygulamalarda tehdit taraması**: **Gerektiren** , zorlar **uygulamaları doğrula** iş ve kişisel profiller için seçeneği etkinleştirilmiştir.

   > [!Note]
   > Bu ayar yalnızca Android O ve üstü cihazlarda çalışır.

### <a name="connectivity"></a>Bağlantı

- **Her zaman açık VPN**: Seçin **etkinleştirme** otomatik olarak bağlanın ve VPN yeniden bağlanmak için bir VPN istemcisi ayarlamak için. Her Zaman Açık VPN bağlantıları; kullanıcı cihazı kilitlediğinde, cihaz yeniden başlatıldığında veya kablosuz ağ değiştiğinde bağlı durumda kalır veya hemen bağlanır. 

  Her zaman açık VPN'yi tüm VPN istemcilerinde devre dışı bırakmak için **Yapılandırılmadı**'yı seçin.

  > [!IMPORTANT]
  > Bir cihaza yalnızca bir tane Her Zaman Açık VPN ilkesi dağıttığınızdan emin olun. Bir cihaza birden çok Her Zaman Açık VPN ilkesi dağıtma desteklenmez.

- **VPN istemcisi**: AlwaysOn destekleyen bir VPN İstemcisi'ni seçin. Seçenekleriniz şunlardır:
  - Cisco AnyConnect
  - F5 Access
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Özel
    - **Paket kimliği**: Google Play Store'da uygulamanın paket Kimliğini girin. Örneğin Play mağazasındaki uygulamanın URL'si `https://play.google.com/store/details?id=com.contosovpn.android.prod` ise, paket kimliği `com.contosovpn.android.prod` olur.

  > [!IMPORTANT]
  >  - Seçtiğiniz VPN istemcisinin cihaza yüklenmesi ve cihazın uygulama başına VPN iş profillerini desteklemesi gerekir. Aksi takdirde bir hata oluşur. 
  >  - VPN istemci uygulamasını yine de **Yönetilen Google Play Mağazası**'nda onaylamanız, uygulamayı Intune ile eşitlemeniz ve cihaza dağıtmanız gerekir. Bu yapıldıktan sonra uygulama kullanıcının iş profiline yüklenir.
  >  - Bilinen sorunlar vardır uygulama başına VPN Android 3.0.4 için F5'e erişim ile kullanırken. Bkz: [Android 3.0.4 için F5'e erişim için F5'ın sürüm notları](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android) daha fazla bilgi için.

- **Kilit modunda**: Seçin **etkinleştirme** tüm ağ trafiğini VPN tünelini kullanmasını zorunlu kılmak için. VPN'e bir bağlantı oluşturulmazsa, cihazın ağ erişimi olmaz.

  Trafiğin VPN tünelinden veya mobil ağdan akmasına izin vermek için **Yapılandırılmadı**'yı seçin.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).

Ayrılmış bir cihaz bilgi noktası profillerini oluşturabilirsiniz [Android](device-restrictions-android.md#kiosk) ve [Windows 10](kiosk-settings.md) cihazlar.

## <a name="see-also"></a>Ayrıca bkz.

[Android kuruluş cihazlarının Microsoft Intune sorun giderme ve yapılandırma](https://support.microsoft.com/help/4476974)
