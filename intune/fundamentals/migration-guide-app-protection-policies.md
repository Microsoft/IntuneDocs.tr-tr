---
title: Geçiş sırasında uygulama koruma ilkelerini yapılandırma
titleSuffix: Microsoft Intune
description: Bu makalede, bir Microsoft Intune geçişi sırasında uygulama koruma ilkeleri ayarlamak için gerekli adımlar sağlanmaktadır.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/09/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 183a1dc7083aa9b427df225297fb7c393939220f
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77515059"
---
# <a name="configure-app-protection-policies-optional"></a>Uygulama koruma ilkelerini yapılandırma (isteğe bağlı)


Uygulama koruma ilkeleri ile şunları yapabilirsiniz:
* Uygulamaları şifreleme
* Uygulamaya erişildiğinde kullanılacak bir PIN tanımlama
* Uygulamaların jail-break uygulanmış veya kökü belirtilmiş cihazlarda çalışmasını engelleme ve daha pek çok koruma işlemi.

Kullanıcının telefonu kayıpsa veya çalındıysa kişisel bilgilere dokunmadan yalnızca kurumsal verileri seçmeli olarak uzaktan silebilirsiniz.

Uygulama koruma ilkeleri uygulama düzeyinde güvenlik uygular ve cihaz kaydı gerektirmez. Bunları, Intune’a kayıtlı olan veya olmayan cihazlarla kullanabilirsiniz. Ayrıca, bir üçüncü taraf MDM sağlayıcısına kayıtlı cihazlara da uygulayabilirsiniz.

## <a name="app-protection-policies-with-lob-apps"></a>İş kolu uygulamaları ile uygulama koruma ilkeleri

Ayrıca, hem iOS/ıpados hem de Android platformları için [Microsoft Intune uygulama SDK 'sını](../developer/app-sdk-get-started.md) Microsoft Intune veya uygulama sarmalama aracı 'nı kullanarak mobil uygulama koruma ilkelerini iş kolu (LOB) uygulamalarınıza genişletebilirsiniz. Daha fazla bilgi için bkz. [iOS için Uygulama Sarmalama Aracı](../developer/app-wrapper-prepare-ios.md) ve [Android için Uygulama Sarmalama Aracı](./../developer/app-wrapper-prepare-android.md). Ayrıca bkz. [Uygulama koruması için LOB uygulamalarını hazırlama](../developer/apps-prepare-mobile-application-management.md).

## <a name="how-do-app-protection-policies-help-during-migration"></a>Uygulama koruma ilkeleri geçiş sırasında nasıl yardımcı olur?

Geçiş işleminde, cihazları eski MDM sağlayıcısından kaldırıp Intune’a kaydetmeniz gerektirir. Bunun için planlama yapmanız ve son kullanıcılarınızı eski MDM sağlayıcılarını bırakıp hemen Intune'a kaydolmaya teşvik etmeniz gerekir. Ancak, geçiş sırasında kayıt işlemini geciktiren kullanıcılar olabilir ve cihazları hiçbir MDM sağlayıcısı tarafından yönetilmiyor olabilir.

Bu dönem, şirket kaynaklarına erişime hala izin veriliyorsa kuruluşunuzu cihaz hırsızlığına ve şirket verilerinin kaybedilmesine karşı daha savunmasız hale getirebilir. Ayrıca şirket kaynaklarına erişim engellenirse kullanıcı verimliliğinin kaybıyla karşı karşıya da bırakabilir.

Intune geçiş sırasında şirket verileri için koruma sunar, böylece cihaz düzeyinde yönetim yokken şirket verileriniz için güvenliğe sahip olursunuz.

Eski MDM sağlayıcısında koşullu erişimi devre dışı bıraktığınızda, kullanıcılar bunları Intune 'a oluştururken üretken olmaya devam edebilir.

## <a name="task-list-for-app-protection-policies"></a>Uygulama koruma ilkeleri için görev listesi

- [Uygulama koruma ilkeleri oluşturma ve atama](~/apps/app-protection-policies.md)

## <a name="next-steps"></a>Sonraki adımlar

[Geçiş konusunda dikkat edilmesi gereken önemli noktalar](migration-guide-considerations.md)
