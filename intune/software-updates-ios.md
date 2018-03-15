---
title: "Microsoft Intune'da iOS güncelleştirme ilkelerini yapılandırma"
titlesuffix: 
description: "Denetimli iOS cihazlarını otomatik olarak en yeni yazılım güncelleştirmesini yüklemeye zorlamak üzere iOS için güncelleştirme ilkelerini yapılandırın."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.openlocfilehash: 2062f9cd551ec6d7f42449041e6c8de837221631
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2018
---
# <a name="configure-ios-update-policies-in-microsoft-intune"></a>Microsoft Intune'da iOS güncelleştirme ilkelerini yapılandırma
iOS için güncelleştirme ilkeleri, denetimli iOS cihazlarını otomatik olarak en yeni yazılım güncelleştirmesini yüklemeye zorlamanıza olanak sağlar. Cihazların güncelleştirmeyi yüklemesini istemediğinizde, gün ve saat yapılandırma seçeneğine sahip olursunuz.

## <a name="configure-the-ios-update-policy"></a>iOS güncelleştirme ilkesini yapılandırma
1. Azure portalında Intune sayfasına gidin.
2. **Intune** sayfasında, **Yazılım güncelleştirmeleri** > **iOS Güncelleştirme İlkeleri**’ni seçin.
4. İlkeler sayfasında, **Oluştur**’u seçtikten sonra ilke için bir ad ve açıklama girin.
5. **Ayarlar** > **Yapılandırma**’yı seçin ve iOS cihazlarının en son güncelleştirmeyi yüklemeye zorlanmadığı durumlara ilişkin ayrıntıları girin.
6. Bu yapılandırmayı kaydetmek için **Tamam**’ı seçin. **Güncelleştirme ilkesi oluştur** sayfasına geri dönersiniz. İlkeyi oluşturmak ve ayarlarınızı kaydetmek için **Oluştur**’u seçin.

Profil oluşturulur ve iOS güncelleştirme ilkeleri listesi sayfasında görüntülenir.

## <a name="assign-an-ios-update-policy-to-users"></a>Bir iOS güncelleştirme ilkesini kullanıcılara atama
Kullanıcılara bir iOS güncelleştirme ilkesi atamak için yapılandırdığınız bir ilkeyi seçin. Mevcut ilkeler **Yazılım güncelleştirmeleri** > **iOS Güncelleştirme İlkeleri** sayfasında bulunur.
1. Kullanıcılara atamak istediğiniz ilkeyi seçin ve ardından **Atamalar**’ı seçin. Azure Active Directory güvenlik gruplarını seçebileceğiniz ve bunları ilkeye atayabileceğiniz sayfa açılır.
2. Azure AD güvenlik gruplarının görüntülendiği sayfayı açmak için **Grupları seçin** öğesini seçin. İlkeyi kullanıcılara dağıtmak için **Seç** öğesini seçin.

İlkeyi kullanıcılara uyguladınız. İlkenin hedeflediği kullanıcılar tarafından kullanılan cihazlar, güncelleştirme uyumluluğu için denetlenir.

## <a name="change-the-restricted-days-for-the-policy"></a>İlkeye yönelik kısıtlı günleri değiştirme
1. **Yazılım güncelleştirmeleri** sayfasında, **iOS Güncelleştirme İlkeleri**’ni seçin.
2. Güncelleştirmek istediğiniz iOS güncelleştirme ilkesini seçin.
3. **Özellikler**’i seçin ve kısıtlı günler bilgileri güncelleştirin.

## <a name="monitor-ios-devices-with-older-ios-versions"></a>Eski iOS sürümleri çalıştıran iOS cihazlarını izleme 
<!-- 1352223 -->
**Güncel olmayan iOS Cihazları** raporu, **Yazılım güncelleştirmeleri** > **iOS Güncelleştirme İlkeleri** sayfasında kullanılabilir. Raporda, bir iOS güncelleştirme ilkesi tarafından hedeflenmiş ancak güncelleştirilememiş denetimli iOS cihazların listesini görüntüleyebilirsiniz. Her cihaz için cihazın neden otomatik olarak güncelleştirilmediğiyle ilgili bir durum görüntüleyebilirsiniz.