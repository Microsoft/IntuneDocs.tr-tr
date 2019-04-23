---
title: Microsoft Intune - Azure’da cihazlar için Wi-Fi profili oluşturma | Microsoft Docs
description: Microsoft Intune’da Wi-Fi cihaz yapılandırma profilleri oluşturmak için adımları inceleyin. Android, Android Kurumsal, Android bilgi noktası, iOS, macOS, Windows 10 ve sonrası ve Windows Holographic for Business için profil oluşturun. Bu profilleri kullanarak sertifika kullanmak için bir Wi-Fi bağlantısı oluşturmak, EAP türü seçmek, kimlik doğrulama yöntemi seçmek, proxy etkinleştirmek gibi pek çok şey yapabilirsiniz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/16/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 708c4d4572d84f17a711ac6deb16c02d82b9eea7
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61514991"
---
# <a name="add-and-use-wi-fi-settings-on-your-devices-in-microsoft-intune"></a>Microsoft Intune’da cihazlarınız için Wi-Fi ayarları ekleme ve kullanma

Wi-Fi ağ erişim elde etmek için çok sayıda mobil cihaz tarafından kullanılan kablosuz bir ağdır. Microsoft Intune kullanıcılara ve cihazlara kuruluşunuzdaki dağıtılabilir yerleşik Wi-Fi ayarlarını içerir. Bu ayar grubu bir "profili" olarak adlandırılır ve farklı kullanıcılara ve gruplara atanabilir. Kendilerine atandıktan sonra kullanıcılarınızın kuruluşunuzun Wi-Fi ağına kendilerini yapılandırmadan erişin.

Örneğin Contoso Wi-Fi adında yeni bir Wi-Fi ağı kurdunuz. Ağı kurduktan sonra tüm iOS cihazları bu ağa bağlanacak şekilde ayarlamak isteyeceksiniz. İşlem şöyledir:

1. Contoso Wi-Fi kablosuz ağa bağlamak ayarları içeren bir Wi-Fi profili oluşturun.
2. Profili iOS cihazlarının tüm kullanıcılarını içeren bir gruba atayın.
3. Kullanıcılar, yeni Contoso Wi-Fi ağını cihazlarındaki kablosuz ağ listesinde bulabilirler. Daha sonra seçtiğiniz kimlik doğrulama yöntemini kullanarak ağa bağlanabilirler.

Bu makalede bir Wi-Fi profili oluşturma adımları listelenir. Ayrıca, her platform için farklı ayarlar açıklayan bağlantılar içerir.

## <a name="supported-device-platforms"></a>Desteklenen cihaz platformları

Wi-Fi profilleri aşağıdaki cihaz platformlarını destekler:

- Android 4 ve üzeri
- Android Kurumsal ve bilgi noktası
- iOS 8.0 ve üzeri
- macOS (Mac OS X 10.11 ve üzeri)
- Windows 10 ve sonrası, Windows 10 Mobile ve Windows Holographic for Business

> [!NOTE]
> Windows 8.1 çalıştıran cihazlarda daha önce başka bir cihazdan dışarı aktarılmış olan bir Wi-Fi yapılandırmasını içeri aktarabilirsiniz.

## <a name="create-a-device-profile"></a>Bir cihaz profili oluşturma

1. [Azure portalında](https://portal.azure.com) **Tüm Hizmetler**’i seçin > **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin. 
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. Wi-Fi profili için bir **Ad** ve **Açıklama** girin.
4. Açılan **Platform** listesinde Wi-Fi ayarlarının uygulanacağı cihaz platformunu seçin. Seçenekleriniz şunlardır:

    - **Android**
    - **Android kurumsal**
    - **iOS**
    - **macOS**
    - **Windows 8.1 ve üzeri**
    - **Windows 10 ve üzeri**

5. **Profil Türü** olarak **Wi-Fi**’ı seçin.

    - Bilgi noktası olarak çalışan **Android Kurumsal** cihazlarda **Yalnızca cihaz sahibi** > **Wi-Fi**’ı seçebilirsiniz.
    - **Windows 8.1 ve sonrasında** **Wi-Fi içeri aktar**’ı seçebilirsiniz. Bu seçenek, Wi-Fi ayarlarını daha önce başka cihazdan dışarı aktarmış olduğunuz bir XML dosyası olarak içeri aktarmanıza olanak tanır.

6. Bazı Wi-Fi ayarları platformdan platforma farklılık gösterir. Belirli bir platforma yönelik ayarları görmek için aşağıdakilerden birini seçin:

    - [Android](wi-fi-settings-android.md)
    - [Android Kurumsal ve bilgi noktası](wi-fi-settings-android-enterprise.md)
    - [iOS](wi-fi-settings-ios.md)
    - [macOS](wi-fi-settings-macos.md)
    - [Windows 10 ve üzeri](wi-fi-settings-windows.md)
    - [Windows 8.1 ve sonrası](wi-fi-settings-import-windows-8-1.md), Windows Holographic for Business dahil

    Çoğu platformda **Temel** ve **Kurumsal** ayarları bulunur. **Temel**, ağ adı ve SSID gibi özellikler içerir. **Kurumsal**, Genişletilebilir Kimlik Doğrulama Protokolü (EAP) gibi daha gelişmiş bilgiler sağlamanıza olanak tanır.

7. Wi-Fi ayarlarınızı ekledikten sonra **Profil oluştur** > **Oluştur**’u seçerek yapılandırma profilini ekleyin. Profil oluşturulur ve profiller listesinde (**Cihaz yapılandırması** > **Profiller**) gösterilir.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturuldu ancak hiçbir şey yapmıyor. Ardından, [bu profili atarsınız](device-profile-assign.md) ve [atamanın durumunu izlemenize.](device-profile-monitor.md).
