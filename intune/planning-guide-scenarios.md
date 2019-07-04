---
title: Kullanım örneği senaryolarını tanımlama
titleSuffix: Microsoft Intune
description: Bu makale, bir Microsoft Intune salt bulut uygulaması için Intune kullanım örneği ve alt kullanım örneği senaryolarını belirlemenize yardımcı olur.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4b3c9af9-78da-44d2-8bd2-3f0f8885952d
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 28e48d64ba220f75f412ef117a08b07dfd477d06
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2019
ms.locfileid: "67549280"
---
# <a name="identify-mobile-device-management-use-case-scenarios"></a>Mobil cihaz yönetimi kullanım örneği senaryolarını belirleme

Kullanım örneği senaryolarınızı tanımlamak, başarılı bir Intune dağıtımı planlama sürecinin önemli bir parçasıdır. Kullanım örneği senaryoları, kullanıcılarınızı kullanıcı türüne veya role ve cihazın (şirket veya kişisel gibi) kime ait olduğun göre yönetilebilir gruplara ayırmanıza yardımcı oldukları için yararlıdır.

Kuruluşunuzun Intune kullanım örneği senaryolarının yanı sıra kuruluş gruplarını ve her kullanım örneği ile ilişkili mobil cihaz platformlarını tanımlamanıza yardımcı olmak için birkaç örnekten bahsedelim.

## <a name="device-ownership"></a>Cihaz sahipliği
Dağıtımınız için ana kullanım örneği senaryolarını tanımlamanıza yardımcı olmak üzere kuruluşunuzun Intune dağıtım hedeflerine ve amaçlarına başvurarak başlayabilirsiniz. Intune dağıtım planınız kapsamında, aşağıdaki soruları yanıtlayın:

- Şirkete ait cihazları desteklemeyi planlıyor musunuz?

- Kişisel cihazları (KCG) desteklemeyi planlıyor musunuz?

Bunlar ya bir/ya ötekisi tarzı seçenekler değildir. Kuruluş hedeflerinize ulaşmak için her iki cihaz sahiplik türünü de desteklemeniz gerektiği ortaya çıkabilir. Alt kullanım örnekleri, değişik cihaz yönetim ilkelerini nerelerde uygulayacağınızı netleştirmeye yardımcı olur.

### <a name="user-type-or-device-role"></a>Kullanıcı türü veya cihaz rolü

Her kullanım örneği senaryosunun alt kullanım örnekleri de içerip içermediğini belirleyin. Örneğin, kuruluşunuz, aşağıdaki kullanıcı türüne veya cihaz rolüne bağlı olarak ek alt kullanım örnekleri içeren bir kurumsal kullanım örneği senaryosunu desteklemek için gerekenleri belirlemiş olabilir:

- Bilgi çalışanı

- Yönetici

- Bilgi noktası

Kullanım örneği ve alt kullanım örneği senaryolarına birkaç örnek aşağıda verilmiştir:

| **Kullanım örnekleri** | **Alt kullanım örnekleri** |
|:---:|:---:|
| Kurumsal | Bilgi çalışanı |              
| Kurumsal | Yöneticiler |           
| Kurumsal | Bilgi noktası |
| KCG | Bilgi çalışanı |           
| KCG | Yöneticiler |

Kuruluşunuzun kullanım örneği ve alt kullanım örneği senaryolarını girmek için [yukarıdaki tablonun bir şablonunu indirebilirsiniz](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0).

## <a name="organizational-groups-for-your-scenarios"></a>Senaryolarınız için kuruluş grupları

Şimdi, her bir kullanım örneği ve alt kullanım örneği senaryosu ile ilişkili kuruluş gruplarını tanımlamanız gerekir. Örneğin:

| **Kullanım örnekleri** | **Alt kullanım örnekleri** | **Kuruluş grupları** |
|:---:|:---:|:---:|
| Kurumsal | Bilgi çalışanı | İK, Finans |               
| Kurumsal | Yönetici | İK, Finans |            
| Kurumsal | Bilgi noktası | Perakende |
| KCG | Bilgi çalışanı | Pazarlama, Satış |            
| KCG | Yönetici | Pazarlama, Satış |


## <a name="mobile-device-platforms-for-your-scenarios"></a>Senaryolarınız için mobil cihaz platformları

Sonraki adım, her bir kullanım örneği senaryosuyla ilişkili mobil cihaz platformlarını belirlemektir. Bunlar birden fazla olabilir.

Örneğin, kurumsal kullanım örneği senaryonuz iOS ve Android Samsung Knox cihaz platformlarını destekleyebilir. KCG ilkeniz Android (Samsung Knox olmayan) ve Windows 10 Mobile gibi ek mobil cihaz platformları için destek içerebilir. Önceki örnekleri temel alarak mobil her kullanım örneği senaryosu ile cihaz platformları ilişkilendirdik.

| **Kullanım örnekleri** | **Alt kullanım örnekleri** | **Gruplar** | **Cihaz platformları** |   
|:---:|:---:|:---:|:---:|
| Kurumsal | Bilgi çalışanı | İK, Finans | iOS |                                                           
| Kurumsal | Yöneticiler | İK, Finans | iOS |                                                           
| Kurumsal | Bilgi noktası | Perakende | Android |
| KCG | Bilgi çalışanı | Pazarlama, Satış | iOS |                                                           
| KCG | Yöneticiler | Pazarlama, Satış | iOS |

## <a name="next-steps"></a>Sonraki adımlar

Sonraki bölümde [Her kullanım örneği senaryosu için Intune gereksinimlerini tanımlama](planning-guide-requirements.md) hakkında yönergeler sağlanır.
