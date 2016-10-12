---
title: "iOS için Microsoft Intune Uygulama SDK’sı Geliştirici Kılavuzu | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 975708b5204ab83108a9174083bb87dfeb04a063
ms.openlocfilehash: 52ad28686fa279a7ec251d073283c3554d1c81fc


---

# iOS için Microsoft Intune Uygulama SDK’sı Geliştirici Kılavuzu

> [!NOTE]
> Öncelikle, desteklenen platformlarda tümleştirme için nasıl hazırlık yapıldığını açıklayan [Intune Uygulama SDK’sını Kullanmaya Başlama Kılavuzu](intune-app-sdk-get-started.md)’nu okumanız önerilir.* 

iOS için Microsoft Intune Uygulama SDK’sı, Intune Mobil Uygulama Yönetimi’ni (MAM) iOS uygulamanıza eklemenizi sağlar. MAM özellikli bir uygulama, Intune Uygulama SDK'sı ile tümleşiktir ve uygulama Intune tarafından etkin bir şekilde yönetildiğinde, BT yöneticilerinin ilkeleri mobil uygulamanıza dağıtmasını sağlar.


# SDK’nın kapsamı 

iOS için Intune Uygulama SDK'sı; bir statik kitaplık, kaynak dosyaları, API üst bilgileri, bir Hata Ayıklama ayarları plist dosyası ve bir yapılandırıcı aracı içerir. Mobil uygulamalar yalnızca kaynak dosyalar içerebilir ve çoğu ilke zorlaması için kitaplıklarla statik bağlantılar oluşturabilir. Gelişmiş Intune MAM özellikleri API'ler aracılığıyla zorunlu kılınır.

Bu kılavuz, iOS için Intune Uygulama SDK'sının aşağıdaki bileşenlerinin kullanımını açıklar:

* **libIntuneMAM.a**: Intune Uygulama SDK’sının statik kitaplığı. Uygulamanızda uzantılar kullanılmıyorsa, uygulamanızı Intune mobil uygulama yönetimi için etkinleştirmek üzere bu kitaplığı projenize bağlayın. Yönergeler, "Uygulamanızı Intune Uygulama SDK'sı ile oluşturma" bölümünde bulunur.

* **IntuneMAM.framework**: Intune Uygulama SDK’sı çerçevesi. Uygulamanızı Intune mobil uygulama yönetimi için etkinleştirmek üzere bu çerçeveyi projenize bağlayın. Uygulamanızda uzantılar kullanılıyorsa, projenizin birden çok statik kitaplık kopyası oluşturmasını önlemek için statik kitaplık yerine bu çerçeveyi kullanın.

* **IntuneMAMResources.bundle**: SDK’nın bağımlı olduğu kaynakları içeren bir kaynak paketi. 

* **Üst bilgiler**: Intune Uygulama SDK'sı API'lerini gösterir. API kullanırsanız, API’yi içeren üst bilgi dosyasını dahil etmeniz gerekir. Aşağıdaki üst bilgi dosyaları, Intune Uygulama SDK'sının işlevselliğini etkinleştirmek için gereken API işlev çağrılarını içerir. 
    
    * IntuneMAMAsyncResult.h
    * IntuneMAMDataProtectionInfo.h
    * IntuneMAMDataProtectionManager.h
    * IntuneMAMFileProtectionInfo.h
    * IntuneMAMFileProtectionManager.h
    * IntuneMAMPolicyDelegate.h
    * IntuneMAMLogger.h 


# Intune Uygulama SDK’sı nasıl çalışır?

iOS için Intune Uygulama SDK'sının amacı, kodda minimum düzeyde değişiklik yaparak iOS uygulamalarına yönetim özellikleri eklemeyi sağlamaktır. Daha az kod değişikliği vardır ve pazarlama süresi daha kısadır ancak mobil uygulamanızın tutarlılığı ve kararlılığı yine de garanti edilir. 

Uygulamanın statik kitaplığa bağlanması ve kaynak paketini içermesi gerekir. MAMDebugSettings.plist dosyası isteğe bağlıdır. Bu dosya, uygulamayı Microsoft Intune aracılığıyla dağıtmaya gerek kalmadan geçerli MAM ilkelerinin benzetimini gerçekleştirmek amacıyla pakete eklenebilir. Ayrıca hata ayıklama derlemelerinde, MAMDebugSettings.plist dosyası iTunes dosya paylaşımı aracılığıyla uygulamanın Belgeler dizinine aktarılarak, dosyadaki ilkeler uygulanabilir.

# Mobil uygulamanızda SDK oluşturma 

Intune Uygulama SDK'sını etkinleştirmek için aşağıdaki adımları tamamlayın:

1. **1. Seçenek**: Aşağıdakileri yaparak `libIntuneMAM.a` kitaplığına bağlantı oluşturun:

    `libIntuneMAM.a` kitaplığını proje hedefinin "Bağlantılı Çerçeveler ve Kitaplıklar" listesine sürükleyip bırakın.
    ![Intune Uygulama SDK’sı iOS - bağlantılı çerçeveler ve kitaplıklar](../media/intune-app-sdk-ios-linked-frameworks-and-libraries.png) 

    **Not**: Uygulamanızı App Store’da yayınlamayı planlıyorsanız, lütfen yayın için oluşturulan ve hata ayıklama sürümü olmayan `libIntuneMAM.a` sürümünü kullanın. Yayın sürümü "sürüm" klasöründe olacaktır. Hata ayıklama sürümü, Intune Uygulama SDK'sı ile sorun giderme konuları için yararlı olan ayrıntılı çıktıyı içerir.
    
    **2. Seçenek**: `IntuneMAM.framework` öğesini projenize bağlayın. `IntuneMAM.framework` öğesini proje hedefinin "Bağlantılı Çerçeveler ve Kitaplıklar" listesine sürükleyip bırakın.
    
    **Not**: Çerçeveyi kullanırsanız, uygulamanızı App Store’a göndermeden önce evrensel çerçeveden benzetici mimarilerini elle çıkarmanız gerekir. "Uygulamanızı App Store’a gönderme" adlı bölüme bakın.

2. Aşağıdaki iOS çerçevelerini projeye ekleyin:
    * MessageUI.framework
    * Security.framework
    * MobileCoreServices.framework
    * SystemConfiguration.framework
    * libsqlite3.dylib
    * libc++.dylib
    * ImageIO.framework
    * LocalAuthentication.framework
    * AudioToolbox.framework

    **Not**: Uygulama iOS 7’yi hedefliyorsa, `LocalAuthentication.framework` “Durum” özniteliğini “İsteğe bağlı” olarak ayarlayın. “Durum” ayarlanmazsa uygulama iOS 7’de başlatılamaz.

    **Not**: Xcode 7, `.dylib` uzantılarını `.tbd`.

3. `IntuneMAMResources.bundle` kaynak paketini “Derleme Aşamaları” içindeki “Paket Kaynaklarını Kopyala” altına sürükleyerek kaynak paketini projeye ekleyin.
![Intune Uygulama SDK’sı iOS - paket kaynaklarını kopyalama](../media/intune-app-sdk-ios-copy-bundle-resources.png)
 
4. `{PATH_TO_LIB}` öğesini Intune Uygulama SDK'sı konumu ile değiştirerek `-force_load {PATH_TO_LIB}/libIntuneMAM.a` öğesini aşağıdakilerden birine ekleyin:
    * Projenin `OTHER_LDFLAGS` derlemesi yapılandırma ayarı 
    * Kullanıcı arabiriminin "Diğer Bağlayıcı Bayrakları"<br>

    **Not**: `PATH_TO_LIB`öğesini bulmak için `libIntuneMAM.a` dosyasını seçin ve “Dosya” menüsünden “Bilgi Al” öğesini belirleyin. “Nerede” bilgisini (yol) “Bilgi” penceresinin “Genel” bölümünden kopyalayıp yapıştırın.

5. Mobil uygulamanız Info.plist içinde bir ana Nib veya Görsel Taslak tanımlıyorsa, Ana Görsel Taslak veya Ana Nib dosyası alanlarını kaldırın. Daha önce kaldırdığınız Görsel Taslak veya Nib değerlerini IntuneMAMSettings adlı yeni bir sözlük altına aşağıdaki anahtar adlarından uygun olanıyla birlikte ekleyin:
    * MainStoryboardFile
    * MainStoryboardFile~ipad
    * MainNibFile
    * MainNibFile~ipad
    
   **Not**: Mobil uygulamanız Info.plist dosyasında bir ana Nib veya Görsel Taslak tanımlamıyorsa bu ayarlar **gerekli değildir**. 

    **Not**: Dosya gövdesinin herhangi bir yerine sağ tıklayıp, görünüm türünü “Ham Anahtarları/Değerleri Göster” olarak değiştirerek Info.plist dosyasını ham biçimde görüntüleyebilirsiniz (anahtar adlarını görmek için).

6. Her bir proje hedefinde “Özellikler” öğesine tıklayıp “Anahtar Zinciri Paylaşımı” anahtarını etkinleştirerek anahtar zinciri paylaşımını etkinleştirin (önceden etkinleştirilmemişse). Anahtarlık paylaşımı, sonraki adıma devam etmek için gereklidir.

    **Not**: Sağlama profilinizin, yeni anahtarlık paylaşımı değerlerini desteklemesi gerekir. Anahtarlık erişim grupları bir joker karakteri desteklemelidir. Bunu doğrulamak için .mobileprovision dosyasını bir metin düzenleyicide açıp 'keychain-access-groups' araması yapın ve bir joker karakter kullandığınızdan emin olun, örneğin: 
    ```
    <key>keychain-access-groups</key>
    <array>
    <string>YOURBUNDLESEEDID.*</string>
    </array>
    ```
7. Anahtarlık paylaşımını etkinleştirdikten sonra Intune Uygulama SDK'sı verilerinin depolanacağı ayrı bir erişim grubu oluşturmak için aşağıdaki adımları izleyin. Kullanıcı arabirimini veya yetkilendirmeler dosyasını kullanarak bir anahtarlık erişim grubu oluşturabilirsiniz:

    Kullanıcı arabirimini kullanarak anahtarlık erişim grubu oluşturmak için: 
    
    * Mobil uygulamanızda tanımlanmış bir anahtarlık erişim grubu yoksa, uygulamanın paket kimliğini ilk grup olarak ekleyin.
    * `com.microsoft.intune.mam` paylaşılan anahtar zinciri grubunu ekleyin. Bu erişim grubu Intune Uygulama SDK'sı tarafından verileri depolamak için kullanılır.  
    * `com.microsoft.adalcache` öğesini var olan erişim gruplarınıza ekleyin. 

    ![Intune Uygulama SDK’sı iOS - anahtarlık paylaşımı](../media/intune-app-sdk-ios-keychain-sharing.png) 

    Anahtarlık paylaşımı erişim grubunu oluşturmak için normal kullanıcı arabirimi yerine yetkilendirme dosyasını kullanıyorsanız, yetkilendirme dosyasında anahtarlık erişim grubunun başına `$(AppIdentifierPrefix)` eklemeniz gerekir. Örneğin:  
    * `$(AppIdentifierPrefix)com.microsoft.intune.mam` 
    * `$(AppIdentifierPrefix)com.microsoft.adalcache`

    **Not**: Yetkilendirme dosyası, iOS uygulamanızın içinde özel izinler ve özellikler belirtmek için kullanılan ve mobil uygulamanıza özgü olan bir XML dosyasıdır.

8. Uygulama URL şemalarını Info.plist dosyasında tanımlıyorsa, her URL şeması için `-intunemam` sonekiyle başka bir şema ekleyin.

9. iOS 9+ için geliştirilen mobil uygulamalarda, uygulamanızın geçtiği her protokolü, uygulamanızın Info.plist dosyasının `UIApplication canOpenURL` dizisinde bulunan `LSApplicationQueriesSchemes` öğesine dahil etmeniz gerekir. Ayrıca, listelenen her protokol için yeni bir protokolün eklenmesi ve bu protokolün `-intunemam`. Diziye ayrıca `http-intunemam`, `https-intunemam`ve `ms-outlook-intunemam` öğelerini dahil etmeniz gerekir. 

10. Uygulamanın yetkilendirmelerinde tanımlanan uygulama grupları varsa, bu grupları `AppGroupIdentitifiers` anahtarı altındaki IntuneMAMSettings sözlüğüne bir dize dizisi olarak ekleyin.

11. Mobil uygulamanızı Azure Directory Kimlik Doğrulaması Kitaplığı’na (ADAL) bağlayın. Objective C için ADAL kitaplığı [Github'dan alınabilir](https://github.com/AzureAD/azure-activedirectory-library-for-objc).

    **Not**: Intune Uygulama SDK’sı, 19.06.2015’ten itibaren ADAL aracısı dal kodunda test edilmiştir. ADAL kitaplığının en son/çalışan sürümü ile bağlantı oluşturduğunuzdan emin olun.

12. `ADALiOSBundle.bundle` kaynak paketini “Derleme Aşamaları” içindeki “Paket Kaynaklarını Kopyala” altına sürükleyerek kaynak paketini projeye ekleyin.

13. Kitaplığa bağlantı oluştururken `-force_load PATH_TO_ADAL_LIBRARY` bağlayıcı seçeneğini kullanın.

    `-force_load {PATH_TO_LIB}/libADALiOS.a` seçeneğini projenin `OTHER_LDFLAGS` derleme yapılandırma ayarına veya kullanıcı arabirimindeki “Diğer Bağlayıcı Bayraklar” seçeneğine ekleyin. `PATH_TO_LIB` ADAL ikili dosyalarının konumuyla değiştirilmelidir. 

# Uygulamanızda Azure Directory Kimlik Doğrulama Kitaplığı (ADAL) ayarlarını yapılandırma 

Intune Uygulama SDK'sı, kimlik doğrulama ve koşullu başlatma senaryosu için ADAL kullanır. Cihaz kayıt senaryoları olmadan yönetim için MAM hizmetinde kullanıcı kimliğini kaydetmek için de ADAL kullanır. 

ADAL genellikle, uygulamaya verilen belirteçlerin güvenliğini sağlamak için uygulamaların ClientID olarak bilinen benzersiz kimliği ve diğer tanımlayıcıları kaydetmesini ve almasını gerektirir. Intune Uygulama SDK’sı Azure Active Directory ile iletişim kurarken varsayılan kayıt değerlerini kullanır.  

Uygulama kendi kimlik doğrulama senaryosu için ADAL kullanıyorsa, son kullanıcılardan kimlik doğrulamasının iki kez (Intune Uygulama SDK’sı tarafından bir kez ve uygulama tarafından bir kez) istenmemesi için uygulamanın mevcut kayıt değerlerini kullanması ve Intune Uygulama SDK'sının varsayılan değerlerini geçersiz kılması gerekir. 

##ADAL SSS

**Hangi ADAL ikili dosyalarını kullanmalıyım?** 

Intune Uygulama SDK'sı şu anda Koşullu Erişim gerektiren uygulamaları (dolayısıyla Microsoft Authenticator uygulamasına dayalı olan uygulamaları) desteklemek için [GitHub'da ADAL](https://github.com/AzureAD/azure-activedirectory-library-for-objc)’ın aracı dalını kullanır. Ancak, SDK hala ADAL’ın ana dalı ile uyumludur. Lütfen, uygulamanıza uygun olan dalı kullanın.

**ADAL ikili dosyalarına nasıl bağlantı kurarım?**

`-force_load {PATH_TO_LIB}/libADALiOS.a` seçeneğini projenin `OTHER_LDFLAGS` derleme yapılandırma ayarına veya kullanıcı arabirimindeki “Diğer Bağlayıcı Bayraklar” seçeneğine ekleyin. `PATH_TO_LIB` ADAL ikili dosyalarının konumuyla değiştirilmelidir. Ayrıca, ADAL paketini uygulamanıza kopyaladığınızdan emin olun.  

Daha fazla ayrıntı için [Github'da ADAL](https://github.com/AzureAD/azure-activedirectory-library-for-objc) yönergelerine bakın.


**Aynı sağlama profiliyle imzalanan diğer uygulamalarla ADAL önbelleğini nasıl paylaşırım?**

Uygulamanızda tanımlanmış bir anahtar zinciri erişim grubu yoksa, uygulamanın paket kimliğini ilk grup olarak ekleyin.
Anahtar zinciri yetkilendirmelerine `com.microsoft.adalcache` ve `com.microsoft.workplacejoin` erişim gruplarını ekleyerek ADAL SSO’yu etkinleştirin. 

ADAL paylaşımlı önbellek anahtar zinciri grubunu açıkça ayarlıyorsanız, ayarın `<app_id_prefix>.com.microsoft.adalcache` olduğundan emin olun. Bu ayarı geçersiz kılmadığınız sürece ADAL bunu sizin için ayarlar. `com.microsoft.adalcache` öğesini değiştirmek için özel bir anahtar zinciri grubu belirtmek isterseniz, bunu lütfen “IntuneMAMSettings” altındaki Info.plist içinde `ADALCacheKeychainGroupOverride` anahtarını kullanarak belirtin.

**Intune Uygulama SDK’sını uygulamamda zaten kullanılan ADAL ayarlarını kullanmaya nasıl zorlarım?** 

Uygulamanız zaten ADAL kullanıyorsa, aşağıdaki ayarları doldurma hakkında bilgi edinmek için lütfen aşağıdaki IntuneMAMSettings bölümüne göz atın:  

* ADALClientId
* ADALRedirectUri
* ADALRedirectScheme
* ADALCacheKeychainGroupOverride

**AAD üretim ve iç sınama ortamları arasında nasıl geçiş yapabilirim?**

`MAMPolicies.plist` içindeki `AadAuthorityURI` ayarı, ADAL çağrıları için kullanılan AAD ortamını belirtmek için kullanılabilir. Bu ayar, geçersiz kılınmadığı takdirde şu anda AAD Üretim Öncesi Ortamını (PPE) kullanmaya ayarlanmıştır.
    
PPE’ye karşı sınamak için bir derleme zamanı veya çalışma zamanı anahtarı kullanabilirsiniz. 

MAM hizmeti URL'leri ve AAD’ın derleme zamanı ortam anahtarı için `UsePPE` Boole bayrağını MAMEnvironment.plist içinde true olarak ayarlayın (**Not**: Bunu Info.plist aracılığıyla yapmak için destek sunulmaz). 

Bir çalışma zamanı ortam anahtarı için PPE kullanmak amacıyla standart kullanıcı varsayılanlarındaki `com.microsoft.intune.mam.useppe` öğesini "1" olarak ayarlayın. Bu, varolan `com.microsoft.intune.mam.AADAuthorityEnvironment` ayarının yerine geçer. 

**Çalışma zamanında sağlanan bir kiracıya özgü URL ile AAD yetkilisi URL’sini nasıl geçersiz kılarım?** 

IntuneMAMPolicyManager örneğinde `aadAuthorityUriOverride` özelliğini seçin.

**Not**: SDK’nın uygulama tarafından alınan ADAL yenileme belirtecini yeniden kullanmasına izin vermek için cihaz kayıt senaryosu olmadan MAM’da buna gerek duyacaksınız.

**Not:** SDK, değerin temizlenmemesi veya değiştirilmemesi durumunda ilke yenileme ve bunu takip eden kayıt istekleri için bu yetkilendirme URL’sini kullanmaya devam eder.  Bu nedenle, bir şirket kullanıcısı uygulamadaki oturumunu kapattığında değeri temizlemek ve yeni bir şirket kullanıcısı oturum açtığında sıfırlamak önemlidir.


**Uygulamam kimlik doğrulaması için ADAL kullanıyorsa ne yapmalıyım?**

Uygulama kimlik doğrulaması için zaten ADAL kullanıyorsa aşağıdaki adımlar gereklidir. Uygulamanız ADAL’a bağımlı değilse; uygulamanızın ADAL kullanmaması durumunda Intune hizmetine kaydolma bölümünü gözden geçirmelisiniz.

* Projenin Info.plist dosyasında, `ADALClientId` anahtar adlı IntuneMAMSettings sözlüğü altında, ADAL çağrıları için kullanılacak ClientID değerini belirtin. 

* Projenin Info.plist dosyasında, `ADALRedirectUri` anahtar adlı IntuneMAMSettings sözlüğü altında, ADAL çağrıları için kullanılacak Yeniden yönlendirme URI'si değerini belirtin. Ayrıca, uygulamanızın Yeniden Yönlendirme URI’sinin biçimine bağlı olarak `ADALRedirectScheme` belirtmeniz gerekebilir.



#Uygulamanızı MAM hizmetine kaydetme 

## API'leri kullanma
Intune Uygulama SDK’sı artık iOS uygulamalarının Intune’a MDM ile kaydedilmesine gerek kalmadan Intune’dan MAM ilkelerini alma özelliği sunuyor. Bu yeni işlevselliği desteklemek için SDK, uygulamanın MAM ilkelerini almasına izin veren yeni API'ler sağlıyor. Yeni API'leri kullanabilmek için aşağıdaki adımları tamamlayın:

1. Cihaz kaydı ile veya cihaz kaydı olmadan uygulamaların yönetilmesini destekleyen son Intune Uygulama SDK’sı sürümünü kullanın. Uygulamanızda bu özelliğe sahip olmayan daha eski bir SDK sürümü kullanıldıysa, Intune MAM kitaplığını ve son SDK’nın üst bilgilerini içeren Üst Bilgiler klasörünü güncelleştirmeniz gerekir.

2. API’leri çağıran tüm dosyalara IntuneMAMEnrollment.h ekleyin 

3. PPE’ye karşı sınamak için bir derleme zamanı veya çalışma zamanı anahtarı kullanabilirsiniz. 

    MAM hizmeti URL'leri ve AAD’ın derleme zamanı ortam anahtarı için `UsePPE` Boole bayrağını MAMEnvironment.plist içinde true olarak ayarlayın (**not**: Bunu Info.plist aracılığıyla yapmak için destek sunulmaz). 

    Bir çalışma zamanı ortam anahtarı için PPE kullanmak amacıyla standart kullanıcı varsayılanlarındaki `com.microsoft.intune.mam.useppe` öğesini "1" olarak ayarlayın. Bu, varolan `com.microsoft.intune.mam.AADAuthorityEnvironment` ayarının yerine geçer. 


##Hesapları Kaydetme 

Bir uygulama belirli bir kullanıcı hesabı adına kaydedildiyse, Intune hizmetinden MAM ilkeleri alabilir.  Yeni oturum açan tüm kullanıcıları Intune Uygulama SDK'sına kaydetmek uygulamanın görevidir.  Yeni kullanıcı hesabının kimliği doğrulandıktan sonra uygulama, Headers/IntuneMAMEnrollment.h içinde bulunan `registerAndEnrollAccount` yöntemini çağırmalıdır: 

```
/** 


 *  This method will add the account to the list of registered accounts. 
 *  An enrollment request will immediately be started.
 *  @param identity The UPN of the account to be registered with the SDK 
 */ 

(void)registerAndEnrollAccount:(NSString *)identity; 

```
SDK, yukarıdaki yöntemi çağırarak kullanıcı hesabını kaydeder ve uygulamayı bu hesap adına kaydetmeyi dener.  Kayıt işlemi herhangi bir nedenle başarısız olursa, SDK kayıt işlemini 24 saat sonra otomatik olarak yeniden dener.  Uygulama, hata ayıklama amacıyla herhangi bir kayıt isteğinin sonuçlarıyla ilgili bir temsilci yoluyla bildirim alabilir (aşağıdaki ayrıntılara göz atın).

Bu API çağrıldıktan sonra, uygulama normal çalışmasına devam edebilir.  Kayıt başarılı olursa, SDK kullanıcıya uygulamanın yeniden başlatılması gerektiğini bildirir.  Bu sırada, kullanıcı uygulamayı hemen yeniden başlatabilir.


##Hesapların Kaydını Kaldırma 


Bir kullanıcı bir uygulamanın oturumunu kapatmadan önce, uygulamanın kullanıcının SDK kaydını kaldırması gerekir.  Bu şunları sağlar: 

1. Yeniden kayıt denemeleri kullanıcının hesabında artık gerçekleşmez. 
2. Kullanıcı uygulamayı başarıyla kaydettiyse, kullanıcı ve uygulamanın Intune MAM Hizmeti’ndeki kayıtları silinir ve MAM ilkeleri kaldırılır.
3. İsteğe bağlı olarak, tüm iş veya okul verilerinin silindiğinden emin olmak için seçmeli silme işlemi başlatılabilir. 

Kullanıcı oturumunu kapatmadan önce, uygulamanın Headers/IntuneMAMEnrollment.h içinde bulunan aşağıdaki API’yi çağırması gerekir: 

```
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

Bu yöntem, kullanıcı hesabının AAD belirteçleri silinmeden önce çağrılmalıdır.  SDK, kullanıcının uygulama belirtecinin kullanıcı adına Intune MAM Hizmeti’nde belirli isteklerde bulunmasını gerektirir. 

Uygulama kullanıcının iş veya okulla ilgili verilerini kendi kendine silerse, `doWipe` bayrağı false olarak ayarlanabilir.  Aksi takdirde, uygulama SDK’nın seçmeli silme başlatmasını sağlayabilir ve bu durumda uygulamanın seçmeli silme temsilcisine çağrı yapılır). 

```
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@”user@foo.com” withWipe:YES]; 
```


##Oturum Açmadan Önce Kaydetme 

Kullanıcının Azure Active Directory’de oturum açmasını sağlamayan bir uygulama, aşağıdaki API’yi çağırıp SDK’nın söz konusu kimlik doğrulamasını gerçekleştirmesini sağlayarak Intune Hizmeti’nden MAM ilkeleri alabilir. Uygulamalar AAD ile bir kullanıcının kimlik doğrulamasını gerçekleştirmediklerinde ancak uygulamalarındaki verileri korumak için MAM ilkelerini almaları gerektiğinde bunu kullanmalıdır. Örneğin; Başka bir kimlik doğrulama hizmeti, uygulamada oturum açma için kullanılıyorsa veya uygulama oturum açmayı hiçbir şekilde desteklemiyorsa. Bunu yapmak için uygulama Headers/IntuneMAMEnrollment.h içinde bulunan `loginAndEnrollAccount` yöntemini çağırmalıdır:

```
/** 
 *  Creates an enrollment request which is started immediately. 
 *  If no token can be retrieved for the identity, the user will be prompted 
 *  to enter their credentials, after which enrollment will be retried. 
 *  @param identity The UPN of the account to be logged in and enrolled. 
 */ 
 (void)loginAndEnrollAccount: (NSString *)identity; 

```
Bu yöntemi çağrıldığına SDK, mevcut bir belirteç bulunamazsa kullanıcıdan kimlik bilgilerini girmesini ister ve ardından bu hesap adına uygulamayı kaydetmeyi dener. Bu yöntem “nil” kimliğiyle çağrılabilir ve bu durumda SDK cihazdaki mevcut MAM kullanıcısını kaydeder veya mevcut kullanıcı bulunamazsa kullanıcıdan kullanıcı adı girmesini ister. 

Kayıt başarısız olursa, uygulama hatanın ayrıntılarına bağlı olarak bu API’yi gelecekte yeniden çağırmayı göz önünde bulundurmalıdır. Uygulama herhangi bir kayıt isteğinin sonuçlarıyla ilgili bir temsilci yoluyla bildirim alabilir (ayrıntılara göz atın). 

Bu API çağrıldıktan sonra, uygulama normal çalışmasına devam edebilir.  Kayıt başarılı olursa, yukarıdaki hesap kaydetme bölümünde gösterildiği gibi, SDK kullanıcıya uygulamanın yeniden başlatılmasının gerektiğini bildirir. 

##Hata Ayıklama Bilgileri 

Uygulama, Intune MAM hizmetine yapılan aşağıdaki istekler hakkında hata ayıklama bildirimleri alabilir: 

 - Kayıt İstekleri 
 - İlke Güncelleştirme İstekleri 
 - Kayıt Silme İstekleri 

Bildirimler, Headers/IntuneMAMEnrollmentDelegate.h içinde bulunabilen temsilci yöntemleri aracılığıyla sunulur: 

```
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

Bu temsilci yöntemleri aşağıdaki bilgileri içeren bir ```IntuneMAMEnrollmentStatus``` nesnesi getirir: 

- İstekle ilişkili hesabın kimliği 
- İstek sonucunu gösteren Durum Kodu 
- Durum kodunun açıklamasını içeren bir hata dizesi 
- Bir NSError nesnesi 

Bu nesne, getirilebilecek belirli durum kodlarıyla birlikte Headers/IntuneMAMEnrollmentStatus.h içinde tanımlanır. 

Bu bilginin hata ayıklama amaçlı olduğuna ve hiçbir uygulamanın iş mantığının bu bildirimlere dayanmaması gerektiğine dikkat edilmesi önemlidir.  Buradaki amaç, uygulamanın bu bilgileri hata ayıklama veya izleme amacıyla telemetri hizmetine gönderebilmesidir. 


##Örnek Kod 

Aşağıdakiler temsilci yöntemlerine örnek uygulamalardır: 

```
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


##Uygulamayı Yeniden Başlatma 

Bir uygulama MAM ilkelerini ilk kez aldığında, gerekli kancaları uygulamak için yeniden başlatılması gerekir.  Bir uygulamaya yeniden başlatma gerekliliğini bildirmek için SDK, Headers/IntuneMAMPolicyDelegate.h içinde bir temsilci yöntemi sağlar. 
```
 - (BOOL) restartApplication 
```
Bu yöntemin dönüş değeri, uygulamanın gerekli yeniden başlatma işlemini uygulayıp uygulayamayacağını SDK’ya bildirir.   

 - Dönüş değeri true olursa, uygulama yeniden başlatma işlemini kendi yapar.   
 - Dönüş değeri false olursa, SDK uygulamayı bu yöntemin dönüşünün ardından yeniden başlatır.  SDK hemen, kullanıcıya uygulamanın yeniden başlatılması gerektiğini belirten bir iletişim kutusu getirir. 



# Intune Uygulama SDK'sı Ayarlarını Yapılandırma

Uygulamanın Info.plist dosyasında yer alan IntuneMAMSettings sözlüğü, Intune Uygulama SDK’sını yapılandırmak için kullanılır. Desteklenen tüm yapılandırmaların listesi aşağıda verilmiştir. 

Bu ayarlardan bazıları önceki bölümlerde ele alınmış olabilir ve bazıları tüm uygulamalar için geçerli değildir. 

Ayar  | Tür  | Tanım | Gerekli mi?
--       |  --   |   --       |  --
ADALClientId  | Dize  | Uygulamanın AAD istemci tanımlayıcısı. | Uygulama ADAL kullanıyorsa gereklidir.
ADALRedirectUri  | Dize  | Uygulamanın AAD yeniden yönlendirme URI'si. | Uygulama ADAL kullanıyorsa ADALRedirectUri veya ADALRedirectScheme gereklidir. 
ADALRedirectScheme  | Dize  | Uygulamanın AAD yeniden yönlendirme şeması. Bu, uygulamanın yeniden yönlendirme URI'si `scheme://bundle_id` biçimindeyse ADALRedirectUri yerine kullanılabilir. | Uygulama ADAL kullanıyorsa ADALRedirectUri veya ADALRedirectScheme gereklidir. 
ADALLogOverrideDisabled | Boole değeri  | SDK’nın tüm ADAL günlüklerini (varsa, uygulamadan gelen ADAL çağrıları dahil) kendi günlük dosyasına yönlendirip yönlendirmeyeceğini belirtir. Varsayılan ayar HAYIR’dır. Uygulamanın kendi ADAL günlüğü geri aramasını ayarlamasını istiyorsanız EVET olarak ayarlayın. | İsteğe bağlı.
ADALCacheKeychainGroupOverride | Dize  | ADAL önbelleğinde "com.microsoft.adalcache" yerine kullanılacak anahtar zinciri grubunu belirtir. Bunun uygulama kimliği öneki içermediğini unutmayın. Bu, çalışma zamanında sağlanan dizeye önek olarak eklenir. | İsteğe bağlı.
AppGroupIdentifiers | Dize Dizisi  | Uygulamanın yetkilendirme dosyasının com.apple.security.application bölümündeki uygulama grupları dizisi. | Uygulama, uygulama grupları kullanıyorsa gereklidir.
ContainingAppBundleId | Dize | Uzantıyı içeren uygulamanın paket kimliğini belirtir. | iOS uzantıları için gereklidir.
DebugSettingsEnabled| Boole değeri | EVET olarak ayarlanırsa, Ayarlar paketindeki sınama ilkeleri uygulanabilir. Uygulamalar bu ayar etkin olarak **gönderilmemelidir**. | İsteğe bağlı.
MainNibFile<br>MainNibFile~ipad  | Dize  | Bu ayar, uygulamanın ana nib dosya adını içerir.  | Uygulama Info.plist dosyasında MainNibFile tanımlıyorsa gereklidir.
MainStoryboardFile<br>MainStoryboardFile~ipad  | Dize  | Bu ayar, uygulamanın ana film şeridi dosya adını içerir. | Uygulama Info.plist dosyasında UIMainStoryboardFile tanımlıyorsa gereklidir
MAMPolicyRequired| Boole değeri| Uygulama Intune MAM ilkesine sahip değilse, uygulamanın başlatılmasının engellenip engellenmeyeceğini belirtir. Varsayılan ayar “hayır”dır. 
MAMPolicyWarnAbsent | Boole değeri| Uygulama Intune MAM ilkesine sahip değilse, uygulamanın başlatıldığı sırada kullanıcıyı uyarıp uyarmayacağını belirtir. Not: Bu ayar EVET olarak belirlenmişse uygulamalar mağazaya gönderilemez | İsteğe bağlı.
MultiIdentity | Boole değeri| Uygulamanın çoklu kimliği fark edip edemediğini belirtir | İsteğe bağlı.
SplashIconFile <br>SplashIconFile~ipad | Dize  | Intune giriş simge dosyasını belirtir. Daha fazla bilgi için burada bulunan "Başlangıçtaki Görüntü Dosyaları" bölümüne bakın. | İsteğe bağlı.
SplashDuration | Sayı | Intune Giriş ekranının uygulama başlatılırken gösterileceği en kısa süre miktarı (saniye cinsinden). Varsayılan olarak 1,5’tir. | İsteğe bağlı.
BackgroundColor| Dize| Giriş ve PIN ekranlarının arka plan rengini belirtir. ‘#XXXXXX’ biçiminde bir onaltılık RGB dizesini kabul eder; burada ‘X’ 0-9 veya A-F aralığındadır. Diyez işareti atlanabilir.   | İsteğe bağlı, varsayılan olarak açık gridir.
ForegroundColor| Dize| Metin rengi gibi, giriş ve PIN ekranlarının ön plan rengini belirtir. ‘#XXXXXX’ biçiminde bir onaltılık RGB dizesini kabul eder; burada ‘X’ 0-9 veya A-F aralığındadır. Diyez işareti atlanabilir.  | İsteğe bağlı, varsayılan olarak Siyahtır.
AccentColor | Dize| PIN ekranının düğme metin rengi ve kutu vurgu rengi gibi ara rengi belirtir.  ‘#XXXXXX’ biçiminde bir onaltılık RGB dizesini kabul eder; burada ‘X’ 0-9 veya A-F aralığındadır. Diyez işareti atlanabilir.| İsteğe bağlı, varsayılan olarak sistem mavisidir.
MAMTelemetryDisabled| Boole değeri| SDK’nın arka ucuna herhangi bir telemetri verisi gönderip göndermeyeceğini belirtir| İsteğe bağlı.
MAMTelemetryUsePPE | Boole değeri | SDK için Üretim Öncesi Ortam (PPE) arka ucuna veri gönderip göndermeyeceğini belirtir. Sınama telemetri verilerinin müşteri verileriyle karışmaması için uygulamalarınızı Intune ilkesiyle sınarken bunu kullanın. | İsteğe bağlı.

## Telemetri 

Varsayılan olarak iOS için Intune Uygulama SDK'sı, Microsoft Intune’a gönderilen kullanım olaylarına ilişkin telemetri verilerini günlüğe kaydeder. Veriler aşağıdaki kullanım olaylarında günlüğe kaydedilir: 

1. **Uygulama başlatma**: Microsoft Intune’un yönetim türüne göre MAM özellikli uygulama kullanımı hakkında bilgi almasına yardımcı olmak amaçlıdır (MDM ile MAM, MDM kaydı olmadan MAM vb.).

2. **EnrollApplication API çağrısı**: Microsoft Intune’un başarı oranı hakkında ve istemci tarafından yapılan `enrollApplication` çağrısının diğer performans ölçümleriyle ilgili bilgi edinmesine yardımcı olmak amaçlıdır.

**Not**: Intune Uygulama SDK’sı telemetri verilerini mobil uygulamanızdan Microsoft Intune’a göndermemeyi seçerseniz, `MAMTelemetryDisabled` özelliğini IntuneMAMSettings sözlüğü içinde ‘EVET’ olarak ayarlayarak Intune Uygulama SDK’sını devre dışı bırakmanız gerekir.


## SDK’yı uzantınız içinde oluşturma (isteğe bağlı) 

Uzantı oluştururken, "SDK’yı mobil uygulamanız içinde oluşturma” hakkındaki bölümde özetlenen ve mobil uygulamanızı oluşturmak için kullanılan yönergeleri izleyin. Ayrıca, IntuneMAMSettings sözlüğü altında, uygulamanın paket kimliği değerine sahip bir `ContainingAppBundleId` anahtarı ekleyerek her bir uzantının Info.plist dosyasını güncelleştirin.

## SDK’yı çerçeveniz içinde oluşturma (isteğe bağlı)

Intune Uygulama SDK'sında yapılan son güncelleştirmelerle birlikte, artık ekli uygulama çerçeveleri içeren mobil uygulamanızı belirli bir bağlayıcı bayrağı ile derlemeniz gerekmiyor. 

## Başlangıçtaki Görüntü Dosyaları (isteğe bağlı)

MAM özellikli bir uygulama Microsoft Intune tarafından etkin olarak yönetiliyorsa, Intune Uygulama SDK'sı, kullanıcıya uygulamanın yönetildiğini belirtmek için uygulama başlatılırken bir başlangıç ekranı görüntüler. İsterseniz, "Şirketiniz tarafından yönetilen" başlangıç sayfasında gösterilmek üzere görüntü dosyaları ekleyebilirsiniz. Görüntüler için aşağıdaki kılavuzları kullanın:

* Dosya adlarını, uygulamanın Info.plist dosyasındaki IntuneMAMSettings sözlüğüne `SplashIconFile` ve `SplashIconFile~ipad` anahtar adlarıyla ekleyin. 

* Görüntü boyutu ve gereksinimleri:

    * iPhone 6s Plus ve iPhone 6 Plus için 180 x 180, diğer iPhone modelleri için 120x120 ve iPad için 152x152. 
    
    * Dosya adlarından .png uzantısını kaldırın. 
    
    * Kitaplığa bağlantı oluştururken `@2x` sonekini ve 3 kat ölçek sürümleri için `@3x` sonekini kullanın. Görüntüler doğru boyutta değilse, uyacak şekilde ölçeklendirilir. SplashIconFile değerleri belirtilmezse, Intune Uygulama SDK’sı uygulamanın simgelerinden birini seçer (tüm iPhone’lar için 60x60, iPad için 76x76).

**Not**: Bu ekran başlatma ile tetiklenir, ancak kullanıcı tarafından kalıcı olarak kapatılabilir.



#Çoklu Kimliği Etkinleştirme (isteğe bağlı)

SDK varsayılan olarak, ilkeyi uygulamaya bir bütün olarak uygular. Çoklu Kimlik, ilkenin her kimlik düzeyinde uygulanmasına izin vermek üzere etkinleştirilebilen bir MAM özelliğidir.  Bu, diğer MAM özelliklerine kıyasla daha fazla uygulama katılımı gerektirir. 

Uygulama etkin kimliği değiştirmeyi amaçladığında, bunu uygulama SDK’sına bildirmesi gerekir. Ayrıca bir kimlik değişikliği gerektiğinde SDK bunu uygulamaya bildirir. Şu anda yalnızca tek bir yönetilen kimlik desteklenir. Kullanıcı cihaz veya uygulamayı kaydettikten sonra, SDK bu kimliği kullanır ve bunu birincil yönetilen kimlik olarak kabul eder. Uygulamadaki diğer kullanıcılar kısıtlanmamış ilke ayarlarıyla yönetilmeyen olarak kabul edilirler. 

Bir kimliğin yalnızca dizi olarak tanımlandığını aklınızda bulundurun. Kimlikler büyük/küçük harfe duyarlıdır ve SDK’ya kimlik için yapılan istekler, kimlik ayarlandığı sırada kullanılan özgün büyük/küçük harf dizimiyle aynı olmadığı sürece sonuç getirmeyebilir.


##Kimlikleri Anlama 
  
Bir kimlik bir hesabın kullanıcı adıdır (ör. user@contoso.com). Geliştiriciler uygulamanın kimliğini aşağıdaki farklı düzeylerde ayarlayabilir: 

* **İşlem kimliği**: İşlem kimliği işlem genelindeki kimliği ayarlar ve genellikle tek kimlikli uygulamalar için kullanılır. Bu kimlik tüm işlemleri, dosyaları ve UI’yi etkiler.
* **UI Kimliği**: Ana iş parçacığında UI işlemlerine kes/kopyala/yapıştır, PIN, kimlik doğrulaması, veri paylaşımı vb. gibi ilkelerden hangilerinin uygulanacağını belirler. UI kimliği, dosya işlemlerini (şifreleme, yedekleme vb.) etkilemez. 
* **İş parçacığı kimliği**: İş parçacığı kimliği geçerli iş parçacığında hangi ilkelerin uygulanacağını etkiler. Bu tüm işlemleri, dosyaları ve UI’yi etkiler.

Kullanıcı yönetilse de yönetilmese de kimlikleri uygun olarak ayarlamak uygulamanın sorumluluğudur.

Zaman içinde herhangi bir noktada, her iş parçacığı UI işlemleri ve dosya işlemleri için etkili bir kimliğe sahiptir. Bu, varsa hangi ilkelerin uygulanmasını gerektiğini belirleyen kimliktir. 'Kimlik' ‘kimliksiz’ ise ve kullanıcı yönetilmiyorsa hiçbir ilke uygulanmaz. 
 
 

##İş Parçacığı Kuyrukları
 
Uygulamalar, iş parçacığı kuyruklarına genellikle zaman uyumsuz ve zaman uyumlu görevler gönderir. SDK, Genel Gönderme Merkezi (GCD) çağrılarını yakalar ve geçerli iş parçacığı kimliğini gönderilen görev ile ilişkilendirir. Görevler çalıştırıldığında, SDK iş parçacığı kimliğini geçici olarak görev ile ilişkili kimlik olarak değiştirir, görevleri yürütür ve sonra özgün iş parçacığı kimliğini geri yükler. `NSOperationQueue` GCD üzerinde oluşturulduğundan `NSOperations`, iş parçacığı kimliğinde `NSOperationQueue` öğesine eklendiği zaman çalışır. `NSOperations` veya doğrudan GCD kullanılarak gönderilen işlevlerde, çalıştıkları sırada geçerli iş parçacığı kimliğini değiştirme özelliği de bulunur. Bu kimlik, gönderen iş parçacığından devralınan kimliği geçersiz kılar. 

##Dosya Sahibi
 
SDK, yerel dosya sahibi kimliğini izler ve ilkeleri buna göre uygular. Dosya sahibi, dosya oluşturulduğunda veya dosya kesme modunda açıldığında belirlenir. Sahip, işlemi gerçekleştiren iş parçacığının etkin dosya işlem kimliğine ayarlanır. Alternatif olarak, uygulamalar `IntuneMAMFilePolicyManager` kullanarak sahip kimliğini açıkça ayarlayabilir. Uygulamalar, dosya sahibini almak ve UI kimliğini dosya içeriğini görüntülemeden önce ayarlamak için `IntuneMAMFilePolicyManager` kullanabilir.


##Paylaşılan Veri Dosyaları
 
Uygulama hem yönetilen hem de yönetilmeyen kullanıcı verilerini içeren dosyalar oluşturursa, yönetilen kullanıcının verilerini şifrelemek uygulamanın sorumluluğundadır. Veriler, `IntuneMAMDataProtectionManager` öğesinin `protect` ve `unprotect` API’leri kullanılarak şifrelenebilir. `protect` yöntemi, bir kimliği yönetilen veya yönetilmeyen kullanıcı olarak kabul eder. Kullanıcı yönetiliyorsa, veriler şifrelenir. Kullanıcı yönetilmiyorsa, kimliği kodlayan verilere bir üst bilgi eklenir ancak veriler şifrelenmez.  `protectionInfo` yöntemi, verilerin sahibini almak için kullanılabilir.

##Paylaşım Uzantıları
 
Uygulama bir Paylaşım Uzantısı içeriyorsa, paylaşılan öğenin sahibi `IntuneMAMDataProtectionManager` içindeki `protectionInfoForItemProvider` yöntemi kullanılarak alınabilir. Paylaşılan öğe bir dosya ise, dosya sahibi ayarı SDK tarafından yapılır. Paylaşılan öğe veriyse, bu verinin bir dosyaya işlenmesi durumunda dosya sahibini ayarlamak ve bu veriyi UI’de göstermeden önce `setUIPolicyIdentity` API’sine çağrı yapmak uygulamanın sorumluluğudur (aşağıda açıklanmıştır).
 
#Çoklu Kimliği Etkinleştirme
 
Varsayılan olarak uygulamalar tek kimlik kabul edilir ve işlem kimliği SDK tarafından kayıtlı kullanıcıya ayarlanır. Çoklu kimlik desteğini etkinleştirmek için uygulamanın Info.plist dosyası içindeki IntuneMAMSettings sözlüğüne ‘EVET’ değeri ve 'MultiIdentity' adıyla bir boole ayarı eklenmesi gerekir. Çoklu kimlik etkinleştirildiğinde, işlem kimliği, UI kimliği ve iş parçacığı kimlikleri nil olarak ayarlanır ve bunları uygun bir şekilde ayarlamak uygulamanın sorumluluğudur.

 
##Kimlikleri Değiştirme
 
###Uygulama tarafından başlatılan kimlik değişimi
Başlatma sırasında, çoklu kimlik uygulamaları bilinmeyen, yönetilmeyen bir hesap altında çalışıyor gibi kabul edilir. Koşullu başlatma UI’si çalışmaz ve uygulamada hiçbir ilke uygulanmaz. Kimliğin değiştirilmesi gerektiğinde bunu SDK’ya bildirmek uygulamanın sorumluluğudur. Genellikle, bu durum uygulamanın belirli bir kullanıcı hesabına ait verileri göstermek üzere olduğu sırada gerçekleşir.

Kullanıcının bir dizüstü bilgisayarda belge, posta kutusu veya bir sekme açmayı denemesi örnek olarak gösterilebilir. Dosya, posta kutusu veya sekme gerçekten açılmadan uygulamanın SDK’ya bildirimde bulunması gerekir. Bu `IntuneMAMPolicyManager` içindeki `setUIPolicyIdentity` API’si üzerinden yapılır. Bu API, kullanıcı yönetilse de yönetilmese de çağrılmalıdır. Kullanıcı yönetiliyorsa, SDK koşullu başlatma denetimleri gerçekleştirir (jailbreak algılama, PIN, kimlik doğrulama vb.). Kimlik değişiminin sonucu, uygulamaya bir tamamlama işleyicisi üzerinden zaman uyumsuz olarak döndürülür. Uygulama, başarılı bir sonuç kodu döndürülene kadar belgeyi, posta kutusunu, sekmeyi vb. açmayı ertelemelidir. Kimlik değişimi başarısız olursa, uygulamanın işlemi iptal etmesi gerekir. 

###SDK tarafından başlatılan kimlik değişimi
SDK’nın uygulamadan belirli bir kimliğe değiştirilmesini istemesini gerektiren durumlar vardır. Çoklu kimlik uygulamalarının bu isteği işlemek için `IntuneMAMPolicyDelegate` içindeki `identitySwitchRequired` yöntemini uygulaması gerekir. Çağrıldığı zaman, uygulama belirli kimliğe değiştirilme isteğini yerine getirebiliyorsa, `IntuneMAMAddIdentityResultSuccess` öğesini tamamlama işleyicisine geçirmesi gerekir. Kimliği değiştirme işlemini yerine getiremiyorsa, uygulamanın `IntuneMAMAddIdentityResultFailed` öğesini tamamlama işleyicisine geçirmesi gerekir. Bu çağrıya yanıt olarak uygulamanın `setUIPolicyIdentity` öğesini çağırması gerekmez. SDK, uygulamanın yönetilmeyen bir kullanıcı hesabıyla değiştirilmesini gerektirirse, boş dize `identitySwitchRequired` çağrısına geçirilir. 
 
###Seçmeli temizleme
Uygulama seçmeli silme ile temizlendiğinde, SDK `IntuneMAMPolicyDelegate` içindeki `wipeDataForAccount` yönetimini çağırır. Belirtilen kullanıcı hesabını ve onunla ilişkili tüm verileri kaldırmak uygulamanın sorumluluğudur. SDK, kullanıcının sahip olduğu tüm dosyaları kaldırma özelliğine sahiptir ve uygulamanın `wipeDataForAccount` çağrısından “FALSE” sonucu getirmesi durumunda bunu uygular. Bu yöntemin bir arka plan iş parçacığından çağrıldığını ve kullanıcının tüm verileri kaldırılana kadar uygulamanın döndürülmeyeceğini aklınızda bulundurun (uygulamanın "FALSE" olarak döndürülmesi durumunda dosyalar hariç olmak üzere).

# Xcode’da Intune Uygulama SDK'sı hatalarını ayıklama

MAM özellikli uygulamanızı Microsoft Intune ile elle sınamadan önce, Xcode’da bir **Settings.bundle** dosyası kullanabilirsiniz. Böylece, Intune bağlantısına gerek olmadan test ilkelerini ayarlayabilirsiniz. Etkinleştirmek için:

* Projenizdeki en üst düzey klasöre sağ tıklayarak bir Settings.bundle dosyası ekleyin. Menüden "Ekle -> Yeni Dosya" seçimini yapın. Eklenecek "Kaynaklar" altında bulunan "Ayarlar Paketi" şablonunu seçin.

* Yalnızca hata ayıklama derlemelerinde, MAMDebugSettings.plist öğesini Settings.bundle dosyasına kopyalayın.

* Root.plist dosyasına (Settings.bundle içinde) "Tür" = Alt Bölme ve "Dosya Adı" = MAMDebugSettings değerine sahip bir tercih ekleyin.

* **Ayarlar -> Uygulamanızın-Adı** altında “Sınama İlkelerini Etkinleştir” seçeneğini açın.

* Uygulamayı başlatın (Xcode içinde veya dışında). 

* **Ayarlar -> Uygulamanızın-Adı -> Sınama İlkelerini Etkinleştir** altında bir ilkeyi açın, ör. "PIN."

* Uygulamayı başlatın (Xcode içinde veya dışında). PIN kodunun beklendiği gibi çalıştığını doğrulayın.

> [!NOTE]
> Ayarları etkinleştirmek ve değiştirmek için artık **Ayarlar -> Uygulamanızın-Adı -> Sınama İlkelerini Etkinleştir** seçeneğini kullanabilirsiniz.

# iOS için Önerilen En İyi Uygulamalar

iOS için geliştirmeye yönelik olarak önerilen en iyi uygulamalardan bazıları aşağıda verilmiştir:

iOS dosya sistemi büyük/küçük harfe duyarlıdır. Dosya adları için büyük/küçük harflerin `libIntuneMAM.a` ve `IntuneMAMResources.bundle` gibi doğru olduğundan emin olun.

Xcode `libIntuneMAM.a`dosyasını bulamıyorsa, bu kitaplığın yolunu bağlayıcı arama yollarına ekleyerek sorunu düzeltebilirsiniz.



##SSS 

 **Uygulamamın tüm kullanıcılarının MAM hizmetine kayıtlı olması gerekiyor mu?**

Hayır.  Aslında, yalnızca iş veya okul hesaplarının Intune uygulama SDK'sına kayıtlı olması gerekir.  Bir hesabın iş veya okul bağlamında kullanıldığını belirlemek uygulamaların sorumluluğudur.   
 
**Uygulamada zaten oturum açmış kullanıcılar ne olacak?  Kayıtlı olmaları gerekli mi?** 

Uygulama, kullanıcıların kimlikleri başarıyla doğrulandıktan sonra kullanıcıları kaydetmekten sorumlu olmakla birlikte, ayrıca, uygulamada MDM bulunmayan MAM işlevi olmadan önce mevcut olabilecek tüm hesapları kaydetmekten de sorumludur.   


Bunu yapmak için uygulamanın `registeredAccounts:` yöntemini kullanması gerekir.  Bu yöntem, Intune MAM hizmetine kayıtlı tüm hesapları içeren bir NSDictionary döndürür.  Uygulamadaki herhangi bir mevcut hesap listede yoksa, uygulama bu hesapları `registerAndEnrollAccount:` aracılığıyla kaydetmelidir. 


 

**SDK, kayıtları ne sıklıkta yeniden dener?** 

SDK daha önce başarısız olan tüm kayıtları otomatik olarak 24 saatte bir yeniden dener.  SDK, bu işlemi bir kullanıcının kuruluşunun kullanıcı uygulamada oturum açtıktan sonra MAM’ı etkinleştirildiğinden emin olmak için yapıyorsa, kullanıcı başarıyla kaydedilir ve ilkeleri alır. 

SDK, bir kullanıcının uygulamayı başarıyla kaydettiğini algıladığında yeniden denemeyi durdurur.  Bunun nedeni, bir uygulamayı herhangi bir zamanda yalnızca 1 kullanıcının kaydedebilmesidir. Kullanıcının kaydı silinirse, yeniden denemeler aynı 24 saatlik zaman aralığında yeniden başlar. 


 
**Kullanıcının kaydının neden kaldırılması gerekir?** 

SDK aşağıdaki eylemleri arka planda düzenli aralıklarla gerçekleştirir:

 - Uygulama henüz kaydedilmemişse, tüm kayıtlı hesapları 24 saatte bir kaydetmeyi dener. 
 - Uygulama kaydedildiyse, SDK her 8 saatte bir MAM ilkesi güncelleştirmelerini denetler. 

Bir kullanıcının kaydını kaldırarak SDK’ya kullanıcının uygulamayı artık kullanmayacağını bildirir ve söz konusu kullanıcı hesabına ait yukarıdaki periyodik olayların tümünü durdurabilir.  Ayrıca bir uygulama kaydı silme işlemi ve gerekirse seçmeli silme işlemi tetikler. 

**Kaydı kaldırma yönteminde doWipe bayrağını true olarak ayarlamalı mıyım?** Bu yöntem, kullanıcının uygulamadaki oturumunu kapatmasından önce çağrılmalıdır.  Oturum kapatma işleminin bir parçası olarak kullanıcı verileri uygulamadan silinirse, `doWipe` false olarak ayarlanabilir.  Ancak, uygulama kullanıcı verilerini gerçekten kaldırmazsa, SDK’nın verileri el ile silebilmesi için bunun true olarak ayarlanması gerekir. 

**Bir uygulama kaydının kaldırılmasının başka yolları var mı?** Evet, BT yöneticisi uygulamaya seçmeli silme komutu gönderebilir; bu durumda kullanıcı kaydı kaldırılır ve kullanıcı verileri silinir.  SDK bu senaryoyu otomatik olarak işler ve kayıt silme temsilci yöntemiyle bir bildirim gönderir. 

#Uygulamanızı App Store’a gönderme
Intune Uygulama SDK’sının hem statik kitaplık hem de çerçeve derlemeleri evrensel ikili dosyalardır; yani tüm cihaz ve benzetici mimarilerine yönelik kodları içerirler. Apple, App Store’a gönderilen uygulamaları benzetici kodu içermeleri durumunda reddeder. Yalnızca cihaz derlemeleri için statik kitaplığa karşı derleme yapıldığında, bağlayıcı, benzetici kodunu otomatik olarak çıkartır.

Uygulamanız Intune Uygulama SDK’sının **çerçeve derlemesini** kullanıyorsa, uygulamanızı App Store’a göndermeden önce evrensel çerçeveden benzetici mimarilerini elle çıkarmanız gerekir. Aşağıdaki yönergeler bunu yapmanıza yardımcı olur:

1. `IntuneMAM.framework` öğesinin Masaüstünüzde olduğundan emin olun.
2. Aşağıdaki komutları çalıştırın:
    
    ```
    lipo ~/Desktop/IntuneMAM.framework/IntuneMAM -remove i386 -remove x86_64 -output ~/Desktop/IntuneMAM.device_only
    ```
    İlk komut, benzetici mimarilerini çerçevenin dylib öğesinden kaldırır.
    ```
    cp ~/Desktop/IntuneMAM.device_only ~/Desktop/IntuneMAM.framework/IntuneMAM 
    ```
    İkinci komut, yalnızca cihaz dylib öğesini çerçeve klasörüne kopyalar.



<!--HONumber=Sep16_HO4-->


