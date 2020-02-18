---
title: Intune cihaz kaydı için çok faktörlü kimlik doğrulaması isteme
titleSuffix: Microsoft Intune
description: Azure AD’de Intune cihaz kaydı için çok faktörlü kimlik doğrulaması isteme.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 94280c73-c05c-4e72-b0dd-a7cb997782f9
ROBOTS: ''
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 14347d12888ff5ef61d4543409a08fbdeb371c89
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77415212"
---
# <a name="require-multi-factor-authentication-for-intune-device-enrollments"></a>Intune cihaz kayıtları için çok faktörlü kimlik doğrulaması isteme

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune, şirket kaynaklarınızı güvenli hale getirmenize yardımcı olmak üzere cihaz kaydı için Azure Active Directory (AD) çok faktörlü kimlik doğrulamasını (MFA) kullanabilir.

MFA, aşağıdaki doğrulama yöntemlerinden herhangi ikisini veya daha fazlasını zorunlu tutar:

- Bildiğiniz bir şey (genellikle parola veya PIN).
- Sahip olduğunu bir şey (telefon gibi kopyalaması kolay olmayan güvenilir bir cihaz).
- Sahip olduğunuz bir özellik (parmak izi gibi biyometrik bilgiler).

MFA, iOS/ıpados, Android, Windows 8.1 veya üzeri, Windows Phone 8,1 ya da Windows 10 Mobile veya üzeri cihazlarda desteklenir.

MFA’yı etkinleştirdiğinizde, son kullanıcıların bir cihazı kaydetmek için kimlik bilgilerini iki şekilde sağlamaları gerekir.

## <a name="configure-intune-to-require-multi-factor-authentication-at-device-enrollment"></a>Intune'u cihaz kaydında çok faktörlü kimlik doğrulama isteyecek şekilde yapılandırma

Bir cihaz kaydedildiğinde MFA istemek için şu adımları izleyin:

>[!Important]
>Bu ilkeyi uygulamak için kullanıcılara atanmış bir Azure Active Directory Premium P1 veya üzeri olması gerekir.

>[!Important]
>Microsoft Intune kaydı için **Cihaz tabanlı erişim kuralları** yapılandırmayın.

1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)' nde oturum açın, **cihaz** **koşullu erişim** > seçin. *Intune*’dan erişilen Koşullu Erişim düğümü *Azure AD*’den erişilen düğümle aynıdır.
2. **Yeni ilke**’yi seçin.
3. **Yeni** ilkede, ilke için açıklayıcı bir ad yazın.
4. **Atamalar** kısmında **Kullanıcılar ve gruplar**’ı seçin. 
5. **Kullanıcılar ve gruplar**’da **Kullanıcı veya grup seçin**’e tıklayın ve **Kullanıcılar ve gruplar**’ı işaretleyin. Daha sonra, bu ilkeyi alacak kullanıcı ve/veya grupları seçin ve **Bitti**’ye tıklayın.
6. **Atamalar** kısmında **Bulut uygulamaları**’nı seçin.
7. **Bulut uygulamaları**‘nın **Ekleme** sekmesinde, **Uygulama seç**’i, daha sonra **Seçin** > **Microsoft Intune Kaydı**’nı ve son olarak **Bitti**’yi seçin. **Microsoft Intune kaydı**' nı seçerek, koşullu erişim MFA yalnızca cihazın kaydına uygulanır (tek seferlik MFA istemi).
8. **Atamalar** bölümünde, **Koşullar** altında MFA için hiçbir ayar yapılandırmanız gerekmez.
9. **Erişim denetimleri** kısmında **Ver**’i seçin.
10. **Ver** kısmında **Erişim ver**’i ve daha sonra **Çok faktörlü kimlik doğrulamasını gerektir**’i seçin. **Cihazın uyumlu olarak işaretlenmesini gerektir**’i seçmeyin çünkü bir cihaz kaydedilene kadar cihazın uyumluluğu değerlendirilemez. Daha sonra **Seç**’e tıklayın.
11. **Yeni ilke**’de **İlkeyi etkinleştir** > **Açık**’ı ve daha sonra **Oluştur**’u seçin.



## <a name="next-steps"></a>Sonraki adımlar

Artık kullanıcılar bir cihaz kaydettiğinde; PIN, telefon veya biyometrik bilgiler gibi ikinci bir kimlik tanımlama şekli ile kimlik doğrulamaları gerekecektir.
