---
title: Intune ile Mobile Threat Defense
titleSuffix: Intune Azure preview
description: "Cihaz riskine dayalı olarak şirket kaynaklarına erişimi koruma"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fe2387f57d73b86b647e997eac4c411fbaf2bfbc
ms.sourcegitcommit: bee30f4c9e04129d70305fcafc4152c6e062a8b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2017
---
# <a name="mobile-threat-defense-integration-with-intune"></a>Intune ile Mobile Threat Defense tümleştirmesi


Intune Mobile Threat Defense bağlayıcıları, uyumluluk ilkeleriniz ve koşullu erişim kurallarınız için bilgi kaynağı olarak seçtiğiniz Mobile Threat Defense satıcınızdan yararlanmasına olanak sağlar. Bu, özellikle ele geçirilen mobil cihazlardan olmak üzere, BT Yöneticilerinin Exchange ve Sharepoint gibi şirket kaynaklarına bir koruma katmanı eklemesine olanak sağlar.

## <a name="what-problem-does-this-solve"></a>Hangi sorunu çözer?

Şirketlerin hassas verileri fiziksel, uygulama tabanlı ve ağ tabanlı tehditlerin yanı sıra işletim sistemi güvenlik açıklarını içeren yeni tehditlerden koruması gerekir.
Geçmişte, şirketler bilgisayarları saldırıdan koruma konusunda proaktif olarak çalışırken, mobil cihazlar izlenmiyor ve korumasız bırakılıyordu. Mobil platformlarda uygulama yalıtımı ve denetlenen tüketici uygulama mağazaları gibi yerleşik korumalar bulunmasına rağmen, bu platformlar hala karmaşık saldırılara karşı savunmasızdır. Bugün, iş için cihaz kullanan çalışan sayısı daha fazladır ve hassas bilgilere daha çok erişim ihtiyacı duyarlar. Cihazların giderek daha karmaşık hale gelen saldırılardan korunması gerekir.

## <a name="how-the-intune-mobile-threat-defense-connectors-work"></a>Intune Mobile Threat Defense bağlayıcıları nasıl çalışır?

Bağlayıcı, Intune ve seçtiğiniz Mobile Threat Defense satıcınız arasında bir iletişim kanalı oluşturarak şirket kaynaklarını korur. Intune Mobile Threat Defense iş ortakları, raporlama veya uygulama amaçlarıyla, Intune ile paylaşmak üzere tehdit bilgilerini etkin bir şekilde tarayan ve analiz eden mobil cihazlar için sezgisel, dağıtımı kolay uygulamalar sunar. Örneğin, bağlı bir Mobile Threat Defense uygulaması, Mobile Threat Defense satıcısına ağınızdaki bir telefonun Bağlantıyı İzinsiz İzleme saldırılarına karşı korunmasız bir ağa bağlandığını bildirirse, bu bilgi paylaşılır ve uygun bir risk düzeyinde (düşük/orta/yüksek) sınıflandırılır ve ardından cihaz ele geçirildiği sırada seçtiğiniz belirli kaynaklara erişimin kaldırılıp kaldırılmayacağını belirlemek için Intune’da yapılandırdığınız risk düzeyi izinleriyle karşılaştırılabilir.

## <a name="sample-scenarios"></a>Örnek senaryolar

Mobile Threat Defense çözümü, bir cihazı etkilenmiş olarak kabul ettiğinde:

![Mobile Threat Defense’te etkilenmiş cihaz](./media/MTD-image-1.png)

Cihaz düzeltildiğinde erişim izni verilir:

![Mobile Threat Defense Erişim verildi](./media/MTD-image-2.png)

## <a name="mobile-threat-defense-partners"></a>Mobile Threat Defense iş ortakları

Cihaz, ağ ve uygulama riskine dayalı olarak şirket kaynağına erişimi korumayı şununla öğrenin:

- [Lookout](lookout-mobile-threat-defense-connector.md)
- [Skycure](skycure-mobile-threat-defense-connector.md)
- [Check Point SandBlast Mobile](checkpoint-sandblast-mobile-mobile-threat-defense-connector.md)