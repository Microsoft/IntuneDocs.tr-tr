---
title: "Intune’da kayıt kısıtlamalarını ayarlama"
titlesuffix: Azure portal
description: "Intune’da platforma göre kaydı kısıtlama ve cihaz kayıt sınırı ayarlama. \""
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 11/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bdb89d3426bd2dd040b184c8f7c23397bbed576b
ms.sourcegitcommit: a99a5104400708b47ecee80075264d541b82874f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/09/2017
---
# <a name="set-enrollment-restrictions"></a>Kayıt kısıtlamalarını ayarlama

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune yöneticisi olarak, Intune ile yönetime kaydedilebilecek cihazların sayısını ve türlerini tanımlayan kayıt kısıtlamaları oluşturabilir ve bunları yönetebilirsiniz. Birden çok kısıtlama oluşturabilir ve bunları farklı kullanıcı gruplarına uygulayabilirsiniz. Farklı kısıtlamalarınız için [öncelik sırası](#change-enrollment-restriction-priority) ayarlayabilirsiniz.

>[!NOTE]
>Kayıt kısıtlamaları güvenlik özellikleri değildir. Güvenliği aşılan cihazlar karakterlerini yanlış gösterebilir. Bu kısıtlamalar, kötü amaçlı olmayan kullanıcılara yönelik olabilecek en iyi engeldir.

>[!NOTE]
>Gruba atanan kayıt kısıtlaması ve aşağıda sözü edilen öncelik işlevi, Intune müşteri tabanı geneline dağıtım aşamasındadır. Bu dağıtım tamamlanana kadar, grup ve öncelik özelliklerine erişemeyebilirsiniz. 

Özel olarak şu kayıt kısıtlamalarını oluşturabilirsiniz:

- Kayıtlı cihaz sayısı üst sınırı
- Kaydedilebilecek cihaz platformları:
  - Android
  - Android for Work
  - iOS
  - Mac OS
  - Windows
- iOS, Android, Android for Work ve Windows (yalnızca Windows 10 sürümleri kullanılabilir, Windows 8.1’e izin verilmişse bu alanı boş bırakın) için platform işletim sistemi sürümü
  - En düşük sürüm
  - En yüksek sürüm
- Kişisel cihazları kısıtlama (yalnızca iOS, Android, Android for Work ve macOS)

## <a name="default-restrictions"></a>Varsayılan kısıtlamalar

Hem cihaz türü hem de cihaz sınırı kayıt kısıtlamaları için varsayılan kısıtlamalar otomatik olarak sağlanır. Varsayılanların seçeneklerini değiştirebilirsiniz. Varsayılan kısıtlamalar tüm kullanıcı kayıtlarıyla kullanıcısız kayıtlar için geçerlidir. Daha yüksek önceliklere sahip yeni kısıtlamalar oluşturarak, bu varsayılan kısıtlamaları geçersiz kılabilirsiniz.

## <a name="create-a-restriction"></a>Kısıtlama oluşturma

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler**'i seçin, **Intune** için arama yapın ve ardından **Intune**'u seçin.
3. **Cihaz kaydı** > **Kayıt kısıtlamaları**’nı seçin.
4. **Kısıtlama oluştur**'u seçin.
5. Kısıtlamaya bir ad ve açıklama ekleyin.
6. **Kısıtlama türü**'nü seçin ve **Oluştur**'a tıklayın.
7. Cihaz sınırı kısıtlamaları için, **Cihaz sınırı**'na tıklayarak kullanıcının kaydedebileceği cihaz sayısı üst sınırını ayarlayın.
8. Cihaz türü kısıtlamaları için, çeşitli platformlara ve sürümlere izin vermek veya bunları engellemek üzere **Platformlar**'a ve **Platform yapılandırmaları**'na tıklayın.
9. **Atamalar** > **+ Grupları seçin**'e tıklayın.
10. **Grupları seçin** alanında, bir veya birden çok grup seçin ve ardından **Seç**'e tıklayın. Kısıtlama yalnızca atandığı gruplara uygulanır. Kısıtlamayı en az bir gruba atamazsanız, hiçbir etkisi olmaz.
11. **Kaydet**'e tıklayın.
12. Yeni kısıtlama, varsayılan öncelik düzeyinin hemen üstündeki öncelik düzeyiyle oluşturulur. [Önceliği değiştirebilirsiniz](#change-enrollment-restriction-priority).

## <a name="set-device-type-restrictions"></a>Cihaz türü kısıtlamalarını ayarlama

Aşağıdaki adımları izleyerek bir cihaz türü kısıtlamasının ayarlarını değiştirebilirsiniz:

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler**'i seçin, **Intune** için arama yapın ve ardından **Intune**'u seçin.
3. **Cihaz kaydı** > **Kayıt kısıtlamaları**’nı seçin.
4. **Cihaz Türü Kısıtlamaları**'nın altında, ayarlamak istediğiniz kısıtlamayı seçin.
5. Kısıtlama adının altında (varsayılan kısıtlama için **Tüm Kullanıcılar**), **Platformlar**'ı seçin. Listelenen her platform için **İzin Ver** veya **Engelle**'yi seçin.
6. **Kaydet**'e tıklayın.
7. Kısıtlama adının altında (varsayılan kısıtlama için **Tüm Kullanıcılar**), **Platform Yapılandırmaları**'nı seçin ve listelenen platformlar için en düşük ve en yüksek **Sürümleri** belirtin. Desteklenen sürümler şunlardır:
  - Android ve Android for Work major.minor.rev.build destekler.
  - iOS major.minor.rev destekler.
  - Windows, yalnızca Windows 10 için major.minor.rev.build destekler.
  İşletim sistemi sürümleri, Aygıt Kayıt Programı, Apple School Manager veya Apple Configurator uygulaması ile kaydedilen Apple cihazlar için geçerli değildir. 
8. Listelenen her platformda **Kişiye ait** cihazlar için **İzin Ver** veya **Engelle**'yi seçin.

    ![Varsayılan cihaz platform yapılandırmaları ile cihaz kısıtlamaları iş alanının, kişisel ayarların yapılandırıldığını gösteren ekran görüntüsü.](media/device-restrictions-platform-configurations.png)
9. **Kaydet**'e tıklayın.

>[!NOTE]
>- Kişisel Android cihazların kaydını engellerseniz kişisel Android for Work cihazlar hala kaydedilebilir durumda olacaktır.
>- Varsayılan olarak, Android for Work cihaz ayarlarınız Android cihazlarınız için ayarlarınızla aynı olacaktır. Ancak Android for Work ayarlarınızı değiştirdikten sonra artık bu durum oluşmaz.
>- Kişisel Android for Work kaydını engellerseniz, yalnızca kurumsal Android cihazlar Android for Work olarak kaydolabilir.

## <a name="set-device-limit-restrictions"></a>Cihaz sınırı kısıtlamalarını ayarlama

Aşağıdaki adımları izleyerek bir cihaz sınırı kısıtlamasının ayarlarını değiştirebilirsiniz:

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler**'i seçin, **Intune** için arama yapın ve ardından **Intune**'u seçin.
3. **Cihaz kaydı** > **Kayıt kısıtlamaları**’nı seçin.
4. **Cihaz Sınırı Kısıtlamaları**'nın altında, ayarlamak istediğiniz kısıtlamayı seçin.
5. **Cihaz Sınırı**'nı seçin ve ardından, açılan listede kullanıcının kaydedebileceği cihaz sayısı üst sınırını belirtin.
    ![Cihaz sınır kısıtlamaları ile cihaz sınır kısıtlamaları dikey penceresinin ekran görüntüsü.](./media/device-restrictions-limit.png)
6. **Kaydet**'e tıklayın.

## <a name="change-enrollment-restriction-priority"></a>Kayıt kısıtlama önceliğini değiştirme

Kullanıcı kısıtlamalar atanmış birden çok grupta yer alıyorsa, öncelik kullanılır. Kullanıcılar, yalnızca içinde bulundukları gruba atanmış olan en yüksek öncelik kısıtlamasına uymak zorundadır. Örneğin, Ali öncelik düzeyi 5 olan kısıtlamaların atandığı A grubunda ve öncelik düzeyi 2 olan kısıtlamaların atandığı B grubunda yer alıyordur. Ali yanızca öncelik düzeyi 2 olan kısıtlamalara uymak zorundadır. 

Kısıtlama oluşturduğunuzda, bu listede varsayılanın hemen üstüne eklenir.

Cihaz kaydı, hem cihaz türü hem de cihaz sınırı kısıtlamaları için varsayılan kısıtlamalar içerir. Daha yüksek öncelikli kısıtlamalarla geçersiz kılınmadığı sürece, bu iki kısıtlama tüm kullanıcılara uygulanır. 

Varsayılan kısıtlamalar dışındaki tüm kısıtlamaların önceliğini değiştirebilirsiniz. 

**Kısıtlama önceliğini değiştirmek için**

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler**'i seçin, **Intune** için arama yapın ve ardından **Intune**'u seçin.
3. **Cihaz kaydı** > **Kayıt kısıtlamaları**’nı seçin.
4. Öncelik listesinde kısıtlamanın üzerine gelin.
5. Üç dikey noktayı kullanarak, önceliği listede dilediğiniz konuma sürükleyin.





