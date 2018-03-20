---
title: "iOS toplu satın alınan uygulamaları yönetme | Microsoft Docs"
titlesuffix: Azure portal
description: "iOS mağazasından toplu satın aldığınız uygulamaları Intune’a eşitlemeyi, ardından bunların kullanımını yönetmeyi ve izlemeyi öğrenin.\""
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 04a94e4baee23ac9a4a742a2ff11591087381fde
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-manage-ios-apps-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Microsoft Intune ile toplu satın alma programından satın alınan iOS uygulamalarını yönetme


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

iOS uygulama deposu, şirketinizde çalıştırmak istediğiniz uygulamanın birden çok lisansını satın almanıza olanak sağlar. Birden fazla kopya satın almak, şirketinizdeki uygulamaları etkili bir şekilde yönetmenize yardımcı olur.

Microsoft Intune, bu program aracılığıyla satın aldığınız birden fazla kopyayı yönetmenize şu şekilde yardımcı olur:

- Uygulama mağazasından lisans bilgilerini raporlama.
- Kaç lisans kullandığınızı izleme.
- Uygulamanın sahip olduğunuzdan daha fazla kopyasını yüklemenizi engelleme.

Toplu satın alınan uygulamaları atamak için kullanabileceğiniz iki yöntem vardır:

### <a name="device-licensing"></a>Cihaz lisanslama

Cihazlara bir uygulama atadığınızda yalnızca bir uygulama lisansı kullanılır ve bu lisans, atadığınız cihazla ilişkili olur.

Bir cihaza toplu satın alınan uygulamalar atadığınızda, cihaz son kullanıcısının mağazaya erişmek için bir Apple kimliği belirtmesi gerekmez.

### <a name="user-licensing"></a>Kullanıcı lisanslama

Bir kullanıcıya uygulama atadığınızda yalnızca bir uygulama lisansı kullanılır ve bu lisans kullanıcıyla ilişkilendirilir. Uygulama, kullanıcının sahip olduğu birden fazla cihazda (Apple tarafından denetlenen bir sınır ile) çalıştırılabilir.

Kullanıcılara toplu satın alınan uygulamalar atadığınızda, tüm son kullanıcılar mağazaya erişmek için geçerli ve benzersiz bir Apple kimliği belirtmek zorundadır.

Ayrıca, Apple Volume Purchase Program (VPP) mağazasından satın aldığınız kitapları Intune ile eşitleyebilir, yönetebilir ve atayabilirsiniz. Daha fazla bilgi için bkz. [Bir toplu satın alma programı aracılığıyla satın aldığınız iOS e-Kitaplarını yönetme](vpp-ebooks-ios.md).

## <a name="manage-volume-purchased-apps-for-ios-devices"></a>iOS cihazları için toplu satın alınan uygulamaları yönetme

### <a name="supports-apple-volume-purchase-program-volume-purchased-apps-for-ios-devices"></a>iOS cihazlar için Apple Volume Purchase Program ile toplu satın alınan uygulamaları destekler

[Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) veya [Apple Volume Purchase Program for Education](http://volume.itunes.apple.com/us/store) aracılığıyla iOS uygulamaları için birden çok lisans satın alın. Bu sürece Apple web sitesinden bir Apple VPP hesabının ayarlanması ve Apple VPP belirtecinin Intune’a yüklenmesi dahildir.  Toplu satın alma bilgilerinizi daha sonra Intune’la eşitleyebilir ve toplu satın alınan uygulama kullanımınızı izleyebilirsiniz.

### <a name="supports-business-to-business-volume-purchased-apps-for-ios-devices"></a>iOS cihazlar için İşletmeler Arası toplu satın alınan uygulamaları destekler

Ayrıca üçüncü taraf geliştiriciler de iTunes Connect’te belirtilen yetkilendirilmiş İş için Volume Purchase Program üyelerine özel olarak uygulama dağıtabilir. Bu İş için VPP üyeleri, Volume Purchase Program App Store’da oturum açabilir ve uygulamalarını satın alabilir. Son kullanıcı tarafından satın alınan İş için VPP uygulamaları, kullanıcının Intune kiracılarıyla eşitlenecektir.

## <a name="before-you-start"></a>Başlamadan önce
Başlamadan önce Apple'dan bir VPP belirteci almanız ve Intune hesabınıza yüklemeniz gerekir. Ayrıca, aşağıdaki ölçütleri de anlamanız gerekir:

* Intune hesabınızla birden fazla VPP belirteci ilişkilendirebilirsiniz.
* Daha önce bir VPP belirtecini farklı bir ürünle kullandıysanız Intune ile kullanılacak yeni bir tane oluşturmanız gerekir.
* Her belirteç bir yıl için geçerlidir.
* Varsayılan olarak Intune, Apple VPP hizmetiyle günde iki kez eşitlenir. Dilediğiniz zaman bir el ile eşitleme başlatabilirsiniz.
* Intune ile Apple VPP kullanmaya başlamadan önce diğer mobil cihaz yönetimi (MDM) satıcıları ile oluşturulan mevcut tüm VPP kullanıcı hesaplarını kaldırın. Intune, bir güvenlik önlemi olarak bu kullanıcı hesaplarını Intune ile eşitlemez. Intune yalnızca Intune tarafından oluşturulan Apple VPP hizmeti verilerini eşitler.
* Intune, 256’ya kadar VPP belirtecinin eklenmesini destekler.
* Apple’ın Aygıt Kayıt Profili (DEP) programı, mobil cihaz yönetimi (MDM) kaydını otomatikleştirir. DEP kullanarak kuruluş cihazlarına dokunmadan onları yapılandırabilirsiniz. Apple’ın VPP’sinde kullandığınız program aracı hesabıyla DEP programına kaydolabilirsiniz. Apple Kayıt Programı kimliği, [Apple Dağıtım Programları](https://deploy.apple.com) web sitesinde listelenen programlara özeldir ve iTunes mağazası gibi Apple hizmetlerinde oturum açmak için kullanılamaz.
* Kullanıcı lisans modelini kullanan VPP uygulamalarını kullanıcılara veya (kullanıcı benzeşimi olan) cihazlara atadığınızda, her Intune kullanıcısının, cihazında Apple hüküm ve koşullarını kabul ettiğinde, benzersiz bir Apple kimliği ya da bir e-posta adresi ile ilişkilendirilmesi gerekir. Yeni bir Intune kullanıcısı için cihaz ayarladığınızda, cihazı kullanıcının benzersiz Apple kimliği veya e-posta adresi ile yapılandırdığınızdan emin olun. Apple kimliği veya e-posta adresi ve Intune kullanıcısı, benzersiz bir çift oluşturur ve en fazla beş cihazda kullanılabilir.
* Bir VPP belirtecinin aynı anda yalnızca bir Intune hesabında kullanılması desteklenir. Aynı VPP belirtecini birden çok Intune kiracısı için yeniden kullanmayın.
* Kullanıcı lisans modelini kullanan VPP uygulamalarını kullanıcılara veya (kullanıcı benzeşimi olan) cihazlara atadığınızda, her Intune kullanıcısının, cihazında Apple hüküm ve koşullarını kabul ettiğinde, benzersiz bir Apple kimliği ya da bir e-posta adresi ile ilişkilendirilmesi gerekir.
Yeni bir Intune kullanıcısı için bir cihaz ayarladığınızda, cihazı kullanıcının benzersiz Apple kimliği veya e-posta adresi ile yapılandırdığınızdan emin olun. Apple kimliği veya e-posta adresi ve Intune kullanıcısı, benzersiz bir çift oluşturur ve bu çift beş cihaza kadar kullanılabilir.

>[!IMPORTANT]
>VPP belirtecini Intune'da içeri aktardıktan sonra aynı belirteci başka bir cihaz yönetimi çözümüne aktarmayın. Bunun yapılması lisans atama ve kullanıcı kayıtlarının kaybına neden olabilir.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Apple VPP belirtecini almak ve karşıya yüklemek için

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
1.  **Intune** bölmesinde **Kurulum** altında bulunan **Mobil uygulamalar** > **iOS VPP belirteçleri**’ni seçin.
2.  VPP belirteçleri listesi bölmesinde **Oluştur**’u seçin.
4. **VPP belirteci oluştur** bölmesinde aşağıdaki bilgileri girin:
    - **VPP belirteç dosyası** - Henüz kaydolmadıysanız Volume Purchase Program for Business veya Education programına kaydolun. Kaydolduktan sonra hesabınıza yönelik Apple VPP belirtecini indirin ve burada seçin.
    - **Apple Kimliği** - Toplu satın alma programıyla ilişkilendirilmiş hesabın Apple kimliğini girin.
    - **Ülke/Bölge** - VPP ülke mağazasını seçin.  Intune, belirtilen VPP ülke mağazasındaki tüm yerel ayarlarla VPP uygulamaları eşitler.
        > [!WARNING]  
        > Ülkeyi değiştirmek, bu belirteç ile oluşturulan uygulamalar için Apple hizmetiyle bir sonraki eşitlemede uygulamanın meta verilerini ve mağaza URL’sini güncelleştirir. Uygulama, yeni ülke mağazasında yoksa güncelleştirilmez.

    - **VPP hesabı türü** - **İş** veya **Eğitim**’i seçin.
    - **Otomatik uygulama güncelleştirmeleri** - **Açık** veya **Kapalı** olarak ayarlayın. Bu seçenek etkinleştirildiğinde Intune, cihaz bildirim yaptığında belirtilen belirteç için satın alınan tüm uygulamaları güncelleştirir.
uygulama mağazasındaki VPP uygulama güncelleştirmelerini algılayacak ve cihaz bildirim yaptığında bunları cihaza otomatik olarak gönderecektir.
4. İşiniz bittiğinde **Oluştur**’u seçin.

Belirteç, belirteçler listesi bölmesinde görüntülenir.

İstediğiniz zaman **Şimdi eşitle**’yi seçerek Apple tarafından tutulan verileri Intune ile eşitleyebilirsiniz.

## <a name="to-assign-a-volume-purchased-app"></a>Toplu satın alınmış bir uygulamayı atamak için

1.  **Intune** bölmesinde **Yönet** altında bulunan **Mobil uygulamalar** > **Uygulamalar**’ı seçin.
2.  Uygulama listesi bölmesinde atamak istediğiniz uygulamayı ve daha sonra **Atamalar**’ı seçin.
3.  ***Uygulama adı*** - **Atamalar** bölmesinde, **Grup ekle**’yi seçin, ardından **Grup ekle** bölmesinde bir **Atama türü** seçin ve uygulamayı atamak istediğiniz Azure AD kullanıcı veya cihaz gruplarını seçin.
5.  Seçtiğiniz her grup için aşağıdaki ayarları yapılandırın:
    - **Tür** - Uygulamanın **Kullanılabilir** mi (son kullanıcılar uygulamayı Şirket Portalı’ndan indirebilir) yoksa **Gerekli** mi (son kullanıcıların cihazlarında uygulama otomatik olarak yüklenir) olacağını seçin.
    - **Lisans türü** - **Kullanıcı lisanslama** veya **Cihaz lisanslama**’yı seçin.
6.  İşiniz bittikten sonra **Kaydet**’i seçin.


>[!NOTE]
>Görüntülenen uygulama listesi, bir belirteçle ilişkilendirilir. Birden çok VPP belirteci ile ilişkilendirilmiş bir uygulamanız varsa aynı uygulamanın her bir belirteç için bir kez olmak üzere birden çok kez görüntülendiğini görürsünüz.

## <a name="end-user-prompts-for-vpp"></a>VPP için Son Kullanıcı İstemleri

Son kullanıcı, birkaç senaryoda VPP uygulama yüklemesi için istem alır. Aşağıdaki tabloda bütün koşullar açıklanmıştır:

| # | Senaryo                                | Bir Apple VPP programına davet                              | Uygulama yükleme istemi | Apple kimliği istemi |
|---|--------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------|-----------------------------------|
| 1 | KCG – kullanıcı lisanslı                             | Y                                                                                               | Y                                           | Y                                 |
| 2 | Şirket – kullanıcı lisanslı (denetimsiz cihaz)     | Y                                                                                               | Y                                           | Y                                 |
| 3 | Şirket – kullanıcı lisanslı (denetimli cihaz)         | Y                                                                                               | N                                           | Y                                 |
| 4 | KCG – cihaz lisanslı                           | N                                                                                               | Y                                           | N                                 |
| 5 | ŞİRKET – cihaz lisanslı (denetimsiz cihaz)                           | N                                                                                               | Y                                           | N                                 |
| 6 | ŞİRKET – cihaz lisanslı (denetimli cihaz)                           | N                                                                                               | N                                           | N                                 |
| 7 | Bilgi noktası modu (denetimli cihaz) – cihaz lisanslı | N                                                                                               | N                                           | N                                 |
| 8 | Bilgi noktası modu (denetimli cihaz) – kullanıcı lisanslı   | --- | ---                                          | ---                                |

> [!Note]  
> VPP kullanıcı lisanslama kullanarak VPP uygulamalarını Bilgi Noktası modu cihazlarına atamanız önerilmez.

## <a name="revoking-app-licenses-and-deleting-tokens"></a>Uygulama lisanslarını iptal etme ve belirteçleri silme 

<!-- 820863 -->  
Bir veya daha fazla iOS Volume Purchase Program (VPP) uygulaması olan belirli bir cihaz için, cihazla ilişkili cihaza dayalı tüm uygulama lisanslarını iptal edersiniz. Bir uygulama lisansını iptal etmek ilgili VPP uygulamasını cihazdan kaldırmaz. Bir VPP uygulamasını kaldırmak ve bir lisansı geri kazanmak için VPP uygulamasının atama türünü **Kaldır** olarak değiştirmeniz gerekir. Bir kullanıcıya atanan uygulamayı kaldırırsanız Intune, kullanıcı veya cihaz lisansını geri kazanır ve uygulamayı cihazdan kaldırır.

>[!NOTE]
>Bir çalışan şirketten ayrıldığında ve artık AAD gruplarının bir parçası olmadığında, Intune tüm kullanıcı lisanslı iOS VPP uygulama lisanslarını alır.

<!-- 820879 -->  
Konsolu kullanarak bir iOS Volume Purchasing Program (VPP) belirtecini silebilirsiniz. VPP belirteci kopya örnekleriniz olduğunda bu gerekli olabilir. Bir belirteci silmek, ilişkili uygulamaları ve atamayı da siler. Ancak bir belirteci silmek uygulama lisanslarını iptal etmez veya uygulamaları kaldırmaz. 

>[!NOTE]
>Intune, bir belirteç silindikten sonra uygulama lisanslarını iptal edemez. 

<!-- 820870 -->  
Belirli bir VPP belirteci için tüm VPP uygulamalarının lisansını iptal etmek amacıyla önce belirteçle ilişkili tüm uygulama lisanslarını iptal etmeli, ardından belirteci silmelisiniz.

## <a name="further-information"></a>Daha fazla bilgi

Uygun cihaza sahip bir kullanıcı, bir VPP uygulamasını cihaza ilk kez yüklemeye çalıştığında, kullanıcıdan Apple Volume Purchase Program’e katılması istenir. Uygulamanın yüklenmeye devam etmesi için önce katılmaları gerekir. Apple Volume Purchase programına katılma daveti, kullanıcının, iOS cihazında iTunes uygulamasını kullanabilmesini gerektirir. iTunes Store uygulamasını devre dışı bırakmak için bir ilke belirlediyseniz VPP uygulamaları için kullanıcı tabanlı lisanslama çalışmaz. Çözüm, ilkeyi kaldırarak iTunes uygulamasına izin vermek veya cihaz tabanlı lisanslama kullanmaktır.

## <a name="next-steps"></a>Sonraki adımlar

Uygulama atamalarını izlemenize yardımcı olacak bilgiler için bkz. [Uygulamaları izleme](apps-monitor.md).
