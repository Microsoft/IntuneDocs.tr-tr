---
title: "Windows 10 için Intune cihaz kısıtlama ayarları"
titlesuffix: Azure portal
description: "Windows 10 cihazlarında cihaz ayarlarını ve işlevselliğini denetlemek için kullanabileceğiniz Intune ayarlarını öğrenin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 89f2d806-2e97-430c-a9a1-70688269627f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 182088fa7c99f9f933d2228c0cdcf6a29aa4d727
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2017
---
# <a name="windows-10-and-later-device-restriction-settings-in-microsoft-intune"></a>Microsoft Intune’da Windows 10 ve üzeri cihaz kısıtlama ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="general"></a>Genel
-   **Ekran yakalama (yalnızca mobil)** - Kullanıcının cihaz ekranını resim olarak yakalamasına olanak sağlar.
-   **Kopyala ve yapıştır (yalnızca mobil)** - Cihazda uygulamalar arasında kopyalama ve yapıştırma eylemlerine izin verin.
-   **El ile kayıt kaldırma** - Kullanıcının iş yeri hesabını cihazdan el ile silmesine olanak sağlar.
-   **Elle kök sertifika yüklemesi (yalnızca mobil)** - Kullanıcının elle kök sertifikaları ve ara CAP sertifikaları yüklemesini engeller.
-   **Tanılama verileri gönderme** - Olası değerler şunlardır:
    -       **Hiçbiri** Microsoft’a hiç veri gönderilmez
    -       **Temel** Microsoft’a sınırlı bilgi gönderilir
    -       **Gelişmiş** Microsoft’a gelişmiş tanılama bilgileri gönderilir
    -       **Tam** Gelişmiş ayarıyla aynı veriler, artı olarak cihazın durumuyla ilgili ek veriler gönderilir
-   **Kamera** - Cihazdaki kameranın kullanılmasına izin verin veya bunu engelleyin.
-   **OneDrive dosya eşitleme** - Cihazın dosyaları OneDrive’a eşitlemesini engeller.
-   **Çıkarılabilir depolama** - SD kartı gibi dış depolama cihazlarının cihazla kullanılıp kullanılamayacağını belirtir.
-   **Coğrafi konum** - Cihazın konum hizmetleri bilgilerini kullanıp kullanamayacağını belirtir.
-   **İnternet paylaşımı** - Cihazda İnternet bağlantısı paylaşımının kullanımına izin verin.
-   **Telefon sıfırlama** - Kullanıcının cihazını fabrika ayarlarına sıfırlayıp sıfırlayamayacağını denetler.
-   **USB bağlantısı (yalnızca mobil)** - Cihazların USB bağlantısı aracılığıyla harici depolama cihazlarına erişip erişemeyeceğini denetler.
-   **Hırsızlık Önleme modu (yalnızca mobil)** - Windows Hırsızlık Önleme modunun etkin olup olmadığını yapılandırın.
-   **Cortana** - Cortana sesli yardımcısını etkinleştirin veya devre dışı bırakın.
-   **Ses kaydı (yalnızca mobil)** - Cihaz ses kaydedicisinin kullanılmasına izin verin veya bunu engelleyin.
-   **Cihaz adındaki değişiklikler** - Son kullanıcının cihaz adını değiştirmesini engeller (yalnızca Windows 10 Mobile)
-   **Sağlama paketleri ekleme** - Sağlama paketleri yükleyen çalışma zamanı yapılandırma aracısını engeller.
-   **Sağlama paketlerini kaldırma** - Sağlama paketlerini kaldıran çalışma zamanı yapılandırma aracısını engeller.
-   **Cihaz bulma** - Bir cihazın diğer cihazlar tarafından bulunmasını engelleyin.
-   **Görev Değiştirici (yalnızca mobil)** - Cihazdaki görev değiştiriciyi engeller.
-   **SIM kart hatası iletişim kutusu (yalnızca mobil)** -SIM kart algılanmazsa cihazda bir hata iletisinin görüntülenmesini engeller.


## <a name="password"></a>Parola
-   **Parola** - Son kullanıcının cihaza erişmek için parola girmesini zorunlu tutun.
    -   **Gerekli parola türü** - Parolanın yalnızca sayısal mı yoksa alfasayısal mı olacağını belirtir.
    -   **En az parola uzunluğu** - Yalnızca Windows 10 Mobile için geçerlidir.
    -   **Cihaz silinmeden önceki oturum açma hatası sayısı** - Windows 10 çalıştıran cihazlar için: Cihazda BitLocker etkinse, belirttiğiniz oturum açma sayısından sonra cihaz BitLocker kurtarma moduna alınır. Cihazda BitLocker etkin değilse, bu ayar uygulanmaz.
Windows 10 Mobile çalıştıran cihazlar için: Belirttiğiniz oturum açma sayısından sonra cihaz silinir.
    -   **Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı** - Ekran kilitlenmeden önce cihazın boşta bekleyeceği süreyi belirtir.
    -   **Parola geçerlilik süresi (gün)** - Cihaz parolasının ne kadar süre sonra değiştirilmesi gerektiğini belirtir.
    -   **Önceki parolaların yeniden kullanılmasını engelle** - Önceden kullanılmış ve cihaz tarafından anımsanacak olan parola sayısını belirtir.
    -   **Cihaz boşta kalma durumundan çıktığında parola isteme (yalnızca mobil)** - Cihazın kilidini açmak için kullanıcının parola girmesi gerektiğini belirtir (yalnızca Windows 10 Mobile).
    -   **Basit parolalar** – 1111 ve 1234 gibi basit parolalar kullanılmasına izin verir. Bu ayar, Windows resimli parolalarının kullanımına izin verir veya bunu engeller.
-   **Şifreleme** - Hedeflenen cihazlarda şifrelemeyi etkinleştirin (yalnızca Windows 10 Mobile).

## <a name="personalization"></a>Kişiselleştirme

-   **Masaüstü arka plan resmi URL'si (Yalnızca masaüstü)** - Windows masaüstü duvar kağıdı olarak kullanmak istediğiniz PNG, JPG veya JPEG biçiminde bir resmin URL'sini belirtin. Kullanıcıların bunu değiştirmesi mümkün olmayacaktır.

## <a name="privacy"></a>Gizlilik

-   **Girişi kişiselleştirme** – Cortana, dikte veya Microsoft Mağazası uygulamaları için bulut tabanlı konuşma hizmeti kullanılmasına izin vermez. Bu hizmetlere izin verirseniz Microsoft, hizmeti geliştirmek için sesli veri toplayabilir.
-   **Eşleştirme ve gizlilik kullanıcı onayı istemlerini otomatik kabul et** – Windows'un, uygulama çalıştırırken eşleştirme ve gizlilik onay iletilerini otomatik olarak kabul etmesine izin ver.


## <a name="locked-screen-experience"></a>Kilit ekranı deneyimi


-   **İşlem merkezi bildirimleri (yalnızca mobil)** - Cihaz kilitleme ekranında İşlem Merkezi bildiriminin görünmesine izin verir (yalnızca Windows 10 Mobile).
-   **Kilit ekranı resmi URL'si (yalnızca masaüstü)** - Windows kilit ekranı duvar kağıdı olarak kullanılacak PNG, JPG veya JPEG biçiminde bir resim URL'si belirtin. Kullanıcıların bunu değiştirmesi mümkün olmayacaktır.
-   **Kullanıcı tarafından yapılandırılabilir ekran zaman aşımı (yalnızca mobil)** – Kullanıcıların süreyi yapılandırmasına izin verir 
-   **Kilitleme ekranında Cortana (yalnızca masaüstü) ** – Cihaz kilitleme ekranındayken kullanıcının Cortana ile etkileşim kurmasına izin vermez (yalnızca Windows 10 masaüstü).
-   **Kilitli ekranda bildirimler** – Cihaz kilitleme ekranında uyarı iletileri gösterilmesini engelleyin.
-   **Ekran zaman aşımı (yalnızca mobil)** - Ekranın kapanarak kilitlenmesi için geçecek süreyi saniye olarak belirtir.



## <a name="app-store"></a>Uygulama Mağazası

-   **Uygulama mağazası (yalnızca mobil)** - Windows 10 Mobile cihazlarında uygulama mağazasının kullanılmasını etkinleştirin veya engelleyin.
-   **Mağaza uygulamalarını otomatik güncelleştir** - Microsoft Mağazası'ndan yüklenen uygulamaların otomatik olarak güncelleştirilmesine izin verir.
-   **Güvenilir uygulama yüklemesi** - Güvenilir bir sertifikayla imzalanan uygulamaların dışarıdan yüklenmesine izin verir.
-   **Geliştirici kilidini açma** - Dışarıdan yüklenen uygulamaların son kullanıcı tarafından değiştirilmesine izin verme gibi Windows geliştirici ayarlarına izin verir.
-   **Paylaşılan kullanıcı uygulaması verileri** - Uygulamaların aynı cihazdaki farklı kullanıcılar arasında veri paylaşmasına izin verir.
-   **Yalnızca özel mağaza kullan** - Son kullanıcıların yalnızca özel mağazanızdan uygulama indirmesine izin vermek için bu ayarı etkinleştirin.
-   **Mağaza kaynaklı uygulama başlatma** - Cihaza önceden yüklenmiş veya Microsoft Mağazası'ndan indirilmiş tüm uygulamaları devre dışı bırakmak için kullanılır.
-   **Uygulama verilerini sistem birimine yükle** - Uygulamaların cihazın sistem birimine veri depolamasını engeller.
-   **Uygulamaları sistem sürücüsüne yükle** - Uygulamaların cihazın sistem sürücüsüne veri depolamasını engeller.
-   **Oyun DVR (yalnızca masaüstü)** - Oyun kaydetme ve yayınlamaya izin verilip verilmediğini yapılandırır.
-   **Yalnızca mağazadan yüklenebilen uygulamalar** - Kullanıcıların uygulama mağazası dışındaki yerlerden uygulama yükleyip yükleyemeyeceğini yapılandırır.



## <a name="edge-browser"></a>Edge Tarayıcısı
-   **Microsoft Edge tarayıcısı (yalnızca mobil)** - Cihazda Microsoft Edge web tarayıcısının kullanılmasına izin verin.
-   **Adres çubuğu aşağı açılan listesi (yalnızca masaüstü)** – Yazdığınızda Edge'in açılan bir listede bir dizi öneri göstermesini durdurmak için bunu kullanın. Edge ile Microsoft hizmetleri arasında ağ bant genişliği kullanımını en aza indirmeye yardımcı olur.
-   **Microsoft tarayıcıları arasında sık kullanılanları eşitle (yalnızca masaüstü) ** – Windows'un Internet Explorer ve Edge arasında sık kullanılanları eşitlemesine izin verir.
-   **Kullanıcıyı-izleme üst bilgileri gönderme** - Edge tarayıcısını, kullanıcıların ziyaret ettiği web sitelerine izleme (DNT) üst bilgileri gönderecek şekilde yapılandırır.
-   **Tanılama bilgileri** - Tarayıcının İnternet tanımlama bilgilerini cihaza kaydetmesine olanak tanır.
-   **JavaScript** - Edge tarayıcısında JavaScript gibi betiklerin çalıştırılmasına izin verir.
-   **Açılır pencereler** - Tarayıcıdaki açılır pencereleri engeller (yalnızca Windows 10 masaüstü için geçerlidir).
-   **Arama önerileri** - Siz arama sözcükleri yazarken arama motorunuzun site önerilerinde bulunmasına olanak sağlar.
-   **Intranet trafiğini Internet Explorer'a gönder** - Kullanıcıların Internet Explorer’da intranet web siteleri açmasına olanak sağlar (Yalnızca Windows 10 masaüstü).
-   **Otomatik Doldurma** - Kullanıcıların tarayıcıdaki otomatik tamamlama ayarlarını değiştirmesine izin verin (Yalnızca Windows 10 masaüstü).
-   **Parola Yöneticisi** - Edge Parola Yöneticisi özelliğini etkinleştirin veya devre dışı bırakın.
-   **Kurumsal mod site listesi konumu** - Kurumsal modda açılan web siteleri listesinin nerede bulunacağını belirtir. Kullanıcılar bu listeyi düzenleyemez.<br>(Yalnızca Windows 10 masaüstü).
-   **Geliştirici araçları** - Son kullanıcının Edge geliştirici araçlarını açmasını engelleyin.
-   **Uzantılar** - Son kullanıcının cihaza Edge uzantıları yüklemesine izin verin.
-   **InPrivate gözatma** - Son kullanıcının InPrivate gözatma oturumları açmasını engelleyin.
-   **İlk çalıştırma sayfasını göster** – Edge'i ilk kez çalıştırdığınızda giriş sayfasının görüntülenmesini durdurur.
    -   **İlk çalıştırma URL'si** – Bir kullanıcı ilk kez Edge’i çalıştırdığında görüntülenen sayfanın URL'sini belirtir (yalnızca Windows 10 Mobile).
-   **Ana sayfalar** - Edge tarayıcısında giriş sayfası olarak kullanmak istediğiniz sitelerin bir listesini ekler (yalnızca masaüstü).
-   **Başlangıç sayfasındaki değişiklikler** – Kullanıcıların Edge açıldığında görüntülenen başlangıç sayfalarını değiştirmesine izin verir. Edge başladığında açılan sayfayı veya sayfa listesini oluşturmak için Giriş sayfaları ayarını kullanın.
-   **about:flags erişimini engelle** - Son kullanıcının Edge’deki geliştirici ayarları ve deneysel ayarlar içeren about:flags sayfasına erişimini engelleyin.
-   **WebRtc localhost IP adresi** - Web RTC protokolü kullanarak telefon araması yaparken kullanıcıların localhost IP adresinin görüntülenmesini engelleyin.
-   **Varsayılan arama motoru** - Kullanılacak varsayılan arama motorunu belirtin. Son kullanıcılar bu değeri istediği zaman değiştirebilir.
-   **Çıkışta tarama verilerini temizle** – Kullanıcı Edge'den çıktığında geçmişi ve tarama verilerini temizler.
-   **Canlı Kutucuk verisi toplama** – Kullanıcı, Edge'den başlatma menüsüne bir site sabitlediğinde Windows'un Canlı Kutucuk’tan bilgi toplamasını durdurur.

## <a name="edge-browser-smartscreen"></a>Edge Tarayıcısı SmartScreen

-   **SmartScreen** - Sahte web sitelerini engelleyen SmartScreen’i etkinleştirir veya devre dışı bırakır.
-   **Akıllı ekran komut istemini geçersiz kılma** - Son kullanıcının olası kötü amaçlı web siteleri hakkındaki SmartScreen filtre uyarılarını atlamasına izin verin.
-   **Dosyalar için akıllı ekran komut istemini geçersiz kılma** - Son kullanıcının olası kötü amaçlı dosyaları indirme hakkındaki SmartScreen filtre uyarılarını atlamasına izin verin.

## <a name="search"></a>Ara
- **Güvenli Arama (yalnızca mobil)** - Cortana’nın yetişkinlere yönelik içeriği arama sonuçlarında nasıl filtreleyeceğini denetleyin. **Katı**, **Orta** değerlerini seçebilir ya da son kullanıcının kendi ayarlarını seçmesine izin verebilirsiniz.

## <a name="cloud-and-storage"></a>Bulut ve Depolama
-   **Microsoft hesabı** - Kullanıcının bir Microsoft hesabını cihazla ilişkilendirmesine olanak sağlar.
-   **Microsoft olmayan hesaplar** - Kullanıcının cihaza bir Microsoft hesabıyla ilişkilendirilmemiş e-posta hesapları eklemesine olanak sağlar.
-   **Microsoft hesabı için ayar eşitlemesi** - Microsoft hesabıyla ilişkilendirilmiş cihaz ve uygulama ayarlarının cihazlar arasında eşitlenmesine izin verin.

## <a name="cellular-and-connectivity"></a>Hücresel ve Bağlantı

-   **Hücresel veri kanalı** – Bir hücresel ağa bağlandıklarında web’e gözatma gibi eylemlerle kullanıcıların veri kullanmasını durdurun. 
-   **Veri dolaşımı** - Verilere erişirken ağlar arasında dolaşıma izin verin.
-   **Hücresel ağ üzerinden VPN** - Cihazın hücresel ağa bağlandığında VPN bağlantılarına erişip erişemeyeceğini denetler.
-   **Hücresel ağ üzerinden VPN dolaşımı** - Cihazın hücresel ağda dolaşımı sırasında VPN bağlantılarına erişip erişemeyeceğini denetler.
-   **Bluetooth** - Kullanıcının cihazda Bluetooth’u etkinleştirmesine ve yapılandırmasına izin verilip verilmeyeceğini denetler.
-   **Bluetooth bulunabilirliği** - Cihazın diğer Bluetooth özellikli cihazlar tarafından bulunabilmesine olanak sağlar.
-   **Bluetooth önceden eşleştirme** – Belirli Bluetooth cihazlarını bir konak cihazla otomatik olarak eşleşecek şekilde yapılandırmanıza izin verir.
-   **Bluetooth reklamları** - Cihazın Bluetooth üzerinden reklamlar almasına olanak tanır.
-   **Bağlı cihazlar hizmeti** – Başka Bluetooth cihazlar bulmayı ve bunlara bağlanmayı etkinleştiren bağlı cihazlar hizmetine izin verip vermeyeceğinizi seçmenizi sağlar.
-   **NFC** - Kullanıcının cihazda Yakın Alan İletişimi özelliklerini etkinleştirmesine ve yapılandırmasına olanak tanır.
-   **Wi-Fi** - Kullanıcının cihazda Wi-Fi’yi etkinleştirmesine ve yapılandırmasına olanak tanır (yalnızca Windows 10 Mobile).
-   **Wi-Fi etkin noktalarına otomatik bağlanma** - Cihazın ücretsiz Wi-Fi etkin noktalarına otomatik olarak bağlanmasına ve bağlantıyla ilgili hüküm ve koşulları otomatik olarak kabul etmesine olanak sağlar.
-   **El ile Wi-Fi yapılandırması** - Kullanıcının kendi Wi-Fi bağlantılarını yapılandırıp yapılandıramayacağını veya yalnızca Wi-Fi profili tarafından yapılandırılan bağlantıları kullanıp kullanamayacağını denetleyin (yalnızca Windows 10 Mobile).
-   **Wi-Fi tarama aralığı** – Cihazların ne sıklıkta Wi-Fi ağlarını tarayacağını belirtir. 1 (en çok) ile 500 (en az) arasında bir değer belirtin.
-   **Bluetooth izin verilen hizmetler** – Onaltılık dize olarak izin verilen Bluetooth hizmet ve profillerinin bir listesini belirtin.


## <a name="control-panel-and-settings"></a>Denetim Masası ve Ayarlar

-   **Ayarlar uygulaması** - Windows ayarlar uygulamasına erişimi engelleyin.
    -   **Sistem** - Ayarlar uygulamasının sistem alanına erişimini engeller.
        -   **Güç ve uyku ayarlarındaki değişiklikler (yalnızca masaüstü)** - Son kullanıcının cihazın güç ve uyku ayarlarını değiştirmesini engeller.
    -   **Cihazlar** - Ayarlar uygulamasının cihazlar alanına erişimini engeller.
    -   **Ağ ve İnternet** - Ayarlar uygulamasının ağ ve İnternet alanına erişimini engeller.
    -   **Kişiselleştirme** - Ayarlar uygulamasının kişiselleştirme alanına erişimini engeller.
    -   **Hesaplar** - Ayarlar uygulamasının erişim kolaylığı alanına erişimini engeller.
    -   **Saat ve Dil** - Ayarlar uygulamasının saat ve dil alanına erişimini engeller.
        -   **Sistem Saatindeki değişiklikler** - Son kullanıcının cihazın tarih ve saatini değiştirmesini engeller.
        -   **Bölge ayarlarındaki değişiklikler (yalnızca masaüstü)** - Son kullanıcının cihazın bölge ayarlarını değiştirmesini engeller.
        -   **Dil ayarlarındaki değişiklikler (yalnızca masaüstü)** - Kullanıcının cihazın dil ayarlarını değiştirmesini engeller.
    -   **Oyun** - Ayarlar kısmında Oyun uygulamasına erişimini engeller.
    -   **Erişim Kolaylığı** - Ayarlar uygulamasının erişim kolaylığı alanına erişimini engeller.
    -   **Gizlilik** - Ayarlar uygulamasının gizlilik alanına erişimini engeller.
    -   **Güncelleştirme ve Güvenlik** - Ayarlar uygulamasının güncelleştirmeler ve güvenlik alanına erişimini engeller.

## <a name="defender"></a>Defender

-   **Gerçek zamanlı izleme** - Kötü amaçlı yazılım, casus yazılım ve istenmeyen diğer yazılımlar için gerçek zamanlı taramayı etkinleştirir.
-   **Davranış izleme** - Defender’ın cihazlarda bilinen şüpheli etkinlik düzenlerini denetlemesine olanak sağlar.
-   **Ağ İnceleme Sistemi (NIS)** - NIS, cihazları ağ tabanlı açıklara karşı korumaya yardımcı olur. Kötü amaçlı trafiği algılamaya ve engellemeye yardımcı olmak için Microsoft Endpoint Protection Center’dan bilinen açıkların imzalarını kullanır.
-   **İndirilen tüm öğeleri tara** - Defender’ın İnternet’ten indirilen tüm dosyaları tarayıp taramayacağını denetler.
-   **Microsoft web tarayıcılarında yüklenen betikleri tarama** - Defender’ın Internet Explorer’da kullanılan betikleri taramasına olanak sağlar.
-   **Defender'a son kullanıcı erişimi** - Windows Defender kullanıcı arabiriminin son kullanıcılardan gizlenip gizlenmediğini denetler.
Bu ayar değiştirildiğinde, kullanıcının bilgisayarının bir sonraki yeniden başlatılmasında devreye girer.
-   **İmza güncelleştirme aralığı (saat olarak)** - Defender'ın yeni imza dosyalarını denetleme aralığını belirtin.
-   **Dosya ve program etkinliğini izleme** - Defender’ın cihazlarda dosya ve program etkinliğini izlemesine izin verir.
-   **Karantinaya alınmış kötü amaçlı yazılım silinmeden önce geçecek gün sayısı** - Defender’ın çözümlenen kötü amaçlı yazılımı belirttiğiniz sayıda gün boyunca izlemeye devam etmesine olanak sağlar; böylece daha önce etkilenmiş olan cihazları el ile denetleyebilirsiniz. Gün sayısını **0** olarak ayarlarsanız, kötü amaçlı yazılım Karantina klasöründe kalır ve otomatik olarak kaldırılmaz.
-   **Tarama sırasında CPU kullanım sınırı** - Taramaların kullanmasına izin verilecek CPU miktarını sınırlandırmanıza (**1** ile **100** arasında) olanak sağlar.
-   **Arşiv dosyalarını tara** - Defender’ın Zip veya Cab dosyaları gibi arşivlenmiş dosyaları taramasına izin verir.
-   **Gelen posta iletilerini tarama** - Defender’ın cihaza gelen e-posta iletilerini taramasına izin verir.
-   **Tam tarama sırasında çıkarılabilir sürücüleri tarama** - Defender’ın USB çubukları gibi çıkarılabilir sürücüleri taramasına olanak sağlar.
-   **Tam tarama sırasında eşlenmiş ağ sürücülerini tarama** - Defender’ın eşlenmiş ağ sürücüsündeki dosyaları taramasına olanak sağlar.<br>Sürücüdeki dosyalar salt okunursa Defender bunlarda bulunan kötü amaçlı yazılımı kaldıramaz.
-   **Ağ klasörlerinden açılan dosyaları tarama** - Defender’ın paylaşılan ağ sürücülerindeki dosyaları (örneğin bir UNC yolundan erişilen dosyalar) taramasına olanak sağlar.
Sürücüdeki dosyalar salt okunursa Defender bunlarda bulunan kötü amaçlı yazılımı kaldıramaz.
-   **Bulut koruması** - Microsoft Etkin Koruma Hizmeti’nin yönettiğiniz cihazlardan kötü amaçlı yazılım etkinliğiyle ilgili bilgi almasına izin verir veya bunu engeller. Bu bilgi gelecekte hizmeti geliştirmek için kullanılır.
-   **Örnek göndermeden önce kullanıcılara sor** - Daha fazla analiz gerektirebilecek olası kötü amaçlı dosyaların Microsoft'a otomatik gönderilip gönderilmediğini denetler.
-   **Günlük hızlı tarama gerçekleştirilecek saat** - Her gün seçtiğiniz saatte gerçekleştirilecek olan bir hızlı tarama zamanlamanıza olanak sağlar.
-   **Gerçekleştirilecek sistem taraması türü** - Bir sistem taraması zamanladığınızda gerçekleştirilen tarama düzeyini belirtmenize izin verir.
-   **İstenmeyebilecek uygulamaları algıla**  – Windows şurada istenmeyebilecek uygulamalar algılandığında koruma düzeyini seçin:
        - **Engelle**
        - **Denetim** İstenmeyebilecek uygulamalar hakkında daha fazla bilgi için bkz. [bu konu](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus).
-   **Algılanan kötü amaçlı yazılım tehditlerinde yapılacaklar** – Defender'ın algıladığı her tehdit düzeyinde (Düşük, Orta, Yüksek ve Ciddi) yapmasını istediğiniz işlemleri belirtmek için bu seçeneği kullanın. Yapılabilecek işlemler:
    -   **Temizle**
    -   **Karantina**
    -   **Kaldır**
    -   **İzin ver**
    -   **Kullanıcı tanımlı**
    -   **Engelle**



## <a name="defender-exclusions"></a>Klasör Dışlamaları

-   **Taramaların ve gerçek zamanlı korumanın dışında tutulacak dosyalar ve klasörler** - Dışlama listesine **C:\Yol** veya **%ProgramFiles%\Yol\dosyaadı.exe** gibi bir veya birden çok dosya ve klasör ekler. Bu dosya ve klasörler gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.
-   **Taramaların ve gerçek zamanlı korumanın dışında tutulacak dosya uzantıları** - Dışlama listesine **jpg** veya **txt** gibi bir veya birden çok dosya uzantısı ekleyin. Bu uzantıya sahip dosyaların hiçbiri gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.
-   **Taramaların ve gerçek zamanlı korumanın dışında bırakılacak işlemler** - Dışlama listesine **.exe**, **.com** veya **.scr** türünde bir veya birden çok işlem ekleyin. Bu işlemleri gerçek zamanlı veya zamanlanmış hiçbir taramaya katılmaz.


## <a name="network-proxy"></a>Ağ proxy’si

-   **Proxy ayarlarını otomatik olarak algıla** - Etkinleştirildiğinde, cihaz bir PAC betiğinin yolunu bulmayı dener.
-   **Proxy betiği kullan** - Proxy sunucusunu yapılandırmak için PAC betiği yolu belirtmek isterseniz bu seçeneği belirleyin.
    -   **Kurulum betiği adresi URL’si** - Proxy sunucusunu yapılandırmak için kullanmak istediğiniz bir PAC betiğinin URL’sini girin.
-   **El ile proxy sunucusu kullan** - Proxy sunucusu bilgilerini el ile sağlamak istiyorsanız, bunu seçin.
    -   **Adres** - Proxy sunucusu adını veya IP adresini girin.
    -   **Bağlantı noktası numarası** - Proxy sunucunuzun bağlantı noktası numarasını girin.
    -   **Proxy özel durumları** - Proxy sunucusunu kullanmaması gereken herhangi bir URL girin. Her birini ayırmak için noktalı virgül kullanın.
    -   **Yerel adres için proxy sunucusunu atla** - İntranetinizde yerel adresler için proxy sunucuyu kullanmak istemiyorsanız bu seçeneği etkinleştirin.


## <a name="windows-spotlight"></a>Windows Spot


- **Windows Spot** – Windows 10 cihazlarda tüm Windows Spot işlevselliğini engellemek için bu ayarı kullanın. Bu ayarı engellerseniz aşağıdaki ayarlar kullanılamaz.
    - **Kilitleme ekranında Windows Spot** – Windows Spot’un cihaz kilitleme ekranında bilgi görüntülemesini durdurun.
    - **Windows Spot’ta üçüncü taraf önerileri** – Windows Spot’un Microsoft tarafından yayımlanmayan içeriği önermesini durdurun.
    - **Tüketici Özellikleri** - Başlat menüsü önerileri ve üyelik bildirimleri gibi özellikleri engellemenizi sağlar.
    - **Windows İpuçları** - Windows’da görüntülenen açılır ipuçlarını engellemenize izin verir.
    - **İşlem merkezinde Windows Spot** – Yeni uygulama veya güvenlik içeriği gibi Windows Spot önerilerinin Windows İşlem Merkezi'nde görünmesini engelleyin.
    - **Windows Spot kişiselleştirme** – Windows Spot’un sonuçları bir cihazın kullanımına göre kişiselleştirmesini durdurun.
    - **Windows karşılama deneyimi** – Kullanıcıya yeni veya güncelleştirilmiş özellikler hakkında bilgi gösteren Windows karşılama deneyimini engelleyin.


## <a name="projection"></a>Projeksiyon

- **Kablosuz ekran alıcılarından kullanıcı girişi** -Kablosuz ekran alıcılarından kullanıcı girişini engeller.
- **Bu bilgisayara yansıtma** - Diğer cihazların yansıtma için bilgisayarı bulmasını engeller.
- **Eşleştirme için PIN gerektir** - Bir projeksiyon cihazına bağlanırken PIN gerekmesini sağlayın.

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