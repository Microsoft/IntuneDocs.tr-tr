---
title: "Windows 10 ilke ayarları | Microsoft Intune"
description: "Kayıtlı Windows 10 masaüstü bilgisayarları ve Windows 10 mobil cihazlarında yerleşik ve özel ayarları yapılandırmanıza yardımcı olması için, bu konu başlığı altında listelenen ilke ayarlarını kullanın."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/31/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0178bba517b0fc9e02ba67e6f3aba7a8a0ee445f
ms.openlocfilehash: 9daab32361cfdf8567d03a8ea6e6438e34b61aad


---

# Microsoft Intune’da Windows 10 ilke ayarları

Kayıtlı Windows 10 masaüstü bilgisayarları ve Windows 10 mobil cihazlarında yerleşik ve özel ayarları yapılandırmanıza yardımcı olması için, bu konu başlığı altında listelenen ilke ayarlarını kullanın.

> [!IMPORTANT]
> Windows 10 bilgisayarlarını iki yolla yönetebilirsiniz: bunları kaydederek veya Intune bilgisayar istemcisi yazılımını yükleyerek. Her yöntem farklı özellikler sunar. (Daha fazla bilgi için bkz. [Cihazların nasıl yönetileceğini seçme](/intune/get-started/choose-how-to-manage-devices).)
> Windows 10 bilgisayarlarınızı Intune bilgisayar istemcisi yazılımıyla yönettiğinizde, bu konu başlığı altında ayrıntıları verilen ilkeleri ve ayarları kullanamazsınız. Bu ayarların uygulanması için, Windows 10 cihazlarınızın Intune’a kayıtlı olması gerekir.

## Genel yapılandırma ilkesi ayarları

Kayıtlı Windows 10 masaüstü ve Windows 10 Mobile cihazların genel ayarlarını yapılandırmak isterseniz, Windows 10 için Microsoft Intune **genel yapılandırma ilkesini** kullanın. 


## - Parola

|Ayar adı|Ayrıntılar|
|----------------|----------------------|
|**Cihazların kilidini açmak için parola gerektir**|Desteklenen cihazlarda bir parola gerektir.|
|**Gerekli parola türü**|Gerekli parola türünü belirtir (yalnızca sayısal veya alfasayısal gibi).|
|**Gerekli parola türü** - **Minimum karakter kümesi sayısı**|Küçük harfler, büyük harfler, rakamlar ve semboller şeklinde dört karakter kümesi vardır. Bu ayar parolanın kaç farklı karakter kümesi içermesi gerektiğini belirtir.|
|**Minimum parola uzunluğu**|Cihaz parolasının içermesi gereken minimum karakter sayısını belirtir.<br>(Yalnızca Windows 10 Mobile)|
|**Cihaz temizlenmeden önce izin verilen yinelenen oturum açma hatası sayısı**|Bu sayıda oturum açma denemesi başarısız olursa cihazı temizler.|
|**Ekran kapanmadan önce geçen işlem yapılmayan dakika sayısı**|Ekran kilitlenmeden önce cihazın boşta bekleyeceği süreyi belirtir.|
|**Parola geçerlilik süresi (gün)**|Cihaz parolasının ne kadar süre sonra değiştirilmesi gerektiğini belirtir.|
|**Parola geçmişini anımsa**|Son kullanıcının daha önce kullanılmış parolalar oluşturmasını kısıtlamak isteyip istemediğinizi belirtir.|
|**Parola geçmişini anımsa** - **Önceki parolaların yeniden kullanılmasını önle**|Önceden kullanılmış ve cihaz tarafından anımsanacak olan parola sayısını belirtir.|
|**Cihaz boş bir durumdan döndürüldüğünde parola iste**|Etkinleştirilirse, boşta durumundaki bir cihazın kilidini açmak için kullanıcının parola girmesi gerekir.<br>(Yalnızca Windows 10 Mobile)|

## - Şifreleme

|Ayar adı|Ayrıntılar|
|----------------|----------------------|
|**Cihazda şifrelemeyi gerektir**|Hedeflenen cihazlarda şifrelemeyi etkinleştirir.<br>(Yalnızca Windows 10 Mobile)|

## - Sistem

|Ayar adı|Ayrıntılar|
|----------------|----------------------|
|**Ekran yakalamaya izin ver**|Kullanıcının cihaz ekranını bir resim olarak yakalamasına olanak sağlar.<br>(Yalnızca Windows 10 Mobile)|
|**Elle kayıt kaldırmaya izin ver**|Kullanıcının iş yeri hesabını cihazdan el ile silmesine olanak sağlar.|
|**Elle kök sertifikası yüklemeye izin ver**|Kullanıcının elle kök sertifika yükleyip yükleyemeyeceğini belirtir.<br>(Yalnızca Windows 10 Mobile)|
|**Microsoft'a tanılama ve kullanım verilerinin gönderilmesine izin ver**|Cihazlardan Microsoft’a gönderilecek tanılama ve kullanım verilerinin miktarını belirler.<br><br>**Hayır** - Microsoft’a hiç veri gönderilmez<br>**Temel** -Cihaz Microsoft’a yalnızca sınırlı miktarda bilgi gönderir.<br>**Gelişmiş** - Microsoft’a gelişmiş tanılama bilgileri gönderilir<br>**Tam (önerilen)** - **Gelişmiş** ayarıyla aynı veriler, artı olarak cihazın durumuyla ilgili ek veriler gönderilir|


## - Hesap ve eşitleme

|Ayar adı|Ayrıntılar|
|----------------|----------------------|---------------------|
|**Microsoft Hesabına izin ver**|Kullanıcının bir Microsoft hesabını cihazla ilişkilendirmesine olanak sağlar.|
|**Microsoft olmayan hesapların elle eklenmesine izin ver**|Kullanıcının cihaza bir Microsoft hesabıyla ilişkilendirilmemiş e-posta hesapları eklemesine olanak sağlar.|
|**Microsoft hesapları için ayarları eşitlemeye izin ver**|Microsoft hesabıyla ilişkilendirilmiş cihaz ve uygulama ayarlarının cihazlar arasında eşitlenmesine izin verin.|

## - Microsoft Edge

|Ayar adı|Ayrıntılar|
|----------------|----------------------|
|**Web tarayıcısına izin ver**|Cihazda Microsoft Edge web tarayıcısının kullanılmasına izin verin.<br>(Yalnızca Windows 10 Mobile)|
|**Adres çubuğunda arama önerilerine izin ver**|Siz arama tümcecikleri yazarken arama motorunuzun site önerilerinde bulunmasına olanak sağlar.|
|**Internet Explorer'a intranet trafiği göndermeye izin ver**|Kullanıcıların Internet Explorer’da intranet web siteleri açmasına olanak sağlar.<br>(Yalnızca Windows 10 masaüstü)|
|**İzleme özelliğine izin ver**|Microsoft Edge tarayıcısını, kullanıcıların ziyaret ettiği web sitelerine Do Not Track (İzleme) üst bilgileri gönderecek şekilde yapılandırır.|
|**SmartScreen’i etkinleştir**|Cihazlarda SmartScreen tarayıcı ayarını etkinleştirir.|
|**Etkin betik yazmaya izin ver**|Microsoft Edge tarayıcısında Javascript gibi betiklerin çalıştırılmasına izin verir.|
|**Açılır pencerelere izin ver**|Açılır pencere engelleyicisini etkinleştirir veya devre dışı bırakır.<br>(Yalnızca Windows 10 masaüstü)|
|**Tanımlama bilgilerine izin ver**|Tanımlama bilgilerine izin verin veya bunları devre dışı bırakın.|
|**Otomatik Doldurma’ya izin ver**|Kullanıcıların tarayıcıdaki otomatik tamamlama ayarlarını değiştirmesine izin verin.<br>(Yalnızca Windows 10 masaüstü)|
|**Parola Yöneticisi’ne izin ver**|Microsoft Edge Parola Yöneticisi özelliğini etkinleştirin veya devre dışı bırakın.|
|**Kurumsal Mod site listesi konumu**|Kurumsal modda açılacak web siteleri listesinin nerede olduğunu belirtir. Kullanıcılar bu listeyi düzenleyemez.<br>(Yalnızca Windows 10 masaüstü)|

## - Uygulamalar

|Ayar adı|Ayrıntılar|
|----------------|----------------------|---------------------|
|**Uygulama depolamaya izin ver**|Kullanıcının cihazda uygulama mağazasına erişmesine izin verin.<br>(Yalnızca Windows 10 Mobile)|



## - Hücresel

|Ayar adı|Ayrıntılar|
|----------------|----------------------|---------------------|
|**Veri dolaşımına izin ver**|Verilere erişirken ağlar arasında dolaşıma izin verin.|
|**Hücresel veri üzerinden VPN'ye izin ver**|Cihazın cep telefonu şebekesine bağlandığında VPN bağlantılarına erişip erişemeyeceğini denetler.|
|**Hücresel veri üzerinden VPN dolaşımına izin ver**|Cihazın cep telefonu şebekesinde dolaşımı sırasında VPN bağlantılarına erişip erişemeyeceğini denetler.|

## - Donanım

|Ayar adı|Ayrıntılar|
|----------------|----------------------|
|**Kameraya izin ver**|Cihaz kamerasının kullanılıp kullanılamayacağını belirtir.|
|**Çıkarılabilir depolama birimine izin ver**|Cihazla birlikte SD kartı gibi dış depolama cihazlarının kullanılıp kullanılamayacağını belirtir.|
|**Wi-Fi'a izin ver**|Cihazın Wi-Fi özelliğinin kullanımına izin verir.<br>(Yalnızca Windows 10 Mobile)|
|**İnternet paylaşımına izin ver**|Cihazda İnternet bağlantısı paylaşımının kullanımına izin verin.|
|**Elle Wi-Fi yapılandırmasına izin ver**|Kullanıcının kendi Wi-Fi bağlantılarını yapılandırıp yapılandıramayacağını veya yalnızca Wi-Fi profili tarafından yapılandırılan bağlantıları kullanıp kullanamayacağını denetleyin.<br>(Yalnızca Windows 10 Mobile)|
|**Ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmaya izin ver**|Cihazın ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmasına ve bağlantıyla ilgili hüküm ve koşulları otomatik olarak kabul etmesine olanak sağlar.|
|**Coğrafi konuma izin ver**|Cihazın konum hizmetleri bilgilerini kullanıp kullanamayacağını belirtir.|
|**NFC'ye izin ver**|Cihazın Yakın Alan İletişimi özelliklerini kullanmasına izin verir.|
|**Bluetooth'a izin ver**|Cihazda Bluetooth özelliklerinin kullanılmasına izin verir.|
|**Bluetooth bulunabilirlik moduna izin ver**|Bu cihazın diğer Bluetooth özellikli cihazlar tarafından bulunabilmesine olanak sağlar.|
|**Bluetooth reklamlarına izin ver**|Cihazların Bluetooth üzerinden reklam almasına izin verir.|
|**Telefon sıfırlamaya izin ver**|Kullanıcının cihazını fabrika ayarlarına sıfırlayıp sıfırlayamayacağını denetler.|
|**USB bağlantısına izin ver**|Cihazların USB bağlantısı aracılığıyla dış depolama cihazlarına erişip erişemeyeceğini denetler.|
|**AntiTheft modunu etkinleştir**|Windows AntiTheft modunun etkin olup olmadığını yapılandırın.|

## - Özellikler

|Ayar adı|Ayrıntılar|
|----------------|----------------------|---------------------|
|**Kopyalama ve yapıştırmaya izin ver**|Cihazda kopyalama ve yapıştırmanın kullanımını etkinleştirin veya devre dışı bırakın.<br>(Yalnızca Windows 10 Mobile)|
|**Ses kaydetmeye izin ver**|Cihazda ses kayıt özelliklerinin kullanımını etkinleştirin veya devre dışı bırakın.<br>(Yalnızca Windows 10 Mobile)|
|**Cortana’ya izin ver**|Cortana sesli yardımcısını etkinleştirin veya devre dışı bırakın.|
|**İşlem merkezi bildirimlerine izin ver**|Cihaz kilit ekranında işlem merkezi bildirimlerini etkinleştirin veya devre dışı bırakın.<br>(Yalnızca Windows 10 Mobile)|

## - Windows Defender

Tüm ayarlar yalnızca Windows 10 masaüstüne yöneliktir.

|Ayar adı|Ayrıntılar|
|-|-|
|**Gerçek zamanlı izlemeye izin ver**|Kötü amaçlı yazılım, casus yazılım ve istenmeyen diğer yazılımlar için gerçek zamanlı taramaya izin verir.|
|**Davranış izlemeye izin ver**|Defender’ın cihazlarda bilinen şüpheli etkinlik düzenlerini denetlemesine olanak sağlar.|
|**Ağ Denetleme Sistemi'ni Etkinleştir**|Ağ İnceleme Sistemi (NIS), kötü amaçlı trafiğin algılanmasına ve engellenmesine katkıda bulunmak için Microsoft Endpoint Protection Center’dan gelen bilinen güvenlik açıklarının imzalarını kullanarak ağ tabanlı saldırılara karşı korunmaya yardımcı olur.|
|**Tüm indirmeleri tara**|Defender’ın İnternet’ten indirilen tüm dosyaları tarayıp taramayacağını denetler.|
|**Betik taramaya izin ver**|Defender’ın Internet Explorer’da kullanılan betikleri taramasına olanak sağlar.|
|**Dosya ve program etkinliğini izle**|Defender’ın cihazlarda dosya ve program etkinliğini izlemesine izin vermek için bu ayarı etkinleştirin.|
|**Çözümlenen kötü amaçlı yazılımın izleneceği gün sayısı**|Defender’ın çözümlenen kötü amaçlı yazılımı belirttiğiniz sayıda gün boyunca izlemeye devam etmesine olanak sağlar; böylece daha önce etkilenmiş olan cihazları el ile denetleyebilirsiniz. Gün sayısını **0** olarak ayarlarsanız, kötü amaçlı yazılım Karantina klasöründe kalır ve otomatik olarak kaldırılmaz. |
|**İstemci UI erişimine izin ver**|Windows Defender kullanıcı arabiriminin son kullanıcılardan gizlenip gizlenmediğini denetler.<br>Bu ayar değiştirildiğinde, son kullanıcının bilgisayarı bir sonraki yeniden başlatmasında geçerlilik kazanır.|
|**Günlük hızlı tarama zamanla**|Her gün seçtiğiniz saatte gerçekleştirilecek olan bir hızlı tarama zamanlamanıza olanak sağlar.|
|**Sistem taraması zamanla**|Seçtiğiniz gün ve saatte düzenli olarak gerçekleştirilecek tam veya hızlı bir sistem taraması zamanlamanıza olanak sağlar.|
|**Tarama sırasında CPU kullanımını sınırla**|Taramaların kullanmasına izin verilecek CPU miktarını sınırlandırmanıza (**1** ile **100** arasında) olanak sağlar|
|**Arşiv dosyalarını tara**|Defender’ın Zip veya Cab dosyaları gibi arşivlenmiş dosyaları taramasına izin verir.|
|**E-posta iletilerini tara**|Defender’ın cihaza gelen e-posta iletilerini taramasına izin verir.|
|**Çıkarılabilir sürücüleri tara**|Defender’ın USB çubukları gibi çıkarılabilir sürücüleri taramasına olanak sağlar.|
|**Eşlenen ağ sürücülerini tara**|Defender’ın eşlenen ağ sürücüsündeki dosyaları taramasına olanak sağlar.<br>Sürücüdeki dosyalar salt okunur olduğunda, Defender bunların içinde bulduğu kötü amaçlı yazılımları kaldıramaz.|
|**Paylaşılan ağ klasörlerinden açılan dosyaları tara**|Defender’ın paylaşılan ağ sürücülerindeki dosyaları (örneğin UNC yolundan erişilenler) taramasına olanak sağlar.<br>Sürücüdeki dosyalar salt okunur olduğunda, Defender bunların içinde bulduğu kötü amaçlı yazılımları kaldıramaz.|
|**İmza güncelleştirme aralığı**|Defender’ın yeni imza dosyalarını denetleme aralığını belirtin.|
|**Bulut korumasına izin ver**|Microsoft Etkin Koruma Hizmeti’nin yönettiğiniz cihazlardan kötü amaçlı yazılım etkinliğiyle ilgili bilgi almasına izin verin veya bunu engelleyin. Bu bilgi gelecekte hizmeti geliştirmek için kullanılır.|
|**Kullanıcılardan örnek göndermelerini iste**|Kötü amaçlı olup olmadıklarını saptamak için Microsoft tarafından daha fazla çözümlenmesi gerekebilecek dosyaların Microsoft’a otomatik olarak gönderilip gönderilmeyeceğini denetler.|
|**Olası İstenmeyen Uygulama Algılama**|Bu ayar, kayıtlı Windows masaüstü cihazlarını, Windows Defender tarafından olası istenmeyen yazılım şeklinde sınıflandırılan yazılımları çalıştırmaya karşı korumak üzere kullanılabilir. Bu uygulamaların çalıştırılmasına karşı koruma sağlayabilir veya istenmeyebilecek bir uygulama yüklendiğinde raporlanması için denetim modunu kullanabilirsiniz.|
|**Bir tarama çalıştırılırken veya gerçek zamanlı koruma kullanılırken dışlanacak dosya ve klasörler**|Dışlama listesinde **C:\Yol** veya **%ProgramFiles%\Yol\dosyaadı.exe** gibi bir veya birden çok dosya ve klasör ekleyin. Bu dosya ve klasörler gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.|
|**Bir tarama çalıştırılırken veya gerçek zamanlı koruma kullanılırken dışlanacak dosya uzantıları**|Dışlama listesine **jpg** veya **txt** gibi bir veya birden çok dosya uzantısı ekleyin. Bu uzantıya sahip dosyaların hiçbiri gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.|
|**Bir tarama çalıştırılırken veya gerçek zamanlı koruma kullanılırken dışlanacak işlemler**|Dışlama listesine **.exe**, **.com** veya **.scr** türünde bir veya birden çok işlem ekleyin. Bu işlemler gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.| 


## - Güncelleştirmeler

|Ayar adı|Ayrıntılar|
|----------------|---------------|
|**Otomatik güncelleştirmelere izin ver**|Otomatik güncelleştirmelere izin vermek bu ayarı etkinleştirin. Ardından, güncelleştirme davranışını denetlemek için aşağıdaki ayarlardan birini yapılandırın:<br /><br />**İndirmeyi bildir**<br /><br />**Bakım sırasında otomatik olarak yükle**<br /><br />**Bakım sırasında otomatik olarak yükle ve yeniden başlat**<br /><br />**Zamanlanan tarihte otomatik yükle ve yeniden başlat** **Not:** Bu seçenek belirtildiğinde şu ayarları yapılandırabilirsiniz: **Son kullanıcıya bildirimi önle** ve **Zamanlanmış güncelleştirmeler için yükleme gününü tanımla**.<br>(Yalnızca Windows 10 masaüstü)|
|**Yayın öncesi özelliklere izin ver**|Microsoft’un Windows 10 cihazlara sürüm öncesi ayarlar ve özellikler dağıtmasına imkan tanır. Yalnızca ayarlara izin vermeyi tercih edebilirsiniz; aksi takdirde tüm sürüm öncesi ayarlar ve özellikler yüklenir.|

## Özel ilke ayarları
Windows 10 ve Windows 10 Mobile cihazlarındaki özellikleri denetlemek için kullanılabilen OMA-URI (Open Mobile Alliance Tekdüzen Kaynak Tanımlayıcısı) ayarlarını dağıtmak üzere Windows 10 ve Windows 10 Mobile cihazları için Microsoft Intune **özel yapılandırma ilkesini** kullanın. Bunlar, birçok mobil cihaz üreticisinin, cihaz özelliklerini denetlemek için kullandığı standart ayarlardır.

Bu özellik, Intune genel yapılandırma ilkesiyle, yapılandırılabilir olmayan Windows 10 ayarlarını dağıtmanıza olanak sağlamak için tasarlanmıştır.



## - Genel

|Ayar adı|Ayrıntılar|
    |----------------|--------------------|
    |**Ad**|Intune konsolunda tanımanıza yardımcı olması için benzersiz bir ad girin.|
    |**Açıklama**|İlkeye genel bir bakış ve ilkeyi bulmanıza yardımcı olacak diğer ek bilgileri içeren bir açıklama sağlayın.|

## - OMA-URI ayarları

|Ayar adı|Ayrıntılar|
    |--------|--------------------|
    |**Ayar adı**|Ayarlar listesinde tanımanıza yardımcı olması için OMA-URI ayarı için benzersiz bir ad girin.|
    |**Ayar açıklaması**|Ayara genel bir bakış ve ayarı bulmanıza yardımcı olacak diğer ek bilgileri içeren bir açıklama sağlayın.|
    |**Veri türü**|Bu OMA-URI ayarını belirteceğiniz tarih türünü seçin. Aşağıdakilerden birini seçin:<br /><br />-   **Dize**<br />-   **Dize (XML)**<br />-   **Tarih ve saat**<br />-   **Tamsayı**<br />-   **Kayan nokta**<br />-   **Boole değeri**|
    |**OMA-URI (büyük küçük harf duyarlı)**|Bir ayar için sağlamak istediğiniz OMA-URI’yi belirtin.|
    |**Değer**|Önceden belirttiğiniz OMA-URI ile ilişkilendirilecek değeri belirtin.|


## Windows 10 URI ayarları
Bu konu başlığı altında, Microsoft Intune **Windows 10 Özel İlkesi**’nde Windows 10 ve Windows 10 Mobile cihazları için yapılandırabileceğiniz ayarlar listelenir.

Windows Özel URI İlkesini kullanmak istiyorsanız tüm cihazlar Intune’a kaydedilmelidir.

## - İlke

|İlke adı|Ayrıntılar|
|---------------|------------|-----------|
|**​Otomatik Güncelleştirmeye İzin Ver**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** - **5** (varsayılan: **1**)|
|**Yükleme Gününü Zamanlama**<br>(yalnızca mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** - Her gün (varsayılan)<br>**1** - Pazar<br>**2** - Pazartesi<br>**3** - Salı<br>**4** - Çarşamba<br>**5** - Perşembe<br>**6** - Cuma<br>**7** - Cumartesi|
|**Yükleme Saatini Zamanlama**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – **23** saat (**0**, gece yarısıdır) (varsayılan: **3**)|
|**DeviceLock/AllowIdleReturnWithoutPassword**<br>(yalnızca mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** - kullanıcı, parola yetkisiz kullanım süresi zamanlayıcısını ayarlayamaz ve değer, “her defasında” olarak ayarlanır<br>**1** - kullanıcı, parola yetkisiz kullanım süresi zamanlayıcısını ayarlayabilir (varsayılan)|
|**WiFi/AllowWiFi**<br>(yalnızca mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – **Wi-Fi bağlantısı kullanılmasına** izin verme.<br>**1** –**Wi-Fi bağlantısı kullanılmasına izin ver** (varsayılan)|
|**WiFi/AllowInternetSharing**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – İnternet paylaşımına izin verme.<br>**1** – İnternet Paylaşımına izin ver (varsayılan)|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**WiFi/AllowManualWiFiConfiguration**<br>(yalnızca mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – MDM tarafından sağlanan dışında bir Wi-Fi bağlantısına izin verilmez.<br>**1** – Önceden MDM tarafından sağlananlar dışında yeni ağ SSID’leri eklenmesine izin verilir (varsayılan)|
|**System/AllowLocation**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/System/AllowLocation<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**System/AllowTelemetry**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/System/AllowTelemetry<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – İzin verilmiyor (yalnızca Kurumsal)<br>**1** – Sınırlı<br>**2** – Tam (varsayılan)<br>**3** - Tam ve tanılama bilgileri|
|**System/AllowExperimentation**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/System/AllowExperimentation<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – İzin verilmiyor<br>**1**- Yalnızca ayarlar (varsayılan)<br>**2**- Ayarlar ve deneme|
|**Security/AntiTheftMode**<br>(yalnızca mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Security/AntiTheftMode<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** - Hırsızlık Önleme moduna izin verme<br>**1** Kullanıcı tercihi (varsayılan)|
|**Connectivity/AllowUSBConnection**<br>(yalnızca mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**System/AllowUserToResetPhone**<br>(yalnızca mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Connectivity/AllowCellularDataRoaming**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Connectivity/AllowVPNOverCellular**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** - Hücresel şebeke üzerinden VPN’ye izin verilmez<br>**1** – VPN, hücresel şebeke de dahil tüm bağlantıları kullanır (varsayılan)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>(yalnızca mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>(yalnızca mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Connectivity/AllowBluetooth**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – Kullanıcının Bluetooth’u açmasına izin verilmez.<br>**1** – Ayrılmış. Kullanıcı Bluetooth’u açabilir ve yapılandırabilir (MDM için Windows Phone 8.1, EAS, Windows 10 masaüstü veya Windows 10 Mobile’da desteklenmez)<br>**2** - İzin verilir. Kullanıcı Bluetooth’u açabilir ve yapılandırabilir (varsayılan)|
|**Experience/AllowScreenCapture**<br>(yalnızca mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Experience/AllowTaskSwitcher**<br>(yalnızca mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Experience/AllowVoiceRecording**<br>(yalnızca mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Experience/AllowSyncMySettings**<br>(yalnızca mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – Dolaşıma izin verme<br>**1** – Dolaşıma izin ver (varsayılan)|
|**Experience/AllowManualMDMUnenrollment**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Accounts/AllowMicrosoftAccountConnection**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Security/AllowManualRootCertificateInstallation**<br>(yalnızca mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Security/AllowAddProvisioningPackages**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Search/DisableBackoff**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Search/DisableBackoff<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** (varsayılan)<br>**1**|
|**Search/PreventRemoteQueries**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0**<br>**1** (varsayılan)|
|**Search/AllowUsingDiacritics**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br> **0** (varsayılan)<br>**1**|
|**Search/AlwaysUseAutoLangDetection**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** (varsayılan)<br>**1**|
|**Search/DisableRemovableDriveIndexing**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** (varsayılan)<br>**1**|
|**Search/PreventIndexingLowDiskSpaceMB**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0**<br>**1** (varsayılan)|
|**Search/AllowIndexingEncryptedStoresOrItems**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** (varsayılan)<br>**1**|
|**Security/AllowRemoveProvisioningPackage**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Security/RequireProvisioningPackageSignature**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** (varsayılan)<br>**1**|
|**AboveLock/AllowActionCenterNotifications**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**TextInput/AllowIMENetworkAccess**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – İzin verme<br>Açık Genişletilmiş Sözlük kapalıdır.<br>Kullanıcı şunları yapamaz:<br>Yeni bir Açık Genişletilmiş Sözlük ekleme<br /><br />Yeni bir arama tümleştirme yapılandırma dosyası ekleme<br>Bulut aday özelliğini kullanma<br>Kullanıcı tarafından kaydedilen sözcüğü gönderme<br>Ek olarak:<br>Bu ilke ayarı etkinleştirilmeden önce eklenen bir Açık Genişletilmiş Sözlük, dönüştürme için kullanılmaz.<br>Bu ilke ayarı etkinleştirilmeden önce yüklenen bir arama tümleştirme yapılandırması kullanılmaz.<br>**1** - İzin ver<br>Açık Genişletilmiş Sözlük eklenebilir ve varsayılan olarak kullanılabilir. Ayrıca, arama tümleştirme işlevi varsayılan olarak kullanılabilir.<br>Kullanıcı şunları yapabilir:<br>Bulut aday özelliğini kullanma<br>Kullanıcı tarafından kaydedilen sözcüğü gönderme.|
|**TextInput/AllowIMELogging**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** - Hatalı dönüştürme günlüğü kapalıdır. Otomatik olarak ayarlanmış veriler ve giriş geçmişi verileri bir dosyaya kaydedilmez.<br>**1** - Hatalı dönüştürme günlüğü açıktır. Otomatik olarak ayarlanmış veriler ve giriş geçmişi verileri bir dosyaya kaydedilir (varsayılan)|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**TextInput/AllowJapaneseIVSCharacters**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**TextInput/AllowJapaneseUserDictionary**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** - Hiçbir karakter filtrelenmez (varsayılan)<br>**1** - Shift JIS karakterleri dışında tümü filtrelenir|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br /><br />**0** - Hiçbir karakter filtrelenmez (varsayılan)<br>**1** - JIS0208 karakterleri dışında tümü filtrelenir|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** - Hiçbir karakter filtrelenmez (varsayılan)<br>**1** - JIS0208 karakterleri veya EUDC karakterleri dışında tümü filtrelenir|
|**TextInput/AllowInputPanel**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Bluetooth/AllowDiscoverableMode**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Bluetooth/AllowAdvertising**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Settings/AllowDataSense**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Settings/AllowDataSense<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Settings/AllowVPN**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Settings/AllowVPN<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Settings/AllowWorkplace**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Settings/AllowDateTime**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Settings/AllowDateTime<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Settings/AllowLanguage**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Settings/AllowLanguage<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Settings/AllowRegion**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Settings/AllowRegion<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Settings/AllowSignInOptions**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Settings/AllowYourAccount**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Settings/AllowPowerSleep**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Settings/AllowAutoPlay**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Experience/AllowCortana**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Experience/AllowCortana<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Search/SafeSearchPermissions**<br>(yalnızca mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – Katı, yetişkinlere yönelik içeriğe karşı en yüksek filtreleme<br>**1** – Orta, yetişkinlere yönelik içeriğe karşı orta düzeyli filtreleme (geçerli arama sonuçları filtrelenmez - varsayılan)|
|**Experience/AllowCopyPaste**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**Başlatmaya Zorlama Boyutu**<br>(yalnızca mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Start/ForceStartSize<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** - kullanıcı boyut değişikliğine izin ver (varsayılan)<br>**1** - tam olmayan ekranı zorla<br>**2** - tam ekranı zorla|
|**Update/RequireDeferUpgrade**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0**: Yükseltmeyi erteleme (geçerli dal olan CB’de kal - varsayılan)<br>**1**: Güncelleştirme ve yükseltmelerin ertelenmesini etkinleştir (Cihaz, geçerli iş dalı olan CBB’nin kurallarına uyar)<br /><br />Daha fazla bilgi için bkz.:<br>[Windows 10 hizmetlerine giriş](https://technet.microsoft.com/library/mt598226.aspx)<br>[Windows 10 dağıtımını planlama](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>(masaüstü ve mobil)|**Açıklama**: Yazılım güncelleştirmelerini 4 haftaya kadar erteleme ilkesi<br /><br />**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br> **0**: Güncelleştirmeleri hemen uygula (varsayılan)<br>**1**-**4**: Yazılım güncelleştirmelerinin erteleneceği hafta sayısı.<br /><br />Daha fazla bilgi için bkz.:<br>[Windows 10 hizmetlerine giriş](https://technet.microsoft.com/library/mt598226.aspx)<br>[Windows 10 dağıtımını planlama](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>(masaüstü ve mobil)|**Açıklama**: Özellik yükseltmelerini 8 aya kadar erteleme ilkesi<br /><br />**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0**: Güncelleştirmeleri hemen uygula (varsayılan)<br>**1**-**8**: Özellik yükseltmelerinin erteleneceği ay sayısı.<br /><br />Daha fazla bilgi için bkz.:<br>[Windows 10 hizmetlerine giriş](https://technet.microsoft.com/library/mt598226.aspx)<br>[Windows 10 dağıtımını planlama](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>(masaüstü ve mobil)|**Açıklama**: Bir CBB makinesinin 5 hafta boyunca güncelleştirme ve yükseltme almayı durdurmasını sağlar. Bu, güncelleştirmelerin birinde sorun olması durumunda kullanılmalıdır.<br /><br />**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Update/PauseDeferrals<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0**: Güncelleştirmeleri hemen uygula (varsayılan)<br>**1**: Güncelleştirmeleri ve yükseltmeleri duraklat (5 hafta sonra süresi dolar)|

## - Windows Defender

|İlke adı|Ayrıntılar|
|---------------|-----------|
|**AllowRealtimeMonitoring**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**AllowBehaviorMonitoring**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**AllowIntrusionPreventionSystem**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**AllowIOAVProtection**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**AllowScriptScanning**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**AllowOnAccessProtection**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**RealTimeScanDirection**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – Tüm dosyaları izle (çift yönlü - varsayılan)<br>**1** – Gelen dosyaları izle<br>**2** – Giden dosyaları izle|
|**DaysToRetainCleanedMalware**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** - **90** – Kötü amaçlı yazılımın ne kadar süre tutulacağını belirtir<br>**Varsayılan değer:** **0** – sonsuza kadar karantina klasöründe tutar ve otomatik olarak kaldırmaz|
|**AllowUserUIAccess**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**ScanParameter**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/ScanParameter<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**1** – Hızlı tarama (varsayılan)<br>**2** - Tam tarama|
|**ScheduleScanDay**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** - Her gün (varsayılan)<br>**1** - Pazartesi<br>**2** - Salı<br>**3** - Çarşamba<br>**4** - Perşembe<br>**5** - Cuma<br>**6** - Cumartesi<br>**7** - Pazar<br>**8** – Zamanlanmış tarama yok|
|**ScheduleScanTime**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** - 12:00<br>**60** – 1:00<br>**120** – 2:00 (varsayılan)<br>**180** – 3:00<br>**240** – 4:00<br>**300** – 5:00<br>**360** – 6:00<br>**420** – 7:00<br>**480** – 8:00<br>**540** – 9:00<br>**600** – 10:00<br>**660** – 11:00<br>**720** – 12:00<br>**780** – 13:00<br>**840** – 14:00<br>**900** – 15:00<br>**960** – 16:00<br>**1020** – 17:00<br>**1080** – 18:00<br>**1140** – 19:00<br>**1200** – 20:00<br>**1260** – 21:00<br>**1320** – 22:00<br>**1381** – Bakım penceresi|
|**ScheduleQuickScanTime**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime<br>**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** - 12:00<br>**60** – 1:00<br>**120** – 2:00 (varsayılan)<br>**180** – 3:00<br>**240** – 4:00<br>**300** – 5:00<br>**360** – 6:00<br>**420** – 7:00<br>**480** – 8:00<br>**540** – 9:00<br>**600** – 10:00<br>**660** – 11:00<br>**720** – 12:00<br>**780** – 13:00<br>**840** – 14:00<br>**900** – 15:00<br>**960** – 16:00<br>**1020** – 17:00<br>**1080** – 18:00<br>**1140** – 19:00<br>**1200** – 20:00<br>**1260** – 21:00<br>**1320** – 22:00<br>**1380** – 23:00|
|**AVGCPULoadFactor**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:0** - **100** (varsayılan: **50**)|
|**AllowArchiveScanning**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**AllowEmailScanning**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning<br /><br />**Veri türü:** Tamsayı<br>**İzin verilen değerler:**<br>**0** – izin verilmiyor (varsayılan)<br>**1** – izin veriliyor|
|**AllowFullScanRemovableDriveScanning**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor (varsayılan)<br>**1** – izin veriliyor|
|**AllowFullScanOnMappedNetworkDrives**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**AllowScanningNetworkFiles**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan) - Ayrıca RTP açık olduğunda ve izin veriliyor olarak ayarlandığında çalıştırılır|
|**SignatureUpdateInterval**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – Bir aralıktaki imzaları denetleme<br>**1** - Saatte bir imzaları denetle<br>**2** – Her 2 saatte bir vb. imzaları denetle<br>**24** – Her gün imzaları denetle<br>**Varsayılan değer:** 8 – Her 8 saatte bir imzaları denetle|
|**AllowCloudProtection**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – izin verilmiyor<br>**1** – izin veriliyor (varsayılan)|
|**SubmitSamplesConsent**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – Her zaman sor (varsayılan)<br>**1** – Güvenli örnekleri otomatik olarak gönder<br>**2** – Hiçbir zaman gönderme<br>**3** – Tüm örnekleri otomatik olarak gönder|
|**ExcludedExtensions**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions<br /><br />**Veri türü:** Dize<br /><br />**İzin verilen değerler:**<br>*&lt;noktalı virgülle ayrılmış uzantılar listesi&gt;* Örn. **obj;lib**<br>**Varsayılan:** Hiçbir uzantı dışlanmaz|
|**ExcludedPaths**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths<br /><br />**Veri türü:** Dize<br /><br />**İzin verilen değerler:**<br /><br />*&lt;noktalı virgülle ayrılmış yollar listesi&gt;*<br /><br />Örnek: **c:\test;c:\test1.exe**<br /><br />**Varsayılan değer:** Hiçbir yol dışlanmaz|
|**ExcludedProcesses**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses<br /><br />**Veri türü:** Dize<br /><br />**İzin verilen değerler:**<br>*&lt;noktalı virgülle ayrılmış yollar listesi&gt;*<br>Örnek: **c:\test.exe;c:\test1.exe**<br>**Varsayılan değer:** Hiçbir işlem dışlanmaz|

## - Edge tarayıcı

|İlke adı|Ayrıntılar|
|---------------|------------|-----------|
|**Tarayıcıya İzin Verme**<br>(yalnızca mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Browser/AllowBrowser<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0**: tarama kapalı<br>**1**: tarama açık (varsayılan)|
|**AllowSearchSuggestionsinAddressBar**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0**: – Arama önerileri gösterme<br>**1**: Arama önerileri göster (varsayılan)|
|**SendIntranetTraffictoInternetExplorer**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0**: Devre dışı (intranet sitelerini Microsoft Edge tarayıcısında aç - varsayılan)<br>**1**: Etkin (intranet sitelerini Internet Explorer'da aç).|
|**Do Not Track’e İzin Verme**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – Devre dışı (DNT gönderilmez - varsayılan)<br>**1** – Etkin (DNT gönder)|
|**SmartScreen’i Yapılandırma**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – İzin verme<br>**1** – İzin ver (varsayılan)|
|**Açılır Pencerelere İzin Ver**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Browser/AllowPopups<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – Açılır pencereleri engelle (varsayılan)<br>**1** – Açılır pencerelere izin ver|
|**Tanımlama Bilgilerine İzin Verme**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Browser/AllowCookies<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – Engelleme. Tüm web sitelerinin tanımlama bilgilerine izin ver (varsayılan)<br>**1** – Yalnızca üçüncü taraf tanımlama bilgilerini engelle<br>**2** – Tüm tanımlama bilgilerini engelle|
|**Parola Kaydetmeye İzin Verme**<br>(masaüstü ve mobil)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – Parola yöneticisi devre dışı; <br>**1** – Parola yöneticisi etkin (varsayılan)|
|**Otomatik Doldurma’ya izin ver**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Browser/AllowAutofill<br /><br />**Veri türü:** Tamsayı<br /><br />**İzin verilen değerler:**<br>**0** – Devre dışı (varsayılan)<br>**1** – Etkin|
|**Enterprise Site Listesi Yapılandırma**<br>(yalnızca masaüstü)|**URI tam yolu:** ./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList<br /><br />**Veri türü:** Dize<br /><br />**İzin verilen değerler:<br>0** – Yapılandırılmadı<br>**1** – Yapılandırılmışsa IE'nin kuruluş modu site listesini kullan (varsayılan)<br>**2** – Kuruluş site listesi için konum belirt|

### Ayrıca bkz.
[Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Aug16_HO2-->


