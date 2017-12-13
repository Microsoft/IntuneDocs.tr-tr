---
title: "Intune ile yönetilen cihazları uzaktan kilitleme"
titlesuffix: Azure portal
description: "Yönettiğiniz cihazları uzaktan kilitlemek için Intune’un nasıl kullanılacağını öğrenin.\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/21/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8905b97a5912010a2516788a8da66441fc6f89ae
ms.sourcegitcommit: 520eb7712625e129b781e2f2b9fe16f9b9f3d08a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2017
---
# <a name="remotely-lock-managed-devices-with-intune"></a>Intune ile yönetilen cihazları uzaktan kilitleme


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Uzaktan kilitleme**, seçilen cihazı kilitler. Cihaz sahibinin kilidi açmak için geçiş kodunu kullanması gerekir. PIN veya parola ayarlanmış bir cihazı yalnızca uzaktan kilitleyebilirsiniz.

## <a name="supported-platforms"></a>Desteklenen platformlar

- Windows - Desteklenmiyor
- Windows Phone - Windows Phone 8.1 ve sonraki sürümlerde desteklenir
- iOS - Desteklenir
- macOS - Desteklenir

    > [!Note]  
    > 6 basamaklı bir kurtarma PIN'i ayarlayın. Kilitliyken, **Cihaza genel bakış** dikey penceresi başka bir cihaz eylemi gönderilene kadar PIN’i görüntüler.
- Android - Desteklenir

## <a name="how-to-remote-lock-a-device"></a>Cihazı uzaktan kilitleme

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.
4. **Cihazlar ve gruplar** dikey penceresinde **Tüm cihazlar**’ı seçin.
5. Yönettiğiniz cihazların listesinden bir cihaz seçin, sonra **Uzaktan kilitleme** uzak cihaz işlemini seçin.

## <a name="next-steps"></a>Sonraki adımlar

Az önce gerçekleştirdiğiniz işlemin durumunu görmek için **Cihazlar ve gruplar** dikey penceresinde **Cihaz Eylemleri**'ni seçin.
