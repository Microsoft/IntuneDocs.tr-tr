---
title: Intune kullanıcısına rol atama
description: Microsoft Intune bir kullanıcıya yerleşik veya özel bir rol atamayı öğrenin.
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
ms.openlocfilehash: d9e337d47757e3c5507c94433f90d5c2863bc1b0
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72503017"
---
# <a name="assign-a-role-to-an-intune-user"></a>Intune kullanıcısına rol atama

Bir Intune kullanıcısına [yerleşik](role-based-access-control.md#built-in-roles) veya [özel](create-custom-role.md) bir rol atayabilirsiniz.

Rolleri oluşturmak, düzenlemek ve atamak için, hesabınızın Azure AD’de aşağıdaki izinlerden birine sahip olması gerekir:
- **Genel Yönetici**
- **Intune Hizmet Yöneticisi**

1. [Azure portalında](https://portal.azure.com) oturum açın.

2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.

3. **Intune** dikey penceresinde, **tüm roller** > **Roller** ' i seçin.

4. **Intune rolleri-tüm roller** dikey penceresinde, atamak istediğiniz yerleşik rolü seçin.

5. *Rol adı*>- **genel bakış** dikey penceresinde **Yönet** > **atamaları**' nı seçin.

6. Özel rol dikey penceresinde, **Ata**'yı seçin.

7. **Rol atamaları** dikey penceresinde atama Için bir **atama adı** ve isteğe bağlı **atama açıklaması** girin.

8. **Üyeler (gruplar)** için izinleri vermek istediğiniz kullanıcıyı içeren bir grup seçin.

9. **Kapsam (gruplar)** için, yukarıdaki üyenin yönetmesine izin verilecek kullanıcıları/cihazları içeren bir grup seçin.

10. **Kapsam (Etiketler)** için, bu rol atamasının uygulanacağı Etiketler ' i seçin.

11. İşiniz bittiğinde **Tamam**’ı seçin. Yeni atama, atamalar listesinde görüntülenir.


## <a name="next-steps"></a>Sonraki adımlar
- [Intune 'da rol tabanlı erişim denetimi hakkında daha fazla bilgi edinin](role-based-access-control.md)
- [Özel bir rol oluşturma](create-custom-role.md)
