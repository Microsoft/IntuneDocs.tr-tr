---
title: "Şirket İçi Exchange’de e-posta erişimini kısıtlama | Microsoft Docs"
description: "Şirket İçi Exchange’de şirket e-postasını korumak ve erişimini denetlemek için koşullu erişim kullanın."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a55071f5-101e-4829-908d-07d3414011fc
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 51e06bafef761eaf06d35343b459262524ad9168
ms.openlocfilehash: c090d4bbc539d4174deee139e51242bae94feeb3


---

# <a name="restrict-email-access-to-exchange-on-premises-and-legacy-exchange-online-dedicated-with-intune"></a>Intune’la Şirket İçi Exchange’e ve eski Ayrılmış Exchange Online ortamına e-posta erişimini kısıtlama

> [!NOTE]
> Adanmış Exchange Online ortamınız varsa ve bunun yapılandırmasının yeni mi yoksa eski mi olduğunu bulmanız gerekiyorsa lütfen hesap yöneticinize başvurun.


Şirket İçi Exchange’e veya eski Adanmış Exchange Online ortamına e-posta erişimini denetlemek için Microsoft Intune kullanarak Şirket İçi Exchange’e koşullu erişimi yapılandırabilirsiniz.
Koşullu erişimin nasıl çalıştığı hakkında daha fazla bilgi edinmek için, [E-posta ve O365 hizmetlerine erişimi kısıtlama]( restrict-access-to-email-and-o365-services-with-microsoft-intune.md) makalesini okuyun.

Koşullu erişimi yapılandırabilmeniz için **önce** aşağıdakileri doğrulayın:

-   Exchange sürümünüzün **Exchange 2010 veya üzeri** olması gerekir. Exchange Server İstemci Erişimi Sunucusu (CAS) dizileri desteklenir.

-   [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] ile Şirket İçi Exchange’i bağlayan **Şirket İçi Exchange bağlayıcısını** kullanmanız gerekir. Bu, cihazları [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] konsolu üzerinden yönetmenizi sağlar. Bağlayıcıyla ilgili ayrıntılar için bkz. [Intune Şirket İçi Exchange bağlayıcısı](intune-on-premises-exchange-connector.md).

    -   Intune konsolunda size sağlanan Şirket İçi Exchange bağlayıcısı, Intune kiracınıza özgüdür ve başka hiçbir kiracıyla kullanılamaz. Ayrıca, kiracınızın Exchange bağlayıcısının **tek bir makineye** yüklendiğinden de emin olmanız önerilir.

        Bağlayıcıyı Intune yönetim konsolundan yükleyebilirsiniz. Şirket İçi Exchange bağlayıcısını yapılandırma yönergeleri için bkz. [Şirket içi veya barındırılan Exchange için Şirket İçi Exchange bağlayıcısını yapılandırma](intune-on-premises-exchange-connector.md).

    -   Bağlayıcıyı, Exchange sunucusuyla iletişim kurabilen tüm makinelere yükleyebilirsiniz.

    -   Bağlayıcı, **Exchange CAS ortamını** destekler. İstiyorsanız bağlayıcıyı Exchange CAS sunucusuna doğrudan yükleyebilirsiniz. Ancak bu, sunucu üzerindeki yükü artıracağı için önerilmez. Bağlayıcıyı yapılandırırken Exchange CAS sunucularından biriyle iletişim kurabilecek şekilde yapılandırmanız gerekir.

-   **Exchange ActiveSync**, sertifika tabanlı kimlik doğrulaması veya kullanıcı kimlik bilgileri girişiyle yapılandırılmalıdır.

Koşullu biçimlendirme ilkeleri yapılandırdığınızda ve bunlarla bir kullanıcı hedeflediğinizde, kullanıcının e-postasına bağlanabilmesi için önce **cihazın** şu özellikleri taşıması gerekir:

-  Etki alanına katılmış bir bilgisayar veya [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] ile **kaydedilmiş** olması gerekir.

-  **Azure Active Directory’de kayıtlı olmalıdır**. Buna ek olarak, istemci Exchange ActiveSync kimliği Azure Active Directory’de kayıtlı olmalıdır.

  Azure Active Directory Cihaz Kayıt hizmeti, Intune ve Office 365 müşterileri için otomatik olarak etkinleştirilir. ADFS Cihaz Kayıt hizmetini zaten dağıtan müşteriler, kayıtlı cihazlarını şirket içi Active Directory'de görmez. **Bu, Windows bilgisayarları ve Windows Phone cihazları için geçerli değildir**.

-   Söz konusu cihaza dağıtılan tüm [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] uyumluluk ilkeleriyle **uyumlu** olmalıdır.

Aşağıdaki çizelgede, Şirket İçi Exchange’e yönelik koşullu erişim ilkeleri tarafından, cihazlara izin verme veya cihazları engelleme yönünde değerlendirme yapmak amacıyla kullanılan akış gösterilir.

![Cihazın Şirket İçi Exchange’e erişimine izin verileceğini veya erişimin engelleneceğini belirleyen karar noktalarının gösterildiği diyagram](../media/ConditionalAccess8-2.png)

Bir koşullu erişim ilkesi karşılanmazsa kullanıcı oturum açtığında şu iletilerden birini görür:

- Cihaz [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] ile kaydedilmediyse veya Azure Active Directory’de kayıtlı değilse Şirket Portalı uygulamasını yükleme, cihazı kaydetme ve e-postayı etkinleştirme yönergelerinin bulunduğu bir ileti görüntülenir. Bu işlem cihazın Exchange ActiveSync kimliğini de Azure Active Directory’deki cihaz kaydıyla ilişkilendirir.

-   Cihaz uyumlu değilse kullanıcıyı sorunla ve sorunun nasıl çözüleceğiyle ilgili bilgileri bulabileceği [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Şirket Portalı web sitesine veya Şirket Portalı uygulamasına yönlendiren bir ileti görüntülenir.

## <a name="support-for-mobile-devices"></a>Mobil cihaz desteği
Aşağıdakiler desteklenir:
-   Windows Phone 8.1 ve üzeri.

-   iOS’ta yerel e-posta uygulaması.

-   Android 4 veya sonraki sürümlerde Gmail gibi Exchange ActiveSync posta istemcileri.
- Exchange ActiveSync posta istemcileri **Android for Work cihazlar**: Android for Work cihazlarda yalnızca **iş profilindeki** **Gmail** ve **Nine Work** uygulamaları desteklenir. Android for Work cihazlarda koşullu erişimin çalışması için Gmail veya Nine Work uygulamasına yönelik bir e-posta profili dağıtmalısınız ve bu uygulamaları ayrıca zorunlu bir yükleme olarak dağıtmanız gerekir. 

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

> [!NOTE]
> Android ve iOS için Microsoft Outlook uygulaması desteklenmez.

## <a name="support-for-pcs"></a>Bilgisayarlar için destek
Aşağıdakiler desteklenir:
-   Windows 8.1 ve üstündeki **Posta** uygulaması (Bilgisayar [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] ile kaydedildiğinde).

##  <a name="configure-a-conditional-access-policy"></a>Koşullu erişim ilkesini yapılandırma

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** > **Koşullu Erişim** > **Şirket İçi Exchange İlkesi**’ni seçin.
![IntuneSA5aSelectExchOnPremPolicy](../media/IntuneSA5aSelectExchOnPremPolicy.png)

2.  İlkeyi size gereken ayarlarla yapılandırın: ![Şirket İçi Exchange ilkesi sayfasının ekran görüntüsü](../media/IntuneSA5bExchangeOnPremPolicy.png)

  - **Cihaz uyumsuzsa veya Microsoft Intune'a kayıtlı değilse e-posta uygulamalarının Şirket İçi Exchange'e erişimini engelle:** Bu seçeneği belirttiğinizde, [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] tarafından yönetilmeyen veya bir uyumluluk ilkesiyle uyumlu olmayan cihazların Exchange hizmetlerine erişimi engellenir.

  - **Varsayılan kuralı geçersiz kılma - Intune'a kayıtlı ve uyumlu cihazların Exchange'e erişmesine her zaman izin ver:** Bu seçeneği işaretlediğinizde, Intune’a kaydedilen ve ilkelerle uyumlu olan cihazların Exchange’e erişmesine izin verilir.
  Bu kural **Varsayılan Kural**’ı geçersiz kılar; diğer bir deyişle, **Varsayılan Kural**’ı erişimi karantinaya alacak veya engelleyecek şekilde ayarlasanız bile, kayıtlı ve uyumlu cihazların yine de Exchange’e erişebileceği anlamına gelir.

  - **Hedeflenen Gruplar:** Exchange’e erişebilmesi için cihazını [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] ile kaydetmesi gereken [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] kullanıcı gruplarını seçin.

  - **Muaf Tutulan Gruplar:** Koşullu erişim ilkesinden muaf tutulan [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] kullanıcı gruplarını seçin. Bu listedeki kullanıcılar, aynı zamanda **Hedeflenen Gruplar** listesinde olsalar bile muaf tutulurlar.

  - **Platform Özel Durumları:** Belirtilen mobil cihaz aileleri ve modellerinde erişim düzeylerini tanımlayan bir kural yapılandırmak için **Kural Ekle**’yi seçin. Bu cihazlar herhangi bir türde olabileceğinden, [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] tarafından desteklenmeyen cihaz türlerini de yapılandırabilirsiniz.

  - **Varsayılan Kural:** Diğer kurallardan herhangi birinin kapsamında yer almayan bir cihaz söz konusu olduğunda cihazın Exchange’e erişmesine izin vermeyi, cihazı engellemeyi veya karantinaya almayı seçebilirsiniz. Kuralı, kayıtlı ve uyumlu cihazlarda erişime izin verecek şekilde ayarladığınızda, iOS, Windows ve Samsung KNOX cihazları için otomatik olarak e-posta erişimi verilir. Kullanıcının e-postasını almak için herhangi bir işlem yapması gerekmez.

        Samsung KNOX çalıştırmayan Android cihazlarda, e-postaya erişebilmeleri için kullanıcılar, kaydı ve uyumluluğu doğrulama işleminde yol gösteren bir karantina e-postası alır. Cihazlara erişimi engellemeye veya cihazları karantinaya almaya yönelik kural ayarlarsanız Intune’a kaydedilmiş olup olmadıklarına bakılmaksızın tüm cihazların Exchange’e erişimi engellenir. Kayıtlı ve uyumlu cihazların bu kuraldan etkilenmesini önlemek için **Varsayılan Kuralı Geçersiz Kıl** kutusunu işaretleyin.
>[!TIP]
>Amacınız e-postaya erişim vermeden önce tüm cihazları engellemekse Erişimi engelle kuralını veya Karantina kuralını seçin. Varsayılan kural tüm cihaz türleri için geçerli olacaktır, böylece platform özel durumları olarak yapılandırdığınız ve [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] tarafından desteklenmeyen cihaz türleri de etkilenir.

  - **Kullanıcı Bildirimi:** Exchange’den gönderilen bildirim e-postasına ek olarak Intune, cihazın engelini kaldırma adımlarını içeren bir e-posta gönderir. Gereksinimlerinize göre özelleştirmek için, varsayılan iletiyi düzenleyebilirsiniz. Çözümleme yönergelerini içeren Intune bildirim e-posta iletisini (bu e-posta kullanıcının Exchange posta kutusuna teslim edilir) almadan önce cihazının engellenmesi durumunda kullanıcı, Exchange’e erişmek ve iletiyi görüntülemek için engellenmemiş bir cihaz ya da başka yöntemler kullanabilir.

        This is especially true when the **Default Rule** is set to block or quarantine. In this case, the user has to go to their app store, download the Microsoft Company Portal app, and enroll their device. This is applicable to iOS, Windows, and Samsung KNOX devices. For devices that don't run Samsung KNOX, you need to send the quarantine email to an alternate email account. The user has to copy the email to their blocked device to complete the enrollment and compliance process.
  > [!NOTE]
  > Exchange’in bildirim e-postası gönderebilmesi için bildirim e-postasını göndermek için kullanılan hesabı belirtmeniz gerekir.
  >
  > Ayrıntılar için bkz. [Şirket içi veya barındırılan Exchange için Şirket İçi Exchange bağlayıcısını yapılandırma](intune-on-premises-exchange-connector.md).

3.  İşiniz bittiğinde **Kaydet**’i seçin.

-   Koşullu erişim ilkesini dağıtmanız gerekmez, hemen geçerli olur.

-   Kullanıcı, bir Exchange ActiveSync profili ayarladıktan sonra cihazın engellenmesi bir ila üç saat arası sürebilir ([!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] tarafından yönetilmiyorsa).

-   Engellenen kullanıcı daha sonra cihazı [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] ile kaydederse ve uyumsuzluğu çözerse iki dakika içinde e-posta erişiminin engeli kaldırılır.

-   Kullanıcı [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] kaydını silerse cihazın engellenmesi bir ila üç saat arası sürebilir.

**Cihaz erişimini kısıtlamak üzere bir koşullu erişim ilkesini nasıl yapılandırabileceğinizi gösteren bazı örnek senaryoları görmek için bkz. [E-posta erişimini kısıtlama örnek senaryoları](restrict-email-access-example-scenarios.md).**

## <a name="next-steps"></a>Sonraki adımlar
-   [SharePoint Online’a erişimi kısıtlama](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

-   [Skype Kurumsal Çevrimiçi Sürüm’e erişimi kısıtlama](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


