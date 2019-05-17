---
title: Microsoft Intune'da iOS ayarlarını kullanma - Azure | Microsoft Docs
titleSuffix: ''
description: Parola gereksinimlerini belirleme, kilit ekranını denetleme, yerleşik uygulamaları kullanma, kısıtlanmış veya onaylı uygulamalar ekleme, Bluetooth cihazlarını yönetme, yedekleme ve depolama amacıyla buluta bağlanma, bilgi noktası modunu etkinleştirme, etki alanı ekleme ve kullanıcıların Safari web tarayıcısıyla etkileşim kurma şeklini denetleme gibi özellikleri kısıtlamak amacıyla Microsoft Intune'daki iOS cihazları için ayar ekleme, yapılandırma veya oluşturma işlemlerini gerçekleştirin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/02/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0d0623e9d12132ac470813d65510bc2c76379109
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59898641"
---
# <a name="ios-device-settings-to-allow-or-restrict-features-using-intune"></a>Intune'u kullanarak özelliklere izin vermeyi veya bunları kısıtlamayı sağlayan iOS cihaz ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makalede iOS cihazlarında denetleyebileceğiniz farklı ayarlar listelenir ve açıklanır. Mobil cihaz yönetimi (MDM) çözümünüz kapsamında bu ayarları kullanabilir ve bu sayede özellikleri etkinleştirip devre dışı bırakabilir, parola kuralları uygulayabilir, belirli uygulamalara izin verebilir veya bunları kısıtlayabilir ve çok daha fazlasını yapabilirsiniz.

Bu ayarlar, Intune'da bir cihaz yapılandırma profiline eklenir ve daha sonra iOS cihazlarınıza atanır veya dağıtılır.

## <a name="before-you-begin"></a>Başlamadan önce

[Cihaz kısıtlamaları yapılandırma profili oluşturma](device-restrictions-configure.md#create-the-profile).

## <a name="general"></a>Genel

- **Kullanım verilerini paylaşma**: Cihazın Apple’a tanılama ve kullanım verileri göndermesini engellemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı bu verilerin gönderilmesine izin verir.
  - **Tanılama gönderimi ayarlarının değiştirilmesi (yalnızca denetimli)**: **Engelle** ayarı kullanıcının **Tanılama ve Kullanım** (cihaz ayarları) altındaki tanılama gönderimi ve uygulama analizi ayarlarını değiştirmesini engeller. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının bu cihaz ayarlarını değiştirmesine izin verir.

    Bu özellik şu platformlarda geçerlidir:  
    - iOS 9.3.2 ve üzeri

- **Ekran yakalama**: Cihazda ekran görüntülerini veya ekran yakalamalarını önlemek için **Engelle**'yi seçin. iOS 9.0 ve üzeri sürümlerde, bu seçenek ekran kayıtlarını engellemeyi de içerir. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının ekran içeriğini bir resim veya video olarak yakalamasına olanak tanır.
  - **Classroom uygulamasıyla ekranı uzaktan izleme (yalnızca denetimli)**: Classroom uygulamasının cihazda ekranı uzaktan görüntülemesini önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı Apple Classroom uygulamasının ekranı görüntülemesine izin verir.

    Bu özellik şu platformlarda geçerlidir:  
    - iOS 9.3 ve üzeri

  - **Classroom uygulamasıyla kullanıcıya sormadan ekranı izleme (yalnızca denetimli)**: **İzin Ver** olarak ayarlanırsa öğretmenler öğrencilerin bilgisi olmadan Classroom uygulamasını kullanarak, öğrencilerin iOS cihazlarının ekranını sessizce izleyebilir. Classroom uygulaması kullanılarak sınıfa kaydedilmiş olan öğrenci cihazları, söz konusu dersin öğretmenine otomatik olarak izin verir. **Yapılandırılmadı** (varsayılan) ayarı bu özelliği engeller.
- **Güvenilmeyen TLS sertifikaları**: Cihazda güvenilmeyen Aktarım Katmanı Güvenliği (TLS) sertifikalarını önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı TLS sertifikalarına izin verir.
- **Kurumsal uygulama güveni**: Cihazda Ayarlar > Genel > Profiller ve Cihaz Yönetimi altındaki **Güvenilen Kurumsal Geliştirici** düğmesini kaldırmak için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının uygulama mağazasından indirilmemiş uygulamalara güvenmeyi seçmesine olanak tanır.
- **Hesap değişikliği (yalnızca denetimli)**: **Engelle** olarak ayarlandığında kullanıcı iOS ayarlar uygulamasından cihaza özgü ayaları güncelleştiremez. Örneğin kullanıcı yeni cihaz hesapları oluşturamaz ya da kullanıcı adını veya parolasını değiştiremez. **Yapılandırılmadı** (varsayılan) ayarı kullanıcıların bu ayarları değiştirmesine izin verir.

  Bu özellik Posta, Kişiler, Takvim ve Twitter gibi iOS ayarları uygulamasından erişilebilen ayarlar için de geçerlidir. Bu özellik hesap ayarları iOS ayarları uygulamasından yapılandırılamayan uygulamalar (Microsoft Outlook uygulaması gibi) için geçerli değildir.
- **Ekran saati (yalnızca denetimli)**: Kullanıcıların Ekran Saati'nde (cihaz ayarları) kendi kısıtlamalarını ayarlamalarını önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** kullanıcının cihazda cihaz kısıtlamalarını (ebeveyn denetimleri veya içerik ve gizlilik kısıtlamaları gibi) yapılandırmasına izin verir.

  Bu ayar **Cihaz ayarlarında kısıtlamaları etkinleştirme** ayarının yeniden adlandırılmış halidir. Bu değişikliğin etkisi:  
  
  - iOS 11.4.1 ve öncesi: **Engelle** ayarı son kullanıcıların cihaz ayarlarında kendi kısıtlamalarını ayarlamalarını önler. Bu aynı ayardır ve son kullanıcılar açısından hiçbir değişikliğe neden olmaz.
  - iOS 12.0 ve üzeri: **Engelle** ayarı son kullanıcıların içerik ve gizlilik kısıtlamaları da dahil olmak üzere cihaz ayarlarında kendi **Ekran Saati** (Ayarlar > Genel > Ekran Saati) ayarlarını yapmalarını önler. iOS 12.0'dan yükseltilen cihazlar artık cihaz ayarlarında kısıtlamalar sekmesini (Ayarlar > Genel > Cihaz Yönetimi > Yönetim Profili > Kısıtlamalar) görmez. Bu ayarlar **Ekran Saati** altındadır.
  
- **Cihazdaki tüm içerikleri ve ayarları silme seçeneğinin kullanımı (yalnızca denetimli)**: Kullanıcıların cihazda tüm içerikleri ve ayarları silme seçeneğini kullanamaması için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı kullanıcılara bu ayarlar için erişim verir.
- **Cihaz adı değişikliği (yalnızca denetimli)**: Cihaz adının değiştirilememesi için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının cihaz adını değiştirmesine izin verir.
- **Bildirim ayarlarının değiştirilmesi (yalnızca denetimli)**: Bildirim ayarlarının değiştirilememesi için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının cihaz bildirim ayarlarını değiştirmesine izin verir.
- **Duvar kağıdının değiştirilmesi (yalnızca denetimli):** **Engelle** ayarı duvar kağıdının değiştirilmesini önler. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının cihazda duvar kağıdını değiştirmesine izin verir.
- **Kurumsal uygulama güven ayarlarının değiştirilmesi (yalnızca denetimli)**: **Engelle** ayarı kullanıcının denetimli cihazlarda kurumsal uygulama güven ayarlarını değiştirmesini önler. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının uygulama mağazasından indirilmemiş uygulamalara güvenmesine izin verir.
- **Yapılandırma profili değişiklikleri (yalnızca denetimli)**: **Engelle** ayarı cihazda yapılandırma profili değişikliklerini önler. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının yapılandırma profillerini yüklemesine izin verir.
- **Etkinleştirme Kilidi (yalnızca denetimli)**: Denetimli iOS cihazlarında Etkinleştirme Kilidi’ni etkinleştirmek için **İzin Ver**'i seçin. Etkinleştirme Kilidi, kaybolan veya çalınan bir cihazın yeniden etkinleştirilmesini zorlaştırır.
- **Uygulama kaldırmayı engelle (yalnızca denetimli)**: Kullanıcıların uygulamaları kaldırmasını önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı kullanıcıların cihazdan uygulama kaldırmasına izin verir.
- **USB Kısıtlı modunu engeller (yalnızca denetimli)**: Denetimli cihazlarda USB Kısıtlı modunu devre dışı bırakmak için **Engelle**'yi seçin. USB Kısıtlı modu USB aksesuarlarının bir saatten uzun süre kilitli kalmış olan cihazlarla veri değişimi yapmasını engeller. **Yapılandırılmadı** (varsayılan) ayarı USB Kısıtlı moduna izin verir.
- **Otomatik tarih ve saati zorla (yalnızca denetimli)**: **Gerekli** ayarı denetimli cihazların Tarih ve Saati otomatik olarak ayarlamasını zorunlu tutar. Cihazın hücresel bağlantıları olduğunda veya konum hizmetleriyle arasında Wi-Fi etkinleştirildiğinde saat dilimi güncelleştirilir.
- **Öğrencilerin Classroom dersinden ayrılmak için izin istemesini gerekli yap (yalnızca denetimli)**: **Gerekli** ayarı Classroom uygulamasını kullanarak yönetilmeyen bir derse kaydolan öğrencilerin dersten ayrılmadan önce öğretmenden izin istemesini zorunlu tutar. **Yapılandırılmadı** (varsayılan) ayarı öğrencinin izin istemesini zorunlu tutmaz.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11.3 ve üzeri

- **Classroom'un sormadan bir uygulamayı ve cihazı kilitlemesine izin ver (yalnızca denetimli)**: **Etkinleştir** ayarı öğretmenin Classroom uygulamasını kullanarak öğrenciye sormadan uygulamaları kilitlemesine veya cihazı kilitlemesine izin verir. Uygulamaların kilitlenmesi cihazın yalnızca öğretmenin belirttiği uygulamalara erişebileceği anlamına gelir. **Yapılandırılmadı** (varsayılan) ayarı öğretmenlerin öğrenciye sormadan Classroom uygulamasını kullanarak uygulamaları veya cihazları kilitlemesini önler. 

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11.0 ve üzeri

- **Classroom sınıflarına istek göndermeden otomatik olarak katıl (yalnızca denetimli)**: **Etkinleştir** ayarı öğrencilerin öğretmene sormadan Classroom uygulamasındaki derse otomatik olarak katılmasına izin verir. **Yapılandırılmadı** (varsayılan) ayarı öğrencilerin Classroom uygulamasındaki derse katılma isteğini öğretmene sorar.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11.0 ve üzeri

- **Havadan PKI güncelleştirmelerine izin ver**: **İzin Ver** ayarı kullanıcılarınızın cihazlarını bir bilgisayara bağlamadan yazılım güncelleştirmeleri almasına olanak tanır.
- **Reklam izlemeyi sıfırla**: Cihaz reklam tanımlayıcısını devre dışı bırakmak için **Sınırla**'yı seçin. **Yapılandırılmadı** (varsayılan) bu tanımlayıcının etkin kalmasını sağlar.
- **VPN oluşturmayı engelle (yalnızca denetimli)**: **Engelle** ayarı kullanıcıların VPN yapılandırma ayarları oluşturmasını önler. **Yapılandırılmadı** (varsayılan) ayarı kullanıcıların cihazda VPN'ler oluşturmasına olanak tanır.
- **eSIM ayarlarının değiştirilmesi (yalnızca denetimli)**: **Engelle** ayarı kullanıcıların cihazda eSIM için hücresel planı kaldırmasını veya eklemesini önler. **Yapılandırılmadı** (varsayılan) ayarı kullanıcıların bu ayarları değiştirmesine izin verir.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 12.1 ve üzeri

- **Yazılım güncelleştirmelerini geciktir (yalnızca denetimli)**: **Yapılandırılmadı** (varsayılan) olarak ayarlandığında Apple tarafından yayımlanan yazılım güncelleştirmeleri anında cihazda gösterilir. Örneğin Apple tarafından bir iOS güncelleştirmesinin yayımlanması durumunda ilgili güncelleştirme normal bir şekilde yayın tarihinde cihazda görünür.

  **Etkinleştir** ayarını kullanarak güncelleştirmelerin cihazlarda gösterilmesini 0-90 gün boyunca geciktirebilirsiniz. Bu ayar, güncelleştirmelerin yüklenme tarihini veya durumunu denetlemez. 

  - **Yazılım güncelleştirmelerinin görünürlüğünü geciktir**: 0-90 gün arasında bir değer girin. Gecikme süresi sona erdiğinde kullanıcılara gecikmenin tetiklendiği tarihte kullanılabilir durumda olan en eski işletim sistemi sürümüne güncelleştirme bildirimi gönderilir.

    Örneğin **1 Ocak** tarihinde iOS.12a'nın yayımlanması ve **Görünürlük geciktirme** ayarının **5 gün** olması durumunda iOS 12.a, son kullanıcı cihazlarında kullanılabilir güncelleştirme olarak gösterilmez. Yayımlandıktan sonraki **altıncı günde** bu güncelleştirme kullanıma sunulur ve kullanıcılar tarafından yüklenebilir.

    Bu ayarın geçerli olduğu sürümler:  
    - iOS 11.3 ve üzeri

## <a name="password"></a>Parola

- **Parola**: **Gerekli** ayarı son kullanıcının cihaza erişmek için parola girmesini zorunlu tutar. **Yapılandırılmadı** ayarı kullanıcıların parola girmeden cihaza erişmelerine izin verir.
  - **Basit parolalar**: Daha karmaşık parolaları zorunlu tutmak için **Engelle**'yi seçin. **Yapılandırılmadı** ayarı `0000` ve `1234` gibi basit parolalara izin verir.
  - **Gerekli parola türü**: Kuruluşunuzun gerektirdiği parola türünü seçin. Seçenekleriniz şunlardır:
    - **Cihaz varsayılanı**
    - **Sayısal**
    - **Alfasayısal**
  - **Paroladaki alfasayısal olmayan karakter sayısı**: Parolada bulunması gereken `#` veya `@` gibi simge karakterlerinin sayısını belirtin.
  - **Minimum parola uzunluğu**: Kullanıcının girmesi gereken uzunluk alt sınırını girin (4 ile 14 karakter arasında).
  - **Cihaz silinmeden önceki oturum açma hatası sayısı**: Cihaz silinmeden önce izin verilecek başarısız oturum açma sayısını girin (1-11 arasında).
  - **Ekran kilitlendikten sonra parola istenene kadar geçmesi gereken, işlem yapılmayan dakika sayısı**<sup>1</sup>: Kullanıcının parolasını yeniden girmesi gerekmeden önce cihazın ne kadar süreyle boşta kalacağını girin. Girdiğiniz süre cihazda şu anda ayarlanmış olan süreden uzunsa, cihaz girdiğiniz süreyi yoksayar. iOS 8.0 ve daha yeni cihazlarda desteklenir.
  - **Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı**<sup>1</sup>: Ekran otomatik olarak kilitlenmeden önce izin verilecek işlem yapılmayan en fazla dakika sayısını girin. Girdiğiniz süre cihazda şu anda ayarlanmış olan süreden uzunsa, cihaz girdiğiniz süreyi yoksayar.
  - **Parola zaman aşımı (gün sayısı)**: Cihaz parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını girin.
  - **Önceki parolaların yeniden kullanılmasını engelleme**: Eski bir parolanın yeniden kullanılabilmesi için önce kullanılması gereken yeni parola sayısını girin.
  - **Parmak izi ile kilit açma**: Cihaz kilidinin parmak izi kullanılarak açılmasını önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** ayarı, kullanıcının cihaz kilidini parmak izi kullanarak açmasını sağlar.
- **Geçiş kodunun değiştirilmesi (yalnızca denetimli)**: Geçiş kodu değiştirme, ekleme veya kaldırma işlemlerini durdurmak için **Engelle**'yi seçin. Bu özellik engellendikten sonra denetimli cihazlarda geçiş kodu kısıtlamalarında yapılan değişiklikler yoksayılır. **Yapılandırılmadı** (varsayılan) ayarı geçiş kodu ekleme, değiştirme veya kaldırma işlemlerine izin verir.

  - **Parmak izi değişikliği (yalnızca denetimli)**: **Engelle** ayarı kullanıcının TouchID parmak izlerini değiştirme, eklemesi veya kaldırması işlemlerini durdurur. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının cihazda TouchID parmak izlerini güncelleştirmesine izin verir.

- **Parola Otomatik Doldurmayı engelle (yalnızca denetimli)**: iOS Parola Otomatik Doldurma özelliğini engellemek için **Engelle**'yi seçin. **Engelle** ayarının seçilmesi şunlara da neden olur:

  - Safari'de veya diğer uygulamalarda kullanıcılara parolaları kaydetmek isteyip istemedikleri sorulmaz.
  - Otomatik Güçlü Parolalar devre dışı bırakılır ve kullanıcılara güçlü parola önerisi sunulmaz.

  **Yapılandırılmadı** (varsayılan) ayarı bu özelliklere izin verir.

- **Parola yakınlık isteklerini engelle (yalnızca denetimli)**: **Engelle**'yi seçtiğinizde kullanıcının cihazı yakınlardaki cihazlardan parola isteyemez. **Yapılandırılmadı** (varsayılan) ayarı bu parola isteklerine izin verir.
- **Parola paylaşımını engelle (yalnızca denetimli)**: **Engelle** ayarı AirDrop ile cihazlar arasında parola paylaşımı yapılmasını engeller. **Yapılandırılmadı** (varsayılan) ayarı, parolaların paylaşılmasına izin verir.
- **Parola veya kredi kartı bilgilerini Otomatik Doldurma için Touch ID veya Face ID kimlik doğrulamasını gerektir (yalnızca denetimli)**: **Gerekli** olarak ayarlandığında Safari'de ve diğer uygulamalarda parolaların veya kredi kartı bilgilerinin otomatik olarak doldurulması için önce kullanıcıların TouchID veya FaceID ile kimlik doğrulaması yapması gerekir. **Yapılandırılmadı** (varsayılan) ayarı kullanıcıların cihaz ayarlarında bu özelliği denetlemesine izin verir.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11.0 ve üzeri

<sup>1</sup>**Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı** ve **Ekran kilitlendikten sonra parola istenene kadar geçmesi gereken, işlem yapılmayan dakika sayısı**, ayarlarını yapılandırdığınızda, bunlar sırayla uygulanır. Örneğin, her iki ayarın da değerini **5** dakikaya ayarlarsanız, ekran beş dakika sonra otomatik olarak kapanır ve cihazın kilitlenmesi için beş dakika daha geçmesi gerekir. Ancak, kullanıcı ekranı el ile kapatırsa ikinci ayar hemen uygulanır. Aynı örnekte, kullanıcı ekranı kapattıktan sonraki beş dakikanın sonunda cihaz kilitlenir.

## <a name="locked-screen-experience"></a>Kilit Ekranı Deneyimi

- **Cihaz kilitliyken Denetim Merkezi erişimi**: Cihaz kilitliyken Denetim Merkezi uygulamasına erişimi önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** ayarı cihaz kilitliyken kullanıcıların Denetim Merkezi uygulamasına erişmesine izin verir.
- **Cihaz kilitliyken bildirimler**: **Engelle** ayarı cihaz kilitliyken bildirimlere erişilmesini önler. **Yapılandırılmadı** ayarı kullanıcının cihazın kilidini açmadan bildirimlere erişmesine izin verir.
- **Cihaz kilitliyken Cüzdan bildirimleri**: **Engelle** ayarı cihaz kilitliyken Cüzdan uygulamasına erişilmesini önler. **Yapılandırılmadı** ayarı cihaz kilitliyken kullanıcının Cüzdan uygulamasına erişmesine izin verir.
- **Cihaz kilitliyken Bugün görünümü**: **Engelle** ayarı cihaz kilitliyken Bugün görünümüne erişilmesini önler. **Yapılandırılmadı** ayarı cihaz kilitliyken kullanıcının Bugün görünümünü görmesine izin verir.

## <a name="app-store-doc-viewing-gaming"></a>Uygulama Mağazası, Belge Görüntüleme, Oyun

- **Uygulama mağazası**: **Engelle** ayarı denetimli cihazlarda uygulama mağazasına erişimi önler. **Yapılandırılmadı** ayarı erişime izin verir.
  - **App Store'dan uygulama yükleme (yalnızca denetimli)**: Cihaz giriş ekranında uygulama mağazasını engellemek için **Engelle**'yi seçin. Son kullanıcılar, uygulamaları yüklemek için iTunes’u veya Apple Configurator aracını kullanmaya devam edebilir. **Yapılandırılmadı** ayarı giriş ekranında uygulama mağazasına izin verir.
  - **Otomatik uygulama indirme (yalnızca denetimli)**: Başka cihazlarda satın alınmış uygulamaların otomatik olarak indirilmesini önlemek için **Engelle**'yi seçin. Mevcut uygulamalarında yapılan güncelleştirmeler bundan etkilenmez. **Yapılandırılmadı** ayarı başka iOS cihazlarında satın alınmış uygulamaların cihaza indirilmesine izin verir.
- **Uygulama mağazasına erişim için parola**: Kullanıcının uygulama mağazasını ziyaret etmeden önce parola girmesini **gerektirin**. **Yapılandırılmadı** ayarı parola girmeden uygulama mağazasına erişmelerine izin verir.
- **Uygulama içi satın alımlar**: Mağazadan uygulama içi satın alımları önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** ayarı çalışan uygulamanın içinden mağaza satın alımlarına izin verir.
- **Müstehcen iTunes müziği, pod yayını veya haber içeriği (yalnızca denetimli)**: Müstehcen iTunes müziği, pod yayını veya haber içeriğini önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** ayarı cihazın mağazadaki yetişkinlere yönelik olarak derecelendirilmiş içeriğe erişmesine izin verir.
- **iBook mağazasından 'Erotik' olarak işaretlenmiş içerik indirme**: Kullanıcıların iBook mağazasından erotik olarak etiketlenmiş medyayı indirmesini önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** ayarı kullanıcının “Erotik” kategorisindeki kitapları indirmesine izin verir.
- **Yönetilmeyen uygulamalarda kurumsal belgeleri görüntüleme**: **Engelle** ayarı yönetilmeyen uygulamalarda kurumsal belgelerin görüntülenmesini önler. **Yapılandırılmadı** ayarı kurumsal belgelerini herhangi bir uygulamada görüntülenmesine izin verir. Örneğin kullanıcıların OneDrive uygulamasından Dropbox’a dosya kaydetmesini engellemek istiyorsunuz. Bu ayarı **Engelle** olarak yapılandırın. Cihaz ilkeyi aldıktan sonra (örneğin, yeniden başlatıldıktan sonra) artık kaydetmeye izin vermez.
  - **Yönetilen uygulamaların yönetilmeyen kişi hesaplarına kişi yazmasına izin ver**: **İzin Ver** olarak ayarlandığında kullanıcılar cihazdaki yerleşik Kişiler uygulamasına iş ve şirket kişileri de dahil olmak üzere tüm kişilerin Outlook iletişim bilgilerini ekleyebilir ve bu bilgileri güncelleştirebilir. **Yapılandırılmadı** olarak ayarlandığında kullanıcılar cihazdaki yerleşik Kişiler uygulamasına Outlook kişilerini ekleyemez.
  
    Bu ayarı kullanmak için **Yönetilmeyen uygulamalarda kurumsal belgeleri görüntüleme** ayarını **Engelle** olarak belirtin.
  
- **Kurumsal olmayan belgeleri kurumsal uygulamalarda görüntüleme**: **Engelle** ayarı kurumsal olmayan belgelerin kurumsal uygulamalarda görüntülenmesini önler. **Yapılandırılmadı** ayarı tüm belgelerin şirketin yönetilen uygulamalarında görüntülenmesine izin verir.
  - **Yönetilmeyen uygulamaların yönetilen kişi hesaplarından kişi okumasına izin ver**: **İzin Ver** olarak ayarlandığında kullanıcılar herhangi birinin iContacts uygulaması kişi bilgilerini Outlook'a ekleyebilir. **Yapılandırılmadı** ayarı cihazdaki yerleşik Kişiler uygulamasından okumayı (yinelenenleri kaldırma da dahil) önler.
  
    Bu ayarı kullanmak için **Kurumsal olmayan belgeleri kurumsal uygulamalarda görüntüleme** ayarını **Engelle** olarak belirtin.
  
- **AirDrop'u yönetilmeyen uygulama olarak değerlendir**: **Gerekli** ayarı AirDrop'un yönetilmeyen bırakma hedefi olarak kabul edilmesini zorunlu tutar. Yönetilen uygulamaların Airdrop'u kullanarak veri göndermesini durdurur. 
- **Game Center arkadaşları ekleme (yalnızca denetimli)**: **Engelle** ayarı kullanıcıların Game Center arkadaşları eklemesini önler. **Yapılandırılmadı** ayarı kullanıcının Game Center'da arkadaş eklemesine izin verir.
- **Game Center (yalnızca denetimli)**: Game Center uygulamasının kullanılmasını **engelleyin**. **Yapılandırılmadı** ayarı cihazda Game Center uygulamasının kullanılmasına izin verir.
- **Çok oyunculu oyunlar (yalnızca denetimli)**: Çok oyunculu oyunları önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** ayarı kullanıcının cihazda çok oyunculu oyunlar oynamasına izin verir.
- **Derecelendirme bölgesi**: İzin verilen indirmeler için derecelendirme bölgesini seçin. Ardından **Filmler** ve **TV Programları** için izin verilen derecelendirmeleri seçin.
- **Uygulamalar**: Kullanıcıların indirebileceği uygulamaların yaş derecelendirmesini seçin. **Tüm Uygulamalara İzin Ver**’i de seçebilirsiniz.

## <a name="built-in-apps"></a>Yerleşik Uygulamalar

- **Kamera**: Cihazdaki kameraya erişim sağlanmasını engellemek için **Engelle**'yi seçin. **Yapılandırılmadı** ayarı cihazın kamerasına erişim sağlar.
  - **FaceTime**: FaceTime uygulamasına erişimi önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** ayarı cihazda FaceTime uygulamasına erişim izni verir.
- **Siri**: **Engelle** ayarı Siri'ye erişimi önler. **Yapılandırılmadı** ayarı cihazda Siri sesli yardımının kullanılmasına izin verir.
  - **Cihaz kilitliyken Siri**: Cihaz kilitliyken Siri'ye erişimi önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** ayarı cihaz kilitliyken cihazda Siri sesli yardımının kullanılmasına izin verir.
  - **Siri küfür filtresi (yalnızca denetimli)**: **Gerekli** ayarı Siri’nin küfürlü dil dikte etmesini veya konuşmasını engeller.
  - **Siri'nin İnternet'ten kullanıcı tarafından oluşturulan içerikleri sorgulaması (yalnızca denetimli)**: **Engelle** ayarı Siri'nin soruları yanıtlamak için web sitelerine erişmesini önler. **Yapılandırılmadı** ayarı Siri'nin İnternet'te kullanıcı tarafından oluşturulan içeriğe erişmesine izin verir.
- **Apple News (yalnızca denetimli)**: Cihazda Apple News uygulamasına erişimi engellemek için **Engelle**'yi seçin. **Yapılandırılmadı** ayarı Apple News uygulamasının kullanılmasına izin verir.
- **iBooks mağazası (yalnızca denetimli)**: **Engelle** ayarı iBooks mağazasına erişimi engeller. **Yapılandırılmadı** ayarı kullanıcıların iBooks mağazasındaki kitaplara göz atmasına ve bunları satın almasına izin verir.
- **Cihazdaki Mesajlar uygulaması (yalnızca denetimli)**: Kullanıcıların cihazdaki Mesajlar uygulamasını kullanamaması için **Engelle**'yi seçin. **Yapılandırılmadı** ayarı kısa mesaj göndermek ve okumak için Mesajlar uygulamasının kullanılmasına izin verir.
- **Podcasts (yalnızca denetimli)**: **Engelle** ayarı kullanıcıların Podcasts uygulamasını kullanmasını önler. **Yapılandırılmadı** ayarı Podcasts uygulamasının kullanılmasına izin verir.
- **Müzik hizmeti (yalnızca denetimli)**: **Engelle** ayarı Müzik uygulamasını klasik moda döndürür ve Müzik hizmetini devre dışı bırakır. **Yapılandırılmadı** ayarı Müzik uygulamasının kullanılmasına izin verir.
- **iTunes Radio hizmeti (yalnızca denetimli)**: **Engelle** ayarı kullanıcıların iTunes Radio uygulamasını kullanmasını önler. **Yapılandırılmadı** ayarı iTunes Radio uygulamasının kullanılmasına izin verir.
- **Arkadaşlarımı Bul uygulamasının ayarlarında yapılan değişiklikler (yalnızca denetimli)**: **Engelle** ayarı Arkadaşlarımı Bul uygulamasının ayarlarında yapılan değişiklikleri önler. **Yapılandırılmadı** ayarı kullanıcının Arkadaşlarımı Bul uygulamasının ayarlarını değiştirmesine izin verir.
- **Spotlight aramasının İnternet'ten sonuç döndürmesi (yalnızca denetimli)**: **Engelle** ayarı Spotlight'ın İnternet araması sonuçlarını döndürmesini durdurur. **Yapılandırılmadı** ayarı Spotlight'ın internete bağlanarak arama sonuçlarını getirmesine izin verir.
- **Cihazdan sistem uygulamalarının kaldırılmasını engelle (yalnızca denetimli)**: **Engelle** ayarı seçildiğinde cihazdan sistem uygulamalarını kaldırabilme özelliği devre dışı bırakılır. **Yapılandırılmadı** ayarı sistem uygulamalarının kaldırılmasına izin verir.

#### <a name="safari"></a>Safari

- **Safari (yalnızca denetimli)**: Cihazda Safari tarayıcısının kullanılmasını **engelleyin**. **Yapılandırılmadı** ayarı kullanıcıların Safari tarayıcısını kullanmasına izin verir.
- **Otomatik doldurma**: **Engelle** ayarı cihazdaki Safari uygulamasında otomatik doldurma özelliğini devre dışı bırakır. **Yapılandırılmadı** ayarı kullanıcıların web tarayıcısındaki otomatik tamamlama ayarlarını değiştirmesine olanak tanır.
- **Tanımlama bilgileri**: Cihazda tanımlama bilgilerinin nasıl işleneceğini seçin. Seçenekleriniz şunlardır:
  - İzin Ver
  - Tüm tanımlama bilgilerini engelle
  - Ziyaret edilen web sitelerinin tanımlama bilgilerine izin ver
  - Geçerli web sitesinin tanımlama bilgilerine izin ver
- **JavaScript**: **Engelle** ayarı tarayıcıdaki Java betiklerinin cihazda çalıştırılmasını önler. **Yapılandırılmadı** ayarı Java betiklerine izin verir.
- **Sahtekarlık uyarıları**: Cihazdaki web tarayıcısında sahtekarlık uyarılarının gösterilmesini **gerektirin**. **Yapılandırılmadı** ayarı bu özelliği devre dışı bırakır.
- **Açılır pencereler**: Web tarayıcısında açılır pencere engelleyicisini devre dışı bırakmak için **Engelle**'yi seçin. **Yapılandırılmadı** ayarı açılır pencere engelleyicisine izin verir.

## <a name="restricted-apps"></a>Kısıtlı uygulamalar

Kısıtlı uygulamalar listesinde, aşağıdaki listelerden birini yapılandırabilirsiniz:

- **Yasak uygulamalar**: Intune tarafından yönetilmeyen ve cihazda bulunmasını istemediğiniz uygulamaların listesi. Kullanıcı bu listedeki bir uygulamayı yüklerse, Intune bunu size bildirir.
- **Onaylı uygulamalar**: Kullanıcıların yüklemesine izin verilen uygulamaların listesi. Uyumluluğun korunması için kullanıcılar diğer uygulamaları yüklememelidir. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir. Kullanıcı bu listedeki bir uygulamayı yüklerse, Intune bunu size bildirir.

Bu listelere uygulama eklemek için şunları yapabilirsiniz:

- İstediğiniz uygulamanın iTunes App mağazası URL'sini **ekleyin**. Örneğin Microsoft Çalışma Klasörleri uygulamasını eklemek için `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` girin.

  Uygulamanın URL'sini bulmak için, iTunes App Store'u açın ve uygulamayı arayın. Örneğin `Microsoft Remote Desktop` veya `Microsoft Word` için arama yapın. Uygulamayı seçin ve URL'sini kopyalayın.

  iTunes kullanarak da uygulamayı bulabilir ve ardından **Bağlantıyı Kopyala** görevini kullanıp uygulama URL’sini alabilirsiniz.

- URL'si de dahil olmak üzere uygulamayla ilgili ayrıntıların bulunduğu bir CSV dosyasını içeri aktarın. `<app url>, <app name>, <app publisher>` biçimini kullanın. Bunun yerine, aynı biçimde kısıtlanmış uygulamalar listesini içeren mevcut listeyi dışarı aktarabilirsiniz.

> [!IMPORTANT]
> Kısıtlı uygulama ayarlarını kullanan cihaz profilleri kullanıcı gruplarına atanmalıdır.

## <a name="show-or-hide-apps-supervised-only"></a>Uygulamaları gösterme veya gizleme (yalnızca denetimli)

iOS 9.3 veya daha yeni bir sürümü çalıştıran denetimli cihazlarda, Uygulamaları gösterme veya gizleme listesinde aşağıdaki listelerden birini yapılandırabilirsiniz.

- **Gizli uygulamalar**: Kullanıcılardan gizlenecek uygulamaların listesini girin. Kullanıcılar bu uygulamaları görüntüleyemez veya açamaz.
- **Görünür uygulamalar**: Kullanıcıların görüntüleyebileceği ve başlatabileceği uygulamaların listesini girin. Başka hiçbir uygulama görüntülenemez veya başlatılamaz.

Bu listelere uygulama eklemek için şunları yapabilirsiniz:

- İstediğiniz uygulamanın iTunes App mağazası URL'sini **ekleyin**. Örneğin Microsoft Çalışma Klasörleri uygulamasını eklemek için `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` girin.

  Uygulamanın URL'sini bulmak için, iTunes App Store'u açın ve uygulamayı arayın. Örneğin `Microsoft Remote Desktop` veya `Microsoft Word` için arama yapın. Uygulamayı seçin ve URL'sini kopyalayın.

  iTunes kullanarak da uygulamayı bulabilir ve ardından **Bağlantıyı Kopyala** görevini kullanıp uygulama URL’sini alabilirsiniz.

- URL'si de dahil olmak üzere uygulamayla ilgili ayrıntıların bulunduğu bir CSV dosyasını içeri aktarın. `<app url>, <app name>, <app publisher>` biçimini kullanın. Bunun yerine, aynı biçimde kısıtlanmış uygulamalar listesini içeren mevcut listeyi dışarı aktarabilirsiniz.

## <a name="wireless"></a>Kablosuz

- **Veri dolaşımı**: Cep telefonu şebekesi üzerinden veri dolaşımını önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı cihaz cep telefonu şebekesindeyken veri dolaşımına izin verir.
- **Dolaşım sırasında genel arka planda alma**: **Engelle** ayarı cep telefonu şebekesi üzerinde dolaşım sırasında genel arka planda alma özelliğinin kullanılmasını önler. **Yapılandırılmadı** ayarı cihazın cep telefonu şebekesi üzerinde dolaşımdayken e-posta gibi verileri almasına izin verir.
- **Sesli arama**: Kullanıcıların cihazda sesli arama özelliğini kullanmasını önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı cihazda sesli aramaya izin verir.
- **Ses dolaşımı**: Cep telefonu şebekesi üzerinden ses dolaşımını önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı cihaz cep telefonu şebekesindeyken ses dolaşımına izin verir.
- **Uygulama hücresel veri kullanımı ayarlarının değiştirilmesi (yalnızca denetimli)**: Uygulama hücresel veri kullanımı ayarlarının değiştirilmesini önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının hangi uygulamaların hücresel veri kullanabileceğini denetlemesine izin verir.
- **Hücresel plan ayarlarının değiştirilmesi (yalnızca denetimli)**: **Engelle** ayarı kullanıcıların hücresel plandaki ayarları değiştirmesini önler. **Yapılandırılmadı** (varsayılan) ayarı kullanıcıların değişiklik yapmasına izin verir.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11.0 ve üzeri

- **Kişisel Etkin Nokta**: **Engelle** ayarı her cihaz eşitlemesinde kullanıcıların cihazındaki kişisel etkin noktayı kapatır. Bu ayar, bazı operatörler ile uyumlu olmayabilir. **Yapılandırılmadı** (varsayılan) ayarı kişisel etkin nokta yapılandırmasını kullanıcı tarafından ayarlanmış varsayılan değerinde bırakır.
- **Yalnızca yapılandırma profilleri kullanan Wi-Fi ağlarına katıl (yalnızca denetimli)**: **Gerekli** ayarı cihazın yalnızca Intune yapılandırma profilleri aracılığıyla ayarlanan Wi-Fi ağlarını kullanmasını zorunlu tutar. **Yapılandırılmadı** (varsayılan) ayarı cihazın diğer Wi-Fi ağlarını kullanmasına izin verir.
- **Hücresel kullanım kuralları (yalnızca yönetilen uygulamalar)**: Hücresel ağa bağlıyken yönetilen uygulamaların kullanabileceği veri türlerini tanımlayın. Seçenekleriniz şunlardır:
  - **Hücresel veri kullanımını engelle**: **Tüm yönetilen uygulamalar** için hücresel veri kullanımını engelleyin veya **Belirli uygulamaları seçin**.
  - **Dolaşımdayken hücresel veri kullanımını engelle**: Dolaşım sırasında **Tüm yönetilen uygulamalar** için hücresel veri kullanımını engelleyin veya **Belirli uygulamaları seçin**.

## <a name="connected-devices"></a>Bağlı Cihazlar

- **AirDrop (yalnızca denetimli)**: **Engelle** ayarı cihazdaki AirDrop özelliğinin kullanılmasını engeller. **Yapılandırılmadı** (varsayılan) ayarı yakındaki cihazlarla içerik değişimi için AirDrop özelliğinin kullanılmasına izin verir.
- **Apple Watch eşleştirme (yalnızca denetimli)**: **Engelle** ayarı Apple Watch ile eşleştirmeyi önler. **Yapılandırılmadı** (varsayılan) ayarı cihazın Apple Watch ile eşleştirilmesine izin verir.
- **Eşleştirilen Apple Watch için bilek algılama**: **Gerekli** ayarı eşleştirilmiş Apple Watch'un bilek algılama kullanmasını zorunlu tutar. Gerekli seçilirse, Apple Watch takılmadığında bildirim görüntülemez. 
- **Bluetooth değişikliği (yalnızca denetimli)**: **Engelle** ayarı son kullanıcının cihazda Bluetooth ayarlarını değiştirmesini durdurur. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının bu ayarları değiştirmesine izin verir.
- **iOS cihazının eşleştirilebildiği cihazları kontrol etmek için konak eşleştirmesi (yalnızca denetimli)**: **Yapılandırılmadı** (varsayılan) ayarı yöneticinin bir iOS cihazının hangi cihazlarla eşleşebileceğini denetleyebilmesi için konak eşleştirmeye izin verir. **Engelle** ayarı konak eşleştirmeyi önler.
- **Giden AirPlay istekleri için eşleştirme parolası isteme**: **Gerekli** ayarı kullanıcının diğer Apple cihazlarına içerik akışı sağlamak üzere AirPlay’i kullanması için, eşleştirilen parola gerektirir. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının parola girmeden AirPlay kullanarak içerik akışı yapmasına izin verir.
- **AirPrint'i engelle (yalnızca denetimli)**: Cihazda AirPrint özelliğinin kullanılmasını önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının AirPrint'i kullanmasına izin verir.
  - **AirPrint kimlik bilgilerinin Anahtar Zincirinde depolanmasını engelle (yalnızca denetimli)**: **Engelle** ayarı cihazda kullanıcı adı ve parola için Anahtar Zinciri depolama alanının kullanılmasını önler. **Yapılandırılmadı** (varsayılan) ayarı AirPrint kullanıcı adı ve parolasının Anahtar Zinciri uygulamasında depolanmasına izin verir.
  - **AirPrint için güvenilir bir TLS sertifikası iste (yalnızca denetimli)**: **Gerekli** ayarı cihazın TLS yazdırma iletişimi için güvenilir sertifikalar kullanmasını zorunlu tutar.
  - **AirPrint yazıcılarının iBeacon bulmasını engelle (yalnızca denetimli)**: **Engelle** ayarı kötü amaçlı AirPrint Bluetooth işaretlerinin ağ trafiği için kimlik avı yapmasını engeller. **Yapılandırılmadı** (varsayılan) ayarı cihazda AirPrint yazıcılarının tanıtılmasına izin verir.
- **Yakındaki yeni cihazların ayarlanmasını engelle (yalnızca denetimli)**: **Engelle** ayarı yakındaki yeni cihazların ayarlanması istemini devre dışı bırakır. **Yapılandırılmadı** (varsayılan) ayarı yakındaki diğer Apple cihazlarıyla bağlantı kurulup kurulmayacağının kullanıcıya sorulmasına izin verir.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11.0 ve üzeri

## <a name="keyboard-and-dictionary"></a>Klavye ve Sözlük

- **Sözcük tanımı arama (yalnızca denetimli)**: **Engelle** ayarı kullanıcının belirli bir sözcüğü vurgulayıp cihazda tanımını aramasını engeller. **Yapılandırılmadı** ayarı tanım arama özelliğine erişim sağlar.
- **Tahmine dayalı klavyeler (yalnızca denetimli)**: **Yapılandırılmadı** ayarı kullanıcının isteyebileceği sözcükleri öneren öngörülü klavyelerin kullanılmasına izin verir. **Engelle** ayarı bu özelliği önler.
- **Otomatik düzeltme (yalnızca denetimli)**: **Yapılandırılmadı** ayarı cihazın yanlış yazılan sözcükleri otomatik olarak düzeltmesine izin verir. **Engelle** ayarı otomatik düzeltme kullanılmasını önler.
- **Klavye yazım denetimi (yalnızca denetimli)**: **Yapılandırılmadı** ayarı cihazda yazım denetleyicisinin kullanılmasına izin verir. **Engelle** ayarı yazım denetleyicisine izin verir.
- **Klavye kısayolları (yalnızca denetimli)**: **Yapılandırılmadı** ayarı cihazda klavye kısayollarının kullanılmasına izin verir. **Engelle** ayarı kullanıcının klavye kısayollarını kullanmasını durdurur.
- **Dikte (yalnızca denetimli)**: **Engelle** ayarı kullanıcının metin girmek için sesli giriş kullanmasını durdurur. **Yapılandırılmadı** ayarı kullanıcının dikteyle girişi kullanmasına izin verir.

## <a name="cloud-and-storage"></a>Bulut ve Depolama

- **iCloud'a yedekle**: **Yapılandırılmadı** ayarı kullanıcının cihazı iCloud’a yedeklemesine izin verir. **Engelle** ayarı kullanıcının cihazı iCloud'a yedeklemesini durdurur.
- **iCloud Belge eşitlemesini engelle (yalnızca denetimli)**: **Yapılandırılmadı** ayarı iCloud depolama alanınızda belge ve anahtar-değer eşitlemesine izin verir. **Engelle** ayarı iCloud'ın belgeleri ve verileri eşitlemesini engeller.
- **iCloud'a fotoğraf akışı eşitlemesi**: **Yapılandırılmadı** ayarı kullanıcıların iCloud’a eşitlemek ve tüm kullanıcı cihazlarında fotoğrafların kullanılabilir olmasını sağlamak için cihazlarında **Fotoğraf Akışım**'ı etkinleştirmelerine olanak tanır. **Engelle** ayarı iCloud'a fotoğraf akışının eşitlenmesini önler.
- **Şifreli yedekleme**: Tüm cihaz yedeklemelerinin şifrelenmesini **gerektirir**.
- **iCloud Fotoğraf Arşivi**: Fotoğrafları ve videoları bulutta depolamak üzere iCloud fotoğraf arşivinin kullanılmasını devre dışı bırakmak için **Engelle** olarak ayarlayın. iCloud Fotoğraf Arşivi'nden cihaza tamamen indirilmeyen tüm fotoğraflar cihazdan kaldırılır. **Yapılandırılmadı** ayarı iCloud fotoğraf arşivinin kullanılmasına izin verir.
- **Yönetilen uygulamaları bulutla eşitleme**: **Yapılandırılmadı** ayarı Intune tarafından yönetilen uygulamalarınızın kullanıcının iCloud hesabıyla veri eşitlemesine izin verir. **Engelle** ayarı iCloud'a bu veri eşitlemesini engeller.
- **Paylaşılan fotoğraf akışı**: Cihazda **iCloud Fotoğraf Paylaşımı**’nı devre dışı bırakmak için **Engelle**'yi seçin. **Yapılandırılmadı** ayarı paylaşılan fotoğraf akışına izin verir.
- **Etkinlik devamlılığı**: **Yapılandırılmadı** ayarı kullanıcının bir iOS cihazında başladığı çalışmayı başka bir iOS veya macOS cihazında sürdürmesine izin verir (İletim). **Engelle** ayarı bu iletimi önler.
- **iCloud Anahtar Zinciri eşitlemesini engelle**: **Engelle**'yi seçtiğinizde Anahtar Zincirinde depolanan kimlik bilgilerinin iCloud ile eşitlenmesi devre dışı bırakılır. **Yapılandırılmadı** ayarı kullanıcıların bu kimlik bilgilerini eşitlemesine izin verir.
- **Kurumsal Defter Yedeklemesini Engelle**: Kullanıcıların kurumsal defterleri yedeklemesini önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** ayarı kullanıcıların bu defterleri yedeklemesine izin verir.
- **Kurumsal defter meta veri eşitlemesini (notlar ve vurgular) engelle**: **Engelle** ayarı kurumsal defterlerdeki notların ve vurguların eşitlenmesini önler. **Yapılandırılmadı** ayarı eşitlemeye izin verir.

## <a name="autonomous-single-app-mode-supervised-only"></a>Otonom tek uygulama modu (yalnızca denetimli)

Bu ayarları kullanarak iOS cihazlarını, belirli uygulamaları otonom tek uygulama modunda çalışacak şekilde yapılandırabilirsiniz. Bu mod yapılandırılıp uygulama çalıştırıldığında cihaz kilitlenir. Yalnızca söz konusu uygulamayı çalıştırabilir. Örneğin, kullanıcıların cihazda bir test yapmasına olanak tanıyan bir uygulama ekleyin. Uygulama eylemleri tamamlandığında veya bu ilkeyi kaldırdığınızda cihaz normal durumuna döner.

Uygulamaları eklemek için şunları yapabilirsiniz:

- **Uygulama adı** ile **Uygulama Paketi Grubu Kimliği**'ni girin ve **Ekle**'yi seçin. [Yerleşik iOS uygulamaları için Paket Grubu Kimlikleri](#bundle-ids-for-built-in-ios-apps) (bu makalede), bazı uygulamaları ve onların kimliklerini içerir.
- Uygulama adlarının ve paket kimliklerinin listesini içeren CSV dosyasını **içeri aktarın**. Alternatif olarak uygulamaları içeren mevcut listeyi **dışarı aktarabilirsiniz**.

## <a name="kiosk-supervised-only"></a>Bilgi noktası (yalnızca denetimli)

- **Bilgi noktası modunda çalıştırılacak uygulama**: Bilgi noktası modunda çalıştırmak istediğiniz uygulama türünü seçin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı**: Bilgi noktası ayarları uygulanmaz. Cihaz bilgi noktası modunda çalışmıyor.
  - **Mağaza Uygulaması**: iTunes App mağazasındaki uygulamanın URL'sini girin.
  - **Yönetilen Uygulama**: Intune'a eklediğiniz bir uygulamayı seçin.
  - **Yerleşik Uygulama**: Yerleşik uygulamanın [paket kimliğini](#bundle-ids-for-built-in-ios-apps) girin (bu makalede).

- **Yardımlı dokunma**: **Gerekli**'yi seçerek cihazda Yardımlı Dokunma erişilebilirlik ayarını zorunlu tutun. Bu özellik kullanıcılara zorlanabilecekleri ekran hareketlerinde yardımcı olur. **Yapılandırılmadı** ayarı bilgi noktası modunda bu özelliği çalıştırmaz veya etkinleştirmez.
- **Renkleri ters çevir**: **Gerekli**'yi seçerek görme bozukluğu olan kullanıcıların ekran görüntüsünü değiştirebilmesi için Renkleri ters çevir erişilebilirlik ayarını zorunlu tutun. **Yapılandırılmadı** ayarı bilgi noktası modunda bu özelliği çalıştırmaz veya etkinleştirmez.
- **Mono ses**: **Gerekli**'yi seçerek cihazda Mono ses erişilebilirlik ayarını zorunlu tutun. **Yapılandırılmadı** ayarı bilgi noktası modunda bu özelliği çalıştırmaz veya etkinleştirmez.
- **VoiceOver**: **Gerekli**'yi seçerek ekrandaki metnin yüksek sesle okunmasını sağlamak için VoiceOver erişilebilirlik ayarını zorunlu tutun. **Yapılandırılmadı** ayarı bilgi noktası modunda bu özelliği çalıştırmaz veya etkinleştirmez.
- **Yakınlaştır**: **Gerekli**'yi seçerek kullanıcıların ekranda yakınlaştırmak için dokunma özelliğini kullanabilmesi için Yakınlaştır ayarını zorunlu tutun. **Yapılandırılmadı** ayarı bilgi noktası modunda bu özelliği çalıştırmaz veya etkinleştirmez.
- **Otomatik kilit**: Cihazın otomatik olarak kilitlenmesine **izin verin**. **Yapılandırılmadı** ayarı bu özelliği devre dışı bırakır.
- **Zil düğmesi**: Cihazda zil (sessiz) düğmesini açmaya **izin verin**. **Yapılandırılmadı** ayarı bu özelliği devre dışı bırakır.
- **Ekran döndürme**: Kullanıcı cihazı döndürdüğünde ekran yönünü değiştirmeye **izin verin**. **Yapılandırılmadı** ayarı bu özelliği devre dışı bırakır.
- **Ekran uyku düğmesi**: Cihazda ekran uyandırma düğmesini devre dışı bırakmak için **İzin Ver**'i seçin. **Yapılandırılmadı** ayarı bu özelliği etkinleştirir.
- **Dokunmatik**: **Engelle** ayarı cihazda dokunmatik ekranı devre dışı bırakır. **Yapılandırılmadı** ayarı kullanıcının dokunmatik ekranı kullanmasına izin verir.
- **Ses düğmeleri**: Cihazda ses düğmelerinin kullanılmasına **izin verin**. **Yapılandırılmadı** ayarı ses düğmelerini devre dışı bırakır.
- **Yardımcı dokunma denetimi**: **İzin Ver** ayarı kullanıcıların yardımcı dokunma işlevini kullanmasına olanak tanır. **Yapılandırılmadı** ayarı bu özelliği devre dışı bırakır.
- **Renkleri ters çevirme denetimi**: Kullanıcıların renkleri tersine çevirme denetimini ayarlamasına olanak sağlamak için renkleri tersine çevirme değişikliklerine **izin verin**. **Yapılandırılmadı** ayarı bu özelliği devre dışı bırakır.
- **Seçilen metinde konuşma**: Cihazda Konuşma Seçimi erişilebilirlik ayarlarının bulunmasına **izin verin**. Bu özellik kullanıcının seçtiği metni yüksek sesle okur. **Yapılandırılmadı** ayarı bu özelliği devre dışı bırakır.
- **VoiceOver denetimi**: Kullanıcıların VoiceOver işlevini güncelleştirmesine, örneğin ekran metninin okunma hızını ayarlamasına olanak sağlamak için VoiceOver değişikliklerine **izin verin**. **Yapılandırılmadı** ayarı VoiceOver değişikliklerini engeller.
- **Yakınlaştırma denetimi**: Kullanıcını yakınlaştırmayı değiştirmesine **izin verin**. **Yapılandırılmadı** ayarı yakınlaştırma değişikliklerini engeller.

> [!NOTE]
> Bir iOS cihazını bilgi noktası modunda yapılandırabilmek için, önce Apple Configurator aracını veya Apple Cihaz Kayıt Programı’nı kullanarak cihazı denetimli moda almanız gerekir. Apple Configurator aracını kullanma konusunda Apple'ın kılavuzuna bakın.
> Girdiğiniz iOS uygulaması siz profil atadıktan sonra yüklendiyse, cihaz yeniden başlatılana kadar bilgi noktası moduna girmez.

## <a name="domains"></a>Domains

- **İşaretlenmemiş e-posta etki alanları** > **E-posta Etki Alanı URL'si**: Listeye bir veya daha fazla URL ekleyin. Son kullanıcılar, girdiğiniz etki alanları dışındaki bir etki alanından e-posta aldığında bu e-posta iOS Mail uygulamasında güvenilmeyen olarak işaretlenir.

- **Yönetilen web etki alanları** > **Web Etki Alanı URL'si**; Listeye bir veya daha fazla URL ekleyin. Belgeler girdiğiniz etki alanlarından indirildiğinde yönetilen belgeler olarak değerlendirilir. Bu ayar yalnızca Safari tarayıcısı kullanılarak indirilen belgeler için geçerlidir.

- **Safari parola otomatik doldurma etki alanları** > **Etki Alanı URL'si**: Listeye bir veya daha fazla URL ekleyin. Kullanıcılar yalnızca bu listedeki URL’lerdeki parolaları kaydedebilir. Bu ayar yalnızca Safari tarayıcısı ve denetimli moddaki iOS 9.3 ve üzeri cihazlar için geçerlidir. Herhangi bir URL belirtmezseniz, parolalar tüm web sitelerinden kaydedilebilir.

## <a name="bundle-ids-for-built-in-ios-apps"></a>Yerleşik iOS uygulamaları için paket kimlikleri

Aşağıdaki liste, bazı yaygın yerleşik iOS uygulamalarının paket kimliğini gösterir. Diğer uygulamaların paket kimliğini bulmak için yazılım satıcınıza başvurun.

| Paket Kimliği                   | Uygulama Adı     | Yayımcı |
|-----------------------------|--------------|-----------|
| com.apple.AppStore          | Uygulama Mağazası    | Apple     |
| com.apple.calculator        | Hesap Makinesi   | Apple     |
| com.apple.mobilecal         | Takvim     | Apple     |
| com.apple.camera            | Kamera       | Apple     |
| com.apple.mobiletimer       | Saat        | Apple     |
| com.apple.compass           | Pusula      | Apple     |
| com.apple.MobileAddressBook | Kişiler     | Apple     |
| com.apple.facetime          | FaceTime     | Apple     |
| com.apple.DocumentsApp      | Dosyalar        | Apple     |
| com.apple.mobileme.fmf1     | Arkadaşları Bul | Apple     |
| com.apple.mobileme.fmip1    | iPhone’u Bul  | Apple     |
| com.apple.gamecenter        | Oyun Merkezi  | Apple     |
| com.apple.mobilegarageband  | GarageBand   | Apple     |
| com.apple.Health            | Sistem Durumu       | Apple     |
| com.apple.Home              | Giriş         | Apple     |
| com.apple.iBooks            | iBooks       | Apple     |
| com.apple.iMovie            | iMovie       | Apple     |
| com.apple.itunesconnect.mobile | iTunes Connect | Apple |
| com.apple.MobileStore       | iTunes Store | Apple     |
| com.apple.itunesu           | iTunes U     | Apple     |
| com.apple.Keynote           | Keynote      | Apple     |
| com.apple.mobilemail        | Mail         | Apple     |
| com.apple.Maps              | Harita         | Apple     |
| com.apple.MobileSMS         | İletiler     | Apple     |
| com.apple.Music             | Müzik        | Apple     |
| com.apple.news              | News         | Apple     |
| com.apple.mobilenotes       | Notlar        | Apple     |
| com.apple.Numbers           | Sayılar      | Apple     |
| com.apple.Pages             | Pages        | Apple     |
| com.apple.Photo-Booth       | Photo Booth  | Apple     |
| com.apple.mobileslideshow   | Fotoğraflar       | Apple     |
| com.apple.podcasts          | Podcast’ler     | Apple     |
| com.apple.reminders         | Anımsatıcılar    | Apple     |
| com.apple.mobilesafari      | Safari       | Apple     |
| com.apple.Preferences       | Ayarlar     | Apple     |
| com.apple.SiriViewService   | Siri         | Apple     |
| com.apple.stocks            | Borsa       | Apple     |
| com.apple.tips              | İpuçları         | Apple     |
| com.apple.TV                | TV           | Apple     |
| com.apple.videos            | Videolar       | Apple     |
| com.apple.VoiceMemos        | Sesli Notlar   | Apple     |
| com.apple.Passbook          | Wallet       | Apple     |
| com.apple.Bridge            | Watch        | Apple     |
| com.apple.weather           | Hava Durumu      | Apple     |

## <a name="settings-that-require-supervised-mode"></a>Denetimli mod gerektiren ayarlar

iOS denetimli modu yalnızca Apple Aygıt Kayıt Programı üzerinden ilk cihaz kurulumu sırasında veya Apple Configurator kullanılarak etkinleştirilebilir. Denetimli mod etkinleştirildikten sonra, Intune şu işlevleri kullanarak bir cihazı yapılandırabilir:

- Uygulama Kilidi (Tek Uygulama Modu) 
- Genel HTTP Proxy’si 
- Etkinleştirme Kilidini Atlama 
- Otonom Tek Uygulama Modu 
- Web İçeriği Filtresi 
- Arka plan ve kilit ekranı ayarlama 
- Uygulamaları Sessiz Gönderme 
- Her Zaman Açık VPN 
- Yönetilen uygulama yüklemesine özel olarak izin verme 
- iBookstore 
- iMessages 
- Oyun Merkezi 
- AirDrop 
- AirPlay 
- Konak eşleştirme 
- Bulut Eşitleme 
- Spotlight arama 
- İletim 
- Cihaz silme 
- Kısıtlamalar kullanıcı arabirimi 
- Kullanıcı arabirimine göre yapılandırma profili yüklemesi 
- News 
- Klavye kısayolları 
- Geçiş kodu değişiklikleri 
- Cihaz adı değişiklikleri 
- Otomatik uygulama indirme 
- Kurumsal uygulama güvenine yapılan değişiklikler 
- Apple Music 
- Posta bırakma 
- Apple Watch ile eşleştirme 

> [!NOTE]
> Apple, 2019’da bazı ayarların yalnızca denetimli hale geleceğini doğruladı. Apple’ın bu ayarları yalnızca denetimli moda aktarmasını beklemek yerine ayarları kullanırken bu durumu göz önünde bulundurmanızı öneririz:
> - Son kullanıcılar tarafından uygulama yükleme
> - Uygulama kaldırma
> - FaceTime
> - Safari
> - iTunes
> - Müstehcen içerik
> - iCloud belgeleri ve verileri
> - Çok oyunculu oyun
> - Oyun Merkezi arkadaşları ekleme
> - Siri

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).

[macOS](device-restrictions-macos.md) cihazlarındaki özellikleri ve ayarları da kısıtlayabilirsiniz.
