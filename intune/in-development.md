---
title: Geliştirme - Intune
titleSuffix: ''
description: Geliştirme Intune özellikleri
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/29/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 327019527ea3c374a3ebeb3c29703dbd744d18dc
ms.sourcegitcommit: 9daaeba9a960c50efcc951856234fbfec3635737
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59231777"
---
# <a name="in-development-for-microsoft-intune---april-2019"></a>Microsoft Intune - Nisan 2019 geliştirme

İçinde hazırlık ve planlama, bu sayfa yardımcı olmak için Intune kullanıcı Arabirimi güncelleştirmeleri ve özelliklerinin listesi geliştirme aşamasındadır ancak henüz serbest. Buna ek olarak:

- Bir değişiklik önce harekete gerekecektir tahmin, biz tamamlayıcı bir Office ileti Merkezi'nde gönderi yayınlayacaksınız.
- Ne zaman bir özellik, üretimde ya da önizleme olarak başlatılır veya genel kullanıma sunulan özellik açıklaması bu sayfayı kapatmak ve üzerine taşınır [yenilikler](whats-new.md).
- Bu sayfada ve [yenilikler](whats-new.md) düzenli olarak güncelleştirilir. Ek güncelleştirmeleri daha sonra denetleyin.
- Başvurmak [M365 yol haritası](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) stratejik teslim edilebilirleri ve zaman çizelgeleri için.

> [!Note]
> Bu öğeler, gelecekteki bir sürümde sunulacak Intune özellikleri hakkında daha fazla geçerli beklentileri Microsoft'un yansıtır. Tarih ve tek tek özellikler değişebilir. Geliştirme tüm öğeler, bu sayfada bir özellik açıklaması içerir.

**RSS akışı**: Bu sayfa aşağıdaki URL'yi kullanarak akış okuyucuya yapıştırarak güncelleştirildiğinde bildirim alın: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Azure portalında Intune

<!-- 1904 start-->

### <a name="set-login-settings-and-control-restart-options-on-macos-devices----1210083---"></a>Oturum açma ayarlarını ve macOS cihazlarında yeniden başlatma seçeneklerini denetleme <!-- 1210083 -->
MacOS cihazlarında cihaz yapılandırma profili oluşturabilirsiniz (**cihaz Yapılandırması** > **profilleri** > **profili oluşturma** > seçin **macOS** Platform > **cihaz özellikleri** profil türü için). Yeni oturum açma penceresi ayarlarını gibi özel bir başlık gösteren öğeler içerir, nasıl kullanıcılar oturum açın, göstermek veya güç ayarlarını ve daha fazlasını gizlemek seçin.

Geçerli ayarları görmek için Git [macOS cihaz özelliği ayarlarını](macos-device-features-settings.md).

İçin geçerlidir: macOS

### <a name="advanced-settings-for-windows-defender-firewall----1311949---"></a>Windows Defender Güvenlik Duvarı için Gelişmiş ayarları <!-- 1311949 -->
Yakında istemciler için Windows Defender'ın özel bir güvenlik duvarı kurallarını yönetmek için Intune kullanmak mümkün olacaktır. Kural, uygulamalar, ağ adresleri ve bağlantı noktalarına gelen ve giden davranış belirtebilirsiniz. 

### <a name="require-app-protection-conditional-access----1634317---"></a>Uygulama koruma koşullu erişim gerektirir  <!--1634317 -->
Kullanılacak mümkün olacaktır *gerektiren uygulama koruma İlkesi*, hangi ilke onaylar kullanıcıların koşullu erişim ile koruduğunuz veri erişimini engellemek için oturum açma tamamlanmadan önce bir kullanıcının uygulamaya uygulanır. İlke güvencesi ilk kullanım deneyimi yavaş, ancak ağ sorunları, yönetim yanlış yapılandırmalarını veya uygulama koruma ilkeleri önleme kasıtlı çalışmalarını karşı korumak için yardımcı olur. 

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----16726660---"></a>İş uygulamalarına yönelik çevrimiçi lisanslı Microsoft Store dağıtımı <!-- 16726660 -->
Gerekli çevrimiçi lisanslı Microsoft Store cihaz bağlamında kurumsal uygulamalar için atama mümkün olacaktır. Bu şekilde bir iş uygulaması için Microsoft Store dağıtımı, cihazdaki tüm kullanıcılar için yüklenecek uygulamayı etkinleştirir. Bu yalnızca Windows 10 RS4 + Masaüstü cihazları için geçerlidir. Cihaz bağlamında yükleme seçeneği, istemci uygulamaları atama sayfasında MSFB çevrimiçi lisanslı uygulamaları için kullanılabilir.

### <a name="include-and-exclude-mixture-of-user-groups-and-device-groups-when-assigning-policies-and-profiles----1807547---"></a>Ekleme ve kullanıcı grupları ve cihaz grupları bileşimi ilkeler ve Profiller atarken çıkarma <!-- 1807547 -->
Uyumluluk ilkeleri veya yapılandırma profillerini atarken, kullanıcılara veya cihazlara, bunları güvenlik gruplarına atayabilirsiniz. Şu anda, içerir ve yalnızca kullanıcı grupları hariç *veya* dahil etmek ve yalnızca cihaz gruplarını dışlamak. Gönderilemiyor dahil ve hariç grupların bir karışımını, gibi kullanıcı gruplarını dahil etme *ve* aygıtları grubu hariç.

Dahil etmek ve kullanıcı grupları ve cihaz grupları dışlamak mümkün olacaktır. Grubunu hariç tutmak ve bir kullanıcı grubu içerir. Örneğin, atama veya bir kullanıcı grubuna bir cihaz yapılandırma profili dağıtmak ancak kişisel cihazları.

[Cihaz yapılandırma profillerini atama](device-profile-assign.md) kullanıcı grupları ve cihaz profilleri atama hakkında daha fazla bilgi içerir.

Şunun için geçerlidir: Tüm platformlar

### <a name="retire-noncompliant-devices----1827291---"></a>Uyumlu olmayan cihazları devre dışı bırakma <!-- 1827291 -->
Uyumsuz bir cihazı devre dışı bırakmak için yeni bir uyumluluk eylemi eklemek için ekleyeceğiz. Uyumsuz bir cihazı devre dışı bırakma tüm şirket verileri CİHAZDAN kaldırılır ve Intune tarafından yönetilen cihaz de kaldırır. Bu eylem, gün içinde yapılandırılan değeri ulaşıldığında çalıştırır. Minimum değer 30 gündür. 

### <a name="configure-settings-for-kernel-extensions-on-macos-devices----2043024---"></a>MacOS cihazlarında çekirdek uzantıları için ayarları yapılandırma <!-- 2043024 -->
MacOS cihazlarında cihaz yapılandırma profili oluşturabilirsiniz (**cihaz Yapılandırması** > **profilleri** > **profili oluşturma** > seçin **macOS** platform için). Yeni bir Grup ayarlarını yapılandırmak ve çekirdek uzantıları cihazlarınızda kullanmanıza sağlayacaktır.

İçin geçerlidir: macOS 10.13.2 ve üzeri

### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470---"></a>Bazı ekranlar Kurulum Yardımcısı sırasında atlanacak profili yapılandırma <!-- 2276470 -->
Bir macOS kayıt profili oluşturduğunuzda, bir kullanıcının Kurulum Yardımcısı kullanırken aşağıdaki ekranlardan istediğini atlayabilmesi için bu profili yapılandırabileceksiniz:
- Android Geçişi
- Görüntü Tonu
- Gizlilik
- Yeni bir profil oluşturun ya da bir profil düzenleme iCloudStorage seçili ekranlar Apple MDM sunucusu ile eşitleme gerek atlayın. Kullanıcılar, böylece gecikme profili değişiklikleri çekme cihazların el ile eşitleme verebilir.
Daha fazla bilgi için [macOS cihazlarını cihaz kayıt programı veya Apple School Manager ile otomatik olarak kaydetme](device-enrollment-program-enroll-macos.md).

### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Cihaz kullanıcılarının yüklü veya yüklemeyi denedi tüm yönetilen uygulamalar görüntüleyebilirsiniz. <!-- 2352913 -->
Tüm yönetilen uygulamalar için Şirket portalı Windows listeler&ndash; hem gerekli hem de kullanılabilir&ndash; bir kullanıcı cihazında yüklü. Kullanıcılar, denenen görüntülemek ve bekleyen uygulama yüklemelerini ve bunların geçerli durumlarını mümkün olacaktır. Kuruluşunuzun uygulamalarını gerekli veya kullanılabilir duruma getirilmez, kullanıcılar şirket uygulama yüklenmiş olduğunu açıklayan bir ileti görür. Kullanıcılar ayrıca sıralamak veya uygulamalarını yükleme durumuna göre filtre uygulamak mümkün olacaktır.

### <a name="scope-tags-for-apple-vpp-tokens---2371886---"></a>Kapsam etiketleri Apple VPP belirteçleri <!--2371886 -->
Kapsam etiketleri Apple VPP belirteçleri eklemek mümkün olacaktır. Bu etikete sahip Apple VPP belirtecinin yalnızca aynı kapsam etiketi ile atanan kullanıcılar erişebilir. VPP uygulamalarını ve o belirteç ile satın alınan e-Kitaplar, kapsam etiketleri devralır. Kapsam etiketleri hakkında daha fazla bilgi için bkz: [kullanım RBAC ve kapsam etiketleri](scope-tags.md).

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>"Uygulanabilirlik kuralları" kullandığınızda Windows 10 cihaz yapılandırma profilleri oluşturma <!-- 2549910 -->
Windows 10 cihaz yapılandırma profilleri oluşturma (**cihaz Yapılandırması** > **profilleri** > **profili oluşturma**  >  **Windows 10** platform için). Oluşturma tutulacak bir **Uygulanabilirlik kuralı** profili yalnızca bir belirli sürüm veya belirli bir sürüme uygular. Örneğin, bazı BitLocker ayarları sağlayan bir profil oluşturun. Profili eklediğinizde profil, yalnızca Windows 10 Enterprise çalıştıran cihazlar için uygular bir geçerlilik kuralı kullanın.

Şunun için geçerlidir: 
- Windows 10 ve üzeri

### <a name="enable-win32-app-dependencies----2617348---"></a>Win32 Uygulama bağımlılıklarını etkinleştirin <!-- 2617348 -->
Genel Önizleme - yönetici sizin Win32 uygulamanızı yüklemeden önce diğer uygulamaları bağımlılıkları olarak yüklendiğinden emin zorunlu kılmanız mümkün olacaktır. Özellikle, Win32 Uygulama yüklenmeden önce cihaz bağımlı uygulamalarını yüklemeniz gerekir. Intune yönetim aracısı için 1904 biz hizmeti yükselttikten sonra 1 veya 2 ek hafta sürebilir 1904 sürüme (1.18.120.0 büyük) yalnızca yükseltildikten sonra bu işlevselliği kullanılabilir. Intune'da seçin **istemci uygulamaları** > **uygulamaları** > **Ekle** görüntülenecek **uygulama Ekle** dikey penceresi. Seçin **Windows uygulaması (Win32)** olarak **uygulama türü**. Daha fazla bilgi için [tek başına Intune - Win32 Uygulama Yönetimi](apps-win32-app-management.md).

### <a name="new-device-restriction-setting-for-android-enterprise-device-owner-let-users-connect-to-wi-fi-networks-on-android-enterprise-dedicated-devices-running-multi-app-kiosk-mode---3041940---"></a>Android Enterprise, cihaz sahibi için yeni cihaz kısıtlama ayarı: kullanıcıların çoklu uygulama bilgi noktası modu çalıştıran Android ayrılmış Kurumsal cihazlarda Wi-Fi ağları bağlanmasına olanak tanır <!--3041940 -->
Yöneticileri, kullanıcıların adanmış Android kuruluş cihazlarını çoklu uygulama bilgi noktası modunda çalışan Bluetooth yapılandırmasına olanak tanıyan yeni bir ayarı değiştirmek mümkün olacaktır. Bu ayar Intune konsolunda görmek için **Intune** > **cihaz Yapılandırması** > **profilleri**  >  **Profil oluşturma** > seçin **Android Kurumsal** Platform > **yalnızca cihaz sahibi, cihaz kısıtlamaları** profil türü için > **ayarları**   >  **Adanmış cihazlar** > seçin **çoklu uygulama** gelen **bilgi noktası modu** ayarı açılır. Bir seçenek olarak adlandırılan **Wi-Fi yapılandırma** etkinleştirmek kullanılabilir. 

Şunun için geçerlidir: Android Kurumsal çoklu uygulama bilgi noktası modu çalıştıran cihazlara atanmış. 

### <a name="new-device-restriction-setting-for-android-enterprise-device-owner-let-users-configure-bluetooth-and-pairing-on-android-enterprise-dedicated-devices---3041941---"></a>Android Enterprise, cihaz sahibi için yeni cihaz kısıtlama ayarı: kullanıcıların Bluetooth ve adanmış Android Kurumsal cihazlarda eşleştirme yapılandırmasına olanak tanır <!--3041941 -->
Yöneticileri, kullanıcıların adanmış Android kuruluş cihazlarını çoklu uygulama bilgi noktası modunda çalışan Bluetooth yapılandırmasına olanak tanıyan yeni bir ayarı değiştirmek mümkün olacaktır. Bu ayar Intune konsolunda görmek için **Intune** > **cihaz Yapılandırması** > **profilleri**  >  **Profil oluşturma** > seçin **Android Kurumsal** Platform > **yalnızca cihaz sahibi, cihaz kısıtlamaları** profil türü için > **ayarları**   >  **Adanmış cihazlar** > seçin **çoklu uygulama** gelen **bilgi noktası modu** ayarı açılır. Bir seçenek olarak adlandırılan **Bluetooth yapılandırma** etkinleştirmek kullanılabilir. 

Şunun için geçerlidir: Android Kurumsal çoklu uygulama bilgi noktası modu çalıştıran cihazlara atanmış. 

### <a name="monitor-security-baseline-status-public-preview----3082047---"></a>(Genel Önizleme) güvenlik durumunu izleme <!-- 3082047 --> 
Ne zaman izlemeniz *cihaz durumu* , güvenlik temellerini için Görünüm durumu temel kategorilere göre gibi düzenleyecek *kilit üzerinde*, *BitLocker*ve  *Tarayıcı*. Tüm kullanılabilir temel kategorilerini temsil edilir. Her kategori için kaç cihazın belirli temel kategori eşleşmiyor, yanlış veya uygulanamaz görürsünüz.

###  <a name="intune-security-tasks-for-defender-atp-in-public-preview----3208597---"></a>Intune güvenlik görevleri için Defender ATP (genel Önizleme) <!-- 3208597 -->
Genel önizleme olarak kullanıma sunulacak, Intune hemen güvenlik görevlerini yeni duyurulan Microsoft Defender tehdit ve güvenlik açığı yönetimi için ekler.  Bu tümleştirme sayesinde güvenlik işlemleri yöneticileri Windows Defender ATP (WDATP) Intune yöneticileri için ortaya çıkan tehditleri için önerilen düzeltmeler daha etkili bir şekilde iletişim kurabilir. Güvenlik görevlerini eklenmesi, keşfedin, öncelik sırasına sokmanıza ve uç noktası Güvenlik Açıkları ve yanlış yapılandırmalarını düzeltmek için risk tabanlı bir yaklaşım ekler.

Intune'da güvenlik görevler hakkında daha fazla bilgi için ilgili blog gönderisine bakın [Microsoft Defender ATP'nin güvenlik açığı yönetimi ve tehdit genişletmek için Intune güvenlik görevlerini kullanarak](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Microsoft-Intune-security-tasks-extend-Microsoft-Defender-ATP-s/ba-p/369857). 

### <a name="create-and-use-oemconfig-device-configuration-profiles-in-intune----3305883---"></a>Oluşturma ve Intune'da OEMConfig cihaz yapılandırma profillerini kullanma <!-- 3305883 -->
Intune OEMConfig ile Android Kurumsal cihazların yapılandırılmasını destekler. Özellikle, bir cihaz yapılandırma profili oluşturabilir ve ayarları OEMConfig kullanarak kurumsal Android cihazlar için geçerlidir (**cihaz Yapılandırması** > **profilleri**  >  **Profili oluşturma** > **Android Kurumsal** platform için).

OEM'leri şu anda bir OEM başına temelinde desteğidir. İstediğiniz OEMConfig uygulama OEMConfig uygulamalar listesinde kullanılabilir değilse, ilgili kişi `IntuneOEMConfig@microsoft.com`.

Şunun için geçerlidir: 
- Android Kurumsal

### <a name="new-device-restriction-settings-for-android-enterprise-device-owner----3574254---"></a>Android Enterprise, cihaz sahibi için yeni cihaz kısıtlama ayarları <!-- 3574254 -->
Android Kurumsal cihazlarda izin vermek veya özellikler, parola kuralları ayarla ve daha fazla kısıtlamak için cihaz kısıtlama profili oluşturabilirsiniz (**cihaz Yapılandırması** > **profilleri**  >  **Profili oluşturma** > seçin **Android Kurumsal** Platform > **yalnızca cihaz sahibi > cihaz kısıtlamaları** profil türü için). 

Google Play Store uygulamalarında tam olarak yönetilen cihazlar için yeni ayarları, tam izin vererek, parola ayarları dahil olmak üzere erişim ve daha kullanılabilir olacak. 

Geçerli ayarları listesini görmek için Git [izin vermek veya özellikleri kısıtlamak için Android Kurumsal cihaz ayarları](device-restrictions-android-for-work.md). 

Şunun için geçerlidir: Android Kurumsal tam olarak yönetilen cihazlar

### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>Bir Windows 10 cihaz uyumluluk İlkesi, TPM yonga denetle <!-- 3617671 -->
Güvenilir Platform Modülü (TPM) yonga kümeleri çok sayıda Windows 10 ve üzeri cihazlar vardır. Yeni bir uyumluluk ayarı bir TPM cihazı olup olmadığını denetler.

[Windows 10 ve üzeri uyumluluk İlkesi ayarları](compliance-policy-create-windows.md#windows-10-and-later-policy-settings) geçerli ayarlarını listeler.

Şunun için geçerlidir: 
- Windows 10 ve üzeri

### <a name="configure-your-win32-apps-to-be-installed-on-intune-enrolled-azure-ad-joined-devices----3695227---"></a>Intune'a kayıtlı üzerinde yüklenmesi, Win32 uygulamalarını yapılandırma Azure AD'ye katılmış cihazlar <!-- 3695227 -->
Sizin için mümkün olacaktır Ata Win32 uygulamalarınızı Intune yüklenecek kayıtlı Azure AD alanına katılmış cihazlar. Intune'da Win32 uygulamalar hakkında daha fazla bilgi için bkz. [Win32 Uygulama Yönetimi](apps-win32-app-management.md).

### <a name="windows-defender-advanced-threat-protection-baseline----3754134---"></a>Windows Defender Gelişmiş tehdit koruması temeli <!-- 3754134 -->
Windows Defender Gelişmiş tehdit koruması ayarları yapılandırmanıza yardımcı olması için yeni temeli eklemek için ekleyeceğiz.

### <a name="device-overview-shows-primary-user---794259---"></a>Birincil kullanıcı cihaz genel bakışı gösterir <!--794259 -->
Birincil de kullanıcı aygıt benzeşimi kullanıcı (UDA) adlı kullanıcı, cihaz genel bakış sayfası gösterilir. Bir cihaz için birincil kullanıcı görmek için **Intune** > **cihazları** > **tüm cihazlar** > bir cihaz seçin. Birincil kullanıcıya en görüneceğini **genel bakış** sayfası.

### <a name="expanded-support-for-android-enterprise-fully-managed-devices----3903241-3903244-3903246---"></a>Android Enterprise için genişletilmiş destek tam olarak yönetilen cihazlar <!-- 3903241, 3903244, 3903246 -->
Tam olarak yönetilen Android kuruluş cihazlarının desteğini genişletmek için oluşturacağız ([2019'ın Ocak ilk duyurulan](whats-new.md#week-of-january-14-2019) şunlar için:
- Uyumluluk
- Koşullu erişim
- Yeni son kullanıcı uygulama

Ayarlamak için Android tam olarak yönetilen cihazlar, Git **cihaz kaydı** > **Android kaydını** > **şirkete, tam olarak yönetilen kullanıcı cihazları**. Destek için tam olarak yönetilen Android cihazları hala Önizleme aşamasındadır ve bazı Intune özellikleri tam olarak işlevsel olmayabilir. 

### <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices----4105925---"></a>Android kurumsal iş profili cihazları için raporlama ek yönetilen Google Play uygulaması <!-- 4105925 -->
Android kurumsal iş profili cihazlara dağıttığınız yönetilen Google Play uygulamaları için bir cihaza yüklenen uygulamanın belirli sürüm numarasını görüntülemek mümkün olacaktır. Bu, yalnızca gerekli uygulamalar için geçerlidir. Gelecekteki bir sürümde aynı işlevselliği kullanılabilir uygulamalar için etkinleştirilir.

### <a name="ios-third-party-keyboards----4111843---"></a>iOS üçüncü taraf klavyeler <!-- 4111843 -->
Intune uygulama koruma İlkesi (uygulama) için destek **üçüncü taraf klavyeler** ayarı, bir iOS platform değişikliği nedeniyle sona erecek. Intune Yönetici konsolunda bu ayarı yapılandırmak mümkün olmayacaktır ve Intune uygulama SDK'sı istemcide uygulanmaz.

<!-- 1903 start-->

### <a name="block-users-from-scanning-for-windows-updates----3316758---"></a>Windows güncelleştirmeleri için tarama kullanıcıların engelle <!-- 3316758 -->
Windows güncelleştirmeleri için tarama kullanıcıların engellemek için kullanabileceğiniz yeni bir Windows güncelleştirme halkası ayar ekliyoruz. Bu ayar, portalın içinde kullanılabilir durumda olmaz ancak Intune Graph API'si kullanılarak yapılandırılabilir.

### <a name="windows-update-notifications----3316782---"></a>Windows güncelleştirme bildirimleri <!-- 3316782 -->
Kullanıcıların görmesi Windows güncelleştirme bildirimleri yapılandırmak için bu sayede, Windows güncelleştirme halkası yapılandırmaları için destek ekliyoruz. Bu ayar, portalın içinde kullanılabilir durumda olmaz ancak Intune Graph API'si kullanılarak yapılandırılabilir.

### <a name="easier-access-to-diagnostic-settings----3804627---"></a>Daha kolay erişim için tanılama ayarları <!-- 3804627 -->
Yeni bir seçenek ekliyoruz **denetim günlükleri** dikey penceresinde, doğrudan açmak için kullanabileceğiniz Intune konsolundaki her bir denetim günlüğüne iş yükünün *tanılama ayarları* sayfası.

## <a name="notices"></a>Bildirimler

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).


