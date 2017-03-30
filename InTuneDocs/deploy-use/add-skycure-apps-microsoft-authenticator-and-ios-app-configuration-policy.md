---
title: "Skycure uygulamalarını, Microsoft Authenticator uygulamasını ve iOS yapılandırma ilkesini ekleme | Microsoft Docs"
description: "Skycure uygulamalarını, Microsoft Authenticator uygulamasını ve iOS yapılandırma ilkesini Intune klasik konsoluna ekleyin."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 018d26f4-4a75-4e27-bb04-54f54106cb2f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 86fd9d7212277f9524eb4d7f225df2c7beda1313
ms.openlocfilehash: 2910bcc6b4b34da8c50899cac21d7c9ec926e9ec
ms.lasthandoff: 03/21/2017


---

# <a name="add-skycure-apps-microsoft-authenticator-app-and-ios-configuration-policy"></a>Skycure uygulamalarını, Microsoft Authenticator uygulamasını ve iOS yapılandırma ilkesini ekleme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Skycure uygulamalarını eklemek ve dağıtmak için Intune kullanmalısınız. Böylelikle son kullanıcılar, mobil cihazlarında bir tehdit algılandığında bildirimleri ve tehdidi ortadan kaldıracak yönergeleri alabilir.

Buna ek olarak, kullanıcıların kimliklerinin Azure AD tarafından denetlenebilmesi için [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) uygulamasına ve kullanıcıların Skycure uygulamasında oturum açarken her seferinde kullanıcı adıyla parola girmek zorunda kalmamaları için Skycure iOS uygulamasına Intune ve Azure AD Çoklu Oturum Açma (SSO) kullanmasını bildiren iOS uygulama yapılandırma ilkesine ihtiyacınız vardır.

## <a name="before-you-begin"></a>Başlamadan önce

-   Aşağıdaki adımlar, [Intune klasik konsolunda](https://manage.microsoft.com/) tamamlanmalıdır.

-   Daha önce Skycure Yönetim konsolunda yapılandırılmış olan Azure AD hesabını kullanın. Bu, Intune klasik konsolunda oturum açarken kullanılanla aynı hesap olmalıdır.

-   Skycure tümleştirme dosyasını kullanıma hazır durumda elinizin altında bulundurmalısınız. Bu, daha önce Skycure Yönetim konsolundan indirilen ve iOS uygulama yapılandırma ilkesi parametrelerinin bulunduğu **skycure\_configuration.plist** dosyasını içeren .zip dosyasıdır.

-   Şu işlemlerin nasıl yapıldığını bildiğinizden emin olun:

    -   [Intune’a uygulama ekleme](https://docs.microsoft.com/intune/deploy-use/add-apps).

    -   [Intune’a iOS uygulama yapılandırma ilkesi ekleme](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

## <a name="to-add-the-skycure-app-for-android"></a>Android için Skycure uygulaması eklemek için

1.  Intune klasik konsolunda **Uygulamalar** &gt; **Uygulama Ekle**’yi seçerek Intune Yazılım Yayımcısı’nı başlatın ve ardından **İleri**’ye tıklayın.

2.  **Yazılım kurulumu** sayfasında **Dış bağlantı**’yı seçin, sonra **URL’yi belirtin** alanının altına [Android için Skycure uygulaması url’sini](https://play.google.com/store/apps/details?id=com.skycure.skycure) yapıştırın.

    ![Intune Yazılım Yayımcısı URL’yi Belirtin](../media/mtp/skycure-add-apps-1.png)

3.  **Yazılım açıklaması** sayfasında, **Yayımcı**, **Ad** ve **Açıklama**’yı girin, **Bunu öne çıkan bir uygulama olarak görüntüleyin ve şirket portalında vurgulayın** öğesini seçin ve **İleri**’ye tıklayın.

    ![Intune Yazılım Yayımcısı Yazılım açıklaması](../media/mtp/skycure-add-apps-2.png)

4.  **Karşıya Yükle**’ye, sonra da **Kapat**’a tıklayın.

## <a name="to-add-the-skycure-app-for-ios"></a>iOS için Skycure uygulaması eklemek için

1.  Intune klasik konsolunda **Uygulamalar** &gt; **Uygulama Ekle**’yi seçerek Intune Yazılım Yayımcısı’nı başlatın ve ardından **İleri**’ye tıklayın.

2.  **Yazılım kurulumu** sayfasında **Uygulama Mağazası’ndan Yönetilen iOS Uygulaması**’nı seçin, sonra da **URL’yi belirtin** alanının altına [iOS için Skycure uygulaması url’sini](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) yapıştırın.

    ![Intune Yazılım Yayımcısı Yönetilen iOS uygulaması](../media/mtp/skycure-add-apps-3.png)

3.  **Yazılım açıklaması** sayfasında, **Yayımcı**, **Ad** ve **Açıklama**’yı girin, **Bunu öne çıkan bir uygulama olarak görüntüleyin ve şirket portalında vurgulayın** öğesini seçin ve **İleri**’ye tıklayın.

    ![Intune Yazılım Yayımcısı seçenekleri](../media/mtp/skycure-add-apps-4.png)

4.  **Gereksinimler** sayfasında, **Mobil cihaz türü**’nün altında **Herhangi biri** öğesini seçin ve ardından **İleri**’ye tıklayın.

5.  **Karşıya Yükle**’ye, sonra da **Kapat**’a tıklayın.

## <a name="to-add-the-microsoft-authenticator-app-for-ios"></a>iOS için Microsoft Authenticator uygulaması eklemek için

1.  Intune klasik konsolunda **Uygulamalar** &gt; **Uygulama Ekle**’yi seçerek Intune Yazılım Yayımcısı’nı başlatın ve ardından **İleri**’ye tıklayın.

2.  **Yazılım kurulumu** sayfasında **Uygulama Mağazası’ndan Yönetilen iOS Uygulaması**’nı seçin, sonra da **URL’yi belirtin** alanının altına [iOS için Microsoft Authenticator uygulaması url’sini](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) yapıştırın.

    ![Intune Yazılım Yayımcısı Yönetilen iOS uygulaması 2](../media/mtp/skycure-add-apps-5.png)

3.  **Yazılım açıklaması** sayfasında, **Yayımcı**, **Ad** ve **Açıklama**’yı girin, **Bunu öne çıkan bir uygulama olarak görüntüleyin ve şirket portalında vurgulayın** öğesini seçin ve **İleri**’ye tıklayın.

    ![Intune Yazılım Yayımcısı Yönetilen iOS uygulaması 3](../media/mtp/skycure-add-apps-6.png)

4.  **Gereksinimler** sayfasında, **Mobil cihaz türü**’nün altında **Herhangi biri** öğesini seçin ve ardından **İleri**’ye tıklayın.

5.  **Karşıya Yükle**’ye, sonra da **Kapat**’a tıklayın.

## <a name="to-add-the-skycure-ios-app-configuration-policy"></a>Skycure iOS uygulaması yapılandırma ilkesini eklemek için

1.  Intune klasik konsolunda **İlke** &gt; **Genel Bakış &gt; İlke Ekle**’yi seçin.

2.  İlkeler listesinde **iOS**’u genişletin, **Mobil Uygulama Yapılandırma İlkesi (iOS 8.0 ve üstü)** öğesini ve ardından **İlke Oluştur**’u seçin.

    ![iOS uygulama yapılandırma ilkesi](../media/mtp/skycure-add-apps-7.png)

3.  **İlke Oluştur** sayfasının **Genel** bölümünde, iOS uygulama yapılandırma ilkesi için bir ad ve isteğe bağlı bir açıklama sağlayın.

    a.  Not Defteri gibi bir metin düzenleyicisi kullanarak **skycure\_configuration.plist** dosyasını açın, içeriğini kopyalayın ve **Mobil Uygulama Yapılandırma İlkesi**’nin gövdesine yapıştırın, **Doğrula**’yı seçin ve sonra da **İlkeyi Kaydet**’i seçin.

       ![iOS uygulama yapılandırma ilkesi 2](../media/mtp/skycure-add-apps-8.png)

## <a name="next-steps"></a>Sonraki adımlar

[Skycure uygulamalarını, Microsoft Authenticator uygulamasını ve iOS uygulama yapılandırma ilkesini dağıtma](https://docs.microsoft.com/intune/deploy-use/deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy)
