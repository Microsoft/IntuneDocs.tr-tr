---
title: Intune’a kurumsal tanımlayıcılar ekleme
titleSuffix: ''
description: Microsoft Intune Kurumsal tanımlayıcıları (kayıt yöntemi, IMEI ve seri numaraları) eklemeyi öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 28ad1e492c4bdd7c87371611530cd3f8e2abc2e1
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58798245"
---
# <a name="identify-devices-as-corporate-owned"></a>Cihazları şirkete ait olarak tanımlama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bir Intune yöneticisi olarak cihazları şirkete ait olarak tanımlayabilir, böylece yönetim ve tanımlama işlemlerini geliştirebilirsiniz. Intune, ek yönetim görevleri gerçekleştirebilir ve tam telefon numarası ile şirkete ait cihazların uygulama envanteri gibi ilave bilgiler toplayabilir. Şirkete ait olmayan cihazların kaydını engellemek için cihaz kısıtlamaları da ayarlayabilirsiniz.

Kayıt sırasında Intune, şu özellikleri taşıyan cihazlara otomatik olarak şirkete ait durumunu atar:

- [Cihaz kayıt yöneticisi](device-enrollment-manager-enroll.md) hesabıyla kaydedildi (tüm platformlar)
- Apple [Aygıt Kayıt Programı](device-enrollment-program-enroll-ios.md), [Apple School Manager](apple-school-manager-set-up-ios.md) veya [Apple Configurator](apple-configurator-enroll-ios.md) ile kaydedildi (yalnızca iOS)
- Bir uluslararası mobil ekipman tanımlayıcısı (IMEI) numarası (IMEI numarası olan tüm platformlar) veya seri numarası (iOS ve Android) ile [kayıttan önce şirkete ait olarak tanımlandı](#identify-corporate-owned-devices-with-imei-or-serial-number)
- Azure Active Directory'ye Windows 10 Enterprise cihazı olarak katılmış
- [Cihazın özellikler listesinde](#change-device-ownership) şirket olarak ayarlı

Kayıttan sonra **Kişisel** veya **Şirket** arasında [sahiplik ayarını değiştirebilirsiniz](#change-device-ownership).

## <a name="identify-corporate-owned-devices-with-imei-or-serial-number"></a>Şirkete ait cihazları IMEI veya seri numarası ile belirleme

Bir Intune Yöneticisi olarak oluşturabilir ve 14 basamaklı IMEI numaralarını veya seri numaraları listeleyen bir virgülle ayrılmış değer (.csv) dosyasını içeri aktarın. Intune, cihaz kaydı sırasında cihaz sahipliğini şirket olarak belirtmek için bu tanımlayıcıları kullanır. Desteklenen tüm platformlar için IMEI numaraları bildirebilirsiniz. Yalnızca iOS, macOS ve Android cihazlar için seri numarası bildirebilirsiniz. Listede her IMEI numarası veya seri numarasının yönetim amacıyla belirtilen ayrıntıları bulunabilir.

<!-- When you upload serial numbers for corporate-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as corporate-owned. -->

[Apple cihaz seri numarasını bulmayı öğrenin](https://support.apple.com/HT204308).<br>
[Android cihaz seri numaranızı bulmayı öğrenin](https://support.google.com/store/answer/3333000).

## <a name="add-corporate-identifiers-by-using-a-csv-file"></a>Bir .csv dosyası kullanarak kurumsal tanımlayıcılar ekleme
Listeyi oluşturmak için iki sütunlu, üst bilgisi olmayan bir virgülle ayrılmış değerler (.csv) listesi oluşturun. 14 basamaklı IMEI veya seri numaraları sol sütuna, ayrıntıları sağ sütuna ekleyin. Tek bir .csv dosyasında yalnızca tek bir kimlik türü: IMEI veya seri numarası içeri aktarılabilir. Ayrıntılar 128 karakterle sınırlıdır ve yalnızca yönetimsel kullanım içindir. Ayrıntılar cihazda görüntülenmez. Her .csv dosyası için geçerli sınır 5.000 satırdır.

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
> Bazı Android ve iOS cihazları birden çok IMEI numarasına sahiptir. Intune, kayıtlı cihaz başına yalnızca bir IMEI numarasını okur. IMEI numarasını içeri aktarıyorsanız, ancak Intune tarafından envantere alınan IMEI değil, cihazın kişisel bir cihazı şirkete ait cihaz olarak sınıflandırılır. Bir cihaz için birden fazla IMEI numarası içe aktarırsanız envantere alınmayan numaralar kayıt durumunda **Bilinmeyen** değerini görüntüler.<br>
>Ayrıca unutmayın: Seri numaralarını kimlik iOS cihazları için önerilen biçimindedir.
>Android seri numaralarının mevcut veya benzersiz olacağı garanti edilmez. Seri numarasının güvenilir bir cihaz kimliği olup olmadığını anlamak için cihaz sağlayıcınızla görüşün.
>Cihazın Intune’a gönderdiği seri numaralar, cihazdaki Android Ayarları/Hakkında menülerinde gösterilen kimlikle eşleşmeyebilir. Cihaz üreticisi tarafından belirtilen seri numarasının türünü doğrulayın.
>Nokta (.) içeren seri numaralara sahip bir dosya yükleme denemesi, karşıya yükleme işleminin başarısız olmasına yol açar. Nokta içeren seri numaraları desteklenmez.

### <a name="upload-a-csv-list-of-corporate-identifiers"></a>Kurumsal tanımlayıcıları içeren .csv listesini karşıya yükleme

1. [Azure portalında Intune’da](https://portal.azure.com) **Cihaz kaydı** > **Kurumsal cihaz tanımlayıcıları** > **Ekle** > **CSV dosyasını karşıya yükle**’yi seçin.

   ![Kurumsal cihaz tanımlayıcısı çalışma alanı ile Ekle düğmesinin vurgulanmış hali](./media/add-corp-id.png)

2. İçinde **tanımlayıcılar ekleme** dikey penceresinde tanımlayıcı türünü belirtin: **IMEI** veya **seri**.

3. Klasör simgesine tıklayın ve içeri aktarmak istediğiniz listenin yolunu belirtin. .csv dosyasına gidin ve **Ekle**’yi seçin. 

4. .csv dosyasında Intune’da zaten bulunan kurumsal tanımlayıcılar varsa ancak bunlar farkı ayrıntılara sahipse, **Yinelenen tanımlayıcıları gözden geçirin** açılır penceresi karşınıza çıkar. Intune’da üzerine yazmak istediğiniz tanımlayıcıları seçin ve **Tamam**’a tıklayarak bunları ekleyin. Her bir tanımlayıcı için yalnızca ilk yinelenen öğe karşılaştırılır.

## <a name="manually-enter-corporate-identifiers"></a>Kurumsal tanımlayıcıları el ile girme

1. [Azure portalında Intune’da](https://portal.azure.com) **Cihaz kaydı** > **Kurumsal cihaz tanımlayıcıları** > **Ekle** > **El ile gir**’i seçin.

2. İçinde **tanımlayıcılar ekleme** dikey penceresinde tanımlayıcı türünü belirtin: **IMEI** veya **seri**.

3. Eklemek istediğiniz tüm tanımlayıcılar için **Tanımlayıcı** ve **Ayrıntılar**’ı girin. Tanımlayıcıları girmeyi tamamladığınızda **Ekle**’yi seçin.

5. Intune’da zaten bulunan ancak farklı ayrıntılara sahip kurumsal tanımlayıcılar girdiyseniz, **Yinelenen tanımlayıcıları gözden geçirin** açılır penceresi karşınıza çıkar. Intune’da üzerine yazmak istediğiniz tanımlayıcıları seçin ve **Tamam**’a tıklayarak bunları ekleyin. Her bir tanımlayıcı için yalnızca ilk yinelenen öğe karşılaştırılır.

Yeni cihaz tanımlayıcılarını görmek için **Yenile**'ye tıklayabilirsiniz.

İçeri aktarılan cihazlar her zaman kaydedilmez. Cihazlar, **Kayıtlı** veya **Bağlantı kurulmadı** durumunda olabilir. **Bağlantı kurulmadı**, cihazın Intune hizmetiyle hiç iletişim kurmadığı anlamına gelir.

## <a name="delete-corporate-identifiers"></a>Kurumsal tanımlayıcıları silme

1. [Azure portalında Intune’da](https://portal.azure.com) **Cihaz kaydı** > **Kurumsal cihaz tanımlayıcıları**’nı seçin.
2. Silmek istediğiniz cihaz tanımlayıcılarını seçin ve **Sil**’e dokunun.
3. Silmeyi onaylayın.

Kayıtlı bir cihazın şirket tanımlayıcısını silmek, cihaz sahipliğini değiştirmez. Cihaz sahipliğini değiştirmek için **Cihazlar**’a gidip cihazı seçin, **Özellikler**’i seçin ve **Cihaz sahipliği**’ni değiştirin.

## <a name="imei-specifications"></a>IMEI belirtimleri
Uluslararası Mobil Donanım Kimlikleri (IMEI) hakkındaki ayrıntılı belirtimler için bkz. [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).

## <a name="change-device-ownership"></a>Cihaz sahipliğini değiştirme

Intune’daki tüm cihaz kayıtlarının cihaz özelliklerinde **Sahiplik** görüntülenir. Yönetici olarak, cihazları **Kişisel** veya **Şirkete ait** olarak belirtebilirsiniz.

**Cihaz sahipliğini değiştirmek için:**
1. [Azure portalında Intune](https://portal.azure.com)’da, **Cihazlar**’a gidin ve cihazı seçin.
2. Seçin **özellikleri**.
3. **Cihaz sahipliği**’ni **Kişisel** veya **Şirkete ait** olarak belirtin.

   ![Cihaz kategorisi ve Cihaz sahipliği seçeneklerini gösteren cihaz özellikleri](./media/device-properties.png)
