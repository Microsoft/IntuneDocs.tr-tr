---
title: "Cihaz kaydını etkinleştirme | Microsoft Intune"
description: "MDM yetkilisini ayarlama ve iOS, Windows, Android ve Mac cihazları için kaydı etkinleştirme."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 031cf995da4fa46b244b65a6b1c51b6a1aa00d9f
ms.openlocfilehash: 8c3076b26844669f9927478b5847f88f2265c6c9


---

# <a name="enroll-mobile-devices-and-install-an-app"></a>Mobil cihazları kaydetme ve uygulama yükleme
Intune ile mobil cihaz yönetimini ayarlamak için öncelikle hesabınızla ilişkilendirilmiş olan cihazları yönetebilecek hizmeti tanımlayan *mobil cihaz yönetimi yetkilisini* ayarlamanız gerekir. Bu kılavuzda Intune hizmetini System Center Configuration Manager'ın yerine kullanacağınız kabul edilmektedir. MDM yetkilisi ayarlandıktan sonra cihaz platformları için yönetimi etkinleştirebilir ve Şirket Portalı uygulamasıyla cihazlarınızı kaydedebilirsiniz.

## <a name="enable-device-enrollment"></a>Cihaz kaydını etkinleştirme

1. **Intune'u mobil cihaz yönetimi yetkiliniz yapma**
    [Intune yönetici konsolunda](https://manage.microsoft.com/), **Yönetim** > **Mobil Cihaz Yönetimi**'ni seçin ve ardından **Görevler** altında **MDM Yetkilisini Ayarla**'yı seçin.  

2. MDM Yetkilisi iletişim kutusunda **Evet**’i seçin.

    ![Yönetim konsolu. mdm olarak Intune’u ayarlama](./media/mdmAuthority.png)

## <a name="choose-how-to-enroll-devices"></a>Cihazların nasıl kaydedileceğini belirleme

Intune, cihazları şirketinizin gereksinimlerine göre farklı şekillerde yönetebilir. "Kendi cihazını getir" (KCG), şirkete ait cihaz, "kendi cihazını seç" (CYOD) ve bilgi noktası modu, kullanılabilecek kayıt senaryolardan yalnızca birkaçıdır.

[Cihazların nasıl kaydedileceğini belirlemek](choose-how-to-enroll-devices1.md) için bu adımları uygulayın.

## <a name="enable-mdm-for-your-device-platform"></a>Cihaz platformunuz için MDM’yi etkinleştirme
iOS, Mac ve Android for Work cihazları için kayıt işleminin etkinleştirilerek platform sağlayıcısıyla Intune kiracınız arasında ilişki kurulması gerekir. Windows ve Android cihazlarda yapılması gereken ek işlem yoktur ancak Windows cihazlar için özel bir DNS kaydı girişi oluşturarak cihaz kaydını kolay hale getirebilirsiniz.

Yönetmek istediğiniz cihaz platformu için cihaz kaydını etkinleştirin. Platforma bağlı olarak farklı gereksinimler bulunur:

-  [iOS ve macOS](https://docs.microsoft.com/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune.md)
-  [Window bilgisayar](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)
-  [Window 10 Mobile ve Windows Phone](https://docs.microsoft.com/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune)
- [Android for Work](https://docs.microsoft.com/intune/deploy-use/set-up-android-for-work)

Kayıt etkinleştirildikten sonra kullanıcılar Şirket Portalı uygulamasını cihazlarına indirerek cihaz kayıt işlemini tamamlayabilirler.

### <a name="enable-company-owned-device-enrollment"></a>Şirkete ait cihaz kaydını etkinleştirme
Aşağıdakiler de dahil olmak üzere çeşitli [şirkete ait cihaz kaydı](https://docs.microsoft.com/intune/deploy-use/manage-corporate-owned-devices) senaryolarını da etkinleştirebilirsiniz:
- [Apple Cihaz Kaydı Programı](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
- [Apple Configurator Kurulum Yardımcısı kaydı](https://docs.microsoft.com/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
- [Apple Configurator Kurulum Yardımcısı kaydı](https://docs.microsoft.com/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)
- [Cihaz Kayıt Yöneticisi](https://docs.microsoft.com/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

### <a name="next-steps"></a>Sonraki adımlar
Tebrikler! *Intune hızlı başlangıç kılavuzunun* son adımını da tamamlamış oldunuz. Artık ilk yapılandırmanız tamamlandığına göre, ek MDM işlevselliğini etkinleştirmeyi göz önünde bulundurabilirsiniz.

>[!div class="step-by-step"]

>[&larr; **Cihazları kaydetme**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Yapılandırma sonrası görevler** &rarr;](.\post-configuration-tasks.md)  



<!--HONumber=Dec16_HO1-->


