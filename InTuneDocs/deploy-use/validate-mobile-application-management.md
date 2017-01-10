---
title: "MAM kurulumunuzu doğrulama | Microsoft Docs"
description: "Bu konular, MAM ilkenizin kurulumunun doğru yapıldığını ve beklendiği şekilde çalıştığını nasıl sınayıp doğrulayacağınızı açıklamaktadır."
keywords: 
author: andredm7
ms.author: andredm
manager: angerobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 41d82597-e13e-4c3e-9151-e71392236ca0
ms.reviewer: joglocke
translationtype: Human Translation
ms.sourcegitcommit: d6ff74f0b46baf384dbdedf13ad75538dd33a089
ms.openlocfilehash: 080d8f4fd4b6e1b53df860f4319b1c199d504c06


---

# <a name="validating-your-mobile-application-management-setup"></a>Mobil uygulama yönetimi kurulumunuzu doğrulama

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bu konu, mobil uygulama yönetimini (MAM) ayarladıktan sonra sorunların denetlemesiyle ilgili bilgi sağlar. Bu kılavuz, Azure portalındaki MAM ilkeleri için geçerlidir.

### <a name="checking-for-symptoms"></a>Belirtileri denetleme
MAM bir veri koruma aracı olduğundan kullanıcıların soruları bildirme olasılığı düşüktür. MAM yapılandırmasında bir sorun varsa, kullanıcılar MAM’ın olmadığı durumlardaki gibi sınırsız erişime sahip olur ve bir sorun olduğunun farkında olmayacaklardır. Bu nedenle MAM yapılandırmanızı, MAM ilkelerinizi MAM’in kısıtlamalarını bilinçli olarak sınayabilecek küçük bir grup kullanıcıda pilot bir çalışmayla deneyerek doğrulamanızı öneririz.


### <a name="what-to-check"></a>Denetlenmesi gerekenler

Sınamalar MAM ilkelerinizin davranışının beklendiği gibi olmadığını gösteriyorsa, aşağıdakileri kontrol etmenizi öneririz:

- Kullanıcılar MAM için lisanslı mı?
- Kullanıcılar O365 için lisanslı mı?
- Her kullanıcının MAM uygulaması durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir.

#### <a name="user-mam-status"></a>Kullanıcı MAM durumu
1. Azure portalında **Intune mobil uygulama yönetimi** > **ayarlar** > **uygulama yönetimi** > **Tüm ayarlar** > **Kullanıcılardan uygulama raporlaması** > **kullanıcılar**’ı seçin.

2. Listeden bir kullanıcı seçin veya bir kullanıcı arayıp seçin, sonra **Kullanıcı seç**’i belirtin. **Uygulama raporlama** sütunun en üstünde kullanıcının MAM için lisanslı olup olmadığını göreceksiniz. Bunun altında kullanıcının O365 için lisanslı olup olmadığını ve kullanıcının tüm cihazları için uygulama durumunu göreceksiniz.

![MAM için uygulama durumları](..\media\ts-mam-user-apps.png)

### <a name="what-to-do"></a>Yapılması gereken
Kullanıcı durumuna göre gerçekleştirilecek eylemler şunlardır:

- Kullanıcı MAM için lisanslı değilse, kullanıcıya, [Intune lisanslarını yönetme](..\get-started\start-with-a-paid-subscription-to-microsoft-intune.md) bölümünde anlatıldığı gibi bir Intune lisansı atayın.
- Kullanıcı O365 için lisanslı değilse, kullanıcı için bir lisans edinin.
- Kullanıcının lisansı **İade edilmedi** olarak listeleniyorsa, bu uygulama için doğru biçimde bir MAM ilkesi yapılandırıp yapılandırmadığınıza bakın.
- Bu koşulların, MAM ilkelerinin geçerli olmasını istediğiniz tüm kullanıcılara uygulandığından emin olun.

### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune ile mobil uygulama yönetimi ilkelerinizi yapılandırmak için hazırlanma](..\deploy-use\get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

[Microsoft Intune ile mobil uygulama yönetimi ilkeleri kullanarak uygulama verilerini koruma](..\deploy-use\protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


