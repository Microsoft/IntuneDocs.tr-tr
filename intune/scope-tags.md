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
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 080205e601b857d4765eb6b97eeeeeb8f4e6fc1b
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52187166"
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

