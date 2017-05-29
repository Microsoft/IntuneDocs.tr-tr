---
title: "MAM ve uygulama koruma hakkında sık kullanılan sorular"
description: "Bu makalede, Intune mobil uygulama yönetimi (MAM) ve Intune uygulama koruma hakkında sık sorulan sorulardan bazıları yanıtlanmaktadır."
keywords: 
author: oydang
ms.author: oydang
manager: mtillman
ms.date: 01/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 149def73-9d08-494b-97b7-4ba1572f0623
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 32446d9a6f9383b5449dbabf288b0eac0b483ebb
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="frequently-asked-questions-about-mam-and-app-protection"></a>MAM ve uygulama koruma hakkında sık kullanılan sorular

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bu makalede, Intune mobil uygulama yönetimi (MAM) ve Intune uygulama koruma hakkında sık sorulan sorulardan bazıları yanıtlanmaktadır.

## <a name="mam-basics"></a>MAM Temel Kavramları


**MAM nedir?** [Intune mobil uygulama yönetimi](../deploy-use/overview-of-app-lifecycle-in-microsoft-intune.md), kullanıcılarınız için mobil uygulamaları yayımlama, gönderme, yapılandırma, güvenlik altına alma, izleme ve güncelleştirme gibi eylemler gerçekleştirmenize olanak tanıyan Intune yönetim özellikleri paketini ifade eder.

**MAM uygulama korumanın avantajları nedir?** MAM, bir uygulama içindeki kuruluş verilerini korur. MAM-WE ile, hassas veriler içeren iş veya okul ile ilgili uygulamalar, kendi cihazını getir (KCG) senaryolarında kişisel cihazlar dahil neredeyse her cihazdan yönetilebilir. Microsoft Office uygulamaları gibi birçok üretkenlik uygulaması, Intune MAM tarafından yönetilebilir. Genel kullanıma uygun [Intune özellikli uygulamaların](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) resmi listesine bakın.

**MAM hangi cihaz yapılandırmalarını destekler?** Intune MAM iki yapılandırmayı destekler:
  1. **Intune MDM + MAM**: Bu, MAM ilk kez başlatıldığında desteklenen ilk yapılandırmadır. BT yöneticileri, yalnızca Intune mobil cihaz yönetiminde (MDM) kayıtlı cihazlarda MAM ve uygulama koruma ilkelerini kullanarak uygulamaları yönetebilir. MDM + MAM kullanarak uygulamaları yönetmek için, müşterilerin https://manage.microsoft.com adresindeki Intune bağımsız konsolunu kullanması gerekir.

  2. **Cihaz kaydı olmadan MAM**: Cihaz kaydı olmadan MAM ya da diğer adıyla MAM-WE, BT yöneticilerinin Intune MDM’de kayıtlı olmayan cihazlarda MAM ve uygulama koruma ilkelerini kullanarak uygulamaları yönetmesine olanak sağlar. Bu, uygulamaların üçüncü taraf EMM sağlayıcılarında kayıtlı cihazlarda Intune tarafından yönetilebileceği anlamına gelir. Uygulamaları MAM-WE kullanarak yönetmek için, müşterilerin http://portal.azure.com adresindeki Azure portalında Intune konsolunu kullanması gerekir.


## <a name="app-protection-policies"></a>Uygulama koruma ilkeleri

**Uygulama koruma ilkeleri nelerdir**? Uygulama koruma ilkeleri, bir kuruluşa ait verilerin güvenli veya yönetilen bir uygulamanın içinde kalmasını sağlayan kurallardır. İlke, kullanıcı “kurumsal” verilere erişmeye veya bunları taşımaya çalıştığında uygulanan bir kural veya kullanıcı uygulamadayken yasaklanan veya izlenen bir eylemler kümesi olabilir.

**Uygulama koruma ilkelerinin örnekleri nelerdir?** Her uygulama koruma ilkesi ayarı hakkında ayrıntılı bilgi için [Android uygulama koruma ilkesi ayarları](../deploy-use/android-mam-policy-settings.md) ve [iOS uygulama koruma ilkesi ayarlarına](../deploy-use/ios-mam-policy-settings.md) bakın.

## <a name="apps-you-can-manage-with-app-protection-policies"></a>Uygulama koruma ilkeleri ile yönetebileceğiniz uygulamalar

**Hangi uygulamalar uygulama koruma ilkeleri tarafından yönetilebilir?** [Intune App SDK’sı](../develop/intune-app-sdk.md) tarafından Intune özelliğinin tanıtıldığı veya [Intune Uygulaması Sarmalama Aracı](../deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md) tarafından sarmalanan herhangi bir uygulama, Intune uygulama koruma ilkeleri kullanılarak yönetilebilir. Genel kullanıma sunulan [Intune özellikli uygulamaların](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) resmi listesine bakın.

**Intune özellikli bir uygulamada uygulama koruma ilkelerini kullanmak için temel gereksinimler nelerdir?**
  1. Son kullanıcının bir Azure Active Directory (AAD) hesabı olması gerekir. Azure Active Directory’de Intune kullanıcılarını nasıl oluşturacağınızı öğrenmek için [Kullanıcı ekleme ve Intune'a yönetici izni verme](../get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3.md) konusuna bakın.

  2. Son kullanıcının Azure Active Directory hesabına atanmış bir Microsoft Intune lisansının olması gerekir. Son kullanıcılara Intune lisanslarını nasıl atayacağınızı öğrenmek için [Intune lisanslarını yönetme](../get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4.md) konusuna bakın.

  3. Son kullanıcı bir uygulama koruma ilkesi tarafından hedeflenen bir güvenlik grubuna ait olmalıdır. Aynı uygulama koruma ilkesi, kullanılan belirli uygulamayı hedeflemelidir. Uygulama koruma ilkeleri [Azure portalındaki](http://portal.azure.com) Intune konsolunda oluşturulabilir ve dağıtılabilir. Güvenlik grupları şu anda [Office portalında](http://portal.office.com) oluşturulabilir.

  4. Son kullanıcının AAD hesabını kullanarak uygulamada oturum açması gerekir.

**[Outlook mobil uygulamasını](https://www.microsoft.com/outlook-com/mobile/) kullanmak için ek gereksinimler nelerdir?**

  1. Son kullanıcının cihazında Outlook mobil uygulamasının yüklü olması gerekir.

  2. Son kullanıcının, Azure Active Directory hesabına bağlı bir [Office 365 Exchange Online](https://products.office.com/exchange/exchange-online) posta kutusuna ve lisansına sahip olması gerekir.

  >[!NOTE]
  > Outlook mobil uygulaması şu anda yalnızca Microsoft Exchange Online’ı destekler ve Exchange şirket içi sürümünü veya Office 365’e Özel Exchange’i desteklemez.

**[Word, Excel ve PowerPoint](https://products.office.com/business/office) uygulamalarını kullanmak için ek gereksinimler nelerdir?**

  1. Son kullanıcının Azure Active Directory hesabına bağlı bir [Office 365 İş veya Kurumsal](https://products.office.com/business/compare-more-office-365-for-business-plans) lisansına sahip olması gerekir. Aboneliğin mobil cihazlarda Office uygulamalarını ve [OneDrive İş](https://onedrive.live.com/about/business/)’te bir bulut depolama hesabını içermesi gerekir. Office 365 lisansları [Office portalında](http://portal.office.com) bu [yönergeler](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc) izlenerek atanabilir.

  2. Son kullanıcının, cihazında [OneDrive](https://onedrive.live.com/about/) uygulamasının yüklü olması ve AAD hesabıyla oturum açması gerekir.

  3. OneDrive uygulamasının son kullanıcıya dağıtılan uygulama koruma ilkesi tarafından hedeflenmesi gerekir.

  >[!NOTE]
  > Office mobil uygulamaları şu anda yalnızca SharePoint Online’ı destekler ve SharePoint şirket içi sürümünü desteklemez.

**Office için neden OneDrive gerekiyor?** Intune, uygulamadaki tüm verileri “kurumsal” veya “kişisel” olarak işaretler. Veriler bir iş konumundan geliyorsa “kurumsal” olarak kabul edilir. Office uygulamaları söz konusu olduğunda Intune, aşağıdakileri iş konumu olarak kabul eder: e-posta (Exchange) veya bulut depolama (OneDrive İş hesabı içeren OneDrive uygulaması).

**Skype Kurumsal’ı kullanmak için ek gereksinimler nelerdir?** [Skype Kurumsal](https://products.office.com/skype-for-business/it-pros) lisans gereksinimlerine bakın.
  >[!NOTE]
  > Skype Kurumsal mobil uygulaması şu anda yalnızca Skype Kurumsal Çevrimiçi sürümü destekler.

## <a name="app-protection-features"></a>Uygulama koruma özellikleri

**Çoklu kimlik desteği nedir?** Çoklu kimlik desteği, Intune Uygulama SDK’sının, uygulama koruma ilkelerini yalnızca uygulamada oturum açan iş veya okul hesabına uygulama özelliğidir. Kişisel bir hesap uygulamada oturum açarsa, verilere koruma uygulanmaz.

**Çoklu kimlik desteğinin amacı nedir?** Çoklu kimlik desteği hem “kurumsal” kitleye hem de tüketici kitlesine sahip uygulamaların (yani Office uygulamalarının), “kurumsal” hesaplara yönelik Intune uygulama koruma özellikleri ile genel kullanım için yayımlanabilmesine olanak tanır.

**PIN ekranı ne zaman görüntülenir?** Intune PIN ekranı yalnızca, kullanıcı uygulamadaki “kurumsal” verilere erişmeye çalıştığında gösterilir. Örneğin, Word/Excel/PowerPoint uygulamalarında, son kullanıcı OneDrive İş üzerinden bir belgeyi açmayı denediğinde gösterilir (PIN’i zorunlu kılan bir uygulama koruma ilkesini başarıyla dağıttığınız varsayılırsa).

**Outlook'ta çoklu kimlik desteği nasıl işler?** Outlook’ta kişisel ve “kurumsal” e-postalar birleştirilmiş bir e-posta görünümünde gösterildiği için, Outlook uygulamasını başlattığınız zaman Intune PIN’i istenir.

**Intune uygulama PIN’i nedir?** Kişisel Kimlik Numarası (PIN), bir uygulamadaki kuruluş verilerine doğru kullanıcının eriştiğini doğrulamak için kullanılan bir paroladır.

  1. **Ne zaman kullanıcıdan PIN’ini girmesi istenir?** Intune, kullanıcının uygulama PIN’ini yalnızca kullanıcı “kurumsal” verilere erişmek üzereyken ister. Word/Excel/PowerPoint gibi çok kimlikli uygulamalarda, kullanıcı “kurumsal” bir belge veya dosyayı açmaya çalıştığında kullanıcıdan PIN’ini girmesi istenir. Intune Uygulaması Sarmalama Aracı kullanılan iş kolu uygulamaları gibi tek kimlikli uygulamalarda, Intune Uygulama SDK’sı kullanıcının uygulamadaki deneyiminin her zaman “kurumsal” nitelikli olduğunu bildiğinden, uygulama başlatıldığında PIN girilmesi istenir.

  2. **PIN güvenli midir?** PIN, uygulamadaki kuruluş verilerine yalnızca doğru kullanıcının erişmesine izin verir. Bu nedenle son kullanıcıların, Intune uygulama PIN’lerini ayarlamak veya sıfırlamak için iş veya okul hesaplarında oturum açmaları gerekir. Bu kimlik doğrulaması, Azure Active Directory tarafından güvenli belirteç değişimi ile işlenir ve Intune Uygulama SDK’sı tarafından görülmez. Güvenlik açısından, iş veya okul verilerini korumanın en iyi yolu verileri şifrelemektir. Şifreleme, uygulama PIN’i ile ilişkili değildir; ayrı bir uygulama koruma ilkesidir.

  3. **Intune, PIN’i deneme yanılma saldırılarına karşı nasıl koruyor?** Uygulama PIN’i ilkesinin parçası olarak BT yöneticisi, bir kullanıcının uygulama kilitlenmeden önce PIN’ini doğrulamayı en fazla kaç kez deneyebileceğini belirleyebilir. Deneme sayısına ulaşıldıktan sonra, Intune Uygulama SDK’sı uygulamadaki “kurumsal” verileri temizleyebilir.

**Şifreleme nasıl çalışır?** BT yöneticileri uygulama verilerinin şifrelenmesini gerektiren bir uygulama koruma ilkesi dağıtabilir. İlkenin bir parçası olarak BT yöneticisi, içeriğin ne zaman şifreleneceğini de belirtebilir.

  1. **Intune verileri nasıl şifreliyor?** Şifreleme uygulama koruma ilkesi ayarı hakkında ayrıntılı bilgi için [Android uygulama koruma ilkesi ayarları](../deploy-use/android-mam-policy-settings.md) ve [iOS uygulama koruma ilkesi ayarlarına](../deploy-use/ios-mam-policy-settings.md) bakın.

  2. **Neler şifrelenir?** BT yöneticisinin uygulama koruma ilkesine uygun şekilde, yalnızca “kurumsal” olarak işaretlenen veriler şifrelenir. Veriler bir iş konumundan geliyorsa “kurumsal” olarak kabul edilir. Office uygulamaları söz konusu olduğunda Intune, aşağıdakileri iş konumu olarak kabul eder: e-posta (Exchange) veya bulut depolama (OneDrive İş hesabı içeren OneDrive uygulaması). Intune Uygulaması Sarmalama Aracı kullanılan iş kolu uygulamaları söz konusu olduğunda, tüm veriler “kurumsal” olarak kabul edilir.

**Intune verileri uzaktan nasıl temizler?** Intune üç farklı şekilde uygulama verilerini temizleyebilir: tam cihaz temizleme, MDM için seçmeli temizleme ve MAM için seçmeli temizleme. MDM için uzaktan temizleme hakkında daha fazla bilgi için bkz. [Microsoft Intune kullanarak tam veya seçmeli temizleme ile verilerinizin korunmasına yardımcı olma](../deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune.md). MAM kullanan seçmeli temizleme hakkında daha fazla bilgi için bkz. [ Microsoft Intune ile yönetilen şirket uygulama verilerini temizleme](../deploy-use/wipe-managed-company-app-data-with-microsoft-intune.md)

  1. **Tam temizleme nedir?** [Tam temizleme](../deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe), cihazı varsayılan fabrika ayarlarına döndürerek tüm kullanıcı verilerini ve ayarlarını **cihazdan** kaldırır. Cihaz Intune’dan kaldırılır.
  >[!NOTE]
  > Tam temizleme yalnızca Intune mobil cihaz yönetiminde (MDM) kayıtlı cihazlarda gerçekleştirilebilir.

  2. **MDM için seçmeli temizleme nedir?** Seçmeli temizleme hakkında daha fazla bilgi için bkz. [Microsoft Intune kullanarak tam veya seçmeli temizleme ile verilerinizin korunmasına yardımcı olma](../deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe).

  3. **MAM için seçmeli temizleme nedir?** MAM için seçmeli temizleme, şirket uygulama verilerini uygulamadan kaldırır. Intune Azure portalı kullanarak istek başlatılır. Temizleme isteği başlatmayı öğrenmek için bkz. [ Microsoft Intune ile yönetilen şirket uygulama verilerini temizleme](../deploy-use/wipe-managed-company-app-data-with-microsoft-intune.md)

  4. **MAM için seçmeli temizleme ne kadar sürede gerçekleşir?** Seçmeli temizleme başlatıldığında kullanıcı uygulamayı kullanıyorsa, Intune Uygulama SDK’sı her 30 dakikada bir Intune MAM hizmetinden bir seçmeli temizleme isteği gelip gelmediğini denetler. Ayrıca kullanıcı uygulamayı ilk kez başlattığında ve iş veya okul hesabı ile oturum açtığında da seçmeli temizleme isteği olup olmadığı denetlenir.

**Şirket İçi hizmetler neden Intune korumalı uygulamalar ile çalışmıyor?** Intune uygulama koruması, kullanıcı kimliğinin uygulama ve Intune Uygulama SDK’sı arasında tutarlı olmasına bağlıdır. Bunu garanti etmenin tek yolu modern kimlik doğrulaması yapmaktır. Uygulamaların bir şirket içi yapılandırma ile çalışabileceği senaryolar vardır, ancak bunlar tutarlı değildir ve garanti edilmez.

**Web bağlantılarını yönetilen uygulamalardan açmanın güvenli bir yolu var mı?** Evet! BT yöneticisi, Microsoft Intune tarafından geliştirilen ve Intune ile kolayca yönetilebilen bir web tarayıcısı olan [Intune Managed Browser uygulamasını](../deploy-use/manage-internet-access-using-managed-browser-policies.md) dağıtabilir ve bunun için uygulama koruma ilkesi ayarlayabilir. BT yöneticisi, Intune özellikli tüm uygulamalardaki web bağlantılarının Managed Browser uygulaması kullanılarak açılmasını gerekli kılabilir.


## <a name="app-experience-on-android"></a>Android’de uygulama deneyimi

**Intune uygulama korumasının Android cihazlarda çalışması için neden Şirket Portalı uygulaması gerekiyor?** Uygulama koruma işlevlerinin çoğu Şirket Portalı uygulamasında yerleşik olarak bulunur. Şirket Portalı uygulaması her zaman gerekli olsa bile cihaz kaydı _gerekli değildir_. MAM-WE için son kullanıcının cihazında Şirket Portalı uygulamasının yüklü olması yeterlidir.

## <a name="app-experience-on-ios"></a>iOS’da uygulama deneyimi

**Veri aktarımı ilkesi “yalnızca yönetilen uygulamalar” veya “uygulama yok” olarak ayarlanmış olsa bile, yönetilmeyen uygulamalarda iş veya okul verilerini açmak için iOS paylaşım uzantısını kullanabiliyorum. Bu veri sızıntısına neden olmaz mı?** Intune uygulama koruma ilkesi, cihaz yönetilmeden iOS paylaşım uzantısını denetleyemez. Bu nedenle, Intune _**“kurumsal” verileri veriler uygulama dışında paylaşılmadan önce şifreler**_. Bunu, “kurumsal” dosyayı yönetilen uygulama dışında açmaya çalışarak doğrulayabilirsiniz. Bu dosya şifrelenmiş olmalı ve yönetilen bir uygulama dışında açılamamalıdır.

### <a name="see-also"></a>Ayrıca bkz.
- [Microsoft Intune’da Android mobil uygulama yönetim ilkesi ayarları](../deploy-use/android-mam-policy-settings.md)
- [iOS mobil uygulama yönetim ilkesi ayarları](../deploy-use/ios-mam-policy-settings.md)
- [Mobil uygulama yönetimi kurulumunuzu doğrulama](../deploy-use/validate-mobile-application-management.md)
- [Microsoft Intune ile mobil uygulama yönetimi ilkelerinizi yapılandırmak için hazırlanma](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)
- [Microsoft Intune için destek alma](../troubleshoot/how-to-get-support-for-microsoft-intune.md)

