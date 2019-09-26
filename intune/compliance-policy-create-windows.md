---
title: Microsoft Intune-Azure 'da Windows 10 uyumluluk ayarları | Microsoft Docs
description: Microsoft Intune içindeki Windows 10, Windows holographic ve Surface Hub cihazlarınız için uyumluluk ayarlarken kullanabileceğiniz tüm ayarların listesini görüntüleyin. En düşük ve en yüksek işletim sistemlerinde uyumluluğu denetleyin, parola kısıtlamalarını ve uzunluğu ayarlayın, iş ortağı Anti-Virus (AV) çözümlerini denetleyin, veri depolamada şifrelemeyi etkinleştirin ve daha fazlasını yapın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/12/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cda6c5f5ffa2244376e318e81a38a1ed410a443f
ms.sourcegitcommit: 1494ff4b33c13a87f20e0f3315da79a3567db96e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2019
ms.locfileid: "71305040"
---
# <a name="windows-10-and-later-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Cihazları Intune ile uyumlu veya uyumsuz olarak işaretlemek için Windows 10 ve üzeri ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makalede, Intune 'da Windows 10 ve üzeri cihazlarda yapılandırabileceğiniz farklı uyumluluk ayarları listelenir ve açıklanmaktadır. Mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak BitLocker 'ı gerektirmek, en düşük ve en yüksek işletim sistemi ayarlamak, Microsoft Defender Gelişmiş tehdit koruması (ATP) kullanarak bir risk düzeyi ayarlamak ve daha fazlasını yapmak için bu ayarları kullanın.

Bu özellik şu platformlarda geçerlidir:

- Windows 10 ve üzeri
- Windows 10 Holographic for Business
- Surface Hub

Intune yöneticisi olarak bu uyumluluk ayarlarını kullanarak kuruluşunuzun kaynaklarının korunmasına yardımcı olabilirsiniz. Uyumluluk ilkeleri ve işlevleri hakkında daha fazla bilgi için bkz. [Cihaz uyumluluğunu kullanmaya başlama](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Uyumluluk ilkesi oluşturma](create-compliance-policy.md#create-the-policy). **Platform** olarak **Windows 10 ve üzeri**'ni seçin.

## <a name="device-health"></a>Device health

- **BitLocker gerektir**: **Gerekli**olarak ayarlandığında cihaz, sistem kapalı veya hazırda bekleme durumunda sürücüde depolanan verileri yetkisiz erişimden koruyabilir. Windows BitLocker Sürücü Şifrelemesi, Windows işletim sistemi birimine depolanan tüm verileri şifreler. BitLocker, Windows işletim sistemini ve kullanıcı verilerini korumaya yardımcı olmak için TPM'yi kullanır. Ayrıca, sol tarafta bırakılmış, kayıp veya çalınmış olsa bile bir bilgisayarın üzerinde oynanmadığını doğrulamanıza yardımcı olur. Bilgisayarda uyumlu bir TPM varsa, BitLocker verileri koruyan şifreleme anahtarlarını kilitlemek için TPM kullanır. Sonuç olarak, TPM bilgisayarın durumunu doğrulana kadar anahtarlara erişilemez.

  **Yapılandırılmadı** (varsayılan) ayarını belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

- **Cihazda güvenli önyüklemenin etkinleştirilmesini gerektir**: Gerektir olarak ayarlandığında, sistem, fabrikada güvenilen bir duruma önyükleme **yapılmasını**zorlanmıştır. Etkinleştirildiğinde, makineyi önyüklemek için kullanılan çekirdek bileşenleri, cihazı üreten kuruluşun güvendiği doğru şifreleme imzalarına sahip olmalıdır. UEFI üretici yazılımı, makinenin başlatılmasına izin vermeden önce imzayı doğrular. Herhangi bir dosya üzerinde değişiklik yapılmışsa ve imzasını kesen sistem önyükleme yapmaz.

  **Yapılandırılmadı** (varsayılan) ayarını belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

  > [!NOTE]
  > **Cihazda güvenli önyüklemenin etkinleştirilmesini gerektir** AYARı bazı TPM 1,2 ve 2,0 cihazlarda desteklenir. TPM 2.0 ve sonrasını desteklemeyen cihazlarda ilke durumu Intune'da **Uyumsuz** olarak gösterilir. Desteklenen sürümler hakkında daha fazla bilgi için bkz. [cihaz sistem durumu kanıtlama](https://docs.microsoft.com/windows/security/information-protection/tpm/trusted-platform-module-overview#device-health-attestation).

- **Kod bütünlüğü gerektir**: Kod bütünlüğü, bir sürücünün veya sistem dosyasının belleğe her yüklendiğinde bütünlüğünü doğrulayan bir özelliktir. **Gerekli**olarak ayarlandığında, kod bütünlüğü çekirdeğe imzasız bir sürücü veya sistem dosyası yüklenip yüklenmediğini algılar. Ayrıca, bir sistem dosyasının, yönetici ayrıcalıklarına sahip bir kullanıcı hesabı tarafından çalıştırılan kötü amaçlı yazılımlara karşı değişmediğini de algılar.

  **Yapılandırılmadı** (varsayılan) ayarını belirtirseniz bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez.

Daha fazla kaynak:

- [Durum KANıTLAMA CSP](https://docs.microsoft.com/windows/client-management/mdm/healthattestation-csp) 'si, hizmetinin nasıl çalıştığı hakkında ayrıntılı bilgiler içerir.
- [Destek Ipucu: Intune uyumluluk Ilkenizin kapsamında Cihaz Sistem Durumu Kanıtlama ayarlarını kullanma](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Using-Device-Health-Attestation-Settings-as-Part-of/ba-p/282643)

## <a name="device-properties"></a>Cihaz özellikleri

- **En düşük işletim sistemi sürümü**: **Major.Minor.Build.cu sayı** biçiminde izin verilen en düşük sürümü girin. Doğru değeri almak için, komut istemini açın ve `ver` yazın. `ver` komutu, sürümü şu biçimde döndürür:

  `Microsoft Windows [Version 10.0.17134.1]`

  Bir cihazın girdiğiniz işletim sistemi sürümünden önceki bir sürümü varsa, uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Son kullanıcı cihazını yükseltmeyi seçebilir. Yükseltildikten sonra şirket kaynaklarına erişebilirler.

- **En yüksek işletim sistemi sürümü**: İzin verilen en fazla sürümü, **ana. Minor. Build. Revision sayı** biçiminde girin. Doğru değeri almak için, komut istemini açın ve `ver` yazın. `ver` komutu, sürümü şu biçimde döndürür:

  `Microsoft Windows [Version 10.0.17134.1]`

  Bir cihaz, girilen sürümden daha sonraki bir işletim sistemi sürümünü kullanırken, kuruluş kaynaklarına erişim engellenir. Son kullanıcıdan BT yöneticisine başvurması istenir. Cihaz, işletim sistemi sürümüne izin verecek şekilde değiştirilene kadar kuruluş kaynaklarına erişemez.

- **Mobil cihazlar için gereken en düşük işletim sistemi**: İzin verilen en düşük sürümü, ana. Minor. Build sayı biçiminde girin.

  Bir cihaz, girdiğiniz işletim sistemi sürümünün önceki bir sürümüne sahip olduğunda, uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Son kullanıcı cihazını yükseltmeyi seçebilir. Yükseltildikten sonra şirket kaynaklarına erişebilirler.

- **Mobil cihazlar için gereken en yüksek işletim sistemi**: İzin verilen en fazla sürümü, ana. ikincil. derleme numarasında girin.

  Bir cihaz, girilen sürümden daha sonraki bir işletim sistemi sürümünü kullanırken, kuruluş kaynaklarına erişim engellenir. Son kullanıcıdan BT yöneticisine başvurması istenir. Cihaz, işletim sistemi sürümüne izin verecek şekilde değiştirilene kadar kuruluş kaynaklarına erişemez.

- **Geçerli işletim sistemi derlemeleri**: En düşük ve en yüksek dahil olmak üzere, kabul edilebilir işletim sistemi sürümleri için bir Aralık girin. Kabul edilebilir derleme numaraları için bir virgülle ayrılmış değerler (CSV) dosya listesi **Dışarı Aktarabilirsiniz**.

## <a name="configuration-manager-compliance"></a>Configuration Manager uyumluluğu

Yalnızca Windows 10 ve üzeri çalıştıran ortak yönetilen cihazlar için geçerlidir. Yalnızca Intune cihazları kullanılabilir olmayan bir durum döndürüyor.

- **System Center Configuration Manager cihaz uyumluluğunu gerektir**: System Center Configuration Manager tüm ayarların (yapılandırma öğeleri) uyumlu olmasını zorunlu kılmak için **gerektir** ' i seçin. 

  Örneğin, tüm yazılım güncelleştirmelerinin cihazlarda yüklü olmasını gerektirirsiniz. Configuration Manager’da bu gereksinim, “Yüklü” durumundadır. Cihazdaki herhangi bir program bilinmeyen bir durumdaysa, cihaz Intune 'da uyumlu değildir.
  
  **Yapılandırılmadığında**, ıntune uyumluluk Configuration Manager ayarlarından herhangi birini denetlemez.

## <a name="system-security"></a>Sistem güvenliği

### <a name="password"></a>istemcisiyle yönetilen bir cihaz için)

- **Mobil cihazların kilidini açmak için parola gerektir**: Kullanıcıların cihazlarına erişebilmesi için önce bir parola girmesini **zorunlu tutun**. **Yapılandırılmadığında**, Intune, cihazı uyumluluk için parola ayarları olarak değerlendirmez.
- **Basit parolalar**: Bunu **Engelle** şeklinde ayarlayarak, kullanıcıların **1234** veya **1111** gibi basit parolalar oluşturmalarının önüne geçin. Kullanıcıların **1234** veya **1111** gibi parolalar oluşturmalarına izin vermek için **Yapılandırılmadı** olarak ayarlayın.
- **Parola türü**: Gerekli parola veya PIN türünü seçin. Seçenekleriniz şunlardır:

  - **Cihaz varsayılanı**: Parola, sayısal PIN veya alfasayısal PIN gerektir
  - **Sayısal**: Parola veya sayısal PIN gerektir
  - **Alfasayısal**: Parola veya alfasayısal PIN gerektir. **Parola karmaşıklığını**da seçin: 
    
    - **Rakamlar ve küçük harfler gerektir**
    - **Rakamlar, küçük harfler ve büyük harfler iste**
    - **Rakamlar, küçük harfler, büyük harfler ve özel karakterler iste**

    > [!TIP]
    > Alfasayısal parola ilkeleri karmaşık olabilir. Daha fazla bilgi için yöneticilerin CSP 'Leri okumasını öneririz:
    >
    > - [DeviceLock/alfanümerik ıdevicepasswordrequired CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-alphanumericdevicepasswordrequired)
    > - [DeviceLock/MinDevicePasswordComplexCharacters CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-mindevicepasswordcomplexcharacters)

- **Minimum parola uzunluğu**: Parolanın sahip olması gereken minimum rakam veya karakter sayısını girin.
- **Parola istenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı**: Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi girin.
- **Parola zaman aşımı (gün sayısı)** : Parolanın süresi dolmadan önce geçecek gün sayısını girin ve 1-730 adresinden yeni bir tane oluşturmanız gerekir.
- **Yeniden kullanılması önlenecek önceki parola sayısı**: Daha önce kullanılan kaç parolanın kullanılamayacağını belirtir.
- **Cihaz boşta durumundan çıktığında parola iste (Mobile ve holographic)** : Cihaz boşta durumundan çıkarken kullanıcıları parola girmeye zorlayın.

  > [!IMPORTANT]
  > Parola gereksinimi bir Windows masaüstünde değiştirildiğinde, bu cihaz boşta durumundan etkin 'e geçtiğinde, kullanıcılar bir sonraki oturum açışlarında etkilenir. Gereksinimi karşılayan parolalara sahip olan kullanıcılar parolalarını değiştirmelerini de istenir.

### <a name="encryption"></a>Şifreleme

- **Cihazda veri deposunun şifrelenmesi**: Cihazlarınızda veri deposunun şifrelenmesini sağlamak için **Gerekli Kıl**'ı seçin.

  > [!NOTE]
  > **Bir cihazdaki veri depolama şifrelemesi** ayarı cihazdaki genel şifreleme varlığını denetler. Daha güçlü bir şifreleme ayarı için **BitLocker’ı gerektir** ayarını kullanmayı göz önünde bulundurabilirsiniz. Bu ayar, TPM düzeyinde BitLocker durumunu doğrulamak için Windows Cihaz Sistem Durumu Kanıtlama özelliğinden yararlanır.

### <a name="device-security"></a>Cihaz Güvenliği

- **Güvenlik Duvarı**: Microsoft Defender güvenlik duvarını açmak ve kullanıcıların bunu kapatmasını **engellemek için ayarlayın** . **Yapılandırılmadı** (varsayılan), Microsoft Defender güvenlik duvarını denetlemez ve var olan ayarları değiştirmez.

  [Güvenlik Duvarı CSP 'si](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp)

- **Güvenilir Platform Modülü (TPM)** : İzin **iste**' ye ayarlandığında, Intune sürümü uyumluluk için denetler. TPM yonga sürümü 0 ' dan büyükse cihaz uyumludur (sıfır). Cihazda TPM sürümü yoksa cihaz uyumlu değildir. **Yapılandırılmadığında**, ıNTUNE bir TPM yonga sürümü için cihazı denetlemez.

  [DeviceStatus CSP-DeviceStatus/TPM/SpecificationVersion düğümü](https://docs.microsoft.com/windows/client-management/mdm/devicestatus-csp)
  
- **Virüsten koruma**: **Gerektir**olarak ayarlandığında, [Windows Güvenlik Merkezi](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/)ile kaydedilen ve Symantec ve Microsoft Defender gibi virüsten koruma çözümlerini kullanarak uyumluluğu kontrol edebilirsiniz. **Yapılandırılmadı** olarak bırakıldığında, Intune cihazda herhangi bir AV çözümünün yüklü olup olmadığını denetlemez.
- **Casus yazılımdan koruma**: **Gerektir**olarak ayarlandığında, [Windows Güvenlik Merkezi](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/)ile kaydedilen ve Symantec ve Microsoft Defender gibi casus yazılımdan koruma çözümlerini kullanarak uyumluluğu kontrol edebilirsiniz. **Yapılandırılmadı** olarak bırakıldığında, Intune cihazda herhangi bir casus yazılımdan koruma çözümünün yüklü olup olmadığını denetlemez.

### <a name="defender"></a>Defender

- **Microsoft Defender kötü amaçlı yazılımdan koruma**: Microsoft Defender kötü amaçlı yazılımdan koruma hizmetini açmak ve kullanıcıların bunu kapatmasını **engellemek için ayarlayın** . **Yapılandırılmadı** (varsayılan) hizmeti denetlemez ve var olan ayarları değiştirmez.
- **Microsoft Defender kötü amaçlı yazılımdan koruma en düşük sürümü**: Microsoft Defender kötü amaçlı yazılımdan koruma hizmeti 'nin izin verilen en düşük sürümünü girin. Örneğin, şunu girin: `4.11.0.0`. Boş bırakılırsa, Microsoft Defender kötü amaçlı yazılımdan koruma hizmeti 'nin herhangi bir sürümü kullanılabilir.
- **Microsoft Defender kötü amaçlı yazılımdan koruma güvenlik zekası güncel**: Cihazlarda Windows Güvenlik virüsü ve tehdit koruması güncelleştirmelerini denetler. **Gerektir** , Microsoft Defender güvenlik zekasını güncel olmaya zorlar. **Yapılandırılmadı** (varsayılan) hiçbir gereksinimi zorlamaz.

  [Microsoft Defender virüsten koruma ve diğer Microsoft Antimalware Için güvenlik zekası güncelleştirmeleri](https://www.microsoft.com/en-us/wdsi/defenderupdates) , Güvenlik Zekası hakkında daha fazla bilgi içerir.

- **Gerçek zamanlı koruma**: **Gerekli** olan gerçek zamanlı korumayı etkinleştirir; bu, kötü amaçlı yazılım, casus yazılım ve diğer istenmeyen yazılımları tarar. **Yapılandırılmadı** (varsayılan) bu özelliği denetlemez ve var olan ayarları değiştirmez.

  [Defender/AllowRealtimeMonitoring CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowrealtimemonitoring)

## <a name="microsoft-defender-atp"></a>Microsoft Defender ATP

- **Cihazın makine risk puanı üzerinde veya altında olmasını gerektir**: Bu ayarı, savunma tehdidi hizmetinizdeki risk değerlendirmesini uyumluluk koşulu olarak almak için kullanın. İzin verilen en yüksek tehdit düzeyini seçin:

  - **Temizle**: Cihazda hiçbir tehdit olmamasını gerektirdiği için bu seçenek en güvenlisidir. Cihazın herhangi bir tehdit düzeyine sahip olduğu algılanırsa, uyumlu değil olarak değerlendirilir.
  - **Düşük**: Cihaz, yalnızca düşük düzeydeki tehditler varsa uyumlu olarak değerlendirilir. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
  - **Orta**: Cihazda mevcut tehditler düşük veya orta düzeydeyse cihaz uyumlu olarak değerlendirilir. Yüksek düzeyde tehditler algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Yüksek**: Tüm tehdit düzeylerine izin verdiği için bu seçenek en düşük güvenliğe sahiptir. Bu çözüm, yalnızca raporlama amacıyla kullanıyorsanız kullanışlı olabilir.
  
  Microsoft Defender ATP 'yi (Gelişmiş tehdit koruması) Savunma tehdidi hizmeti olarak ayarlamak için bkz. [Microsoft Defender ATP 'Yi koşullu erişim Ile etkinleştirme](advanced-threat-protection.md).

Değişikliklerinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.

## <a name="windows-holographic-for-business"></a>Windows 10 Holographic for Business

Windows Holographic for Business, **Windows 10 ve sonrası** platformları kullanır. Windows Holographic for Business, aşağıdaki ayarı destekler:

- **Sistem Güvenliği** > **Şifreleme** > **Cihazda veri deposu şifrelemesi**.

Microsoft HoloLens’te cihaz şifrelemesini doğrulamak için bkz. [Cihaz şifrelemesini doğrulama](https://docs.microsoft.com/hololens/hololens-encryption#verify-device-encryption).

## <a name="surface-hub"></a>Surface Hub

Surface Hub, **Windows 10 ve sonrası** platformları kullanır. Surface Hub 'Lar hem uyumluluk hem de koşullu erişim için desteklenir. Surface Hub 'Larda bu özellikleri etkinleştirmek için Intune 'da [Windows 10 otomatik kaydını etkinleştirmenizi](windows-enroll.md) öneririz (Azure Active Directory (Azure AD) gerektirir) ve Surface Hub cihazlarını cihaz grupları olarak hedefleyebilirsiniz. Surface Hub 'Ların uyumluluk ve koşullu erişim için Azure AD 'ye katılmış olması gerekir.

Rehber için bkz. [Windows cihazları için kaydı ayarlama](windows-enroll.md).

## <a name="next-steps"></a>Sonraki adımlar

- [Uyumlu olmayan cihazlara uygulanacak eylemleri ekleyin](actions-for-noncompliance.md) ve [ilkeleri filtrelemek için kapsam etiketlerini kullanın](scope-tags.md).
- [Uyumluluk ilkelerinizi izleyin](compliance-policy-monitor.md).
- Windows 8.1 cihazlar [için uyumluluk ilkesi ayarları](compliance-policy-create-windows-8-1.md) ' na bakın.
