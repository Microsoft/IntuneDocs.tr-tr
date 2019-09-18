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
ms.openlocfilehash: 10366a41be05dbedee5cd84a1222a727a02a1b93
ms.sourcegitcommit: 74911a263944f2dbd9b754415ccda6c68dae0759
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71071470"
---
# <a name="create-a-custom-role-in-intune"></a>Intune 'da özel bir rol oluşturma

Belirli bir iş işlevi için gerekli izinleri içeren özel bir Intune rolü oluşturabilirsiniz. Örneğin bir BT departmanı grubu, uygulamaları, ilkeleri ve yapılandırma profillerini yönetiyorsa tüm bu izinleri tek bir özel role ekleyebilirsiniz. Özel bir rol oluşturduktan sonra, bu izinlere ihtiyacı olan tüm kullanıcılara [atayabilirsiniz](assign-role.md) .

Rolleri oluşturmak, düzenlemek ve atamak için, hesabınızın Azure AD’de aşağıdaki izinlerden birine sahip olması gerekir:
- **Genel Yönetici**
- **Intune Hizmet Yöneticisi**

## <a name="to-create-a-custom-role"></a>Özel bir rol oluşturmak için

1. [Azure portalında](https://portal.azure.com) Intune kimlik bilgilerinizle oturum açın.

2. Soldaki menüden **Tüm hizmetler**’i seçtikten sonra metin kutusu filtresine **Intune** yazın.

3. **Intune** **rolleri tüm roller**Ekle ' yiseçin. >  >  > 

4. **Özel Rol Ekle** dikey penceresinde yeni rol için ad ve açıklama girin, ardından **İzinler**'e tıklayın.

5. **İzinler** dikey penceresinde, bu rolle birlikte kullanmak istediğiniz izinleri seçin. Hangi izinleri uygulamak istediğinize karar vermenize yardımcı olması için [Intune RBAC tablosunu](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) kullanın.

6. **Kapsam (Etiketler)** dikey penceresinde bu rolün etiketlerini seçin. Bu rol, bu etiketlerin de bulunduğu kaynaklara erişebilir.

7. İşiniz bittiğinde **Tamam**’ı seçin.

8. **Özel Rol Ekle** dikey penceresinde **Oluştur**’a tıklayın. Yeni rol, **Intune rolleri-tüm roller** dikey penceresinde listede görüntülenir.

## <a name="next-steps"></a>Sonraki adımlar
- [Bir kullanıcıya rol atama](assign-role.md)
- [Intune 'da rol tabanlı erişim denetimi hakkında daha fazla bilgi edinin](role-based-access-control.md)
