---
title: Microsoft Intune'da iOS ve Android cihazlar için Outlook ayarları
description: iOS ve Android cihazlarda çalışan Microsoft Outlook ayarlarını yapmak için bir yapılandırma ilkesi oluşturun.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7fc9f34bbd3d14ac4291582247b1e45169c2cccc
ms.sourcegitcommit: d92caead1d96151fea529c155bdd7b554a2ca5ac
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2018
ms.locfileid: "48828940"
---
# <a name="microsoft-outlook-configuration-settings"></a>Microsoft Outlook yapılandırma ayarları 

iOS ve Android cihazlarda çalışan Microsoft Outlook ayarlarını yapmak için bir yapılandırma ilkesi kullanın. 

Yönetilen iOS cihazlarına bir uygulama yapılandırma ilkesi oluşturmak için bkz. [Yönetilen iOS cihazları için uygulama yapılandırma ilkeleri ekleme](app-configuration-policies-use-ios.md). Yönetilen Android cihazlarına bir uygulama yapılandırma ilkesi oluşturmak için bkz. [Yönetilen Android cihazları için uygulama yapılandırma ilkeleri ekleme](app-configuration-policies-use-android.md). 

## <a name="configuration-settings"></a>Yapılandırma ayarları

Intune'da bir yapılandırma ilkesi eklerken, Microsoft Outlook'u yapılandırmak için belirli ayarlar yapabilirsiniz. **Yapılandırma ayarları** bölmesinde, e-posta hesap yapılandırmasını ayarlayabilirsiniz.

### <a name="email-account-settings"></a>E-posta hesap ayarları

Aşağıdaki yapılandırma ayarları Microsoft Outlook'a özeldir.

- **E-posta sunucusu**: Exchange sunucunuzun konak adını girin.
- **E-posta hesap adı**: E-posta hesabı için görünen adı girin. Bu ad, cihazlarda kullanıcılara gösterilir.
- **AAD’den kullanıcı adı özniteliği**: Bu ad, Intune’un Azure Active Directory’den (AAD) aldığı özniteliktir. Intune, bu profil tarafından kullanılan kullanıcı adını dinamik olarak oluşturur. Seçenekleriniz şunlardır:
  - **Kullanıcı Asıl Adı**: Adı alır; örneğin `user1` veya `user1@contoso.com`
  - **Birincil SMTP adresi**: Adı e-posta adresi biçiminde alır; örneğin `user1@contoso.com`
  - **sAM Hesap Adı**: Etki alanı gerektirir; örneğin `domain\user1`.

    Şunları da girin:  
    - **Kullanıcı etki alanı adı kaynağı**: **AAD** (Azure Active Directory) veya **Özel**’i seçin.

      Öznitelikleri **AAD**’den almayı seçerseniz şunları girin:
      - **AAD’den kullanıcı etki alanı adı**: Kullanıcının **Tam etki alanı adı** veya **NetBIOS adı** özniteliğini alma arasında seçim yapın

      **Özel** öznitelikler kullanmayı seçerseniz şunları girin:
      - **Kullanılacak özel etki alanı adı**: Intune’un etki alanı adı olarak kullanacağı bir değer seçin; örneğin `contoso.com` veya `contoso`

- **AAD’den e-posta adresi özniteliği**: Kullanıcı için e-posta adresinin nasıl oluşturulacağını seçin. E-posta adresi olarak tam asıl adı kullanmak için **Kullanıcı asıl adı**’nı (`user1@contoso.com` veya `user1`) veya Exchange’de oturum açarken birincil SMTP adresini kullanmak için **Birincil SMTP adresi**’ni (`user1@contoso.com`) seçin.
- **Hesap etki alanı**: (İsteğe bağlı) Hesabın etki alanı.

## <a name="next-steps"></a>Sonraki adımlar
[Intune’da e-posta ayarlarını yapılandırma](email-settings-configure.md)

