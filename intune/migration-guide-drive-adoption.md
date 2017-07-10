---
title: "Koşullu erişimle son kullanıcı benimsemesi sağlama"
description: "Bu makalenin amacı, Intune kaydını teşvik etmek için koşullu erişimden nasıl yararlanılacağına ilişkin öngörüler sağlamaktır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0b2fbcc1d63f229e1b63873841bc300bdde92fa3
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2017
---
# <a name="drive-end-user-adoption-with-conditional-access"></a>Koşullu erişimle son kullanıcı benimsemesi sağlama

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Kaydı silinen cihazlar için e-posta engellemek gibi koşullu erişim özelliklerini Intune ile etkinleştirme, cihaz kaydına ve uyumluluğuna yardımcı olabilir ancak geçiş işleminin başarılı olması için gerekli değildir. Geçiş benimseme hedefleri ve güvenlik gereksinimleriniz başarıyı belirleyen unsurlar olmalıdır.

## <a name="migration-campaign-with-conditional-access"></a>Koşullu erişim ile geçiş kampanyası

Koşullu erişim ile bir geçiş kampanyasını geliştirme için tipik bir yaklaşım şöyledir:

1.  Tüm kullanıcılar için uygulanacak koşullu erişim kuralları ayarlayın ancak eski MDM sağlayıcısından geçiş yapacak kullanıcıları özellikle dışlayın. Tüm koşullu erişimden dışlanan bir Azure AD kullanıcı grubu oluşturabilirsiniz.

2.  Kullanıcılar geçiş yaptıkça, bunları koşullu erişim dışlama grubundan kaldırın.

3.  Geçiş tamamlandıktan sonra, Intune erişime izin vermedikçe varsayılan olarak tüm koşullu erişim ilkelerini engellemek için yapılandırın.

### <a name="advantages"></a>Yararları

-   Yeni kullanıcı hesapları veya önceki çözüm tarafından yönetilmeyen kullanıcı hesabı için erişim denetimi sağlar.

-   Geçişte önceki çözümün kullanıcıları için mehil süresi sağlar.

-   Üretkenlik kaybını en aza indirir

### <a name="disadvantages"></a>Dezavantajlar

-   Önceki çözümün kullanıcıları, koşullu erişim bu kullanıcılar için etkinleştirilene kadar yönetilmeyen cihazları kullanarak kaynaklara potansiyel olarak erişebilir.

> [!TIP]
> Bu birçok yaklaşımdan biridir. Her aşama için kayıt talimatı alındıktan sonra tüm koşullu erişimi etkileyen daha basit bir süreç seçebilir veya koşullu erişimi en baştan uygulayan ve erişim için tam uyumluluk gerektiren daha sıkı bir süreç seçebilirsiniz.

-   [Koşullu erişim](/intune/conditional-access) hakkında daha fazla bilgi edinin.

## <a name="task-list-for-conditional-access"></a>Koşullu erişim için görev listesi

### <a name="task-1-decide-how-you-are-going-to-implement-conditional-access"></a>Görev 1: Koşullu erişimi nasıl uygulayacağınıza karar verme

[Koşullu erişim kullanmanın yaygın yolları](/intune/conditional-access-intune-common-ways-use).

### <a name="task-2-set-up-intune-conditional-access"></a>2. Görev: Intune koşullu erişimi ayarlayın

Aşağıdaki seçeneklerden birini seçin:

-   [Azure Active Directory'de koşullu erişimi yapılandırma](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

-   [Intune ile şirket içi Exchange bağlayıcısını yükleme](/intune/exchange-connector-install)

-   [Exchange Online için uygulama tabanlı koşullu erişim ilkeleri ayarlama](/intune/app-based-conditional-access-intune-exchange-online-create)

-   [SharePoint Online için uygulama tabanlı koşullu erişim ilkeleri ayarlama](/intune/app-based-conditional-access-intune-sharepoint-online-create)

-   [Modern kimlik doğrulaması (ADAL) kullanmayan uygulamaları engelleme](/intune/app-modern-authentication-block)

## <a name="next-steps"></a>Sonraki adımlar

[Normal geçiş süreci](migration-guide-cycle.md)
