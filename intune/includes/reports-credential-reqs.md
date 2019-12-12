---
ms.openlocfilehash: 8483ed3d4198e228bdaaf4723b2c9c0dca9cecfc
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "71830500"
---
<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Azure AD ve Intune kimlik bilgisi gereksinimleri

Kimlik doğrulaması ve yetkilendirme, Azure AD kimlik bilgileri ve Intune rol tabanlı erişim denetimine (RBAC) bağlıdır. Varsayılan olarak kiracınızdaki tüm genel yöneticiler ve Intune hizmet yöneticilerinin Veri ambarına erişimi vardır. Intune rolleri ile kullanıcılara **Intune veri ambarı** kaynağı erişimi vererek daha fazla kullanıcıya erişim sağlayabilirsiniz.

API dahil olmak üzere Intune Veri Ambarı’na erişim önkoşulları şöyledir:

- Kullanıcı şunlardan biri olmalıdır:
  - Azure AD genel yöneticisi
  - Intune hizmet yöneticisi
  - **Intune veri ambarı** kaynağına rol tabanlı erişimi olan kullanıcı
  - [Yalnızca uygulama kimlik doğrulaması](../developer/data-warehouse-app-only-auth.md) kullanılan kullanıcısız kimlik doğrulaması 
