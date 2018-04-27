---
title: Android cihazınızı Intune’dan kaldırma | Microsoft Docs
description: Android cihazının Intune kaydını nasıl silebileceğiniz açıklanır.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f40aab26-7613-48cc-a74e-de83df9465a4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: ec3c0a1c8ce4e04f4d23fb01e7c2525d8f2eed5b
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-remove-your-android-device-from-intune"></a>Android cihazınızı Intune’dan kaldırma

Android cihazınızı Intune’dan kaldırdığınızda cihazınız, şirket kaynaklarına artık erişemez.  Cihazınızı yönetimden kaldırdığınızda ne olacağı hakkında daha fazla bilgi için bkz. [Cihazınızı Intune’dan kaldırdığınızda ne olur?](what-happens-if-you-unenroll-your-device-from-intune-android.md)

## <a name="removing-the-device-from-the-company-portal-app"></a>Cihazınızı Şirket Portalı uygulamasından kaldırma

Cihazınızı Intune’dan kaldırmak ve Şirket Portalı uygulamasını kaldırmak için aşağıdaki adımları izleyin:

1. Şirket Portalı uygulamasının sağ üst köşesindeki üç dikey noktaya dokunarak **eylem menüsünü** açın.

   ![Android Şirket Portalı uygulamasının bir görüntüsü, eylem menüsüyle birlikte sağ üst köşede açılır. Yeni "şirket portalını kaldır" seçeneği; "profilim" ve "ayarlar" seçeneklerinin altında ve "hüküm ve koşullar", "yardım ve geri bildirim" ve "hakkında" seçeneklerinin üstünde üçüncü bir seçenek olarak bulunur.](./media/android_remove_cp_menu_action_after_1705.png)

2. **Şirket Portalı’nı Kaldır**’a dokunun.

3. Açılan bir onay penceresi Şirket Portalı'nı kaldırmak istediğinizden emin olup olmadığınızı sorar. Cihazınızın kaydını sildiğinizde neler olacağı hakkında bazı bilgiler verir. Bu iletiyi okuduktan sonra uygulamayı kaldırmak için **Tamam**'a dokunun.

   ![Eylem menüsünden "şirket portalını kaldır" seçeneği işaretlendikten sonra görünen onay iletişim kutusunun bir görüntüsü. İletişim kutusu, kullanıcıyı “şirket portalını kaldırdığınızda, cihazınız artık şirketinizin destek birimi tarafından yönetilmeyecek ve bu durumda cihazın şirket verilerine, şirket uygulamalarına ve şirket e-postasına erişimi kaldırılabilir” metniyle bilgilendirir. Ardından kullanıcıdan Şirket Portalı uygulamasını kaldırmak istediğini "Evet"'i seçerek onaylamasını ister.](./media/android_remove_cp_menu_confirmation_after_1705.png)

## <a name="removing-data-collected-by-the-company-portal-app"></a>Şirket Portalı uygulaması tarafından toplanan verileri kaldırma

Android için Şirket Portalı uygulamasının cihazınızda depoladığı tüm verileri kaldırmak üzere:

-   Uygulamalar’a gidin -> Uygulamaya tıklayın -> “Verileri temizle” düğmesine basarak verileri temizleyin
-   ‘\storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal’ klasörünü silin

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](https://portal.manage.microsoft.com#HelpDeskDialog) bakın.
