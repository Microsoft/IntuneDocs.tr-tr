---
title: Microsoft Intune için uygulama yaşam döngüsüne genel bakış
description: Microsoft Intune'da yönetilen uygulamaların yaşam döngüsü hakkında bilgi edinin. Uygulama yaşam döngüsü uygulamaların dağıtımı, yapılandırması, korunması ve kullanım dışı bırakılmasını içerir.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: apps; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 53425b56985cbafb4033b11df54597959c0b0d59
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72499713"
---
# <a name="overview-of-the-app-lifecycle-in-microsoft-intune"></a>Microsoft Intune'da uygulama yaşam döngüsüne genel bakış

[!INCLUDE [both-portals](../../intune-classic/includes/note-for-both-portals.md)]

Microsoft Intune uygulama yaşam döngüsü, bir uygulama eklendiğinde başlar, ek aşamalardan geçerek siz uygulamayı kaldırana kadar devam eder. Bu aşamaları inceleyerek, Intune 'da uygulama yönetimi ile çalışmaya başlamak için ihtiyacınız olan ayrıntılara sahip olacaksınız.

![Uygulama yaşam döngüsü-ekleme, dağıtma, yapılandırma, koruma ve devre dışı bırakma.](./media/app-lifecycle/app-lifecycle.png "Intune uygulama yaşam döngüsü")

## <a name="add"></a>Ekleme

Uygulama dağıtımında ilk adım, yönetmek ve atamak istediğiniz uygulamayı Intune’a eklemektir. Birçok farklı uygulama türüyle çalışabilecek olmanıza karşın, temel yordamlar aynıdır. Intune ile, şirket içinde yazılmış uygulamalar (iş kolu), mağazadan uygulamalar, yerleşik uygulamalar ve Web üzerinde uygulamalar dahil farklı uygulama türleri ekleyebilirsiniz. Bu uygulama türlerinden her biri hakkında daha fazla bilgi için bkz. [Microsoft Intune’a uygulama ekleme](apps-add.md). 

## <a name="deploy"></a>Dağıt

Uygulamayı Intune’a ekledikten sonra, [yönettiğiniz kullanıcılara ve cihazlara atayabilirsiniz](apps-deploy.md). Intune bu işlemi kolaylaştırır ve uygulama dağıtıldıktan sonra, Azure portal içinde Intune 'dan dağıtım [başarısını izleyebilirsiniz](apps-monitor.md) . Buna ek olarak, [Apple](vpp-apps-ios.md) ve [Windows](windows-store-for-business.md) uygulama mağazaları gibi bazı uygulama mağazalarında şirketinize toplu uygulama lisansları satın alabilirsiniz. Bu tür uygulamalarda doğrudan Intune yönetim konsolundan lisans dağıtımı yapabilmeniz ve lisans kullanımını izleyebilmeniz için Intune verileri bu mağazalarla eşitleyebilir.

## <a name="configure"></a>Yapılandırma

Uygulama yaşam döngüsü kapsamında, uygulamaların yeni sürümleri düzenli olarak kullanıma sunulur. Intune, dağıtmış olduğunuz uygulamaları kolayca yeni sürüme [güncelleştirmeniz](apps-add.md) için araçlar sağlar. Buna ek olarak, bazı uygulamalar için fazladan işlevsellik yapılandırabilirsiniz; örneğin:
- [iOS uygulama yapılandırma ilkeleri](app-configuration-policies-use-ios.md), uyumlu iOS uygulamaları için uygulama çalıştırıldığında kullanılan ayarlar sağlar. Örneğin, uygulama için belirli marka ayarları veya bağlanması gereken sunucunun adı gerekiyor olabilir.
- [Yönetilen tarayıcı ilkeleri](app-configuration-managed-browser.md), varsayılan cihaz tarayıcısının yerini alan ve kullanıcılarınızın ziyaret edebileceği web sitelerini kısıtlayan Intune yönetilen tarayıcısı için ayarları yapılandırmanıza yardımcı olur.

## <a name="protect"></a>Koruma

Intune, uygulamalarınızdaki verileri korumaya yardımcı olmanın yollarını sağlar. Ana yöntemler şunlardır:
- Belirttiğiniz koşullara bağlı olarak e-posta ve diğer hizmetlere erişimi denetleyen [koşullu erişim](../protect/conditional-access.md). Bu koşullara cihaz türleri veya dağıttığınız bir [cihaz uyumluluk ilkesi](../protect/device-compliance-get-started.md) ile uyumluluk dahildir.
- [Uygulama koruma ilkeleri](app-protection-policy.md), tek tek uygulamalarla çalışarak bunların kullandığı şirket verilerinin korunmasına yardımcı olur. Örneğin, yönetilmeyen uygulamalarla sizin yönettiğiniz uygulamalar arasında veri kopyalamayı kısıtlayabilir ya da uygulamaların yazılım kilidi kırılmış veya kök erişimine izin verilmiş cihazlarda çalıştırılmasını önleyebilirsiniz.

## <a name="retire"></a>Devre dışı bırakma

Sonunda, büyük olasılıkla dağıttığınız uygulamalar eskir ve kaldırılmaları gerekir. Intune, [uygulamaları hizmette devre dışı bırakmayı](../remote-actions/device-management.md) kolaylaştırır.

## <a name="next-steps"></a>Sonraki adımlar

- [Microsoft Intune'da uygulama yönetimini](app-management.md) öğrenin
