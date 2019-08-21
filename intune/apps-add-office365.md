---
title: Microsoft Intune kullanarak Windows 10 cihazlarına Office 365 uygulamaları atama
titleSuffix: ''
description: Windows 10 cihazlarına Office 365 uygulamalarını yüklemek için Microsoft Intune nasıl kullanabileceğinizi öğrenin.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/15/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3292671a-5f5a-429e-90f7-b20019787d22
ms.reviewer: craigma
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seoapril2019
ms.collection: M365-identity-device-management
ms.openlocfilehash: eff9f965649587a929e45d0f9d59305194ffe68b
ms.sourcegitcommit: b1ddc7f4a3d520b7d6755c7a423a46d1e2548592
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69651157"
---
# <a name="assign-office-365-apps-to-windows-10-devices-with-microsoft-intune"></a>Microsoft Intune ile Office 365 uygulamalarını Windows 10 cihazlara atama

Uygulamaları atama, izleme, yapılandırma veya korumadan önce bunları Intune’a eklemelisiniz. Kullanılabilir [uygulama türlerinden](apps-add.md#app-types-in-microsoft-intune) biri, Windows 10 cihazları için Office 365 uygulamalarıdır. Intune 'da bu uygulama türünü seçerek, Windows 10 çalıştıran yönettiğiniz cihazlara Office 365 uygulamaları atayabilir ve yükleyebilirsiniz. Ayrıca, lisanslarınız varsa Microsoft Project Online masaüstü istemcisi ve Microsoft Visio Online Plan 2 için de uygulamalar atayabilir ve yükleyebilirsiniz. Kullanılabilir Office 365 uygulamaları, Azure 'daki Intune konsolundaki uygulamalar listesinde tek bir girdi olarak görüntülenir.

> [!NOTE]
> Microsoft Intune aracılığıyla dağıtılan Office 365 ProPlus uygulamalarını etkinleştirmek için Office 365 ProPlus lisansları kullanmanız gerekir. Şu anda Office 365 Business sürümü Intune tarafından desteklenmemektedir.

## <a name="before-you-start"></a>Başlamadan önce

> [!IMPORTANT]
> Son kullanıcının cihazında .msi Office uygulamaları varsa, bu uygulamaları güvenle kaldırmak için **MSI'yi kaldır** özelliğini kullanmalısınız. Aksi takdirde, Intune tarafından teslim edilen Office 365 uygulamaları yüklenemez.

- Bu uygulamaları dağıtacağınız cihazların Windows 10 Creators Update veya üzerini çalıştırıyor olması gerekir.
- Intune, yalnızca Office 365 paketinden Office uygulamaları eklemeyi destekler.
- Intune uygulama paketini yüklerken herhangi bir Office uygulaması açıksa yükleme başarısız olabilir ve kullanıcılar kaydedilmeyen dosyalardaki veriler kaybedebilir.
- Bu yükleme yöntemi Windows Home, Windows Team, Windows holographic veya Windows holographic for Business cihazlarında desteklenmez.
- Intune, daha önce Intune ile Office 365 uygulamalarını dağıttığınız bir cihaza Microsoft Mağazası’ndan Office 365 masaüstü uygulamalarının (Office Centennial uygulamaları olarak bilinir) yüklenmesini desteklemez. Bu yapılandırmayı yüklerseniz veri kaybına veya bozulmasına neden olabilir.
- Birden fazla gerekli veya kullanılabilir uygulama ataması aynı anda çalışmaz. Bir uygulama ataması, kendinden önce yüklenmiş diğer uygulama atamalarının üzerine yazar. Örneğin ilk Office uygulamaları kümesi Word’ü barındırıyor ve sonraki barındırmıyorsa, Word kaldırılır. Bu koşul Visio ve Project uygulamaları için geçerli değildir.
- Multi-Office 365 dağıtımları Şu anda desteklenmemektedir. Cihaza yalnızca bir dağıtım gönderilir
- **Office sürümü** - Office’in hangi sürümünü (32 bit veya 64 bit) atamak istediğinizi seçin. 32 bit sürümünü hem 32 bit hem de 64 bit cihazlara yükleyebilirsiniz ancak 64 bit sürümünü yalnızca 64 bit cihazlara yükleyebilirsiniz.
- **Son kullanıcı cihazlarından MSI’yi kaldırma** - Son kullanıcı cihazlarında önceden var olan Office .MSI uygulamalarını kaldırmak isteyip istemediğinizi belirtin. Son kullanıcı cihazlarında önceden var olan Office .MSI uygulamaları bulunuyorsa yükleme başarısız olur. Kaldırılacak uygulamalar, **Uygulama Paketini Yapılandır** altında yükleme için seçilen uygulamalarla sınırlı değildir çünkü tüm Office (MSI) uygulamalarını son kullanıcı cihazından kaldıracaktır. Daha fazla bilgi için bkz. [Office 365 ProPlus’a yükseltirken mevcut Office MSI sürümlerini kaldırma](https://docs.microsoft.com/deployoffice/upgrade-from-msi-version). Intune son kullanıcı makinenize Office’i yeniden yüklediğinde, son kullanıcılar önceki .MSI Office yüklemeleri ile aldıkları aynı dil paketini otomatik olarak alır.

## <a name="get-started"></a>başlarken

1. [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)'da oturum açın.
3. **Intune** bölmesinde **İstemci uygulamaları**’nı seçin.
4. **İstemci uygulamaları** iş yükü bölmesindeki **Yönet**’in altında **Uygulamalar**’ı seçin.
5. **Add (Ekle)** seçeneğini belirleyin.
6. **Uygulama ekle** bölmesindeki **Uygulama türü** listesinde bulunan **Office 365 Suite**’in altında **Windows 10**’u seçin.

## <a name="select-settings-format"></a>Ayarlar biçimini seçin

Bir **Ayarlar biçimi**seçerek uygulama ayarını yapılandırmak için bir yöntem seçebilirsiniz. Biçim seçeneklerini ayarlama şunları içerir:
- Yapılandırma Tasarımcısı
- XML verilerini girme

**Yapılandırma Tasarımcısı** ' nı seçtiğinizde, **Uygulama Ekle** dikey penceresi iki ek ayar seçeneği sunmak üzere değişecektir:
- Uygulama paketini Yapılandır
- Uygulama paketi ayarları

<img alt="Add Office 365 - Configuration designer" src="./media/apps-add-office365/apps-add-office365-02.png" width="700">

**XML verisi gir** ' i SEÇTIĞINIZDE, **XML verisi gir** seçeneğini görüntüle seçeneği ile **Uygulama Ekle** dikey penceresine tıklayın. **Yapılandırma dosyası** dikey penceresini göstermek için bunu seçin. 

![Office 365 yapılandırma Tasarımcısı ekleme](./media/apps-add-office365/apps-add-office365-01.png)
    
**XML verisi gir** seçeneği hakkında daha fazla bilgi için bkz. [XML verilerini girin](apps-add-office365.md#enter-xml-format) .

## <a name="configure-app-suite-information"></a>Uygulama paketi bilgilerini Yapılandır

Bu adımda, uygulama paketi hakkında bilgi sağlarsınız. Bu bilgiler, Intune'da uygulama paketini bulmanıza yardımcı olur ve kullanıcıların Şirket Portalı'nda paketi bulması kolaylaşır.

1. **Uygulama Ekle** bölmesinde **Uygulama Paketi Bilgileri**’ni seçin.
2. **Uygulama Paketi Bilgileri** bölmesinde aşağıdakileri yapın:
    - **Paket adı**: Uygulama paketinin Şirket portalı 'nda görüntülendiği şekilde adını girin. Kullandığınız tüm paket adlarının benzersiz olduğundan emin olun. Aynı uygulama paketi adı iki kez kullanılmışsa uygulamalardan yalnızca biri şirket portalında kullanıcılara görüntülenir.
    - **Paket açıklaması**: Uygulama paketi için bir açıklama girin. Örneğin dahil etmek üzere seçtiğiniz uygulamaları listeleyebilirsiniz.
    - **Yayımcı**: Microsoft, yayımcı olarak görünür.
    - **Kategori**: İsteğe bağlı olarak, yerleşik uygulama kategorilerinden birini veya oluşturduğunuz bir kategoriyi seçin. Bu ayar, kullanıcıların şirket portalına göz atarken uygulama paketlerini daha kolay bulabilmesini sağlar.
    - **Şirket Portalı’nda bu uygulamayı öne çıkan uygulama olarak görüntüle**: Kullanıcılar uygulamalara göz attığında, uygulama paketini şirket portalının ana sayfasında önce çıkacak şekilde görüntülemek için bu seçeneği belirleyin.
    - **Bilgi URL'si**: İsteğe bağlı olarak, bu uygulama hakkında bilgi içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Gizlilik URL’si**: İsteğe bağlı olarak, bu uygulamayla ilgili gizlilik bilgilerini içeren bir web sitesinin URL’sini girin. URL, şirket portalında kullanıcılara görüntülenir.
    - **Geliştirici**: Microsoft, geliştirici olarak görünür.
    - **Sahip**: Microsoft, sahip olarak görünür.
    - **Notlar**: Bu uygulamayla ilişkilendirmek istediğiniz notları girin.
    - **Logo**: Office 365 logosu, kullanıcılar şirket portalına gözatarken uygulamayla birlikte görüntülenir.
3. **Tamam**’ı seçin.

## <a name="configure-app-suite"></a>Uygulama paketini Yapılandır

**Biçim biçimlendirme** açılan kutusu altında **yapılandırma Tasarımcısı** seçeneğini belirlediyseniz, **Uygulama Ekle** dikey penceresinde **uygulama paketi yapılandırma** seçeneğini görürsünüz. Cihazlara atamak istediğiniz Office uygulamalarını seçin.

1. **Uygulama Ekle** bölmesinde **Uygulama Paketini Yapılandır**’ı seçin.
2. **Uygulama Paketini Yapılandır** bölmesinde, cihazlara atamak istediğiniz standart Office uygulamalarını seçin.  
    Ayrıca, lisanslarınız varsa Microsoft Project Online masaüstü istemcisi ve Microsoft Visio Online Plan 2 için de uygulamalar yükleyebilirsiniz.
3. **Tamam**’ı seçin.

## <a name="configure-app-suite-settings"></a>Uygulama paketi ayarlarını yapılandırma

**Biçim biçimlendirme** açılan kutusu altında **yapılandırma Tasarımcısı** seçeneğini belirlediyseniz, **Uygulama Ekle** dikey penceresinde **uygulama paketi ayarları** seçeneğini görürsünüz. Bu adımda, uygulama paketi için yükleme seçeneklerini yapılandırın. Pakete eklediğiniz tüm uygulamalar için bu ayarlar uygulanır.

1. **Uygulama Ekle** bölmesinde **Uygulama Paketi Ayarları**’nı seçin.
2. **Uygulama Paketi Ayarları** bölmesinde aşağıdakileri yapın:
    - **Office sürümü**: Office 'in 32-bit veya 64 bit sürümünü atamak isteyip istemediğinizi seçin. 32 bit sürümünü hem 32 bit hem de 64 bit cihazlara yükleyebilirsiniz ancak 64 bit sürümünü yalnızca 64 bit cihazlara yükleyebilirsiniz.
    - **Güncelleştirme kanalı**: Cihazlarda Office 'in nasıl güncelleştirileceğini seçin. Çeşitli güncelleştirme kanalları hakkında bilgi için bkz. [Office 365 ProPlus güncelleştirme kanallarına genel bakış](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus). Aşağıdakilerden birini seçin:
        - **Aylık**
        - **Aylık (Hedeflenen)**
        - **Yarı Yıllık**
        - **Yarı Yıllık (Hedeflenen)**

        Kanal seçtikten sonra isteğe bağlı olarak son kullanıcı cihazlarında seçili kanal için belirli bir Office sürümünü yüklemek için **Belirli**’yi seçin. Daha sonra Office’in **Belirli bir sürümünü** seçip kullanabilirsiniz.
        
        Kullanılabilir sürümler zaman içerisinde değişir. Bu neden yeni bir dağıtım oluştururken kullanılabilir sürümler daha yeni olabilir ve bazı eski sürümleri bulamayabilirsiniz. Mevcut dağıtımlar eski sürümü dağıtmaya devam eder ancak her kanaldaki sürüm listesi sürekli olarak güncelleştirilir.
        
        Sabitlenmiş sürümlerini güncelleştiren (veya diğer özelliklerini güncelleştiren) ve kullanılabilir olarak dağıtılan cihazlar için raporlama durumu, iade etme işlemi gerçekleşene kadar cihaz önceki sürümü yüklerse Yüklendi olarak görünür. Cihaz iade etme işlemi gerçekleştiğinde ise durum geçici olarak Bilinmiyor olur ancak kullanıcıya gösterilmez. Kullanıcı, kullanılabilir yeni sürümü yüklemeye başladığında durumu Yüklendi olarak görür.
        
        Daha fazla bilgi için bkz. [Office 365 ProPlus güncelleştirme kanallarına genel bakış](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus).

    - **Son kullanıcı cihazlarından MSI’yi kaldırma** - Son kullanıcı cihazlarında önceden var olan Office .MSI uygulamalarını kaldırmak isteyip istemediğinizi belirtin. Son kullanıcı cihazlarında önceden var olan Office .MSI uygulamaları bulunuyorsa yükleme başarısız olur. Kaldırılacak uygulamalar, **Uygulama Paketini Yapılandır** altında yükleme için seçilen uygulamalarla sınırlı değildir çünkü tüm Office (MSI) uygulamalarını son kullanıcı cihazından kaldıracaktır. Daha fazla bilgi için bkz. [Office 365 ProPlus’a yükseltirken mevcut Office MSI sürümlerini kaldırma](https://docs.microsoft.com/deployoffice/upgrade-from-msi-version). Intune son kullanıcı makinenize Office’i yeniden yüklediğinde, son kullanıcılar önceki .MSI Office yüklemeleri ile aldıkları aynı dil paketini otomatik olarak alır. 
    - **Uygulama Son Kullanıcı Lisans sözleşmesini otomatik olarak kabul et**: Son kullanıcıların lisans sözleşmesini kabul etmesine gerek yoksa bu seçeneği belirleyin. Ardından Intune, sözleşmeyi otomatik olarak kabul eder.
    - **Paylaşılan bilgisayar etkinleştirmesini kullan**: Birden çok kullanıcı bir bilgisayarı paylaşıyorsa bu seçeneği belirleyin. Daha fazla bilgi için bkz. [Office 365 için paylaşılan bilgisayar etkinleştirmeye genel bakış](https://docs.microsoft.com/DeployOffice/overview-of-shared-computer-activation-for-office-365-proplus).
    - **Diller**: Office, son kullanıcının cihazında Windows ile yüklenen desteklenen dillerin herhangi birine otomatik olarak yüklenir. Uygulama paketiyle birlikte ilave diller yüklemek istiyorsanız bunu seçin. <p></p>
    Intune üzerinden yönetilen Office 365 Pro Plus uygulamaları için ek diller dağıtabilirsiniz. Kullanılabilir diller listesi, dil paketinin **Tür** bilgisini içerir (çekirdek, kısmı ve yazım denetleme). Azure portalında **Microsoft Intune** > **İstemci uygulamaları** > **Uygulamalar** > **Ekle**’yi seçin. **Uygulama ekle** dikey penceresindeki **Uygulama türü** listesinde **Office 365 Paketi** altından **Windows 10**'u seçin. **Uygulama Paketi Ayarları** dikey penceresinde **Diller**'i seçin. Ek bilgi için bkz: [Office 365 ProPlus'ta dil dağıtmaya genel bakış](https://docs.microsoft.com/deployoffice/overview-of-deploying-languages-in-office-365-proplus).

## <a name="select-scope-tags-optional"></a>Kapsam etiketlerini seçin (isteğe bağlı)
Intune 'da istemci uygulama bilgilerini kimlerin görebileceğini anlamak için kapsam etiketlerini kullanabilirsiniz. Kapsam etiketleri hakkında tam Ayrıntılar için bkz. [Dağıtılmış BT için rol tabanlı erişim denetimi ve kapsam etiketleri kullanma](scope-tags.md).

1. **Kapsam (Etiketler)**  > **Ekle**öğesini seçin.
2. Kapsam etiketlerini aramak için **Seç** kutusunu kullanın.
3. Bu uygulamaya atamak istediğiniz kapsam etiketlerinin yanındaki onay kutusunu işaretleyin.
4. **Seç** > **Tamam**'ı seçin.

## <a name="enter-xml-format"></a>XML biçimi girin

**Biçim biçimlendirme** açılan kutusu altında **XML verisi gir** seçeneğini belirlediyseniz, **Uygulama Ekle** dikey penceresinde **XML biçimi gir** seçeneğini görürsünüz. Daha fazla bilgi için bkz. [Office dağıtım aracı Için yapılandırma seçenekleri](https://docs.microsoft.com/DeployOffice/configuration-options-for-the-office-2016-deployment-tool).

## <a name="finish-up"></a>Bitirme

İşiniz bittiğinde, **Uygulama Ekle** bölmesinde **Ekle**’yi seçin. Oluşturduğunuz uygulama, uygulamalar listesinde gösterilir.

## <a name="troubleshooting"></a>Sorun giderme
Intune, Office [365 CDN](https://docs.microsoft.com/office365/enterprise/content-delivery-networks)'yi kullanarak Office 365 ProPlus 'ı istemci bilgisayarlarınıza indirip dağıtmak Için [Office dağıtım aracı](https://docs.microsoft.com/DeployOffice/overview-of-the-office-2016-deployment-tool) 'nı kullanır. Ağ yapılandırmanızın, istemcilerin, gereksiz noktaya giriş yapmaktan kaçınmak için merkezi proxy 'ler aracılığıyla CDN trafiğini yönlendirmek yerine doğrudan CDN 'ye erişmesine izin verdiğinden emin olmak için, [Office 365 uç noktalarını yönetme](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints) bölümünde özetlenen en iyi yöntemlere başvurun dönemlerinde.

Yükleme veya çalışma zamanı sorunlarıyla karşılaşırsanız, hedeflenen bir cihazda [Office 365 için Microsoft desteği ve Kurtarma Yardımcısı](https://diagnostics.office.com) 'nı çalıştırın.

## <a name="errors-during-installation-of-the-app-suite"></a>Uygulama paketinin yüklenmesi sırasında karşılaşılan hatalar

Ayrıntılı yükleme günlüklerinin nasıl görüntüleneceği hakkında bilgi için bkz. [Office 365 ProPlus ULS günlüğünü etkinleştirme](https://blogs.technet.microsoft.com/odsupport/2018/06/18/how-to-enable-office-365-proplus-uls-logging) .

Karşınıza çıkabilecek yaygın hata kodları ve anlamları, aşağıdaki tablolarda listelenmiştir.

### <a name="status-for-office-csp"></a>Office CSP durumu

| Durum | Aşama | Açıklama |
|--------------------------------------------------|--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1460 (ERROR_TIMEOUT) | İndir | Office Dağıtım Aracı’nı indirme başarısız |
| 13 (ERROR_INVALID_DATA) | - | İndirilen Office Dağıtım Aracı’nın imzası doğrulanamıyor |
| CertVerifyCertificateChainPolicy hata kodu | - | İndirilen Office Dağıtım Aracı için sertifika denetimi başarısız |
| 997 | Süren İş | Yükleniyor |
| 0 | Yükleme sonrası | Yükleme başarılı |
| 1603 (ERROR_INSTALL_FAILURE) | - | Şu gibi önkoşul denetimi başarısız oldu: SxS (2016 MSI yüklendiğinde yüklenmeye çalışıldı) sürüm hatalı Matchoınstler |
| 0x8000ffff (E_UNEXPECTED) | - | Makinede Tıkla-Çalıştır Office yokken kaldırılmaya çalışıldı |
| 17002 | - | Senaryoyu tamamlama başarısız (yükleme). Olası nedenler: yükleme işlemi kullanıcı tarafından iptal edildi yükleme sırasında başka bir ınstaldisk alanı tarafından iptal edildi bilinmeyen dil KIMLIĞI |
| 17004 | - | Bilinmeyen SKU’lar |


### <a name="office-deployment-tool-error-codes"></a>Office Dağıtım Aracı hata kodları

| Senaryo | Dönüş kodu | Kullanıcı Arabirimi | Not |
|------------------------------------------------------------------------------------------------------------------|---------------------------------------|----------------------------------------------------|------------------------------------|
| Etkin bir Tıkla-Çalıştır yükleme yokken kaldırma çabası | -2147418113, 0x8000ffff veya 2147549183 | Hata kodu: 30088-1008Hata kodu: 30125-1011 (404) | Office Dağıtım Aracı |
| MSI sürümü yüklü olduğunda yükleyin | 1603 | - | Office Dağıtım Aracı |
| Yükleme, kullanıcı veya başka bir yükleme tarafından iptal edildi | 17002 | - | Tıkla-Çalıştır |
| 32 bit yüklü olan bir cihaza 64 bit yüklemeyi deneyin. | 1603 | - | Office Dağıtım Aracı dönüş kodu |
| Bilinmeyen bir SKU yüklemeyi deneyin (yalnızca geçerli SKU’lardan geçmemiz gerektiğinden, Office CSP için yasal bir kullanım durumu değildir) | 17004 | - | Tıkla-Çalıştır |
| Yetersiz alan | 17002 | - | Tıkla-Çalıştır |
| Tıkla-Çalıştır istemcisi başlatılamadı (beklenmeyen) | 17000 | - | Tıkla-Çalıştır |
| Tıkla-Çalıştır istemcisi, senaryoyu kuyruğa alamadı (beklenmeyen) | 17001 | - | Tıkla-Çalıştır |

## <a name="next-steps"></a>Sonraki adımlar

- Uygulamaları seçtiğiniz gruplara atamak için bkz. [Uygulamaları gruplara atama](/intune-azure/manage-apps/deploy-apps).
