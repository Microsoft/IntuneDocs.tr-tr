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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 25414cd42159d1c3e09b80d236ccb12f0df5662a
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017

---

# <a name="add-corporate-identifiers"></a>Kurumsal tanımlayıcılar ekleme

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Bir BT yöneticisi olarak, şirkete ait cihazları tanımlamak için kullanılan Uluslararası Mobil Donanım Kimliği (IMEI) numaralarının listelendiği bir virgülle ayrılmış değerler (.csv) dosyası oluşturabilir ve içeri aktarabilirsiniz. Her IMEI numarasının, listede yönetim amacıyla belirtilen ayrıntıları bulunabilir.

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

## <a name="add-corporate-identifiers"></a>Kurumsal tanımlayıcılar ekleme
Listeyi oluşturmak için iki sütunlu, üst bilgisi olmayan bir virgülle ayrılmış değerler (.csv) listesi oluşturun. Sol sütuna IMEI tanımlayıcısını ve sağ sütuna ayrıntıları ekleyin. Ayrıntılar 128 karakterle sınırlıdır ve yalnızca yönetimsel kullanım içindir. Ayrıntılar cihazda görüntülenmez. Her .csv dosyası için geçerli sınır 500 satırdır.

**Seri numaraları olan bir .csv dosyası yükleme** – Üst bilgi içermeyen, iki sütunlu, virgülle ayrılmış değer (.csv) listesini oluşturun ve .csv dosyası başına 5.000 cihaz veya 5 MB ile sınırlayın. 

|||
|-|-|
|&lt;IMEI 1&gt;|&lt;Cihaz 1 Ayrıntıları&gt;|
|&lt;IMEI 2&gt;|&lt;Cihaz 2 Ayrıntıları&gt;|

Bu .csv dosyası bir metin düzenleyicisinde görüntülendiğinde aşağıdaki gibi görünür:

```
01234567890123,device details
02234567890123,device details
```


> [!IMPORTANT]
> Bazı Android cihazları birden çok IMEI numarasına sahiptir. Intune, cihaz başına bir IMEI numarası envanteri oluşturur. IMEI numarasını içeri aktarıyorsanız, ancak bu numara Intune tarafından envantere alınan IMEI numarası değilse, cihaz şirkete ait cihaz olarak değil, kişisel cihaz olarak sınıflandırılır. Bir cihaz için birden fazla IMEI numarası içe aktarırsanız, envantere alınmayan numaralar kayıt durumunda **Bilinmeyen** değeri görüntüler.

**Kurumsal tanımlayıcıları içeren .csv listesini eklemek için**

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2. Intune dikey penceresinde **Cihaz kaydı** > **Kayıt Kısıtlamaları**, **Kurumsal Cihaz Tanımlayıcıları**'nı seçin ve **Ekle**'ye tıklayın.

3. **Tanımlayıcıları Ekle** dikey penceresinde **IMEI** tanımlayıcı türünü seçin. Önceden içeri aktarılan numaralar için **Mevcut tanımlayıcıların ayrıntılarının üzerine yazın** seçeneğini belirleyebilirsiniz.  

4. Klasör simgesine tıklayın ve içeri aktarmak istediğiniz listenin yolunu belirtin. IMEI CSV dosyasına gidin ve **Ekle**’yi seçin.

İçeri aktarıldıktan sonra, bu cihazlar kaydedilebilir veya kaydedilmeyebilir ve durumları **Kayıtlı** veya **Bağlantı kurulmadı** olur. **Bağlantı kurulmadı**, cihazın Intune hizmetiyle hiç iletişim kurmadığı anlamına gelir.

## <a name="delete--corporate-identifiers"></a>Kurumsal tanımlayıcıları silme

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2. Intune dikey penceresinde **Cihaz kaydı** > **Kayıt Kısıtlamaları**, **Kurumsal Cihaz Tanımlayıcıları**'nı seçin ve **Sil**'e tıklayın.

3. **Tanımlayıcıları Sil** dikey penceresinde silinecek cihazların tanımlayıcılarının yer aldığı .csv dosyasını bulun ve **Sil**'e tıklayın.

## <a name="imei-specifications"></a>IMEI belirtimleri
Uluslararası Mobil Donanım Kimlikleri (IMEI) hakkındaki ayrıntılı belirtimler için bkz. [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).

