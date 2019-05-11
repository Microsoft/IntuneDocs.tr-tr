---
title: Microsoft Intune - Azure'da macOS cihaz özelliği ayarlarını | Microsoft Docs
description: MacOS cihazları için AirPrint yapılandırmak ve Güç düğmelerini Microsoft Intune gösterme veya gizleme için oturum açma penceresinde özelleştirmek için bkz. Ağınızdaki IP adresi, yol ve bir AirPrint sunucusunun bağlantı noktası ayarlarını almak için adımlara bakın. Bu ayarları bir cihaz yapılandırma profilinde de macOS cihaz özellikleri yapılandırmak için kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/23/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8858848d12ca3f5839741fc15d87e1cd66e9fad0
ms.sourcegitcommit: b0cf661145ccc6e3518db620af199786a623a0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64764860"
---
# <a name="macos-device-feature-settings-in-intune"></a>ıntune'da macOS cihaz özelliği ayarları

Intune, macOS cihazlarınızda özellikleri özelleştirmek için bazı yerleşik ayarlarını içerir. Bu makalede, bu ayarları listeler ve her ayarın ne yaptığını açıklar. Ayrıca, IP adresi, yol ve Terminal uygulamasını (öykünücü) kullanarak, bağlantı noktası AirPrint yazıcıları için adımları listelenir.

Bu özellik şu platformlarda geçerlidir:

- Mac OS

Mobil cihaz Yönetimi (MDM) çözümünüzün bir parçası olarak, bu ayarlar bir başlık oluşturun, kullanıcıların nasıl oturum seçin, bir AirPrint sunucusu ve daha fazlasını eklemek için kullanın.

Bu ayarlar, ıntune'da cihaz yapılandırma profili eklenir ve ardından atanan veya macOS cihazlarına dağıtılabilir.

## <a name="before-you-begin"></a>Başlamadan önce

[Bir macOS cihaz yapılandırma profili oluşturma](device-features-configure.md).

## <a name="airprint"></a>AirPrint

- **IP adresi**: Yazıcı IPv4 veya IPv6 adresini girin. Yazıcılar tanımlamak için konak adları kullanıyorsa, Terminal uygulamasını yazıcı ping göndererek, IP adresini alabilirsiniz. [Yol ve IP adresi al](#get-the-ip-address-and-path) (Bu makalede) daha fazla ayrıntı sağlar.
- **Yol**: Yazıcı yolunu girin. Genellikle yoludur `ipp/print` ağınızdaki yazıcılar için. [Yol ve IP adresi al](#get-the-ip-address-and-path) (Bu makalede) daha fazla ayrıntı sağlar.
- **Bağlantı noktası** (iOS 11.0 ve üstü): AirPrint hedefinin dinleme bağlantı noktasını girin. Bu özellik boş bırakırsanız AirPrint, varsayılan bağlantı noktasını kullanır.
- **TLS** (iOS 11.0 ve üstü): Seçin **etkinleştirme** AirPrint bağlantılarını Aktarım Katmanı Güvenliği (TLS) ile güvenli hale getirmek için.

**Ekleme** AirPrint sunucusu. Birçok AirPrint sunucuları ekleyebilirsiniz.

- **İçeri aktarma** (isteğe bağlı): Ayrıca **alma** AirPrint yazıcıların bir listesini içeren bir virgülle ayrılmış dosyası (.csv). Ayrıca, Intune'da AirPrint yazıcıları ekledikten sonra yapabilecekleriniz **dışarı** bu liste.

Seçin **Tamam** ayarlarınızı kaydetmek için.

### <a name="get-the-ip-address-and-path"></a>Yol ve IP adresi al

AirPrinter sunucuları eklemek için yazıcı, kaynak yolu ve bağlantı noktası IP adresi gerekir. Aşağıdaki adımlar bu bilgilerinin nasıl alınacağını gösterir.

1. AirPrint yazıcıları aynı yerel ağa (alt ağ) bağlı bir Mac üzerinde açın **Terminal** (gelen **/Applications/Utilities**).
2. Terminal uygulamada yazın `ippfind`, select girin.

    Yazıcı bilgilerini not edin. Örneğin, benzer bir şey döndürebilir `ipp://myprinter.local.:631/ipp/port1`. İlk bölümü yazıcı adıdır. Son bölümü (`ipp/port1`) ise kaynak yoludur.

3. Terminale `ping myprinter.local`, select girin.

   IP adresini not edin. Örneğin, benzer bir şey döndürebilir `PING myprinter.local (10.50.25.21)`.

4. IP adresine ve kaynak yolu değerleri kullanın. Bu örnekte IP adresidir `10.50.25.21`, ve kaynak yolu `/ipp/port1`.

## <a name="login-window"></a>Oturum açma penceresi

### <a name="window-layout"></a>Pencere düzeni

- **Ek bilgi menü çubuğunda göster**: Zaman alan menü çubuğunda seçildiğinde **izin** ana bilgisayar adı ve macOS sürümü gösterir. **Yapılandırılmamış** (varsayılan) bu bilgileri menü çubuğunda göster değil.
- **Başlık**: Oturum açma cihaz ekranda görüntülenen bir ileti girin. Örneğin, kuruluş bilgileriniz, Hoş Geldiniz iletisi, bulunmuş bilgilerini ve benzeri girin.
- **Oturum açma biçimi seçin**: Kullanıcıların cihaza nasıl oturum seçin. Seçenekleriniz şunlardır:
  - **Kullanıcı adı ve parola istemi** (varsayılan): Bir kullanıcı adı ve parola girmesini gerektirir.
  - **Tüm kullanıcılar için parola istemini listesinde**: Kullanıcıların kullanıcı adlarını bir kullanıcı listeden seçin ve ardından parolalarını girmeleri gerekir. Ayrıca yapılandırın:

    - **Yerel Kullanıcılar**: **Gizleme** yerel kullanıcı hesapları standart ve yönetici hesaplarını içerebilir kullanıcı listesinde göstermez. Yalnızca ağ ve sistem kullanıcı hesapları gösterilir. **Yapılandırılmamış** (varsayılan), yerel kullanıcı hesapları kullanıcı listesinde gösterilir.
    - **Mobil hesapları**: **Gizleme** mobil hesapları kullanıcı listesinde göstermez. **Yapılandırılmamış** (varsayılan) kullanıcı listesinde Mobil hesapları gösterir. Bazı mobil hesapları, ağ kullanıcıları gösterebilir.
    - **Ağ kullanıcıları**: Seçin **Göster** ağ kullanıcıları kullanıcı listesindeki listelemek için. **Yapılandırılmamış** (varsayılan) değil Göster ağ kullanıcı hesapları kullanıcı listesinde.
    - **Yönetici kullanıcılar**: **Gizleme** yönetici kullanıcı listesinde kullanıcı hesaplarını göstermiyor. **Yapılandırılmamış** (varsayılan) kullanıcı listesinde kullanıcı hesaplarını yönetici gösterir.
    - **Diğer kullanıcıların**: Seçin **Göster** listesine **diğer...**  kullanıcı listesinde kullanıcı. **Yapılandırılmamış** (varsayılan) kullanıcı listesinde diğer kullanıcı hesapları Göster değil.

### <a name="login-screen-power-settings"></a>Oturum açma ekranı güç ayarları

- **Kapat düğmesi**: **Gizleme** kapatma düğmesini oturum açma ekranı göstermez. **Yapılandırılmamış** (varsayılan) kapatma düğmesini gösterir.
- **Düğmeyi yeniden**: **Gizleme** oturum açma ekranı yeniden Başlat düğmesi göstermez. **Yapılandırılmamış** (varsayılan), yeniden Başlat düğmesi gösterilir.
- **Uyku düğmesi**: **Gizleme** oturum açma ekran Uyku düğmesi göstermez. **Yapılandırılmamış** (varsayılan), uyku düğmesi gösterilir.

### <a name="other"></a>Diğer

- **Konsolundan kullanıcı oturum açma devre dışı**: **Devre dışı** oturum açmak için kullanılan macOS komut satırı gizler. Tipik kullanıcıların **devre dışı** yapılandırmaz. **Yapılandırılmamış** (varsayılan), Gelişmiş macOS komut satırını kullanarak oturum açmasına izin verir. Konsol moduna girmek için kullanıcıların girin `>console` kullanıcı alan ve konsol penceresinde kimliğini doğrulaması gerekir.

### <a name="apple-menu"></a>Apple menüsü

Cihazlara kullanıcılar oturum açtıktan sonra aşağıdaki ayarlar, ne yapabileceklerini etkiler.

- **Aşağı bilgisayarı devre dışı bırak**: **Devre dışı** kullanıcıların seçmesini engeller **kapatma** kullanıcı oturum açtıktan sonra seçeneği. **Yapılandırılmamış** (varsayılan), kullanıcıların seçmesine izin verir **kapatma** cihazda menü öğesi.
- **Yeniden başlatma devre dışı**: **Devre dışı** kullanıcıların seçmesini engeller **yeniden** kullanıcı oturum açtıktan sonra seçeneği. **Yapılandırılmamış** (varsayılan), kullanıcıların seçmesine izin verir **yeniden** cihazda menü öğesi.
- **Güç kapalı devre dışı**: **Devre dışı** kullanıcıların seçmesini engeller **gücünün kapatılmasını** kullanıcı oturum açtıktan sonra seçeneği. **Yapılandırılmamış** (varsayılan), kullanıcıların seçmesine izin verir **gücünün kapatılmasını** cihazda menü öğesi.
- **Log Out devre dışı** (macOS 10.13 ve üzeri): **Devre dışı** kullanıcıların seçmesini engeller **oturumunuzu** kullanıcı oturum açtıktan sonra seçeneği. **Yapılandırılmamış** (varsayılan), kullanıcıların seçmesine izin verir **oturumunuzu** cihazda menü öğesi.
- **Kilit ekranında devre dışı** (macOS 10.13 ve üzeri): **Devre dışı** kullanıcıların seçmesini engeller **kilit ekranı** kullanıcı oturum açtıktan sonra seçeneği. **Yapılandırılmamış** (varsayılan), kullanıcıların seçmesine izin verir **kilit ekranı** cihazda menü öğesi.

Seçin **Tamam** ayarlarınızı kaydetmek için.

## <a name="next-steps"></a>Sonraki adımlar

- İçin tüm ayarları görüntülemek [iOS](ios-device-features-settings.md) cihazlar.
- [Bu profili atarsınız](device-profile-assign.md) , gruplara ve [atamanın durumunu izlemenize](device-profile-monitor.md).
