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
ms.openlocfilehash: 0625968c4f0c30d125be73045a52b58a032b2fd7
ms.sourcegitcommit: a59c78c13c4ff68e8a56b69029adfe51704ba570
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57682632"
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
2. Bir **Ad** ve **Açıklama** sağlayın.
3. **Oluştur**’u seçin.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Kapsam etiketini bir role atamak için

1. Intune'da, **rolleri** > **tüm rolleri** > bir rol seçin > **atamaları** > **atama**.
2. Sağlayan bir **atama adı** ve **açıklama**.
3. Seçin **üyeler (gruplar)** ve bu atama bir parçası olarak istediğiniz grupları seçin. Bu gruptaki kullanıcılar, ilkeler ve profiller için kapsam (gruplar) kullanıcıları/cihazları yönetmek için izinlere sahip.
4. Seçin **kapsam (gruplar)** ve kullanıcıları ve bu atama parçası olmasını istediğiniz grupları seçin. Bu gruptaki tüm kullanıcılara/cihazlara, profilleri ve ilkeleri (grubu) üye yöneticileri tarafından yönetiliyor olabilir.
5. Seçin **kapsam (etiketler)** > **Ekle** > Bu role eklemek istediğiniz etiketleri seçin. Üyeler (gruplar) kullanıcılar aynı kapsam etiketi de profilleri ve ilkeleri erişebilir.
6. **Seç** > **Tamam** > **Tamam**'ı seçin. 

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Kapsam etiketini bir yapılandırma profiline eklemek için
1. Intune'da, **cihaz Yapılandırması** > **profilleri** > bir profili seçin > **özellikleri** > **kapsam (etiketler)**   >  **Ekleme**.
2. Altında **etiketleri seçin**, profiline eklemek istediğiniz etiketleri seçin.
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
