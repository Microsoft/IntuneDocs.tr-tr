---
title: Şirket Portalı uygulamasını yapılandırma
titleSuffix: Microsoft Intune
description: Learn how you can apply company-specific branding to the Intune Company Portal app.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b750c09207b1950aa27a5f2cae1267503537b6e7
ms.sourcegitcommit: 01fb3d844958a0e66c7b87623160982868e675b0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74199205"
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>Microsoft Intune Şirket Portalı uygulamasını yapılandırma

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Microsoft Intune şirket portalı, kullanıcıların şirket verilerine eriştiği ve cihaz kaydetmek, uygulama yüklemek ve BT departmanınızdan yardım için bilgi bulmak gibi genel görevleri gerçekleştirebilecekleri yerdir. Additionally, the company portal app allows user to securely access company resources. The company portal app provides several different pages, such as Home, Apps, App details, Devices, and Device details. To quickly find apps within the Company Portal, you can filter the apps on the Apps page.

> [!IMPORTANT]
> To support Google’s Firebase Cloud Messaging (FCM), you must update your Android Company Portal app to the latest version.  

> [!Tip]
> Şirket Portalı’nı özelleştirdiğinizde, yapılandırmalar hem Şirket Portalı web sitesi hem de Şirket Portalı uygulamaları için geçerli olur. Şirket Portalı'na erişmek isteyen kullanıcılara Intune lisansı atanmış olmalıdır.

Şirket Portalı’nı özelleştirerek, son kullanıcılarınız için tanıdık ve yararlı bir deneyim sağlanmasına yardımcı olabilirsiniz. Bunun için Intune portalında **İstemci uygulamaları** > **Markalama ve özelleştirme**'yi seçip gerekli ayarları yapılandırın.

When a user is installing an iOS application from the Company Portal they will receive a prompt. This occurs when the iOS app is linked to the app store, linked to a volume-purchase program (VPP), or linked to a line-of-business (LOB) app. The prompt allows the users to accept the action or allow management of the app. The prompt will display your company name, or when your company name is unavailable, **Company Portal** will be displayed. 

> [!Note]
> Azure Kamu kullanıyorsanız, bir sorunla ilgili yardım alma sürecini başlattığında bunu nasıl paylaşacağına karar vermesi için son kullanıcıya uygulama günlükleri sunulur. Ancak Azure Kamu kullanmıyorsa, kullanıcı bir sorunla ilgili yardım alma sürecini başlattığında Windows 10 için Şirket Portalı uygulama günlüklerini doğrudan Microsoft'a gönderir. Uygulama günlüklerini Microsoft'a göndermek sorunları gidermeyi ve çözmeyi kolaylaştıracaktır. 

## <a name="company-information-and-privacy-statement"></a>Şirket bilgileri ve gizlilik bildirimi
Şirket adı, Şirket Portalı’nın başlığı olarak görüntülenir. Gizlilik bildirimini, kullanıcı gizlilik bağlantısına tıkladığında görüntülenir.

| Alan adı | Uzunluk üst sınırı | Daha fazla bilgi |
|---|---|---|
|**Şirket adı**| 40 | Bu ad Şirket Portalı'nın başlığı olarak görüntülenir ve Intune kullanıcı deneyiminin her yerinde metin olarak gösterilir. |
| **Gizlilik bildirimi URL'si** |     79     | Kullanıcılar Şirket Portalı’nda gizlilik bağlantılarına tıkladığında görüntülenecek kendi şirket gizlilik bildiriminizi belirtebilirsiniz. `<https://www.contoso.com>` biçiminde geçerli bir URL girmeniz gerekir. |

> [!NOTE]
> Consistent with Microsoft and Apple policy, we do not sell any data collected by our service to any third parties for any reason.

## <a name="support-information"></a>Destek bilgileri
Çalışanınıza Intune'la ilgili sorularında bir başvuru noktası sağlamak için şirketinizin destek bilgilerini girin.

|Alan adı|Uzunluk üst sınırı|Daha fazla bilgi|
|---|---|---|
|**Kişi adı** | 40 | This name is displayed on the **Help and Support** page. |
|**Telefon numarası** | 20 | This contact number is displayed on the **Help and Support** page to enable employees to contact you for support. |
|**E-posta adresi**| 40 | This contact address is displayed on the **Help and Support** page. `alias@domainname.com` biçiminde geçerli bir e-posta adresi girmeniz gerekir. |
|**Web sitesinin adı**| 40 | Bu ad destek web sitesi URL'si için görüntülenen kolay addır. If you specify a support website URL and no friendly name, then Go to IT website is displayed on the **Help and Support** page in the Company Portal. |
|**Web sitesi URL'si**| 150 | Kullanıcılarınızın kullanmasını istediğiniz bir destek web siteniz varsa, URL'sini burada belirtin. URL, `https://www.contoso.com` biçiminde olmalıdır. If you don't specify a URL, nothing is displayed for the support website on the **Help and Support** page in the Company Portal. |
| **Ek bilgiler**| 120 | Displayed on the **Help and Support** page. |


## <a name="company-identity-branding-customization"></a>Şirket kimliği marka özelleştirme
Şirket Portalınızı şirket logonuz, şirket adınız, tema renginiz ve arka planınızla özelleştirebilirsiniz.

### <a name="theme-color-and-logo-in-the-company-portal"></a>Şirket Portalı’nda tema rengi ve logo
Şirket Portalı’na bir tema rengi uygulayın. Standart renklerden birini seçin veya özel renk için alt basamaklı onaltılık kodu girin.

|Alan adı|Daha fazla bilgi|
|---|---|
|**Standart renklerden birini seçin veya altı basamaklı onaltılık kod girin**| Bir renk seçmek için **Standart**’ı seçin. Onaltılık kod değerine göre belirli bir renk belirtmek için **Özel**’i seçin.|
|**Tema rengi seçin**| Şirket Portalı’na uygulamak için bir tema rengi seçin. Standart renk seçebilir veya belirli bir onaltılık kodu girebilirsiniz. |
|**Görüntüleme**| Hangisinin görüntüleneceğini seçin: **Şirket logosu ve adı**, **Yalnızca şirket logosu** veya **Yalnızca şirket adı**. |
|**Şirket logonuzu karşıya yükleyin**|Size ait Şirket Portalı’nda görüntülenmek üzere şirket logonuzu yükleyebilirsiniz. En yüksek kontrast düzeyini sağlamak için metin renginin otomatik olarak seçildiğini unutmayın. En iyi görünümü elde etmek için saydam bir arka plana sahip bir logo yükleyin.<p><ul><li>En büyük görüntü boyutu: 400 piksel x 400 piksel</li><li>En büyük dosya boyutu: 750 KB</li><li>Dosya türü: PNG, JPG veya JPEG</li></ul>|

Logo yüklendikten sonra önizleme alanında tema rengiyle logo görüntülenir. Şirketinizin adını görüntülemeyi seçerseniz bu ad, Şirket Portalı’nda siyah veya beyaz renkte görüntülenir. Tema renginizle en yüksek kontrastı sağlayan renk otomatik olarak seçilir. Ekrandaki önizleme alanında şirketinizin adı görüntülenmez. 

### <a name="logo-to-use-on-white-or-light-backgrounds"></a>Beyaz veya açık renk arka planda kullanılacak logo
Beyaz veya açık renk arka planlarda en iyi görünecek logoyu seçin.

|Alan adı|Daha fazla bilgi|
|---|---|
|**Logonuzu karşıya yükleyin**| Bu seçeneğin kullanılabilmesi için şirket logosunu göstermeyi seçmiş olmalısınız. En iyi görünümü elde etmek için saydam bir arka plana sahip bir logo yükleyin.<p><ul><li>En büyük görüntü boyutu: 400 piksel x 400 piksel</li><li>En büyük dosya boyutu: 750 KB</li><li>Dosya türü: PNG, JPG veya JPEG</li></ul>|

### <a name="brand-image-for-company-portal"></a>Şirket Portalı için marka imajı

Şirket markanızı yansıtan bir marka imajı kullanın. Değişikliklerinizi kaydettikten sonra, yapılandırmalarınızın nasıl görüneceğine bakmak için dikey pencerenin üst kısmındaki Intune Web Portalı’nda **Ayarlarınızın önizlemesini görüntüleyin** öğesini seçebilirsiniz. Marka imajını Intune Web Portalı’nda değil, yalnızca bir iOS cihazında görüntüleyebileceğinizi unutmayın. 

|Alan adı|Daha fazla bilgi|
|---|---|
|**Marka imajınızı karşıya yükleyin**| Bu seçenek, marka imajı görüntülemenizi sağlar. iOS Şirket Portalı'nda kullanıcı profili sayfasında arka plan görüntüsü olarak görünür.<p><ul><li>Recommended image width: Greater than 1125px (required to be at least 650 px)</li><li>En yüksek görüntü boyutu: 1,3 MB</li><li>Dosya türü: PNG, JPG veya JPEG</li></ul>|

Doğru bir marka imajı sayesinde şirket markanızı güçlü bir şekilde tanıtarak Şirket Portalı’nda kullanıcı güvenini artırabilirsiniz. Aşağıda, Şirket Portalı için imaj elde etme, seçme ve iyileştirme hakkında bazı ipuçları bulabilirsiniz. 

- Pazarlama veya sanat departmanınıza ulaşın. Bu departmanların elinde zaten onaylanmış birkaç marka imajı olabilir. Departmanlar ayrıca görüntüleri ihtiyaca göre iyileştirme konusunda size yardım edebilir. 

- Yatay ve dikey kompozisyonları değerlendirin. İmajın odak noktasını çevreleyen arka planın yeterli olmasına dikkat edin. İmaj cihaz boyutuna, hizalamasına ve platformuna göre farklı şekillerde kırpılabilir. 

- Sıradan, hazır bir imaj seçmekten kaçının. İmaj, şirketinizin markasını yansıtmalı ve kullanıcılara yakın hissettirmelidir. Elinizde bir imaj yoksa, kullanıcılarınıza hiçbir şey ifade etmeyen sıradan bir görüntü kullanmak yerine hiçbir şey kullanmamak daha iyi olacaktır. 

- Gereksiz meta verileri kaldırın. İmaj dosyası; kamera profili, coğrafi konum, başlık, açıklama gibi meta veriler içerebilir. Kaliteyi korumak ve dosya boyutu sınırını aşmamak için bir görüntü iyileştirme aracını kullanarak bu bilgileri kaldırın. 

Intune'da marka imajı eklendikten veya değiştirildikten sonra son kullanıcıların bu değişikliği iOS cihazlarında görebilmeleri için Şirket Portalı'nın başlangıçta değişikliği algılaması ve ardından marka imajının görüntülenmesi için yeniden başlatılması gerekir. 

### <a name="brand-image-examples"></a>Marka imajı örnekleri

Aşağıdaki görüntüde örnek bir iPad marka imajı gösterilmektedir:

![Örnek iPhone marka imajının ekran görüntüsü](./media/company-portal-app/company-portal-app-03.png)

Aşağıdaki görüntüde örnek bir iPhone marka imajı gösterilmektedir:

![Örnek iPad marka imajının ekran görüntüsü](./media/company-portal-app/company-portal-app-02.png)

## <a name="privacy-statement-customization"></a>Privacy statement customization

You can customize the privacy statement that appears for your organization on managed iOS devices. This message lists the items that your organization can't see or do on managed iOS devices.

Under **Company Portal customization** > **Device management and privacy message**, you can:

- Accept the **Default** to use the list as shown, or
- Choose **Custom** to customize the the list of items that your organization can’t see or do on managed iOS devices. You can use [markdown](https://daringfireball.net/projects/markdown/) to add bullets, bolding, italics, and links.

## <a name="company-portal-derived-credentials-for-ios-devices"></a>Company Portal derived credentials for iOS devices
Intune supports Personal Identity Verification (PIV) and Common Access Card (CAC) Derived Credentials in partnership with credential providers DISA Purebred, Entrust Datacard, and Intercede. End users will go through additional steps post-enrollment of their iOS device to verify their identity in the Company Portal application. Derived Credentials will be enabled for users by first setting up a credential provider for your tenant, then targeting a profile that uses Derived Credentials to users or devices.

> [!NOTE]
> The user will see instructions about derived credentials based on the link that you have specified via Intune.

For more information about derived credentials for iOS devices, see [Use derived credentials in Microsoft Intune](~/protect/derived-credentials.md).

## <a name="dark-mode-for-ios-company-portal"></a>Dark Mode for iOS Company Portal

Dark Mode is available for the iOS Company Portal. Users can download company apps, manage their devices, and get IT support in the color scheme of their choice based on device settings. The iOS Company Portal will automatically match the end user's device settings for dark or light mode. 

## <a name="windows-company-portal-keyboard-shortcuts"></a>Windows Şirket Portalı klavye kısayolları

Son kullanıcılar, Windows Şirket Portalı’nda klavye kısayollarını (hızlandırıcılar) kullanarak gezinti, uygulama ve cihaz eylemlerini tetikleyebilirler.

Windows Şirket Portalı uygulamasında aşağıdaki kısayollar kullanılabilir.

| Alan | Description | Keyboard shortcut |
|:------------------:|:--------------:|:-----------------:|
| Gezinti menüsü | Gezinti | Alt+M |
|  | Giriş | Alt+H |
|  | Tüm uygulamalar | Alt+A |
|  | Yüklenen uygulamalar | Alt+I |
|  | Geri bildirim gönder | Alt+F |
|  | Profilim | Alt+U |
|  | Ayarlar | Alt+T |
| Giriş - Cihaz kutucuğu | Yeniden Adlandır | F2 |
|  | Kaldır | Ctrl+D veya Delete |
|  | Erişimi denetle | Ctrl+M veya F9 |
| Cihaz ayrıntıları | Yeniden Adlandır | F2 |
|  | Kaldır | Ctrl+D veya Delete |
|  | Erişimi denetle | Ctrl+M veya F9 |
| Uygulama ayrıntıları | Yükle | Ctrl+I |
| Cihazlar | Kullanılabilir | Ctrl+D |

Son kullanıcılar, Windows Şirket Portalı uygulamasında kullanılabilen kısayolları da görebilir.

![Windows Şirket Portalı'nda kullanılabilen kısayolların ekran görüntüsü](./media/company-portal-app/company-portal-app-01.png)

## <a name="user-self-service-device-actions-from-the-company-portal"></a>User self-service device actions from the Company Portal

Users can perform actions on their local or remote devices via the Company Portal app or Website. The actions that a user can perform varies based on device platform and configuration. In all cases, the remote device actions can only be performed by device’s Primary User.
- **Retire** – Removes the device from Intune Management. In the company portal app and website, this shows as **Remove**.
- **Wipe** – This action initiates a device reset. In the company portal website this is shown as **Reset**, or **Factory Reset** in the iOS Company Portal App.
- **Rename** – This action changes the device name that the user can see in the Company Portal. It does not change the local device name, only the listing in the Company Portal.
- **Sync** – This action initiates a device check-in with the Intune service. This shows as **Check Status** in the Company Portal.
- **Remote Lock** – This locks the device, requiring a PIN to unlock it.
- **Reset Passcode** – This action is used to reset device passcode. On iOS devices the passcode will be removed and the end user will be required to enter a new code in settings. On supported Android devices, a new passcode is generated by Intune and temporarily displayed in the Company Portal.
- **Key Recovery** – This action is used to recover a personal recovery key for encrypted macOS devices from the Company Portal website. 

### <a name="self-service-actions"></a>Self Service Actions

Some platforms and configurations do not allow self-service device actions. This table below provides further details about self service actions:

|  | Windows 10<sup>(3)</sup> | iOS/iPadOS<sup>(3)</sup> | MacOS<sup>(3)</sup> | Android<sup>(3)</sup> |
|----------------------|--------------------------|-------------------|-----------------------------------|-------------------------|
| Devre dışı bırakma | Available<sup>(1)</sup> | Kullanılabilir | Kullanılabilir | Available<sup>(7)</sup> |
| Silme | Kullanılabilir | Available<sup>(5)</sup> | NA | Available<sup>(7)</sup> |
| Rename<sup>(4)</sup> | Kullanılabilir | Kullanılabilir | Kullanılabilir | Kullanılabilir |
| Sync | Kullanılabilir | Kullanılabilir | Kullanılabilir | Kullanılabilir |
| Uzaktan Kilitleme | Windows Phone only | Kullanılabilir | Kullanılabilir | Kullanılabilir |
| Reset Passcode | Windows Phone only | Available<sup>(8)</sup> | NA | Available<sup>(6)</sup> |
| Key Recovery | NA | NA | Available<sup>(2)</sup> | NA |

<sup>(1)</sup> **Retire** is always blocked on Azure AD Joined Windows devices.<br>
<sup>(2)</sup> **Key Recovery** for MacOS is only available via the Web Portal.<br>
<sup>(3)</sup> All remote actions are disabled if using a Device Enrollment Manager enrollment.<br>
<sup>(4)</sup> **Rename** only changes the device name in the Company Portal app or Web Portal, not on the device.<br>
<sup>(5)</sup> **Wipe** is not available on User Enrolled iOS devices.<br>
<sup>(6)</sup> **Reset Passcode** is not supported on some Android and Android Enterprise configurations. For more information, see [Reset or remove a device passcode in Intune](../remote-actions/device-passcode-reset.md).<br>
<sup>(7)</sup> **Retire** and **Wipe** are not available on Android Enterprise Device Owner scenarios (COPE, COBO, COSU).<br> 
<sup>(8)</sup> **Reset Passcode** is not supported on User Enrolled iOS devices.

## <a name="next-steps"></a>Sonraki adımlar

- [Microsoft Intune kullanarak Windows 10 Şirket Portalı uygulamasını el ile ekleme](company-portal-app.md)
