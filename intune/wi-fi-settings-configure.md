---
title: "Intune Wi-Fi ayarlarını yapılandırma"
titleSuffix: Microsoft Intune
description: "Microsoft Intune’u yönettiğiniz cihazlarda Wi-Fi bağlantılarını yapılandırmak için kullanmayı öğrenin."
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
ms.openlocfilehash: 21bc79d3440e57ec91f7e4482112d77cf233575f
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2018
---
# <a name="how-to-configure-wi-fi-settings-in-microsoft-intune"></a>Microsoft Intune’da Wi-Fi ayarlarını yapılandırma

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune Wi-Fi profillerini, kuruluşunuzdaki cihazlara ve kullanıcılara kablosuz ağ ayarlarını atamak için kullanın. Bir Wi-Fi profili atadığınızda, kullanıcılarınız ağı kendileri yapılandırmak zorunda kalmadan kurumsal Wi-Fi ağınıza erişir.

Örneğin, Contoso Wi-Fi adlı yeni bir Wi-Fi ağı kurdunuz ve tüm iOS cihazlarını bu ağa bağlanacak şekilde ayarlamak istiyorsunuz. İşlem şöyledir:

1. Contoso Wi-Fi kablosuz ağına bağlanmak için gerekli ayarları içeren bir Wi-Fi profili oluşturun.
2. Profili, iOS cihazlarının tüm kullanıcılarını içeren bir gruba atayın.
3. Kullanıcılar yeni Contoso Wi-Fi ağını cihazlarındaki kablosuz ağ listesinde bulur ve bu ağa kolayca bağlanabilir.

## <a name="supported-device-platforms"></a>Desteklenen cihaz platformları

Wi-Fi profilleri aşağıdaki cihaz platformlarını destekler:

- Android 4 ve üzeri
- Android for Work
- iOS 8.0 ve üzeri
- macOS (Mac OS X 10.9 ve üzeri)

Windows 8.1, Windows 10, Windows 10 Mobile ve Windows Holographic for Business çalıştıran cihazlarda, daha önce başka bir cihazdan dışarı aktarılmış olan bir Wi-Fi yapılandırmasını içeri aktarabilirsiniz.

Bu konu başlığı altında verilen bilgileri kullanarak Wi-Fi profilini yapılandırmanın temellerini öğrenin ve sonra cihaza özgü bilgiler için her platformla ilgili olarak sağlanan konuları okuyun.

## <a name="create-a-device-profile-containing-wi-fi-settings"></a>Wi-Fi ayarlarını içeren bir cihaz profili oluşturma

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihaz yapılandırması**’nı seçin.
2. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
3. Profiller dikey penceresinde **Profil Oluştur**’u seçin.
4. **Profil Oluştur** dikey penceresinde, Wi-Fi profili için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden, Wi-Fi ayarlarını uygulamak istediğiniz cihaz platformunu seçin. Şu anda, Wi-Fi ayarları için aşağıdaki platformlardan birini seçebilirsiniz:
    - **Android**
    - **Android for Work**
    - **Android**
    - **macOS**
    - **Windows 8.1 ve üzeri (profili içeri aktarın)**

   > [!IMPORTANT]
   > Windows Holographic for Business dahil olmak üzere Windows 10 çalıştıran cihazlar için bir profil oluşturuyorsanız, **Windows 8.1 ve üzeri** platformunu seçmeniz gerekir. **Windows 10 ve üzeri** platformu bir Wi-Fi profil türü içermez. 

6. Apple ve Android cihazlarda, açılan **WiFi türü** listesinden **Temel** veya **Kurumsal** türlerinden birini seçin. Ağ adı ve SSID gibi temel özellikleri sağlamak için **Temel**’i kullanabilirsiniz. **Kurumsal**, Wi-Fi ağınız bu protokolü kullanıyorsa Genişletilebilir Kimlik Doğrulama Protokolü (EAP) gibi daha gelişmiş bilgileri sağlamanıza olanak tanır. 

   **Wi-Fi içeri aktarma** profili (Windows 8.1 ve üzeri için), Wi-Fi ayarlarını daha önce başka cihazdan dışarı aktarmış olduğunuz bir XML dosyası olarak içeri aktarmanıza olanak tanır.
1. Seçtiğiniz platforma bağlı olarak, yapılandırabileceğiniz ayarlar farklılık gösterir. Her platformun ayrıntılı ayarları için aşağıdaki konulardan birine gidin:
    - [Android ve Android for Work ayarları](wi-fi-settings-android.md)
    - [iOS ayarları](wi-fi-settings-ios.md)
    - [macOS ayarları](wi-fi-settings-macos.md)
    - [Windows 8.1 ve üzeri ayarları](wi-fi-settings-import-windows-8-1.md) (Windows Holographic for Business dahil)
1. Bitirdiğinizde **Profil Oluştur** dikey penceresine dönün ve **Oluştur**’a basın.

Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.

## <a name="next-steps"></a>Sonraki adımlar

Devam edip bu profili gruplara atamak isterseniz, bkz. [Cihaz profillerini atama](device-profile-assign.md).
