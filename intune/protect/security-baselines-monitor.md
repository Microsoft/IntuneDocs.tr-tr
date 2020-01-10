---
title: Microsoft Intune-Azure 'da güvenlik temellerinin başarısını veya başarısızlığını denetleyin | Microsoft Docs
description: Microsoft Intune MDM 'deki kullanıcılara ve cihazlara güvenlik temelleri dağıtımında hata, çakışma ve başarı durumunu denetleyin. Bkz. istemci günlüklerini kullanarak sorun giderme ve Intune 'daki rapor özellikleri.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: shpate
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cbf82c0bef88e4a6d0e790f4b0ecdf73d2731d5d
ms.sourcegitcommit: 9bb1bcd9f1bdd53b470073da956bbd8b0935dfbc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/31/2019
ms.locfileid: "75556411"
---
# <a name="monitor-security-baseline-and-profiles-in-microsoft-intune"></a>Microsoft Intune 'de güvenlik taban çizgisini ve profillerini izleme

Intune, güvenlik temellerinizi izlemek için çeşitli seçenekler sunar. Kullanıcılarınız ve cihazlarınız için geçerli olan güvenlik temelleri profilini izleyebilirsiniz. Ayrıca, gerçek taban çizgisini ve (veya eşleşmeyen) önerilen değerleri de izleyebilirsiniz.

Bu makalede, izleme seçeneklerinde her ikisi de anlatılmaktadır.

[Intune 'Daki güvenlik temelleri](../security-baselines.md) Microsoft Intune içindeki güvenlik temelleri özelliği hakkında daha fazla bilgi sağlar.

## <a name="monitor-the-baseline-and-your-devices"></a>Taban çizgisini ve cihazlarınızı izleyin

Bir taban çizgisini izlerken, Microsoft 'un önerilerine bağlı olarak cihazlarınızın güvenlik durumu hakkında öngörüler elde edersiniz. Bu öngörüleri Intune konsolundaki güvenlik temelinin genel bakış bölmesinden görüntüleyebilirsiniz.  İlk olarak bir taban çizgisi atadıktan sonra verilerin görünmesi 24 saate kadar sürer. Sonraki değişikliklerin görünmesi altı saate kadar sürer.

Taban çizgisi ve cihazlara ilişkin izleme verilerini görüntülemek için [Microsoft Endpoint Manager Yönetim Merkezi](https://go.microsoft.com/fwlink/?linkid=2109431)' nde oturum açın. Sonra, **uç nokta güvenliği** > **güvenlik temelleri**' ni seçin, bir taban çizgisi seçin ve **genel bakış** bölmesini görüntüleyin.

**Genel bakış** bölmesi, durumu izlemek için iki yöntem sunar:

- **Cihaz görünümü** : taban çizgisinin her bir durum kategorisinde kaç cihaz olduğunu gösteren bir Özet.
- **Kategori başına** -her bir kategoriyi taban çizgisinde görüntüleyen ve her bir temel kategori için her bir durum grubu için cihazların yüzdesini içeren bir görünüm.

Her cihaz aşağıdaki durumlardan biri ile temsil edilir ( *cihaz* görünümünde ve ayrıca *Kategori başına* görünümlerde kullanılır):

- **Taban çizgisi Ile eşleşir** -taban çizgisinin tüm ayarları önerilen ayarlarla eşleşir.
- **Taban çizgisine uymuyor** -temeldeki en az bir ayar önerilen ayarla eşleşmiyor.

  > [!NOTE]
  > Bir temel profil oluşturduğunuzda veya düzenlediğinizde, varsayılan bir değer veya yapılandırma ayarında yapılan herhangi bir değişiklik, "taban çizgisine uymuyor" durumunun oluşmasına neden olur. Değiştirilen ayarları belirleme yardımı için Microsoft Desteği başvurun. 

- **Yanlış yapılandırılmış** -en az bir ayar doğru yapılandırılmamış. Bu durum, ayarın çakışma, hata veya bekleme durumunda olduğu anlamına gelir.
- **Uygulanamaz** -en az bir ayar uygulanabilir değildir ve uygulanmaz.

### <a name="device-view"></a>Cihaz görünümü

Genel bakış bölmesi, ana hat için kaç cihazın belirli bir duruma sahip olduğunu gösteren grafik tabanlı bir Özet görüntüler. **Atanan Windows 10 cihazları için güvenlik temeli duruşunu**.

![Cihazların durumunu denetleme](./media/security-baselines-monitor/overview.png)

Bir cihaz, taban çizgisinde farklı kategorilerden farklı bir duruma sahip olduğunda, cihaz tek bir durum ile temsil edilir. Cihazı temsil eden durum, aşağıdaki öncelik sırasına göre alınır: **yanlış yapılandırılmış**, **taban çizgisine uymuyor**, **uygulanamaz**, **taban çizgisiyle eşleşir**.

Örneğin, bir cihazın *yanlış yapılandırılmış* olarak sınıflandırılan bir ayarı varsa ve bir veya daha fazla ayar *taban çizgisiyle eşleşmezse*, cihaz *yanlış*şekilde sınıflandırılır.

Çeşitli durumlara sahip cihazların listesini incelemek ve görüntülemek için grafiğe tıklayabilirsiniz. Böylece, tek tek cihazların ayrıntılarını görüntülemek için bu listeden tek tek cihazları seçebilirsiniz. Örneğin:

- **Cihaz yapılandırması** ' nı seçin > bir hata durumu Içeren profili seçin:

  ![Bir profilin durumunu görüntüleme](./media/security-baselines-monitor/device-configuration-profile-list.png)

- Hata profilini seçin. Profildeki tüm ayarların listesi ve durumları gösterilir. Şimdi, hataya neden olan ayarı bulmak için kaydırma yapabilirsiniz:

  ![Hataya neden olan ayara bakın](./media/security-baselines-monitor/profile-with-error-status.png)

Bir profilde soruna neden olan ayarları görmek için bu raporlamayı kullanın. Ayrıca cihazlara dağıtılan ilkelerin ve profillerin daha ayrıntılı ayrıntılarını alın.

> [!NOTE]
> Bir özellik taban çizgisinde **Yapılandırılmadı** olarak ayarlandığında, ayar yok sayılır ve hiçbir kısıtlama zorlanmaz. Özelliği herhangi bir raporlamada gösterilmez.

### <a name="per-category-view"></a>Kategori başına görünüm

Genel bakış bölmesi, taban çizgisi için kategori başına bir grafik görüntüler; **Kategoriye göre güvenlik temeli sonrası**.  Bu görünüm, taban çizgisinden her bir kategoriyi görüntüler ve bu kategorilerin her biri için bir durum sınıflandırmasına giren cihazların yüzdesini tanımlar.

![Durumun kategori başına görünümü](./media/security-baselines-monitor/monitor-baseline-per-category.png)

Cihazların %100 ' ü kategori için bu durumu bildirene kadar, **eşleşmelerin temeli** için durum görüntülenmez.

Sütunun en üstünde yukarı aşağı ok simgesini seçerek Kategori tarafından her sütuna göre sıralama yapabilirsiniz.

## <a name="monitor-the-profile"></a>Profili izleme

Profili izlemek, cihazlarınızın dağıtım durumu hakkında fikir verir, ancak temel önerilere göre güvenlik durumunu etkilemez.

1. Intune 'da **güvenlik temelleri** ' ni seçin > oluşturulan temel > **profillerini**seçin.

2. Bir profil seçin. **Genel bakışta**görüntüde bu profilin kaç cihaz ve Kullanıcı tarafından atandığını gösterilmektedir:

   ![Kaç cihaza ve kullanıcıya güvenlik temelleri profili atandığını öğrenin](./media/security-baselines-monitor/existing-profile-overview.png)

3. **Yönet** > **özellikleri**altında, taban çizgisinde tüm ayarların bir listesi gösterilir. Ayrıca, bu ayarlardan herhangi birini değiştirebilirsiniz:

   ![Güvenlik temelleri profilindeki ayarları görme ve güncelleştirme](./media/security-baselines-monitor/manage-settings.png)

4. **İzleyici**' de, her bir cihazda profilin dağıtım durumunu, her bir kullanıcının durumunu ve her bir ayarın durumunu Baseline olarak görebilirsiniz:

   ![Güvenlik temelleri profili için farklı izleyici seçeneklerine bakın](./media/security-baselines-monitor/monitor-status-options.png)

## <a name="troubleshoot-using-per-setting-status"></a>Ayar başına durumu kullanarak sorun giderme

Bir güvenlik temeli dağıttıysanız, ancak dağıtım durumu bir hata gösterir. Aşağıdaki adımlar, hatayı gidermeye yönelik bazı yönergeler sağlar.

1. Intune 'da **güvenlik temelleri** ' ni seçin > oluşturulan temel > **profillerini**seçin.

2. **Ayar başına** > **izleme** > bir profil seçin.

3. Tabloda tüm ayarlar ve her ayarın durumu gösterilmektedir. Hataya neden olan ayarı görmek için **hata** sütununu veya **Çakışma** sütununu seçin.

### <a name="mdm-diagnostic-information"></a>MDM tanılama bilgileri

Artık sorunlu ayarı öğrenmiş oldunuz. Bir sonraki adım, bu ayarın neden bir hata veya çakışmaya neden olduğunu bulmadır.

Windows 10 cihazlarında, yerleşik bir MDM tanılama bilgileri raporu vardır. Bu rapor varsayılan değerleri, geçerli değerleri, ilkeyi listeler, cihaza veya kullanıcıya dağıtılıp dağıtılmadığını gösterir ve daha fazlasını içerir. Ayarın bir çakışmaya veya hataya neden neden olduğunu belirlemenize yardımcı olması için bu raporu kullanın.

1. Cihazda, **ayarlar** > **hesaplar** ' a gidin. **iş veya okul erişimi** > .

2. Hesap > **bilgi** > **gelişmiş tanılama raporu** > **rapor oluştur**' u seçin.

3. **Dışarı aktar**' ı seçin ve oluşturulan dosyayı açın.

4. Raporda, raporun farklı bölümlerinde hata veya çakışma ayarını bulun.

  Örneğin, **kayıtlı yapılandırma kaynakları ve hedef kaynaklar** bölümüne veya **yönetilmeyen ilkeler** bölümüne bakın. Neden bir hata veya çakışmaya neden olduğuna ilişkin bir fikir alabilirsiniz.

[Windows 10 ' da MDM başarısızlıklarını tanılama](https://docs.microsoft.com/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10) bu yerleşik rapor hakkında daha fazla bilgi sağlar.

> [!TIP]
> - Bazı ayarlar GUID 'YI de listeler. Herhangi bir küme değeri için yerel kayıt defterinde (regedit) Bu GUID için arama yapabilirsiniz.
> - Olay Görüntüleyicisi Günlükler, sorunlu ayara (**olay görüntüleyicisi** > **uygulama ve hizmet günlükleri** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostics-Provider** > **admin**) bazı hata bilgilerini de içerebilir.

## <a name="next-steps"></a>Sonraki adımlar

[Cihaz profillerini izleyin](../configuration/device-profile-monitor.md) ve [bazı yaygın sorunlar ve çözümleri görüntüleyin](../configuration/device-profile-troubleshoot.md).
