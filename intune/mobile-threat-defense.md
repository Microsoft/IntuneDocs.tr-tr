---
title: Microsoft Intune ile Mobile Threat Defense | Microsoft Intune
description: Cihaz riskine dayalı şirket kaynaklarına erişimi korumak için Mobil Threat Defense iş ortağınız ile Intune Mobil Threat Defense (MTD) kullanın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/11/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 996b5ea3eb3c8d8f3a95bb94fb8a77584143ae8a
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57395371"
---
# <a name="what-is-mobile-threat-defense-integration-with-intune"></a>Intune ile Mobile Threat Defense tümleştirmesi nedir?
Intune uyumluluk ilkeleri ve koşullu erişim kurallarınız için bilgi kaynağı olarak bir Mobile Threat Defense satıcınızdan verilerini tümleştirebilirsiniz. Ele geçirilen mobil cihazlardan erişimi engelleyerek Exchange ve SharePoint gibi şirket kaynaklarını korumaya yardımcı olmak için bu bilgileri kullanabilirsiniz.  

## <a name="what-problem-does-this-solve"></a>Hangi sorunu çözer?
Mobile Threat Defense satıcınızdan bilgilerinden tümleştirme, şirket kaynaklarınıza mobil platformları etkileyen tehditlere karşı korumanıza yardımcı olabilir.  

Genellikle, şirketler bilgisayarları güvenlik açıklarına karşı koruma konusunda proaktif ve mobil cihazlar izlenmiyor ve korumasız genellikle giderken saldırı. Mobil platformlarda uygulama yalıtımı ve denetlenen tüketici uygulama mağazaları gibi yerleşik korumalar sahip olduğu durumlarda bu platformların karmaşık saldırılara karşı savunmasızdır. Daha fazla çalışan iş ve hassas bilgilere erişmek için cihazları kullanma gibi Mobile Threat Defense satıcınızdan bilgilerinden giderek daha karmaşık hale gelen saldırılardan cihazlar ve kaynaklarınızı korumanıza yardımcı olabilir.  

## <a name="how-do-the-intune-mobile-threat-defense-connectors-work"></a>Intune Mobile Threat Defense bağlayıcıları nasıl çalışır?

Intune Mobile Threat Defense Bağlayıcısı seçtiğiniz Mobile Threat Defense satıcınız ile Intune arasındaki iletişimin bir kanal oluşturmak için kullanır. Intune Mobile Threat Defense iş ortakları, sezgisel ve kolay mobil cihazlar için uygulamaları dağıtmanıza olanak sağlar. Bu uygulamalar, etkin bir şekilde tarayan ve Intune ile paylaşmak üzere tehdit bilgilerini analiz. Intune verileri raporlama veya uygulama amaçlarıyla kullanabilirsiniz.  

Örneğin: Bağlı bir Mobile Threat Defense uygulaması, Mobile Threat Defense satıcısına ağınızdaki bir telefon şu an için ortadaki adam saldırıları savunmasızdır bir ağa bağlı olduğundan emin bildirir. Bu bilgiler bir uygun bir risk düzeyine düşük, Orta veya yüksek kategorilere ayrılmıştır. Daha sonra bu risk düzeyi, Intune'da ayarladığınız risk düzeyi izinleri ile karşılaştırılır. Cihazın güvenliği aşıldığında sırada Bu karşılaştırmayı bağlı olarak, seçtiğiniz belirli kaynaklara erişimi iptal edilebilir.

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
