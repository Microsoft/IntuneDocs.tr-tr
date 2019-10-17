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
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5f6682cb-5fcd-4018-b7f7-71768ad3152e
ms.reviewer: kerimh
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: a5e52d1967ff6f5cf97334c099bc2b5b854ae87c
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72502691"
---
# <a name="us-government-endpoints-for-microsoft-intune"></a>Microsoft Intune için ABD devlet uç noktaları

Bu sayfada, Intune dağıtımlarınızdaki ara sunucu ayarları için gereken ABD kamu uç noktaları listelenir.

Güvenlik duvarı ve ara sunucular arkasındaki cihazları yönetmek için Intune iletişimini etkinleştirmeniz gerekir.

- Intune istemcileri iki protokolü de kullandığından, proxy sunucusu hem **HTTP (80)** hem de **HTTPS (443)** desteklemelidir
- Intune bazı görevler (yazılım güncelleştirmelerini indirme gibi) için manage.microsoft.com adresine kimliği doğrulanmamış ara sunucu erişimine ihtiyaç duyar.

Ara sunucu ayarlarını istemci bilgisayarlardan değiştirebilirsiniz. Belirtilen ara sunucu arkasında yer alan tüm istemci bilgisayarların ayarlarını değiştirmek için Grup İlkesi ayarlarını da kullanabilirsiniz.

Yönetilen cihazlar, **Tüm Kullanıcıların** güvenlik duvarları üzerinden hizmetlere erişmesine izin veren yapılandırmalar gerektirir.

Aşağıdaki tabloda Intune istemcisinin eriştiği bağlantı noktaları ve hizmetler listelenir:

|**Bkz**|**IP adresi**|
|---------------------|-----------|
|*. manage.microsoft.us | 52.243.26.209 <br> 52.247.173.11 <br> 52.227.183.12 <br>52.227.180.205 <br> 52.227.178.107 <br> 13.72.185.168 <br> 52.227.173.179 <br> 52.227.175.242 <br> 13.72.39.209 <br> 52.243.26.209 <br> 52.247.173.11 |
| enterpriseregistration.microsoftonline.us | 13.72.188.239 <br> 13.72.55.179 |

## <a name="us-government-customer-designated-endpoints"></a>ABD devlet müşteri tarafından belirlenen uç noktalar:
- Azure portal: https: \//Portal. Azure. us/ 
- Office 365: https: \//Portal. office365. us/ 
- Intune Şirket Portalı: https: \//Portal. Manage. Microsoft. us/ 

## <a name="partner-service-endpoints-that-intune-depends-on"></a>Intune 'un bağımlı olduğu iş ortağı hizmeti uç noktaları:
- AAD Eşitleme hizmeti: https: \//SyncService. gov. us. microsoftonline. com/DirectoryService. svc
- EVO STS: https: \//Login. microsoftonline. us
- Dizin proxy 'Si: https: \//directoryproxy. MicrosoftAzure. us/DirectoryProxy. svc
- AAD Graf: https: \//Directory. MicrosoftAzure. us ve https: \//Graph. MicrosoftAzure. us
- MS Graph: https: \//Graf. Microsoft. us
- ADRS: https: \//enterpriseregistration. microsoftonline. us
