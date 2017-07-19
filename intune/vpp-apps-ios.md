---
title: "Toplu satın alınan iOS uygulamalarını yönetme"
titleSuffix: Intune on Azure
description: "iOS mağazasından toplu satın aldığınız uygulamaları Intune’a eşitlemeyi, ardından bunların kullanımını yönetmeyi ve izlemeyi öğrenin.\""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 16b7ce81eb63a81534af2911b34904d870ac41ad
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2017
---
# <a name="how-to-manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Microsoft Intune ile toplu satın alma programından satın aldığınız iOS uygulamalarını yönetme


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

iOS uygulama deposu, şirketinizde çalıştırmak istediğiniz uygulamanın birden çok lisansını satın almanıza olanak sağlar. Bir uygulamanın birden fazla kopyasını satın almak, uygulamaların satın alınmış birden fazla kopyasını izlemenin getirdiği ek yönetim yükünü azaltmanıza yardımcı olur.

Microsoft Intune, bu program aracılığıyla satın aldığınız uygulamaları yönetmenize şu şekilde yardımcı olur:

- Uygulama mağazasından lisans bilgilerini içeri aktarma
- Kaç lisans kullandığınızı izleme
- Uygulamanın sahip olduğunuzdan daha fazla kopyasını yüklemenizi engelleme

Ayrıca, Apple Volume Purchase Program mağazasından satın aldığınız kitapları Intune ile eşitleyebilir, yönetebilir ve atayabilirsiniz. Kitapları yönetmek için Intune portalındaki **Kitaplar** iş yükünü kullanın. Kitapları yönetme yordamı, uygulama yönetme yordamı ile aynıdır.
Başlamadan önce karşıya bir Apple Volume Purchase Program belirteci yüklemiş olmanız gerekir. Şu anda kitapları yalnızca **Gerekli** yükleme olarak atayabilirsiniz.
Bir cihaza bir kitap atadığınızda, cihazda yerleşik iBooks uygulamasının yüklü olması gerekir. Yüklü değilse son kullanıcının kitabı okumak için uygulamayı yeniden yüklemesi gerekir. Şu anda kaldırılan yerleşik uygulamaları kurtarmak için Intune’u kullanamazsınız.


## <a name="manage-volume-purchased-apps-for-ios-devices"></a>iOS cihazları için toplu satın alınan uygulamaları yönetme
[Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) veya [Apple Volume Purchase Program for Education](http://volume.itunes.apple.com/us/store) aracılığıyla iOS uygulamaları için birden çok lisans satın alın. Bu sürece Apple web sitesinden bir Apple VPP hesabının ayarlanması ve Apple VPP belirtecinin Intune’a yüklenmesi dahildir.  Toplu satın alma bilgilerinizi daha sonra Intune’la eşitleyebilir ve toplu satın alınan uygulama kullanımınızı izleyebilirsiniz.

## <a name="before-you-start"></a>Başlamadan önce
Başlamadan önce Apple'dan bir VPP belirteci almanız ve Intune hesabınıza yüklemeniz gerekir. Ayrıca, aşağıdaki ölçütleri de anlamanız gerekir:

* Intune hesabınızla birden çok toplu satın alma programı belirtecini ilişkilendirebilirsiniz.
* Daha önce bir VPP belirtecini farklı bir ürünle kullandıysanız Intune ile kullanılacak yeni bir tane oluşturmanız gerekir.
* Her belirteç bir yıl için geçerlidir.
* Varsayılan olarak Intune, Apple VPP hizmetiyle günde iki kez eşitlenir. Dilediğiniz zaman bir el ile eşitleme başlatabilirsiniz.
* VPP belirtecini Intune'da içeri aktardıktan sonra aynı belirteci başka bir cihaz yönetimi çözümüne aktarmayın. Bunun yapılması lisans atama ve kullanıcı kayıtlarının kaybına neden olabilir.
* Intune ile iOS VPP kullanmaya başlamadan önce diğer mobil cihaz yönetimi (MDM) satıcıları ile oluşturulan tüm var olan VPP kullanıcı hesaplarını kaldırın. Intune, bir güvenlik önlemi olarak bu kullanıcı hesaplarını Intune ile eşitlemez. Intune yalnızca Intune tarafından oluşturulan Apple VPP hizmeti verilerini eşitler.
* Intune, 256’ya kadar VPP belirtecinin eklenmesini destekler.
* Cihaz Kayıt Profili ya da Apple Configurator aracılığıyla kaydedilmiş bir cihaz için toplu satın alınmış bir uygulamayı atarsanız yalnızca cihazları hedefleyen uygulamalar çalışır. Toplu satın alınmış uygulamaları, kullanıcı benzeşimi olmayan bir DEP cihazının kullanıcılarına hedefleyemezsiniz.
* Bir VPP belirtecinin aynı anda yalnızca bir Intune hesabında kullanılması desteklenir. Aynı VPP belirtecini birden çok Intune kiracısı için yeniden kullanmayın.
* Kullanıcı lisans modelini kullanan VPP uygulamalarını kullanıcılara veya (kullanıcı benzeşimi olan) cihazlara atadığınızda, her Intune kullanıcısının, cihazında Apple hüküm ve koşullarını kabul ettiğinde, benzersiz bir Apple kimliği ya da bir e-posta adresi ile ilişkilendirilmesi gerekir.
Yeni bir Intune kullanıcısı için bir cihaz ayarladığınızda, cihazı kullanıcının benzersiz Apple kimliği veya e-posta adresi ile yapılandırdığınızdan emin olun. Apple kimliği veya e-posta adresi ve Intune kullanıcısı, 5 adede kadar cihazda kullanılabilecek benzersiz bir çift oluşturur.


## <a name="to-get-and-upload-an-apple-vpp-token"></a>Apple VPP belirtecini almak ve karşıya yüklemek için

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **İzleme + Yönetim** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Mobil uygulamalar**’ı seçin.
1.  **Mobil Uygulamalar** iş yükünde **Kurulum** > **iOS VPP Belirteçleri**’ni seçin.
2.  VPP belirteçleri listesi dikey penceresinde **Ekle**’ye tıklayın.
3.  **Yeni VPP Belirteci** dikey penceresinde aşağıdaki bilgileri girin:
    - **VPP belirteç dosyası** - Henüz kaydolmadıysanız Volume Purchase Program for Business veya Education programına kaydolun. Kaydolduktan sonra hesabınıza yönelik Apple VPP belirtecini indirin ve burada seçin.
    - **Apple Kimliği** - Toplu satın alma programıyla ilişkilendirilmiş hesabın Apple kimliğini girin.
    - **VPP hesabı türü** - **İş** veya **Eğitim**’i seçin.
4. İşiniz bittiğinde **Karşıya Yükle**‘ye tıklayın.

Belirteç, belirteçler listesi dikey penceresinde görüntülenir.


İstediğiniz zaman **Şimdi eşitle**’yi seçerek Apple tarafından tutulan verileri Intune ile eşitleyebilirsiniz.

> [!NOTE]
> Microsoft Intune, yalnızca iTunes Store aracılığıyla herkese açık Uygulamaların bilgilerini eşitleyebilir. **iOS için Özel B2B Uygulamaları** henüz desteklenmemektedir. Senaryonuz bu tür uygulamaları hedefliyorsa uygulama bilgileri eşitlenmez.

## <a name="to-assign-a-volume-purchased-app"></a>Toplu satın alınmış bir uygulamayı atamak için

1. **Mobil Uygulamalar** iş yükünde, **Yönet** > **Lisanslı Uygulamalar**’ı seçin.
2. Uygulama listesi dikey penceresinde atamak istediğiniz uygulamayı seçin ve sonra da '**...**' > **Grupları Ata**.
3. <*uygulama adı*> - **Atanan Gruplar** dikey penceresinde **Yönet** > **Atanan Gruplar**’ı seçin.
4. **Grupları Ata**'yı seçin, sonra da **Grup seç** dikey penceresinde uygulamayı atamak istediğiniz Azure AD kullanıcı veya cihaz gruplarını seçin.
**Gerekli** atama eylemini seçmelisiniz. Ayrıca cihaz grubuna atamalar yalnızca Ocak 2017'den sonra oluşturulan yeni kiracılar için yapılabilir. Kiracınız bu tarihten önce oluşturulduysa ve cihaz gruplarına VPP uygulamaları atama seçeneğini kullanamıyorsanız Intune destekle iletişime geçin.
5. İşiniz bittikten sonra **Kaydet**’i seçin.

>[!NOTE]
>Görüntülenen uygulama listesi, bir belirteçle ilişkilendirilir. Birden çok VPP belirteci ile ilişkilendirilmiş bir uygulamanız varsa aynı uygulamanın her bir belirteç için bir kez olmak üzere birden çok kez görüntülendiğini görürsünüz.

Uygulama atamalarını izlemenize yardımcı olacak bilgiler için bkz. [Uygulamaları izleme](apps-monitor.md).

## <a name="further-information"></a>Daha fazla bilgi

Uygulamayı **Gerekli** bir yükleme olarak atadığınızda, uygulamayı yükleyen her kullanıcı bir lisans kullanır.

Lisansı geri kazanmak için atama eylemini **Kaldır** olarak değiştirmeniz gerekir. Uygulama kaldırıldıktan sonra lisans geri kazanılır.

Uygun cihaza sahip bir kullanıcı, bir VPP uygulamasını ilk kez yüklemeye çalıştığında, kullanıcıdan Apple Volume Purchase Program’e katılması istenir. Uygulamanın yüklenmeye devam etmesi için önce katılmaları gerekir. Apple Volume Purchase programına katılma daveti, kullanıcının, iOS cihazında iTunes uygulamasını kullanabilmesini gerektirir. iTunes Store uygulamasını devre dışı bırakmak için bir ilke belirlediyseniz VPP uygulamaları için kullanıcı tabanlı lisanslama çalışmaz. Çözüm, ilkeyi kaldırarak iTunes uygulamasına izin vermek veya cihaz tabanlı lisanslama kullanmaktır.

Bir VPP uygulamasını Kullanılabilir olarak atadığınızda, uygulama içeriği ve lisansı doğrudan uygulama mağazasından atanır.
