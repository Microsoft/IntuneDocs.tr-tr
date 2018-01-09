---
title: "Intune ile Zimperium MTD bağlayıcısı"
titleSuffix: Intune on Azure
description: "Intune ile Zimperium bağlayıcısı tümleştirmesi"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 975d8d84-792a-41ad-925a-4a7f1ae4dcaf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 22fbdb95a0fe0c064f07dea2dca50c516b995b8d
ms.sourcegitcommit: a3a744ea55f38a360ca9f788c77a5b3018d1add5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/30/2017
---
# <a name="zimperium-mobile-threat-defense-connector-with-intune"></a>Intune ile Zimperium Mobile Threat Defense bağlayıcısı

Microsoft Intune ile tümleşen Mobile Threat Defense (MTD) çözümü olan Zimperium tarafından yapılan risk değerlendirmesine göre koşullu erişim kullanarak mobil cihazlardan şirket kaynaklarına erişimi denetleyebilirsiniz. Risk, Zimperium uygulamasını çalıştıran cihazlardan toplanan telemetriye göre değerlendirilir.

Koşullu erişim ilkelerini, Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen Zimperium risk değerlendirmesine göre yapılandırabilirsiniz. Algılanan tehditler temelinde, uyumlu olmayan cihazların şirket kaynaklarına erişmesine izin vermek veya erişimini engellemek için bu ilkeleri kullanabilirsiniz.

## <a name="how-do-intune-and-zimperium-help-protect-your-company-resources"></a>Intune ve Zimperium şirket kaynaklarınızın korunmasına nasıl yardımcı olur?

Android ve iOS için Zimperium uygulaması dosya sistemi, ağ yığını, varsa cihaz ve uygulama telemetrisini yakalar ve mobil tehditlere karşı cihazın riskini değerlendirmek için telemetri verilerini Zimperium bulut hizmetine gönderir.

Intune cihaz uyumluluğu ilkesi, Zimperium Mobile Threat Defense için Zimperium risk değerlendirmesini temel alan bir kural içerir. Bu kural etkinleştirildiğinde Intune, cihazın etkinleştirdiğiniz ilke ile uyumluluğunu değerlendirir. Cihaz uyumsuz bulunursa kullanıcıların Exchange Online ve SharePoint Online gibi kurumsal kaynaklara erişimi engellenir. Kullanıcılar ayrıca, sorunu çözmek ve kurumsal kaynaklara yeniden erişim kazanmak için cihazlarında yüklü olan Zimperium uygulamasından yönergeler alır.

## <a name="sample-scenarios"></a>Örnek senaryolar

Aşağıda Zimperium ile Intune tümleştirmesi için birkaç senaryo bulabilirsiniz:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kötü amaçlı uygulamalardan kaynaklanan tehditlere dayalı olarak erişimi denetleme

Cihazlarda kötü amaçlı yazılım gibi kötü amaçlı uygulamalar algılandığında, tehdit çözülene kadar cihazları engelleyebilirsiniz:

-   Şirket e-postasına bağlanma

-   OneDrive İş uygulaması ile şirket dosyalarını eşitleme

-   Şirket uygulamalarına erişme

**Kötü amaçlı yazılımlar algılandığında engelleme:**

![Kötü amaçlı uygulamalar algılandı](./media/Maliciousapps_blocked_Zimperium.png)

**Düzeltme ile erişim izni verildi:**

![Kötü amaçlı uygulamalar algılandı erişim izni verildi](./media/maliciousapps_unblocked_Zimperium.png)

### <a name="control-access-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak erişimi denetleme

Ağda **bağlantıyı izinsiz izleme** gibi tehditleri algılayın ve cihaz riskine dayalı olarak Wi-Fi ağlarına erişimi koruyun.

**Wi-Fi üzerinden ağ erişimini engelleme:**

![Wi-Fi üzerinden ağ erişimini engelleme](./media/network_wifi_blocked_Zimperium.png)

**Düzeltme ile erişim izni verildi:**

![Düzeltme ile erişim izni verildi](./media/network_wifi_unblocked_Zimperium.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak SharePoint Online’a erişimi denetleme

Ağda **Bağlantıyı izinsiz izleme** gibi tehditleri algılar ve cihaz riskine dayalı olarak kurumsal dosyaların eşitlenmesini engeller.

**Ağ tehditleri algılandığında SharePoint Online’ı engelle:**

![Ağ tehditleri algılandığında SharePoint Online’ı engelleme](./media/network_spo_blocked_Zimperium.png)

**Düzeltme ile erişim izni verildi:**

![Sharepoint için düzeltme ile erişim izni verme örneği](./media/network_spo_unblocked_Zimperium.png)

## <a name="supported-platforms"></a>Desteklenen platformlar

-   **Android 4.1 ve üzeri**

-   **iOS 8 ve üzeri**

## <a name="prerequisites"></a>Önkoşullar

-   Azure Active Directory Premium

-   Microsoft Intune aboneliği

-   Zimperium Mobile Threat Defense aboneliği

    -   Daha fazla bilgi için [Zimperium Web sitesi](https://www.zimperium.com/zips-mobile-ips)'ne bakın.

## <a name="next-steps"></a>Sonraki adımlar

- [Zimperium'u Intune ile tümleştirme](zimperium-mtd-connector-integration.md)

- [Zimperium uygulamalarını ayarlama](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Zimperium cihaz uyumluluk ilkesi oluşturma](mtd-device-compliance-policy-create.md)

- [Zimperium MTD bağlayıcısını etkinleştirme](mtd-connector-enable.md)
