---
title: Intune ile Better Mobile Threat Defense bağlayıcısı
titleSuffix: Intune on Azure
description: Intune ile Better Mobile Threat Defense bağlayıcısını ayarlayın.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 7/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.openlocfilehash: 25a6c892284b6014fc3090b3e673c6385ccbad13
ms.sourcegitcommit: 973a06f4a35b74314fece2bae17dd6885b4211c3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42823236"
---
# <a name="better-mobile-threat-defense-connector-with-intune"></a>Intune ile Better Mobile Threat Defense bağlayıcısı

Microsoft Intune ile tümleştirilen Mobile Threat Defense (MTD) çözümü olan Better Mobile tarafından yapılan risk değerlendirmesine göre koşullu erişim kullanarak mobil cihazlardan şirket kaynaklarına erişimi denetleyebilirsiniz. Risk, Better Mobile uygulamasını çalıştıran cihazlardan toplanan telemetriye göre değerlendirilir.

Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen Better Mobile risk değerlendirmesi temelinde koşullu erişim ilkeleri yapılandırabilirsiniz. Bu ilkeleri kullanarak, algılanan tehditler temelinde uyumlu olmayan cihazların şirket kaynaklarına erişmesine izin verebilir veya erişimlerini engelleyebilirsiniz.

## <a name="how-do-intune-and-better-mobile-help-protect-your-company-resources"></a>Intune ve Better Mobile şirket kaynaklarınızın korunmasına nasıl yardımcı olur?

Better Mobile uygulaması mobil cihazlara yüklenir ve mobil cihazlarda çalışır. Bu uygulama varsa dosya sistemi, ağ yığını, cihaz ve uygulama telemetrisini yakalar ve mobil tehditlere karşı cihazın riskini değerlendirmek için verileri Better Mobile bulut hizmetine gönderir.

Intune cihaz uyumluluğu ilkesi, Better Mobile risk değerlendirmesini temel alan Mobile Threat Defense’e yönelik bir kural içerir. Bu kural etkinleştirildiğinde Intune, cihazın etkinleştirdiğiniz ilke ile uyumluluğunu değerlendirir. Cihaz uyumsuz bulunursa kullanıcıların Exchange Online ve SharePoint Online gibi kurumsal kaynaklara erişimi engellenir. Kullanıcılar ayrıca, sorunu çözmek ve kurumsal kaynaklara yeniden erişim kazanmak için cihazlarında yüklü olan Better Mobile uygulamasından yönergeler alır.

## <a name="sample-scenarios"></a>Örnek senaryolar

Burada sık karşılaşılan bazı senaryolar verilmiştir.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kötü amaçlı uygulamalardan kaynaklanan tehditlere dayalı olarak erişimi denetleme

Cihazlarda kötü amaçlı yazılım gibi kötü amaçlı uygulamalar algılandığında, tehdit çözülene kadar cihazların aşağıdaki eylemleri gerçekleştirmesini engelleyebilirsiniz:

-   Şirket e-postasına bağlanma

-   OneDrive İş uygulaması ile şirket dosyalarını eşitleme

-   Şirket uygulamalarına erişme

**Kötü amaçlı yazılımlar algılandığında engelleme:**

![Kötü amaçlı uygulamalar algılandı](./media/better_mobile_maliciousapps_blocked.png)

**Düzeltme ile erişim izni verildi:**

![Kötü amaçlı uygulamalar algılandı erişim izni verildi](./media/better_mobile_maliciousapps_unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak erişimi denetleme

**Bağlantıyı izinsiz izleme** saldırıları gibi ağınıza yönelik tehditleri algılayın ve cihaz riskine dayalı olarak Wi-Fi ağlarına erişimi koruyun.

**Wi-Fi üzerinden ağ erişimini engelleme:**

![Wi-Fi üzerinden ağ erişimini engelleme](./media/better_mobile_network_wifi_blocked.png)

**Düzeltme ile erişim izni verildi:**

![Düzeltme ile erişim izni verildi](./media/better_mobile_network_wifi_unblocked.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak SharePoint Online’a erişimi denetleme

**Bağlantıyı izinsiz izleme** saldırıları gibi ağınıza yönelik tehditleri algılayın ve cihaz riskine dayalı olarak kurumsal dosyaların eşitlenmesini engelleyin.

**Ağ tehditleri algılandığında SharePoint Online’ı engelle:**

![Ağ tehditleri algılandığında SharePoint Online’ı engelleme](./media/better_mobile_network_spo_blocked.png)

**Düzeltme ile erişim izni verildi:**

![Sharepoint için düzeltme ile erişim izni verme örneği](./media/better_mobile_network_spo_unblocked.png)

## <a name="supported-platforms"></a>Desteklenen platformlar

-   **Android 4.1 ve üzeri**

-   **iOS 8.0 ve üzeri**

## <a name="prerequisites"></a>Önkoşullar

-   Azure Active Directory Premium

-   Microsoft Intune aboneliği

-   Better Mobile Threat Defense aboneliği

    -   Daha fazla bilgi için [Better Mobile web sitesine](https://www.better.mobi/) bakın.

## <a name="next-steps"></a>Sonraki adımlar

- [Better Mobile'ı Intune ile tümleştirme](better-mobile-mtd-connector-integration.md)

- [Better Mobile uygulamalarını ayarlama](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Better Mobile cihaz uyumluluk ilkesi oluşturma](mtd-device-compliance-policy-create.md)

- [Better Mobile MTD bağlayıcısını etkinleştirme](mtd-connector-enable.md)