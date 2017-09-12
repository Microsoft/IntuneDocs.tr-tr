---
title: Intune cihaz uyumluluk ilkeleri
titleSuffix: Azure portal
description: "Microsoft Intune’da cihaz uyumluluğunu öğrenmek için bu konuyu kullanın\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a916fa0d-890d-4efb-941c-7c3c05f8fe7c
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: aa78383233950e342c5ab0f83095bba3c8fda1f9
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2017
---
# <a name="get-started-with-intune-device-compliance-policies"></a>Intune cihaz uyumluluk ilkelerini kullanmaya başlama

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="what-is-device-compliance-in-intune"></a>Intune'da cihaz uyumluluğu nedir?

Intune cihaz uyumluluk ilkeleri, bir cihazın Intune tarafından uyumlu olarak değerlendirilmesi için uyması gereken kuralları ve ayarları tanımlar.

Bu kurallar aşağıdakileri içerir:

- Cihazlara erişmek için bir parola kullanma

- Şifreleme

- Cihazın işletim sistemi engellemeleri kaldırılmış veya kök erişim izni verilmiş olup olmaması

- İzin verilen en düşük işletim sistemi sürümü

- İzin verilen en yüksek işletim sistemi sürümü

- Cihazın Mobile Threat Defense düzeyinde veya daha düşük bir düzeyde olmasını gerektirme

Cihaz uyumluluk ilkelerini, cihazlarınızdaki uyumluluk durumunu izlemek için de kullanabilirsiniz.

### <a name="device-compliance-requirements"></a>Cihaz uyumluluk gereksinimleri

Uyumluluk gereksinimleri temelde, PIN veya şifreleme isteme gibi kurallardır. Bir uyumluluk ilkesinde bunun gerekli olduğunu veya gerekli olmadığını belirtebilirsiniz.

<!---### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

-   When the device is first determined to be non-compliant, an email with noncompliant notification is sent to the user.

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

- Intune EMS

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

- [Azure AD kayıt işlemi](https://docs.microsoft.com/azure/active-directory/active-directory-device-registration-overview) hakkında daha fazla bilgi edinin.

##  <a name="ways-to-use-device-compliance-policies"></a>Cihaz uyumluluk ilkelerini kullanma yolları

### <a name="with-conditional-access"></a>Koşullu erişim ile
E-postaya ve diğer kurumsal kaynaklara yalnızca, bir veya daha fazla cihaz uyumluluk ilkesi kuralına uyan cihazların erişmesine izin vermek için uyumluluk ilkesini koşullu erişimle birlikte kullanabilirsiniz.

### <a name="without-conditional-access"></a>Koşullu erişim olmadan
Cihaz uyumluluk ilkelerini koşullu erişimden bağımsız olarak da kullanabilirsiniz. Uyumluluk ilkelerini bağımsız olarak kullandığınızda, hedeflenen cihazlar değerlendirilir ve uyumluluk durumları raporlanır. Örneğin, kaç cihazın şifrelenmediği ya da hangi cihazlarda işletim sistemi engellemelerinin kaldırıldığı veya kök erişim izni verildiği konusunda bir rapor alabilirsiniz. Ancak uyumluluk ilkelerini bağımsız olarak kullandığınızda, şirket kaynaklarına yönelik erişim kısıtlaması olmaz.

Uyumluluk ilkesini kullanıcılara siz dağıtırsınız. Bir uyumluluk ilkesi kullanıcıya dağıtıldığında, kullanıcının cihazlarında uyumluluk denetimi yapılır. İlke dağıtıldıktan sonra mobil cihazların ilkeyi almasının ne kadar sürdüğü hakkında bilgi edinmek için bkz. Cihazlarınızda ayarları ve özellikleri yönetme.

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

Aşağıdaki platformlar için bir cihaz uyumluluk ilkesi oluşturun:

- [Android](compliance-policy-create-android.md)
- [Android for Work](compliance-policy-create-android-for-work.md)
- [Android](compliance-policy-create-ios.md)
- [macOS](compliance-policy-create-mac-os.md)
- [Windows](compliance-policy-create-windows.md)
