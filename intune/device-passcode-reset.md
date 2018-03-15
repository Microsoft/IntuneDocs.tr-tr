---
title: "Intune ile cihaz geçiş kodlarını sıfırlama ve kaldırma"
titlesuffix: Azure portal
description: "Intune ile yönettiğiniz cihazlarda geçiş kodunu sıfırlama ve kaldırma hakkında bilgi edinin."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4e1496d24fd9d3bb636a4eab00c254b753210f63
ms.sourcegitcommit: eac89306d1391a6d3ae1179612b0820b19c2baa6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="reset-and-remove-the-passcode-on-intune-managed-devices"></a>Intune tarafından yönetilen cihazlardaki geçiş kodunu sıfırlama ve kaldırma


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

*Kaldırma* ve *sıfırlama* terimleri bu makalede değişimli olarak kullanılmıştır.

**Geçiş kodunu kaldır** eylemi, cihaz için <*cihaz adı*> **Genel Bakış** dikey penceresinde görüntülenen yeni bir geçiş kodu oluşturur.

## <a name="supported-platforms"></a>Desteklenen platformlar

- Windows - Desteklenmiyor
- Windows Phone - Windows Phone 8.1’den Azure AD’ye katılmamış Windows 10 Creators güncelleştirmesine kadar, Windows 10 Creators Update ve üzerinde desteklenir
- iOS - Desteklenir
- macOS - Desteklenmiyor
- Android - Android 7'den önceki Android sürümlerinde desteklenir. Android for Work desteklenmiyor.

## <a name="how-to-reset-a-passcode"></a>Geçiş kodunu sıfırlama

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.
4. **Cihazlar** dikey penceresinden **Tüm cihazlar**'ı seçin.
5. Yönettiğiniz cihazların listesinden bir cihaz seçin, sonra **...Daha Fazla**’yı ve ardından **Geçiş kodunu kaldır** uzak cihaz eylemini seçin.

## <a name="next-steps"></a>Sonraki adımlar

Az önce gerçekleştirdiğiniz işlemin durumunu görmek için **Cihazlar** dikey penceresinde **Cihaz eylemleri**'ni seçin.
