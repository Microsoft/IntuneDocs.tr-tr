---
title: Bir Intune kullanıcısı için rol atama
description: Bir kullanıcıya Microsoft Intune yerleşik veya özel bir rol atama hakkında bilgi edinin.
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
ms.openlocfilehash: a22fef1c04ae52a8a4cc65eaadc1ef6fcd524c19
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66043587"
---
# <a name="assign-a-role-to-an-intune-user"></a>Bir Intune kullanıcısı için rol atama

Atayabileceğiniz bir [yerleşik](role-based-access-control.md#built-in-roles) veya [özel](create-custom-role.md) bir Intune kullanıcı rolü.

Rolleri oluşturmak, düzenlemek ve atamak için, hesabınızın Azure AD’de aşağıdaki izinlerden birine sahip olması gerekir:
- **Genel Yönetici**
- **Intune Hizmet Yöneticisi**

Yerleşik her rol için izinlerini tam bir listesi için bkz. [Intune RBAC tablosu](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a).

1. [Azure portal](https://portal.azure.com) oturum açın.

2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.

3. Üzerinde **Intune** dikey penceresinde, seçin **rolleri** > **tüm rolleri**.

4. Üzerinde **Intune rolleri - tüm roller** dikey penceresinde, atamak istediğiniz yerleşik rolü seçin.

5. Üzerinde <*rol adı*>- **genel bakış** dikey penceresinde, seçin **Yönet** > **atamaları**.

6. Özel rol dikey penceresinde, **Ata**'yı seçin.

7. Üzerinde **rol atamaları** dikey penceresinde girin bir **atama adı** ve isteğe bağlı **atama açıklaması** atama.

8. İçin **üyeler (gruplar)**, izinleri vermek istediğiniz kullanıcıyı içeren grubu seçin.

9. İçin **kapsam (gruplar)**, yukarıda seçilen üyenin yönetmek için izin verilecek kullanıcıları/cihazları içeren bir grubu seçin.

10. İçin **kapsam (etiketler)**, bu rol ataması burada uygulanacak etiketleri seçin.

11. İşiniz bittiğinde **Tamam**’ı seçin. Yeni atama, atamalar listesinde görüntülenir.


## <a name="next-steps"></a>Sonraki adımlar
- [Intune rol tabanlı erişim denetimi hakkında daha fazla bilgi edinin](role-based-access-control.md)
- [Özel rol oluşturma](create-custom-role.md)
