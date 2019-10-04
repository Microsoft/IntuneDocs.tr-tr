---
title: Android uygulamalarını Intune uygulama sarmalama aracı ile sarmalama
description: Android uygulamalarınızı, uygulamanın kodunu değiştirmeden nasıl kaydıracağınızı öğrenin. Uygulamaları, mobil uygulama yönetimi ilkelerini uygulayabilmeniz için hazırlayın.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: dfea74c70b81cadfa06c578dc33cdad401fa9e45
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940065"
---
# <a name="prepare-android-apps-for-app-protection-policies-with-the-intune-app-wrapping-tool"></a>Android uygulamalarını Intune uygulama sarmalama aracı ile uygulama koruma ilkeleri için hazırlama

Şirket içi Android uygulamalarınızın davranışını, uygulamanın kodunu değiştirmeden uygulama özelliklerini kısıtlayarak değiştirmek için Android için Microsoft Intune uygulama sarmalama aracı ' nı kullanın.

Araç, PowerShell 'de çalışan ve Android uygulamanız etrafında bir sarmalayıcı oluşturan bir Windows komut satırı uygulamasıdır. Uygulama sarmalandıktan sonra, Intune 'da [mobil uygulama yönetimi ilkelerini](../apps/app-protection-policies.md) yapılandırarak uygulamanın işlevini değiştirebilirsiniz.

Aracı çalıştırmadan önce, [Uygulama sarmalama aracını çalıştırmaya Ilişkin güvenlik konularını](#security-considerations-for-running-the-app-wrapping-tool)gözden geçirin. Aracı indirmek için GitHub 'da [Android için Microsoft Intune uygulama sarmalama aracı](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) ' na gidin.

## <a name="fulfill-the-prerequisites-for-using-the-app-wrapping-tool"></a>Uygulama sarmalama aracını kullanmak için önkoşulları yerine getirmek

- Windows 7 veya üzerini çalıştıran bir Windows bilgisayarda uygulama sarmalama aracını çalıştırmanız gerekir.

- Giriş uygulamanız,. apk dosya uzantısına sahip geçerli bir Android uygulama paketi olmalıdır ve:

  - Şifrelenemez.
  - Daha önce Intune uygulama sarmalama aracı tarafından sarmalanmamalıdır.
  - Android 4,0 veya üzeri için yazılmış olmalıdır.

- Uygulamanın veya şirketiniz tarafından geliştirilmesi gerekir. Google Play Store indirilen uygulamalarda bu aracı kullanamazsınız.

- Uygulama sarmalama aracı 'nı çalıştırmak için [Java Runtime Environment](https://java.com/download/) en son sürümünü yüklemeli ve ardından Java yol değişkeninin Windows ortam değişkeninizdeki C:\ProgramData\Oracle\Java\javapath olarak ayarlandığından emin olmanız gerekir. Daha fazla yardım için bkz. [Java belgeleri](https://java.com/download/help/).

    > [!NOTE]
    > Bazı durumlarda, Java 'nın 32 bit sürümü bellek sorunlarına yol açabilir. 64 bitlik sürümü yüklemek iyi bir fikirdir.

- Android, tüm uygulama paketlerinin (. apk) imzalanmasını gerektirir. Mevcut sertifikaları ve genel imza sertifikası kılavuzunu yeniden **kullanmak** için bkz. [Imzalama sertifikalarını yeniden kullanma ve uygulamaları sarmalama](app-wrapper-prepare-android.md#reusing-signing-certificates-and-wrapping-apps). Sarmalanan çıkış uygulamasını imzalamak için gereken **Yeni** kimlik bilgilerini oluşturmak için Java yürütülebilir Keytool. exe kullanılır. Ayarlanmış parolaların güvenli olması gerekir, ancak uygulama sarmalama aracı 'nı çalıştırmak için gerekli olduklarından bunları bir yere dikkat edin.

    > [!NOTE]
    > Intune uygulama sarmalama aracı, Google 'ın v2 'yi ve uygulama imzalama için yaklaşan v3 imza düzenlerini desteklemez. Intune uygulaması sarmalama aracı 'nı kullanarak. apk dosyasını sarmaladıktan sonra, [Google 'ın sunulan Apkimzalayan aracını]( https://developer.android.com/studio/command-line/apksigner)kullanmaktır. Bu, uygulamanız Son Kullanıcı cihazlarına ulaştıktan sonra Android standartları tarafından düzgün şekilde başlatılabildiğini sağlar. 

- Seçim Bazen bir uygulama, sarmalama sırasında eklenen Intune MAM SDK sınıfları nedeniyle Dalvik çalıştırılabilir (DEX) boyut sınırına ulaşmayabilir. DEX dosyaları, Android uygulaması derlemesinin bir parçasıdır. Intune uygulama sarmalama aracı, en düşük API düzeyi 21 veya daha yüksek olan uygulamalar için ( [v. 1.0.2501.1](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android/releases)itibariyle), dizin oluşturma sırasında otomatik olarak Dex dosyası taşmasını işler. En iyi API düzeyi < 21 olan uygulamalar için en iyi yöntem, sarmalayıcı `-UseMinAPILevelForNativeMultiDex` bayrağını kullanarak en düşük API düzeyini artırmalıdır. Müşterilerin, uygulamanın en düşük API düzeyini artıramasından dolayı aşağıdaki DEX overflow geçici çözümleri kullanılabilir. Bazı kuruluşlarda bu, uygulamayı (IE. app Build ekibi) derleyen ile çalışmayı gerektirebilir:
* Uygulamanın birincil DEX dosyasından kullanılmayan sınıf başvurularını ortadan kaldırmak için ProGuard 'ı kullanın.
* Android Gradle eklentisinin v 3.1.0 veya üstünü kullanan müşteriler için [D8 Dexer](https://android-developers.googleblog.com/2018/04/android-studio-switching-to-d8-dexer.html)'yi devre dışı bırakın.  

## <a name="install-the-app-wrapping-tool"></a>Uygulama sarmalama aracını yükler

1. [GitHub deposundan](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android), Android Için Intune uygulama sarmalama aracı Için ınstallawt. exe yükleme dosyasını bir Windows bilgisayara indirin. Yükleme dosyasını açın.

2. Lisans sözleşmesini kabul edin ve yüklemeyi sona erdirin.

Aracı yüklediğiniz klasörü aklınızda bulabilirsiniz. Varsayılan konum: C:\Program Files (x86) \Microsoft Intune mobil uygulama Management\android\app Wrapping Tool sarmalama aracı.

## <a name="run-the-app-wrapping-tool"></a>Uygulama sarmalama aracını çalıştırma

1. Uygulama sarmalama aracını yüklediğiniz Windows bilgisayarda bir PowerShell penceresi açın.

2. Aracı yüklediğiniz klasörden uygulama sarmalama aracı PowerShell modülünü içeri aktarın:

   ```PowerShell
   Import-Module .\IntuneAppWrappingTool.psm1
   ```

3. Aşağıdaki kullanım söz dizimine sahip **Invoke-AppWrappingTool** komutunu kullanarak aracı çalıştırın:

   ```PowerShell
   Invoke-AppWrappingTool [-InputPath] <String> [-OutputPath] <String> -KeyStorePath <String> -KeyStorePassword <SecureString>
   -KeyAlias <String> -KeyPassword <SecureString> [-SigAlg <String>] [<CommonParameters>]
   ```

   Aşağıdaki tabloda **Invoke-AppWrappingTool** komutunun özellikleri ayrıntılı olarak verilmiştir:

|Özellik|Bilgiler|Örnek|
|-------------|--------------------|---------|
|**-Inputpath**&lt;string @ no__t-2|Kaynak Android uygulamasının (. apk) yolu.| |
 |**-OutputPath**&lt;string @ no__t-2|Çıkış Android uygulamasının yolu. Bu, ınputpath ile aynı dizin yolunuzda paketleme başarısız olur.| |
|**-Keystorepath**&lt;string @ no__t-2|İmzalama için ortak/özel anahtar çiftine sahip olan anahtar deposu dosyasının yolu.|Anahtar deposu dosyaları varsayılan olarak "C:\Program Files (x86) \Java\jreX.X.X_XX\bin." konumunda depolanır. |
|**-KeyStorePassword**&lt;securestring @ no__t-2|Anahtar deposunun şifresini çözmek için kullanılan parola. Android, tüm uygulama paketlerinin (. apk) imzalanmasını gerektirir. KeyStorePassword oluşturmak için Java Keytool kullanın. Java [keystore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) hakkında daha fazla bilgiyi burada bulabilirsiniz.| |
|**-Keyalıas**&lt;dize @ no__t-2|İmzalama için kullanılacak anahtarın adı.| |
|**-KeyPassword**&lt;securestring @ no__t-2|İmzalama için kullanılacak özel anahtarın şifresini çözmek için kullanılan parola.| |
|**-Sigalg**&lt;securestring @ no__t-2| Seçim İmzalama için kullanılacak imza algoritmasının adı. Algoritma özel anahtarla uyumlu olmalıdır.|Örnekler: SHA256withRSA, SHA1withRSA|
|**-UseMinAPILevelForNativeMultiDex**| Seçim Kaynak Android uygulamasının en düşük API düzeyini 21 ' e yükseltmek için bu bayrağı kullanın. Bu bayrak, bu uygulamayı kimlerin yükleyebilen ile sınırlı olacağı için onay isteyecek. Kullanıcılar "-Onayla: $false" parametresini PowerShell komutuna ekleyerek onay iletişim kutusunu atlayabilir. Bayrak yalnızca, DEX taşma hataları nedeniyle başarıyla kaydıramayan en az API < 21 olan uygulamalardaki müşteriler tarafından kullanılmalıdır. | |
| **&lt;CommonParameters @ no__t-2** | Seçim Komut, ayrıntılı ve hata ayıklama gibi ortak PowerShell parametrelerini destekler. |


- Ortak parametrelerin listesi için bkz. [Microsoft betik merkezi](https://technet.microsoft.com/library/hh847884.aspx).

- Araçla ilgili ayrıntılı kullanım bilgilerini görmek için şu komutu girin:

    ```PowerShell
    Help Invoke-AppWrappingTool
    ```

**Örneğinde**

PowerShell modülünü içeri aktarın.

```PowerShell
Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
```

Uygulama sarmalama aracını yerel uygulama HelloWorld. apk üzerinde çalıştırın.

```PowerShell
invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app_wrapped\HelloWorld_wrapped.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\mykeystorefile" -keyAlias mykeyalias -SigAlg SHA1withRSA -Verbose
```

Daha sonra **KeyStorePassword** ve **KeyPassword**istenir. Anahtar deposu dosyasını oluşturmak için kullandığınız kimlik bilgilerini girin.

Sarmalanan uygulama ve bir günlük dosyası oluşturulup belirttiğiniz çıkış yolunda kaydedilir.

## <a name="how-often-should-i-rewrap-my-android-application-with-the-intune-app-wrapping-tool"></a>Intune uygulaması sarmalama aracı ile Android uygulamamı ne sıklıkta yeniden sarmalamalıyım?
Uygulamalarınızı yeniden sarmalamak için gereken ana senaryolar aşağıdaki gibidir:
* Uygulamanın kendisi yeni bir sürüm yayımlamıştır. Uygulamanın önceki sürümü sarmalanmış ve Intune konsoluna yüklendi.
* Android için Intune uygulama sarmalama aracı, anahtar hata düzeltmeleri veya yeni, belirli Intune uygulama koruma ilkesi özelliklerini sağlayan yeni bir sürüm yayımlamıştır. Bu, [Android için Microsoft Intune uygulama sarmalama aracı](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android)için GitHub deposu aracılığıyla her 6-8 haftada bir gerçekleşir.

Yeniden sarmalama için bazı en iyi uygulamalar şunlardır: 
* Oluşturma işlemi sırasında kullanılan imzalama sertifikalarını koruma, bkz. [imzalama sertifikalarını yeniden kullanma ve uygulamaları sarmalama](app-wrapper-prepare-android.md#reusing-signing-certificates-and-wrapping-apps)

## <a name="reusing-signing-certificates-and-wrapping-apps"></a>İmzalama sertifikalarını yeniden kullanma ve uygulamaları sarmalama
Android, Android cihazlara yüklenebilmesi için tüm uygulamaların geçerli bir sertifika tarafından imzalanması gerekir.

Sarmalanan uygulamalar, kaydırma işleminin bir parçası olarak veya mevcut imzalama araçlarınız kullanılarak *sarmalandıktan sonra* imzalanabilir (sarmalamadan önce uygulamadaki imzalama bilgileri atılır). Mümkünse, oluşturma işlemi sırasında zaten kullanılan imzalama bilgileri, kaydırma sırasında kullanılmalıdır. Bu, belirli kuruluşlarda, anahtar deposu bilgilerinin (yani, uygulama derleme ekibi) sahibi olan herhangi bir sorun ile çalışmayı gerektirebilir. 

Önceki imza sertifikası kullanılamazsa veya uygulama daha önce dağıtılmamışsa, [Android Geliştirici Kılavuzu](https://developer.android.com/studio/publish/app-signing.html#signing-manually)'ndaki yönergeleri izleyerek yeni bir imzalama sertifikası oluşturabilirsiniz.

Uygulama daha önce farklı bir imzalama sertifikasıyla dağıtılmışsa, uygulama yükseltmeden sonra Intune 'a yüklenemez. Uygulamanız uygulamanın derlenenden farklı bir sertifikayla imzalanmışsa uygulama yükseltme senaryoları bozulur. Bu nedenle, uygulama yükseltmeleri için yeni imzalama sertifikalarının saklanması gerekir. 

## <a name="security-considerations-for-running-the-app-wrapping-tool"></a>Uygulama sarmalama aracını çalıştırmaya yönelik güvenlik konuları
Olası yanıltma, bilgilerin açığa çıkması ve ayrıcalık yükselmesine karşı engellemek için:

- Giriş iş kolu (LOB) uygulamasının, çıkış uygulamasının ve Java KeyStore 'un, uygulama sarmalama aracının çalıştığı aynı Windows bilgisayarında olduğundan emin olun.

- Çıkış uygulamasını, aracın çalıştığı aynı makinede Intune 'a aktarın. Java Keytool hakkında daha fazla bilgi için bkz. [Keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html) .

- Çıkış uygulaması ve araç, evrensel adlandırma kuralı (UNC) yolındaysanız ve aracı ve giriş dosyalarını aynı bilgisayarda çalıştırmıyorsanız, [Internet Protokolü güvenliği (IPSec)](https://wikipedia.org/wiki/IPsec) veya sunucu iletisi kullanarak ortamı güvenli olacak şekilde ayarlayın [ Block (SMB) imzası](https://support.microsoft.com/kb/887429).

- Uygulamanın güvenilen bir kaynaktan geldiğinden emin olun.

- Sarmalanan uygulamayı içeren çıkış dizinini güvenli hale getirin. Çıkış için Kullanıcı düzeyinde bir dizin kullanmayı düşünün.

## <a name="see-also"></a>Ayrıca bkz.
- [Microsoft Intune ile uygulamaların mobil uygulama yönetimine nasıl hazırlanacağına karar verme](../developer/apps-prepare-mobile-application-management.md)

- [Android için Microsoft Intune uygulama SDK 'Sı Geliştirici Kılavuzu](../developer/app-sdk-android.md)
