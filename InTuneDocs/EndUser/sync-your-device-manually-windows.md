---
title: "Windows cihazınızı el ile eşitleme | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 443c6de7-5187-4dc4-b844-6085a0c659bd
searchScope:
- User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: 4b5f0129d6824a51c36662a1cc7ef4e8a2de9e20
ms.openlocfilehash: ff5a4313337c89da00cb87e0f4dd6c8dcc233361
ms.lasthandoff: 02/18/2017


---

# <a name="sync-your-windows-device-manually"></a>Windows cihazınızı el ile eşitleme

Bazen Windows cihazınıza bir uygulama yüklemeyi denemek, düşündüğünüzden daha uzun sürebilir. Bu durumda, Windows cihazınızı el ile eşitlemeyi deneyebilirsiniz. Eşitlemek yüklemenin hızını artırmaya yardımcı olabilir.

> [!Note]
> Daha yavaş olan veya aynı anda içerik indiren cihazların çok sayıda olduğu bir ağdaysanız uygulamaların yüklenmesi biraz zaman alabilir.

Aşağıdaki Windows sürümleri el ile eşitlenebilir. Ne yazık ki, cihazınızda farklı bir Windows sürümü kullanılıyorsa el ile eşitleme başlatamazsınız.

* [Windows 10 masaüstü ile eşitleme](#windows-10-desktop)
* [Windows 10 Mobile ile eşitleme](#windows-10-mobile)
* [Windows Phone 8.1 ile eşitleme](#windows-phone-81)

## <a name="windows-10-desktop"></a>Windows 10 masaüstü
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

### <a name="steps-to-follow-if-you-see-access-work-or-school"></a>İşe veya okula erişim seçeneğini görüyorsanız izlenecek adımlar

1. **Hesaplar** sayfasında **İşe veya okula erişim**’i seçin.

    ![İşe veya okula Erişim’i seçin](./media/w10-enroll-rs1-connect-to-work-or-school.png)

2. İş veya okul hesabınızı seçin. BT yöneticinizin yaptığı ayarlara bağlı olarak, aşağıda gösterilen örneğe benzeyen iki hesap görebilirsiniz. Bir hesabın yanında bir evrak çantası, diğerinin yanında ise Microsoft logosu var.

    - Evrak çantası olan hesabı görürseniz bunu seçin ve altındaki **Bilgi** düğmesini bulun.
    - Yalnızca Microsoft logosu olan hesabı görürseniz hesabı seçin ve altındaki **Bilgi** düğmesini bulun.

    ![Evrak çantası veya Microsoft logosu yanındaki hesabınızın adını seçin](./media/win10pc-rs1-sync-info-button.png)

3. **Bilgi** düğmesini seçin. Aşağıdaki örneğe benzer bir iletişim kutusu açılır.

    ![Evrak çantası veya Microsoft logosu yanındaki hesabınızın adını seçin](./media/win10pc-rs1-sync-button.png)

4. **Eşitle** düğmesini seçin. Cihazınız Intune'la eşitlenir.

### <a name="steps-to-follow-if-you-see-work-access"></a>İşe erişim görüyorsanız uygulanacak adımlar

1. **Hesaplar** sayfasında **İş yeri erişimi**’ni seçin.

    ![Hesap türü olarak iş yeri erişimini seçme](./media/win10pc-sync-3-work-access.png)

2. **Cihaz yönetimine kaydol** bölümünün altında şirketinizin adını seçin.

    ![Cihaz yönetimi için şirket adı seçme](./media/win10pc-sync-4-tap-com-name.png)

3. **Eşitle** düğmesini seçin.

    ![Eşitleme düğmesini seçme](./media/win10pc-sync-5-tap-sync.png)

   Eşitleme işlemi tamamlanana kadar düğme gri gösterilir.

   ## <a name="windows-10-mobile"></a>Windows 10 Mobile
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

## <a name="windows-phone-81"></a>Windows Phone 8.1
Yavaş çalışan bir uygulama yüklemesini hızlandırmak amacıyla Windows Phone 8.1 cihazınızı el ile eşitlemek için:

1. **Tüm uygulamalar** > **Ayarlar** > **çalışma alanı**’na gidin.

    ![Ayarlar listesi](./media/wp81-1-sync-settings-workplace.png)

2. Şirketinizin adını seçin.

    ![Çalışma alanı hesabı için şirket adını seçme](./media/wp81-2-sync-tap-compname.png)

3. **Eşitle** simgesini seçin.

    ![Eşitleme simgesini seçme](./media/wp81-3-sync-tap-sync-button.png)

   Cihazınızın eşitlenmesi bitene kadar, ekranın en üstünde “Hesabınızı eşitliyoruz” iletisi görüntülenir.

Bu bilgiler yardımcı olmadı mı? BT yöneticinize başvurun. Kişi bilgileri için [Şirket Portalı Web sitesine](http://portal.manage.microsoft.com) bakın.

