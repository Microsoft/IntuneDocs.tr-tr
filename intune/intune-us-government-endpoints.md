---
title: ABD kamu dağıtımları için ağ uç noktaları-Microsoft Intune
titleSuffix: ''
description: Intune için ABD devlet bitiş noktalarını gözden geçirin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/30/2019
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
ms.openlocfilehash: 9828b04ae30d8f35313564b93dfc9b997795bf76
ms.sourcegitcommit: 8d12ab22e23552f9addaef4c28b732fb211945a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/18/2019
ms.locfileid: "68306715"
---
# <a name="us-government-endpoints-for-microsoft-intune"></a>Microsoft Intune için ABD devlet uç noktaları

Bu sayfada, Intune dağıtımlarınızdaki ara sunucu ayarları için gereken ABD kamu uç noktaları listelenir.

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

## <a name="us-government-customer-designated-endpoints"></a>ABD devlet müşteri tarafından belirlenen uç noktalar:
- Azure Portal: https:\//Portal.Azure.us/ 
- Office 365: https:\//Portal.office365.us/ 
- Intune Şirket Portalı: https:\//Portal.Manage.Microsoft.us/ 

## <a name="partner-service-endpoints-that-intune-depends-on"></a>Intune 'un bağımlı olduğu iş ortağı hizmeti uç noktaları:
- AAD eşitleme hizmeti: https:\//SyncService.gov.us.microsoftonline.com/DirectoryService.svc
- EVO STS: https:\//Login.microsoftonline.us
- Dizin proxy 'si: https\/:/directoryproxy.MicrosoftAzure.us/DirectoryProxy.svc
- AAD grafiği: https:\//Directory.MicrosoftAzure.us ve https:\//Graph.MicrosoftAzure.us
- MS Graph: https:\//Graph.Microsoft.us
- Adrs: https:\//enterpriseregistration.microsoftonline.us
