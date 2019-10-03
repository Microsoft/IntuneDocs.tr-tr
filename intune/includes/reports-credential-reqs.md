---
ms.openlocfilehash: 8483ed3d4198e228bdaaf4723b2c9c0dca9cecfc
ms.sourcegitcommit: fc356fd69beaeb3d69982b47e2bdffb6f7127f8c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2019
ms.locfileid: "71830500"
---
<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Azure AD ve Intune kimlik bilgisi gereksinimleri

Kimlik doğrulama ve yetkilendirme, Azure AD kimlik bilgilerini ve Intune rol tabanlı erişim denetimi 'ni (RBAC) temel alır. Kiracınız için tüm genel Yöneticiler ve Intune hizmet yöneticileri varsayılan olarak veri ambarına erişebilir. Intune **veri ambarı** kaynağına erişim izni vererek daha fazla kullanıcıya erişim sağlamak için Intune rollerini kullanın.

Intune veri ambarına (API dahil) erişim gereksinimleri şunlardır:

- Kullanıcı şunlardan biri olmalıdır:
  - Azure AD Genel Yöneticisi
  - Intune Hizmet Yöneticisi
  - **Intune veri ambarı** kaynağına rol tabanlı erişimi olan Kullanıcı
  - [Yalnızca uygulama kimlik doğrulaması](../developer/data-warehouse-app-only-auth.md) kullanan kullanıcı tarafından daha az kimlik doğrulama 
