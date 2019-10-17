---
title: Microsoft Intune - Azure’da Windows 10 cihazlar için e-posta ayarları | Microsoft Docs
description: Exchange sunucularını kullanan ve Azure Active Directory’den öznitelik alan bir cihaz yapılandırma e-posta profili oluşturun. Microsoft Intune kullanarak SSL’yi de etkinleştirebilir ve Windows 10 cihazlarda e-posta ve zamanlamaları eşitleyebilirsiniz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/29/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9882749ec90f2a1de4edf53535a79d893ca60e63
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72492816"
---
# <a name="email-profile-settings-for-devices-running-windows-10---intune"></a>Windows 10 çalıştıran cihazlar için e-posta profili ayarları - Intune

Windows 10 çalıştıran cihazlarınızda posta uygulamasını yapılandırmak için e-posta profili ayarlarını kullanın.

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

## <a name="security-settings"></a>Güvenlik ayarları

- **SSL**: E-posta gönderirken, e-posta alırken ve Exchange sunucusuyla iletişim kurarken Güvenli Yuva Katmanı (SSL) iletişimini kullanın.

## <a name="synchronization-settings"></a>Eşitleme ayarları

- **Eşitlenecek e-posta miktarı**: Eşitlemek istediğiniz e-posta için gün sayısını seçin. Veya **Sınırsız**’ı seçerek kullanılabilir tüm e-postaları eşitleyin.
- **Eşitleme zamanlaması**: Cihazların Exchange sunucusundan verileri eşitleyeceği zamanlamayı seçin. Ayrıca, verileri ulaşır ulaşmaz eşitleyen **İletiler geldiğinde** veya eşitlemenin cihaz kullanıcısı tarafından başlatılmasını gerektiren **El ile** seçeneklerini de belirleyebilirsiniz.

## <a name="content-sync-settings"></a>İçerik eşitleme ayarları

- **Eşitlenecek içerik türü**: Aşağıdaki türler arasından, cihazlara eşitlemek istediğiniz içerik türlerini seçin:
  - **Kişiler**
  - **Takvim**
  - **Görevler**

## <a name="next-steps"></a>Sonraki adımlar
[Intune’da e-posta ayarlarını yapılandırma](../email-settings-configure.md)
