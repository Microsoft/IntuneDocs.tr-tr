---
title: Görünüm ve doğru kişisel veriler
description: Kişisel verileri görüntülemeyi ve düzeltmeyi öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1ba77bc7-505e-4eca-a49e-dcdaa75d0043
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2d0567d605afeb37812d495cc6192100ab76444f
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57399120"
---
# <a name="view-and-correct-personal-data"></a>Görünüm ve doğru kişisel veriler

Intune yöneticileri, erişim izinlerine bağlı olarak bazı kişisel verileri görüntüleyebilir ancak yalnızca son kullanıcılar kendi cihazlarındaki kişisel verileri değiştirebilir.

[!INCLUDE [GDPR-related guidance](./includes/gdpr-dsr-and-stp-note.md)]


## <a name="view-personal-data"></a>Kişisel verileri görüntüleme

Yöneticiler, Intune kullanıcı arabirimindeki çeşitli dikey pencerelerde son kullanıcı kişisel bilgilerini görebilir. Aşağıdaki makaleler, yöneticilerin hangi bilgileri görüp hangilerini göremediğini açıklar:
- Intune’daki [Cihaz ayrıntılarını görme](device-inventory.md) makalesi, bir son kullanıcı cihazındaki ayrıntıları nasıl gözden geçirebileceğinizi açıklar.
- [Uygulama bilgilerini ve atamalarını izleme](apps-monitor.md) makalesi, bir son kullanıcı cihazında yüklü uygulamalar hakkında ayrıntıları nasıl görebileceğinizi açıklar.
- [Cihazımı kaydettiğimde şirketim hangi bilgileri görebilir?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune) makalesi, son kullanıcılara şirketlerinin görebileceği ve göremeyeceği verilerin bir listesini sağlar. Kullanıcılara ne tür veriler toplayacağınızı ve bunları neden toplayacağınızı açıkça anlatmak en iyi yöntemdir. Bu şeffaflığın sağlanması için bu makale ilk adımınız olabilir.

### <a name="who-can-view-the-data"></a>Verileri kim görebilir?

Microsoft, müşteri verilerine erişimi yönetmek için katı denetimler kullanır; önemli görevleri tamamlamaya yetecek en düşük erişim düzeyini verip ihtiyaç kalmadığında erişimi iptal eder. 

Rol tabanlı yönetim denetimini (RBAC) kullanarak son kullanıcının kişisel verilerine erişimi güvenlik altına alabilir ve denetleyebilirsiniz. Daha fazla bilgi için bkz. [Microsoft Intune ile RBAC](role-based-access-control.md).

Online Services Hükümleri ve [Microsoft Online Services Gizlilik Bildirimi](http://go.microsoft.com/fwlink/p/?linkid=131004&clcid=0x409)’ni okuyarak Microsoft veri uygulamaları hakkında daha fazla bilgi edinebilirsiniz. 

## <a name="correct-end-user-personal-data"></a>Son kullanıcı kişisel bilgilerini düzeltme

Yöneticiler, cihaza veya uygulamaya özgü bilgileri güncelleştiremez. Bir son kullanıcı herhangi bir kişisel veriyi düzeltmek istiyorsa (örneğin cihaz adı), bunu doğrudan kendi cihazında yapmalıdır. Bu tür değişiklikler, kullanıcı Intune’a bağlandığı zaman eşitlenir.


## <a name="next-steps"></a>Sonraki adımlar

Intune’da kişisel verileri [denetleme, dışarı aktarma ve silme](privacy-data-audit-export-delete.md) hakkında bilgi edinin.
