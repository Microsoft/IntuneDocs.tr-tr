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
ms.openlocfilehash: bfa2758546595d1e6237d88e128958c50759eb04
ms.sourcegitcommit: 25e4847ead0f56c269cfefe1e01c1b9106a28cf1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78369814"
---
# <a name="create-a-custom-role-in-intune"></a>Intune 'da özel bir rol oluşturma

Belirli bir iş işlevi için gerekli izinleri içeren özel bir Intune rolü oluşturabilirsiniz. Örneğin bir BT departmanı grubu, uygulamaları, ilkeleri ve yapılandırma profillerini yönetiyorsa tüm bu izinleri tek bir özel role ekleyebilirsiniz. Özel bir rol oluşturduktan sonra, bu izinlere ihtiyacı olan tüm kullanıcılara [atayabilirsiniz](assign-role.md) .

Rolleri oluşturmak, düzenlemek ve atamak için, hesabınızın Azure AD’de aşağıdaki izinlerden birine sahip olması gerekir:
- **Genel Yönetici**
- **Intune Hizmet Yöneticisi**

## <a name="to-create-a-custom-role"></a>Özel bir rol oluşturmak için

1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)'Nde, **Oluştur** > **tüm roller** > **Kiracı Yönetimi** > **Roller** ' i seçin.

2. **Temel bilgiler** sayfasında, yeni rol için bir ad ve açıklama girin ve ardından **İleri**' yi seçin.

3. **İzinler** sayfasında, bu rolle birlikte kullanmak istediğiniz izinleri seçin.

4. **Kapsam (Etiketler)** sayfasında bu rolün etiketlerini seçin. Bu rol, bu etiketlerin de bulunduğu kaynaklara erişebilir. **İleri**’yi seçin.

5. **Gözden geçir + oluştur** sayfasında, Işiniz bittiğinde **Oluştur**' u seçin. Yeni rol, **Intune rolleri-tüm roller** dikey penceresinde listede görüntülenir.

## <a name="copy-a-role"></a>Rolü kopyalama

Ayrıca, varolan bir rolü de kopyalayabilirsiniz.

1. [Microsoft Uç Nokta Yöneticisi Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)'Nde, **tüm roller** > **Kiracı Yönetimi** > **rolleri** ' ni seçin > listedeki bir rolün onay kutusunu seçin > **yineleniyor**.

2. **Temel bilgiler** sayfasında, bir ad girin. Benzersiz bir ad kullandığınızdan emin olun.

3. Özgün rolün tüm izinleri ve kapsam etiketleri zaten seçilmeyecektir. Daha sonra yinelenen rolün **adını**, **açıklamasını**, **izinlerini**ve **kapsamını (etiketleri)** değiştirebilirsiniz.

4. İstediğiniz tüm değişiklikleri yaptıktan sonra, **gözden geçir + oluştur** sayfasına ulaşmak için **İleri** ' yi seçin. **Oluştur**’u seçin. 

## <a name="next-steps"></a>Sonraki adımlar
- [Bir kullanıcıya rol atama](assign-role.md)
- [Intune 'da rol tabanlı erişim denetimi hakkında daha fazla bilgi edinin](role-based-access-control.md)


