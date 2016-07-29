---
title: "iOS uygulamalarını Uygulama Sarmalama Aracı’yla sarmalama | Microsoft Intune"
description: "iOS uygulamalarınızı, uygulamanın kendi kodunda değişiklik yapmadan sarmalamayı öğrenmek için bu konu başlığı altındaki bilgileri kullanın. Mobil uygulama yönetimi ilkelerini uygulayabilmek için uygulamaları hazırlayın."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 99ab0369-5115-4dc8-83ea-db7239b0de97
ms.reviewer: matgates
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 19a5b8f8260bace2bbe3626da3df281306f53024
ms.openlocfilehash: ebd68513da55b8bb1715d2c82636abf791cae1ff


---

# Intune Uygulama Sarmalama Aracı ile iOS uygulamalarını mobil uygulama yönetimi için hazırlama
Şirket içi iOS uygulamalarının davranışını, uygulamanın kodunu değiştirmeden uygulama özelliklerini kısıtlayarak değiştirmek için **iOS için Microsoft Intune Uygulama Sarmalama Aracı**'nı kullanın.

Bir uygulama, bir uygulama etrafında 'sarıcı' oluşturan bir Mac OS komut satırı uygulamasıdır. Bir uygulama işlendikten sonra, yapılandırdığınız [mobil uygulama yönetimi ilkelerini](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) kullanarak uygulamaların işlevini değiştirebilirsiniz.

Aracı indirmek için bkz. [iOS için Microsoft Intune Uygulama Sarmalama Aracı](http://www.microsoft.com/en-us/download/details.aspx?id=45218).

## 1. Adım Uygulama sarmalama aracını kullanmak için önkoşulları karşılama

|Gereksinim|Daha fazla bilgi|
|---------------|--------------------------------|
|Desteklenen işletim sistemi ve araç takımı|Uygulama sarmalama aracını, XCode araç takımının sürüm 5 veya üzerinin yüklü olduğu OS X 10.8.5 ya da üzerini çalıştıran bir Mac bilgisayarda çalıştırmalısınız.|
|İmzalama sertifikası ve sağlama profili|Bir Apple imzalama sertifikanız ve sağlama profiliniz olmalıdır. [Apple geliştirici belgelerinize](https://developer.apple.com/) bakın.|
|Uygulama Sarmalama Aracı’yla bir uygulamayı işleme|Uygulamalar şirketiniz veya bağımsız bir yazılım satıcısı (ISV) tarafından geliştirilmiş ve imzalanmış olmalıdır. Bu aracı Apple Store'dan edinilen uygulamaları işlemek için kullanamazsınız. Uygulamalar iOS 7.0 veya üzeri için yazılmış olmalıdır. Ayrıca uygulamalar Konumdan Bağımsız Yürütülebilir (PIE) biçiminde olmalıdır. PIE biçimi hakkında daha fazla bilgi için Apple geliştirici belgelerinize bakın. Son olarak, uygulamanın uzantısı **.app** veya **.ipa** olmalıdır.|
|Sarmalama aracının işleyemediği uygulamalar|Şifrelenmiş uygulamalar, imzalanmamış uygulamalar ve genişletilmiş dosya öznitelikleri olan uygulamalar.|
|Azure Active Directory Library’yi (ADAL) kullanan uygulamalar|Uygulamanız ADAL kullanıyorsa, uygulama 1.0.2 veya daha büyük bir ADAL sürümü içermelidir ve geliştirici kendi uygulama erişimini Intune Mobil Uygulama Yönetimi kaynağına vermelidir.<br /><br />ADAL’ın kullanımı hakkındaki ayrıntılar için bu makalede [Azure Active Directory Library’yi kullanan uygulamalarla ilgili bilgiler](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md#information-for-apps-that-use-the-azure-active-directory-library) bölümüne bakın.|
|Uygulamanız için yetkilendirmeleri ayarlama|Uygulamayı sarmalamadan önce, uygulamaya normal olarak verilenlerin ötesinde ek izinler ve yetenekler veren yetkilendirmeler ayarlamanız gerekir. Yönergeler için bkz. [Uygulama yetkilendirmelerini ayarlama](#setting-app-entitlements).|

## 2. Adım: Uygulama sarmalama aracını yükleme

1.  [Microsoft İndirme Merkezi](https://www.microsoft.com/download/details.aspx?id=45218)’nin **iOS için Microsoft Intune Uygulama Sarmalama Aracı** sayfasından, uygulama sarmalama aracının yükleme dosyasını bir Mac bilgisayara indirin.

2.  Mac bilgisayarında, **Microsoft Intune App Wrapping Tool for iOS.dmg** adlı yükleme dosyasına çift tıklayın.

3.  Son Kullanıcı Lisans Sözleşmesi'ni (EULA) kabul etmek için **Kabul et**’i seçin. Yükleyici bağlanır ve Mac bilgisayarda görüntülenir.

4.  Yükleyici açın ve görüntülenen dosyaları Mac bilgisayarda yeni bir klasöre kopyalayın. Artık takılı olan yükleyici sürücüsünün bağlantısını kesebilirsiniz.

    Artık uygulama sarmalama aracını çalıştırmaya hazırsınız.

## 3. Adım: Uygulama sarmalama aracını çalıştırma

1.  Mac bilgisayarda, bir Terminal penceresi açın ve dosyaları kaydettiğiniz klasöre gidin. Yürütülebilir dosya paketin içinde olduğundan, komutu aşağıdaki şekilde çalıştırmanız gerekir:
```
    ./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager –i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> –p /<path to provisioning profile> –c <SHA1 hash of the certificate> -a <client ID of input app> -r <reply URI of input app> -v true
```
    > [!NOTE]
    > Some parameters are optional as shown in the table below.

    **Example:** The following example command runs the app wrapping tool on an app named **MyApp.ipa**. A provisioning profile and SHA-1 hash are specified. The processed app is created and stored in the **/users/myadmin/Documents** on the Mac computer.

    ```
    /users/myadmin/Downloads/IntuneMAMPackager.app/Contents/MacOS/IntuneMAMPackager -i /users/myadmin/Downloads/MyApp.ipa -o /users/myadmin/Documents/MyApp_Wrapped.ipa -p /users/myadmin/Downloads/My_Provisioning_Profile_.mobileprovision -c 12A3BC45D67EF8901A2B3CDEF4ABC5D6E7890FAB –a 20e1cd0d-268e-4308-9583-02ae97dd353e –r https://contoso/ -v true
    ```
    You can use the following command line properties with the app wrapping tool:

|Özellik|Daha fazla bilgi|
  |------------|--------------------|
  |**-h**|Uygulama sarmalama aracı için kullanılabilir komut satırı özelliklerini görüntüler.|
  |**-i**|Giriş uygulamasının yolunu ve dosya adını belirtir.|
  |**-o**|İşlenen uygulamanın kaydedileceği yolu belirtir.|
  |**-p**|iOS uygulamaları için sağlama profilinizin yolunu belirtir.|
  |**-c**|İmzalama sertifikasının SHA1 karmasını belirtir.|
  |**-a**|Uygulama Azure Active Directory Kitaplıkları kullanıyorsa giriş uygulamasının GUID biçimindeki istemci kimliği (İsteğe bağlı).|
  |**-r**|Uygulama Azure Active Directory Kitaplıkları kullanıyorsa, giriş uygulamasının URI'sini yeniden yönlendir (İsteğe bağlı).|
  |**-v**|Konsola ayrıntılı ileti çıkışı yap (İsteğe bağlı).|

2. İşlem tamamlandıktan sonra **Uygulama başarıyla sarmalandı** iletisi görüntülenir.

    Bir hata oluşursa yardım için [hata iletileri](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md#error-messages) sayfasına bakın.

3.  Sarmalanan uygulama, daha önce belirttiğiniz çıkış klasörüne kaydedilir. Şimdi uygulamayı [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] hizmetine yükleyebilir ve bir mobil uygulama yönetimi ilkesi ile ilişkilendirebilirsiniz.

    > [!IMPORTANT]
    > Uygulamayı yeni bir uygulama olarak yüklemeniz gerekir. Uygulamanın daha eski, sarmalanmamış bir sürümünü güncelleştiremezsiniz.

    Şimdi uygulamayı [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] gruplarınıza dağıtabilirsiniz ve uygulama artık cihazda belirttiğiniz uygulama kısıtlamalarını kullanarak çalıştırılır.

## Hata iletileri ve günlük dosyaları
Uygulama sarmalama aracında karşılaştığınız sorunları gidermek için aşağıdaki bilgileri kullanın.

### Hata iletileri
Uygulama sarmalama aracı başarılı bir şekilde tamamlanamazsa, aşağıdaki hata iletilerinden biri görüntülenir:

|Hata iletisi|Daha fazla bilgi|
|-----------------|--------------------|
|Geçerli bir iOS sağlama profili belirtmeniz gerekir.|Sağlama profiliniz geçerli olmayabilir. Cihazlar için doğru izinlere sahip olduğunuzdan ve profilinizin geliştirmeyi ya da dağıtımı doğru hedeflediğinden emin olun. Sağlama profilinizin süresi dolmuş da olabilir.|
|Geçerli bir giriş uygulaması adı belirtin.|Belirttiğiniz giriş uygulaması adının doğru olduğundan emin olun.|
|Çıkış uygulaması için geçerli bir yol belirtin.|Belirttiğiniz çıkış uygulaması yolunun var olduğundan ve doğru olduğundan emin olun.|
|Geçerli bir giriş sağlama profili belirtin.|Geçerli bir sağlama profili adı ve uzantısı sağladığınızdan emin olun. Sağlama profilinizde eksik yetkilendirmeler olabilir veya **–p** komut satırı seçeneğini eklememiş olabilirsiniz.|
|Belirtilen giriş uygulaması bulunamadı. Geçerli bir giriş uygulaması adı ve yolu belirtin.|Giriş uygulamanızın yolunun geçerli olduğundan ve var olduğundan emin olun. Giriş uygulamasının o konumda bulunduğundan emin olun.|
|Belirttiğiniz giriş sağlama profili dosyası bulunamadı. Geçerli bir giriş sağlama profili dosyası belirtin.|Giriş sağlama dosyasının yolunun geçerli olduğundan ve belirttiğiniz dosyanın var olduğundan emin olun.|
|Belirttiğiniz çıkış uygulaması klasörü bulunamadı. Çıkış uygulaması için geçerli bir yol belirtin.|Belirttiğiniz çıkış yolunun geçerli olduğundan ve var olduğundan emin olun.|
|Çıkış uygulaması .ipa uzantısına sahip değil.|Uygulama sarmalama aracı tarafından yalnızca **.app** ve **.ipa** uzantılarına sahip uygulamalar kabul edilir. Çıkış dosyanızın geçerli bir uzantısı olduğundan emin olun.|
|Geçersiz bir imzalama sertifikası belirtildi. Geçerli bir Apple imzalama sertifikası belirtin.|Apple geliştirici portalından doğru imzalama sertifikasını indirdiğinizden emin olun. Ayrıca, sertifikanızın süresi dolmuş olabilir. Apple sertifikanız ve sağlama profiliniz Xcode içinde bir uygulamayı doğru şekilde imzalamak için kullanılabiliyorsa, uygulama sarmalama aracı için de geçerlidir.|
|Belirttiğiniz giriş uygulaması geçersiz. Geçerli bir uygulama belirtin.|Bir .app veya .ipa dosyası olarak derlenmiş geçerli bir iOS uygulamasına sahip olduğunuzdan emin olun.|
|Belirttiğiniz giriş uygulaması şifrelenmiş. Geçerli bir şifrelenmemiş uygulama belirtin.|Uygulama sarmalama aracı şifrelenmiş uygulamaları desteklemez. Şifrelenmemiş bir uygulama belirtin.|
|Belirttiğiniz giriş uygulaması Position Independent Executable (PIE) biçiminde değil. PIE biçiminde geçerli bir uygulama belirtin.|Position Independent Executable (PIE) uygulamaları, çalıştırıldığında rastgele bir bellek adresinde yüklenebilir, bu da güvenlik açısından faydalı olabilir. Daha fazla bilgi için Apple Geliştirici belgelerinize bakın.|
|Belirttiğiniz giriş uygulaması zaten sarmalanmış. Sarmalanmamış geçerli bir uygulama belirtin.|Araç tarafından işlenmiş olan bir uygulamayı işleyemezsiniz. Bir uygulamayı yeniden işlemek istiyorsanız, aracı uygulamanın orijinal sürümüyle çalıştırın.|
|Belirttiğiniz giriş uygulaması imzalı değil. Geçerli bir imzalı uygulama belirtin.|Uygulama sarmalama aracı, uygulamaların imzalı olmasını gerektirir. Sarmalanan bir uygulamanın nasıl imzalanacağını öğrenmek için geliştirici belgelerinize başvurun.|
|Belirttiğiniz giriş uygulaması .ipa veya .app biçiminde olmalıdır.|Uygulama sarmalama aracı tarafından yalnızca .app ve .ipa uzantıları kabul edilir. Giriş dosyanızın geçerli bir uzantısı olduğundan ve bir .app veya .ipa dosyası olarak derlendiğinden emin olun.|
|Belirttiğiniz giriş uygulaması zaten sarmalanmış ve ilke şablonunun son sürümünde yer alıyor.|Uygulama sarmalama aracı, var olan bir sarmalanmış uygulamayı ilkesi şablonunun son sürümü ile yeniden sarmalamaz.|
|Belirtilen Azure Active Directory İstemci Kimliği, iyi biçimlendirilmiş bir GUID değil. Lütfen geçerli bir İstemci Kimliği belirtin.|İstemci Kimliği parametresini kullanırken, GUID biçiminde geçerli bir İstemci Kimliği sağladığınızdan emin olun.|
|Belirtilen Azure Active Directory yanıt URI'si iyi biçimlendirilmiş bir URI değil. Lütfen geçerli bir URI belirtin.|Yanıt URI'si komut satırı özelliğini kullanırken, geçerli bir yanıt URI'si sağladığınızdan emin olun.|
|UYARI: SHA1 sertifika karması belirtmediniz. Sarmalanan uygulamanızı dağıtmadan önce mutlaka imzalayın.|Geçerli bir SHA karması belirttiğinizden ( **– c** komut satırı özelliğini kullanarak) emin olun.|

### Uygulama sarmalama aracı için günlük dosyaları
Uygulama sarmalama aracı kullanılarak sarmalanan uygulamalar, iOS istemci cihaz konsoluna yazılan günlükler oluşturur. Bu bilgiler, uygulamayla ilgili sorun yaşadığınız ve sorunun uygulama sarmalama aracı ile ilişkili olup olmadığını tanılamanız gereken durumlarda yararlıdır. Bu bilgileri almak için aşağıdaki adımları kullanın:

1.  Uygulamayı çalıştırarak sorunu yeniden oluşturun.

2.  Apple tarafından sunulan [Dağıtılan iOS Uygulamalarının Hatalarını Ayıklama](https://developer.apple.com/library/ios/qa/qa1747/_index.html)yönergelerini izleyerek konsol çıkışını alın.

3.  Konsola aşağıdaki betiği girerek Uygulama Kısıtlamaları çıkışı için kaydedilen günlükleri filtreleyin:

    ```
    grep “IntuneAppRestrictions” <text file containing console output> > <required filtered log file name>
    ```
    Filtrelenmiş günlükleri Microsoft'a gönderebilirsiniz.

    > [!NOTE]
    > Günlük dosyasında, 'yapı sürümü' öğesi, Xcode yapı sürümünü temsil eder.

    Sarmalanan uygulamalar, mevcut kullanıcılara da uygulama kilitlendikten sonra doğrudan cihazdan e-posta yoluyla günlükleri gönderme seçeneği sunar. Kullanıcılar, incelemeniz ve gerekiyorsa Microsoft'a iletmeniz için günlüğü size gönderebilir.

## Azure Active Directory Library kullanan uygulamalarla ilgili bilgiler
Bu konudaki bilgiler yalnızca Azure Active Directory Library (ADAL) kullanan uygulamalar için geçerlidir. Uygulamanızın bu kitaplığı kullanıp kullanmadığından emin değilseniz, uygulamanın geliştiricisine başvurun.

Uygulama, 1.0.2 veya üzeri bir ADAL sürümü içermelidir.

ADAL kullanan uygulamalar için aşağıdakilerin doğru olması gerekir:

-   Uygulama, 1.0.2 veya daha büyük bir ADAL sürümü içermelidir

-   Geliştiriciler, [ADAL kullanan uygulamalarda izlenecek adımlar](#steps-to-follow-for-apps-that-use-adal) başlığı altında açıklandığı gibi, kendi uygulama erişimlerini Intune Mobil Uygulama Yönetimi kaynağına vermelidir.

### Almanız gereken tanımlayıcılara genel bakış
ADAL kullanan uygulamalar, uygulama için iki benzersiz tanımlayıcı elde etmek üzere Azure Yönetim Portalı aracılığıyla kaydolmalıdır:

|Tanımlayıcı|Daha fazla bilgi|Varsayılan değer|
|--------------|--------------------|-----------------|
|**İstemci Kimliği**|Azure Active Directory'ye kaydolduktan sonra her uygulama için benzersiz bir GUID tanımlayıcı oluşturulur.<br /><br />Uygulamanın istemci kimliğini tam olarak biliyorsanız, bu değeri belirtebilirsiniz. Aksi takdirde, varsayılan değer kullanılmalıdır.|6c7e8096-f593-4d72-807f-a5f86dcc9c77|
|**Yeniden yönlendirme URI'si**|Uygulama, geliştiriciler tarafından Azure Active Directory'ye kaydedilirken kimlik doğrulaması belirteçlerinin özellikle bu uç noktasına döndürüldüğünden emin olunması için sağlanabilen bir URI değeri.<br /><br />Bir yeniden yönlendirme URI'si sağlama, uygulama sarmalama aracı için isteğe bağlı bir parametredir. Belirtilmezse, varsayılan bir URI kullanılacaktır.|urn:ietf:wg:oauth:2.0:oob|


### ADAL kullanan uygulamalarda izlenecek adımlar

1.  Almanız gereken değerleri tanımlamak için [Almanız gereken kimliklere genel bakış](#overview-of-identifiers-you-need-to-get) konusunu gözden geçirin.

2.  Aşağıdakileri yaparak Azure Active Directory'de mobil uygulama yönetimine erişimi yapılandırın:

    1. Azure Yönetim Portalı'nda var olan bir Azure Active Directory hesabında oturum açın.

    2.  Azure Active Directory'de **var olan iş kolu uygulaması kaydı** 'na tıklayın.

    3.  Yapılandırma bölümünde, **Diğer uygulamalardaki Web API'lerine Erişimi Yapılandır**'ı seçin.

    4.  **Diğer uygulamalara izinler** bölümünde, ilk açılan listeden **Intune Mobil Uygulama Yönetimi**'ni seçin.

        Artık uygulama sarmalama aracında uygulamanın İstemci Kimliğini kullanabilirsiniz. Uygulamanın İstemci Kimliğini, [Almanız gereken kimliklere genel bakış](#overview-of-identifiers-you-need-to-get) bölümünde açıklandığı gibi Azure Active Directory yönetim portalında bulabilirsiniz.

3.  Uygulama sarmalama aracında komut satırı özellikleri olarak **Client-ID** (**–a** özelliğini kullanarak) ve **Redirect-URI** değerlerini kullanın. Bu değerler elinizde yoksa, varsayılan değerler kullanılır. Her iki değeri de belirtilmelisiniz; aksi takdirde son kullanıcı, işlenen uygulamanın kimlik doğrulamasını başarılı bir biçimde gerçekleştiremez.

### Sertifika, sağlama profili ve kimlik doğrulaması gereksinimleri

|Gereksinim|Ayrıntılar|
|---------------|-----------|
|Sağlama profili|**Sağlama profilini dahil etmeden önce profilin geçerli olduğundan emin olun** - Uygulama sarmalama aracı, bir iOS uygulamasını işlerken sağlama profilinin geçerlilik süresinin dolup dolmadığını denetlemez. Süresi dolmuş bir sağlama profili belirtilirse, uygulama sarmalama aracı süresi dolmuş sağlama profilini içerir ve uygulamanın bir iOS cihazına yüklenemediğini fark edene kadar bir sorun olduğunu anlayamazsınız.|
|Sertifika|**Sertifikayı belirtmeden önce sertifikanın geçerli olduğundan emin olun** - Araç, iOS uygulamalarını işlerken bir sertifikanın geçerlilik süresinin dolup dolmadığını denetlemez. Süresi dolmuş bir sertifika için karma sağlanırsa, araç uygulamayı işler ve imzalar, ancak uygulama cihazlara yüklenemez.<br /><br />**Paketlenen uygulamayı imzalamak için sağlanan sertifikanın, sağlama profilinde bir eşleşmeye sahip olduğundan emin olun** - Sağlama profili, sarmalanan uygulamayı imzalamak için sağlanan sertifikaya yönelik bir eşleşme içeriyorsa araç doğrulamaz.|
|Kimlik doğrulaması|Bir cihazda şifrelemenin çalışması için bir PIN ayarlanmış olmalıdır. Sarmalanan uygulama dağıtılan cihazlarda durum çubuğuna dokunma, kullanıcının [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] ile yeniden kimlik doğrulaması gerçekleştirmesini gerektirir. Sarmalanan bir uygulamada varsayılan ilke, *yeniden başlatma sırasında kimlik doğrulaması* şeklindedir. iOS tüm dış bildirimleri (örneğin, bir telefon araması) uygulamadan çıkıp uygulamayı yeniden başlatarak işler.<br /><br />Sarmalanan uygulamalarda, aynı yayımcıdan herhangi bir sarmalanan uygulamada oturum açan ilk kullanıcı önbelleğe alınır. Bu noktadan sonra, yalnızca bu kullanıcının uygulamaya erişimine izin verilir. Kullanıcıyı sıfırlamak için cihazın kaydının silinmesi ve yeniden kaydedilmesi gerekir.|

### ADAL ile ilgili sorun giderme notları ve teknik notlar

-   ADAL kaynağı bulunmazsa, araç ADAL dinamik kitaplığını içerecektir. Araç, kök klasöründe bir **ADALiOS.bundle** adıyla ADAL kitaplığını arar.

-   Araç, uygulama içinde ADAL ikili dosyaları (varsa) aramaz. Uygulama eski bir sürüme bağlanıyorsa, kimlik doğrulama ilkelerinin etkin olması durumunda oturum açma sırasında çalışma zamanı hataları olabilir.

-   [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Kimlik doğrulaması için AAD belirtecini [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] MAM kaynak kimliğine getirir. Ancak, belirtecin geçerliliğini doğrulayacak herhangi bir çağrıda kullanılmaz. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Uygulama erişimini belirlemek için yalnızca oturum açmış olan kullanıcının UPN’sini okur. AAD belirteci diğer hizmet çağrıları için kullanılmaz.

-   Aynı yayımcıya ait uygulamalar paylaşılan anahtarlıkta depolandığından, kimlik doğrulama belirteçleri bu uygulamalar arasında paylaşılır. Belirli bir uygulamayı ayırmak istiyorsanız, bu uygulama için farklı bir imzalama sertifikası ve sağlama profili kullanmalısınız.

-   İstemci uygulamanızın İstemci Kimliği ve Yeniden Yönlendirme URI'sini sağlarsanız çift oturum açma istekleri engellenir. Bu İstemci Kimliği, AAD Panosu'nda yayımlanan [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] MAM kaynak kimliğine erişmek için kayıtlı olmalıdır. Bunun sağlanamaması, uygulama çalıştığında bir oturum açma hatasına neden olur.

## Uygulama yetkilendirmelerini ayarlama
Uygulamanızı sarmalamadan önce, uygulamaya normalde yapabildiklerini aşan ek izinler ve yetenekler sağlamak için **yetkilendirmeler** verebilirsiniz.  **Yetkilendirme dosyası**, uygulamanızın içinde özel izinleri (örneğin, paylaşılan bir anahtarlığa erişim) belirlemek için kod imzalama sırasında kullanılır. **Yetenekler** olarak adlandırılan belirli uygulama hizmetleri, uygulama geliştirme sırasında Xcode içinde etkinleştirilir. Yetenekler bir kez etkinleştirildikten sonra, yetkilendirmeler dosyanız bunları yansıtır. Yetkilendirmeler ve yetenekler hakkında daha fazla bilgi için, iOS Geliştirici Kitaplığı’nda [Yetenekleri Ekleme](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) konusuna bakın. Desteklenen yeteneklerin tam listesi için bkz. [Desteklenen yetenekler](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/SupportedCapabilities/SupportedCapabilities.html).

### iOS için Uygulama Sarmalama Aracı’nda desteklenen yetenekler

|Özellik|Açıklama|Önerilen yönerge|
|--------------|---------------|------------------------|
|Uygulama Grupları|Birden çok uygulamanın paylaşılan kapsayıcılara erişimine ve uygulamalar arasında işlemler arası ek iletişime olanak tanımak için uygulama gruplarını kullanın.<br /><br />Uygulama gruplarını etkinleştirmek için, **Yetenekler** bölmesini açın ve **Uygulama Grupları** bölümünde **AÇIK** anahtarına tıklayın. Uygulama grupları ekleyebilir veya var olanları seçebilirsiniz.|Uygulama Grupları’nı kullanırken, ters DNS gösterimini kullanın:<br /><br />*grup.com.şirketAdı.UygulamaGrubu*|
|Arka Plan Modları|Arka plan modlarının etkinleştirilmesi, iOS uygulamanızın arka planda çalışmaya devam etmesine olanak tanır.||
|Veri Koruma|Veri koruma, iOS uygulamanız tarafından diskte depolanan dosyaların güvenlik düzeyini yükseltir. Veri koruma, dosyaları diskte şifrelenmiş biçimde depolamak için belirli cihazlarda bulunan yerleşik şifreleme donanımını kullanır. Uygulamanızın veri korumayı kullanması için hazırlanması gerekir.||
|Uygulama İçi Satın Alma|Uygulama İçi satın alma, mağazaya bağlanmanıza ve kullanıcının ödemelerini güvenli bir şekilde işlemenize olanak tanıyarak, mağazıy doğrudan uygulamanızın içine katıştırır. Uygulama İçi Satın Alma yeteneğini kullanarak, gelişmiş işlevler veya uygulamanız tarafından kullanılabilen ek içerik için ödemeleri alabilirsiniz.||
|Anahtarlık Paylaşımı|Anahtarlık paylaşımının etkinleştirilmesi, uygulamanızın ekibiniz tarafından geliştirilen diğer uygulamalarla anahtarlıkta parolaları paylaşabilmesini sağlar.|Anahtarlı Paylaşımı kullanırken, ters DNS gösterimini kullanın:<br /><br />*com.şirketAdı.AnahtarlıkGrubu*|
|Kişisel VPN|Uygulamanızın Ağ Uzantısı çerçevesini kullanarak özel bir sistem VPN yapılandırması oluşturmasını ve bu yapılandırmayı denetlemesini sağlamak için kişisel VPN’yi etkinleştirin.||
|Anında Bildirimler|Apple Anında İletilen Bildirim hizmeti (APNs), ön planda çalışmayan bir uygulamanın kullanıcıya verilecek bilgileri olduğunu bildirmesini sağlar.|Anında iletme bildirimlerinin çalışması için, uygulamaya özgü bir sağlama profili kullanmalısınız.<br /><br />[Apple geliştirici belgelerinde](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) verilen adımları izleyin.|
|Kablosuz Aksesuar Yapılandırması|Kablosuz aksesuar yapılandırması etkinleştirildiğinde, projenize Dış Aksesuar çerçevesi eklenir ve uygulamanızın MFi Wi-Fi aksesuarlarını yapılandırmasına olanak tanınır.||

### Yetkilendirmeleri etkinleştirme adımları

1.  Uygulamanızda yetenekleri etkinleştirin:

    1.  Xcode’da, uygulamanızın hedefine gidin ve **Yetenekler** bölmesine tıklayın.

    2.  Uygun yetenekleri açın. Her yetenek hakkında ayrıntılı bilgi almak ve doğru değerlerin nasıl saptanacağını öğrenmek için, iOS Geliştirici Kitaplığı’nda [Yetenekleri Ekleme](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) konusuna bakın.

    3.  İşlem sırasında oluşturduğunuz tüm kimlikleri not alın.

    4.  Uygulamanızı oluşturun ve sarmalamak üzere imzalayın.

2.  Sağlama profilinizde yetkilendirmeleri etkinleştirin:

    1.  Apple Geliştirici Üye Merkezi’nde oturum açın.

    2.  Uygulamanız için bir sağlama profili oluşturun. Yönergeler için bkz. [iOS için Intune Uygulama Sarmalama Aracı’nın Önkoşulları Nasıl Elde Edilir](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/).

    3.  Sağlama profilinizde, uygulamanızda sahip olduğunuz yetkilendirmelerle aynı yetkilendirmeleri etkinleştirin. Uygulamanızın geliştirilmesi sırasında belirttiğiniz kimliklerle aynı kimlikleri sağlamanız gerekir.

    4.  Sağlama profili sihirbazını tamamlayın ve dosyanızı indirin.

3.  Tüm önkoşullara uyduğunuzdan emin olun ve ardından uygulamayı sarmalayın.

### Sık karşılaşılan yetkilendirme sorunlarını giderme
iOS için Uygulama Sarmalama Aracı yetkilendirme hatası gösterirse, aşağıdaki sorun giderme adımlarını deneyin.

|Sorun|Nedeni|Çözüm|
|---------|---------|--------------|
|Giriş uygulamasından oluşturulan yetkilendirmeler ayrıştırılamadı.|Uygulama Sarmalama Aracı, uygulamadan ayıklanan yetkilendirmeler dosyasını okuyamıyor. Yetkilendirmeler dosyası hatalı biçimlendirilmiş olabilir.|Uygulamanızın yetkilendirmeler dosyasını inceleyin. Bunu yapmak için, aşağıdaki ayrıntılı yönergeleri izleyin. Yetkilendirmeler dosyasını incelerken, yanlış biçimlendirilmiş söz dizimi olup olmadığını denetleyin. Dosya, XML biçiminde olmalıdır.|
|Sağlama profilinde yetkilendirmeler eksik (eksik yetkilendirmeler listelenmiştir). Uygulamayı, söz konusu yetkilendirmeleri içeren bir sağlama profiliyle yeniden paketleyin.|Sağlama profiliyle etkinleştirilen yetkilendirmelerle uygulamada etkinleştirilen yetenekler arasında bir uyuşmazlık var. Bu uyuşmazlık, belirli yeteneklerle ilişkilendirilen kimlikler için de geçerlidir (örneğin, Uygulama Grupları, Anahtarlık Erişimi).|Genel olarak, uygulamayla aynı yetenekleri etkinleştiren yeni bir sağlama profili oluşturabilirsiniz. Profille uygulama arasında kimlikler eşleşmezse, Uygulama Sarmalama Aracı kimlikleri (yapabilirse) değiştirir. Yeni sağlama profili oluşturduktan sonra da bu hatayı almaya devam ediyorsanız, **–e** parametresini kullanarak uygulamadan yetkilendirmeleri kaldırabilirsiniz (aşağıdaki "Uygulamadan yetkilendirmeleri kaldırmak için –e parametresini kullanma” bölümüne bakın).|

### İmzalı bir uygulamanın var olan yetkilendirmelerini bulma
İmzalı uygulamanın ve sağlama profilinin var olan yetkilendirmelerini gözden geçirmek için:

1.  .ipa dosyasını bulun ve uzantısını .zip olarak değiştirin.

2.  .zip dosyasını genişletin. Bu işlem, .app paketinizi içeren bir Payload klasörü oluşturur.

3.  Aşağıda gösterildiği gibi .app paketinde yetkilendirmeleri denetlemek için kod imzalama aracını kullanın:

    ```
    $ codesign -d --entitlements :- "Payload/YourApp.app"
    ```
    burada `YourApp.app`, .app paketinizin asıl adıdır.

4.  Uygulamanın gömülü sağlama profilinin yetkilendirmelerini denetlemek için güvenlik aracını kullanın:

    ```
    $ security -D -i "Payload/YourApp.app/embedded.mobileprovision"
    ```
    burada `YourApp.app`, .app paketinizin asıl adıdır.

### Uygulamadan yetkilendirmeleri kaldırmak için –e parametresini kullanma
Bu komut, uygulamada etkinleştirilmiş olan ve yetkilendirmeler dosyasında yer almayan tüm yetenekleri kaldırır. Uygulama tarafından kullanılmakta olan yetenekleri kaldırırsanız, uygulamanız bozulabilir. Eksik yetenekleri kaldırabileceğiniz durumlara örnek olarak, tüm yeteneklere varsayılan olarak sahip olan, satıcı tarafından oluşturulmuş bir uygulama verilebilir.

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager –i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> –p /<path to provisioning profile> –c <SHA1 hash of the certificate> -e
```

## Uygulama sarmalama aracı için güvenlik ve gizlilik
Uygulama sarmalama aracını kullanırken, güvenlik ve gizlilik açısından aşağıdaki en iyi uygulamaları kullanın.

-   Belirttiğiniz imzalama sertifikası, sağlama profili ve iş kolu uygulaması, uygulama sarmalama aracısını çalıştırmak için kullandığınız Mac bilgisayarda olmalıdır. Dosyalar bir UNC yolu üzerindeyse, bunların Mac bilgisayardan erişilebilir olduğundan emin olun. Yol, IPsec veya SMB imzalama aracılığıyla korunmalıdır.

    [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] konsoluna içeri aktarılan kaydırılan uygulama, aracı çalıştırdığınız bilgisayarda bulunmalıdır. Dosya bir UNC yolu üzerindeyse, yolun [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] konsolunu çalıştıran bilgisayarda erişilebilir durumda olduğundan emin olun. Yol, IPsec veya SMB imzalama aracılığıyla korunmalıdır.

-   Microsoft İndirme Merkezi sitesinden uygulama sarmalama aracının indirildiği ortamın IPsec veya SMB imzalama aracılığıyla korunması gerekir.

-   İşlediğiniz uygulama, saldırılara karşı koruma sağlamak için güvenilir bir kaynaktan gelmelidir.

-   Uygulama sarmalama aracında belirttiğiniz çıkış klasörünün, özellikle uzak bir klasör ise, güvenli olduğundan emin olun.

-   Karşıya dosya yükleme iletişim kutusu içeren iOS uygulamaları, kullanıcıların uygulama için geçerli olan kes, kopyala ve yapıştır kısıtlamalarını aşmasına imkan sağlar. Örneğin, bir kullanıcı karşıya dosya yükleme iletişim kutusunu kullanarak uygulama verilerinin ekran görüntüsünü karşıya yükleyebilir.

-   Kullanıcılar cihazlarındaki belgeler klasörünü sarmalanan bir uygulamadan izliyorsa, **.msftintuneapplauncher**adında bir klasör görebilirler. Bu klasör değiştirilmiş veya silinmişse, bu kısıtlanan uygulamaların düzgün çalışmasını etkileyebilir.

### Ayrıca bkz.
- [Microsoft Intune ile uygulamaların mobil uygulama yönetimi için nasıl hazırlanacağına karar verme](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)</br>
- [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)</br>
- [SDK’yı kullanarak uygulamaları mobil uygulama yönetimi için etkinleştirme](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Jul16_HO4-->


