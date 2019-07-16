---
ms.openlocfilehash: 6ec8f8a613d3b0a0b17f2615de634e70fa282fd7
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2019
ms.locfileid: "68229306"
---
<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Azure AD ve Intune kimlik bilgisi gereksinimleri

Kimlik doğrulaması ve yetkilendirme, Azure AD kimlik bilgileri ve Intune rol tabanlı erişim denetimine (RBAC) bağlıdır. Varsayılan olarak kiracınızdaki tüm genel yöneticiler ve Intune hizmet yöneticilerinin Veri ambarına erişimi vardır. Intune rolleri ile kullanıcılara **Intune veri ambarı** kaynağı erişimi vererek daha fazla kullanıcıya erişim sağlayabilirsiniz.

API dahil olmak üzere Intune Veri Ambarı’na erişim önkoşulları şöyledir:

- Kullanıcı şunlardan biri olmalıdır:
  - Azure AD genel yöneticisi
  - Intune hizmet yöneticisi
  - **Intune veri ambarı** kaynağına rol tabanlı erişimi olan kullanıcı
  - [Yalnızca uygulama kimlik doğrulaması](../data-warehouse-app-only-auth.md) kullanılan kullanıcısız kimlik doğrulaması 
