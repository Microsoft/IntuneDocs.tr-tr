---
title: macOS iş kolu uygulamalarını Microsoft Intune’a ekleme
titleSuffix: ''
description: macOS iş kolu (LOB) uygulamalarını Microsoft Intune’a ekleme hakkında bilgi edinin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/23/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ef8008ac-8b85-4bfc-86ac-1f9fcbd3db76
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c7aa6af751e5ab3e1e3cdff6b1d2e3d6693f65df
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755179"
---
# <a name="how-to-add-macos-line-of-business-lob-apps-to-microsoft-intune"></a>macOS iş kolu (LOB) uygulamalarını Microsoft Intune’a ekleme

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bu makaledeki bilgiler macOS iş kolu uygulamalarını Microsoft Intune’a eklemenize yardımcı olabilir. İş kolu dosyanızı Microsoft Intune'a yükleyebilmek için önce *.pkg* dosyalarınızın ön işlemesini yapacak bir harici araç indirmelisiniz. *.pkg* dosyalarınızın ön işlemesi, bir macOS cihazında yapılmalıdır.

> [!NOTE]
> MacOS Catalina 10,15 sürümünden başlayarak, uygulamalarınızı Intune 'a eklemeden önce, macOS LOB uygulamalarınızın önemli olup olmadığını denetleyin. LOB uygulamalarınızın geliştiricileri uygulamalarını henüz yayımlamadığı takdirde, uygulamalar kullanıcılarınızın macOS cihazlarında çalıştırılamaz. Bir uygulamanın olup olmadığını denetleme hakkında daha fazla bilgi için MacOS uygulamalarınızı ziyaret ederek [MacOS Catalina](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Notarizing-your-macOS-apps-to-prepare-for-macOS/ba-p/808579)' i hazırlayın.

> [!NOTE]
> macOS kullanıcıları bazı yerleşik macOS uygulamalarını kaldırabilir (Stocks ve Harita gibi) ancak siz bu uygulamaları yeniden dağıtmak için Intune’u kullanamazsınız. Son kullanıcılar bu uygulamaları silerse uygulama mağazasına gidip el ile yeniden indirmeleri gerekir.

## <a name="before-your-start"></a>Başlamadan önce

İş kolu dosyanızı Microsoft Intune için karşıya yüklemeden önce, bir dış aracı indirmeniz, indirilen Aracı yürütülebilir olarak işaretlemeniz ve *. pkg* dosyalarını araçla önceden işlem yapmanız gerekir. *.pkg* dosyalarınızın ön işlemesi, bir macOS cihazında yapılmalıdır. Mac için Intune Uygulama Sarmalama Aracı'nı kullanarak Mac uygulamalarının Microsoft Intune tarafından yönetilmesini sağlayın.

> [!IMPORTANT]
> *. Pkg* dosyası, bir Apple geliştirici hesabından elde edilen "Geliştirici Kimliği yükleyicisi" sertifikası kullanılarak imzalanmalıdır. macOS LOB uygulamalarının Microsoft Intune'a yüklemek için yalnızca *.pkg* dosyaları kullanılabilir. *.dmg*’den *.pkg*’ye yapılan dönüştürme gibi diğer biçim dönüştürme işlemleri desteklenmez.
>

1. [Mac Için Intune uygulama sarmalama aracı](https://github.com/msintuneappsdk/intune-app-wrapping-tool-mac)'nı indirin.

    > [!NOTE]
    > **Mac için Intune Uygulama Sarmalama Aracı** bir macOS makinesinde çalıştırılmalıdır. 

2. İndirilen Aracı yürütülebilir olarak işaretleyin:
   - Terminal uygulamasını başlatın.
   - Dizini `IntuneAppUtil` bulunduğu konum olarak değiştirin.
   - Aracı yürütülebilir hale getirmek için aşağıdaki komutu çalıştırın:<br> 
       `chmod +x IntuneAppUtil`

3. Bir *.intunemac* dosyasından *.pkg* LOB uygulama dosyasını sarmalamak için, **Mac için Intune Uygulama Sarmalama Aracı**'nın içinde `IntuneAppUtil` komutunu kullanın.<br>

    macOS için Microsoft Intune Uygulama Sarmalama Aracı'na yönelik kullanılabilecek örnek komutlar:
    > [!IMPORTANT]
    > `<source_file>` bağımsız değişkeninin `IntuneAppUtil` komutlarını çalıştırmadan önce boşluk içermediğinden emin olun.

    - `IntuneAppUtil -h`<br>
    Bu komut aracın kullanım bilgilerini gösterir.
    
    - `IntuneAppUtil -c <source_file> -o <output_file> [-v]`<br>
    Bu komut, *.pkg* LOB uygulama dosyasını bir *.intunemac* dosyasına sarmalar.
    
    - `IntuneAppUtil -r <filename.intunemac> [-v]`<br>
    Bu komut, oluşturulan *.intunemac* dosyası için algılanan parametreleri ve sürümünü ayıklar.

## <a name="select-the-app-type"></a>Uygulama türünü seçin

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Tüm uygulamalar** ** >  > ** **Ekle**' yi seçin.
3. **Uygulama türünü seçin** bölmesinde, **diğer** uygulama türleri altında **iş kolu uygulaması**' nı seçin.
4. **Seçin**’e tıklayın. **Uygulama ekleme** adımları görüntülenir.

## <a name="step-1---app-information"></a>1\. adım-uygulama bilgileri

### <a name="select-the-app-package-file"></a>Uygulama paketi dosyasını seçin

1. **Uygulama Ekle** bölmesinde **uygulama paketi dosyası seç**' e tıklayın. 
2. **Uygulama paket dosyası** bölmesinde gözat düğmesini seçin. Ardından, *. ıntunemac*uzantısına sahip bir MacOS yükleme dosyası seçin.
   Uygulama ayrıntıları görüntülenir.
3. İşiniz bittiğinde uygulamayı eklemek için **uygulama paketi dosyası** bölmesinde **Tamam** ' ı seçin.

### <a name="set-app-information"></a>Uygulama bilgilerini ayarla

1. **Uygulama bilgileri** sayfasında uygulamanızın ayrıntılarını ekleyin. Seçtiğiniz uygulamaya bağlı olarak bu bölmedeki değerlerden bazıları otomatik olarak doldurulabilir.
    - **Ad**: Uygulamanın Şirket Portalı’nda görünen adını girin. Kullandığınız tüm uygulama adlarının benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa uygulamalardan yalnızca biri Şirket Portalı’nda kullanıcılara görüntülenir.
    - **Açıklama**: Uygulama açıklamasını girin. Açıklama, Şirket Portalı’nda görünür.
    - **Yayımcı**: Uygulama yayımcısının adını girin.
    - **En Düşük İşletim Sistemi**: Listeden uygulamanın yüklenebileceği en düşük işletim sistemi sürümünü seçin. Uygulamayı daha önceki bir işletim sistemini çalıştıran cihazlara atarsanız, uygulama yüklenmez.
    - **Kategori**: Yerleşik uygulama kategorilerinden birini veya kendi oluşturduğunuz bir kategoriyi seçin. Kategoriler, kullanıcıların Şirket Portalı’na göz atarken uygulamayı daha kolay bulabilmesini sağlar.
    - **Bunu şirket portalı öne çıkan uygulama olarak göster**: kullanıcılar uygulamalara gözatarken, uygulamayı şirket portalının ana sayfasında göze çarpacak şekilde görüntüleyin.
    - **Bilgi URL’si**: İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL Şirket Portalı’nda görünür.
    - **Gizlilik URL’si**: İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL Şirket Portalı’nda görünür.
    - **Geliştirici**: İsteğe bağlı olarak, uygulama geliştiricisinin adını girin.
    - **Sahip**: İsteğe bağlı olarak uygulama sahibinin adını girin. Örneğin **İK departmanı**.
    - **Notlar**: Bu uygulamayla ilişkilendirmek istediğiniz notları girin.
    - **Logo**: Uygulamayla ilişkilendirilen bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar Şirket Portalı’na göz atarken uygulamayla birlikte görüntülenir.
2. **İleri** ' ye tıklayarak **kapsam etiketleri** sayfasını görüntüleyin.

## <a name="step-2---select-scope-tags-optional"></a>2\. adım-kapsam etiketlerini seçin (isteğe bağlı)
Intune 'da istemci uygulama bilgilerini kimlerin görebileceğini anlamak için kapsam etiketlerini kullanabilirsiniz. Kapsam etiketleri hakkında tam Ayrıntılar için bkz. [Dağıtılmış BT için rol tabanlı erişim denetimi ve kapsam etiketleri kullanma](../fundamentals/scope-tags.md).

1. İsteğe bağlı olarak uygulamanın kapsam etiketlerini eklemek için **kapsam etiketlerini Seç** ' e tıklayın. 
2. **Atamalar** sayfasını göstermek için **İleri** ' ye tıklayın.

## <a name="step-3---assignments"></a>3\. adım-atamalar

1. **Gerekli**, **Kayıtlı cihazlar için kullanılabilir**veya uygulama için Grup atamalarını **Kaldır** ' ı seçin. Daha fazla bilgi için bkz. [kullanıcıları ve cihazları düzenlemek için grup ekleme](~/fundamentals/groups-add.md) ve [Microsoft Intune olan gruplara uygulama atama](apps-deploy.md).
2. **İleri** ' ye tıklayarak **gözden geçir + oluştur** sayfasını görüntüleyin. 

## <a name="step-4---review--create"></a>4\. adım-Inceleme ve oluşturma

1. Uygulama için girdiğiniz değerleri ve ayarları gözden geçirin.
2. İşiniz bittiğinde, uygulamayı Intune 'a eklemek için **Oluştur** ' a tıklayın.

    İş kolu uygulaması için **genel bakış** dikey penceresi görüntülenir.

Oluşturduğunuz uygulama, uygulamalar listesinde görüntülenir ve burada uygulamayı seçtiğiniz gruplara atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](apps-deploy.md).

> [!NOTE]
> *.pkg* dosyası birden çok uygulama ve uygulama yükleyicisi içeriyorsa, cihazda tüm yüklü uygulamalar algılandığında Microsoft Intune yalnızca *uygulamanın* başarıyla yüklendiğini raporlar.

## <a name="update-a-line-of-business-app"></a>İş kolu uygulamasını güncelleştirme

[!INCLUDE [shared-proc-lob-updateapp](../includes/shared-proc-lob-updateapp.md)]

> [!NOTE]
> Intune hizmetinin yeni bir *.pkg* dosyasını cihaza başarılı bir şekilde dağıtması için, *.pkg* paketinizdeki *packageinfo* dosyasında paket `version` ve `CFBundleVersion` dizesini artırmanız gerekir.

## <a name="next-steps"></a>Sonraki adımlar

- Oluşturduğunuz uygulama, uygulamalar listesinde gösterilir. Artık seçtiğiniz gruplara bu uygulamayı atayabilirsiniz. Yardım için bkz. [Uygulamaları gruplara atama](apps-deploy.md).

- Uygulamanızın özelliklerini ve atamasını izleme yolları hakkında daha fazla bilgi edinin. Daha fazla bilgi için bkz. [Uygulama bilgilerini ve atamalarını izleme](apps-monitor.md).

- Intune’da uygulamanızın bağlamı hakkında daha fazla bilgi edinin. Daha fazla bilgi için bkz. [Cihaz ve uygulama yaşam döngülerine genel bakış](../fundamentals/device-lifecycle.md)
