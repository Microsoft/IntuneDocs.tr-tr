---
title: Microsoft Intune ile Lookout MTD bağlayıcısı
titleSuffix: Microsoft Intune
description: Şirket kaynaklarınıza mobil cihaz erişimini kontrol etmek için Lookout Mobile Threat Defense’i (MTD) Intune ile tümleştirme hakkında bilgi edinin.
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
ms.assetid: 3a730a5d-2a90-42b0-aa28-aadfc7a18788
ms.reviewer: davera
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 628aa93af912d6c50a6897dbf871702e46b4893e
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77782136"
---
# <a name="lookout-mobile-endpoint-security-connector-with-intune"></a>Intune ile mobil uç nokta güvenlik bağlayıcısını gevle

Microsoft Intune ile tümleşik bir Mobile Threat Defense çözümü olan Lookout tarafından gerçekleştirilen risk değerlendirmesine dayalı olarak mobil cihazlardan şirket kaynaklarına erişimi denetleyebilirsiniz. Risk, Lookout hizmeti tarafından cihazlardan toplanan ve aşağıdakileri içeren telemetriye göre değerlendirilir:
- İşletim sistemi güvenlik açıkları
- Yüklenen kötü amaçlı uygulamalar
- Kötü amaçlı ağ profilleri

Kayıtlı cihazlar için Intune uyumluluk ilkeleri aracılığıyla etkinleştirilen koşullu erişim ilkelerini, algılanan tehditlere dayalı olarak uyumlu olmayan cihazların şirket kaynaklarına erişmesine izin vermek veya erişimi engellemek için kullanabileceğiniz bir şekilde yapılandırabilirsiniz. Kayıtlı olmayan cihazlar için, algılanan tehditlere dayalı olarak bir blok veya seçmeli Temizleme zorlamak için uygulama koruma ilkelerini kullanabilirsiniz.

## <a name="how-do-intune-and-lookout-mobile-endpoint-security-help-protect-company-resources"></a>Mobil uç nokta güvenliğini Intune ve Gevþme etme şirket kaynaklarını korumaya nasıl yardımcı olur?
Lookout’un mobil uygulaması **Lookout for Work**, mobil cihazlara yüklenir ve mobil cihazlarda çalışır. Bu uygulama varsa dosya sistemi, ağ yığını, cihaz ve uygulama telemetrisini yakalar ve mobil tehditlere karşı cihazın riskini değerlendirmek için bunları Lookout bulut hizmetine gönderir. Lookout konsolundaki tehditlere yönelik risk düzeyi sınıflandırmalarını gereksinimlerinize uyacak şekilde değiştirebilirsiniz.  

Intune’daki uyumluluk ilkesi, Lookout risk değerlendirmesine dayalı Lookout Mobile Threat Defense için bir kural içerir. Bu kural etkinleştirildiğinde Intune, cihazın etkinleştirdiğiniz ilke ile uyumluluğunu değerlendirir.

Cihaz uyumsuz bulunursa Exchange Online ve SharePoint Online gibi kaynaklara erişim engellenebilir. Engellenen cihazlardaki kullanıcılar, sorunu gidermek ve erişimi yeniden kazanmak için gereken adımları alır. Yönergeler Lookout for Work uygulamasından gönderilir.

## <a name="supported-platforms"></a>Desteklenen platformlar  
Aşağıdaki platformlar Intune'da kayıtlıysa Lookout için desteklenir:
* **Android 4.1 ve üzeri**  
* **iOS 8 ve üzeri**  

Platform ve dil desteği hakkında daha fazla bilgi için, [GEVME Web sitesini](https://personal.support.lookout.com/hc/articles/114094140253)ziyaret edin.  

## <a name="prerequisites"></a>Önkoşullar
* Lookout Mobil Uç Nokta Güvenliği kurumsal aboneliği  
* Microsoft Intune aboneliği
* Azure Active Directory Premium
* Kullanıcılara atanmış lisanslarla kurumsal taşınabilirlik ve güvenlik (EMS) E3 veya E5.  

Daha fazla bilgi için bkz: [Lookout Mobil Uç Nokta Güvenliği](https://www.lookout.com/products/mobile-endpoint-security)

## <a name="sample-scenarios"></a>Örnek senaryolar

Intune ile mobil uç nokta güvenliği kullanılırken yaygın senaryolar aşağıda verilmiştir.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kötü amaçlı uygulamalardan kaynaklanan tehditlere dayalı olarak erişimi denetleme
Cihazlarda kötü amaçlı yazılım gibi kötü amaçlı uygulamalar algılandığında, tehdit çözülene kadar cihazların aşağıdaki işlemleri gerçekleştirmesini engelleyebilirsiniz:
* Şirket e-postasına bağlanma
* OneDrive İş uygulaması ile şirket dosyalarını eşitleme
* Şirket uygulamalarına erişme

**Kötü amaçlı yazılımlar algılandığında engelleme:**

![Kötü amaçlı uygulamalar nedeniyle ilkenin erişimini engelleyen kavramsal resim](./media/lookout-mobile-threat-defense-connector/malicious-apps-blocked.png)

**Düzeltme ile erişim izni verildi:**

![Düzeltmeden sonra cihazlara erişim izni gösteren kavramsal resim](./media/lookout-mobile-threat-defense-connector/malicious-apps-unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak erişimi denetleme
Bağlantıyı izinsiz izleme saldırıları gibi ağınıza yönelik tehditleri algılayın ve cihaz riskine dayalı olarak WiFi ağlarına erişimi koruyun.

**WiFi üzerinden ağ erişimini engelleme:**

![Ağ tehditlerine dayalı olarak WiFi erişiminin engellenmesini gösteren resim](./media/lookout-mobile-threat-defense-connector/network-wifi-blocked.png)

**Düzeltme ile erişim izni verildi:**

![Düzeltmeden sonra erişime izin veren Koşullu erişimin kavramsal resmi](./media/lookout-mobile-threat-defense-connector/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak SharePoint Online’a erişimi denetleme

Bağlantıyı izinsiz izleme saldırıları gibi ağınıza yönelik tehditleri algılar ve cihaz riskine dayalı olarak kurumsal dosyaların eşitlenmesini engeller.

**Ağ tehditleri algılandığında SharePoint Online’ı engelle:**

![SharePoint Online 'a erişimi engellemeye yönelik kavramsal resim](./media/lookout-mobile-threat-defense-connector/network-spo-blocked.png)


**Düzeltme ile erişim izni verildi:**

![Ağ tehdidi düzeltildikten sonra erişime izin verme hakkında kavramsal resim](./media/lookout-mobile-threat-defense-connector/network-spo-unblocked.png)

## <a name="next-steps"></a>Sonraki adımlar
Bu çözümü uygulamak için yapılması gereken ana adımlar şunlardır:
- [Lookout tümleştirmenizi ayarlama](lookout-mtd-connector-integration.md)
- [Intune 'da mobil uç nokta güvenliğini etkinleştirme](mtd-connector-enable.md)
- [Lookout for Work uygulamasını ekleme ve atama](mtd-apps-ios-app-configuration-policy-add-assign.md)
- [Lookout cihaz uyumluluğu ilkesini yapılandırma](mtd-device-compliance-policy-create.md)
- [MTD uygulama koruma ilkesi oluşturma](mtd-app-protection-policy.md)

