---
title: "İlke ve uygulama dağıtma"
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
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d0a0a3670388ec95cff86b09ea81661a0825ba83
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/10/2017
---
# <a name="create-policies-and-publish-apps"></a>İlkeleri oluşturma ve uygulamaları yayımlama

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bu konuda Intune yöneticilerinin nasıl ilke oluşturacakları ve yönetilen cihazları dağıtmak için uygulamaları nasıl yayımlayacakları açıklanır.

Uygulamaları Intune'a kaydetmeye başlamadan önce cihazların yönetimi kaydı yapıldığında dağıtılacak olan ilke ayarlarını ve uygulamaları etkinleştirebilirsiniz. Intune ilkeleri, mobil cihazlarda güvenlik ayarlarını denetlemenize, bilgisayarlar için Windows Güvenlik Duvarı ve Endpoint Protection ayarlarını korumanıza ve uygulamaları dağıtmanıza yardımcı olan ayarlar sağlar. Cihazlar Intune'a kaydolduğunda dağıtılacak ilkeleri yapılandırabilir ve uygulamaları ekleyebilirsiniz.

İlkeler ve uygulamalar platforma özgüdür.

## <a name="manage-device-settings"></a>Cihaz ayarlarını yönetme

 Cihaz ilkesi ayarları platforma göre yapılandırılır ve yönetilir. Aşağıdaki bağlantılarda ilgili platformlar için mevcut ayarların listesi bulunur:

- [iOS](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune)
- [Android ve Samsung KNOX Standard](/intune-classic/deploy-use/android-policy-settings-in-microsoft-intune)
- [Android for Work](/intune-classic/deploy-use/android-for-work-policy-settings-in-microsoft-intune)
- [Windows 10 (masaüstü ve mobil)](/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune)
- [Windows 8.1](/intune-classic/deploy-use/windows-configuration-policy-settings-in-microsoft-intune)
- [Windows Phone 8.1](/intune-classic/deploy-use/windows-phone-8-1-policy-settings-in-microsoft-intune)
- [Windows Ekibi](/intune-classic/deploy-use/windows-team-configuration-policy-settings-in-microsoft-intune)
- [Intune istemci yazılımını çalıştıran Windows bilgisayarlar](/intune-classic/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)

[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) hakkında daha fazla bilgi edinebilirsiniz.

## <a name="add-and-deploy-apps"></a>Uygulama ekleme ve dağıtma

Intune'a eklediğiniz uygulamaları yönetilen cihazlara dağıtmak için kullanabileceğiniz iki yöntem vardır:
- **Gerekli yükleme** - Uygulamalar yönetilen cihazlara otomatik olarak yüklenir
- **Kullanılabilir yükleme** - Uygulamalar Intune Şirket Portalı'nda görüntülenir ve kullanıcılar cihazlarına yüklemek istedikleri uygulamaları seçebilir

### <a name="add-apps"></a>Uygulamaları ekleme

Öncelikle aşağıdaki yöntemlerden birini kullanarak uygulamaları Intune'a eklemeniz gerekir:
- [Kaydolmuş cihazlar için uygulama ekleme](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)
- [Intune istemci yazılımı bilgisayarları için uygulama ekleme](/intune-classic/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)

### <a name="deploy-apps"></a>Uygulama dağıtma

Intune'a eklenen uygulamaları yönetilen cihazlara dağıtabilirsiniz:
- [Uygulamaları cihazlara dağıtma](/intune-classic/deploy-use/deploy-use/deploy-apps-in-microsoft-intune)
- Toplu satın alınan uygulamaları dağıtma:
    - [iOS - Toplu Satın Alma Programı](/intune-classic/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)
    - [İş İçin Microsoft Mağazası](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)
    - [Android for Work](/intune-classic/deploy-use/android-for-work-apps)

    Uygulamaları dağıtım için yapılandırdıktan sonra [uygulamaları yapılandırabilirsiniz](/intune-classic/deploy-use/monitor-apps-in-microsoft-intune).

>[!div class="step-by-step"]

>[&larr; **Kullanıcıları ve cihazları düzenleme**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**Şirket Portalı’nı özelleştirme** &rarr;](/intune/company-portal-customize)  
