---
title: Microsoft Intune için Win32 uygulamaları ekleme ve atama
titleSuffix: ''
description: Microsoft Intune ile Win32 uygulamaları eklemeyi, atamayı ve yönetmeyi öğrenin. Bu konu, Intune Win32 uygulaması teslim ve yönetim özelliklerine yönelik genel bir bakışın yanı sıra, Win32 uygulaması sorun giderme bilgilerini sağlar.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/21/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: efdc196b-38f3-4678-ae16-cdec4303f8d2
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: dbefd797fead7113045ee7e7655b715a0b4961fd
ms.sourcegitcommit: 32391f74241ee3289a76ccd5319fe700b800d427
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2020
ms.locfileid: "77075833"
---
# <a name="intune-standalone---win32-app-management"></a>Tek başına Intune-Win32 uygulama yönetimi

[Tek başına Intune](../fundamentals/mdm-authority-set.md) artık daha büyük Win32 uygulama yönetimi özelliklerine izin veriyor. Bulut bağlantılı müşterilerin Win32 uygulama yönetiminde Configuration Manager'ı kullanmaları mümkün olsa da, yanızca Intune kullanan müşteriler Win32 iş kolu (LOB) uygulamalarında daha fazla yönetim özelliğinden yararlanabilir. Bu konu, Intune Win32 uygulaması yönetim özelliklerine yönelik genel bir bakışın yanı sıra, sorun giderme bilgileri sağlar.

> [!NOTE]
> Bu uygulama yönetimi özelliği, Windows uygulamaları için hem 32-bit hem de 64-bit işletim sistemi mimarisini destekler.

> [!IMPORTANT]
> Win32 uygulamaları dağıtıldığında, özellikle de çok sayfalı bir Win32 uygulaması yükleyicinizin olduğu durumlarda [Intune yönetim uzantısı](../apps/intune-management-extension.md) 'nı kullanın. AutoPilot kaydı sırasında Win32 uygulamaları ve iş kolu uygulamaları yüklemesini karıştırırsanız, uygulama yüklemesi başarısız olabilir.  

## <a name="prerequisites"></a>Önkoşullar

Win32 uygulama yönetimini kullanmak için aşağıdaki ölçütleri karşıladığınızdan emin olun:

- Windows 10 sürüm 1607 veya üzeri (Enterprise, Pro ve eğitim sürümleri)
- Windows 10 istemcisi: 
  - Cihazların Azure AD 'ye katılması ve otomatik kaydı yapılmalıdır. Intune yönetim uzantısı, Azure AD 'ye katılmış, karma etki alanına katılmış, Grup İlkesi kayıtlı cihazlar desteklenir. 
  > [!NOTE]
  > Grup İlkesi kayıtlı senaryosu için Son Kullanıcı, Windows 10 cihazını birleştirmek için yerel kullanıcı hesabını kullanır. Kullanıcının AAD Kullanıcı hesabını kullanarak cihazda oturum açması ve Intune 'a kaydedilmesi gerekir. Intune yönetim uzantısı, bir PowerShell betiği veya bir Win32 uygulaması kullanıcı veya cihaza hedeflenirse, bu cihaza Intune yönetim uzantısını yükler.
- Windows uygulama boyutu uygulama başına 8 GB 'A göre belirlenir.

## <a name="prepare-the-win32-app-content-for-upload"></a>Karşıya yükleme için Win32 uygulaması içeriğini hazırlama

Windows Klasik (Win32) uygulamalarını önceden işlemek için [Microsoft Win32 Içerik hazırlığı aracını](https://go.microsoft.com/fwlink/?linkid=2065730) kullanın. Araç, uygulama yükleme dosyalarını *. ıntunewin* biçimine dönüştürür. Araç ayrıca, uygulama yükleme durumunu belirlemede Intune için gereken bazı öznitelikleri algılar. Bu aracı uygulama yükleyicisi klasöründe kullandıktan sonra, Intune konsolunda bir Win32 uygulaması oluşturabilirsiniz.

> [!IMPORTANT]
> [Microsoft Win32 içerik hazırlama aracı](https://go.microsoft.com/fwlink/?linkid=2065730) , *. ıntunewin* dosyasını oluşturduğunda tüm dosyaları ve alt klasörleri sıkıştırır. Microsoft Win32 Içerik Hazırlama Aracı 'nı yükleyici dosya ve klasörlerinden ayrı tutmanız gerekir, böylece araç veya diğer gereksiz dosya ve klasörleri *. ıntunewin* dosyanıza dahil etmeyin.

GitHub 'dan [Microsoft Win32 Içerik hazırlığı aracını](https://go.microsoft.com/fwlink/?linkid=2065730) bir zip dosyası olarak indirebilirsiniz. Daraltılmış dosya **Microsoft-Win32-Content-Prep-Tool-Master**adlı bir klasör içerir. Klasör Prep aracını, lisansı, bir Benioku dosyasını ve sürüm notlarını içerir. 

### <a name="process-flow-to-create-intunewin-file"></a>. Intunewin dosyası oluşturmak için işlem akışı

   <img alt="Process flow to create a .intunewin file" src="./media/apps-win32-app-management/prepare-win32-app.svg" width="700">

### <a name="run-the-microsoft-win32-content-prep-tool"></a>Microsoft Win32 Içerik hazırlığı aracını çalıştırma

Komut penceresinden parametre olmadan `IntuneWinAppUtil.exe` çalıştırırsanız araç, gerekli parametreleri adım adım girmek için size rehberlik eder. Ya da aşağıdaki kullanılabilir komut satırı parametrelerine göre parametreleri komuta ekleyebilirsiniz.

### <a name="available-command-line-parameters"></a>Kullanılabilir komut satırı parametreleri 

|    **Komut satırı parametresi**    |    **Açıklama**    |
|:------------------------------:|:----------------------------------------------------------:|
|    `-h`     |    Yardım    |
|    `-c <setup_folder>`     |    Tüm kurulum dosyalarının klasörü. Bu klasördeki tüm dosyalar *. ıntunewin* dosyasına sıkıştırılacaktır.    |
|    `-s <setup_file>`     |    Kurulum dosyası (*setup.exe* veya *setup.msi* gibi).    |
|    `-o <output_folder>`     |    Oluşturulan *.intunewin* dosyası için çıkış klasörü.    |
|    `-q`       |    Sessiz mod    |

### <a name="example-commands"></a>Örnek komutlar

|    **Örnek komut**    |    **Açıklama**    |
|:-----------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|    `IntuneWinAppUtil -h`    |    Bu komut aracın kullanım bilgilerini gösterir.    |
|    `IntuneWinAppUtil -c c:\testapp\v1.0 -s c:\testapp\v1.0\setup.exe -o c:\testappoutput\v1.0 -q`    |    Bu komut, belirtilen kaynak klasörden ve kurulum dosyasından `.intunewin` dosyasını oluşturur. MSI kurulum dosyası için, bu araç Intune'a gereken bilgileri alır. `-q` belirtilirse, komut sessiz modda çalıştırılır ve çıkış dosyası zaten varsa, bu dosyanın üzerine yazılır. Ayrıca, çıkış klasörü yoksa otomatik olarak oluşturulur.    |

*. Intunewin* dosyası oluştururken, kurulum klasörünün bir alt klasörüne başvurmak için gereken tüm dosyaları yerleştirin. Ardından, ihtiyacınız olan belirli bir dosyaya başvurmak için göreli bir yol kullanın. Örneğin:

**Kurulum kaynak klasörü:** *c:\testapp\v1.0*<br>
**Lisans dosyası:** *c:\testapp\v1.0\licenses\license.txt*

*Licenses\license.txt*göreli yolunu kullanarak *License. txt* dosyasına bakın.

## <a name="create-assign-and-monitor-a-win32-app"></a>Win32 uygulamasını oluşturma, atama ve izleme

İş kolu (LOB) uygulamalarına çok benzer bir biçimde, Win32 uygulamalarını da Microsoft Intune'a ekleyebilirsiniz. Bu gibi uygulamalar normalde şirket içinde veya üçüncü taraflarca yazılır. 

### <a name="process-flow-to-add-a-win32-app-to-intune"></a>Intune 'a bir Win32 uygulaması eklemek için işlem akışı

<img alt="Process flow to add a Win32 app to Intune" src="./media/apps-win32-app-management/add-win32-app.svg" width="500">

### <a name="add-a-win32-app-to-intune"></a>Intune 'a bir Win32 uygulaması ekleme

Aşağıdaki adımlar Windows uygulamasını Intune'a eklemenize yardımcı olacak yönergeler sağlar.

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Tüm uygulamalar** ** >  > ** **Ekle**' yi seçin.
3. **Uygulama türünü seçin** bölmesinde, **diğer** uygulama türleri altında **Windows uygulaması (Win32)** öğesini seçin.

    > [!IMPORTANT]
    > Microsoft Win32 Içerik hazırlığı aracının en son sürümünü kullandığınızdan emin olun. En son sürümü kullanmıyorsanız, uygulamanın Microsoft Win32 Içerik hazırlığı aracının daha eski bir sürümü kullanılarak paketlenmediğini belirten bir uyarı görürsünüz. 

4. **Seçin**’e tıklayın. **Uygulama ekleme** adımları görüntülenir.

## <a name="step-1---app-information"></a>1\. adım-uygulama bilgileri

### <a name="select-the-app-package-file"></a>Uygulama paketi dosyasını seçin

1. **Uygulama Ekle** bölmesinde **uygulama paketi dosyası seç**' e tıklayın. 
2. **Uygulama paket dosyası** bölmesinde gözat düğmesini seçin. Daha sonra *.intunewin* uzantılı bir Windows yükleme dosyası seçin.
   Uygulama ayrıntıları görüntülenir.
3. İşiniz bittiğinde, **uygulama paketi dosyası** bölmesinde **Tamam** ' ı seçin.

### <a name="set-app-information"></a>Uygulama bilgilerini ayarla

1. **Uygulama bilgileri** sayfasında uygulamanızın ayrıntılarını ekleyin. Seçtiğiniz uygulamaya bağlı olarak bu bölmedeki değerlerden bazıları otomatik olarak doldurulabilir.
    - **Ad**: Uygulamanın Şirket Portalı’nda görünen adını girin. Kullandığınız tüm uygulama adlarının benzersiz olduğundan emin olun. Aynı uygulama adı iki kez kullanılmışsa uygulamalardan yalnızca biri Şirket Portalı’nda kullanıcılara görüntülenir.
    - **Açıklama**: Uygulama açıklamasını girin. Açıklama Şirket Portalı’nda görünür.
    - **Yayımcı**: Uygulama yayıncısının adını girin.
    - **Kategori**: Yerleşik uygulama kategorilerinden birini veya kendi oluşturduğunuz bir kategoriyi seçin. Kategoriler, kullanıcıların Şirket Portalı’na göz atarken uygulamayı daha kolay bulabilmesini sağlar.
    - **Bunu şirket portalı öne çıkan uygulama olarak göster**: kullanıcılar uygulamalara gözatarken, uygulamayı şirket portalının ana sayfasında göze çarpacak şekilde görüntüleyin.
    - **Bilgi URL’si**: İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, Şirket Portalı’nda görünür.
    - **Gizlilik URL’si**: İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, Şirket Portalı’nda görünür.
    - **Geliştirici**: İsteğe bağlı olarak, uygulama geliştiricinin adını girin.
    - **Sahip**: İsteğe bağlı olarak uygulama sahibinin adını girin. Örneğin **İK departmanı**.
    - **Notlar**: Bu uygulamayla ilişkilendirmek istediğiniz notları girin.
    - **Logo**: Uygulamayla ilişkilendirilen bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar Şirket Portalı’na göz atarken uygulamayla birlikte görüntülenir.
2. **İleri** ' ye tıklayarak **Program** sayfasını görüntüleyin.

## <a name="step-2-program"></a>2\. Adım: program

1. **Program** sayfasında, uygulama için uygulama yükleme ve kaldırma komutlarını yapılandırın:
    - **Yükleme komutu**: uygulamayı yüklemek için yükleme komut satırını tamamen ekleyin. 

        Örneğin, uygulamanızın dosya adı **MyApp123**ise aşağıdakini ekleyin:<br>
        `msiexec /p “MyApp123.msp”`<p>
        Uygulama `ApplicationName.exe`ise, komut uygulamanın adı ve paket tarafından desteklenen komut bağımsız değişkenleri (anahtarlar) gelir. <br>Örneğin:<br>
        `ApplicationName.exe /quiet`<br>
        Yukarıdaki komutta, `ApplicationName.exe` paketi `/quiet` komut bağımsız değişkenini destekler.<p> 
        Uygulama paketi tarafından desteklenen belirli bağımsız değişkenler için uygulama satıcınıza başvurun.

    - **Kaldır komutu**: uygulamayı uygulamanın GUID 'ine göre kaldırmak için kaldırma komut satırını tamamen ekleyin. 

        Örneğin: `msiexec /x “{12345A67-89B0-1234-5678-000001000000}”`

    - **Davranışı yükler**: Install davranışını **sistem** veya **Kullanıcı**olarak ayarlayın.

        > [!NOTE]
        > Bir Win32 uygulamasını **Kullanıcı** veya **Sistem** bağlamında yüklenecek şekilde yapılandırabilirsiniz. **Kullanıcı** bağlamı yalnızca belirli bir kullanıcıyı ifade eder. **Sistem** bağlamı bir Windows 10 cihazın tüm kullanıcılarını ifade eder.
        >
        > Son kullanıcıların Win32 uygulamalarını yüklemek için cihazda oturum açmış olmaları gerekmez.
        > 
        > Win32 uygulaması yükleme ve kaldırma, uygulama kullanıcı bağlamında yüklenmek üzere ayarlandığında ve cihazdaki son kullanıcının yönetici ayrıcalıklarına sahip olması durumunda yönetici ayrıcalıkları altında (varsayılan olarak) yürütülür.
    
    - **Cihaz yeniden başlatma davranışı**: aşağıdaki seçeneklerden birini belirleyin:
        - **Dönüş kodlarına dayalı davranışı belirleme**: cihazı dönüş kodlarına göre yeniden başlatmak için bu seçeneği belirleyin.
        - **Belirli bir eylem yok**: MSI tabanlı uygulamaların uygulama yüklemesi sırasında cihaz yeniden başlatmalarının görüntülenmesini sağlamak için bu seçeneği belirleyin.
        - **Uygulama yükleme bir cihazın yeniden başlatılmasını zorlayabilir**: uygulama yüklemesinin yeniden başlatmalar olmadan tamamlanmasına izin vermek için bu seçeneği belirleyin.
        - **Intune zorunlu bir cihaz yeniden başlatmaya zorlayacaktır**: başarılı bir uygulama yüklemesinden sonra cihazı her zaman yeniden başlatmak için bu seçeneği belirleyin.

    - **Yükleme sonrası davranışı belirtmek için dönüş kodlarını belirtin**: uygulama yükleme yeniden deneme davranışını veya yükleme sonrası davranışını belirtmek için kullanılan dönüş kodlarını ekleyin. Dönüş kodu girdileri varsayılan olarak uygulama oluşturma işlemi sırasında eklenir. Bununla birlikte, başka dönüş kodları ekleyebilir veya mevcut dönüş kodlarını değiştirebilirsiniz.
        1. **Kod türü** sütununda, **kod türünü** aşağıdakilerden birine ayarlayın:
            - **Failed** : bir uygulama yükleme hatasını gösteren dönüş değeri.
            - **Donanımdan önyükleme** – Donanımdan önyükleme dönüş kodu, istemcide önyükleme yapılmadan sonraki Win32 uygulamalarının yüklenmesine izin vermez. 
            - **Yazılımdan önyükleme** – Yazılımdan önyükleme dönüş kodu, istemci önyüklemesine gerek kalmadan sonraki Win32 uygulamasının yüklenmesine izin verir. Geçerli uygulamanın yüklemesini tamamlamak için önyükleme gereklidir.
            - **Yeniden deneme** – Yeniden deneme dönüş koduyla aracı uygulamayı yüklemeyi üç kez dener. Her denemeden sonra 5 dakika bekler. 
            - **Başarılı** – Uygulamanın başarıyla yüklendiğini belirten dönüş kodu.
        2. Gerekirse, ek dönüş kodları eklemek için **Ekle** ' ye tıklayın veya varolan dönüş kodlarını değiştirin.
2. **İleri** ' ye tıklayarak **gereksinimler** sayfasını görüntüleyin.        

## <a name="step-3-requirements"></a>3\. Adım: gereksinimler

1. **Gereksinimler** sayfasında, uygulama yüklenmeden önce cihazların karşılaması gereken gereksinimleri belirtin:
    - **İşletim sistemi mimarisi**: Uygulamayı yüklemek için gereken mimarileri seçin.
    - **Minimum işletim sistemi**: Uygulamayı yüklemek için gereken minimum işletim sistemini seçin.
    - **Gerekli disk alanı (MB)** : İsteğe bağlı olarak, uygulamayı yüklemek için sistem sürücüsünde gereken boş disk alanını ekleyin.
    - **Gerekli fiziksel bellek (MB)** : İsteğe bağlı olarak, uygulamayı yüklemek için gereken fiziksel belleği (RAM) ekleyin.
    - **Gereken en düşük mantıksal işlemci sayısı**: İsteğe bağlı olarak, uygulamayı yüklemek için gereken en düşük mantıksal işlemci sayısını ekleyin.
    - **Gereken en düşük CPU hızı (MHz)** : İsteğe bağlı olarak, uygulamayı yüklemek için gereken en düşük CPU hızını ekleyin.
    - **Ek gereksinim kurallarını yapılandırın**: 
        1. **Gereksinim kuralı ekle** bölmesini göstermek ve ek gereksinim kurallarını yapılandırmak için **Ekle** ' ye tıklayın. Gereksinimin nasıl doğrulanacağını belirlemek için kullanacağınız kural türünü seçmek için **gereksinim türünü** seçin. Gereksinim kuralları dosya sistemi bilgilerini, kayıt defteri değerlerini veya PowerShell komut dosyalarını temel alabilir. 
            - **Dosya**: **Gereksinim türü**olarak **Dosya** ' yı seçtiğinizde, gereksinim kuralı bir dosya veya klasör, tarih, sürüm veya boyut algılamamalıdır. 
                - **Yol** – Algılanacak dosya veya klasörün bulunduğu klasörün tam yolu.
                - **Dosya veya klasör** - Algılanacak dosya veya klasör.
                - **Özellik** : uygulamanın varlığını doğrulamak için kullanılan kural türünü seçin.
                - **64 bit istemciler üzerinde bir 32 bit uygulamayla ilişkilendirildi** - Tüm yol ortam değişkenlerini 64 bit istemciler üzerinde 32 bit bağlamında genişletmek için **Evet**'i seçin. Tüm yol değişkenlerini 64 bit istemciler üzerinde 64 bit bağlamında genişletmek için **Hayır**'ı (varsayılan) seçin. 32 bit istemciler her zaman 32 bit bağlamını kullanır.
            - **Kayıt defteri**: **Gereksinim türü**olarak **kayıt defteri** ' ni seçtiğinizde, gereksinim kuralı değer, dize, tamsayı veya sürüme göre bir kayıt defteri ayarı tespit etmelidir.
                - **Anahtar yolu** – Algılanacak değerin bulunduğu kayıt defteri girdisinin tam yolu.
                - **Değer adı** - Algılanacak kayıt defteri değerinin adı. Bu değer boşsa algılama anahtarda gerçekleştirilir. Algılama yöntemi dosya veya klasör varlığından farklı bir yöntemse, algılama değeri olarak anahtarın (varsayılan) değeri kullanılır.
                - **Kayıt defteri anahtarı gereksinimi** – gereksinim kuralının nasıl doğrulanacağını belirlemek için kullanılan kayıt defteri anahtarı karşılaştırma türünü seçin.
                - **64 bit istemciler üzerinde bir 32 bit uygulamayla ilişkilendirildi** - 64 bit istemcilerde 32 bit kayıt defterinde arama yapmak için **Evet**'i seçin. 64 bit istemcilerde 64 bit kayıt defterinde arama yapmak için **Hayır**'ı (varsayılan) seçin. 32 bit istemcilerde her zaman 32 bit kayıt defterinde arama yapılır.
            - **Komut dosyası**: Intune konsolunda kullanabileceğiniz dosya, kayıt defteri veya başka bir yöntemi temel alan bir gereksinim kuralı oluştur, **Gereksinim türü**olarak **komut dosyasını** seçin.
                - **Betik dosyası** – PowerShell betiği tabanlı gereksinim kuralı için, var olan kod 0 Ise, stdout 'ı daha ayrıntılı olarak algılayacağız. Örneğin, STDOUT değerini 1 değeri olan bir tamsayı olarak tespit edebilirsiniz.
                - **Komut dosyasını 64 bit istemcilerde 32 bitlik işlem olarak çalıştır** -betiği, 64 bit istemcilerde bir 32 bit işlemde çalıştırmak için **Evet** ' i seçin. Komut dosyasını 64 bit istemcilerde 64 bitlik bir işlemde çalıştırmak için **Hayır** (varsayılan) seçeneğini belirleyin. 32 bitlik istemciler betiği 32 bit bir işlemde çalıştırır.
                - **Bu betiği oturum açmış oturum açma kimlik bilgilerini kullanarak Çalıştır**: komut dosyasını oturum açan cihaz kimlik bilgilerini * * kullanarak çalıştırmak için **Evet** ' i seçin.
                - **Betik imzası denetimini zorla** - Betiğin güvenilen bir yayımcı tarafından imzalandığını doğrulamak için **Evet**'i seçin. Bu doğrulama betiğin hiçbir uyarı veya istem gösterilmeden çalıştırılmasına olanak tanır. Betik engellenmeden çalıştırılır. Betiği imza doğrulaması yapılmadan son kullanıcının onayıyla çalıştırmak için **Hayır**'ı (varsayılan) seçin.
                - **Çıkış verisi türünü seçin**: bir gereksinim kuralı eşleşmesi belirlenirken kullanılan veri türünü seçin.
        2. Gereksinim kurallarını ayarlamayı tamamladığınızda **Tamam**' ı seçin.
2. **İleri** ' ye tıklayarak **algılama kuralları** sayfasını görüntüleyin.   

## <a name="step-4-detection-rules"></a>4\. Adım: algılama kuralları

1. **Algılama kuralları** sayfasında, uygulamanın varlığını algılamak için kuralları yapılandırın:
    
    **Kurallar biçimi**: uygulama varlığının nasıl algılanacağını seçin. Algılama kurallarını el ile yapılandırmayı seçebileceğiniz gibi uygulamanın varlığını algılamak için özel bir betik de kullanabilirsiniz. En az bir algılama kuralı seçmelisiniz. 

    > [!NOTE]
    > **Algılama kuralları** bölmesinde birden fazla kural eklemeyi seçebilirsiniz. Uygulamanı algılanması için **tüm** kuralların koşullarına uyulmalıdır.
    >
    > Intune, uygulamanın cihazda mevcut olmadığını algılarsa, uygulamayı 24 saat sonra yeniden sunar. Bu, yalnızca gerekli amaca yönelik uygulamalar için oluşur.

    - **Algılama kurallarını el ile yapılandırın** - Şu kural türlerinden birini seçebilirsiniz:
        1. **MSI** – MSI sürüm denetimine dayanarak doğrulayın. Bu seçenek tek bir kez eklenebilir. Bu kural türünü seçtiğinizde iki ayarınız olur:
            - **MSI ürün kodu** – Uygulama için geçerli bir MSI ürün kodu ekleyin.
            - **MSI ürün sürümü denetimi** – MSI ürün koduna ek olarak MSI ürün sürümünü doğrulamak için **Evet**'i seçin.
        2. **Dosya** – Dosya veya klasör algılama, tarih, sürüm veya boyut temelinde doğrulayın.
            - **Yol** – Algılanacak dosya veya klasörün bulunduğu klasörün tam yolu.
            - **Dosya veya klasör** - Algılanacak dosya veya klasör.
            - **Algılama yöntemi** – Uygulamanın varlığını doğrulamak için kullanılan algılama yönteminin türünü seçin.
            - **64 bit istemciler üzerinde bir 32 bit uygulamayla ilişkilendirildi** - Tüm yol ortam değişkenlerini 64 bit istemciler üzerinde 32 bit bağlamında genişletmek için **Evet**'i seçin. Tüm yol değişkenlerini 64 bit istemciler üzerinde 64 bit bağlamında genişletmek için **Hayır**'ı (varsayılan) seçin. 32 bit istemciler her zaman 32 bit bağlamını kullanır.
            
            **Dosya tabanlı algılama örnekleri**
            1. Dosyanın varlığını denetleyin.
         
                ![Algılama kuralı bölmesi - dosya varlığı ekran görüntüsü](./media/apps-win32-app-management/apps-win32-app-03.png)
        
            2. Klasör varlığını denetleyin.
         
                ![Algılama kuralı bölmesi - klasör varlığı ekran görüntüsü](./media/apps-win32-app-management/apps-win32-app-04.png)
        
        3. **Kayıt defteri** – Değer, dize, tamsayı veya sürüm temelinde doğrulayın.
            - **Anahtar yolu** – Algılanacak değerin bulunduğu kayıt defteri girdisinin tam yolu.
            - **Değer adı** - Algılanacak kayıt defteri değerinin adı. Bu değer boşsa algılama anahtarda gerçekleştirilir. Algılama yöntemi dosya veya klasör varlığından farklı bir yöntemse, algılama değeri olarak anahtarın (varsayılan) değeri kullanılır.
            - **Algılama yöntemi** – Uygulamanın varlığını doğrulamak için kullanılan algılama yönteminin türünü seçin.
            - **64 bit istemciler üzerinde bir 32 bit uygulamayla ilişkilendirildi** - 64 bit istemcilerde 32 bit kayıt defterinde arama yapmak için **Evet**'i seçin. 64 bit istemcilerde 64 bit kayıt defterinde arama yapmak için **Hayır**'ı (varsayılan) seçin. 32 bit istemcilerde her zaman 32 bit kayıt defterinde arama yapılır.
            
            **Kayıt defteri temelinde algılama örnekleri**
            1. Kayıt defteri anahtarının varlığını denetleyin.
            
                ![Algılama kuralı bölmesi - kayıt defteri anahtarı var ekran görüntüsü](./media/apps-win32-app-management/apps-win32-app-05.png)    
            
            2. Kayıt defteri değerinin var olup olmadığını denetleyin.
        
                ![Algılama kuralı bölmesi - kayıt defteri değeri varlığı ekran görüntüsü](./media/apps-win32-app-management/apps-win32-app-06.png)    
        
            3. Kayıt defteri değer dizesinin eşitliğini denetleyin.
        
                ![Algılama kuralı bölmesi - kayıt defteri değer dizesi eşittir ekran görüntüsü](./media/apps-win32-app-management/apps-win32-app-07.png)    
     
    - **Özel algılama betiği kullan** – Bu uygulamayı algılamak için kullanılacak PowerShell betiğini belirtin. 
    
       1. **Betik dosyası** – İstemcide uygulamanın varlığını algılayacak PowerShell betiğini seçin. Betik hem 0 değerinde çıkış kodu döndürdüğünde hem de STDOUT'a bir dize değeri yazdığında uygulama algılanır.

       2. **Komut dosyasını 64 bit istemcilerde 32 bitlik işlem olarak çalıştır** -betiği, 64 bit istemcilerde bir 32 bit işlemde çalıştırmak için **Evet** ' i seçin. Komut dosyasını 64 bit istemcilerde 64 bitlik bir işlemde çalıştırmak için **Hayır** (varsayılan) seçeneğini belirleyin. 32 bitlik istemciler betiği 32 bit bir işlemde çalıştırır.

       3. **Betik imzası denetimini zorla** - Betiğin güvenilen bir yayımcı tarafından imzalandığını doğrulamak için **Evet**'i seçin. Bu doğrulama betiğin hiçbir uyarı veya istem gösterilmeden çalıştırılmasına olanak tanır. Betik engellenmeden çalıştırılır. Betiği imza doğrulaması yapılmadan son kullanıcının onayıyla çalıştırmak için **Hayır**'ı (varsayılan) seçin.
    
            Intune Aracısı, komut dosyasının sonuçlarını denetler. Betik tarafından standart çıkış (STDOUT) akışına, standart hata (STDERR) akışına ve çıkış koduna yazılan değerleri okur. Betikten sıfırdan farklı bir değerle çıkılırsa, betik başarısız olur ve uygulama algılama durumu Yüklü Değil olur. Çıkış kodu sıfırsa ve STDOUT veri içeriyorsa, uygulama algılama durumu Yüklü'dür. 

            > [!NOTE]
            > Microsoft, betiğinizi UTF-8 olarak kodlamayı önerir. Betikten 0 değeriyle çıkılırsa, betiğin yürütülmesi başarılı olmuştur. İkinci çıkış kanalı uygulamanın algılandığını gösterir - STDOUT verileri uygulamanın istemcide bulunduğunu gösterir. STDOUT akışından belirli bir dize beklemeyiz.

2. Kurallarınızı ekledikten sonra, **Bağımlılıklar** sayfasını göstermek için **İleri** ' yi seçin.

## <a name="step-5-dependencies"></a>5\. Adım: bağımlılıklar

Uygulama bağımlılıkları, Win32 uygulamanızın yüklenebilmesi için yüklenmesi gereken uygulamalardır. Diğer uygulamaların bağımlılık olarak yüklenmesini zorunlu kılabilirsiniz. Özellikle, cihazın Win32 uygulamasını yüklemeden önce bağımlı uygulamaları yüklemesi gerekir. Dahil edilen bağımlılıkların bağımlılıklarını ve uygulamanın kendisini içeren en fazla 100 bağımlılığı vardır. Win32 uygulaması bağımlılıklarını yalnızca Win32 uygulamanız eklendikten ve Intune 'a yüklendikten sonra ekleyebilirsiniz. Win32 uygulamanız eklendikten sonra, Win32 uygulamanızın bölmesinde **Bağımlılıklar** seçeneğini görürsünüz. 

Herhangi bir Win32 uygulaması bağımlılığının de bir Win32 uygulaması olması gerekir. Tek MSI LOB uygulamaları veya Mağaza uygulamaları gibi diğer uygulama türlerine bağlı olarak desteklenmez.

Uygulama bağımlılığı eklerken, uygulama adı ve yayımcı temelinde arama yapabilirsiniz. Ek olarak, eklenen bağımlılıklarınızı uygulama adı ve yayımcıya göre sıralayabilirsiniz. Daha önce eklenen uygulama bağımlılıkları, eklenen uygulama bağımlılığı listesinde seçilemez. 

Her bağımlı uygulamanın otomatik olarak yüklenip yüklenmeyeceğini seçebilirsiniz. Varsayılan olarak, **otomatik olarak install** seçeneği her bağımlılık için **Evet** olarak ayarlanır. Bağımlı uygulama kullanıcı veya cihaza hedeflenmese bile, bağımlı uygulamayı otomatik olarak yükleyerek Intune, Win32 uygulamanızı yüklemeden önce bağımlılığı karşılamak üzere uygulamayı cihaza yükler. Bir bağımlılık özyinelemeli alt bağımlılıklara sahip olabileceğini ve ana bağımlılığı yüklemeden önce her bir alt bağımlılığın yükleneceğini unutmayın. Ayrıca, bağımlılıkların yüklenmesi belirli bir bağımlılık düzeyinde bir yükleme sırasına uymuyor.

### <a name="select-the-dependencies"></a>Bağımlılıkları seçin

**Bağımlılıklar** sayfasında, Win32 uygulamanızın yüklenebilmesi için yüklenmesi gereken uygulamaları seçin:
1. **Bağımlılık Ekle** bölmesini göstermek için **Ekle** ' ye tıklayın.
3. Bağımlı uygulamaları ekledikten sonra **Seç**' e tıklayın.
4. **Otomatik olarak install** sütununun altında **Evet** veya **Hayır** ' ı seçerek bağımlı uygulamanın otomatik olarak yüklenip yüklenmeyeceğini seçin.
5. **İleri** ' ye tıklayarak **kapsam etiketleri** sayfasını görüntüleyin.

### <a name="understand-additional-dependency-details"></a>Ek bağımlılık ayrıntılarını anlayın

Son Kullanıcı, bağımlı uygulamaların Win32 uygulama yükleme işleminin bir parçası olarak indirilmekte olduğunu ve yüklendiğini belirten Windows bildirim bildirimleri ' ni görür. Ayrıca, bağımlı bir uygulama yüklü olmadığında, son kullanıcı genellikle aşağıdaki bildirimlerden birini görür:
- 1 veya daha fazla bağımlı uygulama yüklenemedi
- 1 veya daha fazla bağımlı uygulama gereksinimi karşılanmadı
- 1 veya daha fazla bağımlı uygulama, cihaz yeniden başlatma bekliyor

**Otomatik olarak** bir bağımlılık yüklememeyi seçerseniz, Win32 uygulama yüklemesi denenmez. Ayrıca, uygulama raporlama bağımlılığın `failed` olarak işaretlenip işaretlenmediğini gösterir ve ayrıca bir hata nedeni sağlar. Win 32 uygulama [yükleme ayrıntılarında](troubleshoot-app-install.md#win32-app-installation-troubleshooting)belirtilen bir hataya (veya uyarıya) tıklayarak bağımlılık yükleme hatasını görüntüleyebilirsiniz. 

Her bağımlılık, Intune Win32 uygulaması yeniden deneme mantığına uyar (5 dakika bekledikten sonra 3 kez yüklemeyi deneyin) ve küresel yeniden değerlendirme zamanlaması. Ayrıca, bağımlılıklar yalnızca cihaza Win32 uygulamasını yükleme sırasında uygulanabilir. Bağımlılıklar bir Win32 uygulamasını kaldırmak için geçerli değildir. Bir bağımlılığı silmek için, bağımlılık listesi satırının sonunda bulunan bağımlı uygulamanın solundaki üç noktaya (üç nokta) tıklamalısınız. 

## <a name="step-6---select-scope-tags-optional"></a>6\. adım-kapsam etiketlerini seçin (isteğe bağlı)
Intune 'da istemci uygulama bilgilerini kimlerin görebileceğini anlamak için kapsam etiketlerini kullanabilirsiniz. Kapsam etiketleri hakkında tam Ayrıntılar için bkz. [Dağıtılmış BT için rol tabanlı erişim denetimi ve kapsam etiketleri kullanma](../fundamentals/scope-tags.md).

1. İsteğe bağlı olarak uygulamanın kapsam etiketlerini eklemek için **kapsam etiketlerini Seç** ' e tıklayın. 
2. **Atamalar** sayfasını göstermek için **İleri** ' ye tıklayın.

## <a name="step-7---assignments"></a>7\. adım-atamalar

**Kayıtlı cihazlar Için** **gerekli**olan, kullanılabilir olan cihazları seçebilir veya uygulama için Grup atamalarını **kaldırabilirsiniz** . Daha fazla bilgi için bkz. [kullanıcıları ve cihazları düzenlemek için grup ekleme](~/fundamentals/groups-add.md) ve [Microsoft Intune olan gruplara uygulama atama](apps-deploy.md).

1. Belirli bir uygulama için bir atama türü seçin:
    - **Gerekli**: Uygulama, seçili gruplardaki cihazlara yüklenir.
    - **Kayıtlı cihazlar için bulunur**: Kullanıcılar, Şirket Portalı uygulamasından veya Şirket Portalı web sitesinden uygulamayı yükler.
    - **Kaldırma**: Uygulama, seçilen gruplardaki cihazlardan kaldırılır.
2. **Grup Ekle** ' ye tıklayın ve bu uygulamayı kullanacak grupları atayın.
3. **Grupları seçin** bölmesinde, kullanıcılara veya cihazlara göre ata ' yı seçin. 
4. Gruplarınızı seçtikten sonra, **Son Kullanıcı bildirimleri**, **kullanılabilirliği**ve **yükleme son tarihini**de ayarlayabilirsiniz. Daha fazla bilgi için bkz. [Win32 uygulama kullanılabilirliğini ve bildirimlerini ayarlama](~/apps/apps-win32-app-management.md#set-win32-app-availability-and-notifications).
5. Herhangi bir kullanıcı grubunu bu uygulama atamasından etkilenmeden dışlamak istiyorsanız, **mod** sütununun altına **dahil** ' ı seçin. **Atama düzenleme** bölmesi görüntülenir. **Modunun** **dışlandığından** **dahil** edilmesini sağlayabilirsiniz. **Atama düzenleme** bölmesini kapatmak için **Tamam** ' ı tıklatın.
6. Uygulamalar için atamaları ayarlamayı tamamladıktan sonra, **gözden geçir + oluştur** sayfasını göstermek için **İleri** ' ye tıklayın.

## <a name="step-8---review--create"></a>8\. adım-Inceleme + oluştur

1. Uygulama için girdiğiniz değerleri ve ayarları gözden geçirin. Uygulama bilgilerini doğru yapılandırdığınızdan emin olun.
2. İşiniz bittiğinde, uygulamayı Intune 'a eklemek için **Oluştur** ' a tıklayın.

    İş kolu uygulaması için **genel bakış** dikey penceresi görüntülenir.

Bu noktada, Intune 'a bir Win32 uygulaması ekleme adımlarını tamamladınız. Uygulama atama ve izleme hakkında bilgi için bkz. [Microsoft Intune ile uygulamaları gruplara atama](apps-deploy.md) ve [Microsoft Intune ile uygulama bilgilerini ve atamalarını izleme](apps-monitor.md).

## <a name="delivery-optimization"></a>Teslim Iyileştirme

Windows 10 1709 ve üzeri istemciler, Windows 10 istemcisindeki bir teslim iyileştirme bileşeni kullanarak Intune Win32 uygulama içeriğini indirecek. Teslim iyileştirme, varsayılan olarak açık olan eşler arası işlevsellik sağlar. Teslim iyileştirme, Grup İlkesi ve Intune cihaz yapılandırması aracılığıyla yapılandırılabilir. Daha fazla bilgi için bkz. [Windows 10 Için teslim iyileştirmesi](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization). 

> [!NOTE]
> Ayrıca, Intune Win32 uygulama içeriğini önbelleğe almak için Configuration Manager dağıtım noktalarınıza Microsoft bağlı önbellek sunucusu yükleyebilirsiniz. Daha fazla bilgi için bkz. [Microsoft bağlı önbelleği Configuration Manager-Intune Win32 uygulamaları Için destek](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/microsoft-connected-cache#bkmk_intune).

## <a name="install-required-and-available-apps-on-devices"></a>Gerekli ve kullanılabilir uygulamaları cihazlara yükleme

Son Kullanıcı, gerekli ve kullanılabilir uygulama yüklemeleri için Windows bildirimleri görüntülenir. Aşağıdaki resimde, cihaz yeniden başlatılana kadar uygulama yüklemesinin tamamlanmayacağına ilişkin bildirim örneği gösterilir. 

![Uygulama yüklemesi için Windows bildirim bildirimlerinin ekran görüntüsü](./media/apps-win32-app-management/apps-win32-app-08.png)    

Aşağıdaki görüntüde, son kullanıcıya cihazda uygulama değişikliklerinin yapıldığını bildirir.

![Kullanıcıya uygulama değişikliklerinin yapıldığını bildiren ekran görüntüsü](./media/apps-win32-app-management/apps-win32-app-09.png)    

## <a name="set-win32-app-availability-and-notifications"></a>Win32 uygulama kullanılabilirliğini ve bildirimlerini ayarlama
Bir Win32 uygulaması için başlangıç saatini ve son tarih saatini yapılandırabilirsiniz. Başlangıç zamanında, Intune yönetim uzantısı uygulama içeriğini indirmeyi başlatacak ve gerekli amaç için önbelleğe alacak. Uygulama son tarihte yüklenecektir. Kullanılabilir uygulamalar için, uygulama Şirket Portalı görünür olduğunda başlangıç zamanı görüntülenir ve Son Kullanıcı uygulamayı Şirket Portalı istediğinde içerik indirilir. Ayrıca, yeniden başlatma yetkisiz kullanım süresini de etkinleştirebilirsiniz. 

Aşağıdaki adımları kullanarak, gerekli bir uygulama için bir tarih ve saate göre uygulama kullanılabilirliğini ayarlayın:

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.
2. **Tüm uygulamalar** > **uygulamalar** ' ı seçin.
3. Listeden var olan bir **Windows uygulaması (Win32)** seçin. 
4. Uygulama bölmesinden **Özellikler** ' i seçin > **atamalar** bölümünün yanındaki **Düzenle** ' yi seçin > **gerekli** atama türünün altına **Grup ekleyin** . 
   Uygulama kullanılabilirliği atama türüne göre ayarlanılabileceğini unutmayın. **Atama türü** **gerekli**, **Kayıtlı cihazlar için kullanılabilir**veya **kaldırma**olabilir.
5. Uygulamaya atanacak kullanıcı grubunu belirtmek için **Grup Seç** bölmesinde bir grup seçin. 

    > [!NOTE]
    > **Atama türü** seçenekleri şunları içerir:<br>
    > - **Gerekli**: **Bu uygulamayı tüm kullanıcılar için gerekli hale getirme** ve/veya **Bu uygulamayı tüm cihazlarda gerekli hale**getirme seçeneğini belirleyebilirsiniz.<br>
    > - **Kayıtlı cihazlar Için kullanılabilir**: **Bu uygulamayı kayıtlı cihazları olan tüm kullanıcılar için kullanılabilir**hale getirme seçeneğini belirleyebilirsiniz.<br>
    > - **Kaldır**: ***Bu uygulamayı tüm kullanıcılar için Kaldır** ve/veya **Bu uygulamayı tüm cihazlar için Kaldır**seçeneğini belirleyebilirsiniz.

6. **Son Kullanıcı bildirim** seçeneklerini değiştirmek için **tüm bildirim bildirimlerini göster**' i seçin.
7. **Atama düzenleme** bölmesinde, bu **Kullanıcı bildirimlerini** **tüm bildirim bildirimlerini gösterecek**şekilde ayarlayın. **Son Kullanıcı bildirimlerini** **tüm bildirim bildirimlerini göstermek**, **bilgisayar yeniden başlatmaları için bildirimleri göstermek**veya **Tüm bildirimleri gizlemek**için ayarlayabileceğinizi unutmayın.
8. **Uygulama kullanılabilirliğini** **belirli bir tarih ve saate** ayarlayın ve Tarih ve saati seçin. Bu tarih ve saat, uygulamanın son kullanıcılar cihazına ne zaman indirildiğini belirtir. 
9. **Uygulama yükleme son tarihini** **belirli bir tarih ve saate** ayarlayın ve Tarih ve saati seçin. Bu tarih ve saat, uygulamanın son kullanıcılar cihazında yüklü olduğunu belirtir. Aynı kullanıcı veya cihaz için birden çok atama yapıldığında, uygulama yüklemesinin son tarihi, mümkün olan en erken zamana göre çekilir.

10. **Yeniden başlatma yetkisiz kullanım süresinin**yanında **etkin** ' e tıklayın. Yeniden başlatma yetkisiz kullanım süresi, cihazda uygulama yüklemesi tamamlandıktan hemen sonra başlar. Devre dışı bırakıldığında, cihaz uyarı vermeden yeniden başlatılabilir. <br>Aşağıdaki seçenekleri özelleştirebilirsiniz:
    - **Cihaz yeniden başlatma yetkisiz kullanım süresi (dakika)** : varsayılan değer 1440 dakikadır (24 saat). Bu değer en fazla 2 hafta olabilir.
    - **Yeniden başlatma işleminin (dakika) ardından yeniden başlatma geri sayımı iletişim kutusunun ne zaman gösterileceğini seçin (dakika)** : varsayılan değer 15 dakikadır.
    - **Kullanıcının yeniden başlatma bildirimini yeniden görüntülemesine Izin ver**: **Evet** veya **Hayır**seçeneğini belirleyebilirsiniz.
        - **Erteleme süresini (dakika) seçin**: varsayılan değer 240 dakikadır (4 saat). Erteleme değeri, yeniden başlatma yetkisiz kullanım süresinden daha fazla olamaz.

11. **Gözden geçir + kaydet**' e tıklayın.

## <a name="toast-notifications-for-win32-apps"></a>Win32 uygulamaları için bildirim bildirimleri 
Gerekirse, uygulama ataması başına Son Kullanıcı bildirim bildirimlerinin gösterilmesini gizleyebilirsiniz. Intune 'da, **uygulamalar** > **tüm uygulamalar** ' ı seçin > **grupları Ekle** > > **atamaları** seçin. 

> [!NOTE]
> Kaydı kaldırılan cihazlardaki Intune yönetim uzantısıyla yüklenmiş olan Win32 uygulamaları kaldırılmaz. Yöneticiler, KCG cihazlarına Win32 uygulamalarını sunmamak amacıyla bunları atamadan hariç tutma seçeneğini değerlendirebilir.

## <a name="troubleshoot-win32-app-issues"></a>Win32 uygulamasında sorun giderme
İstemci makinesindeki aracı günlükleri genellikle `C:\ProgramData\Microsoft\IntuneManagementExtension\Logs` yolunda bulunur. Bu günlük dosyalarını görüntülemek için `CMTrace.exe` dosyasından yararlanabilirsiniz. Daha fazla bilgi için bkz. [CMTrace](https://docs.microsoft.com/configmgr/core/support/cmtrace).

![İstemci makinesindeki aracı günlüklerinin ekran görüntüsü](./media/apps-win32-app-management/apps-win32-app-10.png)    

> [!IMPORTANT]
> LOB Win32 uygulamalarının düzgün yüklenmesine ve yürütülmesine izin vermek için, kötü amaçlı yazılımdan koruma ayarları aşağıdaki dizinlerin taranmasını hariç tutmalıdır:<p>
> **X64 istemci makinelerde**:<br>
> *C:\Program Files (x86) \Microsoft Intune Management Extension\Content*<br>
> *C:\windows\ımecache*
>  
> **X86 istemci makinelerde**:<br>
> *C:\Program Files\Microsoft Intune yönetim Extension\Content*<br>
> *C:\windows\ımecache*

### <a name="detecting-the-win32-app-file-version-using-powershell"></a>PowerShell kullanarak Win32 uygulama dosyası sürümü algılanıyor

Win32 uygulama dosyası sürümünü algılamayla karşılaşıyorsanız, aşağıdaki PowerShell komutunu kullanmayı veya değiştirmeyi düşünün:

``` PowerShell

$FileVersion = [System.Diagnostics.FileVersionInfo]::GetVersionInfo("<path to binary file>").FileVersion
#The below line trims the spaces before and after the version name
$FileVersion = $FileVersion.Trim();
if ("<file version of successfully detected file>" -eq $FileVersion)
{
#Write the version to STDOUT by default
$FileVersion
exit 0
}
else
{
#Exit with non-zero failure code
exit 1
}
```

Yukarıdaki PowerShell komutunda, `<path to binary file>` dizesini Win32 uygulama dosyanızın yoluyla değiştirin. Örnek bir yol aşağıdakine benzer olacaktır:<br>
`C:\Program Files (x86)\Microsoft SQL Server Management Studio 18\Common7\IDE\ssms.exe`

Ayrıca, `<file version of successfully detected file>` dizesini, algılamak için gereken dosya sürümü ile değiştirin. Örnek bir dosya sürümü dizesi aşağıdakine benzer:<br>
`2019.0150.18118.00 ((SSMS_Rel).190420-0019)`

Win32 uygulamanızın sürüm bilgilerini almanız gerekiyorsa aşağıdaki PowerShell komutunu kullanabilirsiniz:

``` PowerShell

[System.Diagnostics.FileVersionInfo]::GetVersionInfo("<path to binary file>").FileVersion

```

Yukarıdaki PowerShell komutunda `<path to binary file>`, dosya yolunuza göre değiştirin.

### <a name="additional-troubleshooting-areas-to-consider"></a>Dikkate alınması gereken ek sorun giderme alanı
- Aracının cihazda yüklü olduğundan emin olmak için hedefi denetleyin - Bir grubu hedefleyen Win32 uygulaması veya bir grubu hedefleyen PowerShell Betiği, güvenlik grubu için aracı yükleme ilkesi oluşturur.
- İşletim sistemi sürümünü denetleyin – Windows 10 1607 veya üzeri.  
- Windows 10 SKU'sunu denetleyin - Windows 10 S veya S modu etkinleştirilmiş olarak çalışan Windows sürümleri MSI yüklemesini desteklemez.

Win32 uygulamalarında sorun giderme hakkında daha fazla bilgi için bkz. [Win32 uygulama yükleme sorunlarını giderme](troubleshoot-app-install.md#win32-app-installation-troubleshooting).

## <a name="next-steps"></a>Sonraki adımlar

- Intune'a uygulamaları ekleme hakkında daha fazla bilgi için bkz. [Microsoft Intune'a uygulama ekleme](apps-add.md).
