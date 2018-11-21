---
title: Microsoft Intune - Azure’da cihazlar için Wi-Fi profili oluşturma | Microsoft Docs
description: Microsoft Intune’da Wi-Fi cihaz yapılandırma profilleri oluşturmak için adımları inceleyin. Android, Android Kurumsal, Android bilgi noktası, iOS, macOS, Windows 10 ve sonrası ve Windows Holographic for Business için profil oluşturun. Bu profilleri kullanarak sertifika kullanmak için bir Wi-Fi bağlantısı oluşturmak, EAP türü seçmek, kimlik doğrulama yöntemi seçmek, proxy etkinleştirmek gibi pek çok şey yapabilirsiniz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: a338cce6249cc7c5214a9d69a897cad3eaa09e93
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52188407"
---
# <a name="add-and-use-wi-fi-settings-on-your-devices-in-microsoft-intune"></a>Microsoft Intune’da cihazlarınız için Wi-Fi ayarları ekleme ve kullanma

Microsoft Intune Wi-Fi profillerini, kuruluşunuzdaki cihazlara ve kullanıcılara kablosuz ağ ayarlarını atamak için kullanın. Bir Wi-Fi profili atadığınızda, kullanıcılarınız ağı kendileri yapılandırmadan kuruluşunuzun Wi-Fi ağına erişebilirler.

Örneğin Contoso Wi-Fi adında yeni bir Wi-Fi ağı kurdunuz. Ağı kurduktan sonra tüm iOS cihazları bu ağa bağlanacak şekilde ayarlamak isteyeceksiniz. İşlem şöyledir:

1. Contoso Wi-Fi kablosuz ağına bağlanmak için gerekli ayarları içeren bir Wi-Fi profili oluşturun.
2. Profili, tüm iOS cihaz kullanıcılarını içeren bir gruba atayın.
3. Kullanıcılar, yeni Contoso Wi-Fi ağını cihazlarındaki kablosuz ağ listesinde bulabilirler. Daha sonra seçtiğiniz kimlik doğrulama yöntemini kullanarak ağa bağlanabilirler.

Bir Wi-Fi profili oluşturmak için bu makaledeki adımları kullanın. Daha sonra platformlara özgü ayarlar ve ayrıntılarla ilgili konuları gözden geçirin.

## <a name="supported-device-platforms"></a>Desteklenen cihaz platformları

Wi-Fi profilleri aşağıdaki cihaz platformlarını destekler:

- Android 4 ve üzeri
- Android Kurumsal ve bilgi noktası
- iOS 8.0 ve üzeri
- macOS (Mac OS X 10.11 ve üzeri)
- Windows 10 ve sonrası, Windows 10 Mobile ve Windows Holographic for Business

> [!NOTE]
> Windows 8.1 çalıştıran cihazlarda daha önce başka bir cihazdan dışarı aktarılmış olan bir Wi-Fi yapılandırmasını içeri aktarabilirsiniz.

## <a name="create-a-wi-fi-device-profile"></a>Bir Wi-Fi cihaz profili oluşturma

1. [Azure portalında](https://portal.azure.com) **Tüm Hizmetler**’i seçin > **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin. 
2. **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**'u seçin.
3. Wi-Fi profili için bir **Ad** ve **Açıklama** girin.
4. Açılan **Platform** listesinde Wi-Fi ayarlarının uygulanacağı cihaz platformunu seçin. Seçenekleriniz şunlardır:

    - **Android**
    - **Android kurumsal**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
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

Profil oluşturuldu ancak hiçbir şey yapmıyor. Daha sonra [bu profili atayın](device-profile-assign.md).
