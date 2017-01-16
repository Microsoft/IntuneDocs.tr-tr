---
title: "Önceki sürümler | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: d951084a7f5730a9549f76c987fe80f4d98415cf


---

# <a name="previous-intune-releases"></a>Önceki Intune sürümleri

Bu sayfa, [Microsoft Intune'daki Yenilikler](whats-new-in-microsoft-intune.md) sayfasında yapılan son duyuruların bir listesidir.

[!INCLUDE[wit_nextref](../includes/whats-new-last-six-months.md)]

## <a name="may-2016"></a>Mayıs 2016
Bu özelliklerin tümü, karma dağıtımlar için de desteklenmektedir (Intune içeren Yapılandırma Yöneticisi). Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler](https://technet.microsoft.com/en-us/library/mt718155.aspx) sayfasını gözden geçirin.

### <a name="documentation"></a>Belgeler
[Docs.microsoft.com](https://docs.microsoft.com/en-us/intune)’un önizleme sürümüne hoş geldiniz!
Bu, siz müşterilerimizin Intune’u anlamasını ve kullanmasını kolaylaştırmak için tasarlanmış, tamamen yeni, modern bir içerik platformudur.
Tüm yeni özellikler hakkındaki bilgileri okumak için, bkz. [Docs.microsoft.com ile tanışın](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/)

### <a name="intune-service-health"></a>Intune hizmet durumu
Intune’un hizmet durumu bilgileri, diğer Microsoft hizmetleriyle birlikte merkezi bir konuma taşındı. Artık bu bilgileri [Office 365 yönetim portalında](https://portal.office.com/Admin/Default.aspx), **Hizmet Durumu**’nun altında bulabilirsiniz.
Daha fazla bilgi için [bu blog gönderisine](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/) bakın.

### <a name="app-management"></a>Uygulama yönetimi
- **MAM SDK’sı: PIN uzunluğu yapılandırmasını destekler.** Cihaz PIN’ine benzer şekilde MAM uygulamalarının PIN’i için de uzunluğu belirtebileceksiniz. Bunun için son kullanıcıların sizin ayarladığınız yeni kısıtlamalara uyması gerekecektir. Daha uzun girişi kabul eden biraz değiştirilmiş bir PIN ekranı görecekler. Ayrıntılar için bkz. [Android için MAM ilkesi ayarları](/intune/deploy-use/android-mam-policy-settings) ve [iOS için MAM ilkesi ayarları](/intune/deploy-use/ios-mam-policy-settings).

- **iOS ve Android için Skype Kurumsal.** Artık [kayıt ilkeleri olmadan MAM](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) ile Skype Kurumsal’ı hedefleyebilirsiniz. Kullanıcılar oturum açtığında, MAM ilkeleri uygulanır.

- **MAM ilkeleriyle yönetim için yeni uygulamalar sağlanmıştır.** Android için Microsoft Word, Excel ve PowerPoint uygulamaları artık Intune’a kayıtlı olmayan cihazlarda MAM ilkeleriyle ilişkilendirilebilir. Desteklenen uygulamaların tam listesi için, [Microsoft Intune uygulama iş ortakları](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) sayfasında Microsoft Intune mobil uygulama galerisine gidin.


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
Artık Azure Active Directory (AAD) kiracınızdaki herhangi bir kullanıcı için, uygulama yönetimi ilkelerinizin [durumunu](/intune/deploy-use/monitor-mobile-app-management-policies-with-Microsoft-Intune) görüntüleyebilirsiniz. Buna aşağıdakiler dahildir:
   - Cihazlar
   - Cihazdaki uygulamalar

   Durum değerleri:

   **İade**: İlkenin kullanıcıya dağıtıldığını ve uygulamanın iş bağlamında kullanıldığını ve ilkeyi başarıyla aldığını gösterir.

    **İade değil**: İlkenin kullanıcıya dağıtıldığını, ancak uygulamanın o zamandan bu yana iş bağlamında kullanılmadığını gösterir.


- **Outlook kişilerinin eşitlenmesini önlemek için MAM denetimleri (Android).**
Cihaz kaydı olmadan [mobil uygulama yönetimi](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) için yeni bir ayar vardır. Bu ayar, bir uygulamanın Android cihazlarda kişileri yerel adres defterine eşitlemesini engellemenizi sağlar. Bu ayar etkinleştirildiğinde, hedeflenen uygulamalar artık kişileri yerel adres defterine kaydedemeyecektir. Bu ayar devre dışı bırakıldığında, hedeflenen uygulamalar kişileri yerel adres defterine kaydedebilecektir. [Bir cihazı veya uygulamayı uzaktan temizlediğinizde](/intune/deploy-use/wipe-managed-company-app-data-with-Microsoft-Intune), yerel adres defterine zaten kaydedilmiş kişiler kaldırılacaktır. Bu yeni ayar başlangıçta Android cihazlarda Outlook uygulaması tarafından desteklenmektedir.

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



<!--HONumber=Dec16_HO2-->


