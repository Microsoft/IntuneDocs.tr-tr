---
title: Configure Email settings for iOS devices in Microsoft Intune - Azure | Microsoft Docs
description: See a list of all the email settings you can configure and add to iOS devices in Microsoft Intune, including using Exchange servers, and getting attributes from Azure Active Directory. You can also enable SSL, authenticate users with certificates or username/password, and synchronize email on iOS devices using device configuration profiles in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/12/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 73de0ac94ff02e43fe73ca6357f6008ba71e3b93
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74390829"
---
# <a name="add-e-mail-settings-for-ios-devices-in-microsoft-intune"></a>Add e-mail settings for iOS devices in Microsoft Intune

In Microsoft Intune, you can create and configure email to connect to an email server, choose how users authenticate, use S/MIME for encryption, and more.

This article lists and describes all the email settings available for devices running iOS. You can create a device configuration profile to push or deploy these email settings to your iOS devices.

## <a name="before-you-begin"></a>Başlamadan önce

[Create a device configuration profile](../email-settings-configure.md).

> [!NOTE]
> These settings are available for all enrollment types. For more information on the enrollment types, see [iOS enrollment](../ios-enroll.md).

## <a name="exchange-activesync-account-settings"></a>Exchange ActiveSync account settings

- **E-posta sunucusu**: Exchange sunucunuzun konak adını girin.
- **Hesap adı**: E-posta hesabı için görünen adı girin. Bu ad, cihazlarda kullanıcılara gösterilir.
- **AAD’den kullanıcı adı özniteliği**: Bu ad, Intune’un Azure Active Directory’den (AAD) aldığı özniteliktir. Intune, bu profil tarafından kullanılan kullanıcı adını dinamik olarak oluşturur. Seçenekleriniz şunlardır:
  - **Kullanıcı Asıl Adı**: Adı alır; örneğin `user1` veya `user1@contoso.com`
  - **Birincil SMTP adresi**: Adı e-posta adresi biçiminde alır; örneğin `user1@contoso.com`
  - **sAM Hesap Adı**: Etki alanı gerektirir; örneğin `domain\user1`. Şunları da girin:  
    - **Kullanıcı etki alanı adı kaynağı**: **AAD** (Azure Active Directory) veya **Özel**’i seçin.
      - **AAD**: Get the attributes from Azure AD. Şunları da girin:
        - **User domain name attribute from AAD**: Choose to get the **Full domain name** (`contoso.com`) or the **NetBIOS name** (`contoso`) attribute of the user.

      - **Custom**: Get the attributes from a custom domain name. Şunları da girin:
        - **Custom domain name to use**: Enter a value that Intune uses for the domain name, such as `contoso.com` or `contoso`.

- **AAD’den e-posta adresi özniteliği**: Kullanıcı için e-posta adresinin nasıl oluşturulacağını seçin. Seçenekleriniz şunlardır:
  - **User principal name**: Use the full principal name as the email address, such as `user1@contoso.com` or `user1`.
  - **Primary SMTP address**: Use the primary SMTP address to sign in to Exchange, such as `user1@contoso.com`.
- **Authentication method**: Choose how users to authenticate to the email server. Seçenekleriniz şunlardır:
  - **Certificate**: Select a client SCEP or PKCS certificate profile you previously created to authenticate the Exchange connection. This option provides the most secure and seamless experience for your users.
  - **Username and Password**: Users are prompted to enter their user name and password.
  - **Derived credential**: Use a certificate that’s derived from a user’s smart card. For more information, see [Use derived credentials in Microsoft Intune](../protect/derived-credentials.md).

  >[!NOTE]
  > Azure çok faktörlü kimlik doğrulaması desteklenmez.
  
- **SSL**: **Etkinleştir** olarak belirlenirse e-posta gönderirken, alırken ve Exchange sunucusuyla iletişim kurulurken Güvenli Yuva Katmanı (SSL) iletişimi kullanılır.
- **OAuth**: **Etkinleştir** olarak belirlenirse e-posta gönderirken, alırken ve Exchange ile iletişim kurulurken Open Authorization (OAuth) iletişimi kullanılır. OAuth sunucunuz sertifika kimlik doğrulaması kullanıyorsa, **Kimlik doğrulama yöntemi** olarak **Sertifika**’yı belirleyin ve sertifikayı profile ekleyin. Diğer durumlarda **Kimlik doğrulama yöntemi** olarak **Kullanıcı adı ve parola**’yı belirleyin. OAuth kullanılırken şunları yaptığınızdan emin olun:

  - Bu profili kullanıcılarınıza hedeflemeden önce e-posta çözümünüzün OAuth standardını desteklediğini onaylayın. Office 365 Exchange Online, OAuth standardını destekler. Şirket içi Exchange ve diğer iş ortağı veya üçüncü taraf çözümler ise OAuth’u desteklemeyebilir. Şirket içi Exchange, Modern Kimlik Doğrulaması için yapılandırılabilir ([Şirket İçi Exchange için Karma Modern Kimlik Doğrulaması Duyurusu](https://blogs.technet.microsoft.com/exchange/2017/12/06/announcing-hybrid-modern-authentication-for-exchange-on-premises/) blog gönderisine bakın).

    E-posta profili OAuth kullanıyorsa ancak e-posta hizmeti bunu desteklemiyorsa, **Parolayı yeniden gir** seçeneği bozuk görünür. Örneğin kullanıcı Apple’ın cihaz ayarlarında **Parolayı yeniden gir**’i seçerse hiçbir şey olmaz.

  - OAuth etkin olduğunda son kullanıcılar çok faktörlü kimlik doğrulamasını (MFA) destekleyen, farklı bir “Modern Kimlik Doğrulaması” e-posta oturum açma deneyimine sahip olurlar. 

  - Bazı kuruluşlar, son kullanıcının [self servis uygulama erişimi](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-self-service-access) sağlama becerisini devre dışı bırakır. Bu senaryoda bir Yönetici “iOS Hesapları” kurumsal uygulamasını oluşturup kullanıcıya Azure AD’de uygulama erişimi verene kadar Modern Kimlik Doğrulaması oturum açma denemesi başarısız olabilir.

    Varsayılan eylem, [Uygulama Erişim Paneli](https://docs.microsoft.com/azure/active-directory/user-help/active-directory-saas-access-panel-introduction) **Uygulama Ekle** özelliğini **iş onayı olmadan** kullanarak uygulama eklemektir. Daha fazla bilgi için bkz. [uygulamalara kullanıcı atama](https://docs.microsoft.com/azure/active-directory/manage-apps/ways-users-get-assigned-to-applications).

  > [!NOTE]
  > OAuth’u etkinleştirdiğinizde şunlar olur:  
  > 1. Hedeflenmiş cihazlara yeni bir profil verilir.
  > 2. Son kullanıcılardan kimlik bilgilerini yeniden girmeleri istenir.

## <a name="exchange-activesync-profile-configuration"></a>Exchange ActiveSync profile configuration

> [!IMPORTANT]
> Configuring these settings deploys a new profile to the device, even when an existing email profile is updated to include these settings. Users are prompted to enter their Exchange ActiveSync account password. These settings take affect when the password is entered.

- **Exchange data to sync**: When using Exchange ActiveSync, choose the Exchange services that are synced on the device: Calendar, Contacts, Reminders, Notes, and Email. Seçenekleriniz şunlardır:
  - **All data** (default): Sync is enabled for all services.
  - **Email only**: Sync is enabled for Email only. Sync is disabled for the other services.
  - **Calendar only**: Sync is enabled for Calendar only. Sync is disabled for the other services.
  - **Calendar and Contacts only**: Sync is enabled for Calendar and Contacts only. Sync is disabled for the other services.
  - **Contacts only**: Sync is enabled for Contacts only. Sync is disabled for the other services.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 13.0 and newer
  - iPadOS 13.0 and newer

- **Allow users to change sync settings**: Choose if users can change the Exchange ActiveSync settings for the Exchange services on the device: Calendar, Contacts, Reminders, Notes, and Email. Seçenekleriniz şunlardır:

  - **Yes** (default): Users can change the sync behavior of all services. Choosing **Yes** allows changes to *all* services.
  - **No**: Users can't change the sync settings of all the services. Choosing **No** blocks changes to *all* services.

  > [!TIP]
  > If you configured the **Exchange data to sync** setting to sync only some services, we recommend selecting **No** for this setting. Choosing **No** prevents users from changing the Exchange service that's synced.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 13.0 and newer
  - iPadOS 13.0 and newer

## <a name="exchange-activesync-email-settings"></a>Exchange ActiveSync email settings

- **S/MIME**: S/MIME uses email certificates that provide extra security to your email communications by signing, encrypting, and decrypting. When you use S/MIME with an email message, you confirm the authenticity of the sender, and the integrity and confidentiality of the message.

  Seçenekleriniz şunlardır:

  - **Disable S/MIME** (default): Doesn't use an S/MIME email certificate to sign, encrypt, or decrypt emails.
  - **Enable S/MIME**: Allows users to sign and/or encrypt email in the iOS native mail application. Şunları da girin:

    - **S/MIME signing enabled**: **Disable** (default) doesn't allow users to digitally sign the message. **Enable** allows users to digitally sign outgoing email for the account you entered. Signing helps users who receive messages be certain that the message came from the specific sender, and not from someone pretending to be the sender.
      - **Allow user to change setting**: **Enable** allows users to change the signing options. **Disable** (default) prevents users from changing the signing, and forces users to use the signing you configured.
      - **Signing certificate type**: Your options:
        - **Not configured**: Intune doesn't update or change this setting.
        - **None**: As an administrator, you don't force a specific certificate. Select this option so users can choose their own certificate.
        - **Derived credential**: Use a certificate that’s derived from a user’s smart card. For more information, see [Use derived credentials in Microsoft Intune](../protect/derived-credentials.md).
        - **Certificates**: Select an existing PKCS or SCEP certificate profile that's used for signing email messages.
      - **Allow user to change setting**: **Enable** allows users to change the signing certificate. **Disable** (default) prevents users from changing the signing certificate, and forces users to use the certificate you configured.

        Bu özellik şu platformlarda geçerlidir:  
        - iOS 12 and newer
        - iPadOS 12 and newer

    - **Encrypt by default**: **Enable** encrypts all messages as the default behavior. **Disable** (default) doesn't encrypt all messages as the default behavior.
      - **Allow user to change setting**: **Enable** allows users to change the default encryption behavior. **Disable** prevents users from changing the encryption default behavior, and forces users to use the encryption you configured.

        Bu özellik şu platformlarda geçerlidir:  
        - iOS 12 and newer
        - iPadOS 12 and newer

    - **Force per-message encryption**: Per-message encryption allows users to choose which emails are encrypted before being sent.

      **Enable** shows the per-message encryption option when creating a new email. Users can then choose to opt-in or opt-out of per-message encryption. If the **Encrypt by default** setting is also enabled, enabling per-message encryption allows users to opt out of encryption per message.

      **Disable** (default) prevents the per-message encryption option from showing. If the **Encrypt by default** setting is also disabled, enabling per-message encryption allows users to opt in to encryption per message.

      - **Encryption certificate type**: Your options:
        - **Not configured**: Intune doesn't update or change this setting.
        - **None**: As an administrator, you don't force a specific certificate. Select this option so users can choose their own certificate.
        - **Derived credential**: Use a certificate that’s derived from a user’s smart card. For more information, see [Use derived credentials in Microsoft Intune](../protect/derived-credentials.md).
        - **Certificates**: Select an existing PKCS or SCEP certificate profile that's used for signing email messages.
      - **Allow user to change setting**: **Enable** allow users to change the encryption certificate. **Disable** (default) prevents users from changing the encryption certificate, and forces users to use the certificate you configured.

        Bu özellik şu platformlarda geçerlidir:  
        - iOS 12 and newer
        - iPadOS 12 and newer

- **Eşitlenecek e-posta miktarı**: Eşitlemek istediğiniz e-posta için gün sayısını seçin. Veya **Sınırsız**’ı seçerek kullanılabilir tüm e-postaları eşitleyin.
- **Allow messages to be moved to other email accounts**: **Enable** (default) allows users to move email messages between different accounts the users configured on their devices.
- **Allow email to be sent from third-party applications**: **Enable** (default) allows users to select this profile as the default account for sending email. Üçüncü taraf uygulamaların, örneğin e-postaya dosya eklemek için yerel e-posta uygulamasında e-posta açmasına izin verilir.
- **Synchronize recently used email addresses**: **Enable** (default) allows users to synchronize the list of email addresses that have been recently used on the device with the server.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Ardından [profili atayın](../device-profile-assign.md) ve [durumunu izleyin](../device-profile-monitor.md).

Configure email settings on [Android](../email-settings-android.md), [Android Enterprise](../email-settings-android-enterprise.md), [Windows 10](email-settings-windows-10.md), and [Windows Phone 8.1](email-settings-windows-phone-8-1.md) devices.
