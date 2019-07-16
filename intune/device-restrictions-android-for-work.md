---
title: Android Kurumsal cihaz ayarları Microsoft Intune - Azure | Microsoft Docs
description: Android Kurumsal veya Android for Work cihazlar, cihazın ayarlarını kısıtlamak, dahil olmak üzere kopyalama ve yapıştırma, bildirimleri, uygulama izinleri, veri paylaşımı, parola uzunluğu, Göster başarısız oturum açma, yeniden parolalar, kilidini açmak için parmak izi'ni kullanın ve bluetooth etkinleştir Work kişileriyle paylaşma. Tek bir uygulama veya birden çok uygulama çalıştırmak için cihazları adanmış bir cihaz bilgi noktası olarak yapılandırın.
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
ms.openlocfilehash: d4ab90a36254de49eb27e326086ffb137c782005
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67883428"
---
# <a name="android-enterprise-device-settings-to-allow-or-restrict-features-using-intune"></a>İzin vermek veya Intune kullanarak özellikleri kısıtlamak için android Kurumsal cihaz ayarları

Bu makalede, listeler ve Android Kurumsal cihazlarda denetleyebileceğiniz farklı ayarlar açıklanır. Mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak bu ayarları, özelliklere izin vermek veya devre dışı bırakmak, uygulamaları adanmış cihazlarda çalıştırmak, güvenliği denetlemek ve daha fazlasını yapmak için kullanın.

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz yapılandırma profili oluşturma](device-restrictions-configure.md).

## <a name="device-owner-only"></a>Yalnızca cihaz sahibi

### <a name="general-settings"></a>Genel ayarlar

- **Ekran yakalama**: Cihazda ekran görüntülerini veya ekran yakalamalarını önlemek için **Engelle**'yi seçin. Ayrıca güvenli bir video çıkışına sahip olmayan görüntü cihazlarında gösterilen içeriği engeller. **Yapılandırılmamış** kullanıcının ekran içeriğini resim olarak yakalamasına izin verir.
- **Kamera**: Cihazdaki kameraya erişim sağlanmasını engellemek için **Engelle**'yi seçin. **Gerekli değil** cihazın kamerasını erişmesini sağlar.
- **Varsayılan izin ilkesi**: Bu ayar, çalışma zamanı izinleri istekleri için varsayılan izin ilkesini tanımlar. Olası değerler şöyledir:
  - **Cihaz varsayılanı**: Cihazın varsayılan ayarını kullanın.
  - **Komut istemi**: Kullanıcıdan izni onaylaması istenir.
  - **Otomatik izin ver**: İzinler otomatik olarak verilir.
  - **Otomatik Reddet**: İzinler otomatik olarak reddedilir.
- **Tarih ve saat değişiklikleri**: Kullanıcıların Tarih ve saati el ile ayarlamamasını engellemek için **Engelle** ' yi seçin. **Yapılandırılmamış** ayarlanmış tarih ve saat için kullanıcıların cihazda izin verir.
- **Birim değişiklikleri**: Kullanıcıların cihazın birimini değiştirmesini engellemek için **Engelle** ' yi seçin. **Yapılandırılmamış** cihazda birim ayarlarını kullanımına izin verir.
- **Fabrika Sıfırlaması**: Kullanıcıların cihaz ayarlarındaki fabrika sıfırlaması seçeneğini kullanmalarını engellemek için **Engelle** ' yi seçin. **Yapılandırılmamış** Bu ayar cihazda kullanmasına olanak tanır.
- **Güvenli önyükleme**: Kullanıcıların cihazı güvenli moda yeniden başlatılmasını engellemek için **Engelle** ' yi seçin. **Yapılandırılmamış** kullanıcılar güvenli modda cihazın yeniden başlatılmasına izin verir.
- **Durum çubuğu**: Bildirimler ve hızlı ayarlar dahil olmak üzere durum çubuğuna erişimi engellemek için **Engelle** ' yi seçin. **Yapılandırılmamış** kullanıcıların durum çubuğuna erişimi sağlar.
- **Dolaşım veri Hizmetleri**: Cep telefonu şebekesi üzerinden veri dolaşımını önlemek için **Engelle**'yi seçin. **Yapılandırılmamış** cihaz hücresel ağ kullanırken veri dolaşımına izin verir.
- **Wi-Fi ayarı değişiklikleri**: Kullanıcıların cihaz sahibi tarafından oluşturulan Wi-Fi ayarlarını değiştirmesini engellemek için **Engelle** ' yi seçin. Kullanıcılar kendi Wi-Fi yapılandırmalarını oluşturabilir. **Yapılandırılmamış** kullanıcıların cihazda Wi-Fi ayarlarını değiştirmesine olanak tanır.
- **Wi-Fi erişim noktası yapılandırması**: Kullanıcıların herhangi bir Wi-Fi yapılandırması oluşturmasını veya değiştirmesini engellemek için **Engelle** ' yi seçin. **Yapılandırılmamış** kullanıcıların cihazda Wi-Fi ayarlarını değiştirmesine olanak tanır.
- **Bluetooth yapılandırması**: Kullanıcıların cihazda Bluetooth 'u yapılandırmalarını engellemek için **Engelle** ' yi seçin. **Yapılandırılmamış** cihazda Bluetooth'un kullanımına izin verir.
- **Internet paylaşımı ve etkin noktalara erişim**: İnternet paylaşımını ve taşınabilir etkin noktalara erişimi engellemek için **Engelle** ' yi seçin. **Yapılandırılmamış** internet paylaşımı ve taşınabilir noktalarına erişim sağlar.
- **USB depolama**: Cihazda USB depolamaya erişime **Izin ver** ' i seçin. **Yapılandırılmamış** USB depolama alanına erişimini engeller.
- **USB dosya aktarımı**: USB üzerinden dosya aktarımını engellemek için **Engelle** ' yi seçin. **Yapılandırılmamış** dosyaları aktarma sağlar.
- **Dış medya**: Cihazda herhangi bir dış medyanın kullanılmasını veya bağlanmasını engellemek için **Engelle** ' yi seçin. **Yapılandırılmamış** Dış medya cihazda izin verir.
- **NFC kullanarak Kirme verileri**: Uygulamalardan gelen verileri kirmek için yakın alan Iletişimi (NFC) teknolojisinin kullanılmasını engellemek için **Engelle** ' yi seçin. **Yapılandırılmamış** cihazlar arasında veri paylaşımı için NFC kullanımına izin verir.
- **Hata ayıklama özellikleri**: Kullanıcıların cihazdaki hata ayıklama özelliklerini kullanmasına izin vermek için **Izin ver** ' i seçin. **Yapılandırılmamış** kullanıcıların cihazda hata ayıklama özelliklerini kullanmasını önler.
- **Mikrofon ayarlaması**: Kullanıcıların mikrofonu kapatıp mikrofon birimini değiştirmesine engel olmak için **Engelle** ' yi seçin. **Yapılandırılmamış** kullanma ve cihazda mikrofon ses ayarlamak izin verir.
- **Fabrika ayarlarına sıfırlama koruması e-postaları**: **Google hesabı e-posta adreslerini**seçin. Bunu temizlendikten sonra cihazın kilidini açmak cihaz yöneticilerinin e-posta adreslerini girin. E-posta adresi gibi bir noktalı virgül ile ayırın mutlaka `admin1@gmail.com;admin2@gmail.com`. E-posta değil girdiyseniz, fabrika ayarlarına geri yüklendikten sonra herkes cihazın kilidini açabilirsiniz. Bu e-postalar yalnızca, Kurtarma menüsünü kullanarak Fabrika Sıfırlaması çalıştırma gibi kullanıcı olmayan bir fabrika sıfırlaması çalıştırıldığında geçerlidir.
- **Ağ çıkış taraması**: Kullanıcıların ağ çıkış tarama özelliğini etkinleştirmesine izin vermek için **Etkinleştir** ' i seçin. Cihaz önyüklendiğinde bir ağ bağlantısı olmayan yaptıysanız, kaçış noktası geçici olarak bir ağa bağlayın ve cihaz ilkesini yenilemek sorar. Bu ilke uygulandıktan sonra geçici ağ unutulur ve cihaz önyüklemeye devam eder. Bu özellik, cihazları ağa bağlanır:
  - Son ilkede uygun bir ağ yok.
  - Cihaz uygulama kilidi görev modunda önyüklenir.
  - Kullanıcı cihaz ayarları ulaşamıyor.

  **Yapılandırılmamış** kullanıcıların cihazdaki ağ kaçış tarama özelliği kapatmasını engeller.

- **Sistem güncelleştirmesi**: Cihazın kablosuz güncelleştirmeleri nasıl işlediğini tanımlamak için bir seçenek belirleyin:
  - **Cihaz varsayılanı**: Cihazın varsayılan ayarını kullanın.
  - **Otomatik**: Güncelleştirmeler Kullanıcı etkileşimi olmadan otomatik olarak yüklenir. Bu ilkeyi seçmek, bekleyen tüm güncelleştirmeleri hemen yükler.
  - **Ertelendi**: Güncelleştirmeler 30 gün ertelenir. 30 günün sonunda, Android güncelleştirmeyi yüklemek için kullanıcıya sorar. Cihaz üreticilerin veya taşıyıcıların önemli güvenli güncelleştirmelerinin ertelenmesini engellemek (muaf tutmak) mümkündür. Muaf tutulan bir güncelleştirme cihazda kullanıcıya bir sistem bildirimi gösterir. 
  - **Bakım penceresi**: Güncelleştirmeleri Intune 'da ayarladığınız günlük bakım penceresi sırasında otomatik olarak yüklenir. Yükleme 30 gün boyunca her gün çalışır ve yeterli alan veya pil düzeyleri varsa başarısız olabilir. 30 gün sonra kullanıcıyı uygulamayı yüklemek için Android ister. Bu pencere ayrıca Oynatma uygulamalarının güncelleştirmelerini yüklemek için de kullanılır. Tek uygulamayla ayrılmış cihaz ön plan uygulamaları güncelleştirilemeyebilir, kiosks gibi adanmış cihazlar için bu seçeneği kullanın.

- **Bildirim pencereleri**: **Devre dışı**olarak ayarlandığında, tomerler, gelen çağrılar, giden çağrılar, sistem uyarıları ve sistem hataları dahil olmak üzere pencere bildirimleri cihazda gösterilmez. **Yapılandırılmadı**olarak ayarlandığında, varsayılan işletim sistemi kullanılır ve bu da bildirimleri göstermek olabilir.
- **İlk kullanım Ipuçlarını atla**: Öğreticilerle gezinmek veya uygulama başladığında herhangi bir tanıtım ipucu okumak üzere uygulamalardan önerileri gizlemek veya atlamak için **Etkinleştir** ' i seçin. **Yapılandırılmadı**olarak ayarlandığında, uygulama başlatıldığında Bu önerilerin gösterilmesi için işletim sistemi varsayılanı kullanılır.

### <a name="system-security-settings"></a>Sistem güvenliği ayarları

- **Uygulamalarda tehdit taraması**: **Gerektir** (varsayılan), uygulamaları yüklenmeden önce ve sonra taramak için Google Play koruma sağlar. Tehdit algılarsa, uygulamayı cihazdan kaldırmak için kullanıcıyı uyarabilir. **Yapılandırılmadı** , uygulamaları taramak Için Google Play koruma sağlamaz veya çalıştırılmaz.

### <a name="dedicated-device-settings"></a>Adanmış cihaz ayarları

Adanmış cihazlarınızda bilgi noktası stili bir deneyim yapılandırmak için bu ayarları kullanın. Bir cihazı tek bir uygulamayı çalıştıracak şekilde yapılandırabilir veya birçok uygulama çalıştırabilirsiniz. Cihaz bilgi noktası moduyla ayarlandığında, yalnızca eklediğiniz uygulamalar kullanılabilir. Bu ayarlar Android kurumsal adanmış cihazlara uygulanır. Android kurumsal tam yönetilen cihazlara uygulanmaz.

**Bilgi noktası modu**: Cihazın bir uygulama çalıştırması veya birden çok uygulama çalıştırması durumunda seçin.

- **Tek uygulama**: Kullanıcılar cihazdaki tek bir uygulamaya yalnızca erişebilir. Cihaz başlatıldığında, yalnızca belirli uygulamayı başlatır. Kullanıcılar yeni uygulamalar açamaz veya çalışan uygulamayı değiştiremez.

  **Adımları**
  1. Seçin **bir yönetilen uygulama seçin**, yönetilen Google Play uygulaması listeden seçin. 

      Ardından, listelenen tüm uygulamalar yoksa [bazı Android uygulamaları ekleme](apps-add-android-for-work.md) cihaza. [Uygulamayı adanmış cihazlarınız için oluşturulan cihaz grubuna atadığınızdan](apps-deploy.md)emin olun.

  2. Seçin **Tamam** > **Tamam** seçerek uygulamayı ekleyin.

- **Çoklu uygulama**: Kullanıcılar cihazdaki sınırlı bir uygulama kümesine erişebilirler. Cihaz başlatıldığında, yalnızca eklediğiniz uygulamalar başlatın. Ayrıca, kullanıcılar açabilir bazı web bağlantıları da ekleyebilirsiniz. İlkenin geçerli olduğu kullanıcı giriş ekranında simgeleri için izin verilen uygulamalar görürsünüz.

  > [!IMPORTANT]
  > Çok uygulamayla ayrılmış cihazlarda, Google Play [yönetilen giriş ekranı uygulamasının](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise) şu **olması gerekir**:
  >   - [Bir istemci uygulaması olarak eklenen](apps-add-android-for-work.md) ıntune
  >   - Adanmış cihazlarınız için oluşturulan [cihaz grubuna atandı](apps-deploy.md)
  > 
  > **Giriş ekranı yönetilen** uygulama yapılandırma profilinde de olması için gerekli değildir, ancak bir istemci uygulaması olarak eklenmesi için gereklidir. **Yönetilen giriş ekranı** uygulaması bir istemci uygulaması olarak eklendiğinde, yapılandırma profiline eklediğiniz diğer uygulamalar **yönetilen giriş ekranı** uygulamasında simgeler olarak gösterilir. 
  >
  > Yönetilen giriş ekranı ile birden çok uygulama bilgi noktası modu kullanılırken, çevirici/telefon uygulamaları düzgün çalışmayabilir. 

  - Seçin **Ekle**ve uygulamalarınızı listeden seçin.

    Varsa **giriş ekranı yönetilen** uygulama listelenmez, ardından [Google Play'den ekleme](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise). [Uygulamayı](apps-deploy.md) adanmış cihazlarınız için oluşturulan cihaz grubuna atadığınızdan emin olun.

    Ayrıca diğer ekleyebilirsiniz [Android uygulamaları](apps-add-android-for-work.md) ve [web uygulamaları](web-app.md) cihazla kuruluşunuz tarafından oluşturulmuş. [Uygulamayı adanmış cihazlarınız için oluşturulan cihaz grubuna atadığınızdan](apps-deploy.md)emin olun.

  - **Sanal giriş düğmesi**: Adanmış cihazda bir giriş düğmesi göstermek için **Etkinleştir** ' i seçin. Kullanıcıların uygulamalar arasında kolayca geçiş yapabilirsiniz için bu onay kutusu seçildiğinde, cihazın giriş ekranına kullanıcı döndürür. Bazı Android cihazlarda, kullanıcıların giriş düğmesini göster ekranda yukarı a doğru çekin gerekebilir. **Devre dışı** kullanıcılar, uygulamalar arasında geçiş yapmak için geri düğmesini kullanmalısınız bir giriş düğmesi göstermez.
  - **Bilgi noktası modundan çıkma**: Yöneticilerin cihazı güncelleştirmek için bilgi noktası modunu geçici olarak duraklamasını sağlamak için **Etkinleştir** ' i seçin. Bu özelliği kullanmak için yönetici: 
  
    1. "Bilgi noktası çıkış" düğmesi gösterilene kadar geri düğmesini seçmeye devam eder. 
    2. Düğmeyi seçer ve **bilgi noktası modu kod** sabitini girer.
    3. Değişiklikleriniz bittiğinde seçin **giriş ekranı yönetilen** uygulama. Bu adım, cihazı çoklu uygulama bilgi noktası moduna relocks. 

    **Devre dışı** bilgi noktası modu duraklatma özelliği vermez. Yönetici geri düğmesini seçip "bilgi noktası çıkış" düğmesini seçerse, bir geçiş kodunun gerekli olduğunu belirtir.

    - **Bilgi noktası modu kodunu bırak**: 4-6 basamaklı sayısal bir PIN girin. Yönetici bu PIN'i geçici olarak bilgi noktası modu duraklatmak için kullanır.

  - **Özel URL arka planı ayarla**: Adanmış cihazda arka plan ekranını özelleştirmek için bir URL girin.
    
    > [!NOTE]
    > Çoğu durumda, en az aşağıdaki boyutlardaki görüntülerle başlamasını öneririz:
    >
    > - Numarası 1080x1920 piksel
    > - \ 1920x1080 px
    >    
    > En iyi deneyim ve ayrıntılı Ayrıntılar için, görüntüleme belirtimlerine cihaz başına görüntü varlıkları oluşturulması önerilir.
    >
    > Modern görüntüler, daha yüksek piksel yoğunluklarını ve eşdeğer 2K/4K tanım görüntülerini görüntüleyebilir.
  - **Wi-Fi yapılandırması**: Son kullanıcıların cihazı farklı WiFi ağlarına bağlanmasına izin vermek için **Etkinleştir** ' i seçin. Bu özelliği etkinleştirmek Ayrıca cihaz konumunu da etkinleştirir. **Yapılandırılmadı** (varsayılan), kullanıcıların yönetilen giriş ekranında (kilit görevi modunda) WiFi ağlarına bağlanmasını engeller.

    [Kilit görev modunda](https://developer.android.com/work/dpc/dedicated-devices/lock-task-mode) daha fazla (Android 'in Web sitesini açar).

  - **Bluetooth yapılandırması**: Cihazda Bluetooth 'a izin vermek için **Etkinleştir** ' i seçin ve son kullanıcıların cihazları Bluetooth üzerinden eşleştirmesine izin verin. Bu özelliği etkinleştirmek Ayrıca cihaz konumunu da etkinleştirir. **Yapılandırılmadı** (varsayılan), yönetilen giriş ekranında (kilit görevi modu) kullanıcıların Bluetooth ve eşleme cihazlarını yapılandırmalarını engeller. 

    [Kilit görev modunda](https://developer.android.com/work/dpc/dedicated-devices/lock-task-mode) daha fazla (Android 'in Web sitesini açar).

### <a name="device-password-settings"></a>Cihaz parola ayarları

- **Kilit ekranını devre dışı bırak**: Kullanıcıların cihazda Keyguard kilit ekranı özelliğini kullanmalarını engellemek için **devre dışı bırak** ' ı seçin. **Yapılandırılmamış** tuş korumasını özelliklerine izin verir.
- **Kilit ekranı özellikleri devre dışı**: Cihazda keyguard etkinleştirildiğinde, hangi özelliklerin devre dışı bırakılacağını seçin. Örneğin, **güvenli kamera** işaretlendiğinde kamera özelliği cihazda devre dışı bırakılır. Denetlenmeyen tüm özellikler cihazda etkinleştirilir.

  Bu özellikler, cihaz kilitlendiğinde kullanıcılar tarafından kullanılabilir. Kullanıcılar işaretli özellikleri göremez veya erişemez.

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
- **Kullanıcının bir parolayı yeniden kullanabilmesi için gereken parola sayısı**: Yeniden kullanılamayacak parolalar için 1 ile 24 arasında bir sayı girin. Son kullanıcının daha önce kullanılmış parolalar oluşturmasını önlemek için bu ayarı kullanın.
- **Cihaz silinmeden önceki oturum açma hatası sayısı**: Cihaz temizlenmeden önce izin verilecek başarısız oturum açma işlemlerinin sayısını 4-11 arasında girin.

### <a name="power-settings"></a>Güç ayarları

- **Kilit süresi ekranı**: Cihaz kilitlenmeden önce gerekli olan boşta kalma süresi miktarını ayarlayın.
- **Cihazın takılmasına karşın ekran açık**: Cihazın ekranının prize takılıyken açık kalmasına neden olan güç kaynaklarını seçin.

### <a name="users-and-accounts-settings"></a>Kullanıcılar ve Hesaplar ayarları

- **Yeni Kullanıcı Ekle**: Kullanıcıların yeni kullanıcı eklemesini engellemek için **Engelle** ' yi seçin. Her kullanıcının cihazda özel giriş ekranları, hesaplar, uygulamalar ve ayarlar için kişisel bir alanı vardır. **Yapılandırılmamış** kullanıcıların diğer kullanıcıların cihaza eklemesini sağlar.
- **Kullanıcı kaldırma**: Kullanıcıların kullanıcıları kaldırmasını engellemek için **Engelle** ' yi seçin. **Yapılandırılmamış** CİHAZDAN diğer kullanıcıları kaldırma olanağı sağlar.
- **Hesap değişiklikleri**: Kullanıcıların hesapları değiştirmesini engellemek için **Engelle** ' yi seçin. **Yapılandırılmamış** kullanıcıların cihazda kullanıcı hesaplarını güncelleştirmek sağlar.

### <a name="applications"></a>Uygulamalar

- **Bilinmeyen kaynaklardan yüklemeye Izin ver**: Kullanıcıların **Bilinmeyen kaynakları**açıp kullanabilmesi Için **izin ver** ' i seçin. Bu ayar, uygulamaların Google Play Store dışındaki kaynaklar da dahil olmak üzere bilinmeyen kaynaklardan yüklenmesine izin verir. **Yapılandırılmamış** kullanıcıların açılmasını engeller **bilinmeyen kaynaklar**.
- **Google Play Store 'daki tüm uygulamalara erişime Izin ver**: **Izin ver**olarak ayarlandığında, kullanıcılar Google Play deposundaki tüm uygulamalara erişim sağlar. [Istemci uygulamalarında](apps-add-android-for-work.md)yönetici blokları olan uygulamalara erişim almaz. **Yapılandırılmadı** , kullanıcıları yalnızca yöneticinin kullanılabilir Google Play depolama alanı veya [istemci uygulamalarında](apps-add-android-for-work.md)gerekli uygulamalar üzerinde yaptığı uygulamalara erişmesine zorlar.
- **Uygulama otomatik güncelleştirmeleri**: Otomatik güncelleştirmelerin ne zaman yükleneceğini seçin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı**
  - **Kullanıcı Seçimi**
  - **hiçbir zaman**
  - **Wi-Fi yalnızca**
  - **Her zaman**

### <a name="connectivity"></a>Bağlantı

- **Her zaman VPN**: VPN istemcisini otomatik olarak bağlanıp VPN 'ye yeniden bağlanacak şekilde ayarlamak için **Etkinleştir** ' i seçin. Her Zaman Açık VPN bağlantıları; kullanıcı cihazı kilitlediğinde, cihaz yeniden başlatıldığında veya kablosuz ağ değiştiğinde bağlı durumda kalır veya hemen bağlanır. 

  Her zaman açık VPN'yi tüm VPN istemcilerinde devre dışı bırakmak için **Yapılandırılmadı**'yı seçin.

  > [!IMPORTANT]
  > Bir cihaza yalnızca bir tane Her Zaman Açık VPN ilkesi dağıttığınızdan emin olun. Bir cihaza birden çok Her Zaman Açık VPN ilkesi dağıtma desteklenmez.

- **VPN istemcisi**: Her zaman açık ' ı destekleyen bir VPN istemcisi seçin. Seçenekleriniz şunlardır:
  - Cisco AnyConnect
  - F5 Access
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Özel
    - **Paket kimliği**: Google Play deposundaki uygulamanın paket KIMLIĞINI girin. Örneğin Play mağazasındaki uygulamanın URL'si `https://play.google.com/store/details?id=com.contosovpn.android.prod` ise, paket kimliği `com.contosovpn.android.prod` olur.

  > [!IMPORTANT]
  > - Seçtiğiniz VPN istemcisinin cihaza yüklenmesi ve cihazın uygulama başına VPN iş profillerini desteklemesi gerekir. Aksi takdirde bir hata oluşur. 
  > - VPN istemci uygulamasını yine de **Yönetilen Google Play Mağazası**'nda onaylamanız, uygulamayı Intune ile eşitlemeniz ve cihaza dağıtmanız gerekir. Bu yapıldıktan sonra uygulama kullanıcının iş profiline yüklenir.
  > - Bilinen sorunlar vardır uygulama başına VPN Android 3.0.4 için F5'e erişim ile kullanırken. Bkz: [Android 3.0.4 için F5'e erişim için F5'ın sürüm notları](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android) daha fazla bilgi için.

- **Kilitleme modu**: Tüm ağ trafiğini VPN tünelini kullanacak şekilde zorlamak için **Etkinleştir** ' i seçin. VPN'e bir bağlantı oluşturulmazsa, cihazın ağ erişimi olmaz.

  Trafiğin VPN tünelinden veya mobil ağdan akmasına izin vermek için **Yapılandırılmadı**'yı seçin.

## <a name="work-profile-only"></a>Yalnızca iş profili 

### <a name="work-profile-settings"></a>İş profili ayarları

#### <a name="general"></a>Genel

- **İş ve kişisel profiller arasında kopyalama ve yapıştırma**: İş ve kişisel uygulamalar arasında kopyalamayı ve yapıştırmayı engellemek için **Engelle** ' yi seçin. **Yapılandırılmamış** kullanıcıların kişisel profildeki uygulamalarla kopyalama ve yapıştırma kullanarak veri paylaşmasına izin verir 
- **İş ve kişisel profiller arasında veri paylaşımı**: İş profilindeki uygulamaların kişisel profildeki uygulamalarla paylaşıp paylaşamayacağına seçin. Örneğin, uygulamalar içindeki paylaşma eylemler gibi denetleyebilirsiniz **Paylaş...** seçeneği gibi uygulamalardaki paylaşma eylemlerini denetler. Bu ayar, kopyala/yapıştır pano davranışında geçerli değildir. Paylaşım Seçenekleriniz şunlardır:
  - **Varsayılan paylaşım kısıtlamaları**: Cihazın, Android sürümüne bağlı olarak farklılık gösteren varsayılan paylaşım davranışı. Kişisel profilden iş profiline paylaşmaya varsayılan olarak izin verilir. Buna karşın iş profilinden kişisel profile paylaşma varsayılan olarak engellenir. Bu ayar, iş profilinden kişisel profile veri paylaşılmasını önler. Sürüm 6.0 ve üzerini çalıştıran cihazlarda Google kişisel profilden iş profiline paylaşımı engellemez.
  - **İş profilindeki uygulamalar, kişisel profilden gelen paylaşım isteklerini işleyebilir**: Kişisel ve iş profilinden paylaşıma izin veren yerleşik Android özelliğini sağlar. Etkinleştirildiğinde, kişisel profildeki bir uygulamadan gelen bir paylaşım isteği, iş profilindeki uygulamalarla paylaşım kullanabilir. Bu ayar, 6.0 öncesi sürümleri çalıştıran Android cihazlarının varsayılan davranışıdır.
  - **Sınırlar arasında paylaşıma Izin ver**: Her iki yönde de iş profili sınırları genelinde paylaşıma izin vermez. Bu ayarı seçtiğinizde, iş profilinizdeki uygulamalar kişisel profildeki rozetsiz uygulamalar ile veri paylaşabilir. Bu ayar iş profilindeki yönetilen uygulamaların cihazın yönetilmeyen kısmındaki uygulamalarla paylaşmasına izin verir. Bu nedenle bu ayarı dikkatli kullanın.

- **Cihaz kilitliyken iş profili bildirimleri**: Cihaz kilitlendiğinde iş profilindeki uygulamaların bildirimler halinde verileri gösterip gösteremeyeceğini denetler. **Blok** verileri göstermez. **Yapılandırılmamış** verileri gösterir.
- **Varsayılan uygulama izinleri**: İş profilindeki tüm uygulamalar için varsayılan izin ilkesini ayarlar. Android 6 ile başlayarak, kullanıcıdan, belirli uygulamalar açıldığında bunlar için gereken bazı izinleri vermesi istenir. Bu ilke ayarı, kullanıcıdan iş profilindeki tüm uygulamalar için izin istenip istenmeyeceğini belirlemenize olanak tanır. Örneğin, iş profiline konum erişimi gerektiren bir uygulama atarsınız. Normalde bu uygulama kullanıcıdan konum erişimini onaylamasını veya reddetmesini ister. Bu ilkeyi istem kullanmadan otomatik olarak izinler vermek, izin vermeyi reddetmek veya kararı kullanıcıya bırakmak için kullanabilirsiniz. Aşağıdakilerden birini seçin:
  - **Cihaz varsayılanı**
  - **Sor**
  - **Otomatik olarak izin ver**
  - **Otomatik olarak reddet**

  Ayrıca tek tek uygulamalara izinler vermek için bir Uygulama Yapılandırma ilkesi de kullanabilirsiniz (**İstemci Uygulamaları** > **Uygulama yapılandırma ilkeleri**).

- **Hesap ekleme ve kaldırma**: Son kullanıcıların iş profilinde hesapları el ile eklemesini veya kaldırmasını engellemek için **Engelle** ' yi seçin. Örneğin, Gmail uygulamasını bir Android iş profiline dağıttığınızda, son kullanıcıların bu iş profiline hesap eklemesini veya buradan kaldırmasını engelleyebilirsiniz. **Yapılandırılmamış** iş profilinde hesap ekleme sağlar.  

- **Bluetooth Ile kişi paylaşımı**: , Bluetooth kullanılarak eşleştirilmiş bir otomobil gibi başka bir cihazdan iş kişilerine erişim sağlar. Bu ayar varsayılan olarak yapılandırılmamıştır ve iş profili kişileri gösterilmez. Bu paylaşıma izin verip iş profili kişilerini görüntülemek için **Etkinleştir**’i seçin. Bu ayar, Android OS v6.0 ve üzeri sürümlerde Android iş profili cihazları için geçerlidir. Bu ayarı etkinleştirmek, bazı Bluetooth cihazlarının ilk bağlantı sırasında iş kişilerini önbelleğe almasına izin verebilir. İlk eşleme/eşitleme sonrasına bunu devre dışı bırakmak ise Bluetooth cihazından iş kişilerini kaldırmayabilir.

- **Ekran yakalama**: Çalışma profilindeki cihazda ekran görüntülerini veya ekran yakalamalarını engellemek için **Engelle** ' yi seçin. Ayrıca güvenli bir video çıkışına sahip olmayan görüntü cihazlarında gösterilen içeriği engeller. **Yapılandırılmamış** ekran görüntüleri alma sağlar.

- **Kişisel profilde iş kişisi arayan kimliğini görüntüle**: Etkinleştirildiğinde (**yapılandırılmadığında**), iş iletişim çağıranu ayrıntıları kişisel profilde görüntülenir. Ayarlandığında **blok**, iş kişisi arayan numarası kişisel profilde görüntülenmez. Android işletim sistemi v6.0 ve daha yeni sürümlerde geçerlidir.

- **Kişisel profilden iş kişilerini ara**: Kullanıcıların kişisel profildeki uygulamalarda iş kişilerini aramasını engellemek için **Engelle** ' yi seçin. **Gerekli değil** iş kişilerini Kişisel profildeki arama sağlar.

- **Kamera**: İş profilindeki cihazdaki kameraya erişimi engellemek için **Engelle** ' yi seçin. Kişisel taraftaki kamera, bu ayardan etkilenmez. **Gerekli değil** iş profilinde kameraya erişim sağlar.

#### <a name="work-profile-password"></a>İş profili parolası

- **Iş profili parolası gerektir**: İş profili etkinken Android 7,0 ve üzeri için geçerlidir. Seçin **gerektiren** yalnızca iş profilindeki uygulamalar için geçerli bir geçiş kodu ilkesi girmek için. Varsayılan olarak, son kullanıcı birbirinden ayrı tanımlanmış iki PIN kullanabilir veya PIN’leri iki PIN'den daha güçlü olanın altında birleştirmeyi seçebilir. **Yapılandırılmamış** iş uygulamaları, parola girmeden kullanmasına izin verir.
- **Minimum parola uzunluğu**: Kullanıcının parolasının olması gereken en az karakter sayısını **4**-**16**' dan girin.
- **İş profili kilitlenmeden önce geçen işlem yapılmayan dakika sayısı**: İş profili kilitlenmeden önce geçen süreyi seçin. Daha sonra kullanıcının kimlik bilgilerini girerek tekrar erişim kazanması gerekir.
- **Cihaz silinmeden önceki oturum açma hatası sayısı**: İş profili cihazdan silinmeden önce, kaç kez hatalı parola girilebileceğini girin.
- **Parola zaman aşımı (gün sayısı)** : Son Kullanıcı parolasının değiştirilmesi gereken gün sayısını girin ( **1**-**255**arasında).
- **Gerekli parola türü**: Cihazda ayarlanması gereken parola türünü seçin. Aşağıdakilerden birini seçin:
  - **Cihaz varsayılanı**
  - **Düşük güvenlik biyometriği**
  - **Gerekli**
  - **En az sayısal**
  - **Sayısal karmaşıklık**: ' 1111 ' veya ' 1234 ' gibi yinelenen veya ardışık sayılara izin verilmez
  - **En az alfabetik**
  - **En az alfasayısal**
  - **En az simgeler ile alfasayısal**
- **Önceki parolaların yeniden kullanılmasını engelleme**: Eski bir parolanın yeniden kullanılabilmesi için kullanılması gereken yeni parola sayısını girin ( **1**-**24**arasında).
- **Parmak izi ile kilit açma**: Son kullanıcıların cihazın kilidini açmak için cihaz parmak izi tarayıcısını kullanmasını engellemek için **Engelle** ' yi seçin. **Yapılandırılmamış** kullanıcıların cihazların iş profilindeki bir parmak izi ile kilit açma olanak sağlar.
- **Akıllı kilit ve diğer güven aracıları**: Akıllı Kilit veya diğer güven aracılarının uyumlu cihazlarda kilit ekranı ayarlarını değiştirmesine engel olmak için **Engelle** ' yi seçin. Bazen bir güven aracısı olarak da bilinen bu özelliği devre dışı bırakın veya cihaz güvenilir bir konumda, cihazın kilitleme ekranı parolasını atlamanıza izin verir. Örneğin cihaz belirli bir Bluetooth cihazına bağlıyken ya da bir NFC etiketinin yakınındayken iş profili parolasını atlama. Bu ayarı, kullanıcıların Akıllı Kilit'i yapılandırmasını önlemek için kullanın.

### <a name="device-password"></a>Cihaz parolası

Bu parola ayarlar, bir iş profili kullanan cihazlardaki kişisel profiller için geçerlidir.

- **Minimum parola uzunluğu**: Kullanıcı parolasının, **4**-**14**arasından olması gereken en az karakter sayısını girin.
- **Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı**: Etkin olmayan bir cihaz otomatik olarak kilitlenmeden önce geçen süreyi seçin
- **Cihaz silinmeden önceki oturum açma hatası sayısı**: Tüm veriler cihazdan temizlenmeden önce, kaç kez yanlış parola girilebileceğini girin
- **Parola zaman aşımı (gün sayısı)** : Son Kullanıcı parolasının değiştirilmesi gereken gün sayısını girin ( **1**-**255**arasında)
- **Gerekli parola türü**: Cihazda ayarlanması gereken parola türünü seçin. Aşağıdakilerden birini seçin:
  - **Cihaz varsayılanı**
  - **Düşük güvenlik biyometriği**
  - **Gerekli**
  - **En az sayısal**
  - **Sayısal karmaşıklık**: ' 1111 ' veya ' 1234 ' gibi yinelenen veya ardışık sayılara izin verilmez
  - **En az alfabetik**
  - **En az alfasayısal**
  - **En az simgeler ile alfasayısal**
- **Önceki parolaların yeniden kullanılmasını engelleme**: Eski bir parolanın yeniden kullanılabilmesi için kullanılması gereken yeni parola sayısını girin ( **1**-**24**arasında).
- **Parmak izi ile kilit açma**: Son kullanıcının cihazın kilidini açmak için cihaz parmak izi tarayıcısını kullanmasını engellemek için **Engelle** ' yi seçin. **Yapılandırılmamış** parmak izi kullanarak cihaz kilidini açmak kullanıcının sağlar.
- **Akıllı kilit ve diğer güven aracıları**: Akıllı Kilit veya diğer güven aracılarının uyumlu cihazlarda kilit ekranı ayarlarını değiştirmesine engel olmak için **Engelle** ' yi seçin. Bazen bir güven aracısı olarak da bilinen bu özelliği devre dışı bırakın veya cihaz güvenilir bir konumda, cihazın kilitleme ekranı parolasını atlamanıza izin verir. Örneğin cihaz belirli bir Bluetooth cihazına bağlıyken ya da bir NFC etiketinin yakınındayken iş profili parolasını atlama. Bu ayarı, kullanıcıların Akıllı Kilit'i yapılandırmasını önlemek için kullanın.

### <a name="system-security"></a>Sistem güvenliği

- **Uygulamalarda tehdit taraması**: **Gerektir** , iş ve kişisel profiller Için **uygulamaları doğrula** ayarının etkinleştirilmesini zorunlu kılar.

   > [!Note]
   > Bu ayar yalnızca Android O ve üstü cihazlarda çalışır.

### <a name="connectivity"></a>Bağlantı

- **Her zaman VPN**: VPN istemcisini otomatik olarak bağlanıp VPN 'ye yeniden bağlanacak şekilde ayarlamak için **Etkinleştir** ' i seçin. Her Zaman Açık VPN bağlantıları; kullanıcı cihazı kilitlediğinde, cihaz yeniden başlatıldığında veya kablosuz ağ değiştiğinde bağlı durumda kalır veya hemen bağlanır. 

  Her zaman açık VPN'yi tüm VPN istemcilerinde devre dışı bırakmak için **Yapılandırılmadı**'yı seçin.

  > [!IMPORTANT]
  > Bir cihaza yalnızca bir tane Her Zaman Açık VPN ilkesi dağıttığınızdan emin olun. Bir cihaza birden çok Her Zaman Açık VPN ilkesi dağıtma desteklenmez.

- **VPN istemcisi**: Her zaman açık ' ı destekleyen bir VPN istemcisi seçin. Seçenekleriniz şunlardır:
  - Cisco AnyConnect
  - F5 Access
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Özel
    - **Paket kimliği**: Google Play deposundaki uygulamanın paket KIMLIĞINI girin. Örneğin Play mağazasındaki uygulamanın URL'si `https://play.google.com/store/details?id=com.contosovpn.android.prod` ise, paket kimliği `com.contosovpn.android.prod` olur.

  > [!IMPORTANT]
  > - Seçtiğiniz VPN istemcisinin cihaza yüklenmesi ve cihazın uygulama başına VPN iş profillerini desteklemesi gerekir. Aksi takdirde bir hata oluşur. 
  > - VPN istemci uygulamasını yine de **Yönetilen Google Play Mağazası**'nda onaylamanız, uygulamayı Intune ile eşitlemeniz ve cihaza dağıtmanız gerekir. Bu yapıldıktan sonra uygulama kullanıcının iş profiline yüklenir.
  > - Bilinen sorunlar vardır uygulama başına VPN Android 3.0.4 için F5'e erişim ile kullanırken. Bkz: [Android 3.0.4 için F5'e erişim için F5'ın sürüm notları](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android) daha fazla bilgi için.

- **Kilitleme modu**: Tüm ağ trafiğini VPN tünelini kullanacak şekilde zorlamak için **Etkinleştir** ' i seçin. VPN'e bir bağlantı oluşturulmazsa, cihazın ağ erişimi olmaz.

  Trafiğin VPN tünelinden veya mobil ağdan akmasına izin vermek için **Yapılandırılmadı**'yı seçin.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).

Ayrıca, [Android](device-restrictions-android.md#kiosk) ve [Windows 10](kiosk-settings.md) cihazları için adanmış cihaz bilgi noktası profilleri oluşturabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Intune Android kurumsal cihazlarını yapılandırma ve sorunlarını giderme](https://support.microsoft.com/help/4476974)
