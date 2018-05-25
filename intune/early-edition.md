---
title: Erken sürüm
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 62028232e4d6c9ab20a05480811978234ed0a3c1
ms.sourcegitcommit: 91802e78cd5014d20a828ca25a54a381d452f0f8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/16/2018
---
# <a name="the-early-edition-for-microsoft-intune---may-2018"></a>Microsoft Intune için erken sürüm - Mayıs 2018

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

<!-- 1805 start -->

### <a name="support-for-palo-alto-networks-globalprotect-vpn-profiles----1333680-eeready----"></a>Palo Alto Networks GlobalProtect VPN profilleri için destek <!-- 1333680 eeready ! -->

Bu güncelleştirme ile Intune’da VPN profilleri için VPN bağlantısı olarak Palo Alto Networks GlobalProtect’i seçebilirsiniz (**Cihaz yapılandırması** > **Profiller** > **Profil oluştur** > **Profil türü** > **VPN**). Bu sürümde aşağıdaki platformlar desteklenir: 

- iOS
- Windows 10

### <a name="set-compliance-by-device-location----851881----"></a>Cihaz konumuna göre uyumluluk ayarlama <!-- 851881 ! -->
Bazı durumlarda, ağ bağlantısı tarafından belirlenen bir konumdan şirket kaynaklarına erişimi kısıtlamak isteyebilirsiniz. Cihazın IP adresine bağlı olarak bir uyumluluk ilkesi (**Cihaz uyumluluğu** > **Konumlar**) oluşturabileceksiniz. Cihaz, IP aralığı dışına çıktığında şirket kaynaklarına erişemez.

Uygulandığı öğe: Android cihazlar 6.0 ve üzeri, güncelleştirilmiş Şirket Portalı uygulaması ile

### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Uygulama yüklemesi için geliştirilmiş sorun giderme <!-- 928990 -->
Microsoft Intune MDM ile yönetilen cihazlarda bazen uygulama yüklemeleri başarısız olabilir. Bu uygulamaların yüklemesi başarısız olduğunda, başarısızlık sebebini anlamak ve sorunu gidermek zor olabilir. Uygulama Sorun Giderme özelliklerimizin bir Genel Önizlemesini yayınlıyoruz. Tüm cihazlarda **Yönetilen Uygulamalar** adlı yeni bir düğüm göreceksiniz. Bu düğümde Intune MDM yoluyla teslim edilen uygulamalar listelenir. Burada uygulama yükleme durumlarının bir listesini bulacaksınız. Bir uygulamayı seçtiğinizde, o uygulamaya özel sorun giderme görünümünü açmış olacaksınız. Sorun giderme görünümünde uygulamanın oluşturulma, değiştirilme, hedeflenme ve cihaza teslim edilme tarihleri gibi uçtan uca yaşam döngüsünü bulabileceksiniz. Buna ek olarak, uygulama yüklemesinin başarısız olması durumunda size bir hata kodu ve hatanın sebebiyle ilgili yardım olacak bir ileti sunulacak. 

### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>Onaylanmamış cihaz satıcıları ve modellerine göre uygulama erişimini engelleme <!-- 1425689 ! -->
Intune BT yöneticisi, belirlenen Android üreticileri ve/veya iOS modelleri listesini Intune Uygulama Koruması İlkeleri yoluyla zorlayabilecek. BT yöneticisi, Android ilkeleri için noktalı virgülle ayrılmış bir üretici listesi ve aynı şekilde iOS ilkeleri için bir cihaz modelleri listesi sağlayabilecek. Intune Uygulama Koruması İlkeleri, yalnızca Android ve iOS için geçerlidir. Bu belirtilen listede gerçekleştirilebilecek iki ayrı eylem vardır:
- Belirtilmemiş cihazlarda uygulama erişimini engelleme.
- Veya belirtilmemiş cihazlarda şirket verilerini seçmeli olarak silme. 

İlke gereksinimleri karşılanmazsa kullanıcı, hedeflenen uygulamaya erişemeyecek. Ayarlara bağlı olarak kullanıcı engellenebilir veya uygulama dahilinde kullanıcının şirket verileri seçmeli olarak silinir. iOS cihazlarda bu özellik, en düşük sürüm ayarlarının hedeflenen uygulamalarda zorlanabilmesi için uygulamaların katılımının (WXP, Outlook, Managed Browser, Yammer) Intune APP SDK’sıyla tümleştirilmesini gerektirir. Bu tümleştirme, sıralı bir şekilde gerçekleşir ve belirli uygulama ekiplerine bağımlıdır. Android’de bu özellik, Şirket Portalı’nın en son sürümünü gerektirir.

Son kullanıcı cihazlarında Intune istemcisi, Intune’un Uygulama Koruma İlkeleri dikey penceresinde belirtilen dizelerin basit eşleştirmesine dayalı olarak eylem gerçekleştirir. Bu, tamamen cihazın rapor ettiği değere bağlıdır. Bu nedenle BT yöneticisinin amaçlanan davranışın doğru olduğundan emin olması önerilir. Bu ayar, küçük bir kullanıcı grubuna hedeflenen çeşitli cihaz üreticileri ve modellerinde sınanarak doğruluğundan emin olunabilir. Microsoft Intune’da uygulama koruma ilkelerini görüntülemek ve ilke eklemek için **Mobil uygulamalar** > **Uygulama koruma ilkeleri**’ni seçin. Uygulama koruma ilkeleri hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkeleri nelerdir](app-protection-policy.md).

### <a name="enable-kiosk-mode-on-windows-10-devices----1560072----"></a>Windows 10 cihazlarda bilgi noktası modunu etkinleştirme <!-- 1560072 ! -->
Windows 10 cihazlarda bir yapılandırma profili oluşturabilir ve bilgi noktası modunu etkinleştirebilirsiniz (**Cihaz Yapılandırması** > **Profiller** > **Profil oluştur** > **Windows 10** > **Cihaz Kısıtlamaları** > **Bilgi noktası**). Bu güncelleştirmede **Bilgi noktası (önizleme)** ayarı, **Bilgi noktası (kullanılmayan)** olarak yeniden adlandırıldı. **Bilgi noktası (kullanılmayan)**, artık kullanım için önerilmese de Temmuz güncelleştirmesine kadar işlevselliğini koruyacaktır. **Bilgi noktası (kullanılmayan)**, yeni **Bilgi noktası** türü (**Profil oluştur** > **Windows 10** > **Bilgi noktası (önizleme)**) ile değiştirilmiştir. Bu yeni tür, Windows 10 RS4 ve üzeri sürümlerde Bilgi Noktalarını yapılandırmak üzere ayarlar içerecektir.

Windows 10 ve üzeri için geçerlidir.

### <a name="retrieve-the-associated-app-user-model-id-aumid-for-microsoft-store-for-business-apps-in-kiosk-mode----1560077----"></a>İş İçin Microsoft Store uygulamaları için bilgi noktası modunda ilişkili uygulama kullanıcı model kimliğini (AUMID) alma <!-- 1560077 ! -->
Intune, bilgi noktası profilinde daha iyi bir yapılandırma sağlamak amacıyla İş İçin Microsoft Store (WSfB) uygulamaları için uygulama kullanıcı model kimliğini (AUMID) alabilecek.

İş İçin Microsoft Store uygulamaları hakkında daha fazla bilgi için bkz. [İş İçin Microsoft Store’dan uygulamaları yönetme](windows-store-for-business.md).

### <a name="access-actions-for-app-protection-policies----1483510-eeready---"></a>Uygulama koruma ilkeleri için eylemlere erişme <!-- 1483510 EEready -->
Yakında uyumsuz cihazları açık olarak silmek, engellemek veya uyarmak üzere uygulama koruma ilkeleri yapılandırabileceksiniz. En yeni *silme* eylemi, bir cihazdan şirketinizin verilerini kaldırır. Bir silme işlemi gerçekleştirildiğinde, kullanıcıya silme sebebi ve düzeltme adımları bildirilir. En düşük işletim sistemi sürümü gibi bazı ayarlarda, engelleme ve silme gibi birden fazla eylem gerçekleştirebileceksiniz.

### <a name="new-inventory-information-for-windows-devices----1333569-eeready---"></a>Windows cihazlar için yeni envanter bilgileri <!-- 1333569 eeready -->

Windows cihazlarda, **Donanım** sekmesinde (**Gruplar** > **Tüm mobil cihazlar** > **Cihazlar** > kullanıcıya ait cihazı seçin > **Özellikleri Görüntüle** > **Donanım**) her bir cihaz için şu envanter bilgileri kullanılabilir olacak:
- TPM
- Virüsten Koruma
- Casus Yazılımdan Koruma
- Güvenlik Duvarı
- UAC
- Pil
- Etki alanı adı

Bu verilerin CSP tarafından nasıl alındığı hakkında daha fazla bilgi için [DeviceStatus CSP’si](https://docs.microsoft.com/en-us/windows/client-management/mdm/devicestatus-csp) makalesindeki DeviceGuard girdilerine bakın.

### <a name="intune-and-the-microsoft-edge-browser----1818969---"></a>Intune ve Microsoft Edge tarayıcı <!-- 1818969 -->
Mobil cihazlar (iOS ve Android) için Microsoft Edge tarayıcısı, artık Intune uygulama koruma ilkelerini destekliyor. Şirket Azure AD hesaplarıyla Edge tarayıcı uygulamasında oturum açan kullanıcılar, Intune tarafından korunacak. 

### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot----1821766---"></a>Autopilot için OOBE yapılandırırken yeni dil / bölge ayarı <!-- 1821766 -->
Autopilot profilleri için İlk Çalıştırma Deneyimi sırasında dili ve bölgeyi ayarlamak için yeni bir yapılandırma ayarı kullanılabilir olacak.

### <a name="new-setting-for-configuring-device-keyboard----1821768---"></a>Cihaz klavyesini yapılandırmak için yeni ayar <!-- 1821768 -->
Autopilot profilleri için İlk Çalıştırma Deneyimi sırasında klavyeyi yapılandırmak için yeni bir ayar kullanılabilir olacak.

### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices----1985547---"></a>iOS ve MacOS cihazlarda ekran paylaşımı için TeamViewer kullanma <!-- 1985547 -->
Şu anda [Intune ile yönetilen Android ve Windows cihazları](device-profile-android-teamviewer.md) uzaktan yönetmek için TeamViewer’ı kullanabiliyorsunuz.

Artık yöneticiler, TeamViewer’a bağlanıp iOS ve macOS cihazlarla bir ekran paylaşma oturumu başlatabilecek. iPhone, iPad ve macOS kullanıcıları, diğer herhangi bir masaüstü veya mobil cihazla ekranlarını canlı olarak paylaşabilecek. 

### <a name="device-profile-graphical-user-chart-is-back----2160133---"></a>Cihaz profili kullanıcı grafiği geri geldi <!-- 2160133 -->
Cihaz profili grafiğinde (**Cihaz yapılandırması** > **Profiller** > mevcut bir profil seçin > **Genel bakış**) gösterilen sayısal değerleri geliştirirken, kullanıcı grafiği geçici olarak kaldırılmıştı.

Bu güncelleştirmeyle birlikte kullanıcı grafiği geri geldi ve Azure portalında gösteriliyor.

### <a name="assign-all-users-and-all-devices-as-scope-groups----2196803---"></a>Tüm kullanıcıları ve tüm cihazları kapsam grupları olarak atama <!-- 2196803 -->
Tüm kullanıcıları, tüm cihazları ve tüm kullanıcılar ile tüm cihazları kapsam gruplarına atayabileceksiniz.

### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Autopilot profilleri grup hedeflemeye taşınıyor <!-- 1877935 -->
AutoPilot dağıtım profilleri şu anda seçili cihazlara atanabiliyor. Bu özellik yayımlandıktan sonra bu profilleri atamak için yapmanız gerekenler şunlardır:
- AutoPilot cihazları barındıran Azure AD grupları oluşturun
- İstenen profilleri bir Azure AD profiline atayın. AutoPilot profili artık bu gruptaki AutoPilot cihazlara atanmış olacak.

### <a name="management-name-field-will-be-editable----1875989---"></a>Yönetim adı alanı düzenlenebilir olacak <!-- 1875989 -->
Bir cihazın **Özellikler** dikey penceresindeki yönetim adı alanını düzenleyebileceksiniz. Bu alanı düzenlemek için **Cihazlar** > **Tüm cihazlar** > cihazı seçin > **Özellikler** seçeneğini belirleyin. Bir cihazı benzersiz olarak tanımlamak için yönetim adı alanını kullanabilirsiniz.

<!-- 1804 start -->


### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Yerel Cihaz Güvenliği Seçenekleri ayarlarına ekler <!-- 1403702 -->
Windows 10 cihazlar için ek Yerel Cihaz Güvenliği Seçenekleri ayarları yapılandırabileceksiniz. Ek ayarlar; Microsoft Ağ İstemcisi, Microsoft Ağ Sunucusu, Ağ erişimi ve güvenlik ve Etkileşimli oturum açma bölümlerinde kullanılabilir olacak. Bu ayarları, bir Windows 10 cihaz yapılandırma ilkesi oluşturduğunuzda Endpoint Protection kategorisinde bulabilirsiniz.

### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>İlkelerin, uygulamaların, sertifika ve ağ profillerinin yüklenmesini gerektirme <!-- 1553555 -->
Intune, AutoPilot cihazlar hazırlanırken ilkeleri, uygulamaları ve sertifika ve ağ profillerini yükleyene kadar yöneticiler; son kullanıcıların Windows 10 RS4 masaüstüne erişimini engelleyebilecek.

### <a name="rules-for-removing-devices----1609459---"></a>Cihaz kaldırma kuralları <!-- 1609459 -->
Ayarladığınız süre boyunca (gün) iade edilmeyen cihazları otomatik olarak kaldırmanıza imkan veren yeni kurallar kullanılabilir olacak. Yeni kuralı görmek için **Intune** bölmesine gidin, **Cihazlar**’ı ve **Cihaz kaldırma kuralları**’nı seçin.

### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Windows 10 Enterprise RS4 Autopilot cihazlarda tüketici uygulamaları ve deneyimlerini engelleme<!-- 1621980 -->
Windows 10 Enterprise RS4 AutoPilot cihazlarınızda tüketici uygulama ve deneyimlerinin yüklenmesini önleyebileceksiniz. Bu özelliği görmek için **Intune** > **Cihaz kaydı** > **Windows kaydı** > **Windows AutoPilot profilleri** > **Yeni Oluştur** > **Kayıt ayarları**’na gidin. 

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

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Uygulama koruma ilkeleri  <!-- 679615 -->
Intune Uygulama Koruma İlkeleri, tüm kiracıdaki tüm kullanıcılar için hızlı bir şekilde koruma sağlamaya yönelik genel ve varsayılan ilkeler oluşturma olanağı sunar.

<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Bildirimler

Şu anda etkin bildirim yok.

### <a name="see-also"></a>Ayrıca bkz:
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).
