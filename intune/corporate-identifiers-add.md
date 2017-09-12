---
title: "Intune’a kurumsal tanımlayıcılar ekleme"
titlesuffix: Azure portal
description: "Microsoft Intune’a kurumsal tanımlayıcıları (kayıt yöntemi, IMEI ve seri numaraları) eklemeyi öğrenin. \""
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 85303c503e068ec23c8321b9359760775bbdb6f8
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2017
---
# <a name="identify-devices-as-corporate-owned"></a>Cihazları şirkete ait olarak tanımlama

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune yöneticisi olarak çeşitli yollarla bir cihazı şirkete ait olarak tanımlayabilirsiniz. Intune, şirkete ait cihazlardan ek bilgi toplayabilir. Şirkete ait olmayan cihazların kaydını önlemek için cihaz kısıtlamaları da ayarlayabilirsiniz.

Aşağıdaki koşullardan herhangi biri doğru olduğunda, bir cihaz şirkete ait olarak tanımlanır:

- [Cihaz kayıt yöneticisi](device-enrollment-manager-enroll.md) hesabıyla kaydedildi (tüm platformlar)
- Apple [Aygıt Kayıt Programı](device-enrollment-program-enroll-ios.md), [Apple School Manager](apple-school-manager-set-up-ios.md) veya [Apple Configurator](apple-configurator-enroll-ios.md) ile kaydedildi (yalnızca iOS)
- Bir uluslararası mobil ekipman tanımlayıcısı (IMEI) numarası (IMEI numarası olan tüm platformlar) veya seri numarası (iOS ve Android) ile [kayıttan önce şirkete ait olarak tanımlandı](#identify-corporate-owned-devices-with-imei-or-serial-number)
- Azure Active Directory veya Enterprise Mobility + Security’ye bir Windows 10 Enterprise cihazı olarak kaydedildi (yalnızca Windows 10)
- Cihazın özelliklerinde [cihaz sahipliği şirket](#change-device-ownership) olarak listelenmiş

## <a name="identify-corporate-owned-devices-with-imei-or-serial-number"></a>Şirkete ait cihazları IMEI veya seri numarası ile belirleme

Bir Intune yöneticisi olarak, IMEI numaralarını veya seri numaraları listeleyen bir virgülle ayrılmış değer (.csv) dosyası oluşturup içeri aktarabilirsiniz. Intune, cihaz kaydı sırasında cihaz sahipliğini şirket olarak belirtmek için bu tanımlayıcıları kullanır. Desteklenen tüm platformlar için IMEI numaraları bildirebilirsiniz. Yalnızca iOS ve Android cihazlar için seri numarası bildirebilirsiniz. Listede her IMEI numarası veya seri numarasının yönetim amacıyla belirtilen ayrıntıları bulunabilir.

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

[Apple cihaz seri numarasını bulmayı öğrenin](https://support.apple.com/HT204308).<br>
[Android cihazlarda seri numaranızı bulmayı öğrenin](https://support.google.com/store/answer/3333000).

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
> Bazı Android cihazları birden çok IMEI numarasına sahiptir. Intune, kayıtlı cihaz başına yalnızca bir IMEI numarasını okur. IMEI numarasını içeri aktarıyorsanız ancak bu numara Intune tarafından envantere alınan IMEI numarası değilse cihaz şirkete ait değil, kişisel cihaz olarak sınıflandırılır. Bir cihaz için birden fazla IMEI numarası içe aktarırsanız envantere alınmayan numaralar kayıt durumunda **Bilinmeyen** değerini görüntüler.<br>
>Ayrıca unutmayın: Android Seri numaralarının mevcut veya benzersiz olacağı garanti değildir. Seri numarasının güvenilir bir cihaz kimliği olup olmadığını anlamak için cihaz sağlayıcınızla görüşün.
>Cihazın Intune’a gönderdiği seri numaralar, cihazdaki Android Ayarları/Hakkında menülerinde gösterilen kimlikle eşleşmeyebilir. Cihaz üreticisi tarafından belirtilen seri numarasının türünü doğrulayın.

### <a name="add-a-csv-list-of-corporate-identifiers"></a>Kurumsal tanımlayıcıları içeren .csv listesini ekleme

1. Azure portalında Intune’da **Cihaz kaydı** > **Kurumsal Cihaz Tanımlayıcıları**’nı seçin ve **Ekle**’ye tıklayın.

 ![Kurumsal cihaz tanımlayıcısı çalışma alanının Ekle düğmesi vurgulanmış olarak ekran görüntüsü.](./media/add-corp-id.png)

2. **Tanımlayıcı Ekle** dikey penceresinde tanımlayıcı türünü belirtin: **IMEI**veya **Seri**. Önceden içeri aktarılan numaralar için **Mevcut tanımlayıcıların ayrıntılarının üzerine yazın** seçeneğini belirleyebilirsiniz.

3. Klasör simgesine tıklayın ve içeri aktarmak istediğiniz listenin yolunu belirtin. .csv dosyasına gidin ve **Ekle**’yi seçin. Yeni cihaz tanımlayıcılarını görmek için **Yenile**'ye tıklayabilirsiniz.

İçeri aktarılan cihazlar her zaman kaydedilmez. Cihazlar, **Kayıtlı** veya **Bağlantı kurulmadı** durumunda olabilir. **Bağlantı kurulmadı**, cihazın Intune hizmetiyle hiç iletişim kurmadığı anlamına gelir.

### <a name="delete-corporate-identifiers"></a>Kurumsal tanımlayıcıları silme

1. Azure portalında Intune’da **Cihaz kaydı** > **Kurumsal Cihaz Tanımlayıcıları**’nı seçin.
2. Silmek istediğiniz cihaz tanımlayıcılarını seçin ve **Sil**’e dokunun.
3. Silmeyi onaylayın.

Kayıtlı bir cihazın şirket tanımlayıcısını silmek, cihaz sahipliğini değiştirmez. Cihaz sahipliğini değiştirmek için **Cihazlar** > **Tüm cihazlar**’a gidin, cihazı seçin, **Özellikler**’i seçin ve **Cihaz sahipliği**’ni değiştirin.

### <a name="imei-specifications"></a>IMEI belirtimleri
Uluslararası Mobil Donanım Kimlikleri (IMEI) hakkındaki ayrıntılı belirtimler için bkz. [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).

## <a name="change-device-ownership"></a>Cihaz sahipliğini değiştirme

Intune’daki tüm cihaz kayıtlarının cihaz özelliklerinde **Sahiplik** görüntülenir. Yönetici olarak, cihazları **Kişisel** veya **Şirkete ait** olarak belirtebilirsiniz.

**Cihaz sahipliğini değiştirmek için:**
1. Azure portalında Intune’da, **Cihazlar** > **Tüm cihazlar**’a gidin ve cihazı seçin.
3. **Özellikler**’i seçin.
4. **Cihaz sahipliği**’ni **Kişisel** veya **Şirkete ait** olarak belirtin.

  ![Cihaz kategorisi ve Cihaz sahipliği seçeneklerini gösteren cihaz özellikleri ekran görüntüsü.](./media/device-properties.png)
