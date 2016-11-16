---
title: "MAM ilkeleri önkoşulları | Microsoft Intune"
description: "Bu konu başlığı altında, mobil uygulama yönetimi ilkelerini oluşturabilmeniz için gereken önkoşullar ve kullanıcıları ayarlama işlemleri açıklanır."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5778ccc632b72b3cca2593febeccbf7149591275
ms.openlocfilehash: 6d7843286369e2371ea204ac70d2e85e4c086d76


---

# Azure portalında mobil uygulama yönetimi ilkelerinizi yapılandırmaya hazırlanma
Bu konuda, Azure portalında mobil uygulama yönetimi (MAM) ilkeleri oluşturmadan **önce** tamamlamanız gereken önkoşullar ve adımlar açıklanmaktadır.

Intune MAM ilkelerinin şirket verilerinizi nasıl koruyabileceğini anlamak için bkz. [Mobil uygulama yönetimi ilkelerini kullanarak uygulamaları ve verileri koruma](protect-apps-and-data-with-microsoft-intune.md).

## Azure portalı nedir?
Azure portalı, MAM ilkeleri oluşturmak için yeni yönetim konsoludur ve aşağıdaki MAM senaryolarını destekler:
- **Intune’a kayıtlı cihazlar**
- **Başka bir MDM çözümü tarafından yönetilen cihazlar**
- **Hiçbir MDM çözümü tarafından yönetilmeyen cihazlar (KGC)**


Şu anda, hem **Intune Yönetici konsolu** hem de **Azure portalı** MAM ilkelerini yapılandırmanıza olanak sağlar.  Aşağıdakileri göz önünde bulundurun:

* **Azure portalında** oluşturduğunuz ilkeler yukarıda listelenen **tüm MAM senaryoları** için desteklenir. **Intune Yönetici konsolu** yalnızca **Intune’a kayıtlı ve Intune tarafından yönetilen cihazlar** için ilke oluşturmayı destekler.
* **Yeni ayarlar** yalnızca **Azure portalı**’na eklenebildiğinden Intune Yönetici konsolunda tüm MAM ilke ayarlarını göremeyebilirsiniz.
* Intune yönetici konsolu ve Azure portalının **her ikisinde** de MAM ilkeleri oluşturursanız, **uygulamalara Azure portalındaki ilke uygulanır ve kullanıcılara bu ilke dağıtılır**.
    * Intune yönetici konsolunda oluşturulan MAM ilkeleri, Azure portalına aktarılamaz.  MAM ilkeleri, Azure portalında yeniden oluşturulmalıdır.
* Uygulama ve uygulama yapılandırma ilkeleri dağıtma gibi diğer **uygulama yönetimi özellikleri** şu anda yalnızca **Intune yönetici konsolunda** kullanılabilir.


Azure portalını yeni kullanmaya başladıysanız, Azure portalını kullanmanın temellerini öğrenmek için [Microsoft Intune MAM ilkeleri için Azure portalı](azure-portal-for-microsoft-intune-mam-policies.md) konusunu okuyun.

Intune yönetici konsolunda MAM ilkesi oluşturma yönergeleri için bkz. [Microsoft Intune konsolunda mobil uygulama yönetimi ilkelerini yapılandırma ve dağıtma](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).


##  Desteklenen platformlar
- iOS 8.1 veya üzeri

- Android 4 veya üzeri

>[!NOTE]
>Windows cihazları bu mobil uygulama yönetimi ilkelerini desteklemez. Ancak, Windows 10 cihazlarını Intune'a kaydettiğinizde, benzer bir işlevsellik sunan Windows Bilgi Koruması’nı kullanabilirsiniz. Ayrıntılar için bkz. [Windows Bilgi Koruması’nı (WIP) kullanarak kurumsal verilerinizi koruma](https://technet.microsoft.com/en-us/itpro/windows/keep-secure/protect-enterprise-data-using-wip).

##  Desteklenen uygulamalar
* **Microsoft uygulamaları:** Bu uygulamalarda Intune App SDK’sı yerleşik olarak bulunur ve MAM ilkelerini uygulamadan önce başka işlem yapmanız gerekmez.
Desteklenen Microsoft uygulamalarının tam listesini görmek için Microsoft Intune uygulama iş ortakları sayfasında [Microsoft Intune mobil uygulama galerisine](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) gidin. Desteklenen senaryoları ve platformları görmek, ayrıca uygulamanın birden çok kimliği destekleyip desteklemediğini anlamak için, uygulamaya tıklayın.
* **Kuruluşunuzun iş kolu uygulamaları:** Bunlar, MAM ilkelerini uygulamadan önce Intune Uygulama SDK’sını içerecek şekilde uygulamaların hazırlanmasını gerektirir.

  * Intune tarafından yönetilen cihazlar için, bkz. [MAM için uygulamaların nasıl hazırlanacağına karar verme](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).
  * Çalışana ait cihazlar gibi yönetilmeyen cihazlar veya başka bir mobil cihaz yönetim çözümü tarafından yönetilen cihazlar için bkz. [Intune’a kayıtlı olmayan cihazlardaki iş kolu uygulamalarını ve verilerini koruma](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

## Önkoşullar

-   Microsoft Intune için bir abonelik.    Kullanıcıların, MAM ilkeleri olan uygulamaları alabilmesi için [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] lisanslarına sahip olmaları gerekir.
Şu anda cihazlarınızı yönetmek için [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] kullanıyorsanız [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] aboneliğiniz zaten vardır.  Ayrıca, bir Enterprise Mobility Suite (EMS) lisansı satın aldıysanız da [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] aboneliğiniz vardır. MAM özelliklerini kullanıma almak için [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] uygulamasını deniyorsanız [Microsoft Intune web sayfasında](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/) bir deneme hesabı alabilirsiniz.

    [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] aboneliğinizin olup olmadığını denetlemek için **Faturalama** sayfasına gidin.  [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] seçeneğini aboneliklerde **Etkin** olarak görmeniz gerekir.

-   Aşağıdakiler için gereken bir Office 365 aboneliği:
  - Birden çok kimliği destekleyen uygulamalara MAM ilkeleri uygulamak için.
  - SharePoint Online ve Exchange Online iş hesaplarını oluşturmak için. Exchange şirket içi ve SharePoint şirket içi desteklenmez.
-   Modern kimlik doğrulaması için Skype Kurumsal Çevrimiçi Sürüm. Daha fazla bilgi için bkz. [Modern kimlik doğrulamayı etkinleştirme](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).


- Kullanıcıları oluşturmak için Azure Active Directory (Azure AD). Azure AD, uygulamayı açan ve iş kimlik bilgilerini giren kullanıcıların kimliğini doğrular.

    > [!NOTE]
    > Kullanıcı gruplarının Azure AD içinde kurulması gerekir. Intune kullanıcı grupları Azure portalında MAM ilkeleri dağıtmak için kullanılamaz.

### Kullanıcılar oluşturma ve Microsoft Intune lisansları atama

1.  Yönetici kimlik bilgilerinizle [Office portalında](http://portal.office.com) oturum açın.

2.  Kullanıcıları, **bu** konunun [Kullanıcı ekleme](https://docs.microsoft.com/en-us/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-2) bölümünde açıklandığı gibi ekleyin ve Intune lisansları atayın. Bir kullanıcıya Office portalı, Azure AD portalı ve Azure önizleme portalı erişimi vermek için, kullanıcıya **Genel yönetici rolü** atayın.

5.  MAM ilkeleri Azure Active Directory'deki kullanıcı gruplarına dağıtılır. MAM ilkelerinize yönelik kullanıcı grupları oluşturmak için **bu** konunun [Kullanıcı grubu oluşturma](https://docs.microsoft.com/en-us/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-3) bölümünde açıklandığı gibi bir kullanıcı grubu oluşturun.

### Genel olmayan yönetici kullanıcılar

Genel yöneticiler [Azure portalına](https://portal.azure.com) erişebilir.  Genel yönetici olmayan kullanıcıların ilkeleri yapılandırabilmesini ve diğer mobil uygulama yönetim görevlerini yapabilmesini istiyorsanız kullanıcılara katkıda bulunan rolünü atayabilirsiniz. Ayrıntılı yönergeler için bkz. [Azure aboneliği kaynaklarınıza erişimi yönetmek için rol atama](https://azure.microsoft.com/en-us/documentation/articles/role-based-access-control-configure/).

---------------------------------

Aşağıdaki tabloda yönetici kullanıcılara atayabileceğiniz rol ve izinler listelenir.

|||
|--|----|
|**Rol**|**İzinler**|
|Genel yönetici (Office 365 portalı)|Office 365 portalına ve Azure AD portalına erişim.<br /><br />Azure portalına erişim (hem rol yönetimi hem de mobil uygulama yönetimi görevlerini gerçekleştirebilir).|
|Sahip (Azure portalı)|Azure portalına erişim (hem rol yönetimi hem de mobil uygulama yönetimi görevlerini gerçekleştirebilir).|
|Katkıda bulunan (Azure portalı)|Azure portalına erişim (yalnızca mobil uygulama yönetimi görevlerini gerçekleştirebilir).|




## Sonraki adımlar
[Microsoft Intune ile mobil uygulama yönetimi ilkeleri oluşturma ve dağıtma](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


