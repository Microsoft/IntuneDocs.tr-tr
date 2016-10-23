---
title: "Lookout for Work uygulamasını dağıtma | Microsoft Intune"
description: "Android için Lookout for Work uygulamasını yapılandırın ve dağıtın."
author: karthikaraman
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 99005e15268a60cd801ef1c717088dff2f82927b
ms.openlocfilehash: 8dce0689d5c4a0672b227eedf3ae738217eb17cf


---

# Lookout for Work uygulamalarını yapılandırma ve dağıtma
Bu makalede, Android ve iOS cihazlarda Lookout for Work uygulamasının nasıl yapılandırılacağı ve dağıtılacağı açıklanır.

## Android (Google Play Store uygulaması)

* **1. Adım:**   Lookout for Android uygulamasını, [Microsoft Intune yönetici konsoluna](https://manage.microsoft.com) [Microsoft Intune'da mobil cihazlar için uygulama ekleme](https://docs.microsoft.com/en-us/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune) bölümünde açıklandığı gibi yükleyin.
>[!NOTE]
> Yönetilen tarayıcı gerekliliğine yönelik kutuya tıklamayın.

![Intune Yönetici Konsolu uygulamalar sayfasının Lookout for Work uygulamalarını listede gösteren ekran görüntüsü](../media/mtp/lookout-app-listed-intune-console.png)

* **2. Adım:** Uygulamayı kullanıcılara dağıtın. Yukarıdaki ekranda gösterilen Lookout for Work uygulamasını seçin ve ardından **Dağıtımı Yönet**’i seçin.

  Lookout konsolundaki Kayıt Yönetimi seçeneğine eklenmiş olan kullanıcıları seçmeniz gerekir.  Lookout MTP’ye kullanıcı grupları ekleme hakkında daha fazla bilgi için [aboneliğinizi Lookout cihaz tehdit koruması ile yapılandırma](set-up-your-subscription-with-lookout-mtp#configure-your-subscription-with-lookout-mtp) bölümündeki 3. Adıma göz atın.
>[!IMPORTANT]
> Intune uygulama dağıtım sihirbazı, Azure AD kullanıcı gruplarını tanımaz ve bunun yerine Intune kullanıcı gruplarını kullanır. Bu nedenle, [bu](plan-your-user-and-device-groups.md) konu başlığı altında açıklanan adımları uygulayarak Lookout konsoluna kayıtlı Azure AD kullanıcı grubunu temel alan bir Intune kullanıcı grubu oluşturmanız gerekir.

**Gerekli Yükleme** seçeneğini belirleyerek Lookout uygulamasının kullanıcı cihazında yüklü olmasını zorunlu hale getirin.


## iOS (Lookout uygulamasının Kuruluş imzalı sürümü)

* **1. Adım:** Cihazınızda **iOS yönetimi** ayarlandığından emin olun. Cihazınızı iOS yönetimi için ayarlama konusunda yönergeler için bkz. [iOS ve Mac yönetimini ayarlama](Set up iOS and Mac device management.md).

* **2. Adım:** Lookout for Work iOS uygulamasını **yeniden imzalayın**. Lookout, Lookout for Work iOS uygulamasını iOS App Store dışında dağıtır. **Uygulamayı dağıtmadan önce**, uygulamayı iOS Enterprise Developer Certificate ile yeniden imzalamanız gerekir. Lookout for Work iOS uygulamalarını yeniden imzalama hakkında ayrıntılı yönergeler için Lookout sitesinde bkz. [Lookout for Work iOS uygulamasını yeniden imzalama işlemi](https://personal.support.lookout.com/hc/en-us/articles/114094038714).


* **3. Adım:** iOS için Azure Active Directory kimlik doğrulamasını etkinleştirmek üzere aşağıdakileri yapın:
  1.  [Azure Active Directory yönetim portalı](https://manage.windowsazure.com)’nda oturum açın ve uygulama sayfasına gidin.
  2.  **Lookout for Work iOS uygulamasını** **yerel istemci uygulaması** olarak ekleyin.
  ![yerel uygulama seçeneğini gösteren uygulama ekle iletişim kutusunun ekran görüntüsü](../media/mtp/aad-add-app.png)
  
  3. IPA’yı imzaladığınızda seçtiğiniz müşteri paketi kimliğini **com.lookout.enterprise.yourcompanyname** ile değiştirin.
  4.  **&lt;companyportal://code/ >** ek yeniden yönlendirme URI'sini ve ardından özgün yeniden yönlendirme URI’nizin URL kodlu sürümünü ekleyin.
  5.  Uygulamanıza **Temsilci İzinleri** ekleyin.

  Daha fazla ayrıntı için bkz. [Bir yerel istemci uygulaması yapılandırma](https://azure.microsoft.com/en-us/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).


* **4. Adım:** Yeniden imzalanan .ipa dosyasını [Microsoft Intune’da mobil cihazlar için uygulama ekleme](https://docs.microsoft.com/en-us/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune) bölümünde açıklandığı gibi karşıya yükleyin. En düşük işletim sistemi sürümünü iOS 8.0 veya üzeri olarak ayarlayın.

  ![Intune yönetici konsolundaki uygulamalar sayfasında Lookout for Work’ün uygulama listesinde gösterildiği ekran görüntüsü](../media/mtp/ios-app-uploaded-intune.png)

* **5. Adım:** Yönetilen uygulama yapılandırma ilkesini [iOS uygulamalarını Microsoft Intune’da mobil uygulama yapılandırma ilkeleriyle yapılandırma](https://docs.microsoft.com/en-us/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune) bölümünde açıklandığı gibi oluşturun.

  ![iOS 8.0 veya üzeri yapılandırma ilkesi vurgulanmış olarak yeni ilke oluştur sihirbazının ekran görüntüsü](../media/mtp/ios-app-config.png)

* **6. Adım:** **Uygulamayı kullanıcılara dağıtmak için** Lookout for Work uygulamasını ve **Dağıtımı Yönet**’i seçin.

  Lookout konsolundaki Kayıt Yönetimi seçeneğine eklenmiş olan kullanıcıları seçmeniz gerekir.  Lookout MTP’ye kullanıcı grupları ekleme hakkında daha fazla bilgi için [aboneliğinizi Lookout cihaz tehdit koruması ile yapılandırma](set-up-your-subscription-with-lookout-mtp#configure-your-subscription-with-lookout-mtp) bölümündeki 3. Adıma göz atın.
>[!IMPORTANT]
> Intune uygulama dağıtım sihirbazı, Azure AD kullanıcı gruplarını tanımaz ve bunun yerine Intune kullanıcı gruplarını kullanır. Bu nedenle, [bu](plan-your-user-and-device-groups.md) konu başlığı altında açıklanan adımları uygulayarak Lookout konsoluna kayıtlı Azure AD kullanıcı grubunu temel alan bir Intune kullanıcı grubu oluşturmanız gerekir.

**Gerekli Yükleme** seçeneğini belirleyerek Lookout uygulamasının kullanıcı cihazında yüklü olmasını zorunlu hale getirin.

## Dağıtılmış uygulama cihazda açıldığında ne olur?




Kullanıcı cihazda Lookout for Work’ü açtığında uygulamayı etkinleştirmeleri ve Azure Active Directory seçeneği ile Oturum Açmaları istenir. Son kullanıcı akışı ile ayrıntılı bir rehber aşağıdaki konularda bulunabilir:

* [Android cihazınızda Lookout for Work uygulamasını yüklemeniz istendi](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

* [Lookout for Work’ün Android cihazınızda bulduğu bir tehdidi gidermeniz gerekiyor](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## Sonraki adımlar
* [Uyumluluk ilkesinde cihaz tehdit koruması kuralını etkinleştirme](enable-device-threat-protection-rule-in-compliance-policy.md)



<!--HONumber=Oct16_HO2-->


