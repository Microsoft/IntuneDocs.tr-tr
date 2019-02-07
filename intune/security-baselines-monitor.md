---
title: Başarı veya başarısızlık Microsoft Intune - Azure güvenlik temelleri denetleme | Microsoft Docs
description: Kullanıcılara ve cihazlara Microsoft Intune MDM, güvenlik temellerini dağıtırken hatası, çakışma ve başarı durumunu denetle Intune istemci günlükleri ve rapor özelliklerini kullanarak sorun giderme konusuna bakın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/24/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: db748f7c39cb133c5c7025dbb299f3fd1411ba17
ms.sourcegitcommit: 5b4a6c17bdba2f87e6ae81a3ac0cb88438a0fa27
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55807758"
---
# <a name="monitor-the-security-baseline-and-profile-in-microsoft-intune"></a>Güvenlik temeli ve Intune profilinde izleyin

Farklı güvenlik temellerini kullanırken izleme seçenekleri vardır. Kullanıcılara ve cihazlara uygulanan güvenlik temelleri profilini izleyebilirsiniz. Ayrıca, gerçek taban çizgisi ve önerilen değerler aynı (veya eşleşmeyen) herhangi bir cihaza da izleyebilirsiniz.

Bu makalede her iki izleme çalışma seçeneklerde gösterilmektedir.

[Intune, güvenlik temellerini](security-baselines.md) Intune güvenlik temelleri özelliği hakkında daha fazla ayrıntı sağlar.

## <a name="monitor-the-baseline-and-your-devices"></a>Taban çizgisi ve cihazlarınızı izleyin

Taban çizgisi izlerken, cihazlarınızı Microsoft önerilerine göre güvenlik durumu hakkında bilgi edinme.

> [!NOTE]
> Temel ilk atandıktan sonra raporları güncelleştirilmesi 24 saat sürebilir. Bundan sonra güncelleştirme 6 saat kadar sürebilir.

1. İçinde [Azure portalında](https://portal.azure.com/)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.
2. Seçin **güvenlik temellerini (Önizleme)** > bir taban çizgisi seçin.
3. İçinde **genel bakış**, kaç cihazın seçtiğiniz taban çizgisi ve farklı durumlarını etkilendiğini grafik gösterir:

    ![Cihazların durumunu denetleyin](./media/security-baselines-monitor/overview.png)

    Aşağıdaki durumlar mevcuttur:

    - **Eşleşen temel**: Önerilen ayarları temel tüm ayarlarla eşleşen.
    - **Taban çizgisi eşleşmiyor**: Taban çizgisini en az bir ayarda, önerilen ayarları eşleşmiyor.
    - **Yanlış yapılandırılmış**: En az bir ayarı düzgün yapılandırılmamış. Bu durum, çakışma, hata veya bekleyen durumda ayardır anlamına gelir.
    - **Uygulanamaz**: En az bir ayar geçerli değildir ve uygulanmaz.

4. Cihaz durumları birini seçin. Örneğin, **Misconfigured** durumu.

5. O durumdaki tüm cihazların bir listesi gösterilir. Daha fazla bilgi almak için belirli bir cihaz seçin. 

    Aşağıdaki örnekte, seçin **cihaz Yapılandırması** > profil ile bir hata durumu seçin:

    ![Cihazların durumunu denetleyin](./media/security-baselines-monitor/device-configuration-profile-list.png)

    Hata profili seçin. Profil ve bunların durumunu tüm ayarların bir listesi gösterilir. Şimdi, hataya neden olan ayar bulmak için kaydırabileceği:

    ![Hataya neden olan ayara bakın](./media/security-baselines-monitor/profile-with-error-status.png)

Soruna neden olan herhangi bir profili ayarları görmek için bu bildirimi kullanın. İlkeler ve Profiller cihaza daha fazla ayrıntı ayrıca Al.

> [!NOTE]
> Bir özelliği ayarlandığında **yapılandırılmadı** temelde, ayarı göz ardı edilir ve hiçbir kısıtlama uygulanır. Özelliği, bir raporlama gösterilmiyor.

## <a name="monitor-the-profile"></a>Profil İzleyicisi

Profil izleme, cihazlarınızın dağıtım durumunu, ancak değil temel önerilerine göre güvenlik durumu hakkında Öngörüler sunar.

1. Intune'da seçin **güvenlik temellerini** > bir taban çizgisi seçin > **oluşturulan profiller**.

2. Bir profil seçin. İçinde **genel bakış**, kaç cihazın resmi gösterir ve bu profile atanan kullanıcınız:

    ![Kaç cihaz ve kullanıcıları güvenlik temelleri profili Atanana bakın](./media/security-baselines-monitor/existing-profile-overview.png)

3. Altında **Yönet** > **özellikleri**, tüm temel ayarları gösterilir. Bu ayarlardan herhangi birini değiştirebilirsiniz:

    ![Görebilir ve güvenlik temelleri profilinde ayarlarını güncelleştirme](./media/security-baselines-monitor/manage-settings.png)

4. İçinde **İzleyici**, tek tek cihazlar, her kullanıcının durumunu ve temelindeki her bir ayar durumu profili dağıtım durumunu görebilirsiniz:

    ![Güvenlik temelleri profili için farklı İzleyici seçeneklere bakın](./media/security-baselines-monitor/monitor-status-options.png)

## <a name="troubleshoot-using-per-setting-status"></a>Her bir ayar durumu kullanmayla ilgili sorun giderme

Güvenlik temeli dağıtılmış, ancak bir hata dağıtım durumunu gösterir. Aşağıdaki adımlar, hatayı giderme hakkında rehberlik sağlar.

1. Intune'da seçin **güvenlik temellerini** > bir taban çizgisi seçin > **oluşturulan profiller**.
2. Bir profili seçin > altında **İzleyici** > **her bir ayar durumu**.
3. Tablo, tüm ayarlarını ve her bir ayar durumu gösterir. Seçin **hata** sütun veya **çakışma** hataya neden olan ayar görmek için sütun.

### <a name="mdm-diagnostic-information"></a>MDM tanılama bilgileri

Sorunlu ayarı biliyorsunuz. Sonraki adım, neden bu ayar bir hatası veya çakışması neden olduğunu bulmaktır. 

Windows 10 cihazlarda yerleşik MDM tanılama bilgileri rapor yoktur. Bu rapor, varsayılan değerler, geçerli değerleri içerir, ilke listeler, cihaz veya kullanıcı ve daha fazla bilgi için dağıtılan olmadığını gösterir. Neden ayarı çakışmaya veya hataya neden olduğunu belirlemenize yardımcı olması için bu raporu kullanın.

1. Cihaz üzerinde Git **ayarları** > **hesapları** > **işe veya okula erişim**.
2. Hesabı seçin > **bilgisi** > **Gelişmiş tanılama raporu** > **rapor oluşturma**.
3. Seçin **dışarı**, oluşturulan dosyasını açın.
4. Raporda hatası veya çakışması raporun farklı bölümlerini ayarında arayın.

  Örneğin, konum **kayıtlı yapılandırma kaynaklarını ve hedef kaynaklar** bölüm veya **ilkeleri yönetilmeyen** bölümü. Neden bunu bir hata veya çakışmaya neden olan bir fikir elde edebilirsiniz.

[Windows 10 MDM hatalarını tanılamak](https://docs.microsoft.com/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10) bu yerleşik rapor hakkında daha fazla bilgi sağlar.

> [!TIP]
> - Bazı ayarlar da GUID listeleyin. Bu GUID herhangi bir küme değer için yerel kayıt defterinde (regedit) arayabilirsiniz.
> - Olay Görüntüleyicisi günlüklerini sorunlu ayarı bazı hata bilgilerini de içerebilir (**Olay Görüntüleyicisi'ni** > **uygulama ve hizmet günlükleri**  >   **Microsoft** > **Windows** > **Kurumsal tanılama sağlayıcı DeviceManagement** > **yönetici** ).

## <a name="next-steps"></a>Sonraki adımlar

[Cihaz profillerini izleme](device-profile-monitor.md) ve [bazı yaygın sorunlar ve çözümleri bkz](device-profile-troubleshoot.md).
