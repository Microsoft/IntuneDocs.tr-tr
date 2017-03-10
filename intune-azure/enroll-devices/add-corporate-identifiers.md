---
title: "Intune&quot;a IMEI tanımlayıcıları ekleme"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Microsoft Intune’a kurumsal tanımlayıcıları (IMEI numaraları) eklemeyi öğrenin. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 0d7c8eedbdad917a43d43d2e79ead5663e8e2871
ms.lasthandoff: 02/18/2017

---

# <a name="add-corporate-identifiers"></a>Kurumsal tanımlayıcılar ekleme

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Kurumsal cihazlarınızı tanımlamak için bir Uluslararası Mobil Ekipman Kimliği (IMEI) numaraları listesi oluşturabilirsiniz. Bu cihazlar kayıtlı olabilir veya olmayabilir ve durumları “Kaydedildi” veya “Bağlantı kurulmadı” olabilir. “Bağlantı kurulmadı”, cihazın Intune hizmetiyle hiç bağlantıya geçmediği anlamına gelir.

Listeyi oluşturmak için iki sütunlu, üst bilgisi olmayan bir virgülle ayrılmış değerler (.csv) listesi oluşturun. Sol sütuna IMEI tanımlayıcısını ve sağ sütuna ayrıntıları ekleyin. Liste için geçerli üst sınır 500 satırdır.

Metin düzenleyicisinde, .csv listesi aşağıdaki gibi görünür:

01 234567 890123,cihaz ayrıntıları</br>
02 234567 890123,cihaz ayrıntıları

**Kurumsal tanımlayıcıları içeren .csv listesini eklemek için**

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2. Intune dikey penceresinde **Cihazları kaydet**’i ve ardından **Kurumsal Cihaz Tanımlayıcıları**’nı seçin.

3. Mevcut ayrıntıların üzerine yazılacak yeni ayrıntılar içeren bir dosyayı içeri aktarıyorsanız, mevcut ayrıntıların yerini yenilerinin alması için **Mevcut tanımlayıcıların ayrıntılarının üzerine yazın** seçeneğini kullanın.

4. IMEI CSV dosyasına gidin ve **Ekle**’yi seçin.

**Kurumsal tanımlayıcıları içeren .csv listesini silmek için**

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2. Intune dikey penceresinde **Cihazları kaydet**’i ve ardından **Kurumsal Cihaz Tanımlayıcıları**’nı seçin.

3. **Sil**’i seçin.

