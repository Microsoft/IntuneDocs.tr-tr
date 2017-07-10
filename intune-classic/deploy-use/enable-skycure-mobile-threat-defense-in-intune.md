---
title: "Intune’da Skycure Mobile Threat Defense’i etkinleştirme"
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
ms.openlocfilehash: 4dad45d15fec7189fdcf184839040b9e3f9a3a48
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="enable-skycure-mobile-threat-defense-in-intune"></a>Intune’da Skycure Mobile Threat Defense’i etkinleştirme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Skycure mobil tehdit korumasını etkinleştirmek için [Skycure konsolunda Intune Bağlayıcısı’nı zaten yapılandırmış olmanız gerekir] (/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune).

## <a name="to-enable-the-skycure-mtd-connection-in-intune"></a>Intune'da Skycure MTD bağlantısını etkinleştirmek için

1.  [Intune klasik konsoluna](https://manage.microsoft.com/) gidin ve kimlik bilgilerinizi girin.

2.  **Yönetici** &gt; **Üçüncü Taraf Hizmet Tümleştirmesi**’ni seçin, sonra **Skycure Durumu**’nu seçin ve iki durumlu düğmeyi kullanarak **MTD ile Eşitleme**’yi etkinleştirin.

    ![Intune klasik konsolunda Skycure’u Etkinleştirme iki durumlu düğmesi](../media/mtp/enable-skycure-1.png)

> [!IMPORTANT] 
> Uyumluluk ilkesi kuralları oluşturmadan ve koşullu erişimi yapılandırmadan önce Skycure uygulamalarını yapılandırmanız gerekir. Bu, uygulamanın, e-postaya veya diğer şirket kaynaklarına erişim sağlamadan önce son kullanıcılar için hazır ve kullanılabilir olmasını sağlar.

Bu, Intune yönetici konsolunda Skycure ve Intune tümleştirmesi kurulumunu tamamlar. Bu çözümü uygulamak için sonraki birkaç adım Skycure for Work uygulamalarının dağıtılmasını ve Uyumluluk ilkesinin ayarlanmasını içerir.

## <a name="next-steps"></a>Sonraki adımlar

[Skycure Mobile Threat Defense uyumluluk ilkesi oluşturma](/intune-classic/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)
