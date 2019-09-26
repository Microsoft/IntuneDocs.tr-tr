---
title: Microsoft Intune'da iOS yazılım güncelleştirme ilkelerini yapılandırma - Azure | Microsoft Docs
description: Microsoft Intune’da, Intune tarafından yönetilen veya denetlenen iOS cihazlarında otomatik olarak yüklü yazılımların güncelleştirmelerini kısıtlamak için bir yapılandırma ilkesi oluşturun veya ekleyin. Güncelleştirmelerin yükleneceği tarihi ve saati seçebilirsiniz. Bu ilkeyi gruplara, kullanıcılara veya cihazlara da atayarak yükleme hatalarını denetleyebilirsiniz.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: eeaf3dc1e7f1dfa1cfc3ff0da554f65d416a354b
ms.sourcegitcommit: 62c41976c4da43b36015b715bc255397ebb8c6ad
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274821"
---
# <a name="add-ios-software-update-policies-in-intune"></a>Intune 'A iOS yazılım güncelleştirme ilkeleri ekleme

Yazılım güncelleştirme ilkeleri, denetimli iOS cihazlarını otomatik olarak en yeni işletim sistemi güncelleştirmesini yüklemeye zorlamanıza olanak sağlar. İlke yapılandırırken, cihazların güncelleştirme yüklemesi yapmalarını istemediğiniz gün ve saatleri ekleyebilirsiniz. 

Bu özellik şu platformlarda geçerlidir:

- iOS 10,3 ve üzeri (denetimli)

Cihaz, 8 saatte bir Intune’a iade edilir. Güncelleştirme varsa ve kısıtlanan saatlerde değilse, cihaz en son işletim sistemi güncelleştirmesini indirir ve yükler. Cihazın güncelleştirilmesi için kullanıcı etkileşimi gerekli değildir. İlke, kullanıcının işletim sistemini el ile güncelleştirmesini engellemez.

## <a name="configure-the-policy"></a>İlkeyi yapılandırma

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
2. **Yazılım güncelleştirilmeleri** > **iOS için güncelleştirme ilkeleri** > **Oluştur**’u seçin.
3. Aşağıdaki ayarları girin:

    - **Ad**: Yazılım güncelleştirmeleri ilkeniz için bir ad girin. Örneğin, şunu girin: `iOS restricted update times`.
    - **Açıklama**: İlkenizin için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.

4. **Yapılandırma > ayarları**' nı seçin. Aşağıdaki ayarları girin:

    - **Güncelleştirme yüklemelerinin önlenmesi için zamanları seçin**: Güncelleştirmeler zorlanmadıkça sınırlı bir zaman dilimi belirtin. 
      - Fazla gece blokları desteklenmez ve çalışmayabilir. Örneğin, bir ilkeyi 8 PM *Başlangıç saati* ve 6 ' nın *bitiş saati* ile yapılandırmayın.
      - 12:00 ' da başlayan ve 12 ' de sona erecek bir ilke 0 saat olarak değerlendirilir ve bu, kısıtlama olmadan sonuçlanır.

      Kısıtlanmış zaman çerçevesini ayarlarken, aşağıdaki ayrıntıları girin:

      - **Gün sayısı**: Güncelleştirmelerin yüklü olmadığı haftanın gününü seçin. Örneğin, bu günlerde güncelleştirmelerin yüklenmesini engellemek için Pazartesi, Çarşamba ve Cuma ' yı işaretleyin.
      - **Saat dilimi**: Bir saat dilimi seçin.
      - **Başlangıç zamanı**: Sınırlı zaman çerçevesinin başlangıç saatini seçin. Örneğin, güncelleştirmelerin 5 ' de itibaren yüklenememesi için 5 har girin.
      - **Bitiş zamanı**: Sınırlı zaman çerçevesinin bitiş saatini seçin. Örneğin, güncelleştirme 1 ' den başlayarak yüklenebilmeleri için 1 har girin.

    - Yazılım **güncelleştirme ilkesinde zamanlanan güncelleştirmelerde değişiklik yapmadan son kullanıcılara yazılım güncelleştirmelerinin görünürlüğünü geciktir (gün)** : 

      \* * Denetimli iOS cihazlarınızda yazılım güncelleştirmelerinin görünürlüğünü belirli bir süre için geciktirmek istiyorsanız lütfen [cihaz kısıtlamalarında](device-restrictions-ios.md#general)bu ayarları yapılandırın. Yazılım güncelleştirme ilkeleri tüm cihaz kısıtlamalarını geçersiz kılar. Her iki küme de varsa, yazılım güncelleştirme ilkesi ilk olarak her zaman gelir. 
     
      > [! Önemli  
      > *Başlangıç zamanı* ve *bitiş zamanı* 12 ' ye ayarlanmış bir ilke, 24 saat değil 0 saat olarak değerlendirilir. Bu durum hiçbir kısıtlama vermez.  

5. Değişikliklerinizi kaydetmek ve ilkeyi oluşturmak için **Tamam** > **Oluştur** ' u seçin.

Profil oluşturulur ve ilke listesinde gösterilir.

Intune destek ekibinin Kılavuzu için bkz. [denetimli cihazlar Için Intune 'da yazılım güncelleştirmeleri gecikmesi](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Delaying-visibility-of-software-updates-in-Intune-for-supervised/ba-p/345753).

> [!NOTE]
> Apple MDM, cihazın güncelleştirmeleri belirli bir saatte veya tarihte yüklemeye zorlanmasına izin vermez.

## <a name="change-the-restricted-times-for-the-policy"></a>İlkeye yönelik kısıtlı saatleri değiştirme

1. **Yazılım güncelleştirmeleri**’nde **iOS için güncelleştirme ilkeleri**’ni seçin.
2. Var olan bir ilkeyi > **Ayarlar**’ı seçin.
3. Kısıtlı süreyi güncelleştirin:

    1. Haftanın günlerini seçin
    2. Bu ilkenin uygulandığı saat dilimini seçin
    3. Kara listeye alınan saatler için başlangıç ve bitiş saatlerini girin

    > [!NOTE]
    > **Başlangıç saati** ve **bitiş saatinin** her ikisi de 12Har olarak ayarlandıysa, Intune güncelleştirmelerin ne zaman yükleneceğine ilişkin kısıtlamaları denetlemez. Bu, **güncelleştirme yüklemelerinin yoksayılmasını** ve güncelleştirmelerin herhangi bir zamanda yüklenebilmesini sağlamak için, seçtiğiniz her yapılandırmalardan daha fazla yol gösterir.  

## <a name="assign-the-policy-to-users"></a>Kullanıcılara ilke atama

Var olan ilkeler gruplara, kullanıcılara ve cihazlara atanır. İlke, atandığında uygulanır.

1. **Yazılım güncelleştirmeleri**’nde **iOS için güncelleştirme ilkeleri**’ni seçin.
2. Var olan bir ilkeyi > **Atamalar**’ı seçin. 
3. İlkeye eklemek veya ilkeden dışlamak istediğiniz Azure Active Directory grupları, kullanıcıları veya cihazlarını seçin.
4. İlkeyi gruplarınıza dağıtmak için **Kaydet**’i seçin.

İlkenin hedeflediği kullanıcılar tarafından kullanılan cihazlar, güncelleştirme uyumluluğu için denetlenir. Bu ilke kullanıcısı olmayan cihazları da destekler.

## <a name="monitor-device-installation-failures"></a>Cihaz yükleme hatalarını izleme
<!-- 1352223 -->
 > **İOS cihazları için yazılım güncelleştirmeleri yükleme hatalarıyla** , bir güncelleştirme ilkesi tarafından hedeflenen ve güncelleştirme yapılmaya çalışılan ve güncelleştirilemeyen, denetlenen iOS cihazlarının bir listesi gösterilir. Her cihazda, cihazın otomatik olarak güncelleştirilememesinin nedenini açıklayan bir durum görebilirsiniz. İyi durumda, güncel cihazlar bu listede gösterilmez. “Güncel” cihazlar, cihazın desteklediği en yeni güncelleştirmeyi içerir.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).
