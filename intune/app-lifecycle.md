---
title: Microsoft Intune için uygulama yaşam döngüsüne genel bakış
description: Microsoft Intune'da yönetilen uygulamaların yaşam döngüsü hakkında bilgi edinin. Uygulama yaşam döngüsü uygulamaların dağıtımı, yapılandırması, korunması ve kullanım dışı bırakılmasını içerir.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/19/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: apps; get-started
ms.openlocfilehash: a23f5fb9e05cf9a7fe46456b642aef76b6a79b70
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52183120"
---
# <a name="overview-of-the-app-lifecycle-in-microsoft-intune"></a>Microsoft Intune'da uygulama yaşam döngüsüne genel bakış

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Microsoft Intune uygulama yaşam döngüsü, bir uygulama eklendiğinde başlar, ek aşamalardan geçerek siz uygulamayı kaldırana kadar devam eder. Bu aşamalar anlayarak, ıntune'da uygulama yönetimini kullanmaya başlamak için gereken Ayrıntılar sahip olacaksınız.

![Uygulama yaşam döngüsü](./media/app-lifecycle.png "Intune uygulama yaşam döngüsü")

## <a name="add"></a>Ekle

Uygulama dağıtımında ilk adım, yönetmek ve atamak istediğiniz uygulamayı Intune’a eklemektir. Birçok farklı uygulama türüyle çalışabilecek olmanıza karşın, temel yordamlar aynıdır. Intune ile şirket içinde yazılmış uygulamalar dahil olmak üzere farklı uygulama türlerini (satır iş kolu), uygulama mağazası, yerleşik olarak bulunan uygulama ve uygulamalar web üzerindeki ekleyebilirsiniz. Bu uygulama türlerinden her biri hakkında daha fazla bilgi için bkz. [Microsoft Intune’a uygulama ekleme](apps-add.md). 

## <a name="deploy"></a>Dağıt

Uygulamayı Intune’a ekledikten sonra, [yönettiğiniz kullanıcılara ve cihazlara atayabilirsiniz](apps-deploy.md). Intune bu işlemi kolaylaştırır ve uygulama dağıtıldıktan sonra [başarısını izleyebilirsiniz](apps-monitor.md) Azure portalı içinde ıntune'dan dağıtımın. Buna ek olarak, [Apple](vpp-apps-ios.md) ve [Windows](windows-store-for-business.md) uygulama mağazaları gibi bazı uygulama mağazalarında şirketinize toplu uygulama lisansları satın alabilirsiniz. Bu tür uygulamalarda doğrudan Intune yönetim konsolundan lisans dağıtımı yapabilmeniz ve lisans kullanımını izleyebilmeniz için Intune verileri bu mağazalarla eşitleyebilir.

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