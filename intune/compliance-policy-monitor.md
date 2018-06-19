---
title: Microsoft Intune cihaz uyumluluk ilkelerini izleme
titlesuffix: ''
description: Genel cihaz uyumluluğunu izlemek, raporları görüntülemek ve ilke başına ve ayar başına cihaz uyumluluğunu izlemek için cihaz uyumluluk panosunu kullanın.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 2/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c4c3c3a2d73c6390ef5761f1bd0b12fe55855c6e
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31831880"
---
# <a name="monitor-intune-device-compliance-policies"></a>Intune Cihaz uyumluluk ilkelerini izleme

Uyumluluk raporları, yöneticilerin kuruluşlarındaki cihazların uyumluluk duruşunu analiz etmesine ve kuruluşlarındaki kullanıcıların karşılaştığı uyumluluk sorunlarını hızla gidermelerine yardımcı olur. Cihazların genel uyumluluk durumunu, tek bir ayar için uyumluluk durumunu ve tek bir ilke için uyumluluk durumunu görüntüleyebilir ve tek tek cihazların ayrıntılarına inerek söz konusu cihazı etkileyen belirli ayar ve ilkelere bakabilirsiniz.

> [!NOTE]
> Mart ayında geri bildirimlerinize bağlı olarak Intune hizmetinde bazı güvenlik geliştirmeleri sunacağız. Uyumluluk ilkelerinizin yapılandırmasına bağlı olarak son kullanıcılarınızın e-posta erişimini kaybetmemeleri için eylemler gerçekleştirmeniz gerekebilir. Ayrıntılar için bkz. [Yaklaşan güvenlik geliştirmeleri](https://blogs.technet.microsoft.com/intunesupport/2018/02/09/updated-upcoming-security-enhancements-in-the-intune-service/).

## <a name="before-you-begin"></a>Başlamadan önce

Azure portalında **Intune Cihaz uyumluluk panosu**’nu bulmak için şu adımları izleyin:

1.  [Azure portalı](https://portal.azure.com)’na gidin ve Intune kimlik bilgilerinizle oturum açın.

2.  Soldaki menüden **Tüm hizmetler**’i seçtikten sonra metin kutusu filtresine **Intune** yazın.

3.  **Intune** &gt; **Cihaz uyumluluğu** &gt; **Genel bakış**’ı seçin. **Cihaz uyumluluk panosu** açılır.

> [!IMPORTANT]
> Cihaz uyumluluk ilkelerini almak için, cihazların Intune'a kayıtlı olmaları gerekir.

## <a name="device-compliance-dashboard"></a>Cihaz uyumluluk panosu

**Cihaz uyumluluk panosu**’nda Cihaz uyumluluk ilkesi durumlarını izleyebilirsiniz. Farklı kutucuklar içerisinde yer alan farklı raporlar, kuruluşunuzdaki cihazların uyumluluk duruşlarını gösterir. Aşağıdaki raporları görüntüleyebilirsiniz:

-   Genel cihaz uyumluluk toplamı

-   İlkeye göre cihaz uyumluluğu

-   Ayara göre cihaz uyumluluğu

![Cihaz uyumluluk panosunu gösteren resim](./media/idc-1.png)

Ayrıca, tek bir cihaz için geçerli olan uyumluluk ilkelerini ve ayarlarını, söz konusu ayarların cihazdaki son uyumluluk durumunu görüntüleyebilirsiniz.

### <a name="overall-device-compliance-aggregate-report"></a>Genel cihaz uyumluluk toplamı raporu

Intune’a kayıtlı tüm cihazlar için toplam uyumluluk durumunu gösteren bir halka grafiktir. Cihaz uyumluluk durumları iki farklı veritabanında (Intune ve Azure Active Directory) tutulur. Cihaz uyumluluk ilkesi durumları hakkında daha ayrıntılı bilgiler aşağıdadır:

-   **Uyumlu**: Cihaz, yönetici tarafından hedeflenen bir veya daha fazla cihaz uyumluluk ilkesi ayarını başarıyla uyguladı.

-   **Uyumlu değil:** Cihaz, yönetici tarafından hedeflenen bir veya daha fazla cihaz uyumluluk ilkesi ayarını uygulayamadı veya kullanıcı, yönetici tarafından hedeflenen ilkeler ile uyum sağlayamadı.

-   **Yetkisiz kullanım süresi içinde:** Cihaza yönetici tarafından bir veya daha fazla cihaz uyumluluk ilkesi ayarı hedeflendi ancak kullanıcı ilkeleri henüz uygulamadı. Bu nedenle cihaz uyumlu değil, ancak yönetici tarafından tanımlanan yetkisiz kullanım süresi içinde bulunuyor.

    -   Uyumlu olmayan cihazlara yönelik eylemler hakkında daha fazla bilgi edinin.

-   **Cihaz eşitlenmedi:** Cihaz, aşağıdaki nedenlerden biri sonucunda cihaz uyumluluk ilkesi durumunu bildiremedi:

    -   **Bilinmeyen**: Cihaz çevrimdışı veya Intune ya da Azure AD ile başka bir nedenle iletişim kuramadı.

    -   **Hata**: Cihaz, Intune ve Azure AD ile iletişim kuramadı ve bunun nedenini açıklayan bir hata iletisi aldı.

> [!IMPORTANT]
> Intune’a kaydedilmiş olan ancak hiçbir cihaz uyumluluk ilkesi tarafından hedeflenmeyen cihazlar, **Uyumlu** demeti altında bu rapora dahil edilir.

#### <a name="drill-down-option"></a>Detaya gitme seçeneği

**Cihaz uyumluluk panosu**’nda Cihaz uyumluluğu kutucuğuna tıklarsanız cihaz uyumluluk ilkeleri tarafından hedeflenen her bir cihaz için belirli bir **uyumluluk durumu**, **kullanıcının e-posta diğer adı**, **cihaz modeli** ve **konum** detayına gidebilirsiniz.

![Cihaz uyumluluk panosu ayrıntılarını gösteren resim](./media/idc-2.png)

Belirli bir kullanıcı hakkında daha fazla ayrıntı gerekiyorsa kullanıcının e-posta diğer adını yazarak Cihaz uyumluluğu grafik raporunu filtreleyebilirsiniz.

![Belirli bir kullanıcı için Cihaz uyumluluk panosunu gösteren resim](./media/idc-3.png)

Ayrıca, Cihaz uyumluluk grafiğinde farklı uyumluluk durumlarına tıklayarak kullanıcıya ait cihazların uyumluluk ilkesi durumları hakkında daha ayrıntılı bilgiler görebilirsiniz.

![Farklı durumlar için Cihaz uyumluluk panosunu gösteren resim](./media/idc-4.png)

#### <a name="filter"></a>Filtrele

**Filtre düğmesine** tıklarsanız aşağıdaki seçenekleri içeren filtre geçici açılır öğesi görünür:

-   Model

    -   Serbest biçimli arama dizesi kabul eden metin kutusu
<br></br>
-   Platform

    -   Android

    -   iOS

    -   Mac OS

    -   Windows

    -   Windows Phone

-   Durum

    -   Uyumlu

    -   Uyumlu Değil

    -   Yetkisiz Kullanım süresi içinde

    -   Bilinmiyor

    -   Hata

**Güncelleştir düğmesine** tıkladığınızda geçici açılır öğe kapatılır ve sonuçlar, seçilen filtre ölçütlerine göre güncelleştirilir.

##### <a name="device-details"></a>Cihaz ayrıntıları

Bir cihaza tıklandığında **Cihazlar Bölmesi** cihaz seçilmiş olarak açılır; burada bu cihaza uygulanan cihaz uyumluluğu ilkesi ayarı hakkında daha fazla ayrıntı sağlanır.

Cihaz ilkesi ayarının kendisinin üzerine tıkladığınızda yönetici tarafından hedeflenen bu cihaz uyumluluk ayarının kaynağı olan cihaz uyumluluk ilkesinin adını görebilirsiniz.

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
