---
title: "Intune'da Lookout MTP’yi Etkinleştirme | Microsoft Intune"
description: "Intune Yönetici konsolunda Lookout mobil tehdit korumasını etkinleştirin."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1334500471d2aea5e8c58a3219c755bfd9953424
ms.openlocfilehash: 4ae7d6c571f69c0cc51dc15355e50325afb88694


---

# Intune Yönetici konsolunda Lookout MTP bağlantısını etkinleştirme
Bu konu, Intune'da Lookout MTP bağlantısını nasıl etkinleştireceğinizi gösterir. Bu adımı uygulamadan önce Lookout MTP konsolunda Intune Bağlayıcısını zaten yapılandırmış olmanız gerekir.  Bunu zaten yapmadıysanız, [Lookout mobil tehdit koruması aboneliğinizi ayarlama](set-up-your-subscription-with-lookout-mtp.md) bölümünde açıklanan adımları uygulayın.

Intune’da Lookout MTP bağlantısını yapılandırmak için [Microsoft Intune Yönetici konsolundaki](https://manage.microsoft.com) **Yönetim** sayfasında **Üçüncü Taraf Hizmet Tümleştirmesi**’ni seçin. **Lookout durumu**’nu seçin ve iki durumlu düğmeyi kullanarak **MTP ile Eşitleme**’yi etkinleştirin.

![Etkinleştirme iki durumlu düğme vurgulanmış şekilde Lookout eşitleme sayfasının ekran görüntüsü](../media/mtp/lookout-intune-synchronization.png)

Bu, Intune yönetici konsolunda Lookout ve Intune tümleştirmesi kurulumunu tamamlar.  Bu çözümü uygulamak için sonraki birkaç adım [Lookout for Work uygulamalarının](configure-and-deploy-lookout-for-work-apps.md) dağıtılmasını ve [Uyumluluk](enable-device-threat-protection-rule-in-compliance-policy.md) ilkesinin ayarlanmasını içerir.

>[!IMPORTANT]
> Uyumluluk ilkesi kuralları oluşturmadan ve koşullu erişimi yapılandırmadan önce Lookout for Work uygulamasını yapılandırmanız **gerekir**. Bu, uygulamanın, e-postaya veya diğer şirket kaynaklarına erişim sağlamadan önce son kullanıcılar için hazır ve kullanılabilir olmasını sağlar.
## Sonraki adımlar
[Lookout for Work uygulamasını yapılandırma ](configure-and-deploy-lookout-for-work-apps.md)



<!--HONumber=Sep16_HO2-->


