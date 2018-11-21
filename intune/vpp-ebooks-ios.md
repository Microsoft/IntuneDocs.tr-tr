---
title: Toplu satın alınan iOS e-Kitaplarını yönetme
titlesuffix: Microsoft Intune
description: iOS mağazasından toplu satın aldığınız kitapları Intune’a eşitlemeyi, ardından bunların kullanımını yönetmeyi ve izlemeyi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f5617074-2384-4812-b913-dc94f64c0818
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: a4d40915cce17846ca2aaab29bb597c6580e8920
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52180672"
---
# <a name="how-to-manage-ios-ebooks-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Microsoft Intune ile toplu satın alma aracılığıyla satın aldığınız iOS e-Kitaplarını yönetme


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Apple Volume Purchase Program (VPP), şirketinizdeki kullanıcılara dağıtmak istediğiniz bir kitap için birden fazla lisans satın almanıza izin verir. İşletmecilik veya Eğitim mağazalarından kitap dağıtabilirsiniz.

Microsoft Intune; bu program aracılığıyla satın aldığınız kitapları eşitlemenize, yönetmenize ve atamanıza yardımcı olur. Lisans mağazadan lisans bilgileri içeri aktarabilir ve kaç lisans kullanıldığını izleyebilirsiniz.

Kitap yönetme yordamı da [VPP uygulamaları yönetiminin](vpp-apps-ios.md) benzeridir.

## <a name="manage-volume-purchased-books-for-ios-devices"></a>iOS cihazları için toplu satın alınan kitapları yönetme
iOS kitapları için çok sayıda lisansı [Apple İş İçin Volume Purchase Program](http://www.apple.com/business/vpp/) veya [Apple Eğitim İçin Volume Purchase Program](http://volume.itunes.apple.com/us/store) aracılığıyla satın alırsınız. Bu sürece Apple web sitesinden bir Apple VPP hesabının ayarlanması ve Apple VPP belirtecinin Intune’a yüklenmesi dahildir.  Daha sonra toplu satın alma bilgilerinizi Intune ile eşitleyebilir ve toplu satın alınan kitaplarınızın kullanımını izleyebilirsiniz.

## <a name="before-you-start"></a>Başlamadan önce
Başlamadan önce, Apple'dan bir VPP belirteci alın ve Intune hesabınıza yükleyin. Ek olarak:

* Intune hesabınızla en çok 256 VPP belirtecini ilişkilendirebilirsiniz.
* Daha önce bir VPP belirtecini farklı bir ürünle kullandıysanız Intune ile kullanılacak yeni bir tane oluşturmanız gerekir.
* Her belirteç bir yıl için geçerlidir.
* Varsayılan olarak Intune, Apple VPP hizmetiyle günde iki kez eşitlenir. Dilediğiniz zaman bir el ile eşitleme başlatabilirsiniz.
* VPP belirtecini Intune'da içeri aktardıktan sonra aynı belirteci başka bir cihaz yönetimi çözümüne aktarmayın. Bunun yapılması lisans atama ve kullanıcı kayıtlarının kaybına neden olabilir.
* Intune ile iOS kitaplarını kullanmaya başlamadan önce, diğer mobil cihaz yönetimi (MDM) satıcıları ile oluşturulan mevcut tüm VPP kullanıcı hesaplarını kaldırın. Intune, bir güvenlik önlemi olarak bu kullanıcı hesaplarını Intune ile eşitlemez. Intune yalnızca Intune tarafından oluşturulan Apple VPP hizmetinin verilerini eşitler.
* Bir cihaza bir kitap atadığınızda, cihazda yerleşik iBooks uygulamasının yüklü olması gerekir. Değilse, kitabı okuyabilmek için son kullanıcının uygulamayı yeniden yüklemesi gerekir. Şu anda kaldırılan yerleşik uygulamaları kurtarmak için Intune’u kullanamazsınız.
* Yalnızca Apple Volume Purchase Program sitesinden kitapları atayabilirsiniz. Şirket içinde oluşturduğunuz kitapları karşıya yükleyip, sonra atayamazsınız.
* Kitaplar henüz, uygulamalarda olduğu gibi son kullanıcı kategorilerine atanamamaktadır.
* Kitap bir kez atandıktan sonra lisansı geri kazanılamaz.
* Uygun bir cihazı olan bir kullanıcı, bir VPP kitabını yükleyebilmek için, kitabı ilk kez yüklemeden önce Apple Volume Purchase programına katılmalıdır. Ayrıca, yönetilen Apple kimlikleri olan güvenlik gruplarına da lisans atayabilirsiniz. Bunu yaparsanız, bir kitap yüklerken kullanıcıdan Apple kimliği istenmez.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Apple VPP belirtecini almak ve karşıya yüklemek için

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **İstemci uygulamaları**’nı seçin.
1.  **İstemci uygulamaları** iş yükünde **Kurulum** > **iOS VPP Belirteçleri**’ni seçin.
2.  VPP belirteçleri listesi bölmesinde **Oluştur**’a tıklayın.
3.  **Yeni VPP Belirteci** bölmesinde aşağıdaki bilgileri girin:
    - **VPP belirteç dosyası** - İş İçin Volume Purchase Program veya Eğitim İçin Volume Purchase Program’e kaydolduğunuzdan emin olun. Ardından hesabınızın Apple VPP belirtecini indirin ve buradan seçin.
    - **Apple Kimliği** - Toplu satın alma programıyla ilişkilendirilmiş hesabın Apple kimliğini girin.
    - **VPP hesabı türü** - **İş** veya **Eğitim**’i seçin.
4. İşiniz bittiğinde **Oluştur**’a tıklayın.

Belirteç, belirteçler listesi bölmesinde görüntülenir.


İstediğiniz zaman **Şimdi eşitle**’yi seçerek Apple tarafından tutulan verileri Intune ile eşitleyebilirsiniz.

## <a name="to-assign-a-volume-purchased-app"></a>Toplu satın alınmış bir uygulamayı atamak için

3. **Intune** bölmesinde **eKitaplar**'ı seçin.
1. **e-Kitaplar** iş yükünde **Yönet** > **Tüm e-Kitaplar**'ı seçin.
2. Kitap listesi bölmesinde, atamak istediğiniz kitabı ve daha sonra ‘**...**’ > **Grup Ata**’yı seçin.
3. <*kitap adı*> - **Atanan Gruplar** bölmesinde **Yönet** > **Atanan Gruplar**'ı seçin.
4. **Grupları Ata**'yı, ardından **Grup seç** bölmesinde kitabı atamak istediğiniz Azure AD gruplarını seçin. Cihaz grupları henüz desteklenmemektedir.
**Kullanılabilir** veya **Gerekli** atama eylemlerinden birini seçin. 
5. İşiniz bittikten sonra **Kaydet**’i seçin.

## <a name="next-steps"></a>Sonraki adımlar

Kitap atamalarını izlemenize yardımcı olacak bilgiler için bkz. [Uygulamaları izleme](apps-monitor.md).






