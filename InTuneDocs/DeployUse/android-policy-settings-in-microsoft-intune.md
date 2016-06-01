---
# required metadata

title: Microsoft Intune’da Android yapılandırma ilkesi ayarları | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 71cc39cf-e726-40fd-8d08-78776e099a4b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune’da Android ilke ayarları

## Genel yapılandırma ilkesi

Microsoft Intune **Android genel yapılandırma ilkesini** kullanarak aşağıdaki ayarları yapılandırabilirsiniz:

-   **Mobil cihaz güvenliği ayarları** – Cihazda bir dizi özelliği ve işlevi denetlemenize olanak tanıyan önceden tanımlı ayarlar listesinden seçim yapın.

-   **Bilgi noktası modu** (yalnızca Samsung KNOX cihazlar için) - Bir cihazı yalnızca belirli özelliklerin çalışmasına olanak verecek şekilde kilitleyin. Örneğin, bir cihazın yalnızca belirttiğiniz bir yönetilen uygulamayı çalıştırmasına izin verebilir veya bir cihazdaki ses düğmelerini devre dışı bırakabilirsiniz. Bu ayarlar, bir cihazın tanıtım modeli için veya satış noktası cihazı gibi yalnızca bir işlevi gerçekleştirmeye ayrılan bir cihaz için kullanılabilir.

-   **Uyumlu ve uyumsuz uygulamalar** - Şirketinizdeki uyumlu veya uyumsuz uygulamaların listesini gösterir. Android ve iOS cihazlarında, **Uyumlu Olmayan Uygulamalar Raporu** ile listede belirttiğiniz uygulamalarla kullanıcıların yüklemiş olduğu uygulamalar karşılaştırılarak uyumlu olup olmadığı görüntülenebilir (ancak uygulamanın yüklenmesi engellenemez).

> [!TIP]
> Kullanıcılarınızın kişisel uygulamalar dahil olmak üzere cihazlarındaki uygulamaların değerlendirileceğini ve uyumsuz uygulamaların engelleneceğini ya da uyumsuz olarak bildirileceğini anladığından emin olmak kullanıcılara yönelik hüküm ve koşullar yapılandırabilirsiniz. Kullanıcılar, uygulamalara erişmek üzere cihazlarını kaydedip şirket portalını kullanmadan önce bu hüküm ve koşulları kabul etmelidir. Hüküm ve koşulları kullanma hakkında daha fazla bilgi için bkz. [Microsoft Intune’da hüküm ve koşullar ilkesi ayarları](terms-and-condition-policy-settings-in-microsoft-intune.md)..

Aradığınız ayar bu konu başlığı altında görünmüyorsa, cihazı denetlemek için OMA-URI ayarlarını kullanmanıza olanak sağlayan bir Android özel ilkesini kullanarak bu ayarı oluşturabilirsiniz. Daha fazla bilgi için, bu konunun devamındaki **Özel ilke ayarları** bölümüne bakın.

### Parola ayarları

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX|
|----------------|-|----------------|----------------|
|**Mobil cihazların kilidini açmak için bir parola gerektir**|Desteklenen cihazlarda bir parola gerektir.|Evet|Evet|
|**Minimum parola uzunluğu**|Parola için minimum uzunluk.|Evet|Evet|
|**Cihaz temizlenmeden önce izin verilen yinelenen oturum açma hatası sayısı**|Bu sayıda oturum açma denemesi başarısız olursa cihazı temizler.|Evet|Evet|
|**Ekran kapanmadan önce geçen işlem yapılmayan dakika sayısı**|Cihazın otomatik olarak kilitlenmesinden önce beklenecek dakika sayısını belirtin.|Evet|Evet|
|**Parola geçerlilik süresi (gün)**|Parolanın değiştirilmesi gerekmeden önce geçmesi gereken gün sayısı.|Evet|Evet|
|**Parola geçmişini anımsa**|Daha önce kullanılmış olan parolalardan burada belirtilen sayıda parola anımsanır.|Evet|Evet|
|**Parola geçmişini anımsa** – **Önceki parolaların tekrar kullanılmasını engeller**|Önceden kullanılan parolaların yeniden kullanılmasını önler.|Evet|Evet|
|**Parola kalitesi**|Gereken parola karmaşıklık düzeyini ve biyometrik cihazların kullanılıp kullanılamayacağını seçin.|Evet|Evet|
|**Parmak izi ile kilit açmaya izin ver**|Cihaz kilidini açmak için parmak izi kullanılmasına izin verin.|Hayır|Evet|

### Şifreleme ayarları

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Cihazda şifrelemeyi gerektir**|Mobil cihazdaki dosyaların şifrelenmesini gerektirir.|Evet|Evet|
|**Depolama kartlarında şifrelemeyi gerektir**|Cihaz depolama kartını şifrelemenin gerekip gerekmediğini belirtir.|Hayır|Evet|

### Sistem ayarları

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Ekran yakalamaya izin ver**|Kullanıcının ekran içeriğini bir resim olarak yakalamasına olanak sağlar.|Hayır|Evet|
|**Tanılama verilerinin gönderimine izin ver**|Cihazın Google’a tanılama bilgileri göndermesine izin verir.|Hayır|Evet|
|**Fabrika sıfırlamasına izin ver**|Kullanıcının cihazda bir fabrika sıfırlaması gerçekleştirmesine izin verin.|Hayır|Evet|

### Bulut ayarları – belgeler ve veriler

|Ayar adı|Ayrıntılar|Android be Samsung KNOX|Android 4.0+|
|----------------|----------------------------|----------------|
|**Google yedeklemesine izin ver**|Google yedeklemesinin kullanılmasına izin verir.|Hayır|Evet|

### Bulut ayarları – hesaplar ve eşitleme

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Google hesabı otomatik eşitlemesine izin ver**|Google hesabı ayarlarının otomatik olarak eşitlenmesine izin verir.|Hayır|Evet|

### Uygulama ayarları - tarayıcı

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Web tarayıcısına izin ver**|Cihaz web tarayıcısının kullanılıp kullanılamayacağını belirtir.|Hayır|Evet|
|**Otomatik doldurmaya izin ver**|Kullanılacak web tarayıcısının Otomatik Doldurma işlevine izin verin.|Hayır|Evet|
|**Açılır pencere engelleyicisine izin ver**|Web tarayıcısında açılır pencere engelleyicisinin kullanılmasına izin verir.|Hayır|Evet|
|**Tanımlama bilgilerine izin ver**|Cihazın web tarayıcısının tanımlama bilgilerini kullanmasına izin verin.|Hayır|Evet|
|**Etkin betik yazmaya izin ver**|Cihazın web tarayıcısının etkin betik kullanmasına izin verin.|Hayır|Evet|

### Uygulama ayarları - uygulamalar

|Ayar adı|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Google Play mağazasına izin ver**|Kullanıcının cihazda Google Play mağazasına erişmesine izin verin.|Hayır|Evet|

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
|**Sesli dolaşıma izin ver**|Cihaz cep telefonu şebekesindeyken sesli dolaşıma izin verin.|Hayır|Evet|
|**Veri dolaşımına izin ver**|Cihaz cep telefonu şebekesindeyken veri dolaşımına izin verin.|Hayır|Evet|
|**SMS/MMS iletilerine izin ver**|Cihazda SMS ve MMS mesajlaşmasının kullanımına izin verin.|Hayır|Evet|

### Cihaz özellikleri ayarları - özellikler

|Ayar adı|Ayrıntılar|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Sesli yardımcıya izin ver**|Cihazda sesli yardım yazılımının kullanımına izin verir.|Hayır|Evet|
|**Sesli aramaya izin ver**|Cihazda sesli arama özelliğinin kullanımını etkinleştirir veya devre dışı bırakır.|Hayır|Evet|
|**Kopyalama ve yapıştırmaya izin ver**|Cihazda kopyalama ve yapıştırma işlevine izin verin.|Hayır|Evet|
|**Uygulamalar arasında pano paylaşımına izin ver**|Uygulamalar arasında kopyalama ve yapıştırma için panoyu kullanın.|Hayır|Evet|
|**YouTube'a izin ver**|Cihazda YouTube’un kullanımına izin verin.|Hayır|Evet|

### Uyumlu ve uyumlu olmayan uygulamalar için ayarlar
**Uyumlu ve Uyumsuz Uygulamalar** listesinde, aşağıdaki bilgileri kullanarak uyumlu veya uyumsuz uygulamalar listesini belirtin:

> [!NOTE]
> Tek bir ilke, yalnızca uyumlu uygulamaların veya uyumsuz uygulamaların listesini içerebilir. İkisi de aynı ilkede belirtemezsiniz.

|Ayar adı|Ayrıntılar|
|----------------|--------------------|
|**Kullanıcılar listelenen uygulamaları yüklediğinde uyumsuzluk bildir**|Kullanıcıların yüklemesine ve çalıştırmasına için izin verilmeyen, Intune tarafından yönetilmeyen uygulamaları listeler.|
|**Kullanıcılar listelenen uygulamaları yüklediğinde uyumsuzluk bildirme**|Kullanıcıların yüklemesine izin verilen uygulamaları listeler. Uyumluluğun korunması için kullanıcılar listelenmeyen uygulamaları yüklememelidir. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir.|
|**Ekle**|Seçili listeye bir uygulama ekler. Tercih ettiğiniz bir ad (isteğe bağlı olarak uygulama yayımcısı) ve uygulamanın uygulama mağazasındaki URL'sini belirtin.<br /><br />Yardım için, bu konunun Uygulama mağazalarının URL’lerini belirtme bölümüne bakın.|
|**Uygulamaları İçeri Aktar**|Virgülle ayrılmış bir değerler dosyasında belirttiğiniz uygulamaların listesini içeri aktarır. Dosyadaki biçim, uygulama adı, yayımcı, uygulama URL'sini kullanın.|
|**Düzenle**|Seçilen uygulamanın adını, yayımcısını ve URL'sini düzenlemenize imkan tanır.|
|**Sil**|Seçilen uygulamayı listeden siler.|

### Bilgi noktası modu ayarları
**Samsung KNOX cihazları** için aşağıdaki ayarları belirtin:

|Ayar adı|Ayrıntılar|
|----------------|--------------------|
|**Cihaz bilgi noktası modundayken çalışmasına izin verilecek yönetilen bir uygulama seçin**|**Gözat**'a tıklayın, ardından cihaz bilgi noktası modundayken çalışmasına izin verilecek bir yönetilen uygulama veya mağaza uygulaması seçin. Cihazda başka hiçbir uygulamanın çalışmasına izin verilmez.<br /><br />Yardım için, bu konunun Uygulama mağazalarının URL’lerini belirtme bölümüne bakın.|
|**Ses düğmelerine izin ver**|Cihazdaki ses düğmelerinin kullanımını etkinleştirir veya devre dışı bırakır.|
|**Açma/kapatma düğmesine izin ver**|Cihazın açma/kapatma düğmesini etkinleştirir veya devre dışı bırakır.|

### Uyumlu ve uyumlu olmayan uygulamalar için başvuru bilgileri

#### Uyumlu ve uyumsuz uygulamaları izle
 **Uyumlu Olmayan Uygulamalar Raporu** 'nu kullanarak izin verilen ve engellenen uygulamaların uyumluluğunu görüntüleyin.

###### Uyumlu Olmayan Uygulamalar Raporu'nu çalıştırmak için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **Raporlar** &gt; **Uyumsuz Uygulamalar Raporları**’na tıklayın..

2.  Denetlenmesini istediğiniz cihaz gruplarını seçin, uyumlu uygulamaları mı, uyumsuz uygulamaları mı yoksa her ikisini birden mi denetlemek istediğinizi seçin ve ardından **Raporu Görüntüle**'ye tıklayın..

#### Uygulama mağazalarının URL'lerini belirtme
Uyumlu ve uyumsuz uygulamalar listesinde veya **Cihaz bilgi noktası modundayken çalışmasına izin verilecek bir yönetilen uygulama seçin** seçeneğinde (yalnızca iOS) bir uygulamanın URL'sini belirtmek için aşağıdaki biçimi kullanın:

[Google Play'in uygulamalar bölümünde](https://play.google.com/store/apps) kullanmak istediğiniz uygulamayı arayın.

Uygulama için yükleme sayfasını açın ve URL'yi panoya kopyalayın. Artık bunu uyumlu uygulamalar listesinde veya uyumsuz uygulamalar listesinde gerekli URL olarak kullanabilirsiniz.

**Örnek:** Google Play'de Microsoft Office Mobile uygulamasını arayın. Kullandığınız URL **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub** olacaktır..

## Özel ilke ayarları
Android cihazlardaki özellikleri denetlemek için kullanılabilen OMA-URI (Open Mobile Alliance Tekdüzen Kaynak Tanımlayıcısı) ayarlarını dağıtmak için Microsoft Intune **Android özel yapılandırma ilkesini** kullanın. Bunlar, birçok mobil cihaz üreticisinin, cihaz özelliklerini denetlemek için kullandığı standart ayarlardır.

Bu özellik, Intune ilkeleri ile yapılandırılabilir olmayan Android ayarlarını dağıtmanıza olanak sağlamak için tasarlanmıştır. Bu ilkelerle yapılandırabileceğiniz ayarlar hakkında daha fazla bilgi için bkz. [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)..

> [!NOTE]
> Şu anda Android özel ilkeleri yalnızca önceden paylaşılan bir anahtar içeren Android cihazlar için Wi-Fi ayarlarının yapılandırılmasını destekler. Daha fazla bilgi için, bu konunun devamındaki Önceden paylaşılan anahtarla özel bir Wi-Fi profili yapılandırma bölümüne bakın.

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
    |**Veri türü**|Bu OMA-URI ayarını belirteceğiniz tarih türünü seçin. **Dize, Dize (XML), Tarih ve saat, Tamsayı, Kayan nokta** veya **Boole değeri** seçeneklerinden birini belirleyin..|
    |**OMA-URI (büyük küçük harf duyarlı)**|Bir ayar için sağlamak istediğiniz OMA-URI’yi belirtin.|
    |**Değer**|Önceden belirttiğiniz OMA-URI ile ilişkilendirilecek değeri belirtin.|

### Örnek: Önceden paylaşılan anahtar ile özel bir Wi-Fi profili yapılandırma
Intune, Android cihazlar için Wi-Fi profillerini desteklese de bu özellik şu anda yapılandırmaya önceden paylaşılan anahtar eklenmesini desteklemez. Bu örnekte, Android cihazda önceden paylaşılan anahtar ile Wi-Fi profili oluşturan bir Android özel ilkesinin nasıl oluşturulacağını öğreneceksiniz.

#### Önceden paylaşılan anahtar ile Wi-Fi profili oluşturmak için

1.  Kullanıcılarınızın Android için [Intune Şirket Portalı](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)’nın en son sürümünü kullandığından emin olun.

2.  Bir Android özel ilkesi oluşturun ve aşağıdaki ayarları ekleyin:

|Ayar adı|Ayrıntılar|
|----------------|--------------------|
|**Ayar adı**|Ayar için tercih ettiğiniz bir ad belirtin.|
|**Ayar açıklaması**|Ayar için bir açıklama belirtin.|
|**Veri türü**|**Dize (XML)** öğesini seçin..|
|**OMA URI**|Şunu girin: ./Vendor/MSFT/WiFi/Profile/*&lt;Wi-Fi profiliniz&gt;*/Settings|

3.  **Değer** için aşağıdaki XML kodunu kopyalayıp yapıştırın:

    ```
    <!--
    WEP Wifi Profile
                    <Name of wifi profile> = Name of profile 
                    <SSID of wifi profile> = Plain text of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
                    <WEP password> = Password to connect to the network
    -->
    <WLANProfile 
    xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
      <name><Name of wifi profile></name>
      <SSIDConfig>
        <SSID>
          <name><SSID of wifi profile></name>
        </SSID>
      </SSIDConfig>
      <connectionType>ESS</connectionType>
      <MSM>
        <security>
          <authEncryption>
            <authentication>open</authentication>
            <encryption>WEP</encryption>
            <useOneX>false</useOneX>
          </authEncryption>
          <sharedKey>
            <keyType>networkKey</keyType>
            <protected>false</protected>
            <keyMaterial><WEP password></keyMaterial>
          </sharedKey>
          <keyIndex>0</keyIndex>
        </security>
      </MSM>
    </WLANProfile>
    ```

4.  İşiniz bittiğinde ilkeyi kaydedin ve gerekli Android cihazlarına dağıtın. Yeni Wi-Fi profili, cihazdaki bağlantılar listesinde görüntülenir.

### Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO1-->


