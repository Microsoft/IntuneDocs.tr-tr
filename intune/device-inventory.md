---
title: Cihazları Microsoft Intune - Azure ile görüntüleme | Microsoft Docs
description: İşletim sistemleri, depolama alanı, üretim ve modeli içeren cihaz ayrıntılarınızı görüntüleyin. Azure'da Microsoft Intune ile yüklü uygulamaların bir listesini alın, uyumluluk ilkelerini denetleyin ve TeamViewer'ı ayarlayın. Bu, yönettiğiniz cihazların envanterini görüntülemeye benzer.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: eaaf3e9807a8eab66c24f4d1bb3c3c5ea9f4cfe0
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="see-device-details-in-intune"></a>Intune'da cihaz ayrıntılarına bakın

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Cihazlar** özelliği, yönettiğiniz cihazlarla ilgili olarak donanım ve yüklü uygulamalar gibi ek ayrıntılar sağlar. 

Bu makalede, tüm cihazlarınızı ve özelliklerini Azure portalında nasıl görüntüleyeceğiniz gösterilir.

## <a name="view-your-device-details"></a>Cihaz ayrıntılarınızı görüntüleme

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihazlar**’ı seçin. Cihazlar bölümü içinde birkaç seçeneğiniz vardır:

   - **Genel Bakış**: Kaydettiğiniz cihazlar ve her cihazın çalıştırdığı işletim sistemi hakkında bilgi alın.
   - **Yönet**: Yönettiğiniz cihazların listesini görmek için **Tüm cihazlar**’ı veya **Azure AD cihazları**’nı seçin.
    Listedeki cihazlardan birini seçin. Bu adım, aşağıdakileri seçebileceğiniz <*cihaz adı*> **Genel Bakış**’ı açar:
     - **Genel Bakış**: Cihaz adını, sahibini, bunun kendi cihazını getir (KCG) cihazı olup olmadığını, ne zaman iade edildiğini ve diğer ayrıntıları görün.
     - **Donanım**: Boş depolama alanını, modeli, üreticiyi ve cihaz hakkındaki diğer ayrıntıları görün.
     - **Bulunan uygulamalar**: Intune'un cihazda yüklü olduğunu bulduğu tüm uygulamaların listesini görün.
     - **Cihaz uyumluluğu**: Cihaza atanan tüm uyumluluk ilkelerinin durumunu görüntüler.
     - **Cihaz yapılandırması**: Cihaza atanmış tüm cihaz yapılandırma ilkelerinin uyumluluk durumunu görüntüler.
   - **İzleme**: Yönettiğiniz cihazlarda yapılan eylemlerin listesini ve bunların geçerli durumunu görmek için **Cihaz eylemleri**’ni seçin. **Denetim günlükleri** farklı görevlerin durumunu gösterir.
   - **Kurulum** > **TeamViewer Bağlayıcısı**: TeamViewer yazılımını kullanarak cihazlarda uzaktan yönetimi yapılandırın. Ayrıntılar için bkz. [Intune ile yönetilen Android cihazları için uzaktan yardım sağlama](device-profile-android-teamviewer.md).

Intune, yalnızca şirkete ait cihazlarda uygulama listesi toplar. Kişisel cihazlarda uygulamalar denetlenmez. Windows 10 bilgisayarlarda, şirkete ait cihazlar için yalnızca modern uygulamalar listelenir. Intune, cihazdaki Win32 uygulamalar hakkında bilgi toplamaz. Cihazlarda kullanılan operatöre bağlı olarak, tüm uygulamalar toplanamayabilir.

## <a name="next-steps"></a>Sonraki adımlar
Intune ile [cihazlarınızı yönetmek](device-management.md) için başka neler yapabileceğinizi görün.
