---
title: Windows 10 paylaşılan cihaz ayarları-Microsoft Intune-Azure | Microsoft Docs
description: Paylaşılan veya Microsoft Intune birden çok kullanıcı tarafından kullanılan cihazları yapılandırmak için Windows 10 ' u ekleyin ve kullanın. Microsoft Surface dahil olmak üzere tüm ayarların ve cihazlarda ne yaptıkları hakkında bir liste görürsünüz. Konuk hesaplarını denetleme, hesapları yönetme ve etkin olmayan hesapları silme, yerel depolama alanına kaydetmeye izin verme veya bunu engelleme, güç ve uyku seçeneklerini ayarlama, güncelleştirmelerin ne zaman yükleneceğini seçme ve cihaz yapılandırma profilindeki eğitim ortamlarında cihazları kullanma.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/01/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 67393f83ecd76250e01deef3eee20aa1206b3f99
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71730513"
---
# <a name="windows-10-and-later-settings-to-manage-shared-devices-using-intune"></a>Intune kullanarak paylaşılan cihazları yönetmek için Windows 10 ve üzeri ayarları

Microsoft yüzeyi gibi Windows 10 ve üzeri cihazlar birçok kullanıcı tarafından kullanılabilir. Birden çok kullanıcısı olan cihazlara paylaşılan cihaz denir ve mobil cihaz yönetimi (MDM) çözümlerinin bir parçasıdır.

Microsoft Intune kullanarak, son kullanıcılar bu paylaşılan cihazlarda Konuk hesabıyla oturum açabilir. Cihaz kullandıkları için, yalnızca izin verilen özelliklere erişim sağlar. Intune Yöneticisi olarak, erişimi yapılandırır, hesapların ne zaman silinmekte olduğunu, güç yönetimi ayarlarını kontrol edin ve paylaşılan Windows 10 cihazlarınız için daha fazlasını yapın.

Bu makalede, bir Windows 10 (ve üzeri) cihaz yapılandırma profilinde kullandığınız ayarlar listelenir ve açıklanmaktadır. Profil Intune 'da oluşturulduğunda, profilinizi kuruluşunuzdaki cihaz gruplarına dağıtır veya atarsınız. Ayrıca, bu profili karma cihaz türleri ve işletim sistemi sürümleri ile cihaz gruplarına da atayabilirsiniz.

Intune 'da bu özellik hakkında daha fazla bilgi için bkz. [PAYLAŞıLAN bilgisayar veya birden çok Kullanıcı cihazlarındaki erişimi, hesapları ve güç özelliklerini denetleme](shared-user-device-settings.md). Windows CSP hakkında daha fazla bilgi için bkz. [Sharedpc CSP](https://docs.microsoft.com/windows/client-management/mdm/sharedpc-csp).

## <a name="before-your-begin"></a>Başlamadan önce

[Profili oluşturun](shared-user-device-settings.md).

## <a name="shared-multi-user-device-settings"></a>Paylaşılan çok kullanıcılı cihaz ayarları

- **PAYLAŞıLAN bilgisayar modu**: paylaşılan bilgisayar modunu açmak için **Etkinleştir** ' i seçin. Bu modda, tek seferde cihazda yalnızca bir Kullanıcı oturum açar. Birinci Kullanıcı oturumu kapatana kadar başka bir Kullanıcı oturum açamaz. **Yapılandırılmadı** (varsayılan), bu ayarı Intune tarafından yönetilmeyen olarak bırakır ve bir cihazda bu ayarı denetlemek için herhangi bir ilke göndermez.
- **Konuk hesabı**: oturum açma ekranında Konuk seçeneği oluşturmayı seçin. Konuk hesapları için Kullanıcı kimlik bilgileri veya kimlik doğrulaması gerekmez. Bu ayar her kullanıldığında yeni bir yerel hesap oluşturur. Seçenekleriniz şunlardır:
  - **Konuk**: cihazda yerel olarak bir Konuk hesabı oluşturur.
  - **Etki alanı**: Azure ACTIVE DIRECTORY (ad) içinde bir Konuk hesabı oluşturur.
  - **Konuk ve etki alanı**: cihazda yerel olarak bir Konuk hesabı oluşturur ve Azure ACTIVE DIRECTORY (ad).
- **Hesap yönetimi**: konuklar tarafından oluşturulan yerel hesapları ve ad ve Azure AD hesaplarını otomatik olarak silmek için **etkinleştirin** . Kullanıcı cihazda oturumu kapattığında veya sistem bakımı çalıştırıldığında, bu hesaplar silinir. Etkinleştirildiğinde, aşağıdakileri de ayarlayın:
  - **Hesap silme**: hesapların ne zaman silineceğini seçin: **depolama alanı eşiğine**, **depolama alanı eşiğine ve etkin olmayan eşiğe**veya **oturum kapatıldıktan hemen sonra**. Ayrıca şunu girin:
    - **Delete eşiğini Başlat (%)** : disk alanı yüzdesi (0-100) girin. Toplam disk/depolama alanı girdiğiniz değerin altına düştüğünde, önbelleğe alınmış hesaplar silinir. Disk alanı kazanmak için hesapları sürekli olarak siler. En uzun devre dışı olan hesaplar önce silinir.
    - **Silme eşiğini Durdur (%)** : disk alanı yüzdesi (0-100) girin. Toplam disk/depolama alanı girdiğiniz değeri karşılıyorsa, silme işlemini sonlandırır.

  Konuklar tarafından oluşturulan yerel, AD ve Azure AD hesaplarını tutmak için **devre dışı** olarak ayarlayın.

- **Yerel depolama**: kullanıcıların cihazın sabit sürücüsündeki dosyaları kaydetmesini ve görüntülemesini engellemek için **etkin** ' i seçin. Kullanıcıların dosya Gezgini 'ni kullanarak yerel olarak dosya görüp kaydetmesine izin vermek için **devre dışı** ' yı seçin. **Yapılandırılmadı** (varsayılan), bu ayarı Intune tarafından yönetilmeyen olarak bırakır ve bir cihazda bu ayarı denetlemek için herhangi bir ilke göndermez.
- **Güç ilkeleri**: **etkin**olarak ayarlandığında, kullanıcılar hazırda beklemeyi kapatamaz, tüm uyku işlemlerini geçersiz kılamaz (kapağı kapatma gibi) ve güç ayarlarını değiştiremezler. **Devre dışı**olarak ayarlandığında, kullanıcılar cihazı hazırda beklemeye alabilir, cihazı uyku moduna almak için kapağı kapatabilir ve güç ayarlarını değiştirebilir. **Yapılandırılmadı** (varsayılan), bu ayarı Intune tarafından yönetilmeyen olarak bırakır ve bir cihazda bu ayarı denetlemek için herhangi bir ilke göndermez.
- **Uyku zaman aşımı (saniye cinsinden)** : Cihaz uyku moduna geçmeden önce etkin olmayan saniyeler (0-100) sayısını girin. Bir zaman ayarlamazsanız, cihaz 60 dakika sonra uyku moduna geçer.
- **Bilgisayar uyandığında oturum açma**: kullanıcıların cihaz uyku modundan çıktığında bir parolayla oturum açmasını gerektirmek için **etkin** olarak ayarlanır. Kullanıcıların Kullanıcı adı ve parolasını girmesi gerekmiyorsa **devre dışı** öğesini seçin. **Yapılandırılmadı** (varsayılan), bu ayarı Intune tarafından yönetilmeyen olarak bırakır ve bir cihazda bu ayarı denetlemek için herhangi bir ilke göndermez.
- **Bakım başlangıç zamanı (gece yarısından itibaren dakika)** : Windows Update, gibi otomatik bakım görevleri çalıştırıldığında, dakika cinsinden süreyi (0-1440) girin. Varsayılan başlangıç saati gece yarısı veya sıfır (`0`) dakikadır. Başlangıç saatini, gece yarısından dakikalar içinde bir başlangıç saati girerek değiştirin. Örneğin, bakımın 2 ' de başlamasını istiyorsanız `120` girin. Bakımın 8 PM 'de başlamasını istiyorsanız `1200` girin.
- **Eğitim ilkeleri**: okullar için kullanılan ve daha kısıtlayıcı olan cihazlar için önerilen ayarları kullanmak üzere **etkin** ' i seçin. Varsayılan ve önerilen eğitim ilkelerinin kullanılmamış olması için **devre dışı** öğesini seçin. **Yapılandırılmadı** (varsayılan), bu ayarı Intune tarafından yönetilmeyen olarak bırakır ve bir cihazda bu ayarı denetlemek için herhangi bir ilke göndermez.

  Eğitim ilkelerinin ne yaptığı hakkında daha fazla bilgi için bkz. [Eğitim müşterileri Için Windows 10 yapılandırma önerileri](https://docs.microsoft.com/education/windows/configure-windows-for-education).

> [!TIP]
> [Paylaşılan veya Konuk BIR bilgisayar ayarlama](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc) (başka bir Belgeler Web sitesini açar), paylaşılan modda ayarlanulabilecek kavramlar ve grup ilkeleri de dahil olmak üzere bu Windows 10 özelliğindeki harika bir kaynaktır.

## <a name="next-steps"></a>Sonraki adımlar

- [Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).
- Bkz. [Windows holographic for Business](shared-user-device-settings-windows-holographic.md)için ayarlar.
