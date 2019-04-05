---
title: Intune’da modern kimlik doğrulaması olmayan uygulamaları engelleme
titleSuffix: Microsoft Intune
description: Uygulama ve Microsoft Intune kullanarak modern kimlik doğrulaması (ADAL) hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/03/2019
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.topic: conceptual
ms.technology: ''
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9ca96f36f8813d80c7ebb07bfb3bd65f8aa0b392
ms.sourcegitcommit: 71314481e644025c005019b478b4cbeaf2390ea9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59041680"
---
# <a name="block-apps-that-dont-use-modern-authentication-adal"></a>Modern kimlik doğrulaması (ADAL) kullanmayan uygulamaları engelleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Uygulama tabanlı koşullu erişim ile uygulama koruma ilkeleri kullanarak uygulamaları kullanan [modern kimlik doğrulaması](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a), bir OAuth2 uygulaması olan. Şu anda çoğu Office mobil ve masaüstü uygulaması modern kimlik doğrulaması kullanın. Ancak, vardır üçüncü taraf uygulamaları ve eski Office uygulamaları söz konusu kullanıcı temel kimlik doğrulaması ve form tabanlı kimlik doğrulaması gibi diğer kimlik doğrulama yöntemleri.

## <a name="block-access-to-apps"></a>Uygulamalara erişimi engelle

Modern kimlik doğrulaması kullanmayan uygulamalara erişimi engellemek için koşul erişim uygulamak için Intune uygulama koruma ilkelerini kullanın. Daha fazla bilgi için [Intune ile uygulama tabanlı koşullu erişim](app-based-conditional-access-intune.md).

## <a name="additional-information"></a>Ek bilgiler

Azure AD koşullu erişim hakkında daha fazla bilgi için aşağıdaki konulara bakın:
- [Azure Active Directory'de koşullu erişim nedir?](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)
- [Uygulama tabanlı koşullu erişim nasıl çalışır?](app-based-conditional-access-intune.md#how-app-based-conditional-access-works)
- [SharePoint Online ve Exchange Online için Azure Active Directory koşullu erişim ayarlama](https://docs.microsoft.com/azure/active-directory/conditional-access/conditional-access-for-exo-and-spo)

## <a name="next-steps"></a>Sonraki adımlar

- [Intune ile uygulama tabanlı koşullu erişim](app-based-conditional-access-intune.md)
