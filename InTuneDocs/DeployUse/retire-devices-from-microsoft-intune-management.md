---
# required metadata

title: Cihazları devre dışı bırakma | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Cihazları Intune yönetiminde devre dışı bırakma

Cihazlar ister şirkete ait ister kişisel olsun, belirli bir noktaya gelindiğinde yönetilen cihazın Intune’da yönetimden kaldırılmaı gerekir. Cihazı devre dışı bırakma, görece sorunsuz bir işlemdir; seçmeli temizleme veya tam temizleme yaparsınız.
## Cihazdan verileri ve uygulamaları temizleme
Hem seçmeli temizleme hem de tam temizleme, ilkesini ve şirket portalını kaldırarak cihazı Intune yönetiminden kaldırır. Bu da, artık cihazın Microsoft SharePoint, e-posta veya Office 365 gibi şirket kaynaklarında oturum açmak için gereken kimlik bilgilerine sahip olmadığı anlamına gelir.

[Seçmeli temizleme](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) cihazdaki kişisel bilgileri etkilemediğinden, Intune’a kendi cihazını kaydetmiş olan çalışanlar için tercih edilen işlemdir. Yalnızca şirket verileri kaldırılır.

Şirkete ait cihazlarda, cihazı fabrika ayarlarına sıfırlayan [tam temizleme](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe) işlemini de kullanabilirsiniz.

## Şirket ağına erişimi iptal etme
Bir çalışan şirketten ayrıldığı ve şirkete ait donanımı geri vermeyi ihmal ettiği için cihazı devre dışı bırakıyorsanız, cihazı [uzaktan kilitlemeniz](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) de mümkündür. Bu seçenek, cihazı gözden çıkarmanıza yol açabilecek olsa da hem şirket bilgilerinin hem de şirket donanımının kötüye kullanımını engeller.

Çalışanın Intune kullanıcı hesabındaki lisansı da iptal etmek isteyebilirsiniz. Bu durumda lisans boşta kalır ve lisansı yeni bir kullanıcı hesabına atayabilirsiniz.

## Donanımı devre dışı bırakma
Bazı durumlarda, cihazın kendi ömrü sona erer. Böyle durumlarda, tam temizleme işlemiyle [cihazı fabrika ayarlarına sıfırlamak](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) tüm verileri kaldırır ve cihazı Intune’dan kaldırır. Ardından, şirket ilkenize göre donanımı elden çıkarabilirsiniz.

### Ayrıca bkz.
[Tam veya seçmeli temizleme ile verilerinizin korunmasına yardımcı olma](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)


<!--HONumber=May16_HO2-->


