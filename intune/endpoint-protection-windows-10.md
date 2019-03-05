---
title: Microsoft Intune - Azure'da Windows 10 cihazları için koruma ayarları | Microsoft Docs
description: 'Windows 10 cihazlarda Windows Defender’ı etkinleştirmek için Endpoint Protection kullanma veya yapılandırma özelliği şunları içerir: Application Guard, Güvenlik Duvarı, SmartScreen, şifreleme ve BitLocker, Exploit Guard, Uygulama Denetimi, Güvenlik Merkezi ve Microsoft Intune’daki yerel cihazlarda güvenlik.'
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/04/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4794adda447754b5dc72ff1b320ec69553a8b55a
ms.sourcegitcommit: e8c32bd6db2560570d1e1733f999ae3b2c026908
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57305519"
---
# <a name="windows-10-and-later-settings-to-protect-devices-using-intune"></a>Intune kullanarak cihazları korumak için Windows 10 (ve üzeri) ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune cihazlarınızın korunmasına yardımcı olmak üzere birçok ayarlarını içerir. Bu makalede, etkinleştirin ve Windows 10 ve daha yeni cihazlarda yapılandırabileceğiniz tüm ayarları açıklanır. Bu ayarlar, bir uç nokta koruma yapılandırma profilinde de Intune denetimi güvenlik, BitLocker ve Windows Defender'ın da dahil olmak üzere oluşturulur.

Windows Defender antivirüs'ü yapılandırmak için bkz [Windows 10 cihaz kısıtlamaları](device-restrictions-windows-10.md#windows-defender-antivirus).

## <a name="before-you-begin"></a>Başlamadan önce

[Bir uç nokta koruma cihaz yapılandırma profili oluşturma](endpoint-protection-configure.md).

## <a name="windows-defender-application-guard"></a>Windows Defender Application Guard

Aşağıdaki Windows 10 sürümlerinde desteklenir:

- Enterprise
- Professional

Microsoft Edge kullanırken Windows Defender Application Guard, ortamınızı kuruluşunuz tarafından güvenilir olarak tanımlanmayan sitelerden korur. İçinde yalıtılmış bir ağ sınırında listelenmemiş siteler kullanıcıların ziyaret ettiğinizde, siteleri bir Hyper-V sanal gözatma oturumunda açın. Güvenilen siteler cihaz yapılandırmasında yapılandırılan bir ağ sınırı tarafından tanımlanır.

Application Guard yalnızca Windows 10 (64 bit) cihazlar için kullanılabilir. Bu profili kullanmak, Application Guard’ı etkinleştirmek için bir Win32 bileşeni yükler.

- **Application Guard**: **Edge için etkin** güvenilmeyen siteleri bir Hyper-V sanallaştırılmış gözatma kapsayıcısında açar. Bu özelliği açmak için. **Yapılandırılmamış** (varsayılan) anlamına gelir (güvenilen ve güvenilmeyen) herhangi bir siteyi cihazda açılır.
- **Pano davranışı**: Yerel bilgisayar ile Application Guard sanal tarayıcı arasında hangi kopyala/yapıştır eylemlerine izin verileceğini seçin.
- **Kurumsal sitelerdeki dış içerik**: **Blok** yüklenmesini onaylanmamış Web sitelerinden içerik. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında cihazda kuruluşa ait olmayan siteler açılır.
- **Sanal tarayıcıdan yazdırma**: Seçin **izin** bunu PDF, XPS, yerel ve ağ yazıcılarının sanal tarayıcı içeriklerini içerik yazdırabilirsiniz. **Yapılandırılmadı** (varsayılan) ayarı, tüm yazdırma özelliklerini devre dışı bırakır.
- **Günlük toplama**: **İzin** bir Application Guard gözatma oturumunda gerçekleşen olaylara günlüklerini toplamak için. **Yapılandırılmadı** (varsayılan) ayarı, gözatma oturumunda günlük toplamaz.
- **Kullanıcı tarafından oluşturulan tarayıcı verilerini koruma**: **İzin** bir Application Guard sanal gözatma oturumunda oluşturulan kullanıcı verilerinin (örneğin, parolalar, Sık Kullanılanlar ve tanımlama bilgileri) kaydeder. **Yapılandırılmadı** (varsayılan) ayarı, cihaz yeniden başlatıldığında veya bir kullanıcı oturumu kapadığında kullanıcının indirdiği dosya ve verileri atar.
- **Grafik hızlandırmayı**: Seçin **etkinleştirme** bir sanal grafik işlemcisi birimine erişim alarak grafik açısından yoğun Web sitelerini ve daha hızlı video yüklenemedi. **Yapılandırılmadı** (varsayılan) ayarı, grafik için cihazın CPU’sunu kullanır; sanal grafik işleme birimini kullanmaz.
- **Dosyaları konak dosya sistemine dosya indirme**: **Etkinleştirme** kullanıcıların sanallaştırılmış tarayıcıdan konak işletim sistemine dosya indirmesine şekilde. **Yapılandırılmadı** (varsayılan) ayarı, cihazdaki dosyaları yerel olarak tutar ve konak dosya sistemine indirmez.

## <a name="windows-defender-firewall"></a>Windows Defender Güvenlik Duvarı

Aşağıdaki Windows 10 sürümlerinde desteklenir:
- Ana Sayfası
- Professional
- İş
- Enterprise
- Eğitim
- Mobil
- Mobile Enterprise

### <a name="global-settings"></a>Genel ayarlar

Bu ayarlar tüm ağ türlerine uygulanabilir.

- **Dosya Aktarım Protokolü**: **Blok** FTP'leri devre dışı bırakmak için. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında güvenlik duvarı, durum bilgisi olan FTP filtrelemesi yaparak ikincil bağlantılara izin verir.
- **Silmeden önce güvenlik ilişkilendirme boşta kalma süresi**: Güvenlik ilişkilendirmeleri, hiçbir ağ trafiği algılanmadığında silinir *n* saniye. Boşta kalma süresini saniye cinsinden girin.
- **Önceden paylaşılan anahtar kodlaması**: Seçin **etkinleştirme** UTF-8 kullanarak önceden paylaşılan anahtar kodlaması kullanmak için. **Yapılandırılmadı** (varsayılan) ayarı, yerel depo değerini kullanır.
- **IPSec muafiyetleri**: Belirli bir trafik muaf olacak şekilde yapılandırmak da dahil olmak üzere:
  - **Komşu bulma IPv6 ICMP türü kodlar**
  - **ICMP**
  - **Yönlendirici bulma IPv6 ICMP türü kodlar**
  - **Hem IPv4 hem de IPv6 DHCP ağ trafiği**
- **Sertifika iptali liste doğrulama**: Cihaz sertifika iptal listesini nasıl doğrular seçin. Seçenekleriniz **devre dışı bir CRL doğrulamasını**, **başarısız CRL doğrulamasını yalnızca iptal edilmiş sertifikada**, ve **hata ile karşılaşıldığında CRL başarısız doğrulama**.
- **Kimlik doğrulama kümesini anahtar modülüne desteklemedikleri eşleşen**: **Etkinleştirme** anahtar modülleri, bunlar desteklemeyen kimlik doğrulama paketlerini yoksayması gereken şekilde. **Yapılandırılmadı** olarak ayarlandığında, anahtar oluşturma modülleri kümede belirtilen kimlik doğrulaması paketlerinin tamamını desteklemiyorsa bütün kimlik doğrulaması kümesini yoksaymak ZORUNDA kalır.
- **Paket sıraya alma**: Ölçeklendirmesi alma tarafında yazılım şifreli alma nasıl etkinleştirildiğini girin ve metin iletme için IPSec tünel ağ geçidi senaryosunda temizleyin. Bu ayar, paket sırasının korunmasını onaylar.

### <a name="network-settings"></a>Ağ ayarları

Bu ayarlar; **Etki alanı (iş yeri) ağı**, **Özel (keşfedilebilir) ağ** ve **Ortak (keşfedilemeyen) ağ** dahil olmak üzere belirli ağ türlerine uygulanabilir.

#### <a name="general-settings"></a>Genel ayarlar

- **Windows Defender Güvenlik Duvarı**: Seçin **etkinleştirme** güvenlik duvarı ve Gelişmiş Güvenlik açmak için. **Yapılandırılmadı** (varsayılan) ayarı, diğer ilke ayarlarından bağımsız olarak tüm ağ trafiğine izin verir.
- **Gizli mod**: **Blok** gizli modda çalışmasını gelen güvenlik duvarı. Gizli modu engellemek, **IPsec güvenli paket muafiyetini** de engellemenize imkan verir. **Yapılandırılmadı** (varsayılan) ayarı, güvenlik duvarını gizli modda çalıştırarak yoklama isteklerine yanıtların önlenmesine yardımcı olur.
- **Korumalı**: **Blok** bu özelliği devre dışı bırakır. **Yapılandırılmadı** (varsayılan) ayarı, bu ayarı etkinleştirir. Bu ayar ve Windows Defender Güvenlik Duvarı etkinleştirildiğinde, diğer ilke ayarlarından bağımsız olarak tüm gelen trafik engellenir.
- **Çok noktaya yayına tek noktaya yayın yanıtları**: Ayarlandığında **blok**, çok noktaya yayına tek noktaya yayın yanıtları devre dışı bırakır. Normalde, yayın veya çok noktaya yayın iletilerine tek noktaya yayın yanıtları almak istemezsiniz. Bu yanıtlar bir hizmet (DOS) saldırısına veya bilinen bir bilgisayarı araştırmaya çalışan bir saldırgan reddi belirtebilirsiniz. **Yapılandırılmadı** (varsayılan) ayarı, bu ayarı etkinleştirir.
- **Gelen bildirimler**: Ayarlandığında **blok**, uygulama bir bağlantı noktasında dinleme yapması engellendiğinde kullanıcılara bildirim gizler. **Yapılandırılmadı** (varsayılan) ayarı, bu ayarı etkinleştirir ve bir uygulamanın bağlantı noktasında dinlemesi engellendiğinde kullanıcılara bildirim gösterebilir.
- **Gelen bağlantılar için varsayılan eylem**: Ayarlandığında **blok**, varsayılan güvenlik duvarı gelen bağlantılarda eyleminin değil. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, varsayılan güvenlik duvarı eylemi gelen bağlantılarda çalıştırılır.

#### <a name="rule-merging"></a>Kural birleştirme

- **Uygulama Windows Defender güvenlik duvarı kurallarını yerel depodan yetkili**: Seçin **etkinleştirme** bunlar tanınması ve şekilde güvenlik duvarı kuralları Yerel Depodaki uygulamak için. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, yerel depoda yetkili uygulama güvenlik duvarı kuralları yoksayılır ve uygulanmaz.
- **Yerel mağazada genel bağlantı noktası Windows Defender güvenlik duvarı kuralları**: Seçin **etkinleştirme** genel bağlantı noktası güvenlik duvarı kurallarını tanınıp zorlanması için yerel depolama alanındaki uygulamak için. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, yerel depoda genel bağlantı noktası güvenlik duvarı kuralları yoksayılır ve uygulanmaz.
- **Yerel Depodaki Windows Defender güvenlik duvarı kuralları**: Seçin **etkinleştirme** güvenlik duvarı kurallarını tanınıp zorlanması için yerel depolama alanındaki uygulamak için. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, yerel depodan güvenlik duvarı kuralları yoksayılır ve uygulanmaz.
- **Yerel mağazada IPSec kuralları**: Seçin **etkinleştirme** şema veya bağlantı güvenlik kuralı sürümlerine bakılmaksızın yerel mağazadan bağlantı güvenlik kuralları uygulanamadı. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, şema veya bağlantı güvenlik kuralı sürümlerine bakılmaksızın yerel depodan bağlantı güvenlik kuralları yoksayılır ve uygulanmaz.

## <a name="windows-defender-smartscreen-settings"></a>Windows Defender SmartScreen ayarları

Microsoft Edge’in yüklü olduğu şu Windows 10 sürümlerinde desteklenir:
- Ana Sayfası
- Professional
- İş
- Enterprise
- Eğitim
- Mobil
- Mobile Enterprise

**Ayarları**:

- **Uygulamalar ve dosyalar için SmartScreen**: **Etkinleştirme** Windows SmartScreen dosya yürütme ve uygulama çalıştırma. SmartScreen, bulut tabanlı bir kimlik avından korunma ve kötü amaçlı yazılımdan korunma bileşenidir. **Yapılandırılmadı** (varsayılan) ayarı, SmartScreen’i devre dışı bırakır.
- **Doğrulanmamış dosyaların yürütülmesi**: **Blok** son kullanıcıların, dosyaları çalıştıran, Windows SmartScreen tarafından doğrulanmış olup henüz. **Yapılandırılmadı** (varsayılan) ayarı, bu özelliği devre dışı bırakır ve son kullanıcıların doğrulanmamış dosyaları çalıştırmasına izin verir.

## <a name="windows-encryption"></a>Windows Şifreleme

### <a name="windows-settings"></a>Windows Ayarları

Aşağıdaki Windows 10 sürümlerinde desteklenir:

- Professional
- İş
- Enterprise
- Eğitim
- Mobil
- Mobile Enterprise

**Ayarları**:

- **Cihazları şifrele**: **Gerekli** cihaz şifrelemesini etkinleştirmesini istemek için. Windows sürümü ve sistem yapılandırmasına bağlı olarak kullanıcılardan şunlar istenebilir:  
  - Başka bir sağlayıcı şifrelemesinin etkin olmadığını onaylama
  - Bitlocker Sürücü Şifreleme’yi kapatma ve Bitlocker’ı tekrar açmak zorunda olma
    
    Başka bir şifreleme yöntemi etkinken Windows şifrelemesi açılırsa cihaz kullanılamaz hale gelebilir. 
- **(Yalnızca mobil) depolama kartı şifreleme**: **Gerekli** cihazın kullandığı çıkarılabilir depolama kartlarını şifrelemek için. **Yapılandırılmadı** (varsayılan) ayarı, depolama kartı şifrelemesi gerektirmez ve kullanıcıdan bunu açmasını istemez. Bu ayar yalnızca Windows 10 mobil cihazlar için geçerlidir.

### <a name="bitlocker-base-settings"></a>BitLocker temel ayarları

Aşağıdaki Windows 10 sürümlerinde desteklenir:

- Enterprise
- Eğitim
- Mobil
- Mobile Enterprise
- Professional

Temel ayarlar, tüm veri sürücüsü türleri için evrensel BitLocker ayarlarıdır. Bu ayarlar, tüm veri sürücüsü türlerinde son kullanıcıların değiştirebileceği sürücü şifreleme görevleri veya yapılandırma seçeneklerini yönetir.

- **Diğer disk şifrelemesi için uyarı**: Seçin **blok** başka bir disk şifreleme hizmeti cihazda uyarı istemini devre dışı. **Yapılandırılmadı** (varsayılan) ayarı, uyarının gösterilmesine izin verir.
    - **Azure AD katılımı sırasında şifrelemeyi etkinleştirmek standart kullanıcıların**: Seçeneğini belirlediğinizde **izin**, kullanıcının oturum açtığı zaman standart kullanıcıların/olmayanların BitLocker şifrelemesini etkinleştirebilir. Bu ayar, yalnızca Azure Active Directory'ye katılmış (Azure düzeltmesi) cihazlar için geçerlidir. **Yapılandırılmamış** cihazda BitLocker şifrelemesi yöneticilerinin yalnızca sağlar.
      
      Bu ayar, yalnızca Azure Active Directory'ye katılmış (Azure düzeltmesi) cihazlar için geçerlidir. Bu da gerektiren **diğer disk şifrelemesi için uyarı** ayarı ayarlanması **blok**.
- **Şifreleme yöntemlerini Yapılandır**: **Etkinleştirme** işletim sistemi, veri ve çıkarılabilir sürücüler için şifreleme algoritmalarını yapılandırmak için bu ayarı. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında BitLocker, varsayılan şifreleme yöntemi olarak XTS-AES 128 bit kullanır veya herhangi bir kurulum betiği tarafından belirtilen şifreleme yöntemini kullanır.
  - **İşletim sistemi sürücüleri için şifreleme**: İşletim sistemi sürücüleri için şifreleme yöntemini seçin. XTS-AES algoritmasını kullanmanızı öneririz.
  - **Sabit veri sürücüleri için şifreleme**: Sabit (yerleşik) veri sürücüleri için şifreleme yöntemini seçin. XTS-AES algoritmasını kullanmanızı öneririz.
  - **Çıkarılabilir veri sürücüleri için şifreleme**: Çıkarılabilir veri sürücüleri için şifreleme yöntemini seçin. Çıkarılabilir sürücü, Windows 10 çalıştırmayan cihazlarla kullanılıyorsa AES-CBC algoritmasını kullanmanızı öneririz.

### <a name="bitlocker-os-drive-settings"></a>BitLocker işletim sistemi sürücüsü ayarları
Aşağıdaki Windows 10 sürümlerinde desteklenir:

- Enterprise
- Eğitim
- Mobil
- Mobile Enterprise
- Professional

Bu ayarlar, belirli işletim sistemi veri sürücüleri için geçerlidir.

- **Başlangıçta ek kimlik doğrulaması**: Seçin **gerektiren** Güvenilir Platform Modülü (TPM) kullanımı dahil bilgisayar başlangıcı için kimlik doğrulama gereksinimlerini yapılandırmak için. TPM kullanan cihazlarda yalnızca temel seçenekleri yapılandırmak için bunu **Yapılandırılmadı** (varsayılan) olarak ayarlayın.
  - **Uyumlu olmayan TPM yongası ile BitLocker**: **Blok** (bir cihaz uyumlu bir TPM yongasına sahip olmadığında BitLocker'ı kullanarak devre dışı). **Yapılandırılmadı** olarak ayarlandığında kullanıcılar, uyumlu TPM yongası olmadan BitLocker kullanabilir. BitLocker bir parola veya başlangıç anahtarı gerektirebilir.
  - **Uyumlu TPM başlangıç**: İzin, değil izin ver veya TPM yongası gerektiren seçin.
  - **Uyumlu TPM başlangıç PIN'i**: İzin, değil izin ver veya TPM yongasıyla bir başlangıç PIN'i gerektir seçin. Başlangıç PIN’ini etkinleştirme, son kullanıcı etkileşimi gerektirir. 
  - **Uyumlu TPM başlangıç anahtarı**: İzin vermek için izin verme veya TPM yongasıyla bir başlangıç anahtarı gerektir seçin. Başlangıç anahtarını etkinleştirme, son kullanıcı etkileşimi gerektirir. 
  - **Uyumlu TPM başlangıç anahtarı ve PIN'i**: İzin, izin verme veya başlangıç anahtarı ve PIN'i TPM yongası ile kullanılmasını seçin. Başlangıç anahtarı ve PIN’i etkinleştirme, son kullanıcı etkileşimi gerektirir.
- **Minimum PIN uzunluğu**: **Etkinleştirme** TPM başlangıç PIN'inin en düşük uzunluğunu yapılandırmak için bu ayarı. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, kullanıcılar 6 ila 20 basamak arasında bir başlangıç PIN’i yapılandırabilir.
  - **En az karakter**: Başlangıç PIN'i için gereken karakter sayısını girin gelen **4**-**20**.
- **İşletim sistemi sürücüsünü kurtarma**: **Etkinleştirme** gerekli başlatma bilgileri kullanılamadığında nasıl BitLocker korumalı işletim sistemi denetlemek için bu ayarı kurtarma sürücüler. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, BitLocker kurtarma için varsayılan kurtarma seçenekleri desteklenir. Varsayılan olarak, bir DRA izin ve kurtarma seçeneklerini kurtarma parolası ve kurtarma anahtarı dahil olmak üzere kullanıcı tarafından seçilen kurtarma bilgilerini AD DS'ye yedeklenmiyor.
  - **Sertifika tabanlı veri kurtarma aracısı**: Ayarlandığında **blok**, BitLocker korumalı işletim sistemi sürücülerinde veri kurtarma aracısı kullanamazsınız. BitLocker korumalı işletim sistemi sürücülerinde veri kurtarma aracılarının kullanılabilmesini sağlayan bu ayarı etkinleştirmek için **Yapılandırılmadı** olarak ayarlayın.
  - **Kurtarma parolasının kullanıcı tarafından oluşturulması**: Kullanıcıların izin, gerekli veya 48 basamaklı kurtarma parolası oluşturmalarına izin verilip verilmeyeceğini, seçin.
  - **Kullanıcının kurtarma anahtarı oluşturması**: Kullanıcıların izin, gerekli veya 256 bitlik kurtarma anahtarı oluşturmalarına izin verilip verilmeyeceğini, seçin.
  - **BitLocker kurulum sihirbazında kurtarma seçeneklerini**: Kümesine **blok** böylece kullanıcılar görebilir ve kurtarma seçeneklerini değiştirin. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, kullanıcılar BitLocker’ı açtığında kurtarma seçeneklerini göremez ve değiştiremez.
  - **BitLocker kurtarma bilgilerinin AD DS'ye Kaydet**: Seçin **etkinleştirme** için Azure Active Directory (AAD) BitLocker kurtarma bilgilerini depolamak için. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, kurtarma bilgileri AAD’de depolanmaz.
  - **AD DS'ye depolanan BitLocker kurtarma bilgileri**: Azure AD'de depolanan BitLocker kurtarma bilgilerinin hangi bölümlerinin yapılandırın. Aşağıdakilerden birini seçin:
    - **Yedekleme kurtarma parolaları ve anahtar paketleri**
    - **Yalnızca yedekleme kurtarma parolaları**
  - **Store kurtarma bilgilerini AD DS'de BitLocker'ı etkinleştirmeden önce**: **Gerekli** BitLocker kurtarma bilgilerinin Azure Active Directory (AD) başarıyla depolanan sürece kullanıcıların BitLocker'ı açmasını engellemek için bu ayarı. **Yapılandırılmamış** kurtarma bilgilerinin Azure AD'de depolanan başarıyla değilse bile kullanıcıların BitLocker'ı Aç (varsayılan) sağlar.
- **Önyükleme öncesi kurtarma iletisi ve URL'sini**: **Etkinleştirme** iletiyi ve önyükleme anahtarı kurtarma ekranında görüntülenen URL'yi yapılandırmak için bu ayarı. **Yapılandırılmadı** (varsayılan) ayarı, bu özelliği devre dışı bırakır.
  - **Önyükleme öncesi kurtarma iletisi**: Önyükleme öncesi kurtarma iletisi kullanıcılara görüntüleme şeklini yapılandırın. Aşağıdakilerden birini seçin:
    - **Varsayılan kurtarma iletisi ve URL'sini kullan**
    - **Boş kurtarma iletisi ve URL'si kullan**
    - **Özel kurtarma iletisi kullan**
    - **Özel kurtarma URL'si kullan**

### <a name="bitlocker-fixed-data-drive-settings"></a>BitLocker sabit veri sürücüsü ayarları

Aşağıdaki Windows 10 sürümlerinde desteklenir:

- Enterprise
- Eğitim
- Mobil
- Mobile Enterprise
- Professional

**Ayarları**:

- **BitLocker tarafından korunmayan sabit veri sürücülerine yazma erişimi**: Kümesine **blok** BitLocker korumalı olmayan veri sürücüleri için salt okunur erişim vermek için. Zaman **yapılandırılmadı** (varsayılan), burada ait okuma ve BitLocker korumalı olmayan veri sürücülerine yazma erişimi.
- **Sabit sürücü kurtarma**: **Etkinleştirme** denetlemek için bu ayarı kullanılabilir gerekli başlatma bilgileri olmadığında BitLocker korumalı sabit sürücülerin kurtarma nasıl. **Yapılandırılmadı** (varsayılan) ayarı, bu özelliği devre dışı bırakır.
  - **Veri Kurtarma Aracısı**: **Blok** BitLocker korumalı ile veri kurtarma aracısının kullanımını sabit sürücüler İlke Düzenleyicisi. **Yapılandırılmadı** (varsayılan) ayarı, BitLocker ile korunan sabit sürücülerle veri kurtarma aracılarının kullanımını etkinleştirir.
  - **Kurtarma parolasının kullanıcı tarafından oluşturulması**: Kullanıcıların izin verilip, gerekli veya 48 basamaklı kurtarma parolası oluşturmalarına izin verilip verilmeyeceğini olup olmadığını yapılandırın.  
  - **Kullanıcının kurtarma anahtarı oluşturması**: Kullanıcıların izin verilip, gerekli veya 256 bitlik kurtarma anahtarı oluşturmalarına izin verilip verilmeyeceğini olup olmadığını yapılandırın.
  - **BitLocker kurulum sihirbazında kurtarma seçeneklerini**: Kümesine **blok** böylece kullanıcılar görebilir ve kurtarma seçeneklerini değiştirin. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, kullanıcılar BitLocker’ı açtığında kurtarma seçeneklerini göremez ve değiştiremez.
  - **BitLocker kurtarma bilgilerinin Azure Active Directory'ye kaydetme**: Seçin **etkinleştirme** BitLocker kurtarma bilgilerinin Azure Active Directory (Azure AD) depolamak için. Zaman **yapılandırılmadı** (varsayılan), Kurtarma bilgilerini Azure AD'de depolanan değil.
  - **Azure Active Directory'ye depolanan BitLocker kurtarma bilgileri**: Azure AD'de depolanan BitLocker kurtarma bilgilerinin hangi bölümlerinin yapılandırın. Seçenekleriniz şunlardır:
    - **Yedekleme kurtarma parolaları ve anahtar paketleri**
    - **Yalnızca yedekleme kurtarma parolaları**
  - **Store kurtarma bilgilerinin Azure Active Directory'de BitLocker'ı etkinleştirmeden önce**: **Gerekli** BitLocker kurtarma bilgilerinin Azure AD'de depolanan başarıyla sürece kullanıcıların BitLocker'ı açmasını engellemek için bu ayarı. **Yapılandırılmamış** kurtarma bilgilerinin Azure AD'de başarıyla depolanmadı bile kullanıcıların BitLocker'ı Aç (varsayılan) sağlar.

### <a name="bitlocker-removable-data-drive-settings"></a>BitLocker çıkarılabilir veri sürücüsü ayarları

Aşağıdaki Windows 10 sürümlerinde desteklenir:

- Enterprise
- Eğitim
- Mobil
- Mobile Enterprise
- Professional

**Ayarları**:

- **BitLocker tarafından korunmayan çıkarılabilir veri sürücülerine yazma erişimi**: Kümesine **blok** BitLocker korumalı olmayan veri sürücüleri için salt okunur erişim vermek için. Zaman **yapılandırılmadı** (varsayılan), burada ait okuma ve BitLocker korumalı olmayan veri sürücülerine yazma erişimi.
  - **Başka bir kuruluşta yapılandırılmış cihazlara yazma erişimi**: **Blok** başka bir kuruluşta yapılandırılmış cihazlara yazma erişimi verir. **Yapılandırılmamış** (varsayılan) ayarı, yazma erişimini reddeder.

## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard

Aşağıdaki Windows 10 sürümlerinde desteklenir:

- Ana Sayfası
- Professional
- İş
- Enterprise
- Eğitim
- Mobil
- Mobile Enterprise

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

#### <a name="rules-to-protect-against-ransomware"></a>Fidye Yazılımlarına karşı korunma kuralları
- **Gelişmiş fidye yazılımı koruması**

> [!TIP]
> [Windows Defender Exploit Guard ile saldırı yüzeylerini azaltma](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard), bu kurallar hakkında daha fazla ayrıntı sağlar.

#### <a name="attack-surface-reduction-exceptions"></a>Saldırı Yüzeyi Azaltma özel durumları

- **Dosyaları ve saldırıyı tutulacak klasörü yüzeyi azaltma kurallarından**: Yapılandırılan kurallardan muaf tutulacak konumlar listesi içeri aktarma/ekleyin.

> [!IMPORTANT]
> Uygun yükleme ve yürütme Win32 LOB uygulamalarını izin vermek için kötü amaçlı yazılımdan koruma ayarları aşağıdaki dizinlerin taranmasını dışlamanız gerekir:<p>
> **X64 istemci makineleri**:<br>
> *C:\Program dosyaları (x86) \Microsoft Intune Yönetimi Extension\Content*<br>
> *C:\windows\IMECache*
>  
> **X86 istemci makineleri**:<br>
> *C:\Program Files\Microsoft Intune Yönetimi Extension\Content*<br>
> *C:\windows\IMECache*

### <a name="controlled-folder-access"></a>Denetlenen klasör erişimi

Önemli verileri fidye yazılımı gibi kötü amaçlı uygulama ve tehditlerden korumaya yardımcı olun.

- **Klasör koruma**: Dosya ve klasörleri tarafından kötü amaçlı uygulamalar istenmeyen değişikliklerden koruyun. Bir **Korumalı dosyalara erişimi olan uygulamalar listesi** içeri aktarabilir veya bu uygulamaları el ile ekleyebilirsiniz. Ayrıca bir **Korunması gereken ek klasörler listesi** yükleyebilir veya bu klasörleri el ile ekleyebilirsiniz.

### <a name="network-filtering"></a>Ağ filtreleme

- **Ağ koruması**: Giden bağlantılar, düşük itibarlı IP adreslerini veya etki alanları için herhangi bir uygulamadan korur. Amaç, kimlik avı kuşku verici, yararlanma barındırma siteler ve Internet üzerindeki kötü amaçlı içerik uygulamalardan erişimi olan son kullanıcıların korunmasını sağlamaktır. Ayrıca, üçüncü taraf tarayıcılar'in tehlikeli sitelere bağlanmasını engeller.

  Seçenekleriniz şunlardır:

  - **Yapılandırılmadı** (varsayılan) ayarı, bu özelliği devre dışı bırakır. Kullanıcılar ve uygulamalar tehlikeli etki alanlarına bağlanmasını engellenmez. Yöneticiler, Windows Defender Güvenlik Merkezi'nde bu etkinlik göremez.
  - **Etkinleştirme** ağ koruması blokları kullanıcıları ve uygulamaları tehlikeli etki alanlarına bağlanmasını etkinleştirir. Yöneticiler, Windows Defender Güvenlik Merkezi'nde bu etkinliği görebilirsiniz.
  - **Yalnızca denetim**: Kullanıcılar ve uygulamalar tehlikeli etki alanlarına bağlanmasını engellenmez. Yöneticiler, Windows Defender Güvenlik Merkezi'nde bu etkinliği görebilirsiniz.

  [Defender/EnableNetworkProtection CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection)

### <a name="exploit-protection"></a>Exploit protection

Exploit protection'ı kullanmak için istediğiniz sistem ve uygulama risk azaltma ayarlarını içeren bir XML dosyası oluşturun. Bunun için iki yöntem vardır:

 1. PowerShell: Bir veya daha fazla Get-ProcessMitigation, Set-ProcessMitigation ve ConvertTo-ProcessMitigationPolicy PowerShell cmdlet'lerini kullanın. Cmdlet'ler risk azaltma ayarlarını yapılandırır ve bunların XML gösterimini dışarı aktarır.

 2. Windows Defender Güvenlik Merkezi kullanıcı Arabirimi: Windows Defender Güvenlik Merkezi'nde uygulama & tarayıcı denetimine tıklayın ve sonra Exploit Protection'ı bulmak için gelen ekranın altına kaydırın. Önce Sistem ayarları ve Program ayarları sekmelerini kullanarak risk azaltma ayarlarını yapılandırın. Daha sonra bunların bir XML temsilini dışarı aktarmak için ekranın altında yer alan Dışarı aktarma ayarları bağlantısını bulun.

Bellek, denetim akışı ve ilke kısıtlamalarını yapılandırmanıza izin veren bir XML dosyasını karşıya yükleyerek **Kullanıcıların Exploit Protection arabirimini düzenlemesi**’ni engelleyin. XML dosyasındaki ayarlar bir uygulamanın açıklarından yararlanılmasını engellemek için kullanılabilir. **Yapılandırılmadı** (varsayılan) ayarı, özel bir yapılandırma göndermez. 

## <a name="windows-defender-application-control"></a>Windows Defender Uygulama Denetimi

Aşağıdaki Windows 10 sürümlerinde desteklenir:

**Mobil Cihaz Yönetimi (MDM)**: 
- Professional
- İş
- Enterprise
- Eğitim
- Mobil
- Mobile Enterprise

**Grup ilkesi yönetimi**: 
- Enterprise

Windows Defender Uygulama Denetimi tarafından denetlenmesi gereken veya çalıştırılmasına güvenilen ek uygulamaları seçmek için **Uygulama denetimi kod bütünlüğü ilkelerini** kullanın. Windows mağazasındaki Windows bileşenlerinin ve tüm uygulamaların çalıştırılmasına otomatik olarak güvenilir.

Uygulamalar, **yalnızca denetimli** modda çalıştırıldığında engellenmez. **Yalnızca denetimli** modu, tüm olayları yerel istemci günlüklerine kaydeder.

Uygulama Denetimi etkinleştirildiğinde, yalnızca modun **Zorla**’dan **Yalnızca denetimli**’ye değiştirilmesiyle devre dışı bırakılabilir. Modun **Zorla**’dan **Yapılandırılmadı**’ya değiştirilmesi, Uygulama Denetimi’nin atanmış cihazlarda zorlanmaya devam etmesiyle sonuçlanır.

## <a name="windows-defender-credential-guard"></a>Windows Defender Credential Guard

Aşağıdaki Windows 10 sürümlerinde desteklenir:

- Enterprise

Windows Defender Credential Guard kimlik bilgileri hırsızlığı saldırılarına karşı korur. Gizli dizileri yalnızca ayrıcalıklı sistem yazılımlarının erişebileceği şekilde yalıtır.

**Credential Guard** ayarları şunlardır:

- **Devre dışı**: Credential Guard, daha önce ile açılmışsa uzaktan kapatır **UEFI kilidi olmadan etkin** seçeneği.

- **UEFI kilidiyle etkinleştir**: Credential Guard, uzaktan kayıt defteri anahtarını kullanarak devre dışı bırakılamaz veya Grup İlkesi.

    > [!NOTE]
    > Bu ayarı kullanırsanız ve daha sonra Credential Guard'ı devre dışı bırakmak isterseniz, Grup İlkesi'ni **Devre Dışı** olarak ayarlamalısınız. Ayrıca, UEFI yapılandırma bilgilerini her bilgisayardan fiziksel olarak temizleyin. UEFI yapılandırması devam ettiği sürece, Credential Guard etkindir.

- **UEFI kilidi olmadan etkinleştir**: Credential Guard ' ı uzaktan Grup İlkesi'ni kullanarak devre dışı bırakılmasına olanak verir. Bu ayarı kullanan cihazların Windows 10 sürüm 1511'i veya daha yeni bir sürümü çalıştırıyor olması gerekir.

Credential Guard'ı etkinleştirdiğinizde, aşağıdaki gerekli özellikler de etkinleştirilir:

- **Sanallaştırma tabanlı güvenlik** (VBS): Bir sonraki başlatma işlemi sırasında açar. Sanallaştırma tabanlı güvenlik, güvenlik hizmetlerine destek sağlamak için Windows Hiper Yöneticisi'ni kullanır.
- **Güvenli önyükleme dizini bellek erişimi ile**: Güvenli Önyükleme ve doğrudan bellek erişimi (DMA) korumaları VBS açar. DMA korumaları donanım desteği gerektirir ve yalnızca doğru yapılandırılmış cihazlarda etkinleştirilir.

## <a name="windows-defender-security-center"></a>Windows Defender Güvenlik Merkezi

Aşağıdaki Windows 10 sürümlerinde desteklenir:

- Ana Sayfası
- Professional
- İş
- Enterprise
- Eğitim
- Mobil
- Mobile Enterprise

Windows Defender Güvenlik Merkezi, diğer tüm özelliklerden ayrı bir uygulama veya işlem olarak çalışır. İşlem Merkezi aracılığıyla bildirimler gösterir. Durumunu görmek ve bazı yapılandırmalar için özelliklerin her birini çalıştırmak için bir Toplayıcı veya tek bir yerde görür. [Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) belgelerinden daha fazla bilgi edinin.

#### <a name="windows-defender-security-center-app-and-notifications"></a>Windows Defender Güvenlik Merkezi uygulaması ve bildirimleri

Windows Defender Güvenlik Merkezi uygulamasının çeşitli alanlarına son kullanıcı erişimini engelleyin. Bir bölümü gizlemek, bu bölümle ilgili bildirimleri de engeller.

- **Virüs ve tehdit koruması**
- **Cihaz performans ve sistem durumu**
- **Güvenlik duvarı ve ağ koruması**
- **Uygulama ve tarayıcı denetimi**
- **Aile seçenekleri**
- **Uygulamanın görüntülenen alanlarından bildirimler**: Son kullanıcılara gösterilecek bildirimleri seçin. Kritik olmayan bildirimlere, Windows Defender Antivirus etkinliğinin özetleri ve taramalar tamamlandığında verilen bildirimler dahildir. Diğer tüm bildirimler kritik olarak kabul edilir.

#### <a name="it-contact-information"></a>BT iletişim bilgileri

Windows Defender Güvenlik Merkezi uygulaması ve uygulama bildirimlerinde gösterilecek BT iletişim bilgilerini sağlayın. **Uygulamada ve bildirimlerde göster**, **Yalnızca uygulamada göster**, **Yalnızca bildirimlerde göster** veya **Gösterme** seçeneklerinden birini seçebilirsiniz. **BT kuruluş adı** ile aşağıdaki iletişim seçeneklerinden en az birini girin:

- **BT departmanı telefon numarası veya Skype kimliği**
- **BT departmanı e-posta adresi**
- **BT destek web sitesi URL’si**

## <a name="local-device-security-options"></a>Yerel cihaz güvenliği seçenekleri

Aşağıdaki Windows 10 sürümlerinde desteklenir:
 
- Ana Sayfası
- Professional
- İş
- Enterprise
- Eğitim

Windows 10 cihazlarında yerel güvenlik ayarlarını yapılandırmak için bu seçenekleri kullanın.

### <a name="accounts"></a>Hesaplar

- **Yeni Microsoft hesapları Ekle**: Kümesine **blok** kullanıcıların, cihaz için yeni Microsoft hesapları eklemesini engellemek için. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, kullanıcılar cihazda Microsoft hesabı kullanabilir.
- **Parola olmadan uzaktan oturum açma**: **Blok** yalnızca yerel hesapları cihazın klavye kullanarak oturum açmanız, boş parolalı sağlar. **Yapılandırılmadı** (varsayılan) ayarı, boş parolası olan yerel hesapların fiziksel cihaz dışındaki konumlardan oturum açmasına izin verir.

#### <a name="admin"></a>Yönetici

- **Yerel yönetici hesabı**: Kümesine **etkin** yerel yönetici hesabı izin vermek için. Yerel yönetici hesabını devre dışı bırakmak için **Yapılandırılmadı** (varsayılan) olarak ayarlayın.
- **Yönetici hesabını yeniden adlandır**: Yönetici hesabı için güvenlik tanımlayıcısı (SID) ile ilişkilendirilecek farklı bir hesap adı tanımlayın.

#### <a name="guest"></a>Konuk

- **Konuk hesabı**: Kümesine **etkin** yerel Konuk hesabı izin vermek için. Yerel guest hesabını devre dışı bırakmak için **Yapılandırılmadı** (varsayılan) olarak ayarlayın.
- **Guest hesabını yeniden adlandır**: Konuk hesabı için güvenlik tanımlayıcısı (SID) ile ilişkilendirilecek farklı bir hesap adı tanımlayın.

### <a name="devices"></a>Cihazlar

- **Oturum açma olmadan cihazı çıkar**: Kümesine **blok** kullanıcılar basabilirsiniz için yerleşik taşınabilir cihazın fiziksel çıkarma cihaz güvenli bir şekilde ayırmak düğmesine. **Yapılandırılmadı** (varsayılan) ayarı, cihazı çıkarmak için kullanıcının cihazda oturum açmasını ve izin almayı gerektirir.
- **Paylaşılan yazıcılar için yazıcı sürücülerini yükle**: Zaman **etkin**, paylaşılan bir yazıcıya bağlanan bir parçası olarak herhangi bir kullanıcı bir yazıcı sürücüsü yükleyebilirsiniz. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, paylaşılan yazıcıya bağlanma işlemi kapsamında yalnızca yöneticiler yazıcı sürücüsü yükleyebilir.
- **CD-ROM erişimini yerel etkin kullanıcıya kısıtla**: Zaman **etkin**, yalnızca etkileşimli olarak oturum açmış kullanıcının CD-ROM medyasına kullanabilir. Bu ilke etkinse ve kimse etkileşimli olarak oturum açmamışsa CD-ROM’a ağ üzerinden erişilir. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, herkesin CD-ROM’a erişimi olur.
- **Biçimlendirme ve çıkarılabilir medyayı çıkarma**: Kimlerin Çıkarılabilir NTFS ortamı biçimlendirme ve çıkarma izni olduğunu tanımlayın:
  - **Yapılandırılmadı**
  - **Yöneticiler**
  - **Yöneticiler ve Yetkili Kullanıcılar**
  - **Yöneticiler ve Etkileşimli Kullanıcılar**

### <a name="interactive-logon"></a>Etkileşimli Oturum Açma

- **Ekran koruyucu etkinleşmeden dakika kilit ekranında işlem yapılmadan geçen**: En fazla dakika etkin olmama ekran koruyucu başlatana kadar etkileşimli masaüstünün oturum açma ekranı girin.
- **Oturum açmak CTRL + ALT + DEL gerektir**: Kümesine **etkinleştirme** için CTRL + ALT + DEL tuşlarına, kullanıcıların oturum açmak gerekli değildir. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, kullanıcıların Windows’da oturum açmaları için CTRL+ALT+DEL tuşlarına basmaları gerekir.
- **Akıllı kart kaldırma davranışı**: Akıllı kart oturum açan kullanıcı için akıllı kart okuyucusundan kaldırıldığında ne olacağını belirler. Seçenekleriniz şunlardır:

  - **İş istasyonu kilitleme**: Akıllı kart kaldırıldığında iş istasyonu kilitlenmiş durumda. Bu seçenek kullanıcıların akıllı kartlarını alarak alandan uzaklaşmasına ve yine de korumalı oturumu sürdürmesine olanak tanır.
  - **Oturum kapatmaya zorla**: Akıllı kart kaldırıldığında kullanıcı otomatik olarak kapatılır.
  - **Uzak Masaüstü Hizmetleri oturumu bağlantısını kes**: Akıllı kart kaldırma işlemi, kullanıcının oturumunu günlüğe kaydetmeden oturumunun bağlantısını keser. Bu seçenek kullanıcının daha sonra yeniden oturum açmak zorunda kalmadan akıllı kartı takıp oturumu devam ettirmesine veya akıllı kart okuyucuyla donatılmış başka bir bilgisayarda bunu yapmasına olanak tanır. Yerel bir oturum söz konusuysa, bu ilke İş İstasyonunu Kilitle ilkesiyle tam olarak aynı işlevi görür.

    [LocalPoliciesSecurity seçenekleri](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-interactivelogon-smartcardremovalbehavior) başlığı altında daha fazla ayrıntı sağlanır.

#### <a name="display"></a>Görüntüle

- **Kilit ekranında kullanıcı bilgileri**: Oturum kilitlendiğinde görüntülenen kullanıcı bilgilerini yapılandırın. Yapılandırılmazsa, kullanıcı görünen adı, etki alanı ve kullanıcı adı gösterilir.
  - **Yapılandırılmadı**  
  - **Kullanıcı görünen adı, etki alanı ve kullanıcı adı**
  - **Yalnızca kullanıcı görünen adı**
  - **Kullanıcı bilgilerini görüntüleme**
- **Son oturum açmış kullanıcıyı Gizle**: **Etkinleştirme** kullanıcı adını gizler. **Yapılandırılmadı** (varsayılan) ayarı, kullanıcı adını gösterir.
- **Oturum açma sırasında kullanıcı adını gizle**: **Etkinleştirme** kullanıcı adını gizler. **Yapılandırılmadı** (varsayılan) ayarı, kullanıcı adını gösterir.
- **Oturum açma ileti başlığı**: Oturum açan kullanıcılar için ileti başlığı ayarlayın.
- **Oturum açma ileti metni**: Oturum açan kullanıcılar için ileti metni ayarlayın.

### <a name="network-access-and-security"></a>Ağ erişimi ve güvenlik

- **Adlandırılmış kanallara ve paylaşımlarına anonim erişim**: **Yapılandırılmamış** (varsayılan), paylaşımı ve adlandırılmış yöneltme ayarlarına anonim erişimi kısıtlıyor. Anonim olarak erişilebilen ayarlar için geçerlidir.
- **SAM hesaplarının anonim numaralandırmasına**: **İzin** anonim kullanıcıların SAM hesaplarını listeleme. Windows anonim kullanıcılara etki alanı hesaplarının ve ağ paylaşımlarının adlarını listeleme izni verir.
- **SAM hesaplarının ve paylaşımların anonim listelenmesi**: **Yapılandırılmamış** anonim kullanıcıların etki alanı hesaplarının adlarını numaralandırır ve ağ paylaşımları (varsayılan) anlamına gelir. SAM hesaplarının ve paylaşımlarının anonim listelenmesini önlemek için **Engelle** olarak ayarlayın.
- **Parola değişiminde depolanan LAN Manager karma değerini**: Sonraki parola değişiminde tercih **izin** LAN Yöneticisi (yeni parola karması değerini depolamak için LM). **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, karma değer depolanmaz.
- **PKU2U kimlik doğrulama isteklerini**: **Blok** çevrimiçi kimlikleri kullanmak için PKU2U kimlik doğrulama isteklerini cihaz. **Yapılandırılmadı** (varsayılan) ayarı bu isteklere izin verir.
- **SAM uzak RPC bağlantılarını kısıtla**: Kümesine **izin** kullanıcılar ve gruplar için Güvenlik Hesapları Yöneticisi (kullanıcı hesapları ve parolaları depolayan SAM), uzak RPC çağrıları yapmasını engellemek için. **İzin** açıkça veya kullanıcılar ve gruplar bu uzak çağrı yapmak için reddetmek için varsayılan güvenlik tanımlayıcısı tanım dili (SDDL) dizesi değiştirmek de sağlar. **Yapılandırılmamış** (varsayılan), varsayılan güvenlik tanımlayıcısı kullanır ve kullanıcılar ve grupların SAM'ye uzak RPC çağrı yapmak izin verebilir.
  - **Güvenlik tanımlayıcısı**

### <a name="recovery-console-and-shutdown"></a>Kurtarma konsolu ve kapatma

- **Kapatma sırasında sanal bellek disk belleği dosyası**: Kümesine **etkinleştirme** cihaz kapatıldığında sanal bellek disk belleği dosyasını temizleyin. **Yapılandırılmadı** ayarı, sanal belleği temizlemez.
- **Üzerinde oturum kapatma**: **Blok** Windows oturum açma ekranı Kapat seçeneğini gizler. Kullanıcıların cihazda oturum açıp ve ardından cihazı kapatması gerekir. **Yapılandırılmamış** (varsayılan) kullanıcılar Windows oturum açma ekranı cihazı kapatmasına izin verir.

### <a name="user-account-control"></a>Kullanıcı hesap denetimi

- **Güvenli konum olmadan UIA bütünlüğü**: Ayarlandığında **blok**, dosya sistemindeki güvenli bir konumda uygulamalar yalnızca UIAccess bütünlük ile çalıştırın. **Yapılandırılmadı** (varsayılan) ayarı, uygulamaların dosya sistemindeki güvenli konumlarda bulunmasa bile UIAccess bütünlüğüyle çalıştırılmasına izin verir.
- **Dosya ve kayıt defteri yazma hatalarını kullanıcı başına konumlarında sanal olarak oluştur**: Ayarlandığında **etkin**, korumalı veri yazan uygulamaları konumları başarısız. Ayarlandığında **yapılandırılmadı** (varsayılan), uygulama yazma hatalarının en yönlendirilir çalışma zamanında tanımlanan kullanıcı konumlara kayıt defteri ve dosya sistemi için.
- **Yalnızca imzalı ve doğrulanmış yürütülebilir dosyaları Yükselt**: Kümesine **etkin** çalıştırılmadan önce bir yürütülebilir dosya için PKI sertifika yolu doğrulamasını zorunlu kılmak için. Bir yürütülebilir dosyanın çalışabilmesi için PKI sertifika yolu doğrulamasını zorlamamak için **Yapılandırılmadı** olarak ayarlayın.

#### <a name="uia-elevation-prompt-behavior-settings"></a>UIA yükseltme istemi davranışı ayarları

- **Yöneticiler için yükseltme istemi**: Yönetici Onay Modu'nda yöneticiler için yükseltme isteminin davranışını tanımlayın:
  - **İstem olmadan yükselt**
  - **Güvenli masaüstünde kimlik bilgileri iste**
  - **Güvenli masaüstünde onay iste**
  - **Kimlik bilgileri iste**
  - **Onay iste**
  - **Yapılandırılmamış**: Windows dışı ikililer için onay iste
- **Standart kullanıcılar için yükseltme isteminin**: Standart kullanıcılar için yükseltme isteminin davranışını tanımlayın:
  - **Yükseltme isteklerini otomatik olarak reddet**
  - **Güvenli masaüstünde kimlik bilgileri iste**
  - **Yapılandırılmamış**: Kimlik bilgisi istemi
- **Yükseltme istemlerini kullanıcının etkileşimli masaüstüne yönlendir**: **Etkinleştirme** şekilde tüm yükseltme isteklerinin güvenli masaüstü etkileşimli kullanıcının masaüstüne geçin. Yöneticiler ve standart kullanıcılar için herhangi bir istem davranışı ilke ayarı kullanılır. **Yapılandırılmadı** (varsayılan) ayarı, yöneticiler ve standart kullanıcılar için istem davranışı ilke ayarlarına bakılmaksızın tüm yükseltme isteklerini güvenli masaüstüne gitmeye zorlar.
- **Uygulama yüklemeleri için yükseltilmiş istem**: Ayarlandığında **etkin**, uygulama yükleme paketleri algılandı veya yükseltme istenir. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, bir uygulama paketi yükseltilmiş ayrıcalıklar gerektirdiğinde kullanıcıdan yönetici kullanıcı adı ve parolası istenir.
- **Güvenli Masaüstü olmadan UIA yükseltme istemi**: **Etkinleştirme** UIAccess uygulamalarının güvenli masaüstü kullanmadan, yükseltme isteminde bulunmasına izin vermek için. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, yükseltme istemleri bir güvenli masaüstü kullanır.

#### <a name="admin-approval-mode-settings"></a>Yönetici Onay Modu ayarları

- **Yönetici Onay Modu için yerleşik yönetici**: **Etkin** yönetici onay modu kullanmak için yerleşik Yönetici hesabını sağlar. Ayrıcalık gerektiren herhangi bir işlem, kullanıcıdan işlemi onaylamasını ister. **Yapılandırılmadı** (varsayılan) ayarı, tam yönetici ayrıcalıkları olan tüm uygulamaları çalıştırır.
- **Tüm yöneticileri Yönetici Onay Modu'nda Çalıştır**: Kümesine **etkin** UAC ilke ayarlarının ilgili yönetici onay modu ve tüm devre dışı bırakın. **Yapılandırılmadı** (varsayılan) ayarı, Yönetici Onay Modunu etkinleştirir.

### <a name="microsoft-network-client"></a>Microsoft Ağ İstemcisi

- **İletişimleri dijital olarak imzala (sunucu onaylarsa)**: SMB istemcisinin SMB paket imzalamasını görüşür olmadığını belirler. **Yapılandırılmadı** veya etkin (varsayılan) olarak ayarlandığında Microsoft ağ istemcisi, sunucudan oturum kurulumunda SMB paket imzalama işlemini çalıştırmasını ister. Sunucuda paket imzalama etkinleştirilirse, paket imzalama anlaşması yapılır. **Devre dışı bırak** olarak ayarlandığında, SMB istemcisi hiçbir zaman SMB paket imzalama anlaşması yapmaz.
- **Üçüncü taraf SMB sunucularına şifrelenmemiş parola gönder**: Ayarlandığında **etkinleştirme**, sunucu ileti bloğu (SMB) yeniden yönlendiricisinin doğrulama sırasında parola şifrelemesini desteklemeyen Microsoft olmayan SMB sunucularına düz metin parolalar gönderebilirsiniz. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, parolalar şifrelenir.

### <a name="microsoft-network-server"></a>Microsoft Ağ Sunucusu

- **İletişimleri dijital olarak imzala (istemci kabul ederse)**: SMB sunucusu imzalaması isteyen istemcilerle görüşür olmadığını belirler. **Etkinleştir** olarak ayarlandığında, Microsoft ağ sunucusu istemci tarafından istendiği gibi SMB paket imzalama anlaşması yapar. Başka bir deyişle, istemcide paket imzalama etkinleştirildiyse paket imzalama anlaşması yapılır. **Yapılandırılmadığında** veya devre dışı bırakıldığında (varsayılan), SMB istemcisi hiçbir zaman SMB paket imzalama anlaşması yapmaz.
- **İletişimleri dijital olarak imzala (her zaman)**: SMB sunucu bileşeni tarafından paket imzalama gerekip gerekmediğini belirler. **Etkinleştir** olarak ayarlandığında, Microsoft ağ istemcisi SMB paket imzalamayı kabul etmediği sürece Microsoft ağ sunucusu istemciyle iletişim kurmaz. **Yapılandırılmadı** veya Devre Dışı (varsayılan) olarak ayarlandığında, istemciyle sunucu arasında SMB paket imzalama anlaşması yapılır.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Ardından, [profili atama](device-profile-assign.md), ve [atamanın durumunu izlemenize](device-profile-monitor.md).

Uç nokta koruma ayarlarını yapılandırın [macOS](endpoint-protection-macos.md) cihazlar.
