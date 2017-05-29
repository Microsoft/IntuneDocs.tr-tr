---
title: "Microsoft Intune’la özel VPN profilleri oluşturma"
titleSuffix: Intune Azure preview
description: "Intune’da VPN profillerini oluşturmak için özel yapılandırmalar kullanın."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: b38cbfb323ad4165e6cfc3edbc3c156e4fc1d6a4
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-create-custom-vpn-profiles-in-microsoft-intune"></a>Microsoft Intune’da özel VPN profilleri oluşturma

## <a name="create-a-custom-configuration"></a>Özel yapılandırma oluşturma
Aşağıdakilere yönelik VPN profilleri oluşturmak için Intune özel yapılandırma ilkeleri kullanabilirsiniz:

* Android 4 ve üzeri çalıştıran cihazlar
* Windows 8.1 ve üzeri çalıştıran kayıtlı cihazlar
* Windows Phone 8.1 ve üzeri sürümleri çalıştıran cihazlar 
* Windows 10 masaüstü çalıştıran kayıtlı cihazlar 
* Windows 10 Mobile çalıştıran cihazlar

Standart Intune VPN ilkeleri, kullanmak istediğiniz ayarları içermiyorsa bu tür bir ilke yararlı olabilir.

## <a name="to-create-a-custom-configuration-policy"></a>Özel yapılandırma ilkesi oluşturmak için:

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **Diğer** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihaz yapılandırması**’nı seçin.
4. **Cihaz Yapılandırması** dikey penceresinde **Yönet** > **Profiller**’i seçin.
5. Profiller dikey penceresinde **Profil Oluştur**’u seçin.
6. **Profil Oluştur** dikey penceresinde, VPN profili için **Ad** ve **Açıklama** girin.
7. **Platform** açılan listesinden, VPN ayarlarını uygulamak istediğiniz cihaz platformunu seçin. Şu anda, özel cihaz ayarları için aşağıdaki platformlardan birini seçebilirsiniz:
    - **Outlook Web Access (OWA)**
    - **iOS** (Apple Configurator’dan dışarı aktardığınız dosya kullanılarak yapılandırılır).
    - **macOS** (Apple Configurator’dan dışarı aktardığınız dosya kullanılarak yapılandırılır).
    - **Windows Phone 8.1**
    - **Windows 10 ve üzeri**
6. **Profil** türü açılan listesinden **Özel**’i seçin.
7. **Özel OMA-URI Ayarları** dikey penceresinde, belirtmek istediğiniz her URI ayarı için **Ekle**’yi seçin, gerekli bilgileri sağlayın ve **Tamam**’ı seçin. Örnek:

   ![VPN profili özel yapılandırması iletişim kutusu](./media/Intune_Add_VPN_URI.png)

4.  İhtiyacınız olan tüm URI ayarlarını girdikten sonra **Tamam**’ı seçin ve ardından **Profil Oluştur** dikey penceresinde **Oluştur**’u seçin.

Profil oluşturulur ve profil listesi dikey penceresinde görüntülenir.
Devam edip bu profili gruplara atamak isterseniz, bkz. [Cihaz profillerini atama](device-profile-assign.md).





