---
title: "Skycure uygulamalarını, Microsoft Authenticator uygulamasını ve iOS yapılandırma ilkesini dağıtma | Microsoft Docs"
description: "Skycure uygulamalarını, Microsoft Authenticator uygulamasını ve iOS yapılandırma ilkesini Intune klasik konsoluna dağıtın."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45826fbc-6df5-41b2-8e80-d1353f904b43
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 86fd9d7212277f9524eb4d7f225df2c7beda1313
ms.openlocfilehash: 9f09a070ec120064bdd64bfb05a39ec9e484606c
ms.lasthandoff: 03/21/2017


---

# <a name="deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy"></a>Skycure uygulamalarını, Microsoft Authenticator uygulamasını ve iOS uygulama yapılandırma ilkesini dağıtma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="before-you-begin"></a>Başlamadan önce

-   Aşağıdaki adımlar, [Intune klasik konsolunda](https://manage.microsoft.com/) tamamlanmalıdır.

-   Daha önce Skycure Yönetim konsolunda yapılandırılmış olan Azure AD hesabını kullanın. Bu, Intune klasik konsolunda oturum açarken kullanılanla aynı hesap olmalıdır.

-   Şu işlemlerin nasıl yapıldığını bildiğinizden emin olun:

    -   [Intune ile uygulama dağıtma](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune).

    -   [iOS uygulama yapılandırma ilkesini dağıtma](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

## <a name="to-deploy-skycure-apps-microsoft-authenticator-app-and-the-ios-app-configuration-policy"></a>Skycure uygulamalarını, Microsoft Authenticator uygulamasını ve iOS uygulama yapılandırma ilkesini dağıtmak için

1.  Intune klasik konsolunda, **Uygulamalar** &gt; **Uygulamalar**’ı seçin ve yönetebileceğiniz uygulamaların listesini görüntüleyin.

2.  Aşağıdaki uygulamaları seçin:

    a.  Microsoft Authenticator

    b.  Android için Skycure uygulaması

    c.  iOS için Skycure uygulaması

       ![Intune klasik konsolu dağıtılabilecek tüm uygulamalar](../media/mtp/skycure-deploy-app-1.png)

3.  **Dağıtımları Yönet**’i seçin, Skycure kullanıcılarını içeren Azure AD güvenlik grubunu seçin ve ardından **İleri**’ye tıklayın.

4.  **Dağıtım Eylemi** sayfasında, **Onay** açılan listesinden **Gerekli Yükleme**’yi seçin ve ardından **İleri**’ye tıklayın.

    ![Intune klasik konsolu Dağıtım Eylemi](../media/mtp/skycure-deploy-app-2.png)

5.  **VPN profili** sayfasında, **VPN İlkesi** açılan listesinden **Hiçbiri**’ni seçin ve ardından **İleri**’ye tıklayın.

6.  **Mobil Uygulama Yapılandırması** sayfasında, **Uygulama Yapılandırma İlkesi** açılan listesinden daha önce oluşturulmuş olan iOS Uygulama Yapılandırma İlkesini seçin ve ardından **Son**’a tıklayın.

    ![Intune klasik konsolu Mobil uygulama yapılandırması](../media/mtp/skycure-deploy-app-3.png)

## <a name="next-steps"></a>Sonraki adımlar

[Intune ile Skycure tümleştirmesini kurma](https://docs.microsoft.com/intune/deploy-use/setup-the-skycure-integration-with-Intune)

