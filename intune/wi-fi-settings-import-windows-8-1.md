---
title: Windows 8.1 ve üzeri için Wi-Fi ayarlarını içeri aktarma
titleSuffix: Microsoft Intune
description: Wi-Fi ayarlarını Windows’dan Intune Wi-Fi profiline aktarma.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 157416738e4607d5022f1c3c7ed8251a8e32fe3e
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune"></a>Microsoft Intune’da Windows 8.1 ve üzeri cihazlar için Wi-Fi ayarlarını içeri aktarma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Windows 8.1 veya Windows 10 masaüstü veya mobil ya da Windows Holographic for Business çalıştıran cihazlar için önceden bir dosyaya aktarılmış Wi-Fi yapılandırma profilini içeri aktarabilirsiniz.

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Windows cihazından Wi-Fi ayarlarını dışarı aktarma

Windows'da **netsh wlan** yardımcı programını kullanarak var olan bir Wi-Fi profilini Intune tarafından okunabilen bir XML dosyasına aktarın. Profili başarıyla kullanmak için anahtarın düz metin olarak dışarı aktarılması gerekir.

Gerekli WiFi profilinin zaten yüklü olduğu bir Windows bilgisayarda aşağıdaki adımları kullanın:

1. Dışarı aktarılan W-Fi-profilleri için **c:\WiFi** gibi bir yerel klasör oluşturun.
2. Yönetici olarak bir Komut İstemi açın.
3. `netsh wlan show profiles` komutunu çalıştırın ve dışarı aktarmak istediğiniz profilin adını not edin. Bu örnekte profil adı **WiFiName** şeklindedir.
4. `netsh wlan export profile name="ProfileName" folder=c:\Wifi` komutunu çalıştırın. Bunun yapılması hedef klasörünüzde **Wi-Fi-WiFiName.xml** adlı bir Wi-Fi profili dosyası oluşturur.

## <a name="import-the-wi-fi-settings-into-intune"></a>Wi-Fi ayarlarını Intune'da içeri aktarma

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
4. Cihaz kısıtlama profili için bir **Ad** ve **Açıklama** girin.

    > [!IMPORTANT]
    > - Adın Wi-Fi profili xml’indeki ad özniteliği ile aynı olması **gereklidir**. Yoksa işlem başarısız olur.
    > - Önceden paylaşılan anahtar içeren bir Wi-Fi profilini dışarı aktarıyorsanız komuta `key=clear` eklemeniz **gereklidir**. Örneğin şunu girin: `netsh wlan export profile name="ProfileName" key=clear folder=c:\Wifi`
    > - Windows 10 ile önceden paylaşılan bir anahtarı kullanmak, Intune’da bir düzeltme hatasına sebep olur. Bu durumda, Wi-Fi profili cihaza düzgün bir şekilde atanır ve profil beklendiği gibi çalışır.
    > - Önceden paylaşılan anahtar içeren bir Wi-Fi profilini dışarı aktarıyorsanız dosyanın korumalı olduğundan emin olun. Anahtar düz metin biçimindedir, yani anahtarı korumak sizin sorumluluğunuzdadır.

5. **Platform**’da **Windows 8.1 ve üzerini** seçin.
6. **Profil türü**’nde **Wi-Fi içeri aktarma**’yı seçin.
7. Aşağıdaki ayarları yapılandırın:
  - **Bağlantı adı**: Wi-Fi bağlantısı için bir ad girin. Bu ad, kullanılabilir Wi-Fi ağlarına göz atan son kullanıcılara görüntülenir.
  - **Profil XML’i**: Intune’da içeri aktarmak istediğiniz Wi-Fi profili ayarlarını içeren XML dosyasını seçmek için gözat düğmesini seçin.
  - **Dosya içeriği**: Seçtiğiniz yapılandırma profili için XML kodunu görüntüler.
8. İşiniz bittiğinde **Tamam**’ı seçip profili **Oluşturun**.

Profil oluşturulur ve profiller listesine eklenir.
