---
title: Microsoft Intune'da iOS ayarlarını kullanma - Azure | Microsoft Docs
titleSuffix: ''
description: İOS cihazlarına ayarlar ekleme, yapılandırma veya oluşturma, parola gereksinimlerini ayarlama, kilitli ekranı denetleme, yerleşik uygulamalar kullanma, kısıtlı veya onaylanan uygulamalar ekleme, Bluetooth cihazlarını işleme, yedekleme ve depolama için buluta bağlanma, bilgi noktası modunu etkinleştirin, etki alanları ekleyin ve kullanıcıların Microsoft Intune ' de Safari web tarayıcısıyla nasıl etkileşime gireceğini denetleyin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/24/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: e31fc3b199f6437bbdd7b12e4be8b17ead689c7e
ms.sourcegitcommit: 6a946a055a2014e00a4ca9d71986727a4ebbc777
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71302381"
---
# <a name="ios-and-ipados-device-settings-to-allow-or-restrict-features-using-intune"></a>Intune kullanarak özelliklere izin vermek veya erişimi kısıtlamak için iOS ve ıpados cihaz ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makalede iOS ve ıpados cihazlarında denetleyebileceğinizi belirten farklı ayarlar listelenir. Mobil cihaz yönetimi (MDM) çözümünüz kapsamında bu ayarları kullanabilir ve bu sayede özellikleri etkinleştirip devre dışı bırakabilir, parola kuralları uygulayabilir, belirli uygulamalara izin verebilir veya bunları kısıtlayabilir ve çok daha fazlasını yapabilirsiniz.

Bu ayarlar, Intune'da bir cihaz yapılandırma profiline eklenir ve daha sonra iOS cihazlarınıza atanır veya dağıtılır.

> [!TIP]
> Bu ayarlar Apple MDM ayarlarını kullanır. Bu ayarlar hakkında daha fazla bilgi için bkz. [Apple 'ın mobil cihaz yönetimi ayarları](https://support.apple.com/guide/mdm/welcome/web) (Apple 'ın Web sitesini açar).

## <a name="before-you-begin"></a>Başlamadan önce

[Cihaz kısıtlamaları yapılandırma profili oluşturma](device-restrictions-configure.md).

> [!NOTE]
> Bu ayarlar, bazı ayarların tüm kayıt seçeneklerine uygulanmasıyla farklı kayıt türleri için geçerlidir. Farklı kayıt türleri hakkında daha fazla bilgi için bkz. [iOS kaydı](ios-enroll.md).

## <a name="general"></a>Genel

### <a name="settings-apply-to-all-enrollment-types"></a>Ayarlar için geçerlidir: Tüm kayıt türleri

- **Kullanım verilerini paylaşma**: Cihazın Apple’a tanılama ve kullanım verileri göndermesini engellemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı bu verilerin gönderilmesine izin verir.

- **Ekran yakalama**: Cihazda ekran görüntülerini veya ekran yakalamalarını önlemek için **Engelle**'yi seçin. İOS 9,0 ve üzeri sürümlerde ekran kayıtlarını da engeller. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının ekran içeriğini bir resim veya video olarak yakalamasına olanak tanır.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Cihaz kaydı, otomatik cihaz kaydı (denetimli)

- **Güvenilmeyen TLS sertifikaları**: Cihazda güvenilmeyen Aktarım Katmanı Güvenliği (TLS) sertifikalarını önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı TLS sertifikalarına izin verir.
- **Havadan PKI güncelleştirmelerine izin ver**: **İzin Ver** ayarı kullanıcılarınızın cihazlarını bir bilgisayara bağlamadan yazılım güncelleştirmeleri almasına olanak tanır.
- **Reklam izlemeyi sıfırla**: Cihaz reklam tanımlayıcısını devre dışı bırakmak için **Sınırla**'yı seçin. **Yapılandırılmadı** (varsayılan) bu tanımlayıcının etkin kalmasını sağlar.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Otomatik cihaz kaydı (denetimli)

- **Tanılama gönderme ayarlarının değiştirilmesi**: **Engelle** ayarı kullanıcının **Tanılama ve Kullanım** (cihaz ayarları) altındaki tanılama gönderimi ve uygulama analizi ayarlarını değiştirmesini engeller. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının bu cihaz ayarlarını değiştirmesine izin verir.

  Bu ayarı kullanmak için, **kullanım verilerini paylaşma** ayarını **Engelle**olarak ayarlayın.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 9.3.2 ve üzeri

- **Sınıf uygulamasına göre uzak ekran gözlemme**: Classroom uygulamasının cihazda ekranı uzaktan görüntülemesini önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı Apple Classroom uygulamasının ekranı görüntülemesine izin verir.

  Bu ayarı kullanmak için **ekran yakalama** ayarını **Engelle**olarak ayarlayın.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 9,3 ve üzeri

- **Sınıf uygulamasına göre sorulmayacak ekran izleme**: **İzin Ver** olarak ayarlanırsa öğretmenler öğrencilerin bilgisi olmadan Classroom uygulamasını kullanarak, öğrencilerin iOS cihazlarının ekranını sessizce izleyebilir. Classroom uygulaması kullanılarak sınıfa kaydedilmiş olan öğrenci cihazları, söz konusu dersin öğretmenine otomatik olarak izin verir. **Yapılandırılmadı** (varsayılan) ayarı bu özelliği engeller.

  Bu ayarı kullanmak için **ekran yakalama** ayarını **Engelle**olarak ayarlayın.

- **Kurumsal uygulama güveni**: Cihazda Ayarlar > Genel > Profiller ve Cihaz Yönetimi altındaki **Güvenilen Kurumsal Geliştirici** düğmesini kaldırmak için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının uygulama mağazasından indirilmemiş uygulamalara güvenmeyi seçmesine olanak tanır.
- **Hesap değişikliği**: **Engelle** olarak ayarlandığında kullanıcı iOS ayarlar uygulamasından cihaza özgü ayaları güncelleştiremez. Örneğin kullanıcı yeni cihaz hesapları oluşturamaz ya da kullanıcı adını veya parolasını değiştiremez. **Yapılandırılmadı** (varsayılan) ayarı kullanıcıların bu ayarları değiştirmesine izin verir.

  Bu özellik Posta, Kişiler, Takvim ve Twitter gibi iOS ayarları uygulamasından erişilebilen ayarlar için de geçerlidir. Bu özellik hesap ayarları iOS ayarları uygulamasından yapılandırılamayan uygulamalar (Microsoft Outlook uygulaması gibi) için geçerli değildir.

- **Ekran zamanı**: Kullanıcıların Ekran Saati'nde (cihaz ayarları) kendi kısıtlamalarını ayarlamalarını önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** kullanıcının cihazda cihaz kısıtlamalarını (ebeveyn denetimleri veya içerik ve gizlilik kısıtlamaları gibi) yapılandırmasına izin verir.

  Bu ayar **Cihaz ayarlarında kısıtlamaları etkinleştirme** ayarının yeniden adlandırılmış halidir. Bu değişikliğin etkisi:  
  
  - iOS 11.4.1 ve öncesi: **Engelle** ayarı son kullanıcıların cihaz ayarlarında kendi kısıtlamalarını ayarlamalarını önler. Davranış aynıdır; ve son kullanıcılar için herhangi bir değişiklik yoktur.
  - iOS 12,0 ve üzeri: **Engelle** ayarı son kullanıcıların içerik ve gizlilik kısıtlamaları da dahil olmak üzere cihaz ayarlarında kendi **Ekran Saati** (Ayarlar > Genel > Ekran Saati) ayarlarını yapmalarını önler. iOS 12.0'dan yükseltilen cihazlar artık cihaz ayarlarında kısıtlamalar sekmesini (Ayarlar > Genel > Cihaz Yönetimi > Yönetim Profili > Kısıtlamalar) görmez. Bu ayarlar **Ekran Saati** altındadır.
  
- **Cihazda tüm içeriği ve ayarları silme seçeneğinin kullanımı**: **Engelle** ' yi seçin, böylece kullanıcılar cihazdaki tüm içeriği ve ayarları silme seçeneğini kullanamaz. **Yapılandırılmadı** (varsayılan) ayarı kullanıcılara bu ayarlar için erişim verir.
- **Cihaz adı değişikliği**: Cihaz adının değiştirilememesi için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının cihaz adını değiştirmesine izin verir.
- **Bildirim ayarlarının değiştirilmesi**: Bildirim ayarlarının değiştirilememesi için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının cihaz bildirim ayarlarını değiştirmesine izin verir.
- **Duvar kağıdı değişikliği**: **Engelle** ayarı duvar kağıdının değiştirilmesini önler. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının cihazda duvar kağıdını değiştirmesine izin verir.
- **Kurumsal uygulama güven ayarlarının değiştirilmesi**: **Engelle** ayarı kullanıcının denetimli cihazlarda kurumsal uygulama güven ayarlarını değiştirmesini önler. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının uygulama mağazasından indirilmemiş uygulamalara güvenmesine izin verir.
- **Yapılandırma profili değişiklikleri**: **Engelle** ayarı cihazda yapılandırma profili değişikliklerini önler. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının yapılandırma profillerini yüklemesine izin verir.
- **Etkinleştirme Kilidi**: Denetimli iOS cihazlarında Etkinleştirme Kilidi’ni etkinleştirmek için **İzin Ver**'i seçin. Etkinleştirme Kilidi, kaybolan veya çalınan bir cihazın yeniden etkinleştirilmesini zorlaştırır.
- **Uygulama kaldırmayı engelle**: Kullanıcıların uygulamaları kaldırmasını önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı kullanıcıların cihazdan uygulama kaldırmasına izin verir.
- **Bloklar USB kısıtlı modu**: Denetimli cihazlarda USB Kısıtlı modunu devre dışı bırakmak için **Engelle**'yi seçin. USB kısıtlı modu, USB aksesuarları 'nin bir saatten daha fazla kilitlenen bir cihazla veri alışverişi yapılmasını engeller. **Yapılandırılmadı** (varsayılan) ayarı USB Kısıtlı moduna izin verir.
- **Otomatik tarih ve saati zorla**: **Gerekli** ayarı denetimli cihazların Tarih ve Saati otomatik olarak ayarlamasını zorunlu tutar. Cihazın hücresel bağlantıları olduğunda veya konum hizmetleriyle arasında Wi-Fi etkinleştirildiğinde saat dilimi güncelleştirilir.
- **Öğrencilerin sınıf kursuna izin Istemesini gerektir**: **Gerekli** ayarı Classroom uygulamasını kullanarak yönetilmeyen bir derse kaydolan öğrencilerin dersten ayrılmadan önce öğretmenden izin istemesini zorunlu tutar. **Yapılandırılmadı** (varsayılan) ayarı öğrencinin izin istemesini zorunlu tutmaz.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11,3 ve üzeri

- **Sınıfa, bir uygulamaya kilitleme ve cihazı sormadan kilitleme Izni ver**: **Etkinleştir** ayarı öğretmenin Classroom uygulamasını kullanarak öğrenciye sormadan uygulamaları kilitlemesine veya cihazı kilitlemesine izin verir. Uygulamaların kilitlenmesi cihazın yalnızca öğretmenin belirttiği uygulamalara erişebileceği anlamına gelir. **Yapılandırılmadı** (varsayılan) ayarı öğretmenlerin öğrenciye sormadan Classroom uygulamasını kullanarak uygulamaları veya cihazları kilitlemesini önler. 

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11,0 ve üzeri

- **Sınıf sınıflarını sormadan otomatik olarak birleştir**: **Etkinleştir** ayarı öğrencilerin öğretmene sormadan Classroom uygulamasındaki derse otomatik olarak katılmasına izin verir. **Yapılandırılmadı** (varsayılan) ayarı öğrencilerin Classroom uygulamasındaki derse katılma isteğini öğretmene sorar.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11,0 ve üzeri

- **VPN oluşturmayı engelle**: **Engelle** ayarı kullanıcıların VPN yapılandırma ayarları oluşturmasını önler. **Yapılandırılmadı** (varsayılan) ayarı kullanıcıların cihazda VPN'ler oluşturmasına olanak tanır.
- **Esım ayarlarını değiştirme**: **Engelle** ayarı kullanıcıların cihazda eSIM için hücresel planı kaldırmasını veya eklemesini önler. **Yapılandırılmadı** (varsayılan) ayarı kullanıcıların bu ayarları değiştirmesine izin verir.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 12,1 ve üzeri

- **Yazılım güncelleştirmelerini ertele**: **Yapılandırılmadı** (varsayılan) olarak ayarlandığında Apple tarafından yayımlanan yazılım güncelleştirmeleri anında cihazda gösterilir. Örneğin Apple tarafından bir iOS güncelleştirmesinin yayımlanması durumunda ilgili güncelleştirme normal bir şekilde yayın tarihinde cihazda görünür.

  **Etkinleştir** ayarını kullanarak güncelleştirmelerin cihazlarda gösterilmesini 0-90 gün boyunca geciktirebilirsiniz. Bu ayar, güncelleştirmelerin yüklenme tarihini veya durumunu denetlemez. 

  - **Yazılım güncelleştirmelerinin görünürlüğünü geciktir**: 0-90 gün arasında bir değer girin. Gecikme süresi sona erdiğinde kullanıcılara gecikmenin tetiklendiği tarihte kullanılabilir durumda olan en eski işletim sistemi sürümüne güncelleştirme bildirimi gönderilir.

    Örneğin **1 Ocak** tarihinde iOS.12a'nın yayımlanması ve **Görünürlük geciktirme** ayarının **5 gün** olması durumunda iOS 12.a, son kullanıcı cihazlarında kullanılabilir güncelleştirme olarak gösterilmez. Yayımlandıktan sonraki **altıncı günde** bu güncelleştirme kullanıma sunulur ve kullanıcılar tarafından yüklenebilir.

    Bu ayarın geçerli olduğu sürümler:  
    - iOS 11,3 ve üzeri

## <a name="password"></a>istemcisiyle yönetilen bir cihaz için)

### <a name="settings-apply-to-all-enrollment-types"></a>Ayarlar için geçerlidir: Tüm kayıt türleri

- **Parola**: **Gerekli** ayarı son kullanıcının cihaza erişmek için parola girmesini zorunlu tutar. **Yapılandırılmadı** (varsayılan) kullanıcıların bir parola girmeden cihaza erişmesine izin verir.
  - **Basit parolalar**: Daha karmaşık parolaları zorunlu tutmak için **Engelle**'yi seçin. **Yapılandırılmadı** ayarı `0000` ve `1234` gibi basit parolalara izin verir.
  - **Gerekli parola türü**: Kuruluşunuzun gerektirdiği parola türünü seçin. Seçenekleriniz şunlardır:
    - **Cihaz varsayılanı**
    - **Sayısal**
    - **Alfasayısal**
  - **Paroladaki alfasayısal olmayan karakter sayısı**: Parolada bulunması gereken `#` veya `@` gibi simge karakterlerinin sayısını belirtin.
  - **Minimum parola uzunluğu**: Kullanıcının girmesi gereken minimum uzunluğu 4 ile 14 karakter arasında girin. Kullanıcı kayıtlı cihazlarda 4 ila 6 karakter uzunluğunda bir uzunluk girin.
  
    > [!NOTE]
    > Kullanıcı tarafından kaydedilen cihazlar için:
    >  - Mevcut bir PIN 6 karakterden fazlaysa, yalnızca ilk 6 karakter kullanılır. Örneğin, PIN 'iniz ise `12345678`, PIN ' i `123456`kısaltıldı.
    >  - Kullanıcılar 6 karakterden büyük yeni bir PIN girerseniz, yalnızca ilk 6 karakter kullanılır. Örneğin, PIN olarak girerseniz `12345678` , PIN ' i `123456`kısaltıldı.

  - **Cihaz silinmeden önceki oturum açma hatası sayısı**: Cihaz temizlenmeden önce izin verilecek başarısız oturum açma işlemlerinin sayısını girin (4-11 arasında).
  
    iOS, bu ayarı etkileyebilecek yerleşik güvenliğe sahiptir. Örneğin, iOS, oturum açma hatalarının sayısına bağlı olarak ilkeyi tetikleyebilir. Aynı zamanda aynı geçiş kodunu bir girişimlerle tekrar girmeyi de düşünebilirsiniz. Apple 'ın [iOS Güvenlik Kılavuzu](https://www.apple.com/business/site/docs/iOS_Security_Guide.pdf) (Apple 'ın Web sitesini açar) iyi bir kaynaktır ve Passcodes hakkında daha ayrıntılı bilgiler sağlar.
  
  - **Ekran kilitlendikten sonra parola istenene kadar geçmesi gereken, işlem yapılmayan dakika sayısı**<sup>1</sup>: Kullanıcının parolasını yeniden girmesi gerekmeden önce cihazın ne kadar süreyle boşta kalacağını girin. Girdiğiniz süre cihazda şu anda ayarlanmış olan süreden uzunsa, cihaz girdiğiniz süreyi yoksayar. iOS 8.0 ve daha yeni cihazlarda desteklenir.
  - **Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı**<sup>1</sup>: Ekran otomatik olarak kilitlenmeden önce izin verilecek işlem yapılmayan en fazla dakika sayısını girin. Girdiğiniz süre cihazda şu anda ayarlanmış olan süreden uzunsa, cihaz girdiğiniz süreyi yoksayar. **Hemen**olarak ayarlandığında ekran, cihazın en kısa zamanına bağlı olarak kilitlenir. İPhone 'da 30 saniyedir. İPad 'de bu iki dakikadır.
  - **Parola zaman aşımı (gün sayısı)** : Cihaz parolasının değiştirilmesi gerekmeden önce geçmesi gereken gün sayısını girin.
  - **Önceki parolaların yeniden kullanılmasını engelleme**: Eski bir parolanın yeniden kullanılabilmesi için önce kullanılması gereken yeni parola sayısını girin.
  - **Dokunma kimliği ve yüz kimliği kilit açma**: Cihazın kilidini açmak için parmak izi veya yüz kullanımını engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** , kullanıcının bu yöntemleri kullanarak cihazın kilidini açmasına izin verir.

    Bu ayarı engellemek, cihazın kilidini açmak için çok yönlü kimlik doğrulamasının kullanılmasını da engeller.

    Yüz KIMLIĞI şu şekilde geçerlidir:  
    - iOS 11,0 ve üzeri

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Otomatik cihaz kaydı (denetimli)

- **Geçiş kodu değişikliği**: Geçiş kodu değiştirme, ekleme veya kaldırma işlemlerini durdurmak için **Engelle**'yi seçin. Bu özellik engellendikten sonra denetimli cihazlarda geçiş kodu kısıtlamalarında yapılan değişiklikler yoksayılır. **Yapılandırılmadı** (varsayılan) ayarı geçiş kodu ekleme, değiştirme veya kaldırma işlemlerine izin verir.

  - **Dokunma kimliği ve yüz kimliği değişikliği**: **Blok** , kullanıcının TouchID parmak Izlerini ve yüz kimliğini değiştirmesini, eklemesini veya kaldırmasını engeller. **Yapılandırılmadı** (varsayılan) kullanıcının cihazdaki TouchID parmak izlerini ve yüz KIMLIĞINI güncelleştirmesine izin verir.

    Bu ayarı engellemek, kullanıcının çok yönlü kimlik doğrulamasını değiştirmesini, eklemesini veya kaldırmasını de engeller.

    Yüz KIMLIĞI şu şekilde geçerlidir:  
    - iOS 11,0 ve üzeri

- **Parola Otomatik Doldurmayı engelle**: iOS Parola Otomatik Doldurma özelliğini engellemek için **Engelle**'yi seçin. **Engelle** ayarını seçmek şu sonuçlara da neden olur:

  - Safari'de veya diğer uygulamalarda kullanıcılara parolaları kaydetmek isteyip istemedikleri sorulmaz.
  - Otomatik Güçlü Parolalar devre dışı bırakılır ve kullanıcılara güçlü parola önerisi sunulmaz.

  **Yapılandırılmadı** (varsayılan) ayarı bu özelliklere izin verir.

- **Parola yakınlık isteklerini engelle**: **Engelle**'yi seçtiğinizde kullanıcının cihazı yakınlardaki cihazlardan parola isteyemez. **Yapılandırılmadı** (varsayılan) ayarı bu parola isteklerine izin verir.
- **Parola paylaşımını engelle**: **Engelle**, AirDrop ile cihazlar arasında parola paylaşımı yapılmasını engeller. **Yapılandırılmadı** (varsayılan) ayarı, parolaların paylaşılmasına izin verir.
- **Parola veya kredi kartı bilgileri Için dokunma kimliği veya yüz kimliği kimlik doğrulaması ıste otomatik doldurma**: **Gerekli** olarak ayarlandığında Safari'de ve diğer uygulamalarda parolaların veya kredi kartı bilgilerinin otomatik olarak doldurulması için önce kullanıcıların TouchID veya FaceID ile kimlik doğrulaması yapması gerekir. **Yapılandırılmadı** (varsayılan) ayarı kullanıcıların cihaz ayarlarında bu özelliği denetlemesine izin verir.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11,0 ve üzeri
  
<sup>1</sup>**Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı** ve **Ekran kilitlendikten sonra parola istenene kadar geçmesi gereken, işlem yapılmayan dakika sayısı**, ayarlarını yapılandırdığınızda, bunlar sırayla uygulanır. Örneğin, her iki ayarın da değerini **5** dakikaya ayarlarsanız, ekran beş dakika sonra otomatik olarak kapanır ve cihazın kilitlenmesi için beş dakika daha geçmesi gerekir. Ancak, kullanıcı ekranı el ile kapatırsa ikinci ayar hemen uygulanır. Aynı örnekte, kullanıcı ekranı kapattıktan sonraki beş dakikanın sonunda cihaz kilitlenir.

## <a name="locked-screen-experience"></a>Kilit Ekranı Deneyimi

### <a name="settings-apply-to-all-enrollment-types"></a>Ayarlar için geçerlidir: Tüm kayıt türleri

- **Cihaz kilitliyken Denetim Merkezi erişimi**: Cihaz kilitliyken Denetim Merkezi uygulamasına erişimi önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) cihaz kilitlendiğinde kullanıcıların Denetim Merkezi uygulamasına erişmesine izin verir.
- **Cihaz kilitliyken bildirimler**: **Engelle** ayarı cihaz kilitliyken bildirimlere erişilmesini önler. **Yapılandırılmadı** (varsayılan) kullanıcının cihazın kilidini açmadan bildirimlere erişmesine izin verir.
- **Cihaz kilitliyken Bugün görünümü**: **Engelle** ayarı cihaz kilitliyken Bugün görünümüne erişilmesini önler. **Yapılandırılmadı** (varsayılan) cihaz kilitlendiğinde kullanıcının bugün görünümünü görmesini sağlar.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Cihaz kaydı, otomatik cihaz kaydı (denetimli)

- **Cihaz kilitliyken Cüzdan bildirimleri**: **Engelle** ayarı cihaz kilitliyken Cüzdan uygulamasına erişilmesini önler. **Yapılandırılmadı** (varsayılan), Cihaz kilitliyken kullanıcının cüzdan uygulamasına erişmesine izin verir.

## <a name="app-store-doc-viewing-gaming"></a>Uygulama Mağazası, Belge Görüntüleme, Oyun

### <a name="settings-apply-to-all-enrollment-types"></a>Ayarlar için geçerlidir: Tüm kayıt türleri

- **Yönetilmeyen uygulamalarda kurumsal belgeleri görüntüleme**: **Engelle** ayarı yönetilmeyen uygulamalarda kurumsal belgelerin görüntülenmesini önler. **Yapılandırılmadı** (varsayılan) Şirket belgelerinin herhangi bir uygulamada görüntülenmesine izin verir. Örneğin kullanıcıların OneDrive uygulamasından Dropbox’a dosya kaydetmesini engellemek istiyorsunuz. Bu ayarı **Engelle** olarak yapılandırın. Cihaz ilkeyi aldıktan sonra (örneğin, yeniden başlatıldıktan sonra) artık kaydetmeye izin vermez.

  - **Yönetilmeyen uygulamaların yönetilen kişi hesaplarından kişi okumasına izin ver**: **Izin ver**olarak ayarlandığında, yerleşik iOS kişileri uygulaması gibi yönetilmeyen uygulamalar, Outlook mobil uygulaması da dahil olmak üzere yönetilen uygulamalardan iletişim bilgilerini okuyabilir ve bunlara erişebilir. **Yapılandırılmadı** (varsayılan), cihazdaki yerleşik Kişiler uygulamasından yinelenenleri kaldırma dahil olmak üzere okumayı engeller.  
  
    Bu ayar, iletişim bilgilerinin okunmasına izin verir veya bunu engeller. Uygulamalar arasındaki kişileri eşitlemeyi denetlemez.
  
    Bu ayarı kullanmak için **Yönetilmeyen uygulamalarda kurumsal belgeleri görüntüleme** ayarını **Engelle** olarak belirtin.

  Bu iki ayar hakkında daha fazla bilgi ve iOS için Outlook 'a yönelik ilgili kişileri dışarı aktarma eşitlemesi hakkında daha [fazla bilgi için bkz. destek İpucu: İOS yerel kişiler uygulamasıyla](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Use-Intune-custom-profile-settings-with-the-iOS/ba-p/298453)Intune özel profil ayarlarını kullanın.

- **AirDrop'u yönetilmeyen uygulama olarak değerlendir**: **Gerekli** ayarı AirDrop'un yönetilmeyen bırakma hedefi olarak kabul edilmesini zorunlu tutar. Yönetilen uygulamaların Airdrop'u kullanarak veri göndermesini durdurur. 
- **Kurumsal olmayan belgeleri kurumsal uygulamalarda görüntüleme**: **Engelle** ayarı kurumsal olmayan belgelerin kurumsal uygulamalarda görüntülenmesini önler. **Yapılandırılmadı** (varsayılan) Şirket tarafından yönetilen uygulamalarda tüm belgelerin görüntülenmesine izin verir.

  **Engelleme** ayarı, IOS için Outlook 'ta de ilgili kişileri dışarı aktarma eşitlemesini engeller. Daha fazla bilgi için bkz [. destek İpucu: İOS12 MDM denetimleriyle](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Enabling-Outlook-iOS-Contact-Sync-with-iOS12-MDM/ba-p/298453)Outlook iOS iletişim eşitlemesini etkinleştirme.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Cihaz kaydı, otomatik cihaz kaydı (denetimli)

- **Tüm satın alımlarda ITunes mağazası parolası iste**: Kullanıcının her uygulama içi veya ITunes satın alma için Apple KIMLIĞI parolasını girmesini **gerektir** . **Yapılandırılmadı** (varsayılan) her seferinde parola sormadan satın alma işlemlerine izin verir.
- **Uygulama içi satın alımlar**: Mağazadan uygulama içi satın alımları önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan), satın alma işlemlerinin çalışan bir uygulama içinde depolanmasını sağlar.
- **iBook mağazasından 'Erotik' olarak işaretlenmiş içerik indirme**: Kullanıcıların iBook mağazasından erotik olarak etiketlenmiş medyayı indirmesini önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) kullanıcının "Erotika" kategorisiyle kitap indirmesine izin verir.
- **Yönetilen uygulamaların yönetilmeyen kişi hesaplarına kişi yazmasına izin ver**: **Izin ver**olarak ayarlandığında, Outlook Mobile uygulaması gibi yönetilen uygulamalar, iş ve şirket kişileri dahil iletişim bilgilerini yerleşik iOS kişileri uygulamasına kaydedebilir veya eşitleyebilir. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, yönetilen uygulamalar cihazdaki yerleşik iOS kişileri uygulamasına iletişim bilgilerini kaydedemez veya eşitleyemez.
  
  Bu ayarı kullanmak için **Yönetilmeyen uygulamalarda kurumsal belgeleri görüntüleme** ayarını **Engelle** olarak belirtin.

- **Derecelendirme bölgesi**: İzin verilen indirmeler için derecelendirme bölgesini seçin. Ardından, **filmler**, **TV programları**ve **uygulamalar**için izin verilen derecelendirmeleri seçin.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Otomatik cihaz kaydı (denetimli)

- **Uygulama mağazası**: **Engelle** ayarı denetimli cihazlarda uygulama mağazasına erişimi önler. **Yapılandırılmadı** (varsayılan) erişim sağlar.

  İOS 13,0 ' den itibaren, bu ayar denetimli cihazlar gerektirir.

  - **App Store 'dan uygulama yükleme**: Cihaz giriş ekranında uygulama mağazasını engellemek için **Engelle**'yi seçin. Son kullanıcılar, uygulamaları yüklemek için iTunes’u veya Apple Configurator aracını kullanmaya devam edebilir. **Yapılandırılmadı** (varsayılan), uygulama mağazasının giriş ekranında yapılmasına izin verir.
  - **Otomatik uygulama indirmeleri**: Başka cihazlarda satın alınmış uygulamaların otomatik olarak indirilmesini önlemek için **Engelle**'yi seçin. Mevcut uygulamalarında yapılan güncelleştirmeler bundan etkilenmez. **Yapılandırılmadı** (varsayılan), diğer iOS cihazlarında satın alınan uygulamaların cihaza indirilmesine izin verir.

- **Açık iTunes Music, podcast veya News içeriği**: Müstehcen iTunes müziği, pod yayını veya haber içeriğini önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) cihazın depodan yetişkin olarak derecelendirilmiş içeriğe erişmesine izin verir. iOS 13 ve üzeri, yalnızca denetimli cihazlar gerektirebilir. 

  İOS 13,0 ' den itibaren, bu ayar denetimli cihazlar gerektirir.

- **Game Center arkadaşlar ekleme**: **Engelle** ayarı kullanıcıların Game Center arkadaşları eklemesini önler. **Yapılandırılmadı** (varsayılan) kullanıcının Game Center arkadaş eklemesine izin verir.

  İOS 13,0 ' den itibaren, bu ayar denetimli cihazlar gerektirir.

- **Game Center**: Game Center uygulamasının kullanılmasını **engelleyin**. **Yapılandırılmadı** (varsayılan) cihazda Game Center uygulamasının kullanılmasına izin verir.
- Çok **oyunculu oyunlar**: Çok oyunculu oyunları önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) kullanıcının cihazda çok oyunculu oyunlar oynamasına izin verir.

  İOS 13,0 ' den itibaren, bu ayar denetimli cihazlar gerektirir.

## <a name="built-in-apps"></a>Yerleşik Uygulamalar

### <a name="settings-apply-to-all-enrollment-types"></a>Ayarlar için geçerlidir: Tüm kayıt türleri

- **Siri**: **Engelle** ayarı Siri'ye erişimi önler. **Yapılandırılmadı** (varsayılan) cihazda Siri Voice Yardımcısı 'nın kullanılmasına izin verir.
  - **Cihaz kilitliyken Siri**: Cihaz kilitliyken Siri'ye erişimi önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan), kilitlendiğinde, cihazda Siri Voice Yardımcısı 'nın kullanılmasına izin verir.

- **Safari sahtekarlık uyarıları**: Cihazdaki web tarayıcısında sahtekarlık uyarılarının gösterilmesini **gerektirin**. **Yapılandırılmadı** (varsayılan) ayarı, bu özelliği devre dışı bırakır.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Cihaz kaydı, otomatik cihaz kaydı (denetimli)

- **Internet 'ten sonuçları döndürmek Için Spotlight araması**: **Engelle** ayarı Spotlight'ın İnternet araması sonuçlarını döndürmesini durdurur. **Yapılandırılmadı** (varsayılan) ayarı, Spotlight'ın internete bağlanarak arama sonuçlarını getirmesine izin verir.

- **Safari tanımlama bilgileri**: Cihazda tanımlama bilgilerinin nasıl işleneceğini seçin. Seçenekleriniz şunlardır:
  - Allow
  - Tüm tanımlama bilgilerini engelle
  - Ziyaret edilen web sitelerinin tanımlama bilgilerine izin ver
  - Geçerli web sitesinin tanımlama bilgilerine izin ver

- **Safari JavaScript**: **Engelle** ayarı tarayıcıdaki Java betiklerinin cihazda çalıştırılmasını önler. **Yapılandırılmadı** (varsayılan) Java betiklerine izin verir.

- **Safari açılır pencereleri**: Web tarayıcısında açılır pencere engelleyicisini devre dışı bırakmak için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) açılır pencere engelleyiciye izin verir.

- **Siri komutları Için sunucu tarafında günlüğe kaydetme**: **Disable**olarak ayarlandığında, sunucu tarafı Siri günlüğü kapalıdır. Ayrıca, Siri sunucularında kullanıcı isteklerinin günlüğe kaydedilmesini da engelleyebilir. **Yapılandırılmadı** (varsayılan) sunucu tarafında Siri komutlarını günlüğe kaydeder. Bu ayar engellenmekte olan veya yapılandırılmamış Siri ayarına bağlı değildir.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 12,2 ve üzeri

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Otomatik cihaz kaydı (denetimli)

- **Kamera**: Cihazdaki kameraya erişim sağlanmasını engellemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı, cihazın kamerasına erişim sağlar.

  İOS 13,0 ' den itibaren, bu ayar denetimli cihazlar gerektirir.

  - **FaceTime**: FaceTime uygulamasına erişimi önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) cihazda çok yönlü bir zaman uygulamasına erişime izin verir.

    İOS 13,0 ' den itibaren, bu ayar denetimli cihazlar gerektirir.

- **Siri küfür filtresi**: **Gerekli** ayarı Siri’nin küfürlü dil dikte etmesini veya konuşmasını engeller.

  Bu ayarı kullanmak için **Siri** ayarını **Engelle**olarak ayarlayın.

- **Siri Kullanıcı tarafından oluşturulan içeriği Internet 'ten sorgulamak için**: **Engelle** ayarı Siri'nin soruları yanıtlamak için web sitelerine erişmesini önler. **Yapılandırılmadı** (varsayılan), Siri 'in Internet 'ten Kullanıcı tarafından oluşturulan içeriğe erişmesine izin verir.

  Bu ayarı kullanmak için **Siri** ayarını **Engelle**olarak ayarlayın.

- **Apple News**: Cihazda Apple News uygulamasına erişimi engellemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) Apple News uygulamasının kullanılmasına izin verir.
- **IBOOKS deposu**: **Engelle** ayarı iBooks mağazasına erişimi engeller. **Yapılandırılmadı** (varsayılan), kullanıcıların, IBook mağazasından kitap alıp almasına izin verir.
- **Cihazdaki iletiler uygulaması**: **Blok** , kullanıcıların IMessage için iletiler uygulamasını kullanmalarını engeller. Cihaz metin iletilerini destekliyorsa, kullanıcı SMS kullanarak SMS mesajları gönderip alabilir. **Yapılandırılmadı** (varsayılan) Iletileri Internet üzerinden göndermek ve okumak için Iletiler uygulamasının kullanılmasına izin verir.
- **Pod yayınları**: **Engelle** ayarı kullanıcıların Podcasts uygulamasını kullanmasını önler. **Yapılandırılmadı** (varsayılan) Pod yayınları uygulamasının kullanılmasına izin verir.
- **Müzik hizmeti**: **Engelle** ayarı Müzik uygulamasını klasik moda döndürür ve Müzik hizmetini devre dışı bırakır. **Yapılandırılmadı** (varsayılan) ayarı, Apple Music uygulamasının kullanılmasına izin verir.
- **ITunes radyo hizmeti**: **Engelle** ayarı kullanıcıların iTunes Radio uygulamasını kullanmasını önler. **Yapılandırılmadı** (varsayılan) iTunes Radyo uygulamasının kullanılmasına izin verir.
- **iTunes Mağazası**: **Yapılandırılmadı** (varsayılan) cihazlarda iTunes 'a izin verir. **Blok** , kullanıcıların cihazda iTunes kullanmasını engeller. 

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 4,0 ve üzeri

- **İPhone 'umu bul**: **Yapılandırılmadı** (varsayılan) cihazın yaklaşık konumunu almak için bu uygulama Bul özelliğinin kullanılmasına izin verir. **Block** , bu özelliğin uygulamamda Bul özelliğini engelliyor. 

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 13,0 ve ıpados 13,0 ve üzeri

- **Arkadaşlarımı bul**: **Yapılandırılmadı** (varsayılan) bir Apple cihazından veya iCloud.com aile ve arkadaşlar bulmak için bu uygulamamı Bul özelliğinin kullanılmasına izin verir. **Block** , bu özelliğin uygulamamda Bul özelliğini engelliyor.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 13,0 ve ıpados 13,0 ve üzeri

- **Arkadaşlarımı bul uygulama ayarlarında yapılan değişiklikler**: **Engelle** ayarı Arkadaşlarımı Bul uygulamasının ayarlarında yapılan değişiklikleri önler. **Yapılandırılmadı** (varsayılan) kullanıcının Arkadaşlarımı Bul uygulamasının ayarlarını değiştirmesine izin verir.

- **Internet 'ten sonuçları döndürmek Için Spotlight araması**: **Engelle** ayarı Spotlight'ın İnternet araması sonuçlarını döndürmesini durdurur. **Yapılandırılmadı** (varsayılan) ayarı, Spotlight'ın internete bağlanarak arama sonuçlarını getirmesine izin verir.

- **Cihazdan sistem uygulamalarının kaldırılmasını engelle**: **Engelle** ayarı seçildiğinde cihazdan sistem uygulamalarını kaldırabilme özelliği devre dışı bırakılır. **Yapılandırılmadı** (varsayılan) kullanıcıların sistem uygulamalarını kaldırmasına izin verir.

- **Safari**: Cihazda Safari tarayıcısının kullanılmasını **engelleyin**. **Yapılandırılmadı** (varsayılan) kullanıcıların Safari tarayıcısını kullanmasına izin verir.

  İOS 13,0 ' den itibaren, bu ayar denetimli cihazlar gerektirir.

- **Safari otomatik doldurma**: **Engelle** ayarı cihazdaki Safari uygulamasında otomatik doldurma özelliğini devre dışı bırakır. **Yapılandırılmadı** (varsayılan) ayarı, kullanıcıların web tarayıcısındaki otomatik tamamlama ayarlarını değiştirmesine olanak tanır.

  İOS 13,0 ' den itibaren, bu ayar denetimli cihazlar gerektirir.

## <a name="restricted-apps"></a>Kısıtlı uygulamalar

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Cihaz kaydı, otomatik cihaz kaydı (denetimli)

- **Kısıtlanmış uygulamalar listesi türü**: Kullanıcıların yüklemesine veya kullanmasına izin verilmeyen uygulamaların bir listesini oluşturun. Seçenekleriniz şunlardır:

  - **Yapılandırılmadı** (varsayılan): Intune 'dan bir kısıtlama yoktur. Kullanıcıların atadığınız uygulamalara ve yerleşik uygulamalarına erişimi vardır.
  - **Yasak uygulamalar**: Intune tarafından yönetilmeyen ve cihaza yüklenmesini istemediğiniz uygulamalar. Kullanıcıların yasaklanmış bir uygulamayı yüklemesi engellenmiyor. Ancak bir Kullanıcı bu listeden bir uygulama yüklerse Intune 'da raporlanır.
  - **Onaylı uygulamalar**: Kullanıcıların yüklemesine izin verilen uygulamalar. Kullanıcılar listelenmeyen uygulamaları yüklememelidir. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir. Kullanıcıların onaylı uygulamalar listesinde olmayan bir uygulamayı yüklenmesi engellenmez. Ancak bunu yaptıysanız Intune 'da raporlanır.

Bu listelere uygulama eklemek için şunları yapabilirsiniz:

- İstediğiniz uygulamanın iTunes App mağazası URL'sini **ekleyin**. Örneğin, Microsoft çalışma klasörleri uygulamasını eklemek için veya `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`girin.

  Uygulamanın URL'sini bulmak için, iTunes App Store'u açın ve uygulamayı arayın. Örneğin `Microsoft Remote Desktop` veya `Microsoft Word` için arama yapın. Uygulamayı seçin ve URL'sini kopyalayın.

  iTunes kullanarak da uygulamayı bulabilir ve ardından **Bağlantıyı Kopyala** görevini kullanıp uygulama URL’sini alabilirsiniz.

- URL 'SI dahil olmak üzere uygulamayla ilgili ayrıntılarla bir CSV dosyasını **Içeri aktarın** . `<app url>, <app name>, <app publisher>` biçimini kullanın. Veya, kısıtlanmış uygulamalar listesini içeren mevcut bir listeyi aynı biçimde **dışarı aktarın** .

> [!IMPORTANT]
> Kısıtlı uygulama ayarlarını kullanan cihaz profilleri kullanıcı gruplarına atanmalıdır.

## <a name="show-or-hide-apps"></a>Uygulamaları gösterme veya gizleme

İOS 9,3 veya üstünü çalıştıran cihazlar için geçerlidir.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Otomatik cihaz kaydı (denetimli)

- **Uygulama listesi türü**: Gösterilecek veya gizlenecek uygulamaların bir listesini oluşturun. Seçenekleriniz şunlardır:

  - **Gizli uygulamalar**: Kullanıcılardan gizlenecek uygulamaların listesini girin. Kullanıcılar bu uygulamaları görüntüleyemez veya açamaz.
  - **Görünür uygulamalar**: Kullanıcıların görüntüleyebileceği ve başlatabileceği uygulamaların listesini girin. Başka hiçbir uygulama görüntülenemez veya başlatılamaz.

- **Uygulama URL 'si**: Göstermek veya gizlemek istediğiniz uygulamanın Mağaza uygulama URL 'sini girin. Örneğin:

  - Microsoft çalışma klasörleri uygulamasını eklemek için veya `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`girin. 

  - Microsoft Word uygulamasını eklemek için veya `https://itunes.apple.com/de/app/microsoft-word/id586447913` `https://apps.apple.com/de/app/microsoft-word/id586447913`girin.

  Uygulamanın URL'sini bulmak için, iTunes App Store'u açın ve uygulamayı arayın. Örneğin `Microsoft Remote Desktop` veya `Microsoft Word` için arama yapın. Uygulamayı seçin ve URL'sini kopyalayın.

  iTunes kullanarak da uygulamayı bulabilir ve ardından **Bağlantıyı Kopyala** görevini kullanıp uygulama URL’sini alabilirsiniz.
  
  Paket KIMLIĞINI bulma hakkında daha fazla bilgi için bkz. [iOS uygulaması için paket kimliğini bulma](https://support.microsoft.com/help/4294074/how-to-find-the-bundle-id-for-an-ios-app).

- **Uygulama Paketi Kimliği**: İstediğiniz uygulamanın uygulama [paket kimliğini](bundle-ids-built-in-ios-apps.md) girin. Yerleşik uygulamaları ve iş kolu uygulamalarını gösterebilir veya gizleyebilirsiniz. Apple 'ın Web sitesinde [yerleşik bir Apple Apps](https://support.apple.com/HT208094)listesi bulunur.
- **Uygulama adı**: İstediğiniz uygulamanın uygulama adını girin. Yerleşik uygulamaları ve iş kolu uygulamalarını gösterebilir veya gizleyebilirsiniz. Apple 'ın Web sitesinde [yerleşik bir Apple Apps](https://support.apple.com/HT208094)listesi bulunur.
- **Yayımcı**: İstediğiniz uygulamanın yayımcısını girin.

Uygulamaları eklemek için şunları yapabilirsiniz:

- **Ekle**: Uygulama listenizi oluşturmak için seçin.
- URL 'SI dahil olmak üzere uygulamayla ilgili ayrıntılarla bir CSV dosyasını **Içeri aktarın** . `<app url>, <app name>, <app publisher>` biçimini kullanın. Ya da, aynı biçimde eklediğiniz kısıtlı uygulamaların bir listesini oluşturmak için **dışa aktarın** .

## <a name="wireless"></a>Kablosuz

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Cihaz kaydı, otomatik cihaz kaydı (denetimli)

- **Veri dolaşımı**: Cep telefonu şebekesi üzerinden veri dolaşımını önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı cihaz cep telefonu şebekesindeyken veri dolaşımına izin verir.
- **Dolaşım sırasında genel arka planda alma**: **Engelle** ayarı cep telefonu şebekesi üzerinde dolaşım sırasında genel arka planda alma özelliğinin kullanılmasını önler. **Yapılandırılmadı** ayarı cihazın cep telefonu şebekesi üzerinde dolaşımdayken e-posta gibi verileri almasına izin verir.
- **Sesli arama**: Kullanıcıların cihazda sesli arama özelliğini kullanmasını önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı cihazda sesli aramaya izin verir.
- **Ses dolaşımı**: Cep telefonu şebekesi üzerinden ses dolaşımını önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı cihaz cep telefonu şebekesindeyken ses dolaşımına izin verir.
- **Kişisel Etkin Nokta**: **Engelle** ayarı her cihaz eşitlemesinde kullanıcıların cihazındaki kişisel etkin noktayı kapatır. Bu ayar, bazı operatörler ile uyumlu olmayabilir. **Yapılandırılmadı** (varsayılan) ayarı kişisel etkin nokta yapılandırmasını kullanıcı tarafından ayarlanmış varsayılan değerinde bırakır.
- **Hücresel kullanım kuralları (yalnızca yönetilen uygulamalar)** : Hücresel ağa bağlıyken yönetilen uygulamaların kullanabileceği veri türlerini tanımlayın. Seçenekleriniz şunlardır:
  - **Hücresel veri kullanımını engelle**: **Tüm yönetilen uygulamalar** için hücresel veri kullanımını engelleyin veya **Belirli uygulamaları seçin**.
  - **Dolaşımdayken hücresel veri kullanımını engelle**: Dolaşım sırasında **Tüm yönetilen uygulamalar** için hücresel veri kullanımını engelleyin veya **Belirli uygulamaları seçin**.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Otomatik cihaz kaydı (denetimli)

- **Uygulama hücresel veri kullanım ayarlarında yapılan değişiklikler**: Uygulama hücresel veri kullanımı ayarlarının değiştirilmesini önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının hangi uygulamaların hücresel veri kullanabileceğini denetlemesine izin verir.
- **Hücresel plan ayarlarındaki değişiklikler**: **Engelle** ayarı kullanıcıların hücresel plandaki ayarları değiştirmesini önler. **Yapılandırılmadı** (varsayılan) ayarı kullanıcıların değişiklik yapmasına izin verir.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11,0 ve üzeri

- **Kişisel etkin noktanın Kullanıcı değişikliği**: **Blok**olarak ayarlandığında, Kullanıcı kişisel etkin nokta ayarını değiştiremez. **Yapılandırılmadı** (varsayılan) son kullanıcıların kendi kişisel etkin kullanımlarını etkinleştirmesine veya devre dışı bırakmasına izin verir.

  Bu ayarı engellerseniz ve **Kişisel etkin nokta** ayarını engellerseniz kişisel etkin nokta kapalıdır.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 12,2 ve üzeri

- **Yalnızca yapılandırma profillerini kullanarak Wi-Fi ağlarına katılarak**: **Gerekli** ayarı cihazın yalnızca Intune yapılandırma profilleri aracılığıyla ayarlanan Wi-Fi ağlarını kullanmasını zorunlu tutar. **Yapılandırılmadı** (varsayılan) ayarı cihazın diğer Wi-Fi ağlarını kullanmasına izin verir.
- **Wi-Fi durumu değişikliği**: **Yapılandırılmadı** (varsayılan) kullanıcıların cihazda Wi-Fi açmasına veya kapatmasına izin verir. **Blok** , Wi-Fi ' ı etkinleştirmeyi veya kapatmayı engeller.

## <a name="connected-devices"></a>Bağlı Cihazlar

### <a name="settings-apply-to-all-enrollment-types"></a>Ayarlar için geçerlidir: Tüm kayıt türleri

- **Eşleştirilen Apple Watch için bilek algılama**: **Gerekli** ayarı eşleştirilmiş Apple Watch'un bilek algılama kullanmasını zorunlu tutar. Gerekli seçilirse, Apple Watch takılmadığında bildirim görüntülemez. 

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Cihaz kaydı, otomatik cihaz kaydı (denetimli)

- **Giden AirPlay istekleri için eşleştirme parolası isteme**: **Gerekli** ayarı kullanıcının diğer Apple cihazlarına içerik akışı sağlamak üzere AirPlay’i kullanması için, eşleştirilen parola gerektirir. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının parola girmeden AirPlay kullanarak içerik akışı yapmasına izin verir.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Otomatik cihaz kaydı (denetimli)

- **AirDrop**: **Engelle** ayarı cihazdaki AirDrop özelliğinin kullanılmasını engeller. **Yapılandırılmadı** (varsayılan) ayarı yakındaki cihazlarla içerik değişimi için AirDrop özelliğinin kullanılmasına izin verir.
- **Apple Watch eşleştirme**: **Engelle** ayarı Apple Watch ile eşleştirmeyi önler. **Yapılandırılmadı** (varsayılan) ayarı cihazın Apple Watch ile eşleştirilmesine izin verir.
- **Bluetooth değişikliği**: **Engelle** ayarı son kullanıcının cihazda Bluetooth ayarlarını değiştirmesini durdurur. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının bu ayarları değiştirmesine izin verir.
- **İOS cihazının eşleştirilebileceği cihazları denetlemek Için konak eşleştirme**: **Yapılandırılmadı** (varsayılan) ayarı yöneticinin bir iOS cihazının hangi cihazlarla eşleşebileceğini denetleyebilmesi için konak eşleştirmeye izin verir. **Engelle** ayarı konak eşleştirmeyi önler.
- **AirPrint 'ı engelle**: Cihazda AirPrint özelliğinin kullanılmasını önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının AirPrint'i kullanmasına izin verir.
  - **Anahtarlıkta AirPrint kimlik bilgilerinin depolanmasını engelleyin**: **Engelle** ayarı cihazda kullanıcı adı ve parola için Anahtar Zinciri depolama alanının kullanılmasını önler. **Yapılandırılmadı** (varsayılan) ayarı AirPrint kullanıcı adı ve parolasının Anahtar Zinciri uygulamasında depolanmasına izin verir.
  - **AirPrint için güvenilir BIR TLS sertifikası gerektir**: **Gerekli** ayarı cihazın TLS yazdırma iletişimi için güvenilir sertifikalar kullanmasını zorunlu tutar.
  - **AirPrint yazıcılarının ıişaret bulmayı engelle**: **Engelle** ayarı kötü amaçlı AirPrint Bluetooth işaretlerinin ağ trafiği için kimlik avı yapmasını engeller. **Yapılandırılmadı** (varsayılan) ayarı cihazda AirPrint yazıcılarının tanıtılmasına izin verir.
- **Yeni yakındaki cihazları ayarlamayı engelle**: **Engelle** , yakında bulunan yeni cihazları ayarlamaya yönelik istemi devre dışı bırakır. **Yapılandırılmadı** (varsayılan) ayarı yakındaki diğer Apple cihazlarıyla bağlantı kurulup kurulmayacağının kullanıcıya sorulmasına izin verir.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11,0 ve üzeri

## <a name="keyboard-and-dictionary"></a>Klavye ve Sözlük

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Otomatik cihaz kaydı (denetimli)

- **Sözcük tanımı arama**: **Engelle** ayarı kullanıcının belirli bir sözcüğü vurgulayıp cihazda tanımını aramasını engeller. **Yapılandırılmadı** (varsayılan) ayarı, tanım arama özelliğine erişim sağlar.
- Tahmine **dayalı klavyeler**: **Yapılandırılmadı** (varsayılan), tahmine dayalı klavyeleri kullanarak kullanıcının istedikleri sözcükleri önermesini sağlar. **Engelle** ayarı bu özelliği önler.
- **Otomatik Düzeltme**: **Yapılandırılmadı** (varsayılan) cihazın yanlış yazılan sözcükleri otomatik olarak düzeltmesini sağlar. **Engelle** ayarı otomatik düzeltme kullanılmasını önler.
- **Klavye yazım denetimi**: **Yapılandırılmadı** (varsayılan) cihazda SpellChecker kullanılmasına izin verir. **Engelle** ayarı yazım denetleyicisine izin verir.
- **Klavye kısayolları**: **Yapılandırılmadı** (varsayılan) cihazda klavye kısayollarının kullanılmasına izin verir. **Engelle** ayarı kullanıcının klavye kısayollarını kullanmasını durdurur.
- **Dikte**: **Engelle** ayarı kullanıcının metin girmek için sesli giriş kullanmasını durdurur. **Yapılandırılmadı** (varsayılan) ayarı, kullanıcının dikteyle girişi kullanmasına izin verir.
- **Hızlı yol**: **Yapılandırılmadı** (varsayılan), kullanıcıların, cihazın klavyesinde sürekli bir giriş sağlayan hızlı yol kullanmasına izin verir. Kullanıcılar, sözcükler oluşturmak için anahtarlar arasında çekerek yazı yazabilir. **Block** , kullanıcıların hızlı yol kullanmasını engeller. 

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 13,0 ve ıpados 13,0 ve üzeri

## <a name="cloud-and-storage"></a>Bulut ve Depolama

### <a name="settings-apply-to-all-enrollment-types"></a>Ayarlar için geçerlidir: Tüm kayıt türleri

- **Şifreli yedekleme**: Tüm cihaz yedeklemelerinin şifrelenmesini **gerektirir**.
- **Yönetilen uygulamaları bulutla eşitleme**: **Yapılandırılmadı** (varsayılan), Intune 'a, uygulamaların kullanıcının iCloud hesabıyla veri eşitlemesine olanak tanır. **Engelle** ayarı iCloud'a bu veri eşitlemesini engeller.
- **Kurumsal Defter Yedeklemesini Engelle**: Kullanıcıların kurumsal defterleri yedeklemesini önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan), kullanıcıların bu kitapları yedeklemesini sağlar.
- **Kurumsal defter meta veri eşitlemesini (notlar ve vurgular) engelle**: **Engelle** ayarı kurumsal defterlerdeki notların ve vurguların eşitlenmesini önler. **Yapılandırılmadı** (varsayılan) eşitlemeye izin verir.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Cihaz kaydı, otomatik cihaz kaydı (denetimli)

- **iCloud'a fotoğraf akışı eşitlemesi**: **Yapılandırılmadı** (varsayılan), kullanıcıların, **Cihazlarım için cihazımın akışını** etkinleştirmesine ve tüm kullanıcıların cihazlarında fotoğraflar kullanmalarına olanak sağlar. **Engelle** ayarı iCloud'a fotoğraf akışının eşitlenmesini önler. Bu özelliğin engellenmesi veri kaybına neden olabilir. 
- **iCloud Fotoğraf Arşivi**: Fotoğrafları ve videoları bulutta depolamak üzere iCloud fotoğraf arşivinin kullanılmasını devre dışı bırakmak için **Engelle** olarak ayarlayın. iCloud Fotoğraf Arşivi'nden cihaza tamamen indirilmeyen tüm fotoğraflar cihazdan kaldırılır. **Yapılandırılmadı** (varsayılan) iCloud Fotoğraf kitaplığının kullanılmasına izin verir.
- **Paylaşılan fotoğraf akışı**: Cihazda **iCloud Fotoğraf Paylaşımı**’nı devre dışı bırakmak için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan), paylaşılan fotoğraf akışına izin verir.
- **İletim**: **Yapılandırılmadı** (varsayılan), kullanıcıların bir iOS cihazında çalışmaya başlamasını sağlar ve sonra başka bir iOS veya macOS cihazında başlatıldıklarında çalışmaya devam eder. **Engelle** ayarı bu iletimi önler.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Otomatik cihaz kaydı (denetimli)

- **iCloud'a yedekle**: **Yapılandırılmadı** (varsayılan) kullanıcının cihazı iCloud 'a yedeklemesine izin verir. **Engelle** ayarı kullanıcının cihazı iCloud'a yedeklemesini durdurur.

  İOS 13,0 ' den itibaren, bu ayar denetimli cihazlar gerektirir.

- **ICloud belge eşitlemesini engelle**: **Yapılandırılmadı** (varsayılan), iCloud depolama alanınızda belge ve anahtar-değer eşitlemesine izin verir. **Engelle** ayarı iCloud'ın belgeleri ve verileri eşitlemesini engeller.

  İOS 13,0 ' den itibaren, bu ayar denetimli cihazlar gerektirir.

- **iCloud Anahtar Zinciri eşitlemesini engelle**: **Engelle**'yi seçtiğinizde Anahtar Zincirinde depolanan kimlik bilgilerinin iCloud ile eşitlenmesi devre dışı bırakılır. **Yapılandırılmadı** (varsayılan), kullanıcıların bu kimlik bilgilerini eşitlemesine izin verir.

  İOS 13,0 ' den itibaren, bu ayar denetimli cihazlar gerektirir.

## <a name="autonomous-single-app-mode"></a>Otonom tek uygulama modu

Bu ayarları kullanarak iOS cihazlarını, belirli uygulamaları otonom tek uygulama modunda çalışacak şekilde yapılandırabilirsiniz. Bu mod yapılandırılıp uygulama çalıştırıldığında cihaz kilitlenir. Yalnızca söz konusu uygulamayı çalıştırabilir. Örneğin, kullanıcıların cihazda bir test yapmasına olanak tanıyan bir uygulama ekleyin. Uygulama eylemleri tamamlandığında veya bu ilkeyi kaldırdığınızda cihaz normal durumuna döner.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Otomatik cihaz kaydı (denetimli)

- **Uygulama adı**: İstediğiniz uygulamanın adını girin.
- **Uygulama Paketi Kimliği**: İstediğiniz uygulamanın [paket kimliğini](bundle-ids-built-in-ios-apps.md) girin.
- **Ekle**: Uygulama listenizi oluşturmak için seçin.

Ayrıca, uygulama adlarının ve paket kimliklerinin listesini içeren bir CSV dosyasını **Içeri aktarabilirsiniz** . Alternatif olarak uygulamaları içeren mevcut listeyi **dışarı aktarabilirsiniz**.

## <a name="kiosk"></a>Bilgi noktası

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Otomatik cihaz kaydı (denetimli)

- **Bilgi noktası modunda çalıştırılacak uygulama**: Bilgi noktası modunda çalıştırmak istediğiniz uygulama türünü seçin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): Bilgi noktası ayarları uygulanmaz. Cihaz bilgi noktası modunda çalışmıyor.
  - **Mağaza Uygulaması**: iTunes App mağazasındaki uygulamanın URL'sini girin.
  - **Yönetilen Uygulama**: Intune'a eklediğiniz bir uygulamayı seçin.
  - **Yerleşik Uygulama**: Yerleşik uygulamanın [paket kimliğini](bundle-ids-built-in-ios-apps.md) girin.

- **Yardımlı dokunma**: **Gerekli**'yi seçerek cihazda Yardımlı Dokunma erişilebilirlik ayarını zorunlu tutun. Bu özellik kullanıcılara zorlanabilecekleri ekran hareketlerinde yardımcı olur. **Yapılandırılmadı** ayarı bilgi noktası modunda bu özelliği çalıştırmaz veya etkinleştirmez.
- **Renkleri ters çevir**: **Gerekli**'yi seçerek görme bozukluğu olan kullanıcıların ekran görüntüsünü değiştirebilmesi için Renkleri ters çevir erişilebilirlik ayarını zorunlu tutun. **Yapılandırılmadı** ayarı bilgi noktası modunda bu özelliği çalıştırmaz veya etkinleştirmez.
- **Mono ses**: **Gerekli**'yi seçerek cihazda Mono ses erişilebilirlik ayarını zorunlu tutun. **Yapılandırılmadı** ayarı bilgi noktası modunda bu özelliği çalıştırmaz veya etkinleştirmez.
- **Ses denetimi**: **Gerektir** , cihazda ses denetimi sağlar ve kullanıcıların Siri komutlarını kullanarak işletim sistemini tam olarak denetlemesine olanak tanır. **Yapılandırılmadı** , cihazda ses denetimini devre dışı bırakır.

  Bu ayarın geçerli olduğu sürümler:  
  - iOS 13,0 ve üzeri
  - ıpados 13,0 ve üzeri
  
  > [!TIP]
  > Kuruluşunuz için kullanılabilir LOB uygulamalarınız varsa ve iOS 13,0 yayımları olduğunda gün 0 ' da hazır bir **ses denetimi** yoksa, bu ayarı **yapılandırılmamış**olarak bırakmanız önerilir.

- **VoiceOver**: **Gerekli**'yi seçerek ekrandaki metnin yüksek sesle okunmasını sağlamak için VoiceOver erişilebilirlik ayarını zorunlu tutun. **Yapılandırılmadı** ayarı bilgi noktası modunda bu özelliği çalıştırmaz veya etkinleştirmez.
- **Yakınlaştır**: **Gerekli**'yi seçerek kullanıcıların ekranda yakınlaştırmak için dokunma özelliğini kullanabilmesi için Yakınlaştır ayarını zorunlu tutun. **Yapılandırılmadı** ayarı bilgi noktası modunda bu özelliği çalıştırmaz veya etkinleştirmez.
- **Otomatik kilit**: **Blok** , cihazın otomatik olarak kilitlenmesini engeller. **Yapılandırılmadı** , bu özelliğe izin verir.
- **Zil düğmesi**: **Blok** , cihazdaki zil (sessiz) geçişi devre dışı bırakır. **Yapılandırılmadı** , bu özelliğe izin verir.
- **Ekran döndürme**: **Blok** , Kullanıcı cihazı döndürdüğünde ekran yönünün değiştirilmesini önler. **Yapılandırılmadı** , bu özelliğe izin verir.
- **Ekran uyku düğmesi**: Cihazda ekran uyku modundan çıkarma düğmesini devre dışı bırakmak için **Engelle** ' yi seçin. **Yapılandırılmadı** , bu özelliğe izin verir.
- **Dokunmatik**: **Engelle** ayarı cihazda dokunmatik ekranı devre dışı bırakır. **Yapılandırılmadı** ayarı kullanıcının dokunmatik ekranı kullanmasına izin verir.
- **Ses düğmeleri**: **Blok** , cihazdaki ses düğmelerinin kullanımını engeller. **Yapılandırılmadı** , ses düğmelerine izin verir.
- **Yardımcı dokunma denetimi**: **İzin Ver** ayarı kullanıcıların yardımcı dokunma işlevini kullanmasına olanak tanır. **Yapılandırılmadı** ayarı bu özelliği devre dışı bırakır.
- **Renkleri ters çevirme denetimi**: Kullanıcıların renkleri tersine çevirme denetimini ayarlamasına olanak sağlamak için renkleri tersine çevirme değişikliklerine **izin verin**. **Yapılandırılmadı** ayarı bu özelliği devre dışı bırakır.
- **Seçilen metinde konuşma**: Cihazda Konuşma Seçimi erişilebilirlik ayarlarının bulunmasına **izin verin**. Bu özellik kullanıcının seçtiği metni yüksek sesle okur. **Yapılandırılmadı** ayarı bu özelliği devre dışı bırakır.
- **Ses denetimi değişikliği**: Kullanıcıların, cihazlarındaki ses denetimi durumunu değiştirmesine **Izin verin** . **Yapılandırılmadı** , kullanıcıların cihazlarındaki ses denetimi durumunu değiştirmesini engeller.

  Bu ayarın geçerli olduğu sürümler:  
  - iOS 13,0 ve üzeri
  - ıpados 13,0 ve üzeri

- **VoiceOver denetimi**: Kullanıcıların VoiceOver işlevini güncelleştirmesine, örneğin ekran metninin okunma hızını ayarlamasına olanak sağlamak için VoiceOver değişikliklerine **izin verin**. **Yapılandırılmadı** ayarı VoiceOver değişikliklerini engeller.
- **Yakınlaştırma denetimi**: Kullanıcını yakınlaştırmayı değiştirmesine **izin verin**. **Yapılandırılmadı** ayarı yakınlaştırma değişikliklerini engeller.

> [!NOTE]
> Bir iOS cihazını bilgi noktası modunda yapılandırabilmek için, önce Apple Configurator aracını veya Apple Cihaz Kayıt Programı’nı kullanarak cihazı denetimli moda almanız gerekir. Apple Configurator aracını kullanma konusunda Apple'ın kılavuzuna bakın.
> Girdiğiniz iOS uygulaması siz profil atadıktan sonra yüklendiyse, cihaz yeniden başlatılana kadar bilgi noktası moduna girmez.

## <a name="domains"></a>Etki Alanları

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Cihaz kaydı, otomatik cihaz kaydı (denetimli)

- **İşaretlenmemiş e-posta etki alanları** > **E-posta Etki Alanı URL'si**: Listeye bir veya daha fazla URL ekleyin. Son kullanıcılar, girdiğiniz etki alanları dışındaki bir etki alanından e-posta aldığında bu e-posta iOS Mail uygulamasında güvenilmeyen olarak işaretlenir.

- **Yönetilen web etki alanları** > **Web Etki Alanı URL'si**; Listeye bir veya daha fazla URL ekleyin. Belgeler girdiğiniz etki alanlarından indirildiğinde yönetilen belgeler olarak değerlendirilir. Bu ayar yalnızca Safari tarayıcısı kullanılarak indirilen belgeler için geçerlidir.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: Otomatik cihaz kaydı (denetimli)

- **Safari parola otomatik doldurma etki alanları** > **Etki Alanı URL'si**: Listeye bir veya daha fazla URL ekleyin. Kullanıcılar yalnızca bu listedeki URL’lerdeki parolaları kaydedebilir. Bu ayar yalnızca Safari tarayıcısı ve denetimli moddaki cihazlar için geçerlidir. Herhangi bir URL girmezseniz, parolalar tüm Web sitelerinden kaydedilebilir.

  Bu ayarın geçerli olduğu sürümler:  
  - iOS 9,3 ve üzeri

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
>
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
