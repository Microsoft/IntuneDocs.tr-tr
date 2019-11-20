---
title: Microsoft Intune'a MTD uygulamaları ekleme ve atama
titleSuffix: Microsoft Intune
description: Azure portalında Intune kullanarak Mobile Threat Defense (MTD) uygulamalarını, Microsoft Authenticator uygulamasını ve iOS yapılandırma ilkesini ekleyin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: davera
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 04a18befe73ce63f5619c3efc6def4189db9c8df
ms.sourcegitcommit: 13fa1a4a478cb0e03c7f751958bc17d9dc70010d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/19/2019
ms.locfileid: "74188476"
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a>Intune ile Mobile Threat Defense (MTD) uygulamaları ekleme ve atama

You can use Intune to add and deploy Mobile Threat Defense (MTD) apps so that end users can receive notifications when a threat is identified in their mobile devices, and to receive guidance to remediate the threats.

> [!NOTE]
> This article applies to all Mobile Threat Defense partners.

## <a name="before-you-begin"></a>Başlamadan önce

Complete the following steps in Intune. Şu işlemlerin nasıl yapıldığını bildiğinizden emin olun:

- [Intune’a uygulama ekleme](../apps/apps-add.md).
- [Intune’a iOS uygulama yapılandırma ilkesi ekleme](../apps/app-configuration-policies-use-ios.md).
- [Intune ile uygulama atama](../apps/apps-deploy.md).

> [!TIP]
> The Intune Company Portal works as the broker on Android devices so users can have their identities checked by Azure AD.

## <a name="configure-microsoft-authenticator-for-ios"></a>iOS için Microsoft Authenticator’ı yapılandırma

iOS cihazlarında, Azure AD'nin kullanıcıların kimlikleri denetleyebilmesi için [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) olması gerekir. Additionally, you need an iOS app configuration policy that sets the MTD iOS app you use with Intune.

Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](../apps/store-apps-ios.md). Use this [Microsoft Authenticator app store URL](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) when you configure **App information**.

## <a name="configure-mtd-applications"></a>MTD uygulamalarını yapılandırma

MTD sağlayıcınızı kapsayan bölümü seçin:

- [Lookout for Work](#configure-lookout-for-work-apps)
- [Symantec Endpoint Protection Mobile (SEP Mobile)](#configure-symantec-endpoint-protection-mobile-apps)
- [Check Point SandBlast Mobile](#configure-check-point-sandblast-mobile-apps)
- [Zimperium](#configure-zimperium-apps)
- [Pradeo](#configure-pradeo-apps)
- [Better Mobile](#configure-better-mobile-apps)
- [Sophos Mobile](#configure-sophos-apps)
- [Wandera](#configure-wandera-apps)

### <a name="configure-lookout-for-work-apps"></a>Lookout for Work uygulamalarını yapılandırma

- **Outlook Web Access (OWA)**
  - Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](../apps/store-apps-android.md). Use this [Lookout for work Google app store URL](https://play.google.com/store/apps/details?id=com.lookout.enterprise) for the **Appstore URL**.

- **Android**
  - Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](../apps/store-apps-ios.md). Use this [Lookout for Work iOS app store URL](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) for the **Appstore URL**.

- **Apple mağazası dışında Lookout for Work uygulaması**
  - You must re-sign the Lookout for Work iOS app. Lookout, Lookout for Work iOS uygulamasını iOS App Store dışında dağıtır. Uygulamayı dağıtmadan önce, iOS Enterprise Developer Certificate ile yeniden imzalamanız gerekir.  
  - Lookout for Work iOS uygulamalarını yeniden imzalama hakkında ayrıntılı yönergeler için Lookout web sitesinde [Lookout for Work iOS uygulamasını yeniden imzalama işlemine](https://personal.support.lookout.com/hc/articles/114094038714) bakın.

  - **Azure AD kimlik doğrulamasını Lookout for Work iOS uygulaması kullanıcıları için etkinleştirin.**

    1. [Azure portalı](https://portal.azure.com)'na gidin, kimlik bilgilerinizle oturum açın, sonra uygulama sayfasına gidin.

    2. **Lookout for Work iOS uygulamasını yerel istemci uygulaması** olarak ekleyin.

    3. IPA’yı imzaladığınızda seçtiğiniz müşteri paketi kimliğini **com.lookout.enterprise.yourcompanyname** ile değiştirin.

    4. Özgün yeniden yönlendirme URI’nizin URL ile şifrelenmiş halini takip eden ek bir yeniden yönlendirme URI’si ekleyin: **&lt;companyportal://code/ >** .

    5. Uygulamanıza **Temsilci İzinleri** ekleyin.

    > [!NOTE]
    > Daha fazla ayrıntı için bkz. [Azure AD ile yerel istemci uygulaması yapılandırma](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

  - **Lookout for Work ipa dosyasını ekleyin.**

    - Upload the re-signed .ipa file as described in the [Add iOS LOB apps with Intune](../apps/lob-apps-ios.md) article. Ayrıca en düşük işletim sistemi sürümünü iOS 8.0 veya üstüne ayarlamanız gerekir.

### <a name="configure-symantec-endpoint-protection-mobile-apps"></a>Symantec Endpoint Protection Mobile uygulamalarını yapılandırma

- **Outlook Web Access (OWA)**
  - Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](../apps/store-apps-android.md). Use this [SEP Mobile app store URL](https://play.google.com/store/apps/details?id=com.skycure.skycure) for the **Appstore URL**.  **En düşük işletim sistemi** için **Android 4.0 (Ice Cream Sandwich)** öğesini seçin.

- **Android**
  - Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](../apps/store-apps-ios.md). Use this [SEP Mobile app store URL](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) for the **Appstore URL**.

### <a name="configure-check-point-sandblast-mobile-apps"></a>Check Point SandBlast Mobile uygulamalarını yapılandırma

- **Outlook Web Access (OWA)**  
  - Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](../apps/store-apps-android.md). Use this [Check Point SandBlast Mobile app store URL](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) for the **Appstore URL**.

- **Android**
  - Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](../apps/store-apps-ios.md). Use this [Check Point SandBlast Mobile app store URL](https://apps.apple.com/us/app/sandblast-mobile-protect/id1006390797) for the **Appstore URL**.  

### <a name="configure-zimperium-apps"></a>Zimperium uygulamalarını yapılandırma

- **Outlook Web Access (OWA)**
  - Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](../apps/store-apps-android.md). Use this [Zimperium app store URL](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en) for the **Appstore URL**.

- **Android**
  - Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](../apps/store-apps-ios.md). Use this [Zimperium app store URL](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8) for the **Appstore URL**.  
 
### <a name="configure-pradeo-apps"></a>Pradeo uygulamalarını yapılandırma

- **Outlook Web Access (OWA)**
  - Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](../apps/store-apps-android.md). Use this [Pradeo app store URL](https://play.google.com/store/apps/details?id=net.pradeo.service&hl=en_US) for the **Appstore URL**.

- **Android**
  - Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](../apps/store-apps-ios.md). Use this [Pradeo app store URL](https://itunes.apple.com/us/app/pradeo-agent/id547979360?mt=8) for the **Appstore URL**.

### <a name="configure-better-mobile-apps"></a>Better Mobile uygulamalarını yapılandırma

- **Outlook Web Access (OWA)**
  - Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](../apps/store-apps-android.md). Use this [Active Shield app store URL](https://play.google.com/store/apps/details?id=com.better.active.shield.enterprise) for the **Appstore URL**.

- **Android**
  - Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](../apps/store-apps-ios.md). Use this [ActiveShield app store URL](https://itunes.apple.com/us/app/activeshield/id980234260?mt=8&uo=4) for the **Appstore URL**.

### <a name="configure-sophos-apps"></a>Configure Sophos apps

- **Outlook Web Access (OWA)**
  - Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](../apps/store-apps-android.md). Use this [Sophos app store URL](https://play.google.com/store/apps/details?id=com.sophos.smsec) for the **Appstore URL**.

- **Android**
  - Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](../apps/store-apps-ios.md). Use this [ActiveShield app store URL](https://itunes.apple.com/us/app/sophos-mobile-security/id1086924662?mt=8) for the **Appstore URL**.

### <a name="configure-wandera-apps"></a>Configure Wandera apps

- **Outlook Web Access (OWA)**
  - Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](../apps/store-apps-android.md). Use this [Wandera Mobile app store URL](https://play.google.com/store/apps/details?id=com.wandera.android) for the **Appstore URL**. For **Minimum operating system**, select **Android 5.0**.

- **Android**
  - Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](../apps/store-apps-ios.md). Use this [Wandera Mobile app store URL](https://itunes.apple.com/app/wandera/id605469330) for the **Appstore URL**.

## <a name="configure-your-mtd-apps-with-an-ios-app-configuration-policy"></a>MTD uygulamalarınızı bir iOS uygulama yapılandırma ilkesiyle yapılandırma

### <a name="lookout-for-work-app-configuration-policy"></a>Lookout for Work uygulama yapılandırma ilkesi

Create the iOS app configuration policy as described in the [using iOS app configuration policy](../apps/app-configuration-policies-use-ios.md) article.

### <a name="sep-mobile-app-configuration-policy"></a>SEP Mobile uygulama yapılandırma ilkesi

Use the same Azure AD account previously configured in the [Symantec Endpoint Protection Management console](https://aad.skycure.com), which should be the same account used to sign in to the Intune.

- **Download** the iOS app configuration policy file:
  - [Symantec Endpoint Protection Yönetim konsoluna](https://aad.skycure.com) gidin ve yönetici kimlik bilgilerinizle oturum açın.

  - **Ayarlar**'a gidin ve **Tümleştirmeler**'in altında **Intune**'u seçin. **EMM Tümleştirme Seçimi**'ni seçin. **Microsoft**'u seçin ve ardından seçiminizi kaydedin.

  - **Tümleştirme kurulum dosyaları** bağlantısına tıklayın ve oluşturulan \*.zip dosyasını kaydedin. Bu .zip dosyası, Intune’da iOS uygulama yapılandırma ilkesini oluşturmak için kullanılacak olan * **.plist** dosyasını içerir.

  - SEP Mobile iOS uygulama yapılandırma ilkesini eklemek için [iOS için Microsoft Intune uygulama yapılandırma ilkeleri kullanma](../apps/app-configuration-policies-use-ios.md) yönergelerine bakın.

    - For **Configuration settings format**, select **Enter XML data**, copy the content from the * **.plist** file, and paste its content into the configuration policy body.

> [!NOTE]
> Dosyaları alamıyorsanız, [Symantec Endpoint Protection Mobile Enterprise Desteği](https://support.symantec.com/en_US/contact-support.html)'ne başvurun.

### <a name="check-point-sandblast-mobile-app-configuration-policy"></a>Check Point SandBlast Mobile uygulaması yapılandırma ilkesi

Check Point SandBlast Mobile iOS uygulama yapılandırma ilkesini eklemek için [iOS için Microsoft Intune uygulama yapılandırma ilkelerini kullanma](../apps/app-configuration-policies-use-ios.md) yönergelerine bakın.

- For **Configuration settings format**, select **Enter XML data**, copy the following content and paste it into the configuration policy body.

  `<dict><key>MDM</key><string>INTUNE</string></dict>`


### <a name="zimperium-app-configuration-policy"></a>Zimperium uygulama yapılandırma ilkesi

Zimperium iOS uygulama yapılandırma ilkesini eklemek için [iOS için Microsoft Intune uygulama yapılandırma ilkeleri kullanma](../apps/app-configuration-policies-use-ios.md) yönergelerine bakın.

- For **Configuration settings format**, select **Enter XML data**, copy the following content and paste it into the configuration policy body.

   ```
   <dict>
   <key>provider</key><string>Intune</string>
   <key>userprincipalname</key><string>{{userprincipalname}}</string>
   <key>deviceid</key>
   <string>{{deviceid}}</string>
   <key>serialnumber</key>
   <string>{{serialnumber}}</string>
   <key>udidlast4digits</key>
   <string>{{udidlast4digits}}</string>
   </dict>
   ```

### <a name="pradeo-app-configuration-policy"></a>Pradeo app configuration policy

Pradeo doesn't support application configuration policy on iOS.  Instead, to get a configured app, work with Pradeo to implement custom IPA or APK files that are preconfigured with the settings you want.

### <a name="better-mobile-app-configuration-policy"></a>Better Mobile uygulama yapılandırma ilkesi

Better Mobile iOS uygulama yapılandırma ilkesini eklemek için [iOS için Microsoft Intune uygulama yapılandırma ilkeleri kullanma](../apps/app-configuration-policies-use-ios.md) yönergelerine bakın.

- For **Configuration settings format**, select **Enter XML data**, copy the following content and paste it into the configuration policy body. `https://client.bmobi.net` URL'sini uygun konsol URL'siyle değiştirin.

   ```
    <dict>
   <key>better_server_url</key>
   <string>https://client.bmobi.net</string>
   <key>better_udid</key>
   <string>{{aaddeviceid}}</string>
   <key>better_user</key>
   <string>{{userprincipalname}}</string>
   </dict>
   ```

### <a name="sophos-mobile-app-configuration-policy"></a>Sophos Mobile app configuration policy

Create the iOS app configuration policy as described in the [using iOS app configuration policy](../apps/app-configuration-policies-use-ios.md) article.

### <a name="wandera-app-configuration-policy"></a>Wandera app configuration policy

See the instructions for [using Microsoft Intune app configuration policies for iOS](../apps/app-configuration-policies-use-ios.md) to add the Wandera iOS app configuration policy.

- For **Configuration settings format**, select **Enter XML data**.

Sign in to your RADAR Wandera portal and browse to **Settings** > **EMM Integration** > **App Push**. Select **Intune**, and then copy the content below and paste it into the configuration policy body.  

  ```
  <dict><key>secretKey</key>
  <string>SeeRADAR</string>
  <key>apiKey</key>
  <string> SeeRADAR </string>
  <key>customerId</key>
  <string> SeeRADAR </string>
  <key>email</key>
  <string>{{mail}}</string>
  <key>firstName</key>
  <string>{{username}}</string>
  <key>lastName</key>
  <string></string>
  <key>activationType</key>
  <string>PROVISION_THEN_AWP</string></dict>
  ```

## <a name="assign-apps-to-groups"></a>Gruplara uygulama atama

Bu adım, tüm MTD iş ortakları için geçerlidir. [Intune ile gruplara uygulama atama](../apps/apps-deploy.md) yönergelerine bakın.

## <a name="next-steps"></a>Sonraki adımlar

- [MTD için cihaz uyumluluk ilkesini yapılandırma](mtd-device-compliance-policy-create.md)
