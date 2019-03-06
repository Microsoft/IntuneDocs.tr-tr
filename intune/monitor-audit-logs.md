---
title: Microsoft Intune etkinlikleri için denetim günlükleri
description: Microsoft Intune etkinliklerinin kaydedildiği denetim günlüklerini gözden geçirmeyi öğrenin.
keywords: ''
ms.author: dougeby
author: dougeby
manager: dougeby
ms.date: 02/27/2018
ms.topic: troubleshooting
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 98540af0f0b7d259973d1a7e873c68fc64f488d1
ms.sourcegitcommit: fb2ca28ab0cf89202c935da3f9d98adcea20566d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57460691"
---
# <a name="audit-logs-for-intune-activities"></a>Intune etkinlikleri için denetleme günlükleri
Denetim günlükleri size, Microsoft Intune'da değişiklik yaratan etkinliklerin kaydını sağlar. Eylemleri veya uzak görevleri oluşturun, güncelleştirin (düzenleyin), silin ve atayın; gözden geçirebileceğiniz denetim olayları oluşturun. Intune iş yüklerinin çoğunda denetim günlüklerini gözden geçirebilirsiniz. Denetim tüm müşteriler için varsayılan olarak etkindir ve devre dışı bırakılamaz. Denetim olayları özelliği Aralık 2017’deki yayımlanma tarihinde kaydedilmeye başlandı; daha önceki olaylar mevcut değil.

## <a name="who-can-access-the-data"></a>Verilere kimler erişebilir?
Aşağıdaki izinlere sahip kullanıcılar denetim günlüklerini gözden geçirebilir:
- Genel Yönetici
- Intune Hizmet Yöneticisi
- **Denetim verileri** - **Okuma** izinlerine sahip bir Intune rolüne atanmış olan yöneticiler

## <a name="audit-logs-for-intune-workloads"></a>Intune iş yükleri için denetim günlükleri
Her Intune iş yükü için, İzleme grubunda denetim günlüklerini gözden geçirebilirsiniz.  
1. [Azure portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde, denetim günlüklerini gözden geçirmek istediğiniz iş yükünü seçin, örneğin **Cihazlar**.
4. İş yükünün **İzleme** grubunda **Denetim günlükleri**'ni seçin.

## <a name="review-audit-events"></a>Denetim olaylarını gözden geçirme
![Denetim günlükleri](./media/monitor-audit-logs.png "Denetim günlükleri")

Denetim günlüğünün aşağıdaki öğeleri gösteren bir varsayılan liste görünümü vardır:    

- oluşma tarihi ve saati
- Başlatan (Aktör)
- Uygulama Adı
- Etkinlik
- Hedefler
- Kategori
- Durum

Liste görünümünde bir öğeye tıkladığınızda, öğe hakkında sağlanan tüm ayrıntıları alırsınız.

![Denetim günlükleri](./media/monitor-audit-log-detail.png "Denetim günlükleri")

> [!Note]    
> Denetim günlüğü ayrıntılarındaki **Başlatan (aktör)** bölümü, etkinliğin kim tarafından ve nereden gerçekleştirildiği hakkında bilgi sağlar. Örneğin, etkinliği Azure Portal'da Intune'da gerçekleştirirseniz, **Uygulama**'da her zaman **Microsoft Intune portal uzantısı** listelenir ve **Uygulama Kimliği**'nde her zaman aynı GUID kullanılır. 
>    
> **Hedefler** bölümünde birden çok hedef ve değiştirilen özellikler listelenebilir.  


## <a name="filter-audit-events"></a>Denetim olaylarını filtreleme
Her iş yükünün, o bölmeyle ilişkilendirilmiş denetim olayları kategorisine önceden filtre uygulayan bir menü öğesi vardır. Ayrı bir filtre seçeneği farklı kategorilere geçmenizi sağlar ve o kategorinin olay eylem ayrıntıları gösterilir. UPN'ye göre arama yapabilirsiniz (örneğin, eylemi gerçekleştiren kullanıcı). Tarih aralığı filtresinde 24 saat, 7 gün ve 30 gün seçenekleri sağlanır. Varsayılan olarak, son 30 günün denetim olayları görüntülenir.

## <a name="use-graph-api-to-retrieve-audit-events"></a>Denetim olaylarını almak için Graph API kullanma
Graph API'yi kullanarak en çok bir yıllık denetim olaylarını alma konusundaki ayrıntılar için bkz. [List auditEvents](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/intune_auditing_auditevent_list).
