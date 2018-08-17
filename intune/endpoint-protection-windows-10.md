---
title: Microsoft Intune - Azure’da Windows 10 cihazlara Endpoint Protection ekleme | Microsoft Docs
description: 'Windows 10 cihazlarda Windows Defender’ı etkinleştirmek için Endpoint Protection kullanma veya yapılandırma özelliği şunları içerir: Application Guard, Güvenlik Duvarı, SmartScreen, şifreleme ve BitLocker, Exploit Guard, Uygulama Denetimi, Güvenlik Merkezi ve Microsoft Intune’daki yerel cihazlarda güvenlik.'
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cc378a4f484852d84943b4d1094b71df5b7a530d
ms.sourcegitcommit: 006fa8dd4d605e2873fba6e3a965ef794d6f3764
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36945501"
---
# <a name="endpoint-protection-settings-for-windows-10-and-later-in-intune"></a>Intune’da Windows 10 (ve sonrası) için Endpoint Protection ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Endpoint Protection profili, Windows 10 cihazlarda BitLocker ve Windows Defender gibi güvenlik özelliklerini denetlemenize izin verir.

Bu makaledeki bilgileri kullanarak Endpoint Protection profilleri oluşturun. Windows Defender Virüsten Koruma’yı yapılandırmak için bkz. [Windows 10 Cihaz Kısıtlamaları](device-restrictions-windows-10.md#windows-defender-antivirus). 

## <a name="windows-defender-application-guard"></a>Windows Defender Application Guard

Aşağıdaki Windows 10 sürümlerinde desteklenir:

- Kurumsal 
- Professional

Microsoft Edge kullanırken Windows Defender Application Guard, ortamınızı kuruluşunuz tarafından güvenilir olarak tanımlanmayan sitelerden korur. Kullanıcılar, yalıtılmış ağ sınırı listenizde olmayan siteleri ziyaret ettiğinde siteler Hyper-V sanal gözatma oturumunda açılır. Güvenilen siteler, Cihaz Yapılandırması içinde yapılandırılabilen bir ağ sınırı tarafından tanımlanır.

Application Guard yalnızca Windows 10 (64 bit) cihazlar için kullanılabilir. Bu profili kullanmak, Application Guard’ı etkinleştirmek için bir Win32 bileşeni yükler.

- **Application Guard**: Onaylanmamış siteleri Hyper-V sanallaştırılmış gözatma kapsayıcısında açan bu özelliği açmak için **Etkinleştir** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında tüm siteler (onaylı veya onaysız) cihazda açılır.
- **Pano davranışı**: Yerel bilgisayar ile Application Guard sanal tarayıcısı arasında hangi kopyala/yapıştır eylemlerine izin verileceğini seçin.
- **Kuruluş sitelerinde harici içerik**: Onaylanmamış web sitelerine ait içeriklerin yüklenmesini önlemek için **Engelle** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında cihazda kuruluşa ait olmayan siteler açılır.
- **Sanal tarayıcıdan yazdır**: PDF, XPS, yerel yazıcılar ve/veya ağ yazıcılarının sanal tarayıcı içeriklerini yazdırmasına izin vermek için **İzin ver** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) ayarı, tüm yazdırma özelliklerini devre dışı bırakır.
- **Günlük topla**: Bir Application Guard gözatma oturumunda gerçekleşen olaylara ait günlükleri toplamak için **İzin Ver** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) ayarı, gözatma oturumunda günlük toplamaz.
- **Kullanıcı tarafından oluşturulan tarayıcı verilerini koru**: **İzin Ver** ayarı, bir Application Guard sanal gözatma oturumunda oluşturulan kullanıcı verilerini (parolalar, favoriler ve tanımlama bilgileri gibi) kaydeder. **Yapılandırılmadı** (varsayılan) ayarı, cihaz yeniden başlatıldığında veya bir kullanıcı oturumu kapadığında kullanıcının indirdiği dosya ve verileri atar.
- **Grafik hızlandırma**: Bir sanal grafik işleme birimi erişimi edinerek grafik açısından yoğun web sitelerini ve videoları daha hızlı yüklemek için **Etkinleştir** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) ayarı, grafik için cihazın CPU’sunu kullanır; sanal grafik işleme birimini kullanmaz.
- **Dosyaları konak dosya sistemine indir**: Kullanıcıların sanallaştırılmış tarayıcıdan konak işletim sistemine dosya indirebilmesi için **Etkinleştir** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) ayarı, cihazdaki dosyaları yerel olarak tutar ve konak dosya sistemine indirmez.

## <a name="windows-defender-firewall"></a>Windows Defender Güvenlik Duvarı

Aşağıdaki Windows 10 sürümlerinde desteklenir:
- Giriş
- Professional
- İşletme
- Kurumsal
- Eğitim
- Mobil
- Mobile Enterprise

### <a name="global-settings"></a>Genel ayarlar

Bu ayarlar tüm ağ türlerine uygulanabilir.

- **Dosya Aktarım Protokolü**: Durum bilgisi olan FTP’leri devre dışı bırakmak için **Engelle** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında güvenlik duvarı, durum bilgisi olan FTP filtrelemesi yaparak ikincil bağlantılara izin verir.
- **Silmeden önce güvenlik ilişkilendirme boşta kalma süresi**: Güvenlik ilişkilendirmeleri, *n* saniye boyunca hiçbir ağ trafiği algılanmadığında silinir. Boşta kalma süresini saniye cinsinden girin.
- **Önceden paylaşılan anahtar kodlaması**: UTF-8 kullanarak önceden paylaşılan anahtar kullanmak için **Etkinleştir** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) ayarı, yerel depo değerini kullanır.
- **IPsec muafiyetleri**: Aşağıdakiler dahil olmak üzere bazı trafikleri IPsec’ten muaf olacak şekilde yapılandırın:
  - **Komşu bulma IPv6 ICMP türü kodlar**
  - **ICMP**
  - **Yönlendirici bulma IPv6 ICMP türü kodlar**
  - **Hem IPv4 hem de IPv6 DHCP ağ trafiği**
- **Sertifika iptal listesi doğrulaması**: **CRL doğrulamasını devre dışı bırak**, **CRL doğrulaması yalnızca sertifika iptal edildiğinde başarısız olsun** ve **Bir hata ile karşılaşıldığında CRL doğrulaması başarısız olsun** ayarları dahil olmak üzere sertifika iptal listesi doğrulamasının nasıl uygulanacağını belirleyin.
- **Mümkün olduğunda kimlik doğrulama kümesini anahtar modülüne göre eşleştir**: Anahtar oluşturma modüllerinin yalnızca desteklemediği kimlik doğrulaması paketlerini yoksaymak ZORUNDA kalması için **Etkinleştir** olarak ayarlayın. **Yapılandırılmadı** olarak ayarlandığında, anahtar oluşturma modülleri kümede belirtilen kimlik doğrulaması paketlerinin tamamını desteklemiyorsa bütün kimlik doğrulaması kümesini yoksaymak ZORUNDA kalır.
- **Paket sırası**: IPsec tünel ağ geçidi senaryosunda şifreli alma ve düz metin iletme için alma tarafında yazılım ölçeklendirmenin nasıl etkinleştirildiğini belirtin. Bu ayar, paket sırasının korunmasını sağlar.

### <a name="network-settings"></a>Ağ ayarları

Bu ayarlar; **Etki alanı (iş yeri) ağı**, **Özel (keşfedilebilir) ağ** ve **Ortak (keşfedilemeyen) ağ** dahil olmak üzere belirli ağ türlerine uygulanabilir.

#### <a name="general-settings"></a>Genel ayarlar

- **Windows Defender Güvenlik Duvarı**: Güvenlik duvarını ve gelişmiş güvenliği açmak için **Etkinleştir** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) ayarı, diğer ilke ayarlarından bağımsız olarak tüm ağ trafiğine izin verir.
- **Gizli mod**: Güvenlik duvarının gizli modda çalışmasını önlemek için **Engelle** olarak ayarlayın. Gizli modu engellemek, **IPsec güvenli paket muafiyetini** de engellemenize imkan verir. **Yapılandırılmadı** (varsayılan) ayarı, güvenlik duvarını gizli modda çalıştırarak yoklama isteklerine yanıtların önlenmesine yardımcı olur.
- **Korumalı**: **Engelle** ayarı, bu özelliği devre dışı bırakır. **Yapılandırılmadı** (varsayılan) ayarı, bu ayarı etkinleştirir. Bu ayar ve Windows Defender Güvenlik Duvarı etkinleştirildiğinde, diğer ilke ayarlarından bağımsız olarak tüm gelen trafik engellenir.
- **Çok noktaya yayınlar için tek noktaya yayın yanıtları**: **Engelle** olarak ayarlandığında, çok noktaya yayın için tek noktaya yayın yanıtlarını devre dışı bırakır. Normalde, yayın veya çok noktaya yayın iletilerine tek noktaya yayın yanıtları almak istemezsiniz. Bu yanıtlar bir hizmet reddi (DOS) saldırısına veya bilinen bir canlı bilgisayarı araştırmaya çalışan bir saldırgana işaret eder. **Yapılandırılmadı** (varsayılan) ayarı, bu ayarı etkinleştirir.
- **Gelen bildirimler**: **Engelle** olarak ayarlandığında, bir uygulamanın bağlantı noktasında dinlemesi engellendiğinde kullanıcı bildirimlerini gizler. **Yapılandırılmadı** (varsayılan) ayarı, bu ayarı etkinleştirir ve bir uygulamanın bağlantı noktasında dinlemesi engellendiğinde kullanıcılara bildirim gösterebilir.
- **Gelen bağlantılar için varsayılan eylem**: **Engelle** olarak ayarlandığında, varsayılan güvenlik duvarı eylemi gelen bağlantılarda çalıştırılmaz. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, varsayılan güvenlik duvarı eylemi gelen bağlantılarda çalıştırılır.

#### <a name="rule-merging"></a>Kural birleştirme

- **Yerel depodan yetkili uygulama Windows Defender Güvenlik Duvarı kuralları**: Yerel depoda uygulama güvenlik duvarı kurallarının tanınması ve uygulanması için **Etkinleştir** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, yerel depoda yetkili uygulama güvenlik duvarı kuralları yoksayılır ve uygulanmaz.
- **Yerel depodan genel bağlantı noktası Windows Defender Güvenlik Duvarı kuralları**: Yerel depoda genel bağlantı noktası güvenlik duvarı kurallarının tanınması ve uygulanması için **Etkinleştir** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, yerel depoda genel bağlantı noktası güvenlik duvarı kuralları yoksayılır ve uygulanmaz.
- **Yerel depodan Windows Defender Güvenlik Duvarı kuralları**: Yerel depoda güvenlik duvarı kurallarının tanınması ve uygulanması için **Etkinleştir** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, yerel depodan güvenlik duvarı kuralları yoksayılır ve uygulanmaz.
- **Yerel depodan IPsec kuralları**: Şema veya bağlantı güvenlik kuralı sürümlerine bakılmaksızın yerel depodan bağlantı güvenlik kuralları uygulamak için **Etkinleştir** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, şema veya bağlantı güvenlik kuralı sürümlerine bakılmaksızın yerel depodan bağlantı güvenlik kuralları yoksayılır ve uygulanmaz.

## <a name="windows-defender-smartscreen-settings"></a>Windows Defender SmartScreen ayarları

Aşağıdaki Edge yüklü Windows 10 sürümlerinde desteklenir:
- Giriş
- Professional
- İşletme
- Kurumsal
- Eğitim
- Mobil
- Mobile Enterprise

**Ayarlar**:

- **Uygulamalar ve dosyalar için SmartScreen**: Dosya yürütme ve uygulama çalıştırma için Windows SmartScreen’i **Etkinleştir** olarak ayarlayın. SmartScreen, bulut tabanlı bir kimlik avından korunma ve kötü amaçlı yazılımdan korunma bileşenidir. **Yapılandırılmadı** (varsayılan) ayarı, SmartScreen’i devre dışı bırakır.
- **Doğrulanmamış dosyaları yürütme**: Son kullanıcının, Windows SmartScreen tarafından doğrulanmamış dosyaları çalıştırmasını önlemek için **Engelle** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) ayarı, bu özelliği devre dışı bırakır ve son kullanıcıların doğrulanmamış dosyaları çalıştırmasına izin verir.

## <a name="windows-encryption"></a>Windows Şifreleme

### <a name="windows-settings"></a>Windows Ayarları

Aşağıdaki Windows 10 sürümlerinde desteklenir:

- Professional
- İşletme
- Kurumsal
- Eğitim
- Mobil
- Mobile Enterprise

**Ayarlar**:

- **Cihazları şifrele**: Kullanıcılardan cihaz şifrelemesini etkinleştirmelerini istemek için bunu **Gerektir** olarak ayarlayın. Windows sürümü ve sistem yapılandırmasına bağlı olarak kullanıcılardan şunlar istenebilir:  
  - Başka bir sağlayıcı şifrelemesinin etkin olmadığını onaylama
  - Bitlocker Sürücü Şifreleme’yi kapatma ve Bitlocker’ı tekrar açmak zorunda olma
    
    Başka bir şifreleme yöntemi etkinken Windows şifrelemesi açılırsa cihaz kullanılamaz hale gelebilir. 
- **Depolama kartını şifrele (yalnızca mobil)**: Cihazın kullandığı çıkarılabilir depolama kartlarını şifrelemek için **Gerektir** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) ayarı, depolama kartı şifrelemesi gerektirmez ve kullanıcıdan bunu açmasını istemez. Bu ayar yalnızca Windows 10 mobil cihazlar için geçerlidir.

### <a name="bitlocker-base-settings"></a>BitLocker temel ayarları

Aşağıdaki Windows 10 sürümlerinde desteklenir:

- Kurumsal
- Eğitim
- Mobil
- Mobile Enterprise

Temel ayarlar, tüm veri sürücüsü türleri için evrensel BitLocker ayarlarıdır. Bu ayarlar, tüm veri sürücüsü türlerinde son kullanıcıların değiştirebileceği sürücü şifreleme görevleri veya yapılandırma seçeneklerini yönetir.

- **Başka disk şifrelemeleri için uyar**: Cihazda başka bir disk şifrelemesi olduğunda uyarı istemini devre dışı bırakmak için **Engelle** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) ayarı, uyarının gösterilmesine izin verir.
- **Şifreleme yöntemlerini yapılandır**: İşletim sistemi, veri ve çıkarılabilir sürücüler için şifreleme algoritmalarını yapılandırmak üzere **Etkinleştir** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında BitLocker, varsayılan şifreleme yöntemi olarak XTS-AES 128 bit kullanır veya herhangi bir kurulum betiği tarafından belirtilen şifreleme yöntemini kullanır.
  - **İşletim sistemi sürücüleri için şifreleme**: İşletim sistemi sürücüleri için şifreleme yöntemini seçin. XTS-AES algoritmasını kullanmanızı öneririz.
  - **Sabit veri sürücüleri için şifreleme**: Sabit (yerleşik) veri sürücüleri için şifreleme yöntemini seçin. XTS-AES algoritmasını kullanmanızı öneririz.
  - **Çıkarılabilir veri sürücüleri için şifreleme**: Çıkarılabilir veri sürücülerinin şifreleme yöntemini seçin. Çıkarılabilir sürücü, Windows 10 çalıştırmayan cihazlarla kullanılıyorsa AES-CBC algoritmasını kullanmanızı öneririz.

### <a name="bitlocker-os-drive-settings"></a>BitLocker işletim sistemi sürücüsü ayarları
Aşağıdaki Windows 10 sürümlerinde desteklenir:

- Kurumsal
- Eğitim
- Mobil
- Mobile Enterprise

Bu ayarlar, belirli işletim sistemi veri sürücüleri için geçerlidir.

- **Başlangıçta ek kimlik doğrulaması**: Güvenilir Platform Modülü (TPM) kullanımı dahil olmak üzere, bilgisayarı başlatma için kimlik doğrulama gereksinimlerini yapılandırmak üzere **Gerektir** olarak ayarlayın. TPM kullanan cihazlarda yalnızca temel seçenekleri yapılandırmak için bunu **Yapılandırılmadı** (varsayılan) olarak ayarlayın.
  - **Uyumsuz TPM yongası ile BitLocker**: Bir cihaz, uyumlu TPM yongasına sahip olmadığında BitLocker kullanımını engellemek için **Engelle** (devre dışı bırak) olarak ayarlayın. **Yapılandırılmadı** olarak ayarlandığında kullanıcılar, uyumlu TPM yongası olmadan BitLocker kullanabilir. BitLocker bir parola veya başlangıç anahtarı gerektirebilir.
  - **Uyumlu TPM başlatma**: TPM yongasına izin vermeyi, izin vermemeyi veya gerektirmeyi seçin.
  - **Uyumlu TPM başlangıç PIN'i**: TPM yongasıyla bir başlangıç PIN'i kullanmaya izin vermeyi, izin vermemeyi veya gerektirmeyi seçin. Başlangıç PIN’ini etkinleştirme, son kullanıcı etkileşimi gerektirir. 
  - **Uyumlu TPM başlangıç anahtarı**: TPM yongasıyla bir başlangıç anahtarı kullanmaya izin vermeyi, izin vermemeyi veya gerektirmeyi seçin. Başlangıç anahtarını etkinleştirme, son kullanıcı etkileşimi gerektirir. 
  - **Uyumlu TPM başlangıç anahtarı ve PIN'i**: TPM yongasıyla bir başlangıç anahtarı ve PIN'i kullanmaya izin vermeyi, izin vermemeyi veya gerektirmeyi seçin. Başlangıç anahtarı ve PIN’i etkinleştirme, son kullanıcı etkileşimi gerektirir.
- **En Düşük PIN Uzunluğu**: TPM başlangıç PIN’inin en düşük uzunluğunu yapılandırmak için **Etkinleştir** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, kullanıcılar 6 ila 20 basamak arasında bir başlangıç PIN’i yapılandırabilir.
  - **En düşük karakter sayısı**: Başlangıç PIN'i için gereken **4**-**20** arasındaki karakter sayısını girin.
- **İşletim sistemi sürücüsü kurtarma**: BitLocker ile korunan işletim sistemi sürücülerinin, gerekli başlatma bilgileri olmadığında nasıl kurtarılacağını denetlemek için **Etkinleştir** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, BitLocker kurtarma için varsayılan kurtarma seçenekleri desteklenir. Varsayılan olarak bir DRA’ya izin verilir, kurtarma parolası ve kurtarma anahtarı dahil olmak üzere kurtarma seçenekleri kullanıcı tarafından belirtilir ve kurtarma bilgileri AD DS’ye yedeklenmez.
  - **Sertifika tabanlı veri kurtarma aracısı**: **Engelle** olarak ayarlandığında, BitLocker ile korunan işletim sistemi sürücülerinde veri kurtarma aracısını kullanamazsınız. BitLocker korumalı işletim sistemi sürücülerinde veri kurtarma aracılarının kullanılabilmesini sağlayan bu ayarı etkinleştirmek için **Yapılandırılmadı** olarak ayarlayın.
  - **Kurtarma parolasının kullanıcı tarafından oluşturması**: Kullanıcıların 48 basamaklı bir kurtarma parolası oluşturmasına izin verilip verilmeyeceğini veya bunun gerekli olup olmadığını seçin.
  - **Kurtarma anahtarının kullanıcı tarafından oluşturması**: Kullanıcıların 256 bitlik bir kurtarma anahtarı oluşturmasına izin verilip verilmeyeceğini veya bunun gerekli olup olmadığını seçin.
  - **BitLocker kurulum sihirbazında kurtarma seçenekleri**: Kullanıcıların kurtarma seçeneklerini görememesi ve değiştirememesi için **Engelle** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, kullanıcılar BitLocker’ı açtığında kurtarma seçeneklerini göremez ve değiştiremez.
  - **BitLocker kurtarma bilgilerini AD DS’ye kaydet**: BitLocker kurtarma bilgilerinin Active Directory’de (AAD) depolanması için **Etkinleştir** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, kurtarma bilgileri AAD’de depolanmaz.
  - **AD DS’de depolanmış BitLocker kurtarma bilgileri**: BitLocker kurtarma bilgilerinin hangi bölümlerinin Azure AD’de depolanacağını yapılandırın. Aşağıdakilerden birini seçin:
    - **Yedekleme kurtarma parolaları ve anahtar paketleri**
    - **Yalnızca yedekleme kurtarma parolaları**
  - **BitLocker’ı etkinleştirmeden önce kurtarma bilgilerini AD DS’de depola**: BitLocker kurtarma bilgileri Active Directory’de başarıyla depolanmadan önce kullanıcıların BitLocker’ı açmasını engellemek için **Gerektir** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) ayarı, kurtarma bilgileri Azure Active Directory’de başarıyla depolanmamış olsa bile kullanıcıların BitLocker’ı açmasına izin verir.
- **Önyükleme öncesi kurtarma iletisi ve URL**: Önyükleme öncesi anahtar kurtarma ekranında görüntülenen iletiyi ve URL’yi yapılandırmak için **Etkinleştir** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) ayarı, bu özelliği devre dışı bırakır.
  - **Önyükleme öncesi kurtarma iletisi**: Önyükleme öncesi kurtarma iletisinin kullanıcılara gösterilme şeklini yapılandırın. Aşağıdakilerden birini seçin:
    - **Varsayılan kurtarma iletisi ve URL'sini kullan**
    - **Boş kurtarma iletisi ve URL'si kullan**
    - **Özel kurtarma iletisi kullan**
    - **Özel kurtarma URL'si kullan**

### <a name="bitlocker-fixed-data-drive-settings"></a>BitLocker sabit veri sürücüsü ayarları

Aşağıdaki Windows 10 sürümlerinde desteklenir:

- Kurumsal
- Eğitim
- Mobil
- Mobile Enterprise

**Ayarlar**:

- **BitLocker ile korunmayan sabit veri sürücüsüne yazma erişimi**: BitLocker ile korunmayan sabit veri sürücülerine yalnızca yazma erişimi vermek için **Engelle** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, BitLocker tarafından korunmayan veri sürücülerine okuma ve yazma erişimleri olur.
- **Sabit sürücü kurtarma**: Gerekli başlatma bilgileri olmadığında BitLocker korumalı sabit sürücülerin kurtarılma biçimini denetlemek için **Etkinleştir** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) ayarı, bu özelliği devre dışı bırakır.
  - **Veri kurtarma aracısı**: BitLocker tarafından korunan sabit sürücü İlke Düzenleyicisi ile veri kurtarma aracısının kullanılmasını önlemek için **Engelle** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) ayarı, BitLocker ile korunan sabit sürücülerle veri kurtarma aracılarının kullanımını etkinleştirir.
  - **Kurtarma parolasının kullanıcı tarafından oluşturulması**: Kullanıcıların 48 basamaklı bir kurtarma parolası oluşturmasına izin verilip verilmeyeceğini veya bunun gerekli olup olmadığını yapılandırın.  
  - **Kurtarma anahtarının kullanıcı tarafından oluşturması** - Kullanıcıların 256 bitlik kurtarma anahtarı oluşturmasına izin verilip verilmeyeceğini veya bunun gerekli olup olmadığını yapılandırın.
  - **BitLocker kurulum sihirbazında kurtarma seçenekleri**: Kullanıcıların kurtarma seçeneklerini görememesi ve değiştirememesi için **Engelle** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, kullanıcılar BitLocker’ı açtığında kurtarma seçeneklerini göremez ve değiştiremez.
  - **BitLocker kurtarma bilgilerini AD DS’ye kaydet**: BitLocker kurtarma bilgilerinin Active Directory’de (AAD) depolanması için **Etkinleştir** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, kurtarma bilgileri AAD’de depolanmaz.
  - **AD DS’de BitLocker kurtarma bilgileri**: BitLocker kurtarma bilgilerinin hangi bölümlerinin Azure Active Directory’de depolanacağını yapılandırın. Aşağıdakilerden birini seçin:
    - **Yedekleme kurtarma parolaları ve anahtar paketleri**
    - **Yalnızca yedekleme kurtarma parolaları**
  - **BitLocker’ı etkinleştirmeden önce kurtarma bilgilerini AD DS’de depola**: BitLocker kurtarma bilgileri Active Directory’de başarıyla depolanmadan önce kullanıcıların BitLocker’ı açmasını engellemek için **Gerektir** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) ayarı, kurtarma bilgileri Azure Active Directory’de başarıyla depolanmamış olsa bile kullanıcıların BitLocker’ı açmasına izin verir.

### <a name="bitlocker-removable-data-drive-settings"></a>BitLocker çıkarılabilir veri sürücüsü ayarları

Aşağıdaki Windows 10 sürümlerinde desteklenir:

- Kurumsal
- Eğitim
- Mobil
- Mobile Enterprise

**Ayarlar**:

- **BitLocker ile korunmayan çıkarılabilir veri sürücüsüne yazma erişimi**: BitLocker ile korunmayan veri sürücülerine yalnızca yazma erişimi vermek için **Engelle** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, BitLocker tarafından korunmayan veri sürücülerine okuma ve yazma erişimleri olur.
  - **Başka bir kuruluşta yapılandırılmış cihazlara yazma erişimi**: **Engelle** ayarı, başka bir kuruluşta yapılandırılmış cihazlara yazma erişimi verir. **Yapılandırılmamış** (varsayılan) ayarı, yazma erişimini reddeder.

## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard

Aşağıdaki Windows 10 sürümlerinde desteklenir:

- Giriş
- Professional
- İşletme
- Kurumsal
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

- **Saldırı yüzeyi azaltma kurallarının dışında tutulacak dosya ve klasörler**: Yapılandırılan kuralların dışında tutulacak konumlar listesini içeri aktarın/ekleyin.

### <a name="controlled-folder-access"></a>Denetlenen klasör erişimi

Önemli verileri fidye yazılımı gibi kötü amaçlı uygulama ve tehditlerden korumaya yardımcı olun.

- **Klasör koruma**: Dosya ve klasörleri, kötü amaçlı yazılımlar tarafından yapılan istenmeyen değişikliklerden koruyun. Bir **Korumalı dosyalara erişimi olan uygulamalar listesi** içeri aktarabilir veya bu uygulamaları el ile ekleyebilirsiniz. Ayrıca bir **Korunması gereken ek klasörler listesi** yükleyebilir veya bu klasörleri el ile ekleyebilirsiniz.

### <a name="network-filtering"></a>Ağ filtreleme

Uygulamaların düşük itibarlı IP/etki alanına giden bağlantılarını engelleyin.

### <a name="exploit-protection"></a>Exploit protection

Exploit protection’ı etkinleştirmek için sistemi ve dilediğiniz uygulama risk azaltma ayarlarını içeren bir XML dosyası oluşturun. Bunun için iki yöntem vardır:

 1. PowerShell: Get-ProcessMitigation, Set-ProcessMitigation ve ConvertTo-ProcessMitigationPolicy PowerShell cmdlet’lerinden biri veya daha fazlasını kullanın. Cmdlet'ler risk azaltma ayarlarını yapılandırır ve bunların XML gösterimini dışarı aktarır.

 2. Windows Defender Güvenlik Merkezi Kullanıcı Arabirimi: Windows Defender Güvenlik Merkezi’nde Uygulama & tarayıcı denetimine tıklayın ve çıkan ekranda aşağı kaydırarak Exploit Protection’ı bulun. Önce Sistem ayarları ve Program ayarları sekmelerini kullanarak risk azaltma ayarlarını yapılandırın. Daha sonra bunların bir XML temsilini dışarı aktarmak için ekranın altında yer alan Dışarı aktarma ayarları bağlantısını bulun.

Bellek, denetim akışı ve ilke kısıtlamalarını yapılandırmanıza izin veren bir XML dosyasını karşıya yükleyerek **Kullanıcıların Exploit Protection arabirimini düzenlemesi**’ni engelleyin. XML dosyasındaki ayarlar bir uygulamanın açıklarından yararlanılmasını engellemek için kullanılabilir. **Yapılandırılmadı** (varsayılan) ayarı, özel bir yapılandırma göndermez. 

## <a name="windows-defender-application-control"></a>Windows Defender Uygulama Denetimi

Aşağıdaki Windows 10 sürümlerinde desteklenir:

**Mobil Cihaz Yönetimi (MDM)**: 
- Professional
- İşletme
- Kurumsal
- Eğitim
- Mobil
- Mobile Enterprise

**Grup ilkesi yönetimi**: 
- Kurumsal

Windows Defender Uygulama Denetimi tarafından denetlenmesi gereken veya çalıştırılmasına güvenilen ek uygulamaları seçmek için **Uygulama denetimi kod bütünlüğü ilkelerini** kullanın. Windows mağazasındaki Windows bileşenlerinin ve tüm uygulamaların çalıştırılmasına otomatik olarak güvenilir.

Uygulamalar, **yalnızca denetimli** modda çalıştırıldığında engellenmez. **Yalnızca denetimli** modu, tüm olayları yerel istemci günlüklerine kaydeder.

Uygulama Denetimi etkinleştirildiğinde, yalnızca modun **Zorla**’dan **Yalnızca denetimli**’ye değiştirilmesiyle devre dışı bırakılabilir. Modun **Zorla**’dan **Yapılandırılmadı**’ya değiştirilmesi, Uygulama Denetimi’nin atanmış cihazlarda zorlanmaya devam etmesiyle sonuçlanır.

## <a name="windows-defender-credential-guard"></a>Windows Defender Credential Guard

Aşağıdaki Windows 10 sürümlerinde desteklenir:

- Kurumsal

Windows Defender Credential Guard kimlik bilgileri hırsızlığı saldırılarına karşı korur. Gizli dizileri yalnızca ayrıcalıklı sistem yazılımlarının erişebileceği şekilde yalıtır.

**Credential Guard** ayarları şunlardır:

- **Devre dışı bırak**: Daha önce **UEFI kilidi olmadan etkin** seçeneğiyle açılmışsa Credential Guard’ı uzaktan kapatır.

- **UEFI kilidi ile etkinleştir**: Credential Guard, kayıt defteri anahtarı veya grup ilkesi kullanılarak uzaktan devre dışı bırakılamaz.

    > [!NOTE]
    > Bu ayarı kullanırsanız ve daha sonra Credential Guard'ı devre dışı bırakmak isterseniz, Grup İlkesi'ni **Devre Dışı** olarak ayarlamalısınız. Ayrıca, UEFI yapılandırma bilgilerini her bilgisayardan fiziksel olarak temizleyin. UEFI yapılandırması devam ettiği sürece, Credential Guard etkindir.

- **UEFI kilidi olmadan etkinleştir**: Credential Guard’ın Grup İlkesi kullanılarak uzaktan devre dışı bırakılmasına izin verir. Bu ayarı kullanan cihazların Windows 10 sürüm 1511'i veya daha yeni bir sürümü çalıştırıyor olması gerekir.

Credential Guard'ı etkinleştirdiğinizde, aşağıdaki gerekli özellikler de etkinleştirilir:

- **Sanallaştırma Tabanlı Güvenlik** (VBS): Bir sonraki yeniden önyükleme sırasında açılır. Sanallaştırma tabanlı güvenlik, güvenlik hizmetlerine destek sağlamak için Windows Hiper Yöneticisi'ni kullanır.
- **Dizin Bellek Erişimi ile Güvenli Önyükleme**: VBS'yi Güvenli Önyükleme ve doğrudan bellek erişimi (DMA) korumalarıyla açar. DMA korumaları donanım desteği gerektirir ve yalnızca doğru yapılandırılmış cihazlarda etkinleştirilir.

## <a name="windows-defender-security-center"></a>Windows Defender Güvenlik Merkezi

Aşağıdaki Windows 10 sürümlerinde desteklenir:

- Giriş
- Professional
- İşletme
- Kurumsal
- Eğitim
- Mobil
- Mobile Enterprise

Windows Defender Güvenlik Merkezi, diğer tüm özelliklerden ayrı bir uygulama veya işlem olarak çalışır. İşlem Merkezi aracılığıyla bildirimler gösterir. Her bir özelliğin durumunu görmek ve bazı yapılandırmaları gerçekleştirmek için bir toplayıcı veya tek bir yer olarak görev yapar. [Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) belgelerinden daha fazla bilgi edinin.

#### <a name="windows-defender-security-center-app-and-notifications"></a>Windows Defender Güvenlik Merkezi uygulaması ve bildirimleri

Windows Defender Güvenlik Merkezi uygulamasının çeşitli alanlarına son kullanıcı erişimini engelleyin. Bir bölümü gizlemek, bu bölümle ilgili bildirimleri de engeller.

- **Virüs ve tehdit koruması**
- **Cihaz performans ve sistem durumu**
- **Güvenlik duvarı ve ağ koruması**
- **Uygulama ve tarayıcı denetimi**
- **Aile seçenekleri**
- **Uygulamanın görüntülenen alanlarından bildirimler**: Son kullanıcılara hangi bildirimlerin gösterileceğini seçin. Kritik olmayan bildirimlere, Windows Defender Antivirus etkinliğinin özetleri ve taramalar tamamlandığında verilen bildirimler dahildir. Diğer tüm bildirimler kritik olarak kabul edilir.

#### <a name="it-contact-information"></a>BT iletişim bilgileri

Windows Defender Güvenlik Merkezi uygulaması ve uygulama bildirimlerinde gösterilecek BT iletişim bilgilerini sağlayın. **Uygulamada ve bildirimlerde göster**, **Yalnızca uygulamada göster**, **Yalnızca bildirimlerde göster** veya **Gösterme** seçeneklerinden birini seçebilirsiniz. **BT kuruluş adı** ile aşağıdaki iletişim seçeneklerinden en az birini girin:

- **BT departmanı telefon numarası veya Skype kimliği**
- **BT departmanı e-posta adresi**
- **BT destek web sitesi URL’si**

## <a name="local-device-security-options"></a>Yerel cihaz güvenliği seçenekleri

Aşağıdaki Windows 10 sürümlerinde desteklenir:
 
- Giriş
- Professional
- İşletme
- Kurumsal
- Eğitim

Windows 10 cihazlarında yerel güvenlik ayarlarını yapılandırmak için bu seçenekleri kullanın.

### <a name="accounts"></a>Hesaplar

- **Yeni Microsoft hesapları ekle**: Kullanıcıların cihaza yeni Microsoft hesapları eklemesini önlemek için **Engelle** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, kullanıcılar cihazda Microsoft hesabı kullanabilir.
- **Parola olmadan uzaktan oturum açma**: **Etkinleştir** ayarı, boş parolası olan yerel hesapların cihaz klavyesini kullanarak oturum açmasına izin verir. **Yapılandırılmadı** (varsayılan) ayarı, boş parolası olan yerel hesapların fiziksel cihaz dışındaki konumlardan oturum açmasına izin verir.

#### <a name="admin"></a>Yönetim

- **Yerel yönetici hesabı**: Yerel yönetici hesabına izin vermek için **Etkin** olarak ayarlayın. Yerel yönetici hesabını devre dışı bırakmak için **Yapılandırılmadı** (varsayılan) olarak ayarlayın.
- **Yönetici hesabını yeniden adlandır**: Yönetici hesabının güvenlik tanımlayıcısıyla (SID) ilişkilendirilecek farklı bir hesap adı tanımlayın.

#### <a name="guest"></a>Konuk

- **Guest hesabı**: Yerel guest hesabına izin vermek için **Etkin** olarak ayarlayın. Yerel guest hesabını devre dışı bırakmak için **Yapılandırılmadı** (varsayılan) olarak ayarlayın.
- **Konuk hesabını yeniden adlandır**: Konuk hesabının güvenlik tanımlayıcısıyla (SID) ilişkilendirilecek farklı bir hesap adı tanımlayın.

### <a name="devices"></a>Cihazlar

- **Oturum açma olmadan cihazı çıkar**: Kullanıcıların yerleştirilmiş bir taşınabilir cihazın fiziksel çıkarma düğmesine basarak cihazı güvenle çıkarabilmeleri için **Engelle** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) ayarı, cihazı çıkarmak için kullanıcının cihazda oturum açmasını ve izin almayı gerektirir.
- **Paylaşılan yazıcılar için yazıcı sürücülerini yükle**: **Etkin** olarak ayarlandığında, herhangi bir kullanıcı, paylaşılan yazıcıya bağlanma işlemi kapsamında yazıcı sürücüsü yükleyebilir. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, paylaşılan yazıcıya bağlanma işlemi kapsamında yalnızca yöneticiler yazıcı sürücüsü yükleyebilir.
- **CD-ROM erişimini yerel etkin kullanıcıyla kısıtla**: **Etkin** olarak ayarlandığında, yalnızca etkileşimli olarak oturum açan kullanıcı CD-ROM medyasına erişebilir. Bu ilke etkinse ve kimse etkileşimli olarak oturum açmamışsa CD-ROM’a ağ üzerinden erişilir. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, herkesin CD-ROM’a erişimi olur.
- **Çıkarılabilir medyayı biçimlendir ve çıkar**: Çıkarılabilir NTFS medyasını kimlerin biçimlendirmesine ve çıkarmasına izin verileceğini tanımlayın:
  - **Yapılandırılmadı**
  - **Yöneticiler**
  - **Yöneticiler ve Yetkili Kullanıcılar**
  - **Yöneticiler ve Etkileşimli Kullanıcılar**

### <a name="interactive-logon"></a>Etkileşimli Oturum Açma

- **Ekran koruyucu etkinleştirilmeden önceki kilit ekranında işlem yapılmadan geçen dakika sayısı**: Ekran koruyucu çalıştırılmadan önce etkileşimli masa üstünün oturum açma ekranında işlem yapılmadan geçecek en yüksek dakika sayısını girin.
- **Oturum açmak için CTRL + ALT + DEL gerektir**: Kullanıcıların oturum açması için CTRL+ALT+DEL tuşlarına basmayı gerektirmemek için **Etkin** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, kullanıcıların Windows’da oturum açmaları için CTRL+ALT+DEL tuşlarına basmaları gerekir.
- **Akıllı kart kaldırma davranışı**: Oturum açma kullanıcısı için akıllı kartın akıllı kart okuyucusundan çıkarılması durumunda neler olacağını belirler. Seçenekleriniz şunlardır:

  - **İş İstasyonunu Kilitle**: Akıllı kart çıkarıldığında iş istasyonu kilitlenir. Bu seçenek kullanıcıların akıllı kartlarını alarak alandan uzaklaşmasına ve yine de korumalı oturumu sürdürmesine olanak tanır.
  - **Oturumu Kapatmaya Zorla**: Kullanıcı akıllı kartı çıkardığında oturumu otomatik olarak kapatılır.
  - **Bir Uzak Masaüstü Hizmetleri oturumu bağlantısını kes**: Akıllı kartın çıkarılması kullanıcının oturumunu kapatmadan oturumun bağlantısını keser. Bu seçenek kullanıcının daha sonra yeniden oturum açmak zorunda kalmadan akıllı kartı takıp oturumu devam ettirmesine veya akıllı kart okuyucuyla donatılmış başka bir bilgisayarda bunu yapmasına olanak tanır. Yerel bir oturum söz konusuysa, bu ilke İş İstasyonunu Kilitle ilkesiyle tam olarak aynı işlevi görür.

    [LocalPoliciesSecurity seçenekleri](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-interactivelogon-smartcardremovalbehavior) başlığı altında daha fazla ayrıntı sağlanır.

#### <a name="display"></a>Görüntüle

- **Kilit ekranında kullanıcı bilgileri**: Oturum kilitlendiğinde görüntülenen kullanıcı bilgilerini yapılandırın. Yapılandırılmazsa, kullanıcı görünen adı, etki alanı ve kullanıcı adı gösterilir.
  - **Yapılandırılmadı**
  - **Kullanıcı görünen adı, etki alanı ve kullanıcı adı**
  - **Yalnızca kullanıcı görünen adı**
  - **Kullanıcı bilgilerini görüntüleme**
- **Son oturum açan kullanıcıyı gizle**: **Etkinleştir** ayarı, kullanıcı adını gizler. **Yapılandırılmadı** (varsayılan) ayarı, kullanıcı adını gösterir.
- **Oturum açma sırasında kullanıcı adını gizle**: **Etkinleştir** ayarı, kullanıcı adını gizler. **Yapılandırılmadı** (varsayılan) ayarı, kullanıcı adını gösterir.
- **Oturum açma ileti başlığı**: Oturum açan kullanıcılar için ileti başlığını ayarlayın.
- **Oturum açma ileti metni**: Oturum açan kullanıcılar için ileti metnini ayarlayın.

### <a name="network-access-and-security"></a>Ağ erişimi ve güvenlik

- **Adlandırılmış Kanallara ve Paylaşımlara anonim erişim**: **Yapılandırılmadı** (varsayılan) paylaşım ve Adlandırılmış Kanal ayarlarına anonim erişimi kısıtlar. Anonim olarak erişilebilen ayarlar için geçerlidir.
- **SAM hesaplarının anonim olarak listelenmesi**: Anonim kullanıcıların SAM hesaplarını listelemesine **izin verin**. Windows anonim kullanıcılara etki alanı hesaplarının ve ağ paylaşımlarının adlarını listeleme izni verir.
- **SAM hesaplarının ve paylaşımların anonim listelenmesi**: **Yapılandırılmadı** (varsayılan), anonim kullanıcıların etki alanı hesaplarıyla ağ paylaşımlarının adlarını listeleyebileceği anlamına gelir. SAM hesaplarının ve paylaşımlarının anonim listelenmesini önlemek için **Engelle** olarak ayarlayın.
- **Parola değişiminde depolanan LAN Manager karma değeri**: Bir sonraki parola değişikliğinde, yeni parolanın karma değerini LAN Manager'da (LM) depolamaya **izin verin**. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, karma değer depolanmaz.
- **PKU2U kimlik doğrulama istekleri**: Bu cihaza yönelik PKU2U kimlik doğrulama isteklerinin çevrimiçi kimlikleri kullanmasını **engelleyin**. **Yapılandırılmadı** (varsayılan) ayarı bu isteklere izin verir.
- **SAM'ye uzak RPC bağlantılarını kısıtla**: Kullanıcıların ve grupların SAM'ye uzak çağrı yapmasını engellemek için varsayılan Güvenlik Tanımlayıcısı Tanım Dili dizesine **izin verin**. **Yapılandırılmadı** (varsayılan) ayarında, kullanıcıların ve grupların SAM'ye uzak çağrı yapmasına izin vermek için varsayılan Güvenlik Tanımlayıcısı Tanım Dili dizesi yapılandırılmaz.
  - **Güvenlik tanımlayıcısı**

### <a name="recovery-console-and-shutdown"></a>Kurtarma konsolu ve kapatma

- **Kapatma sırasında sanal bellek disk belleği dosyasını temizle**: Cihaz kapatıldığında sanal bellek disk belleği dosyasını temizlemek için **Etkinleştir** olarak ayarlayın. **Yapılandırılmadı** ayarı, sanal belleği temizlemez.
- **Oturum açmadan cihaz kapatma**: **Engelle** ayarı, Windows oturum açma ekranında kapatma seçeneğini gizler. Kullanıcıların cihazda oturum açıp ve ardından cihazı kapatması gerekir. **Yapılandırılmadı** (varsayılan) ayarı, kullanıcıların Windows oturum açma ekranından cihazı kapatmalarına izin verir.

### <a name="user-account-control"></a>Kullanıcı hesap denetimi

- **Güvenli konum olmadan UIA bütünlüğü**: **Etkinleştir** olarak ayarlandığında, dosya sistemindeki güvenli konumlarda bulunan uygulamalar yalnızca UIAccess bütünlüğüyle çalıştırılır. **Yapılandırılmadı** (varsayılan) ayarı, uygulamaların dosya sistemindeki güvenli konumlarda bulunmasa bile UIAccess bütünlüğüyle çalıştırılmasına izin verir.
- **Dosya ve kayıt defteri yazma hatalarını kullanıcı başına konumlarda sanal olarak oluştur**: **Engelle** olarak ayarlandığında, uygulama yazma hataları çalışma zamanında dosya sistemi ve kayıt defteri için tanımlı kullanıcı konumlarına yeniden yönlendirilir. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, korumalı konumlara veri yazan uygulamalar başarısız olur.
- **Yalnızca imzalı ve doğrulanmış yürütülebilir dosyaları yükselt**: Bir yürütülebilir dosyanın çalışmasına izin verilmeden önce bu dosya için PKI sertifika yolu doğrulamasını zorunlu tutmak için **Etkinleştir** olarak ayarlayın. Bir yürütülebilir dosyanın çalışabilmesi için PKI sertifika yolu doğrulamasını zorlamamak için **Yapılandırılmadı** olarak ayarlayın.

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
- **Yükseltme istemlerini kullanıcının etkileşimli masaüstüne yönlendir**: Tüm yükseltme isteklerinin güvenli masaüstüne değil de etkileşimli kullanıcının masaüstüne gitmesi için **Etkinleştir** olarak ayarlayın. Yöneticiler ve standart kullanıcılar için herhangi bir istem davranışı ilke ayarı kullanılır. **Yapılandırılmadı** (varsayılan) ayarı, yöneticiler ve standart kullanıcılar için istem davranışı ilke ayarlarına bakılmaksızın tüm yükseltme isteklerini güvenli masaüstüne gitmeye zorlar.
- **Uygulama yüklemeleri için yükseltilmiş istem**: **Engelle** olarak ayarlandığında, yükseltme için uygulama yükleme paketleri algılanmaz veya istenmez. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, bir uygulama paketi yükseltilmiş ayrıcalıklar gerektirdiğinde kullanıcıdan yönetici kullanıcı adı ve parolası istenir.
- **Güvenli masaüstü olmadan UIA yükseltme istemi**: UIAccess uygulamalarının güvenli masaüstü kullanmadan yükseltme isteminde bulunmasına izin vermek için **Etkinleştir** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, yükseltme istemleri bir güvenli masaüstü kullanır.

#### <a name="admin-approval-mode-settings"></a>Yönetici Onay Modu ayarları

- **Yerleşik Yönetici için Yönetici Onay Modu**: **Etkin** ayarı, yerleşik Yönetici hesabının Yönetici Onay Modu kullanmasına izin verir. Ayrıcalık gerektiren herhangi bir işlem, kullanıcıdan işlemi onaylamasını ister. **Yapılandırılmadı** (varsayılan) ayarı, tam yönetici ayrıcalıkları olan tüm uygulamaları çalıştırır.
- **Tüm yöneticileri Yönetici Onay Modunda çalıştır**: Yönetici Onay Modunu ve tüm ilgili UAC ilke ayarlarını devre dışı bırakmak için **Engelle** olarak ayarlayın. **Yapılandırılmadı** (varsayılan) ayarı, Yönetici Onay Modunu etkinleştirir.

### <a name="microsoft-network-client"></a>Microsoft Ağ İstemcisi

- **İletişimleri dijital olarak imzala (sunucu onaylarsa)**: SMB istemcisinin SMB paket imzalama anlaşması yapıp yapmayacağını belirler. **Yapılandırılmadı** veya etkin (varsayılan) olarak ayarlandığında Microsoft ağ istemcisi, sunucudan oturum kurulumunda SMB paket imzalama işlemini çalıştırmasını ister. Sunucuda paket imzalama etkinleştirilirse, paket imzalama anlaşması yapılır. **Devre dışı bırak** olarak ayarlandığında, SMB istemcisi hiçbir zaman SMB paket imzalama anlaşması yapmaz.
- **Üçüncü taraf SMB sunucularına şifrelenmemiş parola gönder**: **Etkin** olarak ayarlandığında, Sunucu İleti Bloğu (SMB) yeniden yönlendiricisi kimlik doğrulama sırasında parola şifrelemesini desteklemeyen Microsoft dışı SMB sunucularına düz metin parolalar gönderebilir. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, parolalar şifrelenir.

### <a name="microsoft-network-server"></a>Microsoft Ağ Sunucusu

- **İletişimleri dijital olarak imzala (istemci onaylarsa)**: SMB sunucusunun istekte bulunan istemcilerle SMB paket imzalama anlaşması yapıp yapmayacağını belirler. **Etkinleştir** olarak ayarlandığında, Microsoft ağ sunucusu istemci tarafından istendiği gibi SMB paket imzalama anlaşması yapar. Başka bir deyişle, istemcide paket imzalama etkinleştirildiyse paket imzalama anlaşması yapılır. **Yapılandırılmadığında** veya devre dışı bırakıldığında (varsayılan), SMB istemcisi hiçbir zaman SMB paket imzalama anlaşması yapmaz.
- **İletişimleri dijital olarak imzala (her zaman)**: SMB sunucu bileşeninin paket imzalama gerektirip gerektirmediğini belirler. **Etkinleştir** olarak ayarlandığında, Microsoft ağ istemcisi SMB paket imzalamayı kabul etmediği sürece Microsoft ağ sunucusu istemciyle iletişim kurmaz. **Yapılandırılmadı** veya Devre Dışı (varsayılan) olarak ayarlandığında, istemciyle sunucu arasında SMB paket imzalama anlaşması yapılır.

## <a name="next-steps"></a>Sonraki adımlar

Bu profili gruplara atamak için bkz. [Cihaz profillerini atama](device-profile-assign.md).
