---
title: Microsoft Intune - Azure’da Windows 10 cihaz kısıtlama ayarları | Microsoft Docs
description: Tüm ayarları ve Windows 10 ve üzeri cihazlarda cihaz kısıtlamaları oluşturmak için bunlara ilişkin açıklamaların listesini bakın. Bu ayarları yapılandırma profilinde de ekran görüntüleri, parola gereksinimleri, bilgi noktası ayarları, depolama, Edge tarayıcısı, Windows defender uygulama denetimi, bulutta, Başlat menüsünde ve diğer Microsoft Intune erişmek için kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 8c62a9e6914402d65b215a1f722289bd5660b739
ms.sourcegitcommit: ecd6aebe50b1440a282dfdda771e37fbb8750d42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2018
ms.locfileid: "52728778"
---
# <a name="windows-10-and-newer-device-restriction-settings-in-microsoft-intune"></a>Microsoft Intune Windows 10 (ve üzeri) cihaz kısıtlama ayarları

Bu makale, listeler ve Windows 10 cihazlar için yapılandırabileceğiniz tüm cihaz kısıtlama ayarları açıklar. Bu ayarları bir cihaz yapılandırma profili eklendiğinde ve sonra atanan veya Microsoft Intune kullanarak cihazlarınızı dağıtılmış.

> [!Note]
> Tüm Windows sürümlerinde bütün ayarlar kullanılabilir değildir

## <a name="general"></a>Genel

- **Ekran Yakalama (yalnızca mobil)**: kullanıcının cihaz ekranını resim olarak yakalamasına izin verir.
- **Kopyala ve Yapıştır (yalnızca mobil)**: izin kopyalama ve yapıştırma cihazda uygulamalar arasında.
- **Elle kayıt kaldırmaya**: kullanıcının iş yeri hesabını CİHAZDAN el ile silmesine olanak sağlar.
  - Bilgisayar Azure AD’ye katılmışsa ve otomatik kayıt etkinse, bu ilke ayarı uygulanmaz. 
  - Bu ilke ayarı, Windows 10 Home çalıştıran bilgisayarlarda geçerli değildir.
- **Elle kök sertifika yüklemesi (yalnızca mobil)**: kullanıcının elle kök sertifikaları ve Ara CAP sertifikaları yüklemesini durdurur.

- **Kamera**: izin verin veya cihazdaki kamera kullanımını engelleyin.
- **OneDrive dosya eşitlemesini**: cihazın dosyaları Onedrive'a eşitlemesini engeller.
- **Çıkarılabilir Depolama Birimi**: SD kartı gibi dış depolama cihazlarının cihazla kullanılıp kullanılamayacağını belirtir.
- **Coğrafi konum**: cihazın konum Hizmetleri bilgilerini kullanıp kullanamayacağını belirtir.
- **Internet paylaşımı**: cihazda Internet bağlantısı paylaşımının kullanımına izin verin.
- **Telefon sıfırlama**: kullanıcının cihazında bir temizleme denetler.
- **USB bağlantısı (yalnızca mobil)**: cihazların USB bağlantısı aracılığıyla dış depolama cihazlarına erişip erişemeyeceğini denetler.
- **Hırsızlık önleme modu (yalnızca mobil)**: Windows Antitheft modunun etkin olup olmadığını yapılandırın.
- **Cortana**: etkinleştirmek veya Cortana sesli Yardımcısını devre dışı bırakın.
- **Ses kaydı (yalnızca mobil)**: cihaz ses kaydedicisinin kullanılmasına izin verilip.
- **Cihaz adı değişikliğine**: son kullanıcı (yalnızca Windows 10 Mobile) cihaz adını değiştirmesini engeller.
- **Sağlama paketleri ekleme**: sağlama paketleri yükleyen çalışma zamanı yapılandırma aracısını engeller.
- **Sağlama paketlerini kaldırma**: sağlama paketlerini kaldıran çalışma zamanı yapılandırma aracısını engeller.
- **Cihaz bulma**: bir cihazın diğer cihazlar tarafından bulunmasını engelleyin.
- **Görev değiştirici (yalnızca mobil)**: cihazdaki görev değiştiriciyi engeller.
- **SIM kart hatası iletişim kutusu (yalnızca mobil)**: hiçbir SIM Kart algılanmazsa cihazda görüntüleme alanından bir hata iletisi engeller.
- **Ink çalışma alanı**: kullanıcıların Ink çalışma alanına erişmesini engelleyin. **Yapılandırılmamış** açar Ink çalışma alanına ve kullanıcının kilit ekranının üstünde kullanmasına izin verilir.
- **Otomatik yeniden dağıtım**: tüm kullanıcı verilerini ve ayarlarını kullanarak yönetim haklarına sahip kullanıcılara **CTRL + Win + R** cihaz kilit ekranında. Cihaz otomatik olarak yeniden yapılandırılacak ve yönetime yeniden kaydedilir.
- **Kullanıcıların (yalnızca Windows Insider) cihaz kurulumu sırasında ağa bağlanmasını gerektiren**: seçin **gerektiren** cihaz Windows 10 kurulumu sırasında geçmiş ağ sayfasına devam etmeden önce bir ağa bağlanacak şekilde. Bu özellik önizlemedeyken bu ayarı kullanmak için Windows Insider derleme 1809 veya sonrası gerekir.

## <a name="password"></a>Parola

- **Parola**: son kullanıcının cihaza erişmek için parola girmesini zorunlu tutun.
  - **Gerekli parola türü**: parola sayısal mı olacağını belirtir. yalnızca ya da alfasayısal.
  - **Minimum parola uzunluğu**: yalnızca Windows 10 Mobile için geçerlidir.
  - **Cihaz silinmeden önceki oturum açma hatası sayısı**: Windows 10 çalıştıran cihazlar için: cihazda BitLocker etkin varsa, BitLocker kurtarma moduna işaretinden sonra başarısız olursa, belirtilen sayıda koymanın ne anlamı var. Cihazda BitLocker etkin değilse, bu ayar geçerli değildir. Windows 10 Mobile çalıştıran cihazlar için: başarısız oturum açma belirttiğiniz sayısından sonra cihaz silinir.
  - **Ekran kilitlenmeden işlem yapılmayan dakika**: ekran kilitlenmeden önce bir cihazın boşta bekleyeceği süreyi belirtir.
  - **Parola süresinin sonu (gün)**: sonra cihaz parolasının değiştirilmesi gereken süreyi belirtir.
  - **Önceki parolaların yeniden kullanılmasını engelle**: önceden kullanılmış ve cihaz tarafından anımsanacak olan parola sayısını belirtir.
  - **Cihaz (yalnızca mobil) boşta kalma durumundan çıktığında parola isteme**: kullanıcı (yalnızca Windows 10 Mobile) cihaz kilidini açmak için bir parola girmesi gerektiğini belirtir.
  - **Basit parolalar**: 1111 ve 1234 gibi basit parolaların kullanımına olanak sağlar. Bu ayar, Windows resimli parolalarının kullanımına izin verir veya bunu engeller.
- **Şifreleme**: hedeflenen cihazlarda şifrelemeyi etkinleştirin.

## <a name="personalization"></a>Kişiselleştirme

- **Masaüstü arka plan resmi URL'si (yalnızca Masaüstü)**: Windows masaüstü duvar kağıdı olarak kullanmak istediğiniz JPEG biçiminde bir resmin URL'sini girin. Kullanıcılar bu resmi değiştiremez.

## <a name="privacy"></a>Gizlilik

- **Girişi kişiselleştirme**: Cortana, dikte veya Microsoft Store uygulamaları için bulut tabanlı konuşma hizmetlerinin kullanımına izin verme. Bu hizmetlere izin verirseniz Microsoft, hizmeti geliştirmek için sesli veri toplayabilir.
- **Eşleştirme ve gizlilik Kullanıcı onayı istemlerini otomatik kabul**: uygulama çalıştırırken eşleştirme ve gizlilik otomatik olarak kabul etme Windows izin ver onay iletilerini.
- **Kullanıcı etkinliklerini Yayımla**: **blok** paylaşılan deneyimleri ve görev değiştiricide yakın zamanda kullanılan kaynakların bulunmasını önler.
- **Yalnızca yerel etkinlikler**: **blok** paylaşılan deneyimleri ve görev değiştiricide yalnızca yerel etkinliği temel alan, yakın zamanda kullanılan kaynakların bulunmasını önler.

Cihazdaki tüm uygulamaların erişebileceği bilgileri yapılandırabilirsiniz. **Uygulama başına gizlilik özel durumları**'nı kullanarak uygulama başına özel durumlar tanımlayabilirsiniz.

### <a name="exceptions"></a>Özel durumlar

- **Hesap bilgileri**: Bu uygulamanın kullanıcı adına, resmine ve diğer kişi bilgilerine erişip erişemeyeceğini tanımlayın.
- **Arka plan uygulamaları**: Bu uygulamanın arka planda çalışıp çalışamayacağını tanımlayın.
- **Takvim**: Bu uygulamanın takvime erişip erişemeyeceğini tanımlayın.
- **Arama Geçmişi**: Bu uygulamanın çağrı geçmişime erişip erişemeyeceğini tanımlayın.
- **Kamera**: Bu uygulamanın kameraya erişip erişemeyeceğini tanımlayın.
- **Kişiler**: Bu uygulamanın kişilere erişip erişemeyeceğini tanımlayın.
- **E-posta**: Bu uygulamaya erişebilir ve e-posta Gönder olup olmadığını tanımlar.
- **Konum**: Bu uygulamanın konum bilgilerine erişip erişemeyeceğini tanımlayın.
- **Mesajlaşma**: Bu uygulama okuma veya metin veya MMS iletisi gönder tanımlayın.
- **Mikrofon**: Bu uygulamanın mikrofonu kullanıp kullanamayacağını tanımlayın.
- **Hareket**: Bu uygulamanın cihaz hareket bilgilerine erişip erişemeyeceğini tanımlayın.
- **Bildirimleri**: Bu uygulamanın bildirimlere erişip erişemeyeceğini tanımlayın.
- **Telefon**: Bu uygulamanın telefona erişip erişemeyeceğini tanımlayın.
- **Radyolara**: gönderme ve veri almak ve bu Radyoları açıp kapatması gerekir için Cihazınızı bazı uygulamalar Radyoları (örneğin, Bluetooth) kullanın. Bu uygulamanın bu radyoları denetleyip denetleyemeyeceğini tanımlayın.
- **Görevleri**: Bu uygulamanın görevlerinize erişip erişemeyeceğini tanımlayın.
- **Güvenilen cihazlar**: donanım zaten bağlanmış veya cihazı ile birlikte gelen donanım olduğu bu uygulamanın güvenilen cihazları kullanıp kullanamayacağını seçin. Örneğin, televizyonlar, Projektörler, vb. güvenilen cihazlar kullanır.
- **Geri bildirim ve tanılama**: Bu uygulamanın tanılama bilgilerine erişip varsa seçin.
- **Cihazlarla eşitle** - Bu uygulamanın bu PC, tablet veya telefonla açıkça eşleştirilmemiş kablosuz cihazlarla otomatik olarak bilgi paylaşma ve eşitleme işlemleri yapıp yapamayacağını tanımlayın.

## <a name="per-app-privacy-exceptions"></a>Uygulama başına gizlilik özel durumları

"Varsayılan gizlilik" altında tanımladığınızdan farklı bir gizlilik davranışı olması gereken uygulamaları ekleyebilirsiniz.

- **Paket adı**: uygulama paketi ailesi adı.
- **Uygulama adı**: uygulama adı.

### <a name="exceptions"></a>Özel durumlar

- **Hesap bilgileri**: Bu uygulamanın kullanıcı adına, resmine ve diğer kişi bilgilerine erişip erişemeyeceğini tanımlayın.
- **Arka plan uygulamaları**: Bu uygulamanın arka planda çalışıp çalışamayacağını tanımlayın.
- **Takvim**: Bu uygulamanın takvime erişip erişemeyeceğini tanımlayın.
- **Arama Geçmişi**: Bu uygulamanın çağrı geçmişime erişip erişemeyeceğini tanımlayın.
- **Kamera**: Bu uygulamanın kameraya erişip erişemeyeceğini tanımlayın.
- **Kişiler**: Bu uygulamanın kişilere erişip erişemeyeceğini tanımlayın.
- **E-posta**: Bu uygulamaya erişebilir ve e-posta Gönder olup olmadığını tanımlar.
- **Konum**: Bu uygulamanın konum bilgilerine erişip erişemeyeceğini tanımlayın.
- **Mesajlaşma**: Bu uygulama okuma veya metin veya MMS iletisi gönder tanımlayın.
- **Mikrofon**: Bu uygulamanın mikrofonu kullanıp kullanamayacağını tanımlayın.
- **Hareket**: Bu uygulamanın cihaz hareket bilgilerine erişip erişemeyeceğini tanımlayın.
- **Bildirimleri**: Bu uygulamanın bildirimlere erişip erişemeyeceğini tanımlayın.
- **Telefon**: Bu uygulamanın telefona erişip erişemeyeceğini tanımlayın.
- **Radyolara**: gönderme ve veri almak ve bu Radyoları açıp kapatması gerekir için Cihazınızı bazı uygulamalar Radyoları (örneğin, Bluetooth) kullanın. Bu uygulamanın bu radyoları denetleyip denetleyemeyeceğini tanımlayın.
- **Görevleri**: Bu uygulamanın görevlerinize erişip erişemeyeceğini tanımlayın.
- **Güvenilen cihazlar**: donanım zaten bağlanmış veya cihaz ile birlikte gelen donanım olduğu bu uygulamanın güvenilen cihazları kullanıp kullanamayacağını seçin. Örneğin, televizyonlar, Projektörler, vb. güvenilen cihazlar kullanır.
- **Geri bildirim ve tanılama**: Bu uygulamanın tanılama bilgilerine erişip erişemeyeceğini tanımlayın.
- **Cihazlarla Eşitle**: Bu uygulama otomatik olarak paylaşabilir ve cihazı ile doğrudan eşleştirilmeyen Kablosuz cihazlarla eşitleme bilgileri, seçin.

## <a name="locked-screen-experience"></a>Kilit ekranı deneyimi

- **İşlem Merkezi bildirimleri (yalnızca mobil)**: sağlar İşlem Merkezi bildiriminin görünmesine cihaz kilitleme ekranında (yalnızca Windows 10 Mobile).
- **Ekranı resmi URL'si (yalnızca Masaüstü)**: Windows kilit ekranı duvar kağıdı olarak kullanılan JPEG biçiminde bir resmin URL'sini girin. Kullanıcılar, bu ayarı değiştiremezsiniz.
- **Kullanıcı tarafından yapılandırılabilir ekran zaman aşımı (yalnızca mobil)**: kullanıcıların süreyi yapılandırmasına olanak tanır 
- **(Yalnızca Masaüstü) kilitli ekranda Cortana**: kullanıcı, cihaz kilit ekranında (yalnızca Windows 10 Masaüstü) olduğunda Cortana ile etkileşim kurmasına izin verme.
- **Kilitli ekranda bildirimler**: gelen gösteren cihaz kilitleme ekranında uyarı iletileri engelleyin.
- **Ekran zaman aşımı (yalnızca mobil)**: kapatmak olduğunda ekranın kapanarak saniye cinsinden süreyi belirtir.

## <a name="app-store"></a>Uygulama Mağazası

- **Uygulama Mağazası (yalnızca mobil)**: etkinleştirin veya Windows 10 Mobile cihazlarda uygulama mağazasına kullanımını engelleyin.
- **Mağaza uygulamalarını otomatik güncelleştir**: otomatik olarak güncelleştirilmesi için Microsoft Store yüklenen uygulamaların verir.
- **Güvenilir Uygulama yüklemesi**: dışarıdan yüklenmesine izin güvenilen bir sertifikayla imzalanan uygulamaların sağlar.
- **Geliştirici kilidini açma**: dışarıdan yüklenen uygulamaların son kullanıcı tarafından değiştirilmesine izin verme gibi Windows izin Geliştirici ayarları.
- **Paylaşılan kullanıcı uygulaması verileri**: uygulamaların aynı cihazdaki farklı kullanıcılar arasında veri paylaşmasına izin verir.
- **Yalnızca özel mağaza kullan**: yalnızca özel mağazanızdan uygulama indirmek son kullanıcılara izin vermek için etkinleştirin.
- **Mağazadan indirilen uygulamaları başlatma Store**: cihazda önceden yüklenmiş veya Microsoft Store yüklenen tüm uygulamaları devre dışı bırakmak için kullanılır.
- **Uygulama verilerini sistem birimine Yükle**: uygulamaların depolamasını cihazın sistem birimine veri engeller.
- **Uygulamaları sistem sürücüsüne Yükle**: uygulamaların depolamasını cihazın sistem sürücüsüne veri engeller.
- **Oyun DVR (yalnızca Masaüstü)**: kaydetme ve oyun yayın izin verilip verilmediğini yapılandırır.
- **Uygulamaları yalnızca mağazadan**: Kullanıcıların uygulama mağazası dışındaki yerlerden uygulama yükleyip yükleyemeyeceğini yapılandırır.

## <a name="microsoft-edge-browser"></a>Microsoft Edge Tarayıcısı

### <a name="start-experience"></a>Başlangıç deneyimi

- **Microsoft Edge ile Başlat**: Microsoft Edge başladığında, hangi sayfaların Aç'ı seçin. Seçenekleriniz şunlardır:
  - **Başlangıç sayfaları**: Microsoft Edge başlangıç varsayılan başlangıç sayfası işletim sistemi tarafından tanımlanmış
  - **Yeni bir sekme sayfası**: Microsoft Edge yük ne olursa olsun tanımlanan **yeni bir sekme sayfası URL'si** ayarı
  - **Son oturumun sayfa**: Microsoft Edge son oturumu sayfasında yükler 
  - **Özel başlangıç sayfası**: Microsoft Edge yükler BT yöneticisi tarafından tanımlanan başlangıç sayfası
- **Kullanıcı, başlangıç sayfalarını değiştirebilirsiniz**: **izin** başlangıç sayfalarını değiştirmesine olanak sağlar. Yöneticiler `EdgeHomepageUrls` varsayılan olarak kullanıcıların gördüğü başlangıç sayfalarını girmek için Microsoft Edge açın. **Yapılandırılmamış** kullanıcıların başlangıç sayfalarını değiştirmesini engeller.
- **Yeni sekme sayfası URL'si**: yeni bir sekme sayfasını açmak için URL'yi girin. Örneğin, şunu girin: `https://www.bing.com`.
- **Açık web içeriği yeni bir sekme sayfasında**: seçin **blok** Microsoft Edge Web sitesinde yeni bir sekme açmasını durdurmak için. Engellendiğinde, yeni bir sekme boş açın. **Yapılandırılmamış** gösterilene seçmek kullanıcılar izin verebilir cihaz işletim sistemi varsayılan davranışı kullanır.
- **Giriş düğmesi**: Giriş düğmesi seçili olduğunda ne olacağını seçin. Seçenekleriniz şunlardır:
  - **Başlangıç sayfaları**: seçtiğiniz için seçeneği **Başlat Microsoft Edge ile** açılır ayarlama
  - **Yeni bir sekme sayfası**: seçtiğiniz için seçeneği **yeni bir sekme sayfası URL'si** açılır ayarlama
  - **Özel giriş düğmesi URL'si**: seçtiğiniz için seçeneği **giriş düğmesi URL'si** açılır ayarlama
  - **Gizleme giriş düğmesine**: Giriş düğmesi gizler
- **Kullanıcı Giriş düğmesine değiştirebilirsiniz**: **izin** kullanıcıların giriş düğmesi değiştirmesine olanak tanır. Kullanıcının yaptığı değişiklikleri giriş düğmesi için herhangi bir yönetici ayarları geçersiz kılar. **Yapılandırılmamış** nasıl giriş düğmesi yönetici tarafından yapılandırılan değiştirmesini kullanıcıları engelleyebilir cihaz işletim sistemi varsayılan davranışı kullanır.
- **İlk çalıştırma deneyimi sayfasını göster**: **blok** durdurur ilk gösteren giriş sayfasından, Microsoft Edge çalıştırma süresi. Bu özellik, kuruluşların sıfır emisyon yapılandırmalarına bu sayfayı engellemesine izin, kayıtlı sağlar. **Yapılandırılmamış** giriş sayfasında gösterilir.
  - **İlk çalıştırma deneyimi URL**: kullanıcı ilk kez çalışan Microsoft Edge (yalnızca Windows 10 Mobile) göstermek için sayfanın URL'sini girin.
- **Açılır pencereler**: seçin **blok** tarayıcıdaki açılır pencereleri durdurmak için. Yalnızca Windows 10 masaüstü için geçerlidir. **Yapılandırılmamış** web tarayıcısında açılır pencerelere izin verir.
- **Internet Explorer'a intranet trafiği Gönder**: **izin** kullanıcıların (yalnızca Windows 10 Masaüstü) Microsoft Edge yerine Internet Explorer'da intranet Web siteleri açmasına olanak sağlar. **Yapılandırılmamış** Microsoft Edge kullanmasına olanak tanır.
- **Kurumsal mod site listesi konumu**: Kurumsal modda açılan web siteleri listesini içeren bir URL girin. Kullanıcılar bu listeyi değiştiremez. Yalnızca Windows 10 masaüstü için geçerlidir.
- **Açılırken ileti siteleri Internet Explorer'da**: Internet Explorer 11'de bir site açılmadan önce bir bildirim göstermek için Microsoft Edge yapılandırmak için bu ayarı kullanın. Seçenekleriniz şunlardır:
  - **Yapılandırılmamış**: işletim sistemi varsayılan davranışı kullanılır, bir ileti gösterilmeyebilir.
  - **Microsoft Edge'de siteleri açmak için seçeneği olmadan iletiyi göster**: IE'de siteleri açarken iletiyi göster. Siteleri IE'de açın. Microsoft Edge'de siteleri açarken bir seçenek değildir.
  - **İleti açarken Microsoft Edge'de siteleri göster**: IE'de siteleri açarken iletiyi göster. İletiyi içeren bir **Microsoft Edge'de kullanmaya devam** kullanıcılar Microsoft Edge yerine IE seçebilmeniz bağlantı.

  > [!IMPORTANT]
  > Bu ayarı etkinleştirmenizi gerektirir **kuruluş modu Site listesini yapılandır** ayarını **tüm intranet sitelerinin Internet Explorer 11'e gönderin** ayarı veya her iki ayar.

- **Microsoft uyumluluk listesini**: **blok** Microsoft edge'de Microsoft uyumluluk listesini engeller. Microsoft'un bu listesi, bilinen uyumluluk sorunlarına sahip siteleri düzgün görüntülenmesi Edge yardımcı olur. **Yapılandırılmamış** kullanarak Microsoft uyumluluk listesini sağlar.
- **Başlangıç sayfalarını ve sayfa yeni sekmede dağıtılacak**: seçin **blok** önceden gelen Microsoft Edge önlemek için sayfalar ve yeni bir sekme sayfası başlatın. Önceden yükleme Microsoft Edge başlatın ve yeni bir sekme yükleme süresini en aza indirir. **Yapılandırılmamış** dağıtılacak bu sayfaları için işletim sistemi varsayılan davranışı kullanır.
- **Önceden başlatma başlangıç sayfalarını ve sayfa yeni sekmede**: seçin **blok** Microsoft Edge başlangıç sayfalarını ve yeni bir sayfa önceden başlamasını engellemek için. Önceden başlatma, Microsoft Edge performansını yardımcı olur ve Microsoft Edge başlatmak için gereken süreyi en aza indirir. **Yapılandırılmamış** bu sayfaları için önceden başlatma işletim sistemi varsayılan davranışı kullanır.

### <a name="favorites-and-search"></a>Sık Kullanılanlar ve arama

- **Sık Kullanılanlar çubuğu**: Sık Kullanılanlar çubuğuna herhangi bir Microsoft Edge sayfasında ne olacağını seçin. Seçenekleriniz şunlardır:
  - **Yapılandırılmamış**: Sık Kullanılanlar çubuğu tüm sayfalardaki gizlemek için işletim sistemi varsayılan davranışı kullanır. Kullanıcının bu ayarı değiştirebilirsiniz.
  - **Gizleme**: Sık Kullanılanlar çubuğu tüm sayfalardaki gizler. Kullanıcının bu ayarı değiştiremezsiniz.
  - **Göster**: Sık Kullanılanlar çubuğu tüm sayfalarında gösterilir. Kullanıcının bu ayarı değiştiremezsiniz.
- **Sık Kullanılanlar listesine**: URL'lerin bir listesini Sık Kullanılanlar dosyasına ekleyin. Örneğin, ekleme `http://contoso.com/favorites.html`.
- **Sık Kullanılanlarda değişiklikler kısıtlama**: **blok** ekleme, alma, sıralama veya Sık Kullanılanlar listesine düzenleme kullanıcıların önlemek için. **Yapılandırılmamış** listesini değiştirmek kullanıcıların izin işletim sistemi varsayılan kullanır.
- **(Yalnızca Masaüstü) Microsoft tarayıcıları arasında sık kullanılanları Eşitle**: **gerektiren** Windows Internet Explorer ve Microsoft Edge arasında sık kullanılanları eşitlemeye zorlar. Ekleme, silme, değişiklikler ve siparişi değişikliklerinin Sık Kullanılanlar tarayıcılar arasında paylaşılır.  **Yapılandırılmamış** kullanıcıların seçim tarayıcıları arasında sık kullanılanları Eşitle verebilir işletim sistemi varsayılan kullanır.
- **Varsayılan arama motorunu**: cihazdaki varsayılan arama motorunu seçin. Son kullanıcılar bu değeri istediği zaman değiştirebilir. Seçenekleriniz şunlardır:
  - Varsayılan
  - Bing
  - Google
  - Yahoo
  - Özel değer
- **Arama önerileri**: **yapılandırılmadı** adres çubuğunda arama tümcecikleri yazarken arama motorunuzun site olanak tanır. **Blok** bu özellik engeller.

### <a name="privacy-and-security"></a>Gizlilik ve güvenlik

- **InPrivate Gözatma**: **blok** son kullanıcıların InPrivate Gözatma oturumları açmasını engeller. **Yapılandırılmamış** bu özelliği sağlar.
- **Tarama geçmişi Kaydet**: **blok** Microsoft Edge gözatma geçmişini kaydetmesini engeller. **Yapılandırılmamış** gözatma geçmişini kaydetmeye olanak tanır.
- **Clear veri (yalnızca Masaüstü) Çıkışta gözatma**: **gerektiren** geçmişi ve kullanıcının Microsoft Edge çıkarken tarama verilerini temizler. **Yapılandırılmamış** tarama verilerini önbelleğe alabilir işletim sistemi varsayılan kullanır.
- **Tarayıcı ayarlarını kullanıcının cihazlar arasında eşitleme**: tarayıcı ayarlarını cihazlar arasında eşitleme istediğiniz şekli seçin. Seçenekleriniz şunlardır:
  - **İzin**: Microsoft Edge tarayıcı ayarları kullanıcının cihazlar arasında eşitlenmesine izin ver
  - **Blok ve kullanıcı geçersiz kılma etkinleştir**: Microsoft Edge tarayıcı ayarları kullanıcının cihazlar arasında eşitlemeyi engelleyin. Kullanıcılar bu ayarı geçersiz kılabilirsiniz.
  - **Blok**: Microsoft Edge tarayıcı ayarının kullanıcının cihazlar arasında eşitlemeyi engelleyin. Kullanıcılar, bu ayarı geçersiz kılamaz.
- **Parola Yöneticisi**: **blok** Microsoft Edge parola Yöneticisi özelliğini devre dışı bırakır. **Yapılandırılmamış** bu özelliği sağlar.
- **Tanımlama bilgilerini**: web tarayıcısında tanımlama bilgilerine nasıl işleneceğini seçin. Seçenekleriniz şunlardır:
  - **İzin**: tanımlama bilgilerinin cihazda depolanır.
  - **Tüm tanımlama bilgilerini engelle**: tanımlama bilgilerinin cihazda depolanan değildir.
  - **Yalnızca üçüncü taraf tanımlama bilgilerini engelle**: üçüncü taraf veya iş ortağı tanımlama bilgilerinin cihazda depolanan değildir.
- **Otomatik doldurma**: **blok** otomatik doldurma özelliğinin cihazda devre dışı bırakır. **Yapılandırılmamış** kullanıcıların (yalnızca Windows 10 Masaüstü) tarayıcıdaki otomatik tamamlama ayarlarını değiştirmesine olanak tanır.
- **Kullanıcıyı-izleme üst bilgileri gönderme**: **yapılandırılmadı** cihazlar (önerilen) izleme bilgisi isteyen Web sitelerine not track üst bilgileri göndermesini gerektirir. Seçin **blok** cihaz kullanıcıyı izlemek Web siteleri sağlayan bu üst bilgileri göndermesini önlemek için.
- **WebRtc localhost IP adresi**: **blok** web RTC protokolü kullanılarak telefon aramaları gerçekleştirilirken gösteriliyor kullanıcıların localhost IP adresinin engeller. **Yapılandırılmamış** kullanıcıların localhost IP adresi bu protokolü kullanılarak telefon aramaları gerçekleştirilirken gösterilmesini sağlar.
- **Canlı kutucuk veri toplama**: seçin **blok** Windows Canlı bir site sabitlenmiş Kutucuklardan birini bilgi toplamayı Başlat menüsünden Microsoft Edge için gelen durdurmak için. **Yapılandırılmamış** bu bilgilerin toplanmasını sağlar.
- **Kullanıcı sertifika hataları geçersiz kılma**: **blok** kullanıcıların SSL veya TLS hata içeren Web sitelerine erişmesini engeller. **Yapılandırılmamış** bu sitelere erişmesine olanak tanır.

### <a name="additional"></a>Ek

- **Microsoft Edge tarayıcısı (yalnızca mobil)**: seçin **blok** cihazda Microsoft Edge kullanarak önlemek için. Microsoft Edge'i engellerseniz, ayrı ayrı ayarlar yalnızca Masaüstü için geçerlidir. **Yapılandırılmamış** cihazda Microsoft Edge web tarayıcısının kullanımına izin verir.
- **Adres çubuğu açılır listesi (yalnızca Masaüstü)**: **blok** Microsoft Edge yazarken öneriler listesi aşağı açılan listesinde göstermesini durdurur. Bu seçenek, Microsoft Edge ile Microsoft Hizmetleri arasında ağ bant genişliğini en aza yardımcı olur. **Yapılandırılmamış** öneriler listesini göstermek Microsoft Edge sağlar.
- **Tam ekran**: seçin **blok** yalnızca web içeriğini gösterme ve gizleme Microsoft Edge (tam ekran modu), Microsoft Edge önlemek için. **Yapılandırılmamış** tam ekran modunu kullanmak Microsoft Edge izin veren varsayılan işletim sistemi kullanır.
- **About: Flags sayfasına**: **blok** son kullanıcıların erişmesini engelleyen `about:flags` Geliştirici ayarları ve Deneysel ayarlar içeren Microsoft edge'de sayfası. **Yapılandırılmamış** erişilebilmesini sağlar işletim sistemi varsayılan `about:flags` sayfası.
- **Geliştirici Araçları**: **blok** son kullanıcılar Microsoft Edge geliştirici araçlarını açmasını engeller. **Yapılandırılmamış** geliştirici araçları açmasına izin verir.
- **Uzantıları**: **yapılandırılmadı** son kullanıcıların cihazda Microsoft Edge uzantıları yüklemek olanak tanır. **Blok** yüklemeyi engeller.
- **Dışarıdan yükleme geliştirici uzantıları**: **blok** Microsoft Edge yükler ve doğrulanmamış uzantılarını kullanarak çalışan dışarıdan yükleme engelleyen **yük uzantıları** özelliği. **Yapılandırılmamış** dışarıdan yükleme olarak izin verebileceği işletim sistemi varsayılan kullanır.
- **Gerekli uzantıları**: Microsoft edge'de son kullanıcılar tarafından hangi uzantıları kapatılamaz seçin. Paket aile adları'nı girin ve seçin **Ekle**. [Bir paket aile adı (PFN) bulma](https://docs.microsoft.com/sccm/protect/deploy-use/find-a-pfn-for-per-app-vpn) listeler rehberlik sağlar.

  Ayrıca **alma** paket aile adları içeren bir CSV dosyası.

- **JavaScript**: seçin **blok** tarayıcıda Java betiğinin cihazda çalışmasını engelleyin. **Yapılandırılmamış** Microsoft Edge tarayıcısında çalıştırmak için Javascript gibi betiklerin verir.

## <a name="windows-defender-smart-screen"></a>Windows Defender Smart Screen

- **Microsoft Edge için SmartScreen**: site ve dosya yüklemeleri erişmek için Microsoft Edge Smartscreen'i etkinleştirin.
- **Kötü niyetli site erişimi**: kullanıcıların Windows Defender SmartScreen Filtresi uyarılarını yoksaymasını ve siteye gitmesini engelleyin.
- **Doğrulanmamış dosyayı indirme**: kullanıcıların Windows Defender SmartScreen Filtresi uyarılarını yoksaymasını ve doğrulanmamış dosyaları indirmesini engelleyin.

## <a name="search"></a>Ara

- **Güvenli arama (yalnızca mobil)**: Cortana arama sonuçlarında yetişkinlere yönelik içeriği nasıl filtreleyeceğini denetleyin. **Katı**, **Orta** değerlerini seçebilir ya da son kullanıcının kendi ayarlarını seçmesine izin verebilirsiniz.
- **Aramada web sonuçlarını görüntüle**: blok veya web sonuçları, cihazda yapılan aramalarda görünmesini izin verin.

## <a name="cloud-and-storage"></a>Bulut ve Depolama

- **Microsoft hesabı**: kullanıcının bir Microsoft hesabını cihazla ilişkilendirmesine olanak sağlar.
- **Microsoft olmayan hesaplar**: aygıta e-posta hesapları ekleyin ve bir Microsoft hesabı ile ilişkili olmayan kullanıcıların olanak tanır.
- **Microsoft hesabı için ayar eşitlemesi**: cihazlar arasında eşitlenmesine izin, bir Microsoft hesabıyla ilişkilendirilmiş cihaz ve uygulama ayarlarının verin.

## <a name="cellular-and-connectivity"></a>Hücresel ve Bağlantı

- **Hücresel veri kanalı**: kullanıcıların şebekesine bağlı olduğunuzda Web'e gözatma gibi veri kullanmasını durdurun. 
- **Veri dolaşımı**: verilere erişirken ağlar arasında dolaşıma izin verin.
- **Hücresel ağ üzerinden VPN**: cihaz şebekesine bağlandığında VPN bağlantılarına erişip erişemeyeceğini denetler.
- **Hücresel ağ üzerinden VPN dolaşımı**: cihazın bir cep telefonu şebekesinde dolaşımı sırasında VPN bağlantılarına erişip erişemeyeceğini denetler.
- **Bluetooth**: kullanıcı etkinleştirebilir ve cihazda Bluetooth yapılandırmasına olup olmadığını denetler.
- **Bluetooth bulunabilirlik**: cihazın diğer Bluetooth özellikli cihazlar tarafından bulunabilmesine olanak sağlar.
- **Bluetooth önceden eşleştirme**: belirli Bluetooth cihazlarını bir konak cihazla otomatik olarak kullanmak üzere yapılandırmanıza olanak sağlar.
- **Bluetooth reklamlarına**: cihazın Bluetooth üzerinden reklam almasına izin verir.
- **Bağlı cihazlar hizmetine**: bulma ve Bluetooth diğer cihazlara bağlanmayı etkinleştiren bağlı cihazlar hizmetine izin verilip verilmeyeceğini seçtiğiniz sağlar.
- **NFC**: kullanıcının cihazda yakın alan iletişimi özelliklerini yapılandırmak ve etkinleştirmek olanak tanır.
- **Wi-Fi**: kullanıcının etkinleştirmek ve (yalnızca Windows 10 Mobile) cihazda Wi-Fi yapılandırmasına izin verir.
- **Wi-Fi etkin noktalarına otomatik bağlanma**: cihazın ücretsiz Wi-Fi etkin noktalarına ve hiçbir hüküm ve koşullar bağlantı için otomatik olarak kabul otomatik olarak bağlan olanak tanır.
- **Elle Wi-Fi yapılandırmasına**: olup, kullanıcının kendi Wi-Fi bağlantılarını yapılandırıp yapılandıramayacağını veya olup yalnızca Wi-Fi profili (yalnızca Windows 10 Mobile) tarafından yapılandırılan bağlantıları kullanıp kullanamayacağını.
- **Wi-Fi tarama aralığı**: sıklığını belirtin cihazlar için Wi-Fi ağlarını tarama. 1 (en çok) ile 500 (en az) arasında bir değer belirtin.
- **Bluetooth'a izin verilen hizmetler**: onaltılık dizeler olarak izin verilen Bluetooth hizmetleri ve profillerinin bir listesini belirtin.

## <a name="control-panel-and-settings"></a>Denetim Masası ve Ayarlar

- **Ayarlar uygulamasında**: Windows ayarlar uygulamasına erişimi engelleyin.
  - **Sistem**: ayarlar uygulamasının sistem alanına erişimini engeller.
    - **Güç ve uyku ayarlarının değiştirilmesi (yalnızca Masaüstü)**: son kullanıcının cihazın güç ve uyku ayarlarını değiştirmesini engeller.
  - **Cihazları**: ayarlar uygulamasının cihazlar alanına erişimini engeller.
  - **Ağ ve Internet**: ayarlar uygulamasının ağ ve internet alanına erişimini engeller.
  - **Kişiselleştirme**: ayarlar uygulamasının kişiselleştirme alanına erişimini engeller.
  - **Hesapları**: ayarlar uygulamasında hesaplar alanına erişimini engeller.
  - **Saat ve dil**: ayarlar uygulamasının saat ve dil alanına erişimini engeller.
    - **Sistem saatinin değiştirilmesi**: son kullanıcının cihazın tarih ve saatini değiştirmelerini engeller.
    - **Bölge ayarlarının değiştirilmesi (yalnızca Masaüstü)**: son kullanıcının cihazın bölge ayarlarını değiştirmesini engeller.
    - **Dil ayarlarının değiştirilmesi (yalnızca Masaüstü)**: kullanıcının cihazın dil ayarlarını değiştirmesini engeller.
  - **Oyun**: ayarlar kısmında oyun uygulamasına erişimini engeller.
  - **Erişim Kolaylığı**: Erişim Kolaylığı alanına ayarlar uygulamasının erişimini engeller.
  - **Gizlilik**: ayarlar uygulamasının gizlilik alanına erişimini engeller.
  - **Güncelleştirme ve güvenlik**: güncelleştirmeleri ve ayarlar uygulamasında güvenlik alanına erişimini engeller.

## <a name="start"></a>Başlangıç

- **Başlangıç menüsü düzeni**: Masaüstü cihazlarda Başlat menüsünü özelleştirmek için uygulamaları listelenen sırayla dahil olmak üzere özelleştirmelerinizi ve daha fazlasını içeren bir XML dosyasını karşıya yükleyebilirsiniz. Kullanıcılar, girdiğiniz Başlat menüsü düzenini değiştiremez.
- **Başlat menüsünde Web siteleri için kutucuklar sabitleme**: Masaüstü cihazları için Windows Başlat menüsündeki bağlantılar olarak gösterilen Microsoft Edge görüntüleri alma.
- **Uygulamaları görev çubuğundan Kaldır**: seçin **blok** kullanıcı uygulamaları Başlat menüsünden kaldırmasını durdurmak için.
- **Hızlı Kullanıcı Geçişi**: seçin **blok** aynı anda kapatmadan oturum açmış kullanıcılar arasında geçiş yapma önlemek için.
- **En çok kullanılan uygulamalar**: seçin **blok** gösteren Başlat menüsünde en çok kullanılan uygulamalardan gizlemek için. Bu ayrıca Ayarlar uygulamasında aynı ada sahip iki durumlu ayarı da devre dışı bırakır.
- **Uygulamalar'en son eklenen**: seçin **blok** gösteren Başlangıç menüsündeki son eklenen uygulamaları Gizle için. Bu ayrıca Ayarlar uygulamasında aynı ada sahip iki durumlu ayarı da devre dışı bırakır.
- **Başlangıç ekranı modu**: başlangıç ekranının nasıl gösterilen seçin. Bunu **Tam ekran** veya **Tam ekran değil** şeklinde belirleyebilirsiniz.
- **Son açılan öğeler bağlantı listeleri**: seçin **blok** son atlama listelerini görev çubuğu ve Başlat menüsü üzerinde gösterilen gizlemek için. Bu ayrıca Ayarlar uygulamasında aynı ada sahip iki durumlu ayarı da devre dışı bırakır.
- **Uygulama listesi**: ayarlar uygulamasında gösterilen nasıl seçin. Seçenekleriniz şunlardır: 
  - Daralt
  - Ayarlar uygulamasını daralt ve devre dışı bırak 
  - Ayarlar uygulamasını kaldırır ve devre dışı bırakır
- **Güç düğmesi**: seçin **blok** gösteren Başlangıç menüsündeki güç düğmesinden gizlemek için.
- **Kullanıcı kutucuğunu**: seçin **blok** gelen gösteren Başlangıç menüsündeki kullanıcı kutucuğunda gizlemek için.
  - **Kilit**: seçin **blok** gizlemek için `Lock` gösteren Başlangıç menüsündeki kullanıcı kutucuğunda seçeneği.
  - **Oturumu Kapat**: seçin **blok** gizlemek için `Sign out` gösteren Başlangıç menüsündeki kullanıcı kutucuğunda seçeneği.
- **Kapat**: seçin **blok** gizlemek için `Update and shut down` ve `Shut down` seçenekleri gösteren Başlangıç menüsündeki güç düğmesinde.
- **Uyku**: seçin **blok** gizlemek için `Sleep` gösteren Başlangıç menüsündeki güç düğmesinde seçeneği.
- **Hazırda bekleme**: seçin **blok** gizlemek için `Hibernate` gösteren Başlangıç menüsündeki güç düğmesinde seçeneği.
- **Hesap Değiştir**: seçin **blok** gizlemek için `Switch account` kullanıcı gösteren gelen döşeme Başlat menüsünde.
- **Yeniden başlatma seçenekleri**: seçin **blok** gizlemek için `Update and restart` ve `Restart` seçenekleri gösteren Başlangıç menüsündeki güç düğmesinde.
- **Başlangıç menüsünde belgeler**: Windows Başlat menüsündeki Belgeler klasörünü gösterin veya gizleyin.
- **Başlangıç menüsünde indirmeler**: Windows Başlat menüsündeki indirilenler klasörünü gösterin veya gizleyin.
- **Başlat menüsünde dosya Gezgini**: Windows Başlat menüsündeki dosya Gezgini uygulamasını gösterin veya gizleyin.
- **Başlangıç menüsünde ev grubu**: Windows Başlat menüsündeki ev grubu klasörünü gösterin veya gizleyin.
- **Başlangıç menüsünde müzik**: Windows Başlat menüsündeki müzik klasörünü gösterin veya gizleyin.
- **Başlangıç menüsünde ağ**: Windows Başlat menüsündeki ağ klasörünü gösterin veya gizleyin.
- **Başlangıç menüsünde Kişisel klasörü**: Windows Başlat menüsündeki kişisel klasörünü gösterin veya gizleyin.
- **Başlangıç menüsünde resimler**: Windows Başlat menüsünde Resimler klasörünü gösterin veya gizleyin.
- **Başlangıç menüsünde Ayarlar**: Windows Başlat menüsündeki ayarlar uygulamasını gösterin veya gizleyin.
- **Başlangıç menüsünde videolar**: Windows Başlat menüsündeki videolar klasörünü gösterin veya gizleyin.

## <a name="display"></a>Görüntüle

- **Uygulamalar için GDI ölçeklendirmeyi aç**
- **Uygulamalar için GDI ölçeklendirmeyi kapat**

  GDI DPI ölçeklendirme, İzleyici başına DPI DPI olmayan uygulamalar sağlar. GDI DPI ölçeklendirme olan eski uygulamaları girin. GDI DPI açmak ve bir uygulama üzerinde devre dışı bırakmak için yapılandırılmış ölçeklemeyle, ölçeklendirme uygulama için devre dışıdır.

## <a name="kiosk-preview---obsolete"></a>Bilgi noktası (Önizleme) - Eski

Bu ayarlar salt okunurdur ve değiştirilemez. Bilgi noktası modunu yapılandırmak için bkz. [Windows 10 ve üzerinde bilgi noktası ayarları](kiosk-settings.md).

Bir bilgi noktası cihazı genellikle tek bir uygulama veya belirli bir uygulamalar kümesi çalıştırır. Kullanıcılar, başka özellik veya işlevlere cihaza erişimi engellenmiştir.

- **Bilgi noktası modu**: ilke tarafından desteklenen bilgi noktası modu türünü belirler. Şu seçenekler mevcuttur:

  - **Yapılandırılmamış** (varsayılan): cihazda bilgi noktası modu ilke sağlamaz.
  - **Tek uygulama bilgi noktası**: Profil, cihazın yalnızca bir uygulama çalıştırmasına olanak tanır. Kullanıcı oturum açtığında belirli bir uygulama başlar. Bu mod ayrıca kullanıcının yeni uygulamalar açmasını veya çalışan uygulamayı değiştirmesini önler.
  - **Çoklu uygulama bilgi noktası**: Profil cihazı birçok uygulamaları çalıştırmak etkinleştirir. Yalnızca eklediğiniz uygulamalar kullanıcı tarafından kullanılabilir. Bir çoklu uygulama bilgi noktasının veya sabit amaçlı cihazın yararı, yalnızca ihtiyaç duyulan uygulamalara erişim sağlayıp gerek olmayan uygulamaları göz önünden kaldırarak bireylere anlaşılması kolay bir deneyim sunmasıdır.

#### <a name="single-app-kiosks"></a>Tek uygulama bilgi noktaları

Aşağıdaki ayarları girin:

- **Kullanıcı hesabı**: yerel (cihaz) kullanıcı hesabı, bir AD etki alanı hesabı ya da bilgi noktası uygulamasıyla ilişkili bir Azure AD hesabı girin.
  - Yerel hesap: `devicename\accountname`, `.\accountname` veya `accountname` olarak girin
  - Etki alanı hesabı: `domain\accountname` olarak girin
  - Azure AD hesabı: `AzureAD\emailaddress` olarak girin. Sabit bir etki alanıymış gibi “AzureAD” girdiğinizden emin olun. Daha sonra Azure AD e-posta adresiyle devam edin. Örneğin, şunu girin: `AzureAD\user@contoso.onmicrosoft.com`.

    Herkese açık ortamlarda bulunan ve otomatik oturum açma etkin bilgi noktaları için olabildiğince az ayrıcalığa sahip bir kullanıcı türü (yerel standart kullanıcı hesabı gibi) kullanılmalıdır. Bilgi noktası modu için bir Azure AD hesabı kullanıyorsanız `AzureAD\user@yourorganization.com` girdiğinizden emin olun.

- **Uygulama kullanıcı modeli kimliği (AUMID)**: bilgi noktası uygulamasının AUMID'sini girin. Daha fazla bilgi için bkz. [Yüklü bir uygulamanın Uygulama Kullanıcı Model Kimliğini bulma](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

#### <a name="multi-app-kiosks"></a>Çoklu uygulama bilgi noktaları

[Çoklu uygulama bilgi noktaları](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configure-a-kiosk-in-microsoft-intune), izin verilen uygulamaları ve diğer ayarları listeleyen bir bilgi noktası yapılandırması kullanır. 

**Ekle** düğmesini kullanarak bir bilgi noktası yapılandırması oluşturun (veya mevcut bir yapılandırmayı seçin). Daha sonra aşağıdaki ayarları girin:

- **Bilgi noktası yapılandırma adı**: yapılandırmasını tanımlamak için kullanılan kolay bir ad girin.

- **Bilgi noktası uygulamaları**: Başlat menüsünde kullanılabilir olan uygulamaları girin. Kullanıcılar yalnızca eklediğiniz uygulamaları kullanabilir.

  - **Uygulama türü**: bilgi noktası uygulamasının türünü seçin:
    - **Win32 uygulaması**: geleneksel bir masaüstü uygulaması. Yürütülebilir dosyanın cihaza göre tam yol adına ihtiyacınız vardır.
    - **UWP uygulaması**: bir evrensel Windows uygulaması. [Uygulamanın AUMID’sine](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) ihtiyacınız vardır.

  - **Tanımlayıcı**: tam yol adını (Win32 uygulamaları), yürütülebilir dosyayı girin veya [uygulamanın AUMID'ini](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (UWP uygulamaları).

- **Görev Çubuğu**: Bilgi noktasında görev çubuğunu **Etkinleştirmeyi** (göster) veya **Yapılandırılmadı** (gizli) olarak bırakmayı seçebilirsiniz.

- **Başlangıç menüsü düzeni**: Başlat menüsünde uygulamaları nasıl göründüğünü açıklayan bir XML dosyası girin. [Başlangıç düzenini özelleştirme ve dışarı aktarma](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout), rehberlik ve örnek XML sağlar.

  [Uygulamaları çalıştıran bir Windows 10 bilgi noktası oluşturma](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file) kullanarak ve XML dosyaları oluşturma hakkında daha fazla ayrıntı sağlar.

- **Atanan kullanıcılar**: eklediğiniz uygulamaları kullanabilecek bir veya daha fazla kullanıcı hesaplarını ekleyin. Hesap oturum açtığında, yalnızca yapılandırmada tanımlanmış uygulamalar kullanılabilir durumda olur. Hesap, cihaz için yerel olabilir veya bilgi noktası uygulamasıyla ilişkili Azure AD hesabı olabilir.

    Herkese açık ortamlarda bulunan ve otomatik oturum açma etkin bilgi noktaları için olabildiğince az ayrıcalığa sahip bir kullanıcı türü (yerel standart kullanıcı hesabı gibi) kullanılmalıdır. Bir Azure Active Directory (AD) hesabını bilgi noktası moduna yapılandırmak için `domain\user@tenant.com` biçimini kullanın.

## <a name="windows-defender-antivirus"></a>Windows Defender Virüsten Koruma

- **Gerçek zamanlı izleme**: kötü amaçlı yazılım, casus yazılım ve istenmeyen diğer yazılımlar için gerçek zamanlı taramaya izin verir.
- **Davranış izlemeyi**: cihazlarda bilinen şüpheli etkinlik düzenlerini Defender sağlar denetleyin.
- **Ağ İnceleme sistemi (NIS)**: NIS ağ tabanlı saldırılara karşı korunmaya yardımcı olur. Kötü amaçlı trafiği algılamaya ve engellemeye yardımcı olmak için Microsoft Endpoint Protection Center’dan bilinen açıkların imzalarını kullanır.
- **Tüm indirmeleri tara**: Defender Internet'ten indirilen tüm dosyaları tarayıp taramayacağını denetler.
- **Microsoft web tarayıcılarında yüklenen betikleri tarama**: sağlar Defender'ın Internet Explorer'da kullanılan betikleri taramasına.
- **Defender'a son kullanıcı erişimi**: Windows Defender kullanıcı arabiriminin son kullanıcılardan gizlenip gizlenmediğini denetler. Bu ayar değiştirildiğinde, kullanıcının bilgisayarının bir sonraki yeniden başlatılmasında devreye girer.
- **İmza güncelleştirme aralığı (saat)**: Defender'ın yeni imza dosyalarını zaman aralığı belirtin.
- **Dosya ve program etkinliğini İzle**: Defender cihazlarda dosya ve program etkinliğini izlemesine izin verir.
- **Karantinaya alınmış kötü amaçlı yazılım silinmeden önce gün**: el ile böylece belirttiğiniz gün sayısı daha önce etkilenmiş olan cihazları çözümlenen kötü amaçlı yazılımları İzle devam Defender olanak tanır. Gün sayısını ayarlarsanız **0**, kötü amaçlı yazılım karantina klasöründe kalır ve otomatik olarak kaldırılmaz.
- **Bir tarama sırasında CPU kullanım sınırı**: tarar CPU miktarını kullanmasına izin verilecek kullanın (gelen **1** için **100**).
- **Arşiv dosyalarını tara**: Defender Zip veya Cab dosyaları gibi arşivlenmiş dosyaları taramasına izin verir.
- **Gelen posta iletilerini tarama**: Defender, cihaza gelen e-posta iletilerini taramasına izin verir.
- **Tam tarama sırasında Çıkarılabilir sürücüleri tara**: sağlar Defender ın USB çubukları gibi çıkarılabilir sürücüleri tarama.
- **Tam tarama sırasında eşlenmiş ağ sürücülerini tarama**: eşlenen ağ sürücülerindeki dosyaları taramasına Defender olanak tanır.
  Sürücüdeki dosyalar salt okunur ise, Defender bunların içinde bulduğu kötü amaçlı yazılım kaldırılamıyor.
- **Ağ klasörlerinden açılan dosyaları tara**: (örneğin UNC yolundan erişilen dosyalar) paylaşılan ağ sürücülerindeki dosyaları taramasına Defender olanak tanır. Sürücüdeki dosyalar salt okunur ise, Defender bunların içinde bulduğu kötü amaçlı yazılım kaldırılamıyor.
- **Bulut koruması**: erişim izni verdiği veya Microsoft etkin koruma yönettiğiniz cihazlardan kötü amaçlı yazılım etkinliğiyle ilgili bilgi almasını hizmeti engeller. Bu bilgi gelecekte hizmeti geliştirmek için kullanılır.
- **Örnek göndermeden önce kullanıcılara sor**: kötü amaçlı dosyaları olup olmadığını daha fazla analiz gerektirebilecek denetimleri otomatik olarak Microsoft'a gönderilir.
- **Günlük hızlı tarama gerçekleştirilecek saat**: seçtiğiniz günlük saatte gerçekleştirilecek olan bir hızlı tarama zamanla sağlar.
- **Gerçekleştirilecek sistem taraması türü**: bir sistem taraması zamanladığınızda çalıştıran tarama düzeyini girin.
- **İstenmeyebilecek uygulamaları Algıla**: Windows istenmeyebilecek uygulamalar algılandığında koruma düzeyini seçin:
  - **Engelle**
  - **Denetim** istenmeyebilecek uygulamalar hakkında daha fazla bilgi için bkz. [Algıla ve engelle olası uygulamalar istenmeyen](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus).
- **Algılanan kötü amaçlı yazılım tehditlerine eylemleri**: her risk düzeyi için Defender'ın istediğiniz eylemleri algılar (düşük, Orta, yüksek ve ciddi) seçmek için bu seçeneği kullanın. Seçenekleriniz şunlardır:
  - **Temizle**
  - **Karantina**
  - **Kaldır**
  - **İzin ver**
  - **Kullanıcı tanımlı**
  - **Engelle**

### <a name="windows-defender-antivirus-exclusions"></a>Windows Defender Virüsten Koruma Dışlamaları

- **Dosyalar ve taramaların ve gerçek zamanlı korumanın dışında tutulacak klasörler**: bir veya daha fazla gibi dosya ve klasör ekler **C:\Path** veya **%ProgramFiles%\Path\filename.exe** dışlama listesine. Bu dosya ve klasörler gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.
- **Dosya uzantıları taramaların ve gerçek zamanlı korumanın dışında tutulacak**: gibi bir veya daha fazla dosya uzantısı ekleyin **jpg** veya **txt** dışlama listesine. Bu uzantıya sahip dosyaların hiçbiri gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.
- **Taramaların ve gerçek zamanlı korumanın dışında bırakılacak işlemler**: türünde bir veya daha fazla işlem eklemek **.exe**, **.com**, veya **.scr** dışlama listesine. Bu işlemler gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.

## <a name="network-proxy"></a>Ağ proxy’si

- **Proxy ayarlarını otomatik olarak algıla**: etkin olduğunda, cihaz bir PAC betiğinin yolunu bulmayı dener.
- **Proxy betiği kullan**: proxy sunucusunu yapılandırmak için bir PAC betiğinin yolu girmek için bu seçeneği belirleyin.
  - **Kurulum betiği adresi URL'si**: proxy sunucusunu yapılandırmak için kullanmak istediğiniz bir PAC betiğinin URL'sini girin.
- **El ile proxy sunucusu kullan**: ara sunucu bilgilerini el ile girmek için bu seçeneği belirleyin.
  - **Adresi**: adı veya proxy sunucusunun IP adresini girin.
  - **Bağlantı noktası numarası**: proxy sunucunuzun bağlantı noktası numarasını girin.
  - **Proxy özel durumları**: proxy sunucusunu kullanmaması gereken herhangi bir URL girin. Her birini ayırmak için noktalı virgül kullanın.
  - **Yerel adres için proxy sunucuyu atla**: intranetinizde yerel adresler için proxy sunucusunu kullanmak istemiyorsanız bu seçeneği etkinleştirin.

## <a name="windows-spotlight"></a>Windows Spot

- **Windows spot**: Windows 10 cihazlarda tüm Windows spot işlevselliğini engellemek için bu ayarı kullanın. Bu ayarı engellerseniz aşağıdaki ayarlar kullanılabilir değildir:
  - **Kilit ekranında Windows spot**: Windows spot cihaz kilitleme ekranında bilgi görüntülemesini durdurun.
  - **Windows spot'ta üçüncü taraf önerileri**: Windows, Microsoft tarafından yayımlanmayan içeriği önermesini Spot'un durdurun.
  - **Tüketici özellikleri**: Başlat menüsü önerileri ve üyelik bildirimleri, gibi özellikleri engellemenizi sağlar.
  - **Windows ipuçları**: açılır ipuçlarını Windows içinde görüntülenmesini engelleyin sağlar.
  - **İşlem merkezinde Windows spot**: blok Windows spot önerilerinin Windows İşlem Merkezi'nde görünmesini yeni uygulama veya güvenlik içeriği ister.
  - **Windows spot kişiselleştirme**: durakları Windows Spot'un sonuçları kişiselleştirme, bir cihazın kullanım tabanlı.
  - **Windows Karşılama deneyimi**: yeni veya güncelleştirilmiş özellikleri kullanıcı bilgilerini gösteren Windows Karşılama deneyimi engelleyin.

## <a name="projection"></a>Projeksiyon

- **Kablosuz görüntü alıcılarından kullanıcı girişini**: kablosuz görüntü alıcılarından kullanıcı girişini engeller.
- **Bu Bilgisayara yansıtma**: diğer cihazların yansıtma için bilgisayarı bulma durdurur.
- **Eşleştirme için PIN iste**: bir projeksiyon cihazına bağlanırken PIN isteyin.

## <a name="cloud-printer"></a>Bulut Yazıcı

- **Yazıcı bulma URL'si**: Bulut yazıcılarını bulmak için URL'yi girin.
- **Yazıcı erişim yetkilisi URL'si**: OAuth belirteçlerini almak için kimlik doğrulama uç noktası URL'sini girin. Örneğin `https://login.microsoftonline.com/your Azure AD Tenant ID` gibi bir URI girebilirsiniz.
- **Azure yerel istemci uygulama GUID'si**: Oauthauthority'den OAuth belirteçlerini almak için izin verilen bir istemci uygulama GUID'si girin.
- **Yazdırma hizmeti kaynak URI'si**: Azure portalında yapılandırılmış yazdırma hizmetinin OAuth kaynak URI'si girin. Örneğin `http://MicrosoftEnterpriseCloudPrint/CloudPrint` gibi bir URI girebilirsiniz.
- **Sorgulanacak en yüksek MB/s (yalnızca mobil)**: sorgulanmasını yapmak istediğiniz yazıcılar maksimum sayısını girin. Örneğin, şunu girin: `10`.
- **Yazıcı bulma hizmeti kaynak URI'si**: yazıcı bulma için OAuth kaynak URI'si girin Azure Portalı'nda yapılandırılmış hizmet. Örneğin `http://MopriaDiscoveryService/CloudPrint` gibi bir URI girebilirsiniz.

> [!TIP]
> [Windows Server Hibrit Bulut Yazdırma](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-overview)’yı ayarladıktan sonra bu ayarları yapılandırabilir ve daha sonra Windows cihazlarına dağıtabilirsiniz.

## <a name="local-printer"></a>Yerel Yazıcı

- **Yazıcılar**: eklenmiş olan yerel yazıcı listesi.
- **Varsayılan yazıcı**: varsayılan yazıcıyı ayarlayın.
- **Yeni yazıcı eklemek için kullanıcı erişimi**: izin verme veya engelleme yerel yazıcı kullanımına.

## <a name="reporting-and-telemetry"></a>Raporlama ve Telemetri

- **Kullanım verilerini paylaş**: gönderilen Tanılama verileri düzeyini seçin. Seçenekleriniz şunlardır:
  - Güvenlik
  - Temel
  - Gelişmiş
  - Tam
- **Microsoft Edge tarama verilerini Microsoft 365 analytics'e gönderme**: Bu özelliği kullanmak için **kullanım verilerini paylaş** ayarlar **geliştirilmiş** veya **tam**. Hangi verilerin Microsoft Edge, yapılandırılmış bir ticari kimliği ile Kurumsal cihazlarda Microsoft 365 Analytics'e gönderir. Bu özellik denetler Seçenekleriniz şunlardır:
  - **Yapılandırılmamış**: işletim sistemi varsayılan, tüm gözatma geçmişini gönderemeyebilir kullanır
  - **Yalnızca intranet veri gönderme**: intranet veri geçmişini göndermek yöneticinin sağlar
  - **Yalnızca İnternet'e veri göndermek**: internet veri geçmişini göndermek yöneticinin sağlar
  - **İntranet ve İnternet'e veri göndermek**: intranet ve internet veri geçmişini göndermek yöneticinin sağlar
- **Telemetri proxy sunucusu**: tam etki alanı adı (FQDN) veya bağlı kullanıcı deneyimleri ve Telemetri istekleri, Güvenli Yuva Katmanı (SSL) bağlantısı kullanarak iletmek için bir proxy sunucusunun IP adresini girin. Bu ayarın biçimi *sunucu*:*bağlantı noktası* olur. Adlandırılmış proxy başarısız olursa veya bu ilke etkinleştirildiğinde girilen bir proxy yoksa bağlı kullanıcı deneyimleri ve Telemetri verileri gönderilen değil ve yerel cihazda kalır.

  Örnek biçimler:

  ```
  IPv4: 192.246.246.106:100
  IPv6: [2001:4898:4010:4013:95c1:a8b2:953c:c633]:100
  FQDN: www.contoso.com:345
  ```

## <a name="messaging"></a>Mesajlaşma

- **İleti eşitleme (yalnızca mobil)**: devre dışı her yerden Mesajlaşma ve metin iletisi yedekleme ve geri yükleme.
- **MMS (yalnızca mobil)**: cihazdaki MMS gönderme ve alma işlevini devre dışı bırakın.
- **RCS (yalnızca mobil)**: cihazdaki zengin iletişim hizmetleri gönderme ve alma işlevini devre dışı bırakın.

## <a name="more-information"></a>Daha Fazla Bilgi

Her bir ayara dair ek teknik ayrıntılar ve hangi Windows sürümlerinin desteklendiği hakkında bilgi için bkz. [Windows 10 İlke CSP Başvurusu](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)
