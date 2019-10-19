---
title: Microsoft Intune - Azure’da cihaz uyumluluk ilkeleri | Microsoft Docs
description: Cihaz uyumluluk ilkelerini kullanma, durum ve önem düzeylerine genel bakış, Yetkisizkullanımsüresinde durumunu kullanma, koşullu erişim ile çalışma, cihazları atanmış bir ilke olmadan işleme ve Azure portal ve uyumluluk farklılıkları ile çalışmaya başlama Microsoft Intune 'de klasik Portal
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c6ab0fd0220b252fe2361c0721ea026afcc232c0
ms.sourcegitcommit: 62e264052738fc7fc6f22750589fb4bee7cd9d09
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72532009"
---
# <a name="set-rules-on-devices-to-allow-access-to-resources-in-your-organization-using-intune"></a>Intune'u kullanarak kuruluşunuzdaki kaynaklara erişim izni verme amacıyla cihazlarda kural oluşturun

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Çoğu mobil cihaz yönetimi (MDM) çözümü, kullanıcıların ve cihazların bazı gereksinimleri karşılamasını şart koşarak kuruluş verilerin korunmasına yardımcı olmaktadır. Intune'da bu özellik "uyumluluk ilkeleri" olarak adlandırılır. Uyumluluk ilkeleri, kullanıcıların ve cihazların uyumlu olmak için karşılaması gereken kuralları ve ayarları tanımlar. Yönetici, koşullu erişim ile birleştirildiğinde, kuralları karşılamayan kullanıcıları ve cihazları engelleyebilirler.

Örneğin bir Intune yöneticisi şunları gerekli kılabilir:

- Son kullanıcıların mobil cihazlarındaki kuruluş verilerine erişebilmesi için parola kullanması
- Cihazda jailbreak uygulanmamış veya kök erişim izni verilmemiş olması
- Cihazdaki işletim sistemi sürümü için alt veya üst sınır
- Cihazın belirli bir tehdit düzeyinde veya altında olması

Bu özelliği, kuruluşunuzdaki cihazların uyumluluk durumunu izlemek için de kullanabilirsiniz.

> [!IMPORTANT]
> Intune, cihazdaki tüm uyumluluk değerlendirmeleri için cihaz iade zamanlamasını kullanır. [İlke ve profil yenileme döngüleri](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned) tahmini yenileme zamanlarını listeler.

<!---### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

- When the device is first determined to be noncompliant, an email with noncompliant notification is sent to the user.

- 3 days after initial noncompliance state, a follow up reminder is sent to the user.

- 5 days after initial noncompliance state, a final reminder with a notification that access to company resources will be blocked on the device in 2 days if the compliance issues are not remediated is sent to the user.

- 7 days after initial noncompliance state, access to company resources is blocked. This requires that you have Conditional Access policy that specifies that access from noncompliant devices should    be blocked for services such as Exchange and SharePoint.

### Grace Period

This is the time between when a device is first determined as
noncompliant to when access to company resources on that device is blocked. This time allows for time that the user has to resolve
compliance issues on the device. You can also use this time to create your action sequences to send notifications to the user before their access is blocked.

Remember that you need to implement Conditional Access policies in addition to compliance policies in order for access to company resources to be blocked.--->

## <a name="device-compliance-policies-work-with-azure-ad"></a>Cihaz uyumluluk ilkeleri Azure AD ile birlikte çalışır

Intune, uyumluluk uygulanmasını sağlamak için Azure Active Directory (AD) [koşullu erişim](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) (başka bir docs Web sitesi açar) kullanır. Bir cihaz Intune'a kaydedildiğinde Azure AD kayıt işlemi başlar ve Azure AD'deki cihaz bilgileri güncelleştirilir. En önemli bilgilerden biri, cihaz uyumluluk durumudur. Bu uyumluluk durumu, e-posta ve diğer kuruluş kaynaklarına erişimi engellemek veya erişime izin vermek için koşullu erişim ilkeleri tarafından kullanılır.

- [Azure Active Directory'de cihaz yönetimi nedir?](https://docs.microsoft.com/azure/active-directory/device-management-introduction) sayfasında cihazların Azure AD'ye kayıt nedeni ve yöntemi hakkında ayrıntılı bilgiler verilmektedir.

- [Koşullu erişim](conditional-access.md) ve [koşullu erişim kullanmanın yaygın yolları](conditional-access-intune-common-ways-use.md) , Intune ile ilgili olarak bu özelliği tanımlar.

## <a name="ways-to-use-device-compliance-policies"></a>Cihaz uyumluluk ilkelerini kullanma yolları

### <a name="with-conditional-access"></a>Koşullu erişimle

İlke kurallarına uyum sağlayan cihazlara e-posta ve diğer kuruluş kaynaklarına erişim verebilirsiniz. Cihazlar, ilke kurallarına uymuyorsa kuruluş kaynaklarına erişim almazlar. Bu koşullu erişimdir.

### <a name="without-conditional-access"></a>Koşullu erişim olmadan

Cihaz uyumluluk ilkelerini koşullu erişim olmadan da kullanabilirsiniz. Uyumluluk ilkelerini bağımsız olarak kullandığınızda, hedeflenen cihazlar değerlendirilir ve uyumluluk durumları raporlanır. Örneğin, kaç cihazın şifrelenmediği ya da hangi cihazlarda işletim sistemi engellemelerinin kaldırıldığı veya kök erişim izni verildiği konusunda bir rapor alabilirsiniz. Uyumluluk ilkelerini koşullu erişim olmadan kullandığınızda, kuruluş kaynaklarına hiçbir erişim kısıtlaması yoktur.

## <a name="ways-to-deploy-device-compliance-policies"></a>Cihaz uyumluluk ilkelerini dağıtma yolları

Kullanıcı gruplarındaki kullanıcılara veya cihaz gruplarındaki cihazlara uyumluluk ilkesi dağıtabilirsiniz. Bir uyumluluk ilkesi kullanıcıya dağıtıldığında, kullanıcının tüm cihazlarında uyumluluk denetimi yapılır. Windows 10 sürüm 1803 ve daha yeni cihazlarda, birincil kullanıcı cihazı *kaydetmemişse* cihaz gruplarına dağıtmanız önerilir. Bu senaryoda cihaz gruplarını kullanmak, uyumluluk raporlamasına yardımcı olur.

Intune ayrıca bir dizi yerleşik uyumluluk ilkesi ayarına da sahiptir. Aşağıdaki yerleşik ilkeler, Intune'a kaydedilen tüm cihazlarda değerlendirilir:

- **Kendisine hiçbir uyumluluk ilkesi atanmamış cihazları şöyle işaretle**: Bu özelliğin iki değeri vardır:

  - **Uyumlu**(varsayılan): güvenlik özelliği kapalı
  - **Uyumlu değil**: güvenlik özelliği açık

  Bir cihaza bir uyumluluk ilkesi atanmamışsa, bu cihaz varsayılan olarak uyumlu olarak değerlendirilir. Uyumluluk ilkeleriyle koşullu erişim kullanıyorsanız, varsayılan ayarı **uyumlu değil**olarak değiştirmeniz önerilir. Bir ilke atanmadığı için son kullanıcı uyumsuzsa, [Şirket Portalı](../apps/company-portal-app.md) `No compliance policies have been assigned` ifadesine yer verir.

- **Gelişmiş jailbreak algılama**: etkinleştirildiğinde, bu ayar IOS cihazlarının Intune 'a daha sık iade edilmesine neden olur. Bu özellik etkinleştirildiğinde cihazın konum hizmetleri kullanılır ve pil kullanımı bundan etkilenir. Kullanıcı konum verileri, Intune tarafından depolanmaz.

  Bu ayarın etkinleştirilmesi, cihazlarda şunları gerektirir:
  - Konum hizmetlerinin işletim sistemi düzeyinde etkinleştirilmesi.
  - Şirket Portalı’nın konum hizmetlerini kullanmasına izin verilmesi.
  - Cihazın jailbreak durumunun en az 72 saatte bir değerlendirilip Intune’a rapor edilmesi. Aksi takdirde cihaz uyumsuz olarak işaretlenir. Değerlendirme, Şirket Portalı uygulaması açıldığında veya cihaz fiziksel olarak 500 metre veya daha uzağa taşındığında tetiklenir. Cihazın 72 saat içinde 500 metre hareket etmemesi durumunda gelişmiş jailbreak değerlendirmesi yapılabilmesi için kullanıcının Şirket Portalı uygulamasını açması gerekir.

- **Uyumluluk durumu geçerlilik süresi (gün)** : Alınan tüm uyumluluk ilkeleri için cihazların durum rapor etme süresini girin. Bu süre içinde durum döndürmeyen cihazlar uyumsuz olarak kabul edilir. Varsayılan değer 30 gündür.

Bu ayarları izlemek için bu yerleşik ilkeleri kullanabilirsiniz. Intune ayrıca cihaz platformuna göre belirlenen farklı aralıklarla [yenileme yapar veya güncelleştirmeleri denetler](create-compliance-policy.md#refresh-cycle-times). [Microsoft Intune'daki cihaz ilkeleri ve profiller hakkında yaygın sorular, sorunlar ve çözümler](../configuration/device-profile-troubleshoot.md) sayfası iyi bir kaynaktır.

Uyumluluk raporları, cihazların durumunu denetlemek için harika bir yoldur. [Uyumluluk ilkelerini izleme](compliance-policy-monitor.md) sayfasında da yardımcı bilgiler bulunur.

## <a name="non-compliance-and-conditional-access-on-the-different-platforms"></a>Farklı platformlarda uyumsuzluk ve koşullu erişim

Aşağıdaki tabloda, bir uyumluluk ilkesi koşullu erişim ilkesi ile kullanıldığında uyumlu olmayan ayarların nasıl yönetildiği açıklanır.

---------------------------

|**İlke ayarı**| **Platform** |
| --- | ----|
| **PIN veya Parola yapılandırması** | - **Android 4,0 ve üzeri**: karantinaya alındı</br>- **Samsung KNOX Standard 4,0 ve üzeri**: karantinaya alındı</br>- **Android Enterprise**: karantinaya alındı</br></br>- **iOS 8,0 ve üzeri**: düzeltildi</br>- **MacOS 10,11 ve üzeri**: düzeltildi</br></br>- **Windows 8.1 ve üzeri**: düzeltildi</br>- **Windows Phone 8,1 ve üzeri**: düzeltildi|
| **Cihaz şifrelemesi** | - **Android 4,0 ve üzeri**: karantinaya alındı</br>- **Samsung KNOX Standard 4,0 ve üzeri**: karantinaya alındı</br>- **Android Enterprise**: karantinaya alındı</br></br>- **iOS 8,0 ve üzeri**: DÜZELTILDI (PIN ayarlanarak)</br>- **MacOS 10,11 ve üzeri**: DÜZELTILDI (PIN ayarlanarak)</br></br>- **Windows 8.1 ve üzeri**: uygulanamaz</br>- **Windows Phone 8,1 ve üzeri**: düzeltildi |
| **Jailbreak uygulanmış veya kök erişim izni verilmiş cihaz** | - **Android 4,0 ve üzeri**: karantinaya alındı (ayar değil)</br>- **Samsung KNOX Standard 4,0 ve üzeri**: karantinaya alındı (ayar değil)</br>- **Android Enterprise**: karantinaya alındı (ayar değil)</br></br>- **iOS 8,0 ve üzeri**: karantinaya alındı (ayar değil)</br>- **MacOS 10,11 ve üzeri**: uygulanamaz</br></br>- **Windows 8.1 ve üzeri**: uygulanamaz</br>- **Windows Phone 8,1 ve üzeri**: uygulanamaz |
| **E-posta profili** | - **Android 4,0 ve üzeri**: uygulanamaz</br>- **Samsung KNOX Standard 4,0 ve üzeri**: uygulanamaz</br>- **Android Enterprise**: uygulanamaz</br></br>- **iOS 8,0 ve üzeri**: karantinaya alındı</br>- **MacOS 10,11 ve üzeri**: karantinaya alındı</br></br>- **Windows 8.1 ve üzeri**: uygulanamaz</br>- **Windows Phone 8,1 ve üzeri**: uygulanamaz |
| **En düşük işletim sistemi sürümü** | - **Android 4,0 ve üzeri**: karantinaya alındı</br>- **Samsung KNOX Standard 4,0 ve üzeri**: karantinaya alındı</br>- **Android Enterprise**: karantinaya alındı</br></br>- **iOS 8,0 ve üzeri**: karantinaya alındı</br>- **MacOS 10,11 ve üzeri**: karantinaya alındı</br></br>- **Windows 8.1 ve üzeri**: karantinaya alındı</br>- **Windows Phone 8,1 ve üzeri**: karantinaya alındı |
| **En yüksek işletim sistemi sürümü** | - **Android 4,0 ve üzeri**: karantinaya alındı</br>- **Samsung KNOX Standard 4,0 ve üzeri**: karantinaya alındı</br>- **Android Enterprise**: karantinaya alındı</br></br>- **iOS 8,0 ve üzeri**: karantinaya alındı</br>- **MacOS 10,11 ve üzeri**: karantinaya alındı</br></br>- **Windows 8.1 ve üzeri**: karantinaya alındı</br>- **Windows Phone 8,1 ve üzeri**: karantinaya alındı |
| **Windows durum kanıtlama** | - **Android 4,0 ve üzeri**: uygulanamaz</br>- **Samsung KNOX Standard 4,0 ve üzeri**: uygulanamaz</br>- **Android Enterprise**: uygulanamaz</br></br>- **iOS 8,0 ve üzeri**: uygulanamaz</br>- **MacOS 10,11 ve üzeri**: uygulanamaz</br></br>- **Windows 10 ve Windows 10 Mobile**: karantinaya alındı</br>- **Windows 8.1 ve üzeri**: karantinaya alındı</br>- **Windows Phone 8,1 ve üzeri**: uygulanamaz |

---------------------------

**Düzeltildi**: cihaz işletim sistemi uyumluluğu zorluyor. Örneğin, kullanıcı bir PIN ayarlamaya zorlanır.

**Karantinaya alındı**: cihaz işletim sistemi uyumluluğu zorlamaz. Örneğin Android ve Android Kurumsal cihazlar kullanıcıyı cihazı şifrelemeye zorlamaz. Cihaz uyumsuz olduğunda aşağıdaki işlemler yapılır:

- Kullanıcı için bir koşullu erişim ilkesi geçerliyse cihaz engellenir.
- Şirket Portalı uygulaması, tüm uyumluluk sorunları hakkında kullanıcıya bildirim gönderir.

## <a name="azure-classic-portal-vs-azure-portal"></a>Klasik Azure portalı ve Azure portal karşılaştırması

Cihaz uyumluluk ilkelerini Azure portalında kullanırken göreceğiniz temel fark:

- Azure Portalı’nda uyumluluk ilkeleri, desteklenen her platform için ayrı oluşturulur
- Klasik Azure portalında ise desteklenen tüm platformlarda tek bir cihaz uyumluluk ilkesi ortak kullanılır

<!--- - In the Azure portal, you have the ability to specify actions and notifications that are initiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

- In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

[Klasik portalda](https://manage.microsoft.com) oluşturulan cihaz uyumluluk ilkeleri, [Azure portalında](https://portal.azure.com) görünmez. Ancak bunlar yine de kullanıcılara hedeflenmiştir ve klasik Intune portalı kullanılarak yönetilebilir.

Azure portalındaki yeni cihaz uyumluluk özelliklerini kullanmak için doğrudan bu portalda yeni cihaz uyumluluk ilkeleri oluşturmanız gerekir. Klasik portalda cihaz uyumluluk ilkesi atanmış bir kullanıcıya Azure portalında bir cihaz uyumluluk ilkesi atarsanız, Azure portalından gelen cihaz uyumluluk ilkeleri klasik portalda oluşturulanlardan önceliklidir.

## <a name="next-steps"></a>Sonraki adımlar

- [İlke oluşturun](create-compliance-policy.md) ve önkoşulları görüntüleyin.
- Farklı cihaz platformlarına özgü uyumluluk ayarlarını görüntüleyin:

  - [Outlook Web Access (OWA)](compliance-policy-create-android.md)
  - [Android Kurumsal](compliance-policy-create-android-for-work.md)
  - [Android](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows 10 ve üzeri](compliance-policy-create-windows.md)
  - [Windows Holographic for Business](compliance-policy-create-windows.md#windows-holographic-for-business)
  - [Windows 8.1 ve Windows Phone 8.1](compliance-policy-create-windows-8-1.md)

- [İlke varlıkları için başvuru](../reports-ref-policy.md) sayfasında Intune Veri Ambarı ilke varlıkları hakkında bilgiler yer almaktadır.
