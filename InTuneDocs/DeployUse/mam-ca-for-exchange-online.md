---
title: "Exchange Online için uygulama erişimi yapılandırma | Microsoft Intune"
description: "Bu konu, MAM uygulamaları için bir koşullu erişim ilkesini nasıl yapılandırabileceğinizi açıklar."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f2cd1a1f-fd29-4081-8dfa-c40993a107d5
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0f78ece8bbaf813c0082e6b764d174cf25bcb618
ms.openlocfilehash: fd00785f5e9eeecddb3840dcb9e2674e8786526e


---

# Yalnızca MAM tarafından desteklenen uygulamalara izin vermek için bir Exchange Online koşullu erişimi oluşturma
Bu konu, yalnızca Intune mobil uygulama yönetimi (MAM) ilkelerini destekleyen mobil uygulamalara izin vermek üzere, Exchange Online için koşullu erişimin nasıl ayarlanacağına yönelik adım adım yönergeler sağlar.


## Exchange Online ilkesi oluşturma
1.  Uygulama erişim özelliğini içeren [Azure portal](portal.azure.com)’ında oturum açın. Azure portalı deneyiminde yeniyseniz, bkz. [MAM ilkeleri için Azure portalı](azure-portal-for-microsoft-intune-mam-policies.md).

2.  **Gözat > Intune > Intune mobil uygulama yönetimi dikey penceresi > Ayarlar**’ı ve **koşullu erişim** bölümünde **Exchange Online**’ı seçin.

  ![Ayarlar dikey penceresinin Exchange Online seçeneği vurgulanmış olarak koşullu erişim bölümünü gösteren ekran görüntüsü](../media/mam-ca-settings-exo.png)

3.  **İzin verilen uygulamalar** dikey penceresinde, yalnızca Intune MAM ilkeleri tarafından desteklenen uygulamaların Exchange Online’a erişmesine izin vermek için **Intune uygulama ilkelerini destekleyen uygulamalara izin ver** seçeneğini belirleyin. Bu seçeneği belirlediğinizde, desteklenen uygulamalar listesi görüntülenir.

  >[!NOTE]
  >iOS ve Android’de Exchange Online’a bağlanan yerleşik posta istemcilerini de içeren tüm Exchange Active Sync posta istemcilerinin e-posta göndermesi veya alması engellenir. Kullanıcılar, bunun yerine Outlook posta uygulamasını kullanmaları gerektiğini belirten tek bir e-posta alır. 
4.   Bu ilkeyi kullanıcılara uygulamak için **Kısıtlı Kullanıcı grupları** dikey penceresini açın ve **Kullanıcı grubu ekle**’yi seçin. Bu ilkeyi alması gereken bir veya daha fazla kullanıcı grubu seçin.

  ![Kullanıcı grubu ekle seçeneğinin vurgulandığı kısıtlı kullanıcı grupları dikey penceresinin ekran görüntüsü](../media/mam-ca-add-user-group.png)

5.  Önceki adımda seçtiğiniz kullanıcı grubundaki bazı kullanıcıların bu ilkeden etkilenmemesini isteyebilirsiniz. Bu gibi durumlarda, kullanıcı grubunu muaf tutulan kullanıcı grupları listesine ekleyin. **Exchange Online** dikey penceresinden **Muaf tutulan kullanıcı grupları**’nı seçin. Kullanıcı grupları listesini açmak için **Kullanıcı grubu ekle**’yi seçin. Bu ilkeden muaf tutmak istediğiniz grupları seçin.  

## Geçerli bir ilkeyi değiştirme
### Kullanıcı gruplarını ekleme veya silme

**Kısıtlı kullanıcı grupları** listesinden **bir kullanıcı grubu silmek** için **Kısıtlı kullanıcı grupları** dikey penceresini açın, silmek istediğiniz kullanıcı grubunu vurgulayın ve **Sil** seçeneğini görmek için **üç nokta(...)**’ya tıklayın. Kullanıcı grubunu listeden silmek için **Sil**’i seçin. Bir kullanıcı grubunu **muaf tutulan kullanıcı grubu** listesinden kaldırmak için aynı yordamı izleyebilirsiniz.


## Sonraki adımlar
[Modern kimlik doğrulaması olmayan uygulamaları engelleme](block-apps-with-no-modern-authentication.md)
### Ayrıca bkz.
[Uygulama verilerini MAM ilkeleriyle koruma](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO2-->


