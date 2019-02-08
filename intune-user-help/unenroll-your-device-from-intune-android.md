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
ms.collection: M365-identity-device-management
ms.openlocfilehash: fafd9c92a51c8ef258d151a3c19c271fdc45f4c2
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55835869"
---
# <a name="unenroll-your-android-device-from-management"></a>Android cihazınızın yönetim kaydını silme  

Kayıtlı bir Android cihazın kuruluşunuz tarafından yönetilmesini sonlandırmak için cihazı kaldırın. Bu makalede cihazı Şirket Portalı uygulamasından nasıl kaldıracağınız açıklanmıştır. Cihazı kaldırdıktan sonra:  

* Cihaz, kuruluşunuzun korumalı verilerine ve kaynaklarına erişimi kaybeder.
* Cihaz artık Şirket Portalı’nda görünmez.
* Şirket Portalı’ndan uygulama yükleyemezsiniz.
* Cihazı eklediğinizde değiştirilen tüm ayarlar, mesela kamerayı devre dışı bırakmak veya belirli bir parola uzunluğu gerekliliği gibi ayarlar geçerliliğini kaybeder.  

1. Şirket Portalı’nda sağ üst köşeye gidin ve dikey üç nokta simgesine dokunun. Eylem menüsü açılır.

   ![Android Şirket portalı uygulamasının sağ üst köşede açılır eylem menüsüyle ekran görüntüsü. Yeni "şirket portalını kaldır" seçeneği; "profilim" ve "ayarlar" seçeneklerinin altında ve "hüküm ve koşullar", "yardım ve geri bildirim" ve "hakkında" seçeneklerinin üstünde üçüncü bir seçenek olarak bulunur.](./media/android_remove_cp_menu_action_after_1705.png)

2. **Şirket Portalı’nı Kaldır**’a dokunun.  

3. Cihazınızın kaydını sildiğinizde neler olacağı hakkında bilgi veren bir ileti görüntülenir. **Tamam**’a dokunarak cihazı Şirket Portalı’ndan kaldırmak istediğinizi onaylayın.

   ![Eylem menüsünden Yeni "Şirket portalını Kaldır" seçeneği seçtikten sonra kullanılabilir onayının ekran görüntüsü.](./media/android_remove_cp_menu_confirmation_after_1705.png)

## <a name="remove-data-collected-by-the-company-portal-app"></a>Şirket portalı uygulaması tarafından toplanan verileri kaldırma  

Android için Şirket Portalı uygulamasının cihazınızda depoladığı tüm verileri kaldırmak üzere:

-   Uygulama verilerini temizlemek dokunarak **uygulamaları** > **[*uygulama adını*]** > **verileri temizleme**.
-   Aşağıdaki klasörü silin: \storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal.

## <a name="uninstall-the-company-portal-app"></a>Şirket Portalı uygulamasını kaldırma  
Şirket portalı, bir cihaz Yönetimi uygulamasıdır. Cihazınızın yönetim kaydını kadar kaldırılamaz. Bu işlemi tamamladıysanız Şirket Portalı uygulamasının simgesine dokunun ve **Kaldır** seçeneğini görene kadar basılı tutun. **Kaldır**’a dokunarak uygulamayı cihazınızdan kaldırın.  

Alternatif olarak, dokunun **ayarları** > **uygulamaları** > **Şirket portalı** > **kaldırma**.  

### <a name="remove-the-company-portal-app-as-a-device-administrator"></a>Şirket portalı uygulamasını cihaz yönetici olarak Kaldır  
Son çare olarak, bir cihaz Yöneticisi olarak cihazınızın uygulamayı kaldırabilirsiniz.  

Cihaz şirkete varsa, kuruluşunuzun her zaman Şirket portalı, Cihazınızda olmasını gerektirebilir. Kaldırırsanız, uygulama yeniden kadar erişim e-posta, uygulamalar, Wi-Fi veya VPN gibi korumalı şirket kaynaklarına kaybedebilirsiniz. Yükleme hakkında daha fazla bilgi için bkz: güncelleştirme veya gerekli uygulamaları kaldırma [Intune için uygulama ekleme](https://docs.microsoft.com/intune/apps-add#apps-that-are-added-automatically-by-intune).  

Bir cihaz Yöneticisi olarak Şirket portalı devre dışı bırakılır. Her ayar gerçek adlarını Android Cihazınızda değişebilir.  

**Seçenek 1**:  
1. Seçin **ayarları** > **güvenlik** > **ek güvenlik ayarlarına** > **cihaz yöneticileri** .  
2. NET **Şirket portalı** seçimi.  

**Seçenek 2**:  
1. Seçin **ayarları** > **kilit ekranı ve güvenlik** > **diğer güvenlik ayarları** > **cihaz Yöneticisi uygulamaları**.  
2. NET **Şirket portalı** seçimi.    

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın.
