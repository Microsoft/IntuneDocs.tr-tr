---
title: Microsoft Intune Uygulama SDK’sı Xamarin Bağlamaları
description: Intune App SDK’sı Xamarin Bağlamaları, Xamarin ile oluşturulan iOS ve Android uygulamalarındaki Intune uygulama koruma ilkesini etkinleştirir.
keywords: sdk, Xamarin, intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/08/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: d42fab929d6fa3e7fbaed8e9557573ebbaa1f3ad
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61506806"
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

SDK'ın bağımlı [Active Directory Authentication Library (ADAL)](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/) için kendi [kimlik doğrulaması](https://azure.microsoft.com/documentation/articles/active-directory-authentication-scenarios/) ve koşullu başlatma senaryolarında, uygulamaların ile yapılandırılması gereken [Azure Active Dizin](https://azure.microsoft.com/documentation/articles/active-directory-whatis/). 

Uygulamanız zaten ADAL veya MSAL kullanacak şekilde yapılandırıldı ve kendi özel istemci kimliği Azure Active Directory ile kimlik doğrulaması için kullanılan varsa, Intune mobil uygulama yönetimi (MAM) hizmetine Xamarin uygulama izinleri vermek için adımlar emin olun ardından. Yönergeleri kullanın "[uygulama erişimlerini Intune Uygulama Koruması hizmetine](app-sdk-get-started.md#give-your-app-access-to-the-intune-app-protection-service-optional)" bölümünü [Intune SDK'sı Kılavuzu ile çalışmaya başlama](app-sdk-get-started.md).

## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>iOS mobil uygulamanızda Intune uygulama koruma ilkelerini etkinleştirme
1. [Microsoft.Intune.MAM.Xamarin.iOS NuGet paketini](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.iOS) Xamain.iOS projenize ekleyin.
2.  Intune Uygulama SDK'sını iOS mobil uygulamasına tümleştirmek için gereken genel adımları izleyin. [iOS için Intune Uygulama SDK'si Geliştirici Kılavuzu](app-sdk-ios.md#build-the-sdk-into-your-mobile-app)'nda verilen tümleştirme yönergelerinin 3. adımıyla başlayabilirsiniz. Bu araç, Microsoft.Intune.MAM.Xamarin.iOS paketinde bulunduğu ve derleme sırasında otomatik olarak çalıştırılacağı için IntuneMAMConfigurator’ı çalıştırma bölümündeki son adımı atlayabilirsiniz.
    **Önemli**: Bir uygulama için Anahtarlık paylaşımını etkinleştirdikten Xcode'dan Visual Studio'da biraz farklı olacaktır. Uygulamanın Yetkilendirmeler plist dosyasını açın, "Anahtarlığı Etkinleştir" seçeneğinin etkinleştirildiğinden ve uygun anahtarlık paylaşım gruplarının bu bölüme eklendiğinden emin olun. Ardından, tüm uygun Yapılandırma/Platform bileşimleri için projenin "iOS Paketi İmzalama" seçeneklerindeki "Özel Yetkilendirmeler" alanında Yetkilendirmeler plist dosyasının belirtildiğinden emin olun.
3.  Bağlamalar eklendikten ve uygulama düzgün bir şekilde yapılandırıldıktan sonra, uygulamanız Intune SDK’sının API’lerini kullanmaya başlayabilir. Bunu yapmak için, aşağıdaki ad alanını eklemelisiniz:

      ```csharp
      using Microsoft.Intune.MAM;
      ```
4. Uygulama koruma ilkelerini almaya başlamak için, uygulamanızın Intune MAM hizmetine kaydolması gerekir. Uygulamanız kullanıcıların kimliğini doğrulamak için [Azure Active Directory Authentication Library](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory) (ADAL) veya [Microsoft Authentication Library](https://www.nuget.org/packages/Microsoft.Identity.Client) (MSAL) kullanmıyorsa ve kimlik doğrulamasıyla Intune SDK’sının ilgilenmesini istiyorsanız, IntuneMAMEnrollmentManager’ın LoginAndEnrollAccount yöntemi için uygulamanızın kullanıcıya ait UPN’yi sağlaması gerekir:
      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```
      Çağrı sırasında kullanıcının UPN’si bilinmiyorsa uygulamalar null olarak geçebilir. Bu durumda kullanıcılardan e-posta adreslerini ve parolalarını girmeleri istenir.
      
      Uygulamanız kullanıcıların kimliğini doğrulamak için zaten ADAL veya MSAL kullanılıyorsa, uygulamanız ile Intune SDK’sı arasında çoklu oturum açma (SSO) deneyimi yapılandırabilirsiniz. İlk olarak, belirteçleri iOS için Intune Xamarin Bağlamaları (com.microsoft.adalcache) tarafından kullanılan anahtarlık erişim grubunda depolamak için ADAL/MSAL’ı yapılandırmanız gerekir. ADAL için bunu [AuthenticationContext‘in KeychainSecurityGroup özelliğini ayarlayarak](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet/wiki/Token-cache-serialization#enable-token-cache-sharing-across-ios-applications) yapabilirsiniz. MSAL için ise [PublicClientApplication’ın KeychainSecurityGroup özelliğini ayarlamanız](https://github.com/AzureAD/microsoft-authentication-library-for-dotnet/wiki/msal-net-2-released#you-can-now-enable-sso-between-adal-and-msal-apps-on-xamarinios) gerekir. Sonrasında, Intune SDK’sı tarafından uygulamanızın ayarlarıyla birlikte kullanılan varsayılan AAD ayarlarını geçersiz kılmanız gerekir. Bunu, [iOS için Intune Uygulama SDK'sı Geliştirici Kılavuzu](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk)'nda belirtildiği gibi uygulamanın Info.plist dosyasındaki IntuneMAMSettings sözlüğü aracılığıyla yapabilirsiniz veya IntuneMAMPolicyManager örneğinin AAD geçersiz kılma özelliklerini kullanabilirsiniz. ADAL ayarları statik olan uygulamalarda Info.plist yaklaşımı önerilirken, bu değerleri çalışma zamanında belirleyen uygulamalar için geçersiz kılma özelliklerinin kullanılması önerilir. Tüm SSO ayarları yapılandırıldığında uygulamanız, başarıyla kimlik doğrulaması yaptıktan sonra IntuneMAMEnrollmentManager’ın RegisterAndEnrollAccount yöntemi için kullanıcının UPN’sini sağlayacaktır:
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
    1. Bir Xamarin.Forms uygulaması için ekleme [Microsoft.ıntune.mam.remapper.Tasks NuGet paketini](https://www.nuget.org/packages/Microsoft.Intune.MAM.Remapper.Tasks) Xamarin.Android projenize de. 
2. İçin gerekli genel adımları [Intune uygulama SDK'sını tümleştirme](app-sdk-android.md) ek ayrıntılar için bu belgenin başvurma sırasında bir Android mobil uygulamasına.

### <a name="xamarinandroid-integration"></a>Xamarin.Android tümleştirmesi

Intune uygulama SDK'sını tümleştirmek için eksiksiz bir genel bakış bulunabilir [Android Geliştirici Kılavuzu için Microsoft Intune App SDK](app-sdk-android.md). Yerel bir Android uygulaması Java dilinde geliştirilen ve geliştirilmiş bir Xamarin uygulaması için uygulanması arasındaki farklar vurgulamak için aşağıdaki bölümleri Kılavuzu okuyun ve Intune uygulama SDK'sı Xamarin uygulamanızla tümleştirin yöneliktir C#. Bu bölümlerde, ek olarak değerlendirilmesi gerektiğini ve tamamen kılavuzda okumak için bir alternatif olarak davranamaz.

#### <a name="renamed-methodsapp-sdk-androidmdrenamed-methods"></a>[Yeniden adlandırılan yöntemler](app-sdk-android.md#renamed-methods)
Birçok durumda, Android sınıfında kullanılabilir olan bir yöntem, MAM değiştirme sınıfında kesin olarak işaretlenmiştir. Bu durumda, MAM değiştirme sınıfı benzer ada sahip olup geçersiz kılmanız gereken bir yöntem (`MAM` son ekini alır) sağlar. Örneğin, `MAMActivity`’i geçersiz kılıp `OnCreate()` çağırmak yerine `base.OnCreate()`’den türetilirken, `Activity`, `OnMAMCreate()`’i geçersiz kılmalı ve `base.OnMAMCreate()` çağırmalıdır.

#### <a name="mam-applicationapp-sdk-androidmdmamapplication"></a>[MAM uygulama](app-sdk-android.md#mamapplication)
Uygulamanızı tanımlamalıdır bir `Android.App.Application` öğesinden devralınan sınıf `MAMApplication`. Alt sınıfınızın `[Application]` özniteliği ile doğru şekilde donatıldığından ve `(IntPtr, JniHandleOwnership)` oluşturucusunu geçersiz kıldığından emin olun.
```csharp
    [Application]
    class TaskrApp : MAMApplication
    {
    public TaskrApp(IntPtr handle, JniHandleOwnership transfer)
        : base(handle, transfer) { }
```
> [!NOTE]
> MAM Xamarin bağlamaları ile ilgili bir sorun, uygulamanın hata ayıklama modunda dağıttığınızda çökmesine neden olabilir. Geçici bir çözüm olarak `Debuggable=false` özniteliği eklenmelidir `Application` sınıfı ve `android:debuggable="true"` bayrağı el ile ayarlamanız bildiriminden kaldırılmalıdır.

#### <a name="enable-features-that-require-app-participationapp-sdk-androidmdenable-features-that-require-app-participation"></a>[Uygulama katılımı gerektiren özellikleri etkinleştirme](app-sdk-android.md#enable-features-that-require-app-participation)
Örnek: PIN uygulama için gerekli olup olmadığını belirler
```csharp
MAMPolicyManager.GetPolicy(currentActivity).IsPinRequired;
```
Örnek: Birincil Intune kullanıcısını belirleme
```csharp
IMAMUserInfo info = MAMComponents.Get<IMAMUserInfo>();
return info?.PrimaryUser;
```
Örnek: Cihazı kaydetme belirlemek veya Bulut depolama izin verilir
```csharp
MAMPolicyManager.GetPolicy(currentActivity).GetIsSaveToLocationAllowed(SaveLocation service, String username);
```

#### <a name="register-for-notifications-from-the-sdkapp-sdk-androidmdregister-for-notifications-from-the-sdk"></a>[SDK'dan gelen bildirimlere kaydolması](app-sdk-android.md#register-for-notifications-from-the-sdk)
Uygulamanızı SDK'dan gelen bildirimlere oluşturarak kaydolması gerekir bir `MAMNotificationReceiver` oluşturup `MAMNotificationReceiverRegistry`. Bu alıcı ve öğesinde istenen bildirim türü belirtilerek yapılır `App.OnMAMCreate`aşağıdaki örnekte gösterildiği gibi:
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

#### <a name="mam-enrollment-managerapp-sdk-androidmdmamenrollmentmanager"></a>[MAM kayıt Yöneticisi](app-sdk-android.md#mamenrollmentmanager)
```csharp
IMAMEnrollmentManager mgr = MAMComponents.Get<IMAMEnrollmentManager>();
```

### <a name="xamarinforms-integration"></a>Xamarin.Forms tümleştirmesi

İçin `Xamarin.Forms` uygulamalar olması koşuluyla `Microsoft.Intune.MAM.Remapper` ekleyerek MAM sınıfı yeni otomatik olarak gerçekleştirmek için paket `MAM` sınıf hiyerarşisini, yaygın olarak kullanılan sınıflara `Xamarin.Forms` sınıfları. 

> [!NOTE]
> Buna ek olarak yukarıda ayrıntılı Xamarin.Android tümleştirme için yapılması Xamarin.Forms tümleştirmedir.

Remapper projenize eklendikten sonra MAM eşdeğeri değiştirmeler gerçekleştirmeniz gerekir. Örneğin, `FormsAppCompatActivity` ve `FormsApplicationActivity` sağlanan uygulama geçersiz kılmaları için kullanılmak üzere devam `OnCreate` ve `OnResume` MAM eşdeğerleriyle değiştirilir `OnMAMCreate` ve `OnMAMResume` sırasıyla.

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
Değişiklik yapılmamış durumunda bir değişiklik yapana kadar derleme hatalarla karşılaşabilirsiniz:
* [Derleyici Hatası CS0239](https://docs.microsoft.com/dotnet/csharp/misc/cs0239). Bu hata genellikle bu formda görünen ``'MainActivity.OnCreate(Bundle)': cannot override inherited member 'MAMAppCompatActivityBase.OnCreate(Bundle)' because it is sealed``.
Xamarin sınıfların devralma Remapper değişiklik yaptığında, belirli işlevleri yapıldığı için bu beklenen `sealed` ve bunun yerine geçersiz kılmak için yeni bir MAM değişken eklenir.
* [Derleyici Hatası CS0507](https://docs.microsoft.com/dotnet/csharp/language-reference/compiler-messages/cs0507): Bu hata genellikle bu formda görünen ``'MyActivity.OnRequestPermissionsResult()' cannot change access modifiers when overriding 'public' inherited member ...``. Remapper bazı Xamarin sınıfların devralma değiştiğinde, belirli üye işlevleri değiştirilecek `public`. Bu işlevlerden herhangi birinin geçersiz kılarsanız, bu olması için bu erişim değiştiricileri geçersiz kılmaları değiştirmeniz gerekir `public` de.

> [!NOTE]
> Remapper IntelliSense otomatik tamamlama için Visual Studio kullanan bir bağımlılık yeniden yazar. Bu nedenle, yeniden yükleyin ve doğru şekilde değişiklikleri tanıyabilmesi IntelliSense için Remapper eklendiğinde projeyi yeniden derleyin gerekebilir.

## <a name="support"></a>Destek
Kuruluşunuz var olan bir Intune müşteri ise, Lütfen bir destek bileti açın ve bir sorun oluşturmak için Microsoft desteği temsilcinizle çalışarak [GitHub sorunlar sayfasında](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues) ve size mümkün olduğunca kısa sürede size yardımcı olur. 
