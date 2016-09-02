---
title: "Windows Phone 8.1 ilke ayarları | Microsoft Intune"
description: "Intune, Windows Phone 8.1 cihazlarında yapılandırabileceğiniz çeşitli yerleşik genel ayarlar sağlar. Bunlara ek olarak, Intune’da sağlanmayan özel ayarlar oluşturmak için OMA-URI değerleri belirtebilirsiniz."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 83f7469c-272e-43f2-8139-b0d7bc34f43f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4279ecd098ddaa6d6eb239ee71f9c3f7d450ab3f
ms.openlocfilehash: f2ccc52ceae6bbb63ea76ff4391922099c69f4dd


---

# Microsoft Intune’da Windows Phone 8.1 ilke ayarları

Intune, Windows Phone 8.1 cihazlarında yapılandırabileceğiniz çeşitli yerleşik genel ayarlar sağlar. Buna ek olarak, Intune’da bulunmayan özel ayarlar oluşturmak için Açık Mobil Ortaklığı Tekdüzen Kaynak Tanımlayıcısı (OMA-URI) değerleri belirtebilirsiniz.

## Genel yapılandırma ayarları

Windows Phone 8.1 cihazlarında aşağıdaki ayarları yapılandırmak için Microsoft Intune **Windows Phone genel yapılandırma ilkesini (Windows Phone 8.1 ve üstü)** kullanın:

-   **Mobil cihaz güvenliği ayarları** – Cihazda bir dizi özelliği ve işlevi denetlemenize olanak tanıyan önceden tanımlı ayarlar listesinden seçim yapın.

-   **Uyumlu ve uyumsuz uygulamalar** - Şirketinizdeki uyumlu veya uyumsuz olan uygulamaların listesini belirtin. Windows Phone cihazları, bu uygulamaların yüklenmesini engelleyebilir veya yüklenmesine izin verebilir.

### Uygulanabilirlik ayarları

|Ayar adı|Ayrıntılar|
|----------------|----------------------------------|
|**Tüm yapılandırmaları Windows 10'a uygula**|Bu ilkedeki ayarların Windows Phone 8.1 cihazlarına ek olarak Windows 10 Mobile cihazlarına da uygulanmasını etkinleştirir.|

### Parola ayarları

|Ayar adı|Ayrıntılar|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Mobil cihazların kilidini açmak için bir parola gerektir**|Kullanıcıların cihazlarına erişmek için parola girmelerinin gerekip gerekmediğini belirtir.|Evet|Evet|
|**Gerekli parola türü**|Gerekli parola türünü belirtir (alfasayısal veya yalnızca sayısal gibi).|Evet|Evet|
|**Gerekli parola türü – Minimum karakter kümesi sayısı**|Parolanın kaç farklı karakter kümesi içermesi gerektiğini belirtir. Dört karakter kümesi vardır: küçük harfler, büyük harfler, rakamlar ve simgeler. Bununla birlikte, iOS cihazları için bu ayar, parolanın içermesi gereken simgelerin sayısını belirtir.|Evet|Evet|
|**Minimum parola uzunluğu**|Parolada bulunması gereken minimum karakter sayısını belirtir.|Evet|Evet|
|**Basit parolalara izin ver**|‘0000’ ve ‘1234’ gibi basit karakterlerin kullanılabileceğini belirtir.|Evet|Evet|
|**Cihaz temizlenmeden önce izin verilen yinelenen oturum açma hatası sayısı**|Aygıt temizlenmeden önce kullanıcının girdiği hatalı parolanın kaç kez girilebileceğini belirtir.|Evet|Evet|
|**Ekran kapanmadan önce işlem yapılmadan geçen dakika sayısı**|Ekran otomatik olarak kilitlenmeden önce cihazın boşta bekleyeceği süreyi belirtir.|Evet|Evet|
|**Parola geçerlilik süresi (gün)**|Cihaz parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını belirtir.|Evet|Evet|
|**Parola geçmişini anımsa**|Kullanıcıların daha önce kullanılmış olan parolaları yeniden kullanmasını önlemek için önceden kullanılmış parolaların anımsanıp anımsanmayacağını belirtir.|Evet|Evet|
|**Parola geçmişini anımsa** – **Önceki parolaların tekrar kullanılmasını engeller**|Önceden kullanılmış olan kaç parolanın anımsanacağını belirtir.|Evet|Evet|

### Şifreleme ayarları

|Ayar adı|Ayrıntılar|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Cihazda şifrelemeyi gerektir**|Desteklenen mobil cihazlarda verilerin şifrelenmesini zorunlu tutar.<br>Windows Phone 8 cihazları için bunu **Evet**olarak ayarlamanız gerekir.|Evet|Evet|

### Sistem ayarları

|Ayar adı|Ayrıntılar|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Ekran yakalamaya izin ver**|Kullanıcının ekran içeriğini bir resim dosyası olarak yakalamasına olanak tanır.|Hayır|Evet|
|**Tanılama verilerinin gönderimine izin ver**|Cihazın Microsoft’a tanılama bilgileri göndermesini etkinleştirir.|Hayır|Evet|

### Bulut ayarları – hesaplar ve eşitleme

|Ayar adı|Ayrıntılar|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Microsoft Hesabına izin ver**|Microsoft hesabının cihazla ilişkilendirilmesine olanak tanır.|Hayır|Evet|

### E-posta ayarları

|Ayar adı|Ayrıntılar|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Özel e-posta hesaplarına izin ver**|Cihazın Microsoft olmayan e-posta hesaplarına bağlanmasına olanak tanır.|Hayır|Evet|

### Uygulama ayarları - tarayıcı

|Ayar adı|Ayrıntılar|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Web tarayıcısına izin ver**|Cihazlarda yerleşik web tarayıcısını etkinleştirir veya engeller.|Hayır|Evet|

### Uygulama ayarları - uygulamalar

|Ayar adı|Ayrıntılar|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Uygulama mağazasına izin ver**|Kullanıcıların cihazdan uygulama mağazasına bağlanmasına olanak tanır.|Hayır|Evet|

### Cihaz özellikleri ayarları - donanım

|Ayar adı|Ayrıntılar|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Kameraya izin ver**|Cihazın kamerasını etkinleştirir veya engeller.|Hayır|Evet|
|**Çıkarılabilir depolama birimine izin ver**|Cihazın SD kartları gibi çıkarılabilir depolama birimi kullanmasına olanak tanır.|Evet|Evet|
|**Wi-Fi'a izin ver**|Cihazda Wi-Fi işlevselliğini etkinleştirir veya devre dışı bırakır.|Hayır|Evet|
|**Wi-Fi İnternet paylaşımına izin ver**|Cihazda Wi-Fi internet paylaşımı kullanımını etkinleştirir.|Hayır|Evet
|**Ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmaya izin ver**|Cihazın ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmasına ve tüm kullanım koşullarını otomatik olarak kabul etmesine olanak tanır.|Hayır|Evet|
|**Wi-Fi etkin noktası bildirimine izin ver**|Kullanıcının yakındaki bağlantıların keşfetmesine yardımcı olmak için Wi-Fi bağlantıları hakkında bilgi gönderir.|Hayır|Evet|
|**Coğrafi konuma izin ver**|Cihazın konum bilgilerini kullanmasına olanak tanır.|Hayır|Evet|
|**NFC'ye izin ver**|Yakın alan iletişimi kullanan işlemleri etkinleştirir.|Hayır|Evet|
|**Bluetooth'a izin ver**|Cihazda Bluetooth işlevselliğini etkinleştirir veya devre dışı bırakır.|Hayır|Evet|

### Cihaz özellikleri ayarları - özellikler

|Ayar adı|Ayrıntılar|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Kopyalama ve yapıştırmaya izin ver**|Cihazda kopyalama ve yapıştırma işlevlerini etkinleştirir.|Hayır|Evet|

### İzin verilen ve engellenen uygulamalar için ayarlar
**İzin verilen ve engellenen uygulamalar** listesinde, aşağıdaki bilgileri kullanarak izin vermek ya da engellemek istediğiniz uygulamaların listesini belirtin:

> [!NOTE]
> Tek bir ilke yalnızca izin verilen uygulamaların veya engellenen uygulamaların listesini içerebilir. İkisi de aynı ilkede belirtemezsiniz.

|Ayar adı|Ayrıntılar|
|----------------|--------------------|
|**Cihazların listelenen uygulamaları açmasını engelle**|Kullanıcıların yüklemesine ve çalıştırmasına izin verilmeyen, Intune tarafından yönetilmeyen uygulamaları listeler.|
|**Cihazların yalnızca listelenen uygulamaları yüklemesine izin ver**|Kullanıcıların yüklemesine izin verilen uygulamaları listeler. Kullanıcılar, başka hiçbir uygulama yükleyemez. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir.|
|**Ekle**|Seçili listeye bir uygulama ekler. Tercih ettiğiniz adı, uygulamanın uygulama mağazasındaki URL'sini ve uygulama yayımcısını (isteğe bağlı) belirtin. Daha fazla yardım için, bu konunun Uygulama mağazalarının URL’lerini belirtme bölümüne bakın.
|**Uygulamaları İçeri Aktar**|Belirttiğiniz uygulamaların virgülle ayrılmış bir listesini içeri aktarır. Dosyadaki biçimi, uygulama adını, yayımcıyı ve uygulama URL'sini kullanın.|
|**Düzenle**|Seçilen uygulamanın adını, yayımcısını ve URL'sini düzenlemenize izin verir.|
|**Sil**|Seçilen uygulamayı listeden siler.|
> [!IMPORTANT]
> Windows Phone 8.1 cihazları için izin verilen uygulamalar listesini belirtirseniz, Şirket Portalı uygulamasını bu listeye eklemelisiniz; eklemezseniz uygulama engellenir.


### İzin verilen ve engellenen uygulamalar için başvuru bilgileri

#### Uygulama mağazalarının URL'lerini belirtme
İzin verilen veya engellenen uygulamalar listesinde bir uygulama URL'si belirtmek için aşağıdaki biçimi kullanın:

[Windows Phone Uygulamaları + Oyunlar](http://www.windowsphone.com/en-us/store/overview) sayfasında, kullanmak istediğiniz uygulamayı arayın.

Uygulamanın sayfasını açın ve URL'yi panoya kopyalayın. Artık bunu izin verilen veya engellenen uygulamalar listesinde URL olarak kullanabilirsiniz.

**Örnek:** Mağazada Skype uygulamasını arayın. Kullandığınız URL **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51** olacaktır.

## Özel ilke ayarları
**Windows Phone 8.1 cihazlardaki** özellikleri denetlemek için kullanılabilen OMA-URI ayarlarını dağıtmak için Microsoft Intune **Windows Phone özel yapılandırma ilkesini** kullanın. Bunlar, birçok mobil cihaz üreticisinin, cihaz özelliklerini denetlemek için kullandığı standart ayarlardır.

Bu özellik, Intune genel yapılandırma ilkesiyle, yapılandırılabilir olmayan Windows Phone ayarlarını dağıtmanıza olanak sağlar. Bu ilkelerle yapılandırabileceğiniz ayarlar hakkında daha fazla bilgi için bkz. [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

Windows Phone cihazlar için OMA-URI ayarlarını oluşturmanıza yardımcı olması için bkz. [Windows Phone 8.1 MDM protokolü belgeleri](http://technet.microsoft.com/library/dn499787.aspx).

### Genel ayarlar

|Ayar adı|Ayrıntılar|
|----------------|--------------------|
|**Ad**|Intune konsolunda tanımanıza yardımcı olması için benzersiz bir ad girin.|
|**Açıklama**|İlkeye genel bir bakış ve ilkeyi bulmanıza yardımcı olacak diğer ek bilgileri içeren bir açıklama sağlayın.|

### OMA-URI ayarları

**OMA-URI Ayarları** bölümünde ayar eklemek için **Ekle**’ye tıklayın. Ayrıca varolan bir ayarı düzenleyebilir veya silebilirsiniz.

**OMA-URI Ayarı Ekle veya Düzenle** iletişim kutusunda aşağıdaki bilgileri belirtin:

|Ayar adı|Ayrıntılar|
    |--------|--------------------|
    |**Ayar adı**|Ayarlar listesinde tanımanıza yardımcı olması için OMA-URI ayarı için benzersiz bir ad girin.|
    |**Ayar açıklaması**|Ayara genel bir bakış ve ayarı bulmanıza yardımcı olacak diğer ek bilgileri içeren bir açıklama sağlayın.|
    |**Veri türü**|Bu OMA-URI ayarını belirteceğiniz veri türünü seçin. Aşağıdakilerden birini seçin:<br /><br />-   **Dize**<br />-   **Dize (XML)**<br />-   **Tarih ve saat**<br />-   **Tamsayı**<br />-   **Kayan nokta**<br />-   **Boole değeri**|
    |**OMA-URI (büyük küçük harf duyarlı)**|Bir ayar sağlamak istediğiniz OMA-URI’yi belirtin.|
    |**Değer**|Önceden belirttiğiniz OMA-URI ile ilişkilendirilecek değeri belirtin.|

### Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Aug16_HO3-->


