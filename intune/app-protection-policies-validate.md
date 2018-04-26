---
title: Uygulama koruma ilkesi kurulumunuzu doğrulama
titleSuffix: Microsoft Intune
description: Uygulama koruma ilkenizin kurulduğunu ve doğru şekilde çalıştığını sınamayı öğrenin.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 01/23/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6ea79a2e177b8a4e85454140c7efb9172defe5b6
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-validate-your-app-protection-policy-setup"></a>Uygulama koruma ilkesi kurulumunuzu doğrulama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Uygulama koruma ilkenizin doğru kurulduğunu ve çalıştığını doğrulayın. Bu kılavuz, Azure portaldaki uygulama koruma ilkeleri için geçerlidir.

### <a name="checking-for-symptoms"></a>Belirtileri denetleme
Uygulama koruma bir veri koruması aracı olduğundan, kullanıcıların soruları bildirme olasılığı düşüktür. Uygulama koruma yapılandırmasında bir sorun varsa, kullanıcılar uygulama korumanın olmadığı durumlardaki gibi sınırsız erişime sahip olur ve bir sorun olduğunun farkına varmazlar. Bu nedenle uygulama koruma kısıtlamalarını bilinçli olarak sınayabilecek küçük bir grup kullanıcıya uygulama koruma ilkelerinizin pilot dağıtımını yaparak, uygulama koruma yapılandırmanızı doğrulamanızı öneririz.


### <a name="what-to-check"></a>Denetlenmesi gerekenler

Sınama, uygulama koruma ilkelerinizin davranışının beklendiği gibi olmadığını gösteriyorsa şu öğeleri kontrol etmenizi öneririz:

- Kullanıcılar uygulama koruma için lisanslı mı?
- Kullanıcılar O365 için lisanslı mı?
- Her kullanıcının uygulama koruma uygulamalarındaki durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir.

#### <a name="user-app-protection-status"></a>Kullanıcı uygulama koruma durumu
1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
1. **Uygulamaları yönetme** > **İzleme** >  **Uygulama koruma durumu** > **Atanan kullanıcılar**’ı seçin.

2. Listeden bir kullanıcı seçin veya bir kullanıcı arayıp seçin, sonra **Kullanıcı seçin**’i belirtin. **Uygulama raporlama** sütunun en üstünde kullanıcının uygulama koruması için lisanslı olup olmadığını görebilirsiniz. Ayrıca, kullanıcının O365 için lisanslı olup olmadığını ve kullanıcının tüm cihazları için uygulama durumunu göreceksiniz.



### <a name="what-to-do"></a>Yapılması gereken
Kullanıcı durumuna göre gerçekleştirilecek eylemler şunlardır:

- Kullanıcı uygulamayı koruma için lisanslı değilse, kullanıcıya bir Intune lisansı atayın.
- Kullanıcı O365 için lisanslı değilse, kullanıcı için bir lisans edinin.
- Kullanıcının lisansı **İade edilmedi** olarak listeleniyorsa bu uygulama için doğru biçimde bir uygulama koruma ilkesi yapılandırıp yapılandırmadığınıza bakın.
- Bu koşulların, uygulama koruma ilkelerinin geçerli olmasını istediğiniz tüm kullanıcılara uygulandığından emin olun.

### <a name="see-also"></a>Ayrıca bkz:

[Intune uygulama koruma ilkesi nedir?](app-protection-policies.md)
