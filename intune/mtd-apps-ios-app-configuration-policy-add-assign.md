---
title: Microsoft Intune'a MTD uygulamaları ekleme ve atama
titleSuffix: ''
description: Azure portalında Intune kullanarak Mobile Threat Defense (MTD) uygulamalarını, Microsoft Authenticator uygulamasını ve iOS yapılandırma ilkesini ekleyin.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 06/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6c7f3229c2cb4c5f3f57d84d348053f25eeeb9c9
ms.sourcegitcommit: f70d6aaea59b52cd0d7bd3008afd243868967fd6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37066224"
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a>Intune ile Mobile Threat Defense (MTD) uygulamaları ekleme ve atama

> [!NOTE] 
> Bu konu, tüm Mobile Threat Defense iş ortakları için geçerlidir.

Son kullanıcıların mobil cihazlarında bir tehdit algılandığında bildirim ve bu tehditleri ortadan kaldıracak rehberlik alması için MTD uygulamaları eklemek ve dağıtmak üzere Intune’u kullanabilirsiniz.


## <a name="before-you-begin"></a>Başlamadan önce

Aşağıdaki adımların [Azure portalında](https://portal.azure.com/) tamamlanması gerekir. Şu işlemlerin nasıl yapıldığını bildiğinizden emin olun:

  -   [Intune’a uygulama ekleme](apps-add.md).
  -   [Intune’a iOS uygulama yapılandırma ilkesi ekleme](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).
  -   [Intune ile uygulama atama](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune).
  -   [ iOS uygulama yapılandırma ilkesi ekleme](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

> [!TIP]
> Intune şirket portalı, Android cihazlarda kullanıcı kimliklerinin Azure AD tarafından denetlenebilmesi için aracı olarak çalışır.

## <a name="configure-microsoft-authenticator-for-ios"></a>iOS için Microsoft Authenticator’ı yapılandırma
iOS cihazlarında, Azure AD'nin kullanıcıların kimlikleri denetleyebilmesi için [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) olması gerekir. Ayrıca, Intune ile kullanılacak MTD iOS uygulamasını bildiren iOS uygulama yapılandırma ilkesi gerekir.

Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](store-apps-ios.md). Bu [Microsoft Authenticator uygulama mağazası URL'sini](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) **Uygulama bilgilerini yapılandır** bölümünün altındaki **12. adımda** kullanın.

## <a name="configure-mtd-applications"></a>MTD uygulamalarını yapılandırma

MTD sağlayıcınızı kapsayan bölümü seçin:

  - [Lookout for Work](#configure-lookout-for-work-apps)
  - [Symantec Endpoint Protection Mobile (SEP Mobile)](#configure-symantec-endpoint-protection-mobile-apps)
  - [Check Point SandBlast Mobile](#configure-check-point-sandblast-mobile-apps)
  - [Zimperium](#configure-zimperium-apps)
  - [Pradeo](#configure-pradeo-apps)

### <a name="configure-lookout-for-work-apps"></a>Lookout for Work uygulamalarını yapılandırma

- **Android**
  - Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](store-apps-android.md). Bu [Lookout for work Google uygulama mağazası URL'sini](https://play.google.com/store/apps/details?id=com.lookout.enterprise) **7. adımda** kullanın.

- **iOS**

  - Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](store-apps-ios.md). Bu [Lookout for Work iOS uygulama mağazası URL'sini](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) **Uygulama bilgilerini yapılandırma** bölümünün altındaki **12. adımda** kullanın.

-   **Apple mağazası dışında Lookout for Work uygulaması**
    - Lookout for Work iOS uygulamasını yeniden imzalamanız gerekir. Lookout, Lookout for Work iOS uygulamasını iOS App Store dışında dağıtır. Uygulamayı dağıtmadan önce, iOS Enterprise Developer Certificate ile yeniden imzalamanız gerekir.
    - Lookout for Work iOS uygulamalarını yeniden imzalama hakkında ayrıntılı yönergeler için Lookout web sitesinde [Lookout for Work iOS uygulamasını yeniden imzalama işlemine](https://personal.support.lookout.com/hc/articles/114094038714) bakın.

    - **Azure AD kimlik doğrulamasını Lookout for Work iOS uygulaması kullanıcıları için etkinleştirin.**

        1. [Azure portalı](https://portal.azure.com)'na gidin, kimlik bilgilerinizle oturum açın, sonra uygulama sayfasına gidin.

        2. **Lookout for Work iOS uygulamasını yerel istemci uygulaması** olarak ekleyin.

        3. IPA’yı imzaladığınızda seçtiğiniz müşteri paketi kimliğini **com.lookout.enterprise.yourcompanyname** ile değiştirin.

        4.  Özgün yeniden yönlendirme URI’nizin URL ile şifrelenmiş halini takip eden ek bir yeniden yönlendirme URI’si ekleyin: **&lt;companyportal://code/ >**.

        5.  Uygulamanıza **Temsilci İzinleri** ekleyin.

        > [!NOTE] 
        > Daha fazla ayrıntı için bkz. [Azure AD ile yerel istemci uygulaması yapılandırma](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

     - **Lookout for Work ipa dosyasını ekleyin.**

        - Yeniden imzalanmış .ipa dosyasını [Intune ile iOS LOB uygulamaları ekleme](lob-apps-ios.md) konusunda anlatıldığı gibi karşıya yükleyin. Ayrıca en düşük işletim sistemi sürümünü iOS 8.0 veya üstüne ayarlamanız gerekir.

### <a name="configure-symantec-endpoint-protection-mobile-apps"></a>Symantec Endpoint Protection Mobile uygulamalarını yapılandırma

 - **Android**

    - Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](store-apps-android.md). **7. adımda**, bu [SEP Mobile uygulama mağazası URL'sini](https://play.google.com/store/apps/details?id=com.skycure.skycure) kullanın.  **En düşük işletim sistemi** için **Android 4.0 (Ice Cream Sandwich)** öğesini seçin.

 - **iOS**

    - Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](store-apps-ios.md). **12. adımda**, **Uygulama bilgilerini yapılandır** bölümünün altında bu [SEP Mobile uygulama mağazası URL'sini](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) kullanın.

### <a name="configure-check-point-sandblast-mobile-apps"></a>Check Point SandBlast Mobile uygulamalarını yapılandırma

 - **Android**

    - Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](store-apps-android.md). **7. adımdaki** [Check Point SandBlast Mobile uygulama mağazası URL’sini](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) kullanın.

 - **iOS**

    - iOS uygulamasını edinmek için [Check Point SandBlast Mobile](https://www.checkpoint.com/products/sandblast-mobile/) ile iletişime geçin. [iOS mağaza uygulamalarını Microsoft Intune’a ekleme](store-apps-ios.md) yönergelerine göz atın, daha sonra **Uygulama bilgilerini yapılandırma** bölümünün altında bulunan **12. adımdaki** Apple Store URL’sini kullanın.

### <a name="configure-zimperium-apps"></a>Zimperium uygulamalarını yapılandırma

 - **Android**

    - Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](store-apps-android.md). **7. adım**'da bu [Zimperium uygulama mağazası URL'sini](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en) kullanın.

 - **iOS**

    - Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](store-apps-ios.md). **Uygulama bilgilerini yapılandırma** bölümünün altındaki **12. adım**'da bu [Zimperium uygulama mağazası URL'sini](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8) kullanın.

### <a name="configure-pradeo-apps"></a>Pradeo uygulamalarını yapılandırma

 - **Android**

    - Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](store-apps-android.md). Bu [Pradeo uygulama mağazası URL’sini](https://play.google.com/store/apps/details?id=net.pradeo.service&hl=en_US) **7. adımda** kullanın.

 - **iOS**

    - Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](store-apps-ios.md). **Uygulama bilgilerini yapılandırma** bölümünün altındaki **12. adımda** bu [Pradeo uygulama mağazası URL’sini](https://itunes.apple.com/us/app/pradeo-agent/id547979360?mt=8) kullanın.

## <a name="configure-your-mtd-apps-with-an-ios-app-configuration-policy"></a>MTD uygulamalarınızı bir iOS uygulama yapılandırma ilkesiyle yapılandırma

### <a name="lookout-for-work-app-configuration-policy"></a>Lookout for Work uygulama yapılandırma ilkesi

- iOS uygulama yapılandırma ilkesini [iOS uygulama yapılandırma ilkesini kullanma](app-configuration-policies-use-ios.md) konusunda anlatıldığı gibi oluşturun.

### <a name="sep-mobile-app-configuration-policy"></a>SEP Mobile uygulama yapılandırma ilkesi

-   Daha önce [Symantec Endpoint Protection Yönetim konsolunda](https://aad.skycure.com) yapılandırılmış olan Azure AD hesabını kullanın. Bu, klasik Intune portalında oturum açarken kullanılan hesap olmalıdır.

-   iOS uygulama yapılandırma ilkesi dosyasını **indirmeniz** gerekir: 
    -   [Symantec Endpoint Protection Yönetim konsoluna](https://aad.skycure.com) gidin ve yönetici kimlik bilgilerinizle oturum açın.

    -   **Ayarlar**'a gidin ve **Tümleştirmeler**'in altında **Intune**'u seçin. **EMM Tümleştirme Seçimi**'ni seçin. **Microsoft**'u seçin ve ardından seçiminizi kaydedin.

    -   **Tümleştirme kurulum dosyaları** bağlantısına tıklayın ve oluşturulan \*.zip dosyasını kaydedin. Bu .zip dosyası, Intune’da iOS uygulama yapılandırma ilkesini oluşturmak için kullanılacak olan ***.plist** dosyasını içerir.

    -   SEP Mobile iOS uygulama yapılandırma ilkesini eklemek için [iOS için Microsoft Intune uygulama yapılandırma ilkeleri kullanma](app-configuration-policies-use-ios.md) yönergelerine bakın.

    - **8. adımda** **XML verisi gir** seçeneğini kullanın, ***.plist** dosyasındaki içeriği kopyalayıp yapılandırma ilkesinin gövdesine yapıştırın.

> [!NOTE]
> Dosyaları alamıyorsanız, [Symantec Endpoint Protection Mobile Enterprise Desteği](https://support.symantec.com/en_US/contact-support.html)'ne başvurun.

### <a name="check-point-sandblast-mobile-app-configuration-policy"></a>Check Point SandBlast Mobile uygulaması yapılandırma ilkesi

- Check Point SandBlast Mobile iOS uygulama yapılandırma ilkesini eklemek için [iOS için Microsoft Intune uygulama yapılandırma ilkelerini kullanma](app-configuration-policies-use-ios.md) yönergelerine bakın.
    - **8. adımda** **XML verisi gir** seçeneğini kullanın, aşağıdaki içeriği kopyalayıp yapılandırma ilkesinin gövdesine yapıştırın.

```
<dict><key>MDM</key><string>INTUNE</string></dict>
```

### <a name="zimperium-app-configuration-policy"></a>Zimperium uygulama yapılandırma ilkesi

- Zimperium iOS uygulama yapılandırma ilkesini eklemek için [iOS için Microsoft Intune uygulama yapılandırma ilkeleri kullanma](app-configuration-policies-use-ios.md) yönergelerine bakın.
    - **8. adımda** **XML verisi gir** seçeneğini kullanın, aşağıdaki içeriği kopyalayıp yapılandırma ilkesinin gövdesine yapıştırın.

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

## <a name="assign-apps-to-groups"></a>Gruplara uygulama atama

- Bu adım, tüm MTD iş ortakları için geçerlidir. [Intune ile gruplara uygulama atama](apps-deploy.md) yönergelerine bakın.

## <a name="next-steps"></a>Sonraki adımlar

- [MTD için cihaz uyumluluk ilkesini yapılandırma](mtd-device-compliance-policy-create.md)
