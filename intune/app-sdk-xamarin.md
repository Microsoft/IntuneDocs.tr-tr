---
title: Microsoft Intune Uygulama SDK’sı Xamarin Bağlamaları
description: Intune App SDK’sı Xamarin Bağlamaları, Xamarin ile oluşturulan iOS ve Android uygulamalarındaki Intune uygulama koruma ilkesini etkinleştirir.
keywords: sdk, Xamarin, intune
author: Erikre
manager: dougeby
ms.author: erikre
ms.date: 06/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f8f5e397c314088c7b26edba486f9cbaf9718096
ms.sourcegitcommit: 1eddded65ae9e442dd3bebd16b9428af76a67f34
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2018
ms.locfileid: "35250953"
---
# <a name="microsoft-intune-app-sdk-xamarin-bindings"></a>Microsoft Intune Uygulama SDK’sı Xamarin Bağlamaları

> [!NOTE]
> Öncelikle, desteklenen platformlarda tümleştirme için nasıl hazırlık yapıldığını açıklayan [Intune Uygulama SDK’sını Kullanmaya Başlama](app-sdk-get-started.md) makalesini okumanız önerilir.

## <a name="overview"></a>Genel bakış
[Intune App SDK’sı Xamarin Bağlamaları](https://github.com/msintuneappsdk/intune-app-sdk-xamarin), Xamarin ile oluşturulan iOS ve Android uygulamalarındaki [Intune uygulama koruma ilkesini](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) etkinleştirir. Bu bağlamalar, geliştiricilerin Intune uygulama koruma özelliklerini Xamarin tabanlı uygulamalarına kolayca eklemesini sağlar.

Microsoft Intune Uygulama SDK’sı Xamarin Bağlamaları, Intune uygulama koruma ilkelerini (APP veya MAM ilkeleri olarak da bilinir) Xamarin ile geliştirilen uygulamalarınıza eklemenizi sağlar. MAM özellikli uygulamalar Intune Uygulama SDK’sı ile tümleşiktir. Intune uygulamayı etkin bir şekilde yönetirken, BT yöneticileri mobil uygulamanıza uygulama koruma ilkeleri dağıtabilir.

## <a name="whats-supported"></a>Desteklenen özellikler

### <a name="developer-machines"></a>Geliştirici makineleri
* Windows
* Mac OS


### <a name="mobile-app-platforms"></a>Mobil uygulama platformları
* Android
* iOS


### <a name="intune-mobile-application-management-scenarios"></a>Intune Mobil Uygulama Yönetimi senaryoları

* Intune APP-WE (cihaz kaydı olmadan)
* Intune MDM ile kaydedilen cihazlar
* Üçüncü taraf EMM ile kaydedilen cihazlar

Intune Uygulama SDK’sı Xamarin Bağlamaları ile derlenen Xamarin uygulamaları artık Intune mobil cihaz yönetimi (MDM) ile kaydedilen ve kaydedilmeyen cihazlarda Intune uygulama koruma ilkelerini alabilir.

## <a name="prerequisites"></a>Önkoşullar

[Lisans koşullarını](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20Xamarin%20Component.pdf) gözden geçirin. Kendi kayıtlarınız için lisans koşullarının bir kopyasını yazdırmalı ve saklamalısınız. Intune Uygulama SDK’sı Xamarin Bağlamalarını indirip kullandığınızda bu lisans koşullarını kabul etmiş olursunuz. Kabul etmiyorsanız, yazılımı kullanmayın.

## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>iOS mobil uygulamanızda Intune uygulama koruma ilkelerini etkinleştirme
1. [Microsoft.Intune.MAM.Xamarin.iOS NuGet paketini](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.iOS) Xamain.iOS projenize ekleyin.
2.  Intune Uygulama SDK'sını iOS mobil uygulamasına tümleştirmek için gereken genel adımları izleyin. [iOS için Intune Uygulama SDK'si Geliştirici Kılavuzu](app-sdk-ios.md#build-the-sdk-into-your-mobile-app)'nda verilen tümleştirme yönergelerinin 3. adımıyla başlayabilirsiniz. Bu araç, Microsoft.Intune.MAM.Xamarin.iOS paketinde bulunduğu ve derleme sırasında otomatik olarak çalıştırılacağı için IntuneMAMConfigurator’ı çalıştırma bölümündeki son adımı atlayabilirsiniz.
    **Önemli**: Visual Studio'da uygulama için anahtarlık paylaşımını etkinleştirme işlemi Xcode'dakinden biraz farklıdır. Uygulamanın Yetkilendirmeler plist dosyasını açın, "Anahtarlığı Etkinleştir" seçeneğinin etkinleştirildiğinden ve uygun anahtarlık paylaşım gruplarının bu bölüme eklendiğinden emin olun. Ardından, tüm uygun Yapılandırma/Platform bileşimleri için projenin "iOS Paketi İmzalama" seçeneklerindeki "Özel Yetkilendirmeler" alanında Yetkilendirmeler plist dosyasının belirtildiğinden emin olun.
3.  Bağlamalar eklendikten ve uygulama düzgün bir şekilde yapılandırıldıktan sonra, uygulamanız Intune SDK’sının API’lerini kullanmaya başlayabilir. Bunu yapmak için, aşağıdaki ad alanını eklemelisiniz:

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
      
> [!NOTE] 
> iOS için bir yeniden eşleyici yok. Bir Xamarin.Forms uygulamasıyla tümleştirme, normal bir Xamarin.iOS projesiyle aynı olacaktır. 

## <a name="enabling-intune-app-protection-policies-in-your-android-mobile-app"></a>Android mobil uygulamanızda Intune uygulama koruma ilkelerini etkinleştirme

### <a name="xamarinandroid-integration"></a>Xamarin.Android tümleştirmesi

1. [Microsoft.Intune.MAM.Xamarin.Android NuGet paketinin](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android) son sürümünü Xamain.Android projenize ekleyin. Bu, Intune’un uygulamanızı etkinleştirmesi için gereken başvuruları sağlar.

2. [Android Geliştirici Kılavuzu için Intune Uygulama SDK’sını](app-sdk-android.md) tam olarak okuyun ve uygulayın, şu kısımlara da özellikle dikkat edin:
    1. [Bütün sınıf ve yönetim değişimleri bölümü](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent). 
    2. [MAMApplication bölümü](app-sdk-android.md#mamapplication). Alt sınıfınızın `[Application]` özniteliği ile doğru şekilde donatıldığından ve `(IntPtr, JniHandleOwnership)` oluşturucusunu geçersiz kıldığından emin olun.
    3. [ADAL tümleştirmesi bölümü](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal), uygulamanız AAD’ye karşı kimlik doğrulaması gerçekleştiriyorsa.
    4. [MAM-WE kaydı bölümü](app-sdk-android.md#app-protection-policy-without-device-enrollment), uygulamanıza MAM hizmetinden ilke almak istiyorsanız.

> [!NOTE]
> `Microsoft.Intune.MAM.Xamarin.Android` Bağlamalarındaki [Android Geliştirici Kılavuzu için Intune Uygulama SDK’sından](app-sdk-android.md) eşdeğer API’ler bulmaya çalışırken veya kılavuzdan kod parçacıkları dönüştürürken, Xamarin bağlama oluşturucusunun Android API’lerini şu yollarla değiştirdiğine dikkat edin:
> * Tüm tanımlayıcılar baş harfleri büyük olmak üzere bitişik yazılır (com.foo.bar -> Com.Foo.Bar)
> * Tüm alma/ayarlama işlemleri, özellik işlemlerine dönüştürülür (ör. Foo.getBar() -> Foo.Bar, Foo.setBar("zap") -> Foo.Bar = "zap")
> * Tüm arabirimlerin adının başına “I” karakteri eklenir (FooInterface -> IFooInterface)

### <a name="xamarinforms-integration"></a>Xamarin.Forms tümleştirmesi

**Yukarıdaki adımları tamamlamanın yanında**, `Microsoft.Intune.MAM.Remapper` paketinde sağladığımız `Xamarin.Forms` uygulamaları için. Bu paket, `MAM` sınıflarını `FormsAppCompatActivity` ve `FormsApplicationActivity` gibi yaygın olarak kullanılan `Xamarin.Forms` sınıflarındaki sınıf hiyerarşisine ekleyerek sınıf değişimini sizin için yapar. Böylece `OnMAMCreate` ve `OnMAMResume` gibi işlevlerin MAM eşdeğerleri için geçersiz kılmalar sağlayarak bu sınıfları kullanmaya devam edebilirsiniz. Bunu kullanmak için şunları yapın:

1.  [Microsoft.Intune.MAM.Remapper.Tasks](https://www.nuget.org/packages/Microsoft.Intune.MAM.Remapper.Tasks) NuGet paketini projenize ekleyin. Bu, Intune APP SDK’si Xamarin bağlamalarını siz zaten eklemediyseniz otomatik olarak ekler.

2.  Yukarıdaki 2.2 adımında oluşturduğunuz `MAMApplication` sınıfının `OnMAMCreate`işlevindeki `Xamarin.Forms.Forms.Init(Context, Bundle)` için bir çağrı ekleyin. Intune ile uygulamanız, arka plandayken başlatılabileceği için bu gereklidir.

> [!NOTE]
> Bu işlem, Visual Studio’nun Intellisense otomatik tamamlama için kullandığı bir bağımlılığı yeniden yazdığı için yeniden eşleyici değişiklikleri doğru biçimde algılamak amacıyla Intellisense’i ilk kez çalıştırdıktan sonra Visual Studio’yu yeniden başlatmanız gerekebilir. 


## <a name="support"></a>Support

Kuruluşunuz zaten bir Intune müşterisiyse destek bileti açmak ve [GitHub sorunlar sayfasında](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues) bir sorun bileti oluşturmak için Microsoft desteği temsilcinizle birlikte çalışın, mümkün olduğunca kısa sürede size yardım ederiz. 
