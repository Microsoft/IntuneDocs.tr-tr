---
title: Skycure iOS uygulaması yapılandırma ilkesini indirme
description: Son kullanıcılara dağıtılan Skycure iOS uygulamasıyla kullanmak üzere Skycure iOS uygulaması yapılandırma ilkesini indirin.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 03/16/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d211b876-4d3a-473c-999f-843c0a16cd22
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0f8197146d8b4f42bcf199070551ba13aed92626
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="download-skycure-ios-app-configuration-policy"></a>Skycure iOS uygulaması yapılandırma ilkesini indirme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

##<a name="before-you-begin"></a>Başlamadan önce

Sonraki adımları gerçekleştirmek için Skycure Yönetim Konsolu’nda oturum açmalısınız.

> [!TIP] 
> Microsoft Internet Explorer 11 veya Edge kullanıyorsanız, Skycure Yönetim konsolunu açarken In-Private modunu kullanmanız gerekebilir.

## <a name="to-download-the-ios-app-configuration-policy"></a>iOS uygulaması yapılandırma ilkesini indirmek için

1.  [Skycure Yönetim Konsolu](https://aad.skycure.com)’na gidin.

2.  **Skycure yönetici kimlik bilgilerinizi** girin ve **Devam**’a tıklayın.

    ![Skycure Yönetim konsolu oturum açma](../media/mtp/skycure-ios-app-1.png)

    > [!IMPORTANT] 
    > Skycure yöneticisi kullanıcı adı, Azure Active Directory’de geçerli bir kullanıcı hesabı olması gereken bir e-posta hesabıdır; böyle olmazsa, oturum açılamaz. Skycure, Çoklu Oturum Açma (SSO) kullanarak yöneticisinin kullanıcı adını doğrulamak için Azure Active Directory kullanır.

3.  **Ayarlar** &gt; **Cihaz Yönetimi Tümleştirmeleri** &gt; **EMM Tümleştirme Seçimi**’ne gidin, **Microsoft Intune**’u seçin ve ardından seçiminizi kaydedin.

2.  **Tümleştirme kurulum dosyaları** bağlantısına tıklayın ve oluşturulan \*.zip dosyasını kaydedin. Bu .zip dosyası, klasik Intune portalında iOS uygulaması yapılandırma ilkesini oluşturmak için kullanılacak olan **skycure\_configuration.plist** dosyasını içerir.

![Skycure Tümleştirmesi kurulum dosyaları](../media/mtp/skycure-ios-app-2.png)

## <a name="next-steps"></a>Sonraki adımlar

[Skycure uygulamalarını, Microsoft Authenticator uygulamasını ve iOS yapılandırma ilkesini ekleme](/intune-classic/deploy-use/add-skycure-apps-microsoft-authenticator-and-ios-app-configuration-policy)
