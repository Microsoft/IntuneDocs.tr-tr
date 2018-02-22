---
title: "Android için Microsoft Intune Uygulama SDK’sı geliştirici kılavuzu"
description: "Android için Microsoft Intune Uygulama SDK’sı, Intune mobil uygulama yönetimini (MAM) Android uygulamanıza eklemenizi sağlar."
keywords: SDK
author: erikre
manager: dougeby
ms.author: erikre
ms.date: 01/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3efc522b8b788a0cb6cd1bbc6d04ce7545890de3
ms.sourcegitcommit: 2c7794848777e73d6a9502b4e1000f0b07ac96bc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2018
---
# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a>Android için Microsoft Intune Uygulama SDK’sı geliştirici kılavuzu

> [!NOTE]
> Öncelikle, SDK’nın geçerli özelliklerini kapsayan ve desteklenen her platformda tümleştirmeye nasıl hazırlandığını açıklayan [Intune Uygulama SDK’sına genel bakış](app-sdk.md) bölümünü okumanız önerilir.

Android için Microsoft Intune Uygulama SDK’sı, Intune uygulama koruma ilkelerini (**APP** veya MAM ilkeleri olarak da bilinir) yerel Android uygulamanıza eklemenizi sağlar. Intune ile yönetilen bir uygulama, Intune Uygulama SDK’sı ile tümleşik bir uygulamadır. Intune uygulamayı etkin bir şekilde yönetirken, Intune yöneticileri uygulama koruma ilkelerini Intune ile yönetilen uygulamanıza kolayca dağıtabilir.


## <a name="whats-in-the-sdk"></a>SDK’nın kapsamı

Intune Uygulama SDK’sı aşağıdaki dosyalardan oluşur:  

* **Microsoft.Intune.MAM.SDK.aar**: Support.V4 ve Support.V7 JAR dosyaları dışındaki SDK bileşenleri. Derleme sisteminiz AAR dosyalarını destekliyorsa bu dosya, tek bileşenlerin yerine kullanılabilir.
* **Microsoft.Intune.MAM.SDK.Support.v4.jar**: Android v4 destek kitaplığını kullanan uygulamalarda MAM özelliğini etkinleştirmek için gereken arabirimler. Bu desteğe ihtiyaç duyan uygulamalar JAR dosyasına doğrudan başvurmalıdır.
* **Microsoft.Intune.MAM.SDK.Support.v7.jar**: Android v7 destek kitaplığını kullanan uygulamalarda MAM özelliğini etkinleştirmek için gereken arabirimler. Bu desteğe ihtiyaç duyan uygulamalar JAR dosyasına doğrudan başvurmalıdır.
* **Microsoft.Intune.MDM.SDK.DownlevelStubs.jar**: Bu jar dosyası, yalnızca daha yeni cihazlarda bulunan ama MAMActivity içindeki yöntemlerde başvurulan Android sistem sınıfları için saplamalar içerir. Daha yeni cihazlarda bu saplama sınıfları yoksayılır. Bu jar dosyası yalnızca uygulamanızın MAMActivity'den türetilen sınıflarla yansıtma yaptığı durumlarda gereklidir ve uygulamaların çoğunun bu dosyayı içermesi gerekmez. Bu jar dosyasını kullanırsanız, tüm sınıflarını ProGuard'ın dışında tutmaya dikkat etmelisiniz. Bunlar, "android" kök paketinin altında olacaktır
* **proguard.txt**: ProGuard ile oluşturuluyorsa, uygulanması gereken ProGuard kurallarını içerir.
* **CHANGELOG.txt**: Her SDK sürümünde yapılmış değişikliklerin kaydını sağlar.
* **THIRDPARTYNOTICES.TXT**:  Uygulamanıza derlenecek üçüncü taraf ve/veya OSS kodunu tanıyan bir öznitelik bildirimi.

Oluşturma sisteminiz AAR dosyalarını desteklemiyorsa, Microsoft.Intune.MAM.SDK.aar yerine aşağıdaki dosyaları kullanabilirsiniz.
* **Microsoft.Intune.MAM.SDK.jar**: Intune Şirket Portalı uygulamasında MAM özelliğini ve birlikte çalışabilirliği etkinleştirmek için gereken arabirimler. Uygulamalar bunu bir Android kitaplığı başvurusu olarak belirtmelidir.
* **Kaynak dizini**: SDK’nın bağımlı olduğu kaynaklar (dizeler gibi).
* **AndroidManifest.xml**: Giriş noktaları ve kitaplık gereksinimleri.


## <a name="requirements"></a>Gereksinimler

Intune Uygulama SDK'sı, derlenmiş bir Android projesidir. Sonuç olarak, uygulamanın en düşük veya hedef API sürümleri için kullandığı Android sürümünden büyük ölçüde etkilenmez. SDK; Android API 26 (Android 8.0) üzerinden Android API 19 (Android 4.4+) destekler.


### <a name="company-portal-app"></a>Şirket Portalı uygulaması
Android için Intune Uygulama SDK’sı, uygulama koruma ilkelerini etkinleştirmek için cihazda [Şirket Portalı](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) uygulamasının varlığına bağımlıdır. Şirket Portalı uygulama koruma ilkelerini Intune hizmetinden alır. Uygulama başlatıldığında, ilkeyi ve ilkenin zorlanmasına yönelik kodu Şirket Portalı’dan yükler.

> [!NOTE]
> Cihazda Şirket Portalı uygulaması olmadığında, Intune ile yönetilen bir uygulama Intune uygulama koruma ilkelerini desteklemeyen normal bir uygulama gibi davranır.

Cihaz kaydı olmadan uygulama koruması için kullanıcının Şirket Portalı uygulamasını kullanarak cihazını kaydetmesi gerekli _**değildir**_.

## <a name="sdk-integration"></a>SDK tümleştirmesi

### <a name="build-integration"></a>SDK Tümleştirmesi

Intune Uygulama SDK'sı dış bağımlılıkları olmayan standart bir Android kitaplığıdır. **Microsoft.Intune.MAM.SDK.jar**, hem uygulama koruma ilkesi etkinleştirmesi için gereken arabirimleri hem de Microsoft Intune Şirket Portalı uygulamasıyla birlikte çalışma için gereken kodu içerir.

**Microsoft.Intune.MAM.SDK.jar** bir Android kitaplık başvurusu olarak belirtilmelidir. Bunu yapmak için, uygulama projenizi Android Studio’da açın, **Dosya > Yeni > Yeni modül**’e gidin ve **.JAR/.AAR Paketini İçeri Aktar**’ı seçin. Android arşiv paketimiz Microsoft.Intune.MAM.SDK.aar’ı seçin.

Buna ek olarak, **Microsoft.Intune.MAM.SDK.Support.v4** ve **Microsoft.Intune.MAM.SDK.Support.v7** sırasıyla `android.support.v4` ve `android.support.v7`‘nin Intune çeşitlemelerini içerir. Uygulamanın destek kitaplıklarını eklemek istemediği durumlarda Microsoft.Intune.MAM.SDK.aar’ın içinde yerleşik olarak bulunmaz. Bunlar Android kitaplık projeleri değil standart JAR dosyalarıdır.

#### <a name="proguard"></a>ProGuard

Derleme adımı olarak [ProGuard](http://proguard.sourceforge.net/) (veya başka bir daraltma/gizleme mekanizması) kullanılıyorsa, Intune SDK sınıfları hariç tutulmalıdır. ProGuard için bu, SDK ile dağıtılan proguard.txt dosyasından kurallar ekleyerek gerçekleştirilir.

Azure Active Directory Authentication Library’lerin (ADAL) kendi ProGuard kısıtlamaları olabilir. Uygulamanız ADAL ile tümleştiriliyorsa, bu kısıtlamalarla ilgili olarak ADAL belgelerine bakmalısınız.

### <a name="entry-points"></a>Giriş noktaları

Bu izinler, Azure Active Directory Kimlik Doğrulama Kitaplığı ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) tarafından aracılık edilen kimlik doğrulaması gerçekleştirmek üzere istenir. Bu izinler uygulamaya sağlanmazsa veya kullanıcı tarafından kaldırılırsa, aracı (Şirket Portalı uygulaması) gerektiren kimlik doğrulama akışları devre dışı bırakılır.

Intune Uygulama SDK'sı, Intune uygulama koruma ilkelerini etkinleştirmek için bir uygulamanın kaynak kodunda değişiklik yapılmasını gerektirir. Bu işlem, Android temel sınıflarının, **MAM** olarak adlandırılan eşdeğer Intune temel sınıflarıyla değiştirilmesi yoluyla yapılır. SDK sınıfları, Android temel sınıfı ile uygulamanın söz konusu sınıftan türettiği sürüm arasında çalışır. Örnek olarak bir etkinlik kullanıldığında elde edilen devralma hiyerarşisi şunun gibi görünür: `Activity` > `MAMActivity` > `AppSpecificActivity`.

Örneğin, `AppSpecificActivity` üst öğesi ile etkileşim kurduğunda (örneğin `super.onCreate()` çağırdığında), `MAMActivity` üst sınıftır.

Tipik Android uygulamaları tek bir moda sahiptir ve sisteme [**Context**](https://developer.android.com/reference/android/content/Context.html) nesnesi aracılığıyla erişebilirler. Öte yandan Intune uygulama SDK'sıyla tümleşik uygulamalar çift moda sahiptir. Bu uygulamalar sisteme `Context` nesnesi üzerinden erişmeye devam eder. Kullanılan temel `Activity` baz alınarak, `Context` nesnesi Android tarafından sağlanır veya sistemin sınırlı bir görünümü ve Android tarafından sağlanan `Context` arasında çoğullanır. Bir MAM giriş noktasından türettikten sonra, `Context` kullanmak normalde yaptığınız gibi güvenlidir; örneğin `Activity` sınıflarını başlatıp `PackageManager` kullanmak.


## <a name="replace-classes-methods-and-activities-with-their-mam-equivalent"></a>Sınıfları, yöntemleri ve etkinlikleri MAM eşdeğerleriyle değiştirme

Android temel sınıfları, ilgili MAM eşdeğerleriyle değiştirilmelidir. Bunu yapmak için aşağıdaki tabloda listelenen sınıfların tüm örneklerini bulun ve bunları Intune Uygulama SDK'sındaki eşdeğerleriyle değiştirin. Bunların çoğu uygulama sınıflarınızın devralınacağı sınıflardır, ancak bazıları (örn. MediaPlayer) uygulamanızın türetmede kullanacağı sınıflar olacaktır.

| Android temel sınıf | Intune Uygulama SDK'sı karşılığı |
|--|--|
| android.app.Activity | MAMActivity |
| android.app.ActivityGroup | MAMActivityGroup |
| android.app.AliasActivity | MAMAliasActivity |
| android.app.Application | MAMApplication |
| android.app.DialogFragment | MAMDialogFragment |
| android.app.ExpandableListActivity | MAMExpandableListActivity |
| android.app.Fragment | MAMFragment |
| android.app.IntentService | MAMIntentService |
| android.app.LauncherActivity | MAMLauncherActivity |
| android.app.ListActivity | MAMListActivity |
| android.app.NativeActivity | MAMNativeActivity |
| android.app.PendingIntent | MAMPendingIntent (bkz. [Pending Intent](#pendingintent)) |
| android.app.Service | MAMService |
| android.app.TabActivity | MAMTabActivity |
| android.app.TaskStackBuilder | MAMTaskStackBuilder |
| android.app.backup.BackupAgent | MAMBackupAgent |
| android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
| android.app.backup.FileBackupHelper | MAMFileBackupHelper |
| android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
| android.content.BroadcastReceiver | MAMBroadcastReceiver |
| android.content.ContentProvider | MAMContentProvider |
| android.os.Binder | MAMBinder (Yalnızca Bağlayıcı, Android Arabirimi Tanım Dili (AIDL) arabiriminden oluşturulmadığında gereklidir) |
| android.media.MediaPlayer | MAMMediaPlayer |
| android.media.MediaMetadataRetriever | MAMMediaMetadataRetriever |
| android.provider.DocumentsProvider | MAMDocumentsProvider |
| android.preference.PreferenceActivity | MAMPreferenceActivity |

> [!NOTE]
> Uygulamanıza türetilen kendi `Application` sınıfı gerekmiyor olsa da, [aşağıdaki `MAMApplication` bölümüne bakın](#mamapplication)

### <a name="microsoftintunemamsdksupportv4jar"></a>Microsoft.Intune.MAM.SDK.Support.v4.jar:

| Android Sınıfı Intune MAM | Intune Uygulama SDK'sı karşılığı |
|--|--|
| android.support.v4.app.DialogFragment | MAMDialogFragment
| android.support.v4.app.FragmentActivity | MAMFragmentActivity
| android.support.v4.app.Fragment | MAMFragment
| android.support.v4.app.JobIntentService | MAMJobIntentService
| android.support.v4.app.TaskStackBuilder | MAMTaskStackBuilder
| android.support.v4.content.FileProvider | MAMFileProvider

### <a name="microsoftintunemamsdksupportv7jar"></a>Microsoft.Intune.MAM.SDK.Support.v7.jar:

|Android Sınıfı | Intune Uygulama SDK'sı karşılığı |
|--|--|
|android.support.v7.app.AppCompatActivity | MAMAppCompatActivity |

### <a name="renamed-methods"></a>Yeniden Adlandırılan Yöntemler


Birçok durumda, Android sınıfında kullanılabilir olan bir yöntem, MAM değiştirme sınıfında kesin olarak işaretlenmiştir. Bu durumda, MAM değiştirme sınıfı benzer ada sahip olup (genellikle `MAM` son ekini alır) geçersiz kılmanız gereken bir yöntem sağlar. Örneğin, `MAMActivity`’i geçersiz kılıp `onCreate()` çağırmak yerine `super.onCreate()`’den türetilirken, `Activity`, `onMAMCreate()`’i geçersiz kılmalı ve `super.onMAMCreate()` çağırmalıdır. Java derleyicisi, MAM eşdeğeri yerine özgün metodun yanlışlıkla geçersiz kılınmasını önleyen kesin kısıtlamalar uygulamalıdır.

### <a name="mamapplication"></a>MAMApplication
MAM SDK'sı içindeki kısıtlamalara bağlı olarak, bir `com.microsoft.intune.mam.client.app.MAMApplication` alt sınıfı **oluşturmalı** ve bildiriminizde kullanılan `Application` sınıfının adına ayarlamalısınız. `MAMApplication` soyuttur ve `byte[] getADALSecretKey` için bir geçersiz kılma gerektirir; nasıl uygulanacağı konusunda daha fazla bilgi için lütfen bu işlevle ilgili Javadoc'a bakın.
### <a name="pendingintent"></a>PendingIntent
`PendingIntent.get*` yerine `MAMPendingIntent.get*` yöntemini kullanmanız gerekir. Bundan sonra her zamanki gibi `PendingIntent` sonucunu kullanabilirsiniz.

### <a name="manifest-replacements"></a>Bildirim Değişiklikleri
Hem bildirimde hem de Java kodunda yukarıdaki sınıf değişikliklerinden bazılarını yapmanız gerekebileceğini lütfen unutmayın. Özel not:
* `android.support.v4.content.FileProvider` için olan bildirim başvuruları `com.microsoft.intune.mam.client.support.v4.content.MAMFileProvider` ile değiştirilmelidir.
* Uygulamanızın kendi türetilmiş Uygulama sınıfına ihtiyacı yoksa bildirimde kullanılan Uygulama sınıfı adı olarak `com.microsoft.intune.mam.client.app.MAMApplication` ayarlanmalıdır.

## <a name="sdk-permissions"></a>SDK izinleri

Intune uygulama SDK'sı, tümleştirildiği uygulamalarda üç [Android sistem izni](https://developer.android.com/guide/topics/security/permissions.html) gerektirir:

* `android.permission.GET_ACCOUNTS`  (gerekirse çalışma zamanında istenir)

* `android.permission.MANAGE_ACCOUNTS`

* `android.permission.USE_CREDENTIALS`

Bu izinler, Azure Active Directory Kimlik Doğrulama Kitaplığı ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) tarafından aracılık edilen kimlik doğrulaması gerçekleştirmek üzere istenir. Bu izinler uygulamaya sağlanmazsa veya kullanıcı tarafından kaldırılırsa, aracı (Şirket Portalı uygulaması) gerektiren kimlik doğrulama akışları devre dışı bırakılır.

## <a name="logging"></a>Günlüğe kaydetme

Günlüğe kaydedilen verilerden en iyi şekilde yararlanmak için günlüğün erken başlatılması gerekir. `Application.onMAMCreate()` normalde günlüğü başlatmak için en iyi konumdur.

Uygulamanıza MAM günlüklerini almak için, [Java İşleyicisi](http://docs.oracle.com/javase/7/docs/api/java/util/logging/Handler.html) oluşturun ve bunu `MAMLogHandlerWrapper` konumuna ekleyin. Bu, her günlük iletisi için uygulama işleyicisinde `publish()` çağrısı yapar.

```java
/**
 * Global log handler that enables fine grained PII filtering within MAM logs.  
 *
 * To start using this you should build your own log handler and add it via
 * MAMComponents.get(MAMLogHandlerWrapper.class).addHandler(myHandler, false);  
 *
 * You may also remove the handler entirely via
 * MAMComponents.get(MAMLogHandlerWrapper.class).removeHandler(myHandler);
 */
public interface MAMLogHandlerWrapper {
    /**
     * Add a handler, PII can be toggled.
     *
     * @param handler handler to add.
     * @param wantsPII if PII is desired in the logs.    
     */
    void addHandler(final Handler handler, final boolean wantsPII);

    /**
     * Remove a handler.
     *
     * @param handler handler to remove.
     */
    void removeHandler(final Handler handler);
}
```



## <a name="enable-features-that-require-app-participation"></a>Uygulama katılımı gerektiren özellikleri etkinleştirme

SDK’nın kendi başına uygulayamayacağı çeşitli uygulama koruma ilkeleri vardır. Uygulama bu özellikleri sağlamak için aşağıdaki `AppPolicy` arabiriminde bulabileceğiniz çeşitli API’ler kullanarak davranışını denetleyebilir. Bir `AppPolicy` örneği almak için `MAMPolicyManager.getPolicy` kullanın.

```java
/**
 * External facing application policies.
 */
public interface AppPolicy {

/**
 * Restrict where an app can save personal data.
 * This function is now deprecated. Please use getIsSaveToLocationAllowed(SaveLocation, String) instead
 * @return True if the app is allowed to save to personal data stores; false otherwise.
 */
@Deprecated
boolean getIsSaveToPersonalAllowed();

/**
 * Check if policy prohibits saving to a content provider location.
 *
 * @param location
 *            a content URI to check
 * @return True if location is not a content URI or if policy does not prohibit saving to the content location.
 */
boolean getIsSaveToLocationAllowed(Uri location);

/**
 * Determines if the SaveLocation passed in can be saved to by the username associated with the cloud service.
 *
 * @param service
 *           see {@link SaveLocation}.
 * @param username
 *           the username/email associated with the cloud service being saved to. Use null if a mapping between
 *           the AAD username and the cloud service username does not exist or the username is not known.
 * @return true if the location can be saved to by the identity, false if otherwise.
 */
boolean getIsSaveToLocationAllowed(SaveLocation service, String username);

/**
 * Whether the SDK PIN prompt is enabled for the app.
 *
 * @return True if the PIN is enabled. False otherwise.
 */
boolean getIsPinRequired();

/**
 * Whether the Intune Managed Browser is required to open web links.
 * @return True if the Managed Browser is required, false otherwise
 */
boolean getIsManagedBrowserRequired();

/**
 * Check if policy allows Contact sync to local contact list.
 *
 * @return True if Contact sync is allowed to save to local contact list; false otherwise.
 */
boolean getIsContactSyncAllowed();

/**
 * This method is intended for diagnostic/telemetry purposes only. It can be used to discover whether
 * file encryption is in use. File encryption is transparent to the app, and the app should not need
 * to make any business logic decisions based on this.
 * 
 * @return True if file encryption is in use.
 */
boolean diagnosticIsFileEncryptionInUse();

/**
 * Return the policy in string format to the app.
 *  
 * @return The string representing the policy.
 */
String toString();

}

```

> [!NOTE]
> Cihaz veya uygulama bir Intune yönetim ilkesi altında olmasa bile `MAMPolicyManager.getPolicy` her zaman null olmayan bir Uygulama İlkesi döndürür.

### <a name="example-determine-if-pin-is-required-for-the-app"></a>Örnek: Uygulama için PIN’in gerekli olup olmadığını belirleme

Uygulamanın kendi PIN kullanıcı deneyimi varsa, BT yöneticisi SDK’yı uygulama PIN’ini isteyecek şekilde yapılandırdıysa, uygulamanın deneyimini devre dışı bırakmak isteyebilirsiniz. BT yöneticisinin bu uygulamada uygulama PIN ilkesini dağıtıp dağıtmadığını belirlemek için, geçerli son kullanıcı için aşağıdaki yöntemi çağırın:

```java

MAMPolicyManager.getPolicy(currentActivity).getIsPinRequired();
```

### <a name="example-determine-the-primary-intune-user"></a>Örnek: Birincil Intune kullanıcısını belirleme

AppPolicy’de gösterilen API’lere ek olarak, `MAMUserInfo` arabirimi içinde tanımlanan `getPrimaryUser()` API’si tarafından kullanıcı asıl adı (**UPN**) da gösterilir. UPN’yi almak için aşağıdaki çağrıyı yapın:

```java
MAMUserInfo info = MAMComponents.get(MAMUserInfo.class);
if (info != null) return info.getPrimaryUser();
```

MAMUserInfo arabiriminin tam tanımı şöyledir:

```java
/**
 * External facing user informations.
 *
 */
public interface MAMUserInfo {
       /**
        * Get the primary user name.
        *
        * @return the primary user name or null if the device is not enrolled.
        */
       String getPrimaryUser();
}
```

### <a name="example-determine-if-saving-to-device-or-cloud-storage-is-permitted"></a>Örnek: Cihaz veya bulut depolamasını kaydetmeye izin verilip verilmediğini belirleme

Birçok uygulama, son kullanıcının dosyaları yerel olarak veya bir bulut depolama hizmetine kaydetmesine olanak tanıyan özellikler uygular. Intune Uygulama SDK’sı, BT yöneticilerinin kuruluşlarında uygun gördüğü durumlarda ilke kısıtlamaları uygulayarak veri sızıntısına karşı koruma sağlamasına olanak tanır.  BT’nin denetleyebileceği ilkelerden biri, son kullanıcının “kişisel” ve yönetilmeyen bir veri deposuna kayıt yapıp yapamayacağıdır. Buna yerel konuma, SD karta veya üçüncü taraf yedekleme hizmetlerine kaydetme dahildir.

**Özelliği etkinleştirmek için uygulama katılımı gereklidir.** Uygulamanız kişisel konumlara veya bulut konumlarına doğrudan uygulama üzerinden kaydetmeye izin veriyorsa, BT yöneticisinin bir konuma kaydetmeye izin verilip verilmediğini denetleyebildiğinden emin olmak için bu özelliği uygulamanız gerekir. Aşağıdaki API, uygulamanın, geçerli Intune yönetici ilkesi tarafından kişisel bir depolama alanına kaydetmeye izin verilip verilmediğini bilmesini sağlar. Uygulama, son kullanıcının uygulama üzerinden kullanabildiği kişisel veri depolama alanını bildiği için bundan sonra ilkeyi uygulayabilir.  

İlkenin zorunlu tutulup tutulmadığını belirlemek için aşağıdaki çağrıyı yapın:

```java
MAMPolicyManager.getPolicy(currentActivity).getIsSaveToLocationAllowed(
SaveLocation service, String username);
``````

... burada `service`, aşağıdaki SaveLocation değerlerinden biridir:


    * SaveLocation.ONEDRIVE_İŞ
    * SaveLocation.YEREL
    * SaveLocation.SHAREPOINT

Kullanıcının ilkesinin çeşitli konumlara veri kaydetmesine izin verip vermediğini belirlemeye yönelik önceki yöntem, aynı **AppPolicy** sınıfındaki `getIsSaveToPersonalAllowed()` yöntemiydi. Bu işlev artık **kullanım dışı bırakılmıştır** ve kullanılmamalıdır; aşağıdaki çağrı `getIsSaveToPersonalAllowed()` ile eşdeğerdir:

```java

MAMPolicyManager.getPolicy(currentActivity).getIsSaveToLocationAllowed(SaveLocation.LOCAL, userNameInQuestion);
```

>[!NOTE]
> Söz konusu konum **SaveLocations** sabit listesinde yer almıyorsa, `SaveLocation.OTHER` kullanın.


## <a name="register-for-notifications-from-the-sdk"></a>SDK’dan gelen bildirimlere kaydolma

### <a name="overview"></a>Genel bakış
Intune Uygulama SDK’sı uygulamanıza seçmeli silme gibi bazı ilkelerin (bu ilkeler BT yöneticisi tarafından dağıtıldığında) davranışını denetleme izni verir. BT yöneticisi böyle bir ilke dağıttığında, Intune hizmeti SDK’ya bir bildirim gönderir.

Uygulamanızın `MAMNotificationReceiver` oluşturup `MAMNotificationReceiverRegistry` ile kaydederek SDK’dan gelen bildirimlere kaydolması gerekir. Bu işlem, aşağıdaki örnekte gösterildiği gibi alıcı ve `App.onCreate` öğesinde istenen bildirim türü belirtilerek yapılır:

```java
@Override
public void onCreate() {
  super.onCreate();
  MAMComponents.get(MAMNotificationReceiverRegistry.class)
    .registerReceiver(
      new ToastNotificationReceiver(),
      MAMNotificationType.WIPE_USER_DATA);
  }
``````

### <a name="mamnotificationreceiver"></a>MAMNotificationReceiver

`MAMNotificationReceiver` arabirimi yalnızca Intune hizmetinden bildirimleri alır. Bazı bildirimler doğrudan SDK tarafından işlenirken, bazıları uygulamanın katılımını gerektirir. Bir uygulamanın, bildirimden true veya false değeri döndürmesi **gerekir**. Bildirim sonucunda uygulamayı denediği bazı eylemler başarısız olmadığı sürece, uygulama her zaman true değerini döndürmelidir.

* Bu hata Intune hizmetine bildirilebilir. BT yöneticisi bir silme işlemi başlattıktan sonra uygulamanın kullanıcı verilerini silmekte başarısız olması rapor edilecek bir senaryoya örnek olarak verilebilir.

>[!NOTE]
> `MAMNotificationReceiver.onReceive` öğesinin engellenmesi güvenlidir; çünkü geri çağırma işlemi, kullanıcı arabirimi iş parçacığı üzerinde çalışmamaktadır.

SDK’da tanımlandığı gibi `MAMNotificationReceiver` arabirimi aşağıya eklenmiştir:

```java
/**
 * The SDK is signaling that a MAM event has occurred.
 *
 */
public interface MAMNotificationReceiver {

    /**
     * A notification was received.
     *
     * @param notification
     *            The notification that was received.
     * @return The receiver should return true if it handled the
     *   notification without error (or if it decided to ignore the
     *   notification). If the receiver tried to take some action in
     *   response to the notification but failed to complete that
     *   action it should return false.
     */
    boolean onReceive(MAMNotification notification);
}

```

### <a name="types-of-notifications"></a>Bildirim türleri

Aşağıdaki bildirimler uygulamaya gönderilir ve bazıları uygulama katılımını gerektirebilir:

* **WIPE_USER_DATA**: Bu bildirim bir `MAMUserNotification` sınıfında gönderilir. Bu bildirim alındığında uygulamanın, `MAMUserNotification` ile geçirilen “kurumsal” kimliğiyle ilişkili tüm verileri silmesi beklenir. Bu bildirim şu anda, APP-WE hizmeti kaydını silme sırasında gönderilmektedir. Kullanıcının birincil adı, genellikle kayıt işlemi sırasında belirtilir. Bu bildirime kaydolursanız, uygulamanız tüm kullanıcı verilerinin silindiğinden emin olmalıdır. Kaydolmazsanız, varsayılan seçici silme davranışı gerçekleştirilir.

* **WIPE_USER_AUXILIARY_DATA**: Uygulamalar Intune Uygulama SDK’sının varsayılan seçmeli silme davranışını gerçekleştirmesini ve diğer yandan silme gerçekleştirildiğinde bazı yardımcı verilerin kaldırılmasını isterse bu bildirime kaydolabilir.

* **REFRESH_POLICY**: Bu bildirim bir `MAMUserNotification` içinde gönderilir. Bu bildirim alındığında, önbelleğe alınan herhangi bir Intune ilkesinin geçersiz kılınması ve güncelleştirilmesi gerekir. Bu işlem genellikle SDK tarafından yapılır, ancak ilke kalıcı olarak kullanılıyorsa, uygulama tarafından yapılması gerekir.

* **MANAGEMENT_REMOVED**: Bu bildirim `MAMUserNotification` içinde gönderilir ve uygulamaya, yönetilmeyen bir uygulamaya dönüşmek üzere olduğunu bildirir. Yönetilmeyen duruma gelince, artık şifreli dosyaları okuyamayacak, MAMDataProtectionManager ile şifrelenmiş verileri okuyamayacak, şifrelenmiş panoyla etkileşim kuramayacak veya başka bir şekilde yönetilen uygulama ekosistemine katılamayacaktır.


> [!NOTE]
> Bir uygulamanın hiçbir zaman hem `WIPE_USER_DATA` hem de `WIPE_USER_AUXILIARY_DATA` bildirimleri için kaydı olmamalıdır.


## <a name="configure-azure-active-directory-authentication-library-adal"></a>Azure Active Directory Kimlik Doğrulama Kitaplığı'nı (ADAL) Yapılandırma

İlk olarak, lütfen [GitHub’da ADAL deposu](https://github.com/AzureAD/azure-activedirectory-library-for-android) konusunda bulunan ADAL tümleştirme yönergelerini okuyun.

SDK; [kimlik doğrulaması](https://azure.microsoft.com/documentation/articles/active-directory-authentication-scenarios/) ve koşullu başlatma senaryolarında, uygulamaların [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/) ile yapılandırılmasını gerektiren [ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/) özelliğini kullanır. Yapılandırma değerleri, AndroidManifest meta verileri üzerinden SDK’ya iletilir.

Uygulamanızı yapılandırmak ve uygun kimlik doğrulamasını sağlamak için AndroidManifest.xml içindeki uygulama düğümüne aşağıdakileri ekleyin. Bu yapılandırmalardan bazıları, yalnızca uygulamanız genel olarak kimlik doğrulaması için ADAL kullanıyorsa gereklidir; bu durumda, uygulamanızın kendisini AAD’ye kaydetmek için kullandığı değerleri kullanmanız gerekir. Bu işlem, AAD’nin iki ayrı kayıt değerini (biri uygulamadan, biri SDK’dan) tanıması nedeniyle son kullanıcıdan kimlik doğrulamasının iki kez istenmesini önlemek amacıyla yapılır.

```xml
<meta-data
    android:name="com.microsoft.intune.mam.aad.Authority"
    android:value="https://AAD authority/" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.ClientID"
    android:value="your-client-ID-GUID" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.NonBrokerRedirectURI"
    android:value="your-redirect-URI" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.SkipBroker"
    android:value="[true | false]" />
```

### <a name="adal-metadata"></a>ADAL meta verileri

* **Authority**, kullanımdaki geçerli AAD yetkilisidir. Varsa, AAD hesaplarının yapılandırıldığı ortamınızı kullanmanız gerekir. Bu değer yoksa, Intune varsayılanı kullanılır.

* **ClientID**, kullanılacak AAD İstemci Kimliğidir. Azure AD’ye kaydedildiyse, kendi uygulamanızın ClientID değerini kullanmalısınız. Bu değer yoksa, Intune varsayılanı kullanılır.

* **NonBrokerRedirectURI**, aracısız durumlarda kullanılacak AAD yeniden yönlendirme URI’sidir. Hiçbiri belirtilmemişse, varsayılan `urn:ietf:wg:oauth:2.0:oob` değeri kullanılır. Bu varsayılan değer, çoğu uygulamaya uygundur.

* **SkipBroker**, ClientID’nin aracı yeniden yönlendirme URI’sini kullanacak şekilde yapılandırılmadığı durumlarda kullanılır. Varsayılan değer "false" değeridir.
    * **ADAL’ı tümleştirmeyen** ve **cihaz genelinde aracılı kimlik doğrulaması/SSO’ya katılmak istemeyen** uygulamalar için, bu değer "true" olarak ayarlanmalıdır. Bu değer "true" olduğunda, kullanılacak olan tek yeniden yönlendirme URI’si NonBrokerRedirectURI’dir.

    * Cihaz genelinde SSO aracılığını destekleyen uygulamalar için, bu değer "false" olmalıdır. Değer "false" olduğunda SDK, sistemde aracı kullanılabilirliği temelinde [`com.microsoft.aad.adal.AuthenticationContext.getRedirectUriForBroker()`](https://github.com/AzureAD/azure-activedirectory-library-for-android) ile NonBrokerRedirectURI arasında bir aracı seçer. Genel olarak, aracı Şirket Portalı uygulamasından veya Azure Authenticator uygulamasından sağlanır.

### <a name="common-adal-configurations"></a>Yaygın ADAL yapılandırmaları

Aşağıda, uygulamanın ADAL ile yapılandırılabilmesinin yaygın yolları açıklanmıştır. Uygulamanızın yapılandırmasını bulun ve ADAL meta veri parametrelerini (yukarıda açıklanan parametreler) gerekli değerlere ayarladığınızdan emin olun.

1. **Uygulama ADAL ile tümleştirilmezse:**

    | Gerekli ADAL parametresi | Değer |
    |--|--|
    | Yetkili | AAD hesaplarının yapılandırıldığı, tercih edilen ortam |
    | SkipBroker | True |

2. **Uygulama ADAL ile tümleştirilirse:**

    |Gerekli ADAL parametresi| Değer |
    |--|--|
    | Yetkili | AAD hesaplarının yapılandırıldığı, tercih edilen ortam |
    | İstemci Kimliği | Uygulamanın İstemci Kimliği (uygulama kaydedilirken Azure AD tarafından oluşturulur) |
    | NonBrokerRedirectURI | Uygulama için geçerli bir yeniden yönlendirme URI’si veya varsayılan olarak `urn:ietf:wg:oauth:2.0:oob`. <br><br> Değeri, uygulamanızın İstemci Kimliği için kabul edilebilir bir yeniden yönlendirme URI’si olarak yapılandırdığınızdan emin olun.
    | SkipBroker | False |


3. **Uygulama ADAL’ı tümleştirir ama aracılı kimlik doğrulaması/cihaz genelinde SSO’yu desteklemek:**

    |Gerekli ADAL parametresi| Değer |
    |--|--|
    | Yetkili | AAD hesaplarının yapılandırıldığı, tercih edilen ortam |
    | İstemci Kimliği | Uygulamanın İstemci Kimliği (uygulama kaydedilirken Azure AD tarafından oluşturulur) |
    | NonBrokerRedirectURI | Uygulama için geçerli bir yeniden yönlendirme URI’si veya varsayılan olarak `urn:ietf:wg:oauth:2.0:oob`. <br><br> Değeri, uygulamanızın İstemci Kimliği için kabul edilebilir bir yeniden yönlendirme URI’si olarak yapılandırdığınızdan emin olun.
    | SkipBroker | **True** |

## <a name="app-protection-policy-without-device-enrollment"></a>Cihaz kaydı olmadan uygulama koruma ilkesi

### <a name="overview"></a>Genel bakış
Cihaz kaydı olmadan Intune uygulama koruma ilkesi (APP-WE veya MAM-WE olarak da bilinir), uygulamaların Intune MDM’ye kaydedilmeden Intune tarafından yönetilmesine izin verir. APP-WE, hem cihaz kaydıyla hem de cihaz kaydı olmadan çalışır. Şirket Portalı’nın yine cihaza yüklenmiş olması gerekir, ancak kullanıcının Şirket Portalı’nda oturum açması ve cihazı kaydetmesi gerekmez.

> [!NOTE]
> Tüm uygulamaların cihaz kaydı olmadan uygulama koruma ilkesini desteklemesi gerekir.

### <a name="workflow"></a>İş Akışı

Uygulama yeni bir kullanıcı hesabı oluşturduğunda, hesabı Intune Uygulama SDK’sıyla yönetim için kaydetmelidir. Uygulamayı APP-WE hizmetine kaydetme işleminin ayrıntılarını SDK gerçekleştirir; hatalar olması durumunda gerekirse tüm kayıtları uygun aralıklarla yeniden dener.

Uygulama ayrıca, kayıtlı bir kullanıcının durumunu Intune Uygulama SDK’sında sorgulayıp kullanıcının şirket içeriğine erişimini engellemenin gerekip gerekmediğini de saptayabilir. Yönetim için birden çok hesap kaydedilebilir, ancak şu anda APP-WE hizmetiyle bir kerede tek bir hesap etkin olarak kaydedilebilmektedir. Bu da, bir kerede tek bir hesabın uygulama koruma ilkesini alabildiği anlamına gelir.

Uygulamanın, SDK adına Azure Active Directory Authentication Library’den (ADAL) uygun erişim belirtecini almak için bir geri çağırma sağlaması gerekir. Uygulamanın kimlik doğrulaması yapmak ve kendi erişim belirteçlerini almak için zaten ADAL kullandığı varsayılır.

Uygulama bir hesabı tamamen kaldırdığında, uygulamanın söz konusu kullanıcı için artık ilke uygulamayacağını belirtmek üzere o hesabın kaydını kaldırmalıdır. Kullanıcı MAM hizmetine kaydedilmişse, kullanıcının kaydı kaldırılır ve uygulama temizlenir.


### <a name="overview-of-app-requirements"></a>Uygulama gereksinimlerine genel bakış

APP-WE tümleştirmesini gerçekleştirmek için, uygulamanız kullanıcı hesabını MAM SDK ile kaydetmelidir:

1. Uygulamanın, bir `MAMServiceAuthenticationCallback` arabirimi örneğini gerçekleştirmesi ve kaydetmesi _gerekir_. Geri çağırma örneği, uygulamanın yaşam döngüsünde mümkün olduğunca erken bir aşamada kaydedilmelidir (normalde uygulama sınıfının `onMAMCreate()` yönteminde).

2. Kullanıcı hesabı oluşturulduğunda ve kullanıcı başarıyla ADAL oturumu açtığında, uygulama `registerAccountForMAM()` çağrısı _yapmalıdır_.

3. Kullanıcı hesabı tamamen kaldırıldığında, uygulamanın hesabı Intune yönetiminden kaldırmak için `unregisterAccountForMAM()` çağrısı yapması gerekir.

    > [!NOTE]
    > Kullanıcı uygulama oturumunu geçici olarak kapattıysa, uygulamanın `unregisterAccountForMAM()` çağrısı yapması gerekmez. Çağrı, kullanıcıdan şirket verilerini tümüyle kaldırmak için bir temizleme başlatabilir.


### <a name="mamenrollmentmanager"></a>MAMEnrollmentManager

Tüm gerekli kimlik doğrulama ve kayıt API’leri `MAMEnrollmentManager` arabiriminde bulunabilir. Bir `MAMEnrollmentManager` başvurusu şu şekilde alınabilir:

```java
MAMEnrollmentManager mgr = MAMComponents.get(MAMEnrollmentManager.class);

// make use of mgr

```

Döndürülen `MAMEnrollmentManager` örneğinin null olmaması garanti edilir. API yöntemleri iki kategoriye ayrılır: **kimlik doğrulaması** ve **hesap kaydı**.

> [!NOTE]
> `MAMEnrollmentManager`, yakında kullanım dışı bırakılacak bazı API yöntemleri içerir. Netlik sağlamak açısından, aşağıdaki kod bloğunda yalnızca ilgili yöntemler ve sonuç kodları gösterilir.

```java
package com.microsoft.intune.mam.policy;

public interface MAMEnrollmentManager {
    public enum Result {
        AUTHORIZATION_NEEDED,
        NOT_LICENSED,
        ENROLLMENT_SUCCEEDED,
        ENROLLMENT_FAILED,
        WRONG_USER,
        MDM_ENROLLED,
        UNENROLLMENT_SUCCEEDED,
        UNENROLLMENT_FAILED,
        PENDING,
        COMPANY_PORTAL_REQUIRED;
    }

    //Authentication methods
    interface MAMServiceAuthenticationCallback {
        String acquireToken(String upn, String aadId, String resourceId);
    }
    void registerAuthenticationCallback(MAMServiceAuthenticationCallback callback);
    void updateToken(String upn, String aadId, String resourceId, String token);

    //Registration methods
    void registerAccountForMAM(String upn, String aadId, String tenantId);
    void unregisterAccountForMAM(String upn);
    Result getRegisteredAccountStatus(String upn);
}
```

### <a name="account-authentication"></a>Hesap kimlik doğrulaması

Bu bölümde, `MAMEnrollmentManager` içindeki kimlik doğrulama API yöntemleri ve bunların nasıl kullanıldığı açıklanır.

```java
interface MAMServiceAuthenticationCallback {
        String acquireToken(String upn, String aadId, String resourceId);
}
void registerAuthenticationCallback(MAMServiceAuthenticationCallback callback);
void updateToken(String upn, String aadId, String resourceId, String token);
```

1. SDK’nın verili kullanıcı ve kaynak kimliği için ADAL isteğinde bulunmasına olanak tanımak üzere uygulama `MAMServiceAuthenticationCallback` gerçekleştirmelidir. `registerAuthenticationCallback()` yöntemi çağrılarak `MAMEnrollmentManager` için geri çağırma örneği sağlanmalıdır. Kayıt yeniden denemeleri ve uygulama koruma ilkesi yenileme iadeleri için uygulama yaşam döngüsünün çok erken bir aşamasında belirteç gerekebilir; dolayısıyla geri çağırma kaydı için ideal konum, uygulamanın `MAMApplication` alt sınıfının `onMAMCreate()` yöntemidir.

2. `acquireToken()` yöntemi, verili kullanıcının istenen kaynak kimliği için erişim belirtecini almalıdır. İstenen belirteci almazsa, null değeri döndürmelidir.

3. SDK `acquireToken()` çağrısı yaptığında uygulamanın belirteci sağlayamaması durumunda (örneğin, sessiz kimlik doğrulaması başarısız olursa ve UI göstermek için uygun bir zaman değilse), uygulama daha sonraki bir aşamada `updateToken()` yöntemini çağırarak belirteci sağlayabilir. `updateToken()` çağrısına, önceki `acquireToken()` çağrısında istenen aynı UPN, AAD ID ve kaynak kimliğinin yanı sıra sonunda alınan belirteç de geçirilmelidir. Uygulamanın, sağlanan geri çağırmadan null döndürüldükten sonra, mümkün olan en kısa sürede bu yöntemi çağırması gerekir.

> [!NOTE]
> SDK, belirteci almak için düzenli aralıklarla `acquireToken()` yöntemini çağırır; dolayısıyla `updateToken()` çağrısı yapmak kesin olarak gerekli değildir. Bununla birlikte, bu çağrının yapılması önerilir çünkü kayıtların ve uygulama koruma ilkesi iadelerinin zamanında tamamlanmasına yardımcı olabilir.


### <a name="account-registration"></a>Hesap kaydı

Bu bölümde, `MAMEnrollmentManager` içindeki hesap kaydı API yöntemleri ve bunların nasıl kullanıldığı açıklanır.

```java
void registerAccountForMAM(String upn, String aadId, String tenantId);
void unregisterAccountForMAM(String upn);
Result getRegisteredAccountStatus(String upn);
```

1. Hesabı yönetime kaydetmek için, uygulamanın `registerAccountForMAM()` yöntemini çağırması gerekir. Kullanıcı hesabı hem UPN değeriyle hem de AAD kullanıcı kimliğiyle tanımlanır. Kayıt verilerini kullanıcının AAD kiracısıyla ilişkilendirmek için kiracı kimliği de gereklidir. SDK, verili kullanıcı için MAM hizmetinde uygulamayı kaydetme girişiminde bulunabilir; kayıt başarısız olursa, hesabın kaydı kaldırılana kadar kaydetme işlemini düzenli aralıklarla yeniden dener. Yeniden denemeler normalde 12-24 saatte bir yapılır. SDK, bildirimler yoluyla kayıt girişimlerinin durumunu zaman uyumsuz olarak sağlar.

2. AAD kimlik doğrulaması gerekli olduğundan, kullanıcı hesabını kaydetmek için en uygun zaman, kullanıcının uygulamada oturum açmasından ve ADAL kullanarak başarıyla kimliğini doğrulamasından sonraki bir zamandır.
    * Kullanıcının AAD kimliği ve kiracı kimliği, ADAL kimlik doğrulama çağrısından [`AuthenticationResult`](https://github.com/AzureAD/azure-activedirectory-library-for-android) nesnesinin bir parçası olarak döndürülür. Kiracı kimliği `AuthenticationResult.getTenantID()` yönteminden gelir.
    * Kullanıcı hakkındaki bilgiler `AuthenticationResult.getUserInfo()` çağrısından gelen `UserInfo` türündeki bir alt nesnede bulunur ve AAD kullanıcı kimliği `UserInfo.getUserId()` çağrısı yapılarak o nesneden alınır.

3. Intune yönetiminden bir hesabın kaydını kaldırmak için, uygulamanın `unregisterAccountForMAM()` yöntemini çağırması gerekir. Hesap başarıyla kaydedilmiş ve yönetilmişse, SDK hesabın kaydını kaldırır ve verilerini temizler. Hesap için düzenli aralıklarla yapılan kayıt yeniden denemeleri durdurulur. SDK, bildirimler yoluyla kayıt kaldırma isteğinin durumunu zaman uyumsuz olarak sağlar.

### <a name="important-implementation-notes"></a>Önemli uygulama notları

#### <a name="authentication"></a>Kimlik doğrulama

* Uygulama `registerAccountForMAM()` çağrısı yaptığında, bundan kısa süre sonra farklı bir iş parçacığında `MAMServiceAuthenticationCallback` arabiriminde bir geri çağırma alabilir. İdeal olan, **MAMService belirtecini** alma sürecini hızlandırmak için uygulamanın hesabı kaydetmeden önce ADAL’dan kendi belirtecini almasıdır. Uygulama geri çağırmadan geçerli bir belirteç döndürürse, kayıt işlemine devam edilir ve uygulama bir bildirim yoluyla nihai sonucu alır.

* Uygulama geçerli bir AAD belirteci döndürmezse, kayıt girişiminin nihai sonucu `AUTHENTICATION_NEEDED` olur. Uygulama bildirim yoluyla bu Sonucu alırsa, **MAMService belirtecini** alarak ve kayıt sürecini yeniden başlatmak için `updateToken()` yöntemini çağırarak kayıt sürecini hızlandırabilir. Ama SDK kaydı düzenli aralıklarla yeniden denediğinden ve belirteci almak için geri çağrı yaptığından, bu kesin bir gereklilik _değildir_.

* Düzenli aralıklarla yapılan uygulama koruma ilkesi yenileme iadeleri için belirteci almak üzere uygulamanın kayıtlı `MAMServiceAuthenticationCallback` yöntemi de çağrılır. İstendiğinde uygulama belirteci sağlayamazsa bildirim almaz, ama iade sürecini hızlandırmak için bir sonraki uygun zamanda belirteci almayı ve `updateToken()` yöntemini çağırmayı denemelidir. Belirteç sağlanmazsa, geri çağırma bir sonraki iade girişiminde yine de çağrılır.

#### <a name="registration"></a>Kayıt

* Size kolaylık sağlamak açısından, kayıt yöntemleri eşgüçlüdür; örneğin, `registerAccountForMAM()` yöntemi yalnızca bir hesabı kaydeder ve hesap henüz kaydedilmediyse uygulama kaydı yapmayı dener ve `unregisterAccountForMAM()` yöntemi de şu anda kaydedilmiş durumdaysa hesabın kaydını kaldırır. Birbirini izleyen çağrılar çalışmaz; dolayısıyla bu yöntemlerin birden çok kez çağrılmasının bir zararı olmaz. Buna ek olarak, bu yöntemlere yapılan çağrılar arasındaki iletişim ve sonuç bildirimleri garanti edilmez: şöyle ki, zaten kayıtlı olan bir kimlik için `registerAccountForMAM` çağrılırsa, söz konusu kimlik için yeniden bildirim gönderilmeyebilir. SDK arka planda kayıtları düzenli aralıklarla deneyebildiğinden ve Intune hizmetinden alınan silme isteklerinin tetiklediği kayıt kaldırma işlemleri olabildiğinden, bu yöntemlere yapılan çağrılardan hiçbirine karşılık gelmeyen bildirimlerin gönderilmesi de mümkündür.

* Kayıt yöntemleri istenen sayıda farklı kimlik için çağrılabilir, ama şu anda yalnızca bir kullanıcı hesabı başarılı bir şekilde kaydedilebilir. Intune lisansı olan ve uygulama koruma ilkesi tarafından hedeflenen birden çok kullanıcı hesabı aynı anda veya birbirine çok yakın zamanda kaydedilirse, yarışı hangisinin kazanacağı konusunda bir garanti verilemez.

* Son olarak, belirli bir hesabın kaydedilip kaydedilmediğini görmek ve geçerli durumunu almak için `getRegisteredAccountStatus` yöntemini kullanarak `MAMEnrollmentManager`‘ı sorgulayabilirsiniz. Sağlanan hesap kaydedilmediyse, bu yöntem **null** döndürür. Hesap kayıtlıysa, bu yöntem `MAMEnrollmentManager.Result` sabit listesinin üyelerinden biri olarak hesabın durumunu döndürür.

### <a name="result-and-status-codes"></a>Sonuç ve durum kodları

Hesap ilk kez kaydedildiğinde, `PENDING` durumunda başlar. Bu, ilk MAM hizmeti kayıt girişiminin tamamlanmadığı anlamına gelir. Kayıt girişimi tamamlandığında, aşağıdaki tabloda yer alan Dönüş kodlarından biriyle bir bildirim gönderilir. Buna ek olarak, `getRegisteredAccountStatus()` yöntemi hesabın durumunu döndürür ve böylelikle uygulama, söz konusu kullanıcı için kurumsal içeriğe erişimin engellenip engellenmediğini her zaman saptayabilir. Kayıt girişimi başarısız olursa, SDK arka planda kaydı yeniden denediğinden hesabın durumu zaman içinde değişebilir.

|Sonuç kodu | Açıklama |
| -- | -- |
|AUTHORIZATION_NEEDED | Bu sonuç, uygulamanın kayıtlı `MAMServiceAuthenticationCallback` örneği tarafından belirteç sağlanmadığını veya sağlanan belirtecin geçersiz olduğunu gösterir.  Uygulama mümkünse geçerli bir belirteç almalı ve `updateToken()` yöntemini çağırmalıdır. |
| NOT_LICENSED | Kullanıcı Intune’da lisanslı değildir veya Intune MAM hizmetiyle iletişim kurma girişimi başarısız olmuştur.  Uygulamanın yönetilmeyen (normal) durumda çalışmaya devam etmesi ve kullanıcının engellenmemesi gerekir.  Kullanıcının gelecekte lisanslı duruma gelme olasılığına karşı, kayıt işlemleri düzenli aralıklarla yeniden denenecektir. |
| ENROLLMENT_SUCCEEDED | Kayıt girişimi başarılı olmuştur ve kullanıcı kaydedilmiştir.  Başarılı bir kayıt söz konusu olduğunda, bu bildirimden önce ilke yenileme bildirimi gönderilir.  Kurumsal verilere erişim izni verilmelidir. |
| ENROLLMENT_FAILED | Kayıt girişimi başarısız olmuştur.  Diğer ayrıntılar, cihaz günlüklerinde bulunabilir.  Uygulama bu durumda şirkete erişim izni vermemelidir, çünkü daha önce kullanıcının Intune’da lisanslı olduğu saptanmıştır.|
| WRONG_USER | Cihaz başına yalnızca bir kullanıcı MAM hizmetiyle uygulamayı kaydedebilir.  Başka bir kullanıcı olarak başarıyla kaydetmek için, önce tüm kayıtlı uygulamaların kaydı kaldırılmalıdır.  Aksi takdirde, bu uygulamanın birincil kullanıcı olarak kaydedilmesi gerekir.  Bu denetim lisans denetiminden sonra yapıldığından, uygulama başarıyla kaydedilene kadar kullanıcının kurumsal verilere erişimi engellenmelidir.|
| UNENROLLMENT_SUCCEEDED | Kaydın kaldırılması başarılı olmuştur.|
| UNENROLLMENT_FAILED | Kayıt kaldırma isteği başarısız olmuştur.  Diğer ayrıntılar, cihaz günlüklerinde bulunabilir. |
| PENDING | Kullanıcı için ilk kayıt denemesi devam etmektedir.  Kayıt sonucu bilinir duruma gelene kadar uygulama kurumsal verilere erişimi engelleyebilir ama bunu yapması zorunlu değildir. |
| COMPANY_PORTAL_REQUIRED | Kullanıcının Intune lisansı vardır ama cihaza Şirket Portalı uygulaması yüklenene kadar uygulama kaydedilemez. Intune Uygulama SDK’sı verili kullanıcı için uygulamaya erişimi engellemeyi dener ve kullanıcıyı Şirket Portalı uygulamasını yüklemeye yönlendirir (ayrıntılar için aşağıya bakın). |


### <a name="company-portal-requirement-prompt-override-optional"></a>Şirket Portalı gereksinimi istemini geçersiz kılma (isteğe bağlı)

`COMPANY_PORTAL_REQUIRED` Sonucu alınırsa, SDK kendisi için kayıt istenen kimliğin kullanıldığı etkinliklerin kullanımını engeller. Bunun yerine, SDK bu etkinliklerin Şirket Portalı’nı indirme istemi görüntülemesine neden olur. Uygulamanızda bu davranışı engellemek istiyorsanız, etkinlikler `MAMActivity.onMAMCompanyPortalRequired` gerçekleştirebilir.

Bu yöntem, SDK varsayılan engelleme UI’sini görüntülemeden önce çağrılır. Uygulama etkinlik kimliğini değiştirirse veya kaydolmaya çalışan kullanıcının kaydını kaldırırsa, SDK etkinliği engellemez. Bu durumda, kurumsal verilerin sızdırılmasını önlemek uygulamanın tercihine bağlı olur.

### <a name="notifications"></a>Bildirimler

Uygulamaya kayıt isteğinin tamamlandığını haber vermek için yeni bir tür `MAMNotification` eklenmiştir.  `MAMEnrollmentNotification`, [SDK’dan gelen bildirimlere kaydolma](#register-for-notifications-from-the-sdk) bölümünde açıklandığı gibi `MAMNotificationReceiver` arabirimi üzerinden alınır.

```java
public interface MAMEnrollmentNotification extends MAMUserNotification {
    MAMEnrollmentManager.Result getEnrollmentResult();
}

```

`getEnrollmentResult()` yöntemi, kayıt isteğinin sonucunu döndürür.  `MAMEnrollmentNotification` `MAMUserNotification`‘ın kapsamını genişlettiğinden, kayıt girişiminde bulunulan kullanıcının kimliği de sağlanır. Uygulama, [SDK’dan gelen bildirimlere kaydolma](#Register-for-notifications-from-the-SDK) bölümünde ayrıntılarıyla açıklandığı gibi, bu bildirimleri almak için `MAMNotificationReceiver` arabirimini gerçekleştirmelidir.

Kayıt bildirimi alındığında kayıtlı kullanıcı hesabının durumu değişebilir ama bazı durumlarda da değişmez (örneğin, `AUTHORIZATION_NEEDED` bildirimi `WRONG_USER` gibi daha bilgilendirici bir sonuçtan sonra alınırsa, hesabın durumu olarak daha bilgilendirici olan sonuç korunur).


## <a name="protecting-backup-data"></a>Yedekleme verilerini koruma

Android Marshmallow (API 23) sürümünden itibaren Android’deki bir uygulama, verileri iki yolla yedekleyebilir. Her bir seçenek uygulamanızda kullanılabilir ve Intune veri korumasının doğru bir şekilde uygulandığından emin olmak için farklı adımlar gerektirir. Doğru veri koruma davranışı için gerekli olan ilgili eylemler için aşağıdaki tabloyu gözden geçirebilirsiniz.  Yedekleme yöntemleri hakkında daha fazla bilgi için bkz. [Android API kılavuzu](http://developer.android.com/guide/topics/data/backup.html).

### <a name="auto-backup-for-apps"></a>Uygulamalar için Otomatik Yedekleme

Android, Android Marshmallow cihazlarındaki uygulamalar için Google Drive’a, uygulamanın hedef API’sinden bağımsız olarak [otomatik tam yedeklemeler](https://developer.android.com/guide/topics/data/autobackup.html) sunmaya başlamıştır. AndroidManifest.xml içinde `android:allowBackup` öğesini açıkça **false** olarak ayarlarsanız, uygulamanız hiçbir zaman Android tarafından yedeklenmek üzere sıraya alınmaz ve "kurumsal" veriler uygulama içinde kalır. Bu durumda, başka bir eylem gerekmez.

Ancak, `android:allowBackup` özniteliği, bildirim dosyasında `android:allowBackup` belirtilmemiş olsa bile varsayılan olarak true olarak ayarlanmıştır. Bu, tüm uygulama verilerinin otomatik olarak Google Drive hesabına yedeklendiği anlamına gelir ve bu da **veri sızıntısı riski** oluşturan bir varsayılan davranıştır. Bu nedenle SDK, veri korumasının uygulandığından emin olmak için aşağıda ana hatlarıyla verilen değişiklikleri gerektirir.  Uygulamanızın Android Marshmallow cihazlarında çalışmasını istiyorsanız, müşteri verilerini düzgün bir şekilde korumak için aşağıdaki yönergeleri izlemek önemlidir.  

Intune, XML’de özel kurallar tanımlama becerisi de dahil olmak üzere Android’in sunduğu tüm [Otomatik Yedekleme özelliklerinden](https://developer.android.com/guide/topics/data/autobackup.html) faydalanmanıza olanak tanır, ancak verilerinizin güvenliğini sağlamak için aşağıdaki adımları uygulamanız gerekir:

1. Uygulamanız kendi özel BackupAgent’ını **kullanmıyorsa**, Intune ilkesi uyumluluğu olan otomatik tam yedeklemelere olanak tanımak için varsayılan MAMBackupAgent’ı kullanın. Bunu yaparsanız, `android:fullBackupOnly` bildirim özniteliğini yoksayabilirsiniz çünkü bu bizim yedekleme aracımıza uygulanamaz. Uygulama bildirimine aşağıdakileri yerleştirin:

    ```xml
android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"
    ```


2. **[İsteğe bağlı]** İsteğe bağlı bir özel BackupAgent gerçekleştirdiyseniz, MAMBackupAgent veya MAMBackupAgentHelper kullandığınızdan emin olmalısınız. Aşağıdaki bölümlere bakın. Android M ve üstü sürümlerde kolay yedekleme sağlayan Intune’un **MAMDefaultFullBackupAgent**’ını (1. adımda açıklanmıştır) kullanmaya geçmeniz önerilir.

3. Uygulamanızın hangi tam yedekleme türünü (filtresiz, filtreli veya hiçbiri) almasını istediğinize karar verdiğinizde, `android:fullBackupContent` özniteliğini true, false veya uygulamanızda bir XML kaynağı olarak ayarlamanız gerekir.

4. Ardından, `android:fullBackupContent` içine yerleştirdiğiniz her şeyi bildirimde `com.microsoft.intune.mam.FullBackupContent` adlı meta veri etiketine kopyalamanız _**gerekir**_.

    **1. Örnek**: Uygulamanızın özel durumlar olmadan tam yedeklemeleri olmasını istiyorsanız, hem `android:fullBackupContent` özniteliğini hem de `com.microsoft.intune.mam.FullBackupContent` meta veri etiketini **true** olarak ayarlayın:

    ```xml
    android:fullBackupContent="true"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />  
    ```

    **2. Örnek**: Uygulamanızın kendi özel BackupAgent’ını kullanmasını istiyor ve tam, Intune ilkesiyle uyumlu, otomatik yedeklemelerden vazgeçiyorsanız, özniteliği ve meta veri etiketini **false** olarak ayarlamalısınız:

    ```xml
    android:fullBackupContent="false"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="false" />  
    ```

    **3. Örnek**: Uygulamanızın XML dosyasında tanımlanan özel kurallarınıza uygun olarak tam yedeklemeleri olmasını istiyorsanız, lütfen öznitelikle meta veri etiketini aynı XML kaynağına ayarlayın:

    ```xml
    android:fullBackupContent="@xml/my_scheme"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```


### <a name="keyvalue-backup"></a>Anahtar/Değer Yedeklemesi

[Anahtar/Değer Yedeklemesi](https://developer.android.com/guide/topics/data/keyvaluebackup.html) seçeneği tüm 8+ API’lerinde kullanılabilir ve uygulama verilerini [Android Yedekleme Hizmeti](https://developer.android.com/google/backup/index.html)’ne yükler. Uygulamanızın her kullanıcısı için veri miktarı sınırı 5 MB’tır. Anahtar/Değer Yedeklemesi’ni kullanıyorsanız, bir **BackupAgentHelper** veya **BackupAgent** kullanmalısınız.

### <a name="backupagenthelper"></a>BackupAgentHelper

BackupAgentHelper’ın uygulanması, hem yerel Android işlevselliği hem de Intune MAM tümleştirmesi bakımından BackupAgent‘ın uygulanmasından daha kolaydır. BackupAgentHelper, geliştiricinin tüm dosyaları ve paylaşılan tercihleri sırasıyla bir **FileBackupHelper** ve **SharedPreferencesBackupHelper**’a kaydetmesine olanak tanır. Bunlar, oluşturma sonrasında BackupAgentHelper’a eklenir. Intune MAM ile BackupAgentHelper kullanmak için aşağıdaki adımları izleyin:

1. Çok kimlikli yedeklemeyi BackupAgentHelper ile kullanmak için, Android’in [BackupAgentHelper’ın Kapsamını Genişletme](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgentHelper) yönergelerini izleyin.

2. Sınıfınızı BackupAgentHelper, FileBackupHelper ve SharedPreferencesBackupHelper’ın MAM eşdeğerini içerecek şekilde genişletin.

|Android sınıfı | MAM eşdeğeri |
|--|--|
|BackupAgentHelper |MAMBackupAgentHelper |
|FileBackupHelper | MAMFileBackupHelper
|SharedPreferencesBackupHelper| MAMSharedPreferencesBackupHelper|

Bu yönergeler izlendiğinde, başarılı bir çok kimlikli yedekleme ve geri yükleme elde edilir.

### <a name="backupagent"></a>BackupAgent

BackupAgent, hangi verilerin yedeklendiği konusunda çok daha net olmanızı sağlar. Uygulama sorumluluğunun büyük bölümü geliştiriciye ait olduğundan, Intune aracılığıyla uygun veri korumasını sağlamak için daha fazla adım gerekir. Intune tümleştirme işlerinin büyük bölümü geliştirici olarak size gönderildiğinden, Intune tümleştirmesi biraz daha karmaşıktır.

**MAM tümleştirmesi:**

1. BackupAgent uygulamanızın Android yönergelerine uyduğundan emin olmak için lütfen Android’in [Anahtar/Değer Yedeklemesi](https://developer.android.com/guide/topics/data/keyvaluebackup.html) kılavuzunu ve özellikle de [BackupAgent’ın Kapsamını Genişletme](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent) konusunu dikkatle okuyun.

2. Sınıfınızın kapsamını `MAMBackupAgent` için genişletin.

**Çok Kimlikli Yedekleme:**

1. Yedekleme işleminize başlamadan önce, yedeklemeyi planladığınız dosyaların ve veri arabelleklerinin çok kimlikli senaryolarda **yedeklenmesine BT yöneticisi tarafından gerçekten izin verilip verilmediğini** denetleyin. Bunu saptamak için size `MAMFileProtectionManager` ve `MAMDataProtectionManager` içinde `isBackupAllowed` işlevini sağlıyoruz. Dosya veya veri arabelleğinin yedeklenmesine izin verilmiyorsa, bunu yedeklemenize eklemeye çalışmamanız gerekir.

2. Yedeklemenin belirli bir noktasında, 1. adımda denetlediğiniz dosyaların kimliklerini yedeklemek isterseniz, verileri ayıklamayı planladığınız dosyalarla birlikte `backupMAMFileIdentity(BackupDataOutput data, File … files)` çağrısı yapmanız gerekir. Bu, otomatik olarak yeni yedekleme varlıkları oluşturur ve bunları sizin için `BackupDataOutput` ’a yazar. Bu varlıklar geri yükleme sonrasında otomatik olarak kullanılır.

**Çok Kimlikli Geri Yükleme:**

Veri Yedekleme kılavuzu uygulamanızın verilerini geri yüklemeniz için genel bir algoritma belirler ve [BackupAgent’ı Genişletme](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent) bölümünde bir kod örneği sağlar. Çok kimlikli geri yükleme işlemini başarmak için, bu kod örneğinde sağlanan genel yapıya uymalı ve aşağıdakilere özel olarak dikkat etmelisiniz:

1.  Yedekleme varlıkları arasında ilerlemek için `while(data.readNextHeader())`* döngüsü kullanmalısınız.

2.  `data.getKey()`* `onBackup` içinde yazdığınız anahtarla eşleşmezse, `data.skipEntityData()`* çağrısı yapmalısınız. Bu adımı gerçekleştirmeden geri yüklemeleriniz başarılı olamaz.

3.  `while(data.readNextHeader())`* yapısında yedekleme varlıklarını kullanırken geri dönmekten kaçının, çünkü otomatik olarak yazılan varlıklar kaybedilir.

* Burada `data`, geri yüklemede uygulamanıza geçirilen **BackupDataInput** için yerel değişken adıdır.

## <a name="multi-identity-optional"></a>Çok Kimlikli (isteğe bağlı)

### <a name="overview"></a>Genel bakış
Varsayılan olarak Intune Uygulama SDK’sı, ilkeyi uygulamaya bir bütün halinde uygular. Çok kimlikli, ilkenin her kimlik düzeyinde uygulanmasına izin vermek üzere etkinleştirilebilen, isteğe bağlı bir Intune uygulama koruma özelliğidir. Bu, diğer uygulama koruma özelliklerine kıyasla önemli oranda daha fazla uygulama katılımı gerektirir.

Uygulama, etkin kimliği değiştirmeyi amaçladığında bunu SDK’ya bildirmek *zorundadır*. Bazı durumlarda, bir kimlik değişikliği gerektiğinde SDK bunu uygulamaya bildirir. Ancak çoğu zaman MAM, hangi verilerin kullanıcı arabiriminde görüntülendiğini veya belirli bir anda bir iş parçacığında kullanıldığını bilemez, veri sızıntısını önlemek için doğru kimliğin uygulama tarafından ayarlanması gerekir. Aşağıdaki bölümlerde, uygulama eylemi gerektiren bazı senaryolar verilmiştir.

> [!NOTE]
>  Uygulamanın doğru yerlerde katılımda bulunmaması, veri sızıntısı veya diğer güvenlik sorunlarıyla sonuçlanabilir.

Kullanıcı cihaz veya uygulamayı kaydettikten sonra, SDK bu kimliği kaydeder ve bunu Intune tarafından yönetilen birincil kimlik olarak kabul eder. Uygulamadaki diğer kullanıcılar kısıtlanmamış ilke ayarlarıyla yönetilmeyen olarak kabul edilirler.

> [!NOTE]
> Şu anda cihaz başına yalnızca bir Intune tarafından yönetilen kimlik desteklenir.

Bir kimliğin yalnızca dizi olarak tanımlandığını aklınızda bulundurun. Kimlikler **büyük/küçük harfe duyarlı değildir** ve SDK’ya kimlik için yapılan istekler, kimlik ayarlandığı sırada kullanılan özgün büyük/küçük harf dizimiyle aynı sonucu getirmeyebilir.

### <a name="enabling-multi-identity"></a>Çok kimlikli kullanımı etkinleştirme

Varsayılan olarak, tüm uygulamalar tek kimlikli uygulamalar olarak değerlendirilir. AndroidManifest.xml dosyasına aşağıdaki meta verileri yerleştirerek uygulamanın çok kimliği tanıdığını bildirebilirsiniz.

```xml
  <meta-data
    android:name="com.microsoft.intune.mam.MAMMultiIdentity"
    android:value="true" />
```

### <a name="setting-the-identity"></a>Kimliği Ayarlama

Geliştiriciler uygulama kullanıcısının kimliğini azalan öncelik sırasına göre aşağıdaki düzeylerde ayarlayabilir:

  1. İş parçacığı düzeyi
  2. Bağlam (genellikle Etkinlik) düzeyi
  3. İşlem düzeyi

İş parçacığı düzeyinde ayarlanmış bir kimlik Bağlam düzeyinde ayarlanmış bir kimliğin, bağlam düzeyinde ayarlanmış bir kimlikse işlem düzeyinde ayarlanmış bir kimliğin yerini alır. Bağlam’a ayarlı bir kimlik, yalnızca uygun ilişkili senaryolarda kullanılır. Örneğin dosya GÇ işlemlerinde ilişkili bir Bağlam bulunmaz. Çoğu zaman uygulamalar, Bağlam kimliğini bir Etkinliğe bağlı olarak ayarlar. Etkinlik kimliği söz konusu kimliğe ayarlı değilse bir uygulama, yönetilen bir kimlik hakkındaki verileri *görüntülememelidir*. Genel olarak işlem düzeyi kimliği yalnızca, uygulama belirli bir anda tüm iş parçacıklarında sadece tek bir kullanıcıyla çalışıyorsa kullanışlıdır. Pek çok uygulamanın bunu kullanmaya ihtiyacı yoktur.

Aşağıdaki `MAMPolicyManager` yöntemleri kimlik ayarlamak ve önceden ayarlanan kimlik değerlerini almak için kullanılabilir.

```java
  public static void setUIPolicyIdentity(final Context context, final String identity, final MAMSetUIIdentityCallback mamSetUIIdentityCallback);

  public static String getUIPolicyIdentity(final Context context);

  public static MAMIdentitySwitchResult setProcessIdentity(final String identity);

  public static String getProcessIdentity();

  public static MAMIdentitySwitchResult setCurrentThreadIdentity(final String identity);

  public static String getCurrentThreadIdentity();

/**
   * Get the current app policy. This does NOT take the UI (Context) identity into account.
   * If the current operation has any context (e.g. an Activity) associated with it, use the overload below.
   */
  public static AppPolicy getPolicy();

  /**
  * Get the current app policy. This DOES take the UI (Context) identity into account.
   * If the current operation has any context (e.g. an Activity) associated with it, use this function.
   */
  public static AppPolicy getPolicy(final Context context);


  public static AppPolicy getPolicyForIdentity(final String identity);

  public static boolean getIsIdentityManaged(final String identity);

  ```

>[!NOTE]
> Bir uygulamanın kimliğini null olarak ayarlayarak temizleyebilirsiniz.
>
> Boş dize, hiçbir zaman uygulama koruma ilkesine sahip olmayacak bir kimlik olarak kullanılabilir.

#### <a name="results"></a>Sonuçlar
Kimlik ayarlamak için kullanılan tüm yöntemler, sonuç değerlerini `MAMIdentitySwitchResult` aracılığıyla geri rapor eder. Döndürülebilecek dört değer vardır:

| Dönüş değeri | Senaryo |
|--|--|
| SUCCEEDED | Kimlik değişikliği başarılı oldu. |
| NOT_ALLOWED | Kimlik değişikliğine izin verilmiyor. Kimlik değişikliğine izin verilmiyor. Bu, geçerli iş parçacığı üzerinde farklı bir kimlik ayarlanmışken kullanıcı arabirimi (Bağlam) kimliğini ayarlamak denenirse gerçekleşir. |
| CANCELLED | Kullanıcı, genellikle PIN veya kimlik doğrulama istemi üzerindeki geri tuşuna basarak, kimlik değişikliğini iptal etmiştir. |
| FAILED | Kimlik değişikliği belirlenemeyen bir nedenden dolayı başarısız oldu.|

Şirket verilerini görüntülemeden veya kullanmadan önce uygulama, kimlik geçişinin başarılı olduğundan *emin olmalıdır*. Şu anda birden çok kimlik etkin uygulamalarda, işlem ve iş parçacığı kimliklerinin geçişleri her zaman başarılı olmaktadır ancak hata koşulları ekleme hakkımızı saklı tutuyoruz. İş parçacığı kimliğiyle çakışırsa veya kullanıcı koşullu başlatma gereksinimlerini iptal ederse (yani PIN ekranında geri düğmesine basarsa) kullanıcı arabirimi kimlik geçişi, geçersiz bağımsız değişkenler için başarısız olabilir.


Bir Bağlam kimliği ayarlamak söz konusu olduğunda, sonuç zaman uyumsuz olarak bildirilir. Bağlam bir Etkinlik ise, koşullu başlatma uygulanana kadar SDK kimlik değişikliğinin başarılı olup olmadığını bilmez ve bunun için kullanıcının PIN değerini veya şirket kimlik bilgilerini girmesi gerekebilir. Uygulamanın bu sonucu almak için bir `MAMSetUIIdentityCallback` uygulaması gerekir, bu parametre için null değeri geçirebilirsiniz.

```java
    public interface MAMSetUIIdentityCallback {
        void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult);
  }
```

Ayrıca bir etkinliğin kimliğini, `MAMPolicyManager.setUIPolicyIdentity` çağrısı yapmak yerine doğrudan `MAMActivity` yöntemiyle de ayarlayabilirsiniz. Bunu yapmak için şu yöntemi kullanın:

```java
     public final void switchMAMIdentity(final String newIdentity);
```

Ayrıca, bu etkinliğin kimliğini değiştirme denemelerinin sonucu hakkında uygulamanın bildirim almasını istiyorsanız `MAMActivity` üzerinde bir yöntemi geçersiz kılabilirsiniz.

``` java
    public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);
```

>[!NOTE]
> Kimliği değiştirmek için etkinliğin yeniden oluşturulması gerekebilir. Bu durumda, `onSwitchMAMIdentityComplete` geri çağırma yeni etkinlik örneğine gönderilir.


### <a name="implicit-identity-changes"></a>Örtük Kimlik Değişiklikleri

Uygulamanın kimlik ayarlayabilme özelliğine ek olarak, bir iş parçacığı veya bir bağlamın kimliği uygulama koruma ilkesi olan başka bir Intune ile yönetilen uygulamadan veri girişine göre değişebilir.

#### <a name="examples"></a>Örnekler

  1. Etkinlik başka bir MAM uygulamasından gönderilen bir `Intent` ile başlatılmışsa, etkinliğin kimliği `Intent`’in gönderildiği noktada diğer uygulamadaki etkin kimliğe göre ayarlanır.

  2.  Hizmetler için iş parçacığı kimliği bir `onStart` veya `onBind` çağrısının süresine benzer şekilde ayarlanır. `Binder` öğesinden döndürülen `onBind` içine yapılan çağrılar iş parçacığı kimliğini de geçici olarak ayarlar.

  3. `ContentProvider` içine yapılan çağrılar da benzer şekilde iş parçacığı kimliğini süreleri boyunca ayarlar.


  Ayrıca, bir etkinlikle kullanıcı etkileşimi bir örtük kimlik anahtarına neden olabilir.

  **Örnek:** `Resume` sırasında bir kullanıcının bir yetkilendirme istemini iptal etmesi, boş bir kimliğe örtük anahtar ile sonuçlanır.

  Uygulamaya bu değişiklikler hakkında haber alma fırsatı verilir ve gerekirse uygulama bunları yasaklayabilir. `MAMService` ve `MAMContentProvider`, alt sınıfların geçersiz kılabileceği aşağıdaki yöntemi kullanıma sunar:

  ```java
  public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchResultCallback callback);
  ```

  `MAMActivity` sınıfında, yöntemde ek bir parametre olur:

  ```java
  public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchReason reason,
    final AppIdentitySwitchResultCallback callback);
  ```

  * `AppIdentitySwitchReason`, örtük anahtarın kaynağını yakalar ve `CREATE`, `RESUME_CANCELLED` ve `NEW_INTENT` değerlerini kabul edebilir.  Etkinliği sürdürmek PIN, kimlik doğrulama veya başka bir uyumluluk UI’sinin görüntülenmesine neden olduğunda ve kullanıcı bu UI’yi genellikle geri tuşuna basarak iptal etmeyi denediğinde `RESUME_CANCELLED` nedeni kullanılır.


  * `AppIdentitySwitchResultCallback` aşağıdaki şekildedir:

    ```java
    public interface AppIdentitySwitchResultCallback {
        /**
         * @param result
         *            whether the identity switch can proceed.
         */
        void reportIdentitySwitchResult(AppIdentitySwitchResult result);
    }
    ```

    Burada ```AppIdentitySwitchResult```, SUCCESS veya FAILURE olur.

`onMAMIdentitySwitchRequired` yöntemi, `MAMService.onMAMBind` öğesinden döndürülen bir Bağlayıcı aracılığıyla yapılanlar dışındaki tüm örtük kimlik değişiklikleri için çağrılır. Varsayılan `onMAMIdentitySwitchRequired` uygulamaları hemen şu çağrıyı yapar:

*  Neden RESUME_CANCELLED olduğunda, `reportIdentitySwitchResult(FAILURE)`.

*  Diğer tüm durumlarda `reportIdentitySwitchResult(SUCCESS)`.

  Çoğu uygulamanın bir kimlik anahtarını farklı bir şekilde engellemesi veya geciktirmesi beklenmez, ancak bir uygulamanın böyle yapması gerekirse aşağıdaki noktaların göz önünde bulundurulması gerekir:

  * Bir kimlik değişimi engellenirse, sonuç `Receive` paylaşım ayarları veri girişini yasakladığında olan ile aynıdır.

  * Bir Hizmet ana iş parçacığı üzerinde çalışıyorsa, `reportIdentitySwitchResult` öğesinin zaman uyumlu olarak çağrılması **gerekir**, yoksa UI iş parçacığı kapanır.

  * **Etkinlik** oluşturmak için `onMAMCreate` yönteminden önce `onMAMIdentitySwitchRequired` çağrılır. Kimlik anahtarına izin verilip verilmeyeceğine karar vermek için uygulamanın UI göstermesi gerekiyorsa, bu UI *farklı* bir etkinlik kullanılarak gösterilmelidir.

  * Bir **Etkinlik** içinde, SÜRDÜRME İPTAL EDİLDİ nedeniyle boş kimliğe anahtar istenirse, uygulamanın bu kimlik anahtarı ile tutarlı verileri görüntülemek için sürdürülen etkinliği değiştirmesi gerekir.  Bu mümkün değilse, uygulama anahtarı reddetmelidir ve kullanıcıdan bir kez daha sürdürülen kimlik ilkesine uyması istenir (örneğin, uygulamanın PIN girişi ekranı gösterilerek).

    > [!NOTE]
    > Çok kimlikli bir uygulama, yönetilen ve yönetilmeyen uygulamalardan gelen verileri her zaman alır. Yönetilen kimliklerden alınan verileri yönetilen kabul etmek uygulamanın sorumluluğudur.

  İstenen kimlik yönetiliyorsa (denetlemek için `MAMPolicyManager.getIsIdentityManaged` kullanın), ancak uygulama bu hesabı kullanamıyorsa (mesela e-posta hesapları gibi hesapların, ilk olarak uygulamada ayarlanması gerektiği için) kimlik anahtarı reddedilir.

### <a name="preserving-identity-in-async-operations"></a>Zaman Uyumsuz İşlemlerde Kimliği Koruma
UI iş parçacığındaki işlemler için arka plan görevlerinin başka bir iş parçacığına gönderilmesi yaygın bir durumdur. Çok kimlikli bir uygulama, bu arka plan görevlerinin uygun kimlikle çalıştırıldığından emin olmak ister; bu kimlik çoğunlukla bunları gönderen etkinliğin kullandığı kimliktir. MAM SDK'sı, kimliği koruma konusunda yardımcı olmak için `MAMAsyncTask` ve `MAMIdentityExecutors` sağlar.
#### <a name="mamasynctask"></a>MAMAsyncTask

`MAMAsyncTask` kullanmak için, AsyncTask yerine bundan devralın, sonra da `doInBackground` ve `onPreExecute` geçersiz kılmalarını sırasıyla `doInBackgroundMAM` ve `onPreExecuteMAM` ile değiştirin. `MAMAsyncTask` oluşturucusu bir etkinlik bağlamı alır. Örneğin:

```java
  AsyncTask<Object, Object, Object> task = new MAMAsyncTask<Object, Object, Object>(thisActivity) {

    @Override
    protected Object doInBackgroundMAM(final Object[] params) {
        // Do operations.
    }
    
    @Override
    protected void onPreExecuteMAM() {
        // Do setup.
    };
```

### <a name="mamidentityexecutors"></a>MAMIdentityExecutors
`MAMIdentityExecutors`, `Executor`/`ExecutorService` öğesini `wrapExecutor` ve `wrapExecutorService` yöntemleriyle koruyarak mevcut `Executor` veya `ExecutorService` örneğini bir kimlik olarak sarmalamanıza olanak tanır. Örneğin

```java
  Executor wrappedExecutor = MAMIdentityExecutors.wrapExecutor(originalExecutor, activity);
  ExecutorService wrappedService = MAMIdentityExecutors.wrapExecutorService(originalExecutorService, activity);
```

  ### <a name="file-protection"></a>Dosya Koruması

  Her dosyanın, oluşturulduğu sırada iş parçacığı ve işlem kimliğine dayalı olarak kendisiyle ilişkilendirilmiş bir kimliği vardır. Bu kimlik hem dosya şifreleme hem de seçici silme için kullanılır. Yalnızca kimliği yönetilen ve şifreleme gerektiren ilkesi bulunan dosyalar şifrelenir. SDK'nın varsayılan seçmeli silme işlevselliği, yalnızca silme işleminin istendiği yönetilen kimlikle ilişkilendirilmiş dosyaları siler. Uygulama, `MAMFileProtectionManager` sınıfını kullanarak bir dosyanın kimliğini sorgulayabilir veya değiştirebilir.

  ```java
    public final class MAMFileProtectionManager {
    /**
         * Protect a file. This will synchronously trigger whatever protection is required for the 
           file, and will tag the file for future protection changes.

         *
         * @param identity
         *            Identity to set.
         * @param file
         *            File to protect.
         * @throws IOException
         *             If the file cannot be changed.
         */
        public static void protect(final File file, final String identity) throws IOException;
        
        /**
        * Protect a file obtained from a content provider. This is intended to be used for
        * sdcard (whether internal or removable) files accessed through the Storage Access Framework.
        * It may also be used with descriptors referring to private files owned by this app.
        * It is not intended to be used for files owned by other apps and such usage will fail. If
        * creating a new file via a content provider exposed by another MAM-integrated app, the new
        * file identity will automatically be set correctly if the ContentResolver in use was
        * obtained via a Context with an identity or if the thread identity is set.
        *
        * This will synchronously trigger whatever protection is required for the file, and will tag
        * the file for future protection changes. If an identity is set on a directory, it is set
        * recursively on all files and subdirectories. If MAM is operating in offline mode, this
        * method will silently do nothing.
        *
        * @param identity
        *       Identity to set.
        * @param file
        *       File to protect.
        *
        * @throws IOException
        *       If the file cannot be protected.

        */
        public static void protect(final ParcelFileDescriptor file, final String identity) throws IOException;

        /**
         * Get the protection info on a file.
         *
         * @param file
         *            File or directory to get information on.
         * @return File protection info, or null if there is no protection info.
         * @throws IOException
         *             If the file cannot be read or opened.
         */
        public static MAMFileProtectionInfo getProtectionInfo(final ParcelFileDescriptor file) throws IOException;

    }

    public interface MAMFileProtectionInfo {
        String getIdentity();
    }

  ```
#### <a name="app-responsibility"></a>Uygulama Sorumluluğu
MAM, bir `Activity` öğesinde okunan dosyalar ve görüntülenen veriler arasında otomatik olarak bir ilişki çıkaramaz. Uygulamalar, şirket verilerini görüntülemeden önce kullanıcı arabirimi kimliğini uygun şekilde *ayarlamalıdır*. Bu, dosyalardan veri okumayı içerir. Bir dosya uygulama dışında geliyorsa (bir `ContentProvider` öğesinden geliyorsa veya herkesin yazılabildiği bir konumdan okunuyorsa) uygulama, dosyadan okunan bilgileri görüntülemeden önce (`MAMFileProtectionManager.getProtectionInfo` kullanarak) dosya kimliğini belirleme *girişiminde bulunmalıdır*. `getProtectionInfo` null veya boş olmayan bir kimlik rapor ederse kullanıcı arabirimi kimliği, bu kimlikle eşleşmek üzere (`MAMActivity.switchMAMIdentity` veya `MAMPolicyManager.setUIPolicyIdentity` kullanarak) *ayarlanmalıdır*. Kimlik geçişi başarısız olursa dosyadan okunan veriler *görüntülenmemelidir*.

Örnek bir akış aşağıdaki gibi olabilir:
  * Kullanıcı, uygulamada açmak üzere bir belge seçer
  * Açma akışında, diskten veri okumadan önce içeriği görüntülemek için kullanılacak kimlik uygulama tarafından onaylanır
    * MAMFileProtectionInfo info = MAMFileProtectionManager.getProtectionInfo(docPath)
    * if(info)   MAMPolicyManager.setUIPolicyIdentity(activity, info.getIdentity(), callback)
    * Uygulama geri aramadan önce sonucun rapor edilmesini bekler
    * Sonuç başarısız olarak rapor edilirse uygulama, belgeyi görüntülemez.
  * Uygulama açılır ve dosyayı işler

## <a name="offline-scenarios"></a>Çevrimdışı Senaryolar

Dosya kimliği etiketlemesi çevrimdışı moda karşı hassastır. Aşağıdaki noktalar göz önünde bulundurulmalıdır:

  * Şirket Portalı yüklü değilse, dosyalar kimlik etiketli olamaz.

  * Şirket Portalı yüklüyse ancak uygulamada Intune MAM ilkesi yoksa, dosyalar güvenilir bir şekilde kimlikle etiketlenemez.

  * Dosya kimliği etiketleme kullanılabilir olduğunda, uygulama kayıtlı kullanıcıya ait kabul edildiği durumda önceden tek kimlikli yönetilen uygulama olarak yüklenmediyse, önceden oluşturulan tüm dosyalar kişisel/yönetilmeyen olarak kabul edilir (boş dize kimliğine ait olarak).

### <a name="directory-protection"></a>Dizin Koruması

Dizinler, dosyaları korumak için kullanılan aynı `protect` yöntemiyle korunabilir. Dizin korumasının dizinin içindeki tüm dosyalara, alt dizinlere ve dizin içinde oluşturulan yeni dosyalara yinelemeli olarak uygulandığını lütfen unutmayın. Dizin koruması yinelemeli olarak uygulandığından, çok büyük dizinlerde `protect` çağrısı biraz zaman alabilir. Bu nedenle, çok fazla sayıda dosya içeren bir dizine koruma gerçekleştiren uygulamalar `protect` çağrısını bir arka plan iş parçacığında zaman uyumsuz olarak çalıştırmak isteyebilir.

### <a name="data-protection"></a>Veri Koruma

Çoklu kimliklere ait bir dosyayı etiketlemek mümkün değildir. Aynı dosyada farklı kullanıcılara ait verileri depolaması gereken uygulamalar bunu, `MAMDataProtectionManager` tarafından sağlanan özellikleri kullanarak yapabilir. Bu, uygulamanın veri şifrelemesine ve belirli bir kullanıcıya bağlamasına olanak tanır. Şifrelenmiş veriler, bir dosyadaki diske depolamak için uygundur. Kimlikle ilişkili verileri sorgulayabilir ve verilerin şifresini daha sonra kaldırabilirsiniz.

`MAMDataProtectionManager` kullanan uygulamalar, `MANAGEMENT_REMOVED` bildirimi için bir alıcı gerçekleştirmelidir. Bu bildirim tamamlandıktan sonra, arabellekler korunduğu sırada dosya şifrelemesi etkinleştirilmişse, bu sınıf yoluyla korunan arabellekler artık okunabilir durumda olmaz. Uygulama, bu bildirim sırasında tüm arabellekler üzeride MAMDataProtectionManager.unprotect çağrısı yaparak bu durumu düzeltebilir. Kimlik bilgilerinin korunması isteniyorsa bu bildirim sırasında koruma çağrısı yapmak da güvenli olur; çağrı sırasında şifrelemenin devre dışı bırakılacağı garanti edilir.

```java

public final class MAMDataProtectionManager {
    /**
     * Protect a stream. This will return a stream containing the protected
     * input.
     *
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect, read sequentially. This function
     *            will change the position of the stream but may not have
     *            read the entire stream by the time it returns. The
     *            returned stream will wrap this one. Calls to read on the
     *            returned stream may cause further reads on the original
     *            input stream. Callers should not expect to read directly
     *            from the input stream after passing it to this method.
     *            Calling close on the returned stream will close this one.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static InputStream protect(final InputStream input, final String identity);

    /**
     * Protect a byte array. This will return protected bytes.
     *
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static byte[] protect(final byte[] input, final String identity) throws IOException;

    /**
     * Unprotect a stream. This will return a stream containing the
     * unprotected input.
     *
     * @param input
     *            Input data to protect, read sequentially.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static InputStream unprotect(final InputStream input) throws IOException;

    /**
     * Unprotect a byte array. This will return unprotected bytes.
     *
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static byte[] unprotect(final byte[] input) throws IOException;

    /**
     * Get the protection info on a stream.
     *
     * @param input
     *            Input stream to get information on. Either this input
     *            stream must have been returned by a previous call to
     *            protect OR input.markSupported() must return true.
     *            Otherwise it will be impossible to get protection info
     *            without advancing the stream position. The stream must be
     *            positioned at the beginning of the protected data.
     * @return Data protection info, or null if there is no protection
     *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final InputStream input) throws IOException;

    /**
     * Get the protection info on a stream.
     *
     * @param input
     *            Input bytes to get information on. These must be bytes
     *            returned by a previous call to protect() or a copy of
     *            such bytes.
     * @return Data protection info, or null if there is no protection
     *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final byte[] input) throws IOException;
}

```

### <a name="content-providers"></a>İçerik Sağlayıcıları

Uygulama **ContentProvider** aracılığıyla **ParcelFileDescriptor** dışında kurumsal veriler sağlıyorsa, uygulamanın `MAMContentProvider` içinde `isProvideContentAllowed(String)` yöntemini çağırması, içerik için sahip kimliğinin UPN’sini (kullanıcı asıl adı) geçirmesi gerekir. Bu işlev false döndürürse, içerik çağrıyı yapana *döndürülmemelidir*. İçerik sağlayıcısı aracılığıyla döndürülen dosya tanımlayıcıları dosya kimliğine göre otomatik olarak işlenir.

### <a name="selective-wipe"></a>Seçmeli Silme

Uygulama `WIPE_USER_DATA` bildirimine kayıtlıysa, SDK’nın varsayılan seçmeli silme davranışının avantajından yararlanamaz. Çoklu kimliği tanıyan uygulamalarda, MAM varsayılan seçmeli silme yalnızca silme işleminde kimliği hedeflenen dosyaları sileceğinden bu kayıp daha önemli olabilir.

Çoklu kimliği tanıyan bir uygulama MAM varsayılan seçmeli silme işleminin yapılmasını _**ve**_ silme işleminde kendi eylemlerini gerçekleştirmek isterse, `WIPE_USER_AUXILIARY_DATA` bildirimlerine kayıtlı olması gerekir. Bu bildirim, SDK tarafından MAM varsayılan seçmeli silme gerçekleştirmeden hemen önce gönderilir. Uygulama, hiçbir zaman hemen WIPE_USER_DATA hem de WIPE_USER_AUXILIARY_DATA için kaydedilmemelidir.

## <a name="enabling-mam-targeted-configuration-for-your-android-applications-optional"></a>Android uygulamalarınız için MAM hedefli yapılandırmayı etkinleştirme (isteğe bağlı)
Intune konsolunda uygulamaya özgü anahtar-değer çiftleri yapılandırılabilir. Bu anahtar-değer çiftleri Intune tarafından değiştirilmeden yalnızca uygulamaya geçirilir. Bu tip bir yapılandırma almak isteyen uygulamalar bunun için `MAMAppConfigManager` ve `MAMAppConfig` sınıflarını kullanabilir. Aynı uygulamaya birden çok ilke hedeflenmişse aynı anahtar için birden çok çakışan değer olabilir.

### <a name="example"></a>Örnek
```
MAMAppConfigManager configManager = MAMComponents.get(MAMAppConfigManager.class);
String identity = "user@contoso.com"
MAMAppConfig appConfig = configManager.getAppConfig(identity);
LOGGER.info("App Config Data = " + (appConfig == null ? "null" : appConfig.getFullData()));
String valueToUse = null;
if (appConfig.hasConflict("foo")) {
    List<String> values = appConfig.getAllStringsForKey("foo");
    for (String value : values) {
        if (isCorrectValue(value)) {
            valueToUse = value;
        }
    }
} else {
    valueToUse = appConfig.getStringForKey("foo", MAMAppConfig.StringQueryType.Any);
}
LOGGER.info("Found value " + valueToUse);
```

### <a name="mamappconfig-reference"></a>MAMAppConfig Başvurusu

```
public interface MAMAppConfig {
    /**
     * Conflict resolution types for Boolean values.
     */
    enum BooleanQueryType {
        /**
         * In case of conflict, arbitrarily picks one. This is not guaranteed to return the same value every time.
         */
        Any,
        /**
         * In case of conflict, returns true if any of the values are true.
         */
        Or,
        /**
         * In case of conflict, returns false if any of the values are false.
         */
        And
    }

    /**
     * Conflict resolution types for integer and double values.
     */
    enum NumberQueryType {
        /**
         * In case of conflict, arbitrarily picks one. This is not guaranteed to return the same value every time.
         */
        Any,
        /**
         * In case of conflict, returns the minimum Integer.
         */
        Min,
        /**
         * In case of conflict, returns the maximum Integer.
         */
        Max
    }

    /**
     * Conflict resolution types for Strings.
     */
    enum StringQueryType {
        /**
         * In case of conflict, arbitrarily picks one. This is not guaranteed to return the same value every time.
         */
        Any,
        /**
         * In case of conflict, returns the first result ordered alphabetically.
         */
        Min,
        /**
         * In case of conflict, returns the last result ordered alphabetically.
         */
        Max
    }

    /**
     * Retrieve the List of Dictionaries containing all the custom
     *  config data sent by the MAMService. This will return every
     * Application Configuration setting available for this user, one
     *  mapping for each policy applied to the user.
     */
    List<Map<String, String>> getFullData();

    /**
     * Returns true if there is more than one targeted custom config setting for the key provided. 
     */
    boolean hasConflict(String key);

    /**
     * @return a Boolean value for the given key if it can be coerced into a Boolean, or 
     * null if none exists or it cannot be coerced.
     */
    Boolean getBooleanForKey(String key, BooleanQueryType queryType);

    /**
     * @return a Long value for the given key if it can be coerced into a Long, or null if none exists or it cannot be coerced.
     */
    Long getIntegerForKey(String key, NumberQueryType queryType);

    /**
     * @return a Double value for the given key if it can be coerced into a Double, or null if none exists or it cannot be coerced.
     */
    Double getDoubleForKey(String key, NumberQueryType queryType);

    /**
     * @return a String value for the given key, or null if none exists.
     */
    String getStringForKey(String key, StringQueryType queryType);

    /**
     * Like getBooleanForKey except returns all values if multiple are present.
     */
    List<Boolean> getAllBooleansForKey(String key);

    /**
     * Like getIntegerForKey except returns all values if multiple are present.
     */
    List<Long> getAllIntegersForKey(String key);

    /**
     * Like getDoubleForKey except returns all values if multiple are present.
     */
    List<Double> getAllDoublesForKey(String key);

    /**
     * Like getStringForKey except returns all values if multiple are present.
     */
    List<String> getAllStringsForKey(String key);
}
```

### <a name="notification"></a>Bildirim
Uygulama yapılandırma, yeni bir bildirim türü ekler:
* **REFRESH_APP_CONFIG**: Bu bildirim, bir `MAMUserNotification` ile gönderilir ve yeni uygulama yapılandırmasının kullanılabilir olduğu hakkında uygulamayı bilgilendirir.

MAM hedefli yapılandırma değerleriyle ilgili Graph API işlevleri hakkında daha fazla bilgi için bkz. [Graph API Başvurusu MAM Hedefli Yapılandırma]((https://developer.microsoft.com/graph/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create). <br>

Android’de MAM hedefli bir uygulama yapılandırma ilkesi oluşturma hakkında daha fazla bilgi için [Android için Microsoft Intune uygulama yapılandırma ilkeleri kullanma](https://docs.microsoft.com/intune/app-configuration-policies-use-android) konusunun MAM hedefli uygulama yapılandırması hakkındaki bölümüne bakın.

## <a name="style-customization-optional"></a>Stil Özelleştirme (isteğe bağlı)

MAM SDK tarafından oluşturulan görünümler, içine tümleştirildiği uygulamayla daha iyi eşleşmesi için görsel olarak özelleştirilebilir. Birincil ve ikincil renklerle arka plan renklerini ve uygulama logosunun boyutunu özelleştirebilirsiniz. Bu stil özelleştirmesi isteğe bağlıdır ve özel bir stil yapılandırılmazsa varsayılanlar kullanılır.


### <a name="how-to-customize"></a>Nasıl özelleştirilir?
Stil değişikliklerinin Intune MAM görünümlerine uygulanmasını sağlamak için, önce bir stil geçersiz kılma XML dosyası oluşturmalısınız. Bu dosya uygulamanızın “/res/xml” dizinine yerleştirilmelidir ve bu dosyayı istediğiniz gibi adlandırabilirsiniz. Aşağıda, bu dosyanın uyması gereken biçimin örneği gösterilmektedir.

```xml
<?xml version="1.0" encoding="utf-8"?>
<styleOverrides>
    <item
        name="foreground_color"
        resource="@color/red"/>
    <item
        name="accent_color"
        resource="@color/blue"/>
    <item
        name="background_color"
        resource="@color/green"/>
    <item
        name="logo_image"
        resource="@drawable/app_logo"/>
</styleOverrides>

```

Uygulamanızın içinde zaten mevcut olan kaynakları yeniden kullanmalısınız. Örneğin, yeşil rengini colors.xml dosyasında tanımlamalı ve bu renge burada başvuruda bulunmalısınız. Onaltılı “#0000ff" renk kodunu kullanamazsınız. Uygulama logosu için boyut üst sınırı 110 dip’tir (dp). Daha küçük bir logo resmi kullanabilirsiniz, ama en iyi görünen sonuçlar en yüksek boyutta elde edilir. 110 dip sınırını aşarsanız, resmin ölçeği küçültülür ve büyük olasılıkla bulanık bir görüntü elde edilir.

Aşağıda izin verilen stil özniteliklerinin, bunların denetledikleri UI öğelerinin, XML özniteliği öğe adlarının ve her biri için beklenen kaynak türünün tam listesi verilmiştir.

|Stil özniteliği | Etkilenen UI öğeleri | Öznitelik öğesi adı | Beklenen kaynak türü |
| -- | -- | -- | -- |
| Arka plan rengi | PIN ekranı arka plan rengi <Br>PIN kutusu dolgu rengi | background_color | Renk |
| Ön plan rengi | Ön plan metin rengi <br> Varsayılan durumda PIN kutusu kenarlığı <br> Kullanıcı PIN girdiğinde PIN kutusundaki karakterler (gizlenmiş karakterler dahil)| foreground_color | Renk|
| Vurgu rengi | Vurgulandığında PIN kutusu kenarlığı <br> Köprüler |accent_color | Renk |
| Uygulama logosu | Intune uygulaması PIN ekranında gösterilen büyük simge | logo_image | Çizilebilir |

## <a name="requiring-user-login-prompt-for-an-automatic-app-we-service-enrollment-requiring-intune-app-protection-policies-in-order-to-use-your-sdk-integrated-android-lob-app-and-enabling-adal-sso-optional"></a>Otomatik bir APP-WE hizmeti kaydı için kullanıcı oturum açma istemi gerektirme, SDK ile tümleştirilmiş Android LOB uygulamanızı kullanmak için Intune uygulama koruma ilkelerini gerektirme ve ADAL SSO’yu etkinleştirme (isteğe bağlı)

Aşağıdakiler; otomatik bir APP-WE hizmet kaydı (buna bu bölümde **varsayılan kayıt** adı veriyoruz) için uygulama başlatırken kullanıcı istemi gerektirme, yalnızca Intune tarafından korunan kullanıcıların SDK ile tümleştirilmiş Android LOB uygulamanızı kullanmasına izin vermek için Intune uygulama koruma ilkelerini gerektirme hakkında bir kılavuzdur. Ayrıca SDK ile tümleştirilmiş Android LOB uygulamanız için SSO’yu nasıl etkinleştireceğinizi de açıklar. Bu, Intune özelliği olmayan kullanıcılar tarafından kullanılabilen mağaza uygulamalarında geçerli **değildir**.

> [!NOTE] 
> **Varsayılan kaydın** faydaları arasında, cihazdaki bir uygulama için APP-WE hizmetinden ilke almanın basitleştirilmiş bir yöntemi de bulunur.

### <a name="general-requirements"></a>Genel Gereksinimler
* Intune SDK’sı ekibi, uygulamanızın Uygulama Kimliğine gereksinim duyar. Bunu bulmanın bir yolu [Azure Portalı](https://portal.azure.com/)’nda, **Tüm Uygulamalar** altındaki **Uygulama Kimliği** sütunudur. Intune SDK’sı ekibine kolaylıkla ulaşmanın yolu msintuneappsdk@microsoft.com adresine e-posta göndermektir.
     
### <a name="working-with-the-intune-sdk"></a>Intune SDK’sı ile çalışma
Bu yönergeler, bir son kullanıcı cihazında Intune uygulama koruma ilkeleri gerektirmek isteyen tüm Android ve Xamarin uygulamalarına özgüdür.

1. [Android için Intune SDK’sı kılavuzu](https://docs.microsoft.com/intune/app-sdk-android#configure-azure-active-directory-authentication-library-adal)’nda açıklanan adımları kullanarak ADAL’ı yapılandırın.
> [!NOTE] 
> Uygulamanıza bağlanan “istemci kimliği” terimi, Azure portalındaki “uygulama kimliği” terimi ile aynı şeydir. 
* SSO’yu etkinleştirmek için gereken şey “Yaygın ADAL yapılandırması” #2’dir.

2. Bildirime şu değeri koyarak varsayılan kaydı etkinleştirin: ```xml <meta-data android:name="com.microsoft.intune.mam.DefaultMAMServiceEnrollment" android:value="true" />```
> [!NOTE] 
> Bu, uygulamadaki tek MAM-WE tümleştirmesi olmalıdır. Başka MAMEnrollmentManager API’lerini çağırma denemeleri olursa çakışmalar ortaya çıkabilir.

3. Bildirime şu değeri koyarak gereken MAM ilkesini etkinleştirin: ```xml <meta-data android:name="com.microsoft.intune.mam.MAMPolicyRequired" android:value="true" />```
> [!NOTE] 
> Böylece kullanıcı, cihaza Şirket Portalı’nı indirmeye ve bunu kullanmadan önce varsayılan kayıt akışını tamamlamaya zorlanır.

## <a name="limitations"></a>Sınırlamalar

### <a name="file-size-limitations"></a>Dosya Boyutu sınırlamaları

[ProGuard](http://proguard.sourceforge.net/) olmadan çalışan büyük kod tabanları için, Dalvik yürütülebilir dosya biçiminin sınırlamaları sorun yaratır. Özel olarak, aşağıdaki sınırlamalar ortaya çıkabilir:

1.  Alanlarda 65.000 sınırı.
2.  Metotlarda 65.000 sınırı.

### <a name="policy-enforcement-limitations"></a>İlke zorlama sınırlamaları

* **Ekran Yakalama**: SDK, Activity.onCreate öğesinden zaten geçmiş olan Etkinliklerde yeni bir ekran yakalama ayar değeri uygulayamaz. Bu durum, uygulama ekran görüntülerini devre dışı bırakacak şekilde yapılandırıldığı halde ekran görüntülerinin alınabildiği bir zaman dilimine yol açabilir.

* **İçerik Çözümleyicileri Kullanma**: “Aktarma veya alma” Intune ilkesi, başka bir uygulamadaki içerik sağlayıcısına erişmek için bir içerik çözümleyicisinin kullanılmasını tamamen veya kısmen engelleyebilir. Bu durum ContentResolver yöntemlerinin null döndürmesine veya bir hata değeri oluşturmasına neden olur (örneğin `openOutputStream` engellenirse `FileNotFoundException` oluşturur). Uygulama, içerik çözümleyicisi ile veri yazma hatasının bir ilkeden kaynaklanıp kaynaklanmadığını (veya ilke tarafından kaynaklanabileceğini) şu çağrıyı yaparak belirleyebilir:
    ```java
    MAMPolicyManager.getPolicy(currentActivity).getIsSaveToLocationAllowed(contentURI);
    ```
    veya ilişkili bir etkinlik yoksa şu çağrıyla belirleyebilir

    ```java
    MAMPolicyManager.getPolicy().getIsSaveToLocationAllowed(contentURI);
    ```

    İkinci durumda birden çok kimlikli uygulamalar, iş parçacığı kimliğini uygun şekilde ayarlamaya (veya `getPolicy` çağrısına bir açık kimlik geçirmeye) özen göstermelidir.
    
### <a name="exported-services"></a>Dışarı aktarılan hizmetler

 Intune Uygulama SDK’sına dahil edilen AndroidManifest.xml dosyası, **MAMNotificationReceiverService** öğesini içerir. Bu öğenin, Şirket Portalı’nın yönetilen bir uygulamaya bildirim göndermesine izin vermek üzere dışarı aktarılan bir hizmet olması gerekir. Hizmet, yalnızca Şirket Portalı’nın bildirim göndermesine izin verildiğinden emin olmak için çağıranı denetler.

### <a name="reflection-limitations"></a>Yansıma sınırlamaları
MAM tabanlı sınıflardan bazıları (örn. MAMActivity, MAMDocumentsProvider), yalnızca belirli API düzeylerinin üstünde var olan parametre veya dönüş türlerinin kullanıldığı yöntemler (özgün Android tabanlı sınıflar temelinde) kullanır. Bu nedenle, uygulama bileşenlerinin tüm yöntemlerini listelemek için yansıma kullanmak her zaman mümkün olmayabilir. Bu kısıtlama MAM ile sınırlı değildir; uygulamanın kendisi Android tabanlı sınıflardan bu yöntemleri uyguladığında da aynı kısıtlama geçerli olabilir.
## <a name="expectations-of-the-sdk-consumer"></a>SDK tüketicisinin beklentileri

İlkeleri zorunlu kılma işlemi sonucunda hata koşulları daha sık tetiklenebilir, ancak Intune SDK’sı, Android API’si tarafından sağlanan sözleşmeyi korur. Aşağıda belirtilen Android’e yönelik en iyi uygulamalar, hata olasılığını azaltır:

* Null döndürme olasılığı bulunan Android SDK işlevlerinin şu anda da null olma olasılığı daha yüksektir.  Sorunları en aza indirmek için null denetimlerinin doğru yerlerde olduğundan emin olun.

* Denetlenebilir özellikler MAM değiştirme API'leri aracılığıyla denetlenmelidir.

* Türetilen tüm işlevler üst sınıf sürümlerine çağrılmalıdır.

* Herhangi bir API'yi belirsiz bir şekilde kullanmaktan kaçının. Örneğin, requestCode denetlenmeden `Activity.startActivityForResult` kullanmak garip davranışlara neden olur.

## <a name="telemetry"></a>Telemetri

Android için Intune Uygulama SDK’sı, uygulamanızdan veri toplanmasını denetlemez. Şirket Portalı uygulaması, varsayılan olarak telemetri verilerini günlüğe kaydeder. Bu veriler Microsoft Intune’a gönderilir. Microsoft İlkesi uyarınca kişisel bilgileri toplamıyoruz.

> [!NOTE]
> Son kullanıcılar bu verileri göndermemeyi tercih ederse, Şirket Portalı uygulamasının Ayarlar bölümünde telemetriyi kapatmaları gerekir. Daha fazla bilgi için bkz. [Microsoft kullanım verilerini toplamayı devre dışı bırakma](https://docs.microsoft.com/intune-user-help/turn-off-microsoft-usage-data-collection-android). 

## <a name="recommended-android-best-practices"></a>Android için önerilen en iyi yöntemler

* Tüm kitaplık projeleri, mümkün olduğunda aynı android:package öğesini paylaşmalıdır. Bu durum düzensiz aralıklarla çalışma zamanında hataya neden olmaz; yalnızca derleme zamanıyla ilgili bir sorundur. Intune Uygulama SDK’sının daha yeni sürümleri, gecikmeyi kısmen ortadan kaldıracaktır.

* En yeni Android SDK’sı derleme araçlarını kullanın.

* Tüm gereksiz ve kullanılmayan kitaplıkları kaldırın (örneğin, android.support.v4)
