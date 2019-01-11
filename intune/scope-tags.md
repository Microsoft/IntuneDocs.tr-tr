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
ms.openlocfilehash: 0da6861b6c49fc37691b8c6e464a506670643fa3
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203340"
---
# <a name="use-scope-tags-to-filter-policies"></a>İlke filtrelemek için kapsam etiketleri kullanma

Kapsam etiketleri, oluşturduğunuz özel etiketlerle ilkeleri filtrelemenize imkan verir. Kapsam etiketleri, rolleri ve uygulamalara uygulayabilirsiniz.

Örneğin “Mühendislik Departmanı” adlı bir kapsam etiketi oluşturun ve mühendislik departmanı ile ilgili yapılandırma profillerine bunu atayın. Aynı etiketi “Mühendislik Yöneticileri” rolüne de atayın. Bu kişiler, yalnızca “Mühendislik Departmanı” etiketli ilkeleri görebilecektir.

## <a name="to-create-a-scope-tag"></a>Kapsam etiketi oluşturmak için

**Roller** > **Kapsam (etiketler)** > **Oluştur**’u seçin.

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Kapsam etiketini bir yapılandırma profiline eklemek için

**Cihaz yapılandırması** > **Profiller** > bir profil seçin > **Özellikler** > **Kapsam (Etiketler)** öğesini seçin.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Kapsam etiketini bir role atamak için

**Roller** > **Tüm roller** > **İlke ve Profil Yöneticisi** > **Atamalar** > **Kapsam (Etiketler)** öğesini seçin.

## <a name="to-assign-a-scope-tag-to-an-app"></a>Uygulama için bir kapsam etiketi atama

Seçin **istemci uygulamaları** > **uygulamaları** > bir uygulama seçin > **özellikleri** > **kapsam (etiketler)**  >  **Ekle** > etiketleri seçin > **seçin** > **Tamam** > **Kaydet**.


## <a name="next-steps"></a>Sonraki adımlar

[Rollerinizi](role-based-access-control.md) ve [profillerinizi](device-profile-assign.md) yönetin.

