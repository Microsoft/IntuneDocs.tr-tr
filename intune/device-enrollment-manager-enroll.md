---
title: "Cihazları kaydetme - cihaz kayıt yöneticisi"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: Intune’da cihazları kaydetmek için cihaz kaydı yöneticisi hesabını kullanın. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: aded0826c2628e4dc72859387fbe4a76d683db9e
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017

---

# <a name="enroll-devices-using-device-enrollment-manager"></a>Cihaz kayıt yöneticisini kullanarak cihazları kaydetme

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Kuruluşlar, çok sayıda mobil cihazı tek bir kullanıcı hesabıyla yönetmek için Intune'u kullanabilir. *Cihaz kayıt yöneticisi* (DEM) hesabı, 1.000’e kadar cihazı kaydedebilen özel bir kullanıcı hesabıdır. Varolan kullanıcılara özel DEM yetenekleri vermek için kullanıcıları DEM hesabına ekleyin. Kaydedilen her cihaz tek bir lisans kullanır. Bu hesap aracılığıyla kaydedilen cihazları, kişisel ("KCG") cihazlar olarak değil paylaşılan cihazlar olarak kullanmanızı öneririz.  

Kullanıcıların, cihaz kayıt yöneticileri olarak eklenmesi için Azure portalında mevcut olmaları gerekir. En iyi güvenlik için DEM kullanıcısının Intune yöneticisi olmaması gerekir.

>[!NOTE]
>DEM kayıt yöntemi, şu diğer kayıt yöntemleriyle birlikte kullanılamaz: [Kurulum Yardımcısı ile Apple Configurator](apple-configurator-setup-assistant-enroll-ios.md), [Doğrudan kayıt ile Apple Configurator](apple-configurator-direct-enroll-ios.md) veya [cihaz kayıt programı](device-enrollment-program-enroll-ios.md). 

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Cihaz kayıt yöneticisi senaryo örneği

Bir restoran, garsonlar için 50 satış noktası tableti, mutfak çalışanları içinse sipariş izleyici istiyor. Çalışanların hiçbir zaman şirket verilerine erişmesi veya kullanıcı olarak oturum açması gerekmiyor. Intune yöneticisi, cihaz kayıt yöneticisi hesabı oluşturur ve DEM yetenekleri vermek için restoran yöneticisini DEM hesabına ekler. Yönetici, artık DEM kimlik bilgilerini kullanarak 50 tableti kaydedebilir.

Yalnızca Intune konsolundaki kullanıcılar cihaz kayıt yöneticileri olabilir. Cihaz kayıt yöneticisi bir Intune yöneticisi olamaz.

DEM kullanıcısı şunları yapabilir:

-   1000’e kadar cihazı Intune'a kaydeder.
-   Şirket uygulamalarını almak için Şirket Portalı’nda oturum açın.
-   Role özgü uygulamaları tabletlere dağıtarak şirket verilerine erişimi yapılandırın.

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Bir DEM hesabıyla kaydedilen cihazların kısıtlamaları

Bir cihaz kayıt yöneticisi hesabıyla kaydedilen cihazlarda aşağıdaki kısıtlamalar söz konusudur:

  - Özel bir cihaz "kullanıcısı" yoktur. Bu yüzden e-posta veya şirket verileri erişimi yoktur. Ancak örneğin VPN, verilere erişimi olan cihaz uygulamaları sağlamak için kullanılabilir.

  - Koşullu erişim yoktur çünkü bunlar kullanıcı başına senaryolardır.

  - DEM kullanıcısı, Şirket Portalı’nı kullanarak cihazın kendisinde DEM’e kaydedilen cihazların kaydını kaldıramaz. Intune yöneticisinin bu yeteneği vardır ancak DEM kullanıcısının yoktur.

  - Şirket Portalı uygulamasında veya web sitesinde yalnızca yerel cihaz görünür.
 
  - Kullanıcılar, uygulama yönetimi için kullanıcı başına Apple ID gereksinimlerinden dolayı Apple Volume Purchase Program (VPP) uygulamalarını kullanamaz.
 
  - (Yalnızca iOS) iOS cihazlarını kaydetmek için DEM kullanırsanız cihazları kaydetmek için Apple Configurator veya Apple Aygıt Kayıt Programı’nı (DEP) kullanamazsınız.


> [!NOTE]
> Cihaz kayıt yöneticisiyle yönetilen cihazlara şirket uygulaması dağıtmak için Şirket Portalı uygulamasını cihaz kayıt yöneticisinin kullanıcı hesabına **Gerekli Yükleme** olarak dağıtın.
> Performansı geliştirmek amacıyla, DEM cihazında Şirket Portalı uygulaması görüntülendiğinde yalnızca yerel cihaz gösterilir. Diğer DEM cihazlarının uzaktan yönetimi, yalnızca Intune yönetici konsolundan gerçekleştirilebilir.


## <a name="add-a-device-enrollment-manager"></a>Cihaz kayıt yöneticisi ekleme

1.  Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2.  Intune dikey penceresinde **Cihazları kaydet**’i ve ardından **Cihaz Kayıt Yöneticileri**’ni seçin.

3.  **Ekle**’yi seçin.

4.  **Kullanıcı Ekle** dikey penceresinde, DEM kullanıcısı için bir kullanıcı asıl adı girin ve **Ekle**’yi seçin. DEM kullanıcısı, DEM kullanıcıları listesine eklenir.

## <a name="remove-a-device-enrollment-manager"></a>Cihaz kayıt yöneticisini kaldırma

Cihaz kayıt yöneticisinin kaldırılması, kayıtlı cihazları etkilemez. Cihaz kayıt yöneticisi kaldırıldığında:

-   DEM kullanıcıları listesinde bir kullanıcı kaldırılması kayıtlı cihazları etkilemez ve kayıtlı cihazlar tam olarak yönetilmeye devam eder.

-   Kaldırılan cihaz kayıt yöneticisi hesabının kimlik bilgileri geçerli olmaya devam eder.

-   Kaldırılan cihaz kayıt yöneticisi yine cihazları temizleyemez ve kullanımdan kaldıramaz.

-   Intune yöneticisi tarafından yapılandırılan cihaz başına sınıra ulaşılmamış olması koşuluyla, kaldırılan cihaz kayıt yöneticisi ek cihazlar kaydedemez.

**Cihaz kayıt yöneticisi kaldırmak için**

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2. Intune dikey penceresinde **Cihazları kaydet**’i ve ardından **Cihaz Kayıt Yöneticileri**’ni seçin.

3. **Cihaz Kayıt Yöneticileri** dikey penceresinde DEM kullanıcısına sağ tıklayın ve **Kaldır**’ı seçin.

## <a name="view-the-properties-of-a-device-enrollment-manager"></a>Cihaz kayıt yöneticisinin özelliklerini görüntüleme

1. Azure portalında **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.

2. Intune dikey penceresinde **Cihazları kaydet**’i ve ardından **Cihaz Kayıt Yöneticileri**’ni seçin.

3. **Cihaz Kayıt Yöneticileri** dikey penceresinde DEM kullanıcısına sağ tıklayın ve **Özellikler**’ı seçin.

