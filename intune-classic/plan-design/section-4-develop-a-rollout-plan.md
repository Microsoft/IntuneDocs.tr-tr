---
title: "Intune dağıtımı hedeflenen grup ve zaman çerçevelerini belirleme | Microsoft Docs"
description: "Bu makale, Microsoft Intune yalnızca bulut uygulaması için dağıtım yapılması hedeflenen grupları ve zaman çerçevelerini belirlemeye yardımcı olur."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a63f78f-a7e7-4f44-9288-16b28d5d58ca
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 2a970badf5ac18a05115a72dc267ee455ba4628d
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="develop-an-intune-rollout-plan"></a>Bir Intune dağıtım planı geliştirin

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Bu bölüm, Intune dağıtımınız için hedeflenecek kuruluş gruplarının yanı sıra, her grup için dağıtım zaman çerçevesini ve kullanılacak kayıt yaklaşımlarını belirlemenize yardımcı olur.

## <a name="determine-intune-rollout-targeted-groups-and-timeframes"></a>Intune dağıtımı hedeflenen grupları ve zaman çerçevelerini belirleyin

Öncelikle Intune dağıtımınız ile hedeflenecek grupları belirlemek önemlidir. Bu kılavuzun önceki bölümlerindeki Intune kullanım örneği senaryoları kısmında hedeflenen gruplar ele alınmıştı.

İkinci olarak, her bir grubun Intune dağıtımı için hedefleneceği zaman çerçevesini belirlemeniz gerekir. Normalde bu, her grubun dağıtım zaman çerçevesini belirlemeye yardımcı olması için Intune dağıtım ekibi ve hedeflenen gruplarla iletişim kurmayı gerektirir.

Örneğin, Intune dağıtım ekibi zaman çerçevesini belirlemek için grubun değişiklik isteyip istemediği, kullanıcı ve cihaz sayısı, cihaz platformlarının sayısı, gereksinimler, coğrafi konum ve iş riski gibi faktörleri tartışabilir.

Kuruluşlar genellikle BT bölümündeki küçük bir kullanıcı grubunu hedefleyerek Intune dağıtımını ilk başta pilot olarak denemeyi tercih eder. Ardından pilot deneme, daha kapsamlı bir BT kullanıcıları grubuna genişletilebilir ve diğer kuruluş gruplarından katılım sağlanabilir. Başarılı bir pilot sonrası, kuruluşlar bir tam üretim dağıtımı başlatmaya hazırdır ve kuruluşun geri kalan gruplarını hedefler. Bazı farklı dağıtım grupları ve aşamaları aşağıda verilmiştir:

-   **Pilot:** Dağıtılacak ilk aşama pilot kullanıcılar olmalıdır. Pilot kullanıcıların yeni bir çözüm içindeki ilk kullanıcılar olduklarını anlamaları ve yapılandırma, belgeleme, bildirimler gibi faktörleri iyileştirmek ve sonraki dağıtım aşamalarında diğer tüm kullanıcıların kullanımını kolaylaştırmak amacıyla geri bildirim sağlamaya istekli olmaları gerekir. Bu kullanıcılar, Yöneticiler veya VIP olmamalıdır.

-   **Departmanlar:** Her departman bir dağıtım aşaması olabilir. Bu senaryoda, aynı anda bir departmanın tümünü hedefleyeceksiniz. Bu dağıtım türünde, her aşama büyük olasılıkla mobil cihazı aynı şekilde kullanır ve aynı uygulamalara erişir. Kullanıcılar büyük olasılıkla aynı türde ilkelere sahip olacaktır.

-   **Coğrafi konum:** Bu dağıtım türü aynı kıta, ülke, bölge ya da şirket binasında bulunan tüm kullanıcılara dağıtma gibi belirli bir coğrafi konuma dayalıdır. Bu tür aşamalı dağıtım, kullanıcıların belirli konumuna odaklanma olanağı sağlar. Bu, Intune’un aynı anda dağıtıldığı konum sayısının azalmasıyla daha fazla [beyaz eldiven](#user-assisted-enrollment) yaklaşımına olanak tanıyabilir. Farklı departmanların veya kullanım örneklerinin aynı konumda olma olasılığından dolayı farklı kullanım örnekleri aynı anda dağıtılabilir.

-   **Platform:** Bu dağıtım türü aynı anda benzer platformları dağıtmaya dayalıdır. Örneğin ilk ay tüm iOS cihazları, ardından Android ve daha sonra Windows dağıtılabilir. Bu tür aşamalı dağıtım, yardım masası desteğini basitleştirmeye yardımcı olur. Yardım masası desteğinin aynı anda yalnızca tek bir platformu desteklemesi yeterlidir.

Hedeflenen grupları ve zaman çizelgelerini içeren bir Intune dağıtım planı örneği şu şekildedir:

| **Dağıtım aşaması** | **Temmuz** | **Ağustos** | **Eylül** | **Ekim** |
|:---:|:---:|:---:|:---:|:---:|
| Sınırlı Pilot | BT (50 kullanıcı) |  |  |  |                                                         
| Genişletilmiş Pilot | BT (200 kullanıcı), BT Yöneticileri (10 kullanıcı) |  |  |  |                                                         
| Üretim dağıtım aşaması 1 |  | Satış ve Pazarlama (2000 kullanıcı) |  |  |
| Üretim dağıtım aşaması 2 |  |  | Perakende (1000 kullanıcı) |  |
| Üretim dağıtım aşaması 3 |  |  |  | İK (50 kullanıcı), Finans (40 kullanıcı), Yöneticiler (30 kullanıcı) |

## <a name="determine-the-intune-enrollment-approach"></a>Intune kaydı yaklaşımını belirleme

Artık Intune dağıtımınız için hedeflenen grupları ve zaman çerçevelerini belirlediğinize göre, bir sonraki adım her grup için en uygun Intune kaydı yaklaşımını seçmektir. Kuruluşların Intune dağıtımı için kullanabileceği farklı kayıt yaklaşımları vardır. Bunlar arasında kullanıcı self servis, kullanıcı yardımlı kayıt ve BT teknik fuarı sayılabilir.

### <a name="user-self-service"></a>Kullanıcı self servis

Bu yaklaşımda, kullanıcı genellikle BT departmanı tarafından sağlanan kayıt yönergelerini izleyerek kendi cihazını kaydetmekten sorumludur. Kuruluşlarda en yaygın olarak kullanılan yaklaşım budur ve ölçeklenebilirliği kullanıcı yardımlı kayıttan daha fazladır.

### <a name="user-assisted-enrollment"></a>Kullanıcı yardımlı kayıt

Bu, BT ekibi üyesinin kayıt işlemine kişisel olarak veya Skype üzerinden yardımcı olduğu, "beyaz eldiven" adı verilen yaklaşımdır. Bu yaklaşım genellikle yönetim ekibi ve kayıt sürecinde daha fazla yardıma ihtiyaç duyan diğer gruplarda kullanılır.

### <a name="it-tech-fair"></a>BT teknik fuarı

Intune kullanıcı kaydı için başka bir seçenek de BT teknik fuarı düzenlemektir. Bu etkinlikte, BT grubu, kullanıcıların Intune kaydı hakkında bilgi alabileceği, sorular sorabileceği ve kayıt sürecine ilişkin yardım alabileceği bir Intune kayıt yardım standı kurar. Bu seçeneği kullanmak, özellikle Intune dağıtımının ilk aşamalarında hem BT grubu hem de kullanıcı için yararlı olabilir.

Hedeflenen gruplar, zaman dilimleri ve kayıt yaklaşımlarını içeren bir Intune dağıtım planına bir örnek şu şekildedir:

| **Dağıtım aşaması** | **Temmuz** | **Ağustos** | **Eylül** | **Ekim** |
|:---:|:---:|:---:|:---:|:---:|
| Sınırlı Pilot |  |  |  |  |                                                         
| Self servis | BT |  |  |  |
| Genişletilmiş Pilot |  |  |  |  |                                                         
| Self servis | BT |  |  |  |
| Beyaz eldiven | BT Yöneticileri |  |  |  |
| Üretim dağıtım aşaması 1 |  | Satış, Pazarlama |  |  |
| Self servis |  | Satış ve Pazarlama |  |  |
| Üretim dağıtım aşaması 2 |  |  | Perakende |  |
| Self servis |  |  |  |  |
| Üretim dağıtım aşaması 3 |  |  | Perakende |  |
| Self servis |  |  |  | İK, Finans |
| Beyaz eldiven |  |  |  | Yöneticiler |

## <a name="next-section"></a>Sonraki Bölüm

Sonraki bölümde [bir Intune dağıtımı iletişim planı geliştirme](section-5-develop-a-rollout-communication-plan.md) hakkında yönergeler sağlanır.

