---
title: Intune ile Zimperium MTD bağlayıcısı
titleSuffix: Intune on Azure
description: Şirket kaynaklarınıza mobil cihaz erişimini kontrol etmek için Zimperium Mobile Threat Defense’i Intune ile tümleştirme hakkında bilgi edinin.
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
ms.assetid: 975d8d84-792a-41ad-925a-4a7f1ae4dcaf
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 32ace832e44f1cb6d334f69a0c1f03cb41515b2f
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77782038"
---
# <a name="zimperium-mobile-threat-defense-connector-with-intune"></a>Intune ile Zimperium Mobile Threat Defense bağlayıcısı

Microsoft Intune ile tümleştirilen bir Mobile Threat Defense (MTD) çözümü olan Zemium tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihaz erişimini kontrol edebilirsiniz. Risk, Zimperium uygulamasını çalıştıran cihazlardan toplanan telemetriye göre değerlendirilir.

Kayıtlı cihazlar için Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen en yüksek riskli risk değerlendirmesine dayalı koşullu erişim ilkelerini yapılandırabilirsiniz ve bu sayede uyumsuz cihazların algılanan şirket kaynaklarına erişmesine izin vermek veya erişimi engellemek için kullanabilirsiniz tehditleri. Kayıtlı olmayan cihazlar için, algılanan tehditlere dayalı olarak bir blok veya seçmeli Temizleme zorlamak için uygulama koruma ilkelerini kullanabilirsiniz.

## <a name="how-do-intune-and-zimperium-help-protect-your-company-resources"></a>Intune ve Zimperium şirket kaynaklarınızın korunmasına nasıl yardımcı olur?

Android ve iOS/ıpados için zanium uygulaması dosya sistemi, ağ yığını, cihaz ve kullanılabilir olduğunda uygulama telemetrisini yakalar ve mobil tehditlere karşı cihazın riskini değerlendirmek için telemetri verilerini Zıium bulut hizmetine gönderir.

Intune cihaz uyumluluğu ilkesi, Zimperium Mobile Threat Defense için Zimperium risk değerlendirmesini temel alan bir kural içerir. Bu kural etkinleştirildiğinde Intune, cihazın etkinleştirdiğiniz ilke ile uyumluluğunu değerlendirir. Cihaz uyumsuz bulunursa kullanıcıların Exchange Online ve SharePoint Online gibi kurumsal kaynaklara erişimi engellenir. Kullanıcılar ayrıca, sorunu çözmek ve kurumsal kaynaklara yeniden erişim kazanmak için cihazlarında yüklü olan Zimperium uygulamasından yönergeler alır.

## <a name="sample-scenarios"></a>Örnek senaryolar

Aşağıda Zimperium ile Intune tümleştirmesi için birkaç senaryo bulabilirsiniz:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kötü amaçlı uygulamalardan kaynaklanan tehditlere dayalı olarak erişimi denetleme

Cihazlarda kötü amaçlı yazılım gibi kötü amaçlı uygulamalar algılandığında, tehdit çözülene kadar cihazları engelleyebilirsiniz:

- Şirket e-postasına bağlanma

- OneDrive İş uygulaması ile şirket dosyalarını eşitleme

- Şirket uygulamalarına erişme

**Kötü amaçlı yazılımlar algılandığında engelleme:**

![Algılanan kötü amaçlı uygulamaların kavramsal görüntüsü](./media/zimperium-mobile-threat-defense-connector/Maliciousapps_blocked_Zimperium.png)

**Düzeltme ile erişim izni verildi:**

![Düzeltmeden sonra erişim izni verilen kavramsal resim](./media/zimperium-mobile-threat-defense-connector/maliciousapps_unblocked_Zimperium.png)

### <a name="control-access-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak erişimi denetleme

Ağda **bağlantıyı izinsiz izleme** gibi tehditleri algılayın ve cihaz riskine dayalı olarak Wi-Fi ağlarına erişimi koruyun.

**Wi-Fi üzerinden ağ erişimini engelleme:**

![Wi-Fi üzerinden ağ erişimini engelleme](./media/zimperium-mobile-threat-defense-connector/network_wifi_blocked_Zimperium.png)

**Düzeltme ile erişim izni verildi:**

![Düzeltme ile erişim izni verildi](./media/zimperium-mobile-threat-defense-connector/network_wifi_unblocked_Zimperium.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak SharePoint Online’a erişimi denetleme

Ağda **Bağlantıyı izinsiz izleme** gibi tehditleri algılar ve cihaz riskine dayalı olarak kurumsal dosyaların eşitlenmesini engeller.

**Ağ tehditleri algılandığında SharePoint Online’ı engelle:**

![Ağ tehditleri algılandığında SharePoint Online’ı engelleme](./media/zimperium-mobile-threat-defense-connector/network_spo_blocked_Zimperium.png)

**Düzeltme ile erişim izni verildi:**

![Sharepoint için düzeltme ile erişim izni verme örneği](./media/zimperium-mobile-threat-defense-connector/network_spo_unblocked_Zimperium.png)

## <a name="supported-platforms"></a>Desteklenen platformlar

- **Android 4.1 ve üzeri**

- **iOS 8 ve üzeri**

## <a name="prerequisites"></a>Önkoşullar

- Azure Active Directory Premium

- Microsoft Intune aboneliği

- Zimperium Mobile Threat Defense aboneliği

  - Daha fazla bilgi için bkz. [Zkusurium Web sitesi](https://www.zimperium.com/zips-mobile-ips).

## <a name="next-steps"></a>Sonraki adımlar

- [Zimperium'u Intune ile tümleştirme](zimperium-mtd-connector-integration.md)

- [Zimperium uygulamalarını ayarlama](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Zimperium cihaz uyumluluk ilkesi oluşturma](mtd-device-compliance-policy-create.md)

- [Zimperium MTD bağlayıcısını etkinleştirme](mtd-connector-enable.md)

- [MTD uygulama koruma ilkesi oluşturma](../protect/mtd-app-protection-policy.md)
