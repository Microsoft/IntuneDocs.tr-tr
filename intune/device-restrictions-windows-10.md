---
title: Microsoft Intune - Azure’da Windows 10 cihaz kısıtlama ayarları | Microsoft Docs
description: Tüm ayarları ve Windows 10 ve üzeri cihazlarda cihaz kısıtlamaları oluşturmak için bunlara ilişkin açıklamaların listesini bakın. Bu ayarları yapılandırma profilinde de ekran görüntüleri, parola gereksinimleri, bilgi noktası ayarları, depolama, Edge tarayıcısı, Windows defender uygulama denetimi, bulutta, Başlat menüsünde ve diğer Microsoft Intune erişmek için kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.openlocfilehash: f2b75eb5a87dbfd7a17aee83f173d3d472920428
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203646"
---
# <a name="windows-10-and-newer-device-settings-to-allow-or-restrict-features-using-intune"></a>İzin verme veya kısıtlamanıza Intune kullanarak Windows 10 (ve üzeri) cihaz ayarları

Bu makalede, listeler ve Windows 10 ve daha yeni cihazlarda denetleyebileceğiniz farklı ayarlar açıklanır. Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, bu ayarları kullanın izin ver veya özellikleri devre dışı bırakabilir, parola kuralları ayarla, kilit ekranı özelleştirmek için Windows Defender'ı ve daha fazlasını kullanın.

Bu ayarlar, ıntune'da cihaz yapılandırma profili eklenir ve ardından atanan veya Windows 10 cihazlarına dağıtılabilir.

> [!Note]
> Tüm Windows sürümlerinde bütün ayarlar kullanılabilir değildir

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz yapılandırma profili oluşturma](device-restrictions-configure.md).

## <a name="app-store"></a>Uygulama Mağazası

- **Uygulama Mağazası (yalnızca mobil)**: Etkinleştirin veya Windows 10 Mobile cihazlarda uygulama mağazasına kullanımını engelleyin.
- **Mağaza uygulamalarını otomatik güncelleştir**: Otomatik olarak güncelleştirilmesi için Microsoft Store yüklenen uygulamalar sağlar.
- **Güvenilen uygulama yüklemesi**: Dışarıdan yüklenmesine izin güvenilen bir sertifikayla imzalanan uygulamaların sağlar.
- **Geliştirici kilidini açma**: Dışarıdan yüklenen uygulamaların son kullanıcı tarafından değiştirilmesine izin verme gibi Windows Geliştirici ayarlarına izin verin.
- **Paylaşılan kullanıcı uygulaması verileri**: Uygulamaların aynı cihazdaki farklı kullanıcılar arasında veri paylaşmasına izin verir.
- **Yalnızca özel mağaza kullan**: Yalnızca özel mağazanızdan uygulama indirmek son kullanıcılara izin vermek için bu seçeneği etkinleştirin.
- **Mağazadan indirilen uygulamaları başlatma Store**: Cihaza önceden yüklenmiş veya Microsoft Store yüklenen tüm uygulamaları devre dışı bırakmak için kullanılır.
- **Uygulama verilerini sistem birimine Yükle**: Uygulamaların cihazın sistem birimine veri depolama durdurur.
- **Uygulamaları sistem sürücüsüne Yükle**: Uygulamaların cihazın sistem sürücüsüne veri depolama durdurur.
- **Oyun DVR (yalnızca Masaüstü)**: Kaydetme ve oyun yayın izin verilip verilmediğini yapılandırır.
- **Uygulamaları yalnızca mağazadan**: Kullanıcıların uygulama mağazası dışındaki yerlerden uygulama yükleyip yükleyemeyeceğini yapılandırır.

## <a name="cellular-and-connectivity"></a>Hücresel ve Bağlantı

- **Hücresel veri kanalı**: Kullanıcıların bir hücresel ağa bağlı olduğunuzda Web'e gözatma gibi veri kullanmasını durdurun. 
- **Veri dolaşımı**: Verilere erişirken ağlar arasında dolaşıma izin verin.
- **Hücresel ağ üzerinden VPN**: Cihazın cep telefonu şebekesine bağlandığında VPN bağlantılarına erişip erişemeyeceğini denetler.
- **Hücresel ağ üzerinden VPN dolaşımı**: Cihazın cep telefonu şebekesinde dolaşımı sırasında VPN bağlantılarına erişip erişemeyeceğini denetler.
- **Bluetooth**: Kullanıcı etkinleştirme ve cihazda Bluetooth yapılandırabilir olup olmadığını denetler.
- **Bluetooth bulunabilirlik**: Cihazın diğer Bluetooth özellikli cihazlar tarafından bulunabilmesine olanak sağlar.
- **Bluetooth önceden eşleştirme**: Belirli Bluetooth cihazlarını bir konak cihazla otomatik olarak kullanmak üzere yapılandırmanıza olanak sağlar.
- **Bluetooth reklamlarına**: Cihazın Bluetooth üzerinden reklam almasına izin verir.
- **Bağlı cihazlar hizmetine**: Bulma ve Bluetooth diğer cihazlara bağlanmayı etkinleştiren bağlı cihazlar hizmetine izin verilip verilmeyeceğini seçmenize olanak tanır.
- **NFC**: Kullanıcının cihazda yakın alan iletişimi (NFC) özelliklerini yapılandırmak ve etkinleştirmek olanak sağlar.
- **Wi-Fi**: Kullanıcının etkinleştirme ve (yalnızca Windows 10 Mobile) cihazda Wi-Fi yapılandırmasına olanak tanır.
- **Wi-Fi etkin noktalarına otomatik bağlanma**: Cihazın ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmasına ve bağlantıyla ilgili hüküm ve koşulları otomatik olarak kabul etmesine olanak sağlar.
- **Elle Wi-Fi yapılandırmasına**: Olup, kullanıcının kendi Wi-Fi bağlantılarını yapılandırıp yapılandıramayacağını veya olup yalnızca Wi-Fi profili (yalnızca Windows 10 Mobile) tarafından yapılandırılan bağlantıları kullanıp kullanamayacağını.
- **Wi-Fi tarama aralığı**: Ne sıklıkta belirtin cihazlar için Wi-Fi ağlarını tarama. 1 (en çok) ile 500 (en az) arasında bir değer belirtin.
- **Bluetooth'a izin verilen hizmetler**: Onaltılık dize olarak izin verilen Bluetooth hizmetleri ve profillerinin bir listesini belirtin.

## <a name="cloud-and-storage"></a>Bulut ve Depolama

- **Microsoft hesabı**: Kullanıcının bir Microsoft hesabını cihazla ilişkilendirmesine olanak sağlar.
- **Microsoft olmayan hesaplar**: Bir Microsoft hesabı ile ilişkili olmayan e-posta hesaplarına cihaza ekleme olanağı sunar.
- **Microsoft hesabı için ayar eşitlemesi**: Cihazlar arasında eşitlenmesine izin, bir Microsoft hesabıyla ilişkilendirilmiş cihaz ve uygulama ayarlarının izin verin.

## <a name="cloud-printer"></a>Bulut Yazıcı

- **Yazıcı bulma URL'si**: Bulut yazıcılarını bulmak için URL'yi girin.
- **Yazıcı erişim yetkilisi URL'si**: OAuth belirteçlerini almak için kimlik doğrulama uç noktası URL'sini girin. Örneğin `https://login.microsoftonline.com/your Azure AD Tenant ID` gibi bir URI girebilirsiniz.
- **Azure yerel istemci uygulama GUID'si**: Oauthauthority'den OAuth belirteçlerini almak için izin verilen bir istemci uygulama GUID'si girin.
- **Yazdırma hizmeti kaynak URI'si**: Azure portalında yapılandırılmış yazdırma hizmetinin OAuth kaynak URI'si girin. Örneğin `http://MicrosoftEnterpriseCloudPrint/CloudPrint` gibi bir URI girebilirsiniz.
- **Sorgulanacak en yüksek MB/s (yalnızca mobil)**: Sorgulanacak istediğiniz yazıcılar maksimum sayısını girin. Örneğin, şunu girin: `10`.
- **Yazıcı bulma hizmeti kaynak URI'si**: Yazıcı bulma için OAuth kaynak URI'si girin Azure Portalı'nda yapılandırılmış hizmet. Örneğin `http://MopriaDiscoveryService/CloudPrint` gibi bir URI girebilirsiniz.

> [!TIP]
> [Windows Server Hibrit Bulut Yazdırma](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-overview)’yı ayarladıktan sonra bu ayarları yapılandırabilir ve daha sonra Windows cihazlarına dağıtabilirsiniz.

## <a name="control-panel-and-settings"></a>Denetim Masası ve Ayarlar

- **Ayarlar uygulamasında**: Windows ayarlar uygulamasına erişimi engelleyin.
  - **Sistem**: Ayarlar uygulamasının sistem alanına erişimi engeller.
    - **Güç ve uyku ayarlarının değiştirilmesi (yalnızca Masaüstü)**: Son kullanıcının cihazın güç ve uyku ayarlarını değiştirmesini engeller.
  - **cihazları**: Ayarlar uygulamasının cihazlar alanına erişimi engeller.
  - **Ağ ve Internet**: Ayarlar uygulamasında ağ ve internet alanına erişimi engeller.
  - **Kişiselleştirme**: Ayarlar uygulamasının kişiselleştirme alanına erişimi engeller.
  - **Hesapları**: Ayarlar uygulamasında hesaplar alanına erişimi engeller.
  - **Saat ve dil**: Ayarlar uygulamasında saat ve dil alanına erişimi engeller.
    - **Sistem saatinin değiştirilmesi**: Son kullanıcının cihaz tarih ve saatini değiştirmesini engeller.
    - **Bölge ayarlarının değiştirilmesi (yalnızca Masaüstü)**: Son kullanıcının cihazın bölge ayarlarını değiştirmesini engeller.
    - **Dil ayarlarının değiştirilmesi (yalnızca Masaüstü)**: Kullanıcının cihazın dil ayarlarını değiştirmesini engeller.
  - **Oyun**: Ayarlar kısmında oyun uygulamasına erişimi engeller.
  - **Erişim Kolaylığı**: Erişim Kolaylığı alanına ayarlar uygulamasının erişimi engeller.
  - **Gizlilik**: Ayarlar uygulamasının gizlilik alanına erişimi engeller.
  - **Güncelleştirme ve güvenlik**: Güncelleştirmeler ve güvenlik alanına ayarlar uygulamasına erişimi engeller.

## <a name="display"></a>Görüntüle

- **Uygulamalar için GDI ölçeklendirmeyi aç**
- **Uygulamalar için GDI ölçeklendirmeyi kapat**

  GDI DPI ölçeklendirme, İzleyici başına DPI DPI olmayan uygulamalar sağlar. GDI DPI ölçeklendirme olan eski uygulamaları girin. GDI DPI açmak ve bir uygulama üzerinde devre dışı bırakmak için yapılandırılmış ölçeklemeyle, ölçeklendirme uygulama için devre dışıdır.

## <a name="general"></a>Genel

- **Ekran Yakalama (yalnızca mobil)**: Kullanıcının cihaz ekranını resim olarak yakalamasına izin verir.
- **Kopyala ve Yapıştır (yalnızca mobil)**: İzin kopyalama ve yapıştırma cihazda uygulamalar arasında.
- **Elle kayıt kaldırmaya**: Kullanıcının iş yeri hesabını cihazdan el ile silmesine olanak sağlar.
  - Bilgisayar Azure AD’ye katılmışsa ve otomatik kayıt etkinse, bu ilke ayarı uygulanmaz. 
  - Bu ilke ayarı, Windows 10 Home çalıştıran bilgisayarlarda geçerli değildir.
- **Elle kök sertifika yüklemesi (yalnızca mobil)**: Elle kök sertifikaları ve Ara CAP sertifikaları yüklemesini engeller.

- **Kamera**: İzin verin veya cihazdaki kamera kullanımını engelleyin.
- **OneDrive dosya eşitlemesini**: Cihazın dosyaları Onedrive'a eşitlemesini engeller.
- **Çıkarılabilir Depolama Birimi**: SD kartı gibi dış depolama cihazlarının cihazla kullanılıp kullanılamayacağını belirtir.
- **Coğrafi konum**: Cihazın konum hizmetleri bilgilerini kullanıp kullanamayacağını belirtir.
- **Internet paylaşımı**: Cihazda İnternet bağlantısı paylaşımının kullanımına izin verin.
- **Telefon sıfırlama**: Kullanıcının cihazında bir temizleme denetler.
- **USB bağlantısı (yalnızca mobil)**: Cihazların USB bağlantısı aracılığıyla dış depolama cihazlarına erişip erişemeyeceğini denetler.
- **Hırsızlık önleme modu (yalnızca mobil)**: Windows AntiTheft modunun etkin olup olmadığını yapılandırın.
- **Cortana**: Cortana sesli yardımcısını etkinleştirin veya devre dışı bırakın.
- **Ses kaydı (yalnızca mobil)**: İzin verme veya cihazın ses kaydedicisinin kullanılmasına engelleme.
- **Cihaz adı değişikliğine**: Son kullanıcının (yalnızca Windows 10 Mobile) cihaz adını değiştirmesini engeller.
- **Sağlama paketleri ekleme**: Sağlama paketleri yükleyen çalışma zamanı yapılandırma aracısını engeller.
- **Sağlama paketlerini kaldırma**: Sağlama paketlerini kaldıran çalışma zamanı yapılandırma aracısını engeller.
- **Cihaz bulma**: Bir cihazın diğer cihazlar tarafından bulunmasını engelleyin.
- **Görev değiştirici (yalnızca mobil)**: Cihazdaki görev değiştiriciyi engeller.
- **SIM kart hatası iletişim kutusu (yalnızca mobil)**: Bir hata iletisi yok SIM Kart algılanmazsa cihazda görüntüleme alanından engeller.
- **Ink çalışma alanı**: Kullanıcıların Ink çalışma alanına erişmesini engelleyin. **Yapılandırılmamış** açar Ink çalışma alanına ve kullanıcının kilit ekranının üstünde kullanmasına izin verilir.
- **Otomatik yeniden dağıtım**: Tüm kullanıcı verilerini ve ayarlarını kullanarak yönetim haklarına sahip kullanıcılara **CTRL + Win + R** cihaz kilit ekranında. Cihaz otomatik olarak yeniden yapılandırılacak ve yönetime yeniden kaydedilir.
- **Kullanıcıların (yalnızca Windows Insider) cihaz kurulumu sırasında ağa bağlanmasını gerektiren**: Seçin **gerektiren** cihaz Windows 10 kurulumu sırasında geçmiş ağ sayfasına devam etmeden önce bir ağa bağlanacak şekilde. Bu özellik önizlemedeyken bu ayarı kullanmak için Windows Insider derleme 1809 veya sonrası gerekir.
- **Son işlem Görev Yöneticisi'nden**: Bu ayar, yönetici olmayanların son görevler için Görev Yöneticisi'ni kullanıp kullanamayacağını belirler. **Blok** Görev Yöneticisi'ni kullanarak bir işlem veya cihazdaki görev sona erdirmek için standart kullanıcılar (Yönetici olmayanlar) engeller. **Yapılandırılmamış** (varsayılan), Görev Yöneticisi'ni kullanarak görev ya da bir işlemi sonlandırmak standart kullanıcılar izin verir.

## <a name="kiosk-preview---obsolete"></a>Bilgi noktası (Önizleme) - Eski

Bu ayarlar salt okunurdur ve değiştirilemez. Bilgi noktası modunu yapılandırmak için bkz. [Windows 10 ve üzerinde bilgi noktası ayarları](kiosk-settings.md).

Bir bilgi noktası cihazı genellikle tek bir uygulama veya belirli bir uygulamalar kümesi çalıştırır. Kullanıcılar, başka özellik veya işlevlere cihaza erişimi engellenmiştir.

- **Bilgi noktası modu**: İlke tarafından desteklenen bilgi noktası modu türünü tanımlar. Şu seçenekler mevcuttur:

  - **Yapılandırılmamış** (varsayılan): Cihaz bilgi noktası modu ilke sağlamaz.
  - **Tek uygulama bilgi noktası**: Profil, cihazın yalnızca bir uygulama çalıştırmasına olanak tanır. Kullanıcı oturum açtığında belirli bir uygulama başlar. Bu mod ayrıca kullanıcının yeni uygulamalar açmasını veya çalışan uygulamayı değiştirmesini önler.
  - **Çoklu uygulama bilgi noktası**: Profil birçok uygulamaları çalıştırmak için cihazı etkinleştirir. Yalnızca eklediğiniz uygulamalar kullanıcı tarafından kullanılabilir. Bir çoklu uygulama bilgi noktasının veya sabit amaçlı cihazın yararı, yalnızca ihtiyaç duyulan uygulamalara erişim sağlayıp gerek olmayan uygulamaları göz önünden kaldırarak bireylere anlaşılması kolay bir deneyim sunmasıdır.

#### <a name="single-app-kiosks"></a>Tek uygulama bilgi noktaları

Aşağıdaki ayarları girin:

- **Kullanıcı hesabı**: Yerel (cihaz) kullanıcı hesabı, bir AD etki alanı hesabı veya bilgi noktası uygulamasıyla ilişkili bir Azure AD hesabı girin.
  - Yerel hesap: Girin `devicename\accountname`, `.\accountname`, veya `accountname`
  - Etki alanı hesabı: Olarak girin `domain\accountname`
  - Azure AD hesabı: Girin `AzureAD\emailaddress`. Sabit bir etki alanıymış gibi “AzureAD” girdiğinizden emin olun. Daha sonra Azure AD e-posta adresiyle devam edin. Örneğin, şunu girin: `AzureAD\user@contoso.onmicrosoft.com`.

    Herkese açık ortamlarda bulunan ve otomatik oturum açma etkin bilgi noktaları için olabildiğince az ayrıcalığa sahip bir kullanıcı türü (yerel standart kullanıcı hesabı gibi) kullanılmalıdır. Bilgi noktası modu için bir Azure AD hesabı kullanıyorsanız `AzureAD\user@yourorganization.com` girdiğinizden emin olun.

- **Uygulama kullanıcı modeli kimliği (AUMID)**: Bilgi noktası uygulamasının AUMID'sini girin. Daha fazla bilgi için bkz. [Yüklü bir uygulamanın Uygulama Kullanıcı Model Kimliğini bulma](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

#### <a name="multi-app-kiosks"></a>Çoklu uygulama bilgi noktaları

[Çoklu uygulama bilgi noktaları](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configure-a-kiosk-in-microsoft-intune), izin verilen uygulamaları ve diğer ayarları listeleyen bir bilgi noktası yapılandırması kullanır. 

**Ekle** düğmesini kullanarak bir bilgi noktası yapılandırması oluşturun (veya mevcut bir yapılandırmayı seçin). Daha sonra aşağıdaki ayarları girin:

- **Bilgi noktası yapılandırma adı**: Yapılandırmasını tanımlamak için kullanılan kolay bir ad girin.

- **Bilgi noktası uygulamaları**: Başlat menüsünde kullanılabilir olan uygulamaları girin. Kullanıcılar yalnızca eklediğiniz uygulamaları kullanabilir.

  - **Uygulama türü**: Bilgi noktası uygulamasının türünü seçin:
    - **Win32 uygulaması**: Geleneksel bir masaüstü uygulaması. Yürütülebilir dosyanın cihaza göre tam yol adına ihtiyacınız vardır.
    - **UWP uygulaması**: Bir evrensel Windows uygulaması. [Uygulamanın AUMID’sine](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) ihtiyacınız vardır.

  - **tanımlayıcı**: Tam yol adını (Win32 uygulamaları), yürütülebilir dosyayı girin veya [uygulamanın AUMID'ini](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (UWP uygulamaları).

- **Görev**: Tercih **etkinleştirme** (Göster) görev veya saklamak **yapılandırılmadı** (gizli bilgi).

- **Başlangıç menüsü düzeni**: Başlat menüsünde uygulamaları nasıl göründüğünü açıklayan bir XML dosyası girin. [Başlangıç düzenini özelleştirme ve dışarı aktarma](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout), rehberlik ve örnek XML sağlar.

  [Uygulamaları çalıştıran bir Windows 10 bilgi noktası oluşturma](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file) kullanarak ve XML dosyaları oluşturma hakkında daha fazla ayrıntı sağlar.

- **Atanan kullanıcılar**: Eklediğiniz uygulamaları kullanabilecek bir veya daha fazla kullanıcı hesaplarını ekleyin. Hesap oturum açtığında, yalnızca yapılandırmada tanımlanmış uygulamalar kullanılabilir durumda olur. Hesap, cihaz için yerel olabilir veya bilgi noktası uygulamasıyla ilişkili Azure AD hesabı olabilir.

    Herkese açık ortamlarda bulunan ve otomatik oturum açma etkin bilgi noktaları için olabildiğince az ayrıcalığa sahip bir kullanıcı türü (yerel standart kullanıcı hesabı gibi) kullanılmalıdır. Bir Azure Active Directory (AD) hesabını bilgi noktası moduna yapılandırmak için `domain\user@tenant.com` biçimini kullanın.

## <a name="locked-screen-experience"></a>Kilit ekranı deneyimi

- **İşlem Merkezi bildirimleri (yalnızca mobil)**: Sağlar İşlem Merkezi bildirimleri (yalnızca Windows 10 Mobile) cihaz kilit ekranında görüntülenir.
- **Ekranı resmi URL'si (yalnızca Masaüstü)**: Windows kilit ekranı duvar kağıdı olarak kullanılan JPEG biçiminde bir resmin URL'sini girin. Kullanıcılar, bu ayarı değiştiremezsiniz.
- **Kullanıcı tarafından yapılandırılabilir ekran zaman aşımı (yalnızca mobil)**: Kullanıcıların süreyi yapılandırmasına olanak tanır 
- **(Yalnızca Masaüstü) kilitli ekranda Cortana**: Kullanıcı, cihaz kilit ekranında (yalnızca Windows 10 Masaüstü) olduğunda Cortana ile etkileşim kurmasına izin vermez.
- **Kilitli ekranda bildirimler**: Gelen gösteren cihaz kilitleme ekranında uyarı iletileri engelleyin.
- **Ekran zaman aşımı (yalnızca mobil)**: Bunu kapanır olduğunda ekranın kapanarak saniye cinsinden süreyi belirtir.

## <a name="messaging"></a>Mesajlaşma

- **İleti eşitleme (yalnızca mobil)**: Her yerden Mesajlaşma ve metin iletisi yedekleme devre dışı bırakın ve geri yükleyin.
- **MMS (yalnızca mobil)**: Cihazdaki MMS gönderme ve alma işlevini devre dışı bırakın.
- **RCS (yalnızca mobil)**: Cihazdaki zengin iletişim hizmetleri gönderme ve alma işlevini devre dışı bırakın.

## <a name="microsoft-edge-browser"></a>Microsoft Edge Tarayıcısı

### <a name="start-experience"></a>Başlangıç deneyimi

- **Microsoft Edge ile Başlat**: Microsoft Edge başladığında, hangi sayfaların Aç'ı seçin. Seçenekleriniz şunlardır:
  - **Başlangıç sayfaları**: İşletim sistemi tarafından tanımlanan varsayılan başlangıç sayfasını Microsoft Edge başlama
  - **Yeni bir sekme sayfası**: Microsoft Edge yük ne olursa olsun tanımlanan **yeni bir sekme sayfası URL'si** ayarı
  - **Son oturumun sayfa**: Microsoft Edge son oturum sayfayı yüklemez 
  - **Özel başlangıç sayfası**: Microsoft Edge BT yöneticisi tarafından tanımlı başlangıç sayfasını yükler.
- **Kullanıcı, başlangıç sayfalarını değiştirebilirsiniz**: **İzin** başlangıç sayfalarını değiştirmesine olanak sağlar. Yöneticiler `EdgeHomepageUrls` varsayılan olarak kullanıcıların gördüğü başlangıç sayfalarını girmek için Microsoft Edge açın. **Yapılandırılmamış** kullanıcıların başlangıç sayfalarını değiştirmesini engeller.
- **Yeni sekme sayfası URL'si**: Yeni bir sekme sayfasını açmak için URL'yi girin. Örneğin, şunu girin: `https://www.bing.com`.
- **Açık web içeriği yeni bir sekme sayfasında**: Seçin **blok** Microsoft Edge Web sitesinde yeni bir sekme açmasını durdurmak için. Engellendiğinde, yeni bir sekme boş açın. **Yapılandırılmamış** gösterilene seçmek kullanıcılar izin verebilir cihaz işletim sistemi varsayılan davranışı kullanır.
- **Giriş düğmesi**: Giriş düğmesi seçili olduğunda ne olacağını seçin. Seçenekleriniz şunlardır:
  - **Başlangıç sayfaları**: Seçtiğiniz için seçeneği **Başlat Microsoft Edge ile** açılır ayarlama
  - **Yeni bir sekme sayfası**: Seçtiğiniz için seçeneği **yeni bir sekme sayfası URL'si** açılır ayarlama
  - **Özel giriş düğmesi URL'si**: Seçtiğiniz için seçeneği **giriş düğmesi URL'si** açılır ayarlama
  - **Gizleme giriş düğmesine**: Giriş düğmesini gizler
- **Kullanıcı Giriş düğmesine değiştirebilirsiniz**: **İzin** kullanıcıların giriş düğmesi değiştirmesine olanak tanır. Kullanıcının yaptığı değişiklikleri giriş düğmesi için herhangi bir yönetici ayarları geçersiz kılar. **Yapılandırılmamış** nasıl giriş düğmesi yönetici tarafından yapılandırılan değiştirmesini kullanıcıları engelleyebilir cihaz işletim sistemi varsayılan davranışı kullanır.
- **İlk çalıştırma deneyimi sayfasını göster**: **Blok** durdurur ilk gösteren giriş sayfasından, Microsoft Edge çalıştırma süresi. Bu özellik, kuruluşların sıfır emisyon yapılandırmalarına bu sayfayı engellemesine izin, kayıtlı sağlar. **Yapılandırılmamış** giriş sayfasında gösterilir.
  - **İlk çalıştırma deneyimi URL'si**: Microsoft Edge (yalnızca Windows 10 Mobile) kullanıcı ilk kez çalışan göstermek için sayfanın URL'sini girin.
- **Açılır pencereler**: Seçin **blok** tarayıcıdaki açılır pencereleri durdurmak için. Yalnızca Windows 10 masaüstü için geçerlidir. **Yapılandırılmamış** web tarayıcısında açılır pencerelere izin verir.
- **Internet Explorer'a intranet trafiği Gönder**: **İzin** kullanıcıların (yalnızca Windows 10 Masaüstü) Microsoft Edge yerine Internet Explorer'da intranet Web siteleri açmasına olanak sağlar. **Yapılandırılmamış** Microsoft Edge kullanmasına olanak tanır.
- **Kurumsal mod site listesi konumu**: Kurumsal modda açılan web siteleri listesini içeren bir URL girin. Kullanıcılar bu listeyi değiştiremez. Yalnızca Windows 10 masaüstü için geçerlidir.
- **Açılırken ileti siteleri Internet Explorer'da**: Internet Explorer 11'de bir site açılmadan önce bir bildirim göstermek için Microsoft Edge yapılandırmak için bu ayarı kullanın. Seçenekleriniz şunlardır:
  - **Yapılandırılmamış**: İşletim sistemi varsayılan davranışı, bir ileti gösterilmeyebilir kullanılır.
  - **Microsoft Edge'de siteleri açmak için seçeneği olmadan iletiyi göster**: IE'de siteleri açarken iletiyi gösterir. Siteleri IE'de açın. Microsoft Edge'de siteleri açarken bir seçenek değildir.
  - **İleti açarken Microsoft Edge'de siteleri göster**: IE'de siteleri açarken iletiyi gösterir. İletiyi içeren bir **Microsoft Edge'de kullanmaya devam** kullanıcılar Microsoft Edge yerine IE seçebilmeniz bağlantı.

  > [!IMPORTANT]
  > Bu ayarı etkinleştirmenizi gerektirir **kuruluş modu Site listesini yapılandır** ayarını **tüm intranet sitelerinin Internet Explorer 11'e gönderin** ayarı veya her iki ayar.

- **Microsoft uyumluluk listesini**: **Blok** Microsoft edge'de Microsoft uyumluluk listesini engeller. Microsoft'un bu listesi, Microsoft Edge bilinen uyumluluk sorunlarına sahip siteleri düzgün görüntülenmesi yardımcı olur. **Yapılandırılmamış** kullanarak Microsoft uyumluluk listesini sağlar.
- **Başlangıç sayfalarını ve sayfa yeni sekmede dağıtılacak**: Seçin **blok** başlangıç sayfalarını ve yeni bir sekme sayfası Şubelerdeki Microsoft Edge önlemek için. Önceden yükleme Microsoft Edge başlatın ve yeni bir sekme yükleme süresini en aza indirir. **Yapılandırılmamış** dağıtılacak bu sayfaları için işletim sistemi varsayılan davranışı kullanır.
- **Önceden başlatma başlangıç sayfalarını ve sayfa yeni sekmede**: Seçin **blok** Microsoft Edge başlangıç sayfalarını ve yeni bir sayfa önceden başlamasını engellemek için. Önceden başlatma, Microsoft Edge performansını yardımcı olur ve Microsoft Edge başlatmak için gereken süreyi en aza indirir. **Yapılandırılmamış** bu sayfaları için önceden başlatma işletim sistemi varsayılan davranışı kullanır.

### <a name="favorites-and-search"></a>Sık Kullanılanlar ve arama

- **Sık Kullanılanlar çubuğu**: Sık Kullanılanlar çubuğuna herhangi bir Microsoft Edge sayfasında ne olacağını seçin. Seçenekleriniz şunlardır:
  - **Yapılandırılmamış**: Sık Kullanılanlar çubuğu tüm sayfalardaki gizlemek için işletim sistemi varsayılan davranışı kullanır. Kullanıcının bu ayarı değiştirebilirsiniz.
  - **Gizleme**: Sık Kullanılanlar çubuğu tüm sayfalardaki gizler. Kullanıcının bu ayarı değiştiremezsiniz.
  - **Göster**: Sık Kullanılanlar çubuğu tüm sayfalarında gösterilir. Kullanıcının bu ayarı değiştiremezsiniz.
- **Sık Kullanılanlar listesine**: URL'lerin bir listesini, Sık Kullanılanlar dosyaya ekleyin. Örneğin, ekleme `http://contoso.com/favorites.html`.
- **Sık Kullanılanlarda değişiklikler kısıtlama**: **Blok** ekleme, alma, sıralama veya Sık Kullanılanlar listesine düzenleme kullanıcıların önlemek için. **Yapılandırılmamış** listesini değiştirmek kullanıcıların izin işletim sistemi varsayılan kullanır.
- **(Yalnızca Masaüstü) Microsoft tarayıcıları arasında sık kullanılanları Eşitle**: **Gerekli** Windows Internet Explorer ve Microsoft Edge arasında sık kullanılanları eşitlemeye zorlar. Ekleme, silme, değişiklikler ve siparişi değişikliklerinin Sık Kullanılanlar tarayıcılar arasında paylaşılır.  **Yapılandırılmamış** kullanıcıların seçim tarayıcıları arasında sık kullanılanları Eşitle verebilir işletim sistemi varsayılan kullanır.
- **Varsayılan arama motorunu**: Varsayılan arama motorunu cihazda seçin. Son kullanıcılar bu değeri istediği zaman değiştirebilir. Seçenekleriniz şunlardır:
  - Varsayılan
  - Bing
  - Google
  - Yahoo
  - Özel değer
- **Arama önerileri**: **Yapılandırılmamış** adres çubuğunda arama tümcecikleri yazarken arama motorunuzun site olanak tanır. **Blok** bu özellik engeller.

### <a name="privacy-and-security"></a>Gizlilik ve güvenlik

- **InPrivate Gözatma**: **Blok** son kullanıcıların InPrivate Gözatma oturumları açmasını engeller. **Yapılandırılmamış** bu özelliği sağlar.
- **Tarama geçmişi Kaydet**: **Blok** Microsoft Edge gözatma geçmişini kaydetmesini engeller. **Yapılandırılmamış** gözatma geçmişini kaydetmeye olanak tanır.
- **Clear veri (yalnızca Masaüstü) Çıkışta gözatma**: **Gerekli** geçmişi ve kullanıcının Microsoft Edge çıkarken tarama verilerini temizler. **Yapılandırılmamış** tarama verilerini önbelleğe alabilir işletim sistemi varsayılan kullanır.
- **Tarayıcı ayarlarını kullanıcının cihazlar arasında eşitleme**: Tarayıcı ayarlarını cihazlar arasında eşitleme istediğiniz şekli seçin. Seçenekleriniz şunlardır:
  - **İzin**: Microsoft Edge tarayıcı ayarları kullanıcının cihazlar arasında eşitlenmesine izin ver
  - **Blok ve kullanıcı geçersiz kılma etkinleştir**: Microsoft Edge tarayıcı ayarları kullanıcının cihazlar arasında eşitlemeyi engelleyin. Kullanıcılar bu ayarı geçersiz kılabilirsiniz.
  - **Blok**: Microsoft Edge tarayıcı ayarının kullanıcının cihazlar arasında eşitlemeyi engelleyin. Kullanıcılar, bu ayarı geçersiz kılamaz.
- **Parola Yöneticisi**: **Blok** Microsoft Edge parola Yöneticisi özelliğini devre dışı bırakır. **Yapılandırılmamış** bu özelliği sağlar.
- **Tanımlama bilgilerini**: Web tarayıcısında tanımlama bilgilerine nasıl işleneceğini seçin. Seçenekleriniz şunlardır:
  - **İzin**: Tanımlama bilgilerinin cihazda depolanır.
  - **Tüm tanımlama bilgilerini engelle**: Tanımlama bilgilerinin cihazda depolanmaz.
  - **Yalnızca üçüncü taraf tanımlama bilgilerini engelle**: Üçüncü taraf veya iş ortağı tanımlama bilgilerinin cihazda depolanmaz.
- **Otomatik doldurmaya**: **Blok** otomatik doldurma özelliğinin cihazda devre dışı bırakır. **Yapılandırılmamış** kullanıcıların (yalnızca Windows 10 Masaüstü) tarayıcıdaki otomatik tamamlama ayarlarını değiştirmesine olanak tanır.
- **Kullanıcıyı-izleme üst bilgileri gönderme**: **Yapılandırılmamış** cihazlar (önerilen) izleme bilgisi isteyen Web sitelerine not track üst bilgileri göndermesini gerektirir. Seçin **blok** cihaz kullanıcıyı izlemek Web siteleri sağlayan bu üst bilgileri göndermesini önlemek için.
- **WebRtc localhost IP adresi**: **Blok** web RTC protokolü kullanılarak telefon aramaları gerçekleştirilirken gösteriliyor kullanıcıların localhost IP adresinin engeller. **Yapılandırılmamış** kullanıcıların localhost IP adresi bu protokolü kullanılarak telefon aramaları gerçekleştirilirken gösterilmesini sağlar.
- **Canlı kutucuk veri toplama**: Seçin **blok** Windows Canlı bir site sabitlenmiş Kutucuklardan birini bilgi toplamayı Başlat menüsünden Microsoft Edge için gelen durdurmak için. **Yapılandırılmamış** bu bilgilerin toplanmasını sağlar.
- **Kullanıcı sertifika hataları geçersiz kılma**: **Blok** kullanıcıların SSL veya TLS hata içeren Web sitelerine erişmesini engeller. **Yapılandırılmamış** bu sitelere erişmesine olanak tanır.

### <a name="additional"></a>Ek

- **Microsoft Edge tarayıcısı (yalnızca mobil)**: Seçin **blok** cihazda Microsoft Edge kullanarak önlemek için. Microsoft Edge'i engellerseniz, ayrı ayrı ayarlar yalnızca Masaüstü için geçerlidir. **Yapılandırılmamış** cihazda Microsoft Edge web tarayıcısının kullanımına izin verir.
- **Adres çubuğu açılır listesi (yalnızca Masaüstü)**: **Blok** Microsoft Edge yazarken öneriler listesi aşağı açılan listesinde göstermesini durdurur. Bu seçenek, Microsoft Edge ile Microsoft Hizmetleri arasında ağ bant genişliğini en aza yardımcı olur. **Yapılandırılmamış** öneriler listesini göstermek Microsoft Edge sağlar.
- **Tam ekran**: Seçin **blok** yalnızca web içeriğini gösterme ve gizleme Microsoft Edge (tam ekran modu), Microsoft Edge önlemek için. **Yapılandırılmamış** tam ekran modunu kullanmak Microsoft Edge izin veren varsayılan işletim sistemi kullanır.
- **About: Flags sayfasına**: **Blok** son kullanıcıların erişmesini engelleyen `about:flags` Geliştirici ayarları ve Deneysel ayarlar içeren Microsoft edge'de sayfası. **Yapılandırılmamış** erişilebilmesini sağlar işletim sistemi varsayılan `about:flags` sayfası.
- **Geliştirici Araçları**: **Blok** son kullanıcılar Microsoft Edge geliştirici araçlarını açmasını engeller. **Yapılandırılmamış** geliştirici araçları açmasına izin verir.
- **Uzantıları**: **Yapılandırılmamış** son kullanıcıların cihazda Microsoft Edge uzantıları yüklemek olanak tanır. **Blok** yüklemeyi engeller.
- **Dışarıdan yükleme geliştirici uzantıları**: **Blok** Microsoft Edge yükler ve doğrulanmamış uzantılarını kullanarak çalışan dışarıdan yükleme engelleyen **yük uzantıları** özelliği. **Yapılandırılmamış** dışarıdan yükleme olarak izin verebileceği işletim sistemi varsayılan kullanır.
- **Gerekli uzantıları**: Microsoft edge'de son kullanıcılar tarafından hangi uzantıları kapatılamaz seçin. Paket aile adları'nı girin ve seçin **Ekle**. [Bir paket aile adı (PFN) bulma](https://docs.microsoft.com/sccm/protect/deploy-use/find-a-pfn-for-per-app-vpn) listeler rehberlik sağlar.

  Ayrıca **alma** paket aile adları içeren bir CSV dosyası.

- **JavaScript**: Seçin **blok** tarayıcıda Java betiğinin cihazda çalışmasını engelleyin. **Yapılandırılmamış** Microsoft Edge tarayıcısında çalıştırmak için Javascript gibi betiklerin verir.

## <a name="network-proxy"></a>Ağ proxy’si

- **Proxy ayarlarını otomatik olarak algıla**: Etkinleştirildiğinde, cihaz bir PAC betiğinin yolunu bulmaya çalışır.
- **Proxy betiği kullan**: Proxy sunucusunu yapılandırmak için bir PAC betiğinin yolu girmek için bu seçeneği belirleyin.
  - **Kurulum betiği adresi URL'si**: Proxy sunucusunu yapılandırmak için kullanmak istediğiniz bir PAC betiğinin URL'sini girin.
- **El ile proxy sunucusu kullan**: Ara sunucu bilgilerini el ile girmek için bu seçeneği belirleyin.
  - **Adresi**: Adını veya proxy sunucusunun IP adresini girin.
  - **Bağlantı noktası numarası**: Proxy sunucunuzun bağlantı noktası numarasını girin.
  - **Proxy özel durumları**: Proxy sunucusunu kullanmaması gereken herhangi bir URL girin. Her birini ayırmak için noktalı virgül kullanın.
  - **Yerel adres için proxy sunucuyu atla**: İntranetinizde yerel adresler için proxy sunucusunu kullanmak istemiyorsanız bu seçeneği etkinleştirin.

## <a name="password"></a>istemcisiyle yönetilen bir cihaz için)

- **Parola**: Son kullanıcının cihaza erişmek için parola girmesini zorunlu tutun.
  - **Gerekli parola türü**: Parola sayısal mı olacağını belirtir. yalnızca ya da alfasayısal.
  - **Minimum parola uzunluğu**: Yalnızca Windows 10 Mobile için geçerlidir.
  - **Cihaz silinmeden önceki oturum açma hatası sayısı**: Windows 10 çalıştıran cihazlar için: BitLocker etkin cihazı varsa, belirtilen sayıda oturum açma başarısız olduktan sonra BitLocker kurtarma moduna konur. Cihazda BitLocker etkin değilse, bu ayar geçerli değildir. Windows 10 Mobile çalıştıran cihazlar için: Oturum açma başarısız belirttiğiniz sayısından sonra cihaz silinir.
  - **Ekran kilitlenmeden işlem yapılmayan dakika**: Ekran kilitlenmeden önce cihazın boşta bekleyeceği süreyi belirtir.
  - **Parola süresinin sonu (gün)**: Cihaz parolasının ne kadar süre sonra değiştirilmesi gerektiğini belirtir.
  - **Önceki parolaların yeniden kullanılmasını engelle**: Önceden kullanılmış ve cihaz tarafından anımsanacak olan parola sayısını belirtir.
  - **Cihaz (yalnızca mobil) boşta kalma durumundan çıktığında parola isteme**: Boşta durumundaki bir cihazın kilidini açmak için kullanıcının parola girmesi gerektiğini belirtir (yalnızca Windows 10 Mobile).
  - **Basit parolalar**: 1111 ve 1234 gibi basit parolaların kullanımına olanak sağlar. Bu ayar, Windows resimli parolalarının kullanımına izin verir veya bunu engeller.
- **Şifreleme**: Hedeflenen cihazlarda şifrelemeyi etkinleştirin.

## <a name="per-app-privacy-exceptions"></a>Uygulama başına gizlilik özel durumları

"Varsayılan gizlilik" altında tanımladığınızdan farklı bir gizlilik davranışı olması gereken uygulamaları ekleyebilirsiniz.

- **Paket adı**: Uygulama paketi ailesi adı.
- **Uygulama adı**: Uygulama adı.

### <a name="exceptions"></a>Özel durumlar

- **Hesap bilgileri**: Bu uygulamanın kullanıcı adına, resmine ve diğer kişi bilgilerine erişip erişemeyeceğini tanımlayın.
- **Arka plan uygulamaları**: Bu uygulamanın arka planda çalışıp çalışamayacağını tanımlayın.
- **Takvim**: Bu uygulamanın takvime erişip erişemeyeceğini tanımlayın.
- **Arama Geçmişi**: Bu uygulamanın çağrı geçmişime erişip erişemeyeceğini tanımlayın.
- **Kamera**: Bu uygulamanın kameraya erişip erişemeyeceğini tanımlayın.
- **Kişiler**: Bu uygulamanın kişilere erişip erişemeyeceğini tanımlayın.
- **e-posta**: Bu uygulamaya erişebilir ve e-posta Gönder olup olmadığını tanımlar.
- **Konum**: Bu uygulamanın konum bilgilerine erişip erişemeyeceğini tanımlayın.
- **Mesajlaşma**: Bu uygulama okuma veya metin veya MMS iletisi gönder tanımlayın.
- **Mikrofon**: Bu uygulamanın mikrofonu kullanıp kullanamayacağını tanımlayın.
- **Hareket**: Bu uygulamanın cihaz hareket bilgilerine erişip erişemeyeceğini tanımlayın.
- **Bildirimleri**: Bu uygulamanın bildirimlere erişip erişemeyeceğini tanımlayın.
- **Telefon**: Bu uygulamanın telefona erişip erişemeyeceğini tanımlayın.
- **Radyolara**: Bazı uygulamalar gönderin ve bu Radyoları açıp kapatması gerekir veri almak için Cihazınızı Radyoları (örneğin, Bluetooth) kullanın. Bu uygulamanın bu radyoları denetleyip denetleyemeyeceğini tanımlayın.
- **Görevleri**: Bu uygulamanın görevlerinize erişip erişemeyeceğini tanımlayın.
- **Güvenilen cihazlar**: Donanım zaten bağlanmış olduğunuz veya cihaz ile birlikte gelen donanım olduğu bu uygulamanın güvenilen cihazları kullanıp kullanamayacağını seçin. Örneğin, TV, projektör ve benzeri, güvenilen cihazlar olarak kullanın.
- **Geri bildirim ve tanılama**: Bu uygulamanın tanılama bilgilerine erişip erişemeyeceğini tanımlayın.
- **Cihazlarla Eşitle**: Bu uygulamayı otomatik olarak paylaşabilir ve bilgi cihazı ile doğrudan eşleştirilmeyen Kablosuz cihazlarla eşitleme durumunda seçin.

## <a name="personalization"></a>Kişiselleştirme

- **Masaüstü arka plan resmi URL'si (yalnızca Masaüstü)**: Windows masaüstü duvar kağıdı olarak kullanmak istediğiniz JPEG biçiminde bir resmin URL'sini girin. Kullanıcılar bu resmi değiştiremez.

## <a name="printer"></a>Yazıcı

- **Yazıcılar**: Eklenmiş olan yerel yazıcı listesi.
- **Varsayılan yazıcı**: Varsayılan yazıcıyı ayarlayın.
- **Yeni yazıcı eklemek için kullanıcı erişimi**: İzin verme veya yerel yazıcı kullanımına engelleme.

## <a name="privacy"></a>Gizlilik

- **Girişi kişiselleştirme**: Cortana, dikte veya Microsoft Store uygulamaları için bulut tabanlı konuşma hizmetlerinin kullanımına izin verme. Bu hizmetlere izin verirseniz Microsoft, hizmeti geliştirmek için sesli veri toplayabilir.
- **Eşleştirme ve gizlilik Kullanıcı onayı istemlerini otomatik kabul**: Windows otomatik olarak uygulama çalıştırırken iletileri eşleştirme ve gizlilik onay vermesini sağlar.
- **Kullanıcı etkinliklerini Yayımla**: **Blok** paylaşılan deneyimleri ve görev değiştiricide yakın zamanda kullanılan kaynakların bulunmasını önler.
- **Yalnızca yerel etkinlikler**: **Blok** paylaşılan deneyimleri ve görev değiştiricide yalnızca yerel etkinliği temel alan, yakın zamanda kullanılan kaynakların bulunmasını önler.

Cihazdaki tüm uygulamaların erişebileceği bilgileri yapılandırabilirsiniz. **Uygulama başına gizlilik özel durumları**'nı kullanarak uygulama başına özel durumlar tanımlayabilirsiniz.

### <a name="exceptions"></a>Özel durumlar

- **Hesap bilgileri**: Bu uygulamanın kullanıcı adına, resmine ve diğer kişi bilgilerine erişip erişemeyeceğini tanımlayın.
- **Arka plan uygulamaları**: Bu uygulamanın arka planda çalışıp çalışamayacağını tanımlayın.
- **Takvim**: Bu uygulamanın takvime erişip erişemeyeceğini tanımlayın.
- **Arama Geçmişi**: Bu uygulamanın çağrı geçmişime erişip erişemeyeceğini tanımlayın.
- **Kamera**: Bu uygulamanın kameraya erişip erişemeyeceğini tanımlayın.
- **Kişiler**: Bu uygulamanın kişilere erişip erişemeyeceğini tanımlayın.
- **e-posta**: Bu uygulamaya erişebilir ve e-posta Gönder olup olmadığını tanımlar.
- **Konum**: Bu uygulamanın konum bilgilerine erişip erişemeyeceğini tanımlayın.
- **Mesajlaşma**: Bu uygulama okuma veya metin veya MMS iletisi gönder tanımlayın.
- **Mikrofon**: Bu uygulamanın mikrofonu kullanıp kullanamayacağını tanımlayın.
- **Hareket**: Bu uygulamanın cihaz hareket bilgilerine erişip erişemeyeceğini tanımlayın.
- **Bildirimleri**: Bu uygulamanın bildirimlere erişip erişemeyeceğini tanımlayın.
- **Telefon**: Bu uygulamanın telefona erişip erişemeyeceğini tanımlayın.
- **Radyolara**: Bazı uygulamalar gönderin ve bu Radyoları açıp kapatması gerekir veri almak için Cihazınızı Radyoları (örneğin, Bluetooth) kullanın. Bu uygulamanın bu radyoları denetleyip denetleyemeyeceğini tanımlayın.
- **Görevleri**: Bu uygulamanın görevlerinize erişip erişemeyeceğini tanımlayın.
- **Güvenilen cihazlar**: Bu uygulamanın güvenilen cihazları kullanıp kullanamayacağını seçin. Güvenilen cihazlara donanım zaten bağlanmış olduğunuz veya cihazı ile birlikte gelen donanım olur. Örneğin, televizyonlar, Projektörler, vb. güvenilen cihazlar kullanır.
- **Geri bildirim ve tanılama**: Bu uygulamanın tanılama bilgilerine erişip varsa seçin.
- **Cihazlarla eşitle** - Bu uygulamanın bu PC, tablet veya telefonla açıkça eşleştirilmemiş kablosuz cihazlarla otomatik olarak bilgi paylaşma ve eşitleme işlemleri yapıp yapamayacağını tanımlayın.

## <a name="projection"></a>Projeksiyon

- **Kablosuz görüntü alıcılarından kullanıcı girişini**: Blok kullanıcı kablosuz ekran alıcılarından girişi.
- **Bu Bilgisayara yansıtma**: Diğer cihazların yansıtma için bilgisayarı bulma durdurur.
- **Eşleştirme için PIN iste**: Bir projeksiyon cihazına bağlanırken PIN gerektirir.

## <a name="reporting-and-telemetry"></a>Raporlama ve Telemetri

- **Kullanım verilerini paylaş**: Gönderilen Tanılama verileri düzeyini seçin. Seçenekleriniz şunlardır:
  - Güvenlik
  - Temel
  - Gelişmiş
  - Tam
- **Microsoft Edge tarama verilerini Microsoft 365 analytics'e gönderme**: Bu özelliği kullanmak için **kullanım verilerini paylaş** ayarlar **geliştirilmiş** veya **tam**. Hangi verilerin Microsoft Edge, yapılandırılmış bir ticari kimliği ile Kurumsal cihazlarda Microsoft 365 Analytics'e gönderir. Bu özellik denetler Seçenekleriniz şunlardır:
  - **Yapılandırılmamış**: İşletim sistemi varsayılan, tüm gözatma geçmişini gönderemeyebilir kullanır
  - **Yalnızca intranet veri gönderme**: Yöneticinin intranet veri geçmişini göndermek için
  - **Yalnızca İnternet'e veri göndermek**: Internet veri geçmişini göndermek yöneticinin sağlar
  - **İntranet ve İnternet'e veri göndermek**: İntranet ve internet veri geçmişini göndermek yöneticinin sağlar
- **Telemetri proxy sunucusu**: Tam etki alanı adı (FQDN) veya bağlı kullanıcı deneyimleri ve Telemetri istekleri, Güvenli Yuva Katmanı (SSL) bağlantısı kullanarak iletmek için bir proxy sunucusunun IP adresini girin. Bu ayarın biçimi *sunucu*:*bağlantı noktası* olur. Adlandırılmış proxy başarısız olursa veya bu ilke etkinleştirildiğinde girilen bir proxy yoksa bağlı kullanıcı deneyimleri ve Telemetri verileri gönderilen değil ve yerel cihazda kalır.

  Örnek biçimler:

  ```
  IPv4: 192.246.246.106:100
  IPv6: [2001:4898:4010:4013:95c1:a8b2:953c:c633]:100
  FQDN: www.contoso.com:345
  ```

## <a name="search"></a>Ara

- **Güvenli arama (yalnızca mobil)**: Cortana'nın yetişkinlere yönelik içeriği arama sonuçlarında nasıl filtreleyeceğini denetleyin. **Katı**, **Orta** değerlerini seçebilir ya da son kullanıcının kendi ayarlarını seçmesine izin verebilirsiniz.
- **Aramada web sonuçlarını görüntüle**: Engelleme veya web sonuçları, cihazda yapılan aramalarda görünmesine izin verme.

## <a name="start"></a>Başlat

- **Başlangıç menüsü düzeni**: Masaüstü cihazlarda Başlat menüsünü özelleştirmek için listelenen uygulamalar, sipariş dahil olmak üzere özelleştirmelerinizi ve daha fazlasını içeren bir XML dosyasını karşıya yükleyebilirsiniz. Kullanıcılar, girdiğiniz Başlat menüsü düzenini değiştiremez.
- **Başlat menüsünde Web siteleri için kutucuklar sabitleme**: Görüntüleri Masaüstü cihazları için Windows Başlat menüsündeki bağlantılar olarak gösterilen Microsoft Edge içeri aktarın.
- **Uygulamaları görev çubuğundan Kaldır**: Seçin **blok** kullanıcı uygulamaları Başlat menüsünden kaldırmasını durdurmak için.
- **Hızlı Kullanıcı Geçişi**: Seçin **blok** aynı anda kapatmadan oturum açmış kullanıcılar arasında geçiş yapma önlemek için.
- **En çok kullanılan uygulamalar**: Seçin **blok** gösteren Başlat menüsünde en çok kullanılan uygulamalardan gizlemek için. Bu ayrıca Ayarlar uygulamasında aynı ada sahip iki durumlu ayarı da devre dışı bırakır.
- **Uygulamalar'en son eklenen**: Seçin **blok** gösteren Başlangıç menüsündeki son eklenen uygulamaları Gizle için. Bu ayrıca Ayarlar uygulamasında aynı ada sahip iki durumlu ayarı da devre dışı bırakır.
- **Başlangıç ekranı modu**: Başlangıç ekranına nasıl gösterilen seçin. Bunu **Tam ekran** veya **Tam ekran değil** şeklinde belirleyebilirsiniz.
- **Son açılan öğeler bağlantı listeleri**: Seçin **blok** son atlama listelerini görev çubuğu ve Başlat menüsü üzerinde gösterilen gizlemek için. Bu ayrıca Ayarlar uygulamasında aynı ada sahip iki durumlu ayarı da devre dışı bırakır.
- **Uygulama listesi**: Ayarlar uygulamasında gösterilen nasıl seçin. Seçenekleriniz şunlardır: 
  - Daralt
  - Ayarlar uygulamasını daralt ve devre dışı bırak 
  - Ayarlar uygulamasını kaldırır ve devre dışı bırakır
- **Güç düğmesi**: Seçin **blok** gösteren Başlangıç menüsündeki güç düğmesinden gizlemek için.
- **Kullanıcı kutucuğunu**: Seçin **blok** gelen gösteren Başlangıç menüsündeki kullanıcı kutucuğunda gizlemek için.
  - **Kilit**: Seçin **blok** gizlemek için `Lock` gösteren Başlangıç menüsündeki kullanıcı kutucuğunda seçeneği.
  - **Oturumu Kapat**: Seçin **blok** gizlemek için `Sign out` gösteren Başlangıç menüsündeki kullanıcı kutucuğunda seçeneği.
- **Kapatma**: Seçin **blok** gizlemek için `Update and shut down` ve `Shut down` seçenekleri gösteren Başlangıç menüsündeki güç düğmesinde.
- **Uyku**: Seçin **blok** gizlemek için `Sleep` gösteren Başlangıç menüsündeki güç düğmesinde seçeneği.
- **Hazırda bekleme**: Seçin **blok** gizlemek için `Hibernate` gösteren Başlangıç menüsündeki güç düğmesinde seçeneği.
- **Hesap Değiştir**: Seçin **blok** gizlemek için `Switch account` kullanıcı gösteren gelen döşeme Başlat menüsünde.
- **Yeniden başlatma seçenekleri**:  Seçin **blok** gizlemek için `Update and restart` ve `Restart` seçenekleri gösteren Başlangıç menüsündeki güç düğmesinde.
- **Başlangıç menüsünde belgeler**: Gizleme veya Windows Başlat menüsünde Belgeler klasörünü gösterin.
- **Başlangıç menüsünde indirmeler**: Gizleyebilir veya Windows Başlat menüsünde indirilenler klasöründen gösterebilirsiniz.
- **Başlat menüsünde dosya Gezgini**: Gizleme veya Windows Başlat menüsünde dosya Gezgini uygulamasını gösterin.
- **Başlangıç menüsünde ev grubu**: Gizleme veya Windows Başlat menüsünde ev grubu klasörünü gösterin.
- **Başlangıç menüsünde müzik**: Gizleme veya Windows Başlat menüsünde müzik klasörünü gösterin.
- **Başlangıç menüsünde ağ**: Gizleme veya Windows Başlat menüsünde ağ klasörü gösterir.
- **Başlangıç menüsünde Kişisel klasörü**: Gizle veya Windows Başlat menüsünde Kişisel klasörü gösterir.
- **Başlangıç menüsünde resimler**: Gizleme veya Windows Başlat menüsünde Resimler klasörünü gösterin.
- **Başlangıç menüsünde Ayarlar**: Gizleme veya Windows Başlat menüsünde Ayarlar uygulamasını gösterin.
- **Başlangıç menüsünde videolar**: Gizleme veya Windows Başlat menüsünde videolar klasörünü gösterin.

## <a name="windows-defender-smart-screen"></a>Windows Defender Smart Screen

- **Microsoft Edge için SmartScreen**: Site ve dosya yüklemeleri erişmek için Microsoft Edge Smartscreen'i etkinleştirin.
- **Kötü niyetli site erişimi**: Kullanıcıların Windows Defender SmartScreen Filtresi uyarılarını yoksaymasını ve siteye gitmesini engelleyin.
- **Doğrulanmamış dosyayı indirme**: Kullanıcıların Windows Defender SmartScreen Filtresi uyarılarını yoksaymasını ve doğrulanmamış dosyaları indirmesini engelleyin.

## <a name="windows-spotlight"></a>Windows Spot

- **Windows spot**: Windows 10 cihazlarda tüm Windows spot işlevselliğini engellemek için bu ayarı kullanın. Bu ayarı engellerseniz aşağıdaki ayarlar kullanılabilir değildir:
  - **Kilit ekranında Windows spot**: Windows spot cihaz kilitleme ekranında bilgi görüntülemesini durdurun.
  - **Windows spot'ta üçüncü taraf önerileri**: Windows spot, Microsoft tarafından yayımlanmayan içeriği önermesini gelen durdurun.
  - **Tüketici özellikleri**: Başlat menüsü önerileri ve üyelik bildirimleri, gibi özellikleri engellemenizi sağlar.
  - **Windows ipuçları**: Windows içinde görüntülenmesini açılır ipuçlarını engellemenize olanak sağlar.
  - **İşlem merkezinde Windows spot**: Blok Windows spot önerilerinin, yeni uygulama veya Windows İşlem Merkezi'nde görünmesini güvenlik içeriği gibi.
  - **Windows spot kişiselleştirme**: Durakları Windows Spot'un sonuçları bir cihazın kullanımına göre kişiselleştirilmesi için.
  - **Windows Karşılama deneyimi**: Yeni veya güncelleştirilmiş özellikleri kullanıcı bilgilerini gösteren Windows Karşılama deneyimi engelleyin.

## <a name="windows-defender-antivirus"></a>Windows Defender Virüsten Koruma

- **Gerçek zamanlı izleme**: Kötü amaçlı yazılım, casus yazılım ve istenmeyen diğer yazılımlar için gerçek zamanlı taramaya izin verir.
- **Davranış izlemeyi**: Defender’ın cihazlarda bilinen şüpheli etkinlik düzenlerini denetlemesine olanak sağlar.
- **Ağ denetleme Sistemi'ni (NIS)**: NIS, cihazları ağ tabanlı saldırılara karşı korumaya yardımcı olur. Kötü amaçlı trafiği algılamaya ve engellemeye yardımcı olmak için Microsoft Endpoint Protection Center’dan bilinen açıkların imzalarını kullanır.
- **Tüm indirmeleri tara**: Defender’ın İnternet’ten indirilen tüm dosyaları tarayıp taramayacağını denetler.
- **Microsoft web tarayıcılarında yüklenen betikleri tarama**: Defender’ın Internet Explorer’da kullanılan betikleri taramasına olanak sağlar.
- **Defender'a son kullanıcı erişimi**: Windows Defender kullanıcı arabiriminin son kullanıcılardan gizlenip gizlenmediğini denetler. Bu ayar değiştirildiğinde, kullanıcının bilgisayarının bir sonraki yeniden başlatılmasında devreye girer.
- **İmza güncelleştirme aralığı (saat)**: Defender'ın yeni imza dosyalarını zaman aralığı belirtin.
- **Dosya ve program etkinliğini İzle**: Defender’ın cihazlarda dosya ve program etkinliğini izlemesine izin verir.
- **Karantinaya alınmış kötü amaçlı yazılım silinmeden önce gün**: Defender’ın çözümlenen kötü amaçlı yazılımı belirttiğiniz sayıda gün boyunca izlemeye devam etmesine olanak sağlar; böylece daha önce etkilenmiş olan cihazları el ile denetleyebilirsiniz. Gün sayısını ayarlarsanız **0**, kötü amaçlı yazılım karantina klasöründe kalır ve otomatik olarak kaldırılmaz.
- **Bir tarama sırasında CPU kullanım sınırı**: Taramaların kullanmasına izin verilecek CPU miktarını sınırlandırmanıza (**1** ile **100** arasında) olanak sağlar.
- **Arşiv dosyalarını tara**: Defender’ın Zip veya Cab dosyaları gibi arşivlenmiş dosyaları taramasına izin verir.
- **Gelen posta iletilerini tarama**: Defender’ın cihaza gelen e-posta iletilerini taramasına izin verir.
- **Tam tarama sırasında Çıkarılabilir sürücüleri tara**: Defender’ın USB çubukları gibi çıkarılabilir sürücüleri taramasına olanak sağlar.
- **Tam tarama sırasında eşlenmiş ağ sürücülerini tarama**: Defender’ın eşlenen ağ sürücüsündeki dosyaları taramasına olanak sağlar.
  Sürücüdeki dosyalar salt okunur ise, Defender bunların içinde bulduğu kötü amaçlı yazılım kaldırılamıyor.
- **Ağ klasörlerinden açılan dosyaları tara**: (Örneğin UNC yolundan erişilen dosyalar) paylaşılan ağ sürücülerindeki dosyaları taramasına olanak sağlar. Sürücüdeki dosyalar salt okunur ise, Defender bunların içinde bulduğu kötü amaçlı yazılım kaldırılamıyor.
- **Bulut koruması**: Microsoft Etkin Koruma Hizmeti’nin yönettiğiniz cihazlardan kötü amaçlı yazılım etkinliğiyle ilgili bilgi almasına izin verir veya bunu engeller. Bu bilgi gelecekte hizmeti geliştirmek için kullanılır.
- **Örnek göndermeden önce kullanıcılara sor**: Kötü amaçlı dosyaları olup olmadığını daha fazla çözümlenmesi gerekebilecek denetimleri otomatik olarak Microsoft'a gönderilir.
- **Günlük hızlı tarama gerçekleştirilecek saat**: Her gün seçtiğiniz saatte gerçekleştirilecek olan bir hızlı tarama zamanlamanıza olanak sağlar.
- **Gerçekleştirilecek sistem taraması türü**: Sistem taraması zamanladığınızda çalıştıran tarama düzeyini girin.
- **İstenmeyebilecek uygulamaları Algıla**: Windows algıladığında uygulamalardan olası istenmeyen koruma düzeyini seçin:
  - **Engelle**
  - **Denetim** istenmeyebilecek uygulamalar hakkında daha fazla bilgi için bkz. [Algıla ve engelle olası uygulamalar istenmeyen](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus).
- **Algılanan kötü amaçlı yazılım tehditlerine eylemleri**: Defender'ın her tehdit düzeyinde istediğiniz eylemleri algılar (düşük, Orta, yüksek ve ciddi) seçmek için bu seçeneği kullanın. Seçenekleriniz şunlardır:
  - **Temizle**
  - **Karantina**
  - **Kaldır**
  - **İzin ver**
  - **Kullanıcı tanımlı**
  - **Engelle**

### <a name="windows-defender-antivirus-exclusions"></a>Windows Defender Virüsten Koruma Dışlamaları

- **Dosyalar ve taramaların ve gerçek zamanlı korumanın dışında tutulacak klasörler**: Dışlama listesinde **C:\Yol** veya **%ProgramFiles%\Yol\dosyaadı.exe** gibi bir veya birden çok dosya ve klasör ekler. Bu dosya ve klasörler gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.
- **Dosya uzantıları taramaların ve gerçek zamanlı korumanın dışında tutulacak**: Dışlama listesine jpg veya **txt** gibi bir veya birden çok dosya uzantısı ekleyin. Bu uzantıya sahip dosyaların hiçbiri gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.
- **Taramaların ve gerçek zamanlı korumanın dışında bırakılacak işlemler**: Dışlama listesine .exe, **.com** veya **.scr** türünde bir veya birden çok işlem ekleyin. Bu işlemler gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.

## <a name="next-steps"></a>Sonraki adımlar

Her bir ayara dair ek teknik ayrıntılar ve hangi Windows sürümlerinin desteklendiği hakkında bilgi için bkz. [Windows 10 İlke CSP Başvurusu](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)
