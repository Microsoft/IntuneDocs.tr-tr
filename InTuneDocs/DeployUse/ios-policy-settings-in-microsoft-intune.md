---
title: "iOS ilke ayarları | Microsoft Intune"
description: "Intune ile yönettiğiniz iOS cihazlarında ayarları ve özellikleri denetleyen ilkeler oluşturun."
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ab46be6c-ab73-4c99-8492-66d1dd418293
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f9a492a16605130743b943f6aa49d1d633eb97d4
ms.openlocfilehash: 3292df922eeb53108f2b34d4113b0b6c5a114564


---

# Microsoft Intune’da iOS ilke ayarları

Intune, iOS cihazlarda yapılandırabileceğiniz çeşitli yerleşik genel ayarlar sağlar. Ayrıca, Intune'dan kullanılamayan özel ayarları oluşturmak için Apple Configurator aracını kullanabilirsiniz.

## Genel yapılandırma ilkesi ayarları

Microsoft Intune **iOS genel yapılandırma ilkesini** kullanarak aşağıdaki ayarları yapılandırabilirsiniz:

-   **Genel cihaz ve güvenlik ayarları** – Cihazda bir dizi özelliği ve işlevi denetlemenize olanak tanıyan önceden tanımlı ayarlar listesinden seçim yapın.

-   **Bilgi noktası modu** -Bir cihazı yalnızca belirli özellikleri çalışacak şekilde kilitler. Örneğin, bir cihazın yalnızca belirttiğiniz bir yönetilen uygulamayı çalıştırmasına izin verebilir veya bir cihazdaki ses düğmelerini devre dışı bırakabilirsiniz. Bu ayarlar, bir cihazın tanıtım modeli için veya satış noktası cihazı gibi yalnızca bir işlevi gerçekleştirmeye ayrılan bir cihaz için kullanılabilir.

-   **Uyumlu ve uyumsuz uygulamalar** - Şirketinizdeki uyumlu veya uyumsuz uygulamaların listesini gösterir. Android ve iOS cihazlarında, **Uyumlu Olmayan Uygulamalar Raporu** ile listede belirttiğiniz uygulamalarla kullanıcıların yüklemiş olduğu uygulamalar karşılaştırılarak uyumlu olup olmadığı görüntülenebilir (ancak uygulamanın yüklenmesi engellenemez).

> [!TIP]
> Kullanıcılarınızın kişisel uygulamalar dahil olmak üzere cihazlarındaki uygulamaların değerlendirileceğini ve uyumsuz uygulamaların engelleneceğini ya da uyumsuz olarak bildirileceğini anladığından emin olmak kullanıcılara yönelik hüküm ve koşullar yapılandırabilirsiniz. Kullanıcılar, uygulamalara erişmek üzere cihazlarını kaydedip şirket portalını kullanmadan önce bu hüküm ve koşulları kabul etmelidir. Hüküm ve koşulları kullanma hakkında daha fazla bilgi için bkz. [Microsoft Intune’da hüküm ve koşullar ilkesi ayarları](terms-and-condition-policy-settings-in-microsoft-intune.md).

Aradığınız özellik bu konu başlığı altında görünmüyorsa, [Apple Yapılandırıcı Aracı](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12)'nı kullanarak oluşturduğunuz ayarları içeri aktarmanızı sağlayan bir iOS özel ilkesi kullanarak bu özelliği oluşturabilirsiniz. Daha fazla bilgi için, bu konunun devamındaki **Özel ilke ayarları** bölümüne bakın.

### Güvenlik ayarları

|Ayar adı|Ayrıntılar|iOS|
|----------------|-------|
|**Mobil cihazların kilidini açmak için bir parola gerektir**|Kullanıcıların cihazlarına erişmek için parola girmelerinin gerekip gerekmediğini belirtin.|Evet|
|**Gerekli parola türü**|Gerekli parola türünü belirtir (yalnızca sayısal veya alfasayısal gibi).|Evet|
|**Gerekli parola türü – Minimum karakter kümesi sayısı**|Parolaya içermesi gereken sembol karakterlerinin sayısını belirtir (**#** veya **@** gibi).|Evet|
|**Minimum parola uzunluğu**|Parolada bulunacak minimum karakter sayısını belirtir.|Evet|
|**Basit parolalara izin ver**|‘0000’ ve ‘1234’ gibi basit parolalara izin verin.|Evet|
|**Cihaz temizlenmeden önce izin verilen yinelenen oturum açma hatası sayısı**|Bu sayıda oturum açma denemesi başarısız olursa cihazı temizler.|Evet|
|**Ekran kapanmadan önce geçen işlem yapılmayan dakika sayısı**<sup>1</sup>|Cihazın ekranı kapatılmadan önce beklenecek dakika sayısını belirtin.|Evet|
|**Parola geçerlilik süresi (gün)**|Cihaz parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını belirtir.|Evet|
|**Parola geçmişini anımsa**|Kullanıcının önceden kullanmış olduğu parolaları kullanıp kullanamayacağını belirtir.|Evet|
|**Parola geçmişini anımsa** – **Önceki parolaların yeniden kullanılmasını önle**|Önceden kullanılmış ve cihaz tarafından anımsanacak olan parola sayısını belirtir.|Evet|
|**Parola istenmeden önce geçen işlem yapılmayan dakika sayısı**<sup>1</sup>|Kullanıcının parolasını yeniden girmesi gerekmeden önce cihazın ne kadar süreyle boşta kalabileceğini belirtir.|Evet|
|**Parmak izi ile kilit açmaya izin ver**|Parmak izi kullanarak cihaz kilidini açmaya izin verin.|iOS 7.1 ve üzeri|
<sup>1</sup> iOS cihazlarında **Ekran kapanmadan önce geçen işlem yapılmayan dakika sayısı** ve **Parola istenmeden önce geçen işlem yapılmayan dakika sayısı** ayarlarını sırayla uygulayarak yapılandırın. Örneğin, her iki ayarın da değerini **5** dakikaya ayarlarsanız, ekran 5 dakika sonra otomatik olarak kapanır ve cihazın kilitlenmesi için 5 dakika daha geçmesi gerekir. Ancak, kullanıcı ekranı el ile kapatırsa ikinci ayar hemen uygulanır. Aynı örnekte, kullanıcı ekranı kapattıktan sonraki 5 dakikanın sonunda cihaz kilitlenir.

### Sistem ayarları

|Ayar adı|Ayrıntılar|iOS|
|----------------|-------|
|**Ekran görüntüsüne izin ver**|Kullanıcının ekran içeriğini bir resim olarak yakalamasına izin verir.|Evet|
|**Kilit ekranında denetim merkezine izin ver**|Cihaz kilitli olduğunda denetim merkezi uygulamalarına erişilip erişilemeyeceğini denetler.|iOS 7.1 ve üzeri|
|**Kilit ekranında bildirim görünümüne izin ver**|Kullanıcının, cihazın kilidini açmadan bildirimler görünümüne erişime izin verin.|iOS 7.1 ve üzeri|
|**Kilit ekranında bugün görünümüne izin ver**|Cihaz kilitli olduğunda bildirimlerin görüntülenip görüntülenemeyeceğini denetler.|iOS 7.1 ve üzeri|
|**Tanılama verilerinin gönderimine izin ver**|Cihazın Apple’a tanılama verileri göndermesine izin verin veya bunu engelleyin.|Evet|
|**Güvenilmeyen TLS sertifikalarına izin ver**|Cihazda güvenilmeyen Aktarım Katmanı Güvenliği sertifikalarına izin verin.|Evet|
|**Kilitliyken passbook kullanımına izin ver**|Cihaz kilitliyken kullanıcının Passbook uygulamasına erişmesine izin verin.|Evet|

### Bulut ayarları – belgeler ve veriler

|Ayar adı|Ayrıntılar|iOS|
|----------------|-------|
|**iCloud'a yedeklemeye izin ver**|Kullanıcının cihazı iCloud’a yedeklemesine izin verir.|Evet|
|**iCloud'a belge eşitlemeye izin ver**|iCloud depolama alanınızda belge ve anahtar-değer eşitlemesine izin verin.|Evet|
|**iCloud'a Fotoğraf Akışını eşitlemeye izin ver**|Cihazdaki fotoğrafların iCloud’a eşitlenmesine izin verin.|Evet|
|**Şifreli yedekleme iste**|Tüm cihaz yedeklemelerinin şifrelenmesini zorunlu tutar.|Evet|

### Uygulama ayarları - tarayıcı

|Ayar adı|Ayrıntılar|iOS|
|----------------|-------|
|**Safari'ye izin ver**|Cihazda Safari tarayıcısının kullanılıp kullanılamayacağını belirtin.|Evet|
|**Otomatik doldurmaya izin ver**|Kullanıcı tarayıcıdaki otomatik tamamlama ayarlarını değiştirebilir.|Evet|
|**Açılır pencere engelleyicisine izin ver**|Tarayıcı açılır pencere engelleyicisini etkinleştirin veya devre dışı bırakın.|Evet|
|**Tanımlama bilgilerine izin ver**|Cihazın web tarayıcısının tanımlama bilgilerini kullanmasına izin verin.|Evet|
|**Java betiği oluşturmaya izin ver**|Tarayıcıda Java betiğinin çalıştırılmasına izin verin.|Evet|
|**Sahtekarlık uyarısına izin ver**|Cihazın tarayıcısında sahtekarlık uyarılarına izin verin.|Evet|

### Uygulama ayarları - uygulamalar

|Ayar adı|Ayrıntılar|iOS|
|----------------|-------|
|**Uygulama depolamaya izin ver**|Cihazın uygulama mağazasına erişmesine izin verir.|Evet|
|**Uygulama deposuna erişim için parola iste**|Kullanıcının, uygulama mağazası ziyaret edebilmesi için önce bir parola girmesini gerektirir.|Evet|
|**Uygulama içi satın almalara izin ver**|Çalışan bir uygulamanın içinden mağazada alışveriş yapılmasına izin verir.|Evet|
|**Diğer yönetilmeyen uygulamalardaki yönetilen belgelere izin ver**|Şirket belgelerinin herhangi bir uygulamada görüntülenmesine izin verir.<br>**Örnek:** Kullanıcıların OneDrive uygulamasından Dropbox’a dosya kaydetmesini engellemek istiyorsunuz. Bu ayarı hayır olarak yapılandırın. Cihaz ilkeyi aldıktan (örneğin, yeniden başlatıldıktan) sonra artık kaydetmeye izin vermez.|iOS 7.1 ve üzeri|
|**Diğer yönetilen uygulamalardaki yönetilmeyen belgelere izin ver**|Tüm belgelerin şirketin yönetilen uygulamalarında görüntülenmesine izin verin.|iOS 7.1 ve üzeri|
|**Görüntülü konferansa izin ver**|Cihazda Facetime gibi görüntülü konferans uygulamalarına izin verir.|Evet|
|**Medya mağazasında yetişkinlere yönelik içeriğe izin ver**|Cihazın mağazadaki yetişkinlere yönelik olarak derecelendirilmiş içeriğe erişmesine izin verin.|Evet|

### Uygulama ayarları - Oyunlar

|Ayar adı|Ayrıntılar|iOS|
|----------------|-------|
|**Game Center arkadaşlarını eklemeye izin ver**|Kullanıcının Game Center'da arkadaş eklemesine izin verin.|Evet|
|**Çok oyunculu oyunlara izin ver**|Kullanıcının cihazda çok oyunculu oyunlar oynamasına izin verin.|Evet|

### Cihaz özellikleri ayarları - donanım

|Ayar adı|Ayrıntılar|iOS|
|----------------|-------|
|**Kameraya izin ver**|Cihazdaki kameranın kullanılıp kullanılamayacağını belirtir.|Evet|

### Cihaz özellikleri ayarları - cep telefonu

|Ayar adı|Ayrıntılar|iOS|
|----------------|-------|
|**Sesli dolaşıma izin ver**|Cihaz cep telefonu şebekesindeyken sesli dolaşıma izin verin.|Evet|
|**Veri dolaşımına izin ver**|Cihaz cep telefonu şebekesindeyken veri dolaşımına izin verin.|Evet|
|**Dolaşımdayken genel arka plan almaya izin ver**|Cihazın, cep telefonu şebekesinde dolaşımdayken e-posta gibi verileri almasına izin verir.|Evet|

### Cihaz özellikleri ayarları - özellikler

|Ayar adı|Ayrıntılar|iOS|
|----------------|-------|
|**Siri'ye izin ver**|Cihazda Siri ses yardımcısının kullanımına izin verin.|Evet|
|**Cihaz kilitliyken Siri'ye izin ver**|Cihaz kilitliyken cihazda Siri ses yardımcısının kullanımına izin verin.|Evet|
|**Sesli aramaya izin ver**|Cihazda sesli arama özelliğinin kullanımına izin verin.|Evet|


### Uyumlu ve uyumlu olmayan uygulamalar için ayarlar
**Uyumlu &amp; Uyumsuz Uygulamalar** listesinde, aşağıdaki bilgileri kullanarak uyumlu veya uyumsuz uygulamalar listesini belirtin:

> [!NOTE]
> Tek bir ilke, yalnızca uyumlu uygulamaların veya uyumsuz uygulamaların listesini içerebilir. İkisi de aynı ilkede belirtemezsiniz.

|Ayar adı|Ayrıntılar|
|----------------|--------------------|
|**Kullanıcılar listelenen uygulamaları yüklediğinde uyumsuzluk bildir**|Kullanıcıların yüklemesine ve çalıştırmasına için izin verilmeyen, Intune tarafından yönetilmeyen uygulamaları listeler.|
|**Kullanıcılar listelenen uygulamaları yüklediğinde uyumsuzluk bildirme**|Kullanıcıların yüklemesine izin verilen uygulamaları listeler. Uyumluluğun korunması için kullanıcılar listelenmeyen uygulamaları yüklememelidir. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir.|
|**Ekle**|Seçili listeye bir uygulama ekler. Tercih ettiğiniz bir ad (isteğe bağlı olarak uygulama yayımcısı) ve uygulamanın uygulama mağazasındaki URL'sini belirtin. Daha fazla yardım için, bu konunun devamındaki **Uygulama mağazalarının URL’lerini belirtme** bölümünü okuyun.|
|**Uygulamaları İçeri Aktar**|Virgülle ayrılmış bir değerler dosyasında belirttiğiniz uygulamaların listesini içeri aktarır. Dosyadaki biçim, uygulama adı, yayımcı, uygulama URL'sini kullanın.|
|**Düzenle**|Seçilen uygulamanın adını, yayımcısını ve URL'sini düzenlemenize imkan tanır.|
|**Sil**|Seçilen uygulamayı listeden siler.|

### Bilgi noktası modu ayarları

|Ayar adı|Ayrıntılar|
|----------------|--------------------|
|**Cihaz bilgi noktası modundayken çalışmasına izin verilecek yönetilen bir uygulama seçin**|**Gözat**’ı seçtikten sonra yönetilen uygulamayı veya cihaz bilgi noktası modundayken çalışmasına izin verilecek mağaza uygulamasını belirtin. Cihazda başka hiçbir uygulamanın çalıştırılmasına izin verilmez. Daha fazla yardım için bu konunun devamındaki **Uygulama mağazalarının URL’lerini belirtme** bölümüne bakın.|
|**Dokunmatik ekrana izin ver**|Cihazda dokunmatik ekranı etkinleştirir veya devre dışı bırakır.|
|**Ekran döndürmeye izin ver**|Cihazı döndürdüğünüzde ekran yönünü değiştirmeyi etkinleştirir veya devre dışı bırakır.|
|**Ses düğmelerine izin ver**|Cihazdaki ses düğmelerinin kullanımını etkinleştirir veya devre dışı bırakır.|
|**Ses açma/kapama düğmesine izin ver**|Cihazda ses açma/kapama (sessiz) düğmesini etkinleştirir veya devre dışı bırakır.|
|**Açma/kapatma düğmesine izin ver**|Cihazın açma/kapatma düğmesini etkinleştirir veya devre dışı bırakır.|
|**Otomatik kilide izin ver**|Cihazın otomatik olarak kilitlenmesini etkinleştirir veya devre dışı bırakır.|
|**Mono sesi etkinleştir**| **Mono Ses**erişilebilirlik ayarını etkinleştirir veya devre dışı bırakır.|
|**Seslendirmeyi etkinleştir**|Cihazın ekranındaki metinleri sesli olarak okuyan **VoiceOver** erişilebilirlik ayarını etkinleştirir veya devre dışı bırakır.|
|**Seslendirme ayarlarını etkinleştir**|VoiceOver işlevini ayarlamanıza izin veren seslendirme ayarlarını (örneğin, ekran üzerindeki metnin ne kadar hızlı okunacağı) etkinleştirir veya devre dışı bırakır.|
|**Yakınlaştırmayı etkinleştir**|Cihazın ekranını dokunarak yakınlaştırmanıza olanak sağlayan **Yakınlaştırma** erişilebilirlik ayarını etkinleştirir veya devre dışı bırakır.|
|**Yakınlaştırma ayarlarını etkinleştir**|Yakınlaştırma işlevini ayarlamanıza olanak veren yakınlaştırma ayarlarını etkinleştirir veya devre dışı bırakır.|
|**Renkleri ters çevirmeyi etkinleştir**|Görme engelli kullanıcılara yardımcı olmak için ekranı ayarlayan **Renkleri ters çevir** erişilebilirlik ayarını etkinleştirir veya devre dışı bırakır.|
|**Renkleri ters çevir ayarlarını etkinleştir**|Renkleri ters çevirme işlevini ayarlamanıza olanak veren renkleri ters çevirme ayarlarını etkinleştirir veya devre dışı bırakır.|
|**Yardımcı dokunmayı etkinleştir**|Ekran hareketlerini gerçekleştirmekte zorlanabilecek kullanıcıların bunları yapmasına yardımcı olan **Yardımcı Dokunma** erişilebilirlik ayarını etkinleştirir veya devre dışı bırakır.|
|**Yardımcı dokunma ayarlarını etkinleştir**|Yardımcı dokunma işlevini ayarlamanıza olanak veren yardımcı dokunma ayarlarını etkinleştirir veya devre dışı bırakır.|
|**Seçimi seslendirmeyi etkinleştir**|Seçtiğiniz metni sesli okuyabilen **Seçimi Seslendir** erişilebilirlik ayarını etkinleştirir veya devre dışı bırakır.|
> [!NOTE]
> aşağıdaki notlar, iOS cihazlarda bilgi noktası modu ayarları için geçerlidir:
> 
> -   Bir iOS cihazını bilgi noktası modu için yapılandırmadan önce, [Apple Configurator Tool](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) 'u veya cihaz kayıt yöneticisini kullanarak cihazı denetimli moduna almanız gerekir. Apple Configurator Tool hakkında daha fazla bilgi için Apple belgelerinize bakın.
> -   Belirttiğiniz iOS uygulaması yapılandırma ilkesini dağıttıktan sonra yüklendiyse, cihaz yeniden başlatılana kadar bilgi noktası moduna girmez.

### Uyumlu ve uyumlu olmayan uygulamalar için başvuru bilgileri

#### Uyumlu ve uyumsuz uygulamaları izle
 **Uyumlu Olmayan Uygulamalar Raporu** 'nu kullanarak izin verilen ve engellenen uygulamaların uyumluluğunu görüntüleyin.

##### Uyumlu Olmayan Uygulamalar Raporu'nu çalıştırmak için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com), **Raporlar** &gt; **Uyumsuz Uygulamalar Raporu**’nu seçin.

2.  Denetlemek istediğiniz cihaz gruplarını seçin, uyumlu uygulamaları, uyumsuz uygulamaları veya her ikisini birden denetlemek istediğinizi belirtin ve sonra **Raporu Görüntüle**’yi seçin.

#### Uygulama mağazalarının URL'lerini belirtme
Uyumlu ve uyumsuz uygulamalar listesinde veya **Cihaz bilgi noktası modundayken çalışmasına izin verilecek bir yönetilen uygulama seçin** seçeneğinde (yalnızca iOS) bir uygulamanın URL'sini belirtmek için aşağıdaki biçimi kullanın:

Bir arama motorunu kullanarak iTunes App Store'dan kullanmak istediğiniz uygulamayı bulun ve uygulamanın sayfasını açın.

Sayfanın URL'sini kopyalayın ve bunu uyumlu veya uyumsuz uygulamalar listesini ya da bilgi noktası modunda çalıştırmak istediğiniz uygulamayı yapılandırmak için gereken URL olarak kullanın.

**Örnek:**  **iPad için Microsoft Word**ifadesini aratın. Kullandığınız URL **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8** olacaktır.

> [!NOTE]
> iTunes yazılımını kullanarak da uygulamayı bulabilir ve ardından **Bağlantıyı Kopyala** komutuyla uygulama URL'sini alabilirsiniz.


## Özel ilke ayarları

[Apple Configurator aracını](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) kullanarak oluşturduğunuz ayarları iOS cihazlarına dağıtmak için Microsoft Intune **iOS özel ilkesini** kullanın. Bu araç, bu cihazların işlemini denetleyen ve bunları bir yapılandırma profiline dışarı aktaran birçok ayar oluşturmanızı sağlar. Daha sonra bu yapılandırma profilini bir Intune iOS özel ilkesine içeri aktarabilir ve ayarları kuruluşunuzdaki kullanıcılara ve cihazlara dağıtabilirsiniz.

Bu özellik, Intune genel yapılandırma ilkeleriyle, yapılandırılabilir olmayan iOS ayarlarını dağıtmanıza olanak sağlamak için tasarlanmıştır.

### Önkoşullar
Başlamadan önce, Apple Configurator’ı yüklemiş ve kullanıcılara veya cihazlara dağıtmak istediğiniz ayarları içeren bir yapılandırma dosyası oluşturmuş olmanız gerekir.  [Mac App Store](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12)‘dan Apple Configurator’ı indirebilir ve Apple Configurator hakkında bilgi edinebilirsiniz

> [!NOTE]
> Intune, bir iOS özel ilkesindeki tek tek ayarların uyumluluğunu raporlamaz. Ancak, ilkenin genel uyumluluğu raporlanır.

### Genel ayarlar

|Ayar adı|Ayrıntılar|
    |----------------|--------------------|
    |**Ad**|Intune konsolunda tanımlamanıza yardımcı olması için iOS özel ilkesine benzersiz bir ad girin.|
    |**Açıklama**|iOS özel ilkesine genel bakış ve onu bulmanıza yardımcı olacak diğer ilgili bilgileri sunan bir açıklama sağlayın.|

### Özel ayarlar

|Ayar adı|Ayrıntılar|
    |----------------|--------------------|
|**Özel yapılandırma profili adı (kullanıcılara gösterilir)**|Cihazda ve Intune ilke raporlarında görüntülenecek şekilde ilke için bir ad sağlayın.|
|**Yapılandırma profili dosyası**|**İçeri aktar**’ı seçin, sonra Apple Configurator’ı kullanarak oluşturduğunuz yapılandırma profiline gidin. **Not:** Apple Configurator aracından dışarı aktardığınız ayarların, iOS özel ilkesini dağıttığınız cihazlardaki iOS sürümüyle uyumlu olduğundan emin olun. Uyumsuz ayarların nasıl çözümleneceği hakkında bilgi için, [Apple Developer](https://developer.apple.com/) web sitesinde **Yapılandırma Profili Başvurusu** ve **Mobil Cihaz Yönetim Protokolü Başvurusu** öğesini arayın.|
    |**Yapılandırma profili ayrıntıları**|İçeri aktardığınız yapılandırma profili için xml kodunu görüntüler.|

### Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Jun16_HO4-->


