---
title: Microsoft Intune - Azure’da cihaz uyumluluk ilkeleri | Microsoft Docs
description: Kullanımı cihaz uyumluluk ilkelerini, koşullu erişim, Azure portalında uyumluluk farkları ve atanmış bir ilkesi olmayan cihazları işleme ile çalışma Ingraceperiod durumunu kullanma, durum ve önem derecesi genel bakış kullanmaya başlayın ve Klasik portalda Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/28/2019
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
ms.openlocfilehash: 6a0cb69612e4cf0181fde957f06f490bede7200e
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57392537"
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
> Intune, cihazda tüm uyumluluk değerlendirme için cihaz iade zamanlama izler. [Cihaz iade zamanlama hakkında daha fazla bilgi](https://docs.microsoft.com/intune/device-profile-troubleshoot#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned).

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

## <a name="prerequisites"></a>Önkoşullar

Cihaz uyumluluk ilkelerini kullanmak için emin olun:

- Aşağıdaki abonelikleri kullanın:

  - Intune
  - Azure Active Directory (AD) Premium

- Desteklenen bir platform kullanın:

  - Android
  - iOS
  - macOS (önizleme)
  - Windows 8.1
  - Windows Phone 8.1
  - Windows 10

- Intune uyumluluk durumunu görmek için cihazları kaydetme

- Bir kullanıcı cihazlarını kaydetme veya birincil kullanıcısı kaydetme. Birden çok kullanıcının kayıtlı cihazlar desteklenmez.

## <a name="how-device-compliance-policies-work-with-azure-ad"></a>Cihaz uyumluluk ilkelerini Azure AD ile nasıl çalışır?

Bir cihaz Intune’a kaydedildiğinde Azure AD kayıt işlemi başlar. Bu işlem, Azure AD’de cihazın özniteliklerini güncelleştirir. En önemli bilgilerden biri, cihaz uyumluluk durumudur. Bu uyumluluk durumu, e-posta veya diğer şirket kaynaklarına erişimi engellemek veya mümkün kılmak için koşullu erişim ilkeleri tarafından kullanılır.

[Azure AD kayıt işlemi](https://docs.microsoft.com/azure/active-directory/device-management-introduction) daha fazla bilgi sağlamaktadır.

## <a name="refresh-cycle-times"></a>Döngü sürelerini Yenile

Uyumluluk denetimi, Intune yapılandırma profili aynı yenileme döngüsü kullanır. Genel olarak, zamanları şunlardır:

| Platform | Yenileme döngüsü|
| --- | --- |
| iOS | 6 saatte bir |
| Mac OS | 6 saatte bir |
| Android | 8 saatte bir |
| Cihaz olarak kaydedilen Windows 10 bilgisayarlar | 8 saatte bir |
| Windows Phone | 8 saatte bir |
| Windows 8.1 | 8 saatte bir |

Son olarak cihazın kayıtlı, uyumluluk iade daha sık çalışır:

| Platform | Sıklık |
| --- | --- |
| iOS | 6 saat boyunca her 15 dakikada bir, daha sonra her 6 saatte bir |  
| Mac OS X | 6 saat boyunca her 15 dakikada bir, daha sonra her 6 saatte bir | 
| Android | 15 dakika boyunca 3 dakikada bir, sonraki 2 saat boyunca 15 dakikada bir ve daha sonra 8 saatte bir | 
| Windows Phone | 15 dakika boyunca 5 dakikada bir, sonraki 2 saat boyunca 15 dakikada bir ve daha sonra 8 saatte bir | 
| Cihaz olarak kaydedilen Windows bilgisayarları | 30 dakika boyunca 3 dakikada bir, daha sonra 8 saatte bir | 

Her zaman, kullanıcılar Şirket portalı uygulamasını açın ve hemen bir ilkeyi denetlemek için cihazı eşitleyebilir.

### <a name="assign-an-ingraceperiod-status"></a>InGracePeriod durumu atama

InGracePeriod durumu, uyumluluk ilkesi için bir değerdir. Bu değer, cihazın yetkisiz kullanım süresi ile bu uyumluluk ilkesi için asıl cihaz durumunun bir bileşimi ile belirlenir.

Yani bir cihazın atanmış bir uyumluluk ilkesi için Uyumsuz durumu varsa ve:

- kendisine atanmış bir yetkisiz kullanım süresi yoksa, uyumluluk ilkesi için atanan değer NonCompliant olur
- kendisine atanmış yetkisiz kullanım süresi dolmuşsa, uyumluluk ilkesi için atanan değer NonCompliant olur
- kendisine atanmış yetkisiz kullanım süresi henüz dolmamışsa, uyumluluk ilkesi için atanan değer InGracePeriod olur

Aşağıdaki tabloda bu noktalar özetlenmektedir:

|Asıl uyumluluk durumu|Atanmış yetkisiz kullanım süresi değeri|Geçerli uyumluluk durumu|
|---------|---------|---------|
|Uyumsuz |Bir yetkisiz kullanım süresi atanmamış |Uyumsuz |
|Uyumsuz |Önceki günün tarihi|Uyumsuz|
|Uyumsuz |Sonraki günün tarihi|YetkisizKullanımSüresinde|

Cihaz uyumluluk ilkelerini izleme hakkında daha fazla bilgi için bkz. [Intune Cihaz uyumluluk ilkelerini izleme](compliance-policy-monitor.md).

### <a name="assign-a-resulting-compliance-policy-status"></a>Tek bir uyumluluk ilkesi durumu atama

Bir cihazda birden fazla uyumluluk ilkesi varsa ve cihazın bu atanmış uyumluluk ilkelerinden iki veya daha fazlası için farklı uyumluluk durumları varsa, cihaza tek bir uyumluluk durumu atanır. Bu atama, uyumluluk durumlarına atanan kavramsal önem derecesi düzeyine dayalı olarak yapılır. Uyumluluk durumlarının önem derecesi aşağıdaki gibidir:

|Durum  |Severity  |
|---------|---------|
|Bilinmiyor     |1.|
|NotApplicable     |2|
|Uyumlu|3|
|YetkisizKullanımSüresinde|4|
|Uyumsuz|5|
|Hata|6|

Bir cihazda birden fazla uyumluluk ilkesi varsa, bu ilkelerden en yüksek önem derecesine sahip olanı bu cihaza atanır.

Örneğin bir cihaza üç uyumluluk ilkesi atandığını düşünelim: biri Bilinmiyor durumunda (önem derecesi = 1), biri Uyumlu durumunda (önem derecesi = 3) ve biri InGracePeriod durumunda (önem derecesi = 4). InGracePeriod durumu en yüksek önem derecesine sahip olduğu için bu üç profilde de InGracePeriod uyumluluk durumu görünür.

## <a name="ways-to-use-device-compliance-policies"></a>Cihaz uyumluluk ilkelerini kullanma yolları

#### <a name="with-conditional-access"></a>Koşullu erişim ile
İlke kurallarına uyum sağlayan cihazlara e-posta ve diğer şirket kaynaklarına erişim verebilirsiniz. Cihazlar, ilke kurallarına uymuyorsa şirket kaynaklarına erişim almazlar. Koşullu erişim budur.

#### <a name="without-conditional-access"></a>Koşullu erişim olmadan
Cihaz uyumluluk ilkelerini koşullu erişim olmadan da kullanabilirsiniz. Uyumluluk ilkelerini bağımsız olarak kullandığınızda, hedeflenen cihazlar değerlendirilir ve uyumluluk durumları raporlanır. Örneğin, kaç cihazın şifreli olmayan ya da hangi cihazların, jailbreak uygulanmış veya kök erişim izni verilmiş bir rapor alabilirsiniz. Uyumluluk ilkelerini koşullu erişim olmadan kullandığınızda, tüm kuruluş kaynaklarına yönelik erişim kısıtlaması yok.

## <a name="ways-to-deploy-device-compliance-policies"></a>Cihaz uyumluluk ilkelerini dağıtma yolları
Kullanıcı gruplarındaki kullanıcılara veya cihaz gruplarındaki cihazlara uyumluluk ilkesi dağıtabilirsiniz. Bir uyumluluk ilkesi kullanıcıya dağıtıldığında, kullanıcının tüm cihazlarında uyumluluk denetimi yapılır. Windows 10 sürüm 1803 ve daha yeni cihazlarda, birincil kullanıcı cihazı *kaydetmemişse* cihaz gruplarına dağıtmanız önerilir. Bu senaryoda cihaz gruplarını kullanmak, uyumluluk raporlamasına yardımcı olur.

Yerleşik uyumluluk İlkesi ayarları kümesi (**Intune** > **cihaz uyumluluğu**) tüm Intune'a kayıtlı cihazlar üzerinde değerlendirilir. Bunlar:

- **Cihaz uyumluluk ilkesi atanmamış olarak işaretlemek**: Bu özelliğin iki değeri vardır:

  - **Uyumlu**: güvenlik özelliği kapalı
  - **Uyumsuz** (varsayılan): güvenlik özelliği açık

  Bir cihaza atanmış uyumluluk ilkesi yoksa, bu cihaz uyumsuz olarak değerlendirilir. Varsayılan olarak cihazlar, **Uyumsuz** olarak işaretlenir. Koşullu erişim kullanıyorsanız ayarını değiştirmek önerilen **uyumlu**. Son kullanıcı bir ilke atanmadığından uyumlu değilse, daha sonra Şirket portalı gösterir `No compliance policies have been assigned`.

- **Gelişmiş jailbreak algılama**: Bu ayar etkinleştirildiğinde, iOS cihazlarını Intune ile daha sık iade neden olur. Bu özellik etkinleştirildiğinde cihazın konum hizmetleri kullanılır ve pil kullanımı bundan etkilenir. Kullanıcı konum verileri, Intune tarafından depolanmaz.

  Bu ayarın etkinleştirilmesi, cihazlarda şunları gerektirir:
  - Konum hizmetlerinin işletim sistemi düzeyinde etkinleştirilmesi
  - Şirket Portalı’nın konum hizmetlerini kullanmasına izin verilmesi
  - Cihazın jailbreak durumunun en az 72 saatte bir değerlendirilip Intune’a rapor edilmesi. Aksi takdirde cihaz uyumsuz olarak işaretlenir. Değerlendirme, Şirket Portalı uygulaması açıldığında veya cihaz fiziksel olarak 500 metre veya daha uzağa taşındığında tetiklenir. Cihaz 500 ölçümleri 72 saat içinde hareket etmediği, kullanıcı Gelişmiş jailbreak sonu değerlendirme için Şirket portalı uygulamasını açması gerekir.

- **Uyumluluk durumu geçerlilik süresi (gün)**: Cihazların alınan tüm uyumluluk ilkeleri için durum rapor bir süre girin. Bu süre içinde durum döndürmeyen cihazlar uyumsuz olarak kabul edilir. Varsayılan değer 30 gündür.

Tüm cihazlarda bir **Yerleşik Cihaz Uyumluluk İlkesi** (Azure portalı > Cihaz uyumluluğu > İlke uyumluluğu) vardır. Bu yerleşik ilkeyi kullanarak bu ayarları izleyin.

İlke dağıtıldıktan sonra mobil cihazların ilke almasının ne kadar sürdüğü hakkında bilgi edinmek için bkz. [Cihaz profillerindeki sorunları giderme](device-profile-troubleshoot.md#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned).

Uyumluluk raporları, cihazların durumunu denetlemek için harika bir yoldur. Yönergeler için [Uyumluluk ilkelerini izleme](compliance-policy-monitor.md) makalesine bakın.

### <a name="actions-for-noncompliance"></a>Uyumsuzluğa yönelik eylemler
Uyumluluk ilkesi ölçütlerini sağlamayan cihazlarda geçerli, zamana göre sıralı bir dizi eylem yapılandırabilirsiniz. Bu uyumsuzluk eylemleri, [Uyumsuzluk eylemlerini otomatikleştirme](actions-for-noncompliance.md) makalesinde açıklandığı gibi otomatikleştirilebilir.

## <a name="azure-classic-portal-vs-azure-portal"></a>Klasik Azure portalı ve Azure portal

Cihaz uyumluluk ilkelerini Azure portalında kullanırken göreceğiniz temel fark:

- Azure Portalı’nda uyumluluk ilkeleri, desteklenen her platform için ayrı oluşturulur
- Klasik Azure portalında ise desteklenen tüm platformlarda tek bir cihaz uyumluluk ilkesi ortak kullanılır

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

## <a name="device-compliance-policies-in-the-classic-portal-and-azure-portal"></a>Klasik portalda ve Azure portalında cihaz uyumluluk ilkeleri

[Klasik portalda](https://manage.microsoft.com) oluşturulan cihaz uyumluluk ilkeleri, [Azure portalında](https://portal.azure.com) görünmez. Ancak bunlar yine de kullanıcılara hedeflenmiştir ve klasik Intune portalı kullanılarak yönetilebilir.

Azure portalındaki yeni cihaz uyumluluk özelliklerini kullanmak için doğrudan bu portalda yeni cihaz uyumluluk ilkeleri oluşturmanız gerekir. Klasik portalda cihaz uyumluluk ilkesi atanmış bir kullanıcıya Azure portalında bir cihaz uyumluluk ilkesi atarsanız, Azure portalından gelen cihaz uyumluluk ilkeleri klasik portalda oluşturulanlardan önceliklidir.

## <a name="next-steps"></a>Sonraki adımlar

- Aşağıdaki platformlar için bir cihaz uyumluluk ilkesi oluşturun:

  - [Android](compliance-policy-create-android.md)
  - [Android iş profili](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows](compliance-policy-create-windows.md)

- Intune Veri Ambarı ilke varlıkları hakkında bilgi için bkz. [İlke varlıkları için başvuru](reports-ref-policy.md).
