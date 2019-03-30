---
title: include dosyası
description: include dosyası
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 073115d33f9a4f22fe3706ef15860c2a8d8a68ee
ms.sourcegitcommit: 69aaf89140f82f344404e75a69dc59d8a1585b10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/30/2019
ms.locfileid: "58675502"
---
Bu bildirimler önemli yardımcı olabilecek bilgiler, gelecekteki Intune değişiklikler ve özellikler için hazırlama belirtin. 

### <a name="change-in-enrollment-workflow-with-intune-company-portal-on-corporate-ios-devices-authenticating-with-setup-assistant----1927359---"></a>Kurulum Yardımcısı ile kimlik doğrulaması Kurumsal iOS cihazlarında Intune Şirket portalı ile iş akışı kayıt Değiştir <!-- 1927359 -->
Kurulum kullanırken iOS cihazlarını Apple'nın Kurumsal cihaz kayıt yöntemleri - Apple Configurator, Apple İşletme Yöneticisi, Apple School Manager veya Apple aygıt kayıt programı (DEP) aracılığıyla iş akışı yaklaşan bir değişiklik olduğunu Kimlik Doğrulama Yardımcısı. Bu değişiklik, yalnızca kullanıcı benzeşimi ile kaydedilen cihazlar için geçerlidir.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Ne zaman bu değişiklik alındı ~~Mart~~ cihazların kimliklerini nasıl doğrulayacaklarını belirtebilirsiniz ve Şirket portalı uygulaması'na alırsanız Azure portalında ıntune'da kayıt profilleri Nisan ayında güncelleştirilir. Yukarıda listelenen yöntemleri aracılığıyla iOS cihazlarını kaydetmek için Gelişmiş bir iş akışı olacaktır. 

- Ne zaman yeni cihaz kaydetmek ve Kurulum Yardımcısı ile kimlik doğrulaması, size Şirket portalı uygulamasını otomatik olarak dağıtmak depolamamayı mümkün olacaktır. Son kullanıcılar, artık "Aygıtınızı" ekran ve kayıt akışını "Onayla Cihazınızı" ekran görürsünüz.  
- Koşullu erişimi etkinleştirmek istiyorsanız Kurulum Yardımcısı ile Apple'nın Kurumsal cihaz kayıt yöntemleri biri aracılığıyla kayıtlı cihazlar üzerinde eylem atmanız gerekir. Şirket portalı bu cihazlara yayar göndermek için belirli bir xml ile bir uygulama yapılandırma İlkesi yapılandırmanız gerekiyor. Bunu yapmak için yönergeleri ek bilgi bağlantıdaki blog gönderisinde var. Bu şekilde Şirket portalı göndermeyi seçerseniz, son kullanıcılar artık "Aygıtınızı" ekran ve kayıt akışını "Onayla Cihazınızı" ekran görürsünüz. 
- Şirket portalı'yla dağıtmadıysanız, bu değişiklik, alındıktan sonra son kullanıcıların yükleme uygulamayı Şirket portalı uygulamasından depolamak, oturum açabilirsiniz ancak gerekir ve uygulama yapılandırma profili yukarıda belirtilen bir hata iletisi alırsınız. Bunlar, uygulama için koşullu erişim kullanmanın mümkün olmayacaktır. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Değiştirilen iş akışı kullanmayı planlıyorsanız, göstermek için son kullanıcı kılavuzu güncelleştirmek isteyebilirsiniz:

- Son kullanıcılar artık kayıt akışta Yukarıdaki iki ekran görür. 
- Otomatik olarak dağıtıldığında, şirket portalında oturum açın ve uygulama Mağazası'ndan indirilmemesi gerekir. 

Bir uygulama yapılandırma İlkesi artık gerekirse, bu değişikliğin hazırlık oluşturmayı seçebilirsiniz. Bu yeni iş akışı dağıtıldığında, güncelleştirilmiş kayıt profilleri konsolunda görürsünüz. Biz de bu piyasaya çıkma ileti merkezi yoluyla sizi bilgilendirmek. Bundan sonra son kullanıcılar, Kurulum Yardımcısı ile kimlik doğrulaması yaparak DEP aracılığıyla kaydedebilir ve koşullu erişim için şirket portalını kullanabilir, böylece eyleme gerekecektir.

Bu değişiklik hakkında daha fazla ayrıntı için ek bilgi bağlantısına gönderi destek blog gönderimize göz atabilirsiniz.

#### <a name="additional-information"></a>Ek bilgi 
[https://aka.ms/enrollment_setup_assistant](https://aka.ms/enrollment_setup_assistant)

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

### <a name="plan-for-change-upcoming-fix-for-windows-10-email-profiles-in-intune---3904031--"></a>Değişiklik planı: Intune'da Windows 10 e-posta profilleri için düzeltme <!--3904031-->
Intune e-posta profilleri için Windows 10 Nisan ayında, e-posta profilleri Windows 10 sürümleri gelecek çalışmaya devam etmesini sağlamak için de bir hatayı düzeltmek için Intune hizmetine güncelleştirme Yazar şekilde güncelleştiriyoruz. Bu düzeltme dağıtıldıktan sonra yapmanız gereken bir eylem yoktur.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Windows 10 ile e-posta profilleri kullanıyorsanız, bu değişiklik, etkiler
- Windows 10 Masaüstü cihazlarda yerel e-posta istemcisi veya
- Windows 10 Mobile Outlook e-posta istemcisi

Bu, hem Intune tek başına ve karma mobil cihaz Yönetimi (MDM) müşterilerini etkiler.

Nisan güncelleştirmesi dağıtılırken sonra Intune konsolunda (karma MDM kullanıyorsanız, Configuration Manager Yönetici Konsolu) bu profilleri yeniden oluşturmanız gerekir.

Eylem yapmazsanız, işte Nisan güncelleştirmeden önce oluşturulan profiller için görürsünüz:

- Var olan e-posta profili Intune konsoluna veya Configuration Manager Yönetici Konsolu, hata durumunda gösterilir, ancak son kullanıcılar e-posta erişime sahip olmaya devam. Ancak, sonraki bir Windows güncelleştirmesi dağıtılırken sonra bu profilleri çalışmaz. Son kullanıcılar bu profilleri ile hedeflenen cihazlarda e-posta erişimini kaybedecek.
- Cihazları bu profillere Nisan içinde yansıtılmaz sonra yapılan düzenlemeler hedeflenen.
- Bu profiller bile düzeltme Nisan'da kullanıma sunulma sonra kaldırmak için seçmeli temizleme çalışmaz.

Eylem ve e-posta profilleri yeniden oluşturmanız, son kullanıcıların bir e-posta profili için ilk kez dağıttığınızda benzer adımlarını gerekecektir. Kullanıcılar yeni profili geçerli olan güncelleştirmeyi kabul edene kadar eşitlenmesini kendi e-posta engellenir.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Yalnızca düzeltme Nisan güncelleştirmesi ile kullanıma sonra eylem yapması gerekmez. Intune profillerinizde yeniden oluşturmak başlatabilmeniz bu değişiklik Canlı aşması durumunda biz size ileti merkezi ulaştıracağız.

Intune'da Windows 10 e-posta profilleri kullanıyorsanız, aşağıdaki adımları uygulamanız gerekir:

1. Mevcut Win 10 profili ayarlarını Yakala
2. Atamasını ve/veya var olan profilleri Sil
3. Yakalanan ayarları kullanarak yeni profilleri oluşturmak ve yeni profiller aynı gruplara

Son kullanıcılarınıza bildirmeniz ve bu değişikliği, Yardım Masası izin gerekebilir. Lütfen hata ayrıntılarını ve bu profilleri yeniden oluşturma yönergeleri için ek bilgilere destek blog gönderisine bakın.

#### <a name="additional-information"></a>Ek bilgi
https://aka.ms/Win10EmailProfiles

