---
# required metadata

title: Beklenenler | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 05/03/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

#ROBOTS:
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

Intune için aşağıdaki değişiklikler geliştirilme aşamasındadır. Bu özelliklerin tümü, karma müşteri dağıtımlarında da (Intune ile Configuration Manager) desteklenecektir. Yeni karma özellikler hakkında daha fazla bilgi için, [karma Yenilikler sayfamızı](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx) gözden geçirin..

## İleti Merkezi başlatılıyor
Intune’un [Office 365 Yönetim portalına](https://portal.office.com/) geçirilme sürecinin bir parçası olarak, yeni özellikleri haber vermek ve diğer bildirimleri yapmak için portalın İleti Merkezi’nden yararlanmaya başlayacağız.  Ayrıca, yardımcı Office 365 Yönetim mobil uygulamasını yükleyerek cep telefonunuzda bildirimleri alabilir ve iletileri kolayca kullanıcılara veya dağıtım listesi diğer adlarına iletebilirsiniz.<br>  
Mayıs sürümümüzde size güncelleştirmelerin ne zaman tamamlanacağını haber vermek için İleti Merkezi’ni kullanmaya başlayacağız; ayrıca yeni ve geliştirilmiş Intune özellikleriyle ilgili bilgi de ekleyeceğiz.  Bugün [Office 365 Yönetim portalında](https://portal.office.com/) oturum açarak ve sol gezinti bölmesindeki **İLETİ MERKEZİ** seçeneğini kullanarak İleti Merkezi’ni gözden geçirin.
<!---TFS 1242782--->


## Uygulama yönetimi
- **Tarayıcı için koşullu erişim.** Exchange Online ve SharePoint Online için, bunlara yalnızca yönetilen ve uyumlu iOS ve Android cihazları tarafından erişilebilmesini sağlayacak bir koşullu erişim ilkesi ayarlayabilirsiniz. iOS ve Android cihazlarıyla Outlook Web Access (OWA) ve SharePoint sitelerinde oturum açmayı deneyen son kullanıcılardan, oturum açma işlemini tamamlayabilmek için önce cihazlarını Intune’a kaydetmeleri ve tüm uyumsuzluk sorunlarını çözmeleri istenecektir.
<!---TFS 1175844--->

- **MAM SDK’sı: PIN uzunluğu yapılandırmasını destekler.** Cihaz PIN’ine benzer şekilde MAM uygulamalarının PIN’i için de uzuluğu belirtebileceksiniz. Bunun için son kullanıcıların sizin ayarladığınız yeni kısıtlamalara uyması gerekecektir. Daha uzun girişi kabul eden biraz değiştirilmiş bir PIN ekranı görecekler.
<!--- TFS 1104753--->

- **Outlook kişilerinin eşitlenmesini önlemek için MAM denetimleri (iOS).** Cihaz kaydı olmadan mobil uygulama yönetimi için yeni bir ayar vardır. Bu ayar Intune yöneticisinin, bir uygulamanın iOS cihazlarda kişileri yerel adres defterine eşitlemesini engellemesini sağlar. Bu ayar etkinleştirildiğinde, uygulama artık kişileri yerel adres defterine kaydedemeyecektir. Bu ayar devre dışı bırakıldığında, uygulama kişileri yerel adres defterine kaydedebilecektir. Intune yöneticisi bir cihazı seçmeli olarak temizlediğinde, yerel adres defterine zaten kaydedilmiş tüm kişiler kaldırılacaktır. Bu yeni ayar, artık iOS cihazlarda Outlook uygulaması tarafından desteklenmektedir.
<!---TFS item 1276166--->

- **Android için Skype Kurumsal.** Intune Yöneticileri artık kayıt ilkeleri olmadan MAM ile Skype Kurumsal’ı hedefleyebilir.  Kullanıcıları oturum açtığında, MAM ilkeleri uygulanacaktır.
<!--- TFS item 1248444 --->

- **iOS için Skype Kurumsal.** Intune Yöneticileri artık kayıt ilkeleri olmadan MAM ile Skype Kurumsal’ı hedefleyebilir.  Kullanıcıları oturum açtığında, MAM ilkeleri uygulanacaktır.
<!--- TFS item 1248443 --->

### Xamarin desteği
Microsoft Intune uygulama SDK'sı, artık şu senaryolarda Xamarin uygulamaları destekler:

- Yeni uygulamalar yazma veya Intune SDK’sını kullanarak mevcut iş kolu uygulamalarının kodunda değişiklik yapma. Eklentiyi [Microsoft Intune Github](https://github.com/msintuneappsdk) sayfasından alabilirsiniz.
- Intune uygulama kaydırma aracını kullanarak mevcut iş kolu uygulamalarına MAM desteği ekleme.

Hangi yöntemin kullanılacağını seçerken yardım almak için bkz. [Microsoft Intune ile uygulamaların mobil uygulama yönetimi için nasıl hazırlanacağına karar verme](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)..
<!--- TFS 1061478 & TFS 1152340--->


## Cihaz yönetimi
- **Windows bilgisayarları için uzaktan yardım oturumları.** Windows masaüstü aracısıyla yönetilen bilgisayarlarda TeamViewer tümleştirmesi, son kullanıcı yardım masası bölümlerini desteklemek üzere Windows masaüstü aracısıyla yönetilen bilgisayarlarla uzaktan yardım oturumları oluşturmanıza olanak tanıyacaktır. Bu, Windows 7, 8, 8.1 ve Windows 10’u içerir.
<!--- TFS 1284856--->


<!--- TFS item 1274326 --->

## Erişim denetimi
* **Skype Kurumsal Çevrimiçi, koşullu erişimi destekler.** Skype Kurumsal Çevrimiçi için, Intune yöneticileri buna yalnızca yönetilen ve uyumlu iOS ve Android cihazları tarafından erişilebilmesini sağlayacak bir koşullu erişim ilkesi ayarlayabilecekler. iOS ve Android’de Skype Kurumsal Çevrimiçi mobil uygulamasında oturum açmaya çalışan son kullanıcılardan, oturum açma işlemini tamamlanabilmek için Intune’a kaydolmaları ve tüm uyumsuzluk sorunlarını çözmeleri istenecektir.
<!---TFS item 1254499--->

## Şirket Portalı
* **Cihaz kimliği başlığı son kullanıcılara daha fazla bilgi sağlayacaktır.** Son kullanıcılar Şirket Portalı web sitesini kullanırken seçmiş oldukları cihazı kolayca tanımlayabilecekler. Yanlış cihaz seçiliyse, giriş sayfası başlığındaki “Buraya dokunun” bağlantısına dokunarak doğru cihazı seçebilecekler.
<!--- TFS 1231157--->

* **Windows uygulama paketleri doğrudan Şirket Portalı’ndan sağlanır**: Windows 8, Windows 8.1 ve Windows RT bilgisayarlarının kullanıcıları Windows uygulama paketlerini (.appx uzantılı) artık doğrudan Şirket Portalı web sitesinden yükleyebilir. Daha önce uygulamaları yüklemek için, Intune yöneticilerinin Şirket Portalı uygulamasını dağıtması veya kullanıcıların cihazlarına Şirket Portalı uygulamasını yüklemesi gerekiyordu.
<!--- TFS item 1082481 --->

* **Kullanıcılar cihazlarını uzaktan, Şirket Portalı’ndan kilitleyebilir** Kullanıcıların, cihazları kaybolduğunda veya çalındığında cihazlarını portalı kullanarak uzaktan kilitlemesine olanak sağlamak için Şirket Portalı web sitesine yeni bir uzaktan kilitleme seçeneği eklenmiştir. Aşağıdaki tabloda, Intune için ve Intune ile Configuration Manager için uzaktan kilitleme platform desteği listelenmektedir.
<!--- TFS item 1195661 --->

|Platform  |Destek ayrıntıları|
|---------|---------|
|iOS | Desteklenir|
|Android | Desteklenir|
|Windows Phone 8.1 | Desteklenir|
|Windows 10 Mobile | Yalnızca telefonda bir geçiş kodu ayarlanmışsa desteklenir|
|Bilgisayar (Windows 8.0 ve öncesi) | Desteklenmez|
|Bilgisayar (Windows 8.1) | Desteklenmez|
|Windows Phone 8.0 | Desteklenmez|
|Windows 10 Masaüstü | Desteklenmez|

## Hizmeti kullanımdan kaldırma
* **Bildirim Kurallarında Özel Grup Hedeflemenin Kaldırılması.** Haziran 2016’nın başlarında, bildirim kurallarında kullanıcı tarafından oluşturulan grupların hedeflenmesi için Bildirim Kuralı Oluşturma Sihirbazı’nı artık kullanamayacaksınız.

    Şu anda, Microsoft Intune yönetim konsolundan kullanıcı tarafından oluşturulan bir grubu hedeflemek için, **Yönetici** > **Bildirim Kuralları** > **Yeni Kural Oluştur**’u seçiyorsunuz. Bildirim Kuralı Oluşturma Sihirbazı’nın ikinci adımında, kuralın hedefleyeceği cihaz gruplarını seçmeniz gerekiyor. Bu adım (**Cihaz gruplarını seçin**), Intune Konsolu’ndan kaldırılıyor.

    Intune’un Haziran 2016 sürümünde artık **Cihaz gruplarını seçin** adımı desteklenmeyecektir. Bununla birlikte, Ağustos 2016’ya kadar bu seçeneği görmeye devam edeceksiniz. Ağustos’tan sonra, iki aylık bir süre içinde kiracılarımızı aşamalı olarak yeni deneyime geçirmeye başlayacağız. Ekim 2016’da, tüm mevcut müşterilerin yeni deneyime geçmiş olması gerekiyor. Yeni deneyime geçtikten sonra, artık bildirim kurallarında belirli bir grubu hedefleme seçeneğini görmeyeceksiniz.
<!---   TFS 1278864--->







### Ayrıca bkz.
Son geliştirmelerin ayrıntıları için bkz. [Microsoft Intune’daki Yenilikler](whats-new-in-microsoft-intune.md).


<!--HONumber=May16_HO1-->


