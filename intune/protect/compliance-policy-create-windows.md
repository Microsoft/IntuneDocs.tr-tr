---
title: Microsoft Intune-Azure 'da Windows 10 uyumluluk ayarları | Microsoft Docs
description: Microsoft Intune içindeki Windows 10, Windows holographic ve Surface Hub cihazlarınız için uyumluluk ayarlarken kullanabileceğiniz tüm ayarların listesini görüntüleyin. En düşük ve en yüksek işletim sistemlerinde uyumluluğu denetleyin, parola kısıtlamalarını ve uzunluğu ayarlayın, iş ortağı Anti-Virus (AV) çözümlerini denetleyin, veri depolamada şifrelemeyi etkinleştirin ve daha fazlasını yapın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/10/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 493db6299aa8242d0ca6ab669b313e85d0dc14c6
ms.sourcegitcommit: b1e97211db7cb949eb39be6776b3a11d434fdab0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/10/2019
ms.locfileid: "72251576"
---
# <a name="windows-10-and-later-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Cihazları Intune ile uyumlu veya uyumsuz olarak işaretlemek için Windows 10 ve üzeri ayarları

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bu makalede, Intune 'da Windows 10 ve üzeri cihazlarda yapılandırabileceğiniz farklı uyumluluk ayarları listelenir ve açıklanmaktadır. Mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak BitLocker 'ı gerektirmek, en düşük ve en yüksek işletim sistemi ayarlamak, Microsoft Defender Gelişmiş tehdit koruması (ATP) kullanarak bir risk düzeyi ayarlamak ve daha fazlasını yapmak için bu ayarları kullanın.

Bu özellik için geçerlidir:

- Windows 10 ve üzeri
- Windows holographic for Business
- Surface Hub

Bir Intune Yöneticisi olarak, kuruluş kaynaklarınızı korumaya yardımcı olması için bu uyumluluk ayarlarını kullanın. Uyumluluk ilkeleri ve ne yaptıkları hakkında daha fazla bilgi edinmek için bkz. [Cihaz uyumluluğunu kullanmaya başlama](device-compliance-get-started.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Bir uyumluluk Ilkesi oluşturun](create-compliance-policy.md#create-the-policy). **Platform**için **Windows 10 ve üzeri**' i seçin.

## <a name="device-health"></a>Cihaz sistem durumu

- **BitLocker gerektir**: **gerekli**olarak ayarlandığında cihaz, sistem kapalı veya hazırda bekleme durumunda sürücüde depolanan verileri yetkisiz erişimden koruyabilir. Windows BitLocker Sürücü Şifrelemesi, Windows işletim sistemi biriminde depolanan tüm verileri şifreler. BitLocker, Windows işletim sistemini ve Kullanıcı verilerini korumaya yardımcı olmak için TPM 'YI kullanır. Ayrıca, sol tarafta bırakılmış, kayıp veya çalınmış olsa bile bir bilgisayarın üzerinde oynanmadığını doğrulamanıza yardımcı olur. Bilgisayarda uyumlu bir TPM varsa, BitLocker verileri koruyan şifreleme anahtarlarını kilitlemek için TPM 'YI kullanır. Sonuç olarak, TPM bilgisayarın durumunu doğrulana kadar anahtarlara erişilemez.

  **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.

- **Cihazda güvenli önyüklemenin etkinleştirilmesini gerektir**: **iste**' ye ayarlandığında, sistem fabrika güvenilen durumuna önyüklemeye zorlanır. Etkinleştirildiğinde, makineyi önyüklemek için kullanılan çekirdek bileşenleri, cihazı üreten kuruluşun güvendiği doğru şifreleme imzalarına sahip olmalıdır. UEFı üretici yazılımı, makinenin başlamasını izin vermeden önce imzayı doğrular. Herhangi bir dosya üzerinde değişiklik yapılmışsa ve imzasını kesen sistem önyükleme yapmaz.

  **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.

  > [!NOTE]
  > **Cihazda güvenli önyüklemenin etkinleştirilmesini gerektir** AYARı bazı TPM 1,2 ve 2,0 cihazlarda desteklenir. TPM 2,0 veya üstünü desteklemeyen cihazlarda, Intune 'daki ilke durumu **uyumlu değil**olarak gösterilir. Desteklenen sürümler hakkında daha fazla bilgi için bkz. [cihaz sistem durumu kanıtlama](https://docs.microsoft.com/windows/security/information-protection/tpm/trusted-platform-module-overview#device-health-attestation).

- **Kod bütünlüğü gerektir**: kod bütünlüğü, bir sürücünün veya sistem dosyasının belleğe her yüklendiğinde bütünlüğünü doğrulayan bir özelliktir. **Gerekli**olarak ayarlandığında, kod bütünlüğü çekirdeğe imzasız bir sürücü veya sistem dosyası yüklenip yüklenmediğini algılar. Ayrıca, bir sistem dosyasının, yönetici ayrıcalıklarına sahip bir kullanıcı hesabı tarafından çalıştırılan kötü amaçlı yazılımlara karşı değişmediğini de algılar.

  **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, bu ayar uyumluluk veya uyumsuzluk için değerlendirilmez.

Daha fazla kaynak:

- [Durum KANıTLAMA CSP](https://docs.microsoft.com/windows/client-management/mdm/healthattestation-csp) 'si, hizmetinin nasıl çalıştığı hakkında ayrıntılı bilgiler içerir.
- [Destek Ipucu: Intune uyumluluk Ilkenizin kapsamında Cihaz Sistem Durumu Kanıtlama ayarlarını kullanma](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Using-Device-Health-Attestation-Settings-as-Part-of/ba-p/282643)

## <a name="device-properties"></a>Cihaz özellikleri

- **En düşük işletim sistemi sürümü**: izin verilen en düşük sürümü **Major.Minor.Build.cu sayı** biçiminde girin. Doğru değeri almak için bir komut istemi açın ve `ver` yazın. @No__t-0 komutu sürümü aşağıdaki biçimde döndürür:

  `Microsoft Windows [Version 10.0.17134.1]`

  Bir cihazın girdiğiniz işletim sistemi sürümünden önceki bir sürümü varsa, uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Son Kullanıcı cihazını yükseltmeyi seçebilir. Yükseltildikten sonra şirket kaynaklarına erişebilirler.

- **En yüksek işletim sistemi sürümü**: izin verilen en fazla sürümü, **ana. Minor. Build. Revision sayı** biçiminde girin. Doğru değeri almak için bir komut istemi açın ve `ver` yazın. @No__t-0 komutu sürümü aşağıdaki biçimde döndürür:

  `Microsoft Windows [Version 10.0.17134.1]`

  Bir cihaz, girilen sürümden daha sonraki bir işletim sistemi sürümünü kullanırken, kuruluş kaynaklarına erişim engellenir. Son kullanıcıdan BT yöneticisiyle iletişim kurabilmesi istenir. Cihaz, işletim sistemi sürümüne izin verecek şekilde değiştirilene kadar kuruluş kaynaklarına erişemez.

- **Mobil cihazlar için gereken en düşük işletim sistemi**: izin verilen en düşük sürümü, ana. Minor. Build sayı biçiminde girin.

  Bir cihaz, girdiğiniz işletim sistemi sürümünün önceki bir sürümüne sahip olduğunda, uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Son Kullanıcı cihazını yükseltmeyi seçebilir. Yükseltildikten sonra şirket kaynaklarına erişebilirler.

- **Mobil cihazlar için gereken en yüksek işletim sistemi**: izin verilen en fazla sürümü, ana. ikincil. derleme numarasında girin.

  Bir cihaz, girilen sürümden daha sonraki bir işletim sistemi sürümünü kullanırken, kuruluş kaynaklarına erişim engellenir. Son kullanıcıdan BT yöneticisiyle iletişim kurabilmesi istenir. Cihaz, işletim sistemi sürümüne izin verecek şekilde değiştirilene kadar kuruluş kaynaklarına erişemez.

- **Geçerli işletim sistemi derlemeleri**: en düşük ve en yüksek sürüm içeren, kabul edilebilir işletim sistemi sürümleri için bir Aralık girin. Ayrıca, bu kabul edilebilir işletim sistemi yapı numaralarının bir virgülle ayrılmış değerler (CSV) dosya listesini de **dışarı aktarabilirsiniz** .

## <a name="configuration-manager-compliance"></a>Configuration Manager uyumluluğu

Yalnızca Windows 10 ve üzeri çalıştıran ortak yönetilen cihazlar için geçerlidir. Yalnızca Intune cihazları kullanılabilir olmayan bir durum döndürüyor.

- **System Center Configuration Manager cihaz uyumluluğu gerektir**: System Center Configuration Manager tüm ayarların (yapılandırma öğeleri) uyumlu olmasını zorunlu kılmak için **gerektir** ' i seçin. 

  Örneğin, cihazlarda tüm yazılım güncelleştirmelerinin yüklü olması gerekir. Configuration Manager, bu gereksinimin "yüklü" durumu vardır. Cihazdaki herhangi bir program bilinmeyen bir durumdaysa, cihaz Intune 'da uyumlu değildir.
  
  **Yapılandırılmadığında**, ıntune uyumluluk Configuration Manager ayarlarından herhangi birini denetlemez.

## <a name="system-security"></a>Sistem güvenliği

### <a name="password"></a>Parola

- **Mobil cihazların kilidini açmak için parola gerektir**: Kullanıcıların cihazlarına erişebilmek için bir parola girmelerini **gerektir** . **Yapılandırılmadığında**, Intune, cihazı uyumluluk için parola ayarları olarak değerlendirmez.
- **Basit parolalar**: kullanıcıların, **1234** veya **1111**gibi basit parolalar oluşturmaması için **Engelle** olarak ayarlayın. Kullanıcıların **1234** veya **1111**gibi parolalar oluşturmalarına izin vermek için **Yapılandırılmadı** olarak ayarlayın.
- **Parola türü**: gerekli parola veya PIN türünü seçin. Seçenekleriniz:

  - **Cihaz varsayılanı**: parola, sayısal PIN veya alfasayısal PIN gerektir
  - **Sayısal**: parola veya sayısal PIN gerektir
  - **Alfasayısal**: parola veya alfasayısal PIN gerektirir. **Parola karmaşıklığını**da seçin: 
    
    - **Rakamlar ve küçük harfler gerektir**
    - **Rakamlar, küçük harfler ve büyük harfler iste**
    - **Rakamlar, küçük harfler, büyük harfler ve özel karakterler iste**

    > [!TIP]
    > Alfasayısal parola ilkeleri karmaşık olabilir. Daha fazla bilgi için yöneticilerin CSP 'Leri okumasını öneririz:
    >
    > - [DeviceLock/alfanümerik ıdevicepasswordrequired CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-alphanumericdevicepasswordrequired)
    > - [DeviceLock/MinDevicePasswordComplexCharacters CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-mindevicepasswordcomplexcharacters)

- **Minimum parola uzunluğu**: parolanın sahip olması gereken en az rakam veya karakter sayısını girin.
- **Parola istenmeden önce geçen işlem yapılmayan dakika**sayısı: kullanıcının parolasını yeniden girmesi gerekmeden önce boşta geçen süreyi girin.
- **Parola kullanım süresi (gün)** : parolanın süresi dolmadan önce geçecek gün sayısını girin ve 1-730 adresinden yeni bir tane oluşturmanız gerekir.
- **Yeniden kullanılmasını önleyen önceki parola sayısı**: daha önce kullanılan parolaların sayısını girin.
- **Cihaz boşta durumundan çıktığında parola iste (Mobile ve holographic)** : cihaz boşta durumundan çıkarken kullanıcıları parolayı girmeye zorlayın.

  > [!IMPORTANT]
  > Parola gereksinimi bir Windows masaüstünde değiştirildiğinde, bu cihaz boşta durumundan etkin 'e geçtiğinde, kullanıcılar bir sonraki oturum açışlarında etkilenir. Gereksinimi karşılayan parolalara sahip olan kullanıcılar parolalarını değiştirmelerini de istenir.

### <a name="encryption"></a>Şifreleme

- **Bir cihazda veri depolamayı şifreleme**: cihazlarınızda veri depolamayı şifrelemek için **gerektir** ' i seçin.

  > [!NOTE]
  > **Bir cihaz ayarında veri depolamanın şifrelenmesi** , cihazda şifreleme varlığını denetler. Daha sağlam bir şifreleme ayarı için, TPM düzeyinde BitLocker durumunu doğrulamak üzere Windows Cihaz Sistem Durumu Kanıtlama yararlanan **BitLocker gerektir**seçeneğini kullanmayı düşünün.

### <a name="device-security"></a>Cihaz güvenliği

- **Güvenlik duvarı**: Microsoft Defender güvenlik duvarını açmak ve kullanıcıların bunu kapatmasını **engellemek için ayarlayın** . **Yapılandırılmadı** (varsayılan), Microsoft Defender güvenlik duvarını denetlemez ve var olan ayarları değiştirmez.

  [Güvenlik Duvarı CSP 'si](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp)

  > [!NOTE]
  > Yeniden başlatmanın ardından cihaz hemen eşitleniyorsa veya uykudan uyandırmaya hemen eşitlendikten sonra, bu ayar bir **hata**olarak rapor verebilir. Bu senaryo genel cihaz uyumluluk durumunu etkilemeyebilir. Uyumluluk durumunu yeniden değerlendirmek için cihazı el ile [eşitleyin](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows).

- **Güvenilir Platform Modülü (TPM)** : **gerekli**olarak ayarlandığında, Intune sürümü uyumluluğu denetler. TPM yonga sürümü 0 ' dan büyükse cihaz uyumludur (sıfır). Cihazda TPM sürümü yoksa cihaz uyumlu değildir. **Yapılandırılmadığında**, ıNTUNE bir TPM yonga sürümü için cihazı denetlemez.

  [DeviceStatus CSP-DeviceStatus/TPM/SpecificationVersion düğümü](https://docs.microsoft.com/windows/client-management/mdm/devicestatus-csp)
  
- **Virüsten koruma**: **gerekli**olarak ayarlandığında, [Windows Güvenlik Merkezi](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/)Ile kaydedilen ve Symantec ve Microsoft Defender gibi virüsten koruma çözümlerini kullanarak uyumluluğu kontrol edebilirsiniz. **Yapılandırılmadığında**, Intune cihazda yüklü olan HERHANGI bir av çözümünü denetlemez.
- **Casus yazılımdan koruma**: **gerekli**olarak ayarlandığında, [Windows Güvenlik Merkezi](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/)Ile kaydedilen ve Symantec ve Microsoft Defender gibi casus yazılımdan koruma çözümlerini kullanarak uyumluluğu kontrol edebilirsiniz. **Yapılandırılmadığında**, Intune cihazda yüklü olan herhangi bir casus yazılımdan koruma çözümünü denetlemez.

### <a name="defender"></a>Defender

- **Microsoft Defender kötü amaçlı yazılımdan koruma**: Microsoft Defender kötü amaçlı yazılımdan koruma hizmetini açmak ve kullanıcıların bunu kapatmasını **engellemek için ayarlayın** . **Yapılandırılmadı** (varsayılan) hizmeti denetlemez ve var olan ayarları değiştirmez.
- **Microsoft Defender kötü amaçlı yazılımdan koruma en düşük sürüm**: en düşük Microsoft Defender kötü amaçlı yazılımdan koruma hizmeti sürümünü girin. Örneğin, `4.11.0.0` girin. Boş bırakılırsa, Microsoft Defender kötü amaçlı yazılımdan koruma hizmeti 'nin herhangi bir sürümü kullanılabilir.
- **Microsoft Defender kötü amaçlı yazılımdan koruma güvenlik zekası güncel**: cihazlarda Windows Güvenlik virüsü ve tehdit koruması güncelleştirmelerini denetler. **Gerektir** , Microsoft Defender güvenlik zekasını güncel olmaya zorlar. **Yapılandırılmadı** (varsayılan) hiçbir gereksinimi zorlamaz.

  [Microsoft Defender virüsten koruma ve diğer Microsoft Antimalware Için güvenlik zekası güncelleştirmeleri](https://www.microsoft.com/en-us/wdsi/defenderupdates) , Güvenlik Zekası hakkında daha fazla bilgi içerir.

- **Gerçek zamanlı koruma**: **gerektir** , kötü amaçlı yazılım, casus yazılım ve diğer istenmeyen yazılımları tarayan gerçek zamanlı korumayı etkinleştirir. **Yapılandırılmadı** (varsayılan), bu özelliği denetlemez ve var olan ayarları değiştirmez.

  [Defender/AllowRealtimeMonitoring CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-allowrealtimemonitoring)

## <a name="microsoft-defender-atp"></a>Microsoft Defender ATP

- **Cihazın makine risk puanı üzerinde veya altında olmasını gerektir**: Bu ayarı, savunma tehdidi hizmetinizdeki risk değerlendirmesini uyumluluk koşulu olarak almak için kullanın. İzin verilen en yüksek tehdit düzeyini seçin:

  - **Temizle**: cihazın tehditleri olmadığı için bu seçenek en güvenli seçenektir. Cihazın herhangi bir tehdit düzeyine sahip olduğu algılanırsa, uyumlu değil olarak değerlendirilir.
  - **Düşük**: cihaz, yalnızca düşük düzeyde tehditler varsa uyumlu olarak değerlendirilir. Daha yüksek olan her şey, cihazı uyumlu olmayan bir duruma geçirir.
  - **Orta**: cihazdaki mevcut tehditler düşük veya orta düzeydeyse cihaz uyumlu olarak değerlendirilir. Cihazın yüksek düzeyde tehditleri algılanırsa, uyumlu değil olarak belirlenir.
  - **Yüksek**: Bu seçenek en az güvenlidir ve tüm tehdit düzeylerine izin verir. Bu çözümü yalnızca raporlama amacıyla kullanıyorsanız kullanışlı olabilir.
  
  Microsoft Defender ATP 'yi (Gelişmiş tehdit koruması) Savunma tehdidi hizmeti olarak ayarlamak için bkz. [Microsoft Defender ATP 'Yi koşullu erişim Ile etkinleştirme](advanced-threat-protection.md).

Değişikliklerinizi kaydetmek için **tamam** > **Oluştur** ' u seçin.

## <a name="windows-holographic-for-business"></a>Windows holographic for Business

Windows holographic for Business, **Windows 10 ve üzeri** platformunu kullanır. Windows holographic for Business, aşağıdaki ayarı destekler:

- **Sistem güvenliği** > **şifreleme** > **cihazdaki veri depolamanın şifrelemesi**.

Microsoft HoloLens 'te cihaz şifrelemesini doğrulamak için bkz. [Cihaz şifrelemesini doğrulama](https://docs.microsoft.com/hololens/hololens-encryption#verify-device-encryption).

## <a name="surface-hub"></a>Surface Hub

Surface Hub, **Windows 10 ve üzeri** platformunu kullanır. Surface Hub 'Lar hem uyumluluk hem de koşullu erişim için desteklenir. Surface Hub 'Larda bu özellikleri etkinleştirmek için Intune 'da [Windows 10 otomatik kaydını etkinleştirmenizi](../enrollment/windows-enroll.md) öneririz (Azure Active Directory (Azure AD) gerektirir) ve Surface Hub cihazlarını cihaz grupları olarak hedefleyebilirsiniz. Surface Hub 'Ların uyumluluk ve koşullu erişim için Azure AD 'ye katılmış olması gerekir.

Kılavuz için bkz. [Windows cihazları için kayıt ayarlama](../enrollment/windows-enroll.md) .

## <a name="next-steps"></a>Sonraki adımlar

- [Uyumsuz cihazlara yönelik eylemler ekleyin](actions-for-noncompliance.md) ve [ilkeleri filtrelemek için kapsam etiketlerini kullanın](../fundamentals/scope-tags.md).
- [Uyumluluk Ilkelerinizi izleyin](compliance-policy-monitor.md).
- Windows 8.1 cihazlar [için uyumluluk ilkesi ayarları](compliance-policy-create-windows-8-1.md) ' na bakın.
