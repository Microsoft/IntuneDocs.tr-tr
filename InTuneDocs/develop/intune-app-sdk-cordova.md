---
title: "Microsoft Intune Uygulama SDK&quot;sı Cordova Eklentisi | Microsoft Intune"
description: 
keywords: sdk, Cordova, intune
author: oydang
manager: angrobe
ms.author: oydang
ms.date: 11/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb940cb9-d43f-45ca-b065-ac0adc61dc6f
ms.reviewer: karthikaraman
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: af7df3fcf50c3508d495522341bb287c638f40a3
ms.openlocfilehash: 2af369cc44c710789ab65eb25f10602882772019


---
# ﻿<a name="microsoft-intune-app-sdk-cordova-plugin"></a>Microsoft Intune Uygulama SDK'sı Cordova Eklentisi

> [!NOTE]
> Öncelikle, desteklenen platformlarda tümleştirme için nasıl hazırlık yapıldığını açıklayan [Intune Uygulama SDK’sını Kullanmaya Başlama](intune-app-sdk-get-started.md) makalesini okumanız önerilir.


## <a name="overview"></a>Genel Bakış

[Intune Uygulama SDK'sı Cordova Eklentisi](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam), Cordova ile derlenmiş olan iOS ve Android uygulamalarındaki [Intune mobil uygulama yönetim özelliklerini](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) etkinleştirir. Eklenti, geliştiricilerin Intune uygulama ve veri koruma özelliklerini Cordova tabanlı uygulamalarıyla tümleştirmelerini sağlar.

Uygulamanızın davranışını değiştirmeden SDK özelliklerini etkinleştirebileceğinizi göreceksiniz. Eklentiyi iOS veya Android mobil uygulamanıza eklediğinizde, BT yöneticisi birçok veri koruma özelliğini destekleyen Microsoft Intune Mobil Uygulama Yönetimi (MAM) ile ilkeleri dağıtabilir. Eklentiyi, adımlarının çoğunun Cordova derleme işleminde otomatik olarak gerçekleştirileceği şekilde derledik. Bu sayede uygulamanızı hızlı bir şekilde yönetime uygun hale getirebileceksiniz. Başlamak için aşağıdaki adımlardan hedef platformunuza uygun olanları izleyin.




## <a name="whats-supported"></a>Desteklenen özellikler

### <a name="developer-machines"></a>Geliştirici makineleri
* Windows
* Mac OS


### <a name="mobile-app-platforms"></a>Mobil uygulama platformları
* Android 4.0+
* iOS

### <a name="intune-mobile-application-management-scenarios"></a>Intune Mobil Uygulama Yönetimi senaryoları

* Intune MDM ile kaydedilen cihazlar
* Üçüncü taraf EMM ile kaydedilen cihazlar
* Yönetilmeyen cihazlar (herhangi bir MDM ile kaydedilmeyen)

Intune Uygulama SDK'sı Cordova Eklentisi ile derlenen Cordova uygulamaları artık hem Intune mobil cihaz yönetimi (MDM) ile kaydedilen hem de kaydedilmeyen cihazlarda Intune mobil uygulama yönetimi (MAM) ilkelerini alabilir.



## <a name="prerequisites"></a>Önkoşullar

### <a name="technical-prerequisites"></a>Teknik önkoşullar

* **[Yalnızca Android]** Cihazda her zaman en güncel Microsoft Intune Şirket Portalı uygulamasının yüklü olmalıdır.


* [Cordova için Azure Active Directory Authentication Library (ADAL) eklentisinin](https://github.com/AzureAD/azure-activedirectory-library-for-cordova) 0.8.0 üzeri sürümü gereklidir.
  * **Önemli:** [Burada](https://issues.apache.org/jira/browse/CB-6227?jql=text%20~%20%22plugin%20dependency%22) bildirilen Apache Cordova hatası nedeniyle eklenti bağımlılığına sahip olan uygulamalar eklentiyi otomatik olarak istenen sürüme yükseltmeyecektir.


### <a name="before-you-install-and-use-microsoft-intune-app-sdk-cordova-plugin-you-must"></a>Microsoft Intune Uygulama SDK'sı Cordova Eklentisi'ni yükleyip kullanmadan önce şunları **yapmanız gerekir**:

* [Intune Uygulama SDK'sı Cordova Eklentisi Lisans Koşulları](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam/blob/master/Intune_App_SDK_Cordova_plugin_RTM_license.pdf)'nı gözden geçirmelisiniz.

* Kendi kayıtlarınız için lisans koşullarının bir kopyasını yazdırmalı ve saklamalısınız. Intune Uygulama SDK'sı Cordova Eklentisi'ni indirip kullandığınızda bu lisans koşullarını kabul etmiş olursunuz.  Kabul etmiyorsanız, yazılımı kullanmayın.


## <a name="quick-start"></a>Hızlı başlangıç

1. ADAL sürümünü güncelleştirme:

    ```
    cordova plugin remove cordova-plugin-ms-adal
    cordova plugin add cordova-plugin-ms-adal@0.8.x
    ```

2. Cordova için Intune Uygulama SDK'sı eklentisi:

    ```
    cordova plugin add cordova-plugin-ms-intune-mam
    ```

## <a name="how-to-build-the-plugin-into-your-ios-app"></a>Eklentiyi iOS uygulamanıza ekleme

Uygulamanızın Intune MAM özelliklerinden faydalanabilmesi için uygulamanız gereken adımlar vardır. Bu adımlar kolaylık sağlamak için Cordova derleme işleminde derleme öncesi kanca ile otomatik olarak gerçekleştirilir. Sonuç olarak bu otomatik adımlar, proje yapılandırmasıyla ilişkilendirilmiş olan `*.pbxproj`, `*-Info.plist`, ve `*.entitlements` dosyalarınızı değiştirecektir. Projenizde destek hakları dosyası yoksa, eklenti otomatik olarak bir tane oluşturacaktır.

Bu kurulum yalnızca tek bir hedefi destekler ve birden fazla hedef olması halinde yapılandırma bulunan ilk hedefe uygulanır. İşlem başarısız olursa şu noktaları kontrol edin:

1. Uygulamanızın Xcode projesi `[name].xcodeproj` ve burada `[name]`, `config.xml` içinde tanımlanan değer
2. Projeniz [standart Cordova uygulaması dizin yapısını](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html#directory-structure) kullanıyor.

## <a name="how-to-build-the-plugin-into-your-android-app"></a>Eklentiyi Android uygulamanıza ekleme

1. Bu eklentiyi güncel Cordova araçlarıyla içeri aktarın. Eklenti otomatik olarak `after_compile` adımında çağrılacaktır.

2. Eklenti derleme işleminin sonunda derlenen apk (Android API 14+) dosyasının MAM özellikli sürümünü oluşturacaktır. Derleme çıktısında `[Project]-intunewrapped-[Build_Configuration].apk` bulunacaktır (ör: `helloWorld-intunewrapped-debug.apk`).

Eklenti yalnızca gradle derlemelerini destekler.

[Burada](https://issues.apache.org/jira/browse/CB-9434) bildirilen bir Cordova hatası nedeniyle belirli Cordova kancaları `cordova run` üzerinde yoksayılır. Sarılmış uygulamayı komut satırından çalıştırmak için şunları yapmanız gerekir:

```
$ cordova build
$ cordova run --nobuild
```


### <a name="signing-your-android-app"></a>Android uygulamanızı imzalama
Sarılmış apk dosyasına imza bilgilerini eklemek için normalde imza bilgileri eklediğiniz şekilde `build.json` dosyasını değiştirin. Örneğin:
```json
{
  "android": {
    "release": {
      "keystore": "your.keystore",
      "storePassword": "yourpassword",
      "alias": "youralias",
      "password" : "yourpassword",
      "keystoreType": ""
    }
  }
}
```

### <a name="build-for-android-test-only"></a>Yalnızca test amaçlı Android derlemesi

1. `android:testOnly="true"` değerini `AndroidManifest.xml` dosyasının uygulama düğümüne ekleyin.


2. **Cordova 6.x.x:** `[PROJECT_ROOT]/platforms/android/cordova/lib/Adb.js` içinde 60. satırı değiştirin:

    ```javascript
    var args = ['-s', target, 'install'];
    ```
    seçeneğini
    ```javascript
    var args = ['-s', target, 'install', '-t'];
    ```

Bu işlemin etkisi `adb install` uygulamasını "-t" parametresiyle çalıştırmak olacaktır. Bunun nedeni, `testOnly` uygulamalarının bu olmadan yüklenemeyecek olmasıdır.

### <a name="debugging-from-visual-studio"></a>Visual Studio'dan hata ayıklama
Uygulamayı ilk kez çalıştırdığınızda, Intune tarafından yönetildiğini belirten bir iletişim kutusu görüntülenir. "Bir daha gösterme" seçeneğini işaretleyin ve kesme noktalarına ulaşılması için VS'den hata ayıkla/çalıştır düğmesine tekrar tıklayın.

## <a name="known-limitations"></a>Bilinen Sınırlamalar
### <a name="android"></a>Android
* MultiDex desteği tamamlanmadı.
* Uygulama hedefi Android 4.0 (Android API 14) veya üzeri olmalıdır.

### <a name="ios"></a>iOS
* **Info.plist** dosyasının **CFBundleDocumentTypes** düğümünün altındaki UTI listesini değiştirdiğinizde tekrar derlemeden önce aynı plist dosyasının (**UTImportedTypeDeclarations** düğümü) İçe Aktarılan UTI'ler bölümündeki Intune UTI'lerini temizlemeniz gerekir. Tüm Intune UTI'leri `com.microsoft.intune.mam` ön ekine sahip olacaktır.

* Intune eklentisini Cordova projenizden kaldırmak isterseniz, .xcodeproj ve .plist dosyalarındaki Intune yapılandırmalarından bazılarını geri almak için iOS platformunu da kaldırıp tekrar eklemeniz gerekir.



<!--HONumber=Nov16_HO4-->


