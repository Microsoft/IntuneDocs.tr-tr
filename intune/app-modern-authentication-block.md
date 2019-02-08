---
title: Intune’da modern kimlik doğrulaması olmayan uygulamaları engelleme
titleSuffix: Microsoft Intune
description: Microsoft Intune kullanarak modern kimlik doğrulaması (ADAL) kullanmayan uygulamaları engelleme hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a651f926f8e8cc5beab80a70649c82677e0b2487
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55833061"
---
# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Modern kimlik doğrulaması kullanılmayan uygulamaları engelleme (ADAL)

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Uygulama tabanlı koşullu erişim ile uygulama koruma ilkeleri kullanarak uygulamaları kullanan [modern kimlik doğrulaması](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a), bir OAuth2 uygulaması olan. Şu anda çoğu Office mobil ve masaüstü uygulaması modern kimlik doğrulaması kullanın. Ancak, vardır üçüncü taraf uygulamaları ve eski Office uygulamaları söz konusu kullanıcı temel kimlik doğrulaması ve form tabanlı kimlik doğrulaması gibi diğer kimlik doğrulama yöntemleri.

## <a name="block-apps"></a>Uygulamaları engelleme

Modern kimlik doğrulaması kullanmayan uygulamalara erişimi engellemek için aşağıdaki yöntemlerden öneririz:

- Modern olmayan kimlik doğrulama protokollerini engellemek için ADFS talep kurallarını ayarlayın. [O365’e tarayıcı tabanlı uygulamalar dışındaki tüm erişimi engelleme](https://technet.microsoft.com/library/dn592182.aspx) adlı 3. senaryoda ayrıntılı yönergeler verilmiştir.
- **Exchange ve SharePoint Online** için Azure Active Directory Koşullu Erişimi'ni ve SharePoint Online için PowerShell'in Set-SPOTenant cmdlet'ini kullanın. Ayrıntılı yönergeler için bkz. [SharePoint Online'ı ve Exchange Online'ı Azure Active Directory koşullu erişimi için ayarlama](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-no-modern-authentication#legacy-authentication-protocols).


>[!IMPORTANT]
>Uygulama tabanlı CA, Azure Active Directory (Azure AD) sertifika tabanlı kimlik doğrulaması ile kullanılmamalıdır. Aynı anda bunlardan yalnızca biri yapılandırılmış olabilir.

## <a name="next-steps"></a>Sonraki adımlar

- [Intune ile uygulama tabanlı koşullu erişim](app-based-conditional-access-intune.md)
