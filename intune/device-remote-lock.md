---
title: "Intune ile yönetilen cihazları uzaktan kilitleme"
titlesuffix: Azure portal
description: "Yönettiğiniz cihazları uzaktan kilitlemek için Intune’un nasıl kullanılacağını öğrenin.\""
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 01/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0a8f3c93507cde4363570a9a39f8b3b1f69c07df
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2018
---
# <a name="remotely-lock-managed-devices-with-intune"></a>Intune ile yönetilen cihazları uzaktan kilitleme


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Uzaktan kilitleme**, seçilen cihazı kilitler. Cihaz sahibinin kilidi açmak için geçiş kodunu kullanması gerekir. PIN veya parola ayarlanmış bir cihazı yalnızca uzaktan kilitleyebilirsiniz.

## <a name="supported-platforms"></a>Desteklenen platformlar

Uzaktan kilit, aşağıdaki platformlarda desteklenir:

|Platform|Destek durumu|
|---|---|
|Android|Evet|
|iOS|Evet|
|Mac OS|Evet|
|Windows 10 masaüstü|Hayır|
|Windows 10 Mobile|Evet|
|Windows Phone|Evet, Windows Phone 8.1 ve üstü için|

> [!NOTE]  
> macOS cihazlar için 6 basamaklı bir kurtarma PIN’i ayarlarsınız. Kilitliyken, **Cihaza genel bakış** dikey penceresi başka bir cihaz eylemi gönderilene kadar PIN’i görüntüler.

## <a name="how-to-remote-lock-a-device"></a>Cihazı uzaktan kilitleme

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.
4. **Cihazlar** dikey penceresinden **Tüm cihazlar**'ı seçin.
5. Yönettiğiniz cihazların listesinden bir cihaz seçin, sonra **Uzaktan kilitleme** uzak cihaz işlemini seçin.

## <a name="next-steps"></a>Sonraki adımlar

Az önce gerçekleştirdiğiniz işlemin durumunu görmek için **Cihazlar** dikey penceresinde **Cihaz eylemleri**'ni seçin.
