---
title: "Intune mobil cihaz yönetimi (MDM) Geçiş Kılavuzu | Microsoft Docs"
description: "Bu kılavuzun amacı, müşterilerin bir üçüncü taraf MDM sağlayıcısından Microsoft Intune’a geçişi ile ilgili çeşitli ayrıntılar hakkında bilgilendirilmesini sağlamaktır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8da2695c4c6dc8b45559323b83a4bb77167303b7
ms.openlocfilehash: 444cb61ea57b92924a681c564a1a913f4204ea89
ms.lasthandoff: 03/28/2017


---

# <a name="intune-migration-guide"></a>Intune geçiş kılavuzu

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

![Intune MDM geçiş kılavuzu görseli](../media/MDM-migration-guide-art.PNG)

Intune’a başarılı bir geçiş; geçerli MDM ortamı, iş hedefleri ve teknik gereksinimleri dikkate alan sağlam bir plan ile başlar. Ayrıca, geçiş planınızı destekleyecek ve sizinle işbirliği yapacak önemli paydaşlara sahip olmanız gerekir.

Bu kılavuzun amacı, bir üçüncü taraf MDM sağlayıcısından Intune’a geçiş ile ilgili çeşitli ayrıntılar hakkında bilgiler sağlamaktır.

## <a name="whats-included-in-this-guide"></a>Kılavuza neler dahildir?

Bu kılavuz iki aşamadan oluşur ve bunlar Intune MDM’e geçiş için baştan sona adımlar sağlayarak yardımcı olan görevler, stratejiler ve taktiksel kılavuz içerir.

-   [1. Aşama: Intune’u Mobil cihaz yönetimi (MDM) için hazırlama](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management)

    -   [MDM geçiş gereksinimlerinizi değerlendirme](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements)

    -   [Temel kurulum](https://docs.microsoft.com/intune/plan-design/migration-phase1-basic-setup)

    -   [Cihaz ve uygulama yönetimi ilkelerini yapılandırma](https://docs.microsoft.com/intune/plan-design/migration-phase1-configure-device-and-app-management-policies)

    -   [Uygulama koruma ilkelerini yapılandırma (isteğe bağlı)](https://docs.microsoft.com/intune/plan-design/migration-phase1-configure-app-protection-policies)

    -   [Geçiş konusunda dikkat edilmesi gereken önemli noktalar](https://docs.microsoft.com/intune/plan-design/migration-phase1-special-migration-considerations)

-   [2. Aşama: Geçiş kampanyası](https://docs.microsoft.com/intune/plan-design/migration-phase2-migration-campaign)

    -   [İletişim Planı](https://docs.microsoft.com/intune/plan-design/migration-phase2-communication-plan)

    -   [Koşullu erişimle son kullanıcı benimsemesi sağlama](https://docs.microsoft.com/intune/plan-design/migration-phase2-drive-end-user-adoption-with-conditional-access)
    
    -   [Tipik Geçiş Döngüsü](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle)
        -   [Geçiş izleme](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle#monitoring-migration)
        -   [Geçiş sonrası](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle#post-migration)

## <a name="assumptions"></a>Varsayımlar

-   Intune’u zaten bir kavram kanıtı (PoC) ortamında değerlendirdiniz ve kuruluşunuzda MDM çözümü olarak kullanmaya karar verdiniz.

-   Intune ve özellikleri konusunda zaten bilgi sahibisiniz. 

> [!NOTE]
> Geçiş yapmadan önce Intune hakkında daha fazla bilgi edinmek için bkz. [Intune değerlendirme kılavuzu](https://docs.microsoft.com/intune/understand-explore/sign-up-for-30-day-trial-microsoft-intune).

## <a name="before-you-begin"></a>Başlamadan önce

Yeni Intune dağıtımınızın eski MDM dağıtımınızdan farklı olabileceğini bilmek önemlidir. Geleneksel MDM hizmetlerinden farklı olarak Intune, kimlik tabanlı erişim denetimi odaklıdır ve bu nedenle kuruluşun ağ çevresi dışında mobil cihazlardan şirket verilerine erişimi denetlemek için bir ağ ara sunucusu gereci gerektirmez. Microsoft, birlikte Enterprise Client + Security teklifi olarak anılan, sıkıca tümleşik bulut hizmetleri paketi aracılığıyla veri hizmetlerinin bulut içinde güvenliğini sağlamak için çözümler sunar.

-   [Intune'u kullanmanın yaygın yolları](https://docs.microsoft.com/intune/understand-explore/common-ways-to-use-intune) makalesini gözden geçirin ve [1. Aşama: MDM gereksinimlerini değerlendirme](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements) altındaki soruların yanıtlarını derlemeye başlayın.

## <a name="next-steps"></a>Sonraki adımlar

[1. Aşama: Intune’u mobil cihaz yönetimi (MDM) için hazırlama](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management)

