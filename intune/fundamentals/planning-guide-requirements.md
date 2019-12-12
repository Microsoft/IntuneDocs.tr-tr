---
title: Kullanım örneği senaryosu gereksinimlerini belirleme
titleSuffix: Microsoft Intune
description: Bu makale bir Microsoft Intune yalnızca bulut uygulaması için Intune kullanım örneğini ve alt kullanım örneği senaryosu gereksinimlerini belirlemenize yardımcı olur.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: fd8cb5f7-19f0-4d80-8825-2bafa49624af
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7c72cf963822284702f6b924ca506f8ec1157e91
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72505131"
---
# <a name="determine-use-case-scenario-requirements"></a>Kullanım örneği senaryosu gereksinimlerini belirleme

Bu bölümde, her kullanım örneği senaryosu içindeki tüm kuruluş grupları için gereksinimleri belirlersiniz. Bu süreç mimari ve tasarım, ekleme ve dağıtım gibi diğer Intune dağıtım planlama alanlarına hazırlanmanıza yardımcı olur. Intune dağıtım projenizle ilgili olası boşlukları ve zorlukları da tanımlamanıza yardımcı olacaktır.

Kullanım örneği ve alt kullanım örneği senaryolarınızın her biri ve bunlarla ilişkili kuruluş grupları ve mobil cihaz platformları için farklı gereksinimler kümesine sahip olabilirsiniz. Örneğin, kurumsal kullanım örneği senaryosu gereksinimleriniz, cihazların Intune’a 6 karakterli bir PIN veya devre dışı bırakılmış bulut yedeklemesi gibi daha kısıtlayıcı bir cihaz ayarları kümesiyle kaydedilmesini gerektirebilir. "Kendi cihazını getir" (KCG) kullanım örneği senaryosu daha az kısıtlayıcı olabilir ve 4 karakterli bir PIN ve bulut yedeklemesine izin verir.

Ayrıca, kurumsal kullanım örneği senaryosu için farklı gereksinimler kümesine (Örneğin PIN ayarları, Wi-Fi veya VPN profili, dağıtılan uygulamalar) sahip kuruluş gruplarınız olabilir. Gereksinimleriniz mobil cihaz platformunun yetenekleri (örneğin parmak izi okuyucu, e-posta profili) tarafından da belirlenmiş olabilir.

Her bir kullanım örneği ve alt kullanım örneği senaryosu, kuruluş grubu ve mobil cihaz platformu için farklı gereksinimler kümesini gösteren kuruluş kullanım örneği gereksinimlerine ilişkin birkaç örneği aşağıda bulabilirsiniz. Kuruluşunuzun kullanım örneği gereksinimlerini girmek için aşağıdaki tabloyu da kullanabilirsiniz:

| **Kullanım örnekleri** | **Alt kullanım örnekleri** | **GRUPLAR** | **Cihaz platformları** | **Requirements** |
|:---:|:---:|:---:|:---:|:---:|
| Kurumsal | Bilgi çalışanı | İK, Finans | iOS | Güvenli e-posta, cihaz ayarları, profiller, uygulamalar |                                                          
| Kurumsal | Yöneticiler | İK, Finans | iOS | Güvenli e-posta, cihaz ayarları, profiller, uygulamalar |                                                         
| Kurumsal | Bilgi noktası | Perakende | Android | Cihaz ayarları, profiller, uygulamalar |
| BYOD | Bilgi çalışanı | Pazarlama, Satış | iOS | Güvenli e-posta, cihaz ayarları, profiller, uygulamalar |                                                         
| BYOD | Yöneticiler | Pazarlama, Satış | iOS | Güvenli e-posta, cihaz ayarları, profiller, uygulamalar |

Kuruluşunuzun kullanım örneği ve alt kullanım örneği gereksinimlerini girmek için [yukarıdaki tablonun bir şablonunu indirebilirsiniz](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).


## <a name="examples-of-requirements"></a>Gereksinim örnekleri

"Gereksinimler" sütununda kullanılabilecek birkaç örnek daha verelim:

- **Güvenli e-posta**
  - Exchange Online/şirket içi Exchange için koşullu erişim
  - Outlook uygulaması koruma ilkeleri

- **Cihaz ayarları**
  - Dört, altı karakterli PIN ayarı
  - Bulut yedeklemeyi kısıtla

- **Profiller**
  - Wi-Fi
  - VPN
  - e-posta (Windows 10 mobile)

- **Uygulamalar**
  - Uygulama koruma ilkeleriyle Office 365
  - Uygulama koruma ilkeleri ile iş kolu (LOB)

## <a name="next-steps"></a>Sonraki adımlar

Sonraki bölümde [bir Intune dağıtımı planı geliştirme](planning-guide-rollout-plan.md) hakkında yönergeler sağlanır.
