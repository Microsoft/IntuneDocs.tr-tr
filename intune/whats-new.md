---
title: Microsoft Intune - Azure’daki yenilikler | Microsoft Docs
titlesuffix: ''
description: Intune Azure portalındaki yenilikleri keşfedin
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/27/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
ms.custom: intune-azure; get-started
ms.openlocfilehash: 567a28679b244088af8c943eb483eb4b2b4d88be
ms.sourcegitcommit: 2795255e89cbe97d0b17383d446cca57c7335016
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2018
ms.locfileid: "47403638"
---
# <a name="whats-new-in-microsoft-intune"></a>Microsoft Intune'daki yenilikler
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune’daki haftalık yenilikleri öğrenin. [Yaklaşan değişiklikler](#whats-coming), hizmet hakkında [önemli bildirimler](#notices) ve [geçmiş sunumlar](whats-new-archive.md) hakkında bilgiler de alabilirsiniz. Bazı özelliklerin piyasaya çıkması birkaç haftayı bulabilir ve tüm özellikler ilk hafta bütün müşterilerimize sunulmamış olabilir.

> [!Note]
> Karma mobil cihaz yönetimindeki (MDM) yeni işlevler hakkında bilgi için, [karma Yenilikler sayfasını](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) gözden geçirin.


<!-- Common categories:  
### App management
### Device configuration
### Device enrollment
### Device management
### Intune apps
### Monitor and troubleshoot
### Role-based access control

-->   

## <a name="week-of-september-24-2018"></a>24 Eylül 2018 haftası

### <a name="microsoft-365-device-management-administration-center----3078424---"></a>Microsoft 365 Cihaz Yönetimi yönetim merkezi <!-- 3078424 -->
Microsoft 365'in vadettiği en önemli şeylerden biri basitleştirilmiş yönetimdir ve Intune ve Azure AD koşullu erişim gibi uçtan uca senaryoları sunmak için yıllardır yaptığımız çalışmalarla arka uç Microsoft 365 hizmetlerini tümleştirdik. Yönetim deneyimini birleştirmenin, basitleştirmenin ve tümleştirmenin yeri yeni [Microsoft 365 yönetim merkezidir](http://devicemanagement.microsoft.com). Cihaz Yönetimi için uzman çalışma alanı, kuruluşunuz için gereken tüm cihaz ve uygulama yönetim bilgi ve görevlerine kolay erişim sağlar. Buranın kurumsal son kullanıcı bilgi işlem ekipleri için birinci bulut çalışma alanı haline gelmesini bekliyoruz.

### <a name="support-for-more-third-party-certification-authorities-ca----3093107---"></a>Daha çok sayıda sertifika yetkilisine (CA) destek <!-- 3093107 -->
Basit Sertifika Kayıt Protokolü'nü (SCEP) kullanarak artık Windows, iOS, Android ve macOS kullanan mobil cihazlarda yeni sertifika verebilir ve mevcut sertifikaları yenileyebilirsiniz.

## <a name="week-of-september-17-2018"></a>17 Eylül 2018 haftası

### <a name="app-management"></a>Uygulama yönetimi

### <a name="remove-duplication-of-app-protection-status-tiles----3083391---"></a>Yinelenen uygulama koruması durum kutucuklarını kaldırma <!-- 3083391 -->
**iOS için kullanıcı durumu** ve **Android için kullanıcı durumu** kutucuklarının ikisi de **İstemci Uygulamalar - Genel Bakış** sayfasında ve **İstemci Uygulamalar - Uygulama koruma durumu** sayfasında vardı. Durum kutucukları, yineleme olmaması için **İstemci Uygulamalar - Genel Bakış** sayfasından kaldırılmıştır. 

## <a name="week-of-august-27-2018"></a>27 Ağustos 2018 Haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="packet-tunnel-support-for-ios-per-app-vpn-profiles-for-custom-and-pulse-secure-connection-types----1520957---"></a>Özel ve Pulse Secure bağlantı türleri için iOS uygulama başına VPN profilleri için paket tüneli desteği <!-- 1520957 -->
iOS uygulama başına VPN profillerini kullanırken uygulama katman tüneli (uygulama-proxy) veya paket düzeyi tünel (paket-tünel) kullanabilirsiniz. Bu seçenekler, aşağıdaki bağlantı türleri ile kullanılabilir:
- Özel VPN
- Pulse Secure Hangi değeri kullanmanız gerektiğini bilmiyorsanız VPN sağlayıcınızın belgelerine başvurun.

#### <a name="delay-when-ios-software-updates-are-shown-on-the-device----1949583---"></a>Cihazda iOS yazılım güncelleştirmelerinin gösterilmesini geciktirme <!-- 1949583 -->
Intune > **Yazılım Güncelleştirmeleri** > **iOS güncelleştirme ilkeleri**’nde cihazların güncelleştirme yüklemesini istemediğiniz gün ve saatleri yapılandırabilirsiniz. Gelecek bir güncelleştirme ile bir yazılım güncelleştirmesinin cihazda görüntülenmesini 1-90 gün kadar geciktirebileceksiniz. 
[Microsoft Intune’da iOS güncelleştirme ilkelerini yapılandırma](software-updates-ios.md) makalesi, geçerli ayarları listeler.

#### <a name="office-365-proplus-version----2213968---"></a>Office 365 ProPlus sürümü <!-- 2213968 -->
Intune kullanarak Office 365 ProPlus uygulamalarını Windows 10 cihazlara atarken Office sürümünü seçebilirsiniz. Azure portalında **Microsoft Intune** > **Uygulamalar** > **Uygulama ekle**’yi seçin. Daha sonra açılan **Tür** listesinden **Office 365 ProPlus Paketi (Windows 10)**’u seçin. İlişkili dikey pencereyi görüntülemek için **Uygulama Paketi Ayarları**’nı seçin. **Güncelleştirme Kanalı** için bir değer ayarlayın, örneğin **Aylık**. İsteğe bağlı olarak **Evet**’i seçin ve son kullanıcı cihazlarından diğer Office (msi) sürümünü kaldırın. Son kullanıcı cihazlarında seçili kanal için belirli bir Office sürümü yüklemek için **Belirli**’yi seçin. Bu noktada Office’in **Belirli bir sürüm**ünü seçip kullanabilirsiniz. Kullanılabilir sürümler zaman içerisinde değişir. Bu neden yeni bir dağıtım oluştururken kullanılabilir sürümler daha yeni olabilir ve bazı eski sürümleri bulamayabilirsiniz. Mevcut dağıtımlar eski sürümü dağıtmaya devam eder ancak her kanaldaki sürüm listesi sürekli olarak güncelleştirilir. Daha fazla bilgi için bkz. [Office 365 ProPlus güncelleştirme kanallarına genel bakış](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus).

#### <a name="support-for-register-dns-setting-for-windows-10-vpn----2282852---"></a>Windows 10 VPN için DNS ayarı kaydetme desteği <!-- 2282852 -->
Bu güncelleştirme ile Windows 10 VPN profillerini, VPN arabirimine atanmış IP adreslerini özel profil kullanmaya ihtiyaç duymadan dinamik olarak dahili DNS’e kaydedecek şekilde yapılandırabilirsiniz.
Kullanabileceğiniz geçerli VPN profil ayarları hakkında bilgi için bkz. [Windows 10 VPN ayarları](vpn-settings-windows-10.md). 

#### <a name="the-macos-company-portal-installer-now-includes-the-version-number-in-the-installer-file-name---2652728--"></a>macOS Şirket Portalı yükleyicisi artık sürüm numarası ve yükleyici dosya adını içeriyor <!--2652728-->

#### <a name="ios-automatic-app-updates----2729759-wnready---"></a>iOS otomatik uygulama güncelleştirmeleri <!-- 2729759 wnready -->
Otomatik uygulama güncelleştirmeleri, iOS sürüm 11.0 ve üzerinde cihaz ve kullanıcı lisanslı uygulamalar için kullanılabilir.




### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="windows-hello-will-target-users-and-devices----1106609---"></a>Windows Hello, kullanıcıları ve cihazları hedefleyecek <!-- 1106609 -->
Bir [İş İçin Windows Hello](windows-hello.md) ilkesi oluşturduğunuzda bu ilke, kuruluştaki tüm kullanıcılara (kiracı genelinde) uygulanır. Bu güncelleştirmeyle ilke, bir cihaz yapılandırma ilkesi kullanılarak belirli kullanıcılara veya belirli cihazlara da (**Cihaz Yapılandırması** > **Profiller** > **Profil oluştur** > **Kimlik Koruma** > **İş İçin Windows Hello**) uygulanabilecek.
Azure portalında Intune’da Windows Hello yapılandırması ve ayarları artık hem **Cihaz kaydı** hem de **Cihaz yapılandırması** bölümlerinde bulunuyor. **Cihaz kaydı**, kuruluşun tamamını (kiracı genelinde) hedefler ve Windows AutoPilot (OOBE) destekler. **Cihaz yapılandırması**, iade sırasında uygulanan bir ilkeyi kullanarak cihazları ve kullanıcıları hedefler.
Bu özellik şu platformlarda geçerlidir:  
- Windows 10 ve üzeri
- Windows 10 Holographic for Business

#### <a name="zscaler-is-an-available-connection-for-vpn-profiles-on-ios----1769858-eeready---"></a>iOS’ta VPN profilleri için Zscaler bağlantısı kullanılabilir <!-- 1769858 eeready -->
Bir iOS VPN cihaz yapılandırma profili oluşturduğunuzda (**Cihaz yapılandırması** > **Profiller** > **Profil oluştur** > **iOS** platform > **VPN** profil türü) Cisco, Citrix vb. gibi birkaç bağlantı türü vardır. Bu güncelleştirme ile Zscaler da bir bağlantı türü olarak eklendi. 
[iOS çalıştıran cihazlar için VPN ayarları](vpn-settings-ios.md), kullanılabilir bağlantı türlerini listeler.

#### <a name="fips-mode-for-enterprise-wi-fi-profiles-for-windows-10----1879077-eeready---"></a>Windows 10 için Kurumsal Wi-Fi profilleri için FIPS modu <!-- 1879077 eeready -->
Intune Azure portalında Windows 10 için Kurumsal Wi-Fi profilleri için artık Federal Bilgi İşleme Standardı (FIPS) modunu etkinleştirebilirsiniz. FIPS modunu Wi-Fi profillerinizde etkinleştirirseniz Wi-Fi altyapınızda etkinleştirmeyi de unutmayın.
[Intune’da Windows 10 ve üzeri cihazlar için Wi-Fi ayarları](wi-fi-settings-windows.md) makalesi, bir Wi-Fi profilini nasıl oluşturacağınızı gösterir.

#### <a name="control-s-mode-on-windows-10-and-later-devices---public-preview----1958649---"></a>Windows 10 ve üzeri cihazlarda S modunu denetleme - genel önizleme <!-- 1958649 -->
Bu özellik güncelleştirmesi ile Windows 10 cihazı S modundan çıkaran veya kullanıcıların cihazı S modundan çıkarmasını önleyen bir cihaz yapılandırma profili oluşturabilirsiniz. Bu özellik Intune’da **Cihaz yapılandırması** > **Profiller** >  **Windows 10 ve üzeri** > **Sürüm yükseltme ve mod değiştirme** altındadır.
[S modunda Windows 10’a giriş](https://www.microsoft.com/windows/s-mode) makalesi, S modu hakkında daha fazla bilgi sağlar.
Şunlar için geçerlidir: En son [Windows Insider](https://docs.microsoft.com/en-us/windows-insider/at-work-pro/) derlemesi (önizlemedeyken).


#### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Windows Defender ATP yapılandırma paketi, otomatik olarak yapılandırma profiline eklenir <!-- 2144658 -->
Eskiden Intune’da [Gelişmiş Tehdit Koruması ve ekleme](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile) cihazları kullanırken bir yapılandırma paketini indirip bunu yapılandırma profilinize ekliyordunuz. Bu güncelleştirme ile Intune, paketi otomatik olarak Windows Defender Güvenlik Merkezi’nden alır ve profilinize ekler.
Windows 10 ve üzeri için geçerlidir.

#### <a name="require-users-to-connect-during-device-setup---2311457--"></a>Cihaz kurulumu sırasında kullanıcıların bağlanmasını gerektirme <!--2311457-->
Artık Windows 10 kurulumu sırasında Ağ sayfasından ileri gitmeden önce cihazın bir ağa bağlanmasını gerektirecek cihaz profilleri ayarlayabilirsiniz. Bu özellik önizlemedeyken bu ayarı kullanmak için Windows Insider derleme 1809 veya sonrası gerekir.
Şunlar için geçerlidir: En son [Windows Insider](https://docs.microsoft.com/en-us/windows-insider/at-work-pro/) derlemesi (önizlemedeyken).


#### <a name="restricts-apps-and-block-access-to-company-resources-on-ios-and-android-enterprise-devices----2451462---"></a>iOS ve Android Kurumsal cihazlarında uygulamaları kısıtlama ve şirket kaynaklarına erişimi engelleme <!-- 2451462 -->
**Cihaz uyumluluğu** > **İlkeler** > **İlke oluştur** > **iOS** > **Sistem Güvenliği**’nde yeni **Kısıtlı uygulamalar** ayarı var. Bu yeni ayar, bazı uygulamalar cihaza yüklendiğinde cihazın şirket kaynaklarına erişimini engelleyecek bir uyumluluk ilkesi kullanır. Cihaz, kısıtlı uygulamalar kaldırılana kadar uyumsuz sayılır.
Şunun için geçerlidir: iOS

#### <a name="modern-vpn-support-updates-for-ios----2459928-1819876-and-2650856---"></a>iOS için modern VPN destek güncelleştirmeleri <!-- 2459928, 1819876, and 2650856 -->
Bu güncelleştirme, aşağıdaki iOS VPN istemcileri için destek ekliyor: 
- F5 Erişimi (sürüm 3.0.1 ve üzeri)
- Citrix SSO
- Palo Alto Networks GlobalProtect sürüm 5.0 ve üzeri Bu güncelleştirmede ayrıca:
- iOS için mevcut**F5 Access** bağlantı türü, **F5 Access Eski** olarak yeniden adlandırıldı.
- iOS için mevcut**Palo Alto Networks GlobalProtect** bağlantı türü, **Palo Alto Networks GlobalProtect (eski)** olarak yeniden adlandırıldı.
Bu bağlantı türlerine sahip mevcut profiller, eski VPN istemcileriyle çalışmaya devam edecek. iOS ile Cisco Eski AnyConnect, F5 Access Eski, Citrix VPN veya Palo Alto Networks GlobalProtect sürüm 4.1 ve öncesi kullanıyorsanız yeni uygulamalara geçmelisiniz. iOS 12 sonrası iOS cihazlarda VPN erişiminin kullanılabilir olmasını sağlamak için bunu en kısa zamanda yapmalısınız.
iOS 12 ve VPN profilleri hakkında daha fazla bilgi için bkz. [Microsoft Intune Destek Ekibi Blogu](https://go.microsoft.com/fwlink/?linkid=2013806).

#### <a name="export-azure-classic-portal-compliance-policies-to-recreate-these-policies-in-the-intune-azure-portal----2469637---"></a>Klasik Azure portalı uyumluluk ilkelerini dışarı aktararak bunları Intune Azure portalında yeniden oluşturma <!-- 2469637 -->
Azure klasik portalında oluşturulan ilkeler artık kullanım dışı olacak. Mevcut uyumluluk ilkelerini gözden geçirebilir ve silebilirsiniz ancak güncelleştiremezsiniz. Bazı mevcut uyumluluk ilkelerini geçerli Intune Azure portalına geçirmek istiyorsanız bunları virgülle ayrılmış bir dosyayla (*.csv* dosyası) dışarı aktarabilirsiniz. Daha sonra Intune Azure portalında bu ilkeleri yeniden oluşturmak için dosyadaki ayrıntıları kullanabilirsiniz.

> [!IMPORTANT]
> Azure klasik portalı kullanımdan kalktıktan sonra uyumluluk ilkelerinize erişme veya bunları görüntüleme şansınız olmayacak. Bu sebeple Azure klasik portalı kullanımdan kaldırılmadan önce ilkelerinizi dışarı aktarıp Azure portalında yeniden oluşturduğunuzdan emin olun.

#### <a name="better-mobile---new-mobile-threat-defense-partner----22662717---"></a>Better Mobile - Yeni Mobil Tehdit Savunması iş ortağı <!-- 22662717 -->
Microsoft Intune ile tümleştirilen bir Mobil Tehdit Savunması çözümü olan Better Mobile tarafından yapılan risk değerlendirmesine göre koşullu erişim kullanarak mobil cihazlardan şirket kaynaklarına erişimi denetleyebilirsiniz.

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="lock-the-company-portal-in-single-app-mode-until-user-sign-in---1067692---"></a>Kullanıcı oturum açana kadar Şirket Portalı’nı tek uygulama modunda kilitleme <!--1067692 --> 
DEP kaydı sırasında bir kullanıcının kimliğini Kurulum Yardımcısı yerine Şirket Portalı ile doğrularsanız, artık Şirket Portalı’nı Tekli Uygulama modunda çalıştırma seçeneğiniz var. Bu seçenek, Kurulum Yardımcısı tamamlandıktan hemen sonra cihazı kilitler; böylece kullanıcının cihaza erişmek için oturum açması gerekir. Bu işlem, cihazın eklenmesinin tamamlanmasını ve kullanıcısı olmadan yalnız bırakılmış duruma gelmemesini sağlar.

#### <a name="assign-a-user-and-friendly-name-to-an-autopilot-device---1346521---"></a>Autopilot cihazına kullanıcı ve kolay ad atama <!--1346521 -->
Artık [tek bir Autopilot cihazına kullanıcı atayabilirsiniz](enrollment-autopilot.md). Yöneticiler ayrıca cihazlarını AutoPilot ile ayarlayan kullanıcıları karşılaması için kolay adlar verebilecekler.
Şunlar için geçerlidir: En son [Windows Insider](https://docs.microsoft.com/en-us/windows-insider/at-work-pro/) derlemesi (önizlemedeyken).

#### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>DEP kaydı sırasında Şirket Portalı’nın ön sağlamasını yapmak için VPP cihaz lisanslarını kullanın <!-- 1608345 -->
Artık Aygıt Kayıt Programı (DEP) kayıtları sırasında Şirket Portalı’nın ön sağlamasını yapmak için Volume Purchase Program (VPP) cihaz lisanslarını kullanabileceksiniz. Bunu yapmak için [bir kayıt profili oluşturduğunuzda veya düzenlediğinizde](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile), Şirket Portalı’nı yüklemek için kullanmak istediğiniz VPP belirtecini belirtin. Belirtecinizin süresinin dolmadığından ve Şirket Portalı uygulaması için yeterli lisansınız olduğundan emin olun. Belirtecin süresi dolduğu veya yeterli lisans olmadığı durumlarda, Intune bunun yerine Uygulama Mağazası Şirket Portalı’na istek gönderir (bu, Apple kimliği ister).

#### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Şirket Portalı ön sağlaması için kullanılan bir VPP belirtecini silmek için onay gerekir <!-- 2237634 -->
DEP kaydı sırasında Şirket Portalı’nın ön sağlaması için bir Volume Purchase Program (VPP) belirteci kullanılıyorsa artık bunu silmek için onay gerekir.

#### <a name="block-windows-personal-device-enrollments----1849498---"></a>Windows kişisel cihaz kayıtlarını engelleme <!-- 1849498 -->
[Windows kişisel cihazları engelleyerek](enrollment-restrictions-set.md#set-device-type-restrictions) Intune [mobil cihaz yönetimine](windows-enroll.md) kaydolmasını önleyebilirsiniz. Bu özellikle [Intune PC aracısı](manage-windows-pcs-with-microsoft-intune.md) ile kaydedilen cihazlar engellenemez. Bu özellik, önümüzdeki birkaç hafta içerisinde yayımlanacak, bu nedenle kullanıcı arabiriminde özelliği hemen göremeyebilirsiniz.

#### <a name="specify-machine-name-patterns-in-an-autopilot-profile---1849855--"></a>Autopilot profilinde makine adı desenleri belirtme <!--1849855-->
Autopilot kaydı sırasında [bilgisayar adı](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) oluşturmak ve ayarlamak için [bir bilgisayar adı şablonu](enrollment-autopilot.md#create-an-autopilot-deployment-profile) belirtebilirsiniz. Şunlar için geçerlidir: En son [Windows Insider](https://docs.microsoft.com/en-us/windows-insider/at-work-pro/) derlemesi (önizlemedeyken).


#### <a name="for-windows-autopilot-profiles-hide-the-change-account-options-on-the-company-sign-in-page-and-domain-error-page---1901669---"></a>Windows Autopilot profilleri için şirket oturum açma sayfasında ve etki alanı hata sayfasında hesap değiştirme seçeneklerini gizleme <!--1901669 -->
Yöneticilerin şirket oturum açma ve etki alanı hata sayfalarında hesap değiştirme seçeneklerini gizlemelerine imkan veren [yeni Windows Autopilot profil seçenekleri](enrollment-autopilot.md#create-an-autopilot-deployment-profile) mevcut. Bu seçenekleri gizlemek, Azure Active Directory’de Şirket Markasının yapılandırılmasını gerektirir. Şunlar için geçerlidir: En son [Windows Insider](https://docs.microsoft.com/en-us/windows-insider/at-work-pro/) derlemesi (önizlemedeyken).



### <a name="device-management"></a>Cihaz yönetimi

#### <a name="delete-jamf-devices----2653306--"></a>Jamf cihazlarını silme <!-- 2653306-->
**Cihazlar**’a gidip JAMF cihazını ve daha sonra **Sil**’i seçerek JAMF tarafından yönetilen cihazları silebilirsiniz.

#### <a name="change-terminology-to-retire-and-wipe----2175759---"></a>Terminolojiyi "kullanım dışı bırakma" ve "temizleme" olarak değiştirin <!-- 2175759 -->
Graph API ile tutarlılığı sağlamak için Intune kullanıcı arabirimi ve belgelerine aşağıdaki terim değişiklikleri yansıtıldı:
- **Şirket verilerini kaldırma** terimi, “kullanımdan kaldırma” olarak değiştirilecek
- **Fabrika sıfırlaması** terimi **temizleme** olarak değiştirilecek

#### <a name="confirmation-dialog-if-admin-tries-to-delete-mdm-push-certificate----297909500--"></a>Yönetici MDM Anında İletme Sertifikası’nı silmeye çalıştığında onay iletişim kutusu <!-- 297909500-->
Apple MDM Anında İletme Sertifikası silinmeye çalışılırsa, ilgili iOS ve macOS cihaz sayısını gösteren bir onay iletişim kutusu görüntülenir. Sertifika silinirse bu cihazların yeniden kaydedilmesi gerekir.

### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Windows Installer için ek güvenlik ayarları <!-- 2282430 -->
Kullanıcıların uygulama yüklemelerini denetlemesine olanak sağlayabilirsiniz. Etkinleştirilirse, aksi takdirde güvenlik ihlali nedeniyle durdurulabilecek olan yüklemelerin devam etmesine izin verilebilir. Windows Installer'ı sistemde herhangi bir program yüklerken yükseltilmiş izinler kullanmaya yönlendirebilirsiniz. Buna ek olarak, Windows Bilgi Koruması (WIP) öğelerinin dizine alınmasını ve bunlar hakkındaki meta verilerin şifrelenmemiş bir konumda depolanmasını etkinleştirebilirsiniz. İlke devre dışı bırakıldığında, WIP korumalı öğelerin dizini oluşturulmaz ve Cortana veya dosya gezgini sonuçlarında görünmez. Bu seçeneklerin işlevselliği varsayılan olarak devre dışı bırakılmıştır. 

### <a name="new-user-experience-update-for-the-company-portal-website---2000968---"></a>Şirket Portalı web sitesi için yeni kullanıcı deneyimi güncelleştirmesi <!--2000968 -->
Müşterilerden gelen geri bildirim temelinde Şirket Portalı web sitesine yeni özellikler ekledik. Cihazlarınızın mevcut işlevselliğinde ve kullanılabilirliğinde önemli gelişmeler göreceksiniz. Sitenin &ndash;cihaz ayrıntıları, geri bildirim ve destek, cihaza genel bakış gibi&ndash; alanlarında yeni, modern, hızlı yanıt veren bir tasarım bulunuyor. Şunları da göreceksiniz:

- Tüm cihaz platformları arasında rahat iş akışları
- Geliştirilmiş cihaz kimlik ve kayıt akışları
- Daha yararlı hata iletileri
- Daha rahat bir dil, daha az teknik jargon
- Doğrudan uygulama bağlantıları paylaşabilme seçeneği
- Büyük uygulama katalogları için iyileştirilmiş performans
- Tüm kullanıcılar için artırılmış erişilebilirlik  

[Intune Şirket Portalı belgeleri](https://docs.microsoft.com/en-us/intune-user-help/using-the-intune-company-portal-website) de bu değişiklikleri yansıtacak şekilde güncelleştirildi. Uygulama iyileştirmelerine dair bir örnek görmek isterseniz bkz. [Intune son kullanıcı uygulamaları için kullanıcı arabirimi güncelleştirmeleri](whats-new-app-ui.md).  

### <a name="monitor-and-troubleshoot"></a>İzleme ve sorun giderme

#### <a name="enhanced-jailbreak-detection-in-compliance-reporting---2198738---"></a>Uyumluluk raporlamada gelişmiş jailbreak algılama <!-- 2198738 -->
Gelişmiş jailbreak algılama ayarı durumları, artık yönetici konsolundaki tüm uyumluluk raporlarında görünüyor.

### <a name="role-based-access-control"></a>Rol tabanlı erişim denetimi

#### <a name="scope-tags-for-policies---1081974-eeready--"></a>İlkeler için kapsam etiketleri <!--1081974 eeready-->
Intune kaynaklarına erişimi sınırlamak için [kapsam etiketleri oluşturabilirsiniz](scope-tags.md). Bir rol atamasına kapsam etiketi ekleyin ve daha sonra kapsam etiketini bir yapılandırma profiline ekleyin. Rolün yalnızca eşleşen kapsam etiketlerine sahip yapılandırma profillerine erişimi olacaktır.

## <a name="week-of-august-14-2018"></a>14 Ağustos 2018 Haftası

### <a name="macos-support-for-apple-device-enrollment-program----747651---"></a>Apple Aygıt Kayıt Programı için macOS desteği <!-- 747651 -->
Intune, macOS cihazlarının Apple Aygıt Kayıt Programı'na (DEP) kaydedilmesini artık destekleniyor. Daha fazla bilgi için bkz. [macOS cihazlarını Apple’ın Aygıt Kayıt Programı ile otomatik olarak kaydetme](device-enrollment-program-enroll-macos.md).

## <a name="week-of-july-23-2018"></a>23 Temmuz 2018 haftası

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="line-of-business-lob-app-support-for-macos----1895847---"></a>macOS için iş kolu (LOB) uygulamaları desteği <!-- 1895847 -->
Microsoft Intune, macOS LOB uygulamalarının **Gerekli** veya **Kayıt sonrasında kullanılabilir** olarak dağıtılmasına olanak tanır. Son kullanıcılar, uygulamaları macOS için Şirket Portalı’ndan veya [Şirket Portalı web sitesinden](https://portal.manage.microsoft.com) **Kullanılabilir** olarak edinebilir.

#### <a name="ios-built-in-app-support-for-kiosk-mode----2051098---"></a>Bilgi noktası modu için yerleşik iOS uygulama desteği <!-- 2051098 -->
Mağaza Uygulamaları ve Yönetilen Uygulamalara ek olarak artık iOS cihazında bilgi noktası modunda çalışan Safari gibi Yerleşik Uygulamaları da seçebilirsiniz.

#### <a name="edit-your-office-365-pro-plus-app-deployments----2150145---"></a>Office 365 Pro Plus uygulama dağıtımlarınızı düzenleme <!-- 2150145 -->
Microsoft Intune yöneticisi olarak, Office 365 Pro Plus uygulama dağıtımlarınızı düzenleme olanağınız artar. Ayrıca paketin özelliklerinden herhangi birini değiştirmek için artık dağıtımlarınızı silmeniz gerekmez. Azure portalında **Microsoft Intune** > **İstemci uygulamaları** > **Uygulamalar**’ı seçin. Uygulama listesinden Office 365 Pro Plus Suite ürününüz seçin.  


#### <a name="updated-intune-app-sdk-for-android-is-now-available----2744271--"></a>Güncelleştirilmiş Android için Intune Uygulama SDK'sı artık kullanıma sunuldu <!-- 2744271-->

Android P sürümünü desteklemek amacıyla Android için Intune Uygulama SDK'sının güncelleştirilmiş sürümü kullanıma sunuldu. Bir uygulama geliştiricisiyseniz ve Android için Intune SDK'sını kullanıyorsanız, Android uygulamalarınızdaki Intune işlevselliğinin Android P cihazlarında beklendiği gibi çalışmaya devam edebilmesi için Intune uygulama SDK'sının güncelleştirilmiş sürümünü yüklemelisiniz. Intune Uygulama SDK'sının bu sürümü, SDK güncelleştirmelerini gerçekleştiren yerleşik bir eklenti sağlar. Tümleştirilmiş mevcut kodu yeniden yazmanız gerekmez. Ayrıntılar için bkz. [Android için Intune SDK'sı](https://github.com/msintuneappsdk/ms-intune-app-sdk-android). Intune için eski rozetleme stilini kullanıyorsanız, evrak çantası simgesini kullanmanızı öneririz. Markalama ayrıntıları için [bu GitHub deposuna](https://github.com/msintuneappsdk/intune-app-partner-badge) bakın.


### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="use-smime-to-encrypt-and-sign-a-users-multiple-devices-----1333642---"></a>Bir kullanıcının birden fazla cihazını şifrelemek ve imzalamak için S/MIME kullanın <!-- 1333642 -->
Bu güncelleştirme, içeri aktarılmış yeni bir sertifika profili kullanan S/MIME e-posta şifrelemesi içerir (**Cihaz yapılandırması** > **Profiller** > **Profil oluşturun** > platform seçin > **PKCS içeri aktarılan sertifika** profil türü). Intune’da sertifikaları PFX biçiminde içeri aktarabilirsiniz. Intune, aynı sertifikaları tek bir kullanıcı tarafından kaydedilen birden fazla cihaza teslim edebilir. Ayrıca şunları da içerir:

- Yerel iOS e-posta profili, PFX biçiminde içeri aktarılan sertifikaları kullanan S/MIME şifrelemesini etkinleştirmeyi destekler.
- Windows Phone 10 cihazlarındaki yerel posta uygulaması, S/MIME sertifikalarını otomatik olarak kullanır.
- Özel sertifikalar, birden fazla platforma teslim edilebilir. Ancak tüm e-posta uygulamaları, S/MIME’yi desteklemez.
- Diğer platformlarda S/MIME’yi etkinleştirmek için posta uygulamasını el ile yapılandırmanız gerekebilir.  
- S/MIME şifrelemesini destekleyen e-posta uygulamaları, S/MIME e-posta şifrelemesi için sertifika alma işlemini MDM’nin destekleyemeyeceği bir şekilde halleder, ör. yayımcılarının sertifika deposundan okuma.

Desteklenir: Windows, Windows Phone 10, macOS, iOS, Android

#### <a name="create-device-compliance-policy-using-firewall-settings-on-macos-devices----1497640---"></a>macOS cihazlarında Güvenlik Duvarı ayarlarını kullanarak cihaz uyumluluk ilkesi oluşturma <!-- 1497640 -->
Yeni bir macOS uyumluluk ilkesi oluşturduğunuzda (**Cihaz uyumluluğu** > **İlkeler** > **İlke oluştur** > **Platform: macOS** > **Sistem güvenliği**), bazı yeni **Güvenlik Duvarı** ayarları sağlanır: 

- **Güvenlik Duvarı**: Gelen bağlantıların ortamınızda nasıl işleneceğini yapılandırın.
- **Gelen bağlantılar**: DHCP, Bonjour ve IPSec gibi temel İnternet hizmetleri için gerekenler dışında tüm gelen bağlantıları **engelleyin**. Bu ayar tüm paylaşım hizmetlerini de engeller.
- **Gizli Mod**: Cihazın yoklama isteklerine yanıt vermesini önlemek için gizli modu **etkinleştirin**. Cihaz, yetkilendirilmiş uygulamalardan gelen istekleri yanıtlamaya devam eder.

Şunlar için geçerlidir: macOS 10.12 ve üstü

#### <a name="new-wi-fi-device-configuration-profile-for-windows-10-and-later----1879077---"></a>Windows 10 ve üzeri için yeni Wi-Fi cihaz yapılandırma profili <!-- 1879077 -->
Şu anda XML dosyalarını kullanarak Wi-Fi profillerini içeri ve dışarı aktarabilirsiniz. Bu güncelleştirmeyle, tıpkı bazı diğer platformlarda olduğu gibi Intune’da doğrudan Wi-Fi cihaz yapılandırma profili oluşturabilirsiniz.

Profili oluşturmak için **Cihaz Yapılandırması** > **Profiller** > **Profil Oluştur** > **Windows 10 ve üzeri** > **Wi-Fi** seçeneklerini açın. 

Windows 10 ve üzeri için geçerlidir.

#### <a name="kiosk---obsolete-is-grayed-out-and-cant-be-changed----2149998-eeready---"></a>Bilgi noktası - eski seçenek gri renkte ve değiştirilemez <!-- 2149998 eeready -->
[Bilgi noktası özelliği](device-restrictions-windows-10.md#kiosk-preview---obsolete) (**Cihaz Yapılandırması** > **Profiller** > **Profil oluştur** > **Windows 10 ve üzeri** > **Cihaz kısıtlamaları**) artık kullanılmıyor ve [Windows 10 ve üzeri için bilgi noktası ayarları](kiosk-settings.md) ile değiştirildi. Bu güncelleştirmeyle **Bilgi Noktası - Eski** özelliği gri gösterilir ve kullanıcı arabirimi değiştirilemez veya güncelleştirilemez. 

Bilgi noktası modunu etkinleştirmek için bkz. [Windows 10 ve üzeri için bilgi noktası ayarları](kiosk-settings.md).

Windows 10 ve üzeri, Windows Holographic for Business için geçerlidir

#### <a name="apis-to-use-3rd-party-certification-authorities----2184013---"></a>3. taraf sertifika yetkilileri kullanacak API’ler <!-- 2184013 -->
Bu güncelleştirmede, üçüncü taraf sertifika yetkililerinin Intune ve SCEP ile tümleştirilmesini etkinleştirecek bir Java API’si yer alır. Ardından kullanıcılar, SCEP sertifikasını bir profil ekleyebilir ve MDM kullanarak cihazlara uygulayabilir.

Intune şu anda [Active Directory Sertifika Hizmetleri kullanarak SCEP isteklerini](certificates-scep-configure.md) destekler.

#### <a name="toggle-to-show-or-not-show-the-end-session-button-on-a-kiosk-browser----2455253---"></a>Bir Bilgi Noktası tarayıcısında Oturumu Sonlandır düğmesini gösterme veya gizleme geçişi <!-- 2455253 -->
Artık Bilgi Noktası tarayıcılarını Oturumu Sonlandır düğmesini gösterecek veya gizleyecek şekilde yapılandırabilirsiniz. Denetim seçeneğini **Cihaz yapılandırması** > **Bilgi noktası (önizleme)** > **Bilgi Noktası Web Tarayıcısı**’ndan görebilirsiniz. Açılırsa kullanıcı bir düğmeye tıkladığında uygulama, oturumu sonlandırma için onay ister. Onaylandığında tarayıcı, tüm göz atma verilerini temizler ve varsayılan URL’ye geri gider.

#### <a name="create-an-esim-cellular-configuration-profile----2564077---"></a>eSIM hücresel yapılandırma profili oluşturma <!-- 2564077 -->
**Cihaz yapılandırmasında** bir eSIM hücresel profili oluşturabilirsiniz. Cep telefonu operatörünüz tarafından sağlanan hücresel etkinleştirme kodlarını içeren bir dosyayı içeri aktarabilirsiniz. Ardından bu profilleri, Surface Pro LTE ve diğer eSIM özellikli cihazlar gibi eSIM LTE etkinleştirilmiş Windows 10 cihazlara dağıtabilirsiniz.

[Cihazınızın eSIM profillerini destekleyip desteklemediğini](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data) görmek için kontrol edin.

Windows 10 ve üzeri için geçerlidir. 




### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="automatically-mark-android-devices-enrolled-by-using-samsung-knox-mobile-enrollment-as-corporate----2404851---"></a>Samsung Knox Mobil Kayıt kullanarak “şirket” olarak kaydedilen Android cihazlarını otomatik olarak işaretleyin. <!-- 2404851 -->
Varsayılan olarak Samsung Knox Mobil Kayıt kullanarak kaydedilen Android cihazları, **Cihaz Sahipliği** altında **şirket** olarak işaretlenir. Şirket cihazlarını Knox Mobil Kayıt kullanarak kaydetmeden önce IMEI veya seri numaraları kullanarak el ile belirlemeniz gerekmez.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="bulk-delete-devices-on-devices-blade----1793693---"></a>Cihazlar dikey penceresinde cihazları toplu silme <!-- 1793693 -->

Şimdi Cihazlar dikey penceresinde tek seferde birden fazla cihazı silebilirsiniz. **Cihazlar** > **Tüm cihazlar** > silmek istediğiniz cihazları seçin > **Sil**'i seçin. Silinemeyen cihazlar için bir uyarı görüntülenir.

## <a name="week-of-july-16-2018"></a>16 Temmuz 2018 haftası  

### <a name="more-opportunities-to-sync-in-the-company-portal-app-for-windows"></a>Windows için Şirket Portalı uygulamasında daha fazla eşitleme fırsatı  
Windows için Şirket Portalı uygulaması artık eşitlemeyi doğrudan Windows görev çubuğu ve Başlat menüsünden başlatmanıza olanak tanır. Göreviniz yalnızca cihazları eşitlemek veya şirket kaynaklarına erişim sağlamak olduğunda, bu özellik çok kullanışlıdır. Yeni özelliğe erişmek için görev çubuğunuza veya Başlat menünüze sabitlenmiş Şirket portalı simgesine sağ tıklayın. Menü seçeneklerinde (atlama listesi olarak da bilinir) **Bu cihazı eşitle**’yi seçin. Şirket Portalı, **Ayarlar** sayfasında açılır ve eşitlemenizi başlatır. Yeni işlevselliğe göz atmak için bkz. [Kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md).   

### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows"></a>Windows için Şirket Portalı uygulamasında yeni göz atma deneyimleri  

Artık Windows için Şirket Portalı uygulamasında uygulamalara göz atarken veya uygulama ararken mevcut **Kutucuklar** görünümü ile yeni eklenen **Ayrıntılar** görünümü arasında geçiş yapabilirsiniz. Yeni görünümde ad, yayımcı, yayım tarihi ve yükleme durumu gibi uygulama ayrıntıları listelenir.  

**Uygulamalar** sayfasının **Yüklemeler** görünümü, tamamlanmış ve devam eden uygulama yüklemeleri hakkındaki ayrıntıları görmenizi sağlar. Yeni görünümün neye benzediğine göz atmak için bkz. [Kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md).  
### <a name="improved-company-portal-app-experience-for-device-enrollment-managers"></a>Cihaz kayıt yöneticileri için geliştirilmiş Şirket Portalı uygulaması deneyimi  
Bir cihaz kayıt yöneticisi (DEM) Windows için Şirket Portalı uygulamasında oturum açtığında, uygulama artık yalnızca yöneticinin geçerli, çalışan cihazını listeleyecek. Bu yenilik, uygulama DEM tarafından kaydedilen tüm cihazları göstermeye çalıştığında yaşanan zaman aşımı sorunlarını azaltacak.  


## <a name="week-of-july-9-2018"></a>9 Temmuz 2018 haftası

### <a name="app-management"></a>Uygulama yönetimi

### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>Onaylanmamış cihaz satıcıları ve modellerine göre uygulama erişimini engelleme <!-- 1425689 ! -->
Intune BT yöneticisi, belirlenen Android üreticileri ve/veya iOS modelleri listesini Intune Uygulama Koruması İlkeleri yoluyla zorlayabilir. BT yöneticisi, Android ilkeleri için noktalı virgülle ayrılmış bir üretici listesi ve aynı şekilde iOS ilkeleri için bir cihaz modelleri listesi sağlayabilecek. Intune Uygulama Koruması İlkeleri, yalnızca Android ve iOS için geçerlidir. Bu belirtilen listede gerçekleştirilebilen iki ayrı eylem vardır:
- Belirtilmemiş cihazlarda uygulama erişimini engelleme.
- Veya belirtilmemiş cihazlarda şirket verilerini seçmeli olarak silme. 

İlke gereksinimleri karşılanmazsa kullanıcı, hedeflenen uygulamaya erişemeyecek. Ayarlara bağlı olarak kullanıcı engellenebilir veya uygulama dahilinde kullanıcının şirket verileri seçmeli olarak silinir. iOS cihazlarında, bu özelliğin hedeflenen uygulamalarda zorlanması için Intune APP SDK'nin tümleştirilmesi amacıyla uygulamaların (WXP, Outlook, Managed Browser, Yammer gibi) katılımı gerekir. Bu tümleştirme, sıralı bir şekilde gerçekleşir ve belirli uygulama ekiplerine bağımlıdır. Android’de bu özellik, Şirket Portalı’nın en son sürümünü gerektirir. 

Son kullanıcı cihazlarında Intune istemcisi, Intune’un Uygulama Koruma İlkeleri dikey penceresinde belirtilen dizelerin basit eşleştirmesine dayalı olarak eylem gerçekleştirir. Bu, tamamen cihazın rapor ettiği değere bağlıdır. Bu nedenle BT yöneticisinin amaçlanan davranışın doğru olduğundan emin olması önerilir. Bu ayar, küçük bir kullanıcı grubuna hedeflenen çeşitli cihaz üreticileri ve modellerinde sınanarak doğruluğundan emin olunabilir. Microsoft Intune’da uygulama koruma ilkelerini görüntülemek ve ilke eklemek için **İstemci uygulamaları** > **Uygulama koruma ilkeleri**’ni seçin. Uygulama koruma ilkeleri hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkeleri nedir?](app-protection-policy.md) ve [Intune’da uygulama koruma ilkesi erişim eylemlerini kullanarak verileri seçmeli olarak silme](app-protection-policies-access-actions.md).

### <a name="access-to-macos-company-portal-pre-release-build----1734766---"></a>macOS Şirket Portalı yayın öncesi derlemesine erişim <!-- 1734766 -->
Insider programına katılarak, Microsoft AutoUpdate'i kullanıp derlemeleri erken almak için kaydolabilirsiniz. Kaydolmanız, güncelleştirilmiş Şirket Portalı'nı son kullanıcılarınıza sağlanmadan önce kullanmanıza olanak tanıyacaktır. Daha fazla bilgi için, [Microsoft Intune bloguna](https://blogs.technet.microsoft.com/intunesupport/2018/07/13/use-microsoft-autoupdate-for-early-access-to-the-macos-company-portal-app/) bakın.

## <a name="week-of-july-2-2018"></a>2 Temmuz 2018 Haftası

### <a name="app-management"></a>Uygulama yönetimi

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
- **Casus yazılımdan koruma**: **Gerektir** olarak ayarlandığında, Windows Güvenlik Merkezi’ne kaydedilmiş Symantec ve Windows Defender gibi casus yazılımdan koruma çözümlerini kullanarak uyumluluğu denetleyebilirsiniz. 

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

#### <a name="corporate-owned-single-use-support-for-android-devices----1630973---"></a>Android cihazlar için şirkete ait, tek kullanım desteği <!-- 1630973 -->

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
Microsoft Intune, macOS LOB uygulamalarını Azure portalından yükleme olanağı sağlayacak. GitHub’da bulunan araç tarafından ön işlemden geçtikten sonra macOS LOB uygulamasını Intune’a ekleyebileceksiniz. Azure portalının **Intune** dikey penceresinden **İstemci uygulamaları**’nı seçin. **İstemci uygulamaları** dikey penceresinde **Uygulamalar** > **Ekle**’yi seçin. **Uygulama Ekle** dikey penceresinde, **İş kolu uygulaması**’nı seçin. 

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
Bir cihazda kişisel profil kullanan son kullanıcılar, işle ilgili bir kişiden gelen aramalarda arayan kimliğini göremeyebilir. 

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
  - **Doğrudan Bellek Erişimi (DMA) ile Güvenli Önyükleme**: VBS'yi Güvenli Önyükleme ve doğrudan bellek erişimi ile açar. DMA koruması, donanım desteği gerektirir ve yalnızca düzgün yapılandırılmış cihazlarda etkinleştirilir. 

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
Şirket içi Exchange verilerine erişimi Outlook Mobile ile korumak için artık Intune Uygulama İlke Koruması (APP) ve Koşullu Erişim (CA) kullanabilirsiniz. Azure portalına bir uygulama koruma ilkesi eklemek veya ilkeyi değiştirmek için **Microsoft Intune** > **İstemci uygulamaları** > **Uygulama koruma ilkeleri**’ni seçin. Bu özelliği kullanmadan önce [iOS ve Android için Outlook gereksinimlerini](https://technet.microsoft.com/en-us/library/mt846639(v=exchg.160).aspx) karşıladığınızdan emin olun.

## <a name="notices"></a>Bildirimler

### <a name="plan-for-change-intune-will-move-to-support-macos-1012-and-higher-in-december---2970975--"></a>Değişiklik Planı: Intune, Aralık'ta macOS 10.12 ve üstünü desteklemeye geçecektir <!--2970975--> 

Apple macOS 10.14'ü çok yakın bir geçmişte piyasaya sürmüştür. Bunu nedenle Intune Aralık 2018'de macOS 10.12 ve üstünü desteklemeye geçecektir. 

### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?

Aralık ayından başlayarak macOS 10.11 ve öncesi cihazlardaki son kullanıcıların Intune'a kaydolmak için Şirket Portalını kullanması mümkün olmayacaktır. Bu kullanıcıların destek ve yeni özellikler almaya devam etmek için cihazlarını macOS 10.12 veya üzerine ve Şirket Portalı uygulamasını en son sürüme yükseltmesi gerekecektir. 

macOS 10.12 ve üzeri sürümler şu anda aşağıdakilerde desteklenmektedir: 
- MacBook (2009 sonu veya daha yenisi). 
- iMac (2009 sonu veya daha yenisi)
- MacBook Air (2010 sonu veya daha yenisi).  
- MacBook Pro (2010 sonu veya daha yenisi). 
- Mac Mini (2010 sonu veya daha yenisi). 
- Mac Pro (2010 sonu veya daha yenisi). 

Aralık ayından sonra yukarıda listelenenler dışında cihazları olan son kullanıcılar macOS için Şirket Portalı uygulamasının en son sürümüne erişemeyecektir. MacOS 10.12 öncesi desteklenmeyen sürümleri çalıştıran mevcut kayıtlı cihazlar yönetilmeye ve Intune Yönetim Konsolu'nda listelenmeye devam edecektir.

### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?

Son kullanıcılarınızdan Aralık 2018'den önce cihazlarını desteklenen bir işletim sistemi sürümüne yükseltmelerini isteyin. 
- Etkilenmiş olabilecek cihazları veya kullanıcıları görmek için Azure konsolunda Intune'daki Intune raporlamanıza bakın. Cihazlar > Tüm cihazlar'a gidin ve işletim sistemine göre filtre uygulayın. Kuruluşunuzda hangi cihazların macOS 10.11 çalıştırdığını belirlemenize yardımcı olması için ek sütunlar ekleyebilirsiniz. 
- Hibrit bir mobil cihaz yönetimi (MDM) kullanıyorsanız, Configuration Manager konsolunda Varlık ve Uyumluluk > Cihazlar'a gidin, İşletim Sistemi ve İstemci Sürümü sütunlarını eklemek için sütunlara sağ tıklayın ve işletim sistemine göre listeyi sıralayın. Hibrit MDM'nin artık kullanımdan kaldırıldığını ve olabildiğince kısa bir süre içinde Azure'da Intune'a geçmeniz gerektiğini hatırlatalım. 
 
Ek Bilgiler [https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos-cp](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos-cp)
 

### <a name="plan-for-change-new-intune-support-experience-for-premier-customers"></a>Değişiklik Planı: Premier müşteriler için yeni Intune destek deneyimi 
Bir Microsoft Premier müşterisi olarak şu anda Microsoft Premier Online (MPO) portalını (premier.microsoft.com) ve Azure’da Intune’u (portal.azure.com) kullanarak Intune için destek istekleri oluşturabilirsiniz. 3 Aralık 2018 itibarıyla Premier destek deneyimini geliştirmeye devam etmek adına yalnızca Azure’da Intune ile destek istekleri oluşturabileceksiniz.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
3 Aralık’tan sonra MPO’da destek istekleri oluşturamayacaksınız.  Bunu yapmaya çalıştığınızda, kapatamayacağınız bir istem alacak ve Azure’da Intune’a yönlendirileceksiniz. Burada, sorununuzu vaktinde tanılamak ve çözümlemek için Intune’a ayrılmış Microsoft Desteği’ne yönlendirilecek bir destek isteği oluşturabilirsiniz. MPO’da oluşturulan destek istekleri Azure portalında görüntülenemez, bu nedenle MPO’da destek isteği oluşturmayı bırakmanız gerekir.  

Hibrit mobil cihaz yönetimi (hibrit MDM) veya ortak yönetim kullanıyorsanız ConfigMgr için destek istekleri oluşturmak amacıyla MPO kullanmaya devam edebilirsiniz ancak Intune için destek istekleri oluşturmak amacıyla yalnızca Azure portalını kullanın. Hatırlatmış olalım, hibrit MDM kullanımdan kaldırıldığı için en yakın zamanda Azure’da Intune’a geçmeyi planlamalısınız. Daha fazla bilgi için Hibrit Mobil Cihaz Yönetiminden Azure’da Intune’a geçme konusuna bakın.

Yalnızca Genel Yönetici, Intune Hizmet Yöneticisi ve Hizmet Destek Yöneticisi rollerine sahip kullanıcıların Azure portalında destek biletleri oluşturabileceğini unutmayın.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapabilirim?
- MPO’yu kullanmayı bırakın ve tüm Intune destek isteklerinizi Azure’da Intune kullanarak oluşturun ve yönetin.  
- Gerekirse yardım masanızı uyarın ve belgeleri güncelleştirin.
- MPO’da destek istekleri oluşturmakta olan Genel Yönetici veya Intune Hizmet Yöneticisi rollerine sahip kullanıcılarınız varsa onları Azure Active Directory’de Hizmet Destek Yöneticisi rolüne atayın, böylece Azure portalında destek biletleri oluşturmaya devam edebilirler.
- Daha fazla bilgi ve yardımcı bağlantılar için Ek Bilgiler’e tıklayın.

#### <a name="additional-information"></a>Ek Bilgi
[https://aka.ms/IntuneSupport_MPO_to_Azure](https://aka.ms/IntuneSupport_MPO_to_Azure)

### <a name="take-action-please-update-your-android-device-restriction-or-compliance-policy-password-settings-in-intune"></a>Eylem gerekiyor: Lütfen Intune'da Android cihazınızın kısıtlama veya uyumluluk ilkesi parolasını güncelleştirin
Intune, Android 4.4 ve üstü cihazlarında sağlanan "cihaz varsayılanı" parola türünü kaldıracak. Android platformlarıyla cihaz varsayılanları arasındaki farklardan dolayı, bu ilke cihaz tarafından genellikle isteğe bağlı olarak kabul edilir. Bu ayarın Android'de ne zaman zorunlu tutulacağı konusundaki karışıklığı gidermek için, önümüzdeki sürümlerden birinde kullanıcı arabiriminden bu ayarı kaldıracağız. 
#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
- Cihazlarda parolanın gerekli olmasını amaçlıyorsanız, "cihaz varsayılanı" kullanmak yerine Android platformu profillerinizi düzenleyip gerekli parola türünü açıkça ifade etmenizi öneririz.
- Amacınız parola oluşturup oluşturmama kararını son kullanıcıya bırakmaksa, “Yapılandırılmadı” düğmesini seçin. Bu ayarı kullanıcı arabiriminden kaldırdığınızda, ayar hala ayarlanmış durumdaysa, profili bir sonraki düzenleyişinizde "Cihaz varsayılanı" dışında bir değer seçmeniz istenir.
Bu değişikliğe hazırlanmak için ne yapmam gerek?
Android'inizde ve Android kurumsal cihaz kısıtlaması ve uyumluluk ilkelerinde parola ayarlarını gözden geçirin. Bunlar, Uyumluluk ilkeleri için Sistem güvenliğinin altında ve Cihaz kısıtlamaları için Cihaz parolası veya İş profili ayarları altında listelenir. Ek bilgilerde, diğer ayrıntıların bağlantısı ve bu ayarların yapılandırıldığı ekranların görüntüleri vardır.
#### <a name="additional-information"></a>Ek bilgiler
https://aka.ms/PasswordSettings 

### <a name="plan-for-change-change-password-at-next-auth-added-to-intune---1873216---"></a>Değişiklik Planı: Sonraki Kimlik Doğrulamasında Parolayı Değiştir, Intune’a eklendi<!-- 1873216 -->
Eylül hizmet sürümünde Intune, macOS sürüm 10.13 ve üzerini çalıştıran cihazlar için Apple’ın yeni çıkan **Sonraki Kimlik Doğrulamasında Parolayı Değiştir** ayarını tümleştirmeyi planlıyor. Bu ayar olmadan MDM sağlayıcıları cihazın geçiş kodunun uyumlu olacak şekilde değiştirildiğini doğrulayamıyorlar. Intune’un yapılandırma ve uyumluluk ilkeleri, yalnızca cihazın parolası bir sonraki sefer değiştiğinde uyumlu olarak işaretleneceğini doğrular. Bu yeni Apple özelliği eklendiğinde, macOS kullanıcılarınız uyumlu olsa bile parolalarını güncelleştirmek için bir istek alır.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Bu, Intune veya karma MDM kullanan ve macOS cihaz ilkesine sahip ortamları etkileyecek. Artık Apple’ın **Sonraki Kimlik Doğrulamasında Parolayı Değiştir** ayarı olduğu için Intune, bir parola ilkesi gönderildiğinde kullanıcıları parolalarını değiştirmeye zorlayabilir. Cihaz uyumlu olarak işaretlenene kadar şirket kaynaklarını engellerseniz, son kullanıcılarınız parolalarını sıfırlayana kadar e-posta veya SharePoint siteleri gibi şirket kaynaklarına erişemeyebilirler. Gelecekte, tüm yapılandırma ve uyumluluk parola ilkeleri hedeflenen kullanıcıları parolalarını değiştirmeye zorlayacak.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Durumu yardım masanıza bildirin. Bu macOS cihaz ilkesini kullanmak istemiyorsanız, geçerli macOS ilkenizin atamasını kaldırmanızı veya bu ilkeyi silmenizi öneririz. Müşteri araştırmalarına göre çoğu müşteri bu değişiklikten etkilenmeyecek. Pek çok son kullanıcı, uyumlu kalmak için parolayla kaydolmaya veya parolalarını sıfırlamaya yönelik istek aldıktan sonra parolasını güncelleştiriyor.

### <a name="plan-for-change-intune-moving-to-tls-12"></a>Değişiklik Planı: Intune’u TLS 1.2’ye taşıma
31 Ekim 2018 tarihinden itibaren Intune; sınıfının en iyisi şifrelemeyi sağlamak, hizmetin varsayılan olarak daha güvenli olduğundan emin olmak ve Microsoft Office 365 gibi diğer Microsoft hizmetleriyle uyum sağlamak için Aktarım Katmanı Güvenliği (TLS) protokol sürümü 1.2’yi destekleyecektir. Office, bu değişikliği MC128929 sürümünde gerçekleştirmişti.

Şirket Portalı ayrıca 31 Ekim 2018'de TLS 1.2 desteği vermeye de başlayacaktır.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
31 Ekim 2018 tarihinden itibaren Intune artık TLS protokol sürümü 1.0 veya 1.1’i desteklemeyecektir. Intune’a sorunsuz bir şekilde bağlanmak için tüm istemci-sunucu ve tarayıcı-sunucu birleşimlerinin TLS 1.2 sürümünü kullanması gerekir. Bu değişikliğin, artık Intune tarafından desteklenmeyen ancak Intune yoluyla ilke almaya devam eden ve TLS sürüm 1.2’yi kullanamayacak olan son kullanıcı cihazlarını etkileyeceğine dikkat edin. Android 4.3 ve öncesi çalıştıran cihazlar gibi cihazlar buna dahildir. Etkilenen cihazlar ve tarayıcılar listesi için aşağıdaki Ek Bilgiler kısmına bakın.

31 Ekim 2018’den itibaren, eski bir TLS sürümünün kullanımıyla ilgili bir sorun yaşarsanız, çözümün bir parçası olarak sizden TLS 1.2’ye güncelleştirmeniz veya TLS 1.2 destekleyen bir cihaza geçmeniz istenecektir.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Ortamlarınızdaki TLS 1.0 ve 1.1 bağımlılıklarını önceden kaldırmanızı ve mümkün olan her yerde işletim sistemi düzeyinde TLS 1.0 ve 1.1’i devre dışı bırakmanızı öneririz. TLS 1.2’ye geçişinizi planlamaya hemen başlayın. Şu anda Intune tarafından desteklenmeyen ancak yine de ilke alma ihtimali olan ve TLS sürüm 1.2 ile iletişim kuramayacak olan cihazlar listesi için aşağıdaki web günlüğü gönderisine bakın. Bu son kullanıcıları, şirket kaynaklarına erişimi kaybedecekleri konusunda bilgilendirmeniz gerekebilir.

**Ek Bilgi**: [Şifreleme için Intune’un TLS 1.2’ye taşınması](https://blogs.technet.microsoft.com/intunesupport/2018/06/05/intune-moving-to-tls-1-2-for-encryption/)


### <a name="plan-for-change-use-intune-on-azure-now-for-your-mdm-management----1227338---"></a>Değişiklik Planı: Artık MDM yönetiminiz için Azure’da Intune kullanabilirsiniz <!-- 1227338 -->
Bir yılı aşkın bir süre önce [Azure’da Intune’un genel önizlemesini](https://cloudblogs.microsoft.com/enterprisemobility/2016/12/07/public-preview-of-intune-on-azure/) duyurup altı ay önce Intune için [yeni yönetici deneyiminin genel kullanılabilirliğini](https://cloudblogs.microsoft.com/enterprisemobility/2017/06/08/the-new-intune-and-conditional-access-admin-consoles-are-ga/) yayımlamıştık. 31 Ağustos 2018 itibarıyla, tek başına Intune kullanan müşteriler için klasik Silverlight konsolunda mobil cihaz yönetimini (MDM) kaldıracağız. Bunun yerine MDM ihtiyaçlarınız için [Azure’da Intune](https://aka.ms/Intune_on_Azure) kullanabilirsiniz. MDM için hala klasik konsolu kullanıyorsanız, lütfen bundan vazgeçin ve Azure üzerinden Intune kullanmaya alışın. Bu değişiklik ile hiçbir son kullanıcı etkisi beklemiyoruz. Klasik bilgisayar yönetimi Silverlight’ta kalacaktır. [Buraya](https://aka.ms/Intune_on_Azure_mdm) tıklayarak bu değişikliğin sizi nasıl etkileyeceği hakkında daha fazla bilgi alabilirsiniz.

## <a name="whats-coming"></a>Yakında

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple, Uygulama Taşıma Güvenliği için güncelleştirmeler gerektirecek <!--748318-->
Apple, Uygulama Taşıma Güvenliği (ATS) için belirli gereksinimler uygulayacağını açıkladı. ATS, HTTPS üzerinden yapılan tüm uygulama iletişimlerinde daha sıkı güvenlik uygulamak için kullanılır. Bu değişiklik, iOS Şirket Portalı uygulamaları kullanan Intune müşterilerini etkiler. [Intune destek web günlüğümüzü](https://aka.ms/compportalats) ayrıntılarla güncelleyeceğiz.



## <a name="see-also"></a>Ayrıca bkz:
* [Microsoft Intune Blogu](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform yol haritası](https://www.microsoft.com/cloud-platform/roadmap)
* [Şirket Portalı kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md)
* [Önceki aylardaki yenilikler](whats-new-archive.md)
