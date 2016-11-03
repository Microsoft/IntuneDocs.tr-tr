---
title: "Android uygulamalarını Uygulama Sarmalama Aracı’yla sarmalama | Microsoft Intune"
description: "Android uygulamalarınızı, uygulamanın kendi kodunda değişiklik yapmadan sarmalamayı öğrenmek için bu konu başlığı altındaki bilgileri kullanın. Mobil uygulama yönetimi ilkelerini uygulayabilmek için uygulamaları hazırlayın."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: fe3a9f2fd9ce9a3c3f776dcfd9ad3347a63d0fc1
ms.openlocfilehash: e623755cf926020bcb66d8a6d40e5cce9b46b0ae


---

# Android uygulamalarını Intune Uygulama Sarmalama Aracı ile mobil uygulama yönetimi için hazırlama
Şirket içi Android uygulamalarınızın davranışını, uygulamanın kodunu değiştirmeden uygulama özelliklerini kısıtlayarak değiştirmek için **Android için Microsoft Intune Uygulama Sarmalama Aracı**'nı kullanın.

Bu araç, PowerShell’de çalışan ve Android uygulamanızın etrafında 'sarmalayıcı' oluşturan bir Windows komut satırı uygulamasıdır. Uygulama sarmalandıktan sonra, Intune’daki [mobil uygulama yönetimi ilkelerini](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) yapılandırarak uygulamanın işlevini değiştirebilirsiniz.


Aracı çalıştırmadan önce bkz. [Uygulama sarmalama aracını çalıştırmaya ilişkin güvenlik konuları](#security-considerations-for-running-the-app-wrapping-tool). Aracı indirmek için GitHub’da [Android için Microsoft Intune Uygulama Sarmalama Aracı](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android)’nı ziyaret edin.



## 1. Adım Uygulama sarmalama aracını kullanmak için önkoşulları karşılama

-   Windows 7 veya sonraki sürümlerini çalıştıran bir Windows bilgisayarda uygulama sarmalama aracını çalıştırmanız gerekir.

-   Giriş uygulamanız, **.apk** dosya uzantısıyla geçerli bir Android uygulama paketi olmalıdır ve:

    -   Şifrelenemez

    -   Intune Uygulama Sarmalama Aracı tarafından önceden sarmalanmamış olmalıdır
    -   Android 4.0 veya sonraki sürümler için yazılmış olmalıdır

-   Uygulama, şirketiniz tarafından veya şirketiniz için geliştirilmiş olmalıdır. Bu aracı Google Play Store’dan indirilen uygulamalarda kullanamazsınız.

-   Uygulama sarmalama aracını çalıştırmak için en son [Java Çalışma Zamanı Ortamı](http://java.com/download/) sürümünü yüklemeniz ve ardından Windows ortam değişkenlerinizdeki Java yolu değişkeninin **C:\ProgramData\Oracle\Java\javapath** olarak ayarlandığından emin olmanız gerekir. Daha fazla yardım için bkz. [Java belgeleri](http://java.com/download/help/).

    > [!NOTE]
    > Bazı durumlarda, Java’nın 32 bit sürümü bellek sorunlarına yol açabilir. Bunun yerine 64 bit sürümü yüklemenizi öneririz.

- Android tüm uygulama paketlerinin (.apks) imzalanmasını gerektirir. Sarmalanan çıkış uygulamasını imzalamak amacıyla gerekli kimlik bilgilerini oluşturmak için Java Key Tool’u kullanın. Örneğin, aşağıdaki komut, uygulama sarmalama aracı tarafından sarmalanan çıkış uygulamasını imzalamak için kullanılabilecek anahtarlar oluşturmak için Java yürütülebilir **keytool.exe** dosyası kullanır.

    ```
    keytool.exe -genkeypair -v -keystore mykeystorefile -alias mykeyalias -keyalg RSA -keysize 2048 -validity 50000
    ```
    Bu örnek, RSA algoritması kullanan bir anahtar çifti oluşturur (bir ortak anahtar ve bununla ilişkili 2048 bit boyutlu özel anahtar) ve ardından ortak anahtarı tek öğeli sertifika zinciri olarak depolanan bir X.509 v3 otomatik olarak imzalanan sertifika içine sarmalar. Bu sertifika zinciri ve özel anahtar "mykeystorefile" adlı yeni bir anahtar deposu girdisinde depolanır ve "mykeyalias" diğer adıyla tanımlanır. Anahtar deposu girdisi 50.000 gün boyunca geçerlidir.

    Komut, anahtar deposu ve anahtar için parola sağlamanızı ister. Güvenli ve tahmin etmesi güç parolalar kullanın, ancak daha sonra uygulama sarmalama aracını çalıştırmak için gerekeceğinden, bu parolaları unutmayın.

    Daha ayrıntılı belgeler için Oracle belgeleri web sitesinde Java [keytool](http://docs.oracle.com/javase/6/docs/technotes/tools/windows/keytool.html) ve Java [KeyStore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) hakkında okuma yapabilirsiniz.

## 2. Adım: Uygulama sarmalama aracını yükleme

1.  [GitHub deposundan](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android), Android için Intune Uygulama Sarmalama Aracı’na yönelik **InstallAWT.exe** yükleme dosyasını bir Windows bilgisayarda açın.

2.  Lisans sözleşmesini kabul, sonra yüklemeyi tamamlayın.

Aracı yüklediğiniz klasörü not edin. Varsayılan konum: **C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**.

## 3. Adım Uygulama sarmalama aracını çalıştırma

1.  Uygulama sarmalama aracını yüklediğiniz Windows bilgisayarda, yönetici modunda bir PowerShell penceresi açın.

2.  Aracı yüklediğiniz klasörden uygulama sarmalama aracı PowerShell modülünü içeri aktarın:

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
|**-OutputPath**&lt;Dize&gt;|"Çıktı" Android uygulamasının yolu. Bu dizin yolu InputPath ile aynıysa paket oluşturma başarısız olur.| |
|**-KeyStorePath**&lt;Dize&gt;|İmzalama için ortak/özel anahtar çiftini içeren anahtar deposu dosyasının yolu.|Varsayılan olarak anahtar deposu dosyaları "C:\Program Files (x86)\Java\jreX.X.X_XX\bin" konumunda saklanır. |
|**-KeyStorePassword**&lt;GüvenliDize&gt;|Anahtar deposunun şifresini çözmek için kullanılan parola. Android, tüm uygulama paketlerinin (.apk) imzalanmasını gerektirir. KeyStorePassword üretmek için Java Key Tool’u kullanın. Java [anahtar deposu](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) hakkında daha fazla bilgiyi burada bulabilirsiniz.| |
|**-KeyAlias**&lt;Dize&gt;|İmzalama için kullanılacak anahtarın adı.| |
|**-KeyPassword**&lt;GüvenliDize&gt;|İmzalama için kullanılan özel anahtarın şifresini çözmek için kullanılan parola.| |
|**-SigAlg**&lt;GüvenliDize&gt;| (İsteğe bağlı) İmzalama için kullanan imza algoritmasının adı. Algoritma, özel anahtar ile uyumlu olmalıdır.|Örnekler: SHA256withRSA, SHA1withRSA, MD5withRSA|
| **&lt;CommonParameters&gt;** | (İsteğe bağlı) Komut ayrıntı, hata ayıklama vb. gibi ortak PowerShell parametrelerini destekler. |


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
Uygulama sarmalama aracını **HelloWorld.apk** yerel uygulamasında çalıştırın. 
```
invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app_wrapped\HelloWorld_wrapped.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\mykeystorefile" -keyAlias mykeyalias -SigAlg SHA1withRSA -Verbose
```

Daha sonra sizden **KeyStorePassword** ve **KeyPassword**istenir. Anahtar depolama dosyası oluşturmak için kullandığınız kimlik bilgilerini girin.

Sarmalanan uygulama oluşturulur ve belirttiğiniz çıkış yoluna bir günlük dosyasıyla birlikte kaydedilir.

## Uygulama sarmalama aracını çalıştırmaya ilişkin güvenlik konuları
Olası yanıltma, bilgi ifşası ve ayrıcalıkların yükseltilmesi saldırılarını önlemek için:

-   Giriş iş kolu (LOB) uygulamasının, çıkış uygulamasının ve Java KeyStore’un uygulama sarmalama aracının çalıştığı aynı Windows bilgisayarında olduğundan emin olun.

-   Çıkış uygulamasını, aracın çalıştığı aynı makinede Intune konsoluna aktarın. Java keytool hakkında daha fazla bilgi için bkz. [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html).

-   Çıkış uygulaması ve araç, Evrensel Adlandırma Kuralı (UNC) yolundaysa ve aracı ve giriş dosyalarını aynı bilgisayarda çalıştırmıyorsanız, [İnternet Protokolü Güvenliği (IPsec)](http://en.wikipedia.org/wiki/IPsec) veya [Sunucu İleti Bloğu (SMB) imzalamayı](https://support.microsoft.com/en-us/kb/887429)kullanarak ortamı güvenli olacak şekilde yapılandırın.

-   Uygulamanın güvenilir bir kaynaktan geldiğine emin olun.

-   Sarmalanan uygulamayı içeren çıkış dizinini güvenli hale getirin. Çıkış için kullanıcı düzeyinde bir dizin kullanın.



### Ayrıca bkz.
- [Microsoft Intune ile uygulamaların mobil uygulama yönetimi için nasıl hazırlanacağına karar verme](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)

- [SDK’yı kullanarak uygulamaları mobil uygulama yönetimi için etkinleştirme](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Oct16_HO2-->


