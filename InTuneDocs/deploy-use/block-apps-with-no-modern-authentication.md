---
title: "Modern kimlik doğrulaması olmayan uygulamaları engelleme | Microsoft Docs"
description: 
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 098b652c-01e0-45d1-a731-620b0d3dc7c1
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e55cf608c2e5157feeb40ba20d3988b5b35064db
ms.openlocfilehash: b2d708e35a7993ff7c5e3db170b1025794b33baf
ms.lasthandoff: 02/25/2017


---

# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Modern kimlik doğrulaması kullanılmayan uygulamaları engelleme (ADAL)

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Uygulama koruma ilkeleri bulunan uygulama tabanlı koşullu erişim, bir OAuth2 uygulaması olan [modern kimlik doğrulaması](https://support.office.com/en-US/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) kullanan uygulamalara dayalıdır. Şu anda çoğu Office mobil ve masaüstü uygulaması modern kimlik doğrulaması kullansa da, temel kimlik doğrulaması ve form tabanlı kimlik doğrulaması gibi diğer kimlik doğrulama yöntemleri kullanan üçüncü taraf uygulamaları ve eski Office uygulamaları da vardır.

Bu uygulamalara erişimi engellemek için şunları öneririz:

* Modern olmayan kimlik doğrulama protokollerini engellemek için ADFS talep kurallarını ayarlayın. [O365’e tarayıcı tabanlı uygulamalar dışındaki tüm erişimi engelleme](https://technet.microsoft.com/library/dn592182.aspx) adlı 3. senaryoda ayrıntılı yönergeler verilmiştir.

>[!IMPORTANT]
>Uygulama tabanlı CA, Azure Active Directory (Azure AD) sertifika tabanlı kimlik doğrulaması ile kullanılmamalıdır. Aynı anda bunlardan yalnızca biri yapılandırılmış olabilir.

### <a name="see-also"></a>Ayrıca bkz.
[O365 hizmetlerine yalnızca Intune tarafından desteklenen uygulamaların erişmesine izin verme](allow-policy-managed-apps-access-to-o365.md)

