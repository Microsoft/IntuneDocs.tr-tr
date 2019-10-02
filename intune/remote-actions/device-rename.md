---
title: Microsoft Intune-Azure ile cihaz yeniden adlandırma | Microsoft Docs
description: Microsoft Intune kullanarak bir cihazı yeniden adlandırma.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 35fae5ea1b3294772db4f4db51179892e08ed5d1
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71732605"
---
# <a name="rename-a-device-in-intune"></a>Intune 'da bir cihazı yeniden adlandırma


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

**Cihazı yeniden adlandır** eylemi, Intune 'a kaydedilmiş bir cihazı yeniden adlandırmanızı sağlar. Cihazın adı Intune 'da ve cihazda değişir.

Aşağıdaki cihaz türlerini yeniden adlandırabilirsiniz:
- şirkete ait pencereler 
- iOS denetimli
- şirkete ait MacOS 10

Bu özellik şu anda karma Azure AD Windows cihazlarının yeniden adlandırılmasını desteklemiyor.

## <a name="rename-a-device"></a>Bir cihazı yeniden adlandırma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. @No__t **cihazları**seçin-1**tüm cihazlar** > cihaz seçin > **daha fazla** > **cihaz yeniden adlandır**.
4. **Cihazı yeniden adlandır** dikey penceresinde, metin kutusuna yeni adı yazın. Harf, sayı ve kısa çizgi kullanabilirsiniz. Ad en az bir harf veya kısa çizgi içermelidir.
5. Yeniden adlandırdıktan sonra cihazı yeniden başlatmak istiyorsanız Yeniden Adlandır ' ın yanındaki **Evet** ' i seçerek yeniden **başlatın**.
6. **Yeniden Adlandır**' ı seçin.



## <a name="next-steps"></a>Sonraki adımlar

Cihazı **Yeniden Adlandır** eyleminin durumunu görmek için, cihazın **genel bakış** sayfasını kontrol edin.
