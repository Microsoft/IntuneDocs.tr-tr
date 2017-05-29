---
title: "Uygulama yaşam döngüsüne genel bakış | Microsoft Docs"
description: "Intune yönetilen uygulamalarının, eklenmesinden başlayıp sonunda devre dışı bırakılmasına kadar tüm yaşam döngüsü hakkında bilgi edinin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 2c1b4876e92e64912f237560b346aedceb0771c5
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="overview-of-the-app-lifecycle"></a>Uygulama yaşam döngüsüne genel bakış

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune uygulama yaşam döngüsü, bir uygulama eklendiğinde başlar, ek aşamalardan geçerek siz uygulamayı kaldırana kadar devam eder.

![Uygulama yaşam döngüsü](./media/app-lifecycle.png "Intune uygulama yaşam döngüsü")

## <a name="add"></a>Ekle

Uygulama dağıtımında ilk adım, yönetmek ve dağıtmak istediğiniz uygulamayı Intune’a eklemektir. Birçok farklı uygulama türüyle çalışabilecek olmanıza karşın, temel yordamlar aynıdır. Intune ile hem [kayıtlı cihazlar](add-apps-for-mobile-devices-in-microsoft-intune.md) için, hem de [Intune istemci yazılımıyla yönettiğiniz Windows bilgisayarları](add-apps-for-windows-pcs-in-microsoft-intune.md) için uygulama ekleyebilirsiniz.

## <a name="deploy"></a>Dağıtma

Uygulamayı Intune’a ekledikten sonra [yönettiğiniz cihazlara dağıtabilirsiniz](deploy-apps.md). Intune bu işlemi kolaylaştırır ve uygulama dağıtıldıktan sonra Intune yönetim konsolundan dağıtımın [başarısını izleyebilirsiniz](monitor-apps-in-microsoft-intune.md). Buna ek olarak, [Apple](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md) ve [Windows](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md) uygulama mağazaları gibi bazı uygulama mağazalarında şirketinize toplu uygulama lisansları satın alabilirsiniz. Bu tür uygulamalarda doğrudan Intune yönetim konsolundan lisans dağıtımı yapabilmeniz ve lisans kullanımını izleyebilmeniz için Intune verileri bu mağazalarla eşitleyebilir.

## <a name="configure"></a>Yapılandırma

Uygulama yaşam döngüsü kapsamında, uygulamaların yeni sürümleri düzenli olarak kullanıma sunulur. Intune, dağıtmış olduğunuz uygulamaları kolayca yeni sürüme [güncelleştirmeniz](update-apps-using-microsoft-intune.md) için araçlar sağlar. Buna ek olarak, bazı uygulamalar için fazladan işlevsellik yapılandırabilirsiniz; örneğin:
- [iOS uygulama yapılandırma ilkeleri](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md), uyumlu iOS uygulamaları için uygulama çalıştırıldığında kullanılan ayarlar sağlar. Örneğin, uygulama için belirli marka ayarları veya bağlantı kurulacak sunucunun adı gerekiyor olabilir.
- [Yönetilen tarayıcı ilkeleri](manage-internet-access-using-managed-browser-policies.md), varsayılan cihaz tarayıcısının yerini alan ve kullanıcılarınızın ziyaret edebileceği web sitelerini kısıtlayan Intune yönetilen tarayıcısı için ayarları yapılandırmanıza yardımcı olur.

## <a name="protect"></a>Koruma

Intune, uygulamalarınızdaki verileri korumaya yardımcı olmanın yollarını sağlar. Ana yöntemler şunlardır:
- [Koşullu erişim](restrict-access-to-email-and-o365-services-with-microsoft-intune.md), belirttiğiniz koşullara bağlı olarak e-posta e diğer hizmetlere erişimi denetler. Bu koşullara cihaz türleri veya dağıttığınız bir [cihaz uyumluluk ilkesi](introduction-to-device-compliance-policies-in-microsoft-intune.md) ile uyumluluk dahildir.
- [Mobil uygulama yönetimi (MAM)](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md), tek tek uygulamalarla çalışarak bunların kullandığı şirket verilerinin korunmasına yardımcı olur. Örneğin, yönetilmeyen uygulamalarla sizin yönettiğiniz uygulamalar arasında veri kopyalamayı kısıtlayabilir ya da uygulamaların yazılım kilidi kırılmış veya kök erişimine izin verilmiş cihazlarda çalıştırılmasını önleyebilirsiniz.

## <a name="retire"></a>Devre dışı bırakma

Sonunda, büyük olasılıkla dağıttığınız uygulamalar eskir ve kaldırılmaları gerekir. Intune, [uygulamaları hizmette devre dışı bırakmayı](retire-apps-using-microsoft-intune.md) kolaylaştırır.

