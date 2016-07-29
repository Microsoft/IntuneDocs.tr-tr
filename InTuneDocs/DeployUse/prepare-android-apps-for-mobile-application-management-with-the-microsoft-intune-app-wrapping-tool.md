---
title: "Android uygulamalarını Uygulama Sarmalama Aracı’yla sarmalama | Microsoft Intune"
description: "Android uygulamalarınızı, uygulamanın kendi kodunda değişiklik yapmadan sarmalamayı öğrenmek için bu konu başlığı altındaki bilgileri kullanın. Mobil uygulama yönetimi ilkelerini uygulayabilmek için uygulamaları hazırlayın."
keywords: 
author: karthikaraman
manager: arob98
ms.date: 07/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: matgates
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2038ed6219a94dc4285891d71ce00fd51310f3e3
ms.openlocfilehash: 15d0877f799c89e2a8af65c416c0e914f898641f


---

# Android uygulamalarını Intune Uygulama Sarmalama Aracı ile mobil uygulama yönetimi için hazırlama
Şirket içi Android uygulamalarınızın davranışını, uygulamanın kodunu değiştirmeden uygulama özelliklerini yapılandırmanıza izin verecek şekilde değiştirmek için **Android için Microsoft Intune Uygulaması Sarmalama Aracı**'nı kullanın.

Bu araç, PowerShell’de çalışan ve uygulamanızın etrafında 'sarmalayıcı' oluşturan bir Windows komut satırı uygulamasıdır. Uygulama işlendikten sonra, yapılandırdığınız [mobil uygulama yönetimi ilkelerini](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) kullanarak uygulamanın işlevini değiştirebilirsiniz.

Uygulamanız Azure Active Directory Authentication Library (ADAL) kullanıyorsa, uygulamanızı sarmalamadan önce [Azure Active Directory Authentication Library kullanan uygulamaları sarmalama](#how-to-wrap-apps-that-use-the-azure-active-directory-library) bölümündeki adımları tamamlamanız gerekir. Uygulamanızın bu kitaplığı kullanıp kullanmadığından emin değilseniz, uygulamanın geliştiricisine başvurun.

Aracı çalıştırmadan önce bkz. [Uygulama sarmalama aracını çalıştırmaya ilişkin güvenlik konuları](#security-considerations-for-running-the-app-wrapping-tool). Aracı indirmek için bkz. [Android için Microsoft Intune Uygulama Sarmalama Aracı](https://www.microsoft.com/download/details.aspx?id=47267).

## 1. Adım Uygulama sarmalama aracını kullanmak için önkoşulları karşılama

-   Windows 7 veya sonraki sürümlerini çalıştıran bir Windows bilgisayarda uygulama sarmalama aracını çalıştırmanız gerekir.

-   Giriş uygulamanız, **.apk** uzantısıyla geçerli bir Android uygulama paketi olmalıdır ve:

    -   Şifrelenemez

    -   Uygulama sarmalama aracı tarafından önceden sarmalanmamış olmalıdır

    -   Android 4.0 veya sonraki sürümler için yazılmış olmalıdır

-   Uygulama, şirketiniz tarafından veya şirketiniz için geliştirilmiş olmalıdır. Bu aracı Google Play Mağazası’ndan indirilen uygulamaları işlemek için kullanamazsınız.

-   Uygulama sarmalama aracını çalıştırmak için en son [Java Çalışma Zamanı Ortamı](http://java.com/download/) sürümünü yüklemeniz ve ardından Windows ortam değişkenlerinizdeki Java yolu değişkeninin **C:\ProgramData\Oracle\Java\javapath** olarak ayarlandığından emin olmanız gerekir. Daha fazla yardım için bkz. [Java belgeleri](http://java.com/download/help/).

    > [!NOTE]
    > Bazı durumlarda, Java’nın 32 bit sürümü bellek sorunlarına yol açabilir. Bunun yerine 64 bit sürümü yüklemenizi öneririz.

## 2. Adım Uygulama sarmalama aracını yükleme

1.  Microsoft İndirme Merkezi’nden uygulama sarmalama aracı için yükleme dosyasını bir Windows bilgisayara indirip açın.

2.  Lisans sözleşmesini kabul, sonra yüklemeyi tamamlayın.

Aracı yüklediğiniz klasörü not edin. Varsayılan konum: **C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**.

## 3. Adım Uygulama sarmalama aracını çalıştırma

1.  Uygulama sarmalama aracını yüklediğiniz Windows bilgisayarda, yönetici modunda bir PowerShell penceresi açın.

2.  Aracı yüklediğiniz klasörden uygulama sarmalama aracı PowerShell modülünü içeri aktarın:

    ```
    Import-Module .\IntuneAppWrappingTool.psm1
    ```

3.  **Invoke-AppWrappingTool** komutunu şu parametrelerden biriyle birlikte kullanarak aracı çalıştırın: "İsteğe bağlı" olarak işaretlenmiş parametreler, Azure Active Directory Authentication Library (ADAL) kullanan uygulamalar içindir. Daha fazla bilgi için bkz. [Azure Active Directory Authentication Library kullanan uygulamaları sarmalama](#how-to-wrap-apps-that-use-the-azure-active-directory-library).

|Parametre|Daha fazla bilgi|Örnekler|
|-------------|--------------------|---------|
|**-InputPath**&lt;Dize&gt;|Kaynak Android uygulamasının (.apk) yolu.| |
|**-OutputPath**&lt;Dize&gt;|"Çıktı" Android uygulamasının yolu. Bu dizin yolu InputPath ile aynıysa paket oluşturma başarısız olur.| |
|**-KeyStorePath**&lt;Dize&gt;|İmzalama için ortak/özel anahtar çiftini içeren anahtar deposu dosyasının yolu.| |
|**-KeyStorePassword**&lt;GüvenliDize&gt;|Anahtar deposunun şifresini çözmek için kullanılan parola. Android, tüm uygulama paketlerinin (.apk) imzalanmasını gerektirir. Örnekte gösterildiği gibi KeyStorePassword üretmek için Java Key Tool’u kullanın. [Anahtar deposu](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) hakkında daha fazla bilgi edinin.|keytool.exe -genkey -v -keystore keystorefile -alias ks -keyalg RSA -keysize 2048 -validity 50000 |
|**-KeyAlias**&lt;Dize&gt;|İmzalama için kullanılacak anahtarın adı.| |
|**-KeyPassword**&lt;GüvenliDize&gt;|İmzalama için kullanılan özel anahtarın şifresini çözmek için kullanılan parola.| |
|**-SigAlg**&lt;GüvenliDize&gt;|İmzalama için kullanan imza algoritmasının adı. Algoritma, özel anahtar ile uyumlu olmalıdır.|Örnekler: SHA256withRSA, SHA1withRSA, MD5withRSA|
|**-ClientID**&lt;GUID&gt;|Giriş uygulamasının Azure Active Directory İstemci Kimliği (isteğe bağlı).| |
|**-AuthorityURI**&lt;Uri&gt;|Giriş uygulamasının Azure Active Directory Yetkili URI’si (isteğe bağlı).| |
|**-SkipBroker**&lt;Boole&gt;|Giriş uygulamasının cihaz genelinde aracılık edilen çoklu oturum açmayı destekleyip desteklemediğini belirtir (isteğe bağlı). |**True** - Giriş uygulaması cihaz genelinde aracılık edilen çoklu oturum açmayı desteklemiyor. NonBrokerRedirectURI parametresini kullanın. **False** - Giriş uygulaması cihaz genelinde aracılık edilen çoklu oturum açmayı destekliyor.|
|**-NonBrokerRedirectURI**&lt;URI&gt;|SkipBroker değeri true ise kullanılacak Azure Active Directory Yeniden Yönlendirme URI'si (isteğe bağlı).|  |


**&lt;CommonParameters&gt;**
    (isteğe bağlı – ayrıntı, hata ayıklama vb. gibi ortak PowerShell parametrelerini destekler)

- Ortak parametrelerin listesi için bkz. [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx).

- Araç yardımını görmek için komutu girin:

    ```
    Help Invoke-AppWrappingTool
    ```
- Azure Active Directory (AAD) tümleştirmesi hakkında daha fazlasını öğrenmek için, bkz. [Azure Active Directory kitaplığını kullanan uygulamaları sarmalama](#how-to-wrap-apps-that-use-the-azure-active-directory-library).

**Örnek:**


    Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
    invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app.wrapped\HelloWorld_wrapped2.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\keystorefile" -keyAlias ks -SigAlg SHA1withRSA -Verbose

Daha sonra sizden **KeyStorePassword** ve **KeyPassword**istenir.

Sarmalanan uygulama oluşturulur ve belirttiğiniz çıkış yoluna bir günlük dosyasıyla birlikte kaydedilir.

## Uygulama sarmalama aracını çalıştırmaya ilişkin güvenlik konuları
Olası yanıltma, bilgi ifşası ve ayrıcalıkların yükseltilmesi saldırılarını önlemek için:

-   Giriş iş kolu uygulamasının, çıkış uygulamasının ve Java KeyStore’un, uygulama sarmalama aracının çalıştığı aynı bilgisayarda olduğundan emin olun.

-   Çıkış uygulamasını, aracın çalıştığı aynı bilgisayarda Intune konsoluna aktarın. Java keytool hakkında daha fazla bilgi için bkz. [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html).

-   Çıkış uygulaması ve araç, Evrensel Adlandırma Kuralı (UNC) yolundaysa ve aracı ve giriş dosyalarını aynı bilgisayarda çalıştırmıyorsanız, [İnternet Protokolü Güvenliği (IPsec)](http://en.wikipedia.org/wiki/IPsec) veya [Sunucu İleti Bloğu (SMB) imzalamayı](https://support.microsoft.com/en-us/kb/887429)kullanarak ortamı güvenli olacak şekilde yapılandırın.

-   Özellikle de uygulamanın çalışma zamanı sırasında AAD belirtecine erişmesini sağlayabilecek Azure Active Directory’yi (AAD) kullanıyorsanız, uygulamanın güvenilir bir kaynaktan geldiğinden emin olun.

-   Sarmalanan uygulamayı içeren çıkış dizinini güvenli hale getirin. Çıkış için kullanıcı düzeyinde bir dizin kullanın.

## Azure Active Directory Authentication Library kullanan uygulamaları sarmalama
Uygulamanız Azure Active Directory Authentication Library (ADAL) kullanıyorsa, uygulamanızı sarmalamadan önce bu adımları tamamlamanız gerekir.

### 1. Adım ADAL gereksinimlerini karşıladığınızdan emin olma
ADAL kullanan uygulamalar için aşağıdakilerin doğru olması gerekir:

-   Uygulama, 1.0.2 veya üzeri bir ADAL sürümü içermelidir.

-   Geliştirici, [3. Adım AAD’de mobil uygulama yönetimine erişimi yapılandırma](#step-3-configure-access-to-mobile-app-management-in-aad) başlığı altında açıklandığı gibi, kendi uygulama erişimini Intune Mobil Uygulama Yönetimi kaynağına vermelidir.

### 2. Adım Uygulamanızı kaydederken almanız gereken tanımlayıcıları gözden geçirme
Sıradaki adımda, aşağıdaki tabloda listelenen benzersiz tanımlayıcıları almak için Azure yönetim portalını kullanarak uygulamalarınızı (Azure Active Directory (AAD) ile ADAL kullanan uygulamaları) kaydedeceksiniz. Daha sonra, ADAL’ı uygulamayla tümleştirirken tanımlayıcıları geliştiriciye verirsiniz.

|Tanımlayıcı|Daha fazla bilgi|Varsayılan değer|
|--------------|--------------------|-----------------|
|**İstemci Kimliği**|Uygulama AAD’ye kaydedildikten sonra uygulama için oluşturulan benzersiz bir GUID tanımlayıcısı.<br /><br />Uygulamanın istemci kimliğini biliyorsanız, değerini belirtin. Aksi takdirde, varsayılan değeri kullanın.|6c7e8096-f593-4d72-807f-a5f86dcc9c77|
|**Yetkili URI’si**|AAD nesneleri (örneğin, kullanıcılar ve gruplar) için yetkili Tekdüzen Kaynak Tanımlayıcısı (URI) değeri.<br /><br />Uygulama sarmalama aracı için AuthorityURI parametresi isteğe bağlıdır. Parametreyi kullanmazsanız varsayılan URI kullanılır.||
|**SkipBroker**|Şirket portalının bir aracı olarak kullanılıp kullanılmayacağını belirten değer.<br /><br />**True** – Şirket portalı ADAL kimlik doğrulaması için kullanılmaz.<br /><br />**False** – Şirket portalı ADAL kimlik doğrulaması için kullanılır. Şirket portalı, Çoklu Oturum Açma amacıyla kayıtlı kullanıcıyı kullanıyor.||
|**Aracı Olmayan Yeniden Yönlendirme URI'si**|ADAL tarafından aracı uygulaması kullanılmadığında kullanılacak oturum açma URI’si (Intune şirket portalı).|urn:ietf:wg:oauth:2.0:oob|
|**Kaynak Kimliği**|Uygulamanın AAD kaynaklarına yönelik işaretçi.||

### 3. Adım AAD'de mobil uygulama yönetimine erişimi yapılandırma
Bir uygulamanın AAD kayıt değerlerini uygulama sarmalama aracında kullanabilmeniz için, önce uygulama geliştiricisinin aşağıdaki adımları izleyerek bu uygulamaya Intune Mobil Uygulama Yönetimi kaynağına erişim izni vermesi gerekir:

1.  Azure Yönetim Portalı'nda mevcut bir AAD hesabıyla oturum açın.

2.  **Mevcut iş kolu uygulaması kaydını** seçin.

3.  **Yapılandır** bölümünde, **Diğer uygulamalardaki Web API'lerine Erişimi Yapılandır**'ı seçin.

4.  **Diğer uygulamalara yönelik izinler** bölümündeki ilk açılan listeden **Intune Mobil Uygulama Yönetimi**'ni seçin.

Artık uygulama sarmalama aracında uygulamanın İstemci Kimliğini kullanabilirsiniz. İstemci Kimliğini, [2. Adım Uygulamanızı kaydederken almanız gereken tanımlayıcıları gözden geçirme](#step-2-review-the-identifiers-you-need-to-get-when-you-register-the-app) altındaki tabloda açıklandığı gibi, Azure Active Directory yönetim portalında bulabilirsiniz.

### 4. Adım Uygulama sarmalama aracında AAD tanımlayıcı değerlerini kullanma
Kayıt işleminden aldığınız tanımlayıcı değerlerini kullanarak, bu değerleri uygulama sarmalama aracında komut satırı özellikleri olarak girin. Son kullanıcıların uygulamanın kimlik doğrulamasını başarılı bir şekilde gerçekleştirebilmesi için tablodaki tüm değerleri belirtmelisiniz. Bir değer belirtmezseniz varsayılan değerler kullanılır.

|Tanımlayıcı|Parametre|
|--------------|-------------|
|İstemci Kimliği|İstemci Kimliği|
|Yetkili URI’si|Yetkili URI’si|
|SkipBroker|SkipBroker|
|Aracı Olmayan Yeniden Yönlendirme URI'si|NonBrokerRedirectURI|
|Kaynak Kimliği|ResourceID|
Uygulamanızı sarmalarken şu noktaları dikkate alın:

-   [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], kimlik doğrulamasının başarılı olduğunu doğrulamak için MAM kaynak kimliği ile ilişkili AAD belirtecini getirir. Ancak belirteç, belirtecin geçerliliğini doğrulayacak herhangi bir çağrıda kullanılmaz. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Uygulama erişimini belirlemek için yalnızca oturum açmış olan kullanıcının asıl adını (UPN) okur. AAD belirteci diğer hizmet çağrıları için kullanılmaz.

-   İstemci uygulamanızın İstemci Kimliğini ve Yetkili URI'sini sağlarsanız çifte oturum açma istekleri engellenir. AAD Panosu'nda yayımlanan [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] MAM kaynak kimliğine erişimini etkinleştirmek için İstemci Kimliği’ni kaydetmeniz gerekir. İstemci kimliğini kaydetmezseniz, uygulama çalıştığında kullanıcılar bir oturum açma hatası alır.


### Ayrıca bkz.
- [Microsoft Intune ile uygulamaların mobil uygulama yönetimi için nasıl hazırlanacağına karar verme](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)

- [SDK’yı kullanarak uygulamaları mobil uygulama yönetimi için etkinleştirme](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Jul16_HO4-->


