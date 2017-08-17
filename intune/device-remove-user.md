---
title: "Intune ile bir iOS cihazından kullanıcı kaldırma"
titleSuffix: Intune on Azure
description: "Paylaşılan bir iOS cihazından Intune ile kullanıcı kaldırmayı öğrenin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 00f5898d0f2cc167a66026dd108d6bbd54c39cec
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2017
---
# <a name="remove-a-user-from-a-shared-ios-device-with-intune"></a>Paylaşılan bir iOS cihazından Intune ile kullanıcı kaldırma


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Kullanıcı kaldır** eylemi, iOS Classroom uygulamasını [iOS eğitim profili](education-settings-configure-ios.md) ile yönetmek üzere yapılandırılmış, paylaşılan bir iPad cihazdaki yerel önbellekten seçtiğiniz bir kullanıcıyı siler. 

## <a name="supported-platforms"></a>Desteklenen platformlar

- Windows - Desteklenmiyor
- Windows Phone - Desteklenmiyor
- iOS - iOS 9.3 ve üzerinde desteklenir (yalnızca paylaşılan iPad cihazlar)
- macOS - Desteklenmiyor
- Android - Desteklenmiyor

## <a name="how-to-remove-a-user"></a>Bir kullanıcıyı kaldırma

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.
4. **Cihazlar** dikey penceresinden **Tüm cihazlar**'ı seçin.
5. Yönettiğiniz cihazların listesinden bir iOS cihazı seçin.
6. Cihazın dikey penceresinde **Kullanıcılar**'ı seçin.
7. Listede, kaldırmak istediğiniz kullanıcıya sağ tıklayın, ardından **Kullanıcıyı kaldır**'ı seçin.

## <a name="next-steps"></a>Sonraki adımlar

Az önce gerçekleştirdiğiniz işlemin durumunu görmek için **Cihazlar ve gruplar** dikey penceresinde **Cihaz Eylemleri**'ni seçin.
