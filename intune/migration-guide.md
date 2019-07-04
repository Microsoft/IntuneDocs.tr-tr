---
title: Intune mobil cihaz yönetimi geçiş kılavuzu
titleSuffix: Microsoft Intune
description: Bu kılavuz, bir üçüncü taraf MDM sağlayıcısından Microsoft Intune’a geçiş ile ilgili çeşitli ayrıntılar hakkında bilgi sağlar.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: b34143e17245de61026a536cc0b8c5e8a7f80107
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2019
ms.locfileid: "67549394"
---
# <a name="intune-migration-guide"></a>Intune geçiş kılavuzu

![Microsoft Intune MDM geçiş kılavuzu görseli](./media/MDM-migration-guide-art.PNG)

Microsoft Intune’a başarılı bir geçiş; geçerli mobil cihaz yönetimi (MDM) ortamınızı, iş hedeflerinizi ve teknik gereksinimlerinizi hesaba katan sağlam bir plan ile başlar. Ayrıca, geçiş planınızı destekleyecek ve sizinle işbirliği yapacak önemli proje katılımcılarının olması gerekir.

Bu kılavuz, bir üçüncü taraf MDM sağlayıcısından Intune’a geçiş ile ilgili çeşitli ayrıntılar hakkında bilgi sağlar.

## <a name="whats-included-in-this-guide"></a>Kılavuza neler dahildir?

Bu kılavuz, geçiş işlemini iki aşamaya ayırır. Bu adımlar, aşamalardan oluşan Intune MDM’ye geçiş işleminde size yardımcı olacak görevler, stratejiler ve taktiksel kılavuz içerir.

- [1. Aşama: Intune mobil cihaz yönetimi için hazırlama](migration-guide-prepare.md)

    - [MDM geçiş gereksinimlerinizi değerlendirme](migration-guide-prepare.md#assess-mdm-requirements)

    - [Temel kurulum](migration-guide-setup.md)

    - [Mobil cihaz ve uygulama yönetimi ilkelerini yapılandırma](migration-guide-configure-policies.md)

    - [Uygulama koruma ilkelerini yapılandırma](migration-guide-app-protection-policies.md)

    - [Geçiş konusunda dikkat edilmesi gereken önemli noktalar](migration-guide-considerations.md)

- [2. Aşama: Geçiş kampanyası](migration-guide-campaign.md)

    - [İletişim planı](migration-guide-communication-plan.md)

    - [Koşullu erişimle son kullanıcı benimsemesi sağlama](migration-guide-drive-adoption.md)

    - [Normal geçiş süreci](migration-guide-cycle.md)
        - [Geçiş izleme](migration-guide-cycle.md#monitoring-migration)
        - [Geçiş sonrası](migration-guide-cycle.md#post-migration)

## <a name="assumptions"></a>Varsayımlar

- Intune’u zaten bir kavram kanıtı (PoC) ortamında değerlendirdiniz ve kuruluşunuzda MDM çözümü olarak kullanmaya karar verdiniz.

- Intune ve özellikleri konusunda zaten bilgi sahibisiniz.

## <a name="before-you-begin"></a>Başlamadan önce

Yeni Intune dağıtımınızın eski MDM dağıtımınızdan farklı olabileceğini bilmek önemlidir. Geleneksel MDM hizmetlerinden farklı olarak Intune, kimlik tabanlı erişim denetimi odaklıdır ve bu nedenle kuruluşun ağ çevresi dışında mobil cihazlardan şirket verilerine erişimi denetlemek için bir ağ ara sunucusu gereci gerektirmez. Microsoft, sıkıca tümleşik bulut hizmetleri paketi aracılığıyla, veri hizmetlerinin bulut içinde güvenliğini sağlayan çözümler sunar. Bu çözümlerin genel adı Enterprise Client + Security teklifidir.

- [Intune kullanmanın yaygın yollarını](common-scenarios.md) gözden geçirin.

## <a name="next-steps"></a>Sonraki adımlar

[1. Aşama: Intune mobil cihaz yönetimi için hazırlama](migration-guide-prepare.md)
