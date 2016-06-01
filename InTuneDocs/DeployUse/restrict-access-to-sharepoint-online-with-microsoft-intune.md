---
# required metadata

title: SharePoint Online’a erişimi kısıtlama | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: b088e5a0-fd4a-4fe7-aa49-cb9c8cfb1585

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Intune’la SharePoint Online’a erişimi kısıtlama
SharePoint Online’da bulunan dosyalara erişimi denetlemek için [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] koşullu erişimini kullanın.
Koşullu erişim iki bileşenden oluşur:
- Cihazın uyumlu kabul edilmesi için uyması gereken cihaz uyumluluk ilkesi.
- Cihazın hizmete erişebilmek için uyması gereken koşulları sizin belirlediğiniz koşullu erişim ilkesi.
Koşullu erişimin nasıl çalıştığı hakkında daha fazla bilgi edinmek için, [E-posta ve O365 hizmetlerine erişimi kısıtlama](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) konusunu okuyun.

Kullanıcı cihazında OneDrive gibi desteklenen bir uygulama kullanarak bir dosyaya bağlanmaya çalıştığında, aşağıdaki değerlendirme yapılır:

![Cihazın SharePoint’e erişimine izin verilmesini veya bu erişimin engellenmesini belirleyen karar noktalarının gösterildiği diyagram ](../media/ConditionalAccess8-6.png)

>[!IMPORTANT]
>Modern kimlik doğrulamasının kullanıldığı uygulamalar bulunan bilgisayarlar ve Windows 10 Mobile cihazları için koşullu erişim özelliği, şu anda tüm Intune müşterilerine sağlanmaz. Bu özellikleri zaten kullanıyorsanız, herhangi bir işlem yapmanız gerekmez. Kullanmaya devam edebilirsiniz.

>Bilgisayarlarda veya Windows 10 Mobile cihazlarda modern kimlik doğrulamasının kullanıldığı uygulamalar için koşullu erişim ilkeleri oluşturmadıysanız ve bunu yapmak istiyorsanız, bir istek göndermeniz gerekir.  [Connect sitesinde](http://go.microsoft.com/fwlink/?LinkId=761472), hem bilinen sorunlar hem de bu özelliği nasıl erişebileceğiniz hakkında daha fazla bilgi bulabilirsiniz.

SharePoint Online için koşullu erişim ilkesini yapılandırmadan **önce**:
- **SharePoint Online aboneliğiniz** olmalıdır ve kullanıcılar SharePoint Online lisansına sahip olmalıdır.
- **Enterprise Mobility Suite** veya **Azure Active Directory Premium** aboneliğiniz olmalıdır.

  Gerekli dosyalara bağlanmak için, cihazın:
-   [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]’a **kaydedilmesi** veya etki alanına katılmış bir bilgisayar olması gerekir.

-   Cihazı Azure Active Directory’ye **kaydedin** (cihaz Intune’a kaydedildiğinde bu otomatik olarak gerçekleşir).


-   Dağıtılan tüm [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] uyumluluk ilkelerine uyması gerekir.

Cihaz durumu, Azure Active Directory'de depolanır; bu durumda belirttiğiniz koşullara göre dosyalara erişim izni verilir veya erişim engellenir.

Bir koşul karşılanmazsa, oturum açtığında kullanıcıya şu iletilerden biri sunulur:

-   Cihaz [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]’a kaydedilmediyse veya Azure Active Directory'ye kayıtlı değilse, Şirket Portalı uygulamasının nasıl yükleneceğine ve nasıl kayıt yapılacağına ilişkin yönergeleri içeren bir ileti görüntülenir.

-   Cihaz uyumlu değilse, kullanıcıyı sorunla ve sorunun nasıl çözüleceğiyle ilgili bilgileri bulabileceği [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Şirket Portalı web sitesine yönlendiren bir ileti görüntülenir.

## Mobil cihaz desteği
- iOS 7.1 ve üzeri
- Android 4.0 ve üzeri ile Samsung KNOX Standard 4.0 veya üzeri
- Windows Phone 8.1 ve üzeri

## Bilgisayarlar için destek
- Windows 8.1 ve üzeri (Intune’a kaydedildiğinde)
- Windows 7.0 veya Windows 8.1 (etki alanına katıldığında)

  - Etki alanına katılmış bilgisayarlar, Azure Active Directory’ye [otomatik olarak kaydedilecek](https://azure.microsoft.com/en-us/documentation/articles/active-directory-conditional-access-automatic-device-registration/) şekilde ayarlanmalıdır.
AAD DRS, Intune ve Office 365 müşterileri için otomatik olarak etkinleştirilir. ADFS Cihaz Kayıt Hizmeti'ni zaten dağıtan müşteriler, kayıtlı cihazlarını şirket içi Active Directory'lerinde görmez.

  - İlke etki alanına katılmayı gerektirecek şekilde ayarlanmışsa ve bilgisayar etki alanına katılmamışsa, BT yöneticisine başvurulması gerektiğini belirten bir ileti görüntülenir.

  - İlke etki alanına katılmayı veya uyumluluğu gerektirecek şekilde ayarlandıysa ve bilgisayar iki gereksinimi de karşılamıyorsa, Şirket Portalı uygulamasını yükleme ve kaydetme yönergelerini içeren bir ileti görüntülenir.
-    [Office 365 modern kimlik doğrulamasının etkin olması](https://support.office.com/en-US/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) ve en son Office güncelleştirmelerine sahip olması gerekir.

    Modern kimlik doğrulaması, Office 2013 Windows istemcileri için Active Directory Authentication Library (ADAL) tabanlı oturum açma özelliği sunar ve **çok faktörlü kimlik doğrulaması** ile **sertifika tabanlı kimlik doğrulaması** gibi daha üst düzey güvenlik sağlar.


## SharePoint Online için koşullu erişimi yapılandırma

### Adım 1: Active Directory güvenlik gruplarını yapılandırma
Başlamadan önce koşullu erişim ilkesi için Azure Active Directory güvenlik gruplarını yapılandırın.  **Office 365 yönetici merkezi**‘nde veya **Intune hesap portalı**‘nda bu grupları yapılandırabilirsiniz. Bu gruplar, ilkede kullanıcıları hedeflemek veya muaf tutmak için kullanılır. Bir kullanıcı bir ilke tarafından hedeflendiğinde, kaynaklara erişmek için kullandıkları her bir cihaz uyumlu olmalıdır.

Bir SharePoint Online ilkesinde iki grup türü belirtebilirsiniz:

-   **Hedeflenen gruplar** - İlkenin uygulanacağı kullanıcı gruplarını içerir.

-   **Muaf tutulan gruplar** - İlkeden muaf tutulan kullanıcı gruplarını içerir.

Bir kullanıcı her iki gruptaysa ilkeden muaf tutulur.

### Adım 2: Uyumluluk ilkesi yapılandırma ve dağıtma
Bunu zaten yapmadıysanız, bir uyumluluk ilkesi oluşturun ve bu ilkeyi SharePoint Online ilkesinde hedeflenecek olan kullanıcılara dağıtın.

> Uyumluluk ilkeleri [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] gruplarına dağıtılırken, koşullu erişim ilkeleri Azure Active Directory güvenlik gruplarına dağıtılır.

Uyumluluk ilkesini yapılandırma ayrıntıları için bkz. [Uyumluluk ilkesi oluşturma](create-a-device-compliance-policy-in-microsoft-intune.md).

> Uyumluluk İlkesi dağıtmadıysanız, cihazlar uyumlu olarak kabul edilir.

Hazır olduğunuzda **3. Adım**’a ilerleyin.

### Adım 3: SharePoint Online ilkesini yapılandırma
İlkeyi yalnızca yönetilen ve uyumlu cihazların SharePoint Online’a erişebileceği şekilde yapılandırın. Bu ilke Azure Active Directory’de depolanır.

#### <a name="bkmk_spopolicy"></a>

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** > **Koşullu Erişim** > **SharePoint Online İlkesi**’ne tıklayın.
![SharePoint Online İlkesi sayfasının ekran görüntüsü](../media/IntuneSASharePointOnlineCAPolicy.png)

2.  **SharePoint Online için koşullu erişim ilkesini etkinleştir**’i seçin.

3.  **Uygulama erişimi** altında aşağıdakilere koşullu erişim ilkesini uygulamayı seçebilirsiniz:

    -   **Tüm platformlar**

        Bu seçenek, **SharePoint Online**’a erişmek için kullanılan tüm cihazların Intune’a kaydedilmesini ve ilkelerle uyumlu olmasını gerektirir.  **Modern kimlik doğrulaması** kullanan tüm istemci uygulamaları, koşullu erişim ilkesine bağlıdır. Platform şu anda Intune tarafından desteklenmiyorsa, **SharePoint Online**’a erişim engellenir.
        >[!TIP]
        >Bilgisayarlar için koşullu erişimi zaten kullanıyorsanız, bu seçeneği görmeyebilirsiniz.  Bunun yerine **Belirli platformlar**’ı kullanın. Bilgisayarlar için koşullu erişim şu anda tüm Intune müşterilerine sağlanmamaktadır.   [Microsoft Connect sitesinde](http://go.microsoft.com/fwlink/?LinkId=761472), hem bilinen sorunlar hem de bu özelliği nasıl erişebileceğiniz hakkında daha fazla bilgi bulabilirsiniz.

    -   **Belirli platformlar**

         Koşullu erişim ilkesi, belirttiğiniz platformlarda modern kimlik doğrulaması kullanan tüm istemci uygulamaları için geçerlidir.

     Windows bilgisayarları için, bilgisayar etki alanına katılmış veya [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]’a kaydedilmiş ve uyumlu olmalıdır. Aşağıdaki gereksinimleri ayarlayabilirsiniz:

     -   **Cihazlar bir etki alanına katılmış veya uyumlu olmalıdır.** Bilgisayarların etki alanına katılmış veya [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]’da ayarlanan ilkelerle uyumlu olmasını istiyorsanız bu seçeneği belirtin. Bilgisayar bu iki gereksinimi de karşılamıyorsa, kullanıcıdan cihazı Intune’a kaydetmesi istenir.

     -   **Cihazlar bir etki alanına katılmış olmalıdır.** Bilgisayarların Exchange Online'a erişmek için etki alanına katılmış olmasını zorunlu tutmak için bu seçeneği belirtin. Bilgisayar etki alanına katılmadıysa, e-posta erişimi engellenir ve kullanıcıdan BT yöneticisine başvurması istenir.

     -   **Cihazlar uyumlu olmalıdır.** Bilgisayarların [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] ’a kaydedilmiş ve uyumlu olmalısını zorunlu tutmak için bu seçeneği belirtin. Bilgisayar kayıtlı değilse, kaydetme yönergelerini içeren bir ileti görüntülenir.

4.   **Hedeflenen Gruplar**altında, ilkenin geçerli olacağı Azure Active Directory güvenlik gruplarını seçmek için **Değiştir** ’e tıklayın. Bunu tüm kullanıcılara veya yalnızca seçilmiş bir kullanıcı grubuna hedefleyebilirsiniz.

5.   **Muaf Tutulan Gruplar**altında, bu ilkeden muaf tutulan Active Directory güvenlik gruplarını seçmek için isteğe bağlı olarak **Değiştir** ’e tıklayın.

6.  İşiniz bittiğinde **Kaydet**‘e tıklayın.

Koşullu erişim ilkesini dağıtmanız gerekmez, hemen geçerli olur.

### Adım 4: Uyumluluk ve koşullu erişim ilkelerini izleme
**Gruplar** çalışma alanında, cihazlarınızın durumunu görüntüleyebilirsiniz.

Herhangi bir mobil cihaz grubunu seçin ve ardından **Cihazlar** sekmesinde aşağıdaki **Filtreler**arasından birini seçin:

-   **AAD ile kayıtlı olmayan cihazlar** : Bu cihazların SharePoint Online’a erişimi engellenir.

-   **Uyumlu olmayan cihazlar** : Bu cihazların SharePoint Online’a erişimi engellenir.

-   **AAD ile kayıtlı ve uyumlu cihazlar** : Bu cihazlar SharePoint Online’a erişebilir.

### Ayrıca bkz.
[Microsoft Intune ile e-posta ve O365 hizmetlerine erişimi kısıtlama](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)


<!--HONumber=May16_HO2-->


