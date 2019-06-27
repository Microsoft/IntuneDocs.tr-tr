---
title: Intune ile mobil güvenliği Wandera ayarlama
titleSuffix: Intune on Azure
description: Şirket kaynaklarınıza mobil cihaz erişimini kontrol etmek Intune Wandera mobil güvenliği ayarlama yapma.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6219d4a176eebf81747461b3cc8b478e46e86898
ms.sourcegitcommit: 6bba9f2ef4d1ec699f5713a4da4f960e7317f1cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2019
ms.locfileid: "67407694"
---
# <a name="wandera-mobile-threat-defense-connector-with-intune"></a>Intune ile Wandera Mobile Threat Defense Bağlayıcısı  

Mobil cihaz Wandera tarafından yapılan risk değerlendirmesine dayalı koşullu erişimi kullanarak şirket kaynaklarına erişimi denetler. Wandera Intune ile tümleşen Mobile Threat Defense (MTD) çözümüdür.  Risk Wandera hizmeti tarafından cihazlardan toplanan telemetriye göre değerlendirilen dahil olmak üzere:
- İşletim sistemi güvenlik açıkları
- Yüklenen kötü amaçlı uygulamalar
- Kötü amaçlı ağ profilleri
- Cryptojacking

Yapılandırabileceğiniz *koşullu erişim* Wandera üzerinde ait temel ilkeleri risk değerlendirmesi, Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen. Risk değerlendirmesi ilke izin verebilir veya uyumlu olmayan cihazların algılanan tehditlere dayalı olarak şirket kaynaklarına erişmesini engelleyin.  


## <a name="how-do-intune-and-wandera-mobile-threat-defense-help-protect-your-company-resources"></a>Nasıl Intune ile Mobile Threat Defense Wandera şirket kaynaklarınızın korunmasına yardımcı olur?  

Mobil uygulama Wandera'nın sorunsuz bir şekilde Microsoft Intune kullanarak yükler. Bu uygulama, dosya sistemi, ağ yığını ve cihaz ve uygulama telemetrisini (kullanılabiliyorsa) yakalar. Bu bilgiler, mobil tehditlere karşı cihazın riskini değerlendirmek için Wandera bulut hizmetine eşitler. Bu risk düzeyi sınıflandırmalarını gereksinimlerinize RADAR Wandera konsolunda yapılandırılamaz.

Intune'daki uyumluluk ilkesi için MTD Wandera'nın risk değerlendirmesini temel alan bir kural içerir. Bu kural etkinleştirildiğinde Intune, cihazın etkinleştirdiğiniz ilke ile uyumluluğunu değerlendirir.

Uyumlu olmayan cihazlar için Office 365 gibi kaynaklara erişim engellenebilir. Engellenen cihazlardaki kullanıcılara sorunu çözümleyip tekrar erişim kazanmak için Wandera uygulamasından yol gösteren yönergeler alır.

## <a name="supported-platforms"></a>Desteklenen platformlar  

Aşağıdaki platformlar Intune'da kayıtlıysa Wandera desteklenir:

- Android 5.0 ve üzeri  
- iOS 10.2 ve üzeri  

Platform ve cihaz hakkında daha fazla bilgi için bkz: [Wandera Web sitesi](https://www.wandera.com/why-wandera/features/device-support/).

## <a name="prerequisites"></a>Önkoşullar  

- Microsoft Intune aboneliği  
- Azure Active Directory  
- Wandera Mobile Threat Defense (eski adıyla Wandera güvenli)  

Daha fazla bilgi için [Wandera mobil güvenliği](https://www.wandera.com/mobile-security/).
 
## <a name="sample-scenarios"></a>Örnek senaryolar

Wandera MTD Intune'u birlikte kullanırken oluşan genel senaryolar şunlardır.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Kötü amaçlı uygulamalardan kaynaklanan tehditlere dayalı olarak erişimi denetleme  

Cihazlarda kötü amaçlı yazılım gibi kötü amaçlı uygulamalar algılandığında, tehdit çözmeden ortak Araçlar cihazlardan engelleyebilirsiniz. Ortak blok şunlardır:  
- Şirket e-postasına bağlanma  
- OneDrive İş uygulaması ile şirket dosyalarını eşitleme  
- Şirket uygulamalarına erişme  

**Kötü amaçlı uygulamalar algılandığında engelle**:

![Kötü amaçlı uygulamalar algılandı kavramsal resmi](./media/wandera-mtd-connector/wandera-malicious-apps-blocked.png)  

**Düzeltme ile erişim**: 

![Kavramsal resmi düzeltme sonra erişim izni verildi](./media/wandera-mtd-connector/wandera-malicious-apps-unblocked.png)


### <a name="control-access-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak erişimi denetleme  

ADAM-de-adam saldırıları gibi ağınıza yönelik tehditleri algılayın ve cihaz riskine dayalı olarak Wi-Fi ağlarına erişimi koruyun.  

**Wi-Fi üzerinden ağ erişimini engelle**:  

![Wi-Fi üzerinden ağ erişimini engelleme](./media/wandera-mtd-connector/wandera-network-wifi-blocked.png)

**Düzeltme ile erişim**:  

![Düzeltme ile erişim izni verildi](./media/wandera-mtd-connector/wandera-network-wifi-unblocked.png)  

## <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak SharePoint Online’a erişimi denetleme

Bağlantıyı izinsiz izleme saldırıları gibi ağınıza yönelik tehditleri algılar ve cihaz riskine dayalı olarak kurumsal dosyaların eşitlenmesini engeller.

**Blok SharePoint Ağ tehditleri algılandığında çevrimiçi**:  

![Ağ tehditleri algılandığında SharePoint Online’ı engelleme](./media/wandera-mtd-connector/wandera-network-spo-blocked.png)  


**Düzeltme ile erişim**:  

![Erişim izni verildi SharePoint örneği için düzeltme](./media/wandera-mtd-connector/wandera-network-spo-unblocked.png)  

## <a name="next-steps"></a>Sonraki adımlar

- [Wandera Intune ile tümleştirme](Wandera-mtd-connector-integration.md)
- [Wandera uygulamalarını ayarlama](mtd-apps-ios-app-configuration-policy-add-assign.md)
- [Wandera cihaz uyumluluk ilkesi oluşturma](mtd-device-compliance-policy-create.md)
- [Wandera MTD bağlayıcısını etkinleştirme](mtd-connector-enable.md)