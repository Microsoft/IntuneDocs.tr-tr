---
title: "Uygulama koruma ilkelerinizi doğrulama"
titleSuffix: Azure portal
description: "Bu konu başlıkları altında, uygulama koruma ilkenizin doğru kurulduğunu ve beklendiği şekilde çalıştığını nasıl sınayıp doğrulayabileceğiniz açıklanır.\""
keywords: 
author: erikre
ms.author: erikre
manager: angerobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7914946519bc1977aeabfb474f66d4ced2a8f8ee
ms.sourcegitcommit: 67ec0606c5440cffa7734f4eefeb7121e9d4f94f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/08/2017
---
# <a name="how-to-validate-your-app-protection-policy-setup"></a>Uygulama koruma ilkesi kurulumunuzu doğrulama

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Bu konu, uygulama koruma ilkelerini ayarladıktan sonra sorunların denetlemesiyle ilgili bilgi sağlar. Bu kılavuz, Azure portaldaki uygulama koruma ilkeleri için geçerlidir.

### <a name="checking-for-symptoms"></a>Belirtileri denetleme
Uygulama koruma bir veri koruması aracı olduğundan, kullanıcıların soruları bildirme olasılığı düşüktür. Uygulama koruma yapılandırmasında bir sorun varsa, kullanıcılar uygulama korumanın olmadığı durumlardaki gibi sınırsız erişime sahip olur ve bir sorun olduğunun farkına varmazlar. Bu nedenle, uygulama koruma ilkelerinizi uygulama korumanın kısıtlamalarını bilinçli olarak test edebilecek küçük bir grup kullanıcıya uygulama koruma ilkelerinizin pilot dağıtımını yaparak, uygulama koruma yapılandırmanızı doğrulamanızı öneririz.


### <a name="what-to-check"></a>Denetlenmesi gerekenler

Testler uygulama koruma ilkelerinizin davranışının beklendiği gibi olmadığını gösteriyorsa, aşağıdakileri kontrol etmenizi öneririz:

- Kullanıcılar uygulama koruma için lisanslı mı?
- Kullanıcılar O365 için lisanslı mı?
- Her kullanıcının uygulama koruma uygulamalarındaki durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir.

#### <a name="user-app-protection-status"></a>Kullanıcı uygulama koruma durumu
1. Azure Portal’da **Uygulamaları yönet** > **İzle** >  **Uygulama koruma kullanıcı durumu** > **kullanıcılar**’ı seçin.

2. Listeden bir kullanıcı seçin veya bir kullanıcı arayıp seçin, sonra **Kullanıcı seç**’i belirtin. **Uygulama raporlama** sütunun en üstünde kullanıcının uygulama koruma için lisanslı olup olmadığını göreceksiniz. Bunun altında kullanıcının O365 için lisanslı olup olmadığını ve kullanıcının tüm cihazları için uygulama durumunu göreceksiniz.



### <a name="what-to-do"></a>Yapılması gereken
Kullanıcı durumuna göre gerçekleştirilecek eylemler şunlardır:

- Kullanıcı uygulamayı koruma için lisanslı değilse, kullanıcıya bir Intune lisansı atayın.
- Kullanıcı O365 için lisanslı değilse, kullanıcı için bir lisans edinin.
- Kullanıcının lisansı **Giriş yapmadı** olarak listeleniyorsa, bu uygulama için doğru biçimde bir uygulama koruma ilkesi yapılandırıp yapılandırmadığınıza bakın.
- Bu koşulların, uygulama koruma ilkelerinin geçerli olmasını istediğiniz tüm kullanıcılara uygulandığından emin olun.

### <a name="see-also"></a>Ayrıca bkz.

[Intune uygulama koruma ilkesi nedir?](app-protection-policies.md)
