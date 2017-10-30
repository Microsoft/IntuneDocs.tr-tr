---
title: "iOS güncelleştirme ilkelerini yapılandırma"
titlesuffix: Azure portal
description: "Denetimli iOS cihazlarını otomatik olarak en yeni yazılım güncelleştirmesini yüklemeye zorlamak üzere iOS için güncelleştirme ilkelerini yapılandırın."
keywords: 
author: dougeby
manager: dougeby
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6334421-85e1-4457-9c44-e5db8d4ee00e
ms.openlocfilehash: 199760a60ee2290560ebdf933192de0eaf569e9e
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2017
---
# <a name="configure-ios-update-policies"></a>iOS güncelleştirme ilkelerini yapılandırma
iOS için güncelleştirme ilkeleri, denetimli iOS cihazlarını otomatik olarak en yeni yazılım güncelleştirmesini yüklemeye zorlamanıza olanak sağlar. Cihazların güncelleştirmeyi yüklemesini istemediğinizde, gün ve saat yapılandırma seçeneğine sahip olursunuz.

## <a name="configure-the-ios-update-policy"></a>iOS güncelleştirme ilkesini yapılandırma
1. Azure portalında Intune dikey penceresine gidin.
2. **Intune** dikey penceresinde, **Yazılım güncelleştirmeleri** > **iOS Güncelleştirme İlkeleri**’ni seçin.
4. İlkeler dikey penceresinde, **Oluştur**’u seçtikten sonra ilke için bir ad ve açıklama girin.
5. **Ayarlar** > **Yapılandırma**’yı seçin ve iOS cihazlarının en son güncelleştirmeyi yüklemeye zorlanmadığı durumlara ilişkin ayrıntıları girin.
6. Bu yapılandırmayı kaydetmek için **Tamam**’ı seçin. **Güncelleştirme ilkesi oluştur** dikey penceresine geri dönersiniz. İlkeyi oluşturmak ve ayarlarınızı kaydetmek için **Oluştur**’u seçin.

Profil oluşturulur ve iOS güncelleştirme ilkeleri listesi dikey penceresinde görüntülenir.

## <a name="assign-an-ios-update-policy-to-users"></a>Bir iOS güncelleştirme ilkesini kullanıcılara atama
Kullanıcılara bir iOS güncelleştirme ilkesi atamak için yapılandırdığınız bir ilkeyi seçin. Mevcut ilkeler **Yazılım güncelleştirmeleri** > **iOS Güncelleştirme İlkeleri** dikey penceresinde bulunur.
1. Kullanıcılara atamak istediğiniz ilkeyi seçin ve ardından **Atamalar**’ı seçin. Azure Active Directory güvenlik gruplarını seçebileceğiniz ve bunları ilkeye atayabileceğiniz dikey pencere açılır.
2. Azure AD güvenlik gruplarının görüntülendiği dikey pencereyi açmak için **Grupları seçin** öğesini seçin. İlkeyi kullanıcılara dağıtmak için **Seç** öğesini seçin.

İlkeyi kullanıcılara uyguladınız. İlkenin hedeflediği kullanıcılar tarafından kullanılan cihazlar, güncelleştirme uyumluluğu için denetlenir.

## <a name="change-the-restricted-days-for-the-policy"></a>İlkeye yönelik kısıtlı günleri değiştirme
1. **Yazılım güncelleştirmeleri** dikey penceresinde, **iOS Güncelleştirme İlkeleri**’ni seçin.
2. Güncelleştirmek istediğiniz iOS güncelleştirme ilkesini seçin.
3. **Özellikler**’i seçin ve kısıtlı günler bilgileri güncelleştirin.

## <a name="monitor-ios-devices-with-older-ios-versions"></a>Eski iOS sürümleri çalıştıran iOS cihazlarını izleme 
<!-- 1352223 -->
**Güncel olmayan iOS Cihazları** raporu, **Yazılım güncelleştirmeleri** > **iOS Güncelleştirme İlkeleri** dikey penceresinde kullanılabilir. Raporda, bir iOS güncelleştirme ilkesi tarafından hedeflenmiş ancak güncelleştirilememiş denetimli iOS cihazların listesini görüntüleyebilirsiniz. Her cihaz için cihazın neden otomatik olarak güncelleştirilmediğiyle ilgili bir durum görüntüleyebilirsiniz.