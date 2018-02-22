---
title: "Windows 8.1 ve üzeri için Wi-Fi ayarlarını içeri aktarma"
titleSuffix: Azure portal
description: "Wi-Fi ayarlarını Windows’dan Intune Wi-Fi profiline aktarma.\""
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 1/25/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5b4b77f9c9c1c957e3332c20e010a5e8e8ec2b56
ms.sourcegitcommit: 93622d740cbd12043eedc25a9699cc4256e23e7e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune"></a>Microsoft Intune’da Windows 8.1 ve üzeri cihazlar için Wi-Fi ayarlarını içeri aktarma

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Windows 8.1 veya Windows 10 masaüstü veya mobil ya da Windows Holographic for Business çalıştıran cihazlar için önceden bir dosyaya aktarılmış Wi-Fi yapılandırma profilini içeri aktarabilirsiniz.

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Windows cihazından Wi-Fi ayarlarını dışarı aktarma

Windows'da **netsh wlan** yardımcı programını kullanarak var olan bir Wi-Fi profilini Intune tarafından okunabilen bir XML dosyasına aktarın. Gerekli WiFi profilinin zaten yüklü olduğu bir Windows bilgisayarda bu aşağıdaki yordamı izleyin.
1. Dışarı aktarılan W-Fi-profilleri için **c:\WiFi** gibi bir yerel klasör oluşturun.
1. Yönetici olarak bir Komut İstemi açın.
1. **netsh wlan show profiles** komutunu çalıştırın ve dışarı aktarmak istediğiniz profilin adını not edin. Bu örnekte profil adı **WiFiName** şeklindedir.
1. Şu komutu çalıştırın: **netsh wlan export profile name="ProfileName" folder=c:\Wifi**. Bu komut hedef klasörünüzde **Wi-Fi-WiFiName.xml** adlı bir Wi-Fi profili dosyası oluşturur.

## <a name="import-the-wi-fi-settings-into-intune"></a>Wi-Fi ayarlarını Intune'da içeri aktarma

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihaz yapılandırması**’nı seçin.
2. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
3. Profiller dikey penceresinde **Profil Oluştur**’a tıklayın.
4. **Profil Oluştur** dikey penceresinde, cihaz kısıtlama profili için **Ad** ve **Açıklama** girin.

   > [!WARNING]
   > Adın Wi-Fi profili xml’indeki ad özniteliği ile aynı olması **gereklidir**, yoksa işlem başarısız olur.

5. **Platform** açılan listesinden **Windows 8.1 ve üzeri**’ni seçin.
6. **Profil** türü açılan listesinden **Wi-Fi içeri aktarma**’yı seçin.
7. **Wi-Fi Temel** dikey penceresinde aşağıdaki ayarları yapılandırın:
    - **Bağlantı adı** Wi-Fi bağlantısının adını girin. Bu ad, kullanılabilir Wi-Fi ağlarına göz atan son kullanıcılara görüntülenir.
    - **Profil XML** Intune’da içine aktarmak istediğiniz Wi-Fi profili ayarlarını içeren XML dosyasını seçmek için gözat düğmesine tıklayın.
    - **Dosya içeriği** Seçtiğiniz yapılandırma profili için XML kodunu görüntüler.
8. Bitirdiğinizde **Profil Oluştur** dikey penceresine dönün ve **Oluştur**’a basın.

Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.
