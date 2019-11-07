---
title: Intune ile uygulama tabanlı koşullu erişim ilkesini ayarlama
titleSuffix: Microsoft Intune
description: Intune ile uygulama tabanlı bir koşullu erişim ilkesi oluşturmayı öğrenin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/06/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 465f8b0001e5e2a049a3ffe12469bdb5057854ec
ms.sourcegitcommit: 28622c5455adfbce25a404de4d0437fa2b5370be
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73712841"
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Intune ile uygulama tabanlı koşullu erişim ilkeleri ayarlama

Onaylanan uygulamalar listesinin parçası olan uygulamalar için uygulama tabanlı koşullu erişim ilkeleri ayarlayın. Liste, Microsoft tarafından sınanan onaylı uygulamalardan oluşur.

Uygulama tabanlı koşullu erişim ilkelerini kullanabilmeniz için uygulamalarınıza [Intune uygulama koruma ilkelerinin](../apps/app-protection-policies.md) uygulanması gerekir.

> [!IMPORTANT]
> Bu makale, uygulama tabanlı bir koşullu erişim ilkesi ekleme adımlarında size yol gösterir. Onaylı uygulamalar listesinden SharePoint Online, Microsoft Teams ve Microsoft Exchange Online gibi uygulamaları eklerken de aynı adımları kullanabilirsiniz.

## <a name="create-app-based-conditional-access-policies"></a>Uygulama tabanlı koşullu erişim ilkeleri oluşturma

Koşullu Erişim, bir Azure Active Directory (Azure AD) teknolojisidir. *Intune* 'Dan erişebileceğiniz koşullu erişim düğümü, *Azure AD*'den erişebileceğiniz düğümdür. Aynı düğüm olduğundan, ilkeleri yapılandırmak için Intune ile Azure AD arasında geçiş yapmanız gerekmez.

Microsoft Endpoint Manager yönetim merkezinden koşullu erişim ilkeleri oluşturabilmeniz için önce bir Azure AD Premium lisansınızın olması gerekir.

### <a name="to-create-an-app-based-conditional-access-policy"></a>Uygulama tabanlı bir koşullu erişim ilkesi oluşturmak için

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431) oturum açın

2. **Son nokta güvenliği** > **koşullu erişim** > **Yeni ilke**' yi seçin.

3. Bir ilke **adı**girin ve ardından *atamalar*' ın altında **Kullanıcılar ve gruplar**' ı seçin. İlke için grupları eklemek üzere Dahil Et veya Hariç Tut seçeneklerini kullanın ve **Bitti**’yi seçin.

4. **Bulut uygulamaları veya eylemler**' i seçin ve korunacak uygulamaları seçin. Örneğin **Uygulama seçin**’e tıklayın, **Office 365 SharePoint Online** ve **Office 365 Exchange Online**’ı seçin.

   Değişikliklerinizi kaydetmek için **Bitti**’yi seçin.

5. **Koşullar** > **İstemci uygulamaları**’nı seçerek ilkeyi uygulamalara ve tarayıcılara uygulayın. Örneğin **Evet**’i seçin ve ardından **Tarayıcı** ve **Mobil uygulamalar ve masaüstü istemciler**’i etkinleştirin.

   Değişikliklerinizi kaydetmek için **Bitti**’yi seçin.

6. *Erişim denetimleri*altında, cihaz uyumluluğuna göre koşullu erişim uygulamak Için **izin ver** ' i seçin. Örneğin **Erişim ver** > **Cihazın uyumlu olarak işaretlenmesini gerektir**’i seçin.

   Değişikliklerinizi kaydetmek için **Seçin**’e tıklayın.

7. **Ilkeyi etkinleştir**için **Açık**' ı seçin ve sonra değişikliklerinizi kaydetmek için **Oluştur** ' u seçin.





## <a name="next-steps"></a>Sonraki adımlar
[Modern kimlik doğrulaması olmayan uygulamaları engelleme](app-modern-authentication-block.md)

## <a name="see-also"></a>Ayrıca bkz:

[Uygulama koruma ilkeleriyle uygulama verilerini koruma](../apps/app-protection-policies.md)
[Azure Active Directory’de Koşullu Erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
