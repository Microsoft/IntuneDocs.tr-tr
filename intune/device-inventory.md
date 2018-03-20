---
title: "Cihazları Microsoft Intune - Azure ile görüntüleme | Microsoft Docs"
description: "İşletim sistemleri, depolama alanı, üretim ve model ve daha fazlasını içeren cihaz ayrıntılarınızı görüntüleyin. Yüklü uygulamaların bir listesini alın, uyumluluk ilkelerini denetleyin, TeamViewer'ı ve daha fazlasını Azure'da Microsoft Intune ile kurun. Yönettiğiniz cihazların envanterini görüntülemeye benzerdir."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 934ba0853f8bee851f7027580c276a9fff911b7f
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="see-device-details-in-intune"></a>Intune'da cihaz ayrıntılarına bakın

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Cihazlar** özelliği, yönettiğiniz cihazlarda donanım ve yüklü uygulamalar gibi ek ayrıntılar sağlar. 

Bu makalede, tüm cihazlarınızı ve özelliklerini Azure portalında nasıl görüntüleyeceğiniz gösterilir.

## <a name="view-your-device-details"></a>Cihaz ayrıntılarınızı görüntüleme

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihazlar**’ı seçin. Cihazlar bölümü içinde birkaç seçeneğiniz vardır:

  - **Genel Bakış** Kaydettiğiniz cihazlar ve her cihazın çalıştırdığı işletim sistemleri hakkında bilgi alın.
  - **Yönet** - Yönettiğiniz cihazların listesini görmek için **Tüm cihazlar**’ı veya **Azure AD cihazları**’nı seçin.
    Listedeki cihazlardan birini seçin. Bu adım, aşağıdakileri seçebileceğiniz <*cihaz adı*> **Genel Bakış**’ı açar:
    - **Genel Bakış**  - Cihaz adını, sahibini, kendi cihazını getir (KCG) cihazı olup olmadığını, ne zaman iade edildiğini ve daha fazla ayrıntıyı görün
    - **Donanım** - Boş depolama alanını, modeli, üreticiyi ve cihaz hakkında daha fazla ayrıntıyı görün
    - **Bulunan uygulamalar** - Intune'un cihazda yüklü olduğunu bulduğu tüm uygulamaları listeler
    - **Cihaz uyumluluğu** - Cihaza atanan tüm uyumluluk ilkelerinin durumunu görüntüler
    - **Cihaz yapılandırması** - Cihaza atanmış tüm cihaz yapılandırma ilkelerinin uyumluluk durumunu görüntüler
- **İzleme** - Yönettiğiniz cihazlarda yapılan eylemlerin bir listesini ve bunların geçerli durumunu görmek için **Cihaz eylemleri**’ni seçin. **Denetim günlükleri** farklı görevlerin durumunu gösterir.
- **Kurulum** > **TeamViewer Bağlayıcısı** - Cihazlarda TeamViewer yazılımını kullanarak uzaktan yönetimi yapılandırın. Ayrıntılar için bkz. [Intune ile yönetilen Android cihazları için uzaktan yardım sağlama](device-profile-android-teamviewer.md).

Intune, yalnızca şirkete ait cihazlarda uygulama listesi toplar. Kişisel cihazlarda uygulamalar denetlenmez. Windows 10 bilgisayarlarda, şirkete ait cihazlar için yalnızca modern uygulamalar listelenir. Intune, cihazdaki Win32 uygulamalar hakkında bilgi toplamaz. Cihazların operatör kullanımına bağlı olarak, tüm uygulamalar toplanamaz.

## <a name="next-steps"></a>Sonraki adımlar
Intune ile [cihazlarınızı yönetmek](device-management.md) için başka neler yapabileceğinizi görün.
