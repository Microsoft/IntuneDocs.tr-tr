---
title: "Uygulama koruma ilkelerini bir Intune geçişi sırasında yapılandırma | Microsoft Docs"
description: "Bu makalenin amacı, bir Intune geçişi sırasında uygulama koruma ilkeleri ayarlamak için gerekli adımları sağlamaktır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: 35543604ed68393e859517e32f5186247be001df
ms.lasthandoff: 03/27/2017


---

# <a name="phase-1-configure-app-protection-policies-optional"></a>1. Aşama: Uygulama koruma ilkelerini yapılandırma (isteğe bağlı)

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Uygulama koruma ilkeleri uygulamaları şifrelemenize, uygulamaya erişildiğinde bir PIN tanımlamanıza, uygulamaların jailbreak uygulanmış veya kök erişim izni verilmiş cihazlarda çalışmasını engellemenize ve diğer birçok koruma uygulamanıza olanak sağlar. Kullanıcının telefonu kaybolur veya çalınırsa, mobil uygulama koruma ilkeleri uygulayarak şirket verilerini uzaktan seçmeli olarak silip, kişisel verileri olduğu gibi bırakabilirsiniz.

Uygulama koruma ilkeleri uygulama düzeyinde güvenlik uygular ve cihaz kaydı gerektirmez. Intune'a kayıtlı olan veya olmayan cihazlarla kullanılabilir. Ayrıca, bir üçüncü taraf MDM sağlayıcısına kayıtlı cihazlar ile kullanılabilir.

## <a name="app-protection-policies-with-lob-apps"></a>İş kolu uygulamaları ile uygulama koruma ilkeleri

[Microsoft Intune App SDK](https://docs.microsoft.com/intune/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management) veya Microsoft Intune Uygulama Sarmalama Aracını hem [iOS](https://www.microsoft.com/en-us/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True) hem de [Android](https://www.microsoft.com/en-us/download/details.aspx?id=47267) platformları için kullanarak mobil uygulama koruma ilkelerini iş kolu (LOB) uygulamalarınıza genişletebilirsiniz.

## <a name="how-do-app-protection-policies-help-during-migration"></a>Uygulama koruma ilkeleri geçiş sırasında nasıl yardımcı olur?

Geçiş işlemi, cihazları eski MDM sağlayıcısından kaldırıp Intune'a kaydetmeyi gerektirir. Bunun için planlama yapmanız ve son kullanıcılarınızı eski MDM sağlayıcılarını bırakıp hemen Intune'a kaydolmaya teşvik etmeniz gerekir. Ancak, geçiş sırasında kayıt işlemini geciktiren kullanıcılar olabilir ve cihazları hiçbir MDM sağlayıcısı tarafından yönetilmiyor olabilir.

Bu dönem, şirket kaynaklarına erişime hala izin veriliyorsa kuruluşunuzu cihaz hırsızlığına ve şirket verilerinin kaybedilmesine karşı daha savunmasız hale getirebilir ve/veya şirket kaynaklarına erişim engellenirse kullanıcı verimliliğinin kaybıyla karşı karşıya bırakabilir.

Intune geçiş sırasında şirket verileri için koruma sunar, böylece cihaz düzeyinde yönetim yokken şirket verileriniz için güvenliğe sahip olursunuz.

Eski MDM sağlayıcısındaki koşullu erişimi devre dışı bıraktığınızda kullanıcılar, onları Intune’a eklediğiniz sırada verimli olmaya devam edebilir.

## <a name="task-list-for-app-protection-policies"></a>Uygulama koruma ilkeleri için görev listesi

-   1. Görev: [Mobil uygulama koruma ilkelerini yapılandırmaya hazırlanmayı](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) öğrenin

-   2. Görev: [Mobil uygulama koruma ilkelerini oluşturmayı ve dağıtmayı](https://docs.microsoft.com/en-us/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) öğrenin

## <a name="next-steps"></a>Sonraki adımlar 

[1. Aşama: Geçiş konusunda dikkat edilmesi gereken önemli noktalar](https://docs.microsoft.com/intune/plan-design/migration-phase1-special-migration-considerations)

