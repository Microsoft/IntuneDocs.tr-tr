---
title: macOS iş kolu uygulamalarını Microsoft Intune’a ekleme
titlesuffix: ''
description: macOS iş kolu (LOB) uygulamalarını Microsoft Intune’a eklemeyi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ef8008ac-8b85-4bfc-86ac-1f9fcbd3db76
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d527b36876adf29c12d3577f7dcd09416b4d5a37
ms.sourcegitcommit: 40b1d82df99f09a75a17065cdd0e84d8038f460a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "40255472"
---
# <a name="how-to-add-macos-line-of-business-lob-apps-to-microsoft-intune"></a>macOS iş kolu (LOB) uygulamalarını Microsoft Intune’a ekleme

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Bu makaledeki bilgiler macOS iş kolu uygulamalarını Microsoft Intune’a eklemenize yardımcı olabilir. İş kolu dosyanızı Microsoft Intune'a yükleyebilmek için önce *.pkg* dosyalarınızın ön işlemesini yapacak bir harici araç indirmelisiniz. *.pkg* dosyalarınızın ön işlemesi, bir macOS cihazında yapılmalıdır.

> [!NOTE]
> macOS kullanıcıları bazı yerleşik macOS uygulamalarını kaldırabilir (Stocks ve Harita gibi) ancak siz bu uygulamaları yeniden dağıtmak için Intune’u kullanamazsınız. Son kullanıcılar bu uygulamaları silerse uygulama mağazasına gidip el ile yeniden indirmeleri gerekir.

## <a name="before-your-start"></a>Başlamadan önce

İş kolu dosyanızı Microsoft Intune'a yükleyebilmek için önce *.pkg* dosyalarınızın ön işlemesini yapacak bir harici araç indirmelisiniz. *.pkg* dosyalarınızın ön işlemesi, bir macOS cihazında yapılmalıdır. Mac için Intune Uygulama Sarmalama Aracı'nı kullanarak Mac uygulamalarının Microsoft Intune tarafından yönetilmesini sağlayın.

> [!IMPORTANT]
> macOS LOB uygulamalarının Microsoft Intune'a yüklemek için yalnızca *.pkg* dosyaları kullanılabilir. *.dmg*’den *.pkg*’ye yapılan dönüştürme gibi diğer biçim dönüştürme işlemleri desteklenmez.

1. [Mac için Intune Uygulama Sarmalama Aracı](https://github.com/msintuneappsdk/intune-app-wrapping-tool-mac)'nı indirin ve çalıştırın.

    > [!NOTE]
    > **Mac için Intune Uygulama Sarmalama Aracı** bir macOS makinesinde çalıştırılmalıdır.

2. Bir *.intunemac* dosyasından *.pkg* LOB uygulama dosyasını sarmalamak için, **Mac için Intune Uygulama Sarmalama Aracı**'nın içinde `IntuneAppUtil` komutunu kullanın.<br>

    macOS için Microsoft Intune Uygulama Sarmalama Aracı'na yönelik kullanılabilecek örnek komutlar:
    
    - `IntuneAppUtil -h`<br>
    Bu komut aracın kullanım bilgilerini gösterir.
    
    - `IntuneAppUtil -c <source_file> -o <output_file> [-v]`<br>
    Bu komut, *.pkg* LOB uygulama dosyasını bir *.intunemac* dosyasına sarmalar.
    
    - `IntuneAppUtil -r <filename.intunemac> [-v]`<br>
    Bu komut, oluşturulan *.intunemac* dosyası için algılanan parametreleri ve sürümünü ayıklar.

## <a name="step-1---specify-the-software-setup-file"></a>1. Adım - Yazılım kurulum dosyasını belirtme

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Mobil uygulamalar**’ı seçin.
4. **Mobil uygulamalar** iş yükünde **Yönet** > **Uygulamalar**’ı seçin.
5. Uygulama listesinin üst kısmında **Ekle**’yi seçin.
6. **Uygulama Ekle** bölmesinde **İş kolu uygulaması**’nı seçin.

## <a name="step-2---configure-the-app-package-file"></a>Adım 2 - Uygulama paketi dosyasını yapılandırma

1. **Uygulama ekle** bölmesinde **Uygulama paketi dosyası**’nı seçin.
2. **Uygulama paketi dosyası** bölmesinde gözat düğmesini seçin ve *.intunemac* uzantısına sahip macOS yükleme dosyasını seçin.
3. İşiniz bittiğinde **Tamam**’ı seçin.


## <a name="step-3---configure-app-information"></a>Adım 3 - Uygulama bilgilerini yapılandırma

1. **Uygulama ekle** bölmesinde **Uygulama bilgileri**’ni seçin.
2. **Uygulama bilgileri** bölmesinde uygulamanızın ayrıntılarını ekleyin. Seçtiğiniz uygulamaya bağlı olarak, bölmedeki değerlerden bazıları otomatik olarak doldurulmuş olabilir:
    - **Ad** - Şirket portalında görüntülenmek üzere bir uygulama adı girin. Kullandığınız tüm uygulama adlarının benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa, uygulamalardan yalnızca biri şirket portalında kullanıcılara görüntülenir.
    - **Açıklama** - Şirket portalında kullanıcılara görüntülenmek üzere bir uygulama açıklaması girin.
    - **Yayımcı** - Uygulamanın yayımcısının adını girin.
    - **Minimum İşletim Sistemi** - Listeden uygulamanın yüklenebileceği minimum işletim sistemi sürümünü seçin. Uygulamayı daha önceki bir işletim sistemini çalıştıran cihazlara atarsanız, uygulama yüklenmez.
    - **Kategori** - Yerleşik uygulama kategorilerinden birini veya kendi oluşturduğunuz bir kategoriyi seçin. Böylelikle, şirket portalına göz atarken kullanıcıların uygulamayı bulmaları kolaylaşır.
    - **Bunu Şirket Portalı'nda öne çıkan uygulama olarak görüntüle** - Kullanıcılar uygulamalara göz atarken bu uygulamayı Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüleyin.
    - **Bilgi URL’si** - İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si**- İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici** - İsteğe bağlı olarak, uygulama geliştiricinin adını girin.
    - **Sahip** - İsteğe bağlı olarak, bu uygulamanın sahibi olarak **İK bölümü** gibi bir ad girin.
    - **Notlar** - Bu uygulamayla ilişkilendirmek isteyebileceğiniz notları girin.
    - **Logo** - Uygulamayla ilişkilendirilen bir simgeyi karşıya yükleyin. Bu, kullanıcılar şirket portalına göz atarken uygulamayla birlikte görüntülen simgedir.
3. İşiniz bittiğinde **Tamam**’ı seçin.

## <a name="step-4---finish-up"></a>Adım 4 - Bitirme

1. **Uygulama ekle** bölmesinde uygulama ayrıntılarınızı doğrulayın.
2. Uygulamayı Intune'a yüklemek için **Ekle**’yi seçin.

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](apps-deploy.md).

> [!NOTE]
> *.pkg* dosyası birden çok uygulama ve uygulama yükleyicisi içeriyorsa, cihazda tüm yüklü uygulamalar algılandığında Microsoft Intune yalnızca *uygulamanın* başarıyla yüklendiğini raporlar.

## <a name="step-5---update-a-line-of-business-app"></a>5. Adım - Bir iş kolu uygulamasını güncelleştirme

[!INCLUDE [shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

> [!NOTE]
> Intune hizmetinin yeni bir *.pkg* dosyasını cihaza başarılı bir şekilde dağıtması için, *.pkg* paketinizdeki *packageinfo* dosyasında paket `version` ve `CFBundleVersion` dizesini artırmanız gerekir.

## <a name="next-steps"></a>Sonraki adımlar

- Oluşturduğunuz uygulama, uygulamalar listesinde gösterilir. Artık seçtiğiniz gruplara bu uygulamayı atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](apps-deploy.md).

- Uygulamanızın özelliklerini ve atamasını izleme yolları hakkında daha fazla bilgi edinin. Daha fazla bilgi için bkz. [Uygulama bilgilerini ve atamalarını izleme](apps-monitor.md).

- Intune’da uygulamanızın bağlamı hakkında daha fazla bilgi edinin. Daha fazla bilgi için bkz. [Cihaz ve uygulama yaşam döngülerine genel bakış](introduction-device-app-lifecycles.md)
