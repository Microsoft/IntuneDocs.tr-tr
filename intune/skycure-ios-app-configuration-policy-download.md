---
title: "Intune ile kullanmak üzere Skycure iOS uygulama yapılandırma ilkesini indirme"
titlesuffix: Azure portal
description: "Intune ile kullanmak üzere Skycure iOS uygulama yapılandırma ilkesini indirin."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1bdc2ecf-32d0-4b6a-80b4-dbcdb9909010
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 296d5545530e8001c0648bafac3101b94f45529d
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2017
---
# <a name="download-skycure-ios-app-configuration-policy"></a>Skycure iOS uygulaması yapılandırma ilkesini indirme

## <a name="before-you-begin"></a>Başlamadan önce

Sonraki adımları gerçekleştirmek için Skycure Yönetim Konsolu’nda oturum açmalısınız.

> [!TIP] 
> Microsoft Internet Explorer 11 veya Edge kullanıyorsanız, Skycure Yönetim konsolunu açarken In-Private modunu kullanmanız gerekebilir.

## <a name="to-download-the-ios-app-configuration-policy"></a>iOS uygulaması yapılandırma ilkesini indirmek için

1.  [Skycure Yönetim Konsolu](https://aad.skycure.com)’na gidin.

2.  **Skycure yönetici kimlik bilgilerinizi** girin ve **Devam**’a tıklayın.

    ![Skycure Yönetim konsolu oturum açma](./media/skycure-ios-app-1.png)

    > [!IMPORTANT] 
    > Skycure yöneticisi kullanıcı adı, Azure Active Directory’de geçerli bir kullanıcı hesabı olması gereken bir e-posta hesabıdır; böyle olmazsa, oturum açılamaz. Skycure, Çoklu Oturum Açma (SSO) kullanarak yöneticisinin kullanıcı adını doğrulamak için Azure Active Directory kullanır.

3.  **Ayarlar** &gt; **Cihaz Yönetimi Tümleştirmeleri** &gt; **EMM Tümleştirme Seçimi**’ne gidin, **Microsoft Intune**’u seçin ve ardından seçiminizi kaydedin.

4.  **Tümleştirme kurulum dosyaları** bağlantısına tıklayın ve oluşturulan \*.zip dosyasını kaydedin. Bu .zip dosyası, klasik Intune portalında iOS uygulaması yapılandırma ilkesini oluşturmak için kullanılacak olan **skycure\_configuration.plist** dosyasını içerir.

![Skycure Tümleştirmesi kurulum dosyaları](./media/skycure-ios-app-2.png)

## <a name="next-steps"></a>Sonraki adımlar

[Skycure uygulamaları, Microsoft Authenticator uygulaması ve iOS yapılandırma ilkesini ekleme ve atama](mtd-apps-ios-app-configuration-policy-add-assign.md)
