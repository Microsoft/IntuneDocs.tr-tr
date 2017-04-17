---
title: "Intune&quot;a IMEI tanımlayıcıları ekleme"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Microsoft Intune’a kurumsal tanımlayıcıları (IMEI numaraları) eklemeyi öğrenin. "
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 4ebd74c77145464574a1fed878ec4dbc2eb3c271
ms.openlocfilehash: 7bb8168c442a3340e8c185f1908acd9be15cab05
ms.lasthandoff: 04/05/2017

---

# <a name="add-corporate-identifiers"></a>Kurumsal tanımlayıcılar ekleme

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Bir BT yöneticisi olarak, şirkete ait cihazları tanımlamak için kullanılan Uluslararası Mobil Donanım Kimliği (IMEI) numaralarının listelendiği bir virgülle ayrılmış değerler (.csv) dosyası oluşturabilir ve içeri aktarabilirsiniz. Her IMEI numarasının, listede yönetim amacıyla belirtilen ayrıntıları bulunabilir.

Şirketin sahip olduğu cihazlar için yüklediğiniz seri numaralarının şirket kaydı profili ile eşleştirilmesi gerekir. Ardından cihazların şirkete ait görünmesi için Apple'ın cihaz kayıt programı (DEP) veya Apple Configurator kullanılarak kaydedilmesi gerekir. 

## <a name="create-a-csv-file"></a>.csv dosyası oluşturma
Listeyi oluşturmak için iki sütunlu, üst bilgisi olmayan bir virgülle ayrılmış değerler (.csv) listesi oluşturun. Sol sütuna IMEI tanımlayıcısını ve sağ sütuna ayrıntıları ekleyin. Ayrıntılar 128 karakterle sınırlıdır. Her .csv dosyası için geçerli sınır 500 satırdır.

**Seri numaraları olan bir .csv dosyası yükleme** – Üst bilgi içermeyen, iki sütunlu, virgülle ayrılmış değer (.csv) listesini oluşturun ve .csv dosyası başına 5.000 cihaz veya 5 MB ile sınırlayın.

|||
|-|-|
|&lt;IMEI 1&gt;|&lt;Cihaz 1 Ayrıntıları&gt;|
|&lt;IMEI 2&gt;|&lt;Cihaz 2 Ayrıntıları&gt;|

    This .csv file when viewed in a text editor appears as:

    ```
    01 234567 890123,device details
    02 234567 890123,device details
    ```

**Kurumsal tanımlayıcıları içeren .csv listesini eklemek için**

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2. Intune dikey penceresinde **Cihazları kaydet**’i ve ardından **Kurumsal Cihaz Tanımlayıcıları**’nı seçin.

3. Mevcut ayrıntıların üzerine yazılacak yeni ayrıntılar içeren bir dosyayı içeri aktarıyorsanız, mevcut ayrıntıların yerini yenilerinin alması için **Mevcut tanımlayıcıların ayrıntılarının üzerine yazın** seçeneğini kullanın.

4. IMEI CSV dosyasına gidin ve **Ekle**’yi seçin.

> [!IMPORTANT]
> Bazı Android cihazları birden çok IMEI numarasına sahiptir. Intune, cihaz başına bir IMEI numarası envanteri oluşturur. IMEI numarasını içeri aktarıyorsanız, ancak bu numara Intune tarafından envantere alınan IMEI numarası değilse, cihaz şirkete ait cihaz olarak değil, kişisel cihaz olarak sınıflandırılır. Bir cihaz için birden fazla IMEI numarası içe aktarırsanız, envantere alınmayan numaralar kayıt durumunda **Bilinmeyen** değeri görüntüler.

İçeri aktarıldıktan sonra, bu cihazlar kaydedilebilir veya kaydedilmeyebilir ve durumları **Kayıtlı** veya **Bağlantı kurulmadı** olur. **Bağlantı kurulmadı**, cihazın Intune hizmetiyle hiç iletişim kurmadığı anlamına gelir.

## <a name="delete-a-csv-list"></a>.csv listesini silme

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2. Intune dikey penceresinde **Cihazları kaydet**’i ve ardından **Kurumsal Cihaz Tanımlayıcıları**’nı seçin.

3. **Sil**’i seçin.

Uluslararası Mobil Donanım Kimlikleri (IMEI) hakkındaki ayrıntılı belirtimler için bkz. [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).

