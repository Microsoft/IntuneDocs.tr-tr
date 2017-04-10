---
title: "iOS ilke ayarları | Microsoft Docs"
description: "Intune ile yönettiğiniz iOS cihazlarında ayarları ve özellikleri denetleyen ilkeler oluşturun."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ab46be6c-ab73-4c99-8492-66d1dd418293
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e7d1760a10e63233fe7cc7f6fd57a68c5283647c
ms.openlocfilehash: 05d47e6cf5c7b380ac981d06a3938f38b27a430b


---

# <a name="ios-policy-settings-in-microsoft-intune"></a>Microsoft Intune’da iOS ilke ayarları

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune, iOS cihazlarda yapılandırabileceğiniz bir dizi yerleşik genel ayar sunar. Ayrıca, Intune'dan kullanılamayan özel ayarları oluşturmak için Apple Configurator aracını kullanabilirsiniz.

## <a name="general-configuration-policy-settings"></a>Genel yapılandırma ilkesi ayarları

Microsoft Intune **iOS genel yapılandırma ilkesini** kullanarak aşağıdaki ayarları yapılandırabilirsiniz:

-   **Genel cihaz ve güvenlik ayarları**. Cihazda bir dizi özelliği ve işlevi denetlemenize olanak sağlayan, önceden tanımlı ayarlar listesinden seçim yapın.

-   **Bilgi noktası modu**. Bir cihazı, yalnızca belirli özellikleri çalışacak şekilde kilitler. Örneğin, cihazın yalnızca belirttiğiniz bir yönetilen uygulamayı çalıştırmasına izin verebilir veya cihazdaki ses düğmelerini devre dışı bırakabilirsiniz. Bu ayarlar, bir cihazın tanıtım modeli için veya yalnızca tek bir işlevi (satış noktası cihazı gibi) gerçekleştirmeye ayrılmış bir cihaz için kullanılabilir.

-   **Uyumlu ve uyumsuz uygulamalar**. Şirketinizdeki uyumlu veya uyumsuz uygulamaların listesini belirtin. Android ve iOS cihazlarında **Uyumlu Olmayan Uygulamalar Raporu**’nu kullanarak, listede belirttiğiniz uygulamaları kullanıcıların yüklemiş olduğu uygulamalarla karşılaştırılabilir ve uyumlu olup olmadıklarını görüntüleyebilirsiniz (ancak uygulamanın yüklenmesi engellenemez).

> [!TIP]
> Kullanıcılarınızın, cihazlarındaki uygulamaların (kişisel uygulamalar dahil) değerlendirileceğini ve uyumsuz uygulamaların engelleneceğini ya da uyumsuz olarak bildirileceğini anladığından emin olmak amacıyla, kullanıcılara yönelik hüküm ve koşullar yapılandırabilirsiniz. Kullanıcılar, uygulamalara erişmek üzere cihazlarını kaydedip şirket portalını kullanmadan önce bu hüküm ve koşulları kabul etmelidir. Hüküm ve koşulları kullanma hakkında daha fazla bilgi için bkz. [Microsoft Intune’da hüküm ve koşullar ilkesi ayarları](terms-and-condition-policy-settings-in-microsoft-intune.md).

Aradığınız özellik bu konu başlığı altında görünmüyorsa, [Apple Configurator aracı](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) ile oluşturduğunuz ayarları içeri aktarmanızı sağlayan bir iOS özel ilkesi kullanarak bu özelliği oluşturabilirsiniz. Daha fazla bilgi için, bu konunun devamındaki “Özel ilke ayarları” bölümüne bakın.

### <a name="security-settings"></a>Güvenlik ayarları
Tüm ayarlar iOS 8.0 ve üzeri için geçerlidir.

|Ayar adı|Ayrıntılar|
|----------------|-------|
|**Mobil cihazların kilidini açmak için bir parola iste**|Kullanıcının cihazına erişmek için parola girmesinin gerekip gerekmediğini belirtin.|
|**Gerekli parola türü**|Gerekli parola türünü belirtin (yalnızca sayısal veya alfasayısal gibi).|
|**Parolada gerekli karmaşık karakter sayısı**|Parolada bulunması gereken simge karakterlerinin sayısını belirtin (**#** veya **@** gibi).|
|**En düşük parola uzunluğu**|Parolada bulunacak karakter sayısı için alt sınır belirtin.|
|**Basit parolalara izin ver**|**0000** ve **1234** gibi basit parolalara izin verin.|
|**Cihaz silinmeden önce izin verilen yinelenen oturum açma hatası sayısı**|Bu ayar cihazı temizlemeden önce gerçekleşebilecek başarısız oturum açma girişimlerinin sayısını belirtin.|
|**Parola istenmeden önce geçen işlem yapılmayan dakika sayısı**<sup>1</sup>|Kullanıcının parolasını yeniden girmesi gerekmeden önce cihazın ne kadar süreyle boşta kalabileceğini belirtin.|
|**Parola kullanım süresi (gün)**|Cihaz parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını belirtin.|
|**Parola geçmişini anımsa**|Kullanıcının önceden kullanmış olduğu parolaları kullanıp kullanamayacağını belirtin.|
|**Parola geçmişini anımsa** – **Önceki parolaların tekrar kullanılmasını engeller**|Önceden kullanılmış ve cihaz tarafından anımsanacak olan parola sayısını belirtin.|
|**Ekran kapanmadan önce herhangi bir işlem yapılmadan geçen dakika sayısı**<sup>1</sup>|Cihazın ekranı kapatılmadan önce beklenecek dakika sayısını belirtin.|
|**Parmak izi ile kilit açmaya izin ver**|Parmak izi kullanarak cihaz kilidini açmaya izin verin.|
<sup>1</sup> iOS cihazlarda **Ekran kapanmadan önce herhangi bir işlem yapılmadan geçen dakika sayısı** ve **Parola istenmeden önce herhangi bir işlem yapılmadan geçen dakika sayısı** ayarlarını sırayla uygulayarak yapılandırın. Örneğin, her iki ayarın da değerini **5** dakikaya ayarlarsanız, ekran 5 dakika sonra otomatik olarak kapanır ve cihazın kilitlenmesi için 5 dakika daha geçmesi gerekir. Ancak, kullanıcı ekranı el ile kapatırsa ikinci ayar hemen uygulanır. Aynı örnekte, kullanıcı ekranı kapattıktan sonraki 5 dakikanın sonunda cihaz kilitlenir.

### <a name="system-settings"></a>Sistem ayarları
Tüm ayarlar iOS 8.0 ve üzeri için geçerlidir.

|Ayar adı|Ayrıntılar|
|----------------|-------|
|**Ekran görüntüsüne izin ver**|Kullanıcının ekran içeriğini resim olarak yakalamasına izin verin.|
|**Kilit ekranında denetim merkezine izin ver**|Cihaz kilitliyken kullanıcının denetim merkezi uygulamasına erişmesine izin verin.|
|**Kilit ekranında bildirim görünümüne izin ver**|Kullanıcının, cihazın kilidini açmadan bildirimler görünümüne erişime izin verin.|
|**Kilit ekranında bugün görünümüne izin ver**|Cihaz kilitliyken kullanıcının bildirimleri görüntülemesine izin verin.|
|**Güvenilmeyen TLS sertifikalarına izin ver**|Cihazda güvenilmeyen Aktarım Katmanı Güvenliği sertifikalarına izin verin.|
|**Tanılama verilerinin gönderimine izin ver**|Cihazın Apple’a tanılama verileri göndermesine izin verin veya bunu engelleyin.|
|**Kilitliyken passbook kullanımına izin ver**|Cihaz kilitliyken kullanıcının Passbook uygulamasına erişmesine izin verin.|

### <a name="cloud-settings-for-documents-and-data"></a>Belgeler ve veriler için bulut ayarları
Tüm ayarlar iOS 8.0 ve üzeri için geçerlidir.

|Ayar adı|Ayrıntılar|
|----------------|-------|
|**iCloud'a yedeklemeye izin ver**|Kullanıcının cihazı iCloud’a yedeklemesine izin verin.|
|**iCloud'a belge eşitlemeye izin ver**|iCloud depolama alanınızda belge ve anahtar-değer eşitlemesine izin verin.|
|**iCloud'a Fotoğraf Yayını’nı eşitlemeye izin ver**|Kullanıcıların fotoğrafların iCloud’a eşitlenmesine ve tüm kullanıcıların cihazlarında kullanılabilir olmasına imkan sağlayan **Fotoğraf Akışım**’ı cihazlarında etkinleştirmesine olanak tanır.|
|**Şifreli yedekleme iste**|Tüm cihaz yedeklemelerinin şifrelenmesini zorunlu tutar.|
|**Yönetilen uygulamaların iCloud ile veri eşitlemesine izin verme**|Intune ile yönettiğiniz uygulamaların, kullanıcının iCloud hesabıyla veri eşitlemesine izin verin.|
|**İletim’in başka bir cihazda etkinliklerini sürdürmesine izin verme**|Kullanıcının bir iOS cihazında başladığı çalışmayı başka bir iOS veya Mac OS X cihazında sürdürmesine izin verin.|
|**iCloud Fotoğraf Paylaşma’ya izin ver**|Cihazda **iCloud Fotoğraf Paylaşımı**’nı devre dışı bırakmak için **Hayır** seçeneğini belirleyin.|
|**iCloud Fotoğraf Kitaplığı’na izin ver**|**Hayır** seçeneği ayarlanırsa kullanıcıların fotoğraflar ve videoları bulutta depolamasını sağlayan iCloud fotoğraf kitaplığının kullanımı devre dışı bırakılır.    Bu ayar **Hayır** olarak belirlenirse iCloud Fotoğraf Arşivi'nden cihaza tamamen indirilmeyen tüm fotoğraflar cihazdan kaldırılır.|

### <a name="application-settings-for-the-browser"></a>Tarayıcı için uygulama ayarları
Tüm ayarlar iOS 8.0 ve üzeri için geçerlidir.

|Ayar adı|Ayrıntılar|
|----------------|-------|
|**Safari'ye izin ver**|Cihazda Safari tarayıcısının kullanılıp kullanılamayacağını belirtin.|
|**Otomatik doldurmaya izin ver**|Kullanıcının tarayıcıdaki otomatik tamamlama ayarlarını değiştirmesine izin verin.|
|**Açılır pencere engelleyicisine izin ver**|Tarayıcı açılır pencere engelleyicisini etkinleştirin veya devre dışı bırakın.|
|**Tanımlama bilgilerine izin ver**|Tarayıcının tanımlama bilgilerini kullanmasına izin verin.|
|**Java betiği oluşturmaya izin ver**|Tarayıcıda Java betiğinin çalıştırılmasına izin verin.|
|**Sahtekarlık uyarısına izin ver**|Tarayıcıda sahtekarlık uyarılarına izin verin.|

### <a name="application-settings-for-apps"></a>Uygulamalara yönelik uygulama ayarları
Tüm ayarlar iOS 8.0 ve üzeri için geçerlidir.

|Ayar adı|Ayrıntılar|
|----------------|-------|
|**Uygulama yüklemeye izin ver**|Cihazın uygulama mağazasına erişmesine ve uygulama yüklemesine izin verin.|
|**Uygulama mağazasına erişim için parola iste**|Kullanıcının uygulama mağazasını ziyaret etmeden önce parola girmesini isteyin.|
|**Uygulama içi satın almalara izin ver**|Çalışan bir uygulamanın içinden mağazada alışveriş yapılmasına izin verir.|
|**Diğer yönetilmeyen uygulamalardaki yönetilen belgelere izin ver**|Kurumsal belgelerin tüm uygulamalarda görüntülenmesine izin verin.<br>**Örnek:** Kullanıcıların OneDrive uygulamasından Dropbox’a dosya kaydetmesini engellemek istiyorsunuz. Bu ayarı hayır olarak yapılandırın. Cihaz, ilkeyi aldıktan sonra (örneğin, yeniden başlatıldıktan sonra) artık kaydetmeye izin vermeyecektir.|
|**Diğer yönetilen uygulamalardaki yönetilmeyen belgelere izin ver**|Tüm belgelerin şirketin yönetilen uygulamalarında görüntülenmesine izin verin.|
|**Görüntülü konferansa izin ver**|Cihazda FaceTime gibi görüntülü konferans uygulamalarına izin verin.|
|**Kullanıcının yeni kurumsal uygulama yazarlarına güvenmesine izin ver**|Kullanıcının uygulama mağazasından indirilmemiş uygulamalara güvenmeyi seçmesine izin verir.|


### <a name="application-settings-for-games"></a>Oyunlar için uygulama ayarları
Tüm ayarlar iOS 8.0 ve üzeri için geçerlidir.

|Ayar adı|Ayrıntılar|
|----------------|-------|
|**Game Center arkadaşlarını eklemeye izin ver**|Kullanıcının Game Center'da arkadaş eklemesine izin verin.|
|**Çok oyunculu oyunlara izin ver**|Kullanıcının cihazda çok oyunculu oyunlar oynamasına izin verin.|

### <a name="application-settings-for-media-content"></a>Medya içeriği için uygulama ayarları
Tüm ayarlar iOS 8.0 ve üzeri için geçerlidir.

|Ayar adı|Ayrıntılar|
|----------------|-------|
|**Derecelendirme bölgesi**|Bir bölge seçin, sonra kullanıcıların **Filmler**, **TV Programları** ve **Uygulamalar** için indirebileceği en yüksek derecelendirmeyi seçin.|
|**Medya mağazasında yetişkinlere yönelik içeriğe izin ver**|Cihazın mağazadaki yetişkinlere yönelik olarak derecelendirilmiş içeriğe erişmesine izin verin.|
|**Kullanıcının iBook mağazasından 'Erotika' olarak işaretlenmiş içerik indirmesine izin verme**|Kullanıcının “Erotik” kategorisindeki kitapları indirmesine izin verin.|


### <a name="device-capabilities-settings-for-hardware"></a>Donanım için cihaz özellikleri ayarları
Tüm ayarlar iOS 8.0 ve üzeri için geçerlidir.

|Ayar adı|Ayrıntılar|
|----------------|-------|
|**Kameraya izin ver**|Cihazdaki kameranın kullanılıp kullanılamayacağını belirtin.|
|**Eşleştirilmiş Apple Watch’ları bilek algılama kullanmaya zorla**|Etkinleştirildiğinde, Apple Watch takılmadığında bildirim görüntülemez.|
|**Giden AirPlay istekleri için bir eşleştirme parolası gerektirme**|Kullanıcının diğer Apple cihazlarına içerik akışı sağlamak üzere AirPlay’i kullanması için, eşleştirilen parola isteyin.|

### <a name="device-capabilities-settings-for-cellular"></a>Hücresel veri için cihaz özellikleri ayarları
Tüm ayarlar iOS 8.0 ve üzeri için geçerlidir.

|Ayar adı|Ayrıntılar|
|----------------|-------|
|**Ses dolaşımına izin ver**|Cihaz cep telefonu şebekesindeyken sesli dolaşıma izin verin.|
|**Veri dolaşımına izin ver**|Cihaz cep telefonu şebekesindeyken veri dolaşımına izin verin.|
|**Dolaşımdayken genel arka plan almaya izin ver**|Cihazın, cep telefonu şebekesinde dolaşımdayken e-posta gibi verileri almasına izin verir.|

### <a name="device-capabilities-settings-for-features"></a>Özellikler için cihaz özellikleri ayarları
Tüm ayarlar iOS 8.0 ve üzeri için geçerlidir.

|Ayar adı|Ayrıntılar|
|----------------|-------|
|**Siri'ye izin ver**|Cihazda Siri ses yardımcısının kullanımına izin verin.|
|**Cihaz kilitliyken Siri'ye izin ver**|Cihaz kilitliyken cihazda Siri ses yardımcısının kullanımına izin verin.|
|**Sesli aramaya izin ver**|Cihazda sesli arama özelliğinin kullanımına izin verin.|
|**Yönetilen uygulamalardan Airdrop’a izin verme**|Yönetilen uygulamaların Airdrop aracılığıyla veri göndermesini engeller.|


### <a name="settings-for-compliant-and-noncompliant-apps"></a>Uyumlu ve uyumlu olmayan uygulamalar için ayarlar
**Uyumlu ve Uyumsuz Uygulamalar** listesinde, aşağıdaki bilgileri kullanarak bir uyumlu veya uyumsuz uygulamalar listesi belirleyin.

> [!NOTE]
> Tek bir ilke, yalnızca uyumlu uygulamaların veya uyumsuz uygulamaların bir listesini içerebilir. İkisi de aynı ilkede belirtemezsiniz.

|Ayar adı|Ayrıntılar|
|----------------|--------------------|
|**Kullanıcılar listelenen uygulamaları yüklediğinde uyumsuzluk bildir**|Intune tarafından yönetilmeyen ve kullanıcıların yüklemesine ve çalıştırmasına izin verilmeyen uygulamaları listeleyin.|
|**Kullanıcılar listelenmeyen uygulamaları yüklediğinde uyumsuzluğu bildir**|Kullanıcıların yüklemesine izin verilen uygulamaları listeleyin. Uyumluluğun korunması için kullanıcılar listelenmeyen uygulamaları yüklememelidir. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir.|
|**Ekle**|Seçili listeye bir uygulama ekleyin. Tercih ettiğiniz bir ad (isteğe bağlı olarak uygulama yayımcısı) ve uygulamanın uygulama mağazasındaki URL'sini belirtin. Daha fazla yardım için, bu konunun devamındaki “Uygulama mağazalarının URL’lerini belirtme” bölümünü okuyun.|
|**Uygulamaları İçeri Aktar**|Virgülle ayrılmış değerler dosyasında belirttiğiniz uygulamaların listesini içeri aktarın. Dosyada şu biçimi kullanın: uygulama adı, yayımcı, uygulama URL’si.|
|**Düzenle**|Seçili uygulamanın adını, yayımcısını ve URL'sini düzenleyin.|
|**Sil**|Seçilen uygulamayı listeden silin.|

Uyumlu ve uyumsuz uygulama ayarlarını içeren ilkelerin kullanıcı gruplarına dağıtılması gerekir.

### <a name="kiosk-mode-settings"></a>Bilgi noktası modu ayarları

|Ayar adı|Ayrıntılar|
|----------------|--------------------|
|**Cihaz bilgi noktası modundayken çalışmasına izin verilecek yönetilen bir uygulama seçin**|**Gözat**’ı seçin ve sonra, yönetilen uygulamayı veya cihaz bilgi noktası modundayken çalışmasına izin verilecek mağaza uygulamasını belirtin. Cihazda başka hiçbir uygulamanın çalışmasına izin verilmez. Daha fazla yardım için, bu konunun devamındaki “Uygulama mağazalarının URL’lerini belirtme” bölümüne bakın.|
|**Dokunmatik ekrana izin ver**|Cihazda dokunmatik ekranı etkinleştirin veya devre dışı bırakın.|
|**Ekran döndürmeye izin ver**|Kullanıcı, cihazı döndürdüğünde ekran yönünü değiştirmeyi etkinleştirin veya devre dışı bırakın.|
|**Ses düzeyi düğmelerine izin ver**|Cihazdaki ses düğmelerinin kullanımını etkinleştirin veya devre dışı bırakın.|
|**Ses açma/kapama düğmesine izin ver**|Cihazda ses açma/kapama (sessiz) düğmesini etkinleştirin veya devre dışı bırakın.|
|**Uyku/uyandırma düğmesine izin ver**|Ekranda uykuya geçme ve uyandırma düğmesini etkinleştirin veya devre dışı bırakın.|
|**Otomatik kilide izin ver**|Cihazın otomatik olarak kilitlenmesini etkinleştirin veya devre dışı bırakın.|
|**Mono sesi etkinleştir**|**Mono ses**erişilebilirlik ayarını etkinleştirin veya devre dışı bırakın.|
|**Seslendirmeyi etkinleştir**|Cihazın ekranındaki metinleri sesli olarak okuyan **VoiceOver** erişilebilirlik ayarını etkinleştirin veya devre dışı bırakın.|
|**Seslendirme ayarlarını etkinleştir**|Kullanıcının VoiceOver işlevini ayarlamasına izin veren seslendirme ayarlarını (örneğin, ekran üzerindeki metnin ne kadar hızlı okunacağı) etkinleştirin veya devre dışı bırakın.|
|**Yakınlaştırmayı etkinleştir**|Kullanıcının cihazın ekranını dokunarak yakınlaştırmasına olanak sağlayan **Yakınlaştırma** erişilebilirlik ayarını etkinleştirin veya devre dışı bırakın.|
|**Yakınlaştırma ayarlarını etkinleştir**|Kullanıcının yakınlaştırma işlevini ayarlamasını sağlayan yakınlaştırma ayarlarını etkinleştirin veya devre dışı bırakın.|
|**Renkleri ters çevirmeyi etkinleştir**|Görme bozukluğu olan kullanıcılara yardımcı olmak için ekranı ayarlayan **Renkleri ters çevir** erişilebilirlik ayarını etkinleştirin veya devre dışı bırakın.|
|**Renkleri ters çevir ayarlarını etkinleştir**|Kullanıcının renkleri ters çevirme işlevini ayarlamasına olanak sağlayan renkleri ters çevirme ayarlarını etkinleştirin veya devre dışı bırakın.|
|**Yardımcı dokunmayı etkinleştir**|Ekran hareketlerini gerçekleştirmekte zorlanabilecek kullanıcıların bunları yapmasına yardımcı olan **Yardımcı Dokunma** erişilebilirlik ayarını etkinleştirin veya devre dışı bırakın.|
|**Yardımcı dokunma ayarlarını etkinleştir**|Kullanıcının yardımcı dokunma işlevini ayarlamasına olanak sağlayan yardımcı dokunma ayarlarını etkinleştirin veya devre dışı bırakın.|
|**Seçimi seslendirmeyi etkinleştir**|Kullanıcının seçtiği metni sesli okuyabilen **Seçimi Seslendir** erişilebilirlik ayarını etkinleştirin veya devre dışı bırakın.|
> [!NOTE]
> aşağıdaki notlar, iOS cihazlarda bilgi noktası modu ayarları için geçerlidir:
>
> -   Bir iOS cihazını bilgi noktası modu için yapılandırabilmek için önce, [Apple Configurator aracını](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) veya [Apple Cihaz Kayıt Programı](ios-device-enrollment-program-in-microsoft-intune.md)’nı kullanarak cihazı denetimli moda almanız gerekir. Apple Configurator aracı hakkında daha fazla bilgi için Apple belgelerinize bakın.
> -   Belirttiğiniz iOS uygulaması siz yapılandırma ilkesini dağıttıktan sonra yüklendiyse, cihaz, yeniden başlatılana kadar bilgi noktası moduna girmez.

### <a name="reference-information-for-compliant-and-noncompliant-apps"></a>Uyumlu ve uyumlu olmayan uygulamalar için başvuru bilgileri

**Uyumlu Olmayan Uygulamalar Raporu** 'nu kullanarak izin verilen ve engellenen uygulamaların uyumluluğunu görüntüleyin.

##### <a name="to-run-the-noncompliant-apps-report"></a>Uyumlu Olmayan Uygulamalar Raporu'nu çalıştırmak için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com), **Raporlar** &gt; **Uyumsuz Uygulamalar Raporu**’nu seçin.

2.  Denetlemek istediğiniz cihaz gruplarını seçin, sonra uyumlu uygulamaları, uyumsuz uygulamaları ya da her ikisini de denetlemek istediğinizi belirtin ve sonra **Raporu Görüntüle**’yi seçin.

#### <a name="how-to-specify-urls-to-app-stores"></a>Uygulama mağazalarının URL'lerini belirtme
Uyumlu ve uyumsuz uygulamalar listesinde veya **Cihaz bilgi noktası modundayken çalışmasına izin verilecek bir yönetilen uygulama seçin** seçeneğinde (yalnızca iOS) bir uygulamanın URL'sini belirtmek için aşağıdaki biçimi kullanın:

1. Bir arama motoru kullanarak, iTunes App Store'dan kullanmak istediğiniz uygulamayı bulun ve uygulamanın sayfasını açın.

2. Sayfanın URL'sini kopyalayın ve bunu, uyumlu veya uyumsuz uygulamalar listesini ya da bilgi noktası modunda çalıştırmak istediğiniz uygulamayı yapılandırmak için gereken URL olarak kullanın.

**Örnek:**  **iPad için Microsoft Word**ifadesini aratın. Kullandığınız URL **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8** olacaktır.

> [!NOTE]
> iTunes yazılımını kullanarak da uygulamayı bulabilir ve ardından **Bağlantıyı Kopyala** komutuyla uygulama URL'sini alabilirsiniz.

### <a name="enrollment-settings"></a>Kayıt ayarları
Tüm ayarlar iOS 8.0 ve üzeri için geçerlidir.

|Ayar adı|Ayrıntılar|
|----------------|--------------------|
|**Cihaz denetimli moddayken Etkinleştirme Kilidi’ne izin verme**|Denetimli iOS cihazlarında Etkinleştirme Kilidi’ni etkinleştirin.|

### <a name="supervised-mode-settings"></a>Denetimli mod ayarları
iOS 8.0 ve üstünü çalıştıran denetimli moddaki cihazlarda aşağıdaki ayarları yapılandırabilirsiniz.

### <a name="supervised-mode-settings-for-device-restrictions"></a>Cihaz kısıtlamaları için denetimli mod ayarları

|Ayar adı|Ayrıntılar|
|----------------|--------------------|
|**Hesapta değişikliğe izin verme**|Kullanıcının e-posta yapılandırması gibi hesap ayarlarını değiştirmesine izin verin.|
|**Uygulama hücresel veri kullanım ayarlarında değişikliğe izin verme**|Kullanıcının hangi uygulamaların hücresel veri kullanabileceğini denetlemesine izin verme.|
|**Cihazda tüm içeriği ve ayarları silme seçeneğinin kullanılmasına izin verme**|Kullanıcının, cihazda tüm içeriği ve ayarları silme seçeneğini kullanmasına izin verin.|
|**Kullanıcının cihaz ayarlarında kısıtlamaları etkinleştirmesine izin verme**|Kullanıcının cihazda cihaz kısıtlamalarını (ebeveyn denetimleri) yapılandırmasına izin verin.|
|**Bir iOS cihazının eşleşebileceği cihazları denetlemek için konak eşleştirmesine izin verme**|Yöneticinin bir iOS cihazının hangi cihazlarla eşleşebileceğini denetleyebilmesi için konak eşleştirmeye izin ver.|
|**Kullanıcının yapılandırma profilleri ve sertifikaları yüklemesine izin verme**|Kullanıcının yapılandırma profilleri ve sertifikaları yüklemesine izin verin.|
|**Cihaz adının değiştirilmesine izin verme**|Kullanıcının cihazın adını değiştirmesine izin verin.|
|**Geçiş kodunun değiştirilmesine izin verme**|Cihaz parolasının eklenmesine, değiştirilmesine veya kaldırılmasına izin verin.|
|**Apple Watch eşleştirmesine izin verme**|Cihazın bir Apple Watch ile eşleşmesine izin verin.|
|**Bildirim ayarlarının değiştirilmesine izin verme**|Kullanıcının cihazın bildirim ayarlarını değiştirmesine izin verin.|
|**Duvar kağıdının değiştirilmesine izin verme**|Kullanıcının cihazın duvar kağıdını değiştirmesine izin verin.|

### <a name="supervised-mode-settings-for-feature-restrictions"></a>Özellik kısıtlamaları için denetimli mod ayarları

|Ayar adı|Ayrıntılar|
|----------------|--------------------|
|**AirDrop’a izin verme**|Yakındaki cihazlarla içerik değişimi için AirDrop özelliğinin kullanılmasına izin verin.|
|**Siri’nin kullanıcı tarafından oluşturulan içeriği İnternet’ten sorgulamasına izin verme**|Siri’nin soruları yanıtlamak için web sitelerine erişmesine izin verin.|
|**Siri küfür filtresini kullanma**|Siri’nin küfürlü dil dikte etmesini veya konuşmasını engeller.|
|**Spotlight aramanın İnternet’ten sonuç döndürmesine izin verme**|Spotlight aramasının daha fazla sonuç sağlamak için İnternet’e bağlanmasına izin verin.|
|**Sözcük tanımı aramaya izin verme**|Bir sözcüğü vurgulayıp tanımını aramanıza izin veren iOS özelliğine izin verin.|
|**Öngörülü klavyelere izin verme**|Kullanıcının, isteyebileceği sözcükleri öneren öngörülü klavyeler kullanmasına izin verin.|
|**Otomatik düzeltmeye izin verme**|Cihazın yanlış yazılan sözcükleri otomatik düzeltmesine izin verir.|
|**Klavyenin yazım denetimi yapmasına izin verme**|Cihazın yazım denetimcisine izin verir.|
|**Klavye kısayollarına izin verme**|Klavye kısayollarının kullanılmasına izin verir.|

### <a name="supervised-mode-settings-for-app-restrictions"></a>Uygulama kısıtlamaları için denetimli mod ayarları

|Ayar adı|Ayrıntılar|
|----------------|--------------------|
|**Kurumsal uygulama güven ayarlarının değiştirilmesine izin verme**|Kullanıcıların, kurumsal uygulamaların güven ayarlarını değiştirebilmesini sağlar.|
|**Yalnızca Apple Configuration ve iTunes kullanılarak uygulama yüklenmesine izin verme**|Cihaz giriş ekranından App Store’u etkinleştirir veya devre dışı bırakır. Kullanıcılar, uygulamaları yüklemek ve güncelleştirmek için iTunes’u veya Apple Configurator aracını kullanmaya devam edebilir.|
|**Otomatik uygulama indirmeye izin verme**|Başka cihazlarda satın alınan uygulamaların otomatik olarak bu cihaza indirilmesine izin verir. Bu ayar uygulama güncelleştirmelerini etkilemez.|
|**Find My Friends uygulamasının ayarlarında değişikliğe izin verme**|Kullanıcının Find My Friends uygulamasının ayarlarını değiştirmesine izin verin.|
|**iBooks mağazası erişimine izin verme**|Kullanıcının iBooks mağazasındaki kitaplara göz atmasına ve bunları satın almasına izin verin.|
|**Cihazda Messages uygulamasının kullanılmasına izin verme**|Kısa mesaj göndermek için Messages uygulamasının kullanılmasına izin verin.|
|**Pod yayını kullanılmasına izin verme**|Pod yayını uygulamasının kullanılmasına izin verin.|
|**Music hizmetinin kullanılmasına izin verme**|Apple Music uygulamasının kullanılmasına izin verin.|
|**iTunes Radio hizmetine izin verme**|iTunes Radio uygulamasının kullanılmasına izin verin.|
|**Apple News’a izin verme**|Apple News uygulamasının kullanılmasına izin verin.|
|**Game Center’a izin verme**|Game Center uygulamasının kullanımına izin verin.|


### <a name="show-or-hide-apps"></a>Uygulamaları Gösterme veya Gizleme

iOS 9.3 veya üzerini çalıştıran denetimli cihazlarda aşağıdakileri denetlemek için **Gizli veya gösterilen uygulamalar listesi**’ni kullanın:

- Kullanıcılardan gizlenecek uygulamaların bir listesini belirtin. Kullanıcılar bu uygulamaları görüntüleyemez veya başlatamaz.
- Kullanıcıların görüntüleyebileceği ve başlatabileceği uygulamaların bir listesini belirtin. Başka hiçbir uygulama görüntülenemez veya başlatılamaz.


#### <a name="how-to-create-a-hidden-or-shown-app-list"></a>Gizli veya gösterilen uygulama listesi oluşturma

Aşağıdaki ayarları belirtin:

|Ayar adı|Ayrıntılar|
|-|-|
|**Gizli ve gösterilen uygulamalar listesi**|Gizli veya gösterilen uygulamalar listesi oluşturmak istiyorsanız bu ayarı etkinleştirin.|
|**Listelenen uygulamaları kullanıcılardan sakla**|Kullanıcılardan gizlenecek uygulamaların listesini oluşturmak istiyorsanız bu seçeneği belirtin.<br>Bu liste türünü oluşturduğunuzda, iOS **Ayarlar** ve **Telefon** (iPhone’lar için) uygulamaları dışındaki tüm uygulamalar gizlenebilir.|
|**Kullanıcılara yalnızca listelenen uygulamaları göster**|Kullanıcılara görüntülenecek uygulamaların listesini oluşturmak istiyorsanız bu seçeneği belirtin.<br>Bu liste türünü oluşturduğunuzda, iOS **Ayarlar** ve **Telefon** (iPhone’lar için) uygulamaları dışındaki tüm diğer uygulamalar gizlenir.<br>Buna ek olarak, Şirket Portalı’nı ve Intune’la dağıttığınız ve yönettiğiniz tüm uygulamaları listeye eklemeniz gerekir.|
|**Ekle**|Seçili listeye bir uygulama ekler.<br>Gizli listesi için, gizlemek istediğiniz her uygulamanın **Ad**, **Yayıncı** ve **Uygulama URL'si veya Paket Kimliği** bilgilerini belirtmelisiniz.<br>Gösterilen listesi için, Intune’la yönettiğiniz uygulamaların listesini sağlayan **Yönetilen uygulama seçin** öğesini kullanabilir ve bu uygulamalar arasından seçim yapabilirsiniz veya Mağaza uygulaması seçin öğesini kullanabilir ve ardından görüntülemek istediğiniz her uygulama için **Ad**, **Yayıncı** ve **Uygulama URL’si veya Paket Kimliği** bilgilerini belirtirsiniz.|
|**Uygulamaları İçeri Aktar**|Virgülle ayrılmış bir değerler dosyasında belirttiğiniz uygulamaların listesini içeri aktarır. Dosyadaki biçim, uygulama adı, yayımcı, uygulama URL'sini kullanın.|
|**Düzenle**|Seçilen uygulamanın adını, yayımcısını ve URL'sini düzenlemenize imkan tanır.|
|**Sil**|Seçilen uygulamayı listeden siler.|

#### <a name="app-information-for-built-in-ios-apps"></a>Yerleşik iOS uygulamaları için uygulama bilgileri

Göstermek veya gizlemek istediğiniz yerleşik iOS uygulamalarının ad, yayıncı ve paket kimliği bilgilerini belirlemek için bu listedeki bilgileri kullanın. Listedeki uygulamaların tümünü göstermek veya gizlemek istiyorsanız, aşağıdaki verileri **.csv** uzantılı bir metin dosyasına kopyalayabilir ve ardından **Uygulamaları İçeri Aktar** seçeneğini kullanarak tüm uygulamaları aynı anda içeri aktarabilirsiniz.

```
App Store,Apple,com.apple.AppStore
Calculator,Apple,com.apple.calculator
Calendar,Apple,com.apple.mobilecal
Camera,Apple,com.apple.camera
Clock,Apple,com.apple.mobiletimer
Compass,Apple,com.apple.compass
Contacts,Apple,com.apple.MobileAddressBook
FaceTime,Apple,com.apple.facetime
Find Friends,Apple,com.apple.mobileme.fmf1
Find iPhone,Apple,com.apple.mobileme.fmip1
Game Center,Apple,com.apple.gamecenter
GarageBand,Apple,com.apple.mobilegarageband
Health,Apple,com.apple.Health
iBooks,Apple,com.apple.iBooks
iTunes Store,Apple,com.apple.MobileStore
iTunes U,Apple,com.apple.itunesu
Keynote,Apple,com.apple.Keynote
Mail,Apple,com.apple.mobilemail
Maps,Apple,com.apple.Maps
Messages,Apple,com.apple.MobileSMS
Music,Apple,com.apple.Music
News,Apple,com.apple.news
Notes,Apple,com.apple.mobilenotes
Numbers,Apple,com.apple.Numbers
Pages,Apple,com.apple.Pages
Photo Booth,Apple,com.apple.Photo-Booth
Photos,Apple,com.apple.mobileslideshow
Podcasts,Apple,com.apple.podcasts
Reminders,Apple,com.apple.reminders
Safari,Apple,com.apple.mobilesafari
Settings,Apple,com.apple.Preferences
Stocks,Apple,com.apple.stocks
Tips,Apple,com.apple.tips
Videos,Apple,com.apple.videos
VoiceMemos,Apple,com.apple.VoiceMemos
Wallet,Apple,com.apple.Passbook
Watch,Apple,com.apple.Bridge
Weather,Apple,com.apple.weather


```




## <a name="custom-policy-settings"></a>Özel ilke ayarları

[Apple Configurator aracını](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) kullanarak oluşturduğunuz ayarları iOS cihazlarına dağıtmak için Microsoft Intune **iOS özel ilkesini** kullanın. Bu araç, bu cihazların işlemini denetleyen ve bunları bir yapılandırma profiline dışarı aktaran birçok ayar oluşturmanızı sağlar. Daha sonra bu yapılandırma profilini bir Intune iOS özel ilkesine içeri aktarabilir ve ayarları kuruluşunuzdaki kullanıcılara ve cihazlara dağıtabilirsiniz.

Bu özellik, Intune genel yapılandırma ilkeleriyle yapılandırılamayan iOS ayarlarını dağıtmanıza olanak sağlar.

### <a name="prerequisites"></a>Önkoşullar
Başlamadan önce, Apple Configurator’ı yüklemiş ve kullanıcılara veya cihazlara dağıtmak istediğiniz ayarları içeren bir yapılandırma dosyası oluşturmuş olmanız gerekir. [Mac App Store](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12)‘dan Apple Configurator’ı indirebilir ve Apple Configurator hakkında bilgi edinebilirsiniz.

> [!NOTE]
> Intune, bir iOS özel ilkesindeki tek tek ayarların uyumluluğunu raporlamaz. Ancak, ilkenin genel uyumluluğu raporlanır.

### <a name="general-settings"></a>Genel ayarlar

|Ayar adı|Ayrıntılar|
    |----------------|--------------------|
    |**Ad**|Intune konsolunda tanımlamanıza yardımcı olması için iOS özel ilkesine benzersiz bir ad girin.|
    |**Açıklama**|iOS özel ilkesine genel bakış ve onu bulmanıza yardımcı olacak diğer ilgili bilgileri sunan bir açıklama sağlayın.|

### <a name="custom-settings"></a>Özel ayarlar

|Ayar adı|Ayrıntılar|
    |----------------|--------------------|
|**Özel yapılandırma profili adı (kullanıcılara gösterilir)**|Cihazda ve Intune ilke raporlarında görüntülenecek şekilde ilke için bir ad sağlayın.|
|**Yapılandırma profili dosyası**|**İçeri aktar**’ı seçin ve sonra Apple Configurator’ı kullanarak oluşturduğunuz yapılandırma profiline gidin. **Not:** Apple Configurator aracından dışarı aktardığınız ayarların, iOS özel ilkesini dağıttığınız cihazlardaki iOS sürümüyle uyumlu olduğundan emin olun. Uyumsuz ayarların nasıl çözümleneceği hakkında bilgi için, [Apple Developer](https://developer.apple.com/) web sitesinde **Yapılandırma Profili Başvurusu** ve **Mobil Cihaz Yönetim Protokolü Başvurusu** öğelerini arayın.|
    |**Yapılandırma profili ayrıntıları**|İçeri aktardığınız yapılandırma profili için XML kodunu görüntüleyin.|

### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Dec16_HO5-->


