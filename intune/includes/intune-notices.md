---
ms.openlocfilehash: dc86f2c22410236368753acd4dd3b66698037241
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57736845"
---

Bu bildirimler önemli yardımcı olabilecek bilgiler, gelecekteki Intune değişiklikler ve özellikler için hazırlama belirtin. 

### <a name="change-in-enrollment-workflow-with-intune-company-portal-on-corporate-ios-devices-authenticating-with-setup-assistant----1927359---"></a>Kurulum Yardımcısı ile kimlik doğrulaması Kurumsal iOS cihazlarında Intune Şirket portalı ile iş akışı kayıt Değiştir <!-- 1927359 -->
Kurulum kullanırken iOS cihazlarını Apple'nın Kurumsal cihaz kayıt yöntemleri - Apple Configurator, Apple İşletme Yöneticisi, Apple School Manager veya Apple aygıt kayıt programı (DEP) aracılığıyla iş akışı yaklaşan bir değişiklik olduğunu Kimlik Doğrulama Yardımcısı. Bu değişiklik, yalnızca kullanıcı benzeşimi ile kaydedilen cihazlar için geçerlidir.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Ne zaman bu değişiklik alındı ~~Mart~~ cihazların kimliklerini nasıl doğrulayacaklarını belirtebilirsiniz ve Şirket portalı uygulaması'na alırsanız Azure portalında ıntune'da kayıt profilleri Nisan ayında güncelleştirilir. Yukarıda listelenen yöntemleri aracılığıyla iOS cihazlarını kaydetmek için Gelişmiş bir iş akışı olacaktır. Not:

- Ne zaman yeni cihaz kaydetmek ve Kurulum Yardımcısı ile kimlik doğrulaması, size Şirket portalı uygulamasını otomatik olarak dağıtmak depolamamayı mümkün olacaktır. Son kullanıcılar, artık "Aygıtınızı" ekran ve kayıt akışını "Onayla Cihazınızı" ekran görürsünüz.  
- Koşullu erişimi etkinleştirmek istiyorsanız Kurulum Yardımcısı ile Apple'nın Kurumsal cihaz kayıt yöntemleri biri aracılığıyla kayıtlı cihazlar üzerinde eylem atmanız gerekir. Şirket portalı bu cihazlara yayar göndermek için belirli bir xml ile bir uygulama yapılandırma İlkesi yapılandırmanız gerekiyor. Bunu yapmak için yönergeleri ek bilgi bağlantıdaki blog gönderisinde var. Bu şekilde Şirket portalı göndermeyi seçerseniz, son kullanıcılar artık "Aygıtınızı" ekran ve kayıt akışını "Onayla Cihazınızı" ekran görürsünüz. 
- Şirket portalı'yla dağıtmadıysanız, bu değişiklik, alındıktan sonra son kullanıcıların yükleme uygulamayı Şirket portalı uygulamasından depolamak, bunlar, oturum ancak gerekir ve uygulama yapılandırma profili yukarıda belirtilen bir hata iletisi alırsınız. Bunlar, uygulama için koşullu erişim kullanmanın mümkün olmayacaktır. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Değiştirilen iş akışı kullanmayı planlıyorsanız, göstermek için son kullanıcı kılavuzu güncelleştirmek isteyebilirsiniz:

- Son kullanıcılar artık kayıt akışta Yukarıdaki iki ekran görür. 
- Otomatik olarak dağıtıldığında, şirket portalında oturum açın ve uygulama Mağazası'ndan indirilmemesi gerekir. 

Bir uygulama yapılandırma İlkesi artık gerekirse, bu değişikliğin hazırlık oluşturmayı seçebilirsiniz. Bu yeni iş akışı dağıtıldığında, güncelleştirilmiş kayıt profilleri konsolunda görürsünüz. Biz de bu piyasaya çıkma ileti merkezi yoluyla sizi bilgilendirmek. Bundan sonra son kullanıcılar, Kurulum Yardımcısı ile kimlik doğrulaması yaparak DEP aracılığıyla kaydedebilir ve koşullu erişim için şirket portalını kullanabilir, böylece eyleme gerekecektir.

Bu değişiklik hakkında daha fazla ayrıntı için ek bilgi bağlantısına gönderi destek blog gönderimize göz atabilirsiniz.

#### <a name="additional-information"></a>Ek bilgi 
[https://aka.ms/enrollment_setup_assistant](https://aka.ms/enrollment_setup_assistant)


### <a name="company-portal-changes-for-ios-122-enrollment-in-intune"></a>Intune'da iOS 12.2 kayıt için Şirket portalı değişiklikleri
Apple iOS cihazlarında mobil cihaz Yönetimi (MDM) hizmetlerine kaydetme ile ilgili bazı değişiklikler açıkladı MC172534 içinde paylaşılmıştı. Değişiklik büyük olasılıkla tüm gelecek iOS sürümleri yanı sıra Mart 2019 yakında iOS sürümü görülür. Apple'nın değişiklikleri yansıtmak için şirket Portalı'nda bazı güncelleştirmeler yapıyoruz. 
 
#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Son kullanıcılarınızın cihazlarını iOS 12.2 ve yukarıda yükseltirseniz, bilmeniz değiştirilmiş bir iş akışı ve ıntune'a kaydı için ek adımlar uygulamanız gerekir. Intune Mart güncelleştirmeden sonra İşte yapabileceklerini-  

- Bir yönetim profili yüklemek için Şirket portalı uygulamasında kayıt işlemi başlar
- Git Ayarları > Genel > profiller ve kırmızı rozet bildirim arayın
- Doğru profili seçin ve aracılığıyla için Yükle'ye tıklayın.
- Şirket portalı kaydı için geri dönün

Ek bilgi kayıt akışını hakkında ayrıntılı bilgi için tıklayın.

Kaydı ve yeni bir kayıt, zaten kayıtlı ve yükseltme iOS 12.2 cihazlar gerekir ve yukarıda etkilenen olmamalıdır. Kayıt deneyimi 12,1 ya da daha önceki iOS çalıştıran cihazlarda, Apple tarafından bu yeni sürümle birlikte değişmez. Bir veya Apple'nın Kurumsal kayıt yöntemleri (cihaz kayıt programı, Apple School Manager veya Apple İşletme Yöneticisi) ile kaydedilen cihazlar etkilenmez.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapabilirim?
Belgelerinize ve, son kullanıcı kılavuzu yükseltmek planlamanız gerekir. Bu değişiklikler bilmeniz, Yardım Masası izin isteyebilirsiniz. Sizi bu değişiklik Canlı olduğunda müşterilerimize yenilikler bilgilendirmeyi saklayacağız. 

Şirket portalı değişiklikleri sunuyoruz yararlanmak son kullanıcılarınızın Intune Mart güncelleştirmesi hizmet sonra ne zaman cihazlarını yeni iOS sürümü için güncelleştirme isteyin şirket Portalı Uygulama sürümü 3.9.0. serbest bırakılır.

Şirket portalı değişiklikleri Önizleme ekran görüntüleri ile bir destek blog gönderisi için ek bilgi tıklayın.

Ek Bilgiler [https://aka.ms/CP_changes_iOS12](https://aka.ms/CP_changes_iOS12)

### <a name="plan-for-change-workflow-changes-for-ios-12-enrollment-in-intune"></a>Değişiklik planı: Intune'da iOS 12 kayıt için iş akışı değişiklikleri
Apple iOS cihazlarında mobil cihaz Yönetimi (MDM) hizmetlerine kaydetme ile ilgili bazı değişiklikler açıkladı. Değişiklik büyük olasılıkla tüm gelecek iOS sürümleri yanı sıra iOS spring 2019 sürümü görülür.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Son kullanıcılarınızın cihazlarını iOS 12 Bu yeni sürümüne içinde spring yükseltirseniz, bilmeniz değiştirilmiş bir iş akışı ve ıntune'a kaydı için ek adımlar atmanız gerekir. Bu değişiklik Apple getirir, son kullanıcıların gerekir:

- Bir yönetim profili yüklemek için Şirket portalı uygulamasında kayıt işlemi başlar
- Git Ayarları > Genel > profiller
- Doğru profili seçin ve aracılığıyla için Yükle'ye tıklayın.
- Şirket portalı kaydı için geri dönün 

Kaydı ve yeni bir kayıt, zaten kaydedilen cihazlar gerekir ve yükseltme yeni iOS sürüm sürece etkilenen olmamalıdır.

Kayıt deneyimi 12,1 ya da daha önceki iOS çalıştıran cihazlarda, Apple tarafından bu yeni sürümle birlikte değişmez.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapabilirim?
Belgelerinize ve, son kullanıcı kılavuzu yükseltmek planlamanız gerekir. Bu değişiklikler bilmeniz, Yardım Masası izin isteyebilirsiniz. Sizi ileti merkezi bilgilendirmeyi saklayacağız ve bu değişiklik Canlı olduğunda müşterilerimize yenilikler.

#### <a name="additional-information"></a>Ek bilgi
[Destek blog gönderisinden yararlanarak ekran görüntüleri ve beklenen kayıt akışını gösteren video](https://aka.ms/iOS_enrollment_changes).

### <a name="plan-for-change-user-experience-update-to-intune-company-portal-app-for-ios"></a>Değişiklik planı: İOS için Intune Şirket portalı uygulamasında kullanıcı deneyimi güncelleştirmesi
Bir kullanıcı deneyimi güncelleştirmesi iOS Şirket portalı uygulaması için Intune yakında yayımlar paylaşmak heyecan duyuyoruz. Güncelleştirme Gelişmiş Filtreler ve daha hızlı erişim için uygulamalar ve Kitaplar visual yeniden giriş sayfasının özellik.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Bulunacak geçerli iOS Şirket portalı işlevselliği, bakımı sırasında bu kullanıcı deneyimi güncelleştirmesi:
- Yerel iOS görünüm ile bir giriş sayfası 
- İçerik listeleri ve içerik türünü (uygulamaları veya e-Kitaplar) ve kullanılabilirlik (cihaz Yönetimi gerekli veya Kayıtsız kullanılabilir) göre filtreleme özelliği dahil olmak üzere arama, filtreleme yetenekleri
- E-Kitaplar arama özelliği
- Arama Geçmişi uygulamaları ve e-Kitaplar

Apple TestFlight programı bir parçası kullanıyorsanız, kullanılabilir olduğunda Intune'un güncelleştirilmiş iOS Şirket portalı uygulaması yayın öncesi sürümü hakkında bildirilir. Apple TestFlight programı parçası değilseniz çok geç kaydetmek için değil. Kaydetme, son kullanıcılarınız için kullanılabilir olmadan önce güncelleştirilmiş Şirket portalı uygulamasını kullanmaya olanak sağlar. Doğrudan Intune ekibine geri bildirim de sağlayabilirsiniz.  

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapabilirim?
Herhangi bir eylemde bulunmanız gerekmez; Bu değişiklikler, gelecek iOS CP uygulama sürümde kullanıma sunulacaktır. 

#### <a name="additional-information"></a>Ek bilgi
[https://aka.ms/cp_update_iOS](https://aka.ms/cp_update_iOS)


### <a name="reminder-removal-of-existing-exchange-online-to-intune-connectors----3105122---"></a>Anımsatıcı: Var olan Exchange Online için Intune bağlayıcılar kaldırma <!-- 3105122 -->
Biz Exchange Online için Intune 'Hizmet' bağlayıcı işlevini gelecek bir güncelleştirmede kaldırma, MC165575 içinde paylaşılmıştı. Şubat güncelleştirmesiyle Intune hizmetine yeni bağlayıcılar belirlemek için bu düğmeyi devre dışı bırakırız. Tüm mevcut Exchange Online için Intune bağlayıcılar Mart 2019 kaldırmak planlıyorsanız.
 
#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
'Hizmet' bağlayıcı işlevini ortamınızda kullanmakta olduğunuz, Kayıtlarımıza göre bu yana bu iletiyi alıyorsunuz. 'Hizmet' Bağlayıcısı, Exchange Online için Exchange Active Sync yalnızca cihazların Intune yönetimini destekler ve şirket içi altyapı desteklemiyor. Koşullu erişim (CA) için gerekli olduğu konsolunda görüntülenme şeklini nedeniyle bu bağlayıcının görünür olduğunda gerçekte, bu CA için gerekli değildir. Bu bağlayıcı kullanımı ve Exchange Online koşullu erişim uygulanmadan önce anlamak için kullanmakta olduğunuz. Bu bilgiler, Microsoft 365 Yönetim Merkezi tarafından zaten sağlanır. Burada, bulabilirsiniz yazın uygulaması dahil olmak üzere Exchange Online 7 ile 180 gün arasında kullanılan kullanım raporları sağlar. Daha fazla bilgi için [Office 365 Yönetim Merkezi - e-posta uygulamaları kullanım raporlarında](https://docs.microsoft.com/office365/admin/activity-reports/email-apps-usage?view=o365-worldwide).  
 
Ortamınızda bu bağlayıcıyı kullanmak, izlemek veya Şubat ayında bağlayıcıları devre dışı bıraktıktan sonra Intune'da Exchange Active Sync yalnızca cihazları temizlemek mümkün olmayacaktır. Bu değişiklik sırasında son kullanıcılarınıza beklenen hiçbir etkisi yoktur.
 
#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapabilirim?
Hizmetten hizmete bağlayıcı ayarlama ve Exchange Active Sync yalnızca cihazınız varsa, cihazlarınızı yönetmek için diğer yöntemler geçin. Aşağıdaki seçenekleriniz vardır:

- Mobil cihaz Yönetimi (MDM) cihazlarını kaydetme 
- Cihazlarınızı yönetmek için Intune uygulama koruma ilkelerini kullanma 
- Belgelerinde belirtildiği gibi Exchange denetimleri kullanın [burada](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/clients-and-mobile-in-exchange-online) 

#### <a name="additional-information"></a>Ek bilgi  
https://docs.microsoft.com/intune/exchange-service-connector-configure




### <a name="check-your-delay-visibility-of-software-updates-setting-in-intune"></a>Intune, "Yazılım güncelleştirmelerinin gecikme görünürlük" ayarını denetleyin 

Biz size birkaç ayar konsolda gezinmek MC171466 paylaşılmaz. Intune Mart güncelleştirmesinde tamamen "Gecikme görünürlüğünü yazılım güncelleştirmeleri" ayarı iOS güncelleştirme ilkesi dikey penceresinden kaldıracağız. Bu, zamanlanmış yazılım güncelleştirmeleri uygulamaya biçimini değiştirmez, ancak bir güncelleştirme görünürlüğünü son kullanıcılar için ne kadar süreyle geciktirileceğini etkileyebilir. Bu ayarı kullanıyorsanız Mart bitmeden önce harekete gerekebilir. 

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Şubat Intune hizmet güncelleştirmesinden sonra ayarı konsolunda ve iOS cihaz kısıtlama profillerinde hem de yazılım güncelleştirme dikey penceresinde ilkeleri güncelleştirmek için görüntülendiğini fark edeceksiniz. Konsolunda bu değişikliği gördüğünüzde, işte yapmanız gerekebilir.

- İOS için var olan güncelleştirme ilkeleri için: Özel varsa bu ayarı varsayılan dışında bir 30 gün, yapılandırılmış ve Mart sonunda uygulamaya devam etmek gecikme görünürlük ayar için mevcut yapılandırmalarınızı istediğiniz, yeni bir iOS cihaz kısıtlama profili oluşturmak zorunda kalırsınız. Burada, gecikme görünürlük ayarı mevcut iOS güncelleştirme ilkesini olduğu gibi aynı değerlere sahip ve aynı gruplara hedeflenmesi gerekir. Mart hizmet güncelleştirmesinden sonra artık, artık bu dikey pencerede görünür olacak olduğundan bu ayarda mevcut iOS güncelleştirme ilkeleri için değerlerini düzenlemek mümkün olmayacak. Bunun yerine, yeni profillerinde bu ayarı yapılandırır.
  Gün sayısı değeri geciktirebilir görünürlük konumlarının her ikisinde de gecikme ayarı çalışmaz, görünürlük özel yapılandırılmış ayar değerleri eşleşmiyor ve kullanılabilir duruma geldiği son kullanıcılar, cihazlarında güncelleştirmeyi görür. Diğer ayarlar yazılım güncelleştirme ilkesi dikey penceresinde her zaman bu konsolda üzerinden öncelik yaptıktan sonra bu çoğu müşteri için çok az etkisi olabilir.
- İOS için yeni güncelleştirme ilkeleri için: Intune Şubat hizmet güncelleştirmesinden sonra yazılım güncelleştirmeleri dikey penceresinde yeni ilkeler oluşturacağınız çalışırsanız, bu ayar gri görürsünüz. Konsolunda güncelleştirmeleri görünürlüğünü geciktirmek istiyorsanız cihaz yapılandırma dikey penceresine yeniden yönlendirme Not görürsünüz.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapabilirim?
Bu ayar kullanmayın veya son kullanıcılarınız için görünürlük yazılım güncelleştirmelerinin gecikme istemiyorsanız, eylem gerekmez.

Cihaz kısıtlamaları'nın altında cihaz yapılandırma dikey penceresinde yeni profillerinde ayarını yapılandırma güncelleştirmeleri görünürlüğünü geciktirmek istiyorsanız, başlangıç > Genel. Varsa bu ayarı özel mevcut iOS güncelleştirme ilkeleri yapılandırılmış, kullanıcılarınız için güncelleştirmelerin görünürlüğünü gecikme "gün" için aynı değere sahip yeni bir eşdeğer cihaz kısıtlama profili oluşturun, sonra Şubat ve Mart önce güncelleştirme dağıtılırken. 

BT Pro rehberi güncelleştirin ve Yardım masanız bildirmek isteyebilirsiniz.

Bu ayarı yapılandırma hakkında daha fazla ayrıntı için ek bilgileri Gönder destek blog gönderimize göz atabilirsiniz.

#### <a name="additional-information"></a>Ek bilgi 
[https://aka.ms/Delay_visibility_setting_iOS](https://aka.ms/Delay_visibility_setting_iOS)
