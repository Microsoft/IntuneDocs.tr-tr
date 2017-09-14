---
title: "Intune'da Lookout MTP’yi etkinleştirme"
description: "Intune Yönetici konsolunda Lookout mobil tehdit korumasını etkinleştirin."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 57cdcb50920566c61ed43b5eada5bbde35c2438e
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2017
---
# <a name="enable-lookout-mtd-connection-in-the-intune-classic-portal"></a>Klasik Intune portalında Lookout MTD bağlantısını etkinleştirme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune'da Lookout Mobile Threat Defense (MTD) bağlantısını etkinleştirmek için Lookout konsolunda Intune Bağlayıcısı’nı zaten yapılandırmış olmanız gerekir.  Bunu henüz yapmadıysanız [Lookout Mobile Threat Defense aboneliğinizi ayarlamanız](setup-your-lookout-mtd-subscription.md) gerekir.

Intune’da Lookout MTP bağlantısını yapılandırmak için [Microsoft Intune Yönetici konsolundaki](https://manage.microsoft.com) **Yönetim** sayfasında **Üçüncü Taraf Hizmet Tümleştirmesi**’ni seçin. **Lookout durumu**’nu seçin ve iki durumlu düğmeyi kullanarak **MTP ile Eşitleme**’yi etkinleştirin.

![Etkinleştirme iki durumlu düğme vurgulanmış şekilde Lookout eşitleme sayfasının ekran görüntüsü](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> Uyumluluk ilkesi kuralları oluşturmadan ve koşullu erişimi yapılandırmadan önce Lookout for Work uygulamasını yapılandırmanız **gerekir**. Bu, uygulamanın, e-postaya veya diğer şirket kaynaklarına erişim sağlamadan önce son kullanıcılar için hazır ve kullanılabilir olmasını sağlar.

Bu, Intune yönetici konsolunda Lookout ve Intune tümleştirmesi kurulumunu tamamlar.  Bu çözümü uygulamak için ilerideki birkaç adım [Lookout for Work uygulamaları](/intune-classic/deploy-use/device-threat-protection-policy) ilkesinin dağıtılmasını içerir.


## <a name="next-steps"></a>Sonraki adımlar
[Lookout for Work uygulamasını yapılandırma](/intune-classic/deploy-use/device-threat-protection-apps)
