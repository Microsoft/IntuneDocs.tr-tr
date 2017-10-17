---
title: "Lookout mobile threat defense bağlayıcısı"
description: "Lookout Mobile Threat Defense bağlayıcısı ve Intune ile şirket kaynaklarına erişimi cihaz, ağ ve uygulama riskine dayalı olarak koruyun."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d1e04113d2f8707be0d06cb0783e6113914b856a
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/10/2017
---
# <a name="lookout-mobile-threat-defense-connector-with-intune"></a>Intune ile Lookout Mobile Threat Defense bağlayıcısı

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune ile tümleşik bir Mobile Threat Defense çözümü olan Lookout tarafından gerçekleştirilen risk değerlendirmesine dayalı olarak mobil cihazlardan şirket kaynaklarına erişimi denetleyebilirsiniz. Risk, Lookout hizmeti tarafından cihazlardan toplanan ve aşağıdakileri içeren telemetriye göre değerlendirilir:
- İşletim sistemi güvenlik açıkları
- Yüklenen kötü amaçlı uygulamalar
- Kötü amaçlı ağ profilleri

Intune uyumluluk ilkeleri ile etkinleştirilen Lookout risk değerlendirmesine dayalı olarak koşullu erişim ilkelerini yapılandırabilirsiniz. Ayarlar, algılanan tehditlere dayalı olarak uyumsuz cihazlara izin vermenize veya bunları engellemenize olanak tanır.

## <a name="how-do-intune-and-lookout-mobile-threat-defense-help-protect-company-resources"></a>Intune ve Lookout Mobile Threat Defense, şirket kaynaklarını korumaya nasıl yardımcı olur?
Lookout’un mobil uygulaması **Lookout for Work**, mobil cihazlara yüklenir ve mobil cihazlarda çalışır. Bu uygulama varsa dosya sistemi, ağ yığını, cihaz ve uygulama telemetrisini yakalar ve mobil tehditlere karşı cihazın riskini değerlendirmek için bunları Lookout bulut hizmetine gönderir. Lookout konsolundaki tehditlere yönelik risk düzeyi sınıflandırmalarını gereksinimlerinize uyacak şekilde değiştirebilirsiniz.  

Intune’daki uyumluluk ilkesi, Lookout risk değerlendirmesine dayalı Lookout Mobile Threat Defense için bir kural içerir. Bu kural etkinleştirildiğinde Intune, cihazın etkinleştirdiğiniz ilke ile uyumluluğunu değerlendirir.

Cihaz uyumsuz bulunursa Exchange Online ve SharePoint Online gibi kaynaklara erişim engellenebilir. Engellenen cihazlardaki kullanıcılara, sorunu gidermek ve yeniden erişim sağlamak için adımlar sağlanır. Yönergeler Lookout for Work uygulamasından gönderilir.

## <a name="supported-platforms"></a>Desteklenen platformlar:
Aşağıdaki platformlar Intune'da kayıtlıysa Lookout için desteklenir:
* **Android 4.1 ve üzeri**
* **iOS 8 ve üzeri** Platform ve dil desteği hakkında ek bilgiler için bkz. [Lookout web sitesi](https://personal.support.lookout.com/hc/articles/114094140253).

## <a name="prerequisites"></a>Önkoşullar:
* Microsoft Intune aboneliği
* Azure Active Directory
* Lookout Mobil Uç Nokta Güvenliği kurumsal aboneliği  

Daha fazla bilgi için bkz: [Lookout Mobil Uç Nokta Güvenliği](https://www.lookout.com/products/mobile-endpoint-security)

## <a name="sample-scenarios"></a>Örnek senaryolar
Sık karşılaşılan bazı senaryolar aşağıda verilmiştir:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kötü amaçlı uygulamalardan kaynaklanan tehditlere dayalı olarak erişimi denetleme
Cihazlarda kötü amaçlı yazılım gibi kötü amaçlı uygulamalar algılandığında, tehdit çözülene kadar cihazların aşağıdaki işlemleri gerçekleştirmesini engelleyebilirsiniz:
* Şirket e-postasına bağlanma
* OneDrive İş uygulaması ile şirket dosyalarını eşitleme
* Şirket uygulamalarına erişme

**Kötü amaçlı uygulamalar algılandığında engelle:**
![cihazdaki kötü amaçlı uygulamalar nedeniyle cihazın uyumlu olmadığı belirlendiğinde erişimi engelleyen koşullu erişim ilkesini gösteren diyagram](../media/mtp/malicious-apps-blocked.png)

**Düzeltme ile erişim izni verildi:**

![Düzeltme sonrası cihazın uyumlu olduğu belirlenince erişim izni veren koşullu erişim ilkesini gösteren diyagram](../media/mtp/malicious-apps-unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak erişimi denetleme
Bağlantıyı izinsiz izleme saldırıları gibi ağınıza yönelik tehditleri algılayın ve cihaz riskine dayalı olarak WiFi ağlarına erişimi koruyun.

**WiFi üzerinden ağ erişimini engelle:**
![ağ tehditlerine dayalı olarak WiFi erişimini engelleyen koşullu erişimi gösteren diyagram](../media/mtp/network-wifi-blocked.png)

**Düzeltme ile erişim izni verildi:**

![Tehdidin düzeltilmesinin ardından erişim izni veren koşullu erişimi gösteren diyagram](../media/mtp/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak SharePoint Online’a erişimi denetleme

Bağlantıyı izinsiz izleme saldırıları gibi ağınıza yönelik tehditleri algılar ve cihaz riskine dayalı olarak kurumsal dosyaların eşitlenmesini engeller.

**Ağ tehditleri algılandığında SharePoint Online’ı engelle:**

![Tehdit algılamasına dayalı olarak SharePoint Online’a cihaz erişimini engelleyen koşullu erişimi gösteren diyagram](../media/mtp/network-spo-blocked.png)


**Düzeltme ile erişim izni verildi:**

![Ağ tehdidi düzeltildikten sonra erişim izni veren koşullu erişimi gösteren diyagram](../media/mtp/network-spo-unblocked.png)

## <a name="next-steps"></a>Sonraki adımlar
Bu çözümü uygulamak için yapılması gereken ana adımlar şunlardır:
1.  [Lookout aboneliğinizi ayarlama](setup-your-lookout-mtd-subscription.md)
2.  [Intune’da Lookout Mobile Threat Defense’i etkinleştirme](enable-lookout-mtd-connection.md)
3.  [Lookout Mobile Threat Defense uygulamasını yapılandırma ve dağıtma](configure-deploy-lookout-for-work-app.md)
4.  [Lookout cihaz uyumluluğu ilkesini yapılandırma](create-lookout-device-compliance-policy.md)
5.  [Lookout Mobile Threat Defense tümleştirme sorunlarını giderme](/intune-classic/troubleshoot/device-threat-protection-troubleshooting)
