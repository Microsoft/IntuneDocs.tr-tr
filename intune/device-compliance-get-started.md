---
title: Microsoft Intune - Azure’da cihaz uyumluluk ilkeleri | Microsoft Docs
description: Cihaz uyumluluk ilkelerini kullanma, durum ve önem derecesi genel bakışı, InGracePeriod durumunu kullanma, koşullu erişim ile çalışma, atanmış bir ilkesi olmayan cihazları işleme ve Azure portalı ile Microsoft Intune klasik portal arasındaki uyumluluk farkları konularına giriş
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/08/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: fbed6185abe7656c3269805d1d5ed09eccbaf05e
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59897026"
---
# <a name="set-rules-on-devices-to-allow-access-to-resources-in-your-organization-using-intune"></a>Intune'u kullanarak kuruluşunuzdaki kaynaklara erişim izni verme amacıyla cihazlarda kural oluşturun

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Çoğu mobil cihaz yönetimi (MDM) çözümü, kullanıcıların ve cihazların bazı gereksinimleri karşılamasını şart koşarak kuruluş verilerin korunmasına yardımcı olmaktadır. Intune'da bu özellik "uyumluluk ilkeleri" olarak adlandırılır. Uyumluluk ilkeleri, kullanıcıların ve cihazların uyumlu olmak için karşılaması gereken kuralları ve ayarları tanımlar. Yöneticiler, bunları koşullu erişim özellikleriyle birlikte kullanarak kuralları karşılamayan kullanıcıları ve cihazları engelleyebilir.

Örneğin bir Intune yöneticisi şunları gerekli kılabilir:

- Son kullanıcıların mobil cihazlarındaki kuruluş verilerine erişebilmesi için parola kullanması
- Cihazda jailbreak uygulanmamış veya kök erişim izni verilmemiş olması
- Cihazdaki işletim sistemi sürümü için alt veya üst sınır
- Cihazın belirli bir tehdit düzeyinde veya altında olması

Bu özelliği, kuruluşunuzdaki cihazların uyumluluk durumunu izlemek için de kullanabilirsiniz.

> [!IMPORTANT]
> Intune, cihazdaki tüm uyumluluk değerlendirmeleri için cihaz iade zamanlamasını kullanır. [Cihaz iade zamanlaması hakkında daha fazla bilgi edinin](device-profile-troubleshoot.md#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned).

<!---### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

-   When the device is first determined to be noncompliant, an email with noncompliant notification is sent to the user.

-   3 days after initial noncompliance state, a follow up reminder is sent to the user.

-   5 days after initial noncompliance state, a final reminder with a notification that access to company resources will be blocked on the device in 2 days if the compliance issues are not remediated is sent to the user.

-   7 days after initial noncompliance state, access to company resources is blocked. This requires that you have conditional access policy that specifies that access from noncompliant devices should    be blocked for services such as Exchange and SharePoint.

### Grace Period

This is the time between when a device is first determined as
noncompliant to when access to company resources on that device is blocked. This time allows for time that the user has to resolve
compliance issues on the device. You can also use this time to create your action sequences to send notifications to the user before their access is blocked.

Remember that you need to implement conditional access policies in addition to compliance policies in order for access to company resources to be blocked.--->

## <a name="device-compliance-policies-work-with-azure-ad"></a>Cihaz uyumluluk ilkeleri Azure AD ile birlikte çalışır

Intune, uyumluluk sağlanmasına yardımcı olmak için Azure Active Directory (AD) [koşullu erişim](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) (başka bir web sitesinde bulunan belgeyi açar) özelliğini kullanır. Bir cihaz Intune'a kaydedildiğinde Azure AD kayıt işlemi başlar ve Azure AD'deki cihaz bilgileri güncelleştirilir. En önemli bilgilerden biri, cihaz uyumluluk durumudur. Bu uyumluluk durumu, e-posta veya diğer kuruluş kaynaklarına erişimi engellemek veya mümkün kılmak için koşullu erişim ilkeleri tarafından kullanılır.

- [Azure Active Directory'de cihaz yönetimi nedir?](https://docs.microsoft.com/azure/active-directory/device-management-introduction) sayfasında cihazların Azure AD'ye kayıt nedeni ve yöntemi hakkında ayrıntılı bilgiler verilmektedir.

- [Koşullu erişim](conditional-access.md) ve [koşullu erişimi kullanmanın yaygın yolları](conditional-access-intune-common-ways-use.md) sayfalarında bu özelliğin Intune ile ilgili anlatılmaktadır.

## <a name="ways-to-use-device-compliance-policies"></a>Cihaz uyumluluk ilkelerini kullanma yolları

#### <a name="with-conditional-access"></a>Koşullu erişim ile

İlke kurallarına uyum sağlayan cihazlara e-posta ve diğer kuruluş kaynaklarına erişim verebilirsiniz. Cihazlar, ilke kurallarına uymuyorsa kuruluş kaynaklarına erişim almazlar. Koşullu erişim budur.

#### <a name="without-conditional-access"></a>Koşullu erişim olmadan

Cihaz uyumluluk ilkelerini koşullu erişim olmadan da kullanabilirsiniz. Uyumluluk ilkelerini bağımsız olarak kullandığınızda, hedeflenen cihazlar değerlendirilir ve uyumluluk durumları raporlanır. Örneğin, kaç cihazın şifrelenmediği ya da hangi cihazlarda işletim sistemi engellemelerinin kaldırıldığı veya kök erişim izni verildiği konusunda bir rapor alabilirsiniz. Uyumluluk ilkelerini koşullu erişim olmadan kullandığınızda, kuruluş kaynaklarına yönelik erişim kısıtlaması olmaz.

## <a name="ways-to-deploy-device-compliance-policies"></a>Cihaz uyumluluk ilkelerini dağıtma yolları

Kullanıcı gruplarındaki kullanıcılara veya cihaz gruplarındaki cihazlara uyumluluk ilkesi dağıtabilirsiniz. Bir uyumluluk ilkesi kullanıcıya dağıtıldığında, kullanıcının tüm cihazlarında uyumluluk denetimi yapılır. Windows 10 sürüm 1803 ve daha yeni cihazlarda, birincil kullanıcı cihazı *kaydetmemişse* cihaz gruplarına dağıtmanız önerilir. Bu senaryoda cihaz gruplarını kullanmak, uyumluluk raporlamasına yardımcı olur.

Intune ayrıca bir dizi yerleşik uyumluluk ilkesi ayarına da sahiptir. Aşağıdaki yerleşik ilkeler, Intune'a kaydedilen tüm cihazlarda değerlendirilir:

- **Uyumluluk ilkesi atanmamış cihazları işaretle**: Bu özelliğin iki değeri vardır:

  - **Uyumlu**: güvenlik özelliği kapalı
  - **Uyumsuz** (varsayılan): güvenlik özelliği açık

  Bir cihaza atanmış uyumluluk ilkesi yoksa, bu cihaz uyumsuz olarak değerlendirilir. Varsayılan olarak cihazlar, **Uyumsuz** olarak işaretlenir. Koşullu erişim kullanıyorsanız ayarı **Uyumlu değil** olarak değiştirmenizi öneririz. Bir ilke atanmadığı için son kullanıcı uyumsuzsa, [Şirket Portalı](company-portal-app.md) `No compliance policies have been assigned` ifadesine yer verir.

- **Gelişmiş jailbreak algılama**: Etkinleştirildiğinde bu ayar, iOS cihazların Intune’a daha sık iade edilmesine yol açar. Bu özellik etkinleştirildiğinde cihazın konum hizmetleri kullanılır ve pil kullanımı bundan etkilenir. Kullanıcı konum verileri, Intune tarafından depolanmaz.

  Bu ayarın etkinleştirilmesi, cihazlarda şunları gerektirir:
  - Konum hizmetlerinin işletim sistemi düzeyinde etkinleştirilmesi.
  - Şirket Portalı’nın konum hizmetlerini kullanmasına izin verilmesi.
  - Cihazın jailbreak durumunun en az 72 saatte bir değerlendirilip Intune’a rapor edilmesi. Aksi takdirde cihaz uyumsuz olarak işaretlenir. Değerlendirme, Şirket Portalı uygulaması açıldığında veya cihaz fiziksel olarak 500 metre veya daha uzağa taşındığında tetiklenir. Cihazın 72 saat içinde 500 metre hareket etmemesi durumunda gelişmiş jailbreak değerlendirmesi yapılabilmesi için kullanıcının Şirket Portalı uygulamasını açması gerekir.

- **Uyumluluk durumu geçerlilik süresi (gün)**: Alınan tüm uyumluluk ilkeleri için cihazların durum rapor etme süresini girin. Bu süre içinde durum döndürmeyen cihazlar uyumsuz olarak kabul edilir. Varsayılan değer 30 gündür.

Bu ayarları izlemek için bu yerleşik ilkeleri kullanabilirsiniz. Intune ayrıca cihaz platformuna göre belirlenen farklı aralıklarla [yenileme yapar veya güncelleştirmeleri denetler](create-compliance-policy.md#refresh-cycle-times). [Microsoft Intune'daki cihaz ilkeleri ve profiller hakkında yaygın sorular, sorunlar ve çözümler](device-profile-troubleshoot.md) sayfası iyi bir kaynaktır.

Uyumluluk raporları, cihazların durumunu denetlemek için harika bir yoldur. [Uyumluluk ilkelerini izleme](compliance-policy-monitor.md) sayfasında da yardımcı bilgiler bulunur.

## <a name="non-compliance-and-conditional-access-on-the-different-platforms"></a>Farklı platformlarda uyumsuzluk ve koşullu erişim

Aşağıdaki tabloda bir uyumluluk ilkesi koşullu erişim ilkesi ile kullanıldığında uyumlu olmayan ayarların nasıl yönetildiği açıklanır.

---------------------------

|**İlke ayarı**| **Platform** |
| --- | ----|
| **PIN veya Parola yapılandırması** | - **Android 4.0 ve üzeri**: Karantinaya Alındı</br>- **Samsung Knox Standard 4.0 ve üzeri**: Karantinaya Alındı</br>- **Android Kurumsal**: Karantinaya Alındı</br></br>- **iOS 8.0 ve üzeri**: Çözümlendi</br>- **macOS 10.11 ve üzeri**: Çözümlendi</br></br>- **Windows 8.1 ve üzeri**: Çözümlendi</br>- **Windows Phone 8.1 ve üzeri**: Çözümlendi|
| **Cihaz şifrelemesi** | - **Android 4.0 ve üzeri**: Karantinaya Alındı</br>- **Samsung Knox Standard 4.0 ve üzeri**: Karantinaya Alındı</br>- **Android Kurumsal**: Karantinaya Alındı</br></br>- **iOS 8.0 ve üzeri**: Çözümlendi (PIN ayarlanarak)</br>- **macOS 10.11 ve üzeri**: Çözümlendi (PIN ayarlanarak)</br></br>- **Windows 8.1 ve üzeri**: Geçerli değil</br>- **Windows Phone 8.1 ve üzeri**: Çözümlendi |
| **Jailbreak uygulanmış veya kök erişim izni verilmiş cihaz** | - **Android 4.0 ve üzeri**: Karantinaya Alındı (ayar değil)</br>- **Samsung Knox Standard 4.0 ve üzeri**: Karantinaya Alındı (ayar değil)</br>- **Android Kurumsal**: Karantinaya Alındı (ayar değil)</br></br>- **iOS 8.0 ve üzeri**: Karantinaya Alındı (ayar değil)</br>- **macOS 10.11 ve üzeri**: Geçerli değil</br></br>- **Windows 8.1 ve üzeri**: Geçerli değil</br>- **Windows Phone 8.1 ve üzeri**: Geçerli değil |
| **E-posta profili** | - **Android 4.0 ve üzeri**: Geçerli değil</br>- **Samsung Knox Standard 4.0 ve üzeri**: Geçerli değil</br>- **Android Kurumsal**: Geçerli değil</br></br>- **iOS 8.0 ve üzeri**: Karantinaya Alındı</br>- **macOS 10.11 ve üzeri**: Karantinaya Alındı</br></br>- **Windows 8.1 ve üzeri**: Geçerli değil</br>- **Windows Phone 8.1 ve üzeri**: Geçerli değil |
| **En düşük işletim sistemi sürümü** | - **Android 4.0 ve üzeri**: Karantinaya Alındı</br>- **Samsung Knox Standard 4.0 ve üzeri**: Karantinaya Alındı</br>- **Android Kurumsal**: Karantinaya Alındı</br></br>- **iOS 8.0 ve üzeri**: Karantinaya Alındı</br>- **macOS 10.11 ve üzeri**: Karantinaya Alındı</br></br>- **Windows 8.1 ve üzeri**: Karantinaya Alındı</br>- **Windows Phone 8.1 ve üzeri**: Karantinaya Alındı |
| **En yüksek işletim sistemi sürümü** | - **Android 4.0 ve üzeri**: Karantinaya Alındı</br>- **Samsung Knox Standard 4.0 ve üzeri**: Karantinaya Alındı</br>- **Android Kurumsal**: Karantinaya Alındı</br></br>- **iOS 8.0 ve üzeri**: Karantinaya Alındı</br>- **macOS 10.11 ve üzeri**: Karantinaya Alındı</br></br>- **Windows 8.1 ve üzeri**: Karantinaya Alındı</br>- **Windows Phone 8.1 ve üzeri**: Karantinaya Alındı |
| **Windows durum kanıtlama** | - **Android 4.0 ve üzeri**: Geçerli değil</br>- **Samsung Knox Standard 4.0 ve üzeri**: Geçerli değil</br>- **Android Kurumsal**: Geçerli değil</br></br>- **iOS 8.0 ve üzeri**: Geçerli değil</br>- **macOS 10.11 ve üzeri**: Geçerli değil</br></br>- **Windows 10 ve Windows 10 Mobile**: Karantinaya Alındı</br>- **Windows 8.1 ve üzeri**: Karantinaya Alındı</br>- **Windows Phone 8.1 ve üzeri**: Geçerli değil |

---------------------------

**Düzeltildi**: Cihazın işletim sistemi, uyumluluğu zorunlu kılar. Örneğin, kullanıcı bir PIN ayarlamaya zorlanır.

**Karantinaya Alındı**: Cihazın işletim sistemi, uyumluluğu zorunlu kılmaz. Örneğin Android ve Android Kurumsal cihazlar kullanıcıyı cihazı şifrelemeye zorlamaz. Cihaz uyumsuz olduğunda aşağıdaki işlemler yapılır:

  - Kullanıcı için geçerli bir koşullu erişim ilkesi varsa cihaz engellenir.
  - Şirket Portalı uygulaması, tüm uyumluluk sorunları hakkında kullanıcıya bildirim gönderir.

## <a name="azure-classic-portal-vs-azure-portal"></a>Klasik Azure portalı ve Azure portalı

Cihaz uyumluluk ilkelerini Azure portalında kullanırken göreceğiniz temel fark:

- Azure Portalı’nda uyumluluk ilkeleri, desteklenen her platform için ayrı oluşturulur
- Klasik Azure portalında ise desteklenen tüm platformlarda tek bir cihaz uyumluluk ilkesi ortak kullanılır

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are initiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

[Klasik portalda](https://manage.microsoft.com) oluşturulan cihaz uyumluluk ilkeleri, [Azure portalında](https://portal.azure.com) görünmez. Ancak bunlar yine de kullanıcılara hedeflenmiştir ve klasik Intune portalı kullanılarak yönetilebilir.

Azure portalındaki yeni cihaz uyumluluk özelliklerini kullanmak için doğrudan bu portalda yeni cihaz uyumluluk ilkeleri oluşturmanız gerekir. Klasik portalda cihaz uyumluluk ilkesi atanmış bir kullanıcıya Azure portalında bir cihaz uyumluluk ilkesi atarsanız, Azure portalından gelen cihaz uyumluluk ilkeleri klasik portalda oluşturulanlardan önceliklidir.

## <a name="next-steps"></a>Sonraki adımlar

- [İlke oluşturun](create-compliance-policy.md) ve önkoşulları görüntüleyin.
- Farklı cihaz platformlarına özgü uyumluluk ayarlarını görüntüleyin:

  - [Android](compliance-policy-create-android.md)
  - [Android Kurumsal](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows 10 ve üzeri](compliance-policy-create-windows.md)
  - [Windows 8.1 ve Windows Phone 8.1](compliance-policy-create-windows-8-1.md)

- [İlke varlıkları için başvuru](reports-ref-policy.md) sayfasında Intune Veri Ambarı ilke varlıkları hakkında bilgiler yer almaktadır.