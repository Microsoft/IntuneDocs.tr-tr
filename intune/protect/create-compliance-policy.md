---
title: Create device compliance policies in Microsoft Intune - Azure | Microsoft Docs
description: Create device compliance policies, overview of status and severity levels, using the InGracePeriod status, working with Conditional Access, handling devices without an assigned policy, and the differences in compliance in the Azure portal and classic portal in Microsoft Intune
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/18/2019
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
ms.openlocfilehash: c8452f9b56032864380ec703bfd444dc85ef129b
ms.sourcegitcommit: 13fa1a4a478cb0e03c7f751958bc17d9dc70010d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/19/2019
ms.locfileid: "74188257"
---
# <a name="create-a-compliance-policy-in-microsoft-intune"></a>Microsoft Intune’da uyumluluk ilkesi oluşturma

Intune’un kuruluşunuzun kaynaklarını korumaya yönelik kullanımında cihaz uyumluluk ilkeleri en önemli özelliklerdendir. Intune’da cihazların uyumlu olarak değerlendirilmesi için uyması gereken minimum işletim sistemi sürümü gibi kurallar ve ayarlar oluşturabilirsiniz. If the device isn't compliant, you can then block access to data and resources using [Conditional Access](conditional-access.md).

Ayrıca uyumsuzluğa yönelik olarak kullanıcıya bildirim gönderme gibi önlemler alabilirsiniz. Uyumluluk ilkelerinin işlevleri ve kullanım şekilleri hakkında genel bilgilere için bkz. [Cihaz uyumluluğuna başlama](device-compliance-get-started.md).

Bu makalede:

- Uyumluluk ilkesi oluşturmak için gerekli önkoşullar ve adımlar listelenmiştir.
- İlkeyi kullanıcı ve cihaz gruplarınıza atama adımları gösterilmiştir.
- İlkelerinizi "filtrelemek" için kullanabileceğiniz kapsam etiketleri gibi ek adımlar ve uyumlu olmayan cihazlarda gerçekleştirebileceğiniz işlemler anlatılmıştır.
- Cihazların ilke güncelleştirmelerini aldığı iade yenileme döngüsü süreleri listelenmiştir.

## <a name="before-you-begin"></a>Başlamadan önce

Cihaz uyumluluk ilkelerini kullanmak için aşağıdakilerden emin olun:

- Aşağıdaki abonelikleri kullanın:

  - Intune
  - If you use Conditional Access, then you need Azure Active Directory (AD) Premium edition. [Azure Active Directory fiyatlandırması](https://azure.microsoft.com/pricing/details/active-directory/) sayfasında farklı sürümlerde sunulan özelliklere yer verilmiştir. Intune uyumluluğu için Azure AD gerekli değildir.

- Desteklenen bir platform kullanın:

  - Android device administrator
  - Android Kurumsal
  - iOS
  - Mac OS
  - Windows 10
  - Windows 8.1
  - WVPN profillerinidows Phone 8.1

- Cihazları Intune'a kaydetme (uyumluluk durumunu görmek için gereklidir)

- Cihazları bir kullanıcıya kaydedin veya birincil kullanıcı olmadan kaydedin. Cihazların birden çok kullanıcıya kaydedilmesi desteklenmez.

## <a name="create-the-policy"></a>İlkeyi oluşturma

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Select **Devices** > **Compliance policies** > **Create Policy**.

3. Specify the following properties:

   - **Name**: Enter a descriptive name for the policy. İlkelerinizi daha sonra kolayca tanıyacak şekilde adlandırın. **Jailbreak uygulanmış iOS cihazlarını uyumlu değil olarak işaretle** iyi bir ilke adı örneğidir.

   - **Description**: Enter a description for the policy. Bu ayar isteğe bağlıdır ancak önerilir.

   - **Platform**: Choose the platform of your devices. Seçenekleriniz şunlardır:
     - **Android device administrator**
     - **Android Kurumsal**
     - **iOS/iPadOS**
     - **macOS**
     - **Windows Phone 8.1**
     - **Windows 8.1 ve üzeri**
     - **Windows 10 ve üzeri**

     For *Android Enterprise*, you must then select a **Profile type**:
     - **Device owner**
     - **Work Profile**

   - **Settings**: The following articles list and describe the settings for each platform:
     - [Android device administrator](compliance-policy-create-android.md)
     - [Android Kurumsal](compliance-policy-create-android-for-work.md)
     - [iOS/iPadOS](compliance-policy-create-ios.md)
     - [macOS](compliance-policy-create-mac-os.md)
     - [Windows Phone 8.1, Windows 8.1 ve üzeri](compliance-policy-create-windows-8-1.md)
     - [Windows 10 ve üzeri](compliance-policy-create-windows.md)  

   - **Locations** *(Android device administrator)* : In your policy, you can force compliance by the location of the device. Mevcut konumlar arasından seçim yapın. Henüz bir konumunuz yok mu? Intune'da [Konumları (ağ yalıtımı) kullanma](use-network-locations.md) başlığı altında bazı yönergeler sağlanır.  

   - **Actions for noncompliance**: For devices that don't meet your compliance policies, you can add a sequence of actions to apply automatically. Cihazın uyumsuz olarak işaretlenme zamanlamasını değiştirebilirsiniz (örneğin, bir gün sonra olarak). Ayrıca, cihaz uyumlu olmadığında kullanıcıya e-posta gönderen ikinci bir eylem de yapılandırabilirsiniz.

     [Uyumsuz cihazlar için eylem ekleme](actions-for-noncompliance.md) makalesinde, kullanıcılarınıza e-posta ile gönderilecek bir bildirim oluşturma da dahil olmak üzere daha fazla bilgi sağlanmıştır.

     Örneğin Konumlar özelliğini kullanıyor ve uyumluluk ilkesinde bir konum ekliyorsunuz. En az bir konum seçtiğinizde uyumsuzluk için varsayılan eylem uygulanır. Cihaz, seçili konumlara bağlı değilse hemen uyumsuz olarak değerlendirilir. Kullanıcılarınıza bir gün gibi bir yetkisiz kullanım süresi tanıyabilirsiniz.

   - **Scope (Tags)** : Scope tags are a great way to assign and filter policies to specific groups, such as Sales, HR, All US-NC employees, and so on. Uyumluluk ilkelerinize ayar ekledikten sonra bir kapsam etiketi de ekleyebilirsiniz. [İlke filtrelemek için kapsam etiketleri kullanma](../fundamentals/scope-tags.md) sayfası bu konuda faydalı bir kaynaktır.

4. Bitirdiğinizde, yaptığınız değişiklikleri kaydetmek için **Tamam** > **Oluştur**'u seçin. İlke oluşturulur ve listede gösterilir. Şimdi ilkeyi gruplarınıza atayın.

## <a name="assign-the-policy"></a>İlke atama

İlke oluşturulduktan sonra yapmanız gereken bunu gruplarınıza atamaktır:

1. Oluşturduğunuz ilkelerden birini seçin. Existing policies are in **Devices** > **Compliance policies** > **Policies**.

2. Select the *policy* > **Assignments**. Azure Active Directory (AD) güvenlik gruplarını dahil edebilir veya hariç tutabilirsiniz.

3. Azure AD güvenlik gruplarınızı görmek için **Seçili gruplar**’ı seçin. Select the groups you want this policy to apply > Choose **Save** to deploy the policy.

The users or devices targeted by your policy are evaluated for compliance when they check-in with Intune.

### <a name="evaluate-how-many-users-are-targeted"></a>Kaç kullanıcının hedeflendiğini değerlendirme

İlkeyi atadıktan sonra etkilenen kullanıcı sayısını da **değerlendirebilirsiniz**. Bu özellik, cihaz değil kullanıcı sayısını hesaplar.

1. In Intune, select **Devices** > **Compliance policies** > **Policies**.

2. Select a *policy* > **Assignments** > **Evaluate**. Bu ilkenin kaç kullanıcıyı hedeflediğini gösteren bir ileti görüntülenir.

**Değerlendir** düğmesi gri gösteriliyorsa, ilkenin bir veya birden fazla gruba atandığından emin olun.

<!-- ## Actions for noncompliance

For devices that don't meet your compliance policies, you can add a sequence of actions to apply automatically. You can change the schedule when the device is marked non-compliant, such as after one day. You can also configure a second action that sends an email to the user when the device isn't compliant.

[Add actions for noncompliant devices](actions-for-noncompliance.md) provides more information, including creating a notification email to your users.

For example, you're using the Locations feature, and add a location in a compliance policy. The default action for noncompliance applies when you select at least one location. If the device isn't connected to the selected locations, it's immediately considered not compliant. You can give your users a grace period, such as one day.

## Scope tags

Scope tags are a great way to assign and filter policies to specific groups, such as Sales, HR, All US-NC employees, and so on. After you add the settings, you can also add a scope tag to your compliance policies. [Use scope tags to filter policies](../fundamentals/scope-tags.md) is a good resource.
-->

## <a name="refresh-cycle-times"></a>Yenileme döngüsü süreleri

Intune uses different refresh cycles to check for updates to compliance policies. If the device recently enrolled, the check-in runs more frequently. [Policy and profile refresh cycles](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned) lists the estimated refresh times.

At any time, users can open the Company Portal app, and sync the device to immediately check for policy updates.

### <a name="assign-an-ingraceperiod-status"></a>InGracePeriod durumu atama

InGracePeriod durumu, uyumluluk ilkesi için bir değerdir. Bu değer, cihazın yetkisiz kullanım süresi ile bu uyumluluk ilkesi için asıl cihaz durumunun bir bileşimi ile belirlenir.

Yani bir cihazın atanmış bir uyumluluk ilkesi için Uyumsuz durumu varsa ve:

- The device has no grace period assigned to it, then the assigned value for the compliance policy is NonCompliant
- The device has a grace period that's expired, then the assigned value for the compliance policy is NonCompliant
- The device has a grace period that's in the future, then the assigned value for the compliance policy is InGracePeriod

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

Örneğin bir cihaza üç uyumluluk ilkesi atandığını düşünelim: biri Bilinmiyor durumunda (önem derecesi = 1), biri Uyumlu durumunda (önem derecesi = 3) ve biri InGracePeriod durumunda (önem derecesi = 4). InGracePeriod durumu en yüksek önem düzeyine sahiptir. Bu nedenle üç ilke de InGracePeriod uyumluluk durumuna sahip olur.

## <a name="next-steps"></a>Sonraki adımlar

[İlkelerinizi izleme](compliance-policy-monitor.md).
