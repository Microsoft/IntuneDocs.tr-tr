---
title: Android cihazınızı Intune’dan kaldırma | Microsoft Docs
description: Android cihazınızı Intune Şirket Portalı 'dan kaldırma
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: f40aab26-7613-48cc-a74e-de83df9465a4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: be980a8cd2eb7f0cbe40002f73f9bc36a36d1193
ms.sourcegitcommit: caee3c3fa77586314aa8040b0caf32a0527b669e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75859075"
---
# <a name="unenroll-your-android-device-from-management"></a>Android cihazınızın yönetim kaydını silme  

Kayıtlı bir Android cihazın kuruluşunuz tarafından yönetilmesini sonlandırmak için cihazı kaldırın. Bu makalede cihazı Şirket Portalı uygulamasından nasıl kaldıracağınız açıklanmıştır. Cihazı kaldırdıktan sonra:  

* Cihaz, kuruluşunuzun korumalı verilerine ve kaynaklarına erişimi kaybeder.
* Cihaz artık Şirket Portalı’nda görünmez.
* Şirket Portalı’ndan uygulama yükleyemezsiniz.
* Cihazı eklediğinizde değiştirilen tüm ayarlar, mesela kamerayı devre dışı bırakmak veya belirli bir parola uzunluğu gerekliliği gibi ayarlar geçerliliğini kaybeder.  

> [!NOTE]
> Şirkete ait cihazınızı Microsoft Intune uygulamadan kaydedemez veya kaldıramazsınız. Cihaz ilk cihaz kurulumu sırasında kaydedildiyse ve kuruluşunuzun kaynaklarına erişmek için kaydolmalıdır.  

1. Şirket Portalı’nda sağ üst köşeye gidin ve dikey üç nokta simgesine dokunun. Eylem menüsü açılır.

   ![Android Şirket Portalı uygulamasının sağ üst köşede açılan Eylem menüsü ile ekran görüntüsü. Yeni "şirket portalını kaldır" seçeneği; "profilim" ve "ayarlar" seçeneklerinin altında ve "hüküm ve koşullar", "yardım ve geri bildirim" ve "hakkında" seçeneklerinin üstünde üçüncü bir seçenek olarak bulunur.](./media/android_remove_cp_menu_action_after_1705.png)

2. **Şirket Portalı’nı Kaldır**’a dokunun.  

3. Cihazınızın kaydını sildiğinizde neler olacağı hakkında bilgi veren bir ileti görüntülenir. **Tamam**’a dokunarak cihazı Şirket Portalı’ndan kaldırmak istediğinizi onaylayın.

   ![Eylem menüsünden Yeni "Şirket portalını kaldır" seçeneği seçildikten sonra, sağlanan onayın ekran görüntüsü.](./media/android_remove_cp_menu_confirmation_after_1705.png)

## <a name="remove-data-collected-by-the-company-portal-app"></a>Şirket Portalı uygulaması tarafından toplanan verileri kaldırma  

Android için Şirket Portalı uygulamasının cihazınızda depoladığı tüm verileri kaldırmak üzere:

- **Uygulamalar** > **[*uygulamanın adı*]**  > **verileri temizle**' ya dokunarak uygulama verilerini temizleyin.
- Şu klasörü silin: \storage\ınternal storage\Android\data\com.microsoft.windowsintune.companyportal.

## <a name="uninstall-the-company-portal-app"></a>Şirket Portalı uygulamasını kaldırma

Şirket Portalı bir cihaz yönetimi uygulamasıdır. Cihazınızın yönetimine kaydoluncaya kadar kaldırılamaz. Bu işlemi tamamladıysanız Şirket Portalı uygulamasının simgesine dokunun ve **Kaldır** seçeneğini görene kadar basılı tutun. **Kaldır**’a dokunarak uygulamayı cihazınızdan kaldırın.  

Alternatif olarak, **ayarlar** > **uygulamalar** > **Şirket portalı** **kaldırmak** > ' a dokunun.  

### <a name="remove-the-company-portal-app-as-a-device-administrator"></a>Şirket Portalı uygulamasını bir cihaz yöneticisi olarak kaldırma

Son çare olarak, uygulamayı cihazınızdan bir cihaz yöneticisi olarak kaldırabilirsiniz.  

Şirkete ait bir cihazınız varsa, kuruluşunuz her zaman cihazınızda Şirket Portalı gerekebilir. Yüklemesini kaldırırsanız, uygulama yeniden yükleninceye kadar e-posta, uygulamalar, Wi-Fi veya VPN gibi korunan şirket kaynaklarına erişiminizi kaybedebilirsiniz. Gerekli uygulamaları yükleme, güncelleştirme veya kaldırma hakkında daha fazla bilgi için bkz. [Microsoft Intune uygulama ekleme](/intune/apps/apps-add#apps-that-are-added-automatically-by-intune).

Şirket Portalı Cihaz Yöneticisi olarak devre dışı bırakabilirsiniz. Her ayarın gerçek adları, Android cihazınızda farklılık gösterebilir.  

**Seçenek 1**:  

1. **Ayarlar** > **güvenlik** > **cihaz yöneticileri** > **ek güvenlik ayarları** ' nı seçin.  
2. **Şirket portalı** seçimini temizleyin.  

**2. Seçenek**:

1. **Ayarlar** > **kilit ekranı ve güvenlik** > **Cihaz Yöneticisi uygulamaları** > **diğer güvenlik ayarları** ' nı seçin.
2. **Şirket portalı** seçimini temizleyin.

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın.
