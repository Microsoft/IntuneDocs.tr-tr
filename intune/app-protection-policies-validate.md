---
title: Uygulama koruma ilkesi kurulumunuzu doğrulama
titleSuffix: Microsoft Intune
description: Intune düzgün çalışmasını ve uygulama koruma ilkenizin ayarlanıp ayarlanmadığını test öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/08/2019
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
ms.openlocfilehash: 760ff85bc31cf66e66a3bf98f7da22d5ce48eee0
ms.sourcegitcommit: 364a7dbc7eaa414c7a9c39cf53eb4250e1ad3151
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59292236"
---
# <a name="how-to-validate-your-app-protection-policy-setup-in-microsoft-intune"></a>Microsoft Intune uygulama koruma İlkesi kurulumunuzu doğrulama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Uygulama koruma ilkenizin doğru kurulduğunu ve çalıştığını doğrulayın. Bu kılavuz, Azure portaldaki uygulama koruma ilkeleri için geçerlidir.

## <a name="checking-for-symptoms"></a>Belirtileri denetleme
Uygulama koruma bir veri koruması aracı olduğundan, kullanıcıların soruları bildirme olasılığı düşüktür. Uygulama koruma yapılandırmasında bir sorun varsa, kullanıcı bunlar olmadan uygulama koruması gerekir ve bir sorun bildikleri mıydı sınırsız erişime sahip. Bu nedenle, kullanıcılar uygulama korumanın kısıtlamalarını bilinçli sınayabilirsiniz küçük bir grupla uygulama koruma ilkelerinizin Pilot dağıtımını yaparak uygulama koruma yapılandırmanızı doğrulamanızı öneririz.

## <a name="what-to-check"></a>Denetlenmesi gerekenler

Uygulama koruma İlkesi davranış'ınızı beklendiği gibi çalışan değil gösteriyorsa şu öğeleri kontrol:

- Kullanıcılar uygulama koruma için lisanslı mı?
- Kullanıcılar O365 için lisanslı mı?
- Her biri kullanıcıların uygulama koruma uygulamalarındaki beklendiği gibi durumudur. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir.

### <a name="user-app-protection-status"></a>Kullanıcı uygulama koruma durumu
1. [Azure portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. Seçin **istemci uygulamaları** >  **uygulama koruma durumu**ve ardından **atanan kullanıcılar** Döşe. 
4. Üzerinde **uygulama raporlama** sayfasında **Kullanıcı Seç** kullanıcıların ve grupların listesini getirmek için. 
5. Arayın ve listeden bir kullanıcı seçin ve sonra seçin **Kullanıcı Seç**. Üst kısmındaki **uygulama raporlama** bölmesinde, kullanıcıya uygulama koruma için lisanslı olup olmadığını görebilirsiniz. Ayrıca, kullanıcının O365 için tüm kullanıcı cihazlarına uygulama durumunu için bir lisans olup olmadığını görebilirsiniz.

## <a name="what-to-do"></a>Yapılması gereken
Kullanıcı durumuna göre gerçekleştirilecek eylemler şunlardır:

- Kullanıcının uygulama koruması için lisanslı değilse, Ata bir [Intune lisansı](licenses.md) kullanıcı.
- Kullanıcının O365 için lisanslı değilse olursa, bir [lisans](licenses.md) kullanıcı.
- Bir kullanıcının uygulama olarak listeleniyorsa **iade edilmedi**, size doğru yapılandırmadığınıza bakın bir [uygulama koruma İlkesi](app-protection-policies-validate.md) bu uygulama için.
- Bu koşullar, istediğiniz tüm kullanıcılara uygulanmasını sağlamak [uygulama koruma ilkeleri](app-protection-policies-monitor.md) uygulamak için.

## <a name="see-also"></a>Ayrıca bkz.

- [Intune uygulama koruma ilkesi nedir?](app-protection-policies.md)
- [Intune içeren lisanslar](licenses.md)
- [Kullanıcılar cihazlarını Intune'a kaydedebilmesi için kullanıcılara lisans atama](licenses-assign.md)
- [Uygulama koruma İlkesi kurulumunuzu doğrulama](app-protection-policies-validate.md)
- [Uygulama koruma ilkelerini izleme](app-protection-policies-monitor.md)

