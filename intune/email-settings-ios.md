---
title: Microsoft Intune - Azure’da iOS cihazları için e-posta ayarları | Microsoft Docs
description: Exchange sunucularını kullanan ve Azure Active Directory’den öznitelik alan bir cihaz yapılandırma e-posta profili oluşturun. Microsoft Intune kullanarak ayrıca SSL’yi etkinleştirebilir, sertifika veya kullanıcı adı/parola ile kullanıcıların kimliği doğrulayabilir ve iOS cihazlarda e-posta eşitleyebilirsiniz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3a231adf4e1f5687bc88c8c9b15241d3f89e711d
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905351"
---
# <a name="email-profile-settings-for-ios-devices---intune"></a>iOS cihazlar için e-posta profili ayarları - Intune

iOS çalıştıran cihazlarınızı yapılandırmak için e-posta profili ayarlarını kullanın.

## <a name="email-settings"></a>E-posta ayarları

- **E-posta sunucusu**: Exchange sunucunuzun konak adını girin.
- **Hesap adı**: E-posta hesabı için görünen adı girin. Bu ad, cihazlarda kullanıcılara gösterilir.
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
- **Kimlik doğrulama yöntemi**: E-posta profili tarafından kullanılan kimlik doğrulama yöntemi olarak **Kullanıcı Adı ve Parola**’yı veya **Sertifikalar**’ı seçin. Azure çok faktörlü kimlik doğrulaması desteklenmez.
  - **Sertifika**’yı seçtiyseniz, Exchange bağlantısının kimliğini doğrulamak için kullanılan, daha önce oluşturduğunuz istemci SCEP veya PKCS sertifika profilini seçin.
- **SSL**: E-posta gönderirken, e-posta alırken ve Exchange sunucusuyla iletişim kurarken Güvenli Yuva Katmanı (SSL) iletişimini kullanın.
- **S/MIME**: S/MIME imzalama kullanarak giden e-posta gönderin.
  - **Sertifika**'yı seçtiyseniz Exchange bağlantısının kimliğini doğrulamak için daha önce oluşturduğunuz bir PKCS sertifika profilini seçin.
- **Eşitlenecek e-posta miktarı**: Eşitlemek istediğiniz e-posta için gün sayısını seçin. Veya **Sınırsız**’ı seçerek kullanılabilir tüm e-postaları eşitleyin.
- **İletilerin diğer e-posta hesaplarına taşınmasına izin ver**: Kullanıcıların, e-posta iletilerini cihazlarında yapılandırdıkları farklı hesaplara taşımasına izin verir.
- **Üçüncü taraf uygulamalarından e-posta gönderilmesine izin ver**: Kullanıcının, bu profili e-posta göndermek için varsayılan hesap olarak seçmesini sağlayın ve üçüncü taraf uygulamaların yerel e-posta uygulamasında e-posta açmasına izin verin (örneğin e-postaya dosya eklemek için).
- **Son kullanılan e-posta adreslerini eşitle**: Kullanıcıların cihazda son kullanılan e-posta adreslerinin listesini sunucuyla eşitlemelerine olanak tanır.

## <a name="next-steps"></a>Sonraki adımlar
[Intune’da e-posta ayarlarını yapılandırma](email-settings-configure.md)
