---
title: Intune’da Skycure Mobile Threat Defense’i etkinleştirme
description: Klasik Intune portalında Skycure Mobile Threat Defense’i etkinleştirin.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 03/16/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0cc4e59d-819a-47a2-a26f-4f8d0f8df7bf
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: da4197a41798f4e47ff35d2dfab36c5317f92e21
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="enable-skycure-mobile-threat-defense-in-intune"></a>Intune’da Skycure Mobile Threat Defense’i etkinleştirme

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Skycure mobil tehdit savunmasını etkinleştirmek için [Skycure konsolunda Intune Bağlayıcısı](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)’nı zaten yapılandırmış olmanız gerekir.

## <a name="to-enable-the-skycure-mtd-connection-in-intune"></a>Intune'da Skycure MTD bağlantısını etkinleştirmek için

1.  [Klasik Intune portalına](https://manage.microsoft.com/) gidin ve kimlik bilgilerinizi girin.

2.  **Yönetici** &gt; **Üçüncü Taraf Hizmet Tümleştirmesi**’ni seçin, sonra **Skycure Durumu**’nu seçin ve iki durumlu düğmeyi kullanarak **MTD ile Eşitleme**’yi etkinleştirin.

    ![Klasik Intune portalında Skycure iki durumlu düğmeyi etkinleştirme](../media/mtp/enable-skycure-1.png)

> [!IMPORTANT] 
> Uyumluluk ilkesi kuralları oluşturmadan ve koşullu erişimi yapılandırmadan önce Skycure uygulamalarını yapılandırmanız gerekir. Bu, uygulamanın, e-postaya veya diğer şirket kaynaklarına erişim sağlamadan önce son kullanıcılar için hazır ve kullanılabilir olmasını sağlar.

Bu, Intune yönetici konsolunda Skycure ve Intune tümleştirmesi kurulumunu tamamlar. Bu çözümü uygulamak için sonraki birkaç adım Skycure for Work uygulamalarının dağıtılmasını ve Uyumluluk ilkesinin ayarlanmasını içerir.

## <a name="next-steps"></a>Sonraki adımlar

[Skycure Mobile Threat Defense uyumluluk ilkesi oluşturma](/intune-classic/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)
