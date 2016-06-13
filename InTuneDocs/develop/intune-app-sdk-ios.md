---
# required metadata

title: iOS için Microsoft Intune Uygulama SDK’sı Geliştirici Kılavuzu | Microsoft Intune
description:
keywords:
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# iOS için Microsoft Intune Uygulama SDK’sı Geliştirici Kılavuzu

> [!NOTE] Öncelikle, desteklenen platformlarda tümleştirme için nasıl hazırlık yapıldığını açıklayan [Intune Uygulama SDK’sını Kullanmaya Başlama Kılavuzu](intune-app-sdk-get-started.md)’nu okumanız önerilir. 

iOS için Microsoft Intune Uygulama SDK’sı, Intune Mobil Uygulama Yönetimi’ni (MAM) iOS uygulamanıza eklemenizi sağlar. MAM özellikli bir uygulama, Intune Uygulama SDK'sı ile tümleşiktir ve uygulama etkin bir şekilde yönetildiğinde, BT yöneticilerinin ilkeleri mobil uygulamanıza dağıtmasını sağlar.

# SDK’nın kapsamı

iOS için Intune Uygulama SDK'sı; bir statik kitaplık, kaynak dosyaları, API üst bilgileri, bir Hata Ayıklama ayarları plist dosyası ve bir yapılandırıcı aracı içerir. Mobil uygulamalar yalnızca kaynak dosyalar içerebilir ve çoğu ilke zorlaması için kitaplıklarla statik bağlantılar oluşturabilir. Gelişmiş Intune MAM özellikleri API'ler aracılığıyla zorunlu kılınır.
Bu kılavuz, iOS için Intune Uygulama SDK'sı tümleştirilirken aşağıdakilerin kullanılmasını açıklar:

* **`libIntuneMAM.a`**: Intune Uygulama SDK’sı kitaplığı. Bu kitaplığı projenizle ilişkilendirerek mobil uygulamanızda MAM özelliğini etkinleştirin. Yönergeler buradaki "Uygulamanızı Intune Uygulama SDK'sı ile oluşturma" bölümünde bulunur.

* **`IntuneMAMResources.Bundle`**: SDK’nın bağımlı olduğu kaynakları içeren bir kaynak paketi. 

* **Üst bilgiler**: Intune Uygulama SDK'sı API'lerini gösterir. API kullanırsanız, API’yi içeren üst bilgi dosyasını dahil etmeniz gerekir. 

# Intune Uygulama SDK’sı nasıl çalışır?

iOS için Intune Uygulama SDK'sının amacı, kodda minimum düzeyde değişiklik yaparak iOS uygulamalarına yönetim özellikleri eklemeyi sağlamaktır. Kod değişiği miktarının azaltılması, pazarlama süresini kısaltırken mobil uygulamanızın tutarlılığını ve kararlılığını artırır. 

Uygulamanın statik kitaplığa bağlanması ve kaynak paketini içermesi gerekir. MAMDebugSettings.plist dosyası isteğe bağlıdır. Bu dosya, uygulamayı Microsoft Intune aracılığıyla dağıtmaya gerek kalmadan geçerli MAM ilkelerinin benzetimini gerçekleştirmek amacıyla pakete eklenebilir. Ayrıca hata ayıklama derlemelerinde, MAMDebugSettings.plist dosyası iTunes dosya paylaşımı aracılığıyla uygulamanın Belgeler dizinine aktarılarak, MAMDebugSettings.plist dosyasındaki ilkeler uygulanabilir.

# Intune Uygulama SDK'sı ile uygulamanızı oluşturma 

Intune Uygulama SDK'sını etkinleştirmek için aşağıdaki adımları tamamlayın:

1. Aşağıdakileri yaparak `libIntuneMAM.a` kitaplığına bağlantı oluşturun:

    libIntuneMAM.a kitaplığını proje hedefinin "Bağlantılı Çerçeveler ve Kitaplıklar" listesine sürükleyip bırakın.  

    ![Intune Uygulama SDK’sı iOS - bağlantılı çerçeveler ve kitaplıklar](../media/intune-app-sdk-ios-linked-frameworks-and-libraries.png)
 
    **Not**: Uygulama mağazasında yayınlarken lütfen yayın için oluşturulan ve hata ayıklama sürümü olmayan libIntuneMAM.a sürümünü kullanın. Yayın sürümü "sürüm" klasöründe olacaktır. Hata ayıklama sürümü, Intune Uygulama SDK'sı ile hata ayıklama için yararlı olan ayrıntılı çıktıyı içerir.

2. Aşağıdaki iOS çerçevelerini projeye ekleyin (eksikse).
    * `MessageUI.framework`
    * `Security.framework`
    * `MobileCoreServices.framework`
    * `SystemConfiguration.framework`
    * `libsqlite3.dylib`
    * `libc++.dylib`
    * `ImageIO.framework`
    * `LocalAuthentication.Framework`
    * `AudioToolbox.framework`<br>

    **Not**: Uygulama iOS7’yi hedefliyorsa, `LocalAuthentication.Framework` 'Status' özniteliğini "İsteğe bağlı" olarak ayarlayın. 

    'Status' ayarlanmazsa uygulama iOS7’de başlatılamaz.

    **Not**: Xcode 7, `.dylib` uzantılarını `.tbd`.

3. `IntuneMAMResources.bundle` kaynak paketini “Derleme Aşamaları” içindeki “Paket Kaynaklarını Kopyala” altına sürükleyerek kaynak paketini projeye ekleyin. 

    ![Intune Uygulama SDK’sı iOS - paket kaynaklarını kopyalama](../media/intune-app-sdk-ios-copy-bundle-resources.png)

4. `{PATH_TO_LIB}` öğesini Intune Uygulama SDK'sı konumu ile değiştirerek `-force_load {PATH_TO_LIB}/libIntuneMAM.a` öğesini aşağıdakilerden birine ekleyin:
    * Projenin OTHER_LDFLAGS derlemesi yapılandırma ayarı 
    * Kullanıcı arabiriminin "Diğer Bağlayıcı Bayrakları"<br>

    **Not**: `PATH_TO_LIB`öğesini bulmak için `libIntuneMAM.a` dosyasını seçin ve ‘Dosya’ menüsünden ‘Bilgi Al’ öğesini belirleyin. ‘Nerede’ bilgisini (yol) ‘Bilgi’ penceresinin ‘Genel’ bölümünden kopyalayıp yapıştırın.

5. Mobil uygulamanız `info.plist`içinde bir ana Nib veya Film Şeridi tanımlıyorsa, Ana Film Şeridi veya Ana Nib dosyası alanlarını kaldırın. Daha önce kaldırdığınız Film Şeridi veya Nib değerlerini `IntuneMAMSettings` adlı yeni bir sözlük altına aşağıdaki anahtar adlarından uygun olanıyla birlikte ekleyin:
    * `MainStoryboardFile`
    * `MainStoryboardFile~ipad`
    * `MainNibFile`
    * `MainNibFile~ipad `
    
    Mobil uygulamanız `info.plist`dosyasında bir ana Nib veya Film Şeridi tanımlamıyorsa bu ayarlar **gerekli değildir**. 

    **Not**: Dosya gövdesinin herhangi bir yerine sağ tıklayıp, görünüm türünü “Ham Anahtarları/Değerleri Göster” olarak değiştirerek `info.plist` dosyasını ham biçimde görüntüleyebilirsiniz (anahtar adlarını görmek için).

6. Her bir proje hedefinde ‘Özellikler’ öğesine tıklayıp Anahtarlık Paylaşımı anahtarını etkinleştirerek anahtarlık paylaşımını etkinleştirin (önceden etkinleştirilmemişse). Anahtarlık paylaşımı, sonraki adıma devam etmek için gereklidir.

    **Not**: Sağlama profilinizin, yeni anahtarlık paylaşımı değerlerini desteklemesi gerekir. Anahtarlık erişim grupları bir joker karakteri desteklemelidir. Bunu doğrulamak için `.mobileprovision` dosyasını bir metin düzenleyicisinde açıp 'keychain-access-groups' araması yapın ve bir joker karakter kullandığınızdan emin olun, örn.: 

       <key>keychain-access-groups</key>
       <array>
       <string>YOURBUNDLESEEDID.*</string>
       </array>

7. Anahtarlık paylaşımını etkinleştirdikten sonra Intune Uygulama SDK'sı verilerinin depolanacağı ayrı bir erişim grubu oluşturmak için aşağıdaki adımları izleyin. Kullanıcı arabirimini veya yetkilendirmeler dosyasını kullanarak bir anahtarlık erişim grubu oluşturabilirsiniz:

    Kullanıcı arabirimini kullanarak anahtarlık erişim grubu oluşturmak için: 
    
    * Mobil uygulamanızda tanımlanmış bir anahtarlık erişim grubu yoksa, uygulamanın paket kimliğini ilk grup olarak ekleyin.
    * Paylaşılan com.microsoft.intune.mam anahtarlık grubunu ekleyin. Bu erişim grubu Intune Uygulama SDK'sı tarafından verileri depolamak için kullanılır.  
    * `com.microsoft.adalcache` öğesini var olan erişim gruplarınıza ekleyin. 
 
    ![Intune Uygulama SDK’sı iOS - anahtarlık paylaşımı](../media/intune-app-sdk-ios-keychain-sharing.png)

    Anahtarlık paylaşımı erişim grubunu oluşturmak için normal kullanıcı arabirimi yerine yetkilendirme dosyasını kullanıyorsanız, yetkilendirme dosyasında anahtarlık erişim grubunun başına `$(AppIdentifierPrefix)` eklemeniz gerekir. Örneğin: `$(AppIdentifierPrefix)com.microsoft.intune.mam` ve `$(AppIdentifierPrefix)com.microsoft.adalcache`.

    **Not**: Yetkilendirme dosyası, iOS uygulamanızın içinde özel izinler ve özellikler belirtmek için kullanılan ve mobil uygulamanıza özgü olan bir XML dosyasıdır.

8. iOS 9+ için geliştirilen mobil uygulamalarda, mobil uygulamanızın geçtiği her protokolü, mobil uygulamanızın `UIApplication canOpenURL` dosyasının `LSApplicationQueriesSchemes` dizisinde bulunan `info.plist` öğesine dahil etmeniz gerekir. Ayrıca, listelenen her protokol için yeni bir protokolün eklenmesi ve bu protokolün `-intunemam`. Diziye ayrıca `http-intunemam`, `https-intunemam`ve `ms-outlook-intunemam` öğelerini dahil etmeniz gerekir. 

9. Uygulama URL şemalarını `info.plist file`’nda tanımlıyorsa, her URL şeması için `-intunemam` sonekiyle başka bir şema ekleyin.

10. Uygulamanın yetkilendirmelerinde tanımlanan uygulama grupları varsa, bu grupları `IntuneMAMSettings` anahtarı altındaki `AppGroupIdentitifiers` sözlüğüne bir dize dizisi olarak ekleyin.

11. ADAL kitaplığını mobil uygulamanıza bağlayın. Objective C için ADAL kitaplığı [Github'dan alınabilir](https://github.com/AzureAD/azure-activedirectory-library-for-objc).

    **Not**: Intune Uygulama SDK’sı, 19.06.2015’ten itibaren ADAL aracısı dal kodunda test edilmiştir. ADAL kitaplığının en son/çalışan sürümü ile bağlantı oluşturduğunuzdan emin olun.

12. `ADALiOSBundle.bundle resource` paketini “Derleme Aşamaları” içindeki “Paket Kaynaklarını Kopyala” altına sürükleyerek kaynak paketini projeye ekleyin.

13. Kitaplığa bağlantı oluştururken `-force_load PATH_TO_ADAL_LIBRARY` bağlayıcı seçeneğini kullanın.

    `-force_load {PATH_TO_LIB}/libADALiOS.a` seçeneğini projenin OTHER_LDFLAGS derleme yapılandırma ayarına veya kullanıcı arabirimindeki “Diğer Bağlayıcı Bayrakları” seçeneğine ekleyin. “PATH_TO_LIB” değeri ADAL ikili dosyalarının konumuyla değiştirilmelidir. 

Mobil uygulamanız kendi kimlik doğrulaması için ADAL kullanıyorsa, lütfen burada bulunan "Azure Directory Kimlik Doğrulaması Kitaplık Ayarları" üzerindeki bölümü gözden geçirin.

## Telemetri 

iOS için Intune Uygulama SDK'sı, Microsoft Intune’a gönderilen kullanım olaylarına ilişkin telemetri verilerini varsayılan olarak günlüğe kaydeder.

Veriler aşağıdaki kullanım olaylarında günlüğe kaydedilir: 

1. Microsoft Intune’un yönetim türüne göre MAM özellikli uygulama kullanımı hakkında bilgi almasına yardımcı olmak amacıyla uygulama başlatma.

2. Microsoft Intune’un başarı oranı hakkında ve istemci tarafından yapılan enrollApplication çağrısının diğer performans ölçümleriyle ilgili bilgi edinmesine yardımcı olmak amacıyla EnrollApplication API çağrısı yapma.

**Not**: Intune Uygulama SDK’sı telemetri verilerini mobil uygulamanızdan Microsoft Intune’a göndermemeyi seçerseniz, **MAMTelemetryDisabled** özelliğini `MAMTelemetryDisabled` içinde ‘EVET’ olarak ayarlayarak Intune Uygulama SDK’sını `IntuneMAMSettings`.

## Azure Directory Kimlik Doğrulama Kitaplığı (ADAL) Ayarlarını Yapılandırma (isteğe bağlı)

Intune Uygulama SDK'sı, kimlik doğrulama ve koşullu başlatma senaryosu için ADAL kullanır. ADAL genellikle, uygulamaya verilen belirteçlerin güvenliğini sağlamak için, uygulamaların `ClientID`olarak bilinen benzersiz kimliği ve diğer tanımlayıcıları kaydetmesini ve almasını gerektirir. Intune Uygulama SDK’sı Azure Active Directory ile iletişim kurarken varsayılan kayıt değerlerini kullanır.  Uygulama kendi kimlik doğrulama senaryosu için ADAL kullanıyorsa, son kullanıcılardan kimlik doğrulamasının iki kez (Intune Uygulama SDK’sı tarafından bir kez ve uygulama tarafından bir kez) istenmemesi için, uygulamanın mevcut kayıt değerlerini kullanması ve Intune Uygulama SDK'sının varsayılan değerini geçersiz kılması gerekir. 

Uygulama kendi kimlik doğrulaması için ADAL kullanıyorsa, aşağıdaki adımlar gereklidir. Mobil uygulamanız ADAL’a bağımlı değilse başka bir eylem gerekmez. 

1. Projenin `Info.plist`dosyasında, `IntuneMAMSettings` anahtar adlı `ADALClientId`sözlüğü altında, ADAL çağrıları için kullanılacak `ClientID` değerini belirtin. 

2. Projenin `Info.plist`dosyasında, `IntuneMAMSettings` anahtar adlı `ADALRedirectUri`sözlüğü altında, ADAL çağrıları için kullanılacak Yeniden Yönlendirme URI’sini belirtin. Ayrıca, uygulamanızın Yeniden Yönlendirme URI’sinin biçimine bağlı olarak `ADALRedirectScheme` belirtmeniz gerekebilir.

## Uzantılarınızı Oluşturma (isteğe bağlı) 

Uzantı oluştururken, buradaki "Intune Uygulama SDK'sı ile uygulamanızı Oluşturma" bölümünde özetlenen ve mobil uygulamanızı oluşturmak için kullandığınız yönergeleri izleyin. Bu yönergelere ek olarak, IntuneMAMSettings sözlüğü altında, içeren uygulamanın paket kimliği değerine sahip bir ContainingAppBundleId anahtarı ekleyerek her bir uzantının info.plist dosyasını güncelleştirin.

## Çerçevelerinizi Oluşturma (isteğe bağlı)

Intune Uygulama SDK'sında yapılan son değişikliklerle birlikte, artık ekli uygulama çerçeveleri içeren mobil uygulamanızı belirli bir bağlayıcı bayrağı ile derlemeniz gerekmiyor. 

## Başlangıçtaki Görüntü Dosyaları (isteğe bağlı)

MAM özellikli bir uygulama Microsoft Intune tarafından etkin olarak yönetiliyorsa, Intune Uygulama SDK'sı, kullanıcıya uygulamanın yönetildiğini belirtmek için uygulama başlatılırken bir başlangıç ekranı görüntüler. İsterseniz, "Şirketiniz tarafından yönetilen" başlangıç sayfasında gösterilmek üzere görüntü dosyaları ekleyebilirsiniz. Görüntüler için aşağıdaki kılavuzları kullanın:

* Dosya adlarını uygulamanın info.plist dosyasındaki `IntuneMAMSettings` sözlüğüne `SplashIconFile` ve `SplashIconFile~ipad`. 

* Görüntü boyutu ve gereksinimleri:

    * iPhone 6s Plus ve iPhone 6 Plus için 180 x 180, diğer iPhone modelleri için 120x120 ve iPad için 152x152. 
    
    * Dosya adlarından `.png` uzantısını kaldırma 
    
    * Kitaplığa bağlantı oluştururken `@2x` sonekini ve 3 kat ölçek sürümleri için `@3x` sonekini kullanın. Görüntüler doğru boyutta değilse, uyacak şekilde ölçeklendirilir. SplashIconFile değerleri belirtilmezse, Intune Uygulama SDK’sı uygulamanın simgelerinden birini seçer (tüm iPhone’lar için 60x60, iPad için 76x76).

**Not**: Bu ekran başlatma ile tetiklenir, ancak kullanıcı tarafından kalıcı olarak kapatılabilir.

# Intune Uygulama SDK'sı Ayarlarını Yapılandırma

Uygulamanın `IntuneMAMSettings` dosyasında yer alan `info.plist` sözlüğü, Intune Uygulama SDK’sını yapılandırmak için kullanılır. Desteklenen tüm yapılandırmaların listesi aşağıda verilmiştir. 

Bu ayarlardan bazıları önceki bölümlerde ele alınmış olabilir ve bazıları tüm uygulamalar için geçerli değildir. 

Ayar  | Tür  | Tanım | Gerekli mi?
--|--|--|--
ADALClientId  | Dize  | Uygulamanın AAD istemci tanımlayıcısı. | Uygulama ADAL kullanıyorsa gereklidir.
ADALRedirectUri  | Dize  | Uygulamanın AAD yeniden yönlendirme URI'si. | Uygulama ADAL kullanıyorsa gereklidir. 
AppGroupIdentifier | Dize Dizisi  | Uygulamanın yetkilendirme dosyasının com.apple.security.application bölümündeki uygulama grupları dizisi. | Uygulama, uygulama grupları kullanıyorsa gereklidir.
ContainingAppBundleId  | Dize | Uzantıyı içeren uygulamanın paket kimliğini belirtir. | iOS uzantıları için gereklidir.
MainNibFile<br>MainNibFile~ipad  | Dize  | Bu ayar, uygulamanın ana nib dosya adını içerir.  | Uygulama info.plist dosyasında MainNibFile tanımlıyorsa gereklidir.
MainStoryboardFile<br>MainStoryboardFile~ipad  | Dize  | Bu ayar, uygulamanın ana ana film şeridi dosya adını içerir. | Uygulama info.plist dosyasında UIMainStoryboardFile tanımlıyorsa gereklidir
SplashIconFile <br>SplashIconFile~ipad  | Dize  | Intune giriş simge dosyasını belirtir. Daha fazla bilgi için burada bulunan "Başlangıçtaki Görüntü Dosyaları" bölümüne bakın. | İsteğe bağlı.
SplashDuration | Sayı | Intune Giriş ekranının uygulama başlatılırken gösterileceği en kısa süre miktarı (saniye cinsinden). Varsayılan olarak 1,5’tir. | İsteğe bağlı.
ADALLogOverrideDisabled | Boole değeri  | SDK’nın tüm ADAL günlüklerini (varsa, uygulamadan gelen ADAL çağrıları dahil) kendi günlük dosyasına yönlendirip yönlendirmeyeceğini belirtir. Varsayılan ayar HAYIR’dır. Uygulamanın kendi ADAL günlüğü geri aramasını ayarlamasını istiyorsanız EVET olarak ayarlayın. | İsteğe bağlı.

# Intune Uygulama SDK’sı üst bilgileri 

Aşağıdaki üst bilgiler, Intune Uygulama SDK'sının işlevselliğini etkinleştirmek için gereken API işlev çağrılarını içerir. 

    IntuneMAMAsyncResult.h
    IntuneMAMDataProtectionInfo.h
    IntuneMAMDataProtectionManager.h
    IntuneMAMFileProtectionInfo.h
    IntuneMAMFileProtectionManager.h
    IntuneMAMPolicyDelegate.h
    IntuneMAMLogger.h

# Xcode’da Intune Uygulama SDK'sı hatalarını ayıklama

MAM özellikli uygulamanızı Microsoft Intune ile test etmeden önce, Xcode’da `Settings.bundle` dosyasını kullanabilirsiniz. Böylece, Intune bağlantısına gerek olmadan test ilkelerini ayarlayabilirsiniz. Etkinleştirmek için:

* Projenizdeki en üst düzey klasöre sağ tıklayarak bir `Settings.bundle` ekleyin. Menüden "Ekle -> Yeni Dosya" seçimini yapın. Eklenecek "Kaynaklar" altında bulunan "Ayarlar Paketi" şablonunu seçin.

* Yalnızca hata ayıklama derlemelerinde, `MAMDebugSettings.plist` öğesini `Settings.bundle`.

* `Root.plist` dosyasına (Settings.bundle içinde) "Tür" için Alt Bölme, "Dosya Adı" için `MAMDebugSettings` değerine sahip bir tercih ekleyin.

* "Ayarlar -> Uygulamanızın-Adı" altında “Test İlkelerini Etkinleştir” seçeneğini açın/kapatın.

* Uygulamayı başlatın (Xcode içinde veya dışında). 

* "Ayarlar -> Uygulamanızın-Adı -> Test İlkelerini Etkinleştir" altında bir ilkeyi açın/kapatın, örn. 'PIN'.

* Uygulamayı başlatın (Xcode içinde veya dışında). PIN kodunun beklendiği gibi çalıştığını doğrulayın.

> [!NOTE] Ayarları etkinleştirmek ve açmak/kapatmak için artık "Ayarlar -> Uygulamanızın-Adı -> Test İlkelerini Etkinleştir" seçeneğini kullanabilirsiniz.

# iOS için Önerilen En İyi Uygulamalar

iOS için geliştirmeye yönelik olarak önerilen en iyi uygulamalardan bazıları aşağıda verilmiştir:

iOS dosya sistemi büyük/küçük harfe duyarlıdır. Dosya adları için büyük/küçük harflerin `libIntuneMAM.a` ve `IntuneMAMResources.bundle` gibi doğru olduğundan emin olun.

Xcode `libIntuneMAM.a`dosyasını bulamıyorsa, bu kitaplığın yolunu bağlayıcı arama yollarına ekleyerek sorunu düzeltebilirsiniz.



<!--HONumber=May16_HO2-->


