---
title: "Modern kimlik doğrulaması olmayan uygulamaları engelleme | Microsoft Intune"
description: 
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 098b652c-01e0-45d1-a731-620b0d3dc7c1
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0f78ece8bbaf813c0082e6b764d174cf25bcb618
ms.openlocfilehash: 89f0bc5dd10c173718f9698e6e0342b5eb8c56e8


---

# Modern kimlik doğrulaması kullanılmayan uygulamaları engelleme (ADAL)
MAM ilkeleri (MAM CA) bulunan uygulamalar için koşullu erişim, bir OAuth2 uygulaması olan [modern kimlik doğrulaması](https://support.office.com/en-US/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) kullanan uygulamalara dayalıdır. Şu anda çoğu Office mobil ve masaüstü uygulaması modern kimlik doğrulaması kullansa da, temel kimlik doğrulaması ve form tabanlı kimlik doğrulaması gibi diğer kimlik doğrulama yöntemleri kullanan üçüncü taraf uygulamaları ve eski Office uygulamaları da vardır.

Bu uygulamalara erişimi engellemek için şunları öneririz:

* Modern olmayan kimlik doğrulama protokollerini engellemek için ADFS talep kurallarını ayarlayın. [O365’e tarayıcı tabanlı uygulamalar dışındaki tüm erişimi engelleme](https://technet.microsoft.com/library/dn592182.aspx) adlı 3. senaryoda ayrıntılı yönergeler verilmiştir.

### Ayrıca bkz.
[O365 hizmetlerine yalnızca Intune tarafından desteklenen uygulamaların erişmesine izin verme](allow-policy-managed-apps-access-to-o365.md)



<!--HONumber=Oct16_HO2-->


