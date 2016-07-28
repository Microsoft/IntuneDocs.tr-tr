---
title: "Önceki sürümler | Microsoft Intune"
description: 
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b812a3124c330a9b45378c99ee77959c8d7bc537
ms.openlocfilehash: b30ab535ac7d8b10e3feef52ab01a68ba8572dba


---

# Önceki Intune sürümleri
## Haziran 2016
### Intune hizmet durumu
Intune’un hizmet durumu bilgileri, diğer Microsoft hizmetleriyle birlikte merkezi bir konuma taşındı. Artık bu bilgileri Office 365 yönetim portalında, Hizmet Durumu’nun altında bulabilirsiniz. Daha fazla bilgi için [bu blog gönderisine](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/) bakın.

### Uygulama yönetimi
- **Geliştirilmiş Windows 10 kurumsal veri ilkesi yapılandırma deneyimi.** Windows 10 kurumsal veri koruma ilkesi yapılandırma deneyiminde, uygulama kuralları oluşturma, ağ sınırı tanımını belirtme ve diğer kurumsal veri koruma ayarları ile ilgili geliştirmeler yapıldı. Daha fazla bilgi için bkz: [Microsoft Intune kullanarak kurumsal veri koruma (EDP) ilkesi oluşturma](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune).


### Cihaz yönetimi
- **Olası istenmeyen uygulamalara karşı koruma sağlayan Windows Defender ilke ayarı.** Windows 10 Desktop ve Mobile için genel yapılandırma ilkesine **İstenmeyebilecek Uygulama Algılama** adlı yeni bir Windows Defender ayarı eklendi. Bu ayarı kullanarak kayıtlı Windows masaüstü bilgisayarlarını, Windows Defender tarafından istenmeyebilecek yazılım olarak sınıflandırılan yazılımları çalıştırmaya karşı koruyabilirsiniz. Bu uygulamaların çalıştırılmasına karşı koruma sağlayabilir veya istenmeyebilecek bir uygulama yüklendiğinde raporlanması için denetim modunu kullanabilirsiniz. Daha fazla bilgi için, bkz. [Microsoft Intune’da Windows 10 ilke ayarları](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).
<!---TFS 1244478--->

### Koşullu erişim
- **Intune için Cisco ISE ağ erişimi denetim ilkesi.**  Cisco Identity Service Engine (ISE) 2.1 ile birlikte Microsoft Intune’u kullanan müşteriler, ISE’de bir ağ erişimi denetim ilkesi ayarlayabilir.

    Bu ilke kullandığında, ağa WiFi veya VPN ile erişmeye çalışan cihazlara erişim izni verilmesi için cihazların aşağıdaki koşulları karşılaması gerekir:

    * Intune tarafından yönetiliyor olmalıdır
    * Dağıtılmış tüm Intune uyumluluk ilkeleriyle uyumlu olmalıdır

 Uyumsuz cihazları kullanan son kullanıcıların erişim elde etmek için kaydolması ve uyumluluk sorunlarını gidermesi istenir.
- **Tarayıcı için koşullu erişim.** [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md) ve [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md) için, yalnızca yönetilen ve uyumlu iOS ile Android cihazlarında desteklenen web tarayıcılarından erişilebilmelerini sağlayacak bir koşullu erişim ilkesi ayarlayabilirsiniz. iOS ve Android cihazlarıyla Outlook Web Access (OWA) ve SharePoint sitelerinde oturum açmayı deneyen son kullanıcılardan, oturum açma işlemini tamamlayabilmek için önce cihazlarını Intune’a kaydetmeleri ve tüm uyumsuzluk sorunlarını çözmeleri istenecektir.
<!---TFS 1175844--->

- **Dynamics CRM Online koşullu erişimi destekler.** [Dynamics CRM Online](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md) için, yalnızca yönetilen ve uyumlu iOS ile Android cihazları tarafından erişilebilmelerini sağlayacak bir koşullu erişim ilkesi ayarlayabilirsiniz. iOS ve Android’de Dynamics CRM mobil uygulamasında oturum açmaya çalışan son kullanıcılardan, oturum açma işlemini tamamlanabilmek için Intune’a kaydolmaları ve tüm uyumsuzluk sorunlarını çözmeleri istenecektir.
<!---TFS1295358--->

##E Şirket portalı güncelleştirmeleri

#### Android Şirket Portalı uygulaması

- BT yöneticileri yeni "Cihazların bilinmeyen kaynaklardan uygulama yüklemesine izin vermemesini sağla (Android 4.0 +)" ilkesini uyguladığında, Android 4.0 veya üstü cihazlara sahip son kullanıcılar, "Bilinmeyen kaynaklardan yükleme devre dışı bırakılmalıdır" iletisini görür. Kullanıcıların, **Ayarlar** > **Güvenlik** kısmına gitmesi ve **Bilinmeyen kaynaklar**’ı kapatması gerekir. Uyumluluk iletisindeki bir bağlantı, kullanıcıların, ileti hakkında ve ayarı neden kapatmaları gerektiği hakkında aha fazla [bilgi](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) almasını sağlar.

- BT yöneticileri yeni "Cihazların, güvenlik tehditleri için uygulamaların taranmasını etkinleştirmiş olmasını gerektir (Android 4.0 +)” ilkesini uyguladığında, Android 4.0 veya üstü cihazlara sahip son kullanıcılar, “Cihazı güvenlik tehditleri için tara” iletisini görür. Kullanıcıların, **Ayarlar** > **Google** > **Güvenlik** kısmına gitmesi ve **Cihazı güvenlik tehditleri için tara**’yı açması gerekir. Uyumluluk iletisindeki bir bağlantı, kullanıcıların, ileti hakkında ve ayarı neden açmaları gerektiği hakkında daha fazla [bilgi](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) almasını sağlar.

- BT yöneticileri yeni "USB hata ayıklamanın devre dışı olmasını gerektir (Android 4.2 +)" ilkesini uyguladığında, Android 4.2 veya üstü cihazlara sahip son kullanıcılar, "USB hata ayıklama devre dışı bırakılmalıdır" iletisini görür. Kullanıcıların, **Ayarlar** > **Geliştirici seçenekleri** kısmına gitmesi ve “**USB hata ayıklama**”yı kapatması gerekir. Uyumluluk iletisindeki bir bağlantı, kullanıcıların, ileti hakkında ve ayarı neden kapatmaları gerektiği hakkında aha fazla [bilgi](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) almasını sağlar.

- BT yöneticileri yeni "Minimum Android güvenlik düzeltme eki düzeyi (Android 6.0 +)" ilkesini uyguladığında, Android 6.0 veya üstü cihazlara sahip son kullanıcılar, "Bu cihaz, en düşük Android güvenlik düzeltme eki düzeyini karşılamıyor" iletisini görür. Kullanıcıların, gerekli güvenlik düzeltme ekini yüklemesi gerekir. Uyumluluk iletisindeki bir bağlantı, kullanıcıların gerekli güvenlik düzeltme ekini nasıl yükleneceği hakkında [bilgi](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) almasını ve mevcut durumda kendilerinde hangi güvenlik düzeltme ekinin yüklü olduğunu görmesini sağlar.

#### iOS Şirket Portalı uygulaması

- Son kullanıcılar iş kolu uygulamaları yüklediğinde artık iyileştirilmiş bir uygulama yükleme deneyimi görecektir. Uygulama yüklemesi uzun sürüyorsa, kullanıcılar, eşitleme işleminin devam etmesini zorlamak için cihazlarını el ile eşitleyebilir. Son kullanıcı yönergelerini gözden geçirmek için, bkz. [iOS cihazınızı el ile eşitleme](/Intune/EndUser/sync-your-device-manually-ios).

- iOS için Microsoft Intune Şirket Portalı uygulaması, iOS 8.0 ve sonraki sürümleri desteklemek için güncelleştirildi. Bu güncelleştirme, yalnızca cihaz iOS 8.0 veya sonraki sürümleri çalışıyorsa son kullanıcıların Şirket Portalı uygulamasını yükleyebileceği ve Intune’a yeni cihazları kaydedebileceği anlamına gelir. Desteklenmeyen bir iOS sürümünü çalıştıran, önceden kayıtlı cihazları olan kullanıcılar, cihazlarında Şirket Portalı uygulamasını kullanmaya devam edebilir.


## Mayıs 2016

Bu özelliklerin tümü, karma dağıtımlar için de desteklenmektedir (Intune içeren Yapılandırma Yöneticisi). Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler](https://technet.microsoft.com/en-us/library/mt718155.aspx) sayfasını gözden geçirin.

### Belgeler
[Docs.microsoft.com](https://docs.microsoft.com/en-us/intune)’un önizleme sürümüne hoş geldiniz!
Bu, siz müşterilerimizin Intune’u anlamasını ve kullanmasını kolaylaştırmak için tasarlanmış, tamamen yeni, modern bir içerik platformudur.
Tüm yeni özellikler hakkındaki bilgileri okumak için, bkz. [Docs.microsoft.com ile tanışın](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/)

### Intune hizmet durumu
Intune’un hizmet durumu bilgileri, diğer Microsoft hizmetleriyle birlikte merkezi bir konuma taşındı. Artık bu bilgileri [Office 365 yönetim portalında](https://portal.office.com/Admin/Default.aspx), **Hizmet Durumu**’nun altında bulabilirsiniz.
Daha fazla bilgi için [bu blog gönderisine](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/) bakın.


### Uygulama yönetimi
- **MAM SDK’sı: PIN uzunluğu yapılandırmasını destekler.** Cihaz PIN’ine benzer şekilde MAM uygulamalarının PIN’i için de uzunluğu belirtebileceksiniz. Bunun için son kullanıcıların sizin ayarladığınız yeni kısıtlamalara uyması gerekecektir. Daha uzun girişi kabul eden biraz değiştirilmiş bir PIN ekranı görecekler. Ayrıntılar için bkz. [Android için MAM ilkesi ayarları](/intune/deploy-use/android-mam-policy-settings) ve [iOS için MAM ilkesi ayarları](/intune/deploy-use/ios-mam-policy-settings).

- **iOS ve Android için Skype Kurumsal.** Artık [kayıt ilkeleri olmadan MAM](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) ile Skype Kurumsal’ı hedefleyebilirsiniz. Kullanıcılar oturum açtığında, MAM ilkeleri uygulanır.

- **MAM ilkeleriyle yönetim için yeni uygulamalar sağlanmıştır.** Android için Microsoft Word, Excel ve PowerPoint uygulamaları artık Intune’a kayıtlı olmayan cihazlarda MAM ilkeleriyle ilişkilendirilebilir. Desteklenen uygulamaların tam listesi için, [Microsoft Intune uygulama iş ortakları](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) sayfasında Microsoft Intune mobil uygulama galerisine gidin.


### Şirket portalı güncelleştirmeleri

#### Android Şirket Portalı uygulaması
- **Son kullanıcı bildirimleri**: Son kullanıcılar, cihazlarını Şirket Portalı’na kaydederken veya portaldan kaldırırken artık Android Şirket Portalı uygulamasından bildirimleri göreceklerdir.

- **Android Şirket Portalı uygulamasında Cihaz Kayıt Yöneticileri hesaplarında yapılan değişiklikler.** Performansı ve ölçeği artırmak için, Intune artık Android Şirket Portalı uygulamasının Cihazlarım bölmesinde Cihaz Kayıt Yöneticileri (DEM) cihazlarını göstermez. Yalnızca uygulamayı çalıştıran yerel cihaz, yalnızca Şirket Portalı uygulaması aracılığıyla kaydedilmişse görüntülenir. DEM kullanıcısı, yerel cihazda eylemler gerçekleştirebilir, ancak diğer kaydedilen cihazların uzaktan yönetimi yalnızca Intune yönetici konsolundan gerçekleştirilebilir.

#### Şirket Portalı web sitesi
- **Şirket Portalı web sitesi: Cihaz kimliği başlığı son kullanıcılara daha fazla bilgi sağlayacaktır.** Son kullanıcılar artık Şirket Portalı web sitesini kullanırken seçmiş oldukları cihazı kolayca tanımlayabilirler. Yanlış cihaz seçiliyse, giriş sayfası başlığındaki **Buraya dokunun** bağlantısına dokunarak doğru cihazı seçebilecekler.

## Yakında
- **İleti merkezi kullanıcı arabirimi başlatılıyor**. Intune’un [Office 365 Yönetim portalına](https://portal.office.com/) geçirilme sürecinin bir parçası olarak, yeni özellikleri haber vermek ve diğer bildirimleri yapmak için portalın İleti Merkezi’nden yararlanmaya başlayacağız. Ayrıca, yardımcı Office 365 Yönetim mobil uygulamasını yükleyerek cep telefonunuzda bildirimleri alabilir ve iletileri kolayca kullanıcılara veya dağıtım listesi diğer adlarına iletebilirsiniz.
Mayıs sürümümüzde size güncelleştirmelerin ne zaman tamamlanacağını haber vermek için İleti Merkezi’ni kullanmaya başlayacağız; ayrıca yeni ve geliştirilmiş Intune özellikleriyle ilgili bilgi de ekleyeceğiz. Bugün [Office 365 Yönetim portalında](https://portal.office.com/) oturum açarak ve sol gezinti bölmesindeki İLETİ MERKEZİ seçeneğini kullanarak İleti Merkezi’ni gözden geçirin.

- **Cihaz Kayıt Yöneticileri hesaplarındaki değişiklikler**. Performansı ve ölçeği artırmak için, Intune artık iOS Şirket Portalı uygulamasının **Cihazlarım** bölmesinde **tüm** Cihaz Kayıt Yöneticileri (DEM) cihazlarını göstermez. Yalnızca uygulamayı çalıştıran yerel cihaz, yalnızca Şirket Portalı uygulaması aracılığıyla kaydedilmişse görüntülenir. DEM kullanıcısı, yerel cihazda eylemler gerçekleştirebilir, ancak diğer kaydedilen cihazların uzaktan yönetimi yalnızca Intune yönetici konsolundan gerçekleştirilebilir. Ayrıca Intune, Apple Cihaz Kayıt Programı veya Apple Configurator aracıyla DEM hesaplarını kullanımdan kaldırmaktadır. Her iki kayıt yöntemi, paylaşılan iOS cihazları için kullanıcısız kaydı zaten desteklemektedir. Yalnızca, paylaşılan cihazlar için kullanıcısız kayıt kullanılamadığında DEM hesapları kullanın.

### Bulut yol haritası
[Bulut Platformu yol haritası](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune) ile yaklaşan Intune geliştirmelerinden haberdar olun.

### Hizmeti kullanımdan kaldırma
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


## Nisan 2016
Bu özelliklerin tümü, karma müşteriler için de desteklenmektedir (Intune ile tümleşik Configuration Manager).
### Uygulama yönetimi
- **MAM kullanıcı uyumu.**
Artık Azure Active Directory (AAD) kiracınızdaki herhangi bir kullanıcı için, uygulama yönetimi ilkelerinizin [durumunu](monitor-mobile-app-management-policies-with-Microsoft-Intune.md) görüntüleyebilirsiniz. Buna aşağıdakiler dahildir:
   - Cihazlar
   - Cihazdaki uygulamalar

   Durum değerleri:

   **İade**: İlkenin kullanıcıya dağıtıldığını ve uygulamanın iş bağlamında kullanıldığını ve ilkeyi başarıyla aldığını gösterir.

    **İade değil**: İlkenin kullanıcıya dağıtıldığını, ancak uygulamanın o zamandan bu yana iş bağlamında kullanılmadığını gösterir.


- **Outlook kişilerinin eşitlenmesini önlemek için MAM denetimleri (Android).**
Cihaz kaydı olmadan [mobil uygulama yönetimi](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) için yeni bir ayar vardır. Bu ayar, bir uygulamanın Android cihazlarda kişileri yerel adres defterine eşitlemesini engellemenizi sağlar. Bu ayar etkinleştirildiğinde, hedeflenen uygulamalar artık kişileri yerel adres defterine kaydedemeyecektir. Bu ayar devre dışı bırakıldığında, hedeflenen uygulamalar kişileri yerel adres defterine kaydedebilecektir. [Bir cihazı veya uygulamayı uzaktan temizlediğinizde](wipe-managed-company-app-data-with-Microsoft-Intune.md), yerel adres defterine zaten kaydedilmiş kişiler kaldırılacaktır. Bu yeni ayar başlangıçta Android cihazlarda Outlook uygulaması tarafından desteklenmektedir.

### Cihaz yönetimi
- **Şirkete ait cihazlar için telefon numarası kimliği.** “Şirket” olarak sınıflandırılmış telefonlar artık, örneğin bir mobil cihaz envanter raporu çalıştırdığınızda, tam telefon numaralarıyla tanımlanır. BYOD telefon numaraları, **** ile gizlenmeye devam edilecektir, yalnızca 4 hane görüntülenmektedir.


### Şirket portalı güncelleştirmeleri
**Android Şirket portalı uygulaması** Cihazlarını Intune’a kaydetmeyen ve doğru sertifika yüklememiş kullanıcılar, Android Şirket Portalı uygulamasına oturum açamaz ve "Cihazınızda gerekli bir sertifika eksik olduğundan oturum açılamıyor." iletisini görür. İleti, kullanıcıların sertifikayı yüklemek için yönergeleri görmek üzere dokunabileceği bir "Bu durum nasıl çözümlenir" bağlantısı içerir. Son kullanıcıların sorunu çözümlemek için izlediği adımları görmek için, bkz. [Cihazınızda gerekli bir sertifika eksik](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing).

**iOS Şirket Portalı uygulaması** Listelenen uygulamalar, listelenen cihazlar ve BT iletişim bilgilerini içeren ana ekran içeriğini yenilemek üzere, çekerek yenileme eylemi için destek eklenmiştir. Çekerek yenileme eylemi, uyum veya ilk bilgilerini denetlemez, bu, geçerli cihazınız için döşeme seçilerek ve **Eşitle** düğmesine dokunularak yapılabilir.

**Windows 10 Mobile ve Windows Phone 8.1 Şirket Portalı uygulaması** Son kullanıcılar iş kolu uygulamaları yüklediğinde artık iyileştirilmiş bir uygulama yükleme deneyimi görecektir. Uygulama yüklemesi uzun sürüyorsa, kullanıcılar, eşitleme işleminin devam etmesini zorlamak için cihazlarını el ile eşitleyebilir. Son kullanıcı yönergelerini gözden geçirmek için, bkz. [Uygulama yüklemelerini hızlandırmak için cihazınızı el ile eşitleme](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually).

**Şirket Portalı web sitesi** Windows 10 Mobile ve Windows Phone 8.1 kullanıcıları iş kolu uygulamaları yüklediğinde, artık yüklemelerinin durumu hakkında daha fazla ayrıntı sağlayan aşağıdaki yeni durumları görecektir:

* **Cihazın eşitlenmesi bekleniyor** – kullanıcı "Yükle" öğesine dokunmuştur ve cihaz şimdi Intune altyapısıyla eşitlemeye çalışıyordur. Yüklemenin tamamlanabilmesi için eşitleme gereklidir. "Cihazın eşitlenmesi bekleniyor" iletisi aynı zamanda bir bağlantıdır, kullanıcılar, eşitleme işlemi çok uzun sürüyorsa veya duruyorsa buna dokunarak cihazlarını Intune ile nasıl el ile eşitleyeceklerine dair [yönergeleri](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) görebilir.
* **İndiriliyor** – kullanıcının indirme isteği işlenmektedir ve cihaz uygulamayı indiriyor ve yüklüyordur.

Bu durumlar eklenmeden önce, bir uygulamanın yüklenmesi uzun sürdüğünde, yalnızca, ekranda saatlerce kalabilecek “Yükleniyor” durumu gördükleri için kullanıcıların kafası karışıyordu. Yeni durumların eklenmesi, destek çağırmak yerine, kullanıcıların artık “Cihazın eşitlenmesi bekleniyor" bağlantısına dokunabileceği ve eşitleme işleminin devam etmesini zorlamak için yönergeleri izleyebileceği anlamına geliyor.


## Mart 2016
### 29 Mart 2016 itibariyle yenilikler
Windows 10 genel yapılandırma ilkesine güncelleştirme hariç olmak üzere, 29 Mart 2016’da sunulan tüm özellikler, karma müşteriler için de desteklenmektedir (Intune ile tümleşik Configuration Manager). Windows 10 genel yapılandırma ilkesi güncelleştirmesi için karma desteği yakında geliyor. Bu özelliklerden bazılarının, Configuration Manager'ın en son sürümünü gerektiğini lütfen unutmayın.

### Uygulama yönetimi
- **Outlook kişilerinin eşitlenmesini önlemek için MAM denetimleri (iOS).** Cihaz kaydı olmadan mobil uygulama yönetimi için yeni bir ayar vardır. Bu ayar, bir uygulamanın iOS cihazlarda kişileri yerel adres defterine eşitlemesini engellemenizi sağlar. Bu ayar etkinleştirildiğinde, uygulama artık kişileri yerel adres defterine kaydedemeyecektir. Bu ayar devre dışı bırakıldığında, uygulama kişileri yerel adres defterine kaydedebilecektir. Bir cihazı seçmeli olarak temizlediğinizde, yerel adres defterine zaten kaydedilmiş tüm kişiler kaldırılacaktır. Bu yeni ayar, iOS cihazlarda Outlook uygulaması tarafından desteklenmektedir. Bu ve diğer ayarlar hakkında daha fazla ayrıntı için, bkz. [MAM ilkeleri oluşturma ve dağıtma](https://technet.microsoft.com/en-us/library/dn292747.aspx).

### Erişim denetimi
- **Skype Kurumsal Çevrimiçi Sürüm, koşullu erişimi destekler.** Skype Kurumsal Çevrimiçi Sürüm için, yalnızca yönetilen ve uyumlu iOS ve Android cihazları tarafından erişilebileceği şekilde, bir koşullu erişim ilkesi ayarlayabilirsiniz. iOS ve Android’de Skype Kurumsal Çevrimiçi mobil uygulamasında oturum açmaya çalışan son kullanıcılardan, oturum açma işlemini tamamlanabilmek için Intune’a kaydolmaları ve tüm uyumsuzluk sorunlarını çözmeleri istenecektir. Ayrıntılar için, bkz. [Skype Kurumsal Çevrimiçi Sürümüne erişimi yönetme](https://technet.microsoft.com/en-us/library/mt695297.aspx).

### Cihaz yönetimi
- **iOS 9.3 için Intune desteği.** 21 Mart Pazartesi günü Apple, iOS 9.3’ün kullanıma sunulduğunu duyurdu. Microsoft Intune’un, Apple'nın en son mobil işletim sistemi sürümü ile uyumlu olmasını sağlamak için çalışmalarımızı sürdürüyorduk ve [Intune’un 9.3 iOS cihazlarını yönetmeyi desteklediğini duyurmaktan memnuniyet duyuyoruz](https://blogs.technet.microsoft.com/microsoftintune/2016/03/23/microsoft-intune-provides-support-for-ios-9-3/).

  Kullanıcılar cihazlarını iOS 9.3 sürümüne yükselttiklerinde, şu anda iOS cihazlarını yönetmeye dair mevcut tüm Intune özellikleri sorunsuz bir şekilde çalışmaya devam edecektir. Ayrıca, iOS 9.3 bugün karma müşteriler için de desteklenmektedir (Intune ile tümleşik Configuration Manager).

- **Windows 10 genel yapılandırma ilkesi artık, kaydolmuş Windows 10 bilgisayarlarda Windows Defender’ı yönetmek için ayarlar içermektedir.** Ayrıntılar için, bkz. [Microsoft Intune’da Windows 10 yapılandırma ilkesi ayarları](https://technet.microsoft.com/en-us/library/mt404697.aspx).


### Şirket portalı

- **Windows uygulama paketleri doğrudan Şirket Portalı web sitesinden kullanılabilir.** Windows 8, Windows 8.1 ve Windows RT bilgisayarları artık Windows uygulama paketlerini (.appx uzantılı) doğrudan Şirket Portalı web sitesinden yükleyebilir. Daha önce, uygulamaları yüklemek için, Şirket Portalı uygulamasını dağıtmanız ya da kullanıcıların cihazlarına Şirket Portalı uygulamasını yüklemesi gerekiyordu.

- **Kullanıcıların, Şirket Portalı web sitesinden cihazlarını uzaktan kilitleyebilir.** Kullanıcıların, cihazları kaybolduğunda veya çalındığında cihazlarını Portal’dan uzaktan kilitlemesine olanak sağlamak için Şirket Portalı web sitesine yeni bir Uzaktan Kilitleme seçeneği eklenmiştir. Bkz. [son kullanıcı yönergeleri](https://technet.microsoft.com/library/mt590895.aspx/?wt.mc_id=ui#BKMK_iwp_remote_lock). Aşağıdaki tabloda, Intune Standalone ve Intune ile Configuration Manager için Uzaktan Kilitleme platform desteği listelenmektedir.

|Platform | Destek ayrıntıları|
|---------|----------------|
|Android |Desteklenir|
|iOS |Desteklenir|
|Windows 10 Mobile |Yalnızca telefonda bir parola grubu varsa desteklenir|
|Windows 10 Masaüstü |Desteklenmez|
|Windows Phone 8.1 |Yalnızca telefonda bir parola grubu varsa desteklenir|
|Windows Phone 8.0 |Desteklenmez|
|Bilgisayar (Windows 8.0 ve öncesi) |Desteklenmez|
|Bilgisayar (Windows 8.1) |Desteklenmez|

### 10 Mart 2016 itibariyle yenilikler

### Uygulama yönetimi

- **Üçüncü taraf bir MDM çözümüne kayıtlı cihazlar için iOS "Birlikte açma" yönetiminden yararlanın** iOS "Birlikte açma" yönetiminden yararlanmak için üçüncü taraf mobil cihaz yönetimi (MDM) satıcınızı kullanabilirsiniz. Yapılandırma profili ayarlarında kısıtlamalar belirleyebilir ve uygulamayı [iOS uygulamaları arasında veri aktarımını yönetme](manage-data-transfer-between-ios-apps-with-microsoft-intune.md) kullanarak dağıtabilirsiniz.

     Bu yaklaşımın iki ana faydası vardır:

     1. Kullanıcıların Bulut Hizmetleri veya diğer uygulamalardan herhangi bir kurumsal veriye erişebilmesi için iş hesaplarıyla oturum açması gerekir. Bunun yapılması, verilere erişildiğinde mobil uygulama yönetimi (MAM) ilkelerinin yerinde olmasını sağlar.

     2. Yönetilen e-posta profilleri ve bir üçüncü taraf MDM çözümü aracılığıyla dağıtılmış diğer yönetilen uygulamalar, Intune MAM ilkelerine sahip uygulamalarla dosya ve veri paylaşabilir.

- **Microsoft Outlook uygulamasını Intune'a kayıtlı olmayan cihazlar için MAM ilkeleriyle yönetin** Microsoft Outlook uygulamasını bundan böyle Intune’a kayıtlı olmayan cihazlarda Intune mobil uygulama yönetimi ilkesiyle yönetebilirsiniz. MAM özellikleriyle güncelleştirilmiş Microsoft Outlook uygulaması hem [iOS](https://itunes.apple.com/us/app/microsoft-outlook-email-calendar/id951937596?mt=8) hem de [Android](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook) cihazlarda kullanılabilir. Bir MAM ilkesi oluşturmak için [Mobil uygulama yönetimi ilkeleri oluşturma ve dağıtma](https://technet.microsoft.com/library/mt627829.aspx) konusundaki yönergeleri kullanın.  


- **Mobil uygulama yapılandırma ilkeleri, iOS uygulamalarına yönelik kullanıcı ayrıntılarını belirtmek için daha fazla esneklik sağlar** iOS uygulamasının açıldığında ihtiyaç duyabileceği kullanıcı ayarlarını sağlayabilirsiniz. Örneğin, bir ağ bağlantı noktası veya kullanıcı adı belirtebilirsiniz. Ayrıntılar için bkz. [iOS uygulamalarını Microsoft Intune’da mobil uygulama yapılandırma ilkeleriyle yapılandırma](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md).


- **Microsoft Intune için Adobe Reader’ı kuruluşunuzda Intune ile yönetilen iOS cihazlarına dağıtın** iOS için Adobe Reader uygulaması artık Intune mobil uygulama yönetimi ilkesiyle kayıtlı cihazlar üzerinde yönetilebilir.

- **Dağıtılmış web kliplerinin yönetilen tarayıcıda açıldığından emin olun** Yalnızca iOS ve Android cihazlarda yönetilen tarayıcı kullanılarak açılabilen hedeflenen web kliplerini dağıtabilirsiniz. Örneğin, bağlantıları Şirket Portalı üzerinden şirket kaynaklarına dağıtırsınız ve kullanıcılar bağlantılara gittiğinde bağlantılar MAM ilkesi tarafından yönetilebildikleri yönetilen tarayıcıda doğrudan açılır. Ayrıntılar için bkz. [Uygulama dağıtma](deploy-apps.md).


- **Intune yönetici konsolundan Windows 10 cihazlara yönelik İş İçin Windows Mağazası uygulamalarını bulun, yönetin ve dağıtın** Intune’da uygulamaları bulmak, yönetmek ve yönettiğiniz Windows 10 cihazlara dağıtmak üzere İş İçin Windows Mağazası desteği sağlanır. İş İçin Windows Mağazası bu uygulamaları Intune yönetici konsolundan (diğer uygulamaları yönetmek için kullandığınız konsol) dağıtma ve izleme sürecini yönetmenize olanak sağlar. Özellikle, İş İçin Windows Mağazası “çevrimiçi lisanslı uygulamaların” içerik ve lisansını yönetir. Ayrıntılar için bkz. [İş için Windows Mağazası'ndan satın aldığınız uygulamaları yönetme](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md).


### Cihaz yönetimi
- **iOS cihazları için PFX sertifikalarının dağıtımı** Intune yöneticileri iOS cihazlarda Wi-Fi, e-posta ve VPN kimlik doğrulamasına yönelik iOS PFX sertifikaları oluşturup dağıtabilir. Bu özellik Android ve Windows 10 cihazlarda zaten mevcuttur. Ayrıntılar için bkz. [Sertifika profillerini kullanarak şirket kaynaklarına erişimi etkinleştirme](secure-resource-access-with-certificate-profiles.md).


- **Uygulamaları ve ilkeleri kullanıcı kategorisi seçimine göre farklı cihaz gruplarına uygulayın** Intune administrators can now define custom device categories for users to select from during enrollment. Örneğin yöneticiler, kullanıcılarının "Yazar Kasa" veya "Dağıtım Kamyonu" ya da "Stok Odası" için kullanılan bir cihaz kaydettiğini belirtmesini isteyebilir. Seçilen kategori, cihazın kayıtlı cihaza farklı uygulamalar ve ilkeler dağıtmak için kullanılabilecek bir Intune cihaz grubunun üyesi olmasına neden olur. Ayrıntılar için bkz. [Cihazları cihaz grubu eşleme ile kategorilere ayırma](categorize-devices-with-device-group-mapping-in-microsoft-intune.md).

### Microsoft Şirket Portalı değişiklikleri ve güncelleştirmeleri
Bu sürümde, Şirket Portalı’nda aşağıdaki değişiklikler yapılmıştır.

**Android Şirket Portalı uygulaması**

* Kullanıcılarınız mobil uygulama yönetimi (MAM) tarafından yönetilen bir uygulama başlattığında, şirketi tarafından uygulamanın yönetildiğini bildiren bir ileti görürler. Kullanıcılar bundan böyle “Daha Fazla Bilgi” bağlantısına dokunarak “yönetilen uygulamaların” ne anlama geldiği hakkında buradan [daha fazla bilgi](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_use_mgd_apps) alabilirler. Ayrıca “Bir Daha Gösterme” seçeneğine dokunarak, uygulamayı başlattıklarında iletinin bir daha görüntülenmemesini sağlayabilirler.
* Kullanıcılara kayıt işleminde kılavuzluk eden, kullanıcıların neden kaydolması gerektiği ve BT yöneticilerinin kayıtlı cihazlarda neleri görebileceği ve göremeyeceği hakkında daha fazla bilgi veren yeni ekranlar eklenmiştir. Ayrıntılar için, [kayıt yönergelerine](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc) bakın.
* Kayıt hata iletileri artık Şirket Portalı uygulamasında görüntülenmektedir. Daha önce bu iletiler Şirket Portalı web sitesinde görüntüleniyordu. Bu değişikliğin yapılması tüm hata iletilerinin bundan böyle iki farklı yerde değil, tek bir yerde görüneceği anlamına gelmektedir.


**iOS Şirket Portalı uygulaması**
* Kullanıcılarınız mobil uygulama yönetimi (MAM) tarafından yönetilen bir uygulama başlattığında, şirketi tarafından uygulamanın yönetildiğini bildiren bir ileti görürler. Kullanıcılar bundan böyle “Daha Fazla Bilgi” bağlantısına dokunarak “yönetilen uygulamaların” ne anlama geldiği hakkında buradan [daha fazla bilgi](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_use_mgd_apps) alabilirler. Ayrıca “Bir Daha Gösterme” seçeneğine dokunarak, uygulamayı başlattıklarında iletinin bir daha görüntülenmemesini sağlayabilirler.
* Kullanıcılara kayıt işleminde kılavuzluk eden, kullanıcıların neden kaydolması gerektiği ve BT yöneticilerinin kayıtlı cihazlarda neleri görebileceği ve göremeyeceği hakkında daha fazla bilgi veren yeni ekranlar eklenmiştir. Ayrıntılar için, [kayıt yönergelerine](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device) bakın.
* Kayıt hata iletileri artık Şirket Portalı uygulamasında görüntülenmektedir. Daha önce bu iletiler Şirket Portalı web sitesinde görüntüleniyordu. Bu değişikliğin yapılması tüm hata iletilerinin bundan böyle iki farklı yerde değil, tek bir yerde görüneceği anlamına gelmektedir.




## Şubat 2016
### Microsoft Şirket Portalı değişiklikleri ve güncelleştirmeleri

Bu sürümde, Şirket Portalı’nda aşağıdaki değişiklikler yapılmıştır.

#### Android Şirket Portalı uygulaması
- Kullanıcılara kayıt işleminde kılavuzluk eden, kullanıcıların neden kaydolması gerektiği ve BT yöneticilerinin kayıtlı cihazlarda neleri görebileceği ve göremeyeceği hakkında daha fazla bilgi veren yeni ekranlar eklenmiştir. Ayrıntılar için, [kayıt yönergelerine](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc) bakın.
- Kayıt hata iletileri artık Şirket Portalı uygulamasında görüntülenmektedir. Daha önce bu iletiler Şirket Portalı web sitesinde görüntüleniyordu. Bu değişikliğin yapılması tüm hata iletilerinin bundan böyle iki farklı yerde değil, tek bir yerde görüneceği anlamına gelmektedir.

#### iOS Şirket Portalı uygulaması
 - Kullanıcılara kayıt işleminde kılavuzluk eden, kullanıcıların neden kaydolması gerektiği ve BT yöneticilerinin kayıtlı cihazlarda neleri görebileceği ve göremeyeceği hakkında daha fazla bilgi veren yeni ekranlar eklenmiştir. Ayrıntılar için, [kayıt yönergelerine](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device) bakın.

 - Kayıt hata iletileri artık Şirket Portalı uygulamasında görüntülenmektedir. Daha önce bu iletiler Şirket Portalı web sitesinde görüntüleniyordu. Bu değişikliğin yapılması tüm hata iletilerinin bundan böyle iki farklı yerde değil, tek bir yerde görüneceği anlamına gelmektedir.


## Ocak 2016

### Windows 10 özelliklerinden yararlanın
* **Durum Kanıtlama Hizmeti ile koşullu erişim** Intune yöneticileri artık Intune Yönetici konsolunda Windows 10 Cihaz Durumu Kanıtlama durumunu görüntüleyebilir. Cihaz durumu kanıtlama, yöneticinin istemci bilgisayarlarda güvenilir BIOS, TPM ve önyükleme yazılımı yapılandırmaları olduğundan emin olmasına imkan tanır. Cihaz durumu kanıtlamayı desteklemek için istemci cihazların TPM 2 etkinken Windows 10 çalıştırıyor olması gerekir. Cihaz durumu kanıtlama aşağıdakilerin her biri için etkinleştirilmiş cihaz sayısını görüntüler:
    * Erken başlatılan kötü amaçlı yazılımdan koruma
    * BitLocker
    * Güvenli Önyükleme
    * Kod Bütünlüğü

    Cihaz durumu ayarı, toplanan veri noktaları ve durum kanıtlama rapor hakkında daha fazla bilgi için bkz. [Microsoft Intune için cihaz uyumluluk ilkelerine giriş](introduction-to-device-compliance-policies-in-microsoft-intune.md). [HAS hizmet ayrıntıları](https://msdn.microsoft.com/en-us/library/dn934876.aspx), hizmeti kapsamlı olarak açıklar.

* **Windows 10 İş için Passport İlkesi ve sertifika yönetimi** Intune ile, bir parola, akıllı kart ya da sanal akıllı kartı değiştirmek için Windows 10’da Active Directory’yi veya bir Azure Active Directory hesabını kullanan alternatif oturum açma yöntemi [İş İçin Microsoft Passport’u tümleştirebilirsiniz](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md). Passport oturum açmak için parola yerine kullanıcı hareketi kullanmanıza imkan tanır. Kullanıcı hareketi basit bir PIN, Windows Hello gibi bir biyometrik kimlik doğrulaması ya da parmak izi okuyucu gibi harici bir cihaz olabilir.

* **Belirli uygulamalar için VPN** VPN üzerinden şirket ağınıza otomatik olarak bağlanan uygulamaları seçebilirsiniz. VPN profilini ayarlarken, Kullanıcıların Microsoft Intune ile VPN profilleri kullanarak bağlanmasına yardımcı olun bölümünde anlatıldığı gibi uygulama listesi oluşturun.

* **Windows 10 Tam Silme desteği** Intune yönetici konsolu ile Intune’a kaydedilmiş Windows 10 masaüstü cihazlarına artık uzaktan tam silme uygulayabilirsiniz. Windows 10 tam silme, cihazı fabrika ayarlarına sıfırlar.


### Apple Toplu Satın Alma Programı (VPP) güncelleştirmesi
Intune bundan böyle [İş için Apple Toplu Satın Alma Programı (VPP) ile satın aldığınız uygulamaları yönetmenize](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md) yardımcı olabilir. Buna lisans bilgilerinin Apple ile Intune arasında eşitlenmesi ve her bir uygulamanın kaç tane kopyasını dağıttığınızı izlemeyi içerir.

### Şirkete ait cihazları tanımlamak için IMEI numaralarını kullanın
Bundan böyle şirkete ait mobil cihazları tanımlamaya yardımcı olmak üzere bir IMEI numarasına sahip mobil cihaz platformları için [uluslararası mobil donanım kimliği (IMEI) numaralarını](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) içeri aktarabilirsiniz. Intune’a kaydedildikten sonra, içeri aktarılan IMEI numaralarına sahip cihazlar kişiye ait cihazlara uygulananlardan farklı ilkeleri uygulamak için kullanılabilecek Şirket cihazları olarak etiketlenir.

### Intune MAM ilkeleriyle artık daha fazla uygulama uyumludur
Artık Microsoft iş ortaklarının daha fazla uygulaması Intune mobil uygulama yönetimi (MAM) ilkeleriyle uyumludur (Intune tarafından yönetilen cihazlar için):
* Box for EMM (Box Inc) – yalnızca iOS
* Adobe Reader (Adobe) – yalnızca Android
* Foxit PDF Reader (Foxit Corporation) – iOS ve Android


### IE9 desteği Ocak’ta sona erecektir
Internet Explorer 9, Şubat 2016 tarihinden itibaren Microsoft Intune şirket portalı web sitesine, Intune hesabı portalına ve Intune yönetim konsoluna erişim için resmi bir tarayıcı olarak desteklenmeyecektir. Internet Explorer 10 veya sonraki bir sürüme geçiş yapmanız gerekecektir.


>[!div class="step-by-step"]

>[&larr; **Intune’daki yenilikler**](whats-new-in-microsoft-intune.md)    



<!--HONumber=Jul16_HO3-->


