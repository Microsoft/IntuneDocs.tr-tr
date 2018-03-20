---
title: Microsoft Intune ile Mobile Threat Defense
titleSuffix: 
description: "Cihaz riskine dayalı şirket kaynaklarına erişimi korumak için Mobil Threat Defense iş ortağınız ile Intune Mobil Threat Defense (MTD) kullanın."
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 11/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2eaba4f04d6a1daedf40b7b37d2b44ed5aff4533
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="what-is-mobile-threat-defense-integration-with-intune"></a>Intune ile Mobile Threat Defense tümleştirmesi nedir?


Intune Mobile Threat Defense bağlayıcıları, uyumluluk ilkeleriniz ve koşullu erişim kurallarınız için bilgi kaynağı olarak seçtiğiniz Mobile Threat Defense satıcınızdan yararlanmasına olanak sağlar. Bu, özellikle ele geçirilen mobil cihazlardan olmak üzere, BT yöneticilerinin Exchange ve Sharepoint gibi şirket kaynaklarına bir koruma katmanı eklemesine olanak sağlar.

## <a name="what-problem-does-this-solve"></a>Hangi sorunu çözer?

Şirketlerin hassas verileri fiziksel, uygulama tabanlı ve ağ tabanlı tehditlerin yanı sıra işletim sistemi güvenlik açıklarını içeren yeni tehditlerden koruması gerekir.

Geçmişte, şirketler bilgisayarları saldırıdan koruma konusunda proaktif olarak çalışırken, mobil cihazlar izlenmiyor ve korumasız bırakılıyordu. Mobil platformlarda uygulama yalıtımı ve denetlenen tüketici uygulama mağazaları gibi yerleşik korumalar bulunmasına rağmen, bu platformlar hala karmaşık saldırılara karşı savunmasızdır. Bugün, iş için cihaz kullanan çalışan sayısı daha fazladır ve hassas bilgilere daha çok erişim ihtiyacı duyarlar. Cihazların giderek daha karmaşık hale gelen saldırılardan korunması gerekir.

## <a name="how-do-the-intune-mobile-threat-defense-connectors-work"></a>Intune Mobile Threat Defense bağlayıcıları nasıl çalışır?

Bağlayıcı, Intune ve seçtiğiniz Mobile Threat Defense satıcınız arasında bir iletişim kanalı oluşturarak şirket kaynaklarını korur. Intune Mobile Threat Defense iş ortakları, mobil cihazlar için raporlama veya uygulama amaçlarıyla Intune ile paylaşmak üzere tehdit bilgilerini etkin bir şekilde tarayan ve analiz eden sezgisel, dağıtımı kolay uygulamalar sunar. 

Örneğin bağlı bir Mobile Threat Defense uygulaması, Mobile Threat Defense satıcısına ağınızdaki bir telefonun Bağlantıyı İzinsiz İzleme saldırılarına karşı korunmasız bir ağa bağlandığını bildirirse, bu bilgi paylaşılır ve uygun bir risk düzeyine (düşük/orta/yüksek) sınıflandırılır ve ardından cihaz ele geçirildiği sırada seçtiğiniz belirli kaynaklara erişimin kaldırılıp kaldırılmayacağını belirlemek için Intune’da yapılandırdığınız risk düzeyi izinleriyle karşılaştırılabilir.

## <a name="what-data-does-intune-collect-for-mobile-threat-defense"></a>Intune, Mobile Threat Defense için hangi verileri topluyor?

Intune, kişisel ve kuruluşa ait cihazlardan uygulama envanter bilgilerini toplayarak Lookout for Work gibi Mobile Threat Defense (MTD) sağlayıcıları tarafından alınabilir hale getirir. iOS 11+ cihazlarının kullanıcılarından uygulama envanteri toplayabilirsiniz.

**Uygulama envanteri**  
Şirkete ait iOS 11+ ve kişisel cihazlar için envanterler MTD hizmet sağlayıcınıza gönderilir. Uygulama envanterindeki veriler şunları içerir:

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
- [Skycure](skycure-mobile-threat-defense-connector.md)
- [Check Point SandBlast Mobile](checkpoint-sandblast-mobile-mobile-threat-defense-connector.md)
- [Zimperium](zimperium-mobile-threat-defense-connector.md)
