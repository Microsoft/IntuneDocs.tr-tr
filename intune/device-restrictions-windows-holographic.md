---
title: "Windows Holographic for Business için Intune cihaz kısıtlama ayarları"
titlesuffix: Azure portal
description: "Windows Holographic for Business cihazlarda cihaz ayarlarını ve işlevselliğini denetlemek için kullanabileceğiniz Intune ayarlarını öğrenin.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 1/19/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 300ddb15f2d7b8f2fc6ab4a0e9e32852e0604e0a
ms.sourcegitcommit: 93622d740cbd12043eedc25a9699cc4256e23e7e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2018
---
# <a name="windows-holographic-for-business-device-restriction-settings-in-microsoft-intune"></a>Microsoft Intune’da Windows Holographic for Business cihaz kısıtlama ayarları

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft HoloLens gibi Windows Holographic for Business çalıştıran cihazlarda aşağıdaki cihaz kısıtlama ayarları desteklenir.

## <a name="general"></a>Genel

- **El ile kayıt kaldırma** - Kullanıcının iş yeri hesabını cihazdan el ile silmesine olanak sağlar.
- **Cortana** - Cortana sesli yardımcısını etkinleştirin veya devre dışı bırakın.
- **Coğrafi konum** - Cihazın konum hizmetleri bilgilerini kullanıp kullanamayacağını belirtir.



## <a name="password"></a>Parola
-   **Parola** - Son kullanıcının cihaza erişmek için parola girmesini zorunlu tutun.
    -   **Cihaz boşta kalma durumundan çıktığında parola isteme** - Boşta durumundaki bir cihazın kilidini açmak için kullanıcının parola girmesi gerektiğini belirtir.



## <a name="app-store"></a>Uygulama Mağazası

-   **Uygulama mağazası** - Cihazlarda uygulama mağazası kullanımına izin verin veya bunu engelleyin.
-   **Mağaza uygulamalarını otomatik güncelleştir** - Microsoft Mağazası'ndan yüklenen uygulamaların otomatik olarak güncelleştirilmesine izin verir.
-   **Güvenilir uygulama yüklemesi** - Güvenilir bir sertifikayla imzalanan uygulamaların dışarıdan yüklenmesine izin verir.
-   **Geliştirici kilidini açma** - Dışarıdan yüklenen uygulamaların son kullanıcı tarafından değiştirilmesine izin verme gibi Windows geliştirici ayarlarına izin verir.

## <a name="edge-browser"></a>Edge Tarayıcısı

-   **Microsoft Edge tarayıcısı** - Cihazda Microsoft Edge web tarayıcısının kullanılmasına izin verin.
-   **Tanılama bilgileri** - Tarayıcının İnternet tanımlama bilgilerini cihaza kaydetmesine olanak tanır.
-   **Açılır pencereler** - Tarayıcıdaki açılır pencereleri engeller (yalnızca Windows 10 masaüstü için geçerlidir).
-   **Arama önerileri** - Siz arama sözcükleri yazarken arama motorunuzun site önerilerinde bulunmasına olanak sağlar.
-   **Parola Yöneticisi** - Edge Parola Yöneticisi özelliğini etkinleştirin veya devre dışı bırakın.
- **Kullanıcıyı-izleme üst bilgileri gönderme** - Edge tarayıcısını, kullanıcıların ziyaret ettiği web sitelerine izleme (DNT) üst bilgileri gönderecek şekilde yapılandırır.

## <a name="windows-defender-smart-screen"></a>Windows Defender Smart Screen

- **SmartScreen for Microsoft Edge** - Site ve dosya indirmelerine erişmek için Edge SmartScreen'i etkinleştirin.

## <a name="search"></a>Ara
- **Arama konumu** - Aramanın konumu kullanıp kullanamayacağını belirtin. bilgiler


## <a name="cloud-and-storage"></a>Bulut ve Depolama
-   **Microsoft hesabı** - Kullanıcının bir Microsoft hesabını cihazla ilişkilendirmesine olanak sağlar.

## <a name="cellular-and-connectivity"></a>Hücresel ve Bağlantı

-   **Bluetooth** - Kullanıcının cihazda Bluetooth’u etkinleştirmesine ve yapılandırmasına izin verilip verilmeyeceğini denetler.
-   **Bluetooth bulunabilirliği** - Cihazın diğer Bluetooth özellikli cihazlar tarafından bulunabilmesine olanak sağlar.
-   **Bluetooth reklamları** - Cihazın Bluetooth üzerinden reklamlar almasına olanak tanır.

## <a name="control-panel-and-settings"></a>Denetim Masası ve Ayarlar

- **Sistem Saatindeki değişiklikler** - Son kullanıcının cihazın tarih ve saatini değiştirmesini engeller.

## <a name="reporting-and-telemetry"></a>Raporlama ve Telemetri

- **Kullanım verilerini paylaş** - Tanılama verilerinin gönderim düzeyini seçin.