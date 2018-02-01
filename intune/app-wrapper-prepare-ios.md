---
title: "iOS uygulamalarını Intune Uygulama Sarmalama Aracı ile sarmalama"
description: "iOS uygulamalarınızı, uygulamanın kendi kodunda değişiklik yapmadan sarmalamayı öğrenmek için bu konu başlığı altındaki bilgileri kullanın. Mobil uygulama yönetimi ilkelerini uygulayabilmek için uygulamaları hazırlayın."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 01/18/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 99ab0369-5115-4dc8-83ea-db7239b0de97
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4925fc86596437d0560bd7fa2598eaf95126df16
ms.sourcegitcommit: cede2e15bd62f1073131fbc9af7623cdfc3730cf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2018
---
# <a name="prepare-ios-apps-for-app-protection-policies-with-the-intune-app-wrapping-tool"></a>Intune Uygulama Sarmalama Aracı ile iOS uygulamalarını uygulama koruma ilkelerine hazırlama

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Şirket içi iOS uygulamaları için Intune uygulama koruma özelliklerini uygulamanın kodunu değiştirmeden etkinleştirmek üzere iOS için Microsoft Intune Uygulama Sarmalama Aracı'nı kullanın.

Araç, bir uygulama etrafında sarmalayıcı oluşturan bir Mac OS komut satırı uygulamasıdır. İşleme alındıktan sonra bir uygulamanın işlevselliğini [uygulama koruma ilkeleri](/intune-classic/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console) dağıtarak değiştirebilirsiniz.

Aracı indirmek için bkz. GitHub üzerinde [iOS için Microsoft Intune Uygulama Sarmalama Aracı](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios).



## <a name="general-prerequisites-for-the-app-wrapping-tool"></a>Uygulama Sarmalama Aracı için genel önkoşullar

Uygulama Sarmalama Aracı’nı çalıştırmadan önce bazı genel önkoşulları karşılamanız gerekir:

* Github’dan [iOS için Microsoft Intune Uygulama Sarmalama Aracı](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios)’nı indirin.

* Xcode araç takımının sürüm 5 veya üzeri yüklü olan ve OS X 10.8.5 ya da üzerini çalıştıran bir Mac OS bilgisayar.

* Giriş iOS uygulaması, şirketiniz veya bağımsız bir yazılım satıcısı (ISV) tarafından geliştirilmiş ve imzalanmış olmalıdır.

  * Giriş uygulaması dosyasının uzantısı **.ipa** veya **.app** olmalıdır.

  * Giriş uygulaması iOS 8.0 veya üzeri için derlenmiş olmalıdır.

  * Giriş uygulaması şifrelenemez.

  * Giriş uygulamasının genişletilmiş dosya öznitelikleri olamaz.

  * Intune Uygulama Sarmalama Aracı tarafından işlenmeden önce giriş uygulaması yetkilendirmelerinin ayarlanmış olması gerekir. [Yetkilendirmeler](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/EntitlementKeyReference/Chapters/AboutEntitlements.html) uygulamaya normal olarak verilenlerin ötesinde ek izinler ve yetenekler verir. Yönergeler için bkz. [Uygulama yetkilendirmelerini ayarlama](#setting-app-entitlements).

## <a name="apple-developer-prerequisites-for-the-app-wrapping-tool"></a>Uygulama Sarmalama Aracı için Apple Geliştirici önkoşulları

Sarmalanan uygulamaları kuruluşunuzun kullanıcılarına özel olarak dağıtmak için [Apple Geliştirici Kurumsal Programı](https://developer.apple.com/programs/enterprise/)’na sahip bir hesaba ve Apple Geliştirici hesabınıza bağlı olan ve uygulama imzalamak için gereken çeşitli varlıklara ihtiyacınız vardır.

Kuruluşunuzdaki kullanıcılara dahili olarak iOS uygulamaları dağıtma hakkında daha fazla bilgi için [Apple Geliştirici Kurumsal Programı Uygulamalarını Dağıtma](https://developer.apple.com/library/content/documentation/IDEs/Conceptual/AppDistributionGuide/DistributingEnterpriseProgramApps/DistributingEnterpriseProgramApps.html#//apple_ref/doc/uid/TP40012582-CH33-SW1) adlı resmi kılavuzu okuyun.

Intune tarafından sarmalanan uygulamaları dağıtmak için aşağıdakiler gerekir:

* Apple Geliştirici Kurumsal Programı’nı içeren bir geliştirici hesabı.

* Geçerli Ekip Tanımlayıcısı ile şirket içi ve geçici dağıtım imzalama sertifikası.

  * Intune Uygulama Sarmalama Aracı için parametre olarak imzalama sertifikasının SHA1 karmasına ihtiyacınız olacaktır.


* Şirket içi dağıtım sağlama profili.

### <a name="steps-to-create-an-apple-developer-enterprise-account"></a>Apple Geliştirici Kuruluş hesabı oluşturma adımları
1. [Apple Geliştirici Kurumsal Programı sitesine](https://developer.apple.com/programs/enterprise/) gidin.

2. Sayfanın sağ üst kısmında **Kaydet**’e tıklayın.

3. Kaydedeceğiniz öğenin denetim listesini okuyun. Sayfanın en altındaki **Kaydınıza Başlayın**’a tıklayın.

4. Kuruluşunuzun Apple kimliğiyle **oturum açın**. Apple kimliğiniz yoksa **Apple Kimliği Oluştur**’a tıklayın.

5. **Varlık Türü**’nüzü seçin ve **Devam**’a tıklayın.

6. Kuruluşunuzun bilgilerini girerek formu doldurun. 
              **Devam**'a tıklayın. Bu noktada Apple, kuruluşunuzu kaydetme yetkiniz olup olmadığını doğrulamak için sizinle irtibat kurar.

8. Doğrulamadan sonra **Lisansı Kabul Et**'e tıklayın.

9. Lisansı kabul ettikten sonra, **satın alma ve programı etkinleştirme** seçeneğiyle işlemi tamamlayın.

10. Ekip aracısı (Apple Geliştirici Kurumsal Programı’na kuruluşunuz adına katılan kişi) sizseniz ilk olarak ekip üyelerini davet ederek ve rolleri atayarak ekibinizi oluşturun. Ekibinizi nasıl yöneteceğinizi öğrenmek için [Geliştirici Hesap Ekibinizi Yönetme](https://developer.apple.com/library/content/documentation/IDEs/Conceptual/AppDistributionGuide/ManagingYourTeam/ManagingYourTeam.html#//apple_ref/doc/uid/TP40012582-CH16-SW1) bölümündeki Apple belgelerini okuyun.

### <a name="steps-to-create-an-apple-signing-certificate"></a>Apple imzalama sertifikası oluşturma adımları

1. [Apple Geliştirici portalına](https://developer.apple.com/) gidin.

2. Sayfanın sağ üst kısmında **Hesap**’a tıklayın.

3. Kurumsal Apple kimliğinizle **oturum açın**.

4. **Sertifikalar, Kimlikler ve Profiller**’e tıklayın.

  ![Apple Geliştirici portalı](./media/iOS-signing-cert-1.png)

5. SCP ![Sağ üst köşedeki Apple Geliştirici portalı artı işaretine](./media/iOS-signing-cert-2.png) tıklayarak bir iOS sertifikası ekleyin.

6. **Üretim** altında **Şirket İçi ve Geçici** bir sertifika oluşturmayı seçin.

  ![Şirket içi ve Geçici sertifika seçin](./media/iOS-signing-cert-3.png)

  >[!NOTE]
  >Uygulamayı dağıtmayı planlamıyorsanız ve yalnızca dahili olarak test etmek istiyorsanız, Üretim sertifikası yerine bir iOS Uygulama Geliştirme sertifikası kullanabilirsiniz. Bir geliştirme sertifikası kullanıyorsanız mobil sağlama profilinin, uygulamanın yükleneceği cihazlara başvurduğundan emin olun.

7. Sayfanın altındaki **İleri**’ye tıklayın.

8. Mac OS bilgisayarınızdaki Anahtarlık Erişim uygulamasını kullanarak **Sertifika İmzalama İsteği (CSR)** oluşturma yönergelerini okuyun.

  ![CSR oluşturma yönergelerini okuyun](./media/iOS-signing-cert-4.png)

9. Bir Sertifika İmzalama İsteği oluşturmak için yukarıdaki yönergeleri izleyin. Mac OS bilgisayarınızda **Anahtarlık Erişimi** uygulamasını başlatın.

10. Ekranın üst kısmındaki Mac OS menüsünde **Anahtarlık Erişimi > Sertifika Yardımcısı > Bir Sertifika Yetkilisinden Sertifika İste** bölümüne gidin.  

  ![Anahtarlık Erişimi’nde bir Sertifika Yetkilisinden bir sertifika isteyin](./media/iOS-signing-cert-5.png)

11. Bir CSR dosyasının nasıl oluşturulacağını öğrenmek için Apple geliştirici sitesindeki yönergeleri izleyin. CSR dosyasını Mac OS bilgisayarınıza kaydedin.

  ![Anahtarlık Erişimi’nde bir Sertifika Yetkilisinden bir sertifika isteyin](./media/iOS-signing-cert-6.png)

12. Apple Geliştirici sitesine dönün. 
              **Devam**'a tıklayın. Ardından CSR dosyasını karşıya yükleyin.

13. Apple imzalama sertifikanızı oluşturur. Bunu indirin ve Mac OS bilgisayarınızda hatırlayacağınız bir konuma kaydedin.

  ![İmzalama sertifikanızı indirin](./media/iOS-signing-cert-7.png)

14. Sertifikayı bir anahtarlığa eklemek için indirmiş olduğunuz sertifika dosyasına çift tıklayın.

15. **Anahtarlık Erişimi**’ni yeniden açın. Sertifikanızı bulmak için sağ üst kısımdaki arama çubuğunda sertifikanızın adını aratın. Menünün görünmesini sağlamak için öğeye sağ tıklayın ve **Bilgi Al**’a tıklayın. Örnek ekranlarda üretim sertifikası yerine geliştirme sertifikası kullanıyoruz.

  ![Sertifikanızı bir anahtarlığa ekleyin](./media/iOS-signing-cert-8.png)

16. Bir bilgi iletisi görüntülenir. En alta kaydırın ve **Parmak izleri** etiketinin altına bakın. Uygulama Sarmalama Aracı’nda "-c" için bağımsız değişken olarak kullanmak üzere **SHA1** dizesini (bulanıklaştırılmış) kopyalayın.

  ![Sertifikanızı bir anahtarlığa ekleyin](./media/iOS-signing-cert-9.png)



### <a name="steps-to-create-an-in-house-distribution-provisioning-profile"></a>Şirket İçi Dağıtım Sağlama profili oluşturma adımları

1. [Apple Geliştirici hesabı portalına](https://developer.apple.com/account/) geri giderek kuruluşunuzun Apple kimliğiyle **oturum açın**.

2. **Sertifikalar, Kimlikler ve Profiller**’e tıklayın.

3. SCP ![Sağ üst köşedeki Apple Geliştirici portalı artı işaretine](./media/iOS-signing-cert-2.png) tıklayarak bir iOS sağlama profili ekleyin.

4. **Dağıtım** altında bir **Şirket içi** sağlama profili oluşturmayı seçin.

  ![Şirket içi sağlama profilini seçin](./media/iOS-provisioning-profile-1.png)

5. 
              **Devam**'a tıklayın. Önceden oluşturulan imzalama sertifikasını sağlama profiline bağladığınızdan emin olun.

6. Profilinizi (.mobileprovision uzantısı ile) Mac OS bilgisayarınıza yükleme adımlarını izleyin.

7. Dosyayı hatırlayacağınız bir konuma kaydedin. Bu dosya, Uygulama Sarmalama Aracı kullanılırken -p parametresi için kullanılır.



## <a name="download-the-app-wrapping-tool"></a>Uygulama Sarmalama Aracını indirin

1.  [GitHub](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios)'daki Uygulama Sarmalama Aracı dosyalarını bir macOS bilgisayara indirin.

2.  **Microsoft Intune App Wrapping Tool for iOS.dmg** dosyasına çift tıklayın. Son Kullanıcı Lisans Sözleşmesi (EULA) ile bir pencere görüntülenir. Belgeyi dikkatli okuyun.

3. Paketi bilgisayarınıza bağlayan EULA’yı kabul etmek için **Kabul et**’i seçin.

4.  **IntuneMAMPackager** klasörünü açın ve içeriğini macOS bilgisayarınıza kaydedin. Artık Uygulama Sarmalama Aracını çalıştırmaya hazırsınız.

> [!NOTE]
> Intune MAM Paketleyici, macOS bilgisayarınıza ayrı olarak takılabilir ve sarmalama komutlarını çalıştırırken bir “dosya bulunamadı” hatasına neden olabilir. Bu nedenle IntuneMAMPackager klasörünün içeriğini taşımak, sarmalama sırasında paketleyici yolunun bulunmasına olanak verir.

## <a name="run-the-app-wrapping-tool"></a>Uygulama Sarmalama Aracını çalıştırma

### <a name="use-terminal"></a>Terminal kullanma

macOS Terminal programını açın ve uygulama sarmalama aracı dosyalarını kaydettiğiniz klasöre gidin. Yürütülebilir aracın adı IntuneMAMPackager, bulunduğu konum IntuneMAMPackager/Contents/MacOS klasörüdür. Komutu aşağıdaki gibi çalıştırın:

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> -p /<path to provisioning profile> -c <SHA1 hash of the certificate> [-b [<output app build string>]] [-v] [-e] [-x /<array of extension provisioning profile paths>]
```

> [!NOTE]
> Bazı parametreler aşağıdaki tabloda gösterildiği gibi isteğe bağlıdır.

**Örnek:** Aşağıdaki örnek komut, MyApp.ipa adlı uygulamanın üzerinde Uygulama Sarmalama Aracı'nı çalıştırır. Bir sağlama profili ve imzalama sertifikasının SHA-1 karması belirtilir ve sarmalanan uygulamayı imzalamak için kullanılır. Uygulama çıktısı (MyApp_Wrapped.ipa) oluşturulur ve Masaüstü klasörünüzde depolanır.

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i ~/Desktop/MyApp.ipa -o ~/Desktop/MyApp_Wrapped.ipa -p ~/Desktop/My_Provisioning_Profile_.mobileprovision -c "12 A3 BC 45 D6 7E F8 90 1A 2B 3C DE F4 AB C5 D6 E7 89 0F AB"  -v true
```

### <a name="command-line-parameters"></a>Komut satırı parametreleri
Aşağıdaki komut satırı parametrelerini Uygulama Sarmalama Aracı ile birlikte kullanabilirsiniz:

|Özellik|Kullanımı|
|---------------|--------------------------------|
|**-i**|`<Path of the input native iOS application file>`. Dosya adının sonunda .app veya .ipa olmalıdır. |
|**-o**|`<Path of the wrapped output application>` |
|**-p**|`<Path of your provisioning profile for iOS apps>`|
|**-c**|`<SHA1 hash of the signing certificate>`|
|**-h**|Uygulama Sarmalama Aracı için kullanılabilir komut satırı özellikleri hakkında ayrıntılı kullanım bilgilerini gösterir.|
|**-v**|(İsteğe bağlı) Konsola ayrıntılı ileti çıkışı yapar. Bu bayrağın hataları ayıklamak için kullanılması önerilir.|
|**-e**| (İsteğe bağlı) Uygulama Sarmalama Aracının uygulamayı işlerken eksik yetkilendirmeleri kaldırmasını sağlamak için bu bayrağı kullanın. Daha fazla ayrıntı için [Uygulama yetkilendirmelerini ayarlama](#setting-app-entitlements) bölümüne bakın.|
|**-xe**| (İsteğe bağlı) Uygulamadaki iOS uzantıları hakkında bilgi ve bunları kullanmak için hangi yetkilendirmelerin gerektiğini yazdırır. Daha fazla ayrıntı için [Uygulama yetkilendirmelerini ayarlama](#setting-app-entitlements) bölümüne bakın. |
|**-x**| (İsteğe bağlı) `<An array of paths to extension provisioning profiles>`. Uygulamanızda uzantı sağlayan profiller gerekiyorsa bunu kullanın.|
|**-f**|(İsteğe bağlı) `<Path to a plist file specifying arguments.>` -i, -o ve -p gibi geri kalan IntuneMAMPackager özelliklerini belirtmek için plist şablonu kullanmayı tercih ederseniz bu bayrağı [plist](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html) dosyasının önünde kullanın. Bağımsız değişkenler girişi için bir plist kullanma bölümüne bakın. |
|**-b**|(İsteğe bağlı) Sarmalanan çıkış uygulamasının giriş uygulamasıyla aynı paket sürümüne sahip olmasını isterseniz (önerilmez), -b’yi bağımsız değişken olmadan kullanın. <br/><br/> Sarmalanan uygulamanın özel CFBundleVersion içermesini istiyorsanız `-b <custom bundle version>` kullanın. Özel CFBundleVersion belirtmek isterseniz, yerel uygulamanın CFBundleVersion’unun en az önemli bileşen tarafından artırılması iyi bir fikirdir, ör. 1.0.0 -> 1.0.1. |

### <a name="use-a-plist-to-input-arguments"></a>Bağımsız değişkenler girişi için bir plist kullanma
Uygulama Sarmalama Aracı’nı çalıştırmanın kolay bir yolu, tüm komut satırı bağımsız değişkenlerini bir [plist](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html) dosyasına yerleştirmektir. Plist, bir form arabirimi ile komut satırı bağımsız değişkenlerinizin girişi için kullanabileceğiniz, XML'e benzer bir dosya biçimidir.

IntuneMAMPackager/Contents/MacOS klasöründe, `Parameters.plist` öğesini (boş bir plist şablonu), bir metin düzenleyici veya Xcode ile açın. Aşağıdaki anahtarlar için bağımsız değişkenlerinizi girin:

| Plist anahtarı |  Varsayılan değer| Notlar |
|------------------|--------------|-----|
| Giriş Uygulama Paketi Yolu  |boş| -i ile aynı|
| Çıkış Uygulama Paketi Yolu |boş| -o ile aynı|
| Profil Yolu Sağlama |boş| -p ile aynı|
| SHA-1 Sertifika Karması |boş| -c ile aynı|
| Ayrıntılı Mod Etkin |yanlış| -v ile aynı|
| Eksik Yetkilendirmeleri Kaldır | yanlış| -c ile aynı|
| Varsayılan Derlemeyi Engelle |yanlış | Bağımsız değişkenler olmadan -b kullanma ile eşdeğerdir|
|Dize Geçersiz Kılmayı Derle | boş| Sarmalanan çıkış uygulaması için özel CFBundleVersion |
|Uzantı Sağlayan Profil Yolları | boş| Uygulamanın uzantı sağlama profillerinin bir dizisi.


IntuneMAMPackager’ı plist ile tek bağımsız değişken olarak çalıştırın:

```bash
./IntuneMAMPackager –f Parameters.plist
```

### <a name="post-wrapping"></a>Sarmalama sonrası

Sarmalama işlemi tamamlandıktan sonra, "Uygulama başarıyla sarmalandı" iletisi görüntülenir. Bir hata oluşursa yardım için [hata iletileri](#error-messages-and-log-files) sayfasına bakın.

Sarmalanan uygulama, daha önce belirttiğiniz çıkış klasörüne kaydedilir. Uygulamayı Intune yönetici konsoluna yükleyebilir ve bir mobil uygulama yönetimi ilkesi ile ilişkilendirebilirsiniz.

> [!IMPORTANT]
> Sarmalanan bir uygulama karşıya yüklenirken, uygulamanın eski bir sürümünü, eski sürüm (sarmalanan veya yerel) zaten Intune’da dağıtılmışsa güncelleştirmeyi deneyebilirsiniz. Bir hatayla karşılaşırsanız, uygulamayı yeni bir uygulama olarak karşıya yükleyip eski sürümü silin.

Artık uygulamayı kullanıcı gruplarınıza dağıtabilir ve uygulama için uygulama koruma ilkelerini hedefleyebilirsiniz. Uygulama cihazda belirttiğiniz uygulama ilkeleri kullanılarak çalıştırılır.

## <a name="how-often-should-i-rewrap-my-ios-application-with-the-intune-app-wrapping-tool"></a>Intune Uygulama Sarmalama Aracı ile iOS uygulamamı ne sıklıkta yeniden sarmalamalıyım?
Uygulamalarınızı yeniden sarmalamanız gereken ana senaryolar aşağıdaki gibidir:
* Uygulamanın yeni bir sürümünü yayınlandı. Uygulamanın önceki sürümü sarmalandı ve Intune konsoluna yüklendi.
* iOS için Intune Uygulama Sarmalama Aracı uygulamasının hata düzeltmeleri veya yeni, belirli Intune uygulama koruma ilkesi özellikleri içeren yeni bir sürümü yayınlandı. Bu, [iOS için Microsoft Intune Uygulama Sarmalama Aracı](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios) için 6-8 hafta sonra bir GitHub deposundan gerçekleşir.

iOS için, uygulamayı imzalamak için kullanılan asıl sertifika/sağlama profilinden farklı bir tanesi ile sarmalamak mümkün olsa da, uygulamada belirtilen yetkilendirmeler yeni sağlama profilinde mevcut değilse sarmalama başarısız olacaktır. Uygulamadaki eksik yetkilendirmeleri kaldıran “-e” komut satırı seçeneği kullanılarak sarmalama işleminin başarısız olmamaya zorlanması, uygulamada bozuk işlevselliğe yol açabilir.

Yeniden sarmalama için bazı en iyi uygulamalar şunlardır:
* Farklı bir sağlama profilinin önceki sağlama profillerindeki tüm gerekli yetkilendirmelere sahip olduğundan emin olmak. 

## <a name="error-messages-and-log-files"></a>Hata iletileri ve günlük dosyaları
Uygulama sarmalama aracında karşılaştığınız sorunları gidermek için aşağıdaki bilgileri kullanın.

### <a name="error-messages"></a>Hata iletileri
Uygulama sarmalama aracı başarılı bir şekilde tamamlanamazsa, konsolda aşağıdaki hata iletilerinden biri görüntülenir:

|Hata iletisi|Daha fazla bilgi|
|-----------------|--------------------|
|Geçerli bir iOS sağlama profili belirtmeniz gerekir.|Sağlama profiliniz geçerli olmayabilir. Cihazlar için doğru izinlere sahip olduğunuzdan ve profilinizin geliştirmeyi ya da dağıtımı doğru hedeflediğinden emin olun. Sağlama profilinizin süresi dolmuş da olabilir.|
|Geçerli bir giriş uygulaması adı belirtin.|Belirttiğiniz giriş uygulaması adının doğru olduğundan emin olun.|
|Çıkış uygulaması için geçerli bir yol belirtin.|Belirttiğiniz çıkış uygulaması yolunun var olduğundan ve doğru olduğundan emin olun.|
|Geçerli bir giriş sağlama profili belirtin.|Geçerli bir sağlama profili adı ve uzantısı sağladığınızdan emin olun. Sağlama profilinizde eksik yetkilendirmeler olabilir veya –p komut satırı seçeneğini eklememiş olabilirsiniz.|
|Belirtilen giriş uygulaması bulunamadı. Geçerli bir giriş uygulaması adı ve yolu belirtin.|Giriş uygulamanızın yolunun geçerli olduğundan ve var olduğundan emin olun. Giriş uygulamasının o konumda bulunduğundan emin olun.|
|Belirttiğiniz giriş sağlama profili dosyası bulunamadı. Geçerli bir giriş sağlama profili dosyası belirtin.|Giriş sağlama dosyasının yolunun geçerli olduğundan ve belirttiğiniz dosyanın var olduğundan emin olun.|
|Belirttiğiniz çıkış uygulaması klasörü bulunamadı. Çıkış uygulaması için geçerli bir yol belirtin.|Belirttiğiniz çıkış yolunun geçerli olduğundan ve var olduğundan emin olun.|
|Çıkış uygulaması **.ipa** uzantısına sahip değil.|Uygulama Sarmalama Aracı tarafından yalnızca **.app** ve **.ipa** uzantılarına sahip uygulamalar kabul edilir. Çıkış dosyanızın geçerli bir uzantısı olduğundan emin olun.|
|Geçersiz bir imzalama sertifikası belirtildi. Geçerli bir Apple imzalama sertifikası belirtin.|Apple geliştirici portalından doğru imzalama sertifikasını indirdiğinizden emin olun. Sertifikanızın süresi dolmuş olabilir veya bir ortak veya özel anahtar eksik olabilir. Apple sertifikanız ve sağlama profiliniz Xcode içinde bir uygulamayı doğru şekilde imzalamak için kullanılabiliyorsa, Uygulama Sarmalama Aracı için de geçerlidir.|
|Belirttiğiniz giriş uygulaması geçersiz. Geçerli bir uygulama belirtin.|Bir .app veya .ipa dosyası olarak derlenmiş geçerli bir iOS uygulamasına sahip olduğunuzdan emin olun.|
|Belirttiğiniz giriş uygulaması şifrelenmiş. Geçerli bir şifrelenmemiş uygulama belirtin.|Uygulama Sarmalama Aracı şifrelenmiş uygulamaları desteklemez. Şifrelenmemiş bir uygulama sağlayın.|
|Belirttiğiniz giriş uygulaması Position Independent Executable (PIE) biçiminde değil. PIE biçiminde geçerli bir uygulama belirtin.|Position Independent Executable (PIE) uygulamaları, çalıştırıldığında rastgele bir bellek adresinde yüklenebilir. Bu, güvenlik açısından faydalı olabilir. Güvenlik faydaları için Apple Geliştirici belgelerinize bakın.|
|Belirttiğiniz giriş uygulaması zaten sarmalanmış. Sarmalanmamış geçerli bir uygulama belirtin.|Araç tarafından işlenmiş olan bir uygulamayı işleyemezsiniz. Bir uygulamayı yeniden işlemek istiyorsanız, aracı uygulamanın orijinal sürümüyle çalıştırın.|
|Belirttiğiniz giriş uygulaması imzalı değil. Geçerli bir imzalı uygulama belirtin.|Uygulama sarmalama aracı, uygulamaların imzalı olmasını gerektirir. Sarmalanan bir uygulamanın nasıl imzalanacağını öğrenmek için geliştirici belgelerinize başvurun.|
|Belirttiğiniz giriş uygulaması .ipa veya .app biçiminde olmalıdır.|Uygulama sarmalama aracı tarafından yalnızca .app ve .ipa uzantıları kabul edilir. Giriş dosyanızın geçerli bir uzantısı olduğundan ve bir .app veya .ipa dosyası olarak derlendiğinden emin olun.|
|Belirttiğiniz giriş uygulaması zaten sarmalanmış ve ilke şablonunun son sürümünde yer alıyor.|Uygulama Sarmalama Aracı, var olan bir sarmalanmış uygulamayı ilkesi şablonunun son sürümü ile yeniden sarmalamaz.|
|UYARI: SHA1 sertifika karması belirtmediniz. Sarmalanan uygulamanızı dağıtmadan önce mutlaka imzalayın.|Geçerli bir SHA1 karması belirttiğinizden –c komut satırı bayrağını takip ederek emin olun. |

### <a name="log-files-for-the-app-wrapping-tool"></a>Uygulama Sarmalama Aracı için günlük dosyaları
Uygulama Sarmalama Aracı kullanılarak sarmalanan uygulamalar, iOS istemci cihaz konsoluna yazılan günlükler oluşturur. Bu bilgiler, uygulamayla ilgili sorun yaşadığınızda ve sorunun Uygulama Sarmalama Aracı ile ilişkili olup olmadığını belirlemeniz gerektiğinde yararlıdır. Bu bilgileri almak için aşağıdaki adımları kullanın:

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


### <a name="certificate-provisioning-profile-and-authentication-requirements"></a>Sertifika, sağlama profili ve kimlik doğrulaması gereksinimleri

Tam işlevsellik garantisi için iOS için Uygulama Sarmalama Aracında karşılanması gereken bazı gereksinimler vardır.

|Gereksinim|Ayrıntılar|
|---------------|-----------|
|iOS sağlama profili|Sağlama profilini dahil etmeden önce, geçerli olduğundan emin olun. Uygulama Sarmalama Aracı, bir iOS uygulamasını işlerken sağlama profilinin geçerlilik süresinin dolup dolmadığını denetlemez. Süresi dolmuş bir sağlama profili belirtilirse, uygulama sarmalama aracı süresi dolmuş sağlama profilini içerir ve uygulamanın bir iOS cihazına yüklenemediğini fark edene kadar bir sorun olduğunu anlayamazsınız.|
|iOS imzalama sertifikası|İmzalama sertifikasını belirtmeden önce, geçerli olduğundan emin olun. Araç, iOS uygulamalarını işlerken bir sertifikanın süresinin dolup dolmadığını denetlemez. Süresi dolmuş bir sertifika için karma sağlanırsa, araç uygulamayı işler ve imzalar, ancak uygulama cihazlara yüklenemez.<br /><br />Sarmalanan uygulamayı imzalamak için sağlanan sertifikanın, sağlama profilinde bir eşleşmeye sahip olduğundan emin olun. Araç, sağlama profilinin sarmalanan uygulamayı imzalamak için sağlanan sertifikaya yönelik bir eşleşme içerip içermediğini doğrulamaz.|
|Kimlik doğrulaması|Şifrelemenin çalışması için cihazın PIN’e sahip olması gerekir. Sarmalanan uygulama dağıtılan cihazlarda durum çubuğuna dokunma, kullanıcının iş veya okul hesabıyla yeniden oturum açmasını gerektirir. Sarmalanan bir uygulamada varsayılan ilke, *yeniden başlatma sırasında kimlik doğrulaması* şeklindedir. iOS tüm dış bildirimleri (bir telefon araması gibi) uygulamadan çıkıp uygulamayı yeniden başlatarak işler.


## <a name="setting-app-entitlements"></a>Uygulama yetkilendirmelerini ayarlama
Uygulamanızı sarmalamadan önce, uygulamaya normalde yapabildiklerini aşan ek izinler ve yetenekler sağlamak için *yetkilendirmeler* verebilirsiniz. *Yetkilendirme dosyası*, uygulamanızın içinde özel izinleri (örneğin, paylaşılan bir anahtarlığa erişim) belirlemek için kod imzalama sırasında kullanılır. *Yetenekler* olarak adlandırılan belirli uygulama hizmetleri, uygulama geliştirme sırasında Xcode içinde etkinleştirilir. Yetenekler bir kez etkinleştirildikten sonra, yetkilendirmeler dosyanız bunları yansıtır. Yetkilendirmeler ve yetenekler hakkında daha fazla bilgi için, iOS Geliştirici Kitaplığı’nda [Yetenekleri Ekleme](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) konusuna bakın. Desteklenen yeteneklerin tam listesi için bkz. [Desteklenen yetenekler](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/SupportedCapabilities/SupportedCapabilities.html).

### <a name="supported-capabilities-for-the-app-wrapping-tool-for-ios"></a>iOS için Uygulama Sarmalama Aracı’nda desteklenen yetenekler

|Özellik|Description|Önerilen yönerge|
|--------------|---------------|------------------------|
|Uygulama grupları|Birden çok uygulamanın paylaşılan kapsayıcılara erişimine ve uygulamalar arasında işlemler arası ek iletişime olanak tanımak için uygulama gruplarını kullanın.<br /><br />Uygulama gruplarını etkinleştirmek için, **Yetenekler** bölmesini açın ve **Uygulama Grupları** bölümünde **AÇIK**’a tıklayın. Uygulama grupları ekleyebilir veya var olanları seçebilirsiniz.|Uygulama Grupları’nı kullanırken, ters DNS gösterimini kullanın:<br /><br />*grup.com.şirketAdı.UygulamaGrubu*|
|Arka plan modları|Arka plan modlarının etkinleştirilmesi, iOS uygulamanızın arka planda çalışmaya devam etmesine olanak tanır.||
|Veri koruma|Veri koruma, iOS uygulamanız tarafından diskte depolanan dosyaların güvenlik düzeyini yükseltir. Veri koruma, dosyaları diskte şifrelenmiş biçimde depolamak için belirli cihazlarda bulunan yerleşik şifreleme donanımını kullanır. Uygulamanızın veri korumayı kullanması için hazırlanması gerekir.||
|Uygulama içi satın alma|Uygulama içi satın alma, mağazaya bağlanmanıza ve kullanıcının ödemelerini güvenli bir şekilde işlemenize olanak tanıyarak, mağazayı doğrudan uygulamanızın içine katıştırır. Uygulama içi satın alma yeteneğini kullanarak, gelişmiş işlevler veya uygulamanız tarafından kullanılabilen ek içerik için ödemeleri alabilirsiniz.||
|Anahtarlık paylaşımı|Anahtarlık paylaşımının etkinleştirilmesi, uygulamanızın ekibiniz tarafından geliştirilen diğer uygulamalarla anahtarlıkta parolaları paylaşabilmesini sağlar.|Anahtarlık paylaşımı kullanırken, ters DNS gösterimini kullanın:<br /><br />*com.şirketAdı.AnahtarlıkGrubu*|
|Kişisel VPN|Uygulamanızın Ağ Uzantısı çerçevesini kullanarak özel bir sistem VPN yapılandırması oluşturmasını ve bu yapılandırmayı denetlemesini sağlamak için kişisel VPN’yi etkinleştirin.||
|Anında bildirimler|Apple Anında İletilen Bildirim hizmeti (APNs), ön planda çalışmayan bir uygulamanın kullanıcıya verilecek bilgileri olduğunu bildirmesini sağlar.|Anında iletme bildirimlerinin çalışması için, uygulamaya özgü bir sağlama profili kullanmalısınız.<br /><br />[Apple geliştirici belgelerinde](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) verilen adımları izleyin.|
|Kablosuz aksesuar yapılandırması|Kablosuz aksesuar yapılandırması etkinleştirildiğinde, projenize Dış Aksesuar çerçevesi eklenir ve uygulamanızın MFi Wi-Fi aksesuarlarını ayarlamasına olanak tanınır.||

### <a name="steps-to-enable-entitlements"></a>Yetkilendirmeleri etkinleştirme adımları

1.  Uygulamanızda yetenekleri etkinleştirin:

    a.  Xcode’da, uygulamanızın hedefine gidin ve **Yetenekler** bölmesine tıklayın.

    b.  Uygun yetenekleri açın. Her yetenek hakkında ayrıntılı bilgi almak ve doğru değerlerin nasıl saptanacağını öğrenmek için, iOS Geliştirici Kitaplığı’nda [Yetenekleri Ekleme](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) konusuna bakın.

    c.  İşlem sırasında oluşturduğunuz tüm kimlikleri not alın.

    d.  Uygulamanızı oluşturun ve sarmalamak üzere imzalayın.

2.  Sağlama profilinizde yetkilendirmeleri etkinleştirin:

    a.  Apple Geliştirici Üye Merkezi’nde oturum açın.

    b.  Uygulamanız için bir sağlama profili oluşturun. Yönergeler için bkz. [iOS için Intune Uygulama Sarmalama Aracı’nın Önkoşulları Nasıl Elde Edilir](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/).

    c.  Sağlama profilinizde, uygulamanızda sahip olduğunuz yetkilendirmelerle aynı yetkilendirmeleri etkinleştirin. Uygulamanızın geliştirilmesi sırasında belirttiğiniz kimliklerle aynı kimlikleri sağlamanız gerekir.

    d.  Sağlama profili sihirbazını tamamlayın ve dosyanızı indirin.

3.  Tüm önkoşullara uyduğunuzdan emin olun ve ardından uygulamayı sarmalayın.

### <a name="troubleshoot-common-errors-with-entitlements"></a>Sık karşılaşılan yetkilendirme sorunlarını giderme
iOS için Uygulama Sarmalama Aracı yetkilendirme hatası gösterirse, aşağıdaki sorun giderme adımlarını deneyin.

|Sorun|Nedeni|Çözüm|
|---------|---------|--------------|
|Giriş uygulamasından oluşturulan yetkilendirmeler ayrıştırılamadı.|Uygulama Sarmalama Aracı, uygulamadan ayıklanan yetkilendirmeler dosyasını okuyamıyor. Yetkilendirmeler dosyası hatalı biçimlendirilmiş olabilir.|Uygulamanızın yetkilendirmeler dosyasını inceleyin. Bunun nasıl yapılacağı aşağıdaki yönergelerde açıklanmaktadır. Yetkilendirmeler dosyasını incelerken, yanlış biçimlendirilmiş söz dizimi olup olmadığını denetleyin. Dosya, XML biçiminde olmalıdır.|
|Sağlama profilinde yetkilendirmeler eksik (eksik yetkilendirmeler listelenmiştir). Uygulamayı, söz konusu yetkilendirmeleri içeren bir sağlama profiliyle yeniden paketleyin.|Sağlama profiliyle etkinleştirilen yetkilendirmelerle uygulamada etkinleştirilen yetenekler arasında bir uyuşmazlık var. Bu uyuşmazlık, belirli yeteneklerle ilişkilendirilen kimlikler için de geçerlidir (uygulama grupları ve anahtarlık erişimi gibi).|Genel olarak, uygulamayla aynı yetenekleri etkinleştiren yeni bir sağlama profili oluşturabilirsiniz. Profille uygulama arasında kimlikler eşleşmezse, Uygulama Sarmalama Aracı kimlikleri (yapabilirse) değiştirir. Yeni sağlama profili oluşturduktan sonra da bu hatayı almaya devam ediyorsanız, –e parametresini kullanarak uygulamadan yetkilendirmeleri kaldırabilirsiniz (Uygulamadan yetkilendirmeleri kaldırmak için –e parametresini kullanma bölümüne bakın).|

### <a name="find-the-existing-entitlements-of-a-signed-app"></a>İmzalı bir uygulamanın var olan yetkilendirmelerini bulma
İmzalı uygulamanın ve sağlama profilinin var olan yetkilendirmelerini gözden geçirmek için:

1.  .ipa dosyasını bulun ve uzantısını .zip olarak değiştirin.

2.  .zip dosyasını genişletin. Bu işlem, .app paketinizi içeren bir Payload klasörü oluşturur.

3.  .app paketinde yetkilendirmeleri denetlemek için kod imzalama aracını kullanın; burada `YourApp.app`, .app paketinizin gerçek adıdır:

    ```
    $ codesign -d --entitlements :- "Payload/YourApp.app"
    ```

4.  Uygulamanın gömülü sağlama profilinin yetkilendirmelerini denetlemek için güvenlik aracını kullanın; burada `YourApp.app`, .app paketinizin gerçek adıdır.

    ```
    $ security -D -i "Payload/YourApp.app/embedded.mobileprovision"
    ```

### <a name="remove-entitlements-from-an-app-by-using-the-e-parameter"></a>Uygulamadan yetkilendirmeleri kaldırmak için –e parametresini kullanma
Bu komut, uygulamada etkinleştirilmiş olan ve yetkilendirmeler dosyasında yer almayan tüm yetenekleri kaldırır. Uygulama tarafından kullanılmakta olan yetenekleri kaldırırsanız, uygulamanız bozulabilir. Eksik yetenekleri kaldırabileceğiniz durumlara örnek olarak, tüm yeteneklere varsayılan olarak sahip olan, satıcı tarafından oluşturulmuş bir uygulama verilebilir.

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager –i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> –p /<path to provisioning profile> –c <SHA1 hash of the certificate> -e
```

## <a name="security-and-privacy-for-the-app-wrapping-tool"></a>Uygulama Sarmalama Aracı için güvenlik ve gizlilik
Uygulama Sarmalama Aracını kullanırken, güvenlik ve gizlilik açısından aşağıdaki en iyi uygulamaları kullanın.

-   Belirttiğiniz imzalama sertifikası, sağlama profili ve iş kolu uygulaması, uygulama sarmalama aracını çalıştırmak için kullandığınız Mac OS makinesinde olmalıdır. Dosyalar bir UNC yolu üzerindeyse, bunların Mac OS makineden erişilebilir olduğundan emin olun. Yol, IPsec veya SMB imzalama aracılığıyla korunmalıdır.

    Yönetici konsoluna içeri aktarılan kaydırılan uygulama, aracı çalıştırdığınız bilgisayarda bulunmalıdır. Dosya bir UNC yolu üzerindeyse, yolun yönetici konsolunu çalıştıran bilgisayarda erişilebilir durumda olduğundan emin olun. Yol, IPsec veya SMB imzalama aracılığıyla korunmalıdır.

-   Uygulama Sarmalama Aracının GitHub deposundan indirildiği ortamın IPsec veya SMB imzalama aracılığıyla korunması gerekir.

-   İşlediğiniz uygulama, saldırılara karşı koruma sağlamak için güvenilir bir kaynaktan gelmelidir.

-   Uygulama Sarmalama Aracında belirttiğiniz çıkış klasörünün, özellikle uzak bir klasör ise, güvenli olduğundan emin olun.

-   Karşıya dosya yükleme iletişim kutusu içeren iOS uygulamaları, kullanıcıların uygulama için geçerli olan kes, kopyala ve yapıştır kısıtlamalarını aşmasına imkan sağlar. Örneğin, bir kullanıcı karşıya dosya yükleme iletişim kutusunu kullanarak uygulama verilerinin ekran görüntüsünü karşıya yükleyebilir.

-   Cihazınızdaki belgeler klasörünü sarmalanan bir uygulamadan izliyorsanız, .msftintuneapplauncher adında bir klasör görebilirsiniz. Bu dosyayı değiştirir veya silerseniz, bu, kısıtlanan uygulamaların düzgün çalışmasını etkileyebilir.

## <a name="getting-logs-for-your-wrapped-applications"></a>Sarmalanmış uygulamalarınız için günlükleri alma
Sorun giderme sırasında sarmalanmış uygulamalarınızın günlüklerini almak için aşağıdaki adımları kullanın.

1. Cihazınızda iOS Ayarları uygulamasına gidin ve LOB uygulamanızı seçin.
2. **Tanılama Konsolu** düğmesini **Açık** duruma getirin.
3. LOB uygulamanızı başlatın.
4. "Başlarken" bağlantısına tıklayın.
5. Artık uygulamaları e-posta aracılığıyla veya bir OneDrive konumuna kopyalayarak paylaşabilirsiniz.

>[!NOTE]
Günlük işlevi, Intune Uygulama Sarmalama Aracı sürüm 7.1.13 veya üstüyle sarmalanmış uygulamalar için etkinleştirilir.

### <a name="see-also"></a>Ayrıca bkz:
- [Microsoft Intune ile uygulamaların mobil uygulama yönetimi için nasıl hazırlanacağına karar verme](apps-prepare-mobile-application-management.md)</br>
- [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)</br>
- [SDK’yı kullanarak uygulamaları mobil uygulama yönetimi için etkinleştirme](/intune-classic/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management)
