---
title: Skycure mobile threat defense bağlayıcısı
description: Skycure Mobile Threat Defense bağlayıcısı ve Intune ile şirket kaynaklarına erişimi cihaz, ağ ve uygulama riskine dayalı olarak koruyun.
keywords: ''
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7a004e6c-604a-448c-bfb8-cfda63749f5b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f79e793ec6931d6497c6b66eee98aea39786e962
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="skycure-mobile-threat-defense-connector"></a>Skycure Mobile Threat Defense bağlayıcısı

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Microsoft Intune ile tümleşik çalışan mobil tehdit koruması çözümü Skycure tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihazlardan şirket kaynaklarına erişimi denetleyebilirsiniz. Risk, Skycure çalıştıran cihazlardan toplanan ve aşağıdakileri içeren telemetriye göre değerlendirilir:

-   Fiziksel savunma

-   Ağ savunması

-   Uygulama savunması

-   Güvenlik açıkları savunması

Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen Skycure risk değerlendirmesi temel alan koşullu erişim ilkelerini yapılandırabilirsiniz. Algılanan tehditler temelinde, uyumlu olmayan cihazların şirket kaynaklarına erişimine izin vermek veya erişimini engellemek için bu ilkeler kullanılabilir.

## <a name="how-do-intune-and-skycure-help-protect-your-company-resources"></a>Intune ve Skycure şirket kaynaklarınızın korunmasına nasıl yardımcı olur?

Android veya iOS için Skycure mobil uygulaması dosya sistemi, ağ yığını, cihaz ve uygulama telemetrisini (varsa) yakalar ve mobil tehditlere karşı cihazın riskini değerlendirmek için bunları Skycure bulut hizmetine gönderir.

Intune cihaz uyumluluğu ilkesi, Skycure risk değerlendirmesini temel alan bir Skycure mobil tehdit korumasına yönelik bir kural içerir. Bu kural etkinleştirildiğinde Intune, cihazın etkinleştirdiğiniz ilke ile uyumluluğunu değerlendirir.

Cihaz uyumsuz bulunursa Exchange Online ve SharePoint Online gibi kaynaklara erişimi engellenir. Engellenen cihazlardaki kullanıcılar Skycure mobil uygulamasından sorunu çözmek ve şirket kaynaklarına yeniden erişim kazanmak için yol gösteren yönergeler alır.

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

![Kötü amaçlı uygulamalar algılandı](../media/mtp/skycure-arch-1.png)

**Düzeltme ile erişim izni verildi:**

![Kötü amaçlı uygulamalar algılandı erişim izni verildi](../media/mtp/skycure-arch-2.png)

### <a name="control-access-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak erişimi denetleme

Ağda **bağlantıyı izinsiz izleme** gibi tehditleri algılayın ve cihaz riskine dayalı olarak Wi-Fi ağlarına erişimi koruyun.

**Wi-Fi üzerinden ağ erişimini engelleme:**

![Wi-Fi üzerinden ağ erişimini engelleme](../media/mtp/skycure-arch-3.png)

**Düzeltme ile erişim izni verildi:**

![Düzeltme ile erişim izni verildi](../media/mtp/skycure-arch-4.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak SharePoint Online’a erişimi denetleme

Ağda **Bağlantıyı izinsiz izleme** gibi tehditleri algılar ve cihaz riskine dayalı olarak kurumsal dosyaların eşitlenmesini engeller.

**Ağ tehditleri algılandığında SharePoint Online’ı engelle:**

![Ağ tehditleri algılandığında SharePoint Online’ı engelleme](../media/mtp/skycure-arch-5.png)

**Düzeltme ile erişim izni verildi:**

![Sharepoint için düzeltme ile erişim izni verme örneği](../media/mtp/skycure-arch-6.png)

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

1.  [Skycure’u Azure Active Directory Çoklu Oturum Açma (SS) kullanacak şekilde yapılandırma](/intune-classic/deploy-use/configure-skycure-to-use-azure-active-directory-single-sign-on)

2.  [Skycure iOS uygulaması yapılandırma ilkesini indirme](/intune-classic/deploy-use/download-skycure-ios-app-configuration-policy)

3.  [Skycure uygulamalarını, Microsoft Authenticator’ı ve iOS uygulama yapılandırma ilkesini ekleme](/intune-classic/deploy-use/add-skycure-apps-microsoft-authenticator-and-ios-app-configuration-policy)

4.  [Skycure uygulamalarını, Microsoft Authenticator’ı ve iOS uygulama yapılandırma ilkesini dağıtma](/intune-classic/deploy-use/deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy)

5.  [Intune ile Skycure tümleştirmesi kurma](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)

6.  [Intune’da Skycure Mobile Threat Defense’i etkinleştirme](/intune-classic/deploy-use/enable-skycure-mobile-threat-defense-in-intune)

7.  [Intune’da Skycure Mobile Threat Defense uyumluluk ilkesi oluşturma](/intune-classic/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)
