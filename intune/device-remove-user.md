---
title: Microsoft Intune ile bir iOS cihazından kullanıcı kaldırma
titleSuffix: ''
description: Paylaşılan bir iOS cihazından Intune ile kullanıcı kaldırmayı öğrenin.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 53c4e02f32fa421c745f5bfa15e97023f47ece88
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59897469"
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
