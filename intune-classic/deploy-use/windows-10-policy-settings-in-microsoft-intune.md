---
title: "Windows 10 ilke ayarları | Microsoft Docs"
description: "Kayıtlı Windows 10 masaüstü bilgisayarları ve Windows 10 mobil cihazlarında yerleşik ve özel ayarları yapılandırmanıza yardımcı olması için, bu konu başlığı altında listelenen ilke ayarlarını kullanın."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/03/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: dd81102eb768ab8ad5f9ee1d2f122f15a8e17b89
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="intune-policy-settings-for-windows-10-devices-in-microsoft-intune"></a>Microsoft Intune’daki Windows 10 cihazları için Intune ilke ayarları

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bu konu, Windows 10 cihazlarını yönetmek için kullanabileceğiniz Intune ilke ayarlarını anlamanıza yardımcı olacak bilgiler içermektedir. Bu konunun yanında [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](/intune-classic/get-started/windows-pc-management-capabilities-in-microsoft-intune) makalesindeki yordamları okuyun.

İki ilke türünden birini seçebilirsiniz:

- **Özel ilke**: Cihazlardaki özellikleri denetlemek için kullanılabilecek OMA-URI (Open Mobile Alliance Uniform Resource Identifier) ayarları dağıtmak üzere Windows 10 ve Windows 10 Mobile için Microsoft Intune **özel ilkesini** kullanın. Windows 10, örneğin [İlke Yapılandırma Hizmet Sağlayıcısı (İlke CSP’si)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) aracılığıyla pek çok CSP ayarını kullanıma sunar.
- **Genel yapılandırma ilkesi**: Microsoft Intune ile sağlanan yerleşik listeden ayar seçmek istediğinizde bu ilke türünü kullanın.

## <a name="custom-policy-settings"></a>Özel ilke ayarları

Özel bir ilkede aşağıdaki ayarları sağlayın.

### <a name="general-settings"></a>Genel ayarlar

Intune konsolunda tanımanıza yardımcı olması için bu ilke için bir ad ve isterseniz bir açıklama girin.

### <a name="oma-uri-settings"></a>OMA-URI ayarları

Eklemek istediğiniz her OMA-URI ayarı için aşağıdaki bilgileri girin. Kullanabileceğiniz ayarlar hakkında bilgi edinmek için bu konuda bulunan [Windows 10 URI ayarları başvurusunu](/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune#Windows-10-URI-settings) kullanın:

- **Ayar adı**: Ayar listesinde tanımanıza yardımcı olması için OMA-URI ayarı için benzersiz bir ad girin.
- **Ayar açıklaması**: İsterseniz ayar için bir açıklama girin.
- **Veri türü**: Aşağıdaki veri türleri arasından seçim yapın:
    - **Dize**
    - **Dize (XML)**
    - **Tarih ve saat**
    - **Tamsayı**
    - **Kayan nokta**
    - **Boole değeri**
- **OMA-URI (büyük/küçük harfe duyarlı)**: Bir ayarını girmek istediğiniz OMA-URI’yi belirtin.
- **Değer**: Girdiğiniz OMA-URI ile ilişkilendirilecek değeri belirtin.

### <a name="example"></a>Örnek
Aşağıdaki ekran görüntüsünde **Connectivity/AllowVPNOverCellular** ayarı etkinleştirilmiştir. Bu değer, bir Windows 10 cihazının hücresel bir ağdayken VPN bağlantısı açmasına izin verir.

> ![VPN ayarları içeren özel bir ilke örneği](./media/custom-policy-example.png)

### <a name="how-to-find-the-policies-you-can-configure"></a>Yapılandırabileceğiniz ilkeleri bulma

Windows belge kitaplığındaki [Yapılandırma hizmet sağlayıcısı başvurusu](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) konusunda, Windows 10’un desteklediği tüm yapılandırma hizmet sağlayıcılarının (CSP) tam listesini bulabilirsiniz.

Tüm ayarlar, Windows 10 sürümlerinin tümüyle uyumlu değildir. Windows başlıklı tabloda, her CSP için hangi sürümlerin desteklendiğini gösterir.

Buna ek olarak, Intune konu başlığı altında listelenen ayarların tümünü desteklemez. İstediğiniz ayarı Intune’un destekleyip desteklemediğini öğrenmek için, ilgili ayarın konusunu açın. Her ayar sayfasında, desteklenen işlemi gösterilir. Intune’la çalışmak için, ayarın **Ekle** veya **Değiştir** işlemlerini desteklemesi gerekir.

## <a name="general-configuration-policy-settings"></a>Genel yapılandırma ilkesi ayarları

Kaydedilmiş Windows 10 masaüstü ve Windows 10 Mobile cihazlarının yerleşik ayarlarını yapılandırmak için Microsoft Intune Windows 10 için **genel yapılandırma ilkesini** kullanın.

### <a name="password"></a>Parola

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|
|**Cihazların kilidini açmak için parola gerektir**|-|
|**Gerekli parola türü**|Parolanın alfasayısal mı yoksa sayısal mı olacağını belirtir|
|**Gerekli parola türü** - **Minimum karakter kümesi sayısı**| Parolanın karakter kümelerinden (küçük harfler, büyük harfler, sayılar ve semboller) kaçını içereceğini belirtir|
|**En düşük parola uzunluğu**|Yalnızca Windows 10 Mobile için geçerlidir|
|**Cihaz silinmeden önce izin verilen yinelenen oturum açma hatası sayısı**.|Windows 10 çalıştıran cihazlar için: Cihazda BitLocker etkinse, belirttiğiniz başarısız oturum açma sayısından sonra cihaz BitLocker kurtarma moduna alınır. Cihazda BitLocker etkin değilse, bu ayar uygulanmaz.<br>Windows 10 Mobile çalıştıran cihazlar için: Belirttiğiniz başarısız oturum açma sayısından sonra cihaz silinir.|
|**Ekran kapanmadan önce herhangi bir işlem yapılmadan geçen dakika sayısı**|Ekran kilitlenmeden önce cihazın boşta bekleyeceği süreyi belirtir|
|**Parola kullanım süresi (gün)**|Cihaz parolasının ne kadar süre sonra değiştirilmesi gerektiğini belirtir|
|**Parola geçmişini anımsa**|Son kullanıcının daha önce kullanılmış parolalar oluşturmasının kısıtlanıp kısıtlanmayacağını belirtir|
|**Parola geçmişini anımsa** - **Önceki parolaların yeniden kullanılmasını önle**|Önceden kullanılmış ve cihaz tarafından anımsanacak olan parola sayısını belirtir|
|**Cihaz boş bir durumdan döndürüldüğünde parola iste**|Boşta durumundaki bir cihazın kilidini açmak için kullanıcının parola girmesi gerektiğini belirtir (yalnızca Windows 10 Mobile)|

### <a name="encryption"></a>Şifreleme

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|
|**Cihazda şifrelemeyi gerektir**|Hedeflenen cihazlarda şifrelemeyi etkinleştirir<br>(Yalnızca Windows 10 Mobile)|

### <a name="system"></a>Sistem

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|
|**Ekran yakalamaya izin ver**|Kullanıcının cihaz ekranını bir resim olarak yakalamasına olanak sağlar (yalnızca Windows 10 Mobile)|
|**Elle kayıt kaldırmaya izin ver**|Kullanıcının iş yeri hesabını cihazdan el ile silmesine olanak sağlar|
|**Elle kök sertifikası yüklemeye izin ver**|Windows 10 Mobile için geçerlidir|
|**Microsoft'a tanılama ve kullanım verilerinin gönderilmesine izin ver**|Olası değerler şunlardır:<br><br>**Hayır** - Microsoft’a hiç veri gönderilmez<br>**Temel** - Microsoft’a sınırlı bilgi gönderilir<br>**Gelişmiş** - Microsoft’a gelişmiş tanılama bilgileri gönderilir<br>**Tam (önerilen)** - **Gelişmiş** ayarıyla aynı veriler, artı olarak cihazın durumuyla ilgili ek veriler gönderilir|


### <a name="account-and-synchronization"></a>Hesap ve eşitleme

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|---------------------|
|**Microsoft hesabına izin ver**|Kullanıcının bir Microsoft hesabını cihazla ilişkilendirmesine olanak sağlar|
|**Microsoft olmayan hesapların elle eklenmesine izin ver**|Kullanıcının cihaza bir Microsoft hesabıyla ilişkilendirilmemiş e-posta hesapları eklemesine olanak sağlar|
|**Microsoft hesapları için ayarları eşitlemeye izin ver**|Microsoft hesabıyla ilişkilendirilmiş cihaz ve uygulama ayarlarının cihazlar arasında eşitlenmesine izin verin|

### <a name="microsoft-edge"></a>Microsoft Edge

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|
|**Web tarayıcısına izin ver**|Cihazda Microsoft Edge web tarayıcısının kullanılmasına izin verir<br>(Yalnızca Windows 10 Mobile)|
|**Adres çubuğunda arama önerilerine izin ver**|Siz arama sözcükleri yazarken arama motorunuzun site önerilerinde bulunmasına olanak sağlar|
|**Internet Explorer'a intranet trafiği göndermeye izin ver**|Kullanıcıların Internet Explorer’da intranet web siteleri açmasına olanak sağlar<br>(Yalnızca Windows 10 masaüstü)|
|**Do Not Track özelliğine izin ver**|Microsoft Edge tarayıcısını, kullanıcıların ziyaret ettiği web sitelerine İzleme (DNT) üst bilgileri gönderecek şekilde yapılandırır|
|**SmartScreen’i etkinleştir**||
|**Etkin betik yazmaya izin ver**|Edge tarayıcısında JavaScript gibi betiklerin çalıştırılmasına izin verir|
|**Açılır pencerelere izin ver**|Yalnızca Windows 10 Desktop için geçerlidir|
|**Tanımlama bilgilerine izin ver**||
|**Otomatik Doldurmaya İzin Ver**|Kullanıcıların tarayıcıdaki otomatik tamamlama ayarlarını değiştirmesine olanak tanır<br>(Yalnızca Windows 10 masaüstü)|
|**Parola Yöneticisi’ne izin ver**|Microsoft Edge Parola Yöneticisi özelliğini etkinleştirir veya devre dışı bırakır|
|**Kurumsal Mod site listesi konumu**|Kurumsal modda açılan web siteleri listesinin nerede olduğunu belirtir. Kullanıcılar bu listeyi düzenleyemez.<br>(Yalnızca Windows 10 masaüstü)|

### <a name="apps"></a>Uygulamalar

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|---------------------|
|**Uygulama depolamaya izin ver**|Yalnızca Windows 10 Mobile için geçerlidir|



### <a name="cellular"></a>Hücresel

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|---------------------|
|**Veri dolaşımına izin ver**|Verilere erişirken ağlar arasında dolaşıma izin verin|
|**Hücresel veri üzerinden VPN'ye izin ver**|Cihazın cep telefonu şebekesine bağlandığında VPN bağlantılarına erişip erişemeyeceğini denetler|
|**Hücresel veri üzerinden VPN dolaşımına izin ver**|Cihazın cep telefonu şebekesinde dolaşımı sırasında VPN bağlantılarına erişip erişemeyeceğini denetler|

### <a name="hardware"></a>Donanım

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|
|**Kameraya izin ver**|-|
|**Çıkarılabilir depolamaya izin ver**|Cihazla birlikte SD kartı gibi dış depolama cihazlarının kullanılıp kullanılamayacağını belirtir|
|**Wi-Fi bağlantısına izin ver**|Yalnızca Windows 10 Mobile için geçerlidir|
|**İnternet paylaşımına izin ver**|Cihazda İnternet bağlantısı paylaşımının kullanımına izin verir|
|**Elle Wi-Fi yapılandırmasına izin ver**|Kullanıcının kendi Wi-Fi bağlantılarını yapılandırıp yapılandıramayacağını veya yalnızca Wi-Fi profili tarafından yapılandırılan bağlantıları kullanıp kullanamayacağını denetleyin<br>(Yalnızca Windows 10 Mobile)|
|**Ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmaya izin ver**|Cihazın ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmasına ve bağlantıyla ilgili hüküm ve koşulları otomatik olarak kabul etmesine olanak sağlar|
|**Coğrafi konuma izin ver**|Cihazın konum hizmetleri bilgilerini kullanıp kullanamayacağını belirtir|
|**NFC'ye izin ver**|Cihazın Yakın Alan İletişimi özelliklerini kullanmasına izin verir|
|**Bluetooth'a izin ver**|-|
|**Bluetooth bulunabilirlik moduna izin ver**|Bu cihazın diğer Bluetooth özellikli cihazlar tarafından bulunabilmesine olanak sağlar|
|**Bluetooth reklamlarına izin ver**|Cihazların Bluetooth üzerinden reklam almasına izin verir|
|**Telefon sıfırlamaya izin ver**|Kullanıcının cihazını fabrika ayarlarına sıfırlayıp sıfırlayamayacağını denetler|
|**USB bağlantısına izin ver**|Cihazların USB bağlantısı aracılığıyla dış depolama cihazlarına erişip erişemeyeceğini denetler|
|**AntiTheft modunu etkinleştir**|Windows AntiTheft modunun etkin olup olmadığını yapılandırın|

### <a name="features"></a>Özellikler

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|---------------------|
|**Kopyalama ve yapıştırmaya izin ver**|Yalnızca Windows 10 Mobile için geçerlidir|
|**Ses kaydetmeye izin ver**|Yalnızca Windows 10 Mobile için geçerlidir|
|**Cortana’ya izin ver**|Cortana sesli yardımcısını etkinleştirin veya devre dışı bırakın|
|**İşlem merkezi bildirimlerine izin ver**|Cihaz kilit ekranında işlem merkezi bildirimlerini etkinleştirin veya devre dışı bırakın<br>(Yalnızca Windows 10 Mobile)|

### <a name="windows-defender"></a>Windows Defender

Tüm ayarlar yalnızca Windows 10 masaüstüne yöneliktir.

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|----------------------|---------------------|
|**Gerçek zamanlı izlemeye izin ver**|Kötü amaçlı yazılım, casus yazılım ve istenmeyen diğer yazılımlar için gerçek zamanlı taramaya izin verir|
|**Davranış izlemeye izin ver**|Defender’ın cihazlarda bilinen şüpheli etkinlik düzenlerini denetlemesine olanak sağlar|
|**Ağ İnceleme Sistemi'ni Etkinleştir**|Ağ İnceleme Sistemi (NIS), kötü amaçlı trafiğin algılanmasına ve engellenmesine katkıda bulunmak için Microsoft Endpoint Protection Center’dan gelen bilinen güvenlik açıklarının imzalarını kullanarak ağ tabanlı saldırılara karşı korunmaya yardımcı olur|
|**Tüm indirmeleri tara**|Defender’ın İnternet’ten indirilen tüm dosyaları tarayıp taramayacağını denetler|
|**Betik taramaya izin ver**|Defender’ın Internet Explorer’da kullanılan betikleri taramasına olanak sağlar|
|**Dosya ve program etkinliğini izle**|Defender’ın cihazlarda dosya ve program etkinliğini izlemesine izin verir|
|**Çözümlenen kötü amaçlı yazılımın izleneceği gün sayısı**|Defender’ın çözümlenen kötü amaçlı yazılımı belirttiğiniz sayıda gün boyunca izlemeye devam etmesine olanak sağlar; böylece daha önce etkilenmiş olan cihazları el ile denetleyebilirsiniz. Gün sayısını **0** olarak ayarlarsanız, kötü amaçlı yazılım Karantina klasöründe kalır ve otomatik olarak kaldırılmaz. |
|**İstemci UI erişimine izin ver**|Windows Defender kullanıcı arabiriminin kullanıcılardan gizlenip gizlenmediğini denetler.<br>Bu ayar değiştirildiğinde, son kullanıcının bilgisayarı bir sonraki yeniden başlatmasında geçerlilik kazanır.|
|**Günlük hızlı tarama zamanla**|Her gün seçtiğiniz saatte gerçekleştirilecek olan bir hızlı tarama zamanlamanıza olanak sağlar|
|**Sistem taraması zamanla**|Seçtiğiniz gün ve saatte düzenli olarak gerçekleştirilecek tam veya hızlı bir sistem taraması zamanlamanıza olanak sağlar|
|**Tarama sırasında CPU kullanımını sınırla**|Taramaların kullanmasına izin verilecek CPU miktarını sınırlandırmanıza (**1** ile **100** arasında) olanak sağlar|
|**Arşiv dosyalarını tara**|Defender’ın .zip veya .cab dosyaları gibi arşivlenmiş dosyaları taramasına izin verir.|
|**E-posta iletilerini tara**|Defender’ın cihaza gelen e-posta iletilerini taramasına izin verir|
|**Çıkarılabilir sürücüleri tara**|Defender’ın USB çubukları gibi çıkarılabilir sürücüleri taramasına olanak sağlar|
|**Eşlenen ağ sürücülerini tara**|Defender’ın eşlenen ağ sürücüsündeki dosyaları taramasına olanak sağlar.<br>Sürücüdeki dosyalar salt okunur olduğunda, Defender bunların içinde bulduğu kötü amaçlı yazılımları kaldıramaz.|
|**Paylaşılan ağ klasörlerinden açılan dosyaları tara**|Defender’ın paylaşılan ağ sürücülerindeki dosyaları (örneğin UNC yolundan erişilenler) taramasına olanak sağlar.<br>Sürücüdeki dosyalar salt okunur olduğunda, Defender bunların içinde bulduğu kötü amaçlı yazılımları kaldıramaz.|
|**İmza güncelleştirme aralığı**|Defender’ın yeni imza dosyalarını denetleme aralığını belirtir.|
|**Bulut korumasına izin ver**|Microsoft Etkin Koruma Hizmeti’nin yönettiğiniz cihazlardan kötü amaçlı yazılım etkinliğiyle ilgili bilgi almasına izin verir veya bunu engeller. Bu bilgi gelecekte hizmeti geliştirmek için kullanılır.|
|**Kullanıcılardan örnek göndermelerini iste**|Kötü amaçlı olup olmadıklarını belirlemek için Microsoft tarafından daha fazla çözümlenmesi gerekebilecek dosyaların Microsoft’a otomatik olarak gönderilip gönderilmeyeceğini denetler|
|**Olası İstenmeyen Uygulama Algılama**|Kayıtlı Windows masaüstü cihazlarını, Windows Defender tarafından olası istenmeyen yazılım şeklinde sınıflandırılan yazılımları çalıştırmaya karşı korur. Bu uygulamaların çalıştırılmasına karşı koruma sağlayabilir veya istenmeyebilecek bir uygulama yüklendiğinde raporlanması için denetim modunu kullanabilirsiniz.|
|**Bir tarama çalıştırılırken veya gerçek zamanlı koruma kullanılırken dışlanacak dosya ve klasörler**|Dışlama listesinde **C:\Yol** veya **%ProgramFiles%\Yol\dosyaadı.exe** gibi bir veya birden çok dosya ve klasör ekler. Bu dosya ve klasörler gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.|
|**Bir tarama çalıştırılırken veya gerçek zamanlı koruma kullanılırken dışlanacak dosya uzantıları**|Dışlama listesine **jpg** veya **txt** gibi bir veya birden çok dosya uzantısı ekleyin. Bu uzantıya sahip dosyaların hiçbiri gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.|
|**Bir tarama çalıştırılırken veya gerçek zamanlı koruma kullanılırken dışlanacak işlemler**|Dışlama listesine **.exe**, **.com** veya **.scr** türünde bir veya birden çok işlem ekler. Bu işlemler gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.|


### <a name="updates"></a>Updates

|Ayar adı|Ek bilgiler (gerekliyse)|
|----------------|---------------|
|**Otomatik güncelleştirmelere izin ver**|Otomatik güncelleştirmelere izin verir. Güncelleştirme davranışını denetlemek için aşağıdaki ayarlardan birini yapılandırın:<br />**İndirmeyi bildir**<br />**Bakım sırasında otomatik olarak yükle**<br />**Bakım sırasında otomatik olarak yükle ve yeniden başlat**<br />**Zamanlanan tarihte otomatik yükle ve yeniden başlat** Not: Bu seçenek belirtildiğinde şu ayarları yapılandırabilirsiniz: **Son kullanıcıya bildirimi önle** ve **Zamanlanmış güncelleştirmeler için yükleme gününü tanımla**.<br>(Yalnızca Windows 10 masaüstü)|
|**Yayın öncesi özelliklere izin ver**|Microsoft’un Windows 10 cihazlara sürüm öncesi ayarlar ve özellikler dağıtmasına imkan tanır. Yalnızca ayarlara izin vermeyi tercih edebilirsiniz; aksi takdirde tüm sürüm öncesi ayarlar ve özellikler yüklenir.|

### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

