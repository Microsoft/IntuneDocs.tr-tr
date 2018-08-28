---
title: Microsoft Intune’da kayıt kısıtlamalarını ayarlama
titlesuffix: ''
description: Intune’da platforma göre kaydı kısıtlama ve cihaz kayıt sınırı ayarlama.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: aa91e0c0adcd1182f82c4a09746f154302fae326
ms.sourcegitcommit: 77ed48ab52b55e92ceaa89e9edf53b892fc62adb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/17/2018
ms.locfileid: "40251696"
---
# <a name="set-enrollment-restrictions"></a>Kayıt kısıtlamalarını ayarlama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune yöneticisi olarak, Intune ile yönetime kaydedilebilecek cihazların sayısını ve türlerini tanımlayan kayıt kısıtlamaları oluşturabilir ve bunları yönetebilirsiniz. Birden çok kısıtlama oluşturabilir ve bunları farklı kullanıcı gruplarına uygulayabilirsiniz. Farklı kısıtlamalarınız için [öncelik sırası](#change-enrollment-restriction-priority) ayarlayabilirsiniz.

>[!NOTE]
>Kayıt kısıtlamaları güvenlik özellikleri değildir. Güvenliği aşılan cihazlar karakterlerini yanlış gösterebilir. Bu kısıtlamalar, kötü amaçlı olmayan kullanıcılara yönelik olabilecek en iyi engeldir.

Özel olarak şu kayıt kısıtlamalarını oluşturabilirsiniz:

- Kayıtlı cihaz sayısı üst sınırı.
- Kaydedilebilecek cihaz platformları:
  - Android.
  - Android iş profili.
  - iOS.
  - macOS.
  - Windows.
- iOS, Android, Android iş profili ve Windows’un platform işletim sistemi sürümü. (Yalnızca Windows 10 sürümleri kullanılabilir. Windows 8.1'e izin veriliyorsa bunu boş bırakın.)
  - En düşük sürüm.
  - En yüksek sürüm.
- Kişisel cihazları kısıtlama (yalnızca iOS, Android, Android iş profili ve macOS).

## <a name="default-restrictions"></a>Varsayılan kısıtlamalar

Hem cihaz türü hem de cihaz sınırı kayıt kısıtlamaları için varsayılan kısıtlamalar otomatik olarak sağlanır. Varsayılanların seçeneklerini değiştirebilirsiniz. Varsayılan kısıtlamalar tüm kullanıcı kayıtlarıyla kullanıcısız kayıtlar için geçerlidir. Daha yüksek önceliklere sahip yeni kısıtlamalar oluşturarak, bu varsayılan kısıtlamaları geçersiz kılabilirsiniz.

## <a name="create-a-restriction"></a>Kısıtlama oluşturma

1. Azure portalında oturum açın.
2. **Diğer Hizmetler**'i seçin, **Intune** için arama yapın ve ardından **Intune**'u seçin.
3. **Cihaz kaydı** > **Kayıt kısıtlamaları**’nı seçin.
4. **Kısıtlama oluştur**'u seçin.
5. Kısıtlamaya bir ad ve açıklama ekleyin.
6. **Kısıtlama türü**'nü ve **Oluştur**'u seçin.
7. Cihaz sınırı kısıtlamaları için, **Cihaz sınırı**'nı seçin ve kullanıcının kaydedebileceği cihaz sayısı üst sınırını ayarlayın.
8. Cihaz türü kısıtlamaları için, çeşitli platformlara ve sürümlere izin vermek veya bunları engellemek üzere **Platformlar**'ı ve **Platform yapılandırmaları**'nı seçin.
9. **Atamalar** > **+ Grupları seçin** öğesini seçin.
10. **Grupları seçin** alanında, bir veya birden çok grup seçin ve ardından **Seç** düğmesini kullanın. Kısıtlama yalnızca atandığı gruplara uygulanır. Kısıtlamayı en az bir gruba atamazsanız, hiçbir etkisi olmaz.
11. **Kaydet**’i seçin.
12. Yeni kısıtlama, varsayılan öncelik düzeyinin hemen üstündeki öncelik düzeyiyle oluşturulur. [Önceliği değiştirebilirsiniz](#change-enrollment-restriction-priority).

## <a name="set-device-type-restrictions"></a>Cihaz türü kısıtlamalarını ayarlama

Aşağıdaki adımları izleyerek bir cihaz türü kısıtlamasının ayarlarını değiştirebilirsiniz:

1. Azure portalında oturum açın.
2. **Diğer Hizmetler**'i seçin, **Intune** için arama yapın ve ardından **Intune**'u seçin.
3. **Cihaz kaydı** > **Kayıt kısıtlamaları**’nı seçin.
4. **Cihaz Türü Kısıtlamaları**'nın altında, ayarlamak istediğiniz kısıtlamayı seçin.
5. Kısıtlama adının altında (varsayılan kısıtlama için **Tüm Kullanıcılar**), **Platformlar**'ı seçin. Listelenen her platform için **İzin Ver** veya **Engelle**'yi seçin.
6. **Kaydet**’i seçin.
7. Kısıtlama adının altında (varsayılan kısıtlama için **Tüm Kullanıcılar**), **Platform Yapılandırmaları**'nı seçin. Sonra, listelenen platformlar için en düşük ve en yüksek **Sürümleri** seçin. Desteklenen sürüm biçimleri:
    - Android iş profili desteği major.minor.rev.build.
    - iOS major.minor.rev destekler.
    - Windows, yalnızca Windows 10 için major.minor.rev.build destekler.
  İşletim sistemi sürümleri, Aygıt Kayıt Programı, Apple School Manager veya Apple Configurator uygulaması ile kaydedilen Apple cihazlar için geçerli değildir.
8. Listelenen her platformda **Kişiye ait** cihazlar için **İzin Ver** veya **Engelle**'yi seçin.
    ![Kişilere ait ayarların yapılandırıldığını gösteren, varsayılan cihaz platform yapılandırmaları ile cihaz kısıtlamaları çalışma alanı](media/device-restrictions-platform-configurations.png)
9. **Kaydet**’i seçin.


>[!NOTE]
>- Kişisel Android cihazların kaydını engellerseniz kişisel Android iş profili cihazları hala kaydedilebilir durumda olacaktır.
>- Varsayılan olarak, Android iş profili cihaz ayarlarınız Android cihazlarınızın ayarlarıyla aynı olur. Android iş profili ayarlarınızı değiştirdikten sonra artık bu durum oluşmaz.
>- Kişisel Android iş profili kaydını engellerseniz, yalnızca kurumsal Android cihazlar Android iş profili olarak kaydedilebilir.

## <a name="set-device-limit-restrictions"></a>Cihaz sınırı kısıtlamalarını ayarlama

Aşağıdaki adımları izleyerek bir cihaz sınırı kısıtlamasının ayarlarını değiştirebilirsiniz:

1. Azure portalında oturum açın.
2. **Diğer Hizmetler**'i seçin, **Intune** için arama yapın ve ardından **Intune**'u seçin.
3. **Cihaz kaydı** > **Kayıt kısıtlamaları**’nı seçin.
4. **Cihaz Sınırı Kısıtlamaları**'nın altında, ayarlamak istediğiniz kısıtlamayı seçin.
5. **Cihaz Sınırı**'nı seçin ve ardından, açılan listede kullanıcının kaydedebileceği cihaz sayısı üst sınırını belirtin.
    ![Cihaz sınır kısıtlamalarını içeren cihaz sınır kısıtlamaları dikey penceresi.](./media/device-restrictions-limit.png)
6. **Kaydet**’i seçin.


Kullanıcılar, kayıtlı cihaz sınırına ulaştığında bunu belirten bir bildirim görür. Örneğin, iOS'ta şöyle görünür:

![iOS cihazı sınır bildirimi](./media/enrollment-restrictions-ios-set-limit-notification.png)

## <a name="change-enrollment-restriction-priority"></a>Kayıt kısıtlama önceliğini değiştirme

Kullanıcı kısıtlamalar atanmış birden çok grupta yer alıyorsa, öncelik kullanılır. Kullanıcılar, yalnızca içinde bulundukları gruba atanmış olan en yüksek öncelik kısıtlamasına uymak zorundadır. Örneğin, Ali hem öncelik düzeyi 5 olan kısıtlamaların atandığı A grubunda hem de öncelik düzeyi 2 olan kısıtlamaların atandığı B grubunda yer alıyordur. Ali yanızca öncelik düzeyi 2 olan kısıtlamalara uymak zorundadır.

Kısıtlama oluşturduğunuzda, bu kısıtlama listede varsayılanın hemen üstüne eklenir.

Cihaz kaydı, hem cihaz türü hem de cihaz sınırı kısıtlamaları için varsayılan kısıtlamalar içerir. Daha yüksek öncelikli kısıtlamalarla geçersiz kılınmadığı sürece, bu iki kısıtlama tüm kullanıcılara uygulanır.

Varsayılan kısıtlamalar dışındaki tüm kısıtlamaların önceliğini değiştirebilirsiniz.

1. Azure portalında oturum açın.
2. **Diğer Hizmetler**'i seçin, **Intune** için arama yapın ve ardından **Intune**'u seçin.
3. **Cihaz kaydı** > **Kayıt kısıtlamaları**’nı seçin.
4. Öncelik listesinde kısıtlamanın üzerine gelin.
5. Üç dikey noktayı kullanarak, önceliği listede dilediğiniz konuma sürükleyin.
