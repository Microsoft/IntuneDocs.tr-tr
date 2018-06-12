---
title: Microsoft Intune - Azure’da Windows 10 cihazlara Endpoint Protection ekleme | Microsoft Docs
description: 'Windows 10 cihazlarda Windows Defender’ı etkinleştirmek için Endpoint Protection kullanma veya yapılandırma özelliği şunları içerir: Application Guard, Güvenlik Duvarı, SmartScreen, şifreleme ve BitLocker, Exploit Guard, Uygulama Denetimi, Güvenlik Merkezi ve Microsoft Intune’daki yerel cihazlarda güvenlik.'
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0831f374b9c6da417d8159dce1b58e40f0d3643c
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34744950"
---
# <a name="endpoint-protection-settings-for-windows-10-and-later-in-intune"></a>Intune’da Windows 10 (ve sonrası) için Endpoint Protection ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Endpoint Protection profili, Windows 10 cihazlarda BitLocker ve Windows Defender gibi güvenlik özelliklerini denetlemenize izin verir.

Bu makaledeki bilgileri kullanarak Endpoint Protection profilleri oluşturun. Windows Defender Virüsten Koruma’yı yapılandırmak için bkz. [Windows 10 Cihaz Kısıtlamaları](device-restrictions-windows-10.md#windows-defender-antivirus). 

> [!NOTE]
> Bu ayarlar, Windows 10’un Home ve Professional sürümlerinde desteklenmez.

## <a name="windows-defender-application-guard"></a>Windows Defender Application Guard

Microsoft Edge kullanırken Windows Defender Application Guard ortamınızı kuruluşunuz tarafından güvenilir olarak tanımlanmamış sitelerden korur. Kullanıcılar, yalıtılmış ağ sınırı listenizde olmayan siteleri ziyaret ettiğinde siteler Hyper-V'de sanal gözatma oturumunda açılır. Güvenilen siteler, Cihaz Yapılandırması içinde yapılandırılabilen bir ağ sınırı tarafından tanımlanır. 

Application Guard yalnızca Windows 10 (64 bit) cihazlar için kullanılabilir. Bu profili kullanmak, Application Guard’ı etkinleştirmek için bir Win32 bileşeni yükler.

- **Application Guard**: Onaylanmamış siteleri Hyper-V sanallaştırılmış gözatma kapsayıcısında açın.
- **Pano davranışı**: Yerel bilgisayar ile Application Guard sanal tarayıcısı arasında hangi kopyala/yapıştır eylemlerine izin verileceğini seçin.
- **Kuruluş sitelerinde harici içerik**: Onaylanmamış web sitelerine ait içeriklerin yüklenmesini engelleyin.
- **Sanal tarayıcıdan yazdırma**: PDF, XPS, yerel yazıcılar ve/veya ağ yazıcılarının sanal tarayıcı içeriklerini yazdırmasına izin verin.
- **Günlük toplama**: Bir Application Guard gözatma oturumunda gerçekleşen olaylara ait günlükleri toplayın.
- **Kullanıcı tarafından oluşturulan tarayıcı verilerini koruma**: Bir Application Guard sanal gözatma oturumunda oluşturulan kullanıcı verilerini (parolalar, favoriler ve tanımlama bilgileri gibi) kaydedin.
- **Grafik hızlandırma**: Application Guard sanal gözatma oturumunda çalışırken görsel ağırlıklı web sitelerini daha hızlı yükleyin. Bir sanal grafik işleme birimine erişim etkinleştirildiğinde web siteleri daha hızlı yüklenir.
- **Dosyaları konak dosya sistemine indirin**: Kullanıcıların sanallaştırılmış tarayıcıdan konak işletim sistemine dosya indirmesine izin verin.

## <a name="windows-defender-firewall"></a>Windows Defender Güvenlik Duvarı

### <a name="global-settings"></a>Genel ayarlar

Bu ayarlar tüm ağ türlerine uygulanabilir.

- **Dosya Aktarım Protokolü**: Durum bilgisi olan FTP’leri engelleyin.
- **Silmeden önce güvenlik ilişkilendirme boşta kalma süresi**: Güvenlik ilişkilendirmeleri, *n* saniye boyunca hiçbir ağ trafiği algılanmadığında silinir.
- **Önceden paylaşılan anahtar kodlaması**: UTF-8 kullanarak önceden paylaşılmış anahtarlar kodlayın.
- **IPsec muafiyetleri**: **Komşu bulma IPv6 ICMP tür kodları**, **ICMP**, **Yönlendirici bulma IPv6 ICMP tür kodları** ve **IPv4 ve IPv6 DHCP ağ trafiği** dahil olmak üzere belirli bir trafiği IPsec’ten muaf olacak şekilde yapılandırın.
- **Sertifika iptal listesi doğrulaması**: **CRL doğrulamasını devre dışı bırak** **CRL doğrulaması yalnızca sertifika iptal edildiğinde başarısız olsun** ve **Bir hata ile karşılaşıldığında CRL doğrulaması başarısız olsun** dahil olmak üzere sertifika iptal listesi doğrulamasının nasıl uygulanacağına dair bir değer ayarlayın.
- **Mümkün olduğunda kimlik doğrulama kümesini anahtar modülüne göre eşleştir**: Anahtar oluşturma modüllerini, bir kümedeki tüm kimlik doğrulaması paketlerini desteklemedikleri durumlarda tüm kimlik doğrulama kümesini yoksayacak şekilde ayarlayın.
- **Paket sırası**: IPsec tünel ağ geçidi senaryosunda şifreli alma ve düz metin iletme için alma tarafında yazılım ölçeklendirmenin nasıl etkinleştirildiğini belirtin. Bu ayar, paket sırasının korunmasını sağlar.

### <a name="network-settings"></a>Ağ ayarları

Bu ayarlar; **Etki alanı (iş yeri) ağı**, **Özel (keşfedilebilir) ağ** ve **Ortak (keşfedilemeyen) ağ** dahil olmak üzere belirli ağ türlerine uygulanabilir.

#### <a name="general-settings"></a>Genel ayarlar

- **Windows Defender Güvenlik Duvarı**: Ağ trafiğini engellemek için bu ayarı etkinleştirin.
- **Gizli mod**: Güvenlik Duvarı’nın gizli modda çalışmasını engelleyin. Gizli modu engellemek, **IPsec güvenli paket muafiyetini** de engellemenize imkan verir.
- **Korumalı**: Bu ayarı ve güvenlik duvarı ayarını etkinleştirmek, tüm gelen trafiği engeller.
- **Çok noktaya yayınlara yönelik tek noktaya yayın yanıtları**: Çok noktaya yayına tek noktaya yayın yanıtlarını engelleyin. Normalde, yayın veya çok noktaya yayın iletilerine tek noktaya yayın yanıtları almak istemezsiniz. Bu yanıtlar bir hizmet reddi (DOS) saldırısına veya bilinen bir canlı bilgisayarı araştırmaya çalışan bir saldırgana işaret eder.
- **Gelen bildirimler**: Uygulamanın bir bağlantı noktasında dinlemesi engellendiğinde kullanıcılara bildirim gösterilmesini engelleyin.
- **Gelen bağlantılar için varsayılan eylem**: Güvenlik duvarının gelen bağlantılarda gerçekleştirdiği varsayılan eylemi engelleyin.

#### <a name="rule-merging"></a>Kural birleştirme

- **Yerel depodan yetkili uygulama Windows Defender Güvenlik Duvarı kuralları**: Yerel depoda yetkilendirilmiş uygulama güvenlik duvarı kurallarının tanınması ve uygulanmasını sağlayın.
- **Yerel depodan genel bağlantı noktası Windows Defender Güvenlik Duvarı kuralları**: Yerel depoda genel bağlantı noktası güvenlik duvarı kurallarının tanınması ve uygulanmasını sağlayın.
- **Yerel depodaki Windows Defender Güvenlik Duvarı kuralları**: Yerel depoda güvenlik duvarı kurallarının tanınması ve uygulanmasını sağlayın.
- **Yerel depodaki IPsec kuralları**: Şema veya bağlantı güvenlik kuralı sürümlerine bakılmaksızın yerel depodan bağlantı güvenlik kuralları uygulayın.

## <a name="windows-defender-smartscreen-settings"></a>Windows Defender SmartScreen ayarları

- **Uygulamalar ve dosyalar için SmartScreen**: Dosya yürütme ve uygulama çalıştırma için Windows SmartScreen’i etkinleştirin.
- **Doğrulanmamış dosyaları yürütme**: Son kullanıcının, Windows SmartScreen tarafından doğrulanmamış dosyaları çalıştırmasını engelleyin.

## <a name="windows-encryption"></a>Windows Şifreleme

### <a name="windows-settings"></a>Windows Ayarları

Aşağıdaki iki ayar, tüm Windows 10 sürümleri için geçerlidir:

- **Cihazları şifrele**: Etkinleştirilirse, kullanıcılardan cihaz şifrelemesini etkinleştirmeleri istenir. Ayrıca kullanıcılardan başka bir sağlayıcının şifrelemesinin etkin olmadığını onaylamaları istenir. Başka bir şifreleme yöntemi etkinken Windows şifrelemesi açılırsa cihaz kullanılamaz hale gelebilir.
- **Depolama kartını şifrele**: Cihazın kullandığı çıkarılabilir depolama kartlarını şifrelemek için bu ayarı etkinleştirin.


### <a name="bitlocker-base-settings"></a>BitLocker temel ayarları

Temel ayarlar, tüm veri sürücüsü türleri için evrensel BitLocker ayarlarıdır. BitLocker Grup İlke ayarları, tüm veri sürücüsü türlerinde son kullanıcıların değiştirebileceği sürücü şifreleme görevleri veya yapılandırma seçeneklerini yönetir.

- **Diğer disk şifrelemesi için uyarı**: Son kullanıcıların makinelerindeki diğer disk şifrelemesi için uyarı istemini devre dışı bırakın.
- **Şifreleme yöntemlerini yapılandır**: Bu ayarı işletim sistemi, veri ve çıkarılabilir sürücüler için şifreleme algoritmalarını yapılandırmak için etkinleştirin.
  - **İşletim sistemi sürücüleri için şifreleme**: İşletim sistemi sürücüleri için şifreleme yöntemini seçin. XTS-AES algoritmasını kullanmanızı öneririz.
  - **Sabit veri sürücüleri için şifreleme**: Sabit (yerleşik) veri sürücüleri için şifreleme yöntemini seçin. XTS-AES algoritmasını kullanmanızı öneririz.
  - **Çıkarılabilir veri sürücüleri için şifreleme**: Çıkarılabilir veri sürücülerinin şifreleme yöntemini seçin. Çıkarılabilir sürücü, Windows 10 çalıştırmayan cihazlarla kullanılıyorsa AES-CBC algoritmasını kullanmanızı öneririz.

### <a name="bitlocker-os-drive-settings"></a>BitLocker işletim sistemi sürücüsü ayarları

Bu ayarlar, belirli işletim sistemi veri sürücüleri için geçerlidir.

- **Başlangıçta ek kimlik doğrulaması**: Güvenilir Platform Modülü (TPM) kullanımı dahil olmak üzere, bilgisayar başlatma için kimlik doğrulama gereksinimlerini yapılandırın.
  - **Uyumlu olmayan TPM yongası ile BitLocker**
  - **Uyumlu TPM başlatma**: TPM yongasına izin vermeyi, izin vermemeyi veya gerektirmeyi seçin.
  - **Uyumlu TPM başlangıç PIN'i**: TPM yongasıyla bir başlangıç PIN'i kullanmaya izin vermeyi, izin vermemeyi veya gerektirmeyi seçin.
  - **Uyumlu TPM başlangıç anahtarı**: TPM yongasıyla bir başlangıç anahtarı kullanmaya izin vermeyi, izin vermemeyi veya gerektirmeyi seçin.
  - **Uyumlu TPM başlangıç anahtarı ve PIN'i**: TPM yongasıyla bir başlangıç anahtarı ve PIN'i kullanmaya izin vermeyi, izin vermemeyi veya gerektirmeyi seçin.
- **En Düşük PIN Uzunluğu**: TPM başlangıç PIN'inin en düşük uzunluğunu yapılandırmak için bu ayarı etkinleştirin.
  - **En düşük karakter sayısı**: Başlangıç PIN'i için gereken **4**-**20** arasındaki karakter sayısını girin.
- **İşletim sistemi sürücüsünü kurtarma**: BitLocker ile korunan işletim sistemi sürücülerinin, gerekli başlatma bilgileri olmadığında nasıl kurtarılacağını denetlemek için bu ayarı etkinleştirin.
  - **Sertifika tabanlı veri kurtarma aracısı**: BitLocker korumalı işletim sistemi sürücülerinde veri kurtarma aracıları kullanılabilmesini istiyorsanız bu ayarı etkinleştirin.
  - **Kurtarma parolasının kullanıcı tarafından oluşturması**: Kullanıcıların 48 basamaklı bir kurtarma parolası oluşturmasına izin verilip verilmeyeceğini veya bunun gerekli olup olmadığını seçin.
  - **Kurtarma anahtarının kullanıcı tarafından oluşturması**: Kullanıcıların 256 bitlik bir kurtarma anahtarı oluşturmasına izin verilip verilmeyeceğini veya bunun gerekli olup olmadığını seçin.
  - **BitLocker kurulum sihirbazındaki kurtarma seçenekleri**: Kullanıcıların BitLocker’ı açtıklarında kurtarma seçeneklerini görmesini veya değiştirmesini engellemek için bu ayarı etkinleştirin.
  - **BitLocker kurtarma bilgilerini AD DS'ye kaydet**: BitLocker kurtarma bilgilerinin Active Directory'ye kaydedilmesini etkinleştirir.
  - **AD DS'ye depolanmış BitLocker kurtarma bilgileri**: BitLocker kurtarma bilgilerinin hangi bölümlerinin Active Directory’de depolanacağını yapılandırın. Aşağıdakilerden birini seçin:
    - **Yedekleme kurtarma parolaları ve anahtar paketleri**
    - **Yalnızca yedekleme kurtarma parolaları**
  - **BitLocker’ı etkinleştirmeden önce kurtarma bilgilerini AD DS’de depola**: Kullanıcıların, cihaz etki alanına katılmadan ve BitLocker kurtarma bilgileri Active Directory’ye başarıyla depolanmadan BitLocker’ı açmasını engellemek için bu ayarı etkinleştirin.
- **Önyükleme öncesi kurtarma iletisi ve URL**: Önyükleme öncesi anahtar kurtarma ekranında görüntülenen iletiyi ve URL’yi yapılandırmak için bu ayarı etkinleştirin.
  - **Önyükleme öncesi kurtarma iletisi**: Önyükleme öncesi kurtarma iletisinin kullanıcılara gösterilme şeklini yapılandırın. Aşağıdakilerden birini seçin:
    - **Varsayılan kurtarma iletisi ve URL'sini kullan**
    - **Boş kurtarma iletisi ve URL'si kullan**
    - **Özel kurtarma iletisi kullan**
    - **Özel kurtarma URL'si kullan**

### <a name="bitlocker-fixed-data-drive-settings"></a>BitLocker sabit veri sürücüsü ayarları

- **BitLocker tarafından korunmayan sabit veri sürücülerine yazma erişimi**: Etkinleştirilirse üzerine yazılabilmesi için tüm sabit veya yerleşik veri sürücülerinde BitLocker koruması etkinleştirilmelidir.
- **Sabit sürücü kurtarma**: Gerekli başlatma bilgileri olmadığında BitLocker korumalı sabit sürücülerin kurtarılma biçimini denetlemek için bu ayarı etkinleştirin.
  - **Veri kurtarma aracısı**: BitLocker korumalı sabit sürücülerle veri kurtarma aracıları kullanılmasını istiyorsanız bu ayarı etkinleştirin.
  - **Kurtarma parolasının kullanıcı tarafından oluşturulması**: Kullanıcıların 48 basamaklı bir kurtarma parolası oluşturmasına izin verilip verilmeyeceğini veya bunun gerekli olup olmadığını yapılandırın.  
  - **Kurtarma anahtarının kullanıcı tarafından oluşturması** - Kullanıcıların 256 bitlik kurtarma anahtarı oluşturmasına izin verilip verilmeyeceğini veya bunun gerekli olup olmadığını yapılandırın.
  - **BitLocker kurulum sihirbazındaki kurtarma seçenekleri**: Kullanıcıların BitLocker’ı açtıklarında kurtarma seçeneklerini görmesini veya değiştirmesini engellemek için bu ayarı etkinleştirin.
  - **BitLocker kurtarma bilgilerini AD DS'ye kaydet**: BitLocker kurtarma bilgilerinin Active Directory'ye kaydedilmesini etkinleştirir.
  - **AD DS’de BitLocker kurtarma bilgileri**: BitLocker kurtarma bilgilerinin hangi bölümlerinin Active Directory’de depolanacağını yapılandırın. Aşağıdakilerden birini seçin:
    - **Yedekleme kurtarma parolaları ve anahtar paketleri**
    - **Yalnızca yedekleme kurtarma parolaları**
  - **BitLocker’ı etkinleştirmeden önce kurtarma bilgilerini AD DS’de depola**: Kullanıcıların, cihaz etki alanına katılmadan ve BitLocker kurtarma bilgileri Active Directory’ye başarıyla depolanmadan BitLocker’ı açmasını engellemek için bu ayarı etkinleştirin.

### <a name="bitlocker-removable-data-drive-settings"></a>BitLocker çıkarılabilir veri sürücüsü ayarları

- **BitLocker tarafından korunmayan çıkarılabilir veri sürücülerine yazma erişimi**: BitLocker şifrelemesinin çıkarılabilir depolama sürücülerinde gerekli olup olmadığını belirtin.
  - **Başka bir kuruluşta yapılandırılmış cihazlara yazma erişimi**: Başka bir kuruluşa ait çıkarılabilir veri sürücülerine yazılıp yazılamayacağını belirtin.

## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard

Çalışanlarınızın kullandığı uygulamalarda saldırı yüzeyini yönetmek ve azaltmak için [Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard) kullanın.

### <a name="attack-surface-reduction"></a>Saldırı Yüzeyini Azaltma

- **Windows yerel güvenlik yetkilisi alt sisteminden kimlik bilgisi çalma eylemlerine bayrak ekleme**

Genellikle makinelere bulaşmak için açık arayan kötü amaçlı yazılımlar tarafından kullanılan [eylem ve uygulamaları önlemeye](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard) yardımcı olun.

#### <a name="rules-to-prevent-office-macro-threats"></a>Office Macro tehditlerini önlemek için kurallar

Office uygulamalarının aşağıdaki eylemleri yapmasını engelleyin:

- **Office uygulamalarının diğer işlemlere katılması (özel durum yok)**
- **Office uygulamaları/makrolarının yürütülebilir içerik oluşturması**
- **Office uygulamalarının alt işlemler başlatması**
- **Win32’nin Office makro kodundan içeri aktarması**

#### <a name="rules-to-prevent-script-threats"></a>Komut dosyası tehditlerini önlemek için kurallar

Komut dosyası tehditlerini önlemeye yardımcı olmak için aşağıdakileri engelleyin:

- **Karartılmış js/vbs/ps/makro kod**
- **İnternetten indirilen zararlı yükü yürüten js/vbs(özel durum yok)**
- **PSExec ve WMI komutlarından işlem oluşturma**
- **USB’den çalışan güvenilmeyen ve imzasız işlemler**
- **Bir yaygınlık, yaş veya güvenilenler listesi kriterine uymayan yürütülebilir dosyalar**

#### <a name="rules-to-prevent-email-threats"></a>E-posta tehditlerini önlemek için kurallar

E-posta tehditlerini önlemeye yardımcı olmak için aşağıdakileri engelleyin:

- **E-postadan (web posta/posta istemcisi) gelen yürütülebilir içeriklerin (exe, dll, ps, js, vbs vb.) yürütülmesi**

#### <a name="rules-to-protect-against-ransomware"></a>Fidye yazılımlarına karşı korunmak için kurallar
- **Gelişmiş fidye yazılımı koruması**

> [!TIP]
> [Windows Defender Exploit Guard ile saldırı yüzeylerini azaltma](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard), bu kurallar hakkında daha fazla ayrıntı sağlar.

#### <a name="attack-surface-reduction-exceptions"></a>Saldırı Yüzeyi Azaltma özel durumları

- **Saldırı yüzeyi azaltma kurallarının dışında tutulacak dosya ve klasörler**: Yapılandırılan kuralların dışında tutulacak konumlar listesini içeri aktarın/ekleyin.

### <a name="controlled-folder-access"></a>Denetlenen klasör erişimi

Önemli verileri fidye yazılımı gibi kötü amaçlı uygulama ve tehditlerden korumaya yardımcı olun.

- **Klasör koruma**: Dosya ve klasörleri, kötü amaçlı yazılımlar tarafından yapılan istenmeyen değişikliklerden koruyun. Bir **Korumalı dosyalara erişimi olan uygulamalar listesi** içeri aktarabilir veya bu uygulamaları el ile ekleyebilirsiniz. Ayrıca bir **Korunması gereken ek klasörler listesi** yükleyebilir veya bu klasörleri el ile ekleyebilirsiniz.

### <a name="network-filtering"></a>Ağ filtreleme

Uygulamaların düşük itibarlı IP/etki alanına giden bağlantılarını engelleyin.

### <a name="exploit-protection"></a>Exploit protection

Bellek, denetim akışı ve ilke kısıtlamalarını yapılandırmanıza izin veren bir XML dosyasını karşıya yükleyerek **Kullanıcıların Exploit Protection arabirimini düzenlemesi**’ni engelleyin. XML dosyasındaki ayarlar bir uygulamanın açıklarından yararlanılmasını engellemek için kullanılabilir.

Exploit protection’ı etkinleştirmek için sistemi ve dilediğiniz uygulama risk azaltma ayarlarını temsil eden bir XML dosyası oluşturun. İki yöntemden birini kullanarak bunu yapabilirsiniz:

 1. PowerShell: Get-ProcessMitigation, Set-ProcessMitigation ve ConvertTo-ProcessMitigationPolicy PowerShell cmdlet’lerinden biri veya daha fazlasını kullanın. Cmdlet'ler risk azaltma ayarlarını yapılandırır ve bunların XML gösterimini dışarı aktarır.

 2. Windows Defender Güvenlik Merkezi Kullanıcı Arabirimi: Windows Defender Güvenlik Merkezi’nde Uygulama & tarayıcı denetimine tıklayın ve çıkan ekranda aşağı kaydırarak Exploit Protection’ı bulun. Önce Sistem ayarları ve Program ayarları sekmelerini kullanarak risk azaltma ayarlarını yapılandırın. Daha sonra bunların bir XML temsilini dışarı aktarmak için ekranın altında yer alan Dışarı aktarma ayarları bağlantısını bulun.

## <a name="windows-defender-application-control"></a>Windows Defender Uygulama Denetimi

Windows Defender Uygulama Denetimi tarafından denetlenmesi gereken veya çalıştırılmasına güvenilen ek uygulamaları seçmek için **Uygulama denetimi kod bütünlüğü ilkeleri**’ni kullanın. Windows mağazasındaki Windows bileşenlerinin ve tüm uygulamaların çalıştırılmasına otomatik olarak güvenilir.

Uygulamalar, **yalnızca denetim** modunda çalıştırıldığında engellenmez. **Yalnızca denetimli** modu, tüm olayları yerel istemci günlüklerine kaydeder.

Uygulama Denetimi etkinleştirildiğinde, yalnızca modun **Zorla**’dan **Yalnızca denetimli**’ye değiştirilmesiyle devre dışı bırakılabilir. Modun **Zorla**’dan **Yapılandırılmadı**’ya değiştirilmesi, Uygulama Denetimi’nin atanmış cihazlarda zorlanmaya devam etmesiyle sonuçlanır.

## <a name="windows-defender-credential-guard"></a>Windows Defender Credential Guard
Windows Defender Credential Guard kimlik bilgileri hırsızlığı saldırılarına karşı korur. Gizli dizileri yalnızca ayrıcalıklı sistem yazılımlarının erişebileceği şekilde yalıtır.

**Credential Guard** ayarları şunlardır:

- **Devre dışı**: Daha önce **UEFI kilidi olmadan etkin** seçeneğiyle açılmışsa, Credential Guard’ı uzaktan kapatır.
- **UEFI kilidi ile etkin**: Credential Guard’ın kayıt defteri anahtarı veya Grup İlkesi kullanılarak uzaktan devre dışı bırakılamamasını sağlar.

    > [!NOTE]
    > Bu ayarı kullanırsanız ve daha sonra Credential Guard'ı devre dışı bırakmak isterseniz, Grup İlkesi'ni **Devre Dışı** olarak ayarlamalısınız. Ayrıca, UEFI yapılandırma bilgilerini her bilgisayardan fiziksel olarak temizleyin. UEFI yapılandırması devam ettiği sürece, Credential Guard etkindir.

- **UEFI kilidi olmadan etkin**: Credential Guard’ın Grup İlkesi kullanılarak uzaktan devre dışı bırakılmasına olanak tanır. Bu ayarı kullanan cihazların Windows 10 sürüm 1511'i veya daha yeni bir sürümü çalıştırıyor olması gerekir.

Credential Guard'ı etkinleştirdiğinizde, aşağıdaki gerekli özellikler de etkinleştirilir:

- **Sanallaştırma Tabanlı Güvenlik** (VBS): Bir sonraki yeniden önyükleme sırasında açılır. Sanallaştırma tabanlı güvenlik, güvenlik hizmetlerine destek sağlamak için Windows Hiper Yöneticisi'ni kullanır.
- **Dizin Bellek Erişimi ile Güvenli Önyükleme**: VBS'yi Güvenli Önyükleme ve doğrudan bellek erişimi (DMA) korumalarıyla açar. DMA korumaları donanım desteği gerektirir ve yalnızca doğru yapılandırılmış cihazlarda etkinleştirilir.

## <a name="windows-defender-security-center"></a>Windows Defender Güvenlik Merkezi

Windows Defender Güvenlik Merkezi uygulaması, diğer özelliklerden her biri ayrı bir uygulama veya işlem olarak çalışır. İşlem Merkezi aracılığıyla bildirimler gösterir. Her bir özelliğin durumunu görmek ve bazı yapılandırmaları gerçekleştirmek için bir toplayıcı veya tek bir yer olarak görev yapar. [Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) belgelerinden daha fazla bilgi edinin.

#### <a name="windows-defender-security-center-app-and-notifications"></a>Windows Defender Güvenlik Merkezi uygulaması ve bildirimleri

Windows Defender Güvenlik Merkezi uygulamasının çeşitli alanlarına son kullanıcı erişimini engelleyin. Bir bölümü gizlemek, bu bölümle ilgili bildirimleri de engeller.

- **Virüs ve tehdit koruması**
- **Cihaz performans ve sistem durumu**
- **Güvenlik duvarı ve ağ koruması**
- **Uygulama ve tarayıcı denetimi**
- **Aile seçenekleri**
- **Uygulamanın görüntülenen alanlarından bildirimler**: Son kullanıcılara hangi bildirimlerin gösterileceğini seçin. Kritik olmayan bildirimlere, Windows Defender Antivirus etkinliğinin özetleri ve taramalar tamamlandığında verilen bildirimler dahildir. Diğer tüm bildirimler kritik olarak kabul edilir.

#### <a name="it-contact-information"></a>BT iletişim bilgileri

Windows Defender Güvenlik Merkezi uygulaması ve uygulama bildirimlerinde gösterilecek BT iletişim bilgilerini sağlayın. **Uygulamada ve bildirimlerde göster**, **Yalnızca uygulamada göster**, **Yalnızca bildirimlerde göster** veya **Gösterme** seçeneklerinden birini seçebilirsiniz. **BT kuruluş adı** ile aşağıdaki iletişim seçeneklerinden en az birini girmeniz gerekir:

- **BT departmanı telefon numarası veya Skype kimliği**
- **BT departmanı e-posta adresi**
- **BT destek web sitesi URL’si**

## <a name="local-device-security-options"></a>Yerel cihaz güvenliği seçenekleri

Windows 10 cihazlarında yerel güvenlik ayarlarını yapılandırmak için bu seçenekleri kullanın.

### <a name="accounts"></a>Hesaplar

- **Yeni Microsoft hesapları ekle**: Kullanıcıların bu bilgisayara yeni Microsoft hesapları eklemesini engeller.
- **Parola olmadan uzaktan oturum açma**: Parola korumalı olmayan yerel hesapların fiziksel cihaz dışındaki konumlardan oturum açmasını etkinleştirin.

#### <a name="admin"></a>Yönetim

- **Yerel yönetici hesabı**: Yerel Yönetici hesabının etkin mi yoksa devre dışı mı olduğunu belirleyin.
- **Yönetici hesabını yeniden adlandır**: Yönetici hesabının güvenlik tanımlayıcısıyla (SID) ilişkilendirilecek farklı bir hesap adı tanımlayın.

#### <a name="guest"></a>Konuk

- **Konuk hesabı**: Konuk hesabının etkin mi yoksa devre dışı mı olduğunu belirleyin.
- **Konuk hesabını yeniden adlandır**: Konuk hesabının güvenlik tanımlayıcısıyla (SID) ilişkilendirilecek farklı bir hesap adı tanımlayın.

### <a name="devices"></a>Cihazlar

- **Oturum açma olmadan cihazı çıkar**: Taşınabilir bir bilgisayarın oturum açma gerektirmeden çıkarılmasını engelleyin.
- **Paylaşılan yazıcılar için yazıcı sürücülerini yükle**: Paylaşılan yazıcıya bağlanma işlemi kapsamında yazıcı sürücülerini yüklemeyi yalnızca yöneticilerle kısıtlayın.
- **CD-ROM erişimini yerel etkin kullanıcıya kısıtla**: Bu ayarın etkinleştirilmesi, yalnızca etkileşimli olarak oturum açan kullanıcının CD-ROM medyasına erişmesine izin verir
- **Çıkarılabilir medyayı biçimlendir ve çıkar**: Çıkarılabilir NTFS medyasını kimlerin biçimlendirmesine ve çıkarmasına izin verileceğini tanımlayın:
  - **Yapılandırılmadı**
  - **Yöneticiler ve Yetkili Kullanıcılar**
  - **Yöneticiler ve Etkileşimli Kullanıcılar**

### <a name="interactive-logon"></a>Etkileşimli Oturum Açma

- **Ekran koruyucu etkinleşmeden önceki kilit ekranında işlem yapılmadan geçen dakika sayısı**: Ekran koruyucu çalıştırılmadan önce etkileşimli masa üstünün oturum açma ekranında işlem yapılmadan geçecek en fazla dakika sayısını tanımlayın.
- **Oturum açmak için CTRL+ALT+DEL gerektir**: Kullanıcının oturum açabilmesi için önce CTRL+ALT+DEL tuşlarına basılmasını gerektirin.
- **Akıllı kart kaldırma davranışı**: Oturum açma kullanıcısı için akıllı kartın akıllı kart okuyucusundan çıkarılması durumunda neler olacağını belirler. Seçenekleriniz şunlardır:

  - **İş İstasyonunu Kilitle**: Akıllı kart çıkarıldığında iş istasyonu kilitlenir. Bu seçenek kullanıcıların akıllı kartlarını alarak alandan uzaklaşmasına ve yine de korumalı oturumu sürdürmesine olanak tanır.
  - **Oturumu Kapatmaya Zorla**: Kullanıcı akıllı kartı çıkardığında oturumu otomatik olarak kapatılır.
  - **Bir Uzak Masaüstü Hizmetleri oturumu bağlantısını kes**: Akıllı kartın çıkarılması kullanıcının oturumunu kapatmadan oturumu bağlantısını keser. Bu seçenek kullanıcının daha sonra yeniden oturum açmak zorunda kalmadan akıllı kartı takıp oturumu devam ettirmesine veya akıllı kart okuyucuyla donatılmış başka bir bilgisayarda bunu yapmasına olanak tanır. Yerel bir oturum söz konusuysa, bu ilke İş İstasyonunu Kilitle ilkesiyle tam olarak aynı işlevi görür.

    [LocalPoliciesSecurity seçenekleri](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-interactivelogon-smartcardremovalbehavior) başlığı altında daha fazla ayrıntı sağlanır.

#### <a name="display"></a>Görüntüle

- **Kilit ekranında kullanıcı bilgileri**: Oturum kilitlendiğinde görüntülenen kullanıcı bilgilerini yapılandırın. Yapılandırılmazsa, kullanıcı görünen adı, etki alanı ve kullanıcı adı gösterilir.
  - **Yapılandırılmadı**: Kullanıcı görünen adı, etki alanı ve kullanıcı adı
  - **Kullanıcı görünen adı, etki alanı ve kullanıcı adı**
  - **Yalnızca kullanıcı görünen adı**
  - **Kullanıcı bilgilerini görüntüleme**
- **Son oturum açmış kullanıcıyı gizle**: Bu cihazda oturum açmış olan son kişinin kullanıcı adını görüntülemeyin.
- **Oturum açma sırasında kullanıcı adını gizle**: Kimlik bilgileri girildikten sonra ve cihazın masaüstü gösterilmeden önce bu cihazda oturum açan kişinin kullanıcı adını görüntülemeyin.
- **Oturum açma ileti başlığı**: Oturum açmaya çalışan kullanıcılar için ileti başlığını ayarlayın.
- **Oturum açma ileti metni**: Oturum açmaya çalışan kullanıcılar için ileti metnini ayarlayın.

### <a name="network-access-and-security"></a>Ağ erişimi ve güvenlik

- **Adlandırılmış Kanallara ve Paylaşımlara anonim erişim**: **Yapılandırılmadı** (varsayılan) paylaşım ve Adlandırılmış Kanal ayarlarına anonim erişimi kısıtlar. Anonim olarak erişilebilen ayarlar için geçerlidir.
- **SAM hesaplarının anonim olarak listelenmesi**: Anonim kullanıcıların SAM hesaplarını listelemesine **izin verin**. Windows anonim kullanıcılara etki alanı hesaplarının ve ağ paylaşımlarının adlarını listeleme izni verir.
- **SAM hesaplarının ve paylaşımların anonim listelenmesi**: **Yapılandırılmadı** (varsayılan), anonim kullanıcıların etki alanı hesaplarıyla ağ paylaşımlarının adlarını listeleyebileceği anlamına gelir. SAM hesaplarının ve paylaşımlarının anonim listelenmesini önlemek için **Engelle** olarak ayarlayın.
- **Parola değişiminde depolanan LAN Manager karma değeri**: Bir sonraki parola değişikliğinde, yeni parolanın karma değerini LAN Manager'da (LM) depolamaya **izin verin**. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, karma değer depolanmaz.
- **PKU2U kimlik doğrulama istekleri**: Bu cihaza yönelik PKU2U kimlik doğrulama isteklerinin çevrimiçi kimlikleri kullanmasını **engelleyin**. **Yapılandırılmadı** (varsayılan) ayarı bu isteklere izin verir.
- **SAM'ye uzak RPC bağlantılarını kısıtla**: Kullanıcıların ve grupların SAM'ye uzak çağrı yapmasını engellemek için varsayılan Güvenlik Tanımlayıcısı Tanım Dili dizesine **izin verin**. **Yapılandırılmadı** (varsayılan) ayarında, kullanıcıların ve grupların SAM'ye uzak çağrı yapmasına izin vermek için varsayılan Güvenlik Tanımlayıcısı Tanım Dili dizesi yapılandırılmaz.
  - **Güvenlik tanımlayıcısı**

### <a name="recovery-console-and-shutdown"></a>Kurtarma konsolu ve kapatma

- **Kapatma sırasında sanal bellek disk belleği dosyasını temizle**: Cihaz kapatıldığında sanal bellek disk belleği dosyasını temizleyin.
- **Oturum açma olmadan kapatma**: Bilgisayarı Windows oturum açma ekranından kapatma seçeneğini engelleyin. Bu durumda, kullanıcıların bir sistem kapatması gerçekleştirmek için önce bilgisayarda başarıyla oturum açmaları gerekir.

### <a name="user-account-control"></a>Kullanıcı hesap denetimi

- **Güvenli konum olmadan UIA bütünlüğü**: Dosya sisteminde uygulamaların güvenli olmayan konumlardan UIAccess bütünlük düzeyiyle çalıştırılmasını etkinleştirin.
- **Dosya ve kayıt defteri yazma hatalarını kullanıcı başına konumlarında sanal olarak oluştur**: Uygulama yazma hatalarının tanımlı kayıt defteri ve dosya sistemi konumlarına yeniden yönlendirilip yönlendirilmeyeceğini belirleyin. Bundan başka, uygulamanın başarısız olmasına neden olabilir.
- **Yalnızca imzalı ve doğrulanmış yürütülebilir dosyaları yükselt**: Verili bir yürütülebilir dosyanın çalıştırılmasına izin vermeden önce bu dosya için PKI sertifika yolu doğrulamasını zorunlu tutun.

#### <a name="uia-elevation-prompt-behavior-settings"></a>UIA yükseltme istemi davranışı ayarları

- **Yöneticiler için yükseltme istemi**: Yönetici Onay Modu'nda yöneticiler için yükseltme isteminin davranışını tanımlayın:
  - **İstem olmadan yükselt**
  - **Güvenli masaüstünde kimlik bilgileri iste**
  - **Güvenli masaüstünde onay iste**
  - **Kimlik bilgileri iste**
  - **Onay iste**
  - **Yapılandırılmadı**: Windows dışı ikili dosyalar için onay istemi
- **Standart kullanıcılar için yükseltme istemi**: Standart kullanıcılar için yükseltme isteminin davranışını tanımlayın:
  - **Yükseltme isteklerini otomatik olarak reddet**
  - **Güvenli masaüstünde kimlik bilgileri iste**
  - **Yapılandırılmadı**: Kimlik bilgileri istemi
- **Yükseltme istemlerini kullanıcının etkileşimli masaüstüne yönlendir**: Tüm yükseltme isteklerinin güvenli masaüstü yerine etkileşimli kullanıcının masaüstüne gitmesini etkinleştirin. Yöneticiler ve standart kullanıcılar için istemci davranışı ilke ayarları kullanılır.
- **Uygulama yüklemeleri için yükseltilmiş istem**: Yükseltilmiş ayrıcalıklar gerektiren uygulama yüklemeleri yönetici kimlik bilgileri isteyecektir.
- **Güvenli masaüstü olmadan UIA yükseltme istemi**: UIAccess uygulamalarının güvenli masaüstü kullanmadan yükseltme isteminde bulunmasına izin verin.

#### <a name="admin-approval-mode-settings"></a>Yönetici Onay Modu ayarları

- **Yerleşik Yönetici için Yönetici Onay Modu**: Yerleşik yönetici hesabının Yönetici Onay Modunu mu kullanacağını yoksa tüm uygulamaları tam yönetici ayrıcalıklarıyla mı çalıştıracağını tanımlar.
- **Tüm yöneticileri Yönetici Onay Modunda çalıştır**: Yönetici Onay Modunun ve tüm UAC ilke ayarlarının etkinleştirilip etkinleştirilmeyeceğini tanımlar.

### <a name="microsoft-network-client"></a>Microsoft Ağ İstemcisi

- **İletişimleri dijital olarak imzala (sunucu onaylarsa)**: SMB istemcisinin SMB paket imzalama anlaşması yapmaya çalışıp çalışmayacağını belirler. Etkinleştirildiğinde (Yapılandırılmadı), Microsoft ağ istemcisi sunucudan oturum kurulumunda SMB paket imzalama gerçekleştirilmesini ister. Sunucuda paket imzalama etkinleştirilirse, paket imzalama anlaşması yapılır. Bu ilke devre dışı bırakılırsa, SMB istemcisi hiçbir zaman SMB paket imzalama anlaşması yapmaz.
- **Üçüncü taraf SMB sunucularına şifrelenmemiş parola gönder**: Etkinleştirildiğinde, Sunucu İleti Bloğu (SMB) yeniden yönlendiricisinin kimlik doğrulama sırasında parola şifrelemesini desteklemeyen Microsoft dışı SMB sunucularına düz metin parolalar göndermesine izin verilir.

### <a name="microsoft-network-server"></a>Microsoft Ağ Sunucusu

- **İletişimleri dijital olarak imzala (istemci onaylarsa)**: SMB sunucusunun istekte bulunan istemcilerle SMB paket imzalama anlaşması yapıp yapmayacağını belirler. Etkinleştirildiğinde, Microsoft ağ sunucusu istemci tarafından istendiği gibi SMB paket imzalama anlaşması yapar. Başka bir deyişle, istemcide paket imzalama etkinleştirildiyse paket imzalama anlaşması yapılır. **Yapılandırılmadığında** veya devre dışı bırakıldığında (varsayılan), SMB istemcisi hiçbir zaman SMB paket imzalama anlaşması yapmaz.
- **İletişimleri dijital olarak imzala (her zaman)**: SMB sunucu bileşeninin paket imzalama gerektirip gerektirmediğini belirler. Etkinleştirildiğinde, Microsoft ağ istemcisi SMB paket imzalama gerçekleştirmeyi kabul etmediği sürece Microsoft ağ sunucusu istemciyle iletişim kurmaz. **Yapılandırılmadığında** veya devre dışı bırakıldığında (Varsayılan), istemciyle sunucu arasında SMB paket imzalama anlaşması yapılır.

## <a name="next-steps"></a>Sonraki adımlar

Bu profili gruplara atamak için bkz. [Cihaz profillerini atama](device-profile-assign.md).