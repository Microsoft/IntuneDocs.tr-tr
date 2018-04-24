---
title: Microsoft Intune ile bir iOS cihazından kullanıcı kaldırma
titlesuffix: ''
description: Paylaşılan bir iOS cihazından Intune ile kullanıcı kaldırmayı öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 67a5f60e0877ebc8994ed7d3191a81f51d19c40a
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="remove-a-user-from-a-shared-ios-device"></a>Paylaşılan bir iOS cihazından kullanıcı kaldırma


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

**Kullanıcı kaldır** eylemi, paylaşılan bir iPad cihazındaki yerel önbellekten seçtiğiniz kullanıcıyı siler. iPad cihazının, [iOS eğitim profili](education-settings-configure-ios.md) kullanılarak iOS Classroom uygulamasını yönetecek şekilde ayarlanmış olması gerekir. 

## <a name="supported-platforms"></a>Desteklenen platformlar

- Windows - Desteklenmiyor
- Windows Phone - Desteklenmiyor
- iOS - iOS 9.3 ve üzerinde desteklenir (yalnızca paylaşılan iPad cihazlar)
- macOS - Desteklenmiyor
- Android - Desteklenmiyor

## <a name="remove-a-user"></a>Kullanıcıyı kaldırma

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Cihazlar**’ı seçin.
4. **Cihazlar** bölmesinde **Tüm cihazlar**'ı seçin.
5. Yönettiğiniz cihazların listesinde, bir iOS cihazı seçin.
6. Cihazın bölmesinde **Kullanıcılar**'ı seçin.
7. Listede, kaldırmak istediğiniz kullanıcıya sağ tıklayın ve **Kullanıcıyı kaldır**'ı seçin.

## <a name="next-steps"></a>Sonraki adımlar

- **Kullanıcıyı kaldır** eyleminin durumunu görmek için **Cihazlar** > **Cihaz eylemleri**'ni seçin.
