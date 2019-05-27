---
title: Microsoft Intune - Azure’da ilkeleri kapsam etiketleriyle filtreleme | Microsoft Docs
description: Yapılandırma profillerini belirli rollere filtrelemek için kapsam etiketlerini kullanın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/08/2019
ms.topic: article
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 57a14e1e3c4caea570667096fec71cecf2d88ddf
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66045186"
---
# <a name="use-role-based-access-control-rbac-and-scope-tags-for-distributed-it"></a>Dağıtılmış için rol tabanlı erişim denetimi (RBAC) ve kapsam etiketleri kullanmak BT

Doğru yöneticileri sağ Intune nesnelere görünürlüğü ve doğru erişime sahip olduğunuzdan emin olmak için rol tabanlı erişim denetimi ve kapsam etiketleri kullanabilirsiniz. Rollerini belirleme hangi erişim yöneticileri, hangi nesnelere sahip. Kapsam etiketleri, yöneticilerin görebileceğini hangi nesneleri belirler.

Örneğin, bir Seattle bölgesel office yönetim ilke ve Profil Yöneticisi rolü atanır varsayalım. Bu yönetici görebilir ve yalnızca profilleri ve yalnızca Seattle cihazlar için geçerli olan ilkeleri yönetmek için kullanmanız gerekir. Bunu yapmak için yaptığınız:

1. Seattle adlı bir kapsam etiketi oluşturun.
2. Bir rol ataması ilke ve Profil Yöneticisi rolü için oluşturun: 
    - Üyeler (gruplar) = Seattle BT yöneticilerinin adlı bir güvenlik grubu. Bu gruptaki tüm Yöneticiler, ilkeler ve Profiller kapsam (gruplar) kullanıcıları/cihazları için Yönetme iznine sahip olur.
    - Kapsam (gruplar) = bir güvenlik grubu adlı Seattle kullanıcılar. Bu gruptaki tüm kullanıcılara/cihazlara kendi profilleri ve ilkeleri admins üyeler (gruplar) tarafından yönetilen olabilir. 
    - Kapsam (etiketler) Seattle =. (Gruplar) üye Admins, Seattle kapsam etiketi de cihazları görebilirsiniz.
3. Üyeler (gruplar) erişebilmesi için yöneticilerin istediğiniz profilleri ve ilkeleri Seattle kapsam etiketi ekleyin.
4. Üyeler (gruplar) admins görünür istediğiniz cihazlara Seattle kapsam etiketi ekleyin. 


## <a name="to-create-a-scope-tag"></a>Kapsam etiketi oluşturmak için

1. Intune'da, **rolleri** > **kapsam (etiketler)** > **Oluştur**.

    ![Kapsam etiketi oluştur ekran görüntüsü.](./media/scope-tags/create-scope-tag.png)

2. Bir **Ad** ve **Açıklama** sağlayın.
3. **Oluştur**’u seçin.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Kapsam etiketini bir role atamak için

1. Intune'da, **rolleri** > **tüm rolleri** > bir rol seçin > **atamaları** > **atama**.

    ![Ekran görüntüsü, bir role kapsam atayın.](./media/scope-tags/assign-scope-to-role.png)

2. Sağlayan bir **atama adı** ve **açıklama**.
3. Seçin **üyeler (gruplar)** > **Ekle** > Bu atama bir parçası olarak istediğiniz grupları seçin > **seçin**  >   **Tamam**. Bu gruptaki mUsers ilkeler ve profiller için kapsam (gruplar) kullanıcıları/cihazları yönetmek için izinlere sahip.

    ![Seçili üye grupların ekran görüntüsü.](./media/scope-tags/select-member-groups.png)

4. Kullanıcılar/Gruplar belirli bir dizi cihazları yönetmek istiyorsanız belirleyin **kapsam (gruplar)** > **seçtiğiniz grupları** > **dahiledilecekgruplarıseçin**> istediğiniz grupları seçin > **seçin** > **Tamam**. Bu gruptaki tüm kullanıcılara/cihazlara, profilleri ve ilkeleri (grubu) üye yöneticileri tarafından yönetiliyor olabilir.

    ![Select kapsam gruplarının ekran görüntüsü.](./media/scope-tags/select-scope-groups.png)

    Alternatif olarak, seçebileceğiniz **tüm cihazlar**, **tüm kullanıcılar**, veya **tüm kullanıcılar ve tüm cihazlar**.

    ![Diğer seçenekleri Seç Kapsam grupları için ekran görüntüsü.](./media/scope-tags/scope-group-other-options.png)
    
5. Seçin **kapsam (etiketler)** > **Ekle** > Bu role eklemek istediğiniz etiketleri seçin > **seçin** > **Tamam**. Üyeler (gruplar) kullanıcılar aynı kapsam etiketi de profilleri ve ilkeleri erişebilir.

    ![Select kapsam etiketleri ekran görüntüsü.](./media/scope-tags/select-scope-tags.png)

6. **Tamam**’ı seçin. 

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Kapsam etiketini bir yapılandırma profiline eklemek için
1. Intune'da, **cihaz Yapılandırması** > **profilleri** > bir profil seçin.

    ![Ekran görüntüsü profili seçin.](./media/scope-tags/choose-profile.png)

2. Seçin **özellikleri** > **kapsam (etiketler)** > **ekleme**.

    ![Kapsam etiketleri Ekle ekran görüntüsü.](./media/scope-tags/add-scope-tags.png)

3. Altında **etiketleri seçin**, profiline eklemek istediğiniz etiketleri seçin.
4. Seçin **seçin** > **Tamam** > **Kaydet**.

## <a name="to-assign-a-scope-tag-to-an-app-configuration-policy"></a>Bir uygulama yapılandırma ilkesi için bir kapsam etiketi atamak için
İle cihazları için **cihaz kayıt türü** kümesine **yönetilen cihazlar**:
1. Seçin **istemci uygulamaları** > **uygulama yapılandırma ilkeleri** > Uygulama yapılandırma ilkesi seçin.
2. Seçin **özellikleri** > **kapsam (etiketler)** > ilkeyi atamak istediğiniz etiketleri seçin.

İle cihazları için **cihaz kayıt türü** kümesine **yönetilen uygulamalar**:
1. Seçin **istemci uygulamaları** > **uygulama yapılandırma ilkeleri** > Uygulama yapılandırma ilkesi seçin.
2. Seçin **kapsam (etiketler)** > ilkeyi atamak istediğiniz etiketleri seçin.


## <a name="to-assign-a-scope-tag-to-an-ios-app-provisioning-profile"></a>Bir iOS uygulama sağlama profili bir kapsam etiketi atamak için
1. Intune'da, **istemci uygulamaları** > **iOS uygulama sağlama profilleri** > bir profil seçin.
2. Seçin **özellikleri** > **kapsam (etiketler)** > Profil atamak istediğiniz etiketleri seçin.
3. Seçin **seçin** > **Tamam** > **Kaydet**.

## <a name="to-assign-a-scope-tag-to-an-apple-volume-purchase-program-vpp-token"></a>Kapsam etiketi için bir Apple Volume Purchase Program (VPP) belirtecini atamak için
1. Intune'da, **istemci uygulamaları** > **Apple VPP belirteçleri** > bir VPP belirteci seçin.
2. Seçin **kapsam (etiketler)** > Profil atamak istediğiniz etiketleri seçin. VPP uygulamaları ve e-Kitaplar VPP belirteciyle ilişkilendirilmiş atanmış etiketler devralır.
3. Seçin **seçin** > **Tamam** > **Kaydet**.

## <a name="scope-tag-details"></a>Kapsam etiketi ayrıntıları
Kapsam etiketleri ile çalışırken, bu ayrıntıları unutmayın:

- Kapsam etiketleri şu anda atayabilirsiniz:
    - Rol atamaları
    - Cihaz uyumluluğu ilkeleri
    - Cihaz yapılandırma profilleri
    - Windows 10 güncelleştirme halkaları
    - Yönetilen cihazlar
    - Uygulamalar
    - Uygulama yapılandırma ilkeleri – yönetilen cihazlar
    - PowerShell betikleri
    - DEP belirteçleri
    - iOS uygulama sağlama profili
    - Volume Purchase Program (VPP) belirteçleri
- Bir yönetici Intune nesneyi oluşturduğunda, o yönetici için atanan tüm kapsam etiketleri otomatik olarak yeni nesneye atanır.
- Intune RBAC, Azure Active Directory rolleri için geçerli değildir. Bu nedenle, Intune'daki hizmet yöneticilerinin ve genel yöneticileri rolleri, sahip oldukları hangi kapsam etiketleri ne olursa olsun tam yönetici erişimi ıntune sahiptir.
- Bir rol ataması kapsam etiketleri ile yöneticiler Intune nesneleriyle hiçbir kapsam etiketleri de görebilirsiniz.
- Rol atamalarınızı olması bir kapsam etiketi yalnızca atayabilirsiniz.
- Rol atamalarınızı kapsam (gruplar) içinde listelenen hedef grupları kullanabilirsiniz.
- Rolünüz için atanan bir kapsam etiketi varsa, Intune nesne üzerindeki tüm kapsam etiketleri silemezsiniz. En az bir kapsam etiketi gereklidir.

## <a name="next-steps"></a>Sonraki adımlar

[Rollerinizi](role-based-access-control.md) ve [profillerinizi](device-profile-assign.md) yönetin.
