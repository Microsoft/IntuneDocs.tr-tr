---
title: Microsoft Intune - Azure'da macOS cihaz ayarları | Microsoft Docs
titlesuffix: ''
description: Ekleme, yapılandırma veya macOS cihazlarda parola gereksinimlerini ayarlama dahil olmak üzere kısıtlamanıza, kilit ekranı kontrol, yerleşik uygulamaları kullanın, kısıtlanmış veya onaylı uygulamalar ekleyin, bluetooth cihazların işlemek, yeniden işlenmek üzere buluta bağlayın ayarlarını oluşturma ve Depolama, bilgi noktası modu etkinleştirme, etki alanlarını ekleyin ve kullanıcıların Microsoft Intune Safari web tarayıcısı ile nasıl etkileşim denetim.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/19/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0d58a23899fbf6758687811b293418ee3b2adfb3
ms.sourcegitcommit: 9a4c5b6c2ce511edaeace25426a23f180cb71e15
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/07/2019
ms.locfileid: "57565358"
---
# <a name="macos-device-settings-to-allow-or-restrict-features-using-intune"></a>izin verme veya kısıtlamanıza Intune kullanarak macOS cihaz ayarları

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makalede, listeler ve macOS cihazlarda denetleyebileceğiniz farklı ayarlar açıklanır. Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, izin veya özellikleri devre dışı bırakabilir, parola kuralları, izin veya belirli uygulamalar ve daha fazlasını sınırlamak için bu ayarları kullanın.

Bu ayarlar, ıntune'da cihaz yapılandırma profili eklenir ve ardından atanan veya macOS cihazlarına dağıtılabilir.

## <a name="before-you-begin"></a>Başlamadan önce

[Cihaz kısıtlamalarını yapılandırma profili oluşturma](device-restrictions-configure.md#create-the-profile).

## <a name="general"></a>Genel

- **İçeriği önbelleğe alma block**: Seçin **yapılandırılmadı** içerik önbelleğe almayı etkinleştirmek için (varsayılan). İçeriği önbelleğe alma, uygulama verilerini, web tarayıcı verilerini, indirmeler ve daha fazla yerel olarak cihazda depolar. Seçin **blok** önbellekte depolanır, bu verileri önlemek için.

  Macos'ta içeriği önbelleğe alma ile ilgili daha fazla bilgi için bkz: [Mac üzerinde içerik önbelleğe alınmasını yönetin](https://support.apple.com/guide/mac-help/manage-content-caching-on-mac-mchl3b6c3720/mac) (başka bir Web sitesini açar).

  Bu özellik şu platformlarda geçerlidir:  
  - macOS 10.13 ve üzeri

- **(Yalnızca denetimli) yazılım güncelleştirmelerinin erteleneceği**: Ayarlandığında **yapılandırılmadı** (varsayılan), yazılım güncelleştirmeleri gösterilir cihazda gibi Apple onları serbest bırakır. Bir macOS güncelleştirmesini Apple tarafından belirli bir tarihte yayımlanan, örneğin, sonra bu güncelleştirmeyi doğal olarak yayın tarihindeki cihazda gösterilir.

  **Etkinleştirme** 0-90 güne ait cihazlarda yazılım güncelleştirmeleri gösterilirken gecikme sağlar. Bu ayar, güncelleştirmeler veya yüklü olmayan denetlemez. 

  - **Yazılım güncelleştirmelerini görünürlüğünü gecikme**: 0-90 gün arasında bir değer girin. Gecikme süresi dolduğunda kullanıcılar gecikme tetiklendiğinde erken kullanılabilir işletim sistemi sürümüne güncelleştirmek için bildirim alın.

    Örneğin, bir macOS güncelleştirme kullanılabilir ise **1 Ocak**, ve **gecikme görünürlük** ayarlanır **5 gün**, sonra güncelleştirmeyi, cihazlarda kullanılabilir bir güncelleştirme olarak gösterilmiyor. Üzerinde **altıncı gün** sürümünden güncelleştirmesi kullanıma sunuldu ve son kullanıcılar da yükleyebilirsiniz.

    Bu özellik şu platformlarda geçerlidir:  
    - macOS 10.13.4 ve üzeri

## <a name="password"></a>istemcisiyle yönetilen bir cihaz için)

- **Parola**: Son kullanıcının cihaza erişmek için parola girmesini zorunlu tutun.
  - **Gerekli parola türü**: Olup parolanın yalnızca sayısal olabileceğini ya da alfasayısal olması gerektiğini belirtin (harfler ve sayılar içeren). Bu ayar yalnızca Mac OS X sürüm 10.10.3 ve üzerinde desteklenir.
  - **Paroladaki alfasayısal olmayan karakter sayısı**: Parolada kullanılması gereken karmaşık karakterlerin sayısını belirtin (**0**-**4** karakter).<br>Karmaşık bir karakter, “**?**” gibi bir simgedir.
  - **Minimum parola uzunluğu**: Kullanıcının yapılandırması gereken parolanın uzunluk alt sınırını girin (arasında **4** ve **16** karakter).
  - **Basit parolalar**: **0000** veya **1234** gibi basit parolaların kullanımına izin verin.
  - **Parola istenmeden önce ekran kilitlendikten sonra en fazla dakika**: Bilgisayarın ne kadar süreyle etkinlik dışı kaldıktan sonra kilidinin açılması için bir parolanın gerekli olacağını belirtin.
  - **Ekran kilitlenmeden işlem yapılmayan dakika**: Bilgisayar ekran kilitlenmeden önce boşta bekleyeceği süreyi belirtin.
  - **Parola süresinin sonu (gün)**: Kullanıcının kaç gün geçtikten sonra parolayı değiştirmesi gerekeceğini belirtin (**1**-**255** gün).
  - **Önceki parolaların yeniden kullanılmasını engelle**: Kullanılamayacak, önceden kullanılmış parola sayısını girin gelen **1** için **24**.

- **Blok parola otomatik doldurma**: Seçin **blok** Macos'ta parola otomatik doldurma özelliğinin kullanılmasını önlemek için. Seçme **blok** ayrıca aşağıdaki etkisi:

  - Kullanıcılar, Safari veya herhangi bir uygulama kaydedilmiş bir parola kullanmayı sorulmaz.
  - Otomatik güçlü parolalar devre dışıdır ve kullanıcıların güçlü parolalar önerilen değildir.

  **Yapılandırılmamış** bu özellikleri sağlar.

- **Parola yakınlık isteklerini engellemek**: Seçin **blok** cihazın yakın cihazlardan parola istemeyen şekilde. **Yapılandırılmamış** bu parola istekleri sağlar.

- **Parola paylaşımı block**: **Blok** engeller parolaları Airdrop'a kullanarak cihazlar arasında paylaşma. **Yapılandırılmamış** paylaşılması parola sağlar.

## <a name="restricted-apps"></a>Kısıtlı uygulamalar

Kısıtlı uygulamalar listesinde, aşağıdaki listelerden birini yapılandırabilirsiniz:

- A **Yasak uygulamalar** listesi: Kullanıcıların yüklemesine ve çalıştırmasına izin izin verilmeyen, Intune tarafından yönetilmeyen uygulamaları listeleyin. Kullanıcıların izin verilmeyen uygulamaları yüklenmesini engelleyen değildir, ancak Eğer öyleyse yöneticinin bildirilir.
- Bir **onaylı uygulamalar** listesi: Kullanıcıların yüklemesine izin verilen uygulamaları listeleyin. Kullanıcılar listelenmeyen uygulamaları yüklememelidir. Intune tarafından yönetilen uygulamalara otomatik olarak izin verilir. Kullanıcıların onaylı listede olmayan bir uygulama yüklenmesini engelleyen değildir. Ancak, Eğer öyleyse yöneticinin bildirilir.

Listeyi yapılandırmak için **Ekle**’ye tıklayın, sonra tercih ettiğiniz bir adı (isteğe bağlı olarak uygulama yayımcısı) ve uygulamanın paket kimliğini (örneğin *com.apple.calculator*) belirtin.

## <a name="domains"></a>Etki Alanları

### <a name="unmarked-email-domains"></a>İşaretsiz e-posta etki alanları

**E-posta Etki Alanı URL'si** alanında, listeye bir veya daha fazla URL ekleyin. Kullanıcılar, yapılandırdığınız etki alanı dışındaki bir etki alanından e-posta aldığında, bu e-posta MacOS Mail uygulamasında güvenilmeyen olarak işaretlenir.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).

Üzerinde cihaz özelliklerini ve ayarlarını da kısıtlayabilirsiniz [iOS](device-restrictions-ios.md) cihazlar.