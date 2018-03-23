---
title: Microsoft Intune Uygulama SDK'sı Xamarin Bileşeni
description: Intune App SDK’sı Xamarin bileşeni, Xamarin ile oluşturulan iOS ve Android uygulamalarındaki Intune uygulama koruma ilkesini etkinleştirir.
keywords: sdk, Xamarin, intune
author: Erikre
manager: dougeby
ms.author: erikre
ms.date: 03/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b69cccca8c8be859de94ca8bdb50d6030439233a
ms.sourcegitcommit: 54fc806036f84a8667cf8f74086358bccd30aa7d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/20/2018
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

1. Microsoft Intune MAM Xamarin Bileşeni [lisans koşullarını](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20Xamarin%20Component.pdf) okuyun.

2.  [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)’dan Intune Uygulama SDK’sı Xamarin Bileşeni NuGet paketlerini indirin. Bu paketler, yakında Nuget.org adresinden indirilebilecek.  

## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>iOS mobil uygulamanızda Intune uygulama koruma ilkelerini etkinleştirme
1. `Microsoft.Intune.MAM.Xamarin.iOS` NuGet paketini Xamarin.iOS projenize ekleyin.
2.  Intune Uygulama SDK'sını iOS mobil uygulamasına tümleştirmek için gereken genel adımları izleyin. [iOS için Intune Uygulama SDK'si Geliştirici Kılavuzu](app-sdk-ios.md#build-the-sdk-into-your-mobile-app)'nda verilen tümleştirme yönergelerinin 3. adımıyla başlayabilirsiniz. Bu araç, Microsoft.Intune.MAM.Xamarin.iOS paketinde bulunduğu ve derleme sırasında otomatik olarak çalıştırılacağı için IntuneMAMConfigurator’ı çalıştırma bölümündeki son adımı atlayabilirsiniz.
    **Önemli**: Visual Studio'da uygulama için anahtarlık paylaşımını etkinleştirme işlemi Xcode'dakinden biraz farklıdır. Uygulamanın Yetkilendirmeler plist dosyasını açın, "Anahtarlığı Etkinleştir" seçeneğinin etkinleştirildiğinden ve uygun anahtarlık paylaşım gruplarının bu bölüme eklendiğinden emin olun. Ardından, tüm uygun Yapılandırma/Platform bileşimleri için projenin "iOS Paketi İmzalama" seçeneklerindeki "Özel Yetkilendirmeler" alanında Yetkilendirmeler plist dosyasının belirtildiğinden emin olun.
3.  Bileşen eklendikten ve uygulama düzgün bir şekilde yapılandırıldıktan sonra, uygulamanız Intune SDK'sının API'lerini kullanmaya başlayabilir. Bunu yapmak için, aşağıdaki ad alanını eklemelisiniz:

      ```csharp
      using Microsoft.Intune.MAM;
      ```
4. Uygulama koruma ilkelerini almaya başlamak için, uygulamanızın Intune MAM hizmetine kaydolması gerekir. Uygulamanız kullanıcıların kimliğini doğrulamak için zaten Azure Active Directory Authentication Library (ADAL) kullanıyorsa, kimliği başarıyla doğrulandıktan sonra uygulamanız kullanıcının UPN'sini IntuneMAMEnrollmentManager'ın registerAndEnrollAccount yöntemine sağlamalıdır:
      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```
      **Önemli**: Intune Uygulama SDK'sının varsayılan ADAL ayarlarının üzerine uygulamanızın ayarlarının yazıldığından emin olun. Bunu, [iOS için Intune Uygulama SDK'sı Geliştirici Kılavuzu](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk)'nda belirtildiği gibi uygulamanın Info.plist dosyasındaki IntuneMAMSettings sözlüğü aracılığıyla yapabilirsiniz veya IntuneMAMPolicyManager örneğinin AAD geçersiz kılma özelliklerini kullanabilirsiniz. ADAL ayarları statik olan uygulamalarda Info.plist yaklaşımı önerilirken, bu değerleri çalışma zamanında belirleyen uygulamalar için geçersiz kılma özelliklerinin kullanılması önerilir. 
      
      Uygulamanız ADAL kullanmıyorsa ve kimlik doğrulama işlemini Intune SDK'sının üstlenmesini istiyorsanız, uygulamanız IntuneMAMEnrollmentManager'ın loginAndEnrollAccount yöntemini çağırmalıdır:
      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```

## <a name="enabling-app-protection-policies-in-your-android-mobile-app"></a>Android mobil uygulamanızda uygulama koruma ilkelerini etkinleştirme
`Microsoft.Intune.MAM.Xamarin.Android` NuGet paketini Xamarin.Android projenize ekleyin.

UI çerçevesi kullanmayan Xamarin tabanlı Android uygulamaları için [Android Geliştiricisi için Intune Uygulama SDK’sı Kılavuzu](app-sdk-android.md) belgesini okumanız ve gerekli adımları uygulamanız gerekir. Xamarin tabanlı Android uygulamanız için sınıf, yöntem ve etkinlikleri kılavuzda yer alan [tabloya](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) göre MAM eşdeğerleriyle değiştirmeniz gerekir. Uygulamanızda `android.app.Application` sınıfı tanımlanmıyorsa bir tane oluşturup `MAMApplication` kaynağından devraldığından emin olmanız gerekir.

Xamarin.Forms ve diğer UI çerçeveleri için `MAM.Remapper` adında bir araç sunuyoruz. Bu araç, sınıf değişikliklerini sizin için yapacaktır. Ancak aşağıdaki adımları sizin uygulamanız gerekir:

1.  `Microsoft.Intune.MAM.Remapper.Tasks` NuGet paketini ekleyin.

2.  Android csproj projenize aşağıdaki satırı ekleyin (“x.x.x.x” kısmını asıl paket sürümüyle değiştirin):
  ```xml
 <Import Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.x.x.x.x\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
  ```

3.  Eklediğiniz `remapping-config.json` dosyasının derleme eylemini **RemappingConfigFile** olarak ayarlayın. Dahil edilen `remapping-config.json` yalnızca Xamarin.Forms ile çalışır. Diğer UI çerçeveleri için Remapper NuGet paketindeki Benioku dosyasına bakın.

## <a name="next-steps"></a>Sonraki adımlar

Bileşeni uygulamanıza eklemek için temel adımları tamamladınız. Şimdi Xamarin Android örnek uygulamasındaki adımları uygulayabilirsiniz. Biri Xamarin.Forms, diğeri Android için olmak üzere iki örnek sağladık.
