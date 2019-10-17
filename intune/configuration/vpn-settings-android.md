---
title: Microsoft Intune-Azure 'da Android cihazları için VPN ayarlarını kullanma | Microsoft Docs
description: Microsoft Intune 'de Android cihazlarda VPN bağlantıları oluşturmak için tüm ayarları görüntüleyin. VPN sunucusunun bağlantı adını, IP adresini veya FQDN 'sini girin, kullanıcıların kimlik doğrulamasını yapın ve Citrix, SonicWall, Check Point kapsül ve Pulse Secure bağlantı türlerini seçin.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/06/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8d9fefc2413e2dafbf5d0ad67ea15f5f8406cc1c
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506551"
---
# <a name="android-device-settings-to-configure-vpn-in-intune"></a>Intune 'da VPN yapılandırmak için Android cihaz ayarları

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bu makalede, Android cihazlarda denetleyebilmeniz için farklı VPN bağlantısı ayarları listelenir ve açıklanmaktadır. Mobil cihaz yönetimi (MDM) çözümünüzün bir parçası olarak, bu ayarları kullanarak bir VPN bağlantısı oluşturun, VPN 'in kimlik doğrulamasını yapın, bir VPN sunucusu türü seçin ve daha fazlasını yapın.

Bir Intune Yöneticisi olarak, Android cihazlara VPN ayarları oluşturabilir ve atayabilirsiniz. 

Intune 'da VPN profilleri hakkında daha fazla bilgi edinmek için bkz. [VPN profilleri](vpn-settings-configure.md).

## <a name="before-you-begin"></a>Başlamadan önce

[Bir cihaz yapılandırma profili oluşturun](vpn-settings-configure.md#create-a-device-profile)ve **Android**' i seçin.

## <a name="base-vpn"></a>Taban VPN

- **Bağlantı adı**: Bu bağlantı için bir ad girin. Cihazlarındaki kullanılabilir VPN bağlantılarına göz atan son kullanıcılar bu adı görür. Örneğin, şunu girin: `Contoso VPN`.
- **IP adresi veya FQDN**: Cihazların bağlandığı VPN sunucusunun IP adresini veya tam etki alanı adını (FQDN) girin. Örneğin, **192.168.1.1** veya **vpn.contoso.com** yazın.

  - **Kimlik doğrulama yöntemi**: Cihazların VPN sunucusunda kimliklerini nasıl doğrulayacaklarını seçin. Seçenekleriniz şunlardır:

    - **Sertifikalar**: Bağlantının kimliğini doğrulamak için mevcut bir SCEP veya PKCS sertifika profili seçin. [Sertifikaları yapılandırın](../protect/certificates-configure.md), sertifika profili oluşturma adımlarını listeler.
    - **Kullanıcı adı ve parola**: VPN sunucusunda oturum açarken son kullanıcılardan Kullanıcı adını ve parolasını girmesi istenir.

- **Bağlantı türü**: VPN bağlantısının türünü seçin. Seçenekleriniz şunlardır:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 erişimi**
  - **Pulse Secure**
  - **Citrix SSO**

- **Parmak izi** (yalnızca Check Point Capsule VPN): VPN sunucusunun güvenilir olduğunu doğrulamak için **Contoso Parmak İzi Kodu** gibi bir dize girin. İstemcinin aynı parmak izine sahip herhangi bir sunucuya güvenmesi için istemciye bir parmak izi gönderilir. Cihazda parmak izi yoksa, parmak izini göstererek kullanıcıdan VPN sunucusuna güvenmesini ister. Kullanıcı parmak izini el ile doğrular ve bağlanmak için güvenmeyi seçer.
- **Citrix VPN öznitelikleri için anahtar ve değer çiftleri girin** (yalnızca Citrix): Citrix tarafından sağlanan anahtar ve değer çiftlerini girin. Bu değerler VPN bağlantısının özelliklerini yapılandırır. 

  Ayrıca, anahtarlar ve değer çiftleri ile bir virgülle ayrılmış değerler dosyası (. csv) **Içeri aktarabilirsiniz** . **Verilerin üst bilgileri** ve **anahtar** özelliklerini gözden geçirdiğinizden emin olun.

  Anahtar ve değer çiftlerinizi ekledikten sonra, verilerinizi bir. csv dosyasına yedeklemek için **dışarı aktar** ' ı kullanın.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).

[Android Enterprise](vpn-settings-android-enterprise.md), [iOS](vpn-settings-ios.md), [MacOS](vpn-settings-macos.md), [Windows 10 ve üzeri](vpn-settings-windows-10.md), [Windows 8.1](vpn-settings-windows-8-1.md)ve [Windows Phone 8,1](vpn-settings-windows-phone-8-1.md) cihazları için de VPN profilleri oluşturabilirsiniz.
