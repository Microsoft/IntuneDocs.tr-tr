---
title: Windows bilgisayarı yönetim seçeneklerini karşılaştırma
description: Şirkete ait iOS cihazlarını Apple Aygıt Kayıt Programı’nı (DEP) veya Apple Configurator’ı kullanarak kaydetme
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/27/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 068a73bb-e6b3-44a6-8f6e-4cf7d455bbf3
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c760f9c76e54c0b5f9eb037414870ab1c8943803
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="compare-managing-windows-pcs-as-computers-or-mobile-devices"></a>Windows bilgisayarlarını bilgisayar olarak yönetme ile mobil cihaz olarak yönetmeyi karşılaştırma

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Kuruluşlar Microsoft Intune'u Windows bilgisayarlarını mobil cihaz yönetimi (MDM) ile mobil cihazlar olarak ya da Intune yazılım istemcisi ile bilgisayarlar olarak yönetmek için kullanabilir.  Microsoft, müşterilerin mümkün olan her durumda MDM yönetim çözümünü kullanmasını önerir. Ancak, bu seçenekler arasındaki farkları daha iyi anlamanıza yardımcı olmak için, bu iki yönetim seçeneği aşağıdaki grafikte karşılaştırılmaktadır.

|**Olanak/ Senaryo** |**Bilgisayar olarak Windows**<br>Intune yazılım istemcisi | **Mobil Cihaz olarak Windows**<br>MDM |
|--------------|-------------------------------|-------------------------------|
|**İşletim sistemleri** |Windows 10, Windows 8+, Windows 7, Windows Vista | Windows 10+ |
|**Intune Portalı desteği** |[Silverlight konsolu](https://manage.microsoft.com)|[Azure portalı](https://portal.azure.com) |
|**Koşullu erişim**|Yok|Kullanılabilir <br>[Koşullu erişim nedir?](https://docs.microsoft.com/intune-azure/conditional-access/what-is-conditional-access)|
|**Toplu kayıt**|Yok|Kullanılabilir <br>[Windows cihazlar için toplu kayıt](https://docs.microsoft.com/intune-azure/enroll-devices/bulk-enroll-windows)|
|**Cihaz profilleri**|Yok|Kullanılabilir <br>[Microsoft Intune cihaz profilleri nelerdir?](https://docs.microsoft.com/intune-azure/configure-devices/what-are-device-profiles)|
|**Aracısız kayıt**|Yok |Kullanılabilir<br>[Windows cihazlarını kaydetme](https://docs.microsoft.com/intune-azure/enroll-devices/enroll-windows-devices)|
|**Yazılım güncelleştirme yönetimi**| Windows Güncelleştirmeleri ve Microsoft uygulama güncelleştirmeleri<br>[Yazılım güncelleştirmeleri ile Windows bilgisayarları güncel tutma](https://docs.microsoft.com/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)|Gerek Windows 10, gerekse Microsoft uygulamaları güncelleştirmeleri için İş İçin Microsoft Mağazası<br> [İş ayarları için Windows Update’i yapılandırma](https://docs.microsoft.com/intune-azure/configure-devices/how-to-configure-windows-update-for-business) |
|**Yazılım lisans yönetimi**|Kullanılabilir <br>[Windows bilgisayarı yazılımı için lisans sözleşmelerini yönetme](https://docs.microsoft.com/intune/deploy-use/manage-license-agreements-for-windows-pc-software-in-microsoft-intune)|İş İçin Microsoft Mağazası (yalnızca .appx uygulamaları)<br>[İş İçin Microsoft Mağazası’ndan satın alınan uygulamaları yönetme](https://docs.microsoft.com/intune-azure/manage-apps/wsfb-apps)|
|**Envanter**|Kullanılabilir <br>[Windows bilgisayarları için donanım ve yazılım envanterini görüntüleme](https://docs.microsoft.com/intune/deploy-use/view-hardware-and-software-inventory-for-windows-pcs-in-microsoft-intune)|Kullanılabilir <br>[Uygulama bilgilerini izleme](https://docs.microsoft.com/intune/apps-monitor)<br>[Cihaz yönetimi nedir](https://docs.microsoft.com/intune/device-management)|
|**Windows Güvenlik Duvarı ilkesi**|Kullanılabilir <br>[Windows Güvenlik Duvarı ilkelerini kullanarak Windows bilgisayarlarının korunmasına yardımcı olma](https://docs.microsoft.com/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune) |Yok|
|**Kötü amaçlı yazılımdan koruma**|Uç Nokta Koruma<br>[Endpoint Protection ile Windows bilgisayarların korunmasına yardımcı olma](https://docs.microsoft.com/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)|Windows Defender<br>[Windows Defender ayarları](https://docs.microsoft.com/intune-azure/configure-devices/custom-for-windows-10#windows-defender-settings)|
|**Uzaktan yardım** |TeamViewer<br>[Windows bilgisayarlar için uzaktan yardım isteme ve sağlama](https://docs.microsoft.com/intune/deploy-use/request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune)|Yok |
|**Uygulama dağıtımı** | İş İçin Microsoft Mağazası'nda bulunmaz,<br>yalnızca .exe, .appx ve çok dosyalı .msi<br>[Intune yazılım istemcisini çalıştıran Windows bilgisayarlarına uygulama yükleme](https://docs.microsoft.com/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)|Microsoft Mağazası uygulamaları ve iş kolu uygulamaları içindir<br>[Windows mağazası uygulamaları ekleme](https://docs.microsoft.com/intune/store-apps-windows)<br>[Windows iş kolu (LOB) uygulamaları ekleme](https://docs.microsoft.com/intune/lob-apps-windows)|
|**Uygulama koruma**|Yok|Kullanılabilir <br>[Uygulama koruma ilkeleri nedir?](https://docs.microsoft.com/intune-azure/manage-apps/what-is-app-protection-policy)|
|**Sistem durumu kanıtlama**|Yok|Kullanılabilir|


### <a name="advantages-of-mdm-windows-pc-management"></a>MDM Windows bilgisayarı yönetiminin avantajları
Modern mobil cihaz yönetimi ile Windows bilgisayarı yönetimi aşağıdaki avantajlara sahiptir:
- **Ölçeklenebilirlik** - MDM yönetimi, Intune bulut yönetimi ile birlikte ölçeklenir. Intune yazılım istemcisi, 7000 bilgisayarlar ile sınırlıdır.
- **Basitlik** - İndirilen bir yazılım istemcisine bağımlı olmadan işletim sistemine dahil edilen modern yönetim özelliklerini kullanır
- **Tutarlılık** - Windows bilgisayarlarınız kuruluşunuzdaki diğer tüm mobil cihazlar gibi yönetilir
<!-- - **Cloud optimization** - -->
