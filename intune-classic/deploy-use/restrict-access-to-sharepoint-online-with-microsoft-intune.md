---
title: "SharePoint Online'ı koruma"
description: "SharePoint Online’daki şirket verilerini korumak ve erişimi denetlemek için koşullu erişim kullanın."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b088e5a0-fd4a-4fe7-aa49-cb9c8cfb1585
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f86508d9b187e0026a74c4e82e94cdd5a4d29c3a
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/10/2017
---
# <a name="protect-access-to-sharepoint-online-with-microsoft-intune"></a>Microsoft Intune ile SharePoint Online’a erişimi koruma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

SharePoint Online’da bulunan dosyalara erişimi denetlemek için Microsoft Intune koşullu erişimini kullanın.
Koşullu erişim iki bileşenden oluşur:
- Cihazın uyumlu kabul edilmesi için uyması gereken cihaz uyumluluk ilkesi.
- Cihazın hizmete erişebilmek için uyması gereken koşulları sizin belirlediğiniz bir koşullu erişim ilkesi.
Koşullu erişimin nasıl çalıştığı hakkında daha fazla bilgi edinmek için [E-posta, O365 ve diğer hizmetlere erişimi koruma](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) konusunu okuyun.

Uyumluluk ve koşullu erişim ilkelerini kullanıcılara dağıtırsınız. Bir kullanıcının hizmetlere erişirken kullandığı her cihaz, ilkelerle uyumluluk açısından denetlenir.

Kullanıcı cihazında OneDrive gibi desteklenen bir uygulama kullanarak bir dosyaya bağlanmaya çalıştığında, aşağıdaki değerlendirme yapılır:

![Cihazın SharePoint erişimine izin verilmesini veya bu erişimin engellenmesini belirleyen karar noktalarının gösterildiği diyagram](../media/ConditionalAccess8-6.png)


SharePoint Online için koşullu erişim ilkesini yapılandırmadan **önce**:
- **SharePoint Online aboneliğiniz** olmalıdır ve kullanıcılar SharePoint Online lisansına sahip olmalıdır.
- **Enterprise Mobility + Security (EMS) aboneliğiniz** veya bir **Azure Active Directory (Azure AD) Premium aboneliğiniz** olmalıdır ve kullanıcılar EMS veya Azure AD lisansına sahip olmalıdır. Daha fazla ayrıntı için bkz. [Enterprise Mobility fiyatlandırma sayfası](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) veya [Azure Active Directory fiyatlandırma sayfası](https://azure.microsoft.com/pricing/details/active-directory/).


  Gerekli dosyalara bağlanmak için bir cihazın:
-   Intune’a **kaydedilmesi** veya etki alanına katılmış bir bilgisayar olması gerekir.

-   Azure Active Directory’ye **kaydedilmiş** (cihaz Intune hizmetine kaydedildiğinde bu otomatik olarak gerçekleşir) olması gerekir.


-   Dağıtılmış tüm Intune uyumluluk ilkeleriyle **uyumlu** olmalıdır.

Cihaz durumu, Azure Active Directory'de depolanır; bu durumda belirttiğiniz koşullara göre dosyalara erişim izni verilir veya erişim engellenir.

Bir koşul karşılanmazsa, kullanıcı oturum açtığında şu iletilerden birini görür:

-   Cihaz, Intune ile kaydedilmediyse veya Azure Active Directory'ye kayıtlı değilse Şirket Portalı uygulamasının nasıl yükleneceğine ve nasıl kayıt yapılacağına ilişkin yönergeleri içeren bir ileti görüntülenir.

-   Cihaz uyumlu değilse, kullanıcıyı sorun ve sorunun nasıl çözüleceğiyle ilgili bilgileri bulabileceği Intune Şirket Portalı web sitesine yönlendiren bir ileti görüntülenir.

**Koşullu erişim şirket dışı paylaşım için geçerli değildir**. Kiracınız veya site koleksiyonunuz için şirket dışı paylaşımı nasıl engelleyeceğinizi öğrenmek için bkz. [SharePoint Online ortamınız için şirket dışı paylaşımı yönetme](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85).

>[!NOTE]
>SharePoint Online için koşullu erişimi etkinleştirirseniz, [Remove-SPOTenantSyncClientRestriction](https://technet.microsoft.com/library/dn917451.aspx) konu başlığı altında açıklandığı gibi listedeki etki alanını devre dışı bırakmanızı öneririz.  

## <a name="support-for-mobile-devices"></a>Mobil cihaz desteği
Aşağıdakiler desteklenir:
- iOS 8.0 ve üzeri
- Android 4.0 ve üzeri ile Samsung KNOX Standard 4.0 veya üzeri
- Windows Phone 8.1 ve üzeri

**iOS** ve **Android** cihazlar, SharePoint Online’a bir tarayıcıdan eriştiğinde erişimi koruyabilirsiniz. Erişime yalnızca uyumlu cihazlarda, desteklenen tarayıcılardan izin verilir:
* Safari (iOS)
* Chrome (Android)
* Intune Managed Browser (iOS ve Android 5.0 ve üzeri)

**Desteklenmeyen tarayıcılar engellenir**.

## <a name="support-for-pcs"></a>Bilgisayarlar için destek
Aşağıdakiler desteklenir:
- Windows 8.1 ve üzeri (Bilgisayarlar Intune’a kaydedildiğinde)
- Windows 7.0, Windows 8.1 veya Windows 10 (Bilgisayarlar etki alanına katıldığında),
> [!NOTE]
>Windows 10 bilgisayarlar ile koşullu erişim kullanmak için bu bilgisayarları Windows 10 Yıldönümü Güncelleştirmesi ile güncelleştirmeniz gerekir.

  - Etki alanına katılmış bilgisayarları, Azure Active Directory’ye [otomatik olarak kaydedilecek](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-automatic-device-registration/) şekilde ayarlamanız gerekir. Azure AD Cihaz Kayıt hizmeti, Intune ve Office 365 müşterileri için otomatik olarak etkinleştirilir. ADFS Cihaz Kayıt hizmetini zaten dağıtan müşteriler, kayıtlı cihazlarını şirket içi Active Directory'de görmez.

  - İlke bir etki alanına katılmayı gerektirecek şekilde ayarlanmışsa ve bilgisayar etki alanına katılmamışsa, BT yöneticisine başvurulması gerektiğini belirten bir ileti görüntülenir.

  - İlke bir etki alanına katılmayı veya uyumluluğu gerektirecek şekilde ayarlandıysa ve bilgisayar iki gereksinimi de karşılamıyorsa, Şirket Portalı uygulamasını yükleme ve kaydetme yönergelerini içeren bir ileti görüntülenir.
  >[!NOTE]
  >Intune bilgisayar istemcisi çalıştıran bilgisayarlarda koşullu erişim desteklenmez.

[Office 365 modern kimlik doğrulamasının etkin olması](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) ve en son Office güncelleştirmelerine sahip olması gerekir.

Modern kimlik doğrulama, Office 2013 Windows istemcileri için Active Directory Kimlik Doğrulama Kitaplığı (ADAL) tabanlı oturum açma özelliği sunar ve **çok faktörlü kimlik doğrulaması** ile **sertifika tabanlı kimlik doğrulaması** gibi daha üst düzey güvenlik sağlar.


## <a name="configure-conditional-access-for-sharepoint-online"></a>SharePoint Online için koşullu erişimi yapılandırma

### <a name="step-1-configure-active-directory-security-groups"></a>Adım 1: Active Directory güvenlik gruplarını yapılandırma
Başlamadan önce koşullu erişim ilkesi için Azure Active Directory güvenlik gruplarını yapılandırın. **Office 365 yönetici merkezi**’nde veya **Intune hesap portalı**’nda bu grupları yapılandırabilirsiniz. Bu grupları, ilkede kullanıcıları hedeflemek veya muaf tutmak için kullanırsınız. Bir kullanıcı bir ilke tarafından hedeflendiğinde, kaynaklara erişmek için kullandıkları her bir cihaz uyumlu olmalıdır.

Bir SharePoint Online ilkesinde iki grup türü belirtebilirsiniz:

-   **Hedeflenen gruplar**: İlkenin uygulanacağı kullanıcı gruplarını içerir.

-   **Muaf tutulan gruplar**: İlkeden muaf tutulan kullanıcı gruplarını içerir.

Bir kullanıcı her iki gruptaysa ilkeden muaf tutulur.

### <a name="step-2-configure-and-deploy-a-compliance-policy"></a>Adım 2: Uyumluluk ilkesi yapılandırma ve dağıtma
Bu işlemi gerçekleştirmediyseniz, bir uyumluluk ilkesi oluşturun ve bu ilkeyi SharePoint Online ilkesinde hedeflenen kullanıcılara dağıtın.

> [!NOTE]
> Uyumluluk ilkeleri Intune gruplarına dağıtılırken, koşullu erişim ilkeleri Azure Active Directory güvenlik gruplarına dağıtılır.

Uyumluluk ilkesini yapılandırma ayrıntıları için bkz. [Uyumluluk ilkesi oluşturma](create-a-device-compliance-policy-in-microsoft-intune.md).

> [!IMPORTANT]
> Uyumluluk ilkesi dağıtmadıysanız cihazlar uyumlu olarak kabul edilir.

Hazır olduğunuzda **3. Adım**’a geçin.

### <a name="step-3-configure-the-sharepoint-online-policy"></a>Adım 3: SharePoint Online ilkesini yapılandırma
İlkeyi yalnızca yönetilen ve uyumlu cihazların SharePoint Online’a erişebileceği şekilde yapılandırın. Bu ilke Azure Active Directory’de depolanır.

#### <a name="bkmk_spopolicy"></a>

>[!NOTE]
> Azure AD yönetim konsolunda Intune cihazları için koşullu erişim ilkesi de oluşturabilirsiniz (ilke Azure AD’de **cihaz tabanlı koşullu erişim ilkesi** olarak adlandırılır). Ayrıca, çok faktörlü kimlik doğrulaması gibi diğer koşullu erişim ilkeleri de oluşturabilirsiniz. Salesforce ve Box gibi Azure AD tarafından desteklenen kurumsal üçüncü taraf uygulamaları için de koşullu erişim ilkeleri ayarlayabilirsiniz. Daha fazla ayrıntı için bkz. [Azure Active Directory bağlı uygulamalarda erişim denetimi için Azure Active Directory cihaz tabanlı koşullu erişim ilkesini ayarlama](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-policy-connected-applications/).


1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** > **Koşullu Erişim** > **SharePoint Online İlkesi**’ni seçin.
![SharePoint Online İlkesi sayfasının ekran görüntüsü](../media/mdm-ca-spo-policy-configuration.png)

2.  **SharePoint Online için koşullu erişim ilkesini etkinleştir**’i seçin.

3.  **Uygulama erişimi** altında aşağıdakilere koşullu erişim ilkesini uygulamayı seçebilirsiniz:

    -   **Tüm platformlar**

        Bu seçenek, **SharePoint Online**’a erişmek için kullanılan tüm cihazların Intune’a kaydedilmesini ve ilkelerle uyumlu olmasını gerektirir. **Modern kimlik doğrulaması** kullanan tüm istemci uygulamaları, koşullu erişim ilkesine bağlıdır. Platform şu anda Intune tarafından desteklenmiyorsa, **SharePoint Online**’a erişim engellenir.

        **Tüm platformlar** seçeneğinin belirlenmesi, Azure Active Directory’nin bu ilkeyi, istemci uygulaması tarafından bildirilen platformdan bağımsız olarak tüm kimlik doğrulama isteklerine uygulayacağı anlamına gelir. Aşağıdakiler dışında tüm platformların kaydolması ve uyumlu hale gelmesi gerekir:
        *   Windows cihazların, kaydolması ve uyumlu hale gelmesi, şirket içi Active Directory ile etki alanının birleşik olması veya her ikisi gerekir.
        * Mac gibi desteklenmeyen platformlar. Ancak, bu platformlardan gelen, modern kimlik doğrulaması kullanan uygulamalar yine de engellenir.

    -   **Belirli platformlar**

         Koşullu erişim ilkesi, belirttiğiniz platformlarda modern kimlik doğrulaması kullanan tüm istemci uygulamaları için geçerlidir.

     Windows bilgisayarları için bir bilgisayar etki alanına katılmış veya Intune ile kaydedilmiş ve uyumlu olmalıdır. Aşağıdaki gereksinimleri ayarlayabilirsiniz:

     -   **Cihazlar bir etki alanına katılmış veya uyumlu olmalıdır.** Bilgisayarların etki alanına katılmış veya Intune ile ayarlanan ilkelerle uyumlu olmasını gerekli hale getirmek için bu seçeneği belirtin. Bilgisayar bu gereksinimlerden birini karşılamıyorsa, kullanıcıdan cihazı Intune ile kaydetmesi istenir.

     -   **Cihazlar uyumlu olmalıdır.** Bilgisayarların Intune ile kaydedilmiş ve uyumlu olmasını zorunlu tutmak için bu seçeneği belirtin. Bilgisayar kayıtlı değilse, kaydetme yönergelerini içeren bir ileti görüntülenir.

4.   SharePoint Online ve OneDrive İş’e **Tarayıcı erişimi** altında, Exchange Online’a yalnızca desteklenen tarayıcılar üzerinden erişime izin vermeyi seçebilirsiniz: Safari (iOS) ve Chrome (Android). Diğer tarayıcılardan erişim engellenir. OneDrive için Uygulama erişimi için seçtiğiniz platform kısıtlamaları burada da geçerli olur.

  **Android** cihazlarda, kullanıcılar tarayıcı erişimini etkinleştirmelidir. Bunu yapmak için bir kullanıcı kaydolan cihazda **Tarayıcı Erişimini Etkinleştir** seçeneğini etkinleştirmelidir:
  1.    **Şirket Portalı** uygulamasını açın.
  2.    Üç nokta (...) veya donanım menüsü düğmesinden **Ayarlar** sayfasına gidin.
  3.    **Tarayıcı Erişimi Etkinleştir** düğmesine basın.
  4.    Chrome tarayıcıda, Office 365 oturumunu kapatın ve Chrome’u yeniden başlatın.

  **iOS** ve **Android** platformlarında, Azure Active Directory, cihazın hizmete erişmek amacıyla kullanıldığını belirlemek için cihaza bir Aktarım Katmanı Güvenliği (TLS) sertifikası yayımlar. Cihaz, sertifikayı aşağıdaki ekran görüntülerinde görüleceği gibi kullanıcıya sertifikayı seçmesi için bir istemle ekrana getirir. Kullanıcının tarayıcıyı kullanabilmesi için bu sertifikayı seçmesi gerekir.

  **Android**

  ![Bir iPad cihazda sertifika komut isteminin ekran görüntüsü](../media/mdm-browser-ca-ios-cert-prompt.png)

  **Outlook Web Access (OWA)**

  ![Android cihazda sertifika istemi ekran görüntüsü](../media/mdm-browser-ca-android-cert-prompt.png)
5.  **Hedeflenen Gruplar** altında, ilkenin geçerli olacağı Azure Active Directory güvenlik gruplarını seçmek için **Değiştir**’i seçin. Bunu tüm kullanıcılara veya yalnızca seçilmiş bir kullanıcı grubuna hedefleyebilirsiniz.

6.  **Muaf Tutulan Gruplar** altında, bu ilkeden muaf tutulan Active Directory güvenlik gruplarını seçmek için isteğe bağlı olarak **Değiştir**’i seçin.

7.  İşiniz bittiğinde **Kaydet**’i seçin.

Koşullu erişim ilkesini dağıtmanız gerekmez, hemen geçerli olur.

### <a name="step-4-monitor-the-compliance-and-conditional-access-policies"></a>Adım 4: Uyumluluk ve koşullu erişim ilkelerini izleme
**Gruplar** çalışma alanında, cihazlarınızın durumunu görüntüleyebilirsiniz.

Herhangi bir mobil cihaz grubu seçin. Ardından, **Cihazlar** sekmesinde aşağıdaki **Filtreler** arasından birini seçin:

-   **AAD ile kaydedilmeyen cihazlar**. Bu cihazlar SharePoint Online’dan engellenir.

-   **Uyumlu olmayan cihazlar**. Bu cihazlar SharePoint Online’dan engellenir.

-   **AAD ile kaydedilen ve uyumlu olan cihazlar**. Bu cihazlar SharePoint Online’a erişebilir.

### <a name="see-also"></a>Ayrıca bkz.
[Microsoft Intune ile e-posta ve O365 hizmetlerine erişimi koruma](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)
