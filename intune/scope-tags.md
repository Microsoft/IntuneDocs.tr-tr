---
title: Intune 'da dağıtılan rol tabanlı erişim denetimi (RBAC) ve kapsam etiketlerini kullanma | Microsoft Docs
description: Yapılandırma profillerini belirli rollere filtrelemek için kapsam etiketlerini kullanın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/06/2019
ms.topic: article
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 90865b8a8881ab85089fb379a8398e276574b771
ms.sourcegitcommit: b78793ccbef2a644a759ca3110ea73e7ed6ceb8f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69550032"
---
# <a name="use-role-based-access-control-rbac-and-scope-tags-for-distributed-it"></a>Dağıtılmış BT için rol tabanlı erişim denetimi (RBAC) ve kapsam etiketleri kullanma

Doğru yöneticilerin doğru Intune nesnelerine doğru erişime ve görünürlüğe sahip olduğundan emin olmak için rol tabanlı erişim denetimi ve kapsam etiketlerini kullanabilirsiniz. Roller hangi erişim yöneticilerinin hangi nesnelere sahip olduğunu belirleyen roller. Kapsam etiketleri, yöneticilerin hangi nesneleri görebileceği belirlenir.

Örneğin, bir Seattle bölgesel Office yöneticisinin Ilke ve Profil Yöneticisi rolüne sahip olduğunu varsayalım. Bu yöneticinin yalnızca Seattle cihazları için uygulanan profilleri ve ilkeleri görmesini ve yönetmesini istiyorsunuz. Bu erişimi ayarlamak için şunları yapmanız gerekir:

1. Seattle adlı bir kapsam etiketi oluşturun.
2. Ilke ve Profil Yöneticisi rolü için şu ile bir rol ataması oluşturun: 
    - Üyeler (gruplar) = Seattle BT yöneticileri adlı bir güvenlik grubu. Bu gruptaki tüm yöneticilerin, kapsamdaki kullanıcılar/cihazlar için ilkeleri ve profilleri yönetme izni olacaktır (gruplar).
    - Kapsam (gruplar) = Seattle kullanıcıları adlı bir güvenlik grubu. Bu gruptaki tüm kullanıcıların/cihazların profilleri ve ilkeleri, Üyeler (gruplar) içindeki Yöneticiler tarafından yönetilebilir. 
    - Scope (Etiketler) = Seattle. Üyede (gruplar) bulunan Yöneticiler, Seattle Scope etiketine sahip olan Intune nesnelerini görebilir.
3. Üyeler (gruplar) içindeki yöneticilerin erişimine sahip olmasını istediğiniz ilkelere ve profillere Seattle kapsam etiketini ekleyin.
4. Üyeler (gruplar) içinde yöneticilere görünür olmasını istediğiniz cihazlara Seattle kapsam etiketini ekleyin. 

## <a name="default-scope-tag"></a>Varsayılan kapsam etiketi
Varsayılan kapsam etiketi, kapsam etiketlerini destekleyen tüm etiketlenmemiş nesnelere otomatik olarak eklenir.

Varsayılan kapsam etiketi özelliği, System Center Configuration Manager güvenlik kapsamları özelliğine benzer. 

## <a name="to-create-a-scope-tag"></a>Kapsam etiketi oluşturmak için

1. Intune 'da, **Roller** > **kapsam (Etiketler)**  > **Oluştur**' u seçin.

    ![Kapsam etiketi oluşturma ekranının ekran görüntüsü.](./media/scope-tags/create-scope-tag.png)

3. Belirli gruplardaki tüm cihazları istiyorsanız, **seçili gruplardaki tüm cihazlara kapsam etiketi ata**' yı seçin.
    1. **Dahil edilecek grupları seçin** sayfasında, bu kapsam etiketini atamak istediğiniz cihazları içeren grupları seçin.
    2. **Seç**’i seçin.
4. **Oluştur**’u seçin.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Kapsam etiketini bir role atamak için

1. Intune 'da **Roller** > **tüm roller** ' i seçin > bir rol seçin > **atama** > **ata**' yı seçin.

    ![Role kapsam atama ekran görüntüsü.](./media/scope-tags/assign-scope-to-role.png)

2. **Atama adı** ve **açıklaması**sağlayın.
3. **Üyeler (gruplar)**  > seçin > Bu atamanın parçası olarak istediğiniz grupları seçin > Tamam '**ı** **seçin** > . Bu gruptaki kullanıcıların, kapsamdaki kullanıcıları/cihazları yönetme izinleri olacaktır (gruplar).

    ![Üye gruplarının Seç ekran görüntüsü.](./media/scope-tags/select-member-groups.png)

4. Belirli bir grup kümesindeki kullanıcıları/cihazları yönetmek istiyorsanız **kapsam (gruplar)**  > **Seçili gruplar** > ' ı seçin.**dahil edilecek grupları seçin** > grupları seçin  >  **Tamam ' ı** **seçin**. Bu gruptaki tüm kullanıcılar/cihazlar, Üyeler (Grup) içindeki Yöneticiler tarafından yönetilecektir.

    ![Kapsam gruplarının Seç ekran görüntüsü.](./media/scope-tags/select-scope-groups.png)

    Alternatif olarak, tüm cihazlar, **tüm kullanıcılar**veya tüm **Kullanıcılar &** tüm cihazlar ' ı seçebilirsiniz.

    ![Seçim kapsam grupları için diğer seçeneklerin ekran görüntüsü.](./media/scope-tags/scope-group-other-options.png)
    
5. **Kapsam (Etiketler)**  > **Ekle** ' yi seçin > Bu role eklemek istediğiniz etiketleri seçin >**Tamam**' ı **seçin** > . Üyeler (gruplar) içindeki kullanıcılar aynı kapsam etiketine sahip olan Intune nesnelerine de erişebilir.

    ![Seçim kapsamı etiketlerinin ekran görüntüsü.](./media/scope-tags/select-scope-tags.png)

6. **Tamam**’ı seçin. 

## <a name="assign-scope-tags-to-other-objects"></a>Diğer nesnelere kapsam etiketleri atama

Kapsam etiketlerini destekleyen nesneler için, kapsam etiketleri genellikle **Özellikler**altında görünür. Örneğin, bir yapılandırma profiline bir kapsam etiketi atamak için aşağıdaki adımları izleyin:

1. Intune 'da **cihaz yapılandırma** > **profilleri** ' ni seçin > bir profil seçin.

    ![Profil seçme ekran görüntüsü.](./media/scope-tags/choose-profile.png)

2.  >  **Özellikler** > **kapsam (Etiketler)** **Ekle**öğesini seçin.

    ![Kapsam etiketleri Ekle ekran görüntüsü.](./media/scope-tags/add-scope-tags.png)

3. **Etiket Seç**' in altında, Profile eklemek istediğiniz etiketleri seçin.
4.  > **Tamam**Kaydet > ' i seçin.


## <a name="scope-tag-details"></a>Kapsam etiketi ayrıntıları
Kapsam etiketleriyle çalışırken bu ayrıntıları unutmayın: 

- Kiracıda bu nesnenin birden fazla sürümüne (rol atamaları veya uygulamalar gibi) sahip olması durumunda, bir Intune nesne türüne kapsam etiketleri atayabilirsiniz.
  Aşağıdaki Intune nesneleri, bu kural için özel durumlardır ve şu anda kapsam etiketlerini desteklememektedir:
    - Windows ESP profilleri
    - Cihaz kategorileri
    - Kayıt kısıtlamaları
    - Corp cihaz tanımlayıcıları
    - Hüküm ve Koşullar
    - Autopilot cihazlar
    - Cihaz uyumluluk konumları
    - JAMF cihazları
- VPP belirteciyle ilişkili VPP uygulamaları ve ebook 'lar, ilişkili VPP belirtecine atanan kapsam etiketlerini alırlar.
- DEP belirteciyle ilişkili Aygıt Kayıt Programı (DEP) cihazlar ve DEP profilleri, ilişkili DEP belirtecine atanan kapsam etiketlerini alırlar.
- Yönetici, Intune 'da bir nesne oluşturduğunda, bu yöneticiye atanan tüm kapsam etiketleri otomatik olarak yeni nesnesine atanır.
- Intune RBAC Azure Active Directory rollere uygulanmaz. Bu nedenle, Intune hizmet yöneticileri ve genel Yöneticiler rollerinin, sahip oldukları kapsam etiketleri ne olduğuna bakılmaksızın Intune 'a tam yönetici erişimi vardır.
- Bir rol atamasının kapsam etiketi yoksa, BT yöneticisi BT yöneticileri izinlerine göre tüm nesneleri görebilir. Kapsam etiketleri olmayan yöneticiler, tüm kapsam etiketlerine sahiptir.
- Yalnızca rol atamalarınız içinde olan bir kapsam etiketi atayabilirsiniz.
- Yalnızca rol atamalarınızın kapsamında (gruplar) listelenen grupları hedefleyebilirsiniz.
- Rolünüzün atandığı bir kapsam etiketi varsa, bir Intune nesnesindeki tüm kapsam etiketlerini silemezsiniz. En az bir kapsam etiketi gereklidir.

## <a name="next-steps"></a>Sonraki adımlar

[Birden çok rol ataması](role-based-access-control.md#multiple-role-assignments)olduğunda kapsam etiketlerinin nasıl davranacağını öğrenin.
[Rollerinizi](role-based-access-control.md) ve [profillerinizi](device-profile-assign.md) yönetin.
