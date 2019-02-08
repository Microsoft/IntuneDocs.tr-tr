---
title: Intune ile cihaz tabanlı koşullu erişim ayarlama
titlesuffix: Microsoft Intune
description: Microsoft Intune cihaz uyumluluğu ve mobil uygulama yönetimi göre cihaz tabanlı koşullu erişim ilkesi oluşturmayı öğrenin.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 12/11/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5c9fc2b2e973fdebfd303382e88630ef9999b517
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55844165"
---
# <a name="create-a-device-based-conditional-access-policy"></a>Cihaz tabanlı koşullu erişim ilkesi oluşturma

Intune ile mobil cihaz uyumluluğu için erişim denetimleri ekleyerek Azure Active Directory'de koşullu erişim geliştirebilirsiniz. Cihazların uyumlu olmasını gereksinimlerini tanımlayan Intune uyumluluk ilkesi oluşturduktan sonra izin vermek veya uygulama ve hizmetlere erişimi engellemek için bir cihazın uyumluluk durumunu kullanabilirsiniz. Bu ayarı kullanan bir koşullu erişim ilkesi oluşturarak bunu yapabilirsiniz **cihazın uyumlu olarak işaretlenmesini gerektir**. 

Koşullu erişim ilkesi uygulama veya hizmetleri korumak istediğiniz, koşullar altında uygulamalarına veya hizmetlerine erişilebilir ve ilkenin uygulandığı kullanıcı belirtir. Koşullu erişim, Azure Active Directory'de yapılandırılabilir bir Azure AD premium özelliği olmakla birlikte aynı bu ilkelerden Intune portalından da ayarlayabilirsiniz. 

> [!IMPORTANT]
> Koşullu erişimi ayarlama önce bunlar belirli gereksinimleri karşılaması üzerinde göre cihazlarını değerlendirmek için Intune cihaz uyumluluk ilkeleri ayarlamak gerekir. Bkz: [ıntune cihaz uyumluluk ilkelerini kullanmaya başlama](device-compliance-get-started.md).

## <a name="create-conditional-access-policy"></a>Koşullu erişim ilkesi oluşturma

1.  Intune portalında **koşullu erişim** > **ilkeleri** > **yeni ilke**.
   
    ![Yeni bir koşullu erişim ilkesi oluşturma](media/create-conditional-access-intune/create-ca.png)
 
2.  **Atamalar** altında **Kullanıcılar ve gruplar**’ı seçin. 
3.  Üzerinde **INCLUDE** sekmesinde, kullanıcılar veya gruplar bu koşullu erişim ilkesini uygulamak istediğiniz tanımlayın. Kim içerecek şekilde belirledikten sonra kullanabileceğiniz **hariç** tüm kullanıcıları, rolleri veya bu ilkeden dışlamak istediğiniz grupları varsa sekmesi.  
    - **Tüm kullanıcılar**: Tüm kullanıcılar ve gruplar, iç ve Konuk kullanıcılar dahil olmak üzere ilkeyi uygulamak için bu seçeneği belirleyin.
  
    - **Kullanıcıları ve grupları seçme**: Bu seçeneği belirleyin ve bir veya daha fazla aşağıdaki seçeneklerden birini belirtin:
  
      a. **Tüm Konuk kullanıcılar**: Dahil edilecek veya hariç dış konuk kullanıcılara (örneğin, iş ortakları, dış ortak çalışanlar) için bu seçeneği belirleyin
       
      b. **Dizin rolleri**: Dahil edilecek veya hariç bu rolleri atanmış kullanıcılar için bir veya daha fazla Azure AD rolleri seçin.
      
      c. **Kullanıcılar ve gruplar**: Aramak ve bireysel kullanıcıları veya grupları dahil etmek veya hariç tutmak istediğiniz seçmek için bu seçeneği belirleyin.
     
       > [!TIP]  
       > İlkenin beklendiği gibi çalıştığından emin olmak için kullanıcıların küçük bir gruba göre test edin.
4.  **Done** (Bitti) öğesini seçin.
5.  **Atamalar** altında **Bulut uygulamaları**’nı seçin. 
6.  Üzerinde **Ekle sekmesinin**, uygulamalar ve bu koşullu erişim ilkesi ile korumak istediğiniz hizmetleri belirleyin. Kullanabileceğiniz sonra **hariç** herhangi bir uygulama veya hizmetler bu ilkeden dışlamak istediğiniz varsa sekmesi.
    - **Tüm bulut uygulamaları**: Tüm uygulamalarında ilkeyi uygulamak için bu seçeneği belirleyin.
      > [!IMPORTANT]  
      > Azure portalına erişim için Microsoft Azure Management uygulaması bu listede bulunuyor. Kullandığınızdan emin olun **hariç** ya da burada sekmesinde veya **kullanıcılar ve gruplar** , (veya kullanıcılar veya gruplar belirlediğiniz) oluşturabileceksiniz Azure portalında oturum açmak emin olmak için Seçenekler. 

    - **Uygulamaları seçin**: Bu seçeneği seçin, **seçin**ve ardından aramak ve korumak istediğiniz hizmetleri ve uygulamaları seçmek için uygulamalar listesini kullanın.
    
      ![Yeni bir koşullu erişim ilkesi oluşturma](media/create-conditional-access-intune/create-ca-select-apps.png)

7.  **Done** (Bitti) öğesini seçin.
8.  Altında **atamaları**seçin **koşullar**.
    - **Oturum açma riski**: Bu ilke ile Azure AD kimlik koruması oturum açma riski algılama kullanmak için Evet'i seçin ve ardından ilkenin uygulanması gereken oturum açma risk düzeyleri seçin.
    - **Cihaz platformları**: Üzerinde **INCLUDE** sekmesinde, bu koşullu erişim ilkesi için uygulamak istediğiniz cihaz platformlarını destekleyeceğinizi. Kullanım **hariç** platformları bu ilkeden dışlamak için sekmesinde.
    - **Konumları**: Üzerinde **INCLUDE** sekmesinde, ilkenin herhangi bir konum, BT departmanınızın denetimi altında olan güvenilir ağ konumlarını veya belirli ağ konumlarını uygulanıp uygulanmayacağını belirtin. Kullanım **hariç** ağ konumlarını bu ilkeden dışlamak için sekmesinde. 
    - **İstemci uygulamaları**: Seçin **Evet** tarayıcı uygulamaları, mobil uygulamalar ve masaüstü istemciler için ilke uygulanacaksa belirtmek için. Belirleyebilirsiniz **Modern kimlik doğrulaması istemcileri** (örneğin, iOS için Outlook veya Android için Outlook) ve **Exchange ActiveSync istemcileri**.
    - **Cihaz durumu**: Cihaz uyumlu olarak işaretlenmiş veya Evet'i seçin ve özel olarak cihaz hibrit Azure AD'ye katıldı durumlar hariç, koşullu erişim ilkesi için tüm cihaz durumları uygulanır (veya her ikisi de).
    
      ![Yeni bir koşullu erişim ilkesi oluşturma](media/create-conditional-access-intune/create-ca-device-platforms.png)

      > [!TIP]  
      > Her ikisi de korumak istiyorsanız **Modern kimlik doğrulaması** istemcileri ve **Exchange ActiveSync istemcileri**, iki ayrı bir koşullu erişim ilkeleri, her istemci türü için bir tane oluşturun. Exchange ActiveSync modern kimlik doğrulamayı desteklemesine rağmen Exchange ActiveSync tarafından desteklenen tek koşul platformudur. Multi-Factor authentication dahil, diğer koşullar desteklenmez. Etkili bir şekilde erişim Exchange Online için Exchange ActiveSync'ten korumak için bulut uygulaması, Office 365 Exchange Online ve Exchange ActiveSync istemci uygulaması, seçili yalnızca desteklenen platformlara Uygula ilkesiyle belirten bir koşullu erişim ilkesi oluşturun.

9.  **Done** (Bitti) öğesini seçin.
10. **Erişim denetimleri** altında **Ver**’i seçin. Temel ayarlamış olduğunuz koşullara ne yapılandırın.  Aşağıdaki seçeneklerden birini seçebilirsiniz:
    - **Erişimi engelle**: Bu ilkede belirlenen kullanıcıları belirlediğiniz koşullarda uygulamalara erişim reddedilir.
    - **Erişim ver**: Bu ilkede belirtilen kullanıcıların erişim verilir, ancak aşağıdaki ek eylemlerden herhangi birini gerektirir:
      - **Çok faktörlü kimlik doğrulaması gerektiren**: Kullanıcı, bir telefon araması veya kısa mesaj gibi ek güvenlik gereksinimleri tamamlanması gerekir.
      - **Cihazın uyumlu olarak işaretlenmesini gerektir**: Cihazın Intune ile uyumlu olması gerekir. Kullanıcı, cihaz uyumlu değilse, Cihazınızı ıntune'a kaydetme seçeneği sunulur. 
      - **Hibrit Azure AD'ye katılmış hizmet gerektir**: Cihazların hibrit Azure AD'ye katılmış olması gerekir.
      - **Onaylı istemci uygulaması gerektir**: Cihaz, onaylı istemci uygulamalarını kullanmalıdır. 
      - **Birden çok denetim için**: Seçin **seçilen tüm denetimleri gerekli** böylece bir cihaz, uygulamaya erişmeye çalıştığında yukarıdaki gereksinimlerinin tümüne uygulanır.
    
      ![Erişim verme ayarlarını denetler.](media/create-conditional-access-intune/create-ca-grant-access-settings.png)
 
11. **İlkeyi etkinleştir** altında **Açık**’ı seçin.
     
     ![İlkeyi etkinleştir](media/create-conditional-access-intune/enable-policy.png)

12. **Oluştur**’u seçin.

## <a name="see-also"></a>Ayrıca bkz.
[Intune ile uygulama tabanlı koşullu erişim](app-based-conditional-access-intune.md)
