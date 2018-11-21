---
title: Intune’da veri depolama ve işleme
description: Intune’da kişisel verilerin nasıl depolanıp işlendiğini öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: edb07842-6a16-482e-8c1d-541a29e169a8
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: f1adab40170227926dce1eb7c14117accf1d7d0a
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52185924"
---
# <a name="data-storage-and-processing-in-intune"></a>Intune’da veri depolama ve işleme

Intune [verileri topladıktan](privacy-data-collect.md) sonra, verilerin depolanması ve işlenmesi aşağıda ayrıntılı olarak açıklanmıştır.

## <a name="storing-personal-data"></a>Kişisel verileri depolama

Toplanan ve telemetri olmayan tüm veriler, Intune hizmetinde işlenir ve aşağıdaki depolama konumlarından bir veya birkaçında depolanır: 

- SQLAzure 
- Güvenilir Koleksiyonlar (Service Fabric)  
- Azure depolama 

İzlemenin ve düzgün çalışan bir hizmet sağlamanın anahtarı olan telemetri (hizmet günlükleri, performans günlükleri, hatalar vb.) Microsoft’un telemetri veri depolarına gönderilir.

### <a name="storage-locations"></a>Depolama konumları

Microsoft, Intune hizmetlerini dünya çapında birçok bölgede sunmakta ve yönetmektedir. Intune, yönetici tarafından Müşteri Verileri için yapılan depolama konumu seçimlerine saygı duyar.

Daha fazla bilgi için bkz. [Microsoft Intune Müşteri verilerim nerede?](For more information, see Microsoft Intune Where is my customer data?)

### <a name="personal-data-retention"></a>Kişisel verilerin saklanması

Genel olarak kişisel veriler, kullanıcı Intune yönetiminden kaldırıldıktan sonra otuz gün boyunca Intune tarafından korunur.

Intune kullanımının parçası olarak toplanan telemetri verileri en fazla otuz gün saklanır.

Denetim günlükleri ise bir sene boyunca saklanabilir.

## <a name="processing-personal-data"></a>Kişisel verilerin işlenmesi

Intune, kişisel verileri ISO sertifikalı sistemlerle işler. Daha fazla bilgi için bkz. [Hizmet Güveni Portalı](https://www.microsoft.com/en-us/TrustCenter/stp).

### <a name="profiling-and-marketing"></a>Profil oluşturma ve pazarlama

Microsoft Intune, hizmet sağlama işleminin parçası olarak toplanan hiçbir kişisel veriyi profil oluşturma veya pazarlama amacıyla kullanmaz. 

### <a name="restrict-processing-of-personal-data"></a>Kişisel verilerin işlenmesini kısıtlama

Bir kullanıcıya ait kişisel verilerin işlenmesini kısıtlamak için kullanıcı hesabını aşağıdaki yollarla silebilirsiniz:
1. Kullanıcının aşağıdakiler dahil olmak üzere kişisel verilerinin elektronik kopyasını dışarı aktararak
    - hesaplar
    - hizmet verileri
    - ilişkili uygulamalar
2. Kullanıcının hesabını ve ilişkili verilerini Intune’dan silerek.

## <a name="next-steps"></a>Sonraki adımlar

Intune’un verileri nasıl [güvenlik altına aldığı ve paylaştığı](privacy-data-secure-share.md) hakkında daha fazla bilgi edinin. 