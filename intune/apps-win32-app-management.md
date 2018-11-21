---
title: Microsoft Intune’a Win32 uygulamaları ekleme
titlesuffix: ''
description: Microsoft Intune ile Win32 uygulamaları eklemeyi, teslim etmeyi ve yönetmeyi öğrenin. Bu konu, Intune Win32 uygulaması teslim ve yönetim özelliklerine yönelik genel bir bakışın yanı sıra, Win32 uygulaması sorun giderme bilgilerini sağlar.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: efdc196b-38f3-4678-ae16-cdec4303f8d2
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 0dc1974a57e5a5aa6808936c37e02fd31a7cac7b
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52187303"
---
# <a name="intune-standalone---win32-app-management-public-preview"></a>Intune Tek başına - Win32 uygulama yönetimi (Genel Önizleme)

Intune tek başına daha fazla Win32 uygulama yönetimi özellikleri sağlar. Bulut bağlantılı müşterilerin Win32 uygulama yönetiminde Configuration Manager'ı kullanmaları mümkün olsa da, yanızca Intune kullanan müşteriler Win32 iş kolu (LOB) uygulamalarında daha fazla yönetim özelliğinden yararlanabilir. Bu konu, Intune Win32 uygulaması yönetim özelliklerine yönelik genel bir bakışın yanı sıra, sorun giderme bilgileri sağlar.

## <a name="prerequisites-for-public-preview"></a>Genel önizleme için önkoşullar

- Windows 10 sürüm 1607 veya üzeri (Enterprise)
- Windows 10 istemcisi: 
    - Azure Active Directory’ye (AAD) veya Hibrit Azure Active Directory’ye katılmış olmalıdır
    - Intune’da kayıtlı (MDM ile yönetilen) olmalıdır
- Windows uygulaması boyutu, genel önizlemede uygulama başına 8 GB ile sınırlıdır 

> [!NOTE]
> Şu anda Windows 10 sürüm 1607 Pro ve Education sürümlerini test ediyoruz ve geri bildirimlerinizi bekliyoruz.


## <a name="prepare-the-win32-app-content-for-upload"></a>Karşıya yükleme için Win32 uygulaması içeriğini hazırlama

Win32 uygulamalarını önceden işlemek için [Microsoft Intune Win32 Uygulama Karşıya Yükleme Hazırlık Aracı](https://github.com/Microsoft/Intune-Win32-App-Packaging-Tool)'nı kullanın. Paketleme aracı uygulama yükleme dosyalarını *.intunewin* biçimine dönüştürür. Ayrıca paketleme aracı Intune'a uygulama yükleme durumunu saptamak için gereken özniteliklerin bazılarını da algılar. Uygulama yükleyicisi klasöründe bu aracı kullandıktan sonra, Intune konsolunda Win32 uygulaması oluşturabilirsiniz.

[Microsoft Intune Win32 Uygulama Karşıya Yükleme Hazırlık Aracı](https://github.com/Microsoft/Intune-Win32-App-Packaging-Tool)'nı GitHub'dan indirebilirsiniz.

### <a name="available-command-line-parameters"></a>Kullanılabilir komut satırı parametreleri 

|    **Komut satırı parametresi**    |    **Açıklama**    |
|:------------------------------:|:----------------------------------------------------------:|
|    `-h`     |    Yardım    |
|    `-c <setup_folder>`     |    Tüm kurulum dosyaları için kurulum klasörü.    |
|   ` -s <setup_file>`     |    Kurulum dosyası (*setup.exe* veya *setup.msi* gibi).    |
|    `-o <output_folder>`     |    Oluşturulan *.intunewin* dosyası için çıkış klasörü.    |
|    `-q`       |    Sessiz mod    |

### <a name="example-commands"></a>Örnek komutlar

|    **Örnek komut**    |    **Açıklama**    |
|:-----------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|    `IntuneWinAppUtil -h`    |    Bu komut aracın kullanım bilgilerini gösterir.    |
|    `IntuneWinAppUtil -c <setup_folder> -s <source_setup_file> -o <output_folder> <-q>`    |    Bu komut, belirtilen kaynak klasörden ve kurulum dosyasından `.intunewin` dosyasını oluşturur. MSI kurulum dosyası için, bu araç Intune'a gereken bilgileri alır. `-q` belirtilirse, komut sessiz modda çalıştırılır ve çıkış dosyası zaten varsa, bu dosyanın üzerine yazılır. Ayrıca, çıkış klasörü yoksa otomatik olarak oluşturulur.    |

Oluştururken bir *.intunewin* dosyası, Kurulum klasörünün bir alt klasöre başvurmak için ihtiyacınız olan tüm dosyaları yerleştirin. Ardından, gerek duyduğunuz belirli bir dosyaya başvurmak için göreli bir yol kullanın. Örneğin:

**Kurulum kaynak klasörü:** *c:\testapp\v1.0*<br>
**Lisans dosyası:** *c:\testapp\v1.0\licenses\license.txt*

Başvurmak *license.txt* göreli yolu kullanarak dosya *licenses\license.txt*.

## <a name="create-assign-and-monitor-a-win32-app"></a>Win32 uygulamasını oluşturma, atama ve izleme

İş kolu (LOB) uygulamalarına çok benzer bir biçimde, Win32 uygulamalarını da Microsoft Intune'a ekleyebilirsiniz. Bu gibi uygulamalar normalde şirket içinde veya üçüncü taraflarca yazılır. Aşağıdaki adımlar Windows uygulamasını Intune'a eklemenize yardımcı olacak yönergeler sağlar.

### <a name="step-1-specify-the-software-setup-file"></a>1. Adım: Yazılım kurulum dosyasını belirtme

1.  [Azure portalı](https://portal.azure.com/)’nda oturum açın.
2.  **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümündedir.
3.  **Intune** bölmesinde **İstemci uygulamaları** > **Uygulamalar** > **Ekle**'yi seçin.
4.  **Uygulama ekle** bölmesinde, sağlanan açılan pencereden **Windows uygulaması (Win32) - önizleme**'yi seçin.

    ![Ekran görüntüsü Uygulama ekle - Tür ekle açılan kutusu](./media/apps-win32-app-01.png)

### <a name="step-2-upload-the-app-package-file"></a>2. Adım: Uygulama paketi dosyasını karşıya yükleme

1.  **Uygulama ekle** bölmesinde dosya seçmek için **Uygulama paketi dosyası**’nı seçin. Uygulama paketi dosyası bölmesi görüntülenir.

    ![Uygulama paketi dosyası ekran görüntüsü](./media/apps-win32-app-02.png)

2.  **Uygulama paket dosyası** bölmesinde gözat düğmesini seçin. Daha sonra *.intunewin* uzantılı bir Windows yükleme dosyası seçin.
3.  İşiniz bittiğinde **Tamam**’a tıklayın.

### <a name="step-3-configure-app-information"></a>3. Adım: Uygulama bilgilerini yapılandırma

1.  Uygulamayı yapılandırmak için **Uygulama ekle** bölmesinde **Uygulama bilgileri**’ni seçin.
2.  **Uygulama bilgileri** bölmesinde aşağıdaki bilgileri yapılandırın. Bu bölmedeki değerlerden bazıları otomatik olarak doldurulabilir.
    - **Ad**: Uygulamanın Şirket Portalı’nda görünen adını girin. Aynı uygulama adı iki kez kullanılmışsa, iki uygulama da Şirket Portalı’nda görüntülenir.
    - **Açıklama**: Uygulama için bir açıklama girin. Açıklama, Şirket Portalı’nda görünür.
    - **Yayımcı**: Uygulama yayımcısının adını girin.
    - **Kategori**: Yerleşik uygulama kategorilerinden birini veya kendi oluşturduğunuz kategoriyi seçin. Kategoriler, kullanıcıların Şirket Portalı’na göz atarken uygulamayı daha kolay bulabilmesini sağlar.
    - **Bunu Şirket Portalı’nda öne çıkan uygulama olarak görüntüle**: Kullanıcılar uygulamalara göz atarken bu uygulamayı Şirket Portalı’nın ana sayfasında göze çarpacak şekilde görüntüleyin.
    - **Bilgi URL’si**: İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL Şirket Portalı’nda görünür.
    - **Gizlilik URL’si**: İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, Şirket Portalı’nda görünür.
    - **Geliştirici**: İsteğe bağlı olarak, uygulama geliştiricisinin adını girin.
    - **Sahip**: İsteğe bağlı olarak uygulama sahibinin adını girin. Örneğin **İK departmanı**.
    - **Notlar**: Bu uygulamayla ilişkilendirmek istediğiniz notları girin.
    - **Logo**: Uygulamayla ilişkilendirilen bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar Şirket Portalı’na gözatarken uygulamayla birlikte görüntülenir.
3.  İşiniz bittiğinde **Tamam**’a tıklayın.

### <a name="step-4-configure-app-installation-details"></a>4. Adım: Uygulama yükleme ayrıntılarını yapılandırma
1.  **Uygulama ekle** bölmesinde, uygulamanın yükleme ve kaldırma komutlarını yapılandırmak için **Program**'ı seçin.
2.  Uygulamayı yüklemek için yükleme komut satırının tamamını ekleyin. 

    Örneğin, uygulama dosyanızın adı **MyApp123** ise şunu ekleyin: `msiexec /i “MyApp123.msi”`

3.  Uygulamanın GUID'si temelinde uygulamayı kaldırmak için kaldırma komut satırının tamamını ekleyin. 

    Örneğin: `msiexec /x “{12345A67-89B0-1234-5678-000001000000}”`

    > [!NOTE]
    > Bir Win32 uygulamasını **Kullanıcı** veya **Sistem** bağlamında yüklenecek şekilde yapılandırabilirsiniz. **Kullanıcı** bağlamı yalnızca belirli bir kullanıcıyı ifade eder. **Sistem** bağlamı bir Windows 10 cihazın tüm kullanıcılarını ifade eder.
    >
    > Son kullanıcıların Win32 uygulamalarını yüklemek için cihazda oturum açmış olmaları gerekmez.

4.  İşiniz bittiğinde **Tamam**’a tıklayın.

### <a name="step-5-configure-app-requirements"></a>5. Adım: Uygulama gereksinimlerini yapılandırma

1.  **Uygulama ekle** bölmesinde, uygulamayı yüklemeden önce cihazların karşılaması gereken gereksinimleri yapılandırmak için **Gereksinimler**'i seçin.
2.  **Gereksinimler** bölmesinde aşağıdaki bilgileri yapılandırın. Bu bölmedeki değerlerden bazıları otomatik olarak doldurulabilir.
    - **İşletim sistemi mimarisi**: Uygulamayı yüklemek için gereken mimarileri seçin.
    - **Minimum işletim sistemi**: Uygulamayı yüklemek için gereken minimum işletim sistemini seçin.
    - **Gerekli disk alanı (MB)**: İsteğe bağlı olarak, uygulamayı yüklemek için sistem sürücüsünde gereken boş disk alanını ekleyin.
    - **Gerekli fiziksel bellek (MB)**: İsteğe bağlı olarak, uygulamayı yüklemek için gereken fiziksel belleği (RAM) ekleyin.
    - **Gereken en düşük mantıksal işlemci sayısı**: İsteğe bağlı olarak, uygulamayı yüklemek için gereken en düşük mantıksal işlemci sayısını ekleyin.
    - **Gereken en düşük CPU hızı (MHz)**: İsteğe bağlı olarak, uygulamayı yüklemek için gereken en düşük CPU hızını ekleyin.
3.  İşiniz bittiğinde **Tamam**’a tıklayın.

### <a name="step-6-configure-app-detection-rules"></a>6. Adım: Uygulama algılama kurallarını yapılandırma

1.  **Uygulama ekle** bölmesinde, uygulamanın varlığını algılamaya yönelik kuralları yapılandırmak için **Algılama kuralları**'nı seçin.
2.  **Kuralların biçimi** alanında uygulamanın varlığının nasıl algılanacağını seçin. Algılama kurallarını el ile yapılandırmayı seçebileceğiniz gibi uygulamanın varlığını algılamak için özel bir betik de kullanabilirsiniz. En az bir algılama kuralı seçmelisiniz. 

    > [!NOTE]
    > **Algılama kuralları** bölmesinde birden fazla kural eklemeyi seçebilirsiniz. Uygulamanı algılanması için **tüm** kuralların koşullarına uyulmalıdır.

    - **Algılama kurallarını el ile yapılandırın** - Şu kural türlerinden birini seçebilirsiniz:
        1.  **MSI** – MSI sürüm denetimine dayanarak doğrulayın. Bu seçenek tek bir kez eklenebilir. Bu kural türünü seçtiğinizde iki ayarınız olur:
            - **MSI ürün kodu** – Uygulama için geçerli bir MSI ürün kodu ekleyin.
            - **MSI ürün sürümü denetimi** – MSI ürün koduna ek olarak MSI ürün sürümünü doğrulamak için **Evet**'i seçin.
        2.  **Dosya** – Dosya veya klasör algılama, tarih, sürüm veya boyut temelinde doğrulayın.
            - **Yol** – Algılanacak dosya veya klasörün bulunduğu klasörün tam yolu.
            - **Dosya veya klasör** - Algılanacak dosya veya klasör.
            - **Algılama yöntemi** – Uygulamanın varlığını doğrulamak için kullanılan algılama yönteminin türünü seçin.
            - **64 bit istemciler üzerinde bir 32 bit uygulamayla ilişkilendirildi** - Tüm yol ortam değişkenlerini 64 bit istemciler üzerinde 32 bit bağlamında genişletmek için **Evet**'i seçin. Tüm yol değişkenlerini 64 bit istemciler üzerinde 64 bit bağlamında genişletmek için **Hayır**'ı (varsayılan) seçin. 32 bit istemciler her zaman 32 bit bağlamını kullanır.
            
            **Dosya tabanlı algılama örnekleri**
            1.  Dosyanın varlığını denetleyin.
         
                ![Algılama kuralı bölmesi - dosya varlığı ekran görüntüsü](./media/apps-win32-app-03.png)
        
            2.  Klasör varlığını denetleyin.
         
                ![Algılama kuralı bölmesi - klasör varlığı ekran görüntüsü](./media/apps-win32-app-04.png)
        
        3. **Kayıt defteri** – Değer, dize, tamsayı veya sürüm temelinde doğrulayın.
            - **Anahtar yolu** – Algılanacak değerin bulunduğu kayıt defteri girdisinin tam yolu.
            - **Değer adı** - Algılanacak kayıt defteri değerinin adı. Bu değer boşsa algılama anahtarda gerçekleştirilir. Algılama yöntemi dosya veya klasör varlığından farklı bir yöntemse, algılama değeri olarak anahtarın (varsayılan) değeri kullanılır.
            - **Algılama yöntemi** – Uygulamanın varlığını doğrulamak için kullanılan algılama yönteminin türünü seçin.
            - **64 bit istemciler üzerinde bir 32 bit uygulamayla ilişkilendirildi** - 64 bit istemcilerde 32 bit kayıt defterinde arama yapmak için **Evet**'i seçin. 64 bit istemcilerde 64 bit kayıt defterinde arama yapmak için **Hayır**'ı (varsayılan) seçin. 32 bit istemcilerde her zaman 32 bit kayıt defterinde arama yapılır.
            
            **Kayıt defteri temelinde algılama örnekleri**
            1.  Kayıt defteri anahtarının varlığını denetleyin.
            
                ![Algılama kuralı bölmesi - kayıt defteri anahtarı var ekran görüntüsü](./media/apps-win32-app-05.png)    
            
            2.  Kayıt defteri değerinin var olup olmadığını denetleyin (**Önizlemede sağlanmak**).
        
                ![Algılama kuralı bölmesi - kayıt defteri değeri varlığı ekran görüntüsü](./media/apps-win32-app-06.png)    
        
            3.  Kayıt defteri değer dizesinin eşitliğini denetleyin.
        
                ![Algılama kuralı bölmesi - kayıt defteri değer dizesi eşittir ekran görüntüsü](./media/apps-win32-app-07.png)    
     
    - **Özel algılama betiği kullan** – Bu uygulamayı algılamak için kullanılacak PowerShell betiğini belirtin. 
    
        1.  **Betik dosyası** – İstemcide uygulamanın varlığını algılayacak PowerShell betiğini seçin. Betik hem 0 değerinde çıkış kodu döndürdüğünde hem de STDOUT'a bir dize değeri yazdığında uygulama algılanır.
        2.  **Betiği 64 bitlik istemcilerde 32 bitlik işlem olarak çalıştır** - Betiği oturum açmış olan son kullanıcının kimlik bilgilerini kullanarak çalıştırmak için **Evet**'i seçin. Betiği sistem bağlamında çalıştırmak için **Hayır**'ı (varsayılan) seçin.
        3.  **Betik imzası denetimini zorla** - Betiğin güvenilen bir yayımcı tarafından imzalandığını doğrulamak için **Evet**'i seçin. Bu doğrulama betiğin hiçbir uyarı veya istem gösterilmeden çalıştırılmasına olanak tanır. Betik engellenmeden çalıştırılır. Betiği imza doğrulaması yapılmadan son kullanıcının onayıyla çalıştırmak için **Hayır**'ı (varsayılan) seçin.
    
        Intune sepeti betikten gelen sonuçları denetler. Betik tarafından standart çıkış (STDOUT) akışına, standart hata (STDERR) akışına ve çıkış koduna yazılan değerleri okur. Betikten sıfırdan farklı bir değerle çıkılırsa, betik başarısız olur ve uygulama algılama durumu Yüklü Değil olur. Çıkış kodu sıfırsa ve STDOUT veri içeriyorsa, uygulama algılama durumu Yüklü'dür. 
    
        > [!NOTE]
        > Betikten 0 değeriyle çıkılırsa, betiğin yürütülmesi başarılı olmuştur. İkinci çıkış kanalı uygulamanın algılandığını gösterir - STDOUT verileri uygulamanın istemcide bulunduğunu gösterir. STDOUT akışından belirli bir dize beklemeyiz.
    
3.  Kurallarınızı ekledikten sonra **Ekle** > **Tamam**'ı seçin.

### <a name="step-7-configure-app-return-codes"></a>7. Adım: Uygulama dönüş kodlarını yapılandırma

1.  **Uygulama ekle** bölmesinde **Dönüş kodları**'nı seçerek, uygulama yüklemesi yeniden deneme davranışını veya yükleme sonrası davranışını belirtmek için kullanılan dönüş kodlarını ekleyin. Dönüş kodu girdileri varsayılan olarak uygulama oluşturma işlemi sırasında eklenir. Bununla birlikte, başka dönüş kodları ekleyebilir veya mevcut dönüş kodlarını değiştirebilirsiniz. 
2.  **Dönüş kodları** bölmesinde, başka dönüş kodları ekleyin veya mevcut dönüş kodlarında değişiklik yapın.
    - **Başarısız** – Uygulama yüklemesinin başarısız olduğunu belirten dönüş kodu.
    - **Donanımdan önyükleme** – Donanımdan önyükleme dönüş kodu, istemcide önyükleme yapılmadan sonraki Win32 uygulamalarının yüklenmesine izin vermez. 
    - **Yazılımdan önyükleme** – Yazılımdan önyükleme dönüş kodu, istemci önyüklemesine gerek kalmadan sonraki Win32 uygulamasının yüklenmesine izin verir. Geçerli uygulamanın yüklemesini tamamlamak için önyükleme gereklidir.
    - **Yeniden deneme** – Yeniden deneme dönüş koduyla aracı uygulamayı yüklemeyi üç kez dener. Her denemeden sonra 5 dakika bekler. 
    - **Başarılı** – Uygulamanın başarıyla yüklendiğini belirten dönüş kodu.
3.  Dönüş kodları listenizdeki eklemeleri veya değişiklikleri yaptıktan sonra **Tamam**'ı seçin.

### <a name="step-8-add-the-app"></a>8. Adım: Uygulamayı ekleme

1.  **Uygulama ekle** bölmesinde, uygulama bilgilerini doğru yapılandırdığınızı onaylayın.
2.  Uygulamayı Intune'a yüklemek için **Ekle**’yi seçin.

### <a name="step-9-assign-the-app"></a>9. Adım: Uygulamayı atama

1.  Uygulama bölmesinde **Atamalar**’ı seçin.
2.  Uygulamayla ilgili **Grup ekle** bölmesini açmak için **Grup Ekle**'yi seçin.
3.  Belirli bir uygulama için **atama türü** seçin:
    - **Kayıtlı cihazlar için bulunur**: Kullanıcılar, Şirket Portalı uygulamasından veya Şirket Portalı web sitesinden uygulamayı yükler.
    - **Gerekli**: Uygulama, seçili gruplardaki cihazlara yüklenir.
    - **Kaldırma**: Uygulama, seçilen gruplardaki cihazlardan kaldırılır.
4.  **Eklenen Gruplar**'ı seçin ve bu uygulamayı kullanacak grupları atayın.
5.  Dahil edilen gruplar seçimini tamamlamak için **Ata** bölmesinde **Tamam**'ı seçin.
6.  Herhangi bir kullanıcı grubunun bu uygulama atamasından etkilenmesini istemiyorsanız, **Grupları Dışla**'yı seçin.
7.  **Grup ekle** bölmesinde **Tamam**’ı seçin.
8.  Uygulamanın **Atamalar** bölmesinde **Kaydet**'i seçin.

Bu noktada Intune'a Win32 uygulaması ekleme adımlarını tamamlamış oldunuz. Uygulama atama ve izleme hakkında bilgi için bkz. [Microsoft Intune ile uygulamaları gruplara atama](https://docs.microsoft.com/intune/apps-deploy) ve [Microsoft Intune ile uygulama bilgilerini ve atamalarını izleme](https://docs.microsoft.com/intune/apps-monitor).

## <a name="install-required-and-available-apps-on-devices"></a>Gerekli ve kullanılabilir uygulamaları cihazlara yükleme

Son kullanıcı gerekli ve kullanılabilir uygulama yüklemeleriyle ilgili Windows Bildirimleri görecektir. Aşağıdaki resimde, cihaz yeniden başlatılana kadar uygulama yüklemesinin tamamlanmayacağına ilişkin bildirim örneği gösterilir. 

![Uygulama yüklemesiyle ilgili Windows bildirimleri örneğinin ekran görüntüsü](./media/apps-win32-app-08.png)    

Aşağıdaki resimde, son kullanıcıya cihazda uygulama değişiklikleri yapıldığı bildirilir.

![Son kullanıcıya cihazda uygulama değişiklikleri yapıldığı bildirme örneğinin ekran görüntüsü](./media/apps-win32-app-09.png)    

## <a name="troubleshoot-win32-app-issues"></a>Win32 uygulamasında sorun giderme
İstemci makinesindeki aracı günlükleri genellikle `C:\ProgramData\Microsoft\IntuneManagementExtension\Logs` yolunda bulunur. Bu günlük dosyalarını görüntülemek için `CMTrace.exe` dosyasından yararlanabilirsiniz. *CMTrace.exe*, [SCCM İstemci Araçları](https://docs.microsoft.com/sccm/core/support/tools)'ndan indirilebilir. 

![Aracı günlükleri ekran görüntüsü](./media/apps-win32-app-10.png)    

### <a name="troubleshooting-areas-to-consider"></a>Dikkate alınacak sorun giderme alanları
- Aracının cihazda yüklü olduğundan emin olmak için hedefi denetleyin - Bir grubu hedefleyen Win32 uygulaması veya bir grubu hedefleyen PowerShell Betiği, güvenlik grubu için aracı yükleme ilkesi oluşturur.
- İşletim sistemi sürümünü denetleyin – Windows 10 1607 veya üzeri.  
- Windows 10 SKU'sunu denetleyin - Windows 10 S veya S modu etkinleştirilmiş olarak çalışan Windows sürümleri MSI yüklemesini desteklemez.

## <a name="next-steps"></a>Sonraki adımlar

- Intune'a uygulamaları ekleme hakkında daha fazla bilgi için bkz. [Microsoft Intune'a uygulama ekleme](apps-add.md).
