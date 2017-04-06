---
title: Yenilikler | Microsoft Docs
description: "Bu ayki ve geçmişteki Microsoft Intune sunumlarındaki yenilikleri öğrenin"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: c473a1f05b0a7b0ce5205598b2b9a9b86bfe6c1d
ms.openlocfilehash: bddd8c0dc74835f74a71af1d900d43d84aab894c
ms.lasthandoff: 03/29/2017


---
# <a name="whats-new-in-microsoft-intune---march-2017"></a>Microsoft Intune'daki yenilikler - Mart 2017
Microsoft Intune’un bu sürümündeki yenilikleri öğrenin. Planlama yapmanız gereken yaklaşan değişiklikler hakkında ve geçmiş sunumlar hakkında bilgiler de alabilirsiniz.

> [!Note]
> Bu özelliklerin tümü, sonunda karma müşteri dağıtımlarında (Intune ile Configuration Manager) desteklenecektir. Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler sayfamızı](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) gözden geçirin.

## <a name="new-capabilities"></a>Yeni Özellikler

### <a name="support-for-skycure"></a>Skycure desteği

Artık Microsoft Intune ile tümleşik çalışan mobil tehdit savunması çözümü Skycure tarafından gerçekleştirilen risk değerlendirmesine dayalı koşullu erişimi kullanarak mobil cihazlardan şirket kaynaklarına erişimi denetleyebilirsiniz. Risk, Skycure çalıştıran cihazlardan toplanan ve aşağıdakileri içeren telemetriye göre değerlendirilir:

- Fiziksel savunma
- Ağ savunması
- Uygulama savunması
- Güvenlik açıkları savunması

Intune cihaz uyumluluk ilkeleri ile etkinleştirilen Skycure risk değerlendirmesine dayalı olarak EMS koşullu erişim ilkelerini yapılandırabilirsiniz. Algılanan tehditlere dayalı olarak uyumsuz cihazların şirket kaynaklarına erişimine izin vermek ya da erişimi engellemek için bu ilkeleri kullanabilirsiniz. Daha fazla bilgi için bkz. [Skycure Mobile Threat Defense bağlayıcısı](/intune/deploy-use/skycure-mobile-threat-defense-connector).

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Android Şirket Portalı uygulaması için yeni kullanıcı deneyimi <!--621622-->

Android için Şirket Portalı uygulamasının kullanıcı arabirimi daha modern görünüm ve daha iyi kullanıcı deneyimi için güncelleştiriliyor. Önemli güncelleştirmeler şunlardır:

- Renkler: Şirket Portalı sekmesinin üstbilgileri BT tarafından tanımlanan marka rengindedir.
- Uygulamalar: **Uygulamalar** sekmesindeki **Öne Çıkan Uygulamalar** ve **Tüm Uygulamalar** düğmeleri güncelleştirildi.
- Arama: **Uygulamalar** sekmesinde, **Arama** düğmesi kayan eylem düğmesi şeklinde.
- Uygulamalarda Gezinme: **Tüm Uygulamalar** görünümü daha kolay gezinme için **Öne Çıkan Uygulamalar**, **Tüm Uygulamalar** ve **Kategoriler** bölümlerini sekmeler halinde gösterir.
- Destek: **Cihazlarım** ve **BT İletişim** sekmeleri okunabilirliği artırmak için güncelleştirildi.

Bu değişiklikler hakkında daha ayrıntılı bilgi için bkz. [Intune son kullanıcı uygulamaları için kullanıcı arabirimi güncelleştirmeleri](whats-new-in-intune-app-ui.md).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Yönetilmeyen cihazlar atanmış uygulamalara erişebilir <!--664691-->

Şirket Portalı web sitesinde yapılan tasarım değişikliklerinin bir parçası olarak iOS ve Android kullanıcılar yönetilmeyen cihazlarında kendilerine "kayıtsız kullanılabilir" olarak atanmış uygulamaları yükleyebilecek. Kullanıcılar Intune kimlik bilgilerini kullanarak Şirket Portalı web sitesine girebilecek ve kendilerine atanan uygulamaların listesini görebilecek. "Kayıtsız kullanılabilir" uygulamaların uygulama paketleri Şirket Portalı web sitesinden indirilebilir. Yükleme için kayıt gerektiren uygulamalar bu değişikten etkilenmeyecek ve bu uygulamaları yüklemek isteyen kullanıcılardan cihazlarını kaydetmeleri istenecektir.

### <a name="signing-script-for-windows-10-company-portal---941642--"></a>Windows 10 Şirket Portalı için İmzalama Betiği <!--941642-->

Windows 10 Şirket Portalı uygulamasını indirmeniz ve dışarıdan yüklemeniz gerekiyorsa, artık bir betik kullanarak uygulama imzalama işlemini kuruluşunuz için basitleştirebilir ve kolaylaştırabilirsiniz.   Betiği indirmek ve kullanma yönergelerine göz atmak için TechNet Galerisi’ndeki [Windows 10 Şirket Portalı için Microsoft Intune İmzalama Betiği](https://aka.ms/win10cpscript) makalesine bakın. Bu duyuru hakkında daha ayrıntılı bilgi edinmek için Intune Destek Ekibi Blogundaki [Windows 10 Şirket Portalı uygulamanızı güncelleştirme](https://blogs.technet.microsoft.com/intunesupport/2017/03/13/updating-your-windows-10-company-portal-app/) yazısına bakın.


## <a name="notices"></a>Bildirimler

### <a name="support-for-ios-103"></a>iOS 10.3 desteği

iOS 10.3 sürümü 27 Mart 2017 tarihinden itibaren iOS kullanıcılarına sunulmaya başlandı. Mevcut tüm Intune MDM ve MAM senaryoları Apple’ın en son işletim sistemi ile uyumludur. Kullanıcılarınız cihazlarını ve uygulamalarını iOS 10.3 sürümüne yükselttiklerinde, şu anda iOS cihazlarını yönetmeye dair mevcut tüm Intune özelliklerinin sorunsuz bir şekilde çalışmaya devam etmesini bekliyoruz.

Şu anda bilinen bir sorun yoktur. iOS 10.3 ile ilgili soruna karşılaşırsanız lütfen [Intune destek ekibine](/intune/troubleshoot/contact-assisted-phone-support-for-microsoft-intune) ulaşın.

### <a name="improved-support-for-android-users-based-in-china---720444--"></a>Çin'de bulunan Android kullanıcıları için gelişmiş destek <!--720444-->

Çin’de Google Play Mağazası olmaması nedeniyle, Android cihazlarının uygulamaları Çin’deki uygulama mağazalarından edinmeleri gerekir. Şirket Portalı, Çin’deki Android kullanıcılarını Şirket Portalı ve Outlook uygulamalarını yerel mağazalardan yüklemeleri için yeniden yönlendirerek bu iş akışını destekler. Bu, Koşullu Erişim ilkeleri, mobil aygıt yönetimi ve mobil uygulama yönetimi için etkinleştirildiğinde, kullanıcı deneyimini geliştirir. Android için Şirket Portalı ve Outlook uygulamaları aşağıdaki Çin uygulama mağazalarında bulunabilir:

- [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
- [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)
- [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
- [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
- [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)

### <a name="best-practice-make-sure-your-company-portal-apps-are-up-to-date---879465--"></a>En iyi uygulama: Şirket Portalı uygulamalarınızın güncel olduğundan emin olun <!--879465-->

Aralık 2016’da, iOS, Android, Windows 8.1+ veya Windows Phone 8.1+ cihazı kaydeden bir grup kullanıcı için çok faktörlü kimlik doğrulamasının (MFA) zorlanmasını sağlayan bir güncelleştirme yayımladık. Bu özellik, Android (v5.0.3419.0+) ve iOS (v2.1.17+) için Şirket Portalı uygulamasının belirli temel sürümleri olmadan çalışamaz.

Microsoft, Intune’u sürekli olarak geliştirmek amacıyla hem konsola hem de Şirket Portalı uygulamasına tüm desteklenen platformlarda yeni işlevler ekliyor. Bunun sonucunda, Microsoft yalnızca Şirket Portalı uygulamasının geçerli sürümünde karşılaşılan sorunlara yönelik düzeltmeler yayımlamaktadır. Bu nedenle, en iyi kullanıcı deneyiminden yararlanabilmeniz için Şirket Portalı uygulamalarının en son sürümlerini kullanmanızı öneririz.

>[!Tip]
> Kullanıcılarınızın, cihazlarında uygulamaları ilgili uygulama mağazasından otomatik olarak güncelleştirecek şekilde ayarlamalar yapmasını sağlayın. Android Şirket Portalı uygulamasını bir ağ paylaşımında kullanıma sunduysanız en son sürümü [Microsoft İndirme Merkezi](https://www.microsoft.com/download/details.aspx?id=49140)’nden indirebilirsiniz.

### <a name="microsoft-teams-is-now-enabled-for-mam-on-ios-and-android"></a>Microsoft Teams artık iOS ve Android’de MAM özelliğini kullanabiliyor

Microsoft, Microsoft Teams’in genel kullanıma sunulduğunu açıkladı. iOS ve Android için güncelleştirilmiş Microsoft Teams uygulamaları artık Intune mobil uygulama yönetimi (MAM) özelliklerine sahip olduğundan ekiplerinizin tüm cihazlarda rahatça çalışmasına olanak tanıyıp bir yandan da görüşmeleri ve kurumsal verileri her aşamada koruyabilirsiniz. Daha ayrıntılı bilgi edinmek için Enterprise Mobility and Security blogundaki [Microsoft Teams duyurusuna](https://blogs.technet.microsoft.com/enterprisemobility/2017/03/14/microsoft-teams-is-now-generally-available-and-mam-enabled-on-ios-and-android/) bakın.


## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Azure’da Intune yönetici deneyiminin genel önizlemesindeki yenilikler<!--736542-->

2017 takvim yılının başlarında tam yönetici deneyimimizi Azure’a geçireceğiz. Bu sayede Grafik API’leri kullanılarak genişletilebilen modern bir hizmet platformunda çekirdek EMS iş akışlarının güçlü ve tümleşik yönetimi mümkün olacaktır.

Yeni deneme kiracıları, yeni yönetici deneyiminin genel önizlemesini bu ay Azure portalında görmeye başlayacaklar. Önizleme durumundayken, mevcut Intune konsolu ile gelen yetenekler ve eşlik, yinelemeli olarak sağlanır.

Azure portalındaki yönetici deneyimi, duyurulan yeni gruplandırma ve hedefleme işlevselliğini kullanır; mevcut kiracınız yeni gruplandırma deneyimine geçirildiğinde, siz de kiracınıza yönelik yeni yönetici deneyimini önizlemek üzere geçirilirsiniz. Bu sırada, kiracınız geçirilene kadar yeni işlevleri sınamak veya bunlara göz atmak isterseniz yeni bir Intune deneme hesabına kaydolun veya [yeni belgelere](/intune-azure/introduction/whats-new) bakın.

> [!Note]
> Azure portalı önizlemesine yönelik güncelleştirmeleri bu ay yayımlıyoruz. Ancak, Intune hizmetinin kullanıma sunulma şekli nedeniyle değişiklikler hemen kullanılamayabilir.  Yeni portal özelliklerinin kullanılabilir hale gelmesi için önce hizmetin çeşitli bileşenlerinin sırasıyla güncelleştirilmesi gerekir. Ayın geri kalanında kullanıma sunuldukça Azure portal önizlemesindeki değişiklikleri fark edeceksiniz. Değişikliklerin tam listesi için bkz. [Microsoft Intune önizlemesindeki yenilikler](/intune-azure/introduction/whats-new).

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Yönetim rolleri Azure portalında değiştiriliyor

Klasik Intune portalında (Silverlight) kullanılan mevcut mobil uygulama yönetimi (MAM) yönetim rolleri (Katkıda bulunan, Sahibi ve Salt okunur) yerine Intune Azure portalında yeni rol tabanlı yönetim denetimleri (RBAC) geliyor. Azure portalına geçiş yaptıktan sonra, yöneticilerinizi bu yeni yönetim rollerine yeniden atamanız gerekiyor. RBAC ve yeni roller hakkında daha fazla bilgi için bkz. [Microsoft Intune için rol tabanlı erişim denetimi](/intune-azure/access-control/role-based-access-control).


## <a name="whats-coming"></a>Yakında

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple, Uygulama Taşıma Güvenliği için güncelleştirmeler gerektirecek <!--748318-->

Apple, 2017 baharından itibaren, Uygulama Taşıma Güvenliği (ATS) için belirli gereksinimler uygulayacağını açıkladı. ATS, HTTPS üzerinden yapılan tüm uygulama iletişimlerinde daha sıkı güvenlik uygulamak için kullanılır. Bu değişiklik, iOS Şirket Portalı uygulamaları kullanan Intune müşterilerini etkiler. Daha fazla ayrıntı için bkz. [Intune destek blogu](https://aka.ms/compportalats).

### <a name="see-also"></a>Ayrıca bkz.
* [Microsoft Intune Blogu](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform yol haritası](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Azure önizlemesindeki yenilikler](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Şirket Portalı kullanıcı arabirimindeki yenilikler](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Yenilikler arşivi](whats-new-archive.md)

