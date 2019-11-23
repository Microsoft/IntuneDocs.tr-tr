---
title: Microsoft Intune - Azure’da cihaz uyumluluk ilkelerini izleme | Microsoft Docs
description: Genel cihaz uyumluluğunu izlemek, raporları görüntülemek ve ilke başına ve ayar başına cihaz uyumluluğunu izlemek için cihaz uyumluluk panosunu kullanın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 1/14/2019
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
ms.openlocfilehash: 844e93f3a063ae43342d2967cbd544f3ec425c21
ms.sourcegitcommit: a7b479c84b3af5b85528db676594bdb3a1ff6ec6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74410155"
---
# <a name="monitor-intune-device-compliance-policies"></a>Intune Cihaz uyumluluk ilkelerini izleme

Uyumluluk raporları, cihaz uyumluluğunu gözden geçirmenize ve kuruluşunuzdaki uyumlulukla ilgili sorunları gidermenize yardımcı olur. Bu raporları kullanarak şu konulardaki bilgileri görüntüleyebilirsiniz:

- Cihazların genel uyumluluk durumu
- Ayrı bir ayarın uyumluluk durumu
- Ayrı bir ilkenin uyumluluk durumu
- Cihazları etkileyen belirli ayar ve ilkeleri görüntülemek için bireysel cihazların detayına gitme

## <a name="open-the-compliance-dashboard"></a>Cihaz uyumluluğu panosunu açma

**Intune cihaz uyumluluğu panosunu** açın:

1. Sign in to [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

2. **Cihaz uyumluluğu** > **Genel Bakış**’ı seçin. **Cihaz uyumluluğu panosu** açılacaktır.

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

### <a name="device-compliance-status"></a>Device compliance status

The **Device compliance status** chart shows the compliance states for all Intune enrolled devices. Cihaz uyumluluk durumları iki farklı veritabanında tutulur: Intune ve Azure Active Directory.

> [!IMPORTANT]
> Intune, cihazdaki tüm uyumluluk değerlendirmeleri için cihaz iade zamanlamasını kullanır. [Cihaz iade zamanlaması hakkında daha fazla bilgi edinin](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

Farklı cihaz uyumluluk ilkesi durumlarının açıklamaları:

- **Uyumlu**: Cihaz, bir veya daha fazla cihaz uyumluluk ilkesi ayarını başarıyla uyguladı.

- **Yetkisiz kullanım süresinde:** Cihaz, bir veya daha fazla cihaz uyumluluk ilkesi ayarı tarafından hedefleniyor. Ancak kullanıcı henüz bu ilkeleri uygulamadı. Bu, cihazın uyumsuz ancak yönetici tarafından belirlenen yetkisiz kullanım süresinde olduğunu gösterir.

  - [Uyumlu olmayan cihazlara yönelik eylemler](actions-for-noncompliance.md) hakkında daha fazla bilgi edinin.

- **Değerlendirilmedi**: Yeni kaydedilen cihazlar için ilk durum. Other possible reasons for this state include:

  - Devices that aren't assigned a compliance policy and don't have a trigger to check for compliance
  - Devices that haven't checked in since the compliance policy was last updated
  - Devices not associated to a specific user, such as:
    - iOS devices purchased through Apple's Device Enrollment Program (DEP) that don't have user affinity
    - Android kiosk or Android Enterprise dedicated devices
  - Devices enrolled with a device enrollment manager (DEM) account

- **Uyumsuz**: Cihaz, bir veya daha fazla cihaz uyumluluk ilkesi ayarını uygulayamadı. Veya kullanıcı ilkelere uyum sağlamadı.

- **Cihaz eşitlenmedi:** Cihaz, aşağıdaki nedenlerden biri sonucunda cihaz uyumluluk ilkesi durumunu bildiremedi:

  - **Bilinmeyen**: Cihaz çevrimdışı veya Intune ya da Azure AD ile başka bir nedenle iletişim kuramadı.

  - **Hata**: Cihaz, Intune ve Azure AD ile iletişim kuramadı ve bunun nedenini açıklayan bir hata iletisi aldı.

> [!IMPORTANT]
> Intune’a kaydedilmiş olan ancak hiçbir cihaz uyumluluk ilkesi tarafından hedeflenmeyen cihazlar, **Uyumlu** demeti altında bu rapora dahil edilir.

#### <a name="drill-down-for-more-details"></a>Daha fazla bilgi için detaya gidin

**Cihaz uyumluluk durumu** grafiğinde bir durum seçin. Örneğin **Uyumsuz** durumunu seçin:

![Uyumsuz durumunu seçme](./media/compliance-policy-monitor/select-not-compliant-status.png)

That action opens the **Device compliance** window, and displays devices in a **Device status** chart. The chart shows you more details on the devices in that state, including operating system platform, last check-in date, and more. 

![Pano görüntüsü, bu durumdaki cihazlar hakkında daha fazla ayrıntı sağlar](./media/compliance-policy-monitor/drill-down-details.png)

Belirli bir kullanıcıya ait tüm cihazları görmek istiyorsanız kullanıcının e-postasını yazarak grafik raporunu filtreleyebilirsiniz.

#### <a name="filter-and-columns"></a>Filtre ve sütunlar

![Grafikteki sonuçları değiştirmek için Filtre ve Sütun’u seçme](./media/compliance-policy-monitor/filter-columns.png)

When you select the **Filter** button, the filter fly-out opens with more options, including the **Compliance** state, **Jailbroken** devices, and more. Sonuçları güncelleştirmek için filtreyi **Uygulayın**.

Grafik çıkışında sütun eklemek ve kaldırmak için **Sütunlar** özelliğini kullanın. Örneğin **Kullanıcı asıl adı**, cihazda kayıtlı e-posta adreslerini gösterebilir. Sonuçları güncelleştirmek için sütunları **Uygulayın**.

#### <a name="device-details"></a>Cihaz ayrıntıları

In the **Device details** chart, select a specific device, and then select **Device compliance**:

![Belirli bir cihazı ve daha sonra Cihaz Uyumluluğu’nu seçerek uygulanan uyumluluk ilkelerini görüntüleme](./media/compliance-policy-monitor/see-policies-applied-specific-device.png)

Intune displays more details on the device compliance policy settings applied on that device. Belirli bir ilkeyi seçtiğinizde ilkedeki tüm ayarlar gösterilir.

### <a name="devices-without-compliance"></a>Devices without compliance

On the *Compliance status* page, next to the *Policy compliance* chart, you can select the **Devices without compliance policy** tile to view information about devices that don't have any compliance policies assigned:

![Uyumluluk ilkesi olmayan cihazları görüntüleme](./media/compliance-policy-monitor/devices-without-policies.png)

Kutucuğu seçtiğinizde uyumluluk ilkeleri olmayan cihazlar görüntülenir. Ayrıca cihazın kullanıcısı, ilke dağıtım durumu ve modeli de gösterilir.

#### <a name="what-you-need-to-know"></a>Bilmeniz gerekenler

- **Uyumluluk ilkesi atanmamış cihazları şu şekilde işaretle** güvenlik ayarı için uyumluluk ilkesi olmayan cihazları belirlemek önemlidir. Cihazlar belirlendikten sonra bunlara en az bir uyumluluk ilkesi atayabilirsiniz.

  Bu güvenlik ayarı, Intune portalında yapılandırılabilir. To to **Devices** > **Compliance policies** > **Compliance policy settings**. Daha sonra **Uyumluluk ilkesi atanmamış cihazları şu şekilde işaretle** seçeneğini **Uyumlu** veya **Uyumsuz** olarak ayarlayın. 

  Bu [Intune hizmetinde güvenlik geliştirmesi](https://blogs.technet.microsoft.com/intunesupport/2018/02/09/updated-upcoming-security-enhancements-in-the-intune-service/) hakkında daha fazla bilgi edinin.

- Herhangi bir tür uyumluluk ilkesi atanmış kullanıcılar, cihaz platformu ne olursa olsun raporda yer almaz. Örneğin Android cihazı olan bir kullanıcıya Windows uyumluluk ilkesi atamışsanız cihaz raporda görüntülenmez. Ancak Intune, bu Android cihazı uyumsuz olarak değerlendirir. Sorunların önüne geçmek adına her bir cihaz platformu için ilke oluşturup bunları tüm kullanıcılara dağıtmanızı öneririz.

### <a name="per-policy-device-compliance"></a>İlkeye göre cihaz uyumluluğu

The **Policy compliance** chart shows you the policies, and how many devices are compliant and noncompliant. 

![İlke listesi ile ilke için uyumlu ve uyumsuz cihaz sayısını görme](./media/compliance-policy-monitor/idc-8.png)

### <a name="setting-compliance"></a>Ayar uyumluluğu

The **Setting compliance** chart shows you all device compliance policy settings from all compliance policies, the platforms the policy settings are applied, and the number of noncompliant devices.

![Farklı ilkelerdeki ayar listesini görme](./media/compliance-policy-monitor/idc-10.png)

> [!NOTE]
> A policy can be assigned to a device, and a user on that same device. In some scenarios, a device may sync before the user signs in, such as when the device reboots. Compliance may evaluate this user, and show the device as non compliant. This behavior may also show the System Account as a non-compliant user.
>
> This is a known issue with multi-user Windows 10 devices. Any changes or updates on this behavior are announced in [in development](../fundamentals/in-development.md) and/or [what's new](../fundamentals/whats-new.md).

## <a name="view-compliance-reports"></a>View compliance reports

In addition to using the charts on *Compliance status*, you can view compliance reports from the *Monitor* page of the Admin Center.

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Select **Devices** > **Monitor**, and then from below **Compliance** select the report you want to view. Some of the available compliance reports include:

   - Cihaz uyumluluğu
   - Noncompliant devices
   - Uyumluluk ilkesi olmayan cihazlar
   - Ayar uyumluluğu
   - Policy compliance
   - Windows health attestation report
   - Tehdit aracısı durumu

For more information about reports, see [Intune reports](../fundamentals/reports.md)

## <a name="view-status-of-device-policies"></a>Cihaz ilkelerinin durumunu görüntüleme

Platforma göre, ilkelerinizin farklı durumlarını denetleyebilirsiniz. Örneğin, bir macOS uyumluluk ilkeniz olsun. Bu ilke tarafından etkilenen cihazları görmek ve çakışma veya hata olup olmadığını bilmek istiyorsunuz.

Bu özellik cihaz durumu bildirimine eklenmiştir:

1. Select **Devices** > **Compliance policies** > **Policies**. Platform da dahil olmak üzere ilkelerin listesi, ilkenin atanıp atanmadığı ve diğer ayrıntılar gösterilir.
2. Bir ilke seçin ve **Genel Bakış**'ı seçin. Bu görünümde, ilke ataması aşağıdaki durumları içerir:

    - **Succeeded**: Policy is applied
    - **Error**: The policy failed to apply. Bu ileti, genellikle bir açıklamaya bağlantı veren bir hata kodu görüntüler. 
    - **Conflict**: Two settings are applied to the same device, and Intune can't sort out the conflict. Yöneticinin gözden geçirmesi gerekir.
    - **Pending**: The device hasn’t checked in with Intune to receive the policy yet. 
    - **Not applicable**: The device can't receive the policy. Örneğin ilke, iOS 11.1’e özel bir ayarı güncelleştiriyor ancak cihaz iOS 10 kullanıyor. 

3. Bu ilkeyi kullanan cihazlarla ilgili ayrıntıları görmek için, durumlardan birini seçin. Örneğin **Başarılı**'yı seçin. Sonraki pencerede, cihaz adı ve dağıtım durumu gibi belirli cihaz ayrıntıları listelenir.

## <a name="how-intune-resolves-policy-conflicts"></a>Intune ilke çakışmalarını nasıl çözümler?
Bir cihaza birden çok Intune ilkesi uygulandığında ilke çakışmaları olabilir. İlke ayarları çakışırsa, Intune tüm çakışmaları aşağıdaki kuralları kullanarak çözer:

- Çakışan ayarlar bir Intune yapılandırma ilkesine ve bir uyumluluk ilkesine aitse, uyumluluk ilkesindeki ayarlar yapılandırma ilkesindeki ayarlara göre önceliklidir. Bu, yapılandırma ilkesindeki ayarlar daha güvenli olsa bile gerçekleşir.

- Birden çok uyumluluk ilkesi dağıttıysanız, Intune bu ilkelerin en güvenli olanını kullanır.
