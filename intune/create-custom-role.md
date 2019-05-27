---
title: Intune'da bir özel rol oluşturma
description: Özel bir rol Intune oluşturmayı öğrenin.
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
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: d053b0b37931443a343c91b5122b7a097d248c51
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66048684"
---
# <a name="create-a-custom-role-in-intune"></a>Intune'da bir özel rol oluşturma

Belirli bir işi yapmak için gereken izinleri içeren özel bir Intune rolü oluşturabilirsiniz. Örneğin bir BT departmanı grubu, uygulamaları, ilkeleri ve yapılandırma profillerini yönetiyorsa tüm bu izinleri tek bir özel role ekleyebilirsiniz. Özel bir rolü oluşturduktan sonra aşağıdakileri yapabilirsiniz [atama](assign-role.md) bunu tüm kullanıcılara bu izinlere sahip olmanız gerekir.

Rolleri oluşturmak, düzenlemek ve atamak için, hesabınızın Azure AD’de aşağıdaki izinlerden birine sahip olması gerekir:
- **Genel Yönetici**
- **Intune Hizmet Yöneticisi**

## <a name="to-create-a-custom-role"></a>Özel bir rol oluşturmak için

1. [Azure portalında](https://portal.azure.com) Intune kimlik bilgilerinizle oturum açın.

2. Soldaki menüden **Tüm hizmetler**’i seçtikten sonra metin kutusu filtresine **Intune** yazın.

3. Seçin **Intune** > **rolleri** > **tüm rolleri** > **Ekle**.

4. **Özel Rol Ekle** dikey penceresinde yeni rol için ad ve açıklama girin, ardından **İzinler**'e tıklayın.

5. **İzinler** dikey penceresinde, bu rolle birlikte kullanmak istediğiniz izinleri seçin. Hangi izinleri uygulamak istediğinize karar vermenize yardımcı olması için [Intune RBAC tablosunu](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) kullanın.

6. Üzerinde **kapsam (etiketler)** dikey penceresinde, bu rol için etiketleri seçin. Bu rol, bu etiketlere de sahip kaynaklara erişebilir.

7. İşiniz bittiğinde **Tamam**’ı seçin.

8. **Özel Rol Ekle** dikey penceresinde **Oluştur**’a tıklayın. Yeni rol listesinde görüntülenen **Intune rolleri - tüm roller** dikey penceresi.

## <a name="next-steps"></a>Sonraki adımlar
- [Bir kullanıcıya rol atama](assign-role.md)
- [Intune rol tabanlı erişim denetimi hakkında daha fazla bilgi edinin](role-based-access-control.md)
