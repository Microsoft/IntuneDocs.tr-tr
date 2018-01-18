---
title: "MAM ve uygulama koruma hakkında sık kullanılan sorular"
description: "Bu makalede, Intune mobil uygulama yönetimi (MAM) ve Intune uygulama koruma hakkında sık sorulan sorulardan bazıları yanıtlanmaktadır."
keywords: 
author: oydang
ms.author: oydang
manager: angrobe
ms.date: 01/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 149def73-9d08-494b-97b7-4ba1572f0623
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4c345673eceea4da4efc3b90f43c6f9313ee15f1
ms.sourcegitcommit: 0795870bfe941612259ebec0fe313a783a44d9b9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/11/2018
---
# <a name="frequently-asked-questions-about-mam-and-app-protection"></a>MAM ve uygulama koruma hakkında sık kullanılan sorular

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bu makalede, Intune mobil uygulama yönetimi (MAM) ve Intune uygulama koruma hakkında sık sorulan sorulardan bazıları yanıtlanmaktadır.

## <a name="mam-basics"></a>MAM Temel Kavramları


**MAM nedir?** [Intune mobil uygulama yönetimi](/intune/app-lifecycle), kullanıcılarınız için mobil uygulamaları yayımlama, gönderme, yapılandırma, güvenlik altına alma, izleme ve güncelleştirme gibi eylemler gerçekleştirmenize olanak tanıyan Intune yönetim özellikleri paketini ifade eder.

**MAM uygulama korumanın avantajları nedir?** MAM, bir uygulama içindeki kuruluş verilerini korur. MAM-WE ile, hassas veriler içeren iş veya okul ile ilgili uygulamalar, kendi cihazını getir (KCG) senaryolarında kişisel cihazlar dahil neredeyse her cihazdan yönetilebilir. Microsoft Office uygulamaları gibi birçok üretkenlik uygulaması, Intune MAM tarafından yönetilebilir. Genel kullanıma uygun [Intune özellikli uygulamaların](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) resmi listesine bakın.

**MAM hangi cihaz yapılandırmalarını destekler?** Intune MAM iki yapılandırmayı destekler:
  1. **Intune MDM + MAM**: Bu, MAM ilk kez başlatıldığında desteklenen ilk yapılandırmadır. BT yöneticileri, yalnızca Intune mobil cihaz yönetiminde (MDM) kayıtlı cihazlarda MAM ve uygulama koruma ilkelerini kullanarak uygulamaları yönetebilir. MDM + MAM kullanarak uygulamaları yönetmek için, müşterilerin https://manage.microsoft.com adresindeki Intune bağımsız konsolunu kullanması gerekir.

  2. **Cihaz kaydı olmadan MAM**: Cihaz kaydı olmadan MAM ya da diğer adıyla MAM-WE, BT yöneticilerinin Intune MDM’de kayıtlı olmayan cihazlarda MAM ve uygulama koruma ilkelerini kullanarak uygulamaları yönetmesine olanak sağlar. Bu, uygulamaların üçüncü taraf EMM sağlayıcılarında kayıtlı cihazlarda Intune tarafından yönetilebileceği anlamına gelir. Uygulamaları MAM-WE kullanarak yönetmek için, müşterilerin http://portal.azure.com adresindeki Azure portalında Intune konsolunu kullanması gerekir.


## <a name="app-protection-policies"></a>Uygulama koruma ilkeleri

**Uygulama koruma ilkeleri nelerdir**? Uygulama koruma ilkeleri, bir kuruluşa ait verilerin güvenli veya yönetilen bir uygulamanın içinde kalmasını sağlayan kurallardır. İlke, kullanıcı “kurumsal” verilere erişmeye veya bunları taşımaya çalıştığında uygulanan bir kural veya kullanıcı uygulamadayken yasaklanan veya izlenen bir eylemler kümesi olabilir.

**Uygulama koruma ilkelerinin örnekleri nelerdir?** Her uygulama koruma ilkesi ayarı hakkında ayrıntılı bilgi için [Android uygulama koruma ilkesi ayarları](../deploy-use/android-mam-policy-settings.md) ve [iOS uygulama koruma ilkesi ayarlarına](../deploy-use/ios-mam-policy-settings.md) bakın.

## <a name="apps-you-can-manage-with-app-protection-policies"></a>Uygulama koruma ilkeleri ile yönetebileceğiniz uygulamalar

**Hangi uygulamalar uygulama koruma ilkeleri tarafından yönetilebilir?** [Intune App SDK’sı](/intune/app-sdk) tarafından Intune özelliğinin tanıtıldığı veya [Intune Uygulaması Sarmalama Aracı](/intune/apps-prepare-mobile-application-management) tarafından sarmalanan herhangi bir uygulama, Intune uygulama koruma ilkeleri kullanılarak yönetilebilir. Genel kullanıma sunulan [Intune özellikli uygulamaların](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) resmi listesine bakın.

**Intune özellikli bir uygulamada uygulama koruma ilkelerini kullanmak için temel gereksinimler nelerdir?**
  1. Son kullanıcının bir Azure Active Directory (AAD) hesabı olması gerekir. Azure Active Directory’de Intune kullanıcılarını nasıl oluşturacağınızı öğrenmek için [Kullanıcı ekleme ve Intune'a yönetici izni verme](/intune/users-permissions-add) konusuna bakın.

  2. Son kullanıcının Azure Active Directory hesabına atanmış bir Microsoft Intune lisansının olması gerekir. Son kullanıcılara Intune lisanslarını nasıl atayacağınızı öğrenmek için [Intune lisanslarını yönetme](/intune/licenses-assign) konusuna bakın.

  3. Son kullanıcı bir uygulama koruma ilkesi tarafından hedeflenen bir güvenlik grubuna ait olmalıdır. Aynı uygulama koruma ilkesi, kullanılan belirli uygulamayı hedeflemelidir. Uygulama koruma ilkeleri [Azure portalındaki](http://portal.azure.com) Intune konsolunda oluşturulabilir ve dağıtılabilir. Güvenlik grupları şu anda [Office portalında](http://portal.office.com) oluşturulabilir.

  4. Son kullanıcının AAD hesabını kullanarak uygulamada oturum açması gerekir.

**[Outlook mobil uygulamasını](https://www.microsoft.com/outlook-com/mobile/) kullanmak için ek gereksinimler nelerdir?**

  1. Son kullanıcının cihazında Outlook mobil uygulamasının yüklü olması gerekir.

  2. Son kullanıcının, Azure Active Directory hesabına bağlı bir [Office 365 Exchange Online](https://products.office.com/exchange/exchange-online) posta kutusuna ve lisansına sahip olması gerekir.

  >[!NOTE]
  > Outlook mobil uygulaması şu anda yalnızca Microsoft Exchange Online’ı destekler ve Exchange şirket içi sürümünü veya Office 365’e Özel Exchange’i desteklemez.

**[Word, Excel ve PowerPoint](https://products.office.com/business/office) uygulamalarını kullanmak için ek gereksinimler nelerdir?**

  1. Son kullanıcının Azure Active Directory hesabına bağlı bir [Office 365 İş veya Kurumsal](https://products.office.com/business/compare-more-office-365-for-business-plans) lisansına sahip olması gerekir. Aboneliğin mobil cihazlarda Office uygulamalarını içermesi gerekir ve [OneDrive İş](https://onedrive.live.com/about/business/)’te bir bulut depolama hesabını içerebilir. Office 365 lisansları [Office portalında](http://portal.office.com) bu [yönergeler](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc) izlenerek atanabilir.

  2. Son kullanıcı, “Farklı Kaydet Seçeneğini Engelle” uygulama koruma ilkesi ayarı altından ayrıntılı kaydet özelliğini kullanarak yönetilen bir konum ayarlamalıdır. Örneğin, yönetilen konum OneDrive ise [OneDrive](https://onedrive.live.com/about/) uygulaması son kullanıcının Word, Excel veya PowerPoint uygulamasında yapılandırılmalıdır.

  3. Yönetilen konum OneDrive ise uygulama, son kullanıcıya dağıtılan uygulama koruma ilkesi tarafından hedeflenmelidir.

  >[!NOTE]
  > Office mobil uygulamaları şu anda yalnızca SharePoint Online’ı destekler ve SharePoint şirket içi sürümünü desteklemez.

**Neden yönetilen bir konum (örneğin OneDrive) gereklidir?** Intune, uygulamadaki tüm verileri “kurumsal” veya “kişisel” olarak işaretler. Veriler bir iş konumundan geliyorsa “kurumsal” olarak kabul edilir. Office uygulamaları söz konusu olduğunda Intune, aşağıdakileri iş konumu olarak kabul eder: e-posta (Exchange) veya bulut depolama (OneDrive İş hesabı içeren OneDrive uygulaması).

**Skype Kurumsal’ı kullanmak için ek gereksinimler nelerdir?** [Skype Kurumsal](https://products.office.com/skype-for-business/it-pros) lisans gereksinimlerine bakın.
  >[!NOTE]
  > Skype Kurumsal mobil uygulaması şu anda yalnızca Skype Kurumsal Çevrimiçi sürümü destekler.

## <a name="app-protection-features"></a>Uygulama koruma özellikleri

**Çoklu kimlik desteği nedir?** Çoklu kimlik desteği, Intune Uygulama SDK’sının, uygulama koruma ilkelerini yalnızca uygulamada oturum açan iş veya okul hesabına uygulama özelliğidir. Kişisel bir hesap uygulamada oturum açarsa, verilere koruma uygulanmaz.

**Çoklu kimlik desteğinin amacı nedir?** Çoklu kimlik desteği hem “kurumsal” kitleye hem de tüketici kitlesine sahip uygulamaların (yani Office uygulamalarının), “kurumsal” hesaplara yönelik Intune uygulama koruma özellikleri ile genel kullanım için yayımlanabilmesine olanak tanır.

**Outlook'ta çoklu kimlik desteği nasıl işler?** Outlook’ta kişisel ve “kurumsal” e-postalar birleştirilmiş bir e-posta görünümünde gösterildiği için, Outlook uygulamasını başlattığınız zaman Intune PIN’i istenir.

**Intune uygulama PIN’i nedir?** Kişisel Kimlik Numarası (PIN), bir uygulamadaki kuruluş verilerine doğru kullanıcının eriştiğini doğrulamak için kullanılan bir paroladır.

  1. **Ne zaman kullanıcıdan PIN’ini girmesi istenir?** Intune, kullanıcının uygulama PIN’ini yalnızca kullanıcı “kurumsal” verilere erişmek üzereyken ister. Word/Excel/PowerPoint gibi çok kimlikli uygulamalarda, kullanıcı “kurumsal” bir belge veya dosyayı açmaya çalıştığında kullanıcıdan PIN’ini girmesi istenir. Intune Uygulaması Sarmalama Aracı kullanılan iş kolu uygulamaları gibi tek kimlikli uygulamalarda, Intune Uygulama SDK’sı kullanıcının uygulamadaki deneyiminin her zaman “kurumsal” nitelikli olduğunu bildiğinden, uygulama başlatıldığında PIN girilmesi istenir.

2. **Kullanıcıdan ne sıklıkta Intune PIN’i istenecek?**
BT yöneticisi, Intune yönetici konsolunda “(dakika) sonra erişim gereksinimlerini yeniden denetle” Intune uygulama koruma ilkesini tanımlayabilir. Bu ayar, cihazda erişim gereksinimlerini denetlenmeden önce geçmesi gereken süresi belirtir ve uygulama PIN ekranı yeniden gösterilir. Ancak kullanıcıdan PIN istenme sıklığını etkileyen önemli PIN ayrıntıları şöyledir: 

* **Kullanılabilirliği iyileştirmek için PIN, aynı yayımcının uygulamaları arasında paylaşılır:** iOS’ta bir uygulama PIN’i **aynı yayımcıya ait** tüm uygulamalar arasında paylaşılır. Android’de bir uygulama PIN’i tü uygulamalar arasında paylaşılır.
* **PIN ile ilişkili zamanlayıcının kayıt yapısı:** Bir uygulamaya (uygulama A) erişmek için bir PIN girildiğinde ve uygulama ön plandan (ana girdi odağı) ayrıldığında, bu PIN için PIN zamanlayıcısı sıfırlanır. Bu PIN’i paylaşan başka bir uygulama (uygulama B), zamanlayıcı sıfırlandığı için kullanıcıdan PIN girmesini istemeyecektir. “(dakika) sonra erişim gereksinimlerini yeniden denetle” değeri yeniden karşılandığında istem yeniden görüntülenecektir. 

>[!NOTE] 
> Kullanıcının erişim gereksinimlerini (yani PIN istemini) daha sık doğrulamak için, “(dakika) sonra erişim gereksinimlerini yeniden denetle” ayarındaki değeri azaltmanız önerilir. 

  3. **PIN güvenli midir?** PIN, uygulamadaki kuruluş verilerine yalnızca doğru kullanıcının erişmesine izin verir. Bu nedenle son kullanıcıların, Intune uygulama PIN’lerini ayarlamak veya sıfırlamak için iş veya okul hesaplarında oturum açmaları gerekir. Bu kimlik doğrulaması, Azure Active Directory tarafından güvenli belirteç değişimi ile işlenir ve Intune Uygulama SDK’sı tarafından görülmez. Güvenlik açısından, iş veya okul verilerini korumanın en iyi yolu verileri şifrelemektir. Şifreleme, uygulama PIN’i ile ilişkili değildir; ayrı bir uygulama koruma ilkesidir.

  4. **Intune, PIN’i deneme yanılma saldırılarına karşı nasıl koruyor?** Uygulama PIN’i ilkesinin parçası olarak BT yöneticisi, bir kullanıcının uygulama kilitlenmeden önce PIN’ini doğrulamayı en fazla kaç kez deneyebileceğini belirleyebilir. Deneme sayısına ulaşıldıktan sonra, Intune Uygulama SDK’sı uygulamadaki “kurumsal” verileri temizleyebilir.
  
  5. **Ayın yayımcının uygulamalarında PIN'i neden iki kez ayarlamam gerekiyor?**
MAM (iOS üzerinde) şu anda Intune APP SDK’sının iOS ile tümleştirilmesi için uygulamaların (örneğin WXP, Outlook, Managed Browser, Yammer) katılımını gerektiren alfasayısal ve özel karakterler (‘geçiş kodu’ denilir) içeren uygulama düzeyi PIN’e (iOS) izin verir. Bu olmadan geçiş kodu ayarları, hedeflenmiş uygulamalar için doğru şekilde zorlanır. Bu, iOS için Intune SDK'sı 7.1.12 sürümünde kullanıma sunulmuş olan bir özellikti. <br> Bu özelliği desteklemek ve iOS için Intune SDK'sının önceki sürümleriyle geriye dönük uyumluluğu güvence altına almak için, 7.1.12+ sürümlerinde tüm PIN'ler (sayısal veya geçiş kodu) SDK'nın önceki sürümlerindeki sayısal PIN'den ayrı işlenir. Bu nedenle, cihazda aynı yayımcının iOS için Intune SDK'sının 7.1.12 öncesi VE 7.1.12 sonrası sürümlerini içeren uygulamalar varsa, iki PIN ayarlamaları gerekir. <br><br> Bununla birlikte, iki PIN (her uygulama için) herhangi bir şekilde birbiriyle ilgili değildir; uygulamaya uygulanan uygulama koruma ilkesine uygun olmaları gerekir. Dolayısıyla, *ancak* A ve B uygulamalarına aynı ilkeler uygulandıysa (PIN'e göre), kullanıcı aynı PIN'i iki kez ayarlayabilir. <br><br> Bu davranış Intune Mobil Uygulama Yönetimi'nin etkinleştirildiği iOS uygulamalardaki PIN'e özgüdür. Zaman içinde, uygulamalar iOS için Intune SDK'sının daha yeni sürümlerini benimsedikçe aynı yayımcıdan gelen uygulamalarda iki kez PIN ayarlama gereği sorun olmaktan çıkar. Örnek görmek için lütfen aşağıdaki nota bakın.

>[!NOTE]
> Örneğin, aynı yayımcının A uygulaması 7.1.12 öncesi bir sürümle oluşturulduysa ve B uygulaması 7.1.12 ile veya sonraki bir sürümle oluşturulduysa, iOS cihazında her iki uygulamanın da yüklü olması durumunda son kullanıcının A ve B için ayrı PIN'ler ayarlaması gerekir. <br> Cihazda SDK sürümü 7.1.9 olan bir C uygulaması yüklüyse, A uygulamasıyla aynı PIN'i paylaşır. <br> Sürümü 7.1.14 olan D uygulaması, B uygulamasıyla aynı PIN'i paylaşır. <br> Cihazda yalnızca A ve C uygulamaları yüklüyse, tek bir PIN'in ayarlanması yeterli olur. Cihazda yalnızca B ve D uygulamaları yüklü olduğunda da aynı durum geçerlidir.

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

### <a name="see-also"></a>Ayrıca bkz:
- [Microsoft Intune’da Android mobil uygulama yönetim ilkesi ayarları](../deploy-use/android-mam-policy-settings.md)
- [iOS mobil uygulama yönetim ilkesi ayarları](../deploy-use/ios-mam-policy-settings.md)
- [Mobil uygulama yönetimi kurulumunuzu doğrulama](../deploy-use/validate-mobile-application-management.md)
- [Microsoft Intune ile mobil uygulama yönetimi ilkelerinizi yapılandırmak için hazırlanma](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)
- [Microsoft Intune için destek alma](../troubleshoot/how-to-get-support-for-microsoft-intune.md)
