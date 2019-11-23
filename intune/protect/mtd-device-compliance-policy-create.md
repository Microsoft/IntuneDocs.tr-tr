---
title: Microsoft Intune ile MTD cihaz uyumluluk ilkesi oluşturma
titleSuffix: Microsoft Intune
description: Bir mobil cihazın şirket kaynaklarına erişip erişemeyeceğini belirlemek için MTD iş ortağı tehdit düzeylerinizi kullanan bir Intune cihaz uyumluluğu ilkesi oluşturun.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/20/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5d12254f-ffab-4792-b19c-ab37f5e02f35
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 504c77fb56918cf97312e70f50b38356f9f7efef
ms.sourcegitcommit: a7b479c84b3af5b85528db676594bdb3a1ff6ec6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74409692"
---
# <a name="create-mobile-threat-defense-mtd-device-compliance-policy-with-intune"></a>Intune ile Mobile Threat Defense (MTD) cihaz uyumluluk ilkesi oluşturma

Intune ile MTD, mobil cihazlarda tehditleri algılayıp risk değerlendirmesi yapmanıza yardımcı olur. Bir cihazın uyumlu olup olmadığını belirlemek üzere risk değerlendirmesi yapan bir Intune cihaz uyumluluk ilkesi kuralı oluşturabilirsiniz. You can then use a [Conditional Access policy](create-conditional-access-intune.md) to block access to services based on device compliance.

> [!NOTE]
> Bu bilgiler, tüm Mobile Threat Defense iş ortakları için geçerlidir.

## <a name="before-you-begin"></a>Başlamadan önce

MTD kurulumunun parçası olarak, MTD iş ortağı konsolunda çeşitli tehditleri yüksek, orta ve düşük olarak sınıflandıran bir ilke oluşturdunuz. Şimdi Intune cihaz uyumluluk ilkesinde Mobile Threat Defense düzeyini ayarlamanız gerekiyor.

MTD ile cihaz uyumluluk ilkesinin önkoşulları:

- Intune ile MTD tümleştirmesini ayarlama

## <a name="to-create-an-mtd-device-compliance-policy"></a>MTD cihaz uyumluluk ilkesi oluşturmak için

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Select **Device** > **Compliance policies** > **Create policy**.

3. Specify a device compliance policy **Name**, **Description**, select the **Platform**, then select **Configure** under the **Settings** section.

4. **Uyumluluk ilkesi** bölmesinden **Cihaz Sistem Durumu**’nu seçin.

5. On the **Device Health** pane, choose the Mobile Threat Level from the drop-down list for **Require the device to be at or under the Device Threat Level**.

   - **Güvenli**: En güvenli düzeydir. Cihazda herhangi bir tehdit mevcut olamaz ve yine de şirket kaynaklarına erişebilir. Herhangi bir tehdit bulunursa cihaz uyumsuz olarak değerlendirilir.

   - **Düşük**: Cihaz, yalnızca düşük düzeydeki tehditler varsa uyumludur. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.

   - **Orta**: Cihazda bulunan tehditler düşük veya orta düzeydeyse cihaz uyumludur. Yüksek düzeyde tehditler algılanırsa cihaz uyumsuz olarak değerlendirilir.

   - **Yüksek**: Bu, en az güvenli düzeydir. Bu, tüm tehdit düzeylerine izin verir ve Mobile Threat Defense’i yalnızca raporlama amacıyla kullanır. Cihazlar, bu ayar ile MTD uygulamasının etkin olmasını gerektirir.

6. Select **OK** twice, then select **Create** to create the policy.

> [!IMPORTANT]
> If you create Conditional Access policies for Office 365 or other services, the device compliance evaluation is assessed and noncompliant devices are blocked from accessing corporate resources until the threat is resolved in the device.

## <a name="to-assign-an-mtd-device-compliance-policy"></a>MTD cihaz uyumluluk ilkesini atamak için

To assign a device compliance policy to users:

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Select **Device** > **Compliance policies**.

3. Select the policy you want to assign to users, and then select **Assignments**. Use the available options to *Include* and *Exclude* groups to receive this policy.  

4. Select Save to complete the assignment. When you save the assignment, the policy deploys to your selected users and their devices are evaluated for compliance.

## <a name="next-steps"></a>Sonraki adımlar

[MTD'yi Intune ile etkinleştirme](mtd-connector-enable.md)
