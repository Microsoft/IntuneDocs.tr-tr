---
title: "Intune'a IMEI tanımlayıcıları ekleme"
titleSuffix: Intune on Azure
description: "Microsoft Intune’a kurumsal tanımlayıcıları (IMEI numaraları) eklemeyi öğrenin. \""
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 57ab3b79ad53a4b195fac426d211a114f054602f
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="add-corporate-identifiers"></a>Kurumsal tanımlayıcılar ekleme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bir BT yöneticisi olarak, şirkete ait cihazları tanımlamak için uluslararası mobil donanım kimliği (IMEI) numaralarını veya seri numaraları listeleyen bir virgülle ayrılmış değer (.csv) dosyası oluşturup içeri aktarabilirsiniz. Yalnızca iOS ve Android cihazlar için seri numarası bildirebilirsiniz. Listede her IMEI numarası veya seri numarasının yönetim amacıyla belirtilen ayrıntıları bulunabilir.

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

[Apple cihaz seri numarasını bulmayı öğrenin](https://support.apple.com/HT204308).
[Android cihaz seri numaranızı bulmayı öğrenin](https://support.google.com/store/answer/3333000).

## <a name="add-corporate-identifiers"></a>Kurumsal tanımlayıcılar ekleme
Listeyi oluşturmak için iki sütunlu, üst bilgisi olmayan bir virgülle ayrılmış değerler (.csv) listesi oluşturun. IMEI numaralarını veya seri numaraları sol sütuna, ayrıntıları sağ sütuna ekleyin. Tek bir .csv dosyasında yalnızca tek bir kimlik türü: IMEI veya seri numarası içeri aktarılabilir. Ayrıntılar 128 karakterle sınırlıdır ve yalnızca yönetimsel kullanım içindir. Ayrıntılar cihazda görüntülenmez. Her .csv dosyası için geçerli sınır 500 satırdır.

**Seri numaraları olan bir .csv dosyası yükleme** – Üst bilgi içermeyen, iki sütunlu, virgülle ayrılmış değer (.csv) listesini oluşturun ve .csv dosyası başına 5.000 cihaz veya 5 MB ile sınırlayın.

|||
|-|-|
|&lt;Kimlik 1&gt;|&lt;Cihaz 1 Ayrıntıları&gt;|
|&lt;Kimlik 2&gt;|&lt;Cihaz 2 Ayrıntıları&gt;|

Bu .csv dosyası bir metin düzenleyicisinde görüntülendiğinde aşağıdaki gibi görünür:

```
01234567890123,device details
02234567890123,device details
```

> [!IMPORTANT]
> Bazı Android cihazları birden çok IMEI numarasına sahiptir. Intune, kayıtlı cihaz başına yalnızca bir IMEI numarasını okur. IMEI numarasını içeri aktarıyorsanız, ancak bu numara Intune tarafından envantere alınan IMEI numarası değilse, cihaz şirkete ait cihaz olarak değil, kişisel cihaz olarak sınıflandırılır. Bir cihaz için birden fazla IMEI numarası içe aktarırsanız, envantere alınmayan numaralar kayıt durumunda **Bilinmeyen** değeri görüntüler.

**Kurumsal tanımlayıcıları içeren .csv listesini eklemek için**

1. Intune portalında **Cihaz kaydı** > **Kayıt Kısıtlamaları**, **Kurumsal Cihaz Tanımlayıcıları**'nı seçin ve **Ekle**'ye tıklayın.

 ![Kurumsal cihaz tanımlayıcısı çalışma alanının Ekle düğmesi vurgulanmış olarak ekran görüntüsü.](./media/add-corp-id.png)

2. **Tanımlayıcıları Ekle** dikey penceresinde tanımlayıcı türünü, **IMEI**'yi veya **Seri**'yi seçin. Önceden içeri aktarılan numaralar için **Mevcut tanımlayıcıların ayrıntılarının üzerine yazın** seçeneğini belirleyebilirsiniz.

3. Klasör simgesine tıklayın ve içeri aktarmak istediğiniz listenin yolunu belirtin. .csv dosyasına gidin ve **Ekle**’yi seçin. Yeni cihaz tanımlayıcılarını görmek için **Yenile**'ye tıklayabilirsiniz.

İçeri aktarıldıktan sonra, bu cihazlar kaydedilebilir veya kaydedilmeyebilir ve durumları **Kayıtlı** veya **Bağlantı kurulmadı** olur. **Bağlantı kurulmadı**, cihazın Intune hizmetiyle hiç iletişim kurmadığı anlamına gelir.

## <a name="delete--corporate-identifiers"></a>Kurumsal tanımlayıcıları silme

1. Intune portalında **Cihaz kaydı** > **Kayıt Kısıtlamaları**, **Kurumsal Cihaz Tanımlayıcıları**'nı seçin ve **Sil**'e tıklayın.

3. **Tanımlayıcıları Sil** dikey penceresinde silinecek cihazların tanımlayıcılarının yer aldığı .csv dosyasını bulun ve **Sil**'e tıklayın.

## <a name="imei-specifications"></a>IMEI belirtimleri
Uluslararası Mobil Donanım Kimlikleri (IMEI) hakkındaki ayrıntılı belirtimler için bkz. [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).
