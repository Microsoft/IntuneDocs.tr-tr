---
title: Microsoft Intune - Azure'da macOS cihaz ayarları | Microsoft Docs
titleSuffix: ''
description: Ekle, yapılandırmak veya macOS cihazlarda parola gereksinimlerini ayarlama dahil olmak üzere kısıtlamanıza ayarlarını oluşturun, kilit ekranı kontrol, yerleşik uygulamaları kullanın, kısıtlanmış veya onaylı uygulamalar ekleme, bluetooth cihazların işlemek, yedekleme için buluta bağlayın ve Depolama, bilgi noktası modu etkinleştirme, etki alanlarını ekleyin ve kullanıcıların Microsoft Intune Safari web tarayıcısı ile nasıl etkileşim denetim.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/13/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5feec66e791da4038bd069cdad69a7ba573f27f3
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58798386"
---
# <a name="macos-device-settings-to-allow-or-restrict-features-using-intune"></a>izin verme veya kısıtlamanıza Intune kullanarak macOS cihaz ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makalede, listeler ve macOS cihazlarda denetleyebileceğiniz farklı ayarlar açıklanır. Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, izin veya özellikleri devre dışı bırakabilir, parola kuralları, izin veya belirli uygulamalar ve daha fazlasını sınırlamak için bu ayarları kullanın.

Bu ayarlar, ıntune'da cihaz yapılandırma profili eklenir ve ardından atanan veya macOS cihazlarına dağıtılabilir.

## <a name="before-you-begin"></a>Başlamadan önce

[Cihaz kısıtlamalarını yapılandırma profili oluşturma](device-restrictions-configure.md#create-the-profile).

## <a name="general"></a>Genel

- **Tanım aramaya Block**: **Blok** kullanıcının bir word vurgulama ve sonra cihazdaki tanımı bakarak engeller. **Yapılandırılmamış** (varsayılan) tanımına arama özelliğini erişim sağlar.
- **Block dikte**: **Blok** kullanıcının sesli metin girmek için giriş yapmasını durdurur. **Yapılandırılmamış** (varsayılan), kullanıcının dikte girişini kullanmasını sağlar.
- **İçeriği önbelleğe alma block**: Seçin **yapılandırılmadı** içerik önbelleğe almayı etkinleştirmek için (varsayılan). İçeriği önbelleğe alma, uygulama verilerini, web tarayıcı verilerini, indirmeler ve daha fazla yerel olarak cihazda depolar. Seçin **blok** önbellekte depolanır, bu verileri önlemek için.

  Macos'ta içeriği önbelleğe alma ile ilgili daha fazla bilgi için bkz: [Mac üzerinde içerik önbelleğe alınmasını yönetin](https://support.apple.com/guide/mac-help/manage-content-caching-on-mac-mchl3b6c3720/mac) (başka bir Web sitesini açar).

  Bu özellik şu platformlarda geçerlidir:  
  - macOS 10.13 ve üzeri

- **Yazılım güncelleştirmelerinin erteleneceği**: Ayarlandığında **yapılandırılmadı** (varsayılan), yazılım güncelleştirmeleri gösterilir cihazda gibi Apple onları serbest bırakır. Bir macOS güncelleştirmesini Apple tarafından belirli bir tarihte yayımlanan, örneğin, sonra bu güncelleştirmeyi doğal olarak yayın tarihindeki cihazda gösterilir. Çekirdek derleme güncelleştirmeleri gecikme olmadan izin verilir.

  **Etkinleştirme** 0-90 güne ait cihazlarda yazılım güncelleştirmeleri gösterilirken gecikme sağlar. Bu ayar, güncelleştirmeler veya yüklü olmayan denetlemez. 

  - **Yazılım güncelleştirmelerini görünürlüğünü gecikme**: 0-90 gün arasında bir değer girin. Gecikme süresi dolduğunda kullanıcılar gecikme tetiklendiğinde erken kullanılabilir işletim sistemi sürümüne güncelleştirmek için bildirim alın.

    Örneğin, bir macOS güncelleştirme kullanılabilir ise **1 Ocak**, ve **gecikme görünürlük** ayarlanır **5 gün**, sonra güncelleştirmeyi, cihazlarda kullanılabilir bir güncelleştirme olarak gösterilmiyor. Üzerinde **altıncı gün** sürümünden güncelleştirmesi kullanıma sunuldu ve son kullanıcılar da yükleyebilirsiniz.

    Bu özellik şu platformlarda geçerlidir:  
    - macOS 10.13.4 ve üzeri

## <a name="password"></a>istemcisiyle yönetilen bir cihaz için)

- **Parola**: **Gerekli** son kullanıcının cihaza erişmek için bir parola girin. **Yapılandırılmamış** (varsayılan), bir parola gerektirmez ve basit parolalar engelleme veya en düşük uzunluğunu ayarlama gibi kısıtlamalar zorlamaz.
  - **Gerekli parola türü**: Olup parolanın yalnızca sayısal olabileceğini ya da alfasayısal olması gerektiğini belirtin (harfler ve sayılar içeren). Bu ayar yalnızca Mac OS X sürüm 10.10.3 ve üzerinde desteklenir.
  - **Paroladaki alfasayısal olmayan karakter sayısı**: Parolada kullanılması gereken karmaşık karakterlerin sayısını belirtin (**0**-**4** karakter).<br>Karmaşık bir karakter, “**?**” gibi bir simgedir.
  - **Minimum parola uzunluğu**: Kullanıcının yapılandırması gereken parolanın uzunluk alt sınırını girin (arasında **4** ve **16** karakter).
  - **Basit parolalar**: **0000** veya **1234** gibi basit parolaların kullanımına izin verin.
  - **Parola istenmeden önce ekran kilitlendikten sonra en fazla dakika**: Bilgisayarın ne kadar süreyle etkinlik dışı kaldıktan sonra kilidinin açılması için bir parolanın gerekli olacağını belirtin.
  - **Ekran kilitlenmeden işlem yapılmayan dakika**: Bilgisayar ekran kilitlenmeden önce boşta bekleyeceği süreyi belirtin.
  - **Parola süresinin sonu (gün)**: Kullanıcının kaç gün geçtikten sonra parolayı değiştirmesi gerekeceğini belirtin (**1**-**255** gün).
  - **Önceki parolaların yeniden kullanılmasını engelle**: Kullanılamayacak, önceden kullanılmış parola sayısını girin gelen **1** için **24**.

- **Kullanıcı parolasını değiştirmesini engelleyin**: Seçin **blok** eklenen veya kaldırılan değiştirilmesini geçiş kodunu durdurmak için. **Yapılandırılmamış** (varsayılan) eklenmesine, değiştirilmesine veya kaldırılması geçiş kodlarını sağlar.
- **Blok parmak iziyle kilit açma**: Seçin **blok** cihazın kilidini açmak için parmak izi'ni kullanarak önlemek için. **Yapılandırılmamış** (varsayılan), parmak izi kullanarak cihaz kilidini açmak kullanıcının sağlar.

- **Blok parola otomatik doldurma**: Seçin **blok** Macos'ta parola otomatik doldurma özelliğinin kullanılmasını önlemek için. Seçme **blok** ayrıca aşağıdaki etkisi:

  - Kullanıcılar, Safari veya herhangi bir uygulama kaydedilmiş bir parola kullanmayı sorulmaz.
  - Otomatik güçlü parolalar devre dışıdır ve kullanıcıların güçlü parolalar önerilen değildir.

  **Yapılandırılmamış** (varsayılan), bu özellikleri sağlar.

- **Parola yakınlık isteklerini engellemek**: Seçin **blok** cihazın yakın cihazlardan parola istemeyen şekilde. **Yapılandırılmamış** (varsayılan) Bu parola istekleri sağlar.

- **Parola paylaşımı block**: **Blok** engeller parolaları Airdrop'a kullanarak cihazlar arasında paylaşma. **Yapılandırılmamış** (varsayılan), paylaşılan parola sağlar.

## <a name="built-in-apps"></a>Yerleşik Uygulamalar

- **Safari otomatik doldurmayı engelleyin**: **Blok** cihazda Safari otomatik doldurma özelliğini devre dışı bırakır. **Yapılandırılmamış** (varsayılan), kullanıcıların web tarayıcıdaki otomatik tamamlama ayarlarını değiştirmesine olanak tanır.
- **Kamerayı engelle**: Seçin **blok** için cihaz kameranızı erişimi engellemek için. **Yapılandırılmamış** (varsayılan), cihazın kamerasını erişim sağlar.
- **Apple Music Block**: **Blok** Music uygulaması Klasik moda döner ve Music hizmeti devre dışı bırakır. **Yapılandırılmamış** (varsayılan), Apple Music uygulamasının kullanılmasına izin verir.
- **Spotlight Internet arama sonuçlarında Block**: **Blok** Spotlight Internet aramasının herhangi bir sonuç döndürmesini durdurur. **Yapılandırılmamış** (varsayılan), Spotlight arama, arama sonuçları sağlamak için Internet'e bağlanmasına izin verir.
- **İTunes kullanarak dosya bloğu aktarımı**: **Blok** uygulama dosya paylaşım hizmetlerinin devre dışı bırakır. MacOS 10.13 bulunan ve üzeri. **Yapılandırılmamış** uygulama dosya paylaşım hizmetlerinin (varsayılan) sağlar.

## <a name="restricted-apps"></a>Kısıtlı uygulamalar

Kısıtlı uygulamalar listesinde, aşağıdaki listelerden birini yapılandırabilirsiniz:

- A **Yasak uygulamalar** listesi: Kullanıcıların yüklemesine ve çalıştırmasına izin izin verilmeyen, Intune tarafından yönetilmeyen uygulamaları listeleyin. Kullanıcıların izin verilmeyen uygulamaları yüklenmesini engelleyen değildir, ancak Eğer öyleyse yöneticinin bildirilir.
- Bir **onaylı uygulamalar** listesi: Kullanıcıların yüklemesine izin verilen uygulamaları listeleyin. Kullanıcılar listelenmeyen uygulamaları yüklememelidir. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir. Kullanıcıların onaylı listede olmayan bir uygulama yüklenmesini engelleyen değildir. Ancak, Eğer öyleyse yöneticinin bildirilir.

Listeyi yapılandırmak için **Ekle**’ye tıklayın, sonra tercih ettiğiniz bir adı (isteğe bağlı olarak uygulama yayımcısı) ve uygulamanın paket kimliğini (örneğin *com.apple.calculator*) belirtin.

## <a name="connected-devices"></a>Bağlı cihazlar

- **Airdrop'u engelleyin**: **Blok** Airdrop'a cihazda kullanarak engeller. **Yapılandırılmamış** (varsayılan), yakındaki cihazlarla içerik değişimi için AirDrop özelliğinin kullanılmasını sağlar.
- **Apple Watch otomatik Block kilidini**: **Blok** kullanıcıların macOS cihazlarını, Apple Watch ile kilidini açmasını engeller. **Yapılandırılmamış** (varsayılan), Apple Watch ile macOS cihazlarını kilidini açmak kullanıcıların sağlar.

## <a name="cloud-and-storage"></a>Bulut ve depolama

- **İCloud anahtar zinciri eşitlenmesinin engellenip**: Seçin **blok** icloud Anahtarlıkta depolanan eşitleme kimlik bilgileri devre dışı bırakmak için. **Yapılandırılmamış** (varsayılan), kullanıcıların bu kimlik bilgilerini eşitleme sağlar.
- **İcloud'a belge eşitlemeyi engelleyin**: **Blok** iCloud belgeleri ve verileri eşitlenmesini önler. **Yapılandırılmamış** (varsayılan), iCloud depolama alanınızda belge ve anahtar-değer eşitlemesine izin verir.
- **İCloud posta yedekleme block**: **Blok** iCloud macOS posta uygulamasına eşitlenmesini önler. **Yapılandırılmamış** (varsayılan), icloud posta eşitleme sağlar.
- **İCloud kişi yedekleme block**: **Blok** iCloud cihazları kişilerin eşitlenmesini önler. **Yapılandırılmamış** (varsayılan), iCloud kullanarak kişi eşitleme sağlar.
- **İCloud Takvim yedekleme block**: **Blok** iCloud macOS Takvim uygulamaya eşitlenmesini önler. **Yapılandırılmamış** (varsayılan), icloud Takvim eşitleme sağlar.
- **İCloud anımsatıcı yedekleme block**: **Blok** iCloud macOS anımsatıcılar uygulamaya eşitlenmesini önler. **Yapılandırılmamış** (varsayılan), icloud anımsatıcılar eşitleme sağlar.
- **İCloud yer işareti yedekleme block**: **Blok** iCloud yer işaretleri cihazları eşitlenmesini önler. **Yapılandırılmamış** (varsayılan), yer işareti eşitleme icloud sağlar.
- **İCloud notları yedekleme block**: **Blok** iCloud notları cihazları eşitlenmesini önler. **Yapılandırılmamış** (varsayılan), icloud Notes eşitleme sağlar.

## <a name="domains"></a>Etki Alanları

- **E-posta etki alanı URL'si**: Listeye bir veya daha fazla URL ekleyin. Kullanıcılar, yapılandırdığınız etki alanı dışındaki bir etki alanından e-posta aldığında, bu e-posta MacOS Mail uygulamasında güvenilmeyen olarak işaretlenir.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).

Üzerinde cihaz özelliklerini ve ayarlarını da kısıtlayabilirsiniz [iOS](device-restrictions-ios.md) cihazlar.
