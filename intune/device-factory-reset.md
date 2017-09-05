---
title: "Cihazları Intune ile fabrika ayarlarına sıfırlama"
titleSuffix: Intune on Azure
description: "Intune ile yönettiğiniz cihazları fabrika ayarlarına nasıl sıfırlayacağınızı öğrenin.\""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8eff9b53-eef2-4c50-8aee-556bc49d69f2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fd7273d6c5f75a675d7b01df4225a96fd3a5f821
ms.sourcegitcommit: 10e3ab2aeb79a1fb2243bef2748ccc003fdd4cc7
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2017
---
# <a name="reset-intune-managed-devices-to-factory-settings"></a>Intune tarafından yönetilen cihazları fabrika ayarlarına sıfırlama


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Fabrika sıfırlaması** - Bir cihazı varsayılan ayarlarına döndürür. Cihaz artık Intune tarafından yönetilmez ve hem şirket verileri hem de kişisel veriler kaldırılır. Bu eylemi geri alamazsınız.

## <a name="supported-platforms"></a>Desteklenen platformlar

- Windows - Windows 8.1 ve üzerinde desteklenir (EAS ile yönetilen cihazlar hariç)
- Windows Phone - Desteklenir
- iOS - Desteklenir
- macOS - Desteklenmiyor
- Android - Desteklenir (Android for Work desteklenmiyor)

## <a name="how-to-reset-a-device-to-factory-settings"></a>Bir cihazı fabrika ayarlarına sıfırlama

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.
4. **Cihazlar ve gruplar** dikey penceresinde **Tüm cihazlar**’ı seçin.
5. Yönettiğiniz cihazların listesinden bir cihaz seçin, sonra **Fabrika sıfırlaması** uzak cihaz işlemini seçin.

## <a name="next-steps"></a>Sonraki adımlar

Az önce gerçekleştirdiğiniz işlemin durumunu görmek için **Cihazlar ve gruplar** dikey penceresinde **Cihaz Eylemleri**'ni seçin.
