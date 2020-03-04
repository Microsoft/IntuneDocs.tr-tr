---
title: Intune ile iOS ve Android için Microsoft Edge 'i yönetme
titleSuffix: ''
description: Şirket web sitelerine her zaman karşı korumalar ile erişildiğinden emin olmak için Microsoft Edge ile Intune uygulama koruma ilkelerini kullanın.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/02/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3fb2f050-ec94-42ab-be05-c3d4101148bb
ms.reviewer: ilwu
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9092b40b25ccc19c8b0de97b23c96a845d578df7
ms.sourcegitcommit: a25f556aa9df4fcd9fdacccd12c9029bc6c5fe20
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/03/2020
ms.locfileid: "78256413"
---
# <a name="manage-web-access-by-using-microsoft-edge-with-microsoft-intune"></a>Microsoft Intune ile Microsoft Edge kullanarak Web erişimini yönetme

Intune uygulama koruma ilkelerinin Microsoft Edge ile kullanılması, kurumsal web sitelerine her zaman korumasıyla erişilmesine yardımcı olur. Intune ilkeleri tarafından etkinleştirilen aşağıdaki Microsoft Edge kurumsal özellikleri kullanılabilir:

- **Çift kimlik.** Kullanıcılar, göz atmak için bir iş hesabı ve kişisel hesap ekleyebilir. Office 365 ve Outlook mimarilerinde ve deneyimlerinde olduğu gibi iki kimlik arasında belirgin bir ayrım vardır. Intune yöneticileri, iş hesabı içinde korunan bir gözatma deneyimi için istenen ilkeleri ayarlayabilir.
- **Intune uygulama koruma ilkesi tümleştirmesi.** Microsoft Edge, Intune SDK ile tümleştirildiği için, veri kaybına karşı korunmak üzere uygulama koruma ilkelerini hedefleyebilirsiniz. Bu yetenekler arasında kesme, kopyalama ve yapıştırmayı denetleme, ekran yakalamaları ve Kullanıcı tarafından seçilen bağlantıların yalnızca diğer yönetilen uygulamalarda açılmasını sağlama sayılabilir.
- **Azure uygulama proxy 'Si tümleştirmesi.** Hizmet olarak yazılım (SaaS) uygulamaları ve Web uygulamaları için erişimi denetleyebilirsiniz. Bu, son kullanıcıların kurumsal ağdan bağlanıp internet 'ten bağlanmasına bakılmaksızın, tarayıcı tabanlı uygulamaların yalnızca güvenli Microsoft Edge tarayıcısında çalıştırılmasını sağlamaya yardımcı olur.
- **Uygulama yapılandırması.** Kuruluşunuzun güvenlik duruşunuzu güçlendirin ve son kullanıcılarınız için kullanım kolaylığı özelliklerini yapılandırmak için uygulama yapılandırma ayarlarını kullanabilirsiniz. Örneğin, yer işaretleri, bir giriş sayfası kısayolu, izin verilen veya engellenen siteler ve Azure Active Directory (Azure AD) uygulama proxy 'Si tanımlayabilirsiniz.

Microsoft Edge için Microsoft Intune koruma ilkeleri, kuruluşunuzun verilerini ve kaynaklarını korumanıza yardımcı olur. Bu ilkelerin Microsoft Edge ile kullanılması, şirketinizin kaynaklarının yalnızca yerel olarak yüklü uygulamalar içinde değil, ayrıca Web tarayıcısından erişilen şekilde korunmasını sağlar.

## <a name="getting-started"></a>Başlarken

Siz ve son kullanıcılarınız, kuruluşunuzda kullanılmak üzere genel uygulama mağazalarından Microsoft Edge 'i indirebilir. Tarayıcı ilkeleri için işletim sistemi gereksinimleri aşağıdakilerden biri olabilir:
- Android 4 ve üzeri
- iOS 8.0 ve üzeri

## <a name="application-protection-policies-for-microsoft-edge"></a>Microsoft Edge için uygulama koruma ilkeleri

Microsoft Edge, Intune SDK ile tümleşik olduğundan, bunlara uygulama koruma ilkeleri uygulayabilirsiniz.

Bu ayarları şunlara uygulayabilirsiniz:
- Intune 'a kayıtlı cihazlar.
- Başka bir mobil cihaz yönetim ürünüyle kaydedilen cihazlar.
- Yönetilmeyen cihazlar.

Microsoft Edge, Intune ilkesi ile hedeflenmediğinde, kullanıcılar, Office uygulamaları gibi diğer Intune tarafından yönetilen uygulamalardan verilere erişmek için bunu kullanamaz. 

## <a name="conditional-access-for-microsoft-edge"></a>Microsoft Edge için koşullu erişim

Kullanıcılarınıza yalnızca Microsoft Edge aracılığıyla şirket içeriğine erişmek üzere yönlendirmek için Azure AD koşullu erişimi kullanabilirsiniz. Bu, mobil tarayıcı erişimini Azure AD ile bağlantılı Web uygulamalarına İlkeyle korunan Microsoft Edge 'e kısıtlar. Bu, Safari veya Chrome gibi korumasız tüm tarayıcılardan erişimi engeller. Exchange Online ve SharePoint Online gibi Azure kaynaklarına koşullu erişim, Microsoft 365 Yönetim Merkezi ve hatta [azure ad uygulama ara sunucusu](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started)aracılığıyla dış kullanıcılara kullanıma sunulacak şirket içi siteler uygulayabilirsiniz.

Azure AD bağlantılı web uygulamalarının iOS ve Android 'de Microsoft Edge 'i kullanacak şekilde kısıtlamak için:
1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. Intune düğümü altında, **koşullu erişim** > **Yeni ilke**' yi seçin.
3. Bölmenin **erişim denetimleri** bölümünden **ver** ' i seçin.
4. **Onaylı istemci uygulaması gerektir**’e tıklayın.
5. **İzin** bölmesinde **Seç ' i** seçin. Bu ilke, yalnızca Intune Managed Browser uygulaması tarafından erişilebilir olmasını istediğiniz bulut uygulamalarına atanmalıdır.

    ![Koşullu erişim ilkesi-verme ekran görüntüsü](./media/manage-microsoft-edge/manage-microsoft-edge-01.png)

6. Atamalar bölümünde, **uygulamalar** > **koşullar** ' ı seçin. **Uygulamalar** bölmesi görüntülenir.
7. **Yapılandır**' ın altında, ilkeyi belirli istemci uygulamalarına uygulamak için **Evet** ' i seçin.
8. **Tarayıcı**’nın bir istemci uygulaması olarak seçildiğini doğrulayın.

    ![Koşullu erişim ilkesinin ekran görüntüsü-istemci uygulamalarını seçin](./media/manage-microsoft-edge/manage-microsoft-edge-02.png)

    > [!NOTE]
    > Bu bulut uygulamalarına erişebilecek yerel uygulamaları (tarayıcı olmayan uygulamalar) kısıtlamak için **Mobil uygulamalar ve masaüstü istemciler**’i de seçebilirsiniz.

9. **Atamalar** bölümünde **Kullanıcılar ve gruplar**' ı seçin ve ardından bu ilkeyi atamak istediğiniz kullanıcıları veya grupları seçin.

10. **Atamalar** bölümünde **Bulut uygulamaları**’nı seçerek bu ilkeyle hangi uygulamaları koruyacağınızı seçin.

Yukarıdaki ilke yapılandırıldıktan sonra, kullanıcılar Microsoft Edge 'i kullanarak bu ilkeyle koruduğunuz Azure AD bağlantılı Web uygulamalarına erişim için zorlanır. Kullanıcılar bu senaryoda yönetilmeyen bir tarayıcı kullanmayı denediklerinde, Microsoft Edge kullanması gereken bir ileti alırlar.

> [!TIP]
> Koşullu erişim bir Azure AD teknolojisidir. Intune 'dan erişilen koşullu erişim düğümü, Azure AD 'den erişilen aynı düğümdür.

## <a name="single-sign-on-to-azure-ad-connected-web-apps-in-policy-protected-browsers"></a>İlkeyle korunan tarayıcılarda Azure AD 'ye bağlı Web Apps 'te çoklu oturum açma

İOS ve Android 'de Microsoft Edge, Azure AD 'ye bağlı olan tüm Web uygulamalarına (SaaS ve şirket içi) çoklu oturum açma (SSO) özelliğinden yararlanabilir. SSO, kullanıcıların kimlik bilgilerini yeniden girmeye gerek kalmadan, Microsoft Edge aracılığıyla Azure AD bağlantılı Web uygulamalarına erişmelerini sağlar.

SSO, cihazınızın iOS cihazları için Microsoft Authenticator uygulaması veya Android üzerindeki Intune Şirket Portalı kaydedilmesini gerektirir. Kullanıcılar bunlardan herhangi birine sahip olduklarında, ilke korumalı bir tarayıcıda Azure AD 'ye bağlı bir Web uygulamasına gittiklerinde cihazlarını kaydetmeleri istenir. (Bu, yalnızca cihazı kayıtlı değilse geçerlidir.) Cihaz, kullanıcının Intune tarafından yönetilen hesabına kaydedildikten sonra, bu hesabın Azure AD 'ye bağlı Web uygulamaları için etkin SSO 'SU vardır.

> [!NOTE]
> Cihaz kaydı, Azure AD hizmeti ile basit bir iade etme işlemidir. Tam cihaz kaydı gerektirmez ve bu cihaza cihazda ek ayrıcalıklar vermez.

## <a name="create-a-protected-browser-app-configuration"></a>Korumalı tarayıcı uygulama yapılandırması oluşturma

Microsoft Edge için uygulama yapılandırması oluşturmak için:

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Ekle** > **uygulama yapılandırma ilkeleri** > **uygulamalar** ' ı seçin.
3. **Yapılandırma Ilkesi Ekle** bölmesinde, uygulama yapılandırma ayarları Için bir **ad** ve isteğe bağlı bir **Açıklama** girin.
4. **Cihaz kayıt** türü için **Yönetilen uygulamalar**’ı seçin.
5. **Gerekli uygulamayı Seç ' i**seçin. Ardından, **hedeflenen uygulamalar** bölmesinde IOS/ıpados, Android için veya her ikisi için **Managed Browser** veya **kenarı** seçin.
6. **Yapılandırma Ilkesi Ekle** bölmesine dönmek için **Tamam ' ı** seçin.
7. **Yapılandırma ayarlarını** seçin. **Yapılandırma** bölmesinde, Microsoft Edge yapılandırmalarını sağlamak için anahtar ve değer çiftlerini tanımlarsınız. Tanımlayabileceğiniz farklı anahtar ve değer çiftleri hakkında bilgi edinmek için bu makalenin ilerleyen bölümlerine göz atın.

    > [!NOTE]
    > Microsoft Edge, Managed Browser ile aynı anahtar ve değer çiftini kullanır. Android 'de, uygulama yapılandırma ilkelerinin etkili olabilmesi için Microsoft Edge 'in uygulama koruma ilkelerini hedeflemeli olması gerekir.

8. İşiniz bittiğinde **Tamam**' ı seçin.
9. **Yapılandırma Ilkesi Ekle** bölmesinde **Ekle**' yi seçin.<br>
    Yeni yapılandırma oluşturulur ve **uygulama yapılandırma** bölmesinde görüntülenir.

## <a name="assign-the-configuration-settings-you-created"></a>Oluşturduğunuz yapılandırma ayarlarını atama 

Ayarları Azure AD 'deki Kullanıcı gruplarına atarsınız. Bu kullanıcı hedeflenen korumalı tarayıcı uygulamasını yüklemişse uygulama belirttiğiniz ayarlarla yönetiliyordur.

1. Intune mobil uygulama yönetimi panosunun **uygulamalar** bölmesinde **uygulama yapılandırma ilkeleri**' ni seçin.
2. Uygulama yapılandırmaları listesinden atamak istediğiniz birini seçin.
3. Sonraki bölmede, **atamalar**' ı seçin.
4. **Atamalar** bölmesinde, uygulama yapılandırmasını atamak ISTEDIĞINIZ Azure AD grubunu seçin ve ardından **Tamam**' ı seçin.

## <a name="direct-users-to-microsoft-edge-instead-of-the-intune-managed-browser"></a>Kullanıcıları Intune Managed Browser yerine Microsoft Edge 'e yönlendirin 

Hem Intune Managed Browser hem de Microsoft Edge İlkeyle korunan tarayıcılar olarak kullanılabilir. Kullanıcılarınızın doğru tarayıcı uygulamasını kullanmak üzere yönlendirildiğinden emin olmak için Intune tarafından yönetilen tüm uygulamalarınızı (örneğin, Outlook, OneDrive ve SharePoint) aşağıdaki yapılandırma ayarıyla hedefleyin:

|    Anahtar    |    Değer    |
|------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.useEdge`    |    `true` değeri, kullanıcılarınıza Microsoft Edge 'i indirmek ve kullanmak için yönlendirecektir.<br>`false` değeri, kullanıcılarınızın Intune Managed Browser kullanmasına izin verir.    |

Bu uygulama yapılandırma **değeri ayarlanmamışsa,** aşağıdaki mantık kurumsal bağlantıları açmak için kullanılacak tarayıcıyı tanımlar.

Android’de:
- Intune Managed Browser, bir Kullanıcı cihazındaki hem Intune Managed Browser hem de Microsoft Edge 'e indirildiyse başlatılır. 
- Microsoft Edge, cihazda yalnızca Microsoft Edge indirildiyse ve Intune ilkesi ile hedeflenirse başlatılır.
- Managed Browser, yalnızca cihazda Managed Browser ve Intune ilkesiyle hedeflenirse başlatılır.

İOS/ıpados ' da iOS için Intune SDK 'Sı ile tümleştirilmiş uygulamalar için. 9.0.9+:
- Intune Managed Browser, hem Managed Browser hem de Microsoft Edge cihazında yer alıyorsa başlatılır.  
- Microsoft Edge, yalnızca cihazda Microsoft Edge varsa ve Intune ilkesi ile hedeflenirse başlatılır.
- Managed Browser, yalnızca cihazda Managed Browser ve Intune ilkesiyle hedeflenirse başlatılır.

## <a name="configure-application-proxy-settings-for-microsoft-edge"></a>Microsoft Edge için uygulama proxy 'Si ayarlarını yapılandırma

Kullanıcılara mobil cihazlarındaki intranet sitelerine erişim sağlamak için Microsoft Edge ve [Azure AD uygulama ara sunucusu](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) birlikte kullanabilirsiniz. 

Azure AD Uygulama Ara Sunucusu Etkinleştirme senaryolarına bazı örnekler aşağıda verilmiştir: 

- Kullanıcı, Intune tarafından korunan Outlook mobil uygulamasını kullanıyor. Ardından, bir e-postada intranet sitesinin bağlantısına tıklamıştır ve Microsoft Edge, bu intranet sitesinin kullanıcı tarafından uygulama proxy 'Si aracılığıyla sunulduğunu algılar. Kullanıcı, intranet sitesine ulaşmadan önce geçerli bir Multi-Factor Authentication ve koşullu erişim ile kimlik doğrulamak için uygulama proxy 'Si üzerinden otomatik olarak yönlendirilir. Kullanıcı artık mobil cihazlarında bile iç sitelere erişebiliyor ve Outlook 'taki bağlantı beklendiği gibi çalışıyor.
- Kullanıcı iOS veya Android cihazında Microsoft Edge 'i açar. Microsoft Edge Intune ile korunuyorsa ve uygulama proxy 'Si etkinse, Kullanıcı, kullanıldıkları iç URL 'YI kullanarak bir intranet sitesine gidebilir. Microsoft Edge, bu intranet sitesinin kullanıcıya uygulama proxy 'Si aracılığıyla sunulduğunu algılar. Kullanıcı, intranet sitesine ulaşmadan önce kimlik doğrulaması yapmak için uygulama proxy 'Si üzerinden otomatik olarak yönlendirilir. 

### <a name="before-you-start"></a>Başlamadan önce

- Azure AD Uygulama Ara Sunucusu aracılığıyla iç uygulamalarınızı ayarlayın.
  - Uygulama Proxy’sini yapılandırmak ve uygulama yayımlamak için bkz. [kurulum belgeleri](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).
- Microsoft Edge uygulamasına [Intune uygulama koruma ilkesi](app-protection-policy.md) atanmış olmalıdır.

> [!NOTE]
> Güncelleştirilmiş Uygulama Ara Sunucusu’nun yeniden yönlendirme verilerinin Managed Browser’da veya Microsoft Edge'de etkinleşmesi 24 saati bulabilir.

#### <a name="step-1-enable-automatic-redirection-to-microsoft-edge-from-outlook"></a>1\. Adım: otomatik yeniden yönlendirmeyi Outlook 'tan Microsoft Edge 'e etkinleştirme
Outlook 'U **ilke ile yönetilen tarayıcılarla Web Içeriği paylaşma**ayarını sağlayan bir uygulama koruma ilkesiyle yapılandırın.

![Uygulama koruma ilkesinin ekran görüntüsü-ilke ile yönetilen tarayıcılarla Web içeriğini paylaşma](./media/manage-microsoft-edge/manage-microsoft-edge-03.png)

#### <a name="step-2-set-the-app-configuration-setting-to-enable-app-proxy"></a>2\. Adım: uygulama proxy 'sini etkinleştirmek için uygulama yapılandırma ayarını ayarlama
Microsoft Edge için uygulama ara sunucusunu etkinleştirmek üzere aşağıdaki anahtar/değer çiftine sahip Microsoft Edge 'i hedefleyin:

|    Anahtar    |    Değer    |
|-------------------------------------------------------------------|-------------|
|    com. Microsoft. Intune. mam. managedbrowser. AppProxyRedirection    |    true    |

Şirket içi Web uygulamalarına sorunsuz (ve korumalı) erişim için Microsoft Edge ve Azure AD Uygulama Ara Sunucusu kullanma hakkında daha fazla bilgi için bkz. [daha iyisi: Intune ve Azure Active Directory ekibi, Kullanıcı erişimini geliştirmek için](https://techcommunity.microsoft.com/t5/enterprise-mobility-security/better-together-intune-and-azure-active-directory-team-up-to/ba-p/250254). Bu blog gönderisi Intune Managed Browser başvuruyor, ancak içerik Microsoft Edge 'e de uygulanır.

## <a name="configure-a-homepage-shortcut-for-microsoft-edge"></a>Microsoft Edge için bir giriş sayfası kısayolu yapılandırma

Bu ayar, Microsoft Edge için bir giriş sayfası kısayolu yapılandırmanıza olanak tanır. Yapılandırdığınız giriş sayfası kısayolu, Kullanıcı Microsoft Edge 'de yeni bir sekme açtığında arama çubuğunun altında ilk simge olarak görünür. Kullanıcı, yönetilen bağlamlarına bu kısayolu düzenleyemez veya silemez. Ana sayfa kısayolu, kuruluşunuzun adını ayırt etmek için görüntüler. 

Bir giriş sayfası kısayolunu yapılandırmak için aşağıdaki anahtar/değer çiftini kullanın:

|    Anahtar    |    Değer    |
|-------------------------------------------------------------------|-------------|
|    com. Microsoft. Intune. mam. managedbrowser. giriþ   |    Geçerli bir URL belirtin. Hatalı URL’ler güvenlik önlemi olarak engellenir.<br>**Örnek:**  <`https://www.bing.com`>

## <a name="configure-multiple-top-site-shortcuts-for-new-tab-pages-in-microsoft-edge"></a>Microsoft Edge 'de yeni sekme sayfaları için birden çok üst site kısayolunu yapılandırma 
Benzer şekilde, bir giriş sayfası kısayolunu yapılandırmak için, Microsoft Edge 'de yeni sekme sayfalarında birden çok üst site kısayolunu yapılandırabilirsiniz. Kullanıcı yönetilen bağlamdaki bu kısayolları düzenleyemez veya silemez.

|    Anahtar    |    Değer    |
|-------------------------------------------------------------------|-------------|
|    com. Microsoft. Intune. mam. managedbrowser. managedTopSites   |    Değer URL 'Leri kümesi belirtin. Her üst site kısayolu bir başlık ve URL 'den oluşur. Başlığı ve URL 'YI `|` karakteriyle ayırın. Örneğin: <br> `GitHub | https://github.com/||LinkedIn|https://www.linkedin.com`

## <a name="configure-your-organizations-logo-and-brand-color-for-new-tab-pages-in-microsoft-edge"></a>Microsoft Edge 'de yeni sekme sayfaları için kuruluşunuzun logosunu ve marka rengini yapılandırın

Bu ayarlar, Microsoft Edge 'in yeni sekme sayfasını, sayfanın arka planı olarak kuruluşunuzun logosunu ve marka rengini görüntüleyecek şekilde özelleştirmenize olanak tanır.

Kuruluşunuzun logosunu ve rengini karşıya yüklemek için, önce aşağıdaki adımları uygulayın:
- Azure portal içinde, [Microsoft Endpoint Manager yönetim merkezi](https://go.microsoft.com/fwlink/?linkid=2109431) -> **Kiracı Yönetimi** -> **marka ve özelleştirme** -> **Şirket kimliği markalaması**' na gidin.
- Markanızı ayarlamak için "görüntü" altında "yalnızca şirket logosu" seçeneğini belirleyin. Saydam arka plan logoları önerilir. 
- Markaınızın arka plan rengini ayarlamak için "ekran" bölümünde "Tema rengi" seçeneğini belirleyin. Microsoft Edge, yeni sekme sayfasında rengin daha açık bir gölge kopyasını uygular ve bu da sayfanın yüksek okunabilirlik olmasını sağlar. 

Daha sonra, kuruluşların markasını Microsoft Edge 'e çekmek için aşağıdaki anahtar/değer çiftlerini kullanın:

|    Anahtar    |    Değer    |
|--------------------------------------------------------------------|------------|
|    com. Microsoft. Intune. mam. managedbrowser. NewTabPage. BrandLogo    |    Doğru    |
|    com. Microsoft. Intune. mam. managedbrowser. NewTabPage. BrandColor    |    Doğru    |

## <a name="display-relevant-industry-news-on-new-tab-pages"></a>Yeni sekme sayfalarında ilgili sektör haberlerini görüntüleme

Microsoft Edge Mobile içindeki yeni sekme sayfası deneyimini, kuruluşunuzla ilgili sektör haberlerini görüntüleyecek şekilde yapılandırabilirsiniz. Bu özelliği etkinleştirdiğinizde, Microsoft Edge Mobile kuruluşunuzun etki alanı adını kuruluşunuz, kuruluşunuzun sektör ve rakipler hakkında Web 'den toplamak için kullanır. böylece kullanıcılarınız, tüm merkezi yeni Microsoft Edge içindeki sekme sayfaları. Sektör Haberleri varsayılan olarak kapalıdır ve kuruluşunuz için bu uygulamayı kabul etmek için kullanabilirsiniz. 

|    Anahtar    |    Değer    |
|------------------------------------------------------|----------------------------------------------------------------------------------------------------------------|
|    com. Microsoft. Intune. mam. managedbrowser. NewTabPage. IndustryNews    |    **Doğru** , Microsoft Edge mobil yeni sekme sayfasında sektör haberlerini gösterir.<p>**False** (varsayılan), sektör haberlerini yeni sekme sayfasından gizler.    |

## <a name="configure-managed-bookmarks-for-microsoft-edge"></a>Microsoft Edge için yönetilen yer imlerini yapılandırma

Erişim kolaylığı için, kullanıcılarınızın Microsoft Edge kullanırken kullanılabilir olmasını istediğiniz yer imlerini yapılandırabilirsiniz. 

Bazı ayrıntılar aşağıda verilmiştir:

- Bu yer işaretleri yalnızca kullanıcılar Microsoft Edge 'in [Kurumsal modunu](https://docs.microsoft.com/intune/apps/app-configuration-managed-browser#how-to-configure-bookmarks-for-a-protected-browser) kullanırken görüntülenir. 
- Bu yer işaretleri kullanıcılar tarafından silinemez veya değiştirilemez.
- Bu yer işaretleri listenin en üstünde görünür. Kullanıcıların oluşturmakta olduğu tüm yer işaretleri bu yer işaretlerinin altında görünür.
- Uygulama proxy 'Si yeniden yönlendirmeyi etkinleştirdiyseniz, iç veya dış URL 'lerini kullanarak uygulama proxy 'Si Web uygulamaları ekleyebilirsiniz.
- **Http://** veya **https://** ile tüm URL 'leri listeye girerken ön ek olduğunuzdan emin olun.

Yönetilen yer imlerini yapılandırmak için aşağıdaki anahtar/değer çiftini kullanın:

|    Anahtar    |    Değer    |
|---------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    com. Microsoft. Intune. mam. managedbrowser. yer imleri    |    Bu yapılandırmanın değeri, yer işaretlerinin bir listesidir. Her yer işareti, yer işareti başlığından ve yer işareti URL 'sinden oluşur. Başlığı ve URL 'YI `|` karakteriyle ayırın.      Örnek:<br>`Microsoft Bing|https://www.bing.com`<br>Birden çok yer işaretini yapılandırmak için, her çifti çift karakterle ayırın `||`.<p>Örnek:<br>`Microsoft Bing|https://www.bing.com||Contoso|https://www.contoso.com`    |

## <a name="display-myapps-within-microsoft-edge-bookmarks"></a>Microsoft Edge yer işaretleri içinde Uygulamaps 'Leri görüntüleme

Varsayılan olarak, kullanıcılarınız Microsoft Edge yer işaretleri içindeki bir klasör içinde kendilerine yapılandırılmış olan Uygulamaps sitelerini gösterilir. Klasör, kuruluşunuzun adıyla etiketlenir.

|    Anahtar    |    Değer    |
|------------------------------------------------------|----------------------------------------------------------------------------------------------------------------|
|    com. Microsoft. Intune. mam. managedbrowser. Uygulamaps    |    **Doğru** , Microsoft Edge yer Işaretlerinin Içindeki uygps 'leri gösterir.<p>**False** , Microsoft Edge Içindeki uygulamaps 'leri gizler.    |

## <a name="specify-allowed-or-blocked-sites-list-for-microsoft-edge"></a>Microsoft Edge için izin verilen veya engellenen siteler listesini belirtin
Kullanıcılarınızın iş profilini kullanırken erişebileceği siteleri tanımlamak için uygulama yapılandırması ' nı kullanabilirsiniz. Bir izin verilenler listesi kullanırsanız, kullanıcılarınız yalnızca açıkça listelenen sitelere erişebilir. Engellenen bir liste kullanıyorsanız, kullanıcılarınız, açıkça engellediğiniz durumlar hariç tüm sitelere erişebilir. Yalnızca izin verilen veya engellenen bir liste oluşturmanız gerekir, her ikisini birden değil. Her ikisini de ayarlarsanız, izin verilen liste kabul edilir.  

Microsoft Edge için izin verilen veya engellenen bir site listesini yapılandırmak için aşağıdaki anahtar/değer çiftlerini kullanın. 

|    Anahtar    |    Değer    |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Aşağıdakilerden birini seçin:<p>1. izin verilen URL 'Leri belirtin (yalnızca bu URL 'Lere izin verilir; başka sitelere erişilemez):<br>`com.microsoft.intune.mam.managedbrowser.AllowListURLs`<p>2. Engellenen URL 'Leri belirtin (diğer tüm sitelere erişilebilir):<br>`com.microsoft.intune.mam.managedbrowser.BlockListURLs`    |    Bir anahtara karşılık gelen değer bir URL listesidir. İzin vermek veya engellemek istediğiniz tüm URL 'Leri, kanal `|` karakteriyle ayırarak tek bir değer olarak girersiniz.<br>**Örnekler**<br>`URL1|URL2|URL3`<br>`http://.contoso.com/|https://.bing.com/|https://expenses.contoso.com`  |

### <a name="url-formats-for-allowed-and-blocked-site-list"></a>İzin verilen ve engellenen site listesi için URL biçimleri 
İzin verilen/Engellenen siteler listelerinizi oluşturmak için çeşitli URL biçimleri kullanabilirsiniz. Bu izin verilen desenler aşağıdaki tabloda ayrıntılı olarak verilmiştir. Başlamadan önce bazı notlar: 
- **Http://** veya **https://** ile tüm URL 'leri listeye girerken ön ek olduğunuzdan emin olun.
- Aşağıdaki izin verilen desenler listesindeki kurallara göre joker karakter sembolünü (\*) kullanabilirsiniz.
- Joker karakter, ana bilgisayar adının tamamını (noktalarla ayırarak) veya yolun tüm parçalarını (eğik çizgi ile ayrılmış olarak) eşleştirebilir. Örneğin **, `http://*contoso.com` desteklenmez.**
- Adreste bağlantı noktası numaraları belirtebilirsiniz. Bir bağlantı noktası numarası belirtmezseniz, kullanılan değerler şöyle olacaktır:
  - http için bağlantı noktası 80
  - https için bağlantı noktası 443
- Bağlantı noktası numarası için joker karakter kullanılması **desteklenmez.** Örneğin `http://www.contoso.com:*` ve `http://www.contoso.com:*/` desteklenmez. 

    |    {1&gt;URL&lt;1}    |    Ayrıntılar    |    Eşleşir    |    Eşleşmez    |
    |-------------------------------------------|--------------------------------------------------------|-------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
    |    `http://www.contoso.com`    |    Tek bir sayfayla eşleşir    |    `www.contoso.com`    |    `host.contoso.com`<br>`www.contoso.com/images`<br>`contoso.com/`    |
    |    `http://contoso.com`    |    Tek bir sayfayla eşleşir    |    `contoso.com/`    |    `host.contoso.com`<br>`www.contoso.com/images`<br>`www.contoso.com`    |
    |    `http://www.contoso.com/*;`   |    `www.contoso.com` ile başlayan tüm URL’lerle eşleşir    |    `www.contoso.com`<br>`www.contoso.com/images`<br>`www.contoso.com/videos/tvshows`    |    `host.contoso.com`<br>`host.contoso.com/images`    |
    |    `http://*.contoso.com/*`    |    `contoso.com` altındaki tüm alt etki alanlarını eşleştirir    |    `developer.contoso.com/resources`<br>`news.contoso.com/images`<br>`news.contoso.com/videos`    |    `contoso.host.com`
    |    `http://*contoso.com/*`    |    `contoso.com/` ile biten tüm alt etki alanlarını eşleştirir    |    `http://news-contoso.com`<br>`http://news-contoso.com.com/daily`    |    `http://news-contoso.host.com`    |
    `http://www.contoso.com/images`    |    Tek bir klasörle eşleşir    |    `www.contoso.com/images`    |    `www.contoso.com/images/dogs`    |
    |    `http://www.contoso.com:80`    |    Bir bağlantı noktası numarası kullanarak tek bir sayfayla eşleşir    |    `http://www.contoso.com:80`    |         |
    |    `https://www.contoso.com`    |    Güvenli tek bir sayfayla eşleşir    |    `https://www.contoso.com`    |    `http://www.contoso.com`    |
    |    `http://www.contoso.com/images/*`    |    Tek bir klasör ve tüm alt klasörleriyle eşleşir    |    `www.contoso.com/images/dogs`<br>`www.contoso.com/images/cats`    |    `www.contoso.com/videos`    |
  
- Aşağıda, belirtemeyeceğiniz bazı girişlerin örnekleri verilmiştir:
  - `*.com`
  - `*.contoso/*`
  - `www.contoso.com/*images`
  - `www.contoso.com/*images*pigs`
  - `www.contoso.com/page*`
  - IP adresleri
  - `https://*`
  - `http://*`
  - `https://*contoso.com`
  - `http://www.contoso.com:*`
  - `http://www.contoso.com: /*`

## <a name="transition-users-to-their-personal-context-when-trying-to-access-a-blocked-site"></a>Engellenen bir siteye erişmeye çalışırken kullanıcıları Kişisel bağlamlarına geçirme

Microsoft Edge 'de yerleşik olarak bulunan çift kimlik modeliyle, son kullanıcılarınız için Intune Managed Browser mümkün olandan daha esnek bir deneyim sağlayabilirsiniz. Kullanıcılar Microsoft Edge 'de engellenen bir siteye geldiğinde, bu kullanıcıdan, iş bağlamı yerine kendi kişisel bağlamlarından bağlantısını açmasını isteyebilirsiniz. Bu, kurumsal kaynakları güvenli tutarken korunmalarını sağlar. Örneğin, bir Kullanıcı Outlook aracılığıyla bir haber makalesine bağlantı gönderdiyse, bağlantıyı kişisel bağlamlarına veya bir InPrivate sekmesine açabilirler. İş bağlamları haber web sitelerine izin vermez. Varsayılan olarak, bu geçişlere izin verilir.

Bu yazılım geçişlerine izin verilip verilmeyeceğini yapılandırmak için aşağıdaki anahtar/değer çiftini kullanın:

|    Anahtar    |    Değer    |
|----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.mam.managedbrowser.AllowTransitionOnBlock`    |    **True** (varsayılan), Microsoft Edge 'in engellenen siteleri açmak için kullanıcıları Kişisel bağlamlarına geçişine olanak sağlar.<p>**False** , Microsoft Edge 'in kullanıcıları geçişini engeller. Kullanıcılara erişmeye çalıştıkları sitenin engellendiğini bildiren bir ileti gösterilir.    |

## <a name="disable-inprivate-and-microsoft-accounts-msa-to-restrict-personal-browsing"></a>Kişisel taramayı kısıtlamak için InPrivate ve Microsoft hesaplarını (MSA) devre dışı bırakın
Microsoft Edge ile uygulama başına VPN kullanan, yüksek düzeyde düzenlenen endüstrilerin bazı müşterileri, kullanıcıların yalnızca AAD bağlamlarında gezinmek için kapsam kullanmasını isteyebilir. Bunu başarmak için MDM cihazlarınız için aşağıdaki uygulama yapılandırma ayarlarını kullanabilirsiniz. Bu işlev, MAM kayıtlı cihazlar için kullanılamaz. 

|    Anahtar    |    Değer    |
|-------------------------------------------------------------------|-------------------------------------------------------|
|     `com.microsoft.intune.mam.managedbrowser.disabledFeatures`    |    **InPrivate** , InPrivate tarayıcıyı devre dışı bırakacak. <br> **MSA** , kullanıcıların Microsoft Edge 'e kişisel MSA hesapları ekleme yeteneğini devre dışı bırakır.<br> Hem InPrivate hem de MSA hesaplarını devre dışı bırakmak için `inprivate| msa` kullanın    |  


Ayrıca, kullanıcıların MDM cihazlarında Microsoft Edge Mobile ile gezinmelerini, **yalnızca** Kullanıcı AAD iş hesabıyla oturum açmışsa kısıtlayabilirsiniz. Microsoft Edge için yalnızca kuruluş hesabı modunu yapılandırma anahtarları hakkında daha fazla bilgi edinebilirsiniz:
- [Android org-yalnızca hesap](https://docs.microsoft.com/intune/apps/app-configuration-policies-use-android#allow-only-configured-organization-accounts-in-multi-identity-apps)
- [iOS org-yalnızca hesaplar](https://docs.microsoft.com/intune/apps/app-configuration-policies-use-ios#allow-only-configured-organization-accounts-in-multi-identity-apps)

## <a name="open-restricted-links-directly-in-inprivate-tab-pages"></a>Kısıtlanmış bağlantıları doğrudan InPrivate sekme sayfalarında aç

Sınırlı bağlantıların, kullanıcılara daha sorunsuz bir gözatma deneyimi sağlayan, InPrivate göz atmaya doğrudan açılması gerektiğini yapılandırabilirsiniz. Bu, kullanıcılara bir siteyi görüntülemek için kişisel bağlamlarına geçiş yapmak zorunda olma adımını kaydeder. InPrivate Gözatma yönetilmeyen olarak kabul edilir. bu nedenle, kullanıcılar InPrivate gözatma modunu kullanırken erişemez.

|    Anahtar    |    Değer    |
|----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.mam.managedbrowser.openInPrivateIfBlocked`    |    **Doğru** , kullanıcının kişisel hesabına anahtar yapmasını istemeden siteler doğrudan bir InPrivate sekmesinde otomatik olarak açılır. <p> **False** (varsayılan), siteyi Microsoft Edge içinde engeller ve kullanıcının, kendi kişisel hesabına görüntülemesi istenir.    |

## <a name="disable-microsoft-edge-features-to-customize-the-end-user-experience-for-your-organizations-needs"></a>Kuruluşunuzun ihtiyaçlarına göre son kullanıcı deneyimini özelleştirmek için Microsoft Edge özelliklerini devre dışı bırakın

### <a name="disable-prompts-to-share-usage-data-for-personalization"></a>Kullanım verilerini kişiselleştirme için paylaşmak üzere istemleri devre dışı bırak 

Varsayılan olarak, Microsoft Edge, kullanıcılara, kullanım verileri toplama 'nın gözatma deneyimini kişiselleştirmesini ister. Bu istemin son kullanıcılara görüntülenmesini engellemek için bu verilerin paylaşımını devre dışı bırakabileceksiniz. 

|    Anahtar    |    Değer    |
|----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.mam.managedbrowser.disableShareUsageData`    |     **true** , bu istemi son kullanıcılara görüntülemesini devre dışı bırakır.    |

### <a name="disable-prompts-to-share-browsing-history"></a>Gözatma geçmişini paylaşmak için istemleri devre dışı bırak 

Varsayılan olarak, Microsoft Edge, kullanıcıların gözatma deneyimini kişiselleştirmesini sağlayan geçmiş veri toplamayı gözden geçirme konusunda uyarır. Bu istemin son kullanıcılara görüntülenmesini engellemek için bu verilerin paylaşımını devre dışı bırakabileceksiniz.

|    Anahtar    |    Değer    |
|----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     `com.microsoft.intune.man.managedbrowser.disableShareBrowsingHistory`    |     **true** , bu istemi son kullanıcılara görüntülemesini devre dışı bırakır.     |

### <a name="disable-prompts-that-offer-to-save-passwords"></a>Parolaları kaydetmek için teklif eden istemleri devre dışı bırak
Varsayılan olarak, iOS 'ta Microsoft Edge, kullanıcılarınızın parolalarını anahtarlığa kaydetmenizi sağlar. Kuruluşunuz için bu istemi devre dışı bırakmak isterseniz, aşağıdaki ayarı yapılandırın:

|    Anahtar    |    Değer    |
|-----------------------|-----------------------|
|    `com.microsoft.intune.mam.managedbrowser.disableFeatures`    |    **parola** , son kullanıcının parolalarının kaydedilmesini sağlayan istemleri devre dışı bırakacak.    |

### <a name="disable-inprivate-browsing-and-microsoft-accounts-to-restrict-browsing-to-work-only-contexts"></a>Yalnızca iş bağlamlarına göz atmayı kısıtlamak için InPrivate Gözatma ve Microsoft hesaplarını devre dışı bırakın

Kuruluşunuz yüksek düzeyde düzenlenmiş bir sektörde çalışır veya kullanıcıların Microsoft Edge ile iş kaynaklarına erişmesine izin vermek için uygulama başına VPN kullanıyorsa, Microsoft Edge 'in kullanımını yalnızca MAM korumalı bir bağlam olarak seçebilirsiniz. Bu işlevsellik yalnızca MDM 'ye kayıtlı cihazlar için verilmiştir.

|    Anahtar    |    Değer    |
|-----------|-------------|
|    `com.microsoft.intune.mam.managedbrowser.disableFeatures`    |    **InPrivate** , InPrivate taramayı devre dışı bırakır. <br> **MSA** , kullanıcıların Microsoft Edge uygulamalarına kendi kişisel Microsoft HESAPLARıNı (MSA) eklemesini engeller. <br> Birden çok özelliği devre dışı bırakmak için değerleri `|`ayırın. Örneğin, `inprivate|msa` hem InPrivate hem de kişisel hesapların engellenmesini engeller.   |

### <a name="restrict-microsoft-edge-use-to-allowed-accounts-only"></a>Microsoft Edge kullanımını izin verilen-yalnızca hesaplar olarak kısıtla

InPrivate ve MSA taramayı engellemeye ek olarak, yalnızca Kullanıcı AAD hesabıyla oturum açtığında Microsoft Edge kullanımına izin verebilirsiniz. Bu özellik yalnızca MDM 'ye kayıtlı kullanıcılar için kullanılabilir. Bu ayarı yapılandırma hakkında daha fazla bilgi edinebilirsiniz:

- [Android ayarı](~/apps/app-configuration-policies-use-android.md#allow-only-configured-organization-accounts-in-multi-identity-apps)
- [iOS ayarı](~/apps/app-configuration-policies-use-ios.md#allow-only-configured-organization-accounts-in-multi-identity-apps)


## <a name="use-microsoft-edge-on-ios-to-access-managed-app-logs"></a>İOS üzerinde Microsoft Edge kullanarak yönetilen uygulama günlüklerine erişin 

İOS cihazlarında Microsoft Edge yüklü olan kullanıcılar, Microsoft tarafından yayımlanan tüm uygulamaların yönetim durumunu görüntüleyebilir. Yönetilen iOS uygulamalarında sorun gidermek için günlükleri gönderebilirler. Şöyle yapılır:
1. İOS cihazınızda Microsoft Edge 'i açın.
2. Adres kutusuna `about:intunehelp` yazın. 
3. Microsoft Edge, sorun giderme modunu başlatır.

Uygulama günlüklerinde saklanan ayarların bir listesi için, bkz. [Yönetilen Tarayıcı’da uygulama koruma günlüklerini inceleyin](app-protection-policy-settings-log.md).

Android cihazlarda günlükleri görüntüleme hakkında bilgi için bkz. [e-posta ile GÜNLÜKLERI BT yöneticinize gönderme](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android). 

## <a name="security-and-privacy-for-microsoft-edge"></a>Microsoft Edge için güvenlik ve Gizlilik

Microsoft Edge için ek güvenlik ve gizlilik konuları aşağıda verilmiştir:

- Microsoft Edge, kullanıcıların cihazlarında https://docs.microsoft.com/en-us/intune/apps/app-configuration-policies-use-android#allow-only-configured-organization-accounts-in-multi-identity-apps yerel tarayıcı için ayarlandığı ayarları tüketmez çünkü Microsoft Edge bu ayarlara erişemez.
- Microsoft Edge ile ilişkili bir uygulama koruma ilkesinde erişim için **basıt PIN gerektir** veya erişim **için şirket kimlik bilgilerini gerektir** seçeneğini yapılandırabilirsiniz. Bir kullanıcı kimlik doğrulama sayfasındaki yardım bağlantısını seçerse, ilkede engellenen bir listeye eklenmediğine bakılmaksızın herhangi bir internet sitesine göz atabilir.
- Microsoft Edge, sitelere yalnızca doğrudan erişildiğinde erişimi engelleyebilir. Kullanıcılar, siteye erişmek için ara hizmetler (örneğin bir çeviri hizmeti) kullandıklarında erişimi engellemez.
- Kimlik doğrulamasına izin vermek ve Intune belgelerine erişmek için * **. Microsoft.com** , izin verilenler veya engellenenler listesi ayarlarından muaf tutulur. Her zaman izin verilir.
- Kullanıcılar, veri toplamayı kapatabilir. Microsoft, ürün ve hizmetlerini geliştirmek için Managed Browser’ın performansı ve kullanımı hakkında otomatik olarak anonim bilgiler toplar. Kullanıcılar cihazlarındaki **Kullanım Verileri** ayarını kullanarak veri toplamayı kapatabilir. Bu verilerin toplanması üzerinde denetiminiz yoktur. İOS cihazlarda, kullanıcıların ziyaret ettiği veya güvenilmeyen bir sertifikaya sahip olan Web siteleri açılamaz.

## <a name="next-steps"></a>Sonraki adımlar

- [Uygulama koruma ilkeleri nedir?](app-protection-policy.md) 
