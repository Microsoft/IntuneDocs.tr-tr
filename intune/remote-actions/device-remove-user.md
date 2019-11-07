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
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 772cdbe203b0489a9b2312a1cc10ea1b3182b35d
ms.sourcegitcommit: 28622c5455adfbce25a404de4d0437fa2b5370be
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73713151"
---
# <a name="remove-a-user-from-a-shared-ios-device"></a>Paylaşılan bir iOS cihazından kullanıcı kaldırma


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

**Kullanıcı kaldır** eylemi, paylaşılan bir iPad cihazındaki yerel önbellekten seçtiğiniz kullanıcıyı siler. iPad cihazının, [iOS eğitim profili](../fundamentals/education-settings-configure-ios.md) kullanılarak iOS Classroom uygulamasını yönetecek şekilde ayarlanmış olması gerekir. 

## <a name="supported-platforms"></a>Desteklenen platformlar

- Windows - Desteklenmiyor
- Windows Phone - Desteklenmiyor
- iOS - iOS 9.3 ve üzerinde desteklenir (yalnızca paylaşılan iPad cihazlar)
- macOS - Desteklenmiyor
- Android - Desteklenmiyor

## <a name="remove-a-user"></a>Kullanıcıyı kaldırma

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Cihazlar** > **Tüm cihazlar**’ı seçin.
3. Yönettiğiniz cihazların listesinde, bir iOS cihazı seçin.
4. Cihazın bölmesinde **Kullanıcılar**'ı seçin.
5. Listede, kaldırmak istediğiniz kullanıcıya sağ tıklayın ve **Kullanıcıyı kaldır**'ı seçin.

## <a name="next-steps"></a>Sonraki adımlar

- **Kullanıcıyı kaldır** eyleminin durumunu görmek için **Cihazlar** > **Cihaz eylemleri**'ni seçin.
