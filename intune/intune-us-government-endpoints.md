---
title: ABD devlet kurumu dağıtımlarından - Intune için ağ uç noktaları
titleSuffix: ''
description: ABD kamu uç noktaları, Intune için gözden geçirin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7a86069b7f4093fb437171d5699df2302fc6fd2a
ms.sourcegitcommit: df413d1786c9aa0f409424c1e9e102bf230bbe39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2019
ms.locfileid: "66721698"
---
# <a name="us-government-endpoints-for-microsoft-intune"></a>Microsoft Intune ABD kamu uç noktaları

Bu sayfada Intune dağıtımlarınızı proxy ayarları için gereken ABD kamu uç noktaları listelenir.

Güvenlik duvarı ve ara sunucular arkasındaki cihazları yönetmek için Intune iletişimini etkinleştirmeniz gerekir.

- Intune istemcileri iki protokolü de kullandığından, proxy sunucusu hem **HTTP (80)** hem de **HTTPS (443)** desteklemelidir
- Intune bazı görevler (yazılım güncelleştirmelerini indirme gibi) için manage.microsoft.com adresine kimliği doğrulanmamış ara sunucu erişimine ihtiyaç duyar.

Ara sunucu ayarlarını istemci bilgisayarlardan değiştirebilirsiniz. Belirtilen ara sunucu arkasında yer alan tüm istemci bilgisayarların ayarlarını değiştirmek için Grup İlkesi ayarlarını da kullanabilirsiniz.

Yönetilen cihazlar, **Tüm Kullanıcıların** güvenlik duvarları üzerinden hizmetlere erişmesine izin veren yapılandırmalar gerektirir.

Aşağıdaki tabloda Intune istemcisinin eriştiği bağlantı noktaları ve hizmetler listelenir:

|**Uç noktası**|**IP adresi**|
|---------------------|-----------|
|*.manage.microsoft.us | 52.243.26.209 <br> 52.247.173.11 <br> 52.227.183.12 <br>52.227.180.205 <br> 52.227.178.107 <br> 13.72.185.168 <br> 52.227.173.179 <br> 52.227.175.242 <br> 13.72.39.209 <br> 52.243.26.209 <br> 52.247.173.11 |
| enterpriseregistration.microsoftonline.us | 13.72.188.239 <br> 13.72.55.179 |

## <a name="us-government-customer-designated-endpoints"></a>ABD kamu müşterileri, uç noktaları atanan:
- Azure portalı: https://portal.azure.us/ 
- Office 365: https://portal.office365.us/ 
- Intune Şirket portalı: https://portal.manage.microsoft.us/ 

## <a name="partner-service-endpoints-that-intune-depends-on"></a>Intune bağımlı iş ortağı hizmet uç noktaları:
- AAD eşitleme hizmeti: https://syncservice.gov.us.microsoftonline.com/DirectoryService.svc
- STS Evo: https://login.microsoftonline.us
- Dizin Proxy: https://directoryproxy.microsoftazure.us/DirectoryProxy.svc
- AAD Graph: https://directory.microsoftazure.us ve https://graph.microsoftazure.us
- MS Graph: https://graph.microsoft.us
- ADR: https://enterpriseregistration.microsoftonline.us
