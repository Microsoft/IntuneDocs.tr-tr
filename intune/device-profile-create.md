---
title: Microsoft Intune - Azure’da cihaz profilleri oluşturma | Microsoft Docs
description: Ekleyebilir veya cihaz yapılandırma profili Intune yapılandırabilirsiniz. Platform türünü seçin, ayarlarını yapılandırmak ve bir kapsam etiketi ekleyin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/21/2019
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
ms.openlocfilehash: 066508ba62d4b0ece3fe5a5e95b709a12832f1a0
ms.sourcegitcommit: 1069b3b1ed593c94af725300aafd52610c7d8f04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58394918"
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Microsoft Intune’da cihaz profili oluşturma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Cihaz profilleri eklemek ve ayarları yapılandırmak izin ve daha sonra bu ayarları, kuruluşunuzdaki cihazlara gönderin. [Cihaz profillerini kullanarak cihazlarınızı özellikleri ve ayarları uygula](device-profiles.md) yapabilecekleriniz de dahil olmak üzere daha fazla ayrıntıya gider.

Bu makalede:

- Profil oluşturma adımları listelenir.
- "Profil filtrelemek için" bir kapsam etiketi ekleme işlemi gösterilmektedir.
- Cihaz profilleri ve tüm profil güncelleştirmeleri aldığınızda döngü sürelerini iade yenileme listeler.

## <a name="create-the-profile"></a>Profili oluşturma

1. İçinde [Azure portalında](https://portal.azure.com)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.

2. **Cihaz yapılandırması**’nı seçin. Aşağıdaki seçenekleriniz vardır:

    - **Genel Bakış**: Profillerinizin durumunu listeler ve kullanıcılara ve cihazlara atadığınız Profiller hakkında ek ayrıntılar sağlar.
    - **Yönetme**: Cihaz profilleri oluşturma, özel yükleme [PowerShell betikleri](intune-management-extension.md) profil içinde çalışmak ve veri planları kullanarak cihazlara [Esım](esim-device-configuration.md).
    - **İzleyici**: Bir profilin başarı veya başarısızlık durumunu denetleyin ve ayrıca profillerinize ilişkin günlükleri görüntüleyin.
    - **Kurulum**: Bir SCEP veya PFX sertifika yetkilisi ekleyin veya etkinleştirme [Telekom Gider Yönetimi](telecom-expenses-monitor.md) profilinde.

3. Seçin **profilleri** > **profili oluşturma**. Aşağıdaki özellikleri girin:

   - **Ad**: Profil için açıklayıcı bir ad girin.
   - **Açıklama**: Profil için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
   - **Platform**: Cihazlarınızın platformu seçin. Seçenekleriniz şunlardır:  

       - **Android**
       - **Android kurumsal**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 ve üzeri**
       - **Windows 10 ve üzeri**

   - **Profil türü**: Oluşturmak istediğiniz ayarlarının türünü seçin. Gösterilen listesi bağlıdır **platform** belirleyin.
   - **Ayarları**: Aşağıdaki makaleler her profil türü için ayarları açıklar:

       - [Yönetim Şablonları](administrative-templates-windows.md)
       - [Özel](custom-settings-configure.md)
       - [Teslim iyileştirme](delivery-optimization-windows.md)
       - [Cihaz özellikleri](device-features-configure.md)
       - [Cihaz kısıtlamaları](device-restrictions-configure.md)
       - [Sürüm yükseltme ve modu anahtarı](edition-upgrade-configure-windows-10.md)
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

     Örneğin, **iOS** platformu, profil türü seçeneklerinizi aşağıdaki profile benzer görünmelidir:

     ![Intune'da iOS profili oluşturma](./media/create-device-profile.png)

4. İşiniz bittiğinde seçin **Tamam** > **Oluştur** yaptığınız değişiklikleri kaydedin. Profil oluşturulur ve listede gösterilen.

## <a name="scope-tags"></a>Kapsam etiketleri

Ayarları ekledikten sonra bir kapsam etiketi profiline ekleyebilirsiniz. Kapsam etiketleri atayabilir ve ilkeleri ik ya da tüm ABD NC çalışan gibi belirli gruplara filtre.

Kapsam etiketleri ve neler yapabileceğiniz hakkında daha fazla bilgi için bkz. [kullanım RBAC ve kapsam etiketleri için Dağıtılmış BT](scope-tags.md).

### <a name="add-a-scope-tag"></a>Kapsam etiketi Ekle

1. Seçin **kapsam (etiketler)**.
2. Seçin **Ekle** yeni bir kapsam etiketi oluşturmak için. Veya listeden mevcut bir kapsam etiketi seçin.
3. Değişikliklerinizi kaydetmek için **Tamam**’ı seçin.

## <a name="refresh-cycle-times"></a>Döngü sürelerini Yenile

Intune, yapılandırma profillerini güncelleştirmeleri denetlemek için aşağıdaki yenileme döngüsü kullanır:

| Platform | Yenileme döngüsü|
| --- | --- |
| iOS | 6 saatte bir |
| Mac OS | 6 saatte bir |
| Android | 8 saatte bir |
| Cihaz olarak kaydedilen Windows 10 bilgisayarlar | 8 saatte bir |
| Windows Phone | 8 saatte bir |
| Windows 8.1 | 8 saatte bir |

Son olarak cihazın kayıtlı, iade daha sık çalışır:

| Platform | Sıklık |
| --- | --- |
| iOS | 6 saat boyunca her 15 dakikada bir, daha sonra her 6 saatte bir |  
| Mac OS | 6 saat boyunca her 15 dakikada bir, daha sonra her 6 saatte bir | 
| Android | 15 dakika boyunca 3 dakikada bir, sonraki 2 saat boyunca 15 dakikada bir ve daha sonra 8 saatte bir | 
| Cihaz olarak kaydedilen Windows 10 bilgisayarlar | 30 dakika boyunca 3 dakikada bir, daha sonra 8 saatte bir | 
| Windows Phone | 15 dakika boyunca 5 dakikada bir, sonraki 2 saat boyunca 15 dakikada bir ve daha sonra 8 saatte bir | 
| Windows 8.1 | 15 dakika boyunca 5 dakikada bir, sonraki 2 saat boyunca 15 dakikada bir ve daha sonra 8 saatte bir | 

İstediğiniz zaman, kullanıcılar Şirket portalı uygulamasını açın ve hemen profili güncelleştirmeleri denetlemek için cihazı eşitleyebilir.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).
