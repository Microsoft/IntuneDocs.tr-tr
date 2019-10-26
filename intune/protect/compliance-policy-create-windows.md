---
title: Microsoft Intune-Azure 'da Windows 10 uyumluluk ayarları | Microsoft Docs
description: Microsoft Intune içindeki Windows 10, Windows holographic ve Surface Hub cihazlarınız için uyumluluk ayarlarken kullanabileceğiniz tüm ayarların listesini görüntüleyin. En düşük ve en yüksek işletim sistemlerinde uyumluluğu denetleyin, parola kısıtlamalarını ve uzunluğu ayarlayın, iş ortağı Anti-Virus (AV) çözümlerini denetleyin, veri depolamada şifrelemeyi etkinleştirin ve daha fazlasını yapın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f3c6c029a5c5864eda46a68832b2f9f655553846
ms.sourcegitcommit: 0d6f323152ec62f7d383891cce12ea0a4289cd8f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2019
ms.locfileid: "72889532"
---
# <a name="windows-10-and-later-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Cihazları Intune ile uyumlu veya uyumsuz olarak işaretlemek için Windows 10 ve üzeri ayarları

Bu makalede, Intune 'da Windows 10 ve üzeri cihazlarda yapılandırabileceğiniz farklı uyumluluk ayarları listelenir ve açıklanmaktadır. Mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak BitLocker 'ı gerektirmek, en düşük ve en yüksek işletim sistemi ayarlamak, Microsoft Defender Gelişmiş tehdit koruması (ATP) kullanarak bir risk düzeyi ayarlamak ve daha fazlasını yapmak için bu ayarları kullanın.

Bu özellik şu platformlarda geçerlidir:

- Windows 10 ve üzeri
- Windows 10 Holographic for Business
- Surface Hub

Intune yöneticisi olarak bu uyumluluk ayarlarını kullanarak kuruluşunuzun kaynaklarının korunmasına yardımcı olabilirsiniz. Uyumluluk ilkeleri ve işlevleri hakkında daha fazla bilgi için bkz. [Cihaz uyumluluğunu kullanmaya başlama](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Uyumluluk ilkesi oluşturma](create-compliance-policy.md#create-the-policy). **Platform** olarak **Windows 10 ve üzeri**'ni seçin.

## <a name="device-health"></a>Cihaz Sistem Durumu

### <a name="windows-health-attestation-service-evaluation-rules"></a>Windows sistem durumu kanıtlama hizmeti değerlendirme kuralları

- **BitLocker gerektir**:  
   Windows BitLocker Sürücü Şifrelemesi, Windows işletim sistemi birimine depolanan tüm verileri şifreler. BitLocker, Windows işletim sistemini ve Kullanıcı verilerini korumaya yardımcı olmak için Güvenilir Platform Modülü (TPM) kullanır. Ayrıca, sol tarafta bırakılmış, kayıp veya çalınmış olsa bile bir bilgisayarın üzerinde oynanmadığını doğrulamanıza yardımcı olur. Bilgisayarda uyumlu bir TPM varsa, BitLocker verileri koruyan şifreleme anahtarlarını kilitlemek için TPM kullanır. Sonuç olarak, TPM bilgisayarın durumunu doğrulana kadar anahtarlara erişilemez.  

   - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.
   - **Gerektir** -cihaz, sistem kapalı veya hazırda bekleme durumunda sürücüde depolanan verileri yetkisiz erişimden koruyabilir.  


- **Cihazda güvenli önyüklemenin etkinleştirilmesini gerektir**:  
    - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.
    - **Gerektir** -sistem, fabrikada güvenilen bir duruma önyükleme yapılmasını zorlanmıştır. Makineyi önyüklemek için kullanılan çekirdek bileşenleri, cihazı üreten kuruluşun güvendiği doğru şifreleme imzalarına sahip olmalıdır. UEFI üretici yazılımı, makinenin başlatılmasına izin vermeden önce imzayı doğrular. Herhangi bir dosya üzerinde değişiklik yapılmışsa ve imzasını kesen sistem önyükleme yapmaz.

  > [!NOTE]
  > **Cihazda güvenli önyüklemenin etkinleştirilmesini gerektir** AYARı bazı TPM 1,2 ve 2,0 cihazlarda desteklenir. TPM 2.0 ve sonrasını desteklemeyen cihazlarda ilke durumu Intune'da **Uyumsuz** olarak gösterilir. Desteklenen sürümler hakkında daha fazla bilgi için bkz. [cihaz sistem durumu kanıtlama](https://docs.microsoft.com/windows/security/information-protection/tpm/trusted-platform-module-overview#device-health-attestation).

- **Kod bütünlüğü gerektir**:  
  Kod bütünlüğü, bir sürücünün veya sistem dosyasının belleğe her yüklendiğinde bütünlüğünü doğrulayan bir özelliktir.
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.
  -  **Gerektir** -bir imzalanmamış sürücü veya sistem dosyasının çekirdeğe yüklenip yüklenmediğini algılayan kod bütünlüğü gerektir. Ayrıca, bir sistem dosyasının kötü amaçlı yazılım tarafından değiştirilip değiştirilmediğini algılar veya yönetici ayrıcalıklarına sahip bir kullanıcı hesabı tarafından çalıştırılabilir.

Daha fazla kaynak:

- Sistem durumu kanıtlama hizmeti 'nin nasıl çalıştığı hakkında ayrıntılı bilgi için bkz. [durum KANıTLAMA CSP](https://docs.microsoft.com/windows/client-management/mdm/healthattestation-csp)'si.
- [Destek İpucu: Intune uyumluluk Ilkenizin kapsamında cihaz sistem durumu kanıtlama ayarlarını kullanma](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Using-Device-Health-Attestation-Settings-as-Part-of/ba-p/282643).

## <a name="device-properties"></a>Cihaz Özellikleri

### <a name="operating-system-version"></a>İşletim Sistemi Sürümü

- **En düşük işletim sistemi sürümü**:  
  **Major.Minor.Build.cu sayı** biçiminde izin verilen en düşük sürümü girin. Doğru değeri almak için, komut istemini açın ve `ver` yazın. `ver` komutu, sürümü şu biçimde döndürür:

  `Microsoft Windows [Version 10.0.17134.1]`

  Bir cihazın girdiğiniz işletim sistemi sürümünden önceki bir sürümü varsa, uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Son kullanıcı cihazını yükseltmeyi seçebilir. Yükseltildikten sonra şirket kaynaklarına erişebilirler.

- **En yüksek işletim sistemi sürümü**:  
  İzin verilen en fazla sürümü, **ana. Minor. Build. Revision sayı** biçiminde girin. Doğru değeri almak için, komut istemini açın ve `ver` yazın. `ver` komutu, sürümü şu biçimde döndürür:

  `Microsoft Windows [Version 10.0.17134.1]`

  Bir cihaz, girilen sürümden daha sonraki bir işletim sistemi sürümünü kullanırken, kuruluş kaynaklarına erişim engellenir. Son kullanıcıdan BT yöneticisine başvurması istenir. Cihaz, işletim sistemi sürümüne izin verecek şekilde değiştirilene kadar kuruluş kaynaklarına erişemez.

- **Mobil cihazlar için gereken en düşük işletim sistemi**:  
  İzin verilen en düşük sürümü, ana. Minor. Build sayı biçiminde girin.

  Bir cihaz, girdiğiniz işletim sistemi sürümünün önceki bir sürümüne sahip olduğunda, uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Son kullanıcı cihazını yükseltmeyi seçebilir. Yükseltildikten sonra şirket kaynaklarına erişebilirler.

- **Mobil cihazlar için gereken en yüksek işletim sistemi**:  
  İzin verilen en fazla sürümü, ana. ikincil. derleme numarasında girin.

  Bir cihaz, girilen sürümden daha sonraki bir işletim sistemi sürümünü kullanırken, kuruluş kaynaklarına erişim engellenir. Son kullanıcıdan BT yöneticisine başvurması istenir. Cihaz, işletim sistemi sürümüne izin verecek şekilde değiştirilene kadar kuruluş kaynaklarına erişemez.

- **Geçerli işletim sistemi derlemeleri**:  
  En düşük ve en yüksek dahil olmak üzere, kabul edilebilir işletim sistemi sürümleri için bir Aralık girin. Kabul edilebilir derleme numaraları için bir virgülle ayrılmış değerler (CSV) dosya listesi **Dışarı Aktarabilirsiniz**.

## <a name="configuration-manager-compliance"></a>Configuration Manager uyumluluğu

Yalnızca Windows 10 ve üzeri çalıştıran ortak yönetilen cihazlar için geçerlidir. Yalnızca Intune cihazları kullanılabilir olmayan bir durum döndürüyor.

- **System Center Configuration Manager cihaz uyumluluğunu gerektir**:  
  - **Yapılandırılmadı** (*varsayılan*)-ıntune, uyumluluk için Configuration Manager ayarlarından herhangi birini denetlemez.
  - **Gerektir** -System Center Configuration Manager için tüm ayarların (yapılandırma öğeleri) uyumlu olmasını gerektir.  

    Örneğin, tüm yazılım güncelleştirmelerinin cihazlarda yüklü olmasını gerektirirsiniz. Configuration Manager’da bu gereksinim, “Yüklü” durumundadır. Cihazdaki herhangi bir program bilinmeyen bir durumdaysa, cihaz Intune 'da uyumlu değildir.

## <a name="system-security"></a>Sistem Güvenliği

### <a name="password"></a>Parola

- **Mobil cihazların kilidini açmak için bir parola iste**:  
  - **Yapılandırılmadı** (*varsayılan*)-Bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.
  - **Gerektir** -kullanıcıların cihazına erişebilmeleri için önce bir parola girmesi gerekir. 

- **Basit parolalar**:  
  - **Yapılandırılmadı** (*varsayılan*)-kullanıcılar, **1234** veya **1111**gibi basit parolalar oluşturabilir.
  - **Engelle** -kullanıcılar, **1234** veya **1111**gibi basit parolalar oluşturamaz.

- **Parola türü**:  
  Gerekli parola veya PIN türünü seçin. Seçenekleriniz şunlardır:
  - **Cihaz varsayılanı** (*varsayılan*)-parola, sayısal PIN veya alfasayısal PIN gerektir
  - **Sayısal** -parola veya sayısal PIN gerektir
  - **Alfasayısal** -parola veya alfasayısal PIN gerektirir.  
  
  *Alfasayısal*olarak ayarlandığında aşağıdaki ayarlar kullanılabilir:  
  - **Parola karmaşıklığı**:  
    Seçenekleriniz şunlardır: 
    - **Rakamlar ve küçük harfler gerektir** (*varsayılan*)
    - **Rakamlar, küçük harfler ve büyük harfler iste**
    - **Rakamlar, küçük harfler, büyük harfler ve özel karakterler iste**

    > [!TIP]
    > Alfasayısal parola ilkeleri karmaşık olabilir. Daha fazla bilgi için yöneticilerin CSP 'Leri okumasını öneririz:
    >
    > - [DeviceLock/alfanümerik ıdevicepasswordrequired CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-alphanumericdevicepasswordrequired)
    > - [DeviceLock/MinDevicePasswordComplexCharacters CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-mindevicepasswordcomplexcharacters)

- **Minimum parola uzunluğu**:  
  Parolanın sahip olması gereken minimum rakam veya karakter sayısını girin.

- **Parola istenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı**:  
  Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi girin.

- **Parola kullanım süresi (gün olarak)** :  
  Parolanın süresi dolmadan önce geçecek gün sayısını girin ve 1-730 adresinden yeni bir tane oluşturmanız gerekir.

- **Yeniden kullanılması önlenecek önceki parola sayısı**:  
  Daha önce kullanılan kaç parolanın kullanılamayacağını belirtir.

- **Cihaz boşta durumundan çıktığında parola iste (Mobile ve holographic)** :  
  - **Yapılandırılmadı** (*varsayılan*)
  - **Gerektir** -cihaz boşta durumundan çıkarken cihaz kullanıcılarının parolayı girmesini gerektir.

  > [!IMPORTANT]
  > Parola gereksinimi bir Windows masaüstünde değiştirildiğinde, bu cihaz boşta durumundan etkin 'e geçtiğinde, kullanıcılar bir sonraki oturum açışlarında etkilenir. Gereksinimi karşılayan parolalara sahip olan kullanıcılar parolalarını değiştirmelerini de istenir.

### <a name="encryption"></a>Şifreleme

- **Cihazda veri deposunun şifrelenmesi**:  
  - **Yapılandırılmadı** (*varsayılan*)
  - **Gerektir** -kullanım, cihazlarınızda veri depolamayı şifrelemek için *gerektir* .

  > [!NOTE]
  > **Bir cihazdaki veri depolama şifrelemesi** ayarı cihazdaki genel şifreleme varlığını denetler. Daha güçlü bir şifreleme ayarı için **BitLocker’ı gerektir** ayarını kullanmayı göz önünde bulundurabilirsiniz. Bu ayar, TPM düzeyinde BitLocker durumunu doğrulamak için Windows Cihaz Sistem Durumu Kanıtlama özelliğinden yararlanır.

### <a name="device-security"></a>Cihaz Güvenliği  

- **Güvenlik Duvarı**:  
  - **Yapılandırılmadı** (*varsayılan*)-Intune, Microsoft Defender güvenlik duvarını denetlemez ve var olan ayarları değiştirmez.
  - **Gerektir** -Microsoft Defender güvenlik duvarını açın ve kullanıcıların bunu kapatmasını engelleyin.  

  [Güvenlik Duvarı CSP 'si](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp)

  > [!NOTE]
  > Yeniden başlatmanın ardından cihaz hemen eşitleniyorsa veya uykudan uyandırmaya hemen eşitlendikten sonra, bu ayar bir **hata**olarak rapor verebilir. Bu senaryo genel cihaz uyumluluk durumunu etkilemeyebilir. Uyumluluk durumunu yeniden değerlendirmek için cihazı el ile [eşitleyin](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows).

- **Güvenilir Platform Modülü (TPM)** :  
  - **Yapılandırılmadı** (*varsayılan*)-ıNTUNE, cihazı bir TPM yonga sürümü için denetlemez.
  - **Gerektir** -Intune, uyumluluk için TPM yonga sürümünü denetler. TPM yonga sürümü **0** ' dan büyükse cihaz uyumludur (sıfır). Cihazda TPM sürümü yoksa cihaz uyumlu değildir.  

  [DeviceStatus CSP-DeviceStatus/TPM/SpecificationVersion düğümü](https://docs.microsoft.com/windows/client-management/mdm/devicestatus-csp)
  
- **Virüsten koruma**:  
  - **Yapılandırılmadı** (*varsayılan*)-Intune, cihazda yüklü olan herhangi bir virüsten koruma çözümünü denetlemez. 
  - Symantec ve Microsoft Defender gibi [Windows Güvenlik Merkezi](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/)'ne kayıtlı virüsten koruma çözümlerini kullanarak uyumluluğu kontrol edin.

- **Casus yazılımdan koruma**:  
  - **Yapılandırılmadı** (*varsayılan*)-Intune, cihazda yüklü olan herhangi bir casus yazılımdan koruma çözümünü denetlemez.
  - Symantec ve Microsoft Defender gibi [Windows Güvenlik Merkezi](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/)'ne kayıtlı casus yazılımdan koruma çözümlerini kullanarak uyumluluğu kontrol edin.  

### <a name="defender"></a>Defender

*Aşağıdaki uyumluluk ayarları Windows 10 Masaüstü ile desteklenir.*

- **Microsoft Defender kötü amaçlı yazılımdan koruma**:  
  - **Yapılandırılmadı** (*varsayılan*)-Intune hizmeti denetlemez ve var olan ayarları değiştirmez.
  - **Gerektir** -Microsoft Defender kötü amaçlı yazılımdan koruma hizmetini etkinleştirin ve kullanıcıların bunu kapatmasını engelleyin. 

- **Microsoft Defender kötü amaçlı yazılımdan koruma en düşük sürümü**:  
  Microsoft Defender kötü amaçlı yazılımdan koruma hizmeti 'nin izin verilen en düşük sürümünü girin. Örneğin, şunu girin: `4.11.0.0`. Boş bırakılırsa, Microsoft Defender kötü amaçlı yazılımdan koruma hizmeti 'nin herhangi bir sürümü kullanılabilir.  

  *Varsayılan olarak, sürüm yapılandırılmaz*.

- **Microsoft Defender kötü amaçlı yazılımdan koruma güvenlik zekası güncel**:  
  Cihazlarda Windows Güvenlik virüsü ve tehdit koruması güncelleştirmelerini denetler.  
  - **Yapılandırılmadı** (*varsayılan*)-Intune hiçbir gereksinimi zorlamaz.
  - **Gerektir** -Microsoft Defender Güvenlik Intelligence 'ın güncel olmasını zorunlu kılın. 

  Daha fazla bilgi için bkz. [Microsoft Defender virüsten koruma ve diğer Microsoft Antimalware Için güvenlik zekası güncelleştirmeleri](https://www.microsoft.com/en-us/wdsi/defenderupdates).

- **Gerçek zamanlı koruma**:  
  - **Yapılandırılmadı** (*varsayılan*)-Intune bu özelliği denetlemez ve var olan ayarları değiştirmez.
  - **Gerekli** -kötü amaçlı yazılım, casus yazılım ve diğer istenmeyen yazılımları tarayan gerçek zamanlı korumayı etkinleştirin.  

  [Defender/AllowRealtimeMonitoring CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowrealtimemonitoring)

## <a name="microsoft-defender-atp"></a>Microsoft Defender ATP

### <a name="microsoft-defender-advanced-threat-protection-rules"></a>Microsoft Defender Gelişmiş tehdit koruması kuralları

- **Cihazın makine risk puanı üzerinde veya altında olmasını gerektir**:  
  Bu ayarı, savunma tehdidi hizmetinizdeki risk değerlendirmesini uyumluluk koşulu olarak almak için kullanın. İzin verilen en yüksek tehdit düzeyini seçin:
  - **Yapılandırılmadı** (*varsayılan*)  
  - **Net** -Bu seçenek, cihazın herhangi bir tehdit sahibi olmadığı için en güvenli seçenektir. Cihazın herhangi bir tehdit düzeyine sahip olduğu algılanırsa, uyumlu değil olarak değerlendirilir.
  - **Düşük** -cihaz, yalnızca düşük düzeyde tehditler varsa uyumlu olarak değerlendirilir. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
  - **Orta** -cihazdaki mevcut tehditler düşük veya orta düzeydeyse cihaz uyumlu olarak değerlendirilir. Yüksek düzeyde tehditler algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Yüksek** -Bu seçenek en az güvenlidir ve tüm tehdit düzeylerine izin verir. Bu çözüm, yalnızca raporlama amacıyla kullanıyorsanız kullanışlı olabilir.
  
  Microsoft Defender ATP 'yi (Gelişmiş tehdit koruması) Savunma tehdidi hizmeti olarak ayarlamak için bkz. [Microsoft Defender ATP 'Yi koşullu erişim Ile etkinleştirme](advanced-threat-protection.md).


## <a name="windows-holographic-for-business"></a>Windows 10 Holographic for Business

Windows Holographic for Business, **Windows 10 ve sonrası** platformları kullanır. Windows Holographic for Business, aşağıdaki ayarı destekler:

- **Sistem Güvenliği** > **Şifreleme** > **Cihazda veri deposu şifrelemesi**.

Microsoft HoloLens’te cihaz şifrelemesini doğrulamak için bkz. [Cihaz şifrelemesini doğrulama](https://docs.microsoft.com/hololens/hololens-encryption#verify-device-encryption).

## <a name="surface-hub"></a>Surface Hub

Surface Hub, **Windows 10 ve sonrası** platformları kullanır. Surface Hub 'Lar hem uyumluluk hem de koşullu erişim için desteklenir. Surface Hub 'Larda bu özellikleri etkinleştirmek için Intune 'da [Windows 10 otomatik kaydını etkinleştirmenizi](../enrollment/windows-enroll.md) öneririz (Azure Active Directory (Azure AD) gerektirir) ve Surface Hub cihazlarını cihaz grupları olarak hedefleyebilirsiniz. Surface Hub 'Ların uyumluluk ve koşullu erişim için Azure AD 'ye katılmış olması gerekir.

Rehberlik için bkz. [Windows cihazları için kayıt ayarlama](../enrollment/windows-enroll.md).

## <a name="next-steps"></a>Sonraki adımlar

- [Uyumlu olmayan cihazlara uygulanacak eylemleri ekleyin](actions-for-noncompliance.md) ve [ilkeleri filtrelemek için kapsam etiketlerini kullanın](../fundamentals/scope-tags.md).
- [Uyumluluk ilkelerinizi izleyin](compliance-policy-monitor.md).
- Windows 8.1 cihazlar [için uyumluluk ilkesi ayarları](compliance-policy-create-windows-8-1.md) ' na bakın.
