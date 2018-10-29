---
title: Intune Veri Ambarı API uç noktası
titlesuffix: Microsoft Intune
description: Başvuru konusu, Intune Veri Ambarı API URL’si yapısını açıklar.
keywords: Intune Veri Ambarı
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/09/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d552ec61d148d0489dc263405eac52448c10f9ef
ms.sourcegitcommit: 24d9ae0396ca410f72cc061a3c4c402835ef32a1
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2018
ms.locfileid: "49642918"
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

API’nin geçerli sürümü şudur: `beta`. 

## <a name="odata-query-options"></a>OData sorgu seçenekleri

Mevcut sürüm, aşağıdaki OData sorgu parametrelerini destekler: `$filter, $orderby, $select, $skip,` ve `$top`.

## <a name="datekey-range-filters"></a>DateKey Aralık Filtreleri

`DateKey` aralık filtreleri, anahtar özelliği `dateKey` olan koleksiyonların bazılarından indirilebilen veri miktarını sınırlamak için kullanılabilir. `DateKey` filtresi, aşağıdaki `$filter` sorgu parametresini sağlayarak hizmet performansını en iyi duruma getirmek için kullanılabilir:

1.  `$filter` içinde `lt/le/eq/ge/gt` işleçlerini destekleyen ve `and` mantıksal işleciyle birleştirilen tek başına `DateKey`; bir başlangıç tarihi ve/veya bitiş tarihiyle eşlenebilir.
2.  `maxhistorydays`, özel sorgu seçeneği olarak sağlanır.<br>

## <a name="filter-examples"></a>Filtre örnekleri

> [!NOTE]
> Filtre örneklerinde tarihin 21.2.2018 olduğu varsayılır.

|                             Filtrele                             |           Performansı En İyi Duruma Getirme           |                                          Açıklama                                          |
|:--------------------------------------------------------------:|:--------------------------------------------:|:---------------------------------------------------------------------------------------------:|
|    `maxhistorydays=7`                                            |    Tam                                      |    `DateKey` ile 20180214 ve 20180221 arasında veri döndürülür.                                     |
|    `$filter=DateKey eq 20180214`                                 |    Tam                                      |    `DateKey` ile 20180214’e eşit veri döndürülür.                                                    |
|    `$filter=DateKey ge 20180214 and DateKey lt 20180221`         |    Tam                                      |    `DateKey` ile 20180214 ve 20180220 arasında veri döndürülür.                                     |
|    `maxhistorydays=7&$filter=Id gt 1`                            |    Kısmi, 1'den büyük kimlikler en iyi duruma getirilmez    |    `DateKey` ile 20180214 ve 20180221 arasında veri döndürülür ve kimlik 1'den büyüktür.             |
|    `maxhistorydays=7&$filter=DateKey eq 20180214`                |    Tam                                      |    `DateKey` ile 20180214’e eşit veri döndürülür. `maxhistorydays` yoksayılır.                            |
|    `$filter=DateKey eq 20180214 and Id gt 1`                     |    Yok.                                      |    `DateKey` aralık filtresi olarak kabul edilmez, bu nedenle performans artırılmaz.                              |
|    `$filter=DateKey ne 20180214`                                 |    Yok.                                      |    `DateKey` aralık filtresi olarak kabul edilmez, bu nedenle performans artırılmaz.                              |
|    `maxhistorydays=7&$filter=DateKey eq 20180214 and Id gt 1`    |    Yok.                                      |    `DateKey` aralık filtresi olarak kabul edilmez, bu nedenle performans artırılmaz. `maxhistorydays` yoksayılır.    |
