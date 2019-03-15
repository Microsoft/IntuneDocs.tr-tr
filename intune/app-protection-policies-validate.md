---
title: Uygulama koruma ilkesi kurulumunuzu doğrulama
titleSuffix: Microsoft Intune
description: Uygulama koruma ilkenizin kurulduğunu ve doğru şekilde çalıştığını sınamayı öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/13/2018
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.topic: conceptual
ms.technology: ''
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c340b224dea13f42dae579ddf8b607aa515ea399
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57398552"
---
# <a name="how-to-validate-your-app-protection-policy-setup"></a>Uygulama koruma ilkesi kurulumunuzu doğrulama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Uygulama koruma ilkenizin doğru kurulduğunu ve çalıştığını doğrulayın. Bu kılavuz, Azure portaldaki uygulama koruma ilkeleri için geçerlidir.

## <a name="checking-for-symptoms"></a>Belirtileri denetleme
Uygulama koruma bir veri koruması aracı olduğundan, kullanıcıların soruları bildirme olasılığı düşüktür. Uygulama koruma yapılandırmasında bir sorun varsa olmadan uygulama koruması gerekir ve bir sorun bilmiyorum kullanıcı sınırsız erişime. Bu nedenle, kullanıcılar uygulama korumanın kısıtlamalarını bilinçli sınayabilirsiniz küçük bir grupla uygulama koruma ilkelerinizin Pilot dağıtımını yaparak uygulama koruma yapılandırmanızı doğrulamanızı öneririz.


## <a name="what-to-check"></a>Denetlenmesi gerekenler

Uygulama koruma İlkesi davranış'ınızı beklendiği gibi olmayan gösteriyorsa şu öğeleri kontrol:

- Kullanıcılar uygulama koruma için lisanslı mı?
- Kullanıcılar O365 için lisanslı mı?
- Her kullanıcının uygulama koruma uygulamalarındaki durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir.

### <a name="user-app-protection-status"></a>Kullanıcı uygulama koruma durumu
1. [Azure portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. Seçin **istemci uygulamaları** > **İzleyici** >  **uygulama koruma durumu**ve ardından **atanan kullanıcılar**Döşe. 
4. Üzerinde **uygulama raporlama** sayfasında **Kullanıcı Seç** kullanıcıların ve grupların listesini getirmek için. 
5. Arayın ve listeden bir kullanıcı seçin ve sonra seçin **Kullanıcı Seç**. Üst kısmındaki **uygulama raporlama** bölmesinde, kullanıcıya uygulama koruma için lisanslı olup olmadığını görebilirsiniz. Ayrıca, kullanıcının O365 için tüm kullanıcı cihazlarına uygulama durumunu için bir lisans olup olmadığını görebilirsiniz.



## <a name="what-to-do"></a>Yapılması gereken
Kullanıcı durumuna göre gerçekleştirilecek eylemler şunlardır:

- Kullanıcının uygulama koruması için lisanslı değilse, kullanıcıya bir Intune lisansı atayın.
- Kullanıcının O365 için lisanslı değilse, kullanıcının bir lisansı alır.
- Kullanıcının lisansı **İade edilmedi** olarak listeleniyorsa bu uygulama için doğru biçimde bir uygulama koruma ilkesi yapılandırıp yapılandırmadığınıza bakın.
- Bu koşulların, uygulama koruma ilkelerinin geçerli olmasını istediğiniz tüm kullanıcılara uygulanacağını emin olun.

## <a name="see-also"></a>Ayrıca bkz.

[Intune uygulama koruma ilkesi nedir?](app-protection-policies.md)
