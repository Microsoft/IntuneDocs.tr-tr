---
title: Microsoft Intune ile Mobile Threat Defense
titleSuffix: Microsoft Intune
description: Cihaz riskine dayalı şirket kaynaklarına erişimi korumak için Mobil Threat Defense iş ortağınız ile Intune Mobil Threat Defense (MTD) kullanın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 73c8167c91129d79a98674a92e7ccc5487a6b283
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67885075"
---
# <a name="what-is-mobile-threat-defense-integration-with-intune"></a>Intune ile Mobile Threat Defense tümleştirmesi nedir?
Intune, verileri bir mobil tehdit savunma satıcısından, uyumluluk ilkeleri ve koşullu erişim kuralları için bir bilgi kaynağı olarak tümleştirebilir. Bu bilgileri, güvenliği aşılmış mobil cihazlardan erişimi engelleyerek Exchange ve SharePoint gibi kurumsal kaynakların korunmasına yardımcı olmak için kullanabilirsiniz.  

## <a name="what-problem-does-this-solve"></a>Hangi sorunu çözer?
Mobil tehdit savunma satıcısından bilgi Tümleştirme, mobil platformları etkileyen tehditlere karşı şirket kaynaklarınızı korumanıza yardımcı olabilir.  

Genellikle, şirketler güvenlik açıklarından ve saldırılara karşı koruma sağlarken, mobil cihazlar genellikle izlenmeyen ve korumasız bir şekilde hareket ederken bu bilgisayarlara saldırır. Mobil platformların uygulama yalıtımı ve taklit edilmiş tüketici uygulama depoları gibi yerleşik koruması olduğu durumlarda, bu platformlar gelişmiş saldırılara karşı savunmasız kalır. Daha fazla çalışan cihazları iş için kullanırken ve hassas bilgilere erişebildiklerinden, mobil tehdit savunma satıcısından alınan bilgiler cihazları ve kaynaklarınızı giderek daha fazla karmaşık saldırılara karşı korumanıza yardımcı olabilir.  

## <a name="how-do-the-intune-mobile-threat-defense-connectors-work"></a>Intune Mobile Threat Defense bağlayıcıları nasıl çalışır?

Intune, Intune ile seçtiğiniz Mobile Threat Defense satıcınız arasında bir iletişim kanalı oluşturmak için bir mobil tehdit savunma Bağlayıcısı kullanır. Intune Mobile Threat Defense iş ortakları, mobil cihazlar için uygulama dağıtımı kolay ve kolay bir şekilde sunar. Bu uygulamalar, Intune ile paylaşmak üzere tehdit bilgilerini etkin bir şekilde tarar ve analiz eder. Intune, verileri raporlama veya zorlama amacıyla kullanabilir.  

Örneğin: Bağlı bir mobil tehdit savunma uygulaması, ağınızdaki bir telefonun ortadaki saldırılara açık olan bir ağa bağlı olduğunu Mobile Threat Defense satıcısına bildirir. Bu bilgiler, düşük, orta veya yüksek uygun bir risk düzeyine göre kategorize edilir. Bu risk düzeyi daha sonra Intune 'da ayarladığınız risk düzeyi kesintileri ile karşılaştırılır. Bu karşılaştırmaya bağlı olarak, cihazın güvenliği tehlikeye atıldığında seçtiğiniz belirli kaynaklara erişim iptal edilebilir.

## <a name="what-data-does-intune-collect-for-mobile-threat-defense"></a>Intune, Mobile Threat Defense için hangi verileri topluyor?

Bu etkinleştirildiğinde Intune, kişisel ve şirkete ait cihazlardan uygulama envanter bilgilerini toplayarak Lookout for Work gibi Mobile Threat Defense (MTD) sağlayıcıları tarafından alınabilir hale getirir. iOS cihaz kullanıcılarından uygulama envanteri toplayabilirsiniz.

Bu hizmet isteğe bağlıdır, varsayılan olarak hiçbir uygulama envanteri bilgisi paylaşılmaz. Uygulama envanter bilgileri paylaşılmadan önce bir Intune yöneticisinin hizmet ayarlarında iOS cihazlar için Uygulama Eşitleme’yi etkinleştirmesi gerekir.

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

## <a name="sample-scenarios"></a>Örnek senaryolar

Mobile Threat Defense çözümü, bir cihazı etkilenmiş olarak kabul ettiğinde:

![Mobile Threat Defense’te etkilenmiş cihazı gösteren resim](./media/MTD-image-1.png)

Cihaz düzeltildiğinde erişim izni verilir:

![Mobile Threat Defense Erişimi verildi ekranını gösteren resim](./media/MTD-image-2.png)

> [!NOTE] 
> Intune ile birden fazla Mobil Tehdit Savunması (MTD) satıcısı kullanımı desteklenmez. Birden çok MTD aracının etkin olması, tüm MTD uygulamalarını yüklenmeye ve tehditler için tüm cihazları taramaya zorlayacaktır.

## <a name="mobile-threat-defense-partners"></a>Mobile Threat Defense iş ortakları

Cihaz, ağ ve uygulama riskine dayalı olarak şirket kaynağına erişimi korumayı şununla öğrenin:

- [Lookout](lookout-mobile-threat-defense-connector.md)
- [Symantec Endpoint Protection Mobile](skycure-mobile-threat-defense-connector.md)
- [Check Point SandBlast Mobile](checkpoint-sandblast-mobile-mobile-threat-defense-connector.md)
- [Zimperium](zimperium-mobile-threat-defense-connector.md)
- [Pradeo](pradeo-mobile-threat-defense-connector.md)
- [Better Mobile](better-mobile-threat-defense-connector.md)
- [Sophos Mobile](sophos-mtd-connector.md)
- [Wandera Mobile Threat Defense](wandera-mtd-connector.md)
