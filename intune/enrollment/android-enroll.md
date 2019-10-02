---
title: Intune’da Android cihazları kaydetme
titleSuffix: Microsoft Intune
description: Intune’da Android cihazları kaydetmeyi öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 7/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4a9de31ce7a08edcb7dddc6a65a061c1883021e4
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71730081"
---
# <a name="enroll-android-devices"></a>Android cihazlarını kaydetme

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bir Intune Yöneticisi olarak, Android cihazlarını aşağıdaki yollarla kaydedebilirsiniz:
- Android Enterprise (kullanıcılara en güncel ve güvenli özellikleri sağlayan bir kayıt seçenekleri kümesi sunar):
    - [**Android kurumsal iş profili**](android-work-profile-enroll.md): kişisel cihazlara kurumsal verilere erişim izni verildi. Yöneticiler iş hesaplarını, uygulamaları ve verileri yönetebilir. Cihazdaki kişisel veriler iş verilerinden ayrı tutulur ve yöneticiler kişisel ayarları veya verileri denetlemez. 
    - [**Android kurumsal adanmış**](android-kiosk-enroll.md): dijital imza, Bilet yazdırma veya stok yönetimi gibi şirkete ait, tek kullanım cihazları için. Yöneticiler bir cihazın kullanımını sınırlı sayıda uygulama ve web bağlantısına indirger. Ayrıca kullanıcılar başka uygulama ekleyemez veya farklı eylemler gerçekleştiremez.
    - [**Android kurumsal tam olarak yönetilen**](android-fully-managed-enroll.md): şirkete ait, tek kullanıcı cihazları için özel olarak çalışır ve kişisel kullanım için kullanılır. Yöneticiler cihazın tamamını yönetebilir ve ilke denetimlerini iş profilleri için kullanılamaz hale getirebilirsiniz. 
- Samsung KNOX Standard cihazlar ve [Zeköşeli cihazlar](../configuration/android-zebra-mx-overview.md)dahil olmak üzere [**Android Cihaz Yöneticisi**](android-enroll-device-administrator.md). 

## <a name="prerequisites"></a>Önkoşullar

Mobil cihazların yönetimine hazırlık olarak, **Microsoft Intune**’a mobil cihaz yönetimi (MDM) yetkilisi ayarlamanız gerekir. Yönergeler için bkz. [MDM yetkilisini ayarlama](../fundamentals/mdm-authority-set.md). Bu öğeyi yalnızca mobil cihaz yönetimi için Intune’u ilk defa kurduğunuzda ayarlayabilirsiniz.

Zeköşeli teknolojiler tarafından üretilen cihazlarda, belirli bir cihazın özelliklerine bağlı olarak Şirket Portalı ek izinler vermeniz gerekebilir. [Zeköşeli cihazlarda Mobility uzantılarında](../configuration/android-zebra-mx-overview.md) daha fazla ayrıntı vardır.

Samsung KNOX Standard cihazlarında [daha fazla önkoşul](android-samsung-knox-mobile-enroll.md)vardır.

## <a name="next-steps"></a>Sonraki adımlar

- [Android kurumsal iş profili kayıtlarını ayarlama](android-work-profile-enroll.md)
- [Android kurumsal adanmış cihaz kayıtlarını ayarlama](android-kiosk-enroll.md)
- [Android kurumsal tam olarak yönetilen kayıtları ayarlama](android-fully-managed-enroll.md)
- [Android Cihaz Yöneticisi kaydını ayarlama](android-enroll-device-administrator.md)

