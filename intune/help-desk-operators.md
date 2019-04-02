---
title: Yardım masası sorun giderme portalı
titleSuffix: Microsoft Intune
description: Yardım masası personeli, kullanıcıların teknik sorunlarını çözmek için sorun giderme portalını kullanır.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 03/11/2019
ms.topic: troubleshooting
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: df5b20be667159689aaaee9a790c0a4c5b5864fd
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58798407"
---
# <a name="use-the-troubleshooting-portal-to-help-users-at-your-company"></a>Şirketinizdeki kullanıcılara yardımcı olmak için sorun giderme portalını kullanma

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Sorun giderme portalı, yardım masası operatörlerinin ve Intune yöneticilerinin kullanıcı yardım isteklerini ele almak için kullanıcı bilgilerini görüntülemesine izin verir. Yardım masası bulunan kuruluşlar, kullanıcı gruplarına **Yardım masası işletmeni** atayabilir. Yardım masası işletmeni rolü, **Sorun Giderme** bölmesini kullanabilir.

**Sorun Giderme** bölmesi kullanıcı kayıt sorunlarını da gösterir. Sorunun ayrıntıları ve önerilen düzeltme adımları, yönetici ve yardım masası çalışanlarının sorunları çözmesine yardımcı olabilir. Bazı kayıt sorunları burada yer almaz ve bazı hatalar için düzeltme önerileri bulunmayabilir.

Bir yardım masası işletmeni rolü atama adımları için bkz. [Intune ile rol tabanlı yönetim denetimi (RBAC)](/intune/role-based-access-control)

Bir kullanıcı, Intune ile ilgili teknik bir sorun için destekle bağlantı kurduğunda yardım masası işletmeni kullanıcının adını girer. Intune, şunlar dahil olmak üzere pek çok katman 1 sorununu çözmeye yardımcı veri sunar:

- Kullanıcı durumu
- Atamalar
- Uyumluluk sorunları
- Cihaz yanıt vermiyor
- Cihaz VPN veya Wi-Fi ayarlarını alamıyor
- Uygulama yükleme hatası

## <a name="to-review-troubleshooting-details"></a>Sorun giderme ayrıntılarını gözden geçirmek için

Sorun giderme bölmesinde **Kullanıcı seçin**’e tıklayarak kullanıcı bilgilerini görüntüleyin. Kullanıcı bilgileri, kullanıcıların ve cihazlarının geçerli durumunu anlamanıza yardımcı olabilir.  

1. [Azure portal](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Sorun gider**’i seçin.
4. Sorun gidermek üzere bir kullanıcı belirlemek için **Seçin**’e tıklayın.
5. Adını veya e-posta adresini yazarak bir kullanıcı seçin. Tıklayın **seçin**. Kullanıcı için sorun giderme bilgileri, Sorun Giderme bölmesinde görüntülenir. Bilgiler aşağıdaki tablolarda açıklanmıştır.

> [!Note]  
> **Sorun giderme** bölmesine tarayıcınızı [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting) adresine yönlendirerek de erişebilirsiniz.

## <a name="areas-of-troubleshooting-dashboard"></a>Sorun giderme panosunun alanları

Kullanıcı bilgilerini gözden geçirmek için **Sorun Giderme** bölmesini kullanabilirsiniz.

![](/intune/media/troubleshooting-dash.png)

| Alan | Ad | Açıklama |
| ---  | ---  | ---         |
| 1.   | Hesap durumu  | Geçerli Intune kiracısının durumunu **Etkin** veya **Etkin Değil** olarak gösterir.       |
| 2.   | Kullanıcı seçimi  | Seçili kullanıcının adı. Yeni bir kullanıcı seçmek için **Kullanıcı değiştir**’e tıklayın.       |
| 3.   | Kullanıcı durumu  | Kullanıcının Intune lisansı, cihaz sayısı, cihazların uyumluluk durumu, uygulama sayısı ve uygulamaların uyumluluk durumunu görüntüler.       |
| 4.   | Kullanıcı bilgileri  | Bölmede gözden geçirmek istediğiniz ayrıntıları seçmek için listeyi kullanın. <br>Şunları seçebilirsiniz: <ul><li>İstemci uygulamaları<li>Uyumluluk ilkeleri<li> Yapılandırma ilkeleri<li>Uygulama koruma ilkeleri <li>Kayıt kısıtlamaları</ul>      |
| 5.   | Grup üyeliği  | Seçili kullanıcının üyesi olduğu geçerli grupları gösterir.       |

<!-- this section needs to be updated

## Client apps reference

The apps that are running devices
- managed by Intune and Azure Active Directory (AD) 
- owned by users managed by Intune and Azure Active Directory (AD).

### Properties

The properties of client apps.

| Property      | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Name          | The name of the application.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| OS            | The operating system installed on the device.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Type          | You can choose an assignment type for each app.  <br> **Available** - Users install the app from the Company Portal app or website.  <br> **Not Applicable** - The app is not installed or shown in the Company Portal. <br> **Uninstall** - The app is uninstalled from devices in the selected groups.  <br> **Available with or without enrollment** - Assign this app to groups of users whose devices are not enrolled with Intune. |
| Last Modified | The name of the type of device.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

### Devices

Devices managed by Intune or by users managed by Intune or Azure AD.

| Property           | Description                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Device name        | The name of the type of device.                                                                                                     |
| Managed by         | The timestamp the policy was modified.                                                                                              |
| Azure AD join type | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Ownership          | The type of device ownership (**Company**, **Personal**, or **Unknown**).                                               |
| Intune compliant   | The name of the type of device.                                                                                                     |
| Azure AD compliant | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| App install | Denotes whether an app install failure or success has occurred on the individual device. |
| OS                 | The operating system installed on the device.                                                                                       |
| OS version         | The Operating System version number of the device.                                                                                  |
| Last check-in      | The name of the type of device.                                                                                                     |

### App protection status

An app protection policy is available to mobile apps that integrate with Enterprise Mobility Solution (EMS) technologies. These policies give a baseline of protection for your corporate data when it is downloaded to mobile apps, including the Office mobile apps. 

| Property    | Description                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Status      | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| App name    | The name of the application                                                           |
| Device name | The name of the type of device.                                                       |
| Device type | The name of the type of device.                                                       |
| Policies    | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| Last sync   | The timestamp of the last time the device synchronized with Intune.                   |

## App protection policies reference

An app protection policy is available to mobile apps that integrate with EMS technologies.These policies give a baseline of protection for your corporate data when it is downloaded to mobile apps, including the Office mobile apps. 

### Properties

The table summarizes app protection policies status for devices managed by Intune.

| Property    | Description                                                                                                                                |
|-------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Name        | The name of the application.                                                                                                        |
| Deployed    | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Platform    | The type of device ownership (**Company**, **Personal**, or **Unknown**).                                               |
| Enrollment  | The name of the type of device.                                                                                                     |
| Last Update | The timestamp the policy was modified.                                                                                              |

### Devices

Devices managed by Intune or by users managed by Intune or Azure AD.

| Property           | Text                                                                                                                                |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Device Name        | The name of the type of device.                                                                                                     |
| Managed By         | The timestamp the policy was modified.                                                                                              |
| Azure AD join type | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Ownership          | The type of device ownership (**Company**, **Personal**, or **Unknown**).                                               |
| Intune compliant   | The name of the type of device.                                                                                                     |
| Azure AD compliant | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Azure AD compliant | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| OS                 | The operating system installed on the device.                                                                                       |
| OS version         | The Operating System version number of the device.                                                                                  |
| Last Check in      | The name of the type of device.                                                                                                     |

## Compliance policies reference

Makes sure that the devices used to access company apps and data, comply with certain rules like using a PIN to access the device, and encryption of data stored on the device.

### Properties

The properties of the compliance policies.

| Property      | Description                                                                                                                         |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Assignment    | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Name          | The name of the application.                                                                                                        |
| OS            | The operating system installed on the device.                                                                                       |
| Policy Type   | The type of device ownership (**Company**, **Personal**, and **Unknown**).                                               |
| Last Modified | The name of the type of device.                                                                                                     |

### Devices

Devices managed by Intune or by users managed by Intune or Azure AD.

| Property           | Description                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Device name        | The name of the type of device.                                                                                                     |
| Managed by         | The timestamp the policy was modified.                                                                                              |
| Azure AD join type | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Ownership          | The type of device ownership (**Company**, **Personal**, and **Unknown**).                                               |
| Intune compliant   | The name of the type of device.                                                                                                     |
| Azure AD compliant | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| OS                 | The operating system installed on the device.                                                                                       |
| OS version         | The Operating System version number of the device.                                                                                  |
| Last check-in      | The name of the type of device.                                                                                                     |

### App protection policies

An app protection policy is available to mobile apps that integrate with EMS technologies. These policies give a baseline of protection for your corporate data when it is downloaded to mobile apps, including the Office mobile apps. 

| Property    | Description                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Status      | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| App name    | The name of the application                                                           |
| Device name | The name of the type of device.                                                       |
| Device type | The name of the type of device.                                                       |
| Policies    | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| Last sync   | The timestamp of the last time the device synchronized with Intune.                   |

## Configuration policies reference

An app configuration policy is available to mobile apps with vendor-specific configuration. 

### Properties

The properties of the configuration policies.

| Property      | Description                                                                                                                         |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Assignment    | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Name          | The name of the application.                                                                                                        |
| OS            | The operating system installed on the device.                                                                                       |
| Policy Type   | The type of device ownership (**Company**, **Personal**, or **Unknown**).                                               |
| Last Modified | The name of the type of device.                                                                                                     |

### Devices

Devices managed by Intune or by users managed by Intune or Azure AD.

| Property           | Description                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Device name        | The name of the type of device.                                                                                                     |
| Managed by         | The timestamp the policy was modified.                                                                                              |
| Azure AD join type | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Ownership          | The type of device ownership (**Company**, **Personal**, or **Unknown**).                                               |
| Intune compliant   | The name of the type of device.                                                                                                     |
| Azure AD compliant | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| OS                 | The operating system installed on the device.                                                                                       |
| OS version         | The Operating System version number of the device.                                                                                  |
| Last check-in      | The name of the type of device.                                                                                                     |


### App protection policies

An app protection policy is available to mobile apps that integrate with EMS technologies. These policies give a baseline of protection for your corporate data when it is downloaded to mobile apps, including the Office mobile apps. 

| Property    | Description                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Status      | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| App name    | The name of the application                                                           |
| Device name | The name of the type of device.                                                       |
| Device type | The name of the type of device.                                                       |
| Policies    | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| Last sync   | The timestamp of the last time the device synchronized with Intune.                   |

-->

## <a name="enrollment-failure-reference"></a>Kayıt hatası başvurusu

Kayıt Hataları tablosu, başarısız olan kayıt denemelerini listeler. Aşağıdaki tabloda listelenen bir cihaz, daha sonra başka bir denemede başarılı olarak kaydolmuş olabilir. Bazı başarısız denemeler listelenmemiş olabilir. Hataların tümünde geçiş bilgileri bulunmaz.

| Tablo sütunu | Açıklama |
|-------------|----------|
| Kayıt başlangıç | Kullanıcının kaydı ilk kez başlattığı saat. |
| İşletim Sistemi | Cihazın işletim sistemi. |
| İşletim sistemi sürümü | Cihazın işletim sistemi sürümü. |
| hata | Hatanın nedeni. |

### <a name="failure-details"></a>Hata ayrıntıları

Bir hata satırını seçtiğinizde daha fazla ayrıntı sağlanır.

| Section | Açıklama |
|-------------|----------|
| Hata ayrıntıları | Hatanın daha ayrıntılı bir açıklaması. |
| Toplam düzeltme sayısı | Hatayı gidermek için önerilen adımlar. Bazı hataların düzeltmeleri olmayabilir. |
| Kaynaklar (İsteğe bağlı) | Daha fazla bilgi için bağlantılar veya portaldaki eylem alanları. |

### <a name="enrollment-errors"></a>Kayıt hataları

| Hata | Ayrıntılar |
|-------------|----------|
| iOS Zaman Aşımı veya Hatası | Cihaz ve Intune arasında, kullanıcının kayıt için çok fazla süre harcaması nedeniyle oluşan zaman aşımı. |
| Kullanıcı bulunamadı veya lisanslı değil | Kullanıcının bir lisansı eksik veya kullanıcı hizmetten kaldırılmış. |
| Cihaz zaten kayıtlı | Birisi, başka bir kullanıcı için kayıtlı olan bir cihazı Şirket Portalı'nı kullanarak kaydetmeye çalıştı. |
| Intune'a eklenmedi | Intune mobil cihaz yönetimi (MDM) yetkilisi henüz yapılandırılmamışken bir kayıt girişiminde bulunuldu. |
| Kayıt yetkilendirmesi başarısız oldu | Şirket portalının eski bir sürümü kullanılarak bir kayıt girişiminde bulunuldu. |
| Cihaz desteklenmiyor | Cihaz, Intune kaydı için en düşük gereksinimleri karşılamıyor. |
| Kayıt kısıtlamaları karşılanmadı | Bu kayıt, yönetici tarafından yapılandırılmış bir kayıt kısıtlaması nedeniyle engellendi. |
| Cihaz sürümü çok düşük | Yönetici, daha yüksek bir cihaz sürümü gerektiren bir kayıt kısıtlama yapılandırdı. |
| Cihaz sürümü çok yüksek | Yönetici, daha düşük bir cihaz sürümü gerektiren bir kayıt kısıtlama yapılandırdı. |
| Cihaz olarak kişisel kaydedilemiyor. | Yönetici kişisel kayıtları engellemek için bir kayıt kısıtlama yapılandırmış ve başarısız cihaza şirkete önceden tanımlanmış değildi. |
| Engellenen cihaz platformu | Yönetici bu cihazın platform engelleyen bir kayıt kısıtlama yapılandırdı. |
| Toplu belirteç süresi doldu | Sağlama Paketi toplu belirteç süresi doldu. |
| AutoPilot cihaz veya ayrıntılar bulunamadı | Autopilot cihazı kaydetmeye çalışırken bulunamadı. |
| AutoPilot profili bulunamadı veya atanmadı | Cihaz etkin Autopilot profili yok. |
| Beklenmeyen AutoPilot kayıt yöntemi | Cihaz, izin verilen olmayan bir yöntem kullanılarak kaydetmeye çalıştı. |
| Autopilot cihaz kaldırıldı | Cihaz kaydetmeye çalıştıklarında bu hesap için Autopilot programından kaldırıldı. |
| Cihaz sınırına ulaşıldı | Bu kayıt, yönetici tarafından yapılandırılmış bir cihaz sınırı nedeniyle engellendi. |
| Apple ekleme işlemi | Intune bir Apple MDM anında iletme sertifikası eksik olduğu veya sertifikanın süresi dolduğu için tüm iOS cihazlarının kaydı dönemde engellendi. |
| Cihaz önceden kayıtlı değil | Kurumsal önceden şirkete ait olarak kaydedilmediğinden tüm kişisel kayıtlar bir yönetici tarafından engellendi. |
| Özellik desteklenmiyor | Kullanıcı büyük olasılıkla Intune yapılandırmanız ile uyumlu olmayan bir yöntem aracılığıyla kaydolmaya çalışıyordu. |

## <a name="collect-available-data-from-mobile-device"></a>Mobil cihazdan kullanılabilir verileri toplama

Kullanıcının cihaz sorunlarını giderirken cihaz verilerini toplamaya yardımcı olması için aşağıdaki kaynakları kullanın:
  - [iOS kayıt hatalarını BT yöneticinize gönderme](/intune-user-help/send-errors-to-your-it-admin-ios)
  - [Ayrıntılı günlük kaydı ile şirketinizin destek birimine cihaz sorunlarını çözmede yardımcı olma](/intune-user-help/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android)
  - [USB kablosu kullanarak Android günlüklerini şirketinizin destek birimine gönderme](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
  - [Android tanılama veri günlüklerini e-posta kullanarak BT yöneticinize gönderme](/intune-user-help/send-logs-to-your-it-admin-by-email-android)
  - [Android kayıt hatalarını BT yöneticinize gönderme](/intune-user-help/send-enrollment-errors-to-your-it-administrator-android)

## <a name="next-steps"></a>Sonraki adımlar

Kuruluş cihazınızda, mobil uygulama yönetiminde ve veri koruma görevlerinde rol tanımlamak için Rol tabanlı yönetim denetimi (RBAC) hakkında daha fazla bilgi edinebilirsiniz. Daha fazla bilgi için bkz. [Intune ile rol tabanlı yönetim denetimi (RBAC)](/intune/role-based-access-control).

Microsoft Intune’daki tüm bilinen sorunlar hakkında bilgi edinin. Daha fazla bilgi için bkz. [Microsoft Intune’da bilinen sorunlar](/intune/known-issues).

Bir destek biletini oluşturma ve gerektiğinde yardım alma hakkında bilgi edinin. [Destek alın](/intune/get-support).
