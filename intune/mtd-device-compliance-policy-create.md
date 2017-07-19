---
title: "Intune ile Mobile Threat Defense cihaz uyumluluk ilkesi oluşturma"
titleSuffix: Intune on Azure
description: "Intune'da Mobile Threat Defense cihaz uyumluluk ilkesi oluşturma"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d12254f-ffab-4792-b19c-ab37f5e02f35
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1354d3170f007af2a4bf7f5b2f233a186175c621
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2017
---
# <a name="create-mobile-threat-defense-mtd-device-compliance-policy-with-intune"></a>Intune ile Mobile Threat Defense (MTD) cihaz uyumluluk ilkesi oluşturma

Intune ile MTD, mobil cihazlarda tehditleri algılayıp risk değerlendirmesi yapmanıza yardımcı olur. Bir cihazın uyumlu olup olmadığını belirlemek üzere risk değerlendirmesi yapan bir Intune cihaz uyumluluk ilkesi kuralı oluşturabilirsiniz. Ardından cihaz uyumluluğuna göre hizmetlere erişimi engellemek için bir koşullu erişim ilkesi kullanabilirsiniz.

## <a name="before-you-begin"></a>Başlamadan önce

MTD kurulumunun parçası olarak, MTD iş ortağı konsolunda çeşitli tehditleri yüksek, orta ve düşük olarak sınıflandıran bir ilke oluşturdunuz. Şimdi Intune cihaz uyumluluk ilkesinde Mobile Threat Defense düzeyini ayarlamanız gerekiyor.

MTD ile cihaz uyumluluk ilkesinin önkoşulları:

-   Intune ile MTD tümleştirmesini ayarlama

-   Intune'da MTD bağlayıcısını etkinleştirme

## <a name="to-create-a-mtd-device-compliance-policy"></a>MTD cihaz uyumluluk ilkesi oluşturmak için

1.  [Azure Portal](https://portal.azure.com/)’a gidin ve Intune kimlik bilgilerinizle oturum açın.

2.  **Azure Panosunda**, soldaki menüden **Diğer hizmetler**’i seçtikten sonra, metin kutusu filtresine **Intune** yazın.

3.  **Intune**'u seçin, **Intune Panosu** açılır.

4. **Intune Panosu**'nda, **Cihaz uyumluluğu**'nu, ardından **Yönet** bölümü altından **İlkeler**'i seçin.

5.  **İlke oluştur**'u seçin, cihaz uyumluluğu için **Ad**, **Açıklama** girin, **Platform**'u seçin, sonra **Ayarlar** bölümünün altından **Yapılandır**'ı seçin.

6.  **Uyumluluk ilkesi** dikey penceresinden **Cihaz Sistem Durumu**'nu seçin.

7.  **Cihaz Sistem Durumu** dikey penceresinden **Cihazın Mobile Threat Defense Düzeyi'nde veya altında olmasını gerektir**'in altındaki açılan listeden Mobile Threat Düzeyini seçin.

    a.  **Güvenli**: En güvenli ayardır. Cihazda herhangi bir tehdit mevcut olamaz ve yine de şirket kaynaklarına erişebilir. Herhangi bir tehdit bulunduğunda, cihaz uyumsuz olarak değerlendirilir.

    b.  **Düşük**: Cihaz, yalnızca düşük düzeydeki tehditler varsa uyumludur. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.

    c.  **Orta**: Cihazda bulunan tehditler düşük veya orta düzeydeyse cihaz uyumludur. Yüksek düzeyde tehditler algılanırsa cihaz uyumlu değil olarak değerlendirilir.

    d.  **Yüksek**: Bu en az güvenli seçenektir. Bu tüm tehdit düzeylerine izin verir ve Skycure Mobile Threat Defense’i yalnızca raporlama amacıyla kullanır.

8.  **Tamam**'a iki kez tıklayın, sonra **Oluştur**'u seçin.

> [!IMPORTANT]
> Office 365 veya diğer hizmetler için koşullu erişim ilkeleri oluşturursanız cihazın uyumluluğu değerlendirilir ve cihazdaki tehdit çözümlenene kadar uyumlu olmayan cihazların kurumsal kaynaklara erişimi engellenir.

## <a name="to-assign-a-mtd-device-compliance-policy"></a>Bir MTD cihaz uyumluluk ilkesi atamak için

Kullanıcılara bir cihaz uyumluluk ilkesi atamak için daha önce yapılandırdığınız bir ilkeyi seçin. Mevcut ilkeler, **Cihaz Uyumluluk ilkeleri** dikey penceresinde bulunabilir.

1. Kullanıcılara atamak istediğiniz ilkeyi seçin ve ardından **Atamalar**’ı seçin. Bu işlem, **Azure Active Directory güvenlik gruplarını** seçebileceğiniz ve bunları ilkeye atayabileceğiniz dikey pencereyi açar.

2. Azure AD güvenlik gruplarının görüntülendiği dikey pencereyi açmak için **Grupları seçin** öğesini seçin.  **Seç** öğesi seçildiğinde, ilke kullanıcılara dağıtılır.

    > [!NOTE] 
    > İlkeyi kullanıcılara uyguladınız. İlkenin hedeflediği kullanıcılar tarafından kullanılan cihazlar, uyumluluk için denetlenecek.