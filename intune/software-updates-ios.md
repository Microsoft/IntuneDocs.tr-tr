---
title: "Microsoft Intune'da iOS güncelleştirme ilkelerini yapılandırma"
titlesuffix: 
description: "Denetimli iOS cihazlarını otomatik olarak en yeni yazılım güncelleştirmesini yüklemeye zorlamak üzere iOS için güncelleştirme ilkelerini yapılandırın."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.openlocfilehash: 6ba354fb3b39544f09363651abfd9e1a5c0f6154
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="configure-ios-update-policies-in-microsoft-intune"></a>Microsoft Intune'da iOS güncelleştirme ilkelerini yapılandırma
iOS için güncelleştirme ilkeleri, denetimli iOS cihazlarını otomatik olarak en yeni yazılım güncelleştirmesini yüklemeye zorlamanıza olanak sağlar. Cihazların güncelleştirmeyi yüklemesini istemediğinizde, gün ve saat yapılandırma seçeneğine sahip olursunuz.

## <a name="configure-the-ios-update-policy"></a>iOS güncelleştirme ilkesini yapılandırma
1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
2. **Intune** bölmesinde, **Yazılım güncelleştirmeleri** > **iOS Güncelleştirme İlkeleri**’ni seçin.
4. İlkeler bölmesinde, **Oluştur**’u seçtikten sonra ilke için bir ad ve açıklama girin.
5. **Ayarlar** > **Yapılandırma**’yı seçin ve iOS cihazlarının en son güncelleştirmeyi yüklemeye zorlanmadığı durumlara ilişkin ayrıntıları girin.
6. Bu yapılandırmayı kaydetmek için **Tamam**’ı seçin. **Güncelleştirme ilkesi oluştur** bölmesine geri dönersiniz. İlkeyi oluşturmak ve ayarlarınızı kaydetmek için **Oluştur**’u seçin.

Profil oluşturulur ve iOS güncelleştirme ilkeleri listesi bölmesinde görüntülenir.

## <a name="assign-an-ios-update-policy-to-users"></a>Bir iOS güncelleştirme ilkesini kullanıcılara atama
Kullanıcılara bir iOS güncelleştirme ilkesi atamak için yapılandırdığınız bir ilkeyi seçin. Mevcut ilkeler **Yazılım güncelleştirmeleri** > **iOS Güncelleştirme İlkeleri** bölmesinde bulunur.
1. Kullanıcılara atamak istediğiniz ilkeyi seçin ve ardından **Atamalar**’ı seçin. Azure Active Directory güvenlik gruplarını seçebileceğiniz ve bunları ilkeye atayabileceğiniz bölme açılır.
2. Azure AD güvenlik gruplarının görüntülendiği sayfayı açmak için **Seçili gruplar**’ı seçin.
3. İlkeyi kullanıcılara dağıtmak için **Kaydet**’i seçin.

İlkeyi kullanıcılara uyguladınız. İlkenin hedeflediği kullanıcılar tarafından kullanılan cihazlar, güncelleştirme uyumluluğu için denetlenir.

## <a name="change-the-restricted-days-for-the-policy"></a>İlkeye yönelik kısıtlı günleri değiştirme
1. **Yazılım güncelleştirmeleri** bölmesinde, **iOS Güncelleştirme İlkeleri**’ni seçin.
2. Güncelleştirmek istediğiniz iOS güncelleştirme ilkesini seçin.
3. **Özellikler** > **Ayarlar**’ı seçin ve kısıtlı günler bilgilerini güncelleştirin.

## <a name="monitor-ios-devices-with-older-ios-versions"></a>Eski iOS sürümleri çalıştıran iOS cihazlarını izleme
<!-- 1352223 -->
**Güncel olmayan iOS Cihazları** raporu, **Yazılım güncelleştirmeleri** > **iOS Güncelleştirme İlkeleri** bölmesinde kullanılabilir. Raporda, bir iOS güncelleştirme ilkesi tarafından hedeflenmiş ancak güncelleştirilememiş denetimli iOS cihazların listesini görüntüleyebilirsiniz. Her cihaz için cihazın neden otomatik olarak güncelleştirilmediğiyle ilgili bir durum görüntüleyebilirsiniz.
