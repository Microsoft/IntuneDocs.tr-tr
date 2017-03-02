---
title: "Intune’da kayıt kısıtlamalarını ayarlama"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Intune’da platforma göre kaydı kısıtlama ve cihaz kayıt sınırı ayarlama. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 56996592febf0be5ab74b158a70404728fe17a4d
ms.lasthandoff: 02/18/2017

---

# <a name="set-enrollment-restrictions"></a>Kayıt kısıtlamalarını ayarlama 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Kaydolmasına izin vereceğiniz en fazla cihaz sayısını ve türünü ayarlayabilirsiniz. Kayıt Kısıtlamaları dikey penceresinde şunları ayarlayabilirsiniz:

- Kayıt izni olan platformlar ile Android ve iOS için kişisel olarak sahip olunan cihazların kayıt olmasını engelleyip engellememe.

- Bir kullanıcının kaydetme izni olduğu en fazla cihaz sayısı.

## <a name="set-device-type-restrictions"></a>Cihaz türü kısıtlamalarını ayarlama

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2. Intune dikey penceresinde, **Cihazları kaydet**’i seçtikten sonra **Kayıt Kısıtlamaları**’nı seçin.

3. **Cihaz Türü Kısıtlamaları**’nın altında, **Varsayılan**’ı seçin.

4. **Tüm Kullanıcılar** dikey penceresinde **Platformlar**’ı seçin.

5. Intune’a kaydedilmeye izinli platformlar için **İzin Ver**’i seçin. Kaydedilmesini engellemek istediğiniz platformlar için **Engelle**’yi seçin. Varsayılan ayarlarda **İzin Ver** olarak ayarlanan platformlar. 

    >[!NOTE]
    >Bu ayarlar, Intune yazılım istemcisini kullanan Windows kayıtlarına uygulanmaz veya bu kayıtları engellemez. Bu ayarlar yalnızca mobil cihaz yönetimini kullanan kayıtları etkiler. 

6. **Kaydet**’i seçin.

7. **Platform Yapılandırmaları**’nı seçin.

8. Kişisel olarak sahip olunan iOS ve Android cihazların kaydedilmesine **izin vermeyi** veya bunu **engellemeyi** seçin.

9. **Kaydet**’i seçin.

## <a name="set-device-limit-restrictions"></a>Cihaz sınırı kısıtlamalarını ayarlama

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2. Intune dikey penceresinde, **Cihazları kaydet**’i seçtikten sonra **Kayıt Kısıtlamaları**’nı seçin.

3. **Cihaz Sınırı Kısıtlamaları**’nın altında **Varsayılan**’ı seçin.

4. **Tüm Kullanıcılar** dikey penceresinde **Cihaz Sınırı**’nı seçin.

5. Bir kullanıcının kaydedebileceği en fazla cihaz sayısını seçin ve ardından **Kaydet**'i seçin.

