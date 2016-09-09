---

title: "Android ve Samsung KNOX ilke ayarları | Microsoft Intune"
description: "Intune ile yönettiğiniz Android cihazlarında ayarları ve özellikleri denetleyen ilkeler oluşturun."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71cc39cf-e726-40fd-8d08-78776e099a4b
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 727d28cff074124b5401f6c2931f87df3a9d2d23
ms.openlocfilehash: 1809f619173ca57868cfd2b8466e6e2bcf05f0c7


---

# Microsoft Intune’daki Android ve Samsung KNOX ilke ayarları

Intune, Android cihazlarda yapılandırabileceğiniz bir dizi yerleşik genel ayar sunar. Buna ek olarak, Intune’da bulunmayan özel ayarlar oluşturmak için Açık Mobil Ortaklığı Tekdüzen Kaynak Tanımlayıcısı (OMA-URI) değerleri belirtebilirsiniz.

## Genel yapılandırma ilkesi

Aşağıdakilerin ayarlarını yapılandırmak için Intune **Android genel yapılandırma ilkesini** kullanın:

-   **Mobil cihaz güvenliği ayarları** - Cihazda bir dizi özelliği ve işlevi denetlemenize olanak tanıyan önceden tanımlanmış ayarlar listesinden seçim yapın.

-   **Bilgi noktası modu** (yalnızca Samsung KNOX cihazlar için) - Bir cihazı, yalnızca belirli özelliklerin çalışmasına izin verecek şekilde kilitleyin. Örneğin, cihazın yalnızca belirttiğiniz bir yönetilen uygulamayı çalıştırmasına izin verebilir veya cihazdaki ses düğmelerini devre dışı bırakabilirsiniz. Bu ayarlar, bir cihazın tanıtım modeli için veya satış noktası cihazı gibi yalnızca tek bir işlevi gerçekleştirmeye ayrılmış bir cihaz için kullanılabilir.

-   **Uyumlu ve uyumsuz uygulamalar** - Şirketinizdeki uyumlu veya uyumsuz uygulamaların bir listesini belirtin. Android ve iOS cihazlarında, **Uyumsuz Uygulamalar Raporu**, listede belirttiğiniz uygulamaların kullanıcıların yüklemiş olduğu uygulamalara karşılık uyumluluğunu görmek için kullanılabilir. Rapor, uygulamanın yüklemesini engelleyemez.

> [!TIP]
> Kullanıcılarınızın kişisel uygulamalar dahil cihazlarındaki tüm uygulamaların değerlendirileceğini ve uyumsuz uygulamaların engelleneceğini ya da uyumsuz olarak bildirileceğini anladığından emin olmak için kullanıcılara yönelik hüküm ve koşullar yapılandırabilirsiniz. Kullanıcılar, uygulamalara erişmek üzere cihazlarını kaydedip şirket portalını kullanmadan önce bu hüküm ve koşulları kabul etmelidir. Hüküm ve koşulları kullanma hakkında daha fazla bilgi için bkz. [Microsoft Intune’da hüküm ve koşullar ilkesi ayarları](terms-and-condition-policy-settings-in-microsoft-intune.md).

Aradığınız ayar bu konuda çıkmıyorsa, cihazı denetlemek için OMA-URI ayarları kullanmanıza izin veren bir Android özel ilkesi kullanarak ayar oluşturabilirsiniz. Daha fazla bilgi için bu konunun devamındaki [Özel ilke ayarları](#custom-policy-settings)’na gidin.

### Parola ayarları

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX|
|----------------|-|----------------|----------------|
|**Mobil cihazların kilidini açmak için bir parola gerektir**|Desteklenen cihazlarda bir parola istenip istenmeyeceğini belirtir.|Evet|Evet|
|**Minimum parola uzunluğu**|Minimum parola uzunluğunu belirtir.|Evet|Evet|
|**Cihaz temizlenmeden önce izin verilen yinelenen oturum açma hatası sayısı**|Cihaz silinmeden önce başarısız oturum açma sayısını belirtir.|Evet|Evet|
|**Ekran kapanmadan önce geçen işlem yapılmayan dakika sayısı**|Cihaz otomatik olarak kilitlenmeden önce işlem yapılmayan dakika sayısını belirtir.|Evet|Evet|
|**Parola geçerlilik süresi (gün)**|Parola değiştirilmeden önce geçmesi gereken gün sayısını belirtir.|Evet|Evet|
|**Parola geçmişini anımsa**|Daha önce kullanılan parolalardan kaç tanesinin hatırlanacağını belirtir.|Evet|Evet|
|**Parola geçmişini anımsa** - **Önceki parolaların yeniden kullanılmasını önle**|Önceki parolaların yeniden kullanılmasını engeller.|Evet|Evet|
|**Parola kalitesi**|Gereken parola karmaşıklık düzeyini ve biyometrik cihaz kullanılıp kullanılamayacağını belirtir.|Evet|Evet|
|**Parmak izi ile kilit açmaya izin ver**|Cihaz kilidini açmak için parmak izi kullanılmasına izin verir.|Hayır|Evet|
|**Akıllı Kilit ve diğer güven aracılarına izin ver**<br>(Android 5 ve üzeri)|Uyumlu Android cihazlarda Akıllı Kilitleme özelliğini denetlemenize izin verir. Güven aracısı olarak da bilinen bu telefon özelliği, cihaz güvenilir bir konumdayken (örneğin, belirli bir Bluetooth cihazına bağlı ya da bir NFC etiketinin yakınında olduğunda) cihazın kilitleme ekranı parolasını devre dışı bırakmanıza veya atlamanıza izin verir. Bu ayarı kullanıcıların Akıllı Kilitleme’yi yapılandırmasını önlemek için kullanabilirsiniz.|Evet|Hayır|

### Şifreleme ayarları

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Cihazda şifrelemeyi gerektir**|Mobil cihazdaki dosyaların şifrelenmesini gerektirir.|Evet|Evet|
|**Depolama kartlarında şifrelemeyi gerektir**|Cihaz depolama kartını şifrelemenin gerekip gerekmediğini belirtir.|Hayır|Evet|

### Sistem ayarları

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Ekran yakalamaya izin ver**|Kullanıcının ekran içeriğini resim olarak yakalamasına izin verir.|Hayır|Evet|
|**Tanılama verilerinin gönderimine izin ver**|Cihazın Google’a tanılama bilgileri göndermesine izin verir.|Hayır|Evet|
|**Fabrika sıfırlamasına izin ver**|Kullanıcının cihazda fabrika sıfırlaması gerçekleştirmesine izin verir.|Hayır|Evet|

### Bulut ayarları - belgeler ve veriler

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX|
|----------------|----------------------------|----------------|
|**Google yedeklemesine izin ver**|Google yedeklemesi kullanmaya izin verir.|Hayır|Evet|

### Bulut ayarları - hesaplar ve eşitleme

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Google hesabı otomatik eşitlemesine izin ver**|Google hesabı ayarlarının otomatik olarak eşitlenmesine izin verir.|Hayır|Evet|

### Uygulama ayarları - tarayıcı

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Web tarayıcısına izin ver**|Cihazın varsayılan web tarayıcısının kullanılıp kullanılamayacağını belirtir.|Hayır|Evet|
|**Otomatik doldurmaya izin ver**|Kullanılacak web tarayıcısının otomatik doldurma işlevine izin verir.|Hayır|Evet|
|**Açılır pencere engelleyicisine izin ver**|Web tarayıcısında açılır pencere engelleyicisinin kullanılmasına izin verir.|Hayır|Evet|
|**Tanımlama bilgilerine izin ver**|Cihazın web tarayıcısının tanımlama bilgileri kullanmasına izin verir.|Hayır|Evet|
|**Etkin betik yazmaya izin ver**|Cihazın web tarayıcısının etkin betik kullanmasına izin verir.|Hayır|Evet|

### Uygulama ayarları - uygulamalar

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Google Play mağazasına izin ver**|Kullanıcının cihazda Google Play mağazasına erişmesine izin verir.|Hayır|Evet|

### Cihaz özellikleri ayarları - donanım

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Kameraya izin ver**|Cihaz kamerasının kullanılmasına izin verir.|Evet|Evet|
|**Çıkarılabilir depolama birimine izin ver**|Cihazda SD kartı gibi çıkarılabilir depolama birimi kullanılmasına izin verir.|Hayır|Evet|
|**Wi-Fi'a izin ver**|Cihazın Wi-Fi özelliklerinin kullanımına izin verir.|Hayır|Evet|
|**Wi-Fi İnternet paylaşımına izin ver**|Cihazda Wi-Fi internet paylaşımı kullanımına izin verir.|Hayır|Evet|
|**Coğrafi konuma izin ver**|Cihazın konum bilgilerini kullanmasına izin verir.|Hayır|Evet|
|**NFC'ye izin ver**|Cihaz destekliyorsa, yakın alan iletişimi kullanan işlemlere izin verir.|Hayır|Evet|
|**Bluetooth'a izin ver**|Cihazda Bluetooth özelliğinin kullanımına izin verir.|Hayır|Evet|
|**Kapatmaya izin ver**|Kullanıcının cihazı kapatmasına izin verir.<br /><br />Bu ayar devre dışı bırakılırsa, Samsung KNOX cihazları için **Cihaz temizlenmeden önce izin verilen yinelenen oturum açma hatalarının sayısı** ayarı çalışmaz.|Hayır|Evet|

### Cihaz özellikleri ayarları - cep telefonu

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Sesli dolaşıma izin ver**|Cihaz cep telefonu şebekesindeyken ses dolaşımına izin verir.|Hayır|Evet|
|**Veri dolaşımına izin ver**|Cihaz cep telefonu şebekesindeyken veri dolaşımına izin verir.|Hayır|Evet|
|**SMS/MMS iletilerine izin ver**|Cihazda SMS ve MMS mesajlaşması kullanımına izin verir.|Hayır|Evet|

### Cihaz özellikleri ayarları - özellikler

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Sesli yardımcıya izin ver**|Cihazda sesli yardım yazılımının kullanımına izin verir.|Hayır|Evet|
|**Sesli aramaya izin ver**|Cihazda sesli arama özelliğinin kullanımını etkinleştirir veya devre dışı bırakır.|Hayır|Evet|
|**Kopyalama ve yapıştırmaya izin ver**|Cihazda kopyalama ve yapıştırma işlevine izin verir.|Hayır|Evet|
|**Uygulamalar arasında pano paylaşımına izin ver**|Uygulamalar arasında kopyalama ve yapıştırma için panonun kullanılmasına izin verir.|Hayır|Evet|
|**YouTube'a izin ver**|Cihazda YouTube kullanılmasına izin verir.|Hayır|Evet|

### Uyumlu ve uyumlu olmayan uygulamalar için ayarlar
**Uyumlu &amp; Uyumsuz Uygulamalar** listesinde, aşağıdaki bilgileri kullanan uyumlu veya uyumsuz uygulamaların bir listesini belirtin:

> [!NOTE]
> Tek bir ilke, yalnızca uyumlu uygulamaların veya uyumsuz uygulamaların bir listesini içerebilir. İkisi de aynı ilkede belirtemezsiniz.

|Ayar adı|Ayrıntılar|
|----------------|--------------------|
|**Kullanıcılar listelenen uygulamaları yüklediğinde uyumsuzluk bildir**|Intune tarafından yönetilmeyen ve kullanıcıların yükleyip çalıştırmasını istemediğiniz uygulamaları listeler. Kullanıcılar bu uygulamalardan birini yüklerse, uygulama uyumsuz uygulamalar raporunda listelenir.|
|**Kullanıcılar listelenen uygulamaları yüklediğinde uyumsuzluk bildirme**|İzin vermek istediğiniz uygulamaları listeler. Uyumluluğun korunması için, kullanıcılar listelenmeyen uygulamaları yüklememelidir. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir.|
|**Ekle**|Seçili listeye bir uygulama ekler. Uygulamanın adını, uygulama yayımcısını (isteğe bağlı) ve uygulamanın uygulama mağazasındaki URL’sini belirtin.<br /><br />Daha fazla bilgi için bu konunun devamındaki [Uygulama mağazalarının URL’lerini belirtme](#specify-urls-to-app-stores) bölümüne bakın.|
|**Uygulamaları İçeri Aktar**|Belirttiğiniz uygulamaların virgülle ayrılmış bir listesini içeri aktarır. Dosyadaki biçimi, uygulama adını, yayımcıyı ve uygulama URL'sini kullanın.|
|**Düzenle**|Seçilen uygulamanın adını, yayımcısını ve URL'sini düzenlemenize izin verir.|
|**Sil**|Seçilen uygulamayı listeden siler.|

### Bilgi noktası modu ayarları
**Samsung KNOX cihazları** için aşağıdaki ayarları belirtin:

|Ayar adı|Ayrıntılar|
|----------------|--------------------|
|**Cihaz bilgi noktası modundayken çalışabilecek yönetilen bir uygulama seçme**|**Gözat**’ı seçin, sonra cihaz bilgi noktası modundayken çalışabilecek yönetilen uygulamayı seçin (mağazaya bir bağlantı olarak belirtilen uygulamalar henüz desteklenmemektedir). Cihazda başka hiçbir uygulamanın çalışmasına izin verilmez.|
|**Ses düğmelerine izin ver**|Cihazdaki ses düğmelerinin kullanımını etkinleştirir veya devre dışı bırakır.|
|**Açma/kapatma düğmesine izin ver**|Cihazın açma/kapatma düğmesini etkinleştirir veya devre dışı bırakır.|

### Uyumlu ve uyumlu olmayan uygulamalar için başvuru bilgileri

#### Uyumlu ve uyumsuz uygulamaları izle
 **Uyumlu Olmayan Uygulamalar Raporu** 'nu kullanarak izin verilen ve engellenen uygulamaların uyumluluğunu görüntüleyin.

###### Uyumlu Olmayan Uygulamalar Raporu'nu çalıştırmak için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com), **Raporlar** &gt; **Uyumsuz Uygulamalar Raporu**’nu seçin.

2.  Denetlemek istediğiniz cihaz gruplarını seçin. Sonra uyumlu uygulamaları mı, uyumsuz uygulamaları mı, her ikisini birden mi denetlemek istediğinizi belirleyin. Son olarak, **Raporu Görüntüle**’yi seçin.

#### Uygulama mağazalarının URL'lerini belirtme
Uyumlu veya uyumsuz uygulama listesinde bir uygulama URL'si belirtmek için aşağıdaki adımları uygulayın:

[Google Play'in uygulamalar bölümünde](https://play.google.com/store/apps) kullanmak istediğiniz uygulamayı arayın.

Uygulamanın yükleme sayfasını açın ve URL'yi panoya kopyalayın. Artık bunu uyumlu uygulamalar listesinde veya uyumsuz uygulamalar listesinde gerekli URL olarak kullanabilirsiniz.

Örnek: Microsoft Office Mobile için Google Play'i arayın. Kullandığınız URL **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub** olacaktır.

## Özel ilke ayarları
Android cihazlardaki özellikleri denetlemek için kullanılabilen OMA-URI ayarlarını dağıtmak için Microsoft Intune **Android özel yapılandırma ilkesini** kullanın. Bunlar, birçok mobil cihaz üreticisinin, cihaz özelliklerini denetlemek için kullandığı standart ayarlardır.

Bu özellik, Intune ilkeleri ile yapılandırılabilir olmayan Android ayarlarını dağıtmanıza olanak sağlamak için tasarlanmıştır.

> [!NOTE]
> Şu anda Android özel ilkeleri yalnızca önceden paylaşılan bir anahtar içeren Android cihazlar için Wi-Fi ayarlarının yapılandırılmasını destekler.

### Genel ayarlar

|Ayar adı|Ayrıntılar|
    |----------------|--------------------|
    |**Ad**|Intune konsolunda tanımlamanıza yardımcı olması için Android özel ilkesine benzersiz bir ad girin.|
    |**Açıklama**|Android özel ilkesine genel bakış ve onu bulmanıza yardımcı olacak diğer ilgili bilgileri sunan bir açıklama sağlayın.|

### OMA-URI ayarları

   |Ayar adı|Ayrıntılar|
    |--------|--------------------|
    |**Ayar adı**|Ayarlar listesinde tanımanıza yardımcı olması için OMA-URI ayarı için benzersiz bir ad girin.|
    |**Ayar açıklaması**|Ayara genel bir bakış ve ayarı bulmanıza yardımcı olacak diğer ek bilgileri içeren bir açıklama sağlayın.|
    |**Veri türü**|Bu OMA-URI ayarını belirteceğiniz veri türünü seçin. **Dize, Dize (XML), Tarih ve saat, Tamsayı, Kayan nokta** veya **Boole değeri** seçeneklerinden birini belirleyin.|
    |**OMA-URI (büyük küçük harf duyarlı)**|Bir ayar için sağlamak istediğiniz OMA-URI’yi belirtin.|
    |**Değer**|Önceden belirttiğiniz OMA-URI ile ilişkilendirilecek değeri belirtin.|

### Örnekler

- [Önceden paylaşılan anahtar ile Wi-Fi profili oluşturma](pre-shared-key-wi-fi-profile.md)
- [Özel ilke kullanarak Android cihazları için uygulama başına VPN profili oluşturma](per-app-vpn-for-android-pulse-secure.md)
- [Özel ilkeler kullanarak Samsung KNOX cihazları için uygulamalara izin verme veya bunları engelleme](custom-policy-to-allow-and-block-samsung-knox-apps.md)

### Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Aug16_HO5-->


