---
title: Microsoft Intune-Azure 'da değişiklik ve olayları denetleme | Microsoft Docs
description: Microsoft Intune etkinliklerinin kaydedildiği denetim günlüklerini gözden geçirmeyi öğrenin.
keywords: ''
ms.author: dougeby
author: dougeby
manager: dougeby
ms.date: 03/18/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: b4be1755a07e6ec304edb7bceba8041d5b58263e
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72509992"
---
# <a name="use-audit-logs-to-track-and-monitor-events-in-microsoft-intune"></a>Microsoft Intune olayları izlemek ve izlemek için Denetim günlüklerini kullanma

Denetim günlükleri, Microsoft Intune değişiklik üreten etkinliklerin bir kaydını içerir. Yöneticilerin çoğu Intune iş yükleri için gözden geçirebileceği denetim olayları oluşturma, güncelleştirme (düzenleme), silme, atama ve uzak eylemleri. Varsayılan olarak, tüm müşteriler için denetim etkindir. Devre dışı bırakılamaz.

> [!NOTE]
> Denetim olayları, Aralık 2017 özelliği sürümünde kaydetmeye başladı. Önceki olaylar kullanılamıyor.

## <a name="who-can-access-the-data"></a>Verilere kimler erişebilir?

Aşağıdaki izinlere sahip kullanıcılar denetim günlüklerini gözden geçirebilir:

- Genel Yönetici
- Intune Hizmet Yöneticisi
- **Denetim verileri** - **Okuma** izinlerine sahip bir Intune rolüne atanmış olan yöneticiler

## <a name="audit-logs-for-intune-workloads"></a>Intune iş yükleri için denetim günlükleri

İzleme grubundaki denetim günlüklerini her Intune iş yükü için gözden geçirebilirsiniz:

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. Denetim günlüklerini gözden geçirmek istediğiniz iş yükünü seçin. Örneğin, **cihazlar**' ı seçin.
3. **İzleme**altında **Denetim günlükleri**' ni seçin.

## <a name="route-logs-to-azure-monitor"></a>Günlükleri Azure Izleyici 'ye yönlendirin

Denetim günlükleri ve işletimsel Günlükler de Azure Izleyici 'ye yönlendirilebilir. **Denetim günlükleri**' nde, **veri ayarlarını dışarı aktar**' ı seçin:

![Intune 'da veri ayarlarını dışarı aktar ' i seçerek günlük verilerini Azure izleyici 'ye aktarın](./media/monitor-audit-logs/audit-logs-export-data-settings.png)

Bu özellik hakkında daha fazla bilgi için bkz. [depolama, Olay Hub 'ları veya Log Analytics 'e günlük verileri gönderme](review-logs-using-azure-monitor.md).

## <a name="review-audit-events"></a>Denetim olaylarını gözden geçirme

![Etkinlik gerçekleştiği sırada eylemleri ve tarihleri görmek için Intune 'da denetim günlüklerini seçin](./media/monitor-audit-logs/monitor-audit-logs.png "Denetim günlükleri")

Denetim günlüğünün aşağıdaki öğeleri gösteren bir varsayılan liste görünümü vardır:

- Olayın tarih ve saati
- Başlatan (Aktör)
- Uygulama adı
- Etkinlik
- Hedefler
- Category
- Durum

Bir olayla ilgili daha ayrıntılı bilgileri görmek için listeden bir öğe seçin:

![Intune 'da denetim günlüklerinde kim olduğuna ilişkin daha özel bilgiler alın](./media/monitor-audit-logs/monitor-audit-log-detail.png "Denetim günlüğü ayrıntıları")

> [!NOTE]
> **Başlatan (aktör)** , görevi kimin çalıştırdığını ve nerede Çalıştırıldığın bilgilerini içerir. Örneğin, etkinliği Azure portal Intune 'da çalıştırırsanız, **uygulama** **Microsoft Intune Portal uzantısını** her zaman listeler ve **uygulama kimliği** her zaman aynı GUID 'yi kullanır.
> 
> **Hedef (ler)** bölümünde birden çok hedef ve değiştirilen özellikler listelenir.  

## <a name="filter-audit-events"></a>Denetim olaylarını filtreleme

Her iş yükünün, o bölmeyle ilişkilendirilmiş denetim olayları kategorisine önceden filtre uygulayan bir menü öğesi vardır. Ayrı bir filtre seçeneği farklı kategorilere geçmenizi sağlar ve o kategorinin olay eylem ayrıntıları gösterilir. , Eylemi yapan kullanıcı gibi UPN 'ye göre arama yapabilirsiniz. Tarih aralığı filtresinde 24 saat, 7 gün ve 30 gün seçenekleri sağlanır. Varsayılan olarak, denetim olaylarının son 30 günü gösterilir.

## <a name="use-graph-api-to-retrieve-audit-events"></a>Denetim olaylarını almak için Graph API kullanma

Grafik API 'SI kullanımıyla ilgili ayrıntılar için, bir yıllık denetim olayları almak üzere bkz. [list auditEvents](https://docs.microsoft.com/graph/api/intune-auditing-auditevent-list?view=graph-rest-1.0).

## <a name="next-steps"></a>Sonraki adımlar

[Depolama, Olay Hub 'ları veya Log Analytics 'e günlük verilerini gönderin](review-logs-using-azure-monitor.md).

[İstemci uygulama koruma günlüklerini gözden geçirin](../apps/app-protection-policy-settings-log.md).
