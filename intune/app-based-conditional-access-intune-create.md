---
title: Intune ile uygulama tabanlı koşullu erişim ilkesini ayarlama
titleSuffix: Microsoft Intune
description: Intune ile uygulama tabanlı bir koşullu erişim ilkesi oluşturmayı öğrenin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6bb07f1ddfcbe05f8039f934725c8122ecd96590
ms.sourcegitcommit: bd09decb754a832574d7f7375bad0186a22a15ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/19/2019
ms.locfileid: "71303879"
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Intune ile uygulama tabanlı koşullu erişim ilkeleri ayarlama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Onaylanan uygulamalar listesinin parçası olan uygulamalar için uygulama tabanlı koşullu erişim ilkeleri ayarlayın. Liste, Microsoft tarafından sınanan onaylı uygulamalardan oluşur.

> [!IMPORTANT]
> Bu makale, uygulama tabanlı bir koşullu erişim ilkesi ekleme adımlarında size yol gösterir. Onaylı uygulamalar listesinden SharePoint Online, Microsoft Teams ve Microsoft Exchange Online gibi uygulamaları eklerken de aynı adımları kullanabilirsiniz.

## <a name="create-app-based-conditional-access-policies"></a>Uygulama tabanlı koşullu erişim ilkeleri oluşturma
Koşullu Erişim, bir Azure Active Directory (Azure AD) teknolojisidir. *Intune*’dan erişilen Koşullu Erişim düğümü *Azure AD*’den erişilen düğümle aynıdır. Başka bir deyişle ilkeleri yapılandırmak için Intune ile Azure AD arasında geçiş yapmanız gerekmez.

> [!IMPORTANT]
> Intune portalından koşullu erişim ilkeleri oluşturmak için bir Azure AD Premium lisansa sahip olmanız gerekir.

### <a name="to-create-an-app-based-conditional-access-policy"></a>Uygulama tabanlı bir koşullu erişim ilkesi oluşturmak için

> [!IMPORTANT]
> Uygulama tabanlı koşullu erişim ilkelerini kullanmadan önce uygulamalarınıza [Intune uygulama koruma ilkelerinin](app-protection-policies.md) uygulanması gerekir.

1. **Intune panosunda** **koşullu erişim**' i seçin.

2. **İlkeler** bölmesinde yeni **ilke** ' yi seçerek yeni uygulama tabanlı koşullu erişim ilkenizi oluşturun.

4. İlke için bir ad girip **Atamalar** kısmından uygun ayarları yapılandırdıktan sonra **Erişim denetimleri** bölümünden **Ver**’i seçin.

5. **Onaylı istemci uygulama gerektir**’i, **Seçin**’i ve daha sonra **Oluştur**’u seçerek yeni ilkeyi kaydedin.

## <a name="next-steps"></a>Sonraki adımlar
[Modern kimlik doğrulaması olmayan uygulamaları engelleme](app-modern-authentication-block.md)

## <a name="see-also"></a>Ayrıca bkz.

[Uygulama koruma ilkeleriyle uygulama verilerini koruma](app-protection-policies.md)
[Azure Active Directory’de Koşullu Erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
