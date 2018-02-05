---
title: "Microsoft Intune Uygulama SDK'sı Xamarin Bileşeni"
description: 
keywords: sdk, Xamarin, intune
author: erikre
manager: dougeby
ms.author: erikre
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4b52b83b84e36a89b5e578c9e14c5093715a559c
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="microsoft-intune-app-sdk-xamarin-component"></a>Microsoft Intune Uygulama SDK'sı Xamarin Bileşeni

> [!NOTE]
> Öncelikle, desteklenen platformlarda tümleştirme için nasıl hazırlık yapıldığını açıklayan [Intune Uygulama SDK’sını Kullanmaya Başlama](app-sdk-get-started.md) makalesini okumanız önerilir.



## <a name="overview"></a>Genel bakış
[Intune App SDK’sı Xamarin bileşeni](https://github.com/msintuneappsdk/intune-app-sdk-xamarin), Xamarin ile oluşturulan iOS ve Android uygulamalarındaki [Intune uygulama koruma ilkesini](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) etkinleştirir. Bu bileşen, geliştiricilerin Intune uygulama koruma özelliklerini Xamarin tabanlı uygulamalarına kolayca eklemesini sağlar.

> [!NOTE]
> Xamarin için Intune SDK’sı desteği şu anda önizlemede kullanılabilir. 

Microsoft Intune Uygulama SDK’sı Xamarin Bileşeni, Intune uygulama koruma ilkelerini (APP veya MAM ilkeleri olarak da bilinir) Xamarin ile geliştirilen uygulamalarınıza eklemenizi sağlar. MAM özellikli uygulamalar Intune Uygulama SDK’sı ile tümleşiktir. Intune uygulamayı etkin bir şekilde yönetirken, BT yöneticileri mobil uygulamanıza uygulama koruma ilkeleri dağıtabilir.

## <a name="whats-supported"></a>Desteklenen özellikler

### <a name="developer-machines"></a>Geliştirici makineleri
* Mac OS


### <a name="mobile-app-platforms"></a>Mobil uygulama platformları
* Android
* iOS


### <a name="intune-mobile-application-management-scenarios"></a>Intune Mobil Uygulama Yönetimi senaryoları

* Intune MDM ile kaydedilen cihazlar
* Üçüncü taraf EMM ile kaydedilen cihazlar
* Yönetilmeyen cihazlar (herhangi bir MDM ile kaydedilmeyen)

Intune Uygulama SDK’sı Xamarin Bileşeni ile derlenen Xamarin uygulamaları artık, Intune mobil cihaz yönetimi (MDM) ile kaydedilen ve kaydedilmeyen cihazlarda Intune uygulama koruma ilkelerini alabilir.

## <a name="prerequisites"></a>Önkoşullar

* **[Yalnızca Android]** Cihazda en güncel Microsoft Intune Şirket Portalı uygulaması yüklü olmalıdır.

## <a name="get-started"></a>Başlarken

1.  **Xamarin-component.exe** dosyasını [buradan](https://components.xamarin.com/submit/xpkg) indirin ve ayıklayın.

2. Microsoft Intune MAM Xamarin Bileşeni [lisans koşullarını](https://components.xamarin.com/license/microsoft.intune.mam) okuyun.

3.  Intune Uygulama SDK’sı Xamarin Bileşeni klasörünü [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) veya [Nuget.org](https://www.nuget.org/profiles/msintuneappsdk)’dan indirin ve ayıklayın. 1. ve 3. adımlarda indirdiğiniz dosyaların aynı dizin düzeyinde olması gerekir.

4.  Komut satırında yönetici olarak `Xamarin.Component.exe install <.xam> file` komutunu çalıştırın.

5.  Visual Studio’da önceden oluşturduğunuz Xamarin projesinde **bileşenler** öğesine sağ tıklayın.

6.  **Bileşenleri Düzenle**'yi seçin ve bilgisayarınıza indirdiğiniz Intune Uygulama SDK'sı bileşenini ekleyin.



## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>iOS mobil uygulamanızda Intune uygulama koruma ilkelerini etkinleştirme
1.  Intune Uygulama SDK'sını iOS mobil uygulamasına tümleştirmek için gereken genel adımları izleyin. [iOS için Intune Uygulama SDK'si Geliştirici Kılavuzu](app-sdk-ios.md#build-the-sdk-into-your-mobile-app)'nda verilen tümleştirme yönergelerinin 3. adımıyla başlayabilirsiniz.
    **Önemli**: Visual Studio'da uygulama için anahtarlık paylaşımını etkinleştirme işlemi Xcode'dakinden biraz farklıdır. Uygulamanın Yetkilendirmeler plist dosyasını açın, "Anahtarlığı Etkinleştir" seçeneğinin etkinleştirildiğinden ve uygun anahtarlık paylaşım gruplarının bu bölüme eklendiğinden emin olun. Ardından, tüm uygun Yapılandırma/Platform bileşimleri için projenin "iOS Paketi İmzalama" seçeneklerindeki "Özel Yetkilendirmeler" alanında Yetkilendirmeler plist dosyasının belirtildiğinden emin olun.
2.  Bileşen eklendikten ve uygulama düzgün bir şekilde yapılandırıldıktan sonra, uygulamanız Intune SDK'sının API'lerini kullanmaya başlayabilir. Bunu yapmak için, aşağıdaki ad alanını eklemelisiniz:

      ```csharp
      using Microsoft.Intune.MAM;
      ```
3.    Uygulama koruma ilkelerini almaya başlamak için, uygulamanızın Intune MAM hizmetine kaydolması gerekir. Uygulamanız kullanıcıların kimliğini doğrulamak için zaten Azure Active Directory Authentication Library (ADAL) kullanıyorsa, kimliği başarıyla doğrulandıktan sonra uygulamanız kullanıcının UPN'sini IntuneMAMEnrollmentManager'ın registerAndEnrollAccount yöntemine sağlamalıdır:
      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```
      **Önemli**: Intune Uygulama SDK'sının varsayılan ADAL ayarlarının üzerine uygulamanızın ayarlarının yazıldığından emin olun. Bunu, [iOS için Intune Uygulama SDK'sı Geliştirici Kılavuzu](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk)'nda belirtildiği gibi uygulamanın Info.plist dosyasındaki IntuneMAMSettings sözlüğü aracılığıyla yapabilirsiniz veya IntuneMAMPolicyManager örneğinin AAD geçersiz kılma özelliklerini kullanabilirsiniz. ADAL ayarları statik olan uygulamalarda Info.plist yaklaşımı önerilirken, bu değerleri çalışma zamanında belirleyen uygulamalar için geçersiz kılma özelliklerinin kullanılması önerilir. 
      
      Uygulamanız ADAL kullanmıyorsa ve kimlik doğrulama işlemini Intune SDK'sının üstlenmesini istiyorsanız, uygulamanız IntuneMAMEnrollmentManager'ın loginAndEnrollAccount yöntemini çağırmalıdır:
      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```

## <a name="enabling-app-protection-policies-in-your-android-mobile-app"></a>Android mobil uygulamanızda uygulama koruma ilkelerini etkinleştirme
UI çerçevesi kullanmayan Xamarin tabanlı Android uygulamaları için [Android Geliştiricisi için Intune Uygulama SDK’sı Kılavuzu](app-sdk-android.md) belgesini okumanız ve gerekli adımları uygulamanız gerekir. Xamarin tabanlı Android uygulamanız için sınıf, yöntem ve etkinlikleri kılavuzda yer alan [tabloya](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) göre MAM eşdeğerleriyle değiştirmeniz gerekir. Uygulamanızda `android.app.Application` sınıfı tanımlanmıyorsa bir tane oluşturup `MAMApplication` kaynağından devraldığından emin olmanız gerekir.

Xamarin.Forms ve diğer UI çerçeveleri için `MAM.Remapper` adında bir araç sunuyoruz. Bu araç, sınıf değişikliklerini sizin için yapacaktır. Ancak aşağıdaki adımları sizin uygulamanız gerekir:

1.  `Microsoft.Intune.MAM.Remapper.Tasks` NuGet paketi sürüm 0.1.0.0 veya üzeri için başvuru ekleyin.

2.  Android csproj dosyanıza şu satırı ekleyin:
  ```xml
  <Import
  Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.0.1.X.X\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
  ```

3.  Eklediğiniz `remapping-config.json` dosyasının derleme eylemini **RemappingConfigFile** olarak ayarlayın. Dahil edilen `remapping-config.json` yalnızca Xamarin.Forms ile çalışır. Diğer UI çerçeveleri için Remapper NuGet paketindeki Benioku dosyasına bakın.

## <a name="next-steps"></a>Sonraki adımlar

Bileşeni uygulamanıza eklemek için temel adımları tamamladınız. Şimdi Xamarin Android örnek uygulamasındaki adımları uygulayabilirsiniz. Biri Xamarin.Forms, diğeri Android için olmak üzere iki örnek sağladık.
