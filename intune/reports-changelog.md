---
title: "Intune Veri Ambarı Değişiklik günlüğü | Microsoft Docs"
description: "Intune Veri Ambarı API’sindeki değişikliklerin bir listesi."
keywords: "Intune Veri Ambarı"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6d675a36cd5ea4c11d755174bf2b0bbc5d4b18ec
ms.sourcegitcommit: 5279a0bb8c5aef79aa57aa247ad95888ffe5a12b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/08/2017
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Intune Veri Ambarı API’si için değişiklik günlüğü

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune Veri Ambarı hakkında güncel bilgiler edinin.

## <a name="1710"></a>1710
_Yayımlanma tarihi: Kasım 2017_

### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>Kullanıcı varlığı Veri Ambarı veri modelinde en son kullanıcı verilerini içeriyor <!-- 1544273 -->

Intune Veri Ambarı eri modelinin ilk sürümü yalnızca son geçmiş Intune verilerini içeriyordu. Rapor oluşturucular bir kullanıcının geçerli durumunu yakalayamadı. Bu güncelleştirmede, [**Kullanıcı varlığı**](reports-ref-user.md) en son kullanıcı verileriyle doldurulur.

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>Veri Ambarı veri modelinde yeni varlıklar <!-- 1479526 --><!-- -->

 - [**UserDeviceAssociation**](reports-ref-user-device.md) varlığı eklendi. **UserDeviceAssociation**, kuruluşunuzdaki kullanıcı cihaz ilişkilerini içerir.
 - [**IntuneManagementExtension**](reports-ref-intunemanagementextension.md) varlığı eklendi. **IntuneManagementExtension**, mobil cihazlar için sürüm veya yükleme durumu gibi bilgileri izleyen varlıklar barındırır.

## <a name="next-steps"></a>Sonraki adımlar
 - [Intune’daki haftalık yenilikleri](whats-new.md) öğrenin. Yaklaşan değişiklikler, hizmet hakkında önemli bildirimler ve geçmiş sunumlar hakkında bilgiler de alabilirsiniz. 
 - [Microsoft Intune Blogu](http://go.microsoft.com/fwlink/?LinkID=273882)’nu okuyun.