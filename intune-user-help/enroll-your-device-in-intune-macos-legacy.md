---
title: "Eski macOS cihazınızı Intune’a kaydetme | Microsoft Docs"
description: "macOS cihazının Intune’a nasıl kaydedildiği açıklanır"
keywords: Mac OS X, macOS, OS X
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58eb0e7a-1321-4c66-a281-88fb01e72c1c
searchScope:
- User help
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 23d996132a6c896bb260b1bc4e46cbc6077583b3
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="enroll-your-legacy-macos-device-in-intune"></a>Eski macOS cihazınızı Intune’a kaydetme

Bu yönergeler, OS X Yosemite 10.10 ve öncesi sürümleri çalıştıran macOS cihazlar için geçerlidir. Daha sonraki macOS sürümlerini çalıştıran macOS cihazları kaydetme yönergelerini [burada](enroll-your-device-in-intune-macos-cp.md) bulabilirsiniz.

Kuruluşunuzun uygulamalarına, verilerine ve kaynaklarına erişerek işinizi yapmaya devam edebilirsiniz. İş için bir macOS cihazı kullanıyorsanız, __Yönetim Profili__ yüklemeniz gerekir. Bu yalnızca, şirketinizin destek birimi tarafından ayarlanan ve ayarlarla erişim bilgilerini Mac cihazınıza yükleyen bir dosyadır. Daha fazla bilgi edinmek istiyor musunuz? [Şirket Portalı uygulamasını yükler ve cihazınızı Intune'a kaydederseniz ne olur?](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md) sayfasını inceleyin.

1. Cihazınızın __Dock__ bölümünde __Safari__'yi bulun, yeni bir pencere açın ve ardından [Şirket Portalı web sitesini](https://portal.manage.microsoft.com#HelpDeskDialog) ziyaret edin.
2. İş veya okul hesabınızla Şirket Portalı web sitesinde oturum açın.

  [!INCLUDE[wit_nextref](includes/end-user-password-guidance.md)]

3. Oturum açtıktan sonra sayfanın sol üst köşesindeki **Menü**’ye tıklayın ve **Cihazlarım**’ı seçin.

 ![Henüz herhangi bir uygulamanın yüklenemeyeceğini gösteren web portalı ve altında Cihazlarım düğmesi ile web portalı giriş sayfasının ekran görüntüsü.](./media/macOS_enroll_001_landing_page.png)

4. __Cihazlarım__ sayfasında, kayıtlı cihazların bir listesini veya yalnızca bir başlık görürsünüz. Bu, macOS veya başka bir kayıtlı cihazınız olup olmadığına bağlıdır. Listede olmayan bir cihazı kaydetmek için şu ifadeye sahip başlığı seçin: __Cihazınız listedeyse, tanımlamak için buraya dokunun. Listede değilse, yine buraya tıklayarak cihazınızı kaydedebilirsiniz__. Kayıtlı cihazınız yoksa başlıkta **Kayıtlı cihazınız yok ifadesi yer alır. Buraya dokunarak bu cihazı kaydedin.**

  ![Listelenmemiş cihazları kaydetme veya tanımlanmamış cihazları tanımlama başlık isteminin üzerinde birkaç tanımlanmamış cihazın belirtildiği Cihazlarım sayfasının ekran görüntüsü.](./media/macOS_enroll_002_tap_here_banner.png)

5. __Bu cihazı tanımlama veya kaydetme__ nedeninizle ilgili kısa bir açıklamayı içeren bir açılır pencere görüntülenir. Bilgileri gözden geçirdikten sonra devam etmek için __Kaydet__'e tıklayın.

 ![Bu Cihazı Tanımlayın veya Kaydedin macOS](./media/macOS_enroll_003_IDenroll_popup.png)

6. __Bu cihazı tanımladığınızda__ gerçekleştirilecek işlemlerle ilgili kısa bir açıklamayı içeren ikinci bir açılır pencere görüntülenir. Bilgileri gözden geçirdikten sonra devam etmek için __Yükle__'ye tıklayın.

 ![Bu cihazı kaydet macOS](./media/macOS_enroll_004_enroll_popup.png)

  > [!NOTE]
  > Cihazınızın, kuruluşunuzun kaynaklarına erişmek için yeterli güvenliğe sahip olduğunu doğrulamak için Intune'un bilgisayarınıza erişmesi gerekir. [Cihazınızı Intune'a kaydettiğinizde gerçekleştirilen işlemleri](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios.md) keşfedin.

7. __Sistem Tercihleri__ açılır ve __"Yönetim Profilini" yüklemek__ isteyip istemediğiniz sorulur. Devam etmek için __Yükle__'ye, daha fazla ayrıntıya ulaşmak için ise __Profili Göster__'e tıklayın.

 ![Yönetim Profilini Yükleme](./media/macOS_enroll_005_sysprefs_mgmt_profile.png)

8. Bir macOS penceresi açılır. Değişiklik yapılmasını onaylamak için bilgisayarınızın __Kullanıcı Adı__ ve __Parola__, bilgilerini girip __Tamam__'a tıklayın. Yönetim profili Mac cihazınıza yüklenir.

 ![macOS Profil Yükleme Açılır Penceresi](./media/macOS_enroll_006_sysprefs_admin_login.png)

9. Mac cihazınızda profille ilgili ayrıntılı bilgiler içeren veya __Yükleme__ konusunda emin olup olmadığınızı soran ek iletiler görüntülenebilir. Devam etmek için bu pencerelerde __Devam__ ve __Yükle__ seçeneklerini belirleyin. Yükleme tamamlandıktan sonra yeni yüklediğiniz __Yönetim Profili__ bilgilerini __Cihaz Profilleri__ bölümünde görüntüleyebilirsiniz.

 ![macOS Profili Yüklendi](./media/macOS_enroll_007_sysprefs_installed_profile.png)

Bazı profiller **Doğrulanmamış** olarak görüntülenebilir, şirketinizden oldukları sürece bu durum normaldir.

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne danışın. İletişim bilgilerine [Şirket Portalı web sitesinden](https://portal.manage.microsoft.com#HelpDeskDialog) ulaşabilirsiniz.
