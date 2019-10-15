---
title: Intune 'da veri depolama ve işleme
titleSuffix: Microsoft Intune
description: Kişisel verilerin Intune 'da nasıl depolandığını ve işlendiğini öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: edb07842-6a16-482e-8c1d-541a29e169a8
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9c9a8bd5888ab0977d1ca553d059c1e96cccda75
ms.sourcegitcommit: dd6755383ba89824d1cc128698a65fde6bb2de55
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306888"
---
# <a name="data-storage-and-processing-in-intune"></a>Intune 'da veri depolama ve işleme

Intune [verileri topladıktan](privacy-data-collect.md)sonra bu verilerin depolanması ve işlenmesi aşağıda ayrıntılı olarak devam eder.

## <a name="storing-personal-data"></a>Kişisel verileri depolama

Toplanan tüm telemetri olmayan veriler, Intune hizmeti aracılığıyla işlenir ve aşağıdaki depolama konumlarından bir veya daha fazlasına depolanır: 

- SQLAzure 
- Güvenilir Koleksiyonlar (Service Fabric)  
- Azure Storage 

İzleme için anahtar olan telemetri (hizmet günlükleri, performans günlükleri, hatalar vb.) Microsoft 'un telemetri veri depolarına gönderilir.

### <a name="storage-locations"></a>Depolama konumları

Microsoft, Intune hizmetlerini dünya çapındaki birçok bölgede sunar ve çalışır. Intune, müşteri verileri için yönetici tarafından yapılan depolama konumu eleimlerini uyar.

Daha fazla bilgi için bkz. [verilerinizin nerede bulunduğu](https://www.microsoft.com/trust-center/privacy/data-location) yer.

### <a name="personal-data-retention"></a>Kişisel veri saklama

Genel olarak, kişisel veriler, Kullanıcı Intune yönetiminden kaldırıldıktan sonra 30 gün boyunca Intune tarafından korunur.

Intune kullanımının bir parçası olarak toplanan telemetri verileri en fazla 30 gün boyunca tutulur.

Denetim günlükleri bir yıla kadar tutulur.

## <a name="processing-personal-data"></a>Kişisel verileri işleme

Intune, kişisel verileri ISO sertifikalı sistemlerle işler. Daha fazla bilgi için bkz. [hizmet güveni portalı](https://www.microsoft.com/en-us/TrustCenter/stp).

### <a name="profiling-and-marketing"></a>Profil oluşturma ve pazarlama

Microsoft Intune profil oluşturma veya pazarlama amaçları için hizmeti sağlamanın bir parçası olarak toplanan kişisel verileri kullanmaz. 

### <a name="restrict-processing-of-personal-data"></a>Kişisel verilerin işlenmesini kısıtla

Bir kullanıcının kişisel verilerinin işlenmesini kısıtlamak için, kullanıcılar hesabını şu şekilde silebilirsiniz:
1. Kullanıcının kişisel verilerinin elektronik kopyasını dışarı aktarma
    - accounts
    - hizmet verileri
    - ilişkili Günlükler
2. Kullanıcının hesabı ve Intune 'dan ilişkili veriler siliniyor.

## <a name="next-steps"></a>Sonraki adımlar

Intune 'un kişisel verileri nasıl [güvenlik altına aldığı ve paylaştığı](privacy-data-secure-share.md) hakkında daha fazla bilgi edinin. 
