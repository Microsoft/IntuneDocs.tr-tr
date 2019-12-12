---
title: Microsoft Intune ile rol tabanlı erişim denetimi (RBAC)
description: RBAC 'in kimlerin eylem gerçekleştirebilen ve Microsoft Intune değişiklik yapabileceğinizi denetlemenize nasıl olanak sağladığını öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: pjain
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4a03366037f9b0eced70f0375b3f4b39401e3141
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72509815"
---
# <a name="role-based-access-control-rbac-with-microsoft-intune"></a>Microsoft Intune ile rol tabanlı erişim denetimi (RBAC)

Rol tabanlı erişim denetimi (RBAC), kuruluşunuzun Kaynaklarına kimlerin erişebileceğini ve bu kaynaklarla neler yapabileceğini yönetmenize yardımcı olur.  Intune kullanıcılarınıza [roller atayarak](assign-role.md) , neleri görebileceğini ve değiştirebileceklerini sınırlayabilirsiniz. Her rolün, bu role sahip kullanıcıların kuruluşunuzda ne şekilde erişebileceğini ve değiştirebileceklerini tespit eden bir izinler kümesi vardır.

Rolleri oluşturmak, düzenlemek ve atamak için, hesabınızın Azure AD’de aşağıdaki izinlerden birine sahip olması gerekir:
- **Genel Yönetici**
- **Intune Hizmet Yöneticisi** ( **Intune Yöneticisi**olarak da bilinir)

Intune RBAC hakkında öneri ve öneriler için, örnekleri ve izlenecek yolları gösteren bu beş video serisine bakabilirsiniz: [1](https://www.youtube.com/watch?v=5deXLMLcnKY), [2](https://www.youtube.com/watch?v=38dnMBLuxbQ), [3](https://www.youtube.com/watch?v=6vqg9cAkMbY), [4](https://www.youtube.com/watch?v=5yOLajFFMHE), [5](https://www.youtube.com/watch?v=P5DDvsSF4Wk).

## <a name="roles"></a>Roller
Rol, bu role atanan kullanıcılara verilen izin kümesini tanımlar.
Hem yerleşik hem de özel rolleri kullanabilirsiniz. Yerleşik roller bazı yaygın Intune senaryolarını kapsar. İhtiyaç duyduğunuz tam izinler kümesiyle [kendi özel rollerinizi oluşturabilirsiniz](create-custom-role.md) . Çeşitli Azure Active Directory rollerinin Intune izinleri vardır.
Bir rolü görmek için **ıntune** > **Roller** > **tüm roller** ' i seçin > bir rol seçin. Aşağıdaki sayfaları görürsünüz:

- **Özellikler**: rolün adı, açıklaması, türü, atamaları ve kapsam etiketleri. 
- **İzinler**: rolün hangi izinlere sahip olduğunu tanımlayan uzun bir geçiş kümesini listeler.
- **Atamalar**: hangi kullanıcıların/cihazlara erişimi olduğunu tanımlayan [rol atamalarının]( assign-role.md) bir listesi. Bir rol birden çok atamalara sahip olabilir ve bir Kullanıcı birden çok atama içinde olabilir.

### <a name="built-in-roles"></a>Yerleşik roller
Daha fazla yapılandırma olmadan, gruplara yerleşik roller atayabilirsiniz. Yerleşik bir rolün adını, açıklamasını, türünü veya izinlerini silemez veya düzenleyemezsiniz.

- **Yardım Masası Operatörü**: Kullanıcılar ve cihazlar üzerinde uzak görevler gerçekleştirir, kullanıcılara ve cihazlara uygulama veya ilke atayabilir.
- **İlke ve Profil Yöneticisi**: Uyumluluk ilkesini, yapılandırma profillerini, Apple kaydını, kurumsal cihaz tanımlayıcılarını ve güvenlik temellerini yönetir.
- **Salt Okuma Operatörü**: Kullanıcı, cihaz, kayıt, yapılandırma ve uygulama bilgilerini görüntüler. Intune üzerinde değişiklik yapılamıyor.
- **Uygulama Yöneticisi**: Mobil uygulamalar ve yönetilen uygulamaları yönetir, cihaz bilgilerini okuyabilir ve cihaz yapılandırma profillerini görüntüleyebilir.
- **Intune rol yöneticisi**: özel Intune rollerini yönetir ve yerleşik Intune rolleri için Atamalar ekler. Bu, yöneticilere izin atayabilecek tek Intune rolüdür.
- **Okul yöneticisi**: [eğitim için Intune](../introduction-intune-education.md)Windows 10 cihazlarını yönetir.

### <a name="custom-roles"></a>Özel roller
Özel izinlerle kendi rollerinizi oluşturabilirsiniz. Özel roller hakkında daha fazla bilgi için bkz. [özel rol oluşturma](create-custom-role.md).

### <a name="azure-active-directory-roles-with-intune-access"></a>Intune erişimi olan Azure Active Directory rolleri
| Azure Active Directory rolü | Tüm Intune verileri | Intune denetim verileri |
| --- | :---: | :---: |
| Genel Yönetici | Okuma/yazma | Okuma/yazma |
| Intune Hizmet Yöneticisi | Okuma/yazma | Okuma/yazma |
| Koşullu Erişim Yöneticisi | Yok. | Yok. |
| Güvenlik Yöneticisi | Salt okunur | Salt okunur |
| Güvenlik operatörü | Salt okunur | Salt okunur |
| Güvenlik Okuyucusu | Salt okunur | Salt okunur |
| Uyumluluk Yöneticisi | Yok. | Salt okunur |
| Uyumluluk verileri Yöneticisi | Yok. | Salt okunur |
| Genel okuyucu | Salt Okunur | Salt Okunur |

> [!TIP]
> Intune, Azure AD RBAC ile denetlenen üç Azure AD uzantısını da gösterir: **Kullanıcılar**, **gruplar**ve **koşullu erişim**. Bunlara ek olarak, **Kullanıcı Hesabı Yöneticisi** yalnızca AAD kullanıcısı/grubu etkinliklerini gerçekleştirir ve Intune'daki tüm etkinlikleri gerçekleştirme izinlerinin tümüne sahip değildir. Daha fazla bilgi için bkz. [Azure AD Ile RBAC](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles).
### <a name="roles-created-in-the-intune-classic-portal"></a>Klasik Intune portalında oluşturulan roller
Yalnızca “Tam” izinlere sahip Intune **Hizmet Yöneticileri** kullanıcıları, klasik Intune portalından Azure portalında Intune’a geçirilir. Intune **hizmet yöneticileri** kullanıcılarını, Azure Portal Intune rollerine "salt okunurdur" veya "yardım masası" erişimiyle yeniden atamanız ve klasik portaldan kaldırmanız gerekir.
> [!IMPORTANT]
> Yöneticilerinizin Intune kullanarak bilgisayarları yönetmek için hala erişime ihtiyacı varsa, klasik portalda Intune Hizmet Yöneticisi erişimini saklamanız gerekebilir.

## <a name="role-assignments"></a>Rol atamaları
Rol ataması şunları tanımlar:

- role atanan kullanıcılar
- hangi kaynakları görebileceklerini
- değiştirebilecekleri kaynaklar.

Kullanıcılarınıza hem özel hem de yerleşik roller atayabilirsiniz. Bir Intune rolü atamak için kullanıcının bir Intune lisansı olması gerekir.
Rol atamasını görmek için **ıntune** > **Roller** > **tüm roller** ' i seçin > bir rol seçin > bir atama seçin. Aşağıdaki sayfaları görürsünüz:

- **Özellikler**: atamanın adı, açıklaması, rolü, üyeleri, kapsamları ve etiketleri.
- **Üyeler**: listelenen Azure güvenlik gruplarındaki tüm kullanıcıların, kapsam (gruplar) bölümünde listelenen kullanıcıları/cihazları yönetme izni vardır.
- **Kapsam (gruplar)** : Bu Azure güvenlik gruplarındaki tüm kullanıcılar/cihazlar, üyelerdeki kullanıcılar tarafından yönetilebilir.
- **[Kapsam (Etiketler)](scope-tags.md)** : üyelerdeki kullanıcılar aynı kapsam etiketlerine sahip kaynakları görebilirler.

### <a name="multiple-role-assignments"></a>Çoklu rol atamaları
Bir kullanıcının birden fazla rol ataması, izinleri ve kapsam etiketi varsa, bu rol atamaları aşağıdaki gibi farklı nesnelere genişletilir:

- İzinleri ve kapsam etiketlerini ata yalnızca söz konusu rolün atama kapsamındaki nesneler (ilkeler veya uygulamalar gibi) için geçerlidir (gruplar). Farklı atama özel olarak kendisine izin vermediği takdirde, atama izinleri ve kapsam etiketleri diğer rol atamalarındaki nesnelere uygulanmaz.
- Diğer izinler (örneğin, oluşturma, okuma, güncelleştirme, silme) ve kapsam etiketleri, Kullanıcı atamalarının hiçbirinde aynı türdeki (tüm ilkeler veya tüm uygulamalar gibi) tüm nesneler için geçerlidir.
- Farklı türlerde nesneler için izinler ve kapsam etiketleri (ilkeler veya uygulamalar gibi), birbirlerine uygulanmaz. Bir ilke için okuma izni, örneğin, Kullanıcı atamalarındaki uygulamalar için okuma izni sağlamaz.

## <a name="next-steps"></a>Sonraki adımlar
- [Bir kullanıcıya rol atama](assign-role.md)
- [Özel bir rol oluşturma](create-custom-role.md)
