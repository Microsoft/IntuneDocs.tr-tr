---
title: "Lookout for Work uygulamasını dağıtma | Microsoft Docs"
description: "Android için Lookout for Work uygulamasını yapılandırın ve dağıtın."
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: eaf30c8a59013af6359743227edc8aa6709577c5
ms.lasthandoff: 04/14/2017


---

# <a name="configure-and-deploy-lookout-for-work-app"></a>Lookout for Work uygulamasını yapılandırma ve dağıtma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bu makalede, Android ve iOS cihazlarda Lookout for Work uygulamasının nasıl yapılandırılacağı ve dağıtılacağı açıklanır.

## <a name="android-google-play-store-app"></a>Android (Google Play Store uygulaması)

1.    [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **Uygulamalar**’a gidin ve **Uygulama Ekle**’yi seçin.
2.    Yayımcının **Yazılım Kurulumu** sayfasında **Dış bağlantıyı** seçin ve şu URL'yi belirtin: https://play.google.com/store/apps/details?id=com.lookout.enterprise
  >[!NOTE]
  >Yönetilen tarayıcı gerekliliğine yönelik kutuya tıklamayın.

3.    **Yazılım açıklaması** sayfasında aşağıdaki bilgileri doldurun:
  * **Yayımcı:** Lookout Mobile Security
  * **Adı:**   Lookout for Work
  * **Açıklama:**  Lookout cihazınızı güvenli tutmak için mobil tehditlere karşı en iyi korumayı sunar. Lookout uygulaması cihaza yüklendiğinde, uygulama cihazınızı tehditlerden korur ve herhangi bir tehdit bulunursa size ve şirket yöneticinize uyarı verir.
  * **Kategori:** Bilgisayar Yönetimi

4. İşlemin başarıyla tamamlanmasından sonra **Microsoft Intune’a veri yükleme başarıyla tamamlandı** iletisini görürsünüz.

  Intune konsolunda **Uygulamalar**’a tıkladığınızda artık **Lookout for Work** uygulamasını listede görürsünüz ![Lookout for Work uygulamalarını listede gösteren Intune yönetim konsolu uygulamaları sayfasının ekran görüntüsü](../media/mtp/lookout-app-listed-intune-console.png)

5. Uygulamayı kullanıcılara dağıtmak için Lookout for Work uygulamasını ve **Dağıtımı Yönet**’i seçin.

  Lookout MTP konsolundaki Kayıt Yönetimi seçeneğine eklenen kullanıcıları seçmeniz gerekir.  Lookout MTP’ye kullanıcı grupları ekleme hakkında daha fazla bilgi için [Lookout MTP bölümü ile aboneliğinizi yapılandırma](configure-and-deploy-lookout-for-work-apps.md) bölümünün 3. Adımına göz atın.

  >[!IMPORTANT]
  > Intune uygulama dağıtım Sihirbazı, Azure AD kullanıcı gruplarını tanımaz ve bunun yerine Intune kullanıcı gruplarını kullanır. Dolayısıyla [bu](plan-your-user-and-device-groups.md) bölümde açıklandığı üzere Lookout MTP konsolunda kayıtlı Azure AD kullanıcı grubuna dayalı bir Intune kullanıcı grubu oluşturmanız gerekir.

6. **Gerekli Yükleme** seçeneğini belirleyerek Lookout uygulamasının kullanıcı cihazında yüklü olmasını zorunlu hale getirin.

## <a name="ios-enterprise-signed-version-of-lookout-app"></a>iOS (Lookout uygulamasının Kuruluş imzalı sürümü)

1. Cihazınızda **iOS yönetimi** ayarlandığından emin olun. Cihazınızı iOS yönetimi için ayarlama konusunda yönergeler için bkz. [iOS ve Mac yönetimini ayarlama](set-up-ios-and-mac-management-with-microsoft-intune.md).

2. Lookout for Work iOS uygulamasını **yeniden imzalayın**. Lookout, Lookout for Work iOS uygulamasını iOS App Store dışında dağıtır. **Uygulamayı dağıtmadan önce**, uygulamayı iOS Enterprise Developer Certificate ile yeniden imzalamanız gerekir. Lookout for Work iOS uygulamalarını yeniden imzalama hakkında ayrıntılı yönergeler için Lookout sitesinde bkz. [Lookout for Work iOS uygulamasını yeniden imzalama işlemi](https://personal.support.lookout.com/hc/articles/114094038714).

3. iOS için Azure Active Directory kimlik doğrulamasını etkinleştirmek üzere aşağıdakileri yapın:
  1.  [Azure Active Directory yönetim portalı](https://manage.windowsazure.com)’nda oturum açın ve uygulama sayfasına gidin.
  2.  **Lookout for Work iOS uygulamasını** **yerel istemci uygulaması** olarak ekleyin.
  ![yerel uygulama seçeneğini gösteren uygulama ekle iletişim kutusunun ekran görüntüsü](../media/mtp/aad-add-app.png)
  3. IPA’yı imzaladığınızda seçtiğiniz müşteri paketi kimliğini **com.lookout.enterprise.yourcompanyname** ile değiştirin.
  4.  **&lt;companyportal://code/ >** ek yeniden yönlendirme URI'sini ve ardından özgün yeniden yönlendirme URI’nizin URL kodlu sürümünü ekleyin.
  5.  Uygulamanıza **Temsilci İzinleri** ekleyin.

  Daha fazla ayrıntı için bkz. [Bir yerel istemci uygulaması yapılandırma](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

4. Yeniden imzalanan .ipa dosyasını [Microsoft Intune’da mobil cihazlar için uygulama ekleme](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune) bölümünde açıklandığı gibi karşıya yükleyin. En düşük işletim sistemi sürümünü iOS 8.0 veya üzeri olarak ayarlayın.

  ![Intune yönetici konsolundaki uygulamalar sayfasında Lookout for Work’ün uygulama listesinde gösterildiği ekran görüntüsü](../media/mtp/ios-app-uploaded-intune.png)

5. Yönetilen uygulama yapılandırma ilkesini, [iOS uygulamalarını Microsoft Intune’da mobil uygulama yapılandırma ilkeleriyle yapılandırma](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune) bölümünde açıklandığı gibi oluşturun.

  ![iOS 8.0 veya üzeri yapılandırma ilkesi vurgulanmış olarak yeni ilke oluştur sihirbazının ekran görüntüsü](../media/mtp/ios-app-config.png)

6. **Uygulamayı kullanıcılara dağıtmak için** Lookout for Work uygulamasını ve **Dağıtımı Yönet**’i seçin.

  Lookout konsolundaki Kayıt Yönetimi seçeneğine eklenmiş olan kullanıcıları seçmeniz gerekir.  Lookout MTP’ye kullanıcı grupları ekleme hakkında daha fazla bilgi için [Lookout aboneliğinizi yapılandırma bölümünün](https://docs.microsoft.com/sccm/protect/deploy-use/configure-and-deploy-lookout-for-work-apps) 3. Adımına bakın.

  >[!IMPORTANT]
  > Intune uygulama dağıtım sihirbazı, Azure AD kullanıcı gruplarını tanımaz ve bunun yerine Intune kullanıcı gruplarını kullanır. Bu nedenle, [bu](plan-your-user-and-device-groups.md) konu başlığı altında açıklanan adımları uygulayarak Lookout konsoluna kayıtlı Azure AD kullanıcı grubunu temel alan bir Intune kullanıcı grubu oluşturmanız gerekir.

  **Gerekli Yükleme** seçeneğini belirleyerek Lookout uygulamasının kullanıcı cihazında yüklü olmasını zorunlu hale getirin.

## <a name="what-happens-when-the-deployed-app-is-opened-on-the-device"></a>Dağıtılmış uygulama cihazda açıldığında ne olur?

Kullanıcı cihazda Lookout for Work’ü açtığında uygulamayı etkinleştirmeleri ve Azure Active Directory seçeneği ile Oturum Açmaları istenir. Son kullanıcı akışı ile ayrıntılı bir rehber aşağıdaki konularda bulunabilir:

* [Android cihazınıza Lookout for Work uygulamasını yüklemeniz isteniyor](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

* [Lookout for Work’ün Android cihazınızda bulduğu bir tehdidi gidermeniz gerekiyor](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## <a name="next-steps"></a>Sonraki adımlar
* [Intune'da Lookout cihaz uyumluluğu ilkesi oluşturma](https://docs.microsoft.com/sccm/protect/deploy-use/enable-device-threat-protection-rule-compliance-policy)

