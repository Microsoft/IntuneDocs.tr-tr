---
title: Yenilikler | Microsoft Intune
description: "Bu ayki ve geçmişteki Microsoft Intune sunumlarındaki yenilikleri öğrenin"
keywords: 
author: Lindavr
manager: angrobe
ms.date: 08/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0d70a46d9c13aad1bc0a940836d83a99b93bb95e
ms.openlocfilehash: a753ecfa08adcd27049c70889c50e10618ecddba


---

# Microsoft Intune'daki yenilikler
Microsoft Intune’un bu sürümündeki yenilikleri öğrenin. Planlama yapmanız gereken yaklaşan değişiklikler hakkında ve geçmiş sunumlar hakkında bilgiler de alabilirsiniz.

Bu özelliklerin tümü, sonunda karma müşteri dağıtımlarında (Intune ile Configuration Manager) desteklenecektir. Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler sayfamızı](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx) gözden geçirin.
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

## Ağustos 2016
## Uygulama yönetimi
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

### iOS 9.3 için gizli ve gösterilen uygulamalar
iOS 9.3 veya üzerini çalıştıran denetimli cihazlarda iOS genel yapılandırma ilkesindeki gizli ve gösterilen uygulamalar listesini kullanarak şunları yapabilirsiniz:
- Kullanıcılardan gizlenecek uygulamaların bir listesini belirtin. Kullanıcılar bu uygulamaları görüntüleyemez veya başlatamaz.
- Kullanıcıların görüntüleyebileceği ve başlatabileceği uygulamaların bir listesini belirtin. Başka hiçbir uygulama görüntülenemez veya başlatılamaz.

Belirtebileceğiniz uygulamalara hem sizin dağıttığınız uygulamalar hem de Mesajlar ve Notlar gibi yerleşik iOS uygulamaları dahildir. Ayrıntılar için bkz. [Microsoft Intune’da iOS ilke ayarları]( https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune).
<!---TFS 1279009 checked--->
### Samsung KNOX cihazlar için izin verilen ve engellenen uygulamalar ilkesi
Artık Samsung KNOX cihazlar için aşağıdakilerden birini oluşturmanıza imkan tanıyan özel bir ilke yapılandırabilirsiniz:
- Cihazda çalışması engellenmiş uygulamaların listesi. Engellenenler listesinde tanımlanan bir uygulama cihazda yüklü olsa bile etkinleştirilemez.
- Cihaz kullanıcılarının Google Play mağazasından yüklemesine izin verilen uygulamaların listesi. Mağazadan başka hiçbir uygulama yüklenemez.

Bu ayarlar yalnızca Samsung KNOX çalıştıran cihazlar tarafından kullanılabilir.
Ayrıntılar için bkz. [Özel ilkeler kullanarak Samsung KNOX cihazları için uygulamalara izin verme veya bunları engelleme]( custom-policy-to-allow-and-block-samsung-knox-apps.md).
<!---TFS 1311629 checked --->
### Mobil uygulama yönetimi (MAM) ilkeleriyle uyumlu yeni uygulamalar
[iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) ve [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) için Yammer uygulaması, artık cihazın kayıtlı olup olmadığından bağımsız olarak [Intune mobil uygulama yönetimi (MAM) ilkeleri](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) ile uyumludur.

MAM ile uyumlu uygulamaların tam listesi için [Microsoft Intune uygulama iş ortakları](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) sitesine bakın.
<!--- TFS 1252335 & 1252336 checked--->


<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

### Intune Görüntüleyicisi uygulamaları
Yeni RMS paylaşım uygulamasının kullanıma sunulmasıyla, Ağustos 2016’dan başlayarak aşağıdaki Intune Görüntüleyicisi uygulamalarını kaldırıyoruz:
- Intune AV Görüntüleyicisi
- Intune PDF Görüntüleyicisi
- Google Play’den Android için Intune Resim Görüntüleyicisi

Intune Görüntüleyicisi uygulamalarını kullanmak yerine, Android cihazlarda şirket dosyalarını güvenle görüntülemek için üç ayrı uygulama yerine tek bir uygulama dağıtmanıza olanak tanıyan yeni [Android için Hak Yönetimi uygulamasını (RMS paylaşımı)](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app) kullanmanızı öneririz. Intune görüntüleyicisi uygulamasının desteği sona erdiğinde, bu uygulama Google Store’dan kaldırılacak ve gelecekte kullanıma sunulmayacaktır.

## Cihaz yönetimi
### Android 7.0 desteği
Intune, mobil cihazlar için yeni çıkacak Android 7.0 işletim sistemine yönelik olarak "0. gün" desteği sağlar.
<!---TFS 1262053--->
### Android 7.0 cihazlarda uzaktan geçiş kodu sıfırlama özelliğinin Google tarafından kaldırılması
Google, BT yöneticileri ve son kullanıcıların Android 7.0 cihazların parolasını uzaktan sıfırlama olanağını sona erdiriyor. Daha önce BT yöneticileri bir kullanıcının geçiş kodunu uzaktan sıfırlayabiliyor ve son kullanıcılar Şirket Portalı web sitesinden kendi parolalarını sıfırlayabiliyordu.



## Şirket portalı güncelleştirmeleri
### Şirket Portalı web sitesi
- **Şirket Portalı’ndan Microsoft’a geri bildirim bağlantısı** <br/>
Şirket portalı web sitesi, son kullanıcıların sayfanın en altındaki yeni “Geri Bildirim” bağlantısına dokunarak siteyle ilgili deneyimlerini Microsoft’a göndermesine olanak tanır. Toplanan anonim geri bildirimler, Microsoft’un kullanıcılar için Şirket Portalı web sitesi deneyimini geliştirmesine yardımcı olacak.
<!--- TFS 1313657 checked--->

### iOS
- **En düşük iOS Managed Browser sürümü 8.0 olarak güncelleştirildi**<br/>
iOS için Microsoft Intune Managed Browser uygulaması, iOS 8.0 veya üstünü çalıştıran cihazları destekleyecek şekilde güncelleştirilmiştir. iOS 7.1 cihazları mevcut Managed Browser uygulamasını kullanmaya devam edebilirler, ama yeni Managed Browser özelliklerine erişebilmeleri ve bu özelliklerden tam olarak yararlanabilmeleri için kullanıcılarınızı iOS 8.0 veya üstüne güncelleştirmeye teşvik edin.  
<!---TFS 1313253 checked--->

## Yakında
### Eylül 2016’dan itibaren Intune Grupları Azure Active Directory Grupları’na geçiyor
Intune, Intune’daki kullanıcı ve cihaz grupları olarak Azure Active Directory (AAD) güvenlik gruplarının kullanıldığı yeni bir grup yönetim deneyimi oluşturmaktadır. Bu gruplar **yeni Azure tabanlı Intune yönetici portalını kullanıma aldığımızda** tüm grup yönetimi, ilke yönetimi ve profil yönetimi için kullanılacaktır.

Bu yeni deneyim hizmetler arasında yinelenen gruplarınızın olmasını engelleyecek, **yeni bazı Azure Active Directory Premium (AADP) grup özelliklerine erişmenizi sağlayacak**, ayrıca PowerShell ve Graph kullanılarak kapsamı genişletme olanağı sağlayacaktır. Bu deneyim, kurumsal mobil kullanım yönetimi genelinde grup yönetimi deneyimini de birleştirecektir.

Güvenlik Gruplarına geçiş yapabilmek için, **geçerli yönetici konsolunda** bazı değişiklikler yapılacaktır. **Bu değişiklikler ve AAD güvenlik gruplarının kullanımı, Intune belgelerine kaydedilecektir**.

Intune’u yeni kullanmaya başlayan müşteriler, **güvenlik grubu değişikliklerinden bazılarını geçerli kiracılardan önce göreceklerdir**.

Grup yönetimindeki değişikliklere ek olarak, **aşağıdaki işlevler de kullanım dışı kalacaktır**:
- Yeni grup oluşturulurken üyeleri ve grupları dışlama
- **Gruplanmamış Kullanıcılar** ve **Gruplanmamış Cihazlar** grupları
- Hizmet Yöneticisi rolündeki **Grupları Yönet** işlevi
- Bildirim Kuralları için özel grup tabanlı uyarılar
- Raporlarda gruplarla özetleme
<!--- TFS 1295329--->

### Android için Şirket Portalı’na eklenen 'Bildirimler'
Eylül’de kullanıma sunacağımız güncelleştirmeyle Android için Şirket Portalı’nda giriş sayfasına yeni **Bildirimler** simgesi eklenecektir. Bu simgeye dokunulduğunda **Bildirimler** sayfasına erişim sağlanacak, bu sayfada son kullanıcınıza Şirket Portalı uygulamasında dikkat edilmesi gereken cihaz uyumsuzluğu, kayıt güncelleştirmesi ve kayıt etkinleştirmesi gibi tüm öğeler gösterilecektir. iOS Şirket Portalı uygulamasını da kullanıyorsanız, bildirimler deneyimini zaten görmüş olacaksınız. **Bildirimler** sayfası eklendikten sonra, cihazın önceden kaydedilmiş olması koşuluyla Android için Şirket Portalı’nı her başlattığınızda veya sürdürdüğünüzde **Şirket Erişim Kurulumu** sayfasını görmeyeceksiniz. Birçoğunuzun son kullanıcı kılavuzları oluşturduğunu ve kılavuzunuzun/ekran görüntülerinizin güncelleştirilmesi gerektiğinde önceden size bildirilmesini istediğinizi duyuyoruz. Lütfen deneyimdeki yaklaşan değişiklikleri yansıtacak şekilde belgelerinizi güncelleştirin. Güncelleştirilmiş ekran görüntülerini şu adreste bulabilirsiniz: https://aka.ms/androidcpupdate.  

### iOS son kullanıcılarının uygulamalarını edinme şekillerine yönelik geliştirmeler
Kullanıcıları tüm uygulamalarda tek konuma, yani Şirket Portalı web sitesine yönlendirmek üzere iOS için Şirket Portalı uygulamasındaki uygulama kutucuklarında Eylül ayında aşağıdaki değişiklikler yapılmıştır. Apple kısıtlamaları şu anda iş kolu uygulamalarının ve yönetilen uygulama mağazası uygulamalarının Şirket Portalı uygulamasında listelenmesini yasakladığından kullanıcıların tüm uygulamalarını bulabilmek için farklı görünümleri ziyaret etmesi gerekir.

- **Şirket Uygulamaları** kutucuğu şu anda Şirket Portalı web sitesinin TÜMÜ sekmesindeki tüm uygulamaların bir listesine yönlendirmektedir ve bu şekilde çalışmaya devam edecektir. Kutucuk adı **Tüm Uygulamalar** olarak değişecektir.
- **Diğer Uygulamalar** kutucuğu şu anda, Şirket Portalı uygulamasında bulunan ve Apple’ın Şirket Portalı uygulamasının göstermesine izin verdiği tüm uygulamaları listeleyen görünüme yönlendirmektedir. Kutucuk adı **Öne Çıkan Uygulamalar** olarak değişecek ve kutucuğa dokunan kullanıcıları Şirket Portalı web sitesinin ÖNE ÇIKANLAR sekmesine götürecektir.
-  **Kategoriler** kutucuğu şu anda, Şirket Portalı uygulaması içinde bulunan ve uygulama kategorilerini listeleyen görünüme yönlendirir. Kutucuk adı değişmeyecek, ancak artık Şirket Portalı web sitesinin KATEGORİLER sekmesine yönlendirecektir. Güncelleştirilmiş ekran görüntülerini [burada](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186) bulabilirsiniz.
<!---TFS 1317133--->

### Bulut yol haritası
[Bulut Platformu yol haritası](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune) ile yaklaşan Intune geliştirmelerinden haberdar olun.

### Hizmeti kullanımdan kaldırma
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **iOS Şirket Portalı uygulaması desteğindeki değişiklikler**<br/>
Eylül ayında, iOS için Microsoft Intune Şirket Portalı uygulamasını kullanan tüm kullanıcılarının en son sürümü kullanmaları gerekecektir. Yeni kullanıcılar yalnızca en son sürümünü indirebilecektir ve geçerli kullanıcıların buna güncelleştirme yapmaları gerekecektir. En son sürüm iOS 8.0 veya üzerini gerektirir ve bu yüzden daha önceki iOS sürümlerini çalıştıran cihazlar iOS 8.0 veya üzeri sürüme güncelleştirilene ve sonra Şirket Portalı uygulaması en son sürüme güncelleştirilene kadar Şirket Portalı’nı kullanamayacak veya ona kaydolamayacaktır. iOS 8.0 öncesi sürümleri çalıştıran kayıtlı cihazların Intune Yönetici Konsolu’nda yönetilmesi ve listelenmesi devam edecektir.  

- **En düşük iOS Managed Browser sürümü 8.0 olarak güncelleştirildi**<br/>
Ağustos’ta, Intune yalnızca iOS 8.0 veya üstünü çalıştıran cihazları destekleyecek, güncelleştirilmiş iOS için Microsoft Intune Managed Browser uygulamasını kullanıma sunacaktır. iOS 7.1 cihazları mevcut Managed Browser uygulamasını kullanmaya devam edebilirler, ama yeni Managed Browser özelliklerine erişebilmeleri ve bu özelliklerden tam olarak yararlanabilmeleri için lütfen kullanıcılarınızı iOS 8.0 veya üstüne güncelleştirmeye teşvik edin.  
<!---TFS 1313253--->

- **Windows 8 ve Windows Phone 8 için Şirket Portalı uygulamaları Eylül 2016’dan itibaren kullanımdan kalkacaktır** <br/>
Microsoft Intune Eylül 2016'dan itibaren Windows Phone 8 ve Windows 8 platformları için Microsoft Intune Şirket Portalı uygulamalarına yönelik desteği sonlandıracaktır. Cihazları Windows 8.1 ve Windows Phone 8.1’e güncelleştirin ve bu cihazlara uygulama dağıtmaya devam etmek için ilgili Windows 8.1 ve Windows Phone 8.1 Şirket Portalı uygulamalarını kullanın.
<!---TFS 1255391--->

<!--- - **Custom Group Targeting of Notification Rules Removal.**<br/>
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

    Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

    In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

    In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

    The preliminary timeline for this change is as follows:
    - In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
    - Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
    - Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

--->



## Önceki Intune sürümleri
Son altı ay içinde Intune'da neler yayınlandığını görmek istiyorsanız, bunlar [Önceki Intune yayınları](previous-intune-releases.md) makalesinde listelenmektedir.

### Ayrıca bkz.
* [Microsoft Intune Blogu](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Bulut Platformu yol haritası](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)



<!--HONumber=Aug16_HO4-->


