---
title: Microsoft Intune'da iOS ayarlarını kullanma - Azure | Microsoft Docs
titleSuffix: ''
description: Add, configure, or create settings on iOS devices to restrict features, including setting password requirements, control the locked screen, use built-in apps, add restricted or approved apps, handle bluetooth devices, connect to the cloud for backup and storage, enable kiosk mode, add domains, and control how users interact with the Safari web browser in Microsoft Intune.
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
ms.openlocfilehash: 751ddfae96ebcd190d4d9ce2ca93bfccba972df5
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74390850"
---
# <a name="ios-and-ipados-device-settings-to-allow-or-restrict-features-using-intune"></a>iOS and iPadOS device settings to allow or restrict features using Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

This article lists and describes the different settings you can control on iOS and iPadOS devices. Mobil cihaz yönetimi (MDM) yönteminizin bir parçası olarak bu ayarları kullanabilir ve bu sayede özellikleri etkinleştirip devre dışı bırakabilir, parola kuralları uygulayabilir, belirli uygulamalara izin verebilir veya bunları kısıtlayabilir ve çok daha fazlasını yapabilirsiniz.

Bu ayarlar, Intune'da bir cihaz yapılandırma profiline eklenir ve daha sonra iOS cihazlarınıza atanır veya dağıtılır.

> [!TIP]
> These settings use Apple's MDM settings. For more information on these settings, see [Apple's mobile device management settings](https://support.apple.com/guide/mdm/welcome/web) (opens Apple's web site).

## <a name="before-you-begin"></a>Başlamadan önce

[Cihaz kısıtlamaları yapılandırma profili oluşturma](../device-restrictions-configure.md).

> [!NOTE]
> These settings apply to different enrollment types, with some settings applying to all enrollment options. For more information on the different enrollment types, see [iOS enrollment](../ios-enroll.md).

## <a name="general"></a>Genel

### <a name="settings-apply-to-all-enrollment-types"></a>Settings apply to: All enrollment types

- **Share usage data**: Choose **Block** to prevent the device from sending diagnostic and usage data to Apple. **Yapılandırılmadı** (varsayılan) ayarı bu verilerin gönderilmesine izin verir.

- **Screen capture**: Choose **Block** to prevent screenshots or screen captures on the device. In iOS 9.0 and newer, it also blocks screen recordings. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının ekran içeriğini bir resim veya video olarak yakalamasına olanak tanır.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Settings apply to: Device enrollment, Automated device enrollment (supervised)

- **Untrusted TLS certificates**: Choose **Block** to prevent untrusted Transport Layer Security (TLS) certificates on the device. **Yapılandırılmadı** (varsayılan) ayarı TLS sertifikalarına izin verir.
- **Allow over-the-air PKI updates**: **Allow** lets your users  receive software updates without connecting their devices to a computer.
- **Limit ad tracking**: Choose **Limit** to disable the device advertising identifier. **Yapılandırılmadı** (varsayılan) bu tanımlayıcının etkin kalmasını sağlar.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Settings apply to: Automated device enrollment (supervised)

- **Diagnostics submission settings modification**: **Block** prevents the user from changing the diagnostic submission and app analytics settings in **Diagnostics and Usage** (device Settings). **Yapılandırılmadı** (varsayılan) ayarı kullanıcının bu cihaz ayarlarını değiştirmesine izin verir.

  To use this setting, set the **Share usage data** setting to **Block**.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 9.3.2 and newer

- **Remote screen observation by Classroom app**: Choose **Block** to prevent the Classroom app from remotely viewing the screen on the device. **Yapılandırılmadı** (varsayılan) ayarı Apple Classroom uygulamasının ekranı görüntülemesine izin verir.

  To use this setting, set the **Screen capture** setting to **Block**.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 9.3 and newer

- **Unprompted screen observation by Classroom app**: If set to **Allow**, teachers can silently observe the screen of students iOS devices using the Classroom app without the students' knowledge. Classroom uygulaması kullanılarak sınıfa kaydedilmiş olan öğrenci cihazları, söz konusu dersin öğretmenine otomatik olarak izin verir. **Yapılandırılmadı** (varsayılan) ayarı bu özelliği engeller.

  To use this setting, set the **Screen capture** setting to **Block**.

- **Enterprise app trust**: Choose **Block** to remove the **Trust Enterprise Developer** button in Settings > General > Profiles & Device Management on the device. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının uygulama mağazasından indirilmemiş uygulamalara güvenmeyi seçmesine olanak tanır.
- **Account modification**: When set to **Block**, the user can't update the device-specific settings from the iOS settings app. Örneğin kullanıcı yeni cihaz hesapları oluşturamaz ya da kullanıcı adını veya parolasını değiştiremez. **Yapılandırılmadı** (varsayılan) ayarı kullanıcıların bu ayarları değiştirmesine izin verir.

  Bu özellik Posta, Kişiler, Takvim ve Twitter gibi iOS ayarları uygulamasından erişilebilen ayarlar için de geçerlidir. Bu özellik hesap ayarları iOS ayarları uygulamasından yapılandırılamayan uygulamalar (Microsoft Outlook uygulaması gibi) için geçerli değildir.

- **Screen time**: Choose **Block** to prevent users from setting their own restrictions in Screen Time (device settings). **Yapılandırılmadı** kullanıcının cihazda cihaz kısıtlamalarını (ebeveyn denetimleri veya içerik ve gizlilik kısıtlamaları gibi) yapılandırmasına izin verir.

  Bu ayar **Cihaz ayarlarında kısıtlamaları etkinleştirme** ayarının yeniden adlandırılmış halidir. Bu değişikliğin etkisi:  
  
  - iOS 11.4.1 and earlier: **Block** prevents end users from setting their own restrictions in the device settings. The behavior is the same; and there are no changes for end users.
  - iOS 12.0 and newer: **Block** prevents end users from setting their own **Screen Time** in the device settings (Settings > General > Screen Time), including content and privacy restrictions. iOS 12.0'dan yükseltilen cihazlar artık cihaz ayarlarında kısıtlamalar sekmesini (Ayarlar > Genel > Cihaz Yönetimi > Yönetim Profili > Kısıtlamalar) görmez. Bu ayarlar **Ekran Saati** altındadır.
  
- **Use of the erase all content and settings option on the device**: Choose **Block** so users can't use the erase all content and settings option on the device. **Yapılandırılmadı** (varsayılan) ayarı kullanıcılara bu ayarlar için erişim verir.
- **Device name modification**: Choose **Block** so the device name can't be changed. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının cihaz adını değiştirmesine izin verir.
- **Notification settings modification**: Choose **Block** so the notification settings can't be changed. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının cihaz bildirim ayarlarını değiştirmesine izin verir.
- **Wallpaper modification**: **Block** prevents the wallpaper from being changed. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının cihazda duvar kağıdını değiştirmesine izin verir.
- **Enterprise app trust settings modification**: **Block** prevents the user from changing the enterprise app trust settings on supervised devices. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının uygulama mağazasından indirilmemiş uygulamalara güvenmesine izin verir.
- **Configuration profile changes**: **Block** prevents configuration profile changes on the device. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının yapılandırma profillerini yüklemesine izin verir.
- **Activation Lock**: Choose **Allow** to enable Activation Lock on supervised iOS devices. Etkinleştirme Kilidi, kaybolan veya çalınan bir cihazın yeniden etkinleştirilmesini zorlaştırır.
- **Block app removal**: Choose **Block** to prevent users from removing apps. **Yapılandırılmadı** (varsayılan) ayarı kullanıcıların cihazdan uygulama kaldırmasına izin verir.
- **Blocks USB Restricted mode**: Choose **Block** to disable USB Restricted mode on supervised devices. USB Restricted mode prevents USB accessories from exchanging data with a device that's locked for over an hour. **Yapılandırılmadı** (varsayılan) ayarı USB Kısıtlı moduna izin verir.
- **Force automatic date and time**: **Require** forces supervised devices to set the Date & Time automatically. Cihazın hücresel bağlantıları olduğunda veya konum hizmetleriyle arasında Wi-Fi etkinleştirildiğinde saat dilimi güncelleştirilir.
- **Require students to request permission to leave Classroom course**: **Require** forces students enrolled in an unmanaged course using the Classroom app to request permission from the teacher to leave the course. **Yapılandırılmadı** (varsayılan) ayarı öğrencinin izin istemesini zorunlu tutmaz.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11.3 and newer

- **Allow Classroom to lock to an app and lock the device without prompting**: **Enable** allows teacher to lock apps or lock the device using the Classroom app without prompting the student. Uygulamaların kilitlenmesi cihazın yalnızca öğretmenin belirttiği uygulamalara erişebileceği anlamına gelir. **Yapılandırılmadı** (varsayılan) ayarı öğretmenlerin öğrenciye sormadan Classroom uygulamasını kullanarak uygulamaları veya cihazları kilitlemesini önler.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11.0 and newer

- **Automatically join Classroom classes without prompting**: **Enable** automatically allows students to join a class that is in the Classroom app without prompting the teacher. **Yapılandırılmadı** (varsayılan) ayarı öğrencilerin Classroom uygulamasındaki derse katılma isteğini öğretmene sorar.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11.0 and newer

- **Block VPN creation**: **Block** prevents users from creating VPN configuration settings. **Yapılandırılmadı** (varsayılan) ayarı kullanıcıların cihazda VPN'ler oluşturmasına olanak tanır.
- **Modifying eSIM settings**: **Block** prevents users from removing or adding a cellular plan to the eSIM on the device. **Yapılandırılmadı** (varsayılan) ayarı kullanıcıların bu ayarları değiştirmesine izin verir.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 12.1 and newer

- **Defer software updates**: When set to **Not configured** (default), software updates are shown on the device as Apple releases them. Örneğin Apple tarafından bir iOS güncelleştirmesinin yayımlanması durumunda ilgili güncelleştirme normal bir şekilde yayın tarihinde cihazda görünür.

  **Etkinleştir** ayarını kullanarak güncelleştirmelerin cihazlarda gösterilmesini 0-90 gün boyunca geciktirebilirsiniz. Bu ayar, güncelleştirmelerin yüklenme tarihini veya durumunu denetlemez. 

  - **Delay visibility of software updates**: Enter a value from 0-90 days. Gecikme süresi sona erdiğinde kullanıcılara gecikmenin tetiklendiği tarihte kullanılabilir durumda olan en eski işletim sistemi sürümüne güncelleştirme bildirimi gönderilir.

    Örneğin **1 Ocak** tarihinde iOS.12a'nın yayımlanması ve **Görünürlük geciktirme** ayarının **5 gün** olması durumunda iOS 12.a, son kullanıcı cihazlarında kullanılabilir güncelleştirme olarak gösterilmez. Yayımlandıktan sonraki **altıncı günde** bu güncelleştirme kullanıma sunulur ve kullanıcılar tarafından yüklenebilir.

    Bu ayarın geçerli olduğu sürümler:  
    - iOS 11.3 and newer

## <a name="password"></a>Parola

### <a name="settings-apply-to-all-enrollment-types"></a>Settings apply to: All enrollment types

- **Password**: **Require** the end user to enter a password to access the device. **Not configured** (default) allows users to access the device without entering a password.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Settings apply to: Device enrollment, Automated device enrollment (supervised)

> [!IMPORTANT]
> On user-enrolled devices, if you configure any password setting, then the **Simple passwords** settings is automatically set to **Block**, and a 6 digit PIN is enforced.
>
> For example, you configure the **Password expiration** setting, and push this policy to user-enrolled devices. On the devices, the following happens:
>
> - The **Password expiration** setting is ignored.
> - Simple passwords, such as `1111` or `1234`, aren't allowed.
> - A 6 digit pin is enforced.

- **Simple passwords**: Choose **Block** to require more complex passwords. **Yapılandırılmadı** ayarı `0000` ve `1234` gibi basit parolalara izin verir.

- **Required password type**: Choose the type of password your organization require. Seçenekleriniz şunlardır:
  - **Cihaz varsayılanı**
  - **Sayısal**
  - **Alfasayısal**
- **Number of non-alphanumeric characters in password**: Enter the number of symbol characters, such as `#` or `@`, that must be included in the password.

- **Minimum password length**: Enter the minimum length a user must enter, between 4 and 14 characters. On user enrolled devices, enter a length between 4 and 6 characters.
  
  > [!NOTE]
  > For devices that are user enrolled, users can set a PIN greater than 6 digits. But, no more than 6 digits are enforced on the device. For example, an administrator sets the minimum length to `8`. On user-enrolled devices, users are only required to set a 6 digit PIN. Intune doesn't force a PIN greater than 6 digits on user-enrolled devices.

- **Number of sign-in failures before wiping device**: Enter the number of failed sign-ins to allow before the device is wiped (between 4-11).
  
  iOS has built-in security that can impact this setting. For example, iOS may delay triggering the policy depending on the number of sign in failures. It may also consider repeatedly entering the same passcode as one attempt. Apple's [iOS security guide](https://www.apple.com/business/site/docs/iOS_Security_Guide.pdf) (opens Apple's web site) is a good resource, and provides more specific details on passcodes.
  
- **Maximum minutes after screen lock before password is required**<sup>1</sup>: Enter how long the device stays idle before the user must reenter their password. Girdiğiniz süre cihazda şu anda ayarlanmış olan süreden uzunsa, cihaz girdiğiniz süreyi yoksayar. iOS 8.0 ve daha yeni cihazlarda desteklenir.

- **Maximum minutes of inactivity until screen locks**<sup>1</sup>: Enter the maximum number of minutes of inactivity allowed on the device until the screen locks.

  **iOS options**:  

  - **Not configured** (Default): Intune doesn't touch this setting.
  - **Immediately**: Screen locks after 30 seconds of inactivity.
  - **1**: Screen locks after 1 minute of inactivity.
  - **2**: Screen locks after 2 minutes of inactivity.
  - **3**: Screen locks after 3 minutes of inactivity.
  - **4**: Screen locks after 4 minutes of inactivity.
  - **5**: Screen locks after 5 minutes of inactivity.
    
  **iPadOS options**:  

  - **Not configured** (Default): Intune doesn't touch this setting.
  - **Immediately**: Screen locks after 2 minutes of inactivity.
  - **2**: Screen locks after 2 minutes of inactivity.
  - **5**: Screen locks after 5 minutes of inactivity.
  - **10**: Screen locks after 10 minutes of inactivity.
  - **15**: Screen locks after 15 minutes of inactivity.

  If a value doesn't apply to iOS or iPadOS, then Apple uses the closest *lowest* value. For example, if you enter `4` minutes, then iPadOS devices use `2` minutes. If you enter `10` minutes, then iOS devices use `5` minutes. This is an Apple limitation.
  
  > [!NOTE]
  > The Intune UI for this setting doesn't separate the iOS and iPadOS supported values. The UI might be updated in a future release.

- **Password expiration (days)** : Enter the number of days before the device password must be changed.
- **Prevent reuse of previous passwords**: Enter the number of new passwords that must be used until an old one can be reused.
- **Touch ID and Face ID unlock**: Choose **Block** to prevent using a fingerprint or face to unlock the device. **Not configured** allows the user to unlock the device using these methods.

  Blocking this setting also prevents using FaceID authentication to unlock the device.

  Face ID applies to:  
  - iOS 11.0 and newer

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Settings apply to: Automated device enrollment (supervised)

- **Passcode modification**: Choose **Block** to stop the passcode from being changed, added, or removed. Bu özellik engellendikten sonra denetimli cihazlarda geçiş kodu kısıtlamalarında yapılan değişiklikler yoksayılır. **Yapılandırılmadı** (varsayılan) ayarı, geçiş kodu ekleme, değiştirme veya kaldırma işlemlerine izin verir.

  - **Touch ID and Face ID modification**: **Block** stops the user from changing, adding, or removing TouchID fingerprints and Face ID. **Not configured** (default) allows the user to update the TouchID fingerprints and Face ID on the device.

    Blocking this setting also stops the user from changing, adding, or removing FaceID authentication.

    Face ID applies to:  
    - iOS 11.0 and newer

- **Block password AutoFill**: Choose **Block** to prevent using the AutoFill Passwords feature on iOS. **Engelle** ayarını seçmek şu sonuçlara da neden olur:

  - Safari'de veya diğer uygulamalarda kullanıcılara parolaları kaydetmek isteyip istemedikleri sorulmaz.
  - Otomatik Güçlü Parolalar devre dışı bırakılır ve kullanıcılara güçlü parola önerisi sunulmaz.

  **Yapılandırılmadı** (varsayılan) ayarı bu özelliklere izin verir.

- **Block password proximity requests**: Choose **Block** so a user’s device doesn't request passwords from nearby devices. **Yapılandırılmadı** (varsayılan) ayarı bu parola isteklerine izin verir.
- **Block password sharing**: **Block** prevents sharing passwords between devices using AirDrop. **Yapılandırılmadı** (varsayılan) ayarı, parolaların paylaşılmasına izin verir.
- **Require Touch ID or Face ID authentication for password or credit card information AutoFill**: When set to **Require**, users must authenticate using TouchID or FaceID before passwords or credit card information can be auto filled in Safari and other apps. **Yapılandırılmadı** (varsayılan) ayarı kullanıcıların cihaz ayarlarında bu özelliği denetlemesine izin verir.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11.0 and newer
  
<sup>1</sup>**Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı** ve **Ekran kilitlendikten sonra parola istenene kadar geçmesi gereken, işlem yapılmayan dakika sayısı**, ayarlarını yapılandırdığınızda, bunlar sırayla uygulanır. Örneğin, her iki ayarın da değerini **5** dakikaya ayarlarsanız, ekran beş dakika sonra otomatik olarak kapanır ve cihazın kilitlenmesi için beş dakika daha geçmesi gerekir. Ancak, kullanıcı ekranı el ile kapatırsa ikinci ayar hemen uygulanır. Aynı örnekte, kullanıcı ekranı kapattıktan sonraki beş dakikanın sonunda cihaz kilitlenir.

## <a name="locked-screen-experience"></a>Kilit Ekranı Deneyimi

### <a name="settings-apply-to-all-enrollment-types"></a>Settings apply to: All enrollment types

- **Control Center access while device locked**: Choose **Block** to prevent access to the Control Center app while device is locked. **Not configured** (default) allows users access to the Control Center app when the device is locked.
- **Notifications while device locked**: **Block** prevents access to notifications when the device is locked. **Not configured** (default) allows the user to access the notifications without unlocking the device.
- **Today view while device locked**: **Block** prevents access to the Today view when the device is locked. **Not configured** (default) allows the user to see the Today view when the device is locked.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Settings apply to: Device enrollment, Automated device enrollment (supervised)

- **Wallet notifications while device locked**: **Block** prevents access to the Wallet app when the device is locked. **Not configured** (default) allows the user to access the Wallet app while the device is locked.

## <a name="app-store-doc-viewing-gaming"></a>Uygulama Mağazası, Belge Görüntüleme, Oyun

### <a name="settings-apply-to-all-enrollment-types"></a>Settings apply to: All enrollment types

- **Viewing corporate documents in unmanaged apps**: **Block** prevents viewing corporate documents in unmanaged apps. **Not configured** (default) allows corporate documents to be viewed in any app. Örneğin kullanıcıların OneDrive uygulamasından Dropbox’a dosya kaydetmesini engellemek istiyorsunuz. Bu ayarı **Engelle** olarak yapılandırın. Cihaz ilkeyi aldıktan sonra (örneğin, yeniden başlatıldıktan sonra) artık kaydetmeye izin vermez.

  - **Allow unmanaged apps to read from managed contacts accounts**: When set to **Allow**, unmanaged apps, such as the built-in iOS Contacts app, can read and access contact information from managed apps, including the Outlook mobile app. **Not configured** (default) prevents reading, including removing duplicates, from the built-in Contacts app on the device.  
  
    This setting allows or prevents reading contact information. It doesn't control syncing contacts between the apps.
  
    Bu ayarı kullanmak için **Yönetilmeyen uygulamalarda kurumsal belgeleri görüntüleme** ayarını **Engelle** olarak belirtin.

  For more information about these two settings, and their impact on Outlook for iOS contact export synchronization, see [Support Tip: Use Intune custom profile settings with the iOS Native Contacts App](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Use-Intune-custom-profile-settings-with-the-iOS/ba-p/298453).

- **Treat AirDrop as an unmanaged destination**: **Require** forces AirDrop to be considered an unmanaged drop target. Yönetilen uygulamaların Airdrop'u kullanarak veri göndermesini durdurur. 
- **Viewing non-corporate documents in corporate apps**: **Block** prevents viewing non-corporate documents in corporate apps. **Not configured** (default) allows any document to be viewed in corporate managed apps.

  Setting to **Block** also prevents contact export synchronization in Outlook for iOS. For more information, see [Support Tip: Enabling Outlook iOS Contact Sync with iOS12 MDM Controls](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Enabling-Outlook-iOS-Contact-Sync-with-iOS12-MDM/ba-p/298453).

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Settings apply to: Device enrollment, Automated device enrollment (supervised)

- **Require iTunes Store password for all purchases**: **Require** the user to enter the Apple ID password for each in-app or ITunes purchase. **Not configured** (default) allows purchases without prompting for a password every time.
- **In-app purchases**: Choose **Block** to prevent in-app purchases from the store. **Not configured** (default) allows store purchases within a running app.
- **Download content from iBook store flagged as 'Erotica'** : Choose **Block** to prevent stops users from downloading media from the iBook store that's tagged as erotica. **Not configured** (default) allows the user to download books with the "Erotica" category.
- **Allow managed apps to write contacts to unmanaged contacts accounts**: When set to **Allow**, managed apps, such as the Outlook mobile app, can save or sync contact information, including business and corporate contacts, to the built-in iOS Contacts app. When set to **Not configured** (default), managed apps can't save or sync contact information to the built-in iOS Contacts app on the device.
  
  Bu ayarı kullanmak için **Yönetilmeyen uygulamalarda kurumsal belgeleri görüntüleme** ayarını **Engelle** olarak belirtin.

- **Ratings region**: Choose the ratings region you want to use for allowed downloads. And then choose the allowed ratings for **Movies**, **TV Shows**, and **Apps**.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Settings apply to: Automated device enrollment (supervised)

- **App store**: **Block** prevents access to the app store on supervised devices. **Not configured** (default) allows access.

  Starting with iOS 13.0, this setting requires supervised devices.

  - **Installing apps from App Store**: Choose **Block** to block the app store from the device home screen. Son kullanıcılar, uygulamaları yüklemek için iTunes’u veya Apple Configurator aracını kullanmaya devam edebilir. **Not configured** (default) allows the app store on the home screen.
  - **Automatic app downloads**: Choose **Block** to prevent automatic downloading of apps bought on other devices. Mevcut uygulamalarında yapılan güncelleştirmeler bundan etkilenmez. **Not configured** (default) allows apps bought on other iOS devices to download on the device.

- **Explicit iTunes music, podcast, or news content**: Choose **Block** to prevent explicit iTunes music, podcast, or news content. **Not configured** (default) allows the device to access content rated as adult from the store. iOS 13 and newer may require supervised only devices. 

  Starting with iOS 13.0, this setting requires supervised devices.

- **Adding Game Center friends**: **Block** prevents users from adding Game Center friends. **Not configured** (default) allows the user to add friends in Game Center.

  Starting with iOS 13.0, this setting requires supervised devices.

- **Game Center**: **Block** the use of the Game Center app. **Not configured** (default) allows using the Game Center app on the device.
- **Multiplayer gaming**: Choose **Block** to prevent multiplayer gaming. **Not configured** (default) allows the user to play multiplayer games on the device.

  Starting with iOS 13.0, this setting requires supervised devices.

- **Access to network drive in Files app**: Using the Server Message Block (SMB) protocol, devices can access files or other resources on a network server. **Disable** prevents accessing files on a network SMB drive. **Not configured** (default) allows access.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS and iPadOS 13.0 and newer

## <a name="built-in-apps"></a>Yerleşik Uygulamalar

### <a name="settings-apply-to-all-enrollment-types"></a>Settings apply to: All enrollment types

- **Siri**: **Block** prevents access to Siri. **Not configured** (default) allows using the Siri voice assistant on the device.
  - **Siri while device is locked**: Choose **Block** to prevent access to Siri when the device is locked. **Not configured** (default) allows using the Siri voice assistant on the device when it's locked.

- **Safari fraud warnings**: **Require** fraud warnings to be shown in the web browser on the device. **Yapılandırılmadı** (varsayılan) ayarı, bu özelliği devre dışı bırakır.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Settings apply to: Device enrollment, Automated device enrollment (supervised)

- **Spotlight search to return results from internet**: **Block** stops Spotlight from returning any results from an Internet search. **Yapılandırılmadı** (varsayılan) ayarı, Spotlight'ın internete bağlanarak arama sonuçlarını getirmesine izin verir.

- **Safari cookies**: Choose how cookies are handled on the device. Seçenekleriniz şunlardır:
  - Allow
  - Tüm tanımlama bilgilerini engelle
  - Ziyaret edilen web sitelerinin tanımlama bilgilerine izin ver
  - Geçerli web sitesinin tanımlama bilgilerine izin ver

- **Safari JavaScript**: **Block** prevents Java scripts in the browser from running on the device. **Not configured** (default) allows Java scripts.

- **Safari Pop-ups**: **Block** to disable the pop-up blocker in the web browser. **Not configured** (default) allows the pop-up blocker.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Settings apply to: Automated device enrollment (supervised)

- **Camera**: Choose **Block** to prevent access to the camera on the device. **Yapılandırılmadı** (varsayılan) ayarı, cihazın kamerasına erişim sağlar.

  Starting with iOS 13.0, this setting requires supervised devices.

  - **FaceTime**: **Block** to prevent access to the FaceTime app. **Not configured** (default) allows access to the FaceTime app on the device.

    Starting with iOS 13.0, this setting requires supervised devices.

- **Siri profanity filter**: **Require** prevents Siri from dictating, or speaking profane language.

  To use this setting, set the **Siri** setting to **Block**.

- **Siri to query user-generated content from the internet**: **Block** prevents Siri from accessing websites to answer questions. **Not configured** (default) allows Siri to access user-generated content from the internet.

  To use this setting, set the **Siri** setting to **Block**.

- **Apple News**: Choose **Block** to prevent access to the Apple News app on the device. **Not configured** (default) allows using the Apple News app.
- **iBooks store**: **Block** prevents access to the iBooks store. **Not configured** (default) allows users to browse and buy books from the iBooks store.
- **Messages app on the device**: **Block** prevents users from using the Messages app for iMessage. If the device supports text messaging, the user can still send and receive text messages using SMS. **Not configured** (default) allows using the Messages app to send and read messages over the internet.
- **Podcasts**: **Block** prevents users using the Podcasts app. **Not configured** (default) allows using the Podcasts app.
- **Music service**: **Block** reverts the Music app to classic mode and disables the Music service. **Yapılandırılmadı** (varsayılan) ayarı, Apple Music uygulamasının kullanılmasına izin verir.
- **iTunes Radio service**: **Block** prevents users from using the iTunes Radio app. **Not configured** (default) allows using the iTunes Radio app.
- **iTunes store**: **Not configured** (default) allows iTunes on the devices. **Block** prevents users from using iTunes on the device. 

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 4.0 and newer

- **Find my iPhone**: **Not configured** (default) allows using this Find My app feature to get the approximate location of the device. **Block** prevents this feature in the Find My app. 

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 13.0 and iPadOS 13.0 and newer

- **Find my Friends**: **Not configured** (default) allows using this Find My app feature to find family and friends from an Apple device or iCloud.com. **Block** prevents this feature in the Find My app.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 13.0 and iPadOS 13.0 and newer

- **Changes to the Find My Friends app settings**: **Block** prevents changes to the Find My Friends app settings. **Not configured** (default) allows the user to change settings for the Find My Friends app.

- **Spotlight search to return results from internet**: **Block** stops Spotlight from returning any results from an Internet search. **Yapılandırılmadı** (varsayılan) ayarı, Spotlight'ın internete bağlanarak arama sonuçlarını getirmesine izin verir.

- **Block removal of system apps from device**: Choosing **Block** disables the ability to remove system apps from the device. **Not configured** (default) allows users to remove system apps.

- **Safari**: **Block** using the Safari browser on the device. **Not configured** (default) allows users to use the Safari browser.

  Starting with iOS 13.0, this setting requires supervised devices.

- **Safari Autofill**: **Block** disables the autofill feature in Safari on the device. **Yapılandırılmadı** (varsayılan) ayarı, kullanıcıların web tarayıcısındaki otomatik tamamlama ayarlarını değiştirmesine olanak tanır.

  Starting with iOS 13.0, this setting requires supervised devices.

## <a name="restricted-apps"></a>Kısıtlı uygulamalar

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Settings apply to: Device enrollment, Automated device enrollment (supervised)

- **Type of restricted apps list**: Create a list of apps that users aren't allowed to install or use. Seçenekleriniz şunlardır:

  - **Not configured** (default): There are no restrictions from Intune. Users have access to apps you assign, and built-in apps.
  - **Prohibited apps**: Apps not managed by Intune that you don't want installed on the device. Users aren't prevented from installing a prohibited app. But if a user installs an app from this list, it's reported in Intune.
  - **Approved apps**: Apps that users are allowed to install. Kullanıcılar listelenmeyen uygulamaları yüklememelidir. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir. Kullanıcıların onaylı uygulamalar listesinde olmayan bir uygulamayı yüklenmesi engellenmez. But if they do, it's reported in Intune.

Bu listelere uygulama eklemek için şunları yapabilirsiniz:

- İstediğiniz uygulamanın iTunes App mağazası URL'sini **ekleyin**. For example, to add the Microsoft Work Folders app, enter `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` or `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`.

  Uygulamanın URL'sini bulmak için, iTunes App Store'u açın ve uygulamayı arayın. Örneğin `Microsoft Remote Desktop` veya `Microsoft Word` için arama yapın. Uygulamayı seçin ve URL'sini kopyalayın.

  iTunes kullanarak da uygulamayı bulabilir ve ardından **Bağlantıyı Kopyala** görevini kullanıp uygulama URL’sini alabilirsiniz.

- **Import** a CSV file with details about the app, including the URL. `<app url>, <app name>, <app publisher>` biçimini kullanın. Or, **Export** an existing list that includes the restricted apps list in the same format.

> [!IMPORTANT]
> Kısıtlı uygulama ayarlarını kullanan cihaz profilleri kullanıcı gruplarına atanmalıdır.

## <a name="show-or-hide-apps"></a>Uygulamaları gösterme veya gizleme

Applies to devices running iOS 9.3 or newer.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Settings apply to: Automated device enrollment (supervised)

- **Type of apps list**: Create a list of apps to show or hide. You can show or hide built-in apps and line-of-business apps. Apple's web site has a list of [built-in Apple apps](https://support.apple.com/HT208094). Seçenekleriniz şunlardır:

  - **Hidden apps**: Enter a list of apps that are hidden from users. Kullanıcılar bu uygulamaları görüntüleyemez veya açamaz.
  
    Apple prevents hiding some native apps. For example, you can't hide the **Settings** or **Wallet** apps on the device. [Delete built-in Apple apps](https://support.apple.com/HT208094) lists the apps that can be hidden.
  
  - **Visible apps**: Enter a list of apps that users can view and launch. Başka hiçbir uygulama görüntülenemez veya başlatılamaz.

- **App URL**: Enter the store app URL of the app you want to show or hide. Örneğin:

  - To add the Microsoft Work Folders app, enter `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` or `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`. 

  - To add the Microsoft Word app, enter `https://itunes.apple.com/de/app/microsoft-word/id586447913` or `https://apps.apple.com/de/app/microsoft-word/id586447913`.

  Uygulamanın URL'sini bulmak için, iTunes App Store'u açın ve uygulamayı arayın. Örneğin `Microsoft Remote Desktop` veya `Microsoft Word` için arama yapın. Uygulamayı seçin ve URL'sini kopyalayın.

  iTunes kullanarak da uygulamayı bulabilir ve ardından **Bağlantıyı Kopyala** görevini kullanıp uygulama URL’sini alabilirsiniz.
  
  For more information about locating a Bundle ID, see [How to find the bundle ID for an iOS app](https://support.microsoft.com/help/4294074/how-to-find-the-bundle-id-for-an-ios-app).

- **App Bundle ID**: Enter the app [bundle ID](bundle-ids-built-in-ios-apps.md) of the app you want. You can show or hide built-in apps and line-of-business apps. Apple's web site has a list of [built-in Apple apps](https://support.apple.com/HT208094).
- **App name**: Enter the app name of the app you want. You can show or hide built-in apps and line-of-business apps. Apple's web site has a list of [built-in Apple apps](https://support.apple.com/HT208094).
- **Publisher**: Enter the publisher of the app you want.

Uygulamaları eklemek için şunları yapabilirsiniz:

- **Add**: Select to create your list of apps.
- **Import** a CSV file with details about the app, including the URL. `<app url>, <app name>, <app publisher>` biçimini kullanın. Or, **Export** to create a list of the restricted apps you added, in the same format.

## <a name="wireless"></a>Kablosuz

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Settings apply to: Device enrollment, Automated device enrollment (supervised)

Note needed for Data Roaming (Tip or important note to help with customer confusion): This setting will not show up on the targeted device's management profile. That is because this setting is treated as a remote device action, and every time the state of data roaming is changed on the device, it will become blocked again by the Intune service. Even though it is not in the management profile, it is working if it showing as a success from the reporting in the admin console. 
- **Data roaming**: Choose **Block** to prevent data roaming over the cellular network. **Yapılandırılmadı** (varsayılan) ayarı cihaz cep telefonu şebekesindeyken veri dolaşımına izin verir.

  > [!IMPORTANT]
  > This setting is treated as a remote device action. So, this setting isn't shown in the management profile on the device. Every time the data roaming status changes on the device, **Data roaming** is blocked by the Intune service. In Intune, if the reporting status shows a success, then know that it's working, even though the setting isn't shown in the management profile on the device.

- **Global background fetch while roaming**: **Block** prevents using the global background fetch feature when roaming over the cellular network. **Yapılandırılmadı** ayarı cihazın cep telefonu şebekesi üzerinde dolaşımdayken e-posta gibi verileri almasına izin verir.
- **Voice dialing**: Choose **Block** to prevent users from using the voice dialing feature on the device. **Yapılandırılmadı** (varsayılan) ayarı cihazda sesli aramaya izin verir.
- **Voice roaming**: Choose **Block** to prevent voice roaming over the cellular network. **Yapılandırılmadı** (varsayılan) ayarı cihaz cep telefonu şebekesindeyken ses dolaşımına izin verir.
- **Personal Hotspot**: **Block** turns off the personal hotspot on the users' device with every device sync. This setting might not be compatible with some carriers. **Yapılandırılmadı** (varsayılan) ayarı kişisel etkin nokta yapılandırmasını kullanıcı tarafından ayarlanmış varsayılan değerinde bırakır.

  > [!IMPORTANT]
  > This setting is treated as a remote device action. So, this setting isn't shown in the management profile on the device. Every time the personal hotspot status changes on the device, **Personal Hotspot** is blocked by the Intune service. In Intune, if the reporting status shows a success, then know that it's working, even though the setting isn't shown in the management profile on the device.

- **Cellular usage rules (managed apps only)** : Define the data types that managed apps can use when on cellular networks. Seçenekleriniz şunlardır:
  - **Block use of cellular data**: Block using cellular data for **All managed apps** or **Choose specific apps**.
  - **Block use of cellular data when roaming**: Block using cellular data when roaming for **All managed apps** or **Choose specific apps**.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Settings apply to: Automated device enrollment (supervised)

- **Changes to app cellular data usage settings**: Choose **Block** to prevent changes to the app cellular data usage settings. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının hangi uygulamaların hücresel veri kullanabileceğini denetlemesine izin verir.
- **Changes to cellular plan settings**: **Block** prevents users from changing any settings in the cellular plan. **Yapılandırılmadı** (varsayılan) ayarı kullanıcıların değişiklik yapmasına izin verir.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11.0 and newer

- **User modification of Personal Hotspot**: When set to **Block**, the user can't change the personal hotspot setting. **Not configured** (default) allows end users to enable or disable their personal hotspot.

  If you block this setting and block the **Personal Hotspot** setting, the personal hotspot is turned off.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 12.2 and newer

- **Join Wi-Fi networks only using configuration profiles**: **Require** forces the device to use only Wi-Fi networks set up through Intune configuration profiles. **Yapılandırılmadı** (varsayılan) ayarı cihazın diğer Wi-Fi ağlarını kullanmasına izin verir.
- **Wi-Fi always turned on**: When set to **Require**, Wi-Fi stays on in the Settings app. It can't be turned off in Settings or in the Control Center, even when the device is in airplane mode. **Not configured** (default) allows the user to control turning on or turning off Wi-Fi.

  Configuring this setting doesn't prevent users from selecting a Wi-Fi network.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS and iPadOS 13.0 and newer

## <a name="connected-devices"></a>Bağlı Cihazlar

### <a name="settings-apply-to-all-enrollment-types"></a>Settings apply to: All enrollment types

- **Wrist detection for paired Apple watch**: **Require** forces a paired Apple watch to use wrist detection. Gerekli seçilirse, Apple Watch takılmadığında bildirim görüntülemez. 

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Settings apply to: Device enrollment, Automated device enrollment (supervised)

- **Require AirPlay outgoing requests pairing password**: **Require** a pairing password when the user uses AirPlay to stream content to other Apple devices. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının parola girmeden AirPlay kullanarak içerik akışı yapmasına izin verir.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Settings apply to: Automated device enrollment (supervised)

- **AirDrop**: **Block** prevents using AirDrop on the device. **Yapılandırılmadı** (varsayılan) ayarı, yakındaki cihazlarla içerik değişimi için AirDrop özelliğinin kullanılmasına izin verir.
- **Apple Watch pairing**: **Block** prevents pairing with an Apple Watch. **Yapılandırılmadı** (varsayılan) ayarı cihazın Apple Watch ile eşleştirilmesine izin verir.
- **Bluetooth modification**: **Block** stops the end user from changing Bluetooth settings on the device. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının bu ayarları değiştirmesine izin verir.
- **Host pairing to control the devices an iOS device can pair with**: **Not configured** (default) allows host pairing to let the administrator control which devices an iOS device can pair with. **Engelle** ayarı konak eşleştirmeyi önler.
- **Block AirPrint**: Choose **Block** to prevent using the AirPrint feature on the device. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının AirPrint'i kullanmasına izin verir.
  - **Block storage of AirPrint credentials in Keychain**: **Block** prevents using Keychain storage for username and password on the device. **Yapılandırılmadı** (varsayılan) ayarı AirPrint kullanıcı adı ve parolasının Anahtar Zinciri uygulamasında depolanmasına izin verir.
  - **Require a trusted TLS certificate for AirPrint**: **Require** forces the device to use trusted certificates for TLS printing communication.
  - **Block iBeacon discovery of AirPrint printers**: **Block** prevents malicious AirPrint Bluetooth beacons from phishing for network traffic. **Yapılandırılmadı** (varsayılan) ayarı cihazda AirPrint yazıcılarının tanıtılmasına izin verir.
- **Block setting up new nearby devices**: **Block** disables the prompt to set up new devices that are nearby. **Yapılandırılmadı** (varsayılan) ayarı yakındaki diğer Apple cihazlarıyla bağlantı kurulup kurulmayacağının kullanıcıya sorulmasına izin verir.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11.0 and newer

- **Access to files on USB drive**: Devices can connect and open files on a USB drive. **Disable** prevents device access to the USB drive in the Files app when a USB is connected to the device. Disabling this feature also blocks end users from transferring files onto a USB drive connected to an iPad. **Not configured** (default) allows access to a USB drive in the Files app.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS and iPadOS 13.0 and newer

## <a name="keyboard-and-dictionary"></a>Klavye ve Sözlük

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Settings apply to: Automated device enrollment (supervised)

- **Word definition lookup**: **Block** prevents user from highlighting a word, and then looking up its definition on the device. **Yapılandırılmadı** (varsayılan) ayarı, tanım arama özelliğine erişim sağlar.
- **Predictive keyboards**: **Not configured** (default) allows using predictive keyboards to suggest words the user might want. **Engelle** ayarı bu özelliği önler.
- **Auto-correction**: **Not configured** (default) allows the device to automatically correct misspelled words. **Engelle** ayarı otomatik düzeltme kullanılmasını önler.
- **Keyboard spell-check**: **Not configured** (default) allows using spellchecker on the device. **Engelle** ayarı yazım denetleyicisine izin verir.
- **Keyboard shortcuts**: **Not configured** (default) allows using keyboard shortcuts on the device. **Engelle** ayarı kullanıcının klavye kısayollarını kullanmasını durdurur.
- **Dictation**: **Block** stops the user from using voice input to enter text. **Yapılandırılmadı** (varsayılan) ayarı, kullanıcının dikteyle girişi kullanmasına izin verir.
- **QuickPath**: **Not configured** (default) allows users to use QuickPath, which allows a continuous input on the device's keyboard. Users can type by swiping across the keys to create words. **Block** prevents users from using QuickPath. 

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 13.0 and iPadOS 13.0 and newer

## <a name="cloud-and-storage"></a>Bulut ve Depolama

### <a name="settings-apply-to-all-enrollment-types"></a>Settings apply to: All enrollment types

- **Encrypted backup**: **Require** so device backups must be encrypted.
- **Managed apps sync to cloud**: **Not configured** (default) allows your Intune-manages apps to sync data to the user's iCloud account. **Engelle** ayarı iCloud'a bu veri eşitlemesini engeller.
- **Block Enterprise Book Backup**: Choose **Block** to prevent users from backing up enterprise books. **Not configured** (default) allows users to back up these books.
- **Block enterprise book metadata sync (notes and highlights)** : **Block** prevents syncing notes and highlights in enterprise books. **Not configured** (default) allows the syncing.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Settings apply to: Device enrollment, Automated device enrollment (supervised)

- **Photo stream syncing to iCloud**: **Not configured** (default) lets users enable **My Photo Stream** on their device to sync to iCloud, and have photos available on all the user's devices. **Engelle** ayarı iCloud'a fotoğraf akışının eşitlenmesini önler. Blocking this feature may cause data loss. 
- **iCloud Photo Library**: Set to **Block** to disable using iCloud photo library to store photos and videos in the cloud. iCloud Fotoğraf Arşivi'nden cihaza tamamen indirilmeyen tüm fotoğraflar cihazdan kaldırılır. **Not configured** (default) allows using the iCloud photo library.
- **Shared photo stream**: Choose **Block** to disable **iCloud Photo Sharing** on the device. **Not configured** (default) allows shared photo streaming.
- **Handoff**: **Not configured** (default) allows users to start work on an iOS device, and then continue the work they started on another iOS or macOS device. **Engelle** ayarı bu iletimi önler.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Settings apply to: Automated device enrollment (supervised)

- **Backup to iCloud**: **Not configured** (default) allows the user to back up the device to iCloud. **Engelle** ayarı kullanıcının cihazı iCloud'a yedeklemesini durdurur.

  Starting with iOS 13.0, this setting requires supervised devices.

- **Block iCloud Document sync**: **Not configured** (default) allows document and key-value synchronization to your iCloud storage space. **Engelle** ayarı iCloud'ın belgeleri ve verileri eşitlemesini engeller.

  Starting with iOS 13.0, this setting requires supervised devices.

- **Block iCloud Keychain sync**: Choose **Block** to disable syncing credentials stored in the Keychain to iCloud. **Yapılandırılmadı** (varsayılan), kullanıcıların bu kimlik bilgilerini eşitlemesine izin verir.

  Starting with iOS 13.0, this setting requires supervised devices.

## <a name="autonomous-single-app-mode"></a>Autonomous single app mode

Bu ayarları kullanarak iOS cihazlarını, belirli uygulamaları otonom tek uygulama modunda çalışacak şekilde yapılandırabilirsiniz. Bu mod yapılandırılıp uygulama çalıştırıldığında cihaz kilitlenir. Yalnızca söz konusu uygulamayı çalıştırabilir. Örneğin, kullanıcıların cihazda bir test yapmasına olanak tanıyan bir uygulama ekleyin. Uygulama eylemleri tamamlandığında veya bu ilkeyi kaldırdığınızda cihaz normal durumuna döner.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Settings apply to: Automated device enrollment (supervised)

- **App name**: Enter the name of the app you want.
- **App Bundle ID**: Enter the [bundle ID](bundle-ids-built-in-ios-apps.md) of the app you want.
- **Add**: Select to create your list of apps.

You can also **Import** a CSV file with the list of app names and their bundle IDs. Alternatif olarak uygulamaları içeren mevcut listeyi **dışarı aktarabilirsiniz**.

## <a name="kiosk"></a>Bilgi noktası

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Settings apply to: Automated device enrollment (supervised)

- **App to run in kiosk mode**: Choose the type of apps you want to run in kiosk mode. Seçenekleriniz şunlardır:
  - **Not configured** (default): Kiosk settings aren't applied. Cihaz bilgi noktası modunda çalışmıyor.
  - **Store App**: Enter the URL to an app in the iTunes App store.
  - **Managed App**: Choose an app you added to Intune.
  - **Built-In App**: Enter the [bundle ID](bundle-ids-built-in-ios-apps.md) of the built-in app.

- **Assistive touch**: **Require** the Assistive Touch accessibility setting be on the device. Bu özellik kullanıcılara zorlanabilecekleri ekran hareketlerinde yardımcı olur. **Yapılandırılmadı** ayarı bilgi noktası modunda bu özelliği çalıştırmaz veya etkinleştirmez.
- **Invert colors**: **Require** the Invert Colors accessibility setting so users with visual impairments can change the display screen. **Yapılandırılmadı** ayarı bilgi noktası modunda bu özelliği çalıştırmaz veya etkinleştirmez.
- **Mono audio**: **Require** the Mono audio accessibility setting be on the device. **Yapılandırılmadı** ayarı bilgi noktası modunda bu özelliği çalıştırmaz veya etkinleştirmez.
- **Voice control**: **Require** enables voice control on the device, and allows users to fully control the OS using Siri commands. **Not configured** disables voice control on the device.

  Bu ayarın geçerli olduğu sürümler:  
  - iOS 13.0 and newer
  - iPadOS 13.0 and newer
  
  > [!TIP]
  > If you have LOB apps available for your organization, and they're not **Voice Control** ready on day 0 when iOS 13.0 releases, then we recommend you leave this setting as **Not configured**.

- **VoiceOver**: **Require** the VoiceOver accessibility setting be on the device to read text on the screen out loud. **Yapılandırılmadı** ayarı bilgi noktası modunda bu özelliği çalıştırmaz veya etkinleştirmez.
- **Zoom**: **Require** the Zoom setting be on the device to let users use touch to zoom in on the screen. **Yapılandırılmadı** ayarı bilgi noktası modunda bu özelliği çalıştırmaz veya etkinleştirmez.
- **Auto lock**: **Block** prevents automatic locking of the device. **Not configured** allows this feature.
- **Ringer switch**: **Block** disables the ringer (mute) switch on the device. **Not configured** allows this feature.
- **Screen rotation**: **Block** prevents changing the screen orientation when the user rotates the device. **Not configured** allows this feature.
- **Screen sleep button**: Choose **Block** to disable the screen sleep wake button on the device. **Not configured** allows this feature.
- **Touch**: **Block** disables the touchscreen on the device. **Yapılandırılmadı** ayarı kullanıcının dokunmatik ekranı kullanmasına izin verir.
- **Volume buttons**: **Block** prevents using the volume buttons on the device. **Not configured** allows the volume buttons.
- **Assistive touch control**: **Allow** let users use the assistive touch function. **Yapılandırılmadı** ayarı bu özelliği devre dışı bırakır.
- **Invert colors control**: **Allow** invert color changes to let users adjust the invert colors function. **Yapılandırılmadı** ayarı bu özelliği devre dışı bırakır.
- **Speak on selected text**: **Allow** the Speak Selection accessibility settings be on the device. Bu özellik kullanıcının seçtiği metni yüksek sesle okur. **Yapılandırılmadı** ayarı bu özelliği devre dışı bırakır.
- **Voice control modification**: **Allow** users to change the state of voice control on their devices. **Not configured** blocks users from changing the state of voice control on their devices.

  Bu ayarın geçerli olduğu sürümler:  
  - iOS 13.0 and newer
  - iPadOS 13.0 and newer

- **VoiceOver control**: **Allow** voiceover changes to let users update the VoiceOver function, such as how fast on-screen text is read out loud. **Yapılandırılmadı** ayarı VoiceOver değişikliklerini engeller.
- **Zoom control**: **Allow** zoom changes by the user. **Yapılandırılmadı** ayarı yakınlaştırma değişikliklerini engeller.

> [!NOTE]
> Bir iOS cihazını bilgi noktası modunda yapılandırabilmek için, önce Apple Configurator aracını veya Apple Cihaz Kayıt Programı’nı kullanarak cihazı denetimli moda almanız gerekir. Apple Configurator aracını kullanma konusunda Apple'ın kılavuzuna bakın.
> Girdiğiniz iOS uygulaması siz profil atadıktan sonra yüklendiyse, cihaz yeniden başlatılana kadar bilgi noktası moduna girmez.

## <a name="domains"></a>Domains

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Settings apply to: Device enrollment, Automated device enrollment (supervised)

- **Unmarked email domains** > **Email Domain URL**: Add one or more URLs to the list. Son kullanıcılar, girdiğiniz etki alanları dışındaki bir etki alanından e-posta aldığında bu e-posta iOS Mail uygulamasında güvenilmeyen olarak işaretlenir.

- **Yönetilen web etki alanları** > **Web Etki Alanı URL'si**; Listeye bir veya daha fazla URL ekleyin. Belgeler girdiğiniz etki alanlarından indirildiğinde yönetilen belgeler olarak değerlendirilir. Bu ayar yalnızca Safari tarayıcısı kullanılarak indirilen belgeler için geçerlidir.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Settings apply to: Automated device enrollment (supervised)

- **Safari password autofill domains** > **Domain URL**: Add one or more URLs to the list. Kullanıcılar yalnızca bu listedeki URL’lerdeki parolaları kaydedebilir. This setting applies only to the Safari browser, and devices in supervised mode. If you don't enter any URLs, then passwords can be saved from all web sites.

  Bu ayarın geçerli olduğu sürümler:  
  - iOS 9.3 and newer

## <a name="settings-that-require-supervised-mode"></a>Denetimli mod gerektiren ayarlar

iOS denetimli modu yalnızca Apple Aygıt Kayıt Programı üzerinden ilk cihaz kurulumu sırasında veya Apple Configurator kullanılarak etkinleştirilebilir. Denetimli mod etkinleştirildikten sonra, Intune şu işlevleri kullanarak bir cihazı yapılandırabilir:

- Uygulama Kilidi (Tek Uygulama Modu) 
- Genel HTTP Proxy’si 
- Etkinleştirme Kilidini Atlama 
- Otonom Tek Uygulama Modu 
- Web İçeriği Filtresi 
- Arka plan ve kilit ekranı ayarlama 
- Uygulamaları Sessiz Gönderme 
- Her Zaman Açık VPN 
- Yönetilen uygulama yüklemesine özel olarak izin verme 
- iBookstore 
- iMessages 
- Oyun Merkezi 
- AirDrop 
- AirPlay 
- Konak eşleştirme 
- Bulut Eşitleme 
- Spotlight arama 
- İletim 
- Cihaz silme 
- Kısıtlamalar kullanıcı arabirimi 
- Kullanıcı arabirimine göre yapılandırma profili yüklemesi 
- News 
- Keyboard shortcuts 
- Geçiş kodu değişiklikleri 
- Cihaz adı değişiklikleri 
- Otomatik uygulama indirme 
- Kurumsal uygulama güvenine yapılan değişiklikler 
- Apple Music 
- Posta bırakma 
- Apple Watch ile eşleştirme 

> [!NOTE]
> Apple, 2019’da bazı ayarların yalnızca denetimli hale geleceğini doğruladı. Apple’ın bu ayarları yalnızca denetimli moda aktarmasını beklemek yerine ayarları kullanırken bu durumu göz önünde bulundurmanızı öneririz:
>
> - Son kullanıcılar tarafından uygulama yükleme
> - Uygulama kaldırma
> - FaceTime
> - Safari
> - iTunes
> - Müstehcen içerik
> - iCloud belgeleri ve verileri
> - Multiplayer gaming
> - Oyun Merkezi arkadaşları ekleme
> - Siri

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](../device-profile-assign.md) ve [durumunu izleme](../device-profile-monitor.md).

[macOS](device-restrictions-macos.md) cihazlarındaki özellikleri ve ayarları da kısıtlayabilirsiniz.
