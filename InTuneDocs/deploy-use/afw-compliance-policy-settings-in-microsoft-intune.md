---
title: "Android for Work için uyumluluk ilkesi ayarları | Microsoft Intune"
description: "Bu konuda, Android for Work ile uyumlu Android cihazlar için cihaz uyumluluk ilkesi ayarları açıklanır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 050da562fb03bbc32c4a7c293b6faad4f87ab78e


---


# <a name="compliance-policy-settings-for-android-for-work-devices-in-microsoft-intune"></a>Microsoft Intune’da Android for Work cihazlar için uyumluluk ilkesi ayarları

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

Bu konuda açıklanan ilke ayarları Android for Work cihazlar için geçerlidir.

Diğer platformlar hakkında bilgi arıyorsanız, aşağıdakilerden birine bakın:
> [!div class="op_single_selector"]
- [Android için uyumluluk ilkesi ayarları](android-compliance-policy-settings-in-microsoft-intune.md)
- [iOS cihazları için uyumluluk ilkesi ayarları](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Windows cihazları için uyumluluk ilkesi ayarları](windows-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a>Sistem güvenliği ayarları
### <a name="password"></a>Parola
- **Mobil cihazların kilidini açmak için parola gerektir:** Kullanıcıların cihazlarına erişebilmek için bir parola girmelerini gerektirmek için bunu **Evet** olarak ayarlayın.

-  **Minimum parola uzunluğu:** Kullanıcı parolasının içermesi gereken minimum rakam veya karakter sayısını belirtin.

- **Parola kalitesi:** Bu ayar, belirttiğiniz parola gereksinimlerinin cihazda yapılandırılıp yapılandırılmadığını algılar. Android cihazlarda kullanıcıların belirli parola gereksinimleri yapılandırmasını gerekli hale getirmek için bu ayarı etkinleştirin. Aşağıdakilerden birini seçin:
  -   **Düşük güvenlik biyometriği**
  - **Gerekli**
  -   **En az sayısal**
  -   **En az alfabetik**
  -   **En az alfasayısal**
  -   **Simgelerle alfasayısal**

- **Parola istenmeden önceki bekleme süresi (dakika olarak:**  Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi belirtir.

- **Parola kullanım süresi (gün):** Kullanıcı parolasının süresi dolup yeni bir parola oluşturulması gerekmeden önce geçmesi gereken gün sayısını seçin.

- **Parola geçmişini anımsa:** Kullanıcının önceden kullanılan parolaları oluşturmasını engellemek için bu ayarı **Önceki parolaların yeniden kullanılmasını önle** ile birlikte kullanın.

- **Önceki parolaların yeniden kullanılmasını önle:** **Parola geçmişini anımsa** seçeneği belirlenirse, önceden kullanılmış ve yeniden kullanılamayacak olan parola sayısını belirtin.

- **Cihaz boşta durumundan çıkarken parola gerektir:** Bu ayar, **Parola gerektirmeden önce işlem yapılmadan geçen süre (dakika)** ayarıyla birlikte kullanılmalıdır. **Parola gerektirmeden önce işlem yapılmadan geçen süre (dakika)** ayarında belirtilen süre boyunca etkin olmayan bir cihaza erişmek için son kullanıcılardan bir parola girmesi istenir.

### <a name="encryption"></a>Şifreleme
- **Mobil cihazda şifreleme iste:** Android for Work cihazlarda şifreleme zorunlu olduğundan bu ayarı yapılandırmanız gerekmez.

## <a name="device-health-and-security-settings"></a>Cihaz sistem durumu ve güvenlik ayarları

- **Cihazda jailbreak uygulanmamış veya kök erişim izni verilmemiş olmalıdır:** Bu ayarı etkinleştirirseniz, jailbreak uygulanmış cihazlar uyumsuz olarak değerlendirilir.
- **Cihazların bilinmeyen kaynaklardan uygulama yüklemeyi önlemesini iste:** Android for Work cihazlar bilinmeyen kaynaklardan yüklemeyi her zaman kısıtladığı için bu Android ayarını yapılandırmanız gerekmez. .  

- **USB hata ayıklamanın devre dışı olmasını iste**: Android for Work cihazlarda USB hata ayıklama zaten devre dışı olduğundan bu ayarları devre dışı bırakmanız gerekmez.

- **En düşük Android güvenlik düzeltme eki düzeyi **: En düşük Android düzeltme eki düzeyini belirtmek için bu ayarı kullanın.  En az bu düzeltme eki düzeyinde olmayan cihazlar uyumsuz kabul edilir. Tarih GG-AA-YYYY biçiminde belirtilmelidir.
- **Cihaz tehdit korumasının etkinleştirilmesini iste**: Lookout MTP çözümünden alınan risk değerlendirmesini uyumluluk koşulu olarak kullanmak için bu ayarı etkinleştirin. İzin verilen en yüksek tehdit düzeyini seçin. Bu düzey aşağıdakilerden biri olabilir:

  - **Hiçbiri (güvenli)**: Bu, en güvenli ayardır. Bu, cihazda herhangi bir tehdit olamayacağı anlamına gelir. Herhangi bir tehdit düzeyi algılanırsa cihaz, uyumlu değil olarak değerlendirilir.
  - **Düşük**: Cihaz, yalnızca düşük düzeydeki tehditler varsa uyumlu olarak değerlendirilir. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
  - **Orta**: Cihazdaki tehditler düşük veya orta düzeydeyse cihaz, uyumlu olarak değerlendirilir. Yüksek düzeyde tehditler algılanırsa cihaz, uyumlu değil olarak değerlendirilir.
  - **Yüksek**: Bu, güvenlik düzeyi en düşük olan seçenektir. Temel olarak, tüm tehdit düzeylerine izin verir ve yalnızca raporlama amacıyla kullandığınızda yararlı olabilir.

  Daha fazla ayrıntı için bkz. [Uyumluluk ilkesinde cihaz tehdit koruması kuralını etkinleştirme](enable-device-threat-protection-rule-in-compliance-policy.md).

## <a name="device-property-settings"></a>Cihaz özelliği ayarları
- **Gerekli en düşük işletim sistemi:** Cihaz en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumsuz olarak bildirilir.
  Yükseltme hakkında bilgi içeren bir bağlantı görüntülenir. Son kullanıcı, şirket kaynaklarına erişebilmek için cihazını yükseltmeyi seçebilir.

- **İzin verilen en yüksek işletim sistemi sürümü:** Cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullandığında, şirket kaynaklarına erişim engellenir ve kullanıcıdan BT yöneticisine başvurması istenir. Kuralda işletim sistemine izin veren bir değişiklik oluncaya kadar bu cihaz şirket kaynaklarına erişmek için kullanılamaz.



<!--HONumber=Dec16_HO2-->


