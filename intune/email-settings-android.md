---
title: Android ve Microsoft Intune - Azure'da Android Kurumsal e-posta ayarları | Microsoft Docs
description: Bir cihaz Exchange sunucularının kullandığı yapılandırma e-posta profilleri oluşturma ve Azure Active Directory öznitelikleri alınamıyor. SSL veya SMIME etkinleştirmek, sertifikalar veya kullanıcı adı/parola ile kullanıcıların kimliğini doğrulamak ve e-posta ve zamanlamaları eşitlemek üzerinde Android ve Android iş profili cihazları Intune kullanma.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: ffe25f7e4870f2ea6969d1261f33c69362d75469
ms.sourcegitcommit: fff179f59bd542677cbd4bf3bacc24bb880e2cb6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2018
ms.locfileid: "53032036"
---
# <a name="android-and-android-enterprise-device-settings-to-configure-email-authentication-and-synchronization-in-intune"></a>Android ve Android Kurumsal cihaz ayarları Intune'da e-posta, kimlik doğrulama ve eşitlemeyi yapılandırma

Bu makalede, listeler ve Android ve Android Kurumsal cihazlarda kontrol edebilir farklı bir e-posta ayarları açıklanır. Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, bu ayarları ve e-postaları şifrelemek için SSL kullanmak, bir e-posta sunucusu yapılandırmak için kullanın.

Bir Intune yöneticisi olarak, e-posta ayarları oluşturup bunları aşağıdaki Android cihazlarına atayabilirsiniz:

- Android Samsung Knox Standard
- Android Kurumsal

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz yapılandırma profili oluşturma](email-settings-configure.md).

## <a name="android-samsung-knox"></a>Android (Samsung Knox)

- **E-posta sunucusu**: Exchange sunucunuzun konak adını girin.
- **Hesap adı**: E-posta hesabı için görünen adı girin. Bu ad, cihazlarda kullanıcılara gösterilir.
- **AAD’den kullanıcı adı özniteliği**: Bu ad, Intune’un Azure Active Directory’den (AAD) aldığı özniteliktir. Intune, bu profil tarafından kullanılan kullanıcı adını dinamik olarak oluşturur. Seçenekleriniz şunlardır:
  - **Kullanıcı Asıl Adı**: Adı alır; örneğin `user1` veya `user1@contoso.com`
  - **Kullanıcı adı**: Yalnızca adı alır; örneğin `user1`
  - **sAM Hesap Adı**: Etki alanı gerektirir; örneğin `domain\user1`. sAM hesap adı yalnızca Android cihazlar ile kullanılabilir. Android Kurumsal desteklenmez.

    Şunları da girin:  
    - **Kullanıcı etki alanı adı kaynağı**: **AAD** (Azure Active Directory) veya **Özel**’i seçin.

      Öznitelikleri **AAD**’den almayı seçerseniz şunları girin:
      - **AAD’den kullanıcı etki alanı adı**: Kullanıcının **Tam etki alanı adı** veya **NetBIOS adı** özniteliğini alma arasında seçim yapın

      **Özel** öznitelikler kullanmayı seçerseniz şunları girin:
      - **Kullanılacak özel etki alanı adı**: Intune’un etki alanı adı olarak kullanacağı bir değer seçin; örneğin `contoso.com` veya `contoso`

- **AAD’den e-posta adresi özniteliği**: Kullanıcı için e-posta adresinin nasıl oluşturulacağını seçin. E-posta adresi olarak tam asıl adı kullanmak için **Kullanıcı asıl adı**’nı (`user1@contoso.com` veya `user1`) veya Exchange’de oturum açarken birincil SMTP adresini kullanmak için **Birincil SMTP adresi**’ni (`user1@contoso.com`) seçin.

- **Kimlik doğrulama yöntemi**: E-posta profili tarafından kullanılan kimlik doğrulama yöntemi olarak **Kullanıcı Adı ve Parola**’yı veya **Sertifikalar**’ı seçin.
  - **Sertifika**’yı seçerseniz, Exchange bağlantısının kimliğini doğrulamak için daha önce oluşturduğunuz istemci SCEP veya PKCS sertifika profilini seçin.

### <a name="security-settings"></a>Güvenlik ayarları

- **SSL**: E-posta gönderirken, e-posta alırken ve Exchange sunucusuyla iletişim kurarken Güvenli Yuva Katmanı (SSL) iletişimini kullanın.
- **S/MIME**: Giden e-postaları S/MIME şifrelemesi kullanarak gönderin.
  - **Sertifika**’yı seçerseniz, Exchange bağlantısının kimliğini doğrulamak için daha önce oluşturduğunuz istemci SCEP veya PKCS sertifika profilini seçin.

### <a name="synchronization-settings"></a>Eşitleme ayarları

- **Eşitlenecek e-posta miktarı**: Eşitlemek istediğiniz e-postalar için gün sayısını seçin veya **Sınırsız**’ı seçerek kullanılabilir tüm e-postaları eşitleyin.
- **Eşitleme zamanlaması**: Cihazların Exchange sunucusundan veri eşitleyeceği zamanlamayı seçin. Ayrıca, verileri geldiğinde eşitleyen **İletiler geldiğinde** seçeneğini veya eşitlemenin cihaz kullanıcısı tarafından başlatılmasını gerektiren **El ile** seçeneğini belirleyebilirsiniz.

### <a name="content-sync-settings"></a>İçerik eşitleme ayarları

- **Eşitlenecek içerik türü**: Aşağıdaki türler arasından, cihazlara eşitlemek istediğiniz içerik türlerini seçin:
  - **Kişiler**
  - **Takvim**
  - **Görevler**

## <a name="android-enterprise"></a>Android Kurumsal

- **E-posta uygulaması**: **Gmail**’i veya **Nine Work**’ü seçin
- **E-posta sunucusu**: Exchange sunucunuzun konak adı.
- **AAD’den kullanıcı adı özniteliği**: Bu ad, bu e-posta profili için kullanıcı adı oluşturmak üzere kullanılan Active Directory (AD) veya Azure AD özniteliğidir. **Birincil SMTP Adresi** olarak user1@contoso.com gibi bir değer seçin ya da **Kullanıcı Asıl Adı**’nı (kullanıcı1 veya user1@contoso.com gibi) belirtin.
- **AAD’den e-posta adresi özniteliği**: E-posta adresinin her cihazdaki kullanıcı için nasıl oluşturulacağı. E-posta adresi olarak tam asıl adı kullanmak için **Kullanıcı Asıl Adı**'nı veya **Kullanıcı adı**'nı seçin.
- **Kimlik doğrulama yöntemi**: E-posta profili tarafından kullanılan kimlik doğrulama yöntemi olarak **Kullanıcı Adı ve Parola**’yı veya **Sertifikalar**’ı seçin.
  - **Sertifika**'yı seçtiyseniz Exchange bağlantısının kimliğini doğrulamak için daha önce oluşturduğunuz istemci SCEP veya PKCS sertifika profilini seçin.
- **SSL**: E-posta gönderirken, e-posta alırken ve Exchange sunucusuyla iletişim kurarken Güvenli Yuva Katmanı (SSL) iletişimini kullanın.
- **Eşitlenecek e-posta miktarı**: Eşitlemek istediğiniz e-postalar için gün sayısını seçin veya **Sınırsız**’ı seçerek kullanılabilir tüm e-postaları eşitleyin.
- **Eşitlenecek içerik türü** (Yalnızca Nine Work): Aşağıdakiler arasından cihazlara eşitlemek istediğiniz içerik türlerini seçin:
  - **Kişiler**
  - **Takvim**
  - **Görevler**

## <a name="next-steps"></a>Sonraki adımlar
[Intune’da e-posta ayarlarını yapılandırma](email-settings-configure.md)
