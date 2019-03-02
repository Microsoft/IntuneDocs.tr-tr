---
title: Microsoft Intune'da iOS yazılım güncelleştirme ilkelerini yapılandırma - Azure | Microsoft Docs
description: Microsoft Intune’da, Intune tarafından yönetilen veya denetlenen iOS cihazlarında otomatik olarak yüklü yazılımların güncelleştirmelerini kısıtlamak için bir yapılandırma ilkesi oluşturun veya ekleyin. Güncelleştirmelerin yükleneceği tarihi ve saati seçebilirsiniz. Bu ilkeyi gruplara, kullanıcılara veya cihazlara da atayarak yükleme hatalarını denetleyebilirsiniz.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/06/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 365ada79914caafb07bb19a7f877ca9c86458aae
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57229369"
---
# <a name="add-ios-software-update-policies-in-intune"></a>Intune'da iOS yazılım güncelleştirme ilkelerini ekleme

Yazılım güncelleştirme ilkeleri, denetimli iOS cihazlarını otomatik olarak en yeni işletim sistemi güncelleştirmesini yüklemeye zorlamanıza olanak sağlar. İlke yapılandırırken, cihazların güncelleştirme yüklemesi yapmalarını istemediğiniz gün ve saatleri ekleyebilirsiniz. 

Bu özellik şu platformlarda geçerlidir:

- iOS 10.3 ve üstünü (denetimli)

Cihaz, 8 saatte bir Intune’a iade edilir. Güncelleştirme varsa ve kısıtlanan saatlerde değilse, cihaz en son işletim sistemi güncelleştirmesini indirir ve yükler. Cihazın güncelleştirilmesi için kullanıcı etkileşimi gerekli değildir. İlke, kullanıcının işletim sistemini el ile güncelleştirmesini engellemez.

## <a name="configure-the-policy"></a>İlkeyi yapılandırma

1. İçinde [Azure portalında](https://portal.azure.com)seçin **tüm hizmetleri** > Filtre **Intune** > seçin **Intune**.
2. **Yazılım güncelleştirilmeleri** > **iOS için güncelleştirme ilkeleri** > **Oluştur**’u seçin.
3. Aşağıdaki ayarları girin:

    - **Ad**: Yazılım güncelleştirmeleri ilkeniz için bir ad girin. Örneğin, şunu girin: `iOS restricted update times`.
    - **Açıklama**: İlkeniz için bir açıklama girin. Bu ayar isteğe bağlıdır ancak önerilir.

4. Seçin **ayarlar > Yapılandır**. Aşağıdaki ayarları girin:

    - **Güncelleştirme yüklemelerine engel olmak için saatleri seçin**: Güncelleştirmeleri zorla yüklendiğinde olmayan sınırlı bir zaman çerçevesi girin. Kısıtlı zaman çerçevesini ayarlarken, aşağıdaki bilgileri girin:

      - **Gün**: Güncelleştirmelerin ne zaman yüklü olmayan haftanın günlerini seçin. Örneğin, Pazartesi, Çarşamba ve Cuma şu günlerde yüklü güncelleştirmeleri önlemek için denetleyin.
      - **Saat dilimi**: Bir saat dilimi seçin.
      - **Başlangıç saati**: Sınırlı bir zaman çerçevesi başlangıç saati seçin. Örneğin, 05: 00 başlangıç güncelleştirmeleri yüklü şekilde 5'te girin.
      - **Bitiş saati**: Kısıtlı zaman dilimi bitiş saati seçin. Örneğin, güncelleştirme 1'de başlayarak yüklenebilmesi için 1'da girin.

    - **Zamanlanmış güncelleştirmeler için değişiklik olmadan son kullanıcılara yazılım güncelleştirmelerini görünürlüğünü gecikme (gün)**: 

      **Bu ayar taşınabilir [cihaz kısıtlamaları](device-restrictions-ios.md#general). Portalda bu konumdan kaldırılacak**. Kısa bir süre için burada mevcut ilkeleri değiştirilebilir. Sonra yaklaşık bir ay, mevcut İlkeleri'nden bu ayar kaldırılacak.

      Etkisini sınırlamak için önerilir:
        - Portal bu konumda mevcut ilkeyi kaldırın.
        - Yeni bir [cihaz kısıtlama ilkesi](device-restrictions-ios.md#general).
        - Özgün ilkenin olarak aynı kullanıcıları hedefleyebilirsiniz.

      Bir çakışma varsa, bu ayarın hiçbir şey yapmaz *sürece* iki değer aynıdır. Bir çakışmayı önlemek için değiştirmek veya portal bu konumda mevcut ilkeyi kaldırmak emin olun.

5. Seçin **Tamam** > **Oluştur** yaptığınız değişiklikleri kaydedin ve ilkeyi oluşturun.

Profil oluşturulur ve ilke listesinde gösterilir.

Intune destek ekibinden yönergeler için bkz [gecikme denetimli cihazlar için ıntune'da yazılım güncelleştirmeleri görünürlüğünü](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Delaying-visibility-of-software-updates-in-Intune-for-supervised/ba-p/345753).

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
    > Hem **Başlangıç saati** hem de **Bitiş saati** olarak 12:00 ayarlanırsa, bakım saati denetimi devre dışı bırakılır.

## <a name="assign-the-policy-to-users"></a>Kullanıcılara ilke atama

Var olan ilkeler gruplara, kullanıcılara ve cihazlara atanır. İlke, atandığında uygulanır.

1. **Yazılım güncelleştirmeleri**’nde **iOS için güncelleştirme ilkeleri**’ni seçin.
2. Var olan bir ilkeyi > **Atamalar**’ı seçin. 
3. İlkeye eklemek veya ilkeden dışlamak istediğiniz Azure Active Directory grupları, kullanıcıları veya cihazlarını seçin.
4. İlkeyi gruplarınıza dağıtmak için **Kaydet**’i seçin.

İlkenin hedeflediği kullanıcılar tarafından kullanılan cihazlar, güncelleştirme uyumluluğu için denetlenir. Bu ilke kullanıcısı olmayan cihazları da destekler.

## <a name="monitor-device-installation-failures"></a>Cihaz yükleme hatalarını izleme
<!-- 1352223 -->
**Yazılım güncelleştirmeleri** > **iOS cihazları için yükleme hataları** altında, güncelleştirme ilkesi tarafından hedeflenen, güncelleştirmeyi denemiş ve güncelleştirilememiş denetimli iOS cihazlarının listesi gösterilir. Her cihazda, cihazın otomatik olarak güncelleştirilememesinin nedenini açıklayan bir durum görebilirsiniz. İyi durumda, güncel cihazlar bu listede gösterilmez. “Güncel” cihazlar, cihazın desteklediği en yeni güncelleştirmeyi içerir.

## <a name="next-steps"></a>Sonraki adımlar

[Profili atama](device-profile-assign.md) ve [durumunu izleme](device-profile-monitor.md).
