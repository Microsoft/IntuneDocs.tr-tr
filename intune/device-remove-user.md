---
title: "Microsoft Intune ile bir iOS cihazından kullanıcı kaldırma"
titlesuffix: 
description: "Paylaşılan bir iOS cihazından Intune ile kullanıcı kaldırmayı öğrenin."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ce1b6b439c287b67a7c9e776edf136e78e5ecf5b
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="remove-a-user-from-a-shared-ios-device"></a>Paylaşılan bir iOS cihazından kullanıcı kaldırma


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Kullanıcı kaldır** eylemi, iOS Classroom uygulamasını [iOS eğitim profili](education-settings-configure-ios.md) ile yönetmek üzere yapılandırılmış, paylaşılan bir iPad cihazdaki yerel önbellekten seçtiğiniz bir kullanıcıyı siler. 

## <a name="supported-platforms"></a>Desteklenen platformlar

- Windows - Desteklenmiyor
- Windows Phone - Desteklenmiyor
- iOS - iOS 9.3 ve üzerinde desteklenir (yalnızca paylaşılan iPad cihazlar)
- macOS - Desteklenmiyor
- Android - Desteklenmiyor

## <a name="how-to-remove-a-user"></a>Bir kullanıcıyı kaldırma

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.
4. **Cihazlar** dikey penceresinden **Tüm cihazlar**'ı seçin.
5. Yönettiğiniz cihazların listesinden bir iOS cihazı seçin.
6. Cihazın dikey penceresinde **Kullanıcılar**'ı seçin.
7. Listede, kaldırmak istediğiniz kullanıcıya sağ tıklayın, ardından **Kullanıcıyı kaldır**'ı seçin.

## <a name="next-steps"></a>Sonraki adımlar

Az önce gerçekleştirdiğiniz işlemin durumunu görmek için **Cihazlar** dikey penceresinde **Cihaz eylemleri**'ni seçin.
