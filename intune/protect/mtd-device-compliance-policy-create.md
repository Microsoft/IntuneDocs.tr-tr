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
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74409692"
---
# <a name="create-mobile-threat-defense-mtd-device-compliance-policy-with-intune"></a>Intune ile Mobile Threat Defense (MTD) cihaz uyumluluk ilkesi oluşturma

Intune ile MTD, mobil cihazlarda tehditleri algılayıp risk değerlendirmesi yapmanıza yardımcı olur. Bir cihazın uyumlu olup olmadığını belirlemek üzere risk değerlendirmesi yapan bir Intune cihaz uyumluluk ilkesi kuralı oluşturabilirsiniz. Daha sonra, cihaz uyumluluğuna göre hizmetlere erişimi engellemek için bir [koşullu erişim ilkesi](create-conditional-access-intune.md) kullanabilirsiniz.

> [!NOTE]
> Bu bilgiler, tüm Mobile Threat Defense iş ortakları için geçerlidir.

## <a name="before-you-begin"></a>Başlamadan önce

MTD kurulumunun parçası olarak, MTD iş ortağı konsolunda çeşitli tehditleri yüksek, orta ve düşük olarak sınıflandıran bir ilke oluşturdunuz. Şimdi Intune cihaz uyumluluk ilkesinde Mobile Threat Defense düzeyini ayarlamanız gerekiyor.

MTD ile cihaz uyumluluk ilkesinin önkoşulları:

- Intune ile MTD tümleştirmesini ayarlama

## <a name="to-create-an-mtd-device-compliance-policy"></a>MTD cihaz uyumluluk ilkesi oluşturmak için

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2. **Ilke oluştur** > **cihaz** > **uyumluluk ilkeleri** ' ni seçin.

3. Bir cihaz uyumluluk ilkesi **adı**belirtin, **Açıklama**, **platformu**seçin ve **Ayarlar** bölümü altında **Yapılandır** ' ı seçin.

4. **Uyumluluk ilkesi** bölmesinden **Cihaz Sistem Durumu**’nu seçin.

5. **Cihaz durumu** bölmesinde, cihazın **cihaz tehdit düzeyinde veya altında olmasını gerektir ' ın**açılan listesinden mobil tehdit düzeyini seçin.

   - **Güvenli**: En güvenli düzeydir. Cihazda herhangi bir tehdit mevcut olamaz ve yine de şirket kaynaklarına erişebilir. Herhangi bir tehdit bulunursa cihaz uyumsuz olarak değerlendirilir.

   - **Düşük**: Cihaz, yalnızca düşük düzeydeki tehditler varsa uyumludur. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.

   - **Orta**: Cihazda bulunan tehditler düşük veya orta düzeydeyse cihaz uyumludur. Yüksek düzeyde tehditler algılanırsa cihaz uyumsuz olarak değerlendirilir.

   - **Yüksek**: Bu, en az güvenli düzeydir. Bu, tüm tehdit düzeylerine izin verir ve Mobile Threat Defense’i yalnızca raporlama amacıyla kullanır. Cihazlar, bu ayar ile MTD uygulamasının etkin olmasını gerektirir.

6. **Tamam** ' ı iki kez seçin ve ilkeyi oluşturmak için **Oluştur** ' u seçin.

> [!IMPORTANT]
> Office 365 veya diğer hizmetler için koşullu erişim ilkeleri oluşturursanız, cihaz uyumluluk değerlendirmesi değerlendirilir ve uyumlu olmayan cihazların, tehdit cihazda çözümlenene kadar kurumsal kaynaklara erişmesi engellenir.

## <a name="to-assign-an-mtd-device-compliance-policy"></a>MTD cihaz uyumluluk ilkesini atamak için

Kullanıcılara bir cihaz uyumluluk ilkesi atamak için:

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2. **Cihaz** > **uyumluluk ilkeleri**' ni seçin.

3. Kullanıcılara atamak istediğiniz ilkeyi seçin ve ardından **atamalar**' ı seçin. Bu ilkeyi almak üzere grupları *dahil* etmek ve *dışlamak* için kullanılabilir seçenekleri kullanın.  

4. Atamayı gerçekleştirmek için Kaydet ' i seçin. Atamayı kaydettiğinizde, ilke seçili kullanıcılarınıza dağıtılır ve cihazları uyumluluk için değerlendirilir.

## <a name="next-steps"></a>Sonraki adımlar

[MTD'yi Intune ile etkinleştirme](mtd-connector-enable.md)
