---
title: "Uygulama yaşam döngüsüne genel bakış"
description: "Intune yönetilen uygulamalarının, eklenmesinden başlayıp sonunda devre dışı bırakılmasına kadar tüm yaşam döngüsü hakkında bilgi edinin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cf505bec8a07923db78a870e4d7bfd64660e681c
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="overview-of-the-app-lifecycle"></a>Uygulama yaşam döngüsüne genel bakış

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Intune uygulama yaşam döngüsü, bir uygulama eklendiğinde başlar, ek aşamalardan geçerek siz uygulamayı kaldırana kadar devam eder.

![Uygulama yaşam döngüsü](./media/app-lifecycle.png "Intune uygulama yaşam döngüsü")

## <a name="add"></a>Ekle

Uygulama dağıtımında ilk adım, yönetmek ve atamak istediğiniz uygulamayı Intune’a eklemektir. Birçok farklı uygulama türüyle çalışabilecek olmanıza karşın, temel yordamlar aynıdır. Intune ile hem [kayıtlı cihazlar](apps-add.md) ([Klasik portal](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)) için, hem de [Intune istemci yazılımıyla yönettiğiniz Windows bilgisayarları](/intune-classic/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune) için uygulama ekleyebilirsiniz.

## <a name="deploy"></a>Dağıtma

Uygulamayı Intune’a ekledikten sonra, [yönettiğiniz kullanıcılara ve cihazlara dağıtabilirsiniz](apps-deploy.md) ([Klasik portal](/intune-classic/deploy-use/deploy-apps)). Intune bu işlemi kolaylaştırır ve uygulama dağıtıldıktan sonra Intune yönetim konsolundan dağıtımın [başarısını izleyebilirsiniz](apps-monitor.md) ([Klasik portal](/intune-classic/deploy-use/monitor-apps-in-microsoft-intune)). Buna ek olarak, [Apple](vpp-apps-ios.md) ve ([Klasik portal](/intune-classic/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)) ve [Windows](windows-store-for-business.md) ([Klasik portal](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)) uygulama mağazaları gibi bazı uygulama mağazalarında şirketinize toplu uygulama lisansları satın alabilirsiniz. Bu tür uygulamalarda doğrudan Intune yönetim konsolundan lisans dağıtımı yapabilmeniz ve lisans kullanımını izleyebilmeniz için Intune verileri bu mağazalarla eşitleyebilir.

## <a name="configure"></a>Yapılandırma

Uygulama yaşam döngüsü kapsamında, uygulamaların yeni sürümleri düzenli olarak kullanıma sunulur. Intune, dağıtmış olduğunuz uygulamaları kolayca yeni sürüme [güncelleştirmeniz](apps-add.md) ([Klasik portal](/intune-classic/deploy-use/update-apps-using-microsoft-intune)) için araçlar sağlar. Buna ek olarak, bazı uygulamalar için fazladan işlevsellik yapılandırabilirsiniz; örneğin:
- [iOS uygulama yapılandırma ilkeleri](app-configuration-policies-use-ios.md) ([Klasik portal](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)), uyumlu iOS uygulamaları için uygulama çalıştırıldığında kullanılan ayarlar sağlar. Örneğin, uygulama için belirli marka ayarları veya bağlantı kurulacak sunucunun adı gerekiyor olabilir.
- [Managed Browser ilkeleri](app-configuration-managed-browser.md) ([Klasik portal](/intune-classic/deploy-use/manage-internet-access-using-managed-browser-policies)), varsayılan cihaz tarayıcısının yerini alan ve kullanıcılarınızın ziyaret edebileceği web sitelerini kısıtlayan Intune Managed Browser için ayarları yapılandırmanıza yardımcı olur.

## <a name="protect"></a>Koruma

Intune, uygulamalarınızdaki verileri korumaya yardımcı olmanın yollarını sağlar. Ana yöntemler şunlardır:
- [Koşullu erişim](conditional-access.md) ([Klasik portal](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)), belirttiğiniz koşullara bağlı olarak e-posta e diğer hizmetlere erişimi denetler. Bu koşullara cihaz türleri veya dağıttığınız bir [cihaz uyumluluk ilkesi](device-compliance.md) ([Klasik portal](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)) ile uyumluluk dahildir.
- [Uygulama koruma ilkeleri](app-protection-policy.md) ([Klasik portal](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)), tek tek uygulamalarla çalışarak bunların kullandığı şirket verilerinin korunmasına yardımcı olur. Örneğin, yönetilmeyen uygulamalarla sizin yönettiğiniz uygulamalar arasında veri kopyalamayı kısıtlayabilir ya da uygulamaların yazılım kilidi kırılmış veya kök erişimine izin verilmiş cihazlarda çalıştırılmasını önleyebilirsiniz.

## <a name="retire"></a>Devre dışı bırakma

Sonunda, büyük olasılıkla dağıttığınız uygulamalar eskir ve kaldırılmaları gerekir. Intune, [uygulamaları hizmette devre dışı bırakmayı](device-management.md) ([Klasik portal](/intune-classic/deploy-use/retire-apps-using-microsoft-intune)) kolaylaştırır.
