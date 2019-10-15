---
title: Android için Microsoft Intune uygulama SDK 'Sı Geliştirici Kılavuzu
description: Android için Microsoft Intune uygulama SDK 'Sı, Intune mobil uygulama yönetimi 'ni (MAM) Android uygulamanıza eklemenizi sağlar.
keywords: SDK
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/14/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: b4316c155645ad8e956cfd89c448da688ac133b3
ms.sourcegitcommit: 45d7c76e760c5117bf134fb57f7e248e5b6c4ad5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72314552"
---
# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a>Android için Microsoft Intune uygulama SDK 'Sı Geliştirici Kılavuzu

> [!NOTE]
> Öncelikle SDK 'nın geçerli özelliklerini kapsayan ve desteklenen her platformda tümleştirmeye nasıl hazırlanılacağını açıklayan [Intune uygulama SDK 'sına genel bakış](app-sdk.md)bölümünü okumak isteyebilirsiniz.

Android için Microsoft Intune uygulama SDK 'Sı, Intune uygulama koruma ilkelerini ( **App** veya mam ilkeleri olarak da bilinir) yerel Android uygulamanıza eklemenizi sağlar. Intune ile yönetilen bir uygulama, Intune uygulama SDK 'Sı ile tümleştirilmiş bir uygulamadır. Intune uygulamayı etkin bir şekilde yönetirken, Intune yöneticileri uygulama koruma ilkelerini Intune tarafından yönetilen uygulamanıza kolayca dağıtabilir.


## <a name="whats-in-the-sdk"></a>SDK 'da neler vardır?

Intune uygulama SDK 'Sı aşağıdaki dosyalardan oluşur:

* **Microsoft. Intune. mam. SDK. AAR**: SDK bileşenleri, destek kitaplığı jar dosyaları hariç.
* **Microsoft. Intune. mam. SDK. support. v4. jar**: Android v4 destek kitaplığını kullanan uygulamalarda mam özelliğini etkinleştirmek için gereken sınıflar.
* **Microsoft. Intune. mam. SDK. support. v7. jar**: Android v7 destek kitaplığını kullanan uygulamalarda mam özelliğini etkinleştirmek için gereken sınıflar.
* **Microsoft. Intune. mam. SDK. support. v17. jar**: Android v17 destek kitaplığını kullanan uygulamalarda mam özelliğini etkinleştirmek için gereken sınıflar. 
* **Microsoft. Intune. mam. SDK. support. Text. jar**: `android.support.text` paketindeki Android destek kitaplığı sınıflarını kullanan uygulamalarda mam özelliğini etkinleştirmek için gereken sınıflar.
* **Microsoft. Intune. mam. SDK. Downlevelsaplamalar. AAR**: Bu AAR, yalnızca daha yeni cihazlarda bulunan ancak `MAMActivity` ' deki yöntemlerle başvurulan Android sistem sınıfları için yer tutucular içerir. Daha yeni cihazlar, bu saplama sınıflarını yoksayacak. Bu AAR yalnızca, uygulamanız `MAMActivity` ' dan türetilen sınıflarda yansıma gerçekleştirdiğinde ve çoğu uygulamanın bu uygulamayı içermesi gerekmiyorsa gereklidir. AAR, tüm sınıflarını hariç tutmak için ProGuard kuralları içerir.
* **com. Microsoft. Intune. mam. Build. jar**: [SDK 'yı tümleştirmede yardımcı](#build-tooling)olan bir Gradle eklentisi.
* **Changelog. txt**: her SDK sürümünde yapılan değişikliklerin kaydını sağlar.
* **Üçüncü taraf bildirimleri. TXT**: uygulamanıza derlenecek üçüncü taraf ve/veya OSS kodunu bildiren bir atısyon bildirimi.

## <a name="requirements"></a>Gereksinimler

### <a name="android-versions"></a>Android sürümleri
SDK, Android API 28 (Android 9,0) aracılığıyla Android API 19 (Android 4.4 +) destekler.

### <a name="company-portal-app"></a>Şirket Portalı uygulaması
Android için Intune uygulama SDK 'Sı, uygulama koruma ilkelerini etkinleştirmek için cihazda [Şirket portalı](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) uygulamasının varlığını kullanır. Şirket Portalı, Intune hizmetinden uygulama koruma ilkelerini alır. Uygulama başlatıldığında, bu ilkeyi Şirket Portalı zorlamak için ilkeyi ve kodu yükler.

> [!NOTE]
> Şirket Portalı uygulaması cihazda olmadığında, Intune ile yönetilen bir uygulama, Intune uygulama koruma ilkelerini desteklemeyen normal bir uygulamayla aynı şekilde davranır.

Cihaz kaydı olmadan uygulama koruması için, kullanıcının Şirket Portalı uygulamasını kullanarak cihazı _**kaydetmesi gerekmez.**_

## <a name="sdk-integration"></a>SDK tümleştirmesi

### <a name="sample-app"></a>Örnek uygulama
Intune uygulama SDK 'Sı ile nasıl tümleştirileceğini bir örnek [GitHub](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Android-App)' da bulunabilir. Bu örnek [Gradle Build eklentisini](#gradle-build-plugin)kullanır.

### <a name="referencing-intune-app-libraries"></a>Intune uygulama kitaplıklarına başvurma

Intune uygulama SDK 'Sı, dış bağımlılıkları olmayan standart bir Android kitaplığıdır. **Microsoft. Intune. mam. SDK. AAR** , uygulama koruma ilkesinin etkinleştirilmesi için gereken arabirimleri ve Microsoft Intune şirket portalı uygulamasıyla birlikte çalışmak için gereken kodu içerir.

**Microsoft. Intune. mam. SDK. AAR** , Android kitaplığı başvurusu olarak belirtilmelidir. Bunu yapmak için, uygulama projenizi Android Studio açın ve **dosya > yeni > yeni modüle** gidin ve içeri aktar ' ı seçin **. JAR/. AAR paketi**. Ardından, için bir modül oluşturmak üzere Microsoft. Intune. MAM. SDK. AAR Android arşiv paketimizi seçin. AAR. Uygulama kodunuzu içeren modüle veya modüllere sağ tıklayın ve **Modül ayarları** > **Bağımlılıklar Sekmesi** >  **+ simge** > **Modül bağımlılığı** ' na gidin > **Tamam**' a tıklayarak yeni > oluşturduğunuz mam SDK AAR modülünü seçin. Bu, projenizi oluşturduğunuzda modülünüzün MAM SDK ile derlendiğinden emin olur.

Ayrıca, **Microsoft. Intune. mam. SDK. support. xxx. jar** kitaplıkları karşılık gelen `android.support.XXX` kitaplıklarının Intune türevlerini içerir. Uygulamanın destek kitaplıklarına bağlı olması gerekmiyorsa, Microsoft. Intune. MAM. SDK. AAR içinde yerleşik değildir.

#### <a name="proguard"></a>ProGuard

Yapı adımı olarak [Proguard](http://proguard.sourceforge.net/) (veya başka bir küçültme/gizleme mekanizması) KULLANıLıYORSA, SDK 'nın dahil olması gereken ek yapılandırma kuralları vardır. Dahil olmak üzere. Yapımızda AAR, kurallarımız Proguard adımla otomatik olarak tümleştirilir ve gerekli sınıf dosyaları tutulur.

Azure Active Directory kimlik doğrulama kitaplıkları (ADAL) kendi ProGuard kısıtlamalarına sahip olabilir. Uygulamanız ADAL 'yi tümleştirirse, bu kısıtlamaların ADAL belgelerini izlemeniz gerekir.

### <a name="policy-enforcement"></a>İlke zorlama
Intune uygulama SDK 'Sı, uygulamanızın Intune ilkelerini desteklemesini ve zorlamasına katılmasını sağlayan bir Android kitaplığıdır. 

Çoğu ilke yarı otomatik olarak zorlanır, ancak bazı ilkeler [uygulamanızdan zorla zorlamak için açık katılım](#enable-features-that-require-app-participation)gerektirir.
Kaynak tümleştirmesi gerçekleştirmenizi veya tümleştirme için yapı araçları 'nı kullanmayı, açık katılım gerektiren ilkelerin için kodlanmış olması gerekir.

Otomatik olarak zorlanan ilkeler için, uygulamaların MAM eşdeğerlerine devralmayla çeşitli Android temel sınıflarından devralım ve benzer şekilde belirli Android sistem hizmeti sınıflarına yapılan çağrıları MAM eşdeğerleri ile değiştirmesine izin vermek gerekir. Gerekli olan değişiklikler [aşağıda](#class-and-method-replacements) ayrıntılıdır ve kaynak tümleştirmeyle el ile gerçekleştirilebilir veya derleme araçları aracılığıyla otomatik olarak gerçekleştirilebilir.

### <a name="build-tooling"></a>Yapı araçları
SDK, derleme araçları (Gradle derlemeleri için bir eklenti ve Gradle derlemeleri için bir komut satırı aracı) ile otomatik olarak MAM eşdeğer değişiklikler gerçekleştirir. Bu araçlar, Java derlemesi tarafından oluşturulan sınıf dosyalarını dönüştürür ve özgün kaynak kodunu değiştirmez.

Araçlar yalnızca [doğrudan değiştirme](#class-and-method-replacements) işlemleri gerçekleştirir. [Farklı kaydet ilkesi](#enable-features-that-require-app-participation), [çok kimlikli](#multi-identity-optional), [App-we kaydı](#app-protection-policy-without-device-enrollment), [AndroidManifest DEĞIŞIKLIKLERI](#manifest-replacements) veya [adal yapılandırması](#configure-azure-active-directory-authentication-library-adal) gibi daha karmaşık SDK tümleştirmelerini gerçekleştirmediklerinden, bunlar uygulama tam Intune etkindir. Lütfen uygulamanızla ilgili tümleştirme noktaları için bu belgenin geri kalanını dikkatle gözden geçirin.

> [!NOTE]
> El ile yapılan değişiklikler aracılığıyla MAM SDK 'sının kısmi veya tamamen kaynak tümleştirmesini zaten gerçekleştiren bir projeye karşı araçların çalıştırılması iyi bir hale gelir. Projeniz yine de bağımlılık olarak MAM SDK 'sını listemalıdır.

### <a name="gradle-build-plugin"></a>Gradle derleme eklentisi
Uygulamanız Gradle ile derlenmezse [komut satırı aracıyla tümleştirilmesine](#command-line-build-tool)atlayın. 

Uygulama SDK 'sı eklentisi SDK 'nın bir parçası olarak **GradlePlugin/com. Microsoft. Intune. mam. Build. jar**olarak dağıtılır. Gradle 'ın eklentiyi bulabilmesi için buildscript sınıfdosyasına eklenmesi gerekir. Eklenti, eklenmesi gereken [Javassist](https://jboss-javassist.github.io/javassist/)'ye bağımlıdır. Bunları Sınıfyoluna eklemek için kök @no__t şunu ekleyin-0

```groovy
buildscript {
    repositories {
        jcenter()
    }
    dependencies {
        classpath "org.javassist:javassist:3.22.0-GA"
        classpath files("$PATH_TO_MAM_SDK/GradlePlugin/com.microsoft.intune.mam.build.jar")
    }
}
```

Ardından, APK projeniz için `build.gradle` dosyasında, eklentiyi şu şekilde uygulayın
```groovy
apply plugin: 'com.microsoft.intune.mam'
```

Varsayılan olarak, eklenti **yalnızca** `project` bağımlılıklarında çalışır.
Test derlemesi etkilenmedi. Yapılandırma, listeye sağlanıyor
*  Hariç tutulacak projeler
*  [Dahil edilecek dış bağımlılıklar](#usage-of-includeexternallibraries) 
*  İşlemeden çıkarılacak belirli sınıflar
*  İşlemeden hariç tutulacak çeşitler. Bunlar, tamamen bir varyant adına veya tek bir Flavor öğesine başvurabilir. Örneğin:
     * uygulamanızda derleme türleri varsa, {`savory`, `sweet`} ve {`vanilla`, `chocolate`} türleri ile 0 @no__t ve `release` ' i belirtirseniz
     * `savory` ' dan tüm varyantları hariç tutmak için-1 veya yalnızca bu tam değişkeni dışlamak için-1 @no__t.

#### <a name="example-partial-buildgradle"></a>Örnek kısmi derleme. Gradle

```groovy

apply plugin: 'com.microsoft.intune.mam'

dependencies {
    implementation project(':product:FooLib')
    implementation project(':product:foo-project')
    implementation fileTree(dir: "libs", include: ["bar.jar"])
    implementation fileTree(dir: "libs", include: ["zap.jar"])
    implementation "com.contoso.foo:zap-artifact:1.0.0"
    implementation "com.microsoft.bar:baz:1.0.0"
    implementation "com.microsoft.qux:foo:2.0"

    // Include the MAM SDK
    implementation files("$PATH_TO_MAM_SDK/Microsoft.Intune.MAM.SDK.aar")
}
intunemam {
    excludeProjects = [':product:FooLib']
    includeExternalLibraries = ['bar.jar', "com.contoso.foo:zap-artifact", "com.microsoft.*", "!com.microsoft.qux*"]
    excludeClasses = ['com.contoso.SplashActivity']
    excludeVariants=['savory']
}
```

Bu, aşağıdaki etkilere sahip olacaktır:
* `:product:FooLib` ' a eklendiğinden `excludeProjects`
* `:product:foo-project`, `excludeClasses` ' de olduğu için Atlanan `com.contoso.SplashActivity` dışında yeniden yazıldı
* `bar.jar` ' a eklendiğinden `includeExternalLibraries`
* `zap.jar` bir proje olmadığından ve `includeExternalLibraries` ' ye dahil edilmediğinden, bu değer **yeniden yazıldı**
* `com.contoso.foo:zap-artifact:1.0.0` ' a eklendiğinden `includeExternalLibraries`
* `com.microsoft.bar:baz:1.0.0`, joker karakter (`com.microsoft.*`) aracılığıyla `includeExternalLibraries` ' de yer aldığı için yeniden yazılmıştır.
* `com.microsoft.qux:foo:2.0`, açıkça bir olumsuzlama düzeniyle dışlandığı için, önceki öğeyle aynı joker karakterle eşleşse de yeniden verilmez.

#### <a name="usage-of-includeexternallibraries"></a>Includeexternallibraries kullanımı

Eklenti yalnızca proje bağımlılıkları üzerinde (genellikle `project()` işlevi tarafından sağlanmış) çalıştığı için, MAM-1 @no__t tarafından belirtilen veya Maven ya da diğer paket kaynaklarından elde edilen tüm bağımlılıklar (ör. "`com.contoso.bar:baz:1.2.0`"), ise `includeExternalLibraries` özelliğine sağlanmalıdır. bunların işlenmesi aşağıda açıklanan ölçütlere göre gereklidir. Joker karakterler ("*") desteklenir. @No__t-0 ' dan başlayan bir öğe değildir ve başka bir joker karakterle dahil edilecek kitaplıkları hariç tutmak için kullanılabilir.

Yapıt gösterimi ile dış bağımlılıklar belirtirken, `includeExternalLibraries` değerindeki sürüm bileşenini atlamak önerilir. Sürümü dahil ederseniz, tam bir sürüm olmalıdır. Dinamik sürüm belirtimleri (ör. `1.+`) desteklenmez.

@No__t-0 ' a kitaplık dahil etmeniz gerekip gerekmediğini öğrenmek için kullanmanız gereken genel kural, iki soruyu temel alır:
1. Kitaplıkta MAM eşdeğerleri bulunan sınıflar var mı? Örnekler: `Activity`, `Fragment`, `ContentProvider`, `Service` vb.
2. Yanıt Evet ise, uygulamanız bu sınıfları kullanıyor mu?

Bu soruların her ikisine de ' Yes ' yanıtı verirseniz, bu kitaplığı `includeExternalLibraries` ' a eklemeniz gerekir. 

| Senaryo | Şunları Içermelidir? |
|--|--|
| Uygulamanıza bir PDF görüntüleyici Kitaplığı ekleyin ve kullanıcılar PDF 'Leri görüntülemeye çalıştıklarında uygulamanızda `Activity` ' yı kullanırsınız | Yes |
| Gelişmiş Web performansı için uygulamanıza bir HTTP kitaplığı dahil edersiniz | Hayır |
| @No__t-0, `Application` ve `Fragment` ' den türetilmiş sınıfları içeren, yanıt verme gibi bir kitaplık ekleyin ve bu sınıfları uygulamanızda veya daha fazla türetirsiniz. | Yes |
| @No__t-0, `Application` ve `Fragment` ' den türetilmiş sınıfları içeren yanıt verme gibi bir kitaplık dahil edersiniz, ancak yalnızca statik yardımcılar veya yardımcı program sınıfları kullanıyorsunuz | Hayır |
| @No__t-0 ' dan türetilmiş görünüm sınıflarını içeren bir kitaplık ekler ve bu sınıfları uygulamanızda veya daha fazla türetirsiniz | Yes |

#### <a name="reporting"></a>Raporlama
Yapı eklentisi, yaptığı değişikliklerin HTML raporunu oluşturabilir. Bu raporun oluşturulmasını istemek için `intunemam` yapılandırma bloğunda `report = true` belirtin. Oluşturulduysa, rapor derleme dizinine `outputs/logs` ' a yazılır.

```groovy
intunemam {
    report = true
}
```

#### <a name="verification"></a>Doğrulama
Derleme eklentisi, işleme sınıflarında olası hataları aramak için ek doğrulama çalıştırabilir. Bunu istemek için `intunemam` yapılandırma bloğunda `verify = true` belirtin. Bu, eklentinin görevinin aldığı zamana birkaç saniye ekleyebileceğini unutmayın.

```groovy
intunemam {
    verify = true
}
```

#### <a name="incremental-builds"></a>Artımlı derlemeler
Artımlı oluşturma desteğini etkinleştirmek için `intunemam` yapılandırma bloğunda `incremental = true` belirtin.  Bu, yalnızca değişmiş olan giriş dosyalarını işleyerek derleme performansını artırmaya yönelik deneysel bir özelliktir.  Varsayılan yapılandırma `false` ' dır.

```groovy
intunemam {
    incremental = true
}
```

#### <a name="dependencies"></a>Bağımlılıklar

Gradle eklentisinin [Javassist](https://jboss-javassist.github.io/javassist/)'ye bağımlılığı vardır ve bu, Gradle 'in bağımlılık çözümlemesi için kullanılabilir olması gerekir (yukarıda açıklandığı gibi). Javassist yalnızca eklenti çalıştırılırken derleme zamanında kullanılır. Uygulamanıza Javassist kodu eklenmez.

> [!NOTE] 
> Android Gradle Plugin ve Gradle 4,1 ya da daha yeni sürümü 3,0 veya daha yeni bir sürümünü kullanıyor olmanız gerekir.

### <a name="command-line-build-tool"></a>Komut satırı derleme aracı
Derlemeniz Gradle kullanıyorsa, [sonraki bölüme](#class-and-method-replacements)atlayın.

Komut satırı derleme aracı, SDK 'nın `BuildTool` klasöründe bulunur. Yukarıdaki Gradle eklentisi ile aynı işlevi gerçekleştirir, ancak özel veya Gradle olmayan derleme sistemleriyle tümleştirilebilir. Daha genel olduğundan, çağırmak daha karmaşıktır, bu nedenle Gradle eklentisi bunu yapmak mümkün olduğunda kullanılmalıdır.

#### <a name="using-the-command-line-tool"></a>Komut satırı aracını kullanma

Komut satırı aracı, `BuildTool\bin` dizininde bulunan belirtilen yardımcı betikler kullanılarak çağrılabilir.

Araç aşağıdaki parametreleri bekler.

| Parametre | Açıklama |
| -- | -- |
| `--input` | Değiştirilecek olan jar dosyalarının ve sınıf dosyalarının dizinlerin noktalı virgülle ayrılmış listesi. Bu, yeniden yazmayı düşündüğünüz tüm jars/dizinleri içermelidir. |
| `--output` | Değiştirilen sınıfların depolanacak olan jar dosyalarının ve dizinlerin noktalı virgülle ayrılmış listesi. Giriş girişi başına bir çıkış girişi olması gerekir ve bunların sırasıyla listelenmesi gerekir. |
| `--classpath` | Derleme Sınıfyolu. Bu, hem jar dosyaları dışındaki hem de sınıf dizinleri içerebilir. |
| `--excludeClasses`| Yeniden yazma dışında tutulması gereken sınıfların adlarını içeren noktalı virgülle ayrılmış bir liste. |

İsteğe bağlı olan `--excludeClasses` hariç tüm parametreler gereklidir.

> [!NOTE]
> UNIX benzeri sistemlerde noktalı virgül, bir komut ayırıcısıdır. Kabuğun komut bölmesini önlemek için, her noktalı virgül ' \' ' ı attığınızdan veya tam parametreyi tırnak işaretleriyle sardığınızdan emin olun.

#### <a name="example-command-line-tool-invocation"></a>Örnek komut satırı aracı çağırma

``` batch
> BuildTool\bin\BuildTool.bat --input build\product-foo-project;libs\bar.jar --output mam-build\product-foo-project;mam-build\libs\bar.jar --classpath build\zap.jar;libs\Microsoft.Intune.MAM.SDK\classes.jar;%ANDROID_SDK_ROOT%\platforms\android-27\android.jar --excludeClasses com.contoso.SplashActivity
```

Bu, aşağıdaki etkilere sahip olacaktır:

* `product-foo-project` dizini `mam-build\product-foo-project` ' e yeniden yazıldı
* `bar.jar` `mam-build\libs\bar.jar` ' e yeniden yazıldı
* `zap.jar` yalnızca `--classpath` ' de listelendiğinden **yeniden yazıldı**
* @No__t-0 **sınıfı, @no__t** -2 ' de olsa bile yeniden yazılabilir

> [!NOTE] 
> Derleme aracı şu anda AAR dosyalarını desteklemiyor. Yapı sisteminiz, AAR dosyaları ile ilgilenirken `classes.jar` ' ı daha önceden ayıkladıysanız, derleme aracını çağırmadan önce bunu yapmanız gerekir.


## <a name="class-and-method-replacements"></a>Sınıf ve Yöntem değişiklikleri

Intune yönetimini etkinleştirmek için Android temel sınıflarının karşılık gelen MAM eşdeğerlerine göre değiştirilmeleri gerekir. SDK sınıfları, Android temel sınıfı ile uygulamanın kendi türetilmiş sürümü arasında canlı olarak vardır. Örneğin, bir uygulama etkinliği şu şekilde görünen bir devralma hiyerarşisi ile sona no__t: `Activity` @-1 @ no__t-2 @ no__t-3 @ no__t-4. MAM katmanı, uygulamanızı bir dünyanın yönetilen görünümüyle sorunsuz bir şekilde sağlamak için sistem işlemlerine çağrı uygular.

Temel sınıflara ek olarak, uygulamanızın türemesiz (örn. `MediaPlayer`), gerekli MAM eşdeğerleri de vardır ve [bazı yöntem çağrılarının de değiştirilmeleri gerekir](#wrapped-system-services). Kesin ayrıntılar aşağıda verilmiştir.

> [!NOTE] 
> Uygulamanız SDK [Yapı Araçları](#build-tooling)ile tümleştirildiğinde, aşağıdaki sınıf ve Yöntem değişiklikleri otomatik olarak gerçekleştirilir.

| Android temel sınıfı | Intune uygulama SDK 'Sı değiştirme |
|--|--|
| Android. app. Activity | MAMActivity |
| Android. app. ActivityGroup | MAMActivityGroup |
| Android. app. AliasActivity | MAMAliasActivity |
| Android. app. Application | MAMApplication |
| Android. app. Iletişim kutusu | MAMDialog Iletişim kutusu |
| Android. app. AlertDialog. Builder | Mamalcertdialogbuilder |
| Android. app. DialogFragment | MAMDialogFragment |
| Android. app. ExpandableListActivity | MAMExpandableListActivity |
| Android. app. Fragment | MAMFragment |
| Android. app. ıntservice | MAMIntentService |
| Android. app. LauncherActivity | MAMLauncherActivity |
| Android. app. ListActivity | MAMListActivity |
| Android. app. ListFragment | MAMListFragment |
| Android. app. NativeActivity | MAMNativeActivity |
| Android. app. Pendingamaç | Mampendingamacını (bkz. [bekleyen amaç](#pendingintent)) |
| Android. app. Service | MAMService |
| Android. app. TabActivity | MAMTabActivity |
| Android. app. TaskStackBuilder | MAMTaskStackBuilder |
| Android. app. Backup. BackupAgent | MAMBackupAgent |
| Android. app. Backup. BackupAgentHelper | MAMBackupAgentHelper |
| Android. app. Backup. FileBackupHelper | MAMFileBackupHelper |
| Android. app. Backup. SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
| Android. Content. Yayınalıcısı | Mambroadkalealıcısı |
| Android. Content. ContentProvider | MAMContentProvider |
| Android. OS. Ciltçi | MAMBinder (yalnızca bağlayıcı, Android arabirimi tanım dili (AıDL) arabiriminden oluşturulmasa gereklidir) |
| Android. Media. MediaPlayer | MAMMediaPlayer |
| Android. Media. MediaMetadataRetriever | MAMMediaMetadataRetriever |
| Android. Provider. DocumentsProvider | MAMDocumentsProvider |
| Android. Preference. PreferenceActivity | MAMPreferenceActivity |
| Android. support. multidex. MultiDexApplication | MAMMultiDexApplication |
| Android. pencere öğesi. TextView | MAMTextView |
| Android. pencere öğesi. AutoCompleteTextView | MAMAutoCompleteTextView |
| Android. pencere öğesi. CheckedTextView | MAMCheckedTextView |
| Android. pencere öğesi. EditText | MAMEditText |
| Android. ınputmethodservice. ExtractEditText | MAMExtractEditText |
| Android. pencere öğesi. MultiAutoCompleteTextView | MAMMultiAutoCompleteTextView |

> [!NOTE]
> Uygulamanızın kendi türetilmiş `Application` sınıfına ihtiyacı olmasa bile, [aşağıda `MAMApplication`](#mamapplication) ' ye bakın

### <a name="microsoftintunemamsdksupportv4jar"></a>Microsoft. Intune. MAM. SDK. support. v4. jar:

| Android sınıfı | Intune uygulama SDK 'Sı değiştirme |
|--|--|
| Android. support. v4. app. DialogFragment | MAMDialogFragment
| Android. support. v4. app. FragmentActivity | MAMFragmentActivity
| Android. support. v4. app. Fragment | MAMFragment
| Android. support. v4. app. Jobınttrservice | Mamjobtotservice
| Android. support. v4. app. TaskStackBuilder | MAMTaskStackBuilder
| Android. support. v4. Content. FileProvider | MAMFileProvider
| Android. support. v4. Content. WakefulBroadcastReceiver | MAMWakefulBroadcastReceiver

### <a name="microsoftintunemamsdksupportv7jar"></a>Microsoft. Intune. MAM. SDK. support. v7. jar:

|Android sınıfı | Intune uygulama SDK 'Sı değiştirme |
|--|--|
| Android. support. v7. app. AlertDialog. Builder | Mamalcertdialogbuilder |
| Android. support. v7. app. AppCompatActivity | MAMAppCompatActivity |
| Android. support. v7. pencere öğesi. AppCompatAutoCompleteTextView | MAMAppCompatAutoCompleteTextView |
| Android. support. v7. pencere öğesi. AppCompatCheckedTextView | MAMAppCompatCheckedTextView |
| Android. support. v7. pencere öğesi. AppCompatEditText | MAMAppCompatEditText |
| Android. support. v7. pencere öğesi. AppCompatMultiAutoCompleteTextView | MAMAppCompatMultiAutoCompleteTextView |
| Android. support. v7. pencere öğesi. AppCompatTextView | MAMAppCompatTextView |

### <a name="microsoftintunemamsdksupportv17jar"></a>Microsoft. Intune. MAM. SDK. support. v17. jar:
|Android sınıfı | Intune uygulama SDK 'Sı değiştirme |
|--|--|
| Android. support. v17. yeanback. pencere öğesi. SearchEditText | MAMSearchEditText |

### <a name="microsoftintunemamsdksupporttextjar"></a>Microsoft. Intune. MAM. SDK. support. Text. jar:
|Android sınıfı | Intune uygulama SDK 'Sı değiştirme |
|--|--|
| Android. support. Text. emoji. pencere öğesi. EmojiAppCompatEditText | MAMEmojiAppCompatEditText |
| Android. support. Text. emoji. pencere öğesi. EmojiAppCompatTextView | MAMEmojiAppCompatTextView |
| Android. support. Text. emoji. pencere öğesi. EmojiEditText | MAMEmojiEditText |
| Android. support. Text. emoji. pencere öğesi. EmojiTextView | MAMEmojiTextView |

### <a name="renamed-methods"></a>Yeniden adlandırılan Yöntemler
Çoğu durumda, Android sınıfında kullanılabilir olan bir yöntem MAM değiştirme sınıfında son olarak işaretlenir. Bu durumda, MAM değiştirme sınıfı benzer bir adlandırılmış Yöntem (genellikle `MAM` ile), bunun yerine geçersiz kılmanız gereken bir yöntem sağlar. Örneğin, `MAMActivity` ' dan türetmede, `onCreate()` ' i geçersiz kılmak ve `super.onCreate()` ' yi çağırmak yerine `Activity` `onMAMCreate()` ' ü geçersiz kılıp `super.onMAMCreate()` ' i çağırmalıdır Java derleyicisi, MAM eşdeğeri yerine özgün metodun yanlışlıkla geçersiz kılınmasını engellemek için son kısıtlamaları zorunlu kılmalıdır.

### <a name="mamapplication"></a>MAMApplication
Uygulamanız `android.app.Application` ' ı bir alt sınıfı oluşturursa, bunun yerine `com.microsoft.intune.mam.client.app.MAMApplication` ' nin bir alt sınıfını oluşturmanız **gerekir** . Uygulamanız `android.app.Application` ' ı alt sınıflara içermiyorsa, AndroidManifest. xml ' in `<application>` etiketinde `"android:name"` özniteliği olarak `"com.microsoft.intune.mam.client.app.MAMApplication"` ayarlamanız **gerekir** .

### <a name="pendingintent"></a>Pendingıntent
@No__t-0 yerine `MAMPendingIntent.get*` metodunu kullanmanız gerekir. Bundan sonra, sonuç `PendingIntent` ' ı her zamanki gibi kullanabilirsiniz.

### <a name="wrapped-system-services"></a>Sarmalanan sistem hizmetleri
Bazı sistem hizmeti sınıflarında, hizmet örneğinde istenen yöntemi doğrudan çağırmak yerine bir MAM sarmalayıcı sınıfında statik bir yöntem çağrılması gerekir. Örneğin, `getSystemService(ClipboardManager.class).getPrimaryClip()` ' a yapılan bir çağrı, `MAMClipboardManager.getPrimaryClip(getSystemService(ClipboardManager.class)` ' e bir çağrı olmalıdır. Bu değiştirmeler el ile yapılması önerilmez. Bunun yerine, BuildPlugin 'in bunu yapmasına izin verin.

| Android sınıfı | Intune uygulama SDK 'Sı değiştirme |
|--|--|
| Android. Content. ClipboardManager | MAMClipboard |
| Android. Content. ContentProviderClient | MAMContentProviderClientManagement |
| Android. Content. ContentResolver | MAMContentResolverManagement |
| Android. Content. PM. PackageManager | MAMPackageManagement |
| Android. app. DownloadManager | MAMDownloadManagement |
| Android. Print. PrintManager | MAMPrintManagement |
| Android. support. v4. Print. PrintHelper | MAMPrintHelperManagement |
| Android. View. View | MAMViewManagement |
| Android. View. DragEvent | MAMDragEventManagement |
| Android. app. NotificationManager | MAMNotificationManagement |
| Android. support. v4. app. NotificationManagerCompat | MAMNotificationCompatManagement |

Bazı sınıfların çoğu kendi yöntemlerinin çoğuna sahiptir; Örneğin, `ClipboardManager`, `ContentProviderClient`, `ContentResolver` ve `PackageManager`, diğer sınıflarda yalnızca bir veya iki yöntem sarmalanır, örn. `DownloadManager`, `PrintManager`, `PrintHelper`, `View`, `DragEvent`, `NotificationManager` ve 0. BuildPlugin kullanmazsanız, lütfen tam Yöntem için MAM denk sınıflar tarafından kullanıma sunulan API 'Lere başvurun.

### <a name="manifest-replacements"></a>Bildirim değişiklikleri
Daha önce bildirimde ve Java kodunda yukarıdaki sınıf değiştirmeler yerine getirmek gerekebilir. Özel notta:
* @No__t-0 ' a yönelik bildirim başvuruları `com.microsoft.intune.mam.client.support.v4.content.MAMFileProvider` ile değiştirilmelidir.

## <a name="androidx-libraries"></a>AndroidX kitaplıkları
Android P ile, Google, AndroidX adlı bir destek kitaplıkları kümesi ve var olan Android. support kitaplıklarının son büyük sürümüdür.

Android destek libs 'larından farklı olarak, AndroidX kitaplıklarının MAM türevlerini sağlamayız. Bunun yerine, AndroidX başka herhangi bir harici kitaplık olarak değerlendirilmeli ve derleme eklentisi/aracı tarafından yeniden yazılması gerekir. Gradle derlemeleri için bu, eklenti yapılandırmasının `includeExternalLibraries` alanına `androidx.*` eklenerek yapılabilir. Komut satırı aracının çağırmaları tüm jar dosyalarını açıkça listemalıdır.

### <a name="pre-androidx-architecture-components"></a>Ön AndroidX mimari bileşenleri
Oda, ViewModel ve WorkManager dahil pek çok Android mimarisi bileşeni AndroidX için yeniden paketlenmiştir. Uygulamanız bu kitaplıkların pre-AndroidX türevlerini kullanıyorsa, eklenti yapılandırması 'nın `includeExternalLibraries` alanına `android.arch.*` ekleyerek yeniden yazar uygulanmasını sağlayın. Alternatif olarak, kitaplıkları AndroidX eşdeğerlerine güncelleştirin.

## <a name="sdk-permissions"></a>SDK izinleri

Intune uygulama SDK 'Sı, kendisini tümleştiren uygulamalarda üç [Android Sistem izni](https://developer.android.com/guide/topics/security/permissions.html) gerektirir:

* `android.permission.GET_ACCOUNTS` (gerekirse çalışma zamanında istenen)

* `android.permission.MANAGE_ACCOUNTS`

* `android.permission.USE_CREDENTIALS`

Azure Active Directory kimlik doğrulama kitaplığı ([adal](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)), aracılı kimlik doğrulaması gerçekleştirmek için bu izinleri gerektirir. Bu izinler uygulamaya verilmezse veya Kullanıcı tarafından iptal edildiğinde, aracı gerektiren kimlik doğrulama akışları (Şirket Portalı uygulaması) devre dışı bırakılır.

## <a name="logging"></a>Günlüğe kaydetme

Günlüğe kaydedilen verilerden en iyi şekilde yararlanmak için günlüğe kaydetme erken başlatılmalıdır. `Application.onMAMCreate()` genellikle günlüğe kaydetmeyi başlatmak için en iyi yerdir.

Uygulamanızda MAM günlüklerini almak için bir [Java işleyicisi](https://docs.oracle.com/javase/7/docs/api/java/util/logging/Handler.html) oluşturun ve `MAMLogHandlerWrapper` ' e ekleyin. Bu işlem, her günlük iletisi için uygulama işleyicisinde `publish()` ' yı çağırır.

```java
/**
 * Global log handler that enables fine grained PII filtering within MAM logs.  
 *
 * To start using this you should build your own log handler and add it via
 * MAMComponents.get(MAMLogHandlerWrapper.class).addHandler(myHandler, false);  
 *
 * You may also remove the handler entirely via
 * MAMComponents.get(MAMLogHandlerWrapper.class).removeHandler(myHandler);
 */
public interface MAMLogHandlerWrapper {
    /**
     * Add a handler, PII can be toggled.
     *
     * @param handler handler to add.
     * @param wantsPII if PII is desired in the logs.    
     */
    void addHandler(final Handler handler, final boolean wantsPII);

    /**
     * Remove a handler.
     *
     * @param handler handler to remove.
     */
    void removeHandler(final Handler handler);
}
```

## <a name="enable-features-that-require-app-participation"></a>Uygulama katılımı gerektiren özellikleri etkinleştirme

SDK 'nın kendi başına uygulayamayacağı birkaç uygulama koruma ilkesi vardır. Uygulama, aşağıdaki `AppPolicy` arabiriminde bulabileceğiniz çeşitli API 'Leri kullanarak bu özellikleri elde etme davranışını denetleyebilir. @No__t-0 örneğini almak için `MAMPolicyManager.getPolicy` kullanın.

```java
/**
 * External facing application policies.
 */
public interface AppPolicy {

/**
 * Restrict where an app can save personal data.
  * This function is now deprecated. Use getIsSaveToLocationAllowed(SaveLocation, String) instead
 * @return True if the app is allowed to save to personal data stores; false otherwise.
 */
@Deprecated
boolean getIsSaveToPersonalAllowed();

/**
 * Check if policy prohibits saving to a content provider location.
 *
 * @param location
 *            a content URI to check
 * @return True if location is not a content URI or if policy does not prohibit saving to the content location.
 */
boolean getIsSaveToLocationAllowed(Uri location);

/**
 * Determines if the SaveLocation passed in can be saved to by the username associated with the cloud service.
 *
 * @param service
 *           see {@link SaveLocation}.
 * @param username
 *           the username/email associated with the cloud service being saved to. Use null if a mapping between
 *           the AAD username and the cloud service username does not exist or the username is not known.
 * @return true if the location can be saved to by the identity, false if otherwise.
 */
boolean getIsSaveToLocationAllowed(SaveLocation service, String username);

/**
 * Checks whether any activities which could handle the given intent are allowed by policy. Returns false only if all
 * activities which could otherwise handle the intent are blocked. If there are no activities which could handle the intent
 * regardless of policy, returns true. If some activities are allowed and others blocked, returns true. Note that it is not
 * necessary to use this method for policy enforcement. If your app attempts to launch an intent for which there are no
 * allowed activities, MAM will display a dialog explaining the situation to the user.
 *
 * @param intent
 *         intent to check
 *
 * @return whether any activities which could handle this intent are allowed.
*/
boolean areIntentActivitiesAllowed(Intent intent);

/**
 * Whether the SDK PIN prompt is enabled for the app.
 *
 * @return True if the PIN is enabled. False otherwise.
 */
boolean getIsPinRequired();

/**
 * Whether the Intune Managed Browser is required to open web links.
 * @return True if the Managed Browser is required, false otherwise
 */
boolean getIsManagedBrowserRequired();

/**
 * Check if policy allows taking screenshots.
 *
 * @return True if screenshots will be blocked, false otherwise
 */
boolean getIsScreenCaptureAllowed();

/**
 * Check if policy allows Contact sync to local contact list.
 *
 * @return True if Contact sync is allowed to save to local contact list; false otherwise.
 */
boolean getIsContactSyncAllowed();

/**
 * Get the notification restriction. If {@link NotificationRestriction#BLOCKED BLOCKED}, the app must not show any notifications
 * for the user associated with this policy. If {@link NotificationRestriction#BLOCK_ORG_DATA BLOCK_ORG_DATA}, the app must show
 * a modified notification that does not contain organization data. If {@link NotificationRestriction#UNRESTRICTED
 * UNRESTRICTED}, all notifications are allowed.
 *
 * @return The notification restriction.
 */
NotificationRestriction getNotificationRestriction();

/**
 * This method is intended for diagnostic/telemetry purposes only. It can be used to discover whether file encryption is in use.
 * File encryption is transparent to the app and the app should not need to make any business logic decisions based on this.
 * @return True if file encryption is in use.
 */
boolean diagnosticIsFileEncryptionInUse();

/**
 * Return the policy in string format to the app.
 *  
 * @return The string representing the policy.
 */
String toString();

}
```

> [!NOTE]
> `MAMPolicyManager.getPolicy`, cihaz veya uygulama bir Intune yönetim ilkesi altında olmasa bile her zaman null olmayan bir uygulama Ilkesi döndürür.

### <a name="example-determine-if-pin-is-required-for-the-app"></a>Örnek: uygulama için PIN gerekip gerekmediğini belirleme

Uygulamanın kendi PIN Kullanıcı deneyimi varsa, BT Yöneticisi SDK 'Yı bir uygulama PIN 'ı isteyecek şekilde yapılandırdıysa devre dışı bırakmak isteyebilirsiniz. BT yöneticisinin uygulama PIN ilkesini bu uygulamaya dağıtıp dağıtmadığını öğrenmek için, geçerli Son Kullanıcı için aşağıdaki yöntemi çağırın:

```java

MAMPolicyManager.getPolicy(currentActivity).getIsPinRequired();
```

### <a name="example-determine-the-primary-intune-user"></a>Örnek: birincil Intune kullanıcısını belirleme

AppPolicy ' de kullanıma sunulan API 'Lerin yanı sıra, Kullanıcı asıl adı (**UPN**), `MAMUserInfo` arabiriminde tanımlanan `getPrimaryUser()` API 'si tarafından da kullanıma sunulur. UPN 'yi almak için aşağıdakileri çağırın:

```java
MAMComponents.get(MAMUserInfo.class).getPrimaryUser();
```

Mamuserınfo arabiriminin tam tanımı aşağıda verilmiştir:

```java
/**
 * External facing user information.
 *
 */
public interface MAMUserInfo {
       /**
        * Get the primary user name.
        *
        * @return the primary user name or null if neither the device nor app is enrolled.
        */
       String getPrimaryUser();
}
```

### <a name="example-determine-if-saving-to-device-or-cloud-storage-is-permitted"></a>Örnek: cihaza veya bulut depolama alanına kaydetmeye izin verilip verilmediğini belirleme

Birçok uygulama, son kullanıcının dosyaları yerel olarak veya bir bulut depolama hizmetine kaydetmesine olanak tanıyan özellikler uygular. Intune uygulama SDK 'Sı, BT yöneticilerinin kuruluşlarında sığacak şekilde ilke kısıtlamaları uygulayarak veri sızıntılarına karşı koruma sağlamasına olanak tanır.  Denetleyebileceği ilkelerden biri, son kullanıcının "kişisel" ve yönetilmeyen bir veri deposuna kaydedilip edilmeyeceğini belirtir. Buna yerel bir konuma, SD karta veya üçüncü taraf yedekleme hizmetlerine kaydetme dahildir.

**Özelliği etkinleştirmek için uygulama katılımı gereklidir.** Uygulamanız kişisel veya bulut konumlarına doğrudan uygulamadan kaydetmeye izin veriyorsa, BT yöneticisinin bir konuma kaydetmeye izin verilip verilmediğini denetlemesini sağlamak için bu özelliği uygulamanız gerekir. Aşağıdaki API, uygulamanın, geçerli Intune yöneticisinin ilkesi tarafından kişisel bir mağazaya kaydedilmesine izin verilip verilmeyeceğini bilmesini sağlar. Uygulama, son kullanıcının uygulama aracılığıyla kullanabildiği kişisel veri deposunun farkında olduğundan ilkeyi uygulayabilir.  

İlkenin uygulanıp uygulanmadığını anlamak için aşağıdaki çağrıyı yapın:

```java
MAMPolicyManager.getPolicy(currentActivity).getIsSaveToLocationAllowed(
SaveLocation service, String username);
```

@No__t-0 parametresi aşağıdaki `SaveLocation` değerlerinden biri olmalıdır:


- `SaveLocation.ONEDRIVE_FOR_BUSINESS`
- `SaveLocation.SHAREPOINT`
- `SaveLocation.LOCAL`
- `SaveLocation.OTHER`

@No__t-0, kaydedilmekte olan bulut hizmeti ile ilişkili UPN/Kullanıcı adı/e-posta olmalıdır (Bu, kaydedilmekte olan kullanıcıyla aynı*olması gerekmez)* . AAD UPN ile bulut hizmeti Kullanıcı adı arasında bir eşleme yoksa veya Kullanıcı adı bilinmiyorsa null değerini kullanın. `SaveLocation.LOCAL` bir bulut hizmeti olmadığından, her zaman `null` Kullanıcı adı parametresiyle birlikte kullanılmalıdır.

Bir kullanıcının ilkesinin farklı konumlara veri kaydetmesine izin verip etmediğini belirleyen önceki Yöntem aynı **Apppolicy** sınıfı içinde `getIsSaveToPersonalAllowed()` ' dır. Bu işlev artık **kullanım dışıdır** ve kullanılmamalıdır, aşağıdaki çağrı `getIsSaveToPersonalAllowed()` ' e eşdeğerdir:

```java
MAMPolicyManager.getPolicy(currentActivity).getIsSaveToLocationAllowed(SaveLocation.LOCAL, null);
```

>[!NOTE]
> Söz konusu konum **Saveloot** numaralandırmasında listelenmiyorsa `SaveLocation.OTHER` kullanın.

### <a name="example-determine-if-notifications-with-organization-data-need-to-be-restricted"></a>Örnek: kuruluş verilerine sahip bildirimlerin kısıtlanması gerekip gerekmediğini belirleme

Uygulamanız bildirimleri görüntülüyorsa, bildirimi göstermeden önce bildirimle ilişkili kullanıcı için bildirim kısıtlama ilkesini denetlemeniz gerekir. İlkenin uygulanıp uygulanmadığını anlamak için aşağıdaki çağrıyı yapın.

```java
NotificationRestriction notificationRestriction =
    MAMPolicyManager.getPolicyForIdentity(notificationIdentity).getNotificationRestriction();
```

Kısıtlama `BLOCKED` ise, uygulamanın bu ilkeyle ilişkili kullanıcı için herhangi bir bildirim göstermemelidir. @No__t-0 ise, uygulamanın kuruluş verileri içermeyen bir değiştirilmiş bildirimi göstermesi gerekir. @No__t-0 ise, tüm bildirimlere izin verilir.

@No__t-0 çağrılmadığından, MAM SDK, tek kimlik uygulamaları için bildirimleri otomatik olarak kısıtlamak için en iyi çabayı yapar. Otomatik engelleme etkinse ve `BLOCK_ORG_DATA` ayarlanırsa, bildirim hiç gösterilmeyecektir. Daha ayrıntılı denetim için `getNotificationRestriction` değerini denetleyin ve uygulama bildirimlerini uygun şekilde değiştirin.

## <a name="register-for-notifications-from-the-sdk"></a>SDK 'dan gelen bildirimlere kaydolma

### <a name="overview"></a>Genel Bakış
Intune uygulama SDK 'Sı, uygulamanızın, BT Yöneticisi tarafından dağıtıldığında seçmeli silme gibi bazı ilkelerin davranışını denetlemesine olanak tanır. BT Yöneticisi böyle bir ilke dağıttığında, Intune hizmeti SDK 'ya bir bildirim gönderir.

Uygulamanız `MAMNotificationReceiver` oluşturarak ve `MAMNotificationReceiverRegistry` ile kaydederek SDK 'dan gelen bildirimlere kaydolmalıdır. Bu, aşağıdaki örnekte gösterildiği gibi alıcı ve `App.onCreate` ' da istenen bildirim türü sağlanarak yapılır:

```java
@Override
public void onCreate() {
  super.onCreate();
  MAMComponents.get(MAMNotificationReceiverRegistry.class)
    .registerReceiver(
      new ToastNotificationReceiver(),
      MAMNotificationType.WIPE_USER_DATA);
  }
```

### <a name="mamnotificationreceiver"></a>MAMNotificationReceiver

@No__t-0 arabirimi yalnızca Intune hizmetinden gelen bildirimleri alır. Bazı bildirimler doğrudan SDK tarafından işlenir, diğerleri ise uygulamanın katılımını gerektirir. Bir uygulamanın bir bildirimden true veya false döndürmesi **gerekir** . Bildirimin sonucu olarak denenmeye çalıştık bir eylem başarısız olmadığı sürece her zaman true döndürmelidir.

* Bu hata Intune hizmetine bildirilebilir. BT Yöneticisi bir silme işlemi başlattıktan sonra uygulamanın kullanıcı verilerini temizlememe hakkında rapor almak için bir senaryo örneği.

>[!NOTE]
> @No__t-0 ' da, geri çağırma işlemi kullanıcı arabirimi iş parçacığında çalışmadığından güvenli hale gelir.

SDK 'da tanımlanan `MAMNotificationReceiver` arabirimi aşağıda verilmiştir:

```java
/**
 * The SDK is signaling that a MAM event has occurred.
 *
 */
public interface MAMNotificationReceiver {

    /**
     * A notification was received.
     *
     * @param notification
     *            The notification that was received.
     * @return The receiver should return true if it handled the
     *   notification without error (or if it decided to ignore the
     *   notification). If the receiver tried to take some action in
     *   response to the notification but failed to complete that
     *   action it should return false.
     */
    boolean onReceive(MAMNotification notification);
}
```

### <a name="types-of-notifications"></a>Bildirim türleri

Aşağıdaki bildirimler uygulamaya gönderilir ve bazıları uygulama katılımı gerektirebilir:

* **WIPE_USER_DATA**: Bu bildirim bir `MAMUserNotification` sınıfında gönderilir. Bu bildirim alındığında, uygulamanın yönetilen kimlikle ilişkili tüm verileri (`MAMUserNotification.getUserIdentity()` ' den) silmesi *gerekir* . Bildirim, uygulamanız `unregisterAccountForMAM` ' ı çağırdığında, bir BT Yöneticisi bir silme işlemi başlattığında ya da yönetici tarafından gerekli koşullu erişim ilkeleri karşılanmadığı zaman da dahil olmak üzere çeşitli nedenlerle meydana gelebilir. Uygulamanız bu bildirime kaydolmaz, varsayılan silme davranışı gerçekleştirilir. Varsayılan davranış tek kimlikli bir uygulama için tüm dosyaları veya çok kimlikli bir uygulama için yönetilen kimlikle etiketlenmiş tüm dosyaları siler. Bu bildirim, Kullanıcı arabirimi iş parçacığı üzerinde hiçbir şekilde gönderilmeyecektir.

* **WIPE_USER_AUXILIARY_DATA**: uygulamalar Intune uygulama SDK 'sının varsayılan seçmeli silme davranışını gerçekleştirmesini ve yine de Temizleme gerçekleştiğinde bazı yardımcı verilerin kaldırılmasını istiyorsanız bu bildirime kaydolanırlar. Bu bildirim tek kimlik uygulamaları için kullanılamaz; yalnızca çoklu kimlik uygulamalarına gönderilir. Bu bildirim, Kullanıcı arabirimi iş parçacığı üzerinde hiçbir şekilde gönderilmeyecektir.

* **REFRESH_POLICY**: Bu bildirim bir `MAMUserNotification` ' de gönderilir. Bu bildirim alındığında, uygulamanız tarafından önbelleğe alınan tüm Intune ilkesi kararları geçersiz kılınmalıdır ve güncelleştirilir. Uygulamanız herhangi bir ilke varsayımsını depolamaz bu bildirime kaydolmamalıdır. Bu bildirimin gönderileceği iş parçacığı olarak hiçbir garanti yapılmaz.

* **REFRESH_APP_CONFIG**: Bu bildirim bir `MAMUserNotification` ' de gönderilir. Bu bildirim alındığında, önbelleğe alınan tüm uygulama yapılandırma verileri geçersiz kılınmalıdır ve güncelleştirilir. Bu bildirimin gönderileceği iş parçacığı olarak hiçbir garanti yapılmaz.

* **MANAGEMENT_REMOVED**: Bu bildirim bir `MAMUserNotification` ile gönderilir ve uygulamayı yönetilmeyen hale gelecek şekilde bildirir. Yönetilmeden sonra şifreli dosyaları okuyamayacak, MAMDataProtectionManager ile şifrelenen verileri okuyamayacak, şifrelenmiş Pano ile etkileşime giremeyecek veya yönetilen-App ekosistemine katılamayacak. Daha ayrıntılı bilgi için aşağıdaki ayrıntılara bakın. Bu bildirim, Kullanıcı arabirimi iş parçacığı üzerinde hiçbir şekilde gönderilmeyecektir.

* **MAM_ENROLLMENT_RESULT**: Bu bildirim, uygulamayı bir App-we kayıt denemesinin tamamlandığını bilgilendirmek ve bu girişimin durumunu sağlamak için bir `MAMEnrollmentNotification` ile gönderilir. Bu bildirimin gönderileceği iş parçacığı olarak hiçbir garanti yapılmaz.

* **COMPLIANCE_STATUS**: Bu bildirim bir `MAMComplianceNotification` ' de bir uyumluluk düzeltme denemesinin sonucunu bilgilendirmek için gönderilir. Bu bildirimin gönderileceği iş parçacığı olarak hiçbir garanti yapılmaz.

> [!NOTE]
> Bir uygulama asla `WIPE_USER_DATA` ve `WIPE_USER_AUXILIARY_DATA` bildirimlerine kaydolmamalıdır.

### <a name="management_removed"></a>MANAGEMENT_REMOVED

@No__t-0 bildirimi, daha önce ilkeyle yönetilen bir kullanıcının artık Intune MAM ilkesi tarafından yönetilmeyeceğini gösterir. Bu, Kullanıcı verilerini silme veya Kullanıcı oturumu kapatma gerektirmez (bir temizleme gerekliyse `WIPE_USER_DATA` bildirimi gönderilir). Birçok uygulamanın bu bildirimi hiç işlemesi gerekmez, ancak `MAMDataProtectionManager` kullanan uygulamalar [Bu bildirimin özel not](#data-protection)almalıdır.

MAM, uygulamanın `MANAGEMENT_REMOVED` alıcıyı çağırdığında aşağıdakiler doğru olacaktır:
* MAM, uygulamaya ait olan önceden şifrelenmiş dosyaların (ancak korunmayan veri arabelleklerinin) şifresini zaten çözüldü. Sdcard üzerinde, doğrudan uygulamaya ait olmayan (örn. belgeler veya Indirme klasörleri) ortak konumlardaki dosyalar şifresi çözülür.
* Alıcı yöntemi tarafından oluşturulan yeni dosyalar veya korumalı veri arabellekleri (ya da alıcı başladıktan sonra çalışan başka bir kod) şifrelenmeyecektir.
* Uygulamanın hala şifreleme anahtarlarına erişimi vardır. bu nedenle, şifre çözme veri arabellekleri gibi işlemler başarılı olur.

Uygulamanızın alıcısı döndüğünde, artık şifreleme anahtarlarına erişemez.

## <a name="configure-azure-active-directory-authentication-library-adal"></a>Azure Active Directory kimlik doğrulama kitaplığı 'nı (ADAL) yapılandırma

İlk olarak lütfen [GitHub 'Da adal deposunda](https://github.com/AzureAD/azure-activedirectory-library-for-android)bulunan adal tümleştirme kılavuzunu okuyun.

SDK, [kimlik doğrulama](https://azure.microsoft.com/documentation/articles/active-directory-authentication-scenarios/) ve koşullu başlatma senaryoları için, uygulamaların [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/)ile yapılandırılmasını gerektiren [adal](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/) kullanır. Yapılandırma değerleri, AndroidManifest meta verileri üzerinden SDK 'ya iletilir.

Uygulamanızı yapılandırmak ve uygun kimlik doğrulamasını etkinleştirmek için, AndroidManifest. xml ' deki uygulama düğümüne aşağıdakileri ekleyin. Bu yapılandırmalardan bazıları, yalnızca uygulamanız genel olarak kimlik doğrulaması için ADAL kullanıyorsa gereklidir; Bu durumda, uygulamanızın kendisini AAD 'ye kaydetmek için kullandığı belirli değerlere ihtiyaç duyarsınız. Bu işlem, AAD 'nin iki ayrı kayıt değerini (biri uygulamadan, diğeri SDK 'dan) tanımasını nedeniyle son kullanıcıdan kimlik doğrulamasının iki kez istenmemesini sağlamak için yapılır.

```xml
<meta-data
    android:name="com.microsoft.intune.mam.aad.Authority"
    android:value="https://AAD authority/" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.ClientID"
    android:value="your-client-ID-GUID" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.NonBrokerRedirectURI"
    android:value="your-redirect-URI" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.SkipBroker"
    android:value="[true | false]" />
```

### <a name="adal-metadata"></a>ADAL meta verileri

* **Yetkili** , kullanımdaki AAD yetkilisindir. Bu değer yoksa AAD genel ortamı kullanılır.
    > [!NOTE]
    > Uygulamanız sogeign bulutu kullanıyorsa bu alanı ayarlamayın.

* **ClientID** , kullanılacak AAD ClientID 'Dir (uygulama kimliği olarak da bilinir). Azure AD 'ye kaydolduysanız veya ADAL tümleştirmemişse [varsayılan kayıttan](#default-enrollment-optional) yararlanmak için kendi uygulamanızın ClientID kullanmanız gerekir.

* **Nonbrokerredirecturi** , yalnızca aracısız durumlarda kullanılacak AAD yeniden yönlendirme URI 'sidir. Hiçbiri belirtilmemişse, varsayılan `urn:ietf:wg:oauth:2.0:oob` değeri kullanılır. Bu varsayılan değer çoğu uygulama için uygundur.

  * NonBrokerRedirectURI yalnızca SkipBroker "true" olduğunda kullanılır.

* **Skipbroker** varsayılan adal SSO katılım davranışını geçersiz kılmak için kullanılır. SkipBroker yalnızca bir ClientID belirten **ve** aracılı kimlik doğrulaması/CIHAZ genelinde SSO 'yu desteklemeyen uygulamalar için belirtilmelidir. Bu durumda, "true" olarak ayarlanmalıdır. Çoğu uygulama SkipBroker parametresini ayarlanmamalıdır.

  * Bir SkipBroker değeri belirtmek için bildirimde bir **ClientID belirtilmelidir** .

  * Bir ClientID belirtildiğinde, varsayılan değer "false" dır.

  * SkipBroker "true" olduğunda, NonBrokerRedirectURI kullanılacaktır. ADAL (ve bu nedenle ClientID) tümleştirmesiz uygulamalar, varsayılan olarak "true" olarak değişir.

### <a name="common-adal-configurations"></a>Ortak ADAL yapılandırması

Aşağıda, bir uygulamanın ADAL ile yapılandırılabilmenin yaygın yolları verilmiştir. Uygulamanızın yapılandırmasını bulun ve ADAL meta veri parametrelerini (yukarıda açıklanmıştır) gerekli değerlere ayarladığınızdan emin olun. Her durumda, varsayılan olmayan ortamlar için isteniyorsa, yetkili belirlenebilir. Belirtilmemişse, genel üretim AAD yetkilisi kullanılacaktır.

#### <a name="1-app-does-not-integrate-adal"></a>1. uygulama ADAL 'yi tümleştirmez
ADAL meta **verileri bildirimde bulunmamalıdır.**

#### <a name="2-app-integrates-adal"></a>2. uygulama ADAL ile tümleşir

|Gerekli ADAL parametresi| Değer |
|--|--|
| ClientID | Uygulamanın ClientID 'si (uygulama kaydedildiğinde Azure AD tarafından oluşturulan) |

Gerekirse yetkili belirtilebilir.

Uygulamanızı Azure AD 'ye kaydetmeniz ve uygulamanıza uygulama koruma ilkesi hizmeti erişimi sağlamanız gerekir:
* Bir uygulamayı Azure AD 'ye kaydetme hakkında bilgi için [buraya](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications) bakın.
* Android uygulama izinlerinizi uygulama koruma ilkesi (APP) hizmetine verme adımlarının izlendiğinden emin olun. "Uygulamanızın Intune uygulama koruma hizmeti 'ne erişmesine izin verin (isteğe bağlı)" altındaki [Intune SDK 'sını](https://docs.microsoft.com/intune/app-sdk-get-started#next-steps-after-integration) kullanmaya başlama yönergelerini kullanın. 

Ayrıca [koşullu erişim](#conditional-access) için gereksinimlere bakın.


#### <a name="3-app-integrates-adal-but-does-not-support-brokered-authenticationdevice-wide-sso"></a>3. uygulama ADAL ile tümleşir, ancak aracılı kimlik doğrulaması/cihaz genelinde SSO 'yu desteklemez

|Gerekli ADAL parametresi| Değer |
|--|--|
| ClientID | Uygulamanın ClientID 'si (uygulama kaydedildiğinde Azure AD tarafından oluşturulan) |
| Skipbroker ayarlanmalıdır | **Değeri** |

Gerekliyse, Authority ve NonBrokerRedirectURI belirtilebilir.

### <a name="conditional-access"></a>Koşullu Erişim
Koşullu erişim (CA), AAD kaynaklarına erişimi denetlemek için kullanılabilen bir Azure Active Directory [özelliğidir](https://docs.microsoft.com/azure/active-directory/develop/active-directory-conditional-access-developer) . Intune yöneticileri, yalnızca Intune tarafından yönetilen cihazlardan veya uygulamalardan kaynak erişimine izin veren [CA kuralları tanımlayabilir](https://docs.microsoft.com/intune/conditional-access) . Uygulamanızın uygun olduğunda kaynaklara erişebildiğinden emin olmak için aşağıdaki adımları izlemeniz gerekir. Uygulamanız herhangi bir AAD erişim belirteci alamaz veya yalnızca CA korumalı olmayan kaynaklara erişirse, bu adımları atlayabilirsiniz.

1. [Adal tümleştirme kılavuzunu](https://github.com/AzureAD/azure-activedirectory-library-for-android#how-to-use-this-library)izleyin. 
   Bkz. aracı kullanımı için özellikle adım 11.
2. [Uygulamanızı Azure Active Directory kaydedin](https://docs.microsoft.com/azure/active-directory/active-directory-app-registration). 
   Yeniden yönlendirme URI 'SI, yukarıdaki ADAL tümleştirme kılavuzlarından bulunabilir.
3. Yukarıdaki [ortak adal yapılandırması](#common-adal-configurations), öğe 2 için bildirim meta veri parametrelerini ayarlayın.
4. [Azure Portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExchangeConnectorMenu/aad/connectorType/2) [cihaz tabanlı CA 'yı](https://docs.microsoft.com/intune/conditional-access-intune-common-ways-use) etkinleştirerek her şeyin düzgün yapılandırıldığını test edin ve
    - Uygulamanızda oturum açma, Intune Şirket Portalı yüklenmesini ve kaydını sorar
    - Kayıt sonrasında uygulamanızdaki oturum açma işlemi başarıyla tamamlanır.
5. Uygulamanız Intune uygulama SDK 'Sı tümleştirmesini gönderdikten sonra, [uygulama tabanlı koşullu erişim](https://docs.microsoft.com/intune/conditional-access-intune-common-ways-use#app-based-conditional-access) için onaylanan uygulamalar listesine eklenecek msintuneappsdk@microsoft.com ile iletişim kurun
6. Uygulamanız onaylanan listeye eklendikten sonra, [uygulama tabanlı CA 'Yı yapılandırarak](https://docs.microsoft.com/intune/app-based-conditional-access-intune-create) ve uygulamanızdaki oturum açma işlemini başarıyla tamamladığından emin olarak doğrulayın.

## <a name="app-protection-policy-without-device-enrollment"></a>Cihaz kaydı olmadan uygulama koruma ilkesi

### <a name="overview"></a>Genel Bakış
Cihaz kaydı olmadan Intune uygulama koruma ilkesi (APP-WE veya MAM-WE olarak da bilinir), uygulamaların Intune MDM 'ye kaydedilmesinin gerekli olması gerekmeden Intune tarafından yönetilmesini sağlar. Uygulama-cihaz kaydı ile veya olmadan birlikte ÇALıŞıYORUZ. Şirket Portalı cihaza hala yüklenmesi gerekir, ancak kullanıcının Şirket Portalı oturum açması ve cihazı kaydetmesi gerekmez.

> [!NOTE]
> Tüm uygulamalar, cihaz kaydı olmadan uygulama koruma ilkesini desteklemek için gereklidir.

### <a name="workflow"></a>İş Akışı

Bir uygulama yeni bir kullanıcı hesabı oluşturduğunda, hesabı Intune uygulama SDK 'Sı ile yönetimi için kaydetmeniz gerekir. SDK, uygulamayı APP-WE hizmetine kaydetme ayrıntılarını işleyeceğiz; gerekirse, bir başarısızlık meydana oluşursa ilgili zaman aralıklarında kayıtları yeniden dener.

Uygulama, kullanıcının şirket içeriğine erişimi engellenip engellenmediğini tespit etmek üzere kayıtlı bir kullanıcının durumu için Intune uygulama SDK 'sını de sorgulayabilir. Yönetim için birden çok hesap kaydedilebilir, ancak şu anda yalnızca bir hesap APP-WE hizmetiyle aynı anda kaydedilebilir. Bu, aynı anda yalnızca bir hesabın uygulama koruma ilkesini alabileceği anlamına gelir.

Uygulamanın, SDK adına Azure Active Directory kimlik doğrulama kitaplığından (ADAL) uygun erişim belirtecini almak için bir geri çağırma sağlaması gerekir. Uygulamanın zaten Kullanıcı kimlik doğrulaması için ADAL kullandığı ve kendi erişim belirteçlerini elde eden varsayılır.

Uygulama bir hesabı tamamen kaldırdığında, uygulamanın bu kullanıcı için artık ilke uygulamadığını belirtmek üzere bu hesabın kaydını kaldırmalıdır. Kullanıcı MAM hizmetine kaydedildiyse, Kullanıcı kaydı silinir ve uygulama temizlenir.

### <a name="overview-of-app-requirements"></a>Uygulama gereksinimlerine genel bakış

APP-WE tümleştirmesi uygulamak için, uygulamanızın kullanıcı hesabını MAM SDK ile kaydetmesi gerekir:

1. Uygulamanın `MAMServiceAuthenticationCallback` arabiriminin bir örneğini uygulaması ve kaydetmesi _gerekir_ . Geri çağırma örneği, uygulamanın yaşam döngüsünde mümkün olduğunca erken kaydedilmelidir (genellikle uygulama sınıfının `onMAMCreate()` yönteminde).

2. Bir kullanıcı hesabı oluşturulduğunda ve Kullanıcı ADAL ile başarıyla oturum açtığında, uygulamanın `registerAccountForMAM()` ' i çağırması _gerekir_ .

3. Bir kullanıcı hesabı kaldırıldığında, hesabı Intune yönetiminden kaldırmak için uygulama `unregisterAccountForMAM()` ' ı çağırmalıdır.

    > [!NOTE]
    > Kullanıcı uygulamanın oturumunu geçici olarak kapattığında, uygulamanın `unregisterAccountForMAM()` ' ı çağırması gerekmez. Çağrı, kullanıcının şirket verilerini tamamen kaldırmak için bir silme işlemi başlatabilir.


### <a name="mamenrollmentmanager"></a>MAMEnrollmentManager
Tüm gerekli kimlik doğrulama ve kayıt API 'Leri `MAMEnrollmentManager` arabiriminde bulunabilir. @No__t-0 ' A bir başvuru, aşağıdaki gibi edinilebilir:

```java
MAMEnrollmentManager mgr = MAMComponents.get(MAMEnrollmentManager.class);

// make use of mgr
```

Döndürülen @no__t 0 örneğinin null olmaması garanti edilir. API yöntemleri iki kategoriye ayrılır: **kimlik doğrulama** ve **hesap kaydı**.

```java
package com.microsoft.intune.mam.policy;

public interface MAMEnrollmentManager {
    public enum Result {
        AUTHORIZATION_NEEDED,
        NOT_LICENSED,
        ENROLLMENT_SUCCEEDED,
        ENROLLMENT_FAILED,
        WRONG_USER,
        MDM_ENROLLED,
        UNENROLLMENT_SUCCEEDED,
        UNENROLLMENT_FAILED,
        PENDING,
        COMPANY_PORTAL_REQUIRED;
    }

    //Authentication methods
    interface MAMServiceAuthenticationCallback {
        String acquireToken(String upn, String aadId, String resourceId);
    }
    void registerAuthenticationCallback(MAMServiceAuthenticationCallback callback);
    void updateToken(String upn, String aadId, String resourceId, String token);

    //Registration methods
    void registerAccountForMAM(String upn, String aadId, String tenantId);
    void registerAccountForMAM(String upn, String aadId, String tenantId, String authority);
    void unregisterAccountForMAM(String upn);
    Result getRegisteredAccountStatus(String upn);
}
```

### <a name="account-authentication"></a>Hesap kimlik doğrulaması
Bu bölümde `MAMEnrollmentManager` ' daki kimlik doğrulama API 'SI yöntemleri ve bunların nasıl kullanılacağı açıklanmaktadır.

```java
interface MAMServiceAuthenticationCallback {
        String acquireToken(String upn, String aadId, String resourceId);
}
void registerAuthenticationCallback(MAMServiceAuthenticationCallback callback);
void updateToken(String upn, String aadId, String resourceId, String token);
```

1. Uygulamanın, SDK 'nın verilen kullanıcı ve kaynak KIMLIĞI için bir ADAL belirteci istemesine izin vermek üzere `MAMServiceAuthenticationCallback` arabirimini uygulaması gerekir. @No__t-1 yöntemi çağırarak, geri çağırma örneği `MAMEnrollmentManager` ' a sağlanmalıdır. Kayıt yeniden denemeleri veya uygulama koruma ilkesi yenileme iadelerinin uygulama yaşam döngüsünün başlarında bir belirteç gerekebilir. bu nedenle, geri aramayı kaydetmek için ideal yer, uygulamanın `MAMApplication` alt sınıfının `onMAMCreate()` yöntemidir.

2. @No__t-0 yöntemi, belirtilen kullanıcı için istenen kaynak KIMLIĞI için erişim belirtecini almalıdır. İstenen belirteci elde ediyorsanız, null döndürmelidir.

    > [!NOTE]
    > Uygulamanızın, doğru belirtecin elde edebilmesi için `resourceId` ve `aadId` parametrelerini `acquireToken()` ' ye geçirdiğinden emin olun.

    ```java
    class MAMAuthCallback implements MAMServiceAuthenticationCallback {
        public String acquireToken(String upn, String aadId, String resourceId) {
            return mAuthContext.acquireTokenSilentSync(resourceId, ClientID, aadId).getAccessToken();
        }
    }
    ```

3. Uygulama, SDK `acquireToken()` ' ı çağırdığında bir belirteç sağlayamazsa, örneğin, sessiz kimlik doğrulaması başarısız olursa ve Kullanıcı arabirimi göstermek için uygun bir zaman ise, uygulama daha sonra `updateToken()` metodunu çağırarak bir belirteç sağlayabilir. @No__t-0 ' a ait önceki çağrı tarafından istenen UPN, AAD KIMLIĞI ve kaynak KIMLIĞI, sonunda elde edilen belirteçle birlikte `updateToken()` ' e geçirilmelidir. Uygulama, belirtilen geri aramadan null döndürdükten sonra bu yöntemi mümkün olan en kısa sürede çağırmalıdır.

    > [!NOTE]
    > SDK, belirteci almak için `acquireToken()` ' ı çağırır, bu nedenle `updateToken()` ' i çağırmak kesinlikle gerekli değildir. Ancak, kayıtların ve uygulama koruma ilkesi iadelerinin zamanında tamamlanmasını sağlamak için kesinlikle önerilir.


### <a name="account-registration"></a>Hesap kaydı
Bu bölümde `MAMEnrollmentManager` ' daki hesap kayıt API 'SI yöntemleri ve bunların nasıl kullanılacağı açıklanmaktadır.

```java
void registerAccountForMAM(String upn, String aadId, String tenantId);
void registerAccountForMAM(String upn, String aadId, String tenantId, String authority);
void unregisterAccountForMAM(String upn);
Result getRegisteredAccountStatus(String upn);
```

1. Bir hesabı yönetim için kaydetmek için, uygulama `registerAccountForMAM()` ' ı çağırmalıdır. Bir kullanıcı hesabı hem UPN 'si hem de AAD Kullanıcı KIMLIĞI tarafından tanımlanır. Kiracı KIMLIĞI, kayıt verilerini kullanıcının AAD kiracısı ile ilişkilendirmek için de gereklidir. Kullanıcının yetkisi, belirli bir bağımsız bulutlara karşı kayda izin vermek için de sağlanmış olabilir; daha fazla bilgi için bkz. [Sovereign bulutu kaydı](#sovereign-cloud-registration).  SDK, uygulamayı MAM hizmetinde verilen kullanıcı için kaydetmeyi deneyebilir; kayıt başarısız olursa, hesap kaydı silinene kadar düzenli aralıklarla kaydı yeniden dener. Yeniden deneme süresi genellikle 12-24 saat olur. SDK, bildirimler aracılığıyla zaman uyumsuz olarak kayıt denemelerinin durumunu sağlar.

2. AAD kimlik doğrulaması gerektiğinden Kullanıcı hesabını kaydetmek için en iyi zaman, Kullanıcı uygulamada oturum açtıktan ve ADAL kullanılarak başarıyla doğrulanır. Kullanıcının AAD KIMLIĞI ve kiracı KIMLIĞI, [`AuthenticationResult`](https://github.com/AzureAD/azure-activedirectory-library-for-android) nesnesinin bir PARÇASı olarak adal kimlik doğrulama çağrısından döndürülür.
    * Kiracı KIMLIĞI `AuthenticationResult.getTenantID()` yönteminden gelir.
    * Kullanıcı hakkındaki bilgiler, `AuthenticationResult.getUserInfo()` ' den gelen `UserInfo` türünde bir alt nesnede bulunur ve AAD Kullanıcı KIMLIĞI `UserInfo.getUserId()` çağırarak bu nesneden alınır.

3. Bir hesabın Intune yönetiminden kaydını silmek için uygulama `unregisterAccountForMAM()` ' ı çağırmalıdır. Hesap başarıyla kaydedildiyse ve yönetiliyorsa, SDK hesabın kaydını kaldırır ve verilerini temizler. Hesap için düzenli kayıt yeniden denemeleri durdurulacak. SDK, bildirim aracılığıyla kayıt kaldırma isteğinin durumunu zaman uyumsuz olarak sağlar.

### <a name="sovereign-cloud-registration"></a>Sovereign bulutu kaydı
Bağımsız [bulut kullanan](https://www.microsoft.com/trustcenter/cloudservices/nationalcloud) uygulamalar, `authority` ' ye `registerAccountForMAM()` ' **i sağlamalıdır.**  Bu, ADAL 'in [1.14.0 +](https://github.com/AzureAD/azure-activedirectory-library-for-android/releases/tag/v1.14.0) acquiretoken extraQueryParameters ' de `instance_aware=true` sağlayarak ve Authenticationcallback authenticationresult üzerinde `getAuthority()` ' i çağırarak elde edilebilir.

```java
mAuthContext.acquireToken(this, RESOURCE_ID, CLIENT_ID, REDIRECT_URI, PromptBehavior.FORCE_PROMPT, "instance_aware=true",
        new AuthenticationCallback<AuthenticationResult>() {
            @Override
            public void onError(final Exception exc) {
                // authentication failed
            }

            @Override
            public void onSuccess(final AuthenticationResult result) {
                mAuthority = result.getAuthority();
                // handle other parts of the result
            }
        });
```

> [!NOTE]
> AndroidManifest. xml içinde `com.microsoft.intune.mam.aad.Authority` meta veri öğesini ayarlamayın.

> [!NOTE]
> @No__t-0 yönteminizin yetkinin doğru şekilde ayarlandığından emin olun.

#### <a name="currently-supported-sovereign-clouds"></a>Şu anda desteklenen bağımsız bulutlar

1. Azure ABD kamu bulutu

### <a name="important-implementation-notes"></a>Önemli uygulama notları

#### <a name="authentication"></a>Kimlik Doğrulaması
* Uygulama `registerAccountForMAM()` ' ı çağırdığında, daha sonra farklı bir iş parçacığında `MAMServiceAuthenticationCallback` arabirimine bir geri çağırma alabilir. İdeal olarak, uygulama, istenen belirtecin alımını hızlandırmak için hesabı kaydetmeden önce ADAL 'dan kendi belirtecini almış. Uygulama geri aramadan geçerli bir belirteç döndürürse, kayıt devam eder ve uygulama bir bildirim aracılığıyla nihai sonucu alır.

* Uygulama geçerli bir AAD belirteci döndürmezse, kayıt denemesinin nihai sonucu `AUTHENTICATION_NEEDED` olur. Uygulama bildirim yoluyla bu sonucu alırsa, kayıt işlemini başlatmak için `acquireToken()` ' dan daha önce istenmiş olan ve `updateToken()` yöntemini çağırarak kayıt işlemini hızlandırmak önemle önerilir deneyin.

* Uygulamanın kayıtlı `MAMServiceAuthenticationCallback`, düzenli uygulama koruma ilkesi yenileme iadelerinin bir belirtecini almak için de çağrılır. Uygulama istendiğinde bir belirteç sağlayamadığında bildirim almaz, ancak iade sürecini hızlandırmak için bir sonraki uygun zamanda `updateToken()` ' i çağırıp bir belirteci almayı ve çağırmayı denemelidir. Bir belirteç sağlanmazsa, geri çağırma işlemi bir sonraki iade girişiminde yine de çağırılır.

* Sogeign bulutları için destek, yetkiyi sağlamayı gerektirir.

#### <a name="registration"></a>Kayıt
* Kolaylık olması için kayıt yöntemleri ıdempotent; Örneğin, `registerAccountForMAM()`yalnızca bir hesabı kaydeder ve hesap zaten kayıtlı değilse uygulamayı kaydetmeye çalışır @no__t ve şu anda kayıtlıysa yalnızca bir hesabın kaydını siler. Sonraki çağrılar Ops değildir, bu nedenle bu yöntemlerin birden çok kez çağrılmasının bir riski yoktur. Ayrıca, bu yöntemlere yapılan çağrılar ve sonuç bildirimleri arasındaki yazışmalar garanti edilmez: Yani, zaten kayıtlı olan bir kimlik için `registerAccountForMAM()` çağrılırsa, bildirim bu kimlik için yeniden gönderilmeyebilir. SDK düzenli aralıklarla kayıtları arka planda bir şekilde denediğinden ve Intune hizmetinden alınan silme istekleri tarafından tetiklenebilir olduğundan, bu yöntemlere yapılan çağrılara karşılık gelmediği için bildirimlerin gönderilmesi mümkündür.

* Kayıt yöntemleri herhangi bir sayıda farklı kimlik için çağrılabilir, ancak şu anda yalnızca bir kullanıcı hesabı başarıyla kaydedilebilir. Intune için lisanslanmış ve uygulama koruma ilkesi tarafından hedeflenen birden çok kullanıcı hesabı, aynı anda veya daha yakın bir zamanda kayıtlıysa, bu, ne kadar yarış kazanabileceğini garanti etmez.

* Son olarak, belirli bir hesabın kayıtlı olup olmadığını görmek ve `getRegisteredAccountStatus()` yöntemini kullanarak geçerli durumunu almak için `MAMEnrollmentManager` sorgulama yapabilirsiniz. Belirtilen hesap kayıtlı değilse, bu yöntem **null**döndürür. Hesap kaydedilmişse, bu yöntem `MAMEnrollmentManager.Result` sabit listesinin üyelerinden biri olarak hesabın durumunu döndürür.

### <a name="result-and-status-codes"></a>Sonuç ve durum kodları
Bir hesap ilk kez kaydedildiğinde, ilk MAM hizmeti kayıt denemesinin tamamlanmamış olduğunu belirten `PENDING` durumunda başlar. Kayıt denemesi tamamlandıktan sonra, aşağıdaki tabloda yer alacak sonuç kodlarından biriyle bir bildirim gönderilir. Ayrıca, `getRegisteredAccountStatus()` yöntemi hesabın durumunu döndürür, böylece uygulama her zaman şirket içeriğine erişimin bu kullanıcı için engellenip engellenmediğini tespit edebilir. Kayıt girişimi başarısız olursa, SDK 'nın arka planda yeniden denemesi yaparken hesabın durumu zaman içinde değişebilir.

|Sonuç kodu | Açıklama |
| -- | -- |
| `AUTHORIZATION_NEEDED` | Bu sonuç, bir belirtecin uygulamanın kayıtlı `MAMServiceAuthenticationCallback` örneği tarafından sağlandığını veya belirtilen belirtecin geçersiz olduğunu gösterir.  Uygulamanın geçerli bir belirteç edinmesi ve mümkünse `updateToken()` çağrısı gerekir. |
| `NOT_LICENSED` | Kullanıcı Intune lisansına sahip değil veya Intune MAM hizmetiyle iletişim kurma girişimi başarısız oldu.  Uygulama, yönetilmeyen (normal) bir durumda devam etmelidir ve Kullanıcı engellenmemelidir.  Kullanıcının gelecekte lisanslanması durumunda kayıtlar düzenli aralıklarla yeniden denenir. |
| `ENROLLMENT_SUCCEEDED` | Kayıt girişimi başarılı oldu veya Kullanıcı zaten kayıtlı.  Başarılı bir kayıt söz konusu olduğunda, bu bildirimden önce bir ilke yenileme bildirimi gönderilir.  Kurumsal verilere erişime izin verilmelidir. |
| `ENROLLMENT_FAILED` | Kayıt girişimi başarısız oldu.  Daha fazla ayrıntı cihaz günlüklerinde bulunabilir.  Daha önce kullanıcının Intune için lisanslı olduğunu belirlediğinden, uygulamanın bu durumda kurumsal verilere erişim izni olmaması gerekir.|
| `WRONG_USER` | Cihaz başına yalnızca bir Kullanıcı, MAM hizmeti ile bir uygulamayı kaydedebilir. Bu sonuç, bu sonucun teslim edildiği kullanıcının (ikinci Kullanıcı) MAM ilkesi ile hedeflendiğini, ancak farklı bir kullanıcının zaten kayıtlı olduğunu gösterir. İkinci Kullanıcı için MAM ilkesi zorlanamadığından, bu kullanıcı için kayıt kaydı daha sonra başarılı olmadığı sürece uygulamanız bu kullanıcının verilerine erişime izin vermelidir (muhtemelen Kullanıcı uygulamanızdan kaldırılır). Bu @no__t teslimi ile eş zamanlı olarak, MAM var olan hesabı kaldırma seçeneğiyle istemde olacaktır. İnsan kullanıcısı bir süre içinde yanıt verdiği zaman, ikinci kullanıcıyı kısa bir süre sonra kaydetmek mümkün olacaktır. İkinci Kullanıcı kayıtlı kaldığı sürece, MAM kaydı düzenli aralıklarla yeniden dener. |
| `UNENROLLMENT_SUCCEEDED` | Kayıt başarıyla geri alındı.|
| `UNENROLLMENT_FAILED` | Kayıt kaldırma isteği başarısız oldu.  Daha fazla ayrıntı cihaz günlüklerinde bulunabilir. Genel olarak, uygulama geçerli bir (null ya da boş) UPN 'yi geçirmiş olduğu sürece bu durum oluşmaz. Uygulamanın gidebilmesine yönelik doğrudan, güvenilir bir düzeltme yoktur. Bu değer geçerli bir UPN kaydı silinirken alınmışsa, lütfen Intune MAM ekibine hata olarak bildirin.|
| `PENDING` | Kullanıcı için ilk kayıt denemesi devam ediyor.  Uygulama, kayıt sonucu bilinene kadar kurumsal verilere erişimi engelleyebilir, ancak bunu yapmak için gerekli değildir. |
| `COMPANY_PORTAL_REQUIRED` | Kullanıcı Intune için lisanslanır, ancak Şirket Portalı uygulama cihaza yükleninceye kadar uygulama kaydedilemez. Intune uygulama SDK 'Sı, belirtilen kullanıcı için uygulamaya erişimi engellemeye çalışır ve bu uygulamaları Şirket Portalı uygulamayı yüklemeye yönlendirir (Ayrıntılar için aşağıya bakın). |


### <a name="company-portal-requirement-prompt-override-optional"></a>Şirket Portalı gereksinim istemi geçersiz kıl (isteğe bağlı)
@No__t-0 sonucu alınmışsa, SDK, kayıt istenmiş olan kimliği kullanan etkinliklerin kullanımını engeller. Bunun yerine, SDK bu etkinliklerin Şirket Portalı indirmek için bir istem görüntülemesine neden olur. Uygulamanızda bu davranışı engellemek isterseniz, etkinlikler `MAMActivity.onMAMCompanyPortalRequired` uygulayabilir.

Bu yöntem, SDK varsayılan engelleme Kullanıcı arabirimini görüntülemeden önce çağrılır. Uygulama, etkinlik kimliğini değiştiriyor veya kaydetmeyi deneyen kullanıcının kaydını siler, SDK etkinliği engellemez. Bu durumda, kurumsal verilerin sızmasını önlemek için uygulamaya sahip olmanız gerekir. Yalnızca çoklu kimlik uygulamaları (daha sonra tartışılmış) etkinlik kimliğini değiştirebilecektir.

Açıkça `MAMActivity` ' ı (yapı aracı bu değişikliği yapar), ancak yine de bu bildirimi işlemesi gerekiyorsa, `MAMActivityBlockingListener` ' i uygulayabilirsiniz.

### <a name="notifications"></a>Bildirimler
Uygulama, **MAM_ENROLLMENT_RESULT**türündeki bildirimlere kaydolduktan sonra, uygulamayı kayıt isteğinin tamamlandığını bilgilendirmek için `MAMEnrollmentNotification` gönderilir. @No__t-0, [SDK 'dan gelen bildirimlere kaydolma](#register-for-notifications-from-the-sdk) bölümünde açıklandığı gibi `MAMNotificationReceiver` arabirimi üzerinden alınır.

```java
public interface MAMEnrollmentNotification extends MAMUserNotification {
    MAMEnrollmentManager.Result getEnrollmentResult();
}
```

@No__t-0 yöntemi, kayıt isteğinin sonucunu döndürür.  @No__t-0 `MAMUserNotification` ' i genişlettiğinden, kaydın denendiği kullanıcının kimliği de kullanılabilir. Uygulamanın bu bildirimleri almak için `MAMNotificationReceiver` arabirimini uygulaması gerekir, bu da [SDK 'daki bildirimlere kaydolun](#register-for-notifications-from-the-sdk) bölümünde ayrıntılı olarak açıklanmıştır.

Kayıtlı Kullanıcı hesabının durumu bir kayıt bildirimi alındığında değişebilir, ancak her durumda değişmeyecektir (örneğin, `WRONG_USER` gibi daha bilgilendirici bir sonuçtan sonra `AUTHORIZATION_NEEDED` bildirimi alınmışsa, daha bilgilendirici sonuç olur hesabın durumu olarak tutulur).  Hesap başarıyla kaydedildikten sonra, hesap kaydedilmediği veya temizlenmeden önce durum `ENROLLMENT_SUCCEEDED` olarak kalır.

## <a name="app-ca-with-policy-assurance"></a>Ilke güvencesi olan uygulama CA 'sı

### <a name="overview"></a>Genel Bakış
Ilke güvencesi ile uygulama CA 'sı (koşullu erişim) ile, kaynaklara erişim Intune Uygulama Koruması Ilkelerinin uygulama üzerinde koşullanar.  AAD, Ilke güvencesi korumalı kaynağı ile bir uygulama CA 'sına bir belirteç vermeden önce uygulamanın uygulama tarafından kaydedilmesini ve yönetilmesini zorunlu kılarak bunu zorunlu kılar.  Uygulamanın, belirteç alımı için ADAL Aracısı 'nı kullanması gerekir ve kurulum yukarıda [koşullu erişim](#conditional-access)bölümünde açıklananla aynıdır.

### <a name="adal-changes"></a>ADAL değişiklikleri
ADAL kitaplığı, uygulamayı bir belirteç alma hatasının uygulama yönetimiyle uyumsuz olduğunu bildiren yeni bir hata koduna sahiptir.  Uygulama bu hata kodunu alırsa, uygulamayı kaydederek ve ilkeyi uygulayarak uyumluluğu düzeltmeye çalışmak için SDK 'Yı çağırmalıdır. ADAL `AuthenticationCallback` ' in `onError()` yöntemi tarafından bir özel durum alınır ve hata kodu `ADALError.AUTH_FAILED_INTUNE_POLICY_REQUIRED` olur.  Bu durumda, özel durum, uyumluluk düzeltme aşamasında kullanılmak üzere başka parametrelerin ayıklanabileceği bir `IntuneAppProtectionPolicyRequiredException` ' a dönüşebilir (Aşağıdaki kod örneğine bakın). Düzeltme başarılı olduktan sonra, uygulama ADAL üzerinden belirteç alımı yeniden deneyebilir.

> [!NOTE]
> Bu yeni hata kodu ve Ilke güvencesi içeren uygulama CA 'sı için diğer destek, ADAL kitaplığı 'nın sürüm 1.15.0 (veya üstü) gerektirir.

### <a name="mamcompliancemanager"></a>Mamkarmaşıancemanager
@No__t-0 arabirimi, ADAL 'dan ilke gerekli hatası alındığında kullanılır.  Uygulamayı uyumlu duruma koymaya çalışmak için çağrılması gereken `remediateCompliance()` yöntemini içerir. @No__t-0 ' A bir başvuru, aşağıdaki gibi edinilebilir:

```java
MAMComplianceManager mgr = MAMComponents.get(MAMComplianceManager.class);

// make use of mgr
```

Döndürülen @no__t 0 örneğinin null olmaması garanti edilir.

```java
package com.microsoft.intune.mam.policy;

public interface MAMComplianceManager {
    void remediateCompliance(String upn, String aadId, String tenantId, String authority, boolean showUX);
}
```

@No__t-0 yöntemi, AAD 'nin istenen belirteci vermesini sağlamak üzere uygulamayı yönetim altına koymaya çalışmak üzere çağırılır.  İlk dört parametre ADAL `AuthenticationCallback.onError()` yöntemi tarafından alınan özel durumdan ayıklanamaz (Aşağıdaki kod örneğine bakın).  Son parametre, uyumluluk girişimi sırasında bir UX gösterilip gösterilmeyeceğini denetleyen bir Boole değeri.  Bu işlem sırasında özelleştirilmiş UX gösterme gereksinimi olmayan uygulamalar için varsayılan olarak sunulan basit bir engelleme ilerleme stil arabirimidir.  Yalnızca uyumluluk düzeltmesi devam ederken engellenecek ve nihai sonucu göstermeyecektir.  Uygulama, uyumluluk düzeltme girişiminin başarısını veya başarısızlığını işlemek için bir bildirim alıcısı kaydetmelidir (aşağıya bakın).

@No__t-0 yöntemi, uyumluluk kurma kapsamında bir MAM kaydı gerektirebilir.  Uygulama, kayıt bildirimleri için bir bildirim alıcısı kaydettirirse bir kayıt bildirimi alabilir.  Uygulamanın kayıtlı `MAMServiceAuthenticationCallback`, MAM kaydı için bir belirteç almak üzere çağrılan `acquireToken()` yöntemine sahip olur. `acquireToken()`, uygulama kendi belirtecini elde etmeden önce çağrılır. bu nedenle, başarılı bir belirteç alımı sonrasında uygulamanın kullandığı tüm muhasebe veya hesap oluşturma görevleri henüz yapılmamış olabilir.  Geri çağırma bu durumda bir belirteç elde edebilmelidir.  @No__t-0 ' dan bir belirteç döndüremiyorum, uyumluluk düzeltme girişimi başarısız olur.  İstenen kaynak için geçerli bir belirteçle daha sonra `updateToken()` ' ı çağırırsanız, uyumluluk düzeltmesi verilen belirteçle hemen yeniden denenir.

> [!NOTE]
> Kullanıcı aracıyı yüklemek ve `ADALError.AUTH_FAILED_INTUNE_POLICY_REQUIRED` hatası alınmadan önce cihazı kaydetmek üzere zaten uygun olduğundan, sessiz belirteç alımı `acquireToken()` ' da mümkün olmaya devam edecektir.  Bu, aracıda, istenen belirtecin sessiz acqisition izin vermesini sağlamak için önbelleğinde geçerli bir yenileme belirteci olmasına neden olur.

@No__t-0 yönteminde ilke gerekli hatası alma ve hatayı işlemek için `MAMComplianceManager` çağırma örneği aşağıda verilmiştir.

```java
public void onError(@Nullable Exception exc) {
    if (exc instanceof AuthenticationException && 
        ((AuthenticationException) exc).getCode() == ADALError.AUTH_FAILED_INTUNE_POLICY_REQUIRED) {

        final IntuneAppProtectionPolicyRequiredException policyRequiredException = 
            (IntuneAppProtectionPolicyRequiredException) ex;

        final String upn = policyRequiredException.getAccountUpn();
        final String aadId = policyRequiredException.getAccountUserId();
        final String tenantId = policyRequiredException.getTenantId();
        final String authority = policyRequiredException.getAuthorityURL();

        MAMComplianceManager complianceManager = MAMComponents.get(MAMComplianceManager.class);
        complianceManager.remediateCompliance(upn, aadId, tenantId, authority, showUX);
    }
}
```

### <a name="status-notifications"></a>Durum bildirimleri
Uygulama, **COMPLIANCE_STATUS**türündeki bildirimlere kaydolduktan sonra, uygulamayı uyumluluk düzeltme denemesinin son durumuna bildirmek için bir `MAMComplianceNotification` gönderilir. @No__t-0, [SDK 'dan gelen bildirimlere kaydolma](#register-for-notifications-from-the-sdk) bölümünde açıklandığı gibi `MAMNotificationReceiver` arabirimi üzerinden alınır.

```java
public interface MAMComplianceNotification extends MAMUserNotification {
    MAMCAComplianceStatus getComplianceStatus();
    String getComplianceErrorTitle();
    String getComplianceErrorMessage();
}
```

@No__t-0 yöntemi, `MAMCAComplianceStatus` numaralandırmasından değer olarak uyumluluk düzeltme denemesinin sonucunu döndürür.

|Durum kodu | Açıklama |
| -- | -- |
| BILINMEYEN | Durum bilinmiyor. Bu, beklenmeyen bir hata nedenini gösterebilir. Şirket Portalı günlüklerinde ek bilgiler bulunabilir. |
| Uyumluluk | Uyumluluk düzeltmesi başarılı oldu ve uygulama artık ilkeyle uyumlu. ADAL belirteci alımı yeniden denenmelidir. |
| NOT_COMPLIANT | Uyumluluğun düzeltilmesi girişimi başarısız oldu.  Uygulama uyumlu değil ve ADAL belirteci alma, hata koşulu düzeltilene kadar yeniden denenmemelidir.  Ek hata bilgileri MAMComplianceNotification ile gönderilir. |
| SERVICE_FAILURE | Intune hizmetinden uyumluluk verileri alınmaya çalışılırken bir hata oluştu. Şirket Portalı günlüklerinde ek bilgiler bulunabilir. |
| NETWORK_FAILURE | Intune hizmetine bağlanılırken bir hata oluştu. Uygulama, ağ bağlantısı geri yüklendiğinde belirteç alımı ' nı yeniden denemelidir. |
| CLIENT_ERROR | İstemciyle ilgili bazı nedenlerle uyumluluğu düzeltme girişimi başarısız oldu.  Örneğin, belirteç yok veya yanlış Kullanıcı. Ek hata bilgileri MAMComplianceNotification ile gönderilir. |
| YAYıNLAN | Durum yanıtı, zaman sınırı aşıldığında hizmetten henüz alınmadığı için uyumluluğu düzeltme girişimi başarısız oldu. Uygulama, belirteç alımı daha sonra tekrar denemelidir. |
| COMPANY_PORTAL_REQUIRED | Uyumluluk düzeltmesinin başarılı olabilmesi için Şirket Portalı cihazda yüklü olmalıdır.  Şirket Portalı cihazda zaten yüklüyse, uygulamanın yeniden başlatılması gerekir.  Bu durumda, kullanıcıdan uygulamayı yeniden başlatmasını isteyen bir iletişim kutusu gösterilir. |

Uyumluluk durumu `MAMCAComplianceStatus.COMPLIANT` ise, uygulamanın özgün belirteç alımı (kendi kaynağı için) yeniden başlatması gerekir. Uyumluluk Düzeltme girişimi başarısız olursa, `getComplianceErrorTitle()` ve `getComplianceErrorMessage()` yöntemleri, uygulamanın seçtiği takdirde son kullanıcıya görüntüleyebilen yerelleştirilmiş dizeleri döndürür.  Çoğu hata durumu uygulama tarafından etkilenmez, bu nedenle genel durumda hesap oluşturma veya oturum açma işlemi başarısız olabilir ve kullanıcının daha sonra tekrar denemesini sağlayabilirsiniz.  Bir hata kalıcısa, MAM günlükleri sorunun belirlenmesine yardımcı olabilir.  Son Kullanıcı, [burada](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android "Şirketinizin destek alanına e-posta günlükleri")bulunan yönleri kullanarak günlükleri gönderebilir.

@No__t-0 `MAMUserNotification` ' i genişlettiğinden, düzeltmenin denendiği kullanıcının kimliği de kullanılabilir.

Bu, Mamnotificationahize arabirimini uygulamak için anonim sınıf kullanarak bir alıcıyı kaydetmenin bir örneğidir:

```java
final MAMNotificationReceiverRegistry notificationRegistry = MAMComponents.get(MAMNotificationReceiverRegistry.class);
// create a receiver
final MAMNotificationReceiver receiver = new MAMNotificationReceiver() {
    public boolean onReceive(MAMNotification notification) {
        if (notification.getType() == MAMNotificationType.COMPLIANCE_STATUS) {
            MAMComplianceNotification complianceNotification = (MAMComplianceNotification) notification;
            
            // take appropriate action based on complianceNotification.getComplianceStatus()
            
            // unregister this receiver if no longer needed
            notificationRegistry.unregisterReceiver(this, MAMNotificationType.COMPLIANCE_STATUS);
        }
        return true;
    }
};
// register the receiver
notificationRegistry.registerReceiver(receiver, MAMNotificationType.COMPLIANCE_STATUS);
```

> [!NOTE]
> Bildirimin kaçırılması ile sonuçlanmasına neden olabilecek bir yarış durumundan kaçınmak için `remediateCompliance()` çağrılmadan önce bildirim alıcısı kaydedilmelidir.

### <a name="implementation-notes"></a>Uygulama notları
> [!NOTE]
> **Önemli değişiklik!**  <br>
> Uygulamanın `MAMServiceAuthenticationCallback.acquireToken()` yöntemi, yeni @no__t 2 bayrağı `acquireTokenSilentSync()` ' e kadar *yanlış* geçmelidir.
> Daha önce, aracıdan belirteçleri yenileme ile ilgili bir sorunu gidermek için *doğru* geçirilmesi önerilir, ancak bu bayrak *true*olduğunda bazı senaryolarda BELIRTEÇLERI alma engelleyebilen adal ile ilgili bir sorun bulundu.
```java
AuthenticationResult result = acquireTokenSilentSync(resourceId, clientId, userId, /* forceRefresh */ false);
```

> [!NOTE]
> Düzeltme girişimi sırasında özel bir engelleme UX 'i göstermek istiyorsanız, showUX parametresi için `remediateCompliance()` ' *e geçmelisiniz.* @No__t-0 ' i çağırmadan önce UX 'nizi gösterdiğinizden ve bildirim dinleyicinizi kaydetmeniz gerekir.  Bu, `remediateCompliance()` ' y i çok hızlı bir şekilde başarısız olursa, bildirimin kaçırıldığı bir yarış durumu engeller.  Örneğin, bir etkinlik alt sınıfının `onCreate()` veya `onMAMCreate()` yöntemi, bildirim dinleyicisini kaydetmek için ideal yerdir ve sonra `remediateCompliance()` ' yi çağırır.  @No__t-0 ' a yönelik parametreler, UX 'e amaç ek ekstraları olarak geçirilebilir.  Uyumluluk durumu bildirimi alındığında, sonucu görüntüleyebilir veya yalnızca etkinliği tamamaktarabilirsiniz.

> [!NOTE]
> `remediateCompliance()`, hesabı kaydeder ve kaydı deneyecektir.  Ana belirteç alındıktan sonra, `registerAccountForMAM()` ' ı çağırmak gerekli değildir, ancak bunu yapmakla bir sorun yoktur. Öte yandan, uygulama belirtecini ve Kullanıcı hesabını kaldırmak için bir kullanıcı hesabını kaldıramazsa, hesabı kaldırmak ve arka plan kaydı yeniden denemelerini engellemek için `unregisterAccountForMAM()` ' ı çağırmalıdır.

## <a name="protecting-backup-data"></a>Yedekleme verilerini koruma
Android sıralamada (API 23) itibariyle Android 'in, bir uygulamanın verilerini yedeklemesi için iki yolu vardır. Her seçenek, uygulamanız için kullanılabilir ve Intune veri korumasının doğru bir şekilde uygulandığından emin olmak için farklı adımlar gerektirir. Doğru veri koruma davranışı için gerekli olan ilgili eylemlerde aşağıdaki tabloyu gözden geçirebilirsiniz.  [ANDROID API Kılavuzu](https://developer.android.com/guide/topics/data/backup.html)'ndaki yedekleme yöntemleri hakkında daha fazla bilgi edinebilirsiniz.

### <a name="auto-backup-for-apps"></a>Uygulamalar için otomatik yedekleme
Android, uygulamanın hedef API 'sinden bağımsız olarak Android sıralamada Mallow cihazlarda uygulamalar için Google Drive 'a [otomatik tam yedeklemeler](https://developer.android.com/guide/topics/data/autobackup.html) sunmaya başladı. AndroidManifest. xml ' de, açıkça `android:allowBackup` ' ı **yanlış**olarak ayarlarsanız, uygulamanız hiçbir zaman Android tarafından yedeklemeler için sıraya alınır ve "Kurumsal" veriler uygulama içinde kalır. Bu durumda, başka bir eylem gerekmez.

Ancak, bildirim dosyasında `android:allowBackup` belirtilmediği halde, varsayılan olarak `android:allowBackup` özniteliği true olarak ayarlanır. Bu, tüm uygulama verilerinin otomatik olarak kullanıcının Google Drive hesabına yedeklendiği anlamına gelir ve bu da **veri sızıntısı riski**taşıyan varsayılan bir davranıştır. Bu nedenle SDK, veri korumasının uygulandığından emin olmak için aşağıda özetlenen değişiklikleri gerektirir.  Uygulamanızın Android sıralamada Mallow cihazlarda çalışmasını istiyorsanız, müşteri verilerini düzgün bir şekilde korumak için aşağıdaki yönergeleri izlemeniz önemlidir.  

Intune, XML 'de özel kurallar tanımlama özelliği de dahil olmak üzere Android 'de kullanılabilen tüm [otomatik yedekleme özelliklerini](https://developer.android.com/guide/topics/data/autobackup.html) kullanmanızı sağlar, ancak verilerinizin güvenliğini sağlamak için aşağıdaki adımları izlemeniz gerekir:

1. Uygulamanız kendi özel BackupAgent **kullanmıyorsa,** Intune ilkesi uyumlu olan otomatik tam yedeklemelere izin vermek Için varsayılan MAMBackupAgent kullanın. Uygulama bildiriminde aşağıdakini yerleştirin:

    ```xml
    android:fullBackupOnly="true"
    android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"
    ```
    
2. **[Isteğe bağlı]** İsteğe bağlı bir özel BackupAgent uyguladıysanız, MAMBackupAgent veya MAMBackupAgentHelper kullandığınızdan emin olmanız gerekir. Aşağıdaki bölümlere bakın. Android e ve üzeri sürümlerde kolay bir yedekleme sağlayan Intune 'un **MAMDefaultFullBackupAgent** (adım 1 ' de açıklanan) kullanmaya geçmeyi göz önünde bulundurun.

3. Uygulamanızın hangi tam yedekleme türünü (filtrelenmemiş, filtrelenmiş veya None) alması gerektiğine karar verirken, `android:fullBackupContent` özniteliğini true, false veya uygulamanızda bir XML kaynağı olarak ayarlamanız gerekir.

4. Ardından, @no__t 2 ' ye yerleştirdiğiniz her şeyi, bildirimde `com.microsoft.intune.mam.FullBackupContent` adlı bir meta veri etiketine kopyalamanız _**gerekir**_ .

    **Örnek 1**: uygulamanızın dışlamaları olmadan tam yedeklemeleri olmasını istiyorsanız, hem `android:fullBackupContent` özniteliğini hem de `com.microsoft.intune.mam.FullBackupContent` meta veri etiketini **doğru**olarak ayarlayın:

    ```xml
    android:fullBackupContent="true"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />  
    ```

    **Örnek 2**: uygulamanızın özel BackupAgent kullanmasını ve tam, Intune ilkesi ile uyumlu ve otomatik yedeklemeleri kabul etmek istiyorsanız, öznitelik ve meta veri etiketini **false**olarak ayarlamanız gerekir:

    ```xml
    android:fullBackupContent="false"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="false" />  
    ```

    **Örnek 3**: UYGULAMANıZıN bir XML dosyasında tanımlanan özel kurallara göre tam yedeklemelere sahip olmasını istiyorsanız, öznitelik ve meta veri etıketını aynı XML kaynağına ayarlayın:

    ```xml
    android:fullBackupContent="@xml/my_scheme"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```

### <a name="keyvalue-backup"></a>Anahtar/değer yedeklemesi
[Anahtar/değer yedekleme](https://developer.android.com/guide/topics/data/keyvaluebackup.html) seçeneği, 8 + tüm API 'lerinde kullanılabilir ve uygulama verilerini [Android Yedekleme hizmetine](https://developer.android.com/google/backup/index.html)yükler. Uygulamanızın Kullanıcı başına veri miktarı 5 MB ile sınırlıdır. Anahtar/değer yedeklemesi kullanırsanız, bir **BackupAgentHelper** veya **BackupAgent**kullanmanız gerekir.

### <a name="backupagenthelper"></a>BackupAgentHelper
BackupAgentHelper, yerel Android işlevselliği ve Intune MAM tümleştirmesi açısından BackupAgent 'den daha kolay bir şekilde uygulanır. BackupAgentHelper, geliştiricinin tüm dosyaları ve paylaşılan tercihleri, oluşturulduktan sonra BackupAgentHelper öğesine eklenen bir **Filebackuphelper** ve **Sharedpreferencesbackuphelper** (sırasıyla) olarak kaydetmesini sağlar. Intune MAM ile BackupAgentHelper kullanmak için aşağıdaki adımları izleyin:

1. Çoklu kimlik yedeklemesini bir BackupAgentHelper kullanarak kullanmak için, [BackupAgentHelper 'Yi genişletmek](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgentHelper)için Android kılavuzunu izleyin.

2. Sınıfınız BackupAgentHelper, FileBackupHelper ve SharedPreferencesBackupHelper 'ın MAM eşdeğerini genişletmenizi sağlayabilirsiniz.

|Android sınıfı | MAM eşdeğeri |
|--|--|
|BackupAgentHelper |MAMBackupAgentHelper |
|FileBackupHelper | MAMFileBackupHelper
|SharedPreferencesBackupHelper| MAMSharedPreferencesBackupHelper|

Bu yönergelerin ardından, başarılı bir çoklu kimlik yedekleme ve geri yükleme işlemi yapılır.

### <a name="backupagent"></a>BackupAgent

Bir BackupAgent, hangi verilerin yedeklendiğine ilişkin çok daha açık olmasına olanak sağlar. Geliştirici uygulamadan çok sorumlu olduğundan, Intune 'dan uygun veri korumasını sağlamak için daha fazla adım gerekir. İşin büyük bir çoğunluğu size gönderildiği için geliştirici, Intune tümleştirmesi biraz daha karmaşıktır.

**MAM tümleştirin:**

1. [Anahtar/değer yedeklemesi](https://developer.android.com/guide/topics/data/keyvaluebackup.html) için Android kılavuzunu dikkatle okuyun ve BackupAgent uygulamanızın Android yönergelerine uyduğundan emin olmak Için özellikle [BackupAgent 'yi uzatın](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent) .

2. Sınıfınızın @no__t uzat-0.

**Çoklu kimlik yedekleme:**

1. Yedeklemeye başlamadan önce, yedeklemeyi planladığınız dosyaların veya veri arabelleklerinin, BT yöneticisinin çok kimlik senaryolarında **yedeklenme konusunda gerçekten izin verildiğini** denetleyin. Bunu öğrenmek için, `MAMFileProtectionManager` ve `MAMDataProtectionManager` ' de `isBackupAllowed` işlevi sağlıyoruz. Dosya veya veri arabelleğinin yedeklenmesine izin verilmiyorsa, bunu yedeklemenize dahil etmeden devam etmeniz gerekir.

2. Yedeklemeniz sırasında bir noktada, 1. adımda iade ettiğiniz dosyaların kimliklerini yedeklemek isterseniz, verileri ayıklamayı planladığınız dosyalarla `backupMAMFileIdentity(BackupDataOutput data, File … files)` ' ı çağırmanız gerekir. Bu, otomatik olarak yeni yedekleme varlıkları oluşturur ve bunları sizin için `BackupDataOutput` ' a yazar. Bu varlıklar geri yükleme sonrasında otomatik olarak tüketilecektir.

**Çoklu kimlik geri yükleme:**

Veri yedekleme Kılavuzu, uygulamanızın verilerini geri yüklemek için genel bir algoritma belirtir ve [genişletme BackupAgent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent) bölümünde bir kod örneği sağlar. Bir çoklu kimlik geri yükleme işleminin başarılı olması için, aşağıdaki özel dikkat ile bu kod örneğinde sunulan genel yapıyı izlemeniz gerekir:

1. Yedekleme varlıklarını kullanarak gezinmek için bir `while(data.readNextHeader())` döngüsü kullanmanız gerekir. Önceki kodda `data`, geri yükleme sırasında uygulamanıza geçirilen **Mambackupdataınput** için yerel değişken adıdır.

2. @No__t-1 `onBackup` ' de yazdığınız anahtarla eşleşmezse `data.skipEntityData()` ' a çağrı yapmanız gerekir. Bu adımı uygulamadan geri yükleme işlemi başarısız olabilir. Önceki kodda `data`, geri yükleme sırasında uygulamanıza geçirilen **Mambackupdataınput** için yerel değişken adıdır.

3. Otomatik olarak yazdığımız varlıklar kaybolacağı için `while(data.readNextHeader())` yapısında yedekleme varlıklarını tüketirken döndürmekten kaçının. Önceki kodda `data`, geri yükleme sırasında uygulamanıza geçirilen **Mambackupdataınput** için yerel değişken adıdır.

## <a name="multi-identity-optional"></a>Çoklu kimlik (isteğe bağlı)

### <a name="overview"></a>Genel Bakış
Varsayılan olarak, Intune uygulama SDK 'Sı ilkeyi uygulamaya bir bütün olarak uygular. Çoklu kimlik, ilkenin kimlik düzeyinde uygulanmasına izin vermek üzere etkinleştirilebilen, isteğe bağlı bir Intune uygulama koruma özelliğidir. Bu, diğer uygulama koruma özelliklerinden önemli ölçüde daha fazla uygulama katılımı gerektirir.

> [!NOTE]
> Doğru uygulama katılımı olmaması, veri sızıntılarına ve diğer güvenlik sorunlarına neden olabilir.

Kullanıcı cihazı veya uygulamayı kaydettikten sonra, SDK bu kimliği kaydeder ve Intune tarafından yönetilen birincil kimliği kabul eder. Uygulamadaki diğer kullanıcılar, kısıtlanmamış ilke ayarlarıyla yönetilmeyen olarak kabul edilir.

> [!NOTE]
> Şu anda cihaz başına yalnızca bir Intune yönetilen kimliği desteklenir.

Kimlik bir dize olarak tanımlanır. Kimlikler **büyük/küçük harfe duyarlıdır**ve bir KIMLIK için SDK istekleri, kimlik ayarlanırken başlangıçta kullanılan büyük/küçük harfleri döndürmeyebilir.

Uygulama, etkin kimliği değiştirmeyi amaçladığında SDK 'Yı *bilgilendirmelidir* . Bazı durumlarda, bir kimlik değişikliği gerektiğinde SDK uygulamaya de bildirir. Ancak, MAM çoğu durumda, Kullanıcı arabiriminde hangi verilerin görüntülendiğini veya belirli bir zamanda bir iş parçacığında kullanıldığını veya veri sızıntısını önlemek için doğru kimliği ayarlamak üzere uygulamayı kullanır. Aşağıdaki bölümlerde, uygulama eylemi gerektiren bazı senaryolar çağrılacaktır.

### <a name="enabling-multi-identity"></a>Çoklu kimliği etkinleştirme
Varsayılan olarak, tüm uygulamalar tek kimlikli uygulamalar olarak kabul edilir. AndroidManifest. xml ' ye aşağıdaki meta verileri yerleştirerek, bir uygulamayı birden çok kimliği algılayan şekilde bildirebilirsiniz.

```xml
  <meta-data
    android:name="com.microsoft.intune.mam.MAMMultiIdentity"
    android:value="true" />
```

### <a name="setting-the-identity"></a>Kimliği ayarlama
Geliştiriciler, uygulama kullanıcısının kimliğini azalan önceliğe göre aşağıdaki düzeylerde ayarlayabilir:

  1. İş parçacığı düzeyi
  2. `Context` (genellikle `Activity`) düzeyi
  3. İşlem düzeyi

İş parçacığı düzeyindeki bir kimlik kümesi, işlem düzeyinde ayarlanmış bir kimliğin yerine geçen `Context` düzeyinde ayarlanmış bir kimliğin yerini alır. @No__t-0 ' daki bir kimlik kümesi yalnızca ilgili ilişkili senaryolarda kullanılır. Dosya GÇ işlemleri, örneğin, ilişkili bir @no__t (0) yoktur. En yaygın olarak, uygulamalar `Context` kimliğini bir `Activity` olarak ayarlar. @No__t-1 kimliği aynı kimliğe ayarlanmadığı takdirde, bir uygulamanın yönetilen kimlik için verileri görüntülemesi *gerekir* . Genel olarak, işlem düzeyi kimliği yalnızca uygulamanın her iş parçacığında tek bir kullanıcıyla çalışması durumunda faydalıdır. Birçok uygulamanın bu uygulamayı kullanması gerekebilir.

Uygulamanız sistem hizmetlerini almak için `Application` bağlamını kullanıyorsa, iş parçacığının veya işlem kimliğinin ayarlandığından veya uygulamanızın `Application` bağlamında Kullanıcı arabirimi kimliğini ayarlamış olduğunuzdan emin olun.

Kullanıcı arabirimi kimliğini `setUIPolicyIdentity` veya `switchMAMIdentity` ile güncelleştirirken özel durumları işlemek için her iki yöntemde de bir dizi `IdentitySwitchOption` değeri geçirilebilir.

* `IGNORE_INTENT`: geçerli etkinlikle ilişkili amacı yoksayması gereken bir kimlik anahtarı istiyorsa kullanın.
  Örnek:

  1. Uygulamanız yönetilen bir belge içeren yönetilen bir kimlikle bir amaç alır ve uygulamanız belgeyi görüntüler.
  2. Kullanıcı kendi kişisel kimlik özelliklerine geçiş yaptığında, uygulamanız bir kullanıcı arabirimi kimlik anahtarı ister. Kişisel kimlikte, uygulamanız artık belgeyi görüntülemediğinden, kimlik anahtarını istenirken `IGNORE_INTENT` ' ı kullanırsınız.

  Ayarlanmamışsa, SDK en son amacın uygulamada hala kullanılmakta olduğunu varsayacaktır. Bu, yeni kimliğin alma ilkesinin, amacı gelen veri olarak ele alınmasına ve kimliğini kullanmasına neden olur.

>[!NOTE]
> @No__t-0 Kullanıcı arabirimi işlemleri için kullanıldığından, SDK, `ClipboardManager` işlemleri için ön plan etkinliğinin Kullanıcı arabirimi kimliğini kullanır.
> @No__t-0 ' daki aşağıdaki yöntemler, kimlik ayarlamak ve önceden ayarlanan kimlik değerlerini almak için kullanılabilir.

```java
public static void setUIPolicyIdentity(final Context context, final String identity, final MAMSetUIIdentityCallback mamSetUIIdentityCallback, final EnumSet<IdentitySwitchOption> options);

  public static String getUIPolicyIdentity(final Context context);

  public static MAMIdentitySwitchResult setProcessIdentity(final String identity);

  public static String getProcessIdentity();

  public static MAMIdentitySwitchResult setCurrentThreadIdentity(final String identity);

  public static String getCurrentThreadIdentity();

/**
   * Get the current app policy. This does NOT take the UI (Context) identity into account.
   * If the current operation has any context (e.g. an Activity) associated with it, use the overload below.
   */
  public static AppPolicy getPolicy();

  /**
  * Get the current app policy. This DOES take the UI (Context) identity into account.
   * If the current operation has any context (e.g. an Activity) associated with it, use this function.
   */
  public static AppPolicy getPolicy(final Context context);


  public static AppPolicy getPolicyForIdentity(final String identity);

  public static boolean getIsIdentityManaged(final String identity);
  ```

>[!NOTE]
> Uygulamanın kimliğini null olarak ayarlayarak temizleyebilirsiniz.
>
> Boş dize, hiçbir an uygulama koruma ilkesine sahip olmayacak bir kimlik olarak kullanılabilir.

#### <a name="results"></a>Sonuçlar
@No__t-0 ile sonuç değerlerini yeniden bildirmek için kullanılan tüm yöntemler. Döndürülebilecek dört değer vardır:

| Dönüş değeri | Senaryo |
|--            |--        |
| `SUCCEEDED`    | Kimlik değişikliği başarılı oldu. |
| `NOT_ALLOWED`  | Kimlik değişikliğine izin verilmiyor. Bu, geçerli iş parçacığında farklı bir kimlik ayarlandığında UI (`Context`) kimliğini ayarlamak için bir girişimde bulunulduğunda oluşur. |
| `CANCELLED`    | Kullanıcı, genellikle bir PIN veya kimlik doğrulama isteminde geri düğmesine basılarak kimlik değişikliğini iptal etti. |
| `FAILED`       | Kimlik değişikliği belirlenemeyen bir nedenden dolayı başarısız oldu.|

Uygulama, kurumsal verileri görüntülemeden veya kullanmadan önce bir kimlik anahtarının başarılı olduğundan emin olmalıdır. Şu anda, işlem ve iş parçacığı kimlik anahtarları çoklu kimliği etkinleştirilmiş bir uygulama için her zaman başarılı olur, ancak hata koşulları ekleme hakkını saklı tutarız. UI kimlik anahtarı geçersiz bağımsız değişkenler için başarısız olabilir, iş parçacığı kimliğiyle çakışıyorsa veya Kullanıcı koşullu başlatma gereksinimlerini iptal ederse (örneğin, PIN ekranındaki geri düğmesine basar). Etkinlik üzerinde başarısız bir UI kimliği anahtarı için varsayılan davranış etkinliğin tamamlanmasından (aşağıda `onSwitchMAMIdentityComplete` ' a bakın).

@No__t-0 kimliği `setUIPolicyIdentity` aracılığıyla ayarlandığında, sonuç zaman uyumsuz olarak bildirilir. @No__t-0 ' ı bir `Activity` ise, koşullu başlatma işlemi tamamlanana kadar kimlik değişikliğinin başarılı olup olmadığını ve kullanıcının bir PIN veya kurumsal kimlik bilgilerini girmesini gerektirebilecek SDK bunu bilmez. Uygulama bu sonucu almak için bir @no__t uygulayabilir veya geri çağırma nesnesi için null değeri geçirebilir. @No__t-0 ' a bir çağrı yapılırsa, *aynı bağlam üzerindeki* önceki `setUIPolicyIdentity` çağrısının sonucu henüz teslim edilmediğini, yeni geri çağırma eskisinin yerini değiştirdiğine ve özgün geri aramanın hiçbir şekilde sonuç almadığına unutmayın.

```java
    public interface MAMSetUIIdentityCallback {
        void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult);
  }
```

Ayrıca, `MAMPolicyManager.setUIPolicyIdentity` ' i çağırmak yerine `MAMActivity` ' daki bir yöntem aracılığıyla bir etkinliğin kimliğini doğrudan ayarlayabilirsiniz. Bunu yapmak için aşağıdaki yöntemi kullanın:

```java
     public final void switchMAMIdentity(final String newIdentity, final EnumSet<IdentitySwitchOption> options);
```

Ayrıca, uygulamanın bu etkinliğin kimliğini değiştirme denemelerinin sonucu hakkında bildirim almak istiyorsanız, `MAMActivity` ' da bir yöntemi geçersiz kılabilirsiniz.

``` java
    public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);
```

@No__t-0 ' y i geçersiz kılamazsınız (veya `super` metodunu çağırırsanız), bir etkinlikte başarısız bir kimlik anahtarı etkinliğin tamamlanmasının oluşmasına neden olur. Yöntemini geçersiz kılarsınız, bir başarısız kimlik anahtarından sonra kurumsal verilerin görüntülenmediğinden emin olmanız gerekir.

>[!NOTE]
> Kimliği değiştirmek için etkinliğin yeniden oluşturulması gerekebilir. Bu durumda, `onSwitchMAMIdentityComplete` geri çağırması etkinliğin yeni örneğine teslim edilir.


### <a name="implicit-identity-changes"></a>Örtük kimlik değişiklikleri
Uygulamanın kimliği, bir iş parçacığını veya bağlamın kimliğini ayarlama özelliğine ek olarak, uygulama koruma ilkesi olan başka bir Intune ile yönetilen uygulamadan veri girişi temelinde değişebilir.

#### <a name="examples"></a>Örnekler
1. Bir etkinlik başka bir MAM uygulaması tarafından gönderilen `Intent` ' dan başlatılmışsa, etkinliğin kimliği, `Intent` ' ın gönderildiği noktada diğer uygulamadaki etkin kimliğe göre ayarlanır.

2. Hizmetler için iş parçacığı kimliği, `onStart` veya `onBind` çağrısının süresine benzer şekilde ayarlanır. @No__t-1 ' den döndürülen `Binder` ' a yapılan çağrılar, iş parçacığı kimliğini de geçici olarak ayarlar.

3. @No__t-0 ' a yapılan çağrılar aynı şekilde iş parçacığı kimliğini süreleri olarak ayarlar.


    Ayrıca, bir etkinlikle Kullanıcı etkileşimi örtük bir kimlik anahtarına neden olabilir.

    **Örnek:** @No__t-1 sırasında yetkilendirme isteminde iptal eden bir Kullanıcı, boş bir kimliğe örtük bir anahtarla sonuçlanır.

    Uygulamaya bu değişikliklerden haberdar olmak için bir fırsat verilir ve bu durumda, uygulama bunları bir şekilde kullanabilir. `MAMService` ve `MAMContentProvider`, alt sınıfların geçersiz kılabileceği aşağıdaki yöntemi kullanıma sunar:

    ```java
    public void onMAMIdentitySwitchRequired(final String identity,
      final AppIdentitySwitchResultCallback callback);
    ```

    @No__t-0 sınıfında, yönteminde ek bir parametre bulunur:

    ```java
    public void onMAMIdentitySwitchRequired(final String identity,
      final AppIdentitySwitchReason reason,
      final AppIdentitySwitchResultCallback callback);
    ```

    * @No__t-0 örtük anahtarın kaynağını yakalar ve `CREATE`, `RESUME_CANCELLED` ve `NEW_INTENT` değerlerini kabul edebilir.  @No__t-0 nedeni, etkinlik özgeçmişi PIN, kimlik doğrulama veya diğer uyumluluk Kullanıcı arabiriminin görüntülenmesine neden olduğunda ve Kullanıcı bu kullanıcı ARABIRIMINDEN iptal etmeyi denediğinde, genellikle geri düğmesinin kullanılması durumunda kullanılır.


    * @No__t-0 aşağıdaki gibidir:

      ```java
      public interface AppIdentitySwitchResultCallback {
          /**
            * @param result
            *            whether the identity switch can proceed.
            */
          void reportIdentitySwitchResult(AppIdentitySwitchResult result);
        }
        ```

      @No__t-0 `SUCCESS` ya da `FAILURE` ' dir.

@No__t-0 yöntemi, `MAMService.onMAMBind` ' den döndürülen bir ciltçide yapılan tüm örtük kimlik değişiklikleri için çağrılır. @No__t-0 ' ın varsayılan uygulamaları hemen çağırır:

* `RESUME_CANCELLED`  olduğunda 0.

* diğer tüm durumlarda `reportIdentitySwitchResult(SUCCESS)`.

  Çoğu uygulamanın bir kimlik anahtarını farklı bir şekilde engellemesi veya geciktirmesi beklenmez, ancak bir uygulamanın bunu yapması gerekiyorsa, aşağıdaki noktaların göz önünde bulundurulması gerekir:

  * Bir kimlik anahtarı engellenirse, sonuç `Receive` paylaşım ayarları veri girişini yasakladı.

  * Ana iş parçacığında bir hizmet çalışıyorsa, @no__t **-0 eşzamanlı** olarak ÇAĞRıLMALıDıR veya UI iş parçacığı askıda kalır.

  * **@No__t-1** oluşturmak için, `onMAMIdentitySwitchRequired` `onMAMCreate` ' den önce çağrılır. Uygulamanın kimlik anahtarına izin verip vermeyeceğinizi belirleyebilmek için Kullanıcı arabirimini göstermesi gerekiyorsa, bu UI *farklı* bir etkinlik kullanılarak gösterilmelidir.

  * **@No__t-1**' de, `RESUME_CANCELLED` olarak boş kimliğe bir anahtar istendiğinde, uygulamanın bu kimlik anahtarıyla tutarlı verileri görüntülemesi için devam eden etkinliği değiştirmesi gerekir.  Bu mümkün değilse, uygulama anahtarı reddetmelidir ve kullanıcıdan bir kez daha devam eden kimlik ilkesine uyması istenir (örneğin, uygulama PIN girişi ekranı ile sunulduğundan).

    > [!NOTE]
    > Çok kimlikli bir uygulama, yönetilen ve yönetilmeyen uygulamalardan gelen verileri her zaman alır. Yönetilen kimliklerden alınan verileri yönetilen bir şekilde ele almak uygulamanın sorumluluğundadır.

  İstenen bir kimlik yönetilmiyorsa (denetlemek için `MAMPolicyManager.getIsIdentityManaged` ' ı kullanın), ancak uygulama bu hesabı kullanamayacak (örneğin, e-posta hesapları gibi hesapların önce uygulamada ayarlanması gerektiğinden), kimlik anahtarı reddedildi.

#### <a name="build-plugin--tool-considerations"></a>Derleme eklentisi/araç konuları
@No__t-0, `MAMService` veya `MAMContentProvider` ' den açıkça kalıtımla almadıysanız (Bu değişikliği yapmak için derleme araçlarına izin verseniz), ancak yine de kimlik anahtarlarını işlemesi gerekiyorsa, bunun yerine `MAMActivityIdentityRequirementListener` (bir `Activity` için) veya `MAMIdentityRequirementListener` (`Service` veya `ContentProviders`) uygulayabilirsiniz .
@No__t-0 ' a yönelik varsayılan davranışa, `MAMActivity.defaultOnMAMIdentitySwitchRequired(activity, identity,
reason, callback)` statik yöntemi çağırarak erişilebilir.

Benzer şekilde, `MAMActivity.onSwitchMAMIdentityComplete` ' ı geçersiz kılmanız gerekiyorsa, `MAMActivity` ' den açıkça devralmadan `MAMActivityIdentitySwitchListener` uygulayabilirsiniz.

### <a name="preserving-identity-in-async-operations"></a>Zaman uyumsuz Işlemlerde kimlik koruma
Başka bir iş parçacığına arka plan görevleri göndermek için Kullanıcı arabirimi iş parçacığında işlemler yaygındır. Çok kimlikli bir uygulama, bu arka plan görevlerinin, genellikle kendilerini yükleyen etkinliğin kullandığı kimlik ile uygun kimlik ile çalıştığından emin olmak ister. MAM SDK, kimliği koruma konusunda yardımcı olmak için `MAMAsyncTask` ve `MAMIdentityExecutors` ' i sağlar.
Bu, zaman uyumsuz işlem bir dosyaya şirket verileri yazabileceği veya diğer uygulamalarla iletişim kurabiliyorsa kullanılmalıdır.

#### <a name="mamasynctask"></a>MAMAsyncTask
@No__t-0 ' ı kullanmak için, `AsyncTask` yerine yalnızca ondan devralın ve `doInBackground` ve `onPreExecute` geçersiz kılmalarını sırasıyla `doInBackgroundMAM` ve `onPreExecuteMAM` ile değiştirin. @No__t-0 Oluşturucusu bir etkinlik bağlamını alır. Örnek:

```java
  AsyncTask<Object, Object, Object> task = new MAMAsyncTask<Object, Object, Object>(thisActivity) {

    @Override
    protected Object doInBackgroundMAM(final Object[] params) {
        // Do operations.
    }

    @Override
    protected void onPreExecuteMAM() {
        // Do setup.
    };
}
```

### <a name="mamidentityexecutors"></a>Mamıdentityyürüticileri
`MAMIdentityExecutors`, mevcut bir `Executor` veya `ExecutorService` örneğini bir kimlik ile `Executor` @ no__t-4 @ no__t-5 ' i `wrapExecutor` ve `wrapExecutorService` yöntemleriyle sarmasını sağlar. Örneğin:

```java
  Executor wrappedExecutor = MAMIdentityExecutors.wrapExecutor(originalExecutor, activity);
  ExecutorService wrappedService = MAMIdentityExecutors.wrapExecutorService(originalExecutorService, activity);
```

### <a name="file-protection"></a>Dosya Koruması
Her dosyanın, oluşturma sırasında iş parçacığı ve işlem kimliği temel alınarak onunla ilişkili bir kimliği vardır. Bu kimlik hem dosya şifreleme hem de seçmeli silme için kullanılacaktır. Yalnızca kimliği yönetilen ve şifreleme gerektiren bir ilke olan dosyalar şifrelenir. SDK 'nın varsayılan seçmeli işlevselliği silme işlemi yalnızca bir silme işlemi istenen yönetilen kimlikle ilişkili dosyaları temizler. Uygulama, `MAMFileProtectionManager` sınıfını kullanarak bir dosyanın kimliğini sorgulayabilir veya değiştirebilir.

```java
public final class MAMFileProtectionManager {

   /**
    * Protect a file or directory. This will synchronously trigger whatever protection is required for the file, and will tag the
    * file for future protection changes. If an identity is set on a directory, it is set recursively on all files and
    * subdirectories. New files or directories will inherit their parent directory's identity. If MAM is operating in offline mode,
    * this method will silently do nothing.
    *
    * @param identity
    *       Identity to set.
    * @param file
    *       File to protect.
    *
    * @throws IOException
    *       If the file cannot be protected.
    */
   public static void protect(final File file, final String identity) throws IOException;

   /**
     * Protect a file obtained from a content provider. This is intended to be used for
     * sdcard (whether internal or removable) files accessed through the Storage Access Framework.
     * It may also be used with descriptors referring to private files owned by this app.
     * It is not intended to be used for files owned by other apps and such usage will fail. If
     * creating a new file via a content provider exposed by another MAM-integrated app, the new
     * file identity will automatically be set correctly if the ContentResolver in use was
     * obtained via a Context with an identity or if the thread identity is set.
     *
     * This will synchronously trigger whatever protection is required for the file, and will tag
     * the file for future protection changes. If an identity is set on a directory, it is set
     * recursively on all files and subdirectories. If MAM is operating in offline mode, this
     * method will silently do nothing.
     *
     * @param identity
     *            Identity to set.
     * @param file
     *            File to protect.
     *
     * @throws IOException
     *             If the file cannot be protected.
     */
    public static void protect(final ParcelFileDescriptor file, final String identity) throws IOException;

   /**
    * Get the protection info on a file.
    *
    * @param file
    *            File or directory to get information on.
    * @return File protection info, or null if there is no protection info.
    * @throws IOException
    *             If the file cannot be read or opened.
    */
    public static MAMFileProtectionInfo getProtectionInfo(final File file) throws IOException;

   /**
    * Get the protection info on a file.
    *
    * @param file
    *            File or directory to get information on.
    * @return File protection info, or null if there is no protection info.
    * @throws IOException
    *             If the file cannot be read or opened.
    */
    public static MAMFileProtectionInfo getProtectionInfo(final ParcelFileDescriptor file) throws IOException;

}

public interface MAMFileProtectionInfo {
    String getIdentity();
}
 ```

#### <a name="app-responsibility"></a>Uygulama sorumluluğu
MAM, okunan dosyalar ile `Activity` arasında görüntülenmekte olan veriler arasındaki ilişkiyi otomatik olarak çıkarsamaz. Uygulamalar, kurumsal verileri görüntülemeden önce Kullanıcı arabirimi kimliğini uygun şekilde ayarlamış *olmalıdır* . Bu, dosyalardan okunan verileri içerir. Bir dosya uygulamanın dışından geliyorsa (bir `ContentProvider` ' dan veya genel olarak yazılabilir bir konumdan okunmadan), uygulama, dosyadan okunan bilgileri görüntülemeden önce dosya kimliğini (`MAMFileProtectionManager.getProtectionInfo` kullanarak) belirlemeyi *denemelidir* . @No__t-0 null olmayan ve boş olmayan bir kimlik bildirirse, Kullanıcı *arabirimi kimliği bu kimlikle eşleşecek* şekilde ayarlanmalıdır (`MAMActivity.switchMAMIdentity` veya `MAMPolicyManager.setUIPolicyIdentity` kullanılarak). Kimlik anahtarı başarısız olursa, dosyadaki verilerin görüntülenmemesi *gerekir* .

Örnek akış aşağıdakine benzer bir şekilde görünebilir:
* Kullanıcı uygulamada açmak için bir belge seçer.
  * Açık akış sırasında, diskten veri okumadan önce, uygulama, içeriği göstermek için kullanılması gereken kimliği onaylar:

    ```java
    MAMFileProtectionInfo info = MAMFileProtectionManager.getProtectionInfo(docPath)
    if (info != null)
        MAMPolicyManager.setUIPolicyIdentity(activity, info.getIdentity(), callback, EnumSet.noneOf<IdentitySwitchOption.class>)
    ```

  * Uygulama, geri çağırmaya bir sonuç bildirilene kadar bekler.
  * Bildirilen sonuç bir hata ise, uygulama belgeyi görüntülemez.
* Uygulama açılır ve dosyayı işler.
  
#### <a name="single-identity-to-multi-identity-transition"></a>Tek kimlikle çoklu kimlik geçişi
Daha önce tek kimlik Intune tümleştirmesiyle yayınlanan bir uygulama, daha sonra çok kimliği tümleştirirse, daha önce yüklenen uygulamalar bir geçişe (kullanıcıya görünmez, ilişkili bir UX yoktur) sahip olur. Uygulamanın bu geçişi işlemek için açık bir şey *yapması gerekmez.* Geçişten önce oluşturulan tüm dosyalar yönetilmeye devam edecektir (Bu nedenle, şifreleme ilkesi açık ise şifreli kalacak). İsterseniz, yükseltmeyi algılayabilir ve belirli dosyaları veya dizinleri etiketlemek için `MAMFileProtectionManager.protect` ' ı kullanarak boş kimlikle (şifrelendiklerinde şifrelemeyi kaldırır).

#### <a name="offline-scenarios"></a>Çevrimdışı senaryolar
Dosya kimliği etiketleme, çevrimdışı moda duyarlıdır. Şu noktaların hesaba alınması gerekir:

* Şirket Portalı yüklü değilse, dosyalar kimlik etiketli olamaz.

* Şirket Portalı yüklüyse ancak uygulamada Intune MAM ilkesi yoksa, dosyalar güvenilir bir şekilde kimlik ile etiketlenemez.

* Dosya kimliği etiketleme kullanılabilir olduğunda, uygulama daha önce tek kimlikli yönetilen bir uygulama olarak (Bu durumda kabul edildiğinde) daha önce yüklenmemişse, önceden oluşturulan tüm dosyalar kişisel/yönetilmeyen olarak değerlendirilir (boş dize kimliğine ait). kayıtlı kullanıcıya ait.

### <a name="directory-protection"></a>Dizin koruması
Dizinler, dosyaları korumak için kullanılan `protect` yöntemi kullanılarak korunabilir. Dizin koruması, dizinde bulunan tüm dosyalar ve alt dizinlere ve dizin içinde oluşturulan yeni dosyalara yinelemeli olarak uygulanır. Dizin koruması yinelemeli olarak uygulandığından, büyük dizinler için `protect` çağrısının tamamlanması biraz zaman alabilir. Bu nedenle, çok sayıda dosya içeren bir dizine koruma uygulayan uygulamalar, bir arka plan iş parçacığında `protect` ' ı zaman uyumsuz olarak çalıştırmak isteyebilir.

### <a name="data-protection"></a>Veri Koruma
Bir dosyayı birden çok kimliğe ait olacak şekilde etiketlemek mümkün değildir. Aynı dosyada farklı kullanıcılara ait verileri depolaması gereken uygulamalar, `MAMDataProtectionManager` tarafından belirtilen özellikleri kullanarak bu şekilde el ile yapılabilir. Bu, uygulamanın verileri şifrelemesine ve belirli bir kullanıcıya bağlamasına olanak tanır. Şifrelenmiş veriler bir dosyadaki diske depolamak için uygundur. Kimlikle ilişkili verileri sorgulayabilir ve veriler daha sonra şifrelenmemiş olabilir.

@No__t-0 ' i kullanan uygulamalar, `MANAGEMENT_REMOVED` bildirimi için bir alıcı uygulamalıdır. Bu bildirim tamamlandıktan sonra, arabellekler korunduğunda dosya şifrelemesi etkinleştirilmişse, bu sınıf aracılığıyla korunan arabellekler artık okunamaz. Bir uygulama, bu bildirim sırasındaki tüm arabelleklere `MAMDataProtectionManager.unprotect` çağırarak bu durumu düzeltebilir. Kimlik bilgilerini korumak isteniyorsa, bu bildirim sırasında koruma çağrısı yapmak da güvenlidir; bildirim sırasında şifrelemenin devre dışı bırakılması garanti edilir.

```java

public final class MAMDataProtectionManager {
    /**
     * Protect a stream. This will return a stream containing the protected
     * input.
     *
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect, read sequentially. This function
     *            will change the position of the stream but may not have
     *            read the entire stream by the time it returns. The
     *            returned stream will wrap this one. Calls to read on the
     *            returned stream may cause further reads on the original
     *            input stream. Callers should not expect to read directly
     *            from the input stream after passing it to this method.
     *            Calling close on the returned stream will close this one.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static InputStream protect(final InputStream input, final String identity);

    /**
     * Protect a byte array. This will return protected bytes.
     *
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static byte[] protect(final byte[] input, final String identity) throws IOException;

    /**
     * Unprotect a stream. This will return a stream containing the
     * unprotected input.
     *
     * @param input
     *            Input data to protect, read sequentially.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static InputStream unprotect(final InputStream input) throws IOException;

    /**
     * Unprotect a byte array. This will return unprotected bytes.
     *
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static byte[] unprotect(final byte[] input) throws IOException;

    /**
     * Get the protection info on a stream.
     *
     * @param input
     *            Input stream to get information on. Either this input
     *            stream must have been returned by a previous call to
     *            protect OR input.markSupported() must return true.
     *            Otherwise it will be impossible to get protection info
     *            without advancing the stream position. The stream must be
     *            positioned at the beginning of the protected data.
     * @return Data protection info, or null if there is no protection
     *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final InputStream input) throws IOException;

    /**
     * Get the protection info on a stream.
     *
     * @param input
     *            Input bytes to get information on. These must be bytes
     *            returned by a previous call to protect() or a copy of
     *            such bytes.
     * @return Data protection info, or null if there is no protection
     *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final byte[] input) throws IOException;
}
```

### <a name="content-providers"></a>İçerik sağlayıcıları
Uygulama, bir `ContentProvider` üzerinden `ParcelFileDescriptor` dışında bir şirket verisi sağlıyorsa, uygulamanın, içerik için sahip kimliğinin UPN 'sini (Kullanıcı asıl adı) geçirerek `MAMContentProvider` ' te `isProvideContentAllowed(String)` yöntemini çağırması gerekir. Bu işlev false döndürürse *, içerik çağırana döndürülmemelidir.* Bir içerik sağlayıcısı aracılığıyla döndürülen dosya tanımlayıcıları dosya kimliğine göre otomatik olarak işlenir.

@No__t-0 ' ı açıkça devralmasını ve bunun yerine bu değişikliği yapmak için derleme araçlarına izin vermek istiyorsanız, aynı yöntemin statik bir sürümünü çağırabilirsiniz: `MAMContentProvider.isProvideContentAllowed(provider,
contentIdentity)`.

### <a name="selective-wipe"></a>Seçmeli silme
Çok kimlikli bir uygulama `WIPE_USER_DATA` bildirimine kaydolduktan sonra, söz konusu kullanıcıya ait olan tüm dosyalar dahil olmak üzere, silinen kullanıcının tüm verilerini kaldırma sorumluluğundadır. Uygulama, Kullanıcı verilerini bir dosyadan kaldırırsa, ancak dosyadaki diğer verileri bırakmak isterse, dosyanın kimliğini (`MAMFileProtectionManager.protect` ile kişisel Kullanıcı veya boş kimlik *) değiştirmeli.* Şifreleme ilkesi kullanılıyorsa, silinen kullanıcıya ait kalan dosyaların şifresi çözülür ve Temizleme işleminden sonra uygulamaya erişilemez hale gelir.

@No__t-0 için bir uygulama kaydı, SDK 'nın varsayılan seçmeli silme davranışının avantajını almaz. Çoklu kimlik duyarlı uygulamalar için, MAM varsayılan seçmeli silme yalnızca kimliği bir silme işlemi tarafından hedeflenen dosyaları temizlediğinden bu kayıp daha önemli olabilir. Çok kimlikli bir uygulama, MAM varsayılan seçmeli silme işlemini gerçekleştirmeye _**ve**_ silme sırasında kendi eylemlerini gerçekleştirmeyi dileiyorsa, `WIPE_USER_AUXILIARY_DATA` bildirimlerine kaydolmalıdır. Bu bildirim, MAM varsayılan seçmeli silme işlemini gerçekleştirmeden önce SDK tarafından hemen gönderilir. Bir uygulama asla `WIPE_USER_DATA` ve `WIPE_USER_AUXILIARY_DATA` için hiçbir şekilde kaydolmamalıdır.

Varsayılan seçmeli silme, uygulamayı düzgün bir şekilde kapatacak, etkinlikleri sonlandıracaktır ve uygulama işlemini sonlandıracaktır. Uygulamanız varsayılan seçmeli silme işlemlerini geçersiz kılıyorsa, silme gerçekleştikten sonra kullanıcının bellek içi verilere erişmesini engellemek için uygulamanızı el ile kapatmayı düşünebilirsiniz.

## <a name="enabling-mam-targeted-configuration-for-your-android-applications-optional"></a>Android uygulamalarınız için MAM hedefli yapılandırmayı etkinleştirme (isteğe bağlı)
Uygulamaya özgü anahtar-değer çiftleri, [mam-we](https://docs.microsoft.com/intune/app-configuration-policies-managed-app) ve [Android Enterprise](https://docs.microsoft.com/intune/app-configuration-policies-use-android)için Intune konsolunda yapılandırılabilir.
Bu anahtar-değer çiftleri Intune tarafından hiç yorumlanmaz, ancak uygulamaya geçirilir. Bu tür yapılandırmayı almak isteyen uygulamalar, `MAMAppConfigManager` ve `MAMAppConfig` sınıflarını kullanarak bunu yapabilir. Aynı uygulamaya birden çok ilke hedeflenirse, aynı anahtar için birden fazla çakışan değer bulunabilir.

> [!NOTE] 
> MAM aracılığıyla teslim için yapılandırma kurulumu-`offline` ' da (Şirket Portalı yüklü olmadığında) yok edilebilir.  Bu durumda, boş bir kimlikte yalnızca Android Enterprise AppRestrictions `MAMUserNotification` üzerinden dağıtılır.

### <a name="get-the-app-config-for-a-user"></a>Bir Kullanıcı Için uygulama yapılandırmasını al
Uygulama yapılandırması aşağıdaki gibi alınmış olabilir:
```java
MAMAppConfigManager configManager = MAMComponents.get(MAMAppConfigManager.class);
String identity = "user@contoso.com"
MAMAppConfig appConfig = configManager.getAppConfig(identity);
```

MAM kayıtlı kullanıcı yoksa ancak uygulamanız hala Android kurumsal yapılandırmasını (belirli bir kullanıcıya hedeflenmeyecek) almak istiyorsanız, null veya boş bir dize geçirebilirsiniz.

### <a name="conflicts"></a>Çakışmalar
MAM App config içindeki bir değer, Android kurumsal yapılandırması 'nda aynı anahtarla ayarlanmış bir değeri geçersiz kılacaktır. 

Bir yönetici aynı anahtar için çakışan değerleri yapılandırırsa (örneğin, aynı kullanıcıyı içeren birden çok gruba sahip farklı uygulama yapılandırma kümelerini hedefleyerek), Intune bu çakışmayı otomatik olarak çözmek için herhangi bir yola sahip değildir ve tüm değerleri oluşturur uygulamanız için kullanılabilir. 

Uygulamanız, `MAMAppConfig` nesnesinden verilen bir anahtarın tüm değerlerini isteyebilir:
```java
List<Boolean> getAllBooleansForKey(String key)
List<Long> getAllIntegersForKey(final String key)
List<Double> getAllDoublesForKey(final String key)
List<String> getAllStringsForKey(final String key)
```

veya seçilecek bir değer iste:
```java
Boolean getBooleanForKey(String key, BooleanQueryType queryType)
Long getIntegerForKey(String key, NumberQueryType queryType)
Double getDoubleForKey(String key, NumberQueryType queryType)
String getStringForKey(String key, StringQueryType queryType)

enum BooleanQueryType {
    /**
     * In case of conflict, arbitrarily picks one. This is not guaranteed to return the same value every time.
     */
    Any,
    /**
     * In case of conflict, returns true if any of the values are true.
     */
    Or,
    /**
     * In case of conflict, returns false if any of the values are false.
     */
    And
}

enum NumberQueryType {
    /**
     * In case of conflict, arbitrarily picks one. This is not guaranteed to return the same value every time.
     */
    Any,
    /**
     * In case of conflict, returns the minimum Integer.
     */
    Min,
    /**
     * In case of conflict, returns the maximum Integer.
     */
    Max
}

enum StringQueryType {
    /**
     * In case of conflict, arbitrarily picks one. This is not guaranteed to return the same value every time.
     */
    Any,
    /**
     * In case of conflict, returns the first result ordered alphabetically.
     */
    Min,

    /**
     * In case of conflict, returns the last result ordered alphabetically.
     */
    Max
}
```

Uygulamanız ham verileri anahtar-değer çiftleri kümesinin bir listesi olarak da talep edebilir.

```java
List<Map<String, String>> getFullData()
```

### <a name="full-example"></a>Tam örnek
```java
MAMAppConfigManager configManager = MAMComponents.get(MAMAppConfigManager.class);
String identity = "user@contoso.com"
MAMAppConfig appConfig = configManager.getAppConfig(identity);
String fooValue = null;
if (appConfig.hasConflict("foo")) {
    List<String> values = appConfig.getAllStringsForKey("foo");
    fooValue = chooseBestValue(values);
} else {
    valueToUse = appConfig.getStringForKey("foo", MAMAppConfig.StringQueryType.Any);
}
Long barValue = appConfig.getIntegerForKey("bar", MAMAppConfig.NumberQueryType.Min);
```

### <a name="notification"></a>Bildirim
Uygulama yapılandırması yeni bir bildirim türü ekler:
* **REFRESH_APP_CONFIG**: Bu bildirim bir `MAMUserNotification` ' de gönderilir ve uygulamaya yeni uygulama yapılandırma verilerinin kullanılabilir olduğunu bildirir.

### <a name="further-reading"></a>Daha fazla okuma
Android 'de MAM hedefli bir uygulama yapılandırma ilkesi oluşturma hakkında daha fazla bilgi için bkz. [Android için Microsoft Intune uygulama yapılandırma ilkeleri kullanma](https://docs.microsoft.com/intune/app-configuration-policies-managed-app)bölümünde mam hedefli uygulama yapılandırma bölümüne bakın.

Uygulama yapılandırması, Graph API kullanılarak da yapılandırılabilir. Bilgi için, [mam hedeflenen yapılandırması için Graph API belgelerine](https://docs.microsoft.com/graph/api/resources/intune-mam-targetedmanagedappconfiguration)bakın.

## <a name="style-customization-optional"></a>Stil özelleştirme (isteğe bağlı)
MAM SDK tarafından oluşturulan görünümler, tümleşik olduğu uygulamayla daha yakından eşleşecek şekilde görsel olarak özelleştirilebilir. Birincil, ikincil ve arka plan renklerini ve uygulama logosunun boyutunu özelleştirebilirsiniz. Bu stil özelleştirmesi isteğe bağlıdır ve özel bir stil yapılandırılmamışsa varsayılanlar kullanılacaktır.

### <a name="how-to-customize"></a>Özelleştirme
Stil değişikliklerinin Intune MAM görünümlerine uygulanmasını sağlamak için, önce bir stil geçersiz kılma XML dosyası oluşturmanız gerekir. Bu dosya, uygulamanızın "/Res/xml" dizinine yerleştirilmelidir ve istediğiniz gibi adlandırabilirsiniz. Aşağıda, bu dosyanın izlenmesi gereken biçimin bir örneği verilmiştir.

```xml
<?xml version="1.0" encoding="utf-8"?>
<styleOverrides>
    <item
        name="foreground_color"
        resource="@color/red"/>
    <item
        name="accent_color"
        resource="@color/blue"/>
    <item
        name="background_color"
        resource="@color/green"/>
    <item
        name="logo_image"
        resource="@drawable/app_logo"/>
</styleOverrides>
```

Uygulamanızda zaten mevcut olan kaynakları yeniden kullanmanız gerekir. Örneğin, Colors. xml dosyasında Green rengini tanımlamanız ve buraya başvurmalısınız. "#0000ff" onaltılık renk kodunu kullanamazsınız. Uygulama logosu için en büyük boyut 110 DIP (DP) şeklindedir. Daha küçük bir logo görüntüsü kullanabilirsiniz, ancak en büyük boyuta uymak en iyi arama sonucunu verir. 110 DIP sınırını aşarsanız, görüntü ölçeği küçültülecektir ve büyük olasılıkla bulanıklaştırma olur.

Aşağıda, izin verilen stil özniteliklerinin, kontrol ettikleri Kullanıcı arabirimi öğelerinin, XML özniteliği öğe adlarının ve her biri için beklenen kaynak türünün tamamı listelenmiştir.

|Style özniteliği | Etkilenen UI öğeleri | Öznitelik öğesi adı | Beklenen kaynak türü |
| -- | -- | -- | -- |
| Arka plan rengi | PIN ekranı arka plan rengi <Br>PIN kutusu dolgusu rengi | background_color | Renk |
| Ön plan rengi | Ön plan metin rengi <br> Varsayılan durumda SABITLEME kutusu kenarlığı <br> Kullanıcı bir PIN girdiğinde, PIN kutusundaki karakterler (karıştırılmış karakterler dahil)| foreground_color | Renk|
| Vurgu rengi | Vurgulanan kutu kenarlığını SABITLE <br> Lerinin |accent_color | Renk |
| Uygulama logosu | Intune uygulama PIN ekranında görüntülenen büyük simge | logo_image | Çizilebilir |

## <a name="default-enrollment-optional"></a>Varsayılan kayıt (isteğe bağlı)
Aşağıda, bir otomatik APP-WE hizmeti kaydı için uygulama başlatma konusunda Kullanıcı istemi gerektirme (Bu bölümde bu **varsayılan kaydı** çağırıyoruz), Intune uygulama koruma Ilkelerini yalnızca Intune korumalı kullanıcıların kullanmasına izin vermek için gerekli olan yönergeler verilmiştir. SDK ile tümleşik Android LOB uygulaması. Ayrıca, SDK ile tümleşik Android LOB uygulamanız için SSO 'yu nasıl etkinleştireceğinizi de ele alır. Bu, Intune olmayan kullanıcılar tarafından kullanılabilecek Mağaza uygulamaları **için desteklenmez.**

> [!NOTE] 
> **Varsayılan kayıt** 'nin avantajları, cihazdaki bir uygulama için App-we hizmetinden ilke almanın basitleştirilmiş bir yöntemini içerir.

> [!NOTE] 
> **Varsayılan kayıt** , bulut farkınındır.

Aşağıdaki adımlarla varsayılan kaydı etkinleştirin:

1. Uygulamanız ADAL 'yi tümleştirirse veya SSO 'yu etkinleştirmeniz gerekiyorsa, [ortak adal yapılandırma](#common-adal-configurations) #2 takıp eden [adal 'ı yapılandırın](#configure-azure-active-directory-authentication-library-adal) . Aksi takdirde, bu adımı atlayabilirsiniz.
   
2. Bildirime aşağıdaki değeri koyarak varsayılan kaydı etkinleştirin:
   ```xml 
   <meta-data android:name="com.microsoft.intune.mam.DefaultMAMServiceEnrollment" android:value="true" />
   ```
   > [!NOTE] 
   > Bu, uygulamada tek MAM-WE tümleştirmesi olmalıdır. MAMEnrollmentManager API 'Lerini çağırmaya yönelik başka bir girişim varsa, çakışmalar oluşur.

3. Bildirime aşağıdaki değeri koyarak gerekli MAM ilkesini etkinleştirin:
   ```xml 
   <meta-data android:name="com.microsoft.intune.mam.MAMPolicyRequired" android:value="true" />
   ```
   > [!NOTE] 
   > Bu, kullanıcıyı cihazdaki Şirket Portalı indirmeye ve kullanılmadan önce varsayılan kayıt akışını tamamlamaya zorlar.

## <a name="limitations"></a>Sınırlamalar

### <a name="policy-enforcement-limitations"></a>İlke zorlama sınırlamaları

* **Içerik çözümleyiciler kullanma**: "aktarma veya alma" Intune ilkesi, başka bir uygulamadaki içerik sağlayıcısına erişmek için bir içerik Çözümleyicisinin kullanımını engelleyebilir veya kısmen engelleyebilir. Bu, `ContentResolver` yöntemlerinin null döndürmesine veya bir hata değeri oluşturmasına neden olur (örneğin, `openOutputStream`, engellenirse @no__t 2 ' yi oluşturur). Uygulama, bir içerik Çözümleyicisi aracılığıyla veri yazma hatası olup olmadığını, çağrı yaparak ilkenin (ya da ilkeden kaynaklanmasından kaynaklanan) nasıl kaynaklanabileceğini belirleyebilir:

    ```java
    MAMPolicyManager.getPolicy(currentActivity).getIsSaveToLocationAllowed(contentURI);
    ```

    ya da ilişkili etkinlik yoksa:

    ```java
    MAMPolicyManager.getPolicy().getIsSaveToLocationAllowed(contentURI);
    ```

    Bu ikinci durumda, çoklu kimlik uygulamalarının iş parçacığı kimliğini uygun şekilde ayarlaması gerekir (veya `getPolicy` çağrısına açık bir kimlik geçirebilir).

### <a name="exported-services"></a>Aktarılmış hizmetler
Intune uygulama SDK 'sında bulunan AndroidManifest. xml dosyası, Şirket Portalı yönetilen bir uygulamaya bildirim göndermesini sağlamak için verilen bir hizmet olması gereken **mamnotificationreceiverservice öğesini**içerir. Hizmet, yalnızca Şirket Portalı bildirim gönderme izni verilmesini sağlamak için çağrıyı denetler.

### <a name="reflection-limitations"></a>Yansıma sınırlamaları
MAM temel sınıflarından bazıları (örneğin, `MAMActivity`, `MAMDocumentsProvider`), yalnızca belirli API düzeylerinde bulunan parametre veya dönüş türleri kullanan Yöntemler (özgün Android taban sınıflarına göre) içerir. Bu nedenle, uygulama bileşenlerinin tüm yöntemlerini numaralandırmak için her zaman yansıma kullanılması mümkün olmayabilir. Bu kısıtlama, MAM ile sınırlı değildir, uygulamanın kendisi de Android temel sınıflarından bu yöntemleri uyguladıklarında uygulanacak kısıtlamadır.

### <a name="robolectric"></a>Robolectric
Robolectric altında MAM SDK davranışının test edilmesi desteklenmez. Gerçek cihazlarda veya öykünücülere doğru şekilde benzemez Robolectric altında bulunan davranışlar nedeniyle, Robolectric altında MAM SDK çalıştıran bilinen sorunlar vardır.

Uygulamanızı Robolectric altında test etmeniz gerekiyorsa, önerilen geçici çözüm, uygulama sınıfı mantığınızı bir yardımcıya taşımak ve birim testi APK 'nizi, Mamappler 'dan kalıtımla almayan bir uygulama sınıfıyla üretmeniz gerekir.

## <a name="expectations-of-the-sdk-consumer"></a>SDK tüketicisinin beklentileri
Intune SDK 'sı, Android API 'SI tarafından sunulan sözleşmeyi korur, ancak bu durum, ilke zorlaması nedeniyle hata koşulları daha sık tetiklenebilir. Bu Android en iyi uygulamaları, hata olasılığını azaltır:

* Null döndüreolabilecek Android SDK işlevlerin şimdi null olma olasılığı daha yüksektir.  Sorunları en aza indirmek için null denetimlerinin doğru yerlerde olduğundan emin olun.

* Denetlenecek özellikler, MAM değiştirme API 'Leri aracılığıyla denetlenmelidir.

* Tüm türetilmiş işlevler, süper sınıf sürümlerine çağrı sağlamalıdır.

* Herhangi bir API 'YI belirsiz bir şekilde kullanmaktan kaçının. Örneğin, requestCode denetlenmeden `Activity.startActivityForResult` kullanmak garip davranışlara neden olur.

## <a name="telemetry"></a>Telemetri

Android için Intune uygulama SDK 'Sı, uygulamanızdan veri toplamayı denetlemez. Şirket Portalı uygulama, varsayılan olarak sistem tarafından oluşturulan verileri günlüğe kaydeder. Bu veriler Microsoft Intune gönderilir. Microsoft Ilkesi gereğince, kişisel veri toplamayız.

> [!NOTE]
> Son kullanıcılar bu verileri göndermemeyi seçiyorlarsa, Şirket Portalı uygulamasındaki ayarlar altında Telemetriyi kapatması gerekir. Daha fazla bilgi için bkz. [Microsoft kullanım verilerini toplamayı kapatma](https://docs.microsoft.com/intune-user-help/turn-off-microsoft-usage-data-collection-android). 

## <a name="recommended-android-best-practices"></a>Önerilen Android en iyi uygulamaları

* Tüm kitaplık projeleri, mümkün olduğunda aynı Android: Package öğesini paylaşmalıdır. Bu, çalışma zamanında çapraz bir şekilde başarısız olmaz; Bu yalnızca bir derleme zamanı sorunudur. Intune uygulama SDK 'sının daha yeni sürümleri, bazı yedekliliği kaldırır.

* En yeni Android SDK derleme araçlarını kullanın.

* Tüm gereksiz ve kullanılmayan kitaplıkları kaldırın (örneğin, Android. support. v4)

## <a name="testing"></a>Test Etme
Bkz. [Test Kılavuzu](app-sdk-android-testing-guide.md).
