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
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: pjain
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 68c2dc7df123593513c14e16e2626c7426f50b01
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207426"
---
# <a name="create-a-custom-role-in-intune"></a>Intune 'da özel bir rol oluşturma

Belirli bir iş işlevi için gerekli izinleri içeren özel bir Intune rolü oluşturabilirsiniz. Örneğin bir BT departmanı grubu, uygulamaları, ilkeleri ve yapılandırma profillerini yönetiyorsa tüm bu izinleri tek bir özel role ekleyebilirsiniz. Özel bir rol oluşturduktan sonra, bu izinlere ihtiyacı olan tüm kullanıcılara [atayabilirsiniz](assign-role.md) .

Rolleri oluşturmak, düzenlemek ve atamak için, hesabınızın Azure AD’de aşağıdaki izinlerden birine sahip olması gerekir:
- **Genel Yönetici**
- **Intune Hizmet Yöneticisi**

## <a name="to-create-a-custom-role"></a>Özel bir rol oluşturmak için

1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)'Nde, **Ekle** > **tüm roller** > **Roller** ' i seçin.

2. **Özel Rol Ekle** dikey penceresinde yeni rol için ad ve açıklama girin, ardından **İzinler**'e tıklayın.

3. **İzinler** dikey penceresinde, bu rolle birlikte kullanmak istediğiniz izinleri seçin.

4. **Kapsam (Etiketler)** dikey penceresinde bu rolün etiketlerini seçin. Bu rol, bu etiketlerin de bulunduğu kaynaklara erişebilir.

5. İşiniz bittiğinde **Tamam**’ı seçin.

6. **Özel Rol Ekle** dikey penceresinde **Oluştur**’a tıklayın. Yeni rol, **Intune rolleri-tüm roller** dikey penceresinde listede görüntülenir.


## <a name="copy-a-role"></a>Rolü kopyalama

Ayrıca, varolan bir rolü de kopyalayabilirsiniz.

1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)'Nde, **tüm roller** > **Roller** ' i seçin > listede bir rol seçin > **Yinele**' ye tıklayın.

2. **Yinelenen rol**altında bir ad girin. Benzersiz bir ad kullandığınızdan emin olun.

3. Özgün rolün tüm izinleri ve kapsam etiketleri zaten seçilmeyecektir. Daha sonra yinelenen rolün **adını**, **açıklamasını**, **izinlerini**ve **kapsamını (etiketleri)** değiştirebilirsiniz.

4. **Oluştur**’u seçin. 

## <a name="next-steps"></a>Sonraki adımlar
- [Bir kullanıcıya rol atama](assign-role.md)
- [Intune 'da rol tabanlı erişim denetimi hakkında daha fazla bilgi edinin](role-based-access-control.md)
