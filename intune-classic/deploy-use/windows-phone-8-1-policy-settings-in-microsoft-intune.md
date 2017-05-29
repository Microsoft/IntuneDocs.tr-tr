---
title: "Windows Phone 8.1 ilke ayarları | Microsoft Docs"
description: "Intune, Windows Phone 8.1 cihazlarında yapılandırabileceğiniz çeşitli yerleşik genel ayarlar sağlar. Bunlara ek olarak, Intune’da sağlanmayan özel ayarlar oluşturmak için OMA-URI değerleri belirtebilirsiniz."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 83f7469c-272e-43f2-8139-b0d7bc34f43f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 65d3b454531084008bdbb01dd17f5ce34ef5890f
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="windows-phone-81-policy-settings-in-microsoft-intune"></a>Microsoft Intune’da Windows Phone 8.1 ilke ayarları

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune, Windows Phone 8.1 cihazlarında yapılandırabileceğiniz çeşitli yerleşik genel ayarlar sağlar. Buna ek olarak, Intune’da bulunmayan özel ayarlar oluşturmak için Açık Mobil Ortaklığı Tekdüzen Kaynak Tanımlayıcısı (OMA-URI) değerleri belirtebilirsiniz.

## <a name="general-configuration-settings"></a>Genel yapılandırma ayarları

Windows Phone 8.1 cihazlarında aşağıdaki ayarları yapılandırmak için Microsoft Intune **Windows Phone genel yapılandırma ilkesini (Windows Phone 8.1 ve üstü)** kullanın:

-   **Mobil cihaz güvenliği ayarları** – Cihazda bir dizi özelliği ve işlevi denetlemenize olanak tanıyan önceden tanımlı ayarlar listesinden seçim yapın.

-   **Uyumlu ve uyumsuz uygulamalar** - Şirketinizdeki uyumlu veya uyumsuz olan uygulamaların listesini belirtin. Windows Phone cihazları, bu uygulamaların yüklenmesini engelleyebilir veya yüklenmesine izin verebilir.

### <a name="applicability-settings"></a>Uygulanabilirlik ayarları

|Ayar adı|Ayrıntılar|
|----------------|----------------------------------|
|**Tüm yapılandırmaları Windows 10'a uygula**|Bu ilkedeki ayarların Windows Phone 8.1 cihazlarına ek olarak Windows 10 Mobile cihazlarına da uygulanmasını etkinleştirir.|

### <a name="password-settings"></a>Parola ayarları

|Ayar adı|Ayrıntılar|
|----------------|------|
|**Mobil cihazların kilidini açmak için bir parola iste**|Kullanıcıların cihazlarına erişmek için parola girmelerinin gerekip gerekmediğini belirtir.|
|**Gerekli parola türü**|Gerekli parola türünü belirtir (alfasayısal veya yalnızca sayısal gibi).|
|**Gerekli parola türü – Minimum karakter kümesi sayısı**|Parolanın kaç farklı karakter kümesi içermesi gerektiğini belirtir. Dört karakter kümesi vardır: küçük harfler, büyük harfler, rakamlar ve simgeler. Bununla birlikte, iOS cihazları için bu ayar, parolanın içermesi gereken simgelerin sayısını belirtir.|
|**En düşük parola uzunluğu**|Parolada bulunması gereken minimum karakter sayısını belirtir.|
|**Basit parolalara izin ver**|‘0000’ ve ‘1234’ gibi basit karakterlerin kullanılabileceğini belirtir.|
|**Cihaz silinmeden önce izin verilen yinelenen oturum açma hatası sayısı**|Aygıt temizlenmeden önce kullanıcının girdiği hatalı parolanın kaç kez girilebileceğini belirtir.|
|**Ekran kapanmadan önce işlem yapılmadan geçen dakika sayısı**|Ekran otomatik olarak kilitlenmeden önce cihazın boşta bekleyeceği süreyi belirtir.|
|**Parola kullanım süresi (gün)**|Cihaz parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını belirtir.|Evet|Evet|
|**Parola geçmişini anımsa**|Kullanıcıların daha önce kullanılmış olan parolaları yeniden kullanmasını önlemek için önceden kullanılmış parolaların anımsanıp anımsanmayacağını belirtir.|
|**Parola geçmişini anımsa** – **Önceki parolaların tekrar kullanılmasını engeller**|Önceden kullanılmış olan kaç parolanın anımsanacağını belirtir.|

### <a name="encryption-settings"></a>Şifreleme ayarları

|Ayar adı|Ayrıntılar|
|----------------|------|
|**Cihazda şifrelemeyi gerektir**|Desteklenen mobil cihazlarda verilerin şifrelenmesini zorunlu tutar.|

### <a name="system-settings"></a>Sistem ayarları

|Ayar adı|Ayrıntılar|
|----------------|-----|
|**Ekran yakalamaya izin ver**|Kullanıcının ekran içeriğini bir resim dosyası olarak yakalamasına olanak tanır.|
|**Tanılama verilerinin gönderimine izin ver**|Cihazın Microsoft’a tanılama bilgileri göndermesini etkinleştirir.|

### <a name="cloud-settings--accounts-and-synchronization"></a>Bulut ayarları – hesaplar ve eşitleme

|Ayar adı|Ayrıntılar|
|----------------|------|
|**Microsoft hesabına izin ver**|Microsoft hesabının cihazla ilişkilendirilmesine olanak tanır.|

### <a name="email-settings"></a>E-posta ayarları

|Ayar adı|Ayrıntılar|
|----------------|-----|
|**Özel e-posta hesaplarına izin ver**|Cihazın Microsoft olmayan e-posta hesaplarına bağlanmasına olanak tanır.|

### <a name="application-settings---browser"></a>Uygulama ayarları - tarayıcı

|Ayar adı|Ayrıntılar|
|----------------|-----|
|**Web tarayıcısına izin ver**|Cihazlarda yerleşik web tarayıcısını etkinleştirir veya engeller.|

### <a name="application-settings---apps"></a>Uygulama ayarları - uygulamalar

|Ayar adı|Ayrıntılar|
|----------------|-----|
|**Uygulama depolamaya izin ver**|Kullanıcıların cihazdan uygulama mağazasına bağlanmasına olanak tanır.|

### <a name="device-capabilities-settings---hardware"></a>Cihaz özellikleri ayarları - donanım

|Ayar adı|Ayrıntılar|
|----------------|-----|
|**Kameraya izin ver**|Cihazın kamerasını etkinleştirir veya engeller.|
|**Çıkarılabilir depolamaya izin ver**|Cihazın SD kartları gibi çıkarılabilir depolama birimi kullanmasına olanak tanır.|
|**Wi-Fi bağlantısına izin ver**|Cihazda Wi-Fi işlevselliğini etkinleştirir veya devre dışı bırakır.|
|**Wi-Fi İnternet paylaşımına izin ver**|Cihazda Wi-Fi internet paylaşımı kullanımını etkinleştirir.|
|**Ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmaya izin ver**|Cihazın ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmasına ve tüm kullanım koşullarını otomatik olarak kabul etmesine olanak tanır.|
|**Wi-Fi etkin noktası raporlamasına izin ver**|Kullanıcının yakındaki bağlantıların keşfetmesine yardımcı olmak için Wi-Fi bağlantıları hakkında bilgi gönderir.|
|**Coğrafi konuma izin ver**|Cihazın konum bilgilerini kullanmasına olanak tanır.|
|**NFC'ye izin ver**|Yakın alan iletişimi kullanan işlemleri etkinleştirir.|
|**Bluetooth'a izin ver**|Cihazda Bluetooth işlevselliğini etkinleştirir veya devre dışı bırakır.|

### <a name="device-capabilities-settings---features"></a>Cihaz özellikleri ayarları - özellikler

|Ayar adı|Ayrıntılar|
|----------------|----|
|**Kopyalama ve yapıştırmaya izin ver**|Cihazda kopyalama ve yapıştırma işlevlerini etkinleştirir.|

### <a name="settings-for-allowed-and-blocked-apps"></a>İzin verilen ve engellenen uygulamalar için ayarlar
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


### <a name="reference-information-for-allowed-and-blocked-apps"></a>İzin verilen ve engellenen uygulamalar için başvuru bilgileri

#### <a name="how-to-specify-urls-to-app-stores"></a>Uygulama mağazalarının URL'lerini belirtme
İzin verilen veya engellenen uygulamalar listesinde bir uygulama URL'si belirtmek için aşağıdaki biçimi kullanın:

[Windows Phone Uygulamaları + Oyunlar](http://www.windowsphone.com/store/overview) sayfasında, kullanmak istediğiniz uygulamayı arayın.

Uygulamanın sayfasını açın ve URL'yi panoya kopyalayın. Artık bunu izin verilen veya engellenen uygulamalar listesinde URL olarak kullanabilirsiniz.

**Örnek:** Mağazada Skype uygulamasını arayın. Kullandığınız URL **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51** olacaktır.

## <a name="custom-policy-settings"></a>Özel ilke ayarları
**Windows Phone 8.1 cihazlardaki** özellikleri denetlemek için kullanılabilen OMA-URI ayarlarını dağıtmak için Microsoft Intune **Windows Phone özel yapılandırma ilkesini** kullanın. Bunlar, birçok mobil cihaz üreticisinin, cihaz özelliklerini denetlemek için kullandığı standart ayarlardır.

Bu özellik, Intune genel yapılandırma ilkesiyle, yapılandırılabilir olmayan Windows Phone ayarlarını dağıtmanıza olanak sağlar. Bu ilkelerle yapılandırabileceğiniz ayarlar hakkında daha fazla bilgi için bkz. [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

Windows Phone cihazlar için OMA-URI ayarlarını oluşturmanıza yardımcı olması için bkz. [Windows Phone 8.1 MDM protokolü belgeleri](http://technet.microsoft.com/library/dn499787.aspx).

### <a name="general-settings"></a>Genel ayarlar

|Ayar adı|Ayrıntılar|
|----------------|--------------------|
|**Ad**|Intune konsolunda tanımanıza yardımcı olması için benzersiz bir ad girin.|
|**Açıklama**|İlkeye genel bir bakış ve ilkeyi bulmanıza yardımcı olacak diğer ek bilgileri içeren bir açıklama sağlayın.|

### <a name="oma-uri-settings"></a>OMA-URI ayarları

**OMA-URI Ayarları** bölümünde ayar eklemek için **Ekle**’ye tıklayın. Ayrıca varolan bir ayarı düzenleyebilir veya silebilirsiniz.

**OMA-URI Ayarı Ekle veya Düzenle** iletişim kutusunda aşağıdaki bilgileri belirtin:

|Ayar adı|Ayrıntılar|
    |--------|--------------------|
    |**Ayar Adı**|Ayarlar listesinde tanımanıza yardımcı olması için OMA-URI ayarı için benzersiz bir ad girin.|
    |**Ayar açıklaması**|Ayara genel bir bakış ve ayarı bulmanıza yardımcı olacak diğer ek bilgileri içeren bir açıklama sağlayın.|
    |**Veri türü**|Bu OMA-URI ayarını belirteceğiniz veri türünü seçin. Aşağıdakilerden birini seçin:<br /><br />-   **Dize**<br />-   **Dize (XML)**<br />-   **Tarih ve saat**<br />-   **Tamsayı**<br />-   **Kayan nokta**<br />-   **Boole**|
    |**OMA-URI (büyük küçük harfe duyarlı)**|Bir ayar sağlamak istediğiniz OMA-URI’yi belirtin.|
    |**Değer**|Önceden belirttiğiniz OMA-URI ile ilişkilendirilecek değeri belirtin.|

### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

