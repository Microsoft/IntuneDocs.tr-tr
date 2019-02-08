---
title: Intune ile Pradeo Mobile Threat Defense bağlayıcısı
titleSuffix: Intune on Azure
description: Intune ile Pradeo Mobile Threat Defense bağlayıcısını ayarlayın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: cde4d389-1770-4226-85a3-a2f3b3fb92a3
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 08b2fff66cd231b467cad3701f0e71b373cdb47e
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55847498"
---
# <a name="pradeo-mobile-threat-defense-connector-with-intune"></a>Intune ile Pradeo Mobile Threat Defense bağlayıcısı

Microsoft Intune ile tümleşen Mobile Threat Defense (MTD) çözümü olan Pradeo tarafından yapılan risk değerlendirmesine göre koşullu erişim kullanarak mobil cihazlardan şirket kaynaklarına erişimi denetleyebilirsiniz. Risk, Pradeo uygulamasını çalıştıran cihazlardan toplanan telemetriye göre değerlendirilir.

Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen Pradeo risk değerlendirmesini temel alan koşullu erişim ilkeler yapılandırabilirsiniz. Algılanan tehditler temelinde, uyumlu olmayan cihazların şirket kaynaklarına erişimine izin vermek veya erişimini engellemek için bu ilkeler kullanılabilir.

## <a name="how-do-intune-and-pradeo-help-protect-your-company-resources"></a>Intune ve Pradeo şirket kaynaklarınızın korunmasına nasıl yardımcı olur?

Android ve iOS için Pradeo uygulaması; dosya sistemi, ağ yığını, cihaz ve varsa uygulama telemetrisini yakalar ve telemetri verilerini mobil tehditlere karşı cihaz riskini değerlendirmek için Pradeo bulut hizmetine gönderir.

Intune cihaz uyumluluğu ilkesi, Pradeo risk değerlendirmesini temel alan Pradeo Mobile Threat Defense’e yönelik bir kural içerir. Bu kural etkinleştirildiğinde Intune, cihazın etkinleştirdiğiniz ilke ile uyumluluğunu değerlendirir. Cihaz uyumsuz bulunursa kullanıcıların Exchange Online ve SharePoint Online gibi kurumsal kaynaklara erişimi engellenir. Kullanıcılar ayrıca, sorunu çözmek ve kurumsal kaynaklara yeniden erişim kazanmak için cihazlarında yüklü olan Pradeo uygulamasından yönergeler alır.

## <a name="sample-scenarios"></a>Örnek senaryolar

Burada sık karşılaşılan bazı senaryolar verilmiştir.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kötü amaçlı uygulamalardan kaynaklanan tehditlere dayalı olarak erişimi denetleme

Cihazlarda kötü amaçlı yazılım gibi kötü amaçlı uygulamalar algılandığında, tehdit çözülene kadar cihazların aşağıdaki eylemleri gerçekleştirmesini engelleyebilirsiniz:

-   Şirket e-postasına bağlanma

-   OneDrive İş uygulaması ile şirket dosyalarını eşitleme

-   Şirket uygulamalarına erişme

**Kötü amaçlı yazılımlar algılandığında engelleme:**

![Kötü amaçlı uygulamalar algılandı kavramsal resmi](./media/pradeo_maliciousapps_blocked.png)

**Düzeltme ile erişim izni verildi:**

![Kötü amaçlı uygulamalar algılandı erişim izni verildi](./media/pradeo_maliciousapps_unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak erişimi denetleme

**Bağlantıyı izinsiz izleme** saldırıları gibi ağınıza yönelik tehditleri algılayın ve cihaz riskine dayalı olarak Wi-Fi ağlarına erişimi koruyun.

**Wi-Fi üzerinden ağ erişimini engelleme:**

![Wi-Fi üzerinden ağ erişimini engelleme](./media/pradeo_network_wifi_blocked.png)

**Düzeltme ile erişim izni verildi:**

![Düzeltme ile erişim kavramsal resmi](./media/pradeo_network_wifi_unblocked.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak SharePoint Online’a erişimi denetleme

**Bağlantıyı izinsiz izleme** saldırıları gibi ağınıza yönelik tehditleri algılayın ve cihaz riskine dayalı olarak kurumsal dosyaların eşitlenmesini engelleyin.

**Ağ tehditleri algılandığında SharePoint Online’ı engelle:**

![Ağ tehditleri algılandığında SharePoint Online’ı engelleme](./media/pradeo_network_spo_blocked.png)

**Düzeltme ile erişim izni verildi:**

![Sharepoint örneği için düzeltme erişim kavramsal resmi](./media/pradeo_network_spo_unblocked.png)

## <a name="supported-platforms"></a>Desteklenen platformlar

-   **Android 4.0.3 ve üzeri**

-   **iOS 7 ve üzeri**

## <a name="prerequisites"></a>Önkoşullar

-   Azure Active Directory Premium

-   Microsoft Intune aboneliği

-   Mobile Threat Defense aboneliği için Pradeo Security

    -   Daha fazla bilgi için [Pradeo web sitesine](https://www.pradeo.com/en-US/mobile-threat-protection) bakın.

## <a name="next-steps"></a>Sonraki adımlar

- [Pradeo’yu Intune ile tümleştirme](pradeo-mtd-connector-integration.md)

- [Pradeo uygulamalarını ayarlama](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Pradeo cihaz uyumluluğu ilkesi oluşturma](mtd-device-compliance-policy-create.md)

- [Pradeo MTD bağlayıcısını etkinleştirme](mtd-connector-enable.md)
