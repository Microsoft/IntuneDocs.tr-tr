---
title: Intune 'da dağıtılan rol tabanlı erişim denetimi (RBAC) ve kapsam etiketlerini kullanma | Microsoft Docs
description: Yapılandırma profillerini belirli rollere filtrelemek için kapsam etiketlerini kullanın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/06/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.technology: ''
ms.assetid: a21d3039-f2ed-4f43-b6fa-d00c071edbc4
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: dfb9ec9d28b00e454884bbf0bf296cd72cba4b6f
ms.sourcegitcommit: 5881979c45fc973cba382413eaa193d369b8dcf6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2020
ms.locfileid: "77569226"
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

Varsayılan kapsam etiketi özelliği, Microsoft uç noktası Configuration Manager güvenlik kapsamları özelliğine benzer. 

## <a name="to-create-a-scope-tag"></a>Kapsam etiketi oluşturmak için

1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)'Nde, **kiracı yönetimi** > **Roller** > **kapsam (Etiketler)** > **Oluştur**' u seçin.
2. **Temel bilgiler** sayfasında, bir **ad** ve isteğe bağlı bir **Açıklama**girin. **İleri**’yi seçin.
3. **Atamalar** sayfasında, bu kapsam etiketini atamak istediğiniz cihazları içeren grupları seçin. **İleri**’yi seçin.
4. **Gözden geçir + oluştur** sayfasında **Oluştur**' u seçin.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Kapsam etiketini bir role atamak için

1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)'Nde, **tüm roller** >  > **Roller** ' i seçin > bir rol > **atamaları** seçin > **ata**' **yı seçin.**
2. **Temel bilgiler** sayfasında, bir **atama adı** ve **Açıklama**belirtin. **İleri**’yi seçin.
3. **Yönetici grupları** sayfasında, **dahil edilecek grupları seç**' i seçin ve bu atamanın bir parçası olarak istediğiniz grupları seçin. Bu gruptaki kullanıcıların, kapsamdaki kullanıcıları/cihazları yönetme izinleri olacaktır (gruplar). **İleri**’yi seçin.

    ![Üye gruplarının Seç ekran görüntüsü.](./media/scope-tags/select-member-groups.png)

4. **Kapsam grupları** sayfasında, **ata** için aşağıdaki seçeneklerden birini belirleyin
    - **Seçili gruplar**: yönetmek istediğiniz kullanıcıları/Deivleri içeren grupları seçin. Seçili gruplardaki tüm kullanıcılar/cihazlar Yönetici gruplarındaki kullanıcılar tarafından yönetilir.
    - **Tüm kullanıcılar**: tüm kullanıcılar Yönetici gruplarındaki kullanıcılar tarafından yönetilebilir.
    - **Tüm cihazlar**: tüm cihazlar Yönetici gruplarındaki kullanıcılar tarafından yönetilebilir.
    - **Tüm kullanıcılar ve tüm cihazlar**: tüm kullanıcılar ve cihazlar Yönetici gruplarındaki kullanıcılar tarafından yönetilebilir.

5. **İleri**’yi seçin.
6. **Kapsam etiketleri** sayfasında, bu role eklemek istediğiniz etiketleri seçin. Yönetici gruplarındaki kullanıcılar aynı kapsam etiketine sahip olan Intune nesnelerine de erişebilir.
7. **İleri** ' yi seçerek **gözden geçir + oluştur** sayfasına gidin ve **Oluştur**' u seçin.

## <a name="assign-scope-tags-to-other-objects"></a>Diğer nesnelere kapsam etiketleri atama

Kapsam etiketlerini destekleyen nesneler için, kapsam etiketleri genellikle **Özellikler**altında görünür. Örneğin, bir yapılandırma profiline bir kapsam etiketi atamak için aşağıdaki adımları izleyin:

1. [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)'nde **cihazlar** > **yapılandırma profilleri** ' ni seçin > bir profil seçin.

2. **Özellikler** > **kapsam (Etiketler)** > **düzenle** > **kapsam etiketlerini seçin** > Profile eklemek istediğiniz etiketleri seçin.
4. Seç > **gözden geçir + kaydet**' **i** seçin.

## <a name="scope-tag-details"></a>Kapsam etiketi ayrıntıları
Kapsam etiketleriyle çalışırken bu ayrıntıları unutmayın: 

- Kiracıda bu nesnenin birden fazla sürümüne (rol atamaları veya uygulamalar gibi) sahip olması durumunda, bir Intune nesne türüne kapsam etiketleri atayabilirsiniz.
  Aşağıdaki Intune nesneleri, bu kural için özel durumlardır ve şu anda kapsam etiketlerini desteklememektedir:
    - Windows ESP profilleri
    - Cihaz kategorileri
    - Kayıt kısıtlamaları
    - Corp cihaz tanımlayıcıları
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
[Rollerinizi](role-based-access-control.md) ve [profillerinizi](../configuration/device-profile-assign.md) yönetin.


