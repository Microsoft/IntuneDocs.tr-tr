---
title: "Intune Veri Ambarı API uç noktası | Microsoft Docs"
description: "Başvuru konusu, API URL yapısını açıklar."
keywords: "Intune Veri Ambarı"
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6dd9098a7db7004f0b7273fc4628d5dd1b535d6d
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/04/2018
---
# <a name="intune-data-warehouse-api-endpoint"></a>Intune Veri Ambarı API uç noktası

Intune Veri Ambarı API’sini, belirli rol tabanlı erişim denetimlerine ve Azure AD kimlik bilgilerine sahip bir hesapla kullanabilirsiniz. Daha sonra REST istemcinizi, OAuth 2.0 kullanarak Azure AD’de yetkilendirirsiniz. Ve son olarak, veri ambarı kaynağı olarak kullanılacak anlamlı bir URL oluşturursunuz.

[!INCLUDE[reports-credential-reqs](./includes/reports-credential-reqs.md)]

## <a name="authorization"></a>Yetkilendirme

Azure Active Directory (Azure AD), OAuth 2.0’ı kullanarak Azure AD kiracınızdaki web uygulamalarına ve web API’lerine erişim yetkisi vermenize olanak tanır. Bu kılavuz dilden bağımsızdır ve açık kaynak kitaplıklarınızın hiçbirini kullanmadan nasıl HTTP iletileri gönderip alacağınızı açıklar. OAuth 2.0 yetkilendirme kod akışı, OAuth 2.0 belirtiminin [4.1. bölümünde](https://tools.ietf.org/html/rfc6749#section-4.1) açıklanmıştır.

Daha fazla bilgi için bkz. [OAuth 2.0 ve Azure Active Directory kullanarak web uygulamalarına erişim yetkisi verme](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code).

## <a name="api-url-structure"></a>API URL yapısı

Veri Ambarı API uç noktaları, her kümenin varlıklarını okur. Bu API, bir **GET** HTTP fiili ve bir sorgu seçenekleri alt kümesini destekler.

Intune URL’si aşağıdaki biçimdedir:  
https://fef.{***konum***}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{***varlık-koleksiyonu***}?api-version={***api-sürümü***}

Bu URL aşağıdaki öğeleri içerir:

| Öğe | Örnek | Description |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| location | msua06 | Temel URL, Azure portalında Veri Ambarı API’si dikey penceresinde bulunabilir. |
| varlık-koleksiyonu | tarihler | OData varlık koleksiyonu adı. Veri modelindeki koleksiyonlar ve varlıklar hakkında daha fazla bilgi için bkz. [Veri Modeli](reports-ref-data-model.md). |
| api-sürümü | beta | Sürüm, erişilecek API’nin sürümüdür. Daha fazla bilgi için bkz. [Sürüm](#API-version-information). |


## <a name="api-version-information"></a>API sürüm bilgisi

API’nin geçerli sürümü şudur: `beta`. 

## <a name="odata-query-options"></a>OData sorgu seçenekleri

Mevcut sürüm, aşağıdaki OData sorgu parametrelerini destekler: `$filter, $orderby, $select, $skip,` ve `$top`.