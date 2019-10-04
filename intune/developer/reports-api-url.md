---
title: Intune veri ambarı API uç noktası
titleSuffix: Microsoft Intune
description: Bu başvuru konusu Microsoft Intune veri ambarı API 'SI yapısını açıklar. Filtre örnekleri verilmiştir.
keywords: Intune veri ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: f73e80fed5de74bc074e26502270467b7d846e5c
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940157"
---
# <a name="intune-data-warehouse-api-endpoint"></a>Intune veri ambarı API uç noktası

Intune veri ambarı API 'sini, belirli rol tabanlı erişim denetimlerine ve Azure AD kimlik bilgilerine sahip bir hesapla kullanabilirsiniz. Daha sonra, OAuth 2,0 kullanarak REST istemcinizi Azure AD ile yetkilendirirsiniz. Son olarak, veri ambarı kaynağını çağırmak için anlamlı bir URL oluşturacak.

[!INCLUDE [reports-credential-reqs](../includes/reports-credential-reqs.md)]

## <a name="authorization"></a>Yetkilendirme

Azure Active Directory (Azure AD), Azure AD kiracınızdaki Web uygulamalarına ve Web API 'Lerine erişim yetkisi verme olanağı sağlamak için OAuth 2,0 kullanır. Bu kılavuz dilden bağımsızdır ve herhangi bir açık kaynak kitaplığı kullanmadan HTTP iletilerinin nasıl gönderileceğini ve alınacağını açıklar. OAuth 2,0 yetkilendirme kodu akışı, OAuth 2,0 belirtiminin [4,1 bölümünde](https://tools.ietf.org/html/rfc6749#section-4.1) açıklanmaktadır.

Daha fazla bilgi için bkz. [OAuth 2,0 ve Azure Active Directory kullanarak Web uygulamalarına erişim yetkisi verme](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code).

## <a name="api-url-structure"></a>API URL yapısı

Veri ambarı API uç noktaları, her bir küme için varlıkları okur. API, **Get** http fiilini ve sorgu seçeneklerinin bir alt kümesini destekler.

Intune URL 'SI aşağıdaki biçimi kullanır:  
`https://fef.{location}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{entity-collection}?api-version={api-version}`

> [!NOTE]
> Yukarıdaki URL 'de, aşağıdaki tabloda belirtilen ayrıntılara göre `{location}`, `{entity-collection}` ve `{api-version}` ' yi değiştirin.

URL aşağıdaki öğeleri içerir:

| Öğe | Örnek | Açıklama |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| konum | msua06 | Temel URL, Azure portal veri ambarı API dikey penceresi görüntüleyerek bulunabilir. |
| varlık koleksiyonu | Devicepropertygeçmişleri | OData varlık koleksiyonunun adı. Veri modelindeki koleksiyonlar ve varlıklar hakkında daha fazla bilgi için bkz. [veri modeli](reports-ref-data-model.md). |
| api sürümü | Beta | Sürüm, erişim için API 'nin sürümüdür. Daha fazla bilgi için bkz. [Sürüm](reports-api-url.md#api-version-information). |
| maxhistorydays | 7 | Seçim Alınacak geçmişin en fazla gün sayısı. Bu parametre herhangi bir koleksiyona sağlanabilir, ancak yalnızca anahtar özelliğinin bir parçası olarak `dateKey` içeren koleksiyonlar için geçerli olur. Daha fazla bilgi için bkz. [DateKey Range filtreleri](reports-api-url.md#datekey-range-filters) . |

## <a name="api-version-information"></a>API sürüm bilgileri

Artık @ no__t-0 sorgu parametresini ayarlayarak Intune veri ambarının v 1.0 sürümünü kullanabilirsiniz. Veri ambarındaki koleksiyonlara yapılan güncelleştirmelerin doğası gereği, mevcut senaryoları bozmayın.

Beta sürümünü kullanarak veri ambarının en son işlevlerini deneyebilirsiniz. Beta sürümünü kullanmak için URL 'nizin @ no__t-0 sorgu parametresini içermesi gerekir. Beta sürümü, desteklenen bir hizmet olarak genel kullanıma sunulmadan önce özellikler sunar. Intune yeni özellikler eklerse, beta sürümü davranış ve veri sözleşmelerini değiştirebilir. Beta sürümüne bağımlı olan özel kod veya raporlama araçları, devam eden güncelleştirmelerle kesintiye uğraşmayabilir.

## <a name="odata-query-options"></a>OData sorgu seçenekleri

Geçerli sürüm şu OData sorgu parametrelerini destekliyor: `$filter`, `$select`, `$skip,` ve `$top`. @No__t-0 ' da, sütunlar geçerliyse yalnızca `DateKey` veya `RowLastModifiedDateTimeUTC` desteklenebilir ve diğer özellikler hatalı bir istek tetikleyecektir.

## <a name="datekey-range-filters"></a>DateKey Aralık filtreleri

`DateKey` Aralık filtresi, anahtar özelliği olarak `dateKey` olan bazı koleksiyonlar için indirilecek veri miktarını sınırlamak için kullanılabilir. @No__t-0 filtresi, aşağıdaki `$filter` sorgu parametresini sağlayarak hizmet performansını iyileştirmek için kullanılabilir:

1. `$filter` ' de tek başına @no__t, `lt/le/eq/ge/gt` işleçlerini destekleyerek ve bir başlangıç tarihi ve/veya bitiş tarihi ile eşleştirilebileceği `and` Logic operator ile birleştirme.
2. `maxhistorydays` özel sorgu seçeneği olarak sağlanır.<br>

## <a name="filter-examples"></a>Filtre örnekleri

> [!NOTE]
> Filtre örnekleri bugün 2/21/2019 olduğunu varsayar.

|                             Filtrele                             |           Performans Iyileştirmesi           |                                          Açıklama                                          |
|:--------------------------------------------------------------:|:--------------------------------------------:|:---------------------------------------------------------------------------------------------:|
|    `maxhistorydays=7`                                            |    Tam                                      |    20180214 ile 20180221 arasında `DateKey` ile veri döndürün.                                     |
|    `$filter=DateKey eq 20180214`                                 |    Tam                                      |    @No__t-0 ile 20180214 arasında bir veri döndürün.                                                    |
|    `$filter=DateKey ge 20180214 and DateKey lt 20180221`         |    Tam                                      |    20180214 ile 20180220 arasında `DateKey` ile veri döndürün.                                     |
|    `maxhistorydays=7&$filter=DateKey eq 20180214`                |    Tam                                      |    @No__t-0 ile 20180214 arasında bir veri döndürün. `maxhistorydays` yok sayılır.                            |
|    `$filter=RowLastModifiedDateTimeUTC ge 2018-02-21T23:18:51.3277273Z`                                |    Tam                                       |    @No__t-0 olan dönüş verileri `2018-02-21T23:18:51.3277273Z` ' den büyük veya buna eşit                             |
