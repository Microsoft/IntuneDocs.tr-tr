---
title: Şirket Portalı ile macOS cihazınızı Intune’a kaydetme | Microsoft Docs
description: Bir macOS cihazın Şirket Portalı ile Intune’a nasıl kaydedildiği açıklanır
keywords: Mac OS X, macOS, OS X
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3bb659cc-9b57-4d19-8631-2c26749fa71c
searchScope:
- User help
ROBOTS: ''
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: e3990c0670516de907ac048b844152014db5be57
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="enroll-your-macos-device-in-intune-with-the-company-portal-app"></a>Şirket Portalı uygulaması ile macOS cihazınızı Intune’a kaydetme

Kuruluşunuzun uygulamalarına, verilerine ve kaynaklarına erişmek; işinizi yapmanız kolaylaştırır. Kuruluşunuz, [bu kaynaklara erişimi yönetmek](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-macos.md) için Intune kullanıyor ve Intune, macOS için Şirket Portalı uygulamasını indirmenizi gerektiriyor. Bu yönergeler, OS X El Capitan 10.11+ sürümü macOS cihazlar için geçerlidir.

> [!NOTE]
> Öncekii macOS sürümlerini çalıştıran macOS cihazları kaydetme yönergelerini [burada](enroll-your-device-in-intune-macos-legacy.md) bulabilirsiniz.

1. Cihazınızın __Dock__ bölümünde __Safari__'yi bulun, yeni bir pencere açın ve ardından [Şirket Portalı web sitesini](https://portal.manage.microsoft.com) ziyaret edin.

2. İş veya okul hesabınızla Şirket Portalı web sitesinde oturum açın.

   [!INCLUDE [wit_nextref](includes/end-user-password-guidance.md)]


3. Oturum açtıktan sonra sayfanın sol üst köşesindeki **Menü**’ye tıklayın ve **Cihazlarım**’ı seçin.

   ![Henüz herhangi bir uygulamanın yüklenemeyeceğini gösteren web portalı ve altında Cihazlarım düğmesi ile web portalı giriş sayfasının ekran görüntüsü.](./media/macOS_enroll_001_landing_page.png)

4. __Cihazlarım__ sayfasında, kayıtlı cihazların bir listesini veya yalnızca bir başlık görürsünüz. Bu, macOS veya başka bir kayıtlı cihazınız olup olmadığına bağlıdır. Listede olmayan bir cihazı kaydetmek için şu ifadeye sahip başlığı seçin: __Cihazınız listedeyse, tanımlamak için buraya dokunun. Listede değilse, yine buraya tıklayarak cihazınızı kaydedebilirsiniz__. Kayıtlı cihazınız yoksa başlıkta **Kayıtlı cihazınız yok ifadesi yer alır. Buraya dokunarak bu cihazı kaydedin.**

    ![Listelenmemiş cihazları kaydetme veya tanımlanmamış cihazları tanımlama başlık isteminin üzerinde birkaç tanımlanmamış cihazın belirtildiği Cihazlarım sayfasının ekran görüntüsü.](./media/macOS_enroll_002_tap_here_banner.png)

5. Kayda devam etmek için macOS cihazınıza Şirket Portalı uygulamasını indirin.

    ![Kullanıcıdan macOS Şirket Portalı uygulamasını indirmesini isteyen uyarı. Bu uyarı, yukarıdaki adımda listelenen metni, sağ alt köşesinde “İndir” yazılı bir düğmeyi içerir.](./media/macOS_enroll_IWP_CP_app_notice.png)

6. Mac’iniz, **CompanyPortal.pkg** indirmesini açmanın güvenli olup olmadığını denetleyecektir. Yükleyiciyi açın ve yükleme işlemini tamamlayın.

7. Tamamladıktan sonra **Uygulamalar** klasörünüzü veya **Başlatma Çubuğu**’nu ve daha sonra **Şirket Portalı**’nı açın.

8. Mac’inizde şöyle bir ileti görüntülenecektir: **“CompanyPortal” internetten indirilmiş bir uygulama. Bunu açmak istediğinize emin misiniz?** **Aç**'a tıklayın.

   > [!NOTE]
   > Cihazınızın, kuruluşunuzun kaynaklarına erişmek için yeterli güvenliğe sahip olduğunu doğrulamak için Intune'un bilgisayarınıza erişmesi gerekir. Bilgisayarınız, Şirket Portalı uygulamasını açmayı reddederse [Ağ Geçidi Denetleyicisini](https://support.apple.com/HT202491) kapatıp uygulamayı açmayı deneyin.

9. Şirket Portalı uygulamasında ilk gördüğünüz ekran, sizden Şirket Portalı web sitesinde oturum açmak için kullandığınız iş veya okul hesabıyla **oturum açmanızı** isteyecektir.

10. Şirket Portalı, hesap bilgilerinizi onaylar ve daha sonra **Cihaz Kaydı** ve **Cihaz Uyumluluğu** durumunuzu gösterir. Mac’inizi iş için kullanmanın güvenli olduğundan emin olmanız adına gerçekleştirmeniz gereken eylemler olduğunu işaret eden bazı sarı üçgenler görürsünüz. [Cihazınızı yönetime kaydetmeye](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md) başlamak için **Başla**’ya tıklayın.

11. Mac’iniz yönetime kaydedilmeye başlar. Bu sırada bilgisayarınızın oturum açma bilgilerini sağlamanız istenebilir. Bu kayıt birkaç dakika sürebilir. Bu süre boyunca bilgisayarınızda başka şeyler yapabilirsiniz. Şirket Portalı Kurulumu tamamlandıktan sonra işiniz bittiğine dair bir ileti alırsınız.

Bu bilgiler yardımcı olmadı mı? Şirketinizin destek bölümüne danışın. İletişim bilgilerine [Şirket Portalı web sitesinden](https://portal.manage.microsoft.com#HelpDeskDialog) ulaşabilirsiniz.
