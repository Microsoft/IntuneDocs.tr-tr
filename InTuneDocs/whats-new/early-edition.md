---
title: "Erken Sürüm | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 18d47678b0fbdbd98502f2d3b469b202b567b2e7
ms.openlocfilehash: 3c7edc236878232c6f4c0ae993733c967946e765


---

# <a name="the-early-edition-for-microsoft-intune---january"></a>Microsoft Intune için Erken Sürüm - Ocak

**Erken Sürüm** Microsoft Intune'un gelecek sürümlerinde kullanıma sunulacak yeni özelliklerin bir listesini sağlar. Bu bilgiler NDA kapsamında çok sınırlı bir temelde sağlanır ve değiştirilebilir. Burada listelenen özelliklerden bazılarının son tarihe yetişememe riski vardır ve gelecek sürüme ertelenebilir. Diğer özellikler, müşterinin kullanımına hazır olduğundan emin olmak için pilot (sürüyor) aşamasında test edilmektedir. Sorularınız veya kaygılarınız varsa lütfen Intune/PM arkadaşınıza ulaşın.

Bu sayfa düzenli aralıklarla güncelleştirilir. Ek güncelleştirmeleri daha sonra denetleyin.

> [!Note]
> Intune için aşağıdaki değişiklikler geliştirilme aşamasındadır. Bu özelliklerin tümü, sonunda karma müşteri dağıtımlarında (Intune ile Configuration Manager) desteklenecektir. Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler sayfamızı](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) gözden geçirin.

## <a name="new-capabilities"></a>Yeni Özellikler

### <a name="actions-for-non-compliance---730266--"></a>Uyumsuzluk için eylemler <!--730266-->
_Uyumsuzluk için eylemler_ uyumsuz cihazlar üzerinde eylem gerçekleştirmenize olanak tanıyan yeni bir uyumluluk ilkeleri özelliğidir. Tek veya birden çok eylem belirtebilir ve bu eylemlerin gerçekleştirilmesi gereken zaman aralığını belirtebilirsiniz. Örneğin, uyumsuz cihaz kullanıcılarını cihazlar uyumsuz hale geldiği anda e-posta yoluyla haberdar edebilir veya Koşullu Erişim aracılığıyla 3 günlük yetkisiz kullanım süresi ardından uyumsuz cihazların kurumsal kaynaklara erişimini engelleyebilirsiniz.

### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>Kayıtsız MAM için konsol içi raporlar <!--677961-->
Hem kayıtlı hem kayıtlı olmayan cihazlar için yeni uygulama koruma raporları eklenmiştir. [Intune ile mobil uygulama yönetimi ilkelerini nasıl izleyebileceğinizi buradan](https://docs.microsoft.com/en-us/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune) öğrenebilirsiniz.

### <a name="conditional-access-for-mam-with-sharepoint-online---679339--"></a>SharePoint Online ile MAM için koşullu erişim <!--679339-->
Intune mobil uygulama yönetimi (MAM) ilkeleri tarafından desteklenmeyen uygulamaların SharePoint Online’a erişmesini engelleyebilirsiniz.  Azure portalında Intune mobil uygulama yönetimini kullanarak başlayabilirsiniz. __Ayarlar__ dikey penceresinde SharePoint Online ile ilgili seçeneği içeren __Koşullu Erişim__ kısmını arayın. Bu özellik, hizmet sürümünün geri kalanından ayrı olarak sevk edilir. <!--Find out more about this new feature [here](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-sharepoint-online).-->

### <a name="android-711-support---694397--"></a>Android 7.1.1 desteği <!--694397-->
Intune artık Android 7.1.1 sürümünü tam olarak destekler ve yönetir.

## <a name="notices"></a>Bildirimler

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Windows masaüstü cihazları Windows ayarları aracılığıyla yönetmek varsayılanlara sıfırlıyor <!--663050-->
Windows 10 masaüstü cihazları kaydetmek için varsayılan davranış değişiyor. Yeni kayıtlar artık bilgisayar aracısı üzerinden değil, tipik MDM aracısı kayıt akışını izleyerek yapılacaktır.

Şirket Portalı web sitesi, Windows 10 masaüstü kullanıcılarına Windows 10 masaüstü bilgisayarları mobil cihaz olarak ekleme işlemi için yönergeler sağlayacak kayıt yönergeleri temin edecektir. Bu, zaten kayıtlı olan bilgisayarları etkilemez ve [tercihe göre](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune) kuruluşunuz bilgisayar aracısını kullanarak Windows 10 masaüstü cihazları yönetmeye devam edebilir.

### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>iOS için Şirket Portalı bağlantıları uygulamanın içinde açılır <!--665954-->
Belge ve uygulamalara yönlendirilen bağlantılar da dahil olmak üzere iOS için Şirket Portalı uygulaması içinde bulunan bağlantılar, Safari’nin uygulama içi görünümü kullanılarak doğrudan Şirket Portalı uygulamasında açılır. Bu güncelleştirme Ocak’taki hizmet güncelleştirmesinden ayrı olarak sevk edilir.

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Seçici silme için mobil uygulama yönetimi desteğini iyileştirme <!--581242-->
Bu verilerin "Uygulama verileri silinmeden önce çevrimdışı zaman aralığı" ilkesi nedeniyle otomatik olarak kaldırılması durumunda, son kullanıcılara iş veya okul verilerine yeniden erişim sağlama konusunda ek yönergeler verilir.<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="new-documentation-for-app-protection-policies---583398--"></a>Uygulama koruma ilkeleri için yeni belgeler <!--583398-->
Intune Uygulama Sarmalama Aracı veya Intune Uygulama SDK’sı kullanarak iOS ve Android uygulamalarında uygulama koruma ilkelerini (MAM ilkeleri olarak da bilinir) etkinleştirmek isteyen yöneticiler ve uygulama geliştiricilerine yönelik belgelerimizi güncelleştirdik.

Aşağıdaki makaleler güncelleştirilmiştir:

* [Microsoft Intune ile uygulamaların mobil uygulama yönetimi için nasıl hazırlanacağına karar verme](https://docs.microsoft.com/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
* [Intune Uygulama Sarmalama Aracı ile iOS uygulamalarını mobil uygulama yönetimi için hazırlama](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
* [Microsoft Intune Uygulama SDK’sını kullanmaya başlayın](https://docs.microsoft.com/intune/develop/intune-app-sdk-get-started)
* [iOS için Intune Uygulama SDK’sı geliştirici kılavuzu](https://docs.microsoft.com/intune/develop/intune-app-sdk-ios)

Aşağıdaki makaleler belgeler kitaplığına yeni eklenmiştir:

* [Intune Uygulama SDK’sı Cordova Eklentisi](https://docs.microsoft.com/intune/develop/intune-app-sdk-cordova)
* [Intune Uygulama SDK’sı Xamarin Bileşeni](https://docs.microsoft.com/intune/develop/intune-app-sdk-xamarin)

### <a name="progress-bar-when-launching-the-company-portal-on-ios---665978--"></a>iOS’ta Şirket Portalını başlatılırken ilerleme çubuğu <!--665978-->
iOS için Şirket Portalı, kullanıcıya gerçekleşen yükleme işlemleri hakkında bilgi sağlamak için başlatma ekranında bir ilerleme çubuğu yeniliği sunuyor. Değer değiştiricinin yerini alması için ilerleme çubuğunun aşamalı dağıtımı yapılacaktır. Yani bazı kullanıcılarınız yeni ilerleme çubuğunu görecek, diğerleri ise değer değiştiriciyi görmeye devam edecektir.

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Azure’daki yeni Intune yönetici deneyiminin genel önizlemesi <!--736542-->

2017 takvim yılının başlarında tam yönetici deneyimimizi Azure’a geçireceğiz. Bu sayede Grafik API’leri kullanılarak genişletilebilen modern bir hizmet platformunda çekirdek EMS iş akışlarının güçlü ve tümleşik yönetimi mümkün olacaktır.

Yeni deneme kiracıları, yeni yönetici deneyiminin genel önizlemesini bu ay Azure portalında görmeye başlayacaklar. Önizleme durumundayken, mevcut Intune konsolu ile gelen yetenekler ve eşlik, yinelemeli olarak sağlanır.

Azure portalındaki yönetici deneyimi, duyurulan yeni gruplandırma ve hedefleme işlevselliğini kullanır; mevcut kiracınız yeni gruplandırma deneyimine geçirildiğinde, siz de kiracınıza yönelik yeni yönetici deneyimini önizlemek üzere geçirilirsiniz. Bu sırada, kiracınız geçirilene kadar yeni işlevleri sınamak veya bunlara göz atmak isterseniz yeni bir Intune deneme hesabına kaydolun veya [yeni belgelere](https://docs.microsoft.com/en-us/intune-azure/introduction/what-is-microsoft-intune) bakın.

Kiracınızın geçişinin zaman çizelgesi hakkında sorunuz varsa, geçiş ekibimize şuradan ulaşabilirsiniz: [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

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



<!--HONumber=Dec16_HO4-->


