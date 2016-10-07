---
title:
- "MAM kurulumunuzu doğrulama | Microsoft Intune"
description: "Bu konular, MAM ilkenizin kurulumunun doğru yapıldığını ve beklendiği şekilde çalıştığını nasıl sınayıp doğrulayacağınızı açıklamaktadır."
keywords: 
author: karthikaraman
manager: angerobe
ms.date: 08/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 41d82597-e13e-4c3e-9151-e71392236ca0
ms.reviewer: joglocke
translationtype: Human Translation
ms.sourcegitcommit: 0736b5f24065f55d8fbd312395e4bb7226ebf619
ms.openlocfilehash: 5b6253d3d4c969b6947d83b5c8695a484f8c1d27


---

# Mobil uygulama yönetimi kurulumunuzu doğrulama

Bu konu, mobil uygulama yönetimini (MAM) ayarladıktan sonra sorunların denetlemesiyle ilgili bilgi sağlar. Bu kılavuz, Azure portalındaki MAM ilkeleri için geçerlidir.

### Belirtileri denetleme
MAM bir veri koruma aracı olduğundan kullanıcıların soruları bildirme olasılığı düşüktür. MAM yapılandırmasında bir sorun varsa, kullanıcılar MAM’ın olmadığı durumlardaki gibi sınırsız erişime sahip olur ve bir sorun olduğunun farkında olmayacaklardır. Bu nedenle MAM yapılandırmanızı, MAM ilkelerinizi MAM’in kısıtlamalarını bilinçli olarak sınayabilecek küçük bir grup kullanıcıda pilot bir çalışmayla deneyerek doğrulamanızı öneririz.


### Denetlenmesi gerekenler

Sınamalar MAM ilkelerinizin davranışının beklendiği gibi olmadığını gösteriyorsa, aşağıdakileri kontrol etmenizi öneririz:

- Kullanıcılar MAM için lisanslı mı?
- Kullanıcılar O365 için lisanslı mı?
- Her kullanıcının MAM uygulaması durumu. Uygulamalar için olabilecek durumlar **İade edildi** ve **İade edilmedi** şeklindedir.

#### Kullanıcı MAM durumu
1. Azure portalında **Intune mobil uygulama yönetimi** > **ayarlar** > **uygulama yönetimi** > **Tüm ayarlar** > **Kullanıcılardan uygulama raporlaması** > **kullanıcılar**’ı seçin.

2. Listeden bir kullanıcı seçin veya bir kullanıcı arayıp seçin, sonra **Kullanıcı seç**’i belirtin. **Uygulama raporlama** sütunun en üstünde kullanıcının MAM için lisanslı olup olmadığını göreceksiniz. Bunun altında kullanıcının O365 için lisanslı olup olmadığını ve kullanıcının tüm cihazları için uygulama durumunu göreceksiniz.

![MAM için uygulama durumları](..\media\ts-mam-user-apps.png) 

### Yapılması gereken
Kullanıcı durumuna göre gerçekleştirilecek eylemler şunlardır:

- Kullanıcı MAM için lisanslı değilse, kullanıcıya, [Intune lisanslarını yönetme](..\get-started\start-with-a-paid-subscription-to-microsoft-intune) bölümünde anlatıldığı gibi bir Intune lisansı atayın.
- Kullanıcı O365 için lisanslı değilse, kullanıcı için bir lisans edinin.
- Kullanıcının lisansı **İade edilmedi** olarak listeleniyorsa, bu uygulama için doğru biçimde bir MAM ilkesi yapılandırıp yapılandırmadığınıza bakın.
- Bu koşulların, MAM ilkelerinin geçerli olmasını istediğiniz tüm kullanıcılara uygulandığından emin olun.

### Ayrıca bkz.
[Microsoft Intune ile mobil uygulama yönetimi ilkelerinizi yapılandırmak için hazırlama](..\deploy-use\get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)

[Microsoft Intune ile mobil uygulama yönetimi ilkelerini kullanarak uygulama verilerini koruma](..\deploy-use\protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)



<!--HONumber=Oct16_HO1-->


