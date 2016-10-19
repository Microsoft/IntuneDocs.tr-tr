---
title: Beklenenler | Microsoft Intune
description: 
keywords: 
author: Lindavr
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0d70a46d9c13aad1bc0a940836d83a99b93bb95e
ms.openlocfilehash: 7f84ad1566431a7a72897750fadbc90cb56ec5ce


---

# Microsoft Intune’da kullanıma sunulacak yeni özellikler - Ağustos
Bu bilgiler NDA kapsamında çok sınırlı bir temelde sağlanır ve değiştirilebilir. Burada listelenen özelliklerden bazılarının son tarihe yetişememe riski vardır ve gelecek sürüme ertelenebilir. Diğer özellikler, müşterinin kullanımına hazır olduğundan emin olmak için pilot (sürüyor) aşamasında test edilmektedir. Sorularınız veya kaygılarınız varsa lütfen Intune/PM arkadaşınıza ulaşın.

Bu sayfa düzenli aralıklarla güncelleştirilir. Beklenen yeni güncelleştirmeler için yeniden gelip gözden geçirin.

Intune için aşağıdaki değişiklikler geliştirilme aşamasındadır. Bu özelliklerin tümü, sonunda karma müşteri dağıtımlarında (Intune ile Configuration Manager) desteklenecektir. Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler sayfamızı](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx) gözden geçirin.


## Uygulama yönetimi
### iOS 9.3 için gizli ve gösterilen uygulamalar
iOS 9.3 veya üzerini çalıştıran denetimli cihazlarda iOS genel yapılandırma ilkesindeki gizli ve gösterilen uygulamalar listesini kullanarak şunları yapabilirsiniz:
- Kullanıcılardan gizlenecek uygulamaların bir listesini belirtin. Kullanıcılar bu uygulamaları görüntüleyemez veya başlatamaz.
- Kullanıcıların görüntüleyebileceği ve başlatabileceği uygulamaların bir listesini belirtin. Başka hiçbir uygulama görüntülenemez veya başlatılamaz.

Belirtebileceğiniz uygulamalara hem sizin dağıttığınız uygulamalar hem de Mesajlar ve Notlar gibi yerleşik iOS uygulamaları dahildir.
<!---TFS 1279009--->

### Samsung KNOX cihazlar için izin verilen ve engellenen uygulamalar ilkesi

Artık Samsung KNOX cihazlar için aşağıdakilerden birini oluşturmanıza imkan tanıyan özel bir ilke yapılandırabilirsiniz:
- Cihazda çalışması engellenmiş uygulamaların listesi. Engellenenler listesinde tanımlanan bir uygulama cihazda yüklü olsa bile etkinleştirilemez.
- Cihaz kullanıcılarının Google Play mağazasından yüklemesine izin verilen uygulamaların listesi. Mağazadan başka hiçbir uygulama yüklenemez.

Bu ayarlar yalnızca Samsung KNOX çalıştıran cihazlar tarafından kullanılabilir.
<!--- For details, see [Use custom policies to allow and block apps for Samsung KNOX devices]( custom-policy-to-allow-and-block-samsung-knox-apps.md)--->
<!---TFS 1311629 --->

### Mobil uygulama yönetimi (MAM) ilkeleriyle uyumlu yeni uygulamalar
[iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) ve [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) için Yammer uygulaması, cihazın kayıtlı olup olmadığından bağımsız olarak [Intune mobil uygulama yönetimi (MAM) ilkeleri](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) ile uyumlu olacak.

MAM ile uyumlu uygulamaların tam listesi için [Microsoft Intune uygulama iş ortakları](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) sitesine bakın.
<!--- TFS 1252335 & 1252336--->

## Cihaz yönetimi
### Android 7.0 desteği
Ağustos’ta Intune, mobil cihazlar için yeni çıkacak Android 7.0 işletim sistemine yönelik "0. gün" desteği sağlayacaktır.
<!---TFS 1262053--->
### Android 7.0 cihazlarda uzaktan geçiş kodu sıfırlama özelliğinin Google tarafından kaldırılması
Google, BT yöneticileri ve son kullanıcıların Android 7.0 cihazların parolasını uzaktan sıfırlama olanağını sona erdiriyor. Daha önce BT yöneticileri bir kullanıcının geçiş kodunu uzaktan sıfırlayabiliyor ve son kullanıcılar Şirket Portalı web sitesinden kendi parolalarını sıfırlayabiliyordu.

## Grup yönetimi
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

## Şirket Portalı

### Şirket Portalı’ndan Microsoft’a geri bildirim bağlantısı
Şirket portalı web sitesi, son kullanıcıların sayfanın en altındaki yeni “Geri Bildirim” bağlantısına dokunarak siteyle ilgili deneyimlerini Microsoft’a göndermesine imkan tanıyacak. Toplanan anonim geri bildirimler, Microsoft’un kullanıcılar için Şirket Portalı web sitesi deneyimini geliştirmesine yardımcı olacak.
<!--- TFS 1313657--->

### Android için Şirket Portalı’na eklenen 'Bildirimler'
Eylül’de kullanıma sunacağımız güncelleştirmeyle Android için Şirket Portalı’nda giriş sayfasına yeni **Bildirimler** simgesi eklenecektir. Bu simgeye dokunulduğunda **Bildirimler** sayfasına erişim sağlanacak, bu sayfada son kullanıcınıza Şirket Portalı uygulamasında dikkat edilmesi gereken cihaz uyumsuzluğu, kayıt güncelleştirmesi ve kayıt etkinleştirmesi gibi tüm öğeler gösterilecektir. iOS Şirket Portalı uygulamasını da kullanıyorsanız, bildirimler deneyimini zaten görmüş olacaksınız. **Bildirimler** sayfası eklendikten sonra, cihazın önceden kaydedilmiş olması koşuluyla Android için Şirket Portalı’nı her başlattığınızda veya sürdürdüğünüzde **Şirket Erişim Kurulumu** sayfasını görmeyeceksiniz. Birçoğunuzun son kullanıcı kılavuzları oluşturduğunu ve kılavuzunuzun/ekran görüntülerinizin güncelleştirilmesi gerektiğinde önceden size bildirilmesini istediğinizi duyuyoruz. Lütfen deneyimdeki yaklaşan değişiklikleri yansıtacak şekilde belgelerinizi güncelleştirin. Güncelleştirilmiş ekran görüntülerini şu adreste bulabilirsiniz: https://aka.ms/androidcpupdate.  

### iOS son kullanıcılarının uygulamalarını edinme şekillerine yönelik geliştirmeler
Kullanıcıları tüm uygulamalarda tek konuma, yani Şirket Portalı web sitesine yönlendirmek üzere iOS için Şirket Portalı uygulamasındaki uygulama kutucuklarında Eylül ayında aşağıdaki değişiklikler yapılmıştır. Apple kısıtlamaları şu anda iş kolu uygulamalarının ve yönetilen uygulama mağazası uygulamalarının Şirket Portalı uygulamasında listelenmesini yasakladığından kullanıcıların tüm uygulamalarını bulabilmek için farklı görünümleri ziyaret etmesi gerekir.

- **Şirket Uygulamaları** kutucuğu şu anda Şirket Portalı web sitesinin TÜMÜ sekmesindeki tüm uygulamaların bir listesine yönlendirmektedir ve bu şekilde çalışmaya devam edecektir. Kutucuk adı **Tüm Uygulamalar** olarak değişecektir.
- **Diğer Uygulamalar** kutucuğu şu anda, Şirket Portalı uygulamasında bulunan ve Apple’ın Şirket Portalı uygulamasının göstermesine izin verdiği tüm uygulamaları listeleyen görünüme yönlendirmektedir. Kutucuk adı **Öne Çıkan Uygulamalar** olarak değişecek ve kutucuğa dokunan kullanıcıları Şirket Portalı web sitesinin ÖNE ÇIKANLAR sekmesine götürecektir.
-  **Kategoriler** kutucuğu şu anda, Şirket Portalı uygulaması içinde bulunan ve uygulama kategorilerini listeleyen görünüme yönlendirir. Kutucuk adı değişmeyecek, ancak artık Şirket Portalı web sitesinin KATEGORİLER sekmesine yönlendirecektir.
Güncelleştirilmiş ekran görüntülerini [burada](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186) bulabilirsiniz.
<!---TFS 1317133--->

### BT Uzmanının bir uygulama için bu gereksinimi ayarlaması durumunda iOS Managed Browser uygulamasını yükleme uyarısı
iOS Şirket Portalı uygulamasının Eylül sürümünde bir web klibini yalnızca yönetilen bir tarayıcıda açılacak şekilde yapılandırdıysanız ve yönetilen tarayıcı bir cihazda yüklü değilse, cihazdaki Şirket Portalı uygulaması, web klibinin yüklenebilmesi için önce yönetilen tarayıcının yüklenmesi gerektiği konusunda kullanıcıyı uyarır. 
<!---TFS 1228570--->

## Hizmeti kullanımdan kaldırma
### Windows 8 ve Windows Phone 8 için Şirket Portalı uygulamaları Eylül 2016’dan itibaren kullanımdan kalkacaktır
Microsoft Intune Eylül 2016'dan itibaren Windows Phone 8 ve Windows 8 platformları için Microsoft Intune Şirket Portalı uygulamalarına yönelik desteği sonlandıracaktır. Cihazları Windows 8.1 ve Windows Phone 8.1’e güncelleştirin ve bu cihazlara uygulama dağıtmaya devam etmek için ilgili Windows 8.1 ve Windows Phone 8.1 Şirket Portalı uygulamalarını kullanın.
<!---TFS 1255391--->

### Bildirim Kurallarında Özel Grup Hedeflemenin Kaldırılması
Intune bildirim kuralları, Intune’dan kime e-posta uyarısı gönderileceğini tanımlar. Şu anda, oluşturduğunuz bir Intune cihaz grubundaki cihazların tüm kullanıcılarına e-posta göndermek için bildirim kuralları yapılandırabilirsiniz. Haziran 2016'dan itibaren, kullanıcı tarafından oluşturulan grupları hedefleme artık desteklenmeyecektir.

Bu değişiklikle ilgili ilk zaman çizelgesi şöyledir:
- Eylül 2016’da, yeni kiracılar Bildirim Kuralı Oluşturma Sihirbazı’nın ikinci adımını görmeyecekler. Mevcut kiracılar bundan etkilenmez.
- Ekim 2016’ya doğru, mevcut kiracılardan bazıları sihirbazda “cihaz gruplarını seçme” adımını görmeyecek.
- Daha sonraki bir tarihte, kiracılardan hiçbirinin sihirbazda “cihaz grupları seçme” adımını görmeyeceğini umuyoruz.

<!---   TFS 1278864--->
### iOS Şirket Portalı uygulaması desteğindeki değişiklikler
Eylül ayında, iOS için Microsoft Intune Şirket Portalı uygulamasını kullanan tüm kullanıcılarının en son sürümü kullanmaları gerekecektir. Yeni kullanıcılar yalnızca en son sürümünü indirebilecektir ve geçerli kullanıcıların buna güncelleştirme yapmaları gerekecektir. En son sürüm iOS 8.0 veya üzerini gerektirir ve bu yüzden daha önceki iOS sürümlerini çalıştıran cihazlar iOS 8.0 veya üzeri sürüme güncelleştirilene ve sonra Şirket Portalı uygulaması en son sürüme güncelleştirilene kadar Şirket Portalı’nı kullanamayacak veya ona kaydolamayacaktır. iOS 8.0 öncesi sürümleri çalıştıran kayıtlı cihazların Intune Yönetici Konsolu’nda yönetilmesi ve listelenmesi devam edecektir.

<!---TFS 1283165--->


### Intune Görüntüleyicisi uygulamaları
Yeni RMS paylaşım uygulamasının kullanıma sunulmasıyla birlikte Ağustos 2016’da aşağıdaki Intune Viewer uygulamalarını kullanımdan kaldıracağız:
- Intune AV Görüntüleyicisi
- Intune PDF Görüntüleyicisi
- Google Play’den Android için Intune Resim Görüntüleyicisi

Intune Görüntüleyicisi uygulamalarını kullanmak yerine, Android cihazlarda şirket dosyalarını güvenle görüntülemek için üç ayrı uygulama yerine tek bir uygulama dağıtmanıza olanak tanıyan yeni Android için Hak Yönetimi uygulamasını (RMS paylaşımı) kullanmanızı öneririz. [RMS sharing uygulaması](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app) ile ilgili daha fazla bilgi edinin.
<!--- goes in 1608 What's New--->


### Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new-in-microsoft-intune.md).



<!--HONumber=Aug16_HO4-->


