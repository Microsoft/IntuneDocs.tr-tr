---
title: Intune ile Mobile Threat Defense (MTD) uygulama koruma ilkesi oluşturma
titleSuffix: Microsoft Intune
description: Microsoft Intune ile Mobile Threat Defense (MTD) uygulama koruma ilkesi oluşturun.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 15d986bc5017a44571c6194f9c6b53167b671349
ms.sourcegitcommit: 06a1fe83fd95c9773c011690e8520733e1c031e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2019
ms.locfileid: "72795312"
---
# <a name="create-mobile-threat-defense-app-protection-policy-with-intune"></a>Intune ile Mobile Threat Defense uygulama koruma ilkesi oluşturma

> [!NOTE] 
> Bu makale, uygulama koruma ilkelerini destekleyen tüm Mobile Threat Defense (MTD) iş ortakları için geçerlidir: daha Iyi mobil (Android), Zmıium (iOS), Lookout for Work (Android/iOS).

Intune ile MTD, mobil cihazlarda tehditleri algılayıp risk değerlendirmesi yapmanıza yardımcı olur. Cihazın şirket verilerine erişim izni verilip verilmediğini belirleme riskini değerlendirir eden bir Intune uygulama koruma ilkesi oluşturabilirsiniz. 

## <a name="before-you-begin"></a>Başlamadan önce

MTD kurulumunun parçası olarak, MTD iş ortağı konsolunda çeşitli tehditleri yüksek, orta ve düşük olarak sınıflandıran bir ilke oluşturdunuz. Artık, Intune uygulama koruma ilkesinde Mobile Threat Defense düzeyini ayarlamanız gerekir.

MTD ile uygulama koruma ilkesi önkoşulları:

- Intune ile MTD tümleştirmesini ayarlayın. Bu tümleştirme olmadan MTD uygulama koruma ilkesinin hiçbir etkisi olmayacaktır.

## <a name="to-create-an-mtd-app-protection-policy"></a>MTD uygulama koruma ilkesi oluşturmak için

1. [Azure Portal](https://portal.azure.com/)’a gidin ve Intune kimlik bilgilerinizle oturum açın.

2. **Azure Panosunda**, soldaki menüden **Tüm hizmetler**’i seçtikten sonra, metin kutusu filtresine **Intune** yazın.

3. **Intune**'u seçin, **Intune Panosu** açılır.

4. **Intune panosunda**, **istemci uygulamaları**' nı ve ardından **Yönet** bölümü altında **Uygulama koruma ilkeleri** ' ni seçin.

5. **Ilke oluştur**' u seçin, **ad**, **Açıklama**girin, **platformu**seçin. 

6. **Koşullu başlatma** bölmesinde, **cihaz koşulları** tablosu altında, **izin verilen en fazla cihaz tehdit düzeyi**altındaki açılan listeden mobil tehdit düzeyini seçin.

    a.  **Güvenli**: En güvenli düzeydir. Cihazda herhangi bir tehdit mevcut olamaz ve yine de şirket kaynaklarına erişebilir. Herhangi bir tehdit bulunursa cihaz uyumsuz olarak değerlendirilir.

    b.  **Düşük**: Cihaz, yalnızca düşük düzeydeki tehditler varsa uyumludur. Daha yüksek bir tehdit düzeyi, cihazı uyumlu değil durumuna getirir.

    c.  **Orta**: Cihazda bulunan tehditler düşük veya orta düzeydeyse cihaz uyumludur. Yüksek düzeyde tehditler algılanırsa cihaz uyumsuz olarak değerlendirilir.

    d.  **Yüksek**: Bu, en az güvenli düzeydir. Bu, tüm tehdit düzeylerine izin verir ve Mobile Threat Defense’i yalnızca raporlama amacıyla kullanır. Cihazlar, bu ayar ile MTD uygulamasının etkin olmasını gerektirir.

7. İki kez **Kaydet** ' e tıkladıktan sonra **Oluştur**' u seçin.

## <a name="to-assign-an-mtd-app-protection-policy"></a>Bir MTD uygulama koruma ilkesi atamak için

Kullanıcılara bir cihaz uyumluluk ilkesi atamak için daha önce yapılandırdığınız bir ilkeyi seçin. Mevcut ilkeler, **Cihaz uyumluluk ilkeleri** bölmesinde bulunabilir.

1. Kullanıcılara atamak istediğiniz ilkeyi seçin ve ardından **Atamalar**’ı seçin. Bu eylem, **Azure Active Directory güvenlik gruplarını** seçebileceğiniz ve bunları ilkeye atayabileceğiniz bölmeyi açar.

2. Azure AD güvenlik gruplarını görüntüleyen bölmeyi açmak için **dahil edilecek grupları seç ' i** seçin. **Seç ' i** seçmek ilkeyi kullanıcılara dağıtır.

> [!NOTE] 
> İlkeyi kullanıcılara uyguladınız. İlke tarafından hedeflenen kullanıcılar tarafından kullanılan cihazlar, Intune uygulama koruması aracılığıyla hedeflenen uygulamalardaki şirket verilerine erişim için değerlendirilir.

## <a name="next-steps"></a>Sonraki adımlar  

- Microsoft Intune 'de [Mobile Threat](~/protect/mobile-threat-defense.md) Defense hakkında daha fazla bilgi edinin.
