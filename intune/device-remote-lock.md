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
ms.openlocfilehash: ecd7fa03b35e91b5a77906858fb251348796704d
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
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
|Windows 10|Evet|
|Windows 10 Mobile|Evet|
|Windows Phone|Evet, Windows Phone 8.1 ve üstü için|

> [!NOTE]  
> macOS cihazlar için 6 basamaklı bir kurtarma PIN’i ayarlarsınız. Kilitliyken, **Cihaza genel bakış** dikey penceresi başka bir cihaz eylemi gönderilene kadar PIN’i görüntüler.

## <a name="how-to-remote-lock-a-device"></a>Cihazı uzaktan kilitleme

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.
4. **Cihazlar ve gruplar** dikey penceresinde **Tüm cihazlar**’ı seçin.
5. Yönettiğiniz cihazların listesinden bir cihaz seçin, sonra **Uzaktan kilitleme** uzak cihaz işlemini seçin.

## <a name="next-steps"></a>Sonraki adımlar

Az önce gerçekleştirdiğiniz işlemin durumunu görmek için **Cihazlar ve gruplar** dikey penceresinde **Cihaz Eylemleri**'ni seçin.
