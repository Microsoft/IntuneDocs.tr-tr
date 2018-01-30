---
title: "Windows 10 için Intune Endpoint Protection ayarları"
titlesuffix: Azure portal
description: "Windows 10 cihazlarda BitLocker gibi Endpoint Protection ayarlarını denetlemek için kullanabileceğiniz Intune ayarlarını öğrenin.\""
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 01/16/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f33598abe08ffb958ddac9eb7725ab500f9db981
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
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
3. Profiller dikey penceresinde **Profil oluştur**’u seçin.
4. **Profil oluştur** dikey penceresinde, cihaz özellikleri profili için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden **Windows 10 ve üzeri**’ni seçin.
6. **Profil türü** açılan listesinden **Endpoint protection**'ı seçin.
7. İstediğiniz ayarları yapılandırın. Bu konunun ayrıntılarını, her ayarın ne yaptığını anlamanıza yardımcı olması için kullanın. İşiniz bittiğinde **Tamam**’ı seçin.
8. **Profil oluştur** dikey penceresine dönün ve **Oluştur**’u seçin.

Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.

## <a name="windows-defender-application-guard"></a>Windows Defender Application Guard

Application Guard yalnızca Windows 10 (64 bit) cihazlar için kullanılabilir. Bu profili kullanmak, Application Guard’ı etkinleştirmek için bir Win32 bileşeni yükler.

- **Application Guard** - Onaylanmamış siteleri bir Hyper-V sanallaştırılmış gözatma kapsayıcısında açın.
- **Pano davranışı** - Yerel bilgisayar ile Application Guard sanal tarayıcı arasında hangi kopyala/yapıştır eylemlerine izin verileceğini seçin.
- **Kuruluş sitelerinde harici içerik** - Onaylanmamış web sitelerine ait içeriklerin yüklenmesini engelleyin.
- **Sanal tarayıcıdan yazdırma** - PDF, XPS, yerel yazıcılar ve/veya ağ yazıcılarının sanal tarayıcı içeriklerini yazdırmasına izin verin.
- **Günlük toplama** - Bir Application Guard gözatma oturumunda gerçekleşen olaylara ait günlükleri toplayın.
- **Kullanıcı tarafından oluşturulan tarayıcı verilerini koruma** - Bir Application Guard sanal gözatma oturumunda oluşturulan kullanıcı verilerinin (parolalar, favoriler ve tanımlama bilgileri gibi) kaydedilmesine izin verin.


## <a name="windows-defender-firewall"></a>Windows Defender Güvenlik Duvarı

### <a name="global-settings"></a>Genel ayarlar

Bu ayarlar tüm ağ türlerine uygulanabilir.

- **Dosya Aktarım Protokolü** - Durum bilgisi olan FTP’leri engelleyin.
- **Silmeden önce güvenlik ilişkilendirme boşta kalma süresi** - Güvenlik ilişkilendirmeleri, *n* saniye boyunca hiçbir ağ trafiği algılanmadığında silinir.
- **Önceden paylaşılan anahtar kodlaması** - UTF-8 kullanarak önceden paylaşılmış anahtarlar kodlayın.
- **IPsec istisnaları** - **IPv6 ICMP tür kodları komşu bulma**, **ICMP**, **IPv6 ICMP tür kodları yönlendirici bulma** ve **IPv4 ve IPv6 DHCP ağ trafiği** dahil olmak üzere belirli bir trafiği IPsec’ten muaf olacak şekilde yapılandırın.
- **Sertifika iptali liste doğrulama** - **CRL doğrulamasını devre dışı bırakma** **CRL doğrulamasını yalnızca iptal edilmiş sertifikada başarısız yapma** ve **CRL doğrulamasını herhangi bir hata durumunda başarısız yapma** dahil olmak üzere sertifika iptali liste doğrulamasının nasıl uygulanacağına dair bir değer ayarlayın.
- **Mümkün olduğunda kimlik doğrulama kümesini anahtar modülüne göre eşleştirme** - Anahtar oluşturma modüllerini, bir kümedeki tüm kimlik doğrulaması paketlerini desteklemedikleri durumlarda tüm kimlik doğrulama kümesini şekilde ayarlayın.
- **Paket sıraya alma** - IPsec tünel ağ geçidi senaryosunda şifreli alma ve düz metin iletme için alma tarafında yazılım ölçeklendirmenin nasıl etkinleştirildiğini belirtin. Bu, paket sırasının korunmasını sağlar.

### <a name="network-settings"></a>Ağ ayarları

Bu ayarlar; **Etki alanı (iş yeri) ağı**, **Özel (keşfedilebilir) ağ** ve **Ortak (keşfedilemeyen) ağ** dahil olmak üzere belirli ağ türlerine uygulanabilir.

#### <a name="general-settings"></a>Genel ayarlar

- **Windows Defender Güvenlik Duvarı** - Ağ trafiğini engellemek için bu ayarı etkinleştirin.
- **Gizlilik mod** - Güvenlik Duvarı’nın gizli modda çalışmasını engelleyin. Böylece **IPsec güvenli paket muafiyeti**’ni de engelleyebilirsiniz.
- **Tam korumalı** - Bunu ve güvenlik duvarı ayarını etkinleştirmek, tüm gelen trafiği engeller.
- **Çok noktaya yayına tek noktaya yayın yanıtları** - Çok noktaya yayına tek noktaya yayın yanıtlarını engelleyin. Genellikle çok noktaya yayın veya yayın iletilerine tek noktaya yayın yanıtları istemezsiniz çünkü bu yanıtlar bir hizmet reddi saldırısına veya bilinen bir bilgisayarı araştırmaya çalışan bir saldırgana işaret eder.
- **Gelen bildirimler** -Bir uygulamanın bir bağlantı noktasında dinlenmesi engellendiğinde kullanıcılara bildirim gösterilmesini engelleyin.
- **Gelen bağlantılar için varsayılan eylem** - Güvenlik duvarının gelen bağlantılarda gerçekleştirdiği varsayılan eylemi engelleyin.

#### <a name="rule-merging"></a>Kural birleştirme

- **Yerel mağazada yetkilendirilmiş uygulama Windows Defender Güvenlik Duvarı kuralları** - Yerel mağazada yetkilendirilmiş uygulama güvenlik duvarı kurallarının tanınması ve uygulanmasını sağlayın.
- **Yerel mağazada genel bağlantı noktası Windows Defender Güvenlik Duvarı kuralları** - Yerel mağazada genel bağlantı noktası güvenlik duvarı kurallarının tanınması ve uygulanmasını sağlayın.
- **Yerel mağazada Windows Defender Güvenlik Duvarı kuralları** - Yerel mağazada güvenlik duvarı kurallarının tanınması ve uygulanmasını sağlayın.
- **Yerel mağazada IPsec kuralları** - Şema veya bağlantı güvenlik kuralı sürümlerine bakılmaksızın yerel mağazadan bağlantı güvenlik kuralları uygulayın.

## <a name="windows-defender-smartscreen-settings"></a>Windows Defender SmartScreen ayarları

- **Uygulamalar ve dosyalar için SmartScreen** - Dosya yürütme ve uygulama çalıştırma için Windows SmartScreen’i etkinleştirin.
- **Doğrulanmamış dosyaların yürütülmesi** - Son kullanıcının, Windows SmartScreen tarafından doğrulanmamış dosyaları çalıştırmasını engelleyin.

## <a name="windows-encryption"></a>Windows şifreleme

### <a name="windows-settings"></a>Windows ayarları

Bu ayarlar, tüm Windows 10 sürümleri için geçerlidir.

- **Cihaz şifreleme** - Etkinleştirilirse, kullanıcılardan cihaz şifrelemesini etkinleştirmeleri istenir. Ayrıca kullanıcılardan başka bir sağlayıcının şifrelemesinin etkin olmadığını onaylamaları istenir. Başka bir şifreleme yöntemi etkinken Windows şifrelemesi açılırsa cihaz kullanılamaz hale gelebilir.
- **Depolama kartı şifreleme** - Cihazın kullandığı çıkarılabilir depolama kartlarını şifrelemek için bu ayarı etkinleştirin.


### <a name="bitlocker-base-settings"></a>BitLocker temel ayarları

Temel ayarlar, tüm veri sürücüsü türleri için evrensel BitLocker ayarlarıdır. BitLocker Grup İlke ayarları, tüm veri sürücüsü türlerinde son kullanıcıların değiştirebileceği sürücü şifreleme görevleri veya yapılandırma seçeneklerini yönetir.

- **Diğer disk şifrelemesi için uyarı** - Son kullanıcıların makinelerindeki diğer disk şifrelemesi için uyarı istemini devre dışı bırakın.
- **Şifreleme yöntemlerini yapılandır** - Bu ayarı işletim sistemi, veri ve çıkarılabilir sürücüler için şifreleme algoritmalarını yapılandırmak için etkinleştirin.
    - **İşletim sistemi sürücüleri için şifreleme** - İşletim sistemi sürücüleri için şifreleme yöntemini seçin. XTS-AES algoritmasını kullanmanızı öneririz.
    - **Sabit veri sürücüleri için şifreleme** - Sabit (yerleşik) veri sürücüleri için şifreleme yöntemini seçin. XTS-AES algoritmasını kullanmanızı öneririz.
    - **Çıkarılabilir veri sürücüleri için şifreleme** - Çıkarılabilir veri sürücülerinin şifreleme yöntemini seçin. Çıkarılabilir sürücü, Windows 10 çalıştırmayan cihazlarla kullanılıyorsa AES-CBC algoritmasını kullanmanızı öneririz.

### <a name="bitlocker-os-drive-settings"></a>BitLocker işletim sistemi sürücüsü ayarları

Bu ayarlar, belirli işletim sistemi veri sürücüleri için geçerlidir.

- **Başlangıçta ek kimlik doğrulaması** - Güvenilir Platform Modülü (TPM) kullanımı dahil olmak üzere, bilgisayar başlatma için kimlik doğrulama gereksinimlerini yapılandırın.
    - **Uyumlu olmayan TPM yongası ile BitLocker**
    - **Uyumlu TPM başlangıcı** - TPM yongasına izin verilip verilmeyeceğini veya yonganın gerekli olup olmadığını yapılandırın.
    - **Uyumlu TPM başlangıç PIN’i** - TPM yongasıyla bir PIN’e izin verilip verilmeyeceğini veya PIN’in gerekli olup olmadığını yapılandırın.
    - **Uyumlu TPM başlangıç anahtarı** - TPM yongasıyla bir anahtara izin verilip verilmeyeceğini veya anahtarın gerekli olup olmadığını yapılandırın.
    - **Uyumlu TPM başlangıç anahtarı ve PIN’i** - TPM yongasıyla bir anahtar ve PIN’e izin verilip verilmeyeceğini veya anahtar ve PIN'in gerekli olup olmadığını yapılandırın.
- **En Düşük PIN Uzunluğu** - TPM başlangıç PIN'inin en düşük uzunluğunu yapılandırmak için bu ayarı etkinleştirin.
    - **En düşük karakter sayısı** - Başlangıç PIN'i için gereken **4**-**20** arasındaki karakter sayısını girin.
- **İşletim sistemi sürücüsünü kurtarma** - BitLocker ile korunan işletim sistemi sürücülerinin, gerekli başlatma bilgileri olmadığında nasıl kurtarılacağını denetlemek için bu ayarı etkinleştirin.
    - **Sertifika tabanlı veri kurtarma aracısı** - BitLocker korumalı işletim sistemi sürücülerinde veri kurtarma aracıları kullanılabilmesini istiyorsanız bu ayarı etkinleştirin.
    - **Kullanıcının kurtarma anahtarı oluşturması** - Kullanıcıların 48 basamaklı bir kurtarma parolası oluşturmasına izin verilip verilmeyeceğini veya bunun gerekli olup olmadığını yapılandırın.
    - **Kullanıcının kurtarma anahtarı oluşturması** - Kullanıcıların 256 bitlik kurtarma anahtarı oluşturmasına izin verilip verilmeyeceğini veya bunun gerekli olup olmadığını yapılandırın.
    - **BitLocker kurulum sihirbazında kurtarma seçenekleri** - Kullanıcıların BitLocker’ı açtıklarında kurtarma seçeneklerini görmesini veya değiştirmesini engellemek için bu ayarı etkinleştirin.
    - **BitLocker kurtarma bilgilerini AD DS'ye kaydet** - BitLocker kurtarma bilgilerinin Active Directory'ye kaydedilmesini etkinleştirir.
    - **AD DS'ye depolanan BitLocker kurtarma bilgileri** - BitLocker kurtarma bilgilerinin hangi bölümlerinin Active Directory’de depolanacağını yapılandırın. Aşağıdakilerden birini seçin:
        - **Yedekleme kurtarma parolaları ve anahtar paketleri**
        - **Yalnızca yedekleme kurtarma parolaları**
    - **BitLocker’ı etkinleştirmeden önce kurtarma bilgilerini AD DS’de depolama** - Kullanıcıların, cihaz etki alanına katılmadan ve BitLocker kurtarma bilgileri Active Directory’ye başarıyla depolanmadan BitLocker’ı açmasını engellemek için bu ayarı etkinleştirin.
- **Önyükleme kurtarma iletisi ve URL’si** - Önyükleme anahtarı kurtarma ekranında görüntülenen iletiyi ve URL’yi yapılandırmak için bu ayarı etkinleştirin.
    - **Önyükleme kurtarma iletisi** - Önyükleme kurtarma iletisinin kullanıcılara gösterilme şeklini yapılandırın. Aşağıdakilerden birini seçin:
        - **Varsayılan kurtarma iletisi ve URL'sini kullan**
        - **Boş kurtarma iletisi ve URL'si kullan**
        - **Özel kurtarma iletisi kullan**
        - **Özel kurtarma URL'si kullan**


### <a name="bitlocker-fixed-data-drive-settings"></a>BitLocker sabit veri sürücüsü ayarları

- **BitLocker tarafından korunmayan sabit veri sürücüsüne yazma erişimi** - Etkinleştirilirse üzerine yazılabilmesi için tüm sabit veya yerleşik veri sürücülerinde BitLocker koruması etkinleştirilmelidir.
- **Sabit sürücü kurtarma** - Gerekli başlatma bilgileri olmadığında BitLocker korumalı sabit sürücülerin kurtarılma biçimini denetlemek için bu ayarı etkinleştirin.
    - **Veri kurtarma aracısı** - BitLocker korumalı sabit sürücülerle veri kurtarma aracıları kullanılmasını istiyorsanız bu ayarı etkinleştirin.
    - **Kullanıcının kurtarma anahtarı oluşturması** - Kullanıcıların 48 basamaklı bir kurtarma parolası oluşturmasına izin verilip verilmeyeceğini veya bunun gerekli olup olmadığını yapılandırın.  
    - **Kullanıcının kurtarma anahtarı oluşturması** - Kullanıcıların 256 bitlik kurtarma anahtarı oluşturmasına izin verilip verilmeyeceğini veya bunun gerekli olup olmadığını yapılandırın.
    - **BitLocker kurulum sihirbazında kurtarma seçenekleri** - Kullanıcıların BitLocker’ı açtıklarında kurtarma seçeneklerini görmesini veya değiştirmesini engellemek için bu ayarı etkinleştirin.
    - **BitLocker kurtarma bilgilerini AD DS'ye kaydet** - BitLocker kurtarma bilgilerinin Active Directory'ye kaydedilmesini etkinleştirir.
    - **AD DS’de BitLocker kurtarma bilgileri** - BitLocker kurtarma bilgilerinin hangi bölümlerinin Active Directory’de depolanacağını yapılandırın. Aşağıdakilerden birini seçin:
        - **Yedekleme kurtarma parolaları ve anahtar paketleri**
        - **Yalnızca yedekleme kurtarma parolaları**
    - **BitLocker’ı etkinleştirmeden önce kurtarma bilgilerini AD DS’de depolama** - Kullanıcıların, cihaz etki alanına katılmadan ve BitLocker kurtarma bilgileri Active Directory’ye başarıyla depolanmadan BitLocker’ı açmasını engellemek için bu ayarı etkinleştirin.

### <a name="bitlocker-removable-data-drive-settings"></a>BitLocker çıkarılabilir veri sürücüsü ayarları

- **BitLocker tarafından korunmayan çıkarılabilir veri sürücüsüne yazma erişimi** - BitLocker şifrelemesinin çıkarılabilir depolama sürücülerinde gerekli olup olmadığını belirtin.
  - **Başka bir kuruluşta yapılandırılmış cihazlara yazma erişimi** - Başka bir kuruluşa ait çıkarılabilir veri sürücülerine yazılıp yazılamayacağını belirtin.

## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard

Çalışanlarınızın kullandığı uygulamalarda saldırı yüzeyini yönetmek ve azaltmak için [Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard) kullanın.

### <a name="attack-surface-reduction"></a>Saldırı Yüzeyini Azaltma

Genellikle makinelere bulaşmak için açık arayan kötü amaçlı yazılımlar tarafından kullanılan [eylem ve uygulamaları önlemeye](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard) yardımcı olun.

#### <a name="rules-to-prevent-office-macro-threats"></a>Office Macro tehditlerini önlemek için kurallar

Office uygulamalarının aşağıdaki eylemleri yapmasını engelleyin:

- **Office uygulamalarının diğer işlemlere katılması (özel durum yok)**
- **Office uygulamaları/makrolarının yürütülebilir içerik oluşturması**
- **Office uygulamalarının alt işlemler başlatması**
- **Win32’nin Office makro kodundan içeri aktarması**

#### <a name="rules-to-prevent-script-threats"></a>Komut dosyası tehditlerini önlemek için kurallar

Komut dosyası tehditlerini önlemeye yardımcı olmak için şunları engelleyin:

- **Karartılmış js/vbs/ps/makro kod**
- **İnternetten indirilen zararlı yükü yürüten js/vbs(özel durum yok)**

#### <a name="rules-to-prevent-email-threats"></a>E-posta tehditlerini önlemek için kurallar

E-posta tehditlerini önlemeye yardımcı olmak için şunları engelleyin:

- **E-postadan (web posta/posta istemcisi) gelen yürütülebilir içeriklerin (exe, dll, ps, js, vbs vb.) yürütülmesi**

#### <a name="attack-surface-reduction-exceptions"></a>Saldırı Yüzeyi Azaltma özel durumları

- **Saldırı yüzeyi azaltma kurallarından muaf tutulacak dosya ve klasörler** - Yapılandırılan kurallardan muaf tutulacak konumlar listesi içeri aktarın/ekleyin.

### <a name="controlled-folder-access"></a>Denetlenen klasör erişimi

Önemli verileri fidye yazılımı gibi kötü amaçlı uygulama ve tehditlerden korumaya yardımcı olun.

- **Klasör koruma** - Dosya ve klasörleri, kötü amaçlı yazılımlar tarafından yapılan istenmeyen değişikliklerden koruyun. Bir **Korumalı dosyalara erişimi olan uygulamalar listesi** içeri aktarabilir veya bu uygulamaları el ile ekleyebilirsiniz. Ayrıca bir **Korunması gereken ek klasörler listesi** yükleyebilir veya bu klasörleri el ile ekleyebilirsiniz.

### <a name="network-filtering"></a>Ağ filtreleme

Uygulamaların düşük itibarlı IP/etki alanına giden bağlantılarını engelleyin.

### <a name="exploit-protection"></a>Exploit protection

Bellek, denetim akışı ve ilke kısıtlamalarını yapılandırmanıza izin veren bir XML dosyasını bir uygulamanın açıklarından faydalanılmasını önlemek üzere yükleyerek **Exploit protection’ın kullanıcı tarafından düzenlemesi**’ni engelleyin.

Exploit protection’ı etkinleştirmek için sistemi ve dilediğiniz uygulama risk azaltma ayarlarını temsil eden bir XML dosyası oluşturun. İki yöntemden birini kullanarak bunu yapabilirsiniz:

 1. PowerShell: Risk azaltma ayarlarını yapılandırmak ve XML temsillerini dışarı aktarmak için Get-ProcessMitigation, Set-ProcessMitigation ve ConvertTo-ProcessMitigationPolicy PowerShell cmdlet’lerinden biri veya daha fazlasını kullanın.

 2. Windows Defender Güvenlik Merkezi Kullanıcı Arabirimi: Windows Defender Güvenlik Merkezi’nde Uygulama & tarayıcı denetimine tıklayın ve çıkan ekranda aşağı kaydırarak Exploit Protection’ı bulun. Önce Sistem ayarları ve Program ayarları sekmelerini kullanarak risk azaltma ayarlarını yapılandırın. Daha sonra bunların bir XML temsilini dışarı aktarmak için ekranın altında yer alan Dışarı aktarma ayarları bağlantısını bulun.

## <a name="windows-defender-application-control"></a>Windows Defender Uygulama Denetimi

Windows Defender Uygulama Denetimi tarafından denetlenmesi gereken veya çalıştırılmasına güvenilen ek uygulamaları seçmek için **Uygulama denetimi kod bütünlüğü ilkeleri**’ni kullanın. Windows mağazasındaki Windows bileşenlerinin ve tüm uygulamaların çalıştırılmasına otomatik olarak güvenilir.

Uygulamalar, “yalnızca denetimli” modunda çalıştırıldığında engellenmeyecektir. “Yalnızca denetim” modu, tüm olayları yerel istemci günlüklerine kaydeder.

## <a name="windows-defender-security-center"></a>Windows Defender Güvenlik Merkezi

Windows Defender Güvenlik Merkezi uygulaması, diğer bireysel özelliklerden ayrı bir uygulama veya işlem olarak çalışır ve Eylem Merkezi’nde bildirim gösterir. Her bir özelliğin durumunu görmek ve bazı yapılandırmaları gerçekleştirmek için bir toplayıcı veya tek bir yer olarak görev yapar. [Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) belgelerinden daha fazla bilgi edinin.

#### <a name="windows-defender-security-center-app-and-notifications"></a>Windows Defender Güvenlik Merkezi uygulaması ve bildirimleri

Windows Defender Güvenlik Merkezi uygulamasının çeşitli alanlarına son kullanıcı erişimini engelleyin. Bir bölümü gizlemek, bu bölümle ilgili bildirimleri de engeller.

- **Virüs ve tehdit koruması**
- **Cihaz performans ve sistem durumu**
- **Güvenlik duvarı ve ağ koruması**
- **Uygulama ve tarayıcı denetimi**
- **Aile seçenekleri**
- **Uygulamanın görüntülenen alanlarından bildirimler** - Son kullanıcılara hangi bildirimlerin gösterileceğini seçin. Kritik olmayan bildirimlere, Windows Defender Antivirus etkinliğinin özetleri ve taramalar tamamlandığında verilen bildirimler dahildir. Diğer tüm bildirimler kritik olarak kabul edilir.

#### <a name="it-contact-information"></a>BT iletişim bilgileri

Windows Defender Güvenlik Merkezi uygulaması ve uygulama bildirimlerinde gösterilecek BT iletişim bilgilerini sağlayın. **Uygulamada ve bildirimlerde göster**, **Yalnızca uygulamada göster**, **Yalnızca bildirimlerde göster** veya **Gösterme** seçeneklerinden birini seçebilirsiniz. **BT kuruluş adı** ile aşağıdaki iletişim seçeneklerinden en az birini belirtmeniz gerekir:

- **BT departmanı telefon numarası veya Skype kimliği**
- **BT departmanı e-posta adresi**
- **BT destek web sitesi URL’si**

## <a name="next-steps"></a>Sonraki adımlar

Devam edip bu profili gruplara atamak isterseniz, bkz. [Cihaz profillerini atama](device-profile-assign.md).
