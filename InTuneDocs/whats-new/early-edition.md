---
title: "Erken sürüm | Microsoft Docs"
description: 
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 04/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 31f984fabd2373d242e5e3399bd0c82fbaf53070
ms.lasthandoff: 04/19/2017


---


# <a name="the-early-edition-for-microsoft-intune---april-2017"></a>Microsoft Intune için erken sürüm - Nisan 2017

**Erken Sürüm** Microsoft Intune'un gelecek sürümlerinde kullanıma sunulacak yeni özelliklerin bir listesini sağlar. Bu bilgiler NDA kapsamında çok sınırlı bir temelde sağlanır ve değiştirilebilir. Burada listelenen özelliklerden bazılarının son tarihe yetişememe riski vardır ve gelecek sürüme ertelenebilir. Diğer özellikler, müşterinin kullanımına hazır olduğundan emin olmak için pilot (sürüyor) aşamasında test edilmektedir. Sorularınız veya kaygılarınız varsa lütfen Intune/PM arkadaşınıza ulaşın.

Bu sayfa düzenli aralıklarla güncelleştirilir. Ek güncelleştirmeleri daha sonra denetleyin.

> [!Note]
> Intune için aşağıdaki değişiklikler geliştirilme aşamasındadır. Bu özelliklerin tümü, sonunda karma müşteri dağıtımlarında (Intune ile Configuration Manager) desteklenecektir. Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler sayfamızı](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) gözden geçirin.

## <a name="new-capabilities"></a>Yeni özellikler

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Geliştirilmiş Windows 10 Şirket Portalı uygulaması yükleme durumu <!--676495-->

Windows 10 Şirket Portalı uygulamasında artık Şirket Portalı uygulamasından başlatılan tüm modern uygulama yüklemelerinin ilerleme durumu gösterilecek.

### <a name="improved-status-messaging-in-the-company-portal-app-for-ios---744866--"></a>iOS için Şirket Portalı uygulamasında geliştirilmiş durum iletileri <!--744866-->

iOS için Şirket Portalı uygulamasında artık daha açıklayıcı hata iletileri görüntülenecek ve cihazlardaki gelişmeler hakkında daha açıklayıcı bilgiler verilecek. Bu hata durumları önceden "Şirket Portalı Geçici Olarak Devre Dışı" konulu genel bir hata iletisi içinde listeleniyordu. Ayrıca İnternet bağlantısı olmayan bir kullanıcı iOS üzerinde Şirket Portalı uygulamasını başlattığında ana sayfada "İnternet Bağlantısı Yok" yazan kalıcı bir durum çubuğu görecek.

### <a name="myapps-available-for-managed-browser---822308-822303--"></a>MyApps, Managed Browser ile kullanılabilir <!--822308, 822303-->

Managed Browser için Microsoft MyApps desteği geliştirildi. Yönetim hedefinde yer almayan Managed Browser kullanıcıları doğrudan MyApps hizmetine alınarak yöneticileri tarafından sağlanan SaaS uygulamalarına erişebilecekler. Intune yönetimi hedefinde yer alan kullanıcılar ise MyApps içeriğine yerleşik Managed Browser yer işaretinden erişim sağlayabilecekler.

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Managed Browser ve Şirket Portalı için yeni simgeler <!--918433, 918431-->

Managed Browser uygulamasının hem Android hem de iOS sürümlerinin simgesi güncelleştiriliyor. Yeni simgede Enterprise Mobility + Security (EM+S) paketindeki diğer uygulamalarla tutarlı hale getirmek için güncelleştirilmiş Intune rozeti bulunacak. Managed Browser'ın yeni simgesini [Intune uygulama arabirimindeki yenilikler sayfasında](whats-new-in-intune-app-ui.md) görebilirsiniz.

Şirket Portalı uygulamasının da Android, iOS ve Windows sürümlerinin simgeleri EM+S paketindeki diğer uygulamalarla daha tutarlı hale getirilmek üzere güncelleştiriliyor. Bu simgeler nisan ayından başlayarak mayıs ayının sonuna kadar kademeli olarak kullanıma sunulacak.

### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>iOS Şirket Portalından iOS için Outlook uygulamasına çoklu oturum açma desteği <!--834012-->

Aynı cihazda aynı hesapla iOS için Şirket Portalı uygulamasında oturum açmış kullanıcıların artık Outlook uygulamasında oturum açmasına gerek yok. Kullanıcılar Outlook uygulamasını başlattıktan sonra hesaplarını seçip otomatik olarak oturum açabilecekler. Bu işlevi diğer Microsoft uygulamalarına da eklemek için çalışıyoruz.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Android Şirket Portalı uygulamasında oturum açma ilerleme göstergesi <!--953374-->

Android Şirket Portalı uygulamasında yapılan güncelleştirme ile kullanıcı uygulamayı başlattığında veya sürdürdüğünde oturum açma ilerleme göstergesi görüntüleniyor. Kullanıcının uygulamaya erişmesine izin verilmeden önce göstergede "Bağlanıyor..." ile başlayıp sırasıyla "Oturum açılıyor..." ve "Güvenlik gereksinimleri denetleniyor..."durumları gösteriliyor. Android için Şirket Portalı uygulamasının yeni ekran görüntülerini [Intune uygulama arabirimindeki yenilikler sayfasında](whats-new-in-intune-app-ui.md) görebilirsiniz.


## <a name="notices"></a>Bildirimler

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple, Uygulama Taşıma Güvenliği için güncelleştirmeler gerektirecek <!--748318-->

Apple, 2017 baharından itibaren, Uygulama Taşıma Güvenliği (ATS) için belirli gereksinimler uygulayacağını açıkladı. ATS, HTTPS üzerinden yapılan tüm uygulama iletişimlerinde daha sıkı güvenlik uygulamak için kullanılır. Bu değişiklik, iOS Şirket Portalı uygulamaları kullanan Intune müşterilerini etkiler. Daha fazla ayrıntı için bkz. [Intune destek blogu](https://aka.ms/compportalats).

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Apple kayıt senaryolarına doğrudan erişim <!--951869-->

Intune, Azure Önizleme Portalı'ndaki Cihaz Kaydetme iş yükünü kullanarak Apple kayıt senaryolarına doğrudan erişimi Ocak 2017 sonrasında oluşturulan Intune hesapları için etkinleştirdi. Daha önce, Apple kayıt önizleme sürümüne yalnızca klasik Intune portalı bağlantıları ile erişilebiliyordu. Bu özelliklerin Azure’da kullanılabilmesi için, Ocak 2017 öncesi oluşturulan Intune hesaplarında tek seferlik bir geçiş yapılması gerekir. Geçiş için zaman çizelgesi henüz açıklanmamıştır, ancak konuya ilişkin ayrıntılar olabildiğince çabuk duyurulacaktır. Mevcut hesabınız önizleme sürümüne erişemiyorsa, yeni deneyimi test etmek için bir deneme hesabı oluşturmanızı kesinlikle öneririz.

### <a name="whats-coming-for-appx-in-intune-on-azure----1000270---"></a>Azure'da Intune Appx'leri için yenilikler <!-- 1000270 -->

Azure'da Intune'a geçişin bir parçası olarak üç appx değişikliği yapıyoruz:

1. Klasik Intune konsoluna yalnızca MDM kayıtlı cihazlara dağıtılabilen yeni bir appx uygulama türü ekliyoruz.
2. Var olan appx uygulama türünü yalnızca Intune PC aracısı ile yönetilen PC'lerin hedefleneceği şekilde değiştiriyoruz.
3. Var olan tüm appx'leri geçiş ile MDM appx'leri haline getiriyoruz.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?

Bu durum Intune PC aracısı üzerinden yönetilen mevcut cihazlarınızı etkilemeyecek. Ancak geçiş yapıldıktan sonra geçişi yapılan bu appx'leri Intune PC aracısı ile yönetilen ve daha önceden hedef alınmayan yeni cihazlara dağıtamayacaksınız.

#### <a name="what-action-do-i-need-to-take"></a>Ne yapmam gerekiyor?

Yeni PC dağıtımları gerçekleştirmek istiyorsanız geçiş işleminden sonra appx'i PC appx'i olarak yeniden yüklemeniz gerekecek. Daha fazla bilgi için Intune Destek ekibi blog sayfasındaki [Azure'da Intune Appx'lerinde yapılan değişiklikler](https://aka.ms/appxchange) konusuna bakın.  


## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Azure’daki yeni Intune yönetici deneyiminin genel önizlemesi <!--736542-->

2017 takvim yılının başlarında tam yönetici deneyimimizi Azure’a geçireceğiz. Bu sayede Grafik API’leri kullanılarak genişletilebilen modern bir hizmet platformunda çekirdek EMS iş akışlarının güçlü ve tümleşik yönetimi mümkün olacaktır.

Yeni deneme kiracıları, yeni yönetici deneyiminin genel önizlemesini bu ay Azure portalında görmeye başlayacaklar. Önizleme durumundayken, mevcut Intune konsolu ile gelen yetenekler ve eşlik, yinelemeli olarak sağlanır.

Azure portalındaki yönetici deneyimi, duyurulan yeni gruplandırma ve hedefleme işlevselliğini kullanır; mevcut kiracınız yeni gruplandırma deneyimine geçirildiğinde, siz de kiracınıza yönelik yeni yönetici deneyimini önizlemek üzere geçirilirsiniz. Bu sırada, kiracınız geçirilene kadar yeni işlevleri sınamak veya bunlara göz atmak isterseniz yeni bir Intune deneme hesabına kaydolun veya [yeni belgelere](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune) bakın.

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Android uygulamaları için yönetilen yapılandırma seçenekleri desteği <!-- 621621 -->

Playstore'da yer alan ve yönetilen yapılandırma seçeneklerini destekleyen Android uygulamaları, Intune tarafından yapılandırılabilir.  Bu özellik, BT ekibinin bir uygulama tarafından desteklenen yapılandırma değerlerinin listesini görüntülemesini sağlar ve bu değerlerin yapılandırılması için kılavuzlu bir birinci sınıf kullanıcı arabirimi sunar.

### <a name="remote-assistance-for-android-devices----675418---"></a>Android cihazlar için uzaktan yardım <!-- 675418 -->

Intune, Android cihazlarını çalıştıran kullanıcılarınıza uzaktan yardım etmenizi sağlamak için ayrıca satın alınan [TeamViewer](https://www.teamviewer.com) yazılımını kullanır.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Karmaşık PIN'ler için yeni Android ilkesi <!-- 722069 -->

Android 5.0 ve üzeri çalıştıran cihazların Android cihaz profilinde Sayısal karmaşık türünde parola gereksinimi belirleyebilirsiniz.  Bu ayarı kullanarak cihaz kullanıcılarının 1111 veya 1234 gibi tekrar eden ya da ardışık rakamlardan oluşan PIN'ler oluşturmasını engelleyebilirsiniz.

### <a name="additional-support-for-android-for-work-devices"></a>Android for Work cihazları için ek destek

- **Parola ve iş profili ayarlarını yönetin** <!-- 612808 -->

  Yönettiğiniz Android for Work cihazlarında parola ve iş profili ayarlarını yönetmenizi sağlayan yeni bir Android for Work cihaz kısıtlama ilkesi ekledik.

- **İş ve kişisel profiller arasında veri paylaşımına izin verin** <!-- 1045102 -->

  İş ve kişisel profiller arasında veri paylaşımını yapılandırmanıza yardımcı olmak için bir Android for Work cihaz kısıtlama profilindeki **İş ve kişisel profiller arasında veri paylaşımı** ayarını yeni seçenekler ekleyerek güncelleştirdik.

- **İş ve kişisel profiller arasında kopyalama ve yapıştırma işlemlerini kısıtlama** <!-- 1046094 -->

  Intune ile Android for Work cihazlarını yönettiğinizde iş ve kişisel uygulamalar arasında kopyalama ve yapıştırma eylemlerine izin verilir. Şimdi Android for Work cihazları için yeni bir özel cihaz profili ekleyerek iş ve kişisel uygulamalar arasında kopyala ve yapıştır eylemlerini kısıtlayabilmenizi sağladık.

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>iOS ve Android cihazlara LOB uygulamaları atama <!-- 1057568 -->

iOS (.ipa dosyaları) ve Android (.apk dosyaları) için iş kolu uygulamalarını kullanıcılara veya cihazlara atayabilirsiniz.

###  <a name="new-policies-for-ios-devices----723774-723815-723826-723830-723832---"></a>iOS cihazları için yeni ilkeler <!-- 723774, 723815, 723826, 723830, 723832 -->

- **Ana ekrandaki uygulamalar** - Bir cihaz ilkesi kullanarak kullanıcıların iOS cihazlarının Ana ekranında göreceği uygulamaları denetleyebilirsiniz. Bu ilke Ana ekran yerleşimini değiştirir ancak yüklü olmayan uygulamaları dağıtmaz.

- **AirPrint cihazlarıyla bağlantı** - Bir Intune cihaz ilkesi kullanarak bir iOS cihazının son kullanıcılarının bağlanabileceği AirPrint cihazlarını (ağ yazıcılarını) denetleyebilirsiniz.

- **AirPlay cihazlarıyla bağlantı** - Bir Intune cihaz ilkesi kullanarak bir iOS cihazının son kullanıcılarının bağlanabileceği AirPlay cihazlarını (Apple TV gibi) denetleyebilirsiniz.

- **Özel kilit ekranı iletisi** - Kullanıcıların iOS cihazlarının kilit ekranında varsayılan kilit ekranı mesajı yerine göreceği özel bir ileti yapılandırabilirsiniz.

- **Web içeriği filtresi** - iOS cihazlarının ziyaret edebileceği web sitelerini aşağıdaki iki yöntemden birini kullanarak denetleyebilirsiniz:

  - Apple'ın yerleşik web içeriği filtresini kullanarak izin verilen ve engellenen URL'leri ekleyin.
  - Safari tarayıcısı tarafından yalnızca belirli web sitelerine erişilmesine izin verin. Belirttiğiniz siteler için Safari'de yer işaretleri oluşturulur.


### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>iOS uygulamaları için anında iletme bildirimlerini kısıtlama <!-- 723767 -->

Bir Intune cihaz kısıtlama profilinde iOS cihazlar için aşağıdaki bildirim ayarlarını yapılandırabilirsiniz:

- Belirli bir uygulama için bildirimleri tamamen açma veya kapatma.
- Belirli bir uygulama için bildirim merkezindeki bildirimleri açma veya kapatma.
- Uyarı için **Yok**, **Başlık** veya **Uyarı** türünü belirleme.
- Bu uygulama için rozetlere izin verilip verilmeyeceğini belirleme.
- Bildirim seslerine izin verilip verilmeyeceğini belirleme.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>iOS uygulamalarını otonom tek uygulama modunda çalışacak şekilde yapılandırma <!-- 737837 -->

Bir Intune cihaz profili kullanarak iOS cihazlarını belirtilen uygulamaları otonom tek uygulama modunda çalışacak şekilde yapılandırabilirsiniz. Bu mod yapılandırılıp uygulama çalıştırıldığında cihaz yalnızca belirtilen uygulamayı çalıştıracak şekilde kilitlenir. Buna örnek olarak kullanıcıların cihazda test çözmesini sağlayan bir uygulama verilebilir. Uygulamanın eylemleri tamamlandığında veya bu ilkeyi kaldırdığınızda cihaz normal durumuna geri döner.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>iOS cihazlarda e-posta ve web üzerinde gezinme için güvenilen etki alanlarını yapılandırma <!-- 723765 -->

Bir iOS cihaz kısıtlama profilinden aşağıdaki etki alanı ayarlarını yapılandırabilirsiniz:

- **İşaretlenmemiş e-posta etki alanları** - Son kullanıcı tarafından gönderilen veya alınan ve burada belirttiğiniz etki alanlarıyla eşleşmeyen e-postalar, güvenilmeyen olarak işaretlenir.

- **Yönetilen web etki alanları** - Burada belirttiğiniz URL'lerden indirilen belgeler, yönetilen belgeler olarak değerlendirilir (yalnızca Safari).  

- **Safari otomatik parola doldurma etki alanları (yalnızca denetimli)** - Kullanıcılar yalnızca burada belirttiğiniz desenlerle eşleşen URL'lerdeki parolaları Safari'ye kaydedebilir. Bu ayarı kullanabilmeniz için cihazın denetimli modda olması ve birden fazla kullanıcı için yapılandırılmış olmaması gerekir. (iOS 9.3 ve üzeri)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>iOS Şirket Portalında VPP uygulamaları kullanılabilir <!-- 748782 -->

Toplu satın alınan (VPP) iOS uygulamalarını son kullanıcılara **Kullanılabilir** yüklemeler olarak atayabilirsiniz. Son kullanıcıların uygulamayı yükleyebilmek için bir Apple Store hesabına sahip olmaları gerekir.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>Apple VPP Store'dan alınan eKitapları eşitleme <!-- 800878 -->

Apple toplu satın alma programı mağazasından satın aldığınız kitapları Intune ile eşitleyebilir ve kullanıcılara atayabilirsiniz.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Samsung KNOX Standard cihazları için birden çok kullanıcı yönetimi <!-- 971988 -->

Samsung KNOX Standard çalıştıran cihazlarda artık Intune ile birden çok kullanıcı yönetimi gerçekleştirilebilir. Başka bir deyişle kullanıcılar Azure Active Directory kimlik bilgilerini kullanarak cihazda oturum açıp kapatabilir ve cihaz kullanım durumundan bağımsız olarak merkezden yönetilir.  Oturum açan kullanıcılar kendilerine atanan uygulamalara ilkelere otomatik olarak erişir. Kullanıcılar oturumu kapattığında tüm veriler silinir.

### <a name="additional-windows-device-restriction-settings----818566---"></a>Ek Windows cihaz kısıtlama ayarları <!-- 818566 -->

Ek Edge tarayıcısı desteği, kilit ekranı özelleştirmesi, başlat menüsü özelleştirmeleri, Windows Spot araması duvar kağıdı ve proxy ayarı gibi ek Windows cihaz kısıtlama ayarları için destek ekledik.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Windows 10 Creators Update için birden çok kullanıcı desteği <!-- 822547 -->

Windows 10 Creators Update çalıştıran ve Azure Active Directory etki alanına katılmış olan cihazlar için birden çok kullanıcı yönetimi desteği ekledik. Bu destek sayesinde farklı standart kullanıcılar, Azure AD kimlik bilgilerini kullanarak cihazda oturum açtığında kullanıcı adlarına atanmış olan uygulamalara ve ilkelere erişecek. Kullanıcılar, uygulama yükleme gibi self servis senaryoları için Şirket Portalını şu anda kullanamaz.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Windows 10 PC'ler Fresh Start<!-- 1004830 -->

Bu sürümde, Windows 10 PC'ler için yeni bir Fresh Start cihaz eylemi ekledik.  Bu eylemi düzenlediğinizde PC'ye önceden yüklenmiş olan uygulamalar kaldırılır ve PC otomatik olarak en son Windows sürümüne güncelleştirilir. Bu eylem genellikle yeni bir PC ile gelen önceden yüklü OEM uygulamalarının kaldırılmasına yardımcı olması için kullanılabilir. Bu cihaz eylemi düzenlendiğinde kullanıcı verilerinin tutulup tutulmayacağını yapılandırabilirsiniz.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>Ek Windows 10 yükseltme yolları <!-- 903672 -->

Artık, cihazları aşağıdaki ek Windows 10 sürümlerine yükseltmek için bir sürüm yükseltme ilkesi oluşturabilirsiniz:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Windows 10 cihazlarını toplu kaydetme <!-- 747607 -->

Windows Yapılandırma Tasarımcısı (WCD) kullanarak Windows 10 Creators Update çalıştıran çok sayıda cihazın Azure Active Directory ve Intune’a katılmasını sağlayabilirsiniz. Azure AD kiracınızda otomatik MDM kaydını etkinleştirmek için Windows Yapılandırma Tasarımcısı kullanarak cihazların Azure AD kiracınıza katılmasını sağlayan bir sağlama paketi oluşturun ve paketi toplu kaydetmek ve yönetmek istediğiniz şirkete ait cihazlara uygulayın. Paket cihazlarınıza uygulandıktan sonra cihazlar Azure AD'ye katılır, Intune'a kaydolur ve Azure AD kullanıcılarınızın oturum açmasına hazır hale gelir.  Azure AD kullanıcıları, bu cihazlarda standart kullanıcılardır ve atanan ilkeleri ve gerekli uygulamaları alırlar. Self Servis ve Şirket Portalı senaryoları şu anda desteklenmiyor.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----58112-736644---"></a>PIN ve yönetilen depolama konumları için yeni MAM ayarları <!-- 58112, 736644 -->

Mobil uygulama yönetimi (MAM) senaryolarında size yardımcı olacak iki yeni uygulama ayarı mevcut:

- **Cihaz PIN'i yönetildiğinde uygulama PIN'ini devre dışı bırak** - Kaydedilen cihazda bir cihaz PIN'i olup olmadığını algılar ve varsa uygulama koruma ilkeleri tarafından tetiklenen uygulama PIN'ini atlar. Bu ayar, kayıtlı cihazda MAM özellikli bir uygulamayı açan kullanıcılara gösterilen PIN istemi sayısının azaltılmasını sağlar. Bu özellik hem Android hem de iOS için kullanılabilir.

- **Şirket verilerinin kaydedilebileceği depolama hizmetlerini seçin** - Şirket verilerinin kaydedileceği depolama konumlarını belirtmenizi sağlar. Kullanıcılar seçilen depolama konumu hizmetlerine veri kaydedebilir ve listede olmayan diğer tüm depolama konumu hizmetleri engellenir.

  Desteklenen depolama konumu hizmetlerin listesi:

  - OneDrive
  - İş SharePoint Online
  - Yerel depolama


### <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new-in-microsoft-intune.md).

