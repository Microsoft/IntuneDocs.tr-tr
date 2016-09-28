---
title: "iOS cihazları için uyumluluk ilkesi ayarları | Microsoft Intune"
description: 
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a59d24f-ed58-49b1-b874-b2d4aea3ec76
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4f98937d7adfc0c1584625303da3350785af8169
ms.openlocfilehash: a2f98bbd34cf8b0c86531ae6ff40b1044c15d8bd


---


# Microsoft Intune’da iOS cihazları için uyumluluk ilkesi ayarları

Bu konu başlığı altında açıklanan ilke ayarları iOS 8.0 ve üstünü çalıştıran cihazlar için geçerlidir.

Diğer platformlar hakkında bilgi arıyorsanız, aşağıdakilerden birine bakın:
> [!div class="op_single_selector"]
- [Android cihazları için uyumluluk ilkesi ayarları](android-compliance-policy-settings-in-microsoft-intune.md)
- [Windows cihazları için uyumluluk ilkesi ayarları](windows-compliance-policy-settings-in-microsoft-intune.md)

## Sistem güvenliği ayarları
### Parola
- **Mobil cihazların kilidini açmak için parola gerektir:** Kullanıcıların cihazlarına erişebilmek üzere bir parola girmelerini gerektirmek için bunu **Evet** olarak ayarlayın. Parola kullanan iOS cihazları şifrelenir.

- **Basit parolalara izin ver:** Kullanıcıların ‘**1234**’ veya ‘**1111**’ gibi basit parolalar oluşturmalarına izin vermek için bunu **Evet** olarak ayarlayın.

-  **Minimum parola uzunluğu:** Kullanıcı parolasının içermesi gereken minimum rakam veya karakter sayısını belirtin.
- **Gerekli parola türü:** Kullanıcının oluşturacağı parolanın **Alfasayısal** mı, yoksa **Sayısal** mı olacağını belirtin.

- **Karakter kümesi sayısı alt sınırı:** **Gerekli parola türü** **Alfasayısal** olarak ayarlandıysa, bu ayar, parolanın içermesi gereken karakter kümesi sayısı alt sınırını belirtir. Dört karakter kümesi şunlardır:
  -   Küçük harfler
  -   Büyük harfler
  -   Simgeler
  -   Sayılar

  Bu ayar için daha yüksek bir sayı ayarlandığında, kullanıcıların daha karmaşık parolalar oluşturması zorunlu tutulur.

  iOS cihazları için bu ayar, parolaya eklenmesi gereken özel karakterlerin (örneğin, **!**, **#**, **&amp;**) sayısını gösterir.
- **Parola istenmeden önceki bekleme süresi (dakika olarak:**  Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi belirtin.

- **Parola kullanım süresi (gün):** Kullanıcı parolasının süresi dolup yeni bir parola oluşturulması gerekmeden önce geçmesi gereken gün sayısını seçin.

- **Parola geçmişini anımsa:** Kullanıcının önceden kullanılan parolaları oluşturmasını engellemek için bu ayarı **Önceki parolaların yeniden kullanılmasını önle** ile birlikte kullanın.

- **Önceki parolaların yeniden kullanılmasını önle:** **Parola geçmişini anımsa** seçeneği belirlenirse, önceden kullanılmış ve yeniden kullanılamayacak olan parola sayısını belirtin.

- **Cihaz boşta durumundan çıkarken parola gerektir:** Bu ayar, **Parola gerektirmeden önce işlem yapılmadan geçen süre (dakika)** ayarıyla birlikte kullanılmalıdır. **Parola istenmeden önceki bekleme süresi (dakika olarak)** ayarında belirtilen süre boyunca etkin olmayan bir cihaza erişmek için son kullanıcılardan bir parola girmesi istenir.

### E-posta profili
- **E-posta hesabı Intune tarafından yönetilmelidir:** Bu seçenek **Evet** olarak ayarlandığında, cihazın kendisine dağıtılan uyumsuz e-postayı kullanması gerekir. Aşağıdaki durumlarda cihaz uyumsuz olarak kabul edilir:
  - Uyumluluk ilkesi tarafından hedeflenen kullanıcı grubuna e-posta profilinin de dağıtılması gerekir, yoksa kullanıcıların cihazları uyumsuz olarak kabul edilir.
  - Kullanıcı cihazda zaten bir e-posta hesabı ayarlamışsa ve bu hesap cihaza dağıtılan Intune e-posta profiliyle eşleşiyorsa, cihazın uyumsuz olduğu raporlanır. Intune, kullanıcı tarafından sağlanan profilin üzerine yazamaz ve bu nedenle yönetemez. Uyumluluk sağlamak için kullanıcı varolan e-posta ayarları kaldırmalıdır, böylece Intune yönetilen e-posta profilini yükleyebilir.


- **Intune tarafından yönetilmesi gereken e-posta profilini seçin:**
   **E-posta hesabı Intune tarafından yönetilmelidir** ayarı seçildiyse, Intune e-posta profilini belirtmek için **Seçin**’i işaretleyin. E-posta profili cihazda mevcut olmalıdır.

     E-posta profilleri hakkında ayrıntılı bilgi için bkz. [Microsoft Intune ile e-posta profilleri kullanarak şirket e-postasına erişimi yapılandırma](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).

## Cihaz durumu ayarları

- **Cihazda jailbreak uygulanmamış veya kök erişim izni verilmemiş olmalıdır:** Bu ayarı etkinleştirirseniz, jailbreak uygulanmış cihazlar uyumlu olmaz.

##  Cihaz özellikleri
- **Gerekli en düşük işletim sistemi:** Cihaz en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumsuz olarak bildirilir.
Yükseltme hakkında bilgi içeren bir bağlantı görüntülenir. Son kullanıcı, şirket kaynaklarına erişebilmek için cihazını yükseltmeyi seçebilir.

- **İzin verilen en yüksek işletim sistemi sürümü:** Cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullandığında, şirket kaynaklarına erişim engellenir ve kullanıcıdan BT yöneticisine başvurması istenir. Kuralda işletim sistemine izin veren bir değişiklik oluncaya kadar bu cihaz şirket kaynaklarına erişmek için kullanılamaz.



<!--HONumber=Sep16_HO2-->


