---
title: Microsoft Intune ile iOS denetimli modunu açma
titleSuffix: ''
description: Intune ile iOS denetimli modunu nasıl açacağınızı öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/15/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 8190814-07f0-42d8-9b3a-87c67dd2b7ed
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 79e6ba1541a516b36ae4bd02cf9f60f1a12c8896
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71732585"
---
# <a name="turn-on-ios-supervised-mode"></a>iOS denetimli modunu açma


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Apple iOS denetimli modu, Apple cihazları yönetirken yöneticilere daha fazla seçenek sağlar. Bu nedenle büyük ölçekte dağıtılan şirkete ait cihazlarda kullanışlıdır. Örneğin AirDrop’u kısıtlayabilir veya kullanıcıların cihaz adını değiştirmesini önleyebilirsiniz. Denetimli mod gerektiren ayarlar listesi için bkz. [Intune’da iOS cihaz kısıtlama ayarları](../configuration/device-restrictions-ios.md).

Intune, [Apple Aygıt Kayıt Programı](../enrollment/device-enrollment-program-enroll-ios.md)’nın (DEP) bir parçası olarak denetimli modu destekler.

Denetim gerektiren Apple denetimleri listesi için Apple’ın [Yük ayarları başvurusuna](http://help.apple.com/configurator/mac/2.4/#/cad5370d089) bakın.

## <a name="turn-on-supervised-mode-during-enrollment"></a>Denetimli modu kayıt sırasında açma

[DEP’te bir Apple kayıt profili oluşturduğunuzda](../enrollment/device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) Intune’da cihazlar için denetimli modu açabilirsiniz. **Cihaz Yönetim Ayarları** altında **Denetimli** kutusunu işaretleyin.

## <a name="turn-on-supervised-mode-after-enrollment"></a>Denetimli modu kayıt sonrasında açma

Kayıt sonrasında denetimli modu açmanın tek yolu, iOS cihazı bir Mac’e bağlayıp [Apple Configurator kullanmaktır](../enrollment/apple-configurator-enroll-ios.md) (böylece cihaz sıfırlanır). Kayıttan sonra bir cihazı Intune’da Denetimli mod için yapılandıramazsınız.

## <a name="identify-a-supervised-device"></a>Denetimli bir cihazı tanımlama

Bir cihazın denetimli olup olmadığına karar vermek için kilit ekranına veya **Hakkında** sayfasına bakın:
- Cihazın kilit ekranında **Bu iPhone “Şirket Adı” tarafından yönetilmektedir** yazar.
- Cihazın **hakkında** sayfasında **Bu iPhone 'un denetimli olduğunu söylecektir. Şirket adı, Internet trafiğinizi izleyebilir ve bu cihazı bulabilir.**

## <a name="next-steps"></a>Sonraki adımlar

Diğer cihaz yönetim seçenekleri için bkz. [Microsoft Intune cihaz yönetimi nedir?](device-management.md)
