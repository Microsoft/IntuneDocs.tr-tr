---
title: Windows 10 paylaşılan cihaz ayarları - Microsoft Intune - Azure | Microsoft Docs
description: Ekleyebilir ve Windows 10, paylaşılan veya Microsoft Intune birden çok kullanıcı tarafından kullanılan cihazları yapılandırmak için kullanabilirsiniz. Tüm ayarların bir listesi ve Microsoft Surface dahil olmak üzere, bir cihazda ne yaptıklarını görün. Konuk hesapları denetlemek, hesaplarını yönetme ve etkin olmayan hesaplar silmek, izin verme veya engelleme yerel depoya kaydetme, Ayarla güç ve uyku seçenekleri, ne zaman güncelleştirmeler yüklenir ve cihazları bir cihaz yapılandırma profili eğitim ortamlarında kullanmak seçin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/09/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 31248225205608c6f8809c52b98ed1141395aec1
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57389301"
---
# <a name="windows-10-and-later-settings-to-manage-shared-devices-using-intune"></a>Intune kullanarak paylaşılan cihazları yönetmek üzere Windows 10 ve üzeri ayarları

Windows 10 ve üzeri cihazlar, Microsoft Surface gibi birden çok kullanıcı tarafından kullanılabilir. Birden çok kullanıcıya sahip cihazlar, paylaşılan cihazlar olarak adlandırılır ve bir mobil cihaz Yönetimi (MDM) çözümleri parçasıdır.

Microsoft Intune kullanarak, son kullanıcılar bu paylaşılan cihazlara bir konuk hesabıyla oturum açabilir. Cihaz kullandıkları gibi bunlar yalnızca izin özellikleri erişim elde edin. Intune Yöneticisi olarak erişimi yapılandırma, hesapları ne zaman silineceğini, güç yönetimi ayarlarını denetlemek ve daha fazla bilgi için paylaşılan Windows 10 cihazlarını seçin.

Bu makalede, listeler ve bir Windows 10 (ve üzeri) cihaz yapılandırma profilinde de kullandığınız ayarlar açıklanmaktadır. Intune'da profili oluşturduğunuzda, dağıtmak veya profili, kuruluşunuzdaki cihaz gruplarına atayabilirsiniz. Ayrıca bu profili karma cihaz türleri ve işletim sistemi sürümleri ile cihaz gruplarına atayabilirsiniz.

Intune bu özellik hakkında daha fazla bilgi için bkz. [denetim erişimi, hesapları ve paylaşılan bir bilgisayar veya birden çok kullanıcı cihazlarda güç özellikleri](shared-user-device-settings.md). Windows CSP hakkında daha fazla bilgi için bkz. [SharedPC CSP](https://docs.microsoft.com/windows/client-management/mdm/sharedpc-csp).

## <a name="before-your-begin"></a>Önce başlangıç

[Profil oluşturma](shared-user-device-settings.md).

## <a name="shared-multi-user-device-settings"></a>Paylaşılan birden çok kullanıcı cihaz ayarları

- **Paylaşılan bilgisayar modu**: Seçin **etkinleştirme** paylaşılan bilgisayar modunu açmak için. Bu modda, yalnızca bir cihaza aynı anda oturum açtığında. Başka bir kullanıcı ilk kullanıcı oturumu kadar oturum açamazsınız. **Yapılandırılmamış** (varsayılan), bu Intune tarafından yönetilmeyen ayarı bırakır ve bu ayar bir cihazda denetlemek için herhangi bir ilke anında iletme değil.
- **Konuk hesabı**: Oturum açma ekranında bir konuk seçeneği oluşturmak bu seçeneği seçin. Konuk hesapları, kullanıcı kimlik bilgileri veya kimlik doğrulaması gerekli değildir. Bu ayar, kullanıldığı her zaman yeni bir yerel hesabı oluşturur. Seçenekleriniz şunlardır:
  - **Konuk**: Bir Konuk hesabı, cihazda yerel olarak oluşturur.
  - **Etki alanı**: Bir Konuk hesabı Azure Active Directory (AD) oluşturur.
  - **Konuk ve etki alanı**: Bir Konuk hesabı yerel olarak cihazda ve Azure Active Directory (AD) oluşturur.
- **Hesap Yönetimi**: Kümesine **etkinleştirme** AD ve Azure AD yerel hesaplar konuklar tarafından oluşturulan ve hesapları otomatik olarak silmek için. Bu hesaplar, kullanıcı cihazı kapatıp açtığında veya Sistem Bakımı çalıştığında silinir. Etkin olduğunda, ayrıca ayarlayın:
  - **Hesap silme**: Hesapları ne zaman silineceğini seçin: **Depolama alanı eşik adresindeki**, **depolama alanı eşiği ve etkin olmayan eşik**, veya **hemen sonra oturumu kapatın**. Şunları da girin:
    - **Başlangıç Sil threshold(%)**: Disk alanının yüzdesi (0-100) girin. Toplam disk depolama alanı girdiğiniz değerin altına düştüğünde, önbelleğe alınan hesapları da silinir. Sürekli olarak disk alanını boşaltmak için hesapları da silinir. Tanımladığımız etkin olmayan hesaplar önce silinir.
    - **Delete threshold(%) Durdur**: Disk alanının yüzdesi (0-100) girin. Toplam disk depolama alanı girdiğiniz değer karşıladığında silme durdurur.

  Kümesine **devre dışı** yerel AD, tutmak ve konuklar tarafından oluşturulan Azure AD hesapları.

- **Yerel depolama**: Seçin **etkin** kaydetme ve cihazın bir sabit sürücü dosyalarını görüntüleme kullanıcıların önlemek için. Seçin **devre dışı bırakılmış** kullanıcıların yerel olarak dosya Gezgini'ni kullanarak dosyaları kaydetmek. **Yapılandırılmamış** (varsayılan), bu Intune tarafından yönetilmeyen ayarı bırakır ve bu ayar bir cihazda denetlemek için herhangi bir ilke anında iletme değil.
- **Güç ilkeleri**: Ayarlandığında **etkin**, kullanıcıları olamaz açın hazırda bekletme kapalı (kapağı kapatma gibi) tüm uyku eylemlerini geçersiz kılınamaz ve güç ayarlarını değiştiremezsiniz. Ayarlandığında **devre dışı bırakılmış**, Kullanıcılar Cihaz hazırda bekleme, cihazın uyku moduna kapağını ve güç ayarlarını değiştirmek. **Yapılandırılmamış** (varsayılan), bu Intune tarafından yönetilmeyen ayarı bırakır ve bu ayar bir cihazda denetlemek için herhangi bir ilke anında iletme değil.
- **Zaman aşımı (saniye cinsinden) uyku**: Cihazın uyku moduna geçmeden önce etkin olmayan saniye (0-100) sayısını girin. Bir zaman ayarlamazsanız, cihaz, 60 dakika uyku moduna.
- **PC çıkarılırken oturum**: Kümesine **etkin** kullanıcıların, cihazın uyku modundan söz konusu olduğunda bir parolayla oturum açmasını istemek için. Seçin **devre dışı bırakılmış** kullanıcıların kullanıcı adı ve parola girmeniz gerekmez. **Yapılandırılmamış** (varsayılan), bu Intune tarafından yönetilmeyen ayarı bırakır ve bu ayar bir cihazda denetlemek için herhangi bir ilke anında iletme değil.
- **Bakım başlangıç zamanı (dakika cinsinden gece yarısı)**: Windows Update gibi otomatik bakım görevleri çalıştırdığınızda saat (0-1440) dakika cinsinden girin. Varsayılan başlangıç saati gece yarısından veya sıfır olan (`0`) dakika. Başlangıç saati gece yarısı dakikalar içinde bir başlangıç saati girerek değiştirin. Örneğin, bakım 02: 00 başlamak istiyorsanız, girin `120`. Bakım 8 saat başlamak istiyorsanız girin `1200`.
- **Eğitim ilkeleri**: Seçin **etkin** daha kısıtlayıcı OKULLARDAKİ kullanılan cihazlar için önerilen ayarları kullanmak için. Seçin **devre dışı bırakılmış** için varsayılan ve önerilen eğitim ilkeleri kullanılmaz. **Yapılandırılmamış** (varsayılan), bu Intune tarafından yönetilmeyen ayarı bırakır ve bu ayar bir cihazda denetlemek için herhangi bir ilke anında iletme değil.

  Eğitim ilkeleri neler daha fazla bilgi için bkz: [için eğitim müşterileri Windows 10 yapılandırma önerileri](https://docs.microsoft.com/education/windows/configure-windows-for-education).

## <a name="next-steps"></a>Sonraki adımlar

- [Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).
- Ayarlarını görmek [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md).
