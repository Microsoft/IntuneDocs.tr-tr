---
title: Geçiş sırasında uygulama koruma ilkelerini yapılandırma
titleSuffix: Microsoft Intune
description: Bu makalede, Microsoft Intune geçişi sırasında uygulama koruma ilkeleri ayarlamak için gerekli adımlar sağlanmaktadır.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 49246302cf71fc95d20cdb84099323ba9beffdb3
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940480"
---
# <a name="configure-app-protection-policies-optional"></a>Uygulama koruma ilkelerini yapılandırma (isteğe bağlı)


Uygulama koruma ilkeleri şunları yapmanıza olanak sağlar:
* Uygulamaları şifreleme
* Uygulamaya erişildiğinde bir PIN tanımlayın
* Uygulamaların, caıl kopuk veya kökü belirtilmiş cihazlarda çalışmasını engelleyin ve diğer birçok koruma.

Kullanıcının telefonu kaybolur veya çalınırsa, kişisel verileri bozulmadan bırakarak şirket verilerini uzaktan seçerek temizleyebilirsiniz.

Uygulama koruma ilkeleri, uygulama düzeyinde güvenlik uygular ve cihaz kaydı gerektirmez. Bunları, Intune 'a kayıtlı olan cihazlarla kullanabilirsiniz. Ayrıca, bir üçüncü taraf MDM sağlayıcısına kayıtlı cihazlara de uygulayabilirsiniz.

## <a name="app-protection-policies-with-lob-apps"></a>LOB uygulamaları ile uygulama koruma ilkeleri

Ayrıca, hem iOS hem de Android platformları için [Microsoft Intune uygulama SDK 'sını](../developer/app-sdk-get-started.md) Microsoft Intune veya uygulama sarmalama aracı 'nı kullanarak mobil uygulama koruma ilkelerini iş kolu (LOB) uygulamalarınıza genişletebilirsiniz. Daha fazla bilgi için bkz. [iOS Için uygulama sarmalama aracı](../developer/app-wrapper-prepare-ios.md) ve [Android Için uygulama sarmalama aracı](./../developer/app-wrapper-prepare-android.md). Ayrıca bkz. [uygulama koruması IÇIN LOB uygulamalarını hazırlama](../developer/apps-prepare-mobile-application-management.md).

## <a name="how-do-app-protection-policies-help-during-migration"></a>Uygulama koruma ilkeleri geçiş sırasında nasıl yardımcı olur?

Bir geçişte, cihazları eski MDM sağlayıcısından kaldırmalı ve bunları Intune 'a kaydetmeniz gerekir. Bunu planlamanız ve son kullanıcılarınızın eski MDM sağlayıcısını bırakıp hemen Intune 'a kaydolmasını öneririz. Bununla birlikte, geçiş sırasında kayıt işlemini tamamlamak ve cihazları MDM sağlayıcısı tarafından yönetilmediği kullanıcılar olabilir.

Bu süre, kurumsal kaynak erişimine hala izin veriliyorsa, kuruluşunuzda cihaz hırsızlığı ve şirket veri kaybı için daha savunmasız kalabilir. Ayrıca kurumsal kaynak erişimi engellenmişse Kullanıcı üretkenliğini azaltmaya da yol açabilir.

Intune, geçiş sırasında kurumsal veri korumaları sunabilir, böylece cihaz düzeyinde yönetim olmadığında kurumsal verilerinize yönelik güvenlik kapsamına sahip olabilirsiniz.

Eski MDM sağlayıcısında koşullu erişimi devre dışı bıraktığınızda, kullanıcılar bunları Intune 'a oluştururken üretken olmaya devam edebilir.

## <a name="task-list-for-app-protection-policies"></a>Uygulama koruma ilkeleri için görev listesi

1. [Uygulama koruma ilkesi oluşturma](../apps/app-protection-policies.md#create-an-app-protection-policy)
2. [İlke dağıtma](../apps/app-protection-policies.md#deploy-a-policy-to-users)


## <a name="next-steps"></a>Sonraki adımlar

[Özel geçiş konuları](migration-guide-considerations.md)
