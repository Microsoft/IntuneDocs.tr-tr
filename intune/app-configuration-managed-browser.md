---
title: Web erişimini ilkeyle korunan bir tarayıcı ile yönetme
titlesuffix: Microsoft Intune
description: Web taramayı ve Web veri aktarımını kısıtlamak için ilkeyle korunan bir tarayıcı kullanın.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1feca24f-9212-4d5d-afa9-7c171c5e8525
ms.reviewer: ilwu
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: d86df4c38e0d4313dbff6ff2cd9111b2126dbaba
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52180944"
---
# <a name="manage-internet-access-using-a-microsoft-intune-policy-protected-browser"></a>Microsoft Intune ilke korumalı tarayıcısını kullanarak İnternet erişimini yönetme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune ilkesiyle korunan bir tarayıcı (Microsoft Edge veya Intune Managed Browser) kullanarak kurumsal Web sitelerine her zaman koruma önlemleri devrede olarak erişilmesini sağlayabilirsiniz.  Intune ile yapılandırıldığında korumalı tarayıcılar aşağıdakilerden yararlanabilir:

- Uygulama koruma ilkeleri.
- Koşullu erişim.
- Çoklu oturum açma.
- Uygulama yapılandırma ayarları.
- Azure uygulama proxy tümleştirmesi.

## <a name="getting-started"></a>Başlarken

Microsoft Edge ve Intune Managed Browser, kuruluşunuzda kullanılmak üzere sizin ve son kullanıcılarınızın genel uygulama mağazalarından indirebileceği web tarayıcısı uygulamalarıdır. 

Tarayıcı ilkeleri için işletim sistemi gereksinimleri:
- Android 4 ve üzeri veya
- iOS 8.0 ve üzeri.

Android ve iOS’un daha eski sürümleri Managed Browser'ı kullanmaya devam edebilecek, ancak uygulamanın yeni sürümlerini yükleyemeyecek ve uygulamanın tüm özelliklerine erişemeyecektir. Bu cihazları desteklenen işletim sistemi sürümüne güncelleştirmenizi öneririz.

>[!NOTE]
>Managed Browser, Güvenli Yuva Katmanı sürüm 3 (SSLv3) şifreleme protokolünü desteklemez.


## <a name="application-protection-policies-for-protected-browsers"></a>Korumalı tarayıcılar için uygulama koruma ilkeleri

Microsoft Edge ve Managed Browser’ın Intune SDK’sıyla tümleştirmesi olduğu için bunlara aşağıdakiler de dahil olmak üzere uygulama koruma ilkeleri uygulayabilirsiniz:
- Kesme, kopyalama ve yapıştırma işlemlerini denetleme.
- Ekran yakalamayı önleme.
- Şirket bağlantılarının yalnızca yönetilen uygulama ve tarayıcılarda açılmasını sağlama.

Ayrıntılar için bkz. [Uygulama koruma ilkesi nedir?](app-protection-policy.md)

Bu ayarları şunlara uygulayabilirsiniz:

- Intune’a kayıtlı cihazlar
- Başka bir MDM ürününe kayıtlı cihazlar
- Yönetilmeyen cihazlar

>[!NOTE]
>Kullanıcılar Managed Browser’ı uygulama mağazasından yüklemişse ve Intune tarafından yönetilmiyorsa Microsoft MyApps sitesi üzerinden Çoklu Oturum Açma desteğiyle birlikte temel bir web tarayıcısı olarak kullanılabilir. Kullanıcılar, sağlanan tüm SaaS uygulamalarını görebilecekleri MyApps sitesine doğrudan yönlendirilir.
Managed Browser veya Microsoft Edge, Intune tarafından yönetilmediğinde Intune tarafından yönetilen diğer uygulamaların verilerine erişemez. 


## <a name="conditional-access-for-protected-browsers"></a>Korumalı tarayıcılar için Koşullu Erişim

Managed Browser artık Koşullu Erişim için onaylı bir istemci uygulaması. Yani Azure AD bağlantılı web uygulamalarında mobil tarayıcı erişimini kısıtlayabilir, böylece kullanıcıların yalnızca Managed Browser kullanmasını sağlayarak Safari veya Chrome gibi korumasız tarayıcılardan erişimi engelleyebilirsiniz. Bu koruma; Exchange Online ve SharePoint Online, Office portalı ve hatta [Azure AD Uygulama Ara Sunucusu](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) yoluyla harici kullanıcılara sunduğunuz şirket içi siteler gibi Azure kaynaklarına uygulanabilir. 

Azure AD bağlantılı web uygulamalarının mobil platformlarda Intune Managed Browser kullanmasını kısıtlamak için, onaylı istemci uygulamalarını gerektiren bir Azure AD Koşullu Erişim ilkesi oluşturabilirsiniz. 

1. Azure portalında **Azure Active Directory** > **Kuruluş uygulamaları** > **Koşullu erişim** > **Yeni ilke**’yi seçin. 
2. Daha sonra, dikey pencerenin **Erişim denetimleri** bölümünden **İzin Ver**’i seçin. 
3. **Onaylı istemci uygulaması gerektir**’e tıklayın. 
4. **İzin Ver** dikey penceresinde **Seçin**’e tıklayın. Bu ilke, yalnızca Intune Managed Browser uygulaması tarafından erişilebilir olmasını istediğiniz bulut uygulamalarına atanmalıdır.

    ![Azure AD - Managed Browser koşullu erişim ilkesi](./media/managed-browser-conditional-access-01.png)

5. **Atamalar** bölümünde **Koşullar** > **İstemci uygulamaları**’nı seçin. **İstemci uygulamaları** dikey penceresi görüntülenir.
6. Belirli istemci uygulamalarında ilkeyi uygulamak için **Yapılandır** altında **Evet**’e tıklayın.
7. **Tarayıcı**’nın bir istemci uygulaması olarak seçildiğini doğrulayın.

    ![Azure AD - Managed Browser - İstemci uygulamalarını seçme](./media/managed-browser-conditional-access-02.png)

    > [!NOTE]
    > Bu bulut uygulamalarına erişebilecek yerel uygulamaları (tarayıcı olmayan uygulamalar) kısıtlamak için **Mobil uygulamalar ve masaüstü istemciler**’i de seçebilirsiniz.

8. **Atamalar** bölümünde **Kullanıcılar ve gruplar**’ı seçin ve ardından bu ilkeyi atayacağınız kullanıcı veya grupları seçin. 

    > [!NOTE]
    > Kullanıcıların, Uygulama Yapılandırma ilkelerini alabilmeleri için ayrıca Intune Uygulama Koruması ilkesi ile hedeflenmeleri gerekir. Intune Uygulama Koruma ilkeleri oluşturma hakkında daha fazla bilgi için bkz. [Uygulama koruma ilkeleri nelerdir?](app-protection-policy.md)

9. **Atamalar** bölümünde **Bulut uygulamaları**’nı seçerek bu ilkeyle hangi uygulamaları koruyacağınızı seçin.

Yukarıdaki ilke yapılandırıldıktan sonra kullanıcılar, bu ilkeyle koruduğunuz Azure AD bağlantılı web uygulamalarına erişmek için Intune Managed Browser’ı kullanmaya zorlanacaktır. Bu senaryoda kullanıcılar yönetilmeyen bir tarayıcı kullanmaya çalışırsa, Intune Managed Browser kullanmaları gerektiğine dair bir bildirim göreceklerdir.

Managed Browser, klasik Koşullu Erişim ilkelerini desteklemez. Daha fazla bilgi için bkz. [Azure portalında klasik ilkeleri geçirme](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-migration).

##  <a name="single-sign-on-to-azure-ad-connected-web-apps-in-policy-protected-browsers"></a>İlkeyle korunan tarayıcılarda Azure AD'ye bağlanmış Web uygulamalarında Çoklu Oturum Açma

iOS ve Android’de Microsoft Edge ve Intune Managed Browser Azure AD'ye bağlanmış tüm web uygulamalarında (SaaS ve şirket içi) SSO'dan yararlanabilir. iOS'ta Microsoft Authenticator uygulaması veya Android'de Intune Şirket Portalı uygulaması olduğunda, ilkeyle korunan bir tarayıcının kullanıcıları Azure AD'ye bağlanmış web uygulamalarına kimlik bilgilerini yeniden girmek zorunda kalmadan erişebilir.

SSO, cihazınızın iOS'de Microsoft Authenticator, Android'de Intune Şirket Portalı uygulaması tarafından kaydedilmiş olmasını gerektirir. Authenticator uygulaması veya Şirket Portalı olan kullanıcılardan, ilkeyle korunan bir tarayıcıda Azure AD'ye bağlanmış bir web uygulamasına gittiklerinde; daha önce başka bir uygulamaya kaydedilmemişse cihazlarını kaydetmeleri istenir. Cihaz, Intune tarafından yönetilen bir hesap ile kaydedildiğinde, bu hesapta Azure AD bağlantılı web uygulamaları için SSO etkin olacaktır. 

> [!NOTE]
> Cihaz kaydı, Azure AD hizmeti ile basit bir iade etme işlemidir. Tam cihaz kaydı gerektirmez ve BT ekibine cihaz üzerinde herhangi bir ek ayrıcalık sağlamaz.

## <a name="create-a-protected-browser-app-configuration"></a>Korumalı tarayıcı uygulama yapılandırması oluşturma

>[!IMPORTANT]
>Uygulama yapılandırmalarının uygulanması için kullanıcının korumalı tarayıcısının veya cihazdaki başka bir uygulamanın [Intune uygulama koruma ilkesi]( app-protection-policy.md) tarafından yönetiliyor olması gerekir

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3.  Yönetim listesinin **İstemci uygulamaları** dikey penceresinde **Uygulama yapılandırma ilkeleri**’ni seçin.
4.  **Uygulama yapılandırma ilkeleri** dikey penceresinde, **Ekle**’yi seçin.
5.  **Yapılandırma ilkesi ekle** dikey penceresinde, uygulama yapılandırma ayarları için bir **Ad** ve isteğe bağlı bir **Açıklama** girin.
6.  **Cihaz kayıt** türü için **Yönetilen uygulamalar**’ı seçin.
7.  **Gerekli uygulamayı seçin** öğesini belirleyin ve ardından **Hedeflenen uygulamalar** dikey penceresinde iOS, Android veya her ikisi için **Managed Browser**’ı ve/veya **Edge**'i seçin.
8.  **Tamam**’ı seçerek **Yapılandırma ilkesi ekle** dikey penceresine dönün.
9.  **Yapılandırma ayarları**’nı seçin. **Yapılandırma** dikey penceresinde, Managed Browser için yapılandırmaları sağlamak üzere anahtar ve değer çiftlerini tanımlayın. Tanımlayabileceğiniz farklı anahtar ve değer çiftleri hakkında bilgi edinmek için bu makalenin ilerleyen bölümlerine göz atın.
10. İşiniz bittiğinde **Tamam**’ı seçin.
11. **Yapılandırma ilkesi ekle** dikey penceresinde, **Ekle**’yi seçin.
12. Yeni yapılandırma oluşturulur ve **Uygulama yapılandırması** dikey penceresinde görüntülenir.


## <a name="assign-the-configuration-settings-you-created"></a>Oluşturduğunuz yapılandırma ayarlarını atama

Ayarları Azure AD kullanıcı gruplarına atayın. Bu kullanıcı hedeflenen korumalı tarayıcı uygulamasını yüklemişse uygulama belirttiğiniz ayarlarla yönetiliyordur.

1. Intune mobil uygulama yönetimi panosunun **İstemci uygulamaları** dikey penceresinde, **Yapılandırma ilkeleri ekle**’yi seçin.
2. Uygulama yapılandırmaları listesinden atamak istediğiniz birini seçin.
3. Sonraki dikey pencerede **Atamalar**’ı seçin.
4. **Atamalar** dikey penceresinde, uygulama yapılandırmasını atamak istediğiniz Azure AD grubunu ve ardından **Tamam**’ı seçin.


## <a name="how-to-configure-application-proxy-settings-for-protected-browsers"></a>Korumalı tarayıcılar için Uygulama Ara Sunucusu ayarlarını yapılandırma

Microsoft Edge ve Intune Managed Browser ile [Azure AD Uygulama Ara Sunucusu]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started), iOS ve Android cihaz kullanıcıları için şu senaryoları desteklemek amacıyla birlikte kullanılabilir:

- Bir kullanıcı Microsoft Outlook uygulamasını indirir ve burada oturum açar. Intune uygulama koruma ilkeleri otomatik olarak uygulanır. Bu ilkeler, kayıtlı verileri şifreler ve kullanıcıların şirket dosyalarını cihazdaki yönetilmeyen uygulamalara veya konumlara aktarmasını engeller. Daha sonra kullanıcı Outlook’ta bir İntranet site bağlantısına tıkladığında bağlantının başka bir tarayıcı yerine korumalı tarayıcı uygulamasında açılacağını belirtebilirsiniz. Korumalı tarayıcı bu İntranet sitenin kullanıcıya Uygulama Ara Sunucusu aracılığıyla sunulduğunu algılar. Kullanıcı, İntranet siteye ulaşmadan önce Uygulama Proxy’sinden herhangi bir uygun çok faktörlü kimlik doğrulamasında ve koşullu erişimde kimlik doğrulamak üzere yönlendirilir. Önceden, kullanıcı uzakken bulunamayan bu site artık erişilebilir durumdadır ve Outlook’taki bağlantı olması gerektiği gibi çalışır.
- Bir uzak kullanıcı korumalı tarayıcı uygulamasını açar ve dahili URL’yi kullanarak bir İntranet sitesine gider. Korumalı tarayıcı bu İntranet sitesinin kullanıcıya Uygulama Ara Sunucusu aracılığıyla sunulduğunu algılar. Kullanıcı, İntranet siteye ulaşmadan önce Uygulama Proxy’sinden herhangi bir uygun çok faktörlü kimlik doğrulamasında ve koşullu erişimde kimlik doğrulamak üzere yönlendirilir. Önceden, kullanıcı uzakken bulunamayan bu site artık erişilebilir durumdadır.

### <a name="before-you-start"></a>Başlamadan önce

- Dahili uygulamalarınızı Azure AD Uygulama Proxy’si aracılığıyla ayarlayın.
    - Uygulama Proxy’sini yapılandırmak ve uygulama yayımlamak için bkz. [kurulum belgeleri](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started#how-to-get-started). 
- Managed Browser uygulamasının 1.2.0 veya üzeri bir sürümünü kullanıyor olmanız gerekir.
- Managed Browser veya Microsoft Edge uygulamalarının kullanıcıları, uygulamaya atanmış bir [Intune uygulama koruma ilkesine]( app-protection-policy.md) sahiptir.

    > [!NOTE]
    > Güncelleştirilmiş Uygulama Ara Sunucusu’nun yeniden yönlendirme verilerinin Managed Browser’da veya Microsoft Edge'de etkinleşmesi 24 saati bulabilir.


#### <a name="step-1-enable-automatic-redirection-to-a-protected-browser-from-outlook"></a>1. adım: Outlook'tan korumalı tarayıcıya otomatik yeniden yönlendirmeyi etkinleştirme
Outlook’un, **Managed Browser’da görüntülenecek içeriği kısıtla** ayarına imkan veren bir uygulama koruma ilkesiyle yapılandırılması gereklidir.

#### <a name="step-2-assign-an-app-configuration-policy-assigned-for-the-protected-browser"></a>2. adım: Korumalı tarayıcıya atanmış bir uygulama koruma ilkesini atama.
Bu yordam ile Managed Browser veya Microsoft Edge uygulamasını, uygulama ara sunucusu yeniden yönlendirmesini kullanmak üzere yapılandırabilirsiniz. Microsoft Edge veya Managed Browser uygulama yapılandırması oluşturma yordamını kullanarak aşağıdaki anahtar ve değer çiftini sağlayın:

| Anahtar                                                             | Değer    |
|-----------------------------------------------------------------|----------|
| **com.microsoft.intune.mam.managedbrowser.AppProxyRedirection** | **true** |

Managed Browser, Microsoft Edge ve Azure AD Uygulama Ara Sunucusu’nun şirket içi web uygulamalarına sorunsuz (ve korumalı) erişim için birlikte nasıl kullanılabileceği hakkında daha fazla bilgi için Enterprise Mobility + Security blog gönderisi [Birlikte daha güçlü: Kullanıcı erişimini iyileştirmek için Intune ve Azure Active Directory ekip çalışması yapıyor](https://cloudblogs.microsoft.com/enterprisemobility/2017/07/06/better-together-intune-and-azure-active-directory-team-up-to-improve-user-access)’a bakın.

> [!NOTE]
> Microsoft Edge, Managed Browser ile aynı anahtar ve değer çiftini kullanır. 

## <a name="how-to-configure-the-homepage-for-a-protected-browser"></a>Korumalı tarayıcı için giriş sayfasını yapılandırma

Bu ayar ile kullanıcıların korumalı tarayıcıyı başlattıklarında veya yeni bir sekme oluşturduklarında karşılarına çıkacak giriş sayfasını yapılandırabilirsiniz. Microsoft Edge veya Managed Browser uygulama yapılandırması oluşturma yordamını kullanarak aşağıdaki anahtar ve değer çiftini sağlayın:

|                                Anahtar                                |                                                           Değer                                                            |
|-------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|
| <strong>com.microsoft.intune.mam.managedbrowser.homepage</strong> | Geçerli bir URL belirtin. Hatalı URL’ler güvenlik önlemi olarak engellenir.<br>Örnek: `<https://www.bing.com>` |

## <a name="how-to-configure-bookmarks-for-a-protected-browser"></a>Korumalı tarayıcı için yer işaretlerini yapılandırma

Bu ayar ile Microsoft Edge veya Managed Browser kullanıcılarına sunulmak üzere bazı yer işaretleri yapılandırabilirsiniz.

- Bu yer işaretleri, kullanıcılar tarafından silinemez veya değiştirilemez
- Bu yer işaretleri listenin üstünde görüntülenir. Kullanıcıların kendi oluşturduğu yer işaretleri ise bu yer işaretlerinin altında bulunur.
- Uygulama Proxy’si yeniden yönlendirmesini etkinleştirdiyseniz dahili veya harici URL’den birini kullanarak Uygulama Proxy’si web uygulamaları ekleyebilirsiniz.

Microsoft Edge veya Managed Browser uygulama yapılandırması oluşturma yordamını kullanarak aşağıdaki anahtar ve değer çiftini sağlayın:

|                                Anahtar                                 |                                                                                                                                                                                                                                                         Değer                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <strong>com.microsoft.intune.mam.managedbrowser.bookmarks</strong> | Bu yapılandırmanın değeri, bir yer işaretleri listesidir. Her bir yer işareti, yer işareti adı ve URL’sinden oluşur. Başlık ve URL’yi <strong>&#124;</strong> karakteriyle ayırın.<br><br>Örnek:<br> <code>Microsoft Bing&#124;https://www.bing.com</code><br><br>Birden çok yer işareti yapılandırmak için her bir başlık-URL ikilisini çift karakterle ayırın, <strong>&#124;&#124;</strong><br><br>Örnek:<br> <code>Bing&#124;https://www.bing.com&#124;&#124;Contoso&#124;https://www.contoso.com</code> |

## <a name="how-to-specify-allowed-and-blocked-urls-for-a-protected-browser"></a>Korumalı tarayıcı için izin verilen ve engellenen URL’leri belirtme

Microsoft Edge veya Managed Browser uygulama yapılandırması oluşturma yordamını kullanarak aşağıdaki anahtar ve değer çiftini sağlayın:

|Anahtar|Değer|
|-|-|
|Aşağıdakilerden birini seçin:<br><ul><li>İzin verilen URL’leri belirtme (yalnızca bu URL'lere izin verilir, diğer sitelere erişilemez):<br> **com.microsoft.intune.mam.managedbrowser.AllowListURLs**<br><br></li><li>Engellenen URL’leri belirtme (tüm diğer sitelere erişilebilir):<br>**com.microsoft.intune.mam.managedbrowser.BlockListURLs**</li></ul>|Bir anahtara karşılık gelen değer bir URL listesidir. İzin vermek veya engellemek istediğiniz tüm URL’leri **&#124;** kanalla ayrılan tek bir değer olarak girin.<br><br>Örnekler:<br><br><code>URL1&#124;URL2&#124;URL3</code><br><code>http://*.contoso.com/*&#124;https://*.bing.com/*&#124;https://expenses.contoso.com</code>|

>[!IMPORTANT]
>Her iki anahtarı birden belirtmeyin. Her iki anahtar da aynı kullanıcıya hedeflenirse en kısıtlayıcı seçenek olarak izin verme anahtarı kullanılır.
>Ayrıca, şirket web siteleriniz gibi önemli sayfaları engellemediğinizden emin olun.

### <a name="url-format-for-allowed-and-blocked-urls"></a>İzin verilen ve engellenen URL'ler için URL biçimi
İzin verilenler ve engellenenler listesinde URL belirtirken kullanabileceğiniz izin verilen biçimler ve joker karakterler hakkında bilgi almak için aşağıdaki bilgileri kullanın:

- Joker karakter sembolünü (**&#42;**) aşağıdaki izin verilen örnekler listesinde yer alan kurallara uygun olarak kullanabilirsiniz:

- Tüm URL'leri listeye eklerken başlarına **http** veya **https** önekini yazdığınızdan emin olun.

- Adreste bağlantı noktası numaraları belirtebilirsiniz. Bir bağlantı noktası numarası belirtmezseniz, kullanılan değerler şöyle olacaktır:

  -   http için bağlantı noktası 80

  -   https için bağlantı noktası 443

  Bağlantı noktası numarası için joker karakter kullanımı desteklenmez. Örneğin `http://www.contoso.com:;` ve `http://www.contoso.com: /;` desteklenmez.

- URL belirtirken kullanabileceğini izin verilen desenler hakkında bilgi almak için aşağıdaki tabloyu kullanın:

|                  URL                  |                     Ayrıntılar                      |                                                Eşleşir                                                |                                Eşleşmez                                 |
|---------------------------------------|--------------------------------------------------|-------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------|
|        `http://www.contoso.com`         |              Tek bir sayfayla eşleşir               |                                            `www.contoso.com`                                            |  `host.contoso.com`<br /><br />`www.contoso.com/images`<br /><br />`contoso.com`/   |
|          `http://contoso.com`           |              Tek bir sayfayla eşleşir               |                                             `contoso.com/`                                              | `host.contoso.com`<br /><br />`www.contoso.com/images`<br /><br />`www.contoso.com` |
|    `http://www.contoso.com/&#42;`     | `www.contoso.com` ile başlayan tüm URL’lerle eşleşir |      `www.contoso.com`<br /><br />`www.contoso.com/images`<br /><br />`www.contoso.com/videos/tvshows`      |              `host.contoso.com`<br /><br />`host.contoso.com/images`              |
|    `http://*.contoso.com/*`     |     contoso.com altındaki tüm alt etki alanlarıyla eşleşir     | `developer.contoso.com/resources`<br /><br />`news.contoso.com/images`<br /><br />`news.contoso.com/videos` |                               `contoso.host.com`                                |
|     `http://www.contoso.com/images`     |             Tek bir klasörle eşleşir              |                                        `www.contoso.com/images`                                         |                          `www.contoso.com/images/dogs`                          |
|       `http://www.contoso.com:80`       |  Bağlantı noktası numarası kullanarak tek bir sayfayla eşleşir   |                                       `http://www.contoso.com:80`                                       |                                                                               |
|        `https://www.contoso.com`        |          Güvenli tek bir sayfayla eşleşir           |                                        `https://www.contoso.com`                                        |                            `http://www.contoso.com`                             |
| `http://www.contoso.com/images/&#42;` |    Tek bir klasör ve tüm alt klasörleriyle eşleşir    |                  `www.contoso.com/images/dogs`<br /><br />`www.contoso.com/images/cats`                   |                            `www.contoso.com/videos`                             |

- Belirtemeyeceğiniz bazı girdi örnekleri aşağıda verilmiştir:

  - `*.com`

  - `*.contoso/*`

  - `www.contoso.com/*images`

  - `www.contoso.com/*images*pigs`

  - `www.contoso.com/page*`

  - IP adresleri

  - `https://*`

  - `http://*`

  - `http://www.contoso.com:*`

  - `http://www.contoso.com: /*`

## <a name="how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios"></a>iOS’ta Managed Browser kullanarak yönetilen uygulama günlüklerine erişme

iOS cihazlarında Managed Browser yüklü olan son kullanıcılar, tüm Microsoft uygulamalarının yönetim durumunu görüntüleyebilirler. Yönetilen iOS uygulamalarında sorun gidermek için günlükleri gönderebilirler.

1. iOS **Ayarlar**’ı açın.
2. **Managed Browser** uygulama ayarlarını seçin.
3. **Intune Tanılamayı Etkinleştir**’i açarak tarayıcıyı sorun giderme moduna ayarlayın.
4. **Managed Browser**’ı açın. **Intune Uygulama Durumunu Görüntüle**’ye tıklayarak uygulamaların kendi ilke ayarlarını gözden geçirin.
5. **Başla** ve **Günlük Paylaş** veya **Günlükleri Microsoft’a Gönder**’i seçerek sorun giderme günlüklerini BT yöneticinize veya Microsoft’a gönderin.

Browser’ı ayrıca uygulama içerisinden de sorun giderme modunda açabilirsiniz.

1. Managed Browser’ı açın.
2. Adres kutusuna `about:intunehelp` yazın.
Browser sorun giderme modunda açılacaktır.

Uygulama günlüklerinde saklanan ayarların bir listesi için, bkz. [Yönetilen Tarayıcı’da uygulama koruma günlüklerini inceleyin](app-protection-policy-settings-log.md).

## <a name="security-and-privacy-for-the-managed-browser"></a>Managed Browser için güvenlik ve gizlilik

-   Managed Browser, kullanıcıların cihazlarındaki yerleşik tarayıcı için yaptığı ayarları kullanmaz. Managed Browser bu ayarlara erişemez.

-   Managed Browser ile ilişkilendirilmiş bir uygulama koruma ilkesinde **Erişim için basit PIN gerektir** veya **Erişim için şirket kimlik bilgilerini gerektir** seçeneklerini yapılandırırsanız ve bir kullanıcı kimlik doğrulama sayfasındaki yardım bağlantısını seçerse bu kullanıcı, ilkede bir engelleme listesine eklenmiş olup olmamasından bağımsız olarak herhangi bir İnternet sitesine gözatabilir.

-   Managed Browser sitelere yalnızca doğrudan erişildiğinde erişimi engelleyebilir. Siteye erişmek için ara hizmetler (örneğin bir çeviri hizmeti) kullanıldığında erişimi engellemez.

-   Kimlik doğrulama ve Intune belgelerine erişime izin vermek için **&#42;.microsoft.com** izin ver/engelle liste ayarlarının dışında tutulur. Adrese her zaman izin verilir.

### <a name="turn-off-usage-data"></a>Kullanım verilerini kapatma
Microsoft, ürün ve hizmetlerini geliştirmek için Managed Browser’ın performansı ve kullanımı hakkında otomatik olarak anonim bilgiler toplar. Kullanıcılar cihazlarındaki **Kullanım Verileri** ayarını kullanarak veri toplamayı kapatabilir. Bu verilerin toplanması üzerinde denetiminiz yoktur.

-   iOS cihazlarda, kullanıcıların ziyaret ettiği süresi dolmuş veya güvenilmeyen sertifikalara sahip web siteleri açılmaz.

## <a name="next-steps"></a>Sonraki adımlar

- [Uygulama koruma ilkeleri nedir?](app-protection-policy.md) 
