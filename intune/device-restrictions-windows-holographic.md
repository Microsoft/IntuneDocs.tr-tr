---
title: Microsoft Intune - Azure’da Windows Holographic for Business için cihaz kısıtlamaları | Microsoft Docs
description: Windows Holographic for Business için Microsoft Intune’da kaydı kaldırma, coğrafi konum, parolalar, uygulama mağazasından uygulama yükleme, Microsoft Edge’de çerezler ve açılır pencereler, Windows Defender, arama, bulut ve depolama, bluetooth bağlantısı, sistem saati ve Azure’da kullanım verileri gibi cihaz kısıtlama ayarları hakkında bilgi edinin ve bu ayarları yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f79985c9854af462fa9a456304a3184128283b9c
ms.sourcegitcommit: d8edd1c3d24123762dd6d14776836df4ff2a31dd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2018
ms.locfileid: "51576809"
---
# <a name="device-restriction-settings-for-windows-holographic-for-business-in-intune"></a>Intune’da Windows Holographic for Business için cihaz kısıtlama ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft HoloLens gibi Windows Holographic for Business çalıştıran cihazlarda aşağıdaki cihaz kısıtlama ayarları desteklenir.

## <a name="general"></a>Genel

- **El ile kayıt kaldırma** - Kullanıcının iş yeri hesabını cihazdan el ile silmesine olanak sağlar.
- **Cortana** - Cortana sesli yardımcısını etkinleştirin veya devre dışı bırakın.
- **Coğrafi konum** - Cihazın konum hizmetleri bilgilerini kullanıp kullanamayacağını belirtir.

## <a name="password"></a>Parola
-   **Parola** - Son kullanıcının cihaza erişmek için parola girmesini zorunlu tutun.
    -   **Cihaz boşta kalma durumundan çıktığında parola isteme** - Boşta durumundaki bir cihazın kilidini açmak için kullanıcının parola girmesi gerektiğini belirtir.

## <a name="app-store"></a>Uygulama Mağazası

-   **Mağaza uygulamalarını otomatik güncelleştir** - Microsoft Mağazası'ndan yüklenen uygulamaların otomatik olarak güncelleştirilmesine izin verir.
-   **Güvenilir uygulama yüklemesi** - Güvenilir bir sertifikayla imzalanan uygulamaların dışarıdan yüklenmesine izin verir.
-   **Geliştirici kilidini açma** - Dışarıdan yüklenen uygulamaların son kullanıcı tarafından değiştirilmesine izin verme gibi Windows geliştirici ayarlarına izin verir.

## <a name="microsoft-edge-browser"></a>Microsoft Edge Tarayıcısı

-   **Tanılama bilgileri** - Tarayıcının İnternet tanımlama bilgilerini cihaza kaydetmesine olanak tanır.
-   **Açılır pencereler** - Tarayıcıdaki açılır pencereleri engeller (yalnızca Windows 10 masaüstü için geçerlidir).
-   **Arama önerileri** - Siz arama sözcükleri yazarken arama motorunuzun site önerilerinde bulunmasına olanak sağlar.
-   **Parola Yöneticisi** - Microsoft Edge Parola Yöneticisi özelliğini etkinleştirin veya devre dışı bırakın.
- **Do-not-track (izleme) üst bilgileri gönderme** - Microsoft Edge tarayıcısını, kullanıcıların ziyaret ettiği web sitelerine do-not-track (izleme) üst bilgileri gönderecek şekilde yapılandırır.

## <a name="windows-defender-smart-screen"></a>Windows Defender Smart Screen

- **Microsoft Edge için SmartScreen** - Site ve dosya indirmelerine erişmek için Microsoft Edge SmartScreen’i etkinleştirin.

## <a name="search"></a>Ara
- **Arama konumu** - Aramanın konumu kullanıp kullanamayacağını belirtin. bilgiler

## <a name="cloud-and-storage"></a>Bulut ve Depolama
-   **Microsoft hesabı** - Kullanıcının bir Microsoft hesabını cihazla ilişkilendirmesine olanak sağlar.

## <a name="cellular-and-connectivity"></a>Hücresel ve Bağlantı

-   **Bluetooth** - Kullanıcının cihazda Bluetooth’u etkinleştirmesine ve yapılandırmasına izin verilip verilmeyeceğini denetler.
-   **Bluetooth bulunabilirliği** - Cihazın diğer Bluetooth özellikli cihazlar tarafından bulunabilmesine olanak sağlar.
-   **Bluetooth reklamları** - Cihazın Bluetooth üzerinden reklamlar almasına olanak tanır.

## <a name="control-panel-and-settings"></a>Denetim Masası ve Ayarlar

- **Sistem Saatindeki değişiklikler** - Son kullanıcının cihazın tarih ve saatini değiştirmesini engeller.

## <a name="kiosk---obsolete"></a>Bilgi noktası - Eski

Bu ayarlar salt okunurdur ve değiştirilemez. Bilgi noktası modunu yapılandırmak için bkz. [Bilgi noktası ayarları](kiosk-settings.md#windows-holographic-for-business).

Bir bilgi noktası cihazı genellikle belirli bir uygulama çalıştırır. Kullanıcıların cihazda bilgi noktası uygulaması dışında başka özellik veya işlevlere erişimi engellenmiştir.

- **Bilgi noktası modu**: İlke tarafından desteklenen bilgi noktası modu türünü belirler. Şu seçenekler mevcuttur:

  - **Yapılandırılmamış** (varsayılan) - İlke, bilgi noktası modunu etkinleştirmez. 
  - **Tek uygulama bilgi noktası**: Profil, cihazı yalnızca bir uygulama çalıştıracak şekilde etkinleştirir. Kullanıcı oturum açtığında belirli bir uygulama başlar. Bu mod ayrıca kullanıcının yeni uygulamalar açmasını veya çalışan uygulamayı değiştirmesini önler.
  - **Çoklu uygulama bilgi noktası**: Profil, cihazın birden fazla uygulama çalıştırmasına izin verir. Yalnızca eklediğiniz uygulamalar kullanıcı tarafından kullanılabilir. Bir çoklu uygulama bilgi noktasının veya sabit amaçlı cihazın yararı, yalnızca ihtiyaç duyulan uygulamalara erişim sağlayarak bireylere anlaşılması kolay bir deneyim sunmasıdır. İhtiyaç duymadıkları uygulamaları ise gözlerinin önünden kaldırır. 
  
    Çoklu uygulama bilgi noktası deneyimi için uygulama eklediğinizde, başlat menüsü düzen dosyası da eklersiniz. [Başlat menüsü düzeni dosyası](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-file-for-intune), Intune’da kullanılabilecek örnek bir XML içerir. 

#### <a name="single-app-kiosks"></a>Tek uygulama bilgi noktaları
Aşağıdaki ayarları girin:

- **Kullanıcı hesabı**: Yerel (cihaz için) kullanıcı hesabını veya bilgi noktası uygulamasıyla ilişkili Azure AD hesap oturum açma bilgilerini girin. Azure AD etki alanlarına katılmış hesapları `domain\username@tenant.org` biçiminde girin. 

    Herkese açık ortamlarda bulunan ve otomatik oturum açma etkin bilgi noktaları için olabildiğince az ayrıcalığa sahip bir kullanıcı türü (yerel standart kullanıcı hesabı gibi) kullanılmalıdır. Bir Azure Active Directory (AD) hesabını bilgi noktası moduna yapılandırmak için `AzureAD\user@contoso.com` biçimini kullanın.

- **Uygulamanın uygulama kullanıcı modeli kimliği (AUMID)**: Bilgi noktası uygulamasının AUMID’sini girin. Daha fazla bilgi için bkz. [Yüklü bir uygulamanın Uygulama Kullanıcı Model Kimliğini bulma](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

## <a name="reporting-and-telemetry"></a>Raporlama ve Telemetri

- **Kullanım verilerini paylaş** - Tanılama verilerinin gönderim düzeyini seçin.
