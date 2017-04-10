---
title: "Android uygulamalarını Uygulama Sarmalama Aracı’yla sarmalama | Microsoft Docs"
description: "Android uygulamalarınızı, uygulamanın kendi kodunda değişiklik yapmadan sarmalamayı öğrenmek için bu makaledeki bilgileri kullanın. Mobil uygulama yönetimi ilkelerini uygulayabilmek için uygulamaları hazırlayın."
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: oldang
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f46f13e9dbf03fa2b3e2ec7339cad927ea0b38e0
ms.openlocfilehash: 9a9899e192db1488c9a2c0fd38ffed6cef625c34


---

# <a name="prepare-android-apps-for-mobile-application-management-with-the-intune-app-wrapping-tool"></a>Android uygulamalarını Intune Uygulama Sarmalama Aracı ile mobil uygulama yönetimi için hazırlama

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Şirket içi Android uygulamalarınızın davranışını, uygulamanın kodunu değiştirmeden uygulama özelliklerini kısıtlayarak değiştirmek için Android için Microsoft Intune Uygulama Sarmalama Aracı'nı kullanın.

Bu araç, PowerShell’de çalışan ve Android uygulamanızın etrafında sarmalayıcı oluşturan bir Windows komut satırı uygulamasıdır. Uygulama sarmalandıktan sonra, Intune’daki [mobil uygulama yönetimi ilkelerini](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) yapılandırarak uygulamanın işlevini değiştirebilirsiniz.


Aracı çalıştırmadan önce bkz. [Uygulama Sarmalama Aracını çalıştırmaya ilişkin güvenlik konuları](#security-considerations-for-running-the-app-wrapping-tool). Aracı indirmek için GitHub’daki [Android için Microsoft Intune Uygulama Sarmalama Aracı](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android)’na gidin.



## <a name="fulfill-the-prerequisites-for-using-the-app-wrapping-tool"></a>Uygulama Sarmalama Aracını kullanmak için önkoşulları karşılama

-   Windows 7 veya sonraki sürümlerini çalıştıran bir Windows bilgisayarda Uygulama Sarmalama Aracını çalıştırmanız gerekir.

-   Giriş uygulamanız, .apk dosya uzantısıyla geçerli bir Android uygulama paketi olmalıdır ve:

    -   Şifreli olamaz.
    -   Intune Uygulama Sarmalama Aracı tarafından önceden sarmalanmamış olmalıdır.
    -   Android 4.0 veya sonraki sürümler için yazılmış olmalıdır.

-   Uygulama, şirketiniz tarafından veya şirketiniz için geliştirilmiş olmalıdır. Bu aracı Google Play Store’dan indirilen uygulamalarda kullanamazsınız.

-   Uygulama Sarmalama Aracını çalıştırmak için en son [Java Çalışma Zamanı Ortamı](http://java.com/download/) sürümünü yüklemeniz ve ardından Windows ortam değişkenlerinizdeki Java yolu değişkeninin C:\ProgramData\Oracle\Java\javapath olarak ayarlandığından emin olmanız gerekir. Daha fazla yardım için bkz. [Java belgeleri](http://java.com/download/help/).

    > [!NOTE]
    > Bazı durumlarda, Java’nın 32 bit sürümü bellek sorunlarına yol açabilir. 64-bit sürümü yüklemek iyi bir fikirdir.

- Android tüm uygulama paketlerinin (.apk) imzalanmasını gerektirir. Sarmalanan çıkış uygulamasını imzalamak amacıyla gerekli kimlik bilgilerini oluşturmak için Java keytool kullanın. Örneğin, aşağıdaki komut, Uygulama Sarmalama Aracı tarafından sarmalanan çıkış uygulamasını imzalamak için kullanılabilecek anahtarlar oluşturmak için Java yürütülebilir keytool.exe dosyası kullanır.

    ```
    keytool.exe -genkeypair -v -keystore mykeystorefile -alias mykeyalias -keyalg RSA -keysize 2048 -validity 50000
    ```
    Bu örnek, RSA algoritması kullanarak bir anahtar çifti (bir ortak anahtar ve 2048 bit ilişkili özel anahtar) oluşturur. Ardından ortak anahtarı, tek öğeli sertifika zinciri olarak depolanan bir X.509 v3 otomatik imzalanan sertifika içine sarmalar. Bu sertifika zinciri ve özel anahtar "mykeystorefile" adlı yeni bir anahtar deposu girdisinde depolanır ve "mykeyalias" diğer adıyla tanımlanır. Anahtar deposu girdisi 50.000 gün boyunca geçerlidir.

    Komut, anahtar deposu ve anahtar için parola sağlamanızı ister. Güvenli parolalar kullanın, ancak daha sonra Uygulama Sarmalama Aracını çalıştırmak için gerekeceğinden, bu parolaları not alın.

    Daha ayrıntılı belgeler için Oracle belgeleri web sitesinde Java [keytool](http://docs.oracle.com/javase/6/docs/technotes/tools/windows/keytool.html) ve Java [KeyStore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) hakkında okuma yapabilirsiniz.

## <a name="install-the-app-wrapping-tool"></a>Uygulama Sarmalama Aracını yükleme

1.  [GitHub deposundan](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android), Android için Intune Uygulama Sarmalama Aracı’na yönelik InstallAWT.exe yükleme dosyasını bir Windows bilgisayara indirin. Yükleme dosyasını açın.

2.  Lisans sözleşmesini kabul edip, yüklemeyi tamamlayın.

Aracı yüklediğiniz klasörü not edin. Varsayılan konum: C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool.

## <a name="run-the-app-wrapping-tool"></a>Uygulama Sarmalama Aracını çalıştırma

1.  Uygulama Sarmalama Aracını yüklediğiniz Windows bilgisayarda, yönetici modunda bir PowerShell penceresi açın.

2.  Aracı yüklediğiniz klasörden Uygulama Sarmalama Aracı PowerShell modülünü içeri aktarın:

    ```
    Import-Module .\IntuneAppWrappingTool.psm1
    ```

3.  Aşağıdaki kullanım söz dizimine sahip **invoke-AppWrappingTool** komutunu kullanarak aracı çalıştırın:
    ```
    Invoke-AppWrappingTool [-InputPath] <String> [-OutputPath] <String> -KeyStorePath <String> -KeyStorePassword <SecureString>
    -KeyAlias <String> -KeyPassword <SecureString> [-SigAlg <String>] [<CommonParameters>]
    ```

 Aşağıdaki tabloda **invoke-AppWrappingTool** komutunun özelliklerine ilişkin ayrıntılar verilmiştir:

|Özellik|Bilgiler|Örnek|
|-------------|--------------------|---------|
|**-InputPath**&lt;Dize&gt;|Kaynak Android uygulamasının (.apk) yolu.| |
|**-OutputPath**&lt;Dize&gt;|Çıktı Android uygulamasının yolu. Bu dizin yolu InputPath ile aynıysa paket oluşturma başarısız olur.| |
|**-KeyStorePath**&lt;Dize&gt;|İmzalama için ortak/özel anahtar çiftini içeren anahtar deposu dosyasının yolu.|Varsayılan olarak anahtar deposu dosyaları "C:\Program Files (x86)\Java\jreX.X.X_XX\bin" konumunda saklanır. |
|**-KeyStorePassword**&lt;GüvenliDize&gt;|Anahtar deposunun şifresini çözmek için kullanılan parola. Android, tüm uygulama paketlerinin (.apk) imzalanmasını gerektirir. KeyStorePassword üretmek için Java keytool kullanın. Java [KeyStore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) hakkında daha fazla bilgiyi burada bulabilirsiniz.| |
|**-KeyAlias**&lt;Dize&gt;|İmzalama için kullanılacak anahtarın adı.| |
|**-KeyPassword**&lt;GüvenliDize&gt;|İmzalama için kullanılan özel anahtarın şifresini çözmek için kullanılan parola.| |
|**-SigAlg**&lt;GüvenliDize&gt;| (İsteğe bağlı) İmzalama için kullanan imza algoritmasının adı. Algoritma, özel anahtar ile uyumlu olmalıdır.|Örnekler: SHA256withRSA, SHA1withRSA, MD5withRSA|
| **&lt;CommonParameters&gt;** | (İsteğe bağlı) Komut, ayrıntılı ve hata ayıklama gibi ortak PowerShell parametrelerini destekler. |


- Ortak parametrelerin listesi için bkz. [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx).

- Araca yönelik ayrıntılı kullanım bilgilerini görmek için komutu girin:

    ```
    Help Invoke-AppWrappingTool
    ```

**Örnek:**

PowerShell modülünü içeri aktarın.
```
Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
```
Uygulama Sarmalama Aracını HelloWorld.apk yerel uygulamasında çalıştırın.
```
invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app_wrapped\HelloWorld_wrapped.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\mykeystorefile" -keyAlias mykeyalias -SigAlg SHA1withRSA -Verbose
```

Daha sonra sizden **KeyStorePassword** ve **KeyPassword**istenir. Anahtar depolama dosyası oluşturmak için kullandığınız kimlik bilgilerini girin.

Sarmalanan uygulama ve günlük dosyası oluşturulur ve belirttiğiniz çıkış yoluna kaydedilir.

## <a name="security-considerations-for-running-the-app-wrapping-tool"></a>Uygulama Sarmalama Aracını çalıştırmaya ilişkin güvenlik konuları
Olası yanıltma, bilgi ifşası ve ayrıcalıkların yükseltilmesi saldırılarını önlemek için:

-   Giriş iş kolu (LOB) uygulamasının, çıkış uygulamasının ve Java KeyStore’un Uygulama Sarmalama Aracının çalıştığı aynı Windows bilgisayarında olduğundan emin olun.

-   Çıkış uygulamasını, aracın çalıştığı aynı makinede Intune konsoluna aktarın. Java keytool hakkında daha fazla bilgi için bkz. [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html).

-   Çıkış uygulaması ve araç, Evrensel Adlandırma Kuralı (UNC) yolundaysa ve aracı ve giriş dosyalarını aynı bilgisayarda çalıştırmıyorsanız, [İnternet Protokolü Güvenliği (IPsec)](http://en.wikipedia.org/wiki/IPsec) veya [Sunucu İleti Bloğu (SMB) imzalamayı](https://support.microsoft.com/en-us/kb/887429)kullanarak ortamı güvenli olacak şekilde ayarlayın.

-   Uygulamanın güvenilir bir kaynaktan geldiğine emin olun.

-   Sarmalanan uygulamayı içeren çıkış dizinini güvenli hale getirin. Çıkış için kullanıcı düzeyinde bir dizin kullanın.

### <a name="see-also"></a>Ayrıca bkz.
- [Microsoft Intune ile uygulamaların mobil uygulama yönetimi için nasıl hazırlanacağına karar verme](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)

- [SDK’yı kullanarak uygulamaları mobil uygulama yönetimi için etkinleştirme](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Dec16_HO3-->


