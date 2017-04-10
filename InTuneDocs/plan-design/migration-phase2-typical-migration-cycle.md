---
title: "Tipik bir Intune geçiş döngüsünün çalışması | Microsoft Docs"
description: "Bu makalenin amacı, Intune geçiş döngüsünün nasıl çalıştığını açıklamak ve müşterinin geçiş döngülerini nasıl ele aldığına ilişkin örnekler vermektir."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3688b724-9521-4210-bf4d-bcf47d8d4ca0
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: aa8fb215772b6e8d3a913d929c030d68e363970b
ms.lasthandoff: 03/27/2017


---

# <a name="phase-2-typical-migration-cycle"></a>2. Aşama: Tipik Geçiş Döngüsü

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Bir kuruluşun Intune geçişini BT departmanı içindeki kullanıcılarının bir alt kümesini hedefleyerek küçük bir pilot grup ile başlatması yaygındır. Ayrıca, kuruluşunuzun geçiş zaman çerçevesini belirlemede yardımcı olması için kullanıcıların değişiklik isteyip istemedikleri, kullanıcı sayısı, karmaşıklık, gereksinimler, konum ve iş riski gibi faktörleri ele alması gerekebilir.

Hedef gruplarınızın zaman çizelgesinin nasıl oluşturulacağına ilişkin bir örnek aşağıda verilmiştir:

  | **Geçiş hedeflenen gruplar** | **Dönem 1** | **Dönem 2** | **Dönem 3** | **Dönem 4** | **...**
|:---:|:---:|:---:|:---:|:---:|:---:|
| Sınırlı Pilot BT kuruluşu (50 kullanıcı) | Planı Duyurma | Kayıt talimatı verme | Son tarih verme | Koşullu erişimi zorlama |  |                                                        
| Genişletilmiş Pilot BT kuruluşu (200 kullanıcı) |  | Planı Duyurma | Kayıt talimatı verme | Son tarih verme | Koşullu erişimi zorlama | 
| Geçiş aşaması 1 Teknik bilgiye sahip kullanıcılar (2000) |  |  | Planı Duyurma | Kayıt talimatı verme | Son tarih verme | 
| Geçiş aşaması 2 Doğu ABD |  |  |  | Planı Duyurma | Kayıt talimatı verme | 
| Tüm Bölgeler |  |  |  |  | Planı Duyurma | 

## <a name="customer-migration-case-study"></a>Müşteri geçişi örnek olay incelemesi

### <a name="adatum-corporation"></a>Adatum Corporation

- [Adatum Corporation’ın bir üçüncü taraf MDM sağlayıcısından Intune'a geçiş sürecini](https://gallery.technet.microsoft.com/Intune-migration-guide-893a95e3?redir=0) inceleyin.

## <a name="monitoring-migration"></a>Geçiş izleme

Microsoft Intune, geçişi izleyebilmenizi sağlayan çeşitli yollar sunar:

1.  Intune kullanıcı grubu görünümleri

2.  Yerleşik raporlar kümesi ve

3.  Konsol içi uyarılar.

Her aşamadan sonra kaç kullanıcının cihazlarını kaydettiğini izlemelisiniz, böylece şunları yapabilirsiniz:

-   İletişim planınızın verimliliğini değerlendirmek.

-   Koşullu erişim zorlama etkisini tahmin etmek.

[Bir Intune geçişini nasıl izleyebileceğinizi](https://docs.microsoft.com/intune/deploy-use/understand-microsoft-intune-operations-by-using-reports) öğrenin.

## <a name="post-migration"></a>Geçiş Sonrası

Intune'a geçtikten sonra önceki MDM sağlayıcısını devre dışı bırakmanız ve/veya hizmet aboneliğinizi bitirmeniz gerekecektir. Ayrıca, MDM sağlayıcısının yönergelerini izleyerek gereksiz altyapı gereksinimlerinin tümünü kaldırmanız gerekir.

