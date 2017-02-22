---
title: "Cihaz uyumluluğu | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Microsoft Intune’da cihaz uyumluluğunu öğrenmek için bu konuyu kullanın"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a916fa0d-890d-4efb-941c-7c3c05f8fe7c
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7693d49e2f0fa6e4aa40b6bb71433a7eaab8dd15
ms.openlocfilehash: a4254503e4e6b86079f862966dee2727934f1ee6


---

# <a name="what-is-device-compliance-in-intune-azure-preview"></a>Intune Azure önizlemesinde cihaz uyumluluğu nedir?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Şirket verilerini korumaya yardımcı olmak için şirket uygulamalarına ve verilerine erişmek için kullanılan cihazların belirli kurallarla uyumlu olduğundan emin olmanız gerekir. Bu kurallar, cihazlara ve cihazlarda depolanan şifreleme verilerine erişmek için bir PIN kullanmayı içerebilir. Bu tür bir kurallar kümesine **uyumluluk ilkesi** adı verilir.

##  <a name="how-should-i-use-a-device-compliance-policy"></a>Cihaz uyumluluk ilkesini nasıl kullanmalıyım?
E-postaya ve diğer hizmetlere yalnızca uyumluluk ilkesinin kurallarına uyan cihazların erişmesine izin vermek için, uyumluluk ilkesini koşullu erişimle kullanabilirsiniz.

Uyumluluk ilkesini, koşullu erişimden bağımsız olarak da kullanabilirsiniz.
Uyumluluk ilkelerini bağımsız olarak kullandığınızda, hedeflenen cihazlar değerlendirilir ve uyumluluk durumları raporlanır. Örneğin, kaç cihazın şifrelenmediği ya da hangi cihazların yazılım kilidinin kırıldığı veya kökünün belirtildiği konusunda bir rapor alabilirsiniz. Ancak uyumluluk ilkelerini bağımsız olarak kullandığınızda, şirket kaynaklarına yönelik erişim kısıtlaması olmaz.

Uyumluluk ilkesini kullanıcılara siz dağıtırsınız. Bir uyumluluk ilkesi kullanıcıya dağıtıldığında, kullanıcının cihazlarında uyumluluk denetimi yapılır. İlke dağıtıldıktan sonra mobil cihazların ilkeyi almasının ne kadar sürdüğü hakkında bilgi edinmek için bkz. Cihazlarınızda ayarları ve özellikleri yönetme.

##  <a name="concepts"></a>Kavramlar
Aşağıda, uyumluluk ilkelerinin nasıl kullanıldığını anlamanızda yararlı olacak bazı terimler ve kavramlar verilmiştir.

### <a name="compliance-requirements"></a>Uyumluluk gereksinimleri
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

##  <a name="differences-between-the-classic-intune-admin-console-and-intune-in-the-azure-portal"></a>Klasik Intune yönetim konsoluyla Azure Portal’daki Intune arasındaki farklılıklar


Daha önce klasik Intune yönetim konsolunu kullandıysanız, Azure Portal’daki yeni cihaz uyumluluğu iş akışına geçiş yapmanıza yardımcı olması için aşağıdaki farklılıkları not alın:


-   Azure Portal’da uyumluluk ilkeleri, desteklenen her platform için ayrı oluşturulur. Intune Yönetim konsolunda, tüm desteklenen platformlar için ortak tek bir uyumluluk ilkesi vardır.


<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="next-steps"></a>Sonraki adımlar

[Uyumluluk ilkelerini kullanmaya başlama](get-started-with-device-compliance.md)


<!---### See also

Conditional access--->



<!--HONumber=Feb17_HO1-->


