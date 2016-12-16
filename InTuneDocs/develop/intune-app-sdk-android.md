---
title: "Android için Microsoft Intune Uygulama SDK’sı geliştirici kılavuzu | Microsoft Docs"
description: 
keywords: SDK
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: oydang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 613e293d9bd853d6de7cdc0d753cc8473afc180b
ms.openlocfilehash: 7d6ac9de7dbfee4336121be69a38600448af2b68


---


# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a>Android için Microsoft Intune Uygulama SDK’sı geliştirici kılavuzu

> [!NOTE]
> Öncelikle, SDK’nın geçerli özelliklerini kapsayan ve desteklenen her platformda tümleştirmeye nasıl hazırlandığını açıklayan [Intune Uygulama SDK’sına genel bakış](intune-app-sdk.md) bölümünü okumanız önerilir.

Android için Microsoft Intune Uygulama SDK’sı, Intune mobil uygulama yönetimini (MAM) Android uygulamanıza eklemenizi sağlar. MAM özellikli uygulamalar Intune Uygulama SDK’sı ile tümleşiktir. Böylece, Intune uygulamayı etkin bir şekilde yönetirken BT yöneticilerinin mobil uygulamanıza ilke dağıtması mümkün olur.

## <a name="whats-in-the-sdk"></a>SDK’nın kapsamı

Android için Intune Uygulama SDK'sı dış bağımlılıkları olmayan standart bir Android kitaplığıdır. SDK şunlardan oluşur:  

* **Microsoft.Intune.MAM.SDK.jar**: Intune Şirket Portalı uygulamasında MAM özelliğini ve birlikte çalışabilirliği etkinleştirmek için gereken arabirimler. Uygulamalar bunu bir Android kitaplığı başvurusu olarak belirtmelidir.

* **Microsoft.Intune.MAM.SDK.Support.v4.jar**: Android v4 destek kitaplığını kullanan uygulamalarda MAM özelliğini etkinleştirmek için gereken arabirimler. Bu desteğe ihtiyaç duyan uygulamalar JAR dosyasına doğrudan başvurmalıdır.

* **Microsoft.Intune.MAM.SDK.Support.v7.jar**: Android v7 destek kitaplığını kullanan uygulamalarda MAM özelliğini etkinleştirmek için gereken arabirimler. Bu desteğe ihtiyaç duyan uygulamalar JAR dosyasına doğrudan başvurmalıdır.

* **Kaynak dizini**: SDK’nın bağımlı olduğu kaynaklar (dizeler gibi).

* **Microsoft.Intune.MAM.SDK.aar**: Support.V4 ve Support.V7 JAR dosyaları dışındaki SDK bileşenleri. Derleme sisteminiz AAR dosyalarını destekliyorsa bu dosya, tek bileşenlerin yerine kullanılabilir.

* **AndroidManifest.xml**: Ek giriş noktaları ve kitaplık gereksinimleri.

* **THIRDPARTYNOTICES.TXT**:  Uygulamanıza derlenecek üçüncü taraf ve/veya OSS kodunu tanıyan bir öznitelik bildirimi.

## <a name="requirements"></a>Gereksinimler

Intune Uygulama SDK'sı, derlenmiş bir Android projesidir. Sonuç olarak, uygulamanın en düşük veya hedef API sürümleri için kullandığı Android sürümünden büyük ölçüde etkilenmez. SDK; Android API 14 (Android 4.0+) ile Android API 24 arasındaki sürümleri destekler.

Android için Intune Uygulama SDK’sı, MAM ilkelerini etkinleştirmek için cihazda [Şirket Portalı](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) uygulamasının varlığına bağımlıdır. Cihaz kaydı olmadan MAM için kullanıcının Şirket Portalı uygulamasını kullanarak cihazını kaydetmesi gerekli *değildir*.


## <a name="how-the-intune-app-sdk-works"></a>Intune Uygulama SDK’sı nasıl çalışır?

###<a name="entry-points"></a>Giriş noktaları

Intune Uygulama SDK'sı, Intune uygulama yönetimi ilkelerini etkinleştirmek için bir uygulamanın kaynak kodunda değişiklik yapılmasını gerektirir. Bu işlem, Android temel sınıflarının, `MAM` olarak adlandırılan eşdeğer Intune temel sınıflarıyla değiştirilmesi yoluyla yapılır. SDK sınıfları, Android temel sınıfı ile uygulamanın söz konusu sınıftan türettiği sürüm arasında çalışır. Örnek olarak bir etkinlik kullanıldığında elde edilen devralma hiyerarşisi şunun gibi görünür: `Activity` > `MAMActivity` > `AppSpecificActivity`.

Örneğin, `AppSpecificActivity` üst öğesi ile etkileşim kurduğunda (örneğin `super.onCreate()` çağırdığında), `MAMActivity` üst sınıftır.

Tipik Android uygulamaları tek bir moda sahiptir ve sisteme [Context](https://developer.android.com/reference/android/content/Context.html) nesnesi aracılığıyla erişebilirler. Öte yandan Intune uygulama SDK'sının kullanıldığı uygulamalar çift moda sahiptir. Bu uygulamalar sisteme `Context` nesnesi üzerinden erişmeye devam eder. Kullanılan temel `Activity` baz alınarak, `Context` nesnesi Android tarafından sağlanır veya sistemin sınırlı bir görünümü ve Android tarafından sağlanan `Context` arasında çoğullanır.

Bir Android [giriş noktası](https://developer.android.com/guide/components/fundamentals.html) MAM eşdeğeri tarafından geçersiz kılındığında, giriş noktası yaşam döngüsünün MAM sürümü kullanılmalıdır (`MAMApplication` sınıfı hariç).

Örneğin, `MAMActivity`’i geçersiz kılıp `onCreate` çağırmak yerine `super.onCreate`’den türetilirken, `Activity`, `onMAMCreate`’i geçersiz kılmalı ve `super.onMAMCreate` çağırmalıdır. Bu, Intune’un `Activity` başlatılmasını (diğerlerinin yanı sıra) bazı durumlarda kısıtlar.


###<a name="sdk-permissions"></a>SDK izinleri

Intune uygulama SDK'sı, tümleştirildiği uygulamalarda üç [Android sistem izni](https://developer.android.com/guide/topics/security/permissions.html) gerektirir:

* `android.permission.GET_ACCOUNTS`  (gerekirse çalışma zamanında istenir)

* `android.permission.MANAGE_ACCOUNTS`

* `android.permission.USE_CREDENTIALS`

Bu izinler, Azure Active Directory Kimlik Doğrulama Kitaplığı ([ADAL](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-libraries/)) tarafından aracılık edilen kimlik doğrulaması gerçekleştirmek üzere istenir. Bu izinler uygulamaya sağlanmazsa veya kullanıcı tarafından kaldırılırsa, aracı (Şirket Portalı uygulaması) gerektiren kimlik doğrulama akışları devre dışı bırakılır.


###<a name="company-portal-app"></a>Şirket Portalı uygulaması

Şirket Portalı uygulaması neden gereklidir? Şirket Portalı uygulaması cihaza yüklenip kullanıcı için Intune hizmetinden bir uygulama kısıtlama ilkesi aldığında, SDK giriş noktaları zaman uyumsuz olarak başlatılır. Başlatma, yalnızca işlem en başta Android tarafından oluşturulduysa gereklidir. Başlatma sırasında Şirket Portalı uygulamasıyla bir bağlantı oluşturulur ve ilke uygulamadan alınır.  

> [!NOTE]
> Şirket Portalı uygulaması cihazda olmadığında, Intune özelliği etkinleştirilmiş uygulamanın davranışı değiştirilmez ve uygulama normal bir uygulama gibi davranır.


## <a name="how-to-integrate-with-the-intune-app-sdk"></a>Intune Uygulama SDK'sı ile tümleştirme

Daha önce belirtildiği gibi, SDK, uygulama yönetimi ilkelerini etkinleştirmek için bir uygulamanın kaynak kodunda değişiklik yapılmasını gerektirir. Uygulamanızda MAM özelliğini etkinleştirmek için gereken adımlar aşağıda verilmiştir.

### <a name="replace-classes-methods-and-activities-with-their-mam-equivalent-required"></a>Sınıfları, yöntemleri ve etkinlikleri MAM eşdeğerleriyle değiştirme (zorunlu)

Android temel sınıfları, ilgili MAM eşdeğerleriyle değiştirilmelidir. Bunu yapmak için aşağıdaki tabloda listelenen sınıfların tüm örneklerini bulun ve bunları Intune Uygulama SDK'sındaki eşdeğerleriyle değiştirin.

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
| android.app.PendingIntent | MAMPendingIntent* |
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
| android.provider.DocumentsProvider | MAMDocumentsProvider |
| android.preference.PreferenceActivity | MAMPreferenceActivity |


**Microsoft.Intune.MAM.SDK.Suppveyat.v4.jar**:

| Android sınıfı Intune MAM | Intune Uygulama SDK'sı karşılığı |
|--|--|
| android.support.v4.app.DialogFragment | MAMDialogFragment
| android.support.v4.app.FragmentActivity | MAMFragmentActivity
| android.support.v4.app.Fragment | MAMFragment
| android.support.v4.app.TaskStackBuilder | MAMTaskStackBuilder
| android.support.v4.content.FileProvider | MAMFileProvider

**Microsoft.Intune.MAM.SDK.Suppveyat.v7.jar**:

|Android sınıfı | Intune Uygulama SDK'sı karşılığı |
|--|--|
|android.support.v7.app.ActionBarActivity | MAMActionBarActivity |

>[!NOTE]
>Bir Android [giriş noktası](https://developer.android.com/guide/components/fundamentals.html), MAM eşdeğeri tarafından geçersiz kılındığında, giriş noktası yaşam döngüsünün MAM sürümü kullanılması gerektiğini unutmayın (`MAMApplication` sınıfı hariç).
>
>Örneğin, `MAMActivity`’i geçersiz kılıp `onCreate` çağırmak yerine `super.onCreate`’den türetilirken, `Activity`, `onMAMCreate`’i geçersiz kılmalı ve `super.onMAMCreate` çağırmalıdır. Bu, Intune’un `Activity` başlatılmasını (diğerlerinin yanı sıra) bazı durumlarda kısıtlar.

#### <a name="pendingintent-classes-and-renamed-methods"></a>PendingIntent sınıfları ve yeniden adlandırılan yöntemler

Bir MAM giriş noktasından türettikten sonra, `Context` kullanmak normalde yaptığınız gibi güvenlidir; örneğin `Activity` sınıflarını başlatıp `PackageManager` kullanmak.  

`PendingIntent` sınıfları bu kural için bir özel durumdur. Bu tür sınıflar çağırdığınızda, sınıf adını değiştirmeniz gerekir. Örneğin, `PendingIntent.get*` yerine `MAMPendingIntent.get*` yöntemini kullanmanız gerekir. Bundan sonra her zamanki gibi `PendingIntent` sonucunu kullanabilirsiniz.

Bazı durumlarda, Android sınıfında kullanılabilir olan bir metot, MAM değiştirme sınıfında kesin olarak işaretlenmiştir. Bu durumda, MAM değiştirme sınıfı benzer ada sahip olup (genellikle `MAM` son ekini alır) geçersiz kılmanız gereken bir yöntem sağlar. Örneğin, `ContentProvider.query`yerine `MAMContentProvider.queryMAM`. Java derleyicisi, MAM eşdeğeri yerine özgün metodun yanlışlıkla geçersiz kılınmasını önleyen kesin kısıtlamalar uygulamalıdır.

###<a name="enable-features-that-require-app-participation"></a>Uygulama katılımı gerektiren özellikleri etkinleştirme

SDK bazı ilkeleri kendi başına uygulayamaz. Uygulama bu özellikleri sağlamak için aşağıdaki `AppPolicy` arabiriminde bulabileceğiniz çeşitli API’ler kullanarak davranışını denetleyebilir.

```
/**
 * External facing application policies.
 */
public interface AppPolicy {

/**
 * Restrict where an app can save personal data.
 * <strong>This function is now deprecated. Please use {@link #getIsSaveToLocationAllowed(SaveLocation, String)} instead</strong>
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
 *           the username/email associated with the cloud service being saved to. Use null if a mapping between the AAD username and the cloud service username does not exist or the username is not known.
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
 * Return the policy in string format to the app.
 *  
 * @return The string representing the policy.
 */
String toString();


}

```

### <a name="enable-it-control-over-app-saving-behavior"></a>Uygulama kaydetme davranışı üzerinde BT denetimini etkinleştirme

Birçok uygulama, kullanıcının dosyaları yerel olarak veya bir bulut depolama hizmetine kaydetmesine olanak tanıyan özellikler uygular. Intune Uygulama SDK’sı, BT yöneticilerinin kuruluşlarında uygun gördüğü durumlarda ilke kısıtlamaları uygulayarak veri sızıntısına karşı koruma sağlamasına yardımcı olur.  BT’nin denetleyebileceği ilkelerden biri, kullanıcının “kişisel” ve yönetilmeyen bir veri deposuna kayıt yapıp yapamayacağıdır. Buna yerel konuma, bir SD karta veya üçüncü taraf yedekleme hizmetlerine kaydetme dahildir.

Özelliği etkinleştirmek için uygulama katılımı gereklidir. Uygulamanız kişisel konumlara veya bulut konumlarına doğrudan uygulama üzerinden kaydetmeye izin veriyorsa, BT yöneticisinin bir konuma kaydetmeye izin verilip verilmediğini denetleyebildiğinden emin olmak için bu özelliği uygulamanız gerekir.   

İlkenin uygulanıp uygulanmadığını belirlemek için uygulama aşağıdaki çağrıyı yapabilir. Bu çağrı, uygulamaya geçerli Intune yöneticisi ilkesinin kişisel bir depoya kaydetmeye izin verip vermediğini bildirir. Uygulama, kullanıcının uygulama üzerinden kullanabildiği kişisel veri depolama alanını bildiği için bundan sonra ilkeyi uygulayabilir.

```
MAMComponents.get(AppPolicy.class).getIsSaveToPersonalAllowed();
```

> [!NOTE]
> Cihaz veya uygulama bir Intune yönetim ilkesi altında olmasa bile `MAMComponents.get(AppPolicy.class)` her zaman null olmayan bir uygulama ilkesi döndürür.

### <a name="let-the-app-detect-if-a-pin-policy-is-required"></a>Uygulamanın, PIN ilkesinin gerekli olup olmadığını algılamasına izin verme

Bazı Intune uygulama kısıtlamaları için uygulamanızın Intune Uygulama SDK’sında işlev yinelememesi için bazı işlevlerini devre dışı bırakmasını isteyebilirsiniz. Örneğin uygulama kendi PIN kullanıcı deneyimine sahipse, SDK’nın kullanıcıdan PIN girmesini isteyecek şekilde ayarlaması durumunda bunu devre dışı bırakmak isteyebilir.

Bir Intune PIN ilkesinin uygulama başlatıldığında uygulama PIN’i gerektirecek şekilde ayarlanmış olup olmadığını belirlemek için uygulama şu çağrıyı yapabilir:

```
MAMComponents.get(AppPolicy.class).getIsPinRequired();
```

### <a name="register-for-notifications-from-the-sdk"></a>SDK’dan gelen bildirimlere kaydolma  

Intune Uygulama SDK'sı, uygulamanızın seçmeli silme gibi çeşitli ilkeler BT yöneticisi tarafından dağıtıldığında, bunların davranışını denetlemesine olanak tanır. BT yöneticisi böyle bir ilke dağıttığında, Intune hizmeti SDK’ya bir bildirim gönderir.

Uygulamanızın `MAMNotificationReceiver` sınıfını oluşturup `MAMNotificationReceiverRegistry` ile kaydederek SDK’dan gelen bildirimlere kaydolması gerekir. Bu işlem, şu örnekte gösterildiği gibi alıcı ve `App.onCreate` öğesinde istenen bildirim türü belirtilerek yapılır:

```
@Override
public void onCreate() {
    super.onCreate();
    MAMComponents.get(MAMNotificationReceiverRegistry.class)
.registerReceiver(
                new ToastNotificationReceiver(),
MAMNotificationType.WIPE_USER_DATA);
    }
```

`MAMNotificationReceiver`, Intune hizmetinden bildirimleri alır. SDK bazı bildirimleri doğrudan işler. Diğer bildirimler uygulamanın katılımını gerektirir.

Bir uygulamanın, bildirimden true veya false değeri döndürmesi *gerekir*. Bildirim sonucunda uygulamayı denediği bazı eylemler başarısız olmadığı sürece, uygulama her zaman true değerini döndürmelidir. Bu hata Intune hizmetine bildirilebilir. BT yöneticisi bir silme işlemi başlattıktan sonra uygulamanın kullanıcı verilerini silmekte başarısız olması rapor edilecek bir senaryoya örnek olarak verilebilir.

`MAMNotificationReceiver.onReceive` öğesinin engellenmesi güvenlidir; çünkü geri çağırma işlemi, kullanıcı arabirimi iş parçacığı üzerinde çalışmamaktadır.

Aşağıdaki `MAMNotificationReceiver` arabirimi SDK’da tanımlanmıştır:

```
/**
 * The SDK is signaling that a WG event has occurred.
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

###<a name="types-of-notifications"></a>Bildirim türleri

Aşağıdaki bildirimler uygulamaya gönderilir. Bazıları uygulama katılımı gerektirebilir.

* **`WIPE_USER_DATA`**: Bu bildirim bir `MAMUserNotification` sınıfında gönderilir. Bu bildirim alındığında uygulamanın, `MAMUserNotification` ile geçirilen “kurumsal” kimliğiyle ilişkili tüm verileri silmesi beklenir. Bu bildirim şu anda, Intune hizmeti kaydını silme sırasında gönderilmektedir. Kullanıcının birincil adı, genellikle kayıt işlemi sırasında belirtilir. Bu bildirime kaydolursanız, uygulamanız tüm kullanıcı verilerinin silindiğinden emin olmalıdır. Kaydolmazsanız, uygulama varsayılan seçmeli silme davranışını gerçekleştirir.

* **`WIPE_USER_AUXILIARY_DATA`**: Uygulamalar Intune Uygulama SDK’sının varsayılan seçmeli silme davranışını gerçekleştirmesini ve diğer yandan silme gerçekleştirildiğinde bazı yardımcı verilerin kaldırılmasını isterse bu bildirime kaydolabilir.  

* **`REFRESH_POLICY`**: Bu bildirim `MAMUserNotification` içinde gönderilir. Bu bildirim alındığında, önbelleğe alınan herhangi bir Intune ilkesinin geçersiz kılınması ve güncelleştirilmesi gerekir. Genellikle bu görevi SDK işler. Ancak ilke herhangi bir kalıcı yolla kullanılıyorsa, bu görevi uygulama işlemelidir.



### <a name="protection-of-backup-data"></a>Yedek verileri koruma

Android Marshmallow (API 23) sürümünden itibaren Android’deki bir uygulama, verileri iki yolla yedekleyebilir. Her bir seçenek uygulamanızda kullanılabilir ve Intune veri korumasının doğru bir şekilde uygulandığından emin olmak için farklı adımlar gerektirir. Yedekleme yöntemleri hakkında daha fazla bilgi için bkz. [Android API kılavuzu](http://developer.android.com/guide/topics/data/backup.html).

#### <a name="automatic-backup-for-apps"></a>Uygulamalar için otomatik yedekleme

Android, Android Marshmallow cihazlarındaki uygulamalara, uygulamanın hedef API’sinden bağımsız olarak [otomatik tam yedeklemeler](https://developer.android.com/guide/topics/data/autobackup.html) sunmaya başlamıştır. AndroidManifest.xml dosyanız içinde `android:allowBackup` öğesini açıkça false olarak ayarlarsanız, Android, uygulamanızı hiçbir zaman yedeklenmek üzere sıraya almaz ve "kurumsal" veriler uygulama içinde kalır. Bu durumda, başka bir eylem gerekmez.

`android:allowBackup` özniteliği, bildirim dosyasında `android:allowBackup` belirtilmemiş olsa bile varsayılan olarak true değeriyle ayarlanmıştır. Bu, tüm uygulama verilerinin otomatik olarak Google Drive hesabına yedeklendiği anlamına gelir ve bu da *veri sızıntısı riski* oluşturan bir varsayılan davranıştır. SDK, veri korumasının uygulandığından emin olmak için aşağıdaki değişiklikleri ister. Uygulamanızın Android Marshmallow cihazlarında çalışmasını istiyorsanız, müşteri verilerini düzgün bir şekilde korumak için bu yönergeleri izlemek önemlidir.  

Uygulamanızı yedeklemek için `MAMBackupAgent` veya `MAMBackupAgentHelper` kullanarak bir yedekleme aracısı yazmadıysanız, Otomatik Yedeklemenin uygulama verilerinizi karşıya nasıl yükleyeceğini göz önünde bulunmanız ve denetlemeniz gerekir. Intune, XML’de özel kurallar tanımlama yeteneği de dahil olmak üzere, Android’de kullanılabilen tüm [Otomatik Yedekleme özelliklerini](https://developer.android.com/guide/topics/data/autobackup.html) kullanmanıza izin verir. Ancak verilerinizin güvenliğini sağlamaya yardımcı olmak için aşağıdaki adımları izlemeniz gerekir:

1. Intune ilkesiyle uyumlu olan otomatik tam yedeklemelere izin vermek için varsayılan `MAMBackupAgent` kullanın. Bildiriminize `android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"` yerleştirin.

2. Uygulamanızın hangi tam yedekleme türünü (filtresiz, filtreli veya hiçbiri) almasını istediğinize karar verdiğinizde, `android:fullBackupContent` özniteliğini true, false veya uygulamanızda bir XML kaynağı olarak ayarlayın. `android:fullBackupContent` öğesine yerleştirdiklerinizi, `com.microsoft.intune.mam.FullBackupContent` adı verilen bir meta veri etiketine kopyalayın.

    Örneğin, uygulamanızın bir XML dosyasındaki özel kurallara göre tam yedeklemelere sahip olmasını istiyorsanız, bildiriminizdeki `com.microsoft.intune.mam.FullBackupContent` meta veri etiketi altında şu şekilde bir kaynak belirtin:
    ```
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```



#### <a name="keyvalue-backup"></a>Anahtar/değer yedeklemesi

Tüm API'lerde kullanılabilen anahtar/değer seçeneği `BackupAgentHelper` ve `BackupAgent` kullanır.

##### <a name="backupagenthelper"></a>BackupAgentHelper

`BackupAgentHelper` öğesinin uygulanması, hem yerel Android işlevselliği hem de MAM tümleştirmesi bakımından `BackupAgent` öğesinin uygulanmasından çok daha kolaydır. `BackupAgentHelper`, tüm dosyaları ve paylaşılan tercihleri sırasıyla `FileBackupHelper` veya `SharedPreferencesBackupHelper` öğesine kaydetmenize olanak tanır. Daha sonra bunlar, oluşturulduğu gibi `BackupAgentHelper` öğesine eklenir.

##### <a name="backupagent"></a>BackupAgent

`BackupAgent`, hangi verilerin yedeklendiği konusunda çok daha net olmanızı sağlar. Ancak, bu seçenekleri kullanırsanız Android yedekleme çerçevesinden yararlanamazsınız. Uygulama sorumluluğu size ait olduğundan, MAM aracılığıyla uygun veri koruması sağlamak için daha fazla adım gerekir. MAM tümleştirme işlerinin büyük bölümü geliştirici olarak size gönderildiğinden, MAM tümleştirmesi biraz daha karmaşıktır.

###### <a name="app-does-not-have-a-backup-agent"></a>Uygulama, bir yedekleme aracısına sahip değil

`android:allowBackup =true` olduğunda geliştirici seçenekleri bunlardır.

####### <a name="full-backup-according-to-a-configuration-file"></a>Bir yapılandırma dosyasına göre tam yedekleme

Bildiriminizdeki `com.microsoft.intune.mam.FullBackupContent` meta veri etiketi altında bir kaynak belirtin. Örneğin:     `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />`

`<application>` etiketine şu özniteliği ekleyin: `android:fullBackupContent="@xml/my_scheme"`; burada `my_scheme`, uygulamanızdaki bir XML kaynağıdır.

####### <a name="full-backup-without-exclusions"></a>Dışlamalar olmadan tam yedekleme

Bildirimde `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />` gibi bir etiket sağlayın.

Aşağıdaki özniteliği `<application>` etiketine ekleyin: `android:fullBackupContent="true"`.

###### <a name="app-has-a-backup-agent"></a>Uygulamanın yedekleme aracısı var

`BackupAgent` ve `BackupAgentHelper` için bu kılavuzun başlarındaki önerileri izleyin.

Android Marshmallow’da kolay yedekleme sağlayan `MAMDefaultFullBackupAgent` kullanmaya geçmeniz önerilir.

##### <a name="before-your-backup"></a>Yedeklemeden önce

Yedekleme işlemine başlamadan önce, yedeklemeyi planladığınız dosyaların veya veri arabelleklerinin yedeklenmesine izin verildiğini denetlemeniz gerekir. Bunu denetlemek için bir `isBackupAllowed` işlevini `MAMFileProtectionManager` ve `MAMDataProtectionManager` içinde size sunuyoruz. Dosya veya veri arabelleğinin yedeklenmesine izin verilmiyorsa, bunu yedekleme işleminizde kullanmaya çalışmamanız gerekir.

Yedeklemenin belirli bir noktasında, 1. adımda denetlediğiniz dosyaların kimliklerini yedeklemek isterseniz, verileri ayıklamayı planladığınız dosyalarla birlikte `backupMAMFileIdentity(BackupDataOutput data, File … files)` öğesini çağırmanız gerekir. Bu, otomatik olarak yeni yedekleme varlıkları oluşturur ve bunları sizin için `BackupDataOutput` öğesine yazar. Bu varlıklar geri yükleme sonrasında otomatik olarak kullanılır.

#### <a name="azure-directory-authentication-library-setup"></a>Azure Directory Kimlik Doğrulama Kitaplığını ayarlama  

SDK, kimlik doğrulama ve koşullu başlatma senaryoları için ADAL’a bağlıdır. Bu senaryolar, uygulamaların bir miktar Azure Active Directory (Azure AD) yapılandırmasına sahip olmasını gerektirir. Yapılandırma değerleri, `AndroidManifest` meta verileri üzerinden SDK’ya iletilir.

Uygulamanızı ayarlamak ve uygun kimlik doğrulamasını sağlamak için aşağıdakini `AndroidManifest` içindeki uygulama düğümüne ekleyin. Bu yapılandırmaların bir kısmı yalnızca uygulamanızın genel olarak ADAL kimlik doğrulaması kullanması durumunda gereklidir. Bu durumda, uygulamanızın Azure AD’ye kaydolduğunda kullandığı belirli değerlere ihtiyacınız olur. Bu, Azure AD’nin iki ayrı kayıt değerini (biri uygulamadan, biri SDK’dan) tanıması nedeniyle kullanıcıdan kimlik doğrulamasının iki kez istenmesini önler.

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

GUID'lerin önünde veya sonunda süslü ayraç olması beklenmez.

##### <a name="common-adal-configurations"></a>Yaygın ADAL yapılandırmaları

Daha önce açıklanan değerler için yaygın yapılandırma aşağıda verilmiştir.

###### <a name="app-does-not-integrate-adal"></a>Uygulama ADAL ile tümleştirilmezse

* Yetkili, Azure AD hesaplarının ayarlanmış olduğu istenen ortama ayarlanmalıdır.

* SkipBroker true olarak ayarlanmalıdır.

###### <a name="app-integrates-adal"></a>Uygulama ADAL ile tümleştirilirse

* Yetkili, Azure AD hesaplarının ayarlanmış olduğu istenen ortama ayarlanmalıdır.

* İstemci kimliği, uygulamanın istemci kimliğine ayarlanmalıdır.

* `NonBrokerRedirectURI` , uygulama için geçerli bir yeniden yönlendirme URI’sine ayarlanmalıdır. Veya `urn:ietf:wg:oauth:2.0:oob` geçerli bir Azure AD yeniden yönlendirme URI'si olarak ayarlanmalıdır.

* SkipBroker false (veya absent) olarak ayarlanmalıdır.

* Azure AD, aracı yeniden yönlendirme URI'sini kabul edecek şekilde ayarlanmalıdır.

###### <a name="app-integrates-adal-but-does-not-support-the-azure-ad-authenticator-app"></a>Uygulama, ADAL ile tümleştirilir ancak Azure AD Authenticator uygulamasını desteklemez

* Yetkili, Azure AD hesaplarının ayarlanmış olduğu istenen ortama ayarlanmalıdır.

* İstemci kimliği, uygulamanın istemci kimliğine ayarlanmalıdır.

* `NonBrokerRedirectURI` , uygulama için geçerli bir yeniden yönlendirme URI’sine ayarlanmalıdır. Veya `urn:ietf:wg:oauth:2.0:oob` geçerli bir Azure AD yeniden yönlendirme URI'si olarak ayarlanmalıdır.

#### <a name="logging-in-the-sdk"></a>SDK’da günlüğe kaydetme

Günlüğe kaydetme, `java.util.logging` çerçevesi aracılığıyla yapılır. Günlükleri almak için [Java teknik kılavuzu](http://docs.oracle.com/javase/6/docs/technotes/guides/logging/overview.html). Uygulamaya bağlı olarak, `App.onCreate` genellikle günlüğe kaydetmeyi başlatmak için en iyi yerdir. Unutmayın; günlük iletileri sınıf adına göre anahtarlanır ve sınıf adı gizlenmiş olabilir.

###<a name="multi-identity"></a>Çoklu kimlik

Intune Uygulama SDK’sı varsayılan olarak, ilkeyi uygulamaya bir bütün olarak uygular. Çoklu kimlik, bir ilkeyi her bir kimlik düzeyinde uygulamak için etkinleştirebileceğiniz bir MAM özelliğidir. Bu, diğer MAM özelliklerine kıyasla önemli oranda daha fazla uygulama katılımı gerektirir. Uygulama etkin kimliği değiştirmeyi amaçladığında, bunu uygulama SDK’sına bildirmesi gerekir. Ayrıca bir kimlik değişikliği gerektiğinde SDK bunu uygulamaya bildirmelidir.

Şu anda yalnızca tek bir yönetilen kimlik desteklenir. Kullanıcı cihaz veya uygulamayı kaydettikten sonra, SDK bu kimliği kullanır ve bunu birincil yönetilen kimlik olarak kabul eder. Uygulamadaki diğer kullanıcılar kısıtlanmamış ilke ayarlarıyla yönetilmiyor olarak kabul edilir.

Bir kimliğin yalnızca dizi olarak tanımlandığını aklınızda bulundurun. Kimlikler büyük/küçük harfe duyarlıdır. SDK’ya kimlik için yapılan istekler, kimlik ayarlandığı sırada kullanılan özgün büyük/küçük harf dizimiyle aynı olmadığı sürece sonuç getirmeyebilir.

####<a name="enabling-multi-identity"></a>Çoklu kimliği etkinleştirme

Varsayılan olarak, tüm uygulamalar tek kimlikli uygulamalar olarak değerlendirilir. Bir uygulama, çoklu kimliği fark ettiğini Android bildirimine aşağıdaki meta verileri yerleştirerek bildirir.

```
<meta-data
            android:name="com.microsoft.intune.mam.MAMMultiIdentity"
            android:value="true" />
```
####<a name="setting-the-identity"></a>Kimliği ayarlama

Uygulamanın kimliğini aşağıdaki düzeylerde ayarlayabilirsiniz:

1. İşlem düzeyi

2. Bağlam (genellikle `Activity`) düzeyi

3. İş parçacığı düzeyi

İş parçacığı düzeyinde ayarlanmış bir kimlik, `Context` düzeyinde ayarlanmış bir kimliğin; bağlam düzeyinde ayarlanmış bir kimlikse işlem düzeyinde ayarlanmış bir kimliğin yerini alır. `Context` üzerinde ayarlanmış bir kimlik yalnızca uygun olduğunda kullanılır. Örneğin dosya GÇ görevlerinde ilişkili bir `Context` bulunmaz. Aşağıdaki `MAMPolicyManager` yöntemlerini kimlik ayarlamak ve önceden ayarlanan kimlik değerlerini almak için kullanılabilirsiniz.

```
public static void setUIPolicyIdentity(final Context context, final String identity, final MAMSetUIIdentityCallback mamSetUIIdentityCallback);

public static String getUIPolicyIdentity(final Context context);

public static MAMIdentitySwitchResult setProcessIdentity(final String identity);

public static String getProcessIdentity();

public static MAMIdentitySwitchResult setCurrentThreadIdentity(final String identity);

public static String getCurrentThreadIdentity();

/**
 * Get the currently applicable app policy. Same as MAMComponents.get(AppPolicy.class). This method does
    not take the context identity into account.
 */
public static AppPolicy getPolicy();

/**
 * Get the currently applicable app policy, taking the context
 * identity into account.
 */
public static AppPolicy getPolicy(final Context context);


public static AppPolicy getPolicyForIdentity(final String identity);

public static boolean getIsIdentityManaged(final String identity);

```
Bir uygulamanın kimliğini null olarak ayarlayarak da temizleyebilirsiniz. Boş dize, hiçbir zaman kısıtlamalara sahip olmayacak bir kimlik olarak kullanılabilir. Tüm kimlik ayarlama yöntemleri, sonuç değerlerini ``` MAMIdentitySwitchResult``` aracılığıyla geri rapor eder. Dört değer döndürülebilir:

* **BAŞARILI**: Kimlik değişikliği başarılı oldu.

* **İZİN VERİLMİYOR**: Kimlik değişikliğine izin verilmiyor. Bu, kayıtlı kullanıcı olarak aynı şirkete ait farklı bir kurumsal kullanıcıya geçiş yapmak istenirse meydana gelir. Geçerli iş parçacığı üzerinde farklı bir kimlik ayarlıyken UI (`Context`) kimliğini ayarlamak denenirse de gerçekleşir.

* **İPTAL EDİLDİ**: Kullanıcı, genellikle PIN/auth istemi üzerindeki geri tuşunu seçerek, kimlik değişikliğini iptal etmiştir.

* **BAŞARISIZ**: Kimlik değişikliği belirlenemeyen bir nedenden dolayı başarısız oldu.

Bir `Context` kimliği ayarlamak söz konusu olduğunda, sonuç zaman uyumsuz olarak bildirilir. `Context`, bir `Activity` sınıfıysa, koşullu başlatma sonrasına kadar kimlik değişikliğinin başarılı olup olmadığı bilinmez. Koşullu başlatma, kullanıcının bir PIN veya tam şirket kimlik bilgilerini girmesini gerektirebilir. Bu parametre için null değeri geçirmeye izin verilse de, uygulamanın bu sonucu alması için ```MAMSetUIIdentityCallback``` uygulaması gerekir.

```
public interface MAMSetUIIdentityCallback {
    void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult);
}
```

Ayrıca bir etkinliğin kimliğini, ```MAMPolicyManager.setUIPolicyIdentity``` çağırmak yerine doğrudan `MAMActivity` yöntemiyle ayarlayabilirsiniz. Aşağıdaki yöntemi kullanarak bunu yapabilirsiniz:

 ```public final void switchMAMIdentity(final String newIdentity);```

Uygulamalar ayrıca, etkinliğin kimliğini değiştirme denemelerinin sonucu hakkında bildirim almak için `MAMActivity` üzerinde bir yöntemi geçersiz kılabilir.

```public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);```

> [!NOTE]
> Kimliği değiştirmek için etkinliğin yeniden oluşturulması gerekebilir. Bu durumda, ```onSwitchMAMIdentityComplete``` geri çağırma yeni etkinlik örneğine gönderilir.


####<a name="implicit-identity-changes"></a>Örtük kimlik değişiklikleri

Uygulamanın kimlik ayarlayabilme özelliğine ek olarak, bir iş parçacığı veya bir bağlamın kimliği başka bir MAM özellikli uygulamadan veri girişine göre değişebilir. Örneğin bir etkinlik başka bir MAM uygulamasından gönderilen bir `Intent` sınıfından başlatılmışsa, etkinliğin kimliği `Intent` sınıfının gönderildiği noktada diğer uygulamadaki etkin kimliğe göre ayarlanır.

Hizmetler için iş parçacığının kimliği bir `onStart` veya `onBind` çağrısının süresine benzer şekilde ayarlanır. `Binder` öğesinden döndürülen `onBind` içine yapılan çağrılar iş parçacığı kimliğini de geçici olarak ayarlar. ```ContentProvider``` içine yapılan çağrılar da benzer şekilde iş parçacığı kimliğini süreleri boyunca ayarlar.

Ayrıca, bir etkinlikle kullanıcı etkileşimi bir örtük kimlik anahtarına neden olabilir. Örneğin, ```Resume``` sırasında bir kullanıcının bir yetkilendirme istemini iptal etmesi, boş bir kimliğe örtük anahtar ile sonuçlanır.
Uygulama, bu değişiklikleri algılama ve bazı durumlarda gerekirse bunları yasaklayabilme fırsatına sahiptir. ```MAMService``` ve ```MAMContentProvider```, alt sınıfların geçersiz kılabileceği aşağıdaki yöntemi kullanıma sunar:

```
public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchResultCallback callback);
```
```MAMActivity``` söz konusuysa, yöntemde ek bir parametre olur:
```
public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchReason reason,
    final AppIdentitySwitchResultCallback callback);
```
```AppIdentitySwitchReason``` bölümü örtük anahtarın kaynağını yakalar. ```CREATE```, ```RESUME_CANCELLED``` ve ```NEW_INTENT``` değerlerini kabul edebilir.  Bir etkinliği sürdürmek PIN, kimlik doğrulama veya başka bir uyumluluk UI’ının görüntülenmesine neden olduğunda ve kullanıcı bu UI’ı genellikle geri tuşuna basarak iptal etmeyi denediğinde ```RESUME_CANCELLED``` nedeni kullanılır.
```AppIdentitySwitchResultCallback``` aşağıdaki şekildedir:
```
public interface AppIdentitySwitchResultCallback {
    /**
     * @param result
     *            whether the identity switch can proceed.
     */
    void reportIdentitySwitchResult(AppIdentitySwitchResult result);
}
```
```AppIdentitySwitchResult```, ```SUCCESS``` ya da ```FAILURE``` olur.

```onMAMIdentitySwitchRequired``` yöntemi, ```MAMService.onMAMBind``` öğesinden döndürülen bir `Binder` sınıfı aracılığıyla yapılanlar dışındaki tüm örtük kimlik değişiklikleri için çağrılır. Varsayılan ```onMAMIdentitySwitchRequired``` uygulaması, neden ```RESUME_CANCELLED``` olduğunda hemen ```reportIdentitySwitchResult(FAILURE)``` çağırır ve diğer tüm durumlarda ```reportIdentitySwitchResult(SUCCESS)``` çağırır.

Büyük olasılıkla, çoğu uygulamanın bir kimlik değişimini farklı bir şekilde engellemesi veya geciktirmesi gerekmez. Ancak uygulamanın bunu yapması gerekiyorsa, aşağıdaki noktaları göz önünde bulundurun:

* Bir kimlik değişimi engellenirse, sonuç ```Receive``` paylaşım ayarları veri girişini yasakladığında olan ile aynıdır.

* Bir hizmet ana iş parçacığı üzerinde çalışıyorsa, ```reportIdentitySwitchResult``` öğesinin zaman uyumlu olarak çağrılması *gerekir*, yoksa UI iş parçacığı kapanır.

* ```Activity``` oluşturmak için ```onMAMCreate``` öğesinden önce ```onMAMIdentitySwitchRequired``` çağrılır. Kimlik anahtarına izin verilip verilmeyeceğini denetlemek için uygulamanın UI göstermesi gerekiyorsa, bu UI farklı bir etkinlik kullanılarak gösterilmelidir.

* Bir ```Activity``` içinde, ```RESUME_CANCELLED``` ile eşit bir nedenle boş kimliğe anahtar istenirse, uygulamanın, bu kimlik değişimi ile tutarlı verileri görüntülemek için sürdürülen etkinliği değiştirmesi gerekir. Bu mümkün değilse, uygulama değişimi reddeder. Ve kullanıcıdan bir kez daha sürdürülen kimlik ilkesine uyması istenir (örneğin, PIN girişi ekranı gösterilerek).

> [!NOTE]
> Çok kimlikli bir uygulama, yönetilen ve yönetilmeyen uygulamalardan gelen verileri her zaman alır. Yönetilen kimliklerden alınan verileri yönetilen kabul etmek uygulamanın sorumluluğudur. İstenen kimlik yönetilen ```(MAMPolicyManager.getIsIdentityManaged)``` ise, ancak uygulama bu hesabı kullanamıyorsa (örneğin e-posta hesapları gibi hesapların ilk olarak uygulamada ayarlanması gerektiği için) kimlik değişimi reddedilir.

###<a name="file-protection"></a>Dosya koruması

Her dosyanın, oluşturulduğu sırada iş parçacığı ve işlem kimliğine dayalı olarak kendisiyle ilişkilendirilmiş bir kimliği vardır. Bu kimlik hem dosya şifreleme hem de seçmeli silme için kullanılır. Yalnızca şifreleme gerektiren ilkeye sahip dosyalar şifrelenir. SDK'nın varsayılan seçmeli silme işlemi, yalnızca silme işleminin istendiği kimlikle ilişkilendirilmiş dosyaları siler. Uygulama, ```MAMFileProtectionManager``` kullanarak bir dosyanın kimliğini sorgulayabilir veya değiştirebilir.
```
public final class MAMFileProtectionManager {

    /**
     * Protect a file. This will synchronously trigger whatever protection is required for the file, and will tag the file for
     * future protection changes.
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
     * Get the protection info on a file.
     *
     * @param file
     *            File or directory to get information on.
     * @return File protection info, or null if there is no protection info.
     * @throws IOException
     *             If the file cannot be read or opened.
     */
    public static MAMFileProtectionInfo getProtectionInfo(final File file) throws IOException;
}

public interface MAMFileProtectionInfo {
String getIdentity();
}
```

> [!NOTE]
> Dosya kimliği etiketlemesi çevrimdışı moda karşı hassastır. Aşağıdaki noktaları dikkate alın:
> * Şirket Portalı uygulaması yüklü değilse, dosyalar kimlik etiketli olamaz.
>
> * Şirket Portalı uygulaması yüklü, ancak uygulamada kullanılan bir ilke yoksa, dosyalar güvenilir bir şekilde kimlik etiketli yapılamaz.
>
> * Dosya kimliği etiketleme kullanılabilir olduğunda, uygulama daha önceden tek kimlikli yönetilen uygulama olarak yüklenmediyse, önceden oluşturulan tüm dosyalar kişisel kabul edilir (boş dize kimliğine ait olarak). Bu durumda, bunların kayıtlı kullanıcıya ait olduğu kabul edilir.

####<a name="data-protection"></a>Veri koruma

Çoklu kimliklere ait bir dosyayı etiketlemek mümkün değildir. Aynı dosyada farklı kullanıcılara ait verileri depolaması gereken uygulamalar bunu, ```MAMDataProtectionManager``` tarafından sağlanan özellikleri kullanarak yapabilir. Bu, uygulamanın veri şifrelemesine ve belirli bir kullanıcıya bağlamasına olanak tanır. Şifrelenmiş veriler, bir dosyadaki diske depolamak için uygundur. Kimlikle ilişkili verileri sorgulayabilir ve verilerin şifresini daha sonra kaldırabilirsiniz.

```
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
###<a name="content-providers"></a>İçerik sağlayıcıları

Uygulama bir ```ContentProvider``` aracılığıyla ```ParcelFileDescriptor``` dışında potansiyel kurumsal veriler sağlıyorsa, uygulamanın ```MAMContentProvider``` yöntemini çağırması ve ```isProvideContentAllowed(String)``` içerik için ```UPN``` sahibi geçmesi gerekir. Bu işlev false döndürürse, içeriği çağırana döndürülemez. İçerik sağlayıcısı aracılığıyla döndürülen dosya tanımlayıcıları dosya kimliğine göre otomatik olarak işlenir.

###<a name="selective-wipe"></a>Seçmeli temizleme

Bir uygulama ```WIPE_USER_DATA``` bildirimine kaydolursa, SDK varsayılan seçmeli silme davranışından faydalanamaz. Çoklu kimliği fark eden uygulamalarda, MAM varsayılan seçmeli silme yalnızca silinecek kimlikle eşleşen dosyaları sileceğinden bu durum daha önemli olabilir.

Çoklu kimliği fark eden bir uygulama oluşturuyorsanız, ```WIPE_USER_AUXILIARY_DATA``` için kaydedebilirsiniz. Bu bildirim, SDK varsayılan silme davranışından yararlanmanızı sağlar. Bu bildirim, SDK varsayılan seçmeli silme gerçekleştirmenizden hemen önce gönderilir. Bir uygulamanın hiçbir zaman hem ```WIPE_USER_DATA``` hem de ```WIPE_USER_AUXILIARY_DATA``` kaydı olmaması gerektiğini unutmayın.

### <a name="known-platform-limitations"></a>Bilinen platform sınırlamaları

#### <a name="file-size-limitations"></a>Dosya boyutu sınırlamaları

Android’de, Dalvik yürütülebilir dosya biçimine ilişkin sınırlamalar, ProGuard olmadan çalışan büyük kod temelleri için sorun oluşturabilir. Özellikle aşağıdaki sınırlamalar görülebilir:

* Alanlarda 65.000 sınırı

* Yöntemlerde 65.000 sınırı

Çok sayıda proje dahil ettiğinizde, her `android:package` bir R kopyası alır. Bu, kitaplık eklendikçe alan sayısını önemli ölçüde artırır. Aşağıdaki öneriler bu sınırlamaları azaltmaya yardımcı olabilir:

* Tüm kitaplık projeleri, mümkün olduğunda aynı `android:package` öğesini paylaşmalıdır. Yalnızca derleme zamanıyla ilgili bir sorun olduğundan, bu durum alanda düzensiz aralıklarla hataya neden olmaz. Ayrıca, Android SDK'sının daha yeni sürümleri bazı artıklıkları kaldırmak için DEX dosyalarını önceden işler. Bunun yapılması, alanlarla uzaklığı daha da azaltır.

* Mevcut olan en yeni Android SDK derleme araçlarını kullanın.

* Tüm gereksiz ve kullanılmayan kitaplıkları kaldırın (örneğin, `android.support.v4`).

#### <a name="policy-enforcement-limitations"></a>İlke zorlama sınırlamaları

**Ekran yakalama**: SDK, `Activity.onCreate` öğesinden zaten geçmiş olan `Activity` sınıflarında yeni bir ekran yakalama ayar değeri uygulayamaz. Bu durum, uygulama ekran görüntülerini devre dışı bırakacak şekilde ayarlandığı halde ekran görüntülerinin alınabildiği bir zaman dilimine yol açabilir.

**İçerik çözümleyicileri**: Aktarım veya alma ilkesi, başka bir uygulamadaki içerik sağlayıcısına erişmek için bir içerik çözümleyicisinin kullanılmasını tamamen veya kısmen engelleyebilir. Bu, `ContentResolver` yöntemlerinin null döndürmesine veya bir hata değeri vermesine neden olur. (Örneğin, engellemişse `openOutputStream`, `FileNotFoundException` değeri verir.) Uygulama, bir ilkenin bir içerik çözümleyicisi üzerinden veri yazma hatasına neden olup olmadığını (veya olup olmayacağını) denetlemek için bu çağrıyı yapabilir:

    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI)

**Dışarı aktarılan hizmetler**: Intune Uygulama SDK’sına dahil edilen `AndroidManifest.xml` dosyası, `MAMNotificationReceiverService` öğesini içerir. Bu öğenin, Şirket Portalı uygulamasını kullanan bir uygulamaya bildirim göndermesine izin vermek üzere dışarı aktarılan bir hizmet olması gerekir. Hizmet, yalnızca Şirket Portalı uygulamasının bildirim göndermesine izin verildiğinden emin olmak için çağıranı denetler.

### <a name="android-best-practices"></a>Android en iyi uygulamalar

İlkeleri zorunlu kılma işlemi sonucunda hata koşulları daha sık tetiklenebilir, ancak Intune SDK’sı, Android API’si tarafından sağlanan sözleşmeyi korur. Aşağıda belirtilen Android’e yönelik en iyi uygulamalar, hata olasılığını azaltır:

* Null döndürme olasılığı bulunan Android SDK işlevlerinin şu anda da null olma olasılığı daha yüksektir. Sorunları en aza indirmek için null denetimlerinin doğru yerlerde olduğundan emin olun.

* Denetleyebileceğiniz özellikler için kendi SDK API'lerini kullanın.

* Türetilen tüm işlevler üst sınıf sürümlerine çağrılmalıdır.

* Herhangi bir API'yi belirsiz bir şekilde kullanmaktan kaçının. Örneğin, `requestCode` denetlenmeden `Activity.startActivityForResult/onActivityResult` kullanmak garip davranışlara neden olur.



<!--HONumber=Dec16_HO2-->


