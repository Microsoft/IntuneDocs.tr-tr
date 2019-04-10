---
title: Windows 10 uyumluluk ayarlarına Microsoft Intune - Azure | Microsoft Docs
description: Windows 10, Windows Holographic ve Surface Hub cihazları için Uyumluluk Intune ayarlarken kullanabileceğiniz tüm ayarları bir listesini görürsünüz. En düşük uyumluluğuna denetleyin ve en yüksek işletim sistemi, parola kısıtlamaları ve uzunluğu denetlemek için iş ortağı virüsten koruma (AV) çözümleri, veri depolama ve daha fazlasını şifrelemeyi etkinleştirin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8d956526d483a74ca5929180a48ea2dcd8b3eab7
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423637"
---
# <a name="windows-10-and-later-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Windows 10 ve üzeri ayarları uyumlu veya uyumsuz Intune kullanarak cihazları işaretlemek için

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makale, listeler ve Windows 10 ve üzeri cihazlar ıntune'da yapılandırabileceğiniz farklı uyumluluk ayarları açıklar. Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, bu ayarları kullanın BitLocker gerektir, bir en düşük ve en yüksek işletim sistemi, Windows Defender Gelişmiş tehdit Koruması (ATP) ve daha fazlasını kullanarak bir risk düzeyini ayarlayın.

Bu özellik şu platformlarda geçerlidir:

- Windows 10 ve üzeri
- Windows 10 Holographic for Business
- Surface Hub

Bir Intune Yöneticisi olarak, Kurumsal kaynaklarınızı korumaya yardımcı olmak için bu uyumluluk ayarlarını kullanın. Uyumluluk ilkeleri hakkında daha fazla, hangi bilgi edinmek için bkz [cihaz uyumluluğuyla çalışmaya başlama](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Uyumluluk ilkesi oluşturma](create-compliance-policy.md#create-the-policy). **Platform** olarak **Windows 10 ve üzeri**'ni seçin.

## <a name="device-health"></a>Device health

- **BitLocker gerektir**: Ayarlandığında **gerektiren**, cihaz, sistemin kapalı olduğu veya hazırda bekleme, yetkisiz erişimden sürücüde depolanan verileri koruyabilir. Windows BitLocker Sürücü Şifrelemesi, Windows işletim sistemi birimine depolanan tüm verileri şifreler. BitLocker, Windows işletim sistemini ve kullanıcı verilerini korumaya yardımcı olmak için TPM'yi kullanır. Ayrıca, bir bilgisayar değiştirilmiş değil onaylamak yardımcı olsa bile kaybolur veya çalınırsa, sol katılımsız. Bilgisayarda uyumlu bir TPM varsa, BitLocker verileri koruyan şifreleme anahtarlarını kilitlemek için TPM kullanır. Bunun sonucunda, TPM bilgisayarın durumunu onaylayıncaya kadar anahtarlara erişilemez.

  Ayarlandığında **yapılandırılmadı** (varsayılan), bu ayar, uyumluluk veya uyumsuzluk için değerlendirilmez.

- **Güvenli önyüklemenin cihazda etkinleştirilmesini gerektir**: Ayarlandığında **gerektiren**, sistem güvenilen Fabrika durumuna önyüklenmeye zorlanır. Etkinleştirildiğinde makineyi önyüklemek için kullanılan çekirdek bileşenleri cihazı üreten kuruluş tarafından güvenilen doğru şifreleme imzalarına olması gerekir. UEFI üretici yazılımı, makinenin başlatılmasına izin vermeden önce imzayı doğrular. Herhangi bir dosya, hangi imzalarına keser uyumlu, sistemin önyükleme yapılamıyor.

  Ayarlandığında **yapılandırılmadı** (varsayılan), bu ayar, uyumluluk veya uyumsuzluk için değerlendirilmez.

  > [!NOTE]
  > **Güvenli Önyükleme cihazda etkin olmasını gerektiren** ayarı bazı TPM 1.2 ve 2.0 mobil cihazlarda desteklenir. TPM 2.0 ve sonrasını desteklemeyen cihazlarda ilke durumu Intune'da **Uyumsuz** olarak gösterilir. Desteklenen sürümler hakkında daha fazla bilgi için bkz. [cihaz durumu kanıtlama](https://docs.microsoft.com/windows/security/information-protection/tpm/trusted-platform-module-overview#device-health-attestation).

- **Kod bütünlüğü gerektir**: Kod bütünlüğü bir sürücünün veya sistem dosyasının her belleğe yüklendiğinde bütünlüğünü doğrulayan bir özelliktir. Ayarlandığında **gerektiren**, kod bütünlüğü, imzalanmamış bir sürücü varsa algılar veya sistem dosyasının çekirdeğe yüklenip yüklendiğinden. Ayrıca, bir sistem dosyasının yönetici ayrıcalıklarına sahip bir kullanıcı hesabı tarafından çalıştırmak kötü amaçlı yazılım tarafından değişiklik olup olmadığını algılar.

  Ayarlandığında **yapılandırılmadı** (varsayılan), bu ayar, uyumluluk veya uyumsuzluk için değerlendirilmez.

Daha fazla kaynağı:

- [Sistem durumu kanıtlama CSP'si](https://docs.microsoft.com/windows/client-management/mdm/healthattestation-csp) HAS hizmetinin nasıl çalıştığı hakkında ayrıntılar bulunur.
- [Destek İpucu: Intune uyumluluk ilkenize bir parçası olarak cihaz durumu kanıtlama ayarları kullanma ](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Using-Device-Health-Attestation-Settings-as-Part-of/ba-p/282643)

## <a name="device-properties"></a>Cihaz özellikleri

- **En düşük işletim sistemi sürümü**: Sürümünde izin verilen en düşük girin **major.minor.build.CU numarasını** biçimi. Doğru değeri almak için, komut istemini açın ve `ver` yazın. `ver` komutu, sürümü şu biçimde döndürür:

  `Microsoft Windows [Version 10.0.17134.1]`

  Olduğunda bir cihaza girdiğiniz işletim sistemi sürümünü daha eski bir sürüm varsa, bunu uyumlu değil olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Son kullanıcı, cihazını yükseltmeyi seçebilir. Bunlar yükselttikten sonra kullanıcılar şirket kaynaklarına erişim sağlayabilir.

- **En yüksek işletim sistemi sürümü**: Sürüm, izin verilen en yüksek girin **major.minor.build.revision numarası** biçimi. Doğru değeri almak için, komut istemini açın ve `ver` yazın. `ver` komutu, sürümü şu biçimde döndürür:

  `Microsoft Windows [Version 10.0.17134.1]`

  Bir cihaz girilen belirtilenden sonraki bir işletim sistemi sürümünü kullanarak, kuruluş kaynaklarına erişim engellenir. Son kullanıcı kendi BT yöneticisine başvurması istenir. Cihaz, işletim sistemine izin veren kuralın değiştirilene kadar kuruluş kaynaklarına erişemez.

- **Mobil cihazlar için gereken en düşük işletim sistemi**: En düşük sürümü major.minor.build biçiminde izin girin.

  Bir cihaz, daha önceki bir sürümü olduğunda işletim sistemi sürümü girdiğiniz, bunu uyumlu değil olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Son kullanıcı, cihazını yükseltmeyi seçebilir. Bunlar yükselttikten sonra kullanıcılar şirket kaynaklarına erişim sağlayabilir.

- **Mobil cihazlar için gereken en yüksek işletim sistemi**: Sürümü Major.Minor.Build biçiminde izin verilen üst sınırı girin.

  Bir cihaz girilen belirtilenden sonraki bir işletim sistemi sürümünü kullanarak, kuruluş kaynaklarına erişim engellenir. Son kullanıcı kendi BT yöneticisine başvurması istenir. Cihaz, işletim sistemine izin veren kuralın değiştirilene kadar kuruluş kaynaklarına erişemez.

- **Geçerli işletim sistemi derlemeleri**: Bir aralığın minimum ve maksimum da dahil olmak üzere kabul edilebilir işletim sistemi sürümleri için girin. Kabul edilebilir derleme numaraları için bir virgülle ayrılmış değerler (CSV) dosya listesi **Dışarı Aktarabilirsiniz**.

## <a name="configuration-manager-compliance"></a>Configuration Manager uyumluluk

Windows 10 ve üzeri çalıştıran yalnızca ortak yönetilen cihazlar için geçerlidir. Yalnızca Intune cihazları kullanılabilir değil durumuna döndürün.

- **System Center Configuration Manager cihaz uyumluluğu gerektir**: Seçin **gerektiren** uyumlu olması için System Center Configuration Manager, tüm ayarlarını (yapılandırma öğelerini) zorlamak için. 

  Örneğin, tüm yazılım güncelleştirmelerinin cihazlarda yüklü olmasını gerektirirsiniz. Configuration Manager’da bu gereksinim, “Yüklü” durumundadır. Cihazdaki tüm programları bilinmeyen bir durumda, cihazı Intune'da uyumlu olmadığını.
  
  Zaman **yapılandırılmadı**, Intune değil herhangi bir Configuration Manager uyumluluk ayarlarını denetleyin.

## <a name="system-security"></a>Sistem güvenliği

### <a name="password"></a>istemcisiyle yönetilen bir cihaz için)

- **Mobil cihazların kilidini açmak için parola iste**: **Gerekli** kullanıcıların cihazlarına erişebilmeleri için önce bir parola girin.
- **Basit parolalar**: Kümesine **blok** kullanıcılar gibi basit parolalar oluşturamıyor **1234** veya **1111**. Kullanıcıların **1234** veya **1111** gibi parolalar oluşturmalarına izin vermek için **Yapılandırılmadı** olarak ayarlayın.
- **Parola türü**: Parola yalnızca olması gerekip gerekmediğini seçin **sayısal** karakter veya sayı ve diğer karakterlerin bir karışımı yoksa (**alfasayısal**).

  - **Paroladaki alfasayısal olmayan karakter sayısı**: **Gerekli parola türü** **Alfasayısal** olarak ayarlanırsa bu ayar parolanın içermesi gereken en az karakter kümesi sayısını belirtir. Dört karakter kümesi şunlardır:
    - Küçük harfler
    - Büyük harfler
    - Simgeler
    - Sayılar

    Daha yüksek bir sayı ayarlanırsa kullanıcının daha karmaşık bir parola oluşturması gerekir.

- **Minimum parola uzunluğu**: En düşük rakam veya karakter bulunması gereken sayısını girin.
- **Parola istenmeden önce geçen işlem yapılmayan en fazla dakika**: Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi girin.
- **Parola süresinin sonu (gün)**: Parolanın süresi dolup yeni bir tane oluşturmanız gerekir önce geçen gün sayısını seçin.
- **Yeniden kullanılması önlenecek önceki parola sayısı**: Kullanılamaz önceden kullanılmış parola sayısını girin.
- **Cihaz (Mobil ve Holographic) boşta kalma durumundan çıktığında parola isteme**: Cihaz boşta durumundan çıkarken parola girmesini zorunlu.

### <a name="encryption"></a>Şifreleme

- **Bir cihazdaki veri depolamasının şifrelenmesi**: Seçin **gerektiren** cihazlarınızda veri deposunu şifrelemek için.

  > [!NOTE]
  > **Bir cihazdaki veri depolama şifrelemesi** ayarı cihazdaki genel şifreleme varlığını denetler. Daha güçlü bir şifreleme ayarı için **BitLocker’ı gerektir** ayarını kullanmayı göz önünde bulundurabilirsiniz. Bu ayar, TPM düzeyinde BitLocker durumunu doğrulamak için Windows Cihaz Sistem Durumu Kanıtlama özelliğinden yararlanır.

### <a name="device-security"></a>Cihaz Güvenliği

- **Virüsten koruma**: Ayarlandığında **gerektiren**, kayıtlı virüsten koruma çözümleri kullanarak uyumluluk denetleyebilirsiniz [Windows Güvenlik Merkezi](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/)Symantec ve Windows Defender gibi. **Yapılandırılmadı** olarak bırakıldığında, Intune cihazda herhangi bir AV çözümünün yüklü olup olmadığını denetlemez.
- **Casus yazılımdan koruma**: Ayarlandığında **gerektiren**, kayıtlı bir casus yazılımdan koruma çözümlerini kullanarak uyumluluk denetleyebilirsiniz [Windows Güvenlik Merkezi](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/)Symantec ve Windows Defender gibi. **Yapılandırılmadı** olarak bırakıldığında, Intune cihazda herhangi bir casus yazılımdan koruma çözümünün yüklü olup olmadığını denetlemez.

## <a name="windows-defender-atp"></a>Windows Defender ATP

- **Cihaz veya makine risk puanı altında olmasını gerektir**: Savunması alınan risk değerlendirmesini uyumluluk koşulu olarak tehdit Hizmetleri almak için bu ayarı kullanın. İzin verilen en yüksek tehdit düzeyini seçin:

  - **NET**: Bu seçenek en çok, güvenli, cihazda hiçbir tehdit olmaması gibi. Sahip olan herhangi bir tehdit düzeyi algılanırsa cihaz, uyumsuz olarak değerlendirilir.
  - **Düşük**: Cihaz, yalnızca düşük düzeydeki tehditler varsa uyumlu olarak değerlendirilir. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
  - **Orta**: Cihaz cihazda mevcut tehditler düşük veya Orta düzeydeyse uyumlu olarak değerlendirilir. Yüksek düzeyde tehditler algılanırsa cihaz, uyumlu olmayan olarak belirledi.
  - **Yüksek**: Bu seçenek en az güvenli seçenektir ve tüm tehdit düzeylerine izin verir. Bu çözüm, yalnızca raporlama amacıyla kullanıyorsanız kullanışlı olabilir.
  
  Windows Defender ATP’yi (Gelişmiş Tehdit Koruması) tehdit savunma hizmetiniz olarak ayarlamak için bkz. [Koşullu erişimle Windows Defender ATP’yi etkinleştirme](advanced-threat-protection.md).

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.

## <a name="windows-holographic-for-business"></a>Windows 10 Holographic for Business

Windows Holographic for Business, **Windows 10 ve sonrası** platformları kullanır. Windows Holographic for Business, aşağıdaki ayarı destekler:

- **Sistem Güvenliği** > **Şifreleme** > **Cihazda veri deposu şifrelemesi**.

Microsoft HoloLens’te cihaz şifrelemesini doğrulamak için bkz. [Cihaz şifrelemesini doğrulama](https://docs.microsoft.com/hololens/hololens-encryption#verify-device-encryption).

## <a name="surface-hub"></a>Surface Hub

Surface Hub, **Windows 10 ve sonrası** platformları kullanır. Surface Hub’larda uyumluluk ve koşullu erişim desteklenir. Bu özellikleri Surface hub'larda etkinleştirmek için öneririz [Windows 10 otomatik kaydı etkinleştirme](windows-enroll.md) ıntune'da (Azure Active Directory (Azure AD) gerektirir) ve Surface Hub cihazlarını cihaz gruplarıyla hedefleyebilirsiniz. Surface hub'ların çalışması için Azure AD'ye katılmış uyumluluk ve koşullu erişim için gereklidir.

Rehber için bkz. [Windows cihazları için kaydı ayarlama](windows-enroll.md).

## <a name="next-steps"></a>Sonraki adımlar

- [Uyumsuz cihazlar için Eylemler ekleme](actions-for-noncompliance.md) ve [kapsam etiketleri filtresi ilkeleri kullanan](scope-tags.md).
- [Uyumluluk ilkelerini izleme](compliance-policy-monitor.md).
- Bkz: [Windows 8.1 için Uyumluluk İlkesi ayarları](compliance-policy-create-windows-8-1.md) cihazlar.