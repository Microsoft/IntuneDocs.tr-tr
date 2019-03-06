---
title: Microsoft Intune - Azure'da macOS cihaz özelliği ayarlarını | Microsoft Docs
description: Tüm ayarları macOS cihazlarını AirPrint Microsoft Intune yapılandırmak için bkz. Aynı zamanda ağınızdaki IP adresi, yol ve bir AirPrint sunucusunun bağlantı noktası ayarlarını almak için adımlara bakın. Bu ayarları bir cihaz yapılandırma profilinde de macOS cihazlarını ağınızdaki AirPrint sunucularını kullanacak şekilde yapılandırmak için kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/05/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f9945aa9dd5ad563f6fde854d7f08fda010c18f7
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57392976"
---
# <a name="macos-device-feature-settings-in-intune"></a>ıntune'da macOS cihaz özelliği ayarları

Intune, macOS, ağınızdaki AirPrint yazıcılarına yazdırmak kullanıcıların bazı yerleşik ayarlarını içerir. Bu makalede, bu ayarları listeler ve her ayarın ne yaptığını açıklar. Ayrıca, IP adresi, yol ve Terminal uygulamasını (öykünücü) kullanarak, bağlantı noktası AirPrint yazıcıları için adımları listelenir.

## <a name="before-you-begin"></a>Başlamadan önce

[Bir macOS cihaz yapılandırma profili oluşturma](device-features-configure.md).

## <a name="airprint-settings"></a>AirPrint ayarları

1. İçinde **ayarları**seçin **AirPrint**. AirPrint sunucunun aşağıdaki özellikleri girin:

    - **IP adresi**: Yazıcı IPv4 veya IPv6 adresini girin. Yazıcılar tanımlamak için konak adları kullanıyorsanız, Terminal uygulamasını yazıcı ping göndererek, IP adresini alabilirsiniz. [Yol ve IP adresi al](#get-the-ip-address-and-path) (Bu makalede) daha fazla ayrıntı sağlar.
    - **Yol**: Yazıcı yolunu girin. Genellikle yoludur `ipp/print` ağınızdaki yazıcılar için. [Yol ve IP adresi al](#get-the-ip-address-and-path) (Bu makalede) daha fazla ayrıntı sağlar.
    - **Bağlantı noktası**: AirPrint hedefinin dinleme bağlantı noktasını girin. Bu özellik boş bırakırsanız AirPrint, varsayılan bağlantı noktasını kullanır. Kullanılabilir iOS 11.0 ve sonraki sürümleri.
    - **TLS**: Seçin **etkinleştirme** AirPrint bağlantılarını Aktarım Katmanı Güvenliği (TLS) ile güvenli hale getirmek için. Kullanılabilir iOS 11.0 ve sonraki sürümleri.

2. **Add (Ekle)** seçeneğini belirleyin. AirPrint sunucu listesine eklenir. Birçok AirPrint sunucuları ekleyebilirsiniz.

    Ayrıca **alma** AirPrint yazıcıların bir listesini içeren bir virgülle ayrılmış dosyası (.csv). Ayrıca, Intune'da AirPrint yazıcıları ekledikten sonra yapabilecekleriniz **dışarı** bu liste.

3. İşiniz bittiğinde seçin **Tamam** listenize kaydedin.

## <a name="get-the-ip-address-and-path"></a>Yol ve IP adresi al

AirPrinter sunucuları eklemek için yazıcı, kaynak yolu ve bağlantı noktası IP adresi gerekir. Aşağıdaki adımlar bu bilgilerinin nasıl alınacağını gösterir.

1. AirPrint yazıcıları aynı yerel ağa (alt ağ) bağlı bir Mac üzerinde açın **Terminal** (gelen **/Applications/Utilities**).
2. Terminal uygulamada yazın `ippfind`, select girin.

    Yazıcı bilgilerini not edin. Örneğin, benzer bir şey döndürebilir `ipp://myprinter.local.:631/ipp/port1`. İlk bölümü yazıcı adıdır. Son bölümü (`ipp/port1`) ise kaynak yoludur.

3. Terminale `ping myprinter.local`, select girin.

   IP adresini not edin. Örneğin, benzer bir şey döndürebilir `PING myprinter.local (10.50.25.21)`.

4. IP adresine ve kaynak yolu değerleri kullanın. Bu örnekte IP adresidir `10.50.25.21`, ve kaynak yolu `/ipp/port1`.

## <a name="next-steps"></a>Sonraki adımlar

- İçin tüm ayarları görüntülemek [iOS](ios-device-features-settings.md) cihazlar.
- Bu profili gruplara atamak; bkz: [cihaz profillerini atama](device-profile-assign.md).
