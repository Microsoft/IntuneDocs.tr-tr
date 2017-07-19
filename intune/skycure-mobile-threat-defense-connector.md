---
title: "Intune ile Skycure bağlayıcısı"
titleSuffix: Intune on Azure
description: "Intune ile Skycure bağlayıcısı tümleştirmesi."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: df4ce3f6-a093-432c-ab86-7a83865e389e
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c55fa5b3ea86127648850ae7374107ca65db9764
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="skycure-mobile-threat-defense-connector"></a>Skycure Mobile Threat Defense bağlayıcısı

Microsoft Intune ile tümleşik çalışan mobil tehdit koruması çözümü Skycure tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihazlardan şirket kaynaklarına erişimi denetleyebilirsiniz. Risk, Skycure çalıştıran cihazlardan toplanan ve aşağıdakileri içeren telemetriye göre değerlendirilir:

-   Fiziksel savunma

-   Ağ savunması

-   Uygulama savunması

-   Güvenlik açıkları savunması

Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen Skycure risk değerlendirmesi temel alan koşullu erişim ilkelerini yapılandırabilirsiniz. Algılanan tehditler temelinde, uyumlu olmayan cihazların şirket kaynaklarına erişimine izin vermek veya erişimini engellemek için bu ilkeler kullanılabilir.

## <a name="how-do-intune-and-skycure-help-protect-your-company-resources"></a>Intune ve Skycure şirket kaynaklarınızın korunmasına nasıl yardımcı olur?

Android veya iOS için Skycure mobil uygulaması dosya sistemi, ağ yığını, cihaz ve uygulama telemetrisini (varsa) yakalar ve mobil tehditlere karşı cihazın riskini değerlendirmek için bunları Skycure bulut hizmetine gönderir.

Intune cihaz uyumluluğu ilkesi, Skycure risk değerlendirmesini temel alan bir Skycure Mobile Threat Defense’e yönelik bir kural içerir. Bu kural etkinleştirildiğinde Intune, cihazın etkinleştirdiğiniz ilke ile uyumluluğunu değerlendirir.

Cihaz uyumsuz bulunursa Exchange Online ve SharePoint Online gibi kaynaklara erişim engellenir. Engellenen cihazlardaki kullanıcılar Skycure mobil uygulamasından sorunu çözmek ve şirket kaynaklarına yeniden erişim kazanmak için yol gösteren yönergeler alır.

Intune, Skycure ile iki tümleştirme modunu destekler:

-   **Temel kurulum**, Intune’daki cihazlar için Skycure görünürlüğüne olanak tanıyan salt okunur modudur.

-   **Tam tümleştirme**, Skycure’un Intune’a cihazın risk ve güvenlik olayı ayrıntılarını raporlamasına olanak tanır.

## <a name="sample-scenarios"></a>Örnek senaryolar

Burada sık karşılaşılan bazı senaryolar verilmiştir:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kötü amaçlı uygulamalardan kaynaklanan tehditlere dayalı olarak erişimi denetleme

Cihazlarda kötü amaçlı yazılım gibi kötü amaçlı uygulamalar algılandığında, tehdit çözülene kadar cihazları engelleyebilirsiniz:

-   Şirket e-postasına bağlanma

-   OneDrive İş uygulaması ile şirket dosyalarını eşitleme

-   Şirket uygulamalarına erişme

**Kötü amaçlı yazılımlar algılandığında engelleme:**

![Kötü amaçlı uygulamalar algılandı](./media/skycure-arch-1.png)

**Düzeltme ile erişim izni verildi:**

![Kötü amaçlı uygulamalar algılandı erişim izni verildi](./media/skycure-arch-2.png)

### <a name="control-access-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak erişimi denetleme

Ağda **bağlantıyı izinsiz izleme** gibi tehditleri algılayın ve cihaz riskine dayalı olarak Wi-Fi ağlarına erişimi koruyun.

**Wi-Fi üzerinden ağ erişimini engelleme:**

![Wi-Fi üzerinden ağ erişimini engelleme](./media/skycure-arch-3.png)

**Düzeltme ile erişim izni verildi:**

![Düzeltme ile erişim izni verildi](./media/skycure-arch-4.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak SharePoint Online’a erişimi denetleme

Ağda **Bağlantıyı izinsiz izleme** gibi tehditleri algılar ve cihaz riskine dayalı olarak kurumsal dosyaların eşitlenmesini engeller.

**Ağ tehditleri algılandığında SharePoint Online’ı engelle:**

![Ağ tehditleri algılandığında SharePoint Online’ı engelleme](./media/skycure-arch-5.png)

**Düzeltme ile erişim izni verildi:**

![Sharepoint için düzeltme ile erişim izni verme örneği](./media/skycure-arch-6.png)

## <a name="supported-platforms"></a>Desteklenen platformlar

-   **Android 4.1 ve üzeri**

-   **iOS 8 ve üzeri**

## <a name="pre-requisites"></a>Ön koşullar

-   Azure Active Directory Premium

-   Microsoft Intune aboneliği

-   Skycure Mobile Threat Defense aboneliği

Daha fazla bilgi için [Skycure web sitesini](https://www.skycure.com/skycure-microsoft-integration/) gözden geçirin.

## <a name="next-steps"></a>Sonraki adımlar

Burada, Intune’u Skycure ile tümleştirme işlemini tamamlamak için gereken adımlar verilmiştir:

1.  [Skycure’u Azure Active Directory Çoklu Oturum Açma (SSO) kullanacak şekilde yapılandırma](skycure-azure-sso-configure.md)

2.  [Skycure iOS uygulaması yapılandırma ilkesini indirme](skycure-ios-app-configuration-policy-download.md)

3.  [Skycure uygulamaları, Microsoft Authenticator ve iOS uygulama yapılandırma ilkesi ekleme ve atama](mtd-apps-ios-app-configuration-policy-add-assign.md)

4.  [Intune ile Skycure tümleştirmesi kurma](skycure-mtd-connector-integration.md)

5.  [Intune’da Skycure Mobile Threat Defense’i etkinleştirme](mtd-connector-enable.md)

6.  [Intune’da Skycure Mobile Threat Defense cihaz uyumluluk ilkesi oluşturma](mtd-device-compliance-policy-create.md)
