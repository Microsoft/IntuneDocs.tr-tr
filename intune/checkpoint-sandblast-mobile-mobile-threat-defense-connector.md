---
title: Check Point SandBlast MTD ayarlama | Microsoft Intune
titlesuffix: Microsoft Intune
description: Şirket kaynaklarınıza mobil cihaz erişimini kontrol etmek için Check Point SandBlast Mobile Threat Defense’i Intune ile tümleştirme hakkında bilgi edinin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/03/2017
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 706a4228-9bdf-41e0-b8d1-64c923dd2d2b
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: fc506b6cefe25f937b38f09a0635e94d9802807e
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57399455"
---
# <a name="check-point-sandblast-mobile-threat-defense-connector-with-intune"></a>Check Point SandBlast Mobile Threat Defense bağlayıcısı ile Intune

Microsoft Intune ile tümleşik çalışan mobil tehdit savunması çözümü Check Point SandBlast Mobile tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihazlardan şirket kaynaklarına erişimi denetleyebilirsiniz. Risk, Check Point SandBlast Mobile uygulamasını çalıştıran cihazlardan toplanan telemetriye göre değerlendirilir.

Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen Check Point SandBlast Mobile risk değerlendirmesini temel alan koşullu erişim ilkelerini yapılandırabilirsiniz. Algılanan tehditler temelinde, uyumlu olmayan cihazların şirket kaynaklarına erişimine izin vermek veya erişimini engellemek için bu ilkeler kullanılabilir.

## <a name="how-do-intune-and-check-point-sandblast-mobile-help-protect-your-company-resources"></a>Intune ve Check Point SandBlast Mobile, şirket kaynaklarınızın korunmasına nasıl yardımcı olur?

Android ve iOS için Check Point SandBlast Mobile uygulaması dosya sistemi, ağ yığını, cihaz ve uygulama telemetrisini (varsa) yakalar ve mobil tehditlere karşı cihazın riskini değerlendirmek için telemetri verilerini Check Point SandBlast bulut hizmetine gönderir.

Intune cihaz uyumluluğu ilkesi, Check Point SandBlast risk değerlendirmesini temel alan bir Check Point SandBlast Mobile Tehdit Savunmasına yönelik bir kural içerir. Bu kural etkinleştirildiğinde Intune, cihazın etkinleştirdiğiniz ilke ile uyumluluğunu değerlendirir. Cihaz uyumsuz bulunursa kullanıcıların Exchange Online ve SharePoint Online gibi kurumsal kaynaklara erişimi engellenir. Kullanıcılar ayrıca, sorunu çözmek ve kurumsal kaynaklara yeniden erişim kazanmak için cihazlarında yüklü olan Check Point SandBlast mobil uygulamasından yol gösteren yönergeler alır.

<!-- ## Sample scenarios 
closing syntax for comment above is missing. Please insert closing syntax at intended location. -->

Burada sık karşılaşılan bazı senaryolar verilmiştir:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kötü amaçlı uygulamalardan kaynaklanan tehditlere dayalı olarak erişimi denetleme

Cihazlarda kötü amaçlı yazılım gibi kötü amaçlı uygulamalar algılandığında, tehdit çözülene kadar cihazları engelleyebilirsiniz:

-   Şirket e-postasına bağlanma

-   OneDrive İş uygulaması ile şirket dosyalarını eşitleme

-   Şirket uygulamalarına erişme

**Kötü amaçlı yazılımlar algılandığında engelleme:**

![Kötü amaçlı yazılımlar algılandığında Check Point MTD engellemesi](./media/checkpoint-MTD-2.PNG)

**Düzeltme ile erişim izni verildi:**

![Check Point MTD erişim izni verildi](./media/checkpoint-MTD-3.PNG)

### <a name="control-access-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak erişimi denetleme

Gibi tehditleri algılayın **adam-de-ADAM** ağda ve cihaz riskine dayalı olarak Wi-Fi ağlarına erişimi koruyun.

**Wi-Fi üzerinden ağ erişimini engelleme:**

![Wi-Fi üzerinden Check Point MTD ağ erişimini engelleme](./media/checkpoint-MTD-4.PNG)

**Düzeltme ile erişim izni verildi:**

![Check Point MTD Wi-Fi erişim izni verildi](./media/checkpoint-MTD-5.PNG)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak SharePoint Online’a erişimi denetleme

Gibi tehditleri algılayın **adam-de-ADAM** ağda ve cihaz riskine dayalı olarak Kurumsal dosyaların eşitlenmesini engeller.

**Ağ tehditleri algılandığında SharePoint Online’ı engelle:**

![Check Point MTD SharePoint Online erişimini engelleme](./media/checkpoint-MTD-6.PNG)

**Düzeltme ile erişim izni verildi:**

![Check Point MTD SharePoint Online erişim izni verildi](./media/checkpoint-MTD-7.PNG)

## <a name="supported-platforms"></a>Desteklenen platformlar

-   **Android 4.1 ve üzeri**

-   **iOS 8 ve üzeri**

## <a name="pre-requisites"></a>Ön koşullar

-   Azure Active Directory Premium

-   Microsoft Intune aboneliği

-   Check Point SandBlast Mobile Threat Defense aboneliği
    -   Daha fazla bilgi için bkz. [CheckPoint SandBlast web sitesi](https://www.checkpoint.com/).

## <a name="next-steps"></a>Sonraki adımlar

- [Check Point SandBlast ile Intune tümleştirmesi](checkpoint-sandblast-mobile-mtd-connector-integration.md)

- [CheckPoint SandBlast Mobile uygulama kurulumu](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [CheckPoint SandBlast Mobile cihaz uyumluluk ilkesi oluşturma](mtd-device-compliance-policy-create.md)

- [CheckPoint SandBlast Mobile MTD bağlayıcısı](mtd-connector-enable.md)
