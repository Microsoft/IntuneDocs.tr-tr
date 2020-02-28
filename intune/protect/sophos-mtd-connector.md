---
title: Intune ile Sophos Mobile kullanma
titleSuffix: Intune on Azure
description: Şirket kaynaklarınıza mobil cihaz erişimini denetlemek için Microsoft Intune ile Sophos Mobile çözümünü kullanma.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/21/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 816968d512b73a8592c7a86b39c41057aa99e827
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77782061"
---
# <a name="sophos-mobile-threat-defense-connector-with-intune"></a>Intune ile Sophos Mobile Threat Defense Bağlayıcısı
Microsoft Intune ile tümleştirilen bir Mobile Threat Defense (MTD) çözümü olan Sophos Mobile tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihaz erişimini kontrol edebilirsiniz. Risk, Sophos mobil uygulamasını çalıştıran cihazlardan toplanan telemetriye göre değerlendirilir.
Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen Sophos Mobile risk değerlendirmesini temel alan koşullu erişim ilkelerini, algılanan tehditlere dayalı olarak uyumlu olmayan cihazların şirket kaynaklarına erişmesine izin vermek veya erişimi engellemek için kullanabileceğiniz şekilde yapılandırabilirsiniz.

> [!NOTE]
> Bu mobil tehdit savunma satıcısı, kayıtlı olmayan cihazlar için desteklenmez.

## <a name="how-do-intune-and-sophos-mobile-help-protect-your-company-resources"></a>Intune ve Sophos Mobile, şirket kaynaklarınızın korunmasına nasıl yardımcı olur?
Android ve iOS/ıpados için Sophos Mobile uygulaması dosya sistemi, ağ yığını, cihaz ve kullanılabilir olduğunda uygulama telemetrisini yakalar ve ardından telemetri verilerini, cihazın mobil tehditlere karşı riskini değerlendirmek için Sophos mobil bulut hizmetine gönderir.
Intune cihaz uyumluluk ilkesi, Sophos Mobile risk değerlendirmesini temel alan bir Sophos Mobile Threat Defense kuralı içerir. Bu kural etkinleştirildiğinde Intune, cihazın etkinleştirdiğiniz ilke ile uyumluluğunu değerlendirir. Cihaz uyumsuz bulunursa kullanıcıların Exchange Online ve SharePoint Online gibi kurumsal kaynaklara erişimi engellenir. Kullanıcılar ayrıca, sorunu çözmek ve kurumsal kaynaklara yeniden erişim kazanmak için cihazlarında yüklü olan Sophos mobil uygulamasından kılavuz alır.  

## <a name="sample-scenarios"></a>Örnek senaryolar
Burada sık karşılaşılan bazı senaryolar verilmiştir.  
### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kötü amaçlı uygulamalardan kaynaklanan tehditlere dayalı olarak erişimi denetleme
Cihazlarda kötü amaçlı yazılım gibi kötü amaçlı uygulamalar algılandığında, tehdit çözülene kadar cihazların aşağıdaki eylemleri gerçekleştirmesini engelleyebilirsiniz:
- Şirket e-postasına bağlanma
- OneDrive İş uygulaması ile şirket dosyalarını eşitleme
- Şirket uygulamalarına erişme

**Kötü amaçlı uygulamalar algılandığında engelle**:
 
![Algılanan kötü amaçlı uygulamaların kavramsal görüntüsü](./media/sophos-mtd-connector/sophos_malicious_apps_blocked.png)  

**Düzeltmeye erişim izni verildi**:  
düzeltmeden sonra erişim izni verilen ![kavramsal görüntüsünü](./media/sophos-mtd-connector/sophos_malicious_apps_unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak erişimi denetleme  
Ağ ile ilgili tehditleri, ortadaki adam saldırıları gibi algılayın ve cihaz riskine dayalı olarak Wi-Fi ağlarına erişimi koruyun.  

**Wi-Fi üzerinden ağ erişimini engelleyin**:  
![Wi-Fi ile ağ erişimini engelleyin](./media/sophos-mtd-connector/sophos_network_wifi_blocked.png)

**Düzeltmeye erişim izni verildi**:   
Düzeltme](./media/sophos-mtd-connector/sophos_network_wifi_unblocked.png) ![erişim izni verildi  

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak SharePoint Online’a erişimi denetleme  
Ağınız için, ortadaki adam saldırıları gibi tehditleri algılayın ve cihaz riskine dayalı olarak kurumsal dosyaların eşitlenmesini önleyin.  

**Ağ tehditleri algılandığında SharePoint Online 'ı engelleyin**:   
![ağ tehditleri algılandığında SharePoint Online 'ı engelleyin](./media/sophos-mtd-connector/sophos_network_spo_blocked.png)  

**Düzeltmeye erişim izni verildi**:  
![erişim SharePoint örneği için düzeltmeye verildi](./media/sophos-mtd-connector/sophos_network_spo_unblocked.png)  

## <a name="supported-platforms"></a>Desteklenen platformlar  
- Android 5,0 ve üzeri
- iOS 11.0 ve üzeri

## <a name="prerequisites"></a>Önkoşullar  
- Azure Active Directory Premium
- Microsoft Intune aboneliği 
- Sophos Mobile Threat Defense aboneliği

Daha fazla bilgi için bkz. [Sophos Web sitesi](https://www.sophos.com/en-us/products/mobile-control.aspx).

## <a name="next-steps"></a>Sonraki adımlar  
- [Sophos ile Intune 'U tümleştirme](sophos-mtd-connector-integration.md)
- [Sophos uygulamalarını ayarlama](mtd-apps-ios-app-configuration-policy-add-assign.md)
- [Sophos cihaz uyumluluk ilkesi oluştur](mtd-device-compliance-policy-create.md)
- [Sophos MTD bağlayıcısını etkinleştir](mtd-connector-enable.md)
