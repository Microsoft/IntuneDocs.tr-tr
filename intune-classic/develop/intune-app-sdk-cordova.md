---
title: "Microsoft Intune Uygulama SDK&quot;sı Cordova Eklentisi | Microsoft Docs"
description: 
keywords: sdk, Cordova, intune
author: oydang
manager: angrobe
ms.author: oydang
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb940cb9-d43f-45ca-b065-ac0adc61dc6f
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 6a33f9c4d1b1158d9e4e4843b149a742be9cd469
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---
# <a name="microsoft-intune-app-sdk-cordova-plugin"></a>Microsoft Intune Uygulama SDK'sı Cordova Eklentisi

> [!NOTE]
> Öncelikle, desteklenen platformlarda tümleştirme için nasıl hazırlık yapıldığını açıklayan [Intune Uygulama SDK’sını Kullanmaya Başlama](intune-app-sdk-get-started.md) makalesini okumanız önerilir.

## <a name="overview"></a>Genel Bakış

iOS ve Android uygulamalarında Cordova ile oluşturulmuş [Intune Uygulama SDK’sı Cordova Eklentisi](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune). Eklenti, geliştiricilerin Intune uygulama ve veri koruma özelliklerini Cordova tabanlı uygulamalarıyla tümleştirmelerini sağlar.

Uygulamanızın davranışını değiştirmeden SDK özelliklerini etkinleştirebileceğinizi göreceksiniz. Eklentiyi iOS veya Android uygulamanızda derlemeden önce Microsoft Intune yöneticisi çeşitli veri koruma özelliklerini içeren Intune uygulama koruma ilkesini dağıtabilecek. Eklenti, adımlarının çoğunun Cordova derleme işleminde otomatik olarak gerçekleştirileceği şekilde derlenmiştir. Bu sayede uygulamanızı hızlı bir şekilde Intune uygulama korumasına uygun hale getirebileceksiniz. Başlamak için aşağıdaki adımlardan hedef platformunuza uygun olanları izleyin.

## <a name="supported-platforms"></a>Desteklenen Platformlar

* Eklenti Windows, Mac ve Linux işletim sistemlerinde çalışır
* Eklenti `minSdkVersion` >= 14 ve `targetSdkVersion` <= 24 Android uygulamalarıyla çalışır
* Eklenti iOS 9.0 ve üzerini hedefleyen iOS uygulamalarıyla çalışır.

## <a name="intune-mobile-application-management-scenarios"></a>Intune Mobil Uygulama Yönetimi senaryoları

* Intune MDM ile kaydedilen cihazlar
* Üçüncü taraf EMM ile kaydedilen cihazlar
* Yönetilmeyen cihazlar (herhangi bir MDM ile kaydedilmeyen)

Intune Uygulama SDK'sı Cordova Eklentisi ile derlenen Cordova uygulamaları artık hem Intune mobil cihaz yönetimi (MDM) ile kaydedilen hem de kaydedilmeyen cihazlarda Intune uygulama koruma ilkelerini alabilir.

## <a name="prerequisites"></a>Önkoşullar

### <a name="android"></a>Android

* Cihazda her zaman en güncel Microsoft Intune Şirket Portalı uygulaması yüklü olmalıdır.
* Eklentiyi kullandığınızda Cordova derlemesini yürüteceğiniz yolda en az Java 7 bulunmalıdır.

### <a name="ios"></a>iOS

* MDM özellikleri için cihazda en güncel Microsoft Intune Şirket Portalı uygulaması yüklü olmalıdır. Cihaz kaydı özellikleri olmayan Intune uygulama koruma ilkesi için gerekli *değildir*.

### <a name="both-platforms"></a>Her iki platform

* [Cordova için Azure Active Directory Authentication Library (ADAL) eklentisinin](https://github.com/AzureAD/azure-activedirectory-library-for-cordova) 0.8.0 üzeri sürümü gereklidir.

> [!NOTE]
> [Burada](https://issues.apache.org/jira/browse/CB-6227?jql=text%20~%20%22plugin%20dependency%22) bildirilen Apache Cordova hatası nedeniyle eklenti bağımlılığına sahip olan uygulamalar eklentiyi otomatik olarak istenen sürüme yükseltmeyecektir.



## <a name="quick-start"></a>Hızlı başlangıç

1. ADAL sürümünü güncelleştirme:

  ```shell
  cordova plugin remove cordova-plugin-ms-adal
  cordova plugin add cordova-plugin-ms-adal@0.8.x
  ```

2. Cordova için Intune Uygulama SDK'sı eklentisi:

  ```shell
  cordova plugin add cordova-plugin-ms-intune-mam
  ```

## <a name="build-the-plugin-into-your-ios-app"></a>Eklentiyi iOS uygulamanızda derleme

Uygulamanızın Intune uygulama koruma ilkesi için etkinleştirilmesi amacıyla uygulamanız gereken adımlar vardır. Bu adımlar kolaylık sağlamak için Cordova derleme işleminde derleme öncesi kanca ile otomatik olarak gerçekleştirilir. Sonuç olarak bu otomatik adımlar, proje yapılandırmasıyla ilişkilendirilmiş olan `*.pbxproj`, `*-Info.plist`, ve `*.entitlements` dosyalarınızı değiştirecektir. Projenizde destek hakları dosyası yoksa, eklenti otomatik olarak bir tane oluşturacaktır.

Bu kurulum yalnızca tek bir hedefi destekler ve birden fazla hedef olması halinde yapılandırma bulunan ilk hedefe uygulanır. İşlem başarısız olursa şu noktaları kontrol edin:

1. Uygulamanızın Xcode projesi `[name].xcodeproj` ve burada `[name]`, `config.xml` içinde tanımlanan değer
2. Projeniz [standart Cordova uygulaması dizin yapısını](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html#directory-structure) kullanıyor.

## <a name="build-the-plugin-into-your-android-app"></a>Eklentiyi Android uygulamanızda derleme

1. Bu eklentiyi güncel Cordova araçlarıyla içeri aktarın. Eklenti otomatik olarak `after_compile` adımında çağrılacaktır.

2. Eklenti derleme işleminin sonunda derlenen apk (Android API 14+) dosyasının Intune özellikli sürümünü oluşturacaktır. Derleme çıktısında `[Project]-intunewrapped-[Build_Configuration].apk` bulunacaktır (ör: `helloWorld-intunewrapped-debug.apk`).

> [!NOTE]
> Eklenti yalnızca gradle derlemelerini destekler.

[Burada](https://issues.apache.org/jira/browse/CB-9434) bildirilen bir Cordova hatası nedeniyle belirli Cordova kancaları `cordova run` üzerinde yoksayılır. Sarılmış uygulamayı komut satırından çalıştırmak için şunları yapmanız gerekir:

```shell
$ cordova build
$ cordova run --nobuild
```

## <a name="sign-your-android-app"></a>Android uygulamanızı imzalama

Eklenti aşağıdaki konumlarda bulunan Cordova'ya verdiğiniz imza bilgilerini otomatik olarak tanır:

* platforms/android/debug-signing.properties
* platforms/android/release-signing.properties
* res/native/android/ant.properties

Beklenen biçin hakkında daha fazla bilgi için [Cordova gradle imzalama bilgilerine](https://cordova.apache.org/docs/en/latest/guide/platforms/android/#using-gradle) bakın.

Şu anda `build.json` içinde veya parametreler aracılığıyla isteğe bağlı konumlarda Cordova derlemesine imza bilgisi sağlanmasını desteklemiyoruz.

## <a name="debugging-from-visual-studio"></a>Visual Studio'dan hata ayıklama

Uygulamayı ilk kez çalıştırdığınızda, Intune tarafından yönetildiğini belirten bir iletişim kutusu görüntülenir. "Bir daha gösterme" seçeneğini işaretleyin ve kesme noktalarına ulaşılması için VS'den hata ayıkla/çalıştır düğmesine tekrar tıklayın.

## <a name="known-limitations"></a>Bilinen Sınırlamalar

### <a name="android"></a>Android

* MultiDex desteği tamamlanmadı.
* Uygulama `minSdkVersion` 14 ve `targetSdkVersion` 24 veya altı olmalıdır. Şu anda API 25 hedefleyen uygulamaları desteklemiyoruz
* V2 İmza Şemasıyla imzalanmış olan uygulamaları yeniden imzalayamıyoruz. V2 imzalı uygulamalar eklenti ile sarıldığında sarılan sonuç .apk dosyası imzalanmamış olur.
*
  * Aşağıdakileri `build-extras.gradle` dosyanıza ekleyerek Cordova'nın varsayılan V2 İmzalama özelliğini devre dışı bırakabilirsiniz:

  ```gradle
  android {
      signingConfigs {
          release {
              v2SigningEnabled false
          }
          debug {
              v2SigningEnabled false
          }
      }
      buildTypes {
          release {
              signingConfig signingConfigs.release
          }
          debug {
              signingConfig signingConfigs.debug
          }
      }
  }
  ```

### <a name="ios"></a>iOS

* **Info.plist** dosyasının **CFBundleDocumentTypes** düğümünün altındaki UTI listesini değiştirdiğinizde tekrar derlemeden önce aynı plist dosyasının (**UTImportedTypeDeclarations** düğümü) İçe Aktarılan UTI'ler bölümündeki Intune UTI'lerini temizlemeniz gerekir. Tüm Intune UTI'leri `com.microsoft.intune.mam` ön ekine sahip olacaktır.

* Cordova için Intune Uygulama SDK'sı eklentisini Cordova projenizden kaldırmak isterseniz, .xcodeproj ve .plist dosyalarındaki Intune yapılandırmalarından bazılarını geri almak için iOS platformunu da kaldırıp tekrar eklemeniz gerekir.

