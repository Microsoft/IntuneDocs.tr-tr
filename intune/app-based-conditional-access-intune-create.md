---
title: Intune ile uygulama tabanlı koşullu erişim ilkesi ayarlama
titlesuffix: Microsoft Intune
description: Intune ile uygulama tabanlı koşullu erişim ilkesi oluşturmayı öğrenin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 079671064c09c22d151ea71f8b3fb385652aef0f
ms.sourcegitcommit: bee072b61cf8a1b8ad8d736b5f5aa9bc526e07ec
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53816931"
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Intune ile uygulama tabanlı koşullu erişim ilkeleri ayarlama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Onaylı uygulamalar listesinin parçası olan uygulamalar için uygulama tabanlı koşullu erişim ilkeleri ayarlayın. Liste, Microsoft tarafından sınanan onaylı uygulamalardan oluşur.

> [!IMPORTANT]
> Bu makale uygulama tabanlı bir koşullu erişim ilkesini ekleme konusunda size adım adım yol gösterir. Onaylı uygulamalar listesinden SharePoint Online, Microsoft Teams ve Microsoft Exchange Online gibi uygulamaları eklerken de aynı adımları kullanabilirsiniz.

## <a name="create-app-based-conditional-access-policies-in-azure-ad-workload"></a>Azure AD iş yükünde uygulama tabanlı koşullu erişim ilkeleri oluşturma

BT yöneticileri, Azure AD iş yükünden uygulama tabanlı koşullu erişim ilkeleri oluşturabilir. Bu erişim, Azure ve Intune iş yükleri arasında geçiş yapmanız gerekmediği anlamına gelir.

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

### <a name="see-also"></a>Ayrıca bkz.

[Uygulama koruma ilkeleriyle uygulama verilerini koruma](app-protection-policies.md)
[Azure Active Directory’de Koşullu Erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
