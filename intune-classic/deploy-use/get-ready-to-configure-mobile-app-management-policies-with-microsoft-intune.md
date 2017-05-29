---
title: "MAM ilkeleri önkoşulları | Microsoft Docs"
description: "Bu konu başlığı altında, mobil uygulama yönetimi ilkeleri oluşturmadan önce kullanıcıları ayarlamak için önkoşullar açıklanır."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 3c209a350a7de7ba7ddb71468c5cd4230dcf5423
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="get-ready-to-configure-app-protection-policies-in-the-azure-portal"></a>Azure portalında uygulama koruma ilkelerini yapılandırmaya hazırlanma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Bu konuda, Azure portalında uygulama koruma ilkeleri oluşturmadan **önce** tamamlamanız gereken önkoşullar ve adımlar açıklanmaktadır.

Intune uygulama koruma ilkelerinin şirket verilerinizi nasıl koruyabileceğini anlamak için bkz. [Uygulama koruma ilkelerini kullanarak uygulamaları ve verileri koruma](protect-apps-and-data-with-microsoft-intune.md).

## <a name="what-is-the-azure-portal"></a>Azure portalı nedir?

Azure portalı, uygulama koruma ilkeleri oluşturmaya yönelik yeni yönetim konsoludur. Aşağıdaki MAM senaryolarını destekler:
- Intune’a kayıtlı cihazlar
- Başka bir Mobil Cihaz Yönetimi (MDM) çözümü tarafından yönetilen cihazlar
- Hiçbir MDM çözümü tarafından yönetilmeyen cihazlar (KGC)

Şu anda, hem **Intune Yönetici konsolu** hem de **Azure portalı**, uygulama koruma ilkelerini yapılandırmanıza olanak sağlar.  Aşağıdakileri göz önünde bulundurun:

* **Azure portalında** oluşturduğunuz ilkeler daha önce listelenen **tüm MAM senaryoları** için desteklenir. **Intune Yönetici konsolu** yalnızca **Intune’a kayıtlı ve Intune tarafından yönetilen cihazlar** için ilke oluşturmayı destekler.

* **Yeni ayarlar** yalnızca **Azure portalına** eklenebildiğinden, Intune yönetici konsolunda tüm uygulama koruma ilke ayarlarını göremeyebilirsiniz.

* Intune yönetici konsolu ve Azure portalının **her ikisinde** de uygulama koruma ilkeleri oluşturursanız, **uygulamalara Azure portalındaki ilke uygulanır ve kullanıcılara bu ilke dağıtılır**.
    * Intune yönetici konsolunda oluşturulan uygulama koruma ilkeleri, Azure portalına aktarılamaz.  Uygulama koruma ilkeleri, Azure portalında yeniden oluşturulmalıdır.


* Uygulama ve uygulama yapılandırma ilkeleri dağıtma gibi diğer **uygulama yönetimi özellikleri** şu anda yalnızca **Intune yönetici konsolunda** kullanılabilir.


Azure portalını yeni kullanmaya başladıysanız, Azure portalını kullanmanın temellerini öğrenmek için bkz. [Microsoft Intune uygulama koruma ilkeleri için Azure portalı](azure-portal-for-microsoft-intune-mam-policies.md).

Intune yönetici konsolunda uygulama koruma ilkesi oluşturma yönergeleri için bkz. [Microsoft Intune konsolunda uygulama koruma ilkelerini yapılandırma ve dağıtma](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).


##  <a name="supported-platforms"></a>Desteklenen platformlar
- iOS 8.1 veya üzeri
- Android 4 veya üzeri
- Windows 10

>[!NOTE]
>1703 sürümünden başlayarak kayıt olmadan MAM senaryosunda Windows 10 cihazları için uygulama koruma ilkeleri tanımlanabilir. Ayrıntılar için bkz. [Windows Bilgi Koruması’nı (WIP) kullanarak kurumsal verilerinizi koruma](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).

##  <a name="supported-apps"></a>Desteklenen uygulamalar
* **Microsoft uygulamaları:** Bu uygulamalarda Intune App SDK’sı yerleşik olarak bulunur ve uygulama koruma ilkelerini uygulamadan önce başka işlem yapmanız gerekmez.
Desteklenen Microsoft uygulamalarının tam listesini görmek için Microsoft Intune uygulama iş ortakları sayfasında [Microsoft Intune mobil uygulama galerisine](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) gidin. Desteklenen senaryoları ve platformları görmek, ayrıca uygulamanın birden çok kimliği destekleyip desteklemediğini anlamak için, uygulamaya tıklayın.

* **Kuruluşunuzun iş kolu uygulamaları:** uygulama koruma ilkelerini uygulamadan önce bu uygulamaları Intune Uygulama SDK’sını içerecek şekilde hazırlamanız gerekir.

  * Intune tarafından yönetilen cihazlar için, bkz. [MAM için uygulamaların nasıl hazırlanacağına karar verme](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).

  * Çalışana ait cihazlar gibi yönetilmeyen cihazlar veya başka bir mobil cihaz yönetim çözümü tarafından yönetilen cihazlar için bkz. [Intune’a kayıtlı olmayan cihazlardaki iş kolu uygulamalarını ve verilerini koruma](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

## <a name="prerequisites"></a>Önkoşullar

-   **Microsoft Intune Aboneliği**. Kullanıcıların, uygulama koruma ilkeleri olan uygulamaları alabilmesi için Intune lisanslarına sahip olmaları gerekir.
Şu anda cihazlarınızı yönetmek için Intune kullanıyorsanız Intune aboneliğiniz zaten vardır. Ayrıca, bir Enterprise Mobility Suite (EMS) lisansı satın aldıysanız da Intune aboneliğiniz vardır. MAM özelliklerini kullanıma almak için Intune’u deniyorsanız [Microsoft Intune sayfasında](https://www.microsoft.com/server-cloud/products/microsoft-intune/) bir deneme hesabı alabilirsiniz.

    Intune aboneliğiniz olduğunu doğrulamak için **Faturalama** sayfasına gidin.  Aboneliğiniz varsa, Intune seçeneğini aboneliklerde **Etkin** olarak görmeniz gerekir.

-   Aşağıdakiler için gereken **bir Office 365 aboneliği**:

  - Birden çok kimliği destekleyen uygulamalara uygulama koruma ilkeleri uygulamak için.

  - SharePoint Online ve Exchange Online iş hesaplarını oluşturmak için. Exchange şirket içi ve SharePoint şirket içi desteklenmez.

-   **Modern kimlik doğrulaması için Skype Kurumsal Çevrimiçi Sürüm**. Daha fazla bilgi için bkz. [Modern kimlik doğrulamayı etkinleştirme](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).


- Kullanıcıları oluşturmak için Azure Active Directory (Azure AD). Azure AD, uygulamayı açan ve iş kimlik bilgilerini giren kullanıcıların kimliğini doğrular.

    > [!NOTE]
    > Kullanıcı gruplarının Azure AD içinde kurulması gerekir. Intune kullanıcı grupları Azure portalında uygulama koruma ilkeleri dağıtmak için kullanılamaz.

### <a name="create-users-and-assign-microsoft-intune-licenses"></a>Kullanıcılar oluşturma ve Microsoft Intune lisansları atama

1.  Yönetici kimlik bilgilerinizle [Office portalı](https://portal.office.com)’nda oturum açın.

2.  **Intune değerlendirme kılavuzu**’nun [Intune 30 günlük değerlendirmesini tamamlamak için adımlar](/intune-classic/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune) bölümünde açıklandığı gibi kullanıcıları ekleyin ve ardından Intune lisanslarını atayın. Bir kullanıcıya Office portalı, Azure AD portalı ve Azure önizleme portalı erişimi vermek için, kullanıcıya **Genel yönetici rolü** atayın.

5.  Uygulama koruma ilkeleri Azure Active Directory'deki kullanıcı gruplarına dağıtılır. Uygulama koruma ilkelerinize yönelik kullanıcı grupları oluşturmak için **Değerlendirme aboneliği kullanıcılarını ve cihazlarını düzenlemek için gruplar oluşturun** konusunun [Kullanıcı grubu oluşturma](/intune-classic/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-3) bölümünde açıklandığı gibi bir kullanıcı grubu oluşturun.

### <a name="assign-roles-to-non-global-admin-users"></a>Genel olmayan yönetici kullanıcılara roller atama

Genel yöneticiler [Azure portalına](https://portal.azure.com) erişebilir.  Genel yönetici olmayan kullanıcıların ilkeleri yapılandırabilmesini ve diğer mobil uygulama yönetim görevlerini yapabilmesini istiyorsanız, [Azure abonelik kaynaklarınıza erişimi yönetmek için rol atamalarını kullanma](https://azure.microsoft.com/documentation/articles/role-based-access-control-configure/) makalesini inceleyin.

## <a name="next-steps"></a>Sonraki adımlar
[Microsoft Intune ile uygulama koruma ilkeleri oluşturma ve dağıtma](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)

