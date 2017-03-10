---
title: Intune Mobile Threat Defense | Microsoft Docs
description: "Cihaz riskine dayalı olarak şirket kaynaklarına erişimi koruyun."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 08d87906-8158-4d5e-a49d-ad919efef3d1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b7ab3041a38bd394195a67690d245d1ad9fd0566
ms.openlocfilehash: fd54a1c94c9a4a279710d6be9f7cfe3b48468cb7
ms.lasthandoff: 03/03/2017


---

# <a name="intune-mobile-threat-defense-connectors"></a>Intune Mobile Threat Defense bağlayıcıları

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune Mobile Threat Defense bağlayıcıları, uyumluluk ilkeleriniz ve koşullu erişim kurallarınız için bilgi kaynağı olarak seçtiğiniz Mobile Threat Defense satıcınızdan yararlanmasına olanak sağlar. Bu, özellikle ele geçirilen mobil cihazlardan olmak üzere, BT Yöneticilerinin Exchange ve Sharepoint gibi şirket kaynaklarına bir koruma katmanı eklemesine olanak sağlar.

## <a name="what-problem-does-this-solve"></a>Hangi sorunu çözer?

Şirketlerin hassas verileri fiziksel, uygulama tabanlı ve ağ tabanlı tehditlerin yanı sıra işletim sistemi güvenlik açıklarını içeren yeni tehditlerden koruması gerekir.
Geçmişte, şirketler bilgisayarları saldırıdan koruma konusunda proaktif olarak çalışırken, mobil cihazlar izlenmiyor ve korumasız bırakılıyordu. Mobil platformlarda uygulama yalıtımı ve denetlenen tüketici uygulama mağazaları gibi yerleşik korumalar bulunmasına rağmen, bu platformlar hala karmaşık saldırılara karşı savunmasızdır. Bugün, iş için cihaz kullanan çalışan sayısı daha fazladır ve hassas bilgilere daha çok erişim ihtiyacı duyarlar. Cihazların giderek daha karmaşık hale gelen saldırılardan korunması gerekir.

## <a name="how-the-intune-mobile-threat-defense-connectors-work"></a>Intune Mobile Threat Defense bağlayıcıları nasıl çalışır?

Bağlayıcı, Intune ve seçtiğiniz Mobile Threat Defense satıcınız arasında bir iletişim kanalı oluşturarak şirket kaynaklarını korur. Intune Mobile Threat Defense iş ortakları, raporlama veya uygulama amaçlarıyla, Intune ile paylaşmak üzere tehdit bilgilerini etkin bir şekilde tarayan ve analiz eden mobil cihazlar için sezgisel, dağıtımı kolay uygulamalar sunar. Örneğin, bağlı bir Mobile Threat Defense uygulaması, Mobile Threat Defense satıcısına ağınızdaki bir telefonun Bağlantıyı İzinsiz İzleme saldırılarına karşı korunmasız bir ağa bağlandığını bildirirse, bu bilgi paylaşılır ve uygun bir risk düzeyinde (düşük/orta/yüksek) sınıflandırılır ve ardından cihaz ele geçirildiği sırada seçtiğiniz belirli kaynaklara erişimin kaldırılıp kaldırılmayacağını belirlemek için Intune’da yapılandırdığınız risk düzeyi izinleriyle karşılaştırılabilir.

## <a name="sample-scenarios"></a>Örnek senaryolar

Mobile Threat Defense çözümü, bir cihazı etkilenmiş olarak kabul ettiğinde:

![](http://i.imgur.com/kF8tI42.png)

Cihaz düzeltildiğinde erişim izni verilir:

![](http://i.imgur.com/zG4ZrzX.png)

## <a name="mobile-threat-defense-partners"></a>Mobile Threat Defense iş ortakları

Cihaz, ağ ve uygulama riskine dayalı olarak şirket kaynağına erişimi korumayı şununla öğrenin:

- [Lookout](https://docs.microsoft.com/intune/deploy-use/lookout-mobile-threat-defense-connector)
