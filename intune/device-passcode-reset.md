---
title: Microsoft Intune - Azure ile cihaz geçiş kodlarını sıfırlama | Microsoft Docs
description: Intune ile yönettiğiniz veya izlediğiniz cihazlarda Geçiş kodunu kaldır eylemini kullanarak geçiş kodunu kaldırın veya sıfırlayın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 81330083830eb2e3e1fe3e36217d403a77094a65
ms.sourcegitcommit: 8be5f29107d882c3ecf3dc0ce718a2423f91ce9a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "36964734"
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Intune’da bir cihazın geçiş kodunu sıfırlama veya kaldırma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bir cihazda yeni bir geçiş kodu oluşturmak için **Geçiş kodunu kaldır** eylemini kullanın.

## <a name="supported-platforms"></a>Desteklenen platformlar

- Bir İş profiliyle kaydedilmiş sürüm 8.0 ve üzeri Android cihazlar
- Sürüm 6.0 veya öncesi Android cihazlar
- iOS 
     
## <a name="unsupported-platforms"></a>Desteklenmeyen platformlar

- Bir İş profiliyle kaydedilmiş sürüm 7.0 ve öncesi Android cihazlar
- Sürüm 7.0 veya üzeri Android cihazlar
- Mac OS
- Windows

## <a name="reset-a-passcode"></a>Geçiş kodu sıfırlama

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve ardından **Microsoft Intune**’u seçin.
3. **Cihazlar**’ı ve ardından **Tüm cihazlar**’ı seçin.
4. Yönettiğiniz cihazların listesinden bir cihaz seçin ve sonra da **...Diğer** öğesini seçin. Ardından **Geçiş kodunu kaldır** cihaz uzak eylemini seçin.

## <a name="resetting-android-for-work-passcodes"></a>Android for Work geçiş kodlarını sıfırlama

Desteklenen Android for Work cihazları, yeni bir yönetilen profil kilidini açma parolası veya son kullanıcı için bir yönetilen profil sınaması alır. İş profiline sahip Android 8.0 veya üzeri sürümlerdeki cihazlarda son kullanıcılar, kayıt tamamlandıktan hemen sonra geçiş kodu sıfırlama belirteçlerini etkinleştirmek için bildirim alır. Bildirim, bir İş profili parolası gerekli ve ayarlıysa görüntülenir. Geçiş kodu girildikten sonra bildirim kaybolur.

## <a name="resetting-ios-passcodes"></a>iOS geçiş kodlarını sıfırlama

Geçiş kodları iOS cihazlardan kaldırılır. Ayarlı bir uyumluluk ilkesi varsa cihaz, kullanıcıdan Ayarlar’a gidip yeni bir geçiş kodu ayarlamasını ister. 

## <a name="next-steps"></a>Sonraki adımlar

Az önce gerçekleştirdiğiniz eylemin durumunu görmek için **Cihazlar**’da, **Cihaz eylemleri**’ni seçin.
