---
title: "Erken sürüm"
description: 
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 01/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ac9cb0ad7d1b5e2c29e80f16c172f41c08d3a15d
ms.sourcegitcommit: 5fd17a57989c6da3d325ed2e0018ce16fe20bb79
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/04/2018
---
# <a name="the-early-edition-for-microsoft-intune---january-2018"></a>Microsoft Intune için erken sürüm - Ocak 2018

**Erken sürüm**, Microsoft Intune'un gelecek sürümlerinde kullanıma sunulacak yeni özelliklerin bir listesini sunar. Bu bilgiler kısıtlı bir kapsamla verilmektedir ve değiştirilebilir. Bu bilgileri şirket dışından kimselerle paylaşmayın. Burada listelenen özelliklerden bazılarının son tarihe yetişememe riski vardır ve gelecek sürüme ertelenebilir. Diğer özellikler, müşterinin kullanımına hazır olduğundan emin olmak için pilot (sürüyor) aşamasında test edilmektedir. Herhangi bir sorunuz veya endişeniz varsa lütfen Microsoft ürün grubu ilgili kişisiyle bağlantı kurun.

Bu sayfa düzenli aralıklarla güncelleştirilir. Ek güncelleştirmeleri daha sonra denetleyin.

> [!Note]
>Intune için aşağıdaki değişiklikler geliştirilme aşamasındadır. Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler sayfamızı](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) gözden geçirin.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices 
-->


## <a name="intune-in-the-azure-portal"></a>Azure portalında Intune

### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546---"></a>Windows 10 için Şirket Portalı'ndaki uyumluluk sorunlarının daha kolay çözümü<!--676546 -->

Windows cihazı olan son kullanıcılar, Şirket Portalı uygulamasında uyumsuzluk nedenine dokunabilecek. Buna dokunmaları mümkün olduğunda, ayarlar uygulamasında sorunu çözebilecekleri konuma gidecekler. 

### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625---"></a>Apple toplu kaydında kullanıcı kimlik doğrulaması için yeni seçenek <!-- 747625 -->
Intune, aşağıdaki kayıt yöntemlerinde size Şirket Portalı uygulamasını kullanarak cihazların kimliğini doğrulama seçeneği sağlayacak:

- Apple Cihaz Kaydı Programı
- Apple School Manager
- Apple Configurator Kaydı

Şirket portalı seçeneği kullanılırken, bu kayıt yöntemlerini engellemeden Azure Active Directory çok faktörlü kimlik doğrulaması zorunlu tutulabilir.

Şirket portalı seçeneği kullanılırken, Intune kullanıcı benzeşimi kaydı için iOS Kurulum Yardımcısı'nda kullanıcı kimlik doğrulamasını atlar. Bu, cihazın başlangıçta kullanıcısız bir cihaz olarak kaydedildiği ve dolayısıyla kullanıcı gruplarının yapılandırmaları veya ilkelerini almayacağı anlamına gelir. Yalnızca cihaz gruplarının yapılandırmalarını ve ilkelerini alacak. Bununla birlikte, Intune Şirket Portalı uygulamasını Cihaz üzerine otomatik olarak yükleyecek. Şirket Portalı uygulamasını başlatan ve bu uygulamada oturum açan ilk kullanıcı, Intune'da cihazla ilişkilendirilecek. Bu noktada kullanıcı kendi kullanıcı gruplarının yapılandırmalarını ve ilkelerini alacak. Yeniden kayıt yapılmadan kullanıcı ilişkisi değiştirilemez.

### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Birden çok Apple DEP / Apple School Manager hesabı için Intune desteği <!-- 747685 -->
Intune, sayıları 100'e varan farklı Apple Aygıt Kayıt Programı (DEP) veya Apple School Manager hesabından cihazların kaydını destekleyecek. Karşıya yüklenen her belirteç kayıt profilleri ve cihazlar için ayrı olarak yönetilebilir. Karşıya yüklenen DEP/School Manager belirteçlerinin her biri için farklı bir kayıt profili otomatik olarak atanabilir. Birden çok School Manager belirteci karşıya yüklenirse, Microsoft School Data Sync ile bir kerede tek bir belirteç paylaşılabilir.

Geçişten sonra, Graph üzerinden Apple DEP veya ASM yönetimi için beta Graph API'leri ve yayımlanan betikler artık çalışmayacak. Yeni beta Graph API'leri geliştirme aşamasındadır ve geçiş sonrasında yayınlanacaktır.

### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963-eeready---"></a>İş Yeri veya Okula Erişme ayarlarını kullanarak cihaz kategorilerini seçme <!-- 1058963 eeready --> 
[Cihaz grubu eşlemeyi](https://docs.microsoft.com/en-us/intune/device-group-mapping) etkinleştirdiyseniz, Windows 10'daki kullanıcılardan **Ayarlar** > **Hesaplar** > **İş yeri veya okula eriş** altındaki **Bağlan** düğmesi aracılığıyla veya ilk kez çalıştırma deneyimi sırasında kaydolduktan sona cihaz kategorisini seçmeleri istenecek.

### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Uyumluluk ilkelerinde cihaz gruplarındaki cihazları hedefleme <!--1307012 -->

Uyumluluk ilkelerinde kullanıcı gruplarındaki kullanıcıları hedefleyebileceksiniz. Uyumluluk ilkelerinde cihaz gruplarındaki cihazları hedefleyebileceksiniz. 

### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>Gruplar temelinde uygulama atamasını dahil etme ve hariç tutma <!-- 1406920 -->

Uygulama ataması sırasında ve bir atama türü seçtikten sonra, hem dahil edilecek hem de hariç tutulacak grupları seçebilirsiniz. Ayrıca, dahil edilen gruplar olarak önceden oluşturulmuş grupları da (Tüm Kullanıcılar, Tüm Cihazlar ve Tüm Kullanıcılar+Cihazlar) kullanabilirsiniz.

### <a name="remote-erase-command-support----1438084---"></a>Uzaktan "Sil" komutu desteği <!-- 1438084 -->

Yöneticiler uzaktan Sil komutu gönderebilecek.

> [!IMPORTANT]
> Sil komutu geri alınamaz ve dikkatli kullanılmalıdır.

Sil komutu işletim sistemi de içinde olmak üzere cihazdan tüm verileri kaldırır. Cihaz ayrıca Intune yönetiminden de kaldırılır. Kullanıcıya hiçbir uyarı gönderilmez ve komut gönderildiğinde silme işlemi hemen gerçekleştirilir.

Altı basamaklı bir kurtarma PIN'i yapılandırabileceksiniz. Bu PIN silinmiş olan cihazın kilidini açmak için kullanılabilir ve bu noktada işletim sisteminin yeniden yüklemesi başlar. Silme işlemi başlatıldıktan sonra, Intune'da cihazın genel bakış dikey penceresindeki durum çubuğunda PIN gösterilir. Silme işlemi devam ettiği sürece PIN görüntüde kalacak. Silme işlemi tamamlandıktan sonra, cihaz Intune yönetiminden tamamen kaybolur. Herhangi birinin cihazı geri yükleyen kullanabilmesi için kurtarma PIN'ini bir yere kaydettiğinizden emin olun.

### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Windows arama sonuçlarında Windows Bilgi Koruması (WIP) ile şifrelenmiş veriler <!-- 1469193 -->

Windows Bilgi Koruması (WIP) ilkesindeki yeni bir ayar, Windows arama sonuçlarına WIP ile şifrelenmiş verilerin dahil edilip edilmeyeceğini denetlemenize olanak tanıyacak.

### <a name="website-learning-mode----1631908---"></a>Web Sitesi Öğrenme Modu <!-- 1631908 -->

Intune, Windows Bilgi Koruması (WIP) Öğrenme modunun bir uzantısını kullanıma sunacak. WIP'nin etkinleştirildiği uygulamalar hakkındaki bilgileri görüntülemeye ek olarak, web siteleriyle paylaşılan iş verilerine sahip cihazların özetini de görüntüleyebileceksiniz. Bu bilgilerle, grup ve kullanıcı WIP ilkelerine hangi web sitelerinin eklenmesi gerektiğini saptayabilirsiniz.

### <a name="updates-to-compliance-emails---1637547---"></a>Uyumluluk e-postalarında güncelleştirmeler <!--1637547 -->

Uyumsuz bir cihazı raporlamak amacıyla e-posta gönderildiğinde, uyumsuz cihaz hakkındaki ayrıntılar da eklenecek. Şu makale, bu olguyu belirtecek şekilde güncelleştirilecek: [Uyumsuzluğa yönelik eylemleri otomatikleştirme](#actions-for-noncompliance).

### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal-----1737088-1634311---"></a>Intune için Koşullu Erişim ilkeleri yalnızca Azure Portal'dan sağlanır  <!-- 1737088 1634311 --> 
Koşullu erişimi yapılandıracağınız ve yöneteceğiniz yeri basitleştireceğiz. İlkelerinizi [Azure Portal](https://portal.azure.com)'daki **Azure Active Directory** > **Koşullu Erişim**'de yapılandıracak ve yöneteceksiniz. Size kolaylık olması için, Azure Portal'daki **Intune** > **Koşullu Erişim** konumundan da erişebileceksiniz.

###  <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Süresi dolan ve dolmak üzere olan belirteçler için uyarılar <!-- 1639263 -->
Genel bakış sayfasında süresi dolan ve dolmak üzere olan belirteçler için uyarılar gösterilecek. Tek bir belirtecin uyarısına tıkladığınızda, belirtecin ayrıntılar sayfasına gideceksiniz.  Birden çok belirteç içeren bir uyarıya tıklarsanız, durumlarıyla birlikte tüm belirteçlerin listesine gideceksiniz. Yöneticilerin, süreleri dolmadan önce belirteçleri yenilemesi gerekir.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Güvenli bir ağ üzerinden uzaktan yazdırma <!-- 1709994  -->
PrinterOn’un kablosuz mobil yazdırma çözümleri kullanıcıların güvenli bir ağ üzerinden istedikleri yerde ve istedikleri zaman uzaktan yazdırma işlemi yapmalarını sağlayacak. PrinterOn, hem iOS hem de Android için Intune APP SDK'sıyla tümleştirilecek. Yönetim konsolundaki Intune **Uygulama koruma ilkeleri** dikey penceresi aracılığıyla uygulama koruma ilkelerinde bu uygulamayı hedefleyebileceksiniz. Son kullanıcılar 'PrinterOn for Microsoft' uygulamasını kendi Intune ekosistemlerinde kullanmak üzere Play Store veya iTunes üzerinden indirebilecek.

### <a name="approve-the-company-portal-app-for-android-for-work---1797090---"></a>Android for Work için Şirket Portalı uygulamasını onaylama <!--1797090 -->
Kuruluşunuzda Android for Work kullanılıyorsa, yönetilen Google Play Store'dan otomatik güncelleştirmeleri almaya devam edebilmesini sağlamak üzere Android için Şirket Portalı uygulamasını el ile onaylamanız gerekecek.

### <a name="microsoft-graph-api-for-intune---general-availability-----1833289---"></a>Intune için Microsoft Graph API'si - Genel Kullanılabilirlik  <!-- 1833289 -->
Microsoft Graph'te Intune API'leri, Intune hizmetinde yönetim eylemlerini otomatik hale getirmek için verilere ve yöntemlere programlı erişim sağlayacak.  Bu API'lerin **Genel Kullanılabilirlik** aşaması geldiğinde, müşteriler, iş ortakları ve geliştiriciler API'lerden yararlanarak Intune'la ilgili olan veya Intune desteği gerektiren şirket içi veya ticari çözümleri ya da Microsoft Graph üzerinden sağlanan diğer Microsoft hizmetlerini tümleştirebilecek. 

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Uygulama koruma ilkeleri  <!-- 679615 -->
Intune Uygulama Koruma İlkeleri, tüm kiracıdaki tüm kullanıcılar için hızlı bir şekilde koruma sağlamaya yönelik genel ve varsayılan ilkeler oluşturma olanağı sunar.

### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>iOS - Toplu Satın Alma Programı uygulamalarını iptal etme <!-- 820863 -->
Bir veya daha fazla iOS Toplu Satın Alma Programı (VPP) uygulaması olan belirli bir cihaz için, cihaz için ilişkili cihaza dayalı uygulama lisansını iptal edebilirsiniz. Bir uygulama lisansını iptal etmek ilgili VPP uygulamasını cihazdan kaldırmaz. Bir VPP uygulamasını kaldırmak için, atama işlemini **Kaldır** olarak değiştirmelisiniz. Daha fazla bilgi için bkz. [Microsoft Intune ile toplu satın alma programından satın alınan iOS uygulamalarını yönetme](vpp-apps-ios.md).

### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Bir iOS Toplu Satın Alma Programı belirteci için lisansları iptal et <!-- 820870 -->
Belirli bir VPP Belirteci için tüm iOS Toplu Satın Alma Programı (VPP) uygulamalarının lisansını iptal edebilirsiniz.

### <a name="network-access-control-nac-device-check-in-reporting-----1232250---"></a>Ağ Erişim Denetimi (NAC) cihaz iade raporlama <!-- 1232250 -->
Bu değişiklikten önce BT yöneticileri, NAC tarafından yönetilen bir cihazın Intune tarafında kendi NAC çözümü ile iletişim kurup kurmadığını belirleyemedi. NAC tarafından yönetilen bir cihaz kendi NAC çözümü ile iletişim kurmadığında, cihaz NAC çözümüyle uyumlu değildir ve bu nedenle NAC çözümü tarafından engellenmiş ve daha sonra cihaz uyumluluk durumuna bağlı koşullu erişim ilkeleri tarafından engellenmiştir.

Bu değişiklikle, IT yöneticileri hangi NAC yönetim cihazlarının kendi NAC çözümleriyle başarıyla iletişim kurup kuramadıklarını görebilirler. Bu yeni yetenek, Intune içindeki Cihaz uyumluluk iş yükünde bulunan iki yeni izleme işlevinden oluşur; istatistikler aşağıda gösterilmiştir:
- **Son bir saatteki ortalama NAC çağrıları**
- **Son NAC gelen istek (tarih / saat)**

### <a name="new-ios-device-action------1244701---"></a>Yeni iOS cihaz eylemi  <!-- 1244701 -->
IOS 10.3 denetlenen cihazları kapatabilirsin. Bu eylem, son kullanıcıya herhangi bir uyarı yapılmadan cihazı hemen kapatır. **Cihaz** iş yükünde bir cihaz seçtiğinde, cihaz özelliklerinde **Kapat (yalnızca denetimli)** eylemi bulunabilir.


### <a name="intune-now-provides-the-account-move-operation-----1573558-1579830---"></a>Intune şimdi Hesap Taşıma işlemi sağlıyor <!-- 1573558, 1579830 -->
**Hesap Taşıma** bir kiracıyı bir Azure Ölçeği Birimi'nden (ASU) diğerine taşır. **Hesap Taşı**, hem bunu isteyen Intune destek ekibini aradığınızda istemci tarafından başlatılan senaryolar için, hem de Microsoft'un arka uç hizmetinde ayarlamalar yapması gereken Microsoft tarafından yönetilen bir senaryo olarak kullanılabilir. **Hesap Taşıma** sırasında kiracı salt okunur moda (ROM) girer. ROM süresi boyunca kayıt yaptırma, cihazları yeniden adlandırma, uyumluluk durumunu güncelleme gibi servis işlemleri başarısız olur.




<!-- the following are present prior to 1712 -->
### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Yerleşik uygulama türü kullanarak Office 365 mobil uygulamaları iOS ve Android cihazlara atama <!-- 1332318 -->
**Yerleşik** uygulama türü yönettiğiniz iOS and ve Android cihazlar için Office 365 uygulamaları oluşturmayı ve atamayı kolaylaştırır. Bu uygulamalar Word, Excel, PowerPoint ve OneDrive gibi 0365 uygulamalarını içerir. Uygulama türüne belirli uygulamalar atayabilir ve uygulama bilgileri yapılandırmasını düzenleyebilirsiniz.


### <a name="assignment-conflict-resolution-has-changed-for-ios-store-apps----1480316---"></a>iOS mağaza uygulamaları için atama çakışması çözümlemesi değişti <!-- 1480316 -->
Son kullanıcılar, iOS mağazası uygulamalarının kullanılabilirliğinde bir değişiklikle karşılaşabilir. Şu anda, **Gerekli ve Kullanılabilir** ile **Geçerli değil** arasında bir çakışma ile iki gruba atanan uygulamalar, **Gerekli ve Kullanılabilir** olarak çözümlenir. Değişiklik ile bu çakışmayı yaşayan bir uygulama **Geçerli değil** olarak çözümlenir.

Değişiklik, bir uygulama farklı uygulama amaçlarına sahip birden çok gruba atandığında görülen karışıklığı giderir.

Uygulamanızın Kasım hizmet yayınından önce Bilgi Çalışanı Portalı ve Şirket Portalı’nda kullanılabilir olmasını istiyorsanız iki seçeneğiniz bulunur:

1. Grubunuz için **Geçerli değil** atamasını kaldırın.
2. **Gerekli ve Kullanılabilir** amacı atanmamış yeni bir grup oluşturun ve bu grubu **Geçerli değil** olarak atayın.

Daha fazla bilgi için bkz. [Microsoft Intune ile uygulamaları gruplara atama](apps-deploy.md).

> [!Note]
> Yayından sonra Intune klasik konsolunda Mobil Cihaz Yönetimi (MDM) uygulama atamalarını göremeyecek veya düzenleyemeyeceksiniz. Ancak uygulama atamalarınızı gerçekleştirmek için Azure konsolu veya Intune Graph API’yi kullanabilirsiniz.

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731---"></a>Android for Work cihazlarını Android cihazlardan ayrı olarak yönetme <!-- 1490731 -->
Intune, Android for Work cihazlarının Android platformundan bağımsız olarak kaydını yönetmeyi destekleyecektir. Bu ayarlar **Cihaz Kaydı** > **Kayıt kısıtlamaları** > **Cihaz Türü Kısıtlamaları** altında yönetilir. (Eskiden **Cihaz Kaydı** > **Android for Work Kaydı** > **Android for Work Kayıt Ayarları** altında bulunuyordu.)

Varsayılan olarak, Android for Work cihaz ayarlarınız Android cihazlarınız için ayarlarınızla aynı olacaktır. Ancak Android for Work ayarlarınızı değiştirdikten sonra artık bu durum oluşmaz.
 
Kişisel Android for Work kaydını engellerseniz, yalnızca kurumsal Android cihazlar Android for Work olarak kaydolabilir.

Yeni ayarlarla çalışırken şunları göz önünde bulundurun:

#### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Daha önce hiç Android for Work kaydı eklemediyseniz
Yeni Android for Work platformu varsayılan Cihaz Türü Kısıtlamalarında engellidir. Özelliği ekledikten sonra, cihazların Android for Work ile kaydolmasına izin verebilirsiniz. Bunu yapmak için varsayılan ayarı değiştirin veya varsayılan Cihaz Türü Kısıtlamasının yerine geçen yeni bir Cihaz Türü Kısıtlaması oluşturun.

#### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Android for Work kaydı eklediyseniz
Daha önceden eklediyseniz durumunuz seçtiğiniz ayara bağlıdır:

| Ayar | Varsayılan Cihaz Türü Kısıtlamasında Android for Work durumu | Notlar |
| --- | --- | --- |
| **Tüm cihazları Android olarak yönetme** | Engellendi | Tüm Android cihazların Android for Work ile kaydolması gerekir. |
| **Desteklenen cihazları Android for Work olarak yönetme** | İzin Verildi | Android for Work’ü destekleyen tüm Android cihazların Android for Work ile kaydolması gerekir. |
| **Yalnızca bu gruplardaki kullanıcılar için desteklenen cihazları Android for Work olarak yönetme** | Engellendi | Varsayılan ayarı geçersiz kılmak için ayrı bir Cihaz Türü Kısıtlama ilkesi oluşturuldu. Bu ilke önceden Android for Work kaydına izin vermek için seçtiğiniz grupları tanımlar. Seçili gruplardaki kullanıcıların Android for Work cihazlarını kaydetmesine izin verilir. Diğer tüm kullanıcıların Android for Work ile kaydolması kısıtlanır. |

Tüm durumlarda, hedeflenen düzenlemeniz korunur. Ortamınızda Android for Work’e genel olarak veya grup başına verilen izinleri tutmak için herhangi bir eylem gerçekleştirmeniz gerekmez.

Bu değişiklikler, Kasım güncelleştirmesi ile sunulmaya başlanacaktır ancak hesabınızda yürürlüğe girmesi zaman alabilir. Bu değişiklikler hesabınızda geçerli olduğunda Office 365 portalında bir onay bildirimi alacaksınız.


### <a name="configure-an-ios-app-pin----1586774---"></a>iOS uygulama PIN’i yapılandırma <!-- 1586774 -->
Yakında, hedeflenen iOS uygulamaları için bir PIN’i zorunlu kılmanız mümkün olacaktır. PIN gereksinimini ve sona erme tarihi gün sayısını Azure portalında yapılandırabilirsiniz. Gerektiğinde, kullanıcının bir iOS uygulamasına erişmeden önce yeni bir PIN ayarlaması ve kullanması gerekli olacaktır. Yalnızca Intune Uygulama SDK’sı ile uygulama koruması etkinleştirilmiş iOS uygulamaları bu özelliği destekler.


<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory web siteleri, Intune Managed Browser Uygulaması gerektirebilir ve Managed Browser’da (Genel Önizleme) Çoklu Oturum Açma’yı destekler <!-- 710595 -->   
Azure Active Directory (Azure AD) kullanarak, mobil cihazlarda web sitelerine erişimi Intune Managed Browser uygulaması ile kısıtlayabileceksiniz. Web sitesi verileri, Managed Browser’da güvende ve son kullanıcının kişisel verilerinden ayrı bir yerde olacaktır. Managed Browser ayrıca Azure AD ile korunan sitelerde Çoklu Oturum Açma işlevlerini de destekleyecektir. Managed Browser’da oturum açmak veya Intune tarafından yönetilen başka bir uygulamanın bulunduğu bir cihazda Managed Browser’ı kullanmak, kullanıcıların kimlik bilgilerini girmelerine gerek kalmaksızın Managed Browser’ın Azure AD ile korunan sitelere erişmesine olanak tanır. Bu özellik, Outlook Web Access (OWA) ve SharePoint Online’ın yanı sıra Azure Uygulama Proxy’si yoluyla erişilen intranet kaynakları gibi diğer kurumsal sitelerde de geçerlidir.


<!-- the following are present prior to 1710 -->



### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Windows 10 sürüm yükseltme ilkesi desteği <!-- 903672(archived), 1119689 -->  
Windows 10 cihazları; Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education ve Windows 10 Professional Education N’e yükselten bir Windows 10 sürüm yükseltme ilkesi oluşturabileceksiniz. Windows 10 sürüm yükseltmeleri hakkında daha fazla bilgi için bkz. [Windows 10 sürüm yükseltmelerini yapılandırma](edition-upgrade-configure-windows-10.md).




<!-- the following are present prior to 1709 -->



### <a name="android-for-work-support-for-lookout----1087312---"></a>Lookout için Android for Work desteği <!-- 1087312 -->   
Lookout kullanan Intune bağlayıcısı, Lookout for Work uygulamasını kullanan Android for Work cihazlarını destekleyecektir. Lookout uygulamasını kapsayıcının içinde veya dışında dağıtabilirsiniz.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Intune Uygulama Koruması ve Citrix MDX Geliştirme Araçları<!-- 709185 -->
Cihazları ve uygulamaları Citrix XenMobile MDX ve Microsoft Intune bileşimi ile yönetebilirsiniz. Bu, Citrix’in mVPN teknolojisini kullanırken uygulamaları Intune uygulama koruması ilkesiyle yönetmenize olanak sağlar.

iOS ve Android için Citrix MDX mVPN teknolojisiyle tümleştiren, Intune Uygulama Sarmalama Aracı ve Intune Uygulama SDK’sını içeren bir kod deposu bulabilirsiniz.




<!-- the following are present prior to 1711 -->


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>macOS kullanıcılarını yeni Şirket Portalı uygulamamıza yönlendirme <!--1380728-->   
Bir son kullanıcı, macOS cihazını kaydetmek için Şirket Portalı web sitesinde oturum açtığında, işlemi tamamlamak için yeni macOS Şirket Portalı uygulamasını indirmek üzere yönlendirilecektir. Bu durum, OS X El Capitan 10.11 ve üzeri sürümleri kullanan macOS cihazlarda görülür. 



<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>iOS ve Android için Intune Managed Browser desteği <!-- 1374196 -->
Ekim 2017 itibariyle Android uygulamasındaki Intune Managed Browser uygulaması yalnızca Android 4.4 ve sonraki sürümleri çalıştıran cihazları destekleyecektir. iOS’taki Intune Managed Browser uygulaması yalnızca iOS 9.0 ve sonraki sürümleri çalıştıran cihazları destekleyecektir. Android ve iOS’un daha eski sürümleri Managed Browser'ı kullanmaya devam edebilecek, ancak uygulamanın yeni sürümlerini yükleyemeyecek ve uygulamanın tüm özelliklerine erişemeyecektir. Bu cihazları desteklenen işletim sistemi sürümüne güncelleştirmenizi öneririz.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Kullanıcı, izin verilen en yüksek cihaz kaydı sayısına ulaştığında gösterilen hata iletisi iyileştirildi <!-- 1270370 -->
Genel bir hata iletisi yerine, Android cihazı olan son kullanıcılar kolay, işlem yapılabilir bir hata iletisi görür: “BT yöneticiniz tarafından izin verilen en yüksek cihaz kaydı sayısına ulaştınız. Lütfen kayıtlı bir cihazı kaldırın veya BT yöneticinizden yardım alın.”




## <a name="notices"></a>Bildirimler

Şu anda etkin bildirim yok.




### <a name="see-also"></a>Ayrıca bkz:
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new.md).
