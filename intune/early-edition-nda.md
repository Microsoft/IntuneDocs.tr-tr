---
title: Erken sürüm
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2f9849b2c327397c0b8945ee42d9fca7f9f46250
ms.sourcegitcommit: 58cddb08b64bd60f041eff46ff215e83e13db4e6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40001919"
---
# <a name="the-early-edition-for-microsoft-intune---august-2018"></a>Microsoft Intune için erken sürüm - Ağustos 2018

> [!Note]
> NDA bildirimi: Aşağıdaki değişiklikler, Intune için geliştirilme aşamasındadır. Bu bilgiler NDA kapsamında çok kısıtlı bir kapsamla paylaşılır. Bu bilgilerin hiçbirini sosyal medyada veya Twitter, UserVoice, Reddit vb. gibi kamuya açık web sitelerinde paylaşmayın. 

**Erken sürüm**, NDA altında paylaşılan Microsoft Intune'un gelecek sürümlerinde kullanıma sunulacak yeni özelliklerin bir listesini sunar. Bu bilgiler kısıtlı bir kapsamla verilmektedir ve değiştirilebilir. Bu bilgileri Twitter veya UserVoice’da ya da şirketiniz dışında paylaşmayın. Burada listelenen özelliklerden bazılarının son tarihe yetişememe riski vardır ve gelecek sürüme ertelenebilir. Diğer özellikler, müşterinin kullanımına hazır olduğundan emin olmak için pilot (sürüyor) aşamasında test edilmektedir. Herhangi bir sorunuz veya endişeniz varsa lütfen Microsoft ürün grubu ilgili kişisiyle bağlantı kurun.

Bu sayfa düzenli aralıklarla güncelleştirilir. Ek güncelleştirmeleri daha sonra denetleyin.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Azure portalında Intune

<!-- 1808 start -->

### <a name="windows-hello-will-target-users-and-devices----1106609---"></a>Windows Hello, kullanıcıları ve cihazları hedefleyecek <!-- 1106609 -->
Bir [İş İçin Windows Hello](windows-hello.md) ilkesi oluşturduğunuzda bu ilke, kuruluştaki tüm kullanıcılara (kiracı genelinde) uygulanır. Bu güncelleştirmeyle ilke, bir cihaz yapılandırma ilkesi kullanılarak belirli kullanıcılara veya belirli cihazlara da (**Cihaz Yapılandırması** > **Profiller** > **Profil oluştur** > **Kimlik Koruma** > **İş İçin Windows Hello**) uygulanabilecek.

Azure portalında Intune’da Windows Hello yapılandırması ve ayarları hem **Cihaz kaydı** hem de **Cihaz yapılandırması** bölümlerinde bulunacak. **Cihaz kaydı**, kuruluşun tamamını (kiracı genelinde) hedefler ve Windows AutoPilot (OOBE) destekler. **Cihaz yapılandırması**, iade sırasında uygulanan bir ilkeyi kullanarak cihazları ve kullanıcıları hedefler.

Şunun için geçerlidir:  
- Windows 10 ve üzeri
- Windows 10 Holographic for Business

### <a name="control-s-mode-on-windows-10-and-later-devices---public-preview----1958649---"></a>Windows 10 ve üzeri cihazlarda S modunu denetleme - genel önizleme <!-- 1958649 -->
Bir Windows 10 cihazı S modundan çıkaran veya kullanıcıların cihazı S modundan çıkarmasını önleyen bir cihaz yapılandırma profili oluşturabileceksiniz. Bu özellik Intune’da **Cihaz yapılandırması** > **Profiller** >  **Windows 10 ve üzeri** > **Sürüm yükseltme ve mod değiştirme** altında bulunacak.
[S modunda Windows 10’a giriş](https://www.microsoft.com/windows/s-mode) makalesi, S modu hakkında daha fazla bilgi sağlar.
Şunun için geçerlidir: Windows 10 ve üzeri (1809 ve üzeri)

### <a name="modern-vpn-support-updates-for-ios----2459928-1819876-and-2650856---"></a>iOS için modern VPN destek güncelleştirmeleri <!-- 2459928, 1819876, and 2650856 -->
Gelecekte yapılacak bir güncelleştirme, aşağıdaki iOS VPN istemcilerini destekleyecek: 
- F5 Erişimi (sürüm 3.0.1 ve üzeri)
- Citrix SSO
- Palo Alto Networks GlobalProtect (sürüm 5.0 ve üzeri) Ayrıca gelecek bir güncelleştirmede:
- Mevcut **F5 Erişimi** bağlantı türleri, F5 marka güncelleştirmeleri üzerine **F5 Erişimi Eski** olarak yeniden adlandırılacak.
- Mevcut **Palo Alto Networks GlobalProtect** bağlantı türleri, Palo Alto marka güncelleştirmeleri üzerine **Eski Palo Alto Networks GlobalProtect** olarak yeniden adlandırılacak. 

Bu bağlantı türlerine sahip mevcut profiller, eski VPN istemcisiyle çalışmaya devam edecek. iOS ile Cisco Eski AnyConnect, F5 Access Eski, Citrix VPN veya Eski Palo Alto Networks GlobalProtect kullanıyorsanız yeni uygulamalara geçmelisiniz. iOS 12 sonrası iOS cihazlarda VPN erişiminin kullanılabilir olmasını sağlamak için bunu en kısa zamanda yapmalısınız.

### <a name="lock-the-company-portal-in-single-app-mode-until-user-sign-in---1067692---"></a>Kullanıcı oturum açana kadar Şirket Portalı’nı tek uygulama modunda kilitleme <!--1067692 --> 
DEP kaydı sırasında bir kullanıcının kimliğini Kurulum Yardımcısı yerine Şirket Portalı ile doğrularsanız, Şirket Portalı’nı Tek Uygulama modunda çalıştırma seçeneğiniz olacak. Bu seçenek, Kurulum Yardımcısı tamamlandıktan hemen sonra cihazı kilitler; böylece kullanıcının cihaza erişmek için oturum açması gerekir. Bu işlem, cihazın eklenmesinin tamamlanmasını ve kullanıcısı olmadan yalnız bırakılmış duruma gelmemesini sağlar.

### <a name="scope-tags-for-policies---1081974-eeready--"></a>İlkeler için kapsam etiketleri <!--1081974 eeready-->

Intune kaynaklarına erişimi sınırlamak için kapsam etiketleri oluşturabileceksiniz. Bir rol atamasına kapsam etiketi ekleyin ve daha sonra kapsam etiketini bir yapılandırma profiline ekleyin. Rolün yalnızca eşleşen kapsam etiketlerine sahip yapılandırma profillerine erişimi olacaktır.
Bir kapsam etiketi oluşturmak için **Intune rolleri** > **Kapsam (Etiketler)** > **Oluştur**’u seçin.
Kapsam etiketini bir rol atamasına eklemek için **Intune rolleri** > **Tüm roller** > **İlke ve Profil Yöneticisi** > **Atamalar** > **Kapsam (Etiketler)**’i seçin.
Kapsam etiketini bir yapılandırma profiline eklemek için **Cihaz yapılandırması** > **Profiller** > bir profil seçin > **Özellikler** > **Kapsam (Etiketler)**’i seçin.

### <a name="assign-a-user-and-friendly-name-to-an-autopilot-device---1346521---"></a>Autopilot cihazına kullanıcı ve kolay ad atama <!--1346521 -->
Gelecekteki bir genel önizleme ile yöneticiler, tek bir AutoPilot cihazına bir kullanıcı atayabilecekler.  Yöneticiler ayrıca cihazlarını AutoPilot ile ayarlayan kullanıcıları karşılaması için kolay adlar verebilecekler.

Şunun için geçerlidir: Windows Insider 1809 veya sonraki derlemeler (önizlemedeyken).

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Başka bir MDM tarafından kullanılan Apple VPP belirteci <!-- 1488946 -->
Bir Apple toplu satın alınan program (VPP) belirteci hem Intune hem de başka bir MDM tarafından kullanıldığında Intune bunu algılayacak ve ayrıntıları gösterecek.

### <a name="packet-tunnel-support-for-ios-per-app-vpn-profiles-for-custom-and-pulse-secure-connection-types----1520957---"></a>Özel ve Pulse Secure bağlantı türleri için iOS uygulama başına VPN profilleri için paket tüneli desteği <!-- 1520957 -->
iOS uygulama başına VPN profillerini kullanırken uygulama katman tüneli (uygulama-proxy) veya paket düzeyi tünel (paket-tünel) kullanabileceksiniz. Bu seçenekler, aşağıdaki bağlantı türleri ile kullanılabilecek:
- Özel VPN
- Pulse Secure Hangi değeri kullanmanız gerektiğini bilmiyorsanız VPN sağlayıcınızın belgelerine başvurun.
Şunun için geçerlidir: iOS

### <a name="zscaler-is-an-available-connection-for-vpn-profiles-on-ios----1769858-eeready---"></a>iOS’ta VPN profilleri için Zscaler bağlantısı kullanılabilir <!-- 1769858 eeready -->
Bir iOS VPN cihaz yapılandırma profili oluşturduğunuzda (**Cihaz yapılandırması** > **Profiller** > **Profil oluştur** > **iOS** platform > **VPN** profil türü) Cisco, Citrix vb. gibi birkaç bağlantı türü vardır. Gelecek bir güncelleştirme ile Zscaler da bir bağlantı türü olarak eklenecek. 
[iOS çalıştıran cihazlar için VPN ayarları](vpn-settings-ios.md), kullanılabilir bağlantı türlerini listeler.

### <a name="block-windows-personal-device-enrollments----1849498---"></a>Windows kişisel cihaz kayıtlarını engelleme <!-- 1849498 -->
Windows kişisel cihazların Intune [mobil cihaz yönetimine](windows-enroll.md) kaydolmasını engelleyebileceksiniz. Bu özellikle [Intune PC aracısı](manage-windows-pcs-with-microsoft-intune.md) ile kaydedilen cihazlar engellenemez.
Bu özelliği görmek için **Cihaz kaydı** > **Cihaz kısıtlamaları**’nı seçin.
Bu kısıtlamayı açtığınızda, kayıtlı olan cihazlar etkilenmez.
Kısıtlama açıldıktan sonra Intune, tüm yeni Windows kayıt isteklerinin şirket kaydı olarak yetkilendirildiğinden emin olmak için denetim yapar. Şirket kaydı olarak yetkilendirme için aşağıdaki yöntemler uygundur:
- Kaydeden kullanıcı [cihaz kayıt yöneticisi hesabı]( device-enrollment-manager-enroll.md) kullanıyor.
- Cihaz [Windows Autopilot](enrollment-autopilot.md) yoluyla kaydediliyor.
- Cihazın IMEI numarası **Cihaz kaydı** > **[Şirket cihaz tanımlayıcıları]( corporate-identifiers-add.md)**’nda listelenmiş.
- Cihaz bir [toplu sağlama paketi](windows-bulk-enroll.md) ile kaydediliyor.
- Cihaz [ortak yönetim için SCCM’den otomatik kayıt](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview#how-to-configure-co-management) yoluyla kaydediliyor.

Yetkilendirilmemiş kayıtlar engellenir. Aşağıdaki kayıtlar Intune tarafından şirket olarak işaretlenir ancak Intune yöneticisine cihaz başına denetim sağlamadığı için engellenir:
- [Windows kurulumu sırasında Azure Active Directory katılımı](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx.md) ile [otomatik MDM kaydı](windows-enroll.md#enable-windows-10-automatic-enrollment).
- [Windows kurulumundan Azure Active Directory katılımı](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx.md) ile [otomatik MDM kaydı](windows-enroll.md#enable-windows-10-automatic-enrollment).

Aşağıdaki kişisel kayıt yöntemleri de engellenir:
- [Windows Ayarları’ndan İş Hesabı Ekleme](https://docs.microsoft.com/azure/active-directory/user-help/device-management-azuread-registered-devices-windows10-setup) ile [otomatik MDM kaydı](windows-enroll.md#enable-windows-10-automatic-enrollment).
- Windows Ayarları’ndan [Yalnızca MDM kaydı]( https://docs.microsoft.com/windows/client-management/mdm/mdm-enrollment-of-windows-devices#connecting-personally-owned-devices-bring-your-own-device) seçeneği.

### <a name="specify-machine-name-patterns-in-an-autopilot-profile---1849855--"></a>Autopilot profilinde makine adı desenleri belirtme <!--1849855-->
Autopilot kaydı sırasında [bilgisayar adı](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) oluşturmak ve ayarlamak için bir bilgisayar adı belirtebileceksiniz. Bunu, **Cihaz kaydı** > **Windows kaydı** > **Windows AutoPilot Dağıtım hizmeti** > **Profiller**’de bulunan Autopilot profilinde belirtmeniz gerekecektir. Yalnızca alfasayısal karakterler ve kısa çizgi kullanılabilir.
Şunun için geçerlidir: Windows Insider 1809 veya sonraki derlemeler (önizlemedeyken).

### <a name="ios-version-number-and-build-number-are-shown----1892471---"></a>iOS sürüm numarası ve derleme numarası gösteriliyor <!-- 1892471 -->
**Cihaz uyumluluğu** > **Cihaz uyumluluğu**’nda iOS işletim sistemi sürümü gösterilir. Gelecek bir güncelleştirme ile derleme numarası da gösterilecek.
Güvenlik güncelleştirmeleri kullanıma sunulduğunda Apple genellikle sürüm numarasını olduğu gibi bırakır ancak derleme numarasını güncelleştirir. Derleme numarasına bakarak bir güvenlik açığı güncelleştirmesinin yüklenip yüklenmediğini kolayca denetleyebilirsiniz.

### <a name="for-windows-autopilot-profiles-hide-the-change-account-options-on-the-company-sign-in-page-and-domain-error-page---1901669---"></a>Windows Autopilot profilleri için şirket oturum açma sayfasında ve etki alanı hata sayfasında hesap değiştirme seçeneklerini gizleme <!--1901669 -->
Bir genel önizleme, yöneticilerin şirket oturum açma ve etki alanı hata sayfalarında hesap değiştirme seçeneklerini gizlemelerine imkan veren Windows Autopilot profil seçeneklerini barındıracak. Bu seçenekleri gizlemek, Azure Active Directory’de Şirket Markasının yapılandırılmasını gerektirir. Şunun için geçerlidir: Windows Insider 1809 veya sonraki derlemeler (önizlemedeyken).

### <a name="delay-when-ios-software-updates-are-shown-on-the-device----1949583---"></a>Cihazda iOS yazılım güncelleştirmelerinin gösterilmesini geciktirme <!-- 1949583 -->
Intune > **Yazılım Güncelleştirmeleri** > **iOS güncelleştirme ilkeleri**’nde cihazların güncelleştirme yüklemesini istemediğiniz gün ve saatleri yapılandırabilirsiniz. Gelecek bir güncelleştirme ile bir yazılım güncelleştirmesinin cihazda görüntülenmesini 1-90 gün kadar geciktirebileceksiniz. 
[Microsoft Intune’da iOS güncelleştirme ilkelerini yapılandırma](software-updates-ios.md) makalesi, geçerli ayarları listeler.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Cihaz uyumluluk panosunda kullanımdan kaldırılan cihazlar <!-- 1981119 -->
Gelecek bir güncelleştirme ile kullanımdan kaldırılan cihazlar uyumluluk panosundan da kaldırılacak. Bu durum, uyumluluk numaralarınızı değiştirecek.

### <a name="new-user-experience-update-for-the-company-portal-website---2000968---"></a>Şirket Portalı web sitesi için yeni kullanıcı deneyimi güncelleştirmesi <!--2000968 -->
Müşterilerden gelen geri bildirimler temelinde Şirket Portalı web sitesine yeni özellikler eklenecek. Android, iOS ve Windows cihazlarının mevcut işlevselliğinde ve kullanılabilirliğinde önemli geliştirmeler göreceksiniz. Sitenin cihaz ayrıntıları, geri bildirim ve destek, cihaza genel bakış gibi alanlarında yeni, modern, hızlı yanıt veren bir tasarım elde edeceksiniz. Şunları da göreceksiniz:
- Tüm cihaz platformları arasında rahat iş akışları
- Geliştirilmiş cihaz kimlik ve kayıt akışları
- Daha yararlı hata iletileri
- Daha rahat bir dil, daha az teknik jargon
- Doğrudan uygulama bağlantıları paylaşabilme seçeneği
- Büyük uygulama katalogları için iyileştirilmiş performans
- Tüm kullanıcılar için artırılmış erişilebilirlik

### <a name="office-365-proplus-version----2213968-eeready---"></a>Office 365 ProPlus sürümü <!-- 2213968 eeready -->
Intune kullanarak Office 365 ProPlus uygulamalarını Windows 10 cihazlara atarken Office sürümünü seçebileceksiniz. Azure portalında **Microsoft Intune** > **Uygulamalar** > **Uygulama ekle**’yi seçin. Daha sonra açılan **Tür** listesinden **Office 365 ProPlus Paketi (Windows 10)**’u seçin. İlişkili dikey pencereyi görüntülemek için **Uygulama Paketi Ayarları**’nı seçin. **Güncelleştirme Kanalı** için bir değer ayarlayın, örneğin **Aylık**. İsteğe bağlı olarak **Evet**’i seçin ve son kullanıcı cihazlarından diğer Office (msi) sürümünü kaldırın. Son kullanıcı cihazlarında seçili kanal için belirli bir Office sürümü yüklemek için **Belirli**’yi seçin. Bu noktada Office’in **Belirli bir sürüm**ünü seçip kullanabilirsiniz. Kullanılabilir sürümler zaman içerisinde değişir. Bu neden yeni bir dağıtım oluştururken kullanılabilir sürümler daha yeni olabilir ve bazı eski sürümleri bulamayabilirsiniz. Mevcut dağıtımlar eski sürümü dağıtmaya devam eder ancak her kanaldaki sürüm listesi sürekli olarak güncelleştirilir. Daha fazla bilgi için bkz. [Office 365 ProPlus güncelleştirme kanallarına genel bakış](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus).

### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470---"></a>Kurulum Yardımcısı sırasında bazı ekranları atlamak için profil yapılandırma <!-- 2276470 -->
Bir macOS kayıt profili oluşturduğunuzda, bir kullanıcının Kurulum Yardımcısı kullanırken aşağıdaki ekranlardan istediğini atlayabilmesi için bu profili yapılandırabileceksiniz:
- Android Geçişi
- Görüntü Tonu
- Gizlilik
- iCloudStorage

### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Şirket içi bağlayıcılar için güncelleştirme işleminde değişiklik <!-- 2277554 -->
Müşterilerden gelen geri bildirimlere dayalı olarak şirket içi bağlayıcılarda güncelleştirme işlemi değiştirilecek. Bir şirket içi bağlayıcıyı ilk yüklediğinizde güncelleştirmeler otomatik olarak gerçekleşecek. Bu değişiklik, yeni Microsoft Intune için PFX Sertifika Bağlayıcısı ile başlayacak ve ardından diğer şirket içi bağlayıcı türlerine de sağlanacak. 

### <a name="support-for-register-dns-setting-for-windows-10-vpn----2282852---"></a>Windows 10 VPN için DNS ayarı kaydetme desteği <!-- 2282852 -->
Windows 10 VPN profillerini, VPN arabirimine atanmış IP adreslerini özel profil kullanmaya ihtiyaç duymadan dinamik olarak dahili DNS’e kaydedecek şekilde yapılandırabileceksiniz.
[Windows 10 VPN ayarları](vpn-settings-windows-10.md) makalesi, kullanabileceğiniz geçerli VPN profil ayarlarını listeler. 

### <a name="restricts-apps-and-block-access-to-company-resources-on-ios-and-android-for-work-devices----2451462---"></a>iOS ve Android for Work cihazlarda uygulamaları kısıtlama ve şirket kaynaklarına erişimi engelleme <!-- 2451462 -->
**Cihaz uyumluluğu** > **İlkler** > **İlke oluştur** > **Android for Work** > **Sistem Güvenliği**’nde yeni **Kısıtlı uygulamalar** ayarı olacak. Bu yeni ayar, bazı uygulamalar cihaza yüklendiğinde cihazın şirket kaynaklarına erişimini engelleyecek bir uyumluluk ilkesi kullanır. Cihaz, kısıtlı uygulamalar kaldırılana kadar uyumsuz sayılır.
Şunun için geçerlidir: 
- iOS

### <a name="export-azure-classic-portal-compliance-policies-to-csv-file----2469637---"></a>Azure klasik portal uyumluluk ilkelerini .csv dosyası olarak dışarı aktarma <!-- 2469637 -->
Azure klasik portalında oluşturulan ilkeler artık kullanım dışı olacak.  Bu gerçekleştiğinde mevcut ilkeleri gözden geçirebilir ve silebilirsiniz; güncelleştiremezsiniz. İlkeleri virgülle ayrılan dosya (.csv dosyası) olarak dışarı aktarabilirsiniz. Daha sonra Intune Azure portalında bu ilkeleri yeniden oluşturmak için dosyadaki ayrıntıları kullanabilirsiniz.
> [!IMPORTANT]
> Azure klasik portalı kullanımdan kaldırıldığında ilkelerinize erişemeyecek ve hatta bunları göremeyeceksiniz. Bu sebeple Azure klasik portalı kullanımdan kaldırılmadan önce ilkelerinizi dışarı aktarıp Azure portalında yeniden oluşturduğunuzdan emin olun.

### <a name="change-terminology-to-retire-and-wipe----2175759---"></a>Terminolojiyi "kullanım dışı bırakma" ve "temizleme" olarak değiştirin <!-- 2175759 -->
Graph API ile tutarlılığı sağlamak için, Intune kullanıcı arabirimi ve belgelerine aşağıdaki terim değişiklikleri yansıtılacak:
- **Şirket verilerini kaldır** terimi, **kullanımdan kaldırma** olarak değiştirilecek
- **Fabrika sıfırlaması** terimi **temizleme** olarak değiştirilecek



<!-- 1807 start -->

### <a name="more-sync-opportunities-in-the-company-portal-app-for-windows----2683177---"></a>Windows için Şirket Portalı uygulamasında daha fazla eşitleme fırsatı <!-- 2683177 -->
Windows için Şirket Portalı uygulaması, Windows görev çubuğuna ve Başlat menüsü atlama listesine bir cihaz eşitleme eylemi ekliyor. İki konumdan birine tıklayarak cihazlarınızı hızla eşitleyin ve şirket kaynaklarına erişim sağlayın.  

### <a name="reset-device-passcodes-from-company-portal-app-for-windows-10----2101282---"></a>Windows 10 için Şirket Portalı uygulamasından cihaz geçiş kodlarını sıfırlama <!-- 2101282 --> 
Çalışanlarınız yakın zamanda cihazlarının PIN’i veya geçiş kodunu doğrudan Windows 10 için Şirket Portalı uygulamasından sıfırlayabilecek. Bu işlevsellik, geçiş kodu sıfırlamalarını destekleyen hem uzak hem de yerel Intune tarafından yönetilen cihazlarda kullanılabilecek. Cihaz türüne bağlı olarak, bir uzak cihaza yapılan istek ya cihazın geçerli geçiş kodunu kaldırır ya da geçici bir geçiş kodu oluşturur. Yerel bir cihaz için sıfırlama isteğinde bulunan kullanıcılar, cihazın Ayarlar uygulamasına yeniden yönlendirilir.  

### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows----2317227---"></a>Windows için Şirket Portalı uygulamasında yeni gözatma deneyimleri <!-- 2317227 -->  
Windows için Şirket Portalı uygulamasında uygulamalara gözatarken veya uygulama ararken mevcut **Kutucuklar** görünümü ile yeni eklenen **Ayrıntılar** görünümü arasında geçiş yapabileceksiniz. Yeni görünüm; ad, yayımcı, yayım tarihi ve yükleme durumu gibi uygulama ayrıntılarını listeler.  

**Uygulamalar** sayfası, tamamlanmış ve devam eden uygulama yüklemeleri hakkında ayrıntıları görmenize olanak verecek bir **Yüklemeler** görünümü sunacak. Yeni değişiklikler hakkında geri bildirim veya görüş paylaşmak ister misiniz? Geri bildiriminizi bize Şirket Portalı uygulaması üzerinden gönderin.

### <a name="improved-company-portal-app-experience-for-device-enrollment-manager-users----675800---"></a>Cihaz kayıt yöneticisi kullanıcıları için geliştirilmiş Şirket Portalı uygulama deneyimi <!-- 675800 -->
Bir cihaz kayıt yöneticisi (DEM) Windows için Şirket Portalı uygulamasında oturum açtığında, uygulama yalnızca yöneticinin geçerli, çalışan cihazını listeleyecek. Bu yenilik, uygulama DEM tarafından kaydedilen tüm cihazlara yüklenmeye çalıştığında yaşanan zaman aşımı sorunlarını azaltacak.  

### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>DEP kaydı sırasında Şirket Portalı’nın ön sağlamasını yapmak için VPP cihaz lisanslarını kullanın <!-- 1608345 -->
Aygıt Kayıt Programı (DEP) kayıtları sırasında Şirket Portalı’nın ön sağlamasını yapmak için Volume Purchase Program (VPP) cihaz lisanslarını kullanabileceksiniz. Bunu yapmak için bir kayıt profili oluşturduğunuzda veya düzenlediğinizde, Şirket Portalı’nı yüklemek için kullanmak istediğiniz VPP belirtecini belirtin. Belirtecinizin süresinin dolmadığından ve Şirket Portalı uygulaması için yeterli lisansınız olduğundan emin olun. Belirtecin süresi dolduğu veya yeterli lisans olmadığı durumlarda, Intune bunun yerine Uygulama Mağazası Şirket Portalı’na istek gönderir (bu, Apple kimliği ister).

###  <a name="windows-line-of-business-lob-apps-file-extensions----1884873---"></a>Windows iş kolu (LOB) uygulamaları dosya uzantıları <!-- 1884873 -->
Windows LOB uygulamaları için dosya uzantıları artık *.msi*, *.appx*, *.appxbundle*, *.msix* ve *.msixbundle*’ı içerecek. Microsoft Intune’da, **Mobil uygulamalar** > **Uygulamalar** > **Ekle**’yi seçerek bir uygulama ekleyebilirsiniz. **Bölme ekle** bölmesi görüntülenir ve **Uygulama türünü** seçmenize olanak tanır. Windows LOB uygulamaları için uygulama türü olarak **İş kolu uygulamasını** seçin, **Uygulama paketi dosyasını** seçin ve uygun uzantıya sahip bir yükleme dosyası girin.

### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Windows Defender ATP yapılandırma paketi, otomatik olarak yapılandırma profiline eklenir <!-- 2144658 -->
Şu anda Intune’da [Gelişmiş Tehdit Koruması ve ekleme](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile) cihazları kullanırken bir yapılandırma paketini indirip bunu yapılandırma profilinize ekliyorsunuz. Gelecekteki bir güncelleştirmede Intune, paketi otomatik olarak Windows Defender Güvenlik Merkezi'nden alır ve profilinize ekler.

Windows 10 ve üzeri için geçerlidir.

### <a name="check-for-sccm-compliance----2192052---"></a>SCCM uyumluluğunu denetleme <!-- 2192052 -->
Gelecekte yapılacak bir güncelleştirmede yeni bir System Center Configuration Manager (SCCM) uyumluluk ayarı olacaktır (**Cihaz uyumluluğu** > **İlkeler** > **İlke oluşturma**  > **Windows 10**). SCCM, Intune uyumluluğuna sinyal gönderir. Intune ayarını kullanarak, tüm SCCM sinyallerinin “uyumlu” döndürmesini gerektirebilirsiniz.

Örneğin, tüm yazılım güncelleştirmelerinin cihazlarda yüklü olmasını gerektirirsiniz. SCCM’de bu gereksinim, "Yüklü" durumuna sahiptir. Cihazdaki herhangi bir program bilinmeyen bir durumdaysa cihaz, Intune ile uyumlu olmayacaktır.

Windows 10 ve üzeri için geçerlidir

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Süresi dolan VPP belirteci veya yetersiz Şirket portalı lisansı uyarıları <!-- 2237572 -->
DEP kaydı sırasında Şirket Portalı’nın ön sağlamasını yapmak için Volume Purchase Program (VPP) kullanıyorsanız Intune, VPP belirtecinin süresi dolmak üzereyken ve Şirket Portalı lisansları yetersiz sayıdayken sizi uyarır.

### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Şirket Portalı ön sağlaması için kullanılan bir VPP belirtecini silmek için onay gerekir <!-- 2237634 -->
DEP kaydı sırasında Şirket Portalı’nın ön sağlaması için kullanılıyorsa bir Volume Purchase Program (VPP) belirtecini silmek için onay gerekir.

#### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Windows Installer için ek güvenlik ayarları <!-- 2282430 -->
Kullanıcıların uygulama yüklemelerini denetlemesine olanak sağlayabileceksiniz. Etkinleştirilirse, aksi takdirde güvenlik ihlali nedeniyle durdurulabilecek olan yüklemelerin devam etmesine izin verilebilir. Windows Installer'ı sistemde herhangi bir program yüklerken yükseltilmiş izinler kullanmaya yönlendirebileceksiniz. Buna ek olarak, Windows Bilgi Koruması (WIP) öğelerinin dizine alınmasını ve bunlar hakkındaki meta verilerin şifrelenmemiş bir konumda depolanmasını etkinleştirebileceksiniz. İlke devre dışı bırakıldığında, WIP korumalı öğelerin dizini oluşturulmayacak ve Cortana veya dosya gezgini sonuçlarında görünmeyecek. Bu seçeneklerin işlevselliği varsayılan olarak devre dışı bırakılacak. 

<!-- 1806 start -->

### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>iOS'ta üçüncü taraf klavyeler APP ayarlarıyla engellenebilir <!-- 1248481 -->
iOS cihazlarında, Intune yöneticileri ilke korumalı uygulamalarda kuruluş verilerine erişilirken üçüncü taraf klavyelerin kullanımını engelleyebilecek. Uygulama Koruma İlkesi (APP) üçüncü taraf klavyelerini engelleyecek şekilde ayarlandığında, cihaz kullanıcısı üçüncü taraf klavyesini kullanarak şirket verileriyle ilk kez etkileşim kurarken bir ileti alacak. Yerel klavye dışındaki tüm seçenekler engellenecek ve cihaz kullanıcıları bunları görmeyecek. Cihaz kullanıcıları iletişim kutusu iletisini tek bir kez görür. 

### <a name="require-non-biometric-passcode-on-app-launch-and-timeout----1506985---"></a>Uygulama başlatma işleminde ve zaman aşımı durumunda biyometrik olmayan bir geçiş kodu gerektirin <!-- 1506985 -->

Uygulama başlatma işleminde ve yöneticinin belirttiği zaman aşımı durumunda biyometrik olmayan bir geçiş kodu gerektirerek, Intune şirket verilerine erişim için biyometrik tanımlama kullanımını kısıtlama yoluyla Mobil Uygulama Yönetimi'nin (MAM) etkinleştirildiği uygulamalarda gelişmiş güvenlik sağlayacak. Bu ayar, APP/MAM etkin uygulamalarına erişmek için Touch ID (iOS), Face ID (iOS), Android Biometric, veya geleceğin diğer kimlik doğrulama yöntemlerine güvenen kullanıcıları etkileyecek. Bu ayarlar birden çok parmak izi veya başka biyometrik erişim yöntemi olan bir cihazın şirket verilerini yanlış kullanıcıya gösterebildiği durumları ortadan kaldırarak, Intune yöneticilerinin kullanıcı erişimi üzerinde daha ayrıntılı bir denetim sahibi olmasına olanak tanıyacak. Azure portalında **Microsoft Intune**'u açın. **Mobil uygulamalar** > **Uygulama koruma ilkeleri** > **İlke ekle** > **Ayarlar**'ı seçin. Belirli ayarlar için **Erişim** bölümünü bulun.

### <a name="office-365-pro-plus-language-packs----1833450---"></a>Office 365 Pro Plus dil paketleri <!-- 1833450 -->
Intune yöneticisi olarak, Intune aracılığıyla yönetilen Office 365 Pro Plus uygulamaları için ek dillerin dağıtımını yapabileceksiniz. Kullanılabilir diller listesi, dil paketinin **Tür** bilgisini içerir (çekirdek, kısmı ve yazım denetleme). Azure portalında **Microsoft Intune** > **Mobil uygulamalar** > **Uygulamalar** > **Ekle**'yi seçin. **Uygulama ekle** dikey penceresindeki **Uygulama türü** listesinde **Office 365 Paketi** altından **Windows 10**'u seçin. **Uygulama Paketi Ayarları** dikey penceresinde **Diller**'i seçin.

### <a name="preview-a-new-user-experience-update-for-the-company-portal-website---2000968---"></a>Şirket Portalı web sitesi için yeni kullanıcı deneyimi güncelleştirmesinin önizlemesi <!--2000968 -->
Müşterilerden gelen geri bildirim temelinde Şirket Portalı web sitesine/iOS uygulama kataloğuna yeni özellikler ekliyoruz. Android, iOS ve Windows cihazlarının mevcut işlevselliğinde ve kullanılabilirliğinde önemli geliştirmeler göreceksiniz. Sitenin cihaz ayrıntıları, geri bildirim ve destek, cihaza genel bakış gibi alanlarında yeni, modern, hızlı yanıt veren bir tasarım elde edeceksiniz. Şunları da göreceksiniz:

- Tüm cihaz platformları arasında rahat iş akışları
- Geliştirilmiş cihaz kimlik ve kayıt akışları
- Daha yararlı hata iletileri
- Daha rahat bir dil, daha az teknik jargon
- Doğrudan uygulama bağlantıları paylaşabilme seçeneği
- Büyük uygulama katalogları için iyileştirilmiş performans
- Tüm kullanıcılar için artırılmış erişilebilirlik

Bu güncelleştirme şu anda önizleme aşamasındadır. Önizlemeye katılmak için http://aka.ms/webcpflighting adresinden kaydolabilirsiniz

<!-- 1805 start -->

### <a name="require-non-biometric-passcode-on-cold-app-launch-and-timeout----1506985---"></a>Sıfırdan uygulama başlatma işleminde ve zaman aşımı durumunda biyometrik olmayan bir geçiş kodu gerektirin <!-- 1506985 --> 

Sıfırdan uygulama başlatma işleminde ve yöneticinin belirttiği zaman aşımı durumunda biyometrik olmayan bir geçiş kodu gerektirerek, Intune şirket verilerine erişim için biyometrik tanımlama kullanımını kısıtlama yoluyla Mobil Uygulama Yönetimi'nin (MAM) etkinleştirildiği uygulamalarda gelişmiş güvenlik sağlayacak. Bu ayar, APP/MAM etkin uygulamalarına erişmek için Touch ID (iOS), Face ID (iOS), Android Biometric, veya geleceğin diğer kimlik doğrulama yöntemlerine güvenen kullanıcıları etkileyecek. Bu ayarlar birden çok parmak izi veya başka biyometrik erişim yöntemi olan bir cihazın şirket verilerini yanlış kullanıcıya gösterebildiği durumları ortadan kaldırarak, Intune yöneticilerinin kullanıcı erişimi üzerinde daha ayrıntılı bir denetim sahibi olmasına olanak tanıyacak. Azure portalında **Microsoft Intune**'u açın. **Mobil uygulamalar** > **Uygulama koruma ilkeleri** > **İlke ekle** > **Ayarlar**'ı seçin. Belirli ayarlar için **Erişim** bölümünü bulun.

<!-- 1803 start -->

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Gerekli iş kolu (LOB) uygulamalarını Windows 10 Masaüstü cihazlarında Tüm Kullanıcılara dağıtabilme <!-- 1627835 RS4 -->
Müşteriler gerekli iş kolu Windows 10 uygulamalarını cihaz bağlamlarına yüklemek üzere dağıtabilecek. Böylelikle bu uygulamalar cihazdaki tüm kullanıcılara sağlanabilir. Bu yalnızca Windows 10 Masaüstü cihazları için geçerlidir.

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Android için Şirket Portalı uygulamasında Yardım ve Geri Bildirim deneyimini güncelleştirme <!--1631531 -->

Android uygulamalarına yönelik en iyi yöntemlerle uyumlu olacak şekilde, Android için Şirket Portalı uygulamasında Yardım ve Geri Bildirim deneyimi güncelleştirilecek. Önümüzdeki birkaç ay içinde Android için Şirket Portalı uygulaması güncelleştirilerek **Yardım ve Geri Bildirim** menü öğesi **Yardım** ve **Geri Bildirim Gönder** menü öğelerine ayrılacak. Son kullanıcıları günlükleri Microsoft'a yüklemeye ve şirket desteğine sorunu açıklayan bir e-posta göndermeye yönlendirmek için, **Yardım** sayfasında **Sık Sorulan Sorular** bölümü ve **E-posta Desteği** düğmesi bulunacak. **Geri Bildirim Gönder** kullanıcıyı standart Microsoft geri bildirim gönderimine yönlendirecek ve kullanıcıdan "Bir şeyi beğendim" "Bir şeyi beğenmedim" veya "Bir fikrim var" arasında seçim yapması istenecek.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Uygulama koruma ilkeleri  <!-- 679615 -->
Intune Uygulama Koruma İlkeleri, tüm kiracıdaki tüm kullanıcılar için hızlı bir şekilde koruma sağlamaya yönelik genel ve varsayılan ilkeler oluşturma olanağı sunar.

<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Bildirimler

Şu anda etkin bildirim yok.

### <a name="see-also"></a>Ayrıca bkz:
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).



