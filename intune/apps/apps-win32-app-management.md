---
title: Microsoft Intune için Win32 uygulamaları ekleme ve atama
titleSuffix: ''
description: Microsoft Intune ile Win32 uygulamaları eklemeyi, atamayı ve yönetmeyi öğrenin. Bu konu, Intune Win32 uygulaması teslim ve yönetim özelliklerine yönelik genel bir bakışın yanı sıra, Win32 uygulaması sorun giderme bilgilerini sağlar.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/09/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: efdc196b-38f3-4678-ae16-cdec4303f8d2
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 593c2d2b509047115ebeb3415393d6112484a6a9
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71731197"
---
# <a name="intune-standalone---win32-app-management"></a>Tek başına Intune-Win32 uygulama yönetimi

[Tek başına Intune](../fundamentals/mdm-authority-set.md) artık daha büyük Win32 uygulama yönetimi özelliklerine izin veriyor. Bulut bağlantılı müşterilerin Win32 uygulama yönetiminde Configuration Manager'ı kullanmaları mümkün olsa da, yanızca Intune kullanan müşteriler Win32 iş kolu (LOB) uygulamalarında daha fazla yönetim özelliğinden yararlanabilir. Bu konu, Intune Win32 uygulaması yönetim özelliklerine yönelik genel bir bakışın yanı sıra, sorun giderme bilgileri sağlar.

> [!NOTE]
> Bu uygulama yönetimi özelliği, Windows uygulamaları için hem 32-bit hem de 64-bit işletim sistemi mimarisini destekler.

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

   ![. Intunewin dosyası oluşturmak için işlem akışı](./media/apps-win32-app-management/prepare-win32-app.svg)

### <a name="run-the-microsoft-win32-content-prep-tool"></a>Microsoft Win32 Içerik hazırlığı aracını çalıştırma

Komut penceresinden parametre olmadan `IntuneWinAppUtil.exe` ' ı çalıştırırsanız araç, gerekli parametreleri adım adım girerek size rehberlik eder. Ya da aşağıdaki kullanılabilir komut satırı parametrelerine göre parametreleri komuta ekleyebilirsiniz.

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

   ![Intune 'a bir Win32 uygulaması eklemek için işlem akışı](./media/apps-win32-app-management/add-win32-app.svg)

### <a name="add-a-win32-app-to-intune"></a>Intune 'a bir Win32 uygulaması ekleme

Aşağıdaki adımlar Windows uygulamasını Intune'a eklemenize yardımcı olacak yönergeler sağlar.

### <a name="step-1-specify-the-software-setup-file"></a>1\. Adım: Yazılım kurulum dosyasını belirtme

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Intune** bölmesinde **İstemci uygulamaları** > **Uygulamalar** > **Ekle**'yi seçin.
4. Uygulama **Ekle** bölmesinde, belirtilen açılan listeden **Windows uygulaması (Win32)** öğesini seçin.

    ![Uygulama Ekle dikey penceresinin ekran görüntüsü-tür Ekle açılan kutusu](./media/apps-win32-app-management/apps-win32-app-01.png)

### <a name="step-2-upload-the-app-package-file"></a>2\. Adım: Uygulama paketi dosyasını karşıya yükleme

1. **Uygulama ekle** bölmesinde dosya seçmek için **Uygulama paketi dosyası**’nı seçin. Uygulama paketi dosyası bölmesi görüntülenir.

    ![Uygulama paketi dosyası dikey penceresinin ekran görüntüsü](./media/apps-win32-app-management/apps-win32-app-02.png)

2. **Uygulama paket dosyası** bölmesinde gözat düğmesini seçin. Daha sonra *.intunewin* uzantılı bir Windows yükleme dosyası seçin.

    > [!IMPORTANT]
    > Microsoft Win32 Içerik hazırlığı aracının en son sürümünü kullandığınızdan emin olun. En son sürümü kullanmıyorsanız, uygulamanın Microsoft Win32 Içerik hazırlığı aracının daha eski bir sürümü kullanılarak paketlenmediğini belirten bir uyarı görürsünüz. 

3. İşiniz bittiğinde **Tamam**’a tıklayın.

### <a name="step-3-configure-app-information"></a>3\. Adım: Uygulama bilgilerini yapılandırma

1. Uygulamayı yapılandırmak için **Uygulama ekle** bölmesinde **Uygulama bilgileri**’ni seçin.
2. **Uygulama bilgileri** bölmesinde aşağıdaki bilgileri yapılandırın. Bu bölmedeki değerlerden bazıları otomatik olarak doldurulabilir.
    - **Ad**: Uygulamanın Şirket Portalı’nda görünen adını girin. Aynı uygulama adı iki kez kullanılmışsa, iki uygulama da Şirket Portalı’nda görüntülenir.
    - **Açıklama**: Uygulama için bir açıklama girin. Açıklama Şirket Portalı’nda görünür.
    - **Yayımcı**: Uygulama yayımcısının adını girin.
    - **Kategori**: Yerleşik uygulama kategorilerinden birini veya kendi oluşturduğunuz kategoriyi seçin. Kategoriler, kullanıcıların Şirket Portalı’na göz atarken uygulamayı daha kolay bulabilmesini sağlar.
    - **Bunu Şirket Portalı’nda öne çıkan uygulama olarak görüntüle**: Kullanıcılar uygulamalara göz atarken bu uygulamayı Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüleyin.
    - **Bilgi URL’si**: İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL Şirket Portalı’nda görünür.
    - **Gizlilik URL’si**: İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL Şirket Portalı’nda görünür.
    - **Geliştirici**: İsteğe bağlı olarak, uygulama geliştiricisinin adını girin.
    - **Sahip**: İsteğe bağlı olarak uygulama sahibinin adını girin. Örneğin **İK departmanı**.
    - **Notlar**: Bu uygulamayla ilişkilendirmek istediğiniz notları girin.
    - **Logo**: Uygulamayla ilişkilendirilen bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar Şirket Portalı’na gözatarken uygulamayla birlikte görüntülenir.
3. İşiniz bittiğinde **Tamam**’a tıklayın.

### <a name="step-4-configure-app-installation-details"></a>4\. Adım: Uygulama yükleme ayrıntılarını yapılandırma
1. **Uygulama ekle** bölmesinde, uygulamanın yükleme ve kaldırma komutlarını yapılandırmak için **Program**'ı seçin.
2. Uygulamayı yüklemek için yükleme komut satırının tamamını ekleyin. 

    Örneğin, uygulamanızın dosya adı **MyApp123**ise aşağıdakini ekleyin:<br>
    `msiexec /p “MyApp123.msp”`<p>
    Uygulama `ApplicationName.exe` ise, komut uygulamanın adı ve ardından paket tarafından desteklenen komut bağımsız değişkenleri (anahtarlar) olur. <br>Örneğin:<br>
    `ApplicationName.exe /quiet`<br>
    Yukarıdaki komutta `ApplicationName.exe` paketi, `/quiet` komut bağımsız değişkenini destekler.<p> 
    Uygulama paketi tarafından desteklenen belirli bağımsız değişkenler için uygulama satıcınıza başvurun.

3. Uygulamanın GUID'si temelinde uygulamayı kaldırmak için kaldırma komut satırının tamamını ekleyin. 

    Örneğin: `msiexec /x “{12345A67-89B0-1234-5678-000001000000}”`

    > [!NOTE]
    > Bir Win32 uygulamasını **Kullanıcı** veya **Sistem** bağlamında yüklenecek şekilde yapılandırabilirsiniz. **Kullanıcı** bağlamı yalnızca belirli bir kullanıcıyı ifade eder. **Sistem** bağlamı bir Windows 10 cihazın tüm kullanıcılarını ifade eder.
    >
    > Son kullanıcıların Win32 uygulamalarını yüklemek için cihazda oturum açmış olmaları gerekmez.
    > 
    > Win32 uygulaması yükleme ve kaldırma, uygulama kullanıcı bağlamında yüklenmek üzere ayarlandığında ve cihazdaki son kullanıcının yönetici ayrıcalıklarına sahip olması durumunda yönetici ayrıcalıkları altında (varsayılan olarak) yürütülür.

4. İşiniz bittiğinde **Tamam**’a tıklayın.

### <a name="step-5-configure-app-requirements"></a>5\. Adım: Uygulama gereksinimlerini yapılandırma

1. **Uygulama ekle** bölmesinde, uygulamayı yüklemeden önce cihazların karşılaması gereken gereksinimleri yapılandırmak için **Gereksinimler**'i seçin.
2. **Gereksinim kuralı ekle** bölmesinde aşağıdaki bilgileri yapılandırın. Bu bölmedeki değerlerden bazıları otomatik olarak doldurulabilir.
    - **İşletim sistemi mimarisi**: Uygulamayı yüklemek için gereken mimarileri seçin.
    - **Minimum işletim sistemi**: Uygulamayı yüklemek için gereken minimum işletim sistemini seçin.
    - **Gerekli disk alanı (MB)** : İsteğe bağlı olarak, uygulamayı yüklemek için sistem sürücüsünde gereken boş disk alanını ekleyin.
    - **Gerekli fiziksel bellek (MB)** : İsteğe bağlı olarak, uygulamayı yüklemek için gereken fiziksel belleği (RAM) ekleyin.
    - **Gereken en düşük mantıksal işlemci sayısı**: İsteğe bağlı olarak, uygulamayı yüklemek için gereken en düşük mantıksal işlemci sayısını ekleyin.
    - **Gereken en düşük CPU hızı (MHz)** : İsteğe bağlı olarak, uygulamayı yüklemek için gereken en düşük CPU hızını ekleyin.

3. **Gereksinim kuralı ekle** dikey penceresini göstermek ve ek gereksinim kurallarını yapılandırmak için **Ekle** ' ye tıklayın. Gereksinimin nasıl doğrulanacağını belirlemek için kullanacağınız kural türünü seçmek için **gereksinim türünü** seçin. Gereksinim kuralları dosya sistemi bilgilerini, kayıt defteri değerlerini veya PowerShell komut dosyalarını temel alabilir. 
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
4. İşiniz bittiğinde **Tamam**’a tıklayın.

### <a name="step-6-configure-app-detection-rules"></a>6\. Adım: Uygulama algılama kurallarını yapılandırma

1. **Uygulama ekle** bölmesinde, uygulamanın varlığını algılamaya yönelik kuralları yapılandırmak için **Algılama kuralları**'nı seçin.
2. **Kuralların biçimi** alanında uygulamanın varlığının nasıl algılanacağını seçin. Algılama kurallarını el ile yapılandırmayı seçebileceğiniz gibi uygulamanın varlığını algılamak için özel bir betik de kullanabilirsiniz. En az bir algılama kuralı seçmelisiniz. 

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

        4. Kurallarınızı ekledikten sonra **Ekle** > **Tamam**'ı seçin.

### <a name="step-7-configure-app-return-codes"></a>7\. Adım: Uygulama dönüş kodlarını yapılandırma

1. **Uygulama ekle** bölmesinde **Dönüş kodları**'nı seçerek, uygulama yüklemesi yeniden deneme davranışını veya yükleme sonrası davranışını belirtmek için kullanılan dönüş kodlarını ekleyin. Dönüş kodu girdileri varsayılan olarak uygulama oluşturma işlemi sırasında eklenir. Bununla birlikte, başka dönüş kodları ekleyebilir veya mevcut dönüş kodlarını değiştirebilirsiniz. 
2. **Dönüş kodları** bölmesinde, başka dönüş kodları ekleyin veya mevcut dönüş kodlarında değişiklik yapın.
    - **Failed** : bir uygulama yükleme hatasını gösteren dönüş değeri.
    - **Donanımdan önyükleme** – Donanımdan önyükleme dönüş kodu, istemcide önyükleme yapılmadan sonraki Win32 uygulamalarının yüklenmesine izin vermez. 
    - **Yazılımdan önyükleme** – Yazılımdan önyükleme dönüş kodu, istemci önyüklemesine gerek kalmadan sonraki Win32 uygulamasının yüklenmesine izin verir. Geçerli uygulamanın yüklemesini tamamlamak için önyükleme gereklidir.
    - **Yeniden deneme** – Yeniden deneme dönüş koduyla aracı uygulamayı yüklemeyi üç kez dener. Her denemeden sonra 5 dakika bekler. 
    - **Başarılı** – Uygulamanın başarıyla yüklendiğini belirten dönüş kodu.
3. Dönüş kodları listenizdeki eklemeleri veya değişiklikleri yaptıktan sonra **Tamam**'ı seçin.

### <a name="step-8-add-the-app"></a>8\. Adım: Uygulamayı ekleme

1. **Uygulama ekle** bölmesinde, uygulama bilgilerini doğru yapılandırdığınızı onaylayın.
2. Uygulamayı Intune'a yüklemek için **Ekle**’yi seçin.

### <a name="step-9-assign-the-app"></a>9\. Adım: Uygulamayı atama

1. Uygulama bölmesinde **Atamalar**’ı seçin.
2. Uygulamayla ilgili **Grup ekle** bölmesini açmak için **Grup Ekle**'yi seçin.
3. Belirli bir uygulama için **atama türü** seçin:
    - **Kayıtlı cihazlar için bulunur**: Kullanıcılar, Şirket Portalı uygulamasından veya Şirket Portalı web sitesinden uygulamayı yükler.
    - **Gerekli**: Uygulama, seçili gruplardaki cihazlara yüklenir.
    - **Kaldırma**: Uygulama, seçilen gruplardaki cihazlardan kaldırılır.
4. **Eklenen Gruplar**'ı seçin ve bu uygulamayı kullanacak grupları atayın.
5. Dahil edilen gruplar seçimini tamamlamak için **Ata** bölmesinde **Tamam**'ı seçin.
6. Herhangi bir kullanıcı grubunun bu uygulama atamasından etkilenmesini istemiyorsanız, **Grupları Dışla**'yı seçin.
7. **Grup ekle** bölmesinde **Tamam**’ı seçin.
8. Uygulamanın **Atamalar** bölmesinde **Kaydet**'i seçin.

Bu noktada, Intune 'a bir Win32 uygulaması ekleme adımlarını tamamladınız. Uygulama atama ve izleme hakkında bilgi için bkz. [Microsoft Intune ile uygulamaları gruplara atama](apps-deploy.md) ve [Microsoft Intune ile uygulama bilgilerini ve atamalarını izleme](apps-monitor.md).

## <a name="app-dependencies"></a>Uygulama bağımlılıkları

Uygulama bağımlılıkları, Win32 uygulamanızın yüklenebilmesi için yüklenmesi gereken uygulamalardır. Diğer uygulamaların bağımlılık olarak yüklenmesini zorunlu kılabilirsiniz. Özellikle, cihazın Win32 uygulamasını yüklemeden önce bağımlı uygulamaları yüklemesi gerekir. Dahil edilen bağımlılıkların bağımlılıklarını ve uygulamanın kendisini içeren en fazla 100 bağımlılığı vardır. Win32 uygulaması bağımlılıklarını yalnızca Win32 uygulamanız eklendikten ve Intune 'a yüklendikten sonra ekleyebilirsiniz. Win32 uygulamanız eklendikten sonra, Win32 uygulamanızın dikey penceresinde **Bağımlılıklar** seçeneğini görürsünüz. 

Herhangi bir Win32 uygulaması bağımlılığının de bir Win32 uygulaması olması gerekir. Tek MSI LOB uygulamaları veya Mağaza uygulamaları gibi diğer uygulama türlerine bağlı olarak desteklenmez.

Uygulama bağımlılığı eklerken, uygulama adı ve yayımcı temelinde arama yapabilirsiniz. Ek olarak, eklenen bağımlılıklarınızı uygulama adı ve yayımcıya göre sıralayabilirsiniz. Daha önce eklenen uygulama bağımlılıkları, eklenen uygulama bağımlılığı listesinde seçilemez. 

Her bağımlı uygulamanın otomatik olarak yüklenip yüklenmeyeceğini seçebilirsiniz. Varsayılan olarak, **otomatik olarak install** seçeneği her bağımlılık için **Evet** olarak ayarlanır. Bağımlı uygulama kullanıcı veya cihaza hedeflenmese bile, bağımlı uygulamayı otomatik olarak yükleyerek Intune, Win32 uygulamanızı yüklemeden önce bağımlılığı karşılamak üzere uygulamayı cihaza yükler. Bir bağımlılık özyinelemeli alt bağımlılıklara sahip olabileceğini ve ana bağımlılığı yüklemeden önce her bir alt bağımlılığın yükleneceğini unutmayın. Ayrıca, bağımlılıkların yüklenmesi belirli bir bağımlılık düzeyinde bir yükleme sırasına uymuyor.

Win32 uygulamanıza bir uygulama bağımlılığı eklemek için aşağıdaki adımları kullanın:

1. Intune 'da, eklenen istemci uygulamaları listenizi görüntülemek için **istemci uygulamaları** > **uygulamalar** ' ı seçin. 
2. Eklenen bir **Windows uygulaması (Win32)** uygulaması seçin. 
3. Win32 uygulaması yüklenmeden önce yüklenmesi gereken bağımlı uygulamaları eklemek için **Bağımlılıklar** ' ı seçin. 
4. Uygulama bağımlılığı eklemek için **Ekle** ' ye tıklayın.
5. Bağımlı uygulamaları ekledikten sonra **Seç**' e tıklayın.
6. **Otomatik olarak yüklemek**için **Evet** veya **Hayır** ' ı seçerek bağımlı uygulamanın otomatik olarak yüklenip yüklenmeyeceğini seçin.
7. **Kaydet**'e tıklayın.

Son Kullanıcı, bağımlı uygulamaların Win32 uygulama yükleme işleminin bir parçası olarak indirilmekte olduğunu ve yüklendiğini belirten Windows bildirim bildirimleri ' ni görür. Ayrıca, bağımlı bir uygulama yüklü olmadığında, son kullanıcı genellikle aşağıdaki bildirimlerden birini görür:
- 1 veya daha fazla bağımlı uygulama yüklenemedi
- 1 veya daha fazla bağımlı uygulama gereksinimi karşılanmadı
- 1 veya daha fazla bağımlı uygulama, cihaz yeniden başlatma bekliyor

**Otomatik olarak** bir bağımlılık yüklememeyi seçerseniz, Win32 uygulama yüklemesi denenmez. Ayrıca, uygulama raporlama bağımlılığın `failed` olarak işaretlenip işaretlenmediğini gösterir ve ayrıca bir hata nedeni sağlar. Win 32 uygulama [yükleme ayrıntılarında](troubleshoot-app-install.md#win32-app-installation-troubleshooting)belirtilen bir hataya (veya uyarıya) tıklayarak bağımlılık yükleme hatasını görüntüleyebilirsiniz. 

Her bağımlılık, Intune Win32 uygulaması yeniden deneme mantığına uyar (5 dakika bekledikten sonra 3 kez yüklemeyi deneyin) ve küresel yeniden değerlendirme zamanlaması. Ayrıca, bağımlılıklar yalnızca cihaza Win32 uygulamasını yükleme sırasında uygulanabilir. Bağımlılıklar bir Win32 uygulamasını kaldırmak için geçerli değildir. Bir bağımlılığı silmek için, bağımlılık listesi satırının sonunda bulunan bağımlı uygulamanın solundaki üç noktaya (üç nokta) tıklamalısınız. 

## <a name="delivery-optimization"></a>Teslim Iyileştirme

Windows 10 1709 ve üzeri istemciler, Windows 10 istemcisindeki bir teslim iyileştirme bileşeni kullanarak Intune Win32 uygulama içeriğini indirecek. Teslim iyileştirme, varsayılan olarak açık olan eşler arası işlevsellik sağlar. Teslim iyileştirme, Grup İlkesi ve Intune cihaz yapılandırması aracılığıyla yapılandırılabilir. Daha fazla bilgi için bkz. [Windows 10 Için teslim iyileştirmesi](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization). 

## <a name="install-required-and-available-apps-on-devices"></a>Gerekli ve kullanılabilir uygulamaları cihazlara yükleme

Son Kullanıcı, gerekli ve kullanılabilir uygulama yüklemeleri için Windows bildirimleri görüntülenir. Aşağıdaki resimde, cihaz yeniden başlatılana kadar uygulama yüklemesinin tamamlanmayacağına ilişkin bildirim örneği gösterilir. 

![Uygulama yüklemesi için Windows bildirim bildirimlerinin ekran görüntüsü](./media/apps-win32-app-management/apps-win32-app-08.png)    

Aşağıdaki görüntüde, son kullanıcıya cihazda uygulama değişikliklerinin yapıldığını bildirir.

![Kullanıcıya uygulama değişikliklerinin yapıldığını bildiren ekran görüntüsü](./media/apps-win32-app-management/apps-win32-app-09.png)    

## <a name="toast-notifications-for-win32-apps"></a>Win32 uygulamaları için bildirim bildirimleri 
Gerekirse, uygulama ataması başına Son Kullanıcı bildirim bildirimlerinin gösterilmesini gizleyebilirsiniz. Intune 'da, **istemci uygulamaları** > **uygulamalar** ' ı seçin > Uygulama > **atamaları** > **Ekle grupları**' nı seçin. 

> [!NOTE]
> Kaydı kaldırılan cihazlardaki Intune yönetim uzantısıyla yüklenmiş olan Win32 uygulamaları kaldırılmaz. Yöneticiler, KCG cihazlarına Win32 uygulamalarını sunmamak amacıyla bunları atamadan hariç tutma seçeneğini değerlendirebilir.

## <a name="troubleshoot-win32-app-issues"></a>Win32 uygulamasında sorun giderme
İstemci makinesindeki aracı günlükleri genellikle `C:\ProgramData\Microsoft\IntuneManagementExtension\Logs` yolunda bulunur. Bu günlük dosyalarını görüntülemek için `CMTrace.exe` dosyasından yararlanabilirsiniz. *CMTrace. exe* , [Configuration Manager istemci araçlarından](https://docs.microsoft.com/sccm/core/support/tools)indirilebilir. 

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

Yukarıdaki PowerShell komutunda `<path to binary file>` dizesini Win32 uygulama dosyanızın yoluyla değiştirin. Örnek bir yol aşağıdakine benzer olacaktır:<br>
`C:\Program Files (x86)\Microsoft SQL Server Management Studio 18\Common7\IDE\ssms.exe`

Ayrıca, `<file version of successfully detected file>` dizesini, algılamak için gereken dosya sürümü ile değiştirin. Örnek bir dosya sürümü dizesi aşağıdakine benzer:<br>
`2019.0150.18118.00 ((SSMS_Rel).190420-0019)`

Win32 uygulamanızın sürüm bilgilerini almanız gerekiyorsa aşağıdaki PowerShell komutunu kullanabilirsiniz:

``` PowerShell

[System.Diagnostics.FileVersionInfo]::GetVersionInfo("<path to binary file>").FileVersion

```

Yukarıdaki PowerShell komutunda, `<path to binary file>` ' ı dosya yolunuza göre değiştirin.

### <a name="additional-troubleshooting-areas-to-consider"></a>Dikkate alınması gereken ek sorun giderme alanı
- Aracının cihazda yüklü olduğundan emin olmak için hedefi denetleyin - Bir grubu hedefleyen Win32 uygulaması veya bir grubu hedefleyen PowerShell Betiği, güvenlik grubu için aracı yükleme ilkesi oluşturur.
- İşletim sistemi sürümünü denetleyin – Windows 10 1607 veya üzeri.  
- Windows 10 SKU'sunu denetleyin - Windows 10 S veya S modu etkinleştirilmiş olarak çalışan Windows sürümleri MSI yüklemesini desteklemez.

Win32 uygulamalarında sorun giderme hakkında daha fazla bilgi için bkz. [Win32 uygulama yükleme sorunlarını giderme](troubleshoot-app-install.md#win32-app-installation-troubleshooting).

## <a name="next-steps"></a>Sonraki adımlar

- Intune'a uygulamaları ekleme hakkında daha fazla bilgi için bkz. [Microsoft Intune'a uygulama ekleme](apps-add.md).
