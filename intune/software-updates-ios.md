---
title: Microsoft Intune'da iOS yazılım güncelleştirme ilkelerini yapılandırma - Azure | Microsoft Docs
description: Microsoft Intune’da, Intune tarafından yönetilen veya denetlenen iOS cihazlarında otomatik olarak yüklü yazılımların güncelleştirmelerini kısıtlamak için bir yapılandırma ilkesi oluşturun veya ekleyin. Güncelleştirmelerin yükleneceği tarihi ve saati seçebilirsiniz. Bu ilkeyi gruplara, kullanıcılara veya cihazlara da atayarak yükleme hatalarını denetleyebilirsiniz.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
search.appverid: MET150
ms.openlocfilehash: 12b387a5c09e0d009fa5014ff355104f6bff71f3
ms.sourcegitcommit: e0d55bdda1a818ffe4cfc0ef0592833e22f65a89
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55290647"
---
# <a name="configure-ios-update-policies-in-intune"></a>Intune’da iOS güncelleştirme ilkelerini yapılandırma

Yazılım güncelleştirme ilkeleri, denetimli iOS cihazlarını otomatik olarak en yeni işletim sistemi güncelleştirmesini yüklemeye zorlamanıza olanak sağlar. Bu özellik yalnızca denetimli cihazlarda kullanılabilir. İlke yapılandırırken, cihazların güncelleştirme yüklemesi yapmalarını istemediğiniz gün ve saatleri ekleyebilirsiniz. 

Cihaz, 8 saatte bir Intune’a iade edilir. Güncelleştirme varsa ve kısıtlanan saatlerde değilse, cihaz en son işletim sistemi güncelleştirmesini indirir ve yükler. Cihazın güncelleştirilmesi için kullanıcı etkileşimi gerekli değildir. İlke, kullanıcının işletim sistemini el ile güncelleştirmesini engellemez.

Bu özellik iOS 10.3 ve sonraki sürümleri çalıştıran cihazları destekler. Gecikme süresi ayarı iOS 11.3 ve sonraki sürümlerde kullanılabilir.

## <a name="configure-the-policy"></a>İlkeyi yapılandırma
1. [Azure Portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
3. **Yazılım güncelleştirilmeleri** > **iOS için güncelleştirme ilkeleri** > **Oluştur**’u seçin.
4. İlke için bir ad ve açıklama girin.
5. **Ayarlar**’ı seçin. 

    iOS cihazlarının en son güncelleştirmeyi yüklemeye zorlanmadığı durumlara ilişkin ayrıntıları girin. Bu ayarlar kısıtlı bir zaman çerçevesi oluşturur. Haftanın **Günlerini**, **Saat dilimini**, **Başlangıç saatini**, **Bitiş saatini** ve **Yazılım güncelleştirmesinin görünürlüğünü geciktirme (gün)** seçeneğini ayarlayabilirsiniz. Yazılım güncelleştirmeleri için 1 ila 90 gün arasında bir geciktirme aralığı seçebilirsiniz. Yazılım güncelleştirmesini geciktirmek istemiyorsanız 0 değerini girin. Bu güncelleştirme ayarları, yalnızca denetimli iOS cihazlarında geçerlidir.

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

