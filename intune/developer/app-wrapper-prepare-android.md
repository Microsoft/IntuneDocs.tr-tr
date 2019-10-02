---
title: Android uygulamalarını Intune Uygulama Sarmalama Aracı ile sarmalama
description: Android uygulamalarınızı, uygulamanın kendi kodunda değişiklik yapmadan sarmalamayı öğrenin. Mobil uygulama yönetimi ilkelerini uygulayabilmek için uygulamaları hazırlayın.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/09/2019
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
ms.openlocfilehash: 11547d97ebabdfe0a2b30781433cf7694a470808
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71730297"
---
# <a name="prepare-android-apps-for-app-protection-policies-with-the-intune-app-wrapping-tool"></a>Intune Uygulama Sarmalama Aracı ile Android uygulamalarını uygulama koruma ilkelerine hazırlama

Şirket içi Android uygulamalarınızın davranışını, uygulamanın kodunu değiştirmeden uygulama özelliklerini kısıtlayarak değiştirmek için Android için Microsoft Intune Uygulama Sarmalama Aracı'nı kullanın.

Bu araç, PowerShell’de çalışan ve Android uygulamanızın etrafında sarmalayıcı oluşturan bir Windows komut satırı uygulamasıdır. Uygulama sarmalandıktan sonra, Intune’daki [mobil uygulama yönetimi ilkelerini](../apps/app-protection-policies.md) yapılandırarak uygulamanın işlevini değiştirebilirsiniz.

Aracı çalıştırmadan önce bkz. [Uygulama Sarmalama Aracını çalıştırmaya ilişkin güvenlik konuları](#security-considerations-for-running-the-app-wrapping-tool). Aracı indirmek için GitHub’daki [Android için Microsoft Intune Uygulama Sarmalama Aracı](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android)’na gidin.

## <a name="fulfill-the-prerequisites-for-using-the-app-wrapping-tool"></a>Uygulama Sarmalama Aracını kullanmak için önkoşulları karşılama

- Windows 7 veya sonraki sürümlerini çalıştıran bir Windows bilgisayarda Uygulama Sarmalama Aracını çalıştırmanız gerekir.

- Giriş uygulamanız, .apk dosya uzantısıyla geçerli bir Android uygulama paketi olmalıdır ve:

  - Şifreli olamaz.
  - Intune Uygulama Sarmalama Aracı tarafından önceden sarmalanmamış olmalıdır.
  - Android 4.0 veya sonraki sürümler için yazılmış olmalıdır.

- Uygulama, şirketiniz tarafından veya şirketiniz için geliştirilmiş olmalıdır. Bu aracı Google Play Store’dan indirilen uygulamalarda kullanamazsınız.

- Uygulama Sarmalama Aracını çalıştırmak için en son [Java Çalışma Zamanı Ortamı](https://java.com/download/) sürümünü yüklemeniz ve ardından Windows ortam değişkenlerinizdeki Java yolu değişkeninin C:\ProgramData\Oracle\Java\javapath olarak ayarlandığından emin olmanız gerekir. Daha fazla yardım için bkz. [Java belgeleri](https://java.com/download/help/).

    > [!NOTE]
    > Bazı durumlarda, Java’nın 32 bit sürümü bellek sorunlarına yol açabilir. 64-bit sürümü yüklemek iyi bir fikirdir.

- Android tüm uygulama paketlerinin (.apk) imzalanmasını gerektirir. Mevcut sertifikaları **yeniden kullanma** hakkında bilgi ve imza sertifikaları rehberine ulaşmak için bkz. [İmza sertifikaları ve sarmalama uygulamalarını yeniden kullanma](app-wrapper-prepare-android.md#reusing-signing-certificates-and-wrapping-apps). Sarmalanan çıkış uygulamasını imzalamak için gereken **yeni** kimlik bilgilerini oluşturmak için yürütülebilir Java keytool.exe kullanılır. Ayarlanan parolaların güvenle saklanması gerekir ancak daha sonra Uygulama Sarmalama Aracını çalıştırırken gerekeceği için bu parolaları not alın.

    > [!NOTE]
    > Intune Uygulama Sarmalama Aracı uygulama imzalama için Google'ın v2 ve yakında çıkacak v3 imza düzenlerini desteklemiyor. Intune Uygulama Sarmalama Aracı'nı kullanarak .apk uygulamasını sarmaladıktan sonra, [Google'ın sağladığı Apksigner aracının]( https://developer.android.com/studio/command-line/apksigner) kullanılması önerilir. Bu sayede uygulama son kullanıcıların cihazlarına ulaştığında Android standartları tarafından düzgün başlatılabilir. 

- Seçim Bazen bir uygulama, sarmalama sırasında eklenen Intune MAM SDK sınıfları nedeniyle Dalvik çalıştırılabilir (DEX) boyut sınırına ulaşmayabilir. DEX dosyaları, Android uygulamaları derlemesinin bir parçasıdır. Intune uygulama sarmalama aracı, en düşük API düzeyi 21 veya daha yüksek olan uygulamalar için ( [v. 1.0.2501.1](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android/releases)itibariyle), dizin oluşturma sırasında otomatik olarak Dex dosyası taşmasını işler. En iyi API düzeyi < 21 olan uygulamalar için en iyi yöntem, sarmalayıcı `-UseMinAPILevelForNativeMultiDex` bayrağını kullanarak en düşük API düzeyini artırmalıdır. Müşterilerin, uygulamanın en düşük API düzeyini artıramasından dolayı aşağıdaki DEX overflow geçici çözümleri kullanılabilir. Bazı kuruluşlarda bu, uygulamayı (IE. app Build ekibi) derleyen ile çalışmayı gerektirebilir:
* Uygulamanın birincil DEX dosyasından kullanılmayan sınıf başvurularını ortadan kaldırmak için ProGuard 'ı kullanın.
* Android Gradle eklentisinin v 3.1.0 veya üstünü kullanan müşteriler için [D8 Dexer](https://android-developers.googleblog.com/2018/04/android-studio-switching-to-d8-dexer.html)'yi devre dışı bırakın.  

## <a name="install-the-app-wrapping-tool"></a>Uygulama Sarmalama Aracını yükleme

1. [GitHub deposundan](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android), Android için Intune Uygulama Sarmalama Aracı’na yönelik InstallAWT.exe yükleme dosyasını bir Windows bilgisayara indirin. Yükleme dosyasını açın.

2. Lisans sözleşmesini kabul edip, yüklemeyi tamamlayın.

Aracı yüklediğiniz klasörü not edin. Varsayılan konum: C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool.

## <a name="run-the-app-wrapping-tool"></a>Uygulama Sarmalama Aracını çalıştırma

1. Uygulama Sarmalama Aracını yüklediğiniz Windows bilgisayarda bir PowerShell penceresi açın.

2. Aracı yüklediğiniz klasörden Uygulama Sarmalama Aracı PowerShell modülünü içeri aktarın:

   ```PowerShell
   Import-Module .\IntuneAppWrappingTool.psm1
   ```

3. Aşağıdaki kullanım söz dizimine sahip **invoke-AppWrappingTool** komutunu kullanarak aracı çalıştırın:

   ```PowerShell
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
|**-SigAlg**&lt;GüvenliDize&gt;| (İsteğe bağlı) İmzalama için kullanan imza algoritmasının adı. Algoritma, özel anahtar ile uyumlu olmalıdır.|Örnekler: SHA256withRSA, SHA1withRSA|
|**-UseMinAPILevelForNativeMultiDex**| Seçim Kaynak Android uygulamasının en düşük API düzeyini 21 ' e yükseltmek için bu bayrağı kullanın. Bu bayrak, bu uygulamayı kimlerin yükleyebilen ile sınırlı olacağı için onay isteyecek. Kullanıcılar "-Onayla: $false" parametresini PowerShell komutuna ekleyerek onay iletişim kutusunu atlayabilir. Bayrak yalnızca, DEX taşma hataları nedeniyle başarıyla kaydıramayan en az API < 21 olan uygulamalardaki müşteriler tarafından kullanılmalıdır. | |
| **&lt;CommonParameters&gt;** | (İsteğe bağlı) Komut, ayrıntılı ve hata ayıklama gibi ortak PowerShell parametrelerini destekler. |


- Ortak parametrelerin listesi için bkz. [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx).

- Araca yönelik ayrıntılı kullanım bilgilerini görmek için komutu girin:

    ```PowerShell
    Help Invoke-AppWrappingTool
    ```

**Örnek:**

PowerShell modülünü içeri aktarın.

```PowerShell
Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
```

Uygulama Sarmalama Aracını HelloWorld.apk yerel uygulamasında çalıştırın.

```PowerShell
invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app_wrapped\HelloWorld_wrapped.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\mykeystorefile" -keyAlias mykeyalias -SigAlg SHA1withRSA -Verbose
```

Daha sonra sizden **KeyStorePassword** ve **KeyPassword**istenir. Anahtar depolama dosyası oluşturmak için kullandığınız kimlik bilgilerini girin.

Sarmalanan uygulama ve günlük dosyası oluşturulur ve belirttiğiniz çıkış yoluna kaydedilir.

## <a name="how-often-should-i-rewrap-my-android-application-with-the-intune-app-wrapping-tool"></a>Intune Uygulama Sarmalama Aracı ile Android uygulamamı ne sıklıkta yeniden sarmalamalıyım?
Uygulamalarınızı yeniden sarmalamanız gereken ana senaryolar aşağıdaki gibidir:
* Uygulamanın yeni bir sürümünü yayınlandı. Uygulamanın önceki sürümü sarmalandı ve Intune konsoluna yüklendi.
* Android için Intune Uygulama Sarmalama Aracı uygulamasının hata düzeltmeleri veya yeni, belirli Intune uygulama koruma ilkesi özellikleri içeren yeni bir sürümü yayınlandı. Bu, [Android için Microsoft Intune Uygulama Sarmalama Aracı](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) için her 6-8 haftada bir GitHub deposundan gerçekleşir.

Yeniden sarmalama için bazı en iyi uygulamalar şunlardır: 
* Derleme işleminde kullanılan imzalama sertifikalarının bakımı, bkz. [İmzalama sertifikalarını yeniden kullanma ve uygulamaları sarmalama](app-wrapper-prepare-android.md#reusing-signing-certificates-and-wrapping-apps)

## <a name="reusing-signing-certificates-and-wrapping-apps"></a>İmzalama sertifikalarını yeniden kullanma ve uygulamaları sarmalama
Android cihazlara yüklenecek uygulamaların tamamının geçerli bir sertifika tarafından imzalanmış olması gerekir.

Sarmalanmış uygulamalar, sarmalama işleminin bir parçası olarak veya bu işlemden *sonra*, mevcut imzalama araçlarınız (sarmalama tamamlanmadan önce uygulamadaki herhangi bir imzalama bilgisi) kullanılarak imzalanabilir. Mümkünse derleme işlemi sırasında kullanılan imzalama bilgileri, sarmalama esnasında da kullanılmalıdır. Bazı kuruluşlarda bunu yapabilmek için anahtar deposu bilgilerine kim sahipse (yani uygulama derleme ekibi) onunla birlikte çalışmak gerekebilir. 

Önceki imzalama sertifikası kullanılamıyorsa veya uygulama daha önce dağıtılmamışsa [Android Geliştirici Kılavuzu](https://developer.android.com/studio/publish/app-signing.html#signing-manually)’ndaki yönergeleri takip ederek yeni bir imzalama sertifikası oluşturabilirsiniz.

Uygulama, daha önce farklı bir imzalama sertifikasıyla dağıtılmışsa yükseltme sonrasında Intune’a yüklenemez. Uygulamanız, derlenirken kullanılandan başka bir sertifikayla imzalanırsa uygulama yükseltme senaryoları bozulacaktır. Bu sebeple tüm yeni imzalama sertifikaları, uygulama yükseltmeleri için ayarlanmalıdır. 

## <a name="security-considerations-for-running-the-app-wrapping-tool"></a>Uygulama Sarmalama Aracını çalıştırmaya ilişkin güvenlik konuları
Olası yanıltma, bilgi ifşası ve ayrıcalıkların yükseltilmesi saldırılarını önlemek için:

- Giriş iş kolu (LOB) uygulamasının, çıkış uygulamasının ve Java KeyStore’un Uygulama Sarmalama Aracının çalıştığı aynı Windows bilgisayarında olduğundan emin olun.

- Çıkış uygulamasını, aracın çalıştığı makinede Intune’a aktarın. Java keytool hakkında daha fazla bilgi için bkz. [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html).

- Çıkış uygulaması ve araç, Evrensel Adlandırma Kuralı (UNC) yolundaysa ve aracı ve giriş dosyalarını aynı bilgisayarda çalıştırmıyorsanız, [İnternet Protokolü Güvenliği (IPsec)](https://wikipedia.org/wiki/IPsec) veya [Sunucu İleti Bloğu (SMB) imzalamayı](https://support.microsoft.com/kb/887429)kullanarak ortamı güvenli olacak şekilde ayarlayın.

- Uygulamanın güvenilir bir kaynaktan geldiğine emin olun.

- Sarmalanan uygulamayı içeren çıkış dizinini güvenli hale getirin. Çıkış için kullanıcı düzeyinde bir dizin kullanın.

## <a name="see-also"></a>Ayrıca bkz:
- [Microsoft Intune ile uygulamaların mobil uygulama yönetimi için nasıl hazırlanacağına karar verme](../developer/apps-prepare-mobile-application-management.md)

- [Android için Microsoft Intune Uygulama SDK’sı geliştirici kılavuzu](../developer/app-sdk-android.md)
