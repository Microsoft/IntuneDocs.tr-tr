---
title: iOS için Microsoft Intune Uygulama SDK’sı geliştirici kılavuzu
description: iOS için Microsoft Intune Uygulama SDK’sı, Intune uygulama koruma ilkelerini (APP veya MAM ilkeleri olarak da bilinir) yerel iOS uygulamanıza eklemenizi sağlar.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/13/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7b19a0100a53cebe66dae9805ac0cc5b5314e8ad
ms.sourcegitcommit: 9a4c5b6c2ce511edaeace25426a23f180cb71e15
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/07/2019
ms.locfileid: "57566786"
---
# <a name="microsoft-intune-app-sdk-for-ios-developer-guide"></a>iOS için Microsoft Intune Uygulama SDK’sı geliştirici kılavuzu

> [!NOTE]
> Desteklenen platformlarda tümleştirme için hazırlığın nasıl yapıldığını açıklayan [Intune Uygulama SDK’sı Kılavuzunu Kullanmaya Başlama](app-sdk-get-started.md) makalesini okumanız önerilir.

iOS için Microsoft Intune Uygulama SDK’sı, Intune uygulama koruma ilkelerini (**APP** veya **MAM ilkeleri** olarak da bilinir) yerel iOS uygulamanıza eklemenizi sağlar. MAM özellikli uygulamalar Intune Uygulama SDK’sı ile tümleşiktir. Intune uygulamayı etkin bir şekilde yönetirken, BT yöneticileri mobil uygulamanıza uygulama koruma ilkeleri dağıtabilir.

## <a name="prerequisites"></a>Önkoşullar

* Xcode 9 veya üzeri yüklü olan ve OS X 10.8.5 ya da üzerini çalıştıran bir Mac OS bilgisayara ihtiyaç duyacaksınız.

* Uygulamanız iOS 10 veya üzeri sürümlere yönelik olmalıdır.

* [iOS için Intune Uygulama SDK'sı Lisans Koşulları](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20for%20iOS.pdf)'nı gözden geçirmelisiniz. Kendi kayıtlarınız için lisans koşullarının bir kopyasını yazdırmalı ve saklamalısınız. iOS için Intune Uygulama SDK'sını indirip kullandığınızda bu lisans koşullarını kabul etmiş olursunuz.  Kabul etmiyorsanız, yazılımı kullanmayın.

* iOS için Intune Uygulama SDK'sı dosyalarını [GitHub](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)’dan indirin.

## <a name="whats-in-the-sdk"></a>SDK’nın kapsamı

iOS için Intune Uygulama SDK’sı statik bir kitaplık, kaynak dosyaları, API üst bilgileri, hata ayıklama ayarları .plist dosyası ve bir yapılandırıcı aracı içerir. İstemci uygulamalar yalnızca kaynak dosyaları içerebilir ve çoğu ilke zorlaması için kitaplıklarla statik bağlantılar oluşturabilir. Gelişmiş Intune APP özellikleri API'ler aracılığıyla zorunlu tutulur.

Bu kılavuz, iOS için Intune Uygulama SDK'sının aşağıdaki bileşenlerinin kullanımını açıklar:

* **libIntuneMAM.a**: Intune uygulama SDK'sı statik kitaplığı. Uygulamanızda uzantılar kullanılmıyorsa, uygulamanızı Intune istemci uygulama yönetimi için etkinleştirmek üzere bu kitaplığı projenize bağlayın.

* **Intunemam.Framework**: Intune uygulama SDK'sı çerçevesi. Uygulamanızı Intune istemci uygulama yönetimi için etkinleştirmek üzere bu çerçeveyi projenize bağlayın. Uygulamanızda uzantılar kullanılıyorsa, projenizin birden çok statik kitaplık kopyası oluşturmasını önlemek için statik kitaplık yerine bu çerçeveyi kullanın.

* **Intunemamresources.Bundle**: SDK'ın bağımlı kaynaklara sahip bir kaynak paketi.

* **Üstbilgileri**: Intune uygulama SDK'sı API'lerini gösterir. API kullanırsanız, API’yi içeren üst bilgi dosyasını dahil etmeniz gerekir. Aşağıdaki üst bilgi dosyaları, Intune Uygulama SDK’sı tarafından geliştiricilerin kullanımına sunulan API’ler, veri türleri ve protokollerini içerir:

    * IntuneMAMAppConfig.h
    * IntuneMAMAppConfigManager.h
    * IntuneMAMDataProtectionInfo.h
    * IntuneMAMDataProtectionManager.h
    * IntuneMAMDefs.h
    * IntuneMAMEnrollmentDelegate.h
    * IntuneMAMEnrollmentManager.h
    * IntuneMAMEnrollmentStatus.h
    * IntuneMAMFileProtectionInfo.h
    * IntuneMAMFileProtectionManager.h
    * IntuneMAMLogger.h
    * IntuneMAMPolicy.h
    * IntuneMAMPolicyDelegate.h
    * IntuneMAMPolicyManager.h
    * IntuneMAMVersionInfo.h

Geliştiriciler, yalnızca IntuneMAM.h üst bilgi dosyasını içeri aktararak yukarıdaki tüm dosyaların içeriğine erişebilir


## <a name="how-the-intune-app-sdk-works"></a>Intune Uygulama SDK’sı nasıl çalışır?

iOS için Intune Uygulama SDK'sının amacı, kodda minimum düzeyde değişiklik yaparak iOS uygulamalarına yönetim özellikleri eklemeyi sağlamaktır. Daha az kod değişikliği vardır ve pazarlama süresi daha kısadır ancak mobil uygulamanızın tutarlılığı ve kararlılığı yine de etkilenmez.


## <a name="build-the-sdk-into-your-mobile-app"></a>Mobil uygulamanızda SDK oluşturma

Intune Uygulama SDK'sını etkinleştirmek için aşağıdaki adımları izleyin:

1. **Seçenek 1 (önerilen)**: Bağlantı `IntuneMAM.framework` projenize. `IntuneMAM.framework` öğesini proje hedefinin **Katıştırılmış İkili Dosyalar** listesine sürükleyin.

   > [!NOTE]
   > Çerçeveyi kullanırsanız, uygulamanızı App Store’a göndermeden önce evrensel çerçeveden benzetici mimarilerini elle çıkarmanız gerekir. Daha fazla bilgi için bkz. [Uygulamanızı App Store'a gönderme](#Submit-your-app-to-the-App-Store).

   **Seçenek 2**: Bağlantı `libIntuneMAM.a` kitaplığı. `libIntuneMAM.a` kitaplığını proje hedefinin **Bağlantılı Çerçeveler ve Kitaplıklar** listesine sürükleyin.

    ![Intune Uygulama SDK’sı iOS: bağlantılı çerçeveler ve kitaplıklar](./media/intune-app-sdk-ios-linked-frameworks-and-libraries.png)

    `{PATH_TO_LIB}` öğesini Intune Uygulama SDK'sı konumu ile değiştirerek `-force_load {PATH_TO_LIB}/libIntuneMAM.a` öğesini aşağıdakilerden birine ekleyin:
   * Projenin `OTHER_LDFLAGS` derlemesi yapılandırma ayarı
   * Xcode UI’nin **Diğer Bağlayıcı Bayrakları**

     > [!NOTE]
     > `PATH_TO_LIB` öğesini bulmak için `libIntuneMAM.a` dosyasını seçin ve **Dosya** menüsünden **Bilgi Al** öğesini belirleyin. **Nerede** bilgisini (yol) **Bilgi** penceresinin **Genel** bölümünden kopyalayıp yapıştırın.

     `IntuneMAMResources.bundle` kaynak paketini **Derleme Aşamaları** içindeki **Paket Kaynaklarını Kopyala** altına sürükleyerek kaynak paketini projeye ekleyin.

     ![Intune Uygulama SDK'sı iOS: Paket kaynaklarını kopyalama](./media/intune-app-sdk-ios-copy-bundle-resources.png)

2. Aşağıdaki iOS çerçevelerini projeye ekleyin:  
    * MessageUI.framework  
    * Security.framework  
    * MobileCoreServices.framework  
    * SystemConfiguration.framework  
    * libsqlite3.tbd  
    * libc++.tbd  
    * ImageIO.framework  
    * LocalAuthentication.framework  
    * AudioToolbox.framework  
    * QuartzCore.framework  
    * WebKit.framework

3. Her bir proje hedefinde **Özellikler**’i seçip **Anahtar Zinciri Paylaşımı** anahtarını etkinleştirerek anahtar zinciri paylaşımını etkinleştirin (önceden etkinleştirilmemişse). Anahtarlık paylaşımı, sonraki adıma devam edebilmeniz için gereklidir.

   > [!NOTE]
   > Sağlama profilinizin, yeni anahtarlık paylaşımı değerlerini desteklemesi gerekir. Anahtarlık erişim grupları bir joker karakteri desteklemelidir. Bunu denetlemek için .mobileprovision dosyasını bir metin düzenleyicide açıp **keychain-access-groups** araması yapın ve bir joker karakter kullandığınızdan emin olun. Örneğin:
   >  ```xml
   >  <key>keychain-access-groups</key>
   >  <array>
   >  <string>YOURBUNDLESEEDID.*</string>
   >  </array>
   >  ```

4. Anahtarlık paylaşımını etkinleştirdikten sonra Intune Uygulama SDK'sı verilerinin depolanacağı ayrı bir erişim grubu oluşturmak için aşağıdaki adımları izleyin. UI veya yetkilendirmeler dosyasını kullanarak bir anahtarlık erişim grubu oluşturabilirsiniz. UI öğelerini anahtarlık erişim grubu oluşturmak için kullanıyorsanız aşağıdaki adımları izleyin:

    1. Mobil uygulamanız tüm Anahtarlık erişim gruplarını tanımlanan, uygulamanın ekleme yoksa kimliği olarak paket **ilk** grubu.
    
    2. `com.microsoft.intune.mam` paylaşılan anahtarlık grubunu var olan erişim gruplarınıza ekleyin. Intune Uygulama SDK'sı verileri depolamak için bu erişim grubunu kullanır.
    
    3. `com.microsoft.adalcache` öğesini var olan erişim gruplarınıza ekleyin.
    
        ![Intune Uygulama SDK’sı iOS: Anahtarlık paylaşımı](./media/intune-app-sdk-ios-keychain-sharing.png)
    
    4. Anahtarlık erişim gruplarını oluşturmak için yukarıda gösterilen Xcode UI'ı kullanmak yerine doğrudan yetkilendirme dosyalarını düzenliyorsanız, anahtarlık erişim gruplarını `$(AppIdentifierPrefix)` öğesinin önüne ekleyin (Xcode bunu otomatik olarak işler). Örneğin:
    
        - `$(AppIdentifierPrefix)com.microsoft.intune.mam`
        - `$(AppIdentifierPrefix)com.microsoft.adalcache`
    
        > [!NOTE]
        > Yetkilendirme dosyası, mobil uygulamanıza özel, benzersiz bir XML dosyasıdır. iOS uygulamanızda özel izinler ve özellikler belirtmek için kullanılır. Uygulamanızın önceden bir yetkilendirme dosyası yoksa, anahtarlık paylaşımının etkinleştirilmesi (3. adım) Xcode'un uygulamanız için bir dosya oluşturmasına neden olacaktır. Uygulamanın paket Kimliğini ilk girdi listesinde olduğundan emin olun.

5. Uygulamanızın `UIApplication canOpenURL` öğesine geçirdiği her protokolü, uygulamanızın Info.plist dosyasının `LSApplicationQueriesSchemes` dizisine dahil edin. Sonraki adıma ilerlemeden önce değişikliklerinizi kaydettiğinizden emin olun.

6. Uygulamanız zaten FaceID kullanmıyorsa [NSFaceIDUsageDescription info.plist anahtarının](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/CocoaKeys.html#//apple_ref/doc/uid/TP40009251-SW75) bir varsayılan iletiyle yapılandırıldığından emin olun. Bu, iOS’un kullanıcıya uygulamanın FaceID’yi nasıl kullanacağını bildirmesi için gereklidir. Intune uygulama koruma ilke ayarları, bir BT yöneticisi tarafından yapılandırılırsa FaceID’nin uygulama erişimi için bir yöntem olarak kullanılmasına imkan verir.

7. Uygulamanızın Info.plist dosyasını yapılandırmayı bitirmek için, [SDK deposuna](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios) eklenen IntuneMAMConfigurator aracını kullanın. Araç, üç parametreye sahiptir:

   |Özellik|Kullanımı|
   |---------------|--------------------------------|
   |- i |  `<Path to the input plist>` |
   |- e | `<Path to the entitlements file>` |
   |- o |  (İsteğe bağlı) `<Path to the output plist>` |

'-o' parametresi belirtilmezse, giriş dosyası yerinde değiştirilir. Araç bir kez etkilidir ve uygulamanın Info.plist dosyası her değiştirildiğinde veya yetkilendirmeler yapıldığında yeniden çalıştırılmalıdır. En son sürümde Info.plist yapılandırma gereksinimlerinin değişmesi durumunda, Intune SDK'sını güncelleştirirken de aracın en son sürümünü indirmeniz ve çalıştırmanız gerekir.

## <a name="configure-azure-active-directory-authentication-library-adal"></a>Azure Active Directory Kimlik Doğrulama Kitaplığı'nı (ADAL) Yapılandırma

Intune Uygulama SDK'sı, kimlik doğrulama ve koşullu başlatma senaryoları için [Azure Active Directory Kimlik Doğrulama Kitaplığı](https://github.com/AzureAD/azure-activedirectory-library-for-objc)'nı kullanır. Cihaz kayıt senaryoları olmadan yönetim için MAM hizmetinde kullanıcı kimliğini kaydetmek için de ADAL kullanır.

ADAL genellikle, uygulamaya verilen belirteçlerin güvenliğini sağlamak için uygulamaların (ClientID) benzersiz kimliği ve diğer tanımlayıcıları Azure Active Directory (AAD) ile kaydetmesini ve almasını gerektirir. Aksi belirtilmediği sürece Intune Uygulama SDK'sı, Azure AD ile iletişim kurarken varsayılan kayıt değerlerini kullanır.  

Uygulamanız kullanıcı kimlik doğrulaması için zaten ADAL kullanıyorsa, uygulamanın mevcut kayıt değerlerini kullanması ve Intune Uygulama SDK'sının varsayılan değerlerini geçersiz kılması gerekir. Bu, kullanıcılardan iki kez kimlik doğrulaması (Intune Uygulama SDK'sı ve uygulama tarafından) istenmemesini sağlar.

Uygulamanızın ana dalında [son ADAL sürümüne](https://github.com/AzureAD/azure-activedirectory-library-for-objc/releases) bağlantı vermesi önerilir. Intune Uygulama SDK'sı şu anda koşullu erişim gerektiren uygulamaları desteklemek için ADAL'ın aracı dalını kullanır. (Dolayısıyla bu uygulamalar Microsoft Authenticator uygulamasına bağlıdır.) Ancak, SDK hala ADAL’ın ana dalı ile uyumludur. Uygulamanıza uygun olan dalı kullanın.

### <a name="link-to-adal-binaries"></a>ADAL ikili dosyalarına bağlantı kurma

Uygulamanızla ADAL ikili dosyaları arasında bağlantı kurmak için aşağıdaki adımları izleyin:

1. GitHub'dan [Azure Active Directory Authentication Library (ADAL) for Objective-C](https://github.com/AzureAD/azure-activedirectory-library-for-objc) dosyalarını indirin ve Git alt modülleri veya CocoaPods kullanarak ADAL indirme [talimatlarını](https://github.com/AzureAD/azure-activedirectory-library-for-objc#download) izleyin.

2. Projenize ADAL çerçevesini (1. seçenek) veya statik kitaplığı (2. seçenek) ekleyin.

3. Uygulamanızda tanımlanmış bir anahtar zinciri erişim grubu yoksa, uygulamanın paket kimliğini ilk grup olarak ekleyin.

4. Anahtar zinciri erişim gruplarına `com.microsoft.adalcache` ve `com.microsoft.workplacejoin` ekleyerek ADAL çoklu oturum açma (SSO) ayarını etkinleştirin.

5. ADAL paylaşımlı önbellek anahtar zinciri grubunu açıkça ayarlıyorsanız, ayarın `<appidprefix>.com.microsoft.adalcache` olduğundan emin olun. Bu ayarı geçersiz kılmadığınız sürece ADAL bunu sizin için ayarlar. `com.microsoft.adalcache` öğesini değiştirmek için özel bir anahtar zinciri grubu belirtmek isterseniz, bunu IntuneMAMSettings altındaki Info.plist dosyası içinde `ADALCacheKeychainGroupOverride` anahtarını kullanarak belirtin.

### <a name="configure-adal-settings-for-the-intune-app-sdk"></a>Intune Uygulama SDK'sı için ADAL ayarlarını yapılandırma

Uygulamanız kimlik doğrulaması için zaten ADAL kullanıyorsa ve kendi ADAL ayarlarına sahipse Intune Uygulama SDK'sının Azure Active Directory kimlik doğrulaması sırasında aynı ayarları kullanmasını zorunlu kılabilirsiniz. Bu sayede uygulamanın kullanıcıdan iki kez kimlik doğrulaması istemesi engellenmiş olur. Aşağıdaki ayarları doldurma hakkında bilgi edinmek için [Intune Uygulama SDK'sı için ayarları yapılandırma](#configure-settings-for-the-intune-app-sdk) bölümüne göz atın:  

* ADALClientId
* ADALAuthority
* ADALRedirectUri
* ADALRedirectScheme
* ADALCacheKeychainGroupOverride

Uygulamanız zaten ADAL kullanıyorsa aşağıdaki yapılandırma adımlarının gerçekleştirilmesi gerekir:

1. Projenin Info.plist dosyasında, `ADALClientId` anahtar adlı **IntuneMAMSettings** sözlüğü altında, ADAL çağrıları için kullanılacak istemci kimliği değerini belirtin.

2. Yine `ADALAuthority` anahtar adlı **IntuneMAMSettings** sözlüğü altında, Azure AD yetkilisini belirtin.

3. Yine `ADALRedirectUri` anahtar adlı **IntuneMAMSettings** sözlüğü altında, ADAL çağrıları için kullanılacak yeniden yönlendirme URI'si değerini belirtin. Alternatif olarak, uygulamanın yeniden yönlendirme URI'si `scheme://bundle_id` biçimindeyse bunun yerine `ADALRedirectScheme` belirtebilirsiniz.

Ayrıca, uygulamalar çalışma zamanında bu Azure AD ayarlarını geçersiz kılabilir. Bunu yapmak için `IntuneMAMPolicyManager` örneğinde `aadAuthorityUriOverride`, `aadClientIdOverride` ve `aadRedirectUriOverride` özelliklerini ayarlamanız yeterlidir.

4. İOS uygulama koruma İlkesi (uygulama) hizmeti uygulama izin vermek için adımları izlendiğinden emin olun. Yönergeleri kullanın [Intune SDK'sı Kılavuzu ile çalışmaya başlama](https://docs.microsoft.com/intune/app-sdk-get-started#next-steps-after-integration) altında "verin, uygulama erişimini Intune uygulama koruma hizmeti için (isteğe bağlı)".  

> [!NOTE]
> Statik olan ve çalışma zamanında saptanması gerekmeyen tüm ayarlar için Info.plist yaklaşımı önerilir. `IntuneMAMPolicyManager` özelliklerine atanan değerler, Info.plist dosyasında belirtilen ve bunlara karşılık gelen tüm değerlerden önceliklidir ve uygulama yeniden başlatıldıktan sonra bile kalıcı olmayı sürdürür. Kullanıcının kaydı silinene ya da değerler temizlenene veya değiştirilene kadar SDK ilke iadelerinde bunları kullanmaya devam edecektir.

### <a name="if-your-app-does-not-use-adal"></a>Uygulamanız ADAL kullanmıyorsa

Yukarıda belirtildiği gibi, Intune Uygulama SDK'sı, kimlik doğrulama ve koşullu başlatma senaryoları için [Azure Active Directory Kimlik Doğrulama Kitaplığı](https://github.com/AzureAD/azure-activedirectory-library-for-objc)'nı kullanır. Cihaz kayıt senaryoları olmadan yönetim için MAM hizmetinde kullanıcı kimliğini kaydetmek için de ADAL kullanır. **Uygulamanız kendi kimlik doğrulama mekanizması için ADAL kullanmıyorsa**, Intune Uygulama SDK'sı ADAL parametrelerinin varsayılan değerlerini sağlar ve Azure AD kimlik doğrulamasını yapar. Yukarıda listelenen ADAL ayarları için herhangi bir değer belirtmeniz gerekmez. Varsa uygulamanızın kullandığı kimlik doğrulama mekanizması ADAL istemlerinin üstünde gösterilir. 

## <a name="configure-settings-for-the-intune-app-sdk"></a>Intune Uygulama SDK'sı ayarlarını yapılandırma

Intune Uygulama SDK’sını ayarlamak ve yapılandırmak için uygulamanın Info.plist dosyasında yer alan **IntuneMAMSettings** sözlüğünü kullanabilirsiniz. IntuneMAMSettings sözlüğü Info.plist dosyanızda görünmüyorsa, sözlüğü oluşturmalısınız.

IntuneMAMSettings sözlüğü altında, Intune Uygulama SDK'sını yapılandırmak için desteklenen şu ayarları kullanabilirsiniz.

Bu ayarlardan bazıları önceki bölümlerde ele alınmış olabilir ve bazıları tüm uygulamalar için geçerli değildir.

Ayar  | Type  | Tanım | Gerekli mi?
--       |  --   |   --       |  --
ADALClientId  | Dize  | Uygulamanın Azure AD istemci tanımlayıcısı. | Uygulama ADAL kullanıyorsa gereklidir. |
ADALAuthority | Dize | Uygulamanın Azure AD yetkilisi kullanımda. AAD hesaplarının yapılandırıldığı ortamınızı kullanmanız gerekir. | Uygulama ADAL kullanıyorsa gereklidir. Bu değer yoksa, Intune varsayılanı kullanılır.|
ADALRedirectUri  | Dize  | Uygulamanın Azure AD yeniden yönlendirme URI'si. | Uygulama ADAL kullanıyorsa ADALRedirectUri veya ADALRedirectScheme gereklidir.  |
ADALRedirectScheme  | Dize  | Uygulamanın Azure AD yeniden yönlendirme şeması. Bu, uygulamanın yeniden yönlendirme URI'si `scheme://bundle_id` biçimindeyse ADALRedirectUri yerine kullanılabilir. | Uygulama ADAL kullanıyorsa ADALRedirectUri veya ADALRedirectScheme gereklidir. |
ADALLogOverrideDisabled | Boole değeri  | SDK’nın tüm ADAL günlüklerini (varsa, uygulamadan gelen ADAL çağrıları dahil) kendi günlük dosyasına yönlendirip yönlendirmeyeceğini belirtir. Varsayılan ayar HAYIR’dır. Uygulama kendi ADAL günlüğünü geri çağırma işlevini ayarlayacaksa EVET olarak ayarlayın. | İsteğe bağlı. |
ADALCacheKeychainGroupOverride | Dize  | ADAL önbelleğinde "com.microsoft.adalcache" yerine kullanılacak anahtar zinciri grubunu belirtir. Bunun uygulama kimliği öneki içermediğini unutmayın. Bu, çalışma zamanında sağlanan dizeye önek olarak eklenir. | İsteğe bağlı. |
AppGroupIdentifiers | Dize dizisi  | Uygulamanın yetkilendirme dosyasının com.apple.security.application bölümündeki uygulama grupları dizisi. | Uygulama, uygulama grupları kullanıyorsa gereklidir. |
ContainingAppBundleId | Dize | Uzantıyı içeren uygulamanın paket kimliğini belirtir. | iOS uzantıları için gereklidir. |
DebugSettingsEnabled| Boole değeri | EVET olarak ayarlanırsa, Ayarlar paketindeki sınama ilkeleri uygulanabilir. Uygulamalar bu ayar etkin olarak *gönderilmemelidir*. | İsteğe bağlı. Varsayılan ayar Hayır’dır.|
MainNibFile <br> MainNibFile~ipad  | Dize  | Bu ayar, uygulamanın ana nib dosya adını içerir.  | Uygulama, Info.plist dosyasında MainNibFile tanımlıyorsa gereklidir. |
MainStoryboardFile <br> MainStoryboardFile~ipad  | Dize  | Bu ayar, uygulamanın ana görsel taslak dosya adını içerir. | Uygulama, Info.plist dosyasında UIMainStoryboardFile tanımlıyorsa gereklidir. |
MAMPolicyRequired| Boole değeri| Uygulama bir Intune APP ilkesine sahip değilse, uygulamanın başlatılmasının engellenip engellenmeyeceğini belirtir. Varsayılan ayar HAYIR’dır. <br><br> Not: App Store mampolicyrequired ayarı Evet olarak belirlenmişse uygulamalar gönderilemez. | İsteğe bağlı. Varsayılan ayar Hayır’dır.|
MAMPolicyWarnAbsent | Boole değeri| Uygulama bir Intune APP ilkesine sahip değilse, uygulamanın başlatıldığı sırada kullanıcıyı uyarıp uyarmayacağını belirtir. <br><br> Not: Kullanıcılara uyarı kapatıldıktan sonra da uygulamayı ilke olmadan kullanmak için yine de verilir. | İsteğe bağlı. Varsayılan ayar Hayır’dır. |
MultiIdentity | Boole değeri| Uygulamanın çoklu kimliği fark edip edemediğini belirtir. | İsteğe bağlı. Varsayılan ayar Hayır’dır. |
SplashIconFile <br> SplashIconFile~ipad | Dize  | Intune giriş (başlangıç) simge dosyasını belirtir. | İsteğe bağlı. |
SplashDuration | Sayı | Intune başlangıç ekranının uygulama başlatılırken gösterileceği en kısa süre miktarı (saniye cinsinden). Varsayılan olarak 1,5’tir. | İsteğe bağlı. |
BackgroundColor| Dize| Başlangıç ve PIN ekranlarının arka plan rengini belirtir. #XXXXXX biçiminde bir onaltılık RGB dizesini kabul eder; burada X, 0-9 veya A-F aralığındadır. Diyez işareti atlanabilir.   | İsteğe bağlı. Varsayılan olarak açık gridir. |
ForegroundColor| Dize| Metin rengi gibi, başlangıç ve PIN ekranlarının ön plan rengini belirtir. #XXXXXX biçiminde bir onaltılık RGB dizesini kabul eder; burada X, 0-9 veya A-F aralığındadır. Diyez işareti atlanabilir.  | İsteğe bağlı. Varsayılan olarak siyahtır. |
AccentColor | Dize| PIN ekranının düğme metni rengi ve kutu vurgu rengi gibi tema rengini belirtir. #XXXXXX biçiminde bir onaltılık RGB dizesini kabul eder; burada X, 0-9 veya A-F aralığındadır. Diyez işareti atlanabilir.| İsteğe bağlı. Varsayılan olarak sistem mavisidir. |
MAMTelemetryDisabled| Boole değeri| SDK’nın arka ucuna herhangi bir telemetri verisi gönderip göndermeyeceğini belirtir.| İsteğe bağlı. Varsayılan ayar Hayır’dır. |
MAMTelemetryUsePPE | Boole değeri | MAM SDK'sının PPE telemetri arka ucuna veri gönderip göndermeyeceğini belirtir. Sınama telemetri verilerinin müşteri verileriyle karışmaması için uygulamalarınızı Intune ilkesiyle sınarken bunu kullanın. | İsteğe bağlı. Varsayılan ayar Hayır’dır. |
MaxFileProtectionLevel | Dize | İsteğe bağlı. Uygulamanın destekleyebildiği maksimum `NSFileProtectionType` belirtmesine olanak tanır. Düzey uygulamanın destekleyebildiğinden daha yüksekse, bu değer hizmet tarafından gönderilen ilkeyi geçersiz kılar. Olası değerler: `NSFileProtectionComplete`, `NSFileProtectionCompleteUnlessOpen`, `NSFileProtectionCompleteUntilFirstUserAuthentication`, `NSFileProtectionNone`.|
OpenInActionExtension | Boole değeri | Şurada aç Eylemi uzantıları için EVET olarak ayarlayın. Daha fazla bilgi için UIActivityViewController yoluyla Veri Paylaşımı bölümüne bakın. |
WebViewHandledURLSchemes | Dize Dizisi | Uygulamanızın WebView’unun işlediği URL şemalarını belirtir. | Uygulamanız URL'leri bağlantılar ve/veya javascript aracılığıyla işleyen bir WebView kullanıyorsa gereklidir. |

## <a name="receive-app-protection-policy"></a>Uygulama koruma ilkesini alma

### <a name="overview"></a>Genel Bakış

Intune uygulama koruma ilkesini almak için, uygulamaların Intune MAM hizmetiyle bir kayıt isteği başlatmaları gerekir. Uygulamalar, Intune konsolunda cihaz kaydıyla veya cihaz kaydı olmadan uygulama koruma ilkesini almak için yapılandırılabilir. Kayıt olmadan uygulama koruma ilkesi (**APP-WE** veya MAM-WE olarak da bilinir), uygulamaların Intune mobil cihaz yönetimine (MDM) kaydedilmeden Intune tarafından yönetilmesine izin verir. Her iki durumda da, ilkeyi almak için Intune MAM hizmetine kaydolmak gereklidir.

### <a name="apps-that-use-adal"></a>ADAL kullanan uygulamalar

Zaten ADAL kullanan uygulamalar, kullanıcı başarıyla kimliğini doğruladıktan sonra `IntuneMAMEnrollmentManager` örneğinde `registerAndEnrollAccount` yöntemini çağırmalıdır:

```objc
/*
 *  This method will add the account to the list of registered accounts.
 *  An enrollment request will immediately be started.
 *  @param identity The UPN of the account to be registered with the SDK
 */

(void)registerAndEnrollAccount:(NSString *)identity;
```

SDK, `registerAndEnrollAccount` yöntemini çağırarak kullanıcı hesabını kaydeder ve uygulamayı bu hesap adına kaydetmeyi dener. Kayıt işlemi herhangi bir nedenle başarısız olursa SDK, kayıt işlemini 24 saat sonra otomatik olarak yeniden dener. Uygulama, hata ayıklama için bir temsilci yoluyla herhangi bir kayıt isteğinin sonuçlarıyla ilgili [bildirim](#Status-result-and-debug-notifications) alabilir.

Bu API çağrıldıktan sonra, uygulama normal çalışmasına devam edebilir. Kayıt başarılı olursa, SDK kullanıcıya uygulamanın yeniden başlatılması gerektiğini bildirir. Bu sırada, kullanıcı uygulamayı hemen yeniden başlatabilir.

```objc
[[IntuneMAMEnrollmentManager instance] registerAndEnrollAccount:@”user@foo.com”];
```

### <a name="apps-that-do-not-use-adal"></a>ADAL kullanılmayan uygulamalar

Kullanıcının ADAL kullanarak oturum açmasını sağlamayan bir uygulama, API’yi çağırıp SDK’nın söz konusu kimlik doğrulamasını gerçekleştirmesini sağlayarak Intune MAM hizmetinden uygulama koruma ilkesi alabilir. Azure AD ile bir kullanıcının kimlik doğrulamasını gerçekleştirmeyip, yine de verilerin korunmasına yardımcı olmak için uygulama koruma ilkesi alması gereken uygulamaların bu tekniği kullanması gerekir. Örneğin uygulamada oturum açmak için başka bir kimlik doğrulaması hizmeti kullanılıyor veya uygulama oturum açmayı hiç desteklemiyorsa. Bunu yapmak için, uygulamanın `IntuneMAMEnrollmentManager`örneğinden `loginAndEnrollAccount` yöntemini çağırabilir:

```objc
/**
 *  Creates an enrollment request which is started immediately.
 *  If no token can be retrieved for the identity, the user will be prompted
 *  to enter their credentials, after which enrollment will be retried.
 *  @param identity The UPN of the account to be logged in and enrolled.
 */
 (void)loginAndEnrollAccount: (NSString *)identity;
```

Mevcut herhangi bir belirteç bulunamazsa, SDK bu yöntemi çağırarak kullanıcıdan kimlik bilgilerini ister. Ardından SDK, sağlanan kullanıcı hesabı adına uygulamayı Intune MAM hizmetine kaydetmeyi dener. Yöntem, "nil" kimliği ile çağrılabilir. Bu durumda SDK cihazdaki mevcut yönetilen kullanıcıyı kaydeder (MDM'de) veya mevcut kullanıcı bulunamazsa kullanıcıdan kullanıcı adı girmesini ister.

Kayıt başarısız olursa, uygulama hatanın ayrıntılarına bağlı olarak bu API’yi gelecekte yeniden çağırmayı göz önünde bulundurmalıdır. Uygulama, bir temsilci yoluyla herhangi bir kayıt isteğinin sonuçlarıyla ilgili [bildirim](#Status-result-and-debug-notifications) alabilir.

Bu API çağrıldıktan sonra, uygulama normal çalışmasına devam edebilir. Kayıt başarılı olursa, SDK kullanıcıya uygulamanın yeniden başlatılması gerektiğini bildirir.

Örnek:
```objc
[[IntuneMAMEnrollmentManager instance] loginAndEnrollAccount:@”user@foo.com”];
```

### <a name="let-intune-handle-authentication-and-enrollment-at-launch"></a>Intune'un başlatma sırasında kimlik doğrulama ve kayıt işlemlerini işlemesini sağlama

Uygulamanızın başlatılması tamamlanmadan önce Intune SDK'sının ADAL kullanarak tüm kimlik doğrulaması ve kayıt işlemlerini yapmasını istiyorsanız ve uygulamanız her zaman APP ilkesi gerektiriyorsa, `loginAndEnrollAccount` API'sini kullanmanız gerekmez. Uygulamanın Info.plist dosyasındaki IntuneMAMSettings sözlüğünde aşağıdaki iki ayarı EVET olarak ayarlamanız yeterli olur.

Ayar  | Type  | Tanım |
--       |  --   |   --       |  
AutoEnrollOnLaunch| Boole değeri| Mevcut bir yönetilen kimlik tespit edilirse ve bu kimlik henüz kaydedilmemişse uygulama başlatıldığında otomatik olarak kaydetmeye çalışılıp çalışılmayacağını belirtir. Varsayılan ayar HAYIR’dır. <br><br> Not: Uygulamayı, ayrıca mampolicyrequired ayarı Evet olarak ayarlanmadığı sürece yönetilen kimlik bulunmadıysa veya ADAL önbelleğinde geçerli belirteç için kimlik kullanılabilir, bir kayıt denemesi sessizce kimlik bilgileri için sormadan başarısız olur. |
MAMPolicyRequired| Boole değeri| Uygulamanın bir Intune uygulama koruma ilkesine sahip olmadığında başlatılmasının engellenip engellenmeyeceğini belirtir. Varsayılan ayar HAYIR’dır. <br><br> Not: App Store mampolicyrequired ayarı Evet olarak belirlenmişse uygulamalar gönderilemez. MAMPolicyRequired EVET olarak ayarlandığında AutoEnrollOnLaunch da EVET olarak ayarlanmalıdır. |

Uygulamanız için bu seçeneği belirtirseniz, kayıt sonrasında uygulamanızı yeniden başlatma işlemini yapmanız gerekmez.

### <a name="deregister-user-accounts"></a>Kullanıcı hesaplarının kaydını kaldırma

Kullanıcı bir uygulamanın oturumunu kapatmadan önce, uygulamanın kullanıcı SDK kaydını kaldırması gerekir. Bu şunları sağlar:

1. Yeniden kayıt denemeleri kullanıcının hesabında artık gerçekleşmez.

2. Uygulama koruma ilkesi kaldırılır.

3. Bir uygulama seçmeli silme işlemi (isteğe bağlı) başlatırsa, tüm şirket verileri silinir.

Kullanıcı oturumunu kapatmadan önce, uygulamanın `IntuneMAMEnrollmentManager` örneğinde aşağıdaki yöntemi çağırması gerekir:

```objc
/*
 *  This method will remove the provided account from the list of
 *  registered accounts.  Once removed, if the account has enrolled
 *  the application, the account will be un-enrolled.
 *  @note In the case where an un-enroll is required, this method will block
 *  until the Intune APP AAD token is acquired, then return.  This method must be called before  
 *  the user is removed from the application (so that required AAD tokens are not purged
 *  before this method is called).
 *  @param identity The UPN of the account to be removed.
 *  @param doWipe   If YES, a selective wipe if the account is un-enrolled
 */
(void)deRegisterAndUnenrollAccount:(NSString *)identity withWipe:(BOOL)doWipe;
```

Bu yöntem, kullanıcı hesabının Azure AD belirteçleri silinmeden önce çağrılmalıdır. SDK, kullanıcı adına Intune MAM hizmetinde belirli isteklerde bulunmak için kullanıcı hesabının AAD uygulama belirtecine gerek duyar.

Uygulama kullanıcının şirket verilerini kendi kendine silerse, `doWipe` bayrağı false olarak ayarlanabilir. Aksi takdirde uygulama, seçmeli silme işlemini SDK’nın başlatmasını sağlayabilir. Bu, uygulamanın seçmeli silme temsilcisine çağrı yapılmasına neden olur.

Örnek:
```objc
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@”user@foo.com” withWipe:YES];
```

## <a name="status-result-and-debug-notifications"></a>Durum, sonuç ve hata ayıklama bildirimleri

Uygulama, Intune MAM hizmetine yapılan aşağıdaki istekler hakkında durum, sonuç ve hata ayıklama bildirimleri alabilir:

* Kayıt istekleri
* İlke güncelleştirme istekleri
* Kayıt kaldırma istekleri

Bildirimler temsilci yöntemleri aracılığıyla `IntuneMAMEnrollmentDelegate.h` içinde sunulur:

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

* İstekle ilişkili hesabın kimliği
* İstek sonucunu gösteren bir durum kodu
* Durum kodunun açıklamasını içeren bir hata dizesi
* `NSError` nesnesi. Bu nesne, getirilebilecek belirli durum kodlarıyla birlikte `IntuneMAMEnrollmentStatus.h` içinde tanımlanır.

> [!NOTE]
> Bu bilgiler yalnızca hata ayıklama amacına yöneliktir. Uygulamanızdaki hiçbir iş mantığı bu bildirimlere dayalı olmamalıdır. Bu bilgiler hata ayıklama veya izleme amacıyla telemetri hizmetine gönderilebilir.

### <a name="sample-code"></a>Örnek kod

Aşağıdakiler temsilci yöntemlerine örnek uygulamalardır:

```objc
- (void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus*)status
{
    NSLog(@"enrollment result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

- (void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus*)status
{
    NSLog(@"policy check-in result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

- (void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus*)status
{
    NSLog(@"un-enroll result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}
```

## <a name="application-restart"></a>Uygulama yeniden başlatma

Bir uygulama MAM ilkelerini ilk kez aldığında, gerekli kancaları uygulamak için yeniden başlatılması gerekir. Bir uygulamaya yeniden başlatma gerekliliğini bildirmek için, SDK `IntuneMAMPolicyDelegate.h` içinde bir temsilci yöntemi sağlar.

```objc
 - (BOOL) restartApplication
```

Bu yöntemin dönüş değeri, uygulamanın gerekli yeniden başlatma işlemini kendi yapmasının gerekip gerekmediğini SDK’ya bildirir:

* Dönüş değeri true olursa, uygulamanın yeniden başlatma işlemini kendi yapması gerekir.

* Dönüş değeri false olursa, SDK uygulamayı bu yöntemin dönüşünün ardından yeniden başlatır. SDK kullanıcıya uygulamayı hemen yeniden başlatmasını belirten bir iletişim kutusu gösterir.

## <a name="customize-your-apps-behavior-with-apis"></a>Uygulamanızın davranışını API’lerle özelleştirme

Intune Uygulama SDK'sında, uygulamaya dağıtılan Intune APP ilkesi hakkında bilgi almak için çağırabileceğiniz birkaç API vardır. Uygulamanızın davranışını özelleştirmek için bu verileri kullanabilirsiniz. Aşağıdaki tabloda kullanacağınız bazı temel Intune sınıflarıyla ilgili bilgi sağlanır.

Sınıf | Açıklama
----- | -----------
IntuneMAMPolicyManager.h | IntuneMAMPolicyManager sınıfı, uygulamaya dağıtılan Intune APP ilkesini gösterir. Özellikle, [Çoklu kimliği etkinleştirme](app-sdk-ios.md#enable-multi-identity-optional) için faydalı olan API’leri gösterir. |
IntuneMAMPolicy.h | IntuneMAMPolicy sınıfı uygulamaya uygulanan bazı MAM ilkesi ayarlarını gösterir. Bu ilke ayarları, uygulamanın kendi kullanıcı arabirimini özelleştirebilmesi için gösterilir. İlke ayarlarının çoğu uygulama değil SDK tarafından zorlanır. Uygulamada kullanılması gereken tek ayar Farklı kaydet denetimidir. Bu sınıf Farklı kaydet'i uygulamak için gereken bazı API'leri gösterir. |
IntuneMAMFileProtectionManager.h | IntuneMAMFileProtectionManager sınıfı, uygulamanın sağlanan kimlik temelinde açıkça dosyaların ve dizinlerin güvenliğini sağlamak için kullanabileceği API'leri gösterir. Kimlik Inture tarafından yönetilebilir veya yönetilmeyen bir kimlik olabilir ve SDK uygun MAM ilkesini uygular. Bu sınıfın kullanımı isteğe bağlıdır. |
IntuneMAMDataProtectionManager.h | IntuneMAMDataProtectionManager sınıfı, uygulamanın sağlanan kimlik temelinde veri arabelleklerinin güvenliğini sağlamak için kullanabileceği API'leri gösterir. Kimlik Inture tarafından yönetilebilir veya yönetilmeyen bir kimlik olabilir ve SDK uygun şifrelemeyi uygular. |

## <a name="implement-save-as-controls"></a>Farklı kaydet denetimlerini uygulama

Intune, BT yöneticilerinin yönetilen bir uygulamanın verilerini hangi depolama konumlarına kaydedebileceğini seçmesine olanak tanır. Uygulamalar izin verilen depolama konumları için `IntuneMAMPolicy.h` içinde tanımlanan `isSaveToAllowedForLocation` API’sini kullanarak Intune Uygulama SDK'sını sorgulayabilir.

Yönetilen verileri bulut depolama alanına veya yerel konumlara kaydetmeden önce, BT yöneticisinin o konuma veri kaydedilmesine izin verip vermediğini öğrenmek için uygulamaların `isSaveToAllowedForLocation` API’sini denetlemesi gerekir.

Uygulamalar `isSaveToAllowedForLocation` API'sini kullanırken, depolama konumu için kullanılan UPN’den (varsa) geçmeleri gerekir.

### <a name="supported-save-locations"></a>Desteklenen kaydetme konumları

`isSaveToAllowedForLocation` API’si, BT yöneticisinin aşağıdaki konumlara veri kaydetme izni verip vermediğinin denetlenmesini sağlayan ve `IntuneMAMPolicy.h` içinde tanımlanan sabitler sağlar:

* IntuneMAMSaveLocationOther
* IntuneMAMSaveLocationOneDriveForBusiness
* IntuneMAMSaveLocationSharePoint
* IntuneMAMSaveLocationLocalDrive

Uygulamalar, OneDrive İş gibi “yönetilen” veya “kişisel” olarak kabul edilen konumlara veri kaydedilip kaydedilemeyeceğini denetlemek için `isSaveToAllowedForLocation` içindeki sabitleri kullanmalıdır. Ayrıca uygulama bir konumun “yönetilen” veya “kişisel” olup olmadığını denetleyemiyorsa API kullanılmalıdır.

"Kişisel" olarak bilinen konumları, `IntuneMAMSaveLocationOther` sabiti temsil eder.

Uygulama yerel cihazdaki herhangi bir konuma veri kaydediyorsa `IntuneMAMSaveLocationLocalDrive` sabiti kullanılmalıdır.

## <a name="share-data-via-uiactivityviewcontroller"></a>UIActivityViewController yoluyla Veri Paylaşımı

Sürüm 8.0.2'den başlayarak, yalnızca Intune tarafından yönetilen paylaşım konumları arasından seçim yapılmasını sağlamak üzere Intune Uygulama SDK'sı `UIActivityViewController` eylemlerini filtreleyebilir. Bu davranış, uygulama veri aktarımı ilkesi tarafından denetlenecektir.

### <a name="copy-to-actions"></a>“Şuraya Kopyala” eylemleri

`UIActivityViewController` ve `UIDocumentInteractionController` yoluyla belge paylaşırken, iOS bu belgeyi açmayı destekleyen tüm uygulamalar için “Şuraya kopyala” eylemleri görüntüler. Uygulamalar, Info.plist dosyalarındaki `CFBundleDocumentTypes` ayarı yoluyla destekledikleri belge türlerini bildirir. İlke yönetilmeyen uygulamalara paylaşımı yasaklarsa, bu paylaşım türü artık kullanılabilir olmaz. Bunun yerine kullanıcı, kullanıcı arabirimi olmayan Eylem uzantısını ekleyip bunu Intune Uygulama SDK’sına bağlamak zorunda kalır. Eylem uzantısı, yalnızca bir saplamadır. SDK, dosya paylaşım davranışını uygular. Aşağıdaki adımları izleyin:

1. Uygulamanızın Info.plist `CFBundleURLTypes` ayarı altında en az bir schemeURL tanımlanmış olmalıdır.

2. Uygulamanız ve eylem uzantınız en az bir Uygulama Grubu paylaşmalıdır ve bu Uygulama Grubu IntuneMAMSettings sözlüklerindeki uygulamanın ve uzantısının altındaki `AppGroupIdentifiers` dizisi altında listelenmelidir.

3. Uygulama adından önce gelen “Şurada aç” eylem uzantısını adlandırın. Info.plist dosyasını ihtiyaca göre yerelleştirin.

4. [Apple’ın geliştirici belgelerinde](https://developer.apple.com/ios/human-interface-guidelines/extensions/sharing-and-actions/) açıklandığı gibi uzantısı için bir şablon sağlayın. Alternatif olarak, bu görüntüleri uygulamanın .app dizininden oluşturmak için IntuneMAMConfigurator aracı kullanılabilir. Bunu yapmak için şunu çalıştırın:

    ```bash
    IntuneMAMConfigurator -generateOpenInIcons /path/to/app.app -o /path/to/output/directory
    ```

5. Uzantının Info.plist dosyasındaki IntuneMAMSettings ayarında EVET değerine sahip bir `OpenInActionExtension` Boole ayarı ekleyin.

6. `NSExtensionActivationRule` kuralını, tek dosyayı ve uygulamanın `com.microsoft.intune.mam` ön ekli `CFBundleDocumentTypes` listesindeki tüm türleri destekleyecek şekilde yapılandırın. Örneğin uygulama public.text ve public.image destekliyorsa, etkinleştirme kuralı şu şekilde olur:

    ```objc
    SUBQUERY (
        extensionItems,
        $extensionItem,
        SUBQUERY (
            $extensionItem.attachments,
            $attachment,
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.text” ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.image”).@count == 1
    ).@count == 1
    ```

### <a name="update-existing-share-and-action-extensions"></a>Mevcut Paylaşım ve Eylem uzantılarını güncelleştirme

Uygulamanız zaten Paylaşım ve Eylem uzantılarını barındırıyorsa bunların `NSExtensionActivationRule` ayarları, Intune türlerine izin verecek şekilde değiştirilmelidir. Uzantının desteklediği her tür için `com.microsoft.intune.mam` ön ekli bir tür daha ekleyin. Örneğin mevcut etkinleştirme kuralı şu ise:  

```objc
SUBQUERY (
    extensionItems,
    $extensionItem,
    SUBQUERY (
        $extensionItem.attachments,
        $attachment,
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.url" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.plain-text" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.image" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.data"
    ).@count > 0
).@count > 0
```

Şu şekilde değiştirilmelidir:

```objc
SUBQUERY (
    extensionItems,
    $extensionItem,
    SUBQUERY (
        $extensionItem.attachments,
        $attachment,
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.url" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.plain-text" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.image" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.data" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.url" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.plain-text" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.image" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.data
    ).@count > 0
).@count > 0
```

> [!NOTE]
> Intune türlerini etkinleştirme kuralına eklemek için IntuneMAMConfigurator aracı kullanılabilir. Mevcut etkinleştirme kuralınız önceden tanımlı dize sabitleri (ör. NSExtensionActivationSupportsFileWithMaxCount, NSExtensionActivationSupportsText vb.) kullanıyorsa, koşul sözdizimi hayli karmaşıklaşabilir. IntuneMAMConfigurator aracı ayrıca, Intune türlerini eklerken etkinleştirme kuralını dize sabitlerinden koşul dizesine dönüştürmek için kullanılabilir.

### <a name="what-the-ui-should-look-like"></a>UI nasıl görünmeli?

Eski UI:

![Veri - iOS paylaşım kullanıcı Arabirimi eski paylaşma](./media/sharing-UI-old.png)

Yeni UI:

![Veri - yeni kullanıcı Arabirimi paylaşımı iOS paylaşım](./media/sharing-UI-new.png)

## <a name="enable-targeted-configuration-appmam-app-config-for-your-ios-applications"></a>iOS uygulamalarınız için hedeflenen yapılandırmayı (APP/MAM uygulama yapılandırması) etkinleştirme

MAM'ı hedefleyen yapılandırma (MAM uygulama yapılandırması olarak da bilinir), bir uygulamanın Intune SDK'sı aracılığıyla yapılandırma verileri almasını sağlar. Bu verilerin biçimi ve çeşitleri, uygulamanın sahibi/geliştiricisi tarafından tanımlanmalı ve Intune müşterilerine bildirilmelidir.

Intune yöneticileri, yapılandırma verilerini Intune Azure portalı ve Intune Graph API aracılığıyla hedefleyip dağıtabilir. iOS için Intune Uygulama SDK’sının 7.0.1 sürümü itibarıyla, MAM’ı hedefleyen yapılandırmaya dahil olan uygulamalar, MAM Hizmeti aracılığıyla MAM’ı hedefleyen yapılandırma verileri sağlayabilmektedir. Uygulama yapılandırma verileri MDM kanalı yerine uygulamaya doğrudan MAM Hizmetimiz aracılığıyla iletilir. Intune Uygulama SDK'sı, bu konsollardan alınan verilere erişmesine erişmek için bir sınıf sağlar. Aşağıdaki öğeler önkoşullardır:

* MAM’ı hedefleyen yapılandırma kullanıcı arabirimine erişebilmeniz için uygulamanın Intune MAM hizmetine kaydedilmiş olması gerekir. Daha fazla bilgi için bkz. [Uygulama koruma ilkesi alma](#receive-app-protection-policy).

* Uygulamanızın kaynak dosyasına `IntuneMAMAppConfigManager.h` öğesini dahil edin.

* Uygulama Yapılandırma Nesnesini almak için `[[IntuneMAMAppConfigManager instance] appConfigForIdentity:]` öğesini çağırın.

* `IntuneMAMAppConfig` nesnesinde uygun seçiciyi çağırın. Örneğin, uygulamanızın anahtarı bir dizeyse `stringValueForKey` veya `allStringsForKey` kullanmanız uygun olur. Dönüş değerleri ve hata koşullarıyla ilgili ayrıntılı bir açıklama için bkz. `IntuneMAMAppConfig.h`.

Graph API’nin işlevleri hakkında daha fazla bilgi için bkz. [Graph API Başvurusu](https://developer.microsoft.com/graph/docs/concepts/overview).

iOS'da MAM'ı hedefleyen bir uygulama yapılandırma ilkesi oluşturma hakkında daha fazla bilgi için [iOS için Microsoft Intune uygulama yapılandırma ilkeleri kullanma](https://docs.microsoft.com/intune/app-configuration-policies-use-ios) konusunun MAM'ı hedefleyen uygulama yapılandırması hakkındaki bölümüne bakın.

## <a name="telemetry"></a>Telemetri

Varsayılan olarak iOS için Intune Uygulama SDK'sı, aşağıdaki tür olaylara ilişkin telemetrileri toplar:

* **Uygulama başlatma**: MDM kaydı ve benzeri olmadan Yönetim türü (MDM ile MAM), MAM göre MAM özellikli uygulama kullanımı hakkında bilgi Intune yardımcı olmak için.

* **Kayıt çağrıları**: Başarı oranı ve istemci tarafından yapılan kayıt çağrılarının diğer performans Ölçümleriyle ilgili bilgi Intune yardımcı olmak için.

* **Intune eylemlerini**: Sorunları tanılayın ve Intune işlevselliği sağlayacak yardımcı olmak için Intune SDK'sı eylemler hakkında bilgi topluyoruz.

> [!NOTE]
> Intune Uygulama SDK’sı telemetri verilerini mobil uygulamanızdan Microsoft Intune’a göndermemeyi seçerseniz, Intune Uygulama SDK’sının telemetre yakalama özelliğini devre dışı bırakmanız gerekir. IntuneMAMSettings sözlüğünde `MAMTelemetryDisabled` özelliğini EVET olarak ayarlayın.

## <a name="enable-multi-identity-optional"></a>Çoklu kimliği etkinleştirme (isteğe bağlı)

SDK varsayılan olarak, ilkeyi uygulamaya bir bütün olarak uygular. Çoklu kimlik, bir ilkeyi her bir kimlik düzeyinde uygulamak için etkinleştirebileceğiniz bir MAM özelliğidir. Bu, diğer MAM özelliklerine kıyasla daha fazla uygulama katılımı gerektirir.

Uygulama etkin kimliği değiştirmeyi amaçladığında, bunu uygulama SDK’sına bildirmesi gerekir. Ayrıca bir kimlik değişikliği gerektiğinde SDK bunu uygulamaya bildirir. Şu anda yalnızca tek bir yönetilen kimlik desteklenir. Kullanıcı cihaz veya uygulamayı kaydettikten sonra, SDK bu kimliği kullanır ve bunu birincil yönetilen kimlik olarak kabul eder. Uygulamadaki diğer kullanıcılar kısıtlanmamış ilke ayarlarıyla yönetilmeyen olarak kabul edilirler.

Bir kimliğin yalnızca dizi olarak tanımlandığını aklınızda bulundurun. Kimlikler büyük/küçük harfe duyarlıdır. SDK’ya kimlik için yapılan istekler, kimlik ayarlandığı sırada kullanılan özgün büyük/küçük harf dizimiyle aynı olmadığı sürece sonuç getirmeyebilir.

### <a name="identity-overview"></a>Kimliğe genel bakış

Kimlik, bir hesabın kullanıcı adıdır (örneğin, user@contoso.com). Geliştiriciler uygulamanın kimliğini aşağıdaki düzeylerde ayarlayabilir:

* **İşlem Kimliği**: İşlem genelindeki kimliği ayarlar ve genellikle tek kimlikli uygulamalar için kullanılır. Bu kimlik tüm görevleri, dosyaları ve UI’yi etkiler.

* **UI kimliği**: UI görevlerine Kes/kopyala/yapıştır, PIN, kimlik doğrulaması ve veri paylaşımı gibi ana iş parçacığında hangi ilkelerin uygulanacağını belirler. UI kimliği, şifreleme ve yedekleme gibi dosya görevlerini etkilemez.

* **İş parçacığı kimliği**: Geçerli iş parçacığında hangi ilkelerin uygulanacağını etkiler. Bu kimlik tüm görevleri, dosyaları ve UI’yi etkiler.

Kullanıcı yönetilse de yönetilmese de kimlikleri uygun olarak ayarlamak uygulamanın sorumluluğudur.

Herhangi bir zamanda, her iş parçacığı UI görevleri ve dosya görevleri için etkili bir kimliğe sahiptir. Bu, varsa hangi ilkelerin uygulanması gerektiğini denetlemek için kullanılan kimliktir. Kimlik, “kimliksiz” ise veya kullanıcı yönetilmiyorsa hiçbir ilke uygulanmaz. Aşağıdaki diyagramlar etkin kimliklerin nasıl belirlendiğini gösterir.

  ![Intune uygulama SDK'sı iOS: Kimliği belirleme işlemi](./media/ios-thread-identities.png)

### <a name="thread-queues"></a>İş parçacığı kuyrukları

Uygulamalar, iş parçacığı kuyruklarına genellikle zaman uyumsuz ve zaman uyumlu görevler gönderir. SDK, Genel Gönderme Merkezi (GCD) çağrılarını yakalar ve geçerli iş parçacığı kimliğini gönderilen görev ile ilişkilendirir. Görevler bittiğinde, SDK iş parçacığı kimliğini geçici olarak görev ile ilişkili kimlik olarak değiştirir, görevleri bitirir ve sonra özgün iş parçacığı kimliğini geri yükler.


`NSOperationQueue` GCD üzerinde oluşturulduğu için `NSOperations`, iş parçacığı kimliğinde görevler, `NSOperationQueue` öğesine eklendiği zaman çalışır. `NSOperations` veya doğrudan GCD üzerinde gönderilen işlevler ayrıca, geçerli iş parçacığı kimliğini çalıştıkları sırada değiştirebilirler. Bu kimlik, gönderen iş parçacığından devralınan kimliği geçersiz kılar.

### <a name="file-owner"></a>Dosya sahibi

SDK, yerel dosya sahiplerinin kimliklerini izler ve ilkeleri buna göre uygular. Dosya sahibi, bir dosya oluşturulduğunda veya bir dosya kesme modunda açıldığında belirlenir. Sahip, görevi gerçekleştiren iş parçacığının etkin dosya görevi kimliğine ayarlanır.

Alternatif olarak, uygulamalar `IntuneMAMFilePolicyManager` kullanarak sahip kimliğini açıkça ayarlayabilir. Uygulamalar, dosya sahibini almak ve UI kimliğini dosya içeriğini görüntülemeden önce ayarlamak için `IntuneMAMFilePolicyManager` kullanabilir.

### <a name="shared-data"></a>Paylaşılan veriler

Uygulama hem yönetilen hem de yönetilmeyen kullanıcı verilerini içeren dosyalar oluşturursa, yönetilen kullanıcının verilerini şifrelemek uygulamanın sorumluluğundadır. `IntuneMAMDataProtectionManager` içindeki `protect` ve `unprotect` API'lerini kullanarak veri şifreleyebilirsiniz.

`protect` yöntemi, bir kimliği yönetilen veya yönetilmeyen kullanıcı olarak kabul eder. Kullanıcı yönetiliyorsa, veriler şifrelenir. Kullanıcı yönetilmiyorsa, kimliği kodlayan verilere bir üst bilgi eklenir ancak veriler şifrelenmez. Verilerin sahibini almak için `protectionInfo` yöntemini kullanabilirsiniz.

### <a name="share-extensions"></a>Paylaşım uzantıları

Uygulama bir paylaşım uzantısı içeriyorsa, paylaşılan öğenin sahibi `IntuneMAMDataProtectionManager` içindeki `protectionInfoForItemProvider` yöntemiyle alınabilir. Paylaşılan öğe bir dosya ise, dosya sahibi ayarı SDK tarafından yapılır. Paylaşılan öğenin veri olması durumunda; bu veri bir dosyaya sabitlenmişse dosya sahibini ayarlamak ve bu veriyi UI’da göstermeden önce `setUIPolicyIdentity` API’sini çağırmak uygulamanın görevidir.

### <a name="turn-on-multi-identity"></a>Çoklu kimliği açma

Varsayılan olarak, uygulamalar tek kimlikli olarak değerlendirilir. SDK, kayıtlı kullanıcı için işlem kimliğini ayarlar. Çoklu kimlik desteğini etkinleştirmek için uygulamanın Info.plist dosyası içindeki IntuneMAMSettings sözlüğüne EVET değeri ve `MultiIdentity` adıyla bir Boole ayarı ekleyin.

> [!NOTE]
> Çoklu kimlik etkinleştirildiğinde işlem kimliği, UI kimliği ve iş parçacığı kimlikleri nil olarak ayarlanır. Uygulama, bunları uygun şekilde ayarlamaktan sorumludur.

### <a name="switch-identities"></a>Kimlikleri değiştirme

* **Uygulama tarafından başlatılan kimlik değişimi**:

    Başlatma sırasında, çoklu kimlik uygulamaları bilinmeyen, yönetilmeyen bir hesap altında çalışıyor gibi kabul edilir. Koşullu başlatma UI’si çalışmaz ve uygulamada hiçbir ilke uygulanmaz. Kimliğin değiştirilmesi gerektiğinde bunu SDK’ya bildirmek uygulamanın sorumluluğudur. Genellikle, bu durum uygulamanın belirli bir kullanıcı hesabına ait verileri göstermek üzere olduğu sırada gerçekleşir.

    Kullanıcının bir dizüstü bilgisayarda bir belge, posta kutusu veya sekme açmayı denemesi örnek olarak gösterilebilir. Dosya, posta kutusu veya sekme gerçekten açılmadan uygulamanın SDK’ya bildirimde bulunması gerekir. Bu `IntuneMAMPolicyManager` içindeki `setUIPolicyIdentity` API’si üzerinden yapılır. Bu API, kullanıcı yönetilse de yönetilmese de çağrılmalıdır. Kullanıcı yönetiliyorsa, SDK koşullu başlatma denetimleri gerçekleştirir (jailbreak algılama, PIN ve kimlik doğrulama gibi).

    Kimlik değişiminin sonucu, uygulamaya bir tamamlama işleyicisi üzerinden zaman uyumsuz olarak döndürülür. Uygulama; belge, posta kutusu veya sekmeyi açmayı başarılı sonuç kodu döndürülünceye kadar ertelemelidir. Kimlik değişimi başarısız olursa, uygulamanın görevi iptal etmesi gerekir.

* **SDK tarafından başlatılan kimlik değişimi**:

    SDK’nın uygulamadan belirli bir kimliğe değiştirilmesini istemesini gerektiren durumlar vardır. Çoklu kimlik uygulamalarının bu isteği işlemek için `IntuneMAMPolicyDelegate` içindeki `identitySwitchRequired` yöntemini uygulaması gerekir.

    Bu yöntem çağrıldığı zaman, uygulama belirli kimliğe değiştirilme isteğini yerine getirebiliyorsa, `IntuneMAMAddIdentityResultSuccess` öğesini tamamlama işleyicisine geçirmesi gerekir. Kimliği değiştirme işlemini yerine getiremiyorsa, uygulamanın `IntuneMAMAddIdentityResultFailed` öğesini tamamlama işleyicisine geçirmesi gerekir.

    Bu çağrıya yanıt olarak uygulamanın `setUIPolicyIdentity` öğesini çağırması gerekmez. SDK, uygulamanın yönetilmeyen bir kullanıcı hesabıyla değiştirilmesini gerektirirse, boş dize `identitySwitchRequired` çağrısına geçirilir.

* **Seçmeli silme**:

    Uygulama seçmeli silme ile temizlendiğinde, SDK `IntuneMAMPolicyDelegate` içindeki `wipeDataForAccount` yönetimini çağırır. Belirtilen kullanıcı hesabını ve onunla ilişkili tüm verileri kaldırmak uygulamanın sorumluluğudur. SDK, kullanıcının sahip olduğu tüm dosyaları kaldırma özelliğine sahiptir ve uygulamanın `wipeDataForAccount` çağrısından FALSE sonucu getirmesi durumunda bunu uygular.

    Bu yöntemin bir arka plan iş parçacığından çağrıldığını unutmayın. Kullanıcıya yönelik tüm veriler kaldırılana kadar uygulama bir değer döndürmemelidir (uygulama FALSE döndürürse dosyalar hariç olmak üzere).

## <a name="ios-best-practices"></a>iOS en iyi uygulamalar

iOS için geliştirmeye yönelik önerilen en iyi uygulamalar aşağıda verilmiştir:

* iOS dosya sistemi büyük/küçük harfe duyarlıdır. Büyük/küçük harf kullanımının `libIntuneMAM.a` ve `IntuneMAMResources.bundle` gibi adlar için doğru olduğundan emin olun.

* Xcode `libIntuneMAM.a` dosyasını bulamıyorsa, bu kitaplığın yolunu bağlayıcı arama yollarına ekleyerek sorunu düzeltebilirsiniz.

## <a name="faqs"></a>SSS

### <a name="are-all-of-the-apis-addressable-through-native-swift-or-the-objective-c-and-swift-interoperability"></a>Tüm API’ler yerel Swift veya Objective-C ile Swift birlikte çalışabilirliği aracılığıyla adreslenebilir mi?

Intune Uygulama SDK’sı API’leri yalnızca Objective-C içinde bulunur ve **yerel** Swift’i desteklemez. Objective-C ile Swift arasında birlikte çalışabilirlik gereklidir.

### <a name="do-all-users-of-my-application-need-to-be-registered-with-the-app-we-service"></a>Uygulamamın tüm kullanıcılarının APP-WE hizmetine kayıtlı olması gerekiyor mu?

Hayır. Aslında, yalnızca iş veya okul hesaplarının Intune uygulama SDK'sına kayıtlı olması gerekir. Bir hesabın iş veya okul bağlamında kullanıldığını belirlemek uygulamaların sorumluluğudur.

### <a name="what-about-users-that-have-already-signed-in-to-the-application-do-they-need-to-be-enrolled"></a>Uygulamada zaten oturum açmış kullanıcılar ne olacak? Kayıtlı olmaları gerekli mi?

Kullanıcıların kimliği başarıyla doğrulandıktan sonra kullanıcıları kaydetmek uygulamanın görevidir. Uygulama MDM bulunmayan MAM işlevselliğine sahip olmadan önce var olan hesapları kaydetmek de uygulamanın görevidir.

Bunu yapmak için uygulamanın `registeredAccounts:` yöntemini kullanması gerekir. Bu yöntem, Intune MAM hizmetine kayıtlı tüm hesapları içeren bir NSDictionary döndürür. Uygulamadaki herhangi bir mevcut hesap listede yoksa, uygulama bu hesapları `registerAndEnrollAccount:` aracılığıyla kaydetmelidir.

### <a name="how-often-does-the-sdk-retry-enrollments"></a>SDK, kayıtları ne sıklıkta yeniden dener?

SDK daha önce başarısız olan tüm kayıtları otomatik olarak 24 saatte bir yeniden dener. SDK, bu işlemi bir kullanıcının kuruluşunun kullanıcı uygulamada oturum açtıktan sonra MAM’ı etkinleştirildiğinden emin olmak için yapıyorsa kullanıcı başarıyla kaydedilir ve ilkeleri alır.

SDK, bir kullanıcının uygulamayı başarıyla kaydettiğini algıladığında yeniden denemeyi durdurur. Bunun nedeni, bir uygulamayı belirli bir zamanda yalnızca bir kullanıcının kaydedebilmesidir. Kullanıcının kaydı silinirse, yeniden denemeler aynı 24 saatlik zaman aralığında yeniden başlar.

### <a name="why-does-the-user-need-to-be-deregistered"></a>Kullanıcının kaydının neden kaldırılması gerekir?

SDK şu eylemleri arka planda düzenli aralıklarla gerçekleştirir:

* Uygulama henüz kaydedilmemişse, tüm kayıtlı hesapları 24 saatte bir kaydetmeyi dener.
* Uygulama kaydedildiyse, SDK her 8 saatte bir MAM ilkesi güncelleştirmelerini denetler.

Bir kullanıcının kaydını kaldırmak SDK’ya kullanıcının uygulamayı artık kullanmayacağını bildirir ve söz konusu kullanıcı hesabına ait periyodik olayların tümünü durdurabilir. Ayrıca bir uygulama kaydı silme işlemi ve gerekirse seçmeli silme işlemi tetikler.

### <a name="should-i-set-the-dowipe-flag-to-true-in-the-deregister-method"></a>Kaydı kaldırma yönteminde doWipe bayrağını true olarak ayarlamalı mıyım?

Bu yöntem, kullanıcının uygulamadaki oturumunu kapatmasından önce çağrılmalıdır.  Oturum kapatma işleminin bir parçası olarak kullanıcı verileri uygulamadan silinirse, `doWipe` false olarak ayarlanabilir. Ancak uygulama kullanıcı verilerini kaldırmazsa, SDK’nın verileri silebilmesi için `doWipe` true olarak ayarlanmalıdır.

### <a name="are-there-any-other-ways-that-an-application-can-be-un-enrolled"></a>Bir uygulama kaydının kaldırılmasının başka yolları var mı?

Evet, BT yöneticisi uygulamaya bir seçmeli silme komutu gönderebilir. Bu, kullanıcının kaydını kaldırır, siler ve kullanıcı verilerini temizler. SDK bu senaryoyu otomatik olarak işler ve kayıt silme temsilci yöntemiyle bir bildirim gönderir.

### <a name="is-there-a-sample-app-that-demonstrates-how-to-integrate-the-sdk"></a>SDK'nın nasıl tümleştirileceğini gösteren örnek bir uygulama var mı?

Evet! Açık kaynak örnek uygulamamız [Wagr for iOS](https://github.com/Microsoft/Wagr-Sample-Intune-iOS-App)'yi kısa süre önce yeniledik. Wagr artık Intune Uygulama SDK'sının kullanıldığı uygulama koruma ilkesi için etkinleştirildi.

## <a name="submit-your-app-to-the-app-store"></a>Uygulamanızı App Store’a gönderme

Intune Uygulama SDK’sının hem statik kitaplığı hem de çerçeve derlemesi evrensel ikili dosyalardır. Yani tüm cihaz ve benzetici mimarilerine yönelik kodları içerirler. Apple, App Store’a gönderilen uygulamaları benzetici kodu içermeleri durumunda reddeder. Yalnızca cihaz derlemeleri için statik kitaplığa karşı derleme yapıldığında, bağlayıcı, benzetici kodunu otomatik olarak çıkartır. Uygulamanızı App Store’a yüklemeden önce tüm benzetici kodunun kaldırıldığından emin olmak için aşağıdaki adımları uygulayın.

1. `IntuneMAM.framework` öğesinin masaüstünüzde olduğundan emin olun.

2. Aşağıdaki komutları çalıştırın:

    ```bash
    lipo ~/Desktop/IntuneMAM.framework/IntuneMAM -remove i386 -remove x86_64 -output ~/Desktop/IntuneMAM.device_only
    ```

    ```bash
    cp ~/Desktop/IntuneMAM.device_only ~/Desktop/IntuneMAM.framework/IntuneMAM
    ```
    İlk komut, benzetici mimarilerini çerçevenin DYLIB dosyasından kaldırır. İkinci komut, yalnızca cihaz DYLIB dosyasını çerçeve klasörüne kopyalar.
