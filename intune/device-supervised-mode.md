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
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 8190814-07f0-42d8-9b3a-87c67dd2b7ed
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d5a521641c2d916f1a40679bc8d9445abaaf9872
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57399183"
---
# <a name="turn-on-ios-supervised-mode"></a>iOS denetimli modunu açma


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Apple iOS denetimli modu, Apple cihazları yönetirken yöneticilere daha fazla seçenek sağlar. Bu nedenle büyük ölçekte dağıtılan şirkete ait cihazlarda kullanışlıdır. Örneğin AirDrop’u kısıtlayabilir veya kullanıcıların cihaz adını değiştirmesini önleyebilirsiniz. Denetimli mod gerektiren ayarlar listesi için bkz. [Intune’da iOS cihaz kısıtlama ayarları](device-restrictions-ios.md).

Intune, [Apple Aygıt Kayıt Programı](device-enrollment-program-enroll-ios.md)’nın (DEP) bir parçası olarak denetimli modu destekler.

Denetim gerektiren Apple denetimleri listesi için Apple’ın [Yük ayarları başvurusuna](http://help.apple.com/configurator/mac/2.4/#/cad5370d089) bakın.

## <a name="turn-on-supervised-mode-during-enrollment"></a>Denetimli modu kayıt sırasında açma

[DEP’te bir Apple kayıt profili oluşturduğunuzda](https://docs.microsoft.com/intune/device-enrollment-program-enroll-ios#create-an-apple-enrollment-profile) Intune’da cihazlar için denetimli modu açabilirsiniz. **Cihaz Yönetim Ayarları** altında **Denetimli** kutusunu işaretleyin.

## <a name="turn-on-supervised-mode-after-enrollment"></a>Denetimli modu kayıt sonrasında açma

Kayıt sonrasında denetimli modu açmanın tek yolu, iOS cihazı bir Mac’e bağlayıp [Apple Configurator kullanmaktır](apple-configurator-enroll-ios.md) (böylece cihaz sıfırlanır). Kayıttan sonra bir cihazı Intune’da Denetimli mod için yapılandıramazsınız.

## <a name="identify-a-supervised-device"></a>Denetimli bir cihazı tanımlama

Bir cihazın denetimli olup olmadığına karar vermek için kilit ekranına veya **Hakkında** sayfasına bakın:
- Cihazın kilit ekranında **Bu iPhone “Şirket Adı” tarafından yönetilmektedir** yazar.
- Cihazın **Hakkında** sayfasında ise **Bu cihaz denetimlidir. “Şirket Adı”, internet trafiğinizi izleyebilir ve bu cihazın konumunu belirleyebilir.** yazar.

## <a name="next-steps"></a>Sonraki adımlar

Diğer cihaz yönetim seçenekleri için bkz. [Microsoft Intune cihaz yönetimi nedir?](device-management.md)
