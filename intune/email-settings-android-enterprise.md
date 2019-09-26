---
title: Microsoft Intune-Azure 'da Android kurumsal e-posta ayarları | Microsoft Docs
description: Exchange sunucularını kullanan cihaz yapılandırması e-posta profilleri oluşturun ve Azure Active Directory öznitelikleri alın. SSL veya SMIME 'yi etkinleştirin, sertifikalar veya Kullanıcı adı/parola ile kullanıcıların kimliğini doğrulayın ve Microsoft Intune kullanarak Android iş profili cihazlarındaki e-posta ve zamanlamaları eşitler.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/07/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.reviewer: maholdaa
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8e13c2dce5e8da2ce71b97de496d5234096c3b22
ms.sourcegitcommit: b78793ccbef2a644a759ca3110ea73e7ed6ceb8f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2019
ms.locfileid: "71301947"
---
# <a name="android-enterprise-device-settings-to-configure-email-authentication-and-synchronization-in-intune"></a>Intune 'da e-posta, kimlik doğrulama ve eşitlemeyi yapılandırmak için Android kurumsal cihaz ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makalede, Android kurumsal cihazlarda denetleyebilmeniz için farklı e-posta ayarları listelenir ve açıklanmaktadır. Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, bu ayarları ve e-postaları şifrelemek için SSL kullanmak, bir e-posta sunucusu yapılandırmak için kullanın.

Bir Intune Yöneticisi olarak, iş profilinde Android kurumsal cihazlara e-posta ayarları oluşturabilir ve atayabilirsiniz.

Intune 'da e-posta profilleri hakkında daha fazla bilgi için bkz. [e-posta ayarlarını yapılandırma](email-settings-configure.md)

## <a name="before-you-begin"></a>Başlamadan önce

Bir [cihaz yapılandırma profili](email-settings-configure.md#create-a-device-profile) oluşturun (iş profilini seçin) veya bir [uygulama yapılandırma ilkesi](app-configuration-policies-use-android.md)oluşturun.

## <a name="android-enterprise"></a>Android Kurumsal

- **E-posta uygulaması**: **Gmail** veya **dokuz iş** seçin
- **E-posta sunucusu**: Exchange sunucunuzun ana bilgisayar adı. Örneğin, şunu girin: `outlook.office365.com`.
- **AAD 'Den Kullanıcı adı özniteliği**: Bu ad, Intune 'un Azure Active Directory (Azure AD) 'den aldığı özniteliktir. Intune, bu profil tarafından kullanılan kullanıcı adını dinamik olarak oluşturur. Seçenekleriniz şunlardır:

  - **Kullanıcı asıl adı**: Veya gibi `user1` bir ad alır`user1@contoso.com`
  - **Kullanıcı adı**: Yalnızca adı alır, örneğin`user1`

- **AAD 'Den e-posta adresi özniteliği**: Bu ad, Intune 'un Azure AD 'den aldığı e-posta özniteliğidir. Intune, bu profil tarafından kullanılan e-posta adresini dinamik olarak oluşturur. Seçenekleriniz şunlardır:
  - **Kullanıcı asıl adı**:  E-posta adresi olarak, `user1@contoso.com` veya `user1`gibi tam asıl adı kullanır.
  - **BIRINCIL SMTP adresi**: Exchange 'de oturum açmak için gibi birincil SMTP `user1@contoso.com`adresini kullanır.

- **Kimlik doğrulama yöntemi**: E-posta profili tarafından kullanılan kimlik doğrulama yöntemi olarak **Kullanıcı adı ve parola veya Sertifikalar ' ı** seçin.
  - **Sertifika**’yı seçerseniz, Exchange bağlantısının kimliğini doğrulamak için daha önce oluşturduğunuz istemci SCEP veya PKCS sertifika profilini seçin.
- **SSL**: E-posta gönderirken, e-posta alırken ve Exchange Server ile iletişim kurarken Güvenli Yuva Katmanı (SSL) iletişimini kullanmak için **Etkinleştir** ' i seçin.
- **Eşitlenmesi yapılacak e-posta miktarı**: E-postanın eşitlenmesini istediğiniz süreyi seçin. Veya tüm kullanılabilir e-postaları eşleştirmek için **sınırsız** ' yı seçin.
- **Eşitlenecek içerik türü** (Yalnızca dokuz Iş): Cihazlarda hangi verileri eşitlemesini istediğinizi seçin. Seçenekleriniz şunlardır:
  - **Kişiler**: Son kullanıcıların kişileri cihazlarıyla eşitlemesine izin vermek için **Etkinleştir** ' i seçin.
  - **Takvim**: Son kullanıcıların takvimi cihazlarıyla eşitlemesine izin vermek için **Etkinleştir** ' i seçin.
  - **Görevler**: Son kullanıcıların tüm görevleri cihazlarıyla eşitlemesine izin vermek için **Etkinleştir** ' i seçin.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).

[Android Samsung KNOX](email-settings-android.md), [iOS](email-settings-ios.md), [Windows 10 ve üzeri](email-settings-windows-10.md)ve [Windows Phone 8,1](email-settings-windows-phone-8-1.md) cihazları için e-posta profilleri de oluşturabilirsiniz.
