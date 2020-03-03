---
title: Apple toplu satın alınan uygulamaları yönetme
titleSuffix: Microsoft Intune
description: İOS/ıpados ve macOS App Store 'dan satın aldığınız uygulamaları Microsoft Intune olarak nasıl eşitleyebileceğinizi öğrenin ve ardından kullanımlarını yönetebilir ve izleyebilirsiniz.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/26/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e3efa4a354a71846a5add46794ed853696d04560
ms.sourcegitcommit: fab685b22a010fe231b27a0c5eda34a6f22f4c8d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2020
ms.locfileid: "78216086"
---
# <a name="how-to-manage-ios-and-macos-apps-purchased-through-apple-volume-purchase-program-with-microsoft-intune"></a>Microsoft Intune ile Apple Volume Purchase Program aracılığıyla satın alınan iOS ve macOS uygulamalarını yönetme


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Apple, [Apple Business Manager](https://business.apple.com/) veya [Apple Okul Yöneticisi 'ni](https://school.apple.com/)kullanarak iOS/ıpados ve MacOS cihazlarında kuruluşunuzda kullanmak istediğiniz bir uygulama için birden çok lisans satın almanızı sağlar. Toplu satın alma bilgilerinizi daha sonra Intune’la eşitleyebilir ve toplu satın alınan uygulama kullanımınızı izleyebilirsiniz. Uygulama lisansı satın alma, şirketinizdeki uygulamaları etkin bir şekilde yönetmenize ve satın alınan uygulamaların sahipliğini ve denetimini tutmanıza yardımcı olur. 

Microsoft Intune, bu program aracılığıyla satın alınan uygulamaları yönetmenize yardımcı olur:

- Apple Business Manager 'dan indirdiğinizde bulunan konum belirteçlerini eşitleme.
- Kaç tane lisansın kullanılabilir olduğunu ve satın alınan uygulamalar için kullanıldığını izleme.
- Sahip olduğunuz lisansların sayısına kadar uygulama yüklemenize yardımcı olur.

Ayrıca, Apple Business Manager 'dan satın aldığınız kitapları Intune ile iOS/ıpados cihazlarına eşitleyebilir, yönetebilir ve atayabilirsiniz. Daha fazla bilgi için bkz. [toplu satın alma programı aracılığıyla satın aldığınız iOS/ıpados eBook 'ları yönetme](vpp-ebooks-ios.md).

## <a name="what-are-location-tokens"></a>Konum belirteçleri nedir?
Konum belirteçleri, toplu satın alma programı (VPP) belirteçleri olarak da bilinir. Bu belirteçler, Apple Business Manager kullanılarak satın alınan lisansları atamak ve yönetmek için kullanılır. İçerik yöneticileri, Apple Business Manager 'da izinlerine sahip oldukları konum belirteçleriyle lisanslar satın alabilir ve ilişkilendirebilir. Bu konum belirteçleri daha sonra Apple Business Manager 'dan indirilir ve Microsoft Intune karşıya yüklenir. Microsoft Intune, kiracı başına birden çok konum belirtecinin yüklenmesini destekler. Her belirteç bir yıl için geçerlidir.

## <a name="how-are-purchased-apps-licensed"></a>Satın alınan uygulamalar nasıl lisanslanır?
Satın alınan uygulamalar, Apple 'ın iOS/ıpados ve macOS cihazları için sunduğu iki lisans türü kullanılarak gruplara atanabilir.

|   | Cihaz lisanslama | Kullanıcı lisanslama |
|-----|------------------|----------------|
| **Uygulama Mağazası oturum açma** | Gerekli değildir. | Her son kullanıcının, App Store 'da oturum açmanız istendiğinde benzersiz bir Apple KIMLIĞI kullanması gerekir. |
| **Cihaz yapılandırması uygulama deposuna erişimi engelliyor** | Uygulamalar, Şirket Portalı kullanılarak yüklenip güncelleştirilemeyebilir. | Apple VPP 'ye katılma daveti App Store 'a erişim gerektirir. App Store 'u devre dışı bırakmak için bir ilke ayarladıysanız, VPP uygulamaları için Kullanıcı lisanslama çalışmaz. |
| **Otomatik uygulama güncelleştirmesi** | Apple VPP belirteci ayarlarında, uygulamanın **atama türünün** **gerekli**olduğu şekilde Intune Yöneticisi tarafından yapılandırıldığı gibi. <br> <br> **Atama türü** **Kayıtlı cihazlar için kullanılabiliyorsa**, kullanılabilir uygulama güncelleştirmeleri şirket portalı yüklenebilir. | Kişisel uygulama mağazası ayarları 'nda Son Kullanıcı tarafından yapılandırılır. Bu, Intune Yöneticisi tarafından yönetilemez. |
| **Kullanıcı kaydı** | Desteklenmez. | Yönetilen Apple kimlikleri kullanılarak desteklenir. |
| **Kitap** | Desteklenmez. | Desteklenen. |
| **Kullanılan lisanslar** | cihaz başına 1 lisans. Lisans cihazla ilişkilendirilir. | aynı kişisel Apple KIMLIĞINI kullanarak en fazla 5 cihaz için 1 lisans. Lisans kullanıcıyla ilişkilendirilir. <br> <br> Intune 'da kişisel bir Apple KIMLIĞIYLE ve yönetilen bir Apple KIMLIĞIYLE ilişkili bir Son Kullanıcı 2 uygulama lisansı kullanır.|
| **Lisans geçişi** | Uygulamalar, kullanıcıdan cihaz lisanslarına sessizce geçiş yapabilir. | Uygulamalar cihazdan Kullanıcı lisanslarına geçirilemez. |

> [!NOTE]  
> Şirket Portalı, Kullanıcı kayıt cihazlarına yalnızca Kullanıcı lisanslı uygulamalar yüklenebildiğinden, Kullanıcı kayıt cihazlarında cihaz lisanslı uygulamaları göstermez.

## <a name="what-app-types-are-supported"></a>Hangi uygulama türleri desteklenir?
Apple Business Manager kullanarak ortak ve özel uygulamalar satın alabilir ve dağıtabilirsiniz.
- **Mağaza uygulamaları:** Apple Business Manager 'ı kullanarak, Içerik yöneticileri App Store 'da bulunan ücretsiz ve ücretli uygulamaları satın alabilir.
- **Özel uygulamalar:** Apple Business Manager 'ı kullanarak, Içerik yöneticileri kuruluşunuza özel olarak sunulan özel uygulamalar da satın alabilir. Bu uygulamalar, doğrudan çalıştığınız geliştiriciler tarafından kuruluşunuzun özel ihtiyaçlarına göre tasarlanmıştır. [Özel uygulamaları dağıtma](https://developer.apple.com/business/custom-apps/)hakkında daha fazla bilgi edinin.

## <a name="prerequisites"></a>Önkoşullar
- Kuruluşunuz için bir [Apple Business Manager](https://business.apple.com/) veya [Apple Okul Yöneticisi](https://school.apple.com/) hesabı. 
- Bir veya daha fazla konum belirtece atanan uygulama lisansları satın alındı. 
- Konum belirteçleri indirildi. 

> [!IMPORTANT]
> - Bir konum belirteci, tek seferde yalnızca bir cihaz yönetimi çözümüyle birlikte kullanılabilir. Satın alınan uygulamaları Intune ile kullanmaya başlamadan önce, diğer mobil cihaz yönetimi (MDM) satıcısı ile kullanılan mevcut konum belirteçlerini iptal edin ve kaldırın. 
> - Konum belirteci, tek seferde yalnızca bir Intune kiracısında kullanılmak üzere desteklenir. Birden çok Intune kiracıları için aynı belirteci yeniden kullanmayın.
> - Varsayılan olarak, Intune, konum belirteçlerini günde iki kez Apple ile eşitler. Intune 'dan dilediğiniz zaman el ile eşitleme başlatabilirsiniz.
> - Konum belirtecini Intune 'a aktardıktan sonra aynı belirteci başka bir cihaz yönetimi çözümüne içeri aktarmayın. Bunun yapılması lisans atama ve kullanıcı kayıtlarının kaybına neden olabilir.

## <a name="migrate-from-volume-purchase-program-vpp-to-apps-and-books"></a>Toplu satın alma programı 'ndan (VPP) uygulama ve kitaplara geçiş
Kuruluşunuz henüz Apple Business Manager veya Apple Okul Yöneticisi 'ne geçirilmemişse, Intune 'da satın alınan uygulamaları yönetmeye devam etmeden önce [uygulama ve kitaplara geçiş yapma konusunda Apple 'ın kılavuzunu](https://support.apple.com/HT208257) gözden geçirin.

> [!IMPORTANT]
> - En iyi geçiş deneyimi için, her konum için yalnızca bir VPP satınalmacının geçişini yapın. Her Satınalmacı benzersiz bir konuma geçerse, atanan ve atanmamış tüm lisanslar, uygulamalar ve Kitaplar 'a taşınır.
> - Intune 'da var olan eski VPP belirtecini veya Intune 'da var olan eski VPP belirteciyle ilişkili uygulamaları ve atamaları silmeyin. Bu eylemler, tüm uygulama atamalarının Intune 'da yeniden oluşturulmasını gerektirir.

Mevcut satın alınan VPP içeriğini ve belirteçleri Apple Business Manager veya Apple Okul Yöneticisi ' nde bulunan uygulamalar ve Kitaplar 'a aşağıdaki gibi geçirin:

1. VPP Satınalmacılar ' ı kuruluşunuza katılarak ve her kullanıcıyı benzersiz bir konum seçmek üzere yönlendirecek şekilde davet edin. 
2. Devam etmeden önce kuruluşunuzdaki tüm VPP satınalmacıların 1. adımı tamamladığınızdan emin olun.
3. Satın alınan tüm uygulamaların ve lisansların Apple Business Manager veya Apple Okul Yöneticisi 'ndeki uygulamalara ve kitaplara geçirildiğini doğrulayın.
4. **Sunucu Belirteçlerimi** > **uygulamalar ve Kitaplar > ,** **Apple Business (veya okul) Yöneticisi** > **Ayarlar** ' a giderek yeni konum belirtecini indirin.
5. **Apple VPP belirteçlerini** > ve belirteci eşitleyerek **kiracı yönetimine** > **bağlayıcı ve belirteçlere** giderek Microsoft Endpoint Manager Yönetim Merkezi 'nde konum belirtecini güncelleştirin.

## <a name="upload-an-apple-vpp-or-location-token"></a>Apple VPP veya Location belirtecini karşıya yükleme

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
3. **Apple VPP belirteçleri** > **bağlayıcı ve belirteçler** > **Kiracı Yönetimi** ' ni seçin.
4. VPP belirteçleri listesi bölmesinde **Oluştur**’u seçin.
5. **VPP belirteci oluştur** bölmesinde aşağıdaki bilgileri girin:
    - **VPP belirteç dosyası** -henüz yapmadıysanız, Apple Business Manager veya Apple Okul Yöneticisi için kaydolun. Kaydolduktan sonra hesabınıza yönelik Apple VPP belirtecini indirin ve burada seçin.
    - **Apple Kimliği** -karşıya yüklenen belirteçle Ilişkili hesabın YÖNETILEN Apple kimliğini girin.
    - **Başka BIR MDM 'den belirteç denetimini al** -bu seçeneğin **Evet** olarak ayarlanması, belirtecin başka bir MDM çözümünden Intune 'a yeniden atanalmasına izin verir.
    - **Belirteç adı** -belirteç adını ayarlamak için bir yönetim alanı.    
    - **Ülke/bölge** -VPP ülke/bölge deposunu seçin.  Intune, VPP uygulamalarını belirtilen VPP ülke/bölge deposundan tüm yerel ayarlar için eşitler.
        > [!WARNING]  
        > Ülke/bölge 'yi değiştirmek, bu belirteçle oluşturulan uygulamalar için Apple hizmetiyle bir sonraki eşitlemede uygulamalar meta verilerini ve App Store URL 'sini güncelleştirir. Uygulama, yeni ülke/bölge deposunda yoksa güncelleştirilmeyecek.

    - **VPP hesabı türü** - **İş** veya **Eğitim**’i seçin.
    - **Otomatik uygulama güncelleştirmeleri** - Otomatik güncelleştirmeleri etkinleştirmek için **Açık** veya **Kapalı** olarak ayarlayın. Bu etkinleştirildiğinde Intune, uygulama mağazasındaki VPP uygulama güncelleştirmelerini algılar ve cihaz iade edildiğinde bunları cihaza otomatik olarak gönderir. 
        
        > [!NOTE] 
        > Apple VPP uygulamaları için otomatik uygulama güncelleştirmeleri yalnızca **Gerekli** yükleme amacı ile dağıtılmış olan uygulamaları otomatik olarak güncelleştirir. **Kullanılabilir** yüklemede dağıtılan uygulamalar için otomatik GÜNCELLEŞTIRME, BT Yöneticisi için, uygulamanın yeni bir sürümünün kullanılabildiğini bildiren bir durum iletisi oluşturur. Bu durum iletisi, uygulama seçilerek, cihaz yüklemesi durumu seçilerek ve durum ayrıntıları denetlenerek görüntülenebilir.  

    - **Microsoft 'a hem Kullanıcı hem de cihaz bilgilerini Apple 'a göndermek için izin veriyorum.** -Devam etmek için **kabul** ediyorum ' u seçmeniz gerekir. Microsoft 'un Apple 'a gönderdiği verileri gözden geçirmek için bkz. [Intune 'un Apple 'a gönderdiği veriler](~/protect/data-intune-sends-to-apple.md).

6. İşiniz bittiğinde **Oluştur**’u seçin. Belirteç, belirteçler listesi bölmesinde görüntülenir.

## <a name="synchronize-a-vpp-token"></a>VPP belirtecini eşitler
Seçilen bir belirteç için **Eşitle** ' yi seçerek, Intune 'da satın alınan uygulamalarınızın uygulama adlarını, meta verilerini ve lisans bilgilerini eşitleyebilirsiniz.

## <a name="assign-a-volume-purchased-app"></a>Toplu satın alınan bir uygulamayı atama

1. **Tüm uygulamalar** > **uygulamalar** ' ı seçin.
2. Uygulama listesi bölmesinde atamak istediğiniz uygulamayı ve daha sonra **Atamalar**’ı seçin.
3. **Uygulama adı** - **Atamalar** bölmesinde, **Grup ekle**’yi seçin, ardından **Grup ekle** bölmesinde bir **Atama türü** seçin ve uygulamayı atamak istediğiniz Azure AD kullanıcı veya cihaz gruplarını seçin.
5. Seçtiğiniz her grup için aşağıdaki ayarları yapılandırın:
    - **Tür** - Uygulamanın **Kullanılabilir** mi (son kullanıcılar uygulamayı Şirket Portalı’ndan indirebilir) yoksa **Gerekli** mi (son kullanıcıların cihazlarında uygulama otomatik olarak yüklenir) olacağını seçin.
    - **Lisans türü** - **Kullanıcı lisanslama** veya **Cihaz lisanslama**’yı seçin.
6. İşiniz bittiğinde **Kaydet**’i seçin.


>[!NOTE]
>Kullanılabilir dağıtım amacı yalnızca kullanıcı grupları için desteklenir, cihaz grupları için desteklenmez. Görüntülenen uygulama listesi, bir belirteçle ilişkilendirilir. Birden çok VPP belirteci ile ilişkilendirilmiş bir uygulamanız varsa aynı uygulamanın her bir belirteç için bir kez olmak üzere birden çok kez görüntülendiğini görürsünüz.

> [!NOTE]  
> Intune (veya bu konuyla ilgili diğer MDM), VPP uygulamalarını gerçekten yüklemez. Bunun yerine, Intune, VPP hesabınıza bağlanır ve Apple 'ın hangi cihaza atanacağını belirtir. Buradan, tüm gerçek yükleme Apple ile cihaz arasında işlenir.
> 
> [Apple MDM protokol başvurusu, sayfa 135](https://developer.apple.com/business/documentation/MDM-Protocol-Reference.pdf)

## <a name="end-user-prompts-for-vpp"></a>VPP için Son Kullanıcı İstemleri

Son kullanıcı, birkaç senaryoda VPP uygulama yüklemesi için istem alır. Aşağıdaki tabloda bütün koşullar açıklanmıştır:

| # | Senaryo                                | Bir Apple VPP programına davet                              | Uygulama yükleme istemi | Apple kimliği istemi |
|---|--------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------|-----------------------------------|
| 1. | KCG – kullanıcı lisanslı (Kullanıcı kayıt cihazı değil)                             | Y                                                                                               | Y                                           | Y                                 |
| 2 | Şirket – kullanıcı lisanslı (denetimsiz cihaz)     | Y                                                                                               | Y                                           | Y                                 |
| 3 | Şirket – kullanıcı lisanslı (denetimli cihaz)         | Y                                                                                               | N                                           | Y                                 |
| 4 | KCG – cihaz lisanslı                           | N                                                                                               | Y                                           | N                                 |
| 5 | ŞİRKET – cihaz lisanslı (denetimsiz cihaz)                           | N                                                                                               | Y                                           | N                                 |
| 6 | ŞİRKET – cihaz lisanslı (denetimli cihaz)                           | N                                                                                               | N                                           | N                                 |
| 7 | Bilgi noktası modu (denetimli cihaz) – cihaz lisanslı | N                                                                                               | N                                           | N                                 |
| 8 | Bilgi noktası modu (denetimli cihaz) – kullanıcı lisanslı   | --- | ---                                          | ---                                |

> [!Note]  
> Kullanıcı lisanslama kullanarak, VPP uygulamalarının bilgi noktası modu cihazlara atanması önerilmez.

## <a name="revoking-app-licenses"></a>Uygulama lisanslarını iptal etme

Belirli bir cihaz, Kullanıcı veya uygulamayı temel alan tüm ilişkili iOS/ıpados veya macOS toplu satın alma programı (VPP) uygulama lisanslarını iptal edebilirsiniz.  Ancak iOS/ıpados ve macOS platformları arasında bazı farklılıklar vardır. 

|   | iOS/iPadOS | Mac OS |
|-----|------------------|----------------|
| **Uygulama atamasını Kaldır** | Bir kullanıcıya atanan uygulamayı kaldırdığınızda Intune, kullanıcı veya cihaz lisansını geri kazanır ve uygulamayı cihazdan kaldırır. | Bir kullanıcıya atanmış bir uygulamayı kaldırdığınızda, Intune kullanıcı veya cihaz lisansını geri kazanır. Uygulama cihazdan kaldırılmadı. |
| **Uygulama lisansını iptal et** | Kullanıcı veya cihazdan uygulama lisansını geri kazanır bir uygulama lisansını iptal etme. Uygulamayı cihazdan kaldırmak için atamayı **kaldırmak** üzere değiştirmeniz gerekir. | Kullanıcı veya cihazdan uygulama lisansını geri kazanır bir uygulama lisansını iptal etme. İptal edilen lisans olan macOS uygulaması cihazda kullanılabilir durumda kalır, ancak bir lisans Kullanıcı veya cihaza yeniden atanana kadar güncelleştirilemez. Apple 'a göre, bu gibi uygulamalar 30 günlük yetkisiz kullanım süresinden sonra kaldırılır. Ancak, Apple atama kaldırma eylemini kullanarak Intune 'un uygulamayı kaldırması için bir yol sağlamaz.

>[!NOTE]
> - Bir çalışan şirketten ayrıldığında ve artık AAD gruplarının bir parçası olmadığında, Intune geri kazanır uygulama lisansları.
> - Satın alınan bir uygulamayı **kaldırma** amacını atarken, Intune lisansı geri kazanır ve uygulamayı kaldırır.
> - Bir cihaz, Intune yönetiminden kaldırıldığında, uygulama lisansları geri kazanılır. 

## <a name="deleting-vpp-tokens"></a>VPP belirteçlerini silme
<!-- 820879 -->  
Konsolunu kullanarak bir Apple Volume satın alma programı (VPP) belirtecini silebilirsiniz. VPP belirteci kopya örnekleriniz olduğunda bu gerekli olabilir. Bir belirteci silmek, ilişkili uygulamaları ve atamayı da siler. Ancak bir belirteci silmek uygulama lisanslarını iptal etmez veya uygulamaları kaldırmaz. 

>[!NOTE]
>Intune, bir belirteç silindikten sonra uygulama lisanslarını iptal edemez. 

<!-- 820870 -->  
Belirli bir VPP belirteci için tüm VPP uygulamalarının lisansını iptal etmek amacıyla önce belirteçle ilişkili tüm uygulama lisanslarını iptal etmeli, ardından belirteci silmelisiniz.

## <a name="renewing-app-licenses"></a>Uygulama lisanslarını yenileme

Apple Business Manager veya Apple Okul Yöneticisi 'nden yeni bir belirteç indirerek ve Intune 'da var olan belirteci güncelleştirerek bir Apple VPP belirtecini yenileyebilirsiniz.

## <a name="deleting-a-vpp-app"></a>VPP uygulamasını silme

Şu anda Microsoft Intune bir iOS/ıpados VPP uygulamasını silemezsiniz.

## <a name="assigning-custom-role-permissions-for-vpp"></a>VPP için özel rol izinleri atama

Apple VPP belirteçlerine ve VPP uygulamalarına erişim, Intune 'daki özel yönetici rollerine atanan izinler kullanılarak bağımsız olarak denetlenebilir.

* Intune özel rolünün, **Apple VPP belirteçlerini** > **uygulamalar** altında Apple VPP belirteçlerini yönetmesine Izin vermek için, **yönetilen uygulamalar**için izin atayın.
* Intune özel rolünün, **uygulamalar** > **tüm uygulamalar**' ın altında IOS/ıpados VPP belirteçleri kullanılarak satın alınan uygulamaları yönetmesine Izin vermek için, **mobil uygulamalar**için izin atayın. 

## <a name="additional-information"></a>Ek bilgiler

Apple, VPP belirteçleri oluşturmak ve yenilemek için doğrudan yardım sağlamaktadır. Daha fazla bilgi için Apple belgelerinin bir parçası olan [Volume Purchase Program (VPP) ile kullanıcılarınıza içerik dağıtma](https://go.microsoft.com/fwlink/?linkid=2014661) makalesine bakın. 

Intune portalında **Harici bir MDM’ye atandı** yazıyorsa, VPP belirtecini Intune’da kullanmadan önce yönetici olarak bu belirteci üçüncü taraf MDM’den kaldırmanız gerekir.

## <a name="frequently-asked-questions"></a>Sık sorulan sorular

### <a name="how-many-tokens-can-i-upload"></a>Kaç belirteç karşıya yükleyebilirim?
Intune 'da en fazla 3.000 belirteç yükleyebilirsiniz.

### <a name="how-long-does-the-portal-take-to-update-the-license-count-once-an-app-is-installed-or-removed-from-the-device"></a>Bir uygulama cihaza yüklendikten veya cihazdan kaldırıldıktan sonra portalın lisansı güncelleştirmesi ne kadar sürer?
Lisans, bir uygulama yüklendikten veya kaldırıldıktan sonra birkaç saat içinde güncelleştirilir. Son kullanıcı uygulamayı cihazdan kaldırsa bile lisansın o kullanıcı veya cihaza atanmış olarak kalacağına dikkat edin.

### <a name="is-it-possible-to-oversubscribe-an-app-and-if-so-in-what-circumstance"></a>Bir uygulamaya fazla abone atamak mümkün mü ve hangi durumlarda yapılabilir?
Evet. Intune yöneticisi bir uygulamaya fazladan abone atayabilir. Örneğin yönetici, XYZ uygulaması için 100 lisans satın alıp uygulamayı 500 üyelik bir gruba hedefler. Bu durumda ilk 100 üye (kullanıcı veya cihaz) kendilerine atanan lisansı alır, kalan üyeler lisans atamasında başarısız olur.


## <a name="next-steps"></a>Sonraki adımlar

Uygulama atamalarını izlemenize yardımcı olacak bilgiler için bkz. [Uygulamaları izleme](apps-monitor.md).

Uygulamayla ilgili sorunları giderme hakkında bilgi için bkz. uygulama [sorunlarını giderme](~/apps/troubleshoot-app-install.md) .
