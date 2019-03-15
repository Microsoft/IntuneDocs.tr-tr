---
title: Intune ile uygulama tabanlı koşullu erişim ilkesi ayarlama
titlesuffix: Microsoft Intune
description: Intune ile uygulama tabanlı koşullu erişim ilkesi oluşturmayı öğrenin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2019
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cc73e24da6cd774811eb30d0ca7f551760b9a274
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57389394"
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Intune ile uygulama tabanlı koşullu erişim ilkeleri ayarlama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Onaylı uygulamalar listesinin parçası olan uygulamalar için uygulama tabanlı koşullu erişim ilkeleri ayarlayın. Liste, Microsoft tarafından sınanan onaylı uygulamalardan oluşur.

> [!IMPORTANT]
> Bu makale uygulama tabanlı bir koşullu erişim ilkesini ekleme konusunda size adım adım yol gösterir. Onaylı uygulamalar listesinden SharePoint Online, Microsoft Teams ve Microsoft Exchange Online gibi uygulamaları eklerken de aynı adımları kullanabilirsiniz.

## <a name="create-app-based-conditional-access-policies"></a>Uygulama tabanlı koşullu erişim ilkeleri oluşturma
Koşullu Erişim, bir Azure Active Directory (Azure AD) teknolojisidir. *Intune*’dan erişilen Koşullu Erişim düğümü *Azure AD*’den erişilen düğümle aynıdır. Başka bir deyişle, ilkeler yapılandırmak için Intune ve Azure AD arasında değişim yapmanız gerekmez.

> [!IMPORTANT]
> Intune portalından koşullu erişim ilkeleri oluşturmak için bir Azure AD Premium lisansınız olması gerekir.

### <a name="to-create-an-app-based-conditional-access-policy"></a>Uygulama tabanlı bir koşullu erişim ilkesi oluşturmak için

> [!IMPORTANT]
> Uygulama tabanlı koşullu erişim ilkelerini kullanmadan önce uygulamalarınıza [Intune uygulama koruma ilkeleri](app-protection-policies.md) uygulamanız gerekir.

1. İçinde **Intune Panosu**seçin **koşullu erişim**.

2. **İlkeler** bölmesinde **Yeni ilke**’yi seçerek yeni uygulama tabanlı koşullu erişim ilkenizi oluşturun.

4. İlke için bir ad girip **Atamalar** kısmından uygun ayarları yapılandırdıktan sonra **Erişim denetimleri** bölümünden **Ver**’i seçin.

5. **Onaylı istemci uygulama gerektir**’i, **Seçin**’i ve daha sonra **Oluştur**’u seçerek yeni ilkeyi kaydedin.

## <a name="next-steps"></a>Sonraki adımlar
[Modern kimlik doğrulaması olmayan uygulamaları engelleme](app-modern-authentication-block.md)

### <a name="see-also"></a>Ayrıca bkz.

[Uygulama koruma ilkeleriyle uygulama verilerini koruma](app-protection-policies.md)
[Azure Active Directory’de Koşullu Erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
