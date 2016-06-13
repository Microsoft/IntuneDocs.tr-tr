---
# required metadata

experiment_id: lindavr-abtest-20160527
title: Yenilikler | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune'daki yenilikler

## Mayıs 2016


TeamViewer tümleştirmesi dışında, bu özelliklerin tümü karma dağıtımlarda da (Intune ile Configuration Manager) desteklenir. Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler](https://technet.microsoft.com/en-us/library/mt718155.aspx) sayfasını gözden geçirin.

### Belgeler

[Docs.microsoft.com](https://docs.microsoft.com/en-us/intune)’un önizleme sürümüne hoş geldiniz!
Bu, siz müşterilerimizin Intune’u anlamasını ve kullanmasını kolaylaştırmak için tasarlanmış, tamamen yeni, modern bir içerik platformudur.
Tüm yeni özellikler hakkındaki bilgileri okumak için, bkz. [Docs.microsoft.com ile tanışın](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/)

### Intune hizmet durumu
Intune’un hizmet durumu bilgileri, diğer Microsoft hizmetleriyle birlikte merkezi bir konuma taşındı. Artık bu bilgileri [Office 365 yönetim portalında](https://portal.office.com/Admin/Default.aspx), **Hizmet Durumu**’nun altında bulabilirsiniz.
Daha fazla bilgi için [bu blog gönderisine](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/) bakın.


### Uygulama yönetimi

- **MAM SDK’sı: PIN uzunluğu yapılandırmasını destekler.** Cihaz PIN’ine benzer şekilde MAM uygulamalarının PIN’i için de uzuluğu belirtebileceksiniz. Bunun için son kullanıcıların sizin ayarladığınız yeni kısıtlamalara uyması gerekecektir. Daha uzun girişi kabul eden biraz değiştirilmiş bir PIN ekranı görecekler. Ayrıntılar için bkz. [Android için MAM ilkesi ayarları](/intune/deploy-use/android-mam-policy-settings) ve [iOS için MAM ilkesi ayarları](/intune/deploy-use/ios-mam-policy-settings).

- **iOS ve Android için Skype Kurumsal.** Artık [kayıt ilkeleri olmadan MAM](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) ile Skype Kurumsal’ı hedefleyebilirsiniz. Kullanıcılar oturum açtığında, MAM ilkeleri uygulanır.

- **MAM ilkeleriyle yönetim için yeni uygulamalar sağlanmıştır.** Android için Microsoft Word, Excel ve PowerPoint uygulamaları artık Intune’a kayıtlı olmayan cihazlarda MAM ilkeleriyle ilişkilendirilebilir. Desteklenen uygulamaların tam listesi için, [Microsoft Intune uygulama iş ortakları](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) sayfasında Microsoft Intune mobil uygulama galerisine gidin.

### Cihaz yönetimi

- **Windows bilgisayarları için uzaktan yardım oturumları.** Intune istemci yazılımıyla yönetilen Windows bilgisayarlarında TeamViewer tümleştirmesi, yardım masası bölümünüzü desteklemek için Windows bilgisayarlarıyla uzaktan yardım oturumları oluşturmanıza izin verir. Desteklenen bilgisayarlar Windows 7, 8, 8.1 ve Windows 10’dur.
Ayrıntılar için bkz. [Microsoft Intune bilgisayar istemcisiyle ortak Windows bilgisayarı yönetim görevleri](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#respond-to-a-remote-assistance-request)

### Şirket portalı güncelleştirmeleri

#### Android Şirket portalı uygulaması

- **Son kullanıcı bildirimleri**: Son kullanıcılar, cihazlarını Şirket Portalı’na kaydederken veya portaldan kaldırırken artık Android Şirket Portalı uygulamasından bildirimleri göreceklerdir.

- **Android Şirket Portalı uygulamasında Cihaz Kayıt Yöneticileri hesaplarında yapılan değişiklikler.** Performansı ve ölçeği artırmak için, Intune artık Android Şirket Portalı uygulamasının Cihazlarım bölmesinde Cihaz Kayıt Yöneticileri (DEM) cihazlarını göstermez. Yalnızca uygulamayı çalıştıran yerel cihaz, yalnızca Şirket Portalı uygulaması aracılığıyla kaydedilmişse görüntülenir. DEM kullanıcısı, yerel cihazda eylemler gerçekleştirebilir, ancak diğer kaydedilen cihazların uzaktan yönetimi yalnızca Intune yönetici konsolundan gerçekleştirilebilir.
-
#### Şirket Portalı web sitesi

**Şirket Portalı web sitesi: Cihaz kimliği başlığı son kullanıcılara daha fazla bilgi sağlayacaktır.** Son kullanıcılar artık Şirket Portalı web sitesini kullanırken seçmiş oldukları cihazı kolayca tanımlayabilirler. Yanlış cihaz seçiliyse, giriş sayfası başlığındaki **Buraya dokunun** bağlantısına dokunarak doğru cihazı seçebilecekler.


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

    **Yönetici** çalışma alanında **Bildirim Kuralları** > **Yeni Kural Oluştur**’a tıklayın.

    Bildirim Kuralı Oluşturma Sihirbazı’nın ikinci adımında, kuralın hedefleyeceği cihaz gruplarını seçin. Bu “cihaz gruplarını seçme” adımı, Intune Konsolu’ndan kaldırılıyor.

    Bu değişiklikle ilgili ilk zaman çizelgesi şöyledir:
    - Haziran 2016’da, yeni kiracılar Bildirim Kuralı Oluşturma Sihirbazı’nın ikinci adımını görmeyecekler. Mevcut kiracılar bundan etkilenmez.
    - Ağustos 2016’ya doğru, mevcut kiracılardan bazıları sihirbazda “cihaz gruplarını seçme” adımını görmeyecekler.
    - Ekim 2016’ya doğru, kiracılardan hiçbirinin sihirbazda “cihaz grupları seçme” adımını görmeyeceğini umuyoruz.


- **iOS Şirket Portalı uygulaması desteğindeki değişiklikler**. Önümüzdeki aylarda, iOS için Microsoft Intune Şirket Portalı uygulamasında yapılacak bir güncelleştirmeyle uygulamanın yalnızca iOS 8.0 veya üstünü çalıştıran cihazları desteklemesi sağlanacak. Kullanıcılar, iOS 8.0’ın altındaki sürümleri çalıştıran yeni cihazları kaydedemeyecekler. iOS 8.0’ın altındaki sürümleri çalıştıran kayıtlı cihazlar yönetilmeye devam edecek ve sınırlı bir süre için Şirket Portalı uygulamasını kullanmaya devam edebilecek. Ancak, Şirket Portalı uygulamasının en son sürümlerine erişmek için cihazlar iOS 8.0 veya üstünü çalıştırıyor olmalıdır. Yeni Intune özelliklerinden tam anlamıyla yararlanmaları için kullanıcılara iOS 8.0 veya üstüne güncelleştirmelerini bildirmenizi öneririz.



## Önceki Intune sürümleri
Son altı ay içinde Intune'da neler yayınlandığını görmek istiyorsanız, bunlar [Önceki Intune yayınları](previous-intune-releases.md) makalesinde listelenmektedir.
> [!div class="op_single_selector"]
- [Nisan 2016](previous-intune-releases.md)
- [Mart 2016](previous-intune-releases.md)
- [Şubat 2016](previous-intune-releases.md)
- [Ocak 2016](previous-intune-releases.md)
- [Aralık 2015](previous-intune-releases.md)
- [Kasım 2015](previous-intune-releases.md)




### Ayrıca bkz.
* [Microsoft Intune Blogu](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Bulut Platformu yol haritası](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)


<!--HONumber=Jun16_HO1-->


