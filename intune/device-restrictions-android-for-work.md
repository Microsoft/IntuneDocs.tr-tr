---
title: Microsoft Intune - Azure’da Android iş profili cihaz kısıtlamaları | Microsoft Docs
description: Android Kurumsal profili cihazlarda kopyalama ve yapıştırma, bildirim gösterme, uygulama izinleri, veri paylaşımı, parola uzunluğu, oturum açma hataları, kilidi açmak için parmak izi kullanma, parolaları yeniden kullanma ve iş kişileriyle Bluetooth paylaşımını etkinleştirme gibi bazı ayarları kısıtlayabilirsiniz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 5f153e738aff28cae6481c0502f0682d10b8f104
ms.sourcegitcommit: ecd6aebe50b1440a282dfdda771e37fbb8750d42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2018
ms.locfileid: "52729101"
---
# <a name="work-device-restriction-settings-in-intune"></a>Intune'da Work cihaz kısıtlama ayarları

Bu makalede, Android Kurumsal profilli cihazlar için yapılandırabileceğiniz Microsoft Intune cihaz kısıtlama ayarları listelenmektedir.

## <a name="device-owner-only"></a>Yalnızca cihaz sahibi

### <a name="general-settings"></a>Genel ayarlar

- **Ekran Yakalama**: seçin **blok** cihazın ekran veya ekran görüntüleri önlemek için. Ayrıca güvenli bir video çıkışına sahip olmayan görüntü cihazlarında gösterilen içeriği engeller. **Yapılandırılmamış** kullanıcının ekran içeriğini resim olarak yakalamasına izin verir.
- **Kamera**: seçin **blok** için cihaz kameranızı erişimi engellemek için. **Gerekli değil** cihazın kamerasını erişmesini sağlar.
- **Varsayılan izin ilkesi**: Bu ayar, çalışma zamanı izin istekleri için varsayılan izin ilkesini tanımlar. Olası değerler şöyledir:
  - **Cihaz varsayılanı**: Cihazın varsayılan ayarını kullanın.
  - **İstem**: Kullanıcıdan izni onaylaması istenir.
  - **Otomatik olarak izin ver**: İzinler otomatik olarak verilir.
  - **Otomatik olarak reddet**: İzinler otomatik reddedilir.
- **Tarih ve saat değişikliklerini**: seçin **blok** kullanıcıların el ile tarih ve saat ayarından önlemek için. **Yapılandırılmamış** ayarlanmış tarih ve saat için kullanıcıların cihazda izin verir.
- **Ses düzeyi değişiklikleri**: Kullanıcıların cihaz ses düzeyini değiştirmesini önlemek için **Engelle** olarak ayarlayın. **Yapılandırılmamış** cihazda birim ayarlarını kullanımına izin verir.
- **Fabrika sıfırlaması**: seçin **blok** sıfırlama seçeneği cihazın Ayarları'nda kullanıcıların Fabrika kullanmasını önlemek için. **Yapılandırılmamış** Bu ayar cihazda kullanmasına olanak tanır.
- **Güvenli önyükleme**: Kullanıcıların cihazı güvenli moda önyüklemesini önlemek için **Engelle** olarak ayarlayın. **Yapılandırılmamış** kullanıcılar güvenli modda cihazın yeniden başlatılmasına izin verir.
- **Durum çubuğu**: seçin **blok** durum çubuğu, bildirimler ve hızlı ayarlar dahil olmak üzere erişimi engellemek için. **Yapılandırılmamış** kullanıcıların durum çubuğuna erişimi sağlar.
- **Veri Hizmetleri**: seçin **blok** hücresel ağ üzerinde veri dolaşımını önlemek için. **Yapılandırılmamış** cihaz hücresel ağ kullanırken veri dolaşımına izin verir.
- **Wi-Fi ayar değişiklikleri**: seçin **blok** kullanıcıların cihaz sahibi tarafından oluşturulan Wi-Fi ayarları değiştirmesini önlemek için. Kullanıcılar kendi Wi-Fi yapılandırmalarını oluşturabilir. **Yapılandırılmamış** kullanıcıların cihazda Wi-Fi ayarlarını değiştirmesine olanak tanır.
- **Wi-Fi erişim noktası yapılandırması**: seçin **blok** kullanıcıların oluşturma veya herhangi bir Wi-Fi yapılandırması değiştirmesini önlemek için. **Yapılandırılmamış** kullanıcıların cihazda Wi-Fi ayarlarını değiştirmesine olanak tanır.
- **Bluetooth yapılandırma**: seçin **blok** kullanıcıların cihazda Bluetooth yapılandırmasını önlemek için. **Yapılandırılmamış** cihazda Bluetooth'un kullanımına izin verir.
- **Bluetooth ile kişi paylaşımı**: seçin **blok** kişiler bir Android cihaz Bluetooth kullanarak eşleştirilmiş bir araba sistemi gibi başka bir CİHAZDAN iş erişimi önlemek için. **Yapılandırılmamış** kişiler Android cihaza eşleştirilmiş başka bir Bluetooth cihazına çalışmak erişim sağlar.
- **İnternet paylaşımı ve erişimi noktalarına**: seçin **blok** taşınabilir etkin noktalarına internet paylaşımı ve erişimi önlemek için. **Yapılandırılmamış** internet paylaşımı ve taşınabilir noktalarına erişim sağlar.
- **USB depolamasını**: seçin **izin** cihazdaki USB depolama erişim için. **Yapılandırılmamış** USB depolama alanına erişimini engeller.
- **USB dosya aktarımı**: seçin **blok** önlemek için USB üzerinden dosyaları aktarma. **Yapılandırılmamış** dosyaları aktarma sağlar.
- **Dış medya**: seçin **blok** kullanarak veya CİHAZDAN Dış medya bağlanma önlemek için. **Yapılandırılmamış** Dış medya cihazda izin verir.
- **NFC kullanarak verileri ışın**: seçin **blok** yakın alan iletişimi (NFC) teknolojisini kullanarak ışını veri uygulamalardan önlemek için. **Yapılandırılmamış** cihazlar arasında veri paylaşımı için NFC kullanımına izin verir.
- **Hata ayıklama özellikleri**: seçin **izin** kullanıcıların cihazda hata ayıklama özelliklerini kullanın. **Yapılandırılmamış** kullanıcıların cihazda hata ayıklama özelliklerini kullanmasını önler.
- **Mikrofon Ayarlama**: seçin **blok** mikrofonun sesinin açılmasını ve mikrofon ses kullanıcıların önlemek için. **Yapılandırılmamış** kullanma ve cihazda mikrofon ses ayarlamak izin verir.
- **Fabrika ayarlarına sıfırlama koruması e-postaları**: seçin **Google hesabı e-posta adresleri**. Bunu temizlendikten sonra cihazın kilidini açmak cihaz yöneticilerinin e-posta adreslerini girin. E-posta adresi gibi bir noktalı virgül ile ayırın mutlaka `admin1@gmail.com;admin2@gmail.com`. E-posta değil girdiyseniz, fabrika ayarlarına geri yüklendikten sonra herkes cihazın kilidini açabilirsiniz.
- **Ağ kaçış noktası**: seçin **etkinleştirme** ağ kaçış tarama özelliğini etkinleştirmek kullanıcılara izin vermek için. Cihaz önyüklendiğinde bir ağ bağlantısı olmayan yaptıysanız, kaçış noktası geçici olarak bir ağa bağlayın ve cihaz ilkesini yenilemek sorar. Bu ilke uygulandıktan sonra geçici ağ unutulur ve cihaz önyüklemeye devam eder. Bu özellik, cihazları ağa bağlanır:
  - Son ilkede uygun bir ağ yok.
  - Cihaz uygulama kilidi görev modunda önyüklenir.
  - Kullanıcı cihaz ayarları ulaşamıyor.

  **Yapılandırılmamış** kullanıcıların cihazdaki ağ kaçış tarama özelliği kapatmasını engeller.

- **Bilinmeyen kaynaklardan yüklemeye izin ver**: seçin **izin** kullanıcılar açabilir **bilinmeyen kaynaklar**. Bu ayar, bilinmeyen kaynaklardan yüklemeye uygulamalar sağlar. **Yapılandırılmamış** kullanıcıların açılmasını engeller **bilinmeyen kaynaklar**.
- **Sistem Güncelleştirmesi**: cihaz havadan güncelleştirmeler nasıl işlediğini tanımlamak için bir seçenek belirleyin:
  - **Cihaz Varsayılanı**: Cihazın varsayılan ayarını kullanın.
  - **Otomatik**: Güncelleştirmeler, kullanıcı etkileşimi olmadan otomatik olarak yüklenir. Bu ilkeyi seçmek, bekleyen tüm güncelleştirmeleri hemen yükler.
  - **Erteleme**: Güncelleştirmeler 30 gün boyunca ertelenir. 30 günün sonunda, Android güncelleştirmeyi yüklemek için kullanıcıya sorar. Cihaz üreticilerin veya taşıyıcıların önemli güvenli güncelleştirmelerinin ertelenmesini engellemek (muaf tutmak) mümkündür. Muaf tutulan bir güncelleştirme cihazda kullanıcıya bir sistem bildirimi gösterir. 
  - **Bakım penceresi**: Güncelleştirmeleri Intune'da ayarladığınız bir günlük bakım penceresi içinde otomatik olarak yükler. Yükleme 30 gün boyunca her gün çalışır ve yeterli alan veya pil düzeyleri varsa başarısız olabilir. 30 gün sonra kullanıcıyı uygulamayı yüklemek için Android ister. Bu pencere ayrıca Oynatma uygulamalarının güncelleştirmelerini yüklemek için de kullanılır. Tek uygulama bilgi noktası ön plan uygulamaları güncelleştirilebilir gibi gibi bilgi noktaları, adanmış cihazlar için bu seçeneği kullanın.
- **Otomatik uygulama güncelleştirmeleri**: Otomatik Güncelleştirmeler yüklü olduğunda seçin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı**
  - **Kullanıcı Seçimi**
  - **hiçbir zaman**
  - **Wi-Fi yalnızca**
  - **Her zaman**

### <a name="system-security-settings"></a>Sistem güvenliği ayarları

- **Uygulamalarda tehdit taraması**: **gerektiren** , zorlar **uygulamaları doğrula** iş ve kişisel profiller için seçeneği etkinleştirilmiştir.

### <a name="kiosk-settings"></a>Bilgi noktası ayarları

Bir cihazı tek bir uygulama veya birçok uygulamalarını çalıştırmak için yapılandırabilirsiniz. Yalnızca eklediğiniz uygulamalar bir cihaz bilgi noktası modunda olduğunda kullanılabilir.

**Bilgi noktası modu**: cihaz bir uygulama ya da birden fazla uygulama çalışıp çalışmayacağını seçin.

- **Tek uygulama bilgi noktası**: kullanıcılar cihazda tek bir uygulama yalnızca erişim sağlayabilir. Cihaz başlatıldığında, yalnızca belirli uygulamayı başlatır. Kullanıcılar yeni uygulamalar açamaz veya çalışan uygulamayı değiştiremez.

  **Adımları**
  1. Seçin **bir yönetilen uygulama seçin**, yönetilen Google Play uygulaması listeden seçin. 

      Ardından, listelenen tüm uygulamalar yoksa [bazı Android uygulamaları ekleme](apps-add-android-for-work.md) cihaza. Mutlaka [uygulama bilgi noktası cihazlarınız için oluşturduğunuz cihaz grubuna atama](apps-deploy.md).

  2. Seçin **Tamam** > **Tamam** seçerek uygulamayı ekleyin.

- **Çoklu uygulama bilgi noktası**: kullanıcılar cihazda uygulamalar sınırlı sayıda erişim sağlayabilir. Cihaz başlatıldığında, yalnızca eklediğiniz uygulamalar başlatın. Ayrıca, kullanıcılar açabilir bazı web bağlantıları da ekleyebilirsiniz. İlkenin geçerli olduğu kullanıcı giriş ekranında simgeleri için izin verilen uygulamalar görürsünüz.

  > [ÖNEMLİ] Çoklu uygulama bilgi noktası cihazları için [giriş ekranı yönetilen uygulama](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise) Google play'den **olmalıdır**:
  >   - [Bir istemci uygulaması olarak eklenen](apps-add-android-for-work.md) ıntune
  >   - [Cihaz grubuna atanmış](apps-deploy.md) bilgi noktası cihazlarınız için oluşturuldu
  > 
  > **Giriş ekranı yönetilen** uygulama yapılandırma profilinde de olması için gerekli değildir, ancak bir istemci uygulaması olarak eklenmesi için gereklidir. Zaman **giriş ekranı yönetilen** uygulama, bir istemci uygulaması olarak eklenir, simgeler olarak gösterilir configiration profilinde eklediğiniz diğer tüm uygulamalar **giriş ekranı yönetilen** uygulama. 

  - Seçin **Ekle**ve uygulamalarınızı listeden seçin.

    Varsa **giriş ekranı yönetilen** uygulama listelenmez, ardından [Google Play'den ekleme](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise). Mutlaka [uygulamayı atamak](apps-deploy.md) bilgi noktası cihazlarınız için oluşturduğunuz cihaz grubuna.

    Ayrıca diğer ekleyebilirsiniz [Android uygulamaları](apps-add-android-for-work.md) ve [web uygulamaları](web-app.md) cihazla kuruluşunuz tarafından oluşturulmuş. Mutlaka [uygulama bilgi noktası cihazlarınız için oluşturduğunuz cihaz grubuna atama](apps-deploy.md).

  - **Sanal giriş düğmesi**: seçin **etkinleştirme** bilgi noktası cihazı giriş düğmesi gösterilecek. Kullanıcıların uygulamalar arasında kolayca geçiş yapabilirsiniz için bu onay kutusu seçildiğinde, cihazın giriş ekranına kullanıcı döndürür. Bazı Android cihazlarda, kullanıcıların giriş düğmesini göster ekranda yukarı a doğru çekin gerekebilir. **Devre dışı** kullanıcılar, uygulamalar arasında geçiş yapmak için geri düğmesini kullanmalısınız bir giriş düğmesi göstermez.
  - **Bilgi noktası modu bırakın**: seçin **etkinleştirme** yöneticilerin bilgi noktası modu cihaz güncelleştirmek için geçici olarak duraklatmak sağlamak için. Bu özelliği kullanmak için yönetici şunları yapar: 
  
    1. "Çıkış noktası" düğmesini gösterilen kadar geri düğmesini seçmek devam edin. 
    2. Düğmeyi seçin ve girin **bırakın bilgi noktası modu kodu** PIN.
    3. Değişiklikleriniz bittiğinde seçin **giriş ekranı yönetilen** uygulama. Bu adım, cihazı çoklu uygulama bilgi noktası moduna relocks. 
    
    **Devre dışı** bilgi noktası modu duraklatma özelliği vermez. Yönetici geri düğmesini seçmek devam eder ve devre dışı "Çıkış noktası" düğmesini seçerse bir ileti bir geçiş kodu gerekli olduğunu belirtir.
    
    - **Bilgi noktası modu kod**: girin 4-6 basamaklı sayısal PIN. Yönetici bu PIN'i geçici olarak bilgi noktası modu duraklatmak için kullanır.
 
  - **Özel URL arka plan ayarlamak**: bilgi noktası cihazı üzerinde arka plan ekranı özelleştirmek için bir URL girin.

### <a name="device-password-settings"></a>Cihaz parola ayarları

- **Tuş korumasını**: seçin **devre dışı** kullanır, cihazda tuş korumasını kilit ekranı özelliğini kullanmasını önlemek için. **Yapılandırılmamış** tuş korumasını özelliklerine izin verir.
- **Gerekli parola türü**: Cihaz için gerekli parola türünü tanımlayın. Seçenekleriniz şunlardır:
  - **En az sayısal**
  - **Sayısal karmaşık**: "1111" veya "1234" gibi yinelenen veya ardışık numaralara izin verilmiyor.
  - **En az alfabetik**
  - **En az alfasayısal**
  - **En az simgeler ile alfasayısal**
- **Minimum parola uzunluğu**: parola gerekir girin (4 ile 16 karakter arasında) bir kullanıcı alt sınırını girin.
- **Cihaz silinmeden önceki oturum açma hatası sayısı**: (1-11 arasında) cihaz temizlenmeden önce izin başarısız oturum açma işlemlerinin sayısını girin.

### <a name="power-settings"></a>Güç ayarları

- **Ekran kilitlenme süresi**: Cihaz kilitlenmeden önce boşta geçmesi gereken süreyi belirtin.
- **Cihaz prize takılıyken ekran açık**: Cihaz prize takılıyken hangi güç kaynaklarının ekranın açık kalmasına neden olacağını seçin.

### <a name="users-and-accounts-settings"></a>Kullanıcılar ve Hesaplar ayarları

- **Yeni kullanıcı ekle**: Kullanıcıların yeni kullanıcı eklemesini önlemek için **Engelle** olarak ayarlayın. Her kullanıcının cihazda özel giriş ekranları, hesaplar, uygulamalar ve ayarlar için kişisel bir alanı vardır. **Yapılandırılmamış** kullanıcıların diğer kullanıcıların cihaza eklemesini sağlar.
- **Kullanıcı kaldırma**: Kullanıcıların kullanıcı kaldırmasını önlemek için **Engelle** olarak ayarlayın. **Yapılandırılmamış** CİHAZDAN diğer kullanıcıları kaldırma olanağı sağlar.
- **Hesap değişiklikleri**: Kullanıcıların hesaplarda değişiklik yapmasını önlemek için **Engelle** olarak ayarlayın. **Yapılandırılmamış** kullanıcıların cihazda kullanıcı hesaplarını güncelleştirmek sağlar.

## <a name="work-profile-only"></a>Yalnızca iş profili 

### <a name="work-profile-settings"></a>İş profili ayarları

#### <a name="general"></a>Genel

- **İş ve Kişisel Profiller arasında kopyalama ve yapıştırma**: seçin **blok** Kopyala ve Yapıştır iş ve kişisel uygulamalar arasında önlemek için. **Yapılandırılmamış** kullanıcıların kişisel profildeki uygulamalarla kopyalama ve yapıştırma kullanarak veri paylaşmasına izin verir 
- **İş ve Kişisel Profiller arasında veri paylaşımı**: iş profilindeki uygulamalar kişisel profildeki uygulamalarla paylaşıp seçin. Örneğin, uygulamalar içindeki paylaşma eylemler gibi denetleyebilirsiniz **Paylaş...** seçeneği gibi uygulamalardaki paylaşma eylemlerini denetler. Bu ayar, kopyala/yapıştır pano davranışında geçerli değildir. Paylaşım Seçenekleriniz şunlardır:
  - **Varsayılan paylaşım kısıtlamaları**: Cihazın, Android sürümüne göre farklılık gösteren varsayılan paylaşım davranışı. Kişisel profilden iş profiline paylaşmaya varsayılan olarak izin verilir. Buna karşın iş profilinden kişisel profile paylaşma varsayılan olarak engellenir. Bu ayar, iş profilinden kişisel profile veri paylaşılmasını önler. Sürüm 6.0 ve üzerini çalıştıran cihazlarda Google kişisel profilden iş profiline paylaşımı engellemez.
  - **İş profilindeki uygulamalar kişisel profilden gelen paylaşım isteklerini işleyebilir**: Kişisel profilden iş profiline paylaşıma izin veren yerleşik Android özelliğini etkinleştirir. Etkinleştirildiğinde, kişisel profildeki bir uygulamadan gelen bir paylaşım isteği, iş profilindeki uygulamalarla paylaşım kullanabilir. Bu ayar, 6.0 öncesi sürümleri çalıştıran Android cihazlarının varsayılan davranışıdır.
  - **Sınırlar arası paylaşıma izin ver**: İş profili sınırının ötesinde her iki yönde paylaşımı etkinleştirir. Bu ayarı seçtiğinizde, iş profilinizdeki uygulamalar kişisel profildeki rozetsiz uygulamalar ile veri paylaşabilir. Bu ayar iş profilindeki yönetilen uygulamaların cihazın yönetilmeyen kısmındaki uygulamalarla paylaşmasına izin verir. Bu nedenle bu ayarı dikkatli kullanın.

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

#### <a name="work-profile-password"></a>İş profili parolası

- **İş Profili Parolası Gerektir**: İş profilinin etkinleştirildiği Android 7.0 ve üzerine uygulanır. Seçin **gerektiren** yalnızca iş profilindeki uygulamalar için geçerli bir geçiş kodu ilkesi girmek için. Varsayılan olarak, son kullanıcı birbirinden ayrı tanımlanmış iki PIN kullanabilir veya PIN’leri iki PIN'den daha güçlü olanın altında birleştirmeyi seçebilir. **Yapılandırılmamış** iş uygulamaları, parola girmeden kullanmasına izin verir.
- **En düşük parola uzunluğu**: Kullanıcı parolalarında olması gereken en düşük rakam veya karakter sayısını **4**-**16** arasından belirtin.
- **İş profili kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı**: İş profili kilitlenmeden önce geçmesi gereken süreyi seçin. Daha sonra kullanıcının kimlik bilgilerini girerek tekrar erişim kazanması gerekir.
- **Cihaz silinmeden önceki oturum açma hatası sayısı**: İş profili cihazdan silinmeden önce girilebilecek hatalı parola sayısını girin.
- **Parola kullanım süresi sonu (gün)**: Son kullanıcı parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını girin (**1**-**255** arası).
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
- **Akıllı kilit ve diğer güven aracıları**: seçin **blok** ayarlaması kilit ekranı ayarları uyumlu cihazlarda akıllı kilit veya diğer güven aracılarının önlemek için. Bazen bir güven aracısı olarak da bilinen bu özelliği devre dışı bırakın veya cihaz güvenilir bir konumda, cihazın kilitleme ekranı parolasını atlamanıza izin verir. Örneğin cihaz belirli bir Bluetooth cihazına bağlıyken ya da bir NFC etiketinin yakınındayken iş profili parolasını atlama. Bu ayarı, kullanıcıların Akıllı Kilit'i yapılandırmasını önlemek için kullanın.

### <a name="device-password"></a>Cihaz parolası

Bu parola ayarlar, bir iş profili kullanan cihazlardaki kişisel profiller için geçerlidir.

- **En düşük parola uzunluğu**: Kullanıcı parolalarında olması gereken en düşük rakam veya karakter sayısını **4**-**14** arasından belirtin.
- **Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı**: Etkin olmayan bir cihaz otomatik olarak kilitlenmeden önce geçmesi gereken süreyi seçin
- **Cihaz silinmeden önceki oturum açma hatası sayısı**: Tüm veriler cihazdan silinmeden önce girilebilecek hatalı parola sayısını girin
- **Parola kullanım süresi sonu (gün)**: Son kullanıcı parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını girin (**1**-**255** arası)
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
- **Parmak iziyle kilit açma**: seçin **blok** son kullanıcı, cihazın kilidini açmak için cihazın parmak izi tarayıcısını kullanmasını önlemek için. **Yapılandırılmamış** parmak izi kullanarak cihaz kilidini açmak kullanıcının sağlar.
- **Akıllı kilit ve diğer güven aracıları**: seçin **blok** ayarlaması kilit ekranı ayarları uyumlu cihazlarda akıllı kilit veya diğer güven aracılarının önlemek için. Bazen bir güven aracısı olarak da bilinen bu özelliği devre dışı bırakın veya cihaz güvenilir bir konumda, cihazın kilitleme ekranı parolasını atlamanıza izin verir. Örneğin cihaz belirli bir Bluetooth cihazına bağlıyken ya da bir NFC etiketinin yakınındayken iş profili parolasını atlama. Bu ayarı, kullanıcıların Akıllı Kilit'i yapılandırmasını önlemek için kullanın.

### <a name="system-security"></a>Sistem güvenliği

- **Uygulamalarda tehdit taraması**: **gerektiren** , zorlar **uygulamaları doğrula** iş ve kişisel profiller için seçeneği etkinleştirilmiştir.

   > [!Note]
   > Bu ayar yalnızca Android O ve üstü cihazlarda çalışır.

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
  >  - Seçtiğiniz VPN istemcisinin cihaza yüklenmesi ve cihazın uygulama başına VPN iş profillerini desteklemesi gerekir. Aksi takdirde bir hata oluşur. 
  >  - VPN istemci uygulamasını yine de **Yönetilen Google Play Mağazası**'nda onaylamanız, uygulamayı Intune ile eşitlemeniz ve cihaza dağıtmanız gerekir. Bu yapıldıktan sonra uygulama kullanıcının iş profiline yüklenir.
  >  - Android 3.0.3 için F5 Access ile uygulama başına VPN kullanırken karşılaşabileceğiniz bazı bilinen sorunlar vardır. Daha fazla bilgi için bkz. [Android 3.0.3 için F5 Access’e yönelik F5 sürüm notları](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-3.html#relnotes_known_issues_f5_access_android).

- **Kilitleme modu**: Tüm ağ trafiğini VPN tünelini kullanmaya zorlamak için **Etkinleştir**'i seçin. VPN'e bir bağlantı oluşturulmazsa, cihazın ağ erişimi olmaz.

  Trafiğin VPN tünelinden veya mobil ağdan akmasına izin vermek için **Yapılandırılmadı**'yı seçin.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).

Bilgi noktası profilleri de oluşturabilirsiniz [Android](device-restrictions-android.md#kiosk) ve [Windows 10](kiosk-settings.md) cihazlar.
