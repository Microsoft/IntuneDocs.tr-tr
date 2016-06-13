---
# required metadata

title: Beklenenler | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 05/17/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune’da beklenen özellikler
Bu bilgiler NDA kapsamında çok sınırlı bir temelde sağlanır ve değiştirilebilir. Burada listelenen özelliklerden bazılarının son tarihe yetişememe riski vardır ve gelecek sürüme ertelenebilir. Diğer özellikler, müşterinin kullanımına hazır olduğundan emin olmak için pilot (sürüyor) aşamasında test edilmektedir. Sorularınız veya kaygılarınız varsa lütfen Intune/PM arkadaşınıza ulaşın.

Bu sayfa düzenli aralıklarla güncelleştirilir. Beklenen yeni güncelleştirmeler için yeniden gelip gözden geçirin.

Intune için aşağıdaki değişiklikler geliştirilme aşamasındadır. Bu özelliklerin tümü, karma müşteri dağıtımlarında da (Intune ile Configuration Manager) desteklenecektir. Yeni karma özellikler hakkında daha fazla bilgi için, [karma Yenilikler sayfamızı](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx) gözden geçirin.

## Intune iletişimleri
- **Intune hizmet durumu bilgileri.** Intune’un hizmet durumu bilgileri, diğer Microsoft hizmetleriyle birlikte merkezi bir konuma taşındı. Artık bu bilgileri [Office 365 yönetim portalında](https://portal.office.com/Admin/Default.aspx), Hizmet Durumu’nun altında bulabilirsiniz. Daha fazla bilgi için [bu blog gönderisine](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/) bakın.

- **İleti merkezi kullanıcı arabirimi başlatılıyor.** Intune’un [Office 365 Yönetim portalına](https://portal.office.com/) geçirilme sürecinin bir parçası olarak, yeni özellikleri haber vermek ve diğer bildirimleri yapmak için portalın İleti Merkezi’nden yararlanmaya başlayacağız. Ayrıca, yardımcı Office 365 Yönetim mobil uygulamasını yükleyerek cep telefonunuzda bildirimleri alabilir ve iletileri kolayca kullanıcılara veya dağıtım listesi diğer adlarına iletebilirsiniz.
Mayıs sürümümüzde size güncelleştirmelerin ne zaman tamamlanacağını haber vermek için İleti Merkezi’ni kullanmaya başlayacağız; ayrıca yeni ve geliştirilmiş Intune özellikleriyle ilgili bilgi de ekleyeceğiz. Bugün [Office 365 Yönetim portalında](https://portal.office.com/) oturum açarak ve sol gezinti bölmesindeki **İleti Merkezi** seçeneğini kullanarak İleti Merkezi’ni gözden geçirin.

## Uygulama yönetimi
- **MAM ilkeleriyle yönetim için yeni uygulamalar sağlanmıştır.** Android için Microsoft Word, Excel ve PowerPoint uygulamaları artık Intune’a kayıtlı olmayan cihazlarda MAM ilkeleriyle ilişkilendirilebilir. Desteklenen uygulamaların tam listesi için, [Microsoft Intune uygulama iş ortakları sayfasında](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) Microsoft Intune mobil uygulama galerisine gidin.


- **Tarayıcı için koşullu erişim.** Exchange Online ve SharePoint Online için, bunlara yalnızca yönetilen ve uyumlu iOS ve Android cihazları tarafından erişilebilmesini sağlayacak bir koşullu erişim ilkesi ayarlayabilirsiniz. iOS ve Android cihazlarıyla Outlook Web Access (OWA) ve SharePoint sitelerinde oturum açmayı deneyen son kullanıcılardan, oturum açma işlemini tamamlayabilmek için önce cihazlarını Intune’a kaydetmeleri ve tüm uyumsuzluk sorunlarını çözmeleri istenecektir.
<!---TFS 1175844--->

- **MAM SDK’sı: PIN uzunluğu yapılandırmasını destekler.** Cihaz PIN’ine benzer şekilde MAM uygulamalarının PIN’i için de uzuluğu belirtebileceksiniz. Bunun için son kullanıcıların sizin ayarladığınız yeni kısıtlamalara uyması gerekecektir. Daha uzun girişi kabul eden biraz değiştirilmiş bir PIN ekranı görecekler.
<!--- TFS 1104753--->

- **Android için Skype Kurumsal.** Intune Yöneticileri artık kayıt ilkeleri olmadan MAM ile Skype Kurumsal’ı hedefleyebilir.  Kullanıcıları oturum açtığında, MAM ilkeleri uygulanacaktır.
<!--- TFS item 1248444 --->

- **iOS için Skype Kurumsal.** Intune Yöneticileri artık kayıt ilkeleri olmadan MAM ile Skype Kurumsal’ı hedefleyebilir.  Kullanıcıları oturum açtığında, MAM ilkeleri uygulanacaktır.
<!--- TFS item 1248443 --->

### Xamarin desteği
Microsoft Intune uygulama SDK'sı, artık şu senaryolarda Xamarin uygulamaları destekler:

- Yeni uygulamalar yazma veya Intune SDK’sını kullanarak mevcut iş kolu uygulamalarının kodunda değişiklik yapma. Eklentiyi [Microsoft Intune Github](https://github.com/msintuneappsdk) sayfasından alabilirsiniz.
- Intune uygulama kaydırma aracını kullanarak mevcut iş kolu uygulamalarına MAM desteği ekleme.

Hangi yöntemin kullanılacağını seçerken yardım almak için bkz. [Microsoft Intune ile uygulamaların mobil uygulama yönetimi için nasıl hazırlanacağına karar verme](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune).
<!--- TFS 1061478 & TFS 1152340--->


## Cihaz yönetimi
- **Windows bilgisayarları için uzaktan yardım oturumları.** Windows masaüstü aracısıyla yönetilen bilgisayarlarda TeamViewer tümleştirmesi, son kullanıcı yardım masası bölümlerini desteklemek üzere Windows masaüstü aracısıyla yönetilen bilgisayarlarla uzaktan yardım oturumları oluşturmanıza olanak tanıyacaktır. Bu, Windows 7, 8, 8.1 ve Windows 10’u içerir.
<!--- TFS 1284856--->



## Şirket Portalı

- **Son kullanıcı bildirimleri.** Son kullanıcılar, cihazlarını Şirket Portalı’na kaydederken veya portaldan kaldırırken artık Android Şirket Portalı uygulamasından bildirimleri göreceklerdir.
- **Cihaz kimliği başlığı son kullanıcılara daha fazla bilgi sağlayacaktır.** Son kullanıcılar Şirket Portalı web sitesini kullanırken seçmiş oldukları cihazı kolayca tanımlayabilecekler. Yanlış cihaz seçiliyse, giriş sayfası başlığındaki “Buraya dokunun” bağlantısına dokunarak doğru cihazı seçebilecekler.
<!--- TFS 1231157--->

- **Android Şirket Portalı uygulamasında Cihaz Kayıt Yöneticileri hesaplarında yapılan değişiklikler.** Performansı ve ölçeği artırmak için, Intune artık Android Şirket Portalı uygulamasının **Cihazlarım** bölmesinde Cihaz Kayıt Yöneticileri (DEM) cihazlarını göstermeyecektir. Yalnızca uygulamayı çalıştıran yerel cihaz, yalnızca Şirket Portalı uygulaması aracılığıyla kaydedilmişse gösterilir. DEM kullanıcısı, yerel cihazda eylemler gerçekleştirebilir, ancak diğer kaydedilen cihazların uzaktan yönetimi yalnızca Intune yönetici konsolundan gerçekleştirilebilir.

- **iOS Şirket Portalı uygulamasında Cihaz Kayıt Yöneticileri hesaplarında yapılan değişiklikler.** Performansı ve ölçeği artırmak için, Intune artık iOS Şirket Portalı uygulamasının Cihazlarım bölmesinde tüm Cihaz Kayıt Yöneticileri (DEM) cihazlarını göstermez. Yalnızca uygulamayı çalıştıran yerel cihaz, yalnızca Şirket Portalı uygulaması aracılığıyla kaydedilmişse görüntülenir. DEM kullanıcısı, yerel cihazda eylemler gerçekleştirebilir, ancak diğer kaydedilen cihazların uzaktan yönetimi yalnızca Intune yönetici konsolundan gerçekleştirilebilir.  Ayrıca, Intune, Apple Cihaz Kayıt Programı veya Apple Configurator aracıyla DEM hesaplarını kullanımdan kaldırmaktadır. Her iki kayıt yöntemi, paylaşılan iOS cihazları için kullanıcısız kaydı zaten desteklemektedir.  Yalnızca, paylaşılan cihazlar için kullanıcısız kayıt kullanılamadığında DEM hesapları kullanın.



## Hizmeti kullanımdan kaldırma
**Bildirim Kurallarında Özel Grup Hedeflemenin Kaldırılması.**
Intune bildirim kuralları, Intune’dan kime e-posta uyarısı gönderileceğini tanımlar. Şu anda, oluşturduğunuz bir Intune cihaz grubundaki cihazların tüm kullanıcılarına e-posta göndermek için bildirim kuralları yapılandırabilirsiniz. Yaklaşık 1 Haziran 2016’dan başlayarak, kullanıcı tarafından oluşturulan grupları hedeflemek artık desteklenmeyecektir.

Bugün, bir bildirim kuralıyla Microsoft Intune yönetim konsolundan oluşturduğunuz bir grubu hedeflemek için aşağıdaki adımları izleyebilirsiniz:

**Yönetici** çalışma alanında **Bildirim Kuralları** > **Yeni Kural Oluştur**’a tıklayın.

Bildirim Kuralı Oluşturma Sihirbazı’nın ikinci adımında, kuralın hedefleyeceği cihaz gruplarını seçin. Bu “cihaz gruplarını seçme” adımı, Intune Konsolu’ndan kaldırılıyor.

Bu değişiklikle ilgili ilk zaman çizelgesi şöyledir:
- Haziran 2016’da, yeni kiracılar Bildirim Kuralı Oluşturma Sihirbazı’nın ikinci adımını görmeyecekler. Mevcut kiracılar bundan etkilenmez.
- Ağustos 2016’ya doğru, mevcut kiracılardan bazıları sihirbazda “cihaz gruplarını seçme” adımını görmeyecekler.
- Ekim 2016’ya doğru, kiracılardan hiçbirinin sihirbazda “cihaz gruplarını seçme” adımını görmeyeceğini umuyoruz.

<!---   TFS 1278864--->
**iOS Şirket Portalı uygulaması desteğindeki değişiklikler.**
Önümüzdeki aylarda, iOS için Microsoft Intune Şirket Portalı uygulamasında yapılacak bir güncelleştirmeyle uygulamanın yalnızca iOS 8.0 veya üstünü çalıştıran cihazları desteklemesi sağlanacak. Kullanıcılar, iOS 8.0’ın altındaki sürümleri çalıştıran yeni cihazları kaydedemeyecekler. iOS 8.0’ın altındaki sürümleri çalıştıran kayıtlı cihazlar yönetilmeye devam edecek ve sınırlı bir süre için Şirket Portalı uygulamasını kullanmaya devam edebilecek. Ancak, Şirket Portalı uygulamasının en son sürümlerine erişmek için cihazlar iOS 8.0 veya üstünü çalıştırıyor olmalıdır. Yeni Intune özelliklerinden tam anlamıyla yararlanmaları için kullanıcılara iOS 8.0 veya üstüne güncelleştirmelerini bildirmenizi öneririz.  

- **Intune Görüntüleyicisi uygulamaları.** Yeni RMS paylaşım uygulamasının kullanıma sunulmasıyla, Ağustos 2016’dan başlayarak aşağıdaki Intune Görüntüleyicisi uygulamalarını kaldırıyoruz:
    - Intune AV Görüntüleyicisi
    - Intune PDF Görüntüleyicisi
    - Google Play’den Android için Intune Resim Görüntüleyicisi

  Intune Görüntüleyicisi uygulamalarını kullanmak yerine, Android cihazlarda şirket dosyalarını güvenle görüntülemek için üç ayrı uygulama yerine tek bir uygulama dağıtmanıza olanak tanıyan yeni Android için Hak Yönetimi uygulamasını (RMS paylaşımı) kullanmanızı öneririz. RMS paylaşım uygulaması hakkında daha fazla bilgi edinin (belgelerin bağlantılarıyla).






### Ayrıca bkz.
Son geliştirmelerin ayrıntıları için bkz. [Microsoft Intune’daki Yenilikler](whats-new-in-microsoft-intune.md).


<!--HONumber=May16_HO5-->


