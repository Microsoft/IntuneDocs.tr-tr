---
title: Veri Ambarı Kullanıcı Varlığı Zaman Çizelgesi
titleSuffix: Microsoft Intune
description: Nasıl Microsoft Intune veri ambarı bir zaman çizelgesinde kullanıcıları temsil öğrenin.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/26/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 363D148E-688F-4830-B6DE-AB4FE3648817
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: cfa1df8053301b92c04d92f8c48d2c6c34e30129
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61507622"
---
# <a name="user-lifetime-representation-in-the-microsoft-intune-data-warehouse"></a>Microsoft Intune Veri Ambarı’nda kullanıcı ömrü gösterimi

Zaman tabanlı eğilimler hakkındaki soruları cevaplamak için Intune Veri Ambarı'nda saklanan veri anlık görüntülerini kullanabilirsiniz. Örneğin, bir ay boyunca eklenen kullanıcı sayısına bakabilirsiniz. Ayrıca, sistemden kaldırılan kullanıcıların sayısını da sorabilirsiniz.

Veri ambarı, bu tür öngörüleri sunmak için geçmiş bilgilerini depolar. Veri ambarı, bir varlığın ömrünü izleyebilir. Ambar; bir varlık oluşturulduğunda, varlığın durumu değiştiğinde ve varlık silindiğinde bunları kaydeder. Nicel ölçümlerin günlük anlık görüntüleriyle yakalanan geçmişle bir gün ile bir önceki gün karşılaştırabilir, vb.

Varlık ömürleriyle çalışmak, varlıklarınız değişir durumda olduğundan kafa karıştırıcı olabilir. Yani, 30. günde bir anlık görüntüye bakarsanız, bir kullanıcı kaydı veride etkin durumda bulunmayabilir demektir. 28-29. Günlerde varlık kaydı aktif olarak var olabilir. Ve ardında 28. günden önce, kullanıcı hiç var olmadı.

Bir varlığın ömrünü incelerseniz bu senaryoyu daha iyi anlayabilirsiniz.

**John Smith** adlı bir kullanıcıya 06/01/2017 tarihinde bir lisans atandığını ve ardından **Kullanıcı** tablosunun aşağıdaki girdiye sahip olacağını varsayalım: 
 
| displayName | IsDeleted | StartDateInclusiveUTC | EndDateExclusiveUTC | IsCurrent 
| -- | -- | -- | -- | -- |
| John Smith | FALSE | 06/01/2017 | 12/31/9999 | TRUE
 
John Smith, 25/07/2017 tarihinde lisansından vazgeçti. **Kullanıcı** tablosunda aşağıdaki girdiler bulunur. Var olan kayıtlardaki değişiklikler `marked`. 

| displayName | IsDeleted | StartDateInclusiveUTC | EndDateExclusiveUTC | IsCurrent 
| -- | -- | -- | -- | -- |
| John Smith | FALSE | 06/01/2017 | `07/26/2017` | `FALSE` 
| John Smith | TRUE | 07/26/2017 | 12/31/9999 | TRUE 

İlk satır, John Smith'in 06.01.2017 - 07/25/2017 arasındaki Intune'da var olduğunu belirtir. İkinci kayıt, kullanıcının 07/25/2017 tarihinde silindiği ve artık Intune'de bulunmadığını belirtir.

Şimdi, John Smith'in 08/31/2017 tarihinde atanmış yeni bir lisans aldığını varsayalım, ardından Kullanıcı tablosunda aşağıdaki girdiler bulunur:
 
| displayName | IsDeleted | StartDateInclusiveUTC | EndDateExclusiveUTC | IsCurrent 
| -- | -- | -- | -- | -- |
| John Smith | FALSE | 06/01/2017 | 07/26/2017 | FALSE 
| John Smith | TRUE | 07/26/2017 | `08/31/2017` | `FALSE` 
| John Smith | FALSE | 08/31/2017 | 12/31/9999 | TRUE 
 
Tüm kullanıcıların mevcut durumunu görmek isteyen bir kişi, `IsCurrent = TRUE`de bir filtre uygulamak ister. 
 
Yalnızca var olan kullanıcıları görmek isteyen bir kişi `IsCurrent = TRUE AND IsDeleted = FALSE`de bir filtre uygulamak ister.

## <a name="dimension-tables-in-the-entity-lifetime"></a>Varlık ömründe boyut tabloları

Intune durum değişikliklerinin geçmişini varlıklarda saklamak için kayıtları silmez. Bunun yerine, kaydı silinmiş olarak işaretler. Buna geçici silme denir. Boyut tabloları, kayıtların ömrünü izlemek için çeşitli meta veri sütunları kullanır. 

En yaygın kullanılan meta veri sütunları şunlardır: 

| Meta Veri Özellik Adı  | Değerlerin Yorumu |
|--|--|
| IsDeleted | Varlığın Intune'da silinmiş olup olmadığını belirtir. |
| StartDateInclusiveUTC  | UTC tarihi, varlığın Intune Veri Ambarı'na yüklendiği tarihtir. Varlık, Intune Veri Ambarı'na alınmadan önce oluşturulmuş olabilir. |
| DeletedDateUTC  | UTC tarihi, varlığın Intune'da silindiği tarihtir. |  

**RowLastModifiedDateTimeUTC** gibi önek **Satır** ile başlayan herhangi bir meta veri sütunu, bir kayıt Intune Veri Ambarı'nda ne zaman oluşturulduğunu veya değiştirildiğini belirtir. Ambar, Intune'daki verilerden aşağı akıştadır. Bu değerin, Intune'da varlığın ömrü ile hiçbir ilişkisi yoktur.  
 
Şu anda var olan boyut varlıklarını görmek isteyen herhangi bir kişi, **IsDeleted = FALSE** olan bir filtre uygulamak isteyecektir.

## <a name="next-steps"></a>Sonraki adımlar

 - **Geçerli Kullanıcı** varlığı hakkında daha fazla bilgi edinmek için bkz. [Geçerli kullanıcı varlığı için başvuru](reports-ref-current-user.md).
 - **Kullanıcı** varlığı hakkında daha fazla bilgi edinmek için bkz. [Kullanıcı varlığı için başvuru](reports-ref-user.md).
