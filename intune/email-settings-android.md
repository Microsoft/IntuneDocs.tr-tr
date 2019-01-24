---
title: Microsoft Intune - Azure'da Android e-posta ayarları | Microsoft Docs
description: Bir cihaz Exchange sunucularının kullandığı yapılandırma e-posta profilleri oluşturma ve Azure Active Directory öznitelikleri alınamıyor. SSL veya SMIME etkinleştirme, sertifikalar veya kullanıcı adı/parola ile kullanıcıların kimliğini doğrulamak ve e-posta ve zamanlamaları Intune kullanarak Android Samsung Knox cihazları eşitleyin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/15/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 4336be8d24ac4a81ec6fca09f22d594000bbd9a5
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54831403"
---
# <a name="android-device-settings-to-configure-email-authentication-and-synchronization-in-intune"></a>Intune'da e-posta, kimlik doğrulama ve eşitleme yapılandırma android cihaz ayarları

Bu makale, listeler ve Android Samsung Knox cihazları ıntune'da denetleyebileceğiniz farklı bir e-posta ayarlarını açıklar. Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, bu ayarları ve e-postaları şifrelemek için SSL kullanmak, bir e-posta sunucusu yapılandırmak için kullanın.

Bir Intune Yöneticisi olarak oluşturun ve Android Samsung Knox Standard cihazları için e-posta ayarları atayın.

Intune'da e-posta profilleri hakkında daha fazla bilgi için bkz: [e-posta ayarlarını yapılandırma](email-settings-configure.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz yapılandırma profili oluşturma](email-settings-configure.md#create-a-device-profile).

## <a name="android-samsung-knox"></a>Android (Samsung Knox)

- **E-posta sunucusu**: Exchange sunucunuzun konak adı girin. Örneğin, şunu girin: `outlook.office365.com`.
- **Hesap adı**: E-posta hesabı için görünen ad girin. Bu ad, cihazlarda kullanıcılara gösterilir.
- **Aad'den kullanıcı adı özniteliği**: Bu ad, Azure Active Directory'den (Azure AD) Intune alır özniteliğidir. Intune, bu profil tarafından kullanılan kullanıcı adını dinamik olarak oluşturur. Seçenekleriniz şunlardır:
  - **Kullanıcı asıl adı**: Adı aşağıdaki gibi alır `user1` veya `user1@contoso.com`
  - **Kullanıcı adı**: Ad yalnızca aşağıdaki gibi alır `user1`
  - **sAM hesabı adı**: Etki alanı gibi gerektirir `domain\user1`. sAM hesabı adı yalnızca Android cihazlarıyla kullanılır.

    Şunları da girin:  
    - **Kullanıcı etki alanı adı kaynağı**: Seçin **AAD** (Azure Active Directory) veya **özel**.

      Öznitelikleri **AAD**’den almayı seçerseniz şunları girin:
      - **Kullanıcı etki alanı adı AAD özniteliğinden**: Almak için seçtiğiniz **tam etki alanı adı** veya **NetBIOS adı** kullanıcı özniteliği

      **Özel** öznitelikler kullanmayı seçerseniz şunları girin:
      - **Kullanılacak özel etki alanı adı**: Intune için etki alanı adı gibi kullanan bir değer girin `contoso.com` veya `contoso`

- **Aad'den e-posta adresi özniteliği**: Intune Azure AD'den alır e-posta özniteliği adıdır. Intune, bu profili tarafından kullanılan e-posta adresini dinamik olarak oluşturur. Seçenekleriniz şunlardır:
  - **Kullanıcı asıl adı**:  Tam asıl adı gibi kullanan `user1@contoso.com` veya `user1`, e-posta adresi.
  - **Birincil SMTP adresi**: Birincil SMTP adresi gibi kullanan `user1@contoso.com`, Exchange'de oturum açmak için.

- **Kimlik doğrulama yöntemi**: E-posta profili tarafından kullanılan kimlik doğrulama yöntemi olarak **Kullanıcı Adı ve Parola**’yı veya **Sertifikalar**’ı seçin.
  - **Sertifika**’yı seçerseniz, Exchange bağlantısının kimliğini doğrulamak için daha önce oluşturduğunuz istemci SCEP veya PKCS sertifika profilini seçin.

### <a name="security-settings"></a>Güvenlik ayarları

- **SSL**: E-posta gönderirken, e-posta alırken ve Exchange sunucusuyla iletişim kurarken Güvenli Yuva Katmanı (SSL) iletişimini kullanın.
- **S/MIME**: S/MIME şifrelemesi kullanarak giden e-posta gönderin.
  - **Sertifika**’yı seçerseniz, Exchange bağlantısının kimliğini doğrulamak için daha önce oluşturduğunuz istemci SCEP veya PKCS sertifika profilini seçin.

### <a name="synchronization-settings"></a>Eşitleme ayarları

- **Eşitlenecek e-posta miktarı**: E-posta eşitleme veya seçmek istediğiniz gün sayısını seçin **sınırsız** tüm kullanılabilir e-postayı eşitleyin.
- **Eşitleme zamanlaması**: Cihazların Exchange Server'dan verileri eşitlemek için zamanlamayı seçin. Ayrıca, verileri geldiğinde eşitleyen **İletiler geldiğinde** seçeneğini veya eşitlemenin cihaz kullanıcısı tarafından başlatılmasını gerektiren **El ile** seçeneğini belirleyebilirsiniz.

### <a name="content-sync-settings"></a>İçerik eşitleme ayarları

- **Eşitlenecek içerik türü**: Cihazlara eşitlemek istediğiniz içerik türlerini seçin. **Yapılandırılmamış** bu ayarı devre dışı bırakır. Ayarlandığında **yapılandırılmadı**, cihazı Intune ile eşitlenen ilke güçlendirilmiş gibi bir son kullanıcı etkinleştirir eşitleme eşitleme cihazı tekrar devre dışı bırakılır. 

  Aşağıdaki içeriğe eşitleyebilirsiniz:  
  - **Kişiler**: Seçin **etkinleştirme** son kullanıcıların cihazlarını kişilere eşitleme izin vermek için.
  - **Takvim**: Seçin **etkinleştirme** son kullanıcıların cihazlarını Takvim eşitleme izin vermek için.
  - **Görevleri**: Seçin **etkinleştirme** son kullanıcıların cihazlarını herhangi bir göreve eşitleme izin vermek için.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).

E-posta profillerini oluşturabilirsiniz [Android Enterprise - iş profili](email-settings-android-enterprise.md), [iOS](email-settings-ios.md), [Windows 10 ve üzeri](email-settings-windows-10.md), ve [Windows Phone 8.1](email-settings-windows-phone-8-1.md).
