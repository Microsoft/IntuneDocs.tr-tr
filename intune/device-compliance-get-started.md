---
title: Microsoft Intune cihaz uyumluluk ilkeleri
titleSuffix: ''
description: Microsoft Intune’da cihaz uyumluluğu hakkında bilgi edinin
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/1/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fb3ec168844708d80c83909ab6c58a52ca62e53c
ms.sourcegitcommit: a22309174e617e59ab0cdd0a55abde38711a5f35
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/23/2018
---
# <a name="get-started-with-microsoft-intune-device-compliance-policies"></a>Microsoft Intune cihaz uyumluluk ilkelerini kullanmaya başlama


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune cihaz uyumluluk ilkeleri, bir cihazın Intune tarafından uyumlu olarak değerlendirilmesi için uyması gereken kuralları ve ayarları tanımlar.

Bu kurallar aşağıdakileri içerir:

- Cihazlara erişmek için bir parola kullanma

- Şifreleme

- Cihazın işletim sistemi engellemeleri kaldırılmış veya kök erişim izni verilmiş olup olmaması

- İzin verilen en düşük işletim sistemi sürümü

- İzin verilen en yüksek işletim sistemi sürümü

- Cihazın Mobile Threat Defense düzeyinde veya daha düşük bir düzeyde olmasını gerektirme

Cihaz uyumluluk ilkelerini, cihazlarınızdaki uyumluluk durumunu izlemek için de kullanabilirsiniz.

## <a name="device-compliance-requirements"></a>Cihaz uyumluluk gereksinimleri

Uyumluluk gereksinimleri temelde, PIN veya şifreleme isteme gibi kurallardır. Bir uyumluluk ilkesinde bunun gerekli olduğunu veya gerekli olmadığını belirtebilirsiniz.

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

##  <a name="pre-requisites"></a>Ön koşullar

Intune’da cihaz uyumluluk ilkeleri kullanmak için aşağıdaki hizmetlere aboneliğinizin olması gerekir:

- Intune

- Azure AD Premium

###  <a name="supported-platforms"></a>Desteklenen Platformlar:

-   Android

-   iOS

-   macOS (önizleme)

-   Windows 8.1

-   Windows Phone 8.1

-   Windows 10

> [!IMPORTANT]
> Cihazların, uyumluluk durumunu rapor edebilmek için Intune’a kayıtlı olmaları gerekir.

## <a name="how-intune-device-compliance-policies-work-with-azure-ad"></a>Intune cihaz uyumluluk ilkelerinin Azure AD ile birlikte çalışması

Bir cihaz Intune’a kaydedildiğinde Azure AD kayıt işlemi gerçekleşir. Bu işlem, Azure AD’de cihazın özniteliklerini güncelleştirerek daha fazla bilgi ekler. En önemli bilgilerden biri, koşullu erişim ilkelerinin e-posta veya diğer şirket kaynaklarına erişimi denetlemek için kullandığı cihaz uyumluluk durumu bilgisidir.

- [Azure AD kayıt işlemi](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) hakkında daha fazla bilgi edinin.

### <a name="assigning-a-resulting-device-configuration-profile-status"></a>Tek bir cihaz yapılandırma profili durumu atama

Bir cihaza atanmış birden fazla yapılandırma profili varsa ve cihazın bu atanmış yapılandırma profillerinden iki veya daha fazlası için farklı uyumluluk durumları varsa, cihaza tek bir uyumluluk durumu atanması gerekir. Bu atama, uyumluluk durumlarına atanan kavramsal önem derecesi düzeyine dayalı olarak yapılır. Uyumluluk durumlarının önem derecesi aşağıdaki gibidir:


|Durum  |Önem Derecesi  |
|---------|---------|
|Bekleniyor     |1|
|Başarılı     |2|
|Başarısız     |3|
|Hata     |4|

Cihaza atanmış tüm profiller arasındaki en yüksek önem derecesi seçilerek iki veya daha fazla yapılandırma profilinin son durumu atanır.

Örneğin bir cihaza üç profil atandığını düşünelim: biri Bekleniyor durumunda (önem derecesi = 1), biri Başarılı durumunda (önem derecesi = 2) ve biri Hatalı durumunda (önem derecesi = 4). Hatalı durumu en yüksek önem derecesine sahip olduğu için bu üç profil için de son uyumluluk durumu olarak bu atanır.

### <a name="assigning-an-ingraceperiod-status-for-an-assigned-compliance-policy"></a>Atanmış bir uyumluluk ilkesi için YetkisizKullanımSüresinde durumu atama

Bir uyumluluk ilkesi için YetkisizKullanımSüresinde durumu, cihazın yetkisiz kullanım durumu ve atanmış uyumluluk ilkesi için asıl durumunun birleşimi göz önünde bulundurularak belirlenen bir değerdir. 

Yani bir cihazın atanmış bir uyumluluk ilkesi için Uyumsuz durumu varsa ve:

- kendisine atanmış bir yetkisiz kullanım süresi yoksa, uyumluluk ilkesi için atanan değer Uyumsuz olur.
- kendisine atanmış yetkisiz kullanım süresi dolmuşsa, uyumluluk ilkesi için atanan değer Uyumsuz olur.
- kendisine atanmış yetkisiz kullanım süresi henüz dolmamışsa, uyumluluk ilkesi için atanan değer YetkisizKullanımSüresinde olur.

Aşağıdaki tabloda bu seçenekler özetlenmektedir:


|Asıl uyumluluk durumu|Atanmış yetkisiz kullanım süresi değeri|Geçerli uyumluluk durumu|
|---------|---------|---------|
|Uyumsuz |Bir yetkisiz kullanım süresi atanmamış |Uyumsuz |
|Uyumsuz |Önceki günün tarihi|Uyumsuz|
|Uyumsuz |Sonraki günün tarihi|YetkisizKullanımSüresinde|

Cihaz uyumluluk ilkelerini izleme hakkında daha fazla bilgi için bkz. [Intune Cihaz uyumluluk ilkelerini izleme](compliance-policy-monitor.md).

### <a name="assigning-a-resulting-compliance-policy-status"></a>Tek bir uyumluluk ilkesi durumu atama

Bir cihaza atanmış birden fazla uyumluluk ilkesi varsa ve cihazın bu atanmış uyumluluk ilkelerinden iki veya daha fazlası için farklı uyumluluk durumları varsa, cihaza tek bir uyumluluk durumu atanması gerekir. Bu atama, uyumluluk durumlarına atanan kavramsal önem derecesi düzeyine dayalı olarak yapılır. Uyumluluk durumlarının önem derecesi aşağıdaki gibidir: 

|Durum  |Önem Derecesi  |
|---------|---------|
|Bilinmiyor     |1|
|NotApplicable     |2|
|Uyumlu|3|
|YetkisizKullanımSüresinde|4|
|Uyumsuz|5|
|Hata|6|

Cihaza atanmış tüm ilkeler arasındaki en yüksek önem derecesi seçilerek iki veya daha fazla uyumluluk ilkesinin son durumu belirlenir.
 
Örneğin bir cihaza üç uyumluluk ilkesi atandığını düşünelim: biri Bilinmiyor durumunda (önem derecesi = 1), biri Uyumlu durumunda (önem derecesi = 3) ve biri YetkisizKullanımSüresinde durumunda (önem derecesi = 4). YetkisizKullanımSüresinde durumu en yüksek önem derecesine sahip olduğu için bu üç profil için de son uyumluluk durumu olarak bu atanır.  

##  <a name="ways-to-use-device-compliance-policies"></a>Cihaz uyumluluk ilkelerini kullanma yolları

### <a name="with-conditional-access"></a>Koşullu erişim ile
E-postaya ve diğer kurumsal kaynaklara yalnızca, bir veya daha fazla cihaz uyumluluk ilkesi kuralına uyan cihazların erişmesine izin vermek için uyumluluk ilkesini koşullu erişimle birlikte kullanabilirsiniz.

### <a name="without-conditional-access"></a>Koşullu erişim olmadan
Cihaz uyumluluk ilkelerini koşullu erişimden bağımsız olarak da kullanabilirsiniz. Uyumluluk ilkelerini bağımsız olarak kullandığınızda, hedeflenen cihazlar değerlendirilir ve uyumluluk durumları raporlanır. Örneğin, kaç cihazın şifrelenmediği ya da hangi cihazlarda işletim sistemi engellemelerinin kaldırıldığı veya kök erişim izni verildiği konusunda bir rapor alabilirsiniz. Ancak uyumluluk ilkelerini bağımsız olarak kullandığınızda, şirket kaynaklarına yönelik erişim kısıtlaması olmaz.

Uyumluluk ilkesini kullanıcılara siz dağıtırsınız. Bir uyumluluk ilkesi kullanıcıya dağıtıldığında, kullanıcının cihazlarında uyumluluk denetimi yapılır. İlke dağıtıldıktan sonra mobil cihazların ilke almasının ne kadar sürdüğü hakkında bilgi edinmek için bkz. [Microsoft Intune’da cihaz profillerindeki sorunları giderme](device-profile-troubleshoot.md#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned).

#### <a name="actions-for-non-compliance"></a>Uyumsuzluk için eylemler

Uyumsuzluk için eylemler, uyumluluk ilkesi ölçütlerini sağlamayan cihazlara uygulanacak zamana göre sıralı bir dizi eylem yapılandırmanıza olanak sağlar. Daha fazla bilgi için bkz. [Uyumsuzluk için eylemleri otomatikleştirme](actions-for-noncompliance.md).

##  <a name="using-device-compliance-policies-in-the-intune-classic-portal-vs-azure-portal"></a>Cihaz uyumluluk ilkeleri kullanımının karşılaştırması: klasik Intune portalı ve Azure portalı

Azure portalındaki yeni cihaz uyumluluk ilkesi iş akışına geçişinizi kolaylaştırmak için temel değişiklikleri not edin.

- Azure Portal’da uyumluluk ilkeleri, desteklenen her platform için ayrı oluşturulur.
- Klasik Intune portalında ise desteklenen tüm platformlarda ortak kullanılan tek bir cihaz uyumluluk ilkesi vardı.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="migrate-device-compliance-policies-from-the-intune-classic-portal-to-the-azure-portal"></a>Cihaz uyumluluk ilkelerini klasik Intune portalından Azure portalına geçirme

[Klasik Intune portalında](https://manage.microsoft.com) oluşturulan cihaz uyumluluk ilkeleri yeni [Intune Azure portalında](https://portal.azure.com) görünmez. Ancak bunlar yine de kullanıcılara hedeflenmiştir ve klasik Intune portalı üzerinden yönetilebilir.

Azure portalındaki yeni cihaz uyumluluk özelliklerinden yararlanmak istiyorsanız doğrudan bu portalda yeni cihaz uyumluluk ilkeleri oluşturmanız gerekir. Klasik Intune portalında cihaz uyumluluk ilkesi atanmış bir kullanıcıya Azure portalında yeni bir cihaz uyumluluk ilkesi atarsanız Intune Azure portalından gelen cihaz uyumluluk ilkeleri klasik Intune portalında oluşturulanlardan önceliklidir.

##  <a name="next-steps"></a>Sonraki adımlar

- Aşağıdaki platformlar için bir cihaz uyumluluk ilkesi oluşturun:

   - [Android](compliance-policy-create-android.md)
   - [Android for Work](compliance-policy-create-android-for-work.md)
   - [iOS](compliance-policy-create-ios.md)
   - [macOS](compliance-policy-create-mac-os.md)
   - [Windows](compliance-policy-create-windows.md)

- Intune Veri Ambarı ilke varlıkları hakkında bilgi için bkz. [İlke varlıkları için başvuru](reports-ref-policy.md).
