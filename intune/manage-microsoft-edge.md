---
title: Microsoft Edge Intune kullanarak web erişimini yönetme
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
ms.openlocfilehash: c9a225fbffda25b8d077c3b2be271e86d3e6c85e
ms.sourcegitcommit: 2db7dc2baea0c159f70338e6a0529acc89580773
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2019
ms.locfileid: "67500600"
---
# <a name="manage-web-access-using-microsoft-edge-with-microsoft-intune"></a>Microsoft Edge Intune kullanarak web erişimini yönetme

Microsoft Edge ile Intune uygulama koruma ilkelerini kullanarak, Kurumsal Web siteleri ile yerinde koruma her zaman erişildiğini emin olabilirsiniz. Intune ilkeleriyle etkinleştirilen aşağıdaki Microsoft Edge kurumsal özelliklerini kullanabilirsiniz. Kurumsal özellikler şunlardır:

1.  **Çift kimlik**: Kullanıcılar hem iş hesabı hem de kişisel hesap ekleyerek göz atabilir. Office 365 ve Outlook mimarilerinde ve deneyimlerinde olduğu gibi iki kimlik arasında belirgin bir ayrım vardır. Intune yöneticileri, iş hesabını kullanarak korumalı bir göz atma deneyimi sağlamak üzere istenen ilkeleri belirleyebilir.
2.  **Intune uygulama koruma İlkesi tümleştirmesi** – beri Microsoft Edge, Intune SDK'sı ile tümleşiktir, veri kaybı korumasını sağlamak için uygulama koruma ilkelerini hedefleyebilirsiniz. Kes, Kopyala, denetim bu yeteneklere Yapıştır, Ekran yakalamalarını engelleme yakalar ve yönetilen uygulamalar kullanıcı tarafından seçilen bağlantıları yalnızca diğer açılmasını sağlama.
3.  **Azure uygulama proxy'si tümleştirmesi** - SaaS uygulamalarına erişimi denetleyebilir ve web uygulamaları, tarayıcı tabanlı uygulamalar yalnızca sağlanmasına yardımcı olur, son kullanıcıların şirket ağından bağlanın veya Internet'ten bağlanmak güvenli Microsoft Edge tarayıcısında çalıştırma .
4.  **Uygulama Yapılandırması** – kuruluşlar güvenlik duruşunuzu güçlendirin ve kullanım kolaylığı özellikleri, son kullanıcılarınız için yapılandırmak için uygulama yapılandırma ayarlarını yararlanabilirsiniz. Örneğin, yer işaretleri, giriş sayfası kısayol, izin verilen/engellenen siteler, Azure uygulama proxy'si ve daha fazla tanımlayabilirsiniz.
Microsoft Edge için Microsoft Intune koruma ilkeleri, kuruluşunuzun verilerini ve kaynaklarını korumanıza yardımcı olur. Microsoft Edge ile bu ilkeleri kullanarak şirketinizin kaynaklarına yalnızca yerel olarak yüklü uygulamaların içinde aynı zamanda web tarayıcısı üzerinden erişildiğinde korunmasını sağlar.

## <a name="getting-started"></a>Başlarken

Sizin ve son kullanıcılarınızın Microsoft Edge kullanılmak üzere genel uygulama mağazalarından, kuruluşta indirebilirsiniz. Tarayıcı ilkeleri için işletim sistemi gereksinimleri:
- Android 4 ve üzeri veya
- iOS 8.0 ve üzeri

## <a name="application-protection-policies-for-microsoft-edge"></a>Microsoft Edge için uygulama koruma ilkeleri

Microsoft Edge Intune SDK'sı ile tümleşik olduğundan, bunları da dahil olmak üzere uygulama koruma ilkelerini uygulayabilirsiniz:
- Kesme, kopyalama ve yapıştırma işlemlerini denetleme.
- Ekran yakalamayı önleme.
- Şirket bağlantılarının yalnızca yönetilen uygulama ve tarayıcılarda açılmasını sağlama.

Ayrıntılar için bkz: uygulama koruma ilkeleri nelerdir?
Bu ayarları şunlara uygulayabilirsiniz:
- Intune’a kayıtlı cihazlar
- Başka bir MDM ürününe kayıtlı cihazlar
- Yönetilmeyen cihazlar

Microsoft Edge Intune İlkesi ile hedeflenmiş değil, kullanıcılar Office uygulamaları gibi Intune tarafından yönetilen diğer uygulamalardan verilere erişmek için kullanamazsınız. 

## <a name="conditional-access-for-microsoft-edge"></a>Microsoft Edge için koşullu erişim

Yalnızca Microsoft Edge üzerinden şirket içeriğine erişmek için kullanıcılarınızın yönlendirmek için Azure AD koşullu erişim yararlanabilirsiniz. Bu ilkeyle korunan Microsoft Edge için Azure AD bağlantılı web uygulamalarında mobil tarayıcı erişimini kısıtlar ve bu Safari veya Chrome gibi korumasız diğer tarayıcılardan erişim engellenebilir. Koşullu erişim, Exchange Online ve SharePoint Online, Microsoft 365 Yönetim Merkezi ve hatta yoluyla harici kullanıcılara sunduğunuz şirket içi siteler gibi Azure kaynaklarına uygulanabilir [Azure AD uygulama proxy'si](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started).

Microsoft Edge, iOS ve Android kullanmak için Azure AD bağlantılı web uygulamalarına kısıtlamak için izleyin aşağıdaki adımları:
1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Intune düğümünde seçin **koşullu erişim** > **yeni ilke**.
3. Daha sonra, dikey pencerenin **Erişim denetimleri** bölümünden **İzin Ver**’i seçin.
4. **Onaylı istemci uygulaması gerektir**’e tıklayın.
5. **İzin Ver** dikey penceresinde **Seçin**’e tıklayın. Bu ilke, yalnızca Intune Managed Browser uygulaması tarafından erişilebilir olmasını istediğiniz bulut uygulamalarına atanmalıdır.

    ![Koşullu erişim ilkesi - verin](./media/manage-microsoft-edge/manage-microsoft-edge-01.png)

6. Atamalar bölümünde koşulları seçin > istemci uygulamaları. İstemci uygulamalar dikey penceresinde görüntülenir.
7. Yapılandırma belirli istemci uygulamalarında ilkeyi uygulamak için Evet'e tıklayın.
8. Tarayıcı istemci uygulaması olarak seçildiğini doğrulayın.

    ![Koşullu Erişim İlkesi - istemci uygulamalarını seçme](./media/manage-microsoft-edge/manage-microsoft-edge-02.png)

    > [!NOTE]
    > Bu bulut uygulamalarına erişebilecek yerel uygulamaları (tarayıcı olmayan uygulamalar) kısıtlamak için **Mobil uygulamalar ve masaüstü istemciler**’i de seçebilirsiniz.

9. **Atamalar** bölümünde **Kullanıcılar ve gruplar**’ı seçin ve ardından bu ilkeyi atayacağınız kullanıcı veya grupları seçin.

    > [!NOTE]
    > Kullanıcıların, Uygulama Yapılandırma ilkelerini alabilmeleri için ayrıca Intune Uygulama Koruması ilkesi ile hedeflenmeleri gerekir. Intune Uygulama Koruma ilkeleri oluşturma hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkeleri nelerdir?](app-protection-policy.md)

10. **Atamalar** bölümünde **Bulut uygulamaları**’nı seçerek bu ilkeyle hangi uygulamaları koruyacağınızı seçin.

Yukarıdaki ilke yapılandırıldıktan sonra kullanıcılar, Bu ilkeyle koruduğunuz Azure AD bağlantılı web uygulamalarına erişmek için Microsoft Edge kullanmaya zorlanır. Kullanıcılar bu senaryoda, yönetilmeyen bir tarayıcı kullanmaya çalışırsa, Microsoft Edge kullanmalısınız bir ileti görürler.

> [!TIP]
> Koşullu Erişim, bir Azure Active Directory (Azure AD) teknolojisidir. Azure AD'den erişilen aynıdır, Intune'dan erişilen koşullu erişim düğümü aynı düğümde kullanır.

## <a name="single-sign-on-to-azure-ad-connected-web-apps-in-policy-protected-browsers"></a>İlkeyle korunan tarayıcılarda Azure AD'ye bağlanmış Web uygulamalarında Çoklu Oturum Açma

Microsoft Edge iOS ve Android'de SSO, Azure AD bağlantılı tüm web sitelerinde (SaaS ve şirket içi) yararlanabilir. SSO kullanıcıların kimlik bilgilerini yeniden girmeye gerek kalmadan Microsoft Edge üzerinden Azure AD bağlantılı web uygulamalarına erişmesini sağlar.

SSO, cihazınızın iOS cihazları için Microsoft Authenticator uygulaması veya android'de Intune Şirket portalı tarafından kaydedilecek gerektirir. Kullanıcılar kimlik doğrulayıcı uygulaması ya da Intune Şirket portalı varsa, bir Azure AD bağlantılı web uygulamasına bir ilkeyle korunan tarayıcıda gittiğinizde cihazını zaten henüz kayıtlı değil, cihazlarını kaydetmek için istenir. Cihaz Intune tarafından yönetilen kullanıcı hesabı ile kaydedildikten sonra bu hesabı Azure AD bağlantılı web uygulamaları için SSO etkin olacaktır.

> [!NOTE]
> Cihaz kaydı, Azure AD hizmeti ile basit bir iade etme işlemidir. Tam cihaz kaydı gerektirmez ve BT ekibine cihaz üzerinde herhangi bir ek ayrıcalık sağlamaz.

## <a name="create-a-protected-browser-app-configuration"></a>Korumalı tarayıcı uygulama yapılandırması oluşturma

Uygulama yapılandırmalarının uygulanması için tarayıcı kullanıcı korumalı veya cihazın başka bir uygulama tarafından zaten yönetilmelidir [Intune uygulama koruma İlkesi](app-protection-policy.md).

Aşağıdaki adımlar, bir korumalı browser uygulama yapılandırması oluşturmak için kullanılır:

1. Oturum [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Seçin **istemci uygulamaları** > **uygulama yapılandırma ilkeleri** > **Ekle**.
3. **Yapılandırma ilkesi ekle** dikey penceresinde, uygulama yapılandırma ayarları için bir **Ad** ve isteğe bağlı bir **Açıklama** girin.
4. **Cihaz kayıt** türü için **Yönetilen uygulamalar**’ı seçin.
5. **Gerekli uygulamayı seçin** öğesini belirleyin ve ardından **Hedeflenen uygulamalar** dikey penceresinde iOS, Android veya her ikisi için **Managed Browser**’ı ve/veya **Edge**'i seçin.
6. **Tamam**’ı seçerek **Yapılandırma ilkesi ekle** dikey penceresine dönün.
7. **Yapılandırma ayarları**’nı seçin. Üzerinde **yapılandırma** dikey penceresinde, Microsoft Edge için yapılandırmaları sağlamak için anahtar ve değer çiftlerini tanımlayın. Tanımlayabileceğiniz farklı anahtar ve değer çiftleri hakkında bilgi edinmek için bu makalenin ilerleyen bölümlerine göz atın.

    > [!NOTE]
    > Microsoft Edge, Managed Browser ile aynı anahtar ve değer çiftini kullanır. 

8.  Bitirdiğinizde, **Tamam**’a tıklayın.
9.  **Yapılandırma ilkesi ekle** dikey penceresinde, **Ekle**’yi seçin.<br>
    Yeni yapılandırma oluşturulur ve görüntülenen **uygulama yapılandırması** dikey penceresi.

## <a name="assign-the-configuration-settings-you-created"></a>Oluşturduğunuz yapılandırma ayarlarını atama 

Ayarları Azure AD kullanıcı gruplarına atayın. Bu kullanıcı hedeflenen korumalı tarayıcı uygulamasını yüklemişse uygulama belirttiğiniz ayarlarla yönetiliyordur.

1. Intune mobil uygulama yönetimi panosunun **İstemci uygulamaları** dikey penceresinde, **Yapılandırma ilkeleri ekle**’yi seçin.
2. Uygulama yapılandırmaları listesinden atamak istediğiniz birini seçin.
3. Sonraki dikey pencerede **Atamalar**’ı seçin.
4. **Atamalar** dikey penceresinde, uygulama yapılandırmasını atamak istediğiniz Azure AD grubunu ve ardından **Tamam**’ı seçin.

## <a name="how-to-configure-application-proxy-settings-for-protected-browsers"></a>Korumalı tarayıcılar için Uygulama Ara Sunucusu ayarlarını yapılandırma

Microsoft Edge ve [Azure AD uygulama proxy'si](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) kullanıcıların mobil cihazlarından intranet sitelerine erişmesini sağlamak için birlikte kullanılabilir. 

AD uygulama ara sunucusunu etkinleştirme senaryoları bazı örnekleri şunlardır: 

- Bir kullanıcı Intune tarafından korunan Outlook mobil uygulamasının kullanıyor. Ardından, bir e-posta bir intranet siteye bir bağlantı ve Microsoft Edge bu intranet sitenin kullanıcıya uygulama proxy'si aracılığıyla sunulduğunu algılar. Kullanıcı, intranet siteye ulaşmadan önce herhangi bir uygun çok faktörlü kimlik doğrulaması ve koşullu erişimde kimlik doğrulaması yapmak için uygulama proxy'si aracılığıyla otomatik olarak yönlendirilir. Kullanıcılar, hatta mobil cihazlarında dahili sitelerine erişebildiğinden ve Outlook'taki bağlantı beklendiği gibi çalışır.
- Bir kullanıcı, iOS veya Android cihazına Microsoft Edge açılır. Intune ile korunan Microsoft Edge ve uygulama ara sunucusu etkin kullanıcı için kullanılan dahili URL'yi kullanarak bir intranet sitesine gidebilirsiniz. Microsoft Edge, bu intranet sitenin kullanıcıya uygulama proxy'si aracılığıyla sunulan ve kullanıcı intranet siteye ulaşmadan önce kimlik doğrulaması yapmak için uygulama proxy'si aracılığıyla otomatik olarak yönlendirilir tanır. 

### <a name="before-you-start"></a>Başlamadan önce

- Dahili uygulamalarınızı Azure AD Uygulama Proxy’si aracılığıyla ayarlayın.
    - Uygulama Proxy’sini yapılandırmak ve uygulama yayımlamak için bkz. [kurulum belgeleri](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).
- Microsoft Edge uygulama olmalıdır [Intune uygulama koruma İlkesi](app-protection-policy.md) atanmış.

> [!NOTE]
> Güncelleştirilmiş Uygulama Ara Sunucusu’nun yeniden yönlendirme verilerinin Managed Browser’da veya Microsoft Edge'de etkinleşmesi 24 saati bulabilir.

#### <a name="step-1-enable-automatic-redirection-to-a-protected-browser-from-outlook"></a>1\. adım: Outlook'tan korumalı tarayıcıya otomatik yeniden yönlendirmeyi etkinleştirme
Outlook ayarına imkan veren bir uygulama koruma İlkesi ile yapılandırılması gerekir **yönetilen tarayıcı ilkesiyle içerik paylaşımı web**.

![Uygulama koruma İlkesi - paylaşım web içeriği ilke ile yönetilen tarayıcılar](./media/manage-microsoft-edge/manage-microsoft-edge-03.png)

#### <a name="step-2-set-the-app-configuration-setting-to-enable-app-proxy"></a>2\. adım: Uygulama proxy'sini etkinleştirmek için uygulama yapılandırma ayarını belirle
Microsoft Edge ile hedef Microsoft Edge için uygulama proxy'sini etkinleştirmek için anahtar/değer çifti aşağıda:

|    Anahtar    |    Value    |
|-------------------------------------------------------------------|-------------|
|    com.microsoft.intune.mam.managedbrowser.AppProxyRedirection    |    true    |

Nasıl Microsoft Edge ve Azure AD uygulama ara Sunucusu'nun şirket içi web uygulamalarına sorunsuz (ve korumalı) erişim için kullanılabileceği hakkında daha fazla bilgi için bkz: Enterprise Mobility + Security blog gönderisi [birlikte daha güçlü: Kullanıcı erişimini iyileştirmek için Intune ve Azure Active Directory ekip çalışması yapıyor](https://cloudblogs.microsoft.com/enterprisemobility/2017/07/06/better-together-intune-and-azure-active-directory-team-up-to-improve-user-access)’a bakın. Bu blog gönderisini başvuruları Intune Managed Browser, ancak içerik Microsoft Edge için de geçerlidir.

## <a name="how-to-configure-a-homepage-shortcut-for-microsoft-edge"></a>Microsoft Edge için giriş sayfası kısayol yapılandırma

Bu ayar, Microsoft Edge için giriş sayfası kısayol yapılandırmanıza olanak sağlar.  Yeni bir sekme içinde Microsoft Edge'i açtıklarında yapılandırdığınız giriş sayfası kısayolu altındaki Arama çubuğuna ilk simge olarak görünür. Kullanıcı düzenleme veya yönetilen bağlamları içinde bu kısayol silme mümkün olmayacaktır. Giriş sayfası kısayolu, kuruluşunuzun adını görüntüleyerek bunu ayırt eder. 

Kullanım anahtar/değer çifti giriş sayfası kısayol yapılandırmak için aşağıda:

|    Anahtar    |    Value    |
|-------------------------------------------------------------------|-------------|
|    com.microsoft.intune.mam.managedbrowser.homepage   |    Geçerli bir URL belirtin. Hatalı URL’ler güvenlik önlemi olarak engellenir.<br>**Örnek:** `<https://www.bing.com`>
    |

## <a name="how-to-configure-managed-bookmarks-for-microsoft-edge"></a>Microsoft Edge için yönetilen yer işaretleri yapılandırma

Erişim Kolaylığı için Microsoft Edge kullanırken, kullanıcılarınızın kullanılabilir istediğinizi yer işaretleri yapılandırabilirsiniz. Aşağıda, bazı ayrıntılar verilmiştir:

- Microsoft Edge Kurumsal modu kullanırken bu yer işaretleri yalnızca kullanıcılar için görünür. 
- Bu yer işaretleri silinemez veya kullanıcılar tarafından değiştirilmiş.
- Bu yer işaretleri listenin üstünde görüntülenir. Kullanıcıların kendi oluşturduğu yer işaretleri ise bu yer işaretlerinin altında bulunur.
- Uygulama Proxy’si yeniden yönlendirmesini etkinleştirdiyseniz dahili veya harici URL’den birini kullanarak Uygulama Proxy’si web uygulamaları ekleyebilirsiniz.

Yönetilen yer işaretlerini yapılandırmak için aşağıdaki anahtar/değer çifti kullanın:

|    Anahtar    |    Value    |
|---------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    com.microsoft.intune.mam.managedbrowser.Bookmarks    |    Bu yapılandırmanın değeri, yer işaretleri listesidir. Her bir yer işareti, yer işareti başlık ve yer işareti URL'si oluşur. Başlık ve URL ile ayrı `|` karakter.      **Örnek:**<br>`Microsoft Bing|https://www.bing.com`<br>Birden fazla yer işaretlerini yapılandırmak için her bir çifti çift karakteriyle ayırın `||`.<p>**Örnek:**<br>`Microsoft Bing|https://www.bing.com||Contoso|https://www.contoso.com`    |

## <a name="how-to-display-myapps-within-microsoft-edge-bookmarks"></a>Microsoft Edge yer işaretleri içinde MyApps görüntüleme

Varsayılan olarak, kullanıcılarınız için Microsoft Edge yer işaretleri içinde bir klasördeki yapılandırılmış olan MyApps siteleri gösterilir. Klasör kuruluşunuzun adıyla etiketlenir.

|    Anahtar    |    Value    |
|------------------------------------------------------|----------------------------------------------------------------------------------------------------------------|
|    com.microsoft.intune.mam.managedbrowser.MyApps    |    **Doğru** MyApps içinde Microsoft Edge işaretlerini gösterir.<p>**False** Microsoft Edge içinde MyApps gizler.    |

## <a name="how-to-specify-allowed-or-blocked-sites-list-for-microsoft-edge"></a>Microsoft Edge için izin verilen veya engellenen siteler listesine belirtme
Uygulama yapılandırması, kullanıcılarınız kendi iş profili kullanırken erişebilir hangi siteleri tanımlamak için kullanabilirsiniz. Bir izin verilenler listesi kullanırsanız, kullanıcılarınız yalnızca açıkça listelenen sitelerine erişebildiğinden olacaktır. Engellenen listesi kullanırsanız, kullanıcılarınızın açıkça engellenen siteler dışındaki tüm sitelerin erişmek mümkün olacaktır. Yalnızca, ya da bir izin verilen zorunlu kılmadan veya Engellenenler listesi, ikisi birden. Her ikisi de cihazı hedeflemiyor, izin verilenler getirilmez.  

Kullanabileceğiniz anahtar/değer çiftleri Microsoft Edge için izin verilen veya engellenen site listesi yapılandırmak için aşağıda. Geçerli URL biçimleri hakkında daha fazla bilgi için okumaya devam edin. 

|    Anahtar    |    Value    |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Aşağıdakilerden birini seçin:<p>1. İzin verilen URL’leri belirtme (yalnızca bu URL'lere izin verilir, diğer sitelere erişilemez):<br>`com.microsoft.intune.mam.managedbrowser.AllowListURLs`<p>2. Engellenen URL’leri belirtme (tüm diğer sitelere erişilebilir):<br>`com.microsoft.intune.mam.managedbrowser.BlockListURLs`    |    Bir anahtara karşılık gelen değer bir URL listesidir. İzin vermek veya kanalla ayrılan tek bir değer olarak engellemek istediğiniz URL'leri girin `|` karakter.<br>**Örnekler:**<br>`URL1|URL2|URL3`<br>`http://.contoso.com/|https://.bing.com/|https://expenses.contoso.com`  |

### <a name="url-formats-for-allowed-and-blocked-site-list"></a>URL biçimleri için izin verilen ve engellenen site listesi 
Çeşitli URL biçimleri, izin verilen/engellenen siteler listeleri oluşturmak için kullanabilirsiniz. Bu izin verilen desenler aşağıdaki tabloda açıklanmıştır. Başlamadan önce bazı notlar: 
- Tüm URL'leri listeye eklerken başlarına **http** veya **https** önekini yazdığınızdan emin olun.
- Joker karakter sembolünü kullanabilirsiniz (\*) aşağıdaki izin verilen örnekler listesindeki kurallara göre.
- Joker karakter yalnızca bir tüm compoment (noktalarla ayrılmış) ana bilgisayar adı veya tüm parçalarını (eğik ayrılmış olarak) yol eşleşebilir. Örneğin, `http://*contoso.com` olduğu **değil** desteklenir.
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
    |    `http://www.contoso.com:80`    |    Bir bağlantı noktası numarası kullanarak tek bir sayfayla eşleşir    |    http://www.contoso.com:80    |         |
    |    `https://www.contoso.com`    |    Güvenli tek bir sayfayla eşleşir    |    `https://www.contoso.com`    |    `http://www.contoso.com`    |
    |    `http://www.contoso.com/images/*`    |    Tek bir klasör ve tüm alt klasörleriyle eşleşir    |    `www.contoso.com/images/dogs`<br>`www.contoso.com/images/cats`    |    `www.contoso.com/videos`    |
  
- Belirtemeyeceğiniz bazı girdi örnekleri aşağıda verilmiştir:
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
  
## <a name="defining-behavior-when-users-try-to-access-a-blocked-site"></a>Engellenen bir siteye erişmek kullanıcılara çalıştığınızda davranışını tanımlama

Microsoft Edge ile oluşturulan çift kimlik modeliyle, son kullanıcılarınız Intune Managed Browser ile mümkün olmadığı için daha esnek bir deneyim etkinleştirebilirsiniz. Kullanıcıların Microsoft edge'de engellenen bir site ulaştığınızda, bunları şirket kaynaklarına güvenli korurken korumalı olarak kalmasını sağlar, iş bağlamında yerine kendi kişisel bağlamda bağlantıyı açın istenecek. Bir kullanıcı, Outlook haber makalesine bir bağlantı gönderilir, örneğin, bunlar bağlantıyı kendi kişisel bağlamda veya haber Web sitelerine izin vermeyen iş bağlamları yerine InPrivate bir sekmede açmak mümkün olacaktır. Varsayılan olarak, bu geçiş izin verilir.

Kullanım anahtar/değer çifti, bu geçici bir geçiş izin veriliyorsa yapılandırmak için aşağıda:

|    Anahtar    |    Value    |
|----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.mam.managedbrowser.AllowTransitionOnBlock`    |    **Doğru** Microsoft Edge engellenen siteler açmak için geçiş, kullanıcıların kendi kişisel bağlam sağlar<p>**Blok** kullanıcılar, geçiş gelen Microsoft Edge engeller ve kullanıcıların yalnızca, erişmeye çalıştığınız sitenin engellenir bildiren bir ileti gösterilecek.    |

## <a name="directing-users-to-microsoft-edge-instead-of-the-intune-managed-browser"></a>Microsoft Edge yerine Intune Managed Browser kullanıcılarına yönlendiren 

Intune Managed Browser ve Microsoft Edge sunulmuştur ilkeyle korunan tarayıcı olarak kullanılabilir. Kullanıcılarınızın doğru tarayıcı uygulamasını kullanmak için yönlendirilmesi emin olmak için Intune tarafından yönetilen uygulamalarla (örneğin Outlook, OneDrive ve SharePoint) şu yapılandırma ayarı tüm hedef:

|    Anahtar    |    Değer    |
|------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.useEdge`    |    Değer `true` indirin ve Microsoft Edge kullanıcılarınıza yönlendirir.<br>Değer `false` kullanıcılarınızın Intune Managed Browser kullanmasını sağlar.    |

Bu uygulama yapılandırma değeri ise **değil** ayarlayın, aşağıdaki mantık tarayıcıyı Kurumsal bağlantılarını açmak için kullanılacak tanımlayacaksınız.

Android’de:
- Intune Managed Browser ve Microsoft Edge cihazlarına indirilen bir kullanıcı varsa, Intune Managed Browser başlatılır. 
- Microsoft Edge, yalnızca Microsoft Edge cihaza yüklenir ve Intune ilkesiyle hedeflenen açılır.
- Yalnızca Managed Browser olan cihazda ve Intune ilkesiyle hedeflenen yönetilen tarayıcıda açılır.

Intune SDK’sını iOS v için tümleştiren uygulamalarda iOS’ta. 9.0.9+:
- Cihazda Managed Browser ve Microsoft Edge kullanıyorsanız, Intune Managed Browser başlatılır.  
- Microsoft Edge, yalnızca Microsoft Edge olan cihazda ve Intune ilkesiyle hedeflenen başlatılır.
- Managed Browser olan cihazda ve Intune ilkesiyle hedeflenen yalnızca yönetilen tarayıcı.

## <a name="using-microsoft-edge-on-ios-to-access-managed-app-logs"></a>Microsoft Edge İos'ta yönetilen uygulama günlüklerine erişmek için kullanma. 

Microsoft Edge iOS cihazlarında yüklü olan son kullanıcılar, tüm yönetim durumunu görüntüleyebilir Microsoft yayımlanan uygulamalar. Yönetilen iOS uygulamalarında sorun gidermek için günlükleri gönderebilirler.
1. Microsoft Edge, iOS Cihazınızda açın.
2. Adres kutusuna `about:intunehelp` yazın. 
3. Sorun giderme moduna gelen Microsoft Edge içinde başlatılacak.

Uygulama günlüklerinde saklanan ayarların bir listesi için, bkz. [Yönetilen Tarayıcı’da uygulama koruma günlüklerini inceleyin](app-protection-policy-settings-log.md).

Android cihazlarda günlüklerini görüntüleme için bkz [günlükleri BT yöneticinize gönderme e-posta ile](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android). 

## <a name="security-and-privacy-for-microsoft-edge"></a>Microsoft Edge için güvenlik ve gizlilik

Ek güvenlik ve gizlilik konuları Microsoft Edge için:

- Microsoft Edge, Microsoft Edge için bu ayarları erişemediği için kullanıcıların cihazlarında yerel tarayıcılarında bu işlem için ayarlanan ayarları tüketmez.
- Seçeneğini yapılandırırsanız **erişim için basit PIN gerektir** veya **erişim için Kurumsal kimlik bilgilerini gerektir** uygulama koruma İlkesi, Microsoft Edge ile ilişkili ve bir kullanıcı hakkında Yardım bağlantısını seçerse kimlik doğrulaması sayfası olup ilkesinde bir engelleme listesine eklenmiş olmasından bağımsız olarak herhangi bir Internet sitesine göz atabilir.
- Yalnızca bunlar doğrudan erişildiğinde Microsoft Edge sitelere erişimi engelleyebilir. Siteye erişmek için ara hizmetler (örneğin bir çeviri hizmeti) kullanıldığında erişimi engellemez.
- Kimlik doğrulamasına izin ver ve Intune belgelerine erişim * **. microsoft.com** izin verilenler veya Engellenenler listesi ayarlarının dışında tutulur. Adrese her zaman izin verilir.
Microsoft kullanım verilerini kapatma toplanan performansı ve Microsoft Ürün ve hizmetlerini geliştirmek için Managed Browser kullanımı hakkında anonim bilgileri otomatik olarak açın. Kullanıcılar cihazlarındaki **Kullanım Verileri** ayarını kullanarak veri toplamayı kapatabilir. Bu verilerin toplanması üzerinde denetiminiz yoktur. iOS cihazlarda, kullanıcıların ziyaret ettiği süresi dolmuş veya güvenilmeyen sertifikalara sahip web siteleri açılmaz.

## <a name="next-steps"></a>Sonraki adımlar

- [Uygulama koruma ilkeleri nedir?](app-protection-policy.md) 
