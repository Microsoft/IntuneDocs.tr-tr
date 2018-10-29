---
title: Microsoft Intune - Azure'da Windows cihaz uyumluluk ilkesi oluşturma | Microsoft Docs
description: Windows Phone 8.1, Windows 8.1 ve sonrası, Windows 10 ve sonrası cihazlar için bir Microsoft Intune cihaz uyumluluk ilkesi oluşturun veya yapılandırın. Surface Hub ve Windows Holographic for Business da dahil olmak üzere cihazlarda en düşük ve en yüksek işletim sistemi uyumluluğunu denetleyin, parola kısıtlamaları ve uzunluğunu ayarlayın, BitLocker’ı gerekli kılın, üçüncü (3.) taraf virüsten koruma çözümlerini denetleyin, kabul edilebilir tehdit düzeyini ayarlayın ve veri deposunda şifrelemeyi etkinleştirin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e38e6f615220135e9c4c9c786ab260f5921890ea
ms.sourcegitcommit: 24d9ae0396ca410f72cc061a3c4c402835ef32a1
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2018
ms.locfileid: "49642921"
---
# <a name="add-a-device-compliance-policy-for-windows-devices-in-intune"></a>Intune’da Windows cihazları için cihaz uyumluluk ilkesi ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Windows için Intune cihaz uyumluluk ilkesi, Windows cihazlarının uyumlu olarak değerlendirilmesi için uyması gereken kuralları ve ayarları tanımlar. Şirket kaynaklarına erişime izin vermek veya bunu engellemek için bu ilkeleri koşullu erişimle birlikte kullanabilirsiniz. Ayrıca cihaz raporları alabilir ve uyumsuzluk için eylemler uygulayabilirsiniz. Her platform için cihaz uyumluluk ilkeleri Intune Azure portalında oluşturulabilir. Uyumluluk ilkeleri ve olası önkoşullar hakkında daha fazla bilgi için bkz. [Cihaz uyumluluğunu kullanmaya başlama](device-compliance-get-started.md).

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

- **Gerekli en düşük işletim sistemi:** Cihaz, en düşük işletim sistemi sürümü gereksinimini karşılamadığında uyumsuz olarak bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı görüntülenir. Son kullanıcı, cihazını yükseltmeyi seçip şirket kaynaklarına erişebilir.
- **İzin verilen en yüksek işletim sistemi sürümü**: Cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullandığında, şirket kaynaklarına erişim engellenir. Kullanıcıdan BT yöneticisine başvurması istenir. İşletim sistemine izin veren bir kural değişikliği oluncaya kadar bu cihaz şirket kaynaklarına erişemez.

Windows 8.1 bilgisayarları **3** sürümünü döndürür. Windows için işletim sistemi sürüm kuralı Windows 8.1’e ayarlanırsa, cihaz Windows 8.1’e sahip olsa bile uyumsuz olarak bildirilir.

### <a name="system-security"></a>Sistem güvenliği

#### <a name="password"></a>Parola

- **Mobil cihazların kilidini açmak için parola gerektir**: Kullanıcıların cihazlarına erişebilmek için bir parola girmelerini **gerektir**in.
- **Basit parolalar**: Bunu **Engelle** şeklinde ayarlayarak, kullanıcıların **1234** veya **1111** gibi basit parolalar oluşturmalarının önüne geçin. Kullanıcıların **1234** veya **1111** gibi parolalar oluşturmalarına izin vermek için **Yapılandırılmadı** olarak ayarlayın.
- **Minimum parola uzunluğu**: Parolada bulunması gereken rakam veya karakter sayısı alt sınırını girin.

  Windows çalıştıran ve bir Microsoft hesabı ile erişilen cihazlarda uyumluluk ilkesi, şu durumlarda doğru değerlendirme yapamaz:
  - En düşük parola uzunluğu sekiz karakterden fazlaysa
  - Veya en düşük karakter kümesi sayısı ikiden fazlaysa

- **Parola türü**: Parolanın yalnızca **Sayısal** karakterlerden mi yoksa sayı ve diğer karakterlerin karışımından (**Alfasayısal**) mı oluşması gerektiğini seçin.
  
  - **Paroladaki alfasayısal olmayan karakter sayısı:** **Gerekli parola türü** **Alfasayısal** olarak ayarlandıysa, bu ayar parolanın içermesi gereken karakter kümesi sayısı alt sınırını belirtir. Dört karakter kümesi şunlardır:
    - Küçük harfler
    - Büyük harfler
    - Simgeler
    - Sayılar

    Daha yüksek bir sayı ayarlanırsa kullanıcının daha karmaşık bir parola oluşturması gerekir. Windows çalıştıran ve bir Microsoft Hesabı ile erişilen cihazlarda, minimum parola uzunluğu sekiz karakterden fazlaysa veya minimum karakter kümesi sayısı ikiden büyükse, uyumluluk ilkesi düzgün değerlendirme yapamaz.

- **Parola istenmeden önce geçmesi gereken işlem yapılmayan dakika sayısı**: Kullanıcıdan, parolasını yeniden girmesi istenmeden önce boşta geçen süreyi girin.
- **Parola kullanım süresi (gün)**: Parolanın süresi dolup yeni bir parola oluşturulması gerekmeden önce geçmesi gereken gün sayısını seçin.
- **Yeniden kullanılması engellenen eski parola sayısı**: Önceki parolalardan kaç tanesinin kullanılamayacağını girin.

#### <a name="encryption"></a>Şifreleme

- **Mobil cihazda şifreleme gerektir:** Cihazın veri deposu kaynaklarına bağlanmak için şifrelenmesini **gerektir**in.

## <a name="windows-10-and-later-policy-settings"></a>Windows 10 ve sonraki ilke ayarları

### <a name="device-health"></a>Device health

- **BitLocker gerektir**: BitLocker açık olduğunda, sistemin kapalı olduğu veya hazırda beklemeye girdiği durumlarda cihaz sürücüye depolanmış verileri yetkisiz erişimden koruyabilir. Windows BitLocker Sürücü Şifrelemesi, Windows işletim sistemi birimine depolanan tüm verileri şifreler. BitLocker, Windows işletim sistemini ve kullanıcı verilerini korumaya yardımcı olmak için TPM'yi kullanır. Ayrıca boşta bırakılan, kaybolan veya çalınan bilgisayarlara müdahale edilmemesine yardımcı olur. Bilgisayarda uyumlu bir TPM varsa, BitLocker verileri koruyan şifreleme anahtarlarını kilitlemek için TPM kullanır. Sonuç olarak, TPM bilgisayarın durumunu doğrulayana kadar anahtarlara erişilemez.
- **Cihazda Güvenli Önyüklemenin etkin olmasını gerektir:** Güvenli Önyükleme etkinleştirildiğinde sistem güvenilen fabrika durumuna önyüklenmeye zorlanır. Ayrıca, Güvenli Önyükleme etkinleştirildiğinde makineyi önyüklemek için kullanılan çekirdek bileşenleri cihazı üreten kuruluş tarafından güvenilen doğru şifreleme imzalarına sahip olmalıdır. UEFI üretici yazılımı, makinenin başlatılmasına izin vermeden önce imzayı doğrular. Herhangi dosya ile imzalarını bozacak şekilde oynanmışsa sistem önyüklemesi gerçekleşmez.

  > [!NOTE]
  > **Güvenli Önyükleme cihazda etkinleştirilmeli** ayarı TPM 1.2 ve 2.0 cihazlarda desteklenir. TPM 2.0 ve sonrasını desteklemeyen cihazlarda ilke durumu Intune'da **Uyumsuz** olarak gösterilir. Bu, Windows 10'daki [Cihaz Durumu Kanıtlama](https://docs.microsoft.com/windows/security/information-protection/tpm/trusted-platform-module-overview#device-health-attestation) hizmetinin bir kısıtlamasıdır.

- **Kod bütünlüğü gerektir:** Kod bütünlüğü bir sürücünün veya sistem dosyasının belleğe yüklendiği her durumda bütünlüğünü doğrulayan bir özelliktir. Kod bütünlüğü, imzalanmamış bir sürücünün veya sistem dosyasının çekirdeğe yüklenip yüklenmediğini tespit eder. Veya yönetici ayrıcalıklarına sahip bir kullanıcı hesabı tarafından çalıştırılan sistem dosyalarının kötü amaçlı yazılım tarafından değiştirilip değiştirilmediğini belirler.

HAS hizmetinin nasıl çalıştığı hakkında daha fazla bilgi için bkz. [Sistem Durumu Kanıtlama CSP’si](https://docs.microsoft.com/windows/client-management/mdm/healthattestation-csp).

### <a name="device-properties"></a>Cihaz özellikleri

- **En düşük işletim sistemi sürümü**: İzin verilen en düşük sürümü **major.minor.build.CU** biçiminde girin. Doğru değeri almak için, komut istemini açın ve `ver` yazın. `ver` komutu, sürümü şu biçimde döndürür:

  `Microsoft Windows [Version 10.0.17134.1]`

  Cihazdaki işletim sistemi belirtilen sürümden önceki bir sürümdeyse, cihazın uyumsuz olduğu bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı görüntülenir. Son kullanıcı, şirket kaynaklarına erişebilmek için cihazını yükseltmeyi seçebilir.

- **En yüksek işletim sistemi sürümü**: İzin verilen en yüksek sürümü **major.minor.build.revision** biçiminde girin. Doğru değeri almak için, komut istemini açın ve `ver` yazın. `ver` komutu, sürümü şu biçimde döndürür:

  `Microsoft Windows [Version 10.0.17134.1]`

  Bir cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullandığında, şirket kaynaklarına erişimi engellenir ve kullanıcıdan BT yöneticisi ile iletişim kurması istenir. Kuralda işletim sistemine izin veren bir değişiklik oluncaya kadar bu cihaz şirket kaynaklarına erişmek için kullanılamaz.

- **Mobil cihazlar için gereken en düşük işletim sistemi**: İzin verilen en düşük sürümü major.minor.build biçiminde girin.

  Cihazdaki işletim sistemi belirtilen sürümden önceki bir sürümdeyse, cihazın uyumsuz olduğu bildirilir. Yükseltme hakkında bilgi içeren bir bağlantı görüntülenir. Son kullanıcı, şirket kaynaklarına erişebilmek için cihazını yükseltmeyi seçebilir.

- **Mobil cihazlar için gereken en yüksek işletim sistemi**: İzin verilen en yüksek sürümü major.minor.build biçiminde girin.

  Bir cihaz kuralda belirtilenden sonraki bir işletim sistemi sürümünü kullandığında, şirket kaynaklarına erişimi engellenir ve kullanıcıdan BT yöneticisi ile iletişim kurması istenir. Kuralda işletim sistemine izin veren bir değişiklik oluncaya kadar bu cihaz şirket kaynaklarına erişmek için kullanılamaz.

- **Geçerli işletim sistemi derlemeleri**: İşletim sistemi sürümleri için en düşük ve en yüksek değerler dahil olmak üzere kabul edilebilir bir aralık girin. Kabul edilebilir derleme numaraları için bir virgülle ayrılmış değerler (CSV) dosya listesi **Dışarı Aktarabilirsiniz**.

### <a name="system-security-settings"></a>Sistem güvenliği ayarları

#### <a name="password"></a>Parola

- **Mobil cihazların kilidini açmak için parola gerektir**: Kullanıcıların cihazlarına erişebilmek için bir parola girmelerini **gerektir**in.
- **Basit parolalar**: Bunu **Engelle** şeklinde ayarlayarak, kullanıcıların **1234** veya **1111** gibi basit parolalar oluşturmalarının önüne geçin. Kullanıcıların **1234** veya **1111** gibi parolalar oluşturmalarına izin vermek için **Yapılandırılmadı** olarak ayarlayın.
- **Parola türü**: Parolanın yalnızca **Sayısal** karakterlerden mi yoksa sayı ve diğer karakterlerin karışımından (**Alfasayısal**) mı oluşması gerektiğini seçin.

  - **Paroladaki alfasayısal olmayan karakter sayısı:** **Gerekli parola türü** **Alfasayısal** olarak ayarlandıysa, bu ayar parolanın içermesi gereken karakter kümesi sayısı alt sınırını belirtir. Dört karakter kümesi şunlardır:
    - Küçük harfler
    - Büyük harfler
    - Simgeler
    - Sayılar

    Daha yüksek bir sayı ayarlanırsa kullanıcının daha karmaşık bir parola oluşturması gerekir.

- **Minimum parola uzunluğu**: Parolada bulunması gereken rakam veya karakter sayısı alt sınırını girin.
- **Parola istenmeden önce geçmesi gereken işlem yapılmayan dakika sayısı**: Kullanıcıdan, parolasını yeniden girmesi istenmeden önce boşta geçen süreyi girin.
- **Parola kullanım süresi (gün)**: Parolanın süresi dolup yeni bir parola oluşturulması gerekmeden önce geçmesi gereken gün sayısını seçin.
- **Yeniden kullanılması engellenen eski parola sayısı**: Önceki parolalardan kaç tanesinin kullanılamayacağını girin.
- **Cihaz boşta durumundan çıktığında parola gerektir (Mobil ve Holographic)**: Cihaz boşta durumundan her çıktığında kullanıcıları parola girmeye zorlayın.

#### <a name="encryption"></a>Şifreleme

- **Bir cihazda veri deposu şifreleme**: Cihazlarınızda veri deposunu şifrelemek için **Gerektir**’i seçin.

#### <a name="device-security"></a>Cihaz Güvenliği

- **Virüsten koruma**: **Gerektir** olarak ayarlandığında, Windows Güvenlik Merkezi’ne kaydedilmiş Symantec ve Windows Defender gibi virüsten koruma çözümlerini kullanarak uyumluluğu denetleyebilirsiniz. **Yapılandırılmadı** olarak bırakıldığında, Intune cihazda herhangi bir AV çözümünün yüklü olup olmadığını denetlemez.
- **Casus yazılımdan koruma**: **Gerektir** olarak ayarlandığında, Windows Güvenlik Merkezi’ne kaydedilmiş Symantec ve Windows Defender gibi casus yazılımdan koruma çözümlerini kullanarak uyumluluğu denetleyebilirsiniz. **Yapılandırılmadı** olarak bırakıldığında, Intune cihazda herhangi bir casus yazılımdan koruma çözümünün yüklü olup olmadığını denetlemez.

### <a name="windows-defender-atp"></a>Windows Defender ATP

- **Cihazın makine risk puanında veya bunun altında olmasını gerektir**: Tehdit savunması hizmetlerinizden alınan risk değerlendirmesini uyumluluk koşulu olarak kullanmak için bu ayarı etkinleştirin. İzin verilen en yüksek tehdit düzeyini seçin:
  - **Temiz**: Cihazda hiçbir tehdit olmamasını gerektirdiği için bu seçenek en güvenlisidir. Herhangi bir tehdit düzeyi algılanırsa cihaz, uyumsuz olarak değerlendirilir.
  - **Düşük**: Cihaz, yalnızca düşük düzeyde tehditler varsa uyumlu olarak değerlendirilir. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.
  - **Orta**: Cihazda mevcut tehditler düşük veya orta düzeydeyse cihaz uyumlu olarak değerlendirilir. Yüksek düzeyde tehditler algılanırsa cihaz, uyumlu değil olarak değerlendirilir.
  - **Yüksek**: Tüm tehdit düzeylerine izin verdiği için bu seçenek en düşük güvenliğe sahiptir. Bu çözüm, yalnızca raporlama amacıyla kullanıyorsanız kullanışlı olabilir.
  
  Windows Defender ATP’yi (Gelişmiş Tehdit Koruması) tehdit savunma hizmetiniz olarak ayarlamak için bkz. [Koşullu erişimle Windows Defender ATP’yi etkinleştirme](advanced-threat-protection.md).

## <a name="windows-holographic-for-business"></a>Windows 10 Holographic for Business

Windows Holographic for Business, **Windows 10 ve sonrası** platformları kullanır. Windows Holographic for Business, aşağıdaki ayarı destekler:

- **Sistem Güvenliği** > **Şifreleme** > **Cihazda veri deposu şifrelemesi**.

Microsoft HoloLens’te cihaz şifrelemesini doğrulamak için bkz. [Cihaz şifrelemesini doğrulama](https://docs.microsoft.com/hololens/hololens-encryption#verify-device-encryption).

## <a name="surface-hub"></a>Surface Hub
Surface Hub, **Windows 10 ve sonrası** platformları kullanır. Surface Hub’larda uyumluluk ve koşullu erişim desteklenir. Bu özellikleri Surface Hub’larda etkinleştirmek için Intune’da [Windows 10 otomatik kaydını](windows-enroll.md) etkinleştirmenizi (Azure Active Directory (AD) de gerektirir) ve Surface Hub cihazlarını cihaz gruplarıyla hedeflemenizi öneririz. Uyumluluk ve koşullu erişimin işlevsel olması için Surface Hub’ların Azure Active Directory katılımlı olması gerekir.

Rehber için bkz. [Windows cihazları için kaydı ayarlama](windows-enroll.md).

## <a name="assign-user-or-device-groups"></a>Kullanıcı veya cihaz grupları atama

1. Yapılandırdığınız bir ilkeyi seçin. Mevcut ilkeler **Cihaz uyumluluğu** > **İlkeler**’de bulunur.
2. İlkeyi, sonra da **Atamalar**’ı seçin. AD güvenlik gruplarını dahil edebilir veya hariç tutabilirsiniz.
3. Azure AD güvenlik gruplarınızı görmek için **Seçili gruplar**’ı seçin. Bu ilkeyi uygulamak istediğiniz kullanıcı gruplarını seçin ve daha sonra ilkeyi dağıtmak için **Kaydet**’i seçin.

İlkeyi uyguladınız. İlkenin hedeflediği kullanıcılar tarafından kullanılan cihazlar, uyumluluk için denetlenir.

## <a name="next-steps"></a>Sonraki adımlar
[Uyumsuz cihazlar için e-postayı otomatikleştirme ve eylemleri ekleme](actions-for-noncompliance.md)  
[Intune Cihaz uyumluluk ilkelerini izleme](compliance-policy-monitor.md)
