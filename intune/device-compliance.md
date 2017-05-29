---
title: "Cihaz uyumluluğu"
titleSuffix: Intune Azure preview
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
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 2aec7463b9a2b3bdaa78281fca0bbb39dcd3f884
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="what-is-device-compliance-in-intune-azure-preview"></a>Intune Azure önizlemesinde cihaz uyumluluğu nedir?

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Intune’daki cihaz uyumluluk ilkeleri, bir cihazın Intune ve EMS koşullu erişim ilkeleriyle uyumlu kabul edilmesi için uyması gereken kuralları ve ayarları tanımlar. Cihaz uyumluluk ilkelerini ayrıca, cihazlardaki uyumluluk sorunlarını izlemek ve gidermek için de kullanabilirsiniz. 

Bu kurallar aşağıdakileri içerir:

- Cihazlara erişmek için bir parola kullanma
- Şifreleme
- Cihazın işletim sistemi engellemeleri kaldırılmış veya kök erişim izni verilmiş olup olmaması
- İzin verilen en düşük işletim sistemi sürümü
- İzin verilen en yüksek işletim sistemi sürümü
- Cihazın Mobile Threat Defense düzeyinde veya daha düşük bir düzeyde olmasını gerektirme

<!---##  Concepts
Following are some terms and concepts that are useful to understanding how to use compliance policies.

### Device compliance requirements
Compliance requirements are essentially rules like requiring a device PIN or encryption that you can specify as required or not required for a compliance policy.

### Actions for noncompliance

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

##  <a name="how-should-i-use-a-device-compliance-policy"></a>Cihaz uyumluluk ilkesini nasıl kullanmalıyım?

### <a name="using-ems-conditional-access"></a>EMS koşullu erişimini kullanma
E-postaya ve diğer kurumsal kaynaklara yalnızca bir veya daha fazla cihaz uyumluluk ilkesinin kurallarına uyan cihazların erişmesine izin vermek için, uyumluluk ilkesini EMS koşullu erişimiyle birlikte kullanabilirsiniz.

### <a name="not-using-ems-conditional-access"></a>EMS koşullu erişimini kullanmama
Cihaz uyumluluk ilkelerini, EMS koşullu erişiminden bağımsız olarak da kullanabilirsiniz.
Uyumluluk ilkelerini bağımsız olarak kullandığınızda, hedeflenen cihazlar değerlendirilir ve uyumluluk durumları raporlanır. Örneğin, kaç cihazın şifrelenmediği ya da hangi cihazlarda işletim sistemi engellemelerinin kaldırıldığı veya kök erişim izni verildiği konusunda bir rapor alabilirsiniz. Ancak uyumluluk ilkelerini bağımsız olarak kullandığınızda, şirket kaynaklarına yönelik erişim kısıtlaması olmaz.

Uyumluluk ilkesini kullanıcılara siz dağıtırsınız. Bir uyumluluk ilkesi kullanıcıya dağıtıldığında, kullanıcının cihazlarında uyumluluk denetimi yapılır. İlke dağıtıldıktan sonra mobil cihazların ilkeyi almasının ne kadar sürdüğü hakkında bilgi edinmek için bkz. Cihazlarınızda ayarları ve özellikleri yönetme.

##  <a name="intune-classic-admin-console-vs-intune-azure-preview-portal"></a>Intune klasik yönetici konsolu ile Intune Azure önizleme portalı karşılaştırması

Bugüne kadar Intune klasik yönetim konsolunu kullandıysanız, Azure portalındaki yeni cihaz uyumluluk ilkesi iş akışına geçiş yapmanıza yardımcı olması için aşağıdaki farklılıklara dikkat edin:

-   Azure Portal’da uyumluluk ilkeleri, desteklenen her platform için ayrı oluşturulur. Intune Yönetim konsolunda, tüm desteklenen platformlar için ortak tek bir uyumluluk ilkesi vardır.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="migration-from-intune-classic-console-to-intune-azure-preview-portal"></a>Klasik Intune konsolundan Intune Azure önizleme portalına geçiş

[Klasik Intune konsolunda](https://manage.microsoft.com) oluşturulan cihaz uyumluluk ilkeleri yeni [Intune Azure portalında](https://portal.azure.com) görünmez. Ancak yine de kullanıcılara hedeflenebilir ve klasik Intune konsolu üzerinden yönetilebilir.

Intune Azure portalındaki yeni cihaz uyumluluk özelliklerinden yararlanmak istiyorsanız Intune Azure portalında yeni cihaz uyumluluk ilkeleri oluşturmanız gerekir. Klasik Intune portalında cihaz uyumluluk ilkesi atanmış bir kullanıcıya Intune Azure portalında yeni bir cihaz uyumluluk ilkesi atarsanız, Intune Azure portalından gelen cihaz uyumluluk ilkeleri klasik Intune konsolunda oluşturulanlardan önceliklidir.

##  <a name="next-steps"></a>Sonraki adımlar

[Cihaz uyumluluk ilkelerini kullanmaya başlama](device-compliance-get-started.md)


<!---### See also

Conditional access--->

