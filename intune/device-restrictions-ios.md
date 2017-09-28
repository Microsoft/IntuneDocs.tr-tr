---
title: "iOS için Intune cihaz kısıtlamaları ayarları"
titleSuffix: Azure portal
description: "iOS cihazlarında cihaz ayarlarını ve işlevselliğini denetlemek için kullanabileceğiniz Intune ayarlarını öğrenin.\""
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 09/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 73590192-54ca-4833-9f1d-83e1b654399f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ff2c9943a04ec02a83e821a65e1307e311a9d1c0
ms.sourcegitcommit: 4ce095c0c3fa2e42cf76207b6ff8edf1fe397165
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2017
---
# <a name="ios-device-restriction-settings-in-microsoft-intune"></a>Microsoft Intune’da iOS cihaz kısıtlama ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="general"></a>Genel
    
-   **Tanılama verileri gönderme** - Cihazın Apple’a tanılama verileri göndermesine izin verin veya bunu engelleyin.
-   **Ekran yakalama** - Kullanıcının ekran içeriğini resim olarak yakalamasına izin verin.
    - **Classroom uygulamasıyla ekranı uzaktan izleme (yalnızca denetimli)** - Apple Classroom uygulamasının iOS cihazlarda ekranı izlemesine izin verin veya bunu engelleyin.
    - **Classroom uygulaması tarafından istem olmadan ekranı izleme (yalnızca denetimli)** - İzin veriliyorsa öğretmenler öğrencilerin bilgisi olmadan Classroom uygulamasını kullanarak, öğrencilerin iOS cihazlarının ekranını sessizce izleyebilir.
-   **Güvenilmeyen TLS sertifikaları** - Cihazda güvenilmeyen Aktarım Katmanı Güvenliği sertifikalarına izin verin.
-   **Kurumsal uygulama güveni** - Kullanıcının uygulama mağazasından indirilmemiş uygulamalara güvenmeyi seçmesine izin verir.
- **Hesap değişikliği (yalnızca denetimli)** - Engellendiğinde, kullanıcının iOS ayarları uygulamasından cihaza özgü ayarları değiştirmesini (yeni cihaz hesapları oluşturma ve kullanıcı adını veya parolayı değiştirme gibi) önler.
Bu durum, Posta, Kişiler, Takvim, Facebook ve Twitter gibi iOS ayarları uygulamasından erişilebilen ayarlar için de geçerlidir. Hesap ayarları iOS ayarları uygulamasından yapılandırılamayan uygulamalar (Microsoft Outlook uygulaması gibi) için geçerli değildir.
- **Cihaz ayarlarında kısıtlamaları etkinleştirme (yalnızca denetimli)** - Kullanıcının cihazda cihaz kısıtlamalarını (ebeveyn denetimleri) yapılandırmasına izin verin.
- **Cihazdaki tüm içerikleri ve ayarları silme seçeneğinin kullanımı (yalnızca denetimli)** - Kullanıcının, cihazda tüm içeriği ve ayarları silme seçeneğini kullanmasına izin verin.
- **Cihaz adı değişikliği (yalnızca denetimli)** - Kullanıcının cihazın adını değiştirmesine izin verin.
- **Bildirim ayarlarının değiştirilmesi (yalnızca denetimli)** - Kullanıcının cihazın bildirim ayarlarını değiştirmesine izin verin.
- **Duvar kağıdı değişikliği (yalnızca denetimli)** - Kullanıcının cihazın duvar kağıdını değiştirmesine izin verin.
- **Kurumsal uygulama güven ayarlarının değiştirilmesi (yalnızca denetimli)** - Kullanıcının uygulama mağazasından indirilmemiş uygulamalara güvenmeyi seçmesine izin verir.
- **Yapılandırma profilindeki değişiklikler** - Kullanıcının yapılandırma profilleri yüklemesine izin verin.
- **Etkinleştirme Kilidi (yalnızca denetimli)** - Denetimli iOS cihazlarda Etkinleştirme Kilidi’ni etkinleştirin.

## <a name="password"></a>Parola
-   **Parola** - Son kullanıcının cihaza erişmek için parola girmesini zorunlu tutun.
    -   **Basit parolalar** - 0000 ve 1234 gibi basit parolalara izin verin.
    -   **Gerekli parola türü** - Gerekli parola türünü belirtin (yalnızca sayısal veya alfasayısal gibi).
    -   **Paroladaki alfasayısal olmayan karakter sayısı** - Parolada bulunması gereken simge karakterlerinin sayısını belirtin (**#** veya **@** gibi).
    -   **En az parola uzunluğu** - Parolada bulunacak karakter sayısı için alt sınır belirtin.
    -   **Cihaz silinmeden önceki oturum açma hatası sayısı** - Bu ayar cihazı temizlemeden önce gerçekleşebilecek başarısız oturum açma girişimlerinin sayısını belirtin.
    -   **Ekran kilitlendikten sonra parola istenene kadar geçmesi gereken, işlem yapılmayan dakika sayısı**<sup>1</sup> - Kullanıcının parolasını yeniden girmesi gerekmeden önce cihazın ne kadar süreyle boşta kalabileceğini belirtin.
    -   **Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı**<sup>1</sup> - Cihazın ekranı kapatılmadan önce beklenecek dakika sayısını belirtin.
    -   **Parola kullanım süresi sonu (gün)** - Cihaz parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını belirtin.
    -   **Önceki parolaların yeniden kullanılmasını engelle** - Önceden kullanılmış ve cihaz tarafından anımsanacak olan parola sayısını belirtin.
    -   **Parmak iziyle kilit açma** - Uyumlu cihazların kilidini açmak için parmak izi kullanmaya izin verin.
- **Geçiş kodu değişikliği (yalnızca denetimli)** - Geçiş kodunun değiştirilmesi, eklenmesi veya kaldırılmasını durdurur. 
    - **Parmak izi değişikliği (yalnızca denetimli)** - Kullanıcının TouchID ayarlarını değiştirmesi, eklemesi veya kaldırmasını engeller.

<sup>1</sup>**Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı** ve **Ekran kilitlendikten sonra parola istenene kadar geçmesi gereken, işlem yapılmayan dakika sayısı**, ayarlarını yapılandırdığınızda, bunlar sırayla uygulanır. Örneğin, her iki ayarın da değerini **5** dakikaya ayarlarsanız, ekran 5 dakika sonra otomatik olarak kapanır ve cihazın kilitlenmesi için 5 dakika daha geçmesi gerekir. Ancak, kullanıcı ekranı el ile kapatırsa ikinci ayar hemen uygulanır. Aynı örnekte, kullanıcı ekranı kapattıktan sonraki 5 dakikanın sonunda cihaz kilitlenir.

## <a name="locked-screen-experience"></a>Kilit Ekranı Deneyimi

-   **Cihaz kilitliyken Denetim Merkezi erişimi** - Cihaz kilitliyken kullanıcının denetim merkezi uygulamasına erişmesine izin verin.
-   **Cihaz kilitliyken bildirimler** - Kullanıcının, cihazın kilidini açmadan bildirimler görünümüne erişime izin verin.
-   **Cihaz kilitliyken Passbook** - Cihaz kilitliyken kullanıcının Passbook uygulamasına erişmesine izin verin.
-   **Cihaz kilitliyken Bugün görünümü** - Cihaz kilitliyken kullanıcının Bugün görünümünü görmesine izin verin.

## <a name="app-store-doc-viewing-gaming"></a>Uygulama Mağazası, Belge Görüntüleme, Oyun


-   **Uygulama mağazası** - Denetimli cihazlarda uygulama mağazasına erişimi engelleyin.
    - **App Store'dan uygulama yükleme (yalnızca denetimli)** - Cihaz ana ekranından uygulama mağazasını engeller. Son kullanıcılar, uygulamaları yüklemek için iTunes’u veya Apple Configurator aracını kullanmaya devam edebilir.
    - **Otomatik uygulama yüklemeleri (yalnızca denetimli)** - Başka bir iOS cihazında satın alınan uygulamaların bu cihaza yüklenmesini durdurur.
-   **Uygulama mağazasına erişim için parola** - Kullanıcının uygulama mağazasını ziyaret etmeden önce parola girmesini isteyin.
-   **Uygulama içi satın almalar** - Çalışan bir uygulamanın içinden mağazada alışveriş yapılmasına izin verin.
-   **Müstehcen nitelikli iTunes müziği, podcast'i veya haber içeriği (yalnızca denetimli mod)** - Cihazın mağazadaki yetişkinlere yönelik olarak derecelendirilmiş içeriğe erişmesine izin verin.
-   **iBook mağazasından 'Erotik' olarak işaretlenmiş içeriği indirme** - Kullanıcının “Erotik” kategorisindeki kitapları indirmesine izin verin.
-   **Yönetilmeyen uygulamalarda kurumsal belgeleri görüntüleme** - Kurumsal belgelerin tüm uygulamalarda görüntülenmesine izin verin.<br>**Örnek:** Kullanıcıların OneDrive uygulamasından Dropbox’a dosya kaydetmesini engellemek istiyorsunuz. Bu ayarı hayır olarak yapılandırın. Cihaz, ilkeyi aldıktan sonra (örneğin, yeniden başlatıldıktan sonra) artık kaydetmeye izin vermeyecektir.
-   **Kurumsal olmayan belgeleri kurumsal uygulamalarda görüntüleme** - Tüm belgelerin şirketin yönetilen uygulamalarında görüntülenmesine izin verin.
-   **AirDrop'u yönetilmeyen uygulama olarak değerlendir** - Yönetilen uygulamaların Airdrop aracılığıyla veri göndermesini durdurur.
-   **Game Center'da arkadaş ekleme (yalnızca denetimli)** - Kullanıcının Game Center'da arkadaş eklemesine izin verin.
-   **Game Center (yalnızca denetimli)** - Game Center uygulamasının kullanımını engelleyin veya etkinleştirin.
-   **Çok oyunculu oyunlar (yalnızca denetimli)** - Kullanıcının cihazda çok oyunculu oyunlar oynamasına izin verin.
-   **Derecelendirme bölgesi** - İzin verilen indirmeleri yapılandırmak istediğiniz derecelendirme bölgesini seçin ve sonra da **Filmler** ve **TV Programları** için izin verilen derecelendirmeleri seçin.
-   **Uygulamalar** - Kullanıcıların indirebileceği uygulamaların yaş derecelendirmesini seçin veya **Tüm Uygulamalara İzin Ver**’i seçebilirsiniz.

## <a name="built-in-apps"></a>Yerleşik Uygulamalar

-   **Kamera** - Cihazdaki kameranın kullanılıp kullanılamayacağını seçin. 
    -   **FaceTime** - Cihazda FaceTime uygulamasının kullanılmasına izin verin.
-   **Siri** - Cihazda Siri ses yardımcısının kullanımına izin verin.
    -   **Cihaz kilitliyken Siri** - Cihaz kilitliyken cihazda Siri ses yardımcısının kullanımına izin verin.
    -   **Siri küfür filtresi (yalnızca denetimli)** - Siri’nin küfürlü dil dikte etmesini veya konuşmasını engeller.
    -   **Siri'nin İnternet'ten kullanıcı tarafından oluşturulan içerikleri sorgulaması (yalnızca denetimli)** - Siri’nin soruları yanıtlamak için web sitelerine erişmesine izin verin.
- **Apple News (yalnızca denetimli)** - Apple News uygulamasının kullanılmasına izin verin.
- **iBooks mağazası (yalnızca denetimli)** - Kullanıcının iBooks mağazasındaki kitaplara göz atmasına ve bunları satın almasına izin verin.
- **Cihazdaki mesajlar uygulaması (yalnızca denetimli)** - Kısa mesajları göndermek ve okumak için Mesajlar uygulamasının kullanılmasına izin verin.
- **Podcast'ler (yalnızca denetimli)** - Podcast’ler uygulamasının kullanılmasına izin verin.
- **Music hizmeti (yalnızca denetimli)** - Apple Music uygulamasının kullanılmasına izin verin.
- **iTunes Radio hizmeti (yalnızca denetimli)** - iTunes Radio uygulamasının kullanılmasına izin verin.
- **Arkadaşlarımı Bul uygulamasının ayarlarında yapılan değişiklikler (yalnızca denetimli)** - Kullanıcının Arkadaşlarımı Bul uygulamasının ayarlarını değiştirmesine izin verin.
- **Spotlight aramasının İnternet'ten sonuç döndürmesi (yalnızca denetimli)** - Spotlight aramasının daha fazla sonuç sağlamak için İnternet’e bağlanmasına izin verin.

## <a name="restricted-apps"></a>Kısıtlı uygulamalar

Kısıtlı uygulamalar listesinde, aşağıdaki listelerden birini yapılandırabilirsiniz:

**Yasak uygulamalar** listesi - Intune tarafından yönetilmeyen ve kullanıcıların yüklemesine ve çalıştırmasına izin verilmeyen uygulamaları listeleyin.
**Onaylı uygulamalar** listesi - Kullanıcıların yüklemesine izin verilen uygulamaları listeleyin. Kullanıcılar listelenmeyen uygulamaları yüklememelidir. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir.

Kullanıcıların izin verilmeyen uygulamaları yüklemesi engellenmez, ancak yüklemeleri durumunda bu size bildirilir.

Listeyi yapılandırmak için **Ekle**’ye tıklayın, sonra da tercih ettiğiniz bir ad (isteğe bağlı olarak uygulama yayımcısı) ve uygulamanın uygulama mağazasındaki URL'sini belirtin.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Mağazadaki uygulamanın URL’sini belirtme

Uygulamalar listesinde bir uygulama URL'si belirtmek için aşağıdaki biçimi kullanın:

Bir arama motoru kullanarak, iTunes App Store'dan kullanmak istediğiniz uygulamayı bulun ve uygulamanın sayfasını açın.
Sayfanın URL'sini kopyalayın ve bunu, onaylı veya yasak uygulamalar listesini ya da bilgi noktası modunda çalıştırmak istediğiniz uygulamayı yapılandırmak için gereken URL olarak kullanın.
Kısıtlı uygulama ayarlarını içeren cihaz profilleri kullanıcı gruplarına atanmalıdır.

Örnek: iPad için Microsoft Word ifadesini aratın. Kullandığınız URL https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8 olacaktır.

> [!Note]
> iTunes yazılımını kullanarak da uygulamayı bulabilir ve ardından **Bağlantıyı Kopyala** komutuyla uygulama URL'sini alabilirsiniz.



### <a name="additional-options"></a>Ek seçenekler

Ayrıca, **İçeri Aktar**’a tıklayarak listeyi <*uygulama url’si*>, <*uygulama adı*>, <*uygulama yayımcısı*> biçimindeki bir csv dosyasından doldurabilir veya **Dışarı Aktar**’a tıklayarak kısıtlı uygulama listesinin içeriğiyle, aynı biçimde bir csv dosyası oluşturabilirsiniz.

## <a name="show-or-hide-apps-supervised-only"></a>Uygulamaları gösterme veya gizleme (yalnızca denetimli)

Uygulamaları gösterme veya gizleme listesinde, aşağıdaki listelerden birini yapılandırabilirsiniz (iOS 9.3 veya üstünü çalıştıran denetimli cihazlar gerekir).

**Gizli uygulamalar** listesi - Kullanıcılardan gizlenecek uygulamaların listesini belirtin. Kullanıcılar bu uygulamaları görüntüleyemez veya başlatamaz.
**Görünür uygulamalar** listesi - Kullanıcıların görüntüleyebileceği ve başlatabileceği uygulamaların listesini belirtin. Başka hiçbir uygulama görüntülenemez veya başlatılamaz.

Listeyi yapılandırmak için **Ekle**’ye tıklayın, sonra da tercih ettiğiniz bir ad (isteğe bağlı olarak uygulama yayımcısı) ve uygulamanın uygulama mağazasındaki URL'sini belirtin.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Mağazadaki uygulamanın URL’sini belirtme

Uygulamalar listesinde bir uygulama URL'si belirtmek için aşağıdaki biçimi kullanın:

Bir arama motoru kullanarak, iTunes App Store'dan kullanmak istediğiniz uygulamayı bulun ve uygulamanın sayfasını açın.
Sayfanın URL'sini kopyalayın ve bunu, onaylı veya yasak uygulamalar listesini ya da bilgi noktası modunda çalıştırmak istediğiniz uygulamayı yapılandırmak için gereken URL olarak kullanın.

Örnek: iPad için Microsoft Word ifadesini aratın. Kullandığınız URL https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8 olacaktır.

> [!Note]
> iTunes yazılımını kullanarak da uygulamayı bulabilir ve ardından **Bağlantıyı Kopyala** komutuyla uygulama URL'sini alabilirsiniz.

### <a name="additional-options"></a>Ek seçenekler

Ayrıca, **İçeri Aktar**’a tıklayarak listeyi <*uygulama url’si*>, <*uygulama adı*>, <*uygulama yayımcısı*> biçimindeki bir csv dosyasından doldurabilir veya **Dışarı Aktar**’a tıklayarak gizli veya görünür uygulama listesinin içeriğiyle, aynı biçimde bir csv dosyası oluşturabilirsiniz.


## <a name="wireless"></a>Kablosuz
-   **Veri dolaşımı** - Cihaz cep telefonu şebekesindeyken veri dolaşımına izin verin.
-   **Dolaşım sırasında genel arka planda alma** - Cihazın, cep telefonu şebekesinde dolaşımdayken e-posta gibi verileri almasına izin verin.
-   **Sesli arama** - Cihazda sesli arama özelliğinin kullanımına izin verin.
-   **Ses dolaşımı** - Cihaz cep telefonu şebekesindeyken ses dolaşımına izin verin.
-   **Uygulama hücresel veri kullanımı ayarlarında yapılan değişiklikler (yalnızca denetimli)** - Kullanıcının hangi uygulamaların hücresel veri kullanabileceğini denetlemesine izin verin.
-   **Kişisel Etkin Nokta** - Cihazın kişisel etkin nokta olarak kullanılmasına izin vermeyin. Bu ayar, bazı operatörler ile uyumlu olmayabilir.
-   **Yapılandırma profilleri kullanarak yalnızca Wi-Fi ağlarına katılma (yalnızca denetimli)** - Cihazın yalnızca Intune Wi-Fi profili ile yapılandırılmış Wi-Fi ağlarına katılmasına izin verin.

- **Hücresel kullanım kuralları (yalnızca yönetilen uygulamalar)** - Hücresel ağa bağlıyken yönetilen uygulamaların kullanabileceği veri türlerini tanımlamanızı sağlar. Aşağıdakilerden birini seçin:
    - **Hücresel veri kullanımını engelle**
    - **Dolaşımdayken hücresel veri kullanımını engelle**

## <a name="connected-devices"></a>Bağlı Cihazlar

-   **AirDrop (yalnızca denetimli)** - Yakındaki cihazlarla içerik değişimi için AirDrop özelliğinin kullanılmasına izin verin.
-   **Apple Watch eşleştirme (yalnızca denetimli)** - Cihazın bir Apple Watch ile eşleşmesine izin verin.
-   **Eşleştirilen Apple Watch için bilek algılama** - Etkinleştirildiğinde, Apple Watch takılmadığında bildirim görüntülemez.
-   **Bluetooth değişikliği (yalnızca denetimli)** - Son kullanıcının cihazda Bluetooth ayarlarını değiştirmesini engelleyin.
-   **iOS cihazının eşleştirilebildiği cihazları kontrol etmek için konak eşleştirmesi (yalnızca denetimli)** - Yöneticinin bir iOS cihazının hangi cihazlarla eşleşebileceğini denetleyebilmesi için konak eşleştirmeye izin verin.
-   **Giden AirPlay istekleri için eşleştirme parolası isteme** - Kullanıcının diğer Apple cihazlarına içerik akışı sağlamak üzere AirPlay’i kullanması için, eşleştirme parolası isteyin.

## <a name="keyboard-and-dictionary"></a>Klavye ve Sözlük

-   **Sözcük tanımı arama (yalnızca denetimli)** - Bir sözcüğü vurgulayıp tanımını aramanıza olanak tanıyan iOS özelliğine izin verin.
-   **Metni tahmin eden klavyeler (yalnızca denetimli)** - Kullanıcının, isteyebileceği sözcükleri öneren öngörülü klavyeler kullanmasına izin verin.
-   **Otomatik düzeltme (yalnızca denetimli)** - Cihazın yanlış yazılan sözcükleri otomatik düzeltmesine izin verir.
-   **Klavye yazım denetimi (yalnızca denetimli)** - Cihazın yazım denetimcisine izin verir.
-   **Klavye kısayolları (yalnızca denetimli)** - Klavye kısayollarının kullanılmasına izin verir.
-   **Dikte (yalnızca denetimli)** - Metin girmek için kullanıcının sesli giriş yapmasını durdurur.

## <a name="cloud-and-storage"></a>Bulut ve Depolama
-   **iCloud'a yedekle** - Kullanıcının cihazı iCloud’a yedeklemesine izin verin.
-   **iCloud'a belge eşitleme (yalnızca denetimli)** - iCloud depolama alanınızda belge ve anahtar-değer eşitlemesine izin verin.
-   **iCloud'a fotoğraf akışı eşitlemesi** - Kullanıcıların fotoğrafların iCloud’a eşitlenmesine ve tüm kullanıcıların cihazlarında kullanılabilir olmasına olanak tanıyan **Fotoğraf Akışım**’ı cihazlarında etkinleştirmesine olanak tanır.
-   **Şifrelenmiş yedekleme** - Tüm cihaz yedeklemelerinin şifrelenmesini zorunlu tutun.
-   **iCloud Fotoğraf Arşivi** - **Hayır** seçeneği ayarlanırsa kullanıcıların fotoğraflar ve videoları bulutta depolamasını sağlayan iCloud fotoğraf kitaplığının kullanımı devre dışı bırakılır.    Bu ayar **Hayır** olarak belirlenirse iCloud Fotoğraf Arşivi'nden cihaza tamamen indirilmeyen tüm fotoğraflar cihazdan kaldırılır.
-   **Yönetilen uygulamaları bulutla eşitleme** - Intune ile yönettiğiniz uygulamaların, kullanıcının iCloud hesabıyla veri eşitlemesine izin verin.
-   **Paylaşılan fotoğraf akışı** - Cihazda **iCloud Fotoğraf Paylaşımı**’nı devre dışı bırakmak için **Hayır** olarak ayarlayın.
-   **Etkinlik devamlılığı** - Kullanıcının bir iOS cihazında başladığı çalışmayı başka bir iOS veya macOS cihazında sürdürmesine izin verin (İletim).

## <a name="autonomous-single-app-mode-supervised-only"></a>Otonom tek uygulama modu (yalnızca denetimli)

Bu ayarları kullanarak iOS cihazlarını, belirtilen uygulamaları otonom tek uygulama modunda çalışacak şekilde yapılandırabilirsiniz. Bu mod yapılandırılıp uygulama çalıştırıldığında cihaz yalnızca belirtilen uygulamayı çalıştıracak şekilde kilitlenir. Buna örnek olarak kullanıcıların cihazda test çözmesini sağlayan bir uygulama verilebilir. Uygulama eylemleri tamamlandığında veya bu ilkeyi kaldırdığınızda cihaz normal durumuna döner.

### <a name="settings"></a>Ayarlar

- **Uygulama adı** - Uygulamanın bu dikey penceredeki uygulamalar listesinde görünecek adını girin.
- **Uygulama Paket Kimliği** - Uygulamanın paket kimliğini girin. Yardım için bu konu başlığındaki **Yerleşik iOS uygulamaları için Paket Kimliği başvurusu** konusuna bakın.

Her uygulama adını ve paket kimliğini belirttikten sonra listeye eklemek için **Ekle**’yi seçin.

- **İçeri aktarma** - Uygulama adları ve ilgili paket kimliklerinin listesini içeren virgülle ayrılmış değerler (.csv) dosyasını içeri aktarın.
- **Dışarı aktarma** - Bir virgülle ayrılmış değerler (.csv) dosyasına yapılandırdığınız uygulama adlarını ve ilgili paket kimliklerini dışarı aktarın.

### <a name="bundle-id-reference-for-built-in-ios-apps"></a>Yerleşik iOS uygulamaları için Paket Kimliği başvurusu

Bu liste, bazı yaygın yerleşik iOS uygulamalarının paket kimliğini gösterir. Diğer uygulamaların paket kimliğini bulmak için yazılım satıcınıza başvurun.

```
,com.apple.AppStore,App Store,Apple
,com.apple.calculator,Calculator,Apple
,com.apple.mobilecal,Calendar,Apple
,com.apple.camera,Camera,Apple
,com.apple.mobiletimer,Clock,Apple
,com.apple.compass,Compass,Apple
,com.apple.MobileAddressBook,Contacts,Apple
,com.apple.facetime,FaceTime,Apple
,com.apple.mobileme.fmf1,Find Friends,Apple
,com.apple.mobileme.fmip1,Find iPhone,Apple
,com.apple.gamecenter,Game Center,Apple
,com.apple.mobilegarageband,GarageBand,Apple
,com.apple.Health,Health,Apple
,com.apple.iBooks,iBooks,Apple
,com.apple.MobileStore,iTunes Store,Apple
,com.apple.itunesu,iTunes U,Apple
,com.apple.Keynote,Keynote,Apple
,com.apple.mobilemail,Mail,Apple
,com.apple.MapsMaps,Apple
,com.apple.MobileSMS,Messages,Apple
,com.apple.Music,Music,Apple
,com.apple.news,News,Apple
,com.apple.mobilenotes,Notes,Apple
,com.apple.Numbers,Numbers,Apple
,com.apple.Pages,Pages,Apple
,com.apple.Photo-Booth,Photo Booth,Apple
,com.apple.mobileslideshow,Photos,Apple
,com.apple.podcasts,Podcasts,Apple
,com.apple.reminders,Reminders,Apple
,com.apple.mobilesafariSafari,Apple
,com.apple.Preferences,Settings,Apple
,com.apple.stocks,Stocks,Apple
,com.apple.tips,Tips,Apple
,com.apple.videos,Videos,Apple
,com.apple.VoiceMemos,VoiceMemos,Apple
,com.apple.Passbook,Wallet,Apple
,com.apple.Bridge,Watch,Apple
,com.apple.weather,Weather,Apple


```


## <a name="kiosk-supervised-only"></a>Bilgi noktası (yalnızca denetimli)
-   **Bilgi noktası modunda çalışan uygulama** - Intune’a eklediğiniz bir uygulamayı belirtmek için **Yönetilen Uygulama**’yı veya mağazadaki bir uygulamanın URL’sini belirtmek için **Mağaza Uygulaması**’nı seçin. Cihazda başka hiçbir uygulamanın çalışmasına izin verilmez. Daha fazla yardım için, bu konunun devamındaki “Uygulama mağazalarının URL’lerini belirtme” bölümüne bakın.
    -   **Yardımlı dokunma** - Ekran hareketlerini gerçekleştirmekte zorlanabilecek kullanıcıların bunları yapmasına yardımcı olan **Yardımlı Dokunma** erişilebilirlik ayarını etkinleştirin veya devre dışı bırakın.
    -   **Renkleri ters çevir** - Görsel engelli kullanıcılara yardımcı olmak için ekranı ayarlayan Renkleri Ters Çevir erişilebilirlik ayarını etkinleştirin veya devre dışı bırakın.
    -   **Mono ses** - Mono ses erişilebilirlik ayarını etkinleştirin veya devre dışı bırakın.
    -   **VoiceOver** - Cihazın ekranındaki metinleri sesli olarak okuyan **VoiceOver** erişilebilirlik ayarını etkinleştirin veya devre dışı bırakın.
    -   **Yakınlaştırma** - Kullanıcının cihazın ekranını dokunarak yakınlaştırmasına olanak sağlayan **Yakınlaştırma** erişilebilirlik ayarını etkinleştirin veya devre dışı bırakın.
    -   **Otomatik kilitleme** - Cihazın otomatik olarak kilitlenmesini etkinleştirin veya devre dışı bırakın.
    -   **Ses düğmesi** - Cihazda ses açma/kapama (sessiz) düğmesini etkinleştirin veya devre dışı bırakın.
    -   **Ekran döndürme** - Kullanıcı cihazı döndürdüğünde ekran yönünü değiştirmeyi etkinleştirin veya devre dışı bırakın.
    -   **Ekran uyku düğmesi** - Ekranda uykuya geçme ve uyandırma düğmesini etkinleştirin veya devre dışı bırakın.
    -   **Dokunma** - Cihazda dokunmatik ekranı etkinleştirin veya devre dışı bırakın.
    -   **Ses düzeyi düğmeleri** - Cihazdaki ses düzeyi düğmelerinin kullanımını etkinleştirin veya devre dışı bırakın.
    -   **Yardımlı dokunma denetimi** - Kullanıcının yardımcı dokunma işlevini ayarlamasına olanak sağlayan yardımcı dokunma ayarlarını etkinleştirin veya devre dışı bırakın.
    -   **Renkleri tersine çevirme denetimi** - Kullanıcının renkleri ters çevirme işlevini ayarlamasına olanak sağlayan renkleri ters çevirme ayarlarını etkinleştirin veya devre dışı bırakın.
    -   **Seçilen metinde konuşma** - Kullanıcının seçtiği metni sesli okuyabilen Seçimi Seslendir erişilebilirlik ayarını etkinleştirin veya devre dışı bırakın.
    -   **VoiceOver denetimi** - Kullanıcının VoiceOver işlevini ayarlamasına olanak tanıyan seslendirme ayarlarını (örneğin, ekran üzerindeki metnin ne kadar hızlı okunacağı) etkinleştirin veya devre dışı bırakın.
    -   **Yakınlaştırma denetimi** - Kullanıcının yakınlaştırma işlevini ayarlamasını sağlayan yakınlaştırma ayarlarını etkinleştirin veya devre dışı bırakın.

>[!NOTE]
> Bir iOS cihazını bilgi noktası modunda yapılandırabilmek için, önce Apple Configurator aracını veya Apple Cihaz Kayıt Programı’nı kullanarak cihazı denetimli moda almanız gerekir. Apple Configurator aracı hakkında daha fazla bilgi için Apple belgelerinize bakın.
>Belirttiğiniz iOS uygulaması siz profil atadıktan sonra yüklendiyse cihaz, yeniden başlatılana kadar bilgi noktası moduna girmez.

## <a name="safari"></a>Safari
-   **Safari (yalnızca denetimli)** - Cihazda Safari tarayıcısının kullanılıp kullanılamayacağını belirtin.
-   **Otomatik doldur** - Kullanıcının tarayıcıdaki otomatik tamamlama ayarlarını değiştirmesine izin verin.
-   **Tanımlama bilgileri** - Tarayıcının tanımlama bilgilerini kullanmasına izin verin.
-   **JavaScript** - Tarayıcıda Java betiğinin çalıştırılmasına izin verin.
-   **Dolandırıcılık uyarıları** - Tarayıcıda dolandırıcılık uyarılarına izin verin.
-   **Açılır pencereler** - Tarayıcı açılır pencere engelleyicisini etkinleştirin veya devre dışı bırakın.


## <a name="domains"></a>Domains

### <a name="unmarked-email-domains"></a>İşaretsiz e-posta etki alanları

**E-posta Etki Alanı URL'si** alanında, listeye bir veya daha fazla URL ekleyin. Son kullanıcılar, yapılandırdığınız etki alanları dışındaki bir etki alanından e-posta aldığında, bu e-posta iOS Mail uygulamasında güvenilmeyen olarak işaretlenir.


### <a name="managed-web-domains"></a>Yönetilen web etki alanları

**Web Etki Alanı URL'si** alanında, listeye bir veya daha fazla URL ekleyin. Belgeler belirttiğiniz etki alanlarından indirildiğinde yönetilen belgeler olarak değerlendirilir. Bu ayar yalnızca Safari tarayıcısı kullanılarak indirilen belgeler için geçerlidir.


### <a name="safari-password-auto-fill-domains"></a>Safari otomatik parola doldurma etki alanları

**Etki Alanı URL'si** alanında, listeye bir veya daha fazla URL ekleyin. Kullanıcılar yalnızca bu listedeki URL’lerdeki parolaları kaydedebilir. Bu ayar yalnızca Safari tarayıcısı ve denetimli moddaki iOS 9.3 ve üzeri cihazlar için geçerlidir. Herhangi bir URL belirtmezseniz, parolalar tüm web sitelerinden kaydedilebilir.
