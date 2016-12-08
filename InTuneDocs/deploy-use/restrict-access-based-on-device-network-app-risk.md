---
title: "Cihaz tehdit koruması kullanarak erişimi kısıtlama | Microsoft Intune"
description: "Şirket kaynaklarına erişimi cihaz, ağ ve uygulama riskine dayalı olarak kısıtlayın."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d4cd3d28a9e4c80fb6a2e17856f6dc9230429e70
ms.openlocfilehash: cbd223560810ee1b97966b8bf8da7206cc2a7955


---

# <a name="restrict-access-to-company-resource-based-on-device-network-and-application-risk"></a>Şirket kaynağına erişimi cihaz, ağ ve uygulama riskine dayalı olarak kısıtlama
Microsoft Intune ile tümleşik bir cihaz tehdit koruması çözümü olan Lookout tarafından gerçekleştirilen risk değerlendirmesine dayalı olarak mobil cihazlardan şirket kaynaklarına erişimi denetleyebilirsiniz. Risk, Lookout hizmetinin cihazlardan işletim sistemi (OS) güvenlik açıkları, yüklü kötü amaçlı uygulamalar ve kötü amaçlı ağ profilleri için topladığı telemetriye dayalıdır. Lookout tarafından rapor edilen, Intune uyumluluk ilkeleri ile etkinleştirilen risk değerlendirmesine dayalı olarak bundan sonra Intune’da koşullu erişim ilkeleri yapılandırabilir ve bu cihazlarda algılanan tehditler nedeniyle uyumlu olmadığı belirlenen cihazlara erişim izni verebilir veya erişimi engelleyebilirsiniz.  

## <a name="what-problem-does-this-solve"></a>Hangi sorunu çözer?
Şirketler ve kuruluşların hassas verileri fiziksel, uygulama tabanlı ve ağ tabanlı tehditlerin yanı sıra işletim sistemi güvenlik açıklarını içeren yeni tehditlerden koruması gerekir.

Tarihsel olarak, şirketler ve kuruluşlar bilgisayarları kötü niyetli saldırılara karşı koruma konusunda etkin bir pozisyonda yer almıştır. Mobil, genellikle korumasız ilerleyen yeni ortaya çıkmış bir alandır. Mobil platformlarda uygulama yalıtımı ve denetlenen tüketici uygulama mağazaları gibi teknikler kullanılarak yerleşik işletim sistemi koruması sağlanmasına rağmen, bu platformların karmaşık saldırılara karşı güvenlik açıkları vardır. Mobil cihazlar çalışanlar tarafından iş yapmak ve hassas ve değerli verilere erişmek için giderek daha fazla kullanıldığından, bu cihazların çeşitli karmaşık saldırılardan korunması gerekmektedir.

Intune, Lookout gibi cihaz tehdit koruması çözümlerinin sağladığı risk değerlendirmelerine dayalı olarak şirket kaynaklarına ve verilerine erişimi denetleme olanağı sunar.

## <a name="how-do-intune-and-lookout-device-threat-protection-help-protect-company-resources"></a>Intune ve Lookout cihaz tehdit koruması, şirket kaynaklarını korumaya nasıl yardımcı olur?
Lookout’un mobil uygulaması (Lookout for work) mobil cihazlarda çalışarak dosya sistemini, ağ yığınını, cihaz ve uygulama telemetrisini (kullanılabiliyorsa) yakalar ve bunu Lookout cihaz tehdit koruması bulut hizmetine göndererek mobil tehditler için birleşik bir cihaz riski hesaplar. Lookout konsolundaki tehditlere yönelik risk düzeyi sınıflandırmasını da gereksinimlerinize uyacak şekilde değiştirebilirsiniz.  

Intune’daki uyumluluk ilkesi artık Lookout cihaz tehdit risk değerlendirmesine dayalı Lookout mobil tehdit koruması için yeni bir kural içermektedir. Bu kural etkinleştirildiğinde, Microsoft Intune cihazın etkinleştirdiğiniz ilke ile uyumluluğunu değerlendirir.

Cihazın uyumluluk ilkesiyle uyumsuz olduğu belirlenirse, koşullu erişim ilkeleri kullanılarak Exchange Online ve SharePoint Online gibi kaynaklara erişim engellenebilir. Erişim engellendiğinde, son kullanıcılara sorunu gidermek ve şirket kaynaklarına yeniden erişim sağlamak için bir kılavuz sağlanır. Bu kılavuz Lookout for Work uygulaması aracılığıyla başlatılır.
## <a name="supported-platforms"></a>Desteklenen platformlar:
* **Android 4.1 ve üzeri** ve Microsoft Intune'a kayıtlı.
* **iOS 8 ve üzeri** ve Microsoft Intune'a kayıtlı.
Lookout’un desteklediği platformlar ve diller hakkında bilgi için bu [makaleye](https://personal.support.lookout.com/hc/en-us/articles/114094140253) göz atın.

## <a name="prerequisites"></a>Önkoşullar:
* Microsoft Intune ve Azure Active Directory aboneliği.
* Lookout Mobil Uç Nokta Güvenliği için kurumsal abonelik.  Daha fazla bilgi için bkz: [Lookout Mobil Uç Nokta Güvenliği](https://www.lookout.com/products/mobile-endpoint-security)

## <a name="example-scenarios"></a>Örnek senaryolar
Sık karşılaşılan bazı senaryolar aşağıda verilmiştir:
### <a name="control-access-based-on-threat-from-malicious-apps"></a>Kötü amaçlı uygulamalardan kaynaklanan tehdide dayalı olarak erişimi denetleme:
Kötü amaçlı yazılım gibi kötü amaçlı uygulamalar cihazda algılandığında, bu cihazların şu işlemleri yapmasını engelleyebilirsiniz:
* Tehdit çözümlenmeden önce şirket e-postasına bağlanma.
* OneDrive İş uygulamasını kullanarak şirket dosyalarını eşitleme.
* İş açısından kritik uygulamalara erişme.

**Kötü amaçlı uygulamalar algılandığında erişim engellenir:**
![cihazdaki kötü amaçlı uygulamalar nedeniyle cihazın uyumlu olmadığı belirlendiğinde erişimi engelleyen koşullu erişim ilkesini gösteren diyagram](../media/mtp/malicious-apps-blocked.png)

**Tehdit düzeltildiğinde, cihazın engellenmesi kaldırılır ve şirket kaynaklarına erişebilir:**

![Düzeltme sonrası cihazın uyumlu olduğu belirlenince erişim izni veren koşullu erişim ilkesini gösteren diyagram](../media/mtp/malicious-apps-unblocked.png)
### <a name="control-access-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak erişimi denetleme:
Bağlantıyı izinsiz izleme saldırıları gibi ağınıza yönelik tehditleri algılar ve cihaz riskine dayalı olarak WiFi ağlarına erişimi kısıtlar.

**WiFi üzerinden ağ erişimi engellendi:**
![ağ tehditlerine dayalı olarak WiFi erişimini engelleyen koşullu erişimi gösteren diyagram](../media/mtp/network-wifi-blocked.png)

**Düzeltme ile erişim izni verildi:**

![Tehdidin düzeltilmesinin ardından erişim izni veren koşullu erişimi gösteren diyagram](../media/mtp/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Ağa yönelik tehdide dayalı olarak SharePoint Online’a erişimi denetleme:

Bağlantıyı izinsiz izleme saldırıları gibi ağınıza yönelik tehditleri algılar ve cihaz riskine dayalı olarak kurumsal dosyaların eşitlenmesini engeller.

**Cihazda algılanan ağ tehdidine dayalı olarak SharePoint Online erişimi engellendi:**

![Tehdit algılamasına dayalı olarak SharePoint Online’a cihaz erişimini engelleyen koşullu erişimi gösteren diyagram](../media/mtp/network-spo-blocked.png)


**Düzeltme ile erişim izni verildi:**

![Ağ tehdidi düzeltildikten sonra erişim izni veren koşullu erişimi gösteren diyagram](../media/mtp/network-spo-unblocked.png)

## <a name="next-steps"></a>Sonraki adımlar
Bu çözümü uygulamak için yapılması gereken ana adımlar şunlardır:
1.  [Lookout mobil tehdit koruması aboneliğinizi ayarlama](set-up-your-subscription-with-lookout-mtp.md)
2.  [Intune’da Lookout MTP bağlantısını etkinleştirme](enable-lookout-mtp-connection-in-intune.md)
3.  [Lookout for Work uygulamasını yapılandırma ve dağıtma](configure-and-deploy-lookout-for-work-apps.md)
4.  [Uyumluluk ilkesini yapılandırma](enable-device-threat-protection-rule-in-compliance-policy.md)
5.  [Lookout Tümleştirmesi sorunlarını giderme](http://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration)



<!--HONumber=Nov16_HO1-->


