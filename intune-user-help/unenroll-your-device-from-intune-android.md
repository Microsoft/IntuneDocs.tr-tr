---
title: Android cihazınızı Intune’dan kaldırma | Microsoft Docs
description: Android Cihazınızı Intune şirket Portalı'ndan kaldırma
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/04/2019
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
ms.openlocfilehash: 75b26e178badbaa7905199eb91490134d2b72ba9
ms.sourcegitcommit: 61ed365f7f8826451c41bcab5e19bef97b5a3c72
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2019
ms.locfileid: "54057347"
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
Şirket portalı, bir cihaz Yönetimi uygulamasıdır. Dek kaldırılamaz [cihazınızın yönetim kaydını](unenroll-your-device-from-intune-android.md#unenroll-your-android-device-from-management). Bu işlemi tamamladıysanız Şirket Portalı uygulamasının simgesine dokunun ve **Kaldır** seçeneğini görene kadar basılı tutun. **Kaldır**’a dokunarak uygulamayı cihazınızdan kaldırın.  

Alternatif olarak, dokunun **ayarları** > **uygulamaları** > **Şirket portalı** > **kaldırma**.  

### <a name="remove-company-portal-app-as-device-administrator"></a>Şirket portalı uygulamasını cihaz yönetici olarak Kaldır  
Son çare olarak, bir cihaz Yöneticisi olarak kaldırarak cihazınızın uygulamayı kaldırabilirsiniz.  

Cihaz şirkete varsa, kuruluşunuzun her zaman Şirket portalı, Cihazınızda olmasını gerektirebilir. Kaldırırsanız, uygulama yeniden kadar erişim e-posta, uygulamalar, WiFi veya VPN gibi korumalı şirket kaynaklarına kaybına neden olabilir. Yükleme hakkında daha fazla bilgi için bkz: güncelleştirme veya gerekli uygulamaları kaldırma [Intune için uygulama ekleme](https://docs.microsoft.com/intune/apps-add#apps-that-are-added-automatically-by-intune).  

Bir cihaz Yöneticisi olarak şirket Portalı'nı devre dışı bırakmak için aşağıdaki adımları tamamlayın. Her ayar gerçek adlarını Android Cihazınızda değişebilir.  

**Android adımları seçenek 1**:  
1. Seçin **ayarları** > **güvenlik** > **ek güvenlik ayarlarına** > **cihaz yöneticileri** .  
2. NET **Şirket portalı** seçimi.  

**Android adımları seçeneği 2**:  
1. Seçin **ayarları** > **kilit ekranı ve güvenlik** > **diğer güvenlik ayarları** > **cihaz Yöneticisi uygulamaları**.  
2. NET **Şirket portalı** seçimi.    

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne başvurun. İletişim bilgileri için [Şirket Portalı web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın
