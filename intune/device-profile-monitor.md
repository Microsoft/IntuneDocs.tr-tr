---
title: Microsoft Intune - Azure’da cihaz profillerini görüntüleme | Microsoft Docs
description: Microsoft Intune'da cihaz yapılandırma profili ayrıntılarını görüntüleyin ve yönetin; ayrıca bir profile atanmış olan cihaz sayısının grafik gösterimine bakın ve hangi cihazların atanmış veya dağıtılmış profilleri olduğunu görün.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9deaed87-fb4b-4689-ba88-067bc61686d7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e1c2eb08db58940ed575b3dea011395edd6711fc
ms.sourcegitcommit: 401cedcd7acc6cb3a6f18d4679bdadb0e0cdf443
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="monitor-device-profiles-in-microsoft-intune"></a>Microsoft Intune’da cihaz profillerini izleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune'un Azure portalında cihaz yapılandırma profillerinizi izlemeye ve yönetmeye yardımcı olacak bazı özellikleri vardır. Örneğin, profilin durumunu denetleyebilir, hangi cihazların atandığına bakabilir ve profilin özelliklerini güncelleştirebilirsiniz.

## <a name="view-existing-profiles"></a>Mevcut profilleri görüntüleme

1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Cihaz yapılandırması** > **Profiller**'i seçin.

Tüm mevcut profilleriniz listelenir, ayrıca platform ve profilin herhangi bir cihaza atanıp atanmadığı gibi ayrıntıları içerir.

## <a name="view-details-on-a-profile"></a>Profildeki ayrıntıları görüntüleme

Cihaz profilinizi oluşturduktan sonra, Intune grafikler sağlar. Bu grafikler profilin durumunu, örneğin cihazlara başarıyla atandığını veya çakışma gösterip göstermediğini görüntüler.

1. Mevcut bir profil seçin. Örneğin, bir macOS profili seçin.
2. **Genel Bakış** sekmesini seçin.

    Grafikte, belirli bir cihaz profiline atanan cihazların sayısı gösterilir. Örneğin, yapılandırma cihaz profili macOS cihazlarında geçerliyse, grafik macOS cihazlarının sayısını listeler.

    Ayrıca ayrı cihaz profiline atanmış olan diğer platformlardaki cihazların sayısını da gösterir. Örneğin, macOS olmayan cihazların sayısını gösterir.

    ![Cihaz profiline atanmış olan cihazların sayısını görüntüleme](./media/device-configuration-profile-graphical-chart.png)

3. Grafikteki daireyi seçin. **Cihaz durumu** açılır.

    Profile atanmış olan cihazlar listelenir ve profilin başarıyla dağıtılıp dağıtılmadığı gösterilir. Yalnızca belirli bir platformdaki (örneğin, macOS) cihazların listelendiğine de dikkat edin.

    Cihaz durumu ayrıntılarını kapatın.

4. Profilin özelliklerinde (**Profiller** > belirli bir profil seçin), mevcut özellikleri de değiştirebilirsiniz:
  - **Özellikler**: Adı değiştirin veya mevcut ayarlardan herhangi birini güncelleştirin.
  - **Atamalar**: İlkenin uygulanacağı cihazları dahil edin veya dışlayın. Belirli grupları seçmek için **Seçili Gruplar**'ı seçin.
  - **Cihaz durumu**: Profile atanmış olan cihazlar listelenir ve profilin başarıyla dağıtılıp dağıtılmadığı gösterilir. Belirli bir cihazı seçerek, yüklü uygulamalar da dahil olmak üzere daha da fazla ayrıntı görebilirsiniz.
  - **Kullanıcı durumu**: Bu profilden etkilenen cihazlara sahip kullanıcı adlarını listeler ve profilin başarıyla dağıtılıp dağıtılmadığını gösterir. Belirli bir kullanıcı seçerek daha da fazla ayrıntı görebilirsiniz.
  - **Ayar başına durum**: Profil içindeki tek tek ayarları göstererek çıkışa filtre uygular ve ayarın başarıyla uygulanıp uygulanmadığını gösterir.

## <a name="next-steps"></a>Sonraki adımlar
[Kullanıcı ve cihaz profillerini atama](device-profile-assign.md)  
[Cihaz profilleri ile ilgili sık karşılaşılan sorunlar ve çözüm yolları](device-profile-troubleshoot.md)