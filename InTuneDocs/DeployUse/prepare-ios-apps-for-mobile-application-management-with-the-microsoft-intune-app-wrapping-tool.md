---
title: "iOS uygulamalarını Uygulama Sarmalama Aracı’yla sarmalama | Microsoft Intune"
description: "iOS uygulamalarınızı, uygulamanın kendi kodunda değişiklik yapmadan sarmalamayı öğrenmek için bu konu başlığı altındaki bilgileri kullanın. Mobil uygulama yönetimi ilkelerini uygulayabilmek için uygulamaları hazırlayın."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 99ab0369-5115-4dc8-83ea-db7239b0de97
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c67a5042fd177a4c5bd897092e84281db0977f5e
ms.openlocfilehash: 2c187b61b8fe25b2870d0cbc62f8352494583fc2


---

# Intune Uygulama Sarmalama Aracı ile iOS uygulamalarını mobil uygulama yönetimi için hazırlama
Şirket içi iOS uygulamalarının davranışını, uygulamanın kodunu değiştirmeden uygulama özelliklerini kısıtlayarak değiştirmek için **iOS için Microsoft Intune Uygulama Sarmalama Aracı**'nı kullanın.

Araç, bir uygulama etrafında 'sarmalayıcı' oluşturan bir Mac OS komut satırı uygulamasıdır. Bir uygulama işlendikten sonra, yapılandırdığınız Intune [mobil uygulama yönetimi ilkelerini](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) kullanarak uygulamaların işlevini değiştirebilirsiniz.

Aracı indirmek için bkz. [iOS için Microsoft Intune Uygulama Sarmalama Aracı](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios).



## 1. Adım Uygulama sarmalama aracını kullanarak önkoşulları karşılama
Ön koşullar ve bunları nasıl ayarlayacağınız hakkında bilgi edinmek için [bu blog gönderisini](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) okuyun.

|Gereksinim|Daha fazla bilgi|
|---------------|--------------------------------|
|Desteklenen işletim sistemi ve araç takımı|Uygulama sarmalama aracını, XCode araç takımının sürüm 5 veya üzerinin yüklü olduğu OS X 10.8.5 ya da üzerini çalıştıran bir Mac OS bilgisayarda çalıştırmalısınız.|
|İmzalama sertifikası ve sağlama profili|Bir Apple imzalama sertifikanız ve sağlama profiliniz olmalıdır. [Apple geliştirici belgelerinize](https://developer.apple.com/) bakın.|
|Uygulama Sarmalama Aracı’yla bir uygulamayı işleme|Uygulamalar şirketiniz veya bağımsız bir yazılım satıcısı (ISV) tarafından geliştirilmiş ve imzalanmış olmalıdır. Bu aracı Apple Store'dan edinilen uygulamaları işlemek için kullanamazsınız. Uygulamalar iOS 8.0 veya üzeri için yazılmış olmalıdır. Ayrıca uygulamalar Konumdan Bağımsız Yürütülebilir (PIE) biçiminde olmalıdır. PIE biçimi hakkında daha fazla bilgi için Apple geliştirici belgelerinize bakın. Son olarak, uygulamanın uzantısı **.app** veya **.ipa** olmalıdır.|
|Sarmalama aracının işleyemediği uygulamalar|Şifrelenmiş uygulamalar, imzalanmamış uygulamalar ve genişletilmiş dosya öznitelikleri olan uygulamalar.|
|Uygulamanız için yetkilendirmeleri ayarlama|Uygulamayı sarmalamadan önce, uygulamaya normal olarak verilenlerin ötesinde ek izinler ve yetenekler veren yetkilendirmeler ayarlamanız gerekir. Yönergeler için bkz. [Uygulama yetkilendirmelerini ayarlama](#setting-app-entitlements).|

## 2. Adım Uygulama sarmalama aracını yükleme

1.  **GitHub’da barındırılan** [iOS için Microsoft Intune Uygulama Sarmalama Aracı deposunda](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios), uygulama sarmalama aracı dosyalarını bir Mac OS bilgisayara yerel olarak indirin.

2.  **Microsoft Intune App Wrapping Tool for iOS.dmg** adlı yükleme dosyasına çift tıklayın. Son Kullanıcı Lisans Sözleşmesi (EULA) ile bir pencere görüntülenir. Belgeyi dikkatli okuyun.

3. Paketi bilgisayarınıza bağlayan EULA’yı kabul etmek için **Kabul et**’i seçin.

4.  **IntuneMAMPackager** paketini açın ve dosyaları Mac OS bilgisayarınızda yerel bir klasöre kaydedin. Artık uygulama sarmalama aracını çalıştırmaya hazırsınız.

## 3. Adım. Uygulama sarmalama aracını çalıştırma
* Mac OS bilgisayarınızda, bir Terminal penceresi açın ve uygulama sarmalama aracı dosyalarını kaydettiğiniz klasöre gidin. Yürütülebilir aracın adı **IntuneMAMPackager**, bulunduğu konum **IntuneMAMPackager/Contents/MacOS** klasörüdür. Komutu aşağıdaki şekilde çalıştırmanız gerekir:

    ```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> -p /<path to provisioning profile> -c <SHA1 hash of the certificate> [-b [<output app build string>]] [-v] [-e] [-x /<array of extension provisioning profile paths>]

    ```

    > [!NOTE]
    > Bazı parametreler aşağıdaki tabloda gösterildiği gibi isteğe bağlıdır.

    **Örnek:** Aşağıdaki örnek komut, **MyApp.ipa**adlı bir uygulamanın üzerinde uygulama sarmalama aracını çalıştırır. Bir sağlama profili ve SHA-1 karması belirtilir. İşlenen uygulama oluşturulur, **MyApp_Wrapped.ipa** olarak adlandırılır ve kullanıcının Masaüstü klasöründe depolanır.

    ```
    ./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i ~/Desktop/MyApp.ipa -o ~/Desktop/MyApp_Wrapped.ipa -p ~/Desktop/My_Provisioning_Profile_.mobileprovision -c 12A3BC45D67EF8901A2B3CDEF4ABC5D6E7890FAB  -v true
    ```
    Aşağıdaki komut satırı özelliklerini uygulama sarmalama aracı ile birlikte kullanabilirsiniz:

    |Özellik|Kullanımı|
  |------------|--------------------|
  |**-i**|`<Path of the input native iOS application file>`. Dosyanın sonunda .app veya .ipa olmalıdır. |
  |**-o**|`<Path of the wrapped output application>` |
  |**-p**|`<Path of your provisioning profile for iOS apps>`|
  |**-c**|`<SHA1 hash of the signing certificate>`|
    |-h|Uygulama sarmalama aracı için kullanılabilir komut satırı özellikleri hakkında ayrıntılı kullanım bilgilerini görüntüler.|
  |-v|(İsteğe bağlı ancak yararlıdır) Konsola ayrıntılı ileti çıkışı yapar.|
  |-e | (İsteğe bağlı) Uygulama sarmalama aracının uygulamayı işlerken eksik yetkilendirmeleri kaldırmasını sağlamak için bu bayrağı kullanın. Daha fazla ayrıntı için "Uygulama yetkilendirmelerini ayarlama" bölümüne bakın.|
  |-xe| (İsteğe bağlı) Uygulamadaki iOS uzantıları hakkında bilgi ve bunları kullanmak için hangi yetkilendirmelerin gerektiğini yazdırır. Daha fazla ayrıntı için "Uygulama yetkilendirmelerini ayarlama" bölümüne bakın. |
  |-x| (İsteğe bağlı) `<An array of paths to extension provisioning profiles>`. Uygulamanızda uzantı sağlayan profiller gerekiyorsa bunu kullanın.|
  |-f |(İsteğe bağlı) `<Path to a plist file specifying arguments.>` -i, -o, -p vb. gibi geri kalan IntuneMAMPackager özelliklerini belirtmek için plist şablonu kullanmayı tercih ederseniz bu bayrağı [plist](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html) dosyasının önünde kullanın. Daha fazla ayrıntı için "bağımsız değişkenlerin girişi için bir plist kullanma" bölümüne bakın. |
  |-b|(İsteğe bağlı) Sarmalanan çıkış uygulamasının giriş uygulamasıyla aynı paket sürümüne sahip olmasını isterseniz (önerilmez), -b’yi bağımsız değişken olmadan kullanın. <br/><br/> Sarmalanan uygulamanın özel CFBundleVersion içermesini istiyorsanız `-b <custom bundle version>` kullanın. Özel CFBundleVersion belirtmek isterseniz, yerel uygulamanın CFBundleVersion’unu en az önemli bileşen tarafından artırmanızı öneririz, ör. 1.0.0 -> 1.0.1. |


###Bağımsız değişkenler girişi için bir plist kullanma
Uygulama Sarmalama Aracı’nı çalıştırmanın kolay bir yolu, tüm komut satırı bağımsız değişkenlerini bir [plist](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html) dosyasına yerleştirmektir. Plist, bir form arabirimi ile komut satırı bağımsız değişkenlerimizin girişi için kullanabileceğimiz, XML'e benzer bir dosya biçimidir.

**IntuneMAMPackager/Contents/MacOS** klasöründe, `Parameters.plist` öğesini, bir metin düzenleyici veya Xcode ile boş bir plist şablonu açın. Aşağıdaki anahtarlar için bağımsız değişkenlerinizi girin:

| Plist Anahtarı |  Varsayılan Değer| Notlar |
|------------------|--------------|-----|
| Giriş Uygulama Paketi Yolu  |boş| -i ile aynı. |
| Çıkış Uygulama Paketi Yolu |boş| -o ile aynı.|
| Profil Yolu Sağlama |boş| -p ile aynı. |
| SHA-1 Sertifika Karması |boş| -c ile aynı. |
| Ayrıntılı Mod Etkin |yanlış| -v ile aynı. |
| Eksik Yetkilendirmeleri Kaldır | yanlış| -c ile aynı.|
| Varsayılan Derlemeyi Engelle |yanlış | Bağımsız değişkenler olmadan -b kullanma ile eşdeğerdir. |
|Dize Geçersiz Kılmayı Derle | boş| Sarmalanan çıkış uygulaması için özel CFBundleVersion |
|Uzantı Sağlayan Profil Yolları | boş| Uygulamanın uzantı sağlama profillerinin bir dizisi.
  

Son olarak, IntuneMAMPackager’ı plist ile tek bağımsız değişken olarak çalıştırın:

```
./IntuneMAMPackager –f Parameters.plist
```

* İşlem tamamlandıktan sonra, “**Uygulama başarıyla sarmalandı**” iletisi görüntülenir.

    Bir hata oluşursa yardım için [hata iletileri](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md#error-messages) sayfasına bakın.

*   Sarmalanan uygulama, daha önce belirttiğiniz çıkış klasörüne kaydedilir. Şimdi uygulamayı [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] hizmetine yükleyebilir ve bir mobil uygulama yönetimi ilkesi ile ilişkilendirebilirsiniz.

    > [!IMPORTANT]
    > Sarmalanan bir uygulama karşıya yüklenirken, uygulamanın eski bir sürümünü, eski sürüm (sarmalanan veya yerel) zaten Intune’da dağıtılmışsa güncelleştirmeyi deneyebilirsiniz. Bir hatayla karşılaşırsanız, uygulamayı yeni bir uygulama olarak karşıya yükleyip eski sürümü silin.

    Şimdi uygulamayı [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] gruplarınıza dağıtabilirsiniz ve uygulama artık cihazda belirttiğiniz uygulama kısıtlamalarını kullanarak çalıştırılır.

## Hata iletileri ve günlük dosyaları
Uygulama sarmalama aracında karşılaştığınız sorunları gidermek için aşağıdaki bilgileri kullanın.

### Hata iletileri
Uygulama sarmalama aracı başarılı bir şekilde tamamlanamazsa, konsolda aşağıdaki hata iletilerinden biri görüntülenir:

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
|Geçersiz bir imzalama sertifikası belirtildi. Geçerli bir Apple imzalama sertifikası belirtin.|Apple geliştirici portalından doğru imzalama sertifikasını indirdiğinizden emin olun. Sertifikanızın süresi dolmuş olabilir veya bir ortak veya özel anahtar eksik olabilir. Apple sertifikanız ve sağlama profiliniz Xcode içinde bir uygulamayı doğru şekilde imzalamak için kullanılabiliyorsa, uygulama sarmalama aracı için de geçerlidir.|
|Belirttiğiniz giriş uygulaması geçersiz. Geçerli bir uygulama belirtin.|Bir .app veya .ipa dosyası olarak derlenmiş geçerli bir iOS uygulamasına sahip olduğunuzdan emin olun.|
|Belirttiğiniz giriş uygulaması şifrelenmiş. Geçerli bir şifrelenmemiş uygulama belirtin.|Uygulama sarmalama aracı şifrelenmiş uygulamaları desteklemez. Şifrelenmemiş bir uygulama sağlayın.|
|Belirttiğiniz giriş uygulaması Position Independent Executable (PIE) biçiminde değil. PIE biçiminde geçerli bir uygulama belirtin.|Position Independent Executable (PIE) uygulamaları, çalıştırıldığında rastgele bir bellek adresinde yüklenebilir, bu da güvenlik açısından faydalı olabilir. Daha fazla bilgi için Apple Geliştirici belgelerinize bakın.|
|Belirttiğiniz giriş uygulaması zaten sarmalanmış. Sarmalanmamış geçerli bir uygulama belirtin.|Araç tarafından işlenmiş olan bir uygulamayı işleyemezsiniz. Bir uygulamayı yeniden işlemek istiyorsanız, aracı uygulamanın orijinal sürümüyle çalıştırın.|
|Belirttiğiniz giriş uygulaması imzalı değil. Geçerli bir imzalı uygulama belirtin.|Uygulama sarmalama aracı, uygulamaların imzalı olmasını gerektirir. Sarmalanan bir uygulamanın nasıl imzalanacağını öğrenmek için geliştirici belgelerinize başvurun.|
|Belirttiğiniz giriş uygulaması .ipa veya .app biçiminde olmalıdır.|Uygulama sarmalama aracı tarafından yalnızca .app ve .ipa uzantıları kabul edilir. Giriş dosyanızın geçerli bir uzantısı olduğundan ve bir .app veya .ipa dosyası olarak derlendiğinden emin olun.|
|Belirttiğiniz giriş uygulaması zaten sarmalanmış ve ilke şablonunun son sürümünde yer alıyor.|Uygulama sarmalama aracı, var olan bir sarmalanmış uygulamayı ilkesi şablonunun son sürümü ile yeniden sarmalamaz.|
|UYARI: SHA1 sertifika karması belirtmediniz. Sarmalanan uygulamanızı dağıtmadan önce mutlaka imzalayın.|Geçerli bir SHA1 karması belirttiğinizden **– c** komut satırı bayrağını takip ederek emin olun. |

### Uygulama sarmalama aracı için günlük dosyaları
Uygulama sarmalama aracı kullanılarak sarmalanan uygulamalar, iOS istemci cihaz konsoluna yazılan günlükler oluşturur. Bu bilgiler, uygulamayla ilgili sorun yaşadığınızda ve sorunun uygulama sarmalama aracı ile ilişkili olup olmadığını tanılamanız gerektiğinde yararlıdır. Bu bilgileri almak için aşağıdaki adımları kullanın:

1.  Uygulamayı çalıştırarak sorunu yeniden oluşturun.

2.  Apple tarafından sunulan [Dağıtılan iOS Uygulamalarının Hatalarını Ayıklama](https://developer.apple.com/library/ios/qa/qa1747/_index.html)yönergelerini izleyerek konsol çıkışını alın.

3.  Konsola aşağıdaki betiği girerek Uygulama Kısıtlamaları çıkışı için kaydedilen günlükleri filtreleyin:

    ```
    grep “IntuneAppRestrictions” <text file containing console output> > <required filtered log file name>
    ```
    Filtrelenmiş günlükleri Microsoft'a gönderebilirsiniz.

    > [!NOTE]
    > Günlük dosyasında, 'yapı sürümü' öğesi, Xcode yapı sürümünü temsil eder.

    Sarmalanan uygulamalar, mevcut kullanıcılara da uygulama kilitlendikten sonra doğrudan cihazdan e-posta yoluyla günlükleri gönderme seçeneği sunar. Kullanıcılar, incelemeniz ve gerekiyorsa Microsoft'a iletmeniz için günlükleri size gönderebilir.


### Sertifika, sağlama profili ve kimlik doğrulaması gereksinimleri

Tam işlevsellik garantisi için uygulama sarmalama aracında karşılanması gereken bazı gereksinimler vardır.

|Gereksinim|Ayrıntılar|
|---------------|-----------|
|Sağlama profili|**Dahil etmeden önce sağlama profilinin geçerli olduğundan emin olun**. Uygulama sarmalama aracı, bir iOS uygulamasını işlerken sağlama profilinin geçerlilik süresinin dolup dolmadığını denetlemez. Süresi dolmuş bir sağlama profili belirtilirse, uygulama sarmalama aracı süresi dolmuş sağlama profilini içerir ve uygulamanın bir iOS cihazına yüklenemediğini fark edene kadar bir sorun olduğunu anlayamazsınız.|
|Sertifika|**Belirtmeden önce sertifikanın geçerli olduğundan emin olun**. Araç, iOS uygulamalarını işlerken bir sertifikanın süresinin dolup dolmadığını denetlemez. Süresi dolmuş bir sertifika için karma sağlanırsa, araç uygulamayı işler ve imzalar, ancak uygulama cihazlara yüklenemez.<br /><br />**Paketlenen uygulamayı imzalamak için sağlanan sertifikanın, sağlama profilinde bir eşleşmeye sahip olduğundan emin olun**. Araç, sağlama profilinin sarmalanan uygulamayı imzalamak için sağlanan sertifikaya yönelik bir eşleşme içerip içermediğini doğrulamaz.|
|Kimlik doğrulaması|Şifrelemenin çalışması için cihazın PIN’e sahip olması gerekir. Sarmalanan uygulama dağıtılan cihazlarda durum çubuğuna dokunma, kullanıcının [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] ile yeniden kimlik doğrulaması gerçekleştirmesini gerektirir. Sarmalanan bir uygulamada varsayılan ilke, *yeniden başlatma sırasında kimlik doğrulaması* şeklindedir. iOS, tüm dış bildirimleri (ör. bir telefon çağrısı) uygulamadan çıkıp yeniden başlatarak işler.


## Uygulama yetkilendirmelerini ayarlama
Uygulamanızı sarmalamadan önce, uygulamaya normalde yapabildiklerini aşan ek izinler ve yetenekler sağlamak için **yetkilendirmeler** verebilirsiniz.  **Yetkilendirme dosyası**, uygulamanızın içinde özel izinleri (örneğin, paylaşılan bir anahtarlığa erişim) belirlemek için kod imzalama sırasında kullanılır. **Yetenekler** olarak adlandırılan belirli uygulama hizmetleri, uygulama geliştirme sırasında Xcode içinde etkinleştirilir. Yetenekler bir kez etkinleştirildikten sonra, yetkilendirmeler dosyanız bunları yansıtır. Yetkilendirmeler ve yetenekler hakkında daha fazla bilgi için, iOS Geliştirici Kitaplığı’nda [Yetenekleri Ekleme](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) konusuna bakın. Desteklenen yeteneklerin tam listesi için bkz. [Desteklenen yetenekler](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/SupportedCapabilities/SupportedCapabilities.html).

### iOS için Uygulama Sarmalama Aracı’nda desteklenen yetenekler

|Özellik|Açıklama|Önerilen yönerge|
|--------------|---------------|------------------------|
|Uygulama Grupları|Birden çok uygulamanın paylaşılan kapsayıcılara erişimine ve uygulamalar arasında işlemler arası ek iletişime olanak tanımak için uygulama gruplarını kullanın.<br /><br />Uygulama gruplarını etkinleştirmek için, **Yetenekler** bölmesini açın ve **Uygulama Grupları** bölümünde **AÇIK** anahtarına tıklayın. Uygulama grupları ekleyebilir veya var olanları seçebilirsiniz.|Uygulama Grupları’nı kullanırken, ters DNS gösterimini kullanın:<br /><br />*grup.com.şirketAdı.UygulamaGrubu*|
|Arka Plan Modları|Arka plan modlarının etkinleştirilmesi, iOS uygulamanızın arka planda çalışmaya devam etmesine olanak tanır.||
|Veri Koruma|Veri koruma, iOS uygulamanız tarafından diskte depolanan dosyaların güvenlik düzeyini yükseltir. Veri koruma, dosyaları diskte şifrelenmiş biçimde depolamak için belirli cihazlarda bulunan yerleşik şifreleme donanımını kullanır. Uygulamanızın veri korumayı kullanması için hazırlanması gerekir.||
|Uygulama İçi Satın Alma|Uygulama İçi satın alma, mağazaya bağlanmanıza ve kullanıcının ödemelerini güvenli bir şekilde işlemenize olanak tanıyarak, mağazayı doğrudan uygulamanızın içine katıştırır. Uygulama İçi Satın Alma yeteneğini kullanarak, gelişmiş işlevler veya uygulamanız tarafından kullanılabilen ek içerik için ödemeleri alabilirsiniz.||
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

-   Belirttiğiniz imzalama sertifikası, sağlama profili ve iş kolu uygulaması, uygulama sarmalama aracını çalıştırmak için kullandığınız Mac OS makinesinde olmalıdır. Dosyalar bir UNC yolu üzerindeyse, bunların Mac OS makineden erişilebilir olduğundan emin olun. Yol, IPsec veya SMB imzalama aracılığıyla korunmalıdır.

    [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] konsoluna içeri aktarılan kaydırılan uygulama, aracı çalıştırdığınız bilgisayarda bulunmalıdır. Dosya bir UNC yolu üzerindeyse, yolun [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] konsolunu çalıştıran bilgisayarda erişilebilir durumda olduğundan emin olun. Yol, IPsec veya SMB imzalama aracılığıyla korunmalıdır.

-   Uygulama sarmalama aracının GitHub deposundan indirildiği ortamın IPsec veya SMB imzalama aracılığıyla korunması gerekir.

-   İşlediğiniz uygulama, saldırılara karşı koruma sağlamak için güvenilir bir kaynaktan gelmelidir.

-   Uygulama sarmalama aracında belirttiğiniz çıkış klasörünün, özellikle uzak bir klasör ise, güvenli olduğundan emin olun.

-   Karşıya dosya yükleme iletişim kutusu içeren iOS uygulamaları, kullanıcıların uygulama için geçerli olan kes, kopyala ve yapıştır kısıtlamalarını aşmasına imkan sağlar. Örneğin, bir kullanıcı karşıya dosya yükleme iletişim kutusunu kullanarak uygulama verilerinin ekran görüntüsünü karşıya yükleyebilir.

-   Kullanıcılar cihazlarındaki belgeler klasörünü sarmalanan bir uygulamadan izliyorsa, **.msftintuneapplauncher**adında bir klasör görebilirler. Bu klasör değiştirilmiş veya silinmişse, bu kısıtlanan uygulamaların düzgün çalışmasını etkileyebilir.

### Ayrıca bkz.
- [Microsoft Intune ile uygulamaların mobil uygulama yönetimi için nasıl hazırlanacağına karar verme](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)</br>
- [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)</br>
- [SDK’yı kullanarak uygulamaları mobil uygulama yönetimi için etkinleştirme](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Oct16_HO2-->


