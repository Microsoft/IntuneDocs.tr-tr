---
title: Yenilikler | Microsoft Docs
description: "Bu ayki ve geçmişteki Microsoft Intune sunumlarındaki yenilikleri öğrenin"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: a9336e3d230de962d2623dd627e45c6e9262a822
ms.openlocfilehash: cfe4a0bb802956278387ac2a39d5316482e09332
ms.lasthandoff: 03/02/2017


---
# <a name="whats-new-in-microsoft-intune---february-2017"></a>Microsoft Intune'daki yenilikler - Şubat 2017
Microsoft Intune’un bu sürümündeki yenilikleri öğrenin. Planlama yapmanız gereken yaklaşan değişiklikler hakkında ve geçmiş sunumlar hakkında bilgiler de alabilirsiniz.

> [!Note]
> Bu özelliklerin tümü, sonunda karma müşteri dağıtımlarında (Intune ile Configuration Manager) desteklenecektir. Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler sayfamızı](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) gözden geçirin.

## <a name="new-capabilities"></a>Yeni Özellikler

### <a name="modernizing-the-company-portal-website---753980--"></a>Şirket Portalı web sitesi modernleştiriliyor <!--753980-->
Şirket Portalı web sitesi, yönetilen cihazlara sahip olmayan kullanıcıları hedefleyen uygulamaları destekleyecek. Karşıt renklerden oluşan yeni renk düzeni ve dinamik çizimlerle yeniden tasarlanan web sitesi, yardım masası ilgili kişisine ilişkin ayrıntıların yanı sıra yönetilen mevcut cihazlara yönelik bilgilerin bulunduğu bir "hamburger menüsü" ![Şirket Portalı web sitesinin sol üst köşesine eklenmiş olan hamburger menüsünün küçük resmi](./media/CP_hamburger_menu.png) eklenerek diğer Microsoft ürün ve hizmetleriyle uyumlu hale getirilecek. Kullanıcılara sunulan uygulamaları vurgulayacak şekilde yeniden düzenlenecek olan giriş sayfasında, Öne Çıkan ve Son Güncelleştirilen uygulamaların görüntülendiği döngüler yer alacak. Önce ve sonra görüntülerini [UI güncelleştirmeleri sayfasında](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui) bulabilirsiniz.

### <a name="new-guided-experience-for-windows-10-company-portal---713927--"></a>Windows 10 Şirket Portalı için kullanıcının yönlendirildiği yeni deneyim <!--713927-->
Mart ayından başlayarak, Windows 10 için Şirket Portalı tanımlanmamış veya kaydedilmemiş cihazlar için kullanıcının yönlendirildiği adım adım bir Intune deneyimi içerecektir. Yeni deneyimde, kullanıcılara AAD kaydını (Koşullu Erişim özelliklerinde tanımlama için gerekli) ve MDM kaydını (cihaz yönetim özellikleri için gerekli) gerçekleştirme işlemlerinde kullanıcılara yol gösteren, kullanıcının Windows 10 derlemesi için özelleştirilmiş adım adım yönergeler sağlanır. Kullanıcıya yol gösteren deneyime Şirket Portalı giriş sayfasından erişilebilir ve bu deneyim isteğe bağlıdır; kayıtları tamamlamayan kullanıcılar uygulamayı kullanmaya devam edebilir, ancak sınırlı işlevsellikle karşılaşabilir.

## <a name="notices"></a>Bildirimler

### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>Grup geçişi için iOS cihazlarda grup veya ilke güncelleştirmesi gerekmeyecek <!--898837-->
Azure Active Directory cihaz gruplarına geçiş sırasında, önceden bir Şirket Cihaz Kaydı profili tarafından atanmış olan her Intune cihaz grubu için Şirket Cihaz Kaydı profilinin adına göre AAD'de karşılık gelen bir dinamik cihaz grubu oluşturulacaktır. Bu sayede kaydı yapılan cihazların otomatik olarak gruplanması ve özgün Intune grubundakilerle aynı ilkeleri ve uygulamaları alması sağlanacaktır.

Bir kiracı gruplama ve hedefleme için geçiş işlemine girdiğinde Intune, otomatik olarak Şirket Cihaz Kaydı profili tarafından hedeflenen Intune grubuna karşılık gelecek bir dinamik AAD grubu oluşturacaktır. Intune Yöneticisinin hedef Intune grubunu silmesi halinde karşılık gelen dinamik AAD grubu silinmeyecektir. Grubun üyeleri ve dinamik sorgu silinecek ancak BT Yöneticisi AAD portalı üzerinden kaldırılana kadar grubun kendisi kalacaktır.

Benzer şekilde, BT Yöneticisinin bir Şirket Cihaz Kaydı profili ile hedeflenen Intune grubunu değiştirmesi halinde, Intune yeni profil atamasını yansıtan yeni bir dinamik grup oluşturacak ancak eski atama için oluşturulan dinamik grubu kaldırmayacaktır.

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Windows masaüstü cihazları Windows ayarları aracılığıyla yönetmek varsayılanlara sıfırlıyor <!--663050-->
Windows 10 masaüstü cihazları kaydetmek için varsayılan davranış değişiyor. Yeni kayıtlar artık bilgisayar aracısı üzerinden değil, tipik MDM aracısı kayıt akışını izleyerek yapılacaktır. Şirket Portalı web sitesi, Windows 10 masaüstü kullanıcılarına Windows 10 masaüstü bilgisayarları mobil cihaz olarak ekleme işlemi için yönergeler sağlayacak kayıt yönergeleri temin edecektir. Bu, zaten kayıtlı olan bilgisayarları etkilemez ve [tercihe göre](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune) kuruluşunuz bilgisayar aracısını kullanarak Windows 10 masaüstü cihazları yönetmeye devam edebilir.

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Seçici silme için mobil uygulama yönetimi desteğini iyileştirme <!--581242-->
Bu verilerin "Uygulama verileri silinmeden önce çevrimdışı zaman aralığı" ilkesi nedeniyle otomatik olarak kaldırılması durumunda, son kullanıcılara iş veya okul verilerine yeniden erişim sağlama konusunda ek yönergeler verilir.<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>iOS için Şirket Portalı bağlantıları uygulamanın içinde açılır <!--665954-->
Belge ve uygulamalara yönlendirilen bağlantılar da dahil olmak üzere iOS için Şirket Portalı uygulaması içinde bulunan bağlantılar, Safari’nin uygulama içi görünümü kullanılarak doğrudan Şirket Portalı uygulamasında açılır. Bu güncelleştirme Ocak’taki hizmet güncelleştirmesinden ayrı olarak sevk edilir.

### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Windows cihazları için yeni MDM sunucusu adresi <!--893007-->
MDM sunucusu adresi olarak __manage.microsoft.com__ giren (sorulursa) Windows ve Windows Phone kullanıcıları, cihaz kaydetmeye çalıştıklarında başarısız olacaklardır. MDM sunucusu adresi __manage.microsoft.com__ yerine __enrollment.manage.microsoft.com__ olarak değiştirilmektedir. Kullanıcılarınızı, Windows veya Windows Phone cihazı kaydetmeye çalışırken sorulması halinde MDM sunucusu adresi olarak __enrollment.manage.microsoft.com__ girmeleri konusunda bilgilendirin. CNAME kurulumunuzda herhangi bir değişiklik gerekmez. Bu değişiklik hakkında daha fazla bilgi için [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange) adresini ziyaret edin.

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Android Şirket Portalı uygulaması için yeni kullanıcı deneyimi <!--621622-->
Mart ayından itibaren Android Şirket Portalı uygulaması [Material Design kılavuzuna](https://material.io/guidelines/material-design/introduction.html) uygun olarak modern bir tasarıma sahip olacak. Bu gelişmiş kullanıcı deneyimi şunları içeriyor olacak:

* __Renkler__: Sekme başlıklarının renkleri özel renk paletinize göre değiştirilebilir.
* __Arabirim__: Uygulamalar sekmesindeki Öne Çıkan Uygulamalar ve Tüm Uygulamalar düğmeleri güncelleştirildi. Arama düğmesi artık kayan eylem düğmesi şeklinde.
* __Gezinti__: Tüm Uygulamalar sayfasında daha kolay gezinme için Öne Çıkan Uygulamalar, Tüm Uygulamalar ve Kategoriler sekmeler halinde görüntüleniyor.
* __Hizmet__: Cihazlarım ve BT'ye Başvur sekmelerinin okunabilirliği geliştirildi.

Önce ve sonra görüntülerini [UI güncelleştirmeleri sayfasında](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui) bulabilirsiniz.

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>İş İçin Windows Mağazası’yla birden çok yönetim aracını ilişkilendirme<!--926135-->
İş İçin Windows Mağazası uygulamalarını dağıtmak için birden fazla yönetim aracı kullanmanız durumunda önceden bunların yalnızca birini İş İçin Windows Mağazası ile ilişkilendirebiliyordunuz. Artık mağaza ile Intune ve Configuration Manager gibi birden fazla yönetim aracını ilişkilendirebilirsiniz. Ayrıntılar için bkz. [Microsoft Intune ile İş İçin Windows Mağazası'ndan satın aldığınız uygulamaları yönetme](https://docs.microsoft.com/en-us/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune).

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Azure’da Intune yönetici deneyiminin genel önizlemesindeki yenilikler<!--736542-->

2017 takvim yılının başlarında tam yönetici deneyimimizi Azure’a geçireceğiz. Bu sayede Grafik API’leri kullanılarak genişletilebilen modern bir hizmet platformunda çekirdek EMS iş akışlarının güçlü ve tümleşik yönetimi mümkün olacaktır.

Yeni deneme kiracıları, yeni yönetici deneyiminin genel önizlemesini bu ay Azure portalında görmeye başlayacaklar. Önizleme durumundayken, mevcut Intune konsolu ile gelen yetenekler ve eşlik, yinelemeli olarak sağlanır.

Azure portalındaki yönetici deneyimi, duyurulan yeni gruplandırma ve hedefleme işlevselliğini kullanır; mevcut kiracınız yeni gruplandırma deneyimine geçirildiğinde, siz de kiracınıza yönelik yeni yönetici deneyimini önizlemek üzere geçirilirsiniz. Bu sırada, kiracınız geçirilene kadar yeni işlevleri sınamak veya bunlara göz atmak isterseniz yeni bir Intune deneme hesabına kaydolun veya [yeni belgelere](https://docs.microsoft.com/intune-azure/introduction/whats-new) bakın.

Kiracınızın geçişinin zaman çizelgesi hakkında sorunuz varsa, geçiş ekibimize şuradan ulaşabilirsiniz: [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

Azure’da Intune önizlemesindeki yenilikleri [buradan](https://docs.microsoft.com/intune-azure/introduction/whats-new) bulabilirsiniz.

## <a name="whats-coming"></a>Yakında

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple, Uygulama Taşıma Güvenliği için güncelleştirmeler gerektirecek <!--748318-->

Apple, 2017 baharından itibaren, Uygulama Taşıma Güvenliği (ATS) için belirli gereksinimler uygulayacağını açıkladı. ATS, HTTPS üzerinden yapılan tüm uygulama iletişimlerinde daha sıkı güvenlik uygulamak için kullanılır. Bu değişiklik, iOS Şirket Portalı uygulamaları kullanan Intune müşterilerini etkiler. Daha fazla ayrıntı için bkz. [Intune destek blogu](https://aka.ms/compportalats). 

### <a name="see-also"></a>Ayrıca bkz.
* [Microsoft Intune Blogu](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform yol haritası](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Azure önizlemesindeki yenilikler](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Şirket Portalı kullanıcı arabirimindeki yenilikler](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Yenilikler arşivi](whats-new-archive.md)

