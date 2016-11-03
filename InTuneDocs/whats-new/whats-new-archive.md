---
title: "Yenilikler arşivi | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ec77bc20bf429c804cb502bb46fc549d080a94ac
ms.openlocfilehash: 14698e5f40e76e370e178aeb6187d89fbc5cb2bd


---
## Eylül 2016
## Yeni özellikler, duyurular ve bilgiler
* [Windows koşullu erişim](#windows-conditional-access)
* [iOS 10 desteği](#ios-10-support)
* [Uygulama Sarmalama Aracı, Android ve iOS için cihaz kaydı gerektirmeden MAM’yi destekler](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios)
* [Eylül’de Intune gruplarının Azure Active Directory’ye geçişi başlıyor](#intune-groups-begin-transitioning-to-azure-active-directory-in-september)
* [Android cihazlarını korumak için Lookout tümleştirmesi](#lookout-integration-to-protect-android-devices)
* [Android, iOS ve Windows için Şirket Portalı güncelleştirmeleri](#company-portal-updates)
* [Intune sözlüğü](#intune-glossary)
* [Yakında](#whats-coming)

## Windows koşullu erişim
Artık Windows bilgisayarlarının Exchange Online ve SharePoint Online’a erişmesini engellemek için Intune Yönetici Konsolu aracılığıyla koşullu erişim ilkeleri oluşturabilirsiniz. Office masaüstü ve evrensel uygulamalara erişimi engellemek için de koşullu erişim ilkeleri oluşturabilirsiniz.

## iOS 10 desteği
Mevcut Intune MDM ve MAM senaryoları iOS 10 ile uyumludur. İpuçları için [Intune Desteği Takım Blogu](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/)’na bakın.

## Uygulama Sarmalama Aracı, Android ve iOS için cihaz kaydı gerektirmeden MAM’yi destekler
Intune Uygulama Sarmalama Aracı, iOS ve Android için Intune MAM iş kolu (LOB) uygulamalarını etkinleştirmek için kullanılan bir komut satırı aracıdır. Bu, Intune MAM SDK’sını uygulamanızla tümleştirmenin en basit yoludur; böylelikle uygulamanız, Intune aracılığıyla dağıtılan MAM ilkelerini zorunlu tutabilir. MAM ilkeleri kullanarak şunları yapabilirsiniz:

1. Uygulamanın verileri şifreleyebilirsiniz.
2. Bilgi çalışanlarının uygulamayı başlatırken PIN girmesini gerektirebilirsiniz.
3. Uygulamanın yalnızca diğer yönetilen uygulamalara veri aktarmasına izin verebilirsiniz.
4. Uygulamanın Android, iTunes ve iCloud’a veri yedeklemesini önleyebilirsiniz.
5. Diğer yönetilen uygulamalarla arasında yalnızca Kes, Kopyala ve Yapıştır işlemlerine izin verebilirsiniz.

Güncelleştirilmiş Intune Uygulama Sarmalama Aracı’nın genel önizlemesi, artık iOS ve Android’deki dahili LOB uygulamalarında cihaz kaydına gerek kalmadan MAM desteği sağlar. Bu da son kullanıcılarınızın MAM özellikli LOB uygulamalarını kullanmak için cihazlarını kaydetmek zorunda olmadıkları anlamına gelir.

Genel önizleme yazılımını herkes test edebilir ve msintuneappsdk'nin GitHub’ında bulunan yardımcı belgeleri okuyabilir:

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
* Şirket Portalı ekibine geri bildirim sağlamak için **Geri Bildirim Ver** eylemini kullanın.
* Google Play’de Şirket Portalı uygulamasıyla ilgili değerlendirme veya gözden geçirme sağlamak için **Uygulamamızı değerlendirin** eylemini kullanın.

### iOS
**iOS Şirket Portalı uygulaması desteğindeki değişiklikler**<br/>
iOS için Microsoft Intune Şirket Portalı uygulamasının tüm kullanıcılarının en son sürümü kullanmaları gerekir. Yeni kullanıcılar yalnızca en son sürümünü indirebilir ve geçerli kullanıcıların buna güncelleştirme yapmaları gerekir. En son sürüm iOS 8.0 veya üzerini gerektirir ve bu yüzden daha önceki iOS sürümlerini çalıştıran cihazlar iOS 8.0 veya üzeri sürüme güncelleştirilene ve sonra Şirket Portalı uygulaması en son sürüme güncelleştirilene kadar Şirket Portalı’nı kullanamaz veya ona kaydolamaz. iOS 8.0 öncesi sürümleri çalıştıran kayıtlı cihazların Intune Yönetici Konsolu’nda yönetilmesi ve listelenmesi devam edecektir.
<!---TFS 1283165--->

**iOS son kullanıcılarının uygulamalarını edinme şekillerine yönelik geliştirmeler**<br/>
Kullanıcıları tüm uygulamalarda tek konuma, yani Şirket Portalı web sitesine yönlendirmek üzere iOS için Şirket Portalı uygulamasındaki uygulama kutucuklarında aşağıdaki değişiklikler yapılmıştır. Apple kısıtlamaları iş kolu uygulamalarının ve yönetilen uygulama mağazası uygulamalarının Şirket Portalı uygulamasında listelenmesini yasakladığından kullanıcıların tüm uygulamalarını bulabilmek için farklı görünümleri ziyaret etmesi gerekir.

- **Şirket Uygulamaları** kutucuğu daha önce Şirket Portalı Web sitesinin TÜMÜ sekmesindeki tüm uygulamaların listesine yönlendirmekteydi ve bu şekilde çalışmaya devam edecektir. Kutucuk adı **Tüm Uygulamalar** olarak değişmiştir.
- **Diğer Uygulamalar** kutucuğu daha önce, Şirket Portalı uygulamasında bulunan ve Apple’ın Şirket Portalı uygulamasının göstermesine izin verdiği tüm uygulamaları listeleyen görünüme yönlendiriyordu. Kutucuk adı **Öne Çıkan Uygulamalar** olarak değişmiştir ve kutucuğa dokunan kullanıcıları Şirket Portalı web sitesinin ÖNE ÇIKANLAR sekmesine götürür.
-  **Kategoriler** kutucuğu daha önce Şirket Portalı uygulaması içinde bulunan ve uygulama kategorilerini listeleyen görünüme yönlendirmekteydi. Kutucuk adı değişmemiştir, ancak artık Şirket Portalı web sitesinin KATEGORİLER sekmesine yönlendirir.
Güncelleştirilmiş ekran görüntülerini [burada](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186) bulabilirsiniz.
<!---TFS 1317133--->

**BT Uzmanının bir uygulama için bu gereksinimi ayarlaması durumunda iOS Managed Browser uygulamasını yükleme uyarısı**<br/>
Web klibini yalnızca yönetilen bir tarayıcıda açılacak şekilde yapılandırdıysanız ve yönetilen tarayıcı bir cihazda yüklü değilse, cihazdaki Şirket Portalı uygulaması, web klibinin yüklenebilmesi için önce yönetilen tarayıcının yüklenmesi gerektiği konusunda kullanıcıyı uyarır.
<!---TFS 1228570--->

### Windows
**Windows Phone 8.1 Şirket Portalı uygulamasına Geri Bildirim düğmesi eklendi**<br/>
Windows Phone 8.1 Şirket Portalı uygulaması, son kullanıcıların yeni “geri bildirim gönder” düğmesini kullanarak uygulama hakkında geri bildirim göndermesine olanak tanır. Düğmeyi bulmak için, kullanıcılar Şirket Portalı uygulama ekranının sağ alt kısmındaki “üç nokta” menüsüne dokunur ve sonra da **geri bildirim gönder**’e dokunur. Toplanan anonim geri bildirimler, Microsoft’un kullanıcılar için Şirket Portalı uygulama deneyimini geliştirmesine yardımcı olacak.
<!---TFS 1317806--->

## Intune sözlüğü</br>
Intune ürününde kullanılan bazı terimleri anlamanıza yardımcı olmak için kitaplığa yeni bir [sözlük konusu](https://docs.microsoft.com/intune/understand-explore/intune-glossary) ekledik.



<!--HONumber=Oct16_HO2-->


