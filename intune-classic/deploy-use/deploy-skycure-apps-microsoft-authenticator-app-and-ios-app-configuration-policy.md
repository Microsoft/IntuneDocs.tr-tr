---
title: "Skycure uygulamaları, Microsoft Authenticator uygulaması ve iOS yapılandırma ilkesi dağıtma"
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
ms.openlocfilehash: 60f4ab5a656a2e253d82971d7bea6b3a6c9eb25a
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy"></a>Skycure uygulamalarını, Microsoft Authenticator uygulamasını ve iOS uygulama yapılandırma ilkesini dağıtma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="before-you-begin"></a>Başlamadan önce

-   Aşağıdaki adımlar, [Intune klasik konsolunda](https://manage.microsoft.com/) tamamlanmalıdır.

-   Daha önce Skycure Yönetim konsolunda yapılandırılmış olan Azure AD hesabını kullanın. Bu, Intune klasik konsolunda oturum açarken kullanılanla aynı hesap olmalıdır.

-   Şu işlemlerin nasıl yapıldığını bildiğinizden emin olun:

    -   [Intune ile uygulama dağıtma](/intune-classic/deploy-use/deploy-apps-in-microsoft-intune).

    -   [iOS uygulama yapılandırma ilkesini dağıtma](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

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

[Intune ile Skycure tümleştirmesini kurma](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)
