---
title: Microsoft Intune - Azure’da cihaz profilleri oluşturma | Microsoft Docs
description: Microsoft Intune’da cihaz yapılandırma profili ekleyin veya yapılandırın. Platform türünü seçin, ayarları yapılandırın ve kapsam etiketi ekleyin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/03/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 08c6ece37a4ff6eceaa4df735f365453a4bc7d88
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59898862"
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Microsoft Intune’da cihaz profili oluşturma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Cihaz profillerini kullanarak ayar ekleyip yapılandırabilir ve daha sonra bu ayarları kuruluşunuzdaki cihazlara gönderebilirsiniz. [Cihaz profillerini kullanarak cihazlarınıza özellik ve ayar uygulama](device-profiles.md) sayfasında yapabileceğiniz işlemlerle ilgili ayrıntılı bilgilere yer verilmiştir.

Bu makalede:

- Profil oluşturma adımları listelenmiştir.
- Profili "filtrelemek" için kapsam etiketi ekleme adımları gösterilmektedir.
- Cihazların profilleri ve profil güncelleştirmelerini aldığı iade yenileme döngüsü süreleri listelenmiştir.

## <a name="create-the-profile"></a>Profili oluşturma

1. [Azure portalında](https://portal.azure.com) **Tüm Hizmetler**’i seçin > **Intune**’u filtreleyin ve **Intune**’u seçin.

2. **Cihaz yapılandırması**’nı seçin. Şu seçenekleriniz vardır:

    - **Genel Bakış**: Profillerinizin durumunu listeler, kullanıcılara ve cihazlara atadığınız profiller hakkında ek ayrıntılar sağlar.
    - **Yönet**: Cihaz profilleri oluşturun, profil içinde çalışacak özel [PowerShell betiklerini](intune-management-extension.md) karşıya yükleyin ve [eSIM](esim-device-configuration.md) ile cihazlara veri planı ekleyin.
    - **İzle**: Bir profilin başarı veya başarısızlık durumunu denetleyin ve ayrıca profillerinize ilişkin günlükleri görüntüleyin.
    - **Kurulum**: Bir SCEP veya PFX sertifika yetkilisi ekleyin veya profilde [Telekomünikasyon Gider Yönetimi](telecom-expenses-monitor.md)’ni etkinleştirin.

3. **Profiller** > **Profil Oluştur**'u seçin. Aşağıdaki özellikleri girin:

   - **Ad**: Profil için açıklayıcı bir ad girin. Profillerinizi daha sonra kolayca tanıyacak şekilde adlandırın. Örneğin **Şirketin tamamı için WP e-posta profili** gibi bir profil adı kullanabilirsiniz.
   - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
   - **Platform**: Cihazlarınızın platformu seçin. Seçenekleriniz şunlardır:  

       - **Android**
       - **Android kurumsal**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 ve üzeri**
       - **Windows 10 ve üzeri**

   - **Profil türü**: Oluşturmak istediğiniz ayar türünü seçin. Gösterilen liste, seçtiğiniz **platforma** bağlıdır.
   - **Ayarlar**: Aşağıdaki makaleler her profil türü için ayarları açıklar:

       - [Yönetim şablonları](administrative-templates-windows.md)
       - [Özel](custom-settings-configure.md)
       - [Teslim iyileştirme](delivery-optimization-windows.md)
       - [Cihaz özellikleri](device-features-configure.md)
       - [Cihaz kısıtlamaları](device-restrictions-configure.md)
       - [Sürüm yükseltme ve mod değiştirme](edition-upgrade-configure-windows-10.md)
       - [Eğitim](education-settings-configure.md)
       - [E-posta](email-settings-configure.md)
       - [Uç nokta koruması](endpoint-protection-configure.md)
       - [Kimlik koruması](identity-protection-configure.md)  
       - [Bilgi noktası](kiosk-settings.md)
       - [PKCS sertifikası](certficates-pfx-configure.md)
       - [SCEP sertifikası](certificates-scep-configure.md)
       - [Güvenilir sertifika](certificates-configure.md)
       - [Güncelleştirme ilkeleri](software-updates-ios.md)
       - [VPN](vpn-settings-configure.md)
       - [Wi-Fi](wi-fi-settings-configure.md)
       - [Windows Defender ATP](advanced-threat-protection.md)
       - [Windows Bilgi Koruması](windows-information-protection-configure.md)

     Örneğin **iOS** platformunu seçerseniz profil türü seçenekleriniz aşağıdaki profile benzer olacaktır:

     ![Intune'da iOS profili oluşturma](./media/create-device-profile.png)

4. Bitirdiğinizde, yaptığınız değişiklikleri kaydetmek için **Tamam** > **Oluştur**'u seçin. Profil oluşturulur ve listede gösterilir.

## <a name="scope-tags"></a>Kapsam etiketleri

Profilinize ayar ekledikten sonra bir kapsam etiketi de ekleyebilirsiniz. İK veya Merkez ofis çalışanları gibi belirli gruplara ilke atamak ve filtrelemek kapsam etiketlerini kullanabilirsiniz.

Kapsam etiketleri ve yapabilecekleriniz hakkında daha fazla bilgi için bkz. [Dağıtılmış BT için RBAC ve kapsam etiketlerini kullanma](scope-tags.md).

### <a name="add-a-scope-tag"></a>Kapsam etiketi ekleme

1. **Kapsam (Etiketler)** öğesini seçin.
2. **Ekle**'yi seçerek yeni bir kapsam etiketi oluşturun. İsterseniz listedeki kapsam etiketlerinden birini de seçebilirsiniz.
3. Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="refresh-cycle-times"></a>Yenileme döngüsü süreleri

Intune, yapılandırma profillerindeki güncelleştirmeleri denetlemek için aşağıdaki yenileme döngüsü sürelerini kullanır:

| Platform | Döngü süresi|
| --- | --- |
| iOS | 6 saatte bir |
| Mac OS | 6 saatte bir |
| Android | 8 saatte bir |
| Cihaz olarak kaydedilen Windows 10 bilgisayarlar | 8 saatte bir |
| Windows Phone | 8 saatte bir |
| Windows 8.1 | 8 saatte bir |

Cihaz son zamanlarda kaydedilmişse, iade daha sık çalıştırılır:

| Platform | Sıklık |
| --- | --- |
| iOS | 6 saat boyunca her 15 dakikada bir, daha sonra her 6 saatte bir |  
| Mac OS | 6 saat boyunca her 15 dakikada bir, daha sonra her 6 saatte bir | 
| Android | 15 dakika boyunca 3 dakikada bir, sonraki 2 saat boyunca 15 dakikada bir ve daha sonra 8 saatte bir | 
| Cihaz olarak kaydedilen Windows 10 bilgisayarlar | 30 dakika boyunca 3 dakikada bir, daha sonra 8 saatte bir | 
| Windows Phone | 15 dakika boyunca 5 dakikada bir, sonraki 2 saat boyunca 15 dakikada bir ve daha sonra 8 saatte bir | 
| Windows 8.1 | 15 dakika boyunca 5 dakikada bir, sonraki 2 saat boyunca 15 dakikada bir ve daha sonra 8 saatte bir | 

Kullanıcılar profil güncelleştirmelerini istedikleri zaman denetlemek için Şirket Portalı uygulamasını açıp cihazı eşitleyebilir.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).
