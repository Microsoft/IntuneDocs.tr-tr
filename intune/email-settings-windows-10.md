---
title: Microsoft Intune - Azure’da Windows 10 cihazlar için e-posta ayarları | Microsoft Docs
description: Exchange sunucularını kullanan ve Azure Active Directory’den öznitelik alan bir cihaz yapılandırma e-posta profili oluşturun. Microsoft Intune kullanarak SSL’yi de etkinleştirebilir ve Windows 10 cihazlarda e-posta ve zamanlamaları eşitleyebilirsiniz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/29/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3e2b3708b6b0c75a1384a7cdbdb524dff3f0627d
ms.sourcegitcommit: 9a4c5b6c2ce511edaeace25426a23f180cb71e15
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/07/2019
ms.locfileid: "57565443"
---
# <a name="email-profile-settings-for-devices-running-windows-10---intune"></a>Windows 10 çalıştıran cihazlar için e-posta profili ayarları - Intune

E-posta profili ayarları, Windows 10 çalıştıran cihazlarınıza posta uygulamasını yapılandırmak için kullanın.

- **E-posta sunucusu**: Exchange sunucunuzun konak adı girin.
- **Hesap adı**: E-posta hesabı için görünen ad girin. Bu ad, cihazlarda kullanıcılara gösterilir.
- **Aad'den kullanıcı adı özniteliği**: Bu ad, Azure Active Directory (AAD gelen) Intune alır özniteliğidir. Intune, bu profil tarafından kullanılan kullanıcı adını dinamik olarak oluşturur. Seçenekleriniz şunlardır:
  - **Kullanıcı asıl adı**: Adı aşağıdaki gibi alır `user1` veya `user1@contoso.com`
  - **Birincil SMTP adresi**: Adı gibi e-posta adresi biçiminde alır `user1@contoso.com`
  - **sAM hesabı adı**: Etki alanı gibi gerektirir `domain\user1`.

    Şunları da girin:  
    - **Kullanıcı etki alanı adı kaynağı**: Seçin **AAD** (Azure Active Directory) veya **özel**.

      Öznitelikleri **AAD**’den almayı seçerseniz şunları girin:
      - **Kullanıcı etki alanı adı AAD özniteliğinden**: Almak için seçtiğiniz **tam etki alanı adı** veya **NetBIOS adı** kullanıcı özniteliği

      **Özel** öznitelikler kullanmayı seçerseniz şunları girin:
      - **Kullanılacak özel etki alanı adı**: Intune için etki alanı adı gibi kullanan bir değer girin `contoso.com` veya `contoso`

- **Aad'den e-posta adresi özniteliği**: Kullanıcı için e-posta adresinin nasıl oluşturulacağını seçin. E-posta adresi olarak tam asıl adı kullanmak için **Kullanıcı asıl adı**’nı (`user1@contoso.com` veya `user1`) veya Exchange’de oturum açarken birincil SMTP adresini kullanmak için **Birincil SMTP adresi**’ni (`user1@contoso.com`) seçin.

## <a name="security-settings"></a>Güvenlik ayarları

- **SSL**: E-posta gönderirken, e-posta alırken ve Exchange sunucusuyla iletişim kurarken Güvenli Yuva Katmanı (SSL) iletişimini kullanın.

## <a name="synchronization-settings"></a>Eşitleme ayarları

- **Eşitlenecek e-posta miktarı**: Eşitlemek istediğiniz e-postanın gün sayısını seçin. Veya **Sınırsız**’ı seçerek kullanılabilir tüm e-postaları eşitleyin.
- **Eşitleme zamanlaması**: Ayrıca seçebilir Exchange sunucusundan verileri eşitlemek cihazlar için zamanlamayı seçin **iletiler geldiğinde**, verileri eşitleyen, ulaşır ulaşmaz veya **el ile**burada cihazın kullanıcısı eşitlemenin başlatılması gerekir.

## <a name="content-sync-settings"></a>İçerik eşitleme ayarları

- **Eşitlenecek içerik türü**: Arasından cihazlara eşitlemek istediğiniz içerik türlerini seçin:
  - **Kişiler**
  - **Takvim**
  - **Görevler**

## <a name="next-steps"></a>Sonraki adımlar
[Intune’da e-posta ayarlarını yapılandırma](email-settings-configure.md)
