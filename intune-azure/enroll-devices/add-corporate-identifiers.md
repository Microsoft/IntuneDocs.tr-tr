---
title: "Intune’a IMEI tanımlayıcılarını ekleme | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Microsoft Intune’a kurumsal tanımlayıcıları (IMEI numaraları) eklemeyi öğrenin. "
keywords: 
author: staciebarker
ms.author: stabark
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: e134a6e3ff143dacce1d70ef0ab44ade0722ed57

---

# <a name="add-corporate-identifiers"></a>Kurumsal tanımlayıcılar ekleme

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Kurumsal cihazlarınızı tanımlamak için bir Uluslararası Mobil Ekipman Kimliği (IMEI) numaraları listesi oluşturabilirsiniz. Bu cihazlar kayıtlı olabilir veya olmayabilir ve durumları “Kaydedildi” veya “Bağlantı kurulmadı” olabilir. “Bağlantı kurulmadı”, cihazın Intune hizmetiyle hiç bağlantıya geçmediği anlamına gelir.

Listeyi oluşturmak için iki sütunlu, üst bilgisi olmayan bir virgülle ayrılmış değerler (.csv) listesi oluşturun. Sol sütuna IMEI tanımlayıcısını ve sağ sütuna ayrıntıları ekleyin. Liste için geçerli üst sınır 500 satırdır.

Metin düzenleyicisinde, .csv listesi aşağıdaki gibi görünür:

01 234567 890123,cihaz ayrıntıları</br>
02 234567 890123,cihaz ayrıntıları

**Kurumsal tanımlayıcıları içeren .csv listesini eklemek için**

1. Azure Portal’da **Diğer Hizmetler**’i seçin, metin kutusuna **Intune** girin ve sonra **Diğer** > **Intune**’u seçin.

2. Intune dikey penceresinde **Cihazları kaydet**’i ve ardından **Kurumsal Cihaz Tanımlayıcıları**’nı seçin.

3. Mevcut ayrıntıların üzerine yazılacak yeni ayrıntılar içeren bir dosyayı içeri aktarıyorsanız, mevcut ayrıntıların yerini yenilerinin alması için **Mevcut tanımlayıcıların ayrıntılarının üzerine yazın** seçeneğini kullanın.

4. IMEI CSV dosyasına gidin ve **Ekle**’yi seçin.

**Kurumsal tanımlayıcıları içeren .csv listesini silmek için**

1. Intune dikey penceresinde **Cihazları kaydet**’i ve ardından **Kurumsal Cihaz Tanımlayıcıları**’nı seçin.

2. **Sil**’i seçin.



<!--HONumber=Feb17_HO1-->


