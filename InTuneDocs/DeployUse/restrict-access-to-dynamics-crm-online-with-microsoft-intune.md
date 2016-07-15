---
title: "Dynamics CRM Online’a erişimi kısıtlama | Microsoft Intune"
description: 
keywords: 
author: karthikaraman
manager: jeffgilb
ms.date: 06/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f1c4522b-5a34-4f5a-89d2-7809c4352af7
ms.reviewer: chrisgre
ms.suite: ems
ms.sourcegitcommit: 89e522a99687fc9b6e82db9f721858d17afdce6a
ms.openlocfilehash: 8f90f99d621d7edebcb7a4c67e0774da59098df7


---

# Dynamics CRM Online’a erişimi kısıtlama
Microsoft Dynamics CRM Online’a erişimi, iOS ve Android cihazlardan, Microsoft Intune koşullu erişimle denetleyebilirsiniz.  Intune koşullu erişimi iki bileşenden oluşur:
* Cihazın uyumlu kabul edilmesi için uyması gereken [cihaz uyumluluk ilkesi](introduction-to-device-compliance-policies-in-microsoft-intune.md).
* Cihazın hizmete erişebilmek için uyması gereken koşulları sizin belirlediğiniz [koşullu erişim ilkesi](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).

Koşullu erişimin nasıl çalıştığı hakkında daha fazla bilgi edinmek için, [e-posta, 0365 hizmetlerine ve diğer hizmetlere erişimi kısıtlama](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) makalesini okuyun.

Hedeflenen bir kullanıcı kendi cihazında Dynamics CRM uygulamasını kullanmayı denerse, aşağıdaki değerlendirme yapılır:

![Cihazın hizmete erişimine izin verilmesini veya bu erişimin engellenmesini belirlemek için kullanılan karar noktalarının gösterildiği diyagram](../media/mdm-ca-dynamics-crm-flow-diagram.png)

Dynamics CRM Online’a erişmesi gereken cihaz:
* **Android** veya **iOS** cihazı olmalıdır.
* Microsoft Intune ile **kaydedilmelidir**.
* Dağıtılmış tüm Microsoft Intune uyumluluk ilkeleriyle **uyumlu** olmalıdır.

Cihaz durumu, Azure Active Directory'de depolanır; bu durumda belirttiğiniz koşullara göre erişim izni verilir veya erişim engellenir.

Bir koşul karşılanmazsa, oturum açtığında kullanıcıya şu iletilerden biri sunulur:
* Cihaz Microsoft Intune’a kaydedilmediyse veya Azure Active Directory'ye kayıtlı değilse, şirket portalı uygulamasının nasıl yükleneceğine ve nasıl kayıt yapılacağına ilişkin yönergeleri içeren bir ileti görüntülenir.
* Cihaz uyumlu değilse, kullanıcıyı, sorun hakkında bilgi bulabileceği ve sorunu düzeltebileceği Microsoft Intune Şirket Portalı Web sitesine veya Şirket Portalı uygulamasına yönlendiren bir ileti görüntülenir.

## Dynamics CRM Online için koşullu erişim yapılandırma  
### Adım 1: Active Directory güvenlik gruplarını yapılandırma

Başlamadan önce koşullu erişim ilkesi için Azure Active Directory güvenlik gruplarını yapılandırın. Bu grupları **Office 365 yönetim merkezinde** yapılandırabilirsiniz. Bu gruplar, ilkede kullanıcıları hedeflemek veya muaf tutmak için kullanılır. Bir kullanıcı bir ilke tarafından hedeflendiğinde, kaynaklara erişmek için kullandıkları her bir cihaz uyumlu olmalıdır.

Dynamics CRM ilkesinde kullanmak üzere iki grup türü belirtebilirsiniz:
* **Hedeflenen gruplar** - İlkenin uygulanacağı kullanıcı gruplarını içerir.
* **Muaf tutulan gruplar** - İlkeden muaf tutulan kullanıcı gruplarını içerir.

Bir kullanıcı her iki gruptaysa ilkeden muaf tutulur.

### 2. Adım: Uyumluluk ilkesi yapılandırma ve dağıtma
Bir uyumluluk ilkesi [oluşturun](create-a-device-compliance-policy-in-microsoft-intune.md) ve ilkeden etkilenecek olan tüm cihazlara [dağıtın](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md). Bunlar, Hedeflenen gruplardaki kullanıcılar tarafından kullanılan tüm cihazlar olacaktır.

> [!NOTE]
> [!NOTE] Uyumluluk ilkeleri Microsoft Intune gruplarına dağıtılırken, koşullu erişim ilkeleri Azure Active Directory güvenlik gruplarına hedeflenir.

> [!IMPORTANT]
> [!IMPORTANT] Uyumluluk İlkesi dağıtmadıysanız, cihazlar uyumlu olarak değerlendirilir.

Hazır olduğunuzda 3. Adım‘a ilerleyin.
### Adım 3: Dynamics CRM ilkesi yapılandırma
Ardından, ilkeyi yalnızca yönetilen ve uyumlu cihazların Dynamics CRM’ye erişebileceği şekilde yapılandırın. Bu ilke Azure Active Directory’de depolanır.

1.  Microsoft Intune yönetim konsolunda, **İlke > Koşullu Erişim > Dynamics CRM Online İlkesi**’ni seçin.

  ![Dynamics CRM Online koşullu erişim ilkesi sayfasının ekran görüntüsü](../media/mdm-ca-dynamics-crm-policy-configuration.png)

2.  **Koşullu erişimi etkinleştir** ilkesini seçin.
3.  **Uygulama erişimi** altında aşağıdakilere koşullu erişim ilkesini uygulamayı seçebilirsiniz:
  * **iOS**
  * **Android**
4.  **Hedeflenen Gruplar** altında, ilkenin geçerli olacağı Azure Active Directory güvenlik gruplarını seçmek için **Değiştir**’i seçin. Bunu tüm kullanıcılara veya yalnızca seçilmiş bir kullanıcı grubuna hedefleyebilirsiniz.
5.  **Muaf Tutulan Gruplar** altında, bu ilkeden muaf tutulan Active Directory güvenlik gruplarını seçmek için isteğe bağlı olarak **Değiştir**’i seçin.
6.  İşiniz bittiğinde **Kaydet**’i seçin.

Artık Dynamics CRM için koşullu erişimi yapılandırdınız. Koşullu erişim ilkesini dağıtmanız gerekmez, hemen geçerli olur.
##  Uyumluluk ve koşullu erişim ilkeleri izleme

 **Gruplar** çalışma alanında, cihazlarınızın koşullu erişim durumunu görüntüleyebilirsiniz.

Herhangi bir mobil cihaz grubunu seçin ve ardından **Cihazlar** sekmesinde aşağıdaki **Filtreler**arasından birini seçin:
* **AAD ile kayıtlı olmayan cihazlar** - Bu cihazlar Dynamics CRM’den engellenir.
* **Uyumlu olmayan cihazlar** - Bu cihazlar Dynamics CRM’den engellenir.
* **AAD ile kayıtlı ve uyumlu cihazlar** - Bu cihazlar Dynamics CRM’ye erişebilir.

##  Sonraki adımlar
[Exchange Online'a erişim kısıtlama](restrict-access-to-exchange-online-with-microsoft-intune.md)

[Şirket içi Exchange için erişim kısıtlama](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
[SharePoint Online'a erişimi kısıtlama](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

[Skype Kurumsal Çevrimiçi’ne erişimi kısıtlama](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)



<!--HONumber=Jul16_HO2-->


