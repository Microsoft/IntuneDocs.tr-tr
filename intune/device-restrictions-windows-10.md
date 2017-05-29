---
title: "Windows 10 için Intune cihaz kısıtlama ayarları"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Windows 10 cihazlarında cihaz ayarlarını ve işlevselliğini denetlemek için kullanabileceğiniz Intune ayarlarını öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 89f2d806-2e97-430c-a9a1-70688269627f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 88910c6628bb356e4a757cbdb4cf63b0acf60040
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="windows-10-and-later-device-restriction-settings-in-microsoft-intune"></a>Microsoft Intune’da Windows 10 ve üzeri cihaz kısıtlama ayarları

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

## <a name="general"></a>Genel
-     **Ekran yakalama (yalnızca mobil)** - Kullanıcının cihaz ekranını resim olarak yakalamasına olanak sağlar.
-     **Kopyala ve yapıştır (yalnızca mobil)** - Cihazda uygulamalar arasında kopyalama ve yapıştırma eylemlerine izin verin.
-     **El ile kayıt kaldırma** - Kullanıcının iş yeri hesabını cihazdan el ile silmesine olanak sağlar.
-     **Elle kök sertifikası yüklemesi (yalnızca mobil)** - Kullanıcının elle kök sertifikaları ve aracı CAP sertifikaları yüklemesini engeller.
-     **Tanılama verileri gönderme** - Olası değerler şunlardır:
    -         **Hiçbiri** Microsoft’a hiç veri gönderilmez
    -         **Temel** Microsoft’a sınırlı bilgi gönderilir
    -         **Gelişmiş** Microsoft’a gelişmiş tanılama bilgileri gönderilir
    -         **Tam** Gelişmiş ayarıyla aynı veriler, artı olarak cihazın durumuyla ilgili ek veriler gönderilir
-     **Kamera** - Cihazdaki kameranın kullanılmasına izin verin veya bunu engelleyin.
-     **OneDrive dosya eşitleme** - Cihazın dosyaları OneDrive’a eşitlemesini engeller.
-     **Çıkarılabilir depolama** - Cihazla birlikte SD kartı gibi dış depolama cihazlarının kullanılıp kullanılamayacağını belirtir.
-     **Coğrafi konum** - Cihazın konum hizmetleri bilgilerini kullanıp kullanamayacağını belirtir.
-     **İnternet paylaşımı** - Cihazda İnternet bağlantısı paylaşımının kullanımına izin verin.
-     **Telefon sıfırlama** - Kullanıcının cihazını fabrika ayarlarına sıfırlayıp sıfırlayamayacağını denetler.
-     **USB bağlantısı (yalnızca mobil)** - Cihazların USB bağlantısı aracılığıyla harici depolama cihazlarına erişip erişemeyeceğini denetler.
-     **Hırsızlık Önleme modu (yalnızca mobil)** - Windows Hırsızlık Önleme modunun etkin olup olmadığını yapılandırın.
-     **İşlem merkezi bildirimleri (yalnızca mobil)** - Cihaz kilit ekranında işlem merkezi bildirimlerini etkinleştirin veya devre dışı bırakın (yalnızca Windows 10 Mobile).
-     **Cortana** - Cortana sesli yardımcısını etkinleştirin veya devre dışı bırakın.
-     **Ses kaydı (yalnızca mobil)** - Cihazın ses kaydedicisinin kullanılmasına izin verin veya bunu engelleyin.
-     **Güç ve uyku ayarlarındaki değişiklikler (yalnızca masaüstü)** - Son kullanıcının cihazın güç ve uyku ayarlarını değiştirmesini engeller.
-     **Bölge ayarlarındaki değişiklikler (yalnızca masaüstü)** - Son kullanıcının cihazın bölge ayarlarını değiştirmesini engeller.
-     **Dil ayarlarındaki değişiklikler (yalnızca masaüstü)** - Kullanıcının cihazın dil ayarlarını değiştirmesini engeller.
-     **Sistem Saatindeki değişiklikler** - Son kullanıcının cihazın tarih ve saatini değiştirmesini engeller.
-     **Cihaz adındaki değişiklikler** - Son kullanıcının cihaz adını değiştirmesini engeller.
-     **Sağlama paketleri ekleme** - Sağlama paketleri yükleyen çalışma zamanı yapılandırma aracısını engeller.
-     **Sağlama paketlerini kaldırma** - Sağlama paketlerini kaldıran çalışma zamanı yapılandırma aracısını engeller.
-     **Cihaz bulma** - Bir cihazın diğer cihazlar tarafından bulunmasını engelleyin.
-     **Görev Değiştirici (yalnızca mobil)** - Cihazdaki görev değiştiriciyi engeller.
-     **SIM kart hatası iletişim kutusu (yalnızca mobil)** -SIM kart algılanmazsa cihazda bir hata iletisinin görüntülenmesini engeller.


## <a name="password"></a>Parola
-     **Parola** - Son kullanıcının cihaza erişmek için parola girmesini zorunlu tutun.
    -     **Gerekli parola türü** - Parolanın yalnızca sayısal mı yoksa alfasayısal mı olacağını belirtir.
    -     **En az parola uzunluğu** - Yalnızca Windows 10 Mobile için geçerlidir.
    -     **Cihaz silinmeden önceki oturum açma hatası sayısı** - Windows 10 çalıştıran cihazlar için: Cihazda BitLocker etkinse, belirttiğiniz oturum açma hatası sayısından sonra cihaz BitLocker kurtarma moduna alınır. Cihazda BitLocker etkin değilse, bu ayar uygulanmaz.
Windows 10 Mobile çalıştıran cihazlar için: Belirttiğiniz oturum açma sayısından sonra cihaz silinir.
    -     **Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı** - Ekran kilitlenmeden önce cihazın boşta bekleyeceği süreyi belirtir.
    -     **Parola geçerlilik süresi (gün)** - Cihaz parolasının ne kadar süre sonra değiştirilmesi gerektiğini belirtir.
    -     **Önceki parolaların yeniden kullanılmasını engelle** - Önceden kullanılmış ve cihaz tarafından anımsanacak olan parola sayısını belirtir.
    -     **Cihaz boşta kalma durumundan çıktığında parola isteme** - Boşta durumundaki bir cihazın kilidini açmak için kullanıcının parola girmesi gerektiğini belirtir (yalnızca Windows 10 Mobile).
-     **Şifreleme** - Hedeflenen cihazlarda şifrelemeyi etkinleştirin (yalnızca Windows 10 Mobile).

## <a name="personalization"></a>Kişiselleştirme

-     **Masaüstü arka plan resmi URL'si (yalnızca masaüstü)** - Windows masaüstü duvar kağıdı olarak kullanılacak PNG, JPG veya JPEG biçiminde bir resim URL'si belirtin. Kullanıcıların bunu değiştirmesi mümkün olmayacaktır.

## <a name="locked-screen-experience"></a>Kilit ekranı deneyimi

-     **Kilit ekranı resmi URL'si (yalnızca masaüstü)** - Windows kilit ekranı duvar kağıdı olarak kullanılacak PNG, JPG veya JPEG biçiminde bir resim URL'si belirtin. Kullanıcıların bunu değiştirmesi mümkün olmayacaktır.


## <a name="app-store"></a>Uygulama Mağazası

-     **Uygulama mağazası (yalnızca mobil)** - Windows 10 Mobile cihazlarında uygulama mağazasının kullanılmasını etkinleştirin veya engelleyin.
-     **Mağaza uygulamalarını otomatik güncelleştir** -Windows Mağazası'ndan yüklenen uygulamaların otomatik olarak güncelleştirilmesine izin verir.
-     **Güvenilir uygulama yüklemesi** - Güvenilir bir sertifikayla imzalanan uygulamaların dışarıdan yüklenmesine izin verir.
-     **Geliştirici kilidini açma** - Dışarıdan yüklenen uygulamaların son kullanıcı tarafından değiştirilmesine izin verme gibi Windows geliştirici ayarlarına izin verir.
-     **Paylaşılan kullanıcı uygulaması verileri** - Uygulamaların aynı cihazdaki farklı kullanıcılar arasında veri paylaşmasına izin verir.
-     **Yalnızca özel mağaza kullan** - Son kullanıcıların yalnızca özel mağazanızdan uygulama indirmesine izin vermek için bu ayarı etkinleştirin.
-     **Mağaza kaynaklı uygulama başlatma** - Cihaza önceden yüklenmiş veya Windows Mağazası'ndan indirilmiş tüm uygulamaları devre dışı bırakmak için kullanılır.
-     **Uygulama verilerini sistem birimine yükle** - Uygulamaların cihazın sistem birimine veri depolamasını engeller.
-     **Uygulamaları sistem sürücüsüne yükle** - Uygulamaların cihazın sistem sürücüsüne veri depolamasını engeller.
-     **Oyun DVR (yalnızca masaüstü)** - Oyun kaydetme ve yayınlamaya izin verilip verilmediğini yapılandırır.



## <a name="edge-browser"></a>Edge Tarayıcısı
-     **Microsoft Edge tarayıcısı (yalnızca mobil)** - Cihazda Microsoft Edge web tarayıcısının kullanılmasına izin verin.
-     **SmartScreen** - Sahte web sitelerini engelleyen SmartScreen’i etkinleştirir veya devre dışı bırakır.
-     **Kullanıcıyı-izleme üst bilgileri gönderme** - Edge tarayıcısını, kullanıcıların ziyaret ettiği web sitelerine izleme (DNT) üst bilgileri gönderecek şekilde yapılandırır.
-     **Tanılama bilgileri** - Tarayıcının İnternet tanımlama bilgilerini cihaza kaydetmesine olanak tanır.
-     **JavaScript** - Edge tarayıcısında JavaScript gibi betiklerin çalıştırılmasına izin verir.
-     **Açılır pencereler** - Tarayıcıdaki açılır pencereleri engeller (yalnızca Windows 10 masaüstü için geçerlidir).
-     **Arama önerileri** - Siz arama sözcükleri yazarken arama motorunuzun site önerilerinde bulunmasına olanak sağlar.
-     **Intranet trafiğini Internet Explorer'a gönder** - Kullanıcıların Internet Explorer’da intranet web siteleri açmasına olanak sağlar (Yalnızca Windows 10 masaüstü).
-     **Otomatik Doldurma** - Kullanıcıların tarayıcıdaki otomatik tamamlama ayarlarını değiştirmesine izin verin (Yalnızca Windows 10 masaüstü).
-     **Parola Yöneticisi** - Edge Parola Yöneticisi özelliğini etkinleştirin veya devre dışı bırakın.
-     **Kurumsal mod site listesi konumu** - Kurumsal modda açılan web siteleri listesinin nerede bulunacağını belirtir. Kullanıcılar bu listeyi düzenleyemez.<br>(Yalnızca Windows 10 masaüstü).
-     **Geliştirici araçları** - Son kullanıcının Edge geliştirici araçları açmasını engelleyin.
-     **Uzantılar** - Son kullanıcının cihaza Edge uzantıları yüklemesine izin verin.
-     **InPrivate gözatma** - Son kullanıcının InPrivate gözatma oturumları açmasını engelleyin.
-     **İlk çalıştırma url’si** - Edge tarayıcısı ilk defa çalıştırıldığında açılacak URL'yi girin (yalnızca mobil).
-     **Ana sayfalar** - Edge tarayıcısında ana sayfa olarak kullanılacak sitelerin listesini ekleyin (yalnızca masaüstü).
-     **about:flags erişimini engelle** - Son kullanıcının Edge’deki geliştirici ayarları ve deneysel ayarlar içeren about:flags sayfasına erişimini engelleyin.
-     **Akıllı ekran komut istemini geçersiz kılma** - Son kullanıcının olası kötü amaçlı web siteleri hakkındaki SmartScreen filtre uyarılarını atlamasına izin verin.
-     **Dosyalar için akıllı ekran komut istemini geçersiz kılma** - Son kullanıcının olası kötü amaçlı dosyaları indirme hakkındaki SmartScreen filtre uyarılarını atlamasına izin verin.
-     **WebRtc localhost IP adresi** - Web RTC protokolü kullanarak telefon araması yaparken kullanıcıların localhost IP adresinin görüntülenmesini engelleyin.
-     **Varsayılan arama motoru** - Kullanılacak varsayılan arama motorunu belirtin. Son kullanıcılar bu değeri istediği zaman değiştirebilir.

## <a name="search"></a>Ara
- **Güvenli Arama (yalnızca mobil)** - Cortana’nın yetişkinlere yönelik içeriği arama sonuçlarında nasıl filtreleyeceğini denetleyin. **Katı**, **Orta** değerlerini seçebilir ya da son kullanıcının kendi ayarlarını seçmesine izin verebilirsiniz.

## <a name="cloud-and-storage"></a>Bulut ve Depolama
-     **Microsoft hesabı** - Kullanıcının bir Microsoft hesabını cihazla ilişkilendirmesine olanak sağlar.
-     **Microsoft olmayan hesaplar** - Kullanıcının cihaza bir Microsoft hesabıyla ilişkilendirilmemiş e-posta hesapları eklemesine olanak sağlar.
-     **Microsoft hesabı için ayar eşitlemesi** - Microsoft hesabıyla ilişkilendirilmiş cihaz ve uygulama ayarlarının cihazlar arasında eşitlenmesine izin verin.

## <a name="cellular-and-connectivity"></a>Hücresel ve Bağlantı
-     **Veri dolaşımı** - Verilere erişirken ağlar arasında dolaşıma izin verin.
-     **Hücresel ağ üzerinden VPN** - Cihazın hücresel ağa bağlandığında VPN bağlantılarına erişip erişemeyeceğini denetler.
-     **Hücresel ağ üzerinden VPN dolaşımı** - Cihazın hücresel ağda dolaşımı sırasında VPN bağlantılarına erişip erişemeyeceğini denetler.
-     **Bluetooth** - Kullanıcının cihazda Bluetooth’u etkinleştirmesine ve yapılandırmasına izin verilip verilmeyeceğini denetler.
-     **Bluetooth bulunabilirliği** - Cihazın diğer Bluetooth özellikli cihazlar tarafından bulunabilmesine olanak sağlar.
-     **Bluetooth reklamları** - Cihazın Bluetooth üzerinden reklamlar almasına olanak tanır.
-     **Cihazın Bluetooth adı** - Cihazın Bluetooth adını belirtmenize olanak tanır.
-     **NFC** - Kullanıcının cihazda Yakın Alan İletişimi özelliklerini etkinleştirmesine ve yapılandırmasına olanak tanır.
-     **Wi-Fi** - Kullanıcının cihazda Wi-Fi’yi etkinleştirmesine ve yapılandırmasına olanak tanır (yalnızca Windows 10 Mobile).
-     **Wi-Fi etkin noktalarına otomatik bağlanma** - Cihazın ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmasına ve bağlantıyla ilgili hüküm ve koşulları otomatik olarak kabul etmesine olanak sağlar.
-     **El ile Wi-Fi yapılandırması** - Kullanıcının kendi Wi-Fi bağlantılarını yapılandırıp yapılandıramayacağını veya yalnızca Wi-Fi profili tarafından yapılandırılan bağlantıları kullanıp kullanamayacağını denetleyin (yalnızca Windows 10 Mobile).
-     **Wi-Fi Tarama Aralığı** - Cihazların ne sıklıkta Wi-Fi ağlarını tarayacağını belirtin.

## <a name="control-panel-and-settings"></a>Denetim Masası ve Ayarlar

-     **Ayarlar uygulaması** - Windows ayarlar uygulamasına erişimi engelleyin.
    -     **Sistem** - Ayarlar uygulamasının sistem alanına erişimini engeller.
    -     **Cihazlar** - Ayarlar uygulamasının cihazlar alanına erişimini engeller.
    -     **Ağ ve İnternet** - Ayarlar uygulamasının ağ ve İnternet alanına erişimini engeller.
    -     **Kişiselleştirme** - Ayarlar uygulamasının kişiselleştirme alanına erişimini engeller.
    -     **Hesaplar** - Ayarlar uygulamasının hesaplar alanına erişimini engeller.
    -     **Saat ve Dil** - Ayarlar uygulamasının saat ve dil alanına erişimini engeller.
    -     **Erişim Kolaylığı** - Ayarlar uygulamasının hesaplar alanına erişimini engeller.
    -     **Gizlilik** - Ayarlar uygulamasının gizlilik alanına erişimini engeller.
    -     **Güvenlik Güncelleştirmesi** - Ayarlar uygulamasının güncelleştirmeler ve güvenlik alanına erişimini engeller.

## <a name="defender"></a>Defender

-     **Gerçek zamanlı izleme** - Kötü amaçlı yazılım, casus yazılım ve istenmeyen diğer yazılımlar için gerçek zamanlı taramayı etkinleştirir.
-     **Davranış izleme** - Defender’ın cihazlarda bilinen şüpheli etkinlik kalıplarının var olup olmadığını denetlemesine olanak sağlar.
-     **Ağ İnceleme Sistemi (NIS)** - Ağ İnceleme Sistemi (NIS), kötü amaçlı trafiğin algılanmasına ve engellenmesine katkıda bulunmak için Microsoft Endpoint Protection Center’dan gelen bilinen güvenlik açıklarının imzalarını kullanarak ağ tabanlı saldırılara karşı korunmaya yardımcı olur.
-     **İndirilen tüm öğeleri tara** - Defender’ın İnternet’ten indirilen tüm dosyaları tarayıp taramayacağını denetler.
-     **Microsoft web tarayıcılarında yüklenen betikleri tarama** - Defender’ın Internet Explorer’da kullanılan betikleri taramasına olanak sağlar.
-     **Defender'a son kullanıcı erişimi** - Windows Defender kullanıcı arabiriminin son kullanıcılardan gizlenip gizlenmeyeceğini denetler.
Bu ayar değiştirildiğinde, son kullanıcının bilgisayarı bir sonraki yeniden başlatmasında geçerlilik kazanır.
-     **İmza güncelleştirme aralığı (saat olarak)** - Defender’ın yeni imza dosyalarını denetleme aralığını belirtin.
-     **Dosya ve program etkinliğini izleme** - Defender’ın cihazlarda dosya ve program etkinliğini izlemesine izin verir.
-     **Karantinaya alınmış kötü amaçlı yazılım silinmeden önce geçecek gün sayısı** - Defender’ın çözümlenen kötü amaçlı yazılımı belirttiğiniz sayıda gün boyunca izlemeye devam etmesine olanak sağlar; böylece daha önce etkilenmiş olan cihazları el ile denetleyebilirsiniz. Gün sayısını **0** olarak ayarlarsanız, kötü amaçlı yazılım Karantina klasöründe kalır ve otomatik olarak kaldırılmaz.
-     **Tarama sırasında CPU kullanım sınırı** - Taramaların kullanmasına izin verilecek CPU miktarını sınırlandırmanıza (**1** ile **100** arasında) olanak sağlar.
-     **Arşiv dosyalarını tara** - Defender’ın Zip veya Cab dosyaları gibi arşivlenmiş dosyaları taramasına izin verir.
-     **Gelen posta iletilerini tarama** - Defender’ın cihaza gelen e-posta iletilerini taramasına izin verir.
-     **Tam tarama sırasında çıkarılabilir sürücüleri tarama** - Defender’ın USB çubukları gibi çıkarılabilir sürücüleri taramasına olanak sağlar.
-     **Tam tarama sırasında eşlenmiş ağ sürücülerini tarama** - Defender’ın eşlenmiş ağ sürücüsündeki dosyaları taramasına olanak sağlar.<br>Sürücüdeki dosyalar salt okunur olduğunda, Defender bunların içinde bulduğu kötü amaçlı yazılımları kaldıramaz.
-     **Ağ klasörlerinden açılan dosyaları tarama** - Defender’ın paylaşılan ağ sürücülerindeki dosyaları (örneğin UNC yolundan erişilenler) taramasına olanak sağlar.
Sürücüdeki dosyalar salt okunur olduğunda, Defender bunların içinde bulduğu kötü amaçlı yazılımları kaldıramaz.
-     **Bulut koruması** - Microsoft Etkin Koruma Hizmeti’nin yönettiğiniz cihazlardan kötü amaçlı yazılım etkinliğiyle ilgili bilgi almasına izin verir veya bunu engeller. Bu bilgi gelecekte hizmeti geliştirmek için kullanılır.
-     **Örnek göndermeden önce kullanıcılara sor** - Kötü amaçlı olup olmadıklarını belirlemek için Microsoft tarafından daha fazla çözümlenmesi gerekebilecek dosyaların Microsoft’a otomatik olarak gönderilip gönderilmeyeceğini denetler.
-     **Günlük hızlı tarama gerçekleştirilecek saat** - Her gün seçtiğiniz saatte gerçekleştirilecek olan bir hızlı tarama zamanlamanıza olanak sağlar.
-     **Gerçekleştirilecek sistem taraması türü** - Sistem taraması zamanladığınızda gerçekleştirilecek tarama düzeyini belirtmenize olanak tanır.

## <a name="defender-exclusions"></a>Klasör Dışlamaları

-     **Taramaların ve gerçek zamanlı korumanın dışında tutulacak dosyalar ve klasörler** - Dışlama listesine **C:\Yol** veya **%ProgramFiles%\Yol\dosyaadı.exe** gibi bir veya birden çok dosya ve klasör ekler. Bu dosya ve klasörler gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.
-     **Taramaların ve gerçek zamanlı korumanın dışında tutulacak dosya uzantıları** - Dışlama listesine **jpg** veya **txt** gibi bir veya birden çok dosya uzantısı ekleyin. Bu uzantıya sahip dosyaların hiçbiri gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.
-     **Taramaların ve gerçek zamanlı korumanın dışında bırakılacak işlemler** - Dışlama listesine **.exe**, **.com** veya **.scr** türünde bir veya birden çok işlem ekleyin. Bu işlemler gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.


## <a name="network-proxy"></a>Ağ proxy’si

-     **Proxy ayarlarını otomatik olarak algıla** - Etkinleştirildiğinde, cihaz bir PAC betiğine yol bulmayı dener.
-     **Proxy betiği kullan** - Proxy sunucusunu yapılandırmak için PAC betiğine bir yol belirtmek isterseniz bu seçeneği belirleyin.
    -     **Kurulum betiği adresi URL’si** - Proxy sunucusunu yapılandırmak için kullanmak istediğiniz bir PAC betiğinin URL’sini girin.
-     **El ile proxy sunucusu kullan** - Proxy sunucusu bilgilerini el ile sağlamak istiyorsanız, bunu seçin.
    -     **Adres** - Proxy sunucusu adını veya IP adresini girin.
    -     **Bağlantı noktası numarası** - Proxy sunucunuzun bağlantı noktası numarasını girin.
    -     **Proxy özel durumları** - Proxy sunucusunu kullanmaması gereken herhangi bir URL girin. Her birini ayırmak için noktalı virgül kullanın.
    -     **Yerel adres için proxy sunucusunu atla** - Intranet üzerindeki yerel adresler için proxy sunucusunu kullanmak istemiyorsanız bu seçeneği etkinleştirin.


## <a name="windows-spotlight"></a>Windows Spot

-     **Windows Spot** - İpuçları ve püf noktaları, Windows Kilit ekranı iletileri ve daha birçok özellik sağlayan Windows Spot’a izin verin ya da engelleyin.
    -     **Windows İpuçları** - Windows’da görüntülenen açılır ipuçlarını engellemenize izin verir.
    -     **Tüketici Özellikleri** - Başlat menüsü önerileri ve üyelik bildirimleri gibi özellikleri engellemenizi sağlar.

## <a name="display"></a>Görüntüle

- **Kablosuz ekran alıcılarından kullanıcı girişi** -Kablosuz ekran alıcılarından kullanıcı girişini engeller.
- **Bu bilgisayara yansıtma** - Diğer cihazların yansıtma için bilgisayarı bulmasını engeller.
- **Eşleştirme için PIN gerektir** - Bir projeksiyon cihazına bağlanırken PIN gerektirin.

## <a name="start"></a>Başlangıç

- **Uygulamaları görev çubuğundan kaldır** - Kullanıcıların uygulamaları Başlat menüsünden kaldırmasını engelleyin.
- **Başlat Menüsünde Belgeler** - Windows Başlat menüsündeki Belgeler klasörünü gösterin veya gizleyin.
- **Başlat Menüsünde İndirilenler** - Windows Başlat menüsündeki İndirilenler klasörünü gösterin veya gizleyin.
- **Başlat Menüsünde Dosya Gezgini** - Windows Başlat menüsündeki Dosya Gezgini uygulamasını gösterin veya gizleyin.
- **Başlat Menüsünde Ev Grubu** - Windows Başlat menüsündeki Ev Grubu klasörünü gösterin veya gizleyin.
- **Başlat Menüsünde Müzik** - Windows Başlat menüsündeki Müzik klasörünü gösterin veya gizleyin.
- **Başlat Menüsünde Ağ** - Windows Başlat menüsündeki Ağ klasörünü gösterin veya gizleyin.
- **Başlat Menüsünde Kişisel klasörü** - Windows Başlat menüsündeki Kişisel klasörünü gösterin veya gizleyin.
- **Başlat Menüsünde Resimler** - Windows Başlat menüsündeki Resimler klasörünü gösterin veya gizleyin.
- **Başlat Menüsünde Ayarlar** - Windows Başlat menüsündeki Ayarlar uygulamasını gösterin veya gizleyin.
- **Başlat Menüsünde Videolar** - Windows Başlat menüsündeki Videolar klasörünü gösterin veya gizleyin.
