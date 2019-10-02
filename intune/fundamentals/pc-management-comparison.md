---
title: Windows bilgisayarı yönetim seçeneklerini karşılaştırma
titleSuffix: Microsoft Intune
description: Şirkete ait iOS cihazlarını Apple Aygıt Kayıt Programı’nı (DEP) veya Apple Configurator’ı kullanarak kaydetme.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: archived
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 068a73bb-e6b3-44a6-8f6e-4cf7d455bbf3
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: 217b93fcd78010428ce427a755e6c0c20f4372df
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71732221"
---
# <a name="compare-managing-windows-pcs-as-computers-or-mobile-devices"></a>Windows bilgisayarlarını bilgisayar olarak yönetme ile mobil cihaz olarak yönetmeyi karşılaştırma

[!INCLUDE [classic-portal](../../intune-classic/includes/classic-portal.md)]

Kuruluşlar Microsoft Intune'u Windows bilgisayarlarını mobil cihaz yönetimi (MDM) ile mobil cihazlar olarak ya da Intune yazılım istemcisi ile bilgisayarlar olarak yönetmek için kullanabilir.  Microsoft, müşterilerin mümkün olan her durumda MDM yönetim çözümünü kullanmasını önerir. Ancak, bu seçenekler arasındaki farkları daha iyi anlamanıza yardımcı olmak için, bu iki yönetim seçeneği aşağıdaki grafikte karşılaştırılmaktadır.

|**Olanak/ Senaryo** |**Bilgisayar olarak Windows**<br>Intune yazılım istemcisi | **Mobil Cihaz olarak Windows**<br>MDM |
|--------------|-------------------------------|-------------------------------|
|**İşletim sistemleri** |Windows 10, Windows 8+, Windows 7, Windows Vista | Windows 10+ |
|**Intune Portalı desteği** |[Silverlight konsolu](https://manage.microsoft.com)|[Azure portalı](https://portal.azure.com) |
|**Koşullu erişim**|Yok|Kullanılabilir <br>[Koşullu erişim nedir?](../protect/conditional-access.md)|
|**Toplu kayıt**|Yok|Kullanılabilir <br>[Windows cihazlar için toplu kayıt](../enrollment/windows-bulk-enroll.md)|
|**Cihaz profilleri**|Yok|Kullanılabilir <br>[Microsoft Intune cihaz profilleri nelerdir?](../configuration/device-profiles.md)|
|**Aracısız kayıt**|Yok |Kullanılabilir<br>[Windows cihazlarını kaydetme](../enrollment/windows-enroll.md)|
|**Yazılım güncelleştirme yönetimi**| Windows Güncelleştirmeleri ve Microsoft uygulama güncelleştirmeleri<br>[Yazılım güncelleştirmeleri ile Windows bilgisayarları güncel tutma](../keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)|Gerek Windows 10, gerekse Microsoft uygulamaları güncelleştirmeleri için İş İçin Microsoft Mağazası<br> [İş ayarları için Windows Update’i yapılandırma](../protect/windows-update-for-business-configure.md) |
|**Yazılım lisans yönetimi**|Kullanılabilir <br>[Windows bilgisayarı yazılımı için lisans sözleşmelerini yönetme](../manage-license-agreements-for-windows-pc-software-in-microsoft-intune.md)|İş İçin Microsoft Mağazası (yalnızca .appx uygulamaları)<br>[İş İçin Microsoft Mağazası’ndan satın alınan uygulamaları yönetme](../apps/windows-store-for-business.md)|
|**Envanter**|Kullanılabilir <br>[Windows bilgisayarları için donanım ve yazılım envanterini görüntüleme](view-hardware-and-software-inventory-for-windows-pcs-in-microsoft-intune.md)|Kullanılabilir <br>[Uygulama bilgilerini izleme](../apps/apps-monitor.md)<br>[Cihaz yönetimi nedir](../remote-actions/device-management.md)|
|**Windows Güvenlik Duvarı ilkesi**|Kullanılabilir <br>[Windows Güvenlik Duvarı ilkelerini kullanarak Windows bilgisayarlarının korunmasına yardımcı olma](../help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) |Kullanılabilir <br>[Windows Defender Güvenlik Duvarı](../protect/endpoint-protection-windows-10.md#windows-defender-firewall)|
|**Kötü amaçlı yazılımdan koruma**|Uç Nokta Koruma<br>[Endpoint Protection ile Windows bilgisayarların korunmasına yardımcı olma](../help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)|Windows Defender<br>[Windows Defender’ı etkinleştirme](../protect/advanced-threat-protection.md)|
|**Uzaktan yardım** |TeamViewer<br>[Windows bilgisayarlar için uzaktan yardım isteme ve sağlama](request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune.md)|TeamViewer<br> [Intune cihazlarını uzaktan yönetmek için TeamViewer kullanma](../remote-actions/teamviewer-support.md) |
|**Uygulama dağıtımı** | İş İçin Microsoft Mağazası'nda bulunmaz,<br>yalnızca .exe, .appx ve çok dosyalı .msi<br>[Intune yazılım istemcisini çalıştıran Windows bilgisayarlarına uygulama yükleme](add-apps-for-windows-pcs-in-microsoft-intune.md)|Microsoft Mağazası uygulamaları ve iş kolu uygulamaları içindir<br>[Windows mağazası uygulamaları ekleme](../apps/store-apps-windows.md)<br>[Windows iş kolu (LOB) uygulamaları ekleme](../apps/lob-apps-windows.md)|
|**Uygulama koruma**|Yok|Kullanılabilir <br>[Uygulama koruma ilkeleri nedir?](../apps/app-protection-policy.md)|
|**Durum kanıtlama**|Yok|Kullanılabilir|


## <a name="advantages-of-mdm-windows-pc-management"></a>MDM Windows bilgisayarı yönetiminin avantajları
Modern mobil cihaz yönetimi ile Windows bilgisayarı yönetimi aşağıdaki avantajlara sahiptir:
- **Ölçeklenebilirlik** - MDM yönetimi, Intune bulut yönetimi ile birlikte ölçeklenir. Intune yazılım istemcisi, 7000 bilgisayarlar ile sınırlıdır.
- **Basitlik** - İndirilen bir yazılım istemcisine bağımlı olmadan işletim sistemine dahil edilen modern yönetim özelliklerini kullanır
- **Tutarlılık** - Windows bilgisayarlarınız kuruluşunuzdaki diğer tüm mobil cihazlar gibi yönetilir
<!-- - **Cloud optimization** - -->
