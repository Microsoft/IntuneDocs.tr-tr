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
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0f5ee9a0fe27c3cf9de758fd7155dbd127fb1e5e
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "73712209"
---
# <a name="rename-a-device-in-intune"></a>Intune 'da bir cihazı yeniden adlandırma

**Cihazı yeniden adlandır** eylemi, Intune 'a kaydedilmiş bir cihazı yeniden adlandırmanızı sağlar. Cihazın adı Intune 'da ve cihazda değişir.

Aşağıdaki cihaz türlerini yeniden adlandırabilirsiniz:
- şirkete ait pencereler 
- iOS denetimli
- şirkete ait MacOS 10

Bu özellik şu anda karma Azure AD Windows cihazlarının yeniden adlandırılmasını desteklemiyor.

## <a name="rename-a-device"></a>Bir cihazı yeniden adlandırma

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
3. **Cihazları** > **tüm cihazlar** ' ı seçin > cihaz seçin > **daha fazla** > **cihazı yeniden adlandır**.
4. **Cihazı yeniden adlandır** dikey penceresinde, metin kutusuna yeni adı yazın. Harf, sayı ve kısa çizgi kullanabilirsiniz. Ad en az bir harf veya kısa çizgi içermelidir.
5. Yeniden adlandırdıktan sonra cihazı yeniden başlatmak istiyorsanız Yeniden Adlandır ' ın yanındaki **Evet** ' i seçerek yeniden **başlatın**.
6. **Yeniden Adlandır**' ı seçin.

## <a name="windows-device-rename-rules"></a>Windows cihaz yeniden adlandırma kuralları
Bir Windows cihazını yeniden adlandırırken, yeni ad aşağıdaki kurallara uymalıdır:
- 15 karakter veya daha az (63 bayttan küçük veya buna eşit olmalı, sondaki NULL dahil değildir)
- Null veya boş dize değil
- İzin verilen ASCII: harfler (a-z, A-Z), sayılar (0-9) ve tireler
- İzin verilen Unicode: karakterler > = 0x80, geçerli UTF8 olmalıdır, ıDN eşleme olmalıdır (yani Rtlıdntonameprepunıcode başarılı; bkz. RFC 3492)
- Adlar yalnızca rakam içermemelidir
- Adda boşluk yok
- İzin verilmeyen karakterler: {|} ~ [\] ^ ':; < = >? & @! " # $ % ` ( ) + / , . _ *)


## <a name="next-steps"></a>Sonraki adımlar

Cihazı **Yeniden Adlandır** eyleminin durumunu görmek için, cihazın **genel bakış** sayfasını kontrol edin.
