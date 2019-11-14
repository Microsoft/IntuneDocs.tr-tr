---
title: Windows holographic Business cihaz ayarları-Microsoft Intune-Azure | Microsoft Docs
description: Windows holographic for Business için Microsoft Intune, kayıt, coğrafi konum, parolalar, App Store 'dan uygulama yüklemesi, Microsoft Edge, Microsoft Defender, ara, tanımlama bilgileri ve açılır pencereler dahil cihaz kısıtlama ayarlarını okuyun ve yapılandırın. Azure 'daki bulut ve depolama, Bluetooth bağlantısı, sistem saati ve kullanım verileri.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/13/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1f90a5a13859ff19765e22444a84b9c11405af73
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74059500"
---
# <a name="windows-holographic-for-business-device-settings-to-allow-or-restrict-features-using-intune"></a>Intune kullanarak özelliklere izin vermek veya erişimi kısıtlamak için Windows holographic for Business cihaz ayarları

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bu makalede, Microsoft HoloLens gibi Windows holographic for Business cihazlarında denetleyebilmeniz için farklı ayarlar listelenmektedir ve açıklanmaktadır. Mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak bu ayarları, özelliklere izin vermek veya devre dışı bırakmak, güvenliği denetlemek ve daha fazlasını yapmak için kullanın.

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz yapılandırma profili oluşturun](device-restrictions-configure.md#create-the-profile).

## <a name="general"></a>Genel

- **El ile kayıt kaldırma**: kullanıcının çalışma alanı hesabını cihazdan el ile silmesine olanak sağlar.
- **Cortana**: Cortana sesli yardımcısını etkinleştirin veya devre dışı bırakın.
- **Coğrafi konum**: Cihazın konum hizmetleri bilgilerini kullanıp kullanamayacağını belirtir.

## <a name="password"></a>Parola

- **Parola**: son kullanıcının cihaza erişmek için bir parola girmesini gerektir.
- **Cihaz boşta durumundan çıkarken parola iste**: kullanıcının cihazın kilidini açmak için bir parola girmesi gerektiğini belirtir.

## <a name="app-store"></a>Uygulama Mağazası

- **Mağaza 'dan uygulamaları otomatik güncelleştir**: Microsoft Store yüklenen uygulamaların otomatik olarak güncelleştirilmesini sağlar.
- **Güvenilen uygulama yüklemesi**: güvenilen bir sertifikayla imzalanan uygulamaların dışarıdan yüklenmesine izin verir.
- **Geliştirici kilidi açma**: dışarıdan yüklenen uygulamaların Son Kullanıcı tarafından değiştirilmesine izin verme gibi Windows Geliştirici ayarlarına izin verin.

## <a name="microsoft-edge-browser"></a>Microsoft Edge Tarayıcısı

- **Tanımlama bilgileri**: tarayıcının internet tanımlama bilgilerini cihaza kaydetmesine izin verir.
- **Açılır**pencereler: tarayıcıda açılır pencereleri engeller (yalnızca Windows 10 Masaüstü için geçerlidir).
- **Arama önerileri**: arama cümlelerinizi yazarken arama motorunuzun siteler önermesini sağlar.
- **Parola Yöneticisi**: Microsoft Edge parola Yöneticisi özelliğini etkinleştirin veya devre dışı bırakın.
- **Do-Not-Track üst bilgileri gönder**: Microsoft Edge tarayıcısını, kullanıcıların ziyaret ettiği Web sitelerini izleme üst bilgilerini gönderecek şekilde yapılandırır.

## <a name="microsoft-defender-smart-screen"></a>Microsoft Defender akıllı ekranı

- **Microsoft Edge Için SmartScreen**: site ve dosya indirmelerine erişmek Için Microsoft Edge SmartScreen 'i etkinleştirin.

## <a name="search"></a>Ara

- **Arama konumu** - Aramanın konumu kullanıp kullanamayacağını belirtin. bilgiler

## <a name="cloud-and-storage"></a>Bulut ve Depolama

- **Microsoft hesabı**: kullanıcının cihazla bir Microsoft hesabı ilişkilendirilmesine izin verir.

## <a name="cellular-and-connectivity"></a>Hücresel ve Bağlantı

- **Bluetooth**: kullanıcının cihazda Bluetooth 'u etkinleştirip yapılandırıp yapılandıramayacağını denetler.
- **Bluetooth bulunabilirliği**: cihazın diğer Bluetooth özellikli cihazlar tarafından keşfedilmesini sağlar.
- **Bluetooth tanıtımı**: cihazın Bluetooth üzerinden reklam almasına izin verir.

## <a name="control-panel-and-settings"></a>Denetim Masası ve Ayarlar

- **Sistem saati değişikliği**: son kullanıcının cihaz tarih ve saatini değiştirmesini önler.

## <a name="kiosk---obsolete"></a>Bilgi noktası - Eski

Bu ayarlar salt okunurdur ve değiştirilemez. Bilgi noktası modunu yapılandırmak için bkz. [Bilgi noktası ayarları](kiosk-settings-holographic.md).

Bir bilgi noktası cihazı genellikle belirli bir uygulama çalıştırır. Kullanıcıların cihazda bilgi noktası uygulaması dışında başka özellik veya işlevlere erişimi engellenmiştir.

- **Bilgi noktası modu**: ilke tarafından desteklenen bilgi noktası modunun türünü tanımlar. Şu seçenekler mevcuttur:

  - **Yapılandırılmamış** (varsayılan): İlke, bilgi noktası modunu etkinleştirmez. 
  - **Tek uygulama bilgi noktası**: profil, cihazın yalnızca bir uygulama çalıştırmasına olanak sağlar. Kullanıcı oturum açtığında belirli bir uygulama başlar. Bu mod ayrıca kullanıcının yeni uygulamalar açmasını veya çalışan uygulamayı değiştirmesini önler.
  - **Birden çok uygulama bilgi noktası**: profil, cihazın birden çok uygulama çalıştırmasına olanak sağlar. Yalnızca eklediğiniz uygulamalar kullanıcı tarafından kullanılabilir. Bir çoklu uygulama bilgi noktasının veya sabit amaçlı cihazın yararı, yalnızca ihtiyaç duyulan uygulamalara erişim sağlayarak bireylere anlaşılması kolay bir deneyim sunmasıdır. İhtiyaç duymadıkları uygulamaları ise gözlerinin önünden kaldırır. 
  
    Çoklu uygulama bilgi noktası deneyimi için uygulama eklediğinizde, başlat menüsü düzen dosyası da eklersiniz. [Başlat menüsü düzeni dosyası](/hololens/hololens-kiosk#start-layout-file-for-mdm-intune-and-others), Intune’da kullanılabilecek örnek bir XML içerir. 

### <a name="single-app-kiosks"></a>Tek uygulama bilgi noktaları

Aşağıdaki ayarları girin:

- **Kullanıcı hesabı**: yerel (cihaz) Kullanıcı hesabını veya bilgi noktası uygulamasıyla ILIŞKILI Azure AD hesabı oturum açma bilgilerini girin. Azure AD etki alanlarına katılmış hesapları `domain\username@tenant.org` biçiminde girin. 

    Herkese açık ortamlarda bulunan ve otomatik oturum açma etkin bilgi noktaları için olabildiğince az ayrıcalığa sahip bir kullanıcı türü (yerel standart kullanıcı hesabı gibi) kullanılmalıdır. Bir Azure Active Directory (AD) hesabını bilgi noktası moduna yapılandırmak için `AzureAD\user@contoso.com` biçimini kullanın.

- **Uygulamanın uygulama Kullanıcı MODELI kimliği (aumıd)** : bilgi noktası uygulamasının aumıd 'sini girin. Daha fazla bilgi için bkz. [Yüklü bir uygulamanın Uygulama Kullanıcı Model Kimliğini bulma](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

## <a name="reporting-and-telemetry"></a>Raporlama ve Telemetri

- **Kullanım verilerini paylaşma**: tanılama veri gönderimi düzeyini seçin.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).
