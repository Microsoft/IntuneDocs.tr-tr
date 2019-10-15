---
title: Kişisel verileri görüntüleme ve düzeltme
titleSuffix: Microsoft Intune
description: Kişisel verileri görüntüleme ve düzeltme hakkında bilgi edinin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1ba77bc7-505e-4eca-a49e-dcdaa75d0043
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9b6ca291f55511be9e88b0ff898d9383691542bf
ms.sourcegitcommit: a2654f3642b43b29ab0e1cbb2dfa2b56aae18d0e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/14/2019
ms.locfileid: "72310896"
---
# <a name="view-and-correct-personal-data"></a>Kişisel verileri görüntüleme ve düzeltme

Intune yöneticileri, bazı kişisel verileri erişim izinlerine göre görüntüleyebilir, ancak yalnızca son kullanıcılar cihazının kişisel verilerini değiştirebilir.

[!INCLUDE [GDPR-related guidance](../includes/gdpr-dsr-and-stp-note.md)]


## <a name="view-personal-data"></a>Kişisel verileri görüntüle

Yöneticiler, Son Kullanıcı kişisel bilgilerini Intune kullanıcı arabirimindeki çeşitli dikey pencerelerde görebilir. Aşağıdaki makalelerde, yöneticilerin hangi bilgileri yaptığını ve erişimi yok açıklanmaktadır:
- Intune 'da [cihaz ayrıntılarına bakın](../remote-actions/device-inventory.md) son kullanıcının cihazına ilişkin ayrıntıları nasıl gözden geçirebileceğinizi açıklar.
- [Uygulama bilgilerini ve atamalarını izleme,](../apps/apps-monitor.md) son kullanıcının cihazında yüklü olan uygulamalarla ilgili ayrıntıları nasıl görebileceğinizi açıklar.
- [Cihazımı kaydettiğimde şirketim hangi bilgileri görebilir? makalesi](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune) , son kullanıcılara, şirketlerinin görebileceği ve görebilecekleri verilerin bir listesini sağlar. Kullanıcılarınıza ne tür verileri topladığınızı ve neden topladığınızı açıkça söylemek en iyisidir. Bu makale, saydamlığın ilk adımı olabilir.

### <a name="who-can-view-the-data"></a>Verileri kim görebilir?

Microsoft, müşteri verilerine erişimi yönetmek için katı denetimleri kullanır, anahtar görevlerinin tamamı için gereken en düşük erişim düzeyini ve artık gerekli olmadığında erişimi iptal eder. 

Rol tabanlı yönetim denetimi (RBAC) kullanarak Son Kullanıcı kişisel verilerine erişimi güvenli hale getirebilirsiniz ve denetleyebilirsiniz. Daha fazla bilgi için bkz. [Microsoft Intune Ile RBAC](../fundamentals/role-based-access-control.md).

Çevrimiçi hizmet koşulları ve [Microsoft Online Services gizlilik bildirimi](https://go.microsoft.com/fwlink/p/?linkid=131004&clcid=0x409)' ni okuyarak Microsoft veri uygulamaları hakkında daha fazla bilgi edinebilirsiniz. 

## <a name="correct-end-user-personal-data"></a>Son Kullanıcı kişisel verilerini doğru

Yöneticiler cihaz veya uygulamaya özgü bilgileri güncelleştiremez. Bir son kullanıcı, kişisel verileri (Cihaz adı gibi) düzeltmek isterse, bunu doğrudan cihazlarından yapması gerekir. Bu değişiklikler, Intune 'a bir dahaki sefer bağlandıklarında eşitlenir.


## <a name="next-steps"></a>Sonraki adımlar

Intune 'da kişisel verileri [denetleme, dışarı aktarma veya silme](privacy-data-audit-export-delete.md) hakkında bilgi edinin.
