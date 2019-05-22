---
title: Microsoft Intune ile rol tabanlı erişim denetimi (RBAC)
description: RBAC, nasıl sağladığını öğrenin kimlerin eylem gerçekleştirebileceğini ve Intune değişiklikleri yapın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 895b358760775b1021e545b271acb7ced7fa7b1d
ms.sourcegitcommit: ac3fe7504e58c74495a560a68eae2b784a4f7d46
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/20/2019
ms.locfileid: "65942075"
---
# <a name="role-based-access-control-rbac-with-microsoft-intune"></a>Microsoft Intune ile rol tabanlı erişim denetimi (RBAC)

Rol tabanlı erişim denetimi (RBAC) yönetmenize, kuruluşunuzun kaynakları ve bu kaynaklarla ne yapabileceklerini erişimi olan yardımcı olur.  Tarafından [rol atama](assign-role.md) Intune kullanıcılarınıza ne bunlar bkz değiştirmek ve sınırlayabilirsiniz. Her rolün ne Bu roldeki kullanıcıların erişebileceğini belirlemesine izin ve kuruluşunuz içindeki değişiklik kümesi vardır.

Rolleri oluşturmak, düzenlemek ve atamak için, hesabınızın Azure AD’de aşağıdaki izinlerden birine sahip olması gerekir:
- **Genel Yönetici**
- **Intune Hizmet Yöneticisi** (diğer adıyla **Intune yönetici**)

## <a name="roles"></a>Roller
Bir rol, bu role atanan kullanıcılar için izinler kümesini tanımlar.
Yerleşik ve özel rollerin kullanabilirsiniz. Yerleşik roller, bazı yaygın Intune senaryolarını kapsayan. Yapabilecekleriniz [kendi özel roller oluşturma](create-custom-role.md) , ihtiyacı olan izinlerin tam kümesi. Çeşitli Azure Active Directory rolleri Intune izinlere sahip olursunuz.
Bir rol görmek için **Intune** > **rolleri** > **tüm rolleri** > bir rol seçin. Aşağıdaki sayfaları görürsünüz:

-   **Özellikler**: Adı, açıklamayı, türü, atamalarını ve rolün kapsamı etiketleri. 
-   **İzinleri**: Uzun bir role sahip hangi izinleri tanımlama değiştirir kümesini listeler.
-   **Atamalar**: Listesini [rol atamaları]( assign-role.md) hangi kullanıcıların hangi kullanıcılara/cihazlara erişimi tanımlama. Rol atamaları birden çok olabilir ve bir kullanıcı birden çok atamalarını olabilir.

### <a name="built-in-roles"></a>Yerleşik roller
Daha fazla yapılandırma olmadan grupları için yerleşik roller atayabilirsiniz. Silemez veya adı, açıklama, tür veya yerleşik bir rol izinlerini düzenleyin. Yerleşik her rol için izinlerini tam bir listesi için bkz. [Intune RBAC tablosu](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a).

- **Yardım Masası operatörü**: Kullanıcılar ve cihazlar üzerinde uzak görevler gerçekleştirir ve kullanıcılara veya cihazlara uygulama veya ilke atayabilirsiniz.
- **İlke ve Profil Yöneticisi**: Uyumluluk İlkesi, yapılandırma profillerini, Apple kayıt, Kurumsal cihaz tanımlayıcıları ve güvenlik temellerini yönetir.
- **Salt okunur operatör**: Görünümleri kullanıcı, cihaz, kayıt, yapılandırma ve uygulama bilgileri. Intune'da değişiklik yapamaz.
- **Uygulama Yöneticisi**: Mobil ve yönetilen uygulamaları yönetir, cihaz bilgilerini okuyabilir ve cihaz yapılandırma profillerini görüntüleyebilirsiniz.
- **Intune Rol Yöneticisi**: Özel Intune rolleri yönetir ve yerleşik Intune rol atamalarını ekler. Bu, yöneticilere izin atamanıza yalnızca Intune rolüdür.
- **Okul Yöneticisi**: Windows 10 cihazları yönetir [eğitim için Intune](introduction-intune-education.md).

### <a name="custom-roles"></a>Özel roller
Özel izinlerle kendi rollerinizi oluşturabilirsiniz. Özel roller hakkında daha fazla bilgi için bkz: [özel bir rol oluşturun](create-custom-role.md).

### <a name="azure-active-directory-roles-with-intune-access"></a>Intune erişimi olan Azure Active Directory rolleri
| Azure Active Directory rol | Tüm Intune verileri | Intune denetim verileri |
| --- | :---: | :---: |
| Genel Yönetici | Okuma/yazma | Okuma/yazma |
| Intune Hizmet Yöneticisi | Okuma/yazma | Okuma/yazma |
| Koşullu Erişim Yöneticisi | None | Yok. |
| Güvenlik Yöneticisi | Salt okunur | Salt okunur |
| Güvenlik işleci | Salt okunur | Salt okunur |
| Güvenlik okuyucusu | Salt okunur | Salt okunur |
| Uyumluluk Yöneticisi | Yok. | Salt okunur |
| Uyumluluk veri Yöneticisi | None | Salt okunur |

> [!TIP]
> Intune ayrıca üç Azure AD uzantısı gösterir: **Kullanıcılar**, **grupları**, ve **koşullu erişim**, olmak üzere Azure AD RBAC ile denetlenen. Bunlara ek olarak, **Kullanıcı Hesabı Yöneticisi** yalnızca AAD kullanıcısı/grubu etkinliklerini gerçekleştirir ve Intune'daki tüm etkinlikleri gerçekleştirme izinlerinin tümüne sahip değildir. Daha fazla bilgi için [Azure AD ile RBAC](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles).
### <a name="roles-created-in-the-intune-classic-portal"></a>Klasik Intune portalında oluşturulan roller
Yalnızca “Tam” izinlere sahip Intune **Hizmet Yöneticileri** kullanıcıları, klasik Intune portalından Azure portalında Intune’a geçirilir. Intune atamalıdır **hizmet yöneticileri** "Salt okunur" veya "Yardım Masası" olan kullanıcılar Azure portalında Intune rollerine erişme ve bunları Klasik portaldan kaldırmanız.
> [!IMPORTANT]
> Yöneticilerinizin bilgisayarları Intune kullanarak yönetmek için erişim yine de gerekliyse Klasik portalda Intune Hizmet Yöneticisi erişimini tutmanız gerekebilir.

## <a name="role-assignments"></a>Rol atamaları
Bir rol ataması tanımlar:

- hangi kullanıcı rolüne atanan
- hangi kaynakların görebilir
- hangi kaynakların bunlar değiştirebilirsiniz.

Kullanıcılarınız için özel ve yerleşik roller atayabilirsiniz. Bir Intune rolü atanmış için kullanıcının bir Intune lisansı olması gerekir.
Bir rol ataması görmek için **Intune** > **rolleri** > **tüm rolleri** > bir rol seçin > ataması seçin. Aşağıdaki sayfaları görürsünüz:

-   **Özellikler**: Ad, açıklama, rol, üye, kapsamları ve etiketler atama.
-   **Üyeleri**: Listelenen gruplarındaki tüm kullanıcılar, kapsam (gruplar) listelenen kullanıcıları/cihazları yönetmek için izne sahip.
-   **Kapsam (gruplar)**: Tüm kullanıcılara/cihazlara bu gruplardaki kullanıcılar üyeleri tarafından yönetilebilir.
-   **[Kapsam (etiketler)](scope-tags.md)**: Kullanıcıların üye aynı kapsam etikete sahip kaynakları görebilirsiniz.

### <a name="multiple-role-assignments"></a>Birden çok rol atamaları
Bir kullanıcının birden çok rol atamaları varsa, bu rol atamaları izinleri gibi farklı nesnelere genişletin:

- Atama izinleri yalnızca geçerli nesnelerine (örneğin, ilke veya uygulamalar) Bu rol ataması kapsam (gruplar). Atama izinleri uygulanmaz diğer rol atamaları nesnelerine sürece diğer atamayı özellikle bunları verir.
- (Oluştur ve okuma) gibi diğer izinler geçerlidir (örneğin, tüm ilkeleri veya tüm uygulamalar) aynı türdeki tüm nesneler için herhangi bir kullanıcının atamaları.
- (İlke veya uygulamalar) gibi farklı türde nesneler için izinleri uygulanmaz arasındaki ilişki. Okuma izni için bir ilke, örneğin, bir kullanıcının atamaları uygulamalar için okuma izni sağlamaz.

## <a name="next-steps"></a>Sonraki adımlar
- [Bir kullanıcıya rol atama](assign-role.md)
- [Özel rol oluşturma](create-custom-role.md)
