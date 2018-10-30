---
title: Microsoft Intune'da iOS ve Android cihazlar için Outlook ayarları
description: iOS ve Android cihazlarda çalışan Microsoft Outlook ayarlarını yapmak için bir yapılandırma ilkesi oluşturun.
keywords: ''
author: Erikre
ms.author: erikre
ms.reviewer: smithre4
manager: dougeby
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 24ed1a895dd3e4cad6111b40913b43fa9c6a3cec
ms.sourcegitcommit: 11bd3dbbc9dd762df7c6d20143f2171799712547
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/10/2018
ms.locfileid: "48903531"
---
# <a name="microsoft-outlook-configuration-settings"></a>Microsoft Outlook yapılandırma ayarları 

iOS ve Android cihazlarda çalışan Microsoft Outlook ayarlarını yapmak için bir yapılandırma ilkesi kullanın. 

Yönetilen iOS cihazlarına bir uygulama yapılandırma ilkesi oluşturmak için bkz. [Yönetilen iOS cihazları için uygulama yapılandırma ilkeleri ekleme](app-configuration-policies-use-ios.md). Yönetilen Android cihazlarına bir uygulama yapılandırma ilkesi oluşturmak için bkz. [Yönetilen Android cihazları için uygulama yapılandırma ilkeleri ekleme](app-configuration-policies-use-android.md). 

## <a name="configuration-settings"></a>Yapılandırma ayarları

Intune'da bir yapılandırma ilkesi eklerken, Microsoft Outlook'u yapılandırmak için belirli ayarlar yapabilirsiniz. **Yapılandırma ayarları** bölmesinde, e-posta hesap yapılandırmasını ayarlayabilirsiniz.

### <a name="basic-authentication-email-account-settings"></a>Temel kimlik doğrulaması e-posta hesabı ayarları
iOS ve Android için Outlook, Exchange yöneticilerine ActiveSync protokolü ile Temel kimlik doğrulaması kullanan şirket içi kullanıcılarına hesap yapılandırmalarını “gönderme” olanağı sunar. Daha fazla bilgi için bkz. [iOS ve Android için Outlook’ta Temel kimlik doğrulaması kullanılarak hesap kurulumu](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/account-setup). Hesap kurulumu yapılandırmasını etkinleştirmek için aşağıdaki ayarları yapılandırabilirsiniz:

- **E-posta sunucusu**: Şirket içi Exchange sunucunuzun ana bilgisayar adını girin (örneğin mail.contoso.com).
- **E-posta hesap adı**: E-posta hesabı için görünen adı girin. Bu ad, cihazlarda kullanıcılara gösterilir.
- **AAD'den kullanıcı adı özniteliği**: Bu ad, Intune'un Azure Active Directory'den (Azure AD) aldığı özniteliktir. Intune, bu profil tarafından kullanılan kullanıcı adını dinamik olarak oluşturur. Seçenekleriniz şunlardır:
  - **Kullanıcı Asıl Adı**: Adı alır; örneğin `user1` veya `user1@contoso.com`
  - **Birincil SMTP adresi**: Adı e-posta adresi biçiminde alır; örneğin `user1@contoso.com`
- **AAD’den e-posta adresi özniteliği**: Kullanıcı için e-posta adresinin nasıl oluşturulacağını seçin. E-posta adresi olarak tam asıl adı kullanmak için **Kullanıcı asıl adı**’nı (`user1@contoso.com` veya `user1`) veya Exchange’de oturum açarken birincil SMTP adresini kullanmak için **Birincil SMTP adresi**’ni (`user1@contoso.com`) seçin. **Birincil SMTP adresini** seçmeniz önerilir.
- **Hesap etki alanı**: (İsteğe bağlı) Hesabın etki alanı.

## <a name="next-steps"></a>Sonraki adımlar
[Intune’da e-posta ayarlarını yapılandırma](email-settings-configure.md)

