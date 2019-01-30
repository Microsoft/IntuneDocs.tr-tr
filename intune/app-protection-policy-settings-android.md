---
title: Android uygulama koruma İlkesi ayarları | Microsoft Intune
titlesuffix: Microsoft Intune
description: Bu konu başlığı altında Android cihazları için uygulama koruma ilkesi ayarları açıklanır.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 1/28/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9e9ef9f5-1215-4df1-b690-6b21a5a631f8
ms.reviewer: andcerat
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 08848853a70d0fbdabeb123960f36dc19478e6c2
ms.sourcegitcommit: 0142020a7cd75348c6367facf072ed94238e667f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2019
ms.locfileid: "55230061"
---
# <a name="android-app-protection-policy-settings-in-microsoft-intune"></a>Microsoft Intune’da Android uygulama koruma ilkesi ayarları
Bu makalede Android cihazları için uygulama koruma ilkesi ayarları açıklanır. Açıklanan ilke ayarları, Azure portalındaki **Ayarlar** dikey penceresinde bir uygulama koruma ilkesi için [yapılandırılabilir](app-protection-policies.md).
İlke ayarları üç kategoriye ayrılır: veri koruma ayarları, erişim gereksinimlerini ve koşullu başlatma. Bu makalede *ilkeyle yönetilen uygulamalar* terimi, uygulama koruma ilkeleriyle yapılandırılan uygulamaları ifade eder.

##  <a name="data-protection"></a>Veri koruma 
### <a name="data-transfer"></a>Veri aktarımı
| Ayar | Nasıl kullanılır? | Varsayılan değer |
|------|------|------|
| **Android yedekleme hizmeti için kuruluş verilerini yedekleme** | Seçin **blok** bu uygulama için iş veya Okul verileri yedeklemesini engellemek için [Android yedekleme hizmeti](https://developer.android.com/google/backup/index.html).<br><br> Seçin **izin** bu uygulamanın iş veya Okul verilerini yedeklemesine izin vermek için.| **İzin ver** |
| **Uygulamanın diğer uygulamalara organizasyon veri Gönder** | Hangi uygulamaların bu uygulamadan veri alabileceğini belirtin: <ul><li> **İlke ile yönetilen uygulamalar**: Yalnızca diğer ilkeyle yönetilen uygulamalara aktarıma izin verilir.</li> <li>**Tüm uygulamalar**: Herhangi bir uygulamaya aktarıma izin verilir. </li> <li>**Hiçbiri**: İlkeyle yönetilen diğer uygulamalar da dahil olmak üzere herhangi bir uygulamaya veri aktarımına izin verilmez.</li></ul> <p>Intune’un varsayılan olarak veri aktarımı hedefi olarak izin verebileceği bazı muaf uygulamalar ve hizmetler vardır. Buna ek olarak, verilerin Intune APP'yi desteklemeyen bir uygulamaya aktarılmasına izin vermeniz gerekiyorsa kendi muafiyetlerinizi oluşturabilirsiniz. Daha fazla bilgi için [veri aktarımı muafiyetleri](#Data-transfer-exemptions).<p>Bu ilke, Android Uygulama Bağlantıları için de geçerlidir.  Genel web bağlantılarını yönetilen tarafından **uygulama bağlantılarını Intune Managed Browser'da açın** ilke ayarı.<p>**Not:** *Intune şu anda Android Instant Apps özelliğini desteklemiyor. Intune, uygulamaya gelen veya uygulamadan giden tüm veri bağlantılarını engelleyecektir. Daha fazla bilgi için [Android Instant Apps](https://developer.android.com/topic/instant-apps/index.html) Android Geliştirici belgelerinde.*</p>| **Tüm uygulamalar** | 
|<ul><ui> **Dışarıda tutulacak uygulamaları seçin** | Bu seçeneği seçtiğinizde kullanılabilir *ilke ile yönetilen uygulamalar* önceki seçeneği için. | |
| **Diğer uygulamalardan veri almasına** | Hangi uygulamaların bu uygulamaya veri aktarabileceğini belirtin: <ul><li>**İlke ile yönetilen uygulamalar**: Yalnızca diğer ilkeyle yönetilen uygulamalara aktarmaya izin verin.</li><li>**Tüm uygulamalar**: Hiçbir uygulamadan veri aktarımına izin verilir.</li><li>**Hiçbiri**: İlkeyle yönetilen diğer uygulamalar da dahil olmak üzere hiçbir uygulamadan veri aktarımına izin verilmez. </li></ul> <p>Intune’un veri aktarımı kaynağı olarak izin verebileceği bazı muaf uygulamalar ve hizmetler vardır. Uygulama ve hizmetlerin tam listesi için bkz. [Veri aktarımı muafiyetleri](#data-transfer-exemptions). | **Tüm uygulamalar** |
| **Kurumsal verilerin kopyasını Kaydet** | Seçin **blok** bu uygulamada farklı kaydet seçeneğinin kullanımını devre dışı bırakmak için. Seçin **izin** farklı Kaydet'in kullanılmasına izin vermek istiyorsanız. **Not:** *Bu ayar, Microsoft Excel, OneNote, PowerPoint ve Word için desteklenir. Ayrıca üçüncü taraf ve iş KOLU uygulamaları tarafından desteklenebilir.*| **İzin ver** |  
|<ul><ui> **Kopya seçilen cihazlara kaydedebilir izin ver** |Kullanıcılar, seçili hizmetlere (OneDrive İş, SharePoint ve Yerel Depolama) kaydedebilir. Diğer tüm hizmetler engellenir.  | **0 adet seçildi** |
| **Kesme, kopyalama ve kısıtlama diğer uygulamalar arasında** | Bu uygulamada kes, kopyala ve yapıştır eylemlerinin ne zaman kullanılabileceğini belirtin. Aşağıdakilerden birini seçin: <ul><li>**Engellenen**:  Kesme, kopyalama ve yapıştırma eylemlerine bu uygulama ve diğer herhangi bir uygulama arasında izin vermeyecek.</li><li>**İlke ile yönetilen uygulamalar**: Kesme, kopyalama ve yapıştırma eylemlerine bu uygulama ve diğer ilkeyle yönetilen uygulamalar arasında izin verin.</li><li>**Yapıştırma seçeneğiyle ilke ile yönetilen**: Kesme izin verin veya bu uygulama ve diğer ilkeyle yönetilen uygulamalar arasında kopyalama. Herhangi bir uygulamadan verilerin bu uygulamaya yapıştırılmasına izin verir.</li><li>**Herhangi bir uygulama**: Kesme, kopyalama ve yapıştırma için ve bu uygulamadan ilgili bir kısıtlama olmaz. | **Herhangi bir uygulama** |
| **Ekran yakalama ve Google Yardımcısı** | Seçin **devre dışı** için ekran görüntüsü yakalamayı engelle ve **Android Assistant** bu uygulamayı kullanırken cihazın özelliklerini. Seçme **devre dışı** bu uygulama bir iş veya Okul hesabıyla kullanılırken uygulama değiştirici önizleme görüntüsünü de bulanıklaştıran.| **Etkinleştirme** |
  
### <a name="encryption"></a>Şifreleme
| Ayar | Nasıl kullanılır? | Varsayılan değer |
|------|------|------|
| **Kuruluş verilerini şifreleme** | Seçin **gerektiren** bu uygulamada iş veya Okul verilerinin şifrelenmesini etkinleştirmek için. Intune, uygulama verilerini güvenli bir şekilde şifrelemek için 256 bit AES şifreleme düzeni Android Keystore sistemiyle birlikte OpenSSL kullanır. Veriler, dosya GÇ görevleri sırasında eş zamanlı olarak şifrelenir. Cihaz depolamasındaki içerik her zaman şifrelenir. SDK'sı, 128 bit anahtar içeriği ve eski SDK sürümleri kullanan uygulamalar ile uyumluluk için destek sağlamak üzere devam eder. <br><br> Şifreleme yöntemi FIPS 140-2 sertifikalı **değildir**.     |  **gerektirir**|  



### <a name="functionality"></a>İşlevi
| Ayar | Nasıl kullanılır? | Varsayılan değer |
|------|------|------|
| **Yerel kişiler uygulamasına uygulamayla eşitleme** | Seçin **devre dışı** uygulamanın cihazda yerel kişiler uygulamasına veri kaydetmesini engellemek için. Seçerseniz **etkinleştirme**, uygulama verileri cihaz üzerinde yerel kişiler uygulamasına kaydedebilirsiniz. <br><br>Uygulamadan iş veya okul verilerini kaldırmak için seçmeli silme gerçekleştirdiğinizde, yerel Kişiler uygulamasına doğrudan uygulamadan eşitlenen kişiler kaldırılır. Yerel adres defterinden başka bir dış kaynağa eşitlenen kişiler silinemez. Şu anda bu özellik yalnızca Microsoft Outlook uygulaması için geçerlidir. | **Etkinleştirme** |
| **Organizasyon veri yazdırma** | Seçin **devre dışı** uygulamanın iş veya Okul verilerini yazdırmasını engellemek için. | **Etkinleştirme** |
|**İlkeyle yönetilen tarayıcıyla Web içerik paylaşma** | İlkeyle yönetilen uygulamalarda web içeriklerinin (http/https bağlantılarının) nasıl açıldığını belirtin. Aşağıdakilerden birini seçin:<ul><li>**Gerekli**: Web içeriği yalnızca ilkeyle yönetilen tarayıcıda açmak izin verin.</li><li>**Yapılandırılmamış**: Bir uygulamanın Web bağlantılara izin ver </li></ul><br><br> Cihazlarınızı yönetmek için Intune kullanıyorsanız bkz. [Microsoft Intune'la Managed Browser ilkelerini kullanarak İnternet erişimini yönetme](app-configuration-managed-browser.md).<br><br>**İlkeyle yönetilen tarayıcılar**<br>İlkeyle yönetilen tarayıcılardan birden fazla dağıtırsanız, bunların yalnızca biri başlatılır.  Başlatma sırası, Intune Managed Browser ve ardından Microsoft Edge şeklindedir.  Android’de, Intune Managed Browser veya Microsoft Edge yüklü değilse son kullanıcılarınız http/https bağlantılarını destekleyen diğer ilkeyle yönetilen uygulamalardan birini seçebilir.<p>İlkeyle yönetilen bir tarayıcı gerekliyse ancak yüklü değilse, son kullanıcılarınızdan Intune Managed Browser’ı yüklemeleri istenir.<p>İlkeyle yönetilen bir tarayıcı gerekliyse Android Uygulama Bağlantıları, **Uygulamanın diğer uygulamalara veri aktarmasına izin ver** ilke ayarı tarafından yönetilir.<p>**Intune cihaz kaydı**<br>Cihazlarınızı yönetmek için Intune kullanıyorsanız bkz. Microsoft Intune ile yönetilen tarayıcı ilkelerini kullanarak İnternet erişimini yönetme. <p>**İlkeyle yönetilen Microsoft Edge**<br>Mobil cihazlar (iOS ve Android) için Microsoft Edge tarayıcısı, Intune uygulama koruma ilkelerini destekliyor. Microsoft Edge tarayıcı uygulamasında şirket Azure AD hesaplarıyla oturum açan kullanıcılar, Intune tarafından korunur. Microsoft Edge tarayıcısı, MAM SDK’sını tümleştirir ve bu SDK’nın tüm veri koruma ilkelerini destekler ancak şu işlevleri engeller:<br><ul><li>**Kaydet-olarak**: Microsoft Edge tarayıcısı depolama sağlayıcıları (OneDrive gibi) buluta doğrudan, uygulama içi bağlantıları eklemek bir kullanıcı izin vermez.</li><li>**Kişi eşitleme**: Microsoft Edge tarayıcısı için yerel kişi listelerini kaydetmez.</li></ul><br>**Not:** *Uygulama SDK'sı, bir hedef uygulaması bir tarayıcı olup olmadığını belirleyemiyor. Android cihazlarda, http/https hedefini destekleyen diğer yönetilen tarayıcı uygulamalara izin verilir.* | **Yapılandırılmadı** |
| **Üçüncü taraf klavyeler** | Seçin **devre dışı** üçüncü taraf klavyeler yönetilen uygulamalarda kullanılmasını önlemek için. <br><br>Bu ayar etkinleştirildiğinde kullanıcı, üçüncü taraf klavye kullanımının engellendiğini bildiren tek seferlik bir ileti alır. Bu ileti, kullanıcı klavye kullanımı gerektiren kuruluş verileriyle ilk kez etkileşime geçtiğinde görüntülenir. Yönetilen uygulamaları kullanırken yalnızca standart klavye kullanılabilir ve tüm klavye seçenekler devre dışı bırakıldı. Bu ayar, yönetilmeyen uygulamalarda üçüncü taraf klavye kullanımını etkilemez. | **Etkinleştirme** |



  ## <a name="data-transfer-exemptions"></a>Veri aktarımı muafiyetleri

  Intune uygulama koruma ilkesinin, veri aktarımına hedef ve kaynak olarak izin verebileceği bazı muaf uygulamalar ve platform hizmetleri vardır. Örneğin, Android’deki tüm Intune özellikli uygulamalar, Google Metin Okuma’ya ve Google Metin Okuma’dan veri aktarımı gerçekleştirebilmelidir. Böylece mobil cihazınızın ekranındaki metin sesli okunabilir. Bu liste değiştirilebilir ve güvenli verimlilik için kullanışlı olarak nitelendirilen hizmetleri ve uygulamaları yansıtır.

  ### <a name="full-exemptions"></a>Tam muafiyetler

  Bu uygulama ve hizmetlere, Intune tarafından yönetilen uygulamalara ve uygulamalardan veri aktarımına tam olarak izin verilir.

  |Uygulama/hizmet adı | Açıklama |
  | ------ | ---- |
  | com.android.phone | Yerel telefon uygulaması
  | com.android.vending | Google Play Store |
  | com.android.documentsui | Android Belge Seçici|
  | com.google.android.webview | Outlook dahil birçok uygulama için gerekli olan [WebView](https://developer.android.com/reference/android/webkit/WebView.html). |
  | com.android.webview |Outlook dahil birçok uygulama için gerekli olan [WebView](https://developer.android.com/reference/android/webkit/WebView.html).|
  | com.google.android.tts | Google Metin Okuma |
  | com.android.providers.settings | Android sistem ayarları |
  | com.android.settings | Android sistem ayarları |
  | com.azure.authenticator | Birçok senaryoda başarılı kimlik doğrulaması için gerekli olan Azure Authenticator uygulaması. |
  | com.microsoft.windowsintune.companyportal | Intune Şirket Portalı|

  ### <a name="conditional-exemptions"></a>Koşullu muafiyetler
  Bu uygulama ve hizmetlere, yalnızca belirli koşullar altında Intune tarafından yönetilen uygulamalara ve uygulamalardan veri aktarımına izin verilir.

  |Uygulama/hizmet adı | Açıklama | Muafiyet koşulu|
  | ------ | ---- | --- |
  | com.android.chrome | Google Chrome Tarayıcısı | Chrome, Android 7.0+ sürümünde bazı WebView bileşenleri için kullanılır ve görünümden asla gizlenmez. Ancak uygulamaya giden ve uygulamadan gelen veri akışı her zaman kısıtlandırılır.  |
  | com.skype.raider | Skype | Skype uygulamasına yalnızca telefon aramasıyla biten belirli eylemlerde izin verilir. |
  | com.android.providers.media | Android medya içeriği sağlayıcısı | Yalnızca zil sesi seçimi eyleminde izin verilen medya içeriği sağlayıcısı. |
  | com.google.android.gms; com.google.android.gsf | Google Play Hizmetleri paketleri | Bu paketlere, anında iletme bildirimleri gibi Google Cloud Messaging eylemleri için izin verilir. |

Daha fazla bilgi için bkz. [Uygulamalar için veri aktarım ilkesi özel durumları](app-protection-policies-exception.md).

##  <a name="access-requirements"></a>Erişim gereksinimleri

| Ayar | Nasıl kullanılır? | Varsayılan değer |
|------|------|------|
| **Erişim için PIN** | Seçin **gerektiren** bu uygulamayı kullanmak bir PIN istemek için. Uygulamayı iş veya okul bağlamında ilk kez çalıştırdığında kullanıcıdan bu PIN’i ayarlaması istenir. <br><br> PIN gücü için aşağıdaki ayarları yapılandırın:| **gerektirir** |
|<ul><ui> **PIN türü** | Uygulama koruma ilkeleri uygulanmış olan bir uygulama erişmeden önce sayısal veya geçiş kodu türü PIN gereksinimi ayarlayın. Sayısal gereksinimler yalnızca sayıları içerirken, geçiş kodu en az 1 harf **veya** en az 1 özel karakterle tanımlanabilir. <br><br>**Not:** *İzin verilen özel karakterlere Android İngilizce dil klavyesindeki simgeleri ve özel karakterler içerir.*| **Sayısal** |
|<ul><ui>  **Basit PIN** |Seçin **izin** gibi basit PIN dizileri kullanmasına izin vermek *1234*, *1111*, *abcd* veya *aaaa* . Seçin **blok** basit PIN dizileri kullanmalarını engellemek için. <br><br>**Not:** *PIN türü için geçiş kodu ayarlayın ve basit PIN'e izin ver olarak ayarlanmış, kullanıcının en az bir harf olmalıdır. **veya** PIN en az bir özel karakter. PIN türü için geçiş kodu ayarlayın ve basit PIN'e bloğu, kullanıcının en az bir sayı olmalıdır. **ve** bir harf **ve** PIN en az bir özel karakter.* | **İzin ver** |
| <ul><ui> **Minimum PIN uzunluğu seçin** | PIN dizisindeki basamak sayısı alt sınırını belirtin.  | **4** |
|<ul><ui> **(Android 6.0 +) erişim için PIN yerine parmak izi** | Seçin **izin** kullanmasına izin vermek için [parmak izi kimlik doğrulaması](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) uygulama erişiminde PIN yerine. <br><br>**Not:** *Genel denetimler için bu özelliği destekleyen Android cihazlarda biyometrik. Gibi belirli OEM biyometrik ayarlar *Samsung geçişi*, desteklenmez.* <br><br>Android’de kullanıcının kimliğini kanıtlaması için PIN yerine [Android parmak izi kimlik doğrulaması](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) kullanmasına izin verebilirsiniz. Kullanıcı bu uygulamayı iş veya okul hesabıyla kullanmayı denediğinde, PIN girmek yerine parmak izi kimliğini vermesi istenir. <br><br> Android iş profilleri, **PIN yerine parmak izine izin ver** ilkesinin zorlanabilmesi için ayrı bir parmak izi kaydedilmesini gerektirir. Bu ilke yalnızca Android iş profilinde yüklü ilkeyle yönetilen uygulamalarda devreye girer. Bu ayrı parmak izi, Şirket Portalı’na kayıt olunarak Android iş profili oluşturulduktan sonra cihazla kaydedilmelidir. Android iş profillerini kullanan iş profili parmak izleri hakkında daha fazla bilgi için bkz. [İş profilinizi kilitleme](https://support.google.com/work/android/answer/7029958). |**İzin ver** |
| <ul><ul><ui>**Zaman aşımından sonra PIN ile parmak izi geçersiz kıl** |  Ayarlandığında **gerektiren**, bir PIN istemi, Touch ID istemleri kılar, uygulama için boşta kaldıktan sonra *zaman aşımı* belirttiğiniz süre.   | **gerektirir** |
| <ul><ul><ui>**Zaman aşımı (dakika etkin olmama)** | Touch ID istemleri değiştirilmeden önce ne kadar süreyle uygulama boşta kalabileceği dakika cinsinden belirtin. PIN istemler tarafından.  <br><br>Bu zaman aşımı değeri belirtilen değerden büyük olmalıdır *erişim gereksinimlerini yeniden denetle (sonra işlem yapılmayan dakika)*.| **30** |
|<ul><ui> **PIN sıfırlama kaç gün sonra** | Seçin **Evet** kullanıcıların süreyi gün belirli bir süre sonra kendi uygulama PIN'i değiştirmesini zorunlu tutmak için. <br><br> Varsayılan değer = **Hayır** <br><br> Ayarlandığında *Evet*, sıfırlama istenmeden önce gün sonra yapılandırabilirsiniz. | **Yok**|
| <ul><ul><ui>**Gün sayısı** | Zaman *PIN sıfırlamayı kaç gün sonra* Evet olarak ayarlanırsa, belirlemek ne kadar süreyle önce PIN sıfırlama gereklidir. | **0** | 
|<ul><ui> **Uygulama cihaz PIN'i ayarlandığında PIN'i** | Varsa kümesine **devre dışı**, PIN, bir cihaz bir MDM kayıtlı cihazda gerekli olmayan bir uygulama PIN.   | **Etkinleştirme** |
| **İş veya Okul hesabı için erişim kimlik bilgileri** | Seçin **gerektiren** uygulama erişimi için PIN girmek yerine kendi iş veya Okul hesabıyla oturum açmasını istemek için. Ayarlandığında **gerektiren**, PIN veya biyometrik istemleri açık üzerinde Kurumsal kimlik bilgileri ve her iki PIN veya biyometrik istemleri gösterilir. | **Gerekli değil** |
| **Erişim gereksinimlerini yeniden denetle (sonra işlem yapılmayan dakika)** | Uygulama erişim gereksinimlerini yeniden belirtmek için kullanıcıyı gerekiyor. önce geçmesi gereken işlem yapılmayan dakika sayısını yapılandırın.  <br><br>**Not:** *Android'de PIN, tüm Intune ile yönetilen uygulamalar ile paylaşılır. Uygulama cihazda ön plandan ayrıldığında, PIN zamanlayıcısı sıfırlanır. Bu ayarda tanımlanan zaman aşımı süresince Intune ile yönetilen PIN'ini paylaşan herhangi bir uygulamada kullanıcının bir PIN girmesi gerekmez.*| **30** |


> [!NOTE]  
> Erişim bölümünde yapılandırılan birden çok Intune uygulama koruma ayarının, aynı uygulama ve kullanıcı grubu için iOS'ta nasıl çalıştığı hakkında daha fazla bilgi edinmek için bkz. [Intune MAM sık sorulan sorular](mam-faq.md) ve [Intune’da uygulama koruma ilkesi erişim eylemlerini kullanarak verileri seçmeli olarak silme](app-protection-policies-access-actions.md).


## <a name="conditional-launch"></a>Koşullu başlatma
Erişim koruma ilkenize oturum açmak için güvenlik gereksinimleri ayarlamak için koşullu başlatma ayarlarını yapılandırın. 

Varsayılan olarak bazı ayarlara önceden yapılandırılmış değer ve eylemler sağlanır. *En düşük işletim sistemi sürümü* gibi bazı ayarları silebilirsiniz. Ayrıca **Birini seçin** açılır penceresinden ek ayarlar da seçebilirsiniz. 

| Ayar | Nasıl kullanılır? |  
|---------|------------| 
| **En fazla PIN denemesi** | Kullanıcının yapılandırma eylemi gerçekleştirmek zorunda kalmadan önce başarılı bir şekilde girmesi gereken PIN deneme sayısını belirtin. Bu ilke ayarı biçimi pozitif tamsayıyı destekler. *Eylemler* şunları içerir: <br><ul><li>**PIN sıfırla** - Kullanıcının PIN’ini sıfırlaması gerekir.</li></ul> <ul><li>**Verileri sil** - Uygulamayla ilişkili kullanıcı hesabı cihazdan silinir.  </li></ul> </li></ul> Varsayılan değer = **5** |
| **Çevrimdışı yetkisiz kullanım süresi** | MAM uygulamalarının çevrimdışı çalıştırılabileceği dakika sayısıdır. Uygulama için erişim gereksinimleri yeniden denetlenmeden önce geçmesi gereken süreyi (dakika cinsinden) belirtin. *Eylemler* şunları içerir: <br><ul><li>**Erişimi engelle (dakika)** - MAM uygulamalarının çevrimdışı çalıştırılabileceği dakika sayısıdır. Uygulama için erişim gereksinimleri yeniden denetlenmeden önce geçmesi gereken süreyi (dakika cinsinden) belirtin. Bu süre dolduktan sonra, uygulamanın çalıştırılmaya devam edebilmesi için Azure Active Directory'de (Azure AD) kullanıcı kimlik doğrulaması yapılması gerekir. <br><br>Bu ilke ayarı biçimi pozitif tamsayıyı destekler. <br><br>Varsayılan değer = **720** dakika (12 saat) </li></ul> <ul><li>**Verileri sil (gün)**: Uygulama, yönetici tarafından tanımlanan bu süre içerisinde çevrimdışı çalıştığında kullanıcıdan ağa bağlanmasını ve yeniden kimlik doğrulamasını ister. Kullanıcı başarıyla oturum açarsa, verilerine erişmeye devam edebilir ve çevrimdışı zaman aralığı sıfırlanır.  Kullanıcı kimlik doğrulaması başarısız olursa uygulama, kullanıcı hesabı ve verilerinde seçmeli silme gerçekleştirir. Daha fazla bilgi için bkz. [Intune tarafından yönetilen uygulamalardan kurumsal verileri temizleme](https://docs.microsoft.com/intune/apps-selective-wipe).</li></ul> Bu ilke ayarı biçimi pozitif tamsayıyı destekler. <br><br>  Varsayılan değer = **90 gün** </li></ul> <br><br>  Bu girdi, her örnek farklı eylemi destekleyecek şekilde birden fazla kez görünebilir. |   
| **Jailbreak uygulanmış/kök erişim izni verilmiş cihazlar** |Bu ayarın değeri yoktur. *Eylemler* şunları içerir: <br><ul><li>**Erişimi engelle**  - Bu uygulamanın jailbreak uygulanmış veya kök erişim izni verilmiş cihazlarda çalışması engelleyin. Kullanıcı kişisel görevler için uygulamaları kullanmaya devam edebilir, ancak bu uygulamada iş veya okul verilerine erişmek için farklı bir cihaz kullanması gerekir.</li></ul> <ul><li>**Verileri sil** - Uygulamayla ilişkili kullanıcı hesabı cihazdan silinir.  </li></ul> |
| **En düşük işletim sistemi sürümü** | Bu uygulamayı kullanmak için gereken bir en düşük Android işletim sistemini belirtin. *Eylemler* şunları içerir: <br><ul><li>**Uyar** - Cihazın Android sürümü gereksinimi karşılamıyorsa, kullanıcı bir bildirim görür. Bu bildirim kapatılabilir.  </li></ul> <ul><li>**Erişimi engelle** - Cihazın Android sürümü bu gereksinimi karşılamıyorsa, kullanıcının uygulamaya erişimi engellenir.</li></ul> <ul><li>**Verileri sil** - Uygulamayla ilişkili kullanıcı hesabı cihazdan silinir.  </li></ul> </li></ul>Bu ilke ayarı biçimi birincil.ikincil, birincil.ikincil.derleme, birincil.ikincil.derleme.düzeltme'yi destekler. |
| **En düşük uygulama sürümü** | En düşük işletim sistemi için bir değer belirtin. *Eylemler* şunları içerir: <br><ul><li>**Uyar** - Cihazdaki uygulama sürümü gereksinimi karşılamıyorsa kullanıcı bir bildirim görür. Bu bildirim kapatılabilir.</li></ul> <ul><li>**Erişimi engelle** - Cihazın uygulama sürümü gereksinimi karşılamıyorsa, kullanıcının uygulamaya erişimi engellenir. </li></ul> <ul><li>**Verileri sil** - Uygulamayla ilişkili kullanıcı hesabı cihazdan silinir. </li></ul> </li></ul> Uygulamalar arasında genellikle farklı sürüm şemaları bulunduğundan, en az bir uygulama sürümünün bir uygulamayı hedeflediği (*Outlook sürümü ilkesi* gibi) bir ilke oluşturun.<br><br> Bu girdi, her örnek farklı eylemi destekleyecek şekilde birden fazla kez görünebilir.<br><br> Bu ilke ayarı biçimi birincil.ikincil, birincil.ikincil.derleme, birincil.ikincil.derleme.düzeltme'yi destekler.|
| **En düşük düzeltme eki sürümü** | Google tarafından yayınlanan Android güvenlik düzeltme eklerinde alt sınır gerektirin.  <br><ul><li>**Uyar** - Cihazın Android sürümü gereksinimi karşılamıyorsa, kullanıcı bir bildirim görür. Bu bildirim kapatılabilir.  </li></ul> <ul><li>**Erişimi engelle** - Cihazın Android sürümü bu gereksinimi karşılamıyorsa, kullanıcının uygulamaya erişimi engellenir.</li></ul> <ul><li>**Verileri sil** - Uygulamayla ilişkili kullanıcı hesabı cihazdan silinir.  </li></ul></li></ul> Bu ilke ayarı *YYYY-AA-GG* tarih biçimini destekler. |
| **Cihaz üreticisi/üreticileri** | Bu uygulamayı kullanmak için gereken bir cihaz üreticisi belirtin. *Eylemler* şunları içerir: <br><ul><li>**Belirtilenlere izin ver (belirtilmeyenleri engelle)** - Yalnızca belirtilen üreticiyle eşleşen cihazlar uygulamayı kullanabilir. Diğer tüm cihazlar engellenir. </li></ul> <ul><li>**Belirtilenlere izin ver (belirtilmeyenleri sil)** - Uygulamayla ilişkili kullanıcı hesabı cihazdan silinir. </li></ul> |
