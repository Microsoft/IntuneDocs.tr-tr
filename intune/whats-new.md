---
title: Microsoft Intune - Azure’daki yenilikler | Microsoft Docs
titlesuffix: ''
description: Intune Azure portalındaki yenilikleri keşfedin
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/05/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
/ms.custom: intune-azure
ms.openlocfilehash: e6d3640d63f16b80588860c3c36aba1a81ffbe09
ms.sourcegitcommit: 8ea2ff0941219e72477d7ceaab40a0068e53d508
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37927038"
---
# <a name="whats-new-in-microsoft-intune"></a>Microsoft Intune'daki yenilikler
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune’daki haftalık yenilikleri öğrenin. [Yaklaşan değişiklikler](#whats-coming), hizmet hakkında [önemli bildirimler](#notices) ve [geçmiş sunumlar](whats-new-archive.md) hakkında bilgiler de alabilirsiniz. Bazı özelliklerin piyasaya çıkması birkaç haftayı bulabilir ve tüm özellikler ilk hafta bütün müşterilerimize sunulmamış olabilir.

> [!Note]
> Karma mobil cihaz yönetimindeki (MDM) yeni işlevler hakkında bilgi için, [karma Yenilikler sayfasını](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) gözden geçirin.


<!-- Common categories:  
### App management
### Device enrollment
### Device management
### Device configuration
### Intune apps
### Monitor and troubleshoot
### Role-based access control

-->   
## <a name="week-of-july-2-2018"></a>2 Temmuz 2018 Haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Windows Installer için ek güvenlik ayarları <!-- 2282430 -->
Kullanıcıların uygulama yüklemelerini denetlemesine olanak sağlayabilirsiniz. Etkinleştirilirse, aksi takdirde güvenlik ihlali nedeniyle durdurulabilecek olan yüklemelerin devam etmesine izin verilebilir. Windows Installer'ı sistemde herhangi bir program yüklerken yükseltilmiş izinler kullanmaya yönlendirebilirsiniz. Buna ek olarak, Windows Bilgi Koruması (WIP) öğelerinin dizine alınmasını ve bunlar hakkındaki meta verilerin şifrelenmemiş bir konumda depolanmasını etkinleştirebilirsiniz. İlke devre dışı bırakıldığında, WIP korumalı öğelerin dizini oluşturulmaz ve Cortana veya dosya gezgini sonuçlarında görünmez. Bu seçeneklerin işlevselliği varsayılan olarak devre dışı bırakılmıştır. 

#### <a name="monitor-ios--app-configuration-status-per-device----880037---"></a>Cihaz başına iOS uygulama yapılandırması durumunu izleme <!-- 880037 -->
Microsoft Intune yöneticisi olarak, yönetilen her cihaz için iOS uygulama yapılandırması durumunu izleyebilirsiniz. Azure portalında **Microsoft Intune**'dan **Cihazlar** > **Tüm cihazlar**'ı seçin. Yönetilen cihaz listesinden belirli bir cihazı seçerek o cihazın dikey penceresini görüntüleyin. Cihaz dikey penceresinde **Uygulama yapılandırması**'nı seçin.

#### <a name="access-actions-for-app-protection-policies----1483510---"></a>Uygulama koruma ilkeleri için eylemlere erişme <!-- 1483510 -->
Uyumsuz cihazları açık olarak silmek, engellemek veya uyarmak üzere uygulama koruma ilkeleri yapılandırabilirsiniz. *Silme* eylemi, bir cihazdan şirketinizin verilerini kaldırır. Silme işlemi gerçekleştirildiğinde, cihazın kullanıcısına silme nedeni ve düzeltme adımları bildirilir. En düşük işletim sistemi sürümü gibi bazı ayarlarda, engelleme ve silme gibi birden fazla eylem gerçekleştirebileceksiniz. Bu eylemlerin uygulama başlatıldığında tetiklendiğine dikkat edin.

#### <a name="selective-wipe-of-organizations-app-data----1507030---"></a>Kuruluşun uygulama verilerini seçmeli silme <!-- 1507030 -->
Uygulama Koruma İlkeleri (APP) Erişim ayarlarının koşullarına uyulmadığında, şimdi yöneticiler yeni bir eylem olarak kuruluş verilerinin seçmeli silinmesini yapılandırabilir.  Bu özellik yöneticilerin önceden yapılandırılmış ölçütler temelinde hassas kuruluş verilerini otomatik olarak korumasına ve uygulamalardan kaldırmasına yardımcı olur.

#### <a name="revoking-an-ios-app-purchased-through-vpp----1777384---"></a>VPP üzerinden satın alınan iOS uygulamasını iptal etme <!-- 1777384 -->
Microsoft Intune yöneticisi olarak, Volume Purchase Program (VPP) üzerinden satın alınan seçili iOS uygulamasının tüm lisanslarını iptal edebilirsiniz. Kullanıcı lisanslı uygulamanın artık kendisine atanmış durumda olmadığını kullanıcıya bildirebilirsiniz. Bir uygulama lisansını iptal etmek ilgili VPP uygulamasını cihazdan kaldırmaz. Bir VPP uygulamasını kaldırmak için, atama işlemini **Kaldır** olarak değiştirmelisiniz. Geri kazanılan lisans sayısı, Intune'un **Uygulama** iş yükündeki **Lisanslı Uygulamalar** düğümünde yansıtılacak. iOS VPP uygulamalarıyla ilgili daha fazla bilgi için bkz. [Microsoft Intune ile Volume Purchase Program üzerinden satın alınan iOS uygulamalarını yönetme](vpp-apps-ios.md).

#### <a name="updates-to-out-of-compliance-messages-in-company-portal-app----1832222---"></a>Şirket Portalı uygulamasında uyumsuzluk iletilerine güncelleştirmeler <!-- 1832222 -->
Cihaz uyumlu olmadığında cihaz kullanıcılarının gördüğü iletileri düzelttik. İletiler özgün anlamlarını koruyor ancak daha kolay bir dil ve daha az teknik terminoloji ile güncelleştirildi. Ayrıca belge bağlantılarını ve bunları güncel tutmaya yönelik düzeltme adımlarını da yeniledik.
Aşağıda öncesi ve sonrası gösterilen metin, göreceğiniz ileti iyileştirmelerinin bir örneğidir:
- **Öncesi**: *Bu cihaz, BT yöneticiniz tarafından belirlenen süre içinde Intune ile iletişime geçmedi. Bu sorunu çözmek için lütfen cihazınızda şirket portalı uygulamasını açın ve Uyumluluğu Denetle düğmesine tıklayın.*
- **Sonrası**: *Cihazınız bir süredir kuruluşunuza iade edilmedi. Bağlantıyı yeniden kurmak üzere cihazınızda Şirket Portalı uygulamasını açın ve cihazınız için Ayarları Denetle’ye dokunun.*

#### <a name="revoke-ios-vpp-app-license----1863797---"></a>iOS VPP uygulama lisansını iptal etme <!-- 1863797 -->
Yönetici olarak, bir kullanıcı veya cihaza atanmış olan iOS VPP uygulama lisansını geri kazanabilirsiniz. iOS VPP uygulamasını kaldırmak uygulama lisansını geri kazanmanıza da olanak tanıyacak. Uygulamayı kaldırmadan önce, kullanıcının veya cihazın uygulamayla hedeflenen gruptan kaldırılması gerekir. Kullanıcı veya cihazın gruptan kaldırılması, uygulamanın yeniden yüklenmesini önler. Bu adımlar tamamlandıktan sonra, uygulama lisansını başka bir kullanıcı veya cihaza atamayı seçebilirsiniz. iOS VPP uygulama lisansları hakkında daha fazla bilgi için bkz. [Microsoft Intune'da toplu satın alınan iOS uygulamalarını yönetme](vpp-apps-ios.md).

#### <a name="line-of-business-lob-app-support-for-macos----1895847---"></a>macOS için iş kolu (LOB) uygulamaları desteği <!-- 1895847 -->
Microsoft Intune, macOS LOB uygulamalarının **Gerekli** veya **Kayıt sonrasında kullanılabilir** olarak dağıtılmasına olanak tanır. Son kullanıcılar, uygulamaları macOS için Şirket Portalı’ndan veya [Şirket Portalı web sitesinden](https://portal.manage.microsoft.com) **Kullanılabilir** olarak alabilirler.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963-eenotready---"></a>İş Yeri veya Okula Erişme ayarlarını kullanarak cihaz kategorilerini seçme <!-- 1058963 eenotready --> 
[Cihaz grubu eşlemeyi](https://docs.microsoft.com/en-us/intune/device-group-mapping) etkinleştirdiyseniz, Windows 10'daki kullanıcılardan şimdi **Ayarlar** > **Hesaplar** > **İş yeri veya okula eriş** altındaki **Bağlan** düğmesi aracılığıyla kaydolduktan sona cihaz kategorisini seçmeleri istenecek. 

#### <a name="use-samaccountname-as-the-account-username-for-email-profiles----1500307---"></a>E-posta profilleri için hesap kullanıcı adı olarak sAMAccountName kullanın <!-- 1500307 -->
Android, iOS ve Windows 10'da e-posta profillerinin hesap kullanıcı adı olarak şirket içi **sAMAccountName** adını kullanabilirsiniz. Ayrıca Azure Active Directory'de (Azure AD) `domain`.veya `ntdomain` özniteliğinden etki alanını da alabilirsiniz. Bunun yerine özel bir statik etki alanı girebilirsiniz.

Bu özelliği kullanmak için, şirket içi Active Directory ortamınızdan Azure AD'ye `sAMAccountName` özniteliğini eşitlemeniz gerekir.

[Andoid](email-settings-android.md), [iOS](email-settings-ios.md), [Windows 10 ve üzeri](email-settings-windows-10.md) için geçerlidir

#### <a name="see-device-configuration-profiles-in-conflict----1556983---"></a>Çakışması olan cihaz yapılandırma profillerini görme <!-- 1556983 -->
**Cihaz Yapılandırması**’nda mevcut profillerin bir listesi gösterilir. Bu güncelleştirme ile çakışması olan profiller hakkında ayrıntılar sağlayan yeni bir sütun eklenir. Çakışması olan ayarı ve profili görmek için çakışan bir satırı seçebilirsiniz. 

[Yapılandırma profillerini yönetme](device-profile-monitor.md#view-conflicts) başlığı altında daha fazla bilgi edinebilirsiniz.

#### <a name="new-status-for-devices-in-device-compliance----2308882---"></a>Cihaz uyumluluğunda cihazlar için yeni durum <!-- 2308882 -->
**Cihaz uyumluluğu** > **İlkeler**'de bir ilke seçin ve **Genel Bakış**’ı seçin; aşağıdaki yeni durumlar eklenir:
- başarılı
- hata
- çakışma
- bekleniyor
- uygulanamaz Farklı bir platformun cihaz sayısını gösteren bir resim de görüntülenir. Örneğin bir iOS profiline bakıyorsanız, yeni kutucuk yine bu profile atanmış olan iOS dışı cihazların sayısını gösterir. Bkz. [Cihaz uyumluluk ilkeleri](compliance-policy-monitor.md#view-status-of-device-policies).

#### <a name="device-compliance-supports-3rd-party-anti-virus-solutions----2325484---"></a>Cihaz uyumluluğu üçüncü taraf virüsten koruma çözümlerini destekler <!-- 2325484 -->
Yeni bir cihaz uyumluluğu ilkesi oluşturduğunuzda (**Cihaz uyumluluğu** > **İlkeler** > **İlke oluştur** > **Platform: Windows 10 ve üzeri** > **Ayarlar** > **Sistem Güvenliği**) yeni **[Cihaz Güvenliği](compliance-policy-create-windows.md#windows-10-and-later-policy-settings)** seçenekleri olur: 
- **Virüsten koruma**: **Gerektir** olarak ayarlandığında, Windows Güvenlik Merkezi’ne kaydedilmiş Symantec ve Windows Defender gibi virüsten koruma çözümlerini kullanarak uyumluluğu denetleyebilirsiniz. 
- **Casus yazılım önleme**: **Gerektir** olarak ayarlandığında, Windows Güvenlik Merkezi’ne kaydedilmiş Symantec ve Windows Defender gibi casus yazılım önleme çözümlerini kullanarak uyumluluğu denetleyebilirsiniz. 

Şunlar için geçerlidir: Windows 10 ve üzeri 

### <a name="device-enrollment"></a>Cihaz kaydı

####  <a name="devices-without-profiles-column-in-the-list-of-enrollment-program-tokens----1853904---"></a>Kayıt programı belirteçleri listesinde profil sütunu olmayan cihazlar <!-- 1853904 -->
Kayıt programı belirteçleri listesinde, profil atanmamış olan cihazların sayısını gösteren yeni bir sütun vardır. Bu, yöneticilerin bu cihazları kullanıcılara teslim etmeden önce bunlara profil atamasına yardımcı olur. Yeni sütunu görmek için, **Cihaz kaydı** > **Apple kaydı** > **Kayıt programı belirteçleri**'ne gidin.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="google-name-changes-for-android-for-work-and-play-for-work---842873---"></a>Android for Work ve Play for Work için Google ad değişiklikleri <!--842873 -->
Intune, "Android for Work" terminolojisini Google marka değişikliklerini yansıtacak şekilde güncelleştirdi. "Android for Work" ve "Play for Work" terimleri artık kullanılmıyor. Bağlama göre farklı bir terminoloji kullanılıyor:
- "Android kurumsal", genel olarak modern Android yönetim yığınına karşılık gelir.
- "İş profili" veya "Profil Sahibi", iş profilleriyle yönetilen KCG cihazlarına karşılık gelir.
- "Yönetilen Google Play", Google uygulama mağazasına karşılık gelir.

#### <a name="rules-for-removing-devices----1609459---"></a>Cihaz kaldırma kuralları <!-- 1609459 -->
Ayarladığınız süre boyunca (gün) iade edilmeyen cihazları otomatik olarak kaldırmanıza olanak tanıyan yeni kurallar kullanılabilir. Yeni kuralı görmek için **Intune** bölmesine gidin, **Cihazlar**’ı ve **Cihaz temizleme kuralları**’nı seçin.

#### <a name="corporate-owned-single-cosu-use-support-for-android-devices----1630973---"></a>Android cihazları için şirkete ait, tek (COSU) kullanım desteği <!-- 1630973 -->

Intune şimdi üst düzeyde yönetilen, kilitlenen, bilgi noktası stilindeki Android cihazlarını destekler. Bu sayede yöneticiler cihazın kullanımını tek uygulamayla veya küçük bir uygulama kümesiyle kilitleyebilir ve kullanıcıların cihazda başka uygulamaları etkinleştirmesini veya başka eylemler gerçekleştirmesini engelleyebilir. Android kiosku ayarlamak için, Intune > **Cihaz kaydı** > **Android kaydı** > **Kiosk ve görev cihazı kayıtları**'na gidin. Daha fazla bilgi için bkz. [Android kurumsal kiosk cihazlarının kaydını ayarlama](android-kiosk-enroll.md).

#### <a name="per-row-review-of-duplicate-corporate-device-identifiers-uploaded----2203794--"></a>Karşıya yüklenmiş yinelen şirket cihazı tanımlayıcılarını satır temelinde gözden geçirme <!-- 2203794-->
Şirket kimliklerini karşıya yüklerken, Intune şimdi tüm yinelemelerin listesini sağlar ve size mevcut bilgileri değiştirme veya koruma seçeneği verir. **Cihaz kaydı** > **Şirket Cihazı Tanımlayıcıları** > **Tanımlayıcıları Ekle**'yi seçtikten sonra yinelemeler varsa rapor görüntülenecek. 

#### <a name="manually-add-corporate-device-identifiers----2203803---"></a>Şirket cihazı tanımlayıcılarını el ile ekleme <!-- 2203803 -->
Şimdi şirket cihazı kimliklerini el ile ekleyebilirsiniz. **Cihaz kaydı** > **Şirket Cihazı Tanımlayıcıları** > **Ekle**'yi seçin. 

## <a name="week-of-june-25-2018"></a>25 Haziran 2018 Haftası

### <a name="pradeo---new-mobile-threat-defense-partner----1169249---"></a>Pradeo - Yeni Mobile Threat Defense iş ortağı <!-- 1169249 -->

Microsoft Intune ile tümleşik çalışan Mobile Threat Defense çözümü Pradeo tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihazlardan şirket kaynaklarına erişimi denetleyebilirsiniz.

## <a name="week-of-june-18-2018"></a>18 Haziran 2018 haftası

### <a name="edge-mobile-support-for-intune-app-protection-policies----1817882---"></a>Intune uygulama koruma ilkeleri için Edge mobil desteği <!-- 1817882 -->

Mobil cihazlar için Microsoft Edge tarayıcısı, artık Intune’da tanımlanan uygulama koruma ilkelerini destekliyor.

## <a name="week-of-june-11-2018"></a>11 Haziran 2018 haftası

### <a name="use-fips-mode-with-the-ndes-certificate-connector----1333688---"></a>NDES Sertifika bağlayıcısında FIPS modunu kullanma <!-- 1333688 -->
NDES Sertifika bağlayıcısını Federal Bilgi İşleme Standardı (FIPS) modu etkin bir bilgisayara yüklediğinizde, sertifika verme ve iptal etme işlemleri beklendiği gibi çalışmıyordu. Bu güncelleştirmeyle birlikte FIPS desteği, NDES Sertifika bağlayıcısına eklenmiştir. 

Bu güncelleştirme ayrıca şunları içerir:

- NDES Sertifika bağlayıcısı; Windows Server 2016 ve Windows Server 2012 R2’ye otomatik olarak dahil edilen .NET 4.5 Framework’ü gerektirir. Önceden .NET 3.5 Framework, gereken en düşük sürümdü.
- TLS 1.2 desteği, NDES Sertifika Bağlayıcısına dahil edilmiştir. Bu nedenle NDES Sertifika bağlayıcısı yüklü olan sunucu TLS 1.2’yi destekliyorsa TLS 1.2 kullanılır. Sunucu TLS 1.2 desteklemiyorsa TLS 1.1 kullanılır. Şu anda TLS 1.1, cihazlar ve sunucu arasında kimlik doğrulaması için kullanılmaktadır.

Daha fazla bilgi için bkz. [SCEP sertifikalarını yapılandırma ve kullanma](certificates-scep-configure.md) ve [PKCS sertifikalarını yapılandırma ve kullanma](certficates-pfx-configure.md).

## <a name="week-of-june-4-2018"></a>4 Haziran 2018 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="retrieve-the-associated-app-user-model-id-aumid-for-microsoft-store-for-business-apps-in-kiosk-mode----1560077----"></a>İş İçin Microsoft Store uygulamaları için bilgi noktası modunda ilişkili uygulama kullanıcı model kimliğini (AUMID) alma <!-- 1560077 ! -->
Intune artık bilgi noktası profilinde daha iyi bir yapılandırma sağlamak amacıyla İş İçin Microsoft Store (WSfB) uygulamaları için uygulama kullanıcı model kimliğini (AUMID) alabilir.

İş İçin Microsoft Store uygulamaları hakkında daha fazla bilgi için bkz. [İş İçin Microsoft Store’dan uygulamaları yönetme](windows-store-for-business.md).

#### <a name="new-company-portal-branding-page----1916370---"></a>Yeni Şirket Portalı markalama sayfası <!-- 1916370 -->
Şirket Portalı markalama sayfasının yeni bir düzeni, iletileri ve araç ipuçları vardır.


### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="support-for-palo-alto-networks-globalprotect-vpn-profiles----1333680-eeready----"></a>Palo Alto Networks GlobalProtect VPN profilleri için destek <!-- 1333680 eeready ! -->
Bu güncelleştirme ile Intune’da VPN profilleri için VPN bağlantısı olarak Palo Alto Networks GlobalProtect’i seçebilirsiniz (**Cihaz yapılandırması** > **Profiller** > **Profil oluştur** > **Profil türü** > **VPN**). Bu sürümde aşağıdaki platformlar desteklenir: 

- iOS
- Windows 10

#### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Yerel Cihaz Güvenliği Seçenekleri ayarlarına ekler <!-- 1403702 -->
Artık Windows 10 cihazları için ek Yerel Cihaz Güvenliği Seçenekleri ayarları yapılandırabilirsiniz. Ek ayarlar; Microsoft Ağ İstemcisi, Microsoft Ağ Sunucusu, Ağ erişimi ve güvenlik ve Etkileşimli oturum açma bölümlerinde kullanılabilir. Bu ayarları, bir Windows 10 cihaz yapılandırma ilkesi oluşturduğunuzda Endpoint Protection kategorisinde bulabilirsiniz.

#### <a name="enable-kiosk-mode-on-windows-10-devices----1560072----"></a>Windows 10 cihazlarda bilgi noktası modunu etkinleştirme <!-- 1560072 ! -->
Windows 10 cihazlarda bir yapılandırma profili oluşturabilir ve bilgi noktası modunu etkinleştirebilirsiniz (**Cihaz Yapılandırması** > **Profiller** > **Profil oluştur** > **Windows 10** > **Cihaz Kısıtlamaları** > **Bilgi noktası**). Bu güncelleştirmede **Bilgi noktası (önizleme)** ayarı, **Bilgi noktası (kullanılmayan)** olarak yeniden adlandırıldı. **Bilgi noktası (kullanılmayan)**, artık kullanım için önerilmese de Temmuz güncelleştirmesine kadar işlevselliğini koruyacaktır. **Bilgi noktası (kullanılmayan)**, yeni **Bilgi noktası** türü (**Profil oluştur** > **Windows 10** > **Bilgi noktası (önizleme)**) ile değiştirilmiştir. Bu yeni tür, Windows 10 RS4 ve üzeri sürümlerde Bilgi Noktalarını yapılandırmak üzere ayarlar içerecektir.

Windows 10 ve üzeri için geçerlidir.

#### <a name="device-profile-graphical-user-chart-is-back----2160133---"></a>Cihaz profili kullanıcı grafiği geri geldi <!-- 2160133 -->
Cihaz profili grafiğinde (**Cihaz yapılandırması** > **Profiller** > mevcut bir profil seçin > **Genel bakış**) gösterilen sayısal değerleri geliştirirken, kullanıcı grafiği geçici olarak kaldırılmıştı.

Bu güncelleştirmeyle birlikte kullanıcı grafiği geri geldi ve Azure portalında gösteriliyor.

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="support-for-windows-autopilot-enrollment-without-user-authentication----1165118-wnready---"></a>Kullanıcı kimlik doğrulaması olmadan Windows Autopilot kaydı desteği <!-- 1165118 wnready -->
Intune şimdi kullanıcı kimlik doğrulaması olmadan Windows Autopilot kaydını destekliyor. Bu, Windows Autopilot dağıtım profilinde "Autopilot Dağıtım modu" değerinin "Kendi Kendine Dağıtım" olduğu yeni bir seçenektir.  Bu kayıt türünü başarıyla tamamlamak için cihaz, Windows 10 Insider Preview Derleme 17672 veya üzeri çalıştırmalı ve TPM 2.0 yongasına sahip olmalıdır. Kullanıcı kimlik doğrulaması gerekmediğinden, bu seçeneği yalnızca üzerinde fiziksel denetim sahibi olduğunuz cihazlara atamalısınız.

#### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot----1821766-eeready---"></a>Autopilot için OOBE yapılandırırken yeni dil / bölge ayarı <!-- 1821766 eeready -->
Autopilot profilleri için İlk Çalıştırma Deneyimi sırasında dili ve bölgeyi ayarlamak için yeni bir yapılandırma ayarı kullanılabilir. Yeni ayarı görmek için, **Cihaz kaydı** > **Windows kaydı** > **Dağıtım profilleri** > **Profil oluştur** > **Dağıtım modu** = **Kendi kendine dağıtım** > **Varsayılanlar yapılandırıldı** öğesini seçin.

#### <a name="new-setting-for-configuring-device-keyboard----1821768---"></a>Cihaz klavyesini yapılandırmak için yeni ayar <!-- 1821768 -->
Autopilot profilleri için İlk Çalıştırma Deneyimi sırasında klavyeyi yapılandırmak için yeni bir ayar kullanılabilir olacak. Yeni ayarı görmek için, **Cihaz kaydı** > **Windows kaydı** > **Dağıtım profilleri** > **Profil oluştur** > **Dağıtım modu** = **Kendi kendine dağıtım** > **Varsayılanlar yapılandırıldı** öğesini seçin.

#### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Autopilot profilleri grup hedeflemeye taşınıyor <!-- 1877935 -->
AutoPilot dağıtım profilleri AutoPilot cihazları içeren Azure AD gruplarına atanabilir.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="set-compliance-by-device-location----851881----"></a>Cihaz konumuna göre uyumluluk ayarlama <!-- 851881 ! -->
Bazı durumlarda, ağ bağlantısı tarafından belirlenen bir konumdan şirket kaynaklarına erişimi kısıtlamak isteyebilirsiniz. Artık cihazın IP adresine bağlı olarak bir uyumluluk ilkesi (**Cihaz uyumluluğu** > **Konumlar**) oluşturabilirsiniz. Cihaz, IP aralığı dışına çıktığında şirket kaynaklarına erişemez.

Uygulandığı öğe: Android cihazlar 6.0 ve üzeri, güncelleştirilmiş Şirket Portalı uygulaması ile

#### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Windows 10 Enterprise RS4 Autopilot cihazlarda tüketici uygulamaları ve deneyimlerini engelleme<!-- 1621980 -->
Windows 10 Enterprise RS4 AutoPilot cihazlarınızda tüketici uygulama ve deneyimlerinin yüklenmesini önleyebileceksiniz. Bu özelliği görmek için **Intune** > **Cihaz yapılandırması** > **Profiller** > **Profil oluştur** > **Platform** = **Windows 10 veya üzeri** > **Profil türü** = **Cihaz kısıtlamaları** > **Yapılandır** > **Windows Spot** > **Tüketici özellikleri**'ne gidin. 

#### <a name="uninstall-the-latest-from-windows-10-software-updates----1732948-eeready---"></a>En son Windows 10 yazılım güncelleştirmesini kaldırma <!-- 1732948 eeready -->
Windows 10 makinelerinizde çalışmanın kesilmesine neden olan bir sorun keşfederseniz, en son özellik güncelleştirmesini veya en son kalite güncelleştirmesini kaldırmayı (geri almayı) seçebilirsiniz. Özellik veya kalite güncelleştirmesini kaldırma işlemi yalnızca hizmetin içinde açıldığı hizmet kanalında kullanılabilir. Kaldırma işlemi Windows 10 makinelerinizde önceki güncelleştirmeyi geri yüklemeye yönelik bir ilkeyi tetikler. Özellik güncelleştirmeleri için, en son sürümü kaldırma işleminin uygulanabilme süresini 2-60 gün arasıyla sınırlandırabilirsiniz. Yazılım güncelleştirmesini kaldırma seçeneklerini ayarlamak için, Azure portalının içindeki **Microsoft Intune** dikey penceresinden **Yazılım güncelleştirmeleri**'ni seçin. Ardından, **Yazılım güncelleştirmeleri** dikey penceresinden **Windows 10 Güncelleştirme Kademeleri**'ni seçin. Daha sonra da **Genel Bakış** bölümünde **Kaldır** seçeneğini belirtebilirsiniz.

#### <a name="search-all-devices-for-imei-and-serial-number----1793685---"></a>IMEI ve seri numarası için tüm cihazlarda arama yapma <!-- 1793685 -->
Artık Tüm cihazlar dikey penceresinde IMEI ve seri numaraları için arama yapabilirsiniz (e-posta, UPN, cihaz adı ve yönetim adı da hala kullanılabilir). Intune'da **Cihazlar** > **Tüm cihazlar**'ı seçin ve arama kutusuna aramanızı girin.

#### <a name="management-name-field-will-be-editable----1875989---"></a>Yönetim adı alanı düzenlenebilir olacak <!-- 1875989 -->
Artık bir cihazın **Özellikler** dikey penceresindeki yönetim adı alanını düzenleyebilirsiniz. Bu alanı düzenlemek için **Cihazlar** > **Tüm cihazlar** > cihazı seçin > **Özellikler** seçeneğini belirleyin. Bir cihazı benzersiz olarak tanımlamak için yönetim adı alanını kullanabilirsiniz.

#### <a name="new-all-devices-filter-device-category----1878520---"></a>Yeni Tüm cihazlar filtresi: Cihaz kategorisi <!-- 1878520 -->
Şimdi **Tüm cihazlar** listesini cihaz kategorisine göre filtreleyebilirsiniz. Bunu yapmak için, **Cihazlar** > **Tüm cihazlar** > **Filtre** > **Cihaz kategorisi**'ni seçin.

#### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices----1985547---"></a>iOS ve MacOS cihazlarda ekran paylaşımı için TeamViewer kullanma <!-- 1985547 -->
Artık yöneticiler, [TeamViewer](device-profile-android-teamviewer.md)’a bağlanıp iOS ve macOS cihazlarla bir ekran paylaşma oturumu başlatabilir. iPhone, iPad ve macOS kullanıcıları, diğer herhangi bir masaüstü veya mobil cihazla ekranlarını canlı olarak paylaşabilecek. 

#### <a name="multiple-exchange-connector-support----2070451---"></a>Birden çok Exchange Connector desteği <!-- 2070451 -->
Artık kiracı başına tek bir Microsoft Intune Exchange Connector’la sınırlı değilsiniz. Intune, birden çok Exchange Connector’ı desteklediği için Intune koşullu erişimini birden çok şirket içi Exchange kuruluşunda ayarlayabilirsiniz.

Intune şirket içi Exchange bağlayıcısıyla, cihazın Intune'a kayıtlı olup olmadığına ve Intune cihaz uyumluluk ilkelerine uyup uymadığına bağlı olarak şirket içi Exchange posta kutularınıza cihaz erişimini ayarlayabilirsiniz. Bağlayıcıyı ayarlamak için, Intune şirket içi Exchange bağlayıcısını Azure portalından indirir ve Exchange kuruluşunuzdaki bir sunucuya yüklersiniz. Microsoft Intune panosunda **Şirket içi erişim**'i seçin ve ardından **Kurulum**'un altında **Exchange ActiveSync bağlayıcısı**'nı seçin. Exchange şirket içi bağlayıcısını indirin ve Exchange kuruluşunuzdaki bir sunucuya yükleyin. Artık kiracı başına tek Exchange bağlayıcısıyla sınırlı olmadığınıza göre, başka Exchange kuruluşlarınız varsa her ek Exchange kuruluşu için aynı süreci izleyip bağlayıcı indirebilir ve yükleyebilirsiniz.

#### <a name="new-device-hardware-detail-ccid----2156657---"></a>Yeni cihaz donanım ayrıntısı: CCID <!-- 2156657 -->
Çip Kartı Arabirim Cihazı (CCID) bilgileri şimdi her cihaza eklendi. Bunu görmek için, **Cihazlar** > **Tüm cihazlar**'ı seçin, bir cihaz belirtin, **Donanım**'ı seçin ve **Ağ ayrıntıları**>'nın altına bakın.

#### <a name="assign-all-users-and-all-devices-as-scope-groups----2196803---"></a>Tüm kullanıcıları ve tüm cihazları kapsam grupları olarak atama <!-- 2196803 -->
Şimdi tüm kullanıcıları, tüm cihazları ve tüm kullanıcılar ile tüm cihazları kapsam gruplarına atayabilirsiniz. Bunu yapmak için **Intune rolleri** > **Tüm roller** > **İlke ve profil yöneticisi** > **Atamalar** > atama seçin > **Kapsam (gruplar)** öğesini seçin.

#### <a name="udid-information-now-included-for-ios-and-macos-devices----2219806-wnready--"></a>Şimdi iOS ve macOS cihazlar için UDID bilgileri eklendi <!-- 2219806 wnready-->
iOS ve macOS cihazlarının Benzersiz Cihaz Tanımlayıcısını (UDID) görmek için, **Cihazlar** > **Tüm cihazlar** > cihaz seçin > **Donanım**'a gidin. UDID yalnızca şirket cihazları için sağlanır (şirket cihazları **Cihazlar** > **Tüm cihazlar** > bir cihaz seçin > **Özellikler** > **Cihaz sahipliği** altında ayarlanır).

### <a name="intune-apps"></a>Intune uygulamaları

#### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Uygulama yüklemesi için geliştirilmiş sorun giderme <!-- 928990 -->
Microsoft Intune MDM ile yönetilen cihazlarda bazen uygulama yüklemeleri başarısız olabilir. Bu uygulamaların yüklemesi başarısız olduğunda, başarısızlık sebebini anlamak ve sorunu gidermek zor olabilir. Uygulama Sorun Giderme özelliklerimizin bir Genel Önizlemesini yayınlıyoruz. Tüm cihazlarda **Yönetilen Uygulamalar** adlı yeni bir düğüm göreceksiniz. Bu düğümde Intune MDM yoluyla teslim edilen uygulamalar listelenir. Burada uygulama yükleme durumlarının bir listesini bulacaksınız. Bir uygulamayı seçtiğinizde, o uygulamaya özel sorun giderme görünümünü açmış olacaksınız. Sorun giderme görünümünde uygulamanın oluşturulma, değiştirilme, hedeflenme ve cihaza teslim edilme tarihleri gibi uçtan uca yaşam döngüsünü bulabileceksiniz. Buna ek olarak, uygulama yüklemesinin başarısız olması durumunda size bir hata kodu ve hatanın sebebiyle ilgili yardım olacak bir ileti sunulacak. 

#### <a name="intune-app-protection-policies-and-microsoft-edge----1818968---"></a>Intune uygulama koruma ilkeleri ve Microsoft Edge <!-- 1818968 -->
Mobil cihazlar (iOS ve Android) için Microsoft Edge tarayıcısı, artık Microsoft Intune uygulama koruma ilkelerini destekliyor. Şirket Azure AD hesaplarıyla Edge uygulamasında oturum açan iOS ve Android cihazı kullanıcıları, Intune tarafından korunacak. iOS cihazlarında, **Web içeriği için yönetilen tarayıcı iste** ilkesi Edge yönetildiğinde kullanıcıların bu tarayıcıda bağlantı açmasına olanak tanıyacak.

## <a name="week-of-may-14-2018"></a>14 Mayıs 2018 Haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>İlkelerin, uygulamaların, sertifika ve ağ profillerinin yüklenmesini gerektirme <!-- 1553555 -->

Intune, AutoPilot cihazlar sağlanırken ilkeleri, uygulamaları ve sertifika ve ağ profillerini yükleyene kadar yöneticiler; son kullanıcıların Windows 10 RS4 masaüstüne erişimini engelleyebilecek. Daha fazla bilgi için bkz. [Kayıt durum sayfası ayarlama](windows-enrollment-status.md).

#### <a name="configuring-your-app-protection-policies----2144597-part-2---"></a>Uygulama koruma ilkelerinizi yapılandırma <!-- 2144597 Part 2 -->

Azure portalında, Intune Uygulama Koruması hizmet dikey penceresine gitmek yerine artık yalnızca Intune’a gidersiniz. Intune içinde artık uygulama koruma ilkeleri için yalnızca bir konum bulunur. Tüm uygulama koruma ilkelerinizin Intune’da **Uygulama koruma ilkeleri** altındaki **Mobil uygulama** dikey penceresinde olduğuna dikkat edin. Bu tümleştirme, bulut yönetim idaresini basitleştirmenize yardımcı olur. Tüm uygulama koruma ilkelerinin zaten Intune’da olduğunu ve önceden yapılandırılan tüm ilkelerinizi değiştirebileceğinizi unutmayın. Intune Uygulama İlkesi Koruma (APP) ve Koşullu Erişim (CA) ilkeleri artık **Microsoft Intune** dikey penceresinin **Yönet** bölümü altında veya **Azure Active Directory** dikey penceresinin **Güvenlik** bölümü altında bulunan **Koşullu Erişim** bölümü altındadır. Koşullu erişim ilkelerini değiştirme hakkında daha fazla bilgi için bkz. [Azure Active Directory’de koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). Daha fazla bilgi için bkz. [Uygulama koruma ilkeleri nedir?](app-protection-policy.md)

## <a name="week-of-may-7-2018"></a>7 Mayıs 2018 Haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="samsung-knox-mobile-enrollment-support---1112863--"></a>Samsung Knox mobil kayıt desteği <!--1112863-->

Intune’u Samsung Knox Mobil Kayıt (KME) ile birlikte kullanarak çok sayıda şirkete ait Android cihazları kaydedebilirsiniz. WiFi veya hücresel ağ kullanan kullanıcılar, cihazlarını ilk kez açtıklarında yalnızca birkaç dokunuşla kayıt yapabilir. Knox Dağıtım Uygulaması’nı kullanırken Bluetooth veya NFC yoluyla cihazlar kaydedilebilir. Daha fazla bilgi için bkz. [Android cihazları Samsung’un Knox Mobil Kayıt özelliğini kullanarak otomatik kaydetme](android-samsung-knox-mobile-enroll.md).

#### <a name="requesting-help-in-the-company-portal-for-windows-10----1874137---"></a>Windows 10 için Şirket Portalı uygulamasında yardım isteme <!-- 1874137 -->

Kullanıcı bir sorun hakkında yardım almak için iş akışı başlattığında Windows 10 için Şirket Portalı uygulaması artık uygulama günlüklerini doğrudan Microsoft’a gönderecek. Böylece Microsoft’a bildirilen sorunların giderilmesi ve çözülmesi daha kolay olacak.

## <a name="week-of-april-23-2018"></a>23 Nisan 2018 Haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>Android’de MAM PIN’i için geçiş kodu desteği<!-- 1438086 -->

Intune yöneticileri, sayısal MAM PIN’i yerine geçiş kodu zorlamak için bir uygulama başlatma gereksinimi ayarlayabilir. Bu gereksinim ayarlanırsa kullanıcının, MAM etkin uygulamalara erişim almadan önce bir geçiş kodu ayarlaması ve istendiğinde bunu kullanması gerekir. Geçiş kodu, en az bir özel karakter veya büyük/küçük harf içeren sayısal PIN’dir. Intune, sayısal PIN’e benzer bir şekilde geçiş kodunu destekler. Uzunluk alt sınırı belirler ve yönetici konsolunda karakter ile dizi tekrarlarına izin verir. Bu özellik, Android’de Şirket Portalı’nın en son sürümünü gerektirir. Bu özellik, iOS için zaten kullanılabilir durumdadır.

#### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>macOS için iş kolu (LOB) uygulamaları desteği <!-- 1473977 -->
Microsoft Intune, macOS LOB uygulamalarını Azure portalından yükleme olanağı sağlayacak. GitHub’da bulunan araç tarafından ön işlemden geçtikten sonra macOS LOB uygulamasını Intune’a ekleyebileceksiniz. Azure portalının **Intune** dikey penceresinden **Mobil uygulamalar**’ı seçin. **Mobil uygulamalar** dikey penceresinde **Uygulamalar** > **Ekle**’yi seçin. **Uygulama Ekle** dikey penceresinde, **İş kolu uygulaması**’nı seçin. 

#### <a name="built-in-all-users-and-all-devices-group-for-android-for-work-afw-app-assignment----1813073---"></a>Android for Work (AFW) uygulama atamasında Yerleşik Tüm Kullanıcılar ve Tüm Cihazlar Grubu <!-- 1813073 -->
AFW uygulama ataması için yerleşik **Tüm Kullanıcılar** ve **Tüm Cihazlar** gruplarından yararlanabilirsiniz. Daha fazla bilgi için bkz. [Microsoft Intune’da uygulama atamalarını dahil etme ve dışlama](apps-inc-exl-assignments.md).

#### <a name="intune-will-reinstall-required-apps-that-are-uninstalled-by-users----1947010---"></a>Intune, kullanıcılar tarafından kaldırılan gerekli uygulamaları yeniden yükleyecek <!-- 1947010 -->
Son kullanıcı gerekli bir uygulamayı kaldırırsa Intune, 7 günlük yeniden değerlendirme döngüsünü beklemek yerine 24 saat içerisinde bu uygulamayı otomatik olarak yeniden yükler.

### <a name="device-configuration"></a>Cihaz yapılandırması

####  <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group----1449153-eeready---"></a>Cihaz profil grafiği ve durum listesi bir gruptaki tüm cihazları gösterir <!-- 1449153 eeready -->
Bir cihaz profili yapılandırdığınızda (**Cihaz yapılandırması** > **Profiller**), iOS gibi bir cihaz profili seçersiniz. Bu profili, iOS ve iOS olmayan cihazlar barındıran bir gruba atarsınız. Grafikteki sayı, profilin uygulandığı iOS *ve* iOS olmayan cihazları gösterir (**Cihaz yapılandırması** > **Profiller** > mevcut bir profili seçin > **Genel bakış**). **Genel bakış** sekmesinde grafiği seçtiğinizde, **Cihaz durumu** yalnızca gruptaki iOS cihazları değil, tüm cihazları listeler. 

Bu güncelleştirme ile grafik (**Cihaz yapılandırması** > **Profiller** > mevcut bir profili seçin > **Genel bakış**) yalnızca belirli bir cihaz profili sayısını gösterir. Örneğin yapılandırma cihaz profili iOS cihazlarda geçerliyse grafik yalnızca iOS cihaz sayısını gösterecek. Grafik seçilip **Cihaz durumu** açıldığında yalnızca iOS cihazlar listelenecek.

Bu güncelleştirme hazırlanırken kullanıcı grafiği geçici olarak kaldırılmıştır. 

#### <a name="always-on-vpn-for-windows-10---1333666---"></a>Windows 10 için Her Zaman Açık VPN <!--1333666 -->

Şu anda [Her Zaman Açık](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on), OMA-URI kullanarak oluşturulmuş özel bir sanal özel ağ (VPN) profili ile Windows 10 cihazlarda kullanılabiliyor.

Bu güncelleştirmeyle yöneticiler, Windows 10 VPN profilleri için Her Zaman Açık’ı doğrudan Azure portalındaki Intune’da etkinleştirebilir. Her Zaman Açık VPN profilleri şu durumlarda otomatik olarak bağlanacak:

- Kullanıcılar cihazlarında oturum açtığında
- Cihazdaki ağ değiştiğinde
- Cihaz ekranı kapandıktan sonra yeniden açıldığında

#### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Eğitim profilleri için yeni yazıcı ayarları <!-- 1308900 -->

Eğitim profilleri için yeni ayarlar, **Yazıcılar** kategori: **Yazıcılar**, **Varsayılan yazıcı**, **Yeni yazıcı ekle** altında sağlanır.

#### <a name="show-caller-id-in-personal-profile---android-for-work---1098984---"></a>Kişisel profilde arayan kimliğini gösterme - Android for Work <!--1098984 -->
Bir cihazda kişisel profil kullanan son kullanıcılar, bir iş kişisinden gelen aramalarda arayan kimliğini göremeyebilir. 

Bu güncelleştirme ile **Android for Work** > **Cihaz kısıtlamaları** > **İş profili ayarları** kısmına bunun için yeni bir ayar geldi:
- Kişisel profilde iş kişisi arayan kimliğini görüntüleme

Etkinleştirildiğinde (yapılandırılmadığında), iş kişisi arayan ayrıntıları kişisel profilde görüntülenir. Engellendiğinde ise iş kişisi arayan numarası kişisel profilde görüntülenmez. 

Şunlar için geçerlidir: Android OS v6.0 ve üzeri sürümlerde Android iş profili cihazları

#### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252-----from-1802-and-1804--"></a>Endpoint Protection ayarlarına yeni Windows Defender Credential Guard ayarları eklendi <!--1102252 --><!--from 1802 and 1804-->

Bu güncelleştirmeyle, [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard) (**Cihaz yapılandırması** > **Profiller** > **Endpoint Protection**) aşağıdaki ayarları içerir: 

- **Windows Defender Credential Guard**: Credential Guard'ı sanallaştırma tabanlı güvenlikle açar. Bu özelliğin etkinleştirilmesi, **Güvenli Önyükleme ile Platform Güvenlik Düzeyi** ve **Sanallaştırma Tabanlı Güvenlik** ayarının her ikisi de etkinleştirildiğinde bir sonraki önyüklemede kimlik bilgilerinin korunmasına yardımcı olur. Şu seçenekler mevcuttur:
  - **Devre Dışı**: Credential Guard daha önce **Kilitsiz etkin**" seçeneğiyle açıldıysa, Credential Guard'ı uzaktan kapatır.

  - **UEFI kilidi ile etkin**: Credential Guard’ın kayıt defteri anahtarı veya Grup İlkesi kullanılarak devre dışı bırakılamamasını sağlar. Bu ayarı kullandıktan sonra Credential Guard'ı devre dışı bırakmak için, Grup İlkesi'ni "Devre Dışı" olarak ayarlamalısınız. Ardından, fiziksel olarak kullanıcısı olan her bilgisayardan güvenlik işlevselliğini kaldırın. Bu adımlar UEFI'de kalıcı olan yapılandırmayı temizler. UEFI yapılandırması devam ettiği sürece, Credential Guard etkindir.

  - **Kilitsiz etkin**: Credential Guard’ın Grup İlkesi kullanılarak uzaktan devre dışı bırakılmasına olanak tanır. Bu ayarı kullanan cihazların en az Windows 10 (Sürüm 1511) çalıştırıyor olması gerekir.

Credential Guard yapılandırılırken aşağıdaki bağımlı teknolojiler otomatik olarak etkinleştirilir: 

  - **Sanallaştırma Tabanlı Güvenliği (VBS) etkinleştir**: Bir sonraki yeniden başlatmada sanallaştırma tabanlı güvenliği (VBS) açar. Sanallaştırma tabanlı güvenlik, güvenlik hizmetlerine destek sağlamak için Windows Hiper Yöneticisi'ni kullanır ve Güvenli Önyükleme gerektirir.
  - **Doğrudan Bellek Erişimi (DMA) ile Güvenli Önyükleme**: VBS'yi Güvenli Önyükleme ve doğrudan bellek erişimi ile açar. DMA korumaları donanım desteği gerektirir ve yalnızca düzgün yapılandırılmış cihazlarda etkinleştirilir. 

#### <a name="use-a-custom-subject-name-on-scep-certificate----2064190---"></a>SCEP sertifikasında özel bir konu adı kullanma <!-- 2064190 -->
Bir SCEP sertifika profilinde özel bir konuda **OnPremisesSamAccountName** ortak adını kullanabilirsiniz. Örneğin `CN={OnPremisesSamAccountName})` kullanabilirsiniz.

####  <a name="block-camera-and-screen-captures-on-android-for-work----1098977-eeready--"></a>Android for Work’te kamera ve ekran yakalamayı engelleme <!-- 1098977 eeready-->
Android cihazlar için cihaz kısıtlamaları yapılandırırken iki yeni engelleme özelliği kullanılabilir: 
- Kamera: Cihazdaki tüm kameralara erişimi engeller
- Ekran yakalama: Ekran yakalamayı ve güvenli bir video çıkışına sahip olmayan görüntü cihazlarında gösterilen içeriği engeller

Android for Work’te geçerlidir.


### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>macOS High Sierra 10.13.2+ cihazların kullanıcıları için yeni kayıt adımları <!--1734567 -->
macOS High Sierra 10.13.2, “Kullanıcı Onaylı” MDM kaydı kavramını sundu. Onaylı kayıtlar, Intune’un güvenlik açısından hassas bazı ayarları yönetmesine izin verir. Daha fazla bilgi için Apple’ın destek belgelerine bakın: https://support.apple.com/HT208019.

macOS Şirket Portalı kullanarak kaydedilen cihazlar, son kullanıcı Sistem Tercihleri’ni açıp kendisi onay sağlamadığı sürece “Kullanıcı Onaylı Değil” olarak değerlendirilir. Bu nedenle macOS Şirket Portalı, macOS 10.13.2 ve üzeri cihazlardaki kullanıcıları artık kayıt işleminin sonunda kayıtlarını kendileri onaylamaları için yönlendiriyor. Kayıtlı bir cihaz, kullanıcı onaylı hale gelirse Intune yönetici konsolu bunu rapor eder.



### <a name="device-management"></a>Cihaz yönetimi

#### <a name="advanced-threat-protection-atp-and-intune-are-fully-integrated----eeready-1629303---"></a>Gelişmiş Tehdit Koruması (ATP) ve Intune tamamen tümleştirilmiştir <!-- EEready 1629303 -->

[Gelişmiş Tehdit Koruması (ATP)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection), Windows 10 cihazların risk düzeyini gösterir. Windows Defender Güvenlik Merkezi'nde (ATP portalı), Microsoft Intune'a bir bağlantı oluşturabilirsiniz. Oluşturulduktan sonra, kabul edilebilir tehdit düzeyini saptamak için bir Intune uyumluluk ilkesi kullanılır. Tehdit düzeyi aşılırsa, Azure Active Directory (AD) koşullu erişim ilkesi kuruluşunuz içindeki farklı uygulamalara erişimi engelleyebilir.

Bu özellik Windows 10 cihazlarınızda ATP'nin dosyaları taramasına, tehditleri algılamasına ve riskleri raporlamasına olanak tanır.

Bkz. [Intune’da ATP’yi koşullu erişim ile etkinleştirme](advanced-threat-protection.md).

#### <a name="support-for-user-less-devices----1637553---"></a>Kullanıcısız cihazlar için destek <!-- 1637553 -->
Intune, Microsoft Surface Hub gibi bir kullanıcısız cihazda uyumluluk değerlendirme işlevini destekler. Uyumluluk ilkesi, belirli cihazları hedefleyebilir. Böylece ilişkili kullanıcısı olmayan cihazlar için uyumluluk (ve uyumsuzluk) belirlenebilir.

#### <a name="delete-autopilot-devices----1713650---"></a>Autopilot cihazları silme <!-- 1713650 -->
Intune yöneticileri, [Autopilot cihazlarını silebilir](enrollment-autopilot.md#delete-autopilot-devices).

#### <a name="improved-device-deletion-experience---1832333---"></a>Geliştirilmiş cihaz silme deneyimi <!--1832333 -->
Artık [bir cihazı Intune’dan silmeden](devices-wipe.md#delete-devices-from-the-intune-portal) önce şirket verilerini kaldırmanız veya cihazı fabrika ayarlarına sıfırlamanız istenmez.

Yeni deneyimi görmek için Intune’da oturum açın ve şunları seçin: **Cihazlar** > **Tüm cihazlar** > cihazın adı > **Sil**.

Yine de onayı silmek/devre dışı bırakmak istiyorsanız **Sil** demeden önce standart yaşam döngüsü yolunu izleyip **Şirket verilerini kaldır** ve **Fabrika Sıfırlaması** seçeneklerini kullanabilirsiniz. 

#### <a name="play-sounds-on-ios-when-in-lost-mode----1947769---"></a>Kayıp modundayken iOS cihazda ses çalma <!-- 1947769 -->
Denetimli iOS cihazları, Mobil Cihaz Yönetimi (MDM) [Kayıp Modu](device-lost-mode.md)’ndayken bir [ses çalabilirsiniz](device-locate.md#activate-lost-mode-sound-alert-on-an-ios-device) (**Cihazlar** > **Tüm cihazlar** > bir iOS cihaz seçin > **Genel Bakış** > **Diğer**). Ses, cihaz Kayıp modundan çıkarılana veya kullanıcı sesi cihazda devre dışı bırakana kadar çalmaya devam eder. iOS 9.3 ve üzeri cihazlarda geçerlidir.

#### <a name="block-or-allow-web-results-in-searches-made-on-an-intune-device---1972804--"></a>Intune cihazında yapılan aramalarda web sonuçlarını engelleme veya bu sonuçlara izin verme <!--1972804-->

Yöneticiler şimdi cihazda yapılan aramalarda web sonuçlarını engelleyebilir.

#### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure----2172331---"></a>Apple MDM Anında İletme Sertifikası karşıya yükleme başarısızlığı için iyileştirilmiş hata iletisi <!-- 2172331 -->

Hata iletisi, mevcut bir MDM sertifikası yenilenirken aynı Apple kimliğinin kullanılması gerektiğini açıklar.

#### <a name="test-the-company-portal-for-macos-on-virtual-machines----2216679---"></a>Sanal makinelerde macOS için Şirket Portalı'nı test etme <!-- 2216679 -->

BT yöneticilerinin Parallels Desktop ve VMware Fusion'daki sanal makinelerde macOS için Şirket Portalı uygulamasını test etmelerine yardımcı olacak kılavuzlar yayımladık. [Sanal macOS makinelerini test için kaydetme](macos-enroll.md#enroll-virtual-macos-machines-for-testing) başlığı altında daha fazla bilgi bulabilirsiniz.


### <a name="user-interface"></a>Kullanıcı arabirimi

#### <a name="improved-device-tiles-in-the-windows-10-company-portal---2213364---"></a>Windows 10 Şirket Portalı'nda geliştirilmiş cihaz kutucuları <!--2213364 -->

Kutucuklar görme sorunu olan kullanıcılar açısından daha erişilebilir olacak ve ekran okuma araçlarının daha iyi çalışmasını sağlayacak şekilde güncelleştirildi.

#### <a name="send-diagnostic-reports-in-company-portal-app-for-macos----2216677---"></a>macOS için Şirket Portalı uygulamasında tanılama raporu gönderme <!-- 2216677 -->
macOS cihazları için Şirket Portalı uygulaması, kullanıcıların Intune il ilgili hataları raporlama şeklini iyileştirmek için güncelleştirildi. Şirket Portalı uygulamasından çalışanlarınız şunları yapabilir:

- Tanılama raporlarını doğrudan Microsoft geliştirici ekibine gönderme.
- Bir olay kimliğini şirketinizin destek BT ekibine e-posta ile gönderme.

Daha fazla bilgi için bkz. [macOS için hataları gönderme](/intune-user-help/send-errors-macos).

#### <a name="intune-adapts-to-fluent-design-system-in-the-company-portal-app-for-windows-10----1195010-wnready---"></a>Intune, Windows 10 için Şirket Portalı uygulamasında Fluent Design System'e uyum sağlar <!-- 1195010 WNready -->
Windows 10 için Intune Şirket Portalı, [Fluent Design System'in gezinti görünümü](https://docs.microsoft.com/en-us/windows/uwp/design/basics/navigation-basics) ile güncelleştirildi. Uygulamanın yan tarafı boyunca tüm en üst düzey sayfaların statik, dikey bir listesini göreceksiniz. Sayfaları hızla görüntülemek ve aralarında geçiş yapmak için herhangi bir bağlantıya tıklayın. Bu, Intune'da sürekli daha iyi uyarlanmış, anlayışlı ve tanıdık bir deneyim oluşturma çabalarımız kapsamında göreceğiniz birkaç güncelleştirmeden ilkidir. Güncelleştirilmiş görünümü görmek için [Uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md)’e gidin.

## <a name="week-of-april-16-2018"></a>16 Nisan 2018 Haftası

#### <a name="use-cisco-anyconnect-client-for-ios----eeready-1333708---"></a>iOS için Cisco AnyConnect istemcisini kullanma <!-- EEready 1333708 -->

iOS için yeni bir VPN profili oluştururken, şimdi iki seçenek vardır: **Cisco AnyConnect** ve **Cisco Eski AnyConnect**. Cisco AnyConnect profilleri 4.0.7x ve daha yeni sürümleri destekler. Mevcut iOS Cisco AnyConnect VPN profilleri **Cisco Eski AnyConnect** olarak etiketlenir ve Cisco AnyConnect 4.0.5x ve daha eski sürümlerle bugün olduğu gibi çalışmaya devam eder.

> [!NOTE]
> Bu değişiklik yalnızca iOS'ye yöneliktir. Android, Android for Work ve macOS platformlarında yine tek Cisco AnyConnect seçeneği olacaktır.

#### <a name="jamf-enrolled-macos-devices-can-now-register-with-intune----2370684---"></a>Jamf'ye kayıtlı macOS cihazları artık Intune ile kaydedilebilir <!-- 2370684 -->

macOS şirket portalının 1.3 ve 1.4 sürümleri Jamf cihazlarını Intune ile başarılı bir şekilde kaydedemiyordu. macOS portalının 1.4.2 sürümünde bu sorun çözüldü.


## <a name="week-of-april-9-2018"></a>9 Nisan 2018 Haftası  
#### <a name="updated-help-experience-in-company-portal-app-for-android----1631531---"></a>Android için Şirket Portalı uygulamasında güncelleştirilmiş yardım deneyimi <!-- 1631531 -->

Android platformuna yönelik en iyi uygulamalarla uyumlu olacak şekilde, Android için Şirket Portalı uygulamasında yardım deneyimini güncelleştirdik. Artık kullanıcılar uygulamada bir sorunla karşılaştıklarında **Menü** > **Yardım**’a dokunarak şunları yapabilir:
- Microsoft’a tanılama günlükleri yükleme.
- Sorunu açıklayan ve olay kimliğini içeren bir e-postayı şirket destek bölümünden birine gönderme.  

Güncelleştirilmiş deneyimi görmek için [E-posta ile günlük gönder](/intune-user-help/send-logs-to-your-it-admin-by-email-android) ve [Microsoft’a hata gönder](/intune-user-help/send-logs-to-microsoft-android)’e gidin.


#### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Yeni kayıt hatası eğilim grafiği ve hatanın nedenleri tablosu <!-- 1471783 -->

Kayıt Genel Bakış sayfasında kayıt hatalarının eğilimini ve hataların ilk beş sebebini görüntüleyebilirsiniz. Grafiğe veya tabloya tıklayarak sorun giderme tavsiyeleri ve düzeltme önerileri almak üzere ayrıntıları inceleyebilirsiniz.

#### <a name="update-where-to-configure-your-app-protection-policies----2144597---"></a>Uygulama koruma ilkelerinizi nerede yapılandıracağınızı güncelleştirme <!-- 2144597 -->

Azure portalındaki Microsoft Intune hizmetinde sizi geçici olarak **Intune Uygulama Koruma** hizmeti dikey penceresinden **Mobil uygulama** dikey penceresine yeniden yönlendireceğiz. Tüm uygulama koruma ilkelerinizin zaten Intune’da uygulama yapılandırması altındaki **Mobil uygulama** dikey penceresinde olduğuna dikkat edin. Intune Uygulama Koruması yerine yalnızca Intune’a gideceksiniz. Nisan 2018’de yeniden yönlendirmeyi durduracak ve **Intune Uygulama Koruması** hizmeti dikey penceresini tamamen kaldıracağız, böylece Intune’daki uygulama koruma ilkeleri yalnızca bir konumda bulunacak. 

**Bu değişiklik beni nasıl etkileyecek?**
Bu değişiklik, hem tek başına Intune müşterilerini hem de karma (Configuration Manager ile Intune) müşterileri etkileyecek. Bu tümleştirme, bulut yönetim idaresini basitleştirmenize yardımcı olacak.

**Bu değişikliğe hazırlanmak için ne yapmam gerek?**
Lütfen **Intune Uygulama Koruması** yerine **Intune**’u sık kullanılan olarak etiketleyin ve Intune içerisindeki **Mobil** uygulama dikey penceresinde bulunan Uygulama koruma ilkesi iş akışını inceleyin. Kısa bir süreliğine yenilen yönlendireceğiz ancak daha sonra **Uygulama Koruma** dikey penceresini kaldıracağız. Tüm uygulama koruma ilkelerinin zaten Intune’da olduğunu ve tüm koşullu erişim ilkelerinizi değiştirebileceğinizi unutmayın. Koşullu erişim ilkelerini değiştirme hakkında daha fazla bilgi için bkz. [Azure Active Directory’de koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal). Daha fazla bilgi için bkz. [Uygulama koruma ilkeleri nedir?](app-protection-policy.md) 


## <a name="week-of-april-2-2018"></a>2 Nisan 2018 Haftası

### <a name="intune-apps"></a>Intune uygulamaları

#### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866---"></a>iOS için Şirket Portalı uygulamasında kullanıcı deneyimi güncelleştirmesi <!--1412866 -->
iOS için Şirket Portalı uygulamasına büyük bir kullanıcı deneyimi güncelleştirmesi yayımladık. Güncelleştirme, modern bir görünüm ve his sağlayan yepyeni bir görsel tasarım sunmaktadır. Uygulamanın işlevselliğini korurken kullanılabilirliğini ve erişilebilirliğini artırdık.  

Şunları da göreceksiniz:
- iPhone X desteği.
- Kullanıcıların zamandan tasarruf etmesi için daha hızlı uygulama açma ve yükleme yanıtları.
- Kullanıcılara en güncel durum bilgilerini sağlamak için ek ilerleme çubukları.
- Herhangi bir sorunla karşılaşıldığında bunun daha kolay bildirilmesi için günlükleri karşıya yükleme işleminde iyileştirme.  

Güncelleştirilmiş görünümü görmek için [Uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md)’e gidin.

#### <a name="protect-on-premises-exchange-data-using-intune-app-and-ca----1056954---"></a>Intune APP ve CA kullanarak şirket içi Exchange verilerini koruma <!-- 1056954 -->
Şirket içi Exchange verilerine erişimi Outlook Mobile ile korumak için artık Intune Uygulama İlke Koruması (APP) ve Koşullu Erişim (CA) kullanabilirsiniz. Azure portalına bir uygulama koruma ilkesi eklemek veya ilkeyi değiştirmek için **Microsoft Intune** > **Mobil uygulamalar** > **Uygulama koruma ilkeleri**’ni seçin. Bu özelliği kullanmadan önce [iOS ve Android için Outlook gereksinimlerini](https://technet.microsoft.com/en-us/library/mt846639(v=exchg.160).aspx) karşıladığınızdan emin olun.

## <a name="week-of-march-26-2018"></a>26 Mart 2018 Haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="alerts-for-expiring-ios-line-of-business-lob-apps-for-microsoft-intune----748789---"></a>Microsoft Intune için süresi dolan iOS iş kolu (LOB) uygulamaları uyarıları <!-- 748789 -->

Azure portalında Intune, süresi dolmak üzere olan iOS iş kolu uygulamaları konusunda sizi uyaracaktır. iOS iş kolu uygulamasının yeni sürümü karşıya yüklenince, Intune süre sonu bildirimini uygulama listesinden kaldırır. Bu süre dolumu bildirimi yalnızca yeni yüklenmiş iOS iş kolu uygulamaları için etkin olacaktır. iOS LOB uygulama sağlama profilinin süresinin dolmasına 30 gün kala bir uyarı görünür. Süre dolduğunda uyarı, Süresi Doldu olarak değişir.

#### <a name="customize-your-company-portal-themes-with-hex-codes---1049561---"></a>Şirket Portalı temalarınızı onaltılık kodlarla özelleştirme <!--1049561 -->

Onaltılık kodlar kullanarak Şirket Portalı uygulamalarında tema rengini özelleştirebilirsiniz. Onaltılık kodunuzu girdiğinizde Intune, metin rengi ile arka plan rengi arasında en yüksek düzeyde kontrast sağlayan metin rengini belirler. **Mobil uygulamalar** > **Şirket Portalı**’nda metin renginin ve bu renk ile şirket logonuzun önizlemesini görüntüleyebilirsiniz.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Android Enterprise için gruplar temelinde uygulama atamasını dahil etme ve hariç tutma <!-- 1813081 -->

Android Enterprise (önceki adıyla Android for Work), grupları dahil etme ve hariç tutmayı destekler ancak önceden oluşturulmuş **Tüm Kullanıcılar** ve **Tüm Cihazlar** yerleşik gruplarını desteklemez. Daha fazla bilgi için bkz. [Microsoft Intune’da uygulama atamalarını dahil etme ve dışlama](apps-inc-exl-assignments.md).


### <a name="device-management"></a>Cihaz yönetimi

#### <a name="new-security-enhancements-in-the-intune-service-----1637539---"></a>Intune hizmetinde yeni güvenlik geliştirmeleri <!-- 1637539 -->   

Tek başına Intune müşterilerinin hiçbir ilke atanmamış cihazlarını **Uyumlu** (güvenlik özelliği kapalı) veya **Uyumsuz** (güvenlik özelliği açık) olarak değerlendirmesine imkan veren bir iki durumlu düğme sunduk. Böylece yalnızca cihaz uyumluluğu değerlendirildikten sonra kaynaklara erişim verilmesi sağlanacaktır.

Bu özellik, önceden atanmış uyumluluk ilkeleriniz olup olmadığına bağlı olarak sizi farklı etkileyecektir.

- Cihazlarına hiçbir uyumluluk ilkesi atanmamış yeni veya mevcut bir hesabınız varsa durum otomatik olarak **Uyumlu** şeklinde ayarlanacaktır. Konsolda bu özellik, varsayılan olarak kapalıdır. Son kullanıcılar bundan etkilenmez.
- Cihazlarına uyumluluk ilkesi atanmış mevcut bir hesabınız varsa durum otomatik olarak **Uyumsuz** şeklinde ayarlanacaktır. Özellik, Mart güncelleştirmesi dağıtılırken varsayılan olarak açıktır.

Uyumluluk ilkelerini Koşullu Erişim (CA) ile birlikte kullanıyorsanız ve bu özelliği açtıysanız kendisine en az bir uyumluluk ilkesi atanmamış cihazlarınız artık CA tarafından engellenir. Bu cihazlarla ilişkili olup bu zamana kadar e-postaya erişme izni olan kullanıcılar, tüm cihazlara en az bir uyumluluk ilkesi atamadığınız sürece erişimlerini kaybeder.   

Varsayılan ikili durum, Intune hizmeti Mart güncelleştirmeleri ile hemen kullanıcı arabiriminde gösterilmeye başlasa da bu ikili durumun doğrudan uygulanmadığına dikkat edin. Hesabınızda çalışan bir ikili durum olana kadar durumda yaptığınız değişiklikler cihaz uyumluluğunu etkilemez. Hesabınızı ayarladığımızda İleti merkezi yoluyla sizi bilgilendireceğiz. Bu işlem, Intune hizmetiniz Mart sürümüne güncelleştirildikten sonra birkaç gün sürebilir.

**Ek bilgiler**: [https://aka.ms/compliance_policies](https://aka.ms/compliance_policies)

#### <a name="enhanced-jailbreak-detection----846515---"></a>Gelişmiş jailbreak algılama <!-- 846515 -->

Gelişmiş jailbreak algılama, Intune’un jailbreak uygulanmış cihazları değerlendirme yöntemini geliştiren yeni bir uyumluluk ayarıdır. Ayar, cihazın Intune’a daha sık iade edilmesine neden olur; bu da cihazın konum hizmetlerini kullanır ve pil kullanımını etkiler.

#### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Android O cihazlar için parola sıfırlama <!-- 1238299 -->
İş profiline sahip kayıtlı Android 8.0 cihazlar için parolaları sıfırlayabileceksiniz. Bir Android 8.0 cihaza “Parola sıfırla” isteği gönderdiğinizde cihaz, geçerli kullanıcıya yeni bir cihaz kilidi açma parolası veya yönetilen profil sınaması ayarlar. Parola veya sınama gönderilir ve hemen uygulanır.

#### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Uyumluluk ilkelerinde cihaz gruplarındaki cihazları hedefleme <!--1307012 -->

Uyumluluk ilkelerinde kullanıcı gruplarındaki kullanıcıları hedefleyebilirsiniz. Bu güncelleştirme ile uyumluluk ilkelerinde cihaz gruplarındaki cihazları hedefleyebilirsiniz. Cihaz gruplarının parçası olarak hedeflenen cihazlar, hiçbir uyumluluk eylemi almayacaktır.

#### <a name="new-management-name-column----1333586---"></a>Yeni Yönetim adı sütunu <!-- 1333586 -->
 Cihazlar dikey penceresine **Yönetim adı** adlı yeni bir sütun eklendi. Bu, aşağıdaki formül temelinde her cihaza atanan, otomatik olarak oluşturulmuş ve düzenlenemez bir addır:
- Tüm cihazlar için varsayılan ad: <username><em><devicetype></em><enrollmenttimestamp>
- Toplu eklenen cihazlar: <PaketKimliği/ProfilKimliği><em><DeviceType></em><EnrollmentTime>

Bu, cihazlar dikey penceresinde isteğe bağlı bir sütundur. Varsayılan olarak sağlanmaz ve bu sütuna yalnızca sütun seçici üzerinden erişilebilir. Cihaz adı bu yeni sütundan etkilenmez.

#### <a name="ios-devices-are-prompted-for-a-pin-every-15-minutes---1550837---"></a>15 dakikada bir iOS cihazlardan PIN istenir <!--1550837 -->
Bir iOS cihaza uyumluluk veya yapılandırma ilkesi uygulandıktan sonra her 15 dakikada bir kullanıcılardan bir PIN ayarlamaları istenir. PIN ayarlanana kadar kullanıcılara bu istem gönderilir.

#### <a name="schedule-your-automatic-updates---1805514---"></a>Otomatik güncelleştirmelerinizi zamanlama <!--1805514 -->
Intune, [Windows Güncelleştirme Halkası ayarları](windows-update-for-business-configure.md) kullanarak otomatik güncelleştirme yüklemelerini denetlemenize olanak verir. Bu güncelleştirme ile tekrar eden güncelleştirmeleri hafta, gün ve saat olarak zamanlayabilirsiniz.

#### <a name="use-fully-distinguished-name-as-subject-for-scep-certificate---2221763---"></a>SCEP sertifikası için konu olarak tam ayırt edici ad kullanma <!--2221763 -->
Bir SCEP sertifika profili oluşturduğunuzda Konu Adı girersiniz. Bu güncelleştirme ile konu olarak tam ayırt edici ad kullanabilirsiniz. **Konu Adı** için **Özel**’i seçin ve `CN={{OnPrem_Distinguished_Name}}` girin. `{{OnPrem_Distinguished_Name}}` değişkenini kullanmak için [Azure Active Directory (AD)](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) kullanarak `onpremisesdistingishedname` kullanıcı özniteliğini Azure AD’nizle eşitlediğinizden emin olun.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="enable-bluetooth-contact-sharing---android-for-work---1098983---"></a>Bluetooth kişi paylaşımını etkinleştirme - Android for Work <!--1098983 -->
Varsayılan olarak Android, iş profilindeki kişilerin Bluetooth cihazlarıyla eşitlenmesini önler. Bunun sonucunda iş profili kişileri, Bluetooth cihazlarındaki arayan kimliğinde görüntülenmez.

Bu güncelleştirme ile **Android for Work** > **Cihaz kısıtlamaları** > **İş profili ayarları** kısmına bunun için yeni bir ayar geldi:
- Bluetooth ile kişi paylaşımı

Intune yöneticisi, paylaşıma izin vermek için bu ayarları yapılandırabilir. Bu; bir cihazı, eller serbest kullanım için arayan kimliğini gösteren ve arabada kullanılan bir Bluetooth cihazıyla eşitlerken kullanışlıdır. Etkinleştirildiğinde iş profili kişileri görüntülenir. Etkinleştirilmediğinde iş profili kişileri görüntülenmez.

#### <a name="configure-gatekeeper-to-control-macos-app-download-source----1690459---"></a>macOS uygulama indirme kaynağını denetlemek için Ağ Geçidi Denetleyicisi'ni yapılandırma <!-- 1690459 -->

Uygulamaların nereden indirilebileceğini denetleyerek cihazları uygulamalardan korumak için Ağ Geçidi Denetleyicisini yapılandırabilirsiniz. Yapılandırabileceğiniz indirme kaynakları şunlardır: **Mac App Store**, **Mac App Store ve tanımlanan geliştiriciler** veya **Her Yer**. Ayrıca kullanıcıların bu Ağ Geçidi Denetleyicisi denetimlerini geçersiz kılmak için Control tuşuna tıklayarak uygulama yükleyip yükleyemeyeceklerini de yapılandırabilirsiniz.

Bu ayarlar **Cihaz yapılandırması** -> **Profil oluştur** -> **macOS** -> **Uç nokta koruma** altında bulunabilir.

#### <a name="configure-the-mac-application-firewall----1690461---"></a>Mac uygulaması güvenlik duvarını yapılandırma <!-- 1690461 -->

Mac uygulaması güvenlik duvarını yapılandırabilirsiniz. Bunu kullanarak bağlantıları her bağlantı noktası temelinde değil her uygulama temelinde denetleyebilirsiniz. Güvenlik duvarı korumasının avantajlarından yararlanmanızı kolaylaştırır ve geçerli uygulamalar için açılmış ağ bağlantı noktalarında istenmeyen uygulamaların denetimi ele geçirmesini önlemeye yardımcı olur.

Bu özellik **Cihaz yapılandırması** -> **Profil oluştur** -> **macOS** -> **Uç nokta koruma** altında bulunabilir.

Güvenlik Duvarı ayarını etkinleştirdikten sonra, güvenlik duvarını yapılandırmak için şu iki stratejiyi kullanabilirsiniz:

- Tüm gelen bağlantıları engelleme

   Hedeflenen cihazlar için tüm gelen bağlantıları engelleyebilirsiniz. Bunu yapmayı seçerseniz tüm uygulamalar için gelen bağlantılar engellenir.

- Belirli uygulamalara izin verme veya engelleme

   Belirli uygulamaların gelen bağlantıları almasına izin verebilir veya bunu engelleyebilirsiniz. Ayrıca yoklama isteklerine yönelik yanıtları engellemek için gizli modu da etkinleştirebilirsiniz.

####  <a name="detailed-error-codes-and-messages----1376342---"></a>Ayrıntılı hata kodları ve iletileri <!-- 1376342 -->

Cihaz Yapılandırmanızda, hata kodlarını ve hata iletilerini daha ayrıntılı görebilirsiniz. Bu geliştirilmiş raporlamada ayarlar, bu ayarların durumu ve sorun giderme ayrıntıları gösterilir.

##### <a name="more-information"></a>Daha fazla bilgi

- Tüm gelen bağlantıları engelleme

   Bu, tüm paylaşım hizmetlerinin (Dosya Paylaşımı ve Ekran Paylaşımı gibi) genel bağlantıları almasını engeller. Gelen bağlantıları almasına izin verilen sistem hizmetleri şunlardır:
  - configd - DHCP ve diğer ağ yapılandırma hizmetlerini gerçekleştirir
  - mDNSResponder - Bonjour'u gerçekleştirir
  - racoon -  IPSec'i gerçekleştirir

    Paylaşım hizmetlerini kullanmak için, **Gelen bağlantılar**'ın **Yapılandırılmadı** olarak ayarlandığından emin olun (**Engelle** olarak ayarlanmamalıdır).

- Gizli mod

   Bilgisayarın yoklama isteklerine yanıt vermesini önlemek için bunu etkinleştirin. Bilgisayar, yetkili uygulamalardan gelen istekleri yanıtlamaya devam eder. ICMP (ping) gibi beklenmedik istekler yoksayılır.

#### <a name="disable-checks-on-device-restart---1805490---"></a>Cihazı yeniden başlatma sırasında denetimleri devre dışı bırakma <!--1805490 -->
Intune size [yazılım güncelleştirmelerini yönetme]](windows-update-for-business-configure.md) denetimi verir. Bu güncelleştirme ile <strong>Yeniden başlatma denetimleri</strong> özelliği kullanılabilir ve varsayılan olarak etkindir. Bir cihazı yeniden başlattığınızda yapılan denetimleri (etkin kullanıcılar, pil düzeyleri vb. gibi) atlamak için <strong>Atla</strong>’yı seçin.

#### <a name="new-windows-10-insider-preview-channels-available-for-deployment-rings----1746293---"></a>Yeni Windows 10 Insider Önizleme kanalları dağıtım halkaları için kullanılabilir <!-- 1746293 -->
Artık bir Windows 10 dağıtım halkası seçtiğinizde şu Windows 10 Insider Önizleme bakım kanallarını belirleme seçeneğiniz var:
- Windows Insider derlemesi &#8208; Hızlı
- Windows Insider derlemesi &#8208; Yavaş
- Windows Insider derlemesini yayımlama 

Bu kanallar hakkında daha fazla bilgi için bkz. [Insider Önizleme Derlemelerini Yönetme](https://insider.windows.com/en-us/for-business-organization-admin/).   
Intune’da dağıtım kanalları oluşturma hakkında daha fazla bilgi için bkz. [Intune’da yazılım güncelleştirmelerini yönetme](windows-update-for-business-configure.md).

### <a name="intune-apps"></a>Intune uygulamaları

#### <a name="company-portal-enrollment-improved----1874230-eeready--"></a>Şirket Portalı kaydı geliştirildi <!-- 1874230 eeready-->
Windows 10 derleme 1703’te ve üstünde Şirket Portalı’nı kullanarak cihaz kaydı yapan kullanıcılar, artık uygulamadan çıkmadan kaydın ilk adımını tamamlayabilirler.
#### <a name="hololens-and-surface-hub-now-appear-in-device-lists---1725868---"></a>Artık cihaz listelerinde HoloLens ve Surface Hub gösteriliyor <!--1725868 -->
Intune’a kayıtlı HoloLens ve Surface Hub cihazlarının Android için Şirket Portalı uygulamasına gösterilmesi amacıyla destek ekledik.

#### <a name="custom-book-categories-for-volume-purchase-progream-vpp-ebooks----1488911---"></a>Toplu satın alma programı (VPP) eKitapları için Özel Kitap kategorileri <!-- 1488911 -->
Özel eKitap kategorileri oluşturabilir ve VPP eKitaplarını bu özel eKitap kategorilerine ekleyebilirsiniz. Bundan sonra son kullanıcılar yeni oluşturulan eKitap kategorilerini ve bu kategorilere atanmış olan kitapları görebilecek. Daha fazla bilgi için bkz. [Toplu satın alınan uygulama ve kitapları Microsoft Intune ile yönetme](vpp-apps.md).  

#### <a name="support-changes-for-company-portal-app-for-windows-send-feedback-option----2070166---"></a>Windows için Şirket Portalı’nda geri bildirim gönderme seçeneğinde destek değişiklikleri <!-- 2070166 -->
30 Nisan 2018 tarihinden itibaren Windows için Şirket Portalı uygulamasındaki **Geri Bildirim Gönder** seçeneği, yalnızca Windows 10 Yıldönümü Güncelleştirmesi (1607) ve üzerini çalıştıran cihazlarda kullanılabilecek. Geri bildirim gönderme seçeneği, artık Windows için Şirket Portalı uygulamasını şu sürümlerle birlikte kullanırken desteklenmeyecek:  
- Windows 10, 1507 sürümü  
- Windows 10, 1511 sürümü  
- Windows Phone 8.1 

Cihazınız Windows 10 RS1 ve üzeri çalıştırıyorsa Store’daki Windows Şirket Portalı uygulamasının en son sürümünü indirin. Desteklenmeyen bir sürüm çalıştırıyorsanız lütfen şu kanallar yoluyla geri bildirim göndermeye devam edin: 
- Windows 10’daki Geri Bildirim Merkezi uygulaması
- E-posta WinCPfeedback@microsoft.com  

#### <a name="new-windows-defender-application-guard-settings----1631890---"></a>Yeni Windows Defender Application Guard ayarları <!-- 1631890 -->

- **Grafik hızlandırmayı etkinleştirme**: Yöneticiler, Windows Defender Application Guard için bir sanal grafik işlemcisi etkinleştirebilir. Bu ayar, CPU’nun vGPU’ya işlenen grafikleri boşaltmasına olanak sağlar. Bu, yoğun grafikli sitelerde çalışırken veya kapsayıcı dahilinde video izlerken performansı iyileştirebilir.

- **SaveFilestoHost**: Yöneticiler, dosyaların kapsayıcıda çalışan Microsoft Edge’den konak dosya sistemine geçmesine izin verebilir. Bunu açmak, kullanıcıların kapsayıcıda çalışan Microsoft Edge’den konak dosya sistemine dosya indirmesine imkan sağlar.

#### <a name="mam-protection-policies-targeted-based-on-management-state----1665993---"></a>Yönetim durumu temelinde hedeflenen MAM koruma ilkeleri <!-- 1665993 -->
MAM ilkelerinin hedefini, cihazın yönetim durumuna bağlı olarak belirleyebilirsiniz:
- **Android cihazlar** - Yönetilmeyen cihazları, Intune’da yönetilen cihazları ve Intune’da yönetilen Android Enterprise Profillerini (eski adıyla Android for Work) hedefleyebilirsiniz.
- **iOS cihazlar** - Yönetilmeyen cihazları (yalnızca MAM) veya Intune’da yönetilen cihazları hedefleyebilirsiniz.

    > [!NOTE]
    > - Bu işlev için iOS desteği, Nisan 2018 içerisinde sunulacak.

Daha fazla bilgi için bkz. [Cihaz yönetim durumuna bağlı olarak uygulama koruma ilkeleri hedefleme](app-protection-policies.md).

#### <a name="improvements-to-the-language-in-the-company-portal-app-for-windows----1683758---"></a>Windows için Şirket Portalı uygulamasında dil iyileştirmeleri <!-- 1683758 -->
Daha kullanıcı dostu ve şirketinize özgü olabilmesi için Windows 10 için Şirket Portalı’nda dili iyileştirdik. Yaptıklarımızı gösteren bir örnek görüntü için [uygulama kullanıcı arabirimindeki yeniliklere](whats-new-app-ui.md) bakın.

#### <a name="new-additions-to-our-docs-about-user-privacy----1440709---"></a>Kullanıcı gizliliği belgelerimize yeni eklemeler <!-- 1440709 -->
Kullanıcılarımıza verileri ve gizlilikleri üzerinde daha fazla denetim kazandırma çabalarımızın bir parçası olarak, Şirket Portalı tarafından yerel olarak depolanan verilerin nasıl görüntüleneceğini ve kaldırılacağını açıklayan güncelleştirmeler yayımladık. Bu güncelleştirmeleri bulabileceğiniz yerler şöyledir:

- **Android**: [Android cihazınızı Intune’dan kaldırma](/intune-user-help/unenroll-your-device-from-intune-android.md)
- **Android, kullanıcı kullanım koşullarını reddettiyse**: [“Kullanım Koşulları”nı reddettiyseniz cihaz yönetiminizi kaldırma](/intune-user-help/unenroll-your-device-from-intune-if-you-declined-terms-of-use-android.md)
- **iOS**: [iOS cihazınızı Intune’dan kaldırma](/intune-user-help/unenroll-your-device-from-intune-ios.md)
- **Windows**: [Windows cihazınızı Intune’dan kaldırma](/intune-user-help/unenroll-your-device-from-intune-windows.md)

## <a name="week-of-march-19-2018"></a>19 Mart 2018 Haftası

### <a name="export-all-devices-into-csv-files-in-ie-edge-or-chrome----2258071---"></a>IE, Edge veya Chrome’da tüm cihazları CSV dosyalarına aktarma <!-- 2258071 -->
**Cihazlar** > **Tüm cihazlar**’da cihazları CSV biçimli bir listeye **Dışarı Aktarabilirsiniz**. 10.000’den fazla cihazı olan Internet Explorer (IE) kullanıcıları, cihazlarını birden çok dosyaya başarıyla aktarabilirler. Her dosyada en fazla 10.000 cihaz bulunur.

30.000’den fazla cihazı olan Edge ve Chrome kullanıcıları, cihazlarını birden çok dosyaya başarıyla aktarabilirler. Her dosyada en fazla 30.000 cihaz bulunur.

[Cihazları yönet](device-management.md), yönettiğiniz cihazlarla ne yapabileceğiniz hakkında daha fazla ayrıntı sağlar.

## <a name="week-of-march-12-2018"></a>12 Mart 2018 Haftası

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory web siteleri, Intune Managed Browser uygulaması gerektirebilir ve Managed Browser’da (Genel Önizleme) Çoklu Oturum Açma’yı destekler <!-- 710595 -->

Azure Active Directory (Azure AD) kullanarak artık mobil cihazlarda web sitelerine erişimi Intune Managed Browser uygulaması ile kısıtlayabilirsiniz. Web sitesi verileri, Managed Browser’da güvende ve son kullanıcının kişisel verilerinden ayrı bir yerde olacaktır. Managed Browser ayrıca Azure AD ile korunan sitelerde Çoklu Oturum Açma işlevlerini de destekleyecektir. Managed Browser’da oturum açmak veya Intune tarafından yönetilen başka bir uygulamanın bulunduğu bir cihazda Managed Browser’ı kullanmak, kullanıcıların kimlik bilgilerini girmelerine gerek kalmaksızın Managed Browser’ın Azure AD ile korunan sitelere erişmesine olanak tanır. Bu özellik, Outlook Web Access (OWA) ve SharePoint Online’ın yanı sıra Azure Uygulama Proxy’si yoluyla erişilen intranet kaynakları gibi diğer kurumsal sitelerde de geçerlidir. Ek bilgi için bkz. [Azure Active Directory koşullu erişimde erişim denetimleri](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-controls).

#### <a name="company-portal-app-for-android-visual-updates---976944---"></a>Android için Şirket Portalı uygulaması görsel güncelleştirmeleri <!--976944 -->

Android için Şirket Portalı uygulamasını, Android'in [Materyal Tasarım](https://material.io/) yönergelerine uyacak şekilde güncelleştirdik. Yeni simgelerin resimlerini [Uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md) makalesinde görebilirsiniz.

### <a name="new-windows-defender-exploit-guard-settings----1631893---"></a>Yeni Windows Defender Exploit Guard ayarları <!-- 1631893 -->

Altı yeni <strong>Saldırı Yüzeyi Azaltma</strong> ayarı ve genişletilmiş <strong>Denetimli klasör erişimi: Klasör koruması</strong> işlevleri artık kullanılabilir. Bu ayarlar şurada bulunabilir: Cihaz yapılandırması\Profiller\
Profil oluştur\Endpoint protection\Windows Defender Exploit Guard.

#### <a name="attack-surface-reduction"></a>Saldırı Yüzeyini Azaltma

|Ayar adı  |Ayar seçenekleri  |Description  |
|---------|---------|---------|
|Gelişmiş fidye yazılımı koruması|Etkin, Denetle, Yapılandırılmadı|Agresif fidye yazılımı koruması kullanır.|
|Windows yerel güvenlik yetkilisi alt sisteminden kimlik bilgisi çalma eylemlerine bayrak ekleme|Etkin, Denetle, Yapılandırılmadı|Windows yerel güvenlik yetkilisi alt sisteminden kimlik bilgisi çalma eylemlerine bayrak ekler (lsass.exe).|
|PSExec ve WMI komutlarından işlem oluşturma|Engelle, Denetle, Yapılandırılmadı|PSExec ve WMI komutlarından kaynaklanan işlem oluşturmalarını engeller.|
|USB’den çalışan güvenilmeyen ve imzasız işlemler|Engelle, Denetle, Yapılandırılmadı|USB’den çalışan güvenilmeyen ve imzasız işlemleri engeller.|
|Bir yaygınlık, yaş veya güvenilenler listesi kriterine uymayan yürütülebilir dosyalar|Engelle, Denetle, Yapılandırılmadı|Bir yaygınlık, yaş veya güvenilenler listesi kriterine uymadıkları sürece yürütülebilir dosyaları engeller.|

#### <a name="controlled-folder-access"></a>Denetlenen klasör erişimi

|              Ayar adı               |                                                              Ayar seçenekleri                                                              | Description |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Klasör koruması (zaten uygulanmış) | Yapılandırılmamış, Etkinleştir, Yalnızca denetle (zaten uygulanmış)<br><br> <strong>Yeni</strong><br>Disk değişikliğini engelle, Disk değişikliğini denetle |             |

Dosya ve klasörleri kötü amaçlı uygulamaların yetkisiz değişikliklerinden korur.<br><br>**Etkinleştir**: Güvenilmeyen uygulamaların korumalı klasörlerdeki dosyaları değiştirmesini veya silmesini ve disk kesimlerine yazmasını engeller.<br><br>
**Yalnızca disk değişikliğini engelle**:<br>Güvenilmeyen uygulamaların, disk kesimlerine yazmasını engeller. Güvenilmeyen uygulamalar hala korumalı klasörlerdeki dosyaları değiştirebilir veya silebilir.|

## <a name="week-of-february-19-2018"></a>19 Şubat 2018 haftası

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Birden çok Apple DEP / Apple School Manager hesabı için Intune desteği <!-- 747685 -->

Intune, artık sayıları 100’e varan farklı [Apple Aygıt Kayıt Programı (DEP)](device-enrollment-program-enroll-ios.md) veya [Apple School Manager](apple-school-manager-set-up-ios.md) hesabından cihazların kaydını destekliyor. Karşıya yüklenen her belirteç kayıt profilleri ve cihazlar için ayrı olarak yönetilebilir. Karşıya yüklenen DEP/School Manager belirteçlerinin her biri için farklı bir kayıt profili otomatik olarak atanabilir. Birden çok School Manager belirteci karşıya yüklenirse, Microsoft School Data Sync ile bir kerede tek bir belirteç paylaşılabilir.

Geçişten sonra, Graph üzerinden Apple DEP veya ASM yönetimi için beta Graph API'leri ve yayımlanan betikler artık çalışmayacak. Yeni beta Graph API'leri geliştirme aşamasındadır ve geçiş sonrasında yayınlanacaktır.

#### <a name="see-enrollment-restrictions-per-user----1634444-eeready-wnready---"></a>Kullanıcı başına kayıt kısıtlamalarına bakın <!-- 1634444 eeready wnready -->
Artık **Sorun Giderme** dikey penceresinde **Atamalar** listesinden **Kayıt kısıtlamaları**’nı seçerek her kullanıcı için geçerli olan [kayıt kısıtlamalarını](enrollment-restrictions-set.md) görebilirsiniz.

### <a name="device-management"></a>Cihaz yönetimi
#### <a name="windows-defender-health-status-and-threat-status-reports---854704---"></a>Windows Defender sistem durumu ve tehdit durumu raporları <!--854704 -->

Windows Defender’ın sistem durumunu anlamak, Windows bilgisayarları yönetmenin anahtarıdır.  Bu güncelleştirmeyle Intune, Windows Defender aracısının sistem durumuna yeni raporlar ve eylemler ekler. [Cihaz Uyumluluğu iş yükünde](compliance-policy-monitor.md) bir durum toplama raporu kullanarak, aşağıdakilerden herhangi birine gereksinim duyan cihazları görebilirsiniz:
- imza güncelleştirmesi
- yeniden başlatıp
- el ile müdahale
- tam tarama
- müdahale gerektiren diğer aracı durumları

Her bir durum kategorisi için ayrıntılı bir rapor ile ilgilenilmesi gereken bireysel bilgisayarlar veya **Temiz** olarak raporlananlar listelenir.

#### <a name="new-privacy-settings-for-device-restrictions---1308926---"></a>Cihaz kısıtlamaları için yeni gizlilik ayarları <!--1308926 -->
Cihazlar için [iki yeni gizlilik ayarı](device-restrictions-windows-10.md#privacy) artık kullanılabilir:
- **Kullanıcı etkinliklerini yayımla**: Bunu **Engelle** şeklinde ayarlayarak, görev değiştiricide paylaşılan deneyimleri ve yakın zamanda kullanılan kaynakların bulunmasını önleyin.
- **Yalnızca yerel etkinlikler**: Bunu **Engelle** şeklinde ayarlayarak, görev değiştiricide yalnızca yerel etkinliklere bağlı olan paylaşılan deneyimleri ve yakın zamanda kullanılan kaynakların bulunmasını önleyin.

#### <a name="new-settings-for-the-edge-browser---1469166---"></a>Edge tarayıcısı için yeni ayarlar <!--1469166 -->
Edge tarayıcısı kullanan cihazlar için [iki yeni ayar artık](device-restrictions-windows-10.md#edge-browser) kullanılabilir: **Sık kullanılanlar dosyasının yolu** ve **Sık kullanılanlarda değişiklikler**.

### <a name="app-management"></a>Uygulama yönetimi
#### <a name="protocol-exceptions-for-applications---1035509---"></a>Uygulamalar için protokol özel durumları <!--1035509 -->

Belirli yönetilmeyen uygulamaları açmak için Intune Mobil Uygulama Yönetimi (MAM) veri aktarımı ilkesinde artık özel durumlar oluşturabilirsiniz. Bu tür uygulamaların BT tarafından güvenilen uygulamalar olması gerekir. Oluşturduğunuz özel durumlar dışında, veri aktarımı ilkeniz **yalnızca yönetilen uygulamalar** olarak ayarlı olduğu sürece veri aktarımınız Intune tarafından yönetilen uygulamalarla kısıtlıdır. Protokoller (iOS) veya paketler (Android) kullanarak kısıtlamalar oluşturabilirsiniz.

Örneğin MAM veri aktarımı ilkesine Webex paketini özel durum olarak ekleyebilirsiniz. Böylece, yönetilen bir Outlook e-posta iletisindeki Webex bağlantıları, doğrudan Webex uygulamasında açılacaktır. Veri aktarımı, diğer yönetilmeyen uygulamalarda kısıtlı olmaya devam edecektir. Daha fazla bilgi için bkz. [Uygulamalar için veri aktarım ilkesi özel durumları](app-protection-policies-exception.md).

#### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Windows arama sonuçlarında Windows Bilgi Koruması (WIP) ile şifrelenmiş veriler <!-- 1469193 -->
Windows Bilgi Koruması (WIP) ilkesindeki bir ayar, artık Windows arama sonuçlarına WIP ile şifrelenmiş verilerin dahil edilip edilmeyeceğini denetlemenize olanak tanıyor. Windows Bilgi Koruması ilkesinin **Gelişmiş ayarlar** kısmında **Windows Search Dizin Oluşturucu’nun şifrelenmiş öğeleri aramasına izin ver**’i seçerek bu uygulama koruma ilkesi seçeneğini belirleyin. Uygulama koruma ilkesi, *Windows 10* platformuna ayarlanmalı ve uygulama ilkesi **Kayıt durumu**, **Kayıt ile** olarak ayarlanmalıdır. Daha fazla bilgi için bkz. [Windows Search Dizin Oluşturucu’nun şifrelenmiş öğeleri aramasına izin ver](windows-information-protection-policy-create.md#allow-windows-search-indexer-to-search-encrypted-items).

#### <a name="configuring-a-self-updating-mobile-msi-app----1740840---"></a>Kendi kendini güncelleştiren bir MSI uygulaması yapılandırma <!-- 1740840 -->
Sürüm denetim işlemini yoksaymak için bilinen bir kendi kendini güncelleştiren MSI uygulaması yapılandırabilirsiniz. Bu yetenek, bir yarış durumuna girmeyi önlemek açısından kullanışlıdır. Bu tür bir yarış durumu örneğin uygulama, uygulama geliştiricisi tarafından otomatik olarak güncelleştirilirken diğer yandan Intune tarafından da güncelleştirildiği durumlarda ortaya çıkabilir. Her iki taraf da bir Windows istemcisinde uygulamanın bir sürümünü zorlamaya çalışabilir, böylece bir çakışma ortaya çıkabilir. Otomatik olarak güncelleştirilen bu MSI uygulamaları için **Uygulama bilgileri** dikey penceresindeki **Uygulama sürümünü yoksay**  ayarını yapılandırabilirsiniz. Bu ayar **Evet** olarak değiştirildiğinde, Microsoft Intune, Windows istemcisinde yüklü olan uygulama sürümünü yoksayar.

#### <a name="related-sets-of-app-licenses-supported-in-intune----1864117---"></a>Intune’da desteklenen ilgili uygulama lisans kümeleri <!-- 1864117 -->
Azure portalında Intune, ilgili uygulama lisans kümelerini artık kullanıcı arabiriminde tek bir uygulama öğesi olarak destekliyor. Buna ek olarak, İş İçin Microsoft Store’dan eşitlenmiş Çevrimdışı Lisanslanan uygulamalar da tek bir uygulama girdisi olarak birleştirilecek ve ayrı ayrı paketlerdeki dağıtım ayrıntıları bu tek girdiye taşınacak. Azure portalında ilgili uygulama lisans kümelerini görüntülemek için **Mobil uygulamalar** dikey penceresinden **Uygulama lisansları**’nı seçin.

### <a name="device-configuration"></a>Cihaz yapılandırması
#### <a name="windows-information-protection-wip-file-extensions-for-automatic-encryption----1463582---"></a>Otomatik şifreleme için Windows Bilgi Koruması (WIP) dosya uzantıları <!-- 1463582 -->
Windows Bilgi Koruması (WIP) ilkesindeki bir ayar, WIP politikasında tanımlanan şekilde şirket sınırında bir Sunucu İleti Bloğu (SMB) paylaşımından kopyalarken hangi dosya uzantılarının otomatik olarak şifreleneceğini belirtmenize artık izin veriyor.

#### <a name="configure-resource-account-settings-for-surface-hubs"></a>Surface Hub’lar için kaynak hesap ayarlarını yapılandırma

Surface Hub’lar için kaynak hesap ayarlarını artık uzaktan yapılandırabilirsiniz.

Kaynak hesabı, Skype/Exchange ile kimlik doğrulaması yapmak için bir Surface Hub tarafından kullanılır; böylece bir toplantıya katılabilir.
Surface Hub’ın toplantıdaki konferans odası olarak görünmesi için eşsiz bir kaynak hesabı oluşturmak isteyebilirsiniz.
Örneğin, **Konferans Salonu B41/6233** kaynak hesabı.

> [!NOTE]
> - Alanları boş bırakırsanız cihazın önceden yapılandırılmış özniteliklerini geçersiz kılarsınız.
>
> - Kaynak Hesap özellikleri, Surface Hub’da dinamik olarak değişebilir. Örneğin, parola dönüşü açıksa. Bu nedenle, Azure konsolundaki değerlerin cihazdaki gerçekliği yansıtması biraz zaman alabilir.
>
>   Surface Hub’daki geçerli yapılandırmaları anlamak için Kaynak Hesap bilgileri donanım envanterine (7 günlük aralığı vardır) veya salt okunur özelliklere dahil edilebilir. Uzak eylem gerçekleştikten sonra doğruluğu artırmak için, Surface Hub hesabını/parametrelerini güncelleştirmek üzere eylemi çalıştırdıktan hemen sonra parametrelerin durumunu alabilirsiniz.


##### <a name="attack-surface-reduction"></a>Saldırı Yüzeyini Azaltma


|Ayar adı  |Ayar seçenekleri  |Description  |
|---------|---------|---------|
|Parola korumalı yürütülebilir içeriğin e-postadan yürütülmesi|Engelle, Denetle, Yapılandırılmadı|E-posta üzerinden indirilen parola korumalı yürütülebilir dosyaların çalıştırılmasını engelleyin.|
|Gelişmiş fidye yazılımı koruması|Etkin, Denetle, Yapılandırılmadı|Agresif fidye yazılımı koruması kullanır.|
|Windows yerel güvenlik yetkilisi alt sisteminden kimlik bilgisi çalma eylemlerine bayrak ekleme|Etkin, Denetle, Yapılandırılmadı|Windows yerel güvenlik yetkilisi alt sisteminden kimlik bilgisi çalma eylemlerine bayrak ekler (lsass.exe).|
|PSExec ve WMI komutlarından işlem oluşturma|Engelle, Denetle, Yapılandırılmadı|PSExec ve WMI komutlarından kaynaklanan işlem oluşturmalarını engeller.|
|USB’den çalışan güvenilmeyen ve imzasız işlemler|Engelle, Denetle, Yapılandırılmadı|USB’den çalışan güvenilmeyen ve imzasız işlemleri engeller.|
|Bir yaygınlık, yaş veya güvenilenler listesi kriterine uymayan yürütülebilir dosyalar|Engelle, Denetle, Yapılandırılmadı|Bir yaygınlık, yaş veya güvenilenler listesi kriterine uymadıkları sürece yürütülebilir dosyaları engeller.|

##### <a name="controlled-folder-access"></a>Denetlenen klasör erişimi

|              Ayar adı               |                                                              Ayar seçenekleri                                                              | Description |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Klasör koruması (zaten uygulanmış) | Yapılandırılmamış, Etkinleştir, Yalnızca denetle (zaten uygulanmış)<br><br> <strong>Yeni</strong><br>Disk değişikliğini engelle, Disk değişikliğini denetle |             |

Dosya ve klasörleri kötü amaçlı uygulamaların yetkisiz değişikliklerinden korur.<br><br>**Etkinleştir**: Güvenilmeyen uygulamaların korumalı klasörlerdeki dosyaları değiştirmesini veya silmesini ve disk kesimlerine yazmasını engeller.<br><br>
**Yalnızca disk değişikliğini engelle**:<br>Güvenilmeyen uygulamaların, disk kesimlerine yazmasını engeller. Güvenilmeyen uygulamalar hala korumalı klasörlerdeki dosyaları değiştirebilir veya silebilir.|

#### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies---1704133--"></a>Windows 10 ve üzeri uyumluluk ilkeleri için Sistem Güvenliği ayarlarına eklemeler <!--1704133-->

Güvenlik Duvarı ve Windows Defender Virüsten Koruma dahil olmak üzere Windows 10 uyumluluk ayarlarına bazı eklemeler geldi.


### <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi
### <a name="intune-apps"></a>Intune uygulamaları
#### <a name="support-for-offline-apps-from-the-microsoft-store-for-business---1222672--"></a>İş İçin Microsoft Mağazası uygulamaları için çevrimdışı desteği <!--1222672-->
İş için Microsoft Store’dan satın aldığınız çevrimdışı uygulamalar, artık Azure portalına eşitlenir. Bu uygulamaları cihaz gruplarına veya kullanıcı gruplarına dağıtabilirsiniz. Çevrimdışı uygulamalar, mağaza tarafından değil Intune tarafından yüklenir.

#### <a name="prevent-end-users-from-manually-adding-or-removing-accounts-in-the-work-profile----1728700---"></a>Son kullanıcıların iş profiline el ile hesap eklemesini veya profilden hesap kaldırmasını önleme <!-- 1728700 -->

Bir Android for Work profiline Gmail uygulamasını dağıttığınızda, artık Android for Work cihaz kısıtlama profilindeki **Hesap ekle veya kaldır** ayarını kullanarak son kullanıcıların iş profilinde hesap ekleme veya kaldırma işlemleri yapmasını önleyebilirsiniz.

## <a name="week-of-february-5-2018"></a>5 Şubat 2018 haftası

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625-eeready---"></a>Apple toplu kaydında kullanıcı kimlik doğrulaması için yeni seçenek <!-- 747625 eeready -->

> [!NOTE]
> Yeni kiracılar bu seçeneği hemen görecektir. Mevcut kiracılar için ise bu özellik, Nisan ayı içerisinde sunulacaktır. Bu dağıtım tamamlanana kadar, bu yeni özelliklere erişemeyebilirsiniz.

Intune, artık aşağıdaki kayıt yöntemlerinde size Şirket Portalı uygulamasını kullanarak cihazların kimliğini doğrulama seçeneği sağlıyor:

- Apple Cihaz Kaydı Programı
- Apple School Manager
- Apple Configurator Kaydı

Şirket portalı seçeneği kullanılırken, bu kayıt yöntemlerini engellemeden Azure Active Directory çok faktörlü kimlik doğrulaması zorunlu tutulabilir.

Şirket portalı seçeneği kullanılırken, Intune kullanıcı benzeşimi kaydı için iOS Kurulum Yardımcısı'nda kullanıcı kimlik doğrulamasını atlar. Bu, cihazın başlangıçta kullanıcısız bir cihaz olarak kaydedildiği ve dolayısıyla kullanıcı gruplarının yapılandırmaları veya ilkelerini almadığı anlamına gelir. Cihaz, yalnızca cihaz gruplarının yapılandırmalarını ve ilkelerini alır. Bununla birlikte, Intune Şirket Portalı uygulamasını Cihaz üzerine otomatik olarak yükleyecek. Şirket Portalı uygulamasını başlatan ve bu uygulamada oturum açan ilk kullanıcı, Intune'da cihazla ilişkilendirilecek. Bu noktada kullanıcı, kendi kullanıcı gruplarının yapılandırmalarını ve ilkelerini alacak. Yeniden kayıt yapılmadan kullanıcı ilişkisi değiştirilemez.

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685-eeready---"></a>Birden çok Apple DEP / Apple School Manager hesabı için Intune desteği <!-- 747685 eeready -->

Intune, artık sayıları 100'e varan farklı Apple Aygıt Kayıt Programı (DEP) veya Apple School Manager hesabından cihazların kaydını destekliyor. Karşıya yüklenen her belirteç kayıt profilleri ve cihazlar için ayrı olarak yönetilebilir. Karşıya yüklenen DEP/School Manager belirteçlerinin her biri için farklı bir kayıt profili otomatik olarak atanabilir. Birden çok School Manager belirteci karşıya yüklenirse, Microsoft School Data Sync ile bir kerede tek bir belirteç paylaşılabilir.

Geçişten sonra, Graph üzerinden Apple DEP veya ASM yönetimi için beta Graph API'leri ve yayımlanan betikler artık çalışmayacak. Yeni beta Graph API'leri geliştirme aşamasındadır ve geçiş sonrasında yayınlanacaktır.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Güvenli bir ağ üzerinden uzaktan yazdırma <!-- 1709994  -->
PrinterOn’un kablosuz mobil yazdırma çözümleri kullanıcıların güvenli bir ağ üzerinden istedikleri yerde ve istedikleri zaman uzaktan yazdırma işlemi yapmalarını sağlayacak. PrinterOn, hem iOS hem de Android için Intune APP SDK'sıyla tümleştirilecek. Yönetim konsolundaki Intune **Uygulama koruma ilkeleri** dikey penceresi aracılığıyla uygulama koruma ilkelerinde bu uygulamayı hedefleyebileceksiniz. Son kullanıcılar 'PrinterOn for Microsoft' uygulamasını kendi Intune ekosistemlerinde kullanmak üzere Play Store veya iTunes üzerinden indirebilecek.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager----1352411---"></a>macOS Aygıt Kayıt Yöneticisi’ni kullanan kayıtlar için Şirket Portalı desteği <!-- 1352411 -->

macOS Şirket Portalı’na kaydolurken kullanıcılar, artık Cihaz Kayıt Yöneticisi’ni kullanabilirler.

## <a name="week-of-january-29-2018"></a>29 Ocak 2018 Haftası

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Süresi dolan ve dolmak üzere olan belirteçler için uyarılar <!-- 1639263 -->
Genel bakış sayfasında süresi dolan ve dolmak üzere olan belirteçler için artık uyarılar gösteriliyor. Tek bir belirtecin uyarısına tıkladığınızda, belirtecin ayrıntılar sayfasına gideceksiniz.  Birden çok belirteç içeren bir uyarıya tıklarsanız, durumlarıyla birlikte tüm belirteçlerin listesine gideceksiniz. Yöneticilerin, süreleri dolmadan önce belirteçleri yenilemesi gerekir.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="remote-erase-command-support-for-macos-devices----1438084---"></a>macOS cihazlar için uzaktan “Sil” komutu desteği <!-- 1438084 -->

macOS cihazlar için yöneticiler uzaktan Sil komutu gönderebilir.

> [!IMPORTANT]
> Sil komutu geri alınamaz ve dikkatli kullanılmalıdır.

Sil komutu işletim sistemi de içinde olmak üzere cihazdan tüm verileri kaldırır. Cihaz ayrıca Intune yönetiminden de kaldırılır. Kullanıcıya hiçbir uyarı gönderilmez ve komut gönderildiğinde silme işlemi hemen gerçekleştirilir.

6 basamaklı bir kurtarma PIN’i yapılandırmanız gerekir. Bu PIN silinmiş olan cihazın kilidini açmak için kullanılabilir ve bu noktada işletim sisteminin yeniden yüklemesi başlar. Silme işlemi başlatıldıktan sonra, Intune'da cihazın genel bakış dikey penceresindeki durum çubuğunda PIN gösterilir. Silme işlemi devam ettiği sürece PIN görüntüde kalacak. Silme işlemi tamamlandıktan sonra, cihaz Intune yönetiminden tamamen kaybolur. Herhangi birinin cihazı geri yükleyen kullanabilmesi için kurtarma PIN'ini bir yere kaydettiğinizden emin olun.

#### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Bir iOS Toplu Satın Alma Programı belirteci için lisansları iptal et <!-- 820870 -->
Belirli bir VPP Belirteci için tüm iOS Volume Purchasing Program (VPP) uygulamalarının lisansını iptal edebilirsiniz.

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>iOS - Toplu Satın Alma Programı uygulamalarını iptal etme <!-- 820863 -->
Bir veya daha fazla iOS Volume Purchase Program (VPP) uygulaması olan belirli bir cihaz için, cihazla ilişkili cihaza dayalı uygulama lisansını iptal edebilirsiniz. Bir uygulama lisansını iptal etmek ilgili VPP uygulamasını cihazdan kaldırmaz. Bir VPP uygulamasını kaldırmak için, atama işlemini **Kaldır** olarak değiştirmelisiniz. Daha fazla bilgi için bkz. [Microsoft Intune ile toplu satın alma programından satın alınan iOS uygulamalarını yönetme](vpp-apps-ios.md).

#### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Yerleşik uygulama türü kullanarak Office 365 mobil uygulamaları iOS ve Android cihazlara atama <!-- 1332318 -->
**Yerleşik** uygulama türü yönettiğiniz iOS ve Android cihazlar için Office 365 uygulamaları oluşturmayı ve atamayı kolaylaştırır. Bu uygulamalar Word, Excel, PowerPoint ve OneDrive gibi 0365 uygulamalarını içerir. Uygulama türüne belirli uygulamalar atayabilir ve uygulama bilgileri yapılandırmasını düzenleyebilirsiniz.

#### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>Gruplar temelinde uygulama atamasını dahil etme ve hariç tutma <!-- 1406920 -->

Uygulama ataması sırasında ve bir atama türü seçtikten sonra, hem dahil edilecek hem de hariç tutulacak grupları seçebilirsiniz.

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="you-can-assign-an-application-configuration-policy-to-groups-by-including-and-excluding-assignments-----1480316---"></a>Atamaları dahil ederek veya dışlayarak gruplara bir uygulama yapılandırma ilkesi atayabilirsiniz  <!-- 1480316 -->

Dahil etme ve dışlama atamaları bileşimini kullanarak kullanıcı ve cihaz gruplarına bir uygulama yapılandırma ilkesi atayabilirsiniz. Atamalar, özel seçili gruplar olarak veya sanal bir grup şeklinde seçilebilir. Bir sanal grup **Tüm Kullanıcılar**, **Tüm Cihazlar** ve **Tüm Kullanıcılar + Tüm Cihazlar** şeklinde olabilir.

#### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Windows 10 sürüm yükseltme ilkesi desteği <!-- 903672(archived), 1119689 -->  
Windows 10 cihazları; Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education ve Windows 10 Professional Education N’e yükselten bir Windows 10 sürüm yükseltme ilkesi oluşturabilirsiniz. Windows 10 sürüm yükseltmeleri hakkında daha fazla bilgi için bkz. [Windows 10 sürüm yükseltmelerini yapılandırma](edition-upgrade-configure-windows-10.md).

#### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal-----1737088-1634311---"></a>Intune için Koşullu Erişim ilkeleri yalnızca Azure Portal'dan sağlanır  <!-- 1737088 1634311 -->

Bu yayından başlayarak, Koşullu Erişim ilkelerinizi yalnızca [Azure Portalı](https://portal.azure.com)’ndaki **Azure Active Directory** > **Koşullu Erişim**’de yapılandırabilir ve yönetebilirsiniz. Size kolaylık olması için, Azure Portal'daki Intune'da **Intune** > **Koşullu Erişim** konumundan da erişebilirsiniz.

#### <a name="updates-to-compliance-emails---1637547---"></a>Uyumluluk e-postalarında güncelleştirmeler <!--1637547 -->

Uyumsuz bir cihazı raporlamak amacıyla e-posta gönderildiğinde, bu e-postaya uyumsuz cihaz hakkındaki ayrıntılar da eklenir.


## <a name="week-of-january-22-2018"></a>22 Ocak 2018 haftası

### <a name="intune-apps"></a>Intune uygulamaları

#### <a name="new-functionality-for-the-resolve-action-for-android-devices---1583480--"></a>Android cihazlarda “Çözümle” eylemi için yeni işlev <!--1583480-->

Android için Şirket Portalı uygulaması, **Cihaz ayarlarını güncelleştir** için “Çözümle” eylemini [cihaz şifreleme sorunlarını](/intune-user-help/encrypt-your-device-android) çözümlemek üzere genişletiyor.

#### <a name="remote-lock-available-in-company-portal-app-for-windows-10---676506--"></a>Windows 10 için Şirket Portalı uygulamasında uzaktan kilitleme kullanılabilir <!--676506-->
Son kullanıcılar artık, Windows 10 için Şirket Portalı uygulamasını kullanarak cihazlarını uzaktan kilitleyebilirler. Bu, etkin olarak kullanmakta oldukları yerel cihazda görüntülenmez.

#### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546--"></a>Windows 10 için Şirket Portalı'ndaki uyumluluk sorunlarının daha kolay çözümü<!--676546-->
Windows cihazı olan son kullanıcılar, Şirket Portalı uygulamasında uyumsuzluk nedenine dokunabilecek. Buna dokunmaları mümkün olduğunda, ayarlar uygulamasında sorunu çözebilecekleri konuma gidecekler.

## <a name="week-of-december-11-2017"></a>11 Aralık 2017 haftası

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="new-automatic-redeployment-setting----1469168---"></a>Yeni otomatik yeniden dağıtım ayarı<!-- 1469168 -->
**Otomatik yeniden dağıtım** ayarı, yönetici haklarına sahip olan kullanıcıların cihaz kilidi ekranında **CTRL + Win + R** tuşunu kullanarak tüm kullanıcı verilerini ve ayarlarını silmelerini sağlar. Cihaz otomatik olarak yeniden yapılandırılacak ve yönetime yeniden kaydedilir. Bu ayar, Windows 10 > Aygıt kısıtlamaları > Genel > Otomatik yeniden dağıtma altında bulunabilir. Ayrıntılar için bkz. [Windows 10 için Intune cihaz kısıtlama ayarları](device-restrictions-windows-10.md#general).

#### <a name="support-for-additional-source-editions-in-the-windows-10-edition-upgrade-policy-----903672--1119689---"></a>Windows 10 sürüm yükseltme ilkesinde ek kaynak sürümleri desteği  <!-- 903672,  1119689 -->
Artık başka Windows 10 sürümlerinden (Windows 10 Pro, Windows 10 Pro Education, Windows 10 Cloud, vb.) yükseltme yapmak için Windows 10 sürüm yükseltme ilkesini kullanabilirsiniz. Bu sürümden önce, desteklenen sürüm yükseltme yolları daha sınırlıydı. Ayrıntılar için bkz. [Windows 10 sürüm yükseltmelerini yapılandırma](edition-upgrade-configure-windows-10.md).

#### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>Yeni Windows Defender Güvenlik Merkezi (WDSC) cihaz yapılandırma profili ayarları <!-- 1335507 -->

Intune, cihaz yapılandırma profili ayarlarının Uç nokta koruma altında **Windows Defender Güvenlik Merkezi** adında yeni bir bölüm ekler. BT yöneticileri, son kullanıcıların Windows Defender Güvenlik Merkezi uygulamasının hangi sütunlarına erişebileceklerini yapılandırabilir. Bir BT yöneticisi Windows Defender Güvenlik Merkezi uygulamasında bir sütun gizlerse, gizli sütunlarla ilgili hiçbir bildirim kullanıcının cihazında görüntülenmez.

Yöneticilerin Windows Defender Güvenlik Merkezi aygıt yapılandırma profili ayarlarından gizleyebilecekleri sütunlar şunlardır:
- Virüs ve tehdit koruması
- Cihaz performans ve sistem durumu
- Güvenlik duvarı ve ağ korumaları
- Uygulama ve tarayıcı denetimi
- Aile seçenekleri

BT yöneticileri, kullanıcıların hangi bildirimleri aldığını da özelleştirebilir. Örneğin, kullanıcıların WDSC'deki görünür sütunlar tarafından oluşturulan tüm bildirimleri alıp almayacaklarını veya yalnızca kritik bildirimleri alıp almayacaklarını yapılandırabilirsiniz. Kritik olmayan bildirimlere, Windows Defender Antivirus etkinliğinin periyodik özetleri ve taramalar tamamlandığında verilen bildirimler dahildir. Diğer tüm bildirimler kritik olarak kabul edilir. Ayrıca, bildirim içeriğini kendiniz de özelleştirebilirsiniz, örneğin, kullanıcıların cihazlarında görünen bildirimlere eklemek için BT iletişim bilgilerini sağlayabilirsiniz.

#### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling----1361755---"></a>SCEP ve PFX sertifika işleme için birden çok bağlayıcı desteği <!-- 1361755 -->

Şirket içi NDES bağlayıcısı kullanan müşteriler, artık tek bir kiracıda birden fazla bağlayıcıyı yapılandırarak sertifikaları cihazlara teslim edebilir.

Bu yeni yetenek aşağıdaki senaryoyu destekler:

- **Yüksek kullanılabilirlik**

Her bir NDES bağlayıcısı, Intune'dan sertifika istekleri çeker.  Bir NDES Bağlayıcısı çevrimdışı olursa, diğer bağlayıcı istekleri işlemeye devam edebilir.

#### <a name="customer-subject-name-can-use-aaddeviceid-variable-----1468599---"></a>Özel konu adı AAD_DEVICE_ID değişkenini kullanabilir  <!-- 1468599 -->

Intune'da SCEP sertifika profili oluşturduğunuzda, artık özel konu adını oluştururken AAD_DEVICE_ID değişkenini kullanabilirsiniz.   Bu SCEP profili kullanılarak sertifika istendiğinde, değişkenin yerini sertifika isteğinde bulunan cihazın AAD cihaz kimliği alır.


### <a name="device-management"></a>Cihaz yönetimi

#### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine----1592747---"></a>Jamf'e kayıtlı makro cihazları Intune cihaz uyumluluk motoruyla yönetme <!-- 1592747 -->
Artık, Intune konsolunda tanımlanan ilkelere uyumu değerlendirecek olan MacOS cihaz durumu bilgilerini Intune'a göndermek için Jamf kullanabilirsiniz. Cihaz uyumluluk durumuna ve diğer koşullara (konum, kullanıcı riski vb.) bağlı olarak koşullu erişim, buluta erişen ve Office 365 de dahil olmak üzere Azure AD ile bağlantılı kurum içi uygulamalara erişen macOS cihazlarına uyumluluğu zorlar. [Jamf tümleştirmesini ayarlama](conditional-access-integrate-jamf.md) ve [Jamf tarafından yönetilen cihazlarda uyumluluğu zorlama](conditional-access-assign-jamf.md) hakkında daha fazla bilgi edinin.

#### <a name="new-ios-device-action------1424701---"></a>Yeni iOS cihaz eylemi  <!-- 1424701 -->

Şimdi IOS 10.3 denetlenen cihazlarını kapatabilirsiniz. Bu eylem, son kullanıcıya herhangi bir uyarı yapılmadan cihazı hemen kapatır. **Cihaz** iş yükünde bir cihaz seçtiğinde, cihaz özelliklerinde **Kapat (yalnızca denetimli)** eylemi bulunabilir.

#### <a name="disallow-datetime-changes-to-samsung-knox-devices----1468103---"></a>Samsung Knox cihazlarında tarih/saat değişikliklerine izin vermeme <!-- 1468103 -->

Samsung Knox cihazlarında tarih ve saat değişikliklerini engellemenize olanak tanıyan yeni bir özellik ekledik. Bunu, **Cihaz yapılandırma profilleri** > **Cihaz kısıtlamaları (Android)** > **Genel** altında bulabilirsiniz.

#### <a name="surface-hub-resource-account-supported----1566442----"></a>Surface Hub kaynak hesabını destekler <!-- 1566442  -->

Yeni bir cihaz eylemi eklendi; böylece yöneticiler bir Surface Hub ile ilişkili kaynak hesabını tanımlayıp güncelleyebilir.

Kaynak hesabı, Skype/Exchange ile kimlik doğrulaması yapmak için bir Surface Hub tarafından kullanılır; böylece bir toplantıya katılabilir. Eşsiz bir kaynak hesabı oluşturabilir; böylece Surface Hub toplantıdaki konferans odası olarak görünür. Örneğin, kaynak hesabı *Konferans Salonu B41/6233* olarak görünebilir. Surface Hub için kaynak hesabı (cihaz hesabı olarak bilinir), genellikle Konferans odası konumu için ve diğer kaynak hesabı parametreleri değiştirilmesi gerektiğinde yapılandırılması gerekir.

Yöneticiler bir cihazdaki kaynak hesabını güncelleştirmek istediği zaman, cihazla ilişkili geçerli Active Directory/Azure Active Directory kimlik bilgilerini sağlamaları gerekir. Cihaz için parola rotasyonu açıksa, yöneticiler parolayı bulmak için Azure Active Directory'ye gitmelidir.

> [!NOTE]
> Tüm alanlar bir paket halinde gönderilir ve daha önce yapılandırılmış olan tüm alanların üzerine yazılır. Boş alanlar var olan alanların üzerine yazılır.

Yöneticilerin yapılandırabileceği ayarlar şunlardır:

- **Kaynak hesabı**
   - **Active Directory kullanıcısı**

      EtkiAlanıAdı\KullanıcıAdı veya Kullanıcı Asıl Adı (UPN):user@domainname.com

   - **Parola**

- **İsteğe bağlı kaynak hesabı parametreleri** (belirtilen kaynak hesabını kullanarak ayarlanması gerekir)

   - **Parola rotasyon süresi**

     Güvenlik nedeniyle, hesap şifresinin her hafta Surface Hub tarafından güncellenmesini sağlar. Bu etkinleştirildikten sonra parametreleri yapılandırmak için, Azure Active Directory'deki hesapta önce parolanın sıfırlanması gerekir.

   - **SIP (Oturum Başlatma Protokolü) adresi**

     Yalnızca otomatik bulma başarısız olduğunda kullanılır.

   - **E-posta**

     Cihaz/kaynak hesabının e-posta adresi.

   - **Exchange sunucusu**

     Yalnızca otomatik bulma başarısız olduğunda gereklidir.

   - **Takvim eşitleme**

     Takvim eşitleme ve diğer Exchange server hizmetlerini etkinleştirilip etkinleştirilmeyeceğini belirtir. Örneğin: Toplantı eşitleme.

#### <a name="install-office-apps-on-macos-devices----1494311---"></a>MacOS cihazlarda Office uygulamalarını yükleyin <!-- 1494311 -->
Artık Office uygulamalarını macOS cihazlara yükleyebilirsiniz. Bu yeni uygulama türü, Word, Excel, PowerPoint, Outlook ve OneNote yüklemeye izin verir. Bu uygulamalar, uygulamalarınızı güvenli ve güncel tutmaya yardımcı olmak için ayrıca Microsoft AutoUpdate (MAU) ile gelir.

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="delete-an-ios--volume-purchasing-program-token----820879---"></a>Bir iOS Toplu Satın Alma Programı belirtecini silin <!-- 820879 -->
Konsolu kullanarak iOS Toplu Satın Alma Programı (VPP) belirtecini silebilirsiniz. VPP belirteci kopya örnekleriniz olduğunda bu gerekli olabilir.

### <a name="intune-apps"></a>Intune uygulamaları


### <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

#### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1667026---"></a>Geçerli Kullanıcı adlı yeni bir varlık koleksiyonu şu anda etkin olan kullanıcı verisi ile sınırlıdır <!-- 1667026 -->

**Kullanıcılar** varlık koleksiyonu, kuruluşunuzda kendisine lisans atanmış olan tüm Azure Active Directory (Azure AD) kullanıcılarını içerir. Örneğin, bir kullanıcı Intune'a eklenebilir ve son bir ay içerisinde kaldırılabilir. Bu kullanıcı raporun olduğu saatte bulunmamakla birlikte, verilerde kullanıcı ve durumu bulunur. Kullanıcının verilerinizdeki varlığının süresini gösterecek bir rapor oluşturabilirsiniz.

Buna karşılık, yeni **Geçerli Kullanıcı** varlık koleksiyonu yalnızca kaldırılmamış olan kullanıcıları içerir. **Geçerli kullanıcı** varlık koleksiyonu yalnızca etkin kullanıcıları içerir. **Geçerli Kullanıcı** öğesi hakkında daha fazla bilgi edinmek için bkz. [Geçerli kullanıcı varlığı için başvuru](reports-ref-current-user.md).


### <a name="updated-graph-apis----1736360---"></a>Güncelleştirilmiş Graph API'leri <!-- 1736360 -->

Bu sürümde, beta aşamasında olan Intune için Graph API'lerinden birkaçını güncelleştirdik. Daha fazla bilgi için lütfen aylık [Graph API değişiklik günlüğünü](https://developer.microsoft.com/graph/docs/concepts/changelog) gözden geçirin.

## <a name="week-of-december-4-2017"></a>4 Aralık 2017 haftası

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="intune-supports-windows-information-protection-wip-denied-apps----1479103---"></a>Intune, Windows Information Protection (WIP) tarafından reddedilen uygulamaları destekler <!-- 1479103 -->
Intune'da reddedilen uygulamaları belirtebilirsiniz. Uygulama reddedilirse, şirket bilgilerine erişimi engellenir; aslında izin verilen uygulamalar listesinin tam tersidir. Daha fazla bilgi için bkz. [Windows Information Protection için önerilen reddedilenler listesi](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp?f=255&MSPPError=-2147217396#recommended-deny-list-for-windows-information-protection).



## <a name="notices"></a>Bildirimler

### <a name="plan-for-change-intune-moving-to-support-ios-10-and-later-in-september----2454656---"></a>Değişiklik Planı: Intune, Eylül'de iOS 10 ve üzerine desteklemeye geçiyor <!-- 2454656 -->
Eylül'de, Apple iOS 12'yi kullanıma sunmayı bekliyor. Kullanıma sunulmasından kısa süre sonra, Intune kaydını, Şirket Portalı'nı ve yönetilen tarayıcıyı iOS 10 ve üzerine desteklemeye geçireceğiz.  

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?  
Office 365 mobil uygulamaları iOS 10 ve üzerinde destekleniyor, dolayısıyla işletim sisteminizi ve cihazlarınızı zaten yükseltmiş olabilirsiniz. Bu durumda, bu geçiş sizi etkilemez.  

Öte yandan, aşağıda listelenen cihazlardan herhangi birine sahipseniz veya aşağıda listelenen cihazlardan herhangi birini kaydetmek istiyorsanız, bunların yalnızca iOS 9 ve öncesini desteklediğini bilmelisiniz.  Intune Şirket Portalı'na erişmeye devam etmek için, Eylül'e kadar bu cihazları iOS 10 ve üzerini destekleyen cihazlara yükseltmeniz gerekir:  

* iPhone 4S  
* iPod Touch  
* iPad 2  
* iPad (3. Nesil)  
* iPad Mini (1. Nesil)  

Temmuz'dan başlayarak, hem iOS 9 hem de Şirket Portalı içeren MDM kayıtlı cihazlarda işletim sistemini veya cihazı yükseltmeye yönelik bir ileti gösterilecek. Uygulama koruma ilkelerini kullanıyorsanız, “En düşük iOS işletim sistemi gerekir (Yalnızca uyarı)” erişim ayarını da kullanabilirsiniz.  

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?   
Kuruluşunuzda etkilenen cihazları veya kullanıcıları belirleyin. Azure portalında Intune'da, Cihazlar > Tüm cihazlar'a gidin ve işletim sistemine göre filtreleyin.  İşletim sistemi sürümü gibi ayrıntıların gösterilmesi için Sütunlar'a tıklayın. Eylül'den önce kullanıcılarınızdan cihazlarını desteklenen bir işletim sistemi sürümüne yükseltmelerini isteyin.  

### <a name="plan-for-change-intune-moving-to-tls-12"></a>Değişiklik Planı: Intune’u TLS 1.2’ye taşıma
31 Ekim 2018 tarihinden itibaren Intune; sınıfının en iyisi şifrelemeyi sağlamak, hizmetin varsayılan olarak daha güvenli olduğundan emin olmak ve Microsoft Office 365 gibi diğer Microsoft hizmetleriyle uyum sağlamak için Aktarım Katmanı Güvenliği (TLS) protokol sürümü 1.2’yi destekleyecektir. Office, bu değişikliği MC128929 sürümünde gerçekleştirmişti.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
31 Ekim 2018 tarihinden itibaren Intune artık TLS protokol sürümü 1.0 veya 1.1’i desteklemeyecektir. Intune’a sorunsuz bir şekilde bağlanmak için tüm istemci-sunucu ve tarayıcı-sunucu birleşimlerinin TLS 1.2 sürümünü kullanması gerekir. Bu değişikliğin, artık Intune tarafından desteklenmeyen ancak Intune yoluyla ilke almaya devam eden ve TLS sürüm 1.2’yi kullanamayacak olan son kullanıcı cihazlarını etkileyeceğine dikkat edin. Android 4.3 ve öncesi çalıştıran cihazlar gibi cihazlar buna dahildir. Etkilenen cihazlar ve tarayıcılar listesi için aşağıdaki Ek Bilgiler kısmına bakın.

31 Ekim 2018’den itibaren, eski bir TLS sürümünün kullanımıyla ilgili bir sorun yaşarsanız, çözümün bir parçası olarak sizden TLS 1.2’ye güncelleştirmeniz veya TLS 1.2 destekleyen bir cihaza geçmeniz istenecektir.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Ortamlarınızdaki TLS 1.0 ve 1.1 bağımlılıklarını önceden kaldırmanızı ve mümkün olan her yerde işletim sistemi düzeyinde TLS 1.0 ve 1.1’i devre dışı bırakmanızı öneririz. TLS 1.2’ye geçişinizi planlamaya hemen başlayın. Şu anda Intune tarafından desteklenmeyen ancak yine de ilke alma ihtimali olan ve TLS sürüm 1.2 ile iletişim kuramayacak olan cihazlar listesi için aşağıdaki web günlüğü gönderisine bakın. Bu son kullanıcıları, şirket kaynaklarına erişimi kaybedecekleri konusunda bilgilendirmeniz gerekebilir.

**Ek Bilgi**: [Şifreleme için Intune’un TLS 1.2’ye taşınması](https://blogs.technet.microsoft.com/intunesupport/2018/06/05/intune-moving-to-tls-1-2-for-encryption/)

### <a name="plan-for-change-new-windows-10-setting-for-kiosk-configuration-in-intune----1560072---"></a>Değişiklik Planı: Intune’da Bilgi Noktası Yapılandırması için Yeni Windows 10 Ayarı <!-- 1560072 -->
Windows 10 1709 ve üzeri (RS3 ve üzeri) masaüstü cihazların Intune Azure portalında nerede ve nasıl yapılandırıldığını değiştiriyoruz.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek? 
Kayıtlarımız, Windows 10 > Cihaz Kısıtlamaları > Bilgi Noktası (önizleme) ayarını kullandığınızı gösteriyor. Bu ayar, artık kullanılması önerilmediği için Mayıs ayında kullanıcı arabiriminde Windows 10 > Cihaz Kısıtlamaları > Bilgi Noktası (eski) olarak yeniden adlandırılacak. Ancak Intune’a gelecek Temmuz ayı güncelleştirmesine kadar işlevsel kalacak. Daha sonra arka uçta kullanımdan kaldırılacak ve artık çalışmayacak. Alternatif olarak Mayıs ayında yeni bir Cihaz yapılandırma profili yayımlayacağız: Windows 10 > Bilgi Noktası. Bu profil, Windows 10 RS4 ve üzeri sürümlerde Bilgi Noktalarını yapılandırmaya yönelik ayarlar barındıracak.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?  
Intune Mayıs ayı sonuna doğru Mayıs hizmet güncelleştirmesini yayımladığında, Bilgi Noktası yapılandırmanızı Windows 10 RS3’ten Windows 10 RS4’e geçirebiliyor olduğunuzu test edip doğrulamanız için gerekli yönergeleri paylaşacağız. Bilgi Noktaları için yeni cihaz yapılandırma profilini kullanarak cihazlarınızı Bilgi Noktaları olarak yapılandırmak adına bu yönergeleri kullanabilirsiniz.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Bu değişiklik, hem tek başına Intune müşterilerini hem de karma (Configuration Manager ile Intune) müşterileri etkileyecek. Bu tümleştirme, bulut yönetim idaresini basitleştirmenize yardımcı olacak. Böylece Azure’da grupları, ilkeleri, uygulamaları ve tüm mobil cihazları yönetmek için gitmeniz gereken yalnızca bir dikey pencere olacak (Intune dikey penceresi).

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Lütfen Intune Uygulama Koruması yerine Intune’u sık kullanılan olarak etiketleyin ve Intune içerisindeki Mobil uygulama dikey penceresinde bulunan Uygulama koruma ilkesi iş akışını inceleyin. Kısa bir süreliğine yenilen yönlendirme yapacağız ancak daha sonra Uygulama Koruma dikey penceresini kaldıracağız. Intune’da tüm Uygulama Koruma ilkelerine zaten son verildiğini ve tüm koşullu erişim ilkelerinizi şu belgeleri izleyerek değiştirebileceğinizi unutmayın: [https://aka.ms/azuread_ca](https://aka.ms/azuread_ca).

**Ek bilgiler**: [https://aka.ms/intuneapppolicy](https://aka.ms/intuneapppolicy)

### <a name="plan-for-change-change-in-support-for-the-microsoft-intune-app-sdk-for-cordova-plugin"></a>Değişiklik Planı: Cordova eklentisi için Microsoft Intune Uygulama SDK’sı desteğinde değişiklik
Intune, [Microsoft Intune Uygulama SDK’sı Cordova Eklentisi](app-sdk-cordova.md) için desteği 1 Mayıs 2018 tarihinde kesiyor. Cordova temelli uygulamalarınızı yönetilebilirlik ve kullanılabilirliğe hazırlamak için Intune Uygulama Sarmalama Aracı’nı kullanmanızı öneririz. Bu değişiklik gerçekleştiğinde, Cordova eklentisi için Microsoft Intune Uygulama SDK’sı artık bakıma alınmayacak veya güncelleştirme almayacak. Uygulama geliştiriciler bu eklentiyi kullanamayacaklar. Intune, Cordova ile oluşturulmuş uygulamaları desteklemeye devam etmeyi planlamaktadır. Ancak Cordova eklentisi için Microsoft Intune Uygulama SDK’sı ile oluşturulmuş uygulamalar Intune’da düşük işlevsellikle karşı karşıya kalabilir. Intune Uygulama Sarmalama Aracı ile sarmaladıktan sonra uygulamalar, normalde olduğu gibi son kullanıcılara dağıtılabilir. Google Play Store’a yayımlanmış Cordova temelli Android uygulamalar için:
- İlk başlatmada Intune ilkesi almak için kullanıcılardan kimlik bilgileri istenecek.
- Uygulamalar, uygulama mağazasına Intune kullanıcılarını hedefleyecek şekilde yayımlanmalıdır, örneğin “Intune için Contoso Uygulaması”.

Uygulama Sarmalama Aracı hakkında daha fazla bilgi için bkz. [iOS için Uygulama Sarmalama Aracı](app-wrapper-prepare-ios.md) ve [Android için Uygulama Sarmalama Aracı](app-wrapper-prepare-android.md). Herhangi bir soru veya sorununuz için [msintuneappsdk@microsoft.com](mailto:msintuneappsdk@microsoft.com) ile iletişime geçin.

### <a name="plan-for-change-use-intune-on-azure-now-for-your-mdm-management----1227338---"></a>Değişiklik Planı: Artık MDM yönetiminiz için Azure’da Intune kullanabilirsiniz <!-- 1227338 -->
Bir yılı aşkın bir süre önce [Azure’da Intune’un genel önizlemesini](https://cloudblogs.microsoft.com/enterprisemobility/2016/12/07/public-preview-of-intune-on-azure/) duyurup altı ay önce Intune için [yeni yönetici deneyiminin genel kullanılabilirliğini](https://cloudblogs.microsoft.com/enterprisemobility/2017/06/08/the-new-intune-and-conditional-access-admin-consoles-are-ga/) yayımlamıştık. 31 Ağustos 2018 itibarıyla, tek başına Intune kullanan müşteriler için klasik Silverlight konsolunda mobil cihaz yönetimini (MDM) kaldıracağız. Bunun yerine MDM ihtiyaçlarınız için [Azure’da Intune](https://aka.ms/Intune_on_Azure) kullanabilirsiniz. MDM için hala klasik konsolu kullanıyorsanız, lütfen bundan vazgeçin ve Azure üzerinden Intune kullanmaya alışın. Bu değişiklik ile hiçbir son kullanıcı etkisi beklemiyoruz. Klasik bilgisayar yönetimi Silverlight’ta kalacaktır. [Buraya](https://aka.ms/Intune_on_Azure_mdm) tıklayarak bu değişikliğin sizi nasıl etkileyeceği hakkında daha fazla bilgi alabilirsiniz.

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Apple kayıt senaryolarına doğrudan erişim <!--951869-->
Intune, Azure portalındaki Cihaz Kaydetme iş yükünü kullanarak Apple kayıt senaryolarına doğrudan erişimi Ocak 2017 sonrasında oluşturulan Intune hesapları için etkinleştirdi. Daha önce, Apple kayıt önizleme sürümüne yalnızca klasik Intune portalı bağlantıları ile erişilebiliyordu. Bu özelliklerin Azure’da kullanılabilmesi için Ocak 2017 öncesi oluşturulan Intune hesaplarında tek seferlik bir geçiş yapılması gerekir. Geçiş için zaman çizelgesi henüz açıklanmamıştır, ancak konuya ilişkin ayrıntılar olabildiğince çabuk duyurulacaktır. Mevcut hesabınız Azure portalına erişemiyorsa yeni deneyimi sınamak için bir deneme hesabı oluşturmanızı kesinlikle öneririz.

## <a name="whats-coming"></a>Yakında

### <a name="local-device-security-option-settings----1251887---"></a>Yerel cihaz güvenliği seçeneği ayarları <!-- 1251887 -->
Yeni Yerel Cihaz Güvenlik Seçeneği ayarlarını kullanarak Windows 10 cihazlarda güvenlik ayarlarını etkinleştirebileceksiniz. Bu ayarları, bir Windows 10 cihaz yapılandırma ilkesi oluşturduğunuzda Endpoint Protection kategorisinde bulabilirsiniz.

### <a name="new-user-experience-update-for-the-company-portal-website---2000968--"></a>Şirket Portalı web sitesi için yeni kullanıcı deneyimi güncelleştirmesi <!--2000968-->

Kullanıcı arabirimi güncelleştirmeleri, kolaylaştırılmış iş akışları ve erişilebilirlik iyileştirmeleri içeren bir Şirket Portalı web sitesi deneyimini Nisan ayında tanıtacağız. Bunun içerisinde, size daha kullanıcı dostu bir deneyim sunmak için uygulama paylaşımı ve iyileştirilmiş genel performans gibi müşteri odaklı iyileştirmeler olacak.
Sizin gibi müşterilerden aldığımız geri bildirimlere dayanarak bazı yeni özellikler ekledik. Bu özellikler, geçerli işlevsellik ve kullanılabilirliği büyük oranda artıracak:

* Web sitesi üzerinde kullanıcı arabirimi iyileştirmeleri
* Doğrudan uygulama bağlantıları paylaşabilme seçeneği
* Büyük uygulama katalogları için iyileştirilmiş performans

Bu değişikliğe hazırlanmak için herhangi bir şey yapmanız gerekmez. Güncelleştirilmiş Şirket Portalı web sitesi kullanılabilir duruma geldiğinde size haber vereceğiz. Ancak daha sonra son kullanıcı belgelerini güncel ekran görüntüleriyle güncelleştirmeniz gerekebilir. iOS uygulamasının **Uygulamalar** bölümü web sitesi tarafından sağlandığı için iOS’ta Şirket Portalı belgelerini de güncelleştirmeniz gerekebileceğine dikkat edin. [Uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md) sayfasında bunun için bir örnek görüntü görebilirsiniz.

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple, Uygulama Taşıma Güvenliği için güncelleştirmeler gerektirecek <!--748318-->
Apple, Uygulama Taşıma Güvenliği (ATS) için belirli gereksinimler uygulayacağını açıkladı. ATS, HTTPS üzerinden yapılan tüm uygulama iletişimlerinde daha sıkı güvenlik uygulamak için kullanılır. Bu değişiklik, iOS Şirket Portalı uygulamaları kullanan Intune müşterilerini etkiler. [Intune destek web günlüğümüzü](https://aka.ms/compportalats) ayrıntılarla güncelleyeceğiz.



## <a name="see-also"></a>Ayrıca bkz:
* [Microsoft Intune Blogu](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform yol haritası](https://www.microsoft.com/cloud-platform/roadmap)
* [Şirket Portalı kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md)
* [Önceki aylardaki yenilikler](whats-new-archive.md)
