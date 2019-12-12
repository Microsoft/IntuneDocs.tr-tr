---
title: MAM ve uygulama koruma hakkında sık kullanılan sorular
description: Bu makalede, Intune mobil uygulama yönetimi (MAM) ve Intune uygulama koruma hakkında sık sorulan sorulardan bazıları yanıtlanmaktadır.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/09/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 149def73-9d08-494b-97b7-4ba1572f0623
ms.reviewer: erikre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0880d06e23b84c54cd6e24b6b61b5028c2a1d9bb
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72507149"
---
# <a name="frequently-asked-questions-about-mam-and-app-protection"></a>MAM ve uygulama koruma hakkında sık kullanılan sorular

Bu makalede, Intune mobil uygulama yönetimi (MAM) ve Intune uygulama koruma hakkında sık sorulan sorulardan bazıları yanıtlanmaktadır.

## <a name="mam-basics"></a>MAM Temel Kavramları

**MAM nedir?**<br></br>
[Intune mobil uygulama yönetimi](app-lifecycle.md), kullanıcılarınız için mobil uygulamaları yayımlama, gönderme, yapılandırma, güvenlik altına alma, izleme ve güncelleştirme gibi eylemler gerçekleştirmenize olanak tanıyan Intune yönetim özellikleri paketini ifade eder.

**MAM uygulama korumanın avantajları nedir?**<br></br>
MAM, bir uygulama içindeki kuruluş verilerini korur. Kayıtsız MAM (MAM-WE) ile, hassas veriler içeren iş veya okul ile ilgili uygulamalar, kendi cihazını getir (KCG) senaryolarında kişisel cihazlar dahil neredeyse her cihazdan yönetilebilir. Microsoft Office uygulamaları gibi birçok üretkenlik uygulaması Intune MAM tarafından yönetilebilir. Genel kullanıma sunulan [Intune ile yönetilen uygulamaların](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) resmi listesine bakın.

**MAM hangi cihaz yapılandırmalarını destekler?**<br></br>
Intune MAM iki yapılandırmayı destekler:
- **Intune MDM + MAM**: BT yöneticileri, yalnızca Intune mobil cihaz yönetiminde (MDM) kayıtlı cihazlarda MAM ve uygulama koruma ilkelerini kullanarak uygulamaları yönetebilir. Uygulamaları MAM-WE kullanarak yönetmek için, müşterilerin https://portal.azure.com adresindeki Azure portalında Intune konsolunu kullanması gerekir.

- **Cihaz kaydı olmadan MAM**: Cihaz kaydı olmadan MAM ya da diğer adıyla MAM-WE, BT yöneticilerinin Intune MDM’de kayıtlı olmayan cihazlarda MAM ve uygulama koruma ilkelerini kullanarak uygulamaları yönetmesine olanak sağlar. Bu, uygulamaların üçüncü taraf EMM sağlayıcılarında kayıtlı cihazlarda Intune tarafından yönetilebileceği anlamına gelir. Uygulamaları MAM-WE kullanarak yönetmek için, müşterilerin [https://portal.azure.com](https://portal.azure.com)Azure Portal Intune konsolunu kullanması gerekir. Ayrıca uygulamalar, üçüncü taraf Enterprise Mobility Management (EMM) sağlayıcıları ile kaydedilmiş veya hiçbir MDM ile kaydedilmemiş cihazlarda uygulamalar Intune ile yönetilebilir.


## <a name="app-protection-policies"></a>Uygulama koruma ilkeleri

**Uygulama koruma ilkeleri nedir?**<br></br>
Uygulama koruma ilkeleri, bir kuruluşa ait verilerin güvenli veya yönetilen bir uygulamanın içinde kalmasını sağlayan kurallardır. İlke, kullanıcı “kurumsal” verilere erişmeye veya bunları taşımaya çalıştığında uygulanan bir kural veya kullanıcı uygulamadayken yasaklanan veya izlenen bir eylemler kümesi olabilir.

**Uygulama koruma ilkelerinin örnekleri nelerdir?**<br></br>
Her uygulama koruma ilkesi ayarı hakkında ayrıntılı bilgi için [Android uygulama koruma ilkesi ayarları](app-protection-policy-settings-android.md) ve [iOS uygulama koruma ilkesi ayarlarına](app-protection-policy-settings-ios.md) bakın.

**Farklı cihazlarda aynı kullanıcıya hem MDM hem de MAM ilkelerinin aynı anda uygulanmasını mümkün mü? Örneğin, bir Kullanıcı kendi MAM etkin makinesinden iş kaynaklarına erişebiliyorsa, Ayrıca işe ve Intune MDM ile yönetilen bir cihaz kullanmaya da karşılık gelebilir. Bu fikir için herhangi bir uyarılar var mı?**<br></br>
Kullanıcıya cihaz durumunu ayarlamadan bir MAM ilkesi uygularsanız, Kullanıcı hem KCG cihazında hem de Intune tarafından yönetilen cihazda MAM ilkesini alır. Yönetilen duruma göre bir MAM ilkesi de uygulayabilirsiniz. Bu nedenle, bir uygulama koruma ilkesi oluşturduğunuzda, hedefi tüm uygulama türleri ' nin yanında Hayır ' ı seçin. Ardından aşağıdakilerden birini yapın:
- Intune tarafından yönetilen cihazlara daha az sıkı bir MAM ilkesi uygulayın ve MDM 'ye kayıtlı olmayan cihazlara daha kısıtlayıcı bir MAM ilkesi uygulayın.
- Yalnızca kaydı silinen cihazlara bir MAM ilkesi uygulayın.

Daha fazla bilgi için bkz. [Uygulama koruma ilkelerini izleme](app-protection-policies-monitor.md).

## <a name="apps-you-can-manage-with-app-protection-policies"></a>Uygulama koruma ilkeleri ile yönetebileceğiniz uygulamalar

**Hangi uygulamalar uygulama koruma ilkeleri tarafından yönetilebilir?**<br></br>
[Intune App SDK’sı](../developer/app-sdk.md) ile tümleştirilmiş veya [Intune Uygulaması Sarmalama Aracı](../developer/apps-prepare-mobile-application-management.md) tarafından sarmalanmış herhangi bir uygulama, Intune uygulama koruma ilkeleri kullanılarak yönetilebilir. Genel kullanıma sunulan [Intune ile yönetilen uygulamaların](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) resmi listesine bakın.

**Intune ile yönetilen bir uygulamada uygulama koruma ilkelerini kullanmak için temel gereksinimler nelerdir?**

- Son kullanıcının bir Azure Active Directory (AAD) hesabı olması gerekir. Azure Active Directory’de Intune kullanıcılarını nasıl oluşturacağınızı öğrenmek için [Kullanıcı ekleme ve Intune'a yönetici izni verme](../fundamentals/users-add.md) konusuna bakın.

- Son kullanıcının Azure Active Directory hesabına atanmış bir Microsoft Intune lisansının olması gerekir. Son kullanıcılara Intune lisanslarını nasıl atayacağınızı öğrenmek için [Intune lisanslarını yönetme](../fundamentals/licenses-assign.md) konusuna bakın.

- Son kullanıcı bir uygulama koruma ilkesi tarafından hedeflenen bir güvenlik grubuna ait olmalıdır. Aynı uygulama koruma ilkesi, kullanılan belirli uygulamayı hedeflemelidir. Uygulama koruma ilkeleri [Azure portalındaki](https://portal.azure.com) Intune konsolunda oluşturulabilir ve dağıtılabilir. Güvenlik grupları Şu anda [Microsoft 365 Yönetim merkezinde](https://admin.microsoft.com)oluşturulabilir.

- Son kullanıcının AAD hesabını kullanarak uygulamada oturum açması gerekir.

**Intune Uygulama Koruması olan bir uygulamayı etkinleştirmek istersem, ancak desteklenen bir uygulama geliştirme platformu kullandığımda ne olur?**

Intune SDK geliştirme ekibi etkin bir şekilde sınar ve yerel Android, iOS (obj-C, Swift), Xamarin, Xamarin. Forms ve Cordova platformlarıyla oluşturulmuş uygulamalar için destek sağlar. Bazı müşteriler, bir Kullanıcı ve NativeScript gibi diğer platformlarla Intune SDK tümleştirmesi ile başarılı olmuş olsa da, desteklenen platformlarımızdan başka herhangi bir şeyi kullanarak uygulama geliştiricileri için açık rehberlik veya eklentiler sağlamayız.

**Intune APP SDK’sı, Microsoft Authentication Library’yi (MSAL) veya diğer sosyal hesapları destekliyor mu?**<br></br>
Intune APP SDK’sı, SDK’nın hem 1. hem de 3. taraf sürümleri için bazı gelişmiş ADAL işlevleri kullanır. Dolayısıyla MSAL, Intune Uygulama Koruması hizmetinde kimlik doğrulaması ve koşullu başlatma gibi çoğu temel senaryomuzla birlikte düzgün çalışmaz. Microsoft 'un kimlik ekibinin tüm Microsoft Office uygulamalar için MSAL 'e geçiş yapması, Intune SDK 'sının bu uygulamayı desteklemesi gerekir, ancak bugün bir plan yoktur.

**[Outlook mobil uygulamasını](https://products.office.com/outlook) kullanmak için ek gereksinimler nelerdir?**

- Son kullanıcının cihazında Outlook mobil uygulamasının yüklü olması gerekir.

- Son kullanıcının, Azure Active Directory hesabına bağlı bir [Office 365 Exchange Online](https://products.office.com/exchange/exchange-online) posta kutusuna ve lisansına sahip olması gerekir.

  >[!NOTE]
  > Outlook mobil uygulaması şu anda yalnızca Microsoft Exchange Online için Intune Uygulama Koruması’nı ve [Hibrit modern kimlik doğrulaması ile Exchange Server](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx)’ı destekler ve Exchange’deki Office 365 Özel’i desteklemez.

**[Word, Excel ve PowerPoint](https://products.office.com/business/office) uygulamalarını kullanmak için ek gereksinimler nelerdir?**

- Son kullanıcının Azure Active Directory hesabına bağlı bir [Office 365 İş veya Kurumsal](https://products.office.com/business/compare-more-office-365-for-business-plans) lisansına sahip olması gerekir. Aboneliğin mobil cihazlarda Office uygulamalarını içermesi gerekir ve [OneDrive İş](https://onedrive.live.com/about/business/)’te bir bulut depolama hesabını içerebilir. Office 365 lisansları, bu [yönergeleri](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc)izleyerek [Microsoft 365 Yönetim merkezinde](https://admin.microsoft.com) atanabilir.

- Son kullanıcı, “Farklı Kaydet Seçeneğini Engelle” uygulama koruma ilkesi ayarı altından ayrıntılı kaydet özelliğini kullanarak yönetilen bir konum ayarlamalıdır. Örneğin, yönetilen konum OneDrive ise [OneDrive](https://onedrive.live.com/about/) uygulaması son kullanıcının Word, Excel veya PowerPoint uygulamasında yapılandırılmalıdır.

- Yönetilen konum OneDrive ise uygulama, son kullanıcıya dağıtılan uygulama koruma ilkesi tarafından hedeflenmelidir.

  >[!NOTE]
  > Office mobil uygulamaları şu anda yalnızca SharePoint Online’ı destekler ve SharePoint şirket içi sürümünü desteklemez.

**Office için neden yönetilen bir konum (örneğin OneDrive) gereklidir?**<br></br>
Intune, uygulamadaki tüm verileri “kurumsal” veya “kişisel” olarak işaretler. Veriler bir iş konumundan geliyorsa “kurumsal” olarak kabul edilir. Office uygulamaları söz konusu olduğunda Intune, aşağıdakileri iş konumu olarak kabul eder: e-posta (Exchange) veya bulut depolama (OneDrive İş hesabı içeren OneDrive uygulaması).

**Skype Kurumsal’ı kullanmak için ek gereksinimler nelerdir?**<br></br>
[Skype Kurumsal](https://products.office.com/skype-for-business/it-pros) lisans gereksinimlerine bakın. Skype Kurumsal (SfB) hibrit ve şirket içi yapılandırmaları için bkz. [Skype Kurumsal ve Exchange için Hibrit Modern Kimlik Doğrulaması Genel Kullanıma Sunuldu](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Hybrid-Modern-Auth-for-SfB-and-Exchange-goes-GA/ba-p/134756) ve [AAD ile Skype Kurumsal için Modern Kimlik Doğrulaması](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Modern-Auth-for-SfB-OnPrem-with-AAD/ba-p/180910).

## <a name="app-protection-features"></a>Uygulama koruma özellikleri

**Çoklu kimlik desteği nedir?**<br></br>
Çoklu kimlik desteği, Intune Uygulama SDK’sının, uygulama koruma ilkelerini yalnızca uygulamada oturum açan iş veya okul hesabına uygulama özelliğidir. Kişisel bir hesap uygulamada oturum açarsa, verilere koruma uygulanmaz.

**Çoklu kimlik desteğinin amacı nedir?**<br></br>
Çoklu kimlik desteği hem “kurumsal” kitleye hem de tüketici kitlesine sahip uygulamaların (yani Office uygulamalarının), “kurumsal” hesaplara yönelik Intune uygulama koruma özellikleri ile genel kullanım için yayımlanabilmesine olanak tanır.

**Outlook'ta çoklu kimlik desteği nasıl işler?**<br></br>
Outlook’ta kişisel ve “kurumsal” e-postalar birleştirilmiş bir e-posta görünümünde gösterildiği için, Outlook uygulamasını başlattığınız zaman Intune PIN’i istenir.

**Intune uygulama PIN’i nedir?**<br></br>
Kişisel Kimlik Numarası (PIN), bir uygulamadaki kuruluş verilerine doğru kullanıcının eriştiğini doğrulamak için kullanılan bir paroladır.

- **Ne zaman kullanıcıdan PIN’ini girmesi istenir?**<br></br> Intune, kullanıcının uygulama PIN’ini yalnızca kullanıcı “kurumsal” verilere erişmek üzereyken ister. Word/Excel/PowerPoint gibi çok kimlikli uygulamalarda, kullanıcı “kurumsal” bir belge veya dosyayı açmaya çalıştığında kullanıcıdan PIN’ini girmesi istenir. Intune Uygulaması Sarmalama Aracı kullanılarak yönetilen iş kolu uygulamaları gibi tek kimlikli uygulamalarda, Intune Uygulama SDK’sı kullanıcının uygulamadaki deneyiminin her zaman “kurumsal” nitelikli olduğunu bildiğinden, uygulama başlatıldığında PIN girilmesi istenir.

- **Kullanıcıdan ne sıklıkta Intune PIN’i istenecek?**<br></br> BT yöneticisi, Intune yönetici konsolunda “(dakika) sonra erişim gereksinimlerini yeniden denetle” Intune uygulama koruma ilkesini tanımlayabilir. Bu ayar, cihazda erişim gereksinimlerini denetlenmeden önce geçmesi gereken süresi belirtir ve uygulama PIN ekranı yeniden gösterilir. Ancak kullanıcıdan PIN istenme sıklığını etkileyen önemli PIN ayrıntıları şöyledir: 

  - **Kullanılabilirliği iyileştirmek için PIN, aynı yayımcının uygulamaları arasında paylaşılır:** iOS’ta bir uygulama PIN’i **aynı uygulama yayımcısına ait** tüm uygulamalar arasında paylaşılır. Android’de bir uygulama PIN’i tü uygulamalar arasında paylaşılır.
  - **Cihaz yeniden başlatma işleminden sonra '(dakika) sonra erişim gereksinimlerini yeniden denetle' davranışı:** Bir "PIN zamanlayıcısı" Intune uygulama PIN’inin tekrar ne zaman gösterileceğini belirleyen işlem yapılmadan geçen dakika sayısını izler. iOS’ta PIN zamanlayıcısı, cihaz yeniden başlatma işleminden etkilenmez. Bu nedenle cihazı yeniden başlatmak, Intune PIN ilkesine sahip bir iOS uygulamasında kullanıcının işlem yapmadan geçirdiği dakika sayısı üzerinde hiçbir etki yapmaz. Android’de ise PIN zamanlayıcısı, cihaz yeniden başlatıldığında sıfırlanır. Dolayısıyla Intune PIN ilkesine sahip Android uygulamaları, **cihaz yeniden başlatma işleminden sonra** büyük olasılıkla ‘(dakika) sonra erişim gereksinimlerini yeniden denetle’ ayarının değerini dikkate almaksızın bir uygulama PIN’i isteyecektir.  
  - **PIN ile ilişkili zamanlayıcının kayıt yapısı:** Bir uygulamaya (uygulama A) erişmek için bir PIN girildiğinde ve uygulama ön plandan (ana girdi odağı) ayrıldığında, bu PIN için PIN zamanlayıcısı sıfırlanır. Bu PIN’i paylaşan başka bir uygulama (uygulama B), zamanlayıcı sıfırlandığı için kullanıcıdan PIN girmesini istemeyecektir. “(dakika) sonra erişim gereksinimlerini yeniden denetle” değeri yeniden karşılandığında istem yeniden görüntülenecektir.

iOS cihazlarda PIN, farklı yayımcılardan gelen uygulamalar arasında paylaşılsa bile **(dakika) sonra erişim gereksinimlerini yeniden denetle** süresi geçtikten sonra ana giriş odağı olmayan uygulamada istem yeniden görüntülenir. Yani, örneğin bir kullanıcıda _X_ yayımcısının _A_ uygulaması ve _Y_ yayımcısının _B_ uygulaması varsa bu iki uygulama aynı PIN’i paylaşır. Kullanıcı, _A_ uygulamasına odaklanmıştır (uygulama ön plandadır) ve _B_ uygulaması simge durumuna küçültülmüştür. **(dakika) sonra erişim gereksinimlerini yeniden denetle** süresi geçtikten sonra kullanıcı _B_ uygulamasına geçerse PIN gerekir.

  >[!NOTE] 
  > Kullanıcının erişim gereksinimlerini (örneğin PIN istemini) daha sık doğrulamak için “(dakika) sonra erişim gereksinimlerini yeniden denetle” ayarındaki değeri azaltmanız önerilir. 
      
- **Intune PIN’i, Outlook ve OneDrive için yerleşik uygulama PIN’leriyle birlikte nasıl çalışır?**<br></br>
Intune PIN'i, işlem yapmadan geçen süreye (yani '(dakika) sonra erişim gereksinimlerini yeniden denetle' değerine) bağlı olarak çalışır. Bu sebeple Intune PIN istemleri, genelde varsayılan olarak uygulama başlatmasına bağlı olan Outlook ve OneDrive için yerleşik uygulama PIN’lerinden bağımsız olarak çalışır. Kullanıcı iki PIN istemini de aynı anda alırsa, beklenen davranış Intune PIN’inin öncelik kazanmasıdır. 

- **PIN güvenli midir?**<br></br> PIN, uygulamadaki kuruluş verilerine yalnızca doğru kullanıcının erişmesine izin verir. Bu nedenle son kullanıcıların, Intune uygulama PIN’lerini ayarlamak veya sıfırlamak için iş veya okul hesaplarında oturum açmaları gerekir. Bu kimlik doğrulaması, Azure Active Directory tarafından güvenli belirteç değişimi ile işlenir ve Intune Uygulama SDK’sı tarafından görülmez. Güvenlik açısından, iş veya okul verilerini korumanın en iyi yolu verileri şifrelemektir. Şifreleme, uygulama PIN'i ile ilişkili değildir; ayrı bir uygulama koruma ilkesidir.

- **Intune, PIN’i deneme yanılma saldırılarına karşı nasıl koruyor?**<br></br> Uygulama PIN’i ilkesinin parçası olarak BT yöneticisi, bir kullanıcının uygulama kilitlenmeden önce PIN’ini doğrulamayı en fazla kaç kez deneyebileceğini belirleyebilir. Deneme sayısına ulaşıldıktan sonra, Intune Uygulama SDK’sı uygulamadaki “kurumsal” verileri temizleyebilir.
  
- **Ayın yayımcının uygulamalarında PIN'i neden iki kez ayarlamam gerekiyor?**<br></br> MAM (iOS üzerinde) şu anda Intune APP SDK’sının iOS ile tümleştirilmesi için uygulamaların (örneğin WXP, Outlook, Managed Browser, Yammer) katılımını gerektiren alfasayısal ve özel karakterli uygulama düzeyinde PIN’e (bunlara “geçiş kodu” adı verilir) izin verir. Bu olmadan geçiş kodu ayarları, hedeflenmiş uygulamalar için doğru şekilde zorlanır. Bu, iOS için Intune SDK'sı 7.1.12 sürümünde kullanıma sunulmuş olan bir özellikti. <br><br> Bu özelliği desteklemek ve iOS için Intune SDK'sının önceki sürümleriyle geriye dönük uyumluluğu güvence altına almak için, 7.1.12+ sürümlerinde tüm PIN'ler (sayısal veya geçiş kodu) SDK'nın önceki sürümlerindeki sayısal PIN'den ayrı işlenir. Bu nedenle, cihazda aynı yayımcının iOS için Intune SDK'sının 7.1.12 öncesi VE 7.1.12 sonrası sürümlerini içeren uygulamalar varsa, iki PIN ayarlamaları gerekir. <br><br> Bununla birlikte, iki PIN (her uygulama için) herhangi bir şekilde birbiriyle ilgili değildir; uygulamaya uygulanan uygulama koruma ilkesine uygun olmaları gerekir. Dolayısıyla, *ancak* A ve B uygulamalarına aynı ilkeler uygulandıysa (PIN'e göre), kullanıcı aynı PIN'i iki kez ayarlayabilir. <br><br> Bu davranış Intune Mobil Uygulama Yönetimi'nin etkinleştirildiği iOS uygulamalardaki PIN’e özgüdür. Zaman içinde, uygulamalar iOS için Intune SDK'sının daha yeni sürümlerini benimsedikçe aynı yayımcıdan gelen uygulamalarda iki kez PIN ayarlama gereği sorun olmaktan çıkar. Örnek görmek için lütfen aşağıdaki nota bakın.

  >[!NOTE]
  > Örneğin, aynı yayımcının A uygulaması 7.1.12 öncesi bir sürümle oluşturulduysa ve B uygulaması 7.1.12 ile veya sonraki bir sürümle oluşturulduysa, iOS cihazında her iki uygulamanın da yüklü olması durumunda son kullanıcının A ve B için ayrı PIN'ler ayarlaması gerekir. <br><br> Cihazda SDK sürümü 7.1.9 olan bir C uygulaması yüklüyse, A uygulamasıyla aynı PIN'i paylaşır. <br><br> Sürümü 7.1.14 olan D uygulaması, B uygulamasıyla aynı PIN'i paylaşır. <br><br> Cihazda yalnızca A ve C uygulamaları yüklüyse, tek bir PIN'in ayarlanması yeterli olur. Cihazda yalnızca B ve D uygulamaları yüklü olduğunda da aynı durum geçerlidir.

**Şifreleme nasıl çalışır?**<br></br>
BT yöneticileri uygulama verilerinin şifrelenmesini gerektiren bir uygulama koruma ilkesi dağıtabilir. İlkenin bir parçası olarak BT yöneticisi, içeriğin ne zaman şifreleneceğini de belirtebilir.

- **Intune verileri nasıl şifreliyor?**<br></br> Şifreleme uygulama koruma ilkesi ayarı hakkında ayrıntılı bilgi için [Android uygulama koruma ilkesi ayarları](app-protection-policy-settings-android.md) ve [iOS uygulama koruma ilkesi ayarlarına](app-protection-policy-settings-ios.md) bakın.

- **Neler şifrelenir?**<br></br> BT yöneticisinin uygulama koruma ilkesine uygun şekilde, yalnızca “kurumsal” olarak işaretlenen veriler şifrelenir. Veriler bir iş konumundan geliyorsa “kurumsal” olarak kabul edilir. Office uygulamaları söz konusu olduğunda Intune, aşağıdakileri iş konumu olarak kabul eder: e-posta (Exchange) veya bulut depolama (OneDrive İş hesabı içeren OneDrive uygulaması). Intune Uygulaması Sarmalama Aracı ile yönetilen iş kolu uygulamaları söz konusu olduğunda, tüm veriler “kurumsal” olarak kabul edilir.

**Intune verileri uzaktan nasıl temizler?**<br></br>
Intune üç farklı şekilde uygulama verilerini temizleyebilir: tam cihaz temizleme, MDM için seçmeli temizleme ve MAM için seçmeli temizleme. MDM için uzaktan silme hakkında daha fazla bilgi için bkz. [Silme veya kullanımdan kaldırma işlemlerini kullanarak cihaz kaldırma](../remote-actions/devices-wipe.md). MAM kullanarak seçmeli silme hakkında daha fazla bilgi için bkz. [Kullanımdan kaldırma eylemi](../remote-actions/devices-wipe.md#retire) ve [Uygulamalardan yalnızca şirket verilerini silme](apps-selective-wipe.md).

- **Silme nedir?**<br></br> [Silme](../remote-actions/devices-wipe.md), cihazı varsayılan fabrika ayarlarına döndürerek tüm kullanıcı verilerini ve ayarlarını **cihazdan** kaldırır. Cihaz Intune’dan kaldırılır.
  >[!NOTE]
  > Silme yalnızca Intune mobil cihaz yönetimine (MDM) kayıtlı cihazlarda gerçekleştirilebilir.

- **MDM için seçmeli temizleme nedir?**<br></br> Şirket verilerini kaldırma hakkında bilgi edinmek için [Cihaz kaldırma - kullanımdan kaldırma](../remote-actions/devices-wipe.md#retire) bölümüne bakın.

- **MAM için seçmeli temizleme nedir?**<br></br> MAM için seçmeli temizleme, şirket uygulama verilerini uygulamadan kaldırır. Intune Azure portalı kullanarak istek başlatılır. Bir silme isteği başlatma hakkında bilgi edinmek için bkz. [Uygulamalardan yalnızca şirket verilerini temizleme](apps-selective-wipe.md).

- **MAM için seçmeli temizleme ne kadar sürede gerçekleşir?**<br></br> Seçmeli temizleme başlatıldığında kullanıcı uygulamayı kullanıyorsa, Intune Uygulama SDK’sı her 30 dakikada bir Intune MAM hizmetinden bir seçmeli temizleme isteği gelip gelmediğini denetler. Ayrıca kullanıcı uygulamayı ilk kez başlattığında ve iş veya okul hesabı ile oturum açtığında da seçmeli temizleme isteği olup olmadığı denetlenir.

**Şirket İçi hizmetler neden Intune korumalı uygulamalar ile çalışmıyor?**<br></br>
Intune uygulama koruması, kullanıcı kimliğinin uygulama ve Intune Uygulama SDK’sı arasında tutarlı olmasına bağlıdır. Bunu garanti etmenin tek yolu modern kimlik doğrulaması yapmaktır. Uygulamaların bir şirket içi yapılandırma ile çalışabileceği senaryolar vardır, ancak bunlar tutarlı değildir ve garanti edilmez.

**Web bağlantılarını yönetilen uygulamalardan açmanın güvenli bir yolu var mı?**<br></br>
Evet! BT yöneticisi, Microsoft Intune tarafından geliştirilen ve Intune ile kolayca yönetilebilen bir web tarayıcısı olan [Intune Managed Browser uygulamasını](../apps/app-configuration-managed-browser.md) dağıtabilir ve bunun için uygulama koruma ilkesi ayarlayabilir. BT yöneticisi, Intune ile yönetilen tüm uygulamalardaki web bağlantılarının Managed Browser uygulaması kullanılarak açılmasını gerekli kılabilir.

## <a name="app-experience-on-android"></a>Android’de uygulama deneyimi

**Intune uygulama korumasının Android cihazlarda çalışması için neden Şirket Portalı uygulaması gerekiyor?**<br></br>
Uygulama koruma işlevlerinin çoğu Şirket Portalı uygulamasında yerleşik olarak bulunur. Şirket Portalı uygulaması her zaman gerekli olsa bile cihaz kaydı _gerekli değildir_. MAM-WE için son kullanıcının cihazında Şirket Portalı uygulamasının yüklü olması yeterlidir.

**Aynı uygulama ve kullanıcı kümesine yapılandırılan birden çok Intune uygulama koruma erişimi ayarları Android'de nasıl çalışır?**<br></br>
Son kullanıcı cihazları kendi şirket hesaplarından hedeflenen uygulamaya erişmeyi denediklerinde, erişim için Intune uygulama koruma ilkeleri bu cihazlara belirli bir sırada uygulanır. Genel olarak öncelik engellemededir; ardından kapatılabilen uyarı gelir. Örneğin, belirli bir kullanıcı/uygulama için uygunsa, kullanıcıyı bir yama yükseltmesi alması için uyaran en düşük Android yama sürümü ayarı, kullanıcının erişimini engelleyen en düşük Android yama sürümü ayarından sonra uygulanacaktır. Dolayısıyla, BT yöneticisinin en düşük Android yama sürümü olarak 2018-03-01 ve en düşük Android yama sürümü (yalnızca Uyarı) olarak 2018-02-01'i ayarladığı bir senaryoda, uygulamaya erişmeye çalışan cihazın yama sürümü 2018-01-01 olduğunda, son kullanıcı erişimin engellenmesine yol açan en düşük Android yama sürümüne yönelik daha kısıtlayıcı ayar temel alınarak engellenebilir. 

Farklı ayar türleriyle ilgilenirken, uygulama sürümü gereksinimi önceliklidir ve bunu Android işletim sistemi sürümü gereksinimi ile Android yama sürümü gereksinimi izler. Ardından, tüm ayarlar türlerine yönelik uyarılar aynı sırada denetlenir.

**Intune Uygulama Koruması Ilkeleri, yöneticilerin, son kullanıcı cihazlarının Android cihazlar için Google 'ın SafetyNet kanıtlamasını geçmesini gerektirmesini sağlar. Hizmete yeni bir SafetyNet kanıtlama sonucu ne sıklıkta gönderilir?** <br><br> Yeni bir Google Play hizmeti belirleme, Intune hizmeti tarafından belirlenen bir aralıkta BT yöneticisine bildirilir. Yükleme nedeniyle hizmet çağrısının ne sıklıkta azaltıldı, bu nedenle bu değer dahili olarak korunur ve yapılandırılamaz. Google SafetyNet kanıtlama ayarı için herhangi bir BT Yöneticisi yapılandırılmış eylemi, koşullu başlatma sırasında Intune hizmetine yönelik son bildirilen sonuca göre alınacaktır. Hiçbir veri yoksa, başka hiçbir koşullu başlatma denetimi başarısız olmasına bağlı olarak erişime izin verilir ve kanıtlama sonuçlarını belirlemek için Google Play hizmeti "gidiş dönüş", arka uçta başlayacaktır ve cihaz başarısız olursa kullanıcının zaman uyumsuz olarak sorulması istenir. Eski veriler varsa, son bildirilen sonuca bağlı olarak erişim engellenir veya izin verilir ve benzer şekilde, kanıtlama sonuçlarını belirlemek için bir Google Play hizmeti "gidiş dönüş" işlemi başlar ve cihaz başarısız olursa kullanıcıyı zaman uyumsuz olarak uyarır.

**Intune Uygulama Koruması Ilkeleri, yöneticilerin Android cihazları için Google 'ın uygulamaları doğrula API 'SI aracılığıyla son kullanıcı cihazlarının sinyal göndermesini gerektirmek için yetenek sağlar. Son Kullanıcı bu nedenle uygulama taramasını nasıl açabilir? böylece, bunun nedeni bunlara erişim engellenmemelidir?**<br><br> Bunun nasıl yapılacağı hakkında yönergeler cihaz tarafından biraz farklılık gösterir. Genel işlem, Google Play Store gidip **uygulamalarıma & oyunlarına**tıklayarak, son uygulama taramasının sonucunu tıklayarak, yürütme koruması menüsüne gidecektir. **Tarama cihazını güvenlik tehditlerine** karşı değiştirme seçeneğinin açık olduğundan emin olun.

**Google 'ın SafetyNet kanıtlama API 'SI aslında Android cihazlarını denetmidir? ' Temel bütünlüğü denetle ' ve ' temel bütünlüğü & sertifikalı cihazları denetle ' için yapılandırılabilir değerler arasındaki fark nedir?** <br><br>
Intune, kayıtlı olmayan cihazlar için mevcut kök algılama denetimlerimize eklemek üzere SafetyNet API 'Lerini koruma Google Play kullanır. Google, Android uygulamalarının köklü cihazlarda çalıştırılmasını istemediklerinde benimsemesini sağlamak üzere bu API kümesini geliştirmiştir ve yaşmıştır. Android ödeme uygulaması bu şekilde eklenmiştir. Google, oluşan kök algılama denetimlerinden tamamen ortak bir şekilde paylaşmadığı sürece, bu API 'Lerin cihazlarını barındıran kullanıcıları algılamasını bekledik. Bu kullanıcıların, ilke etkin uygulamalarından daha sonra erişimine veya şirket hesaplarına erişimi engellenebilir. ' Temel bütünlüğü denetle ' size cihazın genel bütünlüğünü söyler. Köklü cihazlar, Öykünücüler, sanal cihazlar ve değişiklik işaretlerine sahip cihazlar temel bütünlüğü başarısız oluyor. ' Sertifikalı cihazların & temel bütünlüğünü denetle ' size, cihazın Google 'ın hizmetleriyle uyumluluğunu söyler. Yalnızca Google tarafından sertifikalı değiştirilmemiş cihazlar bu denetimi geçirebilir. Başarısız olacak cihazlar şunları içerir:

- Temel bütünlük başarısız olan cihazlar
- Kilidi açılmış bir önyükleme yükleyicisine sahip cihazlar
- Özel bir sistem görüntüsü/ROM içeren cihazlar
- Üretici, Google sertifikası için uygulanan veya geçirilecek cihazların 
- Doğrudan Android açık kaynak program kaynak dosyalarından oluşturulan sistem görüntüsü olan cihazlar
- Beta/Geliştirici Önizleme sistem görüntüsü olan cihazlar

Teknik Ayrıntılar için, bkz. [Google 'ın SafetyNet kanıtlama hakkındaki belgeleri](https://developer.android.com/training/safetynet/attestation) .

**Android cihazlar için Intune Uygulama Koruması Ilkesi oluştururken koşullu başlatma bölümünde iki benzer denetim vardır. ' SafetyNet cihaz kanıtlama ' ayarını veya ' jailbreak uygulanmış/kökü belirtilmiş cihazlar ' ayarını gerektirmem gerekir mi?** <br><br>
Google Play korunmamıza sonra, son kullanıcının çevrimiçi olmasını, en azından kanıtlama sonuçlarının belirlenmesi için "gidiş dönüş" sırasında geçen sürenin süresini Son Kullanıcı çevrimdışı ise, BT Yöneticisi ' jailbreak uygulanmış/kökü belirtilmiş cihazlar ' ayarından Zorlanmış olmaya devam edebilir. Bu, Son Kullanıcı çok uzun süredir çevrimdışı ise, ' çevrimdışı yetkisiz kullanım süresi ' değeri yürütmeye gelir ve ağ erişimi kullanılabilir olana kadar iş veya okul verilerine yapılan tüm erişimler Bu Zamanlayıcı değerine ulaşıldığında engellenir. Her iki ayarı açmak, son kullanıcılar mobil verilerde iş veya okul verilerine erişirken önemli olan Son Kullanıcı cihazlarını sağlıklı tutmaya yönelik katmanlı bir yaklaşım sağlar. 

**Google Play koruma API 'Lerinden yararlanan uygulama koruma ilkesi ayarları Google Play Hizmetleri çalışmasını gerektirir. Son kullanıcının olabileceği konumda Google Play Hizmetleri izin verilmiyorsa ne olur?**<br><br>
Hem ' SafetyNet cihaz kanıtlama ' hem de ' uygulamalar üzerinde tehdit taraması ' ayarları, Google 'ın Google Play Hizmetleri sürümünün düzgün şekilde çalışmasını gerektirir. Bunlar güvenlik alanına denk gelen ayarlar olduğundan, Son Kullanıcı bu ayarlarla hedeflendiyse ve uygun Google Play Hizmetleri veya Google Play Hizmetleri erişimi olmayan bir sürüme güvenmemişse engellenir. 

## <a name="app-experience-on-ios"></a>iOS’da uygulama deneyimi
**Cihazıma bir parmak izi veya yüz kimliği eklersem veya bunları cihazımdan kaldırırsam ne olur?**<br></br>
Intune uygulama koruma ilkeleri, yalnızca Intune lisanslı kullanıcılara uygulama erişimi denetimi verir. Uygulamaya erişimi denetleme yollarından biri, desteklenen cihazlarda Apple’ın Touch ID veya Face ID özelliğini gerekli kılmaktır. Intune, cihazın biyometrik veritabanında bir değişiklik olduğunda ve etkin olmama zaman aşımı değeri karşılandığında kullanıcıdan PIN isteyen bir davranış uygular. Biyometrik verilerdeki değişikliklere parmak izi veya yüz kimliği eklenmesi veya kaldırılması dahildir. Intune kullanıcısı bir PIN ayarlamamışsa, Intune PIN’i ayarlamak üzere yönlendirilir.

Bunun amacı, uygulama içerisindeki kuruluş verilerinizin güvenliğini sağlamak ve verileri uygulama düzeyinde korumaktır. Bu özellik yalnızca iOS için kullanılabilir ve iOS için Intune APP SDK’sı sürüm 9.0.1 veya üzeri sürümleri tümleştiren uygulamaların katılımını gerektirir. Hedeflenen uygulamalarda davranışın zorlanabilmesi için SDK tümleştirmesi gereklidir. Bu tümleştirme, sıralı bir şekilde gerçekleşir ve belirli uygulama ekiplerine bağımlıdır. Katılan uygulamalardan bazıları WXP, Outlook, Managed Browser ve Yammer’dır.
  
**Veri aktarım ilkesi "yalnızca yönetilen uygulamalar" veya "uygulama yok" olarak ayarlanmış olsa bile, yönetilmeyen uygulamalarda iş veya okul verilerini açmak için iOS Share uzantısını kullanabiliyorum. Bu veri sızıntısı mı?**<br></br>
Intune uygulama koruma ilkesi, cihaz yönetilmeden iOS paylaşım uzantısını denetleyemez. Bu nedenle, Intune _**“kurumsal” verileri veriler uygulama dışında paylaşılmadan önce şifreler**_ . Bunu, yönetilen uygulama dışında "kurumsal" dosyayı açmaya çalışarak doğrulayabilirsiniz. Bu dosya yalnızca şifrelenmiş ve yönetilen bir uygulama olarak açılmalıdır.

**Aynı uygulama ve kullanıcı kümesine yapılandırılan birden çok Intune uygulama koruma erişimi ayarları iOS'da nasıl çalışır?**<br></br>
Son kullanıcı cihazları kendi şirket hesaplarından hedeflenen uygulamaya erişmeyi denediklerinde, erişim için Intune uygulama koruma ilkeleri bu cihazlara belirli bir sırada uygulanır. Genel olarak öncelik temizlemededir; ardından engelleme, sonra da kapatılabilen uyarı gelir. Örneğin, belirli bir kullanıcı/uygulama için uygunsa, kullanıcıyı iOS sürümünü güncelleştirmesi için uyaran en düşük iOS işletim sistemi ayarı, kullanıcının erişimini engelleyen en düşük iOS işletim sistemi ayarından sonra uygulanacaktır. Dolayısıyla, BT yöneticisinin en düşük iOS işletim sistemi olarak 11.0.0.0 ve en düşük iOS işletim sistemi (yalnızca Uyarı) olarak 11.1.0.0'ı ayarladığı bir senaryoda, uygulamaya erişmeye çalışan cihazın işletim sistemi iOS 10 olduğunda, son kullanıcı erişimin engellenmesine yol açan en düşük iOS işletim sistemi sürümüne yönelik daha kısıtlayıcı ayar temel alınarak engellenebilir.

Farklı ayar türleriyle ilgilenirken, Intune Uygulama SDK'sı sürümü gereksinimi önceliklidir ve bunu uygulama sürümü gereksinimi ile iOS işletim sistemi sürümü gereksinimi izler. Ardından, tüm ayarlar türlerine yönelik uyarılar aynı sırada denetlenir. Intune Uygulama SDK'sı sürümü gereksiniminin, yalnızca temel engelleme senaryoları için Intune ürün ekibinin yönlendirmesiyle yapılandırılmasını öneririz.


## <a name="see-also"></a>Ayrıca bkz:
- [Intune planınızı uygulama](../fundamentals/planning-guide-onboarding.md)
- [Intune sınama ve doğrulama](../fundamentals/planning-guide-test-validation.md)
- [Microsoft Intune’da Android mobil uygulama yönetim ilkesi ayarları](../apps/app-protection-policy-settings-android.md)
- [iOS mobil uygulama yönetim ilkesi ayarları](../apps/app-protection-policy-settings-ios.md)
- [Uygulama koruma ilkeleri ilke yenileme](../apps/app-protection-policy-delivery.md)
- [Uygulama koruma ilkelerinizi doğrulama](../apps/app-protection-policy-delivery.md)
- [Cihaz kaydı olmadan yönetilen uygulamalar için uygulama yapılandırma ilkeleri ekleme](../apps/app-configuration-policies-managed-app.md)
- [Microsoft Intune için destek alma](../fundamentals/get-support.md)
