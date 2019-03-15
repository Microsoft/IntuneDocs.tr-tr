---
title: Intune Veri Ambarı API uç noktası
titlesuffix: Microsoft Intune
description: Bu başvuru konusunda Microsoft Intune veri ambarı API URL'si yapısını açıklar. Filtre örnekler verilmiştir.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/25/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: e0e56c2dd4e26c68a82d5cb9d902e4480e1b98c8
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57396497"
---
# <a name="intune-data-warehouse-api-endpoint"></a>Intune Veri Ambarı API uç noktası

Intune Veri Ambarı API’sini, belirli rol tabanlı erişim denetimlerine ve Azure AD kimlik bilgilerine sahip bir hesapla kullanabilirsiniz. Daha sonra REST istemcinizi, OAuth 2.0 kullanarak Azure AD’de yetkilendirirsiniz. Ve son olarak, veri ambarı kaynağı olarak kullanılacak anlamlı bir URL oluşturursunuz.

[!INCLUDE [reports-credential-reqs](./includes/reports-credential-reqs.md)]

## <a name="authorization"></a>Yetkilendirme

Azure Active Directory (Azure AD), OAuth 2.0’ı kullanarak Azure AD kiracınızdaki web uygulamalarına ve web API’lerine erişim yetkisi vermenize olanak tanır. Bu kılavuz dilden bağımsızdır ve açık kaynak kitaplıklarının hiçbirini kullanmadan nasıl HTTP iletileri gönderip alacağınızı açıklar. OAuth 2.0 yetkilendirme kod akışı, OAuth 2.0 belirtiminin [4.1. bölümünde](https://tools.ietf.org/html/rfc6749#section-4.1) açıklanmıştır.

Daha fazla bilgi için bkz. [OAuth 2.0 ve Azure Active Directory kullanarak web uygulamalarına erişim yetkisi verme](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code).

## <a name="api-url-structure"></a>API URL yapısı

Veri Ambarı API uç noktaları, her kümenin varlıklarını okur. Bu API, bir **GET** HTTP fiili ve bir sorgu seçenekleri alt kümesini destekler.

Intune URL’si aşağıdaki biçimdedir:  
`https://fef.{location}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{entity-collection}?api-version={api-version}`

> [!NOTE]
> Yukarıdaki URL’de `{location}`, `{entity-collection}` ve `{api-version}` değerlerini aşağıdaki tabloda sağlanan ayrıntılarla değiştirin.

Bu URL aşağıdaki öğeleri içerir:

| Öğe | Örnek | Açıklama |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| location | msua06 | Temel URL, Azure portalında Veri Ambarı API’si dikey penceresinde bulunabilir. |
| varlık-koleksiyonu | tarihler | OData varlık koleksiyonu adı. Veri modelindeki koleksiyonlar ve varlıklar hakkında daha fazla bilgi için bkz. [Veri Modeli](reports-ref-data-model.md). |
| api-sürümü | beta | Sürüm, erişilecek API’nin sürümüdür. Daha fazla bilgi için bkz. [Sürüm](#API-version-information). |
| maxhistorydays | 7 | (İsteğe bağlı) Geçmişin alınacağı en fazla gün sayısı. Bu parametre herhangi bir koleksiyon için sağlanabilir ancak yalnızca anahtar özelliğinin bir parçası olarak `dateKey` içeren koleksiyonlarda geçerli olacaktır. Daha fazla bilgi için [DateKey Aralık Filtreleri](reports-api-url.md#datekey-range-filters)’ne bakın. |

## <a name="api-version-information"></a>API sürüm bilgisi

Artık sorgu parametresini ayarlayarak Intune Veri Ambarı’nın v1.0 sürümünü kullanabilirsiniz `api-version=v1.0`. Veri Ambarı’ndaki koleksiyonlara yapılan güncelleştirmeler ek olarak yapılır, yani mevcut senaryoları bozmaz.

Beta sürümünü kullanarak Veri Ambarı’nın en yeni işlevlerini deneyebilirsiniz. Beta sürümünü kullanabilmeniz için URL’nizin sorgu parametresini içermesi gerekir `api-version=beta`. Özellikler, desteklenen bir hizmet olarak herkesin kullanımına açılmadan önce beta sürümünde sunulur. Intune yeni özellikler ekledikçe beta sürümünün davranışında ve veri anlaşmalarında değişiklikler olabilir. Beta sürümüne bağımlı olan özel kodlar veya raporlama araçları, devam eden güncelleştirmelerle birlikte kesilebilir.

## <a name="odata-query-options"></a>OData sorgu seçenekleri

Geçerli sürümü aşağıdaki OData sorgu parametrelerini destekler: `$filter`, `$select`, `$skip,` ve `$top`. İçinde `$filter`, yalnızca `DateKey` veya `RowLastModifiedDateTimeUTC` sütunları geçerlidir ve diğer özellikleri bir hatalı istek tetikleyecek desteklenmiyor olabilir.

## <a name="datekey-range-filters"></a>DateKey Aralık Filtreleri

`DateKey` aralık filtreleri, anahtar özelliği `dateKey` olan koleksiyonların bazılarından indirilebilen veri miktarını sınırlamak için kullanılabilir. `DateKey` filtresi, aşağıdaki `$filter` sorgu parametresini sağlayarak hizmet performansını en iyi duruma getirmek için kullanılabilir:

1.  `$filter` içinde `lt/le/eq/ge/gt` işleçlerini destekleyen ve `and` mantıksal işleciyle birleştirilen tek başına `DateKey`; bir başlangıç tarihi ve/veya bitiş tarihiyle eşlenebilir.
2.  `maxhistorydays`, özel sorgu seçeneği olarak sağlanır.<br>

## <a name="filter-examples"></a>Filtre örnekleri

> [!NOTE]
> Örnekler varsayar bugün filtre 21/2/2019.

|                             Filtre                             |           Performansı En İyi Duruma Getirme           |                                          Açıklama                                          |
|:--------------------------------------------------------------:|:--------------------------------------------:|:---------------------------------------------------------------------------------------------:|
|    `maxhistorydays=7`                                            |    Tam                                      |    `DateKey` ile 20180214 ve 20180221 arasında veri döndürülür.                                     |
|    `$filter=DateKey eq 20180214`                                 |    Tam                                      |    `DateKey` ile 20180214’e eşit veri döndürülür.                                                    |
|    `$filter=DateKey ge 20180214 and DateKey lt 20180221`         |    Tam                                      |    `DateKey` ile 20180214 ve 20180220 arasında veri döndürülür.                                     |
|    `maxhistorydays=7&$filter=DateKey eq 20180214`                |    Tam                                      |    `DateKey` ile 20180214’e eşit veri döndürülür. `maxhistorydays` yoksayılır.                            |
|    `$filter=RowLastModifiedDateTimeUTC ge 2018-02-21T23:18:51.3277273Z`                                |    Tam                                       |    Dönüş verileri ile `RowLastModifiedDateTimeUTC` büyüktür veya eşittir `2018-02-21T23:18:51.3277273Z`                             |
