---
title: "Intune kullanım örneği senaryolarını tanımlama | Microsoft Docs"
description: "Bu makale Intune kullanım örneğini ve bir Microsoft Intune yalnızca bulut uygulaması için alt kullanım örneği senaryolarını tanımlamaya yardımcı olur."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4b3c9af9-78da-44d2-8bd2-3f0f8885952d
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 031820d505e0e9cb007e47a5397934d0e505aed4
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="identify-intune-use-case-scenarios"></a>Intune kullanım örneği senaryolarını tanımlama

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Mobil cihaz yönetimi kullanım örneği senaryoları, kullanıcı türü veya rolünü ve cihazlarının sahipliğini (örneğin, şirket veya kişisel) açıklar. Kullanıcı örneği senaryoları, kullanıcılarınızı yönetilebilir gruplara ayırmanıza olanak tanıdığı için yararlıdır. Kullanım örneği senaryolarınızı tanımlamak, başarılı bir Intune dağıtımı planlama sürecinin önemli bir parçasıdır.

Kuruluşunuzun Intune kullanım örneği senaryolarının yanı sıra kuruluş gruplarını ve her kullanım örneği ile ilişkili mobil cihaz platformlarını tanımlamanıza yardımcı olmak için birkaç örnekten bahsedelim.

## <a name="use-case-scenarios"></a>Kullanım örneği senaryoları

Dağıtımınız için ana kullanım örneği senaryolarını tanımlamanıza yardımcı olmak üzere kuruluşunuzun Intune dağıtım hedeflerine ve amaçlarına başvurarak başlayabilirsiniz. Intune dağıtım planınız kapsamında, aşağıdaki soruları yanıtlamanız gerekir:

-   Şirkete ait cihazları desteklemeyi planlıyor musunuz?

-   Kişisel cihazları (KCG) desteklemeyi planlıyor musunuz?

### <a name="sub-use-case-scenarios"></a>Alt kullanım örneği senaryoları

Ana kullanım örneği senaryolarınızı tanımladıktan sonra, her kullanım örneği senaryosunun ayrıca alt kullanım örnekleri içerip içermediğini belirlemeniz gerekir. Örneğin, bir kuruluş ek alt kullanım örnekleri içeren bir kurumsal kullanım örneği senaryosunu desteklemek için gereksinimler tanımlamış olabilir:

-   Bilgi çalışanı

-   Yöneticiler

-   Bilgi noktası

Kullanım örneği ve alt kullanım örneği senaryolarına birkaç örnek burada verilmiştir. Kuruluşunuzun kullanım örneğini ve alt kullanım örneği senaryolarını girmek için aşağıdaki tabloyu kullanabilirsiniz:

| **Kullanım örnekleri** | **Alt kullanım örnekleri** |
|:---:|:---:|
| Kurumsal | Bilgi çalışanı |              
| Kurumsal | Yöneticiler |           
| Kurumsal | Bilgi noktası |
| KCG | Bilgi çalışanı |           
| KCG | Yöneticiler |

## <a name="identify-organizational-groups-associated-with-use-case-scenarios"></a>Kullanım örneği senaryoları ile ilişkili kuruluş gruplarını tanımlama

Şimdi, her bir kullanım örneği ve alt kullanım örneği senaryosu ile ilişkili kuruluş gruplarını tanımlamanız gerekir. Kuruluşunuzun bilgilerini girmek için şablon olarak kullanılabilecek kullanım örneği ve alt kullanım örneği senaryoları ile ilişkili kuruluş gruplarına birkaç örnek burada verilmiştir:

| **Kullanım örnekleri** | **Alt kullanım örnekleri** | **Kuruluş grupları** |
|:---:|:---:|:---:|
| Kurumsal | Bilgi çalışanı | İK, Finans |               
| Kurumsal | Yönetici | İK, Finans |            
| Kurumsal | Bilgi noktası | Perakende |
| KCG | Bilgi çalışanı | Pazarlama, Satış |            
| KCG | Yönetici | Pazarlama, Satış |

## <a name="identify-mobile-device-platforms-for-use-case-scenarios"></a>Kullanım örneği senaryoları için mobil cihaz platformlarını tanımlama

Burada her bir kullanım örneği senaryosuyla ilişkili mobil cihaz platformlarını belirlersiniz. Örneğin, kurumsal kullanım örneği senaryonuz iOS ve Android Samsung Knox cihaz platformlarını ve KCG ilkeniz, Android (Samsung KNOX olmayan) ve Windows 10 Mobile gibi ek mobil cihaz platformları için destek içerebilir. Her bir kullanım örneği senaryosuyla ilişkili mobil cihaz platformlarına bir örnek burada verilmiştir. Aşağıdaki tabloyu kullanarak, kuruluşunuzun kullanım örneği senaryolarıyla ilişkili cihaz platformlarını girebilirsiniz:

| **Kullanım örnekleri** | **Alt kullanım örnekleri** | **Gruplar** | **Cihaz platformları** |   
|:---:|:---:|:---:|:---:|
| Kurumsal | Bilgi çalışanı | İK, Finans | iOS |                                                           
| Kurumsal | Yöneticiler | İK, Finans | iOS |                                                           
| Kurumsal | Bilgi noktası | Perakende | Android |
| KCG | Bilgi çalışanı | Pazarlama, Satış | iOS |                                                           
| KCG | Yöneticiler | Pazarlama, Satış | iOS |

## <a name="next-steps"></a>Sonraki adımlar

Sonraki bölümde [Her kullanım örneği senaryosu için Intune gereksinimlerini tanımlama](section-3-determine-use-case-requirements.md) hakkında yönergeler sağlanır.

