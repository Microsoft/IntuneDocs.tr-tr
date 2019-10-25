---
title: Microsoft Intune ile Mobile Threat Defense
titleSuffix: Microsoft Intune
description: Cihaz riskine dayalı şirket kaynaklarına erişimi korumak için Mobil Threat Defense iş ortağınız ile Intune Mobil Threat Defense (MTD) kullanın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4abc35b625b9aa072e38c02d2fc4160faa916fb3
ms.sourcegitcommit: 06a1fe83fd95c9773c011690e8520733e1c031e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2019
ms.locfileid: "72785760"
---
# <a name="what-is-mobile-threat-defense-integration-with-intune"></a>Intune ile Mobile Threat Defense tümleştirmesi nedir?
Intune, mobil tehdit savunma satıcısındaki verileri cihaz uyumluluk ilkeleri ve cihaz koşullu erişim kuralları için bir bilgi kaynağı olarak tümleştirebilir. Bu bilgileri, güvenliği aşılmış mobil cihazlardan erişimi engelleyerek Exchange ve SharePoint gibi kurumsal kaynakların korunmasına yardımcı olmak için kullanabilirsiniz.

Intune, Intune uygulama koruma ilkelerini kullanarak, kayıtlı olmayan cihazlar için bu verileri kaynak olarak kullanabilir. Bu nedenle, Yöneticiler bu bilgileri [Microsoft Intune korunan bir uygulamadaki](~/apps/apps-supported-intune-apps.md)kurumsal verileri korumak ve bir blok veya seçmeli silme vermek için kullanabilir.

## <a name="what-problem-does-this-solve"></a>Hangi sorunu çözer?
Mobil tehdit savunma satıcısından bilgi Tümleştirme, mobil platformları etkileyen tehditlere karşı şirket kaynaklarınızı korumanıza yardımcı olabilir.  

Genellikle, şirketler güvenlik açıklarından ve saldırılara karşı koruma sağlarken, mobil cihazlar genellikle izlenmeyen ve korumasız bir şekilde hareket ederken bu bilgisayarlara saldırır. Mobil platformların uygulama yalıtımı ve taklit edilmiş tüketici uygulama depoları gibi yerleşik koruması olduğu durumlarda, bu platformlar gelişmiş saldırılara karşı savunmasız kalır. Daha fazla çalışan cihazları iş için kullanırken ve hassas bilgilere erişebildiklerinden, mobil tehdit savunma satıcısından alınan bilgiler cihazları ve kaynaklarınızı giderek daha fazla karmaşık saldırılara karşı korumanıza yardımcı olabilir.  

## <a name="how-do-the-intune-mobile-threat-defense-connectors-work"></a>Intune Mobile Threat Defense bağlayıcıları nasıl çalışır?

Intune, Intune ile seçtiğiniz Mobile Threat Defense satıcınız arasında bir iletişim kanalı oluşturmak için bir mobil tehdit savunma Bağlayıcısı kullanır. Intune Mobile Threat Defense iş ortakları, mobil cihazlar için uygulama dağıtımı kolay ve kolay bir şekilde sunar. Bu uygulamalar, Intune ile paylaşmak üzere tehdit bilgilerini etkin bir şekilde tarar ve analiz eder. Intune, verileri raporlama veya zorlama amacıyla kullanabilir.  

Örneğin: bağlı bir mobil tehdit savunma uygulaması, ağınızdaki bir telefonun ortadaki saldırılara açık olan bir ağa bağlı olduğunu Mobile Threat Defense satıcısına bildirir. Bu bilgiler, düşük, orta veya yüksek uygun bir risk düzeyine göre kategorize edilir. Bu risk düzeyi daha sonra Intune 'da ayarladığınız risk düzeyi kesintileri ile karşılaştırılır. Bu karşılaştırmaya bağlı olarak, cihazın güvenliği tehlikeye atıldığında seçtiğiniz belirli kaynaklara erişim iptal edilebilir.

## <a name="what-data-does-intune-collect-for-mobile-threat-defense"></a>Intune, Mobile Threat Defense için hangi verileri topluyor?

Bu etkinleştirildiğinde Intune, kişisel ve şirkete ait cihazlardan uygulama envanter bilgilerini toplayarak Lookout for Work gibi Mobile Threat Defense (MTD) sağlayıcıları tarafından alınabilir hale getirir. iOS cihaz kullanıcılarından uygulama envanteri toplayabilirsiniz.

Bu hizmet isteğe bağlıdır, varsayılan olarak hiçbir uygulama envanteri bilgisi paylaşılmaz. Bir Intune Yöneticisi, herhangi bir uygulama envanteri bilgisinin paylaşılmadan önce Mobile Threat Defense bağlayıcı ayarlarındaki **iOS cihazları Için uygulama eşitlemesini** etkinleştirmelidir.

**Uygulama envanteri**  
iOS cihazlar için Uygulama Eşitleme’yi etkinleştirirseniz hem şirkete ait hem de kişisel iOS cihazlar için envanterler MTD hizmet sağlayıcınıza gönderilir. Uygulama envanterindeki veriler şunları içerir:

- Uygulama Kimliği
- Uygulama Sürümü
- Uygulama Kısa Sürümü
- Uygulama Adı
- Uygulama Paketi Boyutu
- Uygulama Dinamik Boyutu
- Uygulamanın doğrulanıp doğrulanmadığı
- Uygulamanın yönetilip yönetilmediği

## <a name="sample-scenarios-for-enrolled-devices-using-device-compliance-policies"></a>Cihaz uyumluluk ilkelerini kullanan kayıtlı cihazlar için örnek senaryolar

Mobile Threat Defense çözümü, bir cihazı etkilenmiş olarak kabul ettiğinde:

![Mobile Threat Defense’te etkilenmiş cihazı gösteren resim](./media/mobile-threat-defense/MTD-image-1.png)

Cihaz düzeltildiğinde erişim izni verilir:

![Mobile Threat Defense Erişimi verildi ekranını gösteren resim](./media/mobile-threat-defense/MTD-image-2.png)

## <a name="sample-scenarios-for-unenrolled-devices-using-intune-app-protection-policies"></a>Intune uygulama koruma ilkelerini kullanarak kayıtlı olmayan cihazların örnek senaryoları

Mobile Threat Defense çözümü, bir cihazı etkilenmiş olarak kabul ettiğinde:<br>
virüslü bir mobil tehdit savunması cihazını gösteren ![resim](./media/mobile-threat-defense/MTD-image-3.png)

Cihaz düzeltildiğinde erişim izni verilir:<br>
Mobil tehdit savunması erişimi verilen ![resim](./media/mobile-threat-defense/MTD-image-4.png)

> [!NOTE] 
> Intune ile birden fazla Mobil Tehdit Savunması (MTD) satıcısı kullanımı desteklenmez. Birden çok MTD bağlayıcısının etkin olması, tüm MTD uygulamalarının tehditlere karşı cihazlara yüklenmesini ve taranmasını zorlayacaktır.

## <a name="mobile-threat-defense-partners"></a>Mobile Threat Defense iş ortakları

Cihaz, ağ ve uygulama riskine dayalı olarak şirket kaynağına erişimi korumayı şununla öğrenin:

- [Lookout for Work](lookout-mobile-threat-defense-connector.md)
- [Symantec Endpoint Protection Mobile](skycure-mobile-threat-defense-connector.md)
- [Check Point SandBlast Mobile](checkpoint-sandblast-mobile-mobile-threat-defense-connector.md)
- [Zimperium](zimperium-mobile-threat-defense-connector.md)
- [Pradeo](pradeo-mobile-threat-defense-connector.md)
- [Better Mobile](better-mobile-threat-defense-connector.md)
- [Sophos Mobile](sophos-mtd-connector.md)
- [Wandera Mobile Threat Defense](wandera-mtd-connector.md)
