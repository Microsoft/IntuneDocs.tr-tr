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
ms.openlocfilehash: 19fff092f7eccfc6de2a027c7834c52698176cbf
ms.sourcegitcommit: 5881979c45fc973cba382413eaa193d369b8dcf6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2020
ms.locfileid: "77569175"
---
# <a name="assign-a-role-to-an-intune-user"></a>Intune kullanıcısına rol atama

Bir Intune kullanıcısına [yerleşik](role-based-access-control.md#built-in-roles) veya [özel](create-custom-role.md) bir rol atayabilirsiniz.

Rolleri oluşturmak, düzenlemek ve atamak için, hesabınızın Azure AD’de aşağıdaki izinlerden birine sahip olması gerekir:
- **Genel Yönetici**
- **Intune Hizmet Yöneticisi**

1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)'Nde, **tüm roller** > , **Kiracı Yönetimi** > **Roller** ' i seçin.

2. **Intune rolleri-tüm roller** dikey penceresinde, **ata** > > **atamaları** atamak istediğiniz yerleşik rolü seçin.

5. **Temel bilgiler** sayfasında, bir **atama adı** ve isteğe bağlı **atama açıklaması**girin ve ardından **İleri**' yi seçin.

6. **Yönetici grupları** sayfasında, izinleri vermek istediğiniz kullanıcıyı içeren grubu seçin. **İleri**’yi seçin.

7. **Kapsam (gruplar)** sayfasında, yukarıdaki üyenin yönetmesine izin verilecek kullanıcıları/cihazları içeren bir grup seçin. **İleri**’yi seçin.

8. **Kapsam (Etiketler)** sayfasında, bu rol atamasının uygulanacağı Etiketler ' i seçin. **İleri**’yi seçin.

9. **Gözden geçir + oluştur** sayfasında, Işiniz bittiğinde **Oluştur**' u seçin. Yeni atama, atamalar listesinde görüntülenir.

## <a name="next-steps"></a>Sonraki adımlar
- [Intune 'da rol tabanlı erişim denetimi hakkında daha fazla bilgi edinin](role-based-access-control.md)
- [Özel bir rol oluşturma](create-custom-role.md)


