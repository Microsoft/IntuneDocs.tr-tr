---
title: Microsoft Intune-Azure 'da iOS/ıpados cihaz ayarları | Microsoft Docs
titleSuffix: ''
description: İOS/ıpados cihazlarında ayarlar ekleme, yapılandırma veya oluşturma; parola gereksinimlerini ayarlama, kilitli ekranı denetleme, yerleşik uygulamalar kullanma, kısıtlı veya onaylanan uygulamalar ekleme, Bluetooth cihazlarını işleme, yedekleme ve depolama için buluta bağlanma, bilgi noktası modunu etkinleştirme, etki alanı ekleme ve kullanıcıların Microsoft Intune ' de Safari web tarayıcısıyla nasıl etkileşime gireceğini denetleme.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 86bb9edf96911379631068925315959468f65872
ms.sourcegitcommit: fab685b22a010fe231b27a0c5eda34a6f22f4c8d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2020
ms.locfileid: "78216023"
---
# <a name="ios-and-ipados-device-settings-to-allow-or-restrict-features-using-intune"></a>Intune kullanarak özelliklere izin vermek veya erişimi kısıtlamak için iOS ve ıpados cihaz ayarları

Bu makalede iOS ve ıpados cihazlarında denetleyebileceğinizi belirten farklı ayarlar listelenir. Mobil cihaz yönetimi (MDM) yönteminizin bir parçası olarak bu ayarları kullanabilir ve bu sayede özellikleri etkinleştirip devre dışı bırakabilir, parola kuralları uygulayabilir, belirli uygulamalara izin verebilir veya bunları kısıtlayabilir ve çok daha fazlasını yapabilirsiniz.

Bu ayarlar, Intune 'da bir cihaz yapılandırma profiline eklenir ve sonra iOS/ıpados cihazlarınıza atanır veya dağıtılır.

> [!TIP]
> Bu ayarlar Apple MDM ayarlarını kullanır. Bu ayarlar hakkında daha fazla bilgi için bkz. [Apple 'ın mobil cihaz yönetimi ayarları](https://support.apple.com/guide/mdm/welcome/web) (Apple 'ın Web sitesini açar).

## <a name="before-you-begin"></a>Başlamadan önce

[Cihaz kısıtlamaları yapılandırma profili oluşturma](../device-restrictions-configure.md).

> [!NOTE]
> Bu ayarlar, bazı ayarların tüm kayıt seçeneklerine uygulanmasıyla farklı kayıt türleri için geçerlidir. Farklı kayıt türleri hakkında daha fazla bilgi için bkz. [iOS/ıpados kaydı](../ios-enroll.md).

## <a name="general"></a>Genel

### <a name="settings-apply-to-all-enrollment-types"></a>Ayarlar için geçerlidir: tüm kayıt türleri

- **Kullanım verilerini paylaşma**: cihazın Apple 'a tanılama ve kullanım verileri göndermesini engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan) ayarı bu verilerin gönderilmesine izin verir.

- **Ekran yakalama**: cihazda ekran görüntülerini veya ekran yakalamalarını engellemek için **Engelle** ' yi seçin. İOS/ıpados 9,0 ve üzeri sürümlerde, ekran kayıtlarını da engeller. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının ekran içeriğini bir resim veya video olarak yakalamasına olanak tanır.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: cihaz kaydı, otomatik cihaz kaydı (denetimli)

- **GÜVENILMEYEN TLS sertifikaları**: cihazda güvenilmeyen aktarım katmanı GÜVENLIĞI (TLS) sertifikalarını engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan) ayarı TLS sertifikalarına izin verir.
- **Kablosuz PKI güncelleştirmelerini engelle**: **blok** , cihazın bir bilgisayara bağlı olmadığı durumlar dışında yazılım güncelleştirmelerini almasını engeller. **Yapılandırılmadı** (varsayılan): bir cihazın bir bilgisayara bağlı olmadan yazılım güncelleştirmelerini almasına izin verir.
- **Ad Izlemeyi sınırla**: cihaz reklam tanımlayıcısını devre dışı bırakmak için **sınır** ' ı seçin. **Yapılandırılmadı** (varsayılan) bu tanımlayıcının etkin kalmasını sağlar.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: otomatik cihaz kaydı (denetimli)

- **Tanılama gönderme ayarları değişikliği**: **blok** , kullanıcının **Tanılama ve kullanım** (cihaz ayarları) içindeki tanılama gönderme ve uygulama analizi ayarlarını değiştirmesini engeller. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının bu cihaz ayarlarını değiştirmesine izin verir.

  Bu ayarı kullanmak için, **kullanım verilerini paylaşma** ayarını **Engelle**olarak ayarlayın.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 9.3.2 ve üzeri
  - ıpados 13,0 ve üzeri

- **Sınıf uygulamasına göre uzak ekran gözlemlemesi**: sınıf uygulamasının cihazda ekranı uzaktan görüntülemesini engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan) ayarı Apple Classroom uygulamasının ekranı görüntülemesine izin verir.

  Bu ayarı kullanmak için **ekran yakalama** ayarını **Engelle**olarak ayarlayın.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 9,3 ve üzeri
  - ıpados 13,0 ve üzeri

- **Sınıf uygulamasına göre istem dışı ekran izleme**: **izin ver**olarak ayarlanırsa, öğretmenler, öğrenciler hakkında bilgi sahibi olmadan ders uygulamasını kullanan iOS/ıpados cihazlarının ekranını sessizce gözlemleyebilirsiniz. Classroom uygulaması kullanılarak sınıfa kaydedilmiş olan öğrenci cihazları, söz konusu dersin öğretmenine otomatik olarak izin verir. **Yapılandırılmadı** (varsayılan) ayarı bu özelliği engeller.

  Bu ayarı kullanmak için **ekran yakalama** ayarını **Engelle**olarak ayarlayın.

- **Kurumsal Uygulama güveni**: Ayarlar > Genel > profilleri cihaz & cihaz yönetimi ' nde **Kurumsal Geliştirici güveni** Kaldır düğmesini kaldırmak için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının uygulama mağazasından indirilmemiş uygulamalara güvenmeyi seçmesine olanak tanır.
- **Hesap değişikliği**: **blok**olarak ayarlandığında, Kullanıcı iOS/ıpados ayarları uygulamasından cihaza özgü ayarları güncelleştiremez. Örneğin kullanıcı yeni cihaz hesapları oluşturamaz ya da kullanıcı adını veya parolasını değiştiremez. **Yapılandırılmadı** (varsayılan) ayarı kullanıcıların bu ayarları değiştirmesine izin verir.

  Bu özellik ayrıca, e-posta, kişiler, takvim, Twitter ve daha fazlası gibi iOS/ıpados ayarları uygulamasından erişilebilen ayarlar için de geçerlidir. Bu özellik, Microsoft Outlook uygulaması gibi iOS/ıpados ayarları uygulamasından yapılandırılamayan hesap ayarlarına sahip uygulamalar için geçerlidir.

- **Ekran zamanı**: kullanıcıların ekran zamanında (cihaz ayarları) kendi kısıtlamalarını ayarlamalarını engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** kullanıcının cihazda cihaz kısıtlamalarını (ebeveyn denetimleri veya içerik ve gizlilik kısıtlamaları gibi) yapılandırmasına izin verir.

  Bu ayar **Cihaz ayarlarında kısıtlamaları etkinleştirme** ayarının yeniden adlandırılmış halidir. Bu değişikliğin etkisi:  
  
  - iOS 11.4.1 ve üzeri: **blok** , son kullanıcıların cihaz ayarlarında kendi kısıtlamalarını değiştirmesini engeller. Davranış aynıdır; ve son kullanıcılar için herhangi bir değişiklik yoktur.
  - iOS 12,0 ve üzeri: **blok** , son kullanıcıların, içerik ve gizlilik kısıtlamaları da dahil olmak üzere cihaz ayarları 'Nda (Ayarlar > Genel > ekran süresi) kendi **ekran süresini** değiştirmesini engeller. iOS 12.0'dan yükseltilen cihazlar artık cihaz ayarlarında kısıtlamalar sekmesini (Ayarlar > Genel > Cihaz Yönetimi > Yönetim Profili > Kısıtlamalar) görmez. Bu ayarlar **Ekran Saati** altındadır.
  
- **Cihazdaki tüm içeriği ve ayarları Sil seçeneğinin kullanımı**: **Engelle** ' yi seçin, böylece kullanıcılar cihazdaki tüm içeriği ve ayarları silme seçeneğini kullanamaz. **Yapılandırılmadı** (varsayılan) ayarı kullanıcılara bu ayarlar için erişim verir.
- **Cihaz adı değişikliği**: cihaz adının değiştirilebilmesi için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının cihaz adını değiştirmesine izin verir.
- **Bildirim ayarlarının değiştirilmesi**: bildirim ayarlarının değiştirilenemez şekilde **blok** seçin. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının cihaz bildirim ayarlarını değiştirmesine izin verir.
- **Duvar kağıdı değişikliği**: **blok** duvar kağıdının değiştirilmesini önler. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının cihazda duvar kağıdını değiştirmesine izin verir.
- **Kurumsal uygulama güven ayarları değişikliği**: **blok** , kullanıcının denetimli cihazlarda kurumsal uygulama güven ayarlarını değiştirmesini engeller. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının uygulama mağazasından indirilmemiş uygulamalara güvenmesine izin verir.
- **Yapılandırma profili değişiklikleri**: **blok** , cihazdaki yapılandırma profili değişikliklerini engeller. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının yapılandırma profillerini yüklemesine izin verir.
- **Etkinleştirme Kilidi**: denetimli IOS/ıpados cihazlarında Etkinleştirme Kilidi etkinleştirmek Için **izin ver** ' i seçin. Etkinleştirme Kilidi, kaybolan veya çalınan bir cihazın yeniden etkinleştirilmesini zorlaştırır.
- **Uygulama kaldırmayı engelle**: kullanıcıların uygulamaları kaldırmasını engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan) ayarı kullanıcıların cihazdan uygulama kaldırmasına izin verir.
- **Cihaz KILITLIYKEN USB donatılara Izin ver**: **ızın ver** , USB aksesuarları 'nin bir saatten daha fazla kilitlenmiş bir cihazla veri alışverişi yapmasına olanak sağlar. **Yapılandırılmamış** (varsayılan), USB kısıtlı modunu cihazda güncelleştirmez ve USB aksesuarları bir saatten daha fazla kilitleniyorsa cihazdan veri aktarımını engellenecektir.
- **Otomatik tarih ve saati zorla**: **gerekli** cihazların otomatik olarak tarih & zamanını ayarlamaya zorlar. Cihazın hücresel bağlantıları olduğunda veya konum hizmetleriyle arasında Wi-Fi etkinleştirildiğinde saat dilimi güncelleştirilir.
- **Öğrencilerden** **ayrılmaları için** öğrencilerin ders uygulamasını kullanarak yönetilmeyen bir kursa kaydolmaya izin istemesini gerektir: **Yapılandırılmadı** (varsayılan) ayarı öğrencinin izin istemesini zorunlu tutmaz.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11,3 ve üzeri
  - ıpados 13,0 ve üzeri

- **Sınıfa sormadan bir uygulamayı kilitlemesine ve cihazı kilitlemesine Izin ver**: **Enable** , öğretmenin uygulamaları kilitlemesine veya öğrenciye sormadan ders uygulamasını kullanarak cihazı kilitlemesine olanak tanır. Uygulamaların kilitlenmesi cihazın yalnızca öğretmenin belirttiği uygulamalara erişebileceği anlamına gelir. **Yapılandırılmadı** (varsayılan) ayarı öğretmenlerin öğrenciye sormadan Classroom uygulamasını kullanarak uygulamaları veya cihazları kilitlemesini önler.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11,0 ve üzeri
  - ıpados 13,0 ve üzeri

- **Sınıf sınıflarını sorulmadan otomatik olarak birleştir**: **Etkinleştir** otomatik olarak, öğrencilerin öğretme istenmeden ders uygulamasındaki bir sınıfa katılmasına izin verir. **Yapılandırılmadı** (varsayılan) ayarı öğrencilerin Classroom uygulamasındaki derse katılma isteğini öğretmene sorar.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11,0 ve üzeri
  - ıpados 13,0 ve üzeri

- **VPN oluşturmayı engelle**: **blok** , kullanıcıların VPN yapılandırma ayarları oluşturmasını engeller. **Yapılandırılmadı** (varsayılan) ayarı kullanıcıların cihazda VPN'ler oluşturmasına olanak tanır.
- **Esım ayarlarını değiştirme**: **Block** , kullanıcıların cihazdaki esım 'e bir hücresel plan kaldırmasını veya bu planı eklemesini önler. **Yapılandırılmadı** (varsayılan) ayarı kullanıcıların bu ayarları değiştirmesine izin verir.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 12,1 ve üzeri
  - ıpados 13,0 ve üzeri

- **Yazılım güncelleştirmelerini ertele**: **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, yazılım güncelleştirmeleri cihazda, Apple tarafından yayımlandığında görüntülenir. Örneğin, bir iOS/ıpados güncelleştirmesi Apple tarafından belirli bir tarihte yayınlanmışsa, bu güncelleştirme doğal olarak cihazda yayın tarihinin etrafında görüntülenir.

  **Etkinleştir** ayarını kullanarak güncelleştirmelerin cihazlarda gösterilmesini 0-90 gün boyunca geciktirebilirsiniz. Bu ayar, güncelleştirmelerin yüklenme tarihini veya durumunu denetlemez. 

  - **Yazılım güncelleştirmeleri gecikmesi**: 0-90 günden bir değer girin. Gecikme süresi sona erdiğinde kullanıcılara gecikmenin tetiklendiği tarihte kullanılabilir durumda olan en eski işletim sistemi sürümüne güncelleştirme bildirimi gönderilir.

    Örneğin **1 Ocak** tarihinde iOS.12a'nın yayımlanması ve **Görünürlük geciktirme** ayarının **5 gün** olması durumunda iOS 12.a, son kullanıcı cihazlarında kullanılabilir güncelleştirme olarak gösterilmez. Yayımlandıktan sonraki **altıncı günde** bu güncelleştirme kullanıma sunulur ve kullanıcılar tarafından yüklenebilir.

    Bu ayarın geçerli olduğu sürümler:  
    - iOS 11,3 ve üzeri
    - ıpados 13,0 ve üzeri

## <a name="password"></a>Parola

### <a name="settings-apply-to-all-enrollment-types"></a>Ayarlar için geçerlidir: tüm kayıt türleri

- **Parola**: son kullanıcının cihaza erişmek için bir parola girmesini **gerektir** . **Yapılandırılmadı** (varsayılan), kullanıcıların bir parola girmeden cihaza erişmesine izin verir.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: cihaz kaydı, otomatik cihaz kaydı (denetimli)

> [!IMPORTANT]
> Kullanıcı tarafından kaydedilen cihazlarda, herhangi bir parola ayarını yapılandırırsanız, **basit parolalar** ayarları otomatik olarak **engelleme**olarak ayarlanır ve 6 basamaklı bir PIN zorlanır.
>
> Örneğin, **parola süre sonu** ayarını yapılandırır ve bu ilkeyi Kullanıcı tarafından kaydedilen cihazlara gönderirsiniz. Cihazlarda aşağıdakiler olur:
>
> - **Parola süre sonu** ayarı yok sayılır.
> - `1111` veya `1234`gibi basit parolalara izin verilmez.
> - 6 basamaklı bir PIN zorlanır.

- **Basit parolalar**: daha karmaşık parolalar Istemek için **Engelle** ' yi seçin. **Yapılandırılmadı** ayarı `0000` ve `1234` gibi basit parolalara izin verir.

- **Gerekli parola türü**: kuruluşunuzun gerektirdiği parola türünü seçin. Seçenekleriniz şunlardır:
  - **Cihaz varsayılanı**
  - **Sayısal**
  - **Alfasayısal**
- **Paroladaki alfasayısal olmayan karakter sayısı**: `#` veya `@`gibi, parolada bulunması gereken simge karakterlerinin sayısını girin.

- **Minimum parola uzunluğu**: bir kullanıcının girmesi gereken minimum uzunluğu 4 ile 14 karakter arasında girin. Kullanıcı kayıtlı cihazlarda 4 ila 6 karakter uzunluğunda bir uzunluk girin.
  
  > [!NOTE]
  > Kullanıcı kayıtlı cihazlarda, kullanıcılar 6 basamaktan daha büyük bir PIN ayarlayabilir. Ancak cihazda 6 ' dan fazla basamak uygulanmaz. Örneğin, bir yönetici minimum uzunluğu `8`olarak ayarlar. Kullanıcı tarafından kaydedilen cihazlarda, kullanıcılardan yalnızca 6 basamaklı bir PIN ayarlaması gerekir. Intune, Kullanıcı tarafından kaydedilen cihazlarda 6 basamaktan daha büyük bir PIN 'ı zorlamaz.

- **Cihaz silinmeden önceki oturum açma hatalarının sayısı**: cihaz temizlenmeden önce izin verilecek başarısız oturum açma işlemlerinin sayısını girin (4-11 arasında).
  
  iOS/ıpados, bu ayarı etkileyebilecek yerleşik güvenliğe sahiptir. Örneğin, iOS/ıpados, oturum açma hatalarının sayısına bağlı olarak ilkeyi tetikleyebilir. Aynı zamanda aynı geçiş kodunu bir girişimlerle tekrar girmeyi de düşünebilirsiniz. Apple 'ın [iOS/ıpados Güvenlik Kılavuzu](https://www.apple.com/business/site/docs/iOS_Security_Guide.pdf) (Apple 'ın Web sitesini açar) iyi bir kaynaktır ve Passcodes hakkında daha ayrıntılı bilgiler sağlar.
  
- **Parola istenmeden önce ekran kilitlenmesinden sonraki en fazla dakika**<sup>1</sup>: kullanıcının parolasını yeniden girmesi gerekmeden önce cihazın ne kadar süreyle boşta kalacağını girin. Girdiğiniz süre cihazda şu anda ayarlanmış olan süreden uzunsa, cihaz girdiğiniz süreyi yoksayar. İOS 8.0 + çalıştıran cihazlarda desteklenir ve ıpados 13.0 +.

- **Ekran kilitlenmeden önce geçmesi gereken en fazla dakika**sayısı<sup>1</sup>: ekran kilitlenmeden önce cihazda izin verilen en fazla dakika cinsinden süre sayısını girin.

  **iOS/ıpados seçenekleri**:  

  - **Yapılandırılmadı** (varsayılan): Intune bu ayara dokunmaz.
  - **Hemen**: 30 saniyelik işlem yapılmadan sonra ekran kilitleri.
  - **1**: 1 dakikalık bir işlem yapılmadan sonra ekran kilitleri.
  - **2**: 2 dakikalık bir işlem yapılmadan sonra ekran kilitleri.
  - **3**: 3 dakikalık bir işlem yapılmadan sonra ekran kilitleri.
  - **4**: 4 dakikalık bir işlem yapılmadan sonra ekran kilitleri.
  - **5**: 5 dakikalık bir işlem yapılmadan sonra ekran kilitleniyor.

  **ıpados seçenekleri**:  

  - **Yapılandırılmadı** (varsayılan): Intune bu ayara dokunmaz.
  - **Hemen**: 2 dakikalık bir işlem yapılmadan sonra ekran kilitleri.
  - **2**: 2 dakikalık bir işlem yapılmadan sonra ekran kilitleri.
  - **5**: 5 dakikalık bir işlem yapılmadan sonra ekran kilitleniyor.
  - **10**: 10 dakikalık bir işlem yapılmadan sonra ekran kilitleniyor.
  - **15**: 15 dakika etkin olmadığında ekran kilitleri.

  Bir değer iOS ve ıpados için uygulanmazsa, Apple en yakın *En düşük* değeri kullanır. Örneğin, `4` dakika girerseniz, ıpados cihazları `2` dakika kullanır. `10` dakika girerseniz, iOS cihazları `5` dakika kullanır. Bu bir Apple kısıtlamasıdır.
  
  > [!NOTE]
  > Bu ayar için Intune kullanıcı arabirimi iOS ve ıpados tarafından desteklenen değerleri birbirinden ayırır. Kullanıcı arabirimi gelecek bir sürümde güncelleştirilmiş olabilir.

- **Parola kullanım süresi (gün)**: cihaz parolasının değiştirilmesi gereken gün sayısını girin.
- **Önceki parolaların yeniden kullanılmasını engelle**: eski bir parolanın yeniden kullanılabilmesi için kullanılması gereken yeni parola sayısını girin.
- **Dokunma kimliği ve yüz kimliği kilit açma**: cihazın kilidini açmak için parmak izini veya yüzü kullanmayı engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** , kullanıcının bu yöntemleri kullanarak cihazın kilidini açmasına izin verir.

  Bu ayarı engellemek, cihazın kilidini açmak için çok yönlü kimlik doğrulamasının kullanılmasını da engeller.

  Yüz KIMLIĞI şu şekilde geçerlidir:  
  - iOS 11,0 ve üzeri
  - ıpados 13,0 ve üzeri

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: otomatik cihaz kaydı (denetimli)

- **Geçiş kodu değişikliği**: geçiş kodunun değiştirilmesini, eklenmesini veya kaldırılmasını durdurmak için **Engelle** ' yi seçin. Bu özellik engellendikten sonra denetimli cihazlarda geçiş kodu kısıtlamalarında yapılan değişiklikler yoksayılır. **Yapılandırılmadı** (varsayılan) ayarı, geçiş kodu ekleme, değiştirme veya kaldırma işlemlerine izin verir.

  - **Dokunma kimliği ve yüz kimliği değişikliği**: **engelleme** , kullanıcının TouchID parmak izlerini ve yüz kimliğini değiştirmesini, eklemesini veya kaldırmasını engeller. **Yapılandırılmadı** (varsayılan), kullanıcının cihazdaki TouchID parmak Izlerini ve yüz kimliğini güncelleştirmesine izin verir.

    Bu ayarı engellemek, kullanıcının çok yönlü kimlik doğrulamasını değiştirmesini, eklemesini veya kaldırmasını de engeller.

    Yüz KIMLIĞI şu şekilde geçerlidir:  
    - iOS 11,0 ve üzeri
    - ıpados 13,0 ve üzeri

- **Parola Otomatik doldurmayı engelle**: IOS/ıpados üzerinde parolaları otomatik doldur özelliğinin kullanılmasını engellemek için **Engelle** ' yi seçin. **Engelle** ayarını seçmek şu sonuçlara da neden olur:

  - Safari'de veya diğer uygulamalarda kullanıcılara parolaları kaydetmek isteyip istemedikleri sorulmaz.
  - Otomatik Güçlü Parolalar devre dışı bırakılır ve kullanıcılara güçlü parola önerisi sunulmaz.

  **Yapılandırılmadı** (varsayılan) ayarı bu özelliklere izin verir.

- **Parola yakınlık Isteklerini engelle**: bir kullanıcının cihazının yakındaki cihazlardan parola Isteyememesi için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan) ayarı bu parola isteklerine izin verir.
- **Parola paylaşmayı engelle**: **blok** , AirDrop kullanan cihazlar arasında parolaların paylaşılmasını önler. **Yapılandırılmadı** (varsayılan) ayarı, parolaların paylaşılmasına izin verir.
- **Parola veya kredi kartı bilgileri Için dokunma kimliği veya yüz kimliği kimlik doğrulaması ıste otomatik doldurma**: **gerekli**olarak ayarlandığında, parolaların veya kredi kartı bilgilerinin otomatik olarak Safari ve diğer uygulamalarda otomatik olarak doldurulabilmesi için kullanıcıların TouchID veya çok yönlü kimliği kullanarak kimlik doğrulaması yapması gerekir. **Yapılandırılmadı** (varsayılan) ayarı kullanıcıların cihaz ayarlarında bu özelliği denetlemesine izin verir.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11,0 ve üzeri
  - ıpados 13,0 ve üzeri
  
<sup>1</sup> **parola istenmeden önce ekran kilitlenmesinden sonra ekran kilitlenmeden ve en fazla dakika geçtikten sonra** **işlem yapılmadan maksimum dakika** sayısını yapılandırdığınızda, bunlar sırayla uygulanır. Örneğin, her iki ayarın da değerini **5** dakikaya ayarlarsanız, ekran beş dakika sonra otomatik olarak kapanır ve cihazın kilitlenmesi için beş dakika daha geçmesi gerekir. Ancak, kullanıcı ekranı el ile kapatırsa ikinci ayar hemen uygulanır. Aynı örnekte, kullanıcı ekranı kapattıktan sonraki beş dakikanın sonunda cihaz kilitlenir.

## <a name="locked-screen-experience"></a>Kilit Ekranı Deneyimi

### <a name="settings-apply-to-all-enrollment-types"></a>Ayarlar için geçerlidir: tüm kayıt türleri

- **Cihaz kilitliyken denetim merkezi erişimi**: Cihaz kilitliyken Denetim Merkezi uygulamasına erişimi engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan), cihaz kilitlendiğinde kullanıcıların Denetim Merkezi uygulamasına erişmesine izin verir.
- **Cihaz kilitliyken bildirimler**: **blok** Cihaz kilitliyken bildirimlere erişimi engeller. **Yapılandırılmadı** (varsayılan), kullanıcının cihazın kilidini açmadan bildirimlere erişmesine izin verir.
- **Cihaz kilitliyken bugün görünümü**: **blok** , Cihaz kilitliyken Bugün görünümüne erişimi engeller. **Yapılandırılmadı** (varsayılan), cihaz kilitlendiğinde kullanıcının bugün görünümünü görmesini sağlar.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: cihaz kaydı, otomatik cihaz kaydı (denetimli)

- **Cihaz kilitliyken cüzdan bildirimleri**: **blok** , Cihaz kilitliyken cüzdan uygulamasına erişimi engeller. **Yapılandırılmadı** (varsayılan), Cihaz kilitliyken kullanıcının cüzdan uygulamasına erişmesine izin verir.

## <a name="app-store-doc-viewing-gaming"></a>Uygulama Mağazası, Belge Görüntüleme, Oyun

### <a name="settings-apply-to-all-enrollment-types"></a>Ayarlar için geçerlidir: tüm kayıt türleri

- **Yönetilmeyen uygulamalarda kurumsal belgeleri görüntüleme**: **blok** , şirket belgelerinin yönetilmeyen uygulamalarda görüntülenmesini önler. **Yapılandırılmadı** (varsayılan), şirket belgelerinin herhangi bir uygulamada görüntülenmesine izin verir. Örneğin kullanıcıların OneDrive uygulamasından Dropbox’a dosya kaydetmesini engellemek istiyorsunuz. Bu ayarı **Engelle** olarak yapılandırın. Cihaz ilkeyi aldıktan sonra (örneğin, yeniden başlatıldıktan sonra) artık kaydetmeye izin vermez.


  > [!NOTE]
  > Bu ayar engellendiğinde, App Store 'dan yüklenen üçüncü taraf klavyeler de engellenir.

  - **Yönetilmeyen uygulamaların yönetilen kişiler hesaplarından okumasına Izin ver**: **izin ver**olarak ayarlandığında, yerleşik IOS/ıpados kişileri uygulaması gibi yönetilmeyen uygulamalar, Outlook mobil uygulaması da dahil olmak üzere yönetilen uygulamalardaki iletişim bilgilerini okuyabilir ve bunlara erişebilir. **Yapılandırılmadı** (varsayılan), cihazdaki yerleşik Kişiler uygulamasından yinelenenleri kaldırma dahil olmak üzere okumayı engeller.  
  
    Bu ayar, iletişim bilgilerinin okunmasına izin verir veya bunu engeller. Uygulamalar arasındaki kişileri eşitlemeyi denetlemez.
  
    Bu ayarı kullanmak için **Yönetilmeyen uygulamalarda kurumsal belgeleri görüntüleme** ayarını **Engelle** olarak belirtin.

  Bu iki ayar hakkında daha fazla bilgi edinmek ve iOS/ıpados 'a yönelik Outlook 'a yönelik etkileri için Outlook 'ta etkileri için bkz. [destek İpucu: iOS/ıpados yerel kişiler uygulamasıyla Intune özel profil ayarlarını kullanma](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Use-Intune-custom-profile-settings-with-the-iOS/ba-p/298453).

- **AirDrop 'u yönetilmeyen hedef olarak değerlendir**: **gerektir** AirDrop, yönetilmeyen bir bırakma hedefi olarak değerlendirilir. Yönetilen uygulamaların Airdrop'u kullanarak veri göndermesini durdurur. 
- Kurumsal **olmayan belgeleri kurumsal uygulamalarda görüntüleme**: **blok** kurumsal uygulamalarda kurumsal olmayan belgelerin görüntülenmesini önler. **Yapılandırılmadı** (varsayılan), şirket tarafından yönetilen uygulamalarda tüm belgelerin görüntülenmesine izin verir.

  **Engelleme** ayarı, IOS için Outlook/ıpados için de ilgili kişileri dışarı aktarma eşitlemesini engeller. Daha fazla bilgi için bkz. [destek İpucu: IOS12 MDM denetimleriyle Outlook iOS/ıpados Iletişim eşitlemesini etkinleştirme](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Enabling-Outlook-iOS-Contact-Sync-with-iOS12-MDM/ba-p/298453).

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: cihaz kaydı, otomatik cihaz kaydı (denetimli)

- **Tüm satın alımlarda ITunes mağazası parolası gerektir**: kullanıcının her uygulama Içi veya iTunes satın alma IÇIN Apple Kimliği parolasını girmesini **gerektir** . **Yapılandırılmadı** (varsayılan), her seferinde parola sormadan satın alma işlemlerine izin verir.
- **Uygulama içi satın almalar**: mağazadan uygulama içi satın alımlardan kaçınmak için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan), çalışan bir uygulama içinde satın alma işlemlerine izin verir.
- **' Erotik ' olarak Işaretlenen iBook mağazasından Içerik indir**: engellemek için **Engelle** ' yi seçin kullanıcıların IBook mağazasından Erotika olarak etiketlenmiş bir medya indirmesini önler. **Yapılandırılmadı** (varsayılan), kullanıcının "Erotika" kategorisiyle kitap indirmesine izin verir.
- **Yönetilen uygulamaların yönetilmeyen kişiler hesaplarına kişi yazmasına Izin ver**: **izin ver**olarak ayarlandığında, Outlook Mobile uygulaması gibi yönetilen uygulamalar, iş ve şirket kişileri dahil iletişim bilgilerini yerleşik IOS/ıpados kişileri uygulamasına kaydedebilir veya eşitleyebilir. **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, yönetilen uygulamalar cihazdaki yerleşik IOS/ıpados kişileri uygulamasına iletişim bilgilerini kaydedemez veya eşitleyemez.
  
  Bu ayarı kullanmak için **Yönetilmeyen uygulamalarda kurumsal belgeleri görüntüleme** ayarını **Engelle** olarak belirtin.

- **Derecelendirme bölgesi**: izin verilen İndirilenler için kullanmak istediğiniz derecelendirme bölgesini seçin. Ardından, **filmler**, **TV programları**ve **uygulamalar**için izin verilen derecelendirmeleri seçin.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: otomatik cihaz kaydı (denetimli)

- **App Store**: **Block** , denetimli cihazlarda uygulama deposuna erişimi engeller. **Yapılandırılmadı** (varsayılan) erişime izin verir.

  İOS/ıpados 13,0 ile başlayarak, bu ayar denetimli cihazlar gerektirir.

  - **App Store 'dan uygulama yükleme**: cihaz ana ekranından uygulama mağazasını engellemek için **Engelle** ' yi seçin. Son kullanıcılar, uygulamaları yüklemek için iTunes’u veya Apple Configurator aracını kullanmaya devam edebilir. **Yapılandırılmadı** (varsayılan), uygulama mağazasının giriş ekranında yapılmasına izin verir.
  - **Otomatik uygulama indirmeleri**: diğer cihazlarda satın alınan uygulamaların otomatik olarak indirilmesini engellemek için **Engelle** ' yi seçin. Mevcut uygulamalarında yapılan güncelleştirmeler bundan etkilenmez. **Yapılandırılmadı** (varsayılan), diğer IOS/ıpados cihazlarında satın alınan uygulamaların cihaza indirilmesine izin verir.

- **Açık iTunes Music, podcast veya News içeriği**: açık iTunes Music, podcast veya News içeriğini engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan), cihazın mağazadan yetişkinlere yönelik olarak derecelendirilmiş içeriğe erişmesine izin verir.

  İOS/ıpados 13,0 ile başlayarak, bu ayar denetimli cihazlar gerektirir.

- **Game Center arkadaş ekleme**: **blok** kullanıcıların Game Center arkadaş eklemesini engeller. **Yapılandırılmadı** (varsayılan), kullanıcının Game Center arkadaş eklemesine izin verir.

  İOS/ıpados 13,0 ile başlayarak, bu ayar denetimli cihazlar gerektirir.

- **Game Center**: Game Center uygulamasının kullanımını **engelleyin** . **Yapılandırılmadı** (varsayılan), cihazda Game Center uygulamasının kullanılmasına izin verir.
- Çok **oyunculu oyunlar**: çok oyunculu oyunları engellemek için **blok** seçin. **Yapılandırılmadı** (varsayılan), kullanıcının cihazda çok oyunculu oyunlar oynamasına izin verir.

  İOS/ıpados 13,0 ile başlayarak, bu ayar denetimli cihazlar gerektirir.

- **Dosyalar uygulamasında ağ sürücüsüne erişim**: sunucu ileti bloğu (SMB) protokolünü kullanarak, cihazlar bir ağ sunucusundaki dosyalara veya diğer kaynaklara erişebilir. **Devre dışı bırak ayarı** , BIR ağ SMB sürücüsündeki dosyalara erişimi engeller. **Yapılandırılmadı** (varsayılan) erişime izin verir.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 13,0 ve üzeri
  - ıpados 13,0 ve üzeri

## <a name="built-in-apps"></a>Yerleşik Uygulamalar

### <a name="settings-apply-to-all-enrollment-types"></a>Ayarlar için geçerlidir: tüm kayıt türleri

- **Siri**: **Block** Siri 'e erişimi engeller. **Yapılandırılmadı** (varsayılan), cihazda Siri Voice Yardımcısı 'nın kullanılmasına izin verir.
  - **Siri Cihaz kilitliyken**: Cihaz kilitliyken Siri 'e erişimi engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan), kilitli olduğunda cihazda Siri Voice Yardımcısı 'nın kullanılmasına izin verir.

- **Safari sahtekarlık uyarıları**: cihazdaki Web tarayıcısında sahtekarlık uyarılarının gösterilmesi **gerekir** . **Yapılandırılmadı** (varsayılan) ayarı, bu özelliği devre dışı bırakır.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: cihaz kaydı, otomatik cihaz kaydı (denetimli)

- **Internet 'ten sonuçları döndürmek Için Spotlight araması**: **Block** , projektörün bir Internet aramasından herhangi bir sonuç döndürmesini engeller. **Yapılandırılmadı** (varsayılan) ayarı, Spotlight'ın internete bağlanarak arama sonuçlarını getirmesine izin verir.

- **Safari tanımlama bilgileri**: cihazda tanımlama bilgilerinin nasıl işleneceğini seçin. Seçenekleriniz şunlardır:
  - İzin ver
  - Tüm tanımlama bilgilerini engelle
  - Ziyaret edilen web sitelerinin tanımlama bilgilerine izin ver
  - Geçerli web sitesinin tanımlama bilgilerine izin ver

- **Safari JavaScript**: **Block** tarayıcıda Java betiklerinin çalıştırılmasını önler. **Yapılandırılmadı** (varsayılan) Java betiklerine izin verir.

- **Safari açılır pencereleri**: Web tarayıcısında açılır pencere engelleyicisini devre dışı bırakma **bloğu** . **Yapılandırılmadı** (varsayılan) açılır pencere engelleyiciye izin verir.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: otomatik cihaz kaydı (denetimli)

- **Kamera**: cihazdaki kameraya erişimi engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan) ayarı, cihazın kamerasına erişim sağlar.

  İOS/ıpados 13,0 ile başlayarak, bu ayar denetimli cihazlar gerektirir.

  - Çok **yönlü saat**: çok yönlü uygulama erişimini engelleme **bloğu** . **Yapılandırılmadı** (varsayılan), cihazda çok yönlü bir zaman uygulamasına erişime izin verir.

    İOS/ıpados 13,0 ile başlayarak, bu ayar denetimli cihazlar gerektirir.

- **Siri küfür filtresi**: **gerektir** , Siri 'ın dikte etmesini veya küfürlü dilini kullanmasını önler.

  Bu ayarı kullanmak için **Siri** ayarını **Engelle**olarak ayarlayın.

- **Siri Kullanıcı tarafından oluşturulan içeriği Internet 'ten sorgulamak için**: **Block** , soruların yanıt vermesi için Web sitelerine erişmesini engeller. **Yapılandırılmadı** (varsayılan), Siri 'in internet 'ten Kullanıcı tarafından oluşturulan içeriğe erişmesine izin verir.

  Bu ayarı kullanmak için **Siri** ayarını **Engelle**olarak ayarlayın.

- **Apple News**: cihazdaki Apple News uygulamasına erişimi engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan) Apple News uygulamasının kullanılmasına izin verir.
- **IBOOKS Store**: **Block** , iBooks deposuna erişimi engeller. **Yapılandırılmadı** (varsayılan), kullanıcıların, iBook mağazasından kitap alıp almasına izin verir.
- **Cihazdaki iletiler uygulaması**: **blok** , kullanıcıların IMessage için iletiler uygulamasını kullanmalarını engeller. Cihaz metin iletilerini destekliyorsa, kullanıcı SMS kullanarak SMS mesajları gönderip alabilir. **Yapılandırılmadı** (varsayılan) iletileri Internet üzerinden göndermek ve okumak için iletiler uygulamasının kullanılmasına izin verir.
- **Pod yayınları**: **blok** , kullanıcıların Pod yayınları uygulamasını kullanmasını engeller. **Yapılandırılmadı** (varsayılan) Pod yayınları uygulamasının kullanılmasına izin verir.
- **Müzik hizmeti**: **blok** , müzik uygulamasını klasik moda geri döndürür ve müzik hizmetini devre dışı bırakır. **Yapılandırılmadı** (varsayılan) ayarı, Apple Music uygulamasının kullanılmasına izin verir.
- **ITunes Radio hizmeti**: **Block** , kullanıcıların iTunes radyo uygulamasını kullanmalarını engeller. **Yapılandırılmadı** (varsayılan), iTunes Radyo uygulamasının kullanılmasına izin verir.
- **iTunes Mağazası**: **yapılandırılmamış** (varsayılan) cihazlarda iTunes izin verir. **Blok** , kullanıcıların cihazda iTunes kullanmasını engeller. 

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 4,0 ve üzeri
  - ıpados 13,0 ve üzeri

- **İPhone 'umu bul**: **Yapılandırılmadı** (varsayılan), cihazın yaklaşık konumunu almak Için bu uygulamamı Bul özelliğinin kullanılmasına izin verir. **Block** , bu özelliğin uygulamamda Bul özelliğini engelliyor. 

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 13,0 ve üzeri
  - ıpados 13,0 ve üzeri

- **Arkadaşlarımı bul**: **Yapılandırılmadı** (varsayılan), bir Apple cihazından veya iCloud.com aile ve arkadaşlar bulmak Için bu uygulamamı Bul özelliğinin kullanılmasına izin verir. **Block** , bu özelliğin uygulamamda Bul özelliğini engelliyor.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 13,0 ve üzeri
  - ıpados 13,0 ve üzeri

- **Arkadaşlarımı bul uygulama ayarlarında yapılan değişiklikler**: **Block** Arkadaşlarımı bul uygulama ayarlarında değişiklik yapılmasını önler. **Yapılandırılmadı** (varsayılan), kullanıcının Arkadaşlarımı Bul uygulamasının ayarlarını değiştirmesine izin verir.

- **Internet 'ten sonuçları döndürmek Için Spotlight araması**: **Block** , projektörün bir Internet aramasından herhangi bir sonuç döndürmesini engeller. **Yapılandırılmadı** (varsayılan) ayarı, Spotlight'ın internete bağlanarak arama sonuçlarını getirmesine izin verir.

- **Cihazdan sistem uygulamalarının kaldırılmasını engelle**: **blok** seçme, sistem uygulamalarını cihazdan kaldırma yeteneğini devre dışı bırakır. **Yapılandırılmadı** (varsayılan), kullanıcıların sistem uygulamalarını kaldırmasına izin verir.

- **Safari**: cihazda Safari tarayıcısını kullanmayı **engelleyin** . **Yapılandırılmadı** (varsayılan), kullanıcıların Safari tarayıcısını kullanmasına izin verir.

  İOS/ıpados 13,0 ile başlayarak, bu ayar denetimli cihazlar gerektirir.

- **Safari otomatik doldurma**: **blok** cihazdaki otomatik doldurma özelliğini devre dışı bırakır. **Yapılandırılmadı** (varsayılan) ayarı, kullanıcıların web tarayıcısındaki otomatik tamamlama ayarlarını değiştirmesine olanak tanır.

  İOS/ıpados 13,0 ile başlayarak, bu ayar denetimli cihazlar gerektirir.

## <a name="restricted-apps"></a>Kısıtlı uygulamalar

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: cihaz kaydı, otomatik cihaz kaydı (denetimli)

- **Kısıtlanmış uygulamalar listesi türü**: Kullanıcıların yüklemesine veya kullanmasına izin verilmeyen uygulamaların bir listesini oluşturun. Seçenekleriniz şunlardır:

  - **Yapılandırılmadı** (varsayılan): Intune 'dan bir kısıtlama yoktur. Kullanıcıların atadığınız uygulamalara ve yerleşik uygulamalarına erişimi vardır.
  - **Yasaklanmış uygulamalar**: Intune tarafından yönetilmeyen ve cihaza yüklenmesini istemediğiniz uygulamalar. Kullanıcıların yasaklanmış bir uygulamayı yüklemesi engellenmiyor. Ancak bir Kullanıcı bu listeden bir uygulama yüklerse Intune 'da raporlanır.
  - **Onaylanan uygulamalar**: Kullanıcıların yüklemesine izin verilen uygulamalar. Kullanıcılar listelenmeyen uygulamaları yüklememelidir. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir. Kullanıcıların onaylı uygulamalar listesinde olmayan bir uygulamayı yüklenmesi engellenmez. Ancak bunu yaptıysanız Intune 'da raporlanır.

Bu listelere uygulama eklemek için şunları yapabilirsiniz:

- İstediğiniz uygulamanın iTunes App mağazası URL'sini **ekleyin**. Örneğin, Microsoft çalışma klasörleri uygulamasını eklemek için `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` veya `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`girin.

  Uygulamanın URL'sini bulmak için, iTunes App Store'u açın ve uygulamayı arayın. Örneğin `Microsoft Remote Desktop` veya `Microsoft Word` için arama yapın. Uygulamayı seçin ve URL'sini kopyalayın.

  iTunes kullanarak da uygulamayı bulabilir ve ardından **Bağlantıyı Kopyala** görevini kullanıp uygulama URL’sini alabilirsiniz.

- URL 'SI dahil olmak üzere uygulamayla ilgili ayrıntılarla bir CSV dosyasını **Içeri aktarın** . `<app url>, <app name>, <app publisher>` biçimini kullanın. Veya, kısıtlanmış uygulamalar listesini içeren mevcut bir listeyi aynı biçimde **dışarı aktarın** .

> [!IMPORTANT]
> Kısıtlı uygulama ayarlarını kullanan cihaz profilleri kullanıcı gruplarına atanmalıdır.

## <a name="show-or-hide-apps"></a>Uygulamaları gösterme veya gizleme

İOS 9,3 + ve ıpados 13.0 + çalıştıran cihazlar için geçerlidir.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: otomatik cihaz kaydı (denetimli)

- **Uygulama türü listesi**: gösterilecek veya gizlenecek uygulamaların bir listesini oluşturun. Yerleşik uygulamaları ve iş kolu uygulamalarını gösterebilir veya gizleyebilirsiniz. Apple 'ın Web sitesinde [yerleşik bir Apple Apps](https://support.apple.com/HT208094)listesi bulunur. Seçenekleriniz şunlardır:

  - **Gizli uygulamalar**: kullanıcılardan gizlenen uygulamaların listesini girin. Kullanıcılar bu uygulamaları görüntüleyemez veya açamaz.
  
    Apple, bazı yerel uygulamaların gizlenmelerini önler. Örneğin, cihazdaki **Ayarlar** uygulamasını gizleyemezsiniz. [Yerleşik Apple uygulamalarını silme](https://support.apple.com/HT208094) , gizli olabilecek uygulamaları listeler.
  
  - **Görünür uygulamalar**: kullanıcıların görüntüleyebileceği ve başlatabileceği uygulamaların bir listesini girin. Başka hiçbir uygulama görüntülenemez veya başlatılamaz.

- **Uygulama URL 'si**: göstermek veya gizlemek istediğiniz uygulamanın Mağaza uygulama URL 'sini girin. Örneğin:

  - Microsoft çalışma klasörleri uygulamasını eklemek için `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` veya `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`girin. 

  - Microsoft Word uygulamasını eklemek için `https://itunes.apple.com/de/app/microsoft-word/id586447913` veya `https://apps.apple.com/de/app/microsoft-word/id586447913`girin.

  Uygulamanın URL'sini bulmak için, iTunes App Store'u açın ve uygulamayı arayın. Örneğin `Microsoft Remote Desktop` veya `Microsoft Word` için arama yapın. Uygulamayı seçin ve URL'sini kopyalayın.

  iTunes kullanarak da uygulamayı bulabilir ve ardından **Bağlantıyı Kopyala** görevini kullanıp uygulama URL’sini alabilirsiniz.

- **Uygulama PAKETI kimliği**: istediğiniz uygulamanın uygulama [paket kimliğini](bundle-ids-built-in-ios-apps.md) girin. Yerleşik uygulamaları ve iş kolu uygulamalarını gösterebilir veya gizleyebilirsiniz. Apple 'ın Web sitesinde [yerleşik bir Apple Apps](https://support.apple.com/HT208094)listesi bulunur.
- **Uygulama adı**: istediğiniz uygulamanın uygulama adını girin. Yerleşik uygulamaları ve iş kolu uygulamalarını gösterebilir veya gizleyebilirsiniz. Apple 'ın Web sitesinde [yerleşik bir Apple Apps](https://support.apple.com/HT208094)listesi bulunur.
- **Yayımcı**: istediğiniz uygulamanın yayımcısını girin.

Uygulamaları eklemek için şunları yapabilirsiniz:

- **Ekle**: uygulama listenizi oluşturmak için seçin.
- URL 'SI dahil olmak üzere uygulamayla ilgili ayrıntılarla bir CSV dosyasını **Içeri aktarın** . `<app url>, <app name>, <app publisher>` biçimini kullanın. Ya da, aynı biçimde eklediğiniz kısıtlı uygulamaların bir listesini oluşturmak için **dışa aktarın** .

## <a name="wireless"></a>Kablosuz

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: cihaz kaydı, otomatik cihaz kaydı (denetimli)

Veri dolaşımı için gereken Not (müşteri karışıklığına yardımcı olması için Ipucu veya önemli not): Bu ayar hedeflenen cihazın yönetim profilinde gösterilmez. Bunun nedeni, bu ayarın uzak bir cihaz eylemi olarak kabul edilmesidir ve cihazdaki veri dolaşımı durumu her değiştirildiğinde, Intune hizmeti tarafından yeniden engellenir. Yönetim profilinde olmasa dahi, yönetim konsolundaki raporlamadan başarı olarak gösterilse de çalışır. 
- **Veri dolaşımı**: hücresel ağ üzerinde veri dolaşımını engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan) ayarı cihaz cep telefonu şebekesindeyken veri dolaşımına izin verir.

  > [!IMPORTANT]
  > Bu ayar uzak cihaz eylemi olarak değerlendirilir. Bu nedenle, bu ayar cihazdaki yönetim profilinde gösterilmez. Cihazda veri dolaşımı durumu her değiştiğinde **veri dolaşımı** , Intune hizmeti tarafından engellenir. Intune 'da, raporlama durumu bir başarı gösteriyorsa, bu ayar cihazdaki yönetim profilinde gösterilmese de, çalıştığını öğrenin.

- **Dolaşım sırasında genel arka plan getirme**: **blok** , hücresel ağ üzerinde dolaşımda genel arka plan getirme özelliğinin kullanılmasını engeller. **Yapılandırılmadı** ayarı cihazın cep telefonu şebekesi üzerinde dolaşımdayken e-posta gibi verileri almasına izin verir.
- **Sesli arama**: kullanıcıların cihazda sesli arama özelliğini kullanmalarını engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan) ayarı cihazda sesli aramaya izin verir.
- **Ses dolaşımı**: hücresel ağ üzerinde ses dolaşımını engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan) ayarı cihaz cep telefonu şebekesindeyken ses dolaşımına izin verir.
- **Kişisel etkin nokta**: **Engelle** , kullanıcıların cihazındaki kişisel etkin noktayı her cihaz eşitlemesine karşı kapatır. Bu ayar bazı taşıyıcılar ile uyumlu olmayabilir. **Yapılandırılmadı** (varsayılan) ayarı kişisel etkin nokta yapılandırmasını kullanıcı tarafından ayarlanmış varsayılan değerinde bırakır.

  > [!IMPORTANT]
  > Bu ayar uzak cihaz eylemi olarak değerlendirilir. Bu nedenle, bu ayar cihazdaki yönetim profilinde gösterilmez. Kişisel etkin nokta durumu cihazda her değiştiğinde **Kişisel etkin nokta** , Intune hizmeti tarafından engellenir. Intune 'da, raporlama durumu bir başarı gösteriyorsa, bu ayar cihazdaki yönetim profilinde gösterilmese de, çalıştığını öğrenin.

- **Hücresel kullanım kuralları (yalnızca yönetilen uygulamalar)**: yönetilen uygulamaların hücresel ağlarda ne zaman kullanabileceği veri türlerini tanımlayın. Seçenekleriniz şunlardır:
  - **Hücresel veri kullanımını engelleyin**: **tüm yönetilen uygulamalar** için hücresel veri kullanmayı engelleyin veya **belirli uygulamaları seçin**.
  - **Dolaşım sırasında hücresel veri kullanımını engelle**: **tüm yönetilen uygulamalar** için Dolaşımda hücresel veri kullanmayı engelleyin veya **belirli uygulamaları seçin**.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: otomatik cihaz kaydı (denetimli)

- **Uygulama hücresel veri kullanım ayarlarında yapılan değişiklikler**: uygulama hücresel veri kullanımı ayarlarında değişiklik yapılmasını engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının hangi uygulamaların hücresel veri kullanabileceğini denetlemesine izin verir.
- **Hücresel plan ayarlarındaki değişiklikler**: **blok** , kullanıcıların hücresel plandaki ayarları değiştirmelerini engeller. **Yapılandırılmadı** (varsayılan) ayarı kullanıcıların değişiklik yapmasına izin verir.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11,0 ve üzeri
  - ıpados 13,0 ve üzeri

- **Kişisel etkin noktanın Kullanıcı değişikliği**: **blok**olarak ayarlandığında Kullanıcı kişisel etkin nokta ayarını değiştiremez. **Yapılandırılmadı** (varsayılan) son kullanıcıların kendi kişisel etkin kullanımlarını etkinleştirmesine veya devre dışı bırakmasına izin verir.

  Bu ayarı engellerseniz ve **Kişisel etkin nokta** ayarını engellerseniz kişisel etkin nokta kapalıdır.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 12,2 ve üzeri
  - ıpados 13,0 ve üzeri

- **Yalnızca yapılandırma profillerini kullanarak Wi-Fi ağlarına katılarak**: **gerektir** ayarı, cihazı yalnızca Intune yapılandırma profilleri aracılığıyla ayarlanan Wi-Fi ağlarını kullanmaya zorlar. **Yapılandırılmadı** (varsayılan) ayarı cihazın diğer Wi-Fi ağlarını kullanmasına izin verir.

  **Gerektir**olarak ayarlandığında, cihazda bir Wi-Fi profili bulunduğundan emin olun. Bir Wi-Fi profili atamadıysanız, bu ayar cihazın İnternet 'e bağlanmasını engelleyebilir. Diğer bir deyişle, bu cihaz kısıtlama profili bir Wi-Fi profilinden önce atanırsa cihazın İnternet 'e bağlanması engellenebilir.
  
  Bağlanamıyorsa, cihazın kaydını kaldırın ve bir Wi-Fi profiliyle yeniden kaydedin. Ardından, bu ayarı cihaz kısıtlamaları profilinde **gerekli** olacak şekilde ayarlayın ve profili cihaza atayın.

- **Wi-Fi her zaman açık**: **gerektir**olarak ayarlandığında, Ayarlar uygulamasında Wi-Fi açık kalır. Cihaz uçak modundayken bile ayarlarda veya denetim merkezinde devre dışı bırakılamaz. **Yapılandırılmadı** (varsayılan), kullanıcının Wi-Fi açma veya kapatma özelliğini denetlemesine izin verir.

  Bu ayarın yapılandırılması, kullanıcıların bir Wi-Fi ağı seçmesini engellemez.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 13,0 ve üzeri
  - ıpados 13,0 ve üzeri

## <a name="connected-devices"></a>Bağlı Cihazlar

### <a name="settings-apply-to-all-enrollment-types"></a>Ayarlar için geçerlidir: tüm kayıt türleri

- **Eşleştirilmiş Apple Watch Için bilek algılama**: **gerektir** , eşleştirilmiş bir Apple Watch 'un bilek algılamayı kullanmasına zorlar. Gerekli seçilirse, Apple Watch takılmadığında bildirim görüntülemez. 

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: cihaz kaydı, otomatik cihaz kaydı (denetimli)

- **AirPlay giden istek Isteklerini gerektir**: Kullanıcı, diğer Apple cihazlarına içerik akışı Için AirPlay kullandığında eşleme parolası **gerektir** . **Yapılandırılmadı** (varsayılan) ayarı kullanıcının parola girmeden AirPlay kullanarak içerik akışı yapmasına izin verir.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: otomatik cihaz kaydı (denetimli)

- **AirDrop**: **Block** cihazda AirDrop kullanımını engelliyor. **Yapılandırılmadı** (varsayılan) ayarı, yakındaki cihazlarla içerik değişimi için AirDrop özelliğinin kullanılmasına izin verir.
- **Apple Watch eşleştirme**: **blok** bir Apple Watch eşlemeyi engeller. **Yapılandırılmadı** (varsayılan) ayarı cihazın Apple Watch ile eşleştirilmesine izin verir.
- **Bluetooth değişikliği**: **blok** son kullanıcının cihazdaki Bluetooth ayarlarını değiştirmesini engeller. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının bu ayarları değiştirmesine izin verir.
- **İOS/ıpados cihazının eşleşebileceği cihazları denetlemek Için konak eşleştirme**: **Yapılandırılmadı** (varsayılan), yöneticinin bir iOS/ıpados cihazının hangi cihazlara eşlenebileceğini denetlemesine izin vermek için konak eşleştirmesine izin verir. **Engelle** ayarı konak eşleştirmeyi önler.
- **AirPrint 'ı engelle**: cihazda AirPrint özelliğinin kullanılmasını engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan) ayarı kullanıcının AirPrint'i kullanmasına izin verir.
  - **Anahtarlıkta AirPrint kimlik bilgilerinin depolanmasını engelle**: **blok** , cihazdaki Kullanıcı adı ve parola için Anahtarlık depolamanın kullanılmasını önler. **Yapılandırılmadı** (varsayılan) ayarı AirPrint kullanıcı adı ve parolasının Anahtar Zinciri uygulamasında depolanmasına izin verir.
  - **AirPrint için güvenilir BIR TLS sertifikası gerektir**: **gerektır** , cihazın TLS yazdırma iletişimi için güvenilir sertifikaları kullanmasını zorlar.
  - **AirPrint yazıcıları bloğunu engelle**: **blok** , ağ trafiği için kimlik avından kötü amaçlı AirPrint Bluetooth işaretlerini engeller. **Yapılandırılmadı** (varsayılan) ayarı cihazda AirPrint yazıcılarının tanıtılmasına izin verir.
- **Yeni yakındaki cihazları ayarlamayı engelle**: **blok** yakında yeni cihazları ayarlamaya yönelik istemi devre dışı bırakır. **Yapılandırılmadı** (varsayılan) ayarı yakındaki diğer Apple cihazlarıyla bağlantı kurulup kurulmayacağının kullanıcıya sorulmasına izin verir.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 11,0 ve üzeri
  - ıpados 13,0 ve üzeri

- **USB sürücüsündeki dosyalara erişim**: cihazlar, dosyaları bir USB sürücüsünde bağlayıp açabilir. **Devre dışı bırak ayarı** , cihaza USB bağlandığında dosyalar uygulamasında USB sürücüsüne cihaz erişimini engeller. Bu özelliğin devre dışı bırakılması, son kullanıcıların bir iPad 'e bağlı USB sürücüsüne dosya aktarımını engeller. **Yapılandırılmadı** (varsayılan) dosyalar uygulamasında USB sürücüsüne erişime izin verir.

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 13,0 ve üzeri
  - ıpados 13,0 ve üzeri

## <a name="keyboard-and-dictionary"></a>Klavye ve Sözlük

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: otomatik cihaz kaydı (denetimli)

- **Sözcük tanımı arama**: **blok** , kullanıcının bir sözcüğü vurgulamasını ve sonra da cihazda tanımını aramasını engeller. **Yapılandırılmadı** (varsayılan) ayarı, tanım arama özelliğine erişim sağlar.
- Tahmine **dayalı klavyeler**: **Yapılandırılmadı** (varsayılan), tahmine dayalı klavyeleri kullanarak kullanıcının istedikleri sözcükleri önermesine izin verir. **Engelle** ayarı bu özelliği önler.
- **Otomatik Düzeltme**: **Yapılandırılmadı** (varsayılan), cihazın yanlış yazılan sözcükleri otomatik olarak düzeltmesini sağlar. **Engelle** ayarı otomatik düzeltme kullanılmasını önler.
- **Klavye yazım denetimi**: **Yapılandırılmadı** (varsayılan), cihazda SpellChecker kullanılmasına izin verir. **Engelle** ayarı yazım denetleyicisine izin verir.
- **Klavye kısayolları**: **Yapılandırılmadı** (varsayılan), cihazda klavye kısayollarının kullanılmasına izin verir. **Engelle** ayarı kullanıcının klavye kısayollarını kullanmasını durdurur.
- **Dikte**: **blok** , kullanıcının metin girmesi için ses girişi kullanmasını engeller. **Yapılandırılmadı** (varsayılan) ayarı, kullanıcının dikteyle girişi kullanmasına izin verir.
- **Hızlı yol**: **Yapılandırılmadı** (varsayılan), kullanıcıların, cihazın klavyesinde sürekli bir giriş sağlayan hızlı yol kullanmasına izin verir. Kullanıcılar, sözcükler oluşturmak için anahtarlar arasında çekerek yazı yazabilir. **Block** , kullanıcıların hızlı yol kullanmasını engeller. 

  Bu özellik şu platformlarda geçerlidir:  
  - iOS 13,0 ve üzeri
  - ıpados 13,0 ve üzeri

## <a name="cloud-and-storage"></a>Bulut ve Depolama

### <a name="settings-apply-to-all-enrollment-types"></a>Ayarlar için geçerlidir: tüm kayıt türleri

- **Şifrelenmiş yedekleme**: **gerekli** olduğundan cihaz yedeklemelerinin şifrelenmesi gerekir.
- **Yönetilen uygulamalar buluta eşitlenir**: **Yapılandırılmadı** (varsayılan), Intune 'A, uygulamaların kullanıcının iCloud hesabıyla veri eşitlemesine olanak tanır. **Engelle** ayarı iCloud'a bu veri eşitlemesini engeller.
- **Kurumsal kitap yedeklemesini engelle**: kullanıcıların kurumsal kitaplar yedeklemesini engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan), kullanıcıların bu kitapları yedeklemesini sağlar.
- **Kurumsal kitap meta verileri eşitlemesini engelleyin (notlar ve vurgular)**: **blok** , kurumsal kitaplar 'da notların ve vurguların eşitlenmesini önler. **Yapılandırılmadı** (varsayılan) eşitlemeye izin verir.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: cihaz kaydı, otomatik cihaz kaydı (denetimli)

- **İCloud 'A fotoğraf akışı eşitleniyor**: **Yapılandırılmadı** (varsayılan), kullanıcıların cihazlarındaki **fotoğraf akışımı** iCloud 'a eşitlemesine ve tüm kullanıcıların cihazlarında kullanılabilir fotoğraflara sahip olmasını sağlar. **Engelle** ayarı iCloud'a fotoğraf akışının eşitlenmesini önler. Bu özelliğin engellenmesi veri kaybına neden olabilir. 
- **ICloud Fotoğraf Kitaplığı**: fotoğraf ve videoları bulutta depolamak için iCloud Fotoğraf Kitaplığı 'nı kullanmayı devre dışı bırakmak için **Engelle** olarak ayarlayın. iCloud Fotoğraf Arşivi'nden cihaza tamamen indirilmeyen tüm fotoğraflar cihazdan kaldırılır. **Yapılandırılmadı** (varsayılan) iCloud Fotoğraf kitaplığının kullanılmasına izin verir.
- **Paylaşılan fotoğraf akışı**: cihazda **iCloud Fotoğraf paylaşımını** devre dışı bırakmak için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan), paylaşılan fotoğraf akışına izin verir.
- **İletim**: **Yapılandırılmadı** (varsayılan), kullanıcıların bir iOS/ıpados cihazında çalışmaya başlamasını sağlar ve sonra başka bir iOS/ıpados veya MacOS cihazında başlattıkları çalışmaya devam eder. **Engelle** ayarı bu iletimi önler.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: otomatik cihaz kaydı (denetimli)

- **İCloud 'A yedekleme**: **Yapılandırılmadı** (varsayılan) kullanıcının cihazı iCloud 'a yedeklemesine izin verir. **Engelle** ayarı kullanıcının cihazı iCloud'a yedeklemesini durdurur.

  İOS/ıpados 13,0 ile başlayarak, bu ayar denetimli cihazlar gerektirir.

- **ICloud belge eşitlemesini engelle**: **Yapılandırılmadı** (varsayılan), iCloud depolama alanınıza belge ve anahtar-değer eşitlemeye izin verir. **Engelle** ayarı, iCloud'ın belgeleri ve verileri eşitlemesini engeller.

  İOS/ıpados 13,0 ile başlayarak, bu ayar denetimli cihazlar gerektirir.

- **ICloud anahtar zinciri eşitlemesini engelle**: anahtarlıkta depolanan kimlik bilgilerinin iCloud 'a eşitlenmesini devre dışı bırakmak için **bloğu** seçin. **Yapılandırılmadı** (varsayılan), kullanıcıların bu kimlik bilgilerini eşitlemesine izin verir.

  İOS/ıpados 13,0 ile başlayarak, bu ayar denetimli cihazlar gerektirir.

## <a name="autonomous-single-app-mode"></a>Otonom tek uygulama modu

İOS/ıpados cihazlarını, belirli uygulamaları otonom tek uygulama modunda çalıştıracak şekilde yapılandırmak için bu ayarları kullanın. Bu mod yapılandırıldığında ve Kullanıcı yapılandırılmış uygulamalardan birini başlattığında, cihaz bu uygulamaya kilitlenir. Uygulama/görev değiştirme, Kullanıcı izin verilen uygulamadan çıkana kadar devre dışı bırakıldı.

Örneğin, okul veya üniversite ortamında, kullanıcıların cihazda bir test geçirmesine imkan tanıyan bir uygulama ekleyin. Veya, son kullanıcı kimlik doğrulaması yapana kadar cihazı Şirket Portalı uygulamasına kilitleyin. Uygulama eylemleri Kullanıcı tarafından tamamlandığında veya bu ilkeyi kaldırdığınızda cihaz normal durumuna geri döner.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: otomatik cihaz kaydı (denetimli)

- **Uygulama adı**: istediğiniz uygulamanın adını girin.
- **Uygulama PAKETI kimliği**: istediğiniz UYGULAMANıN [paket kimliğini](bundle-ids-built-in-ios-apps.md) girin.
- **Ekle**: uygulama listenizi oluşturmak için seçin.

Ayrıca, uygulama adlarının ve paket kimliklerinin listesini içeren bir CSV dosyasını **Içeri aktarabilirsiniz** . Alternatif olarak uygulamaları içeren mevcut listeyi **dışarı aktarabilirsiniz**.

## <a name="kiosk"></a>Bilgi noktası

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: otomatik cihaz kaydı (denetimli)

- **Bilgi noktası modunda çalıştırılacak uygulama**: bilgi noktası modunda çalıştırmak istediğiniz uygulama türlerini seçin. Seçenekleriniz şunlardır:
  - **Yapılandırılmadı** (varsayılan): bilgi noktası ayarları uygulanmaz. Cihaz bilgi noktası modunda çalışmıyor.
  - **Mağaza uygulaması**: iTunes App Store 'da bir uygulamanın URL 'sini girin.
  - **Yönetilen uygulama**: Intune 'a eklediğiniz bir uygulamayı seçin.
  - **Yerleşik uygulama**: yerleşik UYGULAMANıN [paket kimliğini](bundle-ids-built-in-ios-apps.md) girin.

- **Yardımcı dokunma**: cihazda yardımcı dokunma erişilebilirlik ayarının olması **gerekir** . Bu özellik kullanıcılara zorlanabilecekleri ekran hareketlerinde yardımcı olur. **Yapılandırılmadı** ayarı bilgi noktası modunda bu özelliği çalıştırmaz veya etkinleştirmez.
- **Renkleri ters çevir**: görsel sorunları olan kullanıcıların ekran ekranını değiştirebilmeleri Için renkleri ters çevir erişilebilirlik ayarını **gerektir** . **Yapılandırılmadı** ayarı bilgi noktası modunda bu özelliği çalıştırmaz veya etkinleştirmez.
- **Mono ses**: cihazda mono ses erişilebilirlik ayarının olması **gerekir** . **Yapılandırılmadı** ayarı bilgi noktası modunda bu özelliği çalıştırmaz veya etkinleştirmez.
- **Voice Control**: **gerektir** , cihazda ses denetimi sağlar ve kullanıcıların Siri komutlarını kullanarak işletim sistemini tam olarak denetlemesine olanak tanır. **Yapılandırılmadı** , cihazda ses denetimini devre dışı bırakır.

  Bu ayarın geçerli olduğu sürümler:  
  - iOS 13,0 ve üzeri
  - ıpados 13,0 ve üzeri
  
  > [!TIP]
  > Kuruluşunuz için kullanılabilir LOB uygulamalarınız varsa ve iOS 13,0 yayımları olduğunda gün 0 ' da hazır bir **ses denetimi** yoksa, bu ayarı **yapılandırılmamış**olarak bırakmanız önerilir.

- **VoiceOver**: ekrandaki metin okumak için VoiceOver erişilebilirlik ayarının cihazda olması **gerekir** . **Yapılandırılmadı** ayarı bilgi noktası modunda bu özelliği çalıştırmaz veya etkinleştirmez.
- **Yakınlaştır**: kullanıcıların ekranda yakınlaştırmak için dokunmatik kullanmasına izin vermek üzere yakınlaştırma ayarının cihazda olmasını **gerektir** . **Yapılandırılmadı** ayarı bilgi noktası modunda bu özelliği çalıştırmaz veya etkinleştirmez.
- **Otomatik kilit**: **engelleme** cihazın otomatik olarak kilitlenmesini engeller. **Yapılandırılmadı** , bu özelliğe izin verir.
- **Zil düğmesi**: **blok** cihazdaki zil (sessiz) geçiş devre dışı bırakır. **Yapılandırılmadı** , bu özelliğe izin verir.
- **Ekran döndürme**: **blok** , Kullanıcı cihazı döndürürken ekran yönünün değiştirilmesini önler. **Yapılandırılmadı** , bu özelliğe izin verir.
- **Ekran uyku düğmesi**: cihazda ekran uyku modundan çıkarma düğmesini devre dışı bırakmak için **Engelle** ' yi seçin. **Yapılandırılmadı** , bu özelliğe izin verir.
- **Touch**: **Block** cihazdaki dokunmatik ekranı devre dışı bırakır. **Yapılandırılmadı** ayarı kullanıcının dokunmatik ekranı kullanmasına izin verir.
- **Ses düğmeleri**: **blok** , cihazdaki ses düğmelerinin kullanımını engeller. **Yapılandırılmadı** , ses düğmelerine izin verir.
- **Yardımcı dokunma denetimi**: kullanıcıların yardımcı Touch işlevini kullanmasına **izin ver** . **Yapılandırılmadı** ayarı bu özelliği devre dışı bırakır.
- **Renkleri ters çevir denetimi**: kullanıcıların renkleri ters çevirme işlevini ayarlamasına izin vermek için renk değişikliklerine ters çevirmeyi **izin verin** . **Yapılandırılmadı** ayarı bu özelliği devre dışı bırakır.
- **Seçili metinde konuş**: konuşma seçimine **izin ver** erişilebilirlik ayarları cihazda olmalıdır. Bu özellik kullanıcının seçtiği metni yüksek sesle okur. **Yapılandırılmadı** ayarı bu özelliği devre dışı bırakır.
- **Ses denetimi değişikliği**: kullanıcıların cihazlarındaki ses denetimi durumunu değiştirmesine **izin verin** . **Yapılandırılmadı** , kullanıcıların cihazlarındaki ses denetimi durumunu değiştirmesini engeller.

  Bu ayarın geçerli olduğu sürümler:  
  - iOS 13,0 ve üzeri
  - ıpados 13,0 ve üzeri

- **VoiceOver Control**: kullanıcıların, ekran metinlerin hızlı bir şekilde okunması gibi VoiceOver işlevini güncelleştirmesine olanak tanımak için VoiceOver değişikliklere **izin verin** . **Yapılandırılmadı** ayarı VoiceOver değişikliklerini engeller.
- **Yakınlaştırma denetimi**: Kullanıcı tarafından değişikliklere **izin ver** . **Yapılandırılmadı** ayarı yakınlaştırma değişikliklerini engeller.

> [!NOTE]
> İOS/ıpados cihazını bilgi noktası modu için yapılandırmadan önce, Apple Configurator aracını veya Apple Aygıt Kayıt Programı kullanarak cihazı denetimli moda almanız gerekir. Apple Configurator aracını kullanma konusunda Apple'ın kılavuzuna bakın.
> Girdiğiniz iOS/ıpados uygulaması profili atadıktan sonra yüklendiyse, cihaz yeniden başlatılana kadar cihaz bilgi noktası moduna girmez.

## <a name="domains"></a>Domains

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: cihaz kaydı, otomatik cihaz kaydı (denetimli)

- **İşaretlenmemiş e-** posta etki alanları > **eposta etki alanı URL 'si**: listeye bir veya daha fazla URL ekleyin. Son kullanıcılar, girdiğiniz etki alanlarından başka bir etki alanından e-posta aldığınızda, iOS/ıpados posta uygulamasında e-posta güvenilir değil olarak işaretlenir.

- **Yönetilen web etki alanları** > **Web Etki Alanı URL'si**; Listeye bir veya daha fazla URL ekleyin. Belgeler girdiğiniz etki alanlarından indirildiğinde yönetilen belgeler olarak değerlendirilir. Bu ayar yalnızca Safari tarayıcısı kullanılarak indirilen belgeler için geçerlidir.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Ayarlar için geçerlidir: otomatik cihaz kaydı (denetimli)

- Safari parolası etki **alanı URL 'si** > **otomatik doldurma etki alanları** : listeye bir veya daha fazla URL ekleyin. Kullanıcılar yalnızca bu listedeki URL’lerdeki parolaları kaydedebilir. Bu ayar yalnızca Safari tarayıcısı ve denetimli moddaki cihazlar için geçerlidir. Herhangi bir URL girmezseniz, parolalar tüm Web sitelerinden kaydedilebilir.

  Bu ayarın geçerli olduğu sürümler:  
  - iOS 9,3 ve üzeri
  - ıpados 13,0 ve üzeri

## <a name="settings-that-require-supervised-mode"></a>Denetimli mod gerektiren ayarlar

iOS/ıpados Denetimli mod yalnızca Apple Aygıt Kayıt Programı aracılığıyla veya Apple Configurator kullanılarak ilk cihaz kurulumu sırasında etkinleştirilebilir. Denetimli mod etkinleştirildikten sonra, Intune şu işlevleri kullanarak bir cihazı yapılandırabilir:

- Uygulama Kilidi (Tek Uygulama Modu) 
- Genel HTTP Proxy’si 
- Etkinleştirme Kilidini Devre Dışı Bırakma 
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

[Profili atama](../device-profile-assign.md) ve [durumunu izleme](../device-profile-monitor.md).

[macOS](device-restrictions-macos.md) cihazlarındaki özellikleri ve ayarları da kısıtlayabilirsiniz.
