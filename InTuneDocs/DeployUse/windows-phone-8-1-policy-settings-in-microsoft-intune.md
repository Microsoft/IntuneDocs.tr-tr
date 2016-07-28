---
title: "Windows Phone 8.1 ilke ayarları | Microsoft Intune"
description: "Intune, Windows Phone 8.1 cihazlarında yapılandırabileceğiniz çeşitli yerleşik genel ayarlar sağlar. Bunlara ek olarak, Intune’da sağlanmayan özel ayarlar oluşturmak için OMA-URI değerleri belirtebilirsiniz."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 83f7469c-272e-43f2-8139-b0d7bc34f43f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: e11ca62eb242d7c530e8de2ad1e885315d220233


---

# Microsoft Intune’da Windows Phone 8.1 ilke ayarları

Intune, Windows Phone 8.1 cihazlarında yapılandırabileceğiniz çeşitli yerleşik genel ayarlar sağlar. Bunlara ek olarak, Intune’da sağlanmayan özel ayarlar oluşturmak için OMA-URI değerleri belirtebilirsiniz.

## Genel yapılandırma ayarları

Windows Phone 8.1 cihazlarında aşağıdaki ayarları yapılandırmak için Microsoft Intune **Windows Phone genel yapılandırma ilkesini (Windows Phone 8.1 ve üstü)** kullanın:

-   **Mobil cihaz güvenliği ayarları** – Cihazda bir dizi özelliği ve işlevi denetlemenize olanak tanıyan önceden tanımlı ayarlar listesinden seçim yapın.

-   **Uyumlu ve uyumsuz uygulamalar** - Şirketinizdeki uyumlu veya uyumsuz uygulamaların listesini gösterir. Windows Phone cihazları, bu uygulamaların yüklenmesini engelleyebilir veya bu uygulamaların yüklenmesine izin verebilir.

### Uygulanabilirlik ayarları

|Ayar adı|Ayrıntılar|
|----------------|----------------------------------|
|**Tüm yapılandırmaları Windows 10'a uygula**|Bu ilkedeki ayarların Windows Phone 8.1 cihazlarına ek olarak Windows 10 Mobile cihazlarına da uygulanmasına izin verir.|

### Parola ayarları

|Ayar adı|Ayrıntılar|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Mobil cihazların kilidini açmak için bir parola gerektir**|Kullanıcıların cihazlarına erişmek için parola girmelerinin gerekip gerekmediğini belirtir.|Evet|Evet|
|**Gerekli parola türü**|Gerekli parola türünü belirtir (yalnızca sayısal veya alfasayısal gibi).|Evet|Evet|
|**Gerekli parola türü – Minimum karakter kümesi sayısı**|Küçük harfler, büyük harfler, rakamlar ve semboller şeklinde dört karakter kümesi vardır. Bu ayar parolanın kaç farklı karakter kümesi içermesi gerektiğini belirtir). Ancak iOS cihazları için bu ayar, parolanın içermesi gereken sembol karakterlerinin sayısını belirtir)|Evet|Evet|
|**Minimum parola uzunluğu**|Parolada bulunması gereken minimum karakter sayısını belirtir.|Evet|Evet|
|**Basit parolalara izin ver**|Basit parolalar '0000' ve '1234' şeklindedir|Evet|Evet|
|**Cihaz temizlenmeden önce izin verilen yinelenen oturum açma hatası sayısı**|Aygıt temizlenmeden önce kullanıcının girdiği hatalı parolanın kaç kez anımsanabileceğini belirtir.|Evet|Evet|
|**Ekran kapanmadan önce geçen işlem yapılmayan dakika sayısı**|Ekran otomatik olarak kilitlenmeden önce cihazın boşta bekleyeceği süreyi belirtir.|Evet|Evet|
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
|**Tanılama verilerinin gönderimine izin ver**|Cihazın Microsoft’a tanılama bilgileri göndermesine izin verir.|Hayır|Evet|

### Bulut ayarları – hesaplar ve eşitleme

|Ayar adı|Ayrıntılar|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Microsoft Hesabına izin ver**|Microsoft hesabının cihazla ilişkilendirilmesine izin verir.|Hayır|Evet|

### E-posta ayarları

|Ayar adı|Ayrıntılar|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Özel e-posta hesaplarına izin ver**|Cihazın Microsoft olmayan e-posta hesaplarına bağlanmasına izin verin.|Hayır|Evet|

### Uygulama ayarları - tarayıcı

|Ayar adı|Ayrıntılar|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Web tarayıcısına izin ver**|Cihazlarda yerleşik web tarayıcısına izin verir veya bunu engeller.|Hayır|Evet|

### Uygulama ayarları - uygulamalar

|Ayar adı|Ayrıntılar|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Uygulama mağazasına izin ver**|Kullanıcıların cihazdan uygulama mağazasına bağlanmasına olanak tanır.|Hayır|Evet|

### Cihaz özellikleri ayarları - donanım

|Ayar adı|Ayrıntılar|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Kameraya izin ver**|Cihaz kamerasına izin verin veya kamerayı engelleyin.|Hayır|Evet|
|**Çıkarılabilir depolama birimine izin ver**|Cihazın SD kartı gibi çıkarılabilir bir depolamayı kullanmasına olanak tanır.|Evet|Evet|
|**Wi-Fi'a izin ver**|Cihazda Wi-Fi işlevselliğini etkinleştirir veya devre dışı bırakır.|Hayır|Evet|
|**Wi-Fi İnternet paylaşımına izin ver**|Cihazda Wi-Fi internet paylaşımı kullanımına izin verin.|Hayır|Evet
|**Ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmaya izin ver**|Cihazın ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmasına ve tüm kullanım koşullarını otomatik olarak kabul etmesine izin verin.|Hayır|Evet|
|**Wi-Fi etkin noktası bildirimine izin ver**|Yakındaki bağlantıların keşfedilmesine yardımcı olmak için Wi-Fi bağlantıları hakkında bilgi gönderin.|Hayır|Evet|
|**Coğrafi konuma izin ver**|Cihazın konum bilgilerini kullanmasına izin verir.|Hayır|Evet|
|**NFC'ye izin ver**|Yakın alan iletişimi kullanan işlemlere izin verir.|Hayır|Evet|
|**Bluetooth'a izin ver**|Cihazda Bluetooth işlevselliğini etkinleştirir veya devre dışı bırakır.|Hayır|Evet|

### Cihaz özellikleri ayarları - özellikler

|Ayar adı|Ayrıntılar|Windows Phone 8|Windows Phone 8.1|
|----------------|-----------------------------------------|
|**Kopyalama ve yapıştırmaya izin ver**|Cihazda kopyalama ve yapıştırma işlevine izin verin.|Hayır|Evet|

### Uyumlu ve uyumlu olmayan uygulamalar için ayarlar
**Uyumlu &amp; Uyumsuz Uygulamalar** listesinde, aşağıdaki bilgileri kullanarak uyumlu veya uyumsuz uygulamalar listesini belirtin:

> [!NOTE]
> Tek bir ilke, yalnızca uyumlu uygulamaların veya uyumsuz uygulamaların listesini içerebilir. İkisi de aynı ilkede belirtemezsiniz.

|Ayar adı|Ayrıntılar|
|----------------|--------------------|
|**Cihazların listelenen uygulamaları açmasını engelle**|Kullanıcıların yüklemesine ve çalıştırmasına için izin verilmeyen, Intune tarafından yönetilmeyen uygulamaları listeler.|
|**Cihazların yalnızca listelenen uygulamaları yüklemesine izin ver**|Kullanıcıların yüklemesine izin verilen uygulamaları listeler. Kullanıcılar, başka hiçbir uygulama yükleyemez. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir.|
|**Ekle**|Seçili listeye bir uygulama ekler. Tercih ettiğiniz bir ad (isteğe bağlı olarak uygulama yayımcısı) ve uygulamanın uygulama mağazasındaki URL'sini belirtin. Daha fazla yardım için, bu konunun Uygulama mağazalarının URL’lerini belirtme bölümüne bakın.
|**Uygulamaları İçeri Aktar**|Virgülle ayrılmış bir değerler dosyasında belirttiğiniz uygulamaların listesini içeri aktarır. Dosyadaki biçim, uygulama adı, yayımcı, uygulama URL'sini kullanın.|
|**Düzenle**|Seçilen uygulamanın adını, yayımcısını ve URL'sini düzenlemenize imkan tanır.|
|**Sil**|Seçilen uygulamayı listeden siler.|
> [!IMPORTANT]
> Windows Phone 8.1 cihazları için izin verilen uygulamaların bir listesini belirtirseniz, Şirket Portalı uygulamasını bu listeye ekleyin, aksi takdirde engellenir.


### Uyumlu ve uyumlu olmayan uygulamalar için başvuru bilgileri

#### Uygulama mağazalarının URL'lerini belirtme
Uyumlu veya uyumlu olmayan uygulama listesinde bir uygulama URL'si belirtmek için aşağıdaki biçimi kullanın:

 [Windows Phone Uygulamaları + Oyunlar sayfasından](http://www.windowsphone.com/en-us/store/overview) , kullanmak istediğiniz uygulamayı arayın.

Uygulamanın sayfasını açın ve URL'yi panoya kopyalayın. Artık bunu uyumlu uygulamalar listesinde veya uyumsuz uygulamalar listesinde gerekli URL olarak kullanabilirsiniz.

**Örnek:** Mağazada Skype uygulamasını arayın. Kullandığınız URL **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51** olacaktır.

## Özel ilke ayarları 
**Windows 8.1 cihazlarındaki** özellikleri denetlerken kullanılabilen OMA-URI (Open Mobile Alliance Tekdüzen Kaynak Tanımlayıcısı) ayarlarını dağıtmak için Microsoft Intune **Windows Phone özel yapılandırma ilkesini** kullanın. Bunlar, birçok mobil cihaz üreticisinin, cihaz özelliklerini denetlemek için kullandığı standart ayarlardır.

Bu özellik, Intune genel yapılandırma ilkesiyle, yapılandırılabilir olmayan Windows Phone ayarlarını dağıtmanıza olanak sağlamak için tasarlanmıştır. Bu ilkelerle yapılandırabileceğiniz ayarlar hakkında daha fazla bilgi için bkz. [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

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
    |**Veri türü**|Bu OMA-URI ayarını belirteceğiniz tarih türünü seçin. Aşağıdakilerden birini seçin:<br /><br />-   **Dize**<br />-   **Dize (XML)**<br />-   **Tarih ve saat**<br />-   **Tamsayı**<br />-   **Kayan nokta**<br />-   **Boole değeri**|
    |**OMA-URI (Büyük Küçük Harf Duyarlı)**|Bir ayar için sağlamak istediğiniz OMA-URI’yi belirtin.|
    |**Değer**|Önceden belirttiğiniz OMA-URI ile ilişkilendirilecek değeri belirtin.|

### Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Jul16_HO3-->


