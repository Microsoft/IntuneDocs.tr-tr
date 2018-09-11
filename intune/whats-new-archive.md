---
title: Microsoft Intune - Azure’da önceki aylarda yapılan yenilikler | Microsoft Docs
titlesuffix: ''
description: Intune’daki yenilikler sayfasından eski duyuruları gözden geçirme
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/19/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ea9f8662faad1f8ef70fbba4c3706930d31157ac
ms.sourcegitcommit: 2d1e89fa5fa721e79648e41fde147a035e7b047d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2018
ms.locfileid: "43347721"
---
# <a name="whats-new-in-the-microsoft-intune---previous-months"></a>Microsoft Intune’daki yenilikler - önceki aylar

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="november-2017"></a>Kasım 2017

### <a name="troubleshoot-enrollment-issues-----746324---"></a>Kayıt sorunlarını giderme  <!-- 746324 -->

**Sorun Giderme** çalışma alanı, şimdi kullanıcı kayıt sorunlarını gösterir. Sorunun ayrıntıları ve önerilen düzeltme adımları, yönetici ve yardım masası çalışanlarının sorunları çözmesine yardımcı olabilir. Bazı kayıt sorunları burada yer almaz ve bazı hatalar için düzeltme önerileri bulunmayabilir.

### <a name="group-assigned-enrollment-restrictions----747598---"></a>Gruba atanan kayıt kısıtlamaları <!-- 747598 -->

Bir Intune yöneticisi olarak, artık [kullanıcı grupları için özel Cihaz Türü ve Cihaz Sınırı kayıt sınırlamaları oluşturabilirsiniz](enrollment-restrictions-set.md).

Intune Azure portalı, her kısıtlama türü için en fazla 25 örnek oluşturmanıza olanak sağlar. Bunlar daha sonra kullanıcı gruplarına atanabilir. Grup tarafından atanan kısıtlamalar varsayılan kısıtlamaları geçersiz kılar.

Bir kısıtlama türünün tüm örnekleri kesin bir şekilde sıralanmış bir listede tutulur. Bu sıra, çakışmaları çözümlemek için bir öncelik değerini tanımlar. Birden fazla kısıtlama örneğinden etkilenen bir kullanıcı, yalnızca en yüksek öncelik değerine sahip örnek tarafından kısıtlanır. Belirli bir örneği listede farklı bir konuma sürükleyerek örneğin önceliğini değiştirebilirsiniz.

Bu işlevsellik, Android for Work ayarlarının Android For Work kayıt menüsünden Kayıt Kısıtlamaları menüsüne geçişi ile birlikte yayımlanacak. Bu geçiş birkaç gün sürebileceğinden, grup atamasının Kayıt Kısıtlamaları için etkinleştirildiğini görmeden önce hesabınız Kasım yayınının diğer bölümleri için güncelleştirilebilir.

### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Çoklu Ağ Cihazı Kayıt Hizmeti (NDES) bağlayıcısı desteği <!-- 1528104 -->

NDES, etki alanı kimlik bilgileri olmadan çalışan mobil cihazların Basit Sertifika Kayıt Protokolü’nü (SCEP) temel alarak sertifikaları edinmesini sağlar.
Bu güncelleştirme ile birden çok NDES bağlayıcısı desteklenir.

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Android for Work cihazlarını Android cihazlardan ayrı olarak yönetme <!-- 1490731 EEready-->

Intune, Android for Work cihazlarının Android platformundan bağımsız olarak kaydını yönetmeyi destekler. Bu ayarlar **Cihaz Kaydı** > **Kayıt kısıtlamaları** > **Cihaz Türü Kısıtlamaları** altında yönetilir. (Eskiden **Cihaz Kaydı** > **Android for Work Kaydı** > **Android for Work Kayıt Ayarları** altında bulunuyordu.)

Varsayılan olarak, Android for Work cihaz ayarlarınız Android cihazlarınız için ayarlarınızla aynı olur. Ancak Android for Work ayarlarınızı değiştirdikten sonra artık bu durum oluşmaz.

Kişisel Android for Work kaydını engellerseniz, yalnızca kurumsal Android cihazlar Android for Work olarak kaydolabilir.

Yeni ayarlarla çalışırken şu noktaları göz önünde bulundurun:

#### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Daha önce hiç Android for Work kaydı eklemediyseniz

Yeni Android for Work platformu varsayılan Cihaz Türü Kısıtlamalarında engellidir. Özelliği ekledikten sonra, cihazların Android for Work ile kaydolmasına izin verebilirsiniz. Bunu yapmak için varsayılan ayarı değiştirin veya varsayılan Cihaz Türü Kısıtlamasının yerine geçen yeni bir Cihaz Türü Kısıtlaması oluşturun.

#### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Android for Work kaydı eklediyseniz

Daha önceden eklediyseniz durumunuz seçtiğiniz ayara bağlıdır:

| Ayar | Varsayılan Cihaz Türü Kısıtlamasında Android for Work durumu | Notlar |
| --- | --- | --- |
| **Tüm cihazları Android olarak yönetme** | Engellendi | Tüm Android cihazların Android for Work ile kaydolması gerekir. |
| **Desteklenen cihazları Android for Work olarak yönetme** | İzin Verildi | Android for Work’ü destekleyen tüm Android cihazların Android for Work ile kaydolması gerekir. |
| **Yalnızca bu gruplardaki kullanıcılar için desteklenen cihazları Android for Work olarak yönetme** | Engellendi | Varsayılan ayarı geçersiz kılmak için ayrı bir Cihaz Türü Kısıtlama ilkesi oluşturuldu. Bu ilke önceden Android for Work kaydına izin vermek için seçtiğiniz grupları tanımlar. Seçili gruplardaki kullanıcıların Android for Work cihazlarını kaydetmesine izin verilir. Diğer tüm kullanıcıların Android for Work ile kaydolması kısıtlanır. |

Tüm durumlarda, hedeflenen düzenlemeniz korunur. Ortamınızda Android for Work’e genel olarak veya grup başına verilen izinleri tutmak için herhangi bir eylem gerçekleştirmeniz gerekmez.

### <a name="google-play-protect-support-on-android----908720---"></a>Android’de Google Play Protect desteği <!-- 908720 -->

Android Oreo sürümüyle Google, kuruluşların güvenli uygulamalar çalıştırmasına ve Android görüntülerinin güvenliğini sağlamasına imkan veren Google Play Protect adlı bir güvenlik özellikleri paketi piyasaya sunuyor. Intune, artol SafetyNet uzak kanıtlama dahil olmak üzere Google Play Protect özelliklerini destekliyor. Yöneticiler, Google Play Protect’ın yapılandırılması ve iyi durumda olmasını gerektiren uyumluluk ilke gereksinimleri ayarlayabilir.
**SafetyNet cihaz kanıtlama** ayarı, cihazın iyi durumda olduğu ve güvenliğinin aşılmadığını doğrulamak için cihazın bir Google hizmetiyle bağlanmasını gerektirir. Yöneticiler ayrıca, yüklenen uygulamaların Google Play hizmetleri tarafından doğrulanmasını gerektiren bir Android for Work yapılandırma profili ayarı da ayarlayabilir. Koşullu erişim, bir cihaz Google Play Protect gereksinimleriyle uyumlu olmadığında kullanıcıların şirket kaynaklarına erişimini engelleyebilir.

- [Google Play Koruması'nı etkinleştirmek için cihaz uyumluluk ilkesi oluşturmayı](https://docs.microsoft.com/intune/compliance-policy-create-google-play-protect) öğrenin.

### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Yönetilen Uygulamalar izin verilen metin protokolü <!-- 1414050  -->

Intune Uygulama SDK’sı tarafından yönetilen uygulamalar SMS mesajları gönderebilir.


### <a name="app-install-report-updated-to-include-install-pending-status----1249446---"></a>Uygulama yükleme raporu Yükleme Bekletiliyor durumunu içerecek şekilde güncelleştirildi <!-- 1249446 -->  

Her uygulama için **İstemci uygulamaları** iş yükünde **Uygulama** listesi üzerinden erişilebilen **Uygulama yükleme durumu** raporu, şimdi Kullanıcılar ve Cihazlar için **Yükleme Bekletiliyor** sayısını içeriyor.

### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>Mobil Tehdit Algılama için iOS 11 uygulama envanteri API’si<!-- 1391759 -->

Intune, kişisel ve kuruluşa ait cihazlardan uygulama envanter bilgilerini toplayarak Lookout for Work gibi Mobil Tehdit Algılama (MTD) sağlayıcıları için kullanılabilir hale getirir. iOS 11+ cihazlarının kullanıcılarından uygulama envanteri toplayabilirsiniz.

**Uygulama envanteri**  
Şirkete ait iOS 11+ ve kişisel cihazlar için envanterler MTD hizmet sağlayıcınıza gönderilir. Uygulama envanterindeki veriler şunları içerir:

 - Uygulama Kimliği
 - Uygulama Sürümü
 - Uygulama Kısa Sürümü
 - Uygulama Adı
 - Uygulama Paketi Boyutu
 - Uygulama Dinamik Boyutu
 - Uygulamanın doğrulanıp doğrulanmadığı
 - Uygulamanın yönetilip yönetilmediği

### <a name="migrate-hybrid-mdm-users-and-devices-to-intune-standalone----1463747-wnready---"></a>Karma MDM kullanıcıları ve cihazlarını tek başına Intune'a geçirme <!-- 1463747 wnready -->
Kullanıcıları ve onların cihazlarını karma MDM’den Azure Portal’daki Intune’a geçirmek için yeni süreçler ve araçlar artık kullanılabilir. Bunlar sayesinde aşağıdaki görevleri yapabilirsiniz:
- İlkeleri ve profilleri Configuration Manager konsolundan Azure Portal'daki Intune'a kopyalama
- Kullanıcıların bir alt kümesini Azure Portal'da Intune'a taşırken kalanlarını karma MDM'de bırakma
- Cihazları yeniden kaydetmeye gerek kalmadan Azure Portal'daki Intune'a geçirme

Ayrıntılar için bkz. [Karma MDM kullanıcıları ve cihazlarını tek başına Intune'a geçirme](https://docs.microsoft.com/sccm/mdm/deploy-use/migrate-hybridmdm-to-intunesa).

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Yüksek kullanılabilirlik desteği ile şirket içi Exchange bağlayıcısı <!-- 676614 -->
Exchange bağlayıcısı belirtilen CAS'yi kullanarak Exchange bağlantısı oluşturduktan sonra, bağlayıcı artık diğer CAS'leri bulabilir. Birincil CAS kullanılamaz duruma gelirse, birincil CAS kullanılabilir duruma gelene kadar varsa bağlayıcı başka bir CAS’ye yük devreder. Ayrıntılar için bkz. [Yüksek kullanılabilirlik desteği ile şirket içi Exchange bağlayıcısı](exchange-connector-install.md#on-premises-exchange-connector-high-availability-support).

### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>iOS cihazı uzaktan yeniden başlatma (yalnızca denetimli) <!-- 1424595 -->

Artık bir cihaz eylemi kullanarak, denetimli bir iOS 10.3+ cihazı yeniden başlatma için tetikleyebilirsiniz. Cihazı yeniden başlatma eylemini kullanma hakkında daha fazla bilgi için bkz. [Intune ile cihazları uzaktan yeniden başlatma](device-restart.md).

> [!Note]
> Bu komut, denetlenen cihazlar ve **Cihaz Kilidi** erişim hakkı gerektirir. Cihaz hemen yeniden başlatılır. Geçiş koduyla kilitli iOS cihazlar yeniden başlatmadan sonra bir Wi-Fi ağına yeniden katılmaz; yeniden başlatıldıktan sonra sunucu ile iletişim kuramayabilir.

### <a name="single-sign-on-support-for-ios----1333645---"></a>iOS için Çoklu Oturum Açma desteği <!-- 1333645 -->  

iOS kullanıcıları için Çoklu Oturum Açma kullanabilirsiniz. Çoklu Oturum Açma yükünde kullanıcı kimlik bilgilerini aramak için kodlanan iOS uygulamaları bu yük yapılandırması güncelleştirmesi ile işlevseldir. Asıl Ad ve Bölgeyi yapılandırmak için UPN ve Intune Cihaz Kimliğini de kullanabilirsiniz. Ayrıntılar için bkz. [Intune'u iOS cihazında çoklu oturum açma için yapılandırma](sso-ios.md).

### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Kişisel cihazlar için "iPhone’umu Bul" özelliği ekleme <!--1427287-->
Artık iOS cihazlarda Etkinleştirme Kilidi’nin açık olup olmadığını görüntüleyebilirsiniz. Bu özellik önceden Intune’da klasik portalda bulunuyordu.

### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Intune ile yönetilen macOS cihazları uzaktan kilitleme <!-- 1437691 -->

Kayıp bir macOS cihazı kilitleyebilir ve 6 basamaklı bir kurtarma PIN’i ayarlayabilirsiniz. Kilitliyken, **Cihaza genel bakış** dikey penceresi başka bir cihaz eylemi gönderilene kadar PIN’i görüntüler.

Daha fazla bilgi için bkz. [Intune ile yönetilen cihazları uzaktan kilitleme](device-remote-lock.md).

### <a name="new-scep-profile-details-supported----1559808---"></a>Desteklenen yeni SCEP profili ayrıntıları <!-- 1559808 -->

Yöneticiler artık Windows, iOS, macOS ve Android platformlarında SCEP profili oluştururken ek ayarlar yapabilir.  Yöneticiler IMEI, seri numarası veya konu adı biçiminde e-posta dahil ortak ad ayarlayabilir.

<!-- #### Update to what device details your company may see -1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources. -->

### <a name="retain-data-during-a-factory-reset----1588489---"></a>Fabrika sıfırlaması sırasında verileri tutma <!--1588489 -->
Windows 10 sürüm 1709 ve üstünü fabrika ayarlarına sıfırlarken, yeni bir özellik sağlanır. Yöneticiler fabrika sıfırlaması sırasında cihaz kaydı ve diğer sağlanan verilerin cihazda tutulup tutulmayacağını belirtebilir.

Fabrika sıfırlamasında aşağıdaki veriler tutulur:
- Cihazla ilişkilendirilen kullanıcı hesapları
- Makine durumu (etki alanına katılım, Azure Active Directory’ye katılım)
- MDM kaydı
- OEM tarafından yüklenen uygulamalar (mağaza ve Win32 uygulamaları)
- Kullanıcı profili
- Kullanıcı profili dışındaki kullanıcı verileri
- Kullanıcı otomatik oturum açma

Şu veriler korunmaz:
- Kullanıcı dosyaları
- Kullanıcı tarafından yüklenen uygulamalar (mağaza ve Win32 uygulamaları)
- Varsayılan olmayan cihaz ayarları


### <a name="window-10-update-ring-assignments-are-displayed----1621837---"></a>Windows 10 güncelleştirme halkası atamaları görüntülenir <!-- 1621837 -->
**Sorun giderirken**, görüntülediğiniz kullanıcı için Windows 10 güncelleştirme halkası atamalarını görebilirsiniz.  

### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings-----1455974----"></a>Windows Defender Gelişmiş Tehdit Koruması raporlama sıklığı ayarları <!-- 1455974  -->
Windows Defender Gelişmiş Tehdit Koruması (WDATP) hizmeti yöneticilerin yönetilen cihazlar için raporlama sıklığını yönetmesine olanak sağlar. Yeni **Telemetri raporlama sıklığını hızlandır** seçeneğiyle, WDATP daha sık veri toplar ve riskleri değerlendirir. Raporlama için varsayılan ayar, hızı ve performansı en iyi duruma getirir. Raporlama sıklığını artırmak yüksek riskli cihazlar için yararlı olabilir. Bu ayar, **Cihaz yapılandırmaları** içinde **Windows Defender ATP** profilinde bulunabilir.

### <a name="audit-updates----1412961---"></a>Güncelleştirmeleri denetleme <!-- 1412961 -->  
Intune denetimi, Intune’la ilgili değişiklik işlemlerinin bir kaydını sağlar.  Tüm oluşturma, güncelleştirme, silme ve uzak görev işlemleri yakalanır ve bir yıl süreyle tutulur.  Azure portalı her iş yükü içinde son 30 günlük denetim verilerinin bir görünümünü sağlar ve bunlar filtrelenebilir.  Karşılık gelen bir Graph API, geçen yıl için depolanan denetim verilerinin alınmasına olanak sağlar.

Denetim **İZLEYİCİ** grubu altında bulunur. Her bir iş yükü için bir **Denetim Günlükleri** menü öğesi bulunur.

### <a name="company-portal-app-for-macos-is-available---1541700--"></a>Şirket Portalı uygulaması macOS için kullanılabilir <!--1541700-->
MacOS'daki Intune Şirketi Portalı, kayıtlı oldukları tüm cihazlar için kullanıcılarınıza gereken tüm bilgileri ve uyum bildirimlerini temiz bir şekilde görüntülemek için iyileştirilmiş güncel bir tecrübeye sahiptir. Ve Intune Şirketi Portalı bir cihaza dağıtıldığında, macOS için Microsoft AutoUpdate kendisine güncelleme sağlayacaktır. Yeni macOS için Intune Şirket Portalı’nı, bir macOS cihazından Intune Şirketi Portalı web sitesine girerek indirebilirsiniz.

### <a name="microsoft-planner-is-now-part-of-the-mobile-app-management-mam-list-of-approved-apps-----1248473---"></a>Microsoft Planner, artık mobil uygulama yönetimi (MAM) onaylı uygulamalar listesinin bir parçasıdır <!-- 1248473 -->
IOS ve Android için Microsoft Planner uygulaması artık mobil uygulama yönetimi (MAM) için onaylanan uygulamaların bir parçasıdır. Uygulama, tüm kiracılara Azure portalındaki Intune App Protection dikey penceresi aracılığıyla yapılandırılabilir.
- [Onaylı uygulamaların MAM listesi](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) hakkında daha fazla bilgi edin.

### <a name="per-app-vpn-requirement-update-frequency-on-ios-devices------1547061---"></a>IOS cihazlarında Uygulama Başına VPN gereksinimi güncelleştirme sıklığı <!-- 1547061 -->  
Yöneticiler, artık iOS cihazlarındaki uygulamalar için Uygulama Başına VPN gereksinimlerini kaldırabilir; etkilenen cihazlar genellikle bir sonraki Intune iade etme işleminden sonra olacak ve bu da genellikle 15 dakika içinde gerçekleşecektir.  

### <a name="support-for-system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Exchange Bağlayıcı için System Center Operations Manager yönetim paketi desteği <!-- 885457 -->
Exchange bağlayıcı için Sistem Merkezi İşlemleri Yöneticisi (SCOM) yönetim paketi, Exchange bağlayıcı günlüklerini ayrıştırmanıza yardımcı olmak için kullanılabilir. Bu özellik, sorun gidermeniz gerektiğinde Exchange bağlayıcıyı izlemek için size farklı yollar sunar.

### <a name="co-management-for-windows-10-devices-----1243445---"></a>Windows 10 cihazlar için ortak yönetim <!-- 1243445 -->
Ortak yönetim, geleneksel yönetimden modern yönetime bir köprü sağlar ve aşamalı bir yaklaşım ile bu geçişi yapmanızı sağlayan bir yol sunar. Ortak yönetim temelde Windows 10 cihazların, Configuration Manager ve Microsoft Intune tarafından eş zamanlı olarak yönetildiği ve Active Directory (AD) ile Azure Active Directory’ye (Azure AD) katıldığı bir çözümdür.  Bu yapılandırma size, her şeyi aynı anda taşıyamadığınız durumlarda kuruluşunuza uygun bir tempoda zaman içinde modernleştireceğiniz bir yol sunar.  

### <a name="restrict-windows-enrollment-by-os-version----245498---"></a>Windows Kaydını işletim sistemi sürümüyle kısıtlama <!-- 245498 -->
Bir Intune yöneticisi olarak cihaz kayıtları için Windows 10 en düşük ve en yüksek sürümleri belirtebilirsiniz. Bu kısıtlamaları, **Platform Yapılandırmaları** dikey penceresinde ayarlayabilirsiniz.

Intune, Windows 8.1 bilgisayarlar ve telefonların kaydını desteklemeye devam edecektir. Ancak yalnızca Windows 10 sürümleri için en düşük ve en yüksek sınırlar ayarlanabilir. 8.1 cihazların kaydına izin vermek için en düşük sınırı boş bırakın.

### <a name="alerts-for-windows-autopilot-unassigned-devices-----1631236---"></a>Windows AutoPilot’ta atanmamış cihazlar için uyarılar  <!-- 1631236 -->
**Microsoft Intune** > **Cihaz kaydı** > **Genel bakış** sayfasında Windows AutoPilot atanmamış cihazlar için yeni bir uyarı mevcut. Bu uyarı, AutoPilot programından kaç tane cihaza AutoPilot dağıtım profili atanmamış olduğunu gösterir. Uyarıdaki bilgileri kullanarak profiller oluşturun ve bunları profil atanmamış cihazlara atayın. Uyarıya tıkladığınızda, Windows AutoPilot cihazların tam listesini ve cihazlar hakkında ayrıntılı bilgileri görürsünüz. Daha fazla bilgi için bkz. [Windows AutoPilot dağıtım programını kullanarak Windows cihazları kaydetme](https://docs.microsoft.com/intune/enrollment-autopilot).


### <a name="refresh-button-for-devices-list-------1333581---"></a>Cihazlar listesi için Yenile düğmesi    <!-- 1333581 -->
Cihazlar listesi otomatik olarak yenilenmediği için, yeni Yenile düğmesini kullanarak listede görüntülenen cihazları güncelleyebilirsiniz.

### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Symantec Cloud Sertifika Yetkilisi (CA) desteği <!-- 1333638 -->    
Intune artık Symantec Cloud CA’yı desteklemektedir. Böylece Intune Sertifika Bağlayıcısı, Symantec Cloud’dan Intune ile yönetilen cihazlara PKCS sertifikaları verebilir. Intune Sertifika Bağlayıcısı’nı Microsoft Sertifika Yetkilisi (CA) ile kullanıyorsanız, Symantec CA desteğini eklemesi için mevcut Intune Sertifika Bağlayıcısı kurulumunu kullanabilirsiniz.

### <a name="new-items-added-to-device-inventory-----1404455---"></a>Cihaz envanterine yeni öğeler eklendi   <!--1404455 -->
[Kayıtlı cihazların aldığı envanterde](device-inventory.md) artık aşağıdaki yeni öğeler kullanılabilir:

- WIFI Mac adresi
- Toplam depolama alanı
- Toplam boş alanı
- MEID
- Abone operatör

### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Uygulamalara erişimi cihazdaki en düşük Android güvenlik düzeltme ekine göre ayarlama<!-- 1278463 -->   
Yönetici, yönetilen bir hesap altındaki yönetilen bir uygulamaya erişim kazanmak için cihazda yüklü olması gereken en düşük Android güvenlik düzeltme ekini belirleyebilir.

> [!Note]  
> Bu özellik, yalnızca Android 6.0+ cihazlarda Google tarafından yayınlanan düzeltme eklerini kısıtlar.

### <a name="app-conditional-launch-support----1193313---"></a>Uygulama koşullu başlatma desteği <!-- 1193313 -->
Artık BT yöneticileri, uygulama başlatıldığında mobil uygulama yönetiminde (MAM) sayısal PIN yerine bir geçiş kodu kullanılmasını zorlamak için Azure yönetici portalında bir gereksinim ayarlayabilir. Bu gereksinim ayarlanırsa kullanıcının, MAM etkin uygulamalara erişim almadan önce bir geçiş kodu ayarlaması ve istendiğinde bunu kullanması gerekir. Geçiş kodu, en az bir özel karakter veya büyük/küçük harf içeren sayısal PIN’dir. Intune’un bu sürümünde bu özellik, **yalnızca iOS’ta** geçerli olacaktır. Intune, sayısal PIN’e benzer bir geçiş kodunu destekler, uzunluk alt sınırı belirler ve karakter ile dizi tekrarlarına izin verir. Bu özellik, Intune App SDK'yi hedef kod uygulamalarında uygulanacak parola ayarlarının yapılması için bu özelliğe ait kodla tümleştirmek için uygulamaların (WXP, Outlook, Managed Browser, Yammer) katılımını gerektirir.

### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>Cihaz yükleme durum raporunda iş kolu için Uygulama Sürüm numarası <!-- 1233999 -->
Bu sürümle birlikte cihaz yükleme durum raporu, iOS ve Android için iş kolu uygulamalarında uygulama sürüm numarasını görüntüler. Bu bilgiyi kullanarak uygulamalarınızda sorun giderebilir veya eski uygulama sürümleri çalıştıran cihazları bulabilirsiniz.

### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Yöneticiler artık bir cihazda cihaz yapılandırma profili kullanarak Güvenlik Duvarı ayarlarını yapılandırabilir <!-- 951708 -->   
Yöneticiler, cihazlar için güvenlik duvarını etkinleştirebilir ve etki alanı, özel ve ortak ağlar için çeşitli protokoller yapılandırabilir.  Bu güvenlik duvarı ayarlarını “Uç nokta koruma” profilinde bulabilirsiniz.

### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>Windows Defender Application Guard, cihazları kuruluşunuz tarafından belirlenen güvenilmeyen web sitelerinden korumaya yardımcı olur <!-- 958257 -->   
Yöneticiler, bir Windows Bilgi Koruması iş akışını veya cihaz yapılandırmaları altındaki yeni “Ağ sınırı” profilini kullanarak siteleri “güvenilir” veya “kurumsal” olarak tanımlayabilir. Bir 64 bit Windows 10 cihazın güvenilir ağ sınırında listelenmemiş tüm siteler, Microsoft Edge ile görüntülenmeleri durumunda bir Hyper-V sanal bilgisayarındaki tarayıcıda açılır.

Application Guard’ı, “Uç nokta koruma” profilindeki cihaz yapılandırma profillerinde bulabilirsiniz. Yöneticiler buradan, sanallaştırılmış tarayıcı ile konak makine, güvenilmeyen siteler ile güvenilir siteler ve sanallaştırılmış tarayıcıda oluşturulan verileri depolama arasındaki etkileşimi yapılandırabilir. Bir cihazda Application Guard’ı kullanmak için önce bir ağ sınırı yapılandırılmalıdır. Bir cihaz için yalnızca bir ağ sınırı tanımlamak önemlidir.  

### <a name="windows-defender-application-control-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>Windows 10 Enterprise’da Windows Defender Uygulama Denetimi, yalnızca yetkilendirilmiş uygulamalara güvenme modu sağlar <!-- 1031096 -->    
Her gün oluşturulan binlerce yeni kötü amaçlı dosya karşısında virüsten koruma imza tabanlı algılama kullanmak artık yeni saldırılara karşı yeterli korumayı sağlayamıyor. Windows 10 Enterprise’da Windows Defender Uygulama Denetimi'ni kullanarak cihaz yapılandırmasını, uygulamaların bir virüsten koruma veya başka bir güvenlik çözümü tarafından engellenmediği durumda güvenilir olduğu bir moddan, işletim sisteminin yalnızca kuruluşunuzun yetkilendirdiği güvenilir uygulamalara güvendiği bir moda değiştirebilirsiniz. Uygulamalara güveni Windows Defender Uygulama Denetimi'nde atarsınız.

Intune kullanarak uygulama denetleme ilkelerini “yalnızca denetim” modunda veya zorlama modunda yapılandırabilirsiniz. Uygulamalar, “yalnızca denetim” modunda çalıştırıldığında engellenmez. “Yalnızca denetim” modu, tüm olayları yerel istemci günlüklerine kaydeder. Ayrıca, yalnızca Windows bileşenleri ve Microsoft Mağazası uygulamalarının mı yoksa Intelligent Security Graph tarafından tanımlanan diğer itibarlı uygulamaların da mı çalışmaya izni olacağını yapılandırabilirsiniz.

### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>Windows Defender Exploit Guard, Windows 10 için yeni bir yetkisiz erişim önleme işlevleri dizisi <!-- 1063615 -->   
Windows Defender Exploit Guard; uygulamaların kötüye kullanımını azaltacak özel kurallar içerir, makro ve betik tehditlerini önler, düşük itibarlı IP adreslerine yapılan ağ bağlantılarını otomatik olarak önler ve fidye yazılımı ile bilinmeyen tehditlere karşı verileri korur. Windows Defender Exploit Guard aşağıdaki bileşenlerden oluşur:

- **Saldırı Yüzeyi Azaltma (ASR)** makro, betik ve e-posta tehditlerini önlemenize yardımcı kurallar sağlar.
- **Denetimli Klasör erişimi** korumalı klasörlerin içeriklerine erişimi otomatik olarak engeller.
- **Ağ Filtresi** herhangi bir uygulamanın düşük itibarlı bir IP/etki alanına bağlantı yapmasını engeller
- **Exploit Protection** bir uygulamanın kötüye kullanılmasını önlemek üzere kullanılabilecek bellek, denetim akışı ve ilke kısıtlamaları sağlar.

### <a name="manage-powershell-scripts-in-intune-for-windows-10-devices----790537---"></a>Windows 10 cihazlar için Intune’da PowerShell betiklerini yönetme <!-- 790537 -->

Intune yönetim uzantısı, Intune’da PowerShell betiklerini Windows 10 cihazlarda çalıştırmak için karşıya yüklemenize olanak sağlar. Uzantı, Windows 10 mobil cihaz yönetimi (MDM) özelliklerini tamamlar ve modern yönetime geçiş yapmanızı kolaylaştırır. Ayrıntılar için bkz. [Windows 10 cihazlar için Intune’da PowerShell betiklerini yönetme](intune-management-extension.md).

### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Windows 10 için yeni cihaz kısıtlama ayarları      <!-- 1308850 -->
-    Mesajlaşma (yalnızca mobil) - sınamayı ve MMS iletilerini devre dışı bırakır
-    Parola - FIPS’yi ve kimlik doğrulaması için ikincil Windows Hello cihazların kullanımını etkinleştirme ayarları 
-    Görüntü - eski uygulamalar için GDI Ölçeklendirmeyi açma ve kapama ayarları

### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Windows 10 bilgi noktası modu cihaz kısıtlamaları <!-- 1308872 -->   
Windows 10 cihaz kullanıcılarını bilgi noktası moduna kısıtlayabilirsiniz, böylece kullanıcılar önceden tanımlı bir uygulamalar dizisiyle sınırlanır.  Bunun için bir Windows 10 cihaz kısıtlama profili oluşturun ve Bilgi Noktası ayarlarını ayarlayın.

Bilgi noktası modu şu iki modu destekler: **tek uygulama** (kullanıcının yalnızca bir uygulama çalıştırmasına izin verir) veya **çok uygulama** (bir dizi uygulamaya erişme izni verir).  Kullanıcı hesabı ve cihaz adını siz belirlersiniz, böylece desteklenen uygulamalar belirlenir.  Kullanıcı oturum açtığında belirlenen uygulamalarla sınırlı olur.  Daha fazla bilgi için bkz. [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp). 

Bilgi noktası modu şunları gerektirir:

- MDM yetkilisi Intune olmalıdır.
- Uygulamalar hedef cihazda yüklü olmalıdır.
- Cihaz [doğru bir şekilde sağlanmalıdır](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions).

### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Ağ sınırları oluşturmak için yeni cihaz yapılandırma profili <!-- 1311967 -->   
**Ağ sınırı** adı verilen yeni cihaz yapılandırma profilini diğer cihaz yapılandırma profillerinizin yanında bulabilirsiniz. Bu profili kullanarak kurumsal ve güvenilir olarak değerlendirilmesini istediğiniz çevrimiçi kaynakları tanımlayabilirsiniz. Windows Defender Application Guard ve Windows Bilgi Koruması gibi özelliklerin cihazda kullanılabilmesi için *önce* bir ağ sınırı tanımlamanız gerekir. Her cihaz için yalnızca bir ağ sınırı tanımlamanız önemlidir.

Güvenilir olarak değerlendirilmesini istediğiniz kuruluş bulut kaynakları, IP adresi aralıkları ve dahili proxy sunucularını tanımlayabilirsiniz. Tanımlandıktan sonra bu ağ sınırı, Windows Defender Application Guard ve Windows Bilgi Koruması gibi diğer özellikler tarafından kullanılır.

###  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Windows Defender Virüsten Koruma için iki ek ayar <!-- 1338409 -->  
**Dosya engelleme düzeyi**

| | |
|---|---|
| Yapılandırılmadı | **Yapılandırılmadı**, varsayılan Windows Defender Virüsten Koruma engelleme düzeyini kullanır ve güvenli klasörleri algılama riskini artırmadan güçlü bir algılama sağlar. |
| Yüksek | **Yüksek** güçlü bir algılama düzeyi sağlar.
| Yüksek +  | **Yüksek +** Yüksek düzeyine istemci performansını etkileyebilecek ek koruma önlemleri getirir.
| Sıfır tolerans  | **Sıfır tolerans** tüm bilinmeyen yürütülebilir dosyaları engeller. |

**Yüksek** düzeyini ayarlamak, düşük ihtimalle de olsa bazı güvenli dosyaların algılanmasına yol açabilir.
Dosya engelleme düzeyini varsayılan **Yapılandırmadı** düzeyine ayarlamanızı öneririz.

**Bulut tarafından dosya tarama için zaman aşımı uzantısı**  

| | |
|--|--|
| Saniye sayısı (0-50) | Windows Defender Virüsten Koruma’nın buluttan sonuç beklerken bir klasörü engellemesi için geçmesi gereken en uzun süreyi belirtin. Varsayılan süre 10 saniyedir: burada belirtilen ek süre (en fazla 50 saniyeye kadar) bu 10 saniyenin üzerine eklenir. Çoğu zaman tarama, belirtilen en uzun süreden daha kısa zamanda biter. Bu süreyi artırmak, bulutun şüpheli klasörleri ayrıntılı olarak araştırmasına olanak verir. Bu ayarı etkinleştirip fazladan en az 20 saniye belirtmenizi öneririz. |

### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Windows 10 cihazlar için Citrix VPN eklendi <!-- 1512457 -->  
Windows 10 cihazlar için Citrix VPN’i yapılandırabilirsiniz. Windows 10 ve üzeri sürümler için bir VPN yapılandırırken, **Temel VPN** dikey penceresinde bulunan *Bağlantı türü seçin* listesinden Citrix VPN’i seçebilirsiniz.

> [!Note]
> Citrix yapılandırması iOS ve Android için zaten mevcuttu.

### <a name="wi-fi-connections-support-pre-shared-keys-on-ios----1550823---"></a>Wi-Fi bağlantıları iOS’ta önceden paylaşılan anahtarları destekliyor <!-- 1550823 -->
Müşteriler, Wi-Fi profillerini, iOS cihazlarda WPA/WPA2 Kişisel bağlantıları için önceden paylaşılan anahtarları (PSK) kullanacak şekilde yapılandırabilirler. Bu profiller, kullanıcının cihazı Intune’a kaydedildiğinde cihaza gönderilir.

Profil cihaza gönderildikten sonraki adım, profil yapılandırmasına bağlıdır.  Otomatik olarak bağlanmaya ayarlıysa, ağa ihtiyaç olduğunda otomatik olarak bağlanır.  Profil el ile bağlanıyorsa, kullanıcı bağlantıyı el ile etkinleştirmelidir.  

### <a name="access-to-managed-app-logs-for-ios----1469920---"></a>iOS için yönetilen uygulama günlüklerine erişim <!-- 1469920 -->
Managed Browser yüklü olan son kullanıcılar artık tüm Microsoft uygulamalarının yönetim durumunu görüntüleyebilir ve yönetilen iOS uygulamalarında sorun giderme için günlük gönderebilirler.

Bir iOS cihaz üzerinde Managed Browser’da sorun giderme modunu nasıl etkinleştireceğini öğrenmek için bkz. [iOS’a Managed Browser kullanarak yönetilen uygulama günlüklerine erişme](app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios).

### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290----1417174---"></a>Sürüm 2.9.0'da iOS için Şirket Portalı'nda cihaz kurulum iş akışındaki iyileştirmeler <!-- 1417174 -->

iOS için Şirket Portalı uygulamasında cihaz kurulum iş akışı geliştirildi. Dil artık daha kullanıcı dostu ve mümkün olan yerlerde ekranları birleştirdik. Kurulum metninde şirket adınızın kullanılmasıyla diliniz, firmanıza özel hale geldi. Bu güncelleştirilmiş iş akışını  [Uygulama UI sayfasındaki yenilikler](whats-new-app-ui.md) sayfasında görebilirsiniz.


### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>Kullanıcı varlığı Veri Ambarı veri modelinde en son kullanıcı verilerini içeriyor <!-- 1544273 -->
Intune Veri Ambarı eri modelinin ilk sürümü yalnızca son geçmiş Intune verilerini içeriyordu. Rapor oluşturucular bir kullanıcının geçerli durumunu yakalayamadı. Bu güncelleştirmede, **Kullanıcı varlığı** en son kullanıcı verileriyle doldurulur.


## <a name="october-2017"></a>Ekim 2017

### <a name="ios-and-android-line-of-business-app-version-number-is-visible----1380712---"></a>iOS ve Android iş kolu uygulaması sürüm numarası görünürdür <!-- 1380712 -->

Intune’da uygulamalar artık iOS ve Android iş kolu uygulamaları için sürüm numarasını görüntüler. Numara, Azure portalındaki uygulama listesinde ve uygulama genel bakış dikey penceresinde görüntülenir. Son kullanıcılar, uygulama numarasını Şirket Portalı uygulamasında ve web portalında görebilir.

__Tam sürüm numarası__ Tam sürüm numarası, uygulamanın belirli bir sürümünü tanımlar. Numara _Sürüm_(_Derleme_) olarak görünür. Örneğin, 2.2(2.2.17560800)

Tam sürüm numarası iki bileşenden oluşur:

 - **Sürüm**  
   Sürüm numarası uygulamanın insan tarafından okunabilir yayın numarasıdır. Bu, son kullanıcılar tarafından uygulamanın farklı yayınlarını tanımlamak için kullanılır.

 - **Derleme Numarası**  
    Derleme numarası, uygulama algılamada ve uygulamayı programlı olarak yönetmek için kullanılabilen dahili bir numaradır. Derleme numarası, uygulamanın koddaki değişikliklere başvuran bir yinelemesini ifade eder.

[Microsoft Intune Uygulama SDK’sını kullanmaya başlama](app-sdk-get-started.md#line-of-business-app-version-numbers) içinde sürüm numaraları ve iş kolu uygulamaları geliştirme hakkında daha fazla bilgi edinin.

### <a name="device-and-app-management-integration----677972---"></a>Cihaz ve uygulama yönetim tümleştirmesi <!-- 677972 -->   
Artık Intune’un mobil cihaz yönetimi (MDM) ve mobil uygulama yönetimi (MAM) işlevleri Azure portalından erişilebilir olduğu için Intune, uygulama ve cihaz yönetiminde BT yönetici deneyimini tümleştirmeye başladı. Bu değişikliklerin amacı, cihaz ve uygulama yönetimi deneyiminizi kolaylaştırmaktır.

[Intune destek ekibi blogundan](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/) MDM ve MAM değişiklikleri hakkında daha fazla bilgi edinebilirsiniz.

### <a name="new-enrollment-alerts-for-apple-devices----1471790---"></a>Apple cihazları için yeni kayıt uyarıları <!-- 1471790 -->
Kayıt için genel bakış sayfası, BT yöneticileri için Apple cihazlarının yönetimiyle ilgili kullanışlı uyarılar gösterir. Uyarılar, Apple MDM anında iletme sertifikasının süresi neredeyse dolduğunda veya dolduğunda; Aygıt Kayıt Programı belirtecinin süresi neredeyse dolduğunda veya dolduğunda ve Aygıt Kayıt Programında atanmamış cihazlar olduğunda Genel Bakış sayfasında görüntülenir.

### <a name="support-token-replacement-for-app-configuration-without-device-enrollment----1080364---"></a>Cihaz kaydı olmadan uygulama yapılandırması için belirteç değiştirme desteği <!-- 1080364 -->

Kayıtlı olmayan cihazlardaki uygulamaların uygulama yapılandırmalarında dinamik değerler için belirteçleri kullanabilirsiniz. Daha fazla bilgi için bkz. [Cihaz kaydı olmadan yönetilen uygulamalar için uygulama yapılandırma ilkeleri ekleme](app-configuration-policies-managed-app.md).

### <a name="updates-to-the-company-portal-app-for-windows-10---1299474--"></a>Windows 10 için Şirket Portalı uygulamasındaki güncelleştirmeler <!--1299474-->
Windows 10 için Şirketi Portalı uygulamasındaki Ayarlar sayfası, ayarların ve amaçlanan kullanıcı işlemlerinin tüm ayarlarda daha tutarlı olmasını sağlamak için güncelleştirildi. Ayrıca, diğer Windows uygulamalarının düzeniyle eşleşecek şekilde güncelleştirildi. Önce/sonra resimlerini [Uygulama UI'sındaki yenilikler](whats-new-app-ui.md) sayfasında bulabilirsiniz.

### <a name="inform-end-users-what-device-information-can-be-seen-for-windows-10-devices---1337920--"></a>Son kullanıcılara Windows 10 cihazlarında hangi cihaz bilgisinin görülebileceğini bildirin <!--1337920-->
Windows 10 için Şirket Portalı uygulamasındaki Cihaz Ayrıntıları ekranına **Sahiplik Türü** ekledik. Bu, kullanıcıların doğrudan bu sayfadaki Intune son kullanıcı belgelerinden gizlilik hakkında daha fazla bilgi edinmesini sağlar. Ayrıca, bu bilgileri **Hakkında** ekranında bulabilecekler.

### <a name="feedback-prompts-for-the-company-portal-app-for-android---1165249--"></a>Android için Şirket Portalı uygulaması için geri bildirim istekleri <!--1165249-->
Android için Şirket Portalı uygulaması şimdi son kullanıcı geri bildirimi istiyor. Bu geri bildirim doğrudan Microsoft’a gönderilir ve son kullanıcılara uygulamayı genel Google Play Store’da gözden geçirme olanağı tanır. Geri bildirim gerekli değildir ve kullanıcılar, uygulamayı kullanmaya devam edebilmesi için kolayca kapatılabilir.

<!-- #### Update to what device details an organization can see 1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources.-->

### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Kullanıcılarınızın Android için Şirket Portalı uygulamasını kullanmasına yardımcı olma <!-- 1573324, 1573150, 1558616, 1564878 -->

Android için Şirket Portalı uygulaması, son kullanıcıların yeni kullanım durumlarını anlamaları ve mümkün olduğunda kendi kendilerine çözümlemeleri için yönergeler ekledi.
- Son kullanıcılar ekleyebilecekleri en fazla cihaz sayısına ulaştıysa bir cihazı kaldırmak üzere [Azure Active Directory portalına](https://account.activedirectory.windowsazure.com/r/#/profile) yönlendirilir.
- Son kullanıcılara [Samsung Knox cihazlarında etkinleştirme hatalarını düzeltmek](https://go.microsoft.com/fwlink/?linkid=859718) veya [güç tasarrufu modunu devre dışı bırakmak](/intune-user-help/power-saving-mode-android) için izlenecek adımlar verilir. Bu çözümlerden biri sorunları çözmezse [günlükleri Microsoft’a göndermeye](/intune-user-help/send-logs-to-microsoft-android) yönelik bir açıklama sağlarız.

### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>Android cihazlar için yeni 'Çözümleme' eylemi kullanılabilir <!-- 1583480 -->

Android için Şirket Portalı uygulaması _Cihaz ayarlarını güncelleştirme_ sayfasında bir 'Çözümleme' eylemi tanıtıyor. Bu seçeneği belirlemek son kullanıcıyı doğrudan cihazlarının uyumsuz olmasına neden olan ayara götürür. Android için Şirket Portalı uygulaması şu anda bu eylemi [cihaz geçiş kodu](/intune-user-help/set-your-pin-or-password-android), [USB hata ayıklama](/intune-user-help/you-need-to-turn-off-usb-debugging-android) ve [Bilinmeyen Kaynaklar](/intune-user-help/you-need-to-turn-off-unknown-sources-android) ayarları için destekler.

### <a name="device-setup-progress-indicator-in-android-company-portal----1565657---"></a>Android Şirket Portalı uygulamasında cihaz kurulumu ilerleme göstergesi <!-- 1565657 -->
Android için Şirket Portalı uygulaması, bir kullanıcı cihazını kaydettiğinde bir cihaz kurulumu ilerleme göstergesi gösterir. Gösterge, "Cihazınız ayarlanıyor...", ardından "Cihazınız kaydediliyor...", ardından "Cihazınızı kaydetme tamamlanıyor..." ve daha sonra "Cihaz kurulumu tamamlanıyor..." ile başlayan yeni durumlar gösterir.

### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>iOS için Şirket Portalı’nda sertifika tabanlı kimlik doğrulaması desteği <!--1029830-->
iOS için Şirket Portalı’na sertifika tabanlı kimlik doğrulaması (CBA) desteği ekledik. CBA kullanan kullanıcılar kullanıcı adını girer ve “Bir sertifika ile oturum aç” bağlantısına dokunur. CBA, Android ve Windows için Şirket Portalı’nda zaten destekleniyordu. [Şirket Portalı uygulamasında oturum açma](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal) sayfasından daha fazla bilgi edinebilirsiniz.

### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Kayıt durumuna bakılmaksızın kullanılabilir olan uygulamalar artık kayıt istemi yapılmadan yüklenebilir. <!-- 1334712 -->

Android Şirket Portalı uygulamasındaki kayıt durumuna bakılmaksızın kullanılabilir olan şirket uygulamaları, artık kayıt için istem yapılmadan yüklenebilir.

### <a name="windows-autopilot-deployment-program-support-in-microsoft-intune-----747617----"></a>Microsoft Intune’da Windows AutoPilot Dağıtım Programı desteği  <!-- 747617  -->
Artık Microsoft Intune’u Windows AutoPilot Dağıtım Programı ile birlikte kullanarak, BT birimine gerek kalmaksızın kullanıcılarınıza şirket cihazları sağlayabilirsiniz. İlk kez çalıştırma deneyimini (OOBE) özelleştirebilir ve kullanıcılarınızın cihazlarını Azure AD’ye katarak Intune’a kaydetmesi için yol gösterebilirsiniz. Microsoft Intune ve Windows AutoPilot birlikte çalıştığında işletim sistemi görüntülerinin dağıtım, bakım ve yönetim ihtiyacını ortadan kaldırır. Ayrıntılar için bkz. [Windows AutoPilot Dağıtım Programını kullanarak Windows cihazları kaydetme](https://docs.microsoft.com/intune/enrollment-autopilot).

### <a name="quick-start-for-device-enrollment-----1425655---"></a>Cihaz kaydı için hızlı başlangıç  <!-- 1425655 --> 
**Cihaz kaydı** için artık hızlı başlangıç kullanılabilir. Hızlı başlangıç, platformları yönetmek ve kayıt işlemini yapılandırmak için bir başvuru tablosu sağlar. Her bir öğenin kısa açıklaması ve adım adım yönergeler içeren belgelere bağlantılar, başlangıcı basitleştirmek için kullanışlı belgeler sağlar.

### <a name="device-categorization----1427491---"></a>Cihaz kategorilendirme <!-- 1427491 -->
**Cihazlar > Genel Bakış** dikey penceresinde bulunan kayıtlı cihazlar platform grafiği cihazları Android, iOS, macOS, Windows ve Windows Mobile platformlarına göre düzenler.  Diğer işletim sistemlerini çalıştıran cihazlar “Diğer” başlığı altında toplanır.  Bu cihazlar arasında Blackberry, NOKIA ve diğerleri tarafından üretilen cihazlar vardır.  

Kiracınızda hangi cihazların etkilendiğini öğrenmek için **Yönet > Tüm cihazları**’ı seçin ve **Filtrele**’yi kullanarak **İşletim Sistemi** alanını sınırlayın.

### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium - Yeni Mobile Threat Defense iş ortağı  <!-- 954681 -->  
Microsoft Intune ile tümleşen Mobil Tehdit Savunması çözümü olan Zimperium tarafından yapılan risk değerlendirmesine göre koşullu erişim kullanarak mobil cihazlardan şirket kaynaklarına erişimi denetleyebilirsiniz.

#### <a name="how-integration-with-intune-works"></a>Intune ile tümleştirme nasıl çalışır?
Risk, Zimperium çalıştıran cihazlardan toplanan telemetriye göre değerlendirilir. Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen Zimperium risk değerlendirmesine dayalı EMS koşullu erişim ilkelerini yapılandırabilirsiniz. Algılanan tehditler temelinde, uyumlu olmayan cihazların şirket kaynaklarına erişmesine izin vermek veya erişimini engellemek için bu ilkeleri kullanabilirsiniz.

### <a name="new-settings-for-windows-10-device-restriction-profile------978575-1308849---"></a>Windows 10 cihaz kısıtlama profili için yeni ayarlar  <!--- 978575, 1308849, -->  
Windows Defender SmartScreen kategorisinde Windows 10 cihaz kısıtlama profiline yeni ayarlar ekliyoruz.

Windows 10 cihaz kısıtlama profili hakkında ayrıntılar için bkz. [Windows 10 ve üzeri cihaz kısıtlama ayarları]( device-restrictions-windows-10.md).

### <a name="remote-support-for-windows-and-windows-mobile-devices------1070473---"></a>Windows ve Windows Mobile cihazlar için uzak destek  <!-- 1070473 -->  
Artık Intune, Windows ve Windows Mobile cihazlar çalıştıran kullanıcılarınıza uzaktan yardım etmenizi sağlamak için ayrıca satın alınan [TeamViewer](https://www.teamviewer.com) yazılımını kullanabilir.

### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Windows Defender ile cihazları tarama <!-- 1280988  1280990   -->
Artık yönetilen Windows 10 cihazlarda Windows Defender Virüsten Koruma ile **Hızlı Tarama**, **Tam Tarama** ve **İmza güncelleştirme** işlemlerini gerçekleştirebilirsiniz. Cihazın genel bakış dikey penceresinden cihazda çalıştırılacak eylemi seçin. Komut cihaza gönderilmeden önce eylemi onaylamanız istenir. 

**Hızlı tarama**: Hızlı tarama, kayıt defteri anahtarı ve bilinen Windows başlangıç klasörleri gibi kötü amaçlı yazılımların başladığı konumları tarar. Bir hızlı tarama ortalama beş dakika sürer. Bir dosya açıldığında, kapandığında ve bir kullanıcı bir klasöre gittiğinde dosyaları tarayan **Her zaman açık gerçek zamanlı koruma** ayarıyla birlikte kullanıldığında hızlı tarama, sistemde veya çekirdekte olması mümkün kötü amaçlı yazılımlara karşı koruma sağlamaya yardımcı olur. Tarama bittiğinde kullanıcılar, sonuçları cihazlarında görebilir. 

**Tam tarama**: Tam tarama, etkin olmayan bileşenleri bulunan ve daha kapsamlı bir temizlik gerektiren kötü amaçlı yazılım tehditleriyle karşı karşıya kalan cihazlarda gereklidir ve isteğe bağlı taramalar yapmaya yarar. Tam taramanın tamamlanması bir saati bulabilir. Tarama bittiğinde kullanıcılar, sonuçları cihazlarında görebilir. 

**İmza güncelleştirme**: İmza güncelleştirme komutu, Windows Defender Virüsten Koruma kötü amaçlı yazılım tanımlarını ve imzalarını güncelleştirir. Böylece Windows Defender Virüsten Koruma’nın kötü amaçlı yazılımı algılamada her zaman etkili olması sağlanır. Bu özellik yalnızca Windows 10 cihazlar içindir ve cihaz İnternet bağlantısı gerektirir. 

### <a name="the-enabledisable-button-is-removed-from-the-intune-certificate-authority-page-of-the-intune-azure-portal-----1400455---"></a>Intune Azure portalının Intune Sertifika Yetkilisi sayfasından Etkinleştir/Devre Dışı Bırak düğmesi kaldırıldı  <!-- 1400455 -->
 Intune’da sertifika bağlayıcısını ayarlama adımlarından birini kaldırıyoruz. Şu an sertifika bağlayıcısını indirip Intune konsolunda etkinleştiriyorsunuz. Ancak bağlayıcıyı Intune konsolunda devre dışı bıraktığınızda bağlayıcı, sertifika vermeye devam ediyor.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Ekim ayından itibaren, Etkinleştir/Devre Dışı Bırak düğmesi Azure portalının Intune Sertifika Yetkilisi sayfasında görünmeyecek. Bağlayıcı işlevselliği aynı kalacak. Bağlayıcılar Intune’a kaydedilen cihazlara dağıtılmaya devam edecek. Sertifika bağlayıcısını indirmeye ve yüklemeye devam edebileceksiniz. Sertifikaların verilmesini durdurmak için artık sertifika bağlayıcısını devre dışı bırakmak yerine kaldırmanız gerekecek.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Mevcut durumda sertifika bağlayıcınız devre dışıysa bunu kaldırmanız gerekir.

### <a name="new-settings-for-windows-10-team-device-restriction-profile-------1308838---"></a>Windows 10 Team cihaz kısıtlama profili için yeni ayarlar  <!--- 1308838 -->
Bu sürümde, Surface Hub cihazları denetlemenizi kolaylaştırmak için Windows 10 Team cihaz kısıtlama profiline pek çok yeni ayar ekledik.

Bu profil hakkında daha fazla bilgi için bkz. [Windows 10 Team cihaz kısıtlama ayarları](device-restrictions-windows-10-teams.md).

### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Android cihaz kullanıcılarının cihaz tarih ve saatini değiştirmelerini önleme <!-- 1333292 -->
Android cihaz kullanıcılarının cihaz tarih ve saatini değiştirmelerini önlemek için bir [Android özel cihaz ilkesi](custom-settings-android.md) kullanabilirsiniz.

Bunun için bir Android özel ilkesini ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange ayar URI’si ile yapılandırın, bunu **TRUE** olarak ayarlayın ve gerekli gruplara atayın.

### <a name="bitlocker-device-configuration----1397398---"></a>BitLocker cihaz yapılandırması <!-- 1397398 -->
**Windows Şifreleme > Temel Ayarlar** yeni bir **Başka bir disk şifrelemesi için uyarı** ayarı barındırır. Bu ayar, kullanıcının cihazında kullanımda olabilecek bir diğer disk şifrelemesi için [uyarı istemini](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) devre dışı bırakmanızı sağlar.  Uyarı istemi, cihazda BitLocker ayarlamadan önce son kullanıcı onayı gerektirir ve son kullanıcı tarafından onaylanana kadar BitLocker kurulumunu engeller.  Bu yeni ayar, son kullanıcı uyarısını devre dışı bırakır.


### <a name="volume-purchase-program-for-business-apps-will-now-sync-to-your-intune-tenant----800882---"></a>Volume Purchase Program for Business uygulamaları artık Intune kiracınızla eşitlenecek <!-- 800882 -->  
Üçüncü taraf geliştiriciler, iTunes Connect’te belirtilen yetkilendirilmiş Volume Purchase Program for Business (VPP) üyelerine özel olarak uygulama dağıtabilir. Bu İş için VPP üyeleri, Volume Purchase Program App Store’da oturum açabilir ve uygulamalarını satın alabilir.

Bu sürümle birlikte, son kullanıcı tarafından satın alınan iş için VPP uygulamaları, kullanıcının Intune kiracılarıyla eşitlenmeye başlayacak.

### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>VPP uygulamalarını eşitlemek için Apple ülke mağazası seçme <!-- 1332311 -->  
VPP belirtecinizi karşıya yüklerken Volume Purchase Program (VPP) ülke mağazasını yapılandırabilirsiniz. Intune, belirtilen VPP ülke mağazasındaki tüm yerel ayarlarla VPP uygulamaları eşitler.

> [!NOTE]  
> Şu anda Intune, yalnızca Intune kiracısının oluşturulduğu Intune yerel ayarına uyan VPP ülke mağazasındaki VPP uygulamaları eşitliyor.


### <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Android for Work’te iş hesapları ve kişisel hesaplar arasında kopyalama ve yapıştırmayı engelleme <!-- 1098994 -->
Bu sürümle birlikte, Android for Work iş profilini kopyalama ve yapıştırmayı engelleyecek şekilde yapılandırabilirsiniz. Bu yeni ayarı **İş profili ayarları** altında bulunan **Android for Work** Platformunun **Cihaz kısıtlamaları** profilinde bulabilirsiniz.

### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Belirli bölgesel Apple App Store’lar ile sınırlı iOS uygulamaları oluşturma <!-- 1281692 -->
Bir Apple App Store yönetilen uygulaması oluştururken ülke yerel ayarını belirtebileceksiniz.

> [!Note]  
> Şu anda yalnızca ABD mağazasında kullanılabilen Apple App Store yönetilen uygulamaları oluşturabilirsiniz.

###  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>iOS VPP kullanıcı ve cihaz lisanslı uygulamaları güncelleştirme <!-- 1305564 -->  
Intune hizmeti yoluyla belirteç için satın alınmış tüm uygulamaları güncelleştirmek için bu iOS VPP belirtecini yapılandırabileceksiniz. Intune, uygulama mağazasındaki VPP uygulama güncelleştirmelerini algılayacak ve cihaz iade edildiğinde bunları cihaza otomatik olarak gönderecektir.

Bir VPP belirteci ayarlama ve otomatik güncelleştirmeyi etkinleştirme adımları için bkz. [Volume Purchase Program yoluyla satın alınmış iOS uygulamalarını Microsoft Intune ile yönetme] (/intune/vpp-apps-ios).


### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Intune Veri Ambarı veri modeline kullanıcı cihaz ilişkisi varlığı eklendi <!-- 1187917 -->
Artık kullanıcı ve cihaz varlık koleksiyonlarını ilişkilendiren kullanıcı cihaz ilişki bilgilerini kullanarak rapor ve veri görselleştirmeleri oluşturabilirsiniz. OData uç noktası veya özel bir istemci geliştirme yoluyla Veri Ambarı Intune sayfasından alınan Power BI dosyasından (PBIX) veri modeline erişebilirsiniz.

### <a name="review-policy-compliance-for-windows-10-update-rings----1067886---"></a>Windows 10 güncelleştirme halkaları için ilke uyumluluğunu gözden geçirme <!-- 1067886 -->
Yazılım güncelleştirmeleri > Güncelleştirme halkası başına dağıtımı durumu bölümünden Windows 10 güncelleştirme halkalarınız için bir ilke raporu görüntüleyebileceksiniz. İlke raporu, yapılandırdığınız güncelleştirme halkaları için dağıtım durumunu da içerir. 

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Eski iOS sürümleri ile iOS cihazlarını listeleyen yeni rapor   <!-- 1352223 -->
**Güncel olmayan iOS Cihazları** raporu, **Yazılım güncelleştirmeleri** çalışma alanında kullanılabilir. Raporda, bir iOS güncelleştirme ilkesi tarafından hedeflenen ve kullanılabilir güncelleştirmelere sahip denetimli iOS cihazların listesini görüntüleyebilirsiniz. Her cihaz için cihazın neden otomatik olarak güncelleştirilmediğiyle ilgili bir durum görüntüleyebilirsiniz. 

### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Sorun giderme için uygulama koruma ilke atamalarını görüntüleme <!--  1475003 -->
Gelecek sürümde, sorun giderme dikey penceresinde bulunan **Atamalar** açılan listesine **Uygulama koruma ilkesi** seçeneği eklenecek. Artık, uygulama koruma ilkelerini seçerek seçili kullanıcılara atanan uygulama koruma ilkelerini görebileceksiniz.



### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>Şirket Portalı’nda cihaz kurulum iş akışı iyileştirmeleri <!--1490692-->
Android için Şirket Portalı uygulamasında cihaz kurulum iş akışını iyileştirdik. Dil kolay anlaşılır ve şirketinize özgü bir durumdadır ve ekranlar mümkün olduğunca birleştirilmiştir. Bunları [uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md#week-of-october-2-2017) sayfasında görebilirsiniz.

### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Android cihazlarda kişilere erişim isteği için iyileştirilmiş rehber <!--1484985-->

Android için Şirket Portalı uygulaması genellikle son kullanıcının Kişiler izni vermesini gerektirir. Son kullanıcı bu erişimi reddederse, artık kendisini koşullu erişim için bu izni vermesi konusunda uyaran bir uygulama içi bildirim alacak. 

### <a name="secure-startup-remediation-for-android---1490712--"></a>Android için güvenli başlangıç düzeltmesi <!--1490712-->

Android cihazı olan son kullanıcılar, Şirket Portalı uygulamasında uyumsuzluk sebebine dokunabilecek. Buna dokunmaları mümkün olduğunda, ayarlar uygulamasında sorunu çözebilecekleri konuma gidecekler. 

### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo---1475932--"></a>Android Oreo için Şirket Portalı uygulamasındaki son kullanıcılara ilave anında iletme bildirimleri <!--1475932-->

Android Oreo için Şirket Portalı uygulaması, Intune hizmetinden ilke alma gibi arka plan görevleri gerçekleştirdiğinde, son kullanıcılar bununla ilgili ilave bildirimler görür. Bu, Şirket Portalı’nın cihazlarda ne zaman yönetim görevleri gerçekleştirdiği hakkında son kullanıcılara daha fazla şeffaflık sağlar. Bu, Android Oreo için Şirket Portalı uygulamasındaki genel [Şirket Portalı kullanıcı arabirimi iyileştirmesinin](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) bir parçasıdır. 

Android Oreo’da yeni kullanıcı arabirimi öğeleri için etkinleştirilmiş daha fazla iyileştirme mevcuttur.  Son kullanıcılar, Şirket Portalı’nın Intune hizmetinden ilke almak gibi arka plan görevleri gerçekleştirdiğine dair ilave bildirimler alacaktır.  Bu, Şirket Portalı’nın cihazda ne zaman yönetim görevleri gerçekleştirdiği hakkında son kullanıcılara daha fazla şeffaflık sağlar.

### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>İş profilleri bulunan Android için Şirket Portalı uygulamasında yeni davranışlar <!-- 1485783 -->

Bir Android for Work cihazını iş profiliyle kaydettiğinizde cihazda yönetim görevlerini gerçekleştiren uygulama, iş profilindeki Şirket Portalı’dır. 

Kişisel profilde MAM özellikli uygulama kullanmıyorsanız Android için Şirket Portalı uygulamasının artık hiçbir kullanımı yoktur. İş profili deneyimini iyileştirmek için Intune, başarılı bir iş profili kaydından sonra kişisel Şirket Portalı uygulamasını otomatik olarak saklar.

İstediğiniz zaman [Play Store’da Şirket Portalı](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) araması yapıp **Etkinleştir**’e dokunarak kişisel profilinizde Android için Şirket Portalı uygulamasını etkinleştirebilirsiniz.

### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Windows 8.1 ve Windows Phone 8.1 için Şirket Portalı, dayanıklılık moduna geçiyor <!--1428681-->

Ekim 2017’den itibaren Windows 8.1 ve Windows Phone 8.1 için Şirket Portalı uygulamaları, dayanıklılık moduna geçecek. Yani kayıt ve uyumluluk gibi mevcut senaryolar bu platformlarda desteklenmeye devam edecek. Bu uygulamalar Microsoft Mağazası gibi mevcut yayın kanallarından hala indirilebilir. 

Dayanıklılık moduna geçtikten sonra bu uygulamalar, yalnızca kritik güvenlik güncelleştirmelerini alacak. Bu uygulamalar için ek güncelleştirmeler veya özellikler yayımlanmayacak. Yeni özellikler için cihazları Windows 10 veya Windows 10 Mobile’a güncelleştirmenizi öneririz. 


### <a name="block-unsupported-samsung-knox-device-enrollment-----1490695---"></a>Desteklenmeyen Samsung Knox cihaz kaydını engelleme <!-- 1490695 -->

Şirket Portalı uygulaması, yalnızca desteklenen Samsung Knox cihazları kaydetmeye çalışır. MDM kaydını önleyen Knox etkinleştirme hatalarının önüne geçmek için, yalnızca cihazın [Samsung tarafından yayınlanan cihazlar listesinde](https://www.samsungknox.com/knox-supported-devices/knox-workspace) yer aldığı durumlarda cihaz kaydı denenir. Samsung cihazların Knox destekleyen model numaraları olabilir ancak diğerlerinin olamaz. Satın alma dağıtma işlemlerinden önce, cihazınızın kurumsal bayisinden Knox uyumluluğunu doğrulayın. [Android ve Samsung Knox Standard ilke ayarları](/intune/supported-devices-browsers.md#intune-supported-web-browsers)’nda doğrulanan cihazların tam listesini bulabilirsiniz.

### <a name="end-of-support-for-android-43-and-lower----1171126-1326920---"></a>Android 4.3 ve altı sürümler için desteğin son bulması<!-- 1171126, 1326920 -->
Yönetilen uygulamalar ve Android için Şirket Portalı uygulaması, şirket kaynaklarına erişim için Android 4.4 ve üzeri sürümleri gerektirecek. Aralık ayında ise tüm kayıtlı cihazlar zorla devre dışı bırakılacak ve böylece şirket kaynaklarına erişimi kaybedeceklerdir. MDM’siz uygulama koruma ilkeleri kullanıyorsanız uygulamalar güncelleştirme almayacak ve deneyimlerinin kalitesi zamanla düşecek.

### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>Kayıtlı cihazlarda hangi cihaz bilgilerinin görülebileceği hakkında son kullanıcıları bilgilendirme <!--1165314-->
Tüm Şirket Portalı uygulamalarında Cihaz Ayrıntıları ekranına **Sahiplik Türü** ekliyoruz. Böylece kullanıcılar, doğrudan [Şirketiniz hangi bilgileri görebilir?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune) makalesinden gizlilik hakkında bilgi edinebilecekler. Bu değişiklik, yakın zamanda tüm Şirket Portalı uygulamalarında sunulacak. iOS için bu değişikliği [Eylül](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017) ayı içinde duyurduk.

## <a name="september-2017"></a>Eylül 2017

### <a name="intune-supports-ios-11---1428975--"></a>Intune, iOS 11’i destekliyor <!--1428975-->
Intune, iOS 11’i destekliyor. Bu, daha önce [Intune Destek bloğunda](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/) duyurulmuştu.

### <a name="end-of-support-for-ios-80----1164477---"></a>iOS 8.0 desteğinin son bulması <!-- 1164477 -->
Yönetilen uygulamalar ve iOS için Şirket Portalı uygulaması, şirket kaynaklarına erişim için iOS 9.0 ve üzeri sürümleri gerektirecek. Eylül ayından önce güncelleştirmeyen cihazlar, Şirket Portalı veya diğer uygulamalara erişemeyecek. 

### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Windows 10 için Şirket Portalı uygulamasına yenileme eylemi eklendi <!--1132468-->
Windows 10 için Şirket Portalı uygulaması, mobil cihazlarda aşağı çekerek veya masaüstü cihazlarda F5’e basarak kullanıcılara uygulamadaki verileri yenileme imkanı sunar.

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>iOS için hangi cihaz bilgilerinin görülebileceği hakkında son kullanıcıları bilgilendirme <!--739894-->

iOS için Şirket Portalı’nda Cihaz Ayrıntıları ekranına **Sahiplik Türü** ekledik. Bu, kullanıcıların doğrudan bu sayfadaki Intune son kullanıcı belgelerinden gizlilik hakkında daha fazla bilgi edinmesini sağlar. Kullanıcılar bu bilgileri Hakkında ekranında da bulabilir.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Son kullanıcıların kayıt yapmadan Android için Şirket Portalı uygulamasına erişmelerine izin verme <!---1169910--->

Son kullanıcılar yakın zamanda cihazlarını kaydetmeden Android için Şirket Portalı uygulamasına erişebilecek. Uygulama Koruma İlkeleri kullanan kuruluşlardaki son kullanıcılar artık Şirket Portalı uygulamasını açtıklarında cihazlarını kaydetmelerine yönelik komut istemleri almayacaklar. Son kullanıcılar ayrıca cihaz kaydı yapmaksızın Şirket Portalı’dan uygulama yükleyebilecek. 


### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android----1396349---"></a>Android için Şirket Portalı uygulamasında daha kolay anlaşılır bir dil <!---1396349--->  

Android için Şirket Portalı uygulamasında kayıt işlemi, son kullanıcıların kaydını kolaylaştırmak adına yeni metinlerle düzenlendi. Özel kayıt belgeleriniz varsa bunları, değişiklikleri yansıtması için güncelleştirmelisiniz. [Intune son kullanıcı uygulamaları için kullanıcı arabirimi güncelleştirmeleri](whats-new-app-ui.md#week-of-september-11-2017) sayfamızda örnek görüntüleri bulabilirsiniz.

### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Windows 10 Şirket Portalı uygulaması, Windows Bilgi Koruması izin ilkesine eklendi <!-- 677129 -->

Windows 10 Şirket Portalı uygulaması, Windows Bilgi Koruması’nı (WIP) destekleyecek şekilde güncelleştirildi. Uygulama, WIP izin ilkesine eklenebilecek. Bu değişiklik ile uygulamanın **Muaf** listesine eklenme gerekliliği ortadan kalkacak.


## <a name="august-2017"></a>Ağustos 2017

### <a name="improvements-to-device-overview----1404453---"></a>Cihaz önizlemesi iyileştirmeleri <!-- 1404453 -->  
Cihaz önizlemesi iyileştirmeleri artık kayıtlı cihazları gösterirken Exchange ActiveSync tarafından yönetilen cihazları göstermiyor. Exchange ActiveSync cihazları, kayıtlı cihazlarla aynı yönetim seçeneklerine sahip değil. Azure portalında Intune’da kayıtlı cihaz sayısını ve platforma göre kayıtlı cihaz sayısını görüntülemek için, **Cihazlar** > **Genel Bakış**‘a gidin.

### <a name="improvements-to-device-inventory-collected-by-intune"></a>Intune tarafından toplanan cihaz envanteri geliştirmeleri
<!-- 961134, 1104426, 1281327, 1333543 --> Bu sürümde, yönettiğiniz cihazlar tarafından toplanan envanter bilgilerinde aşağıdaki iyileştirmeleri yaptık:
 
-   Android cihazlarda artık her cihaz için cihaz envanterine son düzeltme eki düzeyini gösteren bir sütun ekleyebilirsiniz. Bunu görmek için cihaz listenize **Güvenlik düzeltme eki düzeyi** sütununu ekleyin.
-   Cihaz görünümünü filtrelerken artık cihazları kayıt tarihlerine göre filtreleyebilirsiniz. Örneğin, yalnızca belirttiğiniz bir tarihten sonra kaydedilen cihazları görüntüleyebilirsiniz.
-   **Son Yer Bildirim Tarihi** öğesi tarafından kullanılan filtrede iyileştirmeler yaptık.
-   Cihaz listesinde artık şirkete ait cihazların telefon numaralarını görüntüleyebilirsiniz.
Ayrıca, filtre bölmesini kullanarak cihazları telefon numarasına göre arayabilirsiniz.
 
Cihaz envanteri hakkında daha fazla ayrıntı için bkz. [Intune cihaz envanterini görüntüleme](device-inventory.md).

### <a name="conditional-access-support-for-macos-devices"></a>macOS cihazlar için koşullu erişim desteği 
<!-- 720172 --> Artık Mac cihazların Intune’a kaydedilmesi ve Intune cihaz uyumluluk ilkeleriyle uyumlu olmasını gerektiren bir koşullu erişim ilkesi ayarlayabilirsiniz. Örneğin kullanıcılar, macOS için Intune Şirket Portalı uygulamasını indirebilir ve Mac cihazlarını Intune’a kaydedebilir. Intune ise PIN, şifreleme, işletim sistemi sürümü ve Sistem Bütünlüğü gibi gereksinimleri kullanarak Mac cihazın uyumlu olup olmadığını değerlendirir.

- [macOS cihazlar için koşullu erişim desteği](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) hakkında daha fazla bilgi edinin.

### <a name="company-portal-app-for-macos-is-in-public-preview----1484796---"></a>macOS için Intune Şirket Portalı uygulaması genel önizlemede <!---1484796--->
macOS için Şirket Portalı uygulaması artık Enterprise Mobility + Security’de koşullu erişim için genel önizlemenin bir parçası olarak kullanılabilir. Bu sürüm, macOS 10.11 ve üzerini destekler. Buradan edinin: [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal). 


### <a name="new-device-restriction-settings-for-windows-10"></a>Windows 10 için yeni cihaz kısıtlama ayarları    
<!--1063965, 1308850  --> Bu sürümde, [Windows 10 cihaz kısıtlama profili](/intune/device-restrictions-windows-10) için aşağıdaki kategorilere yeni ayarlar ekledik:

-   Windows Defender SmartScreen
-   Uygulama mağazası

### <a name="updates-to-the-windows-10-endpoint-protection-device-profile-for-bitlocker-settings"></a>BitLocker ayarları için Windows 10 uç nokta koruma cihaz profili güncelleştirmeleri
<!--1459533 -->    
Bu sürümde, BitLocker’ın Windows 10 uç nokta koruma cihaz profilinde çalışması konusunda aşağıdaki iyileştirmeleri yaptık:
 
**BitLocker işletim sistemi sürücü ayarları** altında **Uyumlu olmayan TPM yongası ile BitLocker** için **Engelle**’yi seçtiğinizde, Bu durum eskiden BitLocker’a izin verilmesine yol açıyordu. Artık bunu, seçildiğinde BitLocker’ı engelleyecek şekilde düzelttik.
**BitLocker işletim sistemi sürücü ayarları** altında **Sertifika tabanlı veri kurtarma aracısı** ayarında artık sertifika tabanlı veri kurtarma aracısını engelleyebilirsiniz. Ancak varsayılan olarak bu aracıya izin verilir.
**BitLocker sabit veri sürücü ayarları** altında **Veri kurtarma aracısı** ayarında artık kurtarma aracısını engelleyebilirsiniz.
Daha fazla bilgi için bkz. [Windows 10 ve üzeri sürümler için Endpoint Protection ayarları](endpoint-protection-windows-10.md).


### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Android Şirket Portalı ve Uygulama Koruma İlkesi kullanıcıları için yeni oturum açma deneyimi <!-- 621669 -->
Son kullanıcılar artık Android Şirket Portalı’nı kullanarak cihazlarını kaydetmeden uygulamalara göz atabilir, cihazları yönetebilir ve BT iletişim bilgilerini görüntüleyebilir. Ayrıca, son kullanıcı zaten Intune Uygulama Koruma İlkeleri ile korunan bir uygulama kullanıyorsa ve Android Şirket Portalı'nı başlatırsa artık cihazı kaydetmek için bir istem almaz.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>Android Şirket Portalı uygulamasında pil iyileştirmesini değiştirmek için yeni bir ayar <!--1405990-->
Android için Şirket Portalı uygulamasında **Ayarlar** sayfası, kullanıcıların Şirket Portalı ve Microsoft Authenticator uygulamaları için pil iyileştirmesini kolaylıkla kapatmalarına izin veren yeni bir ayara sahip. Ayarda gösterilen uygulama adı, hangi uygulamanın iş hesabını yönettiğine bağlı olarak değişecektir. E-posta ve veri eşitleyen iş uygulamalarının daha iyi çalışması için kullanıcıların pil iyileştirmesini kapatmalarını öneririz. 

### <a name="multi-identity-support-for-onenote-for-ios---------1234281---"></a>iOS için OneNote’da çoklu kimlik desteği      <!-- 1234281 -->
Son kullanıcılar artık, iOS için Microsoft OneNote ile farklı hesaplar (iş ve kişisel) kullanabilir. Kullanıcıların kişisel not defterlerini etkilemeksizin iş not defterlerinde şirket verilerine uygulama koruma ilkeleri uygulanabilir. Örneğin bir ilke, bir kullanıcının iş not defterlerinde istediği bilgileri bulmasına izin verirken iş not defterlerinden kişisel not defterine şirket verilerini kopyalayıp yapıştırmasını engelleyebilir.
 
- Intune ile [uygulama koruması ve çoklu kimlik](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) destekleyen uygulamalar hakkında daha fazla bilgi edinin.

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices"></a>Samsung Knox Standard cihazlarda uygulamalara izin vermek veya bunları engellemek için yeni ayarlar
<!-- 1305423 822899-->  
Bu sürümde, aşağıdaki uygulama listelerini belirtmenizi sağlayan yeni [cihaz kısıtlama ayarları](device-restrictions-android.md) ekliyoruz:
 
- Kullanıcıların yüklemesine izin verilen uygulamalar
- Kullanıcıların çalıştırması engellenen uygulamalar
- Cihazda kullanıcıdan gizlenen uygulamalar
 
Uygulamayı URL, paket adı ile veya yönettiğiniz uygulamalar listesinden belirtebilirsiniz.

### <a name="new-azure-ad-app-based-conditional-access-policy-ui-link-from-intune"></a>Intune’dan yeni Azure AD uygulama tabanlı koşullu erişim ilkesi kullanıcı arabirimi bağlantısı
<!-- 1016201 --> BT yöneticileri artık, Azure AD iş yükünde yeni koşullu erişim ilkesi kullanıcı arabirimi aracılığıyla uygulama tabanlı ilkeler ayarlayabilir. Azure portalındaki Intune Uygulama Koruması bölümünde bulunan uygulama tabanlı koşullu erişim şimdilik orada kalacak ve yan yana uygulanacaktır. Ayrıca Intune iş yükünde, yeni koşullu erişim ilkesi kullanıcı arabirimine kolay bir bağlantı da bulunur.

- [Azure AD’de uygulama tabanlı koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference) hakkında daha fazla bilgi edinin.



## <a name="july-2017"></a>Temmuz 2017

### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>Android ve iOS cihaz kaydı kısıtlamasını işletim sistemi sürümüyle kısıtlama <!--- 1333256,  1245463 --->
Intune artık iOS ve Android kaydını işletim sistemi sürüm numarasına göre kısıtlamayı desteklemektedir. BT yöneticisi bundan sonra, **Cihaz Türü Kısıtlaması**'nın altından kaydı en düşük ve en yüksek işletim sistemi değerleri arasında bir platform yapılandırmasını sınırlamak üzere ayarlayabilir. Android işletim sistemi sürümleri Büyük.Küçük.Derleme.Düzeltme olarak belirtilmelidir. Burada Küçük, Derleme ve Düzeltme isteğe bağlıdır. iOS sürümleri ise Büyük.Küçük.Derleme olarak belirtilmelidir; burada Küçük ve Derleme isteğe bağlıdır. [Cihaz kaydı kısıtlamaları](enrollment-restrictions-set.md) hakkında daha fazla bilgi edinin.

>[!NOTE]
>Kayıt işlemini Apple kayıt programları veya Apple Configurator ile kısıtlamayın.

### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Android, iOS ve macOS cihazların kişisel cihaz kaydını kısıtlama  <!--- 1333272,  1333275, 1245709 --->
Intune, şirket cihazı IMEI numaralarını güvenilir listeye ekleyerek kişisel cihaz kaydını kısıtlayabilir. Intune artık bu işlevi cihaz seri numarası kullanan iOS, Android ve macOS için genişletmiştir. Intune’a seri numaralarını yükleyerek cihazların şirkete ait olduğunu önceden bildirmiş olursunuz. Kayıt kısıtlamalarını kullanarak kişişel (KCG) cihazları engelleyebilir ve yalnızca şirkete ait cihazların kaydına izin verebilirsiniz. [Cihaz kaydı kısıtlamaları](enrollment-restrictions-set.md) hakkında daha fazla bilgi edinin.

Seri numaralarını içeri aktarmak için **Cihaz kaydı** > **Kurumsal cihaz tanımlayıcıları**’na gidin, **Ekle**’ye tıklayın ve bir .CSV dosyası yükleyin (üst bilgi, seri numarası ve IMEI numaraları gibi ayrıntılar için iki sütun).  Kişisel cihazları kısıtlamak için **Cihaz kaydı** > **Kayıt kısıtlamaları**’na gidin. **Cihaz Türü Kısıtlamaları** altında **Varsayılan**’ı ve daha sonra **Platform Yapılandırmaları**’nı seçin. iOS, Android ve macOS kişisel cihazlar için **İzin Ver** veya **Engelle** seçeneklerinden birini belirtebilirsiniz. 


### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Cihazları Intune ile eşitlemeye zorlayan yeni bir cihaz eylemi <!-- 711369 -->
Bu sürümde, seçili cihazı Intune’da hemen bildirim yapmaya zorlayan yeni bir cihaz eylemi ekledik. Bir cihaz giriş yaptığında, kendisine atanan beklemedeki eylem veya ilkeleri hemen alır.  Bu eylem, atadığınız ilkeleri bir sonraki zamanlanmış iadeyi beklemenize gerek kalmadan hızla doğrulamanız ve ilkelerin sorunlarını gidermenize yardımcı olur.
Ayrıntılar için bkz. [Cihaz eşitleme](device-sync.md)

### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>Denetimli iOS cihazları, son yazılım güncelleştirmesini yüklemeye zorlama <!-- 777100 -->
Denetimli iOS cihazları mevcut son yazılım güncelleştirmesini otomatik olarak yüklemeye zorlayabileceğiniz Yazılım güncelleştirmeleri çalışma alanında yeni bir ilke kullanılabilir durumdadır. Ayrıntılar için bkz. [iOS güncelleştirme ilkelerini yapılandırma](/intune/software-updates-ios)

### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner-----954651-1172027---"></a>Check Point SandBlast Mobile - Yeni Mobile Threat Defense iş ortağı  <!-- 954651, 1172027 -->
Microsoft Intune ile tümleşik çalışan mobil tehdit savunması çözümü Checkpoint SandBlast Mobile tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihazlardan şirket kaynaklarına erişimi denetleyebilirsiniz.

#### <a name="how-integration-with-intune-works"></a>Intune ile tümleştirme nasıl çalışır?
Risk, Checkpoint SandBlast Mobile çalıştıran cihazlardan toplanan telemetriye göre değerlendirilir. Intune cihaz uyumluluk ilkeleri aracılığıyla etkinleştirilen Checkpoint SandBlast Mobile risk değerlendirmesine dayalı olarak EMS koşullu erişim ilkeleri yapılandırabilirsiniz. Algılanan tehditlere dayalı olarak uyumlu olmayan cihazların şirket kaynaklarına erişmesine izin verebilir ya da erişimi engelleyebilirsiniz.


### <a name="deploy-an-app-as-available-in-the-microsoft-store-for-business----748101---"></a>Bir uygulamayı İş için Microsoft Mağazası’nda kullanılabilir olarak dağıtma <!-- 748101 -->
Bu sürümle birlikte, yöneticiler artık İş için Microsoft Mağazası’nı kullanılabilir olarak atayabilir. Kullanılabilir olarak ayarlandığında, son kullanıcılar Microsoft Mağazası’na yönlendirilmeden uygulamayı Şirket Portalı uygulamasından veya web sitesinden yükleyebilir.

### <a name="ui-updates-to-the-company-portal-website---1313244-part-1--"></a>Şirket Portalı web sitesine kullanıcı arabirimi güncelleştirmeleri <!--1313244 part 1-->
Son kullanıcı deneyimini geliştirmek için [Şirket Portalı Web sitesinin](https://portal.manage.microsoft.com) kullanıcı arabiriminde bazı güncelleştirmeler yaptık.

- __Uygulama kutucuklarında yapılan geliştirmeler__: Uygulama simgeleri artık simgedeki baskın renge göre (algılanabilirse) otomatik olarak oluşturulmuş bir arka plan ile görüntülenecektir. Uygun olduğunda, bu arka plan daha önce uygulama kutucuklarında görünen gri kenarlıkların yerine geçer.

    Şirket Portalı web sitesi, gelecek bir sürümde mümkün olduğunda büyük simgeler gösterecektir. BT yöneticilerinin en az 120x120 piksel boyutuna sahip yüksek çözünürlüklü simgeler kullanarak uygulama yayımlamalarını öneririz. 

- __Gezinti değişiklikleri__ Gezinti çubuğu öğeleri, sol üstteki hamburger menüsüne taşındı. Kategoriler sayfası kaldırıldı. Kullanıcılar artık gözatma sırasında içeriği kategorilere göre filtreleyebilir.

- __Öne Çıkan Uygulama Güncelleştirmeleri__: Kullanıcıların öne çıkarmak istediğiniz uygulamalara göz atabileceği siteye ayrı bir sayfa ekledik ve giriş sayfasındaki Öne Çıkan sekmesinde bazı kullanıcı arabirimi değişiklikleri yaptık.

### <a name="ibooks-support-for-the-company-portal-website---1231841--"></a>Şirket Portalı web sitesine yönelik iBooks desteği <!--1231841-->
Şirket Portalı web sitesine, kullanıcıların iBooks’a göz atıp kitap indirmesine olanak tanıyan özel bir sayfa ekledik. 


### <a name="additional-help-desk-troubleshooting-details------applies-to-1263399-1326964-1341642----"></a>İlave yardım masası sorun giderme ayrıntıları <!---  Applies to 1263399, 1326964, 1341642 --->
Intune, sorun giderme ekranını güncelleştirdi ve yöneticilerle yardım masası çalışanları için sağladığı bilgileri artırdı. Artık, kullanıcı tabanlı grup üyeliği için tüm atamaları özetleyen bir **Atamalar** tablosu görebilirsiniz. Liste şunları içerir:
- Mobil uygulamalar
- Uyumluluk ilkeleri
- Yapılandırma profilleri
 
Ayrıca **Cihazlar** tablosu artık **Azure AD katılım türü** ve**Azure AD uyumlu** sütunlarını içeriyor. Daha fazla bilgi için bkz. [kullanıcıların sorunlarını gidermeye yardım etme](help-desk-operators.md).



### <a name="intune-data-warehouse-public-preview"></a>Intune Veri Ambarı (Genel Önizleme)
Intune Veri Ambarı, kiracınızın geçmiş bilgilerini görüntülemenizi sağlamak için her gün veri örnekleri sağlar. Verilere bir Power BI dosyası (PBIX), birçok analiz aracıyla uyumlu bir OData bağlantısı kullanarak veya REST API’si ile etkileşimde bulunarak erişebilirsiniz. Daha fazla bilgi için bkz. [Intune Veri Ambarı’nı Kullanma](reports-nav-create-intune-reports.md).


### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Windows 10 için Şirket Portalı uygulamasında açık ve koyu modlar kullanılabilir <!---676547--->
Windows 10 için Şirket Portalı uygulamasında son kullanıcılar, renk modunu özelleştirebilecek. Kullanıcılar bu değişikliği Şirket Portalı uygulamasının Ayarlar kısmından yapabilir. Değişiklik, kullanıcı uygulamayı yeniden başlattığında görünecektir. Windows 10 sürüm 1607 ve üzeri için uygulama modu varsayılan olarak sistem ayarında olacaktır. Windows 10 sürüm 1511 ve öncesi için uygulama modu varsayılan olarak açık modda olacaktır.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>Windows 10 için Şirket Portalı uygulamasında son kullanıcıların cihaz gruplarını etiketlemelerine izin verme <!---807046-->
Son kullanıcılar, artık doğrudan Windows 10 için Şirket Portalı uygulamasında cihazlarının hangi gruba ait olduğunu etiketleyerek cihaz gruplarını belirleyebilir.



## <a name="june-2017"></a>Haziran 2017

### <a name="new-role-based-administration-access-for-intune-admins------1099990---"></a>Intune yöneticileri için yeni rol tabanlı yönetim erişimi   <!-- 1099990 -->  
Azure AD Koşullu Erişim ilkelerini görüntülemek, oluşturmak, değiştirmek ve silmek için yeni bir koşullu erişim yönetim rolü ekleniyor. Daha önce yalnızca genel yöneticiler ve güvenlik yöneticileri bu izne sahipti. Koşullu erişim ilkelerine erişebilmeleri için Intune yöneticilerine bu rolün izinleri verilebilir.


### <a name="tag-corporate-owned-devices-with-serial-number----1215070---"></a>Şirkete ait cihazları seri numarasıyla etiketleme <!-- 1215070 -->  
Intune artık iOS, macOS ve Android seri numaralarını Kurumsal Cihaz Tanımlayıcıları olarak karşıya yüklemeyi destekliyor. Seri numaralar kayıt sırasında doğrulanmadığı için bu numaraları henüz kişisel cihazların kaydedilmesini engellemek için kullanamazsınız. Kişisel cihazları seri numarasına göre engelleme, yakın bir gelecekte çıkacak.


### <a name="new-remote-actions-for-ios-devices----854689---"></a>iOS cihazları için yeni uzak eylemler <!-- 854689 -->
Bu sürümde, Apple Classroom uygulamasını yöneten paylaşılan iPad cihazlar için iki yeni uzak cihaz eylemi ekledik:

-   [Geçerli kullanıcının oturumunu kapat](device-logout-user.md) - Seçtiğiniz bir iOS cihazının geçerli kullanıcısının oturumunu kapatır.
-   [Kullanıcı kaldır](device-remove-user.md) - Bir iOS cihazdaki yerel önbellekten seçtiğiniz bir kullanıcıyı siler.


### <a name="support-for-shared-ipads-with-the-ios-classroom-app----1044681---"></a>iOS Classroom uygulaması ile paylaşılan iPad'ler için destek <!-- 1044681 -->
Bu sürümde, iOS Classroom uygulamasının kapsamını, paylaşılan iPad’lerde yönetilen Apple kimliklerini kullanarak oturum açan öğrencileri de içerecek şekilde genişlettik.


### <a name="changes-to-intune-built-in-apps----1332306---"></a>Intune yerleşik uygulamalarındaki yenilikler <!-- 1332306 -->
Eskiden Intune’da hızlıca atayabileceğiniz birkaç yerleşik uygulama vardı. Geri bildirimlerinize dayanarak bu listeyi kaldırdık, artık yerleşik uygulamaları görmeyeceksiniz.
Ancak herhangi bir yerleşik uygulamayı önceden atadıysanız bu uygulamalar, uygulama listesinde görünmeye devam edecektir. Bu cihazları gerektiği gibi atamaya devam edebilirsiniz.
Sonraki bir sürümde, Azure portalında yerleşik uygulama seçme ve atama için daha kolay bir yöntem eklemeyi planlıyoruz.

### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Office 365 uygulamalarında yükleme kolaylığı <!--- 1121362 --->
Yeni **Office 365 ProPlus** uygulama türü, Office 365 ProPlus 2016 uygulamalarını Windows 10’un en son sürümünü çalıştıran yönettiğiniz cihazlara atamayı kolaylaştırır. Bunun yanı sıra, Microsoft Project ve Microsoft Visio lisanslarınız varsa bu uygulamaları yükleyebilirsiniz. İstediğiniz uygulamalar birlikte paketlenir ve Intune konsolundaki uygulamalar listesinde tek uygulama olarak gösterilir.
Daha fazla bilgi için bkz. [Windows 10 için Office 365 uygulamaları ekleme](apps-add-office365.md).


### <a name="support-for-offline-apps-from-the-microsoft-store-for-business-----777044----"></a>İş İçin Microsoft Mağazası uygulamaları için çevrimdışı desteği <!--- 777044 --->
İş için Microsoft Mağazası’ndan satın aldığınız çevrimdışı uygulamalar, artık Azure portalına eşitlenecektir. Daha sonra bu uygulamaları cihaz gruplarına veya kullanıcı gruplarına dağıtabilirsiniz. Çevrimdışı uygulamalar, mağaza tarafından değil Intune tarafından yüklenir.

### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---"></a>Microsoft Teams artık onaylı uygulamaların Uygulama temelli CA listesinin bir parçasıdır   <!-- 1257019 -->
iOS ve Android için Microsoft Teams uygulaması artık Exchange ve SharePoint Online için uygulama tabanlı koşullu erişim ilkeleri onaylı uygulamalarının bir parçasıdır. Uygulamayı, uygulama tabanlı koşullu erişim kullanmakta olan tüm kiracıların Azure portalındaki Intune Uygulama Koruması dikey penceresinde yapılandırabilirsiniz.

### <a name="managed-browser-and-app-proxy-integration----1287310---"></a>Managed Browser ve uygulama proxy’si tümleştirmesi <!-- 1287310 -->
Intune Managed Browser artık Azure AD Uygulama Proxy’si hizmeti ile tümleştirilebilir ve bu sayede kullanıcılar uzaktan çalışsalar bile dahili web sitelerine erişebilirler. Tarayıcıyı kullanırken her zaman yaptığınız gibi site URL’sini girmeniz yeterlidir, Managed Browser bu isteği uygulama proxy’si web ağ geçidine yönlendirecektir. Daha fazla bilgi için bkz. [Managed Browser ilkeleri kullanarak İnternet erişimini yönetme](app-configuration-managed-browser.md).

### <a name="new-app-configuration-settings-for-the-intune-managed-browser----682951---"></a>Intune'la Managed Browser için yeni uygulama ayarları <!-- 682951 -->
Bu sürümde, iOS ve Android için Intune Managed Browser uygulamasına ilave yapılandırmalar ekledik. Artık tarayıcının varsayılan giriş sayfasını ve yer işaretlerini yapılandırmak için bir uygulama yapılandırma ilkesi kullanabilirsiniz.
Daha fazla bilgi için bkz. [Managed Browser ilkeleri kullanarak İnternet erişimini yönetme](app-configuration-managed-browser.md)

### <a name="bitlocker-settings-for-windows-10-----951707---"></a>Windows 10 için BitLocker ayarları <!-- 951707 -->
Artık yeni bir Intune cihaz profili kullanarak Windows 10 cihazlar için BitLocker ayarlarını yapılandırabilirsiniz. Örneğin cihazların şifreli olmasını gerekli kılabilir ve BitLocker açık olduğunda uygulanacak başka ayarlar da yapılandırabilirsiniz.
Daha fazla bilgi için bkz. [Windows 10 ve üzeri sürümler için Endpoint Protection ayarları](endpoint-protection-windows-10.md).

### <a name="new-settings-for-windows-10-device-restriction-profile-----978527--978550-978569-1050031-1058611-----"></a>Windows 10 cihaz kısıtlama profili için yeni ayarlar <!--- 978527,  978550, 978569, 1050031, 1058611,  --->
Bu sürümde, Windows 10 cihaz kısıtlama profili için aşağıdaki kategorilere yeni ayarlar ekledik:

-  Windows Defender
-  Hücresel ve bağlantı
-  Kilit ekranı deneyimi
-  Gizlilik
-  Ara
-  Windows Spot
-  Edge tarayıcısı

Windows 10 ayarları hakkında daha fazla bilgi için bkz. [Windows 10 ve üzeri sürümler için cihaz kısıtlama ayarları](device-restrictions-windows-10.md).


### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>Android için Şirket Portalı uygulamasının artık Uygulama Koruma İlkeleri için yeni bir son kullanıcı deneyimi vardır <!--1305217-->
Müşteri geri bildirimi doğrultusunda, Android için Şirket Portalı uygulamasını bir **Şirket İçeriğine Eriş** düğmesi gösterecek şekilde değiştirdik. Amaç, son kullanıcıların yalnızca, Intune mobil uygulama yönetiminin bir özelliği olan Uygulama Koruma İlkelerini destekleyen uygulamalara erişmek için gereksiz yere kayıt işlemi yapmalarını engellemektir. Bu değişiklikleri, [uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md) sayfasında görebilirsiniz.

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Şirket Portalını kolayca kaldırmak için yeni menü eylemi <!--1164569-->
Kullanıcı geri bildirimi doğrultusunda, Android için Şirket Portalı uygulaması, Şirket Portalını cihazınızdan kaldırmak için yeni bir menü eylemi ekledi. Bu eylem cihazı Intune yönetiminden kaldırır, böylece uygulama cihazdan kullanıcı tarafından kaldırılabilir. Bu değişiklikleri [Uygulamanın kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md) sayfasında ve [Android son kullanıcı belgelerinde](/intune-user-help/unenroll-your-device-from-intune-android) görebilirsiniz.

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Windows 10 Creators Güncelleştirmesi ile uygulama eşitleme geliştirmeleri <!--676505-->
Windows 10 için Şirket Portalı uygulaması, Windows 10 Creators Update (sürüm 1703) içeren cihazlarda uygulama yükleme istekleri için eşitlemeyi artık otomatik olarak başlatacak. Bu, “Eşitleme Bekleniyor” durumu sırasında bekletilen uygulama yüklemeleri sorununu azaltacak. Buna ek olarak, kullanıcılar uygulamanın içinden el ile eşitleme başlatabilecek. Bu değişiklikleri, [uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md) sayfasında görebilirsiniz.

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Windows 10 Şirket Portalı için kullanıcının yönlendirildiği yeni deneyim <!---1058938--->
Windows 10 için Şirket Portalı uygulaması, tanımlanmamış veya kaydedilmemiş cihazlar için kullanıcının adım adım yönlendirildiği bir Intune deneyimi içerecek. Yeni deneyim, kullanıcıya Azure Active Directory kaydı sürecinde (Koşullu Erişim özelliklerinde gereklidir) ve MDM kaydı sürecinde (cihaz yönetim özellikleri için gereklidir) kılavuzluk eden adım adım yönergeler sağlıyor. Kılavuzluk destekli deneyime Şirket Portalı giriş sayfasından erişilebilecek. Kullanıcılar, cihaz kaydettirme ve kaydolma işlemlerini tamamlamasa da uygulamayı kullanmaya devam edebilecek, ancak sınırlı bir işlevsellikleri olacak.

Bu güncelleştirme yalnızca Windows 10 Yıldönümü Güncelleştirmesi (derleme 1607) veya üzerini çalıştıran cihazlarda görünür. Bu değişiklikleri, [uygulama kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md) sayfasında görebilirsiniz.


### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Microsoft Intune ve Koşullu Erişim yönetici konsolları genel olarak kullanılabilir
Azure portalında Intune yönetici konsolu ve Koşullu Erişim yönetici konsolunun genel olarak kullanılabilir olduğunu duyuruyoruz. Azure portalında Intune aracılığıyla, artık tüm Intune MAM ve MDM özelliklerini birleştirilmiş tek bir yönetim deneyiminde yönetebilir ve Azure AD gruplandırma ve hedefleme özelliğinden yararlanabilirsiniz. Azure’da koşullu erişim, Azure AD ve Intune’daki zengin özellikleri birleştirilmiş bir konsol ile bir araya getirir. Yönetim deneyimi açısından ise Azure platformuna geçmek modern tarayıcıları kullanmanıza olanak tanır.

Intune artık portal.azure.com adresindeki Azure portalında **önizleme** etiketi olmadan da görünür durumdadır.

İleti merkezinde gruplarınızın geçişini yapmamız için eylemde bulunmanızı isteyen ileti serilerinden birini almadıysanız şu anda mevcut müşterilerin yapması gereken bir eylem yoktur. Tarafımızdaki hatalardan dolayı geçişinizin daha uzun sürdüğünü belirten bir ileti merkezi bildirimi de almış olabilirsiniz. Etkilenen tüm müşterilerin geçişini tamamlamak üzere titizlikle çalışmaya devam ediyoruz.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>iOS için Şirket Portalı uygulamasındaki uygulama kutucukları geliştirmeleri
Şirket Portalı için ayarladığınız marka rengini yansıtmak için giriş sayfasındaki uygulama kutucuklarının tasarımı güncelleştirildi. Daha fazla bilgi için bkz. [Uygulamanın kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md).

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>iOS Şirket Portalı uygulaması için artık hesap seçici kullanılabilir
iOS cihazı kullanıcıları diğer Microsoft uygulamalarında oturum açmak için iş veya okul hesaplarını kullanıyorsa Şirket Portalı uygulamasında oturum açtıklarında yeni hesap seçiciyi görebilirler. Daha fazla bilgi için bkz. [Uygulamanın kullanıcı arabirimindeki yenilikler](whats-new-app-ui.md).

## <a name="may-2017"></a>Mayıs 2017

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Yönetilen cihazların kaydını kaldırmadan MDM yetkilinizi değiştirme <!--1103950-->
Artık Microsoft Desteği’ne başvurmak ve mevcut yönetilen cihazlarınızın kaydını kaldırıp yeniden kaydetmek zorunda kalmadan MDM yetkilinizi değiştirebilirsiniz. Configuration Manager konsolunda, [MDM yetkilinizi değiştirerek](/sccm/mdm/deploy-use/change-mdm-authority) Configuration Manager’a Ayarla (karma) ile Microsoft Intune (tek başına) seçenekleri arasında geçiş yapabilirsiniz.


### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Samsung Knox başlangıç PIN’leri için geliştirilmiş bildirim <!--1087143-->
Şifrelemeyle uyumlu olması için son kullanıcıların Samsung Knox cihazlarında başlangıç PIN’i ayarlamaları gerektiğinde, son kullanıcılara gösterilen bildirime dokunulduğunda bildirimleri Ayarlar uygulamasında doğru yere yerleştirir.  Daha önce, bildirim son kullanıcıyı parola değiştirme ekranına getiriyordu.

### <a name="device-enrollment"></a>Cihaz kaydı

#### <a name="apple-school-manager-asm-support-with-shared-ipad----748864-770395--"></a>Paylaşılan iPad ile Apple School Manager (ASM) desteği <!-- 748864, 770395-->

Intune, iOS cihazlarında hazır kayıt sağlamak için Apple Aygıt Kayıt Programı yerine artık Apple School Manager’ı (ASM) destekler. Paylaşılan iPad’lerde Classroom uygulamasını kullanmak ve Microsoft School Data Sync (SDS) yoluyla ASM’den Azure Active Directory’ye veri eşitlemeyi etkinleştirmek için ASM’nin kullanıma alınması gereklidir. Daha fazla bilgi için bkz. [Apple School Manager ile iOS cihaz kaydını etkinleştirme](apple-school-manager-set-up-ios.md).

> [!NOTE]
> Paylaşılan iPad’leri Classroom uygulaması ile birlikte çalışmak üzere yapılandırmak Azure’da henüz kullanılamayan iOS Eğitim yapılandırmaları gerektirir.  Bu işlev yakında eklenecektir.

### <a name="device-management"></a>Cihaz yönetimi

#### <a name="provide-remote-assistance-to-android-devices-using-teamviewer----675418---"></a>TeamViewer kullanarak Android cihazları için uzaktan yardım sağlama <!-- 675418 -->

Intune, Android cihaz çalıştıran kullanıcılarınıza uzaktan yardım etmenizi sağlamak için artık ayrı satın alınan [TeamViewer](https://www.teamviewer.com) yazılımını kullanabilir. Daha fazla bilgi için bkz. [Intune ile yönetilen Android cihazlar için uzaktan yardım sağlama](device-profile-android-teamviewer.md).

### <a name="app-management"></a>Uygulama yönetimi

#### <a name="new-app-protection-policies-conditions-for-mam----679864---"></a>MAM için yeni uygulama koruma ilkesi koşulları <!-- 679864 -->

Artık kayıt kullanıcıları olmadan MAM için aşağıdaki ilkeleri zorunlu tutan bir gereksinim ayarlayabilirsiniz:

- En düşük uygulama sürümü
- En düşük işletim sistemi sürümü
- Hedeflenen uygulamanın en düşük Intune APP SDK’sı sürümü (yalnızca iOS)

Bu özellik hem Android hem de iOS’ta kullanılabilir. Intune; işletim sistemi platformu sürümleri, uygulama sürümleri ve Intune APP SDK’sı için en düşük sürüm zorlamasını destekler. iOS’ta, SDK’nın tümleştirildiği uygulamalar da SDK düzeyinde en düşük sürüm zorlaması ayarlayabilir. Yukarıda açıklanan üç farklı düzeyde uygulama koruma ilkesi aracılığıyla belirlenen en düşük gereksinimler karşılanmazsa kullanıcı hedeflenen uygulamaya erişemez. Bu noktada, kullanıcı hesabını kaldırabilir (çok kimlikli uygulamalarda), uygulamayı kapatabilir veya işletim sistemi veya uygulama sürümünü güncelleştirebilir.

İşletim sistemi veya uygulama yükseltmesi öneren ve engelleyici olmayan bir bildirim sağlamak için ek ayarlar da yapılandırabilirsiniz. Bu bildirim kapatılabilir ve uygulama normal şekilde kullanılabilir.

Daha fazla bilgi için bkz. [iOS uygulama koruma ilkesi ayarları](app-protection-policy-settings-ios.md) ve [Android uygulama koruma ilkesi ayarları](app-protection-policy-settings-android.md).

#### <a name="configure-app-configurations-for-android-for-work----621621---"></a>Android for Work için uygulama yapılandırmaları ayarlayın <!-- 621621 -->
Mağazadaki bazı Android uygulamaları, bir BT yöneticisinin bir uygulamanın iş profilinde nasıl çalışacağını denetlemesine izin veren yönetilen yapılandırma seçeneklerini destekler. Intune ile artık bir uygulama tarafından desteklenen yapılandırmaları görüntüleyebilir ve bunları bir yapılandırma tasarımcısı veya JSON düzenleyicisi ile Azure portalından yapılandırabilirsiniz. Daha fazla bilgi için bkz. [Android for Work için uygulama yapılandırmaları kullanma](app-configuration-policies-use-android.md).

#### <a name="new-app-configuration-capability-for-mam-without-enrollment----677969---"></a>Kayıt olmadan MAM için yeni uygulama yapılandırma özelliği <!-- 677969 -->
Artık kayıt kanalı olmadan MAM ile uygulama yapılandırma ilkeleri oluşturabilirsiniz. Bu özellik, mobil cihaz yönetimi (MDM) uygulama yapılandırmasında kullanılabilir uygulama yapılandırma ilkelerine eşdeğerdir. Kayıt olmadan MAM kullanılan uygulama yapılandırması örneği için bkz. [Microsoft Intune'la Managed Browser ilkelerini kullanarak İnternet erişimini yönetme](app-configuration-managed-browser.md).

#### <a name="configure-allowed-and-blocked-url-lists-for-the-managed-browser----682960---"></a>Managed Browser için izin verilen ve engellenen URL listelerini yapılandırma <!-- 682960 -->
Artık Azure portalındaki uygulama yapılandırma ayarlarını kullanarak Intune Managed Browser için izin verilen ve engellenen etki alanları ve URL’ler listesi yapılandırabilirsiniz. Bu ayarlar yönetilen bir cihazda mı yoksa yönetilmeyen bir cihazda mı kullanıldığına bakılmaksızın yapılandırılabilir. Daha fazla bilgi için bkz. [Microsoft Intune'la Managed Browser ilkelerini kullanarak İnternet erişimini yönetme](app-configuration-managed-browser.md).

#### <a name="app-protection-policy-helpdesk-view----1069473---"></a>Uygulama koruma ilkesi yardım masası görünümü <!-- 1069473 -->
BT Yardım Masası kullanıcıları, artık kullanıcı lisans durumu ve Sorun Giderme dikey penceresinde kullanıcılara atanan uygulama koruma ilkesi uygulamalarının durumunu denetleyebilir. Ayrıntılar için bkz. [Sorun giderme](./help-desk-operators.md).

### <a name="device-configuration"></a>Cihaz yapılandırması

#### <a name="control-website-visits-on-ios-devices----723832---"></a>iOS cihazlarda web sitesi ziyaretlerini denetleme <!-- 723832 -->
iOS cihazı kullanıcılarının ziyaret edebileceği web sitelerini aşağıdaki iki yöntemden birini kullanarak denetleyebilirsiniz:

- Apple'ın yerleşik web içeriği filtresini kullanarak izin verilen ve engellenen URL'leri ekleyin.

- Safari tarayıcısı tarafından yalnızca belirli web sitelerine erişilmesine izin verin. Belirttiğiniz siteler için Safari'de yer işaretleri oluşturulur.

Daha fazla bilgi için bkz. [iOS cihazları için web içeriği filtresi ayarları](web-content-filter-settings-ios.md).

#### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Android for Work uygulamaları için cihaz izinlerini önceden yapılandırma <!-- 621614 -->
Android for Work cihazı iş profillerine dağıtılan uygulamalarda, artık tek tek uygulamalar için izin durumunu yapılandırabilirsiniz.  Varsayılan olarak, konuma veya cihaz kamerasına erişim gibi cihaz izinlerine ihtiyacı olan Android uygulamaları kullanıcıdan izinleri kabul etmesini veya reddetmesini ister.  Örneğin, uygulama cihazın mikrofonunu kullanıyorsa, son kullanıcıdan mikrofonu kullanmak için uygulamaya izin vermesi istenir. Bu özellik, son kullanıcılar için izinleri tanımlamanıza olanak tanır.  İzinleri a) kullanıcıya bildirimde bulunmadan otomatik olarak reddedilecek şekilde b) kullanıcıya bildirimde bulunmadan otomatik olarak onaylanacak şekilde veya c) kullanıcıya kabul etmesi veya reddetmesi için sorulacak şekilde yapılandırabilirsiniz. Daha fazla bilgi için bkz. [Microsoft Intune’da Android for Work cihaz kısıtlama ayarları](device-restrictions-android-for-work.md).

#### <a name="define-app-specific-pin-for-android-for-work-devices----728976-1102534---"></a>Android for Work cihazlarında uygulamaya özgü PIN’i tanımlama <!-- 728976, 1102534 -->
Android for Work cihazı olarak yönetilen ve bir iş profili bulunan Android 7.0 ve üzeri cihazlarda, yöneticinin yalnızca iş profilindeki uygulamalar için geçerli olacak bir geçiş kodu ilkesi tanımlamasına izin verilir.  Şu seçenekler mevcuttur:

- Yalnızca cihaz genelinde bir geçiş kodu ilkesi tanımlama - Bu, kullanıcının tüm cihaz kilidini açmak için kullanması gereken geçiş kodudur.
- Yalnızca bir iş profili geçiş kodu ilkesi tanımlama - İş profilindeki bir uygulama her açıldığında kullanıcılardan geçiş kodunu girmesi istenir.
- Hem cihaz hem iş profili ilkesi tanımlama - BT yöneticisinin farklı güç düzeylerinde hem cihaz geçiş kodu ilkesi hem de iş profili geçiş kodu ilkesi tanımlama seçeneği vardır (örneğin, cihazın kilidini açmak için dört basamaklı bir PIN, ancak herhangi bir iş uygulamasını açmak için altı basamaklı bir PIN).

Daha fazla bilgi için bkz. [Microsoft Intune’da Android for Work cihaz kısıtlama ayarları](device-restrictions-android-for-work.md).

> [!NOTE]
> Bu özellik yalnızca Android 7.0 ve üzeri sürümlerde kullanılabilir.  Varsayılan olarak, son kullanıcı ayrı tanımlanmış iki PIN kullanabilir veya tanımlanmış olan iki PIN’den en güçlü olanı seçebilir.

#### <a name="new-settings-for-windows-10-devices----978585---"></a>Windows 10 cihazları için yeni ayarlar <!-- 978585 -->
Kablosuz ekranlar, cihaz bulma, görev geçişi ve SIM kartı hata iletileri gibi özellikleri denetleyen yeni [Windows cihaz kısıtlama ayarları](device-restrictions-windows-10.md) ekledik.

#### <a name="updates-to-certificate-configuration----918991-and-823198---"></a>Sertifika yapılandırması güncelleştirmeleri <!-- 918991 and 823198 -->
Bir SCEP sertifika profili oluştururken, <strong>Konu adı biçimi</strong> için <strong>Özel</strong> seçeneği iOS, Android ve Windows cihazları için kullanılabilir. Bu güncelleştirmeden önce, <strong>Özel</strong> alanı yalnızca iOS cihazları için kullanılabiliyordu. Daha fazla bilgi için bkz. [SCEP sertifika profili oluşturma](certificates-scep-configure.md#create-a-scep-certificate-profile).

Bir PKCS sertifika profili oluştururken, **Konu diğer adı** için **Özel Azure AD özniteliği** kullanılabilir. **Departman** seçeneği, **Özel Azure AD özniteliği** seçtiğinizde kullanılabilir. Daha fazla bilgi için bkz. [PKCS sertifika profili oluşturma](certficates-pfx-configure.md#create-a-pkcs-certificate-profile).

#### <a name="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode----662059---"></a>Bir Android cihazı bilgi noktası modunda olduğunda çalışabilen birden çok uygulama yapılandırma <!-- 662059 -->
Bir Android cihazı bilgi noktası modundayken, önceden çalışmasına izin verilen yalnızca bir uygulama yapılandırmanıza izin veriliyordu. Artık uygulama kimliği, mağaza kimliği veya zaten yönettiğiniz Android uygulamasını seçerek birden fazla uygulamayı yapılandırabilirsiniz. Daha fazla bilgi için bkz. [Bilgi noktası modu ayarları](device-restrictions-android.md#kiosk).



## <a name="april-2017"></a>Nisan 2017

### <a name="support-for-managing-the-apple-classroom-app"></a>Apple Classroom uygulamasını yönetme desteği
Artık iOS Classroom uygulamasını iPad cihazlarında yönetebilirsiniz. Doğru sınıf ve öğrenci verileriyle Classroom uygulamasını öğretmenin iPad cihazına kurun ve sınıfa kayıtlı öğrencilerin iPad cihazlarını uygulamayı kullanarak denetlemek için yapılandırın.
Ayrıntılar için bkz. [iOS eğitim ayarlarını yapılandırma](education-settings-configure-ios.md).

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Android uygulamaları için yönetilen yapılandırma seçenekleri desteği <!-- 621621 -->
Playstore’da yer alan ve yönetilen yapılandırma seçeneklerini destekleyen Android uygulamaları, artık Intune tarafından yapılandırılabilir.  Bu özellik, BT ekibinin bir uygulama tarafından desteklenen yapılandırma değerlerinin listesini görüntülemesini sağlar ve bu değerlerin yapılandırılması için kılavuzlu bir birinci sınıf kullanıcı arabirimi sunar.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Karmaşık PIN'ler için yeni Android ilkesi <!-- 722069 -->
Artık Android 5.0 ve üzeri çalıştıran cihazların Android cihaz profilinde Sayısal karmaşık türünde [parola](device-restrictions-android.md#password) gereksinimi belirleyebilirsiniz.  Bu ayarı kullanarak cihaz kullanıcılarının 1111 veya 1234 gibi tekrar eden ya da ardışık rakamlardan oluşan PIN'ler oluşturmasını engelleyebilirsiniz.

### <a name="additional-support-for-android-for-work-devices"></a>Android for Work cihazları için ek destek
- **Parola ve iş profili ayarlarını yönetin** <!-- 612808 -->

  Bu yeni Android for Work cihaz kısıtlama ilkesi artık yönettiğiniz Android for Work cihazlarında parola ve iş profili ayarlarını yönetmenizi sağlar.

- **İş ve kişisel profiller arasında veri paylaşımına izin verin** <!-- 1045102 -->

Bu Android for Work cihaz kısıtlama profili artık iş ve kişisel profiller arasında veri paylaşımını yapılandırmanıza yardımcı olan yeni seçenekler sunar.

- **İş ve kişisel profiller arasında kopyalama ve yapıştırma işlemlerini kısıtlama** <!-- 1046094 -->

  Android for Work cihazları için yeni bir özel cihaz profili, artık iş ve kişisel uygulamalar arasında kopyala ve yapıştır eylemlerini kısıtlayabilmenizi sağlar.

Daha fazla bilgi için bkz. [Android for Work için cihaz kısıtlamaları](device-restrictions-android-for-work.md).

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>iOS ve Android cihazlara LOB uygulamaları atama <!-- 1057568 -->
Artık [iOS](lob-apps-ios.md) (.ipa dosyaları) ve [Android](lob-apps-android.md) (.apk dosyaları) için iş kolu (LOB) uygulamalarını kullanıcılara veya cihazlara atayabilirsiniz.


###  <a name="new-device-policies-for-ios----723774-723815-723826-723830---"></a>iOS için yeni cihaz ilkeleri <!-- 723774, 723815, 723826, 723830 -->
- **Giriş ekranındaki uygulamalar** - Kullanıcıların [iOS cihazlarının giriş ekranında](home-screen-settings-ios.md) göreceği uygulamaları denetler. Bu ilke, Giriş ekranının düzenini değiştirir ancak herhangi bir uygulama dağıtmaz.

- **AirPrint cihazlarıyla bağlantı** - Bir iOS cihazı son kullanıcılarının bağlanabileceği [AirPrint cihazlarını](air-print-settings-ios-macos.md) (ağ yazıcılarını) denetler.

- **AirPlay cihazlarıyla bağlantı** - Bir iOS cihazı son kullanıcılarının bağlanabileceği [AirPlay cihazlarını](airplay-settings-ios.md) (Apple TV gibi) denetler.

- **Özel kilit ekranı iletisi** - Kullanıcıların iOS cihazlarının kilit ekranında varsayılan kilit ekranı iletisi yerine göreceği özel bir ileti yapılandırır. Daha fazla bilgi için bkz. [iOS cihazlarında kayıp modunu etkinleştirme](device-lost-mode.md)

### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>iOS uygulamaları için anında iletme bildirimlerini kısıtlama <!-- 723767 -->
Bir Intune cihaz kısıtlama profilinde iOS cihazlar için artık aşağıdaki [bildirim ayarlarını](app-notification-settings-ios.md) yapılandırabilirsiniz:

- Belirli bir uygulama için bildirimleri tamamen açma veya kapatma.
- Belirli bir uygulama için bildirim merkezindeki bildirimleri açma veya kapatma.
- Uyarı için **Yok**, **Başlık** veya **Uyarı** türünü belirleme.
- Bu uygulama için rozetlere izin verilip verilmeyeceğini belirleme.
- Bildirim seslerine izin verilip verilmeyeceğini belirleme.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>iOS uygulamalarını otonom tek uygulama modunda çalışacak şekilde yapılandırma <!-- 737837 -->
Bir Intune cihaz profili kullanarak belirtilen uygulamaları artık [otonom tek uygulama modunda](device-restrictions-ios.md#autonomous-single-app-mode-supervised-only) çalışacak şekilde iOS cihazlarını yapılandırabilirsiniz. Bu mod yapılandırılıp uygulama çalıştırıldığında cihaz yalnızca belirtilen uygulamayı çalıştıracak şekilde kilitlenir. Buna örnek olarak kullanıcıların cihazda test çözmesini sağlayan bir uygulama verilebilir. Uygulamanın eylemleri tamamlandığında veya bu ilkeyi kaldırdığınızda cihaz normal durumuna geri döner.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>iOS cihazlarda e-posta ve web üzerinde gezinme için güvenilen etki alanlarını yapılandırma <!-- 723765 -->
Artık bir iOS cihaz kısıtlama profilinden aşağıdaki [etki alanı ayarlarını](device-restrictions-ios.md#domains) yapılandırabilirsiniz:

- **İşaretlenmemiş e-posta etki alanları** - Son kullanıcı tarafından gönderilen veya alınan ve burada belirttiğiniz etki alanlarıyla eşleşmeyen e-postalar, güvenilmeyen olarak işaretlenir.

- **Yönetilen web etki alanları** - Burada belirttiğiniz URL'lerden indirilen belgeler, yönetilen belgeler olarak değerlendirilir (yalnızca Safari).  

- **Safari otomatik parola doldurma etki alanları (yalnızca denetimli)** - Kullanıcılar yalnızca burada belirttiğiniz desenlerle eşleşen URL'lerdeki parolaları Safari'ye kaydedebilir. Bu ayarı kullanabilmeniz için cihazın denetimli modda olması ve birden fazla kullanıcı için yapılandırılmış olmaması gerekir. (iOS 9.3 ve üzeri)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>iOS Şirket Portalında VPP uygulamaları kullanılabilir <!-- 748782 -->
iOS toplu satın alınan (VPP) uygulamalarını son kullanıcılara artık **Kullanılabilir** yüklemeler olarak atayabilirsiniz. Son kullanıcıların uygulamayı yükleyebilmek için bir Apple Store hesabına sahip olmaları gerekir.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>Apple VPP Store'dan alınan eKitapları eşitleme <!-- 800878 -->
Apple Volume Purchase Program mağazasından satın aldığınız kitapları artık Intune ile [eşitleyebilir](vpp-apps-ios.md) ve kullanıcılara atayabilirsiniz.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Samsung Knox Standard cihazları için birden çok kullanıcı yönetimi <!-- 971988 -->
Samsung Knox Standard çalıştıran cihazlarda artık Intune ile [birden çok kullanıcı yönetimi](android-enroll.md) gerçekleştirilebilir. Başka bir deyişle kullanıcılar Azure Active Directory kimlik bilgilerini kullanarak cihazda oturum açıp kapatabilir ve cihaz kullanım durumundan bağımsız olarak merkezden yönetilir.  Son kullanıcılar oturum açtığında uygulamalara erişir ve kendilerine uygulanan ilkeleri alır. Kullanıcılar oturumu kapattığında tüm veriler silinir.

### <a name="additional-windows-device-restriction-settings----818566---"></a>Ek Windows cihaz kısıtlama ayarları <!-- 818566 -->
Ek Edge tarayıcısı desteği, cihaz kilit ekranı özelleştirmesi, başlat menüsü özelleştirmeleri, Windows Spot araması duvar kağıdı ve proxy ayarı gibi ek [Windows cihaz kısıtlama ayarları](device-restrictions-windows-10.md) için destek ekledik.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Windows 10 Creators Update için birden çok kullanıcı desteği <!-- 822547 -->
Windows 10 Creators Update çalıştıran ve Azure Active Directory etki alanına katılmış olan cihazlar için [birden çok kullanıcı yönetimi](windows-enroll.md) desteği ekledik. Bu, değişik standart kullanıcılar cihazlarında Azure AD kimlik bilgileriyle oturum açtıklarında, kullanıcı adlarına atanan tüm uygulama ve ilkeleri alacakları anlamına gelir. Kullanıcılar, uygulama yükleme gibi self servis senaryoları için Şirket Portalını şu anda kullanamaz.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Windows 10 PC'ler Fresh Start<!-- 1004830 -->
Windows 10 PC'ler için yeni bir [Fresh Start cihaz eylemi](device-fresh-start.md) artık kullanılabilir.  Bu eylemi düzenlediğinizde PC'ye önceden yüklenmiş olan uygulamalar kaldırılır ve PC otomatik olarak en son Windows sürümüne güncelleştirilir. Bu eylem genellikle yeni bir PC ile gelen önceden yüklü OEM uygulamalarının kaldırılmasına yardımcı olması için kullanılabilir. Bu cihaz eylemi düzenlendiğinde kullanıcı verilerinin tutulup tutulmayacağını yapılandırabilirsiniz.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>Ek Windows 10 yükseltme yolları <!-- 903672 -->
Artık, cihazları aşağıdaki ek Windows 10 sürümlerine yükseltmek için bir [sürüm yükseltme ilkesi](edition-upgrade-configure-windows-10.md) oluşturabilirsiniz:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Windows 10 cihazlarını toplu kaydetme <!-- 747607 -->
Artık, Windows Yapılandırma Tasarımcısı (WCD) kullanarak Windows 10 Creators Update çalıştıran çok sayıda cihazın Azure Active Directory ve Intune’a katılmasını sağlayabilirsiniz. Azure AD kiracınız için [Toplu MDM kaydını](windows-bulk-enroll.md) etkinleştirmek için Windows Yapılandırma Tasarımcısı kullanarak cihazların Azure AD kiracınıza katılmasını sağlayan bir sağlama paketi oluşturun ve paketi toplu kaydetmek ve yönetmek istediğiniz şirkete ait cihazlara uygulayın. Paket cihazlarınıza uygulandıktan sonra cihazlar Azure AD’ye katılır, Intune’a kaydolur ve Azure AD kullanıcılarınızın oturum açmasına hazır hale gelir.  Azure AD kullanıcıları, bu cihazlarda standart kullanıcılardır ve atanan ilkeleri ve gerekli uygulamaları alırlar. Self servis ve Şirket Portalı senaryoları şu anda desteklenmemektedir.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----581122-736644---"></a>PIN ve yönetilen depolama konumları için yeni MAM ayarları <!-- 581122, 736644 -->
Mobil uygulama yönetimi (MAM) senaryolarında size yardımcı olacak iki yeni uygulama ayarı artık mevcuttur:

- **Cihaz PIN'i yönetildiğinde uygulama PIN'ini devre dışı bırak** - Kaydedilen cihazda bir cihaz PIN'i olup olmadığını algılar ve varsa uygulama koruma ilkeleri tarafından tetiklenen uygulama PIN'ini atlar. Bu ayar, kayıtlı cihazda MAM özellikli bir uygulamayı açan kullanıcılara gösterilen PIN istemi sayısının azaltılmasını sağlar. Bu özellik hem Android hem de iOS için kullanılabilir.

- **Şirket verilerinin kaydedilebileceği depolama hizmetlerini seçin** - Şirket verilerinin kaydedileceği depolama konumlarını belirtmenizi sağlar. Kullanıcılar seçilen depolama konumu hizmetlerine veri kaydedebilir ve listede olmayan diğer tüm depolama konumu hizmetleri engellenir.

  Desteklenen depolama konumu hizmetlerin listesi:

  - OneDrive
  - İş SharePoint Online
  - Yerel depolama

### <a name="help-desk-troubleshooting-portal----907448---"></a>Yardım masası sorun giderme portalı <!-- 907448 -->
Yeni [sorun giderme portalı](help-desk-operators.md), yardım masası operatörlerinin ve Intune yöneticilerinin, kullanıcıları ve cihazlarını görüntülemesine ve Intune teknik sorunlarını çözmek için görevler gerçekleştirmelerine izin verir.

## <a name="march-2017"></a>Mart 2017

### <a name="support-for-ios-lost-mode---431695--"></a>İOS Kayıp Modu desteği <!--431695-->
Intune, iOS 9.3 ve üzeri cihazlar için **Kayıp Modu** desteği ekledi. Artık bir cihazı kilitleyerek tüm kullanımını önleyebilir, cihaz kilit ekranında bir ileti ve iletişim telefon numarası görüntüleyebilirsiniz.

Bir yönetici Kayıp Modu’nu devre dışı bırakmadıkça son kullanıcılar cihazın kilidini açamaz. Kayıp modu etkin olduğunda, **Cihazı bul** eylemini kullanarak cihazın coğrafi konumunu Intune konsolundaki bir haritada görüntüleyebilirsiniz.

Cihazın DEP aracılığıyla kaydedilen ve denetimli modda olan, şirkete ait bir iOS cihazı olması gerekir.

Daha fazla bilgi için bkz. [Microsoft Intune cihaz yönetimi nedir](device-management.md)?

### <a name="improvements-to-device-actions-report---677150--"></a>Cihaz Eylemler raporu geliştirmeleri <!--677150-->
Performansı artırmak için Cihaz Eylemler raporunda geliştirmeler yaptık. Bundan sonra ek olarak rapor durumuna göre filtre uygulayabilirsiniz. Örneğin, yalnızca tamamlanan cihaz eylemlerini gösterecek şekilde rapora filtre uygulayabilirsiniz."

### <a name="custom-app-categories---748805--"></a>Özel uygulama kategorileri <!--748805-->
Artık Intune’a eklediğiniz uygulamalar için kategoriler oluşturabilir, düzenleyebilir ve atayabilirsiniz. Şu anda kategoriler yalnızca İngilizce olarak belirtilebilir.
Bkz. [Intune'a uygulama ekleme](apps-add.md).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>Kaydedilmemiş cihaz kullanıcılarına LOB uygulamaları atama <!--748823-->
Cihazları Intune'a kayıtlı olsun ya da olmasın, artık kullanıcılara mağazadan iş kolu uygulamaları atayabilirsiniz. Kullanıcıların cihazları Intune’a kayıtlı değilse yüklemek için Şirket Portalı uygulaması yerine Şirket Portalı web sitesine gitmeleri gerekir.

### <a name="new-compliance-reports---846671--"></a>Yeni uyumluluk raporları <!--846671-->
Artık şirketinizdeki cihazların uyumluluk durumunu size sağlayan ve kullanıcılarınızın karşılaştığı uyumluluk sorunlarını hızlı bir şekilde gidermenize olanak tanıyan uyumluluk raporlarına sahipsiniz. Aşağıdaki konular hakkındaki bilgileri görüntüleyebilirsiniz:

- Cihazların genel uyumluluk durumu
- Ayrı bir ayarın uyumluluk durumu
- Ayrı bir ilkenin uyumluluk durumu

Bu raporları ayrıca bir cihazı incelemek ve cihazı etkileyen belirli ayar ve ilkeleri görüntülemek için de kullanabilirsiniz.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Apple kayıt senaryolarına doğrudan erişim <!--951869-->
Intune, Azure portalındaki Cihaz Kaydetme iş yükünü kullanarak Apple kayıt senaryolarına doğrudan erişimi Ocak 2017 sonrasında oluşturulan Intune hesapları için etkinleştirdi. Daha önce, Apple kayıt önizleme sürümüne yalnızca Azure portalı bağlantıları ile erişilebiliyordu. Bu özelliklerin Azure’da kullanılabilmesi için, Ocak 2017 öncesi oluşturulan Intune hesaplarında tek seferlik bir geçiş yapılması gerekir. Geçiş için zaman çizelgesi henüz açıklanmamıştır, ancak konuya ilişkin ayrıntılar olabildiğince çabuk duyurulacaktır. Mevcut hesabınız önizleme sürümüne erişemiyorsa, yeni deneyimi test etmek için bir deneme hesabı oluşturmanızı kesinlikle öneririz.


## <a name="february-2017"></a>Şubat 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Mobil cihaz kaydını kısıtlama özelliği <!--747600, 795782-->
Intune, katılmasına izin verilecek mobil cihaz platformlarını denetleyen yeni kayıt kısıtlamaları ekliyor. Intune, mobil cihaz platformlarını iOS, macOS, Android, Windows ve Windows Mobile şeklinde ayırıyor.

* Mobil cihaz kaydının kısıtlanması, bilgisayar istemcisi kaydını etkilemez.  
* Yalnızca iOS ve Android için kişisel cihazların kaydedilmesini engelleyen ek seçenek vardır.

Intune, BT yöneticileri [bu makalede](https://docs.microsoft.com/intune-classic/deploy-use/manage-corporate-owned-devices) anlatılan şekilde kuruluş cihazı olarak işaretlemediği sürece tüm yeni cihazları kişisel cihaz olarak işaretler.

### <a name="view-all-actions-on-managed-devices---677150--"></a>Yönetilen cihazlardaki tüm eylemleri görüntüleme <!--677150-->
Yeni __Cihaz Eylemleri__ raporu cihazları fabrika ayarlarına sıfırlama gibi uzaktan gerçekleştirilen eylemleri kimin yaptığını ve ilgili eylemin durumunu göstermektedir. Bkz. [Cihaz yönetimi nedir?](device-management.md)

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Yönetilmeyen cihazlar atanmış uygulamalara erişebilir <!--664691-->
Şirket Portalı web sitesinde yapılan tasarım değişikliklerinin bir parçası olarak iOS ve Android kullanıcılar yönetilmeyen cihazlarında kendilerine "kayıtsız kullanılabilir" olarak atanmış uygulamaları yükleyebilecek. Kullanıcılar Intune kimlik bilgilerini kullanarak Şirket Portalı web sitesine girebilecek ve kendilerine atanan uygulamaların listesini görebilecek. "Kayıtsız kullanılabilir" uygulamaların uygulama paketleri Şirket Portalı web sitesinden indirilebilir. Yükleme için kayıt gerektiren uygulamalar bu değişikten etkilenmeyecek ve bu uygulamaları yüklemek isteyen kullanıcılardan cihazlarını kaydetmeleri istenecektir.

### <a name="custom-app-categories---748805--"></a>Özel uygulama kategorileri <!--748805-->
Artık Intune’a eklediğiniz uygulamalar için kategoriler oluşturabilir, düzenleyebilir ve atayabilirsiniz. Şu anda kategoriler yalnızca İngilizce olarak belirtilebilir.
Bkz. [Intune'a uygulama ekleme](apps-add.md).

### <a name="display-device-categories---814654--"></a>Cihaz kategorilerini görüntüleme <!--814654-->
Artık cihaz kategorisini cihaz listesinde ayrı bir sütunda görüntüleyebilirsiniz. Kategoriyi ayrıca cihaz özellikleri dikey penceresinin özellikler bölümünden de düzenleyebilirsiniz. Bkz. [Intune'a uygulama ekleme](apps-add.md).

### <a name="configure-windows-update-for-business-settings---776716--"></a>İşletmeler için Windows Update ayarlarını yapılandırma <!--776716-->

Hizmet olarak Windows, Windows 10 güncelleştirmeleri sağlamanın yeni yoludur. Windows 10’dan itibaren tüm yeni Özellik Güncelleştirmeleri ve Kalite Güncelleştirmeleri, önceki güncelleştirmelerin hepsinde yer alan içerikleri de kapsayacaktır. Böylece, en son güncelleştirmeyi yüklediğiniz sürece Windows 10 cihazlarınızın tamamen güncel olduğundan emin olabilirsiniz. Önceki Windows sürümlerinin aksine, artık güncelleştirmelerin tamamını yüklemeniz gerekir. Güncelleştirmenin yalnızca bir parçası yüklenemez.

İşletmeler için Windows Update’i kullanarak güncelleştirme yönetimi deneyimini, cihaz grupları için tek tek güncelleştirmelerin onaylanması gerekmeyecek şekilde basitleştirebilirsiniz. Ortamlarınızdaki riski yönetmek amacıyla hala bir güncelleştirme dağıtım stratejisi yapılandırabilirsiniz. Böyle yaptığınızda Windows Update güncelleştirmelerin doğru zamanda yüklenmesini sağlayacaktır. Microsoft Intune, cihazlarda güncelleştirme ayarlarının yapılandırılabilmesini sağlar ve güncelleştirme yüklemelerini erteleme olanağı tanır. Intune, güncelleştirmeleri değil yalnızca güncelleştirme ilkesi atamalarını depolar. Cihazlar, güncelleştirmeler için doğrudan Windows Update’e erişir. **Windows 10 güncelleştirme kademelerini** yapılandırmak ve yönetmek için Intune’u kullanın. Güncelleştirme kademesi, Windows 10 güncelleştirmelerinin ne zaman ve nasıl yükleneceğini yapılandıran bir dizi ayar içerir. Daha ayrıntılı bilgiler için bkz. [İşletmeler için Windows Update ayarlarını yapılandırma](windows-update-for-business-configure.md).
