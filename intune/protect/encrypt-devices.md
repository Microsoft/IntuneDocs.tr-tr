---
title: Platformlar desteklenen şifreleme yöntemiyle cihazları şifreleyin
titleSuffix: Microsoft Intune
description: BitLocker veya Filekasası gibi yerleşik şifreleme yöntemleriyle cihazları şifreleyin ve bu şifrelenmiş cihazların kurtarma anahtarlarını Intune portalından yönetin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/25/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: annovich
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: a5c844377dcd69b6caf5ef9f72fcb8dbb4ef8bd0
ms.sourcegitcommit: 29f3ba071c9348686d3ad6f3b8864d8557e05b97
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77609306"
---
# <a name="use-device-encryption-with-intune"></a>Intune ile cihaz şifrelemesini kullanma

Cihazlarda verileri korumak üzere yerleşik bir diski veya sürücü şifrelemeyi yönetmek için Intune 'U kullanın.

Uç nokta koruma için cihaz yapılandırma profilinin bir parçası olarak disk şifrelemeyi yapılandırın. Intune tarafından aşağıdaki platformlar ve şifreleme teknolojileri desteklenir:

- macOS: Filekasası
- Windows 10 ve üzeri: BitLocker

Intune Ayrıca, tüm yönetilen cihazlarınızda cihazların şifreleme durumu hakkında ayrıntılı bilgiler sunan yerleşik bir [şifreleme raporu](encryption-monitor.md) sağlar.

## <a name="filevault-encryption-for-macos"></a>MacOS için dosya Kasası şifrelemesi

MacOS çalıştıran cihazlarda Filekasadisk şifrelemesini yapılandırmak için Intune 'U kullanın. Daha sonra, bu cihazların şifreleme ayrıntılarını görüntülemek ve Filekasasına şifrelenmiş cihazların kurtarma anahtarlarını yönetmek için Intune şifreleme raporunu kullanın.

Dosya kasasının cihazda çalışması için Kullanıcı tarafından onaylanan cihaz kaydı gereklidir. Kullanıcının kaydın Kullanıcı tarafından onaylanabilmesi için sistem tercihlerinden yönetim profilini el ile onaylaması gerekir.

Filekasası, macOS ile birlikte gelen bir tam disk şifreleme programıdır. **MacOS 10,13 veya üstünü**çalıştıran cihazlarda dosya kasasını yapılandırmak Için Intune 'u kullanabilirsiniz.

Filekasasını yapılandırmak için, macOS platformu için Endpoint Protection için bir [cihaz yapılandırma profili](../configuration/device-profile-create.md) oluşturun. Filekasası ayarları, macOS Endpoint Protection için kullanılabilir ayar kategorilerinden biridir.

Cihazları dosya kasası ile şifrelemek için bir ilke oluşturduktan sonra, ilke iki aşamada cihazlara uygulanır. İlk olarak cihaz, Intune 'un kurtarma anahtarını alıp yedeklemesini sağlamak için hazır hale getirilir. Bu eyleme Emanet denir. Anahtar alındıktan sonra, disk şifrelemesi başlayabilir.

![Dosya Kasası ayarları](./media/encrypt-devices/filevault-settings.png)

Intune ile yönetebileceğiniz Filekasası ayarı hakkında ayrıntılı bilgi için bkz. macOS Endpoint Protection ayarları için Intune makalesindeki [filekasası](endpoint-protection-macos.md#filevault) .

### <a name="permissions-to-manage-filevault"></a>Dosya kasasını yönetme izinleri

Intune 'da Filekasasını yönetmek için hesabınızın ilgili Intune [rol tabanlı erişim denetimi](../fundamentals/role-based-access-control.md) (RBAC) izinlerine sahip olması gerekir.

Aşağıda, **uzak görevler** kategorisinin bir parçası olan ve izin veren yerleşik RBAC rollerinin yer aldığı dosya Kasası izinleri verilmiştir:
 
- **Dosya Kasası anahtarını al**:
  - Yardım Masası Işleci
  - Uç nokta güvenlik yöneticisi

- **Filekasa anahtarını döndür**
  - Yardım Masası Işleci

### <a name="how-to-configure-macos-filevault"></a>MacOS Filekasasını yapılandırma

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2. **Profil oluşturma** > **yapılandırma profilleri** > **cihazları** seçin.

3. Aşağıdaki seçenekleri ayarlayın:

   - Platform: macOS
   - Profil türü: Endpoint Protection

4. **Dosya kasası** > **ayarları** ' nı seçin.

5. *Filekasası*için **Etkinleştir**' i seçin.

6. *Kurtarma anahtarı türü*Için yalnızca **kişisel anahtar** desteklenir.

   Son kullanıcılara cihazlarıyla ilgili kurtarma anahtarını alma hakkında yardım almak için bir ileti eklemeyi düşünün. Bu bilgiler, kişisel kurtarma anahtarı döndürme ayarını kullandığınızda son kullanıcılarınız için yararlı olabilir. Bu, düzenli aralıklarla bir cihaz için otomatik olarak yeni bir kurtarma anahtarı üretebilirler.

   Örneğin: kayıp veya son döndürülen kurtarma anahtarını almak Için herhangi bir cihazdan Intune Şirket Portalı Web sitesinde oturum açın. Portalda *cihazlar* ' a gidin ve filekasasının etkinleştirildiği cihazı seçin ve ardından *Kurtarma anahtarını al*' ı seçin. Geçerli kurtarma anahtarı görüntülenir.

7. Kalan [Filekasası ayarlarını](endpoint-protection-macos.md#filevault) iş gereksinimlerinizi karşılayacak şekilde yapılandırın ve ardından **Tamam**' ı seçin.

  8. Ek ayarların yapılandırmasını tamamladıktan sonra profili kaydedin.  

### <a name="manage-filevault"></a>Dosya kasasını yönetme

Intune, bir macOS cihazını Filekasasıyla şifreledikten sonra, Intune [şifreleme raporunu](encryption-monitor.md)görüntülerken filekasasını kurtarma anahtarlarını görüntüleyebilir ve yönetebilirsiniz.

Intune bir macOS cihazını Filekasasıyla şifreledikten sonra, bu cihazın kişisel kurtarma anahtarını herhangi bir cihazdaki Web Şirket Portalı görüntüleyebilirsiniz. Web Şirket Portalı bir kez, şifrelenen macOS cihazını seçin ve ardından "kurtarma anahtarını al" seçeneğini bir uzak cihaz eylemi olarak belirleyin.

### <a name="retrieve-personal-recovery-key-from-mem-encrypted-macos-devices"></a>MEM şifreli macOS cihazlarından kişisel kurtarma anahtarını alma

Son kullanıcılar iOS Şirket Portalı uygulamasını kullanarak kişisel kurtarma anahtarını (Filekasası anahtarı) alır. Kişisel kurtarma anahtarına sahip olan cihaz Intune 'a kaydolmalıdır ve Intune aracılığıyla Filekasasıyla şifrelenir. İOS Şirket Portalı uygulamasını kullanarak Son Kullanıcı, Filekasakişisel kurtarma anahtarını içeren bir Web sayfası açabilir. Kurtarma anahtarını, *şifreli ve kayıtlı macOS cihazı* ** >  > ** **Kurtarma anahtarı al**' a seçerek de Intune 'dan alabilirsiniz. 

## <a name="bitlocker-encryption-for-windows-10"></a>Windows 10 için BitLocker şifrelemesi

Windows 10 çalıştıran cihazlarda BitLocker Sürücü Şifrelemesi yapılandırmak için Intune 'u kullanın. Ardından, bu cihazların şifreleme ayrıntılarını görüntülemek için Intune şifreleme raporunu kullanın. Ayrıca, Azure Active Directory (Azure AD) içinde bulunan ve cihazlarınızdan BitLocker için önemli bilgilere erişebilirsiniz.

BitLocker, **Windows 10 veya üzerini**çalıştıran cihazlarda kullanılabilir.

Windows 10 veya sonraki bir platformda Endpoint Protection için bir [cihaz yapılandırma profili](../configuration/device-profile-create.md) oluşturduğunuzda BitLocker 'ı yapılandırın. BitLocker ayarları, Windows 10 Endpoint Protection için Windows şifreleme ayarları kategorisinde bulunur.

![BitLocker ayarları](./media/encrypt-devices/bitlocker-settings.png)

### <a name="how-to-configure-windows-10-bitlocker"></a>Windows 10 BitLocker 'ı yapılandırma

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2. **Profil oluşturma** > **yapılandırma profilleri** > **cihazları** seçin.

3. Aşağıdaki seçenekleri ayarlayın:

   - Platform: Windows 10 ve üzeri
   - Profil türü: Endpoint Protection

4. **Windows şifrelemesi** > **Ayarlar** ' ı seçin.

5. BitLocker ayarlarını iş gereksinimlerinizi karşılayacak şekilde yapılandırın ve ardından **Tamam**' ı seçin.

6. Ek ayarların yapılandırmasını tamamladıktan sonra profili kaydedin.

### <a name="manage-bitlocker"></a>BitLocker 'ı yönetme

Intune bir Windows 10 cihazını BitLocker ile şifreledikten sonra, Intune [şifreleme raporunu](encryption-monitor.md)görüntülerken BitLocker kurtarma anahtarlarını görüntüleyebilir ve alabilirsiniz.

### <a name="rotate-bitlocker-recovery-keys"></a>BitLocker kurtarma anahtarlarını döndür

Windows 10 sürüm 1909 veya üstünü çalıştıran bir cihazın BitLocker kurtarma anahtarını uzaktan döndürmek için bir Intune cihaz eylemini kullanabilirsiniz.

#### <a name="prerequisites"></a>Önkoşullar

Cihazların BitLocker kurtarma anahtarının döndürmesini desteklemek için aşağıdaki önkoşulları karşılaması gerekir:

- Cihazların Windows 10 sürüm 1909 veya üstünü çalıştırması gerekir

- Azure AD 'ye katılmış ve Hibriya katılmış cihazlarda anahtar döndürme özelliğinin etkinleştirilmesi için destek bulunmalıdır:

  - **İstemci tabanlı kurtarma parolası döndürme**

  Bu ayar, Windows 10 Endpoint Protection cihaz yapılandırma ilkesinin bir parçası olarak *Windows şifrelemesi* altında bulunur.
  
#### <a name="to-rotate-the-bitlocker-recovery-key"></a>BitLocker kurtarma anahtarını döndürmek için

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2. **Cihazlar** > **Tüm cihazlar**’ı seçin.

3. Yönettiğiniz cihazların listesinde bir cihaz seçin, **daha fazla**' yı seçin ve ardından **BitLocker anahtar döndürme** cihazı uzak eylemi ' ni seçin.

## <a name="next-steps"></a>Sonraki adımlar

[Bir cihaz uyumluluk](compliance-policy-create-windows.md) ilkesi oluşturun.

Yönetmek için şifreleme raporunu kullanın:

- [BitLocker kurtarma anahtarları](encryption-monitor.md#bitlocker-recovery-keys)
- [Filekasası kurtarma anahtarları](encryption-monitor.md#filevault-recovery-keys)

Intune ile yapılandırabileceğiniz şifreleme ayarlarını inceleyerek şunları yapabilirsiniz:

- [Kurulumu](endpoint-protection-windows-10.md#windows-encryption)
- [FileVault](endpoint-protection-macos.md#filevault)
