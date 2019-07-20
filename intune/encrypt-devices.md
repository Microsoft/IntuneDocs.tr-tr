---
title: Desteklenen platformlar şifreleme yöntemlerini kullanarak Microsoft Intune cihazları şifreleme
titleSuffix: Microsoft Intune
description: BitLocker veya Filekasası gibi yerleşik şifreleme yöntemleriyle cihazları şifreleyin ve bu şifrelenmiş cihazların kurtarma anahtarlarını Intune portalından yönetin.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: annovich
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 405cf58f882d40d9bff2f5567a6296352843f3a7
ms.sourcegitcommit: 11a31cd39b727f2254e2705b07d18924e103bd2e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/19/2019
ms.locfileid: "68346542"
---
# <a name="use-device-encryption-with-intune"></a>Intune ile cihaz şifrelemesini kullanma  

Cihazlarda verileri korumak üzere yerleşik bir diski veya sürücü şifrelemeyi yönetmek için Intune 'U kullanın.  

Uç nokta koruma için cihaz yapılandırma profilinin bir parçası olarak disk şifrelemeyi yapılandırın. Intune tarafından aşağıdaki platformlar ve şifreleme teknolojileri desteklenir:  
- MacOS Dosya Kasası   
- Windows 10 ve üzeri: BitLocker  

Intune Ayrıca, tüm yönetilen cihazlarınızda cihazların şifreleme durumu hakkında ayrıntılı bilgiler sunan yerleşik bir [şifreleme raporu](encryption-monitor.md) sağlar.  

## <a name="filevault-encryption-for-macos"></a>MacOS için dosya Kasası şifrelemesi  

MacOS çalıştıran cihazlarda Filekasadisk şifrelemesini yapılandırmak için Intune 'U kullanın. Daha sonra, bu cihazların şifreleme ayrıntılarını görüntülemek ve Filekasasına şifrelenmiş cihazların kurtarma anahtarlarını yönetmek için Intune şifreleme raporunu kullanın.  

Filekasası, macOS ile birlikte gelen bir tam disk şifreleme programıdır. **MacOS 10,13 veya üstünü**çalıştıran cihazlarda dosya kasasını yapılandırmak Için Intune 'u kullanabilirsiniz.  

Filekasasını yapılandırmak için, macOS platformu için Endpoint Protection için bir [cihaz yapılandırma profili](device-profile-create.md) oluşturun. Filekasası ayarları, macOS Endpoint Protection için kullanılabilir ayar kategorilerinden biridir.  

Cihazları dosya kasası ile şifrelemek için bir ilke oluşturduktan sonra, ilke iki aşamada cihazlara uygulanır. İlk olarak cihaz, Intune 'un kurtarma anahtarını alıp yedeklemesini sağlamak için hazır hale getirilir. Bu, Emanet olarak adlandırılır. Anahtar alındıktan sonra, disk şifrelemesi başlayabilir.

![Dosya Kasası ayarları](./media/encrypt-devices/filevault-settings.png)

Intune ile yönetebileceğiniz Filekasası ayarı hakkında ayrıntılı bilgi için bkz. macOS Endpoint Protection ayarları için Intune makalesindeki [filekasası](endpoint-protection-macos.md#filevault) .  

### <a name="how-to-configure-macos-filevault"></a>MacOS Filekasasını yapılandırma 

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açın ve **cihaz yapılandırma** > **profilleri** > **Profil oluştur**' a gidin.  

2. Aşağıdaki seçenekleri ayarlayın:  

   - Platform: macOS  
   - Profil türü: Endpoint protection  

3. **Ayarlar** > **Dosya Kasası**' nı seçin.

4. *Filekasası*için **Etkinleştir**' i seçin.  

5. *Kurtarma anahtarı türü*Için yalnızca **kişisel anahtar** desteklenir.  

   Son kullanıcılara cihazlarıyla ilgili kurtarma anahtarını alma hakkında yardım almak için bir ileti eklemeyi düşünün. Bu bilgiler, kişisel kurtarma anahtarı döndürme ayarını kullandığınızda son kullanıcılarınız için yararlı olabilir. Bu, düzenli aralıklarla bir cihaz için otomatik olarak yeni bir kurtarma anahtarı üretebilirler.  
   
   Örneğin:  Kayıp veya son döndürülen kurtarma anahtarını almak için herhangi bir cihazdan Intune Şirket Portalı Web sitesinde oturum açın. Portalda *cihazlar* ' a gidin ve filekasasının etkinleştirildiği cihazı seçin ve ardından *Kurtarma anahtarını al*' ı seçin. Geçerli kurtarma anahtarı görüntülenir.  

6. Kalan ayarları, iş gereksinimlerinizi karşılayacak şekilde yapılandırın ve ardından **Tamam**' ı seçin.  
   
   > [!NOTE]
   > Dosya Kasası desteği, Temmuz yayını birkaç gün içinde piyasaya sürülene kadar sınırlandırılır. Dağıtım tamamlanana kadar, Filekasasını yapılandırırsanız, **etkinleştirmek**üzere *oturum açana kadar dosya kasasını ertele* seçeneğini ayarlamanız gerekir.   

7. Ek ayarların yapılandırmasını tamamladıktan sonra profili kaydedin.  

###  <a name="manage-filevault"></a>Dosya kasasını yönetme  

Intune, bir macOS cihazını Filekasasıyla şifreledikten sonra, Intune [şifreleme raporunu](encryption-monitor.md)görüntülerken filekasasını kurtarma anahtarlarını görüntüleyebilir ve yönetebilirsiniz.  

## <a name="bitlocker-encryption-for-windows-10"></a>Windows 10 için BitLocker şifrelemesi  

Windows 10 çalıştıran cihazlarda BitLocker Sürücü Şifrelemesi yapılandırmak için Intune 'u kullanın. Ardından, bu cihazların şifreleme ayrıntılarını görüntülemek için Intune şifreleme raporunu kullanın. Ayrıca, Azure Active Directory (Azure AD) içinde bulunan ve cihazlarınızdan BitLocker için önemli bilgilere erişebilirsiniz.  

BitLocker, **Windows 10 veya üzerini**çalıştıran cihazlarda kullanılabilir.  

Windows 10 veya sonraki bir platformda Endpoint Protection için bir [cihaz yapılandırma profili](device-profile-create.md) oluşturduğunuzda BitLocker 'ı yapılandırın. BitLocker ayarları, Windows 10 Endpoint Protection için Windows şifreleme ayarları kategorisinde bulunur.    

![BitLocker ayarları](./media/encrypt-devices/bitlocker-settings.png) 

### <a name="how-to-configure-windows-10-bitlocker"></a>Windows 10 BitLocker 'ı yapılandırma  

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) 'da oturum açın ve profil oluştur > cihaz yapılandırma > Profiller ' e gidin.  

2. Aşağıdaki seçenekleri ayarlayın:  
   - Platformunun Windows 10 ve üzeri  
   - Profil türü: Endpoint protection   

3. **Ayarlar** > **Windows şifrelemesi**' ni seçin.

4. BitLocker ayarlarını iş gereksinimlerinizi karşılayacak şekilde yapılandırın ve ardından **Tamam**' ı seçin.  

5. Ek ayarların yapılandırmasını tamamladıktan sonra profili kaydedin.  

### <a name="manage-bitlocker"></a>BitLocker 'ı yönetme  

Intune bir Windows 10 cihazını BitLocker ile şifreledikten sonra, Intune [şifreleme raporunu](encryption-monitor.md)görüntülerken BitLocker kurtarma anahtarlarını görüntüleyebilir ve alabilirsiniz.  

## <a name="next-steps"></a>Sonraki adımlar  

[Cihaz uyumluluk](compliance-policy-create-windows.md) ilkesi oluşturma  

Yönetmek için şifreleme raporunu kullanın:  
- [BitLocker kurtarma anahtarları](encryption-monitor.md#bitlocker-recovery-keys)
- [Filekasası kurtarma anahtarları](encryption-monitor.md#filevault-recovery-keys)

Intune ile yapılandırabileceğiniz şifreleme ayarlarını inceleyerek şunları yapabilirsiniz:  
- [BitLocker](endpoint-protection-windows-10.md#windows-encryption)  
- [FileVault](endpoint-protection-macos.md#filevault)  
 
 
