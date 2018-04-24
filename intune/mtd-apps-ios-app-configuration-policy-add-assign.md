---
title: Microsoft Intune'a MTD uygulamaları ekleme ve atama
titleSuffix: ''
description: Azure portalında Intune kullanarak Mobile Threat Defense (MTD) uygulamalarını, Microsoft Authenticator uygulamasını ve iOS yapılandırma ilkesini ekleyin.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 07/03/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 08cebf84443e65ded5f7884218fbe17d722bddf2
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a>Intune ile Mobile Threat Defense (MTD) uygulamaları ekleme ve atama

> [!NOTE] 
> Bu konu, tüm Mobile Threat Defense iş ortakları için geçerlidir.

Son kullanıcıların mobil cihazlarında bir tehdit algılandığında bildirim ve bu tehditleri ortadan kaldıracak rehberlik alması için MTD uygulamaları eklemek ve dağıtmak üzere Intune’u kullanabilirsiniz.

iOS cihazlarında, Azure AD'nin kullanıcıların kimlikleri denetleyebilmesi için [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) olması gerekir. Ayrıca, Intune ile kullanılacak MTD iOS uygulamasını bildiren iOS uygulama yapılandırma ilkesi gerekir.

> [!TIP]
> Intune şirket portalı, Android cihazlarda kullanıcı kimliklerinin Azure AD tarafından denetlenebilmesi için aracı olarak çalışır.

## <a name="before-you-begin"></a>Başlamadan önce

-   Aşağıdaki adımların [Azure portalında](https://portal.azure.com/) tamamlanması gerekir.

-   Şu işlemlerin nasıl yapıldığını bildiğinizden emin olun:

    -   [Intune’a uygulama ekleme](apps-add.md).

    -   [Intune’a iOS uygulama yapılandırma ilkesi ekleme](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

    -   [Intune ile uygulama atama](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune).

    -   [ iOS uygulama yapılandırma ilkesi ekleme](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

## <a name="to-add-apps"></a>Uygulama eklemek için

### <a name="all-mtd-partners"></a>Tüm MTD iş ortakları

#### <a name="microsoft-authenticator-app-for-ios"></a>iOS için Microsoft Authenticator uygulaması

- Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](store-apps-ios.md). Bu [Microsoft Authenticator uygulama mağazası URL'sini](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) **Uygulama bilgilerini yapılandır** bölümünün altındaki **5. adımda** kullanın.

### <a name="lookout"></a>Lookout

#### <a name="android"></a>Android
- Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](store-apps-android.md). Bu [Lookout for work Google uygulama mağazası URL'sini](https://play.google.com/store/apps/details?id=com.lookout.enterprise) **7. adımda** kullanın.

#### <a name="ios"></a>iOS

- Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](store-apps-ios.md). Bu [Lookout for Work iOS uygulama mağazası URL'sini](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) **Uygulama bilgilerini yapılandırma** bölümünün altındaki **5. adımda** kullanın.

#### <a name="lookout-for-work-app-outside-the-apple-store"></a>Apple mağazası dışında Lookout for Work uygulaması

Lookout for Work iOS uygulamasını yeniden imzalamanız gerekir. Lookout, Lookout for Work iOS uygulamasını iOS App Store dışında dağıtır. Uygulamayı dağıtmadan önce, iOS Enterprise Developer Certificate ile yeniden imzalamanız gerekir.

Lookout for Work iOS uygulamalarını yeniden imzalama hakkında ayrıntılı yönergeler için Lookout web sitesinde [Lookout for Work iOS uygulamasını yeniden imzalama işlemine](https://personal.support.lookout.com/hc/articles/114094038714) bakın.

##### <a name="enable-azure-ad-authentication-for-lookout-for-work-ios-app"></a>Azure AD kimlik doğrulamasını Lookout for Work iOS uygulaması için etkinleştirme

iOS için Azure Active Directory kimlik doğrulamasını etkinleştirmek üzere aşağıdakileri yapın:

1. [Azure portalı](https://portal.azure.com)'na gidin, kimlik bilgilerinizle oturum açın, sonra uygulama sayfasına gidin.

2. **Lookout for Work iOS uygulamasını****yerel istemci uygulaması** olarak ekleyin.

3. IPA’yı imzaladığınızda seçtiğiniz müşteri paketi kimliğini **com.lookout.enterprise.yourcompanyname** ile değiştirin.

4.  Özgün yeniden yönlendirme URI’nizin URL ile şifrelenmiş halini takip eden ek bir yeniden yönlendirme URI’si ekleyin: **&lt;companyportal://code/ >**.

5.  Uygulamanıza **Temsilci İzinleri** ekleyin.

    > [!NOTE] 
    > Daha fazla ayrıntı için bkz. [Azure AD ile yerel istemci uygulaması yapılandırma](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

##### <a name="add-the-lookout-for-work-ipa-file"></a>Lookout for Work ipa dosyasını ekleme

- Yeniden imzalanmış .ipa dosyasını [Intune ile iOS LOB uygulamaları ekleme](lob-apps-ios.md) konusunda anlatıldığı gibi karşıya yükleyin. Ayrıca en düşük işletim sistemi sürümünü iOS 8.0 veya üstüne ayarlamanız gerekir.

### <a name="skycure"></a>Skycure

#### <a name="android"></a>Android

- Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](store-apps-android.md). Bu [Skycure uygulama mağazası URL'sini](https://play.google.com/store/apps/details?id=com.skycure.skycure) **7. adımda** kullanın.

#### <a name="ios"></a>iOS

- Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](store-apps-ios.md). Bu [Skycure uygulama mağazası URL'sini](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) **Uygulama bilgilerini yapılandır** bölümünün altındaki **5. adımda** kullanın.

### <a name="check-point-sandblast-mobile"></a>Check Point SandBlast Mobile

#### <a name="android"></a>Android

- Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](store-apps-android.md). **7. adımdaki** [Check Point SandBlast Mobile uygulama mağazası URL’sini](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) kullanın.

#### <a name="ios"></a>iOS

- iOS uygulamasını edinmek için [Check Point SandBlast Mobile](https://www.checkpoint.com/products/sandblast-mobile/) ile iletişime geçin. [iOS mağaza uygulamalarını Microsoft Intune’a ekleme](store-apps-ios.md) yönergelerine göz atın, daha sonra **Uygulama bilgilerini yapılandırma** bölümünün altında bulunan **5. adımdaki** Apple store URL’sini kullanın.

### <a name="zimperium"></a>Zimperium

#### <a name="android"></a>Android

- Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](store-apps-android.md). **7. adım**'da bu [Zimperium uygulama mağazası URL'sini](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en) kullanın.

#### <a name="ios"></a>iOS

- Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](store-apps-ios.md). **Uygulama bilgilerini yapılandırma** bölümünün altındaki **5. adım**'da bu [Zimperium uygulama mağazası URL'sini](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8) kullanın.

## <a name="to-associate-the-mtd-app-with-an-ios-app-configuration-policy"></a>MTD uygulamasını bir iOS uygulama yapılandırma ilkesiyle ilişkilendirmek için

### <a name="for-lookout"></a>Lookout için

- iOS uygulama yapılandırma ilkesini [iOS uygulama yapılandırma ilkesini kullanma](app-configuration-policies-use-ios.md) konusunda anlatıldığı gibi oluşturun.

### <a name="for-skycure"></a>Skycure için

-   Daha önce [Skycure Yönetim konsolunda](https://aad.skycure.com) yapılandırılmış olan Azure AD hesabını kullanın. Bu, klasik Intune portalında oturum açarken kullanılan hesap olmalıdır.

-   iOS uygulama yapılandırma ilkesi dosyasını **indirmeniz** gerekir: 
    -   [Skycure Yönetim konsoluna](https://aad.skycure.com) gidin ve yönetici kimlik bilgilerinizle oturum açın.

    -   **Ayarlar** &gt; **Cihaz Yönetimi Tümleştirmeleri** &gt; **EMM Tümleştirme Seçimi**’ne gidin, **Microsoft Intune**’u seçin ve ardından seçiminizi kaydedin.

    -   **Tümleştirme kurulum dosyaları** bağlantısına tıklayın ve oluşturulan \*.zip dosyasını kaydedin. Bu .zip dosyası, Intune’da iOS uygulama yapılandırma ilkesini oluşturmak için kullanılacak olan **skycure\_configuration.plist** dosyasını içerir.

    -   Skycure iOS uygulama yapılandırma ilkesini eklemek için [iOS için Microsoft Intune uygulama yapılandırma ilkeleri kullanma](app-configuration-policies-use-ios.md) yönergelerine bakın.

    - **8. adımda** **XML verisi gir** seçeneğini kullanın, **skycure_configuration.plist** dosyasındaki içeriği kopyalayıp yapılandırma ilkesinin gövdesine yapıştırın.

**skycure_configuration.plist** dosyasının içeriğini şuradan da kopyalayabilirsiniz:

```
<dict>
    <key>MdmType</key>
    <string>Intune</string>
    <key>UserEmail</key>
    <string>{{userprincipalname}}</string>
</dict>
```
### <a name="for-check-point-sandblast-mobile"></a>Check Point SandBlast Mobile için

- Check Point SandBlast Mobile iOS uygulama yapılandırma ilkesini eklemek için [iOS için Microsoft Intune uygulama yapılandırma ilkelerini kullanma](app-configuration-policies-use-ios.md) yönergelerine bakın.
    - **8. adımda** **XML verisi gir** seçeneğini kullanın, aşağıdaki içeriği kopyalayıp yapılandırma ilkesinin gövdesine yapıştırın.

```
<dict><key>MDM</key><string>INTUNE</string></dict>
```

### <a name="for-zimperium"></a>Zimperium için

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

## <a name="to-assign-apps-all-mtd-partners"></a>Uygulama atamak için (Tüm MTD iş ortakları)

- [Intune ile gruplara uygulama atama](apps-deploy.md) yönergelerine bakın.

## <a name="next-steps"></a>Sonraki adımlar

- [MTD için cihaz uyumluluk ilkesi ekleme](mtd-device-compliance-policy-create.md)
