---
title: Microsoft Intune - Azure’da cihaz profillerinde sorun giderme | Microsoft Docs
description: Common questions and answers with device policies and profiles, including profile changes not applied to users or devices, how long it takes for new policies to be pushed to devices, which settings are applied when there are multiple policies, what happens when a profile is deleted or removed, and more with Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/15/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4a1177a37ddbfa7f760339c4ad0cd7773d670540
ms.sourcegitcommit: 01fb3d844958a0e66c7b87623160982868e675b0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74199182"
---
# <a name="common-questions-issues-and-resolutions-with-device-policies-and-profiles-in-microsoft-intune"></a>Common questions, issues, and resolutions with device policies and profiles in Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Get answers to common questions when working with device profiles and policies in Intune. This article also lists the check-in time intervals, provides more detains on conflicts, and more.

## <a name="why-doesnt-a-user-get-a-new-profile-when-changing-a-password-or-passphrase-on-an-existing-wi-fi-profile"></a>Bir kullanıcı, mevcut bir Wi-Fi profilinde parola değiştirirken neden yeni bir profil almıyor?

Şirket Wi-Fi profili oluşturur, profili bir gruba dağıtır, parolayı değiştirir ve profili kaydedersiniz. Profil değiştiğinde, bazı kullanıcılar yeni profili alamayabilir.

Bu sorunu azaltmak için konuk Wi-Fi kurulumu yapın. Şirket Wi-Fi başarısız olursa, kullanıcılar konuk Wi-Fi ile bağlanabilir. Otomatik bağlanma ayarlarının tümünü etkinleştirdiğinizden emin olun. Konuk Wi-Fi profilini tüm kullanıcılara dağıtın.

Bazı ek öneriler:  

- If the Wi-Fi network you're connecting to uses a password or passphrase, make sure you can connect to the Wi-Fi router directly. Bir iOS cihazıyla test edebilirsiniz.
- Bir Wi-Fi uç noktasına (Wi-Fi yönlendiricisi) başarıyla bağlandıktan sonra SSID’yi ve kullanılan kimlik bilgilerini (bu değer erişim kodu veya paroladır) not edin.
- SSID ve kimlik bilgilerini (parola) Önceden Paylaşılan Anahtar alanına girin. 
- Profili, tercihen yalnızca BT ekibinden oluşan, sınırlı sayıda kullanıcıları olan bir test grubuna dağıtın. 
- iOS cihazınızı Intune ile eşitleyin. Daha önce kaydolmadıysanız kaydolun. 
- Aynı Wi-Fi uç noktasına bağlantıyı (ilk adımda bahsedildiği gibi) tekrar test edin.
- Daha büyük gruplara veya sonuçta kuruluşunuzdaki tüm beklenen kullanıcılara dağıtın. 

## <a name="how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned"></a>How long does it take for devices to get a policy, profile, or app after they are assigned?

Intune notifies the device to check in with the Intune service. The notification times vary, including immediately up to a few hours. These notification times also vary between platforms.

If a device doesn't check in to get the policy or profile after the first notification, Intune makes three more attempts. An offline device, such as turned off, or not connected to a network, may not receive the notifications. In this case, the device gets the policy or profile on its next scheduled check-in with the Intune service, which is **estimated** at:

| Platfveyam | Döngü süresi|
| --- | --- |
| iOS | About every 8 hours |
| Mac OS | About every 8 hours |
| Android | About every 8 hours |
| Cihaz olarak kaydedilen Windows 10 bilgisayarlar | About every 8 hours |
| Windows Phone | About every 8 hours |
| Windows 8.1 | About every 8 hours |

If the device recently enrolled, the compliance and configuration check-in runs more frequently, which is **estimated** at:

| Platfveyam | Sıklık |
| --- | --- |
| iOS | Every 15 minutes for 1 hour, and then around every 8 hours |  
| Mac OS | Every 15 minutes for 1 hour, and then around every 8 hours | 
| Android | Every 3 minutes for 15 minutes, then every 15 minutes for 2 hours, and then around every 8 hours | 
| Cihaz olarak kaydedilen Windows 10 bilgisayarlar | Every 3 minutes for 15 minutes, then every 15 minutes for 2 hours, and then around every 8 hours | 
| Windows Phone | Every 5 minutes for 15 minutes, then every 15 minutes for 2 hours, and then around every 8 hours | 
| Windows 8.1 | Every 5 minutes for 15 minutes, then every 15 minutes for 2 hours, and then around every 8 hours | 

At any time, users can open the Company Portal app, **Settings** > **Sync** to immediately check for policy or profile updates.

## <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Hangi eylemler cihaza Intune tarafından anında bildirim gönderilmesine neden olur?

There are different actions that trigger a notification, such as when a policy, profile, or app is assigned (or unassigned), updated, deleted, and so on. These action times vary between platforms.

Devices check in with Intune when they receive a notification to check in, or during the scheduled check-in. When you target a device or user with an action, such as lock, passcode reset, app, profile or policy assignment, then Intune immediately notifies the device to check in to receive these updates.

Other changes, such as revising the contact information in the Company Portal app, don't cause an immediate notification to devices.

## <a name="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-gets-applied"></a>Aynı kullanıcı veya cihaza birden çok ilke atanıyorsa hangi ayarların uygulanacağını nasıl bilebilirim?

When two or more policies are assigned to the same user or device, then the setting that applies happens at the individual setting level:

- Compliance policy settings always have precedence over configuration profile settings.

- If a compliance policy evaluates against the same setting in another compliance policy, then the most restrictive compliance policy setting applies.

- If a configuration policy setting conflicts with a setting in another configuration policy, this conflict is shown in Intune. Bu çakışmaları el ile çözün.

## <a name="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-is-applied-to-the-app"></a>Uygulama koruma ilkeleri birbiriyle çakışırsa ne olur? Uygulamaya hangisi uygulanır?

Conflict values are the most restrictive settings available in an app protection policy *except* for the number entry fields, such as PIN attempts before reset. The number entry fields are set the same as the values, as if you created a MAM policy using the recommended settings option.

Conflicts happen when two profile settings are the same. Örneğin, kopyala/yapıştır ayarı dışında birbirinin aynı olan iki MAM ilkesi yapılandırdığınızı düşünün. Bu senaryoda, kopyala/yapıştır ayarı en kısıtlayıcı değer olarak ayarlanır, ancak ayarların geri kalanı yapılandırıldığı gibi uygulanır.

A policy is deployed to the app and takes effect. A second policy is deployed. In this scenario, the first policy takes precedence, and stays applied. The second policy shows a conflict. If both are applied at the same time, meaning that there isn't preceding policy, then both are in conflict. Çakışmadaki ayarlarda, en kısıtlayıcı olan değerler kullanılır.

## <a name="what-happens-when-ios-custom-policies-conflict"></a>iOS özel ilkeleri çakışırsa ne olur?

Intune, Apple yapılandırma dosyalarının veya özel bir Open Mobile Alliance Tekdüzen Kaynak Tanımlayıcısı (OMA-URI) ilkesinin yükünü değerlendirmez. Yalnızca bir teslim mekanizması olarak görev yapar.

When you assign a custom policy, confirm that the configured settings don't conflict with compliance, configuration, or other custom policies. If a custom policy and its settings conflict, then the settings are applied randomly.

## <a name="what-happens-when-a-profile-is-deleted-or-no-longer-applicable"></a>Bir profil silindiğinde veya artık geçerli olmadığında ne olur?

When you delete a profile, or you remove a device from a group that has the profile, then the profile and settings are removed from the device as described:

- Wi-Fi, VPN, sertifika ve e-posta profilleri: Bu profiller tüm desteklenen kayıtlı cihazlardan kaldırılır.
- Diğer tüm profil türleri:  

  - **Windows and Android devices**: Settings aren't removed from the device
  - **Windows Phone 8.1 cihazları**: Aşağıdaki ayarlar kaldırılır:  
  
    - Mobil cihazların kilidini açmak için bir parola gerektir
    - Basit parolalara izin ver
    - Parola uzunluğu alt sınırı
    - Gerekli parola türü
    - Parola zaman aşımı (gün sayısı)
    - Parola geçmişini anımsa
    - Cihaz temizlenmeden önce izin verilen yinelenen oturum açma hatası sayısı
    - Parola istenmeden önce geçen işlem yapılmayan dakika sayısı
    - Gerekli parola türü – minimum karakter kümesi sayısı
    - Kameraya izin ver
    - Cihazda şifrelemeyi gerektir
    - Çıkarılabilir depolama birimine izin ver
    - Web tarayıcısına izin ver
    - Uygulama mağazasına izin ver
    - Ekran yakalamaya izin ver
    - Coğrafi konuma izin ver
    - Microsoft Hesabına izin ver
    - Kopyalama ve yapıştırmaya izin ver
    - Wi-Fi İnternet paylaşımına izin ver
    - Ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmaya izin ver
    - Wi-Fi etkin noktası bildirimine izin ver
    - Silmeye izin ver
    - Bluetooth'a izin ver
    - NFC'ye izin ver
    - Wi-Fi'a izin ver

  - **iOS**: Aşağıdakiler dışında tüm ayarlar kaldırılır:
  
    - Sesli dolaşıma izin ver
    - Veri dolaşımına izin ver
    - Dolaşım sırasında otomatik eşitlemeye izin ver

## <a name="i-changed-a-device-restriction-profile-but-the-changes-havent-taken-effect"></a>Cihaz kısıtlama profilini değiştirdim ama değişiklikler uygulanmadı

Once set, Windows Phone devices don't allow security policies set using MDM or EAS to be reduced in security. For example, you set a **Minimum number of character password** to 8. You try to reduce it to 4. The more restrictive profile is already applied to the device.

To change the profile to a less secure value, then reset security policies. For example, in Windows 8.1, on the desktop, swipe in from right > select **Settings** > **Control Panel**. **Kullanıcı Hesapları** uygulamasını seçin. In the left-hand navigation menu, there's a **Reset Security Policies** link (toward the bottom). Bunu seçin ve ardından **İlkeleri Sıfırla**’yı seçin.

Other MDM devices, such as Android, Windows Phone 8.1 and later, iOS, and Windows 10 may need to be retired, and re-enrolled in to Intune to apply a less restrictive profile.

## <a name="some-settings-in-a-windows-10-profile-return-not-applicable"></a>Some settings in a Windows 10 profile return "Not Applicable"

Some settings on Windows 10 devices may show as "Not Applicable". When this happens, that specific setting isn't supported on the version or edition of Windows running on the device. This message can occur for the following reasons:

- The setting is only available for newer versions of Windows, and not the current operating system (OS) version on the device.
- The setting is only available for specific Windows editions or specific SKUs, such as Home, Professional, Enterprise, and Education.

To learn more about the version and SKU requirements for the different settings, see the [Configuration Service Provider (CSP) reference](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference).

## <a name="next-steps"></a>Sonraki adımlar

Ek yardım mı gerekiyor? Bkz. [Microsoft Intune için destek alma](../fundamentals/get-support.md).
