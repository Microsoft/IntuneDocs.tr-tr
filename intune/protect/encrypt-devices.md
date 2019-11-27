---
title: Platformlar desteklenen şifreleme yöntemiyle cihazları şifreleyin
titleSuffix: Microsoft Intune
description: BitLocker veya Filekasası gibi yerleşik şifreleme yöntemleriyle cihazları şifreleyin ve bu şifrelenmiş cihazların kurtarma anahtarlarını Intune portalından yönetin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/21/2019
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
ms.openlocfilehash: 13d6a2b9cdc8596c7f5cf81218377754e9412be1
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74390318"
---
# <a name="use-device-encryption-with-intune"></a>Intune ile cihaz şifrelemesini kullanma

Cihazlarda verileri korumak üzere yerleşik bir diski veya sürücü şifrelemeyi yönetmek için Intune 'U kullanın.

Uç nokta koruma için cihaz yapılandırma profilinin bir parçası olarak disk şifrelemeyi yapılandırın. Intune tarafından aşağıdaki platformlar ve şifreleme teknolojileri desteklenir:

- macOS: Filekasası
- Windows 10 ve üzeri: BitLocker

Intune Ayrıca, tüm yönetilen cihazlarınızda cihazların şifreleme durumu hakkında ayrıntılı bilgiler sunan yerleşik bir [şifreleme raporu](encryption-monitor.md) sağlar.

## <a name="filevault-encryption-for-macos"></a>MacOS için dosya Kasası şifrelemesi

MacOS çalıştıran cihazlarda Filekasadisk şifrelemesini yapılandırmak için Intune 'U kullanın. Daha sonra, bu cihazların şifreleme ayrıntılarını görüntülemek ve Filekasasına şifrelenmiş cihazların kurtarma anahtarlarını yönetmek için Intune şifreleme raporunu kullanın.

Filekasası, macOS ile birlikte gelen bir tam disk şifreleme programıdır. **MacOS 10,13 veya üstünü**çalıştıran cihazlarda dosya kasasını yapılandırmak Için Intune 'u kullanabilirsiniz.

Filekasasını yapılandırmak için, macOS platformu için Endpoint Protection için bir [cihaz yapılandırma profili](../configuration/device-profile-create.md) oluşturun. Filekasası ayarları, macOS Endpoint Protection için kullanılabilir ayar kategorilerinden biridir.

Cihazları dosya kasası ile şifrelemek için bir ilke oluşturduktan sonra, ilke iki aşamada cihazlara uygulanır. İlk olarak cihaz, Intune 'un kurtarma anahtarını alıp yedeklemesini sağlamak için hazır hale getirilir. Bu, Emanet olarak adlandırılır. Anahtar alındıktan sonra, disk şifrelemesi başlayabilir.

![Dosya Kasası ayarları](./media/encrypt-devices/filevault-settings.png)

Intune ile yönetebileceğiniz Filekasası ayarı hakkında ayrıntılı bilgi için bkz. macOS Endpoint Protection ayarları için Intune makalesindeki [filekasası](endpoint-protection-macos.md#filevault) .

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

   > [!IMPORTANT]
   > **Oturumu kapatma Isteminde devre dışı bırak** ayarı *Etkinleştir*olarak ayarlandığında bilinen bir sorun vardır. *Enable*olarak ayarlandığında, **atlamaya izin verilen sayısı** ayarı bir değere ayarlanmalıdır ve *yapılandırılmamış*olarak ayarlanmamalıdır. *Yapılandırılmadı*olarak ayarlanırsa, profil cihazda başarısız olur. Bu senaryoda cihaz, daha fazla ayrıntı olmadan **profil durumu özetini** **hata** olarak bildirir.
   >
   > **Oturumu kapatma sırasında Istemi devre dışı bırak** ayarı *Yapılandırılmadı*olarak ayarlandığında, **atlamaya izin verilen zaman sayısı** *yapılandırılmaz* veya bir değere sahip olabilir.
   >
   > Bu sorun, gelecekteki bir güncelleştirmede çözümlenir.

8. Ek ayarların yapılandırmasını tamamladıktan sonra profili kaydedin.  

### <a name="manage-filevault"></a>Dosya kasasını yönetme

Intune, bir macOS cihazını Filekasasıyla şifreledikten sonra, Intune [şifreleme raporunu](encryption-monitor.md)görüntülerken filekasasını kurtarma anahtarlarını görüntüleyebilir ve yönetebilirsiniz.

Intune bir macOS cihazını Filekasasıyla şifreledikten sonra, bu cihazın kişisel kurtarma anahtarını herhangi bir cihazdaki Web Şirket Portalı görüntüleyebilirsiniz. Web Şirket Portalı bir kez, şifrelenen macOS cihazını seçin ve ardından "kurtarma anahtarını al" seçeneğini bir uzak cihaz eylemi olarak belirleyin.

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
