---
title: "Intune ile uygulama tabanlı koşullu erişim ilkesi"
description: "Bu konuda, Intune ile uygulama tabanlı bir koşullu erişim ilkesini nasıl yapılandırabileceğiniz açıklanmaktadır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a7f054868d0bae061f348239614f3a40b96a15b1
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2017
---
# <a name="set-up-app-based-conditional-access-policies"></a>Uygulama tabanlı koşullu erişim ilkeleri ayarlama

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bu konu, onaylı uygulamalar listesinin parçası olan uygulamalar için uygulama tabanlı koşullu erişim ilkelerinin nasıl ayarlanacağı konusunda yönergeler sağlamaktadır. Liste, Microsoft tarafından sınanan onaylı uygulamalardan oluşur.

> [!IMPORTANT]
> Bu konu, Exchange Online kullanarak uygulama tabanlı bir koşullu erişim ilkesi ekleme adımlarını vermektedir, ancak aynı adımları onaylı uygulamalar listesinden SharePoint Online, Microsoft Teams gibi başka uygulamaları eklerken de kullanabilirsiniz.

## <a name="to-create-an-app-based-conditional-access-policy"></a>Uygulama tabanlı bir koşullu erişim ilkesi oluşturmak için
1.  [Azure portalına](https://portal.azure.com) gidin ve kimlik bilgilerinizle oturum açın.

2.  **Diğer hizmetler**’i seçin ve "Intune" yazın.

3.  **Intune Uygulama Koruması**’nı seçin.

4.  **Intune mobil uygulama yönetimi** dikey penceresinde **Tüm Ayarlar**’ı seçin.

5.  **Koşullu erişim** bölümünde **Exchange Online**’ı seçin.

    ![Ayarlar dikey penceresinin Exchange Online seçeneği vurgulanmış olarak koşullu erişim bölümünü gösteren ekran görüntüsü](./media/MAM-conditional-access-1.png)

6. **İzin verilen uygulamalar** dikey penceresinde, yalnızca Intune uygulama koruma ilkeleri tarafından desteklenen uygulamaların Exchange Online’a erişmesine izin vermek için **Intune uygulama ilkelerini destekleyen uygulamalara izin ver** seçeneğini belirleyin. Bu seçeneği belirlediğinizde, desteklenen uygulamalar listesi görüntülenir.

    > [!NOTE]
    > iOS ve Android’de Exchange Online’a bağlanan yerleşik posta istemcilerini de içeren tüm Exchange Active Sync posta istemcilerinin e-posta göndermesi veya alması engellenir. Kullanıcılar, bunun yerine Outlook posta uygulamasını kullanmaları gerektiğini belirten tek bir e-posta alır.

7. Bu ilkeyi kullanıcılara uygulamak için **Kısıtlı Kullanıcı grupları** dikey penceresini açın ve **Kullanıcı grubu ekle**’yi seçin. Bu ilkeyi alması gereken bir veya daha fazla kullanıcı grubu seçin.

    ![Kullanıcı grubu ekle seçeneğinin vurgulandığı kısıtlı kullanıcı grupları dikey penceresinin ekran görüntüsü](./media/mam-ca-add-user-group.png)

8. Önceki adımda seçtiğiniz kullanıcı grubundaki bazı kullanıcıların bu ilkeden etkilenmemesini isteyebilirsiniz. Bu gibi durumlarda, kullanıcı grubunu muaf tutulan kullanıcı grupları listesine ekleyin. **Exchange Online** dikey penceresinden **Muaf tutulan kullanıcı grupları**’nı seçin. Kullanıcı grupları listesini açmak için **Kullanıcı grubu ekle**’yi seçin. Bu ilkeden muaf tutmak istediğiniz grupları seçin.

## <a name="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy"></a>Mevcut uygulama tabanlı CA ilkesindeki kullanıcı gruplarını değiştirmek veya silmek için

1. **Kısıtlanmış kullanıcı grupları** dikey penceresini açın, ardından silmek istediğiniz kullanıcı grubunu vurgulayın.
2. Silme seçeneklerini görmek için üç nokta işaretine tıklayın.
3. Kullanıcı grubunu listeden silmek için **Sil**’i seçin.

## <a name="next-steps"></a>Sonraki adımlar
[Modern kimlik doğrulaması olmayan uygulamaları engelleme](app-modern-authentication-block.md)

### <a name="see-also"></a>Ayrıca bkz.

[Uygulama verilerini uygulama koruma ilkeleriyle koruma](app-protection-policies.md)
