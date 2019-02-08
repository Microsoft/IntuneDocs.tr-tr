---
title: Windows cihazınızı el ile eşitleme | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 07/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4666779620aa0404c12107a374280c403d66bec3
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55840221"
---
# <a name="sync-your-windows-device-manually"></a>Windows cihazınızı el ile eşitleme

Uygulama yükleme hızı istediğiniz kadar yüksek değilse el ile eşitlemeyi başlatın. El ile eşitlemeler, en son güncelleştirmeler ve iletişimler için cihazınızı Intune’a bağlanmaya zorlar. Cihaz eşitlemesi tamamlandıktan sonra yükleme hızı artabilir.

Intune; Şirket Portalı uygulamasından, masaüstü görev çubuğu ve Başlat menüsünden ve cihazın Ayarlar uygulamasından el ile eşitlemeyi destekler. 

Şirket Portalı uygulaması işlevselliği, Creator’s Update (1703) ve üzerini çalıştıran Windows 10 cihazlarda desteklenir. 
* [Şirket Portalı uygulamasından eşitleme](#Sync-from-Company-Portal-app-for-Windows)  

Aşağıdakiler dahil olmak üzere tüm Windows cihazlar, cihazın Ayarlar uygulamasından eşitlenebilir:

* [Windows 10 masaüstü](#windows-10-desktop)  
* [Microsoft HoloLens](#microsoft-hololens)   
* [Windows 10 Mobile](#windows-10-mobile)  
* [Windows Phone 8.1](#windows-phone-81)    

## <a name="sync-directly-from-company-portal-app-for-windows"></a>Windows için Şirket Portalı uygulamasından doğrudan eşitleme
Creator’s Update (1703) ve üzerini çalıştıran Windows 10 cihazları el ile eşitlemek için bu adımları tamamlayın.

1.  Cihazınızda Şirket Portalı uygulamasını açın.

2.  **Ayarlar** > **Eşitle**’yi seçin.

    ![Şirket Portalı uygulamasının Ayarlar bölümünün vurgulandığı giriş sayfasının ekran görüntüsü](./media/RS1_homePage_settings_04.png)  
    
    ![Şirket Portalı uygulamasının Eşitle düğmesinin vurgulandığı ayarlar sayfasının ekran görüntüsü](./media/RS1_settingspage_sync05.png)  

## <a name="sync-from-device-taskbar-or-start-menu"></a>Cihaz görev çubuğundan veya Başlat menüsünden eşitleme   

Eşitleme denetimine uygulama dışında, cihazınızın masaüstünden de erişebilirsiniz. Uygulamayı doğrudan görev çubuğunuza veya Başlat menünüze sabitlediyseniz ve hızla eşitleme yapmak istiyorsanız bu yol kullanışlı olacaktır.  

1. Görev çubuğunuzda veya Başlat menünüzde Şirket Portalı uygulaması simgesini bulun.  
2. Uygulama simgesine sağ tıklayın, böylece uygulamanın menüsü (atlama listesi olarak da bilinir) açılır.  

    ![Bir cihazın masaüstünde Windows görev çubuğunun ekran görüntüsü. Şirket Portalı uygulaması simgesi tıklanmış ve “Görev çubuğuna sabitle”, “Pencereyi kapat” ve “Bu cihazı eşitle” eylemi seçeneklerini içeren bir menü görüntülenmiştir.](./media/sync-device-from-start-menu-1807.png)  

3. **Bu cihazı eşitle**’yi seçin. Şirket Portalı uygulaması, **Ayarlar** sayfasında açılır ve eşitlemenizi başlatır.  

## <a name="sync-from-settings-app"></a>Ayarlar Uygulamasından eşitleme 
Microsoft HoloLens, Windows 10 Desktop, Windows 10 Mobile ve Windows Phone 8.1 cihazlarınızı Ayarlar uygulamasından el ile eşitlemek için bu adımları tamamlayın.  

### <a name="windows-10-desktop"></a>Windows 10 masaüstü
1. Cihazınızda **Başlat** > **Ayarlar**’ı seçin.

2. **Hesaplar**’ı seçin.

    ![Ayarlar sayfasında Hesapları seçme](./media/win10pc-sync-2-settings-accounts.png)  

3. Masaüstü cihazlar için Windows 10’un birden çok sürümü vardır. Hangi adımlar dizisini takip etmeniz gerektiğini belirlemek için ekranınızı aşağıdaki ekran görüntüleriyle karşılaştırın. 

    * Ekranınızda **İş veya okula erişme** yazıyorsa [İş veya okula erişme](#access-work-or-school) adımlarına atlayın.

    ![Ayarlar uygulamasında iş veya okula erişme seçeneği](./media/w10-enroll-rs1-connect-to-work-or-school.png)  

    * Ekranınızda **İş erişimi** yazıyorsa [İş erişimi](#work-access) adımlarına atlayın.  

    ![Hesap türü olarak iş yeri erişimini seçme](./media/win10pc-sync-3-work-access.png)

#### <a name="access-work-or-school-steps"></a>İş veya okula erişme adımları

1. **İş veya okula erişme**’ye tıklayın.

    ![İş veya okula erişme seçeneğini gösteren ekran görüntüsü](./media/w10-enroll-rs1-connect-to-work-or-school.png)  

2. Yanında evrak çantası simgesi bulunan hesabı seçin. Bu hesabı görmüyorsanız şirketiniz ayarlarınızı farklı yapılandırmış olabilir. Bu durumda yanında Microsoft logosu olan hesaba tıklayın.

     ![Evrak çantası veya Microsoft logosu yanındaki hesabınızın adını seçin](./media/win10pc-rs1-sync-info-button.png)

3. **Bilgi**’ye tıklayın. 

4. **Eşitle**’ye tıklayın. 

#### <a name="work-access-steps"></a>İş erişimi adımları

1.  **İş erişimi**’ne tıklayın.

    ![Hesap türü olarak iş yeri erişimini seçme](./media/win10pc-sync-3-work-access.png)

2. **Cihaz yönetimine kaydol**’un altında şirketinizin adını seçin.

    ![Cihaz yönetimi için şirket adı seçme](./media/win10pc-sync-4-tap-com-name.png)

3. **Eşitle**’ye tıklayın. Eşitleme tamamlanana kadar düğme devre dışı kalır.

    ![Eşitleme düğmesini seçme](./media/win10pc-sync-5-tap-sync.png)  


### <a name="windows-10-mobile"></a>Windows 10 Mobile

   1. Cihazınızda **Tüm uygulamalar** > **Ayarlar** > **Hesaplar**’a gidin.

       ![Ayarları ekranında Hesapları Seçme](./media/win10m-sync-1-settings-accounts.png)

   2. **İş erişimi**’ni seçin.

       ![Hesap türü olarak iş yeri erişimini seçme](./media/win10m-sync-2-work-access.png)

   3. **Cihaz yönetimine kaydol**’un altında şirketinizin adını seçin.

       ![Cihaz yönetimi için şirket adı seçme](./media/win10m-sync-3-tap-comp-name.png)

   4. **Eşitle** simgesini seçin. Eşitleme tamamlanana kadar düğme devre dışı kalır.

       ![Eşitleme simgesini seçme](./media/win10m-sync-4-tap-sync.png)  
### <a name="microsoft-hololens"></a>Microsoft HoloLens  
Bu yönergeler, Windows 10 Yıldönümü Güncelleştirmesi (RS1 olarak da bilinir) çalıştıran HoloLens cihazlarda geçerlidir. 
1.  Cihazınızda Ayarlar uygulamasını açın.  

2.  **Hesaplar** > **İş Erişimi**’ni seçin.  
    ![Hesaplar bağlantısının vurgulandığı HoloLens ayarlar uygulamasının ekran görüntüsü](./media/RS1_holoLens_SettingsRS1_Accounts_06.png)  

3.  Bağlı hesabınızı ve ardından **Eşitle**’yi seçin. ![Eşitle düğmesinin vurgulandığı HoloLens ayarlar uygulamasının ekran görüntüsü](./media/RS1_holoLens_SyncRS1_Sync_08.png)  

### <a name="windows-phone-81"></a>Windows Phone 8.1

1. **Tüm uygulamalar** > **Ayarlar** > **çalışma alanı**’na gidin.

    ![Ayarlar listesi](./media/wp81-1-sync-settings-workplace.png)

2. Şirketinizin adını seçin.

    ![Çalışma alanı hesabı için şirket adını seçme](./media/wp81-2-sync-tap-compname.png)

3. **Eşitle** simgesini seçin.

    ![Eşitleme simgesini seçme](./media/wp81-3-sync-tap-sync-button.png)

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](https://go.microsoft.com/fwlink/?linkid=2010980) bakın.
