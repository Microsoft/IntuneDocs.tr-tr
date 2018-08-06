---
title: Microsoft Intune'da iOS yazılım güncelleştirme ilkelerini yapılandırma - Azure | Microsoft Docs
description: Microsoft Intune’da, Intune tarafından yönetilen veya denetlenen iOS cihazlarında otomatik olarak yüklü yazılımların güncelleştirmelerini kısıtlamak için bir yapılandırma ilkesi oluşturun veya ekleyin. Güncelleştirmelerin yükleneceği tarihi ve saati seçebilirsiniz. Bu ilkeyi gruplara, kullanıcılara veya cihazlara da atayarak yükleme hatalarını denetleyebilirsiniz.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.openlocfilehash: b9cc34b2fa45ae447a015f1b3105081041bd0afe
ms.sourcegitcommit: 0a2e737c5520c1a1dec5d732e5df52b5614b27e1
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/26/2018
ms.locfileid: "39268847"
---
# <a name="configure-ios-update-policies-in-intune"></a>Intune’da iOS güncelleştirme ilkelerini yapılandırma

Yazılım güncelleştirme ilkeleri, denetimli iOS cihazlarını otomatik olarak en yeni işletim sistemi güncelleştirmesini yüklemeye zorlamanıza olanak sağlar. Bu özellik yalnızca denetimli cihazlarda kullanılabilir. İlke yapılandırırken, cihazların güncelleştirme yüklemesi yapmalarını istemediğiniz gün ve saatleri ekleyebilirsiniz. 

Cihaz, 8 saatte bir Intune’a iade edilir. Güncelleştirme varsa ve kısıtlanan saatlerde değilse, cihaz en son işletim sistemi güncelleştirmesini indirir ve yükler. Cihazın güncelleştirilmesi için kullanıcı etkileşimi gerekli değildir. İlke, kullanıcının işletim sistemini el ile güncelleştirmesini engellemez.

Bu özellik iOS 10.3 ve sonraki sürümleri çalıştıran cihazları destekler.

## <a name="configure-the-policy"></a>İlkeyi yapılandırma
1. [Azure portalı](https://portal.azure.com)’nda oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Yazılım güncelleştirilmeleri** > **iOS için güncelleştirme ilkeleri** > **Oluştur**’u seçin.
4. İlke için bir ad ve açıklama girin.
5. **Ayarlar**’ı seçin. 

    iOS cihazlarının en son güncelleştirmeyi yüklemeye zorlanmadığı durumlara ilişkin ayrıntıları girin. Bu ayarlar kısıtlı bir zaman çerçevesi oluşturur. Haftanın günlerini, saat dilimini, başlangıç ve bitiş saatlerini yapılandırabilirsiniz.

6. Değişikliklerinizi kaydetmek için **Tamam**’ı seçin. İlkeyi oluşturmak için **Oluştur**’u seçin.

Profil oluşturulur ve ilke listesinde gösterilir. Apple MDM, cihazın güncelleştirmeleri belirli bir saatte veya tarihte yüklemeye zorlanmasına izin vermez. 

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

