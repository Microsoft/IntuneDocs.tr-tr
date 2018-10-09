---
title: Intune ile uygulama tabanlı koşullu erişim ilkesi ayarlama
description: Intune ile uygulama tabanlı koşullu erişim ilkesi oluşturmayı öğrenin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2d6d67454409cf8a8749d28cba6ac76f591da9e3
ms.sourcegitcommit: fffa64f28278573dc83a846b647315def2108781
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48231296"
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Intune ile uygulama tabanlı koşullu erişim ilkeleri ayarlama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makale, onaylı uygulamalar listesinin parçası olan uygulamalar için uygulama tabanlı koşullu erişim ilkelerinin nasıl ayarlanacağını açıklar. Liste, Microsoft tarafından sınanan onaylı uygulamalardan oluşur.

> [!IMPORTANT]
> Bu makale uygulama tabanlı bir koşullu erişim ilkesini ekleme konusunda size adım adım yol gösterir. Onaylanan uygulamalar listesinden SharePoint Online, Microsoft Teams ve Microsoft Exchange Online gibi uygulamaları eklerken de aynı adımları kullanabilirsiniz.

## <a name="create-app-based-conditional-access-policies-in-azure-ad-workload"></a>Azure AD iş yükünde uygulama tabanlı koşullu erişim ilkeleri oluşturma

BT yöneticileri, Azure AD iş yükünden uygulama tabanlı koşullu erişim ilkeleri oluşturabilir. Böylece Azure ve Intune iş yükleri arasında değişim yapmanız gerekmez ve işiniz kolaylaşır.

> [!IMPORTANT]
> Intune Azure portalından Azure AD koşullu erişim ilkeleri oluşturmak için bir Azure AD Premium lisansınız olması gerekir.

### <a name="to-create-an-app-based-conditional-access-policy"></a>Uygulama tabanlı bir koşullu erişim ilkesi oluşturmak için

> [!IMPORTANT]
> Uygulama tabanlı koşullu erişim ilkelerini kullanmadan önce uygulamalarınıza [Intune uygulama koruma ilkeleri](app-protection-policies.md) uygulamanız gerekir.

1. **Intune Panosu**’nda, **Koşullu erişim**’i seçin.

2. **İlkeler** bölmesinde **Yeni ilke**’yi seçerek yeni uygulama tabanlı koşullu erişim ilkenizi oluşturun.

4. İlke için bir ad girip **Atamalar** kısmından uygun ayarları yapılandırdıktan sonra **Erişim denetimleri** bölümünden **Ver**’i seçin.

5. **Onaylı istemci uygulama gerektir**’i, **Seçin**’i ve daha sonra **Oluştur**’u seçerek yeni ilkeyi kaydedin.

## <a name="next-steps"></a>Sonraki adımlar
[Modern kimlik doğrulaması olmayan uygulamaları engelleme](app-modern-authentication-block.md)

### <a name="see-also"></a>Ayrıca bkz:

[Uygulama koruma ilkeleriyle uygulama verilerini koruma](app-protection-policies.md)
[Azure Active Directory’de Koşullu Erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
