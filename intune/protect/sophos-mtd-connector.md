---
title: Intune ile Sophos Mobile kullanma
titleSuffix: Intune on Azure
description: Şirket kaynaklarınıza mobil cihaz erişimini denetlemek için Microsoft Intune ile Sophos Mobile çözümünü kullanma.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9bacc784b9d9498196186b1fac0ef948789832b5
ms.sourcegitcommit: dd6755383ba89824d1cc128698a65fde6bb2de55
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306840"
---
# <a name="sophos-mobile-threat-defense-connector-with-intune"></a>Intune ile Sophos Mobile Threat Defense Bağlayıcısı
Microsoft Intune ile tümleştirilen bir Mobile Threat Defense (MTD) çözümü olan Sophos Mobile tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihaz erişimini kontrol edebilirsiniz. Risk, Sophos mobil uygulamasını çalıştıran cihazlardan toplanan telemetriye göre değerlendirilir.
Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen Sophos Mobile risk değerlendirmesini temel alan koşullu erişim ilkelerini, algılanan tehditlere dayalı olarak uyumlu olmayan cihazların şirket kaynaklarına erişmesine izin vermek veya erişimi engellemek için kullanabileceğiniz şekilde yapılandırabilirsiniz.

## <a name="how-do-intune-and-sophos-mobile-help-protect-your-company-resources"></a>Intune ve Sophos Mobile, şirket kaynaklarınızın korunmasına nasıl yardımcı olur?
Android ve iOS için Sophos Mobile uygulaması dosya sistemi, ağ yığını, cihaz ve kullanılabilir olduğunda uygulama telemetrisini yakalar ve ardından telemetri verilerini, cihazın mobil tehditlere karşı riskini değerlendirmek için Sophos Mobile bulut hizmetine gönderir.
Intune cihaz uyumluluk ilkesi, Sophos Mobile risk değerlendirmesini temel alan bir Sophos Mobile Threat Defense kuralı içerir. Bu kural etkinleştirildiğinde, Intune, etkin olan ilkeyle cihaz uyumluluğunu değerlendirir. Cihaz uyumsuz bulunursa kullanıcıların Exchange Online ve SharePoint Online gibi kurumsal kaynaklara erişimi engellenir. Kullanıcılar ayrıca, sorunu çözmek ve kurumsal kaynaklara yeniden erişim kazanmak için cihazlarında yüklü olan Sophos mobil uygulamasından kılavuz alır.  

## <a name="sample-scenarios"></a>Örnek senaryolar
Bazı yaygın senaryolar aşağıda verilmiştir.  
### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kötü amaçlı uygulamalardan gelen tehditlere dayalı olarak erişimi denetleme
Cihazlarda kötü amaçlı yazılım gibi kötü amaçlı uygulamalar algılandığında, tehdit çözümlenene kadar cihazları aşağıdaki eylemlerden engelleyebilirsiniz:
- Kurumsal e-postaya bağlanma
- Şirket dosyalarını OneDrive Iş uygulamasıyla eşitleme
- Şirket uygulamalarına erişme

**Kötü amaçlı uygulamalar algılandığında engelle**:
 
![Algılanan kötü amaçlı uygulamaların kavramsal görüntüsü](./media/sophos-mtd-connector/sophos_malicious_apps_blocked.png)  

**Düzeltmeye erişim izni verildi**:  
Düzeltme @ no__t-1 ' den sonra izin verilen erişimin ![ ' dan kavramsal görüntüsü

### <a name="control-access-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak erişimi denetleme  
Ağ ile ilgili tehditleri, ortadaki adam saldırıları gibi algılayın ve cihaz riskine dayalı olarak Wi-Fi ağlarına erişimi koruyun.  

**Wi-Fi üzerinden ağ erişimini engelleyin**:  
![Wi-Fi @ no__t-1 üzerinden ağ erişimini engelleyin

**Düzeltmeye erişim izni verildi**:   
![ düzeltme için @ no__t-1 ile erişim verildi  

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak SharePoint Online 'a erişimi denetleme  
Ağınız için, ortadaki adam saldırıları gibi tehditleri algılayın ve cihaz riskine dayalı olarak kurumsal dosyaların eşitlenmesini önleyin.  

**Ağ tehditleri algılandığında SharePoint Online 'ı engelleyin**:   
![ ağ tehditleri algılandığında SharePoint Online 'ı engelle @ no__t-1  

**Düzeltmeye erişim izni verildi**:  
![Erişim SharePoint için düzeltmeye verildi @ no__t-1  

## <a name="supported-platforms"></a>Desteklenen platformlar  
- Android 5,0 ve üzeri
- iOS 11,0 ve üzeri

## <a name="prerequisites"></a>Önkoşullar  
- Azure Active Directory Premium
- Microsoft Intune aboneliği 
- Sophos Mobile Threat Defense aboneliği

Daha fazla bilgi için bkz. [Sophos Web sitesi](https://www.sophos.com/products/mobile-control).  

## <a name="next-steps"></a>Sonraki adımlar  
- [Sophos ile Intune 'U tümleştirme](sophos-mtd-connector-integration.md)
- [Sophos uygulamalarını ayarlama](mtd-apps-ios-app-configuration-policy-add-assign.md)
- [Sophos cihaz uyumluluk ilkesi oluştur](mtd-device-compliance-policy-create.md)
- [Sophos MTD bağlayıcısını etkinleştir](mtd-connector-enable.md)
