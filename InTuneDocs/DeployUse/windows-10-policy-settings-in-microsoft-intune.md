---
# required metadata

title: Microsoft Intune’da Windows 10 ilke ayarları | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune’da Windows 10 ilke ayarları

Kayıtlı Windows 10 masaüstü bilgisayarları ve Windows 10 mobil cihazlarında ayarları yapılandırmanıza yardımcı olması için, bu konu başlığı altında listelenen ilke ayarlarını kullanın.

## Genel yapılandırma ilkesi ayarları

Kayıtlı Windows 10 masaüstü ve Windows 10 Mobile cihazların genel ayarlarını yapılandırmak isterseniz, Windows 10 için Microsoft **genel yapılandırma ilkesini** kullanın:


### Parola

|Ayar adı|Ayrıntılar|Windows 10 Masaüstü|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Cihazların kilidini açmak için parola gerektir**|Desteklenen cihazlarda bir parola gerektir.|Evet|Evet|
|**Gerekli parola türü**|Gerekli parola türünü belirtir. Örneğin, yalnızca sayısal ya da alfasayısal olabilir.|Evet|Evet|
|**Gerekli parola türü** - **Minimum karakter kümesi sayısı**|Küçük harfler, büyük harfler, rakamlar ve semboller şeklinde dört karakter kümesi vardır. Bu ayar parolanın kaç farklı karakter kümesi içermesi gerektiğini belirtir.|Evet|Evet|
|**Minimum parola uzunluğu**|Cihaz parolasının içermesi gereken minimum karakter sayısını belirtir.|Hayır|Evet|
|**Cihaz temizlenmeden önce izin verilen yinelenen oturum açma hatası sayısı**|Bu sayıda oturum açma denemesi başarısız olursa cihazı temizler.|Evet|Evet|
|**Ekran kapanmadan önce geçen işlem yapılmayan dakika sayısı**|Ekran kilitlenmeden önce cihazın boşta bekleyeceği süreyi belirtir.|Evet|Evet|
|**Parola geçerlilik süresi (gün)**|Cihaz parolasının ne kadar süre sonra değiştirilmesi gerektiğini belirtir.|Evet|Evet|
|**Parola geçmişini anımsa**|Son kullanıcının daha önce kullanılmış parolalar oluşturmasını kısıtlamak isteyip istemediğinizi belirtir.|Evet|Evet|
|**Parola geçmişini anımsa** - **Önceki parolaların yeniden kullanılmasını önle**|Önceden kullanılmış ve cihaz tarafından anımsanacak olan parola sayısını belirtir.|Evet|Evet|
|**Resimli parolaya veya PIN’e izin ver**|Oturum açmak için bir resim üzerinde basit hareketler veya basit bir PIN kullanmanıza olanak sağlar.|Evet|Hayır|
|**Cihaz boş bir durumdan döndürüldüğünde parola iste**|Etkinleştirilirse, boşta durumundaki bir cihazın kilidini açmak için kullanıcının parola girmesi gerekir.|Hayır|Evet|

### Şifreleme

|Ayar adı|Ayrıntılar|Windows 10 Masaüstü|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Cihazda şifrelemeyi gerektir**|Hedeflenen cihazlarda şifrelemeyi etkinleştirir.|Hayır|Evet|

### Sistem

|Ayar adı|Ayrıntılar|Windows 10 Masaüstü|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Ekran yakalamaya izin ver**|Kullanıcının cihaz ekranını bir resim olarak yakalamasına olanak sağlar.|Hayır|Evet|
|**Elle kayıt kaldırmaya izin ver**|Kullanıcının iş yeri hesabını cihazdan el ile silmesine olanak sağlar.|Evet|Evet|
|**Elle kök sertifikası yüklemeye izin ver**|Kullanıcının elle kök sertifika yükleyip yükleyemeyeceğini belirtir|Hayır|Evet|
|**Microsoft'a tanılama ve kullanım verilerinin gönderilmesine izin ver**|Cihazlardan Microsoft’a gönderilecek tanılama ve kullanım verilerinin miktarını belirler.<br>**Hayır** - Microsoft’a hiç veri gönderilmez<br>**Temel** -Cihaz Microsoft’a yalnızca sınırlı miktarda bilgi gönderir.<br>**Gelişmiş** - Microsoft’a gelişmiş tanılama bilgileri gönderilir<br>**Tam (önerilen)** - **Gelişmiş** ayarıyla aynı veriler, artı olarak cihazın durumuyla ilgili ek veriler gönderilir|Evet|Evet|


### Hesap ve eşitleme

|Ayar adı|Ayrıntılar|Windows 10 Masaüstü|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Microsoft Hesabına izin ver**|Kullanıcının bir Microsoft hesabını cihazla ilişkilendirmesine olanak sağlar.|Evet|Evet|
|**Microsoft olmayan hesapların elle eklenmesine izin ver**|Kullanıcının cihaza bir Microsoft hesabıyla ilişkilendirilmemiş e-posta hesapları eklemesine olanak sağlar.|Evet|Evet|
|**Microsoft hesapları için ayarları eşitlemeye izin ver**|Microsoft hesabıyla ilişkilendirilmiş cihaz ve uygulama ayarlarının cihazlar arasında eşitlenmesine izin verin.|Evet|Evet|

### E-posta ayarları

|Ayar adı|Ayrıntılar|Windows 10 Masaüstü|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Microsoft hesabını Windows Mail uygulamasında isteğe bağlı hale getir**|Windows Mail uygulamasında Microsoft hesabı gereksinimini kaldırmak için bunu yapılandırın.|Evet|Hayır|



### Microsoft Edge

|Ayar adı|Ayrıntılar|Windows 10 Masaüstü|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Web tarayıcısına izin ver**|Cihazda Edge web tarayıcısının kullanılmasına izin verin.|Hayır|Evet|
|**Adres çubuğunda arama önerilerine izin ver**|Siz arama tümcecikleri yazarken arama motorunuzun site önerilerinde bulunmasına olanak sağlar.|Evet|Evet|
|**Internet Explorer'a intranet trafiği göndermeye izin ver**|Kullanıcıların Internet Explorer’da intranet web siteleri açmasına olanak sağlar.|Evet|Hayır|
|**İzleme özelliğine izin ver**|Edge tarayıcısını, kullanıcıların ziyaret ettiği web sitelerine Do Not Track (İzleme) üst bilgileri gönderecek şekilde yapılandırır.|Evet|Evet|
|**SmartScreen’i etkinleştir**|Cihazlarda SmartScreen tarayıcı ayarını etkinleştirir.|Evet|Evet|
|**Etkin betik yazmaya izin ver**|Edge tarayıcısında Javascript gibi betiklerin çalıştırılmasına izin verir.|Evet|Evet|
|**Açılır pencerelere izin ver**|Açılır pencere engelleyicisini etkinleştirir veya devre dışı bırakır.|Evet|Hayır|
|**Tanımlama bilgilerine izin ver**|Tanımlama bilgilerine izin verin veya bunları devre dışı bırakın.|Evet|Evet|
|**Otomatik Doldurma’ya izin ver**|Kullanıcıların tarayıcıdaki otomatik tamamlama ayarlarını değiştirmesine izin verin.|Evet|Hayır|
|**Parola Yöneticisi’ne izin ver**|Edge Parola Yöneticisi özelliğini etkinleştirin veya devre dışı bırakın.|Evet|Evet|
|**Kurumsal Mod site listesi konumu**|Kurumsal modda açılacak web siteleri listesinin nerede olduğunu belirtir. Kullanıcılar bu listeyi düzenleyemez.|Evet|Hayır|

### Uygulamalar

|Ayar adı|Ayrıntılar|Windows 10 Masaüstü|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Uygulama mağazasına izin ver**|Kullanıcının cihazda uygulama mağazasına erişmesine izin verin.|Hayır|Evet|



### Hücresel

|Ayar adı|Ayrıntılar|Windows 10 Masaüstü|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Veri dolaşımına izin ver**|Verilere erişirken ağlar arasında dolaşıma izin verin.|Evet|Evet|
|**Hücresel veri üzerinden VPN'ye izin ver**|Cihazın cep telefonu şebekesine bağlandığında VPN bağlantılarına erişip erişemeyeceğini denetler.|Evet|Evet|
|**Hücresel veri üzerinden VPN dolaşımına izin ver**|Cihazın cep telefonu şebekesinde dolaşımı sırasında VPN bağlantılarına erişip erişemeyeceğini denetler.|Evet|Evet|

### Donanım

|Ayar adı|Ayrıntılar|Windows 10 Masaüstü|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Kameraya izin ver**|Cihaz kamerasının kullanılıp kullanılamayacağını belirtir.|Evet|Evet|
|**Çıkarılabilir depolama birimine izin ver**|Cihazla birlikte SD kartı gibi dış depolama cihazlarının kullanılıp kullanılamayacağını belirtir.|Evet|Evet|
|**Wi-Fi'a izin ver**|Cihazın Wi-Fi özelliğinin kullanımına izin verir.|Hayır|Evet|
|**İnternet paylaşımına izin ver**|Cihazda İnternet bağlantısı paylaşımının kullanımına izin verin.|Evet|Evet|
|**Elle Wi-Fi yapılandırmasına izin ver**|Kullanıcının kendi Wi-Fi bağlantılarını yapılandırıp yapılandıramayacağını veya yalnızca Wi-Fi profili tarafından yapılandırılan bağlantıları kullanıp kullanamayacağını denetleyin.|Hayır|Evet|
|**Ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmaya izin ver**|Cihazın ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmasına ve bağlantıyla ilgili hüküm ve koşulları otomatik olarak kabul etmesine olanak sağlar.|Evet|Evet|
|**Coğrafi konuma izin ver**|Cihazın konum hizmetleri bilgilerini kullanıp kullanamayacağını belirtir.|Evet|Evet|
|**NFC'ye izin ver**|Cihazın Yakın Alan İletişimi özelliklerini kullanmasına izin verir.|Evet|Evet|
|**Bluetooth'a izin ver**|Cihazda Bluetooth özelliklerinin kullanılmasına izin verir.|Evet|Evet|
|**Bluetooth bulunabilirlik moduna izin ver**|Bu cihazın diğer Bluetooth özellikli cihazlar tarafından bulunabilmesine olanak sağlar.|Evet|Evet|
|**Bluetooth reklamlarına izin ver**|Cihazların Bluetooth üzerinden reklam almasına izin verir.|Evet|Evet|
|**Bluetooth bağlanılabilirlik moduna izin ver** **Önemli:** |Bu ayar Windows 10’da artık desteklenmez ve bir süre sonra kaldırılacaktır.|Evet|Evet|
|**Telefon sıfırlamaya izin ver**|Kullanıcının cihazını fabrika ayarlarına sıfırlayıp sıfırlayamayacağını denetler.|Evet|Evet|
|**USB bağlantısına izin ver**|Cihazların USB bağlantısı aracılığıyla dış depolama cihazlarına erişip erişemeyeceğini denetler.|Evet|Evet|
|**AntiTheft modunu etkinleştir**|Windows AntiTheft modunun etkin olup olmadığını yapılandırın.|Evet|Evet|

### Özellikler

|Ayar adı|Ayrıntılar|Windows 10 Masaüstü|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Kopyalama ve yapıştırmaya izin ver**|Cihazda kopyalama ve yapıştırmanın kullanımını etkinleştirin veya devre dışı bırakın.|Hayır|Evet|
|**Ses kaydetmeye izin ver**|Cihazda ses kayıt özelliklerinin kullanımını etkinleştirin veya devre dışı bırakın.|Hayır|Evet|
|**Cortana’ya izin ver**|Cortana sesli yardımcısını etkinleştirin veya devre dışı bırakın.|Evet|Evet|
|**İşlem merkezi bildirimlerine izin ver**|Cihaz kilit ekranında işlem merkezi bildirimlerini etkinleştirin veya devre dışı bırakın.|Hayır|Evet|

### Defender

|Ayar adı|Ayrıntılar|Windows 10 Masaüstü|Windows 10 Mobile|
|-|-|
|**Gerçek zamanlı izlemeye izin ver**|Kötü amaçlı yazılım, casus yazılım ve istenmeyen diğer yazılımlar için gerçek zamanlı taramaya izin verir.|Evet|Hayır|
|**Davranış izlemeye izin ver**|Defender’ın cihazlarda bilinen şüpheli etkinlik düzenlerini denetlemesine olanak sağlar.|Evet|Hayır
|**Ağ İnceleme Sistemi'ni Etkinleştir**|Ağ İnceleme Sistemi (NIS), kötü amaçlı trafiğin algılanmasına ve engellenmesine katkıda bulunmak için Microsoft Endpoint Protection Center’dan gelen bilinen güvenlik açıklarının imzalarını kullanarak ağ tabanlı saldırılara karşı korunmaya yardımcı olur.|Evet|Hayır
|**Tüm indirmeleri tara**|Defender’ın İnternet’ten indirilen tüm dosyaları tarayıp taramayacağını denetler.|Evet|Hayır
|**Betik taramaya izin ver**|Defender’ın Internet Explorer’da kullanılan betikleri taramasına olanak sağlar.|Evet|Hayır
|**Dosya ve program etkinliğini izle**|Defender’ın cihazlarda dosya ve program etkinliğini izlemesine izin vermek için bu ayarı etkinleştirin.|Evet|Hayır
|**Çözümlenen kötü amaçlı yazılımın izleneceği gün sayısı**|Defender’ın çözümlenen kötü amaçlı yazılımı belirttiğiniz sayıda gün boyunca izlemeye devam etmesine olanak sağlar; böylece daha önce etkilenmiş olan cihazları el ile denetleyebilirsiniz. Gün sayısını **0** olarak ayarlarsanız, kötü amaçlı yazılım Karantina klasöründe kalır ve otomatik olarak kaldırılmaz. |Evet|Hayır
|**İstemci UI erişimine izin ver**|Windows Defender kullanıcı arabiriminin son kullanıcılardan gizlenip gizlenmediğini denetler.<br>Bu ayar değiştirildiğinde, son kullanıcının bilgisayarı bir sonraki yeniden başlatmasında geçerlilik kazanır.|Evet|Hayır
|**Günlük hızlı tarama zamanla**|Her gün seçtiğiniz saatte gerçekleştirilecek olan bir hızlı tarama zamanlamanıza olanak sağlar.|Evet|Hayır
|**Sistem taraması zamanla**|Seçtiğiniz gün ve saatte düzenli olarak gerçekleştirilecek tam veya hızlı bir sistem taraması zamanlamanıza olanak sağlar.|Evet|Hayır
|**Tarama sırasında CPU kullanımını sınırla**|Taramaların kullanmasına izin verilecek CPU miktarını sınırlandırmanıza (**1** ile **100** arasında) olanak sağlar.)|Evet|Hayır
|**Arşiv dosyalarını tara**|Defender’ın Zip veya Cab dosyaları gibi arşivlenmiş dosyaları taramasına izin verir.|Evet|Hayır
|**E-posta iletilerini tara**|Defender’ın cihaza gelen e-posta iletilerini taramasına izin verir.|Evet|Hayır
|**Çıkarılabilir sürücüleri tara**|Defender’ın USB çubukları gibi çıkarılabilir sürücüleri taramasına olanak sağlar.|Evet|Hayır
|**Eşlenen ağ sürücülerini tara**|Defender’ın eşlenen ağ sürücüsündeki dosyaları taramasına olanak sağlar.<br>Sürücüdeki dosyalar salt okunur olduğunda, Defender bunların içinde bulduğu kötü amaçlı yazılımları kaldıramaz.|Evet|Hayır
|**Paylaşılan ağ klasörlerinden açılan dosyaları tara**|Defender’ın paylaşılan ağ sürücülerindeki dosyaları (örneğin UNC yolundan erişilenler) taramasına olanak sağlar.<br>Sürücüdeki dosyalar salt okunur olduğunda, Defender bunların içinde bulduğu kötü amaçlı yazılımları kaldıramaz.|Evet|Hayır
|**İmza güncelleştirme aralığı**|Defender’ın yeni imza dosyalarını denetleme aralığını belirtin.|Evet|Hayır
|**Bulut korumasına izin ver**|Microsoft Etkin Koruma Hizmeti’nin yönettiğiniz cihazlardan kötü amaçlı yazılım etkinliğiyle ilgili bilgi almasına izin verin veya bunu engelleyin. Bu bilgi gelecekte hizmeti geliştirmek için kullanılır.|Evet|Hayır
|**Kullanıcılardan örnek göndermelerini iste**|Kötü amaçlı olup olmadıklarını saptamak için Microsoft tarafından daha fazla çözümlenmesi gerekebilecek dosyaların Microsoft’a otomatik olarak gönderilip gönderilmeyeceğini denetler.|Evet|Hayır
|**Bir tarama çalıştırılırken veya gerçek zamanlı koruma kullanılırken dışlanacak dosya ve klasörler**|Dışlama listesinde **C:\Yol** veya **%ProgramFiles%\Yol\dosyaadı.exe** gibi bir veya birden çok dosya ve klasör ekleyin. Bu dosya ve klasörler gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.|Evet|Hayır
|**Bir tarama çalıştırılırken veya gerçek zamanlı koruma kullanılırken dışlanacak dosya uzantıları**|Dışlama listesine **jpg** veya **txt** gibi bir veya birden çok dosya uzantısı ekleyin. Bu uzantıya sahip dosyaların hiçbiri gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.|Evet|Hayır
|**Bir tarama çalıştırılırken veya gerçek zamanlı koruma kullanılırken dışlanacak işlemler**|Dışlama listesine **.exe**, **.com** veya **.scr** türünde bir veya birden çok işlem ekleyin. Bu işlemler gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.|Evet|Hayır| 


### Güncelleştirme ayarları

|Ayar adı|Ayrıntılar|Windows 10 Masaüstü|Windows 10 Mobile|
|----------------|---------------|----------------------|---------------------|
|**Otomatik güncelleştirmelere izin ver**|Otomatik güncelleştirmelere izin vermek bu ayarı etkinleştirin. Ardından, güncelleştirme davranışını denetlemek için aşağıdaki ayarlardan birini yapılandırın:<br /><br />**İndirmeyi bildir**<br /><br />**Bakım sırasında otomatik olarak yükle**<br /><br />**Bakım sırasında otomatik olarak yükle ve yeniden başlat**<br /><br />**Zamanlanan tarihte otomatik yükle ve yeniden başlat** **Not:** Bu seçenek belirtildiğinde şu ayarları yapılandırabilirsiniz:  **Son kullanıcıya bildirimi önle** ve **Zamanlanmış güncelleştirmeler için yükleme gününü tanımla**.|Evet|Hayır|

## Özel ilke ayarları
Windows 10 ve Windows 10 Mobile cihazlarındaki özellikleri denetlemek için kullanılabilen OMA-URI (Open Mobile Alliance Tekdüzen Kaynak Tanımlayıcısı) ayarlarını dağıtmak üzere Windows 10 ve Windows 10 Mobile cihazları için Microsoft Intune **özel yapılandırma ilkesini** kullanın. Bunlar, birçok mobil cihaz üreticisinin, cihaz özelliklerini denetlemek için kullandığı standart ayarlardır.

Bu özellik, Intune genel yapılandırma ilkesiyle, yapılandırılabilir olmayan Windows 10 ayarlarını dağıtmanıza olanak sağlamak için tasarlanmıştır. Bu ilkelerle yapılandırabileceğiniz ayarlar hakkında daha fazla bilgi için bkz. [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)..

Kaydedilen Windows 10 cihazlarda yapılandırabileceğiniz OMA-URI ayarlarının listesi için bu konunun devamındaki Windows 10 cihazlar için özel URI ayarları bölümüne bakın.

### Genel ayarlar

|Ayar adı|Ayrıntılar|
    |----------------|--------------------|
    |**Ad**|Intune konsolunda tanımanıza yardımcı olması için benzersiz bir ad girin.|
    |**Açıklama**|İlkeye genel bir bakış ve ilkeyi bulmanıza yardımcı olacak diğer ek bilgileri içeren bir açıklama sağlayın.|

### OMA-URI ayarları

|Ayar adı|Ayrıntılar|
    |--------|--------------------|
    |**Ayar adı**|Ayarlar listesinde tanımanıza yardımcı olması için OMA-URI ayarı için benzersiz bir ad girin.|
    |**Ayar açıklaması**|Ayara genel bir bakış ve ayarı bulmanıza yardımcı olacak diğer ek bilgileri içeren bir açıklama sağlayın.|
    |**Veri türü**|Bu OMA-URI ayarını belirteceğiniz tarih türünü seçin. Aşağıdakilerden birini seçin:<br /><br />-   **Dize**<br />-   **Dize (XML)**<br />-   **Tarih ve saat**<br />-   **Tamsayı**<br />-   **Kayan nokta**<br />-   **Boole değeri**|
    |**OMA-URI (büyük küçük harf duyarlı)**|Bir ayar için sağlamak istediğiniz OMA-URI’yi belirtin.|
    |**Değer**|Önceden belirttiğiniz OMA-URI ile ilişkilendirilecek değeri belirtin.|


## Windows 10 cihazlar için özel URI ayarları
Bu konuda, Microsoft Intune **Windows 10 Özel İlkesi**‘nde Windows 10 ve Windows 10 Mobile cihazları için yapılandırabileceğiniz ayarlar listelenir..


> [!NOTE]
> Aşağıdaki tablonun **Destekleyen** sütununda aşağıdaki değerler kullanılır:
> 
> -   **Masaüstü** – Bu ayar yalnızca Intune’a kaydedilen Windows 10 Professional ve Enterprise bilgisayarları destekler.
> -   **Mobil** – Bu ayar yalnızca Windows 10 Mobile cihazları destekler.
> -   **Her İkisi** – Bu ayar hem masaüstü hem de mobil cihazları destekler.
> 
> Windows Özel URI İlkesini kullanmak istiyorsanız tüm cihazlar Intune’a kaydedilmelidir.

### İlke

|İlke adı|Destekleyen|Ayrıntılar|
|---------------|------------|-----------|
|**​Otomatik Güncelleştirmeye İzin Ver**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:0** - **5**<br /><br />**Varsayılan değer:** 1|
|**Yükleme Gününü Zamanlama**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** - Her gün.<br /><br />**1** - Pazar<br /><br />**2** - Pazartesi<br /><br />**3** - Salı<br /><br />**4** - Çarşamba<br /><br />**5** - Perşembe<br /><br />**6** - Cuma<br /><br />**7** - Cumartesi.<br /><br />**Varsayılan değer:** 0|
|**Yükleme Saatini Zamanlama**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:0** – **23** saat (0, gece yarısıdır)<br /><br />**Varsayılan değer:** 3|
|**DeviceLock/AllowIdleReturnWithoutPassword**|Mobil|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** - kullanıcı, parola yetkisiz kullanım süresi zamanlayıcısını ayarlayamaz ve değer, “her defasında” olarak ayarlanır<br /><br />**1** - kullanıcı, parola yetkisiz kullanım süresi zamanlayıcısını ayarlayabilir<br /><br />**Varsayılan değer:** 1|
|**WiFi/AllowWiFi**|Mobil|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – **Wi-Fi bağlantısı kullanılmasına** izin verme.<br /><br />**1** –**Wi-Fi bağlantısı kullanılmasına izin ver**.<br /><br />**Varsayılan değer:** 1|
|**WiFi/AllowInternetSharing**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – İnternet paylaşımına izin verme.<br /><br />**1** – İnternet Paylaşımına izin ver<br /><br />**Varsayılan değer:** 1|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**WiFi/AllowManualWiFiConfiguration**|Mobil|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – MDM tarafından sağlanan dışında bir Wi-Fi bağlantısına izin verilmez.<br /><br />**1** – Önceden MDM tarafından sağlananlar dışında yeni ağ SSID’leri eklenmesine izin verilir.<br /><br />**Varsayılan değer:** 1|
|**System/AllowLocation**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/System/AllowLocation<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**System/AllowTelemetry**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/System/AllowTelemetry<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – İzin verilmiyor (yalnızca Kurumsal)<br /><br />**1** – Sınırlı<br /><br />**2** – Tam<br /><br />**3** - Tam ve tanılama bilgileri<br /><br />**Varsayılan değer:** 2|
|**System/AllowExperimentation**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/System/AllowExperimentation<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – İzin verilmiyor<br /><br />**1**- Yalnızca ayarlar<br /><br />**2**- Ayarlar ve deneme<br /><br />**Varsayılan değer:** 1|
|**Security/AntiTheftMode**|Mobil|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Security/AntiTheftMode<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** - Hırsızlık Önleme moduna izin verme<br /><br />**1** Kullanıcı tercihi<br /><br />**Varsayılan değer:** 1|
|**Connectivity/AllowUSBConnection**|Mobil|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**System/AllowUserToResetPhone**|Mobil|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Connectivity/AllowCellularDataRoaming**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Connectivity/AllowVPNOverCellular**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** - Hücresel şebeke üzerinden VPN’ye izin verilmez<br /><br />**1** – VPN, hücresel şebeke de dahil tüm bağlantıları kullanır.<br /><br />**Varsayılan değer:** 1|
|**Connectivity/AllowVPNRoamingOverCellular**|Mobil|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Connectivity/AllowVPNRoamingOverCellular**|Mobil|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Connectivity/AllowBluetooth**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – Kullanıcının Bluetooth’u açmasına izin verilmez.<br /><br />**1** – Ayrılmış. Kullanıcı Bluetooth’u açabilir ve yapılandırabilir (MDM için Windows Phone 8.1, EAS, Windows 10 masaüstü veya Windows 10 Mobile’da desteklenmez)<br /><br />**2** - İzin verilir. Kullanıcı Bluetooth’u açabilir ve yapılandırabilir.<br /><br />**Varsayılan değer:** 2|
|**Experience/AllowScreenCapture**|Mobil|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Experience/AllowTaskSwitcher**|Mobil|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Experience/AllowVoiceRecording**|Mobil|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Experience/AllowSyncMySettings**|Mobil|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – Dolaşıma izin verme<br /><br />**1** – Dolaşıma izin ver<br /><br />**Varsayılan değer:** 1|
|**Experience/AllowManualMDMUnenrollment**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Accounts/AllowMicrosoftAccountConnection**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Security/AllowManualRootCertificateInstallation**|Mobil|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Security/AllowAddProvisioningPackages**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Search/DisableBackoff**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Search/DisableBackoff<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0**<br /><br />**1**<br /><br />**Varsayılan değer:** 0|
|**Search/PreventRemoteQueries**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0**<br /><br />**1**<br /><br />**Varsayılan değer:** 1|
|**Search/AllowUsingDiacritics**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0**<br /><br />**1**<br /><br />**Varsayılan değer:** 0|
|**Search/AlwaysUseAutoLangDetection**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0**<br /><br />**1**<br /><br />**Varsayılan değer:** 0|
|**Search/DisableRemovableDriveIndexing**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0**<br /><br />**1**<br /><br />**Varsayılan değer:** 0|
|**Search/PreventIndexingLowDiskSpaceMB**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0**<br /><br />**1**<br /><br />**Varsayılan değer:** 1|
|**Search/AllowIndexingEncryptedStoresOrItems**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0**<br /><br />**1**<br /><br />**Varsayılan değer:** 0|
|**Security/AllowRemoveProvisioningPackage**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Security/RequireProvisioningPackageSignature**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0**<br /><br />**1**<br /><br />**Varsayılan değer:** 0|
|**AboveLock/AllowActionCenterNotifications**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**TextInput/AllowIMENetworkAccess**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – İzin verme<br /><br />Açık Genişletilmiş Sözlük kapalıdır.<br /><br />Kullanıcı şunları yapamaz:<br /><br />Yeni bir Açık Genişletilmiş Sözlük ekleme<br /><br />Yeni bir arama tümleştirme yapılandırma dosyası ekleme<br /><br />Bulut aday özelliğini kullanma<br /><br />Kullanıcı tarafından kaydedilen sözcüğü gönderme<br /><br />Ek olarak:<br /><br />Bu ilke ayarı etkinleştirilmeden önce eklenen bir Açık Genişletilmiş Sözlük, dönüştürme için kullanılmaz.<br /><br />Bu ilke ayarı etkinleştirilmeden önce yüklenen bir arama tümleştirme yapılandırması kullanılmaz.<br /><br />**1** - İzin ver<br /><br />Açık Genişletilmiş Sözlük eklenebilir ve varsayılan olarak kullanılabilir. Ayrıca, arama tümleştirme işlevi varsayılan olarak kullanılabilir.<br /><br />Kullanıcı şunları yapabilir:<br /><br />Bulut aday özelliğini kullanma<br /><br />Kullanıcı tarafından kaydedilen sözcüğü gönderme<br /><br />**Varsayılan değer:**|
|**TextInput/AllowKoreanExtendedHanja**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/TextInput/AllowKoreanExtendedHanja<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**TextInput/AllowIMELogging**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** - Hatalı dönüştürme günlüğü kapalıdır. Otomatik olarak ayarlanmış veriler ve giriş geçmişi verileri bir dosyaya kaydedilmez.<br /><br />**1** - Hatalı dönüştürme günlüğü açıktır. Otomatik olarak ayarlanmış veriler ve giriş geçmişi verileri bir dosyaya kaydedilir.<br /><br />**Varsayılan değer:** 1|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**TextInput/AllowJapaneseIVSCharacters**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**TextInput/AllowJapaneseUserDictionary**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** - JIS karakterleri dışında tümü filtrelenir<br /><br />**1** - Hiçbir karakter filtrelenmez<br /><br />**Varsayılan değer:** 1|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** - JIS0208 karakterleri dışında tümü filtrelenir<br /><br />**1** - Hiçbir karakter filtrelenmez<br /><br />**Varsayılan değer:** 1|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** - JIS0208 karakterleri veya EUDC karakterleri dışında tümü filtrelenir<br /><br />**1** - Hiçbir karakter filtrelenmez.<br /><br />**Varsayılan değer:** 1|
|**TextInput/AllowInputPanel**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Bluetooth/AllowDiscoverableMode**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Bluetooth/AllowAdvertising**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Settings/AllowDataSense**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Settings/AllowDataSense<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Settings/AllowVPN**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Settings/AllowVPN<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Settings/AllowWorkplace**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Settings/AllowDateTime**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Settings/AllowDateTime<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Settings/AllowLanguage**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Settings/AllowLanguage<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Settings/AllowRegion**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Settings/AllowRegion<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Settings/AllowSignInOptions**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Settings/AllowYourAccount**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Settings/AllowPowerSleep**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Settings/AllowAutoPlay**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Experience/AllowCortana**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Experience/AllowCortana<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Search/SafeSearchPermissions**|Mobil|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – Katı, yetişkinlere yönelik içeriğe karşı en yüksek filtreleme<br /><br />**1** – Orta, yetişkinlere yönelik içeriğe karşı orta düzeyli filtreleme (geçerli arama sonuçları filtrelenmez)<br /><br />**Varsayılan değer:** 1|
|**Experience/AllowCopyPaste**|Mobil|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**Başlatmaya Zorlama Boyutu**|Mobil|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Start/ForceStartSize<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** - kullanıcı boyut değişikliğine izin ver<br /><br />**1** - tam olmayan ekranı zorla<br /><br />**2** - tam ekranı zorla<br /><br />**Varsayılan değer:** 0|
|**Update/RequireDeferUpgrade**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0**: Yükseltmeyi erteleme (geçerli dal olan CB’de kal)<br /><br />**1**: Güncelleştirme ve yükseltmelerin ertelenmesini etkinleştir (Cihaz, geçerli iş dalı olan CBB’nin kurallarına uyar)<br /><br />**Varsayılan değer: 0**<br /><br />Daha fazla bilgi için bkz.:<br /><br />[Windows 10 hizmetlerine giriş](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Windows 10 dağıtımını planlama](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/DeferUpdatePeriod**|Her İkisi|**Açıklama**: Yazılım güncelleştirmelerini 4 haftaya kadar erteleme ilkesi<br /><br />**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:** 0: Güncelleştirmeleri hemen uygula; 1-4: yazılım güncelleştirmelerinin erteleneceği hafta sayısı.<br /><br />**Varsayılan değer: 0**<br /><br /><br />Daha fazla bilgi için bkz.:<br /><br />[Windows 10 hizmetlerine giriş](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Windows 10 dağıtımını planlama](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/DeferUpgradePeriod**|Her İkisi|**Açıklama**: Özellik yükseltmelerini 8 aya kadar erteleme ilkesi<br /><br />**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:** 0: Yükseltmeleri hemen uygula; 1-8: özellik yükseltmelerinin erteleneceği ay sayısı.<br /><br />**Varsayılan değer: 0**<br /><br />Daha fazla bilgi için bkz.:<br /><br />[Windows 10 hizmetlerine giriş](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Windows 10 dağıtımını planlama](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/PauseDeferrals**|Her İkisi|**Açıklama**: Bir CBB makinesinin 5 hafta boyunca güncelleştirme ve yükseltme almayı durdurmasını sağlar. Bu, güncelleştirmelerin birinde sorun olması durumunda kullanılmalıdır.<br /><br />**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Update/PauseDeferrals<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0**: Güncelleştirmeleri hemen uygula (varsayılan)<br /><br />**1**: Güncelleştirmeleri ve yükseltmeleri duraklat (5 hafta sonra süresi dolar)<br /><br />**Varsayılan değer: 0**|

### Windows Defender

|İlke adı|Destekleyen|Ayrıntılar|
|---------------|------------|-----------|
|**AllowRealtimeMonitoring**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**AllowBehaviorMonitoring**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**AllowIntrusionPreventionSystem**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**AllowIOAVProtection**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**AllowScriptScanning**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**AllowOnAccessProtection**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**RealTimeScanDirection**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – Tüm dosyaları izle (çift yönlü)<br /><br />**1** – Gelen dosyaları izle<br /><br />**2** – Giden dosyaları izle<br /><br />**Varsayılan değer:** 0|
|**DaysToRetainCleanedMalware**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:0** - **90** – Kötü amaçlı yazılımın ne kadar süre tutulacağını belirtir<br /><br />**Varsayılan değer:** 0 – sonsuza kadar karantina klasöründe tutar ve otomatik olarak kaldırmaz|
|**AllowUserUIAccess**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**ScanParameter**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/ScanParameter<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**1** – Hızlı tarama<br /><br />**2** - Tam tarama<br /><br />**Varsayılan değer:** 1|
|**ScheduleScanDay**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** - Her gün<br /><br />**1** - Pazartesi<br /><br />**2** - Salı<br /><br />**3** - Çarşamba<br /><br />**4** - Perşembe<br /><br />**5** - Cuma<br /><br />**6** - Cumartesi<br /><br />**7** - Pazar<br /><br />**8** – Zamanlanmış tarama yok<br /><br />**Varsayılan değer:** 0|
|**ScheduleScanTime**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** - 12:00<br /><br />**60** – 1:00<br /><br />**120** – 2:00<br /><br />**180** – 3:00<br /><br />**240** – 4:00<br /><br />**300** – 5:00<br /><br />**360** – 6:00<br /><br />**420** – 7:00<br /><br />**480** – 8:00<br /><br />**540** – 9:00<br /><br />**600** – 10:00<br /><br />**660** – 11:00<br /><br />**720** – 12:00<br /><br />**780** – 13:00<br /><br />**840** – 14:00<br /><br />**900** – 15:00<br /><br />**960** – 16:00<br /><br />**1020** – 17:00<br /><br />**1080** – 18:00<br /><br />**1140** – 19:00<br /><br />**1200** – 20:00<br /><br />**1260** – 21:00<br /><br />**1320** – 22:00<br /><br />**1381** – Bakım penceresi<br /><br />**Varsayılan değer:** 120|
|**ScheduleQuickScanTime**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** - 12:00<br /><br />**60** – 1:00<br /><br />**120** – 2:00<br /><br />**180** – 3:00<br /><br />**240** – 4:00<br /><br />**300** – 5:00<br /><br />**360** – 6:00<br /><br />**420** – 7:00<br /><br />**480** – 8:00<br /><br />**540** – 9:00<br /><br />**600** – 10:00<br /><br />**660** – 11:00<br /><br />**720** – 12:00<br /><br />**780** – 13:00<br /><br />**840** – 14:00<br /><br />**900** – 15:00<br /><br />**960** – 16:00<br /><br />**1020** – 17:00<br /><br />**1080** – 18:00<br /><br />**1140** – 19:00<br /><br />**1200** – 20:00<br /><br />**1260** – 21:00<br /><br />**1320** – 22:00<br /><br />**1380** – 23:00<br /><br />**Varsayılan değer:** 120|
|**AVGCPULoadFactor**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:0** - **100**<br /><br />**Varsayılan değer:** 50|
|**AllowArchiveScanning**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**AllowEmailScanning**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 0|
|**AllowFullScanRemovableDriveScanning**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 0|
|**AllowFullScanOnMappedNetworkDrives**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**AllowScanningNetworkFiles**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1 – Ayrıca RTP açık olduğunda ve izin veriliyor olarak ayarlandığında çalıştırılır|
|**SignatureUpdateInterval**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – Bir aralıktaki imzaları denetleme<br /><br />**1** - Saatte bir imzaları denetle<br /><br />**2** – Her 2 saatte bir vb. imzaları denetle<br /><br />**24** – Her gün imzaları denetle<br /><br />**Varsayılan değer:** 8 – Her 8 saatte bir imzaları denetle|
|**AllowCloudProtection**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – izin verilmiyor<br /><br />**1** – izin veriliyor<br /><br />**Varsayılan değer:** 1|
|**SubmitSamplesConsent**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** – Her zaman sor<br /><br />**1** – Güvenli örnekleri otomatik olarak gönder<br /><br />**2** – Hiçbir zaman gönderme<br /><br />**3** – Tüm örnekleri otomatik olarak gönder<br /><br />**Varsayılan değer:** 0|
|**ExcludedExtensions**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions<br /><br />**Veri türü:** Dize<br /><br />**İzin verilen değerler:**<br /><br />*&lt;noktalı virgülle ayrılmış uzantılar listesi&gt;* Örn. **obj;lib**<br /><br />**Varsayılan değer:** Hiçbir uzantı dışlanmaz|
|**ExcludedPaths**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths<br /><br />**Veri türü:** Dize<br /><br />**İzin verilen değerler:**<br /><br />*&lt;noktalı virgülle ayrılmış yollar listesi&gt;*<br /><br />Örnek: **c:\test;c:\test1.exe**<br /><br />**Varsayılan değer:** Hiçbir yol dışlanmaz|
|**ExcludedProcesses**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses<br /><br />**Veri türü:** Dize<br /><br />**İzin verilen değerler:**<br /><br />*&lt;noktalı virgülle ayrılmış yollar listesi&gt;*<br /><br />Örnek: **c:\test.exe;c:\test1.exe**<br /><br />**Varsayılan değer:** Hiçbir işlem dışlanmaz|

### Edge tarayıcısı

|İlke adı|Destekleyen|Ayrıntılar|
|---------------|------------|-----------|
|**Tarayıcıya İzin Verme**|Mobil|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Browser/AllowBrowser<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:0**: göz atma kapalıdır; **1**: göz atma açıktır.<br /><br />**Varsayılan değer:** 1|
|**AllowSearchSuggestionsinAddressBar**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:0**: Arama önerilerini gösterme; **1**: Arama önerilerini göster.<br /><br />**Varsayılan değer:** 1|
|**SendIntranetTraffictoInternetExplorer**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:0**: Devre dışı (intranet sitelerini Edge tarayıcısında açın); **1** - Etkin (intranet sitelerini Internet Explorer’da açın).<br /><br />**Varsayılan değer:** 0|
|**Do Not Track’e İzin Verme**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:0** – Devre dışı (DNT gönderilmez);  **1** – Etkin (DNT gönderin)<br /><br />**Varsayılan değer:** 0|
|**SmartScreen’i Yapılandırma**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:0** – İzin verme;  **1** – İzin ver<br /><br />**Varsayılan değer:** 1|
|**Açılır Pencerelere İzin Verme**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Browser/AllowPopups<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:0** – Açılır pencereleri engelle; **1** – Açılır pencerelere izin ver<br /><br />**Varsayılan değer:** 0|
|**Tanımlama Bilgilerine İzin Verme**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Browser/AllowCookies<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:0** – Engelleme. Tüm web sitelerinden tanımlama bilgilerine izin ver; **1** – Yalnızca üçüncü taraf tanımlama bilgilerini engelle; **2** – Tüm tanımlama bilgilerini engelle<br /><br />**Varsayılan değer:** 0|
|**Parola Kaydetmeye İzin Verme**|Her İkisi|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:0** – Parola yöneticisi devre dışı; <br />                        **1** – Parola yöneticisi etkin<br /><br />**Varsayılan değer:** 1|
|**Otomatik Doldurma’ya izin ver**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Browser/AllowAutofill<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:0** – Devre dışı; **1** – Etkin<br /><br />**Varsayılan değer:** 0|
|**Enterprise Site Listesi Yapılandırma**|Masaüstü|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList<br /><br />**Veri türü:** Dize<br /><br />**İzin verilen değerler:0** – Yapılandırılmadı; **1** – Yapılandırıldıysa, IE’nin kuruluş modu site listesini kullan; **2** – Kuruluş site listesinin konumunu belirtin<br /><br />**Varsayılan değer:** 1|

### Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO1-->


