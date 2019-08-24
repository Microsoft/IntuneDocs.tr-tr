---
title: Microsoft Intune - Azure’da Windows 10 cihaz kısıtlama ayarları | Microsoft Docs
description: Windows 10 ve üzeri cihazlarda cihaz kısıtlamaları oluşturmaya yönelik tüm ayarların ve bunların açıklamalarının listesini görüntüleyin. Bu ayarları, ekran görüntülerini, parola gereksinimlerini, bilgi noktası ayarlarını, depodaki uygulamaları, Microsoft Edge tarayıcısı, Windows Defender, buluta erişimi, Başlangıç menüsünü ve Microsoft Intune daha fazlasını denetlemek için bir yapılandırma profilinde kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/13/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5b3fd474e938e2e85a0a08951a9e3f154d980411
ms.sourcegitcommit: b64869b4be357c0741ec01b1a2f0bae13efce937
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/23/2019
ms.locfileid: "69998939"
---
# <a name="windows-10-and-newer-device-settings-to-allow-or-restrict-features-using-intune"></a>Intune kullanarak özelliklere izin vermek veya erişimi kısıtlamak için Windows 10 (ve üzeri) cihaz ayarları

Bu makalede, Windows 10 ve daha yeni cihazlarda denetleyebilmeniz için kullanabileceğiniz tüm farklı ayarlar listelenmiştir ve açıklanmaktadır. Mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak bu ayarları, özelliklere izin vermek veya devre dışı bırakmak, parola kuralları ayarlamak, kilit ekranını özelleştirmek, Windows Defender 'ı kullanmak ve daha fazlasını yapmak için kullanın.

Bu ayarlar, Intune 'da bir cihaz yapılandırma profiline eklenir ve ardından Windows 10 cihazlarınıza atanır veya dağıtılır.

> [!Note]
> Tüm Windows sürümlerinde tüm seçenekler kullanılamaz. Desteklenen sürümleri görmek için, [CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) 'lere başvurun (başka bir Microsoft Web sitesi açar).

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz yapılandırma profili oluşturma](device-restrictions-configure.md#create-the-profile).

## <a name="app-store"></a>Uygulama Mağazası

Bu ayarlar, desteklenen Windows sürümlerini de listeleyen [ApplicationManagement ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement)'sini kullanır.

- **Uygulama Mağazası** (yalnızca mobil): **Yapılandırılmadı** (varsayılan) son kullanıcıların mobil cihazlarda App Store 'a erişmesine izin verir. **Blok** , uygulama mağazasının kullanımını engeller.
- **Mağazadan uygulamaları otomatik güncelleştir**: **Yapılandırılmadı** (varsayılan) Microsoft Store yüklenen uygulamaların otomatik olarak güncelleştirilmesini sağlar. **Blok** , güncelleştirmelerin otomatik olarak yüklenmesini engeller.
- **Güvenilen uygulama yüklemesi**: Microsoft Store olmayan uygulamaların yüklenebilmesinin yanı sıra dışarıdan yükleme olarak da bilinen öğesini seçin. Dışarıdan yükleme, Microsoft Store tarafından sertifikasız bir uygulamayı yüklüyor ve çalıştırmıyor. Örneğin, yalnızca şirket içi bir uygulama. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): İşletim sistemi varsayılanını kullanır.
  - **Engelle**: Dışarıdan yüklemeyi engeller. Microsoft Store olmayan uygulamalar yüklenemez.
  - **İzin ver**: Dışarıdan yüklemeyi sağlar. Microsoft Store olmayan uygulamalar yüklenebilir.
- **Geliştirici kilidi açma**: Dışarıdan yüklenen uygulamaların son kullanıcılar tarafından değiştirilmesine izin verme gibi Windows Geliştirici ayarlarına izin verin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): İşletim sistemi varsayılanını kullanır.
  - **Engelle**: Geliştirici modu ve dışarıdan yükleme uygulamalarını engeller.
  - **İzin ver**: Geliştirici modu ve dışarıdan yükleme uygulamalarına izin verir.

  [Cihazınızı geliştirme Için etkinleştirme](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development) bu özellik hakkında daha fazla bilgi içerir.

- **Paylaşılan kullanıcı uygulaması verileri**: Aynı cihazdaki farklı kullanıcılar arasında ve bu uygulamanın diğer örnekleriyle uygulama verilerini paylaşmaya **Izin ver** ' i seçin. **Yapılandırılmadı** (varsayılan), diğer kullanıcılar ve aynı uygulamanın diğer örnekleri ile veri paylaşmayı engeller.
- **Yalnızca özel mağazayı kullan**: **Izin ver** , bir perakende kataloğu dahil olmak üzere, uygulamaların özel bir mağazadan indirilmesine ve ortak depodan Indirilmesinin yapılmasına izin verir. **Yapılandırılmadı** (varsayılan), uygulamaların özel bir mağazadan ve ortak bir mağazadan indirilmesini sağlar.
- **Mağaza kaynaklı uygulama başlatma**: **Blok** , cihazda önceden yüklenmiş olan veya Microsoft Store indirilen tüm uygulamaları devre dışı bırakır. **Yapılandırılmadı** (varsayılan) bu uygulamaların açılmasını sağlar.
- **Uygulama verilerini sistem birimine yükler**: **Blok** , uygulamaların cihazın sistem biriminde veri depolamasını engeller. **Yapılandırılmadı** (varsayılan), uygulamaların sistem diski biriminde veri depolamasına izin verir.
- **Uygulamaları sistem sürücüsüne yükler**: **Blok** , uygulamaların cihazdaki sistem sürücüsüne yüklenmesini engeller. **Yapılandırılmadı** (varsayılan), uygulamaların sistem sürücüsüne yüklenmesine izin verir.
- **Oyun DVR** (yalnızca masaüstü): **Blok** , Windows oyun kaydını ve yayınlamayı devre dışı bırakır. **Yapılandırılmadı** (varsayılan) oyunları kaydetmeye ve yayınlamasını sağlar.
- **Yalnızca mağazadan uygulamalar**: Bu ayar, kullanıcılar Microsoft Store dışındaki yerlerden uygulama yüklemeleri durumunda kullanıcı deneyimini belirler. Seçenekleriniz şunlardır:

  - **Yapılandırılmadı** (varsayılan): Son kullanıcıların, diğer ilke ayarlarında tanımlı uygulamalar dahil olmak üzere Microsoft Store dışındaki yerlerden uygulama yüklemesine izin verir.  
  - **Her yerden**: Uygulama önerilerini devre dışı bırakır ve kullanıcıların herhangi bir konumdan uygulama yüklemesine olanak tanır.  
  - **Yalnızca mağaza**: Son kullanıcıları yalnızca Microsoft Store uygulama yüklemeye zorlar.
  - **Öneriler**: Microsoft Store mevcut olan Web 'den bir uygulama yüklerken, kullanıcılar onu mağazadan indirdikleri öneren bir ileti görür.  
  - **Depolamayı tercih et**: Microsoft Store dışındaki yerlerden uygulama yüklediklerinde kullanıcıları uyarır.

  [SmartScreen/Enableappınstallcontrol CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen#smartscreen-enableappinstallcontrol)

- **Yüklemeler üzerinde Kullanıcı denetimi**: **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, Windows Installer kullanıcıların, dosyaları yüklemek için Dizin girme gibi sistem yöneticileri için genellikle ayrılmış yükleme seçeneklerini değiştirmelerini engelleyin. **Engelle** , kullanıcıların bu yükleme seçeneklerini değiştirmesine izin verir ve Windows Installer güvenlik özelliklerinden bazıları atlanır.

  [ApplicationManagement/MSIAllowUserControlOverInstall CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-msiallowusercontroloverinstall)

- **Yükseltilmiş ayrıcalıklara sahip uygulamaları yükler**: **Yapılandırılmadı** (varsayılan) olarak ayarlandığında sistem, sistem yöneticisinin dağıtamayacağı veya sunamayacağı programları yüklediğinde geçerli kullanıcının izinlerini uygular. **Blok** Windows Installer, sisteme herhangi bir program yüklerken yükseltilmiş izinleri kullanmak için yönlendirir. Bu ayrıcalıklar tüm programlara genişletilir.

  [ApplicationManagement/MSIAlwaysInstallWithElevatedPrivileges CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-msialwaysinstallwithelevatedprivileges)

- **Başlangıç uygulamaları**: Kullanıcı cihazda oturum açtıktan sonra açılacak uygulamaların bir listesini girin. Windows uygulamalarının paket aile adları (PFN) için noktalı virgülle ayrılmış bir liste kullandığınızdan emin olun. Bu ilkenin çalışması için, Windows uygulamalarındaki bildirimin bir başlangıç görevi kullanması gerekir.

  [ApplicationManagement/LaunchAppAfterLogOn CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-launchappafterlogon)

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="cellular-and-connectivity"></a>Hücresel ve Bağlantı

Bu ayarlar, desteklenen Windows sürümlerini de listelenecek olan [bağlantı ilkesini](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity) ve [Wi-Fi ilkesi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi) CSP 'leri kullanır.

- [Wi-Fi ilkesi CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi)

- **Hücresel veri kanalı**: Son kullanıcıların, hücresel ağa bağlıyken Web 'e göz atma gibi verileri kullanıp kullanmadığı seçin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): , Hücresel veri kanalına izin verebilecek işletim sistemi varsayılanını kullanır. Son kullanıcılar devre dışı bırakabilirsiniz.
  - **Engelle**: Hücresel veri kanalına izin verme. Son kullanıcılar açamaz.
  - **Izin ver (düzenlenemez)** : Hücresel veri kanalına izin verir. Son kullanıcılar bu uygulamayı kapatamaz.

- **Veri dolaşımı**: **Blok** , cihazda hücresel veri dolaşımını önler. **Yapılandırılmadı** (varsayılan), verilere erişirken ağlar arasında dolaşımına izin verir.
- **Hücresel ağ üzerinden VPN**: **Blok** , cihazın bir hücresel ağa bağlıyken VPN bağlantılarına erişmesini önler. **Yapılandırılmadı** (varsayılan), VPN 'nin hücresel dahil herhangi bir bağlantıyı kullanmasına izin verir.
- **Hücresel ağ üzerinden VPN dolaşımı**: **Blok** , cihazın bir hücresel ağda DOLAŞıMDA VPN bağlantılarına erişmesini engeller. **Yapılandırılmadı** (varsayılan), dolaşımda VPN bağlantılarına izin verir.
- **Bağlı cihazlar hizmeti**: **Block** , bağlı cihazlar platformu (CDP) bileşenini devre dışı bırakır. CDP, uzak uygulama başlatma, uzak mesajlaşma, uzak uygulama oturumları ve diğer cihazlar arası deneyimleri desteklemek için diğer cihazlara (Bluetooth/LAN veya bulut aracılığıyla) bulma ve bağlantı sağlar. **Yapılandırılmadı** (varsayılan), diğer Bluetooth cihazlarına bulma ve bağlantı sağlayan bağlı cihazlar hizmetine izin verir.
- **NFC**: **Block** , yakın alan ILETIŞIMLERI (NFC) yeteneklerini engelliyor. **Yapılandırılmadı** (varsayılan) kullanıcıların cihazda NFC özelliklerini etkinleştirmesine ve yapılandırmasına izin verir.
- **Wi-Fi**: **Blok** , kullanıcıların cihazdaki Wi-Fi bağlantılarını kullanmasını ve etkinleştirmelerini, yapılandırmalarını ve kullanmasını engeller. **Yapılandırılmadı** (varsayılan) Wi-Fi bağlantılarına izin verir.
- **Wi-Fi etkin noktalarına otomatik olarak bağlan**: **Blok** cihazların Wi-Fi etkin noktalarına otomatik olarak bağlanmasını engeller. **Yapılandırılmadı** (varsayılan) cihazların ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmasına ve bağlantı için tüm hüküm ve koşulları otomatik olarak kabul etmesine izin verir.
- **El Ile Wi-Fi yapılandırması**: **Blok** , cihazların MDM sunucusu yüklü ağlarının dışında Wi-Fi ' e bağlanmasını engeller. **Yapılandırılmadı** (varsayılan) son kullanıcıların kendi Wi-Fi bağlantısı ağ SSID 'lerini eklemesine ve yapılandırmasına izin verir.
- **Wi-Fi tarama aralığı**: Cihazların Wi-Fi ağlarını ne sıklıkta tarayacağını girin. 1 (en sık) ile 500 (en az sık) arasında bir değer girin. Varsayılan değer `0` (sıfır).

### <a name="bluetooth"></a>Bluetooth

Bu ayarlar, [Bluetooth ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth)'sini kullanır; Ayrıca, desteklenen Windows sürümlerini de listeler.

- **Bluetooth**: **Blok** kullanıcıların Bluetooth 'u etkinleştirmelerini engeller. **Yapılandırılmadı** (varsayılan) cihazda Bluetooth 'a izin verir.
- **Bluetooth bulunabilirliği**: **Blok** , cihazın diğer Bluetooth özellikli cihazlar tarafından keşfedilmesini engeller. **Yapılandırılmadı** (varsayılan), kulaklık gibi diğer Bluetooth özellikli cihazların cihazı bulmasını sağlar.
- **Bluetooth önceden eşleme**: **Blok** , belirli Bluetooth cihazlarının bir konak cihazla otomatik olarak eşleşmesini önler. **Yapılandırılmadı** (varsayılan) konak cihazla otomatik eşleştirmeye izin verir.
- **Bluetooth tanıtımı**: **Blok** , cihazın Bluetooth tanıtımları göndermesini engeller. **Yapılandırılmadı** (varsayılan) cihazın Bluetooth tanıtımları göndermesini sağlar.
- **Bluetooth izin verilen hizmetler**: Izin verilen Bluetooth hizmetleri ve profillerinin bir listesini gibi onaltılık dizeler `{782AFCFC-7CAA-436C-8BF0-78CD0FFBD4AF}`olarak ekleyin.

  [Servicesallowedlist kullanım kılavuzu](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#servicesallowedlist-usage-guide) , hizmet listesi hakkında daha fazla bilgi içerir.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="cloud-and-storage"></a>Bulut ve Depolama

Bu ayarlar, [CSP hesabı ilkesini](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-accounts)kullanır; Ayrıca, desteklenen Windows sürümlerini de listeler.

- **Microsoft hesabı**: **Blok** , son kullanıcıların Microsoft hesabı cihazla ilişkilendirilmesini engeller. **Yapılandırılmadı** (varsayılan) Microsoft hesabı ekleme ve kullanmaya izin verir.
- **Microsoft hesabı olmayan**: **Block** , son kullanıcıların kullanıcı arabirimini kullanarak Microsoft olmayan hesaplar eklemesini önler. **Yapılandırılmadı** (varsayılan), kullanıcıların bir Microsoft hesabı ile ilişkilendirilmemiş e-posta hesapları eklemesine olanak sağlar.
- **Microsoft hesabı Için ayarları eşitleme**: **Yapılandırılmadı** (varsayılan) bir Microsoft hesabı ilişkili cihaz ve uygulama ayarlarının cihazlar arasında eşitlenmesine izin verir. **Blok** bu eşitlemeyi engelliyor.
- **Microsoft hesabı oturum açma Yardımcısı**: **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, son kullanıcılar **Microsoft hesabı oturum açma Yardımcısı** (wlidsvc) hizmetini başlatabilir ve durdurabilir. Bu işletim sistemi hizmeti, kullanıcıların Microsoft hesabı oturum açmasına olanak tanır. **Disable** , son kullanıcıların Microsoft oturum açma Yardımcısı hizmetini (wlidsvc) denetlemesini engeller.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="cloud-printer"></a>Bulut Yazıcı

Bu ayarlar [Enterprisecloudprint ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-enterprisecloudprint)'sini kullanır; Ayrıca, desteklenen Windows sürümlerini de listeler.

- **Yazıcı bulma URL 'si**: Bulut yazıcılarını bulmak için URL 'YI girin. Örneğin, şunu girin: `https://cloudprinterdiscovery.contoso.com`.
- **Yazıcı erişim yetkilisi URL 'si**: OAuth belirteçlerini almak için kimlik doğrulama uç noktası URL 'sini girin. Örneğin, şunu girin: `https://azuretenant.contoso.com/adfs`.
- **Azure yerel istemci uygulama GUID 'si**: OAuthAuthority 'den OAuth belirteçleri almaya izin verilen bir istemci uygulamasının GUID 'sini girin. Örneğin, şunu girin: `E1CF1107-FF90-4228-93BF-26052DD2C714`.
- **Yazdırma hizmeti kaynak URI 'si**: Azure portal yapılandırılmış yazdırma hizmeti için OAuth Kaynak URI 'sini girin. Örneğin, şunu girin: `http://MicrosoftEnterpriseCloudPrint/CloudPrint`.
- **Sorgulanacak en fazla yazıcı**: Sorgulanmasını istediğiniz en fazla yazıcı sayısını girin. Varsayılan değer `20` şeklindedir.
- **Yazıcı bulma hizmeti kaynak URI 'si**: Azure portal için yapılandırılmış yazıcı bulma hizmeti OAuth Kaynak URI 'sini girin. Örneğin, şunu girin: `http://MopriaDiscoveryService/CloudPrint`.

> [!TIP]
> Bir [Windows Server hibrit bulutu](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-overview)oluşturduktan sonra, bu ayarları yapılandırabilir ve ardından Windows cihazlarınıza dağıtabilirsiniz.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="control-panel-and-settings"></a>Denetim Masası ve Ayarlar

- **Ayarlar uygulaması**: **Block** , son kullanıcıların Windows ayarları uygulamasına erişmesini engeller. **Yapılandırılmadı** (varsayılan), kullanıcıların cihazda Ayarlar uygulamasını açmasına olanak sağlar.
  - **Sistem**: **Blok** , ayarlar uygulamasının sistem alanına erişimi engeller. **Yapılandırılmadı** (varsayılan) erişim sağlar.
    - **Güç ve uyku ayarlarının değiştirilmesi** (yalnızca masaüstü): **Blok** , son kullanıcıların cihazdaki güç ve uyku ayarlarını değiştirmesini engeller. **Yapılandırılmadı** (varsayılan) kullanıcıların güç ve uyku ayarlarını değiştirmesine izin verir.
  - **Cihazlar**: **Blok** , cihazdaki ayarlar uygulamasının cihazlar alanına erişimi engeller. **Yapılandırılmadı** (varsayılan) erişim sağlar.
  - **Ağ Internet**: **Blok** , cihazdaki ayarlar uygulamasının ağ & Internet alanına erişimi engeller. **Yapılandırılmadı** (varsayılan) erişim sağlar.
  - **Kişiselleştirme**: **Blok** , cihazdaki ayarlar uygulamasının kişiselleştirme alanına erişimi engeller. **Yapılandırılmadı** (varsayılan) erişim sağlar.
  - **Uygulamalar**: **Blok** , cihazdaki ayarlar uygulamasının uygulamalar alanına erişimi engeller. **Yapılandırılmadı** (varsayılan) erişim sağlar.
  - **Hesaplar**: **Blok** , cihazdaki ayarlar uygulamasının hesaplar alanına erişimi engeller. **Yapılandırılmadı** (varsayılan) erişim sağlar.
  - **Saat ve dil**: **Blok** , cihazdaki ayarlar uygulamasının zaman & dil alanına erişimi engeller. **Yapılandırılmadı** (varsayılan) erişim sağlar.
    - **Sistem saati değişikliği**: **Block** , son kullanıcıların cihazdaki tarih ve saat ayarlarını değiştirmesini engeller. **Yapılandırılmadı** , kullanıcıların bu ayarları değiştirmesine izin verir.
    - **Bölge ayarları değişikliği** (yalnızca masaüstü): **Block** , son kullanıcıların cihazdaki bölge ayarlarını değiştirmesini engeller. **Yapılandırılmadı** , kullanıcıların bu ayarları değiştirmesine izin verir.
    - **Dil ayarlarının değiştirilmesi (yalnızca masaüstü)** : **Block** , son kullanıcıların cihazdaki dil ayarlarını değiştirmesini engeller. **Yapılandırılmadı** , kullanıcıların bu ayarları değiştirmesine izin verir.

      [Ayarlar ilkesi CSP 'si](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings)

  - **Oyun**: **Blok** , cihazdaki ayarlar uygulamasının oyun alanına erişimi engeller. **Yapılandırılmadı** (varsayılan) erişim sağlar.
  - **Erişim kolaylığı**: **Blok** , cihazdaki ayarlar uygulamasının erişim kolaylığı alanına erişimi engeller. **Yapılandırılmadı** (varsayılan) erişim sağlar.
  - **Gizlilik**: **Blok** , cihazdaki ayarlar uygulamasının gizlilik alanına erişimi engeller. **Yapılandırılmadı** (varsayılan) erişim sağlar.
  - **Güncelleştirme ve güvenlik**: **Blok** , cihazdaki ayarlar uygulamasının güncelleştirme & güvenlik alanına erişimi engeller. **Yapılandırılmadı** (varsayılan) erişim sağlar.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="display"></a>Görüntüle

Bu ayarlar, [görüntüleme ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-display)'yi kullanır; Ayrıca, desteklenen Windows sürümlerini de listeler.

GDI DPı ölçeklendirme, DPı kullanmayan uygulamaların, monitör DPı 'si ile uyumlu olmasını sağlar.

- **Uygulamalar IÇIN GDI ölçeklendirmeyi aç**: GDI DPı ölçeklendirme özelliğinin açık olmasını istediğiniz eski uygulamaları **ekleyin** . Örneğin `filename.exe` veya `%ProgramFiles%\Path\Filename.exe` girin.

  Listedeki tüm eski uygulamalar için GDI DPı ölçeklendirme açıktır.

- **Uygulamalar IÇIN GDI ölçeklendirmeyi**kapat: GDI DPı ölçeklendirme özelliğinin kapalı olmasını istediğiniz eski uygulamaları **ekleyin** . Örneğin `filename.exe` veya `%ProgramFiles%\Path\Filename.exe` girin.

  Listedeki tüm eski uygulamalar için GDI DPı ölçeklendirme kapalıdır.

Ayrıca, uygulama listesiyle bir. csv dosyasını **Içeri aktarabilirsiniz** .

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="general"></a>Genel

Bu ayarlar, [deneyim ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience)'yi kullanır; Ayrıca, desteklenen Windows sürümlerini de listeler. 

- **Ekran yakalama** (yalnızca mobil): **Blok** , son kullanıcıların cihazda ekran görüntüleri almasını engeller. **Yapılandırılmadı** (varsayılan) bu özelliğe izin verir.
- **Kopyala ve Yapıştır (yalnızca mobil)** : **Blok** , son kullanıcıların cihazdaki uygulamalar arasında kopyalama ve yapıştırmayı kullanmasını engeller. **Yapılandırılmadı** (varsayılan) bu özelliğe izin verir.
- **El ile kayıt kaldırma**: **Blok** , son kullanıcıların cihazdaki çalışma alanı denetim masasını kullanarak çalışma alanı hesabını silmesini engeller. **Yapılandırılmadı** (varsayılan) bu özelliğe izin verir.

  Bu ilke ayarı, bilgisayar Azure AD 'ye katılırsa ve otomatik kayıt etkinse uygulanmaz.

- **El ile kök sertifika yükleme** (yalnızca mobil): **Blok** , son kullanıcıların kök sertifikaları ve ara Cap sertifikalarını el ile yüklemesini engeller. **Yapılandırılmadı** (varsayılan) bu özelliğe izin verir.
- **Kamera**: **Blok** , son kullanıcıların cihazdaki kamerayı kullanmasını engeller. **Yapılandırılmadı** (varsayılan) bu özelliğe izin verir.
- **OneDrive dosya eşitleme**: **Blok** , son kullanıcıların dosyaları OneDrive 'a bilgisayardan eşitlemesini engeller. **Yapılandırılmadı** (varsayılan) bu özelliğe izin verir.
- **Çıkarılabilir depolama birimi**: **Blok** , son KULLANıCıLARıN cihazla SD kartlar gibi harici depolama cihazlarını kullanmasını engeller. **Yapılandırılmadı** (varsayılan) bu özelliğe izin verir.
- **Coğrafi konum**: **Block** , son kullanıcıların cihazdaki konum hizmetlerini açmasını önler. **Yapılandırılmadı** (varsayılan) bu özelliğe izin verir.
- **Internet paylaşımı**: **Blok** , cihazda Internet bağlantısı paylaşımını önler. **Yapılandırılmadı** (varsayılan) bu özelliğe izin verir.
- **Telefon sıfırlaması**: **Blok** , son kullanıcıların cihazda fabrika sıfırlaması gerçekleştirmesini engeller. **Yapılandırılmadı** (varsayılan) bu özelliğe izin verir.
- **USB bağlantısı**: **Blok** , CIHAZDAKI bir USB bağlantısı aracılığıyla dış depolama cihazlarına erişimi engeller. **Yapılandırılmadı** (varsayılan) bu özelliğe izin verir. USB ücretlendirme bu ayardan etkilenmez.
- **Hırsızlık önleme modu** (yalnızca mobil): **Blok** , son kullanıcıların cihazda antihırsızlık modu tercihini seçmesini engeller. **Yapılandırılmadı** (varsayılan) bu özelliğe izin verir.
- **Cortana**: **Engelle** cihazda Cortana sesli yardımcısını devre dışı bırak. Cortana devre dışı bırakıldığında, kullanıcılar hala cihazdaki öğeleri bulmak için arama yapabilir. **Yapılandırılmadı** (varsayılan) Cortana 'Ya izin verir.
- **Ses kaydı** (yalnızca mobil): **Blok** , son kullanıcıların cihazda cihaz ses kaydedicisi 'ni kullanmasını engeller. **Yapılandırılmadı** (varsayılan), uygulamalar için ses kaydına izin verir.
- **Cihaz adı değişikliği** (yalnızca mobil): **Block** , son kullanıcıların cihazın adını değiştirmesini engeller. **Yapılandırılmadı** (varsayılan) bu özelliğe izin verir.
- **Sağlama paketleri Ekle**: **Blok** , cihaza sağlama paketlerini yükleyen çalışma zamanı yapılandırma aracısını engeller. **Yapılandırılmadı** (varsayılan) bu özelliğe izin verir.
- **Sağlama paketlerini kaldır**: **Blok** , cihazdaki sağlama paketlerini kaldıran çalışma zamanı yapılandırma aracısını engeller. **Yapılandırılmadı** (varsayılan) bu özelliğe izin verir.
- **Cihaz bulma**: **Blok** , cihazın diğer cihazlar tarafından bulunmasını engeller. **Yapılandırılmadı** (varsayılan) bu özelliğe izin verir.
- **Görev değiştirici** (yalnızca mobil): **Blok** , cihazda görev değiştirmeyi engeller. **Yapılandırılmadı** (varsayılan) bu özelliğe izin verir.
- **SIM kart hatası iletişim kutusu** (yalnızca mobil): SIM kart algılanmazsa, cihazda hata iletilerinin gösterilmesini **engelleyin** . **Yapılandırılmadı** (varsayılan) hata iletilerini gösterir.
- **Mürekkep çalışma alanı**: Kullanıcının mürekkep çalışma alanına erişip erişene olduğunu ve nasıl erişebileceğini seçin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Mürekkep çalışma alanını açar ve kullanıcının onu kilit ekranı üzerinde kullanmasına izin verilir.
  - **Kilit ekranında devre dışı bırakıldı**: Mürekkep çalışma alanı etkindir ve özellik açıktır. Ancak, Kullanıcı kilit ekranının üzerine erişemez.
  - **Devre dışı**: Mürekkep çalışma alanına erişim devre dışı bırakıldı. Özellik kapalı.

  [WindowsInkWorkspace ilkesi CSP 'si](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace)

- **Otomatik yeniden dağıtım**: **Izin ver** ' i seçtiğinizde, yönetici haklarına sahip kullanıcılar cihaz kilidi ekranında **CTRL + Win + R** kullanarak tüm Kullanıcı verilerini ve ayarlarını silebilir. Cihaz otomatik olarak yeniden yapılandırılır ve yönetime yeniden kaydedilir. **Yapılandırılmadı** (varsayılan) ayarı bu özelliği engeller.
- **Kullanıcıların cihaz kurulumu sırasında ağa bağlanmasını iste**: Windows kurulumu sırasında ağ sayfasını geçmeden önce cihazın bir ağa bağlanması için **gerektir** ' i seçin. **Yapılandırılmadı** (varsayılan), bir ağa bağlı olmasalar bile kullanıcıların ağ sayfasını geçmemesine izin verir.

  Bu ayar, cihazın bir sonraki temizlenmeden veya sıfırlanışında etkili olur. Diğer Intune yapılandırmaları gibi, yapılandırma ayarlarını almak için cihazın Intune tarafından kaydedilmiş ve yönetilen olması gerekir. Ancak, kaydedildikten ve ilkeleri aldıktan sonra, bir sonraki Windows kurulumu sırasında cihazın sıfırlanması ayarı uygular.

- **Doğrudan bellek erişimi**: **Blok** , Kullanıcı Windows 'a oturum açana kadar tüm ETKIN takılabilir PCI aşağı akış bağlantı noktaları için doğrudan bellek ERIŞIMINI (DMA) engeller. **Etkin** (varsayılan), bir Kullanıcı oturum açmamış olsa bile DMA erişimine izin verir.

  'SINI [DataProtection/AllowDirectMemoryAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection#dataprotection-allowdirectmemoryaccess)

- **Görev Yöneticisi 'Nden son işlem**: Bu ayar, yönetici olmayanların Görev Yöneticisi 'nin görevleri sonlandırıp kullanıp kullanamayacağını belirler. **Blok** , standart kullanıcıların (yönetici olmayanlar), Görev Yöneticisi 'ni kullanarak cihazdaki bir işlem veya görevi sonlandırmasını önler. **Yapılandırılmadı** (varsayılan), standart kullanıcıların, Görev Yöneticisi 'Ni kullanarak bir işlem veya görevi sonlandıralmasına izin verir.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="locked-screen-experience"></a>Kilit ekranı deneyimi

- **İşlem merkezi bildirimleri (yalnızca mobil)** : **Blok** , işlem merkezi bildirimlerinin cihaz kilitleme ekranında gösterilmesini engeller. **Yapılandırılmadı** (varsayılan) kullanıcıların hangi uygulamaların kilit ekranında bildirimleri göstermesini seçmesine olanak sağlar.

  [AboveLock/AllowActionCenterNotifications CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock#abovelock-allowactioncenternotifications)

- **Kilitli ekran resmi URL 'si (yalnızca masaüstü)** : Windows kilit ekranı duvar kağıdı olarak kullanılan JPG, JPEG veya PNG biçimindeki bir resmin URL 'sini girin. Örneğin, şunu girin: `https://contoso.com/image.png`. Bu ayar görüntüyü kilitler ve daha sonra değiştirilemez.
- **Kullanıcı tarafından yapılandırılabilir ekran zaman aşımı (yalnızca mobil)** : **Izin ver** , kullanıcıların ekran zaman aşımını yapılandırmalarına olanak tanır. **Yapılandırılmadı** (varsayılan) kullanıcılara bu seçeneği vermez.

  [DeviceLock/AllowScreenTimeoutWhileLockedUserConfig CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-allowscreentimeoutwhilelockeduserconfig)

- **Kilitli ekranda Cortana** (yalnızca masaüstü): **Blok** , kullanıcıların cihaz kilitleme ekranında olduğunda Cortana ile etkileşime geçmesini engeller. **Yapılandırılmadı** (varsayılan) Cortana ile etkileşime izin verir.

  [AboveLock/AllowCortanaAboveLock CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock#abovelock-allowcortanaabovelock)

- **Kilitli ekranda bildirim bildirimleri**: **Blok** , cihaz kilitleme ekranında bildirim bildirimlerinin gösterilmesini engeller. **Yapılandırılmadı** (varsayılan) bu bildirimlere izin verir.

  [AboveLock/Allowtoine CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock#abovelock-allowtoasts)

- **Ekran zaman aşımı (yalnızca mobil)** : Ekran kilitlemeden ekrana kadar geçen süreyi (saniye cinsinden) ayarlayın. Desteklenen değerler 11-1800 ' dir. Örneğin, bu zaman `300` aşımını 5 dakikaya ayarlamak için girin.

  [DeviceLock/ScreenTimeoutWhileLocked CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-screentimeoutwhilelocked)

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="messaging"></a>Gönderip

Bu ayarlar, [ileti ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-messaging)'sini kullanır; Ayrıca, desteklenen Windows sürümlerini de listeler.

- **İleti eşitleme (yalnızca mobil)** : **Blok** , metin iletilerinin yedeklenmesini ve geri yüklenmesini devre dışı bırakır ve iletileri Windows cihazları arasında eşitlemeyi engeller. Devre dışı bırakma, bilgilerin kuruluşun denetimi dışındaki sunucularda depolanmasını önlemeye yardımcı olur. **Yapılandırılmadı** (varsayılan), kullanıcıların bu ayarları değiştirmesine ve iletilerini eşitlemesine izin verir.
- **MMS (yalnızca mobil)** : **Blok** , cihazda MMS gönderme ve alma işlevini devre dışı bırakır. Kuruluşlar için bu ilkeyi, denetim veya yönetim gereksiniminin parçası olarak cihazlarda MMS 'yi devre dışı bırakmak için kullanın. **Yapılandırılmadı** (varsayılan) MMS gönderme ve alma olanağı sağlar.
- **RCS (yalnızca mobil)** : **Blok** , cihaza zengin iletişim hizmetleri (RCS) gönderme ve alma işlevini devre dışı bırakır. Kuruluşlar için bu ilkeyi, denetim veya yönetim gereksiniminin parçası olarak cihazlarda RCS 'yi devre dışı bırakmak için kullanın. **Yapılandırılmadı** (varsayılan) RCS 'nin gönderme ve alma sağlar.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="microsoft-edge-browser"></a>Microsoft Edge Tarayıcısı

Bu ayarlar, desteklenen Windows sürümlerini de listeleyen [tarayıcı ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser)'sini kullanır.

### <a name="use-microsoft-edge-kiosk-mode"></a>Microsoft Edge bilgi noktası modunu kullan

Kullanılabilir ayarlar, seçtiğiniz seçeneğe göre değişir. Seçenekleriniz şunlardır:

- **Hayır** (varsayılan): Microsoft Edge bilgi noktası modunda çalışmıyor. Tüm Microsoft Edge ayarları, değişiklik ve yapılandırma için kullanılabilir.
- **Dijital/Etkileşimli imza (tek uygulama bilgi noktası)** : Microsoft Edge bilgi noktası modu 'nun yalnızca Windows 10 tek uygulama kiosks üzerinde kullanılması için dijital/Etkileşimli imza modu için geçerli olan Microsoft Edge ayarlarını filtreler. Bir URL tam ekran açmak için bu ayarı seçin ve yalnızca bu Web sitesindeki içeriği gösterin. [Dijital Işaretleri ayarla](https://docs.microsoft.com/windows/configuration/setup-digital-signage) özelliği, bu özellik hakkında daha fazla bilgi sağlar.
- **InPrivate genel göz atma (tek uygulama bilgi noktası)** : Windows 10 tek sunuculu bilgi noktaları için kullanılmak üzere InPrivate genel göz atma modu için geçerli olan Microsoft Edge ayarlarını filtreler. Microsoft Edge 'in çok sekmeli bir sürümünü çalıştırır.
- **Normal mod (çok uygulama bilgi noktası)** : Normal Microsoft Edge bilgi noktası modu için geçerli olan Microsoft Edge ayarlarını filtreler. Tüm göz atma özellikleriyle Microsoft Edge 'in tam bir sürümünü çalıştırır.
- **Genel göz atma (çok uygulama bilgi noktası)** : Windows 10 çok uygulama bilgi noktası üzerinde genel göz atma için geçerli olan Microsoft Edge ayarlarını filtreler.  Microsoft Edge InPrivate 'ın çok bölgeli bir sürümünü çalıştırır.

> [!TIP]
> Bu seçeneklerin ne yaptığı hakkında daha fazla bilgi için bkz. [Microsoft Edge bilgi noktası modu yapılandırma türleri](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

Bu cihaz kısıtlamaları profili, [Windows bilgi noktası ayarları](kiosk-settings-windows.md)kullanılarak oluşturduğunuz bilgi noktası profiliyle doğrudan ilgilidir. Özetlemek için:

1. Cihazı bilgi noktası modunda çalıştırmak için [Windows bilgi noktası ayarları](kiosk-settings-windows.md) profilini oluşturun. Uygulama olarak Microsoft Edge ' i seçin ve bilgi noktası profilinde Microsoft Edge bilgi noktası modunu ayarlayın.
2. Bu makalede açıklanan cihaz kısıtlamaları profilini oluşturun ve Microsoft Edge 'de izin verilen belirli özellikleri ve ayarları yapılandırın. Bilgi noktası profilinizde ([Windows bilgi noktası ayarları](kiosk-settings-windows.md)) seçili olan Microsoft Edge bilgi noktası modu türünü seçtiğinizden emin olun. 

    [Desteklenen bilgi noktası modu ayarları](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-policies-for-kiosk-mode) harika bir kaynaktır.

> [!IMPORTANT] 
> Bu Microsoft Edge profilini, bilgi noktası profilinizle aynı cihazlara ([Windows bilgi noktası ayarları](kiosk-settings-windows.md)) atadığınızdan emin olun.

[ConfigureKioskMode CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-configurekioskmode)

### <a name="start-experience"></a>Deneyim başlangıcı

- **Microsoft Edge 'i Ile Başlat**: Microsoft Edge başladığında hangi sayfaların açılacağını seçin. Seçenekleriniz şunlardır:
  - **Özel başlangıç sayfaları**: Başlangıç sayfalarını `http://www.contoso.com`(gibi) girin. Microsoft Edge, girdiğiniz başlangıç sayfalarını yükler.
  - **Yeni sekme sayfası**: **Yeni sekme URL 'si** ayarında Microsoft Edge yükleme her şey girilir.
  - **Son oturum sayfası**: Microsoft Edge son oturum sayfasını yükler.
  - **Yerel uygulama ayarlarındaki sayfaları Başlat**: Microsoft Edge, işletim sistemi tarafından tanımlanan varsayılan başlangıç sayfası ile başlar.

- **Kullanıcının başlangıç sayfalarını değiştirmesine Izin ver**: **Evet** (varsayılan), kullanıcıların başlangıç sayfalarını değiştirmesine izin verir. Yöneticiler, `EdgeHomepageUrls` varsayılan olarak Microsoft Edge 'i açtığınızda kullanıcıların göreceği başlangıç sayfalarını girmek için kullanabilir. **Hayır** , kullanıcıların başlangıç sayfalarını değiştirmesini engeller.
- **Yeni sekme sayfasında Web Içeriğine Izin ver**: **Evet** (varsayılan) olarak ayarlandığında, Microsoft Edge **Yeni sekme URL 'si** ayarında girilen URL 'yi açar. **Yeni sekme URL 'si** ayarı boşsa, Microsoft Edge, Microsoft Edge ayarlarında listelenen yeni sekme sayfasını açar. Kullanıcılar bunu değiştirebilir. **Hayır**olarak ayarlandığında, Microsoft Edge boş bir sayfayla yeni bir sekme açar. Kullanıcılar bu değişikliği değiştiremezler.
- **Yeni sekme URL 'si**: Yeni sekme sayfasında açılacak URL 'YI girin. Örneğin `https://www.bing.com` veya `https://www.contoso.com` girin.

- **Giriş düğmesi**: Giriş düğmesi seçildiğinde ne olacağını seçin. Seçenekleriniz şunlardır:
  - **Başlangıç sayfaları**: **Microsoft Edge** 'i ayarla seçeneğiyle seçtiğiniz seçeneği açar
  - **Yeni sekme sayfası**: **Yeni sekme URL 'si** ayarında girdiğiniz URL 'yi açar.
  - **Giriş düğmesi URL 'si**: Açılacak URL 'YI girin. Örneğin `https://www.bing.com` veya `https://www.contoso.com` girin.
  - **Giriş düğmesini Gizle**: Giriş düğmesini gizler
- **Kullanıcıların giriş düğmesini değiştirmesine Izin ver**: **Evet** seçeneği, kullanıcıların giriş düğmesini değiştirmesine izin verir. Kullanıcının değişiklikleri, giriş düğmesine tüm yönetici ayarlarını geçersiz kılar. **Hayır** (varsayılan), kullanıcıların giriş düğmesini yöneticinin nasıl yapılandırmalarından değiştirmesini engeller.
- **Ilk çalıştırma deneyimini göster sayfası (yalnızca mobil)** : **Evet** (varsayılan) Microsoft Edge 'de ilk kullanıma giriş sayfasını gösterir. **Hayır** , Microsoft Edge 'i ilk kez çalıştırdığınızda giriş sayfasının gösterilmesini engeller. Bu özellik, bu sayfayı engellemek için sıfır emisyonlarını yapılandırmasına kayıtlı kuruluşlar gibi kuruluşlara izin verir.
- **Ilk çalıştırma DENEYIMI URL listesi konumu** (Yalnızca Windows 10 Mobile): İlk çalıştırma sayfası URL 'lerini içeren XML dosyasına işaret eden URL 'YI girin. Örneğin, şunu girin: `https://www.contoso.com/sites.xml`.

- **Boşta kalma zamanından sonra tarayıcıyı yenile**: Tarayıcı yenilenene kadar boşta kalma dakikalarının sayısını 0-1440 dakikadan itibaren girin. Varsayılan değer `5` dakikadır. (Sıfır) `0` olarak ayarlandığında tarayıcı, boşta kaldıktan sonra yenilenmez.

  Bu ayar yalnızca [InPrivate genel göz atma (tek uygulama bilgi noktası)](#use-microsoft-edge-kiosk-mode)içinde çalıştırılırken kullanılabilir.

- **Açılır pencerelere Izin ver** (yalnızca masaüstü): **Evet** (varsayılan) Web tarayıcısında açılır pencerelere izin verir. **Hayır** , tarayıcıda açılır pencereleri engeller.
- **Internet Explorer 'a intranet trafiği gönder** (Yalnızca masaüstü): **Evet** seçeneği, kullanıcıların intranet Web sitelerini Microsoft Edge yerine Internet Explorer 'da açmasına olanak sağlar. Bu ayar geriye dönük uyumluluk içindir. **Hayır** (varsayılan) kullanıcıların Microsoft Edge kullanmasına izin verir.
- **Kuruluş modu Site listesi konumu** (Yalnızca masaüstü): Kurumsal modda açık bir Web siteleri listesi içeren XML dosyasına işaret eden URL 'YI girin. Kullanıcılar bu listeyi değiştiremez. Örneğin, şunu girin: `https://www.contoso.com/sites.xml`.
- **Internet Explorer 'da siteler açılırken ileti**: Microsoft Edge 'i bir site Internet Explorer 11 ' de açılmadan önce bildirim gösterecek şekilde yapılandırmak için bu ayarı kullanın. Seçenekleriniz şunlardır:
  - **İleti gösterme**: İşletim sistemi varsayılan davranışı kullanılır, bu durum bir ileti göstermez.
  - **Sitenin Internet Explorer 11 ' de açıldığını belirten Iletiyi göster**: IE 'de siteleri açarken iletiyi göster. IE 'de açık siteler. 
  - **Microsoft Edge 'de siteleri açma seçeneği içeren Iletiyi göster**: Siteleri Edge 'de açarken iletiyi gösterir. Bu ileti, kullanıcıların IE yerine Microsoft Edge 'i seçebilmeleri için **Microsoft Edge bağlantısını kullanmaya devam** eder.

  > [!IMPORTANT]
  > Bu ayar, **Kurumsal mod site listesi konumu** ayarını, **Intranet trafiğini Internet Explorer 'a gönder** ayarını veya her iki ayarı da kullanmanızı gerektirir.

- **Microsoft uyumluluk listesine Izin ver**: **Evet** (varsayılan) bir Microsoft Uyumluluk Listesi kullanılmasına izin verir. **Hayır** , Microsoft Edge 'de Microsoft Uyumluluk Listesi 'ni engeller. Microsoft 'un bu listesi, Microsoft Edge 'in bilinen uyumluluk sorunlarına sahip siteleri düzgün şekilde görüntülemesine yardımcı olur.
- **Başlangıç sayfaları ve yeni sekme sayfası Önyükle**: **Evet** (varsayılan) işletim sistemi varsayılan davranışını kullanır, bu da bu sayfaların önyüklenmesi olabilir. Önceden yükleme, Microsoft Edge 'i başlatma ve yeni sekmeler yükleme süresini en aza indirir. **Hayır** , Microsoft Edge 'in başlangıç sayfalarını ve yeni sekme sayfasını önyüklenmesini engeller.
- **Başlangıç sayfalarını ve yeni sekme sayfasını önceden başlatın**: **Evet** (varsayılan) işletim sistemi varsayılan davranışını kullanır, bu da bu sayfaların ön başlatması olabilir. Önceden başlatma, Microsoft Edge performansına yardımcı olur ve Microsoft Edge 'i başlatmak için gereken süreyi en aza indirir. **Hayır** , Microsoft Edge 'in başlangıç sayfalarını ve yeni sekme sayfasını başlatmasını önler.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

### <a name="favorites-and-search"></a>Sık Kullanılanlar ve arama

- **Sık Kullanılanlar çubuğunu göster**: Herhangi bir Microsoft Edge sayfasında Sık Kullanılanlar çubuğunda ne olacağını seçin. Seçenekleriniz şunlardır:
  - **Başlangıç ve yeni sekme sayfalarında**: Microsoft Edge başladığında ve tüm sekme sayfalarında Sık Kullanılanlar çubuğunu gösterir. Son kullanıcılar bu ayarı değiştirebilir.
  - **Tüm sayfalarda**: Tüm sayfalarda Sık Kullanılanlar çubuğunu gösterir. Son kullanıcılar bu ayarı değiştiremezler.
  - **Gizli**: Tüm sayfalarda Sık Kullanılanlar çubuğunu gizler. Son kullanıcılar bu ayarı değiştiremezler.
- **Sık kullanılanlara değişikliklere Izin ver**: **Evet** (varsayılan), kullanıcıların listeyi değiştirmesine izin veren işletim sistemi varsayılanını kullanır. **Hayır** , son kullanıcıların sık kullanılanlar listesini eklemesini, içeri aktarmayı, sıralamasını veya düzenlemesini engeller.
  - **Sık Kullanılanlar listesi**: Sık Kullanılanlar dosyasına bir URL listesi ekleyin. Örneğin, ekleyin `http://contoso.com/favorites.html`.
- **Sık kullanılanları Microsoft tarayıcıları arasında Eşitle** (Yalnızca masaüstü): **Evet** , Windows 'un Internet Explorer ve Microsoft Edge arasında sık kullanılanları eşitlemesine zorlar. Sık Kullanılanlar için eklemeler, silmeler, değişiklikler ve düzen değişiklikleri, tarayıcılar arasında paylaşılır.  **Hayır** (varsayılan) işletim sistemi varsayılanını kullanır, bu da kullanıcılara tarayıcılar arasında sık kullanılanları eşitleme seçeneği verebilir.
- **Varsayılan arama motoru**: Cihazda varsayılan arama altyapısını seçin. Son kullanıcılar bu değeri istediği zaman değiştirebilir. Seçenekleriniz şunlardır:
  - İstemci Microsoft Edge ayarları 'nda arama altyapısı
  - Cıları
  - Google
  - Yahoo!
  - Özel değer: **OpenSearch XML URL 'si**içinde, kısa adı ve arama altyapısının URL 'sini IÇEREN bir https URL 'sini en düşük düzeyde girin. Örneğin, şunu girin: `https://www.contoso.com/opensearch.xml`.
- **Arama önerilerini göster**: **Evet** (varsayılan), adres çubuğuna arama ifadeleri yazarken arama motorunuzun siteler önermesini sağlar. **Hayır** bu özelliği engeller.
- **Arama altyapısında değişikliklere Izin ver**: **Evet** (varsayılan), kullanıcıların yeni arama motorları eklemesine veya Microsoft Edge 'de varsayılan arama altyapısını değiştirmesine izin verir. Kullanıcıların arama altyapısını özelleştirmesini engellemek için **Hayır** ' ı seçin.

  Bu ayar yalnızca [normal modda (çok uygulama bilgi noktası)](#use-microsoft-edge-kiosk-mode)çalışırken kullanılabilir.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

### <a name="privacy-and-security"></a>Gizlilik ve güvenlik

- **InPrivate gözatmaya Izin ver**: **Evet** (varsayılan), Microsoft Edge 'de InPrivate göz atmaya izin verir. Tüm InPrivate sekmeleri kapatıldıktan sonra Microsoft Edge, tarama verilerini cihazdan siler. **Hayır** , son kullanıcıların InPrivate Gözatma oturumlarını açmasını önler.
- **Gözatma geçmişini kaydet**: **Evet** (varsayılan) Microsoft Edge 'de gözatma geçmişinin kaydedilmesine izin verin. **Hayır** , gözatma geçmişinin kaydedilmesini engeller.
- **Çıkışta tarama verilerini temizle** (yalnızca masaüstü): **Evet** , Kullanıcı Microsoft Edge 'den çıktığında geçmişi temizler ve verilere göz atar. **Hayır** (varsayılan) işletim sistemi varsayılanını kullanır, bu da tarama verilerini önbelleğe alabilir.
- **Kullanıcı cihazları arasında tarayıcı ayarlarını Eşitle**: Cihazlar arasında tarayıcı ayarlarını nasıl eşitlemek istediğinizi seçin. Seçenekleriniz şunlardır:
  - **İzin ver**: Kullanıcı cihazları arasında Microsoft Edge tarayıcı ayarlarının eşitlenmesine izin ver
  - **Kullanıcı geçersiz kılmayı engelle ve Etkinleştir**: Kullanıcıların cihazları arasında Microsoft Edge tarayıcı ayarlarının eşitlenmesini engelleyin. Kullanıcılar bu ayarı geçersiz kılabilir.
  - **Engelle**: Kullanıcı cihazları arasında Microsoft Edge tarayıcı ayarı eşitlemesini engelleyin. Kullanıcılar bu ayarı geçersiz kılamaz.

"Kullanıcı geçersiz kılmayı engelle" seçildiğinde, kullanıcı yönetici atamasını geçersiz kılabilir.

- **Parola yöneticisine Izin ver**: **Evet** (varsayılan), Microsoft Edge 'in otomatik olarak parola yöneticisini kullanmasına izin verir. Bu, kullanıcıların cihazdaki parolaları kaydetmesine ve yönetmesine olanak tanır. **Hayır** , Microsoft Edge 'In parola Yöneticisi 'ni kullanmasını engeller.
- **Tanımlama bilgileri**: Web tarayıcısında tanımlama bilgilerinin nasıl işleneceğini seçin. Seçenekleriniz şunlardır:
  - **İzin ver**: Tanımlama bilgileri cihazda depolanır.
  - **Tüm tanımlama bilgilerini engelle**: Tanımlama bilgileri cihazda depolanmaz.
  - **Yalnızca üçüncü taraf tanımlama bilgilerini engelle**: Üçüncü taraf veya iş ortağı tanımlama bilgileri cihazda depolanmaz.
- **Formlarda otomatik doldurmaya Izin ver**: **Evet** (varsayılan) Kullanıcıların tarayıcıdaki otomatik tamamlama ayarlarını değiştirmesine ve form alanlarını otomatik olarak doldurmasına izin verir. **Hayır** özelliği, Microsoft Edge 'de otomatik doldurma özelliğini devre dışı bırakır.
- **Do-Track üstbilgileri gönder**: **Evet** , izleme bilgisi isteyen web sitelerine Do-Not-Track üst bilgilerini gönderir (önerilir). **Hayır** (varsayılan), Web sitelerinin kullanıcıyı izlemesine izin veren üst bilgileri göndermez. Kullanıcı yapılandırabilir.
- **WebRTC localhost IP adresini göster**: **Evet** (varsayılan), bu protokol kullanılarak telefon aramaları yapıldığında kullanıcıların localhost IP adresinin gösterilmesine izin verir. **Hayır** , KULLANıCıLARıN localhost IP adresinin gösterilmesini engeller. 
- **Canlı kutucuk verileri koleksiyonuna Izin ver**: **Evet** (varsayılan), Microsoft Edge 'in başlangıç menüsüne sabitlenmiş canlı kutucukların bilgilerini toplamasını sağlar. **Hayır** , kullanıcılara sınırlı bir deneyim sağlayabilen bu bilgilerin toplanmasını engeller.
- **Kullanıcı, sertifika hatalarını geçersiz kılabilir**: **Evet** (varsayılan), kullanıcıların Güvenli Yuva Katmanı/Aktarım Katmanı Güvenliği (SSL/TLS) hataları olan Web sitelerine erişmesini sağlar. **Hayır** (Artırılmış güvenlik için önerilir), kullanıcıların Web sitelerine SSL veya TLS hatalarıyla erişmesini önler.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

### <a name="additional"></a>Ek

- **Microsoft Edge tarayıcısına Izin ver** (yalnızca mobil): **Evet** (varsayılan) mobil cihazda Microsoft Edge Web tarayıcısının kullanılmasına izin verir. **Hayır** , cihazda Microsoft Edge kullanımını engeller. **Hayır**' ı seçerseniz, diğer tek ayarlar yalnızca masaüstü için geçerlidir.
- **Adres çubuğu açılır listesine Izin ver**: **Evet** (varsayılan), Microsoft Edge 'in adres çubuğu açılır listesini öneriler listesiyle göstermesini sağlar. **Hayır** , Microsoft Edge 'in, yazarken açılan listede öneriler listesi göstermesini engeller. **Hayır**olarak ayarlandığında, şunları yapabilirsiniz:
  - Microsoft Edge ve Microsoft Hizmetleri arasındaki ağ bant genişliğini en aza indirmeye yardımcı olun.
  - Microsoft Edge > ayarlarını **Yazarken arama ve site önerilerini göster ' i** devre dışı bırakın.
- **Tam ekran moduna Izin ver**: **Evet** (varsayılan), Microsoft Edge 'in yalnızca Web içeriğini gösteren ve Microsoft Edge Kullanıcı arabirimini gizleyen tam ekran modunu kullanmasına izin verir. **Hayır** , Microsoft Edge 'de tam ekran modunu engeller.
- **Bayraklar sayfasına Izin ver**: **Evet** (varsayılan), `about:flags` sayfanın erişimine izin verebilecek işletim sistemi varsayılanını kullanır. Sayfa `about:flags` , kullanıcıların geliştirici ayarlarını değiştirmesine ve deneysel özellikleri etkinleştirmesine olanak sağlar. **Hayır** , son kullanıcıların Microsoft Edge 'de `about:flags` sayfaya erişmesini önler.
- **Geliştirici araçlarına Izin ver**: **Evet** (varsayılan), kullanıcıların varsayılan olarak Web sayfalarını oluşturmak ve hatalarını ayıklamak için F12 geliştirici araçlarını kullanmasına izin verir. **Hayır** , son kullanıcıların F12 geliştirici araçlarını kullanmasını önler.
- **JavaScript 'e Izin ver**: **Evet** (varsayılan) JavaScript gibi betiklerin Microsoft Edge tarayıcısında çalışmasına izin verir. **Hayır** , tarayıcıda Java betikleri çalıştırılmasını önler.
- **Kullanıcı, uzantıları yükleyebilir**: **Evet** (varsayılan) son kullanıcıların cihaza Microsoft Edge uzantıları yüklemesine izin verir. **Hayır** , yüklemeyi engeller.
- **Geliştirici uzantılarının dışarıdan yüklenmesine Izin ver**: **Evet** (varsayılan), dışarıdan yükleme izni olabilen işletim sistemi varsayılanını kullanır. Dışarıdan yükleme, doğrulanmamış uzantıları yükleyip çalıştırır. **Hayır** özelliği, **yükleme uzantıları** özelliğini kullanarak Microsoft Edge dışarıdan dışarıdan yüklemeye engel olur. PowerShell gibi diğer yollarla dışarıdan yükleme uzantılarının engellemez.
- **Gerekli uzantılar**: Microsoft Edge 'de son kullanıcılar tarafından kapatılanamaz uzantıları seçin. Paket aile adlarını girin ve **Ekle**' yi seçin. [Bir paket aile adı (PFN) bulma](https://docs.microsoft.com/sccm/protect/deploy-use/find-a-pfn-for-per-app-vpn) bazı rehberlik sağlar.

  Ayrıca paket aile adlarını içeren bir CSV dosyasını **Içeri aktarabilirsiniz** . Ya da, girdiğiniz paket aile adlarını **dışarı aktarın** .

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="network-proxy"></a>Ağ proxy’si

Bu ayarlar, desteklenen Windows sürümlerini de listeleyen [Networkproxy ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)'sini kullanır.

- **Proxy ayarlarını otomatik olarak algıla**: **Blok** , cihazın otomatik olarak bir proxy otomatik yapılandırma (PAC) betiğini algılamasını devre dışı bırakır. **Yapılandırılmadı** (varsayılan) bu özelliği sunar. Etkinleştirildiğinde, cihaz bir PAC betiğinin yolunu bulmaya çalışır.
- **Proxy betiği kullan**: Proxy sunucusunu yapılandırmak için PAC betiğinizin yolunu girmeye **Izin ver** ' i seçin. **Yapılandırılmadı** (varsayılan) bir PAC betiğine URL girmenize izin vermez.
  - **Kurulum komut dosyası adresi URL 'si**: Proxy sunucusunu yapılandırmak için kullanmak istediğiniz PAC betiğinin URL 'sini girin.
- **El ile proxy sunucusu kullan**: Bir proxy sunucusunun adını veya IP adresini ve TCP bağlantı noktası numarasını el ile girmek için **Izin ver** ' i seçin. **Yapılandırılmadı** (varsayılan) bir proxy sunucusunun ayrıntılarını el ile girmenize izin vermez.
  - **Adres**: Proxy sunucusunun adını veya IP adresini girin.
  - **Bağlantı noktası numarası**: Ara sunucunuzun bağlantı noktası numarasını girin.
  - **Proxy özel durumları**: Proxy sunucusunu kullanmamalıdır gereken URL 'Leri girin. Her birini ayırmak için noktalı virgül kullanın.
  - **Yerel adres için proxy sunucusunu atla**: **Yapılandırılmadı** (varsayılan), intranetinizdeki yerel adresler için bir proxy sunucusunun kullanılmasını önler. **Izin ver** , yerel adresler için bir proxy sunucu kullanır.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="password"></a>istemcisiyle yönetilen bir cihaz için)

Bu ayarlar, desteklenen Windows sürümlerini de listeleyen [DeviceLock ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock)'sini kullanır.

- **Parola**: **Gerekli** ayarı son kullanıcının cihaza erişmek için parola girmesini zorunlu tutar. **Yapılandırılmadı** (varsayılan), bir parola olmadan cihaza erişime izin verir. Yalnızca yerel hesaplar için geçerlidir. Etki alanı hesabı parolaları Active Directory (AD) ve Azure AD tarafından yapılandırılmış olarak kalır.

  - **Gerekli parola türü**: Parola türünü seçin. Seçenekleriniz şunlardır:
    - **Yapılandırılmadı**: Parola rakam ve harf içerebilir.
    - **Sayısal**: Parola yalnızca sayı olmalıdır.
    - **Alfasayısal**: Parola sayıların ve harflerin bir karışımı olmalıdır.
  - **Minimum parola uzunluğu**: 4-16 adresinden gereken minimum sayı veya karakter sayısını girin. Örneğin, parola uzunluğunun `6` en az altı karakter gerektirmek için girin.
  
    > [!IMPORTANT]
    > Parola gereksinimi bir Windows masaüstünde değiştirildiğinde, bu cihaz boşta durumundan etkin 'e geçtiğinde, kullanıcılar bir sonraki oturum açışlarında etkilenir. Gereksinimi karşılayan parolalara sahip olan kullanıcılar parolalarını değiştirmelerini de istenir.
    
  - **Cihaz silinmeden önceki oturum açma hatası sayısı**: Cihaz temizlenmeden önce izin verilen kimlik doğrulama hatalarının sayısını 11 ' e kadar girin. Girdiğiniz geçerli sayı sürüme bağlıdır. [DeviceLock/MaxDevicePasswordFailedAttempts CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-maxdevicepasswordfailedattempts) desteklenen değerleri listeler. `0`(sıfır) cihaz temizleme işlevini devre dışı bırakabilir.

    Bu ayarın Ayrıca sürüme bağlı olarak farklı etkileri vardır. Bu ayar hakkında ayrıntılı bilgi için bkz. [DeviceLock/MaxDevicePasswordFailedAttempts CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-maxdevicepasswordfailedattempts).

  - **Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı**: Ekran kilitlenmeden önce cihazın boşta olması gereken sürenin uzunluğunu girin.
  - **Parola zaman aşımı (gün sayısı)** : Cihaz parolasının değiştirilme tarihi olan 1-365 ' dan gün cinsinden süre uzunluğunu girin. Örneğin, 90 gün `90` sonra parolanın süresini dolacak şekilde girin.
  - **Önceki parolaların yeniden kullanılmasını engelleme**: 1-24 adresinden, daha önce kullanılmış olan parolaların sayısını girin. Örneğin, kullanıcıların geçerli `5` parolasına veya önceki dört parolalarından birine yeni bir parola ayarlayamaması için girin.
  - **Cihaz boşta durumundan çıkarken parola iste** (Mobile ve holographic): **Gerektir** ' i seçin ve boşta kaldıktan sonra kullanıcıların kilidini açmak için bir parola girmesi gerekir. **Yapılandırılmadı** (varsayılan) cihaz boşta durumundan çıktığında PIN veya parola gerektirmez.
  - **Basit parolalar**: Kullanıcıların, `1234` veya`1111`gibi basit parolalar oluşturmaması için engelle olarak ayarlayın. Kullanıcıların veya `1234` gibiparolalaroluşturmalarınaizinvermekiçinyapılandırılmadı(varsayılan)olarak`1111`ayarlayın. Bu ayar, Windows resimli parolalarının kullanımına izin verir veya bunu engeller.
- **Asıfatı sırasında otomatik şifreleme**: **Blok** , CIHAZ Azure AD 'ye katılmış olduğunda otomatik BitLocker cihaz şifrelemesini engeller. **Yapılandırılmadı** (varsayılan), şifrelemeyi etkinleştirebilen işletim sistemi varsayılanını kullanır. [BitLocker cihaz şifrelemesi](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption)hakkında daha fazla bilgi.

  [Güvenlik/koruyucu Tautomaticdeviceencryptionforazureadjoineddevices CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-preventautomaticdeviceencryptionforazureadjoineddevices)

- **Federal bilgi Işleme standardı (FIPS) ilkesi**: **Izin ver** , şifreleme, karma ve imzalama için ABD devlet standardı olan Federal bilgi işleme standardı (FIPS) ilkesini kullanır. **Yapılandırılmadı** (varsayılan), FIPS kullanmayan işletim sistemi varsayılanını kullanır.

  [Şifreleme/AllowFipsAlgorithmPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-cryptography#cryptography-allowfipsalgorithmpolicy)

- **Windows Hello cihaz kimlik doğrulaması**: Kullanıcıların bir Windows 10 bilgisayarında oturum açmak için telefon, uygunluk bandı veya IoT cihazı gibi bir Windows Hello yardımcı cihazı kullanmasına **Izin verin** . **Yapılandırılmadı** (varsayılan) işletim sistemi varsayılanını kullanır, bu da Windows Hello yardımcı cihazlarının Windows ile kimlik doğrulamasını engelleyebilir.

  [Authentication/AllowSecondaryAuthenticationDevice CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowsecondaryauthenticationdevice)

- **Web 'de oturum açma**: Security Assertion Markup Language (SAML) gibi ADFS olmayan (Active Directory Federasyon Hizmetleri (AD FS)) Federasyon sağlayıcıları için Windows oturum açma desteği sunar. SAML, Web tarayıcıları çoklu oturum açma (SSO) deneyimi sağlayan güvenli belirteçler kullanır. Seçenekleriniz şunlardır:

  - **Yapılandırılmadı** (varsayılan): Cihazdaki işletim sistemi varsayılanını kullanır.
  - **Etkin**: Web kimlik bilgisi sağlayıcısı oturum açma için etkinleştirildi.
  - **Devre dışı**: Web kimlik bilgisi sağlayıcısı oturum açma için devre dışı bırakıldı.

  [Kimlik doğrulama/Enablewebsignın CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-enablewebsignin)

- **Tercih edilen Azure AD kiracı etki alanı**: Azure AD kuruluşunuzda mevcut bir etki alanı adı girin. Bu etki alanındaki kullanıcılar oturum açtığında, etki alanı adını yazmak zorunda kalmaz. Örneğin, şunu girin: `contoso.com`. Etki alanındaki kullanıcılar `abby`, yerine `abby@contoso.com`gibi kullanıcı adlarını kullanarak oturum açabilir. `contoso.com`

  [Authentication/PreferredAadTenantDomainName CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-preferredaadtenantdomainname)

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="per-app-privacy-exceptions"></a>Uygulama başına gizlilik özel durumları

"Varsayılan gizlilik" bölümünde tanımladıklarınızdan farklı bir gizlilik davranışına sahip olması gereken uygulamalar ekleyebilirsiniz.

- **Paket adı**: Uygulama paketi aile adı.
- **Uygulama adı**: Uygulamanın adı.

### <a name="exceptions"></a>Özel durumlar

- **Hesap bilgileri**: Bu uygulamanın kullanıcı adına, resmine ve diğer kişi bilgilerine erişip erişemeyeceğini tanımlayın.
- **Arka plan uygulamaları**: Bu uygulamanın arka planda çalıştırılıp çalıştırılamayacağını tanımlayın.
- **Takvim**: Bu uygulamanın takvime erişip erişemeyeceğini tanımlayın.
- **Arama geçmişi**: Bu uygulamanın çağrı geçmişime erişip erişemeyeceğini tanımlayın.
- **Kamera**: Bu uygulamanın kameraya erişip erişemeyeceğini tanımlayın.
- **Kişiler**: Bu uygulamanın kişilere erişip erişemeyeceğini tanımlayın.
- **E-posta**: Bu uygulamanın e-postaya erişip erişemeyeceğini tanımlayın.
- **Konum**: Bu uygulamanın konum bilgilerine erişip erişemeyeceğini tanımlayın.
- **Mesajlaşma**: Bu uygulamanın metin veya MMS iletilerini okuyup okuyamayacağını veya gönderemeyeceğini tanımlayın.
- **Mikrofon**: Bu uygulamanın mikrofonu kullanıp kullanamayacağını tanımlayın.
- **Hareket**: Bu uygulamanın cihaz hareket bilgilerine erişip erişemeyeceğini tanımlayın.
- **Bildirimler**: Bu uygulamanın bildirimlere erişip erişemeyeceğini tanımlayın.
- **Telefon**: Bu uygulamanın telefona erişip erişemeyeceğini tanımlayın.
- **Radyolar**: Bazı uygulamalar, verileri göndermek ve almak ve Bu radyoların açık veya kapalı olması için cihazınızda radyoların (örneğin, Bluetooth) kullanır. Bu uygulamanın bu radyoları denetleyip denetleyemeyeceğini tanımlayın.
- **Görevler**: Bu uygulamanın görevlerinize erişip erişemeyeceğini tanımlayın.
- **Güvenilen cihazlar**: Bu uygulamanın Güvenilen cihazları kullanıp kullanseçemediğini seçin. Güvenilen cihazlar, zaten bağlı olduğunuz donanımdır veya cihazla birlikte gelen donanımlardır. Örneğin, güvenilir cihazlar olarak televizyonlar, projektörler vb. kullanın.
- **Geri bildirim ve tanılama**: Bu uygulamanın tanılama bilgilerine erişip erişemeyeceğini tanımlayın.
- **Cihazlarla Eşitle**: Bu uygulamanın, cihaz ile açık bir şekilde eşleştirmeyen kablosuz cihazlarla otomatik olarak bilgi paylaşıp eşitleyip eşitleyebileceğini seçin.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="personalization"></a>Kişiselleştirme

Bu ayarlar, desteklenen Windows sürümlerini de listeleyen [Kişiselleştirme ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/personalization-csp)'sini kullanır.

- **Masaüstü arka plan resmi URL 'si (yalnızca masaüstü)** : Windows masaüstü duvar kağıdı olarak kullanmak istediğiniz. jpg,. jpeg veya. png biçimindeki bir resmin URL 'sini girin. Kullanıcılar bu resmi değiştiremez. Örneğin, şunu girin: `https://contoso.com/logo.png`.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="printer"></a>Yazıcıda

- **Yazıcılar**: Eklenmiş yerel yazıcıların listesi.
- **Varsayılan yazıcı**: Varsayılan yazıcıyı ayarlayın.
- **Yeni yazıcı eklemek Için Kullanıcı erişimi**: Yerel yazıcıların kullanılmasına izin verin veya bunları engelleyin.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="privacy"></a>Gizlilik

Bu ayarlar, desteklenen Windows sürümlerini de listeleyen [Gizlilik ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy)'sini kullanır.

- **Giriş kişiselleştirme**: **Blok** , dikte için ses kullanımını ve Microsoft bulut tabanlı konuşma tanımayı kullanan Cortana ve diğer uygulamalarla iletişim kurmasını engeller. Devre dışıdır ve kullanıcılar, ayarları kullanarak çevrimiçi konuşma tanımayı etkinleştiremez. **Yapılandırılmadı** (varsayılan) kullanıcıların seçmesini sağlar. Bu hizmetlere izin verirseniz, Microsoft, hizmeti geliştirmek için ses verileri toplayabilir.
- **Eşleştirme ve gizlilik Kullanıcı onay Istemlerinin otomatik kabulü**: Uygulamalar çalıştırılırken Windows 'un eşleştirmeyi ve gizlilik izni iletilerini otomatik olarak kabul edebilmesi için **Izin ver** ' i seçin. **Yapılandırılmadı** (varsayılan), uygulamalar açılırken eşleştirme ve gizlilik Kullanıcı onay penceresinin otomatik kabulüne engel olur.
- **Kullanıcı etkinliklerini yayımla**: **Blok** , Etkinlik akışında paylaşılan deneyimleri ve son kullanılan kaynakların bulunmasını engeller. **Yapılandırılmadı** (varsayılan), uygulamaların son kullanıcı etkinliklerini yayımlayabilmesi için bu özelliği sunar.
- **Yalnızca yerel etkinlikler**: **Blok** , paylaşılan deneyimleri ve yalnızca yerel etkinliğe bağlı olarak görev değiştiricisinde son kullanılan kaynakların bulunmasını engeller. **Yapılandırılmadı** (varsayılan) bu özelliği sunar.

Cihazdaki tüm uygulamaların erişebileceği bilgileri yapılandırabilirsiniz. Ayrıca, **uygulama başına gizlilik özel durumlarını**kullanarak uygulama temelinde özel durumlar tanımlayın.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

### <a name="exceptions"></a>Özel durumlar

- **Hesap bilgileri**: Bu uygulamanın kullanıcı adına, resmine ve diğer kişi bilgilerine erişip erişemeyeceğini tanımlayın.
- **Arka plan uygulamaları**: Bu uygulamanın arka planda çalıştırılıp çalıştırılamayacağını tanımlayın.
- **Takvim**: Bu uygulamanın takvime erişip erişemeyeceğini tanımlayın.
- **Arama geçmişi**: Bu uygulamanın çağrı geçmişime erişip erişemeyeceğini tanımlayın.
- **Kamera**: Bu uygulamanın kameraya erişip erişemeyeceğini tanımlayın.
- **Kişiler**: Bu uygulamanın kişilere erişip erişemeyeceğini tanımlayın.
- **E-posta**: Bu uygulamanın e-postaya erişip erişemeyeceğini tanımlayın.
- **Konum**: Bu uygulamanın konum bilgilerine erişip erişemeyeceğini tanımlayın.
- **Mesajlaşma**: Bu uygulamanın metin veya MMS iletilerini okuyup okuyamayacağını veya gönderemeyeceğini tanımlayın.
- **Mikrofon**: Bu uygulamanın mikrofonu kullanıp kullanamayacağını tanımlayın.
- **Hareket**: Bu uygulamanın cihaz hareket bilgilerine erişip erişemeyeceğini tanımlayın.
- **Bildirimler**: Bu uygulamanın bildirimlere erişip erişemeyeceğini tanımlayın.
- **Telefon**: Bu uygulamanın telefona erişip erişemeyeceğini tanımlayın.
- **Radyolar**: Bazı uygulamalar, verileri göndermek ve almak ve Bu radyoların açık veya kapalı olması için cihazınızda radyoların (örneğin, Bluetooth) kullanır. Bu uygulamanın bu radyoları denetleyip denetleyemeyeceğini tanımlayın.
- **Görevler**: Bu uygulamanın görevlerinize erişip erişemeyeceğini tanımlayın.
- **Güvenilen cihazlar**: Bu uygulamanın Güvenilen cihazları kullanıp kullanseçemediğini seçin. Güvenilen cihazlar, zaten bağlı olduğunuz donanımdır veya cihazla birlikte gelen donanımlardır. Örneğin, güvenilir cihazlar olarak televizyonlar, projektörler vb. kullanın.
- **Geri bildirim ve tanılama**: Bu uygulamanın tanılama bilgilerine erişip erişeseçebilmesine seçin.
- **Cihazlarla eşitle** - Bu uygulamanın bu PC, tablet veya telefonla açıkça eşleştirilmemiş kablosuz cihazlarla otomatik olarak bilgi paylaşma ve eşitleme işlemleri yapıp yapamayacağını tanımlayın.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="projection"></a>Projeksiyon

Bu ayarlar, desteklenen Windows sürümlerini de listeleyen [kablolu Lessdisplay Ilke CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wirelessdisplay)'sini kullanır.

- **Kablosuz Görüntü alıcılarından Kullanıcı girişi**: **Blok** , kablosuz görüntü alıcılarından Kullanıcı girişini engeller. **Yapılandırılmadı** (varsayılan) bir kablosuz görüntülemenin, kaynak cihaza klavye, fare, kalem ve dokunmatik giriş göndermesini sağlar.
- **Bu bilgisayara yansıtma**: **Blok** , diğer cihazların yansıtma için cihazı bulmasını önler. **Yapılandırılmadı** (varsayılan) cihazın bulunabilir olmasını sağlar ve kilit ekranının üzerindeki cihaza proje yapabilir.
- **Eşleştirme IÇIN PIN gerektir**: Projeksiyon cihazına bağlanırken her zaman PIN için istem **iste** ' yi seçin. **Yapılandırılmadı** (varsayılan) cihazı bir projeksiyon cihazına eşleştirmek için PIN gerektirmez.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="reporting-and-telemetry"></a>Raporlama ve telemetri

- **Kullanım verilerini paylaşma**: Gönderilen tanılama verilerinin düzeyini seçin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı**: Hiçbir veri paylaşılmıyor.
  - **Güvenlik**: Bağlı kullanıcı deneyimi ve telemetri bileşen ayarları, kötü amaçlı yazılım kaldırma aracı ve Windows Defender hakkındaki veriler de dahil olmak üzere Windows 'un daha güvenli kalmasına yardımcı olmak için gereken bilgiler.
  - **Temel**: Kalite ile ilgili veriler, uygulama uyumluluğu, uygulama kullanımı verileri ve güvenlik düzeyinden alınan veriler de dahil olmak üzere temel cihaz bilgileri.
  - **Gelişmiş**: Windows, Windows Server, System Center ve uygulamalar nasıl kullanılır, gelişmiş güvenilirlik verileri ve hem temel hem de güvenlik seviyelerine ait veriler de dahil olmak üzere ek Öngörüler.
  - **Tam**: Sorunları belirlemek ve gidermek için gereken tüm veriler, ayrıca güvenlik, temel ve gelişmiş düzeylerdeki veriler.

  [System/Allowtelemetri CSP 'si](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry)

- **Microsoft Edge tarama verilerini Microsoft 365 Analytics 'e gönder**: Bu özelliği kullanmak için, **kullanım verilerini paylaşma** ayarlarını **Gelişmiş** veya **tam**olarak ayarlayın. Bu özellik, Microsoft Edge 'in yapılandırılmış ticari KIMLIĞI olan kurumsal cihazlarda Microsoft 365 Analytics 'e gönderdiği verileri denetler. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı**: , Hiçbir göz atma geçmişi verisi gönderemeyebilir, işletim sistemi varsayılanını kullanır
  - **Yalnızca intranet verilerini Gönder**: Yöneticinin intranet veri geçmişini göndermesini sağlar
  - **Yalnızca internet verilerini Gönder**: Yöneticinin internet veri geçmişini göndermesini sağlar
  - **Intranet ve internet verileri gönderme**: Yöneticinin intranet ve internet veri geçmişini göndermesini sağlar

  [Tarayıcı/ConfigureTelemetryForMicrosoft365Analytics CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-configuretelemetryformicrosoft365analytics)

- **Telemetri proxy sunucusu**: Bağlı kullanıcı deneyimlerini ve telemetri isteklerini iletmek için bir Güvenli Yuva Katmanı (SSL) bağlantısı kullanarak bir proxy sunucusunun tam etki alanı adını (FQDN) veya IP adresini girin. Bu ayarın biçimi *sunucu*:*bağlantı noktası* olur. Adlandırılmış ara sunucu başarısız olursa veya bu ilkeyi etkinleştirirken bir proxy girilmemişse, bağlı kullanıcı deneyimleri ve telemetri verileri gönderilmez ve yerel cihazda kalır.

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

- **Güvenli Arama (yalnızca mobil)** : Cortana 'Nın, arama sonuçlarında yetişkinlere yönelik içeriği nasıl filtreleyeceğini denetleyin. Seçenekleriniz şunlardır:
  - **Kullanıcı tanımlı**: Son kullanıcıların kendi ayarlarını seçmesine izin verin.
  - **Katı**: Yetişkinlere yönelik içeriğe karşı en yüksek filtreleme.
  - **Orta**: Yetişkinlere yönelik içeriğe karşı orta filtreleme. Geçerli arama sonuçları filtrelenmez.
- **Aramada Web sonuçlarını görüntüle**: **Engelleme**olarak ayarlandığında kullanıcılar arama yapamıyor ve web sonuçları aramada gösterilmez. **Yapılandırılmadı** (varsayılan) kullanıcıların Web 'de arama yapmasına izin verir ve sonuçlar cihazda gösterilir.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="start"></a>Start

Bu ayarlar, desteklenen Windows sürümlerini de listeleyen [Başlangıç ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-start)'sini kullanır.  

- **Başlangıç menüsü düzeni**: Varsayılan başlangıç yerleşimini geçersiz kılın ve Masaüstü cihazlarda Başlat menüsünü özelleştirin. Özelleştirmeleri içeren bir XML dosyasını karşıya yükleyin, bu da uygulamaların listelendiği sıralama ve daha fazlasını içerir. Kullanıcılar girdiğiniz başlangıç menüsü yerleşimini değiştiremezler.
- **Web sitelerini Başlat menüsündeki kutucuklara sabitle**: Masaüstü cihazları için Windows Başlat menüsünde bağlantılar olarak gösterilen Microsoft Edge 'deki resimleri içeri aktarın.
- **Uygulamaları görev çubuğundan kaldır**: **Blok** , kullanıcıların görev çubuğundan uygulama bağlantısını kaldırmasını engeller. **Yapılandırılmadı** (varsayılan) kullanıcıların görev çubuğundan uygulamaları serbest bırakmanıza izin verir.
- **Hızlı Kullanıcı geçişi**: **Blok** , oturum açmadan aynı anda oturum açan kullanıcılar arasında geçiş yapılmasını engeller. **Yapılandırılmadı** (varsayılan) Kullanıcı kutucuğunda **Kullanıcı Değiştir** ' i gösterir.
- **En çok kullanılan uygulamalar**: **Blok** , en çok kullanılan uygulamaların başlangıç menüsünde gösterilmesini gizler. Bu ayrıca Ayarlar uygulamasında aynı ada sahip iki durumlu ayarı da devre dışı bırakır. **Yapılandırılmadı** (varsayılan) en sık kullanılan uygulamaları gösterir.
- **Son eklenen uygulamalar**: **Blok** , son eklenen uygulamaların başlangıç menüsünde gösterilmesini gizler. Bu ayrıca Ayarlar uygulamasında aynı ada sahip iki durumlu ayarı da devre dışı bırakır. **Yapılandırılmadı** (varsayılan) başlangıç menüsünde son eklenen uygulamaları gösterir.
- **Başlangıç ekranı modu**: Başlangıç ekranının nasıl gösterileceğini seçin. Seçenekleriniz şunlardır:
  - **Kullanıcı tanımlı**: Başlangıç boyutunu zorlamaz. Kullanıcılar boyutu ayarlayabilir.
  - **Tam ekran**: Başlangıçtan önce tam ekran boyutunu zorlar.
  - **Tam olmayan ekran**: Tam ekran olmayan boyutunu zorla Başlat.
- **Atlama listelerinde son açılan öğeler**: **Blok** , son atlama listelerinin başlangıç menüsünde ve görev çubuğunda gösterilmesinin gizlenmesini engeller. Bu ayrıca Ayarlar uygulamasında aynı ada sahip iki durumlu ayarı da devre dışı bırakır. **Yapılandırılmadı** (varsayılan) atlama listelerinde son açılan öğeleri gösterir.
- **Uygulama listesi**: Tüm uygulamalar listelerinin nasıl gösterileceğini seçin. Seçenekleriniz şunlardır:
  - **Kullanıcı tanımlı**: Hiçbir ayar zorunlu değildir. Kullanıcılar uygulama listesinin cihazda nasıl gösterileceğini seçer.
  - **Daralt**: Tüm uygulamalar listesini gizleyin.
  - **Ayarlar uygulamasını daraltma ve devre dışı bırakma**: Tüm uygulamalar listesini gizleyin ve Ayarlar uygulamasındaki **Başlangıç menüsünde uygulama listesini göster** ' i devre dışı bırakın.
  - **Ayarlar uygulamasını kaldırır ve devre dışı bırakır**: Tüm uygulamalar listesini gizleyin, tüm uygulamalar düğmesini kaldırın ve Ayarlar uygulamasındaki **Başlangıç menüsünde uygulama listesini göster** ' i devre dışı bırakın.
- **Güç düğmesi**: **Blok** , güç düğmesinin başlangıç menüsünde gösterilmesini gizler. **Yapılandırılmadı** (varsayılan) güç düğmesini gösterir.
- **Kullanıcı kutucuğu**: **Blok** , Kullanıcı kutucuğunun başlangıç menüsünde gösterilmesini gizler. **Yapılandırılmadı** (varsayılan) Kullanıcı kutucuğunu gösterir ve aşağıdaki ayarları da ayarlar:
  - **Kilit**: **Blok** , **kilit** seçeneğinin başlangıç menüsündeki Kullanıcı kutucuğunda gösterilmesini gizler. **Yapılandırılmadı** (varsayılan) **Lock** seçeneğini gösterir.
  - **Oturumu Kapat**: **Engelle** , **oturumu** kapat seçeneğinin başlangıç menüsündeki Kullanıcı kutucuğunda gösterilmesini gizler. **Yapılandırılmadı** (varsayılan) **oturumu** Kapat seçeneğini gösterir.
- **Kapat**: **Engelle** , **Güncelleştir ve Kapat** ve **Kapat** seçeneklerinin başlangıç menüsündeki güç düğmesinde gösterilmesini gizler. **Yapılandırılmadı** (varsayılan) bu seçenekleri gösterir.
- **Uyku**: **Blok** , **uyku** seçeneğinin başlangıç menüsündeki güç düğmesinde gösterilmesini gizler. **Yapılandırılmadı** (varsayılan) bu seçeneği gösterir.
- **Hazırda Beklet**: **Blok** , **Hazırda Beklet** seçeneğinin başlangıç menüsündeki güç düğmesinde gösterilmesini gizler. **Yapılandırılmadı** (varsayılan) bu seçeneği gösterir.
- **Değiştirme hesabı**: **Blok** , **Switch hesabının** başlangıç menüsündeki Kullanıcı kutucuğunda gösterilmesini gizler. **Yapılandırılmadı** (varsayılan) bu seçeneği gösterir.
- **Yeniden başlatma seçenekleri**:  **Blok** , **güncelleştirme ve yeniden başlatma** ve **yeniden başlatma** seçeneklerinin başlangıç menüsündeki güç düğmesinde gösterilmesini gizler. **Yapılandırılmadı** (varsayılan) bu seçenekleri gösterir.
- **Başlangıç 'Ta belgeler**: Windows Başlat menüsünde Belgeler klasörünü gizleyin veya gösterin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Hiçbir ayar zorunlu değildir. Kullanıcılar kısayolu göstermeyi veya gizlemeyi seçer.
  - **Gizle**: Kısayol gizlenir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
  - **Göster**: Kısayol gösterilir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
- **Başlangıç 'Ta indirmeler**: Windows Başlat menüsünde Indirmeler klasörünü gizleyin veya gösterin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Hiçbir ayar zorunlu değildir. Kullanıcılar kısayolu göstermeyi veya gizlemeyi seçer.
  - **Gizle**: Kısayol gizlenir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
  - **Göster**: Kısayol gösterilir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
- **Başlangıç 'Ta dosya Gezgini**: Dosya gezginini Windows Başlat menüsünde gizleyin veya gösterin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Hiçbir ayar zorunlu değildir. Kullanıcılar kısayolu göstermeyi veya gizlemeyi seçer.
  - **Gizle**: Kısayol gizlenir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
  - **Göster**: Kısayol gösterilir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
- **Başlangıç 'Ta ev grubu**: Windows Başlat menüsünde ev grubu kısayolunu gizleyin veya gösterin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Hiçbir ayar zorunlu değildir. Kullanıcılar kısayolu göstermeyi veya gizlemeyi seçer.
  - **Gizle**: Kısayol gizlenir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
  - **Göster**: Kısayol gösterilir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
- **Başlangıç 'Ta müzik**: Windows Başlat menüsünde müzik klasörünü gizleyin veya gösterin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Hiçbir ayar zorunlu değildir. Kullanıcılar kısayolu göstermeyi veya gizlemeyi seçer.
  - **Gizle**: Kısayol gizlenir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
  - **Göster**: Kısayol gösterilir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
- **Başlangıç 'Ta ağ**: Windows Başlat menüsünü Ağa gelen gizleyin veya gösterin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Hiçbir ayar zorunlu değildir. Kullanıcılar kısayolu göstermeyi veya gizlemeyi seçer.
  - **Gizle**: Kısayol gizlenir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
  - **Göster**: Kısayol gösterilir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
- **Başlangıç olarak kişisel klasör**: Kişisel klasörü Windows Başlat menüsünde gizleyin veya gösterin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Hiçbir ayar zorunlu değildir. Kullanıcılar kısayolu göstermeyi veya gizlemeyi seçer.
  - **Gizle**: Kısayol gizlenir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
  - **Göster**: Kısayol gösterilir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
- **Başlangıç 'Ta resimler**: Windows Başlat menüsünde resimlerin klasörünü gizleyin veya gösterin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Hiçbir ayar zorunlu değildir. Kullanıcılar kısayolu göstermeyi veya gizlemeyi seçer.
  - **Gizle**: Kısayol gizlenir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
  - **Göster**: Kısayol gösterilir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
- **Başlangıç ayarları**: Windows Başlat menüsünde ayarlar kısayolunu gizleyin veya gösterin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Hiçbir ayar zorunlu değildir. Kullanıcılar kısayolu göstermeyi veya gizlemeyi seçer.
  - **Gizle**: Kısayol gizlenir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
  - **Göster**: Kısayol gösterilir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
- **Başlamadan videolar**: Windows Başlat menüsünde videolar klasörünü gizleyin veya gösterin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Hiçbir ayar zorunlu değildir. Kullanıcılar kısayolu göstermeyi veya gizlemeyi seçer.
  - **Gizle**: Kısayol gizlenir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.
  - **Göster**: Kısayol gösterilir ve Ayarlar uygulamasındaki ayarı devre dışı bırakır.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="windows-defender-smart-screen"></a>Windows Defender Smart Screen

- **Microsoft Edge Için SmartScreen**: **Gerektir** , Windows Defender SmartScreen 'i kapatır ve kullanıcıların bunu açmasını önler. **Yapılandırılmadı** (varsayılan) SmartScreen 'i etkinleştirir. Kullanıcıların olası tehditlere karşı korunmasına yardımcı olur ve kullanıcıların bunu kapatmasını engeller.

  Microsoft Edge, kullanıcıların olası kimlik avı dolandırıcılarından ve kötü amaçlı yazılımlardan korunması için Windows Defender SmartScreen (açık) kullanır.

  [Tarayıcı/AllowSmartScreen CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen)

- **Kötü amaçlı site erişimi**: **Engelle** , kullanıcıların Windows Defender SmartScreen Filtresi uyarılarını yok saymasını ve siteye gitmesini engeller. **Yapılandırılmadı** (varsayılan), kullanıcıların uyarıları yok saymasına ve siteye devam etmesine izin verir.

  [Tarayıcı/PreventSmartScreenPromptOverride CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverride)

- **Doğrulanmamış dosya indirme**: **Blok** , kullanıcıların Windows Defender SmartScreen Filtresi uyarılarını yoksaymasını ve doğrulanmamış dosyaları indirmelerini engeller. **Yapılandırılmadı** (varsayılan), kullanıcıların uyarıları yoksaymasına ve doğrulanmamış dosyaları indirmeye devam etmesine izin verir.

  [Tarayıcı/PreventSmartScreenPromptOverrideForFiles CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverrideforfiles)

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="windows-spotlight"></a>Windows Spot

Bu ayarlar, desteklenen Windows sürümlerini de listeleyen [deneyim ILKESI CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience)'sini kullanır.

- **Windows spot**: Kilit ekranında Windows spot 'u kapatır, Windows Ipuçları, Microsoft tüketici özellikleri ve diğer ilgili özellikler. Amacınız, cihazlardan gelen ağ trafiğini en aza indirmektir, bunu **Engelle**olarak ayarlayın. **Yapılandırılmadı** (varsayılan), Windows spot özelliklerine izin verir ve son kullanıcılar tarafından denetlenebilir. Etkinleştirildiğinde, aşağıdaki ayarları da izin verebilir veya engelleyebilirsiniz:

  - **Kilit ekranında Windows spot**: **Blok** , Windows spot 'un cihaz kilitleme ekranında bilgi göstermesini durduruyor. **Yapılandırılmadı** (varsayılan) bu özelliği sunar.
  - **Windows spot 'Da üçüncü taraf önerileri**: **Blok** , Windows spot 'un Microsoft tarafından yayımlanmamış içerik önermasını engeller. **Yapılandırılmadı** (varsayılan) Windows spot Özellikler 'deki iş ortağı yazılım yayımcılarından uygulama ve içerik önerilerine, kilit ekranı servisleri, başlangıç menüsünde önerilen uygulamalar ve Windows ipuçları gibi izin verir.
  - **Tüketici özellikleri**: **Engelleme** , genellikle yalnızca tüketiciler için, başlangıç önerileri, üyelik bildirimleri, Box dışı deneyim uygulama yüklemesi ve yeniden yönlendirme kutucukları gibi deneyimleri kapatır. **Yapılandırılmadı** (varsayılan) ayarı bu özelliklere izin verir.
  - **Windows ipuçları**: **Engelle** açılır pencere ipuçlarını devre dışı bırakır. **Yapılandırılmadı** (varsayılan), Windows Ipuçlarının gösterilmesini sağlar.
  - **İşlem merkezi 'Nde Windows spot**: **Blok** , Windows spot bildirimlerinin işlem merkezinde gösterilmesini engeller. **Yapılandırılmadı** (varsayılan), kullanıcıların Windows 'da daha üretken olmalarını sağlamak için uygulama veya özellik öneren Işlem merkezinde bildirimleri gösterebilir.
  - **Windows spot kişiselleştirme**: **Blok** , Windows 'un kullanıcıya özelleştirilmiş deneyimler sağlaması için tanılama verilerini kullanmasını engeller. **Yapılandırılmadı** (varsayılan), Microsoft 'un kullanıcının ihtiyaçlarını karşılamak üzere özelleştirilmiş öneriler, ipuçları ve teklifler sunmak için tanılama verilerini kullanmasına izin verir.
  - **Windows Karşılama deneyimi**: **Engelle** , Windows spot Windows hoş geldiniz deneyimi özelliğini kapatır. Windows Karşılama deneyimi, Windows 'da ve uygulamalarında güncelleştirmeler ve değişiklikler olduğunda gösterilmez. **Yapılandırılmadı** (varsayılan) yeni veya güncelleştirilmiş özelliklerle ilgili Kullanıcı bilgilerini gösteren Windows Karşılama deneyimine izin verir.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="windows-defender-antivirus"></a>Windows Defender Virüsten Koruma

Bu ayarlar, desteklenen Windows sürümlerini de listeleyen [Defender Ilke CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender)'sini kullanır.

- **Gerçek zamanlı izleme**: **Etkinleştirme** , kötü amaçlı yazılım, casus yazılım ve diğer istenmeyen yazılımlar için gerçek zamanlı taramayı önler. **Yapılandırılmadı** (varsayılan) bu özelliğe izin verir.
- **Davranış izleme**: **Etkinleştir** ayarı, Defender 'ın cihazlarda bilinen şüpheli etkinlik düzenlerini denetlemesini önler. **Yapılandırılmadı** (varsayılan) Windows Defender davranışı Izlemeye izin verir.
- **Ağ İnceleme sistemi (NIS)** : NIS, cihazları ağ tabanlı saldırılara karşı korumaya yardımcı olur. Kötü amaçlı trafiği algılamaya ve engellemeye yardımcı olmak için Microsoft Endpoint Protection Center’dan bilinen açıkların imzalarını kullanır.
- **Tüm Indirmeleri Tara**: Defender’ın İnternet’ten indirilen tüm dosyaları tarayıp taramayacağını denetler.
- **Microsoft Web tarayıcılarında yüklenen betikleri tarayın**: **Yapılandırılmadı** (varsayılan), Defender 'ın Internet Explorer 'da kullanılan betikleri taramasını sağlar. **Etkinleştir** ayarı, bu taramayı önler.
- **Defender 'A Son Kullanıcı erişimi**: **Blok** , Windows Defender Kullanıcı arabirimini son kullanıcılardan gizler. Tüm Windows Defender bildirimleri de bastırılır. **Yapılandırılmadı** (varsayılan), Windows Defender Kullanıcı arabirimine Kullanıcı erişimine izin verir. Bu ayar değiştirildiğinde, kullanıcının bilgisayarının bir sonraki yeniden başlatılmasında devreye girer.
- **İmza güncelleştirme aralığı (saat)** : Defender 'ın yeni imza dosyalarını denetleme aralığını 0-24 adresinden girin. Seçenekleriniz şunlardır:

  - **Yapılandırılmadı** varsayılanını
  - **Denetleme**: Defender yeni imza dosyalarını denetetmez.
  - **1-24**: `1` saatte bir denetim yapın `2` , her iki saatte `24` bir denetim yapın, her gün kontrol eder.
- **Dosya ve program etkinliğini izle**: Defender’ın cihazlarda dosya ve program etkinliğini izlemesine izin verir.
- **Karantinaya alınan kötü amaçlı yazılımı silmeden önce geçen gün**: Daha önce etkilenen cihazları el ile kontrol edebilmeniz için, girdiğiniz gün sayısı için çözümlenmiş kötü amaçlı yazılımı izlemeye devam edin. Gün sayısını **0**olarak ayarlarsanız, kötü amaçlı yazılım Karantina klasöründe kalır ve otomatik olarak kaldırılmaz. Olarak `90`ayarlandığında, karantina öğeleri sistemde 90 gün süreyle depolanır ve sonra kaldırılır.
- **Tarama sırasında CPU kullanım sınırı**: Taramaların kullanmasına izin verilen CPU miktarını, **1** ile **100**arasında sınırlayın.
- **Arşiv dosyalarını Tara**: **Etkinleştir** , Defender 'ın zip veya CAB dosyaları gibi arşivlenmiş dosyaları taramasını önler. **Yapılandırılmadı** (varsayılan) Bu taramaya izin verir.
- **Gelen posta Iletilerini Tara**: **Enable** , Defender 'ın cihaza gelen e-posta iletilerini taramasına izin verir. **Yapılandırılmadı** (varsayılan) e-posta taramasını engeller.
- **Tam tarama sırasında çıkarılabilir sürücüleri Tara**: **Etkinleştir** ayarı, çıkarılabilir sürücülerin tam taranmasını önler. **Yapılandırılmadı** (varsayılan), Defender 'ın USB sürücüleri gibi çıkarılabilir sürücüleri taramasına olanak sağlar.
- **Tam tarama sırasında eşlenmiş ağ sürücülerine Tara**: **Etkinleştir** , Defender 'ın eşlenen ağ sürücülerindeki dosyaları taramasına olanak sağlar. **Yapılandırılmadı** (varsayılan) tam taramayı önler. Sürücüdeki dosyalar salt okunurdur, Defender bu bilgisayarlarda bulunan herhangi bir kötü amaçlı yazılımı kaldıramıyor.
- **Ağ klasörlerinden açılan dosyaları tara**: **Yapılandırılmadı** (varsayılan) Defender, bir UNC yolundan erişilen dosyalar gibi paylaşılan ağ sürücülerindeki dosyaları taramasına olanak tanır. **Etkinleştir** ayarı, bu taramayı önler. Sürücüdeki dosyalar salt okunurdur, Defender bu bilgisayarlarda bulunan herhangi bir kötü amaçlı yazılımı kaldıramıyor.
- **Bulut koruması**: **Yapılandırılmadı** (varsayılan) Microsoft Etkin Koruma Hizmeti yönettiğiniz cihazlardan kötü amaçlı yazılım etkinliğiyle ilgili bilgi almasına izin verir. **Enable** , bu özelliği engeller.
- **Örnek göndermeden önce kullanıcılara sor**: Daha fazla analiz gerektirebilecek kötü amaçlı olabilecek dosyaların otomatik olarak Microsoft 'a gönderilip gönderilmeyeceğini denetler. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı**
  - **Her zaman sor**
  - **Kişisel verileri göndermeden önce sor**
  - **Hiçbir şekilde veri gönderme**
  - **Tüm verileri sorulmadan gönder**: Veriler otomatik olarak gönderilir

- **Günlük hızlı tarama gerçekleştirme zamanı**: Günlük hızlı tarama çalıştırmak için saati seçin. **Yapılandırılmadı** , günlük tarama çalıştırmaz. Daha fazla özelleştirme istiyorsanız, ayar **yapmak için sistem taraması türünü** yapılandırın.

  [Defender/ScheduleQuickScanTime CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime)

- **Gerçekleştirilecek sistem taraması türü**: Tarama düzeyini ve taramanın çalıştırılacağı gün ve saati içeren bir sistem taraması zamanlayın. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı**: Cihazda bir sistem taraması zamanlayamıyor. Son kullanıcılar, gerektiğinde taramaları el ile çalıştırabilir veya cihazlarında ister.
  - **Devre dışı bırak**: Cihazdaki tüm sistem taramasını devre dışı bırakır. Cihazları tarayan bir iş ortağı virüsten koruma çözümü kullanıyorsanız bu seçeneği belirleyin.
  - **Hızlı tarama**: Kayıt defteri anahtarları ve bilinen Windows başlangıç klasörleri gibi kötü amaçlı yazılımın kaydedildiği yaygın konumlara bakar.
    - **Zamanlanan gün**: Taramanın çalıştırılacağı günü seçin.
    - **Zamanlanan saat**: Taramanın çalıştırılacağı saati seçin.
  - **Tam tarama**: , Kötü amaçlı yazılımın kaydedildiği yaygın konumlara bakar ve cihazdaki her dosyayı ve klasörü tarar.
    - **Zamanlanan gün**: Taramanın çalıştırılacağı günü seçin.
    - **Zamanlanan saat**: Taramanın çalıştırılacağı saati seçin.

  Bu ayar **günlük hızlı tarama ayarı gerçekleştirme zamanına** göre çakışabilir. Bazı öneriler:

  - Günlük hızlı tarama çalıştırmak için **günlük hızlı tarama ayarı gerçekleştirme saatini** yapılandırın.
  - Günlük hızlı taramayı ve her hafta tam taramayı çalıştırmak için, **günlük hızlı tarama gerçekleştirme saatini**yapılandırın. Gün ve saat ile tam tarama yapmak **için sistem taraması türünü** ayarlayın.
  - **Hızlı tarama**olarak ayarlanacak **sistem taraması türü** ile **günlük hızlı tarama ayarı gerçekleştirmek için geçen süreyi** yapılandırmayın. Bu ayarlar çakışabilir ve bir tarama çalışmayabilir.
  - Her Salı, 6: dakikada bir hızlı tarama çalıştırmak için **sistem taraması türünü ayarı gerçekleştirecek şekilde** yapılandırın.

  [Defender/ScanParameter CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-scanparameter)  
  [Defender/ScheduleScanDay CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescanday)  
  [Defender/ScheduleScanTime CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescantime)

- İstenmeyebilecek **uygulamaları Algıla**: Windows istenmeyebilecek uygulamalar algıladığında koruma düzeyini seçin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Windows Defender istenmeyebilecek uygulamaların korunması devre dışı bırakıldı.
  - **Engelle**: Windows Defender istenmeyebilecek uygulamaları algılar ve algılanan öğeler engellenir. Bu öğeler, diğer tehditlerle birlikte geçmiş olarak gösterilir.
  - **Denetim**: Windows Defender istenmeyebilecek uygulamalar algılar, ancak hiçbir işlem gerçekleşmez. Windows Defender 'ın işlem yapması için gereken uygulamalar hakkındaki bilgileri gözden geçirebilirsiniz. Örneğin, Olay Görüntüleyicisi Windows Defender tarafından oluşturulan olayları arayın.

  İstenmeyebilecek uygulamalar hakkında daha fazla bilgi için bkz. istenmeyebilecek [uygulamaları algılama ve engelleme](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus).

- **Algılanan kötü amaçlı yazılım tehditleri eylemleri**: Defender 'ın algıladığı her tehdit düzeyi için hangi eylemleri ele geçirmesine istediğinizi seçin: düşük, orta, yüksek ve önemli. Mümkün değilse, Windows Defender tehdit 'nin düzeltildiğinden emin olmak için en iyi seçeneği seçer. Seçenekleriniz şunlardır:
  - **Temizle**
  - **Karantina**
  - **Kaldır**
  - **İzin ver**
  - **Kullanıcı tanımlı**
  - **Engelle**

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

### <a name="windows-defender-antivirus-exclusions"></a>Windows Defender Virüsten Koruma Dışlamaları

- **Taramaların ve gerçek zamanlı korumanın dışında tutulacak dosyalar ve klasörler**: Dışlama listesinde **C:\Yol** veya **%ProgramFiles%\Yol\dosyaadı.exe** gibi bir veya birden çok dosya ve klasör ekler. Bu dosya ve klasörler gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.
- **Taramalardan ve gerçek zamanlı korumanın dışında tutulacak dosya uzantıları**: Dışlama listesine **jpg** veya **txt** gibi bir veya birden çok dosya uzantısı ekleyin. Bu uzantılara sahip tüm dosyalar gerçek zamanlı veya zamanlanmış taramalara dahil değildir.
- **Taramaların ve gerçek zamanlı korumanın dışında tutulacak süreçler**: Dışlama listesine **.exe**, **.com** veya **.scr** türünde bir veya birden çok işlem ekleyin. Bu süreçler gerçek zamanlı veya zamanlanmış taramalara dahil değildir.

Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="next-steps"></a>Sonraki adımlar

Her bir ayara dair ek teknik ayrıntılar ve hangi Windows sürümlerinin desteklendiği hakkında bilgi için bkz. [Windows 10 İlke CSP Başvurusu](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)
