---
title: Intune 'a kurumsal tanımlayıcılar ekleme
titleSuffix: ''
description: Microsoft Intune için kurumsal tanımlayıcıların (kayıt yöntemi, ıMEı ve seri numaraları) nasıl ekleneceğini öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: spshumwa
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: afc9d953e1d324adb3f00eb5209732a858bbbcda
ms.sourcegitcommit: 45d7c76e760c5117bf134fb57f7e248e5b6c4ad5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72314684"
---
# <a name="identify-devices-as-corporate-owned"></a>Cihazları şirkete ait olarak tanımla

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bir Intune Yöneticisi olarak, yönetim ve tanımlamayı iyileştirmek için cihazları şirkete ait olarak belirleyebilirsiniz. Intune, ek yönetim görevleri gerçekleştirebilir ve şirketin sahip olduğu cihazlardan tam telefon numarası ve uygulama envanteri gibi ek bilgiler toplayabilir. Ayrıca, şirkete ait olmayan cihazların kaydını engellemek için cihaz kısıtlamalarını da ayarlayabilirsiniz.

Kayıt sırasında, Intune aşağıdakiler olan cihazlara şirkete ait durumu otomatik olarak atar:

- Bir [Cihaz Kayıt Yöneticisi](device-enrollment-manager-enroll.md) hesabıyla (tüm platformlar) kayıtlı
- Apple [aygıt kayıt programı](device-enrollment-program-enroll-ios.md), [Apple Okul Yöneticisi](apple-school-manager-set-up-ios.md)veya [Apple Configurator](apple-configurator-enroll-ios.md) 'a kaydolmuş (yalnızca iOS)
- Uluslararası bir mobil ekipman tanımlayıcısı (ıMEı) numarası (ıMEı numarası olan tüm platformlar) veya seri numarası (iOS ve Android) ile [kayıt yapılmadan önce şirkete ait olarak tanımlanır](#identify-corporate-owned-devices-with-imei-or-serial-number)
- İş veya okul kimlik bilgileriyle Azure Active Directory katıldı. [Azure Active Directory kayıtlı olan cihazlar](https://docs.microsoft.com/azure/active-directory/devices/overview) kişisel olarak işaretlenir.
- [Cihazın Özellikler listesinde](#change-device-ownership) şirket olarak ayarla

Kayıttan sonra, **Kişisel** ve **Şirket**arasındaki [sahiplik ayarını değiştirebilirsiniz](#change-device-ownership) .

## <a name="identify-corporate-owned-devices-with-imei-or-serial-number"></a>Şirkete ait cihazları ıMEı veya seri numarası ile tanımla

Bir Intune Yöneticisi olarak, 14 basamaklı ıMEı numaralarını veya seri numaraları listeleyen bir virgülle ayrılmış değer (. csv) dosyası oluşturup içeri aktarabilirsiniz. Intune, cihaz kaydı sırasında cihaz sahipliğini şirket olarak belirtmek için bu tanımlayıcıları kullanır. Her ıMEı veya seri numarası, yönetim amaçları için listede belirtilen ayrıntılara sahip olabilir.

Bu özellik aşağıdaki platformlar için desteklenir:

| Platform | IMEı numaraları | Seri numaraları |
|---|---|---|
| Windows | Desteklenen (Windows Phone) | Desteklenmiyor |
| iOS/macOS | Desteklenmiyor | Desteklenen |
| Cihaz Yöneticisi yönetilen Android OS ile v10 arasındaki | Desteklenmiyor | Desteklenmiyor |
| Diğer Android | Desteklenmiyor | Desteklenen |

<!-- When you upload serial numbers for corporate-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as corporate-owned. -->

[Apple cihaz seri numarasını bulmayı öğrenin](https://support.apple.com/HT204308).<br>
[Android cihaz seri numaranızı bulmayı öğrenin](https://support.google.com/store/answer/3333000).

## <a name="add-corporate-identifiers-by-using-a-csv-file"></a>Bir. csv dosyası kullanarak kurumsal tanımlayıcılar ekleme
Listeyi oluşturmak için, üst bilgisi olmayan iki sütunlu, virgülle ayrılmış değer (. csv) listesi oluşturun. Sol sütunda 14 basamaklı ıMEı veya seri numaralarını ve sağ sütundaki ayrıntıları ekleyin. Tek bir. csv dosyasına yalnızca bir tür ID, ıMEı veya seri numarası aktarılabilir. Ayrıntılar 128 karakterle sınırlıdır ve yalnızca yönetim kullanımı içindir. Ayrıntılar cihazda görüntülenmiyor. Geçerli sınır. csv dosyası başına 5.000 satır.

**Seri numaralarını içeren bir. csv dosyasını karşıya yükleyin** – üst bilgi içermeyen iki sütunlu, virgülle ayrılmış değer (. csv) listesi oluşturun ve listeyi. csv dosyası başına 5.000 cihaz veya 5 MB ile sınırlayın.

|||
|-|-|
|&lt;ıD #1 &gt;|&lt;Device #1 Ayrıntılar @ no__t-1|
|&lt;ıD #2 &gt;|&lt;Device #2 Ayrıntılar @ no__t-1|

Bu. csv dosyası bir metin düzenleyicisinde görüntülendiğinde şöyle görünür:

```
01234567890123,device details
02234567890123,device details
```

> [!IMPORTANT]
> Bazı Android ve iOS cihazlarında birden çok ıMEı numarası vardır. Intune, kayıtlı cihaz başına yalnızca bir ıMEı numarasını okur. IMEı numarasını içeri aktarırsanız ancak Intune tarafından envantere alınan ıMEı değilse, cihaz şirkete ait bir cihaz yerine kişisel cihaz olarak sınıflandırılır. Bir cihaz için birden fazla ıMEı numarası içe aktarırsanız, envantere alınmayan numaralar kayıt durumu için **bilinmiyor** olarak görüntülenir.<br>
>Ayrıca Note: seri numaralar, iOS cihazları için önerilen tanımlama biçimidir.
>Android seri numaralarının benzersiz olması veya mevcut olmaması garanti edilmez. Seri numarasının güvenilir bir cihaz KIMLIĞI olup olmadığını anlamak için cihaz sağlayıcınızla görüşün.
>Cihaz tarafından Intune 'a bildirilen seri numaraları, cihazdaki Android ayarları/hakkında menülerindeki görünen KIMLIKLE eşleşmeyebilir. Cihaz üreticisi tarafından bildirilen seri numarası türünü doğrulayın.
>Nokta (.) içeren seri numaralarına sahip bir dosya karşıya yüklenmeye çalışılması, yüklemenin başarısız olmasına neden olur. Noktalarla seri numaralar desteklenmez.

### <a name="upload-a-csv-list-of-corporate-identifiers"></a>Kurumsal tanımlayıcıların bir. csv listesini karşıya yükle

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın, **cihaz kaydı** > **Kurumsal cihaz tanımlayıcıları** > **Add** > **CSV dosyasını karşıya yükle**' yi seçin.

   ![Ekle düğmesi vurgulanmış şekilde kurumsal cihaz tanımlayıcısı çalışma alanı](./media/corporate-identifiers-add/add-corp-id.png)

2. **Tanımlayıcıları Ekle** dikey penceresinde tanımlayıcı türünü belirtin: **IMEI** veya **seri**.

3. Klasör simgesine tıklayıp içeri aktarmak istediğiniz listenin yolunu belirtin. . Csv dosyasına gidin ve **Ekle**' yi seçin. 

4. . Csv dosyası zaten Intune 'da olan ancak farklı ayrıntılara sahip olan şirket tanımlayıcılarını içeriyorsa, **yinelenen tanımlayıcıları gözden geçir** açılır penceresi görüntülenir. Intune 'a üzerine yazmak istediğiniz tanımlayıcıları seçin ve tanımlayıcıları eklemek için **Tamam** ' ı seçin. Her tanımlayıcı için yalnızca ilk yineleme karşılaştırılır.

## <a name="manually-enter-corporate-identifiers"></a>Şirket tanımlayıcılarını el ile girin

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın, **cihaz kaydı** > **Kurumsal cihaz tanımlayıcıları** > **Ekle** > **el ile girin**.

2. **Tanımlayıcıları Ekle** dikey penceresinde tanımlayıcı türünü belirtin: **IMEI** veya **seri**.

3. Eklemek istediğiniz her tanımlayıcı için **tanımlayıcıyı** ve **ayrıntıları** girin. Tanımlayıcıları girmeyi tamamladığınızda **Ekle**' yi seçin.

5. Zaten Intune 'da olan ancak farklı ayrıntılara sahip olan kurumsal tanımlayıcılar girdiyseniz **yinelenen tanımlayıcıları gözden geçir** açılır penceresi görüntülenir. Intune 'a üzerine yazmak istediğiniz tanımlayıcıları seçin ve tanımlayıcıları eklemek için **Tamam** ' ı seçin. Her tanımlayıcı için yalnızca ilk yineleme karşılaştırılır.

Yeni cihaz tanımlayıcılarını görmek için **Yenile** ' yi tıklatabilirsiniz.

İçeri aktarılan cihazların kayıtlı olması gerekmez. Cihazlar, **kayıtlı** veya **bağlantı kurulmamış**bir duruma sahip olabilir. **Bağlantı kurulmadı** , cihazın Intune hizmetiyle hiçbir şekilde iletişim kurmadığı anlamına gelir.

## <a name="delete-corporate-identifiers"></a>Kurumsal tanımlayıcıları silme

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın, **cihaz kaydı** > **Kurumsal cihaz tanımlayıcıları**' nı seçin.
2. Silmek istediğiniz cihaz tanımlayıcılarını seçin ve **Sil**' i seçin.
3. Silme işlemini onaylayın.

Kayıtlı bir cihazın kurumsal tanımlayıcısını silmek, cihazın sahipliğini değiştirmez. Bir cihazın sahipliğini değiştirmek için **cihazlar**' a gidin, cihazı seçin, **Özellikler**' i seçin ve **cihaz sahipliğini**değiştirin.

## <a name="imei-specifications"></a>IMEı belirtimleri
Uluslararası Mobil ekipman tanımlayıcıları hakkında ayrıntılı belirtimler için bkz. [3Ggpp 23,003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).

## <a name="change-device-ownership"></a>Cihaz sahipliğini değiştirme

Cihaz özellikleri, Intune 'daki her cihaz kaydı için **sahiplik** görüntüler. Yönetici olarak, cihazları **Kişisel** veya **Şirket**olarak belirtebilirsiniz.

**Cihaz sahipliğini değiştirmek için:**
1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın, **cihazlar** ' a gidin ve cihazı seçin.
2. **Özellikler**'i seçin.
3. **Cihaz sahipliğini** **Kişisel** veya **Şirket**olarak belirtin.

   ![Cihaz kategorisi ve cihaz sahipliği seçeneklerini gösteren cihaz özellikleri](./media/corporate-identifiers-add/device-properties.png)
