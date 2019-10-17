---
title: Microsoft Intune - Azure’da cihaz profillerini görüntüleme | Microsoft Docs
description: Microsoft Intune’da cihaz yapılandırma profili ayrıntılarını görüntüleyin ve yönetin; ayrıca bir profile atanmış olan cihaz sayısının grafik gösterimine bakın ve hangi cihazların atanmış veya dağıtılmış profilleri olduğunu görün. Çakışan ayarlara sahip profillerde sorun da giderebilirsiniz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/25/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9deaed87-fb4b-4689-ba88-067bc61686d7
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6110cdf76649c2f4e0f06cf14fc892d7156d34b9
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506857"
---
# <a name="monitor-device-profiles-in-microsoft-intune"></a>Microsoft Intune’da cihaz profillerini izleme

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune'un Azure portalında cihaz yapılandırma profillerinizi izlemeye ve yönetmeye yardımcı olacak bazı özellikleri vardır. Örneğin, profilin durumunu denetleyebilir, hangi cihazların atandığına bakabilir ve profilin özelliklerini güncelleştirebilirsiniz.

## <a name="view-existing-profiles"></a>Mevcut profilleri görüntüleme

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Cihaz yapılandırması** > **Profiller**'i seçin.

Tüm mevcut profilleriniz listelenir, ayrıca platform gibi ayrıntılar ve profilin herhangi bir cihaza atanıp atanmadığı gösterilir.

## <a name="view-details-on-a-profile"></a>Profildeki ayrıntıları görüntüleme

Cihaz profilinizi oluşturduktan sonra, Intune grafikler sağlar. Bu grafikler profilin durumunu, örneğin cihazlara başarıyla atandığını veya çakışma gösterip göstermediğini görüntüler.

1. Mevcut bir profil seçin. Örneğin, bir macOS profili seçin.
2. **Genel Bakış** sekmesini seçin.

    Üstteki grafikte, belirli bir cihaz profiline atanan cihazların sayısı gösterilir. Örneğin, yapılandırma cihaz profili macOS cihazlarında geçerliyse, grafik macOS cihazlarının sayısını listeler.

    Ayrıca ayrı cihaz profiline atanmış olan diğer platformlardaki cihazların sayısını da gösterir. Örneğin, macOS olmayan cihazların sayısını gösterir.

    ![Cihaz profiline atanmış olan cihazların sayısını görüntüleme](./media/device-profile-monitor/device-configuration-profile-graphical-chart.png)

    Alttaki grafikte, belirli bir cihaz profiline atanan kullanıcıların sayısı gösterilir. Örneğin, yapılandırma cihaz profili macOS kullanıcılarında geçerliyse, grafik macOS kullanıcılarının sayısını listeler.

3. Üstteki grafikte yer alan daireyi seçin. **Cihaz durumu** açılır.

    Profile atanmış olan cihazlar listelenir ve profilin başarıyla dağıtılıp dağıtılmadığı gösterilir. Yalnızca belirli bir platformdaki (örneğin, macOS) cihazların listelendiğine de dikkat edin.

    **Cihaz durumu** ayrıntılarını kapatın.

4. Alttaki grafikte yer alan daireyi seçin. **Kullanıcı durumu** açılır. 

    Profile atanmış olan kullanıcılar listelenir ve profilin başarıyla dağıtılıp dağıtılmadığı gösterilir. Yalnızca belirli bir platformdaki (örneğin, macOS) kullanıcıların listelendiğine de dikkat edin.

    **Kullanıcı durumu** ayrıntılarını kapatın.

5. **Profiller** listesine dönerek belirli bir profil seçin. Ayrıca mevcut özellikleri değiştirebilirsiniz:
    - **Özellikler**: Adı değiştirin veya mevcut ayarlardan herhangi birini güncelleştirin.
    - **Atamalar**: İlkenin uygulanacağı cihazları dahil edin veya dışlayın. Belirli grupları seçmek için **Seçili Gruplar**'ı seçin.
    - **Cihaz durumu**: Profile atanmış olan cihazlar listelenir ve profilin başarıyla dağıtılıp dağıtılmadığı gösterilir. Belirli bir cihazı seçerek, yüklü uygulamalar da dahil olmak üzere daha da fazla ayrıntı görebilirsiniz.
    - **Kullanıcı durumu**: Bu profilden etkilenen cihazlara sahip kullanıcı adlarını listeler ve profilin başarıyla dağıtılıp dağıtılmadığını gösterir. Belirli bir kullanıcı seçerek daha da fazla ayrıntı görebilirsiniz.
    - **Ayar başına durum**: Profil içindeki tek tek ayarları göstererek çıkışa filtre uygular ve ayarın başarıyla uygulanıp uygulanmadığını gösterir.

## <a name="view-conflicts"></a>Çakışmaları görüntüleme

**Cihazlar** > **Tüm cihazlar**’da çakışma yaratan ayarları görebilirsiniz. Bir çakışma olduğunda, bu ayarı içeren tüm yapılandırma profilleri de gösterilir. Yöneticiler bu özelliği kullanarak sorun gidermeye ve profiller arasındaki herhangi bir uyuşmazlığı düzeltmeye yardımcı olabilir.

1. Intune’da **Cihazlar** > **Tüm Cihazlar**’ı seçtikten sonra listeden mevcut bir cihazı seçin. Son kullanıcılar, Şirket Portalı uygulamasından cihaz adını alabilir.
2. **Cihaz yapılandırması**’nı seçin. Cihaza uygulanan tüm yapılandırma ilkeleri listelenir.
3. İlkeyi seçin. İlke, cihaza uygulanan ilkedeki tüm ayarları gösterir. Bir cihaz **Çakışma** durumundaysa, o satırı seçin. Açılan yeni pencerede, çakışma yaratan ayara sahip tüm profilleri ve profil adlarını görürsünüz.

Çakışma yaratan ayarı ve bunu içeren ilkelerin hangileri olduğunu bulduğunuza göre çakışmayı çözümlemeniz daha kolay olacaktır. 

## <a name="next-steps"></a>Sonraki adımlar
[Kullanıcı ve cihaz profillerini atama](../device-profile-assign.md)  
[Cihaz profilleri ile ilgili sık karşılaşılan sorunlar ve çözüm yolları](device-profile-troubleshoot.md)
