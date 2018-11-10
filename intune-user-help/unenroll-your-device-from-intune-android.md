---
title: Android cihazınızı Intune’dan kaldırma | Microsoft Docs
description: Android cihazının Intune kaydını nasıl silebileceğiniz açıklanır.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/23/2018
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
ms.openlocfilehash: d932005c955afed7f16e9766b559b77b2cd43182
ms.sourcegitcommit: 604b29c480b24270b5debc3e5f3141c8149ee6ed
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2018
ms.locfileid: "49959494"
---
# <a name="unenroll-your-android-device-from-management"></a>Android cihazınızın yönetim kaydını silme  

Kayıtlı bir Android cihazın kuruluşunuz tarafından yönetilmesini sonlandırmak için cihazı kaldırın. Bu makalede cihazı Şirket Portalı uygulamasından nasıl kaldıracağınız açıklanmıştır. Cihazı kaldırdıktan sonra:  

* Cihaz, kuruluşunuzun korumalı verilerine ve kaynaklarına erişimi kaybeder.
* Cihaz artık Şirket Portalı’nda görünmez.
* Şirket Portalı’ndan uygulama yükleyemezsiniz.
* Cihazı eklediğinizde değiştirilen tüm ayarlar, mesela kamerayı devre dışı bırakmak veya belirli bir parola uzunluğu gerekliliği gibi ayarlar geçerliliğini kaybeder.  

1. Şirket Portalı’nda sağ üst köşeye gidin ve dikey üç nokta simgesine dokunun. Eylem menüsü açılır.

   ![Android Şirket Portalı uygulamasının bir görüntüsü, eylem menüsüyle birlikte sağ üst köşede açılır. Yeni "şirket portalını kaldır" seçeneği; "profilim" ve "ayarlar" seçeneklerinin altında ve "hüküm ve koşullar", "yardım ve geri bildirim" ve "hakkında" seçeneklerinin üstünde üçüncü bir seçenek olarak bulunur.](./media/android_remove_cp_menu_action_after_1705.png)

2. **Şirket Portalı’nı Kaldır**’a dokunun.  

3. Cihazınızın kaydını sildiğinizde neler olacağı hakkında bilgi veren bir ileti görüntülenir. **Tamam**’a dokunarak cihazı Şirket Portalı’ndan kaldırmak istediğinizi onaylayın.

   ![Eylem menüsünden "şirket portalını kaldır" seçeneği işaretlendikten sonra görünen onay iletişim kutusunun bir görüntüsü. İletişim kutusu, kullanıcıyı “şirket portalını kaldırdığınızda, cihazınız artık şirketinizin destek birimi tarafından yönetilmeyecek ve bu durumda cihazın şirket verilerine, şirket uygulamalarına ve şirket e-postasına erişimi kaldırılabilir” metniyle bilgilendirir. Ardından kullanıcıdan Şirket Portalı uygulamasını kaldırmak istediğini "Evet"'i seçerek onaylamasını ister.](./media/android_remove_cp_menu_confirmation_after_1705.png)

## <a name="removing-data-collected-by-the-company-portal-app"></a>Şirket Portalı uygulaması tarafından toplanan verileri kaldırma  

Android için Şirket Portalı uygulamasının cihazınızda depoladığı tüm verileri kaldırmak üzere:

-   Uygulamalar’a gidin -> Uygulamaya tıklayın -> “Verileri temizle” düğmesine basarak verileri temizleyin
-   ‘\storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal’ klasörünü silin

## <a name="uninstall-the-company-portal-app"></a>Şirket Portalı uygulamasını kaldırma  
Şirket Portalı bir cihaz yönetim uygulamasıdır; [cihazınızı yönetimden kaldırana](unenroll-your-device-from-intune-android.md#unenroll-your-android-device-from-management) kadar kaldırılamaz. Bu işlemi tamamladıysanız Şirket Portalı uygulamasının simgesine dokunun ve **Kaldır** seçeneğini görene kadar basılı tutun. **Kaldır**’a dokunarak uygulamayı cihazınızdan kaldırın.  

Bunun yerine **Ayarlar** > **Uygulamalar** > **Şirket Portalı** > **Kaldır**’a da dokunabilirsiniz.  

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne başvurun. İletişim bilgileri için [Şirket Portalı web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın
