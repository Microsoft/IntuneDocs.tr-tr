---
title: Intune mobil cihaz yönetimi geçiş kılavuzu
titlesuffix: Microsoft Intune
description: Bu kılavuz, bir üçüncü taraf MDM sağlayıcısından Microsoft Intune’a geçiş ile ilgili çeşitli ayrıntılar hakkında bilgi sağlar.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 9bfefff2ef5960b6e52a8a37c2fd31466d16cbff
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2018
---
# <a name="intune-migration-guide"></a>Intune geçiş kılavuzu

![Microsoft Intune MDM geçiş kılavuzu görseli](./media/MDM-migration-guide-art.PNG)

Microsoft Intune’a başarılı bir geçiş; geçerli mobil cihaz yönetimi (MDM) ortamınızı, iş hedeflerinizi ve teknik gereksinimlerinizi hesaba katan sağlam bir plan ile başlar. Ayrıca, geçiş planınızı destekleyecek ve sizinle işbirliği yapacak önemli proje katılımcılarının olması gerekir.

Bu kılavuz, bir üçüncü taraf MDM sağlayıcısından Intune’a geçiş ile ilgili çeşitli ayrıntılar hakkında bilgi sağlar.

## <a name="whats-included-in-this-guide"></a>Kılavuza neler dahildir?

Bu kılavuz, geçiş işlemini iki aşamaya ayırır. Bu adımlar, aşamalardan oluşan Intune MDM’ye geçiş işleminde size yardımcı olacak görevler, stratejiler ve taktiksel kılavuz içerir.

-   [1. Aşama: Intune’u mobil cihaz yönetimine hazırlama](migration-guide-prepare.md)

    -   [MDM geçiş gereksinimlerinizi değerlendirme](migration-guide-prepare.md#assess-mdm-requirements)

    -   [Temel kurulum](migration-guide-setup.md)

    -   [Mobil cihaz ve uygulama yönetimi ilkelerini yapılandırma](migration-guide-configure-policies.md)

    -   [Uygulama koruma ilkelerini yapılandırma](migration-guide-app-protection-policies.md)

    -   [Geçiş konusunda dikkat edilmesi gereken önemli noktalar](migration-guide-considerations.md)

-   [2. Aşama: Geçiş kampanyası](migration-guide-campaign.md)

    -   [İletişim planı](migration-guide-communication-plan.md)

    -   [Koşullu erişimle son kullanıcı benimsemesi sağlama](migration-guide-drive-adoption.md)

    -   [Normal geçiş süreci](migration-guide-cycle.md)
        -   [Geçiş izleme](migration-guide-cycle.md#monitoring-migration)
        -   [Geçiş sonrası](migration-guide-cycle.md#post-migration)

## <a name="assumptions"></a>Varsayımlar

-   Intune’u zaten bir kavram kanıtı (PoC) ortamında değerlendirdiniz ve kuruluşunuzda MDM çözümü olarak kullanmaya karar verdiniz.

-   Intune ve özellikleri konusunda zaten bilgi sahibisiniz.

## <a name="before-you-begin"></a>Başlamadan önce

Yeni Intune dağıtımınızın eski MDM dağıtımınızdan farklı olabileceğini bilmek önemlidir. Geleneksel MDM hizmetlerinden farklı olarak Intune, kimlik tabanlı erişim denetimi odaklıdır ve bu nedenle kuruluşun ağ çevresi dışında mobil cihazlardan şirket verilerine erişimi denetlemek için bir ağ ara sunucusu gereci gerektirmez. Microsoft, sıkıca tümleşik bulut hizmetleri paketi aracılığıyla, veri hizmetlerinin bulut içinde güvenliğini sağlayan çözümler sunar. Bu çözümlerin genel adı Enterprise Client + Security teklifidir.

-   [Intune kullanmanın yaygın yollarını](common-scenarios.md) gözden geçirin.

## <a name="next-steps"></a>Sonraki adımlar

[1. Aşama: Intune’u mobil cihaz yönetimine hazırlama](migration-guide-prepare.md)
