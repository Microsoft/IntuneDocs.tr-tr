---
title: Microsoft Intune - Azure’da cihaz uyumluluk ilkelerini izleme | Microsoft Docs
description: Genel cihaz uyumluluğunu izlemek, raporları görüntülemek ve ilke başına ve ayar başına cihaz uyumluluğunu izlemek için cihaz uyumluluk panosunu kullanın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 128f615a9551c31e6b0e0de4f1d269083874bf48
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77515127"
---
# <a name="monitor-intune-device-compliance-policies"></a>Intune Cihaz uyumluluk ilkelerini izleme

Uyumluluk raporları, cihaz uyumluluğunu gözden geçirmenize ve kuruluşunuzdaki uyumlulukla ilgili sorunları gidermenize yardımcı olur. Bu raporları kullanarak şu konulardaki bilgileri görüntüleyebilirsiniz:

- Cihazların genel uyumluluk durumu
- Ayrı bir ayarın uyumluluk durumu
- Ayrı bir ilkenin uyumluluk durumu
- Cihazları etkileyen belirli ayar ve ilkeleri görüntülemek için bireysel cihazların detayına gitme

## <a name="open-the-compliance-dashboard"></a>Cihaz uyumluluğu panosunu açma

**Intune cihaz uyumluluğu panosunu** açın:

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2. **Cihazların** > **genel bakış** > **uyumluluk durumu** sekmesini seçin.

> [!IMPORTANT]
> Cihaz uyumluluk ilkelerini almak için, cihazların Intune'a kayıtlı olmaları gerekir.

## <a name="dashboard-overview"></a>Panoya genel bakış

Pano açıldığında tüm uyumluluk raporları ile genel bir bakış elde edersiniz. Bu raporlarda şunları görüp denetleyebilirsiniz:

- Genel cihaz uyumluluğu
- İlkeye göre cihaz uyumluluğu
- Ayara göre cihaz uyumluluğu
- Tehdit aracısı durumu
- Cihaz koruma durumu

![Pano görüntüsü, cihaz uyumluluğu panosunu ve farklı raporları gösterir](./media/compliance-policy-monitor/idc-1.png)

Bu raporda gezindikçe her bir ayar için uyumluluk durumu da dahil olmak üzere belirli bir cihazda geçerli bazı uyumluluk ilkeleri ve ayarlarını da görebilirsiniz.

### <a name="device-compliance-status"></a>Cihaz uyumluluk durumu

**Cihaz uyumluluk durumu** grafiği, Intune 'a kayıtlı tüm cihazların uyumluluk durumlarını gösterir. Cihaz uyumluluk durumları iki farklı veritabanında tutulur: Intune ve Azure Active Directory.

> [!IMPORTANT]
> Intune, cihazdaki tüm uyumluluk değerlendirmeleri için cihaz iade zamanlamasını kullanır. [Cihaz iade zamanlaması hakkında daha fazla bilgi edinin](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

Farklı cihaz uyumluluk ilkesi durumlarının açıklamaları:

- **Uyumlu**: Cihaz, bir veya daha fazla cihaz uyumluluk ilkesi ayarını başarıyla uyguladı.

- **Yetkisiz kullanım süresinde:** Cihaz, bir veya daha fazla cihaz uyumluluk ilkesi ayarı tarafından hedefleniyor. Ancak kullanıcı henüz bu ilkeleri uygulamadı. Bu, cihazın uyumsuz ancak yönetici tarafından belirlenen yetkisiz kullanım süresinde olduğunu gösterir.

  - [Uyumlu olmayan cihazlara yönelik eylemler](actions-for-noncompliance.md) hakkında daha fazla bilgi edinin.

- **Değerlendirilmedi**: Yeni kaydedilen cihazlar için ilk durum. Bu durumun diğer olası nedenleri şunlardır:

  - Uyumluluk ilkesi atanmamış ve uyumluluğu denetlemek için bir tetikleyicisi olmayan cihazlar
  - Uyumluluk ilkesinin son güncelleştirilme sonrasında iade edilmemiş cihazlar
  - Belirli bir kullanıcıyla ilişkilendirilmemiş cihazlar, örneğin:
    - Apple 'ın Kullanıcı benzeşimi olmayan Aygıt Kayıt Programı (DEP) aracılığıyla satın alınan iOS/ıpados cihazları
    - Android bilgi noktası veya Android kurumsal adanmış cihazlar
  - Cihaz Kayıt Yöneticisi (DEM) hesabıyla kaydedilen cihazlar

- **Uyumsuz**: Cihaz, bir veya daha fazla cihaz uyumluluk ilkesi ayarını uygulayamadı. Veya kullanıcı ilkelere uyum sağlamadı.

- **Cihaz eşitlenmedi:** Cihaz, aşağıdaki nedenlerden biri sonucunda cihaz uyumluluk ilkesi durumunu bildiremedi:

  - **Bilinmeyen**: Cihaz çevrimdışı veya Intune ya da Azure AD ile başka bir nedenle iletişim kuramadı.

  - **Hata**: Cihaz, Intune ve Azure AD ile iletişim kuramadı ve bunun nedenini açıklayan bir hata iletisi aldı.

> [!IMPORTANT]
> Intune’a kaydedilmiş olan ancak hiçbir cihaz uyumluluk ilkesi tarafından hedeflenmeyen cihazlar, **Uyumlu** demeti altında bu rapora dahil edilir.

#### <a name="drill-down-for-more-details"></a>Daha fazla bilgi için detaya gidin

**Cihaz uyumluluk durumu** grafiğinde bir durum seçin. Örneğin **Uyumsuz** durumunu seçin:

![Uyumsuz durumunu seçme](./media/compliance-policy-monitor/select-not-compliant-status.png)

Bu eylem **cihaz uyumluluk** penceresini açar ve cihazları bir **cihaz durumu** grafiğinde görüntüler. Grafik, işletim sistemi platformu, son iade tarihi ve daha fazlası dahil olmak üzere söz konusu durumdaki cihazlar hakkında daha fazla ayrıntı gösterir.
![Pano görüntüsü bu belirli durumda cihaz hakkında daha fazla ayrıntı gösterir](./media/compliance-policy-monitor/drill-down-details.png)

Belirli bir kullanıcıya ait tüm cihazları görmek istiyorsanız kullanıcının e-postasını yazarak grafik raporunu filtreleyebilirsiniz.

#### <a name="filter-and-columns"></a>Filtre ve sütunlar

![Grafikteki sonuçları değiştirmek için Filtre ve Sütun’u seçme](./media/compliance-policy-monitor/filter-columns.png)

**Filtre** düğmesini seçtiğinizde, filtre, **Uyumluluk** durumu, **jailbreak uygulanmış** cihazları ve daha fazlası dahil olmak üzere daha fazla seçenek ile açılır. Sonuçları güncelleştirmek için filtreyi **Uygulayın**.

Grafik çıkışında sütun eklemek ve kaldırmak için **Sütunlar** özelliğini kullanın. Örneğin **Kullanıcı asıl adı**, cihazda kayıtlı e-posta adreslerini gösterebilir. Sonuçları güncelleştirmek için sütunları **Uygulayın**.

#### <a name="device-details"></a>Cihaz ayrıntıları

**Cihaz ayrıntıları** grafiğinde, belirli bir cihaz seçin ve ardından **cihaz uyumluluğu**' nu seçin:

![Belirli bir cihazı ve daha sonra Cihaz Uyumluluğu’nu seçerek uygulanan uyumluluk ilkelerini görüntüleme](./media/compliance-policy-monitor/see-policies-applied-specific-device.png)

Intune, bu cihaza uygulanan cihaz uyumluluk ilkesi ayarları hakkında daha fazla ayrıntı görüntüler. Belirli bir ilkeyi seçtiğinizde ilkedeki tüm ayarlar gösterilir.

### <a name="devices-without-compliance"></a>Uyumlu olmayan cihazlar

Uyumluluk *durumu* sayfasında, *ilke uyumluluk* grafiği ' nin yanında, uyumluluk ilkeleri atanmamış cihazlarla ilgili bilgileri görüntülemek Için **Uyumluluk ilkesi olmayan cihazlar** kutucuğunu seçebilirsiniz:

![Uyumluluk ilkesi olmayan cihazları görüntüleme](./media/compliance-policy-monitor/devices-without-policies.png)

Kutucuğu seçtiğinizde uyumluluk ilkeleri olmayan cihazlar görüntülenir. Ayrıca cihazın kullanıcısı, ilke dağıtım durumu ve modeli de gösterilir.

#### <a name="what-you-need-to-know"></a>Bilmeniz gerekenler

- **Uyumluluk ilkesi atanmamış cihazları şu şekilde işaretle** güvenlik ayarı için uyumluluk ilkesi olmayan cihazları belirlemek önemlidir. Cihazlar belirlendikten sonra bunlara en az bir uyumluluk ilkesi atayabilirsiniz.

  Bu güvenlik ayarı, Intune portalında yapılandırılabilir. **Cihazlara** , uyumluluk **ilkeleri** > **Uyumluluk ilkesi ayarları** > . Daha sonra **Uyumluluk ilkesi atanmamış cihazları şu şekilde işaretle** seçeneğini **Uyumlu** veya **Uyumsuz** olarak ayarlayın.

  Bu [Intune hizmetinde güvenlik geliştirmesi](https://blogs.technet.microsoft.com/intunesupport/2018/02/09/updated-upcoming-security-enhancements-in-the-intune-service/) hakkında daha fazla bilgi edinin.

- Herhangi bir tür uyumluluk ilkesi atanmış kullanıcılar, cihaz platformu ne olursa olsun raporda yer almaz. Örneğin Android cihazı olan bir kullanıcıya Windows uyumluluk ilkesi atamışsanız cihaz raporda görüntülenmez. Ancak Intune, bu Android cihazı uyumsuz olarak değerlendirir. Sorunların önüne geçmek adına her bir cihaz platformu için ilke oluşturup bunları tüm kullanıcılara dağıtmanızı öneririz.

### <a name="per-policy-device-compliance"></a>İlkeye göre cihaz uyumluluğu

**İlke uyumluluk** grafiği, ilkeleri ve kaç cihazın uyumlu ve uyumsuz olduğunu gösterir.

![İlke listesi ile ilke için uyumlu ve uyumsuz cihaz sayısını görme](./media/compliance-policy-monitor/idc-8.png)

### <a name="setting-compliance"></a>Ayar uyumluluğu

**Ayar uyumluluğu** grafiği tüm uyumluluk ilkelerinden tüm cihaz uyumluluk ilkesi ayarlarını, ilke ayarlarının uygulandığı platformları ve uyumlu olmayan cihazların sayısını gösterir.

![Farklı ilkelerdeki ayar listesini görme](./media/compliance-policy-monitor/idc-10.png)

## <a name="view-compliance-reports"></a>Uyumluluk raporlarını görüntüle

*Uyumluluk durumundaki*grafikleri kullanmanın yanı sıra, **cihaz uyumluluğu** > **raporlar** ' a gidebilirsiniz.

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2. **Cihazlar** > **İzleyicisi**' ni seçin ve ardından aşağıdaki **Uyumluluk** ' den görüntülemek istediğiniz raporu seçin. Kullanılabilir uyumluluk raporlarının bazıları şunlardır:

   - Cihaz uyumluluğu
   - Uyumsuz cihazlar
   - Uyumluluk ilkesi olmayan cihazlar
   - Ayar uyumluluğu
   - İlke uyumluluğu
   - Windows sistem durumu kanıtlama raporu
   - Tehdit aracısı durumu

Raporlar hakkında daha fazla bilgi için bkz. [Intune raporları](../fundamentals/reports.md)

## <a name="view-status-of-device-policies"></a>Cihaz ilkelerinin durumunu görüntüleme

Platforma göre, ilkelerinizin farklı durumlarını denetleyebilirsiniz. Örneğin, bir macOS uyumluluk ilkeniz olsun. Bu ilke tarafından etkilenen cihazları görmek ve çakışma veya hata olup olmadığını bilmek istiyorsunuz.

Bu özellik cihaz durumu bildirimine eklenmiştir:

1. **Cihaz** > **uyumluluk ilkeleri** > **ilkeleri**' ni seçin. Platform da dahil olmak üzere ilkelerin listesi, ilkenin atanıp atanmadığı ve diğer ayrıntılar gösterilir.
2. Bir ilke seçin ve **Genel Bakış**'ı seçin. Bu görünümde, ilke ataması aşağıdaki durumları içerir:

    - **Başarılı**: ilke uygulandı
    - **Hata**: ilke uygulanamadı. Bu ileti, genellikle bir açıklamaya bağlantı veren bir hata kodu görüntüler.
    - **Çakışma**: aynı cihaza iki ayar uygulanır ve Intune çakışmayı sıralayamazsınız. Yöneticinin gözden geçirmesi gerekir.
    - **Bekliyor**: cihaz, ilkeyi henüz alacak şekilde Intune ile iade edilmedi.
    - **Uygulanamaz**: cihaz ilkeyi alamıyor. Örneğin ilke, iOS 11.1’e özel bir ayarı güncelleştiriyor ancak cihaz iOS 10 kullanıyor.

3. Bu ilkeyi kullanan cihazlarla ilgili ayrıntıları görmek için, durumlardan birini seçin. Örneğin **Başarılı**'yı seçin. Sonraki pencerede, cihaz adı ve dağıtım durumu gibi belirli cihaz ayrıntıları listelenir.

## <a name="how-intune-resolves-policy-conflicts"></a>Intune ilke çakışmalarını nasıl çözümler?

Bir cihaza birden çok Intune ilkesi uygulandığında ilke çakışmaları olabilir. İlke ayarları çakışırsa, Intune tüm çakışmaları aşağıdaki kuralları kullanarak çözer:

- Çakışan ayarlar bir Intune yapılandırma ilkesine ve bir uyumluluk ilkesine aitse, uyumluluk ilkesindeki ayarlar yapılandırma ilkesindeki ayarlara göre önceliklidir. Bu, yapılandırma ilkesindeki ayarlar daha güvenli olsa bile gerçekleşir.

- Birden çok uyumluluk ilkesi dağıttıysanız, Intune bu ilkelerin en güvenli olanını kullanır.

## <a name="next-steps"></a>Sonraki adımlar

[Uyumluluk ilkelerine genel bakış](device-compliance-get-started.md)
