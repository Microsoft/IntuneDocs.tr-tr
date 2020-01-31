---
title: Microsoft Intune - Azure’da Windows 10 cihaz kısıtlama ayarları | Microsoft Docs
description: Windows 10 ve üzeri cihazlarda cihaz kısıtlamaları oluşturmaya yönelik tüm ayarların ve bunların açıklamalarının listesini görüntüleyin. Bu ayarları, ekran görüntülerini, parola gereksinimlerini, bilgi noktası ayarlarını, depodaki uygulamaları, Microsoft Edge tarayıcısı, Microsoft Defender, buluta erişimi, Başlangıç menüsünü ve Microsoft Intune daha fazlasını denetlemek için bir yapılandırma profilinde kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/28/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0dd1ecb5666b8bbb8b26a001be56372d86839f31
ms.sourcegitcommit: b0d683917af83170f85022b270270d8ced8e301c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76812323"
---
# <a name="windows-10-and-newer-device-settings-to-allow-or-restrict-features-using-intune"></a>Intune kullanarak özelliklere izin vermek veya erişimi kısıtlamak için Windows 10 (ve üzeri) cihaz ayarları

Bu makalede, Windows 10 ve daha yeni cihazlarda denetleyebilmeniz için kullanabileceğiniz tüm farklı ayarlar listelenmiştir ve açıklanmaktadır. Mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak bu ayarları, özelliklere izin vermek veya devre dışı bırakmak, parola kuralları ayarlamak, kilit ekranını özelleştirmek, Microsoft Defender 'ı kullanmak ve daha fazlasını yapmak için kullanın.

Bu ayarlar, Intune 'da bir cihaz yapılandırma profiline eklenir ve ardından Windows 10 cihazlarınıza atanır veya dağıtılır.

> [!Note]
> Tüm Windows sürümlerinde tüm seçenekler kullanılamaz. Desteklenen sürümleri görmek için, [CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) 'lere başvurun (başka bir Microsoft Web sitesi açar).

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz yapılandırma profili oluşturma](device-restrictions-configure.md#create-the-profile).

## <a name="app-store"></a>Uygulama Mağazası

Bu ayarlar, desteklenen Windows sürümlerini de listeleyen [ApplicationManagement ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement)'sini kullanır.

- **App Store** (yalnızca mobil): **Block** , son kullanıcıların mobil cihazlarda uygulama deposuna erişmesini önler. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Varsayılan olarak, işletim sistemi son kullanıcıların App Store 'a erişmesine izin verebilir.
- **Store 'dan uygulamaları otomatik güncelleştir**: **blok** , güncelleştirmelerin Microsoft Store otomatik olarak yüklenmesini engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Varsayılan olarak, işletim sistemi Microsoft Store yüklenen uygulamaların otomatik olarak güncelleştirilmesini sağlayabilir.

  [ApplicationManagement/AllowAppStoreAutoUpdate CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate)

- **Güvenilen uygulama yüklemesi**: Microsoft Store olmayan uygulamalar yüklenebiliyorsa, dışarıdan yükleme olarak da bilinen ' yi seçin. Dışarıdan yükleme, Microsoft Store tarafından sertifikasız bir uygulamayı yüklüyor ve çalıştırmıyor. Örneğin, yalnızca şirket içi bir uygulama. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Intune bu ayarı değiştirmez veya güncelleştirmez.
  - **Engelle**: dışarıdan yüklemeyi engeller. Microsoft Store olmayan uygulamalar yüklenemez.
  - **Izin ver**: dışarıdan yüklemeyi sağlar. Microsoft Store olmayan uygulamalar yüklenebilir.
- **Geliştirici kilidi açma**: dışarıdan yüklenen uygulamaların son kullanıcılar tarafından değiştirilmesine izin verme gibi Windows Geliştirici ayarlarına izin verin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Intune bu ayarı değiştirmez veya güncelleştirmez.
  - **Engelle**: Geliştirici modunu ve dışarıdan yükleme uygulamalarını engeller.
  - **Izin ver**: geliştirici modu ve dışarıdan yükleme uygulamalarına izin verir.

  [Cihazınızı geliştirme Için etkinleştirme](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development) bu özellik hakkında daha fazla bilgi içerir.
  
  [ApplicationManagement/AllowAllTrustedApps CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)

- **Paylaşılan kullanıcı uygulaması verileri**: aynı cihazdaki farklı kullanıcılar arasında ve bu uygulamanın diğer örnekleriyle uygulama verilerini paylaşmaya **izin ver** ' i seçin. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Varsayılan olarak işletim sistemi, diğer kullanıcılar ve aynı uygulamanın diğer örnekleri ile veri paylaşmayı önleyebilir.

  [ApplicationManagement/AllowSharedUserAppData CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowshareduserappdata)

- **Yalnızca özel mağazayı kullan**: **izin ver** , bir perakende kataloğu dahil olmak üzere yalnızca uygulamaların özel bir mağazadan indirilmesine ve ortak depodan İndirilme yapmasına izin verir. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Varsayılan olarak işletim sistemi, uygulamaların özel bir mağazadan ve ortak bir mağazadan indirilebilmelerine izin verebilir.

  [ApplicationManagement/RequirePrivateStoreOnly CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

- **Mağaza kaynaklı uygulama başlatma**: **blok** cihazda önceden yüklenmiş olan veya Microsoft Store indirilen tüm uygulamaları devre dışı bırakır. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Varsayılan olarak, işletim sistemi bu uygulamaların açmasına izin verebilir.

  [ApplicationManagement/DisableStoreOriginatedApps CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-disablestoreoriginatedapps)

- **Uygulama verilerini sistem birimine yükler**: **blok** , uygulamaların cihaz sistem biriminde veri depolamasını engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Varsayılan olarak, IŞLETIM sistemi uygulamaların sistem diski biriminde veri depolamasına izin verebilir.

  [ApplicationManagement/Kısıttappdatatosystemvolume CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-restrictappdatatosystemvolume)

- **Uygulamaları sistem sürücüsüne yükleme**: **blok** , uygulamaların cihazdaki sistem sürücüsüne yüklenmesini engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Varsayılan olarak, IŞLETIM sistemi uygulamaların sistem sürücüsüne yüklenmesine izin verebilir.

  [ApplicationManagement/Kısıttapptosystemvolume CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-restrictapptosystemvolume)

- **Game DVR** (yalnızca masaüstü): **blok** , Windows oyun kaydı ve yayını devre dışı bırakır. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Varsayılan olarak, işletim sistemi oyunları kaydetmeye ve yayınlamasını sağlayabilir.

  [ApplicationManagement/AllowGameDVR CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowgamedvr)

- **Yalnızca mağazadan uygulamalar**: Bu ayar, kullanıcılar Microsoft Store dışındaki yerlerden uygulama yüklerken Kullanıcı deneyimini belirler. Seçenekleriniz şunlardır:

  - **Yapılandırılmadı** (varsayılan): Intune bu ayarı değiştirmez veya güncelleştirmez. Varsayılan olarak, işletim sistemi son kullanıcıların diğer ilke ayarlarında tanımlı uygulamalar dahil olmak üzere Microsoft Store dışındaki yerlerden uygulama yüklemelerine izin verebilir.  
  - **Her yerde**: uygulama önerilerini devre dışı bırakır ve kullanıcıların herhangi bir konumdan uygulama yüklemesine izin verir.  
  - **Yalnızca depola**: son kullanıcıları yalnızca Microsoft Store uygulama yüklemeye zorlar.
  - **Öneriler**: Microsoft Store bulunan Web 'den bir uygulama yüklerken, kullanıcılar onu mağazadan indirdikleri öneren bir ileti görür.  
  - **Depoyu tercih et**: Microsoft Store dışındaki yerlerden uygulama yüklediklerinde kullanıcıları uyarır.

  [SmartScreen/Enableappınstallcontrol CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen#smartscreen-enableappinstallcontrol)

- **Yüklemeler üzerinde Kullanıcı denetimi**: **blok** kullanıcıların, dosyaları yüklemek için Dizin girme gibi sistem yöneticileri için genellikle ayrılmış yükleme seçeneklerini değiştirmelerini engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Windows Installer, varsayılan olarak kullanıcıların bu yükleme seçeneklerini değiştirmelerini engelleyebilir ve Windows Installer güvenlik özelliklerinden bazıları atlanır.

  [ApplicationManagement/MSIAllowUserControlOverInstall CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-msiallowusercontroloverinstall)

- **Yükseltilmiş ayrıcalıklarla uygulamalar yükleme**: **blok** , sistem üzerinde herhangi bir program yüklerken yükseltilmiş izinleri kullanmak Windows Installer. Bu ayrıcalıklar tüm programlara genişletilir. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Varsayılan olarak, sistem, bir sistem yöneticisinin dağıtamayacağı veya sunamayacağı programları yüklediğinde geçerli kullanıcının izinlerini uygulayabilir. 

  [ApplicationManagement/MSIAlwaysInstallWithElevatedPrivileges CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-msialwaysinstallwithelevatedprivileges)

- **Başlangıç uygulamaları**: Kullanıcı cihazda oturum açtıktan sonra açılacak uygulamaların listesini girin. Windows uygulamalarının paket aile adları (PFN) için noktalı virgülle ayrılmış bir liste kullandığınızdan emin olun. Bu ilkenin çalışması için, Windows uygulamalarındaki bildirimin bir başlangıç görevi kullanması gerekir.

  [ApplicationManagement/LaunchAppAfterLogOn CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-launchappafterlogon)

## <a name="cellular-and-connectivity"></a>Hücresel ve Bağlantı

Bu ayarlar, desteklenen Windows sürümlerini de listelenecek olan [bağlantı ilkesini](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity) ve [Wi-Fi ilkesi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi) CSP 'leri kullanır.

- [Wi-Fi ilkesi CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi)

- **Hücresel veri kanalı**: son kullanıcıların, hücresel ağa bağlıyken Web 'e göz atma gibi verileri kullanıp kullanmadığı seçin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Intune bu ayarı değiştirmez veya güncelleştirmez. Son kullanıcılar devre dışı bırakabilirsiniz.
  - **Engelle**: hücresel veri kanalına izin verme. Son kullanıcılar açamaz.
  - **Izin ver (düzenlenemez)** : hücresel veri kanalına izin verir. Son kullanıcılar bu uygulamayı kapatamaz.

- **Veri dolaşımı**: **blok** , cihazda hücresel veri dolaşımını önler. **Yapılandırılmadı** (varsayılan), verilere erişirken ağlar arasında dolaşıma izin verir.
- **Hücresel ağ üzerinden VPN**: **blok** cihazın BIR hücresel ağa bağlıyken VPN bağlantılarına erişmesini önler. **Yapılandırılmadı** (varsayılan), VPN 'nin hücresel dahil herhangi bir bağlantı kullanmasına izin verir.
- **Hücresel ağ üzerinden VPN dolaşımı**: **blok** cihazın bir hücresel ağda dolaşımda VPN bağlantılarına erişmesini engeller. **Yapılandırılmadı** (varsayılan), DOLAŞıM sırasında VPN bağlantılarına izin verir.
- **Bağlı cihazlar hizmeti**: **blok** bağlı cihazlar platformu (CDP) bileşenini devre dışı bırakır. CDP, uzak uygulama başlatma, uzak mesajlaşma, uzak uygulama oturumları ve diğer cihazlar arası deneyimleri desteklemek için diğer cihazlara (Bluetooth/LAN veya bulut aracılığıyla) bulma ve bağlantı sağlar. **Yapılandırılmadı** (varsayılan) bağlı cihazlar hizmetine izin verir ve diğer Bluetooth cihazlarına bulmayı ve bağlantıyı sağlar.
- **NFC**: **Block** , yakın alan iletişimleri (NFC) yeteneklerini engelliyor. **Yapılandırılmadı** (varsayılan), KULLANıCıLARıN cihazda NFC özelliklerini etkinleştirmesine ve yapılandırmasına izin verir.
- **Wi-Fi**: **Block** , kullanıcıların cihazdaki Wi-Fi bağlantılarını kullanmasını ve etkinleştirmelerini, yapılandırmalarını ve kullanmasını engeller. **Yapılandırılmadı** (varsayılan) Wi-Fi bağlantılarına izin verir.
- **Wi-Fi etkin noktalarına otomatik olarak bağlan**: **blok** cihazların Wi-Fi etkin noktalarına otomatik olarak bağlanmasını engeller. **Yapılandırılmadı** (varsayılan), cihazların ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmasına ve bağlantı için tüm hüküm ve koşulları otomatik olarak kabul etmesine izin verir.
- **El Ile Wi-Fi yapılandırması**: **blok** cihazların, MDM sunucusu yüklü ağlarının dışında Wi-Fi ' a bağlanmasını engeller. **Yapılandırılmadı** (varsayılan) son kullanıcıların kendi Wi-Fi bağlantısı ağ SSID 'lerini eklemesine ve yapılandırmasına izin verir.
- **Wi-Fi tarama aralığı**: cihazların ne sıklıkta Wi-Fi ağlarını tarayacağını girin. 1 (en sık) ile 500 (en az sık) arasında bir değer girin. Varsayılan değer `0` (sıfır).

### <a name="bluetooth"></a>Bluetooth

Bu ayarlar, [Bluetooth ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth)'sini kullanır; Ayrıca, desteklenen Windows sürümlerini de listeler.

- **Bluetooth**: **blok** kullanıcıların Bluetooth 'u etkinleştirmelerini engeller. **Yapılandırılmamış** (varsayılan) cihazda Bluetooth 'a izin verir.
- **Bluetooth bulunabilirliği**: **blok** cihazın diğer Bluetooth özellikli cihazlar tarafından keşfedilmesini engeller. **Yapılandırılmadı** (varsayılan), kulaklık gibi diğer Bluetooth özellikli cihazların cihazı bulmasını sağlar.
- **Bluetooth önceden eşleme**: **blok** , belirli Bluetooth cihazlarının bir konak cihazla otomatik olarak eşleşmesini önler. **Yapılandırılmadı** (varsayılan) konak cihazla otomatik eşleştirmeye izin verir.
- **Bluetooth reklamcılık**: **blok** cihazın Bluetooth tanıtımları göndermesini engeller. **Yapılandırılmadı** (varsayılan), cihazın Bluetooth tanıtımları göndermesini sağlar.
- **Bluetooth izin verilen hizmetler**: Izin verilen Bluetooth hizmetleri ve profillerinin bir listesini, `{782AFCFC-7CAA-436C-8BF0-78CD0FFBD4AF}`gibi onaltılı dizeler olarak **ekleyin** .

  [Servicesallowedlist kullanım kılavuzu](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#servicesallowedlist-usage-guide) , hizmet listesi hakkında daha fazla bilgi içerir.

## <a name="cloud-and-storage"></a>Bulut ve Depolama

Bu ayarlar, [CSP hesabı ilkesini](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-accounts)kullanır; Ayrıca, desteklenen Windows sürümlerini de listeler.

- **Microsoft hesabı**: **Block** , son kullanıcıların bir Microsoft hesabı cihazla ilişkilendirilmesini engeller. **Yapılandırılmadı** (varsayılan) Microsoft hesabı eklemeye ve kullanılmasına izin verir.
- **Microsoft hesabı dışı**: **Block** , son kullanıcıların kullanıcı arabirimini kullanarak Microsoft olmayan hesaplar eklemesini önler. **Yapılandırılmadı** (varsayılan), kullanıcıların bir Microsoft hesabı ile ilişkilendirilmemiş e-posta hesapları eklemesine olanak sağlar.
- **Microsoft hesabı Için ayarların eşitlenmesi**: **Yapılandırılmadı** (varsayılan), bir Microsoft hesabı ilişkili cihaz ve uygulama ayarlarının cihazlar arasında eşitlenmesine izin verir. **Blok** bu eşitlemeyi engelliyor.
- **Microsoft hesabı oturum açma Yardımcısı**: **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, son kullanıcılar **Microsoft hesabı oturum açma Yardımcısı** (wlidsvc) hizmetini başlatabilir ve durdurabilir. Bu işletim sistemi hizmeti, kullanıcıların Microsoft hesabı oturum açmasına olanak tanır. **Disable** , son kullanıcıların Microsoft oturum açma Yardımcısı hizmetini (wlidsvc) denetlemesini engeller.

## <a name="cloud-printer"></a>Bulut Yazıcı

Bu ayarlar [Enterprisecloudprint ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-enterprisecloudprint)'sini kullanır; Ayrıca, desteklenen Windows sürümlerini de listeler.

- **Yazıcı bulma URL 'si**: bulut yazıcılarını bulmak için URL 'yi girin. Örneğin, şunu girin: `https://cloudprinterdiscovery.contoso.com`.
- **Yazıcı erişim yetkilisi URL 'si**: OAuth belirteçlerini almak için kimlik doğrulama uç noktası URL 'sini girin. Örneğin, şunu girin: `https://azuretenant.contoso.com/adfs`.
- **Azure yerel istemci uygulama GUID 'si**: OAuthAuthority 'den OAuth belirteçleri almaya izin verilen bir ISTEMCI uygulamasının GUID 'sini girin. Örneğin, şunu girin: `E1CF1107-FF90-4228-93BF-26052DD2C714`.
- **Yazdırma hizmeti kaynak URI 'si**: Azure Portal yapılandırılmış yazdırma hizmeti için OAUTH Kaynak URI 'sini girin. Örneğin, şunu girin: `http://MicrosoftEnterpriseCloudPrint/CloudPrint`.
- **Sorgulanacak en fazla yazıcı**: sorgulanmasını istediğiniz en fazla yazıcı sayısını girin. Varsayılan değer `20`.
- **Yazıcı bulma hizmeti kaynak URI 'si**: Azure Portal için yapılandırılmış yazıcı bulma hizmeti OAUTH Kaynak URI 'sini girin. Örneğin, şunu girin: `http://MopriaDiscoveryService/CloudPrint`.

> [!TIP]
> Bir [Windows Server hibrit bulutu](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-overview)oluşturduktan sonra, bu ayarları yapılandırabilir ve ardından Windows cihazlarınıza dağıtabilirsiniz.

## <a name="control-panel-and-settings"></a>Denetim Masası ve Ayarlar

- **Settings App**: **Block** , son kullanıcıların Windows ayarları uygulamasına erişmesini önler. **Yapılandırılmadı** (varsayılan), kullanıcıların cihazda Ayarlar uygulamasını açmasına olanak sağlar.
  - **System**: **Block** , ayarlar uygulamasının sistem alanına erişimi engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
    - **Güç ve uyku ayarlarının değiştirilmesi** (yalnızca masaüstü): **Block** , son kullanıcıların cihazdaki güç ve uyku ayarlarını değiştirmesini engeller. **Yapılandırılmadı** (varsayılan), kullanıcıların güç ve uyku ayarlarını değiştirmesine izin verir.
  - **Cihazlar**: **blok** cihazdaki ayarlar uygulamasının cihazlar alanına erişimi engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
  - **Ağ Internet**: **Block** , cihazdaki ayarlar uygulamasının ağ & Internet alanına erişimi engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
  - **Kişiselleştirme**: **blok** cihazdaki ayarlar uygulamasının kişiselleştirme alanına erişimi engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
  - **Uygulamalar**: **blok** cihazdaki ayarlar uygulamasının uygulamalar alanına erişimi engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
  - **Hesaplar**: **blok** cihazdaki ayarlar uygulamasının hesaplar alanına erişimi engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
  - **Zaman ve dil**: **blok** cihazdaki ayarlar uygulamasının zaman & dil alanına erişimi engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
    - **Sistem saati değişikliği**: **Block** , son kullanıcıların cihazdaki tarih ve saat ayarlarını değiştirmesini engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Kullanıcılar bu ayarları değiştirebilir.
    - **Bölge ayarlarının değiştirilmesi** (yalnızca masaüstü): **Block** , son kullanıcıların cihazdaki bölge ayarlarını değiştirmesini engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Kullanıcılar bu ayarları değiştirebilir.
    - **Dil ayarlarının değiştirilmesi (yalnızca masaüstü)** : **Block** , son kullanıcıların cihazdaki dil ayarlarını değiştirmesini engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Kullanıcılar bu ayarları değiştirebilir.

      [Ayarlar ilkesi CSP 'si](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings)

  - **Oyun**: **Block** , cihazdaki ayarlar uygulamasının oyun alanına erişimi engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
  - **Erişim kolaylığı**: **blok** cihazdaki ayarlar uygulamasının erişim kolaylığı alanına erişimi engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
  - **Gizlilik**: **blok** cihazdaki ayarlar uygulamasının gizlilik alanına erişimi engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
  - **Update ve Security**: **Block** , cihazdaki ayarlar uygulamasının Update & Security alanına erişimi engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.

## <a name="display"></a>Görüntüle

Bu ayarlar, [görüntüleme ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-display)'yi kullanır; Ayrıca, desteklenen Windows sürümlerini de listeler.

GDI DPı ölçeklendirme, DPı kullanmayan uygulamaların, monitör DPı 'si ile uyumlu olmasını sağlar.

- **Uygulamalar IÇIN GDI ölçeklendirmeyi aç**: GDI DPI ölçeklendirme özelliğinin açık olmasını istediğiniz eski uygulamaları **ekleyin** . Örneğin `filename.exe` veya `%ProgramFiles%\Path\Filename.exe` girin.

  Listedeki tüm eski uygulamalar için GDI DPı ölçeklendirme açıktır.

- **Uygulamalar IÇIN GDI ölçeklendirmeyi**kapat: GDI DPI ölçeklendirme özelliğinin kapalı olmasını istediğiniz eski uygulamaları **ekleyin** . Örneğin `filename.exe` veya `%ProgramFiles%\Path\Filename.exe` girin.

  Listedeki tüm eski uygulamalar için GDI DPı ölçeklendirme kapalıdır.

Ayrıca, uygulama listesiyle bir. csv dosyasını **Içeri aktarabilirsiniz** .

## <a name="general"></a>Genel

Bu ayarlar, [deneyim ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience)'yi kullanır; Ayrıca, desteklenen Windows sürümlerini de listeler. 

- **Ekran yakalama** (yalnızca mobil): **Block** , son kullanıcıların cihazda ekran görüntüleri almasını engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
- **Kopyala ve Yapıştır (yalnızca mobil)** : **Block** , son kullanıcıların cihazdaki uygulamalar arasında Kopyala ve Yapıştır kullanmasını engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
- **El ile kayıt kaldırma**: **blok** , son kullanıcıların cihazdaki çalışma alanı denetim masasını kullanarak çalışma alanı hesabını silmesini engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.

  Bu ilke ayarı, bilgisayar Azure AD 'ye katılırsa ve otomatik kayıt etkinse uygulanmaz.

- **El ile kök sertifika yüklemesi** (yalnızca mobil): **blok** , son kullanıcıların kök sertifikaları ve ara Cap sertifikalarını el ile yüklemesini engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
- **Kamera**: **blok** son kullanıcıların cihazdaki kamerayı kullanmasını engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.

  [Kamera CSP 'si](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-camera)

- **OneDrive dosya eşitleme**: **blok** son kullanıcıların dosyaları OneDrive 'a cihazdan eşitlemesini engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
- **Çıkarılabilir depolama birimi**: **blok** , son kullanıcıların cihazla SD kartlar gibi dış depolama cihazlarını kullanmasını engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
- **Coğrafi konum**: **blok** son kullanıcıların cihazdaki konum hizmetlerini açmasını önler. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
- **İnternet paylaşımı**: **engelleme** cihazda İnternet bağlantısı paylaşımını önler. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
- **Telefon sıfırlaması**: **blok** son kullanıcıların cihazda fabrika sıfırlaması gerçekleştirmesini engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
- **USB bağlantısı**: **blok** , cihazdaki bir USB bağlantısı aracılığıyla dış depolama cihazlarına erişimi engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. USB ücretlendirme bu ayardan etkilenmez.
- **Hırsızlık önleme modu** (yalnızca mobil): **Block** son kullanıcıların cihazda antihırsızlık modu tercihini seçmesini önler. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
- **Cortana**: **blok** , cihazda Cortana sesli yardımcısını devre dışı bırakır. Cortana devre dışı bırakıldığında, kullanıcılar hala cihazdaki öğeleri bulmak için arama yapabilir. **Yapılandırılmadı** (varsayılan) Cortana 'ya izin verir.
- **Ses kaydı** (yalnızca mobil): **blok** , son kullanıcıların cihazda cihaz ses kaydedicisi 'ni kullanmasını engeller. **Yapılandırılmadı** (varsayılan), uygulamalar için ses kaydına izin verir.
- **Cihaz adı değişikliği** (yalnızca mobil): **Block** , son kullanıcıların cihaz adını değiştirmesini engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
- **Sağlama paketleri ekleme**: **blok** , cihaza sağlama paketlerini yükleyen çalışma zamanı yapılandırma aracısını engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
- **Sağlama paketlerini kaldır**: **blok** , kaynak sağlama paketlerini cihazdan kaldıran çalışma zamanı yapılandırma aracısını engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
- **Cihaz bulma**: **blok** cihazın diğer cihazlar tarafından bulunmasını engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
- **Görev değiştirici** (yalnızca mobil): **blok** cihazda görev değiştirmeyi engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
- **SIM kart hatası iletişim kutusu** (yalnızca mobil): bir SIM kart algılanmazsa cihazda hata Iletilerinin gösterilmesini **engelleyin** . **Yapılandırılmadı** (varsayılan) hata iletilerini gösterir.
- **Mürekkep çalışma alanı**: kullanıcının mürekkep çalışma alanına erişip erişene olduğunu ve nasıl erişebileceğini seçin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): mürekkep çalışma alanını açar ve kullanıcının bu dosyayı kilit ekranı üzerinde kullanmasına izin verilir.
  - **Kilit ekranında devre dışı**: mürekkep çalışma alanı etkindir ve özellik açıktır. Ancak, Kullanıcı kilit ekranının üzerine erişemez.
  - **Devre dışı**: mürekkep çalışma alanına erişim devre dışı bırakıldı. Özellik kapalı.

  [WindowsInkWorkspace ilkesi CSP 'si](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace)

- **Otomatik yeniden dağıtım**: yönetici haklarına sahip kullanıcıların, cihaz kilidi ekranında **CTRL + Win + R** kullanarak tüm Kullanıcı verilerini ve ayarlarını silmesine **izin ver** ' i seçin. Cihaz otomatik olarak yeniden yapılandırılır ve yönetime yeniden kaydedilir. **Yapılandırılmadı** (varsayılan) ayarı bu özelliği engeller.
- Cihazların **Cihaz kurulumu sırasında ağa bağlanmasını gerektir**: Windows kurulumu sırasında ağ sayfasını geçmeden önce cihazın bir ağa bağlanması için **gerektir** ' i seçin. **Yapılandırılmadı** (varsayılan), kullanıcıların bir ağa bağlı olmasa bile ağ sayfasını geçmemesine izin verir.

  Bu ayar, cihazın bir sonraki temizlenmeden veya sıfırlanışında etkili olur. Diğer Intune yapılandırmaları gibi, yapılandırma ayarlarını almak için cihazın Intune tarafından kaydedilmiş ve yönetilen olması gerekir. Ancak, kaydedildikten ve ilkeleri aldıktan sonra, bir sonraki Windows kurulumu sırasında cihazın sıfırlanması ayarı uygular.

  [TenantLockdown CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)

- **Doğrudan bellek erişimi**: **blok** , Kullanıcı Windows 'a oturum açana kadar tüm etkin takılabilir PCI aşağı akış bağlantı noktaları için doğrudan bellek erişimini (DMA) engeller. **Etkin** (varsayılan) bir Kullanıcı oturum açmamış olsa bile DMA erişimine izin verir.

  [DataProtection/AllowDirectMemoryAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection#dataprotection-allowdirectmemoryaccess)

- **Görev Yöneticisi 'nden Işlemleri Sonlandır**: Bu ayar, yönetici olmayanların Görev Yöneticisi 'nin görevleri sonlandırıp kullanıp kullanamayacağını belirler. **Blok** , standart kullanıcıların (yönetici olmayanlar), Görev Yöneticisi 'ni kullanarak cihazdaki bir işlem veya görevi sonlandırmasını önler. **Yapılandırılmadı** (varsayılan), standart kullanıcıların, Görev Yöneticisi 'ni kullanarak bir işlem veya görevi sonlandıralmasına izin verir.

## <a name="locked-screen-experience"></a>Kilit ekranı deneyimi

- **İşlem merkezi bildirimleri (yalnızca mobil)** : **blok** , cihaz kilitleme ekranında işlem merkezi bildirimlerinin gösterilmesini engeller. **Yapılandırılmadı** (varsayılan), kullanıcıların hangi uygulamaların kilit ekranında bildirimleri göstermesini seçmesine izin verir.

  [AboveLock/AllowActionCenterNotifications CSP](https://msdn.microsoft.com/ie/dn904962(v=vs.94)#AboveLock_AllowActionCenterNotifications)

- **Kilitli ekran resmi URL 'si (yalnızca masaüstü)** : Windows kilit ekranı duvar kağıdı olarak kullanılan jpg, JPEG veya PNG biçiminde bir resmin URL 'sini girin. Örneğin, şunu girin: `https://contoso.com/image.png`. Bu ayar görüntüyü kilitler ve daha sonra değiştirilemez.

  [Kişiselleştirme/Lockscreenımageurl CSP](https://docs.microsoft.com/windows/client-management/mdm/personalization-csp)

- **Kullanıcı tarafından yapılandırılabilir ekran zaman aşımı (yalnızca mobil)** : **izin ver** kullanıcıların ekran zaman aşımını yapılandırmasına izin verir. **Yapılandırılmadı** (varsayılan), kullanıcılara bu seçeneği vermez.

  [DeviceLock/AllowScreenTimeoutWhileLockedUserConfig CSP](https://msdn.microsoft.com/ie/dn904962(v=vs.94)#DeviceLock_AllowScreenTimeoutWhileLockedUserConfig)

- **Kilitli ekranda Cortana** (yalnızca masaüstü): **blok** kullanıcıların, cihaz kilit ekranı üzerinde olduğunda Cortana ile etkileşime geçmesini engeller. **Yapılandırılmadı** (varsayılan) Cortana ile etkileşime izin verir.

  [AboveLock/AllowCortanaAboveLock CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock#abovelock-allowcortanaabovelock)

- **Kilitli ekranda bildirim bildirimleri**: **blok** bildirimlerin cihaz kilitleme ekranında gösterilmesini engeller. **Yapılandırılmadı** (varsayılan) bu bildirimlere izin verir.

  [AboveLock/Allowtoine CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock#abovelock-allowtoasts)

- **Ekran zaman aşımı (yalnızca mobil)** : ekran kilitlemeden ekrana kadar geçen süreyi (saniye cinsinden) ayarlayın. Desteklenen değerler 11-1800 ' dir. Örneğin, bu zaman aşımını 5 dakikaya ayarlamak için `300` girin.

  [DeviceLock/ScreenTimeoutWhileLocked CSP](https://msdn.microsoft.com/ie/dn904962(v=vs.94)#DeviceLock_ScreenTimeoutWhileLocked)

## <a name="messaging"></a>İleti

Bu ayarlar, [ileti ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-messaging)'sini kullanır; Ayrıca, desteklenen Windows sürümlerini de listeler.

- **İleti eşitleme (yalnızca mobil)** : **blok** metin iletilerinin yedeklenmesini ve geri yüklenmesini devre dışı bırakır ve Windows cihazları arasında ileti eşitlemeye engel olmaz. Devre dışı bırakma, bilgilerin kuruluşun denetimi dışındaki sunucularda depolanmasını önlemeye yardımcı olur. **Yapılandırılmadı** (varsayılan), kullanıcıların bu ayarları değiştirmesine ve iletilerini eşitlemesine izin verir.
- **MMS (yalnızca mobil)** : **blok** , cihazda MMS gönderme ve alma işlevini devre dışı bırakır. Kuruluşlar için bu ilkeyi, denetim veya yönetim gereksiniminin parçası olarak cihazlarda MMS 'yi devre dışı bırakmak için kullanın. **Yapılandırılmadı** (varsayılan), MMS gönderme ve alma sağlar.
- **RCS (yalnızca mobil)** : **blok** , cihaza zengin iletişim hizmetleri (RCS) gönderme ve alma işlevini devre dışı bırakır. Kuruluşlar için bu ilkeyi, denetim veya yönetim gereksiniminin parçası olarak cihazlarda RCS 'yi devre dışı bırakmak için kullanın. **Yapılandırılmadı** (varsayılan) RCS 'nin gönderme ve alma yapmasına izin verir.

## <a name="microsoft-edge-browser"></a>Microsoft Edge Tarayıcısı

Bu ayarlar, desteklenen Windows sürümlerini de listeleyen [tarayıcı ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser)'sini kullanır.

### <a name="use-microsoft-edge-kiosk-mode"></a>Microsoft Edge bilgi noktası modunu kullan

Kullanılabilir ayarlar, seçtiğiniz seçeneğe göre değişir. Seçenekleriniz şunlardır:

- **Hayır** (varsayılan): Microsoft Edge bilgi noktası modunda çalışmıyor. Tüm Microsoft Edge ayarları, değişiklik ve yapılandırma için kullanılabilir.
- **Dijital/Etkileşimli imza (tek uygulama bilgi noktası)** : yalnızca Windows 10 tek uygulama kiosks ' de kullanılmak üzere dijital/Etkileşimli imza için geçerli olan Microsoft Edge ayarlarını filtreler. Bir URL tam ekran açmak için bu ayarı seçin ve yalnızca bu Web sitesindeki içeriği gösterin. [Dijital Işaretleri ayarla](https://docs.microsoft.com/windows/configuration/setup-digital-signage) özelliği, bu özellik hakkında daha fazla bilgi sağlar.
- **InPrivate genel göz atma (tek uygulama bilgi noktası)** : Windows 10 tek uygulama kiosları 'nda kullanılmak üzere InPrivate genel göz atma modu için geçerli olan Microsoft Edge ayarlarını filtreler. Microsoft Edge 'in çok sekmeli bir sürümünü çalıştırır.
- **Normal mod (çok uygulama bilgi noktası)** : normal Microsoft Edge bilgi noktası modu için geçerli olan Microsoft Edge ayarlarını filtreler. Tüm göz atma özellikleriyle Microsoft Edge 'in tam bir sürümünü çalıştırır.
- **Genel göz atma (çok uygulama bilgi noktası)** : bir Windows 10 çok uygulama bilgi noktasında genel göz atma için geçerli olan Microsoft Edge ayarlarını filtreler.  Microsoft Edge InPrivate 'ın çok bölgeli bir sürümünü çalıştırır.

> [!TIP]
> Bu seçeneklerin ne yaptığı hakkında daha fazla bilgi için bkz. [Microsoft Edge bilgi noktası modu yapılandırma türleri](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

Bu cihaz kısıtlamaları profili, [Windows bilgi noktası ayarları](kiosk-settings-windows.md)kullanılarak oluşturduğunuz bilgi noktası profiliyle doğrudan ilgilidir. Özetlersek:

1. Cihazı bilgi noktası modunda çalıştırmak için [Windows bilgi noktası ayarları](kiosk-settings-windows.md) profilini oluşturun. Uygulama olarak Microsoft Edge ' i seçin ve bilgi noktası profilinde Microsoft Edge bilgi noktası modunu ayarlayın.
2. Bu makalede açıklanan cihaz kısıtlamaları profilini oluşturun ve Microsoft Edge 'de izin verilen belirli özellikleri ve ayarları yapılandırın. Bilgi noktası profilinizde ([Windows bilgi noktası ayarları](kiosk-settings-windows.md)) seçili olan Microsoft Edge bilgi noktası modu türünü seçtiğinizden emin olun. 

    [Desteklenen bilgi noktası modu ayarları](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-policies-for-kiosk-mode) harika bir kaynaktır.

> [!IMPORTANT] 
> Bu Microsoft Edge profilini, bilgi noktası profilinizle aynı cihazlara ([Windows bilgi noktası ayarları](kiosk-settings-windows.md)) atadığınızdan emin olun.

[ConfigureKioskMode CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-configurekioskmode)

### <a name="start-experience"></a>Deneyim başlangıcı

- **Microsoft Edge 'i Ile Başlat**: Microsoft Edge başladığında hangi sayfaların açılacağını seçin. Seçenekleriniz şunlardır:
  - **Özel başlangıç sayfaları**: `http://www.contoso.com`gibi başlangıç sayfalarını girin. Microsoft Edge, girdiğiniz başlangıç sayfalarını yükler.
  - **Yeni sekme sayfası**: **Yeni sekme URL 'Si** ayarında Microsoft Edge yükleme her şey girilir.
  - **Son oturum sayfası**: Microsoft Edge son oturum sayfasını yükler.
  - **Yerel uygulama ayarlarındaki sayfaları Başlat**: Microsoft Edge, işletim sistemi tarafından tanımlanan varsayılan başlangıç sayfası ile başlar.

- **Kullanıcının başlangıç sayfalarını değiştirmesine Izin ver**: **Evet** (varsayılan), kullanıcıların başlangıç sayfalarını değiştirmesine izin verir. Yöneticiler, Microsoft Edge 'i açtığınızda kullanıcıların varsayılan olarak göreceği başlangıç sayfalarını girmek için `EdgeHomepageUrls` kullanabilir. **Hayır** , kullanıcıların başlangıç sayfalarını değiştirmesini engeller.
- **Yeni sekme sayfasında Web Içeriğine Izin ver**: **Evet** (varsayılan) olarak ayarlandığında, Microsoft Edge **Yeni sekme URL 'si** ayarında girilen URL 'yi açar. **Yeni sekme URL 'si** ayarı boşsa, Microsoft Edge, Microsoft Edge ayarlarında listelenen yeni sekme sayfasını açar. Kullanıcılar bunu değiştirebilir. **Hayır**olarak ayarlandığında, Microsoft Edge boş bir sayfayla yeni bir sekme açar. Kullanıcılar bu değişikliği değiştiremezler.
- **Yeni sekme URL 'si**: yeni sekme sayfasında açılacak URL 'yi girin. Örneğin `https://www.bing.com` veya `https://www.contoso.com` girin.

- **Giriş düğmesi**: Giriş düğmesi seçildiğinde ne olacağını seçin. Seçenekleriniz şunlardır:
  - **Başlangıç sayfaları**: **Microsoft Edge** 'i ayarla ayarında seçtiğiniz seçeneği açar
  - **Yeni sekme sayfası**: **Yeni sekme URL 'si** ayarında girdiğiniz URL 'yi açar.
  - **Giriş düğmesi URL 'si**: açılacak URL 'yi girin. Örneğin `https://www.bing.com` veya `https://www.contoso.com` girin.
  - **Giriş düğmesini Gizle**: giriş düğmesini gizler
- **Kullanıcıların giriş düğmesini değiştirmesine Izin ver**: **Evet** seçeneği, kullanıcıların giriş düğmesini değiştirmesine izin verir. Kullanıcının değişiklikleri, giriş düğmesine tüm yönetici ayarlarını geçersiz kılar. **Hayır** (varsayılan), kullanıcıların giriş düğmesini yöneticinin nasıl yapılandırmasıyla değiştirmesini engeller.
- **Ilk çalıştırma deneyimini göster sayfası (yalnızca mobil)** : **Evet** (varsayılan) Microsoft Edge 'de ilk kullanıma giriş sayfasını gösterir. **Hayır** , Microsoft Edge 'i ilk kez çalıştırdığınızda giriş sayfasının gösterilmesini engeller. Bu özellik, bu sayfayı engellemek için sıfır emisyonlarını yapılandırmasına kayıtlı kuruluşlar gibi kuruluşlara izin verir.
- **Ilk çalıştırma DENEYIMI URL listesi konumu** (yalnızca Windows 10 Mobile): ilk çalıştırma sayfa URL 'SINI içeren XML dosyasına işaret eden URL 'yi girin. Örneğin, şunu girin: `https://www.contoso.com/sites.xml`.

- **Boşta kalma zamanından sonra tarayıcıyı yenile**: 0-1440 dakika içinde tarayıcı yenilenene kadar boşta kalma dakikalarının sayısını girin. Varsayılan değer `5` dakikadır. `0` (sıfır) olarak ayarlandığında tarayıcı, boşta kaldıktan sonra yenilenmez.

  Bu ayar yalnızca [InPrivate genel göz atma (tek uygulama bilgi noktası)](#use-microsoft-edge-kiosk-mode)içinde çalıştırılırken kullanılabilir.

- **Açılır pencerelere Izin ver** (yalnızca masaüstü): **Evet** (varsayılan) Web tarayıcısında açılır pencerelere izin verir. **Hayır** , tarayıcıda açılır pencereleri engeller.
- **Internet Explorer 'a intranet trafiği gönder** (yalnızca masaüstü): **Evet** seçeneği, kullanıcıların Intranet web sitelerini Microsoft Edge yerine Internet Explorer 'da açmasına olanak sağlar. Bu ayar geriye dönük uyumluluk içindir. **Hayır** (varsayılan), kullanıcıların Microsoft Edge kullanmasına izin verir.
- **Kuruluş modu Site listesi konumu** (yalnızca masaüstü): Kurumsal modda açık bir Web siteleri LISTESINI içeren XML dosyasına işaret eden URL 'yi girin. Kullanıcılar bu listeyi değiştiremez. Örneğin, şunu girin: `https://www.contoso.com/sites.xml`.
- **Internet Explorer 'da siteler açılırken ileti**: Microsoft Edge 'i bir site Internet Explorer 11 ' de açılmadan önce bildirim gösterecek şekilde yapılandırmak için bu ayarı kullanın. Seçenekleriniz şunlardır:
  - **İleti gösterme**: işletim sistemi varsayılan davranışı kullanılır, bu durum bir ileti göstermez.
  - **Sitenin Internet Explorer 11 ' de açıldığını belirten Iletiyi göster**: IE 'de siteleri açarken iletiyi göster. IE 'de açık siteler. 
  - **Microsoft Edge 'de siteleri açma seçeneği içeren Iletiyi göster**: siteleri Microsoft Edge 'de açarken iletiyi göster. Bu ileti, kullanıcıların IE yerine Microsoft Edge 'i seçebilmeleri için **Microsoft Edge bağlantısını kullanmaya devam** eder.

  > [!IMPORTANT]
  > Bu ayar, **Kurumsal mod site listesi konumu** ayarını, **Intranet trafiğini Internet Explorer 'a gönder** ayarını veya her iki ayarı da kullanmanızı gerektirir.

- **Microsoft uyumluluk listesine Izin ver**: **Evet** (varsayılan) bir Microsoft Uyumluluk Listesi kullanılmasına izin verir. **Hayır** , Microsoft Edge 'de Microsoft Uyumluluk Listesi 'ni engeller. Microsoft 'un bu listesi, Microsoft Edge 'in bilinen uyumluluk sorunlarına sahip siteleri düzgün şekilde görüntülemesine yardımcı olur.
- **Başlangıç sayfalarını ve yeni sekme sayfasını Önyükle**: **Evet** (varsayılan), bu sayfaları önceden yüklemek için olabilecek işletim sistemi varsayılan davranışını kullanır. Önceden yükleme, Microsoft Edge 'i başlatma ve yeni sekmeler yükleme süresini en aza indirir. **Hayır** , Microsoft Edge 'in başlangıç sayfalarını ve yeni sekme sayfasını önyüklenmesini engeller.
- **Başlangıç sayfaları ve yeni sekme sayfası ön başlatması**: **Evet** (varsayılan), bu sayfaları önceden başlatmak olabilecek işletim sistemi varsayılan davranışını kullanır. Önceden başlatma, Microsoft Edge performansına yardımcı olur ve Microsoft Edge 'i başlatmak için gereken süreyi en aza indirir. **Hayır** , Microsoft Edge 'in başlangıç sayfalarını ve yeni sekme sayfasını başlatmasını önler.

### <a name="favorites-and-search"></a>Sık Kullanılanlar ve arama

- **Sık Kullanılanlar çubuğunu göster**: herhangi bir Microsoft Edge sayfasında Sık Kullanılanlar çubuğunda ne olacağını seçin. Seçenekleriniz şunlardır:
  - **Başlangıç ve yeni sekme sayfalarında**: Microsoft Edge başladığında ve tüm sekme sayfalarında Sık Kullanılanlar çubuğunu gösterir. Son kullanıcılar bu ayarı değiştirebilir.
  - **Tüm sayfalarda**: tüm sayfalarda Sık Kullanılanlar çubuğunu gösterir. Son kullanıcılar bu ayarı değiştiremezler.
  - **Gizli**: tüm sayfalarda Sık Kullanılanlar çubuğunu gizler. Son kullanıcılar bu ayarı değiştiremezler.
- **Sık kullanılanlara değişikliklere Izin ver**: **Evet** (varsayılan), kullanıcıların listeyi değiştirmesine izin veren işletim sistemi varsayılanını kullanır. **Hayır** , son kullanıcıların sık kullanılanlar listesini eklemesini, içeri aktarmayı, sıralamasını veya düzenlemesini engeller.
  - **Sık Kullanılanlar listesi**: Sık Kullanılanlar dosyasına URL 'lerin bir listesini ekleyin. Örneğin, `http://contoso.com/favorites.html`ekleyin.
- **Microsoft tarayıcıları arasında sık kullanılanları Eşitle** (yalnızca masaüstü): **Evet** , Windows 'un Internet Explorer ve Microsoft Edge arasında sık kullanılanları eşitlemesine zorlar. Sık Kullanılanlar için eklemeler, silmeler, değişiklikler ve düzen değişiklikleri, tarayıcılar arasında paylaşılır.  **Hayır** (varsayılan) işletim sistemi varsayılanını kullanır, bu da kullanıcılara tarayıcılar arasında sık kullanılanları eşitleme seçeneği verebilir.
- **Varsayılan arama motoru**: cihazda varsayılan arama altyapısını seçin. Son kullanıcılar bu değeri istediği zaman değiştirebilir. Seçenekleriniz şunlardır:
  - İstemci Microsoft Edge ayarları 'nda arama altyapısı
  - Cıları
  - Google
  - Yahoo!
  - Özel değer: **OpenSearch XML URL 'Si**içinde, kısa adı ve arama altyapısının URL 'sini IÇEREN BIR https URL 'sini en düşük düzeyde girin. Örneğin, şunu girin: `https://www.contoso.com/opensearch.xml`.
- **Arama önerilerini göster**: **Evet** (varsayılan) arama motorunuzun, adres çubuğuna arama ifadeleri yazarken site önermesine izin verir. **Hayır** bu özelliği engeller.
- **Arama altyapısında değişikliklere Izin ver**: **Evet** (varsayılan), kullanıcıların yeni arama motorları eklemesine veya Microsoft Edge 'de varsayılan arama altyapısını değiştirmesine izin verir. Kullanıcıların arama altyapısını özelleştirmesini engellemek için **Hayır** ' ı seçin.

  Bu ayar yalnızca [normal modda (çok uygulama bilgi noktası)](#use-microsoft-edge-kiosk-mode)çalışırken kullanılabilir.

### <a name="privacy-and-security"></a>Gizlilik ve güvenlik

- **InPrivate gözatmaya Izin ver**: **Evet** (varsayılan), Microsoft Edge 'de InPrivate gözatmaya izin verir. Tüm InPrivate sekmeleri kapatıldıktan sonra Microsoft Edge, tarama verilerini cihazdan siler. **Hayır** , son kullanıcıların InPrivate Gözatma oturumlarını açmasını önler.
- **Gözatma geçmişini kaydet**: **Evet** (varsayılan) gözatma geçmişinin Microsoft Edge 'de kaydedilmesine izin verin. **Hayır** , gözatma geçmişinin kaydedilmesini engeller.
- **Çıkışta tarama verilerini temizle** (yalnızca masaüstü): **Evet** , Kullanıcı Microsoft Edge 'den çıktığında geçmişi temizler ve verilere göz atar. **Hayır** (varsayılan) işletim sistemi varsayılanını kullanır, bu da tarama verilerini önbelleğe alabilir.
- **Tarayıcı ayarlarını kullanıcının cihazları arasında Eşitle**: tarayıcı ayarlarını cihazlar arasında nasıl eşitlemek istediğinizi seçin. Seçenekleriniz şunlardır:
  - **Izin ver**: kullanıcıların cihazları arasında Microsoft Edge tarayıcı ayarlarının eşitlenmesine izin ver
  - **Kullanıcı geçersiz kılmayı engelle ve Etkinleştir**: Microsoft Edge tarayıcı ayarlarının kullanıcı cihazları arasında eşitlenmesini engelleyin. Kullanıcılar bu ayarı geçersiz kılabilir.
  - **Engelle**: Kullanıcı cihazları arasında Microsoft Edge tarayıcı ayarı eşitlemesini engelleyin. Kullanıcılar bu ayarı geçersiz kılamaz.

"Kullanıcı geçersiz kılmayı engelle" seçildiğinde, kullanıcı yönetici atamasını geçersiz kılabilir.

- **Parola Yöneticisi 'Ne Izin ver**: **Evet** (varsayılan), Microsoft Edge 'In otomatik olarak parola yöneticisini kullanmasına izin verir. Bu, kullanıcıların cihazdaki parolaları kaydetmesine ve yönetmesine olanak tanır. **Hayır** , Microsoft Edge 'In parola Yöneticisi 'ni kullanmasını engeller.
- **Tanımlama bilgileri**: Web tarayıcısında tanımlama bilgilerinin nasıl işlendiğini seçin. Seçenekleriniz şunlardır:
  - **Izin ver**: tanımlama bilgileri cihazda depolanıyor.
  - **Tüm tanımlama bilgilerini engelle**: tanımlama bilgileri cihazda depolanmaz.
  - **Yalnızca üçüncü taraf tanımlama bilgilerini engelle**: üçüncü taraf veya iş ortağı tanımlama bilgileri cihazda depolanmaz.
- **Formlarda otomatik doldurmaya Izin ver**: **Evet** (varsayılan), kullanıcıların tarayıcıdaki otomatik tamamlama ayarlarını değiştirmesine ve form alanlarını otomatik olarak doldurmasına izin verir. **Hayır** özelliği, Microsoft Edge 'de otomatik doldurma özelliğini devre dışı bırakır.
- **Do-Not-Track üst bilgileri gönder**: **Evet** , izleme bilgisi isteyen web sitelerine Do-Not-Track üst bilgilerini gönderir (önerilir). **Hayır** (varsayılan), Web sitelerinin kullanıcıyı izlemesine izin veren üst bilgileri göndermez. Kullanıcı yapılandırabilir.
- **WebRTC localhost IP adresini göster**: **Evet** (varsayılan), bu protokol kullanılarak telefon ARAMALARı yapıldığında kullanıcıların localhost IP adresinin gösterilmesini sağlar. **Hayır** , KULLANıCıLARıN localhost IP adresinin gösterilmesini engeller. 
- **Canlı kutucuk veri toplamaya Izin ver**: **Evet** (varsayılan), Microsoft Edge 'In Başlat menüsüne sabitlenmiş canlı kutucuktan bilgi toplamasına izin verir. **Hayır** , kullanıcılara sınırlı bir deneyim sağlayabilen bu bilgilerin toplanmasını engeller.
- **Kullanıcı sertifika hatalarını geçersiz kılabilir**: **Evet** (varsayılan), kullanıcıların Güvenli Yuva Katmanı/Aktarım katmanı GÜVENLIĞI (SSL/TLS) hataları olan Web sitelerine erişmesine izin verir. **Hayır** (Artırılmış güvenlik için önerilir), kullanıcıların Web sitelerine SSL veya TLS hatalarıyla erişmesini önler.

### <a name="additional"></a>Fazladan

- **Microsoft Edge tarayıcısına Izin ver** (yalnızca mobil): **Evet** (varsayılan) mobil cihazda Microsoft Edge Web tarayıcısının kullanılmasına izin verir. **Hayır** , cihazda Microsoft Edge kullanımını engeller. **Hayır**' ı seçerseniz, diğer tek ayarlar yalnızca masaüstü için geçerlidir.
- **Adres çubuğu açılır listesine Izin ver**: **Evet** (varsayılan), Microsoft Edge 'in adres çubuğu açılır listesini öneriler listesiyle göstermesini sağlar. **Hayır** , Microsoft Edge 'in, yazarken açılan listede öneriler listesi göstermesini engeller. **Hayır**olarak ayarlandığında, şunları yapabilirsiniz:
  - Microsoft Edge ve Microsoft Hizmetleri arasındaki ağ bant genişliğini en aza indirmeye yardımcı olun.
  - Microsoft Edge > ayarlarını **Yazarken arama ve site önerilerini göster ' i** devre dışı bırakın.
- **Tam ekran moduna Izin ver**: **Evet** (varsayılan), Microsoft Edge 'in yalnızca Web Içeriğini gösteren ve Microsoft Edge Kullanıcı arabirimini gizleyen tam ekran modunu kullanmasına izin verir. **Hayır** , Microsoft Edge 'de tam ekran modunu engeller.
- **Bayrak hakkında Izin ver sayfası**: **Evet** (varsayılan) işletim sistemi varsayılanını kullanır ve bu, `about:flags` sayfasına erişime izin verebilir. `about:flags` sayfası kullanıcıların geliştirici ayarlarını değiştirmesine ve deneysel özellikleri etkinleştirmesine olanak sağlar. **Hayır** , son kullanıcıların Microsoft Edge 'de `about:flags` sayfasına erişmesini önler.
- **Geliştirici araçlarına Izin ver**: **Evet** (varsayılan), kullanıcıların varsayılan olarak Web sayfalarını derlemek ve hatalarını ayıklamak için F12 geliştirici araçlarını kullanmasına izin verir. **Hayır** , son kullanıcıların F12 geliştirici araçlarını kullanmasını önler.
- **JavaScript 'e Izin ver**: **Evet** (varsayılan) JavaScript gibi betiklerin Microsoft Edge tarayıcısında çalışmasına izin verir. **Hayır** , tarayıcıda Java betikleri çalıştırılmasını önler.
- **Kullanıcı Uzantıları yükleyebilir**: **Evet** (varsayılan) son kullanıcıların cihaza Microsoft Edge uzantıları yüklemesine izin verir. **Hayır** , yüklemeyi engeller.
- **Geliştirici uzantılarının dışarıdan yüklenmesine Izin ver**: **Evet** (varsayılan), dışarıdan yükleme izni olabilen işletim sistemi varsayılanını kullanır. Dışarıdan yükleme, doğrulanmamış uzantıları yükleyip çalıştırır. **Hayır** özelliği, **yükleme uzantıları** özelliğini kullanarak Microsoft Edge dışarıdan dışarıdan yüklemeye engel olur. PowerShell gibi diğer yollarla dışarıdan yükleme uzantılarının engellemez.
- **Gerekli uzantılar**: Microsoft Edge 'de son kullanıcılar tarafından kapatılanamaz uzantıları seçin. Paket aile adlarını girin ve **Ekle**' yi seçin. [Uygulama BAŞıNA VPN için bir paket aile adı (PFN) bulma](https://docs.microsoft.com/configmgr/protect/deploy-use/find-a-pfn-for-per-app-vpn) bazı kılavuzluk sağlar.

  Ayrıca paket aile adlarını içeren bir CSV dosyasını **Içeri aktarabilirsiniz** . Ya da, girdiğiniz paket aile adlarını **dışarı aktarın** .

## <a name="network-proxy"></a>Ağ proxy’si

Bu ayarlar, desteklenen Windows sürümlerini de listeleyen [Networkproxy ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)'sini kullanır.

- **Proxy ayarlarını otomatik olarak algıla**: **Engelle** , cihazın otomatik olarak bir proxy otomatik yapılandırma (PAC) betiğini algılamasını devre dışı bırakır. **Yapılandırılmadı** (varsayılan), bu özelliği sunar. Etkinleştirildiğinde, cihaz bir PAC betiğinin yolunu bulmaya çalışır.
- **Proxy betiği kullan**: proxy sunucusunu YAPıLANDıRMAK için Pac betiğinizin yolunu girmeye **izin ver** ' i seçin. **Yapılandırılmadı** (varsayılan), bir PAC BETIĞININ URL 'sini girmenize izin vermez.
  - **Kurulum komut dosyası adresi URL 'si**: proxy sunucusunu yapılandırmak için kullanmak istediğiniz Pac BETIĞININ URL 'sini girin.
- **El ile proxy sunucusu kullan**: bir proxy sunucusunun adını veya IP ADRESINI ve TCP bağlantı noktası numarasını el ile girmek Için **izin ver** ' i seçin. **Yapılandırılmadı** (varsayılan), bir proxy sunucusunun ayrıntılarını el ile girmenize izin vermez.
  - **Adres**: proxy sunucusunun adını veya IP adresini girin.
  - **Bağlantı noktası numarası**: proxy sunucunuzun bağlantı noktası numarasını girin.
  - **Proxy özel durumları**: proxy sunucusunu kullanmamalıdır gereken URL 'leri girin. Her birini ayırmak için noktalı virgül kullanın.
  - **Yerel adres için proxy sunucusunu atla**: **Yapılandırılmadı** (varsayılan), intranetinizdeki yerel adresler için bir proxy sunucu kullanılmasını önler. **Izin ver** , yerel adresler için bir proxy sunucu kullanır.

## <a name="password"></a>istemcisiyle yönetilen bir cihaz için)

Bu ayarlar, desteklenen Windows sürümlerini de listeleyen [DeviceLock ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock)'sini kullanır.

- **Parola**: son kullanıcının cihaza erişmek için bir parola girmesini **gerektir** . **Yapılandırılmadı** (varsayılan), bir parola olmadan cihaza erişime izin verir. Yalnızca yerel hesaplar için geçerlidir. Etki alanı hesabı parolaları Active Directory (AD) ve Azure AD tarafından yapılandırılmış olarak kalır.

  - **Gerekli parola türü**: parola türünü seçin. Seçenekleriniz şunlardır:
    - **Yapılandırılmadı**: parola, sayı ve harf içerebilir.
    - **Sayısal**: parola yalnızca sayı olmalıdır.
    - **Alfasayısal**: parola sayıların ve harflerin karışımı olmalıdır.
  - **Minimum parola uzunluğu**: 4-16 adresinden gereken minimum sayı veya karakterleri girin. Örneğin, parola uzunluğu için en az altı karakter gerektiren `6` girin.
  
    > [!IMPORTANT]
    > Parola gereksinimi bir Windows masaüstünde değiştirildiğinde, bu cihaz boşta durumundan etkin 'e geçtiğinde, kullanıcılar bir sonraki oturum açışlarında etkilenir. Gereksinimi karşılayan parolalara sahip olan kullanıcılar parolalarını değiştirmelerini de istenir.
    
  - **Cihaz silinmeden önceki oturum açma hatalarının sayısı**: Cihaz silinmeden önce izin verilen kimlik doğrulama hatalarının sayısını 11 ' e kadar girin. Girdiğiniz geçerli sayı sürüme bağlıdır. [DeviceLock/MaxDevicePasswordFailedAttempts CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-maxdevicepasswordfailedattempts) desteklenen değerleri listeler. `0` (sıfır) cihaz temizleme işlevini devre dışı bırakabilir.

    Bu ayarın Ayrıca sürüme bağlı olarak farklı etkileri vardır. Bu ayar hakkında ayrıntılı bilgi için bkz. [DeviceLock/MaxDevicePasswordFailedAttempts CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-maxdevicepasswordfailedattempts).

  - **Ekran kilitlenmeden önce geçen işlem yapılmayan dakika sayısı**: ekran kilitlenmeden önce cihazın boşta kalması gereken sürenin uzunluğunu girin.
  - **Parola kullanım süresi (gün)** : cihaz parolasının değiştirilme tarihi olan 1-365 ' dan gün cinsinden süre uzunluğunu girin. Örneğin, 90 gün sonra parolayı sona erdirmek için `90` girin.
  - **Önceki parolaların yeniden kullanılmasını engelle**: daha önce kullanılan ve 1-24 'den kullanılamayan parolaların sayısını girin. Örneğin, kullanıcıların geçerli parolasına veya önceki dört parolalarından birine yeni bir parola ayarlayamaması için `5` girin.
  - **Cihaz boşta durumundan çıktığında parola iste** (Mobile ve holographic): **gerektir** ' i seçin, böylece kullanıcılar, boşta kaldıktan sonra cihazın kilidini açmak için bir parola girmelidir. **Yapılandırılmadı** (varsayılan) cihaz boşta durumundan çıktığında PIN veya parola gerektirmez.
  - **Basit parolalar**: kullanıcıların `1234` veya `1111`gibi basit parolalar oluşturmaması için **Engelle** olarak ayarlayın. Kullanıcıların `1234` veya `1111`gibi parolalar oluşturmalarına izin vermek için **Yapılandırılmadı** (varsayılan) olarak ayarlayın. Bu ayar, Windows resimli parolalarının kullanımına izin verir veya bunu engeller.
- **Aayarlaması sırasında otomatik şifreleme**: **blok** , cihaz Azure AD 'ye katılmış olduğunda otomatik BitLocker cihaz şifrelemesini engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. [BitLocker cihaz şifrelemesi](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption)hakkında daha fazla bilgi.

  [Güvenlik/koruyucu Tautomaticdeviceencryptionforazureadjoineddevices CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-preventautomaticdeviceencryptionforazureadjoineddevices)

- **Federal bilgi Işleme standardı (FIPS) ilkesi**: **izin ver** , şifreleme, karma ve imzalama için ABD devlet standardı olan Federal BILGI işleme standardı (FIPS) ilkesini kullanır. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. İşletim sistemi varsayılanı FIPS kullanamaz.

  [Şifreleme/AllowFipsAlgorithmPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-cryptography#cryptography-allowfipsalgorithmpolicy)

- **Windows Hello cihaz kimlik doğrulaması**: kullanıcıların bir Windows 10 bilgisayarında oturum açmak için telefon, uygunluk bandı veya IoT cihazı gibi bir Windows Hello yardımcı cihazı kullanmasına **izin verin** . **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. İşletim sistemi varsayılanı, Windows Hello yardımcı cihazlarının Windows ile kimlik doğrulamasından engel olabilir.

  [Authentication/AllowSecondaryAuthenticationDevice CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowsecondaryauthenticationdevice)

- **Web 'de oturum açma**: ADFS olmayan (Active Directory Federasyon Hizmetleri (AD FS)) Federasyon sağlayıcıları için SECURITY ASSERTION MARKUP Language (SAML) gibi Windows oturum açma desteği sunar. SAML, Web tarayıcıları çoklu oturum açma (SSO) deneyimi sağlayan güvenli belirteçler kullanır. Seçenekleriniz şunlardır:

  - **Yapılandırılmadı** (varsayılan): Intune bu ayarı değiştirmez veya güncelleştirmez.
  - **Etkin**: Web kimlik bilgisi sağlayıcısı oturum açma için etkinleştirildi.
  - **Devre dışı**: Web kimlik bilgisi sağlayıcısı oturum açma için devre dışı bırakıldı.

  [Kimlik doğrulama/Enablewebsignın CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-enablewebsignin)

- **Tercih edilen Azure AD kiracı etki alanı**: Azure AD kuruluşunuzda mevcut bir etki alanı adı girin. Bu etki alanındaki kullanıcılar oturum açtığında, etki alanı adını yazmak zorunda kalmaz. Örneğin, şunu girin: `contoso.com`. `contoso.com` etki alanındaki kullanıcılar, `abby@contoso.com`yerine `abby`gibi kullanıcı adlarını kullanarak oturum açabilir.

  [Authentication/PreferredAadTenantDomainName CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-preferredaadtenantdomainname)

## <a name="per-app-privacy-exceptions"></a>Uygulama başına gizlilik özel durumları

"Varsayılan gizlilik" bölümünde tanımladıklarınızdan farklı bir gizlilik davranışına sahip olması gereken uygulamalar ekleyebilirsiniz.

- **Paket adı**: uygulama paketi aile adı.
- **Uygulama adı**: uygulamanın adı.

### <a name="exceptions"></a>Özel Durumlar

- **Hesap bilgileri**: Bu uygulamanın kullanıcı adına, resmine ve diğer kişi bilgilerine erişip erişemeyeceğini tanımlayın.
- **Arka plan uygulamaları**: Bu uygulamanın arka planda çalıştırılıp çalıştırılamayacağını tanımlayın.
- **Takvim**: Bu uygulamanın takvime erişip erişemeyeceğini tanımlayın.
- **Arama geçmişi**: Bu uygulamanın çağrı geçmişime erişip erişemeyeceğini tanımlayın.
- **Kamera**: Bu uygulamanın kameraya erişip erişemeyeceğini tanımlayın.
- **Kişiler**: Bu uygulamanın kişilere erişip erişemeyeceğini tanımlayın.
- **E-posta**: Bu uygulamanın e-postaya erişip erişemeyeceğini tanımlayın.
- **Konum**: Bu uygulamanın konum bilgilerine erişip erişemeyeceğini tanımlayın.
- **Mesajlaşma**: Bu uygulamanın metın veya MMS iletilerini okuyup okuyamayacağını veya gönderemeyeceğini tanımlayın.
- **Mikrofon**: Bu uygulamanın mikrofonu kullanıp kullanamayacağını tanımlayın.
- **Hareket**: Bu uygulamanın cihaz hareket bilgilerine erişip erişemeyeceğini tanımlayın.
- **Bildirimler**: Bu uygulamanın bildirimlere erişip erişemeyeceğini tanımlayın.
- **Telefon**: Bu uygulamanın telefona erişip erişemeyeceğini tanımlayın.
- **Radyolar**: bazı uygulamalar, veri göndermek ve almak ve Bu radyoların açık veya kapalı olması için cihazınızda radyoları (örneğin Bluetooth) kullanır. Bu uygulamanın bu radyoları denetleyip denetleyemeyeceğini tanımlayın.
- **Görevler**: Bu uygulamanın görevlerinize erişip erişemeyeceğini tanımlayın.
- **Güvenilen cihazlar**: Bu uygulamanın Güvenilen cihazları kullanıp kullanseçemediğini seçin. Güvenilen cihazlar, zaten bağlı olduğunuz donanımdır veya cihazla birlikte gelen donanımlardır. Örneğin, güvenilir cihazlar olarak televizyonlar, projektörler vb. kullanın.
- **Geri bildirim ve tanılama**: Bu uygulamanın tanılama bilgilerine erişip erişemeyeceğini tanımlayın.
- **Cihazlarla Eşitle**: Bu uygulamanın, cihazla açıkça eşleşmeyen kablosuz cihazlarla otomatik olarak bilgi paylaşıp eşitleyip eşitleyebileceğini seçin.

## <a name="personalization"></a>Kişiselleştirme

Bu ayarlar, desteklenen Windows sürümlerini de listeleyen [Kişiselleştirme ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/personalization-csp)'sini kullanır.

- **Masaüstü arka plan resmi URL 'si (yalnızca masaüstü)** : Windows masaüstü duvar kağıdı olarak kullanmak istediğiniz. jpg,. jpeg veya. png biçimindeki bir resmin URL 'sini girin. Kullanıcılar bu resmi değiştiremez. Örneğin, şunu girin: `https://contoso.com/logo.png`.

## <a name="printer"></a>Yazıcıda

- **Yazıcılar**: eklenen yerel yazıcıların listesi.
- **Varsayılan yazıcı**: varsayılan yazıcıyı ayarlayın.
- **Yeni yazıcı eklemek Için Kullanıcı erişimi**: yerel yazıcıların kullanımına izin verin veya bunu engelleyin.

## <a name="privacy"></a>Gizlilik

Bu ayarlar, desteklenen Windows sürümlerini de listeleyen [Gizlilik ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy)'sini kullanır.

- **Giriş kişiselleştirme**: **blok** , dikte Için ses kullanımını ve Cortana ile Microsoft bulut tabanlı konuşma tanımayı kullanan diğer uygulamalarla konuşmasını önler. Devre dışıdır ve kullanıcılar, ayarları kullanarak çevrimiçi konuşma tanımayı etkinleştiremez. **Yapılandırılmadı** (varsayılan) kullanıcıların seçmesini sağlar. Bu hizmetlere izin verirseniz, Microsoft, hizmeti geliştirmek için ses verileri toplayabilir.
- **Eşleştirme ve gizlilik Kullanıcı onay Istemlerini otomatik olarak kabul**et: **izin ver** ' i seçin. bu nedenle Windows, uygulamaları çalıştırırken eşleştirmeyi ve gizlilik izin iletilerini otomatik olarak kabul edebilir **Yapılandırılmadı** (varsayılan), uygulamalar açılırken eşleştirme ve gizlilik Kullanıcı onay penceresinin otomatik kabulüne engel olur.
- **Kullanıcı etkinliklerini Yayımla**: **blok** , paylaşılan deneyimleri ve etkinlik akışındaki son kullanılan kaynakları bulmayı engeller. **Yapılandırılmadı** (varsayılan), uygulamaların son kullanıcı etkinliklerini yayımlayabilmesi için bu özelliği sunar.
- **Yalnızca yerel etkinlikler**: **blok** , paylaşılan deneyimleri ve yalnızca yerel etkinliğe bağlı olarak görev değiştiricisinde son kullanılan kaynakların bulunmasını engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.

Cihazdaki tüm uygulamaların erişebileceği bilgileri yapılandırabilirsiniz. Ayrıca, **uygulama başına gizlilik özel durumlarını**kullanarak uygulama temelinde özel durumlar tanımlayın.

### <a name="exceptions"></a>Özel Durumlar

- **Hesap bilgileri**: Bu uygulamanın kullanıcı adına, resmine ve diğer kişi bilgilerine erişip erişemeyeceğini tanımlayın.
- **Arka plan uygulamaları**: Bu uygulamanın arka planda çalıştırılıp çalıştırılamayacağını tanımlayın.
- **Takvim**: Bu uygulamanın takvime erişip erişemeyeceğini tanımlayın.
- **Arama geçmişi**: Bu uygulamanın çağrı geçmişime erişip erişemeyeceğini tanımlayın.
- **Kamera**: Bu uygulamanın kameraya erişip erişemeyeceğini tanımlayın.
- **Kişiler**: Bu uygulamanın kişilere erişip erişemeyeceğini tanımlayın.
- **E-posta**: Bu uygulamanın e-postaya erişip erişemeyeceğini tanımlayın.
- **Konum**: Bu uygulamanın konum bilgilerine erişip erişemeyeceğini tanımlayın.
- **Mesajlaşma**: Bu uygulamanın metın veya MMS iletilerini okuyup okuyamayacağını veya gönderemeyeceğini tanımlayın.
- **Mikrofon**: Bu uygulamanın mikrofonu kullanıp kullanamayacağını tanımlayın.
- **Hareket**: Bu uygulamanın cihaz hareket bilgilerine erişip erişemeyeceğini tanımlayın.
- **Bildirimler**: Bu uygulamanın bildirimlere erişip erişemeyeceğini tanımlayın.
- **Telefon**: Bu uygulamanın telefona erişip erişemeyeceğini tanımlayın.
- **Radyolar**: bazı uygulamalar, veri göndermek ve almak ve Bu radyoların açık veya kapalı olması için cihazınızda radyoları (örneğin Bluetooth) kullanır. Bu uygulamanın bu radyoları denetleyip denetleyemeyeceğini tanımlayın.
- **Görevler**: Bu uygulamanın görevlerinize erişip erişemeyeceğini tanımlayın.
- **Güvenilen cihazlar**: Bu uygulamanın Güvenilen cihazları kullanıp kullanseçemediğini seçin. Güvenilen cihazlar, zaten bağlı olduğunuz donanımdır veya cihazla birlikte gelen donanımlardır. Örneğin, güvenilir cihazlar olarak televizyonlar, projektörler vb. kullanın.
- **Geri bildirim ve tanılama**: Bu uygulamanın tanılama bilgilerine erişip erişe, bu uygulamayı seçin.
- **Cihazlarla eşitle** - Bu uygulamanın bu PC, tablet veya telefonla açıkça eşleştirilmemiş kablosuz cihazlarla otomatik olarak bilgi paylaşma ve eşitleme işlemleri yapıp yapamayacağını tanımlayın.

## <a name="projection"></a>Projeksiyon

Bu ayarlar, desteklenen Windows sürümlerini de listeleyen [kablolu Lessdisplay Ilke CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wirelessdisplay)'sini kullanır.

- **Kablosuz Görüntü alıcılarından Kullanıcı girişi**: **engelleme** , kablosuz görüntü alıcılarından Kullanıcı girişini engeller. **Yapılandırılmadı** (varsayılan), kablosuz bir ekran 'ın, kaynak cihaza klavye, fare, kalem ve dokunmatik giriş göndermesini sağlar.
- **Bu bilgisayara yansıtma**: **blok** , diğer cihazların projeksiyon için cihazı bulmasını önler. **Yapılandırılmadı** (varsayılan), cihazın bulunabilir olmasını sağlar ve kilit ekranının üzerinde cihaza proje verebilir.
- **Eşleştirme IÇIN PIN gerektir**: bir projeksiyon cihazına bağlanırken her zaman PIN için **istem iste ' yi seçin.** **Yapılandırılmadı** (varsayılan), cihazı bir projeksiyon cihazına EŞLEŞTIRMEK için PIN gerektirmez.

## <a name="reporting-and-telemetry"></a>Raporlama ve telemetri

- **Kullanım verilerini paylaşma**: gönderilen tanılama verilerinin düzeyini seçin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı**: hiçbir veri paylaşılmıyor.
  - **Güvenlik**: bağlı kullanıcı deneyimi ve telemetri bileşen ayarları, kötü amaçlı yazılım kaldırma aracı ve Microsoft Defender hakkındaki veriler de dahil olmak üzere Windows 'un daha güvenli kalmasına yardımcı olmak için gereken bilgiler.
  - **Temel**: kalite ile ilgili verileri, uygulama uyumluluğunu, uygulama kullanımı verilerini ve güvenlik düzeyinden verileri içeren temel cihaz bilgileri.
  - **Gelişmiş**: Windows, Windows Server, System Center ve uygulamaların nasıl kullanıldığı, gelişmiş güvenilirlik verilerinin ve hem temel hem de güvenlik seviyelerinin verileri dahil olmak üzere ek Öngörüler.
  - **Full**: sorunları belirlemek ve gidermek için gereken tüm veriler ile güvenlik, temel ve gelişmiş düzeylerdeki veriler.

  [System/Allowtelemetri CSP 'si](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry)

- **Microsoft Edge tarama verilerini Microsoft 365 Analytics 'e gönder**: Bu özelliği kullanmak için, **kullanım verilerini paylaşma** ayarlarını **Gelişmiş** veya **tam**olarak ayarlayın. Bu özellik, Microsoft Edge 'in yapılandırılmış ticari KIMLIĞI olan kurumsal cihazlarda Microsoft 365 Analytics 'e gönderdiği verileri denetler. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı**: Intune bu ayarı değiştirmez veya güncelleştirmez. İşletim sistemi varsayılanı, hiçbir göz atma geçmişi verisi gönderemeyebilir.
  - **Yalnızca intranet verilerini Gönder**: yöneticinin intranet veri geçmişini göndermesini sağlar
  - **Yalnızca internet verilerini Gönder**: yöneticinin internet veri geçmişini göndermesini sağlar
  - **Intranet ve internet verileri gönderme**: yöneticinin intranet ve internet veri geçmişini göndermesini sağlar

  [Tarayıcı/ConfigureTelemetryForMicrosoft365Analytics CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-configuretelemetryformicrosoft365analytics)

- **Telemetri proxy sunucusu**: bağlı kullanıcı deneyimlerini ve telemetri isteklerini iletmek için bir proxy sunucusunun tam etki alanı adını (FQDN) veya IP adresini (bir GÜVENLI yuva KATMANı (SSL) bağlantısı kullanarak girin. Bu ayarın biçimi *sunucu*:*bağlantı noktası* olur. Adlandırılmış ara sunucu başarısız olursa veya bu ilkeyi etkinleştirirken bir proxy girilmemişse, bağlı kullanıcı deneyimleri ve telemetri verileri gönderilmez ve yerel cihazda kalır.

  Örnek biçimler:

  ```
  IPv4: 192.246.246.106:100
  IPv6: [2001:4898:4010:4013:95c1:a8b2:953c:c633]:100
  FQDN: www.contoso.com:345
  ```

  [System/TelemetryProxy CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-telemetryproxy)

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="search"></a>Ara

Bu ayarlar, desteklenen Windows sürümlerini de listeleyen [arama ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-search)'sini kullanır. 

- **Güvenli Arama (yalnızca mobil)** : Cortana 'nın, arama sonuçlarında yetişkinlere yönelik içeriği nasıl filtreleyeceğini denetleyin. Seçenekleriniz şunlardır:
  - **Kullanıcı tanımlı**: son kullanıcıların kendi ayarlarını seçmesine izin verin.
  - **Katı**: yetişkin içerikli en yüksek filtreleme.
  - **Orta**: yetişkinlere yönelik içeriğe göre orta filtreleme. Geçerli arama sonuçları filtrelenmez.
- **Aramada Web sonuçlarını görüntüle**: **blok**olarak ayarlandığında kullanıcılar arama yapamıyor ve web sonuçları aramada gösterilmez. **Yapılandırılmadı** (varsayılan), kullanıcıların Web 'de arama yapmasına izin verir ve sonuçlar cihazda gösterilir.

## <a name="start"></a>Başlat

Bu ayarlar, desteklenen Windows sürümlerini de listeleyen [Başlangıç ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-start)'sini kullanır.  

- **Başlangıç menüsü düzeni**: varsayılan başlangıç yerleşimini geçersiz kılın ve masaüstü cihazlarındaki Başlat menüsünü özelleştirin. Özelleştirmeleri içeren bir XML dosyasını karşıya yükleyin, bu da uygulamaların listelendiği sıralama ve daha fazlasını içerir. Kullanıcılar girdiğiniz başlangıç menüsü yerleşimini değiştiremezler.
- **Web sitelerini Başlangıç menüsünde kutucuklara sabitle**: masaüstü cihazlar Için Windows Başlat menüsünde bağlantılar olarak gösterilen Microsoft Edge 'den görüntüleri içeri aktarın.
- **Görev çubuğundan uygulamaları kaldırma**: **blok** kullanıcıların görev çubuğundan uygulama bağlantısını kaldırmasını engeller. **Yapılandırılmadı** (varsayılan), kullanıcıların görev çubuğundan uygulamaları serbest bırakmanıza izin verir.
- **Hızlı Kullanıcı geçişi**: **blok** , oturum açmadan aynı anda oturum açan kullanıcılar arasında geçiş yapılmasını engeller. **Yapılandırılmadı** (varsayılan) Kullanıcı kutucuğunda **Kullanıcı Değiştir** ' i gösterir.
- **En çok kullanılan uygulamalar**: **blok** , en çok kullanılan uygulamaların başlangıç menüsünde gösterilmesini gizler. Bu ayrıca Ayarlar uygulamasında aynı ada sahip iki durumlu ayarı da devre dışı bırakır. **Yapılandırılmadı** (varsayılan) en sık kullanılan uygulamaları gösterir.
- **Son eklenen uygulamalar**: **blok** , son eklenen uygulamaların başlangıç menüsünde gösterilmesini gizler. Bu ayrıca Ayarlar uygulamasında aynı ada sahip iki durumlu ayarı da devre dışı bırakır. **Yapılandırılmadı** (varsayılan) başlangıç menüsünde son eklenen uygulamaları gösterir.
- **Başlangıç ekranı modu**: başlangıç ekranının nasıl gösterileceğini seçin. Seçenekleriniz şunlardır:
  - **Kullanıcı tanımlı**: başlangıç boyutunu zorlamaz. Kullanıcılar boyutu ayarlayabilir.
  - **Tam ekran**: başlangıç boyutunu tam ekran olarak zorlar.
  - **Tam ekran**: başlangıçtan önce tam olmayan boyutunu zorla.
- **Atlama listelerinde son açılan öğeler**: **blok** , son atlama listelerinin başlangıç menüsünde ve görev çubuğunda gösterilmesinin gizlenmesini engeller. Bu ayrıca Ayarlar uygulamasında aynı ada sahip iki durumlu ayarı da devre dışı bırakır. **Yapılandırılmadı** (varsayılan) atlama listelerinde son açılan öğeleri gösterir.
- **Uygulama listesi**: tüm uygulamalar listelerinin nasıl gösterileceğini seçin. Seçenekleriniz şunlardır:
  - **Kullanıcı tanımlı**: hiçbir ayar zorunlu değildir. Kullanıcılar uygulama listesinin cihazda nasıl gösterileceğini seçer.
  - **Daralt**: tüm uygulamalar listesini gizle.
  - **Ayarları uygulamayı daraltın ve devre dışı bırakın**: tüm uygulamalar listesini gizleyin ve Ayarlar uygulamasındaki **Başlat menüsünde uygulama listesini göster** ' i devre dışı bırakın.
  - **Ayarları uygulamayı kaldırır ve devre dışı bırakır**: tüm uygulamalar listesini gizleyin, tüm uygulamalar düğmesini kaldırın ve Ayarlar uygulamasındaki **Başlangıç menüsünde uygulama listesini göster** ' i devre dışı bırakın.
- **Güç düğmesi**: **blok** güç düğmesinin başlangıç menüsünde gösterilmesini gizler. **Yapılandırılmadı** (varsayılan) güç düğmesini gösterir.
- **Kullanıcı kutucuğu**: **blok** , Kullanıcı kutucuğunun başlangıç menüsünde gösterilmesini gizler. **Yapılandırılmadı** (varsayılan) Kullanıcı kutucuğunu gösterir ve ayrıca aşağıdaki ayarları Ayarlar:
  - **Kilit**: **blok** **kilit** seçeneğinin başlangıç menüsündeki Kullanıcı kutucuğunda gösterilmesini gizler. **Yapılandırılmadı** (varsayılan) **Lock** seçeneğini gösterir.
  - **Oturumu**kapat: **Engelle** , **oturumu** kapat seçeneğinin başlangıç menüsündeki Kullanıcı kutucuğunda gösterilmesini gizler. **Yapılandırılmadı** (varsayılan) **oturumu** Kapat seçeneğini gösterir.
- **Kapat**: **Engelle** , **Güncelleştir ve Kapat** ve **Kapat** seçeneklerinin başlangıç menüsündeki güç düğmesinde gösterilmesini gizler. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
- **Sleep**: **blok** , **uyku** seçeneğinin başlangıç menüsündeki güç düğmesinde gösterilmesini gizler. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
- **Hazırda Beklet**: **Engelle** , **Hazırda Beklet** seçeneğinin başlangıç menüsündeki güç düğmesinde gösterilmesini gizler. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
- **Hesap değiştir**: **Engelle** , **Switch hesabının** başlangıç menüsündeki Kullanıcı kutucuğunda gösterilmesini gizler. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
- **Yeniden başlatma seçenekleri**: **blok** , **güncelleştirme ve yeniden başlatma** ve **yeniden başlatma** seçeneklerinin başlangıç menüsündeki güç düğmesinde gösterilmesini gizler. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
- **Başlangıç 'Ta belgeler**: Windows Başlat menüsünde Belgeler klasörünü gizleyin veya gösterin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): hiçbir ayar zorunlu değildir. Kullanıcılar kısayolu göstermeyi veya gizlemeyi seçer.
  - **Gizle**: kısayol gizlenir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
  - **Göster**: kısayol gösterilir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
- **Başlangıç 'Ta indirmeler**: Windows Başlat menüsünde indirmeler klasörünü gizleyin veya gösterin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): hiçbir ayar zorunlu değildir. Kullanıcılar kısayolu göstermeyi veya gizlemeyi seçer.
  - **Gizle**: kısayol gizlenir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
  - **Göster**: kısayol gösterilir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
- **Başlangıç 'Ta dosya Gezgini**: Windows Başlat menüsünde Dosya Gezgini 'ni gizleyin veya gösterin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): hiçbir ayar zorunlu değildir. Kullanıcılar kısayolu göstermeyi veya gizlemeyi seçer.
  - **Gizle**: kısayol gizlenir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
  - **Göster**: kısayol gösterilir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
- **Başlangıç 'Ta ev grubu**: Windows Başlangıç menüsünde ev grubu kısayolunu gizleyin veya gösterin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): hiçbir ayar zorunlu değildir. Kullanıcılar kısayolu göstermeyi veya gizlemeyi seçer.
  - **Gizle**: kısayol gizlenir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
  - **Göster**: kısayol gösterilir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
- **Başlangıç 'Ta müzik**: Windows Başlat menüsünde müzik klasörünü gizleyin veya gösterin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): hiçbir ayar zorunlu değildir. Kullanıcılar kısayolu göstermeyi veya gizlemeyi seçer.
  - **Gizle**: kısayol gizlenir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
  - **Göster**: kısayol gösterilir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
- **Başlangıç 'Ta ağ**: Windows başlat menüsünü ağa gelen gizleyin veya gösterin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): hiçbir ayar zorunlu değildir. Kullanıcılar kısayolu göstermeyi veya gizlemeyi seçer.
  - **Gizle**: kısayol gizlenir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
  - **Göster**: kısayol gösterilir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
- **Başlangıç klasörü**: Windows Başlat menüsünde Kişisel klasörünü gizleyin veya gösterin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): hiçbir ayar zorunlu değildir. Kullanıcılar kısayolu göstermeyi veya gizlemeyi seçer.
  - **Gizle**: kısayol gizlenir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
  - **Göster**: kısayol gösterilir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
- **Başlangıç 'Ta resimler**: Windows Başlat menüsünde resimlerin klasörünü gizleyin veya gösterin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): hiçbir ayar zorunlu değildir. Kullanıcılar kısayolu göstermeyi veya gizlemeyi seçer.
  - **Gizle**: kısayol gizlenir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
  - **Göster**: kısayol gösterilir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
- **Başlangıç ayarları**: Windows Başlat menüsünde ayarlar kısayolunu gizleyin veya gösterin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): hiçbir ayar zorunlu değildir. Kullanıcılar kısayolu göstermeyi veya gizlemeyi seçer.
  - **Gizle**: kısayol gizlenir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
  - **Göster**: kısayol gösterilir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
- **Başlamadan videolar**: Windows Başlat menüsünde videoların klasörünü gizleyin veya gösterin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): hiçbir ayar zorunlu değildir. Kullanıcılar kısayolu göstermeyi veya gizlemeyi seçer.
  - **Gizle**: kısayol gizlenir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
  - **Göster**: kısayol gösterilir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.

## <a name="microsoft-defender-smart-screen"></a>Microsoft Defender akıllı ekranı

- **Microsoft Edge Için SmartScreen**: **gerektir** , Microsoft Defender SmartScreen 'i kapatır ve kullanıcıların bunu açmasını önler. **Yapılandırılmadı** (varsayılan), SmartScreen 'i etkinleştirir. Kullanıcıların olası tehditlere karşı korunmasına yardımcı olur ve kullanıcıların bunu kapatmasını engeller.

  Microsoft Edge, kullanıcıların olası kimlik avı dolandırıcılarından ve kötü amaçlı yazılımlardan korunması için Microsoft Defender SmartScreen (açık) kullanır.

  [Tarayıcı/AllowSmartScreen CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen)

- **Kötü amaçlı site erişimi**: **blok** kullanıcıların Microsoft Defender SmartScreen Filtresi uyarılarını yok saymalarını engeller ve siteye gitmesini engeller. **Yapılandırılmadı** (varsayılan), kullanıcıların uyarıları yoksaymasına ve siteye devam etmesine izin verir.

  [Tarayıcı/PreventSmartScreenPromptOverride CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverride)

- **Doğrulanmamış dosya indirme**: **engelleme** , kullanıcıların Microsoft Defender SmartScreen Filtresi uyarılarını yoksaymasını ve doğrulanmamış dosyaları indirmesini engeller. **Yapılandırılmadı** (varsayılan), kullanıcıların uyarıları yoksaymasına ve doğrulanmamış dosyaları indirmeye devam etmesine izin verir.

  [Tarayıcı/PreventSmartScreenPromptOverrideForFiles CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverrideforfiles)

## <a name="windows-spotlight"></a>Windows Spot

Bu ayarlar, desteklenen Windows sürümlerini de listeleyen [deneyim ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience)'sini kullanır.

- **Windows spot**: **blok** kilit ekranında Windows spot 'u, Windows ipuçlarını, Microsoft tüketici özelliklerini ve diğer ilgili özellikleri kapatır. Amacınız, cihazlardan gelen ağ trafiğini en aza indirmektir, bunu **Engelle**olarak ayarlayın. **Yapılandırılmadı** (varsayılan), Windows spot özelliklerine izin verir ve son kullanıcılar tarafından denetlenebilir. Etkinleştirildiğinde, aşağıdaki ayarları da izin verebilir veya engelleyebilirsiniz:

  - **Kilit ekranında Windows spot**: **blok** Windows spot 'un cihaz kilitleme ekranında bilgi göstermesini engeller. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
  - **Windows spot 'Ta üçüncü taraf önerileri**: blok Windows spot 'un Microsoft tarafından yayımlanmamış içerik önermasını **önleyemez** . **Yapılandırılmadı** (varsayılan); kilit ekranı servisleri, başlangıç menüsünde önerilen uygulamalar ve Windows Ipuçları gibi Windows spot özelliklerinde iş ortağı yazılım yayımcılarından uygulama ve içerik önerilerine izin verir.
  - **Tüketici özellikleri**: **engelleme** , genellikle yalnızca tüketiciler için, başlangıç önerileri, üyelik bildirimleri, kutudan çıkarma deneyimi uygulama yüklemesi ve yeniden yönlendirme kutucukları gibi deneyimleri kapatır. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.
  - **Windows ipuçları**: **blok** açılır pencere ipuçlarını devre dışı bırakır. **Yapılandırılmadı** (varsayılan), Windows ipuçlarının gösterilmesini sağlar.
  - **İşlem merkezi 'Nde Windows spot**: **blok** , Windows spot bildirimlerinin işlem merkezinde gösterilmesini engeller. **Yapılandırılmadı** (varsayılan), kullanıcıların Windows 'da daha üretken olmalarını sağlamak için uygulama veya özellik öneren işlem merkezinde bildirimleri gösterebilir.
  - **Windows spot kişiselleştirme**: **blok** , Windows 'un kullanıcıya özelleştirilmiş deneyimler sağlaması için tanılama verilerini kullanmasını engeller. **Yapılandırılmadı** (varsayılan), Microsoft 'un Kullanıcı Ihtiyaçlarına göre Windows 'u uyarlamak üzere kişiselleştirilmiş öneriler, ipuçları ve teklifler sunmak için tanılama verilerini kullanmasına izin verir.
  - **Windows hoş geldiniz deneyimi**: **blok** Windows spot Windows hoş geldiniz deneyimi özelliğini kapatır. Windows Karşılama deneyimi, Windows 'da ve uygulamalarında güncelleştirmeler ve değişiklikler olduğunda gösterilmez. **Yapılandırılmadı** (varsayılan), yeni veya güncelleştirilmiş özelliklerle ilgili Kullanıcı bilgilerini gösteren Windows Karşılama deneyimine izin verir.

## <a name="microsoft-defender-antivirus"></a>Microsoft Defender virüsten koruma

Bu ayarlar, desteklenen Windows sürümlerini de listeleyen [Defender Ilke CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender)'sini kullanır.

- **Gerçek zamanlı izleme**: **Etkinleştir** kötü amaçlı yazılım, casus yazılım ve diğer istenmeyen yazılım için gerçek zamanlı taramayı etkinleştirir. Kullanıcılar bu uygulamayı kapatamaz. 

  **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Ayarı etkinleştirir ve sonra **Yapılandırılmadı**olarak değiştirirseniz, Intune ayarı daha önce yapılandırılmış durumda bırakır. Varsayılan olarak, işletim sistemi bu özelliği etkinleştirir ve kullanıcıların değiştirmesini sağlar.

  Intune bu özelliği devre dışı bırakır. Devre dışı bırakmak için özel bir URI kullanın.

  [Defender/AllowRealtimeMonitoring CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowrealtimemonitoring)

- **Davranış izleme**: **etkinleştirme** davranış izlemeyi etkinleştirir ve cihazlarda bilinen şüpheli etkinlik desenlerini denetler. Kullanıcılar davranış izlemeyi kapatamaz. 

  **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Ayarı etkinleştirir ve sonra **Yapılandırılmadı**olarak değiştirirseniz, Intune ayarı daha önce yapılandırılmış durumda bırakır. Varsayılan olarak, işletim sistemi davranış Izlemeyi etkinleştirir ve kullanıcıların bunu değiştirmesine izin verir.

  Intune bu özelliği devre dışı bırakır. Devre dışı bırakmak için özel bir URI kullanın.

  [Defender/AllowBehaviorMonitoring CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowbehaviormonitoring)

- **Ağ İnceleme sistemi (NIS)** : NIS, cihazları ağ tabanlı saldırılara karşı korumaya yardımcı olur. Kötü amaçlı trafiği algılamaya ve engellemeye yardımcı olmak için Microsoft Endpoint Protection Center’dan bilinen açıkların imzalarını kullanır.

  **Etkinleştir** ayarı, ağ koruması ve ağ engellemeyi etkinleştirir. Kullanıcılar bu uygulamayı kapatamaz. Etkinleştirildiğinde, kullanıcıların bilinen güvenlik açıklarına bağlanması engellenir.

  **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Ayarı etkinleştirir ve sonra **Yapılandırılmadı**olarak değiştirirseniz, Intune ayarı daha önce yapılandırılmış durumda bırakır. Varsayılan olarak, işletim sistemi NIS 'yi etkinleştirir ve kullanıcıların bunu değiştirmesine izin verir.

  Intune bu özelliği devre dışı bırakır. Devre dışı bırakmak için özel bir URI kullanın.

  [Defender/EnableNetworkProtection CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection)

- **Tüm Indirmeleri Tara**: **Etkinleştir** ayarı bu ayarı açar ve Defender, Internet 'ten indirilen tüm dosyaları tarar. Kullanıcılar bu ayarı kapatamaz. 

  **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Ayarı etkinleştirir ve sonra **Yapılandırılmadı**olarak değiştirirseniz, Intune ayarı daha önce yapılandırılmış durumda bırakır. Varsayılan olarak, işletim sistemi bu ayarı etkinleştirir ve kullanıcıların değiştirmesini sağlar.

  Intune bu özelliği devre dışı bırakır. Devre dışı bırakmak için özel bir URI kullanın.

  [Defender/Allowwioavprotection CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowioavprotection)

- **Microsoft Web tarayıcılarında yüklenen dosyaları tara**: **Etkinleştir** , Defender 'ın Internet Explorer 'da kullanılan betikleri taramasını sağlar. Kullanıcılar bu ayarı kapatamaz. 

  **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Ayarı etkinleştirir ve sonra **Yapılandırılmadı**olarak değiştirirseniz, Intune ayarı daha önce yapılandırılmış durumda bırakır. Varsayılan olarak, işletim sistemi bu ayarı etkinleştirir ve kullanıcıların değiştirmesini sağlar.

  Intune bu özelliği devre dışı bırakır. Devre dışı bırakmak için özel bir URI kullanın.

  [Defender/AllowScriptScanning CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowscriptscanning)

- **Defender 'A Son Kullanıcı erişimi**: **blok** , Microsoft Defender Kullanıcı arabirimini son kullanıcılardan gizler. Tüm Microsoft Defender bildirimleri de bastırılır.

  **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Ayarı engeller ve sonra **Yapılandırılmadı**olarak değiştirirseniz, Intune ayarı daha önce yapılandırılmış durumda bırakır. Varsayılan olarak, işletim sistemi Microsoft Defender Kullanıcı arabirimine Kullanıcı erişimine izin verir ve kullanıcıların bunu değiştirmesine izin verir.

  Intune bu özelliği devre dışı bırakır. Devre dışı bırakmak için özel bir URI kullanın.

  Bu ayar değiştirildiğinde, kullanıcının bilgisayarının bir sonraki yeniden başlatılmasında devreye girer.

  [Defender/AllowUserUIAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowuseruiaccess)

- **Güvenlik Zekası güncelleştirme aralığı (saat)** : Defender 'ın, 0-24 adresinden yeni güvenlik zekasını denetlediği aralığı girin. Seçenekleriniz şunlardır:

  - **Yapılandırılmadı** (varsayılan): Intune bu ayarı değiştirmez veya güncelleştirmez. İşletim sistemi varsayılanı, güncelleştirmeleri her 8 saatte bir denetleyebilir.
  - **Denetleme**: Defender yeni güvenlik zekası güncelleştirmelerini denetlemez.
  - **1-24**: her saatte bir denetim `1`, `2` her iki saatte bir denetim `24` denetler ve bu şekilde devam eder.
  
  [Defender/Signatureupdateınterval CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-signatureupdateinterval)
  
- **Dosya ve program etkinliğini izle**: Defender 'ın cihazlarda dosya ve program etkinliğini izlemesine izin verir. Seçenekleriniz şunlardır:

  - **Yapılandırılmadı** (varsayılan): Intune bu ayarı değiştirmez veya güncelleştirmez. İşletim sistemi varsayılanı tüm dosyaları izleyebilir.
  - **İzleme devre dışı**
  - **Tüm dosyaları izle**
  - **Yalnızca gelen dosyaları izle**
  - **Yalnızca giden dosyaları izle**

  [Defender/RealTimeScanDirection CSP 'si](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-realtimescandirection)

- **Karantinaya alınan kötü amaçlı yazılımı silmeden önce geçen gün**: daha önce etkilenen cihazları el ile kontrol edebilmeniz için, girdiğiniz gün sayısı için çözümlenmiş kötü amaçlı yazılımı izlemeye devam edin Gün sayısını `0`ayarlarsanız, kötü amaçlı yazılım Karantina klasöründe kalır ve otomatik olarak kaldırılmaz. `90`olarak ayarlandığında, karantina öğeleri sistemde 90 gün boyunca depolanır ve sonra kaldırılır.

  [Defender/DaysToRetainCleanedMalware CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-daystoretaincleanedmalware)

- **Tarama sırasında CPU kullanım sınırı**: taramaların kullanmasına ızın verilen CPU miktarını, `0` `100`ile sınırlayın.
- **Arşiv dosyalarını Tara**: **Enable** , zip veya CAB dosyaları gibi arşiv dosyalarını taramak için Defender 'ı etkinleştirir. Kullanıcılar bu ayarı kapatamaz.

  **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Ayarı etkinleştirir ve sonra **Yapılandırılmadı**olarak değiştirirseniz, Intune ayarı daha önce yapılandırılmış durumda bırakır. Varsayılan olarak, işletim sistemi bu taramayı etkinleştirir ve kullanıcıların değiştirmesini sağlar.

  Intune bu özelliği devre dışı bırakır. Devre dışı bırakmak için özel bir URI kullanın.

  [Defender/AllowArchiveScanning CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowarchivescanning)

- **Gelen posta Iletilerini Tara**: **Enable** , Defender 'ın cihaza geldikçe e-posta iletilerini taramasını sağlar. Etkinleştirildiğinde, altyapı posta gövdesini ve eklerini çözümlemek için posta kutusu ve posta dosyalarını ayrıştırır. . PST (Outlook),. dbx,. mbx, MIME (Outlook Express) ve BinHex (Mac) biçimlerini tarayabilirsiniz.

  **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Ayarı etkinleştirir ve sonra **Yapılandırılmadı**olarak değiştirirseniz, Intune ayarı daha önce yapılandırılmış durumda bırakır. Varsayılan olarak, işletim sistemi bu taramayı kapatır ve kullanıcıların bunu değiştirmesine izin verir.

  Intune bu özelliği devre dışı bırakır. Devre dışı bırakmak için özel bir URI kullanın.

  [Defender/AllowEmailScanning CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowemailscanning)

- **Tam tarama sırasında çıkarılabilir sürücüleri Tara**: **Etkinleştir** ayarı, tam tarama sırasında Defender çıkarılabilir sürücü taramalarını etkinleştirir. Kullanıcılar bu ayarı kapatamaz.

  **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Ayarı etkinleştirir ve sonra **Yapılandırılmadı**olarak değiştirirseniz, Intune ayarı daha önce yapılandırılmış durumda bırakır. Varsayılan olarak, işletim sistemi Defender 'ın USB sürücüleri gibi çıkarılabilir sürücüleri taramasını sağlar ve kullanıcıların bu ayarı değiştirmesine izin verir.

  Bir hızlı tarama sırasında, çıkarılabilir sürücüler yine de taranabilecek.

  Intune bu özelliği devre dışı bırakır. Devre dışı bırakmak için özel bir URI kullanın.

  [Defender/AllowFullScanRemovableDriveScanning CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanremovabledrivescanning)

- **Tam tarama sırasında eşlenmiş ağ sürücülerine Tara**: **Etkinleştir** , Defender tarafından eşlenen ağ sürücülerindeki dosyaları tarar. Sürücüdeki dosyalar salt okunurdur, Defender bu bilgisayarlarda bulunan herhangi bir kötü amaçlı yazılımı kaldıramıyor. Kullanıcılar bu ayarı kapatamaz.

  **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Ayarı etkinleştirir ve sonra **Yapılandırılmadı**olarak değiştirirseniz, Intune ayarı daha önce yapılandırılmış durumda bırakır. Varsayılan olarak, işletim sistemi bu özelliği etkinleştirir ve kullanıcıların değiştirmesini sağlar.

  Hızlı tarama sırasında, eşlenmiş ağ sürücüleri yine de taranamaz.

  Intune bu özelliği devre dışı bırakır. Devre dışı bırakmak için özel bir URI kullanın.

  [Defender/AllowFullScanOnMappedNetworkDrives CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowfullscanonmappednetworkdrives)

- **Ağ klasörlerinden açılan dosyaları tara**: **Enable** Defender, bir UNC yolundan erişilen dosyalar gibi ağ klasörlerinden veya paylaşılan ağ sürücülerinden açılan dosyaları tarar. Kullanıcılar bu ayarı kapatamaz. Sürücüdeki dosyalar salt okunurdur, Defender bu bilgisayarlarda bulunan herhangi bir kötü amaçlı yazılımı kaldıramıyor.

  **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Ayarı etkinleştirir ve sonra **Yapılandırılmadı**olarak değiştirirseniz, Intune ayarı daha önce yapılandırılmış durumda bırakır. Varsayılan olarak, işletim sistemi Ağ klasörlerinden açılan dosyaları tarar ve kullanıcıların bunu değiştirmesine izin verir.

  Intune bu özelliği devre dışı bırakır. Devre dışı bırakmak için özel bir URI kullanın.

  [Defender/AllowScanningNetworkFiles CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowscanningnetworkfiles)

- **Bulut koruması**: **etkinleştirme** , yönettiğiniz cihazlardan gelen kötü amaçlı yazılım etkinlikleri hakkında bilgi almak için Microsoft etkin koruma hizmeti açar. Kullanıcılar bu ayarı değiştiremezler. 

  **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Ayarı etkinleştirir ve sonra **Yapılandırılmadı**olarak değiştirirseniz, Intune ayarı daha önce yapılandırılmış durumda bırakır. Varsayılan olarak, işletim sistemi Microsoft Etkin Koruma Hizmeti bilgi almasına izin verir ve kullanıcıların bu ayarı değiştirmesine izin verir.

  Intune bu özelliği devre dışı bırakır. Devre dışı bırakmak için özel bir URI kullanın.

  [Defender/AllowCloudProtection CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowcloudprotection)

- **Örnek gönderimi yapmadan önce kullanıcılara sor**: daha fazla analiz gerektirebilecek kötü amaçlı olabilecek dosyaların otomatik olarak Microsoft 'a gönderilip gönderilmeyeceğini denetler. Seçenekleriniz şunlardır:

  - **Yapılandırılmadı** (varsayılan): Intune bu ayarı değiştirmez veya güncelleştirmez. İşletim sistemi varsayılanı, güvenli örnekleri otomatik olarak gönderebilir.
  - **Her zaman sor**
  - **Kişisel verileri göndermeden önce sor**
  - **Hiçbir şekilde veri gönderme**
  - **Tüm verileri sorulmadan gönder**: veriler otomatik olarak gönderilir.

  [Defender/Submitsamplesonay CSP 'si](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent)

- **Günlük hızlı tarama gerçekleştirme süresi**: günlük hızlı tarama çalıştırmak için saati seçin. **Yapılandırılmadı** , günlük tarama çalıştırmaz. Daha fazla özelleştirme istiyorsanız, ayar **yapmak için sistem taraması türünü** yapılandırın.

  [Defender/ScheduleQuickScanTime CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime)

- **Gerçekleştirilecek sistem taraması türü**: tarama düzeyini ve taramanın çalıştırılacağı günü ve saati içeren bir sistem taraması zamanlayın. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı**: cihazda bir sistem taraması zamanlayamıyor. Son kullanıcılar, gerektiğinde taramaları el ile çalıştırabilir veya cihazlarında ister.
  - **Devre dışı bırak**: cihazdaki tüm sistem taramasını devre dışı bırakır. Cihazları tarayan bir iş ortağı virüsten koruma çözümü kullanıyorsanız bu seçeneği belirleyin.
  - **Hızlı tarama**: kayıt defteri anahtarları ve bilinen Windows başlangıç klasörleri gibi kötü amaçlı yazılımın kaydedildiği yaygın konumlara bakar.
    - **Zamanlanan gün**: taramanın çalıştırılacağı günü seçin.
    - **Zamanlanan saat**: taramanın çalıştırılacağı saati seçin.
  - **Tam tarama**: kötü amaçlı yazılımın kaydedildiği yaygın konumlara bakar ve cihazdaki her dosyayı ve klasörü tarar.
    - **Zamanlanan gün**: taramanın çalıştırılacağı günü seçin.
    - **Zamanlanan saat**: taramanın çalıştırılacağı saati seçin.

  > [!TIP]
  > Bu ayar **günlük hızlı tarama ayarı gerçekleştirme zamanına** göre çakışabilir. Bazı öneriler:  
  >
  > - Günlük hızlı tarama ve haftalık tam tarama zamanlamak istiyorsanız:
  >   1. **Günlük hızlı tarama ayarı gerçekleştirme saatini** yapılandırın.
  >   2. Tam tarama yapmak için **gerçekleştirilecek sistem taraması türünü** yapılandırın.
  > 
  > - Her gün yalnızca bir hızlı tarama (tam tarama yok) istiyorsanız, her iki ayarı kullanın: **günlük hızlı tarama** veya **gerçekleştirilecek sistem taraması türü**. Örneğin, 6 ' da her Salı günde bir hızlı tarama çalıştırmak için, ayar **yapmak için sistem taraması türünü** yapılandırın.
  > 
  > - **Hızlı tarama**olarak ayarlanacak **sistem taraması türü** ile **günlük hızlı tarama ayarı gerçekleştirmek için geçen süreyi** yapılandırmayın. Bu ayarlar çakışabilir ve bir tarama çalışmayabilir.

  [Defender/ScanParameter CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-scanparameter)  
  [Defender/ScheduleScanDay CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescanday)  
  [Defender/ScheduleScanTime CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescantime)

- İstenmeyebilecek **uygulamaları Algıla**: Windows istenmeyebilecek uygulamalar algıladığında koruma düzeyini seçin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Microsoft Defender istenmeyebilecek uygulamalar koruması devre dışı bırakıldı.
  - **Engelle**: Microsoft Defender istenmeyebilecek uygulamaları algılar ve algılanan öğeler engellenir. Bu öğeler, diğer tehditlerle birlikte geçmiş olarak gösterilir.
  - **Denetim**: Microsoft Defender istenmeyebilecek uygulamaları algılar, ancak hiçbir işlem gerçekleşmez. Microsoft Defender 'ın işlem yapması için gereken uygulamalarla ilgili bilgileri gözden geçirebilirsiniz. Örneğin, Olay Görüntüleyicisi Microsoft Defender tarafından oluşturulan olayları arayın.

  İstenmeyebilecek uygulamalar hakkında daha fazla bilgi için bkz. istenmeyebilecek [uygulamaları algılama ve engelleme](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus).

  [Defender/PUAProtection CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-puaprotection)

- **Örnek gönderme onayı**: Şu anda bu ayarın etkisi yoktur. Bu ayarı kullanmayın. Gelecekteki bir sürümde kaldırılabilir.

- **Erişim koruması**: **blok** , erişilen veya indirilen dosyaların taranmasını engeller. Kullanıcılar açamaz.

  **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez. Ayarı engeller ve sonra **Yapılandırılmadı**olarak değiştirirseniz, Intune ayarı daha önce işletim sistemi tarafından yapılandırılan durumunda bırakır. Varsayılan olarak, işletim sistemi bu özelliği sağlar ve kullanıcıların bunu değiştirmesine izin verir.

  Intune bu özelliği kullanmaz. Etkinleştirmek için özel bir URI kullanın.

  [Defender/AllowOnAccessProtection CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowonaccessprotection)

- **Algılanan kötü amaçlı yazılım tehditleri eylemleri**: kötü amaçlı yazılım iş parçacıklarını nasıl işlemek istediğinizi seçin. **Yapılandırılmadı** (varsayılan) Microsoft Defender 'ın en iyi seçeneği seçmesini sağlar. **Etkinleştir**olarak ayarlandığında, Defender 'ın algıladığı her tehdit düzeyi için hangi eylemleri istediğini seçin: düşük, orta, yüksek ve önemli. Seçenekleriniz şunlardır:
  
  - **Temizle**
  - **Karantina**
  - **Kaldır**
  - **İzin ver**
  - **Kullanıcı tanımlı**
  - **Engelle**

  Eyleminiz mümkün değilse, Microsoft Defender tehdit 'nin düzeltildiğinden emin olmak için en iyi seçeneği seçer. 

  [Defender/ThreatSeverityDefaultAction CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-threatseveritydefaultaction)

### <a name="microsoft-defender-antivirus-exclusions"></a>Microsoft Defender virüsten koruma dışlamaları

- **Taramaların ve gerçek zamanlı korumanın dışında tutulacak dosya ve klasörler**: dışlamalar listesine **C:\path** veya **%ProgramFiles%\yol\filename.exe** gibi bir veya daha fazla dosya ve klasör ekler. Bu dosya ve klasörler gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.
- **Taramaların ve gerçek zamanlı korumanın dışında tutulacak dosya uzantıları**: dışlamalar listesine **jpg** veya **txt** gibi bir veya daha fazla dosya uzantısı ekleyin. Bu uzantılara sahip tüm dosyalar gerçek zamanlı veya zamanlanmış taramalara dahil değildir.
- **Taramaların ve gerçek zamanlı korumanın dışında tutulacak süreçler**: dışlamalar listesine **. exe**, **. com**veya **. scr** türünde bir veya daha fazla işlem ekleyin. Bu süreçler gerçek zamanlı veya zamanlanmış taramalara dahil değildir.

## <a name="power-settings"></a>Güç ayarları

### <a name="battery"></a>Ak

- **Enerji tasarrufunu açmak Için pil düzeyi**: cihaz pil gücünü kullanırken, 0-100 adresinden enerji tasarrufu 'nı açmak için pil ücreti düzeyini girin. Pil ücreti düzeyini gösteren bir yüzde değeri girin. Varsayılan değer %70 ' dir. %70 olarak ayarlandığında enerji tasarrufu, pilin %70 ' i veya daha az kullanılabilir olduğunu açık hale getirir.

  [Güç/enerji Gysaverbatteryıthresholdonpili CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)

- **Kapağı kapatma (yalnızca mobil)** : cihaz pil gücünü kullanırken, kapak kapatıldığında ne olacağını seçin. Seçenekleriniz şunlardır:

  - **Yapılandırılmadı** (varsayılan): Intune bu ayarı değiştirmez veya güncelleştirmez.
  - **Eylem yok**: cihaz açık kalır ve pil gücünü kullanmaya devam eder.
  - **Uyku**: Cihaz uyku moduna geçer ve az miktarda pil ücreti kullanır. Bilgisayar hala açık ve açık uygulamalar ve dosyalar rasgele erişimli bellek (RAM) içinde depolanır.
  - **Hazırda Beklet**: cihaz hazırda bekleme moduna girer. Açık uygulamalar ve dosyalar sabit diskte depolanır ve cihaz kapanır.
  - **Kapat**: Cihaz kapanıyor. Açık uygulamalar ve dosyalar kaydedilmeden kapalıdır.

  [Power/Selectlidcloseactiononpili CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-selectlidcloseactiononbattery)

- **Güç düğmesi**: cihaz pil gücünü kullanırken, güç düğmesi seçildiğinde ne olacağını seçin. Seçenekleriniz şunlardır:

  - **Yapılandırılmadı** (varsayılan): Intune bu ayarı değiştirmez veya güncelleştirmez.
  - **Eylem yok**: cihaz açık kalır ve pil gücünü kullanmaya devam eder.
  - **Uyku**: Cihaz uyku moduna geçer ve az miktarda pil ücreti kullanır. Bilgisayar hala açık ve açık uygulamalar ve dosyalar rasgele erişimli bellek (RAM) içinde depolanır.
  - **Hazırda Beklet**: cihaz hazırda bekleme moduna girer. Açık uygulamalar ve dosyalar sabit diskte depolanır ve cihaz kapanır.
  - **Kapat**: Cihaz kapanıyor. Açık uygulamalar ve dosyalar kaydedilmeden kapalıdır.

  [Power/Selectpowerbuttonactiononpili CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-selectpowerbuttonactiononbattery)

- **Uyku düğmesi**: cihaz pil gücünü kullanırken, uyku düğmesi seçildiğinde ne olacağını seçin. Seçenekleriniz şunlardır:

  - **Yapılandırılmadı** (varsayılan): Intune bu ayarı değiştirmez veya güncelleştirmez.
  - **Eylem yok**: cihaz açık kalır ve pil gücünü kullanmaya devam eder.
  - **Uyku**: Cihaz uyku moduna geçer ve az miktarda pil ücreti kullanır. Bilgisayar hala açık ve açık uygulamalar ve dosyalar rasgele erişimli bellek (RAM) içinde depolanır.
  - **Hazırda Beklet**: cihaz hazırda bekleme moduna girer. Açık uygulamalar ve dosyalar sabit diskte depolanır ve cihaz kapanır.
  - **Kapat**: Cihaz kapanıyor. Açık uygulamalar ve dosyalar kaydedilmeden kapalıdır.

  [Power/Selecttur Epbuttonactiononpili CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-selectsleepbuttonactiononbattery)

- **Karma uyku**: cihaz pil gücünü kullanırken, **devre dışı bırakma** , cihazın karma uyku moduna geçmesini önler. Karma uyku modundayken, açılan uygulamalar ve dosyalar rastgele erişim belleği (RAM) ve sabit disk üzerinde depolanır. Bu, az miktarda pil ücreti kullanır. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.

  [Power/Turnoffhybridstaeponpili CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-turnoffhybridsleeponbattery)

### <a name="pluggedin"></a>Pluggedın

- **Enerji tasarrufunu açmak Için pil düzeyi**: cihaz prize takılıyken, 0-100 adresinden enerji tasarrufu 'nı açmak için pil ücreti düzeyini girin. Pil ücreti düzeyini gösteren bir yüzde değeri girin. Varsayılan değer %70 ' dir. %70 olarak ayarlandığında enerji tasarrufu, pilin %70 ' i veya daha az kullanılabilir olduğunu açık hale getirir.

  [Güç/enerji Gysaverbatteryıthresholdpluggedın CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)

- **Kapağı kapatma (yalnızca mobil)** : cihaz prize takılıyken, kapak kapatıldığında ne olacağını seçin. Seçenekleriniz şunlardır:

  - **Yapılandırılmadı** (varsayılan): Intune bu ayarı değiştirmez veya güncelleştirmez.
  - **Eylem yok**: cihaz açık kalır.
  - **Uyku**: Cihaz uyku moduna girer. Bilgisayar hala açık ve açık uygulamalar ve dosyalar rasgele erişimli bellek (RAM) içinde depolanır.
  - **Hazırda Beklet**: cihaz hazırda bekleme moduna girer. Açık uygulamalar ve dosyalar sabit diskte depolanır ve cihaz kapanır.
  - **Kapat**: Cihaz kapanıyor. Açık uygulamalar ve dosyalar kaydedilmeden kapalıdır.
  
    [Power/Selectlidcloseactionpluggedın CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-selectlidcloseactionpluggedin)
  
- **Güç düğmesi**: cihaz prize takılıyken, güç düğmesi seçildiğinde ne olacağını seçin. Seçenekleriniz şunlardır:

  - **Yapılandırılmadı** (varsayılan): Intune bu ayarı değiştirmez veya güncelleştirmez.
  - **Eylem yok**: cihaz açık kalır.
  - **Uyku**: Cihaz uyku moduna girer. Bilgisayar hala açık ve açık uygulamalar ve dosyalar rasgele erişimli bellek (RAM) içinde depolanır.
  - **Hazırda Beklet**: cihaz hazırda bekleme moduna girer. Açık uygulamalar ve dosyalar sabit diskte depolanır ve cihaz kapanır.
  - **Kapat**: Cihaz kapanıyor. Açık uygulamalar ve dosyalar kaydedilmeden kapalıdır.

  [Power/Selectpowerbuttonactionpluggedın CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-selectpowerbuttonactionpluggedin)

- **Uyku düğmesi**: cihaz prize takılıyken, uyku düğmesi seçildiğinde ne olacağını seçin. Seçenekleriniz şunlardır:

  - **Yapılandırılmadı** (varsayılan): Intune bu ayarı değiştirmez veya güncelleştirmez.
  - **Eylem yok**: cihaz açık kalır.
  - **Uyku**: Cihaz uyku moduna girer. Bilgisayar hala açık ve açık uygulamalar ve dosyalar rasgele erişimli bellek (RAM) içinde depolanır.
  - **Hazırda Beklet**: cihaz hazırda bekleme moduna girer. Açık uygulamalar ve dosyalar sabit diskte depolanır ve cihaz kapanır.
  - **Kapat**: Cihaz kapanıyor. Açık uygulamalar ve dosyalar kaydedilmeden kapalıdır.

  [Power/Selecttur Epbuttonactionpluggedın CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-selectsleepbuttonactionpluggedin)

- **Karma uyku**: cihaz prize takılıyken, **devre dışı bırak ayarı** cihazın karma uyku moduna geçmesini önler. Karma uyku modundayken, açılan uygulamalar ve dosyalar rastgele erişim belleği (RAM) ve sabit disk üzerinde depolanır. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Intune bu ayarı değiştirmez veya güncelleştirmez.

  [Power/Turnoffhybridstaeppluggedın CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-turnoffhybridsleeppluggedin)

## <a name="next-steps"></a>Sonraki adımlar

Her bir ayara dair ek teknik ayrıntılar ve hangi Windows sürümlerinin desteklendiği hakkında bilgi için bkz. [Windows 10 İlke CSP Başvurusu](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)
