---
title: "Tipik bir Intune geçiş döngüsü nasıl gerçekleşir"
description: "Bu makalede, Intune geçiş döngüsünün nasıl işlediği açıklanmakta ve bu döngüleri nasıl idare edebileceğinize dair örnekler verilmektedir."
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3688b724-9521-4210-bf4d-bcf47d8d4ca0
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 69cd071f4e5ac8e1c2cd7543951475a3f74bf808
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="typical-migration-cycle"></a>Tipik geçiş döngüsü

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

[Adatum Corporation’ın bir üçüncü taraf MDM sağlayıcısından Intune'a geçiş sürecini](https://gallery.technet.microsoft.com/Intune-migration-guide-893a95e3?redir=0) inceleyin.

## <a name="monitoring-migration"></a>Geçiş izleme

Intune, geçişi izleyebilmenizi sağlayan çeşitli yollar sunar:

* Intune kullanıcı grubu görünümleri

* Yerleşik raporlar kümesi

* Konsol içi uyarılar

Her aşamadan sonra kaç kullanıcının cihazlarını kaydettiğini izleyerek şunları yapabilirsiniz:

-   İletişim planınızın verimliliğini değerlendirmek.

-   Koşullu erişim zorlama etkisini tahmin etmek.


## <a name="post-migration"></a>Geçiş Sonrası

Intune'a geçtikten sonra önceki MDM sağlayıcısını devre dışı bırakın ve hizmet aboneliğinizi bitirin. Ayrıca, MDM sağlayıcısının yönergelerini izleyerek gereksiz altyapı gereksinimlerinin tümünü kaldırın.
