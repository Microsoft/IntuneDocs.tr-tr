---
title: "Uygulamaları dağıtma | Microsoft Intune"
description: "Bu konu başlığı altında, Intune’la uygulamaları dağıtmaya başlamadan önce anlamanız gereken kavramlar açıklanır."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ad5ea85c-aa2e-4110-a184-172cd0b8f270
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c4a760b6362356a6bafa8b6acc69299647a5e0f3
ms.openlocfilehash: 377597aabc03c020060e2851c6fc25e0c780ea51


---

# Microsoft Intune ile uygulamaları dağıtma

Bu konu başlığı altında, Microsoft Intune’la uygulamaları dağıtmaya başlamadan önce anlamanız gereken bazı kavramlar açıklanır.


## Uygulama dağıtım eylemleri
Uygulamaları dağıtırken aşağıdaki dağıtım eylemlerden birini seçebilirsiniz:

-   **Gerekli yükleme** – Uygulama herhangi bir kullanıcı müdahalesi gerekmeden cihaza yüklenir.

    > [!TIP]
    > Denetimli modda olmayan iOS cihazları ve tüm Android cihazları için kullanıcı yükleme öncesinde uygulama teklifini kabul etmelidir.
    >
    >  Bir kullanıcı gerekli yükleme olarak dağıttığınız bir uygulamayı kaldırırsa, Intune genelde yedi günde bir gerçekleştirilen bir sonraki envanter döngüsünden sonra uygulamayı otomatik olarak yeniden yükler.

-   **Kullanılabilir yükleme** – Uygulama şirket portalında gösterilir ve kullanıcılar tarafından isteğe bağlı olarak yüklenebilir.

-   **Kaldır** – Uygulama cihazdan kaldırılır.

-   **Geçerli değil** – Uygulama şirket portalında gösterilmez ve herhangi bir cihaza yüklenmez.

#### Her yükleme türünde hangi dağıtım eylemlerinin kullanılabildiğini anlama

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

## Dağıtım çakışmaları
Bir cihaz tarafından aynı dağıtım eylemiyle iki dağıtım alındığında aşağıdaki kurallar geçerli olur:

-   Cihaz grubuna yapılan dağıtımlar, kullanıcı grubuna yapılan dağıtımlara göre önceliklidir. Ancak bir uygulama **Kullanılabilir** dağıtım eylemiyle bir kullanıcı grubuna dağıtılır ve aynı uygulama aynı zamanda **Geçerli Değil** dağıtım eylemiyle bir cihaz grubuna dağıtılırsa, uygulama şirket portalında kullanıcılar tarafından yüklenebilir.

-   Yükleme eylemi, kaldırma eylemine göre önceliklidir.

-   Cihaz tarafından hem gerekli yükleme hem de kullanılabilir yükleme alınırsa, eylemler birleştirilir. Başka bir deyişle, kullanıcı, gerekli yüklemeye başlamadan önce şirket portalından kullanılabilir uygulamayı yükleyebilir.


## Sonraki adımlar

[Microsoft Intune'da uygulamaları dağıtmayı](deploy-apps-in-microsoft-intune.md) öğrenin.



<!--HONumber=Jul16_HO4-->


