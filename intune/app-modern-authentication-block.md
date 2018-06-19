---
title: Intune’da modern kimlik doğrulaması olmayan uygulamaları engelleme
titleSuffix: Microsoft Intune
description: Modern kimlik doğrulaması (ADAL) kullanmayan uygulamaları engelleme hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dcdc7628f75221228d788c2cb1995189ea8f81f0
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34223110"
---
# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Modern kimlik doğrulaması kullanılmayan uygulamaları engelleme (ADAL)

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Uygulama koruma ilkeleri bulunan uygulama tabanlı koşullu erişim, bir OAuth2 uygulaması olan [modern kimlik doğrulaması](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) kullanan uygulamalara dayalıdır. Şu anda çoğu Office mobil ve masaüstü uygulaması modern kimlik doğrulaması kullansa da temel kimlik doğrulaması ve form tabanlı kimlik doğrulaması gibi diğer kimlik doğrulama yöntemleri kullanan üçüncü taraf uygulamaları ve eski Office uygulamaları da vardır.

Bu uygulamalara erişimi engellemek için şunları öneririz:

* Modern olmayan kimlik doğrulama protokollerini engellemek için ADFS talep kurallarını ayarlayın. [O365’e tarayıcı tabanlı uygulamalar dışındaki tüm erişimi engelleme](https://technet.microsoft.com/library/dn592182.aspx) adlı 3. senaryoda ayrıntılı yönergeler verilmiştir.
* **SharePoint Online** için PowerShell komutu [Set-SPOTenant](https://technet.microsoft.com/library/fp161390.aspx) kullanarak eski kimlik doğrulama protokolleri özelliğini false olarak ayarlamak için SharePoint Online hizmetindeki modern olmayan kimlik doğrulamasını devre dışı bırakın:

```
 Set-SPOTenant -LegacyAuthProtocolsEnabled $false
```


>[!IMPORTANT]
>Uygulama tabanlı CA, Azure Active Directory (Azure AD) sertifika tabanlı kimlik doğrulaması ile kullanılmamalıdır. Aynı anda bunlardan yalnızca biri yapılandırılmış olabilir.

### <a name="see-also"></a>Ayrıca bkz:
[Intune ile uygulama tabanlı koşullu erişim](app-based-conditional-access-intune.md)
