---
title: Microsoft Intune'a MTD uygulamaları ekleme ve atama
titleSuffix: Microsoft Intune
description: Azure portalında Intune kullanarak Mobile Threat Defense (MTD) uygulamalarını, Microsoft Authenticator uygulamasını ve iOS yapılandırma ilkesini ekleyin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/21/2019
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
ms.openlocfilehash: f5ca8b7c94569861ccc5c4235315a7a57de9d838
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72504399"
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a>Intune ile Mobile Threat Defense (MTD) uygulamaları ekleme ve atama  

> [!NOTE] 
> Bu makale tüm Mobile Threat Defense iş ortakları için geçerlidir.

Mobil tehdit savunma (MTD) uygulamalarını eklemek ve dağıtmak için Intune 'u kullanabilirsiniz. böylece, son kullanıcılar mobil cihazlarında bir tehdit tanımlandığında bildirim alabilir ve tehditleri düzeltmeye yönelik rehberlik elde edebilir.

## <a name="before-you-begin"></a>Başlamadan önce    
Aşağıdaki adımların [Azure portalında](https://portal.azure.com/) tamamlanması gerekir. Şu işlemlerin nasıl yapıldığını bildiğinizden emin olun:

- [Intune’a uygulama ekleme](../apps/apps-add.md).
- [Intune’a iOS uygulama yapılandırma ilkesi ekleme](../apps/app-configuration-policies-use-ios.md).
- [Intune ile uygulama atama](../apps/apps-deploy.md).

> [!TIP]
> Intune Şirket Portalı, kullanıcıların kimliklerinin Azure AD tarafından denetlenmesi için Android cihazlarda aracı olarak kullanılır.

## <a name="configure-microsoft-authenticator-for-ios"></a>iOS için Microsoft Authenticator’ı yapılandırma  
iOS cihazlarında, Azure AD'nin kullanıcıların kimlikleri denetleyebilmesi için [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) olması gerekir. Ayrıca, Intune ile kullandığınız MTD iOS uygulamasını ayarlayan bir iOS uygulama yapılandırma ilkesine ihtiyacınız vardır.

Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](../apps/store-apps-ios.md). Bu [Microsoft Authenticator uygulama mağazası URL'sini](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) **Uygulama bilgilerini yapılandır** bölümünün altındaki **12. adımda** kullanın.

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
  - Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](../apps/store-apps-android.md). Bu [Lookout for work Google uygulama mağazası URL'sini](https://play.google.com/store/apps/details?id=com.lookout.enterprise) **7. adımda** kullanın.

- **Android**
  - Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](../apps/store-apps-ios.md). **AppStore URL 'si**için bu [Lookout for Work IOS App Store URL](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) 'sini **adım 11** ' de kullanın.

- **Apple mağazası dışında Lookout for Work uygulaması**  
  - Lookout for Work iOS uygulamasını yeniden imzalamanız gerekir. Lookout, Lookout for Work iOS uygulamasını iOS App Store dışında dağıtır. Uygulamayı dağıtmadan önce, iOS Enterprise Developer Certificate ile yeniden imzalamanız gerekir.  
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

    - Yeniden imzalanan. ipa dosyasını [Intune Ile IOS LOB uygulamaları ekleme](../apps/lob-apps-ios.md) makalesinde açıklandığı gibi karşıya yükleyin. Ayrıca en düşük işletim sistemi sürümünü iOS 8.0 veya üstüne ayarlamanız gerekir.

### <a name="configure-symantec-endpoint-protection-mobile-apps"></a>Symantec Endpoint Protection Mobile uygulamalarını yapılandırma  
- **Outlook Web Access (OWA)**
  - Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](../apps/store-apps-android.md). **7. adımda**, bu [SEP Mobile uygulama mağazası URL'sini](https://play.google.com/store/apps/details?id=com.skycure.skycure) kullanın.  **En düşük işletim sistemi** için **Android 4.0 (Ice Cream Sandwich)** öğesini seçin.

- **Android**
  - Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](../apps/store-apps-ios.md). **AppStore URL 'si**için **adım 11** ' de bu [Sep mobil uygulama mağazası URL 'sini](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) kullanın.

### <a name="configure-check-point-sandblast-mobile-apps"></a>Check Point SandBlast Mobile uygulamalarını yapılandırma  
- **Outlook Web Access (OWA)**  
  - Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](../apps/store-apps-android.md). **7. adımdaki** [Check Point SandBlast Mobile uygulama mağazası URL’sini](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) kullanın.

- **Android**
  - Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](../apps/store-apps-ios.md). **AppStore URL 'si**için **adım 11** ' de bu [Check Point sandblast mobil uygulama mağazası URL](https://apps.apple.com/us/app/sandblast-mobile-protect/id1006390797) 'sini kullanın.  

### <a name="configure-zimperium-apps"></a>Zimperium uygulamalarını yapılandırma  
- **Outlook Web Access (OWA)**
  - Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](../apps/store-apps-android.md). **7. adım**'da bu [Zimperium uygulama mağazası URL'sini](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en) kullanın.

- **Android**
  - Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](../apps/store-apps-ios.md). **AppStore URL 'si**için **adım 11** ' de bu [zyium uygulama mağazası URL](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8) 'sini kullanın.  
 
### <a name="configure-pradeo-apps"></a>Pradeo uygulamalarını yapılandırma  
- **Outlook Web Access (OWA)**
  - Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](../apps/store-apps-android.md). Bu [Pradeo uygulama mağazası URL’sini](https://play.google.com/store/apps/details?id=net.pradeo.service&hl=en_US) **7. adımda** kullanın.

- **Android**
  - Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](../apps/store-apps-ios.md). **AppStore URL 'si**için **adım 11** ' de bu [pradeo uygulama mağazası URL 'sini](https://itunes.apple.com/us/app/pradeo-agent/id547979360?mt=8) kullanın.

### <a name="configure-better-mobile-apps"></a>Better Mobile uygulamalarını yapılandırma  
- **Outlook Web Access (OWA)**
  - Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](../apps/store-apps-android.md). **7. adımda** bu [Active Shield uygulama mağazası URL'sini](https://play.google.com/store/apps/details?id=com.better.active.shield.enterprise) kullanın.

- **Android**
  - Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](../apps/store-apps-ios.md). **AppStore URL 'si**için **adım 11** ' de bu [ActiveShield App Store URL 'sini](https://itunes.apple.com/us/app/activeshield/id980234260?mt=8&uo=4) kullanın.

### <a name="configure-sophos-apps"></a>Sophos uygulamalarını yapılandırma  
- **Outlook Web Access (OWA)**
  - Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](../apps/store-apps-android.md). **7. adımda**Bu [Sophos App Store URL 'sini](https://play.google.com/store/apps/details?id=com.sophos.smsec) kullanın.

- **Android**
  - Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](../apps/store-apps-ios.md). **AppStore URL 'si**için **adım 11** ' de bu [ActiveShield App Store URL 'sini](https://itunes.apple.com/us/app/sophos-mobile-security/id1086924662?mt=8) kullanın.

### <a name="configure-wandera-apps"></a>Wandera uygulamalarını yapılandırma  
 
- **Outlook Web Access (OWA)**
  - Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](../apps/store-apps-android.md). **Adım 7**' de bu [Wandera mobil uygulama mağazası URL 'sini](https://play.google.com/store/apps/details?id=com.wandera.android) kullanın. **En düşük işletim sistemi**için **Android 5,0**' i seçin.

- **Android**
  - Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](../apps/store-apps-ios.md). **AppStore URL 'si**için **adım 11** ' de bu [wandera mobil uygulama mağazası URL 'sini](https://itunes.apple.com/app/wandera/id605469330) kullanın.

## <a name="configure-your-mtd-apps-with-an-ios-app-configuration-policy"></a>MTD uygulamalarınızı bir iOS uygulama yapılandırma ilkesiyle yapılandırma  

### <a name="lookout-for-work-app-configuration-policy"></a>Lookout for Work uygulama yapılandırma ilkesi  
- İOS uygulama yapılandırma ilkesini [iOS uygulama yapılandırma ilkesi kullanma](../apps/app-configuration-policies-use-ios.md) makalesinde açıklandığı gibi oluşturun.

### <a name="sep-mobile-app-configuration-policy"></a>SEP Mobile uygulama yapılandırma ilkesi  
- Daha önce [Symantec Endpoint Protection yönetim konsolunda](https://aad.skycure.com)yapılandırılmış olan Azure AD hesabını kullanın. Bu, klasik Intune portalında oturum açmak için kullanılan hesap olmalıdır.

- İOS uygulama yapılandırma ilkesi dosyasını **indirin** : 
  - [Symantec Endpoint Protection Yönetim konsoluna](https://aad.skycure.com) gidin ve yönetici kimlik bilgilerinizle oturum açın.

  - **Ayarlar**'a gidin ve **Tümleştirmeler**'in altında **Intune**'u seçin. **EMM Tümleştirme Seçimi**'ni seçin. **Microsoft**'u seçin ve ardından seçiminizi kaydedin.

  - **Tümleştirme kurulum dosyaları** bağlantısına tıklayın ve oluşturulan \*.zip dosyasını kaydedin. Bu .zip dosyası, Intune’da iOS uygulama yapılandırma ilkesini oluşturmak için kullanılacak olan * **.plist** dosyasını içerir.

  - SEP Mobile iOS uygulama yapılandırma ilkesini eklemek için [iOS için Microsoft Intune uygulama yapılandırma ilkeleri kullanma](../apps/app-configuration-policies-use-ios.md) yönergelerine bakın.

  - **8. adımda** **XML verisi gir** seçeneğini kullanın, * **.plist** dosyasındaki içeriği kopyalayıp yapılandırma ilkesinin gövdesine yapıştırın.

> [!NOTE]  
> Dosyaları alamıyorsanız, [Symantec Endpoint Protection Mobile Enterprise Desteği](https://support.symantec.com/en_US/contact-support.html)'ne başvurun.

### <a name="check-point-sandblast-mobile-app-configuration-policy"></a>Check Point SandBlast Mobile uygulaması yapılandırma ilkesi  
- Check Point SandBlast Mobile iOS uygulama yapılandırma ilkesini eklemek için [iOS için Microsoft Intune uygulama yapılandırma ilkelerini kullanma](../apps/app-configuration-policies-use-ios.md) yönergelerine bakın.
  - **8. adımda** **XML verisi gir** seçeneğini kullanın, aşağıdaki içeriği kopyalayıp yapılandırma ilkesinin gövdesine yapıştırın.

        <dict><key>MDM</key><string>INTUNE</string></dict>


### <a name="zimperium-app-configuration-policy"></a>Zimperium uygulama yapılandırma ilkesi  
- Zimperium iOS uygulama yapılandırma ilkesini eklemek için [iOS için Microsoft Intune uygulama yapılandırma ilkeleri kullanma](../apps/app-configuration-policies-use-ios.md) yönergelerine bakın.
  - **8. adımda** **XML verisi gir** seçeneğini kullanın, aşağıdaki içeriği kopyalayıp yapılandırma ilkesinin gövdesine yapıştırın.
 
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

### <a name="pradeo-app-configuration-policy"></a>Pradeo uygulama yapılandırma ilkesi  
Pradeo, iOS üzerinde uygulama yapılandırma ilkesini desteklemez.  Bunun yerine, yapılandırılmış bir uygulama almak için, tercih ettiğiniz ayarlarla önceden yapılandırılmış özel IPA veya APK dosyalarını uygulamak üzere Pradeo ile birlikte çalışın.

### <a name="better-mobile-app-configuration-policy"></a>Better Mobile uygulama yapılandırma ilkesi  
- Better Mobile iOS uygulama yapılandırma ilkesini eklemek için [iOS için Microsoft Intune uygulama yapılandırma ilkeleri kullanma](../apps/app-configuration-policies-use-ios.md) yönergelerine bakın.
  - **8. adımda** **XML verisi gir** seçeneğini kullanın, aşağıdaki içeriği kopyalayıp yapılandırma ilkesinin gövdesine yapıştırın. `https://client.bmobi.net` URL'sini uygun konsol URL'siyle değiştirin.

        <dict>
        <key>better_server_url</key>
        <string>https://client.bmobi.net</string>
        <key>better_udid</key>
        <string>{{aaddeviceid}}</string>
        <key>better_user</key>
        <string>{{userprincipalname}}</string>
        </dict>


### <a name="sophos-mobile-app-configuration-policy"></a>Sophos mobil uygulama yapılandırma ilkesi  
İOS uygulama yapılandırma ilkesini [iOS uygulama yapılandırma ilkesi kullanma](../apps/app-configuration-policies-use-ios.md) makalesinde açıklandığı gibi oluşturun.

### <a name="wandera-app-configuration-policy"></a>Wandera uygulama yapılandırma ilkesi  
Wandera iOS uygulama yapılandırma ilkesini eklemek için [iOS için Microsoft Intune uygulama yapılandırma ilkeleri kullanma](../apps/app-configuration-policies-use-ios.md) yönergelerine bakın.
- **8. ADıMDA** **XML verisi gir**seçeneğini kullanın. RADAR bir portalda oturum açın ve **ayarlar** > **EMM tümleştirmesi** > **uygulama gönderimi**' ne gidin. **Intune**' u seçin ve ardından aşağıdaki içeriği kopyalayıp yapılandırma ilkesi gövdesine yapıştırın.  

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

## <a name="assign-apps-to-groups"></a>Gruplara uygulama atama  
- Bu adım, tüm MTD iş ortakları için geçerlidir. [Intune ile gruplara uygulama atama](../apps/apps-deploy.md) yönergelerine bakın.

## <a name="next-steps"></a>Sonraki adımlar  
- [MTD için cihaz uyumluluk ilkesini yapılandırma](mtd-device-compliance-policy-create.md)