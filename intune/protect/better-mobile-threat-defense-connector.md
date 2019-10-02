---
title: Intune ile Better Mobile Threat Defense bağlayıcısı
titleSuffix: Intune on Azure
description: Intune ile Better Mobile Threat Defense bağlayıcısını ayarlayın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/25/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: dd7401469d6fdc9d8380e27425ad797554e5f243
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71729905"
---
# <a name="better-mobile-threat-defense-connector-with-intune"></a>Intune ile Better Mobile Threat Defense bağlayıcısı

Microsoft Intune ile tümleştirilen Mobile Threat Defense (MTD) çözümü daha Iyi mobil tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihaz erişimini kontrol edebilirsiniz. Risk, Better Mobile uygulamasını çalıştıran cihazlardan toplanan telemetriye göre değerlendirilir.

Koşullu erişim ilkelerini, Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen daha Iyi mobil risk değerlendirmesine göre yapılandırabilirsiniz. Bu, uyumsuz cihazların algılanan tehditler temelinde şirket kaynaklarına erişmesine izin vermek veya erişimi engellemek için kullanabilirsiniz.

## <a name="how-do-intune-and-better-mobile-help-protect-your-company-resources"></a>Intune ve Better Mobile şirket kaynaklarınızın korunmasına nasıl yardımcı olur?

Better Mobile uygulaması mobil cihazlara yüklenir ve mobil cihazlarda çalışır. Bu uygulama varsa dosya sistemi, ağ yığını, cihaz ve uygulama telemetrisini yakalar ve mobil tehditlere karşı cihazın riskini değerlendirmek için verileri Better Mobile bulut hizmetine gönderir.

Intune cihaz uyumluluğu ilkesi, Better Mobile risk değerlendirmesini temel alan Mobile Threat Defense’e yönelik bir kural içerir. Bu kural etkinleştirildiğinde Intune, cihazın etkinleştirdiğiniz ilke ile uyumluluğunu değerlendirir. Cihaz uyumsuz bulunursa kullanıcıların Exchange Online ve SharePoint Online gibi kurumsal kaynaklara erişimi engellenir. Kullanıcılar ayrıca, sorunu çözmek ve kurumsal kaynaklara yeniden erişim kazanmak için cihazlarında yüklü olan Better Mobile uygulamasından yönergeler alır.

## <a name="sample-scenarios"></a>Örnek senaryolar

Burada sık karşılaşılan bazı senaryolar verilmiştir.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kötü amaçlı uygulamalardan kaynaklanan tehditlere dayalı olarak erişimi denetleme

Cihazlarda kötü amaçlı yazılım gibi kötü amaçlı uygulamalar algılandığında, tehdit çözülene kadar cihazların aşağıdaki eylemleri gerçekleştirmesini engelleyebilirsiniz:

- Şirket e-postasına bağlanma

- OneDrive İş uygulaması ile şirket dosyalarını eşitleme

- Şirket uygulamalarına erişme

**Kötü amaçlı yazılımlar algılandığında engelleme:**

![Algılanan kötü amaçlı uygulamaları gösteren resim](./media/better-mobile-threat-defense-connector/better_mobile_maliciousapps_blocked.png)

**Düzeltme ile erişim izni verildi:**

![Kötü amaçlı uygulamalar algılandı erişim izni verildi](./media/better-mobile-threat-defense-connector/better_mobile_maliciousapps_unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak erişimi denetleme

**Bağlantıyı izinsiz izleme** saldırıları gibi ağınıza yönelik tehditleri algılayın ve cihaz riskine dayalı olarak Wi-Fi ağlarına erişimi koruyun.

**Wi-Fi üzerinden ağ erişimini engelleme:**

![Wi-Fi üzerinden ağ erişimini engelleme](./media/better-mobile-threat-defense-connector/better_mobile_network_wifi_blocked.png)

**Düzeltme ile erişim izni verildi:**

![Düzeltilmekte olan erişimi gösteren resim](./media/better-mobile-threat-defense-connector/better_mobile_network_wifi_unblocked.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak SharePoint Online’a erişimi denetleme

**Bağlantıyı izinsiz izleme** saldırıları gibi ağınıza yönelik tehditleri algılayın ve cihaz riskine dayalı olarak kurumsal dosyaların eşitlenmesini engelleyin.

**Ağ tehditleri algılandığında SharePoint Online’ı engelle:**

![Ağ tehditleri algılandığında SharePoint Online’ı engelleme](./media/better-mobile-threat-defense-connector/better_mobile_network_spo_blocked.png)

**Düzeltme ile erişim izni verildi:**

![Sharepoint için düzeltme ile erişim izni verme örneği](./media/better-mobile-threat-defense-connector/better_mobile_network_spo_unblocked.png)

## <a name="supported-platforms"></a>Desteklenen platformlar

- **Android 4.1 ve üzeri**

- **iOS 8.0 ve üzeri**

## <a name="prerequisites"></a>Önkoşullar

- Azure Active Directory Premium

- Microsoft Intune aboneliği

- Better Mobile Threat Defense aboneliği

  - Daha fazla bilgi için [Better Mobile web sitesine](https://www.better.mobi/) bakın.

## <a name="next-steps"></a>Sonraki adımlar

- [Better Mobile'ı Intune ile tümleştirme](better-mobile-mtd-connector-integration.md)

- [Better Mobile uygulamalarını ayarlama](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Better Mobile cihaz uyumluluk ilkesi oluşturma](mtd-device-compliance-policy-create.md)

- [Better Mobile MTD bağlayıcısını etkinleştirme](mtd-connector-enable.md)
