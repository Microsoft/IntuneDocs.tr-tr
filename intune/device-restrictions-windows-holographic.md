---
title: Windows Holographic iş cihaz ayarları - Microsoft Intune - Azure | Microsoft Docs
description: Windows Holographic for Business için Microsoft Intune’da kaydı kaldırma, coğrafi konum, parolalar, uygulama mağazasından uygulama yükleme, Microsoft Edge’de çerezler ve açılır pencereler, Windows Defender, arama, bulut ve depolama, bluetooth bağlantısı, sistem saati ve Azure’da kullanım verileri gibi cihaz kısıtlama ayarları hakkında bilgi edinin ve bu ayarları yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: bea8d6d8e3503b9ec6fba7b2eda4842b68786e54
ms.sourcegitcommit: bd09decb754a832574d7f7375bad0186a22a15ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/19/2019
ms.locfileid: "71302316"
---
# <a name="windows-holographic-for-business-device-settings-to-allow-or-restrict-features-using-intune"></a>Windows Holographic for Business izin vermek veya Intune kullanarak özellikleri kısıtlamak için cihaz ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makale, listeler ve farklı ayarları denetleyebilirsiniz gibi Microsoft Hololens cihazları Windows Holographic for Business açıklar. Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, izin veya özellikler, güvenlik denetimi ve daha fazla devre dışı için bu ayarları kullanın.

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz yapılandırma profili oluşturma](device-restrictions-configure.md#create-the-profile).

## <a name="general"></a>Genel

- **El ile kayıt kaldırma**: Kullanıcının iş yeri hesabını cihazdan el ile silmesine olanak sağlar.
- **Cortana**: Cortana sesli yardımcısını etkinleştirin veya devre dışı bırakın.
- **Coğrafi konum**: Cihazın konum hizmetleri bilgilerini kullanıp kullanamayacağını belirtir.

## <a name="password"></a>istemcisiyle yönetilen bir cihaz için)

- **Parola**: Son kullanıcının cihaza erişmek için parola girmesini zorunlu tutun.
- **Cihaz boşta durumundan çıkarken parola iste**: Kullanıcının cihazın kilidini açmak için bir parola girmesi gerektiğini belirtir.

## <a name="app-store"></a>Uygulama Mağazası

- **Mağazadan uygulamaları otomatik güncelleştir**: Microsoft Store yüklenen uygulamaların otomatik olarak güncelleştirilmesini sağlar.
- **Güvenilen uygulama yüklemesi**: Güvenilen bir sertifikayla imzalanan uygulamaların dışarıdan yüklenmesine izin verir.
- **Geliştirici kilidi açma**: Dışarıdan yüklenen uygulamaların Son Kullanıcı tarafından değiştirilmesine izin verme gibi Windows Geliştirici ayarlarına izin verin.

## <a name="microsoft-edge-browser"></a>Microsoft Edge Tarayıcısı

- **Tanımlama bilgileri**: Tarayıcının internet tanımlama bilgilerini cihaza kaydetmesine izin verir.
- **Açılır pencereler**: Tarayıcıda açılır pencereleri engeller (yalnızca Windows 10 Masaüstü için geçerlidir).
- **Arama önerileri**: Siz arama tümcecikleri yazarken arama motorunuzun site önerilerinde bulunmasına olanak sağlar.
- **Parola Yöneticisi**: Microsoft Edge parola Yöneticisi özelliğini etkinleştirin veya devre dışı bırakın.
- **Do-Track üstbilgileri gönder**: Microsoft Edge tarayıcısını, kullanıcıların ziyaret ettiği Web sitelerine üst bilgileri izlememek üzere yapılandırır.

## <a name="windows-defender-smart-screen"></a>Windows Defender Smart Screen

- **Microsoft Edge Için SmartScreen**: Site ve dosya indirmelerine erişmek için Microsoft Edge SmartScreen 'i etkinleştirin.

## <a name="search"></a>Ara

- **Arama konumu** - Aramanın konumu kullanıp kullanamayacağını belirtin. bilgiler

## <a name="cloud-and-storage"></a>Bulut ve Depolama

- **Microsoft hesabı**: Kullanıcının bir Microsoft hesabını cihazla ilişkilendirmesine olanak sağlar.

## <a name="cellular-and-connectivity"></a>Hücresel ve Bağlantı

- **Bluetooth**: Kullanıcının cihazda Bluetooth 'U etkinleştirip yapılandırıp yapılandıramayacağını denetler.
- **Bluetooth bulunabilirliği**: Cihazın diğer Bluetooth özellikli cihazlar tarafından keşfedilmesini sağlar.
- **Bluetooth tanıtımı**: Cihazın Bluetooth üzerinden reklam almasına izin verir.

## <a name="control-panel-and-settings"></a>Denetim Masası ve Ayarlar

- **Sistem saati değişikliği**: Son kullanıcının cihaz tarih ve saatini değiştirmesini engeller.

## <a name="kiosk---obsolete"></a>Bilgi noktası - Eski

Bu ayarlar salt okunurdur ve değiştirilemez. Bilgi noktası modunu yapılandırmak için bkz. [Bilgi noktası ayarları](kiosk-settings-holographic.md).

Bir bilgi noktası cihazı genellikle belirli bir uygulama çalıştırır. Kullanıcıların cihazda bilgi noktası uygulaması dışında başka özellik veya işlevlere erişimi engellenmiştir.

- **Bilgi noktası modu**: İlke tarafından desteklenen bilgi noktası modu türünü tanımlar. Şu seçenekler mevcuttur:

  - **Yapılandırılmadı** (varsayılan): İlke bilgi noktası modunu etkinleştirmez. 
  - **Tek uygulama bilgi noktası**: Profil, cihazın yalnızca bir uygulama çalıştırmasına olanak sağlar. Kullanıcı oturum açtığında belirli bir uygulama başlar. Bu mod ayrıca kullanıcının yeni uygulamalar açmasını veya çalışan uygulamayı değiştirmesini önler.
  - **Birden çok uygulama bilgi noktası**: Profil, cihazın birden çok uygulama çalıştırmasına olanak sağlar. Yalnızca eklediğiniz uygulamalar kullanıcı tarafından kullanılabilir. Bir çoklu uygulama bilgi noktasının veya sabit amaçlı cihazın yararı, yalnızca ihtiyaç duyulan uygulamalara erişim sağlayarak bireylere anlaşılması kolay bir deneyim sunmasıdır. İhtiyaç duymadıkları uygulamaları ise gözlerinin önünden kaldırır. 
  
    Çoklu uygulama bilgi noktası deneyimi için uygulama eklediğinizde, başlat menüsü düzen dosyası da eklersiniz. [Başlat menüsü düzeni dosyası](/hololens/hololens-kiosk#start-layout-file-for-mdm-intune-and-others), Intune’da kullanılabilecek örnek bir XML içerir. 

### <a name="single-app-kiosks"></a>Tek uygulama bilgi noktaları

Aşağıdaki ayarları girin:

- **Kullanıcı hesabı**: Yerel (cihaza) Kullanıcı hesabını veya bilgi noktası uygulamasıyla ilişkili Azure AD hesabı oturum açma bilgilerini girin. Azure AD etki alanlarına katılmış hesapları `domain\username@tenant.org` biçiminde girin. 

    Herkese açık ortamlarda bulunan ve otomatik oturum açma etkin bilgi noktaları için olabildiğince az ayrıcalığa sahip bir kullanıcı türü (yerel standart kullanıcı hesabı gibi) kullanılmalıdır. Bir Azure Active Directory (AD) hesabını bilgi noktası moduna yapılandırmak için `AzureAD\user@contoso.com` biçimini kullanın.

- Uygulamanın **uygulama Kullanıcı MODELI kimliği (AUMıD)** : Bilgi noktası uygulamasının AUMıD 'sini girin. Daha fazla bilgi için bkz. [Yüklü bir uygulamanın Uygulama Kullanıcı Model Kimliğini bulma](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

## <a name="reporting-and-telemetry"></a>Raporlama ve Telemetri

- **Kullanım verilerini paylaşma**: Tanılama veri gönderimi düzeyini seçin.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).
