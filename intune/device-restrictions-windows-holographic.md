---
title: Windows Holographic iş cihaz ayarları - Microsoft Intune - Azure | Microsoft Docs
description: Windows Holographic for Business için Microsoft Intune’da kaydı kaldırma, coğrafi konum, parolalar, uygulama mağazasından uygulama yükleme, Microsoft Edge’de çerezler ve açılır pencereler, Windows Defender, arama, bulut ve depolama, bluetooth bağlantısı, sistem saati ve Azure’da kullanım verileri gibi cihaz kısıtlama ayarları hakkında bilgi edinin ve bu ayarları yapılandırın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: cdac4623c6c5c9e7258897e1536856e6b24492ea
ms.sourcegitcommit: fff179f59bd542677cbd4bf3bacc24bb880e2cb6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2018
ms.locfileid: "53032019"
---
# <a name="windows-holographic-for-business-device-settings-to-allow-or-restrict-features-using-intune"></a>Windows Holographic for Business izin vermek veya Intune kullanarak özellikleri kısıtlamak için cihaz ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makale, listeler ve farklı ayarları denetleyebilirsiniz gibi Microsoft Hololens cihazları Windows Holographic for Business açıklar. Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, izin veya özellikler, güvenlik denetimi ve daha fazla devre dışı için bu ayarları kullanın.

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz yapılandırma profili oluşturma](device-restrictions-configure.md).

## <a name="general"></a>Genel

- **Elle kayıt kaldırmaya**: kullanıcının iş yeri hesabını CİHAZDAN el ile silmesine olanak sağlar.
- **Cortana**: etkinleştirmek veya Cortana sesli Yardımcısını devre dışı bırakın.
- **Coğrafi konum**: cihazın konum Hizmetleri bilgilerini kullanıp kullanamayacağını belirtir.

## <a name="password"></a>istemcisiyle yönetilen bir cihaz için)

- **Parola**: son kullanıcının cihaza erişmek için parola girmesini zorunlu tutun.
- **Cihaz boşta durumundan çıkarken parola iste**: kullanıcının cihaz kilidini açmak için bir parola girmesi gerektiğini belirtir.

## <a name="app-store"></a>Uygulama Mağazası

- **Mağaza uygulamalarını otomatik güncelleştir**: otomatik olarak güncelleştirilmesi için Microsoft Store yüklenen uygulamaların verir.
- **Güvenilir Uygulama yüklemesi**: dışarıdan yüklenmesine izin güvenilen bir sertifikayla imzalanan uygulamaların sağlar.
- **Geliştirici kilidini açma**: dışarıdan yüklenen uygulamaların son kullanıcı tarafından değiştirilmesine izin verme gibi Windows izin Geliştirici ayarları.

## <a name="microsoft-edge-browser"></a>Microsoft Edge Tarayıcısı

- **Tanımlama bilgilerini**: tarayıcının internet tanımlama bilgilerini cihaza kaydetmesine olanak tanır.
- **Açılır pencereler**: (yalnızca Windows 10 Masaüstü için geçerlidir) tarayıcıdaki açılır pencereleri engeller.
- **Arama önerileri**: siz arama tümcecikleri yazarken arama motorunuzun site olanak tanır.
- **Parola Yöneticisi**: etkinleştirmek veya Microsoft Edge parola Yöneticisi özelliğini devre dışı bırakın.
- **Kullanıcıyı-izleme üst bilgileri gönderme**: göndermek için Microsoft Edge tarayıcısı yapılandırır üst bilgileri, kullanıcıların ziyaret ettiği Web sitelerine izleme (Dnt).

## <a name="windows-defender-smart-screen"></a>Windows Defender Smart Screen

- **Microsoft Edge için SmartScreen**: site ve dosya yüklemeleri erişmek için Microsoft Edge Smartscreen'i etkinleştirin.

## <a name="search"></a>Ara

- **Arama konumu** - Aramanın konumu kullanıp kullanamayacağını belirtin. bilgiler

## <a name="cloud-and-storage"></a>Bulut ve Depolama

- **Microsoft hesabı**: kullanıcının bir Microsoft hesabını cihazla ilişkilendirmesine olanak sağlar.

## <a name="cellular-and-connectivity"></a>Hücresel ve Bağlantı

- **Bluetooth**: kullanıcı etkinleştirebilir ve cihazda Bluetooth yapılandırmasına olup olmadığını denetler.
- **Bluetooth bulunabilirlik**: cihazın diğer Bluetooth özellikli cihazlar tarafından bulunabilmesine olanak sağlar.
- **Bluetooth reklamlarına**: cihazın Bluetooth üzerinden reklam almasına izin verir.

## <a name="control-panel-and-settings"></a>Denetim Masası ve Ayarlar

- **Sistem saatinin değiştirilmesi**: son kullanıcının cihazın tarih ve saatini değiştirmelerini engeller.

## <a name="kiosk---obsolete"></a>Bilgi noktası - Eski

Bu ayarlar salt okunurdur ve değiştirilemez. Bilgi noktası modunu yapılandırmak için bkz. [Bilgi noktası ayarları](kiosk-settings.md#windows-holographic-for-business).

Bir bilgi noktası cihazı genellikle belirli bir uygulama çalıştırır. Kullanıcıların cihazda bilgi noktası uygulaması dışında başka özellik veya işlevlere erişimi engellenmiştir.

- **Bilgi noktası modu**: ilke tarafından desteklenen bilgi noktası modu türünü belirler. Şu seçenekler mevcuttur:

  - **Yapılandırılmamış** (varsayılan): İlke, bilgi noktası modunu etkinleştirmez. 
  - **Tek uygulama bilgi noktası**: Profil, cihazın yalnızca bir uygulama çalıştırmasına olanak tanır. Kullanıcı oturum açtığında belirli bir uygulama başlar. Bu mod ayrıca kullanıcının yeni uygulamalar açmasını veya çalışan uygulamayı değiştirmesini önler.
  - **Çoklu uygulama bilgi noktası**: Profil, cihazın birden fazla uygulama çalıştırmasına olanak tanır. Yalnızca eklediğiniz uygulamalar kullanıcı tarafından kullanılabilir. Bir çoklu uygulama bilgi noktasının veya sabit amaçlı cihazın yararı, yalnızca ihtiyaç duyulan uygulamalara erişim sağlayarak bireylere anlaşılması kolay bir deneyim sunmasıdır. İhtiyaç duymadıkları uygulamaları ise gözlerinin önünden kaldırır. 
  
    Çoklu uygulama bilgi noktası deneyimi için uygulama eklediğinizde, başlat menüsü düzen dosyası da eklersiniz. [Başlat menüsü düzeni dosyası](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-file-for-intune), Intune’da kullanılabilecek örnek bir XML içerir. 

#### <a name="single-app-kiosks"></a>Tek uygulama bilgi noktaları

Aşağıdaki ayarları girin:

- **Kullanıcı hesabı**: yerel (cihaz) kullanıcı hesabını veya Azure AD hesabını girin bilgi noktası uygulamasıyla ilişkili oturum açma. Azure AD etki alanlarına katılmış hesapları `domain\username@tenant.org` biçiminde girin. 

    Herkese açık ortamlarda bulunan ve otomatik oturum açma etkin bilgi noktaları için olabildiğince az ayrıcalığa sahip bir kullanıcı türü (yerel standart kullanıcı hesabı gibi) kullanılmalıdır. Bir Azure Active Directory (AD) hesabını bilgi noktası moduna yapılandırmak için `AzureAD\user@contoso.com` biçimini kullanın.

- **Uygulama kullanıcı modeli kimliği (AUMID)**: bilgi noktası uygulamasının AUMID'sini girin. Daha fazla bilgi için bkz. [Yüklü bir uygulamanın Uygulama Kullanıcı Model Kimliğini bulma](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

## <a name="reporting-and-telemetry"></a>Raporlama ve Telemetri

- **Kullanım verilerini paylaş**: tanılama verisi gönderme düzeyini seçin.
