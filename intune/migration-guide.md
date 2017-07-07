---
title: "Intune mobil cihaz yönetimi geçiş kılavuzu"
description: "Bu kılavuzun amacı, müşterilerin bir üçüncü taraf MDM sağlayıcısından Microsoft Intune’a geçişi ile ilgili çeşitli ayrıntılar hakkında bilgilendirilmesini sağlamaktır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9e86f342413a0f31c51d7a56f862986c433309eb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="intune-migration-guide"></a>Intune geçiş kılavuzu

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

![Intune MDM geçiş kılavuzu görseli](./media/MDM-migration-guide-art.PNG)

Intune'a başarılı bir geçiş; geçerli mobil cihaz yönetimi (MDM) ortamını, iş hedeflerini ve teknik gereksinimleri dikkate alan sağlam bir plan ile başlar. Ayrıca, geçiş planınızı destekleyecek ve sizinle işbirliği yapacak önemli paydaşlara sahip olmanız gerekir.

Bu kılavuzun amacı, bir üçüncü taraf MDM sağlayıcısından Intune’a geçiş ile ilgili çeşitli ayrıntılar hakkında bilgiler sağlamaktır.

## <a name="whats-included-in-this-guide"></a>Kılavuza neler dahildir?

Bu kılavuz iki aşamadan oluşur ve bunlar Intune MDM’e geçiş için baştan sona adımlar sağlayarak yardımcı olan görevler, stratejiler ve taktiksel kılavuz içerir.

-   [1. Aşama: Intune'u Mobil cihaz yönetimi için hazırlama] (migration-guide-prepare.md)

    -   [MDM geçiş gereksinimlerinizi değerlendirme](migration-guide-prepare.md#assess-mdm-requirements)

    -   [Temel kurulum](migration-guide-setup.md)

    -   [Mobil cihaz ve uygulama yönetimi ilkelerini yapılandırma](migration-guide-configure-policies.md)

    -   [Uygulama koruma ilkelerini yapılandırma] (migration-guide-app-protection-policies.md)

    -   [Geçiş konusunda dikkat edilmesi gereken önemli noktalar](migration-guide-considerations.md)

-   [2. Aşama: Geçiş kampanyası](migration-guide-campaign.md)

    -   [İletişim Planı](migration-guide-communication-plan.md)

    -   [Koşullu erişimle son kullanıcı benimsemesi sağlama](migration-guide-drive-adoption.md)
    
    -   [Tipik Geçiş Döngüsü](migration-guide-cycle.md)
        -   [Geçiş izleme](migration-guide-cycle.md#monitoring-migration)
        -   [Geçiş sonrası](migration-guide-cycle.md#post-migration)

## <a name="assumptions"></a>Varsayımlar

-   Intune’u zaten bir kavram kanıtı (PoC) ortamında değerlendirdiniz ve kuruluşunuzda MDM çözümü olarak kullanmaya karar verdiniz.

-   Intune ve özellikleri konusunda zaten bilgi sahibisiniz. 

> [!NOTE]
> Geçiş yapmadan önce Intune hakkında daha fazla bilgi edinmek için bkz. [Intune değerlendirme kılavuzu](/intune-classic/understand-explore/sign-up-for-30-day-trial-microsoft-intune).

## <a name="before-you-begin"></a>Başlamadan önce

Yeni Intune dağıtımınızın eski MDM dağıtımınızdan farklı olabileceğini bilmek önemlidir. Geleneksel MDM hizmetlerinden farklı olarak Intune, kimlik tabanlı erişim denetimi odaklıdır ve bu nedenle kuruluşun ağ çevresi dışında mobil cihazlardan şirket verilerine erişimi denetlemek için bir ağ ara sunucusu gereci gerektirmez. Microsoft, birlikte Enterprise Client + Security teklifi olarak anılan, sıkıca tümleşik bulut hizmetleri paketi aracılığıyla veri hizmetlerinin bulut içinde güvenliğini sağlamak için çözümler sunar.

-   [Intune kullanmanın yaygın yollarını](migration-guide-prepare.md#assess-mdm-requirements) gözden geçirin.

## <a name="next-steps"></a>Sonraki adımlar

[1. Aşama: Intune'u mobil cihaz yönetimi için hazırlama] (migration-guide-prepare.md)
