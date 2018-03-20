---
title: "Microsoft Intune’la özel VPN profilleri oluşturma"
titleSuffix: 
description: "Intune’da VPN profillerini oluşturmak için özel yapılandırmalar kullanın."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ec9b959d086051985287a62f7d10fe8d4cbad7e9
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-create-custom-vpn-profiles-in-microsoft-intune"></a>Microsoft Intune’da özel VPN profilleri oluşturma

Aşağıdaki platformlar için VPN profilleri oluştururken Intune özel yapılandırma ilkeleri kullanabilirsiniz:

* Android 4 ve üzeri
* Windows 8.1 ve üzeri çalıştıran kayıtlı cihazlar
* Windows Phone 8.1 ve üzeri
* Windows 10 masaüstü çalıştıran kayıtlı cihazlar 
* Windows 10 Mobile

Standart Intune VPN ilkeleri, kullanmak istediğiniz ayarları içermiyorsa bu tür bir ilke yararlı olabilir.

## <a name="to-create-a-custom-configuration-policy"></a>Özel yapılandırma ilkesi oluşturmak için:

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Cihaz yapılandırması**’nı seçin.
2. **Yönet** bölümü altındaki **Cihaz yapılandırması** bölmesinden **Profiller**’i seçin.
5. Profiller bölmesinde **Profil oluştur**’u seçin.
6. **Profil oluştur** bölmesinde, VPN profili için **Ad** ve **Açıklama** girin.
7. **Platform** açılan listesinden, VPN ayarlarını uygulamak istediğiniz cihaz platformunu seçin. Şu anda, özel cihaz ayarları için aşağıdaki platformlardan birini seçebilirsiniz:
    - **Android**
    - **Android for Work**
    - **iOS** (Apple Configurator’dan dışarı aktardığınız dosya kullanılarak yapılandırılır).
    - **macOS** (Apple Configurator’dan dışarı aktardığınız dosya kullanılarak yapılandırılır).
    - **Windows Phone 8.1**
    - **Windows 8.1 ve üzeri**
    - **Windows 10 ve üzeri**
6. **Profil** türü açılan listesinden **Özel**’i seçin.
7. **Özel OMA-URI Ayarları** bölmesinde, belirtmek istediğiniz her URI ayarı için **Ekle**’yi seçin, gerekli bilgileri sağlayın ve **Tamam**’ı seçin. Örnek:

   ![VPN profili özel yapılandırması iletişim kutusu](./media/Intune_Add_VPN_URI.png)

4.  İhtiyacınız olan tüm URI ayarlarını girdikten sonra **Tamam**’ı seçin ve ardından **Profil oluştur** bölmesinde **Oluştur**’u seçin.

Profil oluşturulur ve profil listesi bölmesinde görüntülenir.
Devam edip bu profili gruplara atamak isterseniz, bkz. [Cihaz profillerini atama](device-profile-assign.md).




