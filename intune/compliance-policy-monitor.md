---
title: Microsoft Intune - Azure’da cihaz uyumluluk ilkelerini izleme | Microsoft Docs
description: Genel cihaz uyumluluğunu izlemek, raporları görüntülemek ve ilke başına ve ayar başına cihaz uyumluluğunu izlemek için cihaz uyumluluk panosunu kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/20/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7ce117f21c1ad78c2c977466398ce6d30989cc6a
ms.sourcegitcommit: a2bad7465422b98eb3c10f03dc5a24fd99cee78d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/13/2019
ms.locfileid: "67041300"
---
# <a name="monitor-intune-device-compliance-policies"></a>Intune Cihaz uyumluluk ilkelerini izleme

Uyumluluk raporları, cihaz uyumluluğunu gözden geçirmenize ve kuruluşunuzdaki uyumlulukla ilgili sorunları gidermenize yardımcı olur. Bu raporları kullanarak şu konulardaki bilgileri görüntüleyebilirsiniz:

- Cihazların genel uyumluluk durumu
- Ayrı bir ayarın uyumluluk durumu
- Ayrı bir ilkenin uyumluluk durumu
- Cihazları etkileyen belirli ayar ve ilkeleri görüntülemek için bireysel cihazların detayına gitme

## <a name="open-the-compliance-dashboard"></a>Cihaz uyumluluğu panosunu açma

**Intune cihaz uyumluluğu panosunu** açın:

1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

2. **Cihaz uyumluluğu** > **Genel Bakış**’ı seçin. **Cihaz uyumluluğu panosu** açılacaktır.

> [!IMPORTANT]
> Cihaz uyumluluk ilkelerini almak için, cihazların Intune'a kayıtlı olmaları gerekir.

## <a name="dashboard-overview"></a>Panoya genel bakış

Pano açıldığında tüm uyumluluk raporları ile genel bir bakış elde edersiniz. Bu raporlarda şunları görüp denetleyebilirsiniz:

- Genel cihaz uyumluluğu
- İlkeye göre cihaz uyumluluğu
- Ayara göre cihaz uyumluluğu
- Cihaz koruma durumu
- Tehdit aracısı durumu

![Pano görüntüsü, cihaz uyumluluğu panosunu ve farklı raporları gösterir](./media/compliance-policy-monitor/idc-1.png)

Bu raporda gezindikçe her bir ayar için uyumluluk durumu da dahil olmak üzere belirli bir cihazda geçerli bazı uyumluluk ilkeleri ve ayarlarını da görebilirsiniz.

### <a name="device-compliance-status-report"></a>Cihaz uyumluluk durumu raporu

Grafik, Intune’a kayıtlı tüm cihazlar için uyumluluk durumunu gösterir. Cihaz uyumluluk durumları iki farklı veritabanlarında saklanır: Intune ve Azure Active Directory. 

> [!IMPORTANT]
> Intune, cihazdaki tüm uyumluluk değerlendirmeleri için cihaz iade zamanlamasını kullanır. [Cihaz iade zamanlaması hakkında daha fazla bilgi edinin](https://docs.microsoft.com/intune/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

Farklı cihaz uyumluluk ilkesi durumlarının açıklamaları:

- **Uyumlu**: Cihaz, bir veya daha fazla cihaz uyumluluk İlkesi ayarları başarıyla uygulandı.

- **İçinde yetkisiz kullanım süresi:** Cihaz, cihaz uyumluluk İlkesi ayarlarını bir veya daha fazla yöneliktir. Ancak kullanıcı henüz bu ilkeleri uygulamadı. Bu, cihazın uyumsuz ancak yönetici tarafından belirlenen yetkisiz kullanım süresinde olduğunu gösterir.

  - [Uyumlu olmayan cihazlara yönelik eylemler](actions-for-noncompliance.md) hakkında daha fazla bilgi edinin.

- **Değerlendirilmedi**: Yeni kaydedilen cihazlar için başlangıç durumu. Diğer olası nedenler durumu:

  - Uyumluluk denetimi için bir tetikleyici yok ve bir uyumluluk ilkesi atanmamış cihazlar
  - Uyumluluk ilkesinin son güncelleştirmesinden sonra İade edilmeyen cihazları
  - Belirli bir kullanıcı gibi ilişkili olmayan cihazlar:
    - Kullanıcı benzeşimi olmayan Apple'nın cihaz kayıt programı (DEP) aracılığıyla satın alınan iOS cihazları
    - Android kiosk veya ayrılmış Android kuruluş cihazlarının
  - Cihaz kayıt Yöneticisi (DEM) hesabı ile kayıtlı cihazlar

- **Uyumlu değil:** Cihaz, bir veya daha fazla cihaz uyumluluk İlkesi ayarları uygulamak başarısız oldu. Veya kullanıcı ilkelere uyum sağlamadı.

- **Cihaz eşitlenmedi:** Cihazın cihaz uyumluluk İlkesi durumunu bildiremedi aşağıdaki nedenlerden biri:

  - **Bilinmeyen**: Cihaz çevrimdışı veya Intune ya da başka bir nedenle Azure AD ile iletişim kurmak için başarısız.

  - **Hata**: Cihaz, Intune ve Azure AD ile iletişim kuramadı ve neden olan bir hata iletisi aldı.

> [!IMPORTANT]
> Intune’a kaydedilmiş olan ancak hiçbir cihaz uyumluluk ilkesi tarafından hedeflenmeyen cihazlar, **Uyumlu** demeti altında bu rapora dahil edilir.

#### <a name="drill-down-for-more-details"></a>Daha fazla bilgi için detaya gidin

**Cihaz uyumluluk durumu** grafiğinde bir durum seçin. Örneğin **Uyumsuz** durumunu seçin:

![Uyumsuz durumunu seçme](./media/compliance-policy-monitor/select-not-compliant-status.png)

Bu durumdaki cihazlar hakkında işletim sistemi platformu, son iade etme tarihi vb. gibi daha fazla ayrıntı görüntülenir. 

![Pano görüntüsü, bu durumdaki cihazlar hakkında daha fazla ayrıntı sağlar](./media/compliance-policy-monitor/drill-down-details.png)

Belirli bir kullanıcıya ait tüm cihazları görmek istiyorsanız kullanıcının e-postasını yazarak grafik raporunu filtreleyebilirsiniz.

#### <a name="filter-and-columns"></a>Filtre ve sütunlar

![Grafikteki sonuçları değiştirmek için Filtre ve Sütun’u seçme](./media/compliance-policy-monitor/filter-columns.png)

**Filtrele** düğmesini seçtiğinizde uyumluluk durumu, jailbreak uygulanmış cihazlar ve daha fazlasını içeren seçenekleri barındıran filtre öğesi açılır. Sonuçları güncelleştirmek için filtreyi **Uygulayın**.

Grafik çıkışında sütun eklemek ve kaldırmak için **Sütunlar** özelliğini kullanın. Örneğin **Kullanıcı asıl adı**, cihazda kayıtlı e-posta adreslerini gösterebilir. Sonuçları güncelleştirmek için sütunları **Uygulayın**.

#### <a name="device-details"></a>Cihaz ayrıntıları

Grafikten belirli bir cihaz seçin ve daha sonra **Cihaz uyumluluğu**’na tıklayın:

![Belirli bir cihazı ve daha sonra Cihaz Uyumluluğu’nu seçerek uygulanan uyumluluk ilkelerini görüntüleme](./media/compliance-policy-monitor/see-policies-applied-specific-device.png)

Burada, söz konusu cihaz için uygulanan cihaz uyumluluk ilkesi ayarları hakkında daha ayrıntılı bilgiler sunulur. Belirli bir ilkeyi seçtiğinizde ilkedeki tüm ayarlar gösterilir.

### <a name="devices-without-compliance-policy"></a>Uyumluluk ilkesi olmayan cihazlar
**Cihaz uyumluluğu** > **Genel bakış** bölümündeki rapor, atanmış uyumluluk ilkeleri olmayan cihazları da belirler:

![Uyumluluk ilkesi olmayan cihazları görüntüleme](./media/compliance-policy-monitor/devices-without-policies.png)

Kutucuğu seçtiğinizde uyumluluk ilkeleri olmayan cihazlar görüntülenir. Ayrıca cihazın kullanıcısı, ilke dağıtım durumu ve modeli de gösterilir.

#### <a name="what-you-need-to-know"></a>Bilmeniz gerekenler

- **Uyumluluk ilkesi atanmamış cihazları şu şekilde işaretle** güvenlik ayarı için uyumluluk ilkesi olmayan cihazları belirlemek önemlidir. Cihazlar belirlendikten sonra bunlara en az bir uyumluluk ilkesi atayabilirsiniz.

  Bu güvenlik ayarı, Intune portalında yapılandırılabilir. **Cihaz uyumluluğu** > **Uyumluluk ilkesi ayarları**’nı seçin. Daha sonra **Uyumluluk ilkesi atanmamış cihazları şu şekilde işaretle** seçeneğini **Uyumlu** veya **Uyumsuz** olarak ayarlayın. 

  Bu [Intune hizmetinde güvenlik geliştirmesi](https://blogs.technet.microsoft.com/intunesupport/2018/02/09/updated-upcoming-security-enhancements-in-the-intune-service/) hakkında daha fazla bilgi edinin.

- Herhangi bir tür uyumluluk ilkesi atanmış kullanıcılar, cihaz platformu ne olursa olsun raporda yer almaz. Örneğin Android cihazı olan bir kullanıcıya Windows uyumluluk ilkesi atamışsanız cihaz raporda görüntülenmez. Ancak Intune, bu Android cihazı uyumsuz olarak değerlendirir. Sorunların önüne geçmek adına her bir cihaz platformu için ilke oluşturup bunları tüm kullanıcılara dağıtmanızı öneririz.

### <a name="per-policy-device-compliance-report"></a>İlkeye göre cihaz uyumluluğu raporu

**Cihaz uyumluluğu** > **İlke uyumluluğu** raporu, ilkeleri ve uyumlu/uyumsuz cihaz sayısını gösterir. 

![İlke listesi ile ilke için uyumlu ve uyumsuz cihaz sayısını görme](./media/compliance-policy-monitor/idc-8.png)

Belirli bir uyumluluk ilkesi seçtiğinizde bu ilkenin hedeflediği tüm cihazların **uyumluluk durumu**, **kullanıcının e-posta diğer adı**, **cihaz modeli** ve **konum** bilgilerini görebilirsiniz.

## <a name="setting-compliance-report"></a>Ayar uyumluluk raporu

**Cihaz uyumluluğu** > **Ayar uyumluluğu** raporu, uyumluluk ayarı başına tüm uyumluluk durumlarındaki toplam cihaz sayısını gösterir. Tüm uyumluluk ilkelerindeki bütün uyumluluk ilkesi ayarlarını, ilke ayarlarının uygulandığı platformları ve uyumsuz cihaz sayılarını gösterir.

![Farklı ilkelerdeki ayar listesini görme](./media/compliance-policy-monitor/idc-10.png)

Belirli bir ayar seçtiğinizde bu ayarın hedeflediği tüm cihazların **uyumluluk durumu**, **kullanıcının e-posta diğer adı**, **cihaz modeli** ve **konum** bilgilerini görebilirsiniz.

> [!NOTE]
> Azure Active Directory katılımlı Windows 10 cihazlar, Sistem Hesabı’nı uyumsuz kullanıcı olarak gösterebilir. Bu beklenen bir davranıştır ve genel cihaz uyumluluğunu etkilemez. 

## <a name="view-status-of-device-policies"></a>Cihaz ilkelerinin durumunu görüntüleme

Platforma göre, ilkelerinizin farklı durumlarını denetleyebilirsiniz. Örneğin, bir macOS uyumluluk ilkeniz olsun. Bu ilke tarafından etkilenen cihazları görmek ve çakışma veya hata olup olmadığını bilmek istiyorsunuz.

Bu özellik cihaz durumu bildirimine eklenmiştir:

1. **Cihaz uyumluluğu** > **İlkeler**'i seçin. Platform da dahil olmak üzere ilkelerin listesi, ilkenin atanıp atanmadığı ve diğer ayrıntılar gösterilir.
2. Bir ilke seçin ve **Genel Bakış**'ı seçin. Bu görünümde, ilke ataması aşağıdaki durumları içerir:

    - Başarılı: İlke uygulanır
    - Hata: İlkeyi uygulamak başarısız oldu. Bu ileti, genellikle bir açıklamaya bağlantı veren bir hata kodu görüntüler. 
    - Çakışma: İki ayar aynı cihaza uygulanır ve Intune çakışma sıralayamazsınız. Yöneticinin gözden geçirmesi gerekir.
    - Bekleyen: Cihaz İlkesi henüz almak için Intune hizmetine giriş iade edilmemiş. 
    - Uygulanamaz: Cihaz, ilkeyi alamaz. Örneğin ilke, iOS 11.1’e özel bir ayarı güncelleştiriyor ancak cihaz iOS 10 kullanıyor. 

3. Bu ilkeyi kullanan cihazlarla ilgili ayrıntıları görmek için, durumlardan birini seçin. Örneğin **Başarılı**'yı seçin. Sonraki pencerede, cihaz adı ve dağıtım durumu gibi belirli cihaz ayrıntıları listelenir.

## <a name="how-intune-resolves-policy-conflicts"></a>Intune ilke çakışmalarını nasıl çözümler?
Bir cihaza birden çok Intune ilkesi uygulandığında ilke çakışmaları olabilir. İlke ayarları çakışırsa, Intune tüm çakışmaları aşağıdaki kuralları kullanarak çözer:

- Çakışan ayarlar bir Intune yapılandırma ilkesine ve bir uyumluluk ilkesine aitse, uyumluluk ilkesindeki ayarlar yapılandırma ilkesindeki ayarlara göre önceliklidir. Bu, yapılandırma ilkesindeki ayarlar daha güvenli olsa bile gerçekleşir.

- Birden çok uyumluluk ilkesi dağıttıysanız, Intune bu ilkelerin en güvenli olanını kullanır.
