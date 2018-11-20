---
title: Intune’da modern kimlik doğrulaması olmayan uygulamaları engelleme
titleSuffix: Microsoft Intune
description: Modern kimlik doğrulaması (ADAL) kullanmayan uygulamaları engelleme hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cf8b323d6f7afa5fc7e3cfecbf04f61e0d11d9c5
ms.sourcegitcommit: 6ff5df63a2fff291d7ac5fed9c51417fe808650d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52167374"
---
# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Modern kimlik doğrulaması kullanılmayan uygulamaları engelleme (ADAL)

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Uygulama tabanlı koşullu erişim ile uygulama koruma ilkeleri kullanarak uygulamaları kullanan [modern kimlik doğrulaması](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a), bir OAuth2 uygulaması olan. Şu anda çoğu Office mobil ve masaüstü uygulaması modern kimlik doğrulaması kullanın. Ancak, vardır üçüncü taraf uygulamaları ve eski Office uygulamaları söz konusu kullanıcı temel kimlik doğrulaması ve form tabanlı kimlik doğrulaması gibi diğer kimlik doğrulama yöntemleri.

Bu uygulamalara erişimi engellemek için aşağıdaki yöntemlerden öneririz:

* Modern olmayan kimlik doğrulama protokollerini engellemek için ADFS talep kurallarını ayarlayın. [O365’e tarayıcı tabanlı uygulamalar dışındaki tüm erişimi engelleme](https://technet.microsoft.com/library/dn592182.aspx) adlı 3. senaryoda ayrıntılı yönergeler verilmiştir.
* **Exchange ve SharePoint Online** için Azure Active Directory Koşullu Erişimi'ni ve SharePoint Online için PowerShell'in Set-SPOTenant cmdlet'ini kullanın. Ayrıntılı yönergeler için bkz. [SharePoint Online'ı ve Exchange Online'ı Azure Active Directory koşullu erişimi için ayarlama](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-no-modern-authentication#legacy-authentication-protocols).


>[!IMPORTANT]
>Uygulama tabanlı CA, Azure Active Directory (Azure AD) sertifika tabanlı kimlik doğrulaması ile kullanılmamalıdır. Aynı anda bunlardan yalnızca biri yapılandırılmış olabilir.

### <a name="see-also"></a>Ayrıca bkz.
[Intune ile uygulama tabanlı koşullu erişim](app-based-conditional-access-intune.md)
