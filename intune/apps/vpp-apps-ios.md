---
title: Apple toplu satın alınan uygulamaları yönetme
titleSuffix: Microsoft Intune
description: İOS ve macOS App Store 'dan satın aldığınız uygulamaları Microsoft Intune olarak nasıl eşitleyebileceğinizi öğrenin ve ardından kullanımlarını yönetebilir ve izleyebilirsiniz.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/22/2019
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
ms.openlocfilehash: 9625243698bffc93ed969a8c2e4b06b4f3093f4d
ms.sourcegitcommit: 06a1fe83fd95c9773c011690e8520733e1c031e3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2019
ms.locfileid: "72785525"
---
# <a name="how-to-manage-ios-and-macos-apps-purchased-through-apple-volume-purchase-program-with-microsoft-intune"></a>Microsoft Intune ile Apple Volume Purchase Program aracılığıyla satın alınan iOS ve macOS uygulamalarını yönetme


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Apple, şirketinizde iOS ve macOS cihazlarında çalıştırmak istediğiniz bir uygulama için birden çok lisans satın almanızı sağlar. Birden fazla kopya satın almak, şirketinizdeki uygulamaları etkili bir şekilde yönetmenize yardımcı olur.

Microsoft Intune, bu program aracılığıyla satın aldığınız birden fazla kopyayı yönetmenize şu şekilde yardımcı olur:

- Uygulama mağazasından lisans bilgilerini raporlama.
- Kaç lisans kullandığınızı izleme.
- Uygulamanın sahip olduğunuzdan daha fazla kopyasını yüklemenizi engelleme.

Toplu satın alınan uygulamaları atamak için kullanabileceğiniz iki yöntem vardır:

## <a name="device-licensing"></a>Cihaz lisanslama

Cihazlara bir uygulama atadığınızda yalnızca bir uygulama lisansı kullanılır ve bu lisans, atadığınız cihazla ilişkili olur.

Bir cihaza toplu satın alınan uygulamalar atadığınızda, cihaz son kullanıcısının mağazaya erişmek için bir Apple kimliği belirtmesi gerekmez.

## <a name="user-licensing"></a>Kullanıcı lisanslama

Bir kullanıcıya uygulama atadığınızda yalnızca bir uygulama lisansı kullanılır ve bu lisans kullanıcıyla ilişkilendirilir. Uygulama, kullanıcının sahip olduğu 5 adede kadar cihazda çalıştırılabilir (cihaz sınırı Apple tarafından denetlenir).

Kullanıcılara toplu satın alınan uygulamalar atadığınızda, tüm son kullanıcılar mağazaya erişmek için geçerli ve benzersiz bir Apple kimliği belirtmek zorundadır.

Ayrıca, Apple Volume Purchase program (VPP) mağazasından satın aldığınız kitapları Intune ile iOS cihazlarına eşitleyebilir, yönetebilir ve atayabilirsiniz. Daha fazla bilgi için bkz. [Bir toplu satın alma programı aracılığıyla satın aldığınız iOS e-Kitaplarını yönetme](vpp-ebooks-ios.md).

## <a name="manage-volume-purchased-apps-for-ios-and-macos-devices"></a>İOS ve macOS cihazları için toplu satın alınan uygulamaları yönetme

### <a name="supports-apple-volume-purchase-program-volume-purchased-apps"></a>Apple Volume Purchase Program toplu satın alınan uygulamaları destekler

[İş Apple Volume Purchase program](https://www.apple.com/business/vpp/) veya [eğitim Apple Volume Purchase program](https://volume.itunes.apple.com/us/store)aracılığıyla iOS ve MacOS uygulamaları için birden çok lisans satın alın. Bu sürece Apple web sitesinden bir Apple VPP hesabının ayarlanması ve Apple VPP belirtecinin Intune’a yüklenmesi dahildir.  Toplu satın alma bilgilerinizi daha sonra Intune’la eşitleyebilir ve toplu satın alınan uygulama kullanımınızı izleyebilirsiniz.

### <a name="supports-business-to-business-volume-purchased-apps"></a>Işletmeden toplu satın alınan uygulamaları destekler

Ayrıca, üçüncü taraf geliştiriciler, App Store Connect 'te belirtilen Iş üyeleri için yetkili toplu satın alma programı ' na özel olarak uygulama dağıtabilir. Bu İş için VPP üyeleri, Volume Purchase Program App Store’da oturum açabilir ve uygulamalarını satın alabilir. Son kullanıcı tarafından satın alınan İş için VPP uygulamaları, kullanıcının Intune kiracılarıyla eşitlenecektir.

## <a name="before-you-start"></a>Başlamadan önce
Başlamadan önce Apple'dan bir VPP belirteci almanız ve Intune hesabınıza yüklemeniz gerekir. Ayrıca, aşağıdaki ölçütleri de anlamanız gerekir:

* Intune hesabınızla birden fazla VPP belirteci ilişkilendirebilirsiniz.
* Daha önce bir VPP belirtecini farklı bir ürünle kullandıysanız Intune ile kullanılacak yeni bir tane oluşturmanız gerekir.
* Her belirteç bir yıl için geçerlidir.
* Varsayılan olarak Intune, Apple VPP hizmetiyle günde iki kez eşitlenir. Dilediğiniz zaman bir el ile eşitleme başlatabilirsiniz.
* Intune ile Apple VPP kullanmaya başlamadan önce diğer mobil cihaz yönetimi (MDM) satıcıları ile oluşturulan mevcut tüm VPP kullanıcı hesaplarını kaldırın. Intune, bir güvenlik önlemi olarak bu kullanıcı hesaplarını Intune ile eşitlemez. Intune yalnızca Intune tarafından oluşturulan Apple VPP hizmeti verilerini eşitler.
* Intune, 256’ya kadar VPP belirtecinin eklenmesini destekler.
* Apple’ın Aygıt Kayıt Profili (DEP) programı, mobil cihaz yönetimi (MDM) kaydını otomatikleştirir. DEP kullanarak kuruluş cihazlarına dokunmadan onları yapılandırabilirsiniz. Apple’ın VPP’sinde kullandığınız program aracı hesabıyla DEP programına kaydolabilirsiniz. Apple Kayıt Programı kimliği, [Apple Dağıtım Programları](https://deploy.apple.com) web sitesinde listelenen programlara özeldir ve iTunes mağazası gibi Apple hizmetlerinde oturum açmak için kullanılamaz.
* Kullanıcı lisans modelini kullanan VPP uygulamalarını kullanıcılara veya (kullanıcı benzeşimi olan) cihazlara atadığınızda, her Intune kullanıcısının, cihazında Apple hüküm ve koşullarını kabul ettiğinde, benzersiz bir Apple kimliği ya da bir e-posta adresi ile ilişkilendirilmesi gerekir.
* Yeni bir Intune kullanıcısı için cihaz ayarladığınızda, cihazı kullanıcının benzersiz Apple kimliği veya e-posta adresi ile yapılandırdığınızdan emin olun. Apple kimliği veya e-posta adresi ve Intune kullanıcısı, benzersiz bir çift oluşturur ve en fazla beş cihazda kullanılabilir.
* Bir VPP belirtecinin aynı anda yalnızca bir Intune hesabında kullanılması desteklenir. Aynı VPP belirtecini birden çok Intune kiracısı için yeniden kullanmayın.

>[!IMPORTANT]
>VPP belirtecini Intune'da içeri aktardıktan sonra aynı belirteci başka bir cihaz yönetimi çözümüne aktarmayın. Bunun yapılması lisans atama ve kullanıcı kayıtlarının kaybına neden olabilir.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Apple VPP belirtecini almak ve karşıya yüklemek için

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Intune** bölmesinde, **Kurulum**altında **Istemci uygulamalar** > **Apple VPP belirteçleri** ' ni seçin.
4. VPP belirteçleri listesi bölmesinde **Oluştur**’u seçin.
5. **VPP belirteci oluştur** bölmesinde aşağıdaki bilgileri girin:
    - **VPP belirteç dosyası** - Henüz kaydolmadıysanız Volume Purchase Program for Business veya Education programına kaydolun. Kaydolduktan sonra hesabınıza yönelik Apple VPP belirtecini indirin ve burada seçin.
    - **Apple Kimliği** - Toplu satın alma programıyla ilişkilendirilmiş hesabın Apple kimliğini girin.
    - **Ülke/bölge** -VPP ülke/bölge deposunu seçin.  Intune, VPP uygulamalarını belirtilen VPP ülke/bölge deposundan tüm yerel ayarlar için eşitler.
        > [!WARNING]  
        > Ülke/bölge 'yi değiştirmek, bu belirteçle oluşturulan uygulamalar için Apple hizmetiyle bir sonraki eşitlemede uygulamalar meta verilerini ve mağaza URL 'sini güncelleştirir. Uygulama, yeni ülke/bölge deposunda yoksa güncelleştirilmeyecek.

    - **VPP hesabı türü** - **İş** veya **Eğitim**’i seçin.
    - **Otomatik uygulama güncelleştirmeleri** - Otomatik güncelleştirmeleri etkinleştirmek için **Açık** veya **Kapalı** olarak ayarlayın. Bu etkinleştirildiğinde Intune, uygulama mağazasındaki VPP uygulama güncelleştirmelerini algılar ve cihaz iade edildiğinde bunları cihaza otomatik olarak gönderir. Apple VPP uygulamaları için otomatik uygulama güncelleştirmeleri yalnızca **Gerekli** yükleme amacı ile dağıtılmış olan uygulamaları otomatik olarak güncelleştirir. **Kullanılabilir** yüklemede dağıtılan uygulamalar için otomatik GÜNCELLEŞTIRME, BT Yöneticisi için, uygulamanın yeni bir sürümünün kullanılabildiğini bildiren bir durum iletisi oluşturur. Bu durum iletisi, uygulama seçilerek, cihaz yüklemesi durumu seçilerek ve durum ayrıntıları denetlenerek görüntülenebilir. Kullanıcı ayrıca eski bir sürümü yüklenmiş olsa dahi uygulamanın Şirket Portalında yüklü olmadığını görecektir. Bu durumda, kullanıcı uygulamanın yeni sürümünü yüklemek için Şirket Portalı uygulamasındaki uygulama ayrıntıları ekranında **Yükle** ' ye tıklayarak uygulamayı yeniden yükleyebilir.

        > [!NOTE]
        > Otomatik uygulama güncelleştirmeleri, iOS 11,0 ve üzeri ya da macOS 10,12 ve üzeri için hem cihaz hem de Kullanıcı lisanslı uygulamalar için çalışır.
6. İşiniz bittiğinde **Oluştur**’u seçin.

Belirteç, belirteçler listesi bölmesinde görüntülenir.

İstediğiniz zaman **Şimdi eşitle**’yi seçerek Apple tarafından tutulan verileri Intune ile eşitleyebilirsiniz.

## <a name="to-assign-a-volume-purchased-app"></a>Toplu satın alınmış bir uygulamayı atamak için

1. **Intune** bölmesinde **Yönet** altında bulunan **İstemci uygulamaları** > **Uygulamalar**’ı seçin.
2. Uygulama listesi bölmesinde atamak istediğiniz uygulamayı ve daha sonra **Atamalar**’ı seçin.
3. ***Uygulama adı*** - **Atamalar** bölmesinde, **Grup ekle**’yi seçin, ardından **Grup ekle** bölmesinde bir **Atama türü** seçin ve uygulamayı atamak istediğiniz Azure AD kullanıcı veya cihaz gruplarını seçin.
5. Seçtiğiniz her grup için aşağıdaki ayarları yapılandırın:
    - **Tür** - Uygulamanın **Kullanılabilir** mi (son kullanıcılar uygulamayı Şirket Portalı’ndan indirebilir) yoksa **Gerekli** mi (son kullanıcıların cihazlarında uygulama otomatik olarak yüklenir) olacağını seçin.
    - **Lisans türü** - **Kullanıcı lisanslama** veya **Cihaz lisanslama**’yı seçin.
6. İşiniz bittikten sonra **Kaydet**’i seçin.


>[!NOTE]
>Kullanılabilir dağıtım amacı yalnızca kullanıcı grupları için desteklenir, cihaz grupları için desteklenmez. Görüntülenen uygulama listesi, bir belirteçle ilişkilendirilir. Birden çok VPP belirteci ile ilişkilendirilmiş bir uygulamanız varsa aynı uygulamanın her bir belirteç için bir kez olmak üzere birden çok kez görüntülendiğini görürsünüz.

## <a name="end-user-prompts-for-vpp"></a>VPP için Son Kullanıcı İstemleri

Son kullanıcı, birkaç senaryoda VPP uygulama yüklemesi için istem alır. Aşağıdaki tabloda bütün koşullar açıklanmıştır:

| # | Senaryo                                | Bir Apple VPP programına davet                              | Uygulama yükleme istemi | Apple kimliği istemi |
|---|--------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------|-----------------------------------|
| 1 | KCG – kullanıcı lisanslı                             | Iz                                                                                               | Iz                                           | Iz                                 |
| 2 | Şirket – kullanıcı lisanslı (denetimsiz cihaz)     | Iz                                                                                               | Iz                                           | Iz                                 |
| 3 | Şirket – kullanıcı lisanslı (denetimli cihaz)         | Iz                                                                                               | No                                           | Iz                                 |
| 4 | KCG – cihaz lisanslı                           | No                                                                                               | Iz                                           | No                                 |
| 5 | ŞİRKET – cihaz lisanslı (denetimsiz cihaz)                           | No                                                                                               | Iz                                           | No                                 |
| 6 | ŞİRKET – cihaz lisanslı (denetimli cihaz)                           | No                                                                                               | No                                           | No                                 |
| 7 | Bilgi noktası modu (denetimli cihaz) – cihaz lisanslı | No                                                                                               | No                                           | No                                 |
| 8 | Bilgi noktası modu (denetimli cihaz) – kullanıcı lisanslı   | --- | ---                                          | ---                                |

> [!Note]  
> VPP kullanıcı lisanslama kullanarak VPP uygulamalarını Bilgi Noktası modu cihazlarına atamanız önerilmez.

## <a name="revoking-app-licenses"></a>Uygulama lisanslarını iptal etme

Belirli bir cihaz, Kullanıcı veya uygulamayı temel alan tüm ilişkili iOS veya macOS toplu satın alma programı (VPP) uygulama lisanslarını iptal edebilirsiniz.  Ancak iOS ve macOS platformları arasında bazı farklılıklar vardır. 

### <a name="revoking-app-licenses-on-ios"></a>İOS 'ta uygulama lisanslarını iptal etme
Uygulamanın artık kendisine atanmış durumda olmadığını kullanıcıya bildirebilirsiniz. Ancak, bir uygulama lisansını iptal etmek ilgili VPP uygulamasını cihazdan kaldırmaz. VPP uygulamasını kaldırmak ve kullanıcı veya cihaza atanmış olan uygulama lisansını geri kazanmak için, atama eylemini **Kaldırma** olarak değiştirmeniz gerekir. Bir kullanıcıya atanan uygulamayı kaldırdığınızda Intune, kullanıcı veya cihaz lisansını geri kazanır ve uygulamayı cihazdan kaldırır. Geri kazanılan lisans sayısı, Intune'un **Uygulama** iş yükündeki **Lisanslı Uygulamalar** düğümünde yansıtılacak. Bir VPP uygulaması kaldırıldıktan ve uygulama lisansı geri kazanıladıktan sonra, uygulama lisansını başka bir kullanıcıya veya cihaza atamayı seçebilirsiniz.


### <a name="revoking-app-licenses-on-macos"></a>MacOS 'ta uygulama lisanslarını iptal etme
Uygulama lisansını iptal etmek, VPP uygulamasını cihazdan kaldırmaz. Bir kullanıcıya atanmış bir uygulama lisansını iptal ettiğinizde, Intune kullanıcı veya cihaz lisansını geri kazanır. İptal edilen lisans olan macOS uygulaması cihazda kullanılabilir durumda kalır, ancak bir lisans Kullanıcı veya cihaza yeniden atanana kadar güncelleştirilemez. Apple 'a göre, bu gibi uygulamalar 30 günlük yetkisiz kullanım süresinden sonra kaldırılır. Ancak, Apple atama **kaldırma** eylemini kullanarak Intune 'un uygulamayı kaldırması için bir yol sağlamaz. Ancak, geri kazanılan uygulama lisansını başka bir kullanıcıya veya cihaza atamayı seçebilirsiniz.

>[!NOTE]
>Bir çalışan şirketten ayrıldığında ve artık AAD gruplarının bir parçası olmadığında, Intune hem iOS hem de macOS Kullanıcı lisanslı VPP uygulama lisanslarını alacaktır.

## <a name="deleting-vpp-tokens"></a>VPP belirteçlerini silme
<!-- 820879 -->  
Konsolunu kullanarak bir Apple Volume satın alma programı (VPP) belirtecini silebilirsiniz. VPP belirteci kopya örnekleriniz olduğunda bu gerekli olabilir. Bir belirteci silmek, ilişkili uygulamaları ve atamayı da siler. Ancak bir belirteci silmek uygulama lisanslarını iptal etmez veya uygulamaları kaldırmaz. 

>[!NOTE]
>Intune, bir belirteç silindikten sonra uygulama lisanslarını iptal edemez. 

<!-- 820870 -->  
Belirli bir VPP belirteci için tüm VPP uygulamalarının lisansını iptal etmek amacıyla önce belirteçle ilişkili tüm uygulama lisanslarını iptal etmeli, ardından belirteci silmelisiniz.

## <a name="renewing-app-licenses"></a>Uygulama lisanslarını yenileme

Apple Volume Purchase Program portalından yeni belirteç indirerek ve Intune'da mevcut belirteci güncelleştirerek Apple VPP belirtecini yenileyebilirsiniz.

## <a name="deleting-a-vpp-app"></a>VPP uygulamasını silme

Şu anda bir iOS VPP uygulamasını Microsoft Intune’dan silmeniz mümkün değildir.

## <a name="assigning-custom-role-permissions-for-vpp"></a>VPP için özel rol izinleri atama

Apple VPP belirteçlerine ve VPP uygulamalarına erişim, Intune 'daki özel yönetici rollerine atanan izinler kullanılarak bağımsız olarak denetlenebilir.

* Bir Intune özel rolünün, **istemci uygulamaları** > **Apple VPP BELIRTEÇLERI**altında Apple VPP belirteçlerini yönetmesine Izin vermek için, **yönetilen uygulamalar**için izin atayın.
* Bir Intune özel rolünün, **istemci uygulamaları** > **uygulama**altındaki iOS VPP belirteçleri kullanılarak satın alınan uygulamaları yönetmesine Izin vermek için, **mobil uygulamalar**için izin atayın. 

## <a name="additional-information"></a>Ek bilgiler

Uygun cihaza sahip bir kullanıcı, bir VPP uygulamasını cihaza ilk kez yüklemeye çalıştığında, kullanıcıdan Apple Volume Purchase Program’e katılması istenir. Uygulamanın yüklenmeye devam etmesi için önce katılmaları gerekir. Apple Volume Purchase program 'a katılma daveti, kullanıcının iOS veya macOS cihazında App Store uygulamasını kullanmasını gerektirir. App Store uygulamasını devre dışı bırakmak için bir ilke ayarladıysanız, VPP uygulamaları için Kullanıcı tabanlı lisanslama çalışmaz. Çözüm, ilke kaldırılarak Uygulama Mağazası uygulamasına izin vermek veya cihaz tabanlı lisanslama kullanmaktır.

Apple, VPP belirteçleri oluşturmak ve yenilemek için doğrudan yardım sağlamaktadır. Daha fazla bilgi için Apple belgelerinin bir parçası olan [Volume Purchase Program (VPP) ile kullanıcılarınıza içerik dağıtma](https://go.microsoft.com/fwlink/?linkid=2014661) makalesine bakın. 

Intune portalında **Harici bir MDM’ye atandı** yazıyorsa, VPP belirtecini Intune’da kullanmadan önce yönetici olarak bu belirteci üçüncü taraf MDM’den kaldırmanız gerekir.

## <a name="frequently-asked-questions"></a>Sık sorulan sorular

### <a name="how-long-does-the-portal-take-to-update-the-license-count-once-an-app-is-installed-or-removed-from-the-device"></a>Bir uygulama cihaza yüklendikten veya cihazdan kaldırıldıktan sonra portalın lisansı güncelleştirmesi ne kadar sürer?
Lisans, bir uygulama yüklendikten veya kaldırıldıktan sonra birkaç saat içinde güncelleştirilir. Son kullanıcı uygulamayı cihazdan kaldırsa bile lisansın o kullanıcı veya cihaza atanmış olarak kalacağına dikkat edin.

### <a name="is-it-possible-to-oversubscribe-an-app-and-if-so-in-what-circumstance"></a>Bir uygulamaya fazla abone atamak mümkün mü ve hangi durumlarda yapılabilir?
Evet. Intune yöneticisi bir uygulamaya fazladan abone atayabilir. Örneğin yönetici, XYZ uygulaması için 100 lisans satın alıp uygulamayı 500 üyelik bir gruba hedefler. Bu durumda ilk 100 üye (kullanıcı veya cihaz) kendilerine atanan lisansı alır, kalan üyeler lisans atamasında başarısız olur.

### <a name="how-frequently-does-intune-sync-vpp-tokens-with-apple"></a>Intune, VPP belirteçlerini Apple ile ne sıklıkta eşitler?
Intune, VPP belirteçlerini ve lisansları Apple ile günde iki kez eşitler. Intune Yöneticisi **istemci uygulamaları** > **Apple VPP belirteçleri**altında el ile eşitleme başlatabilir.

## <a name="next-steps"></a>Sonraki adımlar

Uygulama atamalarını izlemenize yardımcı olacak bilgiler için bkz. [Uygulamaları izleme](apps-monitor.md).
