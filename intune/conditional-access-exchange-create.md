---
title: Exchange koşullu erişim ilkesi oluşturma
titlesuffix: Microsoft Intune
description: Intune'da Exchange şirket içi ve eski Exchange Online Dedicated için koşullu erişimi yapılandırın.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 127dafcb-3f30-4745-a561-f62c9f095907
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fbe55be15df9755c109ec7e8e8e23db3c27931b0
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905538"
---
# <a name="create-a-conditional-access-policy-for-exchange-on-premises-and-legacy-exchange-online-dedicated"></a>Exchange şirket içi ve eski Exchange Online Dedicated için koşullu erişim ilkesi oluşturun.

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makalede, cihaz uyumluluğuna bağlı olarak şirket içi Exchange için koşullu erişimi nasıl yapılandıracağınız gösterilir.

Ayrılmış Exchange Online ortamınız varsa ve bunun yapılandırmasının yeni mi yoksa eski mi olduğunu bulmanız gerekiyorsa, lütfen hesap yöneticinize başvurun. Şirket İçi Exchange’e veya eski Ayrılmış Exchange Online ortamına e-posta erişimini denetlemek için, Intune’da Şirket İçi Exchange’e koşullu erişim yapılandırın.

## <a name="before-you-begin"></a>Başlamadan önce

Koşullu erişim yapılandırabilmek için önce aşağıdakileri doğrulayın:

- Exchange sürümünüzün **Exchange 2010 SP1 veya üzeri** olması gerekir. Exchange Server İstemci Erişimi Sunucusu (CAS) dizisi desteklenir.

- Intune hizmetini şirket içi Exchange’e bağlayan [Exchange Active Sync şirket içi Exchange bağlayıcısını](exchange-connector-install.md) kullanmanız gerekir.

    >[!IMPORTANT]
    >Şirket içi Exchange bağlayıcısı, Intune kiracınıza özgüdür ve başka bir kiracıyla kullanılamaz. Intune artık abonelik başına birden çok şirket içi Exchange bağlayıcısını destekler. Birden çok şirket içi Exchange kuruluşunuz varsa, her Exchange kuruluşu için ayrı bağlayıcılar ayarlayabilirsiniz.

- Şirket içi Exchange kuruluşu için bu bağlayıcı, makine Exchange sunucusuyla iletişim kurabildiği sürece herhangi bir makineye yüklenebilir.

- Bağlayıcı **Exchange CAS ortamını** destekler. İsterseniz, teknik olarak bağlayıcıyı doğrudan Exchange CAS sunucusuna yükleyebilirsiniz, ancak sunucu üzerindeki yükü artıracağından bunun yapılması önerilmez. Bağlayıcıyı yapılandırırken Exchange CAS sunucularından biriyle iletişim kurabilecek şekilde yapılandırmanız gerekir.

- **Exchange ActiveSync**, sertifika tabanlı kimlik doğrulaması veya kullanıcı kimlik bilgileri girişiyle yapılandırılmalıdır.

- Koşullu biçimlendirme ilkeleri yapılandırıldığında ve hedef kullanıcı belirlendiğinde, kullanıcının e-postasına bağlanabilmesi için önce **cihazın** şu özellikleri taşıması gerekir:
    - Intune’a **kayıtlı** veya etki alanına katılmış bir bilgisayar olmalıdır.
    - **Azure Active Directory’de kayıtlı olmalıdır**. Buna ek olarak, istemci Exchange ActiveSync kimliği Azure Active Directory’de kayıtlı olmalıdır.
<br></br>
- Azure AD Cihaz Kayıt Hizmeti (DRS), Intune ve Office 365 müşterileri için otomatik olarak etkinleştirilir. ADFS Cihaz Kayıt Hizmeti'ni zaten dağıtmış olan müşteriler, kayıtlı cihazlarını şirket içi Active Directory'lerinde görmez. **Bu, Windows bilgisayarları ve Windows Phone cihazları için geçerli değildir**.

- Söz konusu cihaza dağıtılan cihaz uyumluluk ilkeleriyle **uyumluluk**.

- Cihaz, koşullu erişim ayarlarına uyum sağlamıyorsa kullanıcıya oturum açtığında aşağıdaki iletilerden biri gösterilir:
    - Cihaz Intune’a kaydolmadıysa veya Azure Active Directory’de kayıtlı değilse, Şirket Portalı uygulamasını yükleme, cihazı kaydetme ve e-postayı etkinleştirme yönergelerinin bulunduğu bir ileti görüntülenir. Bu işlem cihazın Exchange ActiveSync kimliğini de Azure Active Directory’deki cihaz kaydıyla ilişkilendirir.
    - Cihaz uyumlu değilse, kullanıcıyı sorun hakkında bilgi bulabileceği ve sorunu düzeltebileceği Intune Şirket Portalı Web sitesine veya Şirket Portalı uygulamasına yönlendiren bir ileti görüntülenir.

### <a name="support-for-mobile-devices"></a>Mobil cihaz desteği

- Windows Phone 8.1 ve üzeri
- iOS’ta yerel e-posta uygulaması.
- Android 4 veya sonraki sürümlerdeki Gmail gibi EAS posta istemcileri.
- EAS posta istemcileri **Android iş profili cihazları:** Android iş profili cihazlarında yalnızca **iş profilindeki** **Gmail** ve **Nine Work** uygulamaları desteklenir. Android iş profili cihazlarında koşullu erişimin çalışması için Gmail veya Nine Work uygulamasına yönelik bir e-posta profili dağıtmalısınız. Ayrıca bu uygulamaları da zorunlu yükleme olarak dağıtmanız gerekir.

> [!NOTE]
> Android ve iOS için Microsoft Outlook uygulaması desteklenmez. 

### <a name="support-for-pcs"></a>Bilgisayarlar için destek

Windows 8.1 ve üstündeki yerel **Posta** uygulaması (Intune ile kaydedildiğinde)


## <a name="configure-exchange-on-premises-access"></a>Şirket içi Exchange erişimini yapılandırma

1. [Azure portalı](https://portal.azure.com/)’na gidin ve Intune kimlik bilgilerinizle oturum açın.

1. Oturumunuz başarıyla açıldıktan sonra **Azure Panosu**'nu görürsünüz.

1. Soldaki menüden **Tüm hizmetler**’i seçtikten sonra metin kutusu filtresine **Intune** yazın.

1. **Intune**’u seçin, **Intune Panosu**’nu görürsünüz.

1. **Şirket içi erişim**'i seçin. **Şirket içi erişim** bölmesinde koşullu erişim ilkesinin durumu ve bundan etkilenen cihazlar gösterilir.

1. **Yönet**’in altında **Şirket içi Exchange erişimi**’ni seçin.

1. **Şirket içi Exchange erişimi** bölmesinde **Evet**’i seçerek şirket içi Exchange erişim denetimini etkinleştirin.

    > [!NOTE]
    > Exchange Active Sync şirket içi bağlayıcısını yapılandırmadıysanız, bu seçenek devre dışı bırakılır.  Şirket içi Exchange için koşullu erişimi etkinleştirebilmek için önce en az bir bağlayıcıyı yüklemeli ve yapılandırmalısınız. Diğer ayrıntılar için bkz. [Intune Şirket İçi Exchange Connector’ı yükleme](exchange-connector-install.md).

1. **Atama**’nın altında **Eklenen Gruplar**’ı seçin.  Koşullu erişimin uygulanacağı güvenlik kullanıcı grubunu seçin. Bu eylem için kullanıcıların cihazlarını Intune’da kaydetmeleri ve uyumluluk profilleriyle uyumlu olmaları gerekir.

1. Belirli kullanıcı gruplarını dışta tutmak istiyorsanız, **Dışlanan Gruplar**’ı seçip ardından da cihaz kaydı ve uyumluluk gereksiniminden muaf tutmak istediğiniz kullanıcı grubunu seçerek bunu yapabilirsiniz.

1. Varsayılan e-posta iletisini değiştirmek için, **Ayarlar**’ın altında **Kullanıcı bildirimleri**’ni seçin. Bu ileti, cihazı uyumlu olmayan ve şirket içi Exchange’e erişmek isteyen kullanıcılara gönderilir. İleti şablonunda Biçimlendirme dili kullanılır.  Ayrıca yazarken iletinin nasıl görüneceğini gösteren bir önizleme de görebilirsiniz.
    > [!TIP]
    > Biçimlendirme dili hakkında daha fazla bilgi edinmek için bu Wikipedia [makalesine](https://en.wikipedia.org/wiki/Markup_language) bakın.

1. **Gelişmiş Exchange Active Sync erişim ayarları** bölmesinde, Intune tarafından yönetilmeyen cihazlardan erişim için ve sonraki iki adımda açıklandığı gibi platform düzeyi kuralları için genel varsayılan kuralı ayarlayın.

1. Koşullu erişimden veya diğer kurallardan etkilenmeyen bir cihaz söz konusu olduğunda, cihazın Exchange’e erişmesine izin vermeyi, veya engellemeyi seçebilirsiniz.

   - Bunu erişime izin verecek şekilde ayarlarsanız, tüm cihazlar şirket içi Exchange’e hemen erişebilir.  **Eklenen Gruplar** içindeki kullanıcılara ait cihazlar, sonunda uyumluluk ilkelerine uymadığı veya Intune’a kaydedilmemiş olduğu belirlenirse engellenir.
   - Bunu erişimi engelleyecek şekilde ayarlarsanız, başlangıçta tüm cihazların şirket içi Exchange’e erişimi hemen engellenir.  **Eklenen Gruplar** içindeki kullanıcılara ait cihazlar, Intune’a kaydolduğunda ve uyumlu olarak değerlendirildiğinde erişim kazanır. Samsung Knox Standard çalıştırmayan Android cihazlar bu ayarı desteklemediğinden, her zaman engellenir.

1. **Cihaz platformu özel durumları**’nın altında **Ekle**’yi seçerek platformları belirtin. **Yönetilmeyen cihaz erişimi** ayarı **engellendi** olarak belirlenirse, engellemek için bir platform özel durumu olsa bile, kayıtlı ve uyumlu cihazlara izin verilir. Ayarları kaydetmek için **Tamam**’ı seçin.

1. **Şirket içi** bölmesinde **Kaydet**’e tıklayarak koşullu erişim ilkesini kaydedin.

## <a name="create-azure-ad-conditional-access-policies-in-intune"></a>Intune'da Azure AD Koşullu erişim ilkeleri oluşturma

Intune 1704 sürümünden başlayarak, yöneticiler Intune Azure portalından Azure AD koşullu erişim ilkeleri oluşturabilir ve bu sayede, Azure ve Intune iş yükleri arasında geçiş yapmanıza gerek kalmaz.

> [!IMPORTANT]
> Intune Azure portalından Azure AD koşullu erişim ilkeleri oluşturmak için bir Azure AD Premium lisansınız olması gerekir.

### <a name="to-create-azure-ad-conditional-access-policy"></a>Azure AD koşullu erişim ilkesi oluşturmak için

1. **Intune Panosu**’nda, **Koşullu erişim**’i seçin.

2. **İlkeler** bölmesinde **Yeni ilke**’yi seçerek yeni Azure AD koşullu erişim ilkenizi oluşturun.

## <a name="see-also"></a>Ayrıca bkz:

[Azure Active Directory’de Koşullu Erişim](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
