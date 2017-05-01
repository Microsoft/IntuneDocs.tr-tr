---
title: "SharePoint Online için uygulama erişimini yapılandırma"
description: 
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 531b09bb-ddfd-498f-8ee3-6675d2466208
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 992273f88e4bbe234f11f936d6416dbaf0d394e9
ms.lasthandoff: 04/19/2017


---

# <a name="create-a-sharepoint-online-conditional-access-policy-to-only-allow-apps-supported-by-mam"></a>Yalnızca MAM tarafından desteklenen uygulamalara izin vermek için bir SharePoint Online koşullu erişim ilkesi oluşturma
Bu konu, yalnızca Intune mobil uygulama yönetimi (MAM) ilkelerini destekleyen mobil uygulamalara izin vermek üzere, Exchange Online için koşullu erişimin nasıl ayarlanacağına yönelik adım adım yönergeler sağlar.

## <a name="configure-a-sharepoint-online-policy"></a>SharePoint Online ilkesi yapılandırma
**Adım 1:** Uygulama erişim özelliğini içeren [Azure portalında](https://portal.azure.com) oturum açın. Azure portalı deneyiminde yeniyseniz, bkz. [MAM ilkeleri için Azure portalı](azure-portal-for-microsoft-intune-mam-policies.md).

**Adım 2:** **Gözat > Intune > Intune mobil uygulama yönetimi dikey penceresi > Ayarlar**’ı ve **koşullu erişim** bölümünde **SharePoint Online**’ı seçin.

![Koşullu erişim bölümü ve SharePoint Online dikey penceresinin açık halini gösteren ayarlar dikey penceresinin ekran görüntüsü](../media/mam-ca-settings-spo.png)

**Adım 3:** **İzin verilen uygulamalar** dikey penceresinde, yalnızca Intune MAM ilkeleri tarafından desteklenen uygulamaların SharePoint Online’a erişmesine izin vermek için **Intune uygulama ilkelerini destekleyen uygulamalara izin ver** seçeneğini belirleyin. Yalnızca Intune MAM ilkeleri tarafından desteklenen uygulamalara izin ver seçeneğini belirlediğinizde, desteklenen uygulamaların listesi görüntülenir.

![Uygulamaların listesini gösteren izin verilen uygulamalar dikey penceresinin ekran görüntüsü](../media/mam-ca-spo-allowed-apps.png)

**Adım 4:** Bu ilkeyi kullanıcılara uygulamak için **Kısıtlı kullanıcı grupları** dikey penceresini açın ve **Kullanıcı grubu ekle**’yi seçin. Bu ilkeyi alması gereken bir veya daha fazla kullanıcı grubu seçin.

![Kullanıcı grubu ekle seçeneğinin vurgulandığı kısıtlı kullanıcı grupları dikey penceresinin ekran görüntüsü](../media/mam-ca-spo-restricted-groups.png)


**Adım 5:** Önceki adımda seçtiğiniz kullanıcı grubundaki bazı kullanıcıların bu ilkeden etkilenmemesini isteyebilirsiniz. Bu gibi durumlarda, kullanıcı grubunu muaf tutulan kullanıcı grupları listesine ekleyin. **SharePoint Online** dikey penceresinden **Muaf tutulan kullanıcı grupları**’nı seçin. Kullanıcı grupları listesini açmak için **Kullanıcı grubu ekle**’yi seçin. Bu ilkeden muaf tutmak istediğiniz grupları seçin.  

## <a name="modifying-an-existing-policy"></a>Geçerli bir ilkeyi değiştirme
### <a name="adding-or-deleting-user-groups"></a>Kullanıcı grupları ekleme veya silme
**Kısıtlı kullanıcı grupları** listesinden **bir kullanıcı grubunu silmek** için Kısıtlı kullanıcı grupları dikey penceresini açın, silmek istediğiniz kullanıcı grubunu vurgulayın ve ... üzerine tıklayın. silme seçeneğini görmek için. Kullanıcı grubunu listeden silmek için **Sil**’i seçin. Bir kullanıcı grubunu **muaf tutulan kullanıcı grubu** listesinden kaldırmak için aynı yordamı izleyebilirsiniz.


## <a name="next-steps"></a>Sonraki adımlar
[Exchange Online için uygulama erişimi yapılandırma](mam-ca-for-exchange-online.md)

[Modern kimlik doğrulaması olmayan uygulamaları engelleme](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Ayrıca bkz.

[Uygulama verilerini MAM ilkeleriyle koruma](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

