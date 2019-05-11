---
title: Intune ile Sophos Mobile tümleştirmesini ayarlama
titleSuffix: Intune on Azure
description: Şirket kaynaklarınıza mobil cihaz erişimini kontrol etmek Intune Sophos mobil çözüm ayarlama yapma.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/30/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 94af7600ddfc5612c666bc38cb871d84c8c4baa5
ms.sourcegitcommit: b1ad73f5c9fd0ad8026c572aef8d15e258951c8f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/29/2019
ms.locfileid: "64880828"
---
# <a name="sophos-mobile-threat-defense-connector-with-intune"></a>Intune ile Sophos Mobile Threat Defense Bağlayıcısı
Şirket kaynaklarına olan Microsoft Intune ile tümleşik bir Mobile Threat Defense (MTD) çözümü Sophos Mobile tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihaz erişimini kontrol edebilirsiniz. Risk, Sophos Mobile uygulamasını çalıştıran cihazlardan toplanan telemetriye göre değerlendirilir.
İzin verme veya engelleme algılanan tehditlere dayalı olarak şirket kaynaklarına erişmek için uyumsuz cihazlar için kullanabileceğiniz Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen Sophos Mobile risk değerlendirmesine dayalı koşullu erişim ilkelerini yapılandırabilirsiniz.

## <a name="how-do-intune-and-sophos-mobile-help-protect-your-company-resources"></a>Nasıl Intune ve Sophos mobil şirket kaynaklarınızın korunmasına yardımcı olur?
Android ve iOS için Sophos mobil uygulama varsa dosya sistemi, ağ yığınını, cihaz ve uygulama telemetrisini yakalar ve ardından telemetri verilerini mobil tehditlere karşı cihazın riskini değerlendirmek için Sophos mobil bulut hizmetine gönderir.
Intune cihaz uyumluluk İlkesi Sophos Mobile risk değerlendirmesini temel alan Sophos Mobile Threat Defense için bir kural içerir. Bu kural etkinleştirildiğinde Intune, cihazın etkinleştirdiğiniz ilke ile uyumluluğunu değerlendirir. Cihaz uyumsuz bulunursa kullanıcıların Exchange Online ve SharePoint Online gibi kurumsal kaynaklara erişimi engellenir. Kullanıcılar ayrıca, sorunu çözmek ve kurumsal kaynaklara yeniden erişim kazanmak için cihazlarında yüklü Sophos mobil uygulamasından yönergeler alır.  

## <a name="sample-scenarios"></a>Örnek senaryolar
Burada sık karşılaşılan bazı senaryolar verilmiştir.  
### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kötü amaçlı uygulamalardan kaynaklanan tehditlere dayalı olarak erişimi denetleme
Cihazlarda kötü amaçlı yazılım gibi kötü amaçlı uygulamalar algılandığında, tehdit çözülene kadar cihazların aşağıdaki eylemleri gerçekleştirmesini engelleyebilirsiniz:
- Şirket e-postasına bağlanma
- OneDrive İş uygulaması ile şirket dosyalarını eşitleme
- Şirket uygulamalarına erişme

**Kötü amaçlı uygulamalar algılandığında engelle**:
 
![Kötü amaçlı uygulamalar algılandı kavramsal resmi](./media/sophos-mtd-connector/sophos_malicious_apps_blocked.png)  

**Düzeltme ile erişim**:  
![Kavramsal resmi düzeltme sonra erişim izni verildi](./media/sophos-mtd-connector/sophos_malicious_apps_unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak erişimi denetleme  
ADAM-de-adam saldırıları gibi ağınıza yönelik tehditleri algılayın ve cihaz riskine dayalı olarak Wi-Fi ağlarına erişimi koruyun.  

**Wi-Fi üzerinden ağ erişimini engelle**:  
![Wi-Fi üzerinden ağ erişimini engelleme](./media/sophos-mtd-connector/sophos_network_wifi_blocked.png)

**Düzeltme ile erişim**:   
![Düzeltme üzerinde erişim izni verildi](./media/sophos-mtd-connector/sophos_network_wifi_unblocked.png)  

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak SharePoint Online’a erişimi denetleme  
ADAM-de-adam saldırıları gibi ağınıza yönelik tehditleri algılayın ve cihaz riskine dayalı olarak Kurumsal dosyaların eşitlenmesini engeller.  

**Blok SharePoint Ağ tehditleri algılandığında çevrimiçi**:   
![Blok SharePoint Ağ tehditleri algılandığında çevrimiçi](./media/sophos-mtd-connector/sophos_network_spo_blocked.png)  

**Düzeltme ile erişim**:  
![Erişim izni verildi Sharepoint örneği için düzeltme](./media/sophos-mtd-connector/sophos_network_spo_unblocked.png)  

## <a name="supported-platforms"></a>Desteklenen platformlar  
- Android 5.0 ve üzeri
- iOS 11.0 ve sonraki

## <a name="prerequisites"></a>Önkoşullar  
- Azure Active Directory Premium
- Microsoft Intune aboneliği 
- Sophos Mobile Threat Defense aboneliği

Daha fazla bilgi için [Sophos Web sitesi](https://www.sophos.com/products/mobile-control).  

## <a name="next-steps"></a>Sonraki adımlar  
- [Sophos Intune ile tümleştirme](sophos-mtd-connector-integration.md)
- [Sophos uygulamalarını ayarlama](mtd-apps-ios-app-configuration-policy-add-assign.md)
- [Sophos cihaz uyumluluk ilkesi oluşturma](mtd-device-compliance-policy-create.md)
- [Sophos MTD bağlayıcısını etkinleştirme](mtd-connector-enable.md)
