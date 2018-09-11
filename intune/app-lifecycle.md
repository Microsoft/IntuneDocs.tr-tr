---
title: Microsoft Intune için uygulama yaşam döngüsüne genel bakış
description: Microsoft Intune'da yönetilen uygulamaların yaşam döngüsü hakkında bilgi edinin. Uygulama yaşam döngüsü uygulamaların dağıtımı, yapılandırması, korunması ve kullanım dışı bırakılmasını içerir.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/06/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6
ms.reviewer: mghadial
ms.suite: ems
ms.custom: apps; get-started
ms.openlocfilehash: ad9eea41d0d40eed9aee07bcf5a77118c0efdab8
ms.sourcegitcommit: 18f51ae8291b57562921e40fc364a5a60a59b139
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2018
ms.locfileid: "44253763"
---
# <a name="overview-of-the-app-lifecycle-in-microsoft-intune"></a>Microsoft Intune'da uygulama yaşam döngüsüne genel bakış

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Microsoft Intune uygulama yaşam döngüsü, bir uygulama eklendiğinde başlar, ek aşamalardan geçerek siz uygulamayı kaldırana kadar devam eder. Bu aşamaları anladığınızda, Intune'da uygulama yönetimine başlamak için ihtiyacınız olan ayrıntıları elde etmiş olursunuz.

![Uygulama yaşam döngüsü](./media/app-lifecycle.png "Intune uygulama yaşam döngüsü")

## <a name="add"></a>Ekle

Uygulama dağıtımında ilk adım, yönetmek ve atamak istediğiniz uygulamayı Intune’a eklemektir. Birçok farklı uygulama türüyle çalışabilecek olmanıza karşın, temel yordamlar aynıdır. Intune ile, şirket içinde yazılmış uygulamalar (iş kolu uygulamaları), mağazadan alınan uygulamalar, yerleşik uygulamalar ve web'deki uygulamalar gibi farklı uygulama türlerini ekleyebilirsiniz. Bu uygulama türlerinden her biri hakkında daha fazla bilgi için bkz. [Microsoft Intune’a uygulama ekleme](apps-add.md). 

## <a name="deploy"></a>Dağıt

Uygulamayı Intune’a ekledikten sonra, [yönettiğiniz kullanıcılara ve cihazlara atayabilirsiniz](apps-deploy.md). Intune bu işlemi kolaylaştırır ve uygulama dağıtıldıktan sonra Azure portalı içinde Intune'dan dağıtımın [başarısını izleyebilirsiniz](apps-monitor.md). Buna ek olarak, [Apple](vpp-apps-ios.md) ve [Windows](windows-store-for-business.md) uygulama mağazaları gibi bazı uygulama mağazalarında şirketinize toplu uygulama lisansları satın alabilirsiniz. Bu tür uygulamalarda doğrudan Intune yönetim konsolundan lisans dağıtımı yapabilmeniz ve lisans kullanımını izleyebilmeniz için Intune verileri bu mağazalarla eşitleyebilir.

## <a name="configure"></a>Yapılandırma

Uygulama yaşam döngüsü kapsamında, uygulamaların yeni sürümleri düzenli olarak kullanıma sunulur. Intune, dağıtmış olduğunuz uygulamaları kolayca yeni sürüme [güncelleştirmeniz](apps-add.md) için araçlar sağlar. Buna ek olarak, bazı uygulamalar için fazladan işlevsellik yapılandırabilirsiniz; örneğin:
- [iOS uygulama yapılandırma ilkeleri](app-configuration-policies-use-ios.md), uyumlu iOS uygulamaları için uygulama çalıştırıldığında kullanılan ayarlar sağlar. Örneğin, uygulama için belirli marka ayarları veya bağlanması gereken sunucunun adı gerekiyor olabilir.
- [Yönetilen tarayıcı ilkeleri](app-configuration-managed-browser.md), varsayılan cihaz tarayıcısının yerini alan ve kullanıcılarınızın ziyaret edebileceği web sitelerini kısıtlayan Intune yönetilen tarayıcısı için ayarları yapılandırmanıza yardımcı olur.

## <a name="protect"></a>Koruma

Intune, uygulamalarınızdaki verileri korumaya yardımcı olmanın yollarını sağlar. Ana yöntemler şunlardır:
- Belirttiğiniz koşullara bağlı olarak e-postaya ve diğer hizmetlere erişimi denetleyen [koşullu erişim](conditional-access.md). Bu koşullara cihaz türleri veya dağıttığınız bir [cihaz uyumluluk ilkesi](device-compliance.md) ile uyumluluk dahildir.
- [Uygulama koruma ilkeleri](app-protection-policy.md), tek tek uygulamalarla çalışarak bunların kullandığı şirket verilerinin korunmasına yardımcı olur. Örneğin, yönetilmeyen uygulamalarla sizin yönettiğiniz uygulamalar arasında veri kopyalamayı kısıtlayabilir ya da uygulamaların yazılım kilidi kırılmış veya kök erişimine izin verilmiş cihazlarda çalıştırılmasını önleyebilirsiniz.

## <a name="retire"></a>Devre dışı bırakma

Sonunda, büyük olasılıkla dağıttığınız uygulamalar eskir ve kaldırılmaları gerekir. Intune, [uygulamaları hizmette devre dışı bırakmayı](device-management.md) kolaylaştırır.

## <a name="next-steps"></a>Sonraki adımlar:

- [Microsoft Intune'da uygulama yönetimini](app-management.md) öğrenin