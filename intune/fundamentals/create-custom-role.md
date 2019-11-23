---
title: Create a custom role in Intune
description: Learn how to create a custom role in Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: pjain
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3ca83287c58f8d2fb7c8eec5f8cc793e2c67b77a
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74390697"
---
# <a name="create-a-custom-role-in-intune"></a>Create a custom role in Intune

You can create a custom Intune role that includes any permissions required for a specific job function. Örneğin bir BT departmanı grubu, uygulamaları, ilkeleri ve yapılandırma profillerini yönetiyorsa tüm bu izinleri tek bir özel role ekleyebilirsiniz. After creating a custom role, you can [assign](assign-role.md) it to any users that need those permissions.

Rolleri oluşturmak, düzenlemek ve atamak için, hesabınızın Azure AD’de aşağıdaki izinlerden birine sahip olması gerekir:
- **Genel Yönetici**
- **Intune Hizmet Yöneticisi**

## <a name="to-create-a-custom-role"></a>Özel bir rol oluşturmak için

1. [Azure portalında](https://portal.azure.com) Intune kimlik bilgilerinizle oturum açın.

2. Soldaki menüden **Tüm hizmetler**’i seçtikten sonra metin kutusu filtresine **Intune** yazın.

3. Choose **Intune** > **Roles** > **All roles** > **Add**.

4. **Özel Rol Ekle** dikey penceresinde yeni rol için ad ve açıklama girin, ardından **İzinler**'e tıklayın.

5. **İzinler** dikey penceresinde, bu rolle birlikte kullanmak istediğiniz izinleri seçin.

6. On the **Scope (Tags)** blade, choose the tags for this role. This role can access resources that also have these tags.

7. İşiniz bittiğinde **Tamam**’ı seçin.

8. **Özel Rol Ekle** dikey penceresinde **Oluştur**’a tıklayın. The new role is displayed in the list on the **Intune roles - All roles** blade.


## <a name="copy-a-role"></a>Copy a role

You can also copy an existing role.

1. Sign into the [Azure portal](https://portal.azure.com) with your Intune credentials and select **Intune**.

2. Select **Roles** > **All roles** > select a role in the list > **Duplicate**.

3. Under **Duplicate role**, enter a name. Make sure to use a unique name.

4. All the permissions and scope tags from the original role will already be selected. You can subsequently change the duplicate role's **Name**, **Description**, **Permissions**, and **Scope (Tags)** .

5. **Oluştur**’u seçin. 

## <a name="next-steps"></a>Sonraki adımlar
- [Assign a role to a user](assign-role.md)
- [Learn more about role-based access control in Intune](role-based-access-control.md)
