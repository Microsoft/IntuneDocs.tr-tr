---
title: "Windows 8.1 ve üzeri için Wi-Fi ayarlarını içeri aktarma"
titleSuffix: Microsoft Intune
description: "Wi-Fi ayarlarını Windows’dan Intune Wi-Fi profiline aktarma."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 890a10ecf4212656c189adaf46bb2839898758c1
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune"></a>Microsoft Intune’da Windows 8.1 ve üzeri cihazlar için Wi-Fi ayarlarını içeri aktarma

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Windows 8.1 veya Windows 10 masaüstü veya mobil ya da Windows Holographic for Business çalıştıran cihazlar için önceden bir dosyaya aktarılmış Wi-Fi yapılandırma profilini içeri aktarabilirsiniz.

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Windows cihazından Wi-Fi ayarlarını dışarı aktarma

Windows'da **netsh wlan** yardımcı programını kullanarak var olan bir Wi-Fi profilini Intune tarafından okunabilen bir XML dosyasına aktarın. Gerekli WiFi profilinin zaten yüklü olduğu bir Windows bilgisayarda bu aşağıdaki yordamı izleyin.
1. Dışarı aktarılan W-Fi-profilleri için **c:\WiFi** gibi bir yerel klasör oluşturun.
1. Yönetici olarak bir Komut İstemi açın.
1. **netsh wlan show profiles** komutunu çalıştırın ve dışarı aktarmak istediğiniz profilin adını not edin. Bu örnekte profil adı **WiFiName** şeklindedir.
1. Şu komutu çalıştırın: **netsh wlan export profile name="ProfileName" folder=c:\Wifi**. Bu komut hedef klasörünüzde **Wi-Fi-WiFiName.xml** adlı bir Wi-Fi profili dosyası oluşturur.

## <a name="import-the-wi-fi-settings-into-intune"></a>Wi-Fi ayarlarını Intune'da içeri aktarma

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde, **Cihaz yapılandırması**’nı seçin.
4. **Yönet** bölümü altındaki **Cihaz yapılandırması** bölmesinden **Profiller**’i seçin.
5. Profiller bölmesinde **Profil oluştur**’a tıklayın.
6. **Profil oluştur** bölmesinde, cihaz kısıtlama profili için **Ad** ve **Açıklama** girin.


   > [!WARNING]
   > Adın Wi-Fi profili xml’indeki ad özniteliği ile aynı olması **gereklidir**, yoksa işlem başarısız olur.

7. **Platform** açılan listesinden **Windows 8.1 ve üzeri**’ni seçin.
8. **Profil** türü açılan listesinden **Wi-Fi içeri aktarma**’yı seçin.
9. **Wi-Fi** bölmesinde, aşağıdaki ayarları yapılandırın:
    - **Bağlantı adı** Wi-Fi bağlantısının adını girin. Bu ad, kullanılabilir Wi-Fi ağlarına göz atan son kullanıcılara görüntülenir.
    - **Profil XML** Intune’da içine aktarmak istediğiniz Wi-Fi profili ayarlarını içeren XML dosyasını seçmek için gözat düğmesine tıklayın.
    - **Dosya içeriği** Seçtiğiniz yapılandırma profili için XML kodunu görüntüler.
10. Bitirdiğinizde **Tamam**’ı seçin, **Profil Oluştur** bölmesine gidin ve **Oluştur**’u seçin.

Profil oluşturulur ve profil listesi bölmesinde görüntülenir.
