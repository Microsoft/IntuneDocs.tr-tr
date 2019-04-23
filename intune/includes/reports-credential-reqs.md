---
ms.openlocfilehash: 015e50d24149a6b6242eda86d5f3d62489e9955d
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61511354"
---
<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Azure AD ve Intune kimlik bilgisi gereksinimleri

Kimlik doğrulaması ve yetkilendirme, Azure AD kimlik bilgileri ve Intune rol tabanlı erişim denetimine (RBAC) bağlıdır. Varsayılan olarak kiracınızdaki tüm genel yöneticiler ve Intune hizmet yöneticilerinin Veri ambarına erişimi vardır. Intune rolleri ile kullanıcılara **Intune veri ambarı** kaynağı erişimi vererek daha fazla kullanıcıya erişim sağlayabilirsiniz.

API dahil olmak üzere Intune Veri Ambarı’na erişim önkoşulları şöyledir:

  -  Kullanıcı şunlardan biri olmalıdır:
      -  Azure AD genel yöneticisi
      -  Intune hizmet yöneticisi
      -  **Intune veri ambarı** kaynağına rol tabanlı erişimi olan kullanıcı
      -  [Yalnızca uygulama kimlik doğrulaması](../data-warehouse-app-only-auth.md) kullanılan kullanıcısız kimlik doğrulaması 
