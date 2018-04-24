---
title: Android ve Android for Work çalıştıran cihazlar için Microsoft Intune e-posta ayarları
titleSuffix: ''
description: Android ve Android for Work çalıştıran cihazlarda e-posta ayarlarını yapılandırmak için kullanabileceğiniz Microsoft Intune ayarlarını öğrenin.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 10bea7ace3fe03db66fa6f8a83a94679dfdc071c
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="email-profile-settings-in-microsoft-intune-for-devices-running-android-and-android-for-work"></a>Android ve Android for Work çalıştıran cihazlar için Microsoft Intune'da e-posta profili ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makalede, Android çalıştıran cihazlarınız için yapılandırabileceğiniz e-posta profili ayarları gösterilmektedir.

Bir Intune yöneticisi olarak, e-posta ayarları oluşturup bunları aşağıdaki Android cihazlarına atayabilirsiniz:
- [Android Samsung Knox Standard](#android-samsung-knox-standard-email-settings)
- [Android for Work](#android-for-work-email-settings)

## <a name="android-samsung-knox-standard-email-settings"></a>Android Samsung Knox Standard e-posta ayarları
- **E-posta sunucusu** - Exchange sunucunuzun konak adı.
- **Hesap adı** - E-posta hesabının, cihazlarda kullanıcılara gösterilecek olan görünen adı.
- **AAD’den kullanıcı adı özniteliği** - Bu ad, bu e-posta profilinin kullanıcı adını oluşturmak üzere kullanılan Active Directory (AD) veya Azure AD özniteliğidir. **Birincil SMTP Adresi** olarak user1@contoso.com gibi bir değer seçin ya da **Kullanıcı Asıl Adı**’nı (kullanıcı1 veya user1@contoso.com gibi) belirtin.
- **AAD’den e-posta adresi özniteliği** - E-posta adresinin her cihazdaki kullanıcı için nasıl oluşturulacağı. Exchange'de oturum açarken birincil SMTP adresini kullanmak için **Birincil SMTP Adresi**'ni veya e-posta adresi olarak tam asıl adı kullanmak için **Kullanıcı Asıl Adı**'nı seçin.
- **Kimlik doğrulama yöntemi** - E-posta profili tarafından kullanılan kimlik doğrulama yöntemi olarak **Kullanıcı Adı ve Parola**’yı veya **Sertifikalar**’ı seçin.
    - **Sertifika**'yı seçtiyseniz Exchange bağlantısının kimliğini doğrulamak için daha önce oluşturduğunuz istemci SCEP veya PKCS sertifika profilini seçin.

### <a name="security-settings"></a>Güvenlik ayarları

- **SSL** - E-posta gönderirken, e-posta alırken ve Exchange sunucusuyla iletişim kurarken Güvenli Yuva Katmanı (SSL) iletişimini kullanın.
- **S/MIME** - Giden e-postaları S/MIME şifrelemesi kullanarak gönderin.
    - **Sertifika**'yı seçtiyseniz Exchange bağlantısının kimliğini doğrulamak için daha önce oluşturduğunuz istemci SCEP veya PKCS sertifika profilini seçin.

### <a name="synchronization-settings"></a>Eşitleme ayarları

- **Eşitlenecek e-posta miktarı** - Eşitlemek istediğiniz e-postalar için gün sayısını seçin veya **Sınırsız**’ı seçerek kullanılabilir tüm e-postayı eşitleyin.
- **Eşitleme zamanlaması** - Cihazların Exchange sunucusundan veri eşitleyeceği zamanlamayı seçin. Ayrıca, verileri geldiğinde eşitleyen **İletiler geldiğinde** seçeneğini veya eşitlemenin cihaz kullanıcısı tarafından başlatılmasını gerektiren **El ile** seçeneğini belirleyebilirsiniz.

### <a name="content-sync-settings"></a>İçerik eşitleme ayarları

- **Eşitlenecek içerik türü**Aşağıdaki türler arasından, cihazlara eşitlemek istediğinizi içerik türlerini seçin:
    - **Kişiler**
    - **Takvim**
    - **Görevler**

## <a name="android-for-work-email-settings"></a>Android for Work e-posta ayarları

- **E-posta uygulaması** - **Gmail**'i veya **Nine Work**'ü seçin
- **E-posta sunucusu** - Exchange sunucunuzun konak adı.
- **AAD'den kullanıcı adı özniteliği** - Bu ad, bu e-posta profili için kullanıcı adı oluşturmak üzere kullanılan Active Directory (AD) veya Azure AD özniteliğidir. **Birincil SMTP Adresi** olarak user1@contoso.com gibi bir değer seçin ya da **Kullanıcı Asıl Adı**’nı (kullanıcı1 veya user1@contoso.com gibi) belirtin.
- **AAD’den e-posta adresi özniteliği** - E-posta adresinin her cihazdaki kullanıcı için nasıl oluşturulacağı. E-posta adresi olarak tam asıl adı kullanmak için **Kullanıcı Asıl Adı**'nı veya **Kullanıcı adı**'nı seçin.
- **Kimlik doğrulama yöntemi** - E-posta profili tarafından kullanılan kimlik doğrulama yöntemi olarak **Kullanıcı Adı ve Parola**’yı veya **Sertifikalar**’ı seçin.
    - **Sertifika**'yı seçtiyseniz Exchange bağlantısının kimliğini doğrulamak için daha önce oluşturduğunuz istemci SCEP veya PKCS sertifika profilini seçin.
- **SSL** - E-posta gönderirken, e-posta alırken ve Exchange sunucusuyla iletişim kurarken Güvenli Yuva Katmanı (SSL) iletişimini kullanın.
- **Eşitlenecek e-posta miktarı** - Eşitlemek istediğiniz e-postalar için gün sayısını seçin veya **Sınırsız**’ı seçerek kullanılabilir tüm e-postayı eşitleyin.
- **Eşitlenecek içerik türü** (Yalnızca Nine Work) - Aşağıdakiler arasından cihazlara eşitlemek istediğiniz içerik türlerini seçin:
    - **Kişiler**
    - **Takvim**
    - **Görevler**
