---
title: Koşullu erişimle Son Kullanıcı benimsemesini sürücü
titleSuffix: Microsoft Intune
description: Microsoft Intune 'de kayıt yapmak için koşullu erişimi nasıl kullanacağınızı öğrenin.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 115313816542fd642e6a0c67900abd48b7146e42
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72510070"
---
# <a name="drive-end-user-adoption-with-conditional-access-in-microsoft-intune"></a>Microsoft Intune koşullu erişimle Son Kullanıcı benimsemesini sürücü olarak

Kayıtlı olmayan cihazlar için e-postayı engelleme gibi Intune ile koşullu erişim özelliklerini etkinleştirmek, kayıt ve uyumluluğun sağlanmasına yardımcı olabilir, ancak geçiş işleminin başarılı olması için gerekli değildir. Geçiş benimseme hedefleri ve güvenlik gereksinimleriniz başarıyı belirleyen unsurlar olmalıdır.

## <a name="migration-campaign-with-conditional-access"></a>Koşullu erişimle geçiş kampanyası

Bir geçiş kampanyasını koşullu erişimle geliştirmeyle ilgili tipik bir yaklaşım aşağıda verilmiştir:

1. Koşullu erişim kurallarını tüm kullanıcılar için zorunlu olacak şekilde ayarlayın, ancak özellikle eski MDM sağlayıcısından geçirilmesi gereken kullanıcıları hariç tutun. Tüm koşullu erişime sahip kullanıcılar için bir Azure AD Kullanıcı grubu oluşturabilirsiniz.

2. Kullanıcılar geçiş yaparken bunları koşullu erişim dışlama grubundan kaldırın.

3. Geçiş tamamlandıktan sonra, Intune erişime izin verilmediği takdirde tüm koşullu erişim ilkelerini varsayılan olarak engellenecek şekilde yapılandırın.

### <a name="advantages"></a>Yararları

- Yeni kullanıcı hesapları veya önceki çözüm tarafından yönetilmeyen kullanıcı hesabı için erişim denetimi sağlar.

- Geçişte önceki çözümün kullanıcıları için mehil süresi sağlar.

- Üretkenlik kaybını en aza indirir

### <a name="disadvantages"></a>Dezavantajlar

- Önceki çözümün kullanıcıları, koşullu erişim bu kullanıcılar için etkinleştirilene kadar yönetilmeyen cihazları kullanarak kaynaklara erişebilme olasılığı vardır.


Bu birçok yaklaşımdan biridir. Her aşama kaydolduktan sonra tüm koşullu erişimi engelleyen daha basit bir işlem veya çok başından koşullu erişimi zorlayan daha sıkı bir işlem seçebilirsiniz ve tüm erişim için tam uyumluluk gerektirir.

- [Koşullu Erişim](../protect/conditional-access.md) hakkında daha fazla bilgi edinin.

## <a name="task-list-for-conditional-access"></a>Koşullu erişim için görev listesi

### <a name="task-1-decide-how-you-are-going-to-implement-conditional-access"></a>Görev 1: koşullu erişimi nasıl uygulayacağınıza karar verin

[Koşullu erişim kullanmanın yaygın yolları](../protect/conditional-access-intune-common-ways-use.md).

### <a name="task-2-set-up-intune-conditional-access"></a>2\. görev: Intune koşullu erişimini ayarlama

Aşağıdaki seçeneklerden birini seçin:

- [Azure Active Directory Koşullu erişimi yapılandırma](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

- [Intune ile şirket içi Exchange bağlayıcısını yükleme](../protect/exchange-connector-install.md)

- [Exchange Online için uygulama tabanlı koşullu erişim ilkeleri ayarlama](../protect/app-based-conditional-access-intune-create.md)

- [SharePoint Online için uygulama tabanlı koşullu erişim ilkeleri ayarlama](../protect/app-based-conditional-access-intune-create.md)

- [Modern kimlik doğrulaması (ADAL) kullanmayan uygulamaları engelleme](../protect/app-modern-authentication-block.md)

## <a name="next-steps"></a>Sonraki adımlar

[Tipik geçiş döngüsü](../migration-guide-cycle.md) hakkında bilgi edinin.
