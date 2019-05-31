---
title: Denetim değişiklikleri ve olayları Microsoft Intune - Azure | Microsoft Docs
description: Microsoft Intune etkinliklerinin kaydedildiği denetim günlüklerini gözden geçirmeyi öğrenin.
keywords: ''
ms.author: dougeby
author: dougeby
manager: dougeby
ms.date: 03/18/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5d39b62762d623c150ac6198bd2d6215b4410663
ms.sourcegitcommit: 063177c6c365fef3642edd7c455790958469aad9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/30/2019
ms.locfileid: "66412299"
---
# <a name="use-audit-logs-to-track-and-monitor-events-in-microsoft-intune"></a>İzleme ve Microsoft Intune olayları izlemek için denetim günlüklerini kullanın

Denetim günlükleri Intune değişiklik yaratan etkinliklerin kaydını içerir. Oluşturun, güncelleştirin (düzenleyin), silme, atama ve uzak eylemleri tüm yöneticiler çoğu Intune iş yükleri için gözden geçirebilirsiniz denetim olayları oluşturun. Varsayılan olarak, Denetim tüm müşteriler için etkindir. Bunu devre dışı bırakılamaz.

> [!NOTE]
> Denetim olayları üzerinde aralık 2017 özellik yayını kaydı başlatıldı. Önceki olaylar mevcut değildir.

## <a name="who-can-access-the-data"></a>Verilere kimler erişebilir?

Aşağıdaki izinlere sahip kullanıcılar denetim günlüklerini gözden geçirebilir:

- Genel Yönetici
- Intune Hizmet Yöneticisi
- **Denetim verileri** - **Okuma** izinlerine sahip bir Intune rolüne atanmış olan yöneticiler

## <a name="audit-logs-for-intune-workloads"></a>Intune iş yükleri için denetim günlükleri

Her Intune iş yükü için izleme grubunda denetim günlüklerini gözden geçirebilirsiniz:

1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Denetim günlüklerini gözden geçirmek istediğiniz iş yükünü seçin. Örneğin, **cihazları**.
3. Altında **izleme**, seçin **denetim günlükleri**.

## <a name="route-logs-to-azure-monitor"></a>Azure İzleyici günlüklerine yol

Denetim günlüklerini ve operasyonel günlükler, Azure İzleyici ayrıca yönlendirilebilir. İçinde **denetim günlükleri**seçin **veri dışa aktarma ayarları**:

![Azure için günlük verileri dışarı aktarma Intune'da veri ayarlarını dışa aktarma seçerek İzleyicisi](./media/audit-logs-export-data-settings.png)

Bu özellik hakkında daha fazla bilgi için bkz. [olay hub'ları, depolama için günlük verileri gönderin veya günlük analizi](review-logs-using-azure-monitor.md).

## <a name="review-audit-events"></a>Denetim olaylarını gözden geçirme

![Denetim günlükleri Eylemler ve tarihleri olayların ne zaman oluştuğunu görmek için Intune içinde seçin](./media/monitor-audit-logs.png "denetim günlükleri")

Denetim günlüğünün aşağıdaki öğeleri gösteren bir varsayılan liste görünümü vardır:

- Tarih ve saat oluşum
- Başlatan (Aktör)
- Uygulama Adı
- Etkinlik
- Hedefler
- Category
- Durum

Bir olay hakkında daha ayrıntılı bilgi için listede bir öğe seçin:

![Kimin yaptığını, Intune'da ne Denetim günlükleri hakkında daha fazla bilgi edinin](./media/monitor-audit-log-detail.png "denetim günlüğü ayrıntılarındaki")

> [!NOTE]
> **Başlatan (aktör)** görev çalıştıran ve burada çalıştırıldığı hakkındaki bilgileri içerir. Örneğin, etkinlik Intune'da Azure portalında, ardından çalıştırırsanız **uygulama** her zaman listeler **Intune portal uzantısı** ve **uygulama kimliği** her zaman aynı GUID kullanılır.
> 
> **Listelenebilir** bölümde birden çok hedef ve değiştirilen özellikler listelenir.  

## <a name="filter-audit-events"></a>Denetim olaylarını filtreleme

Her iş yükünün, o bölmeyle ilişkilendirilmiş denetim olayları kategorisine önceden filtre uygulayan bir menü öğesi vardır. Ayrı bir filtre seçeneği farklı kategorilere geçmenizi sağlar ve o kategorinin olay eylem ayrıntıları gösterilir. Eylemi gerçekleştiren kullanıcı gibi UPN'ye göre arama yapabilirsiniz. Tarih aralığı filtresinde 24 saat, 7 gün ve 30 gün seçenekleri sağlanır. Varsayılan olarak, son 30 Günün denetim olayları görüntülenir.

## <a name="use-graph-api-to-retrieve-audit-events"></a>Denetim olaylarını almak için Graph API kullanma

En çok bir yıllık denetim olaylarını almak için graph API kullanma hakkında daha fazla bilgi için bkz [List auditEvents](https://docs.microsoft.com/graph/api/intune-auditing-auditevent-list?view=graph-rest-1.0).

## <a name="next-steps"></a>Sonraki adımlar

[Olay hub'ları, depolama için günlük verileri gönderin veya günlük analizi](review-logs-using-azure-monitor.md).

[İstemci uygulama koruma günlüklerini gözden geçirme](app-protection-policy-settings-log.md).
