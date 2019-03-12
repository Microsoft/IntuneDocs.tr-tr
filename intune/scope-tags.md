---
title: Microsoft Intune - Azure’da ilkeleri kapsam etiketleriyle filtreleme | Microsoft Docs
description: Yapılandırma profillerini belirli rollere filtrelemek için kapsam etiketlerini kullanın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/08/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: bca2d52bb47a149c6a36bc1b8cbc4d65e50c0f4c
ms.sourcegitcommit: 3abc3bb93a95a81154146325c26c119a784e7487
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57756811"
---
# <a name="use-rbac-and-scope-tags-for-distributed-it"></a>Dağıtılmış için RBAC ve kapsam etiketleri kullanmak BT

Doğru yöneticileri sağ Intune nesnelere görünürlüğü ve doğru erişime sahip olduğunuzdan emin olmak için rol tabanlı erişim denetimi (RBAC) ve kapsam etiketleri kullanabilirsiniz. Rollerini belirleme hangi erişim yöneticileri, hangi nesnelere sahip. Kapsam etiketleri, yöneticilerin görebileceğini hangi nesneleri belirler.

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
- Bir yönetici Intune nesneyi oluşturduğunda, o yönetici için atanan tüm kapsam etiketleri otomatik olarak yeni nesneye atanır.
- Intune RBAC, Azure Active Directory rolleri için geçerli değildir. Bu nedenle, Intune'daki hizmet yöneticilerinin ve genel yöneticileri rolleri, sahip oldukları hangi kapsam etiketleri ne olursa olsun tam yönetici erişimi ıntune sahiptir.
- Bir rol ataması kapsam etiketleri ile yöneticiler Intune nesneleriyle hiçbir kapsam etiketleri de görebilirsiniz.
- Rol atamalarınızı olması bir kapsam etiketi yalnızca atayabilirsiniz.
- Rol atamalarınızı kapsam (gruplar) içinde listelenen hedef grupları kullanabilirsiniz.
- Rolünüz için atanan bir kapsam etiketi varsa, Intune nesne üzerindeki tüm kapsam etiketleri silemezsiniz. En az bir kapsam etiketi gereklidir.
- Bir kullanıcının birden çok rol atamaları varsa, bu rol atamaları izinleri gibi farklı nesnelere genişletin:
    - Atama izinleri yalnızca geçerli nesnelerine (örneğin, ilke veya uygulamalar) Bu rol ataması kapsam (gruplar). Atama izinleri uygulanmaz diğer rol atamaları nesnelerine sürece diğer atamayı özellikle bunları verir.
    - (Oluştur ve okuma) gibi diğer izinler geçerlidir (örneğin, tüm ilkeleri veya tüm uygulamalar) aynı türdeki tüm nesneler için herhangi bir kullanıcının atamaları.
    - (İlke veya uygulamalar) gibi farklı türde nesneler için izinleri uygulanmaz arasındaki ilişki. Okuma izni için bir ilke, örneğin, bir kullanıcının atamaları uygulamalar için okuma izni sağlamaz.





## <a name="next-steps"></a>Sonraki adımlar

[Rollerinizi](role-based-access-control.md) ve [profillerinizi](device-profile-assign.md) yönetin.
