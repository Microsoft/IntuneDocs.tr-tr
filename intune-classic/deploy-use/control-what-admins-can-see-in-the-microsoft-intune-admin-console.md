---
title: "Konsol görünümlerini yönetici rolleri için özelleştirme | Microsoft Docs"
description: "Intune yönetim konsolu görünümünü filtreleyerek, yöneticilerinize yalnızca rolleri için gereken öğelerin gösterilmesini sağlamanıza yardımcı olmak için bu konuyu kullanın."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0783eaa-67dc-410e-9e80-4d3aa72f36d8
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e7d1760a10e63233fe7cc7f6fd57a68c5283647c
ms.openlocfilehash: ee35fb2c8e39af099fb061211ea1fdf767230217
ms.lasthandoff: 12/30/2016


---

# <a name="customize-intune-console-views-according-to-admin-roles"></a>Intune konsol görünümlerini yönetici rollerine göre özelleştirme

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Yöneticilerinizin yalnızca rolleri için görmeleri gereken öğeleri görmelerini sağlamak için Microsoft Intune yönetim konsolu görünümünü filtreleyebilirsiniz. Örneğin, yalnızca yönetici konsolu kullanıcılarının kötü amaçlı yazılım tanımlarını güncelleştirebilmesine veya cihazlardaki şifreyi sıfırlamasına izin verebilirsiniz. Bunu, belirli kullanıcılara atadığınız, önceden ayarlanmış **belirtimler** kullanılarak yaparsınız. Bu kullanıcılar yönetim konsoluna eriştiklerinde, yalnızca belirtimlerine özgü öğeleri görebilir.

## <a name="to-create-a-custom-view"></a>Özel bir görünüm oluşturmak için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **Yönetim** &gt; **Hizmet Yöneticileri**’ni seçin.

2.  Hizmet yöneticileri listesinden, belirtimini değiştirmek istediğiniz kullanıcıyı seçin ve sonra da **Erişimi Yönet**’i seçin.

3.  **Erişimi Yönet** iletişim kutusunda, seçilen kullanıcıya vermek istediğiniz erişim düzeyini seçin. Şunlar arasından seçim yapabilirsiniz:

    -   **Tam erişim**
    -   **Salt okunur erişim**
    -   **Yardım Masası - Gruplar düğümü**

    Tam erişim ve salt okunur erişimin anlamı kolayca anlaşılır. <!--- **Helpdesk - Groups Node** allows users to choose from one of the following designations that provide custom levels of access to the Intune admin console:--->

    **Yardım Masası - Gruplar Düğümü**, yöneticinin neler görebileceğini ve yapabileceğini şu şekilde kısıtlar:

    -   Kullanıcı ve cihazların listelerini görme. Yönetici, görünümü değiştirmek için filtreleri kullanamaz. Bununla birlikte, yöneticinin görebileceklerini değiştirmek için grup filtresini kullanabilirsiniz. Daha fazla bilgi için bkz. [Microsoft Intune'la kullanıcı ve cihazları yönetmek için grupları kullanma](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

    -   Kullanıcı ve cihaz listesini yazdırma.

    -   Kullanıcı ve cihaz listesini dışarı aktarma.

    -   Kullanıcı veya cihazın özelliklerini görüntüleme.

    -   Aşağıdaki uzak görevleri gerçekleştirin:

        -   Kötü amaçlı yazılım taraması çalıştırma

        -   Hızlı bir kötü amaçlı yazılım taraması çalıştırma

        -   Bilgisayarı yeniden başlatma

        -   Kötü amaçlı yazılım tanımlarını güncelleştirme

        -   İlkeleri yenileme

        -   Envanter yenileme

        -   Cihazı uzaktan kilitleme

        -   Geçiş kodu sıfırlama

Yapılandırdığınız yöneticiye, Intune yönetim konsolunu bir sonraki açısında kendisine onun için belirttiğiniz erişim düzeyi verilir.

