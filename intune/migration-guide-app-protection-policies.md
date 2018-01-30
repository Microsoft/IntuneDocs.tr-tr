---
title: "Intune geçişi sırasında uygulama koruma ilkelerini yapılandırma"
description: "Bu makalede, bir Intune geçişi sırasında uygulama koruma ilkeleri ayarlamak için gerekli adımlar sağlanmaktadır."
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: d3c176b84a8555de245a1f4014c39885e50ab21d
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="configure-app-protection-policies-optional"></a>Uygulama koruma ilkelerini yapılandırma (isteğe bağlı)


Uygulama koruma ilkeleri ile şunları yapabilirsiniz:
* Uygulamaları şifreleme
* Uygulamaya erişildiğinde kullanılacak bir PIN tanımlama
* Uygulamaların jail-break uygulanmış veya kökü belirtilmiş cihazlarda çalışmasını engelleme ve daha pek çok koruma işlemi.

Kullanıcının telefonu kayıpsa veya çalındıysa kişisel bilgilere dokunmadan yalnızca kurumsal verileri seçmeli olarak uzaktan silebilirsiniz.

Uygulama koruma ilkeleri uygulama düzeyinde güvenlik uygular ve cihaz kaydı gerektirmez. Bunları, Intune’a kayıtlı olan veya olmayan cihazlarla kullanabilirsiniz. Ayrıca, bir üçüncü taraf MDM sağlayıcısına kayıtlı cihazlara da uygulayabilirsiniz.

## <a name="app-protection-policies-with-lob-apps"></a>İş kolu uygulamaları ile uygulama koruma ilkeleri

[Microsoft Intune App SDK](app-sdk-get-started.md) veya Microsoft Intune Uygulama Sarmalama Aracını hem [iOS](https://www.microsoft.com/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True) hem de [Android](https://www.microsoft.com/download/details.aspx?id=47267) platformları için kullanarak mobil uygulama koruma ilkelerini iş kolu (LOB) uygulamalarınıza genişletebilirsiniz.

## <a name="how-do-app-protection-policies-help-during-migration"></a>Uygulama koruma ilkeleri geçiş sırasında nasıl yardımcı olur?

Geçiş işleminde, cihazları eski MDM sağlayıcısından kaldırıp Intune’a kaydetmeniz gerektirir. Bunun için planlama yapmanız ve son kullanıcılarınızı eski MDM sağlayıcılarını bırakıp hemen Intune'a kaydolmaya teşvik etmeniz gerekir. Ancak, geçiş sırasında kayıt işlemini geciktiren kullanıcılar olabilir ve cihazları hiçbir MDM sağlayıcısı tarafından yönetilmiyor olabilir.

Bu dönem, şirket kaynaklarına erişime hala izin veriliyorsa kuruluşunuzu cihaz hırsızlığına ve şirket verilerinin kaybedilmesine karşı daha savunmasız hale getirebilir. Ayrıca şirket kaynaklarına erişim engellenirse kullanıcı verimliliğinin kaybıyla karşı karşıya da bırakabilir.

Intune geçiş sırasında şirket verileri için koruma sunar, böylece cihaz düzeyinde yönetim yokken şirket verileriniz için güvenliğe sahip olursunuz.

Eski MDM sağlayıcısındaki koşullu erişimi devre dışı bıraktığınızda kullanıcılar, onları Intune’a eklediğiniz sırada verimli olmaya devam edebilir.

## <a name="task-list-for-app-protection-policies"></a>Uygulama koruma ilkeleri için görev listesi

1. [Uygulama koruma ilkesi oluşturma](app-protection-policies.md#create-an-app-protection-policy)
2. [İlke dağıtma](app-protection-policies.md#deploy-a-policy-to-users)


## <a name="next-steps"></a>Sonraki adımlar

[Geçiş konusunda dikkat edilmesi gereken önemli noktalar](migration-guide-considerations.md)
