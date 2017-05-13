---
title: "iOS için Microsoft Intune Uygulama SDK’sı geliştirici kılavuzu | Microsoft Docs"
description: "iOS için Microsoft Intune Uygulama SDK’sı, Intune uygulama koruma ilkelerini mobil uygulama yönetimi (MAM) biçiminde iOS uygulamanıza eklemenizi sağlar."
keywords: 
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df54ac3a62b5ef21e8a32f3a282dd5299974a1b0
ms.openlocfilehash: 1d2cb0d4b9442262c562e559a675f5a4a28ee572
ms.contentlocale: tr-tr
ms.lasthandoff: 05/03/2017


---

# <a name="microsoft-intune-app-sdk-for-ios-developer-guide"></a>iOS için Microsoft Intune Uygulama SDK’sı geliştirici kılavuzu

> [!NOTE]
> Öncelikle, desteklenen platformlarda tümleştirme için hazırlığın nasıl yapıldığını açıklayan [Intune Uygulama SDK’sını Kullanmaya Başlama Kılavuzu](intune-app-sdk-get-started.md) makalesini okumanız önerilir.

iOS için Microsoft Intune Uygulama SDK’sı, Intune uygulama koruma ilkelerini (**APP** veya **MAM ilkeleri** olarak da bilinir) yerel iOS uygulamanıza eklemenizi sağlar. MAM özellikli uygulamalar Intune Uygulama SDK’sı ile tümleşik çalışır. Intune uygulamayı etkin bir şekilde yönetirken, BT yöneticileri mobil uygulamanıza uygulama koruma ilkeleri dağıtabilir.

## <a name="prerequisites"></a>Önkoşullar

* Xcode 8 veya üzeri yüklü olan ve OS X 10.8.5 ya da üzerini çalıştıran bir Mac OS bilgisayara ihtiyaç duyacaksınız.

* Uygulamanızda iOS 9 veya üstü hedeflenmelidir.

* [iOS için Intune Uygulama SDK’sı Lisans Koşulları](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20for%20iOS%20.pdf)’nı gözden geçirmelisiniz. Kendi kayıtlarınız için lisans koşullarının bir kopyasını yazdırmalı ve saklamalısınız. iOS için Intune Uygulama SDK'sını indirip kullandığınızda bu lisans koşullarını kabul etmiş olursunuz.  Kabul etmiyorsanız, yazılımı kullanmayın.

* iOS için Intune Uygulama SDK'sı dosyalarını [GitHub](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)’dan indirin.

## <a name="whats-in-the-sdk"></a>SDK’nın kapsamı

iOS için Intune Uygulama SDK’sı statik bir kitaplık, kaynak dosyaları, API üst bilgileri, hata ayıklama ayarları .plist dosyası ve bir yapılandırıcı aracı içerir. Mobil uygulamalar yalnızca kaynak dosyaları içerebilir ve çoğu ilke zorlaması için kitaplıklarla statik bağlantılar oluşturabilir. Gelişmiş Intune MAM özellikleri API'ler aracılığıyla zorunlu kılınır.

Bu kılavuzda, iOS için Intune Uygulama SDK'sının aşağıdaki bileşenlerinin kullanımı açıklanır:

* **libIntuneMAM.a**: Intune Uygulama SDK’sı statik kitaplığı. Uygulamanızda uzantılar kullanılmıyorsa, uygulamanızı Intune mobil uygulama yönetimi için etkinleştirmek üzere bu kitaplığı projenize bağlayın.

* **IntuneMAM.framework**: Intune Uygulama SDK’sı çerçevesi. Uygulamanızı Intune mobil uygulama yönetimi için etkinleştirmek üzere bu çerçeveyi projenize bağlayın. Uygulamanızda uzantılar kullanılıyorsa, projenizin birden çok statik kitaplık kopyası oluşturmasını önlemek için statik kitaplık yerine bu çerçeveyi kullanın.

* **IntuneMAMResources.bundle**: SDK’nın bağımlı olduğu kaynakları içeren bir kaynak paketi.

* **Üst bilgiler**: Intune Uygulama SDK'sı API'lerini gösterir. API kullanırsanız, API’yi içeren üst bilgi dosyasını dahil etmeniz gerekir. Aşağıdaki üst bilgi dosyaları, Intune Uygulama SDK'sının işlevselliğini etkinleştirmek için gereken API işlev çağrılarını içerir:

    * IntuneMAMAsyncResult.h
    * IntuneMAMDataProtectionInfo.h
    * IntuneMAMDataProtectionManager.h
    * IntuneMAMFileProtectionInfo.h
    * IntuneMAMFileProtectionManager.h
    * IntuneMAMPolicyDelegate.h
    * IntuneMAMLogger.h


## <a name="how-the-intune-app-sdk-works"></a>Intune Uygulama SDK’sı nasıl çalışır?

iOS için Intune Uygulama SDK'sının amacı, kodda minimum düzeyde değişiklik yaparak iOS uygulamalarına yönetim özellikleri eklemeyi sağlamaktır. Daha az kod değişikliği vardır ve pazara ulaşma süresi daha kısadır ancak mobil uygulamanızın tutarlılığı ve kararlılığı yine de etkilenmez.


## <a name="build-the-sdk-into-your-mobile-app"></a>Mobil uygulamanızda SDK oluşturma

Intune Uygulama SDK'sını etkinleştirmek için aşağıdaki adımları izleyin:

1. **1. Seçenek (önerilir)**: `IntuneMAM.framework` çerçevesini projenize bağlayın. `IntuneMAM.framework` öğesini proje hedefinin **Bağlantılı Çerçeveler ve Kitaplıklar** listesine sürükleyin.

    > [!NOTE]
    > Çerçeveyi kullanırsanız, uygulamanızı App Store’a göndermeden önce evrensel çerçeveden simülatör mimarilerini kendiniz çıkarmanız gerekir. Diğer ayrıntılar için bkz. [Uygulamanızı App Store’a gönderme](#Submit-your-app-to-the-App-Store).

2. **2. Seçenek**: `libIntuneMAM.a` kitaplığına bağlanın. `libIntuneMAM.a` kitaplığını proje hedefinin **Bağlantılı Çerçeveler ve Kitaplıklar** listesine sürükleyin.

    ![Intune Uygulama SDK’sı iOS: bağlantılı çerçeveler ve kitaplıklar](../media/intune-app-sdk-ios-linked-frameworks-and-libraries.png)

    > [!NOTE]
    > Uygulamanızı App Store’da yayınlamayı planlıyorsanız, lütfen hata ayıklama sürümünü değil yayın için oluşturulan `libIntuneMAM.a` sürümünü kullanın. Yayın sürümü, **sürüm** klasöründe olacaktır. Hata ayıklama sürümünün, Intune Uygulama SDK'sında sorunları gidermeye yardımcı olan ayrıntılı bir çıkışı vardır.

    `{PATH_TO_LIB}` öğesini Intune Uygulama SDK'sı konumu ile değiştirerek `-force_load {PATH_TO_LIB}/libIntuneMAM.a` öğesini aşağıdakilerden birine ekleyin:
      * Projenin `OTHER_LDFLAGS` derlemesi yapılandırma ayarı
      * Kullanıcı arabiriminin **Diğer Bağlayıcı Bayrakları**

        > [!NOTE]
        > `PATH_TO_LIB` öğesini bulmak için `libIntuneMAM.a` dosyasını seçin ve ardından **Dosya** menüsünde **Bilgi Al** öğesini seçin. **Nerede** bilgisini (yol) **Bilgi** penceresinin **Genel** bölümünden kopyalayıp yapıştırın.

3. Aşağıdaki iOS çerçevelerini projeye ekleyin:
    * MessageUI.framework
    * Security.framework
    * MobileCoreServices.framework
    * SystemConfiguration.framework
    * libsqlite3.tbd
    * libc++.tbd
    * ImageIO.framework
    * LocalAuthentication.framework
    * AudioToolbox.framework


4. `IntuneMAMResources.bundle` kaynak paketini **Derleme Aşamaları** içindeki **Paket Kaynaklarını Kopyala** altına sürükleyerek kaynak paketini projeye ekleyin.

    ![Intune Uygulama SDK’sı iOS - paket kaynaklarını kopyalama](../media/intune-app-sdk-ios-copy-bundle-resources.png)

5. Mobil uygulamanız, Info.plist dosyası içinde bir ana nib veya görsel taslak dosyası tanımlıyorsa **Ana Görsel Taslak** veya **Ana Nib** alanlarını kesin. Info.plist dosyasında, bu değerleri ve bunlara karşılık gelen değerleri **IntuneMAMSettings** adlı yeni bir sözlük altına aşağıdaki anahtar adlarından uygun olanıyla birlikte yapıştırın:
    * MainStoryboardFile
    * MainStoryboardFile~ipad
    * MainNibFile
    * MainNibFile~ipad
    > [!NOTE]
  > Mobil uygulamanız, Info.plist dosyasında bir ana nib veya görsel taslak dosyası tanımlamıyorsa bu ayarlar gerekli değildir.

    Dosya gövdesinin herhangi bir yerine sağ tıklayıp, görünüm türünü **Ham Anahtarları/Değerleri Göster** olarak değiştirerek Info.plist dosyasını ham biçimde görüntüleyebilirsiniz (anahtar adlarını görmek için).

6. Her proje hedefinde **Özellikler**’i seçip **Anahtarlık Paylaşımı** anahtarını etkinleştirerek anahtarlık paylaşımını etkinleştirin (önceden etkinleştirilmemişse). Anahtarlık paylaşımı, sonraki adıma devam edebilmeniz için gereklidir.

  > [!NOTE]
    > Sağlama profilinizin, yeni anahtarlık paylaşımı değerlerini desteklemesi gerekir. Anahtarlık erişim grupları bir joker karakteri desteklemelidir. Bunu denetlemek için .mobileprovision dosyasını bir metin düzenleyicide açıp **keychain-access-groups** araması yapın ve bir joker karakter kullandığınızdan emin olun. Örneğin:
    ```xml
    <key>keychain-access-groups</key>
    <array>
    <string>YOURBUNDLESEEDID.*</string>
    </array>
    ```

7. Anahtarlık paylaşımını etkinleştirdikten sonra Intune Uygulama SDK'sının verilerini depolayacağı ayrı bir erişim grubu oluşturmak için aşağıdaki adımları izleyin. Kullanıcı arabirimini veya yetkilendirmeler dosyasını kullanarak bir anahtarlık erişim grubu oluşturabilirsiniz. Anahtarlık erişim grubunu oluşturmak için kullanıcı arabirimini kullanıyorsanız, aşağıdaki adımları izlediğinizden emin olun:

    1. Mobil uygulamanızda tanımlanmış bir anahtarlık erişim grubu yoksa, uygulamanın paket kimliğini ilk grup olarak ekleyin.

    2. `com.microsoft.intune.mam` paylaşılan anahtarlık grubunu mevcut erişim gruplarınıza ekleyin. Intune Uygulama SDK'sı verileri depolamak için bu erişim grubunu kullanır.

    3. `com.microsoft.adalcache` öğesini mevcut erişim gruplarınıza ekleyin.

        4. `com.microsoft.workplacejoin` öğesini mevcut erişim gruplarınıza ekleyin.
            ![Intune Uygulama SDK’sı iOS: anahtarlık paylaşımı](../media/intune-app-sdk-ios-keychain-sharing.png)

      5. Anahtarlık paylaşımı erişim grubunu oluşturmak için yetkilendirme dosyasını kullanıyorsanız, yetkilendirme dosyasında anahtarlık erişim grubunun başına `$(AppIdentifierPrefix)` ekleyin. Örneğin:

            * `$(AppIdentifierPrefix)com.microsoft.intune.mam`
            * `$(AppIdentifierPrefix)com.microsoft.adalcache`

    > [!NOTE]
    > Yetkilendirme dosyası mobil uygulamanıza özel, benzersiz bir XML dosyasıdır. iOS uygulamanızda özel izinleri ve özellikleri belirtmek için kullanılır.

7. Uygulama URL şemalarını Info.plist dosyasında tanımlıyorsa, her URL şeması için `-intunemam` sonekiyle başka bir şema ekleyin.

8. iOS 9+ için geliştirilen mobil uygulamalarda, uygulamanızın geçtiği her protokolü, uygulamanızın Info.plist dosyasının `LSApplicationQueriesSchemes` dizisinde bulunan `UIApplication canOpenURL` öğesine dahil edin. Ayrıca, listelenen her protokol için yeni bir protokol ekleyin ve bu protokolün sonuna `-intunemam` ekleyin. Diziye ayrıca `http-intunemam`, `https-intunemam`ve `ms-outlook-intunemam` öğelerini de dahil etmeniz gerekir.

9. Uygulamanın yetkilendirmelerinde tanımlanan uygulama grupları varsa, bu grupları `AppGroupIdentifiers` anahtarı altındaki **IntuneMAMSettings** sözlüğüne bir dize dizisi olarak ekleyin.



## <a name="configure-azure-active-directory-authentication-library-adal"></a>Azure Active Directory Authentication Library’yi (ADAL) Yapılandırma

Intune Uygulama SDK’sı kimlik doğrulama ve koşullu başlatma senaryolarında [Azure Active Directory Authentication Library](https://github.com/AzureAD/azure-activedirectory-library-for-objc)’yi kullanır. Cihaz kayıt senaryoları olmadan yönetim için MAM hizmetinde kullanıcı kimliğini kaydetmek için de ADAL kullanır.

ADAL normal olarak, uygulamaya verilen belirteçlerin güvenliğini sağlamak için uygulamaların Azure Active Directory (AAD) ile kaydedilmesini ve benzersiz kimlik (İstemci Kimliği) ile diğer tanımlayıcıları almasını gerektirir. Başka türlü belirtilmediği sürece, Intune Uygulama SDK’sı Azure AD ile iletişim kurarken varsayılan kayıt değerlerini kullanır.  

Uygulamanız kullanıcıların kimliğini doğrulamak için zaten ADAL kullanıyorsa, uygulamanın mevcut kayıt değerlerini kullanması ve Intune Uygulama SDK'sının varsayılan değerlerini geçersiz kılması gerekir. Bu, kullanıcılardan iki kez kimlik doğrulaması (Intune Uygulama SDK'sı ve uygulama tarafından) istenmemesini sağlar.

### <a name="recommendations"></a>Öneriler

Uygulamanızın ana dalı üzerindeki [ADAL’ın en son sürümüne](https://github.com/AzureAD/azure-activedirectory-library-for-objc/releases) bağlanması önerilir. Intune Uygulama SDK'sı şu anda koşullu erişim gerektiren uygulamaları desteklemek için ADAL’ın aracı dalını kullanır. (Dolayısıyla bu uygulamalar Microsoft Authenticator uygulamasına bağımlıdır.) Ancak, SDK hala ADAL’ın ana dalı ile uyumludur. Uygulamanıza uygun olan dalı kullanın.

### <a name="link-to-adal-binaries"></a>ADAL ikili dosyalarına bağlanma

Uygulamanızı ADAL ikili dosyalarına bağlamak için aşağıdaki adımları izleyin:

1. GitHub’dan [Objective-C için Azure Active Directory Authentication Library (ADAL)](https://github.com/AzureAD/azure-activedirectory-library-for-objc) öğesini indirin, ardından Git alt modüllerini veya CocoaPods kullanarak ADAL’ı indirme [yönergelerini](https://github.com/AzureAD/azure-activedirectory-library-for-objc/blob/master/README.md) izleyin.

2. `ADALiOSBundle.bundle` kaynak paketini **Derleme Aşamaları** içindeki **Paket Kaynaklarını Kopyala** altına sürükleyerek kaynak paketini projeye ekleyin.

3. `-force_load {PATH_TO_LIB}/libADALiOS.a` seçeneğini projenin `OTHER_LDFLAGS` derleme yapılandırma ayarına veya kullanıcı arabirimindeki **Diğer Bağlayıcı Bayraklar** seçeneğine ekleyin. `PATH_TO_LIB`, ADAL ikili dosyalarının konumuyla değiştirilmelidir.



### <a name="share-the-adal-token-cache-with-other-apps-signed-with-the-same-provisioning-profile"></a>Aynı sağlama profiliyle imzalanan diğer uygulamalarla ADAL belirteç önbelleği paylaşılır mı?**

ADAL belirteçlerini aynı sağlama profiliyle imzalanan uygulamalar arasında paylaşmak istiyorsanız aşağıdaki yönergeleri izleyin:

1. Uygulamanızda tanımlanmış bir anahtarlık erişim grubu yoksa, uygulamanın paket kimliğini ilk grup olarak ekleyin.

2. Anahtarlık yetkilendirmelerine `com.microsoft.adalcache` ve `com.microsoft.workplacejoin` erişim gruplarını ekleyerek ADAL çoklu oturum açma (SSO) ayarını etkinleştirin.

3. ADAL paylaşımlı önbellek anahtarlık grubunu açıkça ayarlıyorsanız, ayarın `<app_id_prefix>.com.microsoft.adalcache` olduğundan emin olun. Bu ayarı geçersiz kılmadığınız sürece ADAL bunu sizin için ayarlar. `com.microsoft.adalcache` öğesini değiştirmek için özel bir anahtarlık grubu belirtmek isterseniz, bunu IntuneMAMSettings altındaki Info.plist dosyası içinde `ADALCacheKeychainGroupOverride` anahtarını kullanarak belirtin.

### <a name="configure-adal-settings-for-the-intune-app-sdk"></a>Intune Uygulama SDK’sı için ADAL ayarlarını yapılandırma

Uygulamanız kimlik doğrulaması için zaten ADAL kullanıyorsa ve kendi ADAL ayarları varsa, Intune Uygulama SDK’sını Azure Active Directory ile kimlik doğrulaması sırasında aynı ayarları kullanmaya zorlayabilirsiniz. Bu işlem, uygulamanın kullanıcıdan iki kez kimlik doğrulaması istememesini sağlar. Aşağıdaki ayarları doldurma konusunda bilgi için bkz. [Intune Uygulama SDK’sı için ayarları yapılandırma](#configure-settings-for-the-intune-app-sdk):  

* ADALClientId
* ADALAuthority
* ADALRedirectUri
* ADALRedirectScheme
* ADALCacheKeychainGroupOverride

Uygulamanız zaten ADAL kullanıyorsa, aşağıdaki yapılandırmalar gereklidir:

1. Projenin Info.plist dosyasında, anahtar adı `ADALClientId` olan **IntuneMAMSettings** sözlüğünün altında, ADAL çağrıları için kullanılacak istemci kimliği değerini belirtin.

2. Yine anahtar adı `ADALAuthority` olan **IntuneMAMSettings** sözlüğünün altında, Azure AD yetkilisini belirtin.

3. Anahtar adı `ADALRedirectUri` olan **IntuneMAMSettings** sözlüğünün altında, ADAL çağrıları için kullanılacak yeniden yönlendirme URI’sini de belirtin. Ayrıca, uygulamanızın yeniden yönlendirme URI’sinin biçimine bağlı olarak `ADALRedirectScheme` belirtmeniz gerekebilir.


Bunlara ek olarak, çalışma zamanında kiracıya özgü URL ile Azure AD yetkilisi URL’sini geçersiz kılabilirsiniz. Bunu yapmak için, `IntuneMAMPolicyManager` örneğinde `aadAuthorityUriOverride` özelliğini ayarlamanız yeterli olur.

> [!NOTE]
> SDK’nın uygulama tarafından getirilen ADAL yenileme belirtecini yeniden kullanmasına izin vermek amacıyla [cihaz kaydı içermeyen APP](#App-protection-policy-without-device-enrollment) için AAD Yetkilisi URL’sinin ayarlanması gereklidir.

SDK, değerin temizlenmemesi veya değiştirilmemesi durumunda ilke yenileme ve bunu takip eden kayıt istekleri için bu yetkilendirme URL’sini kullanmaya devam eder.  Dolayısıyla, yönetilen bir kullanıcı uygulamada oturumu kapattığında değeri temizlemek ve yeni bir yönetilen kullanıcı oturum açtığında değeri sıfırlamak önemlidir.

### <a name="if-your-app-does-not-use-adal"></a>Uygulamanız ADAL kullanmıyorsa

Uygulamanız ADAL kullanmıyorsa, Intune Uygulama SDK'sı ADAL parametrelerinin varsayılan değerlerini sağlar ve Azure AD kimlik doğrulamasını gerçekleştirir. Yukarıda listelenen ADAL ayarları için herhangi bir değer belirtmeniz gerekmez.

## <a name="app-protection-policy-without-device-enrollment"></a>Cihaz kaydı olmadan uygulama koruma ilkesi

### <a name="overview"></a>Genel bakış
**APP-WE** veya MAM-WE olarak da bilinen cihaz kaydı olmadan Intune uygulama koruma ilkesi, cihazın Intune mobil cihaz yönetimine (MDM) kaydolmasına gerek kalmadan uygulamaların Intune tarafından yönetilmesine olanak tanır. Bu yeni işlevselliği desteklemek için, uygulamanın kullanıcı hesaplarının yönetim için kaydedilmesine katılması gerekir. Yeni API'leri kullanmak için şu adımları izleyin:

1. Cihaz kaydıyla veya cihaz kaydı olmadan uygulamaların yönetilmesini destekleyen son Intune Uygulama SDK’sı sürümünü kullanın.

2. API’leri çağıran tüm dosyalara IntuneMAMEnrollment.h ekleyin.

### <a name="register-user-accounts"></a>Kullanıcı hesaplarını kaydetme

Uygulama belirtilen kullanıcı hesabı adına APP-WE hizmetine kaydolduysa, Intune hizmetinden uygulama koruma ilkesini alabilir. Yeni oturum açan tüm kullanıcıları SDK'ya kaydetmek uygulamanın sorumluluğundadır. Yeni kullanıcı hesabının kimliği doğrulandıktan sonra uygulama, Headers/IntuneMAMEnrollment.h içindeki `registerAndEnrollAccount` yöntemini çağırmalıdır:

```objc
/**


 *  This method will add the account to the list of registered accounts.
 *  An enrollment request will immediately be started.
 *  @param identity The UPN of the account to be registered with the SDK
 */

(void)registerAndEnrollAccount:(NSString *)identity;

```
SDK, `registerAndEnrollAccount` yöntemini çağırarak kullanıcı hesabını kaydeder ve uygulamayı bu hesap adına kaydetmeyi dener. Kayıt işlemi herhangi bir nedenle başarısız olursa SDK, kayıt işlemini 24 saat sonra otomatik olarak yeniden dener. Uygulama, hata ayıklama için bir temsilci yoluyla herhangi bir kayıt isteğinin sonuçlarıyla ilgili bildirim alabilir.

Bu API çağrıldıktan sonra, uygulama normal çalışmasına devam edebilir. Kayıt başarılı olursa, SDK kullanıcıya uygulamanın yeniden başlatılması gerektiğini bildirir. Bu sırada, kullanıcı uygulamayı hemen yeniden başlatabilir.

### <a name="deregister-user-accounts"></a>Kullanıcı hesaplarının kaydını kaldırma

Kullanıcı bir uygulamanın oturumunu kapatmadan önce, uygulamanın kullanıcı SDK kaydını kaldırması gerekir. Bu şunları sağlar:

1. Kullanıcının hesabında artık yeniden kayıt denemeleri gerçekleştirilmez.

2. Uygulama koruma İlkesi kaldırılır.

3. Uygulama seçmeli temizleme işlemi başlatırsa (isteğe bağlı), tüm şirket verileri silinir.

Kullanıcı oturumunu kapatmadan önce, uygulamanın `Headers/IntuneMAMEnrollment.h` içinde şu API’yi çağırması gerekir:

```objc
/*
 *  This method will remove the provided account from the list of
 *  registered accounts.  Once removed, if the account has enrolled
 *  the application, the account will be un-enrolled.
 *  @note In the case where an un-enroll is required, this method will block
 *  until the Intune MAM AAD token is acquired, then return.  This method must be called before  
 *  the user is removed from the application (so that required AAD tokens are not purged
 *  before this method is called).
 *  @param identity The UPN of the account to be removed.
 *  @param doWipe   If YES, a selective wipe if the account is un-enrolled
 */

(void)deRegisterAndUnenrollAccount:(NSString *)identity withWipe:(BOOL)doWipe;
```

Bu yöntem, kullanıcı hesabının Azure AD belirteçleri silinmeden önce çağrılmalıdır. SDK’nın kullanıcı adına APP-WE hizmetinden belirli isteklerde bulunabilmesi için kullanıcı hesabının AAD belirteçlerine ihtiyacı vardır.

Uygulama kendi kendine kullanıcının şirket verilerini silecekse, `doWipe` bayrağı false olarak ayarlanabilir. Aksi takdirde uygulama, seçmeli temizleme işlemini SDK’nın başlatmasını sağlayabilir. Bu, uygulamanın seçmeli temizleme temsilcisine çağrı yapılmasına neden olur.

```objc
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@”user@foo.com” withWipe:YES];
```

### <a name="apps-that-do-not-use-adal"></a>ADAL kullanmayan uygulamalar

Kullanıcının oturumu açılırken ADAL kullanmayan uygulamalar, bu kimlik doğrulamasını SDK’nın işlemesi için API’yi çağırarak yine de Intune hizmetinden uygulama koruma ilkesini alabilir. Azure AD ile bir kullanıcının kimlik doğrulamasını gerçekleştirmeyip, yine de verilerin korunmasına yardımcı olmak için uygulama koruma ilkesini alması gereken uygulamaların bu tekniği kullanması gerekir. Örneğin uygulamada oturum açmak için başka bir kimlik doğrulaması hizmeti kullanılıyor veya uygulama oturum açmayı hiç desteklemiyorsa. Bunu yapmak için uygulama Headers/IntuneMAMEnrollment.h içindeki `loginAndEnrollAccount` yöntemini çağırmalıdır:

```objc
/**
 *  Creates an enrollment request which is started immediately.
 *  If no token can be retrieved for the identity, the user will be prompted
 *  to enter their credentials, after which enrollment will be retried.
 *  @param identity The UPN of the account to be logged in and enrolled.
 */
 (void)loginAndEnrollAccount: (NSString *)identity;

```

Mevcut herhangi bir belirteç bulunamazsa, SDK bu yöntemi çağırarak kullanıcıdan kimlik bilgilerini ister. Ardından SDK, sağlanan kullanıcı hesabı adına uygulamayı APP-WE hizmetine kaydetmeyi dener. Yöntem, "nil" kimliği ile çağrılabilir. Bu durumda SDK cihazdaki mevcut yönetilen kullanıcıyı kaydeder veya mevcut kullanıcı bulunamazsa kullanıcıdan kullanıcı adı girmesini ister.

Kayıt başarısız olursa, uygulama hatanın ayrıntılarına bağlı olarak bu API’yi gelecekte yeniden çağırmayı göz önünde bulundurmalıdır. Uygulama, bir temsilci yoluyla herhangi bir kayıt isteğinin sonuçlarıyla ilgili [bildirimler](#Status-result-and-debug-notifications) alabilir.

Bu API çağrıldıktan sonra, uygulama normal çalışmasına devam edebilir. Kayıt başarılı olursa, SDK kullanıcıya uygulamanın yeniden başlatılması gerektiğini bildirir.

## <a name="status-result-and-debug-notifications"></a>Durum, sonuç ve hata ayıklama bildirimleri

Uygulama, Intune MAM hizmetine yapılan aşağıdaki istekler hakkında durum, sonuç ve hata ayıklama bildirimleri alabilir:

 - Kayıt istekleri
 - İlke güncelleştirme istekleri
 - Kayıt kaldırma istekleri

Bildirimler, `Headers/IntuneMAMEnrollmentDelegate.h` içinde temsilci yöntemleriyle sunulur:

```objc
/**
 *  Called when an enrollment request operation is completed.
 * @param status status object containing debug information
 */

(void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

/**
 *  Called when a MAM policy request operation is completed.
 *  @param status status object containing debug information
 */
(void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

/**
 *  Called when a un-enroll request operation is completed.
 *  @Note: when a user is un-enrolled, the user is also de-registered with the SDK
 *  @param status status object containing debug information
 */

(void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

```

Bu temsilci yöntemleri aşağıdaki bilgileri içeren bir `IntuneMAMEnrollmentStatus` nesnesi getirir:

- İstekle ilişkilendirilmiş hesabın kimliği
- İsteğin sonucunu gösteren bir durum kodu
- Durum kodunun açıklamasını içeren bir hata dizesi
- Bir `NSError` nesnesi

Bu nesne, döndürülebilecek belirli durum kodlarıyla birlikte `IntuneMAMEnrollmentStatus.h` içinde tanımlanır.


### <a name="sample-code"></a>Örnek kod

Aşağıdakiler temsilci yöntemlerinin örnek uygulamalarıdır:

```objc
- (void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"enrollment result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}


- (void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"policy check-in result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

- (void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"un-enroll result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

```

## <a name="app-restart"></a>Uygulamayı yeniden başlatma

Bir uygulamada uygulama koruma ilkeleri ilk kez alındığında, gerekli kancaları uygulamak için yeniden başlatılması gerekir. Bir uygulamaya yeniden başlatma gerekliliğini bildirmek için SDK, Headers/IntuneMAMPolicyDelegate.h içinde bir temsilci yöntemi sağlar.

```objc
 - (BOOL) restartApplication
```
Bu yöntemin dönüş değeri, uygulamanın gerekli yeniden başlatma işlemini uygulayıp uygulayamayacağını SDK’ya bildirmelidir:   

 - Dönüş değeri true olursa, uygulama yeniden başlatma işlemini kendi yapmalıdır.   

 - Dönüş değeri false olursa, SDK uygulamayı bu yöntemin dönüşünün ardından yeniden başlatır. SDK hemen, kullanıcıya uygulamayı yeniden başlatmasını belirten bir iletişim kutusu gösterir.

## <a name="customize-your-apps-behavior"></a>Uygulamanızın davranışını özelleştirme

Intune Uygulama SDK’sının, uygulamaya dağıtılan uygulama koruma ilkesi hakkında bilgi almak için çağırabileceğiniz çeşitli API’leri vardır. Bu verileri kullanarak uygulamanızın davranışını özelleştirebilirsiniz. Uygulama koruma ilkesi ayarlarının çoğu, uygulama değil SDK tarafından otomatik olarak zorunlu tutulur. Uygulamanın gerçekleştirmesi gereken tek ayar, Farklı kaydet denetimidir.

### <a name="get-app-protection-policy"></a>Uygulama koruma ilkesini alma

#### <a name="intunemampolicymanagerh"></a>IntuneMAMPolicyManager.h
IntuneMAMPolicyManager sınıfı, uygulamaya dağıtılan uygulama koruma ilkesini ortaya koyar. Özellikle, [Çoklu kimliği etkinleştirme](#-enable-multi-identity-optional) işlemi için yararlı olan API’leri ortaya koyar.

#### <a name="intunemampolicyh"></a>IntuneMAMPolicy.h
IntuneMAMPolicy sınıfı, uygulamaya dağıtılan uygulama koruma ilkesini ortaya koyar. Bu sınıfta ortaya konan ilke ayarlarının çoğu SDK tarafından zorunlu tutulur, ama ilke ayarlarının nasıl zorlandığını temel alarak uygulamanızın davranışını her zaman özelleştirebilirsiniz.

Bu sınıf, sonraki bölümde ayrıntılı olarak açıklanan Farklı kaydet denetimlerini uygulamak için gereken bazı API’leri ortaya koyar.

### <a name="implement-save-as-controls"></a>Farklı kaydet denetimlerini uygulama

Intune, BT yöneticilerinin yönetilen bir uygulamanın verilerini hangi depolama konumlarına kaydedebileceğini seçmesine olanak tanır. Uygulamalar izin verilen depolama konumları için **IntuneMAMPolicy.h** içinde tanımlanan **isSaveToAllowedForLocation** API’sini kullanarak Intune’u sorgulayabilir.

Yönetilen verileri bulut depolama alanı veya yerel konumlara kaydetmeden önce, BT yöneticisinin o konuma veri kaydedilmesine izin verip vermediğini öğrenmek için uygulamalar **isSaveToAllowedForLocation** API’sini sorgulamalıdır.

Uygulamalar **isSaveToAllowedForLocation** API'sini kullanırken, depolama konumu için kullanılan UPN’den (varsa) geçmeleri gerekir.

#### <a name="supported-save-locations"></a>Desteklenen kaydetme konumları

**isSaveToAllowedForLocation** API’si, BT yöneticisinin IntuneMAMPolicy.h içinde tanımlanan aşağıdaki konumlara veri kaydetme izni verip vermediğinin denetlenmesini sağlayan sabitler sunar:

* IntuneMAMSaveLocationOther
* IntuneMAMSaveLocationOneDriveForBusiness
* IntuneMAMSaveLocationSharePoint
* IntuneMAMSaveLocationLocalDrive

Uygulamalar, OneDrive İş gibi “yönetilen” olarak kabul edilen veya “kişisel” olarak kabul edilen konumlara veri kaydedilip kaydedilemeyeceğini denetlemek için **isSaveToAllowedForLocation** API’sindeki sabitleri kullanmalıdır. Ayrıca uygulama bir konumun “yönetilen” veya “kişisel” olup olmadığını denetleyemiyorsa API kullanılmalıdır.

"Kişisel" olarak bilinen konumlar, `IntuneMAMSaveLocationOther` sabitiyle temsil edilir.

Uygulama yerel cihazdaki herhangi bir konuma veri kaydediyorsa `IntuneMAMSaveLocationLocalDrive` sabiti kullanılmalıdır.

## <a name="configure-settings-for-the-intune-app-sdk"></a>Intune Uygulama SDK’sı için ayarları yapılandırma

Uygulamanın Info.plist dosyasında yer alan **IntuneMAMSettings** sözlüğünü kullanarak Intune Uygulama SDK’sını ayarlayabilir ve yapılandırabilirsiniz. Info.plist dosyasında IntuneMAMSettings sözlüğü görünmüyorsa, uygulamanızın Info.plist dosyasında alan adı "IntuneMAMSettings" olan bir sözlük oluşturmalısınız.

SDK’yı yapılandırmak için, IntuneMAMSettings sözlüğünün altına yapılandırma ayarlarının anahtar/değer satırlarını ekleyebilirsiniz. Aşağıdaki tabloda desteklenen tüm ayarlar listelenmiştir.

Bu ayarlardan bazıları önceki bölümlerde ele alınmış olabilir ve bazıları da tüm uygulamalar için geçerli değildir.

Ayar  | Tür  | Tanım | Gerekli mi?
--       |  --   |   --       |  --
ADALClientId  | Dize  | Uygulamanın Azure AD istemci tanımlayıcısı. | Uygulama ADAL kullanıyorsa gereklidir. |
ADALAuthority | Dize | Uygulamanın kullanımdaki Azure AD yetkilisi. AAD hesaplarının yapılandırılmış olduğu kendi ortamınızı kullanmalısınız. | Uygulama ADAL kullanıyorsa gereklidir. Bu değer yoksa, Intune varsayılanı kullanılır.|
ADALRedirectUri  | Dize  | Uygulamanın Azure AD yeniden yönlendirme URI'si. | Uygulama ADAL kullanıyorsa ADALRedirectUri veya ADALRedirectScheme gereklidir.  |
ADALRedirectScheme  | Dize  | Uygulamanın Azure AD yeniden yönlendirme şeması. Bu, uygulamanın yeniden yönlendirme URI'si `scheme://bundle_id` biçimindeyse ADALRedirectUri yerine kullanılabilir. | Uygulama ADAL kullanıyorsa ADALRedirectUri veya ADALRedirectScheme gereklidir. |
ADALLogOverrideDisabled | Boole değeri  | SDK’nın tüm ADAL günlüklerini (varsa, uygulamadan gelen ADAL çağrıları dahil) kendi günlük dosyasına yönlendirip yönlendirmeyeceğini belirtir. Varsayılan ayar HAYIR’dır. Uygulama kendi ADAL günlüğünü geri çağırma işlevini ayarlayacaksa EVET olarak ayarlayın. | İsteğe bağlı. |
ADALCacheKeychainGroupOverride | Dize  | ADAL önbelleğinde "com.microsoft.adalcache" yerine kullanılacak anahtarlık grubunu belirtir. Bunun uygulama kimliği öneki içermediğini unutmayın. Bu, çalışma zamanında sağlanan dizeye önek olarak eklenir. | İsteğe bağlı. |
AppGroupIdentifiers | Dize dizisi  | Uygulamanın yetkilendirme dosyasının com.apple.security.application bölümündeki uygulama grupları dizisi. | Uygulama, uygulama grupları kullanıyorsa gereklidir. |
ContainingAppBundleId | Dize | Uzantıyı içeren uygulamanın paket kimliğini belirtir. | iOS uzantıları için gereklidir. |
DebugSettingsEnabled| Boole değeri | EVET olarak ayarlanırsa, Ayarlar paketindeki test ilkeleri uygulanabilir. Uygulamalar bu ayar etkinleştirilmiş olarak *gönderilmemelidir*. | İsteğe bağlı. |
MainNibFile<br>MainNibFile~ipad  | Dize  | Bu ayar, uygulamanın ana nib dosya adını içerir.  | Uygulama, Info.plist dosyasında MainNibFile tanımlıyorsa gereklidir. |
MainStoryboardFile<br>MainStoryboardFile~ipad  | Dize  | Bu ayar, uygulamanın ana görsel taslak dosya adını içerir. | Uygulama, Info.plist dosyasında UIMainStoryboardFile tanımlıyorsa gereklidir. |
MAMPolicyRequired| Boole değeri| Uygulama bir Intune uygulama koruma ilkesine sahip değilse, uygulamanın başlatılmasının engellenip engellenmeyeceğini belirtir. Varsayılan ayar HAYIR’dır. <br><br> Not: Uygulamalar, MAMPolicyRequired EVET olarak ayarlanmış şekilde App Store’a gönderilemez. | İsteğe bağlı. |
MAMPolicyWarnAbsent | Boole değeri| Uygulama bir Intune uygulama koruma ilkesine sahip değilse, uygulamanın başlatıldığı sırada kullanıcıyı uyarıp uyarmayacağını belirtir. Bu ayar EVET olarak belirlenmişse uygulamaların mağazaya gönderilemeyeceğini unutmayın. | İsteğe bağlı. |
MultiIdentity | Boole değeri| Uygulamanın çoklu kimliği tanıyıp tanımadığını belirtir. | İsteğe bağlı. |
SplashIconFile <br>SplashIconFile~ipad | Dize  | Intune giriş (başlangıç) simge dosyasını belirtir. | İsteğe bağlı. |
SplashDuration | Sayı | Intune başlangıç ekranının uygulama başlatılırken gösterileceği en kısa süre (saniye cinsinden). Varsayılan olarak 1,5’tir. | İsteğe bağlı. |
BackgroundColor| Dize| Başlangıç ve PIN ekranlarının arka plan rengini belirtir. #XXXXXX biçiminde bir onaltılık RGB dizesini kabul eder; burada X, 0-9 veya A-F aralığındadır. Diyez işareti atlanabilir.   | İsteğe bağlı. Varsayılan olarak açık gridir. |
ForegroundColor| Dize| Metin rengi gibi, başlangıç ve PIN ekranlarının ön plan rengini belirtir. #XXXXXX biçiminde bir onaltılık RGB dizesini kabul eder; burada X, 0-9 veya A-F aralığındadır. Diyez işareti atlanabilir.  | İsteğe bağlı. Varsayılan olarak siyahtır. |
AccentColor | Dize| PIN ekranının düğme metni rengi ve kutu vurgu rengi gibi tema rengini belirtir. #XXXXXX biçiminde bir onaltılık RGB dizesini kabul eder; burada X, 0-9 veya A-F aralığındadır. Diyez işareti atlanabilir.| İsteğe bağlı. Varsayılan olarak sistem mavisidir. |
MAMTelemetryDisabled| Boole değeri| SDK’nın arka ucuna herhangi bir telemetri verisi gönderip göndermeyeceğini belirtir.| İsteğe bağlı. |

> [!NOTE]
> Uygulamanız App Store’da kullanıma sunulacaksa, App Store standartlarına göre `MAMPolicyRequired` "NO" olarak ayarlanmalıdır.

## <a name="telemetry"></a>Telemetri

Varsayılan olarak iOS için Intune Uygulama SDK'sı, aşağıdaki kullanım olaylarına ilişkin telemetri verilerini günlüğe kaydeder. Bu veriler Microsoft Intune’a gönderilir.

* **Uygulama başlatma**: Microsoft Intune’un yönetim türüne göre MAM özellikli uygulama kullanımı hakkında bilgi almasına yardımcı olmak amaçlıdır (MDM ile MAM, MDM kaydı olmadan MAM vb.).

* **Kayıt çağrıları**: Microsoft Intune’un başarı oranı hakkında ve istemci tarafında başlatılan kayıt çağrılarının diğer performans ölçümleriyle ilgili bilgi edinmesine yardımcı olma amaçlıdır.

> [!NOTE]
> Intune Uygulama SDK’sı telemetri verilerini mobil uygulamanızdan Microsoft Intune’a göndermemeyi seçerseniz, Intune Uygulama SDK’sının telemetre yakalama özelliğini devre dışı bırakmanız gerekir. IntuneMAMSettings sözlüğünde `MAMTelemetryDisabled` özelliğini EVET olarak ayarlayın.

## <a name="enable-multi-identity-optional"></a>Çoklu kimliği etkinleştirme (isteğe bağlı)

SDK varsayılan olarak, ilkeyi uygulamaya bir bütün olarak uygular. Çoklu kimlik, bir ilkeyi her kimlik düzeyinde uygulamak için etkinleştirebileceğiniz bir MAM özelliğidir. Bu, diğer MAM özelliklerine kıyasla daha fazla uygulama katılımı gerektirir.

Uygulama etkin kimliği değiştirmeyi amaçladığında, bunu uygulama SDK’sına bildirmelidir. Ayrıca bir kimlik değişikliği gerektiğinde SDK bunu uygulamaya bildirir. Şu anda yalnızca tek bir yönetilen kimlik desteklenir. Kullanıcı cihaz veya uygulamayı kaydettikten sonra, SDK bu kimliği kullanır ve bunu birincil yönetilen kimlik olarak kabul eder. Uygulamadaki diğer kullanıcılar kısıtlanmamış ilke ayarlarıyla yönetilmeyen olarak kabul edilirler.

Bir kimliğin yalnızca dize olarak tanımlandığını aklınızda bulundurun. Kimlikler büyük/küçük harfe duyarlı değildir. SDK’ya kimlik için yapılan istekler, kimlik ayarlandığı sırada kullanılan özgün büyük/küçük harf dizimiyle aynı olmadığı sürece sonuç getirmeyebilir.

### <a name="identity-overview"></a>Kimliğe genel bakış

Kimlik, bir hesabın kullanıcı adıdır (örneğin, user@contoso.com. Geliştiriciler uygulamanın kimliğini aşağıdaki düzeylerde ayarlayabilir:

* **İşlem kimliği**: İşlem genelindeki kimliği ayarlar ve asıl olarak tek kimlikli uygulamalar için kullanılır. Bu kimlik tüm görevleri, dosyaları ve UI’yi etkiler.

* **UI Kimliği**: Ana iş parçacığında UI görevlerine kes/kopyala/yapıştır, PIN, kimlik doğrulaması ve veri paylaşımı gibi ilkelerden hangilerinin uygulanacağını belirler. UI kimliği, şifreleme ve yedekleme gibi dosya görevlerini etkilemez.

* **İş parçacığı kimliği**: Geçerli iş parçacığında hangi ilkelerin uygulanacağını etkiler. Bu kimlik tüm görevleri, dosyaları ve UI’yi etkiler.

Kullanıcı yönetilse de yönetilmese de kimlikleri uygun olarak ayarlamak uygulamanın sorumluluğundadır.

Herhangi bir zamanda, her iş parçacığının UI görevleri ve dosya görevleri için etkili bir kimliği vardır. Bu, hangi ilkelerin (varsa) uygulanması gerektiğini denetlemek için kullanılan kimliktir. Kimlik, “kimliksiz” ise veya kullanıcı yönetilmiyorsa hiçbir ilke uygulanmaz. Aşağıdaki diyagramlarda, etkili kimliklerin nasıl saptandığı gösterilir.

  ![Intune Uygulama SDK’sı iOS: bağlantılı çerçeveler ve kitaplıklar](../media/intune-app-sdk/ios-thread-identities.png)

### <a name="thread-queues"></a>İş parçacığı kuyrukları

Uygulamalar, iş parçacığı kuyruklarına sıklıkla zaman uyumsuz ve zaman uyumlu görevler gönderir. SDK, Genel Gönderme Merkezi (GCD) çağrılarını yakalar ve geçerli iş parçacığı kimliğini gönderilen görev ile ilişkilendirir. Görevler bittiğinde, SDK iş parçacığı kimliğini geçici olarak görevle ilişkili kimlik olarak değiştirir, görevleri bitirir ve sonra özgün iş parçacığı kimliğini geri yükler.


`NSOperationQueue` GCD üzerinde oluşturulduğu için `NSOperations`, iş parçacığı kimliğinde görevler, `NSOperationQueue` öğesine eklendiği zaman çalışır. `NSOperations` veya doğrudan GCD üzerinde gönderilen işlevler ayrıca, geçerli iş parçacığı kimliğini çalıştıkları sırada değiştirebilirler. Bu kimlik, gönderen iş parçacığından devralınan kimliği geçersiz kılar.

### <a name="file-owner"></a>Dosya sahibi

SDK, yerel dosya sahiplerinin kimliklerini izler ve ilkeleri buna göre uygular. Dosya sahibi, bir dosya oluşturulduğunda veya bir dosya kesme modunda açıldığında belirlenir. Sahip, görevi gerçekleştiren iş parçacığının etkin dosya görevi kimliğine ayarlanır.

Alternatif olarak, uygulamalar `IntuneMAMFilePolicyManager` kullanarak sahip kimliğini açıkça ayarlayabilir. Uygulamalar, dosya sahibini almak ve UI kimliğini dosya içeriğini görüntülemeden önce ayarlamak için `IntuneMAMFilePolicyManager` kullanabilir.

### <a name="shared-data"></a>Paylaşılan veriler

Uygulama hem yönetilen hem de yönetilmeyen kullanıcı verilerini içeren dosyalar oluşturursa, yönetilen kullanıcının verilerini şifrelemek uygulamanın sorumluluğundadır. `IntuneMAMDataProtectionManager` içindeki `protect` ve `unprotect` API'lerini kullanarak veri şifreleyebilirsiniz.

`protect` yöntemi, bir kimliği yönetilen veya yönetilmeyen kullanıcı olarak kabul eder. Kullanıcı yönetiliyorsa, veriler şifrelenir. Kullanıcı yönetilmiyorsa, kimliği kodlayan verilere bir üst bilgi eklenir ancak veriler şifrelenmez. Verilerin sahibini almak için `protectionInfo` yöntemini kullanabilirsiniz.

### <a name="share-extensions"></a>Paylaşım uzantıları

Uygulama bir paylaşım uzantısı içeriyorsa, paylaşılan öğenin sahibi `IntuneMAMDataProtectionManager` içindeki `protectionInfoForItemProvider` yöntemiyle alınabilir. Paylaşılan öğe bir dosya ise, dosya sahibi ayarı SDK tarafından yapılır. Paylaşılan öğenin veri olması durumunda; bu veri bir dosyaya sabitlenmişse dosya sahibini ayarlamak ve bu veriyi UI’da göstermeden önce `setUIPolicyIdentity` API’sini çağırmak uygulamanın görevidir.

### <a name="turning-on-multi-identity"></a>Çoklu kimliği açma

Varsayılan olarak, uygulamalar tek kimlikli olarak değerlendirilir. SDK, kayıtlı kullanıcı için işlem kimliğini ayarlar. Çoklu kimlik desteğini etkinleştirmek için uygulamanın Info.plist dosyası içindeki IntuneMAMSettings sözlüğüne EVET değeri ve `MultiIdentity` adıyla bir Boole ayarı ekleyin.

> [!NOTE]
> Çoklu kimlik etkinleştirildiğinde işlem kimliği, UI kimliği ve iş parçacığı kimlikleri nil olarak ayarlanır. Uygulama, bunları uygun şekilde ayarlamaktan sorumludur.

### <a name="switching-identities"></a>Kimlikleri değiştirme

* **Uygulama tarafından başlatılan kimlik değişimi**:

    Başlatma sırasında, çoklu kimlik uygulamaları bilinmeyen, yönetilmeyen bir hesap altında çalışıyor gibi kabul edilir. Koşullu başlatma UI’si çalışmaz ve uygulamada hiçbir ilke uygulanmaz. Kimliğin değiştirilmesi gerektiğinde bunu SDK’ya bildirmek uygulamanın sorumluluğundadır. Normalde, bu durum uygulamanın belirli bir kullanıcı hesabına ait verileri göstermek üzere olduğu sırada gerçekleşir.

    Kullanıcının bir dizüstü bilgisayarda bir belge, posta kutusu veya sekme açmayı denemesi örnek olarak gösterilebilir. Dosya, posta kutusu veya sekme gerçekten açılmadan uygulamanın SDK’ya bildirimde bulunması gerekir. Bu `IntuneMAMPolicyManager` içindeki `setUIPolicyIdentity` API’si üzerinden yapılır. Bu API, kullanıcı yönetilse de yönetilmese de çağrılmalıdır. Kullanıcı yönetiliyorsa, SDK koşullu başlatma denetimleri gerçekleştirir (kök erişim izni algılama, PIN ve kimlik doğrulama gibi).

    Kimlik değişiminin sonucu, uygulamaya bir tamamlama işleyicisi üzerinden zaman uyumsuz olarak döndürülür. Uygulama; belge, posta kutusu veya sekmeyi açmayı başarılı sonuç kodu döndürülünceye kadar ertelemelidir. Kimlik değişimi başarısız olursa, uygulamanın görevi iptal etmesi gerekir.

* **SDK tarafından başlatılan kimlik değişimi**:

    SDK’nın uygulamadan belirli bir kimliğe değiştirilmesini istemesini gerektiren durumlar vardır. Çoklu kimlik uygulamalarının bu isteği işlemek için `IntuneMAMPolicyDelegate` içindeki `identitySwitchRequired` yöntemini uygulaması gerekir.

    Bu yöntem çağrıldığı zaman, uygulama belirtilen kimliğe geçiş isteğini yerine getirebiliyorsa, tamamlama işleyicisine `IntuneMAMAddIdentityResultSuccess` öğesini geçirmesi gerekir. Kimliği değiştirme işlemini yerine getiremiyorsa, uygulamanın tamamlama işleyicisine `IntuneMAMAddIdentityResultFailed` öğesini geçirmesi gerekir.

    Bu çağrıya yanıt olarak uygulamanın `setUIPolicyIdentity` öğesini çağırması gerekmez. SDK, uygulamanın yönetilmeyen bir kullanıcı hesabıyla değiştirilmesini gerektirirse, boş dize `identitySwitchRequired` çağrısına geçirilir.

* **Seçmeli temizleme**:

    Uygulama seçmeli temizleme işlemiyle temizlendiğinde, SDK `IntuneMAMPolicyDelegate` içindeki `wipeDataForAccount` yöntemini çağırır. Belirtilen kullanıcı hesabını ve onunla ilişkili tüm verileri kaldırmak uygulamanın sorumluluğundadır. SDK, kullanıcının sahip olduğu tüm dosyaları kaldırabilir ve uygulamanın `wipeDataForAccount` çağrısından FALSE sonucu getirmesi durumunda bunu uygular.

    Bu yöntemin bir arka plan iş parçacığından çağrıldığını unutmayın. Kullanıcıya yönelik tüm veriler kaldırılana kadar uygulama bir değer döndürmemelidir (uygulama FALSE döndürürse dosyalar hariç olmak üzere).

## <a name="test-app-protection-policy-settings-in-xcode"></a>Xcode’da uygulama koruma ilkesi ayarlarını test etme

Intune kullanan uygulamanızı üretim ortamında el ile test etmeden önce, Xcode’dayken bir Settings.bundle dosyası kullanabilirsiniz. Böylece, Intune bağlantısına gerek olmadan test etmek için uygulama koruma ilkelerini ayarlayabilirsiniz.

### <a name="enable-policy-testing"></a>İlke testini etkinleştirme

Xcode’da ilke testini etkinleştirmek için aşağıdaki adımları izleyin:

1. Hata ayıklama derlemesinde olduğunuzdan emin olun. Projenizdeki en üst düzey klasöre sağ tıklayarak bir Settings.bundle dosyası ekleyin. Menüden **Ekle** > **Yeni Dosya**’yı seçin. **Kaynaklar**’ın altında **Ayarlar Paketi** şablonunu seçin.

2.  Aşağıdaki bloğu, hata ayıklama derlemesinin Settings.bundle/**Root.plist** dosyasına kopyalayın:
    ```xml
    <key>PreferenceSpecifiers</key>
    <array>
        <dict>
            <key>Type</key>
            <string>PSChildPaneSpecifier</string>
            <key>Title</key>
            <string>MDM Debug Settings</string>
            <key>Key</key>
            <string>MAMDebugSettings</string>
            <key>File</key>
            <string>MAMDebugSettings</string>
        </dict>
    </array>
    ```

3. Uygulamanın Info.plist dosyasındaki **IntuneMAMSettings** sözlüğüne, "DebugSettingsEnabled" adlı bir Boole değeri ekleyin. DebugSettingsEnabled değerini "EVET" olarak ayarlayın.



### <a name="app-protection-policy-settings"></a>Uygulama koruma ilkesi ayarları

Aşağıdaki tabloda, MAMDebugSettings.plist’i kullanarak test edebileceğiniz uygulama koruma ilkesi ayarları açıklanır. Bir ayarı açmak için, onu MAMDebugSettings.plist’e ekleyin.

| İlke ayarı adı | Açıklama | Olası değerler |
| -- | -- | -- |
| AccessRecheckOfflineTimeout | Intune’un uygulamanın başlatılmasını engellemeden veya kimlik doğrulaması etkinleştirildiyse uygulama sürdürülmeden önce, uygulamanın çevrimdışı kalabileceği dakika cinsinden süre. | 0’dan büyük herhangi bir tamsayı |
|    AccessRecheckOnlineTimeout | Başlatma veya sürdürülme sırasında kullanıcıdan PIN veya kimlik doğrulaması istenmeden önce uygulamanın çalıştırılabileceği dakika cinsinden süre (erişim için kimlik doğrulaması veya PIN etkinleştirildiyse). | 0’dan büyük herhangi bir tamsayı |
| AppSharingFromLevel | Bu uygulamanın hangi uygulamalardan veri kabul edebileceğini belirtir. | 0 = |
## <a name="ios-best-practices"></a>iOS en iyi yöntemleri

iOS için geliştirmeye yönelik önerilen en iyi yöntemler aşağıda verilmiştir:

* iOS dosya sistemi büyük/küçük harfe duyarlıdır. Büyük/küçük harf kullanımının `libIntuneMAM.a` ve `IntuneMAMResources.bundle` gibi dosya adlarında doğru olduğundan emin olun.

* Xcode `libIntuneMAM.a` dosyasını bulamıyorsa, bu kitaplığın yolunu bağlayıcı arama yollarına ekleyerek sorunu düzeltebilirsiniz.

## <a name="faqs"></a>Sık Sorulan Sorular


**Yerel Swift veya Objective-C ve Swift birlikte çalışabilirliği aracılığıyla tüm API’ler adreslenebilir midir?** 

Intune Uygulama SDK API'leri yalnızca Objective-C içindedir ve **yerel** Swift’i desteklemez. Swift’in Objective-C ile birlikte çalışabilir olması gereklidir.


**Uygulamamın tüm kullanıcılarının APP-WE hizmetine kayıtlı olması gerekiyor mu?**

Hayır. Aslında, yalnızca iş veya okul hesaplarının Intune uygulama SDK'sına kayıtlı olması gerekir. Bir hesabın iş veya okul bağlamında kullanılıp kullanılmadığını belirlemek uygulamaların sorumluluğundadır.   

**Uygulamada zaten oturum açmış kullanıcılar ne olacak? Kayıtlı olmaları gerekli mi?**

Kullanıcıların kimliği başarıyla doğrulandıktan sonra kullanıcıları kaydetmek uygulamanın sorumluluğundadır. Uygulama MDM bulunmayan MAM işlevselliğine sahip olmadan önce var olan hesapları kaydetmek de uygulamanın sorumluluğundadır.   

Bunu yapmak için uygulamanın `registeredAccounts:` yöntemini kullanması gerekir. Bu yöntem, Intune MAM hizmetine kayıtlı tüm hesapları içeren bir NSDictionary döndürür. Uygulamadaki mevcut hesaplardan herhangi biri listede yoksa, uygulama bu hesapları `registerAndEnrollAccount:` aracılığıyla kaydetmelidir.

**SDK, kayıtları ne sıklıkta yeniden dener?**

SDK daha önce başarısız olan tüm kayıtları otomatik olarak 24 saatte bir yeniden dener. SDK bu işlemi, kullanıcı uygulamada oturum açtıktan sonra bir kullanıcının kuruluşunun MAM’ı etkinleştirildiğinden emin olmak için yapıyorsa kullanıcı başarıyla kaydedilir ve ilkeleri alır.

SDK, bir kullanıcının uygulamayı başarıyla kaydettiğini algıladığında yeniden denemeyi durdurur. Bunun nedeni, bir uygulamayı belirli bir zamanda tek bir kullanıcının kaydedebilmesidir. Kullanıcının kaydı silinirse, yeniden denemeler aynı 24 saatlik zaman aralığında tekrar başlar.

**Kullanıcının kaydının neden kaldırılması gerekir?**

SDK şu eylemleri arka planda düzenli aralıklarla gerçekleştirir:

 - Uygulama henüz kaydedilmemişse, tüm kayıtlı hesapları 24 saatte bir kaydetmeyi dener.
 - Uygulama kaydedildiyse, SDK her 8 saatte bir uygulama koruma ilkesi güncelleştirmelerini denetler.

Bir kullanıcının kaydını kaldırmak SDK’ya kullanıcının uygulamayı artık kullanmayacağını bildirir ve söz konusu kullanıcı hesabına ait periyodik olayların tümünü durdurabilir. Ayrıca uygulama kaydı silme işlemini ve gerekirse seçmeli silme işlemini tetikler.

**Kaydı kaldırma yönteminde doWipe bayrağını true olarak ayarlamalı mıyım?**

Bu yöntem, kullanıcının uygulamadaki oturumunu kapatmasından önce çağrılmalıdır.  Oturum kapatma işlemi kapsamında kullanıcı verileri uygulamadan silinirse, `doWipe` false olarak ayarlanabilir. Ancak uygulama kullanıcı verilerini kaldırmazsa, SDK’nın verileri silebilmesi için `doWipe` true olarak ayarlanmalıdır.

**Bir uygulama kaydını kaldırmanın başka yolları var mı?**

Evet, BT yöneticisi uygulamaya bir seçmeli temizleme komutu gönderebilir. Bu, kullanıcının kaydını kaldırır, siler ve kullanıcı verilerini temizler. SDK bu senaryoyu otomatik olarak işler ve kayıt silme temsilci yöntemiyle bir bildirim gönderir.



## <a name="submit-your-app-to-the-app-store"></a>Uygulamanızı App Store’a gönderme

Intune Uygulama SDK’sının hem statik kitaplığı hem de çerçeve derlemesi evrensel ikili dosyalardır. Yani tüm cihaz ve simülatör mimarilerine yönelik kodları içerirler. Apple, App Store’a gönderilen uygulamaları simülatör kodu içermeleri durumunda reddeder. Yalnızca cihaz derlemeleri için statik kitaplığa karşı derleme yapıldığında, bağlayıcı, simülatör kodunu otomatik olarak çıkartır. Uygulamanızı App Store’a yüklemeden önce tüm simülatör kodunun kaldırıldığından emin olmak için aşağıdaki adımları uygulayın.

1. `IntuneMAM.framework` öğesinin masaüstünüzde olduğundan emin olun.

2. Şu komutları çalıştırın:

    ```bash
    lipo ~/Desktop/IntuneMAM.framework/IntuneMAM -remove i386 -remove x86_64 -output ~/Desktop/IntuneMAM.device_only
    ```

    ```bash
    cp ~/Desktop/IntuneMAM.device_only ~/Desktop/IntuneMAM.framework/IntuneMAM
    ```
    İlk komut, simülatör mimarilerini çerçevenin DYLIB dosyasından kaldırır. İkinci komut, yalnızca cihaz DYLIB dosyasını çerçeve klasörüne kopyalar.

