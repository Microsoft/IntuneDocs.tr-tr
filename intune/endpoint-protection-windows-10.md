---
title: "Windows 10 için Intune Endpoint Protection ayarları"
titlesuffix: Azure portal
description: "Windows 10 cihazlarda BitLocker gibi Endpoint Protection ayarlarını denetlemek için kullanabileceğiniz Intune ayarlarını öğrenin.\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 66d13a5a5d4b74cc70696239514875fe0092a164
ms.sourcegitcommit: 4742390f29f84e553e674ea31c88318bda6ab059
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="endpoint-protection-settings-for-windows-10-and-later-in-microsoft-intune"></a>Microsoft Intune'da Windows 10 ve sonrası için Endpoint Protection ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Endpoint Protection profili, Windows 10 cihazlarda BitLocker ve Windows Defender gibi güvenlik özelliklerini denetlemenize izin verir.

Bu konudaki bilgileri Endpoint Protection profilleri oluşturmak için kullanın.

> [!Note]
> Bu ayarlar, Windows 10’un Home ve Professional sürümlerinde desteklenmez.

## <a name="create-an-endpoint-protection-profile"></a>Endpoint Protection profili oluşturma

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihaz yapılandırması**’nı seçin.
2. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
3. Profiller dikey penceresinde **Profil Oluştur**’u seçin.
4. **Profil Oluştur** dikey penceresinde, cihaz özellikleri profili için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden **Windows 10 ve üzeri**’ni seçin.
6. **Profil türü** açılan listesinden **Endpoint protection**'ı seçin.
7. **Windows şifrelemesi** dikey penceresinde istediğiniz ayarları yapılandırın. Bu konunun ayrıntılarını, her ayarın ne yaptığını anlamanıza yardımcı olması için kullanın. İşiniz bittiğinde **Tamam**’ı seçin.
8. **Profil Oluştur** dikey penceresine dönün ve **Oluştur**'u seçin.

Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.

## <a name="windows-defender-smartscreen-settings"></a>Windows Defender SmartScreen ayarları

- **Uygulamalar ve dosyalar için SmartScreen** - Dosya yürütme ve uygulama çalıştırma için Windows SmartScreen’i etkinleştirin.
- **Doğrulanmamış dosyaların yürütülmesi** - Son kullanıcının, Windows SmartScreen tarafından doğrulanmamış dosyaları çalıştırmasını engelleyin.

## <a name="windows-encryption-settings"></a>Windows şifreleme ayarları

### <a name="windows-settings"></a>Windows Ayarları

- **Cihazların şifrelenmesini gerektir (Yalnızca masaüstü)** - Etkinleştirilirse kullanıcılardan cihaz şifrelemesini etkinleştirmesi istenir. Ayrıca kullanıcılardan başka bir sağlayıcının şifrelemesinin etkin olmadığını onaylamaları istenir. Başka bir şifreleme yöntemi etkinken Windows şifrelemesi açılırsa cihaz kullanılamaz hale gelebilir.
- **Depolama Kartının şifrelenmesini gerektir (yalnızca mobil)** - Cihazın kullandığı çıkarılabilir depolama kartlarını şifrelemek için bu ayarı etkinleştirin.


### <a name="bitlocker-base-settings"></a>BitLocker temel ayarları

- **Şifreleme yöntemlerini yapılandır** - Bu ayarı işletim sistemi, veri ve çıkarılabilir sürücüler için şifreleme algoritmalarını yapılandırmak için etkinleştirin.
    - **İşletim sistemi sürücüleri için şifreleme** - İşletim sistemi sürücüleri için şifreleme yöntemini seçin. XTS-AES algoritmasını kullanmanızı öneririz.
    - **Sabit veri sürücüleri için şifreleme** - Sabit (yerleşik) veri sürücüleri için şifreleme yöntemini seçin. XTS-AES algoritmasını kullanmanızı öneririz.
    - **Çıkarılabilir veri sürücüleri için şifreleme** - Çıkarılabilir veri sürücülerinin şifreleme yöntemini seçin. Çıkarılabilir sürücü, Windows 10 çalıştırmayan cihazlarla kullanılıyorsa AES-CBC algoritmasını kullanmanızı öneririz.


### <a name="bitlocker-os-drive-settings"></a>BitLocker işletim sistemi sürücüsü ayarları

- **Başlangıçta ek kimlik doğrulaması gerektir** -
    - **Uyumlu olmayan TPM yongası ile BitLocker** -
    - **TPM başlangıcı** - TPM yongasına izin verilip verilmeyeceğini veya yonganın gerekli olup olmadığını yapılandırın.
    - **TPM başlangıç PIN'i** - TPM yongasıyla bir PIN’e izin verilip verilmeyeceğini veya PIN'in gerekli olup olmadığını yapılandırın.
    - **TPM başlangıç anahtarı** - TPM yongasıyla bir anahtara izin verilip verilmeyeceğini veya anahtarın gerekli olup olmadığını yapılandırın.
    - **TPM başlangıç anahtarı ve PIN** - TPM yongasıyla bir anahtar ve PIN’e izin verilip verilmeyeceğini veya anahtar ve PIN'in gerekli olup olmadığını yapılandırın.
- **En Düşük PIN Uzunluğu** - TPM başlangıç PIN'inin en düşük uzunluğunu yapılandırmak için bu ayarı etkinleştirin.
    - **En düşük karakter sayısı** - Başlangıç PIN'i için gereken **4**-**20** arasındaki karakter sayısını girin.
- **İşletim sistemi sürücüsünü kurtarmayı etkinleştir** - BitLocker ile korunan işletim sistemi sürücülerinin, gerekli başlatma bilgileri olmadığında nasıl kurtarılacağını denetlemek için bu ayarı etkinleştirin.
    - **Sertifika tabanlı veri kurtarma aracısı** - BitLocker korumalı işletim sistemi sürücülerinde veri kurtarma aracıları kullanılabilmesini istiyorsanız bu ayarı etkinleştirin.
    - **Kullanıcının kurtarma anahtarı oluşturması** - Kullanıcıların 48 basamaklı bir kurtarma parolası oluşturmasına izin verilip verilmeyeceğini veya bunun gerekli olup olmadığını yapılandırın.
    - **Kullanıcının kurtarma anahtarı oluşturması** - Kullanıcıların 256 bitlik kurtarma anahtarı oluşturmasına izin verilip verilmeyeceğini veya bunun gerekli olup olmadığını yapılandırın.
    - **BitLocker kurulum sihirbazında kurtarma seçeneklerini gizle** - Kullanıcıların BitLocker'ı açtıklarında kurtarma seçeneklerini görmesini veya değiştirmesini engellemek için bu ayarı etkinleştirin.
    - **BitLocker kurtarma bilgilerini AD DS'ye kaydet** - BitLocker kurtarma bilgilerinin Active Directory'ye kaydedilmesini etkinleştirir.
    - **BitLocker kurtarma bilgilerinin AD DS'ye depolanmasını yapılandır** -BitLocker kurtarma bilgilerinin hangi bölümlerinin Active Directory'de depolanacağını yapılandırın. Aşağıdakilerden birini seçin:
        - **Yedekleme kurtarma parolaları ve anahtar paketleri**
        - **Yalnızca yedekleme kurtarma parolaları**
    - **BitLocker'ı etkinleştirmeden önce kurtarma bilgilerinin AD DS'de depolanmasını gerektir** - Kullanıcıların, cihaz etki alanına katılmadan ve BitLocker kurtarma bilgileri Active Directory'ye başarıyla depolanmadan BitLocker'ı açmasını engellemek için bu ayarı etkinleştirin.
- **Önyükleme kurtarma iletisi ve URL'sini etkinleştir** - Önyükleme anahtarı kurtarma ekranında görüntülenen iletiyi ve URL'yi yapılandırmak için bu ayarı etkinleştirin.
    - **Önyükleme kurtarma iletisi** - Önyükleme kurtarma iletisinin kullanıcılara gösterilme şeklini yapılandırın. Aşağıdakilerden birini seçin:
        - **Varsayılan kurtarma iletisi ve URL'sini kullan**
        - **Boş kurtarma iletisi ve URL'si kullan**
        - **Özel kurtarma iletisi kullan**
        - **Özel kurtarma URL'si kullan**


### <a name="bitlocker-fixed-data-drive-settings"></a>BitLocker sabit veri sürücüsü ayarları

- **BitLocker tarafından korunmayan sabit veri sürücüsüne yazma erişimini engelle** - Etkinleştirilirse üzerine yazılabilmesi için tüm sabit veya yerleşik veri sürücülerinde BitLocker koruması etkinleştirilmelidir.
- **Sabit sürücü kurtarmayı etkinleştir** - Gerekli başlatma bilgileri olmadığında BitLocker korumalı sabit sürücülerin kurtarılma biçimini denetlemek için bu ayarı etkinleştirin.
    - **Veri kurtarma aracısı** - BitLocker korumalı sabit sürücülerle veri kurtarma aracıları kullanılmasını istiyorsanız bu ayarı etkinleştirin.
    - **Kullanıcının kurtarma anahtarı oluşturması** - Kullanıcıların 48 basamaklı bir kurtarma parolası oluşturmasına izin verilip verilmeyeceğini veya bunun gerekli olup olmadığını yapılandırın.  
    - **Kullanıcının kurtarma anahtarı oluşturması** - Kullanıcıların 256 bitlik kurtarma anahtarı oluşturmasına izin verilip verilmeyeceğini veya bunun gerekli olup olmadığını yapılandırın.
    - **BitLocker kurulum sihirbazında kurtarma seçeneklerini gizle** - Kullanıcıların BitLocker'ı açtıklarında kurtarma seçeneklerini görmesini veya değiştirmesini engellemek için bu ayarı etkinleştirin.
    - **BitLocker kurtarma bilgilerini AD DS'ye kaydet** - BitLocker kurtarma bilgilerinin Active Directory'ye kaydedilmesini etkinleştirir.
    - **BitLocker kurtarma bilgilerinin AD DS'ye depolanmasını yapılandır** -BitLocker kurtarma bilgilerinin hangi bölümlerinin Active Directory'de depolanacağını yapılandırın. Aşağıdakilerden birini seçin:
        - **Yedekleme kurtarma parolaları ve anahtar paketleri**
        - **Yalnızca yedekleme kurtarma parolaları**
    - **BitLocker'ı etkinleştirmeden önce kurtarma bilgilerinin AD DS'ye depolanmasını iste** - Kullanıcıların, cihaz etki alanına katılıp BitLocker kurtarma bilgileri Active Directory'de başarıyla depolanmadıkça BitLocker'ı açmalarını engellemek için bu ayarı etkinleştirin.


### <a name="bitlocker-removable-data-drive-settings"></a>BitLocker çıkarılabilir veri sürücüsü ayarları

- **BitLocker tarafından korunmayan çıkarılabilir veri sürücüsüne yazma erişimini engelle** - BitLocker şifrelemesinin çıkarılabilir depolama sürücülerinde gerekli olup olmadığını belirtin.
    - **Başka bir kuruluşta yapılandırılmış cihazlara yazma erişimini engelle** - Başka bir kuruluşa ait çıkarılabilir veri sürücülerine yazılıp yazılamayacağını belirtin.



## <a name="next-steps"></a>Sonraki adımlar

Devam edip bu profili gruplara atamak isterseniz, bkz. [Cihaz profillerini atama](device-profile-assign.md).
