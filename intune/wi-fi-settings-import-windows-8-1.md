---
title: Microsoft Intune’da Windows cihazları için Wi-Fi ayarlarını içeri aktarma - Azure | Microsoft Docs
description: Netsh wlan kullanarak Wi-Fi ayarlarını bir Windows cihazından dışarı aktarın. Ardından, Windows 8.1, Windows 10 ve Windows Holographic for Business çalıştıran cihazlara Wi-Fi profili oluşturmak için bu dosyayı Intune’da içeri aktarın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e32749225af3f19ab07decbcf1488595b7d946fd
ms.sourcegitcommit: cff65435df070940da390609d6376af6ccdf0140
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2018
ms.locfileid: "49424875"
---
# <a name="import-wi-fi-settings-for-windows-devices-in-intune"></a>Intune’da Windows cihazları için Wi-Fi ayarlarını içeri aktarma

Windows çalıştıran cihazlar için daha önce bir dosyaya aktarılmış Wi-Fi yapılandırma profilini içeri aktarabilirsiniz. **Windows 10 ve sonrası cihazlar için doğrudan Intune’da [Wi-Fi profili de oluşturabilirsiniz](wi-fi-settings-windows.md)**.

Şunun için geçerlidir:  
- Windows 8.1 ve üzeri
- Windows 10 ve üzeri
- Windows 10 masaüstü veya mobil
- Windows 10 Holographic for Business

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Windows cihazından Wi-Fi ayarlarını dışarı aktarma

Windows’ta `netsh wlan` kullanarak mevcut bir Wi-Fi profilini Intune tarafından okunabilen bir XML dosyasına aktarın. Profili başarıyla kullanmak için anahtarın düz metin olarak dışarı aktarılması gerekir.

Gerekli WiFi profilinin zaten yüklü olduğu bir Windows bilgisayarda aşağıdaki adımları kullanın:

1. Dışarı aktarılan W-Fi-profilleri için **c:\WiFi** gibi bir yerel klasör oluşturun.
2. Yönetici olarak bir Komut İstemi açın.
3. `netsh wlan show profiles` komutunu çalıştırın ve dışarı aktarmak istediğiniz profilin adını not edin. Bu örnekte profil adı **WiFiName** şeklindedir.
4. `netsh wlan export profile name="ProfileName" folder=c:\Wifi` komutunu çalıştırın. Bu komut, hedef klasörünüzde **Wi-Fi-WiFiName.xml** adlı bir Wi-Fi profil dosyası oluşturur.

## <a name="import-the-wi-fi-settings-into-intune"></a>Wi-Fi ayarlarını Intune'da içeri aktarma

1. [Azure portalında](https://portal.azure.com) **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. Cihaz kısıtlama profili için bir **Ad** ve **Açıklama** girin.

    > [!IMPORTANT]
    > - Adın Wi-Fi profili xml’indeki ad özniteliği ile aynı olması **gereklidir**. Yoksa işlem başarısız olur.
    > - Önceden paylaşılan anahtar içeren bir Wi-Fi profilini dışarı aktarıyorsanız komuta `key=clear` eklemeniz **gereklidir**. Örneğin şunu girin: `netsh wlan export profile name="ProfileName" key=clear folder=c:\Wifi`
    > - Windows 10 ile önceden paylaşılan bir anahtarı kullanmak, Intune’da bir düzeltme hatasına sebep olur. Bu durumda, Wi-Fi profili cihaza düzgün bir şekilde atanır ve profil beklendiği gibi çalışır.
    > - Önceden paylaşılan anahtar içeren bir Wi-Fi profilini dışarı aktarıyorsanız dosyanın korumalı olduğundan emin olun. Anahtar düz metin biçimindedir, yani anahtarı korumak sizin sorumluluğunuzdadır.

4. **Platform**’da **Windows 8.1 ve üzerini** seçin.
5. **Profil türü**’nde **Wi-Fi içeri aktarma**’yı seçin.
6. Aşağıdaki ayarları yapılandırın:
    - **Bağlantı adı**: Wi-Fi bağlantısı için bir ad girin. Bu ad, kullanılabilir Wi-Fi ağlarına göz atan son kullanıcılara görüntülenir.
    - **Profil XML’i**: Gözat düğmesini seçin ve içeri aktarmak istediğiniz Wi-Fi profil ayarlarını içeren XML dosyasını seçin.
    - **Dosya içeriği**: Seçtiğiniz yapılandırma profili için XML kodunu görüntüler.
7. İşiniz bittiğinde **Tamam** > **Oluştur**’u seçerek değişikliklerinizi kaydedin. Profil oluşturuldu ve profiller listesinde gösteriliyor.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturuldu ancak hiçbir şey yapmıyor. Daha sonra [bu profili atayın](device-profile-assign.md).

## <a name="more-resources"></a>Daha fazla kaynak

Diğer kullanılabilir platformlar dahil olmak üzere [Wi-Fi ayarlarına genel bakış](wi-fi-settings-configure.md).