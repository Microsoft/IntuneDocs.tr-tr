---
title: Intune’da veri güvenliği ve paylaşımı
description: Intune’da kişisel verilerin nasıl güvenlik altına alınıp paylaşıldığını öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 68921fd6-5f50-456c-a3af-83d7bc4b134b
ms.reviewer: angerobe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 085b6a3a68964a200a5d6c462b3710b9744ac99f
ms.sourcegitcommit: 07528df71460589522a2e1b3e5f9ed63eb773eea
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34474624"
---
# <a name="data-security-and-sharing-in-intune"></a>Intune’da veri güvenliği ve paylaşımı


## <a name="data-security"></a>Veri güvenliği

Microsoft Intune, Microsoft Enterprise Mobility ve Security Suite bulut hizmeti teklifinin önemli bir bileşenidir. [Veri yönetimi stratejisini](https://www.microsoft.com/en-us/TrustCenter/Security/default.aspx) desteklemek için tüm Microsoft bulut hizmetleri [Microsoft Gizliliği](https://www.microsoft.com/en-us/trustcenter/privacy) ve [Microsoft Güvenliği](https://www.microsoft.com/en-us/trustcenter/security/) metodolojileri ile geliştirilmiştir.  

Microsoft Intune, Microsoft Azure hizmet ekiplerinin veri güvenliği ihlali işlemlerine karşı güvenliği sağlamak için aldığı teknik ve organizasyonel önlemleri alır.

Daha fazla bilgi için bkz. [Hizmet Güveni Portalı](https://www.microsoft.com/en-us/TrustCenter/stp).

Intune, aşağıdakilere benzer veri azaltma teknikleri kullanır:

- toplama
- bazı özellikler için isteğe bağlı veri toplama
- doğruluğu veya hassaslığı azaltılan veriler

Intune, Varsayılan olarak Veri Korumasını sağlamak amacıyla destek olayları için RBAC ve JiT güvenliği gibi teknikler de kullanır. 

### <a name="data-breach-reporting"></a>Veri ihlalini raporlama

Müşterinin Raporlayabildiği Güvenlik Olayı (CRSI) tanımlandığında müşteriler bilgilendirilir. Bu işlem, Intune kullanan Microsoft O365 müşterilerine ihlal bildirimi yapmak için Microsoft O365 ekibiyle birlikte çalışmayı içerir.

## <a name="data-sharing"></a>Veri paylaşımı

Kiracı yöneticileri bazı işlevleri (Apple Aygıt Kayıt Programı gibi) açtığında, Microsoft Intune uygun üçüncü taraflarla veri paylaşımı için yönetici onayı alır. Böyle durumlarda Intune, şu taraflarla kişisel verileri paylaşabilir:

- Microsoft’un aracısı olarak davranan üçüncü taraflar.
- Yalnızca kiracı yöneticileri Intune’a açıkça bu izni verdiğinde Microsoft’un aracısı olarak davranan üçüncü taraflar.

Microsoft aracısı olarak davranan tüm üçüncü tarafları [Online Services Alt Yüklenici listesinde](https://aka.ms/Online_Serv_Subcontractor_List) bulabilirsiniz.

Bu varlıklarla veri paylaşmanın amacı müşteri desteğine ve teknik desteğe, hizmet bakımına ve diğer işlemlere yardımcı olmaktır.

Bir kiracının üçüncü tarafla anlaşması, üçüncü tarafın hizmetinde tutulan Intune kişisel verilerini yönetir. Bu anlaşma ayrıca Intune’a üçüncü taraf hizmete veri iletme izni verir.  

Belirli üçüncü taraflarla paylaşılan veriler hakkında daha fazla bilgi için aşağıdaki makalelere bakın:
- [Intune’un Apple’a gönderdiği veriler](data-intune-sends-to-apple.md)
- [Intune’un Google’a gönderdiği veriler](data-intune-sends-to-google.md)
- [Apple’ın Intune’a gönderdiği veriler](data-apple-sends-to-intune.md)
- [Google’ın Intune’a gönderdiği veriler](data-google-sends-to-intune.md)
- [Jamf Pro’dan Intune’a paylaşılan bilgiler](conditional-access-integrate-jamf.md#information-shared-from-jamf-pro-to-intune)

### <a name="system-center-configuration-manager-data-sharing"></a>System Center Configuration Manager veri paylaşımı

Microsoft Intune, System Center Configuration Manager ile herhangi bir veri paylaşmaz. Microsoft Intune doğrudan müşteri tarafından dağıtılan, yönetilen ve işletilen bir şirket içi üründür. Configuration Manager tarafından toplanan tanılama ve kullanım verileri yalnızca gelecek sürümlerin yükleme deneyimini, kalitesini ve güvenliğini geliştirmek için kullanılır.

Daha fazla bilgi edinmek için bkz. [SCCM için tanılama ve kullanım verileri](https://docs.microsoft.com/en-us/sccm/core/plan-design/diagnostics/diagnostics-and-usage-data.md). 


## <a name="next-steps"></a>Sonraki adımlar

Intune’da kişisel verileri [görüntülemeyi ve düzeltmeyi](privacy-data-view-correct.md) öğrenin.