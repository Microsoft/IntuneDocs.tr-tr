---
title: Windows bilgisayarlarını koruma ilkeleri
titleSuffix: Microsoft Intune
description: Intune istemci yazılımı tarafından yönetilen Windows bilgisayarlarının güvenliğini sağlamaya yardımcı olmak için bu ilkeleri kullanın.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 02/28/2019
ms.topic: archived
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: d081f466-45dd-41d1-ab25-6d974c72a52a
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: 306c67e2744c38cfc8214d1c8dee2732cd0bd1ce
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72505006"
---
# <a name="use-policies-to-help-protect-windows-pcs-that-run-the-intune-client-software"></a>Intune istemci yazılımını çalıştıran Windows bilgisayarlarını korumaya yardımcı olmak için ilkeleri kullanma

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Microsoft Intune, [Intune istemci yazılımı](../manage-windows-pcs-with-microsoft-intune.md) tarafından yönetilen Windows bilgisayarlarının güvenliğini sağlamaya yardımcı olmak için kullanabileceğiniz üç ilke sunar.


## <a name="software-updates"></a>Yazılım güncelleştirmeleri

Intune, Microsoft’tan veya diğer şirketlerden önemli yazılım güncelleştirmeleri kullanıma sunulduğunda bunu size bildirerek, [yönettiğiniz Windows bilgisayarlarının güncelliğini korumanızı](../keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) kolaylaştırır. Bu güncelleştirmeleri onaylayabilir veya reddedebilirsiniz. Onaylanan güncelleştirmeler tüm uygun bilgisayarlara otomatik olarak yüklenir.

## <a name="windows-firewall"></a>Windows Güvenlik Duvarı

Windows Güvenlik Duvarı, bilgisayar korsanlarını, kötü amaçlı yazılımları ve diğer tehditleri Windows bilgisayarlarından uzak tutmaya yardımcı olur. Intune sayesinde, yönettiğiniz tüm bilgisayarlarda [Windows Güvenlik Duvarı için ayar ve özellikleri yönetme](../help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) imkanına sahip olursunuz.

## <a name="endpoint-protection"></a>Uç Nokta Koruma

Bir BT yöneticisi olarak en önemli önceliklerinizden biri, [yönettiğiniz Windows bilgisayarlarına kötü amaçlı yazılım ve virüs bulaşmasını engellemektir](../help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md). Intune, Endpoint Protection ile tümleşik çalışarak kötü amaçlı yazılım tehditlerine karşı gerçek zamanlı koruma sağlar, kötü amaçlı yazılım tanımlarını güncel tutar ve bilgisayarları otomatik olarak tarar. Endpoint Protection, kötü amaçlı yazılım saldırılarını yönetmek ve izlemek için yardımcı araçlar da sağlar.

## <a name="see-also"></a>Ayrıca bkz:

[Cihaz ilkeleri ve profillerle ilgili yaygın sorular, sorunlar ve çözümler](../configuration/device-profile-troubleshoot.md)
