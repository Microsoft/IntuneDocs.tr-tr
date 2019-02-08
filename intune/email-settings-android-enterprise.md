---
title: Microsoft Intune - Azure'da Android Kurumsal e-posta ayarları | Microsoft Docs
description: Cihaz Exchange sunucularının kullandığı yapılandırma e-posta profilleri oluşturma ve Azure Active Directory öznitelikleri alınamıyor. SSL veya SMIME etkinleştirme, sertifikalar veya kullanıcı adı/parola ile kullanıcıların kimliğini doğrulamak ve e-posta ve Microsoft Intune kullanarak Android iş profili cihazları zamanlamalarda eşitleyin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/10/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: e95159b4ce0cd4b1daa90a9da96b214c4cf80f70
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55847673"
---
# <a name="android-enterprise-device-settings-to-configure-email-authentication-and-synchronization-in-intune"></a>Intune'da e-posta, kimlik doğrulama ve eşitleme yapılandırma android Kurumsal cihaz ayarları

Bu makalede, listeler ve Android Kurumsal cihazlarda kontrol edebilir farklı bir e-posta ayarları açıklanır. Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, bu ayarları ve e-postaları şifrelemek için SSL kullanmak, bir e-posta sunucusu yapılandırmak için kullanın.

Bir Intune Yöneticisi olarak oluşturabilir ve e-posta ayarları iş profilinde Android kuruluş cihazlarının atayın.

Intune'da e-posta profilleri hakkında daha fazla bilgi için bkz: [e-posta ayarlarını yapılandırma](email-settings-configure.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz yapılandırma profili oluşturma](email-settings-configure.md#create-a-device-profile)ve iş profili seçin.

## <a name="android-enterprise"></a>Android Kurumsal

- **E-posta uygulaması**: Şunlardan birini seçin **Gmail** veya **dokuz çalışma**
- **E-posta sunucusu**: Exchange sunucunuzun konak adı. Örneğin, şunu girin: `outlook.office365.com`.
- **Aad'den kullanıcı adı özniteliği**: Bu ad, Azure Active Directory'den (Azure AD) Intune alır özniteliğidir. Intune, bu profil tarafından kullanılan kullanıcı adını dinamik olarak oluşturur. Seçenekleriniz şunlardır:

  - **Kullanıcı asıl adı**: Adı aşağıdaki gibi alır `user1` veya `user1@contoso.com`
  - **Kullanıcı adı**: Ad yalnızca aşağıdaki gibi alır `user1`

- **Aad'den e-posta adresi özniteliği**: Intune Azure AD'den alır e-posta özniteliği adıdır. Intune, bu profili tarafından kullanılan e-posta adresini dinamik olarak oluşturur. Seçenekleriniz şunlardır:
  - **Kullanıcı asıl adı**:  Tam asıl adı gibi kullanan `user1@contoso.com` veya `user1`, e-posta adresi.
  - **Birincil SMTP adresi**: Birincil SMTP adresi gibi kullanan `user1@contoso.com`, Exchange'de oturum açmak için.

- **Kimlik doğrulama yöntemi**: Seçin **kullanıcı adı ve parola** veya **sertifikaları** e-posta profili tarafından kullanılan kimlik doğrulama yöntemi olarak.
  - **Sertifika**’yı seçerseniz, Exchange bağlantısının kimliğini doğrulamak için daha önce oluşturduğunuz istemci SCEP veya PKCS sertifika profilini seçin.
- **SSL**: Seçin **etkinleştirme** e-posta alırken ve Exchange sunucusuyla iletişim kurarken gönderirken, Güvenli Yuva Katmanı (SSL) iletişimini kullanmak için.
- **Eşitlenecek e-posta miktarı**: Eşitlemek istediğiniz e-postanın süre miktarını seçin. Ya da seçin **sınırsız** tüm kullanılabilir e-postayı eşitleyin.
- **Eşitlenecek içerik türü** (yalnızca Nine Work): Cihazlara eşitlemek istediğiniz hangi verileri seçin. Seçenekleriniz şunlardır:
  - **Kişiler**: Seçin **etkinleştirme** son kullanıcıların cihazlarını kişilere eşitleme izin vermek için.
  - **Takvim**: Seçin **etkinleştirme** son kullanıcıların cihazlarını Takvim eşitleme izin vermek için.
  - **Görevleri**: Seçin **etkinleştirme** son kullanıcıların cihazlarını herhangi bir göreve eşitleme izin vermek için.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).

E-posta profillerini oluşturabilirsiniz [Android Samsung Knox](email-settings-android.md), [iOS](email-settings-ios.md), [Windows 10 ve üzeri](email-settings-windows-10.md), ve [Windows Phone 8.1](email-settings-windows-phone-8-1.md) cihazlar.