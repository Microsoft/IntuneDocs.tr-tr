---
# required metadata

title: iOS cihazları için uyumluluk ilkesi ayarları | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 4a59d24f-ed58-49b1-b874-b2d4aea3ec76

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Microsoft Intune’da iOS cihazları için uyumluluk ilkesi ayarları

Bu konu başlığı altında açıklanan ilke ayarları iOS 6 ve üstünü çalıştıran cihazlar için geçerlidir.

Diğer platformlar hakkında bilgi arıyorsanız, aşağıdakilerden birine bakın:
> [!div class="op_single_selector"]
- [Android cihazları için uyumluluk ilkesi ayarları](android-compliance-policy-settings-in-microsoft-intune.md)
- [Windows cihazları için uyumluluk ilkesi ayarları](windows-compliance-policy-settings-in-microsoft-intune.md)

## Sistem güvenliği ayarları
### Parola
- **Mobil cihazların kilidini açmak için parola iste:**    Kullanıcıların cihazlarına erişmeden önce parola girmelerini zorunlu tutmak için bunu **Evet** olarak ayarlayın.

- Parola kullanan iOS cihazları şifrelenir.

-  **Basit parolalara izin ver:**   Kullanıcıların
- ‘**1234**’ veya

- ‘**1111**’ gibi basit parolalar oluşturmasına izin vermek için **Evet** olarak ayarlayın. Minimum parola uzunluğu:
  -   Kullanıcı parolasının içermesi gereken
  -   minimum rakam veya karakter sayısını belirtin.
  -   **Gerekli parola türü:** Kullanıcının
  -   **Alfasayısal** parola mı yoksa **Sayısal** parola mı oluşturması gerektiğini belirtin.

  **Minimum karakter kümesi sayısı:** **Gerekli parola türü**’nü

  **Alfasayısal** olarak ayarladıysanız, parolanın içermesi gereken
- minimum karakter kümesi sayısını belirtmek için bu ayarı kullanın.

- Dört karakter kümesi şunlardır:

- Küçük harfler

- Büyük harfler

- Simgeler Sayılar

### Bu ayar için daha yüksek bir sayı ayarlandığında, kullanıcıların daha karmaşık parolalar oluşturması zorunlu tutulur.
- iOS cihazlar için bu ayar, parolaya eklenmesi gereken özel karakterlerin (örneğin, **!**, **#**, **&amp;**) sayısını gösterir. **Parola istenmeden önceki bekleme süresi (dakika olarak:**  Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi belirtin.
  - **Parola kullanım süresi (gün olarak):** Kullanıcının parolasının süresi dolmadan ve yenisini oluşturması istenmeden
  - önce geçecek gün sayısını seçin. **Parola geçmişini anımsa:** Kullanıcının önceden kullanılmış olan parolaları yeniden kullanmasını kısıtlamak için bu ayarı **Önceki parolaların yeniden kullanılmasını engelle** ayarıyla birlikte kullanın.


- **Önceki parolaların yeniden kullanılmasını engelle:** **Parola geçmişini anımsa** seçildiyse, önceden kullanılmış olan parolalardan kaç tanesinin yeniden kullanılamayacağını belirtin.

     Cihaz boş bir durumdan döndürüldüğünde parola iste:

## Bu ayar **Parola istenmeden önce geçen işlem yapılmayan dakika sayısı** ayarı ile birlikte kullanılmalıdır.

- Son kullanıcılardan,

##  **Parola istenmeden önceki bekleme süresi (dakika olarak)** ayarında belirtilen süre boyunca etkin olmayan bir cihaza erişmek için bir parola girmesi istenir.
- E-posta profili
**E-posta hesabı Intune tarafından yönetilmelidir:** Bu seçenek **Evet** olarak ayarlandığında, cihazın kendisine dağıtılan uyumsuz e-postayı kullanması gerekir. Aşağıdaki durumlarda cihaz uyumsuz olarak kabul edilir:

- Uyumluluk ilkesi tarafından hedeflenen kullanıcı grubuna e-posta profilinin de dağıtılması gerekir, yoksa kullanıcıların cihazları uyumsuz olarak kabul edilir. Kullanıcı cihazda zaten bir e-posta hesabı ayarlamışsa ve bu hesap cihaza dağıtılan Intune e-posta profiliyle eşleşiyorsa, cihazın uyumsuz olduğu raporlanır.


<!--HONumber=May16_HO2-->


