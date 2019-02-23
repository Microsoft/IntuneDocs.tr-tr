---
title: Intune cihaz kaydı için çok faktörlü kimlik doğrulaması isteme
titlesuffix: Microsoft Intune
description: Azure AD’de Intune cihaz kaydı için çok faktörlü kimlik doğrulaması isteme.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 94280c73-c05c-4e72-b0dd-a7cb997782f9
ROBOTS: ''
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b6d4497c3cf62e6679ce222cf4185f48bdf846b1
ms.sourcegitcommit: e5f501b396cb8743a8a9dea33381a16caadc51a9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2019
ms.locfileid: "56742236"
---
# <a name="require-multi-factor-authentication-for-intune-device-enrollments"></a>Intune cihaz kayıtları için çok faktörlü kimlik doğrulaması isteme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune, şirket kaynaklarınızı güvenli hale getirmenize yardımcı olmak üzere cihaz kaydı için Azure Active Directory (AD) çok faktörlü kimlik doğrulamasını (MFA) kullanabilir.

MFA, aşağıdaki doğrulama yöntemlerinden herhangi ikisini veya daha fazlasını zorunlu tutar:

- Bildiğiniz bir şey (genellikle parola veya PIN).
- Sahip olduğunu bir şey (telefon gibi kopyalaması kolay olmayan güvenilir bir cihaz).
- Sahip olduğunuz bir özellik (parmak izi gibi biyometrik bilgiler).

MFA; iOS, Android, Windows 8.1 veya üzeri, Windows Phone 8.1 ya da Windows 10 Mobile veya üzeri cihazlar için desteklenir.

MFA’yı etkinleştirdiğinizde, son kullanıcıların bir cihazı kaydetmek için kimlik bilgilerini iki şekilde sağlamaları gerekir.

## <a name="configure-intune-to-require-multi-factor-authentication-at-device-enrollment"></a>Intune'u cihaz kaydında çok faktörlü kimlik doğrulama isteyecek şekilde yapılandırma

Bir cihaz kaydedildiğinde MFA istemek için şu adımları izleyin:

>[!Important]
>Bu ilkeyi uygulamak için kullanıcılara atanmış bir Azure Active Directory Premium P1 veya üzeri olması gerekir.

>[!Important]
>Microsoft Intune kaydı için **Cihaz tabanlı erişim kuralları** yapılandırmayın.

1. Kimlik bilgilerinizle [Microsoft Azure portalında](https://portal.azure.com) oturum açın.
2. Portalda, Git **Intune** ve **koşullu erişim**. Erişilen koşullu erişim düğümü *Intune* aynı düğümde erişilen aynıdır *Azure AD'ye*.
4. **Yeni ilke**’yi seçin.
5. **Yeni** ilkede, ilke için açıklayıcı bir ad yazın.
6. **Atamalar** kısmında **Kullanıcılar ve gruplar**’ı seçin. 
7. **Kullanıcılar ve gruplar**’da **Kullanıcı veya grup seçin**’e tıklayın ve **Kullanıcılar ve gruplar**’ı işaretleyin. Daha sonra, bu ilkeyi alacak kullanıcı ve/veya grupları seçin ve **Bitti**’ye tıklayın.
8. **Atamalar** kısmında **Bulut uygulamaları**’nı seçin.
9. **Bulut uygulamaları**‘nın **Ekleme** sekmesinde, **Uygulama seç**’i, daha sonra **Seçin** > **Microsoft Intune Kaydı**’nı ve son olarak **Bitti**’yi seçin.
10. **Atamalar** bölümünde, **Koşullar** altında MFA için hiçbir ayar yapılandırmanız gerekmez.
11. **Erişim denetimleri** kısmında **Ver**’i seçin.
12. **Ver** kısmında **Erişim ver**’i ve daha sonra **Çok faktörlü kimlik doğrulamasını gerektir**’i seçin. **Cihazın uyumlu olarak işaretlenmesini gerektir**’i seçmeyin çünkü bir cihaz kaydedilene kadar cihazın uyumluluğu değerlendirilemez. Daha sonra **Seç**’e tıklayın.
13. **Yeni ilke**’de **İlkeyi etkinleştir** > **Açık**’ı ve daha sonra **Oluştur**’u seçin.



## <a name="next-steps"></a>Sonraki adımlar

Artık kullanıcılar bir cihaz kaydettiğinde; PIN, telefon veya biyometrik bilgiler gibi ikinci bir kimlik tanımlama şekli ile kimlik doğrulamaları gerekecektir.
