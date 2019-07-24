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
ms.openlocfilehash: 627899eafb2175b2d3034045bd765a10f4a203d6
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67882501"
---
# <a name="use-role-based-access-control-rbac-and-scope-tags-for-distributed-it"></a>Dağıtılmış BT için rol tabanlı erişim denetimi (RBAC) ve kapsam etiketleri kullanma

Doğru yöneticilerin doğru Intune nesnelerine doğru erişime ve görünürlüğe sahip olduğundan emin olmak için rol tabanlı erişim denetimi ve kapsam etiketlerini kullanabilirsiniz. Roller hangi erişim yöneticilerinin hangi nesnelere sahip olduğunu belirleyen roller. Kapsam etiketleri, yöneticilerin hangi nesneleri görebileceği belirlenir.

Örneğin, bir Seattle bölgesel ofis yöneticisine Ilke ve Profil Yöneticisi rolü atandığını varsayalım. Bu yöneticinin yalnızca Seattle cihazları için uygulanan profilleri ve ilkeleri görmesini ve yönetmesini istiyorsunuz. Bunu yapmak için şunları yapmanız gerekir:

1. Seattle adlı bir kapsam etiketi oluşturun.
2. Ilke ve Profil Yöneticisi rolü için şu ile bir rol ataması oluşturun: 
    - Üyeler (gruplar) = Seattle BT yöneticileri adlı bir güvenlik grubu. Bu gruptaki tüm yöneticilerin, kapsamdaki kullanıcılar/cihazlar için ilkeleri ve profilleri yönetme izni olacaktır (gruplar).
    - Kapsam (gruplar) = Seattle kullanıcıları adlı bir güvenlik grubu. Bu gruptaki tüm kullanıcıların/cihazların profilleri ve ilkeleri, Üyeler (gruplar) içindeki Yöneticiler tarafından yönetilebilir. 
    - Scope (Etiketler) = Seattle. Üye (gruplar) içindeki Yöneticiler, Seattle kapsam etiketine sahip olan cihazları görebilir.
3. Üyeler (gruplar) içindeki yöneticilerin erişebilmesini istediğiniz ilkelere ve profillere Seattle kapsam etiketini ekleyin.
4. Üyeler (gruplar) içinde yöneticilere görünür olmasını istediğiniz cihazlara Seattle kapsam etiketini ekleyin. 


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
3. **Üyeler (gruplar)**  > seçin > Bu atamanın parçası olarak istediğiniz grupları seçin > Tamam '**ı** **seçin** > . Bu gruptaki mUsers, kapsamdaki Kullanıcı/cihazların ilkelerini ve profillerini yönetme izinlerine sahip olacaktır (gruplar).

    ![Üye gruplarının Seç ekran görüntüsü.](./media/scope-tags/select-member-groups.png)

4. Belirli bir grup kümesindeki kullanıcıları/cihazları yönetmek istiyorsanız **kapsam (gruplar)**  > **Seçili gruplar** > ' ı seçin.**dahil edilecek grupları seçin** > grupları seçin > Tamam ' ı **seçin** > . Bu gruptaki tüm kullanıcılar/cihazlar, profilleri ve ilkelerine Üyeler (Grup) içindeki Yöneticiler tarafından yönetilmiş olabilir.

    ![Kapsam gruplarının Seç ekran görüntüsü.](./media/scope-tags/select-scope-groups.png)

    Alternatif olarak, tüm cihazlar , **tüm kullanıcılar**veya tüm **Kullanıcılar &** tüm cihazlar ' ı seçebilirsiniz.

    ![Seçim kapsam grupları için diğer seçeneklerin ekran görüntüsü.](./media/scope-tags/scope-group-other-options.png)
    
5. **Kapsam (Etiketler)**  > **Ekle** ' yi seçin > Bu role eklemek istediğiniz etiketleri seçin >**Tamam**' ı **seçin** > . Üyeler (gruplar) içindeki kullanıcıların aynı kapsam etiketine sahip olan ilkelere ve profillere erişimi olur.

    ![Seçim kapsamı etiketlerinin ekran görüntüsü.](./media/scope-tags/select-scope-tags.png)

6. **Tamam**’ı seçin. 

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Kapsam etiketini bir yapılandırma profiline eklemek için
1. Intune 'da **cihaz yapılandırma** > **profilleri** ' ni seçin > bir profil seçin.

    ![Profil seçme ekran görüntüsü.](./media/scope-tags/choose-profile.png)

2.  >  **Özellikler** > **kapsam (Etiketler)** **Ekle**öğesini seçin.

    ![Kapsam etiketleri Ekle ekran görüntüsü.](./media/scope-tags/add-scope-tags.png)

3. **Etiket Seç**' in altında, Profile eklemek istediğiniz etiketleri seçin.
4.  > **Tamam** Kaydet > ' i seçin.

## <a name="to-assign-a-scope-tag-to-an-app-configuration-policy"></a>Bir uygulama yapılandırma ilkesine kapsam etiketi atama
**Cihaz kayıt türü** **yönetilen**cihazlara ayarlanmış cihazlarda:
1. **İstemci uygulamaları** > **uygulama yapılandırma ilkeleri** ' ni seçin > bir uygulama yapılandırma ilkesi seçin.
2. **Özellikler** > **kapsam (Etiketler)** seçeneğini belirleyin > ilkeye atamak istediğiniz etiketleri seçin.

**Cihaz kayıt türü** **yönetilen uygulamalar**olarak ayarlanan cihazlar için:
1. **İstemci uygulamaları** > **uygulama yapılandırma ilkeleri** ' ni seçin > bir uygulama yapılandırma ilkesi seçin.
2. **Kapsam (Etiketler)** seçeneğini belirleyin > ilkeye atamak istediğiniz etiketleri seçin.


## <a name="to-assign-a-scope-tag-to-an-ios-app-provisioning-profile"></a>Bir iOS uygulaması sağlama profiline kapsam etiketi atamak için
1. Intune 'da, bir profil seçmek > **istemci uygulamaları** > **iOS uygulama sağlama profilleri** ' ni seçin.
2. **Özellikler** > **kapsam (Etiketler)** öğesini seçin > Profile atamak istediğiniz etiketleri seçin.
3.  > **Tamam** Kaydet > ' i seçin.

## <a name="to-assign-a-scope-tag-to-an-apple-volume-purchase-program-vpp-token"></a>Bir Apple Volume Purchase Program (VPP) belirtecine kapsam etiketi atamak için
1. Intune 'da, **istemci uygulamaları** > **Apple VPP belirteçleri** ' ni seçin > bir VPP belirteci seçin.
2. **Kapsam (Etiketler)** seçeneğini belirleyin > Profile atamak istediğiniz etiketleri seçin. VPP belirteciyle ilişkili VPP uygulamaları ve ebook 'lar atanan etiketleri alır.
3.  > **Tamam** Kaydet > ' i seçin.

## <a name="scope-tag-details"></a>Kapsam etiketi ayrıntıları
Kapsam etiketleriyle çalışırken bu ayrıntıları unutmayın:

- Şu anda kapsam etiketlerini atayabilirsiniz:
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
  - Volume Purchase program (VPP) belirteçleri
- Yönetici, Intune 'da bir nesne oluşturduğunda, bu yöneticiye atanan tüm kapsam etiketleri otomatik olarak yeni nesnesine atanır.
- Intune RBAC Azure Active Directory rollere uygulanmaz. Bu nedenle, Intune hizmet yöneticileri ve genel Yöneticiler rollerinin, sahip oldukları kapsam etiketleri ne olduğuna bakılmaksızın Intune 'a tam yönetici erişimi vardır.
- Kapsam etiketleriyle bir rol atamasında bulunan Yöneticiler, kapsam etiketleri olmayan Intune nesnelerini de görebilir.
- Yalnızca rol atamalarınız içinde olan bir kapsam etiketi atayabilirsiniz.
- Yalnızca rol atamalarınızın kapsamında (gruplar) listelenen grupları hedefleyebilirsiniz.
- Rolünüzün atandığı bir kapsam etiketi varsa, bir Intune nesnesindeki tüm kapsam etiketlerini silemezsiniz. En az bir kapsam etiketi gereklidir.

## <a name="next-steps"></a>Sonraki adımlar

[Rollerinizi](role-based-access-control.md) ve [profillerinizi](device-profile-assign.md) yönetin.
