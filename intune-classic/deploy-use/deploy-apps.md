---
title: "Uygulama dağıtma"
description: "Bu konu başlığı altında, Intune’la uygulamaları dağıtmaya başlamadan önce anlamanız gereken kavramlar açıklanır."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ad5ea85c-aa2e-4110-a184-172cd0b8f270
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 13c4046ed431dc25bda9a2facc59dbcb6d3e5ab5
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="deploy-apps-with-microsoft-intune"></a>Microsoft Intune ile uygulamaları dağıtma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bu konu başlığı altında, Microsoft Intune’la uygulamaları dağıtmaya başlamadan önce anlamanız gereken bazı kavramlar açıklanır.


## <a name="app-deployment-actions"></a>Uygulama dağıtım eylemleri
Uygulamaları dağıtırken aşağıdaki dağıtım eylemlerden birini seçebilirsiniz:

-   **Gerekli yükleme** – Uygulama herhangi bir kullanıcı müdahalesi gerekmeden cihaza yüklenir.

    > [!TIP]
    > Denetimli modda olmayan iOS cihazları ve tüm Android cihazları için kullanıcı yükleme öncesinde uygulama teklifini kabul etmelidir.
    >
    >  Bir kullanıcı gerekli yükleme olarak dağıttığınız bir uygulamayı kaldırırsa, Intune genelde yedi günde bir gerçekleştirilen bir sonraki envanter döngüsünden sonra uygulamayı otomatik olarak yeniden yükler.

-   **Kullanılabilir yükleme** – Uygulama şirket portalında gösterilir ve kullanıcılar tarafından isteğe bağlı olarak yüklenebilir.

-   **Kaldır** – Uygulama cihazdan kaldırılır.

-   **Geçerli değil** – Uygulama şirket portalında gösterilmez ve herhangi bir cihaza yüklenmez.

#### <a name="understand-which-deployment-actions-are-available-for-each-installer-type"></a>Her yükleme türünde hangi dağıtım eylemlerinin kullanılabildiğini anlama

|Yükleyici türü|Zorunlu yükleme|Kullanılabilir yükleme|Kaldır|Geçerli değil|
|------------------|--------------------|---------------------|-------------|------------------|
|Windows uygulama paketi (bir kullanıcı grubuna dağıtılır)|Evet|Evet|Evet|Evet|
|Windows uygulama paketi (bir cihaz grubuna dağıtılır)|Evet|Hayır|Evet|Evet|
|Mobil cihazlar için uygulama paketi (bir kullanıcı grubuna dağıtılır)|Evet|Evet|Evet|Evet|
|Mobil cihazlar için uygulama paketi (bir cihaz grubuna dağıtılır)|Evet|Hayır|Evet|Evet|
|Windows Installer (bir kullanıcı grubuna dağıtılır)|Hayır|Evet|Hayır|Evet|
|Windows Installer (bir cihaz grubuna dağıtılır)|Evet|Hayır|Evet|Evet|
|Dış bağlantı (bir kullanıcı grubuna dağıtılır)|Hayır|Evet|Hayır|Evet|
|Dış bağlantı (bir cihaz grubuna dağıtılır)|Hayır|Hayır|Hayır|Hayır|
|Uygulama mağazasından yönetilen iOS uygulaması (bir kullanıcı grubuna dağıtılır)|Evet|Evet|Evet|Evet|
|Uygulama mağazasından yönetilen iOS uygulaması (bir cihaz grubuna dağıtılır)|Evet|Hayır|Evet|Evet|
> [!TIP]
> Uygulamaları dağıtırken hem kullanıcı hem de cihaz gruplarını seçerseniz, uygulamayı yalnızca **Kullanılabilir yükleme** olarak dağıtabilirsiniz.

## <a name="deployment-conflicts"></a>Dağıtım çakışmaları
Bir cihaz tarafından aynı dağıtım eylemiyle iki dağıtım alındığında aşağıdaki kurallar geçerli olur:

-   Cihaz grubuna yapılan dağıtımlar, kullanıcı grubuna yapılan dağıtımlara göre önceliklidir. Ancak bir uygulama **Kullanılabilir** dağıtım eylemiyle bir kullanıcı grubuna dağıtılır ve aynı uygulama aynı zamanda **Geçerli Değil** dağıtım eylemiyle bir cihaz grubuna dağıtılırsa, uygulama şirket portalında kullanıcılar tarafından yüklenebilir.

-   Yükleme eylemi, kaldırma eylemine göre önceliklidir.

-   Cihaz tarafından hem gerekli yükleme hem de kullanılabilir yükleme alınırsa, eylemler birleştirilir. Başka bir deyişle, kullanıcı, gerekli yüklemeye başlamadan önce şirket portalından kullanılabilir uygulamayı yükleyebilir.


## <a name="next-steps"></a>Sonraki adımlar

[Microsoft Intune'da uygulamaları dağıtmayı](deploy-apps-in-microsoft-intune.md) öğrenin.
