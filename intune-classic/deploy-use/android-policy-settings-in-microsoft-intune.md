---
title: "Android ve Samsung KNOX ilke ayarları"
description: "Intune ile yönettiğiniz Android cihazlarında ayarları ve özellikleri denetleyen ilkeler oluşturun."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 10/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71cc39cf-e726-40fd-8d08-78776e099a4b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e1b18486f84bb5d4d47caceb871bf6884b9b8f89
ms.sourcegitcommit: 53a1f5226d1e1172f013a1b192321dde610b2d6c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2017
---
# <a name="android-and-samsung-knox-standard-policy-settings-in-microsoft-intune"></a>Microsoft Intune’da Android ve Samsung KNOX Standard ilke ayarları

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune, Android cihazlarda yapılandırabileceğiniz bir dizi yerleşik genel ayar sunar. Buna ek olarak, Intune’da bulunmayan özel ayarlar oluşturmak için Açık Mobil Ortaklığı Tekdüzen Kaynak Tanımlayıcısı (OMA-URI) değerleri belirtebilirsiniz.

## <a name="general-configuration-policy"></a>Genel yapılandırma ilkesi

Aşağıdakilerin ayarlarını yapılandırmak için Intune **Android genel yapılandırma ilkesini** kullanın:

-   **Mobil cihaz güvenliği ayarları** - Cihazda bir dizi özelliği ve işlevi denetlemenize olanak tanıyan önceden tanımlanmış ayarlar listesinden seçim yapın.

-   **Bilgi noktası modu** (yalnızca Samsung KNOX Standard cihazlar için) - Bir cihazı, yalnızca belirli özelliklerin çalışmasına izin verecek şekilde kilitleyin. Örneğin, cihazın yalnızca belirttiğiniz bir yönetilen uygulamayı çalıştırmasına izin verebilir veya cihazdaki ses düğmelerini devre dışı bırakabilirsiniz. Bu ayarlar, bir cihazın tanıtım modeli için veya satış noktası cihazı gibi yalnızca tek bir işlevi gerçekleştirmeye ayrılmış bir cihaz için kullanılabilir.

-   **Uyumlu ve uyumsuz uygulamalar** - Şirketinizdeki uyumlu veya uyumsuz uygulamaların bir listesini belirtin. Android ve iOS cihazlarında, **Uyumsuz Uygulamalar Raporu**, listede belirttiğiniz uygulamaların kullanıcıların yüklemiş olduğu uygulamalara karşılık uyumluluğunu görmek için kullanılabilir. Rapor, uygulamanın yüklemesini engelleyemez.

> [!TIP]
> Kullanıcılarınızın kişisel uygulamalar dahil cihazlarındaki tüm uygulamaların değerlendirileceğini ve uyumsuz uygulamaların engelleneceğini ya da uyumsuz olarak bildirileceğini anladığından emin olmak için kullanıcılara yönelik hüküm ve koşullar yapılandırabilirsiniz. Kullanıcılar, uygulamalara erişmek üzere cihazlarını kaydedip şirket portalını kullanmadan önce bu hüküm ve koşulları kabul etmelidir. Hüküm ve koşulları kullanma hakkında daha fazla bilgi için bkz. [Microsoft Intune’da hüküm ve koşullar ilkesi ayarları](terms-and-condition-policy-settings-in-microsoft-intune.md).

Aradığınız ayar bu konuda çıkmıyorsa, cihazı denetlemek için OMA-URI ayarları kullanmanıza izin veren bir Android özel ilkesi kullanarak ayar oluşturabilirsiniz. Daha fazla bilgi için bu konunun devamındaki [Özel ilke ayarları](#custom-policy-settings)’na gidin.

### <a name="password-settings"></a>Parola ayarları

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX Standard|
|----------------|-|----------------|----------------|
|**Mobil cihazların kilidini açmak için bir parola iste**|Desteklenen cihazlarda bir parola istenip istenmeyeceğini belirtir.|Evet|Evet|
|**En düşük parola uzunluğu**|Minimum parola uzunluğunu belirtir.|Evet|Evet|
|**Cihaz silinmeden önce izin verilen yinelenen oturum açma hatası sayısı**|Cihaz silinmeden önce başarısız oturum açma sayısını belirtir.|Evet|Evet|
|**Ekran kapanmadan önce herhangi bir işlem yapılmadan geçen dakika sayısı**|Cihaz otomatik olarak kilitlenmeden önce işlem yapılmayan dakika sayısını belirtir.|Evet|Evet|
|**Parola kullanım süresi (gün)**|Parola değiştirilmeden önce geçmesi gereken gün sayısını belirtir.|Evet|Evet|
|**Parola geçmişini anımsa**|Daha önce kullanılan parolalardan kaç tanesinin hatırlanacağını belirtir.|Evet|Evet|
|**Parola geçmişini anımsa** - **Önceki parolaların yeniden kullanılmasını önle**|Önceki parolaların yeniden kullanılmasını engeller.|Evet|Evet|
|**Parola kalitesi**|Gereken parola karmaşıklık düzeyini ve biyometrik cihaz kullanılıp kullanılamayacağını belirtir.|Evet|Evet|
|**Parmak izi ile kilit açmaya izin ver**|Cihaz kilidini açmak için parmak izi kullanılmasına izin verir.|Hayır|Evet|
|**Akıllı Kilit ve diğer güven aracılarına izin ver**<br>(Android 5 ve üzeri)|Uyumlu Android cihazlarda Akıllı Kilitleme özelliğini denetlemenize izin verir. Güven aracısı olarak da bilinen bu telefon özelliği, cihaz güvenilir bir konumdayken (örneğin, belirli bir Bluetooth cihazına bağlı ya da bir NFC etiketinin yakınında olduğunda) cihazın kilitleme ekranı parolasını devre dışı bırakmanıza veya atlamanıza izin verir. Bu ayarı kullanıcıların Akıllı Kilitleme’yi yapılandırmasını önlemek için kullanabilirsiniz.|Evet|Hayır|

### <a name="encryption-settings"></a>Şifreleme ayarları

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX Standard|
|----------------|---|-------------|----------------|
|**Cihazda şifrelemeyi gerektir**|Mobil cihazdaki dosyaların şifrelenmesini gerektirir.|Evet|Evet|
|**Depolama kartlarında şifreleme iste**|Cihaz depolama kartını şifrelemenin gerekip gerekmediğini belirtir.|Hayır|Evet|

### <a name="system-settings"></a>Sistem ayarları

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX Standard|
|----------------|---|-------------|----------------|
|**Ekran yakalamaya izin ver**|Kullanıcının ekran içeriğini resim olarak yakalamasına izin verir.|Hayır|Evet|
|**Tanılama verilerinin gönderimine izin ver**|Cihazın Google’a tanılama bilgileri göndermesine izin verir.|Hayır|Evet|
|**Fabrika sıfırlamasına izin ver**|Kullanıcının cihazda fabrika sıfırlaması gerçekleştirmesine izin verir.|Hayır|Evet|

### <a name="cloud-settings---documents-and-data"></a>Bulut ayarları - belgeler ve veriler

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX Standard|
|----------------|----|------------------------|----------------|
|**Google yedeklemesine izin ver**|Google yedeklemesi kullanmaya izin verir.|Hayır|Evet|

### <a name="cloud-settings---accounts-and-synchronization"></a>Bulut ayarları - hesaplar ve eşitleme

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX Standard|
|----------------|-----|-----------|----------------|
|**Google hesabı otomatik eşitlemesine izin ver**|Google hesabı ayarlarının otomatik olarak eşitlenmesine izin verir.|Hayır|Evet|

### <a name="application-settings---browser"></a>Uygulama ayarları - tarayıcı

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX Standard|
|----------------|-----|-----------|----------------|
|**Web tarayıcısına izin ver**|Cihazın varsayılan web tarayıcısının kullanılıp kullanılamayacağını belirtir.|Hayır|Evet|
|**Otomatik doldurmaya izin ver**|Kullanılacak web tarayıcısının otomatik doldurma işlevine izin verir.|Hayır|Evet|
|**Açılır pencere engelleyicisine izin ver**|Web tarayıcısında açılır pencere engelleyicisinin kullanılmasına izin verir.|Hayır|Evet|
|**Tanımlama bilgilerine izin ver**|Cihazın web tarayıcısının tanımlama bilgileri kullanmasına izin verir.|Hayır|Evet|
|**Etkin betik yazmaya izin ver**|Cihazın web tarayıcısının etkin betik kullanmasına izin verir.|Hayır|Evet|

### <a name="application-settings---apps"></a>Uygulama ayarları - uygulamalar

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX Standard|
|----------------|----|------------|----------------|
|**Google Play mağazasına izin ver**|Kullanıcının cihazda Google Play mağazasına erişmesine izin verir.|Hayır|Evet|

### <a name="device-capabilities-settings---hardware"></a>Cihaz özellikleri ayarları - donanım

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX Standard|
|----------------|-----|-----------|----------------|
|**Kameraya izin ver**|Cihaz kamerasının kullanılmasına izin verir.|Evet|Evet|
|**Çıkarılabilir depolama birimine izin ver**|Cihazda SD kartı gibi çıkarılabilir depolama birimi kullanılmasına izin verir.|Hayır|Evet|
|**Wi-Fi bağlantısına izin ver**|Cihazın Wi-Fi özelliklerinin kullanımına izin verir.|Hayır|Evet|
|**Wi-Fi İnternet paylaşımına izin ver**|Cihazda Wi-Fi internet paylaşımı kullanımına izin verir.|Hayır|Evet|
|**Coğrafi konuma izin ver**|Cihazın konum bilgilerini kullanmasına izin verir.|Hayır|Evet|
|**NFC'ye izin ver**|Cihaz destekliyorsa, yakın alan iletişimi kullanan işlemlere izin verir.|Hayır|Evet|
|**Bluetooth'a izin ver**|Cihazda Bluetooth özelliğinin kullanımına izin verir.|Hayır|Evet|
|**Kapatmaya izin ver**|Kullanıcının cihazı kapatmasına izin verir.<br /><br />Bu ayar devre dışı bırakılırsa, Samsung KNOX Standard cihazları için **Cihaz temizlenmeden önce izin verilen yinelenen oturum açma hatalarının sayısı** ayarı çalışmaz.|Hayır|Evet|

### <a name="device-capabilities-settings---cellular"></a>Cihaz özellikleri ayarları - cep telefonu

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX Standard|
|----------------|---|-------------|----------------|
|**Ses dolaşımına izin ver**|Cihaz cep telefonu şebekesindeyken ses dolaşımına izin verir.|Hayır|Evet|
|**Veri dolaşımına izin ver**|Cihaz cep telefonu şebekesindeyken veri dolaşımına izin verir.|Hayır|Evet|
|**SMS/MMS iletilerine izin ver**|Cihazda SMS ve MMS mesajlaşması kullanımına izin verir.|Hayır|Evet|

### <a name="device-capabilities-settings---features"></a>Cihaz özellikleri ayarları - özellikler

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX Standard|
|----------------|----|------------|----------------|
|**Sesli yardıma izin ver**|Cihazda sesli yardım yazılımının kullanımına izin verir.|Hayır|Evet|
|**Sesli aramaya izin ver**|Cihazda sesli arama özelliğinin kullanımını etkinleştirir veya devre dışı bırakır.|Hayır|Evet|
|**Kopyalama ve yapıştırmaya izin ver**|Cihazda kopyalama ve yapıştırma işlevine izin verir.|Hayır|Evet|
|**Uygulamalar arasında pano paylaşımına izin ver**|Uygulamalar arasında kopyalama ve yapıştırma için panonun kullanılmasına izin verir.|Hayır|Evet|
|**YouTube'a izin ver**|Cihazda YouTube kullanılmasına izin verir.|Hayır|Evet|

### <a name="settings-for-compliant-and-noncompliant-apps"></a>Uyumlu ve uyumlu olmayan uygulamalar için ayarlar
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

Uyumlu ve uyumsuz uygulama ayarlarını içeren ilkelerin kullanıcı gruplarına dağıtılması gerekir.

### <a name="kiosk-mode-settings"></a>Bilgi noktası modu ayarları
**Samsung KNOX Standard cihazlar** için aşağıdaki ayarları belirtin:

|Ayar adı|Ayrıntılar|
|----------------|--------------------|
|**Cihaz bilgi noktası modundayken çalışabilecek yönetilen bir uygulama seçin**|**Gözat**’ı seçin, sonra cihaz bilgi noktası modundayken çalışabilecek yönetilen uygulamayı seçin (mağazaya bir bağlantı olarak belirtilen uygulamalar henüz desteklenmemektedir). Cihazda başka hiçbir uygulamanın çalışmasına izin verilmez.|
|**Ses düzeyi düğmelerine izin ver**|Cihazdaki ses düğmelerinin kullanımını etkinleştirir veya devre dışı bırakır.|
|**Uyku/uyandırma düğmesine izin ver**|Cihazın açma/kapatma düğmesini etkinleştirir veya devre dışı bırakır.|

### <a name="reference-information-for-compliant-and-noncompliant-apps"></a>Uyumlu ve uyumlu olmayan uygulamalar için başvuru bilgileri

#### <a name="monitor-compliant-and-noncompliant-apps"></a>Uyumlu ve uyumsuz uygulamaları izle
**Uyumlu Olmayan Uygulamalar Raporu** 'nu kullanarak izin verilen ve engellenen uygulamaların uyumluluğunu görüntüleyin.

###### <a name="to-run-the-noncompliant-apps-report"></a>Uyumlu Olmayan Uygulamalar Raporu'nu çalıştırmak için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com), **Raporlar** &gt; **Uyumsuz Uygulamalar Raporu**’nu seçin.

2.  Denetlemek istediğiniz cihaz gruplarını seçin. Sonra uyumlu uygulamaları mı, uyumsuz uygulamaları mı, her ikisini birden mi denetlemek istediğinizi belirleyin. Son olarak, **Raporu Görüntüle**’yi seçin.

#### <a name="specify-urls-to-app-stores"></a>Uygulama mağazalarının URL'lerini belirtme
Uyumlu veya uyumsuz uygulama listesinde bir uygulama URL'si belirtmek için aşağıdaki adımları uygulayın:

[Google Play'in uygulamalar bölümünde](https://play.google.com/store/apps) kullanmak istediğiniz uygulamayı arayın.

Uygulamanın yükleme sayfasını açın ve URL'yi panoya kopyalayın. Artık bunu uyumlu uygulamalar listesinde veya uyumsuz uygulamalar listesinde gerekli URL olarak kullanabilirsiniz.

Örnek: Microsoft Office Mobile için Google Play'i arayın. Kullandığınız URL **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub** olacaktır.

## <a name="custom-policy-settings"></a>Özel ilke ayarları
Android cihazlardaki özellikleri denetlemek için kullanılabilen OMA-URI ayarlarını dağıtmak için Microsoft Intune **Android özel yapılandırma ilkesini** kullanın. Bunlar, birçok mobil cihaz üreticisinin, cihaz özelliklerini denetlemek için kullandığı standart ayarlardır.

Bu özellik, Intune ilkeleri ile yapılandırılabilir olmayan Android ayarlarını dağıtmanıza olanak sağlamak için tasarlanmıştır.
Intune, şu anda sınırlı sayıda Android özel ilkesi destekler. Hangi ilkeleri yapılandırabileceğinizi öğrenmek için bu konu başlığındaki örneklere bakın.

### <a name="general-settings"></a>Genel ayarlar

|Ayar adı|Ayrıntılar|
    |----------------|--------------------|
    | **Ad** |Intune konsolunda tanımlamanıza yardımcı olması için Android özel ilkesine benzersiz bir ad girin.|
    | **Açıklama** |Android özel ilkesine genel bakış ve onu bulmanıza yardımcı olacak diğer ilgili bilgileri sunan bir açıklama sağlayın.|

### <a name="oma-uri-settings"></a>OMA-URI ayarları

   |Ayar adı|Ayrıntılar|
    |--------|--------------------|
    | **Ayar Adı** |Ayarlar listesinde tanımanıza yardımcı olması için OMA-URI ayarı için benzersiz bir ad girin.|
    | **Ayar açıklaması** |Ayara genel bir bakış ve ayarı bulmanıza yardımcı olacak diğer ek bilgileri içeren bir açıklama sağlayın.|
    | **Veri türü** |Bu OMA-URI ayarını belirteceğiniz veri türünü seçin. **Dize, Dize (XML), Tarih ve saat, Tamsayı, Kayan nokta** veya **Boole değeri** seçeneklerinden birini belirleyin.|
    | **OMA-URI (büyük küçük harfe duyarlı)** |Bir ayar için sağlamak istediğiniz OMA-URI’yi belirtin.|
    | **Değer** |Önceden belirttiğiniz OMA-URI ile ilişkilendirilecek değeri belirtin.|

### <a name="examples"></a>Örnekler

- [Önceden paylaşılan anahtar ile Wi-Fi profili oluşturma](pre-shared-key-wi-fi-profile.md)
- [Özel ilke kullanarak Android cihazlar için uygulama başına VPN profili oluşturma](per-app-vpn-for-android-pulse-secure.md)
- [Özel ilkeler kullanarak Samsung KNOX cihazları için uygulamalara izin verme veya bunları engelleme](custom-policy-to-allow-and-block-samsung-knox-apps.md)

## <a name="supported-samsung-knox-standard-devices"></a>Desteklenen Samsung KNOX Standard cihazlar

Şirket Portalı uygulaması, yalnızca cihazın [desteklenen KNOX cihazlar listesinde](https://www.samsungknox.com/knox-supported-devices/knox-workspace) görüntülendiği durumlarda MDM kaydı sırasında Samsung KNOX etkinleştirmesi yapmaya çalışır. Böylece MDM kaydını önleyen KNOX kayıt hatalarının önüne geçilir. Samsung KNOX etkinleştirmesini desteklemeyen cihazlar, standart Android cihazlar olarak kaydedilir. Bir Samsung cihazın KNOX’u destekleyen model numaraları olabilir, diğerlerinin olamaz. Samsung cihazlar satın alıp dağıtmadan önce, cihazınızın kurumsal bayisinden KNOX uyumluluğunu doğrulayın.

Aşağıdaki Samsung cihaz modelleri KNOX’u desteklemez ve Android için Şirket Portalı uygulaması tarafından yerel Android cihazlar olarak kaydedilir:

| **Cihaz adı** | **Cihaz model numaraları** |
| --- | --- |
| Galaxy A3 | SM-A300G<br>SM-A310Y<br>SM-A320FL |
| Galaxy A5 | SM-A500G |
| Galaxy Alpha | SM-G850M |
| Galaxy Avant | SM-G386T |
| Galaxy C9/C9 Pro | SM-C900F |
| Galaxy Core 2/Core 2 Duos | SM-G355H<br>SM-G355M |
| Galaxy Core Lite | SM-G3588V |
| Galaxy Core Prime | SM-G360H |
| Galaxy Core LTE | SM-G386F<br>SM-G386W |
| Galaxy Grand | GT-I9082L<br>GT-I9082<br>GT-I9080L |
| Galaxy Grand 3 | SM-G7200 |
| Galaxy Grand Neo | GT-I9060I |
| Galaxy Grand Prime | SM-G530M |
| Galaxy Grand Prime Value Edition | SM-G531H |
| Galaxy J Max | SM-T285YD |
| Galaxy J1 | SM-J100H<br>SM-J100M<br>SM-J100ML |
| Galaxy J1 Ace | SM-J110F<br>SM-J110H |
| Galaxy J1 Mini | SM-J105M |
| Galaxy J2/J2 Pro | SM-J200H<br>SM-J210F |
| Galaxy J3 | SM-J320F<br>SM-J320FN<br>SM-J320H<br>SM-J320M<br>SM-J320W8 |
| Galaxy J5 | SM-J500G |
| Galaxy J7 | SM-J710F |
| Galaxy J7 Prime | SM-J727T1 |
| Galaxy K Zoom | SM-C115 |
| Galaxy Light | SGH-T399N |
| Galaxy Note 3 | SM-N9002<br>SM-N9009 |
| Galaxy Note 5 | SM-N920G<br>SM-N920I<br>SM-N920W8 |
| Galaxy Note 7/Note 7 Duos | SM-N930S<br>SM-N9300<br>SM-N930F<br>SM-N930T<br>SM-N9300<br>SM-N930F<br>SM-N930S<br>SM-N930T |
| Galaxy Note 10.1 3G | SM-P602 |
| Galaxy NotePRO 12.2&quot; | SM-P902 |
| Galaxy On5 | SM-G570MSM-G570Y |
| Galaxy On7 | SM-G600FY<br>SM-G610M<br>SM-G610Y |
| Galaxy S2 Plus | GT-I9105P |
| Galaxy S3 Mini | SM-G730A<br>SM-G730V |
| Galaxy S3 Neo | GT-I9300<br>GT-I9300I |
| Galaxy S4 | SM-S975L |
| Galaxy S4 Active | GT-I9295 |
| Galaxy S4 Neo | SM-G318ML |
| Galaxy S5 | SM-G9006W<br>SM-G900M |
| Galaxy S5 Neo | SM-G903M |
| Galaxy S6 Edge | 404SCSM-G925I<br>SM-G928G |
| Galaxy Tab A 7.0&quot; | SM-T280SM-T285 |
| Galaxy Tab A 9.7&quot; | SM-P555M |
| Galaxy Tab 3 7&quot;/Tab 3 Lite 7&quot; | SM-T116SM-T210SM-T211 |
| Galaxy Tab 3 8.0&quot; | SM T311 |
| Galaxy Tab 3 10.1&quot; | GT-P5200<br>GT-P5210<br>GT-P5220 |
| Galaxy Trend 2 Lite | SM-G318H |
| Galaxy V Plus | SM-G318HZ |
| Galaxy Young 2 Duos | SM-G130BU |



### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
