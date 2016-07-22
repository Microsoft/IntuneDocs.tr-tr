---
title: "Yönetilen tarayıcı ilkelerini kullanarak İnternet erişimini yönetme | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc946303-e09b-4d73-8bf4-87742299bc54
ms.reviewer: jeffgilb
ms.suite: ems
ms.sourcegitcommit: 2df44199ecd904dcfb6774a942244338c1384186
ms.openlocfilehash: c4462af584d54225084159dfa35f5e1d07c36397


---

# Microsoft Intune'la yönetilen tarayıcı ilkelerini kullanarak İnternet erişimini yönetme
Yönetilen tarayıcı, Microsoft Intune kullanarak kuruluşunuzda dağıtabileceğiniz bir web tarama uygulamasıdır. Yönetilen tarayıcı ilkesi, yönetilen tarayıcı kullanıcılarının ziyaret edebileceği web sitelerini kısıtlayan bir izin verilenler listesi veya engellenenler listesi yapılandırır.

Bu uygulama yönetilen bir uygulama olduğundan, kesme, kopyalama ve yapıştırma kullanımını denetleme, ekran yakalamayı önleme ve kullanıcıların tıkladığı içeriklerin yalnızca diğer yönetilen uygulamalarda açılmasını sağlama gibi mobil uygulama yönetimi ilkelerini uygulayabilirsiniz. Ayrıntılar için bkz. [Microsoft Intune konsolunda mobil uygulama yönetimi ilkelerini yapılandırma ve dağıtma](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).

> [!IMPORTANT]
>Kullanıcılar, uygulama mağazasından yönetilen tarayıcıyı yüklerse ve Intune tarafından yönetilmiyorsa, şu davranış geçerli olur: iOS – Yönetilen tarayıcı uygulaması, temel bir web tarayıcısı olarak kullanılabilir, ancak bazı özellikler kullanılamaz ve Intune ile yönetilen diğer uygulamalardan verilere erişilemez.
Android – Yönetilen tarayıcı uygulaması kullanılamaz.
Kullanıcılar yönetilen tarayıcıyı iOS 9'dan küçük bir sürümdeki bir iOS cihazına yüklerse oluşturduğunu hiçbir ilke tarafından yönetilmez. Tarayıcının Intune tarafından yönetildiğinden emin olmak için, uygulamayı kaldırmaları ve sizin yönetilen uygulama olarak onlara dağıtmanız gerekir. iOS 9 ve üstünde kullanıcı yönetilen tarayıcıyı kendisi yüklerse tarayıcının ilke tarafından yönetilmesine izin vermesi istenir.

Aşağıdaki cihaz türleri için yönetilen tarayıcı ilkeleri oluşturabilirsiniz:

-   Android 4 ve üzeri çalıştıran cihazlar

-   iOS 7.1 ve üzeri çalıştıran cihazlar

Intune Managed Browser, [Microsoft Intune uygulama iş ortaklarının](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) web içeriğini açmayı destekler.

## Yönetilen tarayıcı ilkesi oluşturma

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** &gt; **İlke Ekle**'ye tıklayın.

2.  Aşağıdaki **Yazılım** ilkesi türlerinden birini yapılandırın:

    -   **Yönetilen Tarayıcı İlkesi (Android 4 ve üzeri)**

    -   **Yönetilen Tarayıcı İlkesi (iOS 7.1 ve üzeri)**

    İlkeleri oluşturma ve kullanma hakkında daha fazla bilgi için, [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) konusuna bakın.

3.  Yönetilen tarayıcı ilkesi ayarlarını yapılandırmanıza yardımcı olması için aşağıdaki tabloyu kullanın:

|Ayar adı|Ayrıntılar|
    |----------------|--------------------|
    |**Ad**|Yönetilen tarayıcı ilkesini Intune konsolunda tanımanıza yardımcı olması için benzersiz bir ad belirtin.|
    |**Açıklama**|Yönetilen tarayıcı ilkesine genel bir bakış ve profili bulmanıza yardımcı olacak diğer ek bilgileri içeren bir açıklama sağlayın.|
    |**Yönetilen Tarayıcının açabileceği URL'leri kısıtlamak için bir izin verilenler listesi veya engellenenler listesi yapılandırma**|Aşağıdaki seçeneklerden birini belirleyin:<br /><br />**Yönetilen tarayıcının yalnızca aşağıdaki URL'leri açmasına izin ver** – Yönetilen tarayıcının açabileceği URL'lerin bir listesini belirtin.<br /><br />**Yönetilen tarayıcının aşağıdaki URL'leri açmasını engelle** – Yönetilen tarayıcının açmasının engelleneceği URL'lerin bir listesini belirtin. **Not**: Aynı yönetilen tarayıcı ilkesine hem izin verilen hem de engellenen URL'leri ekleyemezsiniz.<br />Belirtebileceğiniz URL biçimleri hakkında daha fazla bilgi için, bu konudaki **İzin verilen ve engellenen URL’ler için URL biçimi** bölümüne bakın.|

4.  İşiniz bittiğinde **İlkeyi Kaydet**'e tıklayın.

Yeni ilke, **İlke** çalışma alanının **Yapılandırma İlkeleri** düğümünde görüntülenir.

## Yönetilen tarayıcı uygulaması için bir dağıtımı oluşturma
Yönetilen tarayıcı ilkesini oluşturduktan sonra, yönetilen tarayıcı uygulaması için bir yazılım dağıtımı oluşturabilir ve bunu oluşturduğunuz yönetilen tarayıcı ilkesiyle ilişkilendirebilirsiniz.

> [!IMPORTANT]
> Yönetilen tarayıcı ilkeleri diğer Intune ilkeleriyle aynı şekilde dağıtılmaz. Bu ilke türü bir yönetilen yarayıcı yazılım paketiyle ilişkilendirilmelidir.

İlkeyi uygulamayla ilişkilendirmek için **Mobil Uygulama Yönetimi** sayfasında yönetilen tarayıcı ilkesini seçtiğinizden emin olarak uygulamayı dağıtın.

Uygulamaları dağıtma hakkında daha fazla bilgi için bkz. [Microsoft Intune’da uygulamaları dağıtma](deploy-apps-in-microsoft-intune.md).

## Yönetilen tarayıcı için güvenlik ve gizlilik

-   iOS cihazlarda, kullanıcıların ziyaret ettiği süresi dolmuş veya güvenilmeyen sertifikalara sahip web siteleri açılmaz.

-   Kullanıcıların cihazlarındaki yerleşik tarayıcı için yaptıkları ayarlar yönetilen tarayıcı tarafından kullanılmaz. Bunun nedeni yönetilen tarayıcının bu ayarlara erişimi olmamasıdır.

-   Yönetilen tarayıcıyla ilişkilendirilmiş bir mobil uygulama yönetimi ilkesinde **Erişim için basit PIN gerektir** veya **Erişim için şirket kimlik bilgilerini gerektir** seçeneklerini yapılandırırsanız ve bir kullanıcı kimlik doğrulama sayfasındaki yardım bağlantısına tıklarsa, yönetilen tarayıcı ilkesinde bir engelleme listesine eklenmiş olmasından bağımsız olarak herhangi bir İnternet sitesine göz atabilir.

-   Yönetilen tarayıcı sitelere yalnızca doğrudan erişildiğinde erişimi engelleyebilir. Siteye erişmek için ara hizmetler (örneğin bir çeviri hizmeti) kullanıldığında erişimi engelleyemez.

-   Kimlik doğrulamasına izin vermek ve Intune belgelerine erişilebildiğinden emin olmak için **&#42;.microsoft.com** izin verilenler veya engellenenler listesi ayarlarının dışında tutulur ve her zaman izin verilir.

### Kullanım verilerini kapatma
Microsoft, ürün ve hizmetlerini geliştirmek için yönetilen tarayıcının performansı ve kullanımı hakkında anonim bilgileri otomatik olarak toplar, ancak kullanıcılar cihazlarındaki **Kullanım Verileri** ayarını kullanarak veri toplamayı kapatabilir. Bu verilerin toplanması üzerinde denetiminiz yoktur.

## Başvuru bilgileri

### İzin verilen ve engellenen URL'ler için URL biçimi
İzin verilenler ve engellenenler listesinde URL belirtirken kullanabileceğiniz izin verilen biçimler ve joker karakterler hakkında bilgi almak için aşağıdaki bilgileri kullanın.

-   ‘**&#42;**’ joker karakter sembolünü aşağıdaki izin verilen örnekler listesindeki kurallara uygun olarak kullanabilirsiniz.

-   Tüm URL'leri listeye eklerken başlarına **http** veya **https** önekini yazdığınızdan emin olun.

-   Adreste bağlantı noktası numaraları belirtebilirsiniz. Bir bağlantı noktası numarası belirtmezseniz, kullanılan değerler şöyle olacaktır:

    -   http için bağlantı noktası 80

    -   https için bağlantı noktası 443

    Bağlantı noktası için joker karakter kullanılması desteklenmez, örneğin, **http&colon;//www&period;contoso&period;com:*;** ve **http&colon;//www&period;contoso&period;com: /*;**

-   URL belirtirken kullanabileceğini izin verilen desenler hakkında bilgi almak için aşağıdaki tabloyu kullanın:

|URL|Ayrıntılar|Eşleşir|Eşleşmez|
    |-------|---------------|-----------|------------------|
    |http://www.contoso.com|Tek bir sayfayla eşleşir|www.contoso.com|host.contoso.com<br /><br />www.contoso.com/images<br /><br />contoso.com/|
    |http://contoso.com|Tek bir sayfayla eşleşir|contoso.com/|host.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com|
    |http://www.contoso.com/&#42;|www.contoso.com ile başlayan tüm URL'lerle eşleşir|www.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com/videos/tvshows|host.contoso.com<br /><br />host.contoso.com/images|
    |http://&#42;.contoso.com/&#42;|contoso.com altındaki tüm alt etki alanlarıyla eşleşir|developer.contoso.com/resources<br /><br />news.contoso.com/images<br /><br />news.contoso.com/videos|contoso.host.com|
    |http://www.contoso.com/images|Tek bir klasörle eşleşir|www.contoso.com/images|www.contoso.com/images/dogs|
    |http://www.contoso.com:80|Bir bağlantı noktası numarası kullanan tek bir sayfayla eşleşir|http://www.contoso.com:80||
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

### İzin verilenler ve engellenenler listeleri arasındaki çakışmalar nasıl çözümlenir?
Bir cihaza birden çok yönetilen tarayıcı ilkesi dağıtılır ve ayarlar çakışırsa, hem mod (izin verme veya engelleme) hem de URL listeleri çakışmalar için incelenir. Bir çakışma durumunda aşağıdaki davranış uygulanır:

-   İki ilkenin modu aynı ancak URL listeleri farklıysa, URL'ler cihazda uygulanmaz.

-   İki ilkenin modu farklı ancak URL listeleri aynıysa, URL'ler cihazda uygulanmaz.

-   Bir cihaz ilk defa yönetilen tarayıcı ilkelerini alıyorsa ve iki ilke çakışıyorsa, URL'ler cihazda uygulanmaz. Çakışmaları görüntülemek için **İlkeler** çalışma alanının **İlke Çakışmaları** düğümünü kullanın.

-   Bir cihaz zaten bir yönetilen tarayıcı ilkesi aldıysa ve çakışan ayarlara sahip ikinci bir ilke dağıtılıyorsa, orijinal ayarlar cihazda kalır. Çakışmaları görüntülemek için **İlkeler** çalışma alanının **İlke Çakışmaları** düğümünü kullanın.



<!--HONumber=Jul16_HO2-->


