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
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: pjain
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0539e4d12173ba2c7ba8d3af3364daf69ddbbf34
ms.sourcegitcommit: 74911a263944f2dbd9b754415ccda6c68dae0759
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71071541"
---
# <a name="assign-a-role-to-an-intune-user"></a>Intune kullanıcısına rol atama

Bir Intune kullanıcısına [yerleşik](role-based-access-control.md#built-in-roles) veya [özel](create-custom-role.md) bir rol atayabilirsiniz.

Rolleri oluşturmak, düzenlemek ve atamak için, hesabınızın Azure AD’de aşağıdaki izinlerden birine sahip olması gerekir:
- **Genel Yönetici**
- **Intune Hizmet Yöneticisi**

Yerleşik her rolün izinlerinin tam listesi için bkz. [ıNTUNE RBAC tablosu](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a).

1. [Azure portal](https://portal.azure.com) oturum açın.

2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.

3. **Intune** dikey penceresinde **Roller** > **tüm roller**' i seçin.

4. **Intune rolleri-tüm roller** dikey penceresinde, atamak istediğiniz yerleşik rolü seçin.

5. <*Rol adı*>- **genel bakış** dikey penceresinde,**atamaları** **Yönet** > ' i seçin.

6. Özel rol dikey penceresinde, **Ata**'yı seçin.

7. **Rol atamaları** dikey penceresinde atama Için bir **atama adı** ve isteğe bağlı **atama açıklaması** girin.

8. **Üyeler (gruplar)** için izinleri vermek istediğiniz kullanıcıyı içeren bir grup seçin.

9. **Kapsam (gruplar)** için, yukarıdaki üyenin yönetmesine izin verilecek kullanıcıları/cihazları içeren bir grup seçin.

10. **Kapsam (Etiketler)** için, bu rol atamasının uygulanacağı Etiketler ' i seçin.

11. İşiniz bittiğinde **Tamam**’ı seçin. Yeni atama, atamalar listesinde görüntülenir.


## <a name="next-steps"></a>Sonraki adımlar
- [Intune 'da rol tabanlı erişim denetimi hakkında daha fazla bilgi edinin](role-based-access-control.md)
- [Özel bir rol oluşturma](create-custom-role.md)
