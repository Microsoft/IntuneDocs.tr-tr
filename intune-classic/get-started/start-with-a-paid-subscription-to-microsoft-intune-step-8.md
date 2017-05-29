---
title: "Cihaz kaydını etkinleştirme | Microsoft Docs"
description: "MDM yetkilisini ayarlama ve iOS, Windows, Android ve Mac cihazları için kaydı etkinleştirme."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 76d6000c87843d1a785cd1027eb927f565784ca2
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="enable-enrollment-for-mobile-devices"></a>Mobil cihaz kaydını etkinleştirme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bu konuda bir Intune yöneticisinin mobil cihaz kaydını nasıl etkinleştirileceği açıklanır. Telefonunuzda Intune’u kullanırken yardım almak için bkz. [İşleri tamamlamak için yönetilen cihazları kullanma](https://docs.microsoft.com/intune-user-help/company-portal-frequently-asked-questions).

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

- [iOS ve macOS](/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)
- [Window 10 ve Windows Phone](/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune)
- [Window PC](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) (Intune yazılım istemcisi)
- [Android for Work](/intune-classic/deploy-use/set-up-android-for-work)

Kayıt etkinleştirildikten sonra kullanıcılar Şirket Portalı uygulamasını cihazlarına indirerek cihaz kayıt işlemini tamamlayabilirler.

### <a name="enable-company-owned-device-enrollment"></a>Şirkete ait cihaz kaydını etkinleştirme
Aşağıdakiler de dahil olmak üzere çeşitli [şirkete ait cihaz kaydı](/intune-classic/deploy-use/manage-corporate-owned-devices) senaryolarını da etkinleştirebilirsiniz:
- [Apple Cihaz Kaydı Programı](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
- [Apple Configurator Kurulum Yardımcısı kaydı](/intune-classic/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
- [Apple Configurator ile doğrudan kayıt](/intune-classic/deploy-use/ios-direct-enrollment-in-microsoft-intune)
- [Cihaz Kayıt Yöneticisi](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

### <a name="next-steps"></a>Sonraki adımlar
Tebrikler! *Intune hızlı başlangıç kılavuzunun* son adımını da tamamlamış oldunuz. Artık ilk yapılandırmanız tamamlandığına göre, ek MDM işlevselliğini etkinleştirmeyi göz önünde bulundurabilirsiniz.

>[!div class="step-by-step"]
>[&larr; **Cihazları kaydetme**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Yapılandırma sonrası görevler** &rarr;](.\post-configuration-tasks.md)  

