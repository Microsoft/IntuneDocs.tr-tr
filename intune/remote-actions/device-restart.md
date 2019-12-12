---
title: Microsoft Intune - Azure ile cihazları yeniden başlatma | Microsoft Docs
description: Azure portalında Microsoft Intune'u kullanarak Yeniden başlatma uzak eylemiyle Windows ve iOS cihazlarını yeniden başlatın.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/21/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b7b77c4f0127c9ee16b255d0e0e28622b85c323b
ms.sourcegitcommit: ec69e7ccc6e6183862a48c1b03ca6a3bf573f354
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2019
ms.locfileid: "74907262"
---
# <a name="remotely-restart-devices-with-intune"></a>Cihazları Intune ile uzaktan başlatma


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

**Yeniden Başlat** cihaz işlemi, seçtiğiniz cihazın yeniden başlatılmasına neden olur. Yeniden başlatma işlemi cihaz sahibine otomatik olarak bildirilmez ve cihaz sahibi çalışmasını kaybedebilir.

## <a name="supported-platforms"></a>Desteklenen platformlar

- Windows - Windows 8.1 ve üzerinde desteklenir
- Windows Phone - Windows Phone 8.1 ve sonraki sürümlerde desteklenir
- Android bilgi noktası cihazları-Android 7,0 ve üzeri sürümlerde desteklenir
- iOS - Desteklenir

    > [!Note]  
    > Bu komut için, denetlenen bir cihaz ve **Cihaz Kilidi** erişim hakkı gerekir. Cihaz hemen yeniden başlatılır. Geçiş koduyla kilitlenen iOS cihazları, yeniden başlatma sonrasında Wi-Fi ağına yeniden katılmaz. Yeniden başlatma sonrasında, cihaz sunucuyla iletişim kuramayabilir.
- macOS - Desteklenmiyor
- Android ve Android iş profili cihazları - Desteklenmiyor

## <a name="restart-a-device"></a>Cihazı yeniden başlatma

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
3. **Cihazlar** > **Tüm cihazlar**’ı seçin.
4. Yönettiğiniz cihazların listesinde bir cihaz seçin > **yeniden başlat** ** > .**

## <a name="next-steps"></a>Sonraki adımlar

- **Yeniden başlat** cihaz eyleminin durumunu görmek için **Cihazlar** > **Cihaz eylemleri**'ni seçin.
