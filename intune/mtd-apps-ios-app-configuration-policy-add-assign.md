---
title: "Intune'a MTD uygulamaları ekleme ve atama"
titleSuffix: Intune on Azure
description: "Azure'da Intune'a MTD uygulamaları, Microsoft Authenticator uygulaması ve iOS yapılandırma ilkesi ekleme"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7b3fb86648a86b161eadfc071bdacbfd4ea0222f
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a>Intune ile Mobile Threat Defense (MTD) uygulamaları ekleme ve atama

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

### <a name="skycure-app-for-android"></a>Android için Skycure uygulaması

- Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](store-apps-android.md). Bu [Skycure uygulama mağazası URL'sini](https://play.google.com/store/apps/details?id=com.skycure.skycure) **7. adımda** kullanın.

### <a name="skycure-app-for-ios"></a>iOS için Skycure uygulaması

- Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](store-apps-ios.md). Bu [Skycure uygulama mağazası URL'sini](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) **Uygulama bilgilerini yapılandır** bölümünün altındaki **5. adımda** kullanın.

### <a name="microsoft-authenticator-app-for-ios"></a>iOS için Microsoft Authenticator uygulaması

- Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](store-apps-ios.md). Bu [Microsoft Authenticator uygulama mağazası URL'sini](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) **Uygulama bilgilerini yapılandır** bölümünün altındaki **5. adımda** kullanın.

### <a name="lookout-for-work-android-app"></a>Lookout for work Android uygulaması

- Yönergeler için bkz. [Microsoft Intune'a Android mağazası uygulamaları ekleme](store-apps-android.md). Bu [Lookout for work Google uygulama mağazası URL'sini](https://play.google.com/store/apps/details?id=com.lookout.enterprise) **7. adımda** kullanın.

### <a name="lookout-for-work-ios-app"></a>Lookout for Work iOS uygulaması

- Yönergeler için bkz. [Microsoft Intune'a iOS mağazası uygulamaları ekleme](store-apps-ios.md). Bu [Lookout for Work iOS uygulama mağazası URL'sini](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) **Uygulama bilgilerini yapılandırma** bölümünün altındaki **5. adımda** kullanın.

### <a name="lookout-for-work-app-outside-the-apple-store"></a>Apple mağazası dışında Lookout for Work uygulaması

Lookout for Work iOS uygulamasını yeniden imzalamanız gerekir. Lookout, Lookout for Work iOS uygulamasını iOS App Store dışında dağıtır. Uygulamayı dağıtmadan önce, iOS Enterprise Developer Certificate ile yeniden imzalamanız gerekir.

Lookout for Work iOS uygulamalarını yeniden imzalama hakkında ayrıntılı yönergeler için Lookout web sitesinde [Lookout for Work iOS uygulamasını yeniden imzalama işlemine](https://personal.support.lookout.com/hc/articles/114094038714) bakın.

#### <a name="enable-azure-ad-authentication-for-lookout-for-work-ios-app"></a>Azure AD kimlik doğrulamasını Lookout for Work iOS uygulaması için etkinleştirme

iOS için Azure Active Directory kimlik doğrulamasını etkinleştirmek üzere aşağıdakileri yapın:

1. [Azure portalı](https://portal.sazure.com)'na gidin, kimlik bilgilerinizle oturum açın, sonra uygulama sayfasına gidin.
  
2. **Lookout for Work iOS uygulamasını** **yerel istemci uygulaması** olarak ekleyin.

3. IPA’yı imzaladığınızda seçtiğiniz müşteri paketi kimliğini **com.lookout.enterprise.yourcompanyname** ile değiştirin.

4.  Özgün yeniden yönlendirme URI’nizin URL ile şifrelenmiş halini takip eden ek bir yeniden yönlendirme URI’si ekleyin: **&lt;companyportal://code/ >**.

5.  Uygulamanıza **Temsilci İzinleri** ekleyin.

    > [!NOTE] 
    > Daha fazla ayrıntı için bkz. [Azure AD ile yerel istemci uygulaması yapılandırma](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

#### <a name="add-the-lookout-for-work-ipa-file"></a>Lookout for Work ipa dosyasını ekleme

- Yeniden imzalanmış .ipa dosyasını [Intune ile iOS LOB uygulamaları ekleme](lob-apps-ios.md) konusunda anlatıldığı gibi karşıya yükleyin. Ayrıca en düşük işletim sistemi sürümünü iOS 8.0 veya üstüne ayarlamanız gerekir.

## <a name="to-associate-the-mtd-app-with-an-ios-app-configuration-policy"></a>MTD uygulamasını bir iOS uygulama yapılandırma ilkesiyle ilişkilendirmek için

### <a name="for-skycure"></a>Skycure için

-   Daha önce Skycure Yönetim konsolunda yapılandırılmış olan Azure AD hesabını kullanın. Bu, Intune klasik konsolunda oturum açarken kullanılanla aynı hesap olmalıdır.

-   Skycure tümleştirme dosyasını kullanıma hazır durumda elinizin altında bulundurmalısınız. Bu, daha önce Skycure Yönetim konsolundan indirilen ve iOS uygulama yapılandırma ilkesi parametrelerinin bulunduğu **skycure\_configuration.plist** dosyasını içeren .zip dosyasıdır.

- Skycure iOS uygulama yapılandırma ilkesini eklemek için [iOS için Microsoft Intune uygulama yapılandırma ilkeleri kullanma](app-configuration-policies-use-ios.md) yönergelerine bakın.
    - 8. adımda **XML verisi gir** seçeneğini kullanın, **skycure_configuration.plist** dosyasındaki içeriği kopyalayıp yapılandırma ilkesi gövdesine yapıştırın.

**skycure_configuration.plist** dosyasının içeriğini şuradan da kopyalayabilirsiniz:

```
<dict>
    <key>MdmType</key>
    <string>Intune</string>
    <key>UserEmail</key>
    <string>{{userprincipalname}}</string>
</dict>

```
### <a name="for-lookout"></a>Lookout için

- iOS uygulama yapılandırma ilkesini [iOS uygulama yapılandırma ilkesini kullanma](app-configuration-policies-use-ios.md) konusunda anlatıldığı gibi oluşturun.

## <a name="to-assign-mtd-apps"></a>MTD uygulamaları atamak için

- [Intune ile gruplara uygulama atama](apps-deploy.md) yönergelerine bakın.

## <a name="next-steps"></a>Sonraki adımlar

[Intune ile Skycure tümleştirmesini kurma](skycure-mtd-connector-integration.md)
[Intune ile Lookout tümleştirmesini kurma](lookout-mtd-connector-integration.md)
