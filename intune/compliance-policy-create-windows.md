---
title: Microsoft Intune - Azure'da Windows cihazlarda uyumluluğu denetle | Microsoft Docs
description: Windows Phone 8.1, Windows 8.1 ve sonrası, Windows 10 ve sonrası cihazlar için bir Microsoft Intune cihaz uyumluluk ilkesi oluşturun veya yapılandırın. Surface Hub ve Windows Holographic for Business da dahil olmak üzere cihazlarda en düşük ve en yüksek işletim sistemi uyumluluğunu denetleyin, parola kısıtlamaları ve uzunluğunu ayarlayın, BitLocker’ı gerekli kılın, üçüncü (3.) taraf virüsten koruma çözümlerini denetleyin, kabul edilebilir tehdit düzeyini ayarlayın ve veri deposunda şifrelemeyi etkinleştirin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/04/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d27b4389318a8b4caeb86dec9c2c79efa0ac89f1
ms.sourcegitcommit: da9ee02de327f202b00be44c79bf7abd35b9929b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57335046"
---
# <a name="add-a-device-compliance-policy-for-windows-devices-in-intune"></a>Intune’da Windows cihazları için cihaz uyumluluk ilkesi ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune cihaz uyumluluk İlkesi, cihazlarının uyumlu olarak değerlendirilmesi için uyması gereken kuralları ve ayarları içerir. Bu ilkeleri koşullu erişimle izin vermek veya kuruluşunuzun kaynaklarına erişimi engellemek için kullanın. Ayrıca cihaz raporları alabilir ve uyumsuzluk için eylemler uygulayabilirsiniz.

Uyumluluk ilkeleri ve olası önkoşullar hakkında daha fazla bilgi için bkz. [Cihaz uyumluluğunu kullanmaya başlama](device-compliance-get-started.md).

Aşağıdaki tabloda bir uyumluluk ilkesi koşullu erişim ilkesi ile kullanıldığında uyumlu olmayan ayarların nasıl yönetildiği açıklanır.

---------------------------

| **İlke ayarı** | **Windows 8.1 ve üzeri** | **Windows Phone 8.1 ve üzeri** |
|----| ----| --- |
| **PIN veya Parola yapılandırması** | Çözümlendi | Çözümlendi |   
| **Cihaz şifrelemesi** | Uygulanamaz | Çözümlendi |   
| **Jailbreak uygulanmış veya kök erişim izni verilmiş cihaz** | Geçerli değil | Geçerli değil |  
| **E-posta profili** | Geçerli değil | Geçerli değil |   
| **En düşük işletim sistemi sürümü** | Karantinaya Alındı | Karantinaya Alındı |   
| **En yüksek işletim sistemi sürümü** | Karantinaya Alındı | Karantinaya Alındı |   
| **Windows durum kanıtlama** | Karantinaya alındı: Windows 10 ve Windows 10 Mobile|Uygulanamaz: Windows 8.1 |

-------------------------------

**Düzeltilen** = Cihazın işletim sistemi, uyumluluğu mecbur kılar. (Örneğin, kullanıcı bir PIN ayarlamaya zorlanır.)

**Karantinaya alındı** = Cihazın işletim sistemi uyumluluğu mecbur kılmaz. (Örneğin, Android cihazlar kullanıcıyı cihazı şifrelemeye zorlamaz.) Cihaz uyumsuz olduğunda, aşağıdaki işlemler yapılır:

- Kullanıcı için geçerli bir koşullu erişim ilkesi varsa cihaz engellenir.
- Şirket portalı, tüm uyumluluk sorunları hakkında kullanıcıya bildirim gönderir.

## <a name="create-a-device-compliance-policy"></a>Cihaz uyumluluğu ilkesi oluşturma

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
5. **Platform** olarak **Windows Phone 8.1**, **Windows 8.1 ve sonrası** veya **Windows 10 ve sonrası**.
6. **Ayarları Yapılandır**’ı seçin ve **Cihaz Durumu**, **Cihaz Özellikleri** ve **Sistem Güvenliği** ayarlarını girin. İşiniz bittiğinde **Tamam**’ı ve **Oluştur**’u seçin.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="windows-81-devices-policy-settings"></a>Windows 8.1 cihaz ilke ayarları

Bu ilke ayarları, şu platformları çalıştıran cihazlarda geçerlidir:

- Windows Phone 8.1
- Windows 8.1 ve üzeri

### <a name="device-properties"></a>Cihaz özellikleri

- **Gerekli en düşük işletim sistemi**: Bir cihaz en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı görüntülenir. Son kullanıcı, cihazını yükseltmeyi seçip şirket kaynaklarına erişebilir.
- **İzin verilen en yüksek işletim sistemi sürümü**: Bir cihaz girilen kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullanarak, şirket kaynaklarına erişimi engellenir. Kullanıcıdan BT yöneticisine başvurması istenir. Cihaz, işletim sistemine izin veren kuralın değiştirene kadar kuruluş kaynaklarına erişemez.

Windows 8.1 bilgisayarları **3** sürümünü döndürür. Windows için işletim sistemi sürüm kuralı Windows 8.1’e ayarlanırsa, cihaz Windows 8.1’e sahip olsa bile uyumsuz olarak bildirilir.

### <a name="system-security"></a>Sistem güvenliği

#### <a name="password"></a>istemcisiyle yönetilen bir cihaz için)

- **Mobil cihazların kilidini açmak için parola iste**: **Gerekli** kullanıcıların cihazlarına erişebilmeleri için önce bir parola girin.
- **Basit parolalar**: Kümesine **blok** kullanıcılar gibi basit parolalar oluşturamıyor **1234** veya **1111**. Kullanıcıların **1234** veya **1111** gibi parolalar oluşturmalarına izin vermek için **Yapılandırılmadı** olarak ayarlayın.
- **Minimum parola uzunluğu**: En düşük rakam veya karakter bulunması gereken sayısını girin.

  Windows çalıştıran ve bir Microsoft hesabı ile erişilen cihazlarda uyumluluk ilkesi, şu durumlarda doğru değerlendirme yapamaz:
  - En düşük parola uzunluğu sekiz karakterden fazlaysa
  - Veya en düşük karakter kümesi sayısı ikiden fazlaysa

- **Parola türü**: Parola yalnızca olması gerekip gerekmediğini seçin **sayısal** karakter veya sayı ve diğer karakterlerin bir karışımı yoksa (**alfasayısal**).
  
  - **Paroladaki alfasayısal olmayan karakter sayısı**: **Gerekli parola türü** **Alfasayısal** olarak ayarlanırsa bu ayar parolanın içermesi gereken en az karakter kümesi sayısını belirtir. Dört karakter kümesi şunlardır:
    - Küçük harfler
    - Büyük harfler
    - Simgeler
    - Sayılar

    Daha yüksek bir sayı ayarlanırsa kullanıcının daha karmaşık bir parola oluşturması gerekir. Bir Microsoft hesabı ile güvenliği sağlanan cihazlar için Uyumluluk İlkesi düzgün değerlendirme yapamaz:

    - En düşük parola uzunluğu sekiz karakterden fazlaysa
    - Veya minimum karakter kümesi sayısı ikiden ise

- **Parola istenmeden önce geçen işlem yapılmayan en fazla dakika**: Kullanıcı parolasını yeniden girmeden önce boşta geçen süreyi girin.
- **Parola süresinin sonu (gün)**: Parolanın süresi dolup yeni bir tane oluşturmanız gerekir önce geçen gün sayısını seçin.
- **Yeniden kullanılması önlenecek önceki parola sayısı**: Kullanılamaz önceden kullanılmış parola sayısını girin.

#### <a name="encryption"></a>Şifreleme

- **Mobil cihazda şifreleme gerektir**: **Gerekli** veri deposu kaynaklarına bağlanmak için şifrelenmesini cihaz.

## <a name="windows-10-and-later-policy-settings"></a>Windows 10 ve sonraki ilke ayarları

### <a name="device-health"></a>Device health

- **BitLocker gerektir**: Cihaz, BitLocker açık olduğunda, sistemin kapalı olduğu veya hazırda yetkisiz erişimden sürücüde depolanan verileri koruyabilirsiniz. Windows BitLocker Sürücü Şifrelemesi, Windows işletim sistemi birimine depolanan tüm verileri şifreler. BitLocker, Windows işletim sistemini ve kullanıcı verilerini korumaya yardımcı olmak için TPM'yi kullanır. Ayrıca, bir bilgisayar değiştirilmiş değil onaylamak yardımcı olsa bile kaybolur veya çalınırsa, sol katılımsız. Bilgisayarda uyumlu bir TPM varsa, BitLocker verileri koruyan şifreleme anahtarlarını kilitlemek için TPM kullanır. Bunun sonucunda, TPM bilgisayarın durumunu onaylayıncaya kadar anahtarlara erişilemez.
- **Güvenli önyüklemenin cihazda etkinleştirilmesini gerektir**: Güvenli Önyükleme etkinleştirildiğinde sistem güvenilen fabrika durumuna önyüklenmeye zorlanır. Ayrıca, Güvenli Önyükleme etkinleştirildiğinde makineyi önyüklemek için kullanılan çekirdek bileşenleri cihazı üreten kuruluş tarafından güvenilen doğru şifreleme imzalarına sahip olmalıdır. UEFI üretici yazılımı, makinenin başlatılmasına izin vermeden önce imzayı doğrular. Herhangi bir dosya, hangi imzalarına keser uyumlu, sistemin önyükleme yapılamıyor.

  > [!NOTE]
  > **Güvenli Önyükleme cihazda etkin olmasını gerektiren** ayarı bazı TPM 1.2 ve 2.0 mobil cihazlarda desteklenir. TPM 2.0 ve sonrasını desteklemeyen cihazlarda ilke durumu Intune'da **Uyumsuz** olarak gösterilir. Desteklenen sürümler hakkında daha fazla bilgi için bkz. [cihaz durumu kanıtlama](https://docs.microsoft.com/windows/security/information-protection/tpm/trusted-platform-module-overview#device-health-attestation).

- **Kod bütünlüğü gerektir**: Kod bütünlüğü bir sürücünün veya sistem dosyasının her belleğe yüklendiğinde bütünlüğünü doğrulayan bir özelliktir. Kod bütünlüğü çekirdeğe imzasız bir sürücünün veya sistem dosyasının yüklenip yüklenmediğini algılar. Ayrıca, bir sistem dosyasının yönetici ayrıcalıklarına sahip bir kullanıcı hesabı tarafından çalıştırmak kötü amaçlı yazılım tarafından değiştirilip değiştirilmediğini algılar.

HAS hizmetinin nasıl çalıştığı hakkında daha fazla bilgi için bkz. [Sistem Durumu Kanıtlama CSP’si](https://docs.microsoft.com/windows/client-management/mdm/healthattestation-csp).

### <a name="device-properties"></a>Cihaz özellikleri

- **En düşük işletim sistemi sürümü**: Sürümünde izin verilen en düşük girin **major.minor.build.CU numarasını** biçimi. Doğru değeri almak için, komut istemini açın ve `ver` yazın. `ver` komutu, sürümü şu biçimde döndürür:

  `Microsoft Windows [Version 10.0.17134.1]`

  Olduğunda bir cihaza girdiğiniz işletim sistemi sürümünü daha eski bir sürüm varsa, bunu uyumlu değil olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Son kullanıcı, cihazını yükseltmeyi seçebilir. Bunlar yükselttikten sonra kullanıcılar şirket kaynaklarına erişim sağlayabilir.

- **En yüksek işletim sistemi sürümü**: Sürüm, izin verilen en yüksek girin **major.minor.build.revision numarası** biçimi. Doğru değeri almak için, komut istemini açın ve `ver` yazın. `ver` komutu, sürümü şu biçimde döndürür:

  `Microsoft Windows [Version 10.0.17134.1]`

  Bir cihaz girdiğiniz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullanarak, şirket kaynaklarına erişimi engellenir ve kullanıcıya, kullanıcıdan BT yöneticisine başvurması istenir. İşletim sistemine izin veren kuralın değiştirilinceye kadar cihaz şirket kaynaklarına erişemez.

- **Mobil cihazlar için gereken en düşük işletim sistemi**: En düşük sürümü major.minor.build biçiminde izin girin.

  Bir cihaz, daha önceki bir sürümü olduğunda işletim sistemi sürümü girdiğiniz, bunu uyumlu değil olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı gösterilir. Son kullanıcı, cihazını yükseltmeyi seçebilir. Bunlar yükselttikten sonra kullanıcılar şirket kaynaklarına erişim sağlayabilir.

- **Mobil cihazlar için gereken en yüksek işletim sistemi**: Sürümü Major.Minor.Build biçiminde izin verilen üst sınırı girin.

  Bir cihaz bir işletim sistemi sürümünü kullandığında girdiğiniz olandan daha sonra şirket kaynaklarına erişimi engellenir ve kullanıcıya, kullanıcıdan BT yöneticisine başvurması istenir. İşletim sistemine izin veren kuralın değiştirilinceye kadar cihaz şirket kaynaklarına erişemez.

- **Geçerli işletim sistemi derlemeleri**: Bir aralığın minimum ve maksimum da dahil olmak üzere kabul edilebilir işletim sistemi sürümleri için girin. Kabul edilebilir derleme numaraları için bir virgülle ayrılmış değerler (CSV) dosya listesi **Dışarı Aktarabilirsiniz**.

### <a name="configuration-manager-compliance"></a>Configuration Manager uyumluluk

Windows 10 ve üzeri çalıştıran yalnızca ortak yönetilen cihazlar için geçerlidir. Yalnızca Intune cihazları kullanılabilir değil durumuna döndürün.

- **System Center Configuration Manager cihaz uyumluluğu gerektir**: Seçin **gerektiren** uyumlu olması için System Center Configuration Manager, tüm ayarlarını (yapılandırma öğelerini) zorlamak için. 

  Örneğin, tüm yazılım güncelleştirmelerinin cihazlarda yüklü olmasını gerektirirsiniz. Configuration Manager’da bu gereksinim, “Yüklü” durumundadır. Cihazdaki tüm programları bilinmeyen bir durumda, cihazı Intune'da uyumlu olmadığını.
  
  Zaman **yapılandırılmadı**, Intune değil herhangi bir Configuration Manager uyumluluk ayarlarını denetleyin.

### <a name="system-security-settings"></a>Sistem güvenliği ayarları

#### <a name="password"></a>istemcisiyle yönetilen bir cihaz için)

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

#### <a name="encryption"></a>Şifreleme

- **Bir cihazdaki veri depolamasının şifrelenmesi**: Seçin **gerektiren** cihazlarınızda veri deposunu şifrelemek için.

  > [!NOTE]
  > **Bir cihazdaki veri depolama şifrelemesi** ayarı cihazdaki genel şifreleme varlığını denetler. Daha güçlü bir şifreleme ayarı için **BitLocker’ı gerektir** ayarını kullanmayı göz önünde bulundurabilirsiniz. Bu ayar, TPM düzeyinde BitLocker durumunu doğrulamak için Windows Cihaz Sistem Durumu Kanıtlama özelliğinden yararlanır.

#### <a name="device-security"></a>Cihaz Güvenliği

- **Virüsten koruma**: Ayarlandığında **gerektiren**, kayıtlı virüsten koruma çözümleri kullanarak uyumluluk denetleyebilirsiniz [Windows Güvenlik Merkezi](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/)Symantec ve Windows Defender gibi. **Yapılandırılmadı** olarak bırakıldığında, Intune cihazda herhangi bir AV çözümünün yüklü olup olmadığını denetlemez.
- **Casus yazılımdan koruma**: Ayarlandığında **gerektiren**, kayıtlı bir casus yazılımdan koruma çözümlerini kullanarak uyumluluk denetleyebilirsiniz [Windows Güvenlik Merkezi](https://blogs.windows.com/windowsexperience/2017/01/23/introducing-windows-defender-security-center/)Symantec ve Windows Defender gibi. **Yapılandırılmadı** olarak bırakıldığında, Intune cihazda herhangi bir casus yazılımdan koruma çözümünün yüklü olup olmadığını denetlemez.

### <a name="windows-defender-atp"></a>Windows Defender ATP

- **Cihaz veya makine risk puanı altında olmasını gerektir**: Savunması alınan risk değerlendirmesini uyumluluk koşulu olarak tehdit Hizmetleri almak için bu ayarı kullanın. İzin verilen en yüksek tehdit düzeyini seçin:
  - **NET**: Bu seçenek en çok, güvenli, cihazda hiçbir tehdit olmaması gibi. Sahip olan herhangi bir tehdit düzeyi algılanırsa cihaz, uyumsuz olarak değerlendirilir.
  - **Düşük**: Cihaz, yalnızca düşük düzeydeki tehditler varsa uyumlu olarak değerlendirilir. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
  - **Orta**: Cihaz cihazda mevcut tehditler düşük veya Orta düzeydeyse uyumlu olarak değerlendirilir. Yüksek düzeyde tehditler algılanırsa cihaz uyumsuz olarak değerlendirilir.
  - **Yüksek**: Bu seçenek en az güvenli seçenektir ve tüm tehdit düzeylerine izin verir. Bu çözüm, yalnızca raporlama amacıyla kullanıyorsanız kullanışlı olabilir.
  
  Windows Defender ATP’yi (Gelişmiş Tehdit Koruması) tehdit savunma hizmetiniz olarak ayarlamak için bkz. [Koşullu erişimle Windows Defender ATP’yi etkinleştirme](advanced-threat-protection.md).

## <a name="windows-holographic-for-business"></a>Windows 10 Holographic for Business

Windows Holographic for Business, **Windows 10 ve sonrası** platformları kullanır. Windows Holographic for Business, aşağıdaki ayarı destekler:

- **Sistem Güvenliği** > **Şifreleme** > **Cihazda veri deposu şifrelemesi**.

Microsoft HoloLens’te cihaz şifrelemesini doğrulamak için bkz. [Cihaz şifrelemesini doğrulama](https://docs.microsoft.com/hololens/hololens-encryption#verify-device-encryption).

## <a name="surface-hub"></a>Surface Hub
Surface Hub, **Windows 10 ve sonrası** platformları kullanır. Surface Hub’larda uyumluluk ve koşullu erişim desteklenir. Bu özellikleri Surface hub'larda etkinleştirmek için öneririz [Windows 10 otomatik kaydı etkinleştirme](windows-enroll.md) ıntune'da (Ayrıca gerektiren Azure Active Directory (Azure AD)) ve Surface Hub cihazlarını cihaz gruplarıyla hedefleyebilirsiniz. Surface hub'ların çalışması için Azure AD'ye katılmış uyumluluk ve koşullu erişim için gereklidir.

Rehber için bkz. [Windows cihazları için kaydı ayarlama](windows-enroll.md).

## <a name="assign-user-or-device-groups"></a>Kullanıcı veya cihaz grupları atama

1. Yapılandırdığınız bir ilkeyi seçin. Mevcut ilkeler **Cihaz uyumluluğu** > **İlkeler**’de bulunur.
2. İlkeyi, sonra da **Atamalar**’ı seçin. AD güvenlik gruplarını dahil edebilir veya hariç tutabilirsiniz.
3. Azure AD güvenlik gruplarınızı görmek için **Seçili gruplar**’ı seçin. Bu ilkeyi uygulamak istediğiniz kullanıcı gruplarını seçin ve daha sonra ilkeyi dağıtmak için **Kaydet**’i seçin.

İlkeyi uyguladınız. İlkenin hedeflediği kullanıcılar tarafından kullanılan cihazlar, uyumluluk için değerlendirilir.

## <a name="next-steps"></a>Sonraki adımlar
[Uyumsuz cihazlar için e-postayı otomatikleştirme ve eylemleri ekleme](actions-for-noncompliance.md)  
[Intune Cihaz uyumluluk ilkelerini izleme](compliance-policy-monitor.md)
