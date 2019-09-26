---
title: Microsoft Intune-Azure 'da cihazlara VPN ayarları ekleme | Microsoft Docs
description: Android, Android Enterprise, iOS, macOS ve Windows cihazlarında, Microsoft Intune ' de sanal özel ağ (VPN) bağlantıları oluşturmak için yerleşik ayarları kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d43c41e0ba6c2f8ccaccdfd0804b02f501b9e3a1
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2019
ms.locfileid: "71302787"
---
# <a name="create-vpn-profiles-to-connect-to-vpn-servers-in-intune"></a>Intune 'da VPN sunucularına bağlanmak için VPN profilleri oluşturma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Sanal özel ağlar (VPN 'Ler), kullanıcılarınızın kuruluş ağınıza güvenli uzaktan erişim olanağı sağlar. Cihazlar VPN sunucusuyla bir bağlantı başlatmak için bir VPN bağlantısı profili kullanır. Microsoft Intune ' deki **VPN profilleri** , kuruluşunuzun kullanıcılara ve cihazlarına VPN ayarları atayarak kurumsal ağınıza kolayca ve güvenli bir şekilde bağlanabilmelerini sağlar.

Örneğin, kuruluş ağındaki bir dosya paylaşımıyla bağlantı kurmak için gerekli ayarlarla tüm iOS cihazlarını yapılandırmak istiyorsunuz. Bu ayarları içeren bir VPN profili oluşturursunuz. Ardından, bu profili iOS cihazlarından oluşan tüm kullanıcılara atarsınız. Kullanıcılar, VPN bağlantısını kullanılabilir ağlar listesinde görür ve ağa kolaylıkla bağlanabilir.

> [!NOTE]
> Aşağıdaki platformlar için VPN profilleri oluşturmak üzere [Intune özel yapılandırma ilkelerini](custom-settings-configure.md) kullanabilirsiniz:
>
> * Android 4 ve üzeri
> * Windows 8.1 ve üzeri çalıştıran kayıtlı cihazlar
> * Windows Phone 8.1 ve üzeri
> * Windows 10 masaüstü çalıştıran kayıtlı cihazlar
> * Windows 10 Mobile
> * Windows 10 Holographic for Business

## <a name="vpn-connection-types"></a>VPN bağlantısı türleri

VPN profillerini oluştururken aşağıdaki bağlantı türlerini kullanabilirsiniz:

|Bağlantı türü|Platform|
|-|-|
|Otomatik|Windows 10|
|Check Point Capsule VPN|-Android<br/>-Android kurumsal iş profilleri<br/>-iOS<br/>-macOS<br/>-Windows 10<br/>-Windows 8.1<br/>-Windows Phone 8,1|
|Cisco AnyConnect|-Android<br/>-Android kurumsal iş profilleri<br/>-Android kurumsal cihaz sahibi (tam olarak yönetilen)<br/>-iOS<br/>-macOS|
|Cisco (IPSec)|iOS|
|Citrix SSO|-Android<br/>-Android kurumsal iş profilleri: [Uygulama yapılandırma ilkesini](app-configuration-policies-use-android.md) kullanma<br/>-iOS<br/>-Windows 10|
|Özel VPN|-iOS<br/>-macOS|
|F5 Access|-Android<br/>-Android kurumsal iş profilleri<br/>-Android kurumsal cihaz sahibi (tam olarak yönetilen)<br/>-iOS<br/>-macOS<br/>-Windows 10<br/>-Windows 8.1<br/>-Windows Phone 8,1|
|IKEv2|Windows 10|
|L2TP|Windows 10|
|Palo Alto Networks GlobalProtect|-Android kurumsal iş profilleri: [Uygulama yapılandırma ilkesini](app-configuration-policies-use-android.md) kullanma<br/>-iOS<br/>-Windows 10|
|PPTP|Windows 10|
|Pulse Secure|-Android<br/>-Android kurumsal iş profilleri<br/>-Android kurumsal cihaz sahibi (tam olarak yönetilen)<br/>-iOS<br/>-macOS<br/>-Windows 10<br/>-Windows 8.1<br/>-Windows Phone 8,1|
|SonicWall Mobile Connect|-Android<br/>-Android kurumsal iş profilleri<br/>-iOS<br/>-macOS<br/>-Windows 10<br/>-Windows 8.1<br/>-Windows Phone 8,1|
|Zscaler|-Android kurumsal iş profilleri: [Uygulama yapılandırma ilkesini](app-configuration-policies-use-android.md) kullanma<br/>-iOS|

> [!IMPORTANT]
> Bir cihaza atanan VPN profillerini kullanmadan önce profil için geçerli VPN uygulamasını yüklemeniz gerekir. Uygulamayı Intune kullanarak atamanıza yardımcı olması için [Microsoft Intune'da uygulama yönetimi nedir?](app-management.md) makalesinde verilen bilgileri kullanabilirsiniz.  

[Özel ayarları olan bir profil oluşturma](custom-settings-configure.md) konu başlığı altında verilen URI ayarlarını kullanarak özel VPN profilleri oluşturmayı öğrenin.

## <a name="create-a-device-profile"></a>Bir cihaz profili oluşturma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da **cihaz yapılandırma** > **profilleri** > **Profil oluştur**' u seçin.
2. Aşağıdaki özellikleri girin:

    - **Ad**: Profil için açıklayıcı bir ad girin. Profillerinizi daha sonra kolayca tanıyacak şekilde adlandırın. Örneğin, iyi bir profil adı **Şirket genelinde VPN profilidir**.
    - **Açıklama**: Profil için açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.
    - **Platform**: Cihazlarınızın platformu seçin. Seçenekleriniz şunlardır:

      - **Android**
      - **Yalnızca Android kurumsal** > **cihaz sahibi**
      - **Yalnızca Android kurumsal** > **iş profili**
      - **iOS/ıpados**
      - **macOS**
      - **Windows Phone 8.1**
      - **Windows 8.1 ve üzeri**
      - **Windows 10 ve üzeri**

    - **Profil türü**: **VPN**' yi seçin.

3. Seçtiğiniz platforma bağlı olarak, yapılandırabileceğiniz ayarlar farklılık gösterir. Her platformun ayrıntılı ayarları için aşağıdaki makalelere bakın:

    - [Android ayarları](vpn-settings-android.md)
    - [Android kurumsal ayarları](vpn-settings-android-enterprise.md)
    - [iOS/ıpados ayarları](vpn-settings-ios.md)
    - [macOS ayarları](vpn-settings-macos.md)
    - [Windows Phone 8.1 ayarları](vpn-settings-windows-phone-8-1.md)
    - [Windows 8.1 ayarları](vpn-settings-windows-8-1.md)
    - [Windows 10 ayarları](vpn-settings-windows-10.md) (Windows Holographic for Business dahil)

4. İşiniz bittiğinde, profilinizi **oluşturun** .

Profil oluşturulur ve profil listesinde görüntülenir. Bu profili gruplara atamak için bkz. [cihaz profillerini atama](device-profile-assign.md).

## <a name="secure-your-vpn-profiles"></a>VPN profillerinizin güvenliğini sağlama

VPN profilleri, farklı üreticilerden farklı bağlantı türleri ve farklı protokoller kullanabilir. Bu bağlantılar genellikle aşağıdaki yöntemlerle güvenli hale getirilir.

### <a name="certificates"></a>Sertifikalar

VPN profilini oluştururken, Intune’da önceden oluşturduğunuz bir SCEP veya PKCS sertifika profilini seçersiniz. Bu profil, kimlik sertifikası olarak bilinir. Kullanıcının cihazının bağlanmasına izin vermek için oluşturduğunuz bir güvenilir sertifika profiline (veya *kök sertifikaya*) göre kimlik doğrulaması yapmak için kullanılır. Güvenilir sertifika, VPN bağlantısının kimliğini doğrulayan bilgisayara atanır. Bu, genellikle VPN sunucusudur.

Intune’da sertifika profillerini oluşturma ve kullanma hakkında daha fazla bilgi için bkz. [Microsoft Intune ile sertifikaları yapılandırma](certificates-configure.md).

### <a name="user-name-and-password"></a>Kullanıcı adı ve parola

Kullanıcı, kullanıcı adı ve parola girerek VPN sunucusunda kimliğini doğrular.

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulduğunda henüz herhangi bir işlem gerçekleştirmez. Sonra, [profili](device-profile-assign.md) bazı cihazlara atayın.

Ayrıca, [Android](android-pulse-secure-per-app-vpn.md) ve [iOS](vpn-setting-configure-per-app.md) cihazlarında uygulama başına VPN 'ler oluşturabilir ve kullanabilirsiniz.
