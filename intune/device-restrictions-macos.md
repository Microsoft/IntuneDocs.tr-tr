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
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d32224581c16325f0b060608409aa422cbf49d90
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2019
ms.locfileid: "71302368"
---
# <a name="macos-device-settings-to-allow-or-restrict-features-using-intune"></a>Intune'u kullanarak özelliklere izin vermeyi veya bunları kısıtlamayı sağlayan macOS cihaz ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makalede macOS cihazlarda denetleyebileceğiniz farklı ayarlar listelenmekte ve açıklanmaktadır. Mobil cihaz yönetimi (MDM) yönteminizin bir parçası olarak bu ayarları kullanabilir ve bu sayede özellikleri etkinleştirip devre dışı bırakabilir, parola kuralları uygulayabilir, belirli uygulamalara izin verebilir veya bunları kısıtlayabilir ve çok daha fazlasını yapabilirsiniz.

Bu ayarlar, Intune'da bir cihaz yapılandırma profiline eklenir ve daha sonra macOS cihazlarınıza atanır veya dağıtılır.

## <a name="before-you-begin"></a>Başlamadan önce

[Cihaz kısıtlamaları yapılandırma profili oluşturma](device-restrictions-configure.md).

> [!NOTE]
> Bu ayarlar farklı kayıt türleri için geçerlidir. Farklı kayıt türleri hakkında daha fazla bilgi için bkz. [MacOS kaydı](macos-enroll.md).

## <a name="general"></a>Genel

### <a name="settings-apply-to-device-enrollment"></a>Ayarlar için geçerlidir: Cihaz kaydı

- **Tanım arama**: **Engelle** ayarı kullanıcının belirli bir sözcüğü vurgulayıp cihazda tanımını aramasını engeller. **Yapılandırılmadı** (varsayılan) ayarı, tanım arama özelliğine erişim sağlar.
- **Dikte**: **Engelle** ayarı kullanıcının metin girmek için sesli giriş kullanmasını durdurur. **Yapılandırılmadı** (varsayılan) ayarı, kullanıcının dikteyle girişi kullanmasına izin verir.
- **İçerik önbelleğe alma**: İçeriğin önbelleğe alınmasını etkinleştirmek için **Yapılandırılmadı** (varsayılan) ayarını seçin. İçeriği önbelleğe alma ayarı uygulama verilerini, web tarayıcısı verilerini, indirilen verileri ve daha fazlasını cihazda depolar. Bu verilerin önbellekte depolanmasını önlemek için **Engelle**'yi seçin.

  macOS cihazlarda içeriği önbelleğe alma özelliği hakkında daha fazla bilgi için bkz. [Mac'te içeriği önbelleğe almayı yönetme](https://support.apple.com/guide/mac-help/manage-content-caching-on-mac-mchl3b6c3720/mac) (başka bir web sitesini açar).

  Bu özellik şu platformlarda geçerlidir:  
  - macOS 10,13 ve üzeri

- **Yazılım güncelleştirmelerini ertele**: **Yapılandırılmadı** (varsayılan) olarak ayarlandığında Apple tarafından yayımlanan yazılım güncelleştirmeleri anında cihazda gösterilir. Örneğin Apple tarafından bir macOS güncelleştirmesinin yayımlanması durumunda ilgili güncelleştirme normal bir şekilde yayın tarihinde cihazda görünür. Çekirdek derleme güncelleştirmelerine gecikme olmadan izin verilir.

  **Etkinleştir** ayarını kullanarak güncelleştirmelerin cihazlarda gösterilmesini 0-90 gün boyunca geciktirebilirsiniz. Bu ayar, güncelleştirmelerin yüklenme tarihini veya durumunu denetlemez. 

  - **Yazılım güncelleştirmelerinin görünürlüğünü geciktir**: 0-90 gün arasında bir değer girin. Gecikme süresi sona erdiğinde kullanıcılara gecikmenin tetiklendiği tarihte kullanılabilir durumda olan en eski işletim sistemi sürümüne güncelleştirme bildirimi gönderilir.

    Örneğin, bir macOS güncelleştirmesi **1 Ocak**'ta kullanılabiliyorsa ve **gecikme görünürlüğü** **5 güne**ayarlanırsa, güncelleştirme kullanılabilir bir güncelleştirme olarak gösterilmez. Yayımlandıktan sonraki **altıncı günde** bu güncelleştirme kullanıma sunulur ve kullanıcılar tarafından yüklenebilir.

    Bu özellik şu platformlarda geçerlidir:  
    - macOS 10.13.4 ve üzeri

- **Ekran görüntüleri**: Cihazın Apple 'ın otomatik cihaz kaydı 'nda (DEP) kayıtlı olması gerekir. **Engelle**olarak ayarlandığında, kullanıcılar ekran ekran görüntüsünü kaydedemez. Ayrıca, derslik uygulamasının uzak ekranları gözlemmasını önler. **Yapılandırılmadı** (varsayılan) kullanıcıların ekran görüntülerini yakalamalarını sağlar ve derslik uygulamasının uzak ekranları görüntülemesine olanak tanır.

### <a name="settings-apply-to-automated-device-enrollment"></a>Ayarlar için geçerlidir: Otomatik cihaz kaydı

- **Sınıf uygulaması aracılığıyla uzak ekran Gözlemliği**: **Devre dışı bırak** , öğretmenlerin öğrencilerin ekranlarını görmek için sınıf uygulamasını kullanmalarını önler. **Yapılandırılmadı** (varsayılan) öğretmenlerin öğrencilerinin ekranlarını görmesini sağlar.

  Bu ayarı kullanmak için **ekran görüntüleri** ayarını **Yapılandırılmadı** olarak ayarlayın (ekran görüntülerine izin verilir).

- **Sınıf uygulamasına göre sorulmayacak ekran izleme**: **Izin ver** , öğretmenlere öğrenciye gerek duymadan öğrencilerinin ekranlarını görmesine imkan tanır. **Yapılandırılmadı** (varsayılan), öğretmenin ekranları görebilmesi için öğrencinin kabul etmesi gerekir.

  Bu ayarı kullanmak için **ekran görüntüleri** ayarını **Yapılandırılmadı** olarak ayarlayın (ekran görüntülerine izin verilir).

- **Öğrenciler sınıf sınıfından ayrılmak için izin istemelidir**: , Yönetilmeyen bir sınıfta kayıtlı öğrencileri kurs bırakmaya yönelik öğretmeye onay almak için izin **ister** . **Yapılandırılmadı** (varsayılan) öğrenciye her seçtiğinde öğrenciye ayrılın.

- **Öğretmenler, sınıf uygulamasındaki cihazları veya uygulamaları otomatik olarak kilitleyebilir**: **Izin ver** , öğretmenlerin öğrencinin onayını almadan bir öğrencinin cihazını veya uygulamasını kilitlemesine olanak tanır. **Yapılandırılmadı** (varsayılan), öğretmenin cihazı veya uygulamayı kilitleyebilmesi için öğrencinin kabul etmesi gerekir.

- **Öğrenciler, sınıf sınıfına otomatik olarak katılabilir**: **Izin ver** , öğrencilerin öğretmeden bir sınıfa katılmasına olanak sağlar. **Yapılandırılmadı** (varsayılan) bir sınıfa katmak için öğretmen onayını gerektirir.

## <a name="password"></a>istemcisiyle yönetilen bir cihaz için)

### <a name="settings-apply-to-device-enrollment"></a>Ayarlar için geçerlidir: Cihaz kaydı

- **Parola**: **Gerekli** ayarı son kullanıcının cihaza erişmek için parola girmesini zorunlu tutar. **Yapılandırılmadı** (varsayılan) parola gerektirmez. Ayrıca basit parolaları engelleme veya minimum uzunluğu ayarlama gibi herhangi bir kısıtlamayı zorlamaz.
  - **Gerekli parola türü**: Parolanın yalnızca Sayısal olabileceğini ya da Alfasayısal (harfler ve sayılar içeren) olması gerektiğini belirtin.

    Bu özellik şu platformlarda geçerlidir:  
    - macOS 10.10.3 ve üzeri

  - **Paroladaki alfasayısal olmayan karakter sayısı**: Parolada kullanılması gereken karmaşık karakterlerin sayısını belirtin (**0**-**4** karakter).<br>Karmaşık bir karakter, “ **?** ” gibi bir simgedir.
  - **Minimum parola uzunluğu**: Kullanıcının yapılandırması gereken parolanın uzunluk alt sınırını girin (**4** ile **16** karakter arasında).
  - **Basit parolalar**: **0000** veya **1234** gibi basit parolaların kullanımına izin verin.
  - **Ekran kilitlendikten sonra parola istenene kadar geçmesi gereken, işlem yapılmayan dakika sayısı**: Bilgisayarın ne kadar süreyle etkinlik dışı kaldıktan sonra kilidinin açılması için bir parolanın gerekli olacağını belirtin.
  - **Ekran kilitlenmeden önce geçmesi gereken, işlem yapılmayan dakika sayısı**: Ekran kilitlenmeden önce bilgisayarın boşta bekleyeceği süreyi belirtir.
  - **Parola kullanım süresi (gün olarak)** : Kullanıcının kaç gün geçtikten sonra parolayı değiştirmesi gerekeceğini belirtin (**1**-**255** gün).
  - **Önceki parolaların yeniden kullanılmasını engelle**: Daha önce kullanılan kaç parolanın yeniden kullanılamayacağını belirtin (**1** ile **24** arası).

- **Kullanıcının Geçiş Kodunu Değiştirmesini Engelle**: Geçiş kodu değiştirme, ekleme veya kaldırma işlemlerini önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı, geçiş kodu ekleme, değiştirme veya kaldırma işlemlerine izin verir.
- **Parmak İzi ile Kilit Açmayı Engelle**: Cihaz kilidinin parmak izi kullanarak açılmasını önlemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı, kullanıcının cihaz kilidini parmak izi kullanarak açmasını sağlar.

- **Parola Otomatik Doldurmayı engelle**: macOS Parola Otomatik Doldurma özelliğini engellemek için **Engelle**'yi seçin. **Engelle** ayarını seçmek şu sonuçlara da neden olur:

  - Safari'de veya diğer uygulamalarda kullanıcılara parolaları kaydetmek isteyip istemedikleri sorulmaz.
  - Otomatik Güçlü Parolalar devre dışı bırakılır ve kullanıcılara güçlü parola önerisi sunulmaz.

  **Yapılandırılmadı** (varsayılan) ayarı bu özelliklere izin verir.

- **Parola yakınlık isteklerini engelle**: **Engelle**'yi seçtiğinizde kullanıcının cihazı yakınlardaki cihazlardan parola isteyemez. **Yapılandırılmadı** (varsayılan) ayarı bu parola isteklerine izin verir.

- **Parola paylaşımını engelle**: **Engelle**, AirDrop ile cihazlar arasında parola paylaşımı yapılmasını engeller. **Yapılandırılmadı** (varsayılan) ayarı, parolaların paylaşılmasına izin verir.

## <a name="built-in-apps"></a>Yerleşik Uygulamalar

### <a name="settings-apply-to-device-enrollment"></a>Ayarlar için geçerlidir: Cihaz kaydı

- **Safari Otomatik Doldurmayı engelle**: **Engelle** ayarı, cihazdaki Safari uygulamasında otomatik doldurma özelliğini devre dışı bırakır. **Yapılandırılmadı** (varsayılan) ayarı, kullanıcıların web tarayıcısındaki otomatik tamamlama ayarlarını değiştirmesine olanak tanır.
- **Kamerayı engelle**: Cihazdaki kameraya erişim sağlanmasını engellemek için **Engelle**'yi seçin. **Yapılandırılmadı** (varsayılan) ayarı, cihazın kamerasına erişim sağlar.
- **Apple Music'i engelle**: **Engelle** ayarı, Müzik uygulamasını klasik moda döndürür ve Müzik hizmetini devre dışı bırakır. **Yapılandırılmadı** (varsayılan) ayarı, Apple Music uygulamasının kullanılmasına izin verir.
- **Spotlight İnternet Araması Sonuçlarını Engelle**: **Engelle** ayarı, Spotlight'ın İnternet araması sonuçlarını döndürmesini engeller. **Yapılandırılmadı** (varsayılan) ayarı, Spotlight'ın internete bağlanarak arama sonuçlarını getirmesine izin verir.
- **iTunes kullanarak dosya aktarımı yapılmasını engelleyin**: **Engelle**, uygulama dosya paylaşım hizmetlerini devre dışı bırakır. **Yapılandırılmadı** (varsayılan), uygulama dosya paylaşım hizmetlerine izin verir.

  Bu özellik şu platformlarda geçerlidir:  
  - macOS 10,13 ve üzeri

## <a name="restricted-apps"></a>Kısıtlı uygulamalar

### <a name="settings-apply-to-device-enrollment"></a>Ayarlar için geçerlidir: Cihaz kaydı

- **Kısıtlanmış uygulamalar listesi türü**: Kullanıcıların yüklemesine veya kullanmasına izin verilmeyen uygulamaların bir listesini oluşturun. Seçenekleriniz şunlardır:

  - **Yapılandırılmadı** (varsayılan): Intune 'dan bir kısıtlama yoktur. Kullanıcıların atadığınız uygulamalara ve yerleşik uygulamalarına erişimi vardır.
  - **Yasak uygulamalar**: Intune tarafından yönetilmeyen ve cihaza yüklenmesini istemediğiniz uygulamalar. Kullanıcıların yasaklanmış bir uygulamayı yüklemesi engellenmiyor. Ancak bir Kullanıcı bu listeden bir uygulama yüklerse Intune 'da raporlanır.
  - **Onaylı uygulamalar**: Kullanıcıların yüklemesine izin verilen uygulamalar. Kullanıcılar listelenmeyen uygulamaları yüklememelidir. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir. Kullanıcıların onaylı uygulamalar listesinde olmayan bir uygulamayı yüklenmesi engellenmez. Ancak bunu yaptıysanız Intune 'da raporlanır.
- **Uygulama Paketi Kimliği**: İstediğiniz uygulamanın uygulama [paket kimliğini](bundle-ids-built-in-ios-apps.md) girin. Yerleşik uygulamaları ve iş kolu uygulamalarını gösterebilir veya gizleyebilirsiniz. Apple 'ın Web sitesinde [yerleşik bir Apple Apps](https://support.apple.com/HT208094)listesi bulunur.
- **Uygulama adı**: İstediğiniz uygulamanın uygulama adını girin. Yerleşik uygulamaları ve iş kolu uygulamalarını gösterebilir veya gizleyebilirsiniz. Apple 'ın Web sitesinde [yerleşik bir Apple Apps](https://support.apple.com/HT208094)listesi bulunur.
- **Yayımcı**: İstediğiniz uygulamanın yayımcısını girin.

Bu listelere uygulama eklemek için şunları yapabilirsiniz:

- **Ekle**: Uygulama listenizi oluşturmak için seçin.
- URL 'SI dahil olmak üzere uygulamayla ilgili ayrıntılarla bir CSV dosyasını **Içeri aktarın** . `<app bundle ID>, <app name>, <app publisher>` biçimini kullanın. Ya da, eklediğiniz uygulamaların bir listesini aynı biçimde oluşturmak için **dışa aktarın** .

## <a name="connected-devices"></a>Bağlı cihazlar

### <a name="settings-apply-to-device-enrollment"></a>Ayarlar için geçerlidir: Cihaz kaydı

- **AirDrop'u engelleyin**: **Engelle** ayarı, cihazdaki AirDrop özelliğinin kullanılmasını engeller. **Yapılandırılmadı** (varsayılan) ayarı, yakındaki cihazlarla içerik değişimi için AirDrop özelliğinin kullanılmasına izin verir.
- **Apple Watch ile otomatik kilit açmayı engelleyin**: **Engelle** ayarı, kullanıcıların Apple Watch cihazlarıyla macOS cihazlarının kilidini açmalarını engeller. **Yapılandırılmadı** (varsayılan) ayarı, kullanıcıların Apple Watch cihazlarıyla macOS cihazlarının kilidini açmalarına izin verir.

## <a name="cloud-and-storage"></a>Bulut ve depolama

### <a name="settings-apply-to-device-enrollment"></a>Ayarlar için geçerlidir: Cihaz kaydı

- **iCloud Anahtar Zinciri eşitlemesini engelle**: **Engelle**'yi seçtiğinizde Anahtar Zincirinde depolanan kimlik bilgilerinin iCloud ile eşitlenmesi devre dışı bırakılır. **Yapılandırılmadı** (varsayılan), kullanıcıların bu kimlik bilgilerini eşitlemesine izin verir.
- **iCloud Belge Eşitlemesini Engelle**: **Engelle** ayarı, iCloud'ın belgeleri ve verileri eşitlemesini engeller. **Yapılandırılmadı** (varsayılan), iCloud depolama alanınızda belge ve anahtar-değer eşitlemesine izin verir.
- **iCloud Posta Yedeklemesini Engelle**: **Engelle** ayarı, macOS Posta uygulamasıyla iCloud arasında eşitleme yapılmasını engeller. **Yapılandırılmadı** (varsayılan) ayarı, iCloud ile Posta eşitlemesine izin verir.
- **iCloud Kişi Yedeklemesini Engelle**: **Engelle** ayarı, cihazlardaki kişilerin iCloud ile eşitlenmesini engeller. **Yapılandırılmadı** (varsayılan) ayarı, iCloud ile kişi eşitlemesine izin verir.
- **iCloud Takvim Yedeklemesini Engelle**: **Engelle** ayarı, macOS Takvim uygulamasıyla iCloud arasında eşitleme yapılmasını engeller. **Yapılandırılmadı** (varsayılan) ayarı, iCloud ile Takvim eşitlemesine izin verir.
- **iCloud Anımsatıcı Yedeklemesini Engelle**: **Engelle** ayarı, macOS Anımsatıcılar uygulamasıyla iCloud arasında eşitleme yapılmasını engeller. **Yapılandırılmadı** (varsayılan) ayarı, iCloud ile Anımsatıcılar eşitlemesine izin verir.
- **iCloud Yer İşareti Yedeklemesini Engelle**: **Engelle** ayarı, cihazlardaki yer işaretlerinin iCloud ile eşitlenmesini engeller. **Yapılandırılmadı** (varsayılan) ayarı, iCloud ile Yer İşareti eşitlemesine izin verir.
- **iCloud Not Yedeklemesini Engelle**: **Engelle** ayarı, cihazlardaki notların iCloud ile eşitlenmesini engeller. **Yapılandırılmadı** (varsayılan) ayarı, iCloud ile not eşitlemesine izin verir.
- **ICloud Fotoğraf kitaplığını engelle**: **Blok** ICloud Fotoğraf kitaplığını devre dışı bırakır ve iCloud 'ın cihaz fotoğraflarını eşitlemesini önler. İCloud fotoğraf kitaplığından tamamen indirilmeyen tüm fotoğraflar cihazdaki yerel depolama alanından kaldırılır. **Yapılandırılmadı** (varsayılan) cihaz ile iCloud Fotoğraf Kitaplığı arasında fotoğrafların eşitlenmesine izin verir.
- **İletim**: **Yapılandırılmadı** (varsayılan), kullanıcıların bir macOS cihazında çalışmaya başlamasını sağlar ve sonra başka bir iOS veya macOS cihazında başlatıldıklarında çalışmaya devam eder. **Blok** , cihazdaki iletim özelliğini engeller. 

  Bu özellik şu platformlarda geçerlidir:  
  - macOS 10,15 ve üzeri

## <a name="domains"></a>Etki Alanları

### <a name="settings-apply-to-device-enrollment"></a>Ayarlar için geçerlidir: Cihaz kaydı

- **E-posta Etki Alanı URL'si**: Listeye bir veya daha fazla URL **ekleyin** . Kullanıcılar, yapılandırdığınız sunucudan farklı bir etki alanından e-posta aldıklarında, macOS Mail uygulamasında e-posta güvenilir değil olarak işaretlenir.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).

[iOS](device-restrictions-ios.md) cihazlardaki özellikleri ve ayarları da kısıtlayabilirsiniz.
