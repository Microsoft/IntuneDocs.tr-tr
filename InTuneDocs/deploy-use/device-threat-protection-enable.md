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
ms.sourcegitcommit: 53862e49c922b75b414fd5aceec3bba2b10299a6
ms.openlocfilehash: 1297522d0f7b52ebe14eb7b938f3458e7308ae27


---

# <a name="enable-lookout-mtp-connection-in-the-intune-admin-console"></a>Intune Yönetici konsolunda Lookout MTP bağlantısını etkinleştirme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune'da Lookout kötü amaçlı tehdit koruma (MTP) bağlantısını etkinleştirmek için Lookout konsolunda Intune Bağlayıcısı’nı zaten yapılandırmış olmanız gerekir.  Bunu yapmadıysanız [Lookout mobil tehdit koruması aboneliğinizi ayarlamanız](set-up-your-subscription-with-lookout-mtp.md) gerekir.

Intune’da Lookout MTP bağlantısını yapılandırmak için [Microsoft Intune Yönetici konsolundaki](https://manage.microsoft.com) **Yönetim** sayfasında **Üçüncü Taraf Hizmet Tümleştirmesi**’ni seçin. **Lookout durumu**’nu seçin ve iki durumlu düğmeyi kullanarak **MTP ile Eşitleme**’yi etkinleştirin.

![Etkinleştirme iki durumlu düğme vurgulanmış şekilde Lookout eşitleme sayfasının ekran görüntüsü](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> Uyumluluk ilkesi kuralları oluşturmadan ve koşullu erişimi yapılandırmadan önce Lookout for Work uygulamasını yapılandırmanız **gerekir**. Bu, uygulamanın, e-postaya veya diğer şirket kaynaklarına erişim sağlamadan önce son kullanıcılar için hazır ve kullanılabilir olmasını sağlar.

Bu, Intune yönetici konsolunda Lookout ve Intune tümleştirmesi kurulumunu tamamlar.  Bu çözümü uygulamak için sonraki birkaç adım [Lookout for Work uygulamalarının](configure-and-deploy-lookout-for-work-apps.md) dağıtılmasını ve [Uyumluluk](enable-device-threat-protection-rule-in-compliance-policy.md) ilkesinin ayarlanmasını içerir.


## <a name="next-steps"></a>Sonraki adımlar
[Lookout for Work uygulamasını yapılandırma](configure-and-deploy-lookout-for-work-apps.md)



<!--HONumber=Jan17_HO2-->

