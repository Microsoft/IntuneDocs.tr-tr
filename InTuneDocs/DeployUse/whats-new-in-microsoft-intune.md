---
title: Yenilikler | Microsoft Intune
description: "Bu ayki ve geçmişteki Microsoft Intune sunumlarındaki yenilikleri öğrenin"
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 09/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5b3256852431efb83fb2cc9fa067dd3f4a68a050
ms.openlocfilehash: cef0a26204a22c95d2b639500246e435fcf7f9f7


---

# Microsoft Intune'daki yenilikler -- Eylül
Microsoft Intune’un bu sürümündeki yenilikleri öğrenin. Planlama yapmanız gereken yaklaşan değişiklikler hakkında ve geçmiş sunumlar hakkında bilgiler de alabilirsiniz.

Bu özelliklerin tümü, sonunda karma müşteri dağıtımlarında (Intune ile Configuration Manager) desteklenecektir. Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler sayfamızı](https://technet.microsoft.com/library/mt718155.aspx) gözden geçirin.
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

>[!IMPORTANT]
>Blog gönderisi - Microsoft Intune kullanarak mobil cihazların güncel kalmasını sağlama<br>
>Yakın zamanda iOS cihazlarına yapılan "Trident" kötü amaçlı yazılım saldırılarından sonra, Intune’un cihazınızı güvenli ve güncel tutmaya yardımcı olabileceği değişik yolları göstermek için [Microsoft Intune kullanarak mobil cihazların güncel kalmasını sağlama](https://blogs.technet.microsoft.com/enterprisemobility/2016/08/26/ensuring-mobile-devices-are-up-to-date-using-microsoft-intune/) adında yeni bir blog gönderisi yayımladık.

## iOS 10 desteği
Mevcut Intune MDM ve MAM senaryoları iOS 10 ile uyumludur. İpuçları için [Intune Desteği Takım Blogu](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/)’na bakın.

## Uygulama Sarmalama Aracı, Android ve iOs için cihaz kaydı gerektirmeden MAM’yi destekler
Intune Uygulama Sarmalama Aracı, iOS ve Android için Intune MAM iş kolu (LOB) uygulamalarını etkinleştirmek için kullanılan bir komut satırı aracıdır. Bu, Intune MAM SDK’sını uygulamanızla tümleştirmenin en basit yoludur; böylelikle uygulamanız, Intune aracılığıyla dağıtılan MAM ilkelerini zorunlu tutabilir. MAM ilkeleri kullanarak şunları yapabilirsiniz:

1. Uygulamanın verileri şifreleyebilirsiniz.
2. Bilgi çalışanlarının uygulamayı başlatırken PIN girmesini gerektirebilirsiniz.
3. Uygulamanın yalnızca diğer yönetilen uygulamalara veri aktarmasına izin verebilirsiniz.
4. Uygulamanın Android, iTunes ve iCloud’a veri yedeklemesini önleyebilirsiniz.
5. Diğer yönetilen uygulamalarla arasında yalnızca Kes, Kopyala ve Yapıştır işlemlerine izin verebilirsiniz.

Güncelleştirilmiş Intune Uygulama Sarmalama Aracı’nın genel önizlemesi, artık iOs ve Android’deki dahili LOB uygulamalarında cihaz kaydına gerek kalmadan MAM desteği sağlar. Bu da son kullanıcılarınızın MAM özellikli LOB uygulamalarını kullanmak için cihazlarını kaydetmek zorunda olmadıkları anlamına gelir.

Genel önizleme yazılımını herkes test edesilir ve msintuneappsdk'nin GitHub’ında bulunan yardımcı belgeleri okuyabilir:

http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

Android ve iOS Yayın öncesi Sürüm için Microsoft Intune Uygulama Sarmalayıcı’yı yükleyip kullanmadan önce:

* Android ve iOS Yayın öncesi Sürüm için Microsoft Intune Uygulama Sarmalama Aracı’nın Microsoft Lisans Koşulları’nı gözden geçirmelisiniz
* Kendi kayıtlarınız için lisans koşullarının bir kopyasını yazdırmalı ve saklamalısınız. Android Yayın Öncesi Sürüm için Microsoft Intune Uygulama Sarmalama Aracı’nı indirerek ve kullanarak bu lisans koşullarını kabul etmiş sayılırsınız. Kabul etmiyorsanız, yazılımı kullanmayın.
<!---TFS 1235607--->

## Eylül’de Intune gruplarının Azure Active Directory’ye geçişi başlıyor
Bazı yeni Intune hesapları, Intune kullanıcı grupları yerine Azure Active Directory güvenlik gruplarını kullanacaktır. Intune portalı gruplar sayfasında sizi Azure yönetim portalına yönlendiren bir bağlantı olacağı için, güvenlik gruplarıyla çalıştığınızı anlayabileceksiniz.

## Android cihazlarını korumak için Lookout tümleştirmesi
Microsoft, Android mobil cihazlardaki kötü amaçlı yazılımları, riskli uygulamaları ve diğer tehditleri algılayarak cihazları korumak için Lookout’un mobil tehdit koruma çözümüyle tümleştiriliyor. Lookout’ın çözümü tehdit düzeyini saptamanıza yardımcı olur ve bu ayar yapılandırılabilir. Lookout’un risk değerlendirmesi temelinde cihaz uyumluluğunu saptamak için Intune’da bir uyumluluk ilkesi kuralı oluşturabilirsiniz. Koşullu erişim ilkelerini kullanarak, cihaz uyumluluk durumuna göre şirket kaynaklarına erişime izin verebilir veya erişimi reddedebilirsiniz.

Uyumlu olmayan cihazların son kullanıcılarının kaydolmaları istenir. Erişim kazanmak için Android cihazlarına Lookout for Work uygulamasını yüklemeleri, uygulamaları etkinleştirmeleri ve Lookout for Work uygulamasında bildirilen tehditleri gidermeleri gerekir. Daha fazla bilgi edinmek için bkz. [Cihaz, ağ ve uygulama riskine dayalı olarak erişimi kısıtlama](restrict-access-based-on-device-network-app-risk.md).


## Şirket Portalı güncelleştirmeleri

### Android

**Android için Şirket Portalı’na eklenen “Bildirimler”**<br/>
Şirket Portalı’nda giriş sayfasına Android için yeni Bildirimler simgesi eklendi. Bu simgeye dokunulduğunda Bildirimler sayfasına erişim sağlanır; bu sayfada son kullanıcınıza Şirket Portalı uygulamasında dikkat edilmesi gereken cihaz uyumsuzluğu, kayıt güncelleştirmesi ve kayıt etkinleştirmesi gibi tüm öğeler gösterilir. iOS Şirket Portalı uygulamasında bu bildirimler deneyimi önceden sağlanmıştır. Yeni Bildirimler sayfasının bulunması, cihazın önceden kaydedilmiş olması koşuluyla kullanıcının Şirket Portalı’nı her başlattığında veya sürdürdüğünde Şirket Erişim Kurulumu sayfasını artık görmeyeceği anlamına gelir. Kendi son kullanıcı yönergelerinizi oluşturuyorsanız, bu değişikliği yansıtacak şekilde belgelerinizi güncelleştirmek isteyebilirsiniz. Güncelleştirilmiş ekran görüntülerini [burada](https://aka.ms/androidcpupdate) bulabilirsiniz.  
<!---TFS 1095560--->

**Android için Şirket Portalı’nda geri bildirim sağlama**</br>
Android için Şirket Portalı’nın menüsüne yeni bir öğe eklendi. **Yardım ve Geri Bildirim**’e dokunulduğunda üç eylem gösterilir:
* Şirket Portalı hakkındaki sorunları BT bölümünüze bildirmek için **Yardım Al**’ı kullanın. BT, e-posta istemcinizi kullanarak bir e-posta oluşturur ve bu e-postaya Şirket Portalı günlüklerini ekler. **Yardım Al** seçeneği, **Ayarlar** sayfasındaki **Veri Gönder** özelliğinin yerini almıştır.
* Şirket Portalı ekibine geri bildirim sağlamak için **Geri Bildirim Verin** eylemini kullanın.
* Google Play’de Şirket Portalı uygulamasıyla ilgili değerlendirme veya gözden geçirme sağlamak için **Uygulamamızı değerlendirin** eylemini kullanın.

### iOS
**iOS Şirket Portalı uygulaması desteğindeki değişiklikler**<br/>
iOS için Microsoft Intune Şirket Portalı uygulamasının tüm kullanıcılarının en son sürümü kullanmaları gerekir. Yeni kullanıcılar yalnızca en son sürümünü indirebilir ve geçerli kullanıcıların buna güncelleştirme yapmaları gerekir. En son sürüm iOS 8.0 veya üzerini gerektirir ve bu yüzden daha önceki iOS sürümlerini çalıştıran cihazlar iOS 8.0 veya üzeri sürüme güncelleştirilene ve sonra Şirket Portalı uygulaması en son sürüme güncelleştirilene kadar Şirket Portalı’nı kullanamaz veya ona kaydolamaz. iOS 8.0 öncesi sürümleri çalıştıran kayıtlı cihazların Intune Yönetici Konsolu’nda yönetilmesi ve listelenmesi devam edecektir.
<!---TFS 1283165--->

**iOS son kullanıcılarının uygulamalarını edinme şekillerine yönelik geliştirmeler**<br/>
Kullanıcıları tüm uygulamalarda tek konuma, yani Şirket Portalı web sitesine yönlendirmek üzere iOS için Şirket Portalı uygulamasındaki uygulama kutucuklarında aşağıdaki değişiklikler yapılmıştır. Apple kısıtlamaları iş kolu uygulamalarının ve yönetilen uygulama mağazası uygulamalarının Şirket Portalı uygulamasında listelenmesini yasakladığından kullanıcıların tüm uygulamalarını bulabilmek için farklı görünümleri ziyaret etmesi gerekir.

- **Şirket Uygulamaları** kutucuğu daha önce Şirket Portalı Web sitesinin TÜMÜ sekmesindeki tüm uygulamaların listesine yönlendirmekteydi ve bu şekilde çalışmaya devam edecektir. Kutucuk adı **Tüm Uygulamalar** olarak değişmiştir.
- **Diğer Uygulamalar** kutucuğu daha önce, Şirket Portalı uygulamasında bulunan ve Apple’ın Şirket Portalı uygulamasının göstermesine izin verdiği tüm uygulamaları listeleyen görünüme yönlendiriyordu. Kutucuk adı **Öne Çıkan Uygulamalar** olarak değişmiştir ve kutucuğa dokunan kullanıcıları Şirket Portalı web sitesinin ÖNE ÇIKANLAR sekmesine götürür.
-  **Kategoriler** kutucuğu daha önce, Şirket Portalı uygulaması içinde bulunan ve uygulama kategorilerini listeleyen görünüme yönleniyordu. Kutucuk adı değişmemiştir, ancak artık Şirket Portalı web sitesinin KATEGORİLER sekmesine yönlendirir.
Güncelleştirilmiş ekran görüntülerini [burada](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186) bulabilirsiniz.
<!---TFS 1317133--->

**BT Uzmanının bir uygulama için bu gereksinimi ayarlaması durumunda iOS Managed Browser uygulamasını yükleme uyarısı**<br/>
Web klibini yalnızca yönetilen bir tarayıcıda açılacak şekilde yapılandırdıysanız ve yönetilen tarayıcı bir cihazda yüklü değilse, cihazdaki Şirket Portalı uygulaması, web klibinin yüklenebilmesi için önce yönetilen tarayıcının yüklenmesi gerektiği konusunda kullanıcıyı uyarır.
<!---TFS 1228570--->

### Windows
**Windows Phone 8.1 Şirket Portalı uygulamasına Geri Bildirim düğmesi eklendi**<br/>
Windows Phone 8.1 Şirket Portalı uygulaması, son kullanıcıların yeni “geri bildirim gönder” düğmesini kullanarak uygulama hakkında geri bildirim göndermesine olanak tanır. Düğmeyi bulmak için, kullanıcılar Şirket Portalı uygulama ekranının sağ alt kısmındaki “üç nokta” menüsüne dokunur ve sonra da **geri bildirim gönder**’e dokunur. Toplanan anonim geri bildirimler, Microsoft’un kullanıcılar için Şirket Portalı uygulama deneyimini geliştirmesine yardımcı olacak.
<!---TFS 1317806--->


## Yakında

### Intune Grupları Azure Active Directory Grupları’na geçiyor
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

### Exchange Online ve SharePoint Online için yeni Koşullu Erişim uygulama ilkeleri
Exchange Online ve SharePoint Online’a erişimi kısıtlayabileceksiniz ve yalnızca Outlook, Word, Excel ve OneDrive gibi Office mobil uygulamalarından erişim gelebilecek. Bu yeni özellik, Intune mobil uygulama yönetimi (MAM) ilkeleriyle mükemmel bir uyum sağlar ve yerleşik posta istemcilerine veya Intune MAM ilkeleriyle yapılandırılmamış olan diğer uygulamalara erişimi engelleyebilirsiniz. Böylelikle, kullanıcılarınızın kuruluşunuzun verilerine Intune MAM kullanılarak korunan uygulamalarla erişmesi güvence altına alır. Intune mobil uygulama yönetimini Azure portalından başlatabilirsiniz. “Ayarlar” dikey penceresinde yeni Koşullu Erişim bölümünü bulun.



### Hizmeti kullanımdan kaldırma

- **Windows 8 ve Windows Phone 8 için Şirket Portalı uygulamaları kullanımdan kalkacaktır** <br/>
Microsoft Intune, Ekim 2016'dan itibaren Windows 8 ve Windows Phone 8 Şirket Portalı uygulamaları desteğini kaldıracaktır. Microsoft Intune, Windows Phone 8 platform desteğini de kaldıracaktır. Bunların sonucunda, herhangi bir Windows Phone 8 cihazını kaydetmeniz veya güncelleştirmeniz mümkün olmayacaktır. Önceden kaydedilen Windows Phone 8 ve Windows 8 cihazlarını yönetmeye devam edebilirsiniz. Windows 8 ve Windows Phone 8 cihazlarını Windows 8.1’e ve Windows Phone 8.1’e güncelleştirin ve bu cihazlara bir kesinti olmadan uygulama dağıtmaya devam etmek için ilgili Windows 8.1 ve Windows Phone 8.1 Şirket Portalı uygulamalarını kullanın.



### Bulut yol haritası
[Bulut Platformu yol haritası](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune) ile yaklaşan Intune geliştirmelerinden haberdar olun.


## Önceki Intune sürümleri
Son altı ay içinde Intune'da neler yayınlandığını görmek istiyorsanız, bunlar [Önceki Intune yayınları](previous-intune-releases.md) makalesinde listelenmektedir.

### Ayrıca bkz.
* [Microsoft Intune Blogu](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Bulut Platformu yol haritası](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)



<!--HONumber=Sep16_HO4-->


