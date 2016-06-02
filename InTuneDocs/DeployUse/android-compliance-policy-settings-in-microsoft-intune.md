---
# required metadata

title: Android cihazları için uyumluluk ilkesi ayarları | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Microsoft Intune’da Android cihazları için uyumluluk ilkesi ayarları

Bu konu başlığı altında açıklanan ilke ayarları Android 4.0 ve üstünü veya Samsung KNOX 4.0 ve üstünü çalıştıran cihazlar için geçerlidir.

Diğer platformlar hakkında bilgi arıyorsanız, aşağıdakilerden birine bakın:
> [!div class="op_single_selector"]
- [iOS cihazları için uyumluluk ilkesi ayarları](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Windows cihazları için uyumluluk ilkesi ayarları](windows-compliance-policy-settings-in-microsoft-intune.md)

## Sistem güvenliği ayarları
### Parola
- **Mobil cihazların kilidini açmak için parola iste:** Kullanıcıların cihazlarına erişmeden önce parola girmelerini zorunlu tutmak için bunu **Evet**

-  olarak ayarlayın.

- **Minimum parola uzunluğu:** Kullanıcı parolasının içermesi gereken minimum rakam veya karakter sayısını belirtin. **Parola kalitesi:** Android cihazlarda parola gereksinimlerini yapılandırmak için bu ayarı etkinleştirin.
  -   **Aşağıdakilerden birini seçin:**
  - **Düşük güvenlik biyometriği**
  -   **Gerekli**
  -   **En az sayısal**
  -   **En az alfabetik**
  -   **En az alfasayısal**

- Simgelerle alfasayısal

- **Parola istenmeden önceki bekleme süresi (dakika olarak:**  Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi belirtir.

- **Parola kullanım süresi (gün olarak):** Kullanıcının parolasının süresi dolmadan ve yenisini oluşturması istenmeden

- önce geçecek gün sayısını seçin.

- **Parola geçmişini anımsa:** Kullanıcının önceden kullanılmış olan parolaları yeniden kullanmasını kısıtlamak için bu ayarı **Önceki parolaların yeniden kullanılmasını engelle** ayarıyla birlikte kullanın.

### **Önceki parolaların yeniden kullanılmasını engelle:** **Parola geçmişini anımsa** seçildiyse,
- önceden kullanılmış olan parolalardan kaç tanesinin yeniden kullanılamayacağını belirtin. Cihaz boş bir durumdan döndürüldüğünde parola iste:

## Bu ayar **Parola istenmeden önce geçen işlem yapılmayan dakika sayısı** ayarı ile birlikte kullanılmalıdır.

- Son kullanıcılardan,

## **Parola istenmeden önceki bekleme süresi (dakika olarak)** ayarında belirtilen süre boyunca etkin olmayan bir cihaza erişmek için son kullanıcılardan bir parola girmesi istenir.
- Şifreleme
  **Mobil cihazda şifreleme iste:** Cihazın kaynaklara bağlanabilmek amacıyla şifrelenmesini zorunlu tutmak için **Evet** olarak ayarlayın.

- Cihazların şifrelenmesi için, **Mobil cihazların kilidini açmak
  için parola iste** ayarı yapılandırılmalıdır.


<!--HONumber=May16_HO2-->


