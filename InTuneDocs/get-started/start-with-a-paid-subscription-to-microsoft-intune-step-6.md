---
title: "İlkeleri ve uygulamaları dağıtma | Microsoft Docs"
description: "Cihazların yönetim kaydı yapıldığında uygulanacak ilke ayarlarını ve uygulama dağıtımlarını etkinleştirebilirsiniz."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 402475d87dc1c57d34669cc9553939521adcd146
ms.lasthandoff: 04/14/2017


---

# <a name="create-policies-and-publish-apps"></a>İlkeleri oluşturma ve uygulamaları yayımlama

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bu konuda Intune yöneticilerinin nasıl ilke oluşturacakları ve yönetilen cihazları dağıtmak için uygulamaları nasıl yayımlayacakları açıklanır.

Uygulamaları Intune'a kaydetmeye başlamadan önce cihazların yönetimi kaydı yapıldığında dağıtılacak olan ilke ayarlarını ve uygulamaları etkinleştirebilirsiniz. Intune ilkeleri, mobil cihazlarda güvenlik ayarlarını denetlemenize, bilgisayarlar için Windows Güvenlik Duvarı ve Endpoint Protection ayarlarını korumanıza ve uygulamaları dağıtmanıza yardımcı olan ayarlar sağlar. Cihazlar Intune'a kaydolduğunda dağıtılacak ilkeleri yapılandırabilir ve uygulamaları ekleyebilirsiniz.

İlkeler ve uygulamalar platforma özgüdür.

## <a name="manage-device-settings"></a>Cihaz ayarlarını yönetme

 Cihaz ilkesi ayarları platforma göre yapılandırılır ve yönetilir. Aşağıdaki bağlantılarda ilgili platformlar için mevcut ayarların listesi bulunur:

- [iOS](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune)
- [Android ve Samsung KNOX Standard](https://docs.microsoft.com/intune/deploy-use/android-policy-settings-in-microsoft-intune)
- [Android for Work](https://docs.microsoft.com/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)
- [Windows 10 (masaüstü ve mobil)](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)
- [Windows 8.1](https://docs.microsoft.com/intune/deploy-use/windows-configuration-policy-settings-in-microsoft-intune)
- [Windows Phone 8.1](https://docs.microsoft.com/intune/deploy-use/windows-phone-8-1-policy-settings-in-microsoft-intune)
- [Windows Ekibi](https://docs.microsoft.com/intune/deploy-use/windows-team-configuration-policy-settings-in-microsoft-intune)
- [Intune istemci yazılımını çalıştıran Windows bilgisayarlar](https://docs.microsoft.com/intune/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)

[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) hakkında daha fazla bilgi edinebilirsiniz.

## <a name="add-and-deploy-apps"></a>Uygulama ekleme ve dağıtma

Intune'a eklediğiniz uygulamaları yönetilen cihazlara dağıtmak için kullanabileceğiniz iki yöntem vardır:
- **Gerekli yükleme** - Uygulamalar yönetilen cihazlara otomatik olarak yüklenir
- **Kullanılabilir yükleme** - Uygulamalar Intune Şirket Portalı'nda görüntülenir ve kullanıcılar cihazlarına yüklemek istedikleri uygulamaları seçebilir

### <a name="add-apps"></a>Uygulamaları ekleme

Öncelikle aşağıdaki yöntemlerden birini kullanarak uygulamaları Intune'a eklemeniz gerekir:
- [Kaydolmuş cihazlar için uygulama ekleme](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)
- [Intune istemci yazılımı bilgisayarları için uygulama ekleme](https://docs.microsoft.com/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)

### <a name="deploy-apps"></a>Uygulama dağıtma

Intune'a eklenen uygulamaları yönetilen cihazlara dağıtabilirsiniz:
- [Uygulamaları cihazlara dağıtma](https://docs.microsoft.com/intune/deploy-use/deploy-use/deploy-apps-in-microsoft-intune)
- Toplu satın alınan uygulamaları dağıtma:
    - [iOS - Toplu Satın Alma Programı](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)
    - [İş için Windows Mağazası](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)
    - [Android for Work](https://docs.microsoft.com/Intune/deploy-use/android-for-work-apps)

    Dağıtılacak uygulamaları ekledikten sonra [uygulamaları yapılandırabilir](https://docs.microsoft.com/intune/deploy-use/update-apps-using-microsoft-intune) ve [uygulamaları izleyebilirsiniz](https://docs.microsoft.com/intune/deploy-use/monitor-apps-in-microsoft-intune).

>[!div class="step-by-step"]

>[&larr; **Kullanıcıları ve cihazları düzenleme**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**Şirket Portalı’nı özelleştirme** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-7.md)  

