---
title: Microsoft Intune MTD cihaz uyumluluk ilkesi oluşturma | Microsoft Intune
description: Bir mobil cihazın şirket kaynaklarına erişip erişemeyeceğini belirlemek için MTD iş ortağı tehdit düzeylerinizi kullanan bir Intune cihaz uyumluluğu ilkesi oluşturun.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5d12254f-ffab-4792-b19c-ab37f5e02f35
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8a7ef9462d5d46a88c9590bb1f643e57b5bd76af
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55844539"
---
# <a name="create-mobile-threat-defense-mtd-device-compliance-policy-with-intune"></a>Intune ile Mobile Threat Defense (MTD) cihaz uyumluluk ilkesi oluşturma

> [!NOTE] 
> Bu bilgiler, tüm Mobile Threat Defense iş ortakları için geçerlidir.

Intune ile MTD, mobil cihazlarda tehditleri algılayıp risk değerlendirmesi yapmanıza yardımcı olur. Bir cihazın uyumlu olup olmadığını belirlemek üzere risk değerlendirmesi yapan bir Intune cihaz uyumluluk ilkesi kuralı oluşturabilirsiniz. Daha sonra kullanabileceğiniz bir [koşullu erişim ilkesi](create-conditional-access-intune.md) cihaz uyumluluğuna göre hizmetlere erişimi engellemek için.

## <a name="before-you-begin"></a>Başlamadan önce

MTD kurulumunun parçası olarak, MTD iş ortağı konsolunda çeşitli tehditleri yüksek, orta ve düşük olarak sınıflandıran bir ilke oluşturdunuz. Şimdi Intune cihaz uyumluluk ilkesinde Mobile Threat Defense düzeyini ayarlamanız gerekiyor.

MTD ile cihaz uyumluluk ilkesinin önkoşulları:

-   Intune ile MTD tümleştirmesini ayarlama

## <a name="to-create-an-mtd-device-compliance-policy"></a>MTD cihaz uyumluluk ilkesi oluşturmak için

1.  [Azure portalı](https://portal.azure.com/)’na gidin ve Intune kimlik bilgilerinizle oturum açın.

2.  **Azure Panosu**'nda, soldaki menüden **Tüm hizmetler**’i seçtikten sonra, metin kutusu filtresine **Intune** yazın.

3.  **Intune**'u seçin, **Intune Panosu** açılır.

4. **Intune Panosu**'nda, **Cihaz uyumluluğu**'nu, ardından **Yönet** bölümü altından **İlkeler**'i seçin.

5.  **İlke oluştur**'u seçin, cihaz uyumluluğu için **Ad**, **Açıklama** girin, **Platform**'u seçin, sonra **Ayarlar** bölümünün altından **Yapılandır**'ı seçin.

6.  **Uyumluluk ilkesi** bölmesinden **Cihaz Sistem Durumu**’nu seçin.

7.  **Cihaz Sistem Durumu** bölmesinden **Cihazın Cihaz Tehdit Düzeyinde veya altında olmasını gerektir**'in altındaki açılan listeden Mobil Tehdit Düzeyini seçin.

    a.  **Güvenli**: Bu en güvenli düzeydir. Cihazda herhangi bir tehdit mevcut olamaz ve yine de şirket kaynaklarına erişebilir. Herhangi bir tehdit bulunursa cihaz uyumsuz olarak değerlendirilir.

    b.  **Düşük**: Cihaz, yalnızca düşük düzeydeki tehditler varsa uyumludur. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.

    c.  **Orta**: Cihazda bulunan tehditler düşük veya Orta düzeydeyse cihaz uyumludur. Yüksek düzeyde tehditler algılanırsa cihaz uyumsuz olarak değerlendirilir.

    d.  **Yüksek**: Bu en az güvenli düzeydir. Bu, tüm tehdit düzeylerine izin verir ve Mobile Threat Defense’i yalnızca raporlama amacıyla kullanır. Cihazlar, bu ayar ile MTD uygulamasının etkin olmasını gerektirir.

8.  **Tamam**'a iki kez tıklayın, sonra **Oluştur**'u seçin.

> [!IMPORTANT]
> Office 365 veya diğer hizmetler için koşullu erişim ilkeleri oluşturursanız cihazın uyumluluğu değerlendirilir ve cihazdaki tehdit çözümlenene kadar uyumlu olmayan cihazların kurumsal kaynaklara erişimi engellenir.

## <a name="to-assign-an-mtd-device-compliance-policy"></a>MTD cihaz uyumluluk ilkesini atamak için

Kullanıcılara bir cihaz uyumluluk ilkesi atamak için daha önce yapılandırdığınız bir ilkeyi seçin. Mevcut ilkeler, **Cihaz uyumluluk ilkeleri** bölmesinde bulunabilir.

1. Kullanıcılara atamak istediğiniz ilkeyi seçin ve ardından **Atamalar**’ı seçin. Bu eylem, **Azure Active Directory güvenlik gruplarını** seçebileceğiniz ve bunları ilkeye atayabileceğiniz bölmeyi açar.

2. Azure AD güvenlik gruplarının görüntülendiği sayfayı açmak için **Dahil edilecek grupları seçin** öğesini seçin.  **Seç** öğesi seçildiğinde, ilke kullanıcılara dağıtılır.

    > [!NOTE] 
    > İlkeyi kullanıcılara uyguladınız. İlkenin hedeflediği kullanıcılar tarafından kullanılan cihazlar, uyumluluk için denetlenir.

## <a name="next-steps"></a>Sonraki adımlar

- [MTD'yi Intune ile etkinleştirme](mtd-connector-enable.md)
