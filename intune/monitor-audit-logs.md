---
title: "Intune etkinlikleri için denetleme günlükleri"
description: "Intune etkinliklerinin kaydedildiği denetim günlüklerini gözden geçirmeyi öğrenin"
keywords: 
author: dougeby
manager: angrobe
ms.date: 12/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4
ms.openlocfilehash: 30067f60163a644f4347c51c249c25fb3428f8ba
ms.sourcegitcommit: ef8610aa2ea0acdc40bad948ed7ba3a3a4464453
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/12/2017
---
# <a name="audit-logs-for-intune-activities"></a>Intune etkinlikleri için denetleme günlükleri
Denetim günlükleri size, Microsoft Intune'da değişiklik yaratan etkinliklerin kaydını sağlar. Eylemleri veya uzak görevleri oluşturun, güncelleştirin (düzenleyin), silin ve atayın; gözden geçirebileceğiniz denetim olayları oluşturun. Intune iş yüklerinin çoğunda denetim günlüklerini gözden geçirebilirsiniz. 

## <a name="who-can-access-the-data"></a>Verilere kimler erişebilir?
Aşağıdaki izinlere sahip kullanıcılar denetim günlüklerini gözden geçirebilir:
- Genel Yönetici
- Intune Hizmet Yöneticisi
- **Denetim verileri** - **Okuma** izinlerine sahip bir Intune rolüne atanmış olan yöneticiler

## <a name="audit-logs-for-intune-workloads"></a>Intune iş yükleri için denetim günlükleri
Her Intune iş yükü için, İzleme grubunda denetim günlüklerini gözden geçirebilirsiniz.  
1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde, denetim günlüklerini gözden geçirmek istediğiniz iş yükünü seçin.
4. İş yükünün **İzleme** grubunda **Denetim günlükleri**'ni seçin.

## <a name="review-audit-events"></a>Denetim olaylarını gözden geçirme
![Denetim günlükleri](./media/monitor-audit-logs.png "Denetim günlükleri")

Denetim günlüğünün aşağıdaki öğeleri gösteren bir varsayılan liste görünümü vardır:    

- oluşma tarihi ve saati
- Başlatan (Aktör)
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
Her iş yükünün, o dikey pencereyle ilişkilendirilmiş denetim olayları kategorisine önceden filtre uygulayan bir menü öğesi vardır. Ayrı bir filtre seçeneği farklı kategorilere geçmenizi sağlar ve o kategorinin olay eylem ayrıntıları gösterilir. UPN'ye göre arama yapabilirsiniz (örneğin, eylemi gerçekleştiren kullanıcı). Tarih aralığı filtresinde 24 saat, 7 gün ve 30 gün seçenekleri sağlanır. Varsayılan olarak, son 30 günün denetim olayları görüntülenir.

## <a name="use-graph-api-to-retrieve-audit-events"></a>Denetim olaylarını almak için Graph API kullanma
Graph API'yi kullanarak en çok bir yıllık denetim olaylarını alma konusundaki ayrıntılar için bkz. [List auditEvents](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/intune_auditing_auditevent_list).