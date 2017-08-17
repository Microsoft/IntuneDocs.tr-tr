---
title: "Intune ile cihazlardan şirket verilerini kaldırma"
titleSuffix: Intune on Azure
description: "Intune ile yönettiğiniz cihazlardan yalnızca şirket verilerini kaldırma hakkında bilgi edinin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f021e95f-157f-4e8a-9253-1cff03d6ee3e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b0cc7d62770057ff9df5a36e6e5df58b29430534
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2017
---
# <a name="remove-company-data-from-intune-managed-devices"></a>Intune tarafından yönetilen cihazlardan şirket verilerini kaldırma


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Şirket verilerini kaldır** cihaz eylemi, Intune tarafından yönetilen cihazlardan yalnızca şirket verilerini kaldırır. Eylem, cihazdan kişisel verileri kaldırmaz. Kaldırma işleminden sonra cihaz artık Intune tarafından yönetilmez ve şirket kaynaklarına erişemez.

## <a name="supported-platforms"></a>Desteklenen platformlar

- Windows - Desteklenir (Azure Active Directory'e katılan Windows cihazları için desteklenmez)
- Windows Phone - Desteklenir
- iOS - Desteklenir
- macOS - Desteklenir
- Android - Desteklenir

## <a name="how-to-remove-company-data"></a>Şirket verilerini kaldırma

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.
4. **Cihazlar ve gruplar** dikey penceresinde **Tüm cihazlar**’ı seçin.
5. Yönettiğiniz cihazların listesinden bir cihaz seçin, bir cihaz seçin, sonra **Şirket verilerini kaldır** uzak cihaz işlemini seçin.

## <a name="next-steps"></a>Sonraki adımlar

Az önce gerçekleştirdiğiniz işlemin durumunu görmek için **Cihazlar ve gruplar** dikey penceresinde **Cihaz Eylemleri**'ni seçin.
