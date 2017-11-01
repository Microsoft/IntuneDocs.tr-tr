---
title: "Managed Browser uygulaması ile web erişimini yönetme"
titlesuffix: Azure portal
description: "Web’e gözatmayı ve web verilerinin başka uygulamalara aktarımını kısıtlamak için Managed Browser uygulamasını dağıtın.\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1feca24f-9212-4d5d-afa9-7c171c5e8525
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 99b8b50dbbb2dc2e3d7e8cd5af2f95fa2bb3b861
ms.sourcegitcommit: 42a0e4c83e33c1a25506ca75d673e861e9206945
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/26/2017
---
# <a name="manage-internet-access-using-managed-browser-policies-with-microsoft-intune"></a>Microsoft Intune ile Managed Browser ilkelerini kullanarak İnternet erişimini yönetme

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Managed Browser, kuruluşunuzda kullanılmak üzere genel uygulama mağazalarından indirebileceğiniz bir web tarayıcısı uygulamasıdır. Intune ile yapılandırıldığında Manager Browser:
- MyApps hizmeti aracılığıyla Çoklu Oturum Açma ile şirket sitelerine ve SaaS uygulamalarına erişmek ve bu esnada web verilerini korumak için kullanılabilir.
- Kurumsal bağlamda kullanıcının girebileceği siteleri kısıtlamak için kısıtlanan URL’ler ve etki alanları listesiyle önceden yapılandırılabilir.
- Bir giriş sayfası ve belirttiğiniz yer işaretleriyle önceden yapılandırılabilir.

Uygulamanın Intune SDK’sıyla tümleştirmesi olduğundan, buna aşağıdakiler de dahil olmak üzere uygulama koruma ilkeleri de uygulayabilirsiniz:
- Kesme, kopyalama ve yapıştırma işlemlerini denetleme
- Ekran yakalamayı önleme
- Bu sayede kullanıcıların seçtiği içeriklerin bağlantılarının yalnızca diğer yönetilen uygulamalarda açıldığından emin olabilirsiniz.

Ayrıntılar için bkz. [Uygulama koruma ilkesi nedir?](/intune/app-protection-policy)

Bu ayarları şunlara uygulayabilirsiniz:

- Intune’a kayıtlı cihazlar
- Başka bir MDM ürününe kayıtlı cihazlar
- Yönetilmeyen cihazlar

Kullanıcılar Managed Browser’ı uygulama mağazasından yüklemişse ve Intune tarafından yönetilmiyorsa Microsoft MyApps sitesi üzerinden Çoklu Oturum Açma desteğiyle birlikte temel bir web tarayıcısı olarak kullanılabilir. Kullanıcılar, sağlanan tüm SaaS uygulamalarını görebilecekleri MyApps sitesine doğrudan yönlendirilir.
Managed Browser, Intune tarafından yönetilmediğinde Intune tarafından yönetilen diğer uygulamaların verilerine erişemez. 

Managed Browser, Güvenli Yuva Katmanı sürüm 3 (SSLv3) şifreleme protokolünü desteklemez.

Aşağıdaki cihaz türleri için Managed Browser ilkeleri oluşturabilirsiniz:

-   Android 4 ve üzeri çalıştıran cihazlar

-   iOS 8.0 ve üzerini çalıştıran cihazlar

>[!IMPORTANT]
>Ekim 2017 itibariyle Android uygulamasındaki Intune Managed Browser uygulaması yalnızca Android 4.4 ve sonraki sürümleri çalıştıran cihazları desteklemektedir. iOS’taki Intune Managed Browser uygulaması yalnızca iOS 9.0 ve sonraki sürümleri çalıştıran cihazları destekleyecektir.
>Android ve iOS’un daha eski sürümleri Managed Browser'ı kullanmaya devam edebilecek, ancak uygulamanın yeni sürümlerini yükleyemeyecek ve uygulamanın tüm özelliklerine erişemeyecektir. Bu cihazların desteklenen işletim sistemi sürümüne güncelleştirmenizi öneririz.


Intune Managed Browser, [Microsoft Intune uygulama iş ortaklarının](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx) web içeriklerini açmayı destekler.

## <a name="create-a-managed-browser-app-configuration"></a>Bir Managed Browser uygulama yapılandırması oluşturma

1.  Azure Portal’da oturum açın.
2.  **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3.  Yönetim listesinin **Mobil uygulamalar** dikey penceresinde **Uygulama yapılandırma ilkeleri**’ni seçin.
4.  **Uygulama Yapılandırma ilkeleri** dikey penceresinde **Ekle**’yi seçin.
5.  **Uygulama yapılandırması ekle** dikey penceresinde, uygulama yapılandırma ayarları için bir **Ad** ve isteğe bağlı bir **Açıklama** girin.
6.  **Cihaz kaydı** türü için **Yönetilen cihazlar** veya **Yönetilen uygulamalar**’ı seçin.
7.  **Gerekli uygulamaları seç**’e tıklayın ve ardından **Hedeflenen uygulamalar** dikey penceresinde iOS için, Android için veya her ikisi için **Managed Browser**’ı seçin.
8.  **Tamam**’ı seçerek **Uygulama yapılandırması ekle** dikey penceresine dönün.
9.  **Yapılandırma Ayarları**’nı seçin. **Yapılandırma** dikey penceresinde, Managed Browser için yapılandırmaları sağlamak üzere anahtar ve değer çiftlerini tanımlayın. Tanımlayabileceğiniz farklı anahtar ve değer çiftleri hakkında bilgi edinmek için bu makalenin ilerleyen bölümlerine göz atın.
10. İşiniz bittiğinde **Tamam**’ı seçin.
11. **Uygulama yapılandırması ekle** dikey penceresinde, **Oluştur**’u seçin.
12. Yeni yapılandırma oluşturulur ve **Uygulama yapılandırması** dikey penceresinde görüntülenir.

>[!IMPORTANT]
>Mevcut durumda Managed Browser, otomatik kayıt kullanmaktadır. Uygulama yapılandırmalarının uygulanması için cihazdaki başka bir uygulamanın Intune uygulama koruma ilkeleri tarafından yönetiliyor olması gerekir.

## <a name="assign-the-configuration-settings-you-created"></a>Oluşturduğunuz yapılandırma ayarlarını atama

Ayarları Azure AD kullanıcı gruplarına atayın. Bu kullanıcı Managed Browser uygulamasını yüklemişse uygulama belirttiğiniz ayarlarla yönetiliyordur.

1. Intune mobil uygulama yönetimi panosunun **Ayarlar** dikey penceresinde, **Uygulama yapılandırması**’nı seçin.
2. Uygulama yapılandırmaları listesinden atamak istediğiniz birini seçin.
3. Sonraki dikey pencerede **Kullanıcı Grupları**’nı seçin.
4. **Kullanıcı grupları** dikey penceresinde, uygulama yapılandırmasını atamak istediğiniz Azure AD grubunu ve ardından **Tamam**’ı seçin.


## <a name="how-to-configure-application-proxy-settings-for-the-managed-browser"></a>Managed Browser için Uygulama Proxy’si ayarlarını yapılandırma

Intune Managed Browser ve [Azure AD Uygulama Proxy’si]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started), iOS ve Android cihaz kullanıcıları için şu senaryoları desteklemek amacıyla birlikte kullanılabilir:

- Bir kullanıcı Microsoft Outlook uygulamasını indirir ve burada oturum açar. Intune uygulama koruma ilkeleri otomatik olarak uygulanır. Bu ilkeler, kayıtlı verileri şifreler ve kullanıcıların şirket dosyalarını cihazdaki yönetilmeyen uygulamalara veya konumlara aktarmasını engeller. Daha sonra kullanıcı Outlook’ta bir İntranet site bağlantısına tıkladığında bağlantının başka bir tarayıcı yerine Managed Browser uygulamasında açılacağını belirtebilirsiniz. Managed Browser bu İntranet sitenin kullanıcıya Uygulama Proxy’si aracılığıyla sunulduğunu algılar. Kullanıcı, İntranet siteye ulaşmadan önce Uygulama Proxy’sinden herhangi bir uygun çok faktörlü kimlik doğrulamasında ve koşullu erişimde kimlik doğrulamak üzere yönlendirilir. Önceden, kullanıcı uzakken bulunamayan bu site artık erişilebilir durumdadır ve Outlook’taki bağlantı olması gerektiği gibi çalışır.
- Bir uzak kullanıcı Managed Browser uygulamasını açar ve dahili URL’yi kullanarak bir İntranet siteye gider. Managed Browser bu İntranet sitenin kullanıcıya Uygulama Proxy’si aracılığıyla sunulduğunu algılar. Kullanıcı, İntranet siteye ulaşmadan önce Uygulama Proxy’sinden herhangi bir uygun çok faktörlü kimlik doğrulamasında ve koşullu erişimde kimlik doğrulamak üzere yönlendirilir. Önceden, kullanıcı uzakken bulunamayan bu site artık erişilebilir durumdadır.

### <a name="before-you-start"></a>Başlamadan önce

- Dahili uygulamalarınızı Azure AD Uygulama Proxy’si aracılığıyla ayarlayın.
    - Uygulama Proxy’sini yapılandırmak ve uygulama yayımlamak için bkz. [kurulum belgeleri]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started#how-to-get-started). 
    - Managed Browser uygulamasının 1.2.0 veya üzeri bir sürümünü kullanıyor olmanız gerekir.
    - Managed Browser uygulamasının kullanıcıları, uygulamaya atanmış bir [Intune uygulama koruma ilkesine]( app-protection-policy.md) sahiptir.

#### <a name="step-1-enable-automatic-redirection-to-the-managed-browser-from-outlook"></a>1. adım: Outlook'tan Managed Browser’a otomatik yeniden yönlendirmeyi etkinleştirme
Outlook’un, **Managed Browser’da görüntülenecek içeriği kısıtla** ayarına imkan veren bir uygulama koruma ilkesiyle yapılandırılması gereklidir.

#### <a name="step-2-assign-an-app-configuration-policy-assigned-for-the-managed-browser"></a>2. adım: Managed Browser’a atanmış bir uygulama koruma ilkesini atama.
Bu yordam ile Managed Browser uygulamasını, uygulama proxy’si yeniden yönlendirmeyi kullanmak üzere yapılandırabilirsiniz. Managed Browser uygulama yapılandırması oluşturma yordamını kullanarak aşağıdaki anahtar ve değer çiftini sağlayın:

|||
|-|-|
|Anahtar|Değer|
|**com.microsoft.intune.mam.managedbrowser.AppProxyRedirection**|**true**|


## <a name="how-to-configure-the-homepage-for-the-managed-browser"></a>Managed Browser için giriş sayfası yapılandırma

Bu ayar ile kullanıcıların Managed Browser’ı başlattıklarında veya yeni bir sekme oluşturduklarında karşılarına çıkacak giriş sayfasını yapılandırabilirsiniz. Managed Browser uygulama yapılandırması oluşturma yordamını kullanarak aşağıdaki anahtar ve değer çiftini sağlayın:

|||
|-|-|
|Anahtar|Değer|
|**com.microsoft.intune.mam.managedbrowser.homepage**|Geçerli bir URL belirtin. Hatalı URL’ler güvenlik önlemi olarak engellenir.<br>Örnek: **https://www.bing.com**|


## <a name="how-to-configure-bookmarks-for-the-managed-browser"></a>Managed Browser için yer işaretleri yapılandırma

Bu ayar ile Managed Browser kullanıcılarına sunulmak üzere bazı yer işaretleri yapılandırabilirsiniz.

- Bu yer işaretleri, kullanıcılar tarafından silinemez veya değiştirilemez
- Bu yer işaretleri listenin üstünde görüntülenir. Kullanıcıların kendi oluşturduğu yer işaretleri ise bu yer işaretlerinin altında bulunur.
- Uygulama Proxy’si yeniden yönlendirmesini etkinleştirdiyseniz dahili veya harici URL’den birini kullanarak Uygulama Proxy’si web uygulamaları ekleyebilirsiniz.

Managed Browser uygulama yapılandırması oluşturma yordamını kullanarak aşağıdaki anahtar ve değer çiftini sağlayın:

|||
|-|-|
|Anahtar|Değer|
|**com.microsoft.intune.mam.managedbrowser.bookmarks**|Bu yapılandırmanın değeri, bir yer işaretleri listesidir. Her bir yer işareti, yer işareti adı ve URL’sinden oluşur. Başlık ve URL’yi **&#124;** karakteriyle ayırın.<br><br>Örnek: **Microsoft Bing&#124;https://www.bing.com**<br><br>Birden çok yer işareti yapılandırmak için her bir başlık-URL ikilisini çift karakterle ayırın, **&#124;&#124;**<br><br>Örnek: **Bing&#124;https://www.bing.com&#124;&#124;Contoso&#124;https://www.contoso.com**|

## <a name="how-to-specify-allowed-and-blocked-urls-for-the-managed-browser"></a>Managed Browser için izin verilen ve engellenen URL’leri belirtme

Managed Browser uygulama yapılandırması oluşturma yordamını kullanarak aşağıdaki anahtar ve değer çiftini sağlayın:

|||
|-|-|
|Anahtar|Değer|
|Aşağıdakilerden birini seçin:<br><br>- İzin verilen URL'leri belirtme (yalnızca bu URL'lere izin verilir; başka sitelere erişilemez): **com.microsoft.intune.mam.managedbrowser.AllowListURLs**<br><br>- Engellenen URL’leri belirtme (tüm diğer sitelere erişilebilir): <br><br>**com.microsoft.intune.mam.managedbrowser.BlockListURLs**|Bir anahtara karşılık gelen değer bir URL listesidir. İzin vermek veya engellemek istediğiniz tüm URL’leri **&#124;** kanalla ayrılan tek bir değer olarak girin.<br><br>Örnekler:<br><br>**URL1&#124;URL2&#124;URL3**<br>**http://*.contoso.com/*&#124;https://*.bing.com/*&#124;https://expenses.contoso.com**|

>[!IMPORTANT]
>Her iki anahtarı birden belirtmeyin. Her iki anahtar da aynı kullanıcıya hedeflenirse en kısıtlayıcı seçenek olarak izin verme anahtarı kullanılır.
>Ayrıca, şirket web siteleriniz gibi önemli sayfaları engellemediğinizden emin olun.

### <a name="url-format-for-allowed-and-blocked-urls"></a>İzin verilen ve engellenen URL'ler için URL biçimi
İzin verilenler ve engellenenler listesinde URL belirtirken kullanabileceğiniz izin verilen biçimler ve joker karakterler hakkında bilgi almak için aşağıdaki bilgileri kullanın:

-   Joker karakter sembolünü (**&#42;**) aşağıdaki izin verilen örnekler listesinde yer alan kurallara uygun olarak kullanabilirsiniz:

-   Tüm URL'leri listeye eklerken başlarına **http** veya **https** önekini yazdığınızdan emin olun.

-   Adreste bağlantı noktası numaraları belirtebilirsiniz. Bir bağlantı noktası numarası belirtmezseniz, kullanılan değerler şöyle olacaktır:

    -   http için bağlantı noktası 80

    -   https için bağlantı noktası 443

    Bağlantı noktası numarası için joker karakter kullanımı desteklenmez. Örneğin, **http&colon;//www&period;contoso&period;com:*;** ve **http&colon;//www&period;contoso&period;com: /*;** desteklenmez.

-   URL belirtirken kullanabileceğini izin verilen desenler hakkında bilgi almak için aşağıdaki tabloyu kullanın:

|URL|Ayrıntılar|Eşleşir|Eşleşmez|
|-------|---------------|-----------|------------------|
|http://www.contoso.com|Tek bir sayfayla eşleşir|www.contoso.com|host.contoso.com<br /><br />www.contoso.com/images<br /><br />contoso.com/|
|http://contoso.com|Tek bir sayfayla eşleşir|contoso.com/|host.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com|
|http://www.contoso.com/&#42;|www.contoso.com ile başlayan tüm URL'lerle eşleşir|www.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com/videos/tvshows|host.contoso.com<br /><br />host.contoso.com/images|
|http://&#42;.contoso.com/&#42;|contoso.com altındaki tüm alt etki alanlarıyla eşleşir|developer.contoso.com/resources<br /><br />news.contoso.com/images<br /><br />news.contoso.com/videos|contoso.host.com|
|http://www.contoso.com/images|Tek bir klasörle eşleşir|www.contoso.com/images|www.contoso.com/images/dogs|
|http://www.contoso.com:80|Bağlantı noktası numarası kullanarak tek bir sayfayla eşleşir|http://www.contoso.com:80|
|https://www.contoso.com|Güvenli tek bir sayfayla eşleşir|https://www.contoso.com|http://www.contoso.com|
|http://www.contoso.com/images/&#42;|Tek bir klasör ve tüm alt klasörleriyle eşleşir|www.contoso.com/images/dogs<br /><br />www.contoso.com/images/cats|www.contoso.com/videos|

-   Belirtemeyeceğiniz bazı girdi örnekleri aşağıda verilmiştir:

    -   &#42;.com

    -   &#42;.contoso/&#42;

    -   www.contoso.com/&#42;images

    -   www.contoso.com/&#42;images&#42;pigs

    -   www.contoso.com/page&#42;

    -   IP adresleri

    -   https://&#42;

    -   http://&#42;

    -   http://www.contoso.com:&#42;

    -   http://www.contoso.com: /&#42;

## <a name="security-and-privacy-for-the-managed-browser"></a>Managed Browser için güvenlik ve gizlilik

-   Managed Browser, kullanıcıların cihazlarındaki yerleşik tarayıcı için yaptığı ayarları kullanmaz. Managed Browser bu ayarlara erişemez.

-   Managed Browser ile ilişkilendirilmiş bir uygulama koruma ilkesinde **Erişim için basit PIN gerektir** veya **Erişim için şirket kimlik bilgilerini gerektir** seçeneklerini yapılandırırsanız ve bir kullanıcı kimlik doğrulama sayfasındaki yardım bağlantısını seçerse bu kullanıcı, ilkede bir engelleme listesine eklenmiş olup olmamasından bağımsız olarak herhangi bir İnternet sitesine gözatabilir.

-   Managed Browser sitelere yalnızca doğrudan erişildiğinde erişimi engelleyebilir. Siteye erişmek için ara hizmetler (örneğin bir çeviri hizmeti) kullanıldığında erişimi engellemez.

-   Kimlik doğrulama ve Intune belgelerine erişime izin vermek için **&#42;.microsoft.com** izin ver/engelle liste ayarlarının dışında tutulur. Adrese her zaman izin verilir.

### <a name="turn-off-usage-data"></a>Kullanım verilerini kapatma
Microsoft, ürün ve hizmetlerini geliştirmek için Managed Browser’ın performansı ve kullanımı hakkında otomatik olarak anonim bilgiler toplar. Kullanıcılar cihazlarındaki **Kullanım Verileri** ayarını kullanarak veri toplamayı kapatabilir. Bu verilerin toplanması üzerinde denetiminiz yoktur.


-   iOS cihazlarda, kullanıcıların ziyaret ettiği süresi dolmuş veya güvenilmeyen sertifikalara sahip web siteleri açılmaz.
-   Managed Browser, kullanıcıların cihazlarındaki yerleşik tarayıcı için yaptığı ayarları kullanmaz. Managed Browser bu ayarlara erişemez.

-   Managed Browser ile ilişkilendirilmiş bir uygulama koruma ilkesinde **Erişim için basit PIN gerektir** veya **Erişim için şirket kimlik bilgilerini gerektir** seçeneklerini yapılandırırsanız ve bir kullanıcı kimlik doğrulama sayfasındaki yardım bağlantısını seçerse bu kullanıcı, ilkede bir engelleme listesine eklenmiş olup olmamasından bağımsız olarak herhangi bir İnternet sitesine gözatabilir.

-   Managed Browser sitelere yalnızca doğrudan erişildiğinde erişimi engelleyebilir. Siteye erişmek için ara hizmetler (örneğin bir çeviri hizmeti) kullanıldığında erişimi engellemez.

-   Kimlik doğrulama ve Intune belgelerine erişime izin vermek için **&#42;.microsoft.com** izin ver/engelle liste ayarlarının dışında tutulur. Adrese her zaman izin verilir.

### <a name="turn-off-usage-data"></a>Kullanım verilerini kapatma
Microsoft, ürün ve hizmetlerini geliştirmek için Managed Browser’ın performansı ve kullanımı hakkında otomatik olarak anonim bilgiler toplar. Kullanıcılar cihazlarındaki **Kullanım Verileri** ayarını kullanarak veri toplamayı kapatabilir. Bu verilerin toplanması üzerinde denetiminiz yoktur.
