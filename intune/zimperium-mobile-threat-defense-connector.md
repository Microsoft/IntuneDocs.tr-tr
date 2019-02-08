---
title: Intune ile Zimperium MTD bağlayıcısı
titleSuffix: Intune on Azure
description: Şirket kaynaklarınıza mobil cihaz erişimini kontrol etmek için Zimperium Mobile Threat Defense’i Intune ile tümleştirme hakkında bilgi edinin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/29/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 975d8d84-792a-41ad-925a-4a7f1ae4dcaf
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ed8bd99a5013ccb01525b8216ef1250c2a61f20b
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55848602"
---
# <a name="zimperium-mobile-threat-defense-connector-with-intune"></a>Intune ile Zimperium Mobile Threat Defense bağlayıcısı

Microsoft Intune ile tümleşen Mobile Threat Defense (MTD) çözümü olan Zimperium tarafından yapılan risk değerlendirmesine göre koşullu erişim kullanarak mobil cihazlardan şirket kaynaklarına erişimi denetleyebilirsiniz. Risk, Zimperium uygulamasını çalıştıran cihazlardan toplanan telemetriye göre değerlendirilir.

Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen Zimperium risk değerlendirmesine dayalı koşullu erişim ilkelerini yapılandırabilirsiniz. Risk değerlendirmesi ilke izin verebilir veya uyumlu olmayan cihazların algılanan tehditlere dayalı olarak şirket kaynaklarına erişmesini engelleyin.

## <a name="how-do-intune-and-zimperium-help-protect-your-company-resources"></a>Intune ve Zimperium şirket kaynaklarınızın korunmasına nasıl yardımcı olur?

Android ve iOS için Zimperium uygulaması dosya sistemi, ağ yığını, cihaz ve varsa uygulama telemetrisini yakalar ve telemetri verilerini mobil tehditlere karşı cihaz riskini değerlendirmek için Zimperium bulut hizmetine gönderir.

Intune cihaz uyumluluğu ilkesi, Zimperium Mobile Threat Defense için Zimperium risk değerlendirmesini temel alan bir kural içerir. Bu kural etkinleştirildiğinde Intune, cihazın etkinleştirdiğiniz ilke ile uyumluluğunu değerlendirir. Cihaz uyumsuz bulunursa kullanıcıların Exchange Online ve SharePoint Online gibi kurumsal kaynaklara erişimi engellenir. Kullanıcılar ayrıca, sorunu çözmek ve kurumsal kaynaklara yeniden erişim kazanmak için cihazlarında yüklü olan Zimperium uygulamasından yönergeler alır.

## <a name="sample-scenarios"></a>Örnek senaryolar

Aşağıda Zimperium ile Intune tümleştirmesi için birkaç senaryo bulabilirsiniz:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kötü amaçlı uygulamalardan kaynaklanan tehditlere dayalı olarak erişimi denetleme

Cihazlarda kötü amaçlı yazılım gibi kötü amaçlı uygulamalar algılandığında, tehdit çözülene kadar cihazları engelleyebilirsiniz:

-   Şirket e-postasına bağlanma

-   OneDrive İş uygulaması ile şirket dosyalarını eşitleme

-   Şirket uygulamalarına erişme

**Kötü amaçlı yazılımlar algılandığında engelleme:**

![Kötü amaçlı uygulamalar algılandı kavramsal resmi](./media/Maliciousapps_blocked_Zimperium.png)

**Düzeltme ile erişim izni verildi:**

![Kavramsal resmi düzeltme sonra erişim izni verildi](./media/maliciousapps_unblocked_Zimperium.png)

### <a name="control-access-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak erişimi denetleme

Gibi tehditleri algılayın **adam-de-ADAM** ağda ve cihaz riskine dayalı olarak Wi-Fi ağlarına erişimi koruyun.

**Wi-Fi üzerinden ağ erişimini engelleme:**

![Wi-Fi üzerinden ağ erişimini engelleme](./media/network_wifi_blocked_Zimperium.png)

**Düzeltme ile erişim izni verildi:**

![Düzeltme ile erişim izni verildi](./media/network_wifi_unblocked_Zimperium.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak SharePoint Online’a erişimi denetleme

Gibi tehditleri algılayın **adam-de-ADAM** ağda ve cihaz riskine dayalı olarak Kurumsal dosyaların eşitlenmesini engeller.

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

    -   Daha fazla bilgi için [Zimperium Web sitesi](https://www.zimperium.com/zips-mobile-ips).

## <a name="next-steps"></a>Sonraki adımlar

- [Zimperium'u Intune ile tümleştirme](zimperium-mtd-connector-integration.md)

- [Zimperium uygulamalarını ayarlama](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Zimperium cihaz uyumluluk ilkesi oluşturma](mtd-device-compliance-policy-create.md)

- [Zimperium MTD bağlayıcısını etkinleştirme](mtd-connector-enable.md)
