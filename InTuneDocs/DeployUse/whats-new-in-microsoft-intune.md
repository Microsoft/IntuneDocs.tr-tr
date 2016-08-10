---
title: Yenilikler | Microsoft Intune
description: "Bu ayki ve geçmişteki Microsoft Intune sunumlarındaki yenilikleri öğrenin"
keywords: 
author: Lindavr
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b93c6fe16e598c6f4b0d87981de8655f3de9c8d3
ms.openlocfilehash: 051f2994c59b2886a81a50d7c72f51627064bc6a


---

# Microsoft Intune'daki yenilikler
Microsoft Intune’un bu sürümündeki yenilikleri öğrenin. Planlama yapmanız gereken yaklaşan değişiklikler hakkında ve geçmiş sunumlar hakkında bilgiler de alabilirsiniz.

Bu özelliklerin tümü, sonunda karma müşteri dağıtımlarında (Intune ile Configuration Manager) desteklenecektir. Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler sayfamızı](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx) gözden geçirin.

## Ağustos 2016
## Şirket portalı güncelleştirmeleri

### Android
- **Android Şirket Portalı uygulaması**<br/>
Android için Intune Şirket Portalı uygulaması, mobil cihazlar için yeni çıkacak Android 7.0 işletim sistemine yönelik "0. gün" desteği sağlar.  

- **Android 7.0 cihazlarda uzaktan geçiş kodu sıfırlama özelliğinin Google tarafından kaldırılması**<br/>
Android 7.0 cihazlarda uzaktan parola sıfırlama özelliği Google tarafından kaldırıldığından, Intune BT yöneticileri ve son kullanıcılar Android 7.0 cihazlarda parolayı sıfırlayamaz. Android 7.0 öncesi sürümlerde, BT yöneticileri bir kullanıcının parolasını uzaktan sıfırlamaya; son kullanıcılar da parolalarını Şirket Portalı web sitesinden sıfırlamaya devam edebilecek.

## Temmuz 2016
## Uygulama yönetimi
### Uygulama sağlama profili güncelleştirme deneyimini geliştirme
Apple iOS iş kolu mobil uygulamaları, eklenen ve sertifika kullanılarak kodla imzalanan bir sağlama profiliyle oluşturulur. Uygulama iOS cihazında çalıştırıldığında, iOS uygulamanın bütünlüğünü onaylar ve sağlama profiliyle tanımlanan ilkeleri zorunlu tutar.

Uygulamaları imzalamak için kullandığınız kurumsal imzalama sertifikasının süresi normalde 3 yıldır. Öte yandan, 1 yıl sonra sağlama profilinin süresi dolar. Bu güncelleştirmeyle Intune size, sertifikası hala geçerli olduğu halde süresi dolmak üzere olan uygulamaların bulunduğu cihazlara, yeni sağlama profili ilkesini önceden dağıtmak için araçlar getirir. Daha fazla bilgi için bkz. [İş kolu uygulamalarınızın güncel kalmasını sağlamak için iOS mobil sağlama profili ilkelerini kullanma](/intune/deploy-use/ios-mobile-app-provisioning-profiles).
<!--- TFS 1280247--->
### Intune uygulamaları için Xamarin SDK sağlanır
Intune Uygulaması SDK Xamarin bileşeni, Xamarin ile oluşturulan mobil iOS ve Android uygulamalarınızda Intune mobil uygulama yönetimi özelliklerini etkinleştirmenize olanak tanır. Bileşeni [Xamarin mağazasında](https://components.xamarin.com/view/Microsoft.Intune.MAM) veya [Microsoft Intune Github sayfasında](https://github.com/msintuneappsdk) bulabilirsiniz.
<!--- TFS 1061478 --->

## Cihaz yönetimi
### Cihaz kayıt sınırlarında artış
Intune, yapılandırılabilir cihaz kayıt sayısı üst sınırını kullanıcı başına 5 cihazdan 15 cihaza çıkardı.
<!---TFS 1289896 --->

### Intune istemci yazılımını çalıştıran Windows bilgisayarları için TeamViewer Tümleştirmesi
Intune istemcisini çalıştıran Windows bilgisayarlarında [TeamViewer](https://www.teamviewer.com) tümleştirmesi, son kullanıcı yardım masası departmanlarını desteklemek için Windows bilgisayarlarıyla uzaktan yardım oturumları oluşturmanıza imkan tanır. Bu, Windows 7, 8, 8.1 ve Windows 10’u içerir. Ayrıntılar için bkz. [Microsoft Intune bilgisayar istemcisiyle ortak Windows bilgisayarı yönetim görevleri](intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

## Şirket portalı güncelleştirmeleri
### Şirket Portalı web sitesi
- **Windows cihazlarını kaydetme işleminde geliştirilmiş son kullanıcı deneyimi**<br/>
Koşullu erişim kullanırken, Şirket Portalı web sitesindeki Windows 8.1, Windows 10 Masaüstü ve Windows 10 Mobile için kayıt adımları netleştirilmiştir. Kullanıcılara artık birbirinden ayrı “Cihaz kaydı” ve “Workplace Join” adımları gösterilir. Böylelikle cihazlarının durumunu daha kolay görebilir ve Workplace Join (WPJ) hatasıyla karşılaşırlarsa işlemi tamamlayabilirler. Ayrı adımların, BT yöneticileri için sorun giderme işlemini de basitleştirmesi beklenmektedir. Daha önce, son kullanıcılar cihazı kaydetmeyi denerken WPJ dışındaki tüm kayıt adımları başarılı olduğunda, kaydedilen cihaz kullanıcıların belirleyebilmesi için cihaz listesinde gösterilmeyebiliyor ve kullanıcılarda kafa karışıklığına neden oluyordu.

### Android
- **Android Şirket Portalı uygulaması**<br/>
Android son kullanıcıları cihazlarında gerekli bir sertifikanın eksik olduğunu bildiren bir hata iletisi görürlerse, eksik sertifikayı yükleme [adımlarına](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) ulaşmak için “Bu nasıl çözülür” düğmesine dokunabilirler. Kullanıcılar adımları tamamladıkları halde bir “eksik sertifika” hata iletisi daha görürlerse, BT yöneticilerine başvurmaları ve bu [bağlantıyı](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues) sağlamaları istenir. Bu bağlantı, BT yöneticilerinin sertifika sorununu çözmek için kullanabilecekleri adımları içerir.

- **Dışarıdan uygulama yüklemelerini kayıtlı cihazlarla kısıtlama**<br/>
Android için Intune Şirket Portalı uygulaması kullanılarak Intune’a kaydedilmeyen Android cihazları, artık Şirket Portalı web sitesi üzerinden uygulama yükleyemezler.
<!---TFS 1299082--->

### iOS
- **iOS Şirket Portalı uygulamasında Cihaz Kayıt Yöneticileri hesaplarında yapılan değişiklikler**<br/>
Performansı ve ölçeği artırmak için, Intune artık iOS Şirket Portalı uygulamasının **Cihazlarım** bölmesinde Cihaz Kayıt Yöneticileri (DEM) cihazlarını görüntülemez. Yalnızca uygulamayı çalıştıran yerel cihaz, yalnızca Şirket Portalı uygulaması aracılığıyla kaydedilmişse görüntülenir.

    DEM kullanıcısı, yerel cihazda eylemler gerçekleştirebilir, ancak diğer kaydedilen cihazların uzaktan yönetimi yalnızca Intune yönetici konsolundan gerçekleştirilebilir. Ayrıca Intune, Apple Cihaz Kayıt Programı veya Apple Configurator aracıyla DEM hesaplarını kullanımdan kaldırmaktadır. Her iki kayıt yöntemi, paylaşılan iOS cihazları için kullanıcısız kaydı zaten desteklemektedir.

    Yalnızca, paylaşılan cihazlar için kullanıcısız kayıt kullanılamadığında DEM hesapları kullanın. Daha fazla bilgi için bkz. [Şirket ait cihazları Microsoft Intune'da Cihaz Kayıt Yöneticisi ile kaydetme](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

## Windows özelliklerinde ad değişiklikleri
- [Windows için Microsoft Passport](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) artık **İş için Windows Hello** olarak adlandırılıyor.
- [Kurumsal veri koruma](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) artık **Windows Bilgi Koruması** olarak adlandırılıyor.

## Yakında
### Ağustos 2016’nın başında Intune Grupları Azure Active Directory Grupları’na geçiyor
Intune, Azure Active Directory (AAD) güvenlik gruplarının kullanıldığı yeni bir grup yönetim deneyimi oluşturmaktadır. Bu Azure AD tabanlı güvenlik grupları hem kullanıcıları hem de cihazları içerebilir ve yeni Azure tabanlı Intune yönetici portalını kullanıma aldığımızda tüm grup yönetimi, ilke yönetimi ve profil yönetimi için kullanılacaktır.

Bu yeni deneyimin sağlayacakları:
- Sizi hizmetler arasında grupları yinelemek zorunda kalmaktan kurtarır.
- Yeni eklenen bazı Azure Active Directory Premium (AADP) grup özelliklerine erişmenize olanak tanır.
- PowerShell ve Graph kullanılarak genişletilebilirlik sağlar.
- Kurumsal mobil kullanım yönetimi genelinde grup yönetimi deneyimini birleştirir.

Güvenlik Gruplarına geçiş yapabilmek için, geçerli yönetici konsolunda bazı değişiklikler yapılacaktır. Bu değişiklikler ve Azure AD güvenlik gruplarının kullanımı, Intune belgelerine kaydedilecektir.

Intune’u yeni kullanmaya başlayan müşteriler, güvenlik grubu değişikliklerinden bazılarını geçerli kiracılardan önce göreceklerdir.

Grup yönetimindeki değişikliklere ek olarak, aşağıdaki işlevler de kullanım dışı kalacaktır:
- Yeni grup oluşturulurken üyeleri ve grupları dışlama
- **Gruplanmamış Kullanıcılar** ve **Gruplanmamış Cihazlar** grupları
- Hizmet Yöneticisi rolündeki **Grupları Yönet** işlevi
- Bildirim Kuralları için özel grup tabanlı uyarılar
- Raporlarda gruplarla özetleme

Ağustos ayında, kullanım dışı bırakılan bu işlevlerin etkisini azaltma hakkında daha fazla bilgi sunulacaktır.

### Android için Şirket Portalı’na eklenen 'Bildirimler'
Eylül’de kullanıma sunacağımız güncelleştirmeyle Android için Şirket Portalı’nda giriş sayfasına yeni **Bildirimler** simgesi eklenecektir. Bu simgeye dokunulduğunda **Bildirimler** sayfasına erişim sağlanacak, bu sayfada son kullanıcınıza Şirket Portalı uygulamasında dikkat edilmesi gereken cihaz uyumsuzluğu, kayıt güncelleştirmesi ve kayıt etkinleştirmesi gibi tüm öğeler gösterilecektir. iOS Şirket Portalı uygulamasını da kullanıyorsanız, bildirimler deneyimini zaten görmüş olacaksınız. **Bildirimler** sayfası eklendikten sonra, cihazın önceden kaydedilmiş olması koşuluyla Android için Şirket Portalı’nı her başlattığınızda veya sürdürdüğünüzde **Şirket Erişim Kurulumu** sayfasını görmeyeceksiniz. Birçoğunuzun son kullanıcı kılavuzları oluşturduğunu ve kılavuzunuzun/ekran görüntülerinizin güncelleştirilmesi gerektiğinde önceden size bildirilmesini istediğinizi duyuyoruz. Lütfen deneyimdeki yaklaşan değişiklikleri yansıtacak şekilde belgelerinizi güncelleştirin. Güncelleştirilmiş ekran görüntülerini şu adreste bulabilirsiniz: https://aka.ms/androidcpupdate.  



### Bulut yol haritası
[Bulut Platformu yol haritası](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune) ile yaklaşan Intune geliştirmelerinden haberdar olun.

### Hizmeti kullanımdan kaldırma
- **iOS Şirket Portalı uygulaması desteğindeki değişiklikler**<br/>
Temmuz ayında, iOS için Microsoft Intune Şirket Portalı uygulamasını kullanan tüm kullanıcılarının en son sürümü kullanmaları gerekecektir. Yeni kullanıcılar yalnızca en son sürümünü indirebilecektir ve geçerli kullanıcıların buna güncelleştirme yapmaları gerekecektir. En son sürüm iOS 8.0 veya üzerini gerektirir ve bu yüzden daha önceki iOS sürümlerini çalıştıran cihazlar iOS 8.0 veya üzeri sürüme güncelleştirilene ve sonra Şirket Portalı uygulaması en son sürüme güncelleştirilene kadar Şirket Portalı’nı kullanamayacak veya ona kaydolamayacaktır. iOS 8.0 öncesi sürümleri çalıştıran kayıtlı cihazların Intune Yönetici Konsolu’nda yönetilmesi ve listelenmesi devam edecektir.  

- **En düşük iOS Managed Browser sürümü 8.0 olarak güncelleştirildi**<br/>
Ağustos’ta, Intune yalnızca iOS 8.0 veya üstünü çalıştıran cihazları destekleyecek, güncelleştirilmiş iOS için Microsoft Intune Managed Browser uygulamasını kullanıma sunacaktır. iOS 7.1 cihazları mevcut Managed Browser uygulamasını kullanmaya devam edebilirler, ama yeni Managed Browser özelliklerine erişebilmeleri ve bu özelliklerden tam olarak yararlanabilmeleri için lütfen kullanıcılarınızı iOS 8.0 veya üstüne güncelleştirmeye teşvik edin.  
<!---TFS 1313253--->

- **Windows 8 ve Windows Phone 8 için Şirket Portalı uygulamaları Eylül 2016’dan itibaren kullanımdan kalkacaktır** <br/>
Eylül 2016'den itibaren, Microsoft Intune Windows Phone 8 ve Windows 8 platformları için Microsoft Intune Şirket Portalı uygulamaları desteğine son verecektir. Cihazları Windows 8.1 ve Windows Phone 8.1’e güncelleştirin ve bu cihazlara uygulama dağıtmaya devam etmek için ilgili Windows 8.1 ve Windows Phone 8.1 Şirket Portalı uygulamalarını kullanın.
<!---TFS 1255391--->

- **Intune Görüntüleyicisi uygulamaları** <br/>
Yeni RMS paylaşım uygulamasının kullanıma sunulmasıyla, Ağustos 2016’dan başlayarak aşağıdaki Intune Görüntüleyicisi uygulamalarını kaldırıyoruz:
    - Intune AV Görüntüleyicisi
    - Intune PDF Görüntüleyicisi
    - Google Play’den Android için Intune Resim Görüntüleyicisi

  Intune Görüntüleyicisi uygulamalarını kullanmak yerine, Android cihazlarda şirket dosyalarını güvenle görüntülemek için üç ayrı uygulama yerine tek bir uygulama dağıtmanıza olanak tanıyan yeni [Android için Hak Yönetimi uygulamasını (RMS paylaşımı)](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app) kullanmanızı öneririz. Intune görüntüleyicisi uygulamasının desteği sona erdiğinde, bu uygulama Google Store’dan kaldırılacak ve gelecekte kullanıma sunulmayacaktır.

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



<!--HONumber=Aug16_HO1-->


