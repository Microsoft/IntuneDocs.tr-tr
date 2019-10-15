---
title: Intune 'da veri güvenliği ve paylaşımı
titleSuffix: Microsoft Intune
description: Kişisel verilerin Intune 'da güvenli ve paylaşılan olduğunu öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 68921fd6-5f50-456c-a3af-83d7bc4b134b
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 53480b7a2e008af46f4f8929cc6321e10b042b33
ms.sourcegitcommit: dd6755383ba89824d1cc128698a65fde6bb2de55
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306743"
---
# <a name="data-security-and-sharing-in-intune"></a>Intune 'da veri güvenliği ve paylaşımı


## <a name="data-security"></a>Veri güvenliği

Microsoft Intune, Microsoft Enterprise Mobility ve Security Suite Bulut hizmeti teklifi 'nin temel bir bileşenidir. [Veri idare stratejisini](https://www.microsoft.com/en-us/TrustCenter/Security/default.aspx)desteklemek için, tüm Microsoft bulut Hizmetleri [Microsoft gizliliği](https://www.microsoft.com/en-us/trustcenter/privacy) ve [Microsoft Güvenlik](https://www.microsoft.com/en-us/trustcenter/security/) yöntemleri ile geliştirilmiştir.  

Microsoft Intune, Microsoft Azure hizmet ekiplerinin veri ihlali işlemlerine karşı güvenliğini sağlamak için aldığı teknik ve kurumsal ölçüleri izler.

Daha fazla bilgi için bkz. [hizmet güveni portalı](https://www.microsoft.com/en-us/TrustCenter/stp).

Intune, şunun gibi en düşük düzeyde veri seçme tekniklerini kullanır

- Toplama
- Bazı özellikler için isteğe bağlı veri toplama
- veriler daha az kesin veya gizli hale getirilir

Intune, varsayılan olarak veri korumayı sağlamak için destek olayları için RBAC ve JIT güvenlik gibi teknikler de kullanır. 

### <a name="data-breach-reporting"></a>Veri ihlali raporlaması

Müşteri tarafından raporlanabilir bir güvenlik olayı (CRSı) tanımlandığında müşteriler bilgilendirilir. Bu işlem, Intune kullanarak herhangi bir Microsoft O365 müşterisi için ihlal bildirimine iletişim kurmak üzere Microsoft O365 ekibiyle çalışmayı içerir.

## <a name="data-sharing"></a>Veri paylaşımı

Kiracı yöneticileri belirli işlevleri (Apple Aygıt Kayıt Programı gibi) açıp, Microsoft Intune uygun üçüncü taraflarla veri paylaşımı için yönetici onayı edinir. Bu gibi durumlarda, Intune kişisel verileri ile paylaşabilir:

- Microsoft 'un aracıları gibi davranan üçüncü taraflar.
- Üçüncü taraflar, Microsoft 'un aracıları olarak davranmayan, ancak yalnızca kiracı yöneticilerinin Intune iznini açıkça izin vermesi durumunda.

Microsoft aracıları gibi davranan tüm üçüncü taraflar, [çevrimiçi hizmetler taşeronları listesine](https://aka.ms/Online_Serv_Subcontractor_List)dahil edilmiştir.

Bu tür varlıklarla veri paylaşımı, müşteri ve teknik desteğe, hizmet bakımını ve diğer işlemlere yardımcı olmak için yapılır.

Üçüncü tarafa sahip bir kiracının sözleşmesi, üçüncü tarafın hizmetinde tutulan Intune kişisel verilerini yönetir. Ayrıca, Intune 'a verileri üçüncü taraf hizmetine aktarma izni verir.  

Belirli üçüncü taraflarla paylaşılan veriler hakkında daha fazla bilgi için aşağıdaki makalelere bakın:
- [Intune 'un Apple 'a gönderdiği veriler](data-intune-sends-to-apple.md)
- [Intune 'un Google 'a gönderdiği veriler](data-intune-sends-to-google.md)
- [Apple Intune 'a gönderilen veriler](data-apple-sends-to-intune.md)
- [Google 'ın Intune 'a gönderdiği veriler](data-google-sends-to-intune.md)
- [Veri JAMF Pro, Intune 'a gönderir](data-jamf-sends-to-intune.md)

### <a name="system-center-configuration-manager-data-sharing"></a>System Center Configuration Manager veri paylaşımı

Microsoft Intune, System Center Configuration Manager hiçbir veri paylaşmaz. System Center Configuration Manager, doğrudan müşteri tarafından dağıtılan, yönetilen ve çalıştırılan şirket içi bir üründür. Configuration Manager tarafından toplanan tanılama ve kullanım verileri, gelecekteki sürümlerin yükleme deneyimini, kalitesini ve güvenliğini geliştirmek içindir.

Daha fazla bilgi için bkz. [SCCM Için tanılama ve kullanım verileri](https://docs.microsoft.com/sccm/core/plan-design/diagnostics/diagnostics-and-usage-data). 


## <a name="next-steps"></a>Sonraki adımlar

Intune 'da kişisel verileri [görüntüleme ve düzeltme](privacy-data-view-correct.md) hakkında bilgi edinin.
