---
title: Microsoft Intune’da kayıt kısıtlamalarını ayarlama
titlesuffix: ''
description: Intune’da platforma göre kaydı kısıtlama ve cihaz kayıt sınırı ayarlama.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: de77ad92eac4aa869aec504f1762ad6f216c74d2
ms.sourcegitcommit: bea4a81d262607c6e9dd1e26f5cd1a2faf7d051b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2018
ms.locfileid: "45602155"
---
# <a name="set-enrollment-restrictions"></a>Kayıt kısıtlamalarını ayarlama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune yöneticisi olarak, Intune ile yönetime kaydedilebilecek cihazların sayısını ve türlerini tanımlayan kayıt kısıtlamaları oluşturabilir ve bunları yönetebilirsiniz. Birden çok kısıtlama oluşturabilir ve bunları farklı kullanıcı gruplarına uygulayabilirsiniz. Farklı kısıtlamalarınız için [öncelik sırası](#change-enrollment-restriction-priority) ayarlayabilirsiniz.

>[!NOTE]
>Kayıt kısıtlamaları güvenlik özellikleri değildir. Güvenliği aşılan cihazlar karakterlerini yanlış gösterebilir. Bu kısıtlamalar, kötü amaçlı olmayan kullanıcılara yönelik olabilecek en iyi engeldir.

Özel olarak şu kayıt kısıtlamalarını oluşturabilirsiniz:

- Kayıtlı cihaz sayısı üst sınırı.
- Kaydedilebilecek cihaz platformları:
  - Android
  - Android iş profili
  - iOS
  - Mac OS
  - Windows
- iOS, Android, Android iş profili ve Windows’un platform işletim sistemi sürümü. (Yalnızca Windows 10 sürümleri kullanılabilir. Windows 8.1'e izin veriliyorsa bunu boş bırakın.)
  - En düşük sürüm.
  - En yüksek sürüm.
- Kişisel cihazları kısıtlama (yalnızca iOS, Android, Android iş profili, macOS ve Windows).

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

Aşağıdaki adımları izleyerek bir cihaz türü kısıtlamasının ayarlarını değiştirebilirsiniz. Bu kısıtlamalar, zaten kayıtlı olan cihazları etkilemez. Bu özellikle [Intune PC aracısı](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune.md) ile kaydedilen cihazlar engellenemez.

1. Azure portalında oturum açın.
2. **Diğer Hizmetler**'i seçin, **Intune** için arama yapın ve ardından **Intune**'u seçin.
3. **Cihaz kaydı** > **Kayıt kısıtlamaları**’nı seçin.
4. **Cihaz Türü Kısıtlamaları** > ayarlamak istediğiniz kısıtlamayı seçin > **Özellikler** > **Platform seçin**. Listelenen her platform için **İzin Ver** veya **Engelle**'yi seçin.
    ![Bir platforma izin verme veya platformu engelleme ekran görüntüsü](media/enrollment-restrictions-set/platform-allow-block.png)
5. **Tamam**’ı seçin.
6. **Platformları yapılandır**’ı seçin.
    ![Platform yapılandırma ekran görüntüsü](media/enrollment-restrictions-set/configure-platforms.png)
7. Listelenen platformlar için en düşük ve en yüksek **Sürümler**’i seçin. Desteklenen sürüm biçimleri:
    - Android iş profili desteği major.minor.rev.build.
    - iOS major.minor.rev destekler. İşletim sistemi sürümleri, Aygıt Kayıt Programı, Apple School Manager veya Apple Configurator uygulaması ile kaydedilen Apple cihazlar için geçerli değildir.
    - Windows, yalnızca Windows 10 için major.minor.rev.build destekler.
8. Listelenen her platformda **Kişiye ait** cihazlar için **İzin Ver** veya **Engelle**’yi seçin.
9. **Tamam**’ı seçin.

### <a name="blocking-personal-android-devices"></a>Kişisel Android cihazlarını engelleme
- Kişisel Android cihazların kaydını engellerseniz kişisel Android iş profili cihazları hala kaydedilebilir durumda olacaktır.
- Varsayılan olarak, Android iş profili cihaz ayarlarınız Android cihazlarınızın ayarlarıyla aynı olur. Android iş profili ayarlarınızı değiştirdikten sonra artık bu durum oluşmaz.
- Kişisel Android iş profili kaydını engellerseniz, yalnızca kurumsal Android cihazlar Android iş profili olarak kaydedilebilir.

### <a name="blocking-personal-windows-devices"></a>Kişisel Windows cihazlarını engelleme
Kişisel Windows cihazlarının kayıt yapmasını engellerseniz, Intune, kurumsal bir kayıt olarak yetkilendirildiğinden emin olmak için her yeni Windows kayıt isteğini denetler. Yetkilendirilmemiş kayıtlar engellenir.

Windows şirket kaydı olarak yetkilendirme için aşağıdaki yöntemler uygundur:
 - Kaydeden kullanıcı [cihaz kayıt yöneticisi hesabı]( device-enrollment-manager-enroll.md) kullanıyor.
- Cihaz [Windows AutoPilot](enrollment-autopilot.md) yoluyla kaydediliyor.
- Cihaz Windows Autopilot ile kaydediliyor ancak Windows Ayarları'ndan bir yalnızca MDM kaydı seçeneği değil.
- Cihazın IMEI numarası **Cihaz kaydı** > **[Şirket cihaz tanımlayıcıları](corporate-identifiers-add.md)**’nda listelenmiş. (Windows Phone 8.1 için desteklenmez.)
- Cihaz bir [toplu sağlama paketi](windows-bulk-enroll.md) ile kaydediliyor.
- Cihaz [ortak yönetim için SCCM’den otomatik kayıt](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview#how-to-configure-co-management.md) yoluyla kaydediliyor.
 
Aşağıdaki kayıtlar Intune tarafından şirket olarak işaretlenir ancak Intune yöneticisine cihaz başına denetim sağlamadığı için engellenir:
 - [Windows kurulumu sırasında Azure Active Directory'ye katılma](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx.md)\* ile [otomatik MDM kaydı](windows-enroll.md#enable-windows-10-automatic-enrollment).
- [Windows Ayarları'ndan Azure Active Directory'ye katılma](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-setup.md) ile [otomatik MDM kaydı](windows-enroll.md#enable-windows-10-automatic-enrollment).
 
Aşağıdaki kişisel kayıt yöntemleri de engellenir:
- [Windows Ayarları'ndan İş Hesabı ekleme](https://docs.microsoft.com/azure/active-directory/device-management-azuread-registered-devices-windows10-setup.md)\* ile [otomatik MDM kaydı](windows-enroll.md#enable-windows-10-automatic-enrollment).
- Windows Ayarları’ndan [Yalnızca MDM kaydı]( https://docs.microsoft.com/windows/client-management/mdm/mdm-enrollment-of-windows-devices#connecting-personally-owned-devices-bring-your-own-device) seçeneği.

\* Bunlar, Autopilot ile kaydedilirse engellenmez.

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
