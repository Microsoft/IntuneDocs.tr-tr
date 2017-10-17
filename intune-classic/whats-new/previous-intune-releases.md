---
title: "Önceki sürümler"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: NOINDEX,NOFOLLOW
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 592fa765dd56fd645a86be19baef8be87707b398
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/10/2017
---
# <a name="previous-intune-releases"></a>Önceki Intune sürümleri

Bu sayfa, [Microsoft Intune'daki Yenilikler](whats-new-in-microsoft-intune.md) sayfasında yapılan son duyuruların bir listesidir.

[!INCLUDE[wit_nextref](../includes/whats-new-last-six-months.md)]

## <a name="july-2016"></a>Temmuz 2016

### <a name="app-management"></a>Uygulama yönetimi

__Uygulama sağlama profilini güncelleştirme deneyimini geliştirme__ Apple iOS iş kolu mobil uygulamaları, eklenen ve sertifika kullanılarak kodla imzalanan bir sağlama profiliyle oluşturulur. Uygulama iOS cihazında çalıştırıldığında, iOS uygulamanın bütünlüğünü onaylar ve sağlama profiliyle tanımlanan ilkeleri zorunlu tutar.

Uygulamaları imzalamak için kullandığınız kurumsal imzalama sertifikasının süresi normalde 3 yıldır. Öte yandan, 1 yıl sonra sağlama profilinin süresi dolar. Bu güncelleştirmeyle Intune size, sertifikası hala geçerli olduğu halde süresi dolmak üzere olan uygulamaların bulunduğu cihazlara, yeni sağlama profili ilkesini önceden dağıtmak için araçlar getirir. Daha fazla bilgi için bkz. [İş kolu uygulamalarınızın güncel kalmasını sağlamak için iOS mobil sağlama profili ilkelerini kullanma](/intune-classic/deploy-use/ios-mobile-app-provisioning-profiles).
<!--- TFS 1280247--->

__Intune uygulamaları için Xamarin SDK’sı sağlanır__ Intune Uygulaması SDK Xamarin bileşeni, Xamarin ile oluşturulan mobil iOS ve Android uygulamalarınızda Intune mobil uygulama yönetimi özelliklerini etkinleştirmenize olanak tanır. Bileşeni [Xamarin mağazasında](https://components.xamarin.com/view/Microsoft.Intune.MAM) veya [Microsoft Intune Github sayfasında](https://github.com/msintuneappsdk) bulabilirsiniz.
<!--- TFS 1061478 --->

### <a name="device-management"></a>Cihaz yönetimi
__Cihaz kayıt sınırlarında artış__ Intune, yapılandırılabilir cihaz kayıt sayısı üst sınırını kullanıcı başına 5 cihazdan 15 cihaza çıkardı.
<!---TFS 1289896 --->

__Intune istemci yazılımını çalıştıran Windows bilgisayarlar için TeamViewer Tümleştirmesi__
[TeamViewer](/intune-classic/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

### <a name="company-portal-updates"></a>Şirket portalı güncelleştirmeleri

__Şirket Portalı web sitesi__
- **Windows cihazlarını kaydetme işleminde geliştirilmiş son kullanıcı deneyimi**<br/>
Koşullu erişim kullanırken, Şirket Portalı web sitesindeki Windows 8.1, Windows 10 Masaüstü ve Windows 10 Mobile için kayıt adımları netleştirilmiştir. Kullanıcılara artık birbirinden ayrı “Cihaz kaydı” ve “Workplace Join” adımları gösterilir. Böylelikle cihazlarının durumunu daha kolay görebilir ve Workplace Join (WPJ) hatasıyla karşılaşırlarsa işlemi tamamlayabilirler. Ayrı adımların, BT yöneticileri için sorun giderme işlemini de basitleştirmesi beklenmektedir. Daha önce, son kullanıcılar cihazı kaydetmeyi denerken WPJ dışındaki tüm kayıt adımları başarılı olduğunda, kaydedilen cihaz kullanıcıların belirleyebilmesi için cihaz listesinde gösterilmeyebiliyor ve kullanıcılarda kafa karışıklığına neden oluyordu.

__Android__
- **Android Şirket Portalı uygulaması**<br/>
Android son kullanıcıları, cihazlarında gerekli bir sertifikanın eksik olduğunu bildiren bir hata iletisi görürse BT yöneticilerinin sertifika sorununu çözmek için kullanabileceği adımları da içeren [adımları](/intune-classic/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues) almak için “Nasıl çözülür” düğmesine dokunabilir.

- **Dışarıdan uygulama yüklemelerini kayıtlı cihazlarla kısıtlama**<br/>
Android için Intune Şirket Portalı uygulaması kullanılarak Intune’a kaydedilmeyen Android cihazları, artık Şirket Portalı web sitesi üzerinden uygulama yükleyemezler.
<!---TFS 1299082--->

__iOS__
- **iOS Şirket Portalı uygulamasında Cihaz Kayıt Yöneticileri hesaplarında yapılan değişiklikler**<br/>
Performansı ve ölçeği artırmak için, Intune artık iOS Şirket Portalı uygulamasının **Cihazlarım** bölmesinde Cihaz Kayıt Yöneticileri (DEM) cihazlarını görüntülemez. Yalnızca uygulamayı çalıştıran yerel cihaz, yalnızca Şirket Portalı uygulaması aracılığıyla kaydedilmişse görüntülenir.

DEM kullanıcısı, yerel cihazda eylemler gerçekleştirebilir, ancak diğer kaydedilen cihazların uzaktan yönetimi yalnızca Intune yönetici konsolundan gerçekleştirilebilir. Ayrıca Intune, Apple Cihaz Kayıt Programı veya Apple Configurator aracıyla DEM hesaplarını kullanımdan kaldırmaktadır. Her iki kayıt yöntemi, paylaşılan iOS cihazları için kullanıcısız kaydı zaten desteklemektedir.

Yalnızca, paylaşılan cihazlar için kullanıcısız kayıt kullanılamadığında DEM hesapları kullanın. Daha fazla bilgi için bkz. [Şirket ait cihazları Microsoft Intune'da Cihaz Kayıt Yöneticisi ile kaydetme](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### <a name="change-of-names-for-windows-features"></a>Windows özelliklerinde ad değişiklikleri
- [Windows için Microsoft Passport](/intune-classic/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) artık **İş için Windows Hello** olarak adlandırılıyor.
- [Kurumsal veri koruma](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) artık **Windows Bilgi Koruması** olarak adlandırılıyor.


## <a name="june-2016"></a>Haziran 2016
### <a name="intune-service-health"></a>Intune hizmet durumu
Intune’un hizmet durumu bilgileri, diğer Microsoft hizmetleriyle birlikte merkezi bir konuma taşındı. Artık bu bilgileri Office 365 yönetim portalında, Hizmet Durumu’nun altında bulabilirsiniz. Daha fazla bilgi için [bu blog gönderisine](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/) bakın.

### <a name="app-management"></a>Uygulama yönetimi
- **Geliştirilmiş Windows 10 kurumsal veri ilkesi yapılandırma deneyimi.** Windows 10 kurumsal veri koruma ilkesi yapılandırma deneyiminde, uygulama kuralları oluşturma, ağ sınırı tanımını belirtme ve diğer kurumsal veri koruma ayarları ile ilgili geliştirmeler yapıldı. Daha fazla bilgi için bkz: [Microsoft Intune kullanarak kurumsal veri koruma (EDP) ilkesi oluşturma](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune).


### <a name="device-management"></a>Cihaz yönetimi
- **Olası istenmeyen uygulamalara karşı koruma sağlayan Windows Defender ilke ayarı.** Windows 10 Desktop ve Mobile için genel yapılandırma ilkesine **İstenmeyebilecek Uygulama Algılama** adlı yeni bir Windows Defender ayarı eklendi. Bu ayarı kullanarak kayıtlı Windows masaüstü bilgisayarlarını, Windows Defender tarafından istenmeyebilecek yazılım olarak sınıflandırılan yazılımları çalıştırmaya karşı koruyabilirsiniz. Bu uygulamaların çalıştırılmasına karşı koruma sağlayabilir veya istenmeyebilecek bir uygulama yüklendiğinde raporlanması için denetim modunu kullanabilirsiniz. Daha fazla bilgi için, bkz. [Microsoft Intune’da Windows 10 ilke ayarları](/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune).
<!---TFS 1244478--->

### <a name="conditional-access"></a>Koşullu erişim
- **Intune için Cisco ISE ağ erişimi denetim ilkesi.**  Cisco Identity Service Engine (ISE) 2.1 ile birlikte Microsoft Intune’u kullanan müşteriler, ISE’de bir ağ erişimi denetim ilkesi ayarlayabilir.

    Bu ilke kullandığında, ağa WiFi veya VPN ile erişmeye çalışan cihazlara erişim izni verilmesi için cihazların aşağıdaki koşulları karşılaması gerekir:

    * Intune tarafından yönetiliyor olmalıdır
    * Dağıtılmış tüm Intune uyumluluk ilkeleriyle uyumlu olmalıdır

 Uyumsuz cihazları kullanan son kullanıcıların erişim elde etmek için kaydolması ve uyumluluk sorunlarını gidermesi istenir.
- **Tarayıcı için koşullu erişim.** [Exchange Online](/intune-classic/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune) için, yalnızca yönetilen ve uyumlu iOS ile Android cihazlarda desteklenen web tarayıcılarından erişilebilmelerini sağlayacak bir koşullu erişim ilkesi ayarlayabilirsiniz. iOS ve Android cihazlarıyla Outlook Web Access (OWA) ve SharePoint sitelerinde oturum açmayı deneyen son kullanıcılardan, oturum açma işlemini tamamlayabilmek için önce cihazlarını Intune’a kaydetmeleri ve tüm uyumsuzluk sorunlarını çözmeleri istenecektir.
<!---TFS 1175844--->

- **Dynamics CRM Online koşullu erişimi destekler.** [Dynamics CRM Online](/intune-classic/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune) için, yalnızca yönetilen ve uyumlu iOS ile Android cihazları tarafından erişilebilmelerini sağlayacak bir koşullu erişim ilkesi ayarlayabilirsiniz. iOS ve Android’de Dynamics CRM mobil uygulamasında oturum açmaya çalışan son kullanıcılardan, oturum açma işlemini tamamlanabilmek için Intune’a kaydolmaları ve tüm uyumsuzluk sorunlarını çözmeleri istenecektir.
<!---TFS1295358--->

### <a name="intune-company-portal-updates"></a>Intune Şirket Portalı güncelleştirmeleri

__Android Şirket Portalı uygulaması__

- BT yöneticileri yeni "Cihazların bilinmeyen kaynaklardan uygulama yüklemesine izin vermemesini sağla (Android 4.0 +)" ilkesini uyguladığında, Android 4.0 veya üstü cihazlara sahip son kullanıcılar, "Bilinmeyen kaynaklardan yükleme devre dışı bırakılmalıdır" iletisini görür. Kullanıcıların, **Ayarlar** > **Güvenlik** kısmına gitmesi ve **Bilinmeyen kaynaklar**’ı kapatması gerekir. Uyumluluk iletisindeki bir bağlantı, kullanıcıların, ileti hakkında ve ayarı neden kapatmaları gerektiği hakkında aha fazla [bilgi](/intune-user-help/you-are-asked-to-turn-off-unknown-sources-android) almasını sağlar.

- BT yöneticileri yeni "Cihazların, güvenlik tehditleri için uygulamaların taranmasını etkinleştirmiş olmasını gerektir (Android 4.0 +)” ilkesini uyguladığında, Android 4.0 veya üstü cihazlara sahip son kullanıcılar, “Cihazı güvenlik tehditleri için tara” iletisini görür. Kullanıcıların, **Ayarlar** > **Google** > **Güvenlik** kısmına gitmesi ve **Cihazı güvenlik tehditleri için tara**’yı açması gerekir. Uyumluluk iletisindeki bir bağlantı, kullanıcıların, ileti hakkında ve ayarı neden açmaları gerektiği hakkında daha fazla [bilgi](/intune-user-help/you-are-asked-to-turn-on-scan-device-for-security-threats-android) almasını sağlar.

- BT yöneticileri yeni "USB hata ayıklamanın devre dışı olmasını gerektir (Android 4.2 +)" ilkesini uyguladığında, Android 4.2 veya üstü cihazlara sahip son kullanıcılar, "USB hata ayıklama devre dışı bırakılmalıdır" iletisini görür. Kullanıcıların, **Ayarlar** > **Geliştirici seçenekleri** kısmına gitmesi ve “**USB hata ayıklama**”yı kapatması gerekir. Uyumluluk iletisindeki bir bağlantı, kullanıcıların, ileti hakkında ve ayarı neden kapatmaları gerektiği hakkında aha fazla [bilgi](/intune-user-help/you-are-asked-to-turn-off-usb-debugging-android) almasını sağlar.

- BT yöneticileri yeni "Minimum Android güvenlik düzeltme eki düzeyi (Android 6.0 +)" ilkesini uyguladığında, Android 6.0 veya üstü cihazlara sahip son kullanıcılar, "Bu cihaz, en düşük Android güvenlik düzeltme eki düzeyini karşılamıyor" iletisini görür. Kullanıcıların, gerekli güvenlik düzeltme ekini yüklemesi gerekir. Uyumluluk iletisindeki bir bağlantı, kullanıcıların gerekli güvenlik düzeltme ekini nasıl yükleneceği hakkında [bilgi](/intune-user-help/you-are-asked-to-turn-on-scan-device-for-security-threats-android) almasını ve mevcut durumda kendilerinde hangi güvenlik düzeltme ekinin yüklü olduğunu görmesini sağlar.

__iOS Şirket Portalı uygulaması__

- Son kullanıcılar iş kolu uygulamaları yüklediğinde artık iyileştirilmiş bir uygulama yükleme deneyimi görecektir. Uygulama yüklemesi uzun sürüyorsa, kullanıcılar, eşitleme işleminin devam etmesini zorlamak için cihazlarını el ile eşitleyebilir. Son kullanıcı yönergelerini gözden geçirmek için, bkz. [iOS cihazınızı el ile eşitleme](/intune-user-help/sync-your-device-manually-ios).

- iOS için Microsoft Intune Şirket Portalı uygulaması, iOS 8.0 ve sonraki sürümleri desteklemek için güncelleştirildi. Bu güncelleştirme, yalnızca cihaz iOS 8.0 veya sonraki sürümleri çalışıyorsa son kullanıcıların Şirket Portalı uygulamasını yükleyebileceği ve Intune’a yeni cihazları kaydedebileceği anlamına gelir. Desteklenmeyen bir iOS sürümünü çalıştıran, önceden kayıtlı cihazları olan kullanıcılar, cihazlarında Şirket Portalı uygulamasını kullanmaya devam edebilir.

## <a name="may-2016"></a>Mayıs 2016
Bu özelliklerin tümü, karma dağıtımlar için de desteklenmektedir (Intune içeren Yapılandırma Yöneticisi). Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler](https://technet.microsoft.com/library/mt718155.aspx) sayfasını gözden geçirin.

### <a name="documentation"></a>Belgeler
[Docs.microsoft.com](https://docs.microsoft.com/intune)’un önizleme sürümüne hoş geldiniz!
Bu, siz müşterilerimizin Intune’u anlamasını ve kullanmasını kolaylaştırmak için tasarlanmış, tamamen yeni, modern bir içerik platformudur.
Tüm yeni özellikler hakkındaki bilgileri okumak için, bkz. [Docs.microsoft.com ile tanışın](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/)

### <a name="intune-service-health"></a>Intune hizmet durumu
Intune’un hizmet durumu bilgileri, diğer Microsoft hizmetleriyle birlikte merkezi bir konuma taşındı. Artık bu bilgileri [Office 365 yönetim portalında](https://portal.office.com/Admin/Default.aspx), **Hizmet Durumu**’nun altında bulabilirsiniz.
Daha fazla bilgi için [bu blog gönderisine](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/) bakın.

### <a name="app-management"></a>Uygulama yönetimi
- **MAM SDK’sı: PIN uzunluğu yapılandırmasını destekler.** Cihaz PIN’ine benzer şekilde MAM uygulamalarının PIN’i için de uzunluğu belirtebileceksiniz. Bunun için son kullanıcıların sizin ayarladığınız yeni kısıtlamalara uyması gerekecektir. Daha uzun girişi kabul eden biraz değiştirilmiş bir PIN ekranı görecekler. Ayrıntılar için bkz. [Android için MAM ilke ayarları](/intune-classic/deploy-use/ios-mam-policy-settings).

- **iOS ve Android için Skype Kurumsal.** Artık [kayıt ilkeleri olmadan MAM](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) ile Skype Kurumsal’ı hedefleyebilirsiniz. Kullanıcılar oturum açtığında, MAM ilkeleri uygulanır.

- **MAM ilkeleriyle yönetim için yeni uygulamalar sağlanmıştır.** Android için Microsoft Word, Excel ve PowerPoint uygulamaları artık Intune’a kayıtlı olmayan cihazlarda MAM ilkeleriyle ilişkilendirilebilir. Desteklenen uygulamaların tam listesi için, [Microsoft Intune uygulama iş ortakları](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx) sayfasında Microsoft Intune mobil uygulama galerisine gidin.


### <a name="company-portal-updates"></a>Şirket portalı güncelleştirmeleri

#### <a name="android-company-portal-app"></a>Android Şirket Portalı uygulaması
- **Son kullanıcı bildirimleri**: Son kullanıcılar, cihazlarını Şirket Portalı’na kaydederken veya portaldan kaldırırken artık Android Şirket Portalı uygulamasından bildirimleri göreceklerdir.

- **Android Şirket Portalı uygulamasında Cihaz Kayıt Yöneticileri hesaplarında yapılan değişiklikler.** Performansı ve ölçeği artırmak için, Intune artık Android Şirket Portalı uygulamasının Cihazlarım bölmesinde Cihaz Kayıt Yöneticileri (DEM) cihazlarını göstermez. Yalnızca uygulamayı çalıştıran yerel cihaz, yalnızca Şirket Portalı uygulaması aracılığıyla kaydedilmişse görüntülenir. DEM kullanıcısı, yerel cihazda eylemler gerçekleştirebilir, ancak diğer kaydedilen cihazların uzaktan yönetimi yalnızca Intune yönetici konsolundan gerçekleştirilebilir.

#### <a name="company-portal-website"></a>Şirket Portalı web sitesi
- **Şirket Portalı web sitesi: Cihaz kimliği başlığı son kullanıcılara daha fazla bilgi sağlayacaktır.** Son kullanıcılar artık Şirket Portalı web sitesini kullanırken seçmiş oldukları cihazı kolayca tanımlayabilirler. Yanlış cihaz seçiliyse, giriş sayfası başlığındaki **Buraya dokunun** bağlantısına dokunarak doğru cihazı seçebilecekler.

### <a name="service-deprecation"></a>Hizmeti kullanımdan kaldırma
- **Intune Görüntüleyicisi uygulamaları.** Yeni RMS paylaşım uygulamasının kullanıma sunulmasıyla, Ağustos 2016’dan başlayarak aşağıdaki Intune Görüntüleyicisi uygulamalarını kaldırıyoruz:
    - Intune AV Görüntüleyicisi
    - Intune PDF Görüntüleyicisi
    - Google Play’den Android için Intune Resim Görüntüleyicisi

  Intune Görüntüleyicisi uygulamalarını kullanmak yerine, Android cihazlarda şirket dosyalarını güvenle görüntülemek için üç ayrı uygulama yerine tek bir uygulama dağıtmanıza olanak tanıyan yeni Android için Hak Yönetimi uygulamasını (RMS paylaşımı) kullanmanızı öneririz. RMS paylaşım uygulaması hakkında daha fazla bilgi edinin (belgelerin bağlantılarıyla).

- **Bildirim Kurallarında Özel Grup Hedeflemenin Kaldırılması.**
Intune bildirim kuralları, Intune’dan kime e-posta uyarısı gönderileceğini tanımlar. Şu anda, oluşturduğunuz bir Intune cihaz grubundaki cihazların tüm kullanıcılarına e-posta göndermek için bildirim kuralları yapılandırabilirsiniz. Yaklaşık 1 Haziran 2016’dan başlayarak, kullanıcı tarafından oluşturulan grupları hedeflemek artık desteklenmeyecektir.

    Bugün, bir bildirim kuralıyla Microsoft Intune yönetim konsolundan oluşturduğunuz bir grubu hedeflemek için aşağıdaki adımları izleyebilirsiniz:

    **Yönetici** çalışma alanında **Bildirim Kuralları** > **Yeni Kural Oluştur**’a tıklayın

    Bildirim Kuralı Oluşturma Sihirbazı’nın ikinci adımında, kuralın hedefleyeceği cihaz gruplarını seçin. Bu “cihaz gruplarını seçme” adımı, Intune Konsolu’ndan kaldırılıyor.

    Bu değişiklikle ilgili ilk zaman çizelgesi şöyledir:
    - Haziran 2016’da, yeni kiracılar Bildirim Kuralı Oluşturma Sihirbazı’nın ikinci adımını görmeyecekler. Mevcut kiracılar bundan etkilenmez.
    - Ağustos 2016’ya doğru, mevcut kiracılardan bazıları sihirbazda “cihaz gruplarını seçme” adımını görmeyecekler.
    - Ekim 2016’ya doğru, kiracılardan hiçbirinin sihirbazda “cihaz grupları seçme” adımını görmeyeceğini umuyoruz.


- **iOS Şirket Portalı uygulaması desteğindeki değişiklikler**. Önümüzdeki aylarda, iOS için Microsoft Intune Şirket Portalı uygulamasında yapılacak bir güncelleştirmeyle uygulamanın yalnızca iOS 8.0 veya üstünü çalıştıran cihazları desteklemesi sağlanacak. Kullanıcılar, iOS 8.0’ın altındaki sürümleri çalıştıran yeni cihazları kaydedemeyecekler. iOS 8.0’ın altındaki sürümleri çalıştıran kayıtlı cihazlar yönetilmeye devam edecek ve sınırlı bir süre için Şirket Portalı uygulamasını kullanmaya devam edebilecek. Ancak, Şirket Portalı uygulamasının en son sürümlerine erişmek için cihazlar iOS 8.0 veya üstünü çalıştırıyor olmalıdır. Yeni Intune özelliklerinden tam anlamıyla yararlanmaları için kullanıcılara iOS 8.0 veya üstüne güncelleştirmelerini bildirmenizi öneririz.  


## <a name="april-2016"></a>Nisan 2016
Bu özelliklerin tümü, karma müşteriler için de desteklenmektedir (Intune ile tümleşik Configuration Manager).

### <a name="app-management"></a>Uygulama yönetimi
- **MAM kullanıcı uyumu.**
Artık Azure Active Directory (AAD) kiracınızdaki herhangi bir kullanıcı için, uygulama yönetimi ilkelerinizin [durumunu](/intune-classic/deploy-use/monitor-mobile-app-management-policies-with-Microsoft-Intune) görüntüleyebilirsiniz. Buna aşağıdakiler dahildir:
   - Cihazlar
   - Cihazdaki uygulamalar

   Durum değerleri:

   **İade**: İlkenin kullanıcıya dağıtıldığını ve uygulamanın iş bağlamında kullanıldığını ve ilkeyi başarıyla aldığını gösterir.

    **İade değil**: İlkenin kullanıcıya dağıtıldığını, ancak uygulamanın o zamandan bu yana iş bağlamında kullanılmadığını gösterir.


- **Outlook kişilerinin eşitlenmesini önlemek için MAM denetimleri (Android).**
[Mobil uygulama yönetimi](/intune-classic/deploy-use/wipe-managed-company-app-data-with-Microsoft-Intune) için yeni bir ayar kullanılabilir durumda, yerel adres defterine kaydedilmiş kişiler kaldırılacak. Bu yeni ayar başlangıçta Android cihazlarda Outlook uygulaması tarafından desteklenmektedir.

### <a name="device-management"></a>Cihaz yönetimi
- **Şirkete ait cihazlar için telefon numarası kimliği.** “Şirket” olarak sınıflandırılmış telefonlar artık, örneğin bir mobil cihaz envanter raporu çalıştırdığınızda, tam telefon numaralarıyla tanımlanır. BYOD telefon numaraları, **** ile gizlenmeye devam edilecektir, yalnızca 4 hane görüntülenmektedir.


### <a name="company-portal-updates"></a>Şirket portalı güncelleştirmeleri
**Android Şirket portalı uygulaması** Cihazlarını Intune’a kaydetmeyen ve doğru sertifika yüklememiş kullanıcılar, Android Şirket Portalı uygulamasına oturum açamaz ve "Cihazınızda gerekli bir sertifika eksik olduğundan oturum açılamıyor." iletisini görür. İleti, kullanıcıların sertifikayı yüklemek için yönergeleri görmek üzere dokunabileceği bir "Bu durum nasıl çözümlenir" bağlantısı içerir. Son kullanıcıların sorunu çözümlemek için izlediği adımları görmek için, bkz. [Cihazınızda gerekli bir sertifika eksik](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing).

**iOS Şirket Portalı uygulaması** Listelenen uygulamalar, listelenen cihazlar ve BT iletişim bilgilerini içeren ana ekran içeriğini yenilemek üzere, çekerek yenileme eylemi için destek eklenmiştir. Çekerek yenileme eylemi, uyum veya ilk bilgilerini denetlemez, bu, geçerli cihazınız için döşeme seçilerek ve **Eşitle** düğmesine dokunularak yapılabilir.

**Windows 10 Mobile ve Windows Phone 8.1 Şirket Portalı uygulaması** Son kullanıcılar iş kolu uygulamaları yüklediğinde artık iyileştirilmiş bir uygulama yükleme deneyimi görecektir. Uygulama yüklemesi uzun sürüyorsa, kullanıcılar, eşitleme işleminin devam etmesini zorlamak için cihazlarını el ile eşitleyebilir. Son kullanıcı yönergelerini gözden geçirmek için, bkz. [Uygulama yüklemelerini hızlandırmak için cihazınızı el ile eşitleme](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually).

**Şirket Portalı web sitesi** Windows 10 Mobile ve Windows Phone 8.1 kullanıcıları iş kolu uygulamaları yüklediğinde, artık yüklemelerinin durumu hakkında daha fazla ayrıntı sağlayan aşağıdaki yeni durumları görecektir:

* **Cihazın eşitlenmesi bekleniyor** – kullanıcı "Yükle" öğesine dokunmuştur ve cihaz şimdi Intune altyapısıyla eşitlemeye çalışıyordur. Yüklemenin tamamlanabilmesi için eşitleme gereklidir. "Cihazın eşitlenmesi bekleniyor" iletisi aynı zamanda bir bağlantıdır, kullanıcılar, eşitleme işlemi çok uzun sürüyorsa veya duruyorsa buna dokunarak cihazlarını Intune ile nasıl el ile eşitleyeceklerine dair [yönergeleri](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) görebilir.
* **İndiriliyor** – kullanıcının indirme isteği işlenmektedir ve cihaz uygulamayı indiriyor ve yüklüyordur.

Bu durumlar eklenmeden önce, bir uygulamanın yüklenmesi uzun sürdüğünde, yalnızca, ekranda saatlerce kalabilecek “Yükleniyor” durumu gördükleri için kullanıcıların kafası karışıyordu. Yeni durumların eklenmesi, destek çağırmak yerine, kullanıcıların artık “Cihazın eşitlenmesi bekleniyor" bağlantısına dokunabileceği ve eşitleme işleminin devam etmesini zorlamak için yönergeleri izleyebileceği anlamına geliyor.

>[!div class="step-by-step"]

>[&larr; **Intune’daki yenilikler**](whats-new-in-microsoft-intune.md)    
