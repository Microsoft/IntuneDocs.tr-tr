---
title: Microsoft Intune ile Lookout MTD bağlayıcısı
titleSuffix: Microsoft Intune
description: Şirket kaynaklarınıza mobil cihaz erişimini kontrol etmek için Lookout Mobile Threat Defense’i (MTD) Intune ile tümleştirme hakkında bilgi edinin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/11/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3a730a5d-2a90-42b0-aa28-aadfc7a18788
ms.reviewer: davera
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a6dfce050726cfddadc493f73c91701021dc21ea
ms.sourcegitcommit: 7315fe72b7e55c5dcffc6d87f185f3c2cded9028
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2019
ms.locfileid: "67529804"
---
# <a name="lookout-mobile-endpoint-security-connector-with-intune"></a>Intune ile lookout mobil uç nokta güvenliği Bağlayıcısı

Microsoft Intune ile tümleşik bir Mobile Threat Defense çözümü olan Lookout tarafından gerçekleştirilen risk değerlendirmesine dayalı olarak mobil cihazlardan şirket kaynaklarına erişimi denetleyebilirsiniz. Risk, Lookout hizmeti tarafından cihazlardan toplanan ve aşağıdakileri içeren telemetriye göre değerlendirilir:
- İşletim sistemi güvenlik açıkları
- Yüklenen kötü amaçlı uygulamalar
- Kötü amaçlı ağ profilleri

Intune uyumluluk ilkeleri ile etkinleştirilen Lookout risk değerlendirmesine dayalı koşullu erişim ilkelerini yapılandırabilirsiniz. Ayarlar, algılanan tehditlere dayalı olarak uyumsuz cihazlara izin vermenize veya bunları engellemenize olanak tanır.

## <a name="how-do-intune-and-lookout-mobile-endpoint-security-help-protect-company-resources"></a>Intune ve Lookout mobil uç nokta güvenliği şirket kaynaklarını korumaya nasıl yardımcı?
Lookout’un mobil uygulaması **Lookout for Work**, mobil cihazlara yüklenir ve mobil cihazlarda çalışır. Bu uygulama varsa dosya sistemi, ağ yığını, cihaz ve uygulama telemetrisini yakalar ve mobil tehditlere karşı cihazın riskini değerlendirmek için bunları Lookout bulut hizmetine gönderir. Lookout konsolundaki tehditlere yönelik risk düzeyi sınıflandırmalarını gereksinimlerinize uyacak şekilde değiştirebilirsiniz.  

Intune’daki uyumluluk ilkesi, Lookout risk değerlendirmesine dayalı Lookout Mobile Threat Defense için bir kural içerir. Bu kural etkinleştirildiğinde Intune, cihazın etkinleştirdiğiniz ilke ile uyumluluğunu değerlendirir.

Cihaz uyumsuz bulunursa Exchange Online gibi kaynaklara erişim ve SharePoint Online engellenebilir. Engellenen cihazlardaki kullanıcılara, sorunu çözün ve yeniden erişim kazanmak için adımlar sağlanır. Yönergeler Lookout for Work uygulamasından gönderilir.

## <a name="supported-platforms"></a>Desteklenen platformlar  
Aşağıdaki platformlar Intune'da kayıtlıysa Lookout için desteklenir:
* **Android 4.1 ve üzeri**  
* **iOS 8 ve üzeri**  

Platform ve dil desteği hakkında ek bilgi için ziyaret [Lookout Web sitesi](https://personal.support.lookout.com/hc/articles/114094140253).  

## <a name="prerequisites"></a>Önkoşullar
* Lookout Mobil Uç Nokta Güvenliği kurumsal aboneliği  
* Microsoft Intune aboneliği
* Azure Active Directory Premium
* Enterprise Mobility ve Security (EMS) E3 veya E5, kullanıcılara atanmış lisansları.  

Daha fazla bilgi için bkz: [Lookout Mobil Uç Nokta Güvenliği](https://www.lookout.com/products/mobile-endpoint-security)

## <a name="sample-scenarios"></a>Örnek senaryolar

Mobil uç nokta güvenliği Intune'u birlikte kullanırken oluşan genel senaryolar şunlardır.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kötü amaçlı uygulamalardan kaynaklanan tehditlere dayalı olarak erişimi denetleme
Cihazlarda kötü amaçlı yazılım gibi kötü amaçlı uygulamalar algılandığında, tehdit çözülene kadar cihazların aşağıdaki işlemleri gerçekleştirmesini engelleyebilirsiniz:
* Şirket e-postasına bağlanma
* OneDrive İş uygulaması ile şirket dosyalarını eşitleme
* Şirket uygulamalarına erişme

**Kötü amaçlı yazılımlar algılandığında engelleme:**

![Kötü amaçlı uygulamalar nedeniyle erişimi engelleme İlkesi kavramsal resmi](./media/malicious-apps-blocked.png)

**Düzeltme ile erişim izni verildi:**

![Düzeltmeden sonra cihazlar için izin verilen erişim gösteren kavramsal resim](./media/malicious-apps-unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak erişimi denetleme
Bağlantıyı izinsiz izleme saldırıları gibi ağınıza yönelik tehditleri algılayın ve cihaz riskine dayalı olarak WiFi ağlarına erişimi koruyun.

**WiFi üzerinden ağ erişimini engelleme:**

![Ağ tehditlerine dayalı olarak WiFi erişimini engelleyen gösteren resim](./media/network-wifi-blocked.png)

**Düzeltme ile erişim izni verildi:**

![Kavramsal resim erişimine düzeltmeden sonra koşullu erişim](./media/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak SharePoint Online’a erişimi denetleme

Bağlantıyı izinsiz izleme saldırıları gibi ağınıza yönelik tehditleri algılar ve cihaz riskine dayalı olarak kurumsal dosyaların eşitlenmesini engeller.

**Ağ tehditleri algılandığında SharePoint Online’ı engelle:**

![SharePoint Online'a erişimi engelleyen kavramsal resmi](./media/network-spo-blocked.png)


**Düzeltme ile erişim izni verildi:**

![Ağ tehdidi düzeltildikten sonra erişim veren kavramsal resmi](./media/network-spo-unblocked.png)

## <a name="next-steps"></a>Sonraki adımlar
Bu çözümü uygulamak için yapılması gereken ana adımlar şunlardır:
1. [Lookout tümleştirmenizi ayarlama](lookout-mtd-connector-integration.md)
2. [Intune'da mobil uç nokta güvenliği etkinleştirme](mtd-connector-enable.md)
3. [Lookout for Work uygulamasını ekleme ve atama](mtd-apps-ios-app-configuration-policy-add-assign.md)
4. [Lookout cihaz uyumluluğu ilkesini yapılandırma](mtd-device-compliance-policy-create.md)
