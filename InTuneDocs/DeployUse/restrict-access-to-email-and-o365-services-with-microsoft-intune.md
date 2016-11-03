---
title: "E-posta ve O365 hizmetlerine erişimi kısıtlama | Microsoft Intune"
description: "Bu konu başlığı altında, SharePoint Online’daki ve diğer hizmetlerdeki şirket e-postasına ve şirket verilerine yalnızca uyumlu cihazların erişmesine izin vermek için koşullu erişimin nasıl kullanılabileceği açıklanır."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c564d292-b83b-440d-bf08-3f5b299b7a5e
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 99b01f5ca5bb389fc8a9d87e956796823fee6c0d
ms.openlocfilehash: 6e11d71265f01ae31ab3124a46aaa544ad2f453a


---

# Microsoft Intune ile e-posta, O365 hizmetleri ve diğer hizmetlere erişimi kısıtlama
Intune’un koşullu erişimiyle, şirket e-postanıza ve O365 hizmetlerine erişimi kısıtlayabilirsiniz. Intune'un koşullu erişim özelliği, şirketinizin e-postasına ve O365 hizmetlerine erişimin, ayarladığınız kurallara uyan cihazlarla sınırlı olduğundan emin olmanızı sağlar.
## Koşullu erişim nasıl çalışır?
Uyumluluk ilkesi ayarları kullanılarak cihazın uyumluluğunu değerlendirilir. Koşullu erişim, belirli bir hizmete erişimi kısıtlamak veya erişim izni vermek için bu değerlendirmeyi kullanır. Koşullu erişim ilkesi uyumluluk ilkesiyle birlikte kullanıldığında, yalnızca uyumlu cihazların hizmete erişmesine izin verilir. Uyumluluk ilkesi ve koşullu erişim ilkesi kullanıcıya dağıtılır. Kullanıcının hizmetlere erişirken kullandığı her cihaz, ilkelerle uyumluluk açısından denetlenir.

Cihazın uyumluluğunun değerlendirilebilmesi için, cihazı kullanan kullanıcıya dağıtılmış bir uyumluluk ilkesi olması gerektiğini unutmayın.
Kullanıcıya hiçbir uyumluluk ilkesi dağıtılmadıysa, cihaz uyumlu olarak kabul edilir ve hiçbir erişim kısıtlaması uygulanmaz.

Cihazlar ilkelerde ayarlanan koşulları karşılamadığında, kullanıcı cihazı kaydetme ve cihazın uyumlu olmasını önleyen sorunu düzeltme sürecinde yönlendirilir.

Tipik bir koşullu erişim akışı:

![Şemada, bir cihazın hizmete erişimine izin verilmesini veya bu erişimin engellenmesini belirlemek için kullanılan karar noktaları gösterilmektedir](../media/ConditionalAccess4.png)

## Koşullu erişim ilkesi nasıl yapılandırılır?
Microsoft **Şirket İçi Exchange**’e, **Exchange Online**’a, **Ayrılmış Exchange Online**’a, **SharePoint Online**’a ve **Skype Kurumsal Çevrimiçi Sürüm**’e erişimi yönetmek için koşullu erişim kullanın.

Koşullu erişimi ayarlamak için, bir cihaz uyumluluk ilkesi ve bir de koşullu erişim ilkesi ayarlayın.

Uyumluluk ilkesi geçiş kodu, şifreleme ve cihazın yazılım kilidinin kırılmış olup olmadığı gibi ayarları içerir. Cihazın uyumlu kabul edilmesi için bu kurallara uyması gerekir.

Koşullu erişim ilkesi ayarlayarak aşağıdakiler temelinde erişimi kısıtlayabilirsiniz:
- Cihaz uyumluluğunu durumu.
- Cihaz üzerinde çalışan platform.
- Hizmetlere erişmek için kullanılan uygulama türü.

Diğer Intune ilkelerinden farklı olarak, koşullu erişim ilkelerini dağıtmazsınız. Bunun yerine, ilkeyi yapılandırdığınızda ve ilkenin uygulanacağı kullanıcıları seçtiğinizde, ilke tüm hedeflenen kullanıcılara uygulanır. Bir kullanıcı bir ilke tarafından hedeflendiğinde, kaynaklara erişmek için kullandıkları her bir cihaz uyumlu olmalıdır.


## Sonraki adımlar
1. [Cihaz uyumluluk İlkesi ve nasıl çalıştığı hakkında bilgi edinin. ](introduction-to-device-compliance-policies-in-microsoft-intune.md)

2. [Uyumluluk ilkesi oluşturma](create-a-device-compliance-policy-in-microsoft-intune.md)

2.  Aşağıdakilerden biri için koşullu erişim ilkesi oluşturun:
> [!div class="op_single_selector"]
  - [Exchange Online için koşullu erişim ilkesi oluşturma](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Şirket İçi Exchange için koşullu erişim ilkesi oluşturma](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Yeni Ayrılmış Exchange Online için koşullu erişim ilkesi oluşturma](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Eski Ayrılmış Exchange Online için koşullu erişim ilkesi oluşturma](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [SharePoint Online için koşullu erişim ilkesi oluşturma](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  - [Skype Kurumsal Çevrimiçi için koşullu erişim ilkesi oluşturma](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  - [Dynamics CRM Online için koşullu erişim ilkesi oluşturma](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Sep16_HO3-->


