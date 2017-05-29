---
title: Yenilikler | Microsoft Docs
description: "Bu ayki ve geçmişteki Microsoft Intune sunumlarındaki yenilikleri öğrenin"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 2e6452a066aa7eaeb295a3b531d83dc3b632bcf5
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---
# <a name="whats-new-in-microsoft-intune---april-2017"></a>Microsoft Intune'daki yenilikler - Nisan 2017
Microsoft Intune’un bu sürümündeki yenilikleri öğrenin. Planlama yapmanız gereken yaklaşan değişiklikler hakkında ve geçmiş sunumlar hakkında bilgiler de alabilirsiniz.

> [!Note]
> Bu özelliklerin tümü, sonunda karma müşteri dağıtımlarında (Intune ile Configuration Manager) desteklenecektir. Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler sayfamızı](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) gözden geçirin.

## <a name="new-capabilities"></a>Yeni özellikler

### <a name="myapps-available-for-managed-browser---822308-822303--"></a>MyApps, Managed Browser ile kullanılabilir <!--822308, 822303-->

Managed Browser için Microsoft MyApps desteği geliştirildi. Yönetim hedefinde yer almayan Managed Browser kullanıcıları doğrudan MyApps hizmetine alınarak yöneticileri tarafından sağlanan SaaS uygulamalarına erişebilecekler. Intune yönetimi hedefinde yer alan kullanıcılar ise MyApps içeriğine yerleşik Managed Browser yer işaretinden erişim sağlayabilecekler.

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431-971473--"></a>Managed Browser ve Şirket Portalı için yeni simgeler <!--918433, 918431, 971473-->

Managed Browser uygulamasının hem Android hem de iOS sürümlerinin simgesi güncelleştiriliyor. Yeni simgede Enterprise Mobility + Security (EM+S) paketindeki diğer uygulamalarla tutarlı hale getirmek için güncelleştirilmiş Intune rozeti bulunacak. Managed Browser'ın yeni simgesini [Intune uygulama arabirimindeki yenilikler sayfasında](whats-new-in-intune-app-ui.md) görebilirsiniz.

Şirket Portalı uygulamasının da Android, iOS ve Windows sürümlerinin simgeleri EM+S paketindeki diğer uygulamalarla daha tutarlı hale getirilmek üzere güncelleştiriliyor. Bu simgeler nisan ayından başlayarak mayıs ayının sonuna kadar kademeli olarak kullanıma sunulacak.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Android Şirket Portalı uygulamasında oturum açma ilerleme göstergesi <!--953374-->

Android Şirket Portalı uygulamasında yapılan güncelleştirme ile kullanıcı uygulamayı başlattığında veya sürdürdüğünde oturum açma ilerleme göstergesi görüntüleniyor. Kullanıcının uygulamaya erişmesine izin verilmeden önce göstergede "Bağlanıyor..." ile başlayıp sırasıyla "Oturum açılıyor..." ve "Güvenlik gereksinimleri denetleniyor..."durumları gösteriliyor. Android için Şirket Portalı uygulamasının yeni ekran görüntülerini [Intune uygulaması kullanıcı arabirimindeki yenilikler sayfasında](whats-new-in-intune-app-ui.md) görebilirsiniz.

### <a name="block-apps-from-accessing-sharepoint-online----679339---"></a>Uygulamaların SharePoint Online’a erişmesini engelleyin <!-- 679339 -->

Uygulama koruma ilkelerinin uygulanmadığı uygulamaların [SharePoint Online](/intune-classic/deploy-use/mam-ca-for-sharepoint-online)’a erişmesini engellemek için artık uygulama tabanlı koşullu erişim ilkesi oluşturabilirsiniz. Uygulama tabanlı koşullu erişim senaryosunda, Azure portalını kullanarak SharePoint Online’a erişmesini istediğiniz uygulamaları belirtebilirsiniz.

### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>iOS Şirket Portalından iOS için Outlook uygulamasına çoklu oturum açma desteği <!--834012-->
Aynı cihazda aynı hesapla iOS için Şirket Portalı uygulamasında oturum açmış kullanıcıların artık Outlook uygulamasında oturum açmasına gerek yok. Kullanıcılar Outlook uygulamasını başlattıktan sonra hesaplarını seçip otomatik olarak oturum açabilecekler. Bu işlevi diğer Microsoft uygulamalarına da eklemek için çalışıyoruz.

### <a name="improved-status-messaging-in-the-company-portal-app-for-ios---744866--"></a>iOS için Şirket Portalı uygulamasında geliştirilmiş durum iletileri <!--744866-->
iOS için Şirket Portalı uygulamasında artık daha açıklayıcı hata iletileri görüntülenecek ve cihazlardaki gelişmeler hakkında daha açıklayıcı bilgiler verilecek. Bu hata durumları önceden "Şirket Portalı Geçici Olarak Devre Dışı" konulu genel bir hata iletisi içinde listeleniyordu. Ayrıca İnternet bağlantısı olmayan bir kullanıcı iOS üzerinde Şirket Portalı uygulamasını başlattığında ana sayfada "İnternet Bağlantısı Yok" yazan kalıcı bir durum çubuğu görecek.

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Geliştirilmiş Windows 10 Şirket Portalı uygulaması yükleme durumu <!--676495-->

Windows 10 Şirket Portalı uygulamasında başlatılan uygulama yüklemelerine yönelik geliştirmeler şunları içerir:
-    MSI paketleri için daha hızlı yükleme durumu raporlaması
-    Windows 10 Yıldönümü Güncelleştirmesi ve üzerini çalıştıran cihazlardaki modern uygulamalar için daha hızlı yükleme durumu raporlaması
-    Windows 10 Yıldönümü Güncelleştirmesi ve üzerini çalıştıran cihazlardaki modern uygulama yüklemeleri için yeni ilerleme çubuğu

Yeni ilerleme çubuğunu [Intune uygulama arabirimindeki yenilikler sayfasında](whats-new-in-intune-app-ui.md) görebilirsiniz.

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Windows 10 cihazlarını toplu kaydetme <!-- 747607 -->

Artık Azure AD kiracınız için Windows Configuration Designer /intune-classic/deploy-use/bulk-enroll-windows) ile Azure Active Directory ve Intune’da Windows 10 Creators Update’i çalıştıran çok sayıda cihazın arasına katılabilir, Windows Configuration Designer kullanarak Azure AD kiracınızda cihaz birleştiren bir sağlama paketi oluşturabilir ve bu paketi, toplu olarak kaydetmek ve yönetmek istediğiniz şirkete ait cihazlara uygulayabilirsiniz. Paket cihazlarınıza uygulandıktan sonra cihazlar Azure AD'ye katılır, Intune'a kaydolur ve Azure AD kullanıcılarınızın oturum açmasına hazır hale gelir.  Azure AD kullanıcıları, bu cihazlarda standart kullanıcılardır ve atanan ilkeleri ve gerekli uygulamaları alırlar. Self Servis ve Şirket Portalı senaryoları şu anda desteklenmiyor.

## <a name="notices"></a>Bildirimler

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Apple kayıt senaryolarına doğrudan erişim <!--951869-->

Intune, Azure Önizleme Portalı'ndaki Cihaz Kaydetme iş yükünü kullanarak Apple kayıt senaryolarına doğrudan erişimi Ocak 2017 sonrasında oluşturulan Intune hesapları için etkinleştirdi. Daha önce, Apple kayıt önizleme sürümüne yalnızca klasik Intune portalı bağlantıları ile erişilebiliyordu. Bu özelliklerin Azure’da kullanılabilmesi için, Ocak 2017 öncesi oluşturulan Intune hesaplarında tek seferlik bir geçiş yapılması gerekir. Geçiş için zaman çizelgesi henüz açıklanmamıştır, ancak konuya ilişkin ayrıntılar olabildiğince çabuk duyurulacaktır. Mevcut hesabınız önizleme sürümüne erişemiyorsa, yeni deneyimi test etmek için bir deneme hesabı oluşturmanızı kesinlikle öneririz.

### <a name="whats-coming-for-appx-in-intune-on-azure----1000270---"></a>Azure'da Intune Appx'leri için yenilikler <!-- 1000270 -->

Azure'da Intune'a geçişin bir parçası olarak üç appx değişikliği yapıyoruz:

1. Klasik Intune konsoluna yalnızca MDM kayıtlı cihazlara dağıtılabilen yeni bir appx uygulama türü ekliyoruz.
2. Var olan appx uygulama türünü yalnızca Intune PC aracısı ile yönetilen PC'lerin hedefleneceği şekilde değiştiriyoruz.
3. Var olan tüm appx'leri geçiş ile MDM appx'leri haline getiriyoruz.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?

Bu durum Intune PC aracısı üzerinden yönetilen mevcut cihazlarınızı etkilemeyecek. Ancak geçiş yapıldıktan sonra geçişi yapılan bu appx'leri Intune PC aracısı ile yönetilen ve daha önceden hedef alınmayan yeni cihazlara dağıtamayacaksınız.

#### <a name="what-action-do-i-need-to-take"></a>Ne yapmam gerekiyor?

Yeni PC dağıtımları gerçekleştirmek istiyorsanız geçiş işleminden sonra appx'i PC appx'i olarak yeniden yüklemeniz gerekecek. Daha fazla bilgi için Intune Destek ekibi blog sayfasındaki [Azure'da Intune Appx'lerinde yapılan değişiklikler](https://aka.ms/appxchange) konusuna bakın.  

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Azure’da Intune yönetici deneyiminin genel önizlemesindeki yenilikler<!--736542-->

2017 takvim yılının başlarında tam yönetici deneyimimizi Azure’a geçireceğiz. Bu sayede Grafik API’leri kullanılarak genişletilebilen modern bir hizmet platformunda çekirdek EMS iş akışlarının güçlü ve tümleşik yönetimi mümkün olacaktır.

Yeni deneme kiracıları, yeni yönetici deneyiminin genel önizlemesini bu ay Azure portalında görmeye başlayacaklar. Önizleme durumundayken, mevcut Intune konsolu ile gelen yetenekler ve eşlik, yinelemeli olarak sağlanır.

Azure portalındaki yönetici deneyimi, duyurulan yeni gruplandırma ve hedefleme işlevselliğini kullanır; mevcut kiracınız yeni gruplandırma deneyimine geçirildiğinde, siz de kiracınıza yönelik yeni yönetici deneyimini önizlemek üzere geçirilirsiniz. Bu sırada, kiracınız geçirilene kadar yeni işlevleri sınamak veya bunlara göz atmak isterseniz yeni bir Intune deneme hesabına kaydolun veya [yeni belgelere](/intune/whats-new) bakın.

> [!Note]
> Azure portalı önizlemesine yönelik güncelleştirmeleri bu ay yayımlıyoruz. Ancak, Intune hizmetinin kullanıma sunulma şekli nedeniyle değişiklikler hemen kullanılamayabilir.  Yeni portal özelliklerinin kullanılabilir hale gelmesi için önce hizmetin çeşitli bileşenlerinin sırasıyla güncelleştirilmesi gerekir. Ayın geri kalanında kullanıma sunuldukça Azure portal önizlemesindeki değişiklikleri fark edeceksiniz. Değişikliklerin tam listesi için bkz. [Microsoft Intune önizlemesindeki yenilikler](/intune/whats-new).

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Yönetim rolleri Azure portalında değiştiriliyor

Klasik Intune portalında (Silverlight) kullanılan mevcut mobil uygulama yönetimi (MAM) yönetim rolleri (Katkıda bulunan, Sahibi ve Salt okunur) yerine Intune Azure portalında yeni rol tabanlı yönetim denetimleri (RBAC) geliyor. Azure portalına geçiş yaptıktan sonra, yöneticilerinizi bu yeni yönetim rollerine yeniden atamanız gerekiyor. RBAC ve yeni roller hakkında daha fazla bilgi için bkz. [Microsoft Intune için rol tabanlı erişim denetimi](/intune/role-based-access-control).

## <a name="whats-coming"></a>Yakında

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Tüm platformlar için Şirket Portalı uygulamalarında gelişmiş oturum açma deneyimi <!--User Story 1132123-->

Android, iOS ve Windows için Intune Şirket Portalı uygulamalarında oturum açma deneyimini geliştirecek bir değişikliği önümüzdeki birkaç ay içinde piyasaya süreceğiz. Yeni kullanıcı deneyimi, Azure AD bu değişikliği gerçekleştirdiğinde Şirket Portalına yönelik tüm platformlarda görünecektir. Ayrıca, kullanıcılar artık tek kullanımlık bir kod ile başka bir cihazdan Şirket Portalında oturum açabilir. Bu, özellikle kullanıcıların kimlik bilgileri olmadan oturum açması gerektiğinde faydalıdır.

[Uygulamanın kullanıcı arabirimindeki yenilikler](whats-new-in-intune-app-ui.md) sayfasında, önceki oturum açma deneyiminin, kimlik bilgileriyle yeni oturum açma deneyiminin ve başka bir cihazdan yeni oturum açma deneyiminin ekran görüntülerini bulabilirsiniz.

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Değişiklik planı: Intune, Intune İş Ortağı Portalı deneyimini değiştiriyor <!-- 1050016 -->

2017 Mayıs ayı ortalarındaki hizmet güncelleştirmesinden başlayarak, manage.microsoft.com’dan Intune İş Ortağı sayfasını kaldırıyoruz.  

İş ortağı yöneticisiyseniz, artık Intune İş Ortağı sayfasında müşterileriniz adına görüntüleyemeyecek ve işlem yapamayacaksınız; bunun yerine Microsoft’taki diğer iki iş ortağı portalından birinde oturum açmanız gerekecektir.

Hem [Microsoft İş Ortağı Merkezi](https://partnercenter.microsoft.com/) hem de [Microsoft Office 365 İş Ortağı Yönetim Merkezi](https://portal.office.com/), yönettiğiniz müşteri hesaplarında oturum açmanıza olanak tanıyacaktır. İş ortağı olarak ilerlemek için, lütfen müşterilerinizi bu sitelerimizden birini kullanarak yönetin.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple, Uygulama Taşıma Güvenliği için güncelleştirmeler gerektirecek <!--748318-->

Apple, Uygulama Taşıma Güvenliği (ATS) için belirli gereksinimler uygulayacağını açıkladı. ATS, HTTPS üzerinden yapılan tüm uygulama iletişimlerinde daha sıkı güvenlik uygulamak için kullanılır. Bu değişiklik, iOS Şirket Portalı uygulamaları kullanan Intune müşterilerini etkiler.

Yeni ATS gereksinimlerinin kullanılmasını zorunlu kılan Apple TestFlight programı aracılığıyla iOS için Şirket Portalı uygulamasının yeni bir sürümünü kullanıma sunduk. ATS uyumluluğunuzu sınamak için bunu denemek isterseniz, adınızı, soyadınızı, e-posta adresinizi ve şirketinizin adını e-posta ile <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> adresine gönderin. Daha fazla ayrıntı için bkz. [Intune destek blogu](https://aka.ms/compportalats).

### <a name="see-also"></a>Ayrıca bkz.
* [Microsoft Intune Blogu](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform yol haritası](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Azure önizlemesindeki yenilikler](https://docs.microsoft.com/intune/whats-new)
* [Şirket Portalı kullanıcı arabirimindeki yenilikler](/intune-classic/whats-new/whats-new-in-company-portal-ui)
* [Yenilikler arşivi](whats-new-archive.md)

