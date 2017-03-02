---
title: "Uygulamaları gruplara atama | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Intune’a uygulama eklediğinizde, bu uygulamayı kullanıcı veya cihaz gruplarına atamak istersiniz."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 638ad0d87c19c9e40e96b42d18e5c4342f40a156
ms.lasthandoff: 02/16/2017

---

# <a name="how-to-assign-apps-to-groups-with-microsoft-intune"></a>Microsoft Intune ile uygulamaları gruplara atama

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune’a uygulama eklediğinizde, bunu kullanıcılara ve cihazlara vermek istersiniz. Bunu, uygulamayı atayarak yaparsınız.

Uygulamalar, Intune tarafından yönetilip yönetilmediğine bakılmaksızın uygulamalara atanabilir. Uygulamaları kullanıcılara ve cihazlara atamaya yönelik çeşitli seçenekleri anlamanıza yardımcı olması için aşağıdaki tabloyu kullanın:

||||
|-|-|-|-|
|&nbsp;|Intune’a kayıtlı cihazlar|Intune’a kayıtlı olmayan cihazlar|
|Kullanıcılara atama|Evet|Evet|
|Cihazlara atama|Evet|Hayır|
|Sarmalanan uygulamaları veya Intune SDK’sında birleştirilmiş uygulamaları atama (uygulama koruma ilkeleri için)|Evet|Evet|
|Uygulamaları Kullanılabilir olarak atama|Evet|Evet|
|Uygulamalarını Gerekli olarak atama|Evet|Hayır|
|Uygulamaları kaldırma|Evet|Evet|
|Son kullanıcıların Şirket Portalı uygulamasından kullanılabilir uygulamaları yüklemesi|Evet|Hayır|
|Son kullanıcıların web tabanlı Şirket Portalı’ndan kullanılabilir uygulamaları yüklemesi|Evet|Evet|

> [!NOTE]
> Şu anda, iOS ve Android uygulamalarını (hem iş kolu uygulamaları hem de mağazadan satın uygulamalar), Intune’a kaydedilmeyen cihazlara atayabilirsiniz.

## <a name="how-to-assign-an-app"></a>Uygulama atama

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Uygulamaları yönet**’i seçin.
1. **Uygulamaları Yönet** iş yükünde **Yönet** > **Uygulamalar**’ı seçin.
2. Uygulama listesi dikey penceresinde, atamak istediğiniz uygulamaya tıklayın.
3. <*uygulama adı*> - **Genel Bakış** dikey penceresinde **Yönet** > **Atamalar**’ı seçin.
4. **Grup Seç** öğesini seçin, ardından **Grupları seçin** dikey penceresinde uygulamayı atamak istediğiniz Azure AD gruplarını seçin.
5. Seçtiğiniz her uygulama için, **atama türü** olarak aşağıdakilerden birini seçin:
    - **Kullanılabilir** Kullanıcılar Şirket Portalı’ndan veya web sitesinden uygulamayı yükler.
    - **Uygulanamaz** - Uygulama yüklenmez veya Şirket Portalı’nda gösterilmez.
    - **Gerekli** - Uygulama, seçili gruplardaki cihazlara yüklenir.
    - **Kaldırma** - Uygulama, seçilen gruplardaki cihazlardan kaldırılır.
    - **Kayıtlı veya kayıtsız kullanılabilir** - Bu uygulamayı, cihazları Intune’a kayıtlı olmayan kullanıcı gruplarına atayın. Yardım için yukarıdaki tabloya bakın.
6. İşiniz bittikten sonra **Kaydet**’i seçin.

Artık uygulama seçtiğiniz gruba atanır.

Uygulama atamalarını izlemenize yardımcı olacak bilgiler için bkz. [Uygulamaları izleme](monitor-apps.md).

