---
title: Microsoft Intune Microsoft Edge kullanarak Web erişimini yönetme
titleSuffix: ''
description: Intune uygulama koruma ilkeleri, şirket Web sitelerini her zaman yerinde koruma ile erişilen emin olmak için Microsoft Edge ile kullanın.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 06/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3fb2f050-ec94-42ab-be05-c3d4101148bb
ms.reviewer: ilwu
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b267e1c59ab59737b58b73054b90b0f8e026e959
ms.sourcegitcommit: cb4e71cd48311ea693001979ee59f621237a6e6f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2019
ms.locfileid: "67558125"
---
# <a name="manage-web-access-by-using-microsoft-edge-with-microsoft-intune"></a>Microsoft Intune Microsoft Edge kullanarak Web erişimini yönetme

Microsoft Edge ile Intune uygulama koruma ilkelerini kullanarak, Kurumsal Web siteleri ile yerinde koruma her zaman erişildiğini olun yardımcı olur. Intune ilkeleri ile etkinleştirilen aşağıdaki Microsoft Edge Kurumsal özellikler mevcuttur:

- **İkili kimlik.** Kullanıcı gözatma için bir kişisel hesap yanı sıra, bir iş hesabı ekleyebilirsiniz. Office 365 ve Outlook mimarilerinde ve deneyimlerinde olduğu gibi iki kimlik arasında belirgin bir ayrım vardır. Intune yöneticileri, iş hesabı içinde korumalı gözatma deneyimi için istenen ilkeleri ayarlayabilir.
- **Intune uygulama koruma İlkesi tümleştirmesi.** Microsoft Edge Intune SDK'sı ile tümleşik olduğundan, veri kaybına karşı koruma için uygulama koruma ilkelerini hedefleyebilirsiniz. Bu yeteneklere denetleme kesme, kopyalama ve yapıştırma, ekran yakalamayı önleme ve yönetilen uygulamalar kullanıcı tarafından seçilen bağlantıları yalnızca diğer açılmasını sağlama.
- **Azure uygulama proxy'si tümleştirmesi.** Yazılım erişimi hizmet (SaaS) uygulamaları olarak denetleyebilir ve web uygulamaları. Bu, son kullanıcıların şirket ağından bağlanın veya internet'ten bağlanmak tarayıcı tabanlı uygulamalar yalnızca güvenli Microsoft Edge tarayıcısında çalıştırdığınızdan emin olun yardımcı olur.
- **Uygulama yapılandırması.** Uygulama yapılandırma ayarlarını, kuruluşunuzun güvenlik duruşunu güçlendirmek ve kullanım kolaylığı özellikleri, son kullanıcılarınız için yapılandırmak için kullanabilirsiniz. Örneğin, yer işaretleri, giriş sayfası kısayol, izin verilen veya engellenen siteler ve Azure Active Directory (Azure AD) uygulama proxy'si tanımlayabilirsiniz.

Microsoft Edge için Microsoft Intune koruma ilkeleri, kuruluşunuzun verilerini ve kaynaklarını korumanıza yardımcı olur. Microsoft Edge ile bu ilkeleri kullanarak şirketinizin kaynaklarına yalnızca yerel olarak yüklü uygulamaların içinde aynı zamanda web tarayıcısı üzerinden erişildiğinde korunmasını sağlar.

## <a name="getting-started"></a>Başlarken

Sizin ve son kullanıcılarınızın Microsoft Edge kullanılmak üzere genel uygulama mağazalarından, kuruluşta indirebilirsiniz. İşletim sistemi gereksinimlerini tarayıcı ilkeleri için aşağıdakilerden birini şunlardır:
- Android 4 ve üzeri
- iOS 8.0 ve üzeri

## <a name="application-protection-policies-for-microsoft-edge"></a>Microsoft Edge için uygulama koruma ilkeleri

Microsoft Edge Intune SDK'sı ile tümleşik olduğundan, bunlara uygulama koruma ilkeleri uygulayabilirsiniz.

Bu ayarları şunlara uygulayabilirsiniz:
- Intune'a kayıtlı cihazlar.
- Başka bir mobil cihaz yönetim ürününe kayıtlı cihazlar.
- Yönetilmeyen cihazlar.

Microsoft Edge Intune İlkesi ile hedeflenmiş değil, kullanıcılar Office uygulamaları gibi diğer Intune tarafından yönetilen uygulamalardan verilere erişmek için kullanamazsınız. 

## <a name="conditional-access-for-microsoft-edge"></a>Microsoft Edge için koşullu erişim

Azure AD koşullu erişim, yalnızca Microsoft Edge üzerinden şirket içeriğine erişmek için kullanıcılarınızın yönlendirmek için kullanabilirsiniz. Bu, ilkeyle korunan Microsoft Edge için Azure AD bağlantılı web uygulamalarında mobil tarayıcı erişimini kısıtlar. Bu blokları herhangi diğer korumasız tarayıcılardan erişim, Safari veya Chrome gibi. Exchange Online ve SharePoint Online, Microsoft 365 Yönetim Merkezi ve hatta yoluyla harici kullanıcılara sunduğunuz şirket içi siteler gibi Azure kaynaklarına koşullu erişim uygulayabilirsiniz [Azure AD uygulama proxy'si](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started).

Microsoft Edge, iOS ve Android kullanmak için Azure AD bağlantılı web uygulamalarına kısıtlamak için:
1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Intune düğümünde seçin **koşullu erişim** > **yeni ilke**.
3. Seçin **Grant** gelen **erişim denetimleri** dikey pencerenin bölümü.
4. **Onaylı istemci uygulaması gerektir**’e tıklayın.
5. Seçin **seçin** üzerinde **Grant** dikey penceresi. Bu ilke, yalnızca Intune Managed Browser uygulaması tarafından erişilebilir olmasını istediğiniz bulut uygulamalarına atanmalıdır.

    ![Ekran görüntüsü, koşullu erişim ilkesi - verin](./media/manage-microsoft-edge/manage-microsoft-edge-01.png)

6. Atamalar bölümünde **koşullar** > **istemci uygulamaları**. **İstemci uygulamaları** dikey penceresi görünür.
7. Altında **yapılandırma**seçin **Evet** belirli istemci uygulamalarında ilkeyi uygulamak için.
8. **Tarayıcı**’nın bir istemci uygulaması olarak seçildiğini doğrulayın.

    ![Ekran görüntüsü, koşullu erişim ilkesi - istemci uygulamalarını seçme](./media/manage-microsoft-edge/manage-microsoft-edge-02.png)

    > [!NOTE]
    > Bu bulut uygulamalarına erişebilecek yerel uygulamaları (tarayıcı olmayan uygulamalar) kısıtlamak için **Mobil uygulamalar ve masaüstü istemciler**’i de seçebilirsiniz.

9. İçinde **atamaları** bölümünden **kullanıcılar ve gruplar**, kullanıcıları veya bu ilkeyi atamak istediğiniz grupları seçin.

    > [!NOTE]
    > Kullanıcıların, Uygulama Yapılandırma ilkelerini alabilmeleri için ayrıca Intune Uygulama Koruması ilkesi ile hedeflenmeleri gerekir. Intune Uygulama Koruma ilkeleri oluşturma hakkında daha fazla bilgi için bkz: [Uygulama koruma ilkeleri nelerdir?](app-protection-policy.md).

10. **Atamalar** bölümünde **Bulut uygulamaları**’nı seçerek bu ilkeyle hangi uygulamaları koruyacağınızı seçin.

Yukarıdaki ilke yapılandırıldıktan sonra kullanıcılar bu ilkeyle koruduğunuz Azure AD bağlantılı web uygulamalarına erişmek için Microsoft Edge kullanmaya zorlanır. Kullanıcılar bu senaryoda, yönetilmeyen bir tarayıcı kullanmaya çalışırsa, Microsoft Edge kullanmalısınız bir ileti alırlar.

> [!TIP]
> Koşullu erişim, bir Azure AD teknolojisidir. Azure AD'den erişilen aynıdır, Intune'dan erişilen koşullu erişim düğümü aynı düğümde kullanır.

## <a name="single-sign-on-to-azure-ad-connected-web-apps-in-policy-protected-browsers"></a>İlkeyle korunan tarayıcılar Azure AD bağlantılı web uygulamalarında Çoklu oturum açma

Microsoft Edge iOS ve Android çoklu oturum açma (SSO), Azure AD bağlantılı tüm web sitelerinde (SaaS ve şirket içi) yararlanabilir. SSO kullanıcıların kimlik bilgilerini yeniden girmeye gerek kalmadan Microsoft Edge üzerinden Azure AD bağlantılı web uygulamalarına erişmesini sağlar.

SSO, cihazınızın iOS cihazları için Microsoft Authenticator uygulaması veya android'de Intune Şirket portalı tarafından kaydedilecek gerektirir. Kullanıcılar bu olduğunda, bir Azure AD bağlantılı web uygulaması ilkeyle korunan bir tarayıcıda karar verdiğinizde, cihazlarını kaydetmek için istenir. (Bu yalnızca, cihaz zaten kayıtlı edilmemiş geçerlidir.) Cihaz Intune tarafından yönetilen kullanıcı hesabı ile kaydedildikten sonra bu hesabı Azure AD bağlantılı web uygulamaları için SSO etkin sahiptir.

> [!NOTE]
> Cihaz kaydı, Azure AD hizmeti ile basit bir iade etme işlemidir. Tam cihaz kaydı gerektirmez ve getirmezse BT cihazdaki herhangi bir ek ayrıcalık.

## <a name="create-a-protected-browser-app-configuration"></a>Korumalı tarayıcı uygulama yapılandırması oluşturma

Uygulama yapılandırmalarının uygulanması için tarayıcı kullanıcı korumalı veya cihazın başka bir uygulama tarafından zaten yönetilmelidir [Intune uygulama koruma İlkesi](app-protection-policy.md).

Korumalı browser uygulama yapılandırması oluşturmak için:

1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Seçin **istemci uygulamaları** > **uygulama yapılandırma ilkeleri** > **Ekle**.
3. **Yapılandırma ilkesi ekle** dikey penceresinde, uygulama yapılandırma ayarları için bir **Ad** ve isteğe bağlı bir **Açıklama** girin.
4. **Cihaz kayıt** türü için **Yönetilen uygulamalar**’ı seçin.
5. Seçin **gerekli uygulamayı seçin**. Ardından **hedeflenen uygulamalar** dikey penceresinde, seçin **Managed Browser** veya **Edge** iOS, Android veya her ikisi için de.
6. Seçin **Tamam** dönmek için **yapılandırma İlkesi Ekle** dikey penceresi.
7. **Yapılandırma ayarlarını** seçin. Üzerinde **yapılandırma** dikey penceresinde, Microsoft Edge için yapılandırmaları sağlamak için anahtar ve değer çiftlerini tanımlayın. Tanımlayabileceğiniz farklı anahtar ve değer çiftleri hakkında bilgi edinmek için bu makalenin ilerleyen bölümlerine göz atın.

    > [!NOTE]
    > Microsoft Edge, Managed Browser ile aynı anahtar ve değer çiftini kullanır. 

8. İşiniz bittiğinde **Tamam**.
9. **Yapılandırma ilkesi ekle** dikey penceresinde, **Ekle**’yi seçin.<br>
    Yeni yapılandırma oluşturulur ve görüntülenen **uygulama yapılandırması** dikey penceresi.

## <a name="assign-the-configuration-settings-you-created"></a>Oluşturduğunuz yapılandırma ayarlarını atama 

Azure AD'de ayarları kullanıcı gruplarına atayabilirsiniz. Bu kullanıcı hedeflenen korumalı tarayıcı uygulamasını yüklemişse uygulama belirttiğiniz ayarlarla yönetiliyordur.

1. Üzerinde **istemci uygulamaları** dikey penceresi Intune mobil uygulama yönetimi panosunun, select **uygulama yapılandırma ilkeleri**.
2. Uygulama yapılandırmaları listesinden atamak istediğiniz birini seçin.
3. Sonraki dikey pencerede seçin **atamaları**.
4. Üzerinde **atamaları** dikey penceresinde, Azure AD grubunu uygulama yapılandırmasını atamak ve ardından istediğiniz **Tamam**.

## <a name="configure-application-proxy-settings-for-protected-browsers"></a>Korumalı tarayıcılar için uygulama Proxy ayarlarını yapılandırma

Microsoft Edge kullanabilirsiniz ve [Azure AD uygulama proxy'si](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) birlikte kullanıcıların mobil cihazlarından intranet sitelerine erişmesini sağlamak için. 

Azure AD uygulama ara sunucusunu etkinleştirme senaryoları bazı örnekleri şunlardır: 

- Bir kullanıcı Intune tarafından korunan Outlook mobil uygulamasının kullanıyor. Ardından, bir e-posta bir intranet siteye bir bağlantı ve Microsoft Edge bu intranet sitenin kullanıcıya uygulama proxy'si aracılığıyla sunulduğunu algılar. Kullanıcı, intranet siteye ulaşmadan önce herhangi bir uygun çok faktörlü kimlik doğrulaması ve koşullu erişim, kimlik doğrulama için uygulama proxy'si aracılığıyla otomatik olarak yönlendirilir. Kullanıcı, hatta mobil cihazlarında, iç sitelere erişmeye bulabildiği ve Outlook'taki bağlantı beklendiği gibi çalışır.
- Bir kullanıcı, iOS veya Android cihazına Microsoft Edge açılır. Intune ile korunan Microsoft Edge ve uygulama ara sunucusu etkin kullanıcı için kullanılan dahili URL'yi kullanarak bir intranet sitesine gidebilirsiniz. Microsoft Edge, bu intranet sitenin kullanıcıya uygulama proxy'si aracılığıyla sunulduğunu algılar. Kullanıcı, intranet siteye ulaşmadan önce kimlik doğrulaması yapmak için uygulama proxy'si aracılığıyla otomatik olarak yönlendirilir. 

### <a name="before-you-start"></a>Başlamadan önce

- Dahili uygulamalarınızın Azure AD uygulama proxy'si aracılığıyla ayarlayın.
    - Uygulama Proxy’sini yapılandırmak ve uygulama yayımlamak için bkz. [kurulum belgeleri](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).
- Microsoft Edge uygulamasına sahip olmanız gerekir [Intune uygulama koruma İlkesi](app-protection-policy.md) atanmış.

> [!NOTE]
> Güncelleştirilmiş Uygulama Ara Sunucusu’nun yeniden yönlendirme verilerinin Managed Browser’da veya Microsoft Edge'de etkinleşmesi 24 saati bulabilir.

#### <a name="step-1-enable-automatic-redirection-to-a-protected-browser-from-outlook"></a>1\. adım: Outlook'tan korumalı tarayıcıya otomatik yeniden yönlendirmeyi etkinleştirme
Outlook ayarına imkan veren bir uygulama koruma İlkesi ile yapılandırma **yönetilen tarayıcı ilkesiyle içerik paylaşımı web**.

![Ekran görüntüsü, uygulama koruma İlkesi - paylaşım web içeriği ilke ile yönetilen tarayıcılar](./media/manage-microsoft-edge/manage-microsoft-edge-03.png)

#### <a name="step-2-set-the-app-configuration-setting-to-enable-app-proxy"></a>2\. adım: Uygulama proxy'sini etkinleştirmek için uygulama yapılandırma ayarını belirle
Microsoft Edge, Microsoft Edge için uygulama proxy'sini etkinleştirmek için aşağıdaki anahtar/değer çifti ile hedef:

|    Anahtar    |    Value    |
|-------------------------------------------------------------------|-------------|
|    com.microsoft.intune.mam.managedbrowser.AppProxyRedirection    |    true    |

Microsoft Edge ve Azure AD uygulama ara Sunucusu'nun şirket içi web uygulamalarına sorunsuz (ve korumalı) erişim için kullanma hakkında daha fazla bilgi için bkz. [birlikte daha güçlü: Kullanıcı erişimini iyileştirmek için Intune ve Azure Active Directory ekip çalışması yapıyor](https://cloudblogs.microsoft.com/enterprisemobility/2017/07/06/better-together-intune-and-azure-active-directory-team-up-to-improve-user-access)’a bakın. Bu blog gönderisini başvuruları Intune Managed Browser, ancak içerik Microsoft Edge için de geçerlidir.

## <a name="configure-a-homepage-shortcut-for-microsoft-edge"></a>Microsoft Edge için giriş sayfası kısayol yapılandırın

Bu ayar, Microsoft Edge için giriş sayfası kısayol yapılandırmanıza olanak sağlar. Kullanıcının Microsoft Edge'de yeni bir sekmede açtığında yapılandırdığınız giriş sayfası kısayolu altındaki Arama çubuğuna ilk simge olarak görünür. Kullanıcı düzenleyemez veya bu kısayol, yönetilen bir bağlamda silemezsiniz. Giriş sayfası kısayol bunu ayırt etmek için kuruluşunuzun adını görüntüler. 

Giriş sayfası kısayol yapılandırmak için aşağıdaki anahtar/değer çifti kullanın:

|    Anahtar    |    Değer    |
|-------------------------------------------------------------------|-------------|
|    com.microsoft.intune.mam.managedbrowser.homepage   |    Geçerli bir URL belirtin. Hatalı URL’ler güvenlik önlemi olarak engellenir.<br>**Örnek:**  <`https://www.bing.com`>
    |

## <a name="configure-managed-bookmarks-for-microsoft-edge"></a>Microsoft Edge için yönetilen yer işaretleri yapılandırma

Erişim Kolaylığı için Microsoft Edge kullanırken, kullanıcılarınızın kullanılabilir istediğinizi yer işaretleri yapılandırabilirsiniz. 

Aşağıda, bazı ayrıntılar verilmiştir:

- Microsoft Edge Kurumsal modu kullanırken bu yer işaretleri, yalnızca kullanıcılar için görünür. 
- Bu yer işaretleri silinemez veya kullanıcılar tarafından değiştirilmiş.
- Bu yer işaretleri listenin üstünde görünür. Kullanıcılar oluşturma işaretlerini bu yer işaretleri altında görünür.
- Uygulama proxy'si yeniden yönlendirmesini etkinleştirdiyseniz, uygulama proxy'si web uygulamaları, dahili veya harici URL'den kullanarak ekleyebilirsiniz.

Yönetilen yer işaretlerini yapılandırmak için aşağıdaki anahtar/değer çifti kullanın:

|    Anahtar    |    Value    |
|---------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    com.microsoft.intune.mam.managedbrowser.Bookmarks    |    Bu yapılandırmanın değeri, yer işaretleri listesidir. Her bir yer işareti, yer işareti başlık ve yer işareti URL'si oluşur. Başlık ve URL ile ayrı `|` karakter.      Örnek:<br>`Microsoft Bing|https://www.bing.com`<br>Birden fazla yer işaretlerini yapılandırmak için her bir çifti çift karakteriyle ayırın `||`.<p>Örnek:<br>`Microsoft Bing|https://www.bing.com||Contoso|https://www.contoso.com`    |

## <a name="display-myapps-within-microsoft-edge-bookmarks"></a>MyApps içinde Microsoft Edge yer imlerini görüntüle

Varsayılan olarak, kullanıcılarınız için Microsoft Edge yer işaretleri içinde bir klasördeki yapılandırılmış olan MyApps siteleri gösterilmektedir. Klasör kuruluşunuzun adını taşır.

|    Anahtar    |    Value    |
|------------------------------------------------------|----------------------------------------------------------------------------------------------------------------|
|    com.microsoft.intune.mam.managedbrowser.MyApps    |    **Doğru** MyApps içinde Microsoft Edge işaretlerini gösterir.<p>**False** Microsoft Edge içinde MyApps gizler.    |

## <a name="specify-allowed-or-blocked-sites-list-for-microsoft-edge"></a>Microsoft Edge için izin verilen veya engellenen siteler listesini belirtin
Uygulama yapılandırması, kullanıcılarınız kendi iş profili kullanırken erişebilir hangi siteleri tanımlamak için kullanabilirsiniz. Bir izin verilenler listesi kullanırsanız, kullanıcılarınız yalnızca açıkça listelenen sitelerine erişebildiğinden. Engellenen listesi kullanırsanız, açıkça engellediğiniz olanlar dışındaki tüm sitelerin kullanıcılarınız erişebilir. Yalnızca izin verilen veya engellenen listesi, ikisini dayatır. Her ikisi de koymak, izin verilenler uygulanır.  

Aşağıdaki anahtar/değer çiftleri herhangi birini yapılandırmak için Microsoft Edge için bir izin verilen veya engellenen site listesi kullanın. 

|    Anahtar    |    Değer    |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Aşağıdakilerden birini seçin:<p>1. İzin verilen URL’leri belirtme (yalnızca bu URL'lere izin verilir, diğer sitelere erişilemez):<br>`com.microsoft.intune.mam.managedbrowser.AllowListURLs`<p>2. Engellenen URL’leri belirtme (tüm diğer sitelere erişilebilir):<br>`com.microsoft.intune.mam.managedbrowser.BlockListURLs`    |    Bir anahtara karşılık gelen değer bir URL listesidir. İzin vermek veya kanalla ayrılan tek bir değer olarak engellemek istediğiniz URL'leri girin `|` karakter.<br>**Örnekler:**<br>`URL1|URL2|URL3`<br>`http://.contoso.com/|https://.bing.com/|https://expenses.contoso.com`  |

### <a name="url-formats-for-allowed-and-blocked-site-list"></a>URL biçimleri için izin verilen ve engellenen site listesi 
Çeşitli URL biçimleri, izin verilen/engellenen siteler listeleri oluşturmak için kullanabilirsiniz. Bu izin verilen desenler aşağıdaki tabloda açıklanmıştır. Başlamadan önce bazı notlar: 
- Tüm URL'leri listeye eklerken başlarına **http** veya **https** önekini yazdığınızdan emin olun.
- Joker karakter sembolünü kullanabilirsiniz (\*) aşağıdaki izin verilen örnekler listesindeki kurallara göre.
- Joker karakter yalnızca bir ana bilgisayar (noktalarla ayrılmış) veya tüm parçalarını (eğik ayrılmış olarak) yol tüm bileşeninin eşleşebilir. Örneğin, `http://*contoso.com` olduğu **değil** desteklenir.
- Adreste bağlantı noktası numaraları belirtebilirsiniz. Bir bağlantı noktası numarası belirtmezseniz, kullanılan değerler şöyle olacaktır:
    - http için bağlantı noktası 80
    - https için bağlantı noktası 443
- Bağlantı noktası numarası için joker karakter kullanılması **değil** desteklenir. Örneğin `http://www.contoso.com:*` ve `http://www.contoso.com:*/` desteklenmez. 

    |    URL    |    Ayrıntılar    |    Eşleşir    |    Eşleşmez    |
    |-------------------------------------------|--------------------------------------------------------|-------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
    |    `http://www.contoso.com`    |    Tek bir sayfayla eşleşir    |    `www.contoso.com`    |    `host.contoso.com`<br>`www.contoso.com/images`<br>`contoso.com/`    |
    |    `http://contoso.com`    |    Tek bir sayfayla eşleşir    |    `contoso.com/`    |    `host.contoso.com`<br>`www.contoso.com/images`<br>`www.contoso.com`    |
    |    `http://www.contoso.com/&#42;`   |    `www.contoso.com` ile başlayan tüm URL’lerle eşleşir    |    `www.contoso.com`<br>`www.contoso.com/images`<br>`www.contoso.com/videos/tvshows`    |    `host.contoso.com`<br>`host.contoso.com/images`    |
    |    `http://*.contoso.com/*`    |    Altındaki tüm alt etki alanlarıyla eşleşir `contoso.com`    |    `developer.contoso.com/resources`<br>`news.contoso.com/images`<br>`news.contoso.com/videos`    |    `contoso.host.com`    |
    |    `http://www.contoso.com/images`    |    Tek bir klasörle eşleşir    |    `www.contoso.com/images`    |    `www.contoso.com/images/dogs`    |
    |    `http://www.contoso.com:80`    |    Bir bağlantı noktası numarası kullanarak tek bir sayfayla eşleşir    |    `http://www.contoso.com:80`    |         |
    |    `https://www.contoso.com`    |    Güvenli tek bir sayfayla eşleşir    |    `https://www.contoso.com`    |    `http://www.contoso.com`    |
    |    `http://www.contoso.com/images/*`    |    Tek bir klasör ve tüm alt klasörleriyle eşleşir    |    `www.contoso.com/images/dogs`<br>`www.contoso.com/images/cats`    |    `www.contoso.com/videos`    |
  
- Belirtemezsiniz girişleri bazı örnekleri aşağıda verilmiştir:
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
  
## <a name="define-behavior-when-users-try-to-access-a-blocked-site"></a>Engellenen bir siteye erişmek kullanıcılara çalıştığınızda davranışını tanımlayın

Microsoft Edge ile oluşturulan çift kimlik modeliyle, son kullanıcıların Intune Managed Browser ile mümkün olandan daha esnek bir deneyim etkinleştirebilirsiniz. Kullanıcıların Microsoft edge'de engellenen bir site ulaştığınızda, kendi iş bağlamında yerine kendi kişisel bağlamda bağlantıyı açmak için isteyebilir. Bu, bunları şirket kaynaklarına güvenli korurken korumalı olarak kalmasını sağlar. Bir kullanıcı bir haber makalesine Outlook ile bir bağlantı gönderilir, örneğin, bunlar bağlantıyı kendi kişisel bağlamda veya bir InPrivate sekmesinden açabilirsiniz. Kendi iş bağlamında haber Web sitelerine izin vermez. Varsayılan olarak, bu geçiş izin verilir.

Bu geçici bir geçiş izin verip yapılandırmak için aşağıdaki anahtar/değer çifti kullanın:

|    Anahtar    |    Value    |
|----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.mam.managedbrowser.AllowTransitionOnBlock`    |    **Doğru** Microsoft Edge engellenen siteler açmak için geçiş, kullanıcıların kendi kişisel bağlam sağlar.<p>**Blok** Microsoft Edge, kullanıcıların geçiş öğesinden engeller. Kullanıcılar yalnızca erişmeye çalıştığınız sitenin engellendiğini bildiren bir ileti görüntülenir.    |

## <a name="direct-users-to-microsoft-edge-instead-of-the-intune-managed-browser"></a>Microsoft Edge yerine Intune Managed Browser kullanıcıları 

Intune Managed Browser ve Microsoft Edge tarayıcı İlkesi korumalı olarak kullanılabilir. Kullanıcılarınızın doğru tarayıcı uygulamasını kullanmak için yönlendirilmesi emin olmak için tüm, Intune tarafından yönetilen uygulamaların (örneğin, Outlook, OneDrive ve SharePoint) ile şu yapılandırma ayarı hedef:

|    Anahtar    |    Değer    |
|------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.useEdge`    |    Değer `true` indirin ve Microsoft Edge kullanıcılarınıza yönlendirir.<br>Değer `false` kullanıcılarınızın Intune Managed Browser kullanmasını sağlar.    |

Bu uygulama yapılandırma değeri ise **değil** ayarlayın, aşağıdaki mantık tarayıcıyı Kurumsal bağlantılarını açmak için kullanılacak tanımlayacaksınız.

Android’de:
- Intune Managed Browser ve Microsoft Edge cihazlarına indirilen bir kullanıcı varsa, Intune Managed Browser başlatır. 
- Microsoft Edge, yalnızca Microsoft Edge cihaza yüklenir ve Intune ilkesiyle hedeflenen başlatır.
- Yönetilen tarayıcının yalnızca Managed Browser olan cihazda ve Intune ilkesiyle hedeflenen başlatır.

Intune SDK’sını iOS v için tümleştiren uygulamalarda iOS’ta. 9.0.9+:
- Cihazda Managed Browser ve Microsoft Edge kullanıyorsanız, Intune Managed Browser başlatır.  
- Microsoft Edge, yalnızca Microsoft Edge olan cihazda ve Intune ilkesiyle hedeflenen başlatır.
- Yönetilen tarayıcının yalnızca Managed Browser olan cihazda ve Intune ilkesiyle hedeflenen başlatır.

## <a name="use-microsoft-edge-on-ios-to-access-managed-app-logs"></a>Microsoft Edge İos'ta yönetilen uygulama günlüklerine erişmek için kullanın. 

Microsoft Edge iOS cihazlarında yüklü olan kullanıcılar, tüm yönetim durumunu görüntüleyebilir Microsoft yayımlanan uygulamalar. Yönetilen iOS uygulamalarında sorun gidermek için günlükleri gönderebilirler. Şöyle yapılır:
1. Microsoft Edge, iOS Cihazınızda açın.
2. Adres kutusuna `about:intunehelp` yazın. 
3. Microsoft Edge, sorun giderme modunda açılacaktır.

Uygulama günlüklerinde saklanan ayarların bir listesi için, bkz. [Yönetilen Tarayıcı’da uygulama koruma günlüklerini inceleyin](app-protection-policy-settings-log.md).

Android cihazlarda günlüklerini görüntüleme için bkz [günlükleri BT yöneticinize gönderme e-posta ile](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android). 

## <a name="security-and-privacy-for-microsoft-edge"></a>Microsoft Edge için güvenlik ve gizlilik

Microsoft Edge için ek güvenlik ve gizlilik konuları şunlardır:

- Microsoft Edge, bu ayarları erişemediği için Microsoft Edge kullanıcılar, cihazlarında yerel tarayıcılarında bu işlem için ayarlanan ayarları kullanmaz.
- Seçeneğini yapılandırabilirsiniz **erişim için basit PIN gerektir** veya **erişim için Kurumsal kimlik bilgilerini gerektir** Microsoft Edge ile ilişkili bir uygulama koruma İlkesi içinde. Kullanıcı kimlik doğrulama sayfasındaki Yardım bağlantısını seçerse olup ilkesinde bir engelleme listesine eklenmiş olmasından bağımsız olarak herhangi internet sitesine göz atabilirsiniz.
- Yalnızca bunlar doğrudan erişildiğinde Microsoft Edge sitelere erişimi engelleyebilir. Kullanıcılar siteye erişmek için Ara hizmetler (örneğin, bir çeviri hizmeti) kullandığınızda, erişimi engellemez.
- Kimlik doğrulamasına izin ver ve Intune belgelerine erişim * **. microsoft.com** izin verilenler veya Engellenenler listesi ayarlarının dışında tutulur. Her zaman izin verilir.
- Kullanıcılar, veri toplamayı kapatabilirsiniz. Microsoft, ürün ve hizmetlerini geliştirmek için Managed Browser’ın performansı ve kullanımı hakkında otomatik olarak anonim bilgiler toplar. Kullanıcılar cihazlarındaki **Kullanım Verileri** ayarını kullanarak veri toplamayı kapatabilir. Bu verilerin toplanması üzerinde denetiminiz yoktur. İOS cihazlarında ettiği süresi dolmuş veya güvenilmeyen sertifikalara sahip, kullanıcıların ziyaret ettiği Web siteleri açılmaz.

## <a name="next-steps"></a>Sonraki adımlar

- [Uygulama koruma ilkeleri nedir?](app-protection-policy.md) 
