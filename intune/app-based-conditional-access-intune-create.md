---
title: Intune ile uygulama tabanlı koşullu erişim ilkesi ayarlama
description: Intune ile uygulama tabanlı koşullu erişim ilkesi oluşturmayı öğrenin.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: da6f351f4ce5cf6b0aeae977ffbef56dab5bd2df
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Intune ile uygulama tabanlı koşullu erişim ilkeleri ayarlama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makale, onaylı uygulamalar listesinin parçası olan uygulamalar için uygulama tabanlı koşullu erişim ilkelerinin nasıl ayarlanacağını açıklar. Liste, Microsoft tarafından sınanan onaylı uygulamalardan oluşur.

> [!IMPORTANT]
> Bu makale, Exchange Online kullanarak uygulama tabanlı bir koşullu erişim ilkesi ekleme adımlarını vermektedir, ancak aynı adımları onaylı uygulamalar listesinden SharePoint Online, Microsoft Teams gibi başka uygulamaları eklerken de kullanabilirsiniz.

## <a name="to-create-an-app-based-conditional-access-policy"></a>Uygulama tabanlı bir koşullu erişim ilkesi oluşturmak için
1.  [Azure portalına](https://portal.azure.com) gidin ve kimlik bilgilerinizle oturum açın.

2.  **Tüm hizmetler**’i seçin ve “Intune” yazın.

3.  **Intune Uygulama Koruması**’nı seçin.

4.  **Koşullu erişim** bölümündeki **Intune Uygulama Koruması**’nda **Exchange Online**’ı seçin.

    ![Exchange Online seçeneğinin vurgulandığı koşullu erişim bölümünün ayarlar bölmesini gösteren ekran görüntüsü](./media/MAM-conditional-access-1.png)

6. **İzin verilen uygulamalar** bölmesinde, yalnızca Intune uygulama koruma ilkeleri tarafından desteklenen uygulamaların Exchange Online’a erişmesine izin vermek için **Intune uygulama ilkelerini destekleyen uygulamalara izin ver** seçeneğini belirleyin. Bu seçeneği belirlediğinizde, desteklenen uygulamalar listesi görüntülenir.

    > [!NOTE]
    > iOS ve Android’de Exchange Online’a bağlanan yerleşik posta istemcilerini de içeren tüm Exchange Active Sync posta istemcilerinin e-posta göndermesi veya alması engellenir. Kullanıcılar, bunun yerine Outlook posta uygulamasını kullanmaları gerektiğini belirten tek bir e-posta alır.

7. Bu ilkeyi kullanıcılara uygulamak için **Kısıtlı Kullanıcı grupları** bölmesini açın ve **Kullanıcı grubu ekle**’yi seçin. Bu ilkeyi alması gereken bir veya daha fazla kullanıcı grubu seçin.

    ![Kullanıcı grubu ekle seçeneğinin vurgulandığı kısıtlı kullanıcı grupları bölmesinin ekran görüntüsü](./media/mam-ca-add-user-group.png)

8. Önceki adımda seçtiğiniz kullanıcı grubundaki bazı kullanıcıların bu ilkeden etkilenmemesini isteyebilirsiniz. Bu gibi durumlarda, kullanıcı grubunu muaf tutulan kullanıcı grupları listesine ekleyin. **Exchange Online** bölmesinden, **Muaf tutulan kullanıcı grupları**’nı seçin. Kullanıcı grupları listesini açmak için **Kullanıcı grubu ekle**’yi seçin. Bu ilkeden muaf tutmak istediğiniz grupları seçin.

## <a name="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy"></a>Mevcut uygulama tabanlı CA ilkesindeki kullanıcı gruplarını değiştirmek veya silmek için

1. **Kısıtlanmış kullanıcı grupları** bölmesini açın, ardından silmek istediğiniz kullanıcı grubunu vurgulayın.
2. Silme seçeneklerini görmek için üç nokta işaretine tıklayın.
3. Kullanıcı grubunu listeden silmek için **Sil**’i seçin.

## <a name="create-app-based-conditional-access-policies-in-azure-ad-workload"></a>Azure AD iş yükünde uygulama tabanlı koşullu erişim ilkeleri oluşturma

Intune 1708 sürümünden başlayarak BT yöneticileri, Azure AD iş yükünden uygulama tabanlı koşullu erişim ilkeleri oluşturabilirler. Böylece Azure ve Intune iş yükleri arasında değişim yapmanız gerekmez ve işiniz kolaylaşır.

> [!IMPORTANT]
> Intune Azure portalından Azure AD koşullu erişim ilkeleri oluşturmak için bir Azure AD Premium lisansınız olması gerekir.

### <a name="to-create-an-app-based-conditional-access-policy"></a>Uygulama tabanlı bir koşullu erişim ilkesi oluşturmak için

> [!IMPORTANT]
> Uygulama tabanlı koşullu erişim ilkelerini kullanmadan önce uygulamalarınıza [Intune uygulama koruma ilkeleri](app-protection-policies.md) uygulamanız gerekir.

1. **Intune Panosu**’nda, **Koşullu erişim**’i seçin.

2. **İlkeler** bölmesinde **Yeni ilke**’yi seçerek yeni uygulama tabanlı koşullu erişim ilkenizi oluşturun.

4. İlke için bir ad girip **Atamalar** kısmından uygun ayarları yapılandırdıktan sonra **Erişim denetimleri** bölümünden **Ver**’i seçin.

5. **Onaylı istemci uygulama gerektir**’i, **Seçin**’i ve daha sonra **Oluştur**’u seçerek yeni ilkeyi kaydedin.

## <a name="next-steps"></a>Sonraki adımlar
[Modern kimlik doğrulaması olmayan uygulamaları engelleme](app-modern-authentication-block.md)

### <a name="see-also"></a>Ayrıca bkz:

[Uygulama koruma ilkeleriyle uygulama verilerini koruma](app-protection-policies.md)
[Azure Active Directory’de Koşullu Erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
