---
title: "Intune VPN ayarlarını yapılandırma"
titleSuffix: Azure portal
description: "Intune’u, yönettiğiniz cihazlarda VPN bağlantılarını yapılandırmak için kullanmayı öğrenin.\""
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
ms.openlocfilehash: 772b7f025adc7ae80d0f14c5c630209c4c7529b2
ms.sourcegitcommit: 93622d740cbd12043eedc25a9699cc4256e23e7e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-configure-vpn-settings-in-microsoft-intune"></a>Microsoft Intune’da VPN ayarlarını yapılandırma

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Sanal özel ağlar (VPN’ler), kullanıcılarınıza şirket ağınıza güvenli uzaktan erişim vermenize olanak tanır. Cihazlar VPN sunucusuyla bir bağlantı başlatmak için bir VPN bağlantısı profili kullanır. VPN ayarlarını kuruluşunuzdaki kullanıcılar ve cihazlara atamak için Microsoft Intune’da **VPN profilleri** kullanarak ağa kolay ve güvenli bir şekilde bağlanabilmelerini sağlayın.

Örneğin, tüm iOS cihazlara kurumsal ağ üzerindeki bir dosya paylaşımına bağlanmak için gereken ayarları sağlamak istediğinizi varsayın. Kurumsal ağa bağlanmak için gereken ayarları içeren bir VPN profili oluşturur ve ardından bu profili iOS cihazlarını kullanan tüm kullanıcılara atarsınız. Kullanıcılar VPN bağlantısını kullanılabilir ağlar listesinde görür ve ağa kolaylıkla bağlanabilir.

## <a name="vpn-connection-types"></a>VPN bağlantısı türleri

VPN profillerini oluştururken aşağıdaki bağlantı türlerini kullanabilirsiniz:

|Bağlantı türü|Android<br>Android for Work|iOS|Mac OS|Windows Phone 8.1|Windows 8.1|Windows 10|
|-|-|-|-|-|-|-|
|Pulse Secure|Evet|Evet|Evet|Evet|Evet|Evet|
|Cisco (IPSec)|Hayır|Evet|Hayır|Hayır|Hayır|Hayır|
|Citrix|Evet|Evet|Hayır|Hayır|Hayır|Evet|
|F5 Edge İstemcisi|Evet|Evet|Evet|Evet|Evet|Evet|
|Dell SonicWALL Mobile Connect|Evet|Evet|Evet|Evet|Evet|Evet|
|Check Point Capsule VPN|Evet|Evet|Evet|Evet|Evet|Evet|
|Cisco AnyConnect|Evet|Evet|Evet|Hayır|Hayır|Hayır|
|Otomatik|Hayır|Hayır|Hayır|Hayır|Hayır|Evet|
|IKEv2|Hayır|Hayır|Hayır|Hayır|Hayır|Evet|
|L2TP|Hayır|Hayır|Hayır|Hayır|Hayır|Evet|
|PPTP|Hayır|Hayır|Hayır|Hayır|Hayır|Evet|
|Özel|Hayır|Evet|Evet|Hayır|Hayır|Hayır|


> [!IMPORTANT]
> Bir cihaza atanan VPN profillerini kullanmadan önce profil için geçerli VPN uygulamasını yüklemeniz gerekir. Uygulamayı Intune kullanarak atamanıza yardımcı olması için [Microsoft Intune'da uygulama yönetimi nedir](app-management.md) konusunda verilen bilgileri kullanabilirsiniz.  

[Özel VPN profilleri oluşturma](custom-vpn-profiles-create.md) konu başlığı altında verilen URI ayarlarını kullanarak özel VPN profilleri oluşturmayı öğrenin.     

## <a name="create-a-device-profile-containing-vpn-settings"></a>VPN ayarlarını içeren bir cihaz profili oluşturma

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihaz yapılandırması**’nı seçin.
2. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
3. Profiller dikey penceresinde **Profil Oluştur**’u seçin.
4. **Profil Oluştur** dikey penceresinde, VPN profili için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden, VPN ayarlarını uygulamak istediğiniz cihaz platformunu seçin. Şu anda, VPN cihaz ayarları için aşağıdaki platformlardan birini seçebilirsiniz:
    - **Android**
    - **Android for Work**
    - **Android**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 ve üzeri**
    - **Windows 10 ve üzeri**
6. **Profil** türü açılan listesinden **VPN**’yi seçin.
7. Seçtiğiniz platforma bağlı olarak, yapılandırabileceğiniz ayarlar farklılık gösterir. Her platformun ayrıntılı ayarları için aşağıdaki konulardan birine gidin:
    - [Android ve Android for Work ayarları](vpn-settings-android.md)
    - [iOS ayarları](vpn-settings-ios.md)
    - [macOS ayarları](vpn-settings-macos.md)
    - [Windows Phone 8.1 ayarları](vpn-settings-windows-phone-8-1.md)
    - [Windows 8.1 ayarları](vpn-settings-windows-8-1.md)
    - [Windows 10 ayarları](vpn-settings-windows-10.md) (Windows Holographic for Business dahil)
8. Bitirdiğinizde **Profil Oluştur** dikey penceresine dönün ve **Oluştur**’a basın.

Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.
Devam edip bu profili gruplara atamak isterseniz, bkz. [Cihaz profillerini atama](device-profile-assign.md).


## <a name="methods-of-securing-vpn-profiles"></a>VPN profillerini güvenli hale getirme yöntemleri

VPN profilleri, farklı üreticilerden farklı bağlantı türleri ve farklı protokoller kullanabilir. Bu bağlantılar genellikle iki yöntemden biri kullanılarak güvenli hale getirilir.

### <a name="certificates"></a>Sertifikalar

VPN profilini oluştururken, Intune’da önceden oluşturduğunuz bir SCEP veya PKCS sertifika profilini seçersiniz. Bu kimlik sertifikası olarak bilinir. Kullanıcının cihazının bağlanmasına izin verildiğini belirtmek için oluşturduğunuz bir güvenilir sertifika profiline (veya *kök sertifikaya*) göre kimlik doğrulaması yapmak için kullanılır. Güvenilir sertifika, VPN bağlantısının kimliğini doğrulayan bilgisayara atanır. Bu, genellikle VPN sunucusudur.

Intune’da sertifika profillerini oluşturma ve kullanma hakkında daha fazla bilgi için bkz. [Microsoft Intune ile sertifikaları yapılandırma](certificates-configure.md).

### <a name="user-name-and-password"></a>Kullanıcı adı ve parola

Kullanıcı, kullanıcı adı ve parola girerek VPN sunucusunda kimliğini doğrular.
