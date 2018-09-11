---
title: Microsoft Intune - Azure’da ilkeleri kapsam etiketleriyle filtreleme | Microsoft Docs
description: Yapılandırma profillerini belirli rollere filtrelemek için kapsam etiketlerini kullanın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 000505df3c0898ed0939244dfe1b075c64097611
ms.sourcegitcommit: e814cfbbefe818be3254ef6f859a7bf5f5b99123
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2018
ms.locfileid: "43329436"
---
# <a name="use-scope-tags-to-filter-policies"></a>İlke filtrelemek için kapsam etiketleri kullanma

Kapsam etiketleri, oluşturduğunuz özel etiketlerle ilkeleri filtrelemenize imkan verir.

Örneğin “Mühendislik Departmanı” adlı bir kapsam etiketi oluşturun ve mühendislik departmanı ile ilgili yapılandırma profillerine bunu atayın. Aynı etiketi “Mühendislik Yöneticileri” rolüne de atayın. Bu kişiler, yalnızca “Mühendislik Departmanı” etiketli ilkeleri görebilecektir.

## <a name="to-create-a-scope-tag"></a>Kapsam etiketi oluşturmak için

**Roller** > **Kapsam (etiketler)** > **Oluştur**’u seçin.

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Kapsam etiketini bir yapılandırma profiline eklemek için

**Cihaz yapılandırması** > **Profiller** > bir profil seçin > **Özellikler** > **Kapsam (Etiketler)** öğesini seçin.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Kapsam etiketini bir role atamak için

**Roller** > **Tüm roller** > **İlke ve Profil Yöneticisi** > **Atamalar** > **Kapsam (Etiketler)** öğesini seçin.

## <a name="next-steps"></a>Sonraki adımlar

[Rollerinizi](role-based-access-control.md) ve [profillerinizi](device-profile-assign.md) yönetin.

