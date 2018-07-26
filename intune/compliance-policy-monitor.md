---
title: Microsoft Intune - Azure’da cihaz uyumluluk ilkelerini izleme | Microsoft Docs
description: Genel cihaz uyumluluğunu izlemek, raporları görüntülemek ve ilke başına ve ayar başına cihaz uyumluluğunu izlemek için cihaz uyumluluk panosunu kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 7/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 557bdbace1752b8680cd15d7ba190577bec23e24
ms.sourcegitcommit: 2e849eea920dcd6ef1b78e5aee26434bb7b01bff
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/18/2018
ms.locfileid: "39132468"
---
# <a name="monitor-intune-device-compliance-policies"></a>Intune Cihaz uyumluluk ilkelerini izleme

Uyumluluk raporları, yöneticilerin kuruluşlarındaki cihazların uyumluluk duruşunu analiz etmesine ve kuruluşlarındaki kullanıcıların karşılaştığı uyumluluk sorunlarını hızla gidermelerine yardımcı olur. Cihazların genel uyumluluk durumunu, tek bir ayar için uyumluluk durumunu ve tek bir ilke için uyumluluk durumunu görüntüleyebilir ve tek tek cihazların ayrıntılarına inerek söz konusu cihazı etkileyen belirli ayar ve ilkelere bakabilirsiniz.

## <a name="before-you-begin"></a>Başlamadan önce

Azure portalında **Intune Cihaz uyumluluk panosu**’nu bulmak için şu adımları izleyin:

1. [Azure portalında](https://portal.azure.com) Intune kimlik bilgilerinizle oturum açın.

2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.

3. **Cihaz uyumluluğu** > **Genel Bakış**’ı seçin. **Cihaz uyumluluğu panosu** açılacaktır.

> [!IMPORTANT]
> Cihaz uyumluluk ilkelerini almak için, cihazların Intune'a kayıtlı olmaları gerekir.

## <a name="device-compliance-dashboard"></a>Cihaz uyumluluk panosu

**Cihaz uyumluluğu panosu**’nda farklı cihazların uyumluluğunu, koruma durumunu ve daha fazlasını izleyebilirsiniz. Aşağıdaki raporları görüntüleyebilirsiniz:

- Genel cihaz uyumluluk toplamı

- İlkeye göre cihaz uyumluluğu

- Ayara göre cihaz uyumluluğu

- Cihaz koruma durumu

- Tehdit aracısı durumu

![Cihaz uyumluluk panosunu gösteren resim](./media/idc-1.png)

Ayrıca, tek bir cihaz için geçerli olan uyumluluk ilkelerini ve ayarlarını, söz konusu ayarların cihazdaki son uyumluluk durumunu görüntüleyebilirsiniz.

### <a name="overall-device-compliance-aggregate-report"></a>Genel cihaz uyumluluk toplamı raporu

Intune’a kayıtlı tüm cihazlar için toplam uyumluluk durumunu gösteren bir halka grafiktir. Cihaz uyumluluk durumları iki farklı veritabanında (Intune ve Azure Active Directory) tutulur. Cihaz uyumluluk ilkesi durumları hakkında daha ayrıntılı bilgiler aşağıdadır:

- **Uyumlu**: Cihaz, yönetici tarafından hedeflenen bir veya daha fazla cihaz uyumluluk ilkesi ayarını başarıyla uyguladı.

- **Uyumlu değil:** Cihaz, yönetici tarafından hedeflenen bir veya daha fazla cihaz uyumluluk ilkesi ayarını uygulayamadı veya kullanıcı, yönetici tarafından hedeflenen ilkeler ile uyum sağlayamadı.

- **Yetkisiz kullanım süresi içinde:** Cihaza yönetici tarafından bir veya daha fazla cihaz uyumluluk ilkesi ayarı hedeflendi ancak kullanıcı ilkeleri henüz uygulamadı. Bu nedenle cihaz uyumlu değil, ancak yönetici tarafından tanımlanan yetkisiz kullanım süresi içinde bulunuyor.

  - Uyumlu olmayan cihazlara yönelik eylemler hakkında daha fazla bilgi edinin.

- **Cihaz eşitlenmedi:** Cihaz, aşağıdaki nedenlerden biri sonucunda cihaz uyumluluk ilkesi durumunu bildiremedi:

  - **Bilinmeyen**: Cihaz çevrimdışı veya Intune ya da Azure AD ile başka bir nedenle iletişim kuramadı.

  - **Hata**: Cihaz, Intune ve Azure AD ile iletişim kuramadı ve bunun nedenini açıklayan bir hata iletisi aldı.

> [!IMPORTANT]
> Intune’a kaydedilmiş olan ancak hiçbir cihaz uyumluluk ilkesi tarafından hedeflenmeyen cihazlar, **Uyumlu** demeti altında bu rapora dahil edilir.

#### <a name="drill-down-option"></a>Detaya gitme seçeneği

**Cihaz uyumluluğu panosu**’nda bir cihaz uyumluluğu kutucuğunu seçerek cihaz uyumluluk ilkeleri tarafından hedeflenen her bir cihaz için belirli bir **uyumluluk durumu**, **kullanıcının e-posta diğer adı**, **cihaz modeli** ve **konum** detayına gidebilirsiniz.

![Cihaz uyumluluk panosu ayrıntılarını gösteren resim](./media/idc-2.png)

Belirli bir kullanıcı hakkında daha fazla ayrıntı gerekiyorsa kullanıcının e-posta diğer adını yazarak Cihaz uyumluluğu grafik raporunu filtreleyebilirsiniz.

![Belirli bir kullanıcı için Cihaz uyumluluk panosunu gösteren resim](./media/idc-3.png)

Ayrıca, Cihaz uyumluluk grafiğinde farklı uyumluluk durumlarına tıklayarak kullanıcıya ait cihazların uyumluluk ilkesi durumları hakkında daha ayrıntılı bilgiler görebilirsiniz.

![Farklı durumlar için Cihaz uyumluluk panosunu gösteren resim](./media/idc-4.png)

#### <a name="filter"></a>Filtrele

**Filtre düğmesini** seçtiğinizde aşağıdaki seçenekleri içeren filtre geçici açılır öğesi görünür:

- Model

  - Serbest biçimli arama dizesi kabul eden metin kutusu

- Platform

  - Android

  - iOS

  - Mac OS

  - Windows

  - Windows Phone

- Durum

  - Uyumlu

  - Uyumlu Değil

  - Yetkisiz Kullanım süresi içinde

  - Bilinmiyor

  - Hata

**Güncelleştir düğmesini** seçtiğinizde geçici açılır öğe kapatılır ve sonuçlar, seçilen filtre ölçütleri kullanılarak güncelleştirilir.

##### <a name="device-details"></a>Cihaz ayrıntıları

Bir cihaz seçildiğinde, bu cihazın seçili olduğu **Cihazlar** bölümü açılır. Burada, söz konusu cihaz için uygulanan cihaz uyumluluk ilkesi ayarı hakkında daha ayrıntılı bilgiler sunulur.

Cihaz ilkesi ayarını seçtiğinizde, yönetici tarafından hedeflenen bu cihaz uyumluluk ayarının kaynağı olan cihaz uyumluluk ilkesinin adını görebilirsiniz.

### <a name="devices-without-compliance-policy"></a>Uyumluluk ilkesi olmayan cihazlar
Bu rapor, kendisine atanmış bir uyumluluk ilkesi olmayan cihazları belirler. Uyumluluk ilkesi olmayan cihazları “uyumsuz” olarak işaretleyen güvenlik ayarının sunulmasıyla birlikte bu cihazların belirlenebilmesi önem kazandı. Cihazlar belirlendikten sonra bunlara en az bir uyumluluk ilkesi atayabilirsiniz.

> [!NOTE]
> Yeni güvenlik ayarı, Intune portalında yapılandırılabilir. **Cihaz uyumluluğu**’nu seçin, **Kurulum** altında **Uyumluluk ilkesi ayarları**’na tıklayın. **Uyumluluk ilkesi atanmamış cihazları şu şekilde işaretle:** seçeneğini **Uyumlu** veya **Uyumsuz** olarak ayarlamak için iki durumlu düğmeyi kullanın. Bu [Intune hizmetinde güvenlik geliştirmesi](https://blogs.technet.microsoft.com/intunesupport/2018/02/09/updated-upcoming-security-enhancements-in-the-intune-service/) hakkında daha fazla bilgi edinin.

![Uyumluluk ilkesi olmayan Cihazlar raporunu gösteren görüntü](./media/idc-12.png)

**Uyumluluk ilkesi olmayan cihazlar** kutucuğu Cihaz uyumluluğu panosunda bulunur ve uyumluluk ilkesi olmayan tüm cihazları, cihazın kullanıcısını, uyumluluk durumunu ve modelini gösterir.

> [!NOTE]
> Herhangi bir tür uyumluluk ilkesi atanmış kullanıcılar, cihaz platformu ne olursa olsun raporda yer almaz. Örneğin Android cihazı olan bir kullanıcıya yanlışlıkla Windows uyumluluk ilkesi atamışsanız cihaz raporda görüntülenmez. Ancak Intune, bu Android cihazı uyumsuz olarak değerlendirir. Sorunların önüne geçmek adına her bir cihaz platformu için ilke oluşturup bunları tüm kullanıcılara dağıtmanızı öneririz.

### <a name="per-policy-device-compliance-report"></a>İlkeye göre cihaz uyumluluğu raporu

Bu raporda, uyumluluk ilkesine göre görünüm ve her bir uyumluluk durumundaki toplam cihaz sayısı sunulmaktadır. **İlke uyumluluğu** kutucuğuna **Cihaz uyumluluk panosu**’ndan erişilebilir. Bu kutucuk; daha önce yönetici tarafından oluşturulan tüm ilkeleri, ilkenin uygulandığı platformları, uyumlu olan ve olmayan cihazların sayısını gösterir.

![İlkeye göre cihaz uyumluluğu raporunu gösteren resim](./media/idc-8.png)

İlke uyumluluğu kutucuğuna ve sonra cihaz uyumluluk ilkelerinden birine tıkladığınızda, cihaz uyumluluk ilkesi tarafından hedeflenen her bir cihaz için **uyumluluk durumu**, **kullanıcının e-posta diğer adı**, **cihaz modeli** ve **konum** bilgilerini görebilirsiniz.

## <a name="setting-compliance-report"></a>Ayar uyumluluk raporu

Bu raporu kullanarak uyumluluk ayarına göre her bir uyumluluk durumundaki toplam cihaz sayısını görüntüleyebilirsiniz. **Ayarlar uyumluluğu** başlığına **Cihaz uyumluluk panosu**’ndan erişilebilir. Bu kutucuk; yönetici tarafından oluşturulan tüm cihaz uyumluluk ilkelerinin tüm cihaz uyumluluk ilkesi ayarlarını, ilke ayarlarının uygulandığı platformları, uyumlu olmayan cihazların sayısını gösterir.

![Ayara göre cihaz uyumluluğu raporunu gösteren resim](./media/idc-10.png)

Ayar uyumluluğu kutucuğuna ve sonra cihaz uyumluluk ilkesi ayarlarından birine tıkladığınızda, cihaz uyumluluk ilkesi ayarı tarafından hedeflenen her bir cihaz için **uyumluluk durumu**, **kullanıcının e-posta diğer adı**, **cihaz modeli** ve **konum** bilgilerini görebilirsiniz.

## <a name="view-status-of-device-policies"></a>Cihaz ilkelerinin durumunu görüntüleme

Platforma göre, ilkelerinizin farklı durumlarını denetleyebilirsiniz. Örneğin, bir macOS uyumluluk ilkeniz olsun. Bu ilke tarafından etkilenen cihazları görmek ve çakışma veya hata olup olmadığını bilmek istiyorsunuz.

Bu özellik cihaz durumu bildirimine eklenmiştir:

1. **Cihaz uyumluluğu** > **İlkeler**'i seçin. Platform da dahil olmak üzere ilkelerin listesi, ilkenin atanıp atanmadığı ve diğer ayrıntılar gösterilir.
2. Bir ilke seçin ve **Genel Bakış**'ı seçin. Bu görünümde, ilke ataması aşağıdaki durumları içerir:

  - Başarılı: İlke uygulandı
  - Hata: İlke uygulanamadı. Bu genellikle bir açıklamaya bağlantı veren bir hata kodu görüntüler. 
  - Çakışma: İki ayar aynı cihaza uygulanır ve Intune çakışmayı sıralayamaz. Yöneticinin gözden geçirmesi gerekir.
  - Bekleyen: Cihaz, ilkeyi almak için henüz Intune’a iade edilmemiş. 
  - Uygulanamaz: Cihaz ilkeyi alamaz. Örneğin ilke, iOS 11.1’e özel bir ayarı güncelleştiriyor ancak cihaz iOS 10 kullanıyor. 

3. Bu ilkeyi kullanan cihazlarla ilgili ayrıntıları görmek için, durumlardan birini seçin. Örneğin **Başarılı**'yı seçin. Sonraki pencerede, cihaz adı ve dağıtım durumu gibi belirli cihaz ayrıntıları listelenir.

## <a name="how-intune-resolves-policy-conflicts"></a>Intune ilke çakışmalarını nasıl çözümler?
Bir cihaza birden çok Intune ilkesi uygulandığında ilke çakışmaları olabilir. İlke ayarları çakışırsa, Intune tüm çakışmaları aşağıdaki kuralları kullanarak çözer:

- Çakışan ayarlar bir Intune yapılandırma ilkesine ve bir uyumluluk ilkesine aitse, uyumluluk ilkesindeki ayarlar yapılandırma ilkesindeki ayarlara göre önceliklidir. Bu, yapılandırma ilkesindeki ayarlar daha güvenli olsa bile gerçekleşir.

- Birden çok uyumluluk ilkesi dağıttıysanız, Intune bu ilkelerin en güvenli olanını kullanır.
