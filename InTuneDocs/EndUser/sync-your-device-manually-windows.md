---
title: "Windows cihazınızı el ile eşitleme | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
ms.author: stabar
manager: angrobe
ms.date: 10/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 443c6de7-5187-4dc4-b844-6085a0c659bd
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2d7630d71505fadc22ab135ff0c8988b314793ad
ms.openlocfilehash: e0f18e4e1077f7843b4f8d8ea6d9e485f715bc3c


---


# Windows cihazınızı el ile eşitleme
Uygulamanızın yüklenmesi çok uzun sürerse, Windows cihazınızı el ile eşitlemeyi deneyebilirsiniz. El ile eşitleme, yükleme hızını artırmaya yardımcı olabilir.

Yalnızca aşağıdaki sürümler desteklenir. Sahip olduğunuz cihazın türüyle eşleşen yönergeleri kullanın.

* [Windows 10 Mobile](#windows-10-mobile)
* [Windows 10 masaüstü](#windows-10-desktop)
* [Windows Phone 8.1](#windows-phone-8-1)


## Windows 10 Mobile
Yavaş çalışan bir uygulama yüklemesini hızlandırmak amacıyla Windows 10 Mobile cihazınızı el ile eşitlemek için:

1. **Tüm uygulamalar** > **Ayarlar** > **Hesaplar**’a gidin.

    ![Ayarları ekranında Hesapları Seçme](./media/win10m-sync-1-settings-accounts.png)

2. **İş yeri erişimi**’ni seçin.

    ![Hesap türü olarak iş yeri erişimini seçme](./media/win10m-sync-2-work-access.png)

3. **Cihaz yönetimine kaydol**’un altında, şirketinizin adını seçin.

    ![Cihaz yönetimi için şirket adı seçme](./media/win10m-sync-3-tap-comp-name.png)

4. **Eşitle** simgesini seçin.

    ![Eşitleme simgesini seçme](./media/win10m-sync-4-tap-sync.png)

    Ekranın en üstünde “Hesabınızı eşitliyoruz” iletisi görüntülenir. Cihazınızın eşitlenmesi bitene kadar **Eşitle** düğmesi gri gösterilir.

## Windows 10 masaüstü
Birden fazla Windows 10 sürümü olduğundan iki grup adım vardır. Hangi adımları kullanacağınızı anlamak için ekran görüntülerine bakın ve cihazınızda gördüğünüze benzeyen ekran görüntüsündeki adımları uygulayın. 

1. **Başlat** düğmesini ve ardından **Ayarlar**’ı seçin.

    ![Başlat düğmesi](./media/win10pc-sync-1-start-button.png)

2. **Ayarlar** sayfasında **Hesaplar**’ı seçin.

    ![Ayarlar sayfasında Hesapları seçme](./media/win10pc-sync-2-settings-accounts.png)

3. Sonraki iki ekrana bakarak kendi cihazınızda gördüğünüze benzeyeni bulun. Cihazınızda gördüğünüz ekrana uyan adımları uygulayın.

    “İşe veya okula erişim” ekranını görürseniz, [İşe veya okula Erişim seçeneğini görüyorsanız izlenecek adımlar](#steps-to-follow-if-you-see-access-work-or-school) kısmındaki yönergeleri izleyin.

    ![İşe veya okula erişim seçeneğini görüyorsanız izlenecek eşitleme adımları](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    “İşe erişim” ekranını görürseniz, [İşe erişim seçeneğini görüyorsanız izlenecek adımlar](#steps-to-follow-if-you-see-your-account) kısmındaki adımları izleyin.

    ![Hesap türü olarak iş yeri erişimini seçme](./media/win10pc-sync-3-work-access.png) 

### İşe veya okula erişim seçeneğini görüyorsanız izlenecek adımlar

1. **Hesaplar** sayfasında **İşe veya okula erişim**’i seçin.

    ![İşe veya okula Erişim’i seçin](./media/w10-enroll-rs1-connect-to-work-or-school.png)

2. İş veya okul hesabınızı seçin. BT yöneticinizin yaptığı ayarlara bağlı olarak, aşağıda gösterilen örneğe benzeyen iki hesap görebilirsiniz. Bir hesabın yanında bir evrak çantası, diğerinin yanında ise Microsoft logosu var. 

    - Evrak çantası olan hesabı görürseniz bunu seçin ve altındaki **Bilgi** düğmesini bulun. 
    - Yalnızca Microsoft logosu olan hesabı görürseniz hesabı seçin ve altındaki **Bilgi** düğmesini bulun.

    ![Evrak çantası veya Microsoft logosu yanındaki hesabınızın adını seçin](./media/win10pc-rs1-sync-info-button.png)

3. **Bilgi** düğmesini seçin. Aşağıdaki örneğe benzer bir iletişim kutusu açılır.

    ![Evrak çantası veya Microsoft logosu yanındaki hesabınızın adını seçin](./media/win10pc-rs1-sync-button.png)

4. **Eşitle** düğmesini seçin. Cihazınız Intune'la eşitlenir.

### İşe erişim görüyorsanız uygulanacak adımlar
    
1. **Hesaplar** sayfasında **İş yeri erişimi**’ni seçin.

    ![Hesap türü olarak iş yeri erişimini seçme](./media/win10pc-sync-3-work-access.png)

2. **Cihaz yönetimine kaydol** bölümünün altında şirketinizin adını seçin.

    ![Cihaz yönetimi için şirket adı seçme](./media/win10pc-sync-4-tap-com-name.png)

3. **Eşitle** düğmesini seçin.

    ![Eşitleme düğmesini seçme](./media/win10pc-sync-5-tap-sync.png)

   Eşitleme işlemi tamamlanana kadar düğme gri gösterilir.

## Windows Phone 8.1
Yavaş çalışan bir uygulama yüklemesini hızlandırmak amacıyla Windows Phone 8.1 cihazınızı el ile eşitlemek için:

1. **Tüm uygulamalar** > **Ayarlar** > **çalışma alanı**’na gidin.

    ![Ayarlar listesi](./media/wp81-1-sync-settings-workplace.png)

2. Şirketinizin adını seçin.

    ![Çalışma alanı hesabı için şirket adını seçme](./media/wp81-2-sync-tap-compname.png)

3. **Eşitle** simgesini seçin.

    ![Eşitleme simgesini seçme](./media/wp81-3-sync-tap-sync-button.png)

   Cihazınızın eşitlenmesi bitene kadar, ekranın en üstünde “Hesabınızı eşitliyoruz” iletisi görüntülenir.

Bu bilgiler yardımcı olmadı mı? BT yöneticinize başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](http://portal.manage.microsoft.com) bakın.



<!--HONumber=Oct16_HO3-->


