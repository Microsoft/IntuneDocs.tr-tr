---
title: Microsoft Intune - Azure'da macOS ayarlarını kullanma | Microsoft Docs
titleSuffix: ''
description: Parola gereksinimlerini belirleme, kilit ekranını denetleme, yerleşik uygulamaları kullanma, kısıtlanmış veya onaylı uygulamalar ekleme, Bluetooth cihazlarını yönetme, yedekleme ve depolama amacıyla buluta bağlanma, bilgi noktası modunu etkinleştirme, etki alanı ekleme ve kullanıcıların Safari web tarayıcısıyla etkileşim kurma şeklini denetleme gibi özellikleri kısıtlama amacıyla Microsoft Intune'daki macOS cihazlar için ayar ekleme, yapılandırma veya oluşturma işlemlerini gerçekleştirin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/10/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: fb5fe19852ffff30566cb6758e156def3b7d64a5
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72494017"
---
# <a name="macos-device-settings-to-allow-or-restrict-features-using-intune"></a>Intune'u kullanarak özelliklere izin vermeyi veya bunları kısıtlamayı sağlayan macOS cihaz ayarları

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bu makalede macOS cihazlarda denetleyebileceğiniz farklı ayarlar listelenmekte ve açıklanmaktadır. Mobil cihaz yönetimi (MDM) yönteminizin bir parçası olarak bu ayarları kullanabilir ve bu sayede özellikleri etkinleştirip devre dışı bırakabilir, parola kuralları uygulayabilir, belirli uygulamalara izin verebilir veya bunları kısıtlayabilir ve çok daha fazlasını yapabilirsiniz.

Bu ayarlar, Intune'da bir cihaz yapılandırma profiline eklenir ve daha sonra macOS cihazlarınıza atanır veya dağıtılır.

## <a name="before-you-begin"></a>Başlamadan önce

[Cihaz kısıtlamaları yapılandırma profili oluşturma](../device-restrictions-configure.md).

> [!NOTE]
> Bu ayarlar farklı kayıt türleri için geçerlidir. Farklı kayıt türleri hakkında daha fazla bilgi için bkz. [MacOS kaydı](../macos-enroll.md).

## <a name="general"></a>Genel

### <a name="settings-apply-to-device-enrollment"></a>Ayarlar için geçerlidir: cihaz kaydı

- **Tanım arama**: **blok** , kullanıcının bir sözcüğü vurgulamasını ve sonra da cihazda tanımını aramasını engeller. **Yapılandırılmadı** (varsayılan) ayarı, tanım arama özelliğine erişim sağlar.
- **Dikte**: **blok** , kullanıcının metin girmesi için ses girişi kullanmasını engeller. **Yapılandırılmadı** (varsayılan) ayarı, kullanıcının dikteyle girişi kullanmasına izin verir.
- **İçerik önbelleğe alma**: içerik önbelleğe almayı etkinleştirmek için **Yapılandırılmadı** (varsayılan) seçeneğini belirleyin. İçeriği önbelleğe alma ayarı uygulama verilerini, web tarayıcısı verilerini, indirilen verileri ve daha fazlasını cihazda depolar. Bu verilerin önbellekte depolanmasını önlemek için **Engelle**'yi seçin.

  macOS cihazlarda içeriği önbelleğe alma özelliği hakkında daha fazla bilgi için bkz. [Mac'te içeriği önbelleğe almayı yönetme](https://support.apple.com/guide/mac-help/manage-content-caching-on-mac-mchl3b6c3720/mac) (başka bir web sitesini açar).

  Bu özellik şu platformlarda geçerlidir:  
  - macOS 10,13 ve üzeri

- **Yazılım güncelleştirmelerini ertele**: **Yapılandırılmadı** (varsayılan) olarak ayarlandığında, yazılım güncelleştirmeleri cihazda, Apple tarafından yayımlandığında görüntülenir. Örneğin Apple tarafından bir macOS güncelleştirmesinin yayımlanması durumunda ilgili güncelleştirme normal bir şekilde yayın tarihinde cihazda görünür. Çekirdek derleme güncelleştirmelerine gecikme olmadan izin verilir.

  **Etkinleştir** ayarını kullanarak güncelleştirmelerin cihazlarda gösterilmesini 0-90 gün boyunca geciktirebilirsiniz. Bu ayar, güncelleştirmelerin yüklenme tarihini veya durumunu denetlemez. 

  - **Yazılım güncelleştirmeleri gecikmesi**: 0-90 günden bir değer girin. Gecikme süresi sona erdiğinde kullanıcılara gecikmenin tetiklendiği tarihte kullanılabilir durumda olan en eski işletim sistemi sürümüne güncelleştirme bildirimi gönderilir.

    Örneğin, bir macOS güncelleştirmesi **1 Ocak**'ta kullanılabiliyorsa ve **gecikme görünürlüğü** **5 güne**ayarlanırsa, güncelleştirme kullanılabilir bir güncelleştirme olarak gösterilmez. Yayımlandıktan sonraki **altıncı günde** bu güncelleştirme kullanıma sunulur ve kullanıcılar tarafından yüklenebilir.

    Bu özellik şu platformlarda geçerlidir:  
    - macOS 10.13.4 ve üzeri

- **Ekran görüntüleri**: cihazın Apple 'ın otomatik cihaz kaydı 'NDA (DEP) kayıtlı olması gerekir. **Engelle**olarak ayarlandığında, kullanıcılar ekran ekran görüntüsünü kaydedemez. Ayrıca, derslik uygulamasının uzak ekranları gözlemmasını önler. **Yapılandırılmadı** (varsayılan), kullanıcıların ekran görüntülerini yakalamalarını sağlar ve derslik uygulamasının uzak ekranları görüntülemesine olanak tanır.

### <a name="settings-apply-to-automated-device-enrollment"></a>Ayarlar için geçerlidir: otomatik cihaz kaydı

- **Sınıf uygulaması aracılığıyla uzak ekran**izleme: **devre dışı bırakma** , öğretmenlerin öğrencilerin ekranlarını görmek için sınıf uygulamasını kullanmalarını önler. **Yapılandırılmadı** (varsayılan), öğretmenlerin öğrencilerinin ekranlarını görmesini sağlar.

  Bu ayarı kullanmak için **ekran görüntüleri** ayarını **Yapılandırılmadı** olarak ayarlayın (ekran görüntülerine izin verilir).

- **Sınıf uygulamasına göre sorulmadan ekran gözlemleyerek**, öğretmenlere öğrenci 'nin kabul etmesini gerektirmeden öğrencilerinin ekranlarını görmesine **izin** verir. **Yapılandırılmadı** (varsayılan), öğretmenin ekranları görebilmesi için öğrencinin kabul etmesi gerekir.

  Bu ayarı kullanmak için **ekran görüntüleri** ayarını **Yapılandırılmadı** olarak ayarlayın (ekran görüntülerine izin verilir).

- **Öğrenciler sınıf sınıfına ayrılmak için izin istemelidir**: bir yönetilmeyen sınıfta kayıtlı öğrencileri, kursu bırakmaya yönelik öğretmen onayı almak için **ister** . **Yapılandırılmadı** (varsayılan) öğrenciye her ne kadar her seçtiğinde, öğrencinin kursu bırakmasını sağlar.

- **Öğretmenler, sınıf uygulamasındaki cihazları veya uygulamaları otomatik olarak kilitleyebilir**: **izin ver** öğretmenlerin öğrencinin onayını almadan bir öğrencinin cihazını veya uygulamasını kilitlemesine olanak tanır. **Yapılandırılmadı** (varsayılan), öğretmenin cihazı veya uygulamayı kilitleyebilmesi için öğrencinin kabul etmesi gerekir.

- **Öğrenciler ders sınıfına otomatik olarak katılabilir**: **izin ver** , öğrenciye sormadan bir sınıfa katılmasına olanak sağlar. **Yapılandırılmadı** (varsayılan), bir sınıfa katılması için öğretmen onayını gerektirir.

## <a name="password"></a>Parola

### <a name="settings-apply-to-device-enrollment"></a>Ayarlar için geçerlidir: cihaz kaydı

- **Parola**: son kullanıcının cihaza erişmek için bir parola girmesini **gerektir** . **Yapılandırılmadı** (varsayılan) parola gerektirmez. Ayrıca basit parolaları engelleme veya minimum uzunluğu ayarlama gibi herhangi bir kısıtlamayı zorlamaz.
  - **Gerekli parola türü**: parolanın yalnızca sayısal olup olmayacağını ya da alfasayısal (harfler ve sayılar içeren) olması gerektiğini belirtin.

    Bu özellik şu platformlarda geçerlidir:  
    - macOS 10.10.3 ve üzeri

  - **Paroladaki alfasayısal olmayan karakter sayısı**: parolada gereken karmaşık karakter sayısını belirtin (**0** ile **4**arasında).<br>Karmaşık bir karakter, “ **?** ” gibi bir simgedir.
  - **Minimum parola uzunluğu**: bir kullanıcının yapılandırması gereken parola uzunluğu alt sınırını girin ( **4** ile **16** karakter arasında).
  - **Basit parolalar**: **0000** veya **1234**gibi basit parolaların kullanılmasına izin verin.
  - **Parola istenmeden önce ekran kilitlenmesinden sonra geçen en fazla dakika**: kilidini açmak için bir parola istenmeden önce bilgisayarın ne kadar süreyle devre dışı olması gerektiğini belirtin.
  - **Ekran kilitlenmeden önce geçen işlem yapılmayan dakika sayısı**: ekran kilitlenmeden önce bilgisayarın boşta olması gereken sürenin uzunluğunu belirtin.
  - **Parola kullanım süresi (gün)** : kullanıcının parolayı değiştirmesi gereken gün sayısını belirtin (**1** ile **255** gün arasında).
  - **Önceki parolaların yeniden kullanılmasını engelle**: daha önce kullanılan parolaların sayısını **1** ile **24**arasında girin.

- **Kullanıcının geçiş kodunu değiştirmesini engelle**: geçiş kodunun değiştirilmesini, eklenmesini veya kaldırılmasını durdurmak için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan) ayarı, geçiş kodu ekleme, değiştirme veya kaldırma işlemlerine izin verir.
- **Parmak Iziyle kilidi açma 'Yı engelle**: cihazın kilidini açmak için parmak izi kullanmayı engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan) ayarı, kullanıcının cihaz kilidini parmak izi kullanarak açmasını sağlar.

- **Parola Otomatik doldurmayı engelle**: MacOS 'Ta parolaları otomatik doldur özelliğinin kullanılmasını engellemek için **Engelle** ' yi seçin. **Engelle** ayarını seçmek şu sonuçlara da neden olur:

  - Safari'de veya diğer uygulamalarda kullanıcılara parolaları kaydetmek isteyip istemedikleri sorulmaz.
  - Otomatik Güçlü Parolalar devre dışı bırakılır ve kullanıcılara güçlü parola önerisi sunulmaz.

  **Yapılandırılmadı** (varsayılan) ayarı bu özelliklere izin verir.

- **Parola yakınlık Isteklerini engelle**: bir kullanıcının cihazının yakındaki cihazlardan parola Isteyememesi için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan) ayarı bu parola isteklerine izin verir.

- **Parola paylaşmayı engelle**: **blok** , AirDrop kullanan cihazlar arasında parolaların paylaşılmasını önler. **Yapılandırılmadı** (varsayılan) ayarı, parolaların paylaşılmasına izin verir.

## <a name="built-in-apps"></a>Yerleşik Uygulamalar

### <a name="settings-apply-to-device-enrollment"></a>Ayarlar için geçerlidir: cihaz kaydı

- **Safari Safari otomatik doldurma**: **blok** cihazdaki otomatik doldurma özelliğini devre dışı bırakır. **Yapılandırılmadı** (varsayılan) ayarı, kullanıcıların web tarayıcısındaki otomatik tamamlama ayarlarını değiştirmesine olanak tanır.
- **Kamerayı engelle**: cihazdaki kameraya erişimi engellemek için **Engelle** ' yi seçin. **Yapılandırılmadı** (varsayılan) ayarı, cihazın kamerasına erişim sağlar.
- **Engelle Apple Music**: **blok** , müzik uygulamasını klasik moda geri döndürür ve müzik hizmetini devre dışı bırakır. **Yapılandırılmadı** (varsayılan) ayarı, Apple Music uygulamasının kullanılmasına izin verir.
- **Spotlight Internet araması sonuçlarını engelle**: **blok** , projektörün bir Internet aramasından sonuçları döndürmesini durduruyor. **Yapılandırılmadı** (varsayılan) ayarı, Spotlight'ın internete bağlanarak arama sonuçlarını getirmesine izin verir.
- **İTunes kullanarak dosya aktarımını engelle**: **blok** uygulama dosya paylaşımı hizmetlerini devre dışı bırakır. **Yapılandırılmadı** (varsayılan), uygulama dosya paylaşım hizmetlerine izin verir.

  Bu özellik şu platformlarda geçerlidir:  
  - macOS 10,13 ve üzeri

## <a name="restricted-apps"></a>Kısıtlı uygulamalar

### <a name="settings-apply-to-device-enrollment"></a>Ayarlar için geçerlidir: cihaz kaydı

- **Kısıtlanmış uygulamalar listesi türü**: Kullanıcıların yüklemesine veya kullanmasına izin verilmeyen uygulamaların bir listesini oluşturun. Seçenekleriniz şunlardır:

  - **Yapılandırılmadı** (varsayılan): Intune 'dan bir kısıtlama yoktur. Kullanıcıların atadığınız uygulamalara ve yerleşik uygulamalarına erişimi vardır.
  - **Yasaklanmış uygulamalar**: Intune tarafından yönetilmeyen ve cihaza yüklenmesini istemediğiniz uygulamalar. Kullanıcıların yasaklanmış bir uygulamayı yüklemesi engellenmiyor. Ancak bir Kullanıcı bu listeden bir uygulama yüklerse Intune 'da raporlanır.
  - **Onaylanan uygulamalar**: Kullanıcıların yüklemesine izin verilen uygulamalar. Kullanıcılar listelenmeyen uygulamaları yüklememelidir. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir. Kullanıcıların onaylı uygulamalar listesinde olmayan bir uygulamayı yüklenmesi engellenmez. Ancak bunu yaptıysanız Intune 'da raporlanır.
- **Uygulama PAKETI kimliği**: istediğiniz uygulamanın uygulama [paket kimliğini](bundle-ids-built-in-ios-apps.md) girin. Yerleşik uygulamaları ve iş kolu uygulamalarını gösterebilir veya gizleyebilirsiniz. Apple 'ın Web sitesinde [yerleşik bir Apple Apps](https://support.apple.com/HT208094)listesi bulunur.
- **Uygulama adı**: istediğiniz uygulamanın uygulama adını girin. Yerleşik uygulamaları ve iş kolu uygulamalarını gösterebilir veya gizleyebilirsiniz. Apple 'ın Web sitesinde [yerleşik bir Apple Apps](https://support.apple.com/HT208094)listesi bulunur.
- **Yayımcı**: istediğiniz uygulamanın yayımcısını girin.

Bu listelere uygulama eklemek için şunları yapabilirsiniz:

- **Ekle**: uygulama listenizi oluşturmak için seçin.
- URL 'SI dahil olmak üzere uygulamayla ilgili ayrıntılarla bir CSV dosyasını **Içeri aktarın** . `<app bundle ID>, <app name>, <app publisher>` biçimini kullanın. Ya da, eklediğiniz uygulamaların bir listesini aynı biçimde oluşturmak için **dışa aktarın** .

## <a name="connected-devices"></a>Bağlı cihazlar

### <a name="settings-apply-to-device-enrollment"></a>Ayarlar için geçerlidir: cihaz kaydı

- **AirDrop bloğu**: **Block** cihazda AirDrop kullanımını engeller. **Yapılandırılmadı** (varsayılan) ayarı, yakındaki cihazlarla içerik değişimi için AirDrop özelliğinin kullanılmasına izin verir.
- **Apple Watch otomatik kilit açma engelle**: **Block** , kullanıcıların MacOS cihazını Apple Watch kilidini açmalarını engeller. **Yapılandırılmadı** (varsayılan) ayarı, kullanıcıların Apple Watch cihazlarıyla macOS cihazlarının kilidini açmalarına izin verir.

## <a name="cloud-and-storage"></a>Bulut ve depolama

### <a name="settings-apply-to-device-enrollment"></a>Ayarlar için geçerlidir: cihaz kaydı

- **ICloud anahtar zinciri eşitlemesini engelle**: anahtarlıkta depolanan kimlik bilgilerinin iCloud 'a eşitlenmesini devre dışı bırakmak için **bloğu** seçin. **Yapılandırılmadı** (varsayılan), kullanıcıların bu kimlik bilgilerini eşitlemesine izin verir.
- **ICloud belge eşitlemesini engelle**: **blok** , iCloud 'ın belge ve verileri eşitlemesini engeller. **Yapılandırılmadı** (varsayılan), iCloud depolama alanınızda belge ve anahtar-değer eşitlemesine izin verir.
- **ICloud posta yedeklemesini engelle**: **blok** , ICloud 'ın MacOS posta uygulamasıyla eşitlenmesini önler. **Yapılandırılmadı** (varsayılan) ayarı, iCloud ile Posta eşitlemesine izin verir.
- **İCloud 'La Iletişim yedeklemeyi engelle**: **blok** , iCloud 'ın cihaz kişilerini eşitlemesini engeller. **Yapılandırılmadı** (varsayılan) ayarı, iCloud ile kişi eşitlemesine izin verir.
- **ICloud takvim yedeklemesini engelle**: **blok** , ICloud 'ın MacOS Takvim uygulamasıyla eşitlenmesini engeller. **Yapılandırılmadı** (varsayılan) ayarı, iCloud ile Takvim eşitlemesine izin verir.
- **ICloud anımsatıcı yedeklemesini engelle**: **blok** , ICloud 'ın MacOS anımsatıcıları uygulamasıyla eşitlenmesini engeller. **Yapılandırılmadı** (varsayılan) ayarı, iCloud ile Anımsatıcılar eşitlemesine izin verir.
- **ICloud yer Işareti yedeklemesini engelle**: **blok** , ICloud 'ın cihaz yer imlerini eşitlemesini önler. **Yapılandırılmadı** (varsayılan) ayarı, iCloud ile Yer İşareti eşitlemesine izin verir.
- **ICloud notları yedeklemesini engelle**: **blok** , iCloud 'ın cihaz notlarını eşitlemesini önler. **Yapılandırılmadı** (varsayılan) ayarı, iCloud ile not eşitlemesine izin verir.
- **ICloud Fotoğraf kitaplığını engelle**: **blok** iCloud Fotoğraf kitaplığını devre dışı bırakır ve iCloud 'ın cihaz fotoğraflarını eşitlemesini önler. İCloud fotoğraf kitaplığından tamamen indirilmeyen tüm fotoğraflar cihazdaki yerel depolama alanından kaldırılır. **Yapılandırılmadı** (varsayılan), cihaz Ile ICloud Fotoğraf Kitaplığı arasında fotoğrafların eşitlenmesine izin verir.
- **İletim**: **Yapılandırılmadı** (varsayılan), kullanıcıların bir MacOS cihazında iş başlatmasını sağlar ve sonra başka bir iOS veya MacOS cihazında başlattıkları çalışmaya devam eder. **Blok** , cihazdaki iletim özelliğini engeller. 

  Bu özellik şu platformlarda geçerlidir:  
  - macOS 10,15 ve üzeri

## <a name="domains"></a>Domains

### <a name="settings-apply-to-device-enrollment"></a>Ayarlar için geçerlidir: cihaz kaydı

- **E-posta etki alanı URL 'si**: listeye bir veya daha fazla URL **ekleyin** . Kullanıcılar, yapılandırdığınız sunucudan farklı bir etki alanından e-posta aldıklarında, macOS Mail uygulamasında e-posta güvenilir değil olarak işaretlenir.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](../device-profile-assign.md) ve [durumunu izleme](../device-profile-monitor.md).

[iOS](../device-restrictions-ios.md) cihazlardaki özellikleri ve ayarları da kısıtlayabilirsiniz.
