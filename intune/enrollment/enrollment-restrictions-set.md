---
title: Microsoft Intune 'de kayıt kısıtlamalarını ayarlama
titleSuffix: ''
description: Intune 'da kaydı platforma kısıtlama ve cihaz kayıt sınırı ayarlama.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/17/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d96cd3e6496bbfde35a666bfcf4a1f6427e45173
ms.sourcegitcommit: 11ae6a37527ef5b3ac042743950254f3ef559c53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/11/2019
ms.locfileid: "72280255"
---
# <a name="set-enrollment-restrictions"></a>Kayıt kısıtlamalarını ayarlama

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bir Intune Yöneticisi olarak, cihazları aşağıdakiler dahil olmak üzere hangi cihazların Intune ile yönetime kaydolabileceğini tanımlayan kayıt kısıtlamaları oluşturabilir ve bunları yönetebilirsiniz:
- cihaz sayısı
- işletim sistemleri ve sürümleri birden çok kısıtlama oluşturabilir ve bunları farklı Kullanıcı gruplarına uygulayabilirsiniz. Farklı kısıtlamalarınız için [öncelik sırasını](#change-enrollment-restriction-priority) ayarlayabilirsiniz.

>[!NOTE]
>Kayıt kısıtlamaları güvenlik özellikleri değildir. Güvenliği aşılmış cihazlar karakterleri yanlış temsil edebilir. Bu kısıtlamalar, kötü amaçlı olmayan kullanıcılar için en iyi çaba ortadan kaldırılır.

Oluşturabileceğiniz belirli kayıt kısıtlamaları şunlar olabilir:

- En fazla kayıtlı cihaz sayısı.
- Kaydolabilir cihaz platformları:
  - Android Cihaz Yöneticisi
  - Android kurumsal iş profili
  - iOS
  - macOS
  - Windows
  - Windows Mobile
- İOS, Android Cihaz Yöneticisi, Android kurumsal iş profili, Windows ve Windows Mobile için Platform işletim sistemi sürümü. (Yalnızca Windows 10 sürümleri kullanılabilir. Windows 8.1 izin veriliyorsa bunu boş bırakın.)
  - En düşük sürüm.
  - En yüksek sürüm.
- Kişisel cihazları kısıtlama (iOS, Android Cihaz Yöneticisi, Android kurumsal iş profili, macOS, Windows ve Windows Mobile).

## <a name="default-restrictions"></a>Varsayılan kısıtlamalar

Varsayılan kısıtlamalar, hem cihaz türü hem de cihaz sınırı kayıt kısıtlamaları için otomatik olarak sağlanır. Varsayılanlar için seçenekleri değiştirebilirsiniz. Varsayılan kısıtlamalar tüm kullanıcılar ve kullanıcısız kayıtlar için geçerlidir. Daha yüksek önceliklerle yeni kısıtlamalar oluşturarak bu Varsayılanları geçersiz kılabilirsiniz.

## <a name="create-a-device-type-restriction"></a>Cihaz türü kısıtlaması oluşturma

1. Azure portal oturum açın.
2. **Diğer hizmetler**' i seçin, **Intune**' u arayın ve ardından **Intune**' u seçin.
3. **Cihaz kaydı**@no__t seçin-1**Kayıt kısıtlamaları** > **kısıtlama oluşturma** > **cihaz türü kısıtlaması**.
    bir cihaz türü kısıtlaması oluşturmak için ![Ekran Cap @ no__t-1
4. **Temel bilgiler** sayfasında, kısıtlamaya bir **ad** ve isteğe bağlı bir **Açıklama**sağlayın.
5. **İleri ' yi** seçerek **Platform ayarları** sayfasına gidin.
6. **Platform**altında, bu kısıtlamanın izin vermek istediğiniz platformlar Için **izin ver** ' i seçin.
    Platform ayarlarını seçmek için ![Ekran ucu @ no__t-1
7. **Sürümler**altında, izin verilen platformların desteklemesini istediğiniz en düşük ve en yüksek sürümleri seçin. Sürüm kısıtlamaları yalnızca Şirket Portalı kaydedilmiş cihazlara uygulanır.
     Desteklenen sürüm biçimleri şunlardır:
    - Android Cihaz Yöneticisi ve Android kurumsal iş profili, ana. ikincil. Rev. Build 'yi destekler.
    - iOS, ana. Minor. Rev 'ı destekler. İşletim sistemi sürümleri Aygıt Kayıt Programı, Apple Okul Yöneticisi veya Apple Configurator uygulaması ile kaydolmasını sağlayan Apple cihazlarına uygulanmaz.
    - Windows yalnızca Windows 10 için ana. Minor. Build. Rev 'ı destekler.
    > [!Note]
    > Windows 10 kayıt sırasında Rev numarası sağlamaz, örneğin, 10.0.17134.100 içine girdiğinizde ve cihaz 10.0.17134.174 ise kayıt sırasında engellenir.

8. **Kişisel**olarak sahip olunan cihazlara izin vermek istediğiniz platformlar Için **izin ver** ' i seçin.
9. **Atamalar** sayfasına gitmek için **İleri ' yi** seçin.
10. **Dahil edilecek grupları seç** ' i seçin ve ardından bu kısıtlamaya dahil etmek istediğiniz grupları bulmak için arama kutusunu kullanın. Kısıtlama yalnızca atandığı gruplar için geçerlidir. En az bir gruba kısıtlama atamadıysanız, hiçbir etkisi olmaz. Sonra **Seç**' i seçin. 
    Platform ayarlarını seçmek için ![Ekran ucu @ no__t-1
11. **İleri ' yi** seçerek **gözden geçir + oluştur** sayfasına gidin.
12. Kısıtlamayı oluşturmak için **Oluştur** ' u seçin.
13. Yeni kısıtlama, varsayılan olarak yalnızca bir öncelik ile oluşturulur. [Önceliği değiştirebilirsiniz](#change-enrollment-restriction-priority).


## <a name="create-a-device-limit-restriction"></a>Cihaz sınırı kısıtlaması oluşturma

1. Azure portal oturum açın.
2. **Diğer hizmetler**' i seçin, **Intune**' u arayın ve ardından **Intune**' u seçin.
3. **Cihaz kaydı**@no__t seçin-1**Kayıt kısıtlamaları** > **kısıtlama oluşturma** > **cihaz sınır kısıtlaması**.
    cihaz sınırı kısıtlaması oluşturmak için ![Ekran Cap @ no__t-1
4. **Temel bilgiler** sayfasında, kısıtlamaya bir **ad** ve isteğe bağlı bir **Açıklama**sağlayın.
5. **Cihaz sınırı** sayfasına gitmek için **İleri ' yi** seçin.
6. **Cihaz sınırı**için, bir kullanıcının kaydedebileceği en fazla cihaz sayısını seçin.
    cihaz sınırı seçimi için ![Ekran Cap @ no__t-1
7. **Atamalar** sayfasına gitmek için **İleri ' yi** seçin.
8. **Dahil edilecek grupları seç** ' i seçin ve ardından bu kısıtlamaya dahil etmek istediğiniz grupları bulmak için arama kutusunu kullanın. Kısıtlama yalnızca atandığı gruplar için geçerlidir. En az bir gruba kısıtlama atamadıysanız, hiçbir etkisi olmaz. Sonra **Seç**' i seçin. 
    @no__t-Grup seçme için 0Ekran Cap @ no__t-1
11. **İleri ' yi** seçerek **gözden geçir + oluştur** sayfasına gidin.
12. Kısıtlamayı oluşturmak için **Oluştur** ' u seçin.
13. Yeni kısıtlama, varsayılan olarak yalnızca bir öncelik ile oluşturulur. [Önceliği değiştirebilirsiniz](#change-enrollment-restriction-priority).

KCG kayıtları sırasında kullanıcılar, kayıtlı cihazların sınırlarını karşıladıklarında bu bildirimleri bildiren bir bildirim görür. Örneğin, iOS 'ta:

![iOS cihaz sınırı bildirimi](./media/enrollment-restrictions-set/enrollment-restrictions-ios-set-limit-notification.png)

> [!IMPORTANT]
> Cihaz sınırı kısıtlamaları aşağıdaki Windows kayıt türleri için uygulanmaz:
> - Ortak yönetilen kayıtlar
> - GPO kayıtları
> - Azure Active Directory Birleştirilmiş kayıtlar
> - Toplu Azure Active Directory katılmış kayıtlar
> - Autopilot kayıtları
> - Cihaz kayıt yöneticisi kayıtları
>
> Cihaz sınırı kısıtlamaları, paylaşılan cihaz senaryolarında kabul edildiği için bu kayıt türleri için zorlanmaz.
> [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/device-management-azure-portal#configure-device-settings), bu kayıt türleri için sabit sınırlar ayarlayabilirsiniz.


## <a name="change-enrollment-restrictions"></a>Kayıt kısıtlamalarını değiştirme

Aşağıdaki adımları izleyerek, bir kayıt kısıtlamasının ayarlarını değiştirebilirsiniz. Bu kısıtlamalar, zaten kaydedilmiş olan cihazları etkilemez. [INTUNE bilgisayar aracısına](../fundamentals/manage-windows-pcs-with-microsoft-intune.md) kayıtlı cihazlar bu özellikle engellenmiyor.

1. Azure portal oturum açın.
2. **Diğer hizmetler**' i seçin, **Intune**' u arayın ve ardından **Intune**' u seçin.
3. **Cihaz kaydı** > **Kayıt kısıtlamaları** ' nı seçin > > **özelliklerini**değiştirmek istediğiniz kısıtlamayı seçin.
4. Değiştirmek istediğiniz ayarların yanındaki **Düzenle** ' yi seçin.
5. **Düzenle** sayfasında, istediğiniz değişiklikleri yapın ve **gözden geçir + kaydet** sayfasına ilerleyin ve ardından **Kaydet**' i seçin.


## <a name="blocking-personal-android-devices"></a>Kişisel Android cihazlarını engelleme
- Kişisel Android Cihaz Yöneticisi cihazlarını kayıttan engellerseniz, kişisel Android kurumsal iş profili cihazları yine de kayıt yapabilir.
- Varsayılan olarak, Android kurumsal iş profili cihazlarınızın ayarları, Android Cihaz Yöneticisi cihazlarınızla ilgili ayarlarınızla aynıdır. Android kurumsal iş profilinizi veya Android Cihaz Yöneticisi ayarlarınızı değiştirdikten sonra bu durum artık böyle değildir.
- Kişisel Android kurumsal iş profili kaydını engellerseniz, yalnızca şirkete ait Android cihazları Android kurumsal iş profillerine kaydedebilir.

## <a name="blocking-personal-windows-devices"></a>Kişisel Windows cihazlarını engelleme
Kişisel olarak sahip olunan Windows cihazlarının kaydını engellerseniz, Intune, her yeni Windows kayıt isteğinin bir kurumsal kayıt olarak yetkilendirildiğinden emin olmak için kontrol eder. Yetkisiz kayıtlar engellenir.

Aşağıdaki yöntemler bir Windows Kurumsal kaydı olarak yetkilendirildiği şekilde niteler:
- Kaydolan Kullanıcı bir [cihaz kayıt yöneticisi hesabı]( device-enrollment-manager-enroll.md)kullanıyor.
- Cihaz [Windows Autopilot](enrollment-autopilot.md)üzerinden kaydolur.
- Cihaz Windows Autopilot ile kaydedilir ancak Windows ayarlarından yalnızca MDM kaydı seçeneği değildir.
- Cihazın ıMEı numarası, **cihaz kaydı** >  **[Kurumsal cihaz tanımlayıcılarında](corporate-identifiers-add.md)** listelenir. (Windows Phone 8,1 için desteklenmez.)
- Cihaz, [toplu sağlama paketiyle](windows-bulk-enroll.md)kaydolur.
- Cihaz, GPO 'dan kaydolur veya [ortak yönetim IÇIN SCCM 'den otomatik kayıt](https://docs.microsoft.com/sccm/comanage/quickstart-paths#bkmk_path1)yapar.
 
Aşağıdaki kayıtlar Intune tarafından şirket olarak işaretlenir. Ancak, Intune Yöneticisi cihaz başına denetim sunmdıklarından, bunlar engellenir:
- Windows kurulumu \* [sırasında Azure Active Directory JOIN](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx)Ile [Otomatik MDM kaydı](windows-enroll.md#enable-windows-10-automatic-enrollment) .
- [Windows ayarlarından gelen Azure Active Directory JOIN](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network)Ile [Otomatik MDM kaydı](windows-enroll.md#enable-windows-10-automatic-enrollment) .
 
Aşağıdaki kişisel kayıt yöntemleri de engellenir:
- Windows ayarlarından \* ' [den Iş hesabı ekle](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network)' ye SAHIP [Otomatik MDM kaydı](windows-enroll.md#enable-windows-10-automatic-enrollment) .
- [Yalnızca Windows ayarlarından MDM kaydı]( https://docs.microsoft.com/windows/client-management/mdm/mdm-enrollment-of-windows-devices#connecting-personally-owned-devices-bring-your-own-device) seçeneği.

\*, Autopilot ile kayıtlıysa bu engellenmeyecektir.


## <a name="change-enrollment-restriction-priority"></a>Kayıt kısıtlama önceliğini değiştirme

Öncelik, bir Kullanıcı, kısıtlamalar atanmış birden çok grupta bulunduğunda kullanılır. Kullanıcılar yalnızca içinde bulundukları bir gruba atanan en yüksek öncelik kısıtlamasına tabidir. Örneğin, Ali, öncelik 5 kısıtlamalarına atandı ve ayrıca Grup B 'nin öncelik 2 kısıtlamalarına atanmasını sağlar. Ali yalnızca öncelik 2 kısıtlamalarına tabidir.

Bir kısıtlama oluşturduğunuzda, bu, varsayılan olarak yalnızca listenin üzerine eklenir.

Cihaz kaydı, hem cihaz türü hem de cihaz sınırı kısıtlamaları için varsayılan kısıtlamaları içerir. Bu iki kısıtlama, daha yüksek öncelikli kısıtlamalarla geçersiz kılınmadığı müddetçe tüm kullanıcılara uygulanır.

Varsayılan olmayan kısıtlamanın önceliğini değiştirebilirsiniz.

1. Azure portal oturum açın.
2. **Diğer hizmetler**' i seçin, **Intune**' u arayın ve ardından **Intune**' u seçin.
3. @No__t-1**kayıt kısıtlamalarını** **cihaz kaydı**' nı seçin.
4. Öncelik listesindeki kısıtlamanın üzerine gelin.
5. Üç dikey noktayı kullanarak, önceliği listede istenen konuma sürükleyin.
