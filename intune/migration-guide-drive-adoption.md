---
title: Koşullu erişimle son kullanıcı benimsemesi sağlama
titleSuffix: Microsoft Intune
description: Koşullu erişim cihaz kaydına Microsoft Intune için kullanmayı öğrenin.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 40e78d85c215bbb5cc126705f26041ce4f7786f4
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2019
ms.locfileid: "67549447"
---
# <a name="drive-end-user-adoption-with-conditional-access-in-microsoft-intune"></a>Microsoft Intune koşullu erişimle son kullanıcı benimsemesi

Kaydı silinen cihazlar için e-posta engellemek gibi koşullu erişim özelliklerini Intune ile etkinleştirme cihaz kaydına ve uyumluluğuna yardımcı olabilir ancak geçiş başarılı olması için gerekli değildir. Geçiş benimseme hedefleri ve güvenlik gereksinimleriniz başarıyı belirleyen unsurlar olmalıdır.

## <a name="migration-campaign-with-conditional-access"></a>Koşullu erişim ile geçiş kampanyası

Koşullu erişim ile bir geçiş kampanyasını geliştirme için tipik bir yaklaşım şöyledir:

1. Tüm kullanıcılar için zorlanacak ancak eski MDM sağlayıcısından geçiş yapacak kullanıcıları özellikle hariç tutmak için koşullu erişim kuralları ayarlayın. Tüm koşullu erişim dışlanan kullanıcılar ile bir Azure AD kullanıcı grubu oluşturabilirsiniz.

2. Kullanıcılar geçiş yaptıkça, bunları koşullu erişim dışlama grubundan kaldırın.

3. Geçiş tamamlandıktan sonra Intune erişime izin vermedikçe varsayılan olarak engellemek için tüm koşullu erişim ilkelerini yapılandırabilirsiniz.

### <a name="advantages"></a>Yararları

- Yeni kullanıcı hesapları veya önceki çözüm tarafından yönetilmeyen kullanıcı hesabı için erişim denetimi sağlar.

- Geçişte önceki çözümün kullanıcıları için mehil süresi sağlar.

- Üretkenlik kaybını en aza indirir

### <a name="disadvantages"></a>Dezavantajlar

- Önceki çözümün kullanıcıları, koşullu erişim bu kullanıcılar için etkinleştirilene kadar yönetilmeyen cihazları kullanarak kaynaklara potansiyel olarak erişebilir.


Bu birçok yaklaşımdan biridir. Her aşama kaydetmeye talimatı alındıktan sonra tüm koşullu erişimi etkileyen daha basit bir işlem veya en çok baştan koşullu erişimi zorunlu kılar ve tüm erişim için tam uyumluluk gerektiren daha sıkı bir süreç seçebilirsiniz.

- [Koşullu Erişim](conditional-access.md) hakkında daha fazla bilgi edinin.

## <a name="task-list-for-conditional-access"></a>Koşullu erişim için görev listesi

### <a name="task-1-decide-how-you-are-going-to-implement-conditional-access"></a>1\. Görev: Nasıl koşullu erişim uygulamaktır yerleştireceğinize karar verme

[Koşullu erişim kullanmanın yaygın yolları](conditional-access-intune-common-ways-use.md).

### <a name="task-2-set-up-intune-conditional-access"></a>2\. Görev: Intune koşullu erişimi ayarlama

Aşağıdaki seçeneklerden birini seçin:

- [Azure Active Directory'de koşullu erişimi yapılandırma](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

- [Intune ile şirket içi Exchange bağlayıcısını yükleme](exchange-connector-install.md)

- [Exchange Online için uygulama tabanlı koşullu erişim ilkeleri ayarlama](app-based-conditional-access-intune-create.md)

- [SharePoint Online için uygulama tabanlı koşullu erişim ilkeleri ayarlama](app-based-conditional-access-intune-create.md)

- [Modern kimlik doğrulaması (ADAL) kullanmayan uygulamaları engelleme](app-modern-authentication-block.md)

## <a name="next-steps"></a>Sonraki adımlar

[Tipik geçiş döngüsü](migration-guide-cycle.md) hakkında bilgi edinin.
