---
title: "Erken sürüm | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: d0b3a883bb307fb06cb8d16500798086f328314a
ms.openlocfilehash: eeebf8b6b3bc5c7c35386eb20c96097af1f6769c
ms.lasthandoff: 02/14/2017


---


# <a name="the-early-edition-for-microsoft-intune---february-2017"></a>Microsoft Intune için erken sürüm - Şubat 2017

**Erken Sürüm** Microsoft Intune'un gelecek sürümlerinde kullanıma sunulacak yeni özelliklerin bir listesini sağlar. Bu bilgiler NDA kapsamında çok sınırlı bir temelde sağlanır ve değiştirilebilir. Burada listelenen özelliklerden bazılarının son tarihe yetişememe riski vardır ve gelecek sürüme ertelenebilir. Diğer özellikler, müşterinin kullanımına hazır olduğundan emin olmak için pilot (sürüyor) aşamasında test edilmektedir. Sorularınız veya kaygılarınız varsa lütfen Intune/PM arkadaşınıza ulaşın.

Bu sayfa düzenli aralıklarla güncelleştirilir. Ek güncelleştirmeleri daha sonra denetleyin.

> [!Note]
> Intune için aşağıdaki değişiklikler geliştirilme aşamasındadır. Bu özelliklerin tümü, sonunda karma müşteri dağıtımlarında (Intune ile Configuration Manager) desteklenecektir. Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler sayfamızı](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) gözden geçirin.

## <a name="new-capabilities"></a>Yeni Özellikler

### <a name="modernizing-the-company-portal-website---753980--"></a>Şirket Portalı web sitesi modernleştiriliyor <!--753980-->
Şubat ayından itibaren, karşıt renklerden oluşan yeni renk düzeni ve dinamik çizimlerle yeniden tasarlanan Şirket Portalı web sitesi, yardım masası ilgili kişisine ilişkin ayrıntıların yanı sıra yönetilen mevcut cihazlara yönelik bilgilerin bulunduğu bir "hamburger menüsü" de ![Şirket Portalı web sitesinin sol üst köşesine eklenmiş olan hamburger menüsünün küçük resmi](./media/CP_hamburger_menu.png) eklenerek diğer Microsoft ürün ve hizmetleriyle uyumlu hale getirilecektir. Kullanıcılara sunulan uygulamaları vurgulayacak şekilde yeniden düzenlenecek olan giriş sayfasında, Öne Çıkan ve Son Güncelleştirilen uygulamaların görüntülendiği döngüler yer alacak. Önce ve sonra görüntülerini [UI güncelleştirmeleri sayfasında](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui) bulabilirsiniz.

### <a name="new-guided-experience-for-windows-10-company-portal---713927--"></a>Windows 10 Şirket Portalı için kullanıcının yönlendirildiği yeni deneyim <!--713927-->
Mart ayından başlayarak, Windows 10 için Şirket Portalı tanımlanmamış veya kaydedilmemiş cihazlar için kullanıcının yönlendirildiği adım adım bir Intune deneyimi içerecektir. Yeni deneyimde, kullanıcılara AAD kaydını (Koşullu Erişim özelliklerinde tanımlama için gerekli) ve MDM kaydını (cihaz yönetim özellikleri için gerekli) gerçekleştirme işlemlerinde kullanıcılara yol gösteren, kullanıcının Windows 10 derlemesi için özelleştirilmiş adım adım yönergeler sağlanır. Kullanıcıya yol gösteren deneyime Şirket Portalı giriş sayfasından erişilebilir ve bu deneyim isteğe bağlıdır; kayıtları tamamlamayan kullanıcılar uygulamayı kullanmaya devam edebilir, ancak sınırlı işlevsellikle karşılaşabilir.

###

## <a name="notices"></a>Bildirimler

### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>Grup geçişi için iOS cihazlarda grup veya ilke güncelleştirmesi gerekmeyecek <!--898837-->
Azure Active Directory cihaz gruplarına geçiş sırasında, önceden bir Şirket Cihaz Kaydı profili tarafından atanmış olan her Intune cihaz grubu için Şirket Cihaz Kaydı profilinin adına göre AAD'de karşılık gelen bir dinamik cihaz grubu oluşturulacaktır. Bu sayede kaydı yapılan cihazların otomatik olarak gruplanması ve özgün Intune grubundakilerle aynı ilkeleri ve uygulamaları alması sağlanacaktır.

Bir kiracı gruplama ve hedefleme için geçiş işlemine girdiğinde Intune, otomatik olarak Şirket Cihaz Kaydı profili tarafından hedeflenen Intune grubuna karşılık gelecek bir dinamik AAD grubu oluşturacaktır. Intune Yöneticisinin hedef Intune grubunu silmesi halinde karşılık gelen dinamik AAD grubu silinmeyecektir. Grubun üyeleri ve dinamik sorgu silinecek ancak BT Yöneticisi AAD portalı üzerinden kaldırılana kadar grubun kendisi kalacaktır.

Benzer şekilde, BT Yöneticisinin bir Şirket Cihaz Kaydı profili ile hedeflenen Intune grubunu değiştirmesi halinde, Intune yeni profil atamasını yansıtan yeni bir dinamik grup oluşturacak ancak eski atama için oluşturulan dinamik grubu kaldırmayacaktır.

### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Windows cihazları için yeni MDM sunucusu adresi <!--893007-->
MDM sunucusu adresi olarak __manage.microsoft.com__ giren (sorulursa) Windows ve Windows Phone kullanıcıları, cihaz kaydetmeye çalıştıklarında başarısız olacaklardır. MDM sunucusu adresi __manage.microsoft.com__ yerine __enrollment.manage.microsoft.com__ olarak değiştirilmektedir. Kullanıcılarınızı, Windows veya Windows Phone cihazı kaydetmeye çalışırken sorulması halinde MDM sunucusu adresi olarak __enrollment.manage.microsoft.com__ girmeleri konusunda bilgilendirin. Bu güncelleştirme, DNS'de __EnterpriseEnrollment.contoso.com__ adresini __manage.microsoft.com__ adresine yönlendiren CNAME kaydının DNS'de __EnterpriseEnrollment.contoso.com__ adresini __EnterpriseEnrollment-s.manage.microsoft.com__ adresine yönlendiren bir CNAME kaydıyla değiştirilmesini gerektirir. Bu değişiklik hakkında daha fazla bilgi için [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange) adresini ziyaret edin.

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Android Şirket Portalı uygulaması için yeni kullanıcı deneyimi <!--621622-->
Mart ayından itibaren Android Şirket Portalı uygulaması [Material Design kılavuzuna](https://material.io/guidelines/material-design/introduction.html) uygun olarak modern bir tasarıma sahip olacak. Bu gelişmiş kullanıcı deneyimi şunları içeriyor olacak:

* __Renkler__: Sekme başlıklarının renkleri özel renk paletinize göre değiştirilebilir.
* __Arabirim__: Uygulamalar sekmesindeki Öne Çıkan Uygulamalar ve Tüm Uygulamalar düğmeleri güncelleştirildi. Arama düğmesi artık kayan eylem düğmesi şeklinde.
* __Gezinti__: Tüm Uygulamalar sayfasında daha kolay gezinme için Öne Çıkan Uygulamalar, Tüm Uygulamalar ve Kategoriler sekmeler halinde görüntüleniyor.
* __Hizmet__: Cihazlarım ve BT'ye Başvur sekmelerinin okunabilirliği geliştirildi.

Önce ve sonra görüntülerini [UI güncelleştirmeleri sayfasında](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui) bulabilirsiniz.

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>İş İçin Windows Mağazası’yla birden çok yönetim aracını ilişkilendirme<!--926135-->
İş İçin Windows Mağazası uygulamalarını dağıtmak için birden fazla yönetim aracı kullanmanız durumunda önceden bunların yalnızca birini İş İçin Windows Mağazası ile ilişkilendirebiliyordunuz. Artık mağaza ile Intune ve Configuration Manager gibi birden fazla yönetim aracını ilişkilendirebilirsiniz. Ayrıntılar için bkz. [Microsoft Intune ile İş İçin Windows Mağazası'ndan satın aldığınız uygulamaları yönetme](https://docs.microsoft.com/en-us/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune).

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Azure’daki yeni Intune yönetici deneyiminin genel önizlemesi <!--736542-->

2017 takvim yılının başlarında tam yönetici deneyimimizi Azure’a geçireceğiz. Bu sayede Grafik API’leri kullanılarak genişletilebilen modern bir hizmet platformunda çekirdek EMS iş akışlarının güçlü ve tümleşik yönetimi mümkün olacaktır.

Yeni deneme kiracıları, yeni yönetici deneyiminin genel önizlemesini bu ay Azure portalında görmeye başlayacaklar. Önizleme durumundayken, mevcut Intune konsolu ile gelen yetenekler ve eşlik, yinelemeli olarak sağlanır.

Azure portalındaki yönetici deneyimi, duyurulan yeni gruplandırma ve hedefleme işlevselliğini kullanır; mevcut kiracınız yeni gruplandırma deneyimine geçirildiğinde, siz de kiracınıza yönelik yeni yönetici deneyimini önizlemek üzere geçirilirsiniz. Bu sırada, kiracınız geçirilene kadar yeni işlevleri sınamak veya bunlara göz atmak isterseniz yeni bir Intune deneme hesabına kaydolun veya [yeni belgelere](https://docs.microsoft.com/en-us/intune-azure/introduction/what-is-microsoft-intune) bakın.

Kiracınızın geçişinin zaman çizelgesi hakkında sorunuz varsa, geçiş ekibimize şuradan ulaşabilirsiniz: [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="february-2017"></a>Şubat 2017

#### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Mobil cihaz kaydını kısıtlama özelliği <!--747600, 795782-->
Intune, katılmasına izin verilecek mobil cihaz platformlarını denetleyen yeni kayıt kısıtlamaları ekliyor. Intune, mobil cihaz platformlarını iOS, macOS, Android, Windows ve Windows Mobile şeklinde ayırıyor.

* Mobil cihaz kaydının kısıtlanması, bilgisayar istemcisi kaydını etkilemez.  
* Yalnızca iOS ve Android için kişisel cihazların kaydedilmesini engelleyen ek seçenek vardır.

Intune, BT yöneticileri [bu makalede](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices) anlatılan şekilde kuruluş cihazı olarak işaretlemediği sürece tüm yeni cihazları kişisel cihaz olarak işaretler.

#### <a name="view-all-actions-on-managed-devices---677150--"></a>Yönetilen cihazlardaki tüm eylemleri görüntüleme <!--677150-->
Yeni __Cihaz Eylemleri__ raporu cihazları fabrika ayarlarına sıfırlama gibi uzaktan gerçekleştirilen eylemleri kimin yaptığını ve ilgili eylemin durumunu göstermektedir.

#### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Yönetilmeyen cihazlar atanmış uygulamalara erişebilir <!--664691-->
Şirket Portalı web sitesinde yapılan tasarım değişikliklerinin bir parçası olarak iOS ve Android kullanıcılar yönetilmeyen cihazlarında kendilerine "kayıtsız kullanılabilir" olarak atanmış uygulamaları yükleyebilecek. Kullanıcılar Intune kimlik bilgilerini kullanarak Şirket Portalı web sitesine girebilecek ve kendilerine atanan uygulamaların listesini görebilecek. "Kayıtsız kullanılabilir" uygulamaların uygulama paketleri Şirket Portalı web sitesinden indirilebilir. Yükleme için kayıt gerektiren uygulamalar bu değişikten etkilenmeyecek ve bu uygulamaları yüklemek isteyen kullanıcılardan cihazlarını kaydetmeleri istenecektir.

#### <a name="custom-app-categories---748805--"></a>Özel uygulama kategorileri <!--748805-->
Artık Intune’a eklediğiniz uygulamalar için kategoriler oluşturabilir, düzenleyebilir ve atayabilirsiniz. Şu anda kategoriler yalnızca İngilizce olarak belirtilebilir.
Bkz. [Intune'a uygulama ekleme](/intune-azure/manage-apps/add-apps).

#### <a name="display-device-categories---814654--"></a>Cihaz kategorilerini görüntüleme <!--814654-->
Artık cihaz kategorisini cihaz listesinde ayrı bir sütunda görüntüleyebilirsiniz. Kategoriyi ayrıca cihaz özellikleri dikey penceresinin özellikler bölümünden de düzenleyebilirsiniz.

### <a name="january-2017"></a>Ocak 2017

#### <a name="custom-app-categories---748805--"></a>Özel uygulama kategorileri <!--748805-->
Artık Intune’a eklediğiniz uygulamalar için kategoriler oluşturabilir, düzenleyebilir ve atayabilirsiniz. Şu anda kategoriler yalnızca İngilizce olarak belirtilebilir.

#### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748803--"></a>Cihazlar kayıtlı olsa da olmasa da iş kolu uygulamaları atayın <!--748803-->
Artık, cihazları Intune’a kayıtlı olsun ya da olmasın, kullanıcılara mağazadan iş kolu uygulamaları atayabilirsiniz. Kullanıcıların cihazları Intune’a kayıtlı değilse yüklemek için Şirket Portalı uygulaması yerine Şirket Portalı web sitesine gitmeleri gerekir.

### <a name="december-2016"></a>Aralık 2016

#### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Azure portalının genel önizlemesinde telekom gider yönetimi tümleştirmesi<!--747605-->
Artık Azure portalında üçüncü taraf telekom gider yönetimi (TEM) hizmetleri ile tümleştirme önizlemesine başlıyoruz. Yurt içi verilerin ve dolaşım verilerinin kullanımına yönelik sınırlamalarını zorunlu olarak uygulamak için Intune'u kullanabilirsiniz. Bu tümleştirmelere [Saaswedo](http://www.saaswedo.com) ile başlıyoruz. Deneme kiracınızda bu özelliği etkinleştirmek için lütfen [Microsoft desteğe başvurun](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

### <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new-in-microsoft-intune.md).

