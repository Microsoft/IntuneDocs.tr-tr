---
title: "Intune&quot;da Lookout MTP’yi Etkinleştirme | Microsoft Docs"
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
translationtype: Human Translation
ms.sourcegitcommit: d42fa20a3bc6b6f4a74dd0872aae25cfb33067b9
ms.openlocfilehash: d2a10a0e14d9b0b4d2e3f8e2715b47d984e5aa66
ms.lasthandoff: 03/21/2017


---

# <a name="enable-lookout-mtd-connection-in-the-intune-classic-console"></a>Intune klasik konsolunda Lookout MTD bağlantısını etkinleştirme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune'da Lookout Mobile Threat Defense (MTD) bağlantısını etkinleştirmek için Lookout konsolunda Intune Bağlayıcısı’nı zaten yapılandırmış olmanız gerekir.  Bunu henüz yapmadıysanız [Lookout Mobile Threat Defense aboneliğinizi ayarlamanız](set-up-your-subscription-with-lookout-mtp.md) gerekir.

Intune’da Lookout MTP bağlantısını yapılandırmak için [Microsoft Intune Yönetici konsolundaki](https://manage.microsoft.com) **Yönetim** sayfasında **Üçüncü Taraf Hizmet Tümleştirmesi**’ni seçin. **Lookout durumu**’nu seçin ve iki durumlu düğmeyi kullanarak **MTP ile Eşitleme**’yi etkinleştirin.

![Etkinleştirme iki durumlu düğme vurgulanmış şekilde Lookout eşitleme sayfasının ekran görüntüsü](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> Uyumluluk ilkesi kuralları oluşturmadan ve koşullu erişimi yapılandırmadan önce Lookout for Work uygulamasını yapılandırmanız **gerekir**. Bu, uygulamanın, e-postaya veya diğer şirket kaynaklarına erişim sağlamadan önce son kullanıcılar için hazır ve kullanılabilir olmasını sağlar.

Bu, Intune yönetici konsolunda Lookout ve Intune tümleştirmesi kurulumunu tamamlar.  Bu çözümü uygulamak için sonraki birkaç adım [Lookout for Work uygulamalarının](https://docs.microsoft.com/intune/deploy-use/device-threat-protection-apps) dağıtılmasını ve [Uyumluluk](https://docs.microsoft.com/intune/deploy-use/device-threat-protection-policy) ilkesinin ayarlanmasını içerir.


## <a name="next-steps"></a>Sonraki adımlar
[Lookout for Work uygulamasını yapılandırma](https://docs.microsoft.com/intune/deploy-use/device-threat-protection-apps)

