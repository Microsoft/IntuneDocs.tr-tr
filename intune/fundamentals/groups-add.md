---
title: Kullanıcıları ve cihazları düzenlemek için grup ekleme
titleSuffix: Microsoft Intune
description: Kullanıcıları ve cihazları coğrafi konum, bölüm veya donanım belirtimlerine göre düzenlemek için gruplar ekleyin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/20/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: altsou
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 183e8cc5924f6ce1f002225150d808841924e20c
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514651"
---
# <a name="add-groups-to-organize-users-and-devices"></a>Kullanıcıları ve cihazları düzenlemek için grup ekleme

Intune, cihazları ve kullanıcıları yönetmek için Azure Active Directory (Azure AD) gruplarını kullanır. Bir Intune yöneticisi olarak grupları, kuruluş gereksinimlerinize uyacak şekilde ayarlayabilirsiniz. Kullanıcı veya cihazları coğrafi konum, departman veya donanım özelliklerine göre düzenlemek için grup oluşturun. Büyük ölçekli görevleri yönetmek için grupları kullanın. Örneğin, birçok kullanıcı için ilkeler ayarlayabilir veya bir cihaz kümesine uygulama dağıtabilirsiniz.

Aşağıdaki grup türlerini ekleyebilirsiniz:

- **Atanan gruplar** -kullanıcıları veya cihazları statik bir gruba el ile ekleyin. 
- **Dinamik Gruplar** (Azure AD Premium gerekir)-oluşturduğunuz bir ifadeye göre Kullanıcı veya cihazları Kullanıcı gruplarına veya cihaz gruplarına otomatik olarak ekleyin.

  Örneğin, yönetici başlığıyla bir kullanıcı eklendiğinde, Kullanıcı otomatik olarak **Tüm Yöneticiler** kullanıcı grubuna eklenir. Ya da bir cihazda iOS/ıpados cihaz işletim sistemi türü varsa, cihaz otomatik olarak **tüm iOS/ıpados cihazları** cihazları grubuna eklenir.

## <a name="add-a-new-group"></a>Yeni bir grup ekleme

Yeni bir grup oluşturmak için aşağıdaki adımları kullanın.

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Yeni grup** > **grupları** seçin:

   ![Yeni Grup seçiliyken Azure portal ekran görüntüsü](./media/groups-add/groups-add-new.png)

3. **Grup türü**' nde, aşağıdaki seçeneklerden birini seçin:

    - **Güvenlik**: güvenlik grupları, kaynaklara kimlerin erişebileceğini tanımlar ve Intune 'daki gruplarınız için önerilir. Örneğin, kullanıcılar için **Tüm Charlotte çalışanları** veya **uzak çalışanlar**gibi gruplar oluşturabilirsiniz. Ya da, **tüm iOS/ıpados cihazları** veya **tüm Windows 10 öğrenci cihazları**gibi cihazlar için gruplar oluşturabilirsiniz.

        > [!TIP]
        > Oluşturulan kullanıcılar ve gruplar, [Microsoft 365 Yönetim Merkezi](https://admin.microsoft.com)'nde, Azure Active Directory Yönetim merkezinde ve [Azure Portal Microsoft Intune](https://go.microsoft.com/fwlink/?linkid=2090973)de görülebilir. Kuruluş kiracınızda, tüm bu alanlarda gruplar oluşturabilir ve yönetebilirsiniz.
        >
        > Birincil rolünüz cihaz yönetimi ise, [Microsoft Endpoint Manager yönetim merkezini](https://go.microsoft.com/fwlink/?linkid=2109431)kullanmanızı öneririz.

    - **Office 365**: üyelere paylaşılan bir posta kutusuna, takvime, dosyalara, SharePoint sitesine ve daha fazlasına erişim vererek işbirliği olanakları sağlar. Bu seçenek, kuruluşunuzun dışındaki kişilerin de gruba erişmesini sağlar. Daha fazla bilgi için bkz. [Office 365 grupları hakkında bilgi edinin](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

4. Yeni grup için bir **Grup adı** ve **Grup açıklaması** girin. Özel olun ve kullanıcıların grubun ne olduğunu bilmesi için bilgi ekleyin.

    Örneğin, Grup adı için **tüm Windows 10 öğrenci cihazlarını** ve **contoso high okul notlar 9-12 ' deki öğrenciler tarafından kullanılan tüm Windows 10 cihazlarını** Grup açıklaması için girin.

5. **Üyelik türünü**girin. Seçenekleriniz şunlardır:

    - **Atanan**: Yöneticiler bu gruba el ile Kullanıcı veya cihaz atar ve Kullanıcı veya cihazları el ile kaldırır.
    - **Dinamik Kullanıcı**: Yöneticiler üyeleri otomatik olarak eklemek ve kaldırmak için üyelik kuralları oluşturur.
    - **Dinamik cihaz**: Yöneticiler cihazları otomatik olarak eklemek ve kaldırmak için dinamik grup kuralları oluşturur.

        ![Intune grup özelliklerinin ekran görüntüsü](./media/groups-add/groups-add-properties.png)

    Bu üyelik türleri ve dinamik ifadeler oluşturma hakkında daha fazla bilgi için bkz.:

    - [Azure AD kullanarak temel Grup oluşturma ve üye ekleme](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    - [Azure AD 'de gruplar için dinamik üyelik kuralları](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)

    > [!NOTE]
    > Bu yönetim merkezinde, kullanıcıları veya grupları oluştururken **Azure Active Directory** markalamayı göremeyebilirsiniz. Ancak, kullanmakta olduğunuz şeydir.

6. Yeni grubu eklemek için **Oluştur**’u seçin. Grubunuz listede gösteriliyor.

> [!TIP]
> Oluşturabileceğiniz bazı dinamik Kullanıcı ve cihaz gruplarından bazılarını göz önünde bulundurun, örneğin:
>
> - Contoso Yüksek okuldaki tüm öğrenciler
> - Tüm Android Kurumsal cihazları
> - Tüm iOS 11 ve eski cihazlar
> - Pazarlama
> - İnsan kaynakları
> - Tüm Charlotte çalışanları
> - Tüm WA çalışanları

## <a name="groups-and-policies"></a>Gruplar ve ilkeler

Kuruluşunuzun kaynaklarına erişim, oluşturduğunuz kullanıcılar ve gruplar tarafından denetlenir.

Grupları oluştururken [Uyumluluk ilkelerini](../protect/device-compliance-get-started.md) ve [yapılandırma profillerini](../configuration/device-profiles.md)nasıl uygulayacağınızı düşünün. Örneğin, şu olabilir:

- Bir cihaz işletim sistemine özgü ilkeler.
- Kuruluşunuzdaki farklı rollere özgü ilkeler.
- Active Directory içinde tanımladığınız kuruluş birimlerine özgü ilkeler.

Kuruluşunuzun temel uyumluluk gereksinimlerini oluşturmak için tüm gruplara ve cihazlara uygulanan varsayılan bir ilke oluşturabilirsiniz. Daha sonra, en geniş Kullanıcı ve cihaz kategorileri için daha özel ilkeler oluşturun. Örneğin, her cihaz işletim sistemi için e-posta ilkeleri oluşturabilirsiniz.

Yapılandırma profili önerileri ve Kılavuzu için bkz. [Kullanıcı gruplarına veya cihaz gruplarına Ilke atama](../configuration/device-profile-assign.md#user-groups-vs-device-groups) ve [profil önerileri](../configuration/device-profile-create.md#recommendations).

## <a name="see-also"></a>Ayrıca bkz.

- [Microsoft Intune ile rol tabanlı erişim denetimi (RBAC)](role-based-access-control.md)
- [Azure AD gruplarıyla kaynaklara erişimi yönetme](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
