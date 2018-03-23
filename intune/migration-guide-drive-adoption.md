---
title: Koşullu erişimle son kullanıcı benimsemesi sağlama
titlesuffix: Microsoft Intune
description: Microsoft Intune’da kaydı sağlamak için koşullu erişimi nasıl kullanacağınızı öğrenin.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 31e2a79e5506666cc5ebe655536600b57a429802
ms.sourcegitcommit: 21db583d6a9d3c15a8a8ee5579309dff1cfe1f8b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2018
---
# <a name="drive-end-user-adoption-with-conditional-access-in-microsoft-intune"></a>Microsoft Intune’da koşullu erişimle son kullanıcı benimsemesi sağlama

Kaydı silinen cihazlar için e-postayı engellemek gibi koşullu erişim özelliklerini Intune ile etkinleştirme, cihaz kaydına ve uyumluluğuna yardımcı olabilir ancak geçiş işleminin başarılı olması için gerekli değildir. Geçiş benimseme hedefleri ve güvenlik gereksinimleriniz başarıyı belirleyen unsurlar olmalıdır.

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


Bu birçok yaklaşımdan biridir. Her aşama için kayıt talimatı alındıktan sonra tüm koşullu erişimi etkileyen daha basit bir süreç seçebilir veya koşullu erişimi en baştan uygulayan ve erişim için tam uyumluluk gerektiren daha sıkı bir süreç seçebilirsiniz.

-   [Koşullu erişim](conditional-access.md) hakkında daha fazla bilgi edinin.

## <a name="task-list-for-conditional-access"></a>Koşullu erişim için görev listesi

### <a name="task-1-decide-how-you-are-going-to-implement-conditional-access"></a>Görev 1: Koşullu erişimi nasıl uygulayacağınıza karar verme

[Koşullu erişim kullanmanın yaygın yolları](conditional-access-intune-common-ways-use.md).

### <a name="task-2-set-up-intune-conditional-access"></a>2. Görev: Intune koşullu erişimi ayarlayın

Aşağıdaki seçeneklerden birini seçin:

-   [Azure Active Directory'de koşullu erişimi yapılandırma](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

-   [Intune ile şirket içi Exchange bağlayıcısını yükleme](exchange-connector-install.md)

-   [Exchange Online için uygulama tabanlı koşullu erişim ilkeleri ayarlama](app-based-conditional-access-intune-create.md)

-   [SharePoint Online için uygulama tabanlı koşullu erişim ilkeleri ayarlama](app-based-conditional-access-intune-create.md)

-   [Modern kimlik doğrulaması (ADAL) kullanmayan uygulamaları engelleme](app-modern-authentication-block.md)

## <a name="next-steps"></a>Sonraki adımlar

[Tipik geçiş döngüsü](migration-guide-cycle.md) hakkında bilgi edinin.
