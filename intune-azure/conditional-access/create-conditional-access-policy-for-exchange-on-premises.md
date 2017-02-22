---
title: "Exchange şirket içi koşullu erişim ilkesi | Intune Azure önizlemesi | Microsoft Docs"
description: "Intune Azure önizlemesi: Intune’da Exchange şirket içi koşullu erişimini ve eski Exchange Online Ayrılmış hizmetini nasıl yapılandırabilirsiniz?"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 127dafcb-3f30-4745-a561-f62c9f095907
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 581f9be824ea883fd0208abc3b2ecc09174cb911
ms.openlocfilehash: a80d6a19948291cc80e42ad5a9a2f016effb2f37


---

# <a name="how-to-create-a-conditional-access-policy-for-exchange-on-premises-and-legacy-exchange-online-dedicated-in-microsoft-intune-azure-preview"></a>Microsoft Intune Azure önizlemesinde Exchange şirket içi ve eski Exchange Online Ayrılmış hizmeti için koşullu erişim ilkesini oluşturma


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Bu konu başlığı altında, cihaz uyumluluğu temelinde Exchange şirket içi için koşullu erişimi biçimlendirme işleminde size yol gösterilir.

Ayrılmış Exchange Online ortamınız varsa ve bunun yapılandırmasının yeni mi yoksa eski mi olduğunu bulmanız gerekiyorsa, lütfen hesap yöneticinize başvurun. Şirket İçi Exchange’e veya eski Ayrılmış Exchange Online ortamına e-posta erişimini denetlemek için, Intune’da Şirket İçi Exchange’e koşullu erişim yapılandırın.

## <a name="prerequisites"></a>Önkoşullar

Koşullu erişimi yapılandırabilmeniz için **önce** aşağıdakileri doğrulayın:

- Exchange sürümünüzün **Exchange 2010 veya üzeri** olması gerekir. Exchange Server İstemci Erişimi Sunucusu (CAS) dizisi desteklenir.
- Intune hizmetini şirket içi Microsoft Exchange’e bağlayan **şirket içi Exchange Active Sync bağlayıcısını** kullanmanız gerekir. Bağlayıcıyla ilgili ayrıntılar için bkz. <link>

  - Intune konsolunda size sağlanan Şirket İçi Exchange bağlayıcısı, Intune kiracınıza özgüdür ve başka hiçbir kiracıyla kullanılamaz. Ayrıca, kiracınızın Exchange bağlayıcısının **tek bir makineye** yüklendiğinden de emin olmalısınız.

Bu bağlayıcı Intune yönetim konsolundan indirilmelidir. Şirket içi Exchange bağlayıcısını yapılandırma işleminin yönergeleri için bkz. <link to new topic>

Bu bağlayıcı, makine Exchange sunucusuyla iletişim kurabildiği sürece herhangi bir makineye yüklenebilir.

- Bağlayıcı **Exchange CAS ortamını** destekler. İsterseniz, teknik olarak bağlayıcıyı doğrudan Exchange CAS sunucusuna yükleyebilirsiniz, ancak sunucu üzerindeki yükü artıracağından bunun yapılması önerilmez. Bağlayıcıyı yapılandırırken Exchange CAS sunucularından biriyle iletişim kurabilecek şekilde yapılandırmanız gerekir.
- **Exchange ActiveSync**, sertifika tabanlı kimlik doğrulaması veya kullanıcı kimlik bilgileri girişiyle yapılandırılmalıdır.

Koşullu biçimlendirme ilkeleri yapılandırıldığında ve hedef kullanıcı belirlendiğinde, kullanıcının e-postasına bağlanabilmesi için önce **cihazın** şu özellikleri taşıması gerekir:

- Intune’a **kayıtlı** veya etki alanına katılmış bir bilgisayar olmalıdır.
- **Azure Active Directory’de kayıtlı olmalıdır**. Buna ek olarak, istemci Exchange ActiveSync kimliği Azure Active Directory’de kayıtlı olmalıdır.

AAD DRS, Intune ve Office 365 müşterileri için otomatik olarak etkinleştirilir. ADFS Cihaz Kayıt Hizmeti'ni zaten dağıtan müşteriler, kayıtlı cihazlarını şirket içi Active Directory'lerinde görmez. **Bu, Windows bilgisayarları ve Windows Phone cihazları için geçerli değildir**.

- Söz konusu cihaza dağıtılan tüm Intune uyumluluk ilkeleriyle **uyumlu** olmalıdır.

Cihaz koşullu erişim ayarlarına uygun değilse, kullanıcıya oturum açtığında aşağıdaki iletilerden biri gösterilir:

- Cihaz Intune’a kaydolmadıysa veya Azure Active Directory’de kayıtlı değilse, Şirket Portalı uygulamasını yükleme, cihazı kaydetme ve e-postayı etkinleştirme yönergelerinin bulunduğu bir ileti görüntülenir. Bu işlem cihazın Exchange ActiveSync kimliğini de Azure Active Directory’deki cihaz kaydıyla ilişkilendirir.
- Cihaz uyumlu değilse, kullanıcıyı sorun hakkında bilgi bulabileceği ve sorunu düzeltebileceği Intune Şirket Portalı Web sitesine veya Şirket Portalı uygulamasına yönlendiren bir ileti görüntülenir.

## <a name="support-for-mobile-devices"></a>Mobil cihaz desteği

- Windows Phone 8.1 ve üzeri
- iOS’ta yerel e-posta uygulaması.
- Android 4 veya sonraki sürümlerdeki Gmail gibi EAS posta istemcileri.
- EAS posta istemcileri **Android for Work cihazlar:** Android for Work cihazlarda yalnızca **iş profilindeki** **Gmail** ve **Nine Work** uygulamaları desteklenir. Android for Work cihazlarda koşullu erişimin çalışması için Gmail veya Nine Work uygulamasına yönelik bir e-posta profili dağıtmalısınız. Ayrıca bu uygulamaları da zorunlu yükleme olarak dağıtmanız gerekir.

>[!NOTE]
>Android ve iOS için Microsoft Outlook uygulaması desteklenmez.

> Android for Work, Intune kiracılarında önümüzdeki birkaç ay için kullanıma sunulacaktır.

Android for Work'ün destek durumu hakkında ek bilgi için [Microsoft Intune'daki Yenilikler](https://docs.microsoft.com/en-us/intune/whats-new/whats-new-archive#october-2016) makalesinin Ekim 2016 sürümündeki Android for Work duyurusunu okuyun.

## <a name="support-for-pcs"></a>Bilgisayarlar için destek

Windows 8.1 ve üstündeki **Posta** uygulaması (Intune ile kaydedildiğinde)


## <a name="configure-exchange-on-premises-access"></a>Şirket içi Exchange erişimini yapılandırma

1. Şirket içi dikey penceresini açmak için Azure Portal’da **Koşullu erişim** iş yükünü seçin.
2. **Şirket içi** dikey penceresinde koşullu erişim ilkesinin durumu ve bundan etkilenen cihazlar gösterilir.
3. **Yönet**’in altında **Şirket içi Exchange erişimi**’ni seçin.
4. **Şirket içi Exchange erişimi** dikey penceresinde **Evet**’i seçerek şirket içi Exchange erişim denetimini etkinleştirin.

  >[!NOTE]
  >Exchange Active Sync şirket içi bağlayıcısını yapılandırmadıysanız, bu seçenek devre dışı bırakılır.  Şirket içi Exchange için koşullu erişimi etkinleştirebilmek için önce bu bağlayıcıyı yüklemeli ve yapılandırmalısınız. Diğer ayrıntılar için bkz. [Intune Şirket İçi Exchange Connector’ı yükleme](install-intune-on-premises-exchange-connector.md).

5. **Atama**’nın altında **Eklenen Gruplar**’ı seçin.  Koşullu erişimin uygulanacağı güvenlik kullanıcı grubunu seçin.  Bunun için kullanıcıların cihazlarını Intune’da kaydetmeleri ve uyumluluk profilleriyle uyumlu olmaları gerekir.
6. Belirli kullanıcı gruplarını dışta tutmak istiyorsanız, **Dışlanan Gruplar**’ı seçip ardından da cihaz kaydı ve uyumluluk gereksiniminden muaf tutmak istediğiniz kullanıcı grubunu seçenek bunu yapabilirsiniz.
7. Varsayılan e-posta iletisini değiştirmek için, **Ayarlar**’ın altında **Kullanıcı bildirimleri**’ni seçin. Bu ileti, cihazı uyumlu olmayan ve şirket içi Exchange’e erişmek isteyen kullanıcılara gönderilir. İleti şablonunda Biçimlendirme dili kullanılır.  Ayrıca yazarken iletinin nasıl görüneceğini gösteren bir önizleme de görürsünüz. Biçimlendirme dili hakkında daha fazla bilgi edinmek için bu Wikipedia [makalesine](https://en.wikipedia.org/wiki/Markup_language) bakın.
8. **Gelişmiş Exchange Active Sync erişim ayarları** dikey penceresinde, Intune tarafından yönetilmeyen cihazlardan erişim için ve sonraki iki adımda açıklandığı gibi platform düzeyi kuralları için genel varsayılan kuralı ayarlayın.
9. Koşullu erişimden veya diğer kurallardan etkilenmeyen bir cihaz söz konusu olduğunda, cihazın Exchange’e erişmesine izin vermeyi, veya engellemeyi seçebilirsiniz.
  - Bunu erişime izin verecek şekilde ayarlarsanız, tüm cihazlar şirket içi Exchange’e hemen erişebilir.  **Eklenen Gruplar** içindeki kullanıcılara ait cihazlar, sonunda uyumluluk ilkelerine uymadığı veya Intune’a kaydedilmemiş olduğu belirlenirse engellenir.
  - Bunu erişimi engelleyecek şekilde ayarlarsanız, başlangıçta tüm cihazların şirket içi Exchange’e erişimi hemen engellenir.  **Eklenen Gruplar** içindeki kullanıcılara ait cihazlar, Intune’a kaydolduğunda ve uyumlu olarak değerlendirildiğinde erişim kazanır. Samsung KNOX Standard çalıştırmayan Android cihazlar bu ayarı desteklemediğinden, her zaman engellenir.
10. **Cihaz platformu özel durumları**’nın altında **Ekle**’yi seçerek platformları belirtin. **Yönetilmeyen cihaz erişimi** ayarı **engellendi** olarak belirlenirse, engellemek için bir platform özel durumu olsa bile, kayıtlı ve uyumlu cihazlara izin verilir. Ayarları kaydetmek için **Tamam**’ı seçin.
11. **Şirket içi** dikey penceresinde **Kaydet**’e tıklayarak koşullu erişim ilkesini kaydedin.



<!--HONumber=Feb17_HO1-->


