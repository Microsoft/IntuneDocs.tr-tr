---
title: Cihazları devre dışı bırakma
description: Intune, ilkesini ve şirket portalını kaldırarak cihazı Intune yönetiminden kaldırmak için hem seçmeli silmeyi, hem tam silmeyi destekler.
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/13/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d9dc8fdd7437c9de49df9ea9a4c9641ac9d590de
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="retire-devices-from-intune-management"></a>Cihazları Intune yönetiminde devre dışı bırakma

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Cihazlar ister şirkete ait ister kişisel olsun, yönetilen bir cihazın er ya da geç Intune yönetiminden kaldırılması gerekir.

Cihazlar bir süre Intune hizmetine bağlanmasa bile, müdahale etmediğiniz takdirde Intune’dan hiçbir zaman kaldırılmazlar.

Bir cihazı çeşitli nedenlerle kullanımdan kaldırmanız gerekebilir:

-   Kullanıcının şirketten planlı bir şekilde ("yönetilen" ayrılma) ayrılması
-   Kullanıcı aniden ayrılması (işten çıkartılırsa, istifa ederse, vb.).
-   Cihazın kaybolması
-   Bir cihazın kullanım amacının değiştirilmesi (başka bir kullanıcıya verilmesi, farklı bir amaç için yeniden kullanılması vb.)

Mobil cihaz olarak yönetilen cihazlarda seçmeli silme veya tam silme gerçekleştirebilir veya cihazı kilitleyip parolasını sıfırlayabilirsiniz. Cihazı temizleyerek kullanıcının aboneliğini başka bir cihaz eklemek üzere serbest bırakmış olursunuz. Intune istemci yazılımıyla yönetilen bilgisayarları da devre dışı bırakabilirsiniz.

## <a name="wipe-data-and-apps-from-devices"></a>Cihazdan verileri ve uygulamaları temizleme
Hem seçmeli silme hem de tam silme işlemi, ilkesini ve şirket portalını kaldırarak cihazı Intune yönetiminden kaldırır. Sonuç olarak, cihaz artık Microsoft SharePoint, e-posta veya Office 365 gibi şirket kaynaklarında oturum açmak için gerekli kimlik bilgilerine sahip olmaz.

[Seçmeli temizleme](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) cihazdaki kişisel bilgileri etkilemediğinden, Intune’a kendi cihazını kaydetmiş olan çalışanlar için tercih edilen işlemdir. Yalnızca şirket verileri kaldırılır.

Kullanım amacı değiştirilmesi gereken cihazlarda, cihazı fabrika ayarlarına döndüren [tam temizleme](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe) işlevini de kullanabilirsiniz.

### <a name="removing-user-licenses-and-managed-devices"></a>Kullanıcı lisanslarını ve yönetilen cihazları kaldırma
Kullanıcı lisansını kaldırdığınızda o kullanıcının kayıtlı cihazlarının kaydı silinir. En iyi uygulama olarak, bir kullanıcının Intune lisansını kaldırmadan önce yönetilen cihazlardan şirket verilerini kaldırmak için seçmeli temizleme yöntemini kullanmalısınız. Kullanıcı lisansını kaldırdığınızda cihaz uzaktan eylemler için hedeflenemez.

## <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>Azure Active Directory portalında cihazları silmek için

1.  Kuruluş kimlik bilgilerinizle [http://aka.ms/accessaad](http://aka.ms/accessaad) veya [https://portal.office.com](https://portal.office.com) adresinde oturum açın ve **Yönetim merkezleri** &gt; **Azure AD**’yi seçin.

2.  Azure aboneliğiniz yoksa, bir abonelik oluşturun. Ücretli bir hesabınız varsa, bu işlem kredi kartı veya ödeme gerektirmez. **Ücretsiz Azure Active Directory aboneliğinizi kaydedin** bağlantısını seçin.

4.  **Active Directory**’yi ve ardından kuruluşunuzu seçin.

5.  **Kullanıcılar** sekmesini seçin.

6.  Cihazlarını silmek istediğiniz kullanıcıyı seçin.

7.  **Cihazlar**’ı seçin.

8.  Cihazları uygun bir şekilde seçip **Cihazı sil**’i belirleyin. Cihaz bir sonraki Active Directory eşitlemesinde silinir. Bu genellikle dört saat içinde gerçekleşir. Eşitlemeden sonra cihaz yönetimden kaldırılır. Bu durumda kullanıcının cihaz sınırından bir cihaz eksilir.

## <a name="retire-managed-computers"></a>Yönetilen bilgisayarları devre dışı bırakma
Intune istemci yazılımıyla yönetilen bilgisayarlar, Intune yönetim konsolu aracılığıyla yönetimden kaldırılabilir. Bu durumda istemci yazılımı da kaldırılır ve Intune ilkesi bilgisayardan silinir. [Intune istemci yazılımıyla yönetilen bilgisayarları devre dışı bırakma](retire-a-windows-pc-with-microsoft-intune.md) hakkında bilgi edinin.

## <a name="block-access-a-device"></a>Bir cihaza erişimi engelleme
Bir cihaz kaybolursa ya da bir çalışan, şirkete ait donanımı iade etmeden şirketi terk ederse, [geçiş kodunu sıfırlama ve cihazı uzaktan kilitleme](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) de gerçekleştirebilirsiniz. Bu seçenek, cihazı gözden çıkarmanıza yol açabilecek olsa da şirket bilgilerinin kötüye kullanımını engeller.

Çalışanın Intune kullanıcı hesabındaki lisansı da iptal etmek isteyebilirsiniz. Bu durumda lisans boşta kalır ve lisansı yeni bir kullanıcı hesabına atayabilirsiniz.

## <a name="retire-hardware"></a>Donanımı devre dışı bırakma
Bazı durumlarda, cihazın kendi ömrü sona erer. Böyle durumlarda, tam temizleme işlemiyle [cihazı fabrika ayarlarına sıfırlamak](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) tüm verileri kaldırır ve cihazı Intune’dan kaldırır. Ardından, şirket ilkenize göre donanımı elden çıkarabilirsiniz.

### <a name="see-also"></a>Ayrıca bkz:
[Tam veya seçmeli silme ile verilerinizin korunmasına yardımcı olma](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)
