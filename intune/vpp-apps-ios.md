---
title: "iOS toplu satın alınan uygulamaları yönetme | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Intune Azure önizlemesi: iOS mağazasından toplu satın aldığınız uygulamaları Intune’a eşitlemeyi, ardından bunların kullanımını yönetmeyi ve izlemeyi öğrenin."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 3974145b4c244e251ee91a6216a79a6d8b1ad792
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017

---

# <a name="how-to-manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Microsoft Intune ile toplu satın alma programından satın aldığınız iOS uygulamalarını yönetme


[!INCLUDE[azure_preview](./includes/azure_preview.md)]

iOS uygulama deposu, şirketinizde çalıştırmak istediğiniz uygulamanın birden çok lisansını satın almanıza olanak sağlar. Bu durum, satın alınan uygulamaların birden fazla kopyasın izlemeye yönelik yönetim yükünü azaltmanıza yardımcı olabilir.

Microsoft Intune lisans bilgilerini uygulama mağazasından içeri aktararak, kaç lisans kullandığınızı izleyerek ve sahip olduğunuzdan fazla uygulama kopyasını yüklemenizi önleyerek, bu program aracılığıyla satın aldığınız uygulamaları yönetmenize yardımcı olur.

Ayrıca, Apple toplu satın alma programı mağazasından satın aldığınız kitapları Intune ile eşitleyebilir, yönetebilir, atayabilir ve bunları kullanıcılara atayabilirsiniz. Kitapları yönetmek için Intune portalındaki **Kitaplar** iş yükünü kullanın. Kitapları yönetme yordamı, uygulama yönetme yordamı ile aynıdır.
Bunu yapmak için Apple Volume Purchase Program belirtecini karşıya yüklemeniz gerekir. Şu anda kitapları yalnızca **Gerekli** yükleme olarak atayabilirsiniz.
Bir cihaza bir kitap atadığınızda, cihazda yerleşik iBooks uygulamasının yüklü olması gerekir. Yüklü değilse, son kullanıcının kitabı okumak için uygulamayı yeniden yüklemesi gerekir. Şu anda kaldırılan yerleşik uygulamaları kurtarmak için Intune’u kullanamazsınız.


## <a name="manage-volume-purchased-apps-for-ios-devices"></a>iOS cihazları için toplu satın alınan uygulamaları yönetme
[Apple İş için Toplu Satın Alma Programı](http://www.apple.com/business/vpp/) veya [Apple Eğitim için Toplu Satın Alma Programı](http://volume.itunes.apple.com/us/store) aracılığıyla, iOS uygulamaları için birden çok lisans satın alırsınız. Buna Apple web sitesinden bir Apple VPP hesabının ayarlanması ve Apple VPP belirtecinin Intune’a yüklenmesi dahildir.  Toplu satın alma bilgilerinizi daha sonra Intune’la eşitleyebilir ve toplu satın alınan uygulama kullanımınızı izleyebilirsiniz.

## <a name="before-you-start"></a>Başlamadan önce
Başlamadan önce Apple'dan bir VPP belirteci almanız ve bunu Intune hesabınıza yüklemeniz gerekir. Ayrıca, aşağıdakileri anlamanız gerekir:

* Intune hesabınızla birden çok toplu satın alma programı belirtecini ilişkilendirebilirsiniz.
* Daha önce bir VPP belirtecini farklı bir ürünle kullandıysanız Intune ile kullanılacak yeni bir tane oluşturmanız gerekir.
* Her belirteç bir yıl için geçerlidir.
* Varsayılan olarak Intune, Apple VPP hizmetiyle günde iki kez eşitlenir. Dilediğiniz zaman bir el ile eşitleme başlatabilirsiniz.
* VPP belirtecini Intune'da içeri aktardıktan sonra aynı belirteci başka bir cihaz yönetimi çözümüne aktarmayın. Bunun yapılması lisans atama ve kullanıcı kayıtlarının kaybına neden olabilir.
* Intune ile iOS VPP kullanmaya başlamadan önce diğer mobil cihaz yönetimi (MDM) satıcıları ile oluşturulan tüm var olan VPP kullanıcı hesaplarını kaldırın. Intune bu kullanıcı hesaplarını bir güvenlik önlemi olarak Intune ile eşitlemez. Intune yalnızca Intune tarafından oluşturulan Apple VPP hizmetinden verileri eşitler.
* Intune, 256’ya kadar VPP belirtecinin eklenmesini destekler.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Apple VPP belirtecini almak ve karşıya yüklemek için

1. Azure Portal’da oturum açın.
2. **Diğer Hizmetler** > **Diğer** > **Intune**’u seçin.
3. **Intune** dikey penceresinde **Mobil uygulamalar**’ı seçin.
1.  **Mobil Uygulamalar** iş yükünde **Kurulum** > **iOS VPP Belirteçleri**’ni seçin.
2.  VPP belirteçleri listesi dikey penceresinde **Ekle**’ye tıklayın.
3.  Yeni VPP Belirteci dikey penceresinde aşağıdaki bilgileri belirtin:
    - **VPP belirteç dosyası** - Henüz kaydolmadıysanız, İş İçin Toplu Satın Alma Programı’na veya Eğitim İçin Toplu Satın Alma Programı’na kaydolun. Kaydolduktan sonra hesabınıza yönelik Apple VPP belirtecini indirin ve burada seçin.
    - **Apple Kimliği** - Toplu satın alma programıyla ilişkilendirilmiş hesabın Apple kimliğini girin.
    - **VPP hesabı türü** - **İş** veya **Eğitim**’i seçin.
4. İşiniz bittiğinde **Karşıya Yükle**‘ye tıklayın.

Belirteç, belirteçler listesi dikey penceresinde görüntülenir.


İstediğiniz zaman **Şimdi eşitle**’yi seçerek Apple tarafından tutulan verileri Intune ile eşitleyebilirsiniz.

## <a name="to-assign-a-volume-purchased-app"></a>Toplu satın alınmış bir uygulamayı atamak için

1. **Mobil Uygulamalar** iş yükünde, **Yönet** > **Lisanslı Uygulamalar**’ı seçin.
2. Uygulama listesi dikey penceresinde atamak istediğiniz uygulamayı seçin ve sonra da '**...**' > **Grupları Ata**’yı seçin.
3. <*uygulama adı*> - **Atanan Gruplar** dikey penceresinde **Yönet** > **Atanan Gruplar**’ı seçin.
4. **Grupları Ata**'yı seçin, sonra da **Grup seç** dikey penceresinde uygulamayı atamak istediğiniz Azure AD kullanıcı veya cihaz gruplarını seçin.
**Gerekli** atama eylemini seçmelisiniz. Ayrıca cihaz grubuna atamalar yalnızca Ocak 2017'den sonra oluşturulan yeni kiracılar için yapılabilir. Kiracınız bu tarihten önce oluşturulduysa ve VPP uygulamalarını cihaz gruplarına atama seçeneğini kullanamıyorsanız Intune destek ekibiyle iletişime geçin.
5. İşiniz bittikten sonra **Kaydet**’i seçin.

Uygulama atamalarını izlemenize yardımcı olacak bilgiler için bkz. [Uygulamaları izleme](apps-monitor.md).

## <a name="further-information"></a>Daha fazla bilgi

Uygulamayı **Gerekli** bir yükleme olarak atadığınızda, uygulamayı yükleyen her kullanıcı bir lisans kullanır.

Lisansı geri kazanmak için atama eylemini **Kaldır** olarak değiştirmeniz gerekir. Uygulama kaldırıldıktan sonra lisans geri kazanılır.

Uygun cihaza sahip bir kullanıcı ilk olarak bir VPP uygulaması yüklemeye çalıştığında kullanıcıdan Apple Toplu Satın Alma programına katılması istenir. Uygulama yüklemesi devam etmeden önce bunu yapmaları gerekir.

Bir VPP uygulamasını Kullanılabilir olarak atadığınızda, uygulama içeriği ve lisansı doğrudan uygulama mağazasından atanır.

