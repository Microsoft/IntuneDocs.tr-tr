---
title: "Intune’da Skycure Mobile Threat Defense’i etkinleştirme | Microsoft Docs"
description: "Intune klasik konsolunda Skycure Mobile Threat Defense’i etkinleştirin."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0cc4e59d-819a-47a2-a26f-4f8d0f8df7bf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: a110f2ae4d8a101a7fb977aa651e5ce2c8828e7e
ms.lasthandoff: 03/22/2017


---

# <a name="enable-skycure-mobile-threat-defense-in-intune"></a>Intune’da Skycure Mobile Threat Defense’i etkinleştirme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune'da Skycure mobil tehdit koruması (MTD) bağlantısını etkinleştirmek için [Skycure konsolunda Intune Bağlayıcısı](https://docs.microsoft.com/intune/deploy-use/setup-the-skycure-integration-with-Intune)’nı zaten yapılandırmış olmanız gerekir.

## <a name="to-enable-the-skycure-mtd-connection-in-intune"></a>Intune'da Skycure MTD bağlantısını etkinleştirmek için

1.  [Intune klasik konsoluna](https://manage.microsoft.com/) gidin ve kimlik bilgilerinizi girin.

2.  **Yönetici** &gt; **Üçüncü Taraf Hizmet Tümleştirmesi**’ni seçin, sonra **Skycure Durumu**’nu seçin ve iki durumlu düğmeyi kullanarak **MTD ile Eşitleme**’yi etkinleştirin.

    ![Intune klasik konsolunda Skycure’u Etkinleştirme iki durumlu düğmesi](../media/mtp/enable-skycure-1.png)

> [!IMPORTANT] 
> Uyumluluk ilkesi kuralları oluşturmadan ve koşullu erişimi yapılandırmadan önce Skycure uygulamalarını yapılandırmanız gerekir. Bu, uygulamanın, e-postaya veya diğer şirket kaynaklarına erişim sağlamadan önce son kullanıcılar için hazır ve kullanılabilir olmasını sağlar.

Bu, Intune yönetici konsolunda Skycure ve Intune tümleştirmesi kurulumunu tamamlar. Bu çözümü uygulamak için sonraki birkaç adım Skycure for Work uygulamalarının dağıtılmasını ve Uyumluluk ilkesinin ayarlanmasını içerir.

## <a name="next-steps"></a>Sonraki adımlar

[Skycure Mobile Threat Defense uyumluluk ilkesi oluşturma](https://docs.microsoft.com/intune/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)

