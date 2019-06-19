---
title: Microsoft Intune - Azure’da Windows 10 cihaz kısıtlama ayarları | Microsoft Docs
description: Tüm ayarları ve Windows 10 ve üzeri cihazlarda cihaz kısıtlamaları oluşturmak için bunlara ilişkin açıklamaların listesini bakın. Bu ayarları yapılandırma profilinde de ekran görüntüleri, parola gereksinimleri, bilgi noktası ayarları, depolama, Microsoft Edge tarayıcısı, Windows defender uygulama denetimi, bulutta, Başlat menüsünde ve diğer Microsoft Intune erişmek için kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/18/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9af61c89b90a7f31654cd43a3cfc457b27e9700f
ms.sourcegitcommit: 86aa5fefcba1e71841696b1a5e3ca5bffb1a9528
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/18/2019
ms.locfileid: "67234979"
---
# <a name="windows-10-and-newer-device-settings-to-allow-or-restrict-features-using-intune"></a>İzin verme veya kısıtlamanıza Intune kullanarak Windows 10 (ve üzeri) cihaz ayarları

Bu makalede, listeler ve Windows 10 ve daha yeni cihazlarda denetleyebileceğiniz farklı ayarlar açıklanır. Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, bu ayarları kullanın izin ver veya özellikleri devre dışı bırakabilir, parola kuralları ayarla, kilit ekranı özelleştirmek için Windows Defender'ı ve daha fazlasını kullanın.

Bu ayarlar, ıntune'da cihaz yapılandırma profili eklenir ve ardından atanan veya Windows 10 cihazlarına dağıtılabilir.

> [!Note]
> Tüm seçenekleri, tüm Windows sürümlerinde kullanılabilir. Desteklenen sürümlerinden görmek için başvurmak [ilke CSP'ler](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) (başka bir Microsoft web sitesini açar).

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz yapılandırma profili oluşturma](device-restrictions-configure.md#create-the-profile).

## <a name="app-store"></a>Uygulama Mağazası

Bu ayarları kullanın [ApplicationManagement ilke CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement), desteklenen Windows sürümleri de listelenir.

- **App Store'da** (yalnızca mobil): **Yapılandırılmamış** (varsayılan), son kullanıcıların mobil cihazlarda uygulama mağazasına erişim sağlar. **Blok** kullanarak uygulama mağazası engeller.
- **Mağaza uygulamalarını otomatik güncelleştir**: **Yapılandırılmamış** (varsayılan) otomatik olarak güncelleştirilmesi için Microsoft Store yüklenen uygulamalar sağlar. **Blok** güncelleştirmeleri otomatik olarak yüklenmesini engeller.
- **Güvenilen uygulama yüklemesi**: Microsoft Store uygulamaları, dışarıdan yükleme olarak da bilinen yüklenip yüklenemeyeceğini seçin. Dışarıdan yükleme yüklemeden ve ardından çalışan veya Microsoft Store tarafından onaylı olmayan bir uygulamayı test etme. Örneğin, bir uygulama, şirketiniz için gerçekleştirilir. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): İşletim sistemi varsayılan kullanır.
  - **Blok**: Dışarıdan yükleme engeller. Microsoft Store olmayan uygulamalar yüklenemez.
  - **İzin ver**: Dışarıdan yükleme sağlar. Microsoft Store olmayan uygulamalar yüklenebilir.
- **Geliştirici kilidini açma**: Dışarıdan yüklenen uygulamaların son kullanıcılar tarafından değiştirilmesine izin verme gibi Windows Geliştirici ayarlarına izin verin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): İşletim sistemi varsayılan kullanır.
  - **Blok**: Geliştirici modu ve dışarıdan yükleme uygulamaları engeller.
  - **İzin ver**: Geliştirici modu ve dışarıdan yükleme uygulamaları sağlar.

  [Cihazınızı geliştirme için etkinleştirme](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development) bu özellik hakkında daha fazla bilgi bulunur.

- **Paylaşılan kullanıcı uygulaması verileri**: Seçin **izin** uygulama verilerini aynı cihazda ve bu uygulamanın diğer örnekleri ile farklı kullanıcılar arasında paylaşmak için. **Yapılandırılmamış** (varsayılan) engeller paylaşımı verileri diğer kullanıcıları ve aynı uygulamanın diğer örnekleri.
- **Yalnızca özel mağaza kullan**: **İzin** yalnızca özel mağazadan indirilen ve perakende Kataloğu dahil olmak üzere ortak depodaki yüklenmemiş uygulamaların sağlar. **Yapılandırılmamış** (varsayılan), uygulamaların özel bir depolama ve bir ortak mağaza yüklenmesine izin verir.
- **Mağazadan indirilen uygulamaları başlatma Store**: **Blok** cihaza önceden yüklenmiş veya Microsoft Store yüklenen tüm uygulamaları devre dışı bırakır. **Yapılandırılmamış** (varsayılan) açmak bu uygulamaları tanır.
- **Uygulama verilerini sistem birimine Yükle**: **Blok** uygulamaların cihazın sistem birimine veri depolama durdurur. **Yapılandırılmamış** (varsayılan), sistem diski biriminde verileri depolamak, uygulamaların verir.
- **Uygulamaları sistem sürücüsüne Yükle**: **Blok** uygulamaların cihazın sistem sürücüsünde yüklenmesini de önler. **Yapılandırılmamış** (varsayılan), uygulamaların sistem sürücüsüne yükle izin verir.
- **Oyun DVR** (yalnızca Masaüstü): **Blok** Windows kaydı ve yayın oyun devre dışı bırakır. **Yapılandırılmamış** (varsayılan), kayıt ve oyun yayın sağlar.
- **Uygulamaları yalnızca mağazadan**: **Gerekli** yalnızca Windows App Store uygulamaları yüklemek için son kullanıcıların zorlar. **Yapılandırılmamış** son kullanıcıların Windows App Store dışındaki yerlerden uygulama yükleyip olanak tanır.
- **Güncelleştirme Hatası uygulamalarını yeniden başlatmaya zorla**: Uygulama kullanılırken, güncelleştirilmeyebilir. Bir yeniden başlatmaya zorlamak için bu ayarı kullanın. **Yapılandırılmamış** (varsayılan), uygulamaları yeniden başlatmak için zorlama değil. **Gerekli** yöneticilerin belirli bir tarih ve saat veya yinelenen bir zamanlamaya göre yeniden başlatmaya zorla olanak sağlar. Ayarlandığında **gerektiren**, ayrıca girin:

  - **Başlangıç tarihi/saati**: Uygulamaları yeniden başlatmak için belirli bir tarih ve saat seçin.
  - **Yinelenme**: Günlük, haftalık veya aylık yeniden başlatın.

  [ApplicationManagement/ScheduleForceRestartForUpdateFailures CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)

- **Kullanıcı denetime yüklemeleri**: Ayarlandığında **yapılandırılmadı** (varsayılan), Windows Installer önlemek kullanıcılar dosyaları yüklemek için dizin girerek gibi sistem yöneticileri için genellikle ayrılmış yükleme seçeneklerini değiştirmesini. **Blok** bu yükleme seçeneklerini değiştirmek kullanıcıların sağlar ve Windows Installer güvenlik özelliklerinden bazıları atlanır.

  [ApplicationManagement/MSIAllowUserControlOverInstall CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-msiallowusercontroloverinstall)

- **Yükseltilmiş ayrıcalıklara sahip uygulamaları yüklemek**: Ayarlandığında **yapılandırılmadı** (varsayılan), sistem uygular geçerli kullanıcının izinlerini bir Sistem Yöneticisi dağıtma veya teklif değil programlar yüklendiğinde. **Blok** Windows Installer'ın bir program yüklerken yükseltilmiş izinler kullanmanız yönlendirir. Tüm Programlar'ın bu ayrıcalıkların genişletilir.

  [ApplicationManagement/MSIAlwaysInstallWithElevatedPrivileges CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-msialwaysinstallwithelevatedprivileges)

- **Başlangıç uygulamaları**: Cihaza bir kullanıcı oturum açtıktan sonra açmak için uygulamaların bir listesini girin. Noktalı virgülle ayrılmış liste, paket aile adı (PFN) Windows uygulamalarının kullandığınızdan emin olun. Bu ilkenin çalışması için bir başlangıç görevi Windows uygulamaları bildiriminde kullanmanız gerekir.

  [ApplicationManagement/LaunchAppAfterLogOn CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-launchappafterlogon)

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="cellular-and-connectivity"></a>Hücresel ve Bağlantı

Bu ayarları kullanın [bağlantı İlkesi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity) ve [Wi-Fi İlkesi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi) CSP'ler, desteklenen Windows sürümleri de listeleyin.

- [Wi-Fi İlkesi CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi)

- **Hücresel veri kanalı**: Son kullanıcıların bir hücresel ağa bağlıyken Web'e gözatma gibi verileri kullanıp kullanamayacağını seçin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Hücresel veri kanalına izin verebileceği işletim sistemi varsayılan kullanır. Son kullanıcıların kapatabilirsiniz.
  - **Blok**: Hücresel veri kanalına izin vermez. Son kullanıcıların açamaz.
  - **İzin ver (düzenlenemez)** : Hücresel veri kanalına izin verir. Son kullanıcılar, devre dışı bırakamazlar.

- **Veri dolaşımı**: **Blok** Dolaşım cihazda hücresel veri engeller. **Yapılandırılmamış** (varsayılan), verilere erişirken ağlar arasında dolaşıma izin verir.
- **Hücresel ağ üzerinden VPN**: **Blok** cihazın hücresel ağa bağlandığında VPN bağlantılarına erişmesini engeller. **Yapılandırılmamış** (varsayılan), VPN, hücresel şebeke de dahil olmak üzere herhangi bir bağlantı kullanmaya izin verir.
- **Hücresel ağ üzerinden VPN dolaşımı**: **Blok** cihazın bir cep telefonu şebekesinde dolaşımı sırasında VPN bağlantılarına erişmesini durdurur. **Yapılandırılmamış** (varsayılan) dolaşımı sırasında VPN bağlantılarına izin verir.
- **Bağlı cihazlar hizmetine**: **Blok** bağlı cihazlar Platformu (CDP) bileşenine devre dışı bırakır. CDP, uzaktan uygulama başlatma, uzak Mesajlaşma, uzaktan uygulama oturumlarının ve diğer cihazlar arası deneyimler desteklemek için bulma ve diğer cihazlar (aracılığıyla, Bluetooth/LAN veya Bulut) bağlantısı sağlar. **Yapılandırılmamış** (varsayılan), bulma ve Bluetooth diğer cihazlara bağlanmayı etkinleştiren bağlı cihazlar hizmetine izin verir.
- **NFC**: **Blok** alan iletişimi (NFC) özelliklerini engeller. **Yapılandırılmamış** (varsayılan) etkinleştirmek ve cihazda NFC özellikleri yapılandırmak kullanıcılara izin verir.
- **Wi-Fi**: **Blok** kullanıcılardan ve etkinleştirme, yapılandırma ve cihazda Wi-Fi bağlantıları kullanarak engeller. **Yapılandırılmamış** (varsayılan), Wi-Fi bağlantılarını sağlar.
- **Wi-Fi etkin noktalarına otomatik bağlanma**: **Blok** cihazları otomatik olarak Wi-Fi etkin noktalarına bağlanmasını engeller. **Yapılandırılmamış** (varsayılan) ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmasına ve tüm hüküm ve koşullar bağlantı için otomatik olarak kabul cihazları olanak tanır.
- **Elle Wi-Fi yapılandırmasına**: **Blok** cihazların MDM sunucusu yüklü ağ dışında Wi-Fi bağlanmasını engeller. **Yapılandırılmamış** eklemek ve kendi Wi-Fi bağlantıları ağ Ssıd'leri yapılandırmak son kullanıcıların (varsayılan) sağlar.
- **Wi-Fi tarama aralığı**: Ne sıklıkta girin cihazlar için Wi-Fi ağlarını tarama. Bir değeri 1 (en sık rastlanan) 500 için (en az) girin. Varsayılan değer `0` (sıfır).

### <a name="bluetooth"></a>Bluetooth

Bu ayarları kullanın [Bluetooth İlkesi CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth); desteklenen Windows sürümleri de listelenir.

- **Bluetooth**: **Blok** Bluetooth etkinleştirmesini kullanıcılar önler. **Yapılandırılmamış** (varsayılan) cihazda Bluetooth izin verir.
- **Bluetooth bulunabilirlik**: **Blok** cihazın diğer Bluetooth özellikli cihazlar tarafından bulunabilir olmasını önler. **Yapılandırılmamış** (varsayılan), cihazı bulmak için bir kulaklık gibi diğer Bluetooth özellikli cihazlar izin verir.
- **Bluetooth önceden eşleştirme**: **Blok** belirli Bluetooth cihazlarını bir konak cihazla otomatik olarak eşleştirin engeller. **Yapılandırılmamış** eşleştirme konak cihazla otomatik (varsayılan) sağlar.
- **Bluetooth reklamlarına**: **Blok** cihazın Bluetooth tanıtımları göndermesini engeller. **Yapılandırılmamış** (varsayılan), cihazın Bluetooth tanıtımları göndermek izin verir.
- **Bluetooth'a izin verilen hizmetler**: **Ekleme** listesini izin verilen Bluetooth hizmetleri ve profillerinin onaltılık dizeler olarak gibi `{782AFCFC-7CAA-436C-8BF0-78CD0FFBD4AF}`.

  [ServicesAllowedList Kullanım Kılavuzu](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#servicesallowedlist-usage-guide) hizmet listesi hakkında daha fazla bilgi içeriyor.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="cloud-and-storage"></a>Bulut ve Depolama

Bu ayarları kullanın [ilke CSP hesapları](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-accounts); desteklenen Windows sürümleri de listelenir.

- **Microsoft hesabı**: **Blok** son kullanıcılar Microsoft hesabı'yi aygıtla ilişkilendirme engeller. **Yapılandırılmamış** (varsayılan), ekleme ve bir Microsoft hesabı kullanarak sağlar.
- **Microsoft olmayan hesaplar**: **Blok** son kullanıcılar kullanıcı arabirimini kullanarak Microsoft olmayan hesaplar eklemesini önler. **Yapılandırılmamış** (varsayılan), kullanıcıların bir Microsoft hesabı ile ilişkili olmayan e-posta hesapları eklemesine olanak tanır.
- **Microsoft hesabı için ayar eşitlemesi**: **Yapılandırılmamış** (varsayılan), cihaz ve uygulama ayarlarının cihazlar arasında eşitlenmesine izin bir Microsoft hesabı ile ilişkili izin verir. **Blok** bu eşitlemeyi engeller.
- **Microsoft Account oturum açma Yardımcısı**: Ayarlandığında **yapılandırılmadı** (varsayılan), son kullanıcıların başlatabilir ve durdurabilirsiniz **Microsoft hesabı oturum açma Yardımcısı'nı** (wlidsvc) hizmeti. Bu işletim sistemi hizmet Microsoft hesabında oturum açmalarını sağlar. **Devre dışı** son kullanıcılar Microsoft oturum açma Yardımcısı hizmetini (wlidsvc) denetlemesini engeller.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="cloud-printer"></a>Bulut Yazıcı

Bu ayarları kullanın [EnterpriseCloudPrint ilke CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-enterprisecloudprint); desteklenen Windows sürümleri de listelenir.

- **Yazıcı bulma URL'si**: Bulut yazıcılarını bulmak için URL'yi girin. Örneğin, şunu girin: `https://cloudprinterdiscovery.contoso.com`.
- **Yazıcı erişim yetkilisi URL'si**: OAuth belirteçlerini almak için kimlik doğrulama uç noktası URL'sini girin. Örneğin, şunu girin: `https://azuretenant.contoso.com/adfs`.
- **Azure yerel istemci uygulama GUID'si**: Oauthauthority'den OAuth belirteçlerini almak için izin verilen bir istemci uygulama GUID'si girin. Örneğin, şunu girin: `E1CF1107-FF90-4228-93BF-26052DD2C714`.
- **Yazdırma hizmeti kaynak URI'si**: Azure portalında yapılandırılmış yazdırma hizmetinin OAuth kaynak URI'si girin. Örneğin, şunu girin: `http://MicrosoftEnterpriseCloudPrint/CloudPrint`.
- **Sorgulanacak en fazla yazıcı**: Sorgulanacak istediğiniz yazıcılar maksimum sayısını girin. Varsayılan değer `20` şeklindedir.
- **Yazıcı bulma hizmeti kaynak URI'si**: Yazıcı bulma için OAuth kaynak URI'si girin Azure Portalı'nda yapılandırılmış hizmet. Örneğin, şunu girin: `http://MopriaDiscoveryService/CloudPrint`.

> [!TIP]
> Sonra Kurulum bir [Windows Server karma bulut yazdırma](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-overview), bu ayarları yapılandırın ve ardından Windows cihazlarınıza dağıtın.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="control-panel-and-settings"></a>Denetim Masası ve Ayarlar

- **Ayarlar uygulamasında**: **Blok** son kullanıcıların Windows ayarlar uygulamasına erişimi engeller. **Yapılandırılmamış** (varsayılan), cihazdaki ayarlar uygulamasını açmasına izin verir.
  - **Sistem**: **Blok** ayarlar uygulamasının sistem alanına erişimini engeller. **Yapılandırılmamış** (varsayılan) erişim sağlar.
    - **Güç ve uyku ayarlarının değiştirilmesi** (yalnızca Masaüstü): **Blok** son kullanıcılar cihazın güç ve uyku ayarlarını değiştirmesini engeller. **Yapılandırılmamış** (varsayılan), kullanıcıların ve uyku ayarlarını değiştirmesini güç sağlar.
  - **cihazları**: **Blok** cihazdaki ayarlar uygulamasının cihazlar alanına erişimini engeller. **Yapılandırılmamış** (varsayılan) erişim sağlar.
  - **Ağ ve Internet**: **Blok** cihazdaki ayarlar uygulamasının ağ ve Internet alanına erişimini engeller. **Yapılandırılmamış** (varsayılan) erişim sağlar.
  - **Kişiselleştirme**: **Blok** cihazdaki ayarlar uygulamasının kişiselleştirme alanına erişimini engeller. **Yapılandırılmamış** (varsayılan) erişim sağlar.
  - **Uygulamalar**: **Blok** ayarlar uygulamasının cihazda uygulama alanına erişimi engeller. **Yapılandırılmamış** (varsayılan) erişim sağlar.
  - **Hesapları**: **Blok** ayarlar uygulamasının cihazda alanına erişimi engeller. **Yapılandırılmamış** (varsayılan) erişim sağlar.
  - **Saat ve dil**: **Blok** cihazdaki ayarlar uygulamasının saat ve dil alanına erişimini engeller. **Yapılandırılmamış** (varsayılan) erişim sağlar.
    - **Sistem saatinin değiştirilmesi**: **Blok** son kullanıcıların cihazdaki tarih ve saat ayarlarını değiştirmesini engeller. **Yapılandırılmamış** kullanıcıların bu ayarlarını değiştirmesine olanak sağlar.
    - **Bölge ayarlarının değiştirilmesi** (yalnızca Masaüstü): **Blok** son kullanıcılar cihazın bölge ayarlarını değiştirmesini engeller. **Yapılandırılmamış** kullanıcıların bu ayarlarını değiştirmesine olanak sağlar.
    - **Dil ayarlarının değiştirilmesi (yalnızca Masaüstü)** : **Blok** son kullanıcılar cihazın dil ayarlarını değiştirmesini engeller. **Yapılandırılmamış** kullanıcıların bu ayarlarını değiştirmesine olanak sağlar.

      [Ayarları İlkesi CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings)

  - **Oyun**: **Blok** ayarlar uygulamasının cihazda Oyun alanına erişimi engeller. **Yapılandırılmamış** (varsayılan) erişim sağlar.
  - **Erişim Kolaylığı**: **Blok** cihazdaki ayarlar uygulamasının Erişim Kolaylığı alanına erişimini engeller. **Yapılandırılmamış** (varsayılan) erişim sağlar.
  - **Gizlilik**: **Blok** cihazdaki ayarlar uygulamasının gizlilik alanına erişimini engeller. **Yapılandırılmamış** (varsayılan) erişim sağlar.
  - **Güncelleştirme ve güvenlik**: **Blok** cihazdaki ayarlar uygulamasında güncelleştirme ve güvenlik alanına erişimini engeller. **Yapılandırılmamış** (varsayılan) erişim sağlar.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="display"></a>Görüntüle

Bu ayarları kullanın [ilke CSP görüntüleme](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-display); desteklenen Windows sürümleri de listelenir.

GDI DPI ölçeklendirme, İzleyici DPI kullanan DPI olmayan uygulamalar sağlar.

- **Uygulamalar için GDI ölçeklendirmeyi Aç**: **Ekleme** GDI DPI ölçeklendirme açık istediğiniz eski uygulamaları. Örneğin `filename.exe` veya `%ProgramFiles%\Path\Filename.exe` girin.

  GDI DPI ölçeklendirme, listedeki tüm eski uygulamalar için etkinleştirilir.

- **Uygulamalar için GDI ölçeklendirmeyi Kapat**: **Ekleme** GDI DPI ölçeklendirme kapalı istediğiniz eski uygulamaları. Örneğin `filename.exe` veya `%ProgramFiles%\Path\Filename.exe` girin.

  GDI DPI ölçeklendirme, listedeki tüm eski uygulamalar için kapatılır.

Ayrıca **alma** uygulamaların listesini içeren bir .csv dosyası.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="general"></a>Genel

Bu ayarları kullanın [ilke CSP deneyimi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience); desteklenen Windows sürümleri de listelenir. 

- **Ekran Yakalama** (yalnızca mobil): **Blok** son kullanıcıların cihazda ekran görüntüleri alınmasını engelleyen. **Yapılandırılmamış** (varsayılan), bu özelliği sağlar.
- **Kopyala ve Yapıştır (yalnızca mobil)** : **Blok** son kullanıcılar, Kopyala ve Yapıştır cihazda uygulamalar arasında kullanmasını önler. **Yapılandırılmamış** (varsayılan), bu özelliği sağlar.
- **Elle kayıt kaldırmaya**: **Blok** son kullanıcıların cihazda çalışma alanı Denetim Masası'nı kullanarak kullanıcının iş yeri hesabını silmenizi önler. **Yapılandırılmamış** (varsayılan), bu özelliği sağlar.

  Bu ilke ayarı, Azure AD'ye katılmış bilgisayardır ve otomatik kayıt etkinse geçerli değildir.

- **Elle kök sertifika yüklemesi** (yalnızca mobil): **Blok** son kullanıcıların el ile kök sertifikaları ve Ara CAP sertifikaları yüklemesini engeller. **Yapılandırılmamış** (varsayılan), bu özelliği sağlar.
- **Kamera**: **Blok** son kullanıcıların cihazda kamerayı kullanmasını önler. **Yapılandırılmamış** (varsayılan), bu özelliği sağlar.
- **OneDrive dosya eşitlemesini**: **Blok** son kullanıcıların CİHAZDAN dosyaları Onedrive'a eşitlemesini engeller. **Yapılandırılmamış** (varsayılan), bu özelliği sağlar.
- **Çıkarılabilir Depolama Birimi**: **Blok** son kullanıcıların cihazda SD kartı gibi dış depolama cihazlarının kullanmasını önler. **Yapılandırılmamış** (varsayılan), bu özelliği sağlar.
- **Coğrafi konum**: **Blok** son kullanıcılar cihazın konum hizmetlerini kapatmasını engeller. **Yapılandırılmamış** (varsayılan), bu özelliği sağlar.
- **Internet paylaşımı**: **Blok** cihazda Internet bağlantısı paylaşımının engeller. **Yapılandırılmamış** (varsayılan), bu özelliği sağlar.
- **Telefon sıfırlama**: **Blok** silinmesi veya cihazda Fabrika sıfırlaması yapmak son kullanıcıların engeller. **Yapılandırılmamış** (varsayılan), bu özelliği sağlar.
- **USB bağlantısı**: **Blok** cihazın USB bağlantısı aracılığıyla dış depolama cihazlarına erişimi engeller. **Yapılandırılmamış** (varsayılan), bu özelliği sağlar. USB ile şarj etme, bu ayardan etkilenmez.
- **Hırsızlık önleme modu** (yalnızca mobil): **Blok** son kullanıcıların cihazda hırsızlık önleme modu tercihini seçmesini engeller. **Yapılandırılmamış** (varsayılan), bu özelliği sağlar.
- **Cortana**: **Blok** cihazda Cortana sesli Yardımcısını devre dışı bırakın. Cortana'yı devre dışı olduğunda, kullanıcılar hala cihazda öğelerini bulmak için arama yapabilirsiniz. **Yapılandırılmamış** (varsayılan), Cortana izin verir.
- **Ses kaydı** (yalnızca mobil): **Blok** son kullanıcıların cihazda cihaz ses kaydedicisinin kullanmasını önler. **Yapılandırılmamış** (varsayılan) ses kaydını uygulamalar için izin verir.
- **Cihaz adı değişikliğine** (yalnızca mobil): **Blok** son kullanıcıların cihaz adını değiştirmesini engeller. **Yapılandırılmamış** (varsayılan), bu özelliği sağlar.
- **Sağlama paketleri ekleme**: **Blok** cihazda sağlama paketleri yükleyen çalışma zamanı yapılandırma aracısını engeller. **Yapılandırılmamış** (varsayılan), bu özelliği sağlar.
- **Sağlama paketlerini kaldırma**: **Blok** CİHAZDAN sağlama paketlerini kaldıran çalışma zamanı yapılandırma aracısını engeller. **Yapılandırılmamış** (varsayılan), bu özelliği sağlar.
- **Cihaz bulma**: **Blok** cihazın diğer cihazlar tarafından bulunmasını önler. **Yapılandırılmamış** (varsayılan), bu özelliği sağlar.
- **Görev değiştirici** (yalnızca mobil): **Blok** cihazda görev değiştirmeyi engeller. **Yapılandırılmamış** (varsayılan), bu özelliği sağlar.
- **SIM kart hatası iletişim kutusu** (yalnızca mobil): **Blok** hata iletilerinin cihaza SIM kart algılanırsa gösteriliyor. **Yapılandırılmamış** (varsayılan), hata iletileri gösterir.
- **Ink çalışma alanı**: Varsa ve kullanıcı erişimi nasıl mürekkep çalışma alanı seçin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Mürekkep çalışma alanı ve kullanıcı açar kilit ekranının üstünde kullanmasına izin.
  - **Kilit ekranında devre dışı**: Mürekkep çalışma alanı etkindir ve özelliği açıktır. Ancak, kullanıcının kilit ekranının üstünde erişemez.
  - **Devre dışı**: Mürekkep çalışma alanı erişimi devre dışı bırakıldı. Bu özellik devre dışıdır.

  [CSP WindowsInkWorkspace İlkesi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace)

- **Otomatik yeniden dağıtım**: Seçin **izin** yönetici haklarına sahip kullanıcılar, tüm kullanıcı verilerini ve ayarlarını kullanarak silebilirsiniz. Bu nedenle **CTRL + Win + R** cihaz kilit ekranında. Cihaz otomatik olarak yeniden yapılandırılacak ve yönetime yeniden kaydettirilebilmesi. **Yapılandırılmadı** (varsayılan) ayarı bu özelliği engeller.
- **Kullanıcıların cihaz kurulumu sırasında ağa bağlanmasını gerektiren**: Seçin **gerektiren** cihazın Windows Kurulumu sırasında geçmiş ağ sayfasına geçmeden önce bir ağa bağlanacak şekilde. **Yapılandırılmamış** (varsayılan), bir ağa bağlı değilse olsa bile ağ sayfasını geçerek gitmelerini sağlar.

  Ayarı, cihaz sonlandırılana veya sıfırlama sonraki açışınızda etkin hale gelir. Diğer Intune yapılandırması gibi cihaz kayıtlı ve yapılandırma ayarlarını almak için Intune tarafından yönetilir. Ancak bir kez kaydedilir ve ilkeleri alma, sonra cihaz Fabrika ayarı sonraki Windows Kurulumu sırasında uygular.

- **Doğrudan bellek erişimi**: **Blok** Windows kullanıcının oturum açtığı kadar sık erişimli takılabilir PCI aşağı akış için tüm bağlantı doğrudan bellek erişimi (DMA) engeller. **Etkin** (varsayılan), hatta bir kullanıcı oturum açmadı olduğunda DMA, erişim sağlar.

  CSP: [DataProtection/AllowDirectMemoryAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection#dataprotection-allowdirectmemoryaccess)

- **Son işlem Görev Yöneticisi'nden**: Bu ayar, yönetici olmayanların son görevler için Görev Yöneticisi'ni kullanıp kullanamayacağını belirler. **Blok** Görev Yöneticisi'ni kullanarak bir işlem veya cihazdaki görev sona erdirmek için standart kullanıcılar (Yönetici olmayanlar) engeller. **Yapılandırılmamış** (varsayılan), Görev Yöneticisi'ni kullanarak görev ya da bir işlemi sonlandırmak standart kullanıcılar izin verir.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="locked-screen-experience"></a>Kilit ekranı deneyimi

- **İşlem Merkezi bildirimleri (yalnızca mobil)** : **Blok** gösteren cihaz kilit ekranında İşlem Merkezi bildirimleri engeller. **Yapılandırılmamış** (varsayılan) izin verir, kullanıcıların hangi uygulamaların bildirimleri kilit ekranında Göster'i seçin.

  [AboveLock/AllowActionCenterNotifications CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock#abovelock-allowactioncenternotifications)

- **Ekranı resmi URL'si (yalnızca Masaüstü)** : Windows kilit ekranı duvar kağıdı olarak kullanılan JPG, JPEG veya PNG biçiminde bir resmin URL'sini girin. Örneğin, şunu girin: `https://contoso.com/image.png`. Bu ayar, görüntünün kilitler ve daha sonra değiştirilemez.
- **Kullanıcı tarafından yapılandırılabilir ekran zaman aşımı (yalnızca mobil)** : **İzin** kullanıcıların ekran zaman aşımını yapılandırmasına olanak tanır. **Yapılandırılmamış** (varsayılan) Bu seçenek kullanıcılara vermek değil.

  [DeviceLock/AllowScreenTimeoutWhileLockedUserConfig CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-allowscreentimeoutwhilelockeduserconfig)

- **Kilitli ekranda Cortana** (yalnızca Masaüstü): **Blok** kullanıcıların engeller gelen cihaz kilit ekranında olduğunda Cortana ile etkileşim. **Yapılandırılmamış** (varsayılan), Cortana ile etkileşim sağlar.

  [AboveLock/AllowCortanaAboveLock CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock#abovelock-allowcortanaabovelock)

- **Kilitli ekranda bildirimler**: **Blok** gösteren cihaz kilit ekranında kutlama bildirimleri engeller. **Yapılandırılmamış** (varsayılan), bu bildirimleri sağlar.

  [AboveLock/AllowToasts CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock#abovelock-allowtoasts)

- **Ekran zaman aşımı (yalnızca mobil)** : Ekranından kapatma ekran kilitleme süresi (saniye cinsinden) ayarlayın. Desteklenen değerler 11-1800'dür. Örneğin, `300` bu zaman aşımı 5 dakika olarak ayarlamak için.

  [DeviceLock/ScreenTimeoutWhileLocked CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-screentimeoutwhilelocked)

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="messaging"></a>Mesajlaşma

Bu ayarları kullanın [ilke CSP Mesajlaşma](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-messaging); desteklenen Windows sürümleri de listelenir.

- **İleti eşitleme (yalnızca mobil)** : **Blok** kısa mesaj yedeklenebilir ve geri yüklenebilir ve Windows cihazları arasında iletileri eşitlemeyi devre dışı bırakır. Devre dışı bırakma, kuruluşun denetimi dışında sunucularında depolanan bilgileri önlemeye yardımcı olur. **Yapılandırılmamış** (varsayılan), kullanıcıların bu ayarları değiştirmek ve kendi iletilerini eşitleme sağlar.
- **MMS (yalnızca mobil)** : **Blok** MMS cihazdaki işlevini gönderip devre dışı bırakır. Kuruluşlar için MMS denetleme veya yönetim gereksiniminin parçası olarak cihazlarda devre dışı bırakmak için bu ilkeyi kullanın. **Yapılandırılmamış** MMS gönderme ve alma (varsayılan) izin verir.
- **RCS (yalnızca mobil)** : **Blok** zengin iletişim Hizmetleri (RCS) cihazdaki işlevini gönderip devre dışı bırakır. Kuruluşlar için RCS, denetleme veya yönetim gereksiniminin parçası olarak cihazlarda devre dışı bırakmak için bu ilkeyi kullanın. **Yapılandırılmamış** (varsayılan) RCS gönderip almasına izin verir.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="microsoft-edge-browser"></a>Microsoft Edge Tarayıcısı

Bu ayarları kullanın [tarayıcı İlkesi CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser), desteklenen Windows sürümleri de listelenir.

### <a name="use-microsoft-edge-kiosk-mode"></a>Microsoft Edge bilgi noktası modunu kullan

Kullanılabilir ayarlar, seçtiğiniz bağlı olarak değiştirin. Seçenekleriniz şunlardır:

- **Hayır** (varsayılan): Microsoft Edge, bilgi noktası modunda çalışmıyor. Tüm Microsoft Edge ayarları değiştirin ve yapılandırmak için kullanılabilir.
- **Sayısal/etkileşimli Tabela (tek uygulama bilgi noktası)** : Sayısal/etkileşimli Tabela Microsoft Edge bilgi noktası modu için geçerli olan filtreleri Microsoft Edge ayarları yalnızca Windows 10 tek uygulama bilgi noktaları üzerinde kullanın. URL tam ekran açmak için bu ayarı seçin ve yalnızca bu Web sitesinde içerik gösterir. [Dijital ayarlanan](https://docs.microsoft.com/windows/configuration/setup-digital-signage) bu özellik hakkında daha fazla bilgi sağlar.
- **InPrivate genel (tek uygulama bilgi noktası) gözatma**: Windows 10 tek uygulama bilgi noktaları üzerinde InPrivate genel gözatma Microsoft Edge için bilgi noktası modu için geçerli olan filtreleri Microsoft Edge ayarlarını kullanın. Microsoft Edge çoklu sekme sürümünü çalıştırır.
- **Normal moda (çoklu uygulama bilgi noktası)** : Normal Microsoft Edge bilgi noktası modu için geçerli olan Microsoft Edge ayarlarını filtreler. Microsoft Edge sürümü tam tarama tüm özellikleriyle çalışır.
- **Genel (çoklu uygulama bilgi noktası) gözatma**: Bir Windows 10 çoklu uygulama bilgi noktası genel göz atmak için geçerli olan Microsoft Edge ayarlarını filtreler.  Çoklu sekme sürümü Microsoft Edge InPrivate çalışır.

> [!TIP]
> Bu seçenekler neler daha fazla bilgi için bkz: [Microsoft Edge bilgi noktası modu yapılandırma türlerine](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

Bu cihaz kısıtlamaları profili kullanarak oluşturduğunuz için kiosk profili doğrudan ilgili [Windows bilgi noktası ayarları](kiosk-settings-windows.md). Özetlersek:

1. Oluşturma [Windows bilgi noktası ayarları](kiosk-settings-windows.md) cihaz bilgi noktası modunda çalıştırmak için profili. Microsoft Edge uygulamayı seçin ve Microsoft Edge bilgi noktası modu bilgi noktası profilinde ayarlayın.
2. Bu makalede açıklanan cihaz kısıtlama profili oluşturun ve belirli özellikler ve Microsoft Edge'de izin ayarlarını yapılandırın. Bilgi noktası profilinizde seçili olarak aynı Microsoft Edge bilgi noktası modu türünü seçtiğinizden emin olun ([Windows bilgi noktası ayarları](kiosk-settings-windows.md)). 

    [Bilgi noktası modu ayarları desteklenen](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-policies-for-kiosk-mode) harika bir kaynaktır.

> [!IMPORTANT] 
> Bu Microsoft Edge profili aynı cihaz bilgi noktası profilinizin olarak atadığınızdan emin olun ([Windows bilgi noktası ayarları](kiosk-settings-windows.md)).

[ConfigureKioskMode CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-configurekioskmode)

### <a name="start-experience"></a>Başlangıç deneyimi

- **Microsoft Edge ile Başlat**: Microsoft Edge başladığında, hangi sayfaların Aç'ı seçin. Seçenekleriniz şunlardır:
  - **Özel başlangıç sayfaları**: Başlangıç sayfaları gibi girin `http://www.contoso.com`. Microsoft Edge, girdiğiniz başlangıç sayfalarını yükler.
  - **Yeni bir sekme sayfası**: Microsoft Edge yük ne olursa olsun girildiğini **yeni sekme URL'si** ayarı.
  - **Son oturumun sayfa**: Microsoft Edge, son oturum sayfasını yükler.
  - **Yerel uygulama ayarlarında başlangıç sayfaları**: İşletim sistemi tarafından tanımlanan varsayılan başlangıç sayfasını ile Microsoft Edge başlayın.

- **Kullanıcının başlangıç sayfalarını değiştirmesine izin ver**: **Evet** (varsayılan), kullanıcılara başlangıç sayfalarını değiştirmesine olanak tanır. Yöneticiler `EdgeHomepageUrls` varsayılan olarak kullanıcıların gördüğü başlangıç sayfalarını girmek için Microsoft Edge açın. **Hayır** kullanıcıların başlangıç sayfalarını değiştirmesini engeller.
- **Web içeriği yeni sekme sayfasında izin**: Ayarlandığında **Evet** (varsayılan), Microsoft Edge, girilen URL açılır **yeni sekme URL'si** ayarı. Varsa **yeni sekme URL'si** ayarı boşsa, Microsoft Edge, Microsoft Edge ayarları içinde listelenen yeni sekme sayfası açılır. Kullanıcılar bunu değiştirebilir. Ayarlandığında **Hayır**, Microsoft Edge ile boş bir sayfa yeni sekmede açılır. Kullanıcılar bunu değiştiremez.
- **Yeni sekme URL'si**: Yeni bir sekme sayfasını açmak için URL'yi girin. Örneğin `https://www.bing.com` veya `https://www.contoso.com` girin.

- **Giriş düğmesi**: Giriş düğmesi seçili olduğunda ne olacağını seçin. Seçenekleriniz şunlardır:
  - **Başlangıç sayfaları**: Seçeneği, seçtiğiniz açılır **Başlat Microsoft Edge ile** ayarı
  - **Yeni bir sekme sayfası**: Girdiğiniz URL açılır **yeni sekme URL'si** ayarı.
  - **Giriş düğmesi URL'si**: Açılacak URL'yi girin. Örneğin `https://www.bing.com` veya `https://www.contoso.com` girin.
  - **Gizleme giriş düğmesine**: Giriş düğmesini gizler
- **Kullanıcıların giriş düğmesi değiştirmesine izin verin**: **Evet** kullanıcıların giriş düğmesi değiştirmesine olanak tanır. Kullanıcının yaptığı değişiklikleri giriş düğmesi için herhangi bir yönetici ayarları geçersiz kılar. **Hayır** (varsayılan), kullanıcıların nasıl giriş düğmesi yönetici tarafından yapılandırılan değiştirmesini engeller.
- **İlk çalıştırma deneyimi sayfasında (yalnızca mobil) Göster**: **Evet** (varsayılan), Microsoft Edge'de ilk kullan giriş sayfasını gösterir. **Hayır** durdurur ilk gösteren giriş sayfasından, Microsoft Edge çalıştırma süresi. Kuruluşların bu sayfayı engellemesine izin yapılandırmaları, sıfır emisyonlarını içinde kayıtlı gibi kuruluşlar, bu özelliği sağlar.
- **İlk çalıştırma deneyimi URL konumu listesinde** (yalnızca Windows 10 Mobile): İlk çalıştırma sayfasını URL'leri içeren bir XML dosyasına işaret eden bir URL girin. Örneğin, şunu girin: `https://www.contoso.com/sites.xml`.

- **Boşta kalma süresinden sonra tarayıcıyı yenileyin**: Tarayıcı yenilendikten, 0-1440 kadar boşta dakika sayısını girin dakika. Varsayılan değer `5` dakika. Ayarlandığında `0` olmayan tarayıcıyı yenileyin (sıfır) boşta kaldıktan sonra.

  Bu ayar yalnızca çalıştırıldığında kullanılabilir [(tek uygulama bilgi noktası) genel InPrivate Gözatma](#use-microsoft-edge-kiosk-mode).

- **Açılır pencerelere izin ver** (yalnızca Masaüstü): **Evet** (varsayılan) web tarayıcısında açılır pencerelere izin verir. **Hayır** tarayıcıdaki açılır pencereleri engeller.
- **Internet Explorer'a intranet trafiği Gönder** (yalnızca Masaüstü): **Evet** kullanıcıların Microsoft Edge yerine Internet Explorer'da intranet Web siteleri açmasına olanak sağlar. Bu ayar için geriye dönük uyumluluğa yöneliktir. **Hayır** (varsayılan), kullanıcıların Microsoft Edge kullanmasını sağlar.
- **Kurumsal mod site listesi konumu** (yalnızca Masaüstü): Kurumsal modda açılan web siteleri listesini içeren bir XML dosyasına işaret eden URL girin. Kullanıcılar bu listeyi değiştiremez. Örneğin, şunu girin: `https://www.contoso.com/sites.xml`.
- **Açılırken ileti siteleri Internet Explorer'da**: Internet Explorer 11'de bir site açılmadan önce bir bildirim göstermek için Microsoft Edge yapılandırmak için bu ayarı kullanın. Seçenekleriniz şunlardır:
  - **İletiyi gösterme**: İşletim sistemi varsayılan davranışı, bir ileti gösterilmeyebilir kullanılır.
  - **Internet Explorer 11'de site ileti gösterin açıldığında**: IE'de siteleri açarken iletiyi gösterir. Siteleri IE'de açın. 
  - **Microsoft Edge'de siteler açılır seçeneğiyle iletiyi göster**: İleti Edge'de siteleri açarken gösterir. İletiyi içeren bir **Microsoft Edge'de kullanmaya devam** kullanıcılar Microsoft Edge yerine IE seçebilmeniz bağlantı.

  > [!IMPORTANT]
  > Bu ayarı kullanmanızı gerekli hale getirmiş **Kurumsal mod site listesi konumu** ayarını **Internet Explorer'a intranet trafiği Gönder** ayarı veya her iki ayar.

- **Microsoft uyumluluk listesini izin**: **Evet** (varsayılan), Microsoft uyumluluk listesini kullanarak izin verir. **Hayır** Microsoft edge'de Microsoft uyumluluk listesini engeller. Microsoft'un bu listesi, Microsoft Edge bilinen uyumluluk sorunlarına sahip siteleri düzgün görüntülenmesi yardımcı olur.
- **Dağıtılacak başlangıç sayfalarını ve sayfa yeni sekmede**: **Evet** (varsayılan), bu sayfaları dağıtılacak olabilir işletim sistemi varsayılan davranışı kullanır. Önceden yükleme Microsoft Edge başlatın ve yeni sekmeler yükleme süresini en aza indirir. **Hayır** başlangıç sayfalarını ve yeni bir sekme sayfası Şubelerdeki Microsoft Edge engeller.
- **Önceden başlatma başlangıç sayfalarını ve sayfa yeni sekmede**: **Evet** (varsayılan), bu sayfaları için önceden başlatma işletim sistemi varsayılan davranışı kullanır. Önceden başlatma, Microsoft Edge performansını yardımcı olur ve Microsoft Edge başlatmak için gereken süreyi en aza indirir. **Hayır** Microsoft Edge başlangıç sayfalarını ve yeni bir sayfa önceden başlatmasını engeller.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

### <a name="favorites-and-search"></a>Sık Kullanılanlar ve arama

- **Sık Kullanılanlar çubuğu Göster**: Sık Kullanılanlar çubuğuna herhangi bir Microsoft Edge sayfasında ne olacağını seçin. Seçenekleriniz şunlardır:
  - **Başlat ve yeni bir sekme sayfaları**: Sık Kullanılanlar çubuğu Microsoft Edge başladığında ve tüm sekme sayfaları gösterir. Son kullanıcılar, bu ayarı değiştirebilirsiniz.
  - **Tüm sayfalardaki**: Sık Kullanılanlar çubuğu tüm sayfalarında gösterilir. Son kullanıcılar, bu ayarı değiştiremezsiniz.
  - **Gizli**: Sık Kullanılanlar çubuğu tüm sayfalardaki gizler. Son kullanıcılar, bu ayarı değiştiremezsiniz.
- **Sık Kullanılanlar değişikliğe izin**: **Evet** (varsayılan), kullanıcıların listesini değiştirmek varsayılan işletim sistemi kullanır. **Hayır** son kullanıcılar'ı eklemek için içeri aktarma, sıralama veya Sık Kullanılanlar listesini düzenlemesini engeller.
  - **Sık Kullanılanlar listesine**: URL'lerin bir listesini, Sık Kullanılanlar dosyaya ekleyin. Örneğin, ekleme `http://contoso.com/favorites.html`.
- **Microsoft tarayıcıları arasında sık kullanılanları Eşitle** (yalnızca Masaüstü): **Evet** Windows Internet Explorer ve Microsoft Edge arasında sık kullanılanları eşitlemeye zorlar. Ekleme, silme, değişiklikler ve siparişi değişikliklerinin Sık Kullanılanlar tarayıcılar arasında paylaşılır.  **Hayır** (varsayılan), kullanıcıların seçim tarayıcıları arasında sık kullanılanları Eşitle verebilir işletim sistemi varsayılan olarak kullanır.
- **Varsayılan arama motorunu**: Varsayılan arama motorunu cihazda seçin. Son kullanıcılar bu değeri istediği zaman değiştirebilir. Seçenekleriniz şunlardır:
  - Arama motoru istemci Microsoft Edge ayarları
  - Bing
  - Google
  - Yahoo
  - Özel değer: İçinde **OpenSearch Xml URL'si**, kısa bir ad ve en az bir arama motoru URL'sini içeren bir XML dosyası ile bir HTTPS URL'si girin. Örneğin, şunu girin: `https://www.contoso.com/opensearch.xml`.
- **Arama önerileri göster**: **Evet** (varsayılan), adres çubuğunda arama tümcecikleri yazarken arama motorunuzun site olanak tanır. **Hayır** bu özellik engeller.
- **Arama motoru değişikliklere izin**: **Evet** (varsayılan), yeni arama motorları eklemek veya varsayılan arama motorunu Microsoft edge'de değiştirmek kullanıcıların sağlar. Seçin **Hayır** arama motoru özelleştirmesini kullanıcıların önlemek için.

  Bu ayar yalnızca çalıştırıldığında kullanılabilir [Normal modda (çoklu uygulama bilgi noktası)](#use-microsoft-edge-kiosk-mode).

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

### <a name="privacy-and-security"></a>Gizlilik ve güvenlik

- **InPrivate gözatmaya izin ver**: **Evet** (varsayılan) Microsoft Edge InPrivate Gözatma sağlar. Microsoft Edge InPrivate sekmelerin kapattıktan sonra CİHAZDAN tarama verilerini siler. **Hayır** son kullanıcıların InPrivate Gözatma oturumları açmasını engeller.
- **Tarama geçmişi Kaydet**: **Evet** (varsayılan) Microsoft Edge'de gözatma geçmişini kaydetmeye olanak tanır. **Hayır** gözatma geçmişini kaydetme engeller.
- **Clear Çıkışta tarama verilerini** (yalnızca Masaüstü): **Evet** geçmişini temizler ve kullanıcının Microsoft Edge çıkarken tarama verilerini. **Hayır** (varsayılan) kullanan işletim sistemi varsayılan, tarama verilerini önbelleğe alabilir.
- **Tarayıcı ayarlarını kullanıcının cihazlar arasında eşitleme**: Tarayıcı ayarlarını cihazlar arasında eşitleme istediğiniz şekli seçin. Seçenekleriniz şunlardır:
  - **İzin ver**: Microsoft Edge tarayıcı ayarları kullanıcının cihazlar arasında eşitlenmesine izin ver
  - **Blok ve kullanıcı geçersiz kılma etkinleştir**: Microsoft Edge tarayıcı ayarları kullanıcının cihazlar arasında eşitlemeyi engelleyin. Kullanıcılar bu ayarı geçersiz kılabilirsiniz.
  - **Blok**: Microsoft Edge tarayıcı ayarı kullanıcıların aygıtları arasında eşitlemeyi engelleyin. Kullanıcılar, bu ayarı geçersiz kılamaz.

Kullanıcı, "engelleyin ve kullanıcı geçersiz kılma etkinleştir" seçili olduğunda, yönetici ataması geçersiz kılabilirsiniz.

- **Parola yöneticisine izin ver**: **Evet** (varsayılan), kullanıcılara kaydetme ve cihazın parolaları yönetmek parola Yöneticisi otomatik olarak kullanılacak Microsoft Edge sağlar. **Hayır** Microsoft Edge parola Yöneticisi'ni kullanarak engeller.
- **Tanımlama bilgileri**: Web tarayıcısında tanımlama bilgilerine nasıl işleneceğini seçin. Seçenekleriniz şunlardır:
  - **İzin ver**: Tanımlama bilgilerinin cihazda depolanır.
  - **Tüm tanımlama bilgilerini engelle**: Tanımlama bilgilerinin cihazda depolanmaz.
  - **Yalnızca üçüncü taraf tanımlama bilgilerini engelle**: Üçüncü taraf veya iş ortağı tanımlama bilgilerinin cihazda depolanmaz.
- **Otomatik doldurmaya izin ver formlarında**: **Evet** (varsayılan) izin verir, kullanıcıların tarayıcıdaki otomatik tamamlama ayarlarını değiştirmesine ve form alanlarını otomatik olarak doldurur. **Hayır** Microsoft edge'de otomatik doldurma özelliğinin devre dışı bırakır.
- **Kullanıcıyı-izleme üst bilgileri gönderme**: **Evet** (önerilen) izleme bilgisi isteyen Web sitelerine not track üst bilgileri gönderir. **Hayır** (varsayılan) göndermez üst bilgileri, kullanıcıyı izlemek Web siteleri sağlar. Kullanıcı yapılandırabilirsiniz.
- **WebRTC localhost IP adresi Göster**: **Evet** (varsayılan), kullanıcıların localhost IP adresi, bu protokolü kullanılarak telefon aramaları gerçekleştirilirken gösterilmesini sağlar. **Hayır** gösterilen kullanıcıların localhost IP adresi engeller. 
- **Canlı kutucuk veri toplama izin**: **Evet** Canlı Başlat menüsüne sabitlenmiş olan kutucuklarda bilgi toplamak Microsoft Edge (varsayılan) sağlar. **Hayır** kullanıcılar ile sınırlı bir deneyim sağlayabilir. Bu bilgileri toplama engeller.
- **Kullanıcı sertifika hataları geçersiz kılma**: **Evet** (varsayılan), Güvenli Yuva Katmanı/Aktarım Katmanı Güvenliği (SSL/TLS) hata içeren Web sitelerine erişmek kullanıcıların sağlar. **Hayır** (daha fazla güvenlik için önerilir) kullanıcıların Web siteleri SSL veya TLS hatalarla erişmesini engeller.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

### <a name="additional"></a>Ek

- **Microsoft Edge tarayıcısına izin ver** (yalnızca mobil): **Evet** (varsayılan), mobil cihazda Microsoft Edge web tarayıcısı kullanarak sağlar. **Hayır** cihazda Microsoft Edge kullanarak engeller. Seçerseniz **Hayır**, diğer ayarlardan yalnızca Masaüstü için geçerlidir.
- **Adres çubuğu açılır izin**: **Evet** adres çubuğu aşağı açılan öneri listesi ile göstermek Microsoft Edge (varsayılan) sağlar. **Hayır** Microsoft Edge yazarken öneriler listesi aşağı açılan listesinde göstermesini durdurur. Ayarlandığında **Hayır**,:
  - Microsoft Edge ile Microsoft Hizmetleri arasında ağ bant genişliğini en aza indirmenize yardımcı.
  - Devre dışı **yazarken arama ve site önerileri göster** Microsoft edge'de > ayarlar.
- **Tam ekran moduna izin ver**: **Evet** (varsayılan), Microsoft Edge web içeriği gösterir ve Microsoft Edge kullanıcı arabirimini gizler kullanımı tam ekran moduna sağlar. **Hayır** Microsoft Edge tam ekran modunda engeller.
- **Flags sayfasına hakkında izin**: **Evet** (varsayılan) kullanan erişilebilmesini sağlar işletim sistemi varsayılan `about:flags` sayfası. `about:flags` Sayfası Geliştirici ayarlarını değiştirmek ve Deneysel özellikler etkinleştirmesine olanak sağlar. **Hayır** son kullanıcıların erişmesini engelleyen `about:flags` Microsoft edge'de sayfası.
- **Geliştirici araçlarına izin ver**: **Evet** (varsayılan) oluşturun ve web sayfaları varsayılan olarak hata ayıklama için F12 geliştirici araçları kullanma olanağı sağlar. **Hayır** son kullanıcıların F12 Geliştirici araçlarıyla kullanmasını önler.
- **JavaScript'e izin**: **Evet** (varsayılan), Microsoft Edge tarayıcısında çalıştırmak için Javascript gibi betiklerin izin verir. **Hayır** tarayıcıda Java betiğinin çalışmasını engeller.
- **Kullanıcı Uzantıları yükleyebilirsiniz**: **Evet** (varsayılan), son kullanıcıların cihazda Microsoft Edge uzantıları yükleme sağlar. **Hayır** yüklemeyi engeller.
- **Dışarıdan yükleme Geliştirici uzantılarının izin**: **Evet** (varsayılan) dışarıdan yükleme olarak izin verebileceği işletim sistemi varsayılan olarak kullanır. Dışarıdan yükleme yükler ve doğrulanmamış uzantıları çalıştırır. **Hayır** dışarıdan yükleme yoluyla Microsoft Edge engel **yük uzantıları** özelliği. Bu, PowerShell gibi başka yollar kullanarak dışarıdan yükleme uzantıları engellemez.
- **Gerekli uzantıları**: Microsoft edge'de son kullanıcılar tarafından hangi uzantıları kapatılamaz seçin. Paket aile adları'nı girin ve seçin **Ekle**. [Bir paket aile adı (PFN) bulma](https://docs.microsoft.com/sccm/protect/deploy-use/find-a-pfn-for-per-app-vpn) rehberlik sağlar.

  Ayrıca **alma** paket aile adları içeren bir CSV dosyası. Veya, **dışarı** girdiğiniz paket aile adları.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="network-proxy"></a>Ağ proxy’si

Bu ayarları kullanın [NetworkProxy ilke CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp), desteklenen Windows sürümleri de listelenir.

- **Proxy ayarlarını otomatik olarak algıla**: **Blok** proxy otomatik yapılandırma (PAC) betiği otomatik olarak algılama cihazın devre dışı bırakır. **Yapılandırılmamış** (varsayılan), bu özelliği etkinleştirir. Etkinleştirildiğinde, cihaz bir PAC betiğinin yolunu bulmaya çalışır.
- **Proxy betiği kullan**: Seçin **izin** için proxy sunucusunu yapılandırmak için PAC betiğinin yolunu girin. **Yapılandırılmamış** (varsayılan) için bir PAC betiğinin URL'sini girin, izin vermez.
  - **Kurulum betiği adresi URL'si**: Proxy sunucusunu yapılandırmak için kullanmak istediğiniz bir PAC betiğinin URL'sini girin.
- **El ile proxy sunucusu kullan**: Seçin **izin** adını veya IP adresi ve bir proxy sunucusu TCP bağlantı noktası numarasını el ile girmek için. **Yapılandırılmamış** (varsayılan), bir ara sunucu ayrıntılarını el ile girin izin vermez.
  - **Adresi**: Adını veya proxy sunucusunun IP adresini girin.
  - **Bağlantı noktası numarası**: Proxy sunucunuzun bağlantı noktası numarasını girin.
  - **Proxy özel durumları**: Proxy sunucusunu kullanmaması gereken herhangi bir URL girin. Her birini ayırmak için noktalı virgül kullanın.
  - **Yerel adres için proxy sunucuyu atla**: **Yapılandırılmamış** (varsayılan) intranetinizde yerel adresler için proxy sunucusu kullanarak engeller. **İzin** yerel adresler için proxy sunucusunu kullanır.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="password"></a>istemcisiyle yönetilen bir cihaz için)

Bu ayarları kullanın [DeviceLock ilke CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock), desteklenen Windows sürümleri de listelenir.

- **Parola**: **Gerekli** ayarı son kullanıcının cihaza erişmek için parola girmesini zorunlu tutar. **Yapılandırılmamış** (varsayılan), bir parola olmadan cihaz erişim sağlar. Yalnızca yerel hesaplar için geçerlidir. Etki alanı hesabı parolaları Active Directory (AD) ve Azure AD tarafından yapılandırılmış olarak kalır.

  - **Gerekli parola türü**: Parola türünü seçin. Seçenekleriniz şunlardır:
    - **Yapılandırılmadı**: Parola, sayı ve harf içerebilir.
    - **Sayısal**: Parola yalnızca sayı olması gerekir.
    - **Alfasayısal**: Parola, sayılardan ve harflerden oluşan bir karışımı olmalıdır.
  - **Minimum parola uzunluğu**: Gereken en düşük rakam veya gerekli, 4-16 karakter girin. Örneğin, `6` parola uzunluğu en az altı karakter istemek için.
  
    > [!IMPORTANT]
    > Windows masaüstünde parola gerekliliği değiştirildiğinde, cihaza geçerse, etkin boşta sahip olarak uygulamasında oturum açtığında kullanıcının etkilendiğini. Gereksinimini karşılamayan parolası olan kullanıcılar hala parolalarını değiştirmesi istenir.
    
  - **Cihaz silinmeden önceki oturum açma hatası sayısı**: En fazla 11 cihaz silinebilen önce izin verilen kimlik doğrulama hatalarının sayısını girin. Geçerli sayı sürümüne bağlıdır. [DeviceLock/MaxDevicePasswordFailedAttempts CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-maxdevicepasswordfailedattempts) desteklenen değerleri listeler. `0` (sıfır), cihaz silme işlevselliği devre dışı bırakabilir.

    Bu ayar, ayrıca sürüme bağlı olarak farklı bir etkiye sahiptir. Bu ayar, belirli Ayrıntılar için bkz. [DeviceLock/MaxDevicePasswordFailedAttempts CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-maxdevicepasswordfailedattempts).

  - **Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı**: Ekran kilitlenmeden önce cihazın boşta bekleyeceği süreyi girin.
  - **Parola zaman aşımı (gün sayısı)** : Gün, cihaz parolasının, 1-365'ten değiştirilmesi gereken süreyi girin. Örneğin, `90` parola 90 gün sonra süresi dolacak şekilde.
  - **Önceki parolaların yeniden kullanılmasını engelleme**: 1-24 kullanılamaz önceden kullanılmış parola sayısını girin. Örneğin, `5` için kullanıcıların geçerli parolalarını veya herhangi bir önceki dört parolalarını yeni bir parola ayarlanamaz.
  - **Cihaz boşta durumundan çıkarken parola iste** (Mobil ve Holographic): Seçin **gerektiren** kullanıcılar boşta kaldıktan sonra cihazın kilidini açmak için parola girmeniz gerekir. **Yapılandırılmamış** (varsayılan) gerektirmez bir PIN veya parola cihaz boşta durumundan çıktığında.
  - **Basit parolalar**: Kümesine **blok** kullanıcılar gibi basit parolalar oluşturamıyor `1234` veya `1111`. Kümesine **yapılandırılmadı** kullanıcıların gibi parolalar oluşturmalarına izin vermek için (varsayılan) `1234` veya `1111`. Bu ayar, Windows resimli parolalarının kullanımına izin verir veya bunu engeller.
- **AADJ sırasında otomatik şifreleme**: **Blok** cihaz, cihaz Azure AD'ye katılmış olduğunda ilk kullanım için hazırlanır değilse otomatik BitLocker cihaz şifreleme önlenir. **Yapılandırılmamış** (varsayılan) şifreleme sağlayabilir işletim sistemi varsayılan kullanır. Daha açık [BitLocker cihaz şifreleme](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption).

  [Güvenlik/PreventAutomaticDeviceEncryptionForAzureADJoinedDevices CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-preventautomaticdeviceencryptionforazureadjoineddevices)

- **Federal Bilgi İşleme Standardı (FIPS) İlkesi**: **İzin** bir ABD Federal Bilgi İşleme Standardı (FIPS) ilkesi kullandığı şifreleme, kodlama ve imzalama için standart. **Yapılandırılmamış** (varsayılan), FIPS kullanmaz işletim sistemi varsayılan olarak kullanır.

  [Şifreleme/AllowFipsAlgorithmPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-cryptography#cryptography-allowfipsalgorithmpolicy)

- **Windows Hello cihazı kimlik doğrulaması**: **İzin** kullanıcıların Windows 10 bilgisayara oturum açmak için Windows Hello gibi bir yardımcı cihaz, telefon, uygunluk bant veya IOT cihaz kullanın. **Yapılandırılmamış** (varsayılan), Windows Hello yardımcı cihazların Windows ile kimlik doğrulaması engelleyebilir işletim sistemi varsayılan olarak kullanır.

  [Kimlik doğrulama/AllowSecondaryAuthenticationDevice CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowsecondaryauthenticationdevice)

- **Oturum açma Web**: Windows oturum ADFS dışında (Active Directory Federasyon Hizmetleri) Federasyon sağlayıcıları, güvenlik onaylama işlemi biçimlendirme dili (SAML) gibi için destek sağlar. SAML web tarayıcıları bir çoklu oturum açma (SSO) deneyimi güvenli belirteçleri kullanır. Seçenekleriniz şunlardır:

  - **Yapılandırılmadı** (varsayılan): İşletim sistemi varsayılan cihazda kullanır.
  - **Etkin**: Web Kimlik sağlayıcısı oturum açma için etkinleştirilir.
  - **Devre dışı**: Web Kimlik sağlayıcısı oturum açma devre dışı bırakılmıştır.

  [Kimlik doğrulama/EnableWebSignIn CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-enablewebsignin)

- **Azure AD kiracısı etki alanının tercih edilen**: Azure AD kuruluşunuzda mevcut bir etki alanı adını girin. Bu etki alanındaki kullanıcılar oturum açtığında, etki alanı adını yazmanız gerekmez. Örneğin, şunu girin: `contoso.com`. Kullanıcıların `contoso.com` etki alanı kullanıcı adı gibi kullanarak oturum açabilir `abby`, yerine `abby@contoso.com`.

  [Authentication/PreferredAadTenantDomainName CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-preferredaadtenantdomainname)

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="per-app-privacy-exceptions"></a>Uygulama başına gizlilik özel durumları

"Varsayılan gizlilik" Tanımla'dan farklı bir gizlilik davranışı olması gereken uygulamaları ekleyebilirsiniz.

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
- **Güvenilen cihazlar**: Bu uygulamanın güvenilen cihazları kullanıp kullanamayacağını seçin. Güvenilen cihazlara donanım zaten bağlanmış olduğunuz veya cihaz ile birlikte gelen donanım olmalıdır. Örneğin, TV, projektör ve benzeri, güvenilen cihazlar olarak kullanın.
- **Geri bildirim ve tanılama**: Bu uygulamanın tanılama bilgilerine erişip erişemeyeceğini tanımlayın.
- **Cihazlarla Eşitle**: Bu uygulamayı otomatik olarak paylaşabilir ve bilgi cihazı ile doğrudan eşleştirilmeyen Kablosuz cihazlarla eşitleme durumunda seçin.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="personalization"></a>Kişiselleştirme

Bu ayarları kullanın [kişiselleştirme ilke CSP](https://docs.microsoft.com/windows/client-management/mdm/personalization-csp), desteklenen Windows sürümleri de listelenir.

- **Masaüstü arka plan resmi URL'si (yalnızca Masaüstü)** : Windows masaüstü duvar kağıdı olarak kullanmak istediğiniz .jpg, .jpeg veya .png biçiminde bir resmin URL'sini girin. Kullanıcılar bu resmi değiştiremez. Örneğin, şunu girin: `https://contoso.com/logo.png`.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="printer"></a>Yazıcı

- **Yazıcılar**: Eklenmiş olan yerel yazıcı listesi.
- **Varsayılan yazıcı**: Varsayılan yazıcıyı ayarlayın.
- **Yeni yazıcı eklemek için kullanıcı erişimi**: İzin verme veya yerel yazıcı kullanımına engelleme.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="privacy"></a>Gizlilik

Bu ayarları kullanın [gizlilik ilkesi CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy), desteklenen Windows sürümleri de listelenir.

- **Girişi kişiselleştirme**: **Blok** engeller ses dikte ve Cortana ve Microsoft bulut tabanlı konuşma tanıma kullanan diğer uygulamalar için iletişim kurmasına engel olur. Devre dışı bırakılır ve kullanıcılar ayarları kullanarak çevrimiçi bir konuşma tanıma etkinleştirilemiyor. **Yapılandırılmamış** (varsayılan), kullanıcıların seçmesine olanak sağlar. Microsoft, bu hizmetlere izin verirseniz, hizmeti geliştirmek için sesli veri toplayabilir.
- **Eşleştirme ve gizlilik Kullanıcı onayı istemlerini otomatik kabul**: Seçin **izin** Windows eşleştirme ve gizlilik onay iletilerini uygulama çalıştırırken otomatik olarak kabul edebilir. **Yapılandırılmamış** (varsayılan), uygulama açılırken eşleştirme ve gizlilik Kullanıcı onayı penceresi otomatik olarak kabul engeller.
- **Kullanıcı etkinliklerini yayımla**: **Blok** paylaşılan deneyimleri ve akış etkinliğinde yakın zamanda kullanılan kaynakların bulunmasını önler. **Yapılandırılmamış** (varsayılan), son kullanıcı etkinlikleri uygulamalar yayımlayabilmeniz bu özelliği etkinleştirir.
- **Yalnızca yerel etkinlikler**: **Blok** paylaşılan deneyimleri ve görev değiştiricide yalnızca yerel etkinliği temel alan, yakın zamanda kullanılan kaynakların bulunmasını önler. **Yapılandırılmamış** (varsayılan), bu özelliği etkinleştirir.

Cihazdaki tüm uygulamaların erişebileceği bilgileri yapılandırabilirsiniz. Ayrıca, bir uygulama başına kullanarak özel durum tanımlamak **uygulama başına gizlilik özel durumları**.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

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
- **Güvenilen cihazlar**: Bu uygulamanın güvenilen cihazları kullanıp kullanamayacağını seçin. Güvenilen cihazlara donanım zaten bağlanmış olduğunuz veya cihazı ile birlikte gelen donanım olmalıdır. Örneğin, TV, projektör ve benzeri, güvenilen cihazlar olarak kullanın.
- **Geri bildirim ve tanılama**: Bu uygulamanın tanılama bilgilerine erişip varsa seçin.
- **Cihazlarla eşitle** - Bu uygulamanın bu PC, tablet veya telefonla açıkça eşleştirilmemiş kablosuz cihazlarla otomatik olarak bilgi paylaşma ve eşitleme işlemleri yapıp yapamayacağını tanımlayın.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="projection"></a>Projeksiyon

Bu ayarları kullanın [WirelessDisplay ilke CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wirelessdisplay), desteklenen Windows sürümleri de listelenir.

- **Kablosuz görüntü alıcılarından kullanıcı girişini**: **Blok** kablosuz görüntü alıcılarından kullanıcı girişini engeller. **Yapılandırılmamış** (varsayılan), bir kablosuz görüntü gönderin klavye, fare, Kalem ve Dokunmatik geri kaynak cihaz giriş sağlar.
- **Bu Bilgisayara yansıtma**: **Blok** diğer cihazların yansıtma için cihaz bulmasını engeller. **Yapılandırılmamış** (varsayılan) bulunabilir ve cihaz kilit ekranı üzerinde proje için cihazın izin verir.
- **Eşleştirme için PIN iste**: Seçin **gerektiren** her zaman bir projeksiyon cihazına bağlanırken PIN istemek için. **Yapılandırılmamış** (varsayılan), cihaza bir projeksiyon cihazına kullanmak üzere bir PIN gerektirmez.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="reporting-and-telemetry"></a>Raporlama ve telemetri

- **Kullanım verilerini paylaşma**: Gönderilen Tanılama verileri düzeyini seçin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı**: Paylaşılan veri yok.
  - **Güvenlik**: Windows daha bağlı kullanıcı deneyimi ve Telemetri bileşen ayarları, kötü amaçlı yazılımları temizleme aracı ve Windows Defender'ın verileri dahil olmak üzere korunmasına yardımcı olmak için gerekli olan bilgileri.
  - **Temel**: Kalite ilgili veriler, uygulama uyumluluğu, uygulama kullanımı verilerini ve güvenlik düzeyi verileri dahil olmak üzere temel cihaz bilgileri.
  - **Gelişmiş**: Dahil olmak üzere ek Öngörüler: Windows, Windows Server, System Center ve uygulamaları nasıl kullanıldığı, gerçekleştirdikleri nasıl, Gelişmiş güvenilirlik verileri ve veri hem temel hem de güvenlik düzeyleri.
  - **Tam**: Tüm belirlemek ve sorunları gidermeye yardımcı olmak gereken verileri yanı sıra güvenlik, temel ve gelişmiş düzey verileri.

  [System/AllowTelemetry CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry)

- **Microsoft Edge tarama verilerini Microsoft 365 analytics'e gönderme**: Bu özelliği kullanmak için **kullanım verilerini paylaş** ayarlar **geliştirilmiş** veya **tam**. Hangi verilerin Microsoft Edge, yapılandırılmış bir ticari kimliği ile Kurumsal cihazlarda Microsoft 365 Analytics'e gönderir. Bu özellik denetler Seçenekleriniz şunlardır:
  - **Yapılandırılmadı**: İşletim sistemi varsayılan, tüm gözatma geçmişini gönderemeyebilir kullanır
  - **Yalnızca intranet veri gönderme**: Yöneticinin intranet veri geçmişini göndermek için
  - **Yalnızca İnternet'e veri göndermek**: Internet veri geçmişini göndermek yöneticinin sağlar
  - **İntranet ve İnternet'e veri göndermek**: İntranet ve internet veri geçmişini göndermek yöneticinin sağlar

  [Tarayıcı/ConfigureTelemetryForMicrosoft365Analytics CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-configuretelemetryformicrosoft365analytics)

- **Telemetri proxy sunucusu**: Tam etki alanı adı (FQDN) veya bağlı kullanıcı deneyimleri ve Telemetri istekleri, Güvenli Yuva Katmanı (SSL) bağlantısı kullanarak iletmek için bir proxy sunucusunun IP adresini girin. Bu ayarın biçimi *sunucu*:*bağlantı noktası* olur. Adlandırılmış proxy başarısız olursa veya bir proxy Bu ilkeyi etkinleştirmek, girilen değil, bağlı kullanıcı deneyimleri ve Telemetri verileri gönderilen değil ve yerel cihazda kalır.

  Örnek biçimler:

  ```
  IPv4: 192.246.246.106:100
  IPv6: [2001:4898:4010:4013:95c1:a8b2:953c:c633]:100
  FQDN: www.contoso.com:345
  ```

  [System/TelemetryProxy CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-telemetryproxy)

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="search"></a>Ara

Bu ayarları kullanın [ilke CSP arama](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-search), desteklenen Windows sürümleri de listelenir. 

- **Güvenli arama (yalnızca mobil)** : Cortana'nın yetişkinlere yönelik içeriği arama sonuçlarında nasıl filtreleyeceğini denetleyin. Seçenekleriniz şunlardır:
  - **Kullanıcı tanımlı**: Son kullanıcıların kendi ayarlarını seçmesine izin verin.
  - **Katı**: Yetişkinlere yönelik içeriğe karşı en yüksek filtreleme.
  - **Orta**: Yetişkinlere yönelik içeriğe karşı orta düzeyli filtreleme. Geçerli arama sonuçlarını filtrelersiniz değildir.
- **Aramada web sonuçlarını görüntüle**: Ayarlandığında **blok**olamaz kullanıcılar arama ve web sonuçlarının aramada gösterilen olmayan. **Yapılandırılmamış** (varsayılan), kullanıcıların Web'de arama sağlar ve cihazda sonuçları gösterilir.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="start"></a>Başlat

Bu ayarları kullanın [ilkesini CSP başlatma](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-start), desteklenen Windows sürümleri de listelenir.  

- **Başlangıç menüsü düzeni**: Varsayılan başlangıç düzenini geçersiz kılmasına ve Masaüstü cihazlarını Başlat menüsünde özelleştirebilirsiniz. Listelenen uygulamalar, sipariş dahil olmak üzere özelleştirmelerinizi ve daha fazlasını içeren bir XML dosyasını karşıya yükleyin. Kullanıcılar, girdiğiniz Başlat menüsü düzenini değiştiremez.
- **Başlat menüsünde Web siteleri için kutucuklar sabitleme**: Görüntüleri Masaüstü cihazları için Windows Başlat menüsündeki bağlantılar olarak gösterilen Microsoft Edge içeri aktarın.
- **Uygulamaları görev çubuğundan Kaldır**: **Blok** kullanıcıların görev çubuğundan uygulamaları kaldırmasını engeller. **Yapılandırılmamış** (varsayılan), kullanıcıların uygulamaları görev çubuğundan Kaldır izin verir.
- **Hızlı Kullanıcı Geçişi**: **Blok** aynı anda kapatmadan oturum açmış kullanıcılar arasında değiştirmeyi engeller. **Yapılandırılmamış** gösterir (varsayılan) **Kullanıcı Değiştir** kullanıcı kutucuğunda.
- **En çok kullanılan uygulamalar**: **Blok** gösteren Başlat menüsünde en çok kullanılan uygulamalardan gizler. Bu ayrıca Ayarlar uygulamasında aynı ada sahip iki durumlu ayarı da devre dışı bırakır. **Yapılandırılmamış** (varsayılan), en çok kullanılan uygulamaları gösterir.
- **Uygulamalar'en son eklenen**: **Blok** gizler en son eklenen uygulamaları gösteren Başlat menüsündeki öğesinden. Bu ayrıca Ayarlar uygulamasında aynı ada sahip iki durumlu ayarı da devre dışı bırakır. **Yapılandırılmamış** (varsayılan), son eklenen uygulamaların başlangıç menüsünde gösterir.
- **Başlangıç ekranı modu**: Başlangıç ekranına nasıl gösterilen seçin. Seçenekleriniz şunlardır:
  - **Kullanıcı tanımlı**: Başlangıç boyutunu zorla değil. Kullanıcılar boyutunu ayarlayabilirsiniz.
  - **Tam ekran**: Başlangıç ekran boyutunu zorlar.
  - **Tam olmayan ekran**: Başlangıç tam olmayan ekran boyutunu zorlar.
- **Son açılan öğeler bağlantı listeleri**: **Blok** gizler son atlama listelerini görev çubuğu ve Başlat menüsü üzerinde gösterilen. Bu ayrıca Ayarlar uygulamasında aynı ada sahip iki durumlu ayarı da devre dışı bırakır. **Yapılandırılmamış** (varsayılan), en son açılan öğelerin listelerini gösterir.
- **Uygulama listesi**: Tüm uygulama listelerini nasıl gösterildiğini seçin. Seçenekleriniz şunlardır:
  - **Kullanıcı tanımlı**: Hiçbir ayar zorlanır. Kullanıcılar, uygulama listesini cihazda nasıl gösterilen seçin.
  - **Daralt**: Tüm uygulamalar listesini gizle.
  - **Daralt ve ayarlar uygulamasında devre dışı bırakma**: Tüm uygulamalar listesini gizle ve devre dışı bırakma **başlangıç menüsünde uygulama listesini göster** ayarlar uygulamasında.
  - **Kaldırır ve ayarlar uygulamasında devre dışı bırakır**: Tüm uygulamalar listesini gizle, tüm uygulamaları düğmeyi kaldırma ve devre dışı **başlangıç menüsünde uygulama listesini göster** ayarlar uygulamasında.
- **Güç düğmesi**: **Blok** gösteren Başlangıç menüsündeki güç düğmesinden gizler. **Yapılandırılmamış** (varsayılan) güç düğmesini gösterir.
- **Kullanıcı kutucuğunu**: **Blok** gelen gösteren Başlangıç menüsündeki kullanıcı kutucuğunda gizler. **Yapılandırılmamış** (varsayılan), kullanıcı kutucuğunda gösterir ve ayrıca aşağıdaki ayarları ayarlar:
  - **Kilit**: **Blok** gizler **kilit** gösteren Başlangıç menüsündeki kullanıcı kutucuğunda seçeneği. **Yapılandırılmamış** gösterir (varsayılan) **kilit** seçeneği.
  - **Oturumu Kapat**: **Blok** gizler **oturumunuzu** gösteren Başlangıç menüsündeki kullanıcı kutucuğunda seçeneği. **Yapılandırılmamış** gösterir (varsayılan) **oturumunuzu** seçeneği.
- **Kapatma**: **Blok** gizler **güncelleştir ve Kapat** ve **kapatma** seçenekleri gösteren Başlangıç menüsündeki güç düğmesinde. **Yapılandırılmamış** (varsayılan), bu seçenekler gösterilmektedir.
- **Uyku**: **Blok** gizler **uyku** gösteren Başlangıç menüsündeki güç düğmesinde seçeneği. **Yapılandırılmamış** (varsayılan), bu seçenek gösterir.
- **Hazırda bekleme**: **Blok** gizler **Hazırda Beklet** gösteren Başlangıç menüsündeki güç düğmesinde seçeneği. **Yapılandırılmamış** (varsayılan), bu seçenek gösterir.
- **Hesap Değiştir**: **Blok** gizler **hesap Değiştir** kullanıcı gösteren gelen döşeme Başlat menüsünde. **Yapılandırılmamış** (varsayılan), bu seçenek gösterir.
- **Yeniden başlatma seçenekleri**:  **Blok** gizler **güncelleştirme ve yeniden başlatma** ve **yeniden** seçenekleri gösteren Başlangıç menüsündeki güç düğmesinde. **Yapılandırılmamış** (varsayılan), bu seçenekler gösterilmektedir.
- **Başlangıç menüsünde belgeler**: Gizleme veya Windows Başlat menüsünde Belgeler klasörünü gösterin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Hiçbir ayar zorlanır. Kısayol gizlemek veya göstermek kullanıcılar'ı seçin.
  - **Gizleme**: Kısayol gizlidir ve ayarlar uygulamasında devre dışı bırakır.
  - **Göster**: Kısayol gösterilir ve ayarlar uygulamasında devre dışı bırakır.
- **Başlangıç menüsünde indirmeler**: Gizleyebilir veya Windows Başlat menüsünde indirilenler klasöründen gösterebilirsiniz. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Hiçbir ayar zorlanır. Kısayol gizlemek veya göstermek kullanıcılar'ı seçin.
  - **Gizleme**: Kısayol gizlidir ve ayarlar uygulamasında devre dışı bırakır.
  - **Göster**: Kısayol gösterilir ve ayarlar uygulamasında devre dışı bırakır.
- **Başlat menüsünde dosya Gezgini**: Gizleme veya Windows Başlat menüsünde dosya Gezgini göster. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Hiçbir ayar zorlanır. Kısayol gizlemek veya göstermek kullanıcılar'ı seçin.
  - **Gizleme**: Kısayol gizlidir ve ayarlar uygulamasında devre dışı bırakır.
  - **Göster**: Kısayol gösterilir ve ayarlar uygulamasında devre dışı bırakır.
- **Başlangıç menüsünde ev grubu**: Gizleyebilir veya Windows Başlat menüsünde ev grubu kısayol gösterebilirsiniz. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Hiçbir ayar zorlanır. Kısayol gizlemek veya göstermek kullanıcılar'ı seçin.
  - **Gizleme**: Kısayol gizlidir ve ayarlar uygulamasında devre dışı bırakır.
  - **Göster**: Kısayol gösterilir ve ayarlar uygulamasında devre dışı bırakır.
- **Başlangıç menüsünde müzik**: Gizleme veya Windows Başlat menüsünde müzik klasörünü gösterin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Hiçbir ayar zorlanır. Kısayol gizlemek veya göstermek kullanıcılar'ı seçin.
  - **Gizleme**: Kısayol gizlidir ve ayarlar uygulamasında devre dışı bırakır.
  - **Göster**: Kısayol gösterilir ve ayarlar uygulamasında devre dışı bırakır.
- **Başlangıç menüsünde ağ**: Windows Başlat menüsünde Ağ'ı göstermek veya gizlemek. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Hiçbir ayar zorlanır. Kısayol gizlemek veya göstermek kullanıcılar'ı seçin.
  - **Gizleme**: Kısayol gizlidir ve ayarlar uygulamasında devre dışı bırakır.
  - **Göster**: Kısayol gösterilir ve ayarlar uygulamasında devre dışı bırakır.
- **Başlangıç menüsünde Kişisel klasörü**: Gizleme veya Windows Başlat menüsünde Kişisel klasörü göster. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Hiçbir ayar zorlanır. Kısayol gizlemek veya göstermek kullanıcılar'ı seçin.
  - **Gizleme**: Kısayol gizlidir ve ayarlar uygulamasında devre dışı bırakır.
  - **Göster**: Kısayol gösterilir ve ayarlar uygulamasında devre dışı bırakır.
- **Başlangıç menüsünde resimler**: Gizleme veya Windows Başlat menüsünde Resimler klasörünü gösterin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Hiçbir ayar zorlanır. Kısayol gizlemek veya göstermek kullanıcılar'ı seçin.
  - **Gizleme**: Kısayol gizlidir ve ayarlar uygulamasında devre dışı bırakır.
  - **Göster**: Kısayol gösterilir ve ayarlar uygulamasında devre dışı bırakır.
- **Başlangıç menüsünde Ayarlar**: Gizleyebilir veya Windows Başlat menüsünde Ayarlar kısayol gösterebilirsiniz. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Hiçbir ayar zorlanır. Kısayol gizlemek veya göstermek kullanıcılar'ı seçin.
  - **Gizleme**: Kısayol gizlidir ve ayarlar uygulamasında devre dışı bırakır.
  - **Göster**: Kısayol gösterilir ve ayarlar uygulamasında devre dışı bırakır.
- **Başlangıç menüsünde videolar**: Gizleme veya Windows Başlat menüsünde videolar klasörünü gösterin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Hiçbir ayar zorlanır. Kısayol gizlemek veya göstermek kullanıcılar'ı seçin.
  - **Gizleme**: Kısayol gizlidir ve ayarlar uygulamasında devre dışı bırakır.
  - **Göster**: Kısayol gösterilir ve ayarlar uygulamasında devre dışı bırakır.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="windows-defender-smart-screen"></a>Windows Defender Smart Screen

- **Microsoft Edge için SmartScreen**: **Gerekli** açma kullanıcıları engellemek ve Windows Defender SmartScreen devre dışı bırakır. **Yapılandırılmamış** (varsayılan) üzerinde Smartscreen'i etkinleştirir. Kullanıcıların kapatmayı engellemek ve kullanıcıların olası tehditlere karşı korunmasına yardımcı olur.

  Microsoft Edge, kullanıcılar olası kimlik avı kuşku verici ve kötü amaçlı yazılımlara karşı korumak için Windows Defender SmartScreen (açık) kullanır.

  [Browser/AllowSmartScreen CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen)

- **Kötü niyetli site erişimi**: **Blok** kullanıcıların Windows Defender SmartScreen Filtresi uyarılarını yoksaymasını öğesinden engeller ve siteye gitmesini engeller. **Yapılandırılmamış** (varsayılan) uyarılarını gözardı et ve siteye devam etmesine izin verir.

  [Tarayıcı/PreventSmartScreenPromptOverride CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverride)

- **Doğrulanmamış dosyayı indirme**: **Blok** kullanıcıların Windows Defender SmartScreen Filtresi uyarılarını yoksaymasını öğesinden engeller ve doğrulanmamış dosyaları indirmesini engelleyin. **Yapılandırılmamış** (varsayılan) uyarılarını gözardı et ve doğrulanmamış dosyaları indirmeye devam etmesine izin verir.

  [Browser/PreventSmartScreenPromptOverrideForFiles CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverrideforfiles)

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="windows-spotlight"></a>Windows Spot

Bu ayarları kullanın [ilke CSP deneyimi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience), desteklenen Windows sürümleri de listelenir.

- **Windows spot**: **Blok** kapatır Windows Spot'u kilit ekranı, Windows ipuçları, Microsoft tüketici özellikleri ve diğer ilgili özellikler. Amacınız, cihazlardan gelen ağ trafiğini en aza indirmek için ise, bu ayar **blok**. **Yapılandırılmamış** (varsayılan), Windows spot özelliklerini ve son kullanıcılar tarafından denetlenen sağlar. Etkin olduğunda, izin vermek veya aşağıdaki ayarları engelle:

  - **Kilit ekranında Windows spot**: **Blok** Windows spot cihaz kilitleme ekranında bilgi göstermesini durdurur. **Yapılandırılmamış** (varsayılan), bu özelliği etkinleştirir.
  - **Windows spot'ta üçüncü taraf önerileri**: **Blok** Microsoft tarafından yayımlanan olmayan içeriği önermesini gelen Windows spot durdurur. **Yapılandırılmamış** (varsayılan), uygulama ve içerik önerilerini kilit ekranı spotlight gibi Windows spot özelliklerini iş ortağı yazılım yayımcıları önerilen uygulamaların başlangıç menüsünde ve Windows ipuçları sağlar.
  - **Tüketici özellikleri**: **Blok** genellikle yalnızca tüketicilere yönelik gibi başlatma önerileri, üyelik bildirimleri, sonrası kutusu deneyimi uygulama yüklemesi, out ve yeniden yönlendirme kutucukları deneyimleri devre dışı bırakır. **Yapılandırılmadı** (varsayılan) ayarı bu özelliklere izin verir.
  - **Windows ipuçları**: **Blok** açılır Windows ipuçları devre dışı bırakır. **Yapılandırılmamış** (varsayılan) göstermek Windows ipuçları sağlar.
  - **İşlem merkezinde Windows spot**: **Blok** gösteren işlem merkezinde Windows spot bildirimleri engeller. **Yapılandırılmamış** (varsayılan), uygulamaları veya Windows üzerinde daha üretken olmanıza yardımcı olmak için özellikleri öneren Eylem Merkezi'nde bildirim gösterebilir.
  - **Windows spot kişiselleştirme**: **Blok** Windows kullanıcıya özelleştirilmiş bir deneyim sağlamak için tanılama verilerini kullanmasını engeller. **Yapılandırılmamış** (varsayılan), tanılama veri ipuçları, kişiselleştirilmiş öneriler sağlamak için kullanılmak üzere Microsoft sağlar ve Windows kullanıcı gereksinimleriniz için uygun hale getirmek sunar.
  - **Windows Karşılama deneyimi**: **Blok** kapatır Windows spot Windows Hoş Geldiniz deneyimi özelliğini. Windows Karşılama deneyimi, güncelleştirmeler ve Windows ve uygulamalarına yapılan değişiklikler olduğunda gösterilmez. **Yapılandırılmamış** (varsayılan), Windows Hoş Geldiniz, yeni veya güncelleştirilmiş özellikleri kullanıcı bilgilerini gösteren deneyimi sağlar.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="windows-defender-antivirus"></a>Windows Defender Virüsten Koruma

Bu ayarları kullanın [defender İlkesi CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender), desteklenen Windows sürümleri de listelenir.

- **Gerçek zamanlı izleme**: **Etkinleştirme** kötü amaçlı yazılım, casus yazılım ve istenmeyen diğer yazılımlar için gerçek zamanlı tarama engeller. **Yapılandırılmamış** (varsayılan), bu özelliği sağlar.
- **Davranış izlemeyi**: **Etkinleştirme** cihazlarda bilinen şüpheli etkinlik düzenlerini Defender denetimi engeller. **Yapılandırılmamış** (varsayılan), Windows Defender davranış izlemeye izin verir.
- **Ağ denetleme Sistemi'ni (NIS)** : NIS, cihazları ağ tabanlı saldırılara karşı korumaya yardımcı olur. Kötü amaçlı trafiği algılamaya ve engellemeye yardımcı olmak için Microsoft Endpoint Protection Center’dan bilinen açıkların imzalarını kullanır.
- **Tüm indirmeleri tara**: Defender’ın İnternet’ten indirilen tüm dosyaları tarayıp taramayacağını denetler.
- **Microsoft web tarayıcılarında yüklenen betikleri tarama**: **Yapılandırılmamış** (varsayılan), Internet Explorer'da kullanılan betikleri taramasına olanak sağlar. **Etkinleştirme** Bu tarama engeller.
- **Defender'a son kullanıcı erişimi**: **Blok** Windows Defender kullanıcı arabiriminin son kullanıcılardan gizler. Tüm Windows Defender bildirimler ayrıca görüntülenmez. **Yapılandırılmamış** (varsayılan), Windows Defender kullanıcı Arabiriminin kullanıcı erişim sağlar. Bu ayar değiştirildiğinde, kullanıcının bilgisayarının bir sonraki yeniden başlatılmasında devreye girer.
- **İmza güncelleştirme aralığı (saat)** : Defender denetleyen 0-24 yeni imza dosyalarını aralığını girin. Seçenekleriniz şunlardır:

  - **Yapılandırılmamış** (varsayılan)
  - **İşaretlemeyin**: Defender'ın yeni imza dosyalarını için denetlemez.
  - **1-24**: `1` saatte denetler `2` iki saatte bir denetler `24` her gün ve benzeri denetler.
- **Dosya ve program etkinliğini İzle**: Defender’ın cihazlarda dosya ve program etkinliğini izlemesine izin verir.
- **Karantinaya alınmış kötü amaçlı yazılım silinmeden önce gün**: İzlemeye devam etmek için el ile girin gün sayısını daha önce etkilenmiş olan cihazları kötü amaçlı yazılım çözülmüş. Gün sayısını ayarlarsanız **0**, kötü amaçlı yazılım karantina klasöründe kalır ve otomatik olarak kaldırılmaz. Ayarlandığında `90`, Karantina öğeleri sistemdeki 90 gün boyunca saklanan ve sonra kaldırılır.
- **Bir tarama sırasında CPU kullanım sınırı**: Taramaların kullanmasına, izin verilen CPU miktarını sınırlamak gelen **1** için **100**.
- **Arşiv dosyalarını tara**: **Etkinleştirme** Defender'ın Zip veya Cab dosyaları gibi arşivlenmiş tarama dosyalarından engeller. **Yapılandırılmamış** (varsayılan), bu tarama izin verir.
- **Gelen posta iletilerini tarama**: **Etkinleştirme** Defender'ın cihaza gelen e-posta iletilerini taramasına izin verir. **Yapılandırılmamış** (varsayılan), e-posta taramasına engeller.
- **Tam tarama sırasında Çıkarılabilir sürücüleri tara**: **Etkinleştirme** çıkarılabilir sürücülerin tam tarama engeller. **Yapılandırılmamış** (varsayılan), ın USB çubukları gibi çıkarılabilir sürücüleri taramasına olanak sağlar.
- **Tam tarama sırasında eşlenmiş ağ sürücülerini tarama**: **Etkinleştirme** eşlenen ağ sürücülerindeki dosyaları taramasına olanak sağlar. **Yapılandırılmamış** (varsayılan), tam tarama engeller. Sürücüdeki dosyalar salt okunur ise, Defender bunların içinde bulduğu kötü amaçlı yazılım kaldırılamıyor.
- **Ağ klasörlerinden açılan dosyaları tara**: **Yapılandırılmamış** (varsayılan), bir UNC yolundan erişilen dosyalar gibi paylaşılan ağ sürücülerindeki dosyaları taramasına olanak sağlar. **Etkinleştirme** Bu tarama engeller. Sürücüdeki dosyalar salt okunur ise, Defender bunların içinde bulduğu kötü amaçlı yazılım kaldırılamıyor.
- **Bulut koruması**: **Yapılandırılmamış** (varsayılan), Microsoft etkin koruma yönettiğiniz cihazlardan kötü amaçlı yazılım etkinliğiyle ilgili bilgi almak hizmeti sağlar. **Etkinleştirme** bu özellik engeller.
- **Örnek göndermeden önce kullanıcılara sor**: Kötü amaçlı dosyaları olup olmadığını daha fazla çözümlenmesi gerekebilecek denetimleri otomatik olarak Microsoft'a gönderilir. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı**
  - **Her zaman sor**
  - **Kişisel veri göndermeden önce sor**
  - **Hiçbir zaman veri gönderme**
  - **Tüm verileri sormadan Gönder**: Verileri otomatik olarak gönderilir

- **Günlük hızlı tarama gerçekleştirilecek saat**: Günlük hızlı tarama Çalıştır saati seçin. **Yapılandırılmamış** günlük tarama çalışmaz. Daha fazla özelleştirme istiyorsanız, yapılandırma **gerçekleştirilecek sistem taraması türü** ayarı.

  [Defender/ScheduleQuickScanTime CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime)

  > [!WARNING]
  > Azure portalında ıntune'da, bu ayar, başarısız durumu gösterebilir. Bu raporlama özelliği ile bir hatadır. Davranışı yeniden oluşturma ve sorun giderme sonra Intune ürün grubu durumu aslında bir başarı onaylandı. Raporlama hata gelecek sürümlerden birinde düzeltilecektir. Zaman çizelgelerini değiştikçe geçerli bir ETA değildir. Bu özellik için herhangi bir güncelleştirme de duyurulur [geliştirme için Microsoft Intune](in-development.md).

- **Gerçekleştirilecek sistem taraması türü**: Tarama, günlük ve tarama çalıştırma süresi düzeyini içeren bir sistem taraması Zamanla. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı**: Cihazda bir sistem taraması zamanla değil. Son kullanıcıların el ile tarama gerekli veya istenen cihazlarında çalıştırabilirsiniz.
  - **Devre dışı**: Tüm sistem cihazı taraması devre dışı bırakır. Cihazları tarar bir iş ortağı virüsten koruma çözümü kullanıyorsanız, bu seçeneği belirleyin.
  - **Hızlı tarama**: Ortak konumlarda arar olabileceği yerlere kötü amaçlı yazılım, kayıt defteri anahtarları gibi kayıtlı ve bilinen Windows Başlangıç klasörleri.
    - **Zamanlanan gün**: Tarama günü seçin.
    - **Zamanlanan saat**: Tarama saati seçin.
  - **Tam tarama**: Ortak konumlarda arar olabileceği yerlere kötü amaçlı yazılım kayıtlı ve ayrıca her dosya ve klasör cihazda tarar.
    - **Zamanlanan gün**: Tarama günü seçin.
    - **Zamanlanan saat**: Tarama saati seçin.

  Bu ayar ile çakışabilir **günlük hızlı tarama gerçekleştirilecek saat** ayarı. Bazı öneriler:

  - Günlük hızlı tarama çalıştıracak şekilde yapılandır **günlük hızlı tarama gerçekleştirilecek saat** ayarı.
  - Günlük hızlı tarama ve haftada bir tam tarama çalıştırmak için ardından yapılandırma **günlük hızlı tarama gerçekleştirilecek saat**. Ayarlama **gerçekleştirilecek sistem taraması türü** gün ve saati ile tam bir tarama için.
  - Yapılandırmayın **günlük hızlı tarama gerçekleştirilecek saat** aynı anda ayarı **gerçekleştirilecek sistem taraması türü** kümesine **hızlı tarama**. Bu ayarlar çakışıyor olabilir ve bir tarama çalışmayabilir.
  - 6'da bir hızlı tarama her Salı günü çalıştırmak için yapılandırma **gerçekleştirilecek sistem taraması türü** ayarı.

  [Defender/ScanParameter CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-scanparameter)  
  [Defender/ScheduleScanDay CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescanday)  
  [Defender/ScheduleScanTime CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescantime)

  > [!WARNING]
  > Azure portalında ıntune'da, bu ayar, başarısız durumu gösterebilir. Bu raporlama özelliği ile bir hatadır. Davranışı yeniden oluşturma ve sorun giderme sonra Intune ürün grubu durumu aslında bir başarı onaylandı. Raporlama hata gelecek sürümlerden birinde düzeltilecektir. Zaman çizelgelerini değiştikçe geçerli bir ETA değildir. Bu özellik için herhangi bir güncelleştirme de duyurulur [geliştirme için Microsoft Intune](in-development.md).

- **İstenmeyebilecek uygulamaları Algıla**: Windows şurada istenmeyebilecek uygulamalar algıladığında, koruma düzeyini seçin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Windows Defender olası istenmeyen uygulamalar koruması devre dışı bırakıldı.
  - **Blok**: Windows Defender, istenmeyebilecek uygulamaları algılar ve algılanan öğelerin engellenir. Bu öğeleri tehditlere birlikte geçmişini gösterir.
  - **Denetim**: Windows Defender, istenmeyebilecek uygulamaları algılar ancak herhangi bir eylemi alır. Windows Defender karşı önlem götürecek uygulamalar hakkında bilgileri gözden geçirebilirsiniz. Örneğin, Windows Defender tarafından Olay Görüntüleyicisi oluşturulan olaylar için arama yapın.

  İstenmeyebilecek uygulamalar hakkında daha fazla bilgi için bkz. [Algıla ve engelle olası uygulamalar istenmeyen](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus).

- **Algılanan kötü amaçlı yazılım tehditlerine eylemleri**: Defender'ın algıladığı her tehdit düzeyinde almak istediğiniz eylemleri seçin: Düşük, Orta, yüksek ve ciddi. Bu mümkün değilse, Windows Defender tehdidi düzeltildikten emin olmak için en iyi seçenek seçer. Seçenekleriniz şunlardır:
  - **Temizle**
  - **Karantina**
  - **Kaldır**
  - **İzin ver**
  - **Kullanıcı tanımlı**
  - **Engelle**

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

### <a name="windows-defender-antivirus-exclusions"></a>Windows Defender Virüsten Koruma Dışlamaları

- **Dosyalar ve taramaların ve gerçek zamanlı korumanın dışında tutulacak klasörler**: Dışlama listesinde **C:\Yol** veya **%ProgramFiles%\Yol\dosyaadı.exe** gibi bir veya birden çok dosya ve klasör ekler. Bu dosya ve klasörler gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.
- **Dosya uzantıları taramaların ve gerçek zamanlı korumanın dışında tutulacak**: Dışlama listesine **jpg** veya **txt** gibi bir veya birden çok dosya uzantısı ekleyin. Bu uzantıya sahip dosyaların hiçbiri gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.
- **Taramaların ve gerçek zamanlı korumanın dışında bırakılacak işlemler**: Dışlama listesine **.exe**, **.com** veya **.scr** türünde bir veya birden çok işlem ekleyin. Bu işlemler gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="next-steps"></a>Sonraki adımlar

Her bir ayara dair ek teknik ayrıntılar ve hangi Windows sürümlerinin desteklendiği hakkında bilgi için bkz. [Windows 10 İlke CSP Başvurusu](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)
