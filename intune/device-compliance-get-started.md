---
title: Microsoft Intune - Azure’da cihaz uyumluluk ilkeleri | Microsoft Docs
description: Kullanımı cihaz uyumluluk ilkelerini, koşullu erişim, Azure portalında uyumluluk farkları ve atanmış bir ilkesi olmayan cihazları işleme ile çalışma Ingraceperiod durumunu kullanma, durum ve önem derecesi genel bakış kullanmaya başlayın ve Klasik portalda Intune
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
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423527"
---
# <a name="set-rules-on-devices-to-allow-access-to-resources-in-your-organization-using-intune"></a>Cihazları Intune kullanarak kuruluşunuzda kaynaklara erişim izni vermek için kuralları ayarlayın

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Çok sayıda mobil cihaz Yönetimi (MDM) çözümleri, kullanıcılara ve cihazlara bazı gereksinimlerini gerektirerek kurumsal verilerin korunmasına yardımcı olur. Intune, bu özellik "uyumluluk ilkeleri" olarak adlandırılır. Uyumluluk ilkeleri, kullanıcılara ve cihazlara uyumlu olabilmesi için karşılaması gereken ayarları ve kuralları tanımlar. Koşullu erişim ile birlikte kullanıldığında, yöneticilerin kullanıcıları ve kurallara uymayan cihazları engelleyebilirsiniz.

Örneğin, bir Intune Yöneticisi gerektirebilir:

- Son kullanıcılar, mobil cihazlardaki Kurumsal verilere erişmek için bir parola kullanın.
- Jailbreak uygulanmış veya kök erişim izni verilmiş cihaz değil
- Bir cihazın minimum veya maksimum işletim sistemi sürümü
- Cihazın, veya bu düzeyin altında bir tehdit düzeyi olmasını

Bu özellik, kuruluşunuzdaki cihazların uyumluluk durumunu izlemek için de kullanabilirsiniz.

> [!IMPORTANT]
> Intune, cihazda tüm uyumluluk değerlendirme için cihaz iade zamanlama izler. [Cihaz iade zamanlama hakkında daha fazla bilgi](device-profile-troubleshoot.md#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned).

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

## <a name="device-compliance-policies-work-with-azure-ad"></a>Cihaz uyumluluk ilkelerini Azure AD ile çalışma

Intune, Azure Active Directory (AD) kullanır [koşullu erişim](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) (başka bir docs web sitesini açar) yardımcı uyumluluğu zorlamak için. Ne zaman Intune, Azure AD kayıt işlemi bir cihaz kaydolursa başlar ve Azure AD'de cihaz bilgilerini güncelleştirilir. En önemli bilgilerden biri, cihaz uyumluluk durumudur. Bu uyumluluk durumu, engellemek veya e-posta erişimine izin vermek için koşullu erişim ilkeleri ve diğer kuruluş kaynaklarına tarafından kullanılır.

- [Azure Active Directory'de cihaz yönetimi nedir](https://docs.microsoft.com/azure/active-directory/device-management-introduction) neden ve nasıl Azure AD'de kayıtlı cihazlar üzerindeki harika bir kaynaktır.

- [Koşullu erişim](conditional-access.md) ve [koşullu erişim kullanmanın yaygın yolları](conditional-access-intune-common-ways-use.md) Intune'a bağlantılı olarak, bu özellik açıklanmaktadır.

## <a name="ways-to-use-device-compliance-policies"></a>Cihaz uyumluluk ilkelerini kullanma yolları

#### <a name="with-conditional-access"></a>Koşullu erişim ile

İlke kurallarına uyum cihazlar için e-posta ve diğer kuruluş kaynaklarına, bu cihazlara erişim verebilirsiniz. Ardından cihazların, ilke kurallarına uyum yoksa, kuruluş kaynaklarına erişiminiz olmaz. Koşullu erişim budur.

#### <a name="without-conditional-access"></a>Koşullu erişim olmadan

Cihaz uyumluluk ilkelerini koşullu erişim olmadan da kullanabilirsiniz. Uyumluluk ilkelerini bağımsız olarak kullandığınızda, hedeflenen cihazlar değerlendirilir ve uyumluluk durumları raporlanır. Örneğin, kaç cihazın şifreli olmayan ya da hangi cihazların, jailbreak uygulanmış veya kök erişim izni verilmiş bir rapor alabilirsiniz. Uyumluluk ilkelerini koşullu erişim olmadan kullandığınızda, tüm kuruluş kaynaklarına yönelik erişim kısıtlaması yok.

## <a name="ways-to-deploy-device-compliance-policies"></a>Cihaz uyumluluk ilkelerini dağıtma yolları

Kullanıcı gruplarındaki kullanıcılara veya cihaz gruplarındaki cihazlara uyumluluk ilkesi dağıtabilirsiniz. Bir uyumluluk ilkesi kullanıcıya dağıtıldığında, kullanıcının tüm cihazlarında uyumluluk denetimi yapılır. Windows 10 sürüm 1803 ve daha yeni cihazlarda, birincil kullanıcı cihazı *kaydetmemişse* cihaz gruplarına dağıtmanız önerilir. Bu senaryoda cihaz gruplarını kullanmak, uyumluluk raporlamasına yardımcı olur.

Intune Ayrıca, bir dizi yerleşik uyumluluk İlkesi ayarları içerir. Aşağıdaki yerleşik ilkeleri, Intune'a kayıtlı tüm cihazlara değerlendirme:

- **Cihaz uyumluluk ilkesi atanmamış olarak işaretlemek**: Bu özelliğin iki değeri vardır:

  - **Uyumlu**: güvenlik özelliği kapalı
  - **Uyumsuz** (varsayılan): güvenlik özelliği açık

  Bir cihaza atanmış uyumluluk ilkesi yoksa, bu cihaz uyumsuz olarak değerlendirilir. Varsayılan olarak cihazlar, **Uyumsuz** olarak işaretlenir. Koşullu erişim kullanıyorsanız ayarını değiştirmek önerilen **uyumlu**. Son kullanıcı bir ilke atanmadığından uyumlu değilse, ardından [Şirket portalı uygulamasını](company-portal-app.md) gösterir `No compliance policies have been assigned`.

- **Gelişmiş jailbreak algılama**: Bu ayar etkinleştirildiğinde, iOS cihazlarını Intune ile daha sık iade neden olur. Bu özellik etkinleştirildiğinde cihazın konum hizmetleri kullanılır ve pil kullanımı bundan etkilenir. Kullanıcı konum verileri Intune tarafından saklanmaz.

  Bu ayarın etkinleştirilmesi, cihazlarda şunları gerektirir:
  - İşletim sistemi düzeyinde konum Hizmetleri'ni etkinleştirin.
  - Şirket portalının konum hizmetleri kullanmasına izin verin.
  - Cihazın jailbreak durumunun en az 72 saatte bir değerlendirilip Intune’a rapor edilmesi. Aksi takdirde cihaz uyumsuz olarak işaretlenir. Değerlendirme, Şirket portalı uygulamasını açarak veya cihazı 500 ölçümleri veya daha fazla fiziksel olarak taşıyarak tetiklenir. Cihaz 500 ölçümleri 72 saat içinde hareket etmediği, kullanıcı Gelişmiş jailbreak sonu değerlendirme için Şirket portalı uygulamasını açması gerekir.

- **Uyumluluk durumu geçerlilik süresi (gün)**: Cihazların alınan tüm uyumluluk ilkeleri için durum rapor bir süre girin. Bu süre içinde durum döndürmeyen cihazlar uyumsuz olarak kabul edilir. Varsayılan değer 30 gündür.

Bu ayarları izleyin, bu yerleşik ilkeler kullanabilirsiniz. Intune ayrıca [yeniler ya da güncelleştirmeleri denetler](create-compliance-policy.md#refresh-cycle-times) cihaz platformuna bağlı olarak farklı aralıklarla. [Genel Sorular, sorunlar ve çözümleri cihaz ilkeleri ve profilleri Microsoft Intune](device-profile-troubleshoot.md) iyi bir kaynaktır.

Uyumluluk raporları, cihazların durumunu denetlemek için harika bir yoldur. [Uyumluluk ilkelerini izleme](compliance-policy-monitor.md) bazı yönergeler içerir.

## <a name="non-compliance-and-conditional-access-on-the-different-platforms"></a>Uyumsuzluk ve farklı platformlarda koşullu erişim

Aşağıdaki tabloda bir uyumluluk ilkesi koşullu erişim ilkesi ile kullanıldığında uyumlu olmayan ayarların nasıl yönetildiği açıklanır.

---------------------------

|**İlke ayarı**| **Platform** |
| --- | ----|
| **PIN veya Parola yapılandırması** | - **Android 4.0 ve üzeri**: Karantinaya Alındı</br>- **Samsung Knox Standard 4.0 ve üzeri**: Karantinaya Alındı</br>- **Android Kurumsal**: Karantinaya Alındı</br></br>- **iOS 8.0 ve üstü**: Çözümlendi</br>- **macOS 10.11 ve üzeri**: Çözümlendi</br></br>- **Windows 8.1 ve üzeri**: Çözümlendi</br>- **Windows Phone 8.1 ve üzeri**: Çözümlendi|
| **Cihaz şifrelemesi** | - **Android 4.0 ve üzeri**: Karantinaya Alındı</br>- **Samsung Knox Standard 4.0 ve üzeri**: Karantinaya Alındı</br>- **Android Kurumsal**: Karantinaya Alındı</br></br>- **iOS 8.0 ve üstü**: Çözümlendi (PIN ayarlanarak)</br>- **macOS 10.11 ve üzeri**: Çözümlendi (PIN ayarlanarak)</br></br>- **Windows 8.1 ve üzeri**: Geçerli değil</br>- **Windows Phone 8.1 ve üzeri**: Çözümlendi |
| **Jailbreak uygulanmış veya kök erişim izni verilmiş cihaz** | - **Android 4.0 ve üzeri**: Karantinaya Alındı (ayar değil)</br>- **Samsung Knox Standard 4.0 ve üzeri**: Karantinaya Alındı (ayar değil)</br>- **Android Kurumsal**: Karantinaya Alındı (ayar değil)</br></br>- **iOS 8.0 ve üstü**: Karantinaya Alındı (ayar değil)</br>- **macOS 10.11 ve üzeri**: Geçerli değil</br></br>- **Windows 8.1 ve üzeri**: Geçerli değil</br>- **Windows Phone 8.1 ve üzeri**: Geçerli değil |
| **E-posta profili** | - **Android 4.0 ve üzeri**: Geçerli değil</br>- **Samsung Knox Standard 4.0 ve üzeri**: Geçerli değil</br>- **Android Kurumsal**: Geçerli değil</br></br>- **iOS 8.0 ve üstü**: Karantinaya Alındı</br>- **macOS 10.11 ve üzeri**: Karantinaya Alındı</br></br>- **Windows 8.1 ve üzeri**: Geçerli değil</br>- **Windows Phone 8.1 ve üzeri**: Geçerli değil |
| **En düşük işletim sistemi sürümü** | - **Android 4.0 ve üzeri**: Karantinaya Alındı</br>- **Samsung Knox Standard 4.0 ve üzeri**: Karantinaya Alındı</br>- **Android Kurumsal**: Karantinaya Alındı</br></br>- **iOS 8.0 ve üstü**: Karantinaya Alındı</br>- **macOS 10.11 ve üzeri**: Karantinaya Alındı</br></br>- **Windows 8.1 ve üzeri**: Karantinaya Alındı</br>- **Windows Phone 8.1 ve üzeri**: Karantinaya Alındı |
| **En yüksek işletim sistemi sürümü** | - **Android 4.0 ve üzeri**: Karantinaya Alındı</br>- **Samsung Knox Standard 4.0 ve üzeri**: Karantinaya Alındı</br>- **Android Kurumsal**: Karantinaya Alındı</br></br>- **iOS 8.0 ve üstü**: Karantinaya Alındı</br>- **macOS 10.11 ve üzeri**: Karantinaya Alındı</br></br>- **Windows 8.1 ve üzeri**: Karantinaya Alındı</br>- **Windows Phone 8.1 ve üzeri**: Karantinaya Alındı |
| **Windows durum kanıtlama** | - **Android 4.0 ve üzeri**: Geçerli değil</br>- **Samsung Knox Standard 4.0 ve üzeri**: Geçerli değil</br>- **Android Kurumsal**: Geçerli değil</br></br>- **iOS 8.0 ve üstü**: Geçerli değil</br>- **macOS 10.11 ve üzeri**: Geçerli değil</br></br>- **Windows 10 ve Windows 10 Mobile**: Karantinaya Alındı</br>- **Windows 8.1 ve üzeri**: Karantinaya Alındı</br>- **Windows Phone 8.1 ve üzeri**: Geçerli değil |

---------------------------

**Düzeltilen**: Cihazın işletim sistemi uyumluluğu zorlar. Örneğin, kullanıcı bir PIN ayarlamaya zorlanır.

**Karantinaya alınan**: Cihazın işletim sistemi uyumluluğu zorunlu değildir. Örneğin, Android ve Android Kurumsal cihazlar kullanıcıyı cihazı şifrelemeye zorla. Cihaz uyumsuz olduğunda aşağıdaki işlemler yapılır:

  - Kullanıcı için geçerli bir koşullu erişim ilkesi varsa cihaz engellenir.
  - Şirket portalı uygulamasını tüm uyumluluk sorunları hakkında kullanıcıya bildirir.

## <a name="azure-classic-portal-vs-azure-portal"></a>Klasik Azure portalı ve Azure portal

Cihaz uyumluluk ilkelerini Azure portalında kullanırken göreceğiniz temel fark:

- Azure Portalı’nda uyumluluk ilkeleri, desteklenen her platform için ayrı oluşturulur
- Klasik Azure portalında ise desteklenen tüm platformlarda tek bir cihaz uyumluluk ilkesi ortak kullanılır

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are initiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

[Klasik portalda](https://manage.microsoft.com) oluşturulan cihaz uyumluluk ilkeleri, [Azure portalında](https://portal.azure.com) görünmez. Ancak bunlar yine de kullanıcılara hedeflenmiştir ve klasik Intune portalı kullanılarak yönetilebilir.

Azure portalındaki yeni cihaz uyumluluk özelliklerini kullanmak için doğrudan bu portalda yeni cihaz uyumluluk ilkeleri oluşturmanız gerekir. Klasik portalda cihaz uyumluluk ilkesi atanmış bir kullanıcıya Azure portalında bir cihaz uyumluluk ilkesi atarsanız, Azure portalından gelen cihaz uyumluluk ilkeleri klasik portalda oluşturulanlardan önceliklidir.

## <a name="next-steps"></a>Sonraki adımlar

- [Bir ilke oluşturmak](create-compliance-policy.md) ve önkoşulları görüntüleyin.
- Farklı cihaz platformları için uyumluluk ayarları bakın:

  - [Android](compliance-policy-create-android.md)
  - [Android Kurumsal](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows 10 ve üzeri](compliance-policy-create-windows.md)
  - [Windows 8.1 ve Windows Phone 8.1](compliance-policy-create-windows-8-1.md)

- [İlke varlıkları için başvuru](reports-ref-policy.md) Intune veri ambarı ilke varlıkları hakkında bir bilgi bulunmaz.