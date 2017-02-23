---
title: "Intune Wi-Fi ayarlarını yapılandırma | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Yönettiğiniz cihazlarda Wi-Fi bağlantılarını yapılandırmak için Intune’u kullanmayı öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1fadb488-9c6c-43c1-ba23-8c69db633b96
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 89afae81076d563f4ebba289f8fa82eaea6ab234
ms.openlocfilehash: f91d919a72b7d14353250d2de532ab083a62c210


---

# <a name="how-to-configure-wi-fi-settings"></a>Wi-Fi ayarlarını yapılandırma 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Microsoft Intune Wi-Fi profillerini, kuruluşunuzdaki cihazlara ve kullanıcılara kablosuz ağ ayarlarını dağıtmak için kullanın. Bir Wi-Fi profili dağıttığınızda, kullanıcılarınız ağı kendileri yapılandırmak zorunda kalmadan kurumsal Wi-Fi ağınıza erişir.

Örneğin, Contoso Wi-Fi adlı yeni bir Wi-Fi ağı kurdunuz ve tüm iOS cihazlarını bu ağa bağlanacak şekilde ayarlamak istiyorsunuz. İşlem şöyledir:

1. Contoso Wi-Fi kablosuz ağına bağlanmak için gerekli ayarları içeren bir Wi-Fi profili oluşturun.
2. Profili, iOS cihazlarının tüm kullanıcılarını içeren bir gruba atayın.
3. Kullanıcılar yeni Contoso Wi-Fi ağını cihazlarındaki kablosuz ağ listesinde bulur ve bu ağa kolayca bağlanabilir.

Wi-Fi profilleri aşağıdaki cihaz platformlarını destekler:

- Android 4 ve üzeri
- iOS 8.0 ve üzeri
- macOS (Mac OS X 10.9 ve üzeri)

Windows 8.1, Windows 10 ve Windows 10 Mobile çalıştıran cihazlar için, daha önce başka bir cihazdan dışarı aktarılmış olan bir Wi-Fi yapılandırmasını içeri aktarabilirsiniz.

Bu konu başlığı altında verilen bilgileri kullanarak Wi-Fi profilini yapılandırmanın temellerini öğrenin ve sonra cihaza özgü bilgiler için her platformla ilgili olarak sağlanan konuları okuyun.

## <a name="create-a-device-profile-containing-wi-fi-settings"></a>Wi-Fi ayarlarını içeren bir cihaz profili oluşturma

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **Diğer** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazları yapılandır**’ı seçin.
2. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
3. Profiller dikey penceresinde **Profil Oluştur**’u seçin.
4. **Profil Oluştur** dikey penceresinde, Wi-Fi profili için **Ad** ve **Açıklama** girin.
5. **Platform** açılan listesinden, Wi-Fi ayarlarını uygulamak istediğiniz cihaz platformunu seçin. Şu anda, Wi-Fi ayarları için aşağıdaki platformlardan birini seçebilirsiniz:
    - **Outlook Web Access (OWA)**
    - **Android**
    - **macOS**
    - **Windows 8.1 ve üzeri (profili içeri aktarın)**
6. **Profil** türü açılan listesinden **Wi-Fi temel** veya **Wi-Fi kurumsal**’ı seçin.
    >[!TIP]
    >Ağ adı ve SSID gibi temel özellikleri sağlamak için **Wi-Fi temel**’i kullanın. **Wi-Fi kurumsal**, Wi-Fi ağınız kullanıyorsa Genişletilebilir Kimlik Doğrulama Protokolü (EAP) gibi daha gelişmiş bilgileri sağlamanıza olanak tanır. **Wi-Fi içeri aktarma** (Windows 8.1 ve Windows 10 için), Wi-Fi ayarlarını daha önce başka cihazdan dışarı aktarmış olduğunuz bir XML dosyası olarak içeri aktarmanıza olanak tanır.
7. Seçtiğiniz platforma bağlı olarak, yapılandırabileceğiniz ayarlar farklılık gösterir. Her platformun ayrıntılı ayarları için aşağıdaki konulardan birine gidin:
    - [Android ayarları](wi-fi-for-android.md)
    - [iOS ayarları](wi-fi-for-ios.md)
    - [macOS ayarları](wi-fi-for-macos.md)
    - [Windows Phone 8.1 ayarları](wi-fi-import-for-windows-8-1.md)
8. Bitirdiğinizde, **Profil Oluştur** dikey penceresine dönün ve **Oluştur**’a basın.

Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.
Devam edip bu profili gruplara atamak isterseniz, bkz. [Cihaz profillerini atama](how-to-assign-device-profiles.md).




<!--HONumber=Feb17_HO1-->

