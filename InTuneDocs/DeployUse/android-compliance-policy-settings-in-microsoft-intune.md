---
title: "Android cihazları için uyumluluk ilkesi ayarları | Microsoft Intune"
description: "Bu konu başlığı altında, Android cihazları için cihaz uyumluluk ilkesi ayarları açıklanır."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: be1ebcdf2514e45d383dd49890e0e21acf6ede44
ms.openlocfilehash: f99158924b83254efedb8663b9d6175a6b6775b1


---


# Microsoft Intune’da Android cihazları için uyumluluk ilkesi ayarları

Bu konu başlığı altında açıklanan ilke ayarları Android 4.0 ve üstünü veya Samsung KNOX 4.0 ve üstünü çalıştıran cihazlar için geçerlidir.

Diğer platformlar hakkında bilgi arıyorsanız, aşağıdakilerden birine bakın:
> [!div class="op_single_selector"]
- [iOS cihazları için uyumluluk ilkesi ayarları](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Windows cihazları için uyumluluk ilkesi ayarları](windows-compliance-policy-settings-in-microsoft-intune.md)

## Sistem güvenliği ayarları
### Parola
- **Mobil cihazların kilidini açmak için parola gerektir:** Kullanıcıların cihazlarına erişebilmek için bir parola girmelerini gerektirmek için bunu **Evet** olarak ayarlayın.

-  **Minimum parola uzunluğu:** Kullanıcı parolasının içermesi gereken minimum rakam veya karakter sayısını belirtin.

- **Parola kalitesi:** Android cihazlarda parola gereksinimlerini yapılandırmak için bu ayarı etkinleştirin. Aşağıdakilerden birini seçin:
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

### Şifreleme
- **Mobil cihazda şifreleme gerektir:** Cihazın kaynaklara bağlanmak için şifrelenmesini gerektirmek için bunu **Evet** olarak ayarlayın. **Mobil cihazların kilidini açmak için parola gerektir** ayarını yapılandırdığınızda cihazlar şifrelenir.

## Cihaz sistem durumu ve güvenlik ayarları

- **Cihazda jailbreak uygulanmamış veya kök erişim izni verilmemiş olmalıdır:** Bu ayarı etkinleştirirseniz, jailbreak uygulanmış cihazlar uyumsuz olarak değerlendirilir.
- **Cihazların bilinmeyen kaynaklardan uygulama yüklemeyi önlemesini iste (Android 4.0 veya sonrası)** Üzerinde **Güvenlik > Bilinmeyen kaynaklar** etkinleştirilmiş cihazları engellemek için bu ayarı etkinleştirin ve **Evet** olarak işaretleyin.  
>[!IMPORTANT]
>Dışarıdan uygulama yükleme, **Bilinmeyen kaynaklar** ayarının etkinleştirilmesini gerektirir.  Bu uyumluluk ilkesini yalnızca cihazlara dışarıdan Android uygulaması yüklemiyorsanız zorlamalısınız.

- **USB hata ayıklamanın devre dışı bırakılmasını isteyin (Android 4.2 veya sonrası)**: Bu ayar, cihazdaki USB hata ayıklama seçeneğinin etkin olup olmadığının algılanması gerektiğini belirtir.
- **Cihazların güvenlik tehditleri için taramayı etkinleştirmesini isteyin (Android 4.2-4.4)**: Bu ayar, **Uygulamaları doğrula** özelliğinin cihazda etkinleştirilmesinin gerektiğini belirtir.
- **En düşük Android güvenlik düzeltme eki düzeyi (Android 6.0 veya sonrası)**: En düşük Android düzeltme eki düzeyini belirtmek için bu ayarı kullanın.  En az bu düzeltme eki düzeyinde olmayan cihazlar uyumsuz kabul edilir. Tarih GG-AA-YYYY biçiminde belirtilmelidir.


## Cihaz özelliği ayarları
- **Gerekli en düşük işletim sistemi:** Cihaz en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumsuz olarak bildirilir.
  Yükseltme hakkında bilgi içeren bir bağlantı görüntülenir. Son kullanıcı, şirket kaynaklarına erişebilmek için cihazını yükseltmeyi seçebilir.

- **İzin verilen en yüksek işletim sistemi sürümü:** Cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullandığında, şirket kaynaklarına erişim engellenir ve kullanıcıdan BT yöneticisine başvurması istenir. Kuralda işletim sistemine izin veren bir değişiklik oluncaya kadar bu cihaz şirket kaynaklarına erişmek için kullanılamaz.



<!--HONumber=Jul16_HO5-->


