---
title: Android için uyumluluk ilkesi ayarları
description: Bu konu başlığı altında, Android cihazları için cihaz uyumluluk ilkesi ayarları açıklanır.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 01/23/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4bf478225c22597b1645fc7d18e4329560bb1f03
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="compliance-policy-settings-for-android-devices-in-microsoft-intune"></a>Microsoft Intune’da Android cihazları için uyumluluk ilkesi ayarları

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Bu konu başlığı altında açıklanan ilke ayarları, Android 4.0 ve üstü veya Samsung KNOX 4.0 ve üstünü çalıştıran cihazlar için geçerlidir.

Diğer platformlar hakkında bilgi arıyorsanız, aşağıdakilerden birini seçin:
> [!div class="op_single_selector"]
> - [iOS cihazları için uyumluluk ilkesi ayarları](ios-compliance-policy-settings-in-microsoft-intune.md)
> - [Windows cihazları için uyumluluk ilkesi ayarları](windows-compliance-policy-settings-in-microsoft-intune.md)
> - [Android for Work cihazları için uyumluluk ilkesi ayarları](afw-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a>Sistem güvenliği ayarları
### <a name="password"></a>Parola
- **Mobil cihazların kilidini açmak için parola iste:** Kullanıcıların cihazlarına erişebilmek için bir parola girmelerini istemek için bunu **Evet** olarak ayarlayın.

-  **En düşük parola uzunluğu:** Kullanıcı parolasının içermesi gereken en düşük rakam veya karakter sayısını belirtin.

- **Parola kalitesi:** Bu ayar, belirttiğiniz parola gereksinimlerinin cihazda ayarlanıp ayarlanmadığını algılar. Android cihazlarda kullanıcıların belirli parola gereksinimlerini karşılamasını gerekli hale getirmek için bu ayarı etkinleştirin. Aşağıdakilerden birini seçin:

  -   **Düşük güvenlik biyometriği**
  -   **Gerekli**
  -   **En az sayısal**
  -   **En az alfabetik**
  -   **En az alfasayısal**
  -   **Simgelerle alfasayısal**

- **Parola istenmeden önceki bekleme süresi (dakika olarak:**  Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi belirtin.

- **Parola kullanım süresi (gün):** Kullanıcı parolasının süresi dolup yeni bir parola oluşturulması gerekmeden önce geçmesi gereken gün sayısını seçin.

- **Parola geçmişini anımsama:** Kullanıcının önceden kullanılan parolaları oluşturmasını engellemek için bu ayarı **Önceki parolaların yeniden kullanılmasını önle** ile birlikte kullanın.

- **Önceki parolaların yeniden kullanılmasını önle:** Önceden kullanılmış ve tekrar kullanılamayacak parola sayısını belirtin (eğer **Parola geçmişini hatırla** seçildiyse).

- **Cihaz boşta durumundan çıkarken parola iste:** Bu ayarı,**Parola istenmeden önce geçen işlem yapılmayan süre (dakika)** ayarıyla birlikte kullanın. **Parola istenmeden önce geçen işlem yapılmayan süre (dakika)** ayarında, belirtilen süre boyunca etkin olmayan bir cihaza erişmek için son kullanıcıdan bir parola girmesi istenir.

### <a name="encryption"></a>Şifreleme
- **Mobil cihazda şifreleme gerektir:** Cihazın kaynaklara bağlanmak için şifrelenmiş olmasını gerektirmek üzere, bu seçeneği **Evet** olarak ayarlayın. **Mobil cihazların kilidini açmak için parola gerektir** ayarını yapılandırdığınızda cihazlar şifrelenir.

## <a name="device-health-and-security-settings"></a>Cihaz sistem durumu ve güvenlik ayarları

- **Cihazda jailbreak uygulanmamış veya kök erişim izni verilmemiş olmalıdır**: Bu ayarı etkinleştirirseniz, jailbreak uygulanmış cihazlar uyumsuz olarak değerlendirilir.
- **Cihazların bilinmeyen kaynaklardan uygulama yüklenmesini engellemesini gerektir (Android 4.0 veya üzeri)**: **Güvenlik > Bilinmeyen kaynaklar** ayarı etkinleştirilmiş cihazları engellemek için, bu ayarı etkinleştirin ve değerini **Evet** olarak belirleyin.  

>[!IMPORTANT]
>Dışarıdan uygulama yükleme, **Bilinmeyen kaynaklar** ayarının etkinleştirilmesini gerektirir. Bu uyumluluk ilkesini yalnızca cihazlara dışarıdan Android uygulaması yüklemiyorsanız zorlayın.

- **USB hata ayıklamanın devre dışı bırakılmasını gerektir (Android 4.2 veya üzeri)**: Cihazdaki USB hata ayıklama seçeneğinin etkin olma durumunun algılanıp algılanmayacağını belirlemek için bu ayarı kullanın.
- **Cihazlarda, Cihazı güvenlik tehditleri için tara seçeneğinin etkin olmasını gerektir (Android 4.2-4.4)**: **Uygulamaları doğrula** özelliğinin cihazda etkin olduğunu belirlemek için bu ayarı kullanın.
- **Android güvenlik düzeltme eki için en düşük düzey (Android 6.0 veya sonrası)**: En düşük Android düzeltme eki düzeyini belirlemek için bu ayarı kullanın.  En az bu düzeltme eki düzeyinde olmayan cihazlar uyumsuz kabul edilir. Tarih YYYY-AA-GG biçiminde belirtilmelidir.
- **Cihaz tehdit korumasının etkinleştirilmesini iste**: Lookout MTP çözümünden alınan risk değerlendirmesini uyumluluk koşulu olarak kullanmak için bu ayarı etkinleştirin. İzin verilen en yüksek tehdit düzeyini seçin. Bu düzey aşağıdakilerden biri olabilir:

  - **Hiçbiri (güvenli)**: Bu, en güvenli ayardır. Bu, cihazda herhangi bir tehdit olamayacağı anlamına gelir. Eğer cihazda herhangi bir tehdit algılanırsa, cihaz uyumsuz olarak değerlendirilir.
  - **Düşük**: Cihaz, yalnızca düşük düzeyde tehditler varsa uyumlu olarak değerlendirilir. Daha yüksek bir tehdit düzeyi, cihazı uyumsuz durumuna getirir.
  - **Orta**: Cihazdaki tehditler düşük veya orta düzeydeyse, cihaz uyumlu olarak değerlendirilir. Cihazda yüksek düzeyde tehditler algılanırsa, cihaz uyumsuz olarak değerlendirilir.
  - **Yüksek**: Bu, güvenlik düzeyi en düşük olan seçenektir. Temel olarak bu seçenek, tüm tehdit düzeylerine izin verir ve yalnızca raporlama amacıyla kullandığınızda yararlı olabilir.

  Daha fazla ayrıntı için bkz. [Lookout cihaz uyumluluk ilkesi oluşturma](create-lookout-device-compliance-policy.md).

## <a name="device-property-settings"></a>Cihaz özelliği ayarları

- **Gerekli en düşük işletim sistemi:** Cihaz, en düşük işletim sistemi sürümü gereksinimini karşılamadığında, uyumsuz olarak bildirilir.
  Yükseltmenin yapılması hakkındaki bilgilere yönelik bir bağlantı görüntülenir. Kullanıcı, şirket kaynaklarına erişebilmek için cihazını yükseltmeyi seçebilir.

- **İzin verilen en yüksek işletim sistemi:** Cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullanıyorsa, şirket kaynaklarına erişimi engellenir ve kullanıcıdan BT yöneticisine başvurması istenir. Kuralda ilgili işletim sistemi sürümüne izin veren bir değişiklik oluncaya kadar, bu cihaz şirket kaynaklarına erişmek için kullanılamaz.
