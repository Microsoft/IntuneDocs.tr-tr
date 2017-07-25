---
title: "Intune cihaz envanterini görüntüleme"
titleSuffix: Intune on Azure
description: "Intune ile yönettiğiniz cihazları görüntüleme ve bunların donanımını ve yüklü uygulamalarını anlama hakkında bilgi edinin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3618c5ee0b4a7ff0e7b6a4d6ed58f77a2af0ba66
ms.sourcegitcommit: fb17b59f4aa2b994b149fcc6d32520f74b0de6a5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2017
---
# <a name="how-to-view-intune-device-inventory"></a>Intune cihaz envanterini görüntüleme


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Cihazlar** iş yükü, size, yönettiğiniz cihazlar hakkında, bunların donanım özellikleri ve üzerlerinde yüklü uygulamalar dahil bilgi sağlar. 

Cihaz envanterini görüntülemek için:

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Cihazlar**’ı seçin.

Şimdi aşağıdaki seçeneklerden birini belirleyin:

- **Genel Bakış** Kaydettiğiniz cihazlar ve her cihazın çalıştırdığı işletim sistemleri hakkında bilgi alın.
- **Yönet** - Yönettiğiniz tüm cihazların listesini görmek için **Tüm Cihazlar**’ı seçin.
    Listedeki cihazlardan birini seçerek <*cihaz adı*> **Genel Bakış** dikey penceresini açın. Burada aşağıdakilerden birini seçebilirsiniz:
    - **Genel bakış**  - Cihaz hakkında adı, sahibi, bir KCG cihazı olup olmadığı, ne zaman iade edildiği ve daha fazlasıyla ilgili genel bilgileri görün.
    ![Cihaza genel bakış](./media/device-overview.png)
    - **Donanım** - Cihaz hakkında boş depolama alanı, modeli ve üreticisi gibi daha ayrıntılı bilgileri görün.
    ![Yönetilen cihaz donanım envanteri](./media/hardware-inventory.png)
    - **Bulunan uygulamalar** - Intune'un cihazda yüklü olduğunu bulduğu tüm uygulamaların bir listesini görüntüler.
    ![Bulunan uygulamalar düğümü](./media/detected-applications.png)
    


    - **Cihaz uyumluluğu** - Cihaza atanan tüm uyumluluk ilkelerinin uyumluluk durumunu görüntüler.
    - **Cihaz yapılandırması** - Cihaza atanmış tüm cihaz yapılandırma ilkelerinin uyumluluk durumunu görüntüler.
- **İzleme** Yönettiğiniz cihazlarda yapılan cihaz eylemlerinin bir listesini ve bunların geçerli durumunu görmek için **Cihaz Eylemleri**'ni seçin.
- **Kurulum** > **TeamViewer Bağlayıcısı** - Cihazlarda TeamViewer yazılımını kullanarak uzaktan yönetimi yapılandırmanızı sağlar. Ayrıntılar için bkz. [Intune ile yönetilen Android cihazları için uzaktan yardım sağlama](/intune/device-profile-android-teamviewer).

>[!NOTE]
> Intune, yalnızca şirkete ait cihazlarda uygulama envanteri toplar. Uygulamalar, kişisel cihazlarda envantere alınmaz. Şirkete ait Windows 10 bilgisayarlarda yalnızca modern uygulama envanteri toplanır. Intune, cihazdaki Win32 uygulamalar hakkında bilgi toplamaz.
