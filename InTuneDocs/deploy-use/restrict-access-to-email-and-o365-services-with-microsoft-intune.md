---
title: "E-posta ve Office 365 hizmetlerine erişimi kısıtlama | Microsoft Intune"
description: "Bu konu başlığı altında, SharePoint Online’daki ve diğer hizmetlerdeki şirket e-postasına ve şirket verilerine yalnızca uyumlu cihazların erişmesine izin vermek için koşullu erişimi nasıl kullanabileceğiniz açıklanır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c564d292-b83b-440d-bf08-3f5b299b7a5e
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 5665ca431eb186d4378953b7047228e07ae9dc60


---

# <a name="restrict-access-to-email-office-365-and-other-services-with-microsoft-intune"></a>Microsoft Intune ile e-posta, Office 365 hizmetleri ve diğer hizmetlere erişimi kısıtlama
Intune koşullu erişim kullanarak, şirket e-postanıza, Office 365’e ve diğer hizmetlere erişimi kısıtlayabilirsiniz. Intune koşullu erişim özelliği, şirketinizin e-postasına ve Office 365 hizmetlerine erişimin, ayarladığınız kurallara uyan cihazlarla sınırlı olduğundan emin olmanızı sağlar.
## <a name="how-does-conditional-access-work"></a>Koşullu erişim nasıl çalışır?
Uyumluluk ilkesi ayarları kullanarak cihazın uyumluluğunu değerlendirebilirsiniz. Koşullu erişim, belirli bir hizmete erişimi kısıtlamak veya erişim izni vermek için bu değerlendirmeyi kullanır. Koşullu erişim ilkesini uyumluluk ilkesiyle birlikte kullandığınızda, yalnızca uyumlu cihazların hizmete erişmesine izin verilir. Uyumluluk ilkesi ve koşullu erişim ilkesi kullanıcıya dağıtılır. Kullanıcının hizmetlere erişirken kullandığı her cihaz, ilkelerle uyumluluk açısından denetlenir.

Cihazın uyumluluğunun değerlendirilebilmesi için cihazı kullanan kullanıcıya dağıtılmış bir uyumluluk ilkesi olması gerektiğini unutmayın.
Kullanıcıya hiçbir uyumluluk ilkesi dağıtılmadıysa, cihaz uyumlu olarak kabul edilir ve hiçbir erişim kısıtlaması uygulanmaz.

Cihazlar ilkelerde ayarlanan koşulları karşılamadığında, kullanıcı cihazı kaydetme ve cihazın uyumlu olmasını önleyen sorunu düzeltme sürecinde yönlendirilir.

Tipik bir koşullu erişim akışı:

![Şemada, bir cihazın hizmete erişimine izin verilmesini veya bu erişimin engellenmesini belirlemek için kullanılan karar noktaları gösterilmektedir](../media/ConditionalAccess4.png)

## <a name="how-to-configure-conditional-access"></a>Koşullu erişimi yapılandırma
Microsoft **Şirket İçi Exchange**’e, **Exchange Online**’a, **Ayrılmış Exchange Online**’a, **SharePoint Online**’a ve **Skype Kurumsal Çevrimiçi Sürüm**’e erişimi yönetmek için koşullu erişim kullanın.

Koşullu erişimi ayarlamak için bir cihaz uyumluluk ilkesi ve koşullu erişim ilkesi ayarlayın.

Uyumluluk ilkesi geçiş kodu, şifreleme ve cihazın yazılım kilidinin kırılmış olup olmadığı gibi ayarları içerir. Cihazın uyumlu kabul edilmesi için bu kurallara uyması gerekir.

Koşullu erişim ilkesi ayarlayarak aşağıdakiler temelinde erişimi kısıtlayabilirsiniz:
- Cihaz uyumluluğunu durumu.
- Cihazda çalışan platform.
- Hizmetlere erişmek için kullanılan uygulamaların türü.

Diğer Intune ilkelerinden farklı olarak, koşullu erişim ilkelerini dağıtmazsınız. Bunun yerine, ilkeyi yapılandırdıktan ve ilkenin uygulanacağı kullanıcıları seçtikten sonra, ilke tüm hedeflenen kullanıcılara uygulanır. Bir kullanıcı ilke tarafından hedeflendiğinde, kaynaklara erişmek için kullandıkları her bir cihaz uyumlu olmalıdır.


## <a name="next-steps"></a>Sonraki adımlar
1. [Cihaz uyumluluk ilkesi ve nasıl çalıştığı hakkında bilgi edinin](introduction-to-device-compliance-policies-in-microsoft-intune.md).

2. [Uyumluluk ilkesi oluşturma](create-a-device-compliance-policy-in-microsoft-intune.md).

2.  Aşağıdakilerden biri için koşullu erişim ilkesi oluşturun:
> [!div class="op_single_selector"]
  - [Exchange Online için koşullu erişim ilkesi oluşturma](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Şirket İçi Exchange için koşullu erişim ilkesi oluşturma](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Yeni Ayrılmış Exchange Online için koşullu erişim ilkesi oluşturma](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Eski Ayrılmış Exchange Online için koşullu erişim ilkesi oluşturma](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [SharePoint Online için koşullu erişim ilkesi oluşturma](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  - [Skype Kurumsal Çevrimiçi Sürüm için koşullu erişim ilkesi oluşturma](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  - [Dynamics CRM Online için koşullu erişim ilkesi oluşturma](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


