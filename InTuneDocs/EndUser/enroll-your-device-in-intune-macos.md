---
title: "macOS cihazınızı Intune’a kaydetme | Microsoft Intune"
description: "macOS cihazının Intune’a nasıl kaydedildiği açıklanır"
keywords: Mac OS X, macOS, OS X
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58eb0e7a-1321-4c66-a281-88fb01e72c1c
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6adfb7375f9747f64e7037164f48918789bd7ee0
ms.openlocfilehash: 650e9b0700971e626e4062c312111ef60e74badc


---

# <a name="enroll-your-macos-device-in-intune"></a>macOS cihazınızı Intune'a kaydetme

Kuruluşunuzun uygulamalarına, verilerine ve kaynaklarına erişerek işinizi yapmaya devam edebilirsiniz. İş için bir macOS cihazı kullanıyorsanız, __Yönetim Profili__ yüklemeniz gerekir. Bu profil, BT yöneticiniz tarafından ayarlanan ve ayarlarla erişim bilgilerini Mac cihazınıza yükleyen bir dosyadır. Daha fazla bilgi edinmek istiyor musunuz? [Şirket Portalı uygulamasını yükler ve cihazınızı Intune'a kaydederseniz ne olur?](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md) sayfasını inceleyin.

  > [!NOTE]
  > iPhone veya iPad gibi bir iOS cihazını kaydetmek istiyorsanız [buradaki talimatları uygulayın](enroll-your-device-in-intune-ios.md).

1. Cihazınızın __Dock__ bölümünde __Safari__'yi bulun, yeni bir pencere açın ve ardından [Şirket Portalı web sitesini](http://portal.manage.microsoft.com) ziyaret edin.
2. İş veya okul hesabınızla Şirket Portalı web sitesinde oturum açın.

  [!INCLUDE[wit_nextref](../includes/end-user-password-guidance.md)]

3. Oturum açtığınızda kullanılabilir __Uygulamalar__, __Cihazlarım__ ve BT ekibinize ulaşmak için kullanabileceğiniz __iletişim bilgileri__ bölümlerini göreceksiniz. Sayfanın en üstünde şu uyarı görüntülenir: **Bu cihaz kayıtlı değil veya Şirket Portalı tarafından tanımlanamıyor. <u>Farklı bir cihaz seçmek için buraya dokunun</u>.** __Buraya Dokunun__'a tıklayın.

 ![Şirket Portalı macOS Giriş Sayfası](./media/macOS_enroll_001_landing_page.png)

4. __Bu cihazı tanımlama veya kaydetme__ nedeninizle ilgili kısa bir açıklamayı içeren bir açılır pencere görüntülenir. Bilgileri gözden geçirdikten sonra devam etmek için __Kaydet__'e tıklayın.

 ![Bu Cihazı Tanımlayın veya Kaydedin macOS](./media/macOS_enroll_002_IDenroll_popup.png)

5. __Bu cihazı tanımladığınızda__ gerçekleştirilecek işlemlerle ilgili kısa bir açıklamayı içeren ikinci bir açılır pencere görüntülenir. Bilgileri gözden geçirdikten sonra devam etmek için __Yükle__'ye tıklayın.

 ![Bu cihazı kaydet macOS](./media/macOS_enroll_003_enroll_popup.png)

  > [!NOTE]
  > Cihazınızın, kuruluşunuzun kaynaklarına erişmek için yeterli güvenliğe sahip olduğunu doğrulamak için Intune'un bilgisayarınıza erişmesi gerekir. [Cihazınızı Intune'a kaydettiğinizde gerçekleştirilen işlemleri](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios.md) keşfedin.

6. __Sistem Tercihleri__ açılır ve __"Yönetim Profilini" yüklemek__ isteyip istemediğiniz sorulur. Devam etmek için __Yükle__'ye, daha fazla ayrıntıya ulaşmak için ise __Profili Göster__'e tıklayın.

 ![Yönetim Profilini Yükleme](./media/macOS_enroll_004_sysprefs_mgmt_profile.png)

7. Bir macOS penceresi açılır. Değişiklik yapılmasını onaylamak için bilgisayarınızın __Kullanıcı Adı__ ve __Parola__, bilgilerini girip __Tamam__'a tıklayın. Yönetim profili Mac cihazınıza yüklenir.

 ![macOS Profil Yükleme Açılır Penceresi](./media/macOS_enroll_005_sysprefs_admin_login.png)

8. Mac cihazınızda profille ilgili ayrıntılı bilgiler içeren veya __Yükleme__ konusunda emin olup olmadığınızı soran ek iletiler görüntülenebilir. Devam etmek için bu pencerelerde __Devam__ ve __Yükle__ seçeneklerini belirleyin. Yükleme tamamlandıktan sonra yeni yüklediğiniz __Yönetim Profili__ bilgilerini __Cihaz Profilleri__ bölümünde görüntüleyebilirsiniz.

 ![macOS Profili Yüklendi](./media/macOS_enroll_006_sysprefs_installed_profile.png)

Bu bilgiler yardımcı olmadı mı? BT yöneticinize başvurun. İletişim bilgilerine [Şirket Portalı web sitesinden](http://portal.manage.microsoft.com) ulaşabilirsiniz.



<!--HONumber=Dec16_HO2-->


