---
title: Intune ile Pradeo Mobile Threat Defense bağlayıcısı
titleSuffix: Intune on Azure
description: Şirket kaynaklarınıza mobil cihaz erişimini denetlemek için Intune 'u Pradeo Mobile Threat Defense Bağlayıcısı ile tümleştirmeyi öğrenin.
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
ms.assetid: cde4d389-1770-4226-85a3-a2f3b3fb92a3
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 262d36817e86c8087c6ef4b642d1bd53b1511104
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77782102"
---
# <a name="pradeo-mobile-threat-defense-connector-with-intune"></a>Intune ile Pradeo Mobile Threat Defense bağlayıcısı

Microsoft Intune ile tümleşen bir Mobile Threat Defense (MTD) çözümü olan Pradeo tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihaz erişimini kontrol edebilirsiniz. Risk, Pradeo uygulamasını çalıştıran cihazlardan toplanan telemetriye göre değerlendirilir.

Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen koşullu erişim ilkelerini, algılanan tehditlere dayalı olarak uyumlu olmayan cihazların şirket kaynaklarına erişmesine izin vermek veya erişimi engellemek için kullanabileceğiniz Intune cihaz uyumluluk ilkeleri aracılığıyla yapılandırabilirsiniz.

> [!NOTE]
> Bu mobil tehdit savunma satıcısı, kayıtlı olmayan cihazlar için desteklenmez.

## <a name="how-do-intune-and-pradeo-help-protect-your-company-resources"></a>Intune ve Pradeo şirket kaynaklarınızın korunmasına nasıl yardımcı olur?

Android ve iOS/ıpados için pradeo uygulaması dosya sistemi, ağ yığını, cihaz ve kullanılabilir olduğunda uygulama telemetrisini yakalar ve ardından telemetri verilerini, cihazın mobil tehditlere karşı riskini değerlendirmek için Pradeo bulut hizmetine gönderir.

Intune cihaz uyumluluğu ilkesi, Pradeo risk değerlendirmesini temel alan Pradeo Mobile Threat Defense’e yönelik bir kural içerir. Bu kural etkinleştirildiğinde Intune, cihazın etkinleştirdiğiniz ilke ile uyumluluğunu değerlendirir. Cihaz uyumsuz bulunursa kullanıcıların Exchange Online ve SharePoint Online gibi kurumsal kaynaklara erişimi engellenir. Kullanıcılar ayrıca, sorunu çözmek ve kurumsal kaynaklara yeniden erişim kazanmak için cihazlarında yüklü olan Pradeo uygulamasından yönergeler alır.

## <a name="sample-scenarios"></a>Örnek senaryolar

Burada sık karşılaşılan bazı senaryolar verilmiştir.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kötü amaçlı uygulamalardan kaynaklanan tehditlere dayalı olarak erişimi denetleme

Cihazlarda kötü amaçlı yazılım gibi kötü amaçlı uygulamalar algılandığında, tehdit çözülene kadar cihazların aşağıdaki eylemleri gerçekleştirmesini engelleyebilirsiniz:

- Şirket e-postasına bağlanma

- OneDrive İş uygulaması ile şirket dosyalarını eşitleme

- Şirket uygulamalarına erişme

**Kötü amaçlı yazılımlar algılandığında engelleme:**

![Algılanan kötü amaçlı uygulamaların kavramsal görüntüsü](./media/pradeo-mobile-threat-defense-connector/pradeo_maliciousapps_blocked.png)

**Düzeltme ile erişim izni verildi:**

![Kötü amaçlı uygulamalar algılandı erişim izni verildi](./media/pradeo-mobile-threat-defense-connector/pradeo_maliciousapps_unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak erişimi denetleme

**Bağlantıyı izinsiz izleme** saldırıları gibi ağınıza yönelik tehditleri algılayın ve cihaz riskine dayalı olarak Wi-Fi ağlarına erişimi koruyun.

**Wi-Fi üzerinden ağ erişimini engelleme:**

![Wi-Fi üzerinden ağ erişimini engelleme](./media/pradeo-mobile-threat-defense-connector/pradeo_network_wifi_blocked.png)

**Düzeltme ile erişim izni verildi:**

![Düzeltmeye erişim izni verilen kavramsal resim](./media/pradeo-mobile-threat-defense-connector/pradeo_network_wifi_unblocked.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak SharePoint Online’a erişimi denetleme

**Bağlantıyı izinsiz izleme** saldırıları gibi ağınıza yönelik tehditleri algılayın ve cihaz riskine dayalı olarak kurumsal dosyaların eşitlenmesini engelleyin.

**Ağ tehditleri algılandığında SharePoint Online’ı engelle:**

![Ağ tehditleri algılandığında SharePoint Online’ı engelleme](./media/pradeo-mobile-threat-defense-connector/pradeo_network_spo_blocked.png)

**Düzeltme ile erişim izni verildi:**

![SharePoint için düzeltmeye yönelik kavramsal bir erişim resmi örneği](./media/pradeo-mobile-threat-defense-connector/pradeo_network_spo_unblocked.png)

## <a name="supported-platforms"></a>Desteklenen platformlar

- **Android 4.0.3 ve üzeri**

- **iOS 7 ve üzeri**

## <a name="prerequisites"></a>Önkoşullar

- Azure Active Directory Premium

- Microsoft Intune aboneliği

- Mobile Threat Defense aboneliği için Pradeo Security

  - Daha fazla bilgi için [Pradeo web sitesine](https://www.pradeo.com/en-US/mobile-threat-protection) bakın.

## <a name="next-steps"></a>Sonraki adımlar

- [Pradeo’yu Intune ile tümleştirme](pradeo-mtd-connector-integration.md)

- [Pradeo uygulamalarını ayarlama](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Pradeo cihaz uyumluluğu ilkesi oluşturma](mtd-device-compliance-policy-create.md)

- [Pradeo MTD bağlayıcısını etkinleştirme](mtd-connector-enable.md)
