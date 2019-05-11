---
title: Başarı veya başarısızlık Microsoft Intune - Azure güvenlik temelleri denetleme | Microsoft Docs
description: Kullanıcılara ve cihazlara Microsoft Intune MDM, güvenlik temellerini dağıtırken hatası, çakışma ve başarı durumunu denetle Intune istemci günlükleri ve rapor özelliklerini kullanarak sorun giderme konusuna bakın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/19/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a013698e56b342953e52296270e7571a257db860
ms.sourcegitcommit: dde4b8788e96563edeab63f612347fa222d8ced0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65135087"
---
# <a name="monitor-security-baseline-and-profiles-in-microsoft-intune"></a>Güvenlik temeli ve Microsoft Intune profillerini izleme  

Intune, güvenlik temellerini izlemek için çeşitli seçenekler sunar. Kullanıcılara ve cihazlara uygulanan güvenlik temelleri profilini izleyebilirsiniz. Ayrıca, gerçek taban çizgisi ve önerilen değerler aynı (veya eşleşmeyen) herhangi bir cihaza da izleyebilirsiniz.

Bu makalede her iki izleme çalışma seçeneklerde gösterilmektedir.

[Intune, güvenlik temellerini](security-baselines.md) Intune güvenlik temelleri özelliği hakkında daha fazla ayrıntı sağlar.

## <a name="monitor-the-baseline-and-your-devices"></a>Taban çizgisi ve cihazlarınızı izleyin  

Temel izlerken, cihazlarınızı Microsoft önerilerine göre güvenlik durumu hakkında bilgi edinme. Bu güvenlik temelinin genel bakış bölmesinin ınsights'tan Intune konsolunda görüntüleyebilirsiniz.  Verilerin bir taban çizgisi atadıktan sonra görünmesi 24 saate kadar sürer. Sonraki değişiklikler görüntülenmesi altı saat olur.  

Taban çizgisi ve aygıtları için izleme verilerini görüntülemek için oturum açın [Intune portalı](https://go.microsoft.com/fwlink/?linkid=2090973). Ardından, **cihaz güvenliği** > **güvenlik temellerini (Önizleme)** seçin bir taban çizgisi ve Görünüm **genel bakış** bölmesi.

**Genel bakış** bölmesinde, durumunu izlemek için iki yöntem sunar:
- **Cihaz görünümünü** – her bir durum kategorisi taban çizgisi için kaç cihazın bulunan bir özeti.  
- **Kategori başına** -temelindeki her kategori görüntüler ve her bir temel kategori için her bir durum grubu için cihazların yüzdesini içeren bir görünüm. 

Her cihaz hem de kullanılan aşağıdaki durumlardan biri tarafından temsil edilen *cihaz* görünümü ve *Kategori başına* görünümler:  
- **Eşleşen temel** -önerilen ayarları temelindeki tüm ayarlarıyla eşleşmelidir.
- **Taban çizgisi eşleşmiyor** -taban çizgisini en az bir ayarda, önerilen ayarları eşleşmiyor.
- **Yanlış yapılandırılmış** -en az bir ayarı düzgün yapılandırılmamış. Bu durum, çakışma, hata veya bekleyen durumda ayardır anlamına gelir.
- **Uygulanamaz** -en az bir ayar geçerli değildir ve uygulanmaz.


### <a name="device-view"></a>Cihaz görüntüle
Genel Bakış bölmesinin taban çizgisi için bir özel durum kaç tane cihaza sahip bir grafik tabanlı özeti görüntüler; **Atanan Windows 10 cihazlar için güvenlik temeli duruşunu**.  

![Cihazların durumunu denetleyin](./media/security-baselines-monitor/overview.png)

Bir cihazda temelde farklı kategorilerdeki farklı bir durum varsa, cihaza tek bir durumu tarafından temsil edilir. Cihaz temsil eden durum aşağıdaki öncelik sırasını alınır: **Yanlış yapılandırılmış**, **temel eşleşmiyor**, **uygulanamaz**, **eşleşme temel**.  

Bir cihaz varsa, örneğin, bir ayar olarak sınıflandırılan *yapılandırılmış* ve bir veya daha fazla ayarları olarak sınıflandırılan *temel eşleşmiyor*, cihaz olarak sınıflandırılır *yanlışyapılandırılmış*.  

Detaylandırma ve çeşitli durumları olan cihazların bir listesini görüntülemek için grafik tıklayabilirsiniz. Ardından, ayrı aygıtlar hakkındaki ayrıntıları görüntülemek için listeden cihazları tek tek seçebilirsiniz. Örneğin:
- Seçin **cihaz Yapılandırması** > profil ile bir hata durumu seçin:

  ![Cihazların durumunu denetleyin](./media/security-baselines-monitor/device-configuration-profile-list.png)

- Hata profili seçin. Profil ve bunların durumunu tüm ayarların bir listesi gösterilir. Şimdi, hataya neden olan ayar bulmak için kaydırabileceği:

  ![Hataya neden olan ayara bakın](./media/security-baselines-monitor/profile-with-error-status.png)

Soruna neden olan herhangi bir profili ayarları görmek için bu bildirimi kullanın. İlkeler ve Profiller cihaza daha fazla ayrıntı ayrıca Al.

> [!NOTE]
> Bir özelliği ayarlandığında **yapılandırılmadı** temelde, ayarı göz ardı edilir ve hiçbir kısıtlama uygulanır. Özelliği, bir raporlama gösterilmiyor.

### <a name="per-category-view"></a>Kategori Görünümü
Genel Bakış bölmesinin, taban çizgisi için bir kategori başına grafik görüntüler; **Kategoriye göre güvenlik temeli duruşunu**.  Bu görünüm, her kategori taban çizgisinden görüntüler ve bu kategorilerin her biri için bir durum sınıflandırma giren cihazların yüzdesini belirler. 
 
![Kategori başına görünüm durumu](./media/security-baselines-monitor/monitor-baseline-per-category.png)

Durumu **eşleşme temel** %100 cihaz kategorisi için durumu rapor kadar görüntülemez.   

Sütunun üstündeki yukarı-aşağı ok simgesini seçerek kategoriye göre görüntüle her bir sütuna göre sıralama yapabilirsiniz.  


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
