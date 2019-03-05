---
title: Microsoft Intune’a Win32 uygulamaları ekleme
titlesuffix: ''
description: Microsoft Intune ile Win32 uygulamaları eklemeyi, teslim etmeyi ve yönetmeyi öğrenin. Bu konu, Intune Win32 uygulaması teslim ve yönetim özelliklerine yönelik genel bir bakışın yanı sıra, Win32 uygulaması sorun giderme bilgilerini sağlar.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/04/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: efdc196b-38f3-4678-ae16-cdec4303f8d2
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 35116ccf13cf94960f02c3aff6d8c7c66fbe0e48
ms.sourcegitcommit: da9ee02de327f202b00be44c79bf7abd35b9929b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57335233"
---
# <a name="intune-standalone---win32-app-management"></a>Intune tek başına - Win32 Uygulama Yönetimi

Intune tek başına daha fazla Win32 uygulama yönetimi özellikleri sağlar. Bulut bağlantılı müşterilerin Win32 uygulama yönetiminde Configuration Manager'ı kullanmaları mümkün olsa da, yanızca Intune kullanan müşteriler Win32 iş kolu (LOB) uygulamalarında daha fazla yönetim özelliğinden yararlanabilir. Bu konu, Intune Win32 uygulaması yönetim özelliklerine yönelik genel bir bakışın yanı sıra, sorun giderme bilgileri sağlar.

## <a name="prerequisites"></a>Önkoşullar

- Windows 10 sürüm 1607 veya üzeri (Enterprise, Pro ve Education sürümleri)
- Windows 10 istemcisi: 
    - Azure Active Directory’ye (AAD) veya Hibrit Azure Active Directory’ye katılmış olmalıdır
    - Intune’da kayıtlı (MDM ile yönetilen) olmalıdır
- Windows uygulama boyutu, uygulama 8 GB olarak tavan

## <a name="prepare-the-win32-app-content-for-upload"></a>Karşıya yükleme için Win32 uygulaması içeriğini hazırlama

Kullanım [Microsoft Win32 içerik hazırlığı aracını](https://go.microsoft.com/fwlink/?linkid=2065730) Win32 uygulamaları önceden işlenecek. Aracı uygulama yükleme dosyalarına dönüştürür *.intunewin* biçimi. Aracın bazı Intune tarafından uygulama yükleme durumunu belirlemek için gerekli öznitelikler algılar. Uygulama yükleyicisi klasöründe bu aracı kullandıktan sonra, Intune konsolunda Win32 uygulaması oluşturabilirsiniz.

> [!IMPORTANT]
> [Microsoft Win32 içerik hazırlığı aracını](https://go.microsoft.com/fwlink/?linkid=2065730) oluştururken zıps tüm dosyaları ve alt klasörleri *.intunewin* dosya. Böylece aracı veya diğer gereksiz dosyaları ve klasörleri içermez Microsoft Win32 içerik hazırlığı aracını Installer dosyalarını ve klasörlerini ayrı sakladığınızdan emin olun, *.intunewin* dosya.

İndirebileceğiniz [Microsoft Win32 içerik hazırlığı aracını](https://go.microsoft.com/fwlink/?linkid=2065730) github'dan.

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

### <a name="step-1-specify-the-software-setup-file"></a>1. adım: Yazılım Kurulum dosyasını belirtme

1.  [Azure Portal](https://portal.azure.com/) oturum açın.
2.  **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümündedir.
3.  **Intune** bölmesinde **İstemci uygulamaları** > **Uygulamalar** > **Ekle**'yi seçin.
4.  İçinde **Ekle** uygulama bölmesinde **Windows uygulaması (Win32)** sağlanan aşağı açılan listeden.

    ![Ekran görüntüsü Ekle uygulama dikey penceresi - ekleme türü açılan kutusu](./media/apps-win32-app-01.png)

### <a name="step-2-upload-the-app-package-file"></a>2. adım: Uygulama paketi dosyasını karşıya yükle

1.  **Uygulama ekle** bölmesinde dosya seçmek için **Uygulama paketi dosyası**’nı seçin. Uygulama paketi dosyası bölmesi görüntülenir.

    ![Uygulama paket dosyası dikey penceresinin ekran görüntüsü](./media/apps-win32-app-02.png)

2.  **Uygulama paket dosyası** bölmesinde gözat düğmesini seçin. Daha sonra *.intunewin* uzantılı bir Windows yükleme dosyası seçin.

    > [!IMPORTANT]
    > Microsoft Win32 içerik hazırlığı aracını en son sürümünü kullandığınızdan emin olun. En son sürümü kullanmıyorsanız, uygulamayı Microsoft Win32 içerik hazırlığı aracının eski bir sürümü kullanılarak paketlendi belirten bir uyarı görürsünüz. 

3.  İşiniz bittiğinde **Tamam**’a tıklayın.

### <a name="step-3-configure-app-information"></a>3. adım: Uygulama bilgilerini yapılandırma

1.  Uygulamayı yapılandırmak için **Uygulama ekle** bölmesinde **Uygulama bilgileri**’ni seçin.
2.  **Uygulama bilgileri** bölmesinde aşağıdaki bilgileri yapılandırın. Bu bölmedeki değerlerden bazıları otomatik olarak doldurulabilir.
    - **Ad**: Şirket portalı'nda göründüğü gibi bir uygulama adı girin. Aynı uygulama adı iki kez kullanılmışsa, iki uygulama da Şirket Portalı’nda görüntülenir.
    - **Açıklama**: Uygulama için bir açıklama girin. Açıklama, Şirket Portalı’nda görünür.
    - **Publishe**r: Uygulama yayımcısının adını girin.
    - **Kategori**: Bir veya daha fazla yerleşik uygulama kategorilerinden birini seçin veya oluşturduğunuz bir kategoriyi seçin. Kategoriler, kullanıcıların Şirket Portalı’na göz atarken uygulamayı daha kolay bulabilmesini sağlar.
    - **Bunu şirket Portalı'nda öne çıkan uygulama olarak görüntüle**: Kullanıcılar uygulamalara göz attığında, uygulamayı şirket portalının ana sayfasında önce çıkacak şekilde görüntüleyin.
    - **Bilgi URL'si**: İsteğe bağlı olarak, uygulama hakkında bilgi içeren bir Web sitesinin URL'sini girin. URL, Şirket Portalı’nda görünür.
    - **Gizlilik URL'si**: İsteğe bağlı olarak, uygulamayla ilgili gizlilik bilgilerini içeren bir Web sitesinin URL'sini girin. URL, Şirket Portalı’nda görünür.
    - **Geliştirici**: İsteğe bağlı olarak, uygulama geliştiricisinin adını girin.
    - **Sahibi**: İsteğe bağlı olarak, bu uygulamanın sahibi için bir ad girin. Örneğin **İK departmanı**.
    - **Notları**: Bu uygulamayla ilişkilendirmek istediğiniz notları girin.
    - **Logo**: Uygulamayla ilişkilendirilen bir simgeyi karşıya yükleyin. Bu simge, kullanıcılar Şirket Portalı’na gözatarken uygulamayla birlikte görüntülenir.
3.  İşiniz bittiğinde **Tamam**’a tıklayın.

### <a name="step-4-configure-app-installation-details"></a>4. adım: Uygulama yükleme ayrıntılarını Yapılandır
1.  **Uygulama ekle** bölmesinde, uygulamanın yükleme ve kaldırma komutlarını yapılandırmak için **Program**'ı seçin.
2.  Uygulamayı yüklemek için yükleme komut satırının tamamını ekleyin. 

    Örneğin, uygulama dosyanızın adı **MyApp123** ise şunu ekleyin: `msiexec /i “MyApp123.msi”`

3.  Uygulamanın GUID'si temelinde uygulamayı kaldırmak için kaldırma komut satırının tamamını ekleyin. 

    Örneğin, `msiexec /x “{12345A67-89B0-1234-5678-000001000000}”`

    > [!NOTE]
    > Bir Win32 uygulamasını **Kullanıcı** veya **Sistem** bağlamında yüklenecek şekilde yapılandırabilirsiniz. **Kullanıcı** bağlamı yalnızca belirli bir kullanıcıyı ifade eder. **Sistem** bağlamı bir Windows 10 cihazın tüm kullanıcılarını ifade eder.
    >
    > Son kullanıcıların Win32 uygulamalarını yüklemek için cihazda oturum açmış olmaları gerekmez.

4.  İşiniz bittiğinde **Tamam**’a tıklayın.

### <a name="step-5-configure-app-requirements"></a>5. adım: Uygulama gereksinimlerini yapılandırma

1.  **Uygulama ekle** bölmesinde, uygulamayı yüklemeden önce cihazların karşılaması gereken gereksinimleri yapılandırmak için **Gereksinimler**'i seçin.
2.  **Gereksinimler** bölmesinde aşağıdaki bilgileri yapılandırın. Bu bölmedeki değerlerden bazıları otomatik olarak doldurulabilir.
    - **İşletim sistemi mimarisi**: Mimarileri uygulaması yüklemeniz gerektiğini seçin.
    - **En düşük işletim sistemi**: Uygulamayı yüklemek için gereken en düşük işletim sistemi seçin.
    - **Gerekli disk alanı (MB)**: İsteğe bağlı olarak, sistem sürücüsünde, uygulamayı yüklemek için gereken boş disk alanı ekleyin.
    - **Gerekli fiziksel bellek (MB)**: İsteğe bağlı olarak, uygulamayı yüklemek için gereken fiziksel belleği (RAM) ekleyin.
    - **En düşük gerekli mantıksal işlemcilerin sayısını**: İsteğe bağlı olarak, en az sayıda uygulamayı yüklemek için gereken bir mantıksal işlemci ekleyin.
    - **Gerekli en düşük CPU hızı (MHz)**: İsteğe bağlı olarak, uygulamayı yüklemek için gereken en düşük CPU hızı ekleyin.
3.  İşiniz bittiğinde **Tamam**’a tıklayın.

### <a name="step-6-configure-app-detection-rules"></a>6. adım: Uygulama algılama kuralları yapılandırma

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
            
            2.  Kayıt defteri değeri mevcut olup olmadığını denetleyin.
        
                ![Algılama kuralı bölmesi - kayıt defteri değeri varlığı ekran görüntüsü](./media/apps-win32-app-06.png)    
        
            3.  Kayıt defteri değer dizesinin eşitliğini denetleyin.
        
                ![Algılama kuralı bölmesi - kayıt defteri değer dizesi eşittir ekran görüntüsü](./media/apps-win32-app-07.png)    
     
    - **Özel algılama betiği kullan** – Bu uygulamayı algılamak için kullanılacak PowerShell betiğini belirtin. 
    
        1.  **Betik dosyası** – İstemcide uygulamanın varlığını algılayacak PowerShell betiğini seçin. Betik hem 0 değerinde çıkış kodu döndürdüğünde hem de STDOUT'a bir dize değeri yazdığında uygulama algılanır.

        2.  **Komut dosyası 64 bitlik istemcilerde 32 bitlik işlem olarak çalıştır** - seçin **Evet** betiği, 64 bitlik istemcilerde 32-bit işlem içinde çalıştırmak için. Seçin **Hayır** betiği, 64 bitlik istemcilerde 64-bit işlem içinde çalıştırmak için (varsayılan). 32 bitlik istemcilerde 32-bit işlem içinde betiği çalıştırın.

        3.  **Betik imzası denetimini zorla** - Betiğin güvenilen bir yayımcı tarafından imzalandığını doğrulamak için **Evet**'i seçin. Bu doğrulama betiğin hiçbir uyarı veya istem gösterilmeden çalıştırılmasına olanak tanır. Betik engellenmeden çalıştırılır. Betiği imza doğrulaması yapılmadan son kullanıcının onayıyla çalıştırmak için **Hayır**'ı (varsayılan) seçin.
    
            Intune Aracısı komut dosyası sonuçlarını denetler. Betik tarafından standart çıkış (STDOUT) akışına, standart hata (STDERR) akışına ve çıkış koduna yazılan değerleri okur. Betikten sıfırdan farklı bir değerle çıkılırsa, betik başarısız olur ve uygulama algılama durumu Yüklü Değil olur. Çıkış kodu sıfırsa ve STDOUT veri içeriyorsa, uygulama algılama durumu Yüklü'dür. 

            > [!NOTE]
            > Betikten 0 değeriyle çıkılırsa, betiğin yürütülmesi başarılı olmuştur. İkinci çıkış kanalı uygulamanın algılandığını gösterir - STDOUT verileri uygulamanın istemcide bulunduğunu gösterir. STDOUT akışından belirli bir dize beklemeyiz.

        4.  Kurallarınızı ekledikten sonra **Ekle** > **Tamam**'ı seçin.

### <a name="step-7-configure-app-return-codes"></a>7. adım: Uygulama dönüş kodları yapılandırın

1.  **Uygulama ekle** bölmesinde **Dönüş kodları**'nı seçerek, uygulama yüklemesi yeniden deneme davranışını veya yükleme sonrası davranışını belirtmek için kullanılan dönüş kodlarını ekleyin. Dönüş kodu girdileri varsayılan olarak uygulama oluşturma işlemi sırasında eklenir. Bununla birlikte, başka dönüş kodları ekleyebilir veya mevcut dönüş kodlarını değiştirebilirsiniz. 
2.  **Dönüş kodları** bölmesinde, başka dönüş kodları ekleyin veya mevcut dönüş kodlarında değişiklik yapın.
    - **Başarısız** – bir uygulama yükleme hatası gösteren dönüş değeri.
    - **Donanımdan önyükleme** – Donanımdan önyükleme dönüş kodu, istemcide önyükleme yapılmadan sonraki Win32 uygulamalarının yüklenmesine izin vermez. 
    - **Yazılımdan önyükleme** – Yazılımdan önyükleme dönüş kodu, istemci önyüklemesine gerek kalmadan sonraki Win32 uygulamasının yüklenmesine izin verir. Geçerli uygulamanın yüklemesini tamamlamak için önyükleme gereklidir.
    - **Yeniden deneme** – Yeniden deneme dönüş koduyla aracı uygulamayı yüklemeyi üç kez dener. Her denemeden sonra 5 dakika bekler. 
    - **Başarılı** – Uygulamanın başarıyla yüklendiğini belirten dönüş kodu.
3.  Dönüş kodları listenizdeki eklemeleri veya değişiklikleri yaptıktan sonra **Tamam**'ı seçin.

### <a name="step-8-add-the-app"></a>8. adım: Uygulama ekleme

1.  **Uygulama ekle** bölmesinde, uygulama bilgilerini doğru yapılandırdığınızı onaylayın.
2.  Uygulamayı Intune'a yüklemek için **Ekle**’yi seçin.

### <a name="step-9-assign-the-app"></a>9. adım: Uygulama atama

1.  Uygulama bölmesinde **Atamalar**’ı seçin.
2.  Uygulamayla ilgili **Grup ekle** bölmesini açmak için **Grup Ekle**'yi seçin.
3.  Belirli bir uygulama için **atama türü** seçin:
    - **Kayıtlı cihazlar için kullanılabilir**: Kullanıcılar uygulamayı şirket Portalı Web sitesine veya Şirket portalı uygulamasını yükleyin.
    - **Gerekli**: Uygulama seçilen gruplardaki cihazlara yüklenir.
    - **Kaldırma**: Uygulama, seçilen gruplardaki cihazlardan kaldırılır.
4.  **Eklenen Gruplar**'ı seçin ve bu uygulamayı kullanacak grupları atayın.
5.  Dahil edilen gruplar seçimini tamamlamak için **Ata** bölmesinde **Tamam**'ı seçin.
6.  Herhangi bir kullanıcı grubunun bu uygulama atamasından etkilenmesini istemiyorsanız, **Grupları Dışla**'yı seçin.
7.  **Grup ekle** bölmesinde **Tamam**’ı seçin.
8.  Uygulamanın **Atamalar** bölmesinde **Kaydet**'i seçin.

Bu noktada Intune'a Win32 uygulaması ekleme adımlarını tamamlamış oldunuz. Uygulama atama ve izleme hakkında bilgi için bkz. [Microsoft Intune ile uygulamaları gruplara atama](https://docs.microsoft.com/intune/apps-deploy) ve [Microsoft Intune ile uygulama bilgilerini ve atamalarını izleme](https://docs.microsoft.com/intune/apps-monitor).

## <a name="delivery-optimization"></a>Teslim iyileştirme

Windows 10 1709 ve üzerindeki istemciler Windows 10 istemci üzerinde bir teslim iyileştirme bileşenini kullanarak Intune Win32 uygulama içeriği karşıdan yükler. Teslim iyileştirme, varsayılan olarak açık eşler arası işlevsellik sağlar. Teslim iyileştirme, Grup İlkesi tarafından ve Intune cihaz yapılandırması aracılığıyla yapılandırılabilir. Daha fazla bilgi için [Windows 10 için teslim iyileştirme](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization). 

## <a name="install-required-and-available-apps-on-devices"></a>Gerekli ve kullanılabilir uygulamaları cihazlara yükleme

Son kullanıcı gerekli ve kullanılabilir uygulama yüklemeleri için Windows kutlama bildirimleri görürsünüz. Aşağıdaki resimde, cihaz yeniden başlatılana kadar uygulama yüklemesinin tamamlanmayacağına ilişkin bildirim örneği gösterilir. 

![Bir uygulama yükleme için ekran görüntüsü, Windows kutlama bildirimleri](./media/apps-win32-app-08.png)    

Aşağıdaki görüntüde, cihaza uygulama değişiklikler yapılmıştır son kullanıcıyı uyarır.

![Uygulama değişikliklerini yapılan kullanıcıya bildirimde ekran görüntüsü](./media/apps-win32-app-09.png)    

## <a name="toast-notifications-for-win32-apps"></a>Win32 uygulamaları için kutlama bildirimleri 
Gerekirse, uygulama ataması başına gösteren son kullanıcı bildirimleri gösterilmemesini sağlayabilirsiniz. Intune'dan seçin **istemci uygulamaları** > **uygulamaları** > uygulamayı seçin > **Assignemnts** > **grupları dahil**. 

## <a name="troubleshoot-win32-app-issues"></a>Win32 uygulamasında sorun giderme
İstemci makinesindeki aracı günlükleri genellikle `C:\ProgramData\Microsoft\IntuneManagementExtension\Logs` yolunda bulunur. Bu günlük dosyalarını görüntülemek için `CMTrace.exe` dosyasından yararlanabilirsiniz. *CMTrace.exe*, [SCCM İstemci Araçları](https://docs.microsoft.com/sccm/core/support/tools)'ndan indirilebilir. 

![Aracısı'nın ekran görüntüsü istemci makinesine kaydeder](./media/apps-win32-app-10.png)    

> [!IMPORTANT]
> Uygun yükleme ve yürütme Win32 LOB uygulamalarını izin vermek için kötü amaçlı yazılımdan koruma ayarları aşağıdaki dizinlerin taranmasını dışlamanız gerekir:<p>
> **X64 istemci makineleri**:<br>
> *C:\Program dosyaları (x86) \Microsoft Intune Yönetimi Extension\Content*<br>
> *C:\windows\IMECache*
>  
> **X86 istemci makineleri**:<br>
> *C:\Program Files\Microsoft Intune Yönetimi Extension\Content*<br>
> *C:\windows\IMECache*

Win32 uygulamaları sorunlarını giderme hakkında daha fazla bilgi için bkz. [Win32 uygulama yükleme sorunlarını giderme](troubleshoot-app-install.md#win32-app-installation-troubleshooting).

### <a name="troubleshooting-areas-to-consider"></a>Dikkate alınacak sorun giderme alanları
- Aracının cihazda yüklü olduğundan emin olmak için hedefi denetleyin - Bir grubu hedefleyen Win32 uygulaması veya bir grubu hedefleyen PowerShell Betiği, güvenlik grubu için aracı yükleme ilkesi oluşturur.
- İşletim sistemi sürümünü denetleyin – Windows 10 1607 veya üzeri.  
- Windows 10 SKU'sunu denetleyin - Windows 10 S veya S modu etkinleştirilmiş olarak çalışan Windows sürümleri MSI yüklemesini desteklemez.

## <a name="next-steps"></a>Sonraki adımlar

- Intune'a uygulamaları ekleme hakkında daha fazla bilgi için bkz. [Microsoft Intune'a uygulama ekleme](apps-add.md).
