---
title: Intune 'da özel bir rol oluşturma
description: Microsoft Intune özel rol oluşturmayı öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: pjain
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6b7e8f5077f2052a11c980ae3f5629af810a8a0b
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71731573"
---
# <a name="create-a-custom-role-in-intune"></a>Intune 'da özel bir rol oluşturma

Belirli bir iş işlevi için gerekli izinleri içeren özel bir Intune rolü oluşturabilirsiniz. Örneğin bir BT departmanı grubu, uygulamaları, ilkeleri ve yapılandırma profillerini yönetiyorsa tüm bu izinleri tek bir özel role ekleyebilirsiniz. Özel bir rol oluşturduktan sonra, bu izinlere ihtiyacı olan tüm kullanıcılara [atayabilirsiniz](assign-role.md) .

Rolleri oluşturmak, düzenlemek ve atamak için, hesabınızın Azure AD’de aşağıdaki izinlerden birine sahip olması gerekir:
- **Genel Yönetici**
- **Intune Hizmet Yöneticisi**

## <a name="to-create-a-custom-role"></a>Özel bir rol oluşturmak için

1. [Azure portalında](https://portal.azure.com) Intune kimlik bilgilerinizle oturum açın.

2. Soldaki menüden **Tüm hizmetler**’i seçtikten sonra metin kutusu filtresine **Intune** yazın.

3. @No__t **ıntune** **@no__t-** 3**tüm rollerin** > **Add**' i seçin.

4. **Özel Rol Ekle** dikey penceresinde yeni rol için ad ve açıklama girin, ardından **İzinler**'e tıklayın.

5. **İzinler** dikey penceresinde, bu rolle birlikte kullanmak istediğiniz izinleri seçin.

6. **Kapsam (Etiketler)** dikey penceresinde bu rolün etiketlerini seçin. Bu rol, bu etiketlerin de bulunduğu kaynaklara erişebilir.

7. İşiniz bittiğinde **Tamam**’ı seçin.

8. **Özel Rol Ekle** dikey penceresinde **Oluştur**’a tıklayın. Yeni rol, **Intune rolleri-tüm roller** dikey penceresinde listede görüntülenir.

## <a name="next-steps"></a>Sonraki adımlar
- [Bir kullanıcıya rol atama](assign-role.md)
- [Intune 'da rol tabanlı erişim denetimi hakkında daha fazla bilgi edinin](role-based-access-control.md)
