---
title: Erken sürüm
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b6ca8108924c6c062da0d0ef56ab5b68635dd9ca
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="the-early-edition-for-microsoft-intune---april-2018"></a>Microsoft Intune için erken sürüm - Nisan 2018

**Erken sürüm**, Microsoft Intune'un gelecek sürümlerinde kullanıma sunulacak yeni özelliklerin bir listesini sunar. Bu bilgiler kısıtlı bir kapsamla verilmektedir ve değiştirilebilir. Bu bilgileri şirket dışından kimselerle paylaşmayın. Burada listelenen özelliklerden bazılarının son tarihe yetişememe riski vardır ve gelecek sürüme ertelenebilir. Diğer özellikler, müşterinin kullanımına hazır olduğundan emin olmak için pilot (sürüyor) aşamasında test edilmektedir. Herhangi bir sorunuz veya endişeniz varsa lütfen Microsoft ürün grubu ilgili kişisiyle bağlantı kurun.

Bu sayfa düzenli aralıklarla güncelleştirilir. Ek güncelleştirmeleri daha sonra denetleyin.

> [!Note]
>Intune için aşağıdaki değişiklikler geliştirilme aşamasındadır. Yeni karma özellikler hakkında daha fazla bilgi için [Karma Yenilikler](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) sayfasını gözden geçirin.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Azure portalında Intune

<!-- 1804 start -->

### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252-----from-1802--"></a>Endpoint Protection ayarlarına yeni Windows Defender Credential Guard ayarları eklendi <!--1102252 --><!--from 1802-->

Yeni [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard) ayarları, **Cihaz yapılandırması** > **Profiller** > **Endpoint Protection** bölümüne eklenecek. Eklenecek ayarlar aşağıdaki gibidir:

- Platform Güvenlik Düzeyi: Bir sonraki yeniden başlatmada Platform Güvenlik Düzeyi’nin etkinleştirilip etkinleştirilmeyeceğini belirtin. Sanallaştırma tabanlı güvenlik, Güvenli Önyükleme gerektirir. Sanallaştırma tabanlı güvenlik, isteğe bağlı olarak doğrudan bellek erişimi (DMA) korumaları kullanımıyla etkinleştirilebilir. DMA korumaları, donanım desteği gerektirir ve yalnızca doğru yapılandırılmış cihazlarda etkinleştirilir.
- Sanallaştırma Tabanlı Güvenlik: Bir sonraki yeniden başlatmada sanallaştırma tabanlı güvenliğin etkinleştirilip etkinleştirilmeyeceğini belirtin.
- Windows Defender Credential Guard: Sanallaştırma tabanlı güvenlik ile Credential Guard’ı etkinleştirerek, Güvenli Önyükleme ile Platform Güvenlik Düzeyi ve Sanallaştırma Tabanlı Güvenlik’in etkin olduğu bir sonraki yeniden başlatmada kimlik bilgilerinin korunmasına yardımcı olun. Kullanılabilir seçenekler **Devre dışı**, **UEFI kilidi ile etkin**, **Kilit olmadan etkin** ve **Yapılandırılmadı** şeklindedir.
  - “Devre dışı” seçeneği, “Kilit olmadan etkin” seçeneğiyle açılmış olan Credential Guard’ı uzaktan kapatır.

  - “UEFI kilidi ile etkin” seçeneği, Credential Guard’ın kayıt defteri anahtarı ile veya Grup İlkesi kullanılarak devre dışı bırakılamamasını sağlar. Bu ayarı kullandıktan sonra Credential Guard’ı devre dışı bırakmak için, UEFI’de belirtilen yapılandırmayı kaldırmak üzere Grup İlkesini “Devre Dışı” olarak ayarlamanız ve kullanıcısı fiziksel olarak mevcut olan her bir bilgisayardan güvenlik işlevselliğini kaldırmanız gerekir. UEFI yapılandırması devam ettiği sürece, Credential Guard etkindir.

  - “Kilit olmadan etkin” seçeneği, Credential Guard’ın Grup İlkesi kullanılarak uzaktan devre dışı bırakılmasına imkan verir. Bu ayarı kullanan cihazların en az Windows 10 (Sürüm 1511) çalıştırıyor olması gerekir.

  - “Yapılandırılmadı” seçeneği, ilke ayarını tanımlanmamış halde bırakır. Grup İlkesi, ilke ayarını kayıt defterine yazmaz ve bu nedenle bilgisayarlar ve kullanıcılar üzerinde hiçbir etkisi yoktur. Kayıt defterinde geçerli bir ayar varsa bu ayar değiştirilmeyecektir.

### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>Android’de MAM PIN’i için geçiş kodu desteği<!-- 1438086 -->

Intune yöneticileri, sayısal MAM PIN’i yerine geçiş kodu zorlamak için bir uygulama başlatma gereksinimi ayarlayabilecek. Bu gereksinim ayarlanırsa kullanıcının, MAM etkin uygulamalara erişim almadan önce bir geçiş kodu ayarlaması ve istendiğinde bunu kullanması gerekir. Geçiş kodu, en az bir özel karakter veya büyük/küçük harf içeren sayısal PIN’dir. Intune, sayısal PIN’e benzer bir şekilde geçiş kodunu destekler. Uzunluk alt sınırı belirler ve yönetici konsolunda karakter ile dizi tekrarlarına izin verir. Bu özellik, Android’de Şirket Portalı’nın en son sürümünü gerektirir. Bu özellik, iOS için zaten kullanılabilir durumdadır.

###  <a name="block-camera-and-screen-captures-on-android-for-work----1098977-eeready--"></a>Android for Work’te kamera ve ekran yakalamayı engelleme <!-- 1098977 eeready-->
Android cihazlar için cihaz kısıtlamaları yapılandırırken iki yeni engelleme özelliği kullanılabilir olacak: 
- Kamera: Cihazdaki tüm kameralara erişimi engeller
- Ekran yakalama: Ekran yakalamayı ve güvenli bir video çıkışına sahip olmayan görüntü cihazlarında gösterilen içeriği engeller

Android for Work’te geçerlidir.

### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>macOS için iş kolu (LOB) uygulamaları desteği <!-- 1473977 -->
Microsoft Intune, macOS LOB uygulamalarını Azure portalından yükleme olanağı sağlayacak. GitHub’da bulunan araç tarafından ön işlemden geçtikten sonra macOS LOB uygulamasını Intune’a ekleyebileceksiniz. Azure portalının **Intune** dikey penceresinden **Mobil uygulamalar**’ı seçin. **Mobil uygulamalar** dikey penceresinde **Uygulamalar** > **Ekle**’yi seçin. **Uygulama Ekle** dikey penceresinde, **İş kolu uygulaması**’nı seçin. 

### <a name="support-for-user-less-devices----1637553---"></a>Kullanıcısız cihazlar için destek <!-- 1637553 -->
Intune, Microsoft Surface Hub gibi bir kullanıcısız cihazda uyumluluk değerlendirme işlevini destekleyecek. Uyumluluk ilkesi, belirli cihazları hedefleyebilir. Böylece ilişkili kullanıcısı olmayan cihazlar için uyumluluk (ve uyumsuzluk) belirlenebilir.

### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Yerel Cihaz Güvenliği Seçenekleri ayarlarına ekler <!-- 1403702 -->
Windows 10 cihazlar için ek Yerel Cihaz Güvenliği Seçenekleri ayarları yapılandırabileceksiniz. Ek ayarlar; Microsoft Ağ İstemcisi, Microsoft Ağ Sunucusu, Ağ erişimi ve güvenlik ve Etkileşimli oturum açma bölümlerinde kullanılabilir olacak. Bu ayarları, bir Windows 10 cihaz yapılandırma ilkesi oluşturduğunuzda Endpoint Protection kategorisinde bulabilirsiniz.

### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>İlkelerin, uygulamaların, sertifika ve ağ profillerinin yüklenmesini gerektirme <!-- 1553555 -->
Intune, AutoPilot cihazlar hazırlanırken ilkeleri, uygulamaları ve sertifika ve ağ profillerini yükleyene kadar yöneticiler; son kullanıcıların Windows 10 RS4 masaüstüne erişimini engelleyebilecek.

### <a name="rules-for-removing-devices----1609459---"></a>Cihaz kaldırma kuralları <!-- 1609459 -->
Ayarladığınız süre boyunca (gün) iade edilmeyen cihazları otomatik olarak kaldırmanıza imkan veren yeni kurallar kullanılabilir olacak. Yeni kuralı görmek için **Intune** bölmesine gidin, **Cihazlar**’ı ve **Cihaz kaldırma kuralları**’nı seçin.

### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Windows 10 Enterprise RS4 Autopilot cihazlarda tüketici uygulamaları ve deneyimlerini engelleme<!-- 1621980 -->
Windows 10 Enterprise RS4 AutoPilot cihazlarınızda tüketici uygulama ve deneyimlerinin yüklenmesini önleyebileceksiniz. Bu özelliği görmek için **Intune** > **Cihaz kaydı** > **Windows kaydı** > **Windows AutoPilot profilleri** > **Yeni Oluştur** > **Kayıt ayarları**’na gidin. 

### <a name="advanced-threat-protection-integrated-with-intune----1629303---"></a>Intune ile tümleştirilmiş Gelişmiş Tehdit Koruması <!-- 1629303 -->
[Gelişmiş Tehdit Koruması (ATP)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection), Windows 10 cihazların risk düzeyini gösterir. Intune, Windows 10 cihazların uyumluluğunu değerlendirirken bu değerlendirmede ATP risk puanı da bulunur. Ağınızı korumaya yardımcı olması için ATP’yi koşullu erişim ile kullanabilirsiniz.

### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>macOS High Sierra 10.13.2+ cihazların kullanıcıları için yeni kayıt adımları <!--1734567 -->
macOS High Sierra 10.13.2, “Kullanıcı Onaylı” MDM kaydı kavramını sundu. Onaylı kayıtlar, gelecekte Intune’un güvenlik açısından hassas bazı ayarları yönetmesine izin verecek. Daha fazla bilgi için Apple’ın destek belgelerine bakın: https://support.apple.com/HT208019.

macOS Şirket Portalı kullanarak kaydedilen cihazlar, son kullanıcı Sistem Tercihleri’ni açıp kendisi onay sağlamadığı sürece “Kullanıcı Onaylı Değil” olarak değerlendirilecek. Bu nedenle macOS Şirket Portalı, macOS 10.13.2 ve üzeri cihazlardaki kullanıcıları artık kayıt işleminin sonunda kayıtlarını kendileri onaylamaları için yönlendiriyor. Kayıtlı bir cihaz, kullanıcı onaylı hale gelirse Intune yönetici konsolu bunu rapor eder.

### <a name="delete-autopilot-devices----1713650---"></a>Autopilot cihazları silme <!-- 1713650 -->
Intune yöneticileri, Autopilot cihazları silebilecekler.

### <a name="built-in-all-users-and-all-devices-group-for-android-for-work-afw-app-assignment----1813073---"></a>Android for Work (AFW) uygulama atamasında Yerleşik Tüm Kullanıcılar ve Tüm Cihazlar Grubu <!-- 1813073 -->
AFW uygulama ataması için yerleşik **Tüm Kullanıcılar** ve **Tüm Cihazlar** gruplarından yararlanabileceksiniz. Daha fazla bilgi için bkz. [Microsoft Intune’da uygulama atamalarını dahil etme ve dışlama](apps-inc-exl-assignments.md).

### <a name="improved-device-deletion-experience---1832333---"></a>Geliştirilmiş cihaz silme deneyimi <!--1832333 -->
Artık bir cihazı Intune’dan silmeden önce şirket verilerini kaldırmanız veya cihazı fabrika ayarlarına sıfırlamanız istenmeyecek.

Yeni deneyimi görmek için Intune’da oturum açın ve şunları seçin: **Cihazlar** > **Tüm cihazlar** > cihazın adı > **Sil**.

 Yine de onayı silmek/devre dışı bırakmak istiyorsanız **Sil** demeden önce standart yaşam döngüsü yolunu izleyip **Şirket verilerini kaldır** ve **Fabrika Sıfırlaması** seçeneklerini kullanabilirsiniz. 

### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Autopilot profilleri grup hedeflemeye taşınıyor <!-- 1877935 -->
AutoPilot dağıtım profilleri şu anda seçili cihazlara atanabiliyor. Nisan sonuna doğru bu profilleri şu şekilde atamaya başlayacaksınız:
- AutoPilot cihazları barındıran Azure AD grupları oluşturun
- İstenen profilleri bir Azure AD profiline atayın. AutoPilot profili artık bu gruptaki AutoPilot cihazlara atanmış olacak.

### <a name="play-sounds-on-ios-when-in-lost-mode----1629303---"></a>Kayıp modundayken iOS cihazda ses çalma <!-- 1629303 -->
Denetimli iOS cihazlar, Mobil Cihaz Yönetimi (MDM) [Kayıp Modu](device-lost-mode.md)’ndayken bir ses çalabilirsiniz (**Cihazlar** > **Tüm cihazlar** > bir iOS cihaz seçin > **Genel Bakış** > **Diğer**). Ses, cihaz Kayıp modundan çıkarılana veya kullanıcı sesi cihazda devre dışı bırakana kadar çalmaya devam eder. iOS 9.3 ve üzeri cihazlarda geçerlidir.

### <a name="use-a-custom-subject-name-on-scep-certificate----2064190---"></a>SCEP sertifikasında özel bir konu adı kullanma <!-- 2064190 -->
Bir SCEP sertifika profilinde özel bir konuda **OnPremisesSamAccountName** ortak adını kullanabileceksiniz. Örneğin `CN={OnPremisesSamAccountName})` kullanabilirsiniz.

### <a name="send-diagnostic-reports-in-company-portal-app-for-macos----2216677---"></a>macOS için Şirket Portalı uygulamasında tanılama raporu gönderme <!-- 2216677 -->
macOS cihazlar için Şirket Portalı uygulaması, kullanıcıların Intune il ilgili hataları raporlama şeklini iyileştirmek için güncelleştirilecek. Şirket Portalı uygulamasından çalışanlarınız şunları yapabilecek:
- Tanılama raporlarını doğrudan Microsoft geliştirici ekibine gönderme.
- Bir olay kimliğini şirketinizin destek BT ekibine e-posta ile gönderme.

### <a name="always-on-vpn-for-windows-10---1333666---"></a>Windows 10 için Her Zaman Açık VPN <!--1333666 -->

Şu anda [Her Zaman Açık](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on), OMA-URI kullanarak oluşturulmuş özel bir sanal özel ağ (VPN) profili ile Windows 10 cihazlarda kullanılabiliyor.

Bu güncelleştirmeyle yöneticiler, Windows 10 VPN profilleri için Her Zaman Açık’ı doğrudan Azure portalındaki Intune’da etkinleştirebilecek. Her Zaman Açık VPN profilleri şu durumlarda otomatik olarak bağlanacak:

- Kullanıcılar cihazlarında oturum açtığında
- Cihazdaki ağ değiştiğinde
- Cihaz ekranı kapandıktan sonra yeniden açıldığında

### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure----2172331---"></a>Apple MDM Anında İletme Sertifikası karşıya yükleme başarısızlığı için iyileştirilmiş hata iletisi <!-- 2172331 -->

Hata iletisi, mevcut bir MDM sertifikası yenilenirken aynı Apple kimliğinin kullanılması gerektiğini açıklayacak.

###  <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group----1449153-eeready---"></a>Cihaz profil grafiği ve durum listesi bir gruptaki tüm cihazları gösterir <!-- 1449153 eeready -->
Bir cihaz profili yapılandırdığınızda (**Cihaz yapılandırması** > **Profiller**), iOS gibi bir cihaz profili seçersiniz. Bu profili, iOS ve iOS olmayan cihazlar barındıran bir gruba atarsınız. Grafikteki sayı, profilin uygulandığı iOS *ve* iOS olmayan cihazları gösterir (**Cihaz yapılandırması** > **Profiller** > mevcut bir profili seçin > **Genel bakış**). **Genel bakış** sekmesinde grafiği seçtiğinizde, **Cihaz durumu** yalnızca gruptaki iOS cihazları değil, tüm cihazları listeler. 

Bu güncelleştirme ile grafik (**Cihaz yapılandırması** > **Profiller** > mevcut bir profili seçin > **Genel bakış**) yalnızca belirli bir cihaz profili sayısını gösterecek. Örneğin yapılandırma cihaz profili iOS cihazlarda geçerliyse grafik yalnızca iOS cihaz sayısını gösterecek. Grafik seçilip **Cihaz durumu** açıldığında yalnızca iOS cihazlar listelenecek.

Bu güncelleştirme hazırlanırken kullanıcı grafiği geçici olarak kaldırılmıştır. 


<!-- 1803 start -->

#### <a name="multiple-exchange-connector-support----2070451---"></a>Birden çok Exchange Connector desteği <!-- 2070451 -->

Artık kiracı başına tek bir Microsoft Intune Exchange Connector’la sınırlı değilsiniz. Intune, birden çok Exchange Connector’u destekleyeceği için Intune koşullu erişimini birden çok şirket içi Exchange kuruluşunda ayarlayabilirsiniz.

Intune şirket içi Exchange bağlayıcısıyla, cihazın Intune'a kayıtlı olup olmadığına ve Intune cihaz uyumluluk ilkelerine uyup uymadığına bağlı olarak şirket içi Exchange posta kutularınıza cihaz erişimini ayarlayabilirsiniz. Bağlayıcıyı ayarlamak için, Intune şirket içi Exchange bağlayıcısını Azure portalından indirir ve Exchange kuruluşunuzdaki bir sunucuya yüklersiniz. Microsoft Intune panosunda **Şirket içi erişim**'i seçin ve ardından **Kurulum**'un altında **Exchange ActiveSync bağlayıcısı**'nı seçin. Exchange şirket içi bağlayıcısını indirin ve Exchange kuruluşunuzdaki bir sunucuya yükleyin. Artık kiracı başına tek Exchange bağlayıcısıyla sınırlı olmadığınıza göre, başka Exchange kuruluşlarınız varsa her ek Exchange kuruluşu için aynı süreci izleyip bağlayıcı indirebilir ve yükleyebilirsiniz.

### <a name="support-coming-for-new-cisco-anyconnect-client-for-ios----1333708---"></a>iOS için yeni Cisco AnyConnect istemcisi desteği geliyor <!-- 1333708 -->

iOS için Cisco AnyConnect'e yönelik oluşturulan yeni VPN profilleri Cisco AnyConnect 4.0.7x ve üstüyle çalışacaktır. Mevcut iOS Cisco AnyConnect VPN profilleri **Cisco Eski AnyConnect** olarak etiketlenecek ve bugün olduğu gibi Cisco AnyConnect 4.0.5x ile çalışmaya devam edecektir.

> [!NOTE]
> Bu değişiklik yalnızca iOS'ye yöneliktir; Android, Android for Work ve macOS için yine tek Cisco AnyConnect seçeneği olacaktır.

#### <a name="more-information"></a>Daha fazla bilgi

Yeni uygulamayı desteklemek için yeni bir iOS Cisco AnyConnect VPN profili oluşturmalısınız çünkü yeni Cisco AnyConnect uygulaması ve Cisco Eski AnyConnect uygulaması ayrı uygulamalardır. Ortamınızda AnyConnect istemcisini yönetiyorsanız, yeni Cisco AnyConnect uygulamasını da dağıtmanız gerekir. Ayrıca yükseltmeyi tamamlamak için, Cisco Eski AnyConnect VPN profilini silmeli ve Cisco Eski AnyConnect uygulamasını kaldırmalısınız.

İlk sürümde yeni AnyConnect istemcisi için ağ erişim denetimi (NAC) tümleştirmesi çalışmaz. Gelecek Intune sürümlerinden birinde NAC tümleştirmesi sağlamak için Cisco'yla çalışmaları sürdürüyoruz.

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Gerekli iş kolu (LOB) uygulamalarını Windows 10 Masaüstü cihazlarında Tüm Kullanıcılara dağıtabilme <!-- 1627835 RS4 -->
Müşteriler gerekli iş kolu Windows 10 uygulamalarını cihaz bağlamlarına yüklemek üzere dağıtabilecek. Böylelikle bu uygulamalar cihazdaki tüm kullanıcılara sağlanabilir. Bu yalnızca Windows 10 Masaüstü cihazları için geçerlidir.

### <a name="company-portal-enrollment-improved----1874230--"></a>Şirket Portalı kaydı geliştirildi <!-- 1874230-->
Windows 10 derleme 1703'te ve üstünde Şirket Portalı'nı kullanarak cihaz kaydı yapan kullanıcılar, uygulamadan çıkmadan kaydın ilk adımını tamamlayabilecekler.

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Android için Şirket Portalı uygulamasında Yardım ve Geri Bildirim deneyimini güncelleştirme <!--1631531 -->

Android uygulamalarına yönelik en iyi yöntemlerle uyumlu olacak şekilde, Android için Şirket Portalı uygulamasında Yardım ve Geri Bildirim deneyimini güncelleştiriyoruz. Önümüzdeki birkaç ay içinde Android için Şirket Portalı uygulamasını güncelleştirerek **Yardım ve Geri Bildirim** menü öğesini **Yardım** ve **Geri Bildirim Gönder** menü öğelerine ayıracağız. Son kullanıcıları günlükleri Microsoft'a yüklemeye ve şirket desteğine sorunu açıklayan bir e-posta göndermeye yönlendirmek için, **Yardım** sayfasında **Sık Sorulan Sorular** bölümü ve **E-posta Desteği** düğmesi bulunacak. **Geri Bildirim Gönder** kullanıcıyı standart Microsoft geri bildirim gönderimine yönlendirecek ve kullanıcıdan "Bir şeyi beğendim" "Bir şeyi beğenmedim" veya "Bir fikrim var" arasında seçim yapması istenecek.

<!-- 1802 start -->

### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Eğitim profilleri için yeni yazıcı ayarları <!-- 1308900 -->

Eğitim profilleri için yeni ayarlar, **Yazıcılar** kategori: **Yazıcılar**, **Varsayılan yazıcı**, **Yeni yazıcı ekle** altında kullanılabilir olacak.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Uygulama koruma ilkeleri  <!-- 679615 -->
Intune Uygulama Koruma İlkeleri, tüm kiracıdaki tüm kullanıcılar için hızlı bir şekilde koruma sağlamaya yönelik genel ve varsayılan ilkeler oluşturma olanağı sunar.

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory web siteleri, Intune Managed Browser Uygulaması gerektirebilir ve Managed Browser’da (Genel Önizleme) Çoklu Oturum Açma’yı destekler <!-- 710595 -->   
Azure Active Directory (Azure AD) kullanarak, mobil cihazlarda web sitelerine erişimi Intune Managed Browser uygulaması ile kısıtlayabileceksiniz. Web sitesi verileri, Managed Browser’da güvende ve son kullanıcının kişisel verilerinden ayrı bir yerde olacaktır. Managed Browser ayrıca Azure AD ile korunan sitelerde Çoklu Oturum Açma işlevlerini de destekleyecektir. Managed Browser’da oturum açmak veya Intune tarafından yönetilen başka bir uygulamanın bulunduğu bir cihazda Managed Browser’ı kullanmak, kullanıcıların kimlik bilgilerini girmelerine gerek kalmaksızın Managed Browser’ın Azure AD ile korunan sitelere erişmesine olanak tanır. Bu özellik, Outlook Web Access (OWA) ve SharePoint Online’ın yanı sıra Azure Uygulama Proxy’si yoluyla erişilen intranet kaynakları gibi diğer kurumsal sitelerde de geçerlidir.




## <a name="notices"></a>Bildirimler

Şu anda etkin bildirim yok.


### <a name="see-also"></a>Ayrıca bkz:
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).


