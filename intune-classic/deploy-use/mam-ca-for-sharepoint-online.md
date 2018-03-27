---
title: SharePoint Online için uygulama tabanlı koşullu erişim ilkesi oluşturma
description: ''
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 05/03/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 531b09bb-ddfd-498f-8ee3-6675d2466208
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.openlocfilehash: 5848fc18e0c288f8806f1fc93427d96c48317d64
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="set-up-app-based-conditional-access-ca-policies-for-sharepoint-online"></a>SharePoint Online için uygulama tabanlı koşullu erişim (CA) ilkelerini ayarlama

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Bu konu başlığı altında, SharePoint Online için uygulama tabanlı koşullu erişim ilkesini ayarlama yönergeleri sağlanır. Uygulama tabanlı CA yöneticilerin yalnızca Intune uygulama koruma ilkeleri uygulanmış olan mobil uygulamalara izin vermesini sağlar.

## <a name="to-create-the-app-based-ca-policy-for-sharepoint-online"></a>SharePoint Online’a uygulama tabanlı CA ilkesi oluşturmak için

1. [Azure portalına](https://portal.azure.com) gidin ve kimlik bilgilerinizle oturum açın.

    > [!NOTE]
    > Azure portalı deneyiminde yeniyseniz, [Uygulama koruma ilkeleri için Azure portalı](azure-portal-for-microsoft-intune-mam-policies.md) konusunu okuyun.

2. Soldaki menüden **Daha fazla hizmet**’i seçtikten sonra metin kutusu filtresine **Intune** yazın.

3. **Intune Uygulama Koruma** > **Intune mobil uygulama yönetimi** > **Tüm Ayarlar**’ı seçin.

4. Intune Mobil uygulama yönetimi dikey penceresinde SharePoint Online kutucuğunu seçin.

5. **İzin verilen uygulamalar** dikey penceresinde, yalnızca Intune uygulama koruma ilkeleri tarafından desteklenen uygulamalara izin vermek için **Intune uygulama ilkelerini destekleyen uygulamalara izin ver** seçeneğini belirleyin.

    > [!NOTE] 
    > Yalnızca Intune uygulama koruma ilkeleri tarafından desteklenen uygulamalara izin verme seçeneğini belirlediğinizde, **yalnızca** desteklenen uygulamaları içeren bir liste görüntülenir.

    ![Uygulamaların listesini gösteren izin verilen uygulamalar dikey penceresinin ekran görüntüsü](../media/mam-ca-spo-allowed-apps.png)

## <a name="to-assign-app-based-ca-policies-to-your-users"></a>Kullanıcılarınıza uygulama tabanlı CA ilkeleri atamak için

1. **Kısıtlanmış kullanıcı grupları** dikey penceresini açın ve ardından **Kullanıcı grubu ekle**’yi seçin.

2. Bu ilkeyi alması gereken bir veya daha fazla kullanıcı grubu seçin.

    ![Kullanıcı grubu ekle seçeneğinin vurgulandığı kısıtlı kullanıcı grupları dikey penceresinin ekran görüntüsü](../media/mam-ca-spo-restricted-groups.png)

    > [!IMPORTANT] 
    > Önceki adımda seçtiğiniz kullanıcı grubundaki bazı kullanıcıların bu ilkeden etkilenmemesini isteyebilirsiniz. Bu gibi durumlarda, kullanıcı grubunu muaf tutulan kullanıcı grupları listesine ekleyin. 

3. **SharePoint Online** dikey penceresinde **Muaf tutulan kullanıcı grupları**’nı ve ardından **Kullanıcı grubu ekle**’yi seçerek kullanıcı gruplarının listesini açın.

4. Bu ilkeden muaf tutmak istediğiniz grupları seçin.  

## <a name="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy"></a>Mevcut uygulama tabanlı CA ilkesindeki kullanıcı gruplarını değiştirmek veya silmek için

1. **Kısıtlanmış kullanıcı grupları** dikey penceresini açın, ardından silmek istediğiniz kullanıcı grubunu vurgulayın.
2. Silme seçeneklerini görmek için üç nokta işaretine tıklayın.
3. Kullanıcı grubunu listeden silmek için **Sil**’i seçin.

> [!NOTE] 
> Bir kullanıcı grubunu **Muaf tutulan kullanıcı grubu** listesinden kaldırmak için yordamın adımlarını izleyebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

[Modern kimlik doğrulaması kullanılmayan uygulamaları engelleme](block-apps-with-no-modern-authentication.md)

## <a name="see-also"></a>Ayrıca bkz:

[Uygulama verilerini uygulama koruma ilkeleriyle koruma](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[Exchange Online için uygulama tabanlı CA’yı yapılandırma](mam-ca-for-exchange-online.md)
