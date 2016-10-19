---
title: "Cihazları devre dışı bırakma | Microsoft Intune"
description: "Intune, ilkesini ve şirket portalını kaldırarak cihazı Intune yönetiminden kaldırmak için hem seçmeli silmeyi, hem tam silmeyi destekler."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: cf471320f122eea7804ff6cd6cad208f8cd5a692
ms.openlocfilehash: 29d13dcbc367c18d64f9522fa9a3b962226feebb


---

# Cihazları Intune yönetiminde devre dışı bırakma

Cihazlar ister şirkete ait ister kişisel olsun, belirli bir zaman geldiğinde yönetilen bir cihazın Intune yönetiminden kaldırılması gerekir. Bir cihazın çeşitli nedenlerle kullanımdan kaldırılması gerekebilir:

-   Kullanıcının şirketten planlı bir şekilde ("yönetilen" ayrılma) ayrılması
-   Kullanıcı aniden ayrılması (işten çıkartılırsa, istifa ederse, vb.).
-   Cihazın kaybolması
-   Bir cihazın kullanım amacının değiştirilmesi (başka bir kullanıcıya verilmesi, farklı bir amaç için yeniden kullanılması, vb.)

Mobil cihaz olarak yönetilen cihazlarda seçmeli temizleme veya tam temizleme gerçekleştirebilir veya cihazı kilitleyip parolasını sıfırlayabilirsiniz. Cihazı temizleyerek kullanıcının aboneliğini başka bir cihaz eklemek üzere serbest bırakmış olursunuz. Intune istemci yazılımıyla yönetilen bilgisayarları da devre dışı bırakabilirsiniz.

## Cihazdan verileri ve uygulamaları temizleme
Hem seçmeli temizleme hem de tam temizleme, ilkesini ve şirket portalını kaldırarak cihazı Intune yönetiminden kaldırır. Bu da, artık cihazın Microsoft SharePoint, e-posta veya Office 365 gibi şirket kaynaklarında oturum açmak için gereken kimlik bilgilerine sahip olmadığı anlamına gelir.

[Seçmeli temizleme](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) cihazdaki kişisel bilgileri etkilemediğinden, Intune’a kendi cihazını kaydetmiş olan çalışanlar için tercih edilen işlemdir. Yalnızca şirket verileri kaldırılır.

Kullanım amacı değiştirilmesi gereken cihazlarda, cihazı fabrika ayarlarına döndüren [tam temizleme](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe) işlevini de kullanabilirsiniz.

## Azure Active Directory portalında cihazları silmek için

1.  Kuruluş kimlik bilgilerinizle [http://aka.ms/accessaad](http://aka.ms/accessaad) veya [https://portal.office.com](https://portal.office.com) adresinde oturum açın ve **Yönetim merkezleri** &gt; **Azure AD**’yi seçin.

2.  Azure Aboneliğiniz yoksa, bir abonelik oluşturun. Ücretli bir hesabınız varsa, bu işlem için kredi kartı veya ödeme gerekmez (**Ücretsiz Azure Active Directory kaydınız** abonelik bağlantısını seçin).

4.   **Active Directory** ’yi ve sonra da kuruluşunuzu seçin.

5.   **Kullanıcılar** sekmesini seçin.

6.  Cihazlarını silmek istediğiniz kullanıcıyı seçin.

7.  **Cihazlar**’ı seçin.

8.  Cihazları uygun bir şekilde seçip **Cihazı sil**’i seçin. Cihaz bir sonraki Active Directory eşitlemesinde silinir. Bu da genellikle 4 saat içinde gerçekleşir. Eşitlemeden sonra cihaz yönetimden kaldırılır. Bu durumda kullanıcının cihaz sınırından bir cihaz eksilir.

## Yönetilen bilgisayarları devre dışı bırakma
Intune istemci yazılımıyla yönetilen bilgisayarlar Intune yönetim konsolu aracılığıyla yönetimden kaldırılabilir. Bu durumda istemci yazılımı da kaldırılır ve Intune ilkesi bilgisayardan silinir. [Intune istemci yazılımıyla yönetilen bilgisayarları devre dışı bırakma](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#retire-a-computer.md) hakkında bilgi edinin.

## Bir cihaza erişimi engelleme
Bir cihaz kaybolduğunda ya da bir çalışan şirkete ait donanımı iade etmeden şirketi terk ettiğinde [geçiş kodunu sıfırlama ve cihazı uzaktan kilitleme](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) olanaklarına da sahip olursunuz. Bu seçenek, cihazı gözden çıkarmanıza yol açabilecek olsa da şirket bilgilerinin kötüye kullanımını engeller.

Çalışanın Intune kullanıcı hesabındaki lisansı da iptal etmek isteyebilirsiniz. Bu durumda lisans boşta kalır ve lisansı yeni bir kullanıcı hesabına atayabilirsiniz.

## Donanımı devre dışı bırakma
Bazı durumlarda, cihazın kendi ömrü sona erer. Böyle durumlarda, tam temizleme işlemiyle [cihazı fabrika ayarlarına sıfırlamak](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) tüm verileri kaldırır ve cihazı Intune’dan kaldırır. Ardından, şirket ilkenize göre donanımı elden çıkarabilirsiniz.

### Ayrıca bkz.
[Tam veya seçmeli temizleme ile verilerinizin korunmasına yardımcı olma](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)



<!--HONumber=Aug16_HO4-->


