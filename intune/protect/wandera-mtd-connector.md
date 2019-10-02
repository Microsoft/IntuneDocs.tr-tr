---
title: Intune ile Wandera Mobile Security ayarlama
titleSuffix: Intune on Azure
description: Şirket kaynaklarınıza mobil cihaz erişimini denetlemek için Microsoft Intune ile Wandera Mobile Security 'yi ayarlama.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: f4043ddc2a9f960b30e753c24e0b806e72b6850c
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71732533"
---
# <a name="wandera-mobile-threat-defense-connector-with-intune"></a>Intune ile wandera Mobile Threat Defense Bağlayıcısı  

Wandera tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihazların şirket kaynaklarına erişimini denetleyin. Wandera, Microsoft Intune ile tümleşen bir mobil tehdit savunması (MTD) çözümüdür.  Risk, şu şekilde Wandera hizmeti tarafından toplanan telemetriye göre değerlendirilir:
- İşletim sistemi güvenlik açıkları
- Yüklenen kötü amaçlı uygulamalar
- Kötü amaçlı ağ profilleri
- Cryptojacking

Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen Wandera 'nın risk değerlendirmesini temel alan *koşullu erişim* ilkelerini yapılandırabilirsiniz. Risk değerlendirmesi ilkesi, algılanan tehditlere dayalı olarak uyumlu olmayan cihazların şirket kaynaklarına erişmesine izin verebilir veya erişimi engelleyebilir.  


## <a name="how-do-intune-and-wandera-mobile-threat-defense-help-protect-your-company-resources"></a>Intune ve bir mobil tehdit savunması şirket kaynaklarınızın korunmasına nasıl yardımcı olur?  

Wandera 'nın mobil uygulaması Microsoft Intune kullanarak sorunsuz bir şekilde yüklenir. Bu uygulama dosya sistemi, ağ yığını, cihaz ve uygulama telemetrisini (kullanılabiliyorsa) yakalar. Bu bilgiler, mobil tehditlere karşı cihazın riskini değerlendirmek için Wandera bulut hizmeti ile eşitlenir. Bu risk düzeyi sınıflandırmaları, Wandera konsolunda, RADAR içinde gereksinimlerinize uyacak şekilde yapılandırılabilir.

Intune 'daki uyumluluk ilkesi, Wandera 'nın risk değerlendirmesini temel alan MTD için bir kural içerir. Bu kural etkinleştirildiğinde Intune, cihazın etkinleştirdiğiniz ilke ile uyumluluğunu değerlendirir.

Uyumsuz cihazlarda Office 365 gibi kaynaklara erişim engellenebilir. Engellenen cihazlardaki kullanıcılar, sorunu çözmek ve erişimi yeniden kazanmak için Wandera uygulamasından rehberlik alır.

## <a name="supported-platforms"></a>Desteklenen platformlar  

Aşağıdaki platformlar, Intune 'A kaydolduktan sonra Wandera için desteklenir:

- Android 5,0 ve üzeri  
- iOS 10,2 ve üzeri  

Platform ve cihaz hakkında daha fazla bilgi için bkz. [Wandera Web sitesi](https://www.wandera.com/why-wandera/features/device-support/).

## <a name="prerequisites"></a>Önkoşullar  

- Microsoft Intune aboneliği  
- Azure Active Directory  
- Wandera Mobile Threat Defense (eski adı Wandera)  

Daha fazla bilgi için bkz. [Wandera Mobile Security](https://www.wandera.com/mobile-security/).
 
## <a name="sample-scenarios"></a>Örnek senaryolar

Intune ile Wandera MTD kullanırken yaygın senaryolar aşağıda verilmiştir.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kötü amaçlı uygulamalardan kaynaklanan tehditlere dayalı olarak erişimi denetleme  

Cihazlarda kötü amaçlı yazılım gibi kötü amaçlı uygulamalar algılandığında, tehdidi çözümleyebilmeniz için ortak araçların cihazlarını engelleyebilirsiniz. Ortak bloklar şunlardır:  
- Şirket e-postasına bağlanma  
- OneDrive İş uygulaması ile şirket dosyalarını eşitleme  
- Şirket uygulamalarına erişme  

**Kötü amaçlı uygulamalar algılandığında engelle**:

![Algılanan kötü amaçlı uygulamaların kavramsal görüntüsü](./media/wandera-mtd-connector/wandera-malicious-apps-blocked.png)  

**Düzeltmeye erişim izni verildi**: 

![Düzeltmeden sonra erişim izni verilen kavramsal resim](./media/wandera-mtd-connector/wandera-malicious-apps-unblocked.png)


### <a name="control-access-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak erişimi denetleme  

Ağınızı izinsiz izleme saldırıları ve cihaz riskine dayalı olarak Wi-Fi ağlarına erişimi koruma gibi, ağınıza yönelik tehditleri algılayın.  

**Wi-Fi üzerinden ağ erişimini engelleyin**:  

![Wi-Fi üzerinden ağ erişimini engelleme](./media/wandera-mtd-connector/wandera-network-wifi-blocked.png)

**Düzeltmeye erişim izni verildi**:  

![Düzeltme ile erişim izni verildi](./media/wandera-mtd-connector/wandera-network-wifi-unblocked.png)  

## <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak SharePoint Online’a erişimi denetleme

Bağlantıyı izinsiz izleme saldırıları gibi ağınıza yönelik tehditleri algılar ve cihaz riskine dayalı olarak kurumsal dosyaların eşitlenmesini engeller.

**Ağ tehditleri algılandığında SharePoint Online 'ı engelleyin**:  

![Ağ tehditleri algılandığında SharePoint Online’ı engelleme](./media/wandera-mtd-connector/wandera-network-spo-blocked.png)  


**Düzeltmeye erişim izni verildi**:  

![SharePoint için düzeltmeye erişim verildi örneği](./media/wandera-mtd-connector/wandera-network-spo-unblocked.png)  

## <a name="next-steps"></a>Sonraki adımlar

- [Wandera 'ı Intune ile tümleştirme](wandera-mtd-connector-integration.md)
- [Wandera uygulamaları ayarlama](mtd-apps-ios-app-configuration-policy-add-assign.md)
- [Wandera cihaz uyumluluk ilkesi oluşturma](mtd-device-compliance-policy-create.md)
- [Wandera MTD bağlayıcısını etkinleştir](mtd-connector-enable.md)