---
title: Microsoft Intune - Azure’da cihaz uyumluluk ilkeleri | Microsoft Docs
description: Cihaz uyumluluk ilkelerini kullanma gereksinimleri, durum ve önem derecesi genel bakışı, InGracePeriod durumunu kullanma, koşullu erişim ile çalışma, atanmış bir ilkesi olmayan cihazları işleme ve Azure portalı ile Microsoft Intune klasik portal arasındaki uyumluluk farkları
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2f599f168c1b4ae9aa94324b69ed11e6d426c86d
ms.sourcegitcommit: 4c18352d5b3b30080f7c7257fa63d852b1894850
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2018
---
# <a name="get-started-with-device-compliance-policies-in-intune"></a>Intune’da cihaz uyumluluk ilkelerini kullanmaya başlama

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Uyumluluk gereksinimleri temelde kurallardır, örneğin cihaz PIN’i veya şifreleme gerektirebilir. Cihaz uyumluluk ilkeleri, bir cihazın uyumlu olarak değerlendirilmesi için takip etmesi gereken bu kuralları ve ayarları tanımlar. Bu kurallar şunlardır:

- Cihazlara erişmek için bir parola kullanma

- Şifreleme

- Cihazın işletim sistemi engellemeleri kaldırılmış veya kök erişim izni verilmiş olup olmaması

- İzin verilen en düşük işletim sistemi sürümü

- İzin verilen en yüksek işletim sistemi sürümü

- Cihazın Mobile Threat Defense düzeyinde veya daha düşük bir düzeyde olmasını gerektirme

Cihaz uyumluluk ilkelerini, cihazlarınızdaki uyumluluk durumunu izlemek için de kullanabilirsiniz.

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
Cihaz uyumluluk ilkelerini kullanmak için şunlar gereklidir:

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

- Cihazların uyumluluk durumunun rapor edilebilmesi için Intune’a kayıtlı olmaları gerekir

- Tek bir kullanıcıya kayıtlı veya birincil kullanıcısı olmayan cihazlar desteklenir. Birden fazla kullanıcı bağlamı desteklenmez.

## <a name="how-intune-device-compliance-policies-work-with-azure-ad"></a>Intune cihaz uyumluluk ilkelerinin Azure AD ile birlikte çalışması

Bir cihaz Intune’a kaydedildiğinde Azure AD kayıt işlemi başlar. Bu işlem, Azure AD’de cihazın özniteliklerini güncelleştirir. En önemli bilgilerden biri, cihaz uyumluluk durumudur. Bu uyumluluk durumu, e-posta veya diğer şirket kaynaklarına erişimi engellemek veya mümkün kılmak için koşullu erişim ilkeleri tarafından kullanılır.

[Azure AD kayıt işlemi](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) daha fazla bilgi sağlamaktadır.

### <a name="assign-a-resulting-device-configuration-profile-status"></a>Tek bir cihaz yapılandırma profili durumu atama

Bir cihazda birden fazla yapılandırma profili varsa ve cihazın bu atanmış yapılandırma profillerinden iki veya daha fazlası için farklı uyumluluk durumları varsa cihaza tek bir uyumluluk durumu atanır. Bu atama, uyumluluk durumlarına atanan kavramsal önem derecesi düzeyine dayalı olarak yapılır. Uyumluluk durumlarının önem derecesi aşağıdaki gibidir:

|Durum  |Önem Derecesi  |
|---------|---------|
|Bekleniyor     |1|
|Başarılı     |2|
|Başarısız     |3|
|Hata     |4|

Bir cihazda birden fazla yapılandırma profili varsa bu profillerden en yüksek önem derecesine sahip olanı bu cihaza atanır.

Örneğin bir cihaza üç profil atandığını düşünelim: biri Bekleniyor durumunda (önem derecesi = 1), biri Başarılı durumunda (önem derecesi = 2) ve biri Hatalı durumunda (önem derecesi = 4). Hatalı durumu en yüksek önem derecesine sahip olduğu için bu üç profilde de Hata uyumluluk durumu görünür.

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

|Durum  |Önem Derecesi  |
|---------|---------|
|Bilinmiyor     |1|
|NotApplicable     |2|
|Uyumlu|3|
|YetkisizKullanımSüresinde|4|
|Uyumsuz|5|
|Hata|6|

Bir cihazda birden fazla uyumluluk ilkesi varsa, bu ilkelerden en yüksek önem derecesine sahip olanı bu cihaza atanır.

Örneğin bir cihaza üç uyumluluk ilkesi atandığını düşünelim: biri Bilinmiyor durumunda (önem derecesi = 1), biri Uyumlu durumunda (önem derecesi = 3) ve biri YetkisizKullanımSüresinde durumunda (önem derecesi = 4). InGracePeriod durumu en yüksek önem derecesine sahip olduğu için bu üç profilde de InGracePeriod uyumluluk durumu görünür.

## <a name="ways-to-use-device-compliance-policies"></a>Cihaz uyumluluk ilkelerini kullanma yolları

#### <a name="with-conditional-access"></a>Koşullu erişim ile
İlke kurallarına uyum sağlayan cihazlara e-posta ve diğer şirket kaynaklarına erişim verebilirsiniz. Cihazlar, ilke kurallarına uymuyorsa şirket kaynaklarına erişim almazlar. Koşullu erişim budur.

#### <a name="without-conditional-access"></a>Koşullu erişim olmadan
Cihaz uyumluluk ilkelerini koşullu erişim olmadan da kullanabilirsiniz. Uyumluluk ilkelerini bağımsız olarak kullandığınızda, hedeflenen cihazlar değerlendirilir ve uyumluluk durumları raporlanır. Örneğin, kaç cihazın şifrelenmediği ya da hangi cihazlarda işletim sistemi engellemelerinin kaldırıldığı veya kök erişim izni verildiği konusunda bir rapor alabilirsiniz. Uyumluluk ilkelerini koşullu erişim olmadan kullandığınızda, şirket kaynaklarına yönelik erişim kısıtlaması olmaz.

## <a name="ways-to-deploy-device-compliance-policies"></a>Cihaz uyumluluk ilkelerini dağıtma yolları
Kullanıcı gruplarındaki kullanıcılara veya cihaz gruplarındaki cihazlara uyumluluk ilkesi dağıtabilirsiniz. Bir uyumluluk ilkesi kullanıcıya dağıtıldığında, kullanıcının tüm cihazlarında uyumluluk denetimi yapılır.

**Uyumluluk ilkesi ayarları** (Azure portalı > Cihaz uyumluluğu) şunları barındırır:

- **Kendisine hiçbir uyumluluk ilkesi atanmamış cihazları şöyle işaretle**: Bu özelliğin iki değeri vardır:

  - **Uyumlu**: güvenlik özelliği kapalı
  - **Uyumsuz** (varsayılan): güvenlik özelliği açık

  Bir cihaza atanmış uyumluluk ilkesi yoksa, bu cihaz uyumsuz olarak değerlendirilir. Varsayılan olarak cihazlar, **Uyumsuz** olarak işaretlenir. Koşullu erişim kullanıyorsanız varsayılan **Uyumsuz** ayarını değiştirmemenizi öneririz. Bir ilke atanmadığı için son kullanıcı uyumsuzsa, Şirket Portalı `No compliance policies have been assigned` ifadesine yer verir.

- **Gelişmiş jailbreak algılama**: Etkinleştirildiğinde bu ayar, iOS cihazların Intune’a daha sık iade edilmesine yol açar. Bu özellik etkinleştirildiğinde cihazın konum hizmetleri kullanılır ve pil kullanımı bundan etkilenir. Kullanıcı konum verileri, Intune tarafından depolanmaz.

  Bu ayarın etkinleştirilmesi, cihazlarda şunları gerektirir:
  - Konum hizmetlerinin işletim sistemi düzeyinde etkinleştirilmesi
  - Şirket Portalı’nın konum hizmetlerini kullanmasına izin verilmesi
  - Cihazın jailbreak durumunun en az 72 saatte bir değerlendirilip Intune’a rapor edilmesi. Aksi takdirde cihaz uyumsuz olarak işaretlenir.

- **Uyumluluk durumu geçerlilik süresi (gün)**: Alınan tüm uyumluluk ilkeleri için cihazların durum rapor etme süresini girin. Bu süre içinde durum döndürmeyen cihazlar uyumsuz olarak kabul edilir. Varsayılan değer 30 gündür.

Tüm cihazlarda bir **Varsayılan Cihaz Uyumluluk İlkesi** (Azure portalı > Cihaz uyumluluğu > İlke uyumluluğu) vardır. Bu varsayılan ilkeyi kullanarak bu ayarları izleyin.

İlke dağıtıldıktan sonra mobil cihazların ilke almasının ne kadar sürdüğü hakkında bilgi edinmek için bkz. [Cihaz profillerindeki sorunları giderme](device-profile-troubleshoot.md#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned).

Uyumluluk raporları, cihazların durumunu denetlemek için harika bir yoldur. Yönergeler için [Uyumluluk ilkelerini izleme](compliance-policy-monitor.md) makalesine bakın.

### <a name="actions-for-noncompliance"></a>Uyumsuzluğa yönelik eylemler
Uyumluluk ilkesi ölçütlerini sağlamayan cihazlarda geçerli, zamana göre sıralı bir dizi eylem yapılandırabilirsiniz. Bu uyumsuzluk eylemleri, [Uyumsuzluk eylemlerini otomatikleştirme](actions-for-noncompliance.md) makalesinde açıklandığı gibi otomatikleştirilebilir.

## <a name="azure-classic-portal-vs-azure-portal"></a>Klasik Azure portalı ve Azure portalı

Cihaz uyumluluk ilkelerini Azure portalında kullanırken göreceğiniz temel fark:

- Azure Portalı’nda uyumluluk ilkeleri, desteklenen her platform için ayrı oluşturulur
- Klasik Azure portalında ise desteklenen tüm platformlarda tek bir cihaz uyumluluk ilkesi ortak kullanılır

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

## <a name="device-compliance-policies-in-the-classic-portal-and-azure-portal"></a>Klasik portalda ve Azure portalında cihaz uyumluluk ilkeleri

[Klasik portalda](https://manage.microsoft.com) oluşturulan cihaz uyumluluk ilkeleri, [Azure portalında](https://portal.azure.com) görünmez. Ancak bunlar yine de kullanıcılara hedeflenmiştir ve klasik Intune portalı kullanılarak yönetilebilir.

Azure portalındaki yeni cihaz uyumluluk özelliklerini kullanmak için doğrudan bu portalda yeni cihaz uyumluluk ilkeleri oluşturmanız gerekir. Klasik Intune portalında cihaz uyumluluk ilkesi atanmış bir kullanıcıya Azure portalında bir cihaz uyumluluk ilkesi atarsanız Intune Azure portalından gelen cihaz uyumluluk ilkeleri klasik Intune portalında oluşturulanlardan önceliklidir.

## <a name="next-steps"></a>Sonraki adımlar

- Aşağıdaki platformlar için bir cihaz uyumluluk ilkesi oluşturun:

  - [Android](compliance-policy-create-android.md)
  - [Android for Work](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows](compliance-policy-create-windows.md)

- Intune Veri Ambarı ilke varlıkları hakkında bilgi için bkz. [İlke varlıkları için başvuru](reports-ref-policy.md).
