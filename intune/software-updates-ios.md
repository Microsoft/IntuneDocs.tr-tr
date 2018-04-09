---
title: Microsoft Intune'da iOS yazılım güncelleştirme ilkelerini yapılandırma
titlesuffix: ''
description: Denetimli iOS cihazlarını otomatik olarak en yeni yazılım güncelleştirmesini yüklemeye zorlamak üzere iOS için güncelleştirme ilkelerini yapılandırın.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.openlocfilehash: 39432d09bea822c25ca9e11181a11a1e2298dfef
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="configure-ios-update-policies-in-microsoft-intune"></a>Microsoft Intune'da iOS güncelleştirme ilkelerini yapılandırma

Yazılım güncelleştirme ilkeleri, iOS 10.3 ve üstünü çalıştıran denetimli iOS cihazlarını otomatik olarak en yeni işletim sistemi güncelleştirmesini yüklemeye zorlamanıza olanak sağlar. Bu özellik yalnızca denetimli cihazlarda kullanılabilir. Cihazların güncelleştirmeyi yüklemesini istemediğinizde, gün ve saat yapılandırma seçeneğine sahip olursunuz. 

Cihaz yaklaşık 8 saatte bir güncelleştirme sağlanıp sağlanmadığını denetler ve sınırlandırma olan bir dönemde olmadığında en son işletim sistemi güncelleştirmesini indirmeyi ve yüklemeyi dener. Cihazın güncelleştirilmesi için kullanıcı etkileşimi gerekli değildir. İlke, kullanıcının işletim sistemini güncelleştirmesini engellemez.

## <a name="configure-the-ios-update-policy"></a>iOS güncelleştirme ilkesini yapılandırma
1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde, **Yazılım güncelleştirmeleri** > **iOS Güncelleştirme İlkeleri**’ni seçin.
4. İlkeler bölmesinde, **Oluştur**’u seçtikten sonra ilke için bir ad ve açıklama girin.
5. **Ayarlar** > **Yapılandırma**’yı seçin ve iOS cihazlarının en son güncelleştirmeyi yüklemeye zorlanmadığı durumlara ilişkin ayrıntıları girin. Haftanın günlerini, saat dilimini, başlangıç ve bitiş saatlerini yapılandırabilirsiniz.
6. Bu yapılandırmayı kaydetmek için **Tamam**’ı seçin. **Güncelleştirme ilkesi oluştur** bölmesine geri dönersiniz. İlkeyi oluşturmak ve ayarlarınızı kaydetmek için **Oluştur**’u seçin.

Profil oluşturulur ve iOS güncelleştirme ilkeleri listesi bölmesinde görüntülenir. Apple MDM, cihazın güncelleştirmeyi belirli bir tarih veya saatte yüklemesini zorunlu tutmaya izin vermez. 

## <a name="change-the-restricted-times-for-the-policy"></a>İlkeye yönelik kısıtlı saatleri değiştirme

1.  **Yazılım güncelleştirmeleri** dikey penceresinde, **iOS Güncelleştirme İlkeleri**’ni seçin.
2.  Güncelleştirmek istediğiniz iOS güncelleştirme ilkesini seçin.
3.  **Özellikler**’i seçin ve kısıtlı saat bilgilerini güncelleştirin.
4.  Haftanın günlerini seçin
5.  Bu ilkenin uygulanacağı saat dilimi
6.  Kara listeye alınan saatler için başlangıç ve bitiş saatleri

## <a name="assign-an-ios-update-policy-to-users"></a>Bir iOS güncelleştirme ilkesini kullanıcılara atama

Kullanıcılara bir iOS güncelleştirme ilkesi atamak için yapılandırdığınız bir ilkeyi seçin. Mevcut ilkeler **Yazılım güncelleştirmeleri** > **iOS Güncelleştirme İlkeleri** bölmesinde bulunur.

1. Kullanıcılara atamak istediğiniz ilkeyi seçin ve ardından **Atamalar**’ı seçin. Azure Active Directory güvenlik gruplarını seçebileceğiniz ve bunları ilkeye atayabileceğiniz bölme açılır.
2. Azure AD güvenlik gruplarının görüntülendiği bölmeyi açmak için **Seçilen gruplar**’ı seçin. Hem dahil edilecek hem de dışlanacak grupları atayarak, ilkeye kimlerin erişebileceğini belirleyebilirsiniz.
3. İlkeyi kullanıcılara dağıtmak için **Kaydet**’i seçin.

İlkeyi kullanıcılarınıza veya cihazlarınıza uyguladınız. İlkenin hedeflediği kullanıcılar tarafından kullanılan cihazlar, güncelleştirme uyumluluğu için denetlenir. Bu ilke kullanıcısı olmayan cihazları da destekler.

## <a name="monitor-ios-device-installation-failures"></a>iOS cihaz yükleme hatalarını izleme
<!-- 1352223 -->
**iOS cihazlarında yükleme hataları** raporu, **Yazılım güncelleştirmeleri** bölmesinde sağlanır. Raporda, bir iOS güncelleştirme ilkesi tarafından hedeflenmiş, güncelleştirmeyi denemiş ancak güncelleştirilememiş denetimli iOS cihazların listesini görüntüleyebilirsiniz. Her cihaz için cihazın neden otomatik olarak güncelleştirilmediğiyle ilgili bir durum görüntüleyebilirsiniz. İyi durumda, güncel cihazlar listede gösterilmez. Güncel olma durumunu, cihazın destekleyebileceği en son güncelleştirme olarak tanımlarız.
