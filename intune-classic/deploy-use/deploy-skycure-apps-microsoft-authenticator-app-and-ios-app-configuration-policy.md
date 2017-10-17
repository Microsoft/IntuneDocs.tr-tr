---
title: "Skycure uygulamaları, Microsoft Authenticator uygulaması ve iOS yapılandırma ilkesi dağıtma"
description: "Skycure uygulamalarını, Microsoft Authenticator uygulamasını ve iOS yapılandırma ilkesini klasik Intune portalına dağıtın."
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
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 47b5010c2e4262f61ca8e67727697493ace54928
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/10/2017
---
# <a name="deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy"></a>Skycure uygulamalarını, Microsoft Authenticator uygulamasını ve iOS uygulama yapılandırma ilkesini dağıtma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="before-you-begin"></a>Başlamadan önce

-   Aşağıdaki adımlar, [klasik Intune portalında](https://manage.microsoft.com/) tamamlanmalıdır.

-   Daha önce Skycure Yönetim konsolunda yapılandırılmış olan Azure AD hesabını kullanın. Bu, klasik Intune portalında oturum açarken kullanılan hesap olmalıdır.

-   Şu işlemlerin nasıl yapıldığını bildiğinizden emin olun:

    -   [Intune ile uygulama dağıtma](/intune-classic/deploy-use/deploy-apps-in-microsoft-intune).

    -   [iOS uygulama yapılandırma ilkesini dağıtma](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

## <a name="to-deploy-skycure-apps-microsoft-authenticator-app-and-the-ios-app-configuration-policy"></a>Skycure uygulamalarını, Microsoft Authenticator uygulamasını ve iOS uygulama yapılandırma ilkesini dağıtmak için

1.  Klasik Intune portalında **Uygulamalar** &gt; **Uygulamalar**’ı seçerek yönetebileceğiniz uygulamaların listesini görüntüleyin.

2.  Aşağıdaki uygulamaları seçin:

    a.  Microsoft Authenticator

    b.  Android için Skycure uygulaması

    c.  iOS için Skycure uygulaması

       ![Klasik Intune portalı dağıtılabilecek tüm uygulamalar](../media/mtp/skycure-deploy-app-1.png)

3.  **Dağıtımları Yönet**’i seçin, Skycure kullanıcılarını içeren Azure AD güvenlik grubunu seçin ve ardından **İleri**’ye tıklayın.

4.  **Dağıtım Eylemi** sayfasında, **Onay** açılan listesinden **Gerekli Yükleme**’yi seçin ve ardından **İleri**’ye tıklayın.

    ![Klasik Intune portalı Dağıtım Eylemi](../media/mtp/skycure-deploy-app-2.png)

5.  **VPN profili** sayfasında, **VPN İlkesi** açılan listesinden **Hiçbiri**’ni seçin ve ardından **İleri**’ye tıklayın.

6.  **Mobil Uygulama Yapılandırması** sayfasında, **Uygulama Yapılandırma İlkesi** açılan listesinden daha önce oluşturulmuş olan iOS Uygulama Yapılandırma İlkesini seçin ve ardından **Son**’a tıklayın.

    ![Klasik Intune portalı Mobil uygulama yapılandırması](../media/mtp/skycure-deploy-app-3.png)

## <a name="next-steps"></a>Sonraki adımlar

[Intune ile Skycure tümleştirmesini kurma](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)
