---
title: "Intune cihaz envanterini görüntüleme"
titlesuffix: Azure portal
description: "Intune ile yönettiğiniz cihazları görüntüleme ve bunların donanımını ve yüklü uygulamalarını anlama hakkında bilgi edinin.\""
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 11/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 772e2b1380626384d618e653b90b31a1f421eb72
ms.sourcegitcommit: 80a2eefc1896a42cc2bc16be23093d1abf58b088
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/27/2018
---
# <a name="how-to-view-intune-device-inventory"></a>Intune cihaz envanterini görüntüleme


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Cihazlar** iş yükü, size, yönettiğiniz cihazlar hakkında, bunların donanım özellikleri ve üzerlerinde yüklü uygulamalar dahil bilgi sağlar. 

Cihaz envanterini görüntülemek için:

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.

Şimdi aşağıdaki seçeneklerden birini belirleyin:

- **Genel Bakış** Kaydettiğiniz cihazlar ve her cihazın çalıştırdığı işletim sistemleri hakkında bilgi alın.
- **Yönet** - Yönettiğiniz tüm cihazların listesini görmek için **Tüm cihazlar**’ı seçin.
    Listedeki cihazlardan birini seçerek <*cihaz adı*> **Genel Bakış** dikey penceresini açın. Burada aşağıdakilerden birini seçebilirsiniz:
    - **Genel bakış**  - Cihaz hakkında adı, sahibi, bir KCG cihazı olup olmadığı, ne zaman iade edildiği ve daha fazlasıyla ilgili genel bilgileri görün.
    - **Donanım** - Cihaz hakkında boş depolama alanı, modeli ve üreticisi gibi daha ayrıntılı bilgileri görün.
    - **Bulunan uygulamalar** - Intune'un cihazda yüklü olduğunu bulduğu tüm uygulamaların bir listesini görüntüler.
    - **Cihaz uyumluluğu** - Cihaza atanan tüm uyumluluk ilkelerinin uyumluluk durumunu görüntüler.
    - **Cihaz yapılandırması** - Cihaza atanmış tüm cihaz yapılandırma ilkelerinin uyumluluk durumunu görüntüler.
- **İzleme** - Yönettiğiniz cihazlarda yapılan cihaz eylemlerinin bir listesini ve bunların geçerli durumunu görmek için **Cihaz eylemleri**'ni seçin.
- **Kurulum** > **TeamViewer Bağlayıcısı** - Cihazlarda TeamViewer yazılımını kullanarak uzaktan yönetimi yapılandırmanızı sağlar. Ayrıntılar için bkz. [Intune ile yönetilen Android cihazları için uzaktan yardım sağlama](/intune/device-profile-android-teamviewer).

Intune, yalnızca şirkete ait cihazlarda uygulama envanteri toplar. Uygulamalar, kişisel cihazlarda envantere alınmaz. Şirkete ait Windows 10 bilgisayarlarda yalnızca modern uygulama envanteri toplanır. Intune, cihazdaki Win32 uygulamalar hakkında bilgi toplamaz. Cihazlarda kullandığınız operatöre bağlı olarak tüm envanter öğeleri toplanmayabilir.
