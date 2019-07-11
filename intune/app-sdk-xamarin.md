---
title: Microsoft Intune Uygulama SDK’sı Xamarin Bağlamaları
description: Intune App SDK’sı Xamarin Bağlamaları, Xamarin ile oluşturulan iOS ve Android uygulamalarındaki Intune uygulama koruma ilkesini etkinleştirir.
keywords: sdk, Xamarin, intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/08/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7525971f9ab48b92c3274f56cb1046a6fde948a5
ms.sourcegitcommit: 2614d1b08b8a78cd792aebd2ca9848f391df8550
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67794359"
---
# <a name="microsoft-intune-app-sdk-xamarin-bindings"></a>Microsoft Intune Uygulama SDK’sı Xamarin Bağlamaları

> [!NOTE]
> Öncelikle, desteklenen platformlarda tümleştirme için nasıl hazırlık yapıldığını açıklayan [Intune Uygulama SDK’sını Kullanmaya Başlama](app-sdk-get-started.md) makalesini okumanız önerilir.

## <a name="overview"></a>Genel Bakış
[Intune App SDK’sı Xamarin Bağlamaları](https://github.com/msintuneappsdk/intune-app-sdk-xamarin), Xamarin ile oluşturulan iOS ve Android uygulamalarındaki [Intune uygulama koruma ilkesini](app-protection-policy.md) etkinleştirir. Bu bağlamalar, geliştiricilerin Intune uygulama koruma özelliklerini Xamarin tabanlı uygulamalarına kolayca eklemesini sağlar.

Microsoft Intune Uygulama SDK’sı Xamarin Bağlamaları, Intune uygulama koruma ilkelerini (APP veya MAM ilkeleri olarak da bilinir) Xamarin ile geliştirilen uygulamalarınıza eklemenizi sağlar. MAM özellikli uygulamalar Intune Uygulama SDK’sı ile tümleşiktir. Intune uygulamayı etkin bir şekilde yönetirken, BT yöneticileri mobil uygulamanıza uygulama koruma ilkeleri dağıtabilir.

## <a name="whats-supported"></a>Desteklenen özellikler

### <a name="developer-machines"></a>Geliştirici makineleri
* Windows (Visual Studio sürüm 15.7+)
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

SDK, [kimlik doğrulama](https://azure.microsoft.com/documentation/articles/active-directory-authentication-scenarios/) ve koşullu başlatma senaryoları için [Active Directory Authentication Library (ADAL)](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/) kullanır ve bu sayede uygulamaların [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/)ile yapılandırılması gerekir. 

Uygulamanız zaten ADAL veya MSAL kullanacak şekilde yapılandırıldıysa ve Azure Active Directory kimlik doğrulaması için kendi özel istemci KIMLIĞI kullanılıyorsa, Xamarin uygulama izinlerinizi Intune mobil uygulama yönetimi (MAM) hizmetine verme adımlarının deyiminden. [Intune SDK 'sını kullanmaya başlama](app-sdk-get-started.md)konusunun "[uygulamanızın Intune uygulama koruma hizmeti 'Ne erişmesine izin verme](app-sdk-get-started.md#give-your-app-access-to-the-intune-app-protection-service-optional)" bölümündeki yönergeleri kullanın.

## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>iOS mobil uygulamanızda Intune uygulama koruma ilkelerini etkinleştirme
1. [Microsoft.Intune.MAM.Xamarin.iOS NuGet paketini](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.iOS) Xamain.iOS projenize ekleyin.
2. Intune Uygulama SDK'sını iOS mobil uygulamasına tümleştirmek için gereken genel adımları izleyin. [iOS için Intune Uygulama SDK'si Geliştirici Kılavuzu](app-sdk-ios.md#build-the-sdk-into-your-mobile-app)'nda verilen tümleştirme yönergelerinin 3. adımıyla başlayabilirsiniz. Bu araç, Microsoft.Intune.MAM.Xamarin.iOS paketinde bulunduğu ve derleme sırasında otomatik olarak çalıştırılacağı için IntuneMAMConfigurator’ı çalıştırma bölümündeki son adımı atlayabilirsiniz.
    **Önemli**: Bir uygulama için Anahtarlık paylaşımının etkinleştirilmesi, Visual Studio 'da Xcode 'dan biraz farklıdır. Uygulamanın Yetkilendirmeler plist dosyasını açın, "Anahtarlığı Etkinleştir" seçeneğinin etkinleştirildiğinden ve uygun anahtarlık paylaşım gruplarının bu bölüme eklendiğinden emin olun. Ardından, tüm uygun Yapılandırma/Platform bileşimleri için projenin "iOS Paketi İmzalama" seçeneklerindeki "Özel Yetkilendirmeler" alanında Yetkilendirmeler plist dosyasının belirtildiğinden emin olun.
3. Bağlamalar eklendikten ve uygulama düzgün bir şekilde yapılandırıldıktan sonra, uygulamanız Intune SDK’sının API’lerini kullanmaya başlayabilir. Bunu yapmak için, aşağıdaki ad alanını eklemelisiniz:

      ```csharp
      using Microsoft.Intune.MAM;
      ```

4. Uygulama koruma ilkelerini almaya başlamak için, uygulamanızın Intune MAM hizmetine kaydolması gerekir. Uygulamanız kullanıcıların kimliğini doğrulamak için [Azure Active Directory Authentication Library](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory) (ADAL) veya [Microsoft Authentication Library](https://www.nuget.org/packages/Microsoft.Identity.Client) (MSAL) kullanmıyorsa ve kimlik doğrulamasıyla Intune SDK’sının ilgilenmesini istiyorsanız, IntuneMAMEnrollmentManager’ın LoginAndEnrollAccount yöntemi için uygulamanızın kullanıcıya ait UPN’yi sağlaması gerekir:

      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```

      Çağrı sırasında kullanıcının UPN’si bilinmiyorsa uygulamalar null olarak geçebilir. Bu durumda kullanıcılardan e-posta adreslerini ve parolalarını girmeleri istenir.
      
      Uygulamanız kullanıcıların kimliğini doğrulamak için zaten ADAL veya MSAL kullanılıyorsa, uygulamanız ile Intune SDK’sı arasında çoklu oturum açma (SSO) deneyimi yapılandırabilirsiniz. İlk olarak, belirteçleri iOS için Intune Xamarin Bağlamaları (com.microsoft.adalcache) tarafından kullanılan anahtarlık erişim grubunda depolamak için ADAL/MSAL’ı yapılandırmanız gerekir. ADAL için, [AuthenticationContext 'In ıoskeychainsecuritygroup özelliğini ayarlayarak](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet/wiki/iOS-Keychain-Access)bunu yapabilirsiniz. MSAL için, [PublicClientApplication öğesinin ıoskeychainsecuritygroup özelliğini ayarlamanız](https://github.com/AzureAD/microsoft-authentication-library-for-dotnet/wiki/Xamarin-iOS-specifics#enable-keychain-access)gerekir. Sonrasında, Intune SDK’sı tarafından uygulamanızın ayarlarıyla birlikte kullanılan varsayılan AAD ayarlarını geçersiz kılmanız gerekir. Bunu, [iOS için Intune Uygulama SDK'sı Geliştirici Kılavuzu](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk)'nda belirtildiği gibi uygulamanın Info.plist dosyasındaki IntuneMAMSettings sözlüğü aracılığıyla yapabilirsiniz veya IntuneMAMPolicyManager örneğinin AAD geçersiz kılma özelliklerini kullanabilirsiniz. ADAL ayarları statik olan uygulamalarda Info.plist yaklaşımı önerilirken, bu değerleri çalışma zamanında belirleyen uygulamalar için geçersiz kılma özelliklerinin kullanılması önerilir. Tüm SSO ayarları yapılandırıldığında uygulamanız, başarıyla kimlik doğrulaması yaptıktan sonra IntuneMAMEnrollmentManager’ın RegisterAndEnrollAccount yöntemi için kullanıcının UPN’sini sağlayacaktır:

      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```

      Uygulamalar, IntuneMAMEnrollmentDelegate’in alt sınıflarından birinde EnrollmentRequestWithStatus yöntemini uygulayarak ve IntuneMAMEnrollmentManager’ın Temsilci özelliğini bu sınıfa ait bir örneğe ayarlayarak bir kayıt denemesinin sonucunu belirleyebilir. Örnek için lütfen [örnek Xamarin.iOS uygulamamıza](https://github.com/msintuneappsdk/sample-intune-xamarin-ios) bakın.

      Kayıt başarıyla tamamlandıktan sonra uygulamalar, şu özelliği sorgulayarak kaydedilen hesabın UPN’sini (önceden bilinmiyorsa) belirleyebilir: 

      ```csharp
       string enrolledAccount = IntuneMAMEnrollmentManager.Instance.EnrolledAccount;
      ```      

> [!NOTE] 
> iOS için bir yeniden eşleyici yok. Bir Xamarin.Forms uygulamasıyla tümleştirme, normal bir Xamarin.iOS projesiyle aynı olacaktır. 

## <a name="enabling-intune-app-protection-policies-in-your-android-mobile-app"></a>Android mobil uygulamanızda Intune uygulama koruma ilkelerini etkinleştirme
1. [Microsoft.Intune.MAM.Xamarin.Android NuGet paketini](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android) Xamain.Android projenize ekleyin.
    1. Xamarin. Forms uygulaması için, Xamarin. Android projenize [Microsoft. Intune. mam. remapper. Tasks NuGet paketini](https://www.nuget.org/packages/Microsoft.Intune.MAM.Remapper.Tasks) de ekleyin. 
2. Ek ayrıntılar için bu belgeye başvuru yaparken [, Intune uygulama SDK 'Sını](app-sdk-android.md) Android mobil uygulamasıyla tümleştirmek için gereken genel adımları izleyin.

### <a name="xamarinandroid-integration"></a>Xamarin.Android tümleştirmesi

Intune uygulama SDK 'sını tümleştirmeyle ilgili kapsamlı bir genel bakış [Microsoft Intune, Android Için uygulama SDK 'sı Geliştirici Kılavuzu](app-sdk-android.md)' nda bulunabilir. Kılavuzdan okurken ve Intune uygulama SDK 'sını Xamarin uygulamanızla tümleştirdiğinizde, Java 'da geliştirilen yerel bir Android uygulaması ve içinde C#geliştirilen bir Xamarin uygulaması arasındaki farkları vurgulamak amaçlanmıştır. Bu bölümler ek olarak değerlendirilmelidir ve Kılavuzu tamamen okumak için bir alternatif olarak davranamaz.

#### <a name="remapper"></a>Remapper
1\.4428.1 sürümünden itibaren, `Microsoft.Intune.MAM.Remapper` paket, mam sınıfı, yöntemi ve sistem hizmetleri yerine getirmek için [derleme araçları](app-sdk-android.md#build-tooling) olarak bir Xamarin. Android uygulamasına eklenebilir. Yeniden eşleştirici dahil edildiğinde, yeniden adlandırılmış Yöntemler ve MAM uygulama bölümlerinin MAM denk değiştirme bölümü, uygulama oluşturulduğunda otomatik olarak gerçekleştirilir.

Yeniden eşleştirici tarafından mam bir sınıfı hariç tutmak için, proje `.csproj` dosyanıza aşağıdaki özellik eklenebilir.

```xml
  <PropertyGroup>
    <ExcludeClasses>Semicolon separated list of relative class paths to exclude from MAM-ification</ExcludeClasses>
  </PropertyGroup>
```

#### <a name="renamed-methodsapp-sdk-androidmdrenamed-methods"></a>[Yeniden adlandırılan Yöntemler](app-sdk-android.md#renamed-methods)
Birçok durumda, Android sınıfında kullanılabilir olan bir yöntem, MAM değiştirme sınıfında kesin olarak işaretlenmiştir. Bu durumda, MAM değiştirme sınıfı benzer ada sahip olup geçersiz kılmanız gereken bir yöntem (`MAM` son ekini alır) sağlar. Örneğin, `MAMActivity`’i geçersiz kılıp `OnCreate()` çağırmak yerine `base.OnCreate()`’den türetilirken, `Activity`, `OnMAMCreate()`’i geçersiz kılmalı ve `base.OnMAMCreate()` çağırmalıdır.

#### <a name="mam-applicationapp-sdk-androidmdmamapplication"></a>[MAM uygulaması](app-sdk-android.md#mamapplication)
Uygulamanızda bir `Android.App.Application` sınıf tanımlanmalıdır. MAM el ile tümleştirildiğinde, öğesinden `MAMApplication`devralması gerekir. Alt sınıfınızın `[Application]` özniteliği ile doğru şekilde donatıldığından ve `(IntPtr, JniHandleOwnership)` oluşturucusunu geçersiz kıldığından emin olun.

```csharp
    [Application]
    class TaskrApp : MAMApplication
    {
    public TaskrApp(IntPtr handle, JniHandleOwnership transfer)
        : base(handle, transfer) { }
```

> [!NOTE]
> MAM Xamarin bağlamalarıyla ilgili bir sorun, hata ayıklama modunda dağıtıldığında uygulamanın kilitlenmesine neden olabilir. Geçici bir çözüm olarak, `Debuggable=false` özniteliği `Application` sınıfa eklenmelidir ve `android:debuggable="true"` bayrak el ile ayarlandıysa, bayrağın bildirimden kaldırılması gerekir.

#### <a name="enable-features-that-require-app-participationapp-sdk-androidmdenable-features-that-require-app-participation"></a>[Uygulama katılımı gerektiren özellikleri etkinleştirme](app-sdk-android.md#enable-features-that-require-app-participation)
Örnek: Uygulama için PIN gerekip gerekmediğini belirleme

```csharp
MAMPolicyManager.GetPolicy(currentActivity).IsPinRequired;
```

Örnek: Birincil Intune kullanıcısını belirleme

```csharp
IMAMUserInfo info = MAMComponents.Get<IMAMUserInfo>();
return info?.PrimaryUser;
```

Örnek: Cihaza veya bulut depolamaya kaydetmeye izin verilip verilmediğini belirleme

```csharp
MAMPolicyManager.GetPolicy(currentActivity).GetIsSaveToLocationAllowed(SaveLocation service, String username);
```

#### <a name="register-for-notifications-from-the-sdkapp-sdk-androidmdregister-for-notifications-from-the-sdk"></a>[SDK 'dan gelen bildirimlere kaydolma](app-sdk-android.md#register-for-notifications-from-the-sdk)
Uygulamanız bir `MAMNotificationReceiver` oluşturup ile `MAMNotificationReceiverRegistry`kaydederek SDK 'dan gelen bildirimlere kaydolmalıdır. Bu, aşağıdaki örnekte gösterildiği gibi alıcı ve öğesinde `App.OnMAMCreate`istenen bildirim türü sağlanarak yapılır:

```csharp
public override void OnMAMCreate()
{
    // Register the notification receivers
    IMAMNotificationReceiverRegistry registry = MAMComponents.Get<IMAMNotificationReceiverRegistry>();
    foreach (MAMNotificationType notification in MAMNotificationType.Values())
    {
        registry.RegisterReceiver(new ToastNotificationReceiver(this), notification);
    }
    ...
```

#### <a name="mam-enrollment-managerapp-sdk-androidmdmamenrollmentmanager"></a>[MAM kayıt yöneticisi](app-sdk-android.md#mamenrollmentmanager)

```csharp
IMAMEnrollmentManager mgr = MAMComponents.Get<IMAMEnrollmentManager>();
```

### <a name="xamarinforms-integration"></a>Xamarin.Forms tümleştirmesi

Uygulamalar `Xamarin.Forms` için paket `Microsoft.Intune.MAM.Remapper` , ekleme `MAM` sınıfları tarafından, yaygın olarak kullanılan `Xamarin.Forms` sınıfların Sınıf hiyerarşisine otomatik olarak Mam sınıfı değiştirme işlemini gerçekleştirir. 

> [!NOTE]
> Xamarin. Forms tümleştirmesi, yukarıda açıklanan Xamarin. Android tümleştirmesine ek olarak yapılır.

Yeniden eşleştirici projenize eklendikten sonra, MAM denk değişiklikleri yapmanız gerekir. Örneğin, ve `FormsAppCompatActivity` `FormsApplicationActivity` , uygulamanızda geçersiz kılmaları `OnCreate` sağlayan ve `OnResume` mam eşdeğerlerine `OnMAMCreate` ve `OnMAMResume` sırasıyla değiştirilerek kullanılabilir olmaya devam edebilir.

```csharp
    public class MainActivity : global::Xamarin.Forms.Platform.Android.FormsAppCompatActivity
    {
        protected override void OnMAMCreate(Bundle savedInstanceState)
        {
            base.OnMAMCreate(savedInstanceState);
            global::Xamarin.Forms.Forms.Init(this, savedInstanceState);
            LoadApplication(new App());
        }
```

Değişiklikler yapılmadığından, değişiklikleri yapana kadar aşağıdaki derleme hatalarıyla karşılaşabilirsiniz:
* [Derleyici hatası CS0239](https://docs.microsoft.com/dotnet/csharp/misc/cs0239). Bu hata genellikle bu biçimde ``'MainActivity.OnCreate(Bundle)': cannot override inherited member 'MAMAppCompatActivityBase.OnCreate(Bundle)' because it is sealed``görülür.
Bu, yeniden eşleştirici Xamarin sınıflarının devralınmasını değiştirdiğinde, bazı işlevlerin yapılması `sealed` ve bunun yerine geçersiz kılınmasına yeni bir mam varyantı eklendiği için beklenmektedir.
* [Derleyici Hatası CS0507](https://docs.microsoft.com/dotnet/csharp/language-reference/compiler-messages/cs0507): Bu hata genellikle bu biçimde ``'MyActivity.OnRequestPermissionsResult()' cannot change access modifiers when overriding 'public' inherited member ...``görülür. Remapper, Xamarin sınıflarının bazılarının devralınmasını değiştirdiğinde, bazı üye işlevleri olarak `public`değiştirilir. Bu işlevlerden herhangi birini geçersiz kılarsınız, bu geçersiz kılmaların `public` erişim değiştiricilerini de değiştirmeniz gerekecektir.

> [!NOTE]
> Yeniden Eşleştirici, Visual Studio 'Nun IntelliSense otomatik tamamlama için kullandığı bir bağımlılığı yeniden yazar. Bu nedenle, IntelliSense 'in değişiklikleri doğru tanıması için yeniden eşleştirici eklendiğinde projeyi yeniden yüklemeniz ve yeniden oluşturmanız gerekebilir.

### <a name="company-portal-app"></a>Şirket Portalı uygulaması
Intune SDK 'Sı Xamarin bağlamaları, uygulama koruma ilkelerini etkinleştirmek için cihazda [Şirket portalı](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) Android uygulamasının varlığını kullanır. Şirket Portalı uygulama koruma ilkelerini Intune hizmetinden alır. Uygulama başlatıldığında, ilkeyi ve ilkenin zorlanmasına yönelik kodu Şirket Portalı’dan yükler. Kullanıcının oturum açmış olması gerekmez.

> [!NOTE]
> Şirket Portalı uygulaması **Android** cihazında olmadığında, Intune ile yönetilen bir uygulama, Intune uygulama koruma ilkelerini desteklemeyen normal bir uygulamayla aynı şekilde davranır.

Cihaz kaydı olmadan uygulama koruması için kullanıcının Şirket Portalı uygulamasını kullanarak cihazını kaydetmesi gerekli _**değildir**_ .

### <a name="sample-applications"></a>Örnek uygulamalar
Xamarin. Android ve Xamarin Forms uygulamalarındaki MAM işlevlerini vurgulayan örnek uygulamalar [GitHub](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Xamarin-Android-Apps)' da kullanılabilir.

## <a name="support"></a>Destek
Kuruluşunuz mevcut bir Intune müşterisiyse, lütfen Microsoft destek temsilcisiyle birlikte çalışarak bir destek bileti açın ve [GitHub sorunları sayfasında](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues) bir sorun oluşturun ve mümkün olan en kısa sürede yardım edeceğiz. 
