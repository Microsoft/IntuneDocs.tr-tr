---
title: Microsoft Intune-Azure 'da macOS cihaz özelliği ayarları | Microsoft Docs
description: MacOS cihazlarını AirPrint için yapılandırma ayarlarına bakın ve Microsoft Intune içindeki güç düğmelerini göstermek veya gizlemek için oturum açma penceresini özelleştirin. Ağınızdaki bir AirPrint sunucusunun IP adresini, yolunu ve bağlantı noktası ayarlarını almak için adımlara bakın. MacOS cihaz özelliklerini yapılandırmak için bu ayarları bir cihaz yapılandırma profilinde kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/05/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 63f2832dd321425efe8092f1bb12dd0d479ef71b
ms.sourcegitcommit: b78793ccbef2a644a759ca3110ea73e7ed6ceb8f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69549925"
---
# <a name="macos-device-feature-settings-in-intune"></a>Intune 'da macOS cihaz özelliği ayarları

Intune, macOS cihazlarınızdaki özellikleri özelleştirmek için bazı yerleşik ayarlar içerir. Bu makale, bu ayarları listeler ve her ayarın ne yaptığını açıklar. Ayrıca, Terminal uygulaması 'nı (öykünücü) kullanarak AirPrint yazıcılarının IP adresini, yolunu ve bağlantı noktasını almak için gereken adımları listeler.

Bu özellik şu platformlarda geçerlidir:

- Mac OS

Mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak bu ayarları kullanarak bir başlık oluşturun, kullanıcıların oturum açma şeklini seçin, AirPrint Server ekleme ve daha fazlasını yapın.

Bu ayarlar, Intune'da bir cihaz yapılandırma profiline eklenir ve daha sonra macOS cihazlarınıza atanır veya dağıtılır.

## <a name="before-you-begin"></a>Başlamadan önce

[MacOS cihaz yapılandırma profili oluşturun](device-features-configure.md).

## <a name="airprint"></a>AirPrint

- **IP adresi**: Yazıcının IPv4 veya IPv6 adresini girin. Yazıcıları tanımlamak için konak adlarını kullanıyorsanız, Terminal uygulamasındaki yazıcıya ping ekleyerek IP adresini alabilirsiniz. [IP adresini ve yolu al](#get-the-ip-address-and-path) (Bu makalede) daha fazla ayrıntı sağlar.
- **Yol**: Yazıcının yolunu girin. Yol, genellikle `ipp/print` ağınızdaki yazıcılar içindir. [IP adresini ve yolu al](#get-the-ip-address-and-path) (Bu makalede) daha fazla ayrıntı sağlar.
- **Bağlantı noktası** (iOS 11,0 ve üzeri): AirPrint hedefinin dinleme bağlantı noktasını girin. Bu özelliği boş bırakırsanız AirPrint varsayılan bağlantı noktasını kullanır.
- **TLS** (iOS 11,0 ve üzeri): Aktarım Katmanı Güvenliği (TLS) ile AirPrint bağlantılarını güvenli hale getirmek için **Etkinleştir** ' i seçin.

**Ekle** AirPrint sunucusu. Birçok AirPrint sunucusu ekleyebilirsiniz.

- **Içeri aktar** (isteğe bağlı): Ayrıca, AirPrint yazıcılarının listesini içeren bir virgülle ayrılmış dosyayı (. csv) **Içeri aktarabilirsiniz** . Ayrıca, Intune 'A AirPrint yazıcıları ekledikten sonra bu listeyi **dışarı aktarabilirsiniz** .

Ayarlarınızı kaydetmek için **Tamam ' ı** seçin.

### <a name="get-the-ip-address-and-path"></a>IP adresini ve yolu al

AirPrinter sunucuları eklemek için, yazıcının IP adresi, kaynak yolu ve bağlantı noktası gerekir. Aşağıdaki adımlarda bu bilgilerin nasıl alınacağı gösterilmektedir.

1. AirPrint yazıcıları ile aynı yerel ağa (alt ağ) bağlı bir Mac üzerinde, açık **Terminal** ( **/Applications/Utilities**).
2. Terminal uygulamasında yazın `ippfind`ve ENTER ' u seçin.

    Yazıcı bilgilerini aklınızda edin. Örneğin, şuna benzer `ipp://myprinter.local.:631/ipp/port1`bir şey döndürebilir. İlk bölüm, yazıcının adıdır. Son Bölüm (`ipp/port1`) kaynak yoludur.

3. Terminalde yazın `ping myprinter.local`ve ENTER ' u seçin.

   IP adresini aklınızda edin. Örneğin, şuna benzer `PING myprinter.local (10.50.25.21)`bir şey döndürebilir.

4. IP adresi ve kaynak yolu değerlerini kullanın. Bu örnekte, IP adresi `10.50.25.21`ve kaynak yolu olur. `/ipp/port1`

## <a name="login-items"></a>Oturum açma öğeleri

- **Dosyalar, klasörler ve özel uygulamalar**: Kullanıcı cihazda oturum açtığında açmak istediğiniz bir dosya, klasör, özel uygulama veya sistem uygulamasının yolunu **ekleyin** . Kuruluşunuz için oluşturulmuş veya özelleştirilmiş olan sistem uygulamaları veya uygulamalar genellikle `Applications` klasöründe, `/Applications/AppName.app`şuna benzer bir yol ile yapılır. 

  Birçok dosya, klasör ve uygulama ekleyebilirsiniz. Örneğin şunu girin:  
  
  - `/Applications/Calculator.app`
  - `/Applications`
  - `/Applications/Microsoft Office/root/Office16/winword.exe`
  - `/Users/UserName/music/itunes.app`
  
  Herhangi bir uygulama, klasör veya dosya eklerken doğru yolu girdiğinizden emin olun. Tüm öğeler `Applications` klasörde değil. Bir Kullanıcı bir öğeyi bir konumdan diğerine taşıdıysanız yol değişir. Bu taşınan öğe, Kullanıcı oturum açtığında açılmaz.

## <a name="login-window"></a>Oturum açma penceresi

### <a name="window-layout"></a>Pencere düzeni

- **Menü çubuğunda ek bilgileri göster**: Menü çubuğundaki saat alanı seçildiğinde, **Izin ver** ana bilgisayar adını ve MacOS sürümünü gösterir. **Yapılandırılmadı** (varsayılan), bu bilgileri menü çubuğunda göstermez.
- **Başlık**: Cihazda oturum açma ekranında gösterilen bir ileti girin. Örneğin, kuruluş bilgilerinizi, bir hoş geldiniz iletisini, kayıp ve bulunan bilgileri girin ve bu şekilde devam edin.
- **Oturum açma biçimini seçin**: Kullanıcıların cihazda nasıl oturum açmasını seçin. Seçenekleriniz şunlardır:
  - **Kullanıcı adı ve parola iste** (varsayılan): Kullanıcıların bir Kullanıcı adı ve parola girmesini gerektirir.
  - **Tüm kullanıcıları Listele, parola iste**: Kullanıcıların Kullanıcı listesinden kullanıcı adını seçmesini ve sonra parolasını girmesini gerektirir. Ayrıca şunları yapılandırın:

    - **Yerel kullanıcılar**: **Gizle** , yerel kullanıcı hesaplarını, standart ve yönetici hesaplarını içerebilecek Kullanıcı listesinde göstermez. Yalnızca ağ ve sistem kullanıcı hesapları gösterilir. **Yapılandırılmadı** (varsayılan) Kullanıcı listesindeki yerel kullanıcı hesaplarını gösterir.
    - **Mobil hesaplar**: **Gizle** , Kullanıcı listesinde mobil hesapları göstermez. **Yapılandırılmadı** (varsayılan) Kullanıcı listesindeki mobil hesapları gösterir. Bazı mobil hesaplar, ağ kullanıcıları olarak gösterilebilir.
    - **Ağ kullanıcıları**: Kullanıcı listesindeki ağ kullanıcılarını listelemek için **göster** ' i seçin. **Yapılandırılmadı** (varsayılan) Kullanıcı listesinde ağ kullanıcı hesaplarını göstermez.
    - **Yönetici kullanıcılar**: **Gizle** , Kullanıcı listesinde Yönetici Kullanıcı hesaplarını göstermez. **Yapılandırılmadı** (varsayılan) Kullanıcı listesindeki yönetici kullanıcı hesaplarını gösterir.
    - **Diğer kullanıcılar**: Kullanıcı listesindeki **diğer...** kullanıcıları listelemek için **göster** ' i seçin. **Yapılandırılmadı** (varsayılan) Kullanıcı listesindeki diğer Kullanıcı hesaplarını göstermez.

### <a name="login-screen-power-settings"></a>Oturum açma ekranı güç ayarları

- **Kapat düğmesi**: **Gizle** , oturum açma ekranında Kapat düğmesini göstermez. **Yapılandırılmadı** (varsayılan) Kapalı düğmesini gösterir.
- **Yeniden Başlat düğmesi**: **Gizle** , oturum açma ekranında yeniden Başlat düğmesini göstermez. **Yapılandırılmadı** (varsayılan) yeniden Başlat düğmesini gösterir.
- **Uyku düğmesi**: **Gizle** , oturum açma ekranında uyku düğmesini göstermez. **Yapılandırılmadı** (varsayılan) uyku düğmesini gösterir.

### <a name="other"></a>Diğer

- **Kullanıcı oturumunu konsolundan devre dışı bırak**: **Disable** , oturum açmak Için kullanılan MacOS komut satırını gizler. Tipik kullanıcılar için bu ayarı **devre dışı bırakın** . **Yapılandırılmadı** (varsayılan), gelişmiş kullanıcıların macOS komut satırını kullanarak oturum açmasına olanak sağlar. Konsol modunu girmek için, kullanıcılar Kullanıcı `>console` adı alanına girer ve konsol penceresinde kimlik doğrulaması yapılmalıdır.

### <a name="apple-menu"></a>Apple menüsü

Kullanıcılar cihazlarda oturum açtıktan sonra, aşağıdaki ayarlar neler yapabileceğini etkiler.

- **Kapatmayı devre dışı bırak**: **Devre dışı bırak** seçeneği, kullanıcıların oturum açtıktan sonra Kullanıcı oturumunu seçmesini önler. **Yapılandırılmadı** (varsayılan) kullanıcıların cihazdaki **kapalı** menü öğesini seçmesine izin verir.
- **Yeniden başlatmayı devre dışı bırak**: **Disable** seçeneği, kullanıcıların oturum açtıktan sonra **yeniden başlatma** seçeneğini seçmesini önler. **Yapılandırılmadı** (varsayılan) kullanıcıların cihazdaki **Yeniden Başlat** menü öğesini seçmesine olanak sağlar.
- Kapatmayı **devre dışı bırak**: **Devre dışı bırak** seçeneği, Kullanıcı oturum açtıktan sonra kullanıcıların **kapatma** seçeneğini seçmesini önler. **Yapılandırılmadı** (varsayılan) kullanıcıların cihazdaki **kapatma** menü öğesini seçmesine olanak sağlar.
- **Oturumu kapatma devre dışı** (macOS 10,13 ve üzeri): **Devre dışı bırak** seçeneği, Kullanıcı oturum açtıktan sonra kullanıcıların **Oturumu Kapat** seçeneğini seçmesini önler. **Yapılandırılmadı** (varsayılan) kullanıcıların cihazdaki **oturum kapatma** menü öğesini seçmesine olanak sağlar.
- **Kilit ekranını devre dışı bırak** (macOS 10,13 ve üzeri): **Devre dışı bırak** seçeneği, Kullanıcı oturum açtıktan sonra kullanıcıların **kilit ekranı** seçmesini önler. **Yapılandırılmadı** (varsayılan) kullanıcıların cihazdaki **kilit ekranı** menü öğesini seçmesine izin verir.

Ayarlarınızı kaydetmek için **Tamam ' ı** seçin.

## <a name="next-steps"></a>Sonraki adımlar

- [İOS](ios-device-features-settings.md) cihazlarının tüm ayarlarını görüntüleyin.
- [Bu profili gruplara atayın](device-profile-assign.md) ve [durumunu izleyin](device-profile-monitor.md).
