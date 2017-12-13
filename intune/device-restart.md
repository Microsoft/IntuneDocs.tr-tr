---
title: "Cihazları Intune ile uzaktan başlatma"
titlesuffix: Azure portal
description: "Cihazı yeniden başlatma işlemini kullanarak cihazları uzaktan yeniden başlatma hakkında bilgi edinin.\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/21/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dde251482dd951200e5c1a7f19749ee863cd71b4
ms.sourcegitcommit: 520eb7712625e129b781e2f2b9fe16f9b9f3d08a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2017
---
# <a name="remotely-restart-devices-with-intune"></a>Cihazları Intune ile uzaktan başlatma


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Yeniden Başlat** cihaz işlemi, seçtiğiniz cihazın yeniden başlatılmasına neden olur. Yeniden başlatma işlemi cihaz sahibine otomatik olarak bildirilmez, dolayısıyla cihaz sahibi çalışmasını kaybedebilir.

## <a name="supported-platforms"></a>Desteklenen platformlar

- Windows - Windows 8.1 ve üzerinde desteklenir
- Windows Phone - Windows Phone 8.1 ve sonraki sürümlerde desteklenir
- iOS - Desteklenir

    > [!Note]  
    > Bu komut, denetlenen cihazlar ve **Cihaz Kilidi** erişim hakkı gerektirir. Cihaz hemen yeniden başlatılır. Geçiş koduyla kilitli iOS cihazlar yeniden başlatmadan sonra bir Wi-Fi ağına yeniden katılmaz; yeniden başlatıldıktan sonra sunucu ile iletişim kuramayabilir.
- macOS - Desteklenmiyor
- Android - Desteklenmiyor

## <a name="how-to-restart-a-device"></a>Bir cihazı yeniden başlatma

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.
4. **Cihazlar ve gruplar** dikey penceresinde **Tüm cihazlar**'ı seçin.
5. Yönettiğiniz cihazların listesinden bir cihaz seçin, sonra **Yeniden Başlat** uzak cihaz işlemini seçin.

## <a name="next-steps"></a>Sonraki adımlar

Az önce gerçekleştirdiğiniz işlemin durumunu görmek için **Cihazlar ve gruplar** dikey penceresinde **Cihaz Eylemleri**'ni seçin.
