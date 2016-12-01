---
title: "Android için Microsoft Intune Uygulama SDK’sı Geliştirici Kılavuzu | Microsoft Intune"
description: 
keywords: SDK
author: Msmbaldwin
manager: jeffgilb
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: edbc701effb3817c2f9a160f05e7b5bc8ad0070e
ms.openlocfilehash: ee3a668a5415d14eb82e64e6bb16d9621bb13b57


---


# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a>Android için Microsoft Intune Uygulama SDK’sı Geliştirici Kılavuzu

> [!NOTE]
> Öncelikle, SDK’nın geçerli özelliklerini kapsayan ve desteklenen her platformda tümleştirmeye nasıl hazırlandığını açıklayan [Intune Uygulama SDK’sına genel bakış](intune-app-sdk.md) bölümünü okumanız önerilir. 

Android için Microsoft Intune Uygulama SDK’sı, Intune Mobil Uygulama Yönetimi’ni (MAM) Android uygulamanıza eklemenizi sağlar. MAM özellikli bir uygulama, Intune Uygulama SDK'sı ile tümleşiktir ve uygulama Intune tarafından etkin bir şekilde yönetildiğinde, BT yöneticilerinin ilkeleri mobil uygulamanıza dağıtmasını sağlar.

# <a name="whats-in-the-sdk"></a>SDK’nın kapsamı 

Android için Intune Uygulama SDK'sı dış bağımlılıkları olmayan standart bir Android kitaplığıdır. SDK şunlardan oluşur:  

* **Microsoft.Intune.MAM.SDK.jar**: Intune Şirket Portalı uygulamasında MAM özelliğini ve birlikte çalışabilirliği etkinleştirmek için gereken arabirimler. Uygulamalar bunu bir Android kitaplığı başvurusu olarak belirtmelidir.

* **Microsoft.Intune.MAM.SDK.Support.v4.jar**: Android v4 destek kitaplığından yararlanan uygulamalarda MAM özelliğini etkinleştirmek için gereken arabirimler.  Bu desteğe ihtiyaç duyan uygulamalar jar dosyasına doğrudan başvurmalıdır. 

* **Microsoft.Intune.MAM.SDK.Support.v7.jar**: Android v7 destek kitaplığından yararlanan uygulamalarda MAM özelliğini etkinleştirmek için gereken arabirimler. Bu desteğe ihtiyaç duyan uygulamalar jar dosyasına doğrudan başvurmalıdır.

* **Kaynak dizini**: SDK’nın bağımlı olduğu kaynaklar (dizeler gibi). 

* **Microsoft.Intune.MAM.SDK.aar**: Support.V4 ve Support.V7 jar dosyaları dışındaki SDK bileşenleri. Derleme sisteminiz AAR dosyalarını destekliyorsa bu dosya, tek bileşenlerin yerine kullanılabilir.

* **AndroidManifest.xml**: Ek giriş noktaları ve kitaplık gereksinimleri. 

* **THIRDPARTYNOTICES.TXT**:  Uygulamanıza derlenecek üçüncü taraf ve/veya OSS kodunu tanıyan bir öznitelik bildirimi. 

# <a name="requirements"></a>Gereksinimler 

Intune Uygulama SDK'sı, derlenmiş bir Android projesidir. Sonuç olarak, uygulamanın en düşük veya hedef API sürümleri için kullandığı Android sürümünden büyük ölçüde bağımsızdır. SDK; Android API 14 (Android 4.0+) ile Android API 24 arasındaki sürümleri destekler. 

Android için Intune Uygulama SDK’sı, MAM ilkelerini etkinleştirmek için cihazda [Şirket Portalı](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) uygulamasının varlığına bağımlıdır. Cihaz kayıt olmadan MAM için kullanıcının Şirket Portalı’nı kullanarak cihazını kaydetmesi gerekli **değildir**.


# <a name="how-the-intune-app-sdk-works"></a>Intune Uygulama SDK’sı nasıl çalışır? 

##<a name="entry-points"></a>Giriş Noktaları

Intune Uygulama SDK'sı, Intune uygulama yönetimi ilkelerini etkinleştirmek için bir uygulamanın kaynak kodunda değişiklik yapılmasını gerektirir. Bu işlem, Android temel sınıflarının, **MAM** olarak adlandırılan eşdeğer Intune temel sınıflarıyla değiştirilmesi yoluyla yapılır. SDK sınıfları, Android temel sınıfı ile uygulamanın söz konusu sınıftan türettiği sürüm arasında çalışır.  Örnek olarak bir etkinlik kullanıldığında elde edilen devralma hiyerarşisi şunun gibi görünür: Activity > MAMActivity > AppSpecificActivity.

Örneğin, **AppSpecificActivity** üst grubuyla etkileşim kurduğunda (yani çağırdığında `super.onCreate()`), **MAMActivity** üst sınıftır. 

Tipik Android uygulamaları tek bir moda sahiptir ve sisteme [Context](https://developer.android.com/reference/android/content/Context.html) nesnesi aracılığıyla erişebilirler.  Öte yandan Intune uygulama SDK'sının kullanıldığı uygulamalar çift moda sahiptir. Bu uygulamalar sisteme Context nesnesi aracılığıyla erişmesine karşın, kullanılan temel Etkinliğe bağlı olarak Context nesnesi ya Android tarafından sağlanır ya da sistemin kısıtlanmış bir görünümü ile Android tarafından sağlanan Context nesnesi arasında çoğullanır.

MAM eşdeğeri tarafından geçersiz kılınmış bir Android [giriş noktası](https://developer.android.com/guide/components/fundamentals.html) kullanılırken, giriş noktası yaşam döngüsünün MAM sürümü kullanılmalıdır (**MAMApplication** sınıfı hariç).

Örneğin, **MAMActivity**’den türetilirken `onCreate`’ü geçersiz kılıp `super.onCreate` çağırmak yerine, Etkinlik, `onMAMCreate`’i geçersiz kılmalı ve `super.onMAMCreate`’yı çağırmalıdır. Bunun yapılması, Etkinlik başlatma işleminin (diğerlerinin arasında) belirli durumlarla Intune tarafından kısıtlanmasını sağlar. 


##<a name="sdk-permissions"></a>SDK İzinleri

Intune uygulama SDK'sı, tümleştirildiği uygulamalarda üç [Android sistem izni](https://developer.android.com/guide/topics/security/permissions.html) gerektirir:

* `android.permission.GET_ACCOUNTS`  [gerekirse çalışma zamanında istenir]
* `android.permission.MANAGE_ACCOUNTS`
* `android.permission.USE_CREDENTIALS`

Bu izinler, Azure Active Directory Kimlik Doğrulaması Kitaplığı ([ADAL](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-libraries/)) tarafından aracılık edilen kimlik doğrulaması gerçekleştirmek üzere istenir. Bu izinler uygulamaya sağlanmazsa veya kullanıcı tarafından kaldırılırsa, aracı (Şirket Portalı uygulaması) gerektiren kimlik doğrulama akışları devre dışı bırakılır.


##<a name="company-portal"></a>Şirket Portalı

Şirket Portalı uygulaması neden gereklidir? Şirket Portalı cihaza yüklenip kullanıcı için Intune hizmetinden uygulama kısıtlama ilkesi aldığında, SDK giriş noktaları zaman uyumsuz olarak başlatılır. Başlatma işlemi yalnızca, işlem başlangıçta Android tarafından oluşturulduğunda gereklidir. Başlatma sırasında Şirket Portalı uygulamasıyla bir bağlantı oluşturulur ve ilke, uygulamadan alınır.  

> [!NOTE]
> Şirket Portalı uygulaması cihazda mevcut olmadığında, Intune özelliği etkinleştirilmiş uygulamanın davranışı değiştirilmez ve uygulama, normal bir uygulama gibi davranır.


# <a name="how-to-integrate-with-the-intune-app-sdk"></a>Intune Uygulama SDK'sı ile tümleştirme
 
Daha önce belirtildiği gibi, SDK, uygulama yönetimi ilkelerini etkinleştirmek için bir uygulamanın kaynak kodunda değişiklik yapılmasını gerektirir. Uygulamanızda MAM özelliğini etkinleştirmek için gereken adımlar şunlardır: 

## <a name="replace-classes-methods-and-activities-with-their-mam-equivalent-required"></a>Sınıfları, yöntemleri ve etkinlikleri MAM eşdeğerleriyle değiştirme (zorunlu) 

Android temel sınıfları, ilgili MAM eşdeğerleriyle değiştirilmelidir. Bunu yapmak için, aşağıdaki tabloda listelenen sınıfların tüm örneklerini bulun ve bunları Intune Uygulama SDK'sındaki eşdeğerleriyle değiştirin. 

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
| android.app.PendingIntent | **MAMPendingIntent** * |
| android.app.Service | MAMService |
| android.app.TabActivity | MAMTabActivity |
| android.app.TaskStackBuilder | MAMTaskStackBuilder |
| android.app.backup.BackupAgent | MAMBackupAgent |
| android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
| android.app.backup.FileBackupHelper | MAMFileBackupHelper |
| android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
| android.content.BroadcastReceiver | MAMBroadcastReceiver |
| android.content.ContentProvider | MAMContentProvider |
| android.os.Binder | **MAMBinder** (Yalnızca Bağlayıcı, Android Arabirimi Tanım Dili (AIDL) arabirimden oluşturulmadığında gereklidir) |
| android.provider.DocumentsProvider | MAMDocumentsProvider |
| android.preference.PreferenceActivity | MAMPreferenceActivity |


**Microsoft.Intune.MAM.SDK.Suppveyat.v4.jar**:

| Android Sınıfı Intune MAM | Intune Uygulama SDK'sı karşılığı |
|--|--|
| android.support.v4.app.DialogFragment | MAMDialogFragment
| android.support.v4.app.FragmentActivity | MAMFragmentActivity
| android.support.v4.app.Fragment | MAMFragment
| android.support.v4.app.TaskStackBuilder | MAMTaskStackBuilder
| android.support.v4.content.FileProvider | MAMFileProvider
    
**Microsoft.Intune.MAM.SDK.Suppveyat.v7.jar**:

|Android Sınıfı | Intune Uygulama SDK'sı karşılığı |
|--|--|
|android.support.v7.app.ActionBarActivity | MAMActionBarActivity |

>[!NOTE]
>Unutmayın -- MAM eşdeğeri tarafından geçersiz kılınmış bir Android [giriş noktası](https://developer.android.com/guide/components/fundamentals.html) kullanılırken, giriş noktası yaşam döngüsünün MAM sürümü kullanılmalıdır (**MAMApplication** sınıfı hariç).
>
>Örneğin, **MAMActivity**’den türetilirken `onCreate`’ü geçersiz kılıp `super.onCreate` çağırmak yerine, Etkinlik, `onMAMCreate`’i geçersiz kılmalı ve `super.onMAMCreate`’yı çağırmalıdır. Bunun yapılması, Etkinlik başlatma işleminin (diğerlerinin arasında) belirli durumlarla Intune tarafından kısıtlanmasını sağlar. 

### <a name="pendingintents-and-renamed-methods"></a>PendingIntents ve yeniden adlandırılan yöntemler 

MAM giriş noktalarından birinden türettikten sonra Context nesnesini, Etkinlikleri başlatmak için normalde kullandığınız gibi (**PackageManager**, vb. kullanarak) kullanmak güvenlidir.  

**PendingIntents** bu kural için bir özel durumdur. Bu tür sınıflar çağrılırken, sınıf adını değiştirmeniz gerekir. Örneğin, `PendingIntent.get*` yerine `MAMPendingIntents.get*` yöntemi kullanılmalıdır. Bundan sonra, alışıldığı gibi sonuç **PendingIntents** kullanılabilir.

Bazı durumlarda, Android sınıfında kullanılabilir olan bir metot, MAM değiştirme sınıfında kesin olarak işaretlenmiştir. Bu durumda, MAM değiştirme sınıfı benzer ada sahip olup (genellikle "MAM" son ekini alır) geçersiz kılınması gereken bir metot sağlar. Örneğin, `ContentProvider.query`yerine `MAMContentProvider.queryMAM`. Java derleyicisi, MAM eşdeğeri yerine özgün metodun yanlışlıkla geçersiz kılınmasını önleyen kesin kısıtlamalar uygulamalıdır. 

##<a name="enable-features-that-require-app-participation"></a>Uygulama katılımı gerektiren özellikleri etkinleştirme 

SDK’nın kendi başına uygulayamayacağı bazı ilkeler vardır. Uygulama, aşağıda verilen **AppPolicy** arabiriminde bulabileceğiniz çeşitli API’ler kullanarak davranışını denetleyebilir.  

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

## <a name="enable-it-control-over-app-saving-behavior"></a>Uygulama kaydetme davranışı üzerinde BT denetimini etkinleştirme

Birçok uygulama, son kullanıcının dosyaları yerel olarak veya bir bulut depolama hizmetine kaydetmesine olanak tanıyan özellikler uygular. Intune Uygulama SDK’sı, BT yöneticilerinin kuruluşlarında uygun gördüğü durumlarda ilke kısıtlamaları uygulayarak veri sızıntısına karşı koruma sağlamasına olanak tanır.  BT’nin denetleyebileceği ilkelerden biri, son kullanıcının “kişisel” ve yönetilmeyen bir veri deposuna kayıt yapıp yapamayacağıdır. Buna yerel konuma, SD karta veya üçüncü taraf yedekleme hizmetlerine kaydetme dahildir. 

**Özelliği etkinleştirmek için uygulama katılımı gereklidir.** Uygulamanız kişisel konumlara veya bulut konumlarına doğrudan uygulama üzerinden kaydetmeye izin veriyorsa, BT yöneticisinin bir konuma kaydetmeye izin verilip verilmediğini denetleyebildiğinden emin olmak için bu özelliği uygulamanız gerekir. Aşağıdaki API, uygulamanın, geçerli Intune yönetici ilkesi tarafından kişisel bir depolama alanına kaydetmeye izin verilip verilmediğini bilmesini sağlar. Uygulama, son kullanıcının uygulama üzerinden kullanabildiği kişisel veri depolama alanını bildiği için bundan sonra ilkeyi uygulayabilir.  

İlkenin uygulanıp uygulanmadığını belirlemek için uygulama aşağıdaki çağrıyı yapabilir: 

```
MAMComponents.get(AppPolicy.class).getIsSaveToPersonalAllowed();
```

**Not**: Cihaz veya uygulama bir Intune yönetim ilkesi altında olmasa bile `MAMComponents.get(AppPolicy.class)` her zaman null olmayan bir Uygulama İlkesi döndürür. 

## <a name="allow-app-to-detect-if-pin-policy-is-required"></a>Uygulamanın, PIN İlkesi’nin gerekli olup olmadığını algılamasına izin verme
 
Bazı Intune uygulama kısıtlamaları için uygulamanızın Intune Uygulama SDK’sında işlev yinelememesi için bazı işlevlerini devre dışı bırakmasını isteyebilirsiniz. Örneğin, uygulama kendi PIN kullanıcı deneyimine sahipse, SDK’nın son kullanıcıdan PIN girmesini isteyecek şekilde yapılandırılması durumunda bunu devre dışı bırakmak isteyebilir. 

Bir Intune PIN ilkesinin uygulama başlatıldığında uygulama PIN’i gerektirecek şekilde yapılandırılmış olup olmadığını belirlemek için uygulama aşağıdaki çağrıyı yapabilir: 

```
MAMComponents.get(AppPolicy.class).getIsPinRequired();
```

## <a name="registering-for-notifications-from-the-sdk"></a>SDK’dan gelen bildirimlere kaydolma  

Intune Uygulama SDK'sı, uygulamanızın seçici temizleme gibi çeşitli ilkeler BT yöneticisi tarafından dağıtıldığında, bunların davranışını denetlemesine olanak tanır. BT yöneticisi böyle bir ilke dağıttığında, Intune hizmeti SDK’ya bir bildirim gönderir.

Uygulamanızın **MAMNotificationReceiver** sınıfını oluşturup **MAMNotificationReceiverRegistry** konumuna kaydederek SDK’dan gelen bildirimlere kaydolması gerekir. Bu işlem, aşağıdaki örnekte gösterildiği gibi alıcı ve `App.onCreate` öğesinde istenen bildirim türü belirtilerek yapılır:

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

**MAMNotificationReceiver** Intune hizmetinden bildirimleri alır. Bazı bildirimler doğrudan SDK tarafından işlenirken, bazıları uygulamanın katılımını gerektirir. 

Bir uygulamanın, bildirimden true veya false değeri döndürmesi **gerekir**. 

Bildirim sonucunda uygulamayı denediği bazı eylemler başarısız olmadığı sürece, uygulama her zaman true değerini döndürmelidir. 

* Bu hata Intune hizmetine bildirilebilir. BT yöneticisi bir silme işlemi başlattıktan sonra uygulamanın kullanıcı verilerini silmekte başarısız olması rapor edilecek bir senaryoya örnek olarak verilebilir. 

`MAMNotificationReceiver.onReceive` öğesinin engellenmesi güvenlidir; çünkü geri çağırma işlemi, kullanıcı arabirimi iş parçacığı üzerinde çalışmamaktadır. 

**MAMNotificationReceiver** arabirimi, aşağıya SDK’da belirtilen şekilde eklenir: 

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

##<a name="types-of-notifications"></a>Bildirim türleri
Aşağıdaki bildirimler uygulamaya gönderilir ve bazıları uygulama katılımını gerektirebilir: 

* **`WIPE_USER_DATA`**: Bu bildirim bir **MAMUserNotification** sınıfında gönderilir. Bu bildirim alındığında uygulamanın, **MAMUserNotification** ile geçirilen “kurumsal” kimliğiyle ilişkili tüm verileri silmesi beklenir. Bu bildirim şu anda, Intune Hizmeti kaydını silme sırasında gönderilmektedir. Kullanıcının birincil adı, genellikle kayıt işlemi sırasında belirtilir. Bu bildirime kaydolursanız, uygulamanız tüm kullanıcı verilerinin silindiğinden emin olmalıdır. Kaydolmazsanız, varsayılan seçici silme davranışı gerçekleştirilir.

* **`WIPE_USER_AUXILIARY_DATA`**: Uygulamalar Intune Uygulama SDK’sının varsayılan seçici silme davranışını gerçekleştirmesini ve diğer yandan silme gerçekleştirildiğinde bazı yardımcı verilerin kaldırılmasını isterse bu bildirime kaydolabilir.  

* **`REFRESH_POLICY`**: Bu bildirim bir**MAMUserNotification** içinde gönderilir. Bu bildirim alındığında, önbelleğe alınan herhangi bir Intune ilkesinin geçersiz kılınması ve güncelleştirilmesi gerekir. Bu işlem genellikle SDK tarafından yapılır, ancak ilke kalıcı olarak kullanılıyorsa, uygulama tarafından yapılması gerekir. 



## <a name="protecting-backup-data"></a>Yedekleme verilerini koruma 

Android Marshmallow (API 23) sürümünden itibaren Android’deki bir uygulama, verileri iki yolla yedekleyebilir. Her bir seçenek uygulamanızda kullanılabilir ve Intune veri korumasının doğru bir şekilde uygulandığından emin olmak için farklı adımlar gerektirir. Doğru veri koruma davranışı için gerekli olan ilgili eylemler için aşağıdaki tabloyu gözden geçirebilirsiniz.  Yedekleme yöntemleri hakkında daha fazla bilgi için bkz. [Android API kılavuzu](http://developer.android.com/guide/topics/data/backup.html). 

### <a name="auto-backup-for-apps"></a>Uygulamalar için Otomatik Yedekleme

Android, Android Marshmallow cihazlarındaki uygulamalara, uygulamanın hedef API’sinden bağımsız olarak [otomatik tam yedeklemeler](https://developer.android.com/guide/topics/data/autobackup.html) sunmaya başlamıştır. AndroidManifest.xml içinde `android:allowBackup` öğesini açıkça **false** olarak ayarlarsanız, uygulamanız hiçbir zaman Android tarafından yedeklenmek üzere sıraya alınmaz ve "kurumsal" veriler uygulama içinde kalır. Bu durumda, başka bir eylem gerekmez.

Ancak, `android:allowBackup` özniteliği, bildirim dosyasında `android:allowBackup` belirtilmemiş olsa bile varsayılan olarak true olarak ayarlanmıştır. Bu, tüm uygulama verilerinin otomatik olarak Google Drive hesabına yedeklendiği anlamına gelir ve bu da **veri sızıntısı riski** oluşturan bir varsayılan davranıştır. Bu nedenle SDK, veri korumasının uygulandığından emin olmak için aşağıda ana hatlarıyla verilen değişiklikleri gerektirir.  Uygulamanızın Android Marshmallow cihazlarında çalışmasını istiyorsanız, müşteri verilerini düzgün bir şekilde korumak için aşağıdaki yönergeleri izlemek önemlidir.  

*  Uygulamanızı bir **MAMBackupAgent** veya **MAMBackupAgentHelper** kullanarak yedeklemek için bir yedekleme aracısı yazmadıysanız, uygulamanızın Otomatik Yedekleme tarafından nasıl karşıya yükleneceğini göz önünde bulundurmanız ve denetlemeniz gerekir. Intune, XML’de özel kurallar tanımlama becerisi de dahil olmak üzere Android’in sunduğu tüm [Otomatik Yedekleme özelliklerinden](https://developer.android.com/guide/topics/data/autobackup.html) faydalanmanıza olanak tanır, ancak verilerinizin güvenliğini sağlamak için aşağıdaki adımları uygulamanız gerekir:

    1. Intune ilkesi uyumluluğu olan otomatik tam yedeklemelere olanak tanımak için varsayılan MAMBackupAgent kullanın. Bildiriminize `android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"` yerleştirin. 
    2. Uygulamanızın hangi tam yedekleme türünü (filtresiz, filtreli veya hiçbiri) almasını istediğinize karar verdiğinizde, `android:fullBackupContent` özniteliğini true, false veya uygulamanızda bir XML kaynağı olarak ayarlamanız gerekir. Lütfen `android:fullBackupContent` öğesine yerleştirdiklerinizi, `com.microsoft.intune.mam.FullBackupContent` adı verilen bir meta veri etiketine kopyalayın

    **Örnekler**: Uygulamanızın bir XML dosyasındaki özel kurallara göre tam yedeklemelere sahip olmasını istiyorsanız, lütfen bildiriminizdeki `com.microsoft.intune.mam.FullBackupContent` meta veri etiketi altında bir kaynak belirtin: 
    ```
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```



### <a name="keyvalue-backup"></a>Anahtar/Değer Yedeklemesi

Tüm API'lerde kullanılabilen bu seçenek `BackupAgent` ve `BackupAgentHelper`. 

#### <a name="using-backupagenthelper"></a>BackupAgentHelper kullanma

`BackupAgentHelper` ’ın uygulanması, hem yerel Android işlevselliği hem de MAM tümleştirmesi bakımından `BackupAgent` ‘ın uygulanmasından çok daha kolaydır. `BackupAgentHelper` , geliştiricinin tüm dosyaları ve paylaşılan tercihleri sırasıyla bir `FileBackupHelper` veya `SharedPreferencesBackupHelper`’a kaydetmesine olanak tanır. Bunlar, oluşturma sonrasında `BackupAgentHelper` ’a eklenir. 

#### <a name="using-backupagent"></a>BackupAgent kullanma

`BackupAgent` , hangi verilerin yedeklendiği konusunda çok daha net olmanızı sağlar. Ancak, bu seçenekleri kullanırsanız Android yedekleme çerçevesinden yararlanamazsınız.  Uygulama sorumluluğunun büyük bölümü size ait olduğundan, MAM aracılığıyla uygun veri korumasını sağlamak için daha fazla adım gerekir. MAM tümleştirme işlerinin büyük bölümü geliştirici olarak size gönderildiğinden, MAM tümleştirmesi biraz daha karmaşıktır. 

##### <a name="app-does-not-have-a-backup-agent"></a>Uygulama, bir yedekleme aracısına sahip değil
  
`android:allowBackup =true` olduğunda geliştirici seçenekleri şunlardır:

###### <a name="full-back-up-according-to-a-configuration-file"></a>Bir yapılandırma dosyasına göre tam yedekleme: 

Bildiriminizdeki `com.microsoft.intune.mam.FullBackupContent` meta veri etiketi altında bir kaynak belirtin. Örneğin:     `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />`

`<application>` etiketine şu özniteliği ekleyin: `android:fullBackupContent="@xml/my_scheme"`; burada `my_scheme`, uygulamanızdaki bir XML kaynağıdır. 

###### <a name="full-back-dup-without-exclusions"></a>Dışlamalar olmadan tam yedekleme 

Bildirim dosyasında `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />` 
 
Aşağıdaki özniteliği `<application>` etiketine ekleyin: `android:fullBackupContent="true"`.

##### <a name="app-has-a-backup-agent"></a>Uygulamanın yedekleme aracısı var

Yukarıda ana hatlarıyla verilen `BackupAgent` ve `BackupAgentHelper` bölümlerindeki önerileri izleyin 

Android M’de kolay yedekleme sağlayan `MAMDefaultFullBackupAgent`’ı kullanmaya geçmeniz önerilir. 

#### <a name="before-your-backup"></a>Yedeklemeden önce

Yedekleme işlemine başlamadan önce, yedeklemeyi planladığınız dosyaların veya veri arabelleklerinin yedeklenmesine izin verildiğinden emin olmanız gerekir. Bunu belirlemek için size `isBackupAllowed` ve `MAMFileProtectionManager` ve `MAMDataProtectionManager` işlevi sunulmuştur. Dosya veya veri arabelleğinin yedeklenmesine izin verilmiyorsa, bunu yedeklemede kullanmaya çalışmamanız gerekir.

Yedeklemenin belirli bir noktasında, 1. adımda iade ettiğiniz dosyaların kimliklerini isterseniz verileri ayıklamayı planladığınız dosyalarla birlikte `backupMAMFileIdentity(BackupDataOutput data, File … files)` öğesini çağırmanız gerekir. Bu, otomatik olarak yeni yedekleme varlıkları oluşturur ve bunları sizin için `BackupDataOutput` ’a yazar. Bu varlıklar geri yükleme sonrasında otomatik olarak kullanılır. 

### <a name="configure-azure-directory-authentication-library-adal"></a>Azure Directory Kimlik Doğrulama Kitaplığı’nı (ADAL) Yapılandırma  

SDK; kimlik doğrulama ve koşullu başlatma senaryolarında, uygulamaların bir miktar Azure Active Directory yapılandırmasına sahip olmasını gerektiren ADAL özelliğini kullanır. Yapılandırma değerleri, `AndroidManifest` meta verileri üzerinden SDK’ya iletilir. Uygulamanızı yapılandırmak ve uygun kimlik doğrulamasını sağlamak için `AndroidManifest`. Bu yapılandırmalardan bazıları, yalnızca uygulamanız genel olarak kimlik doğrulaması için ADAL kullanıyorsa gereklidir; bu durumda, uygulamanızın kendisini AAD’ye kaydetmek için kullandığı değerleri kullanmanız gerekir. Bu işlem, AAD’nin iki ayrı kayıt değerini (biri uygulamadan, biri SDK’dan) tanıması nedeniyle son kullanıcıdan kimlik doğrulamasının iki kez istenmesini önlemek amacıyla yapılır. 

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

#### <a name="common-adal-configurations"></a>Yaygın ADAL yapılandırmaları 

Yukarıda açıklanan değerler için yaygın yapılandırma aşağıda verilmiştir. 

##### <a name="app-does-not-integrate-adal"></a>Uygulama ADAL ile tümleştirilmezse

* Yetkili, AAD hesaplarının yapılandırılmış olduğu istenen ortama ayarlanmalıdır.

* SkipBroker true olarak ayarlanmalıdır.

##### <a name="app-integrates-adal"></a>Uygulama ADAL ile tümleştirilirse

* Yetkili, AAD hesaplarının yapılandırılmış olduğu istenen ortama ayarlanmalıdır.

* İstemci kimliği, uygulamanın istemci kimliğine ayarlanmalıdır.

* `NonBrokerRedirectURI` , uygulama için geçerli bir yeniden yönlendirme URI’sine ayarlanmalıdır.
    * Or `urn:ietf:wg:oauth:2.0:oob` geçerli bir AAD yeniden yönlendirme URI’si olarak yapılandırılmalıdır.

* SkipBroker false (veya absent) olarak ayarlanmalıdır

* AAD, aracı yeniden yönlendirme URI'sini kabul edecek şekilde yapılandırılmalıdır.

##### <a name="app-integrates-adal-but-does-not-support-the-aad-authenticator-app"></a>Uygulama ADAL ile tümleştirilir, ancak AAD Doğrulayıcı uygulamasını desteklemezse.

* Yetkili, AAD hesaplarının yapılandırılmış olduğu istenen ortama ayarlanmalıdır.

* İstemci kimliği, uygulamanın istemci kimliğine ayarlanmalıdır.

* `NonBrokerRedirectURI` , uygulama için geçerli bir yeniden yönlendirme URI’sine ayarlanmalıdır.

    * Or `urn:ietf:wg:oauth:2.0:oob` geçerli bir AAD yeniden yönlendirme URI’si olarak yapılandırılmalıdır.

### <a name="how-to-enable-logging-in-the-sdk"></a>SDK’da günlüğü etkinleştirme 

Günlüğe kaydetme, `java.util.logging` çerçevesi aracılığıyla yapılır. Günlükleri almak için [Java teknik kılavuzu](http://docs.oracle.com/javase/6/docs/technotes/guides/logging/overview.html). Uygulamaya bağlı olarak, `App.onCreate` genellikle günlüğe kaydetmeyi başlatmak için en iyi yerdir. Günlük iletileri sınıf adına göre anahtarlanır ve sınıf adı, gizlenmiş olabilir.

##<a name="multiidentity"></a>Çoklu Kimlik
###<a name="overview"></a>Genel Bakış
Intune Uygulama SDK’sı varsayılan olarak, ilkeyi uygulamaya bir bütün olarak uygular. Çoklu Kimlik, ilkenin her kimlik düzeyinde uygulanmasına izin vermek üzere etkinleştirilebilen bir MAM özelliğidir.  Bu, diğer MAM özelliklerine kıyasla önemli oranda daha fazla uygulama katılımı gerektirir. Uygulamanın etkin kimliği değiştirmeyi amaçladığında uygulama SDK'sını bilgilendirmesi gerekir ve kimlik değişikliği gerekli olduğunda da SDK bunu uygulamaya bildirir. Şu anda yalnızca tek bir yönetilen kimlik desteklenir. Kullanıcı cihaz veya uygulamayı kaydettikten sonra, SDK bu kimliği kullanır ve bunu birincil yönetilen kimlik olarak kabul eder. Uygulamadaki diğer kullanıcılar kısıtlanmamış ilke ayarlarıyla yönetilmeyen olarak kabul edilirler. 

Bir kimliğin yalnızca dizi olarak tanımlandığını aklınızda bulundurun. Kimlikler büyük/küçük harfe duyarlıdır ve SDK’ya kimlik için yapılan istekler, kimlik ayarlandığı sırada kullanılan özgün büyük/küçük harf dizimiyle aynı olmadığı sürece sonuç getirmeyebilir.

###<a name="enabling-multiidentity"></a>Çoklu Kimliği Etkinleştirme
Varsayılan olarak, tüm uygulamalar tek kimlikli uygulamalar olarak değerlendirilir. Bir uygulama, çoklu kimliği fark ettiğini Android bildirimine aşağıdaki meta verileri yerleştirerek bildirir.

```
<meta-data
            android:name="com.microsoft.intune.mam.MAMMultiIdentity"
            android:value="true" />
```
###<a name="setting-the-identity"></a>Kimliği Ayarlama

Geliştiriciler uygulamanın kimliğini aşağıdaki düzeylerde ayarlayabilir: 
1. İşlem düzeyi, 
2. Bağlam (genellikle Etkinlik) düzeyi 
3. İş parçacığı düzeyi 

İş parçacığı düzeyinde ayarlanmış bir kimlik Bağlam düzeyinde ayarlanmış bir kimliğin, bağlam düzeyinde ayarlanmış bir kimlikse işlem düzeyinde ayarlanmış bir kimliğin yerini alır. Bağlam’da ayarlanan bir kimlik yalnızca uygun olduğunda kullanılır. Örneğin dosya GÇ işlemlerinde ilişkili bir Bağlam bulunmaz. Aşağıdaki MAMPolicyManager yöntemleri kimlik ayarlamak ve önceden ayarlanan kimlik değerlerini almak için kullanılabilir.

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
Bir uygulamanın kimliğini null olarak ayarlayarak da temizleyebilirsiniz. Boş dize hiçbir zaman kısıtlamalara sahip olmayacak bir kimlik olarak kullanılabilir. Tüm kimlik ayarlama yöntemleri sonuç değerleri ``` MAMIdentitySwitchResult``` aracılığıyla geri rapor eder. Döndürülebilecek dört değer vardır:

1.**BAŞARILI**: Kimlik değişikliği başarılı oldu. 2**İZİN_VERİLMEDİ**: Kimlik değişikliğine izin verilmedi. Bu, kayıtlı kullanıcı olarak aynı şirkete ait farklı bir kurumsal kullanıcıya geçiş yapmak denenirse meydana gelir. Geçerli iş parçacığı üzerinde farklı bir kimlik ayarlıyken UI (Bağlam) kimliğini ayarlamak denenirse de gerçekleşir.
3.**İPTAL EDİLDİ**: Kullanıcı, genellikle PIN/Auth istemi üzerindeki geri tuşuna basarak, kimlik değişikliğini iptal etmiştir.
4.**BAŞARISIZ**: Kimlik değişikliği belirlenemeyen bir nedenden dolayı başarısız oldu.

Bir Bağlam kimliği ayarlamak söz konusu olduğunda, sonuç zaman uyumsuz olarak bildirilir. Bağlam bir Etkinlik ise, koşullu başlatma uygulanana kadar kimlik değişikliğinin başarılı olup olmadığı bilinemez ve bunun için kullanıcının bir PIN veya şirket kimlik bilgilerini tam olarak girmesi gerekebilir. Bu parametre için null değeri geçirmeye izin verilse de, uygulamanın bu sonucu almak için bir ```MAMSetUIIdentityCallback``` uygulaması gerekir.

```
public interface MAMSetUIIdentityCallback {
    void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult); 
}
```

Ayrıca bir etkinliğin kimliğini, ``` MAMPolicyManager.setUIPolicyIdentity``` çağırmak yerine doğrudan bir MAMActivity yöntemiyle ayarlayabilirsiniz. Aşağıdaki yöntemi kullanarak bunu yapabilirsiniz:

 ```public final void switchMAMIdentity(final String newIdentity);```

Uygulamalar ayrıca, etkinliğin kimliğini değiştirme denemelerinin sonucu hakkında bildirim almak için MAMActivity üzerinde bir yöntemi geçersiz kılabilir 

```public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);```

**Not:** Kimliği değiştirmek için etkinliğin yeniden oluşturulması gerekebilir. Bu durumda, ```onSwitchMAMIdentityComplete``` geri çağırma yeni etkinlik örneğine gönderilir.

###<a name="implicit-identity-changes"></a>Örtük Kimlik Değişiklikleri

Uygulamanın kimlik ayarlayabilme özelliğine ek olarak, bir iş parçacığı veya bir bağlamın kimliği başka bir MAM etkin uygulamadan veri girişine göre değişebilir. Örneğin bir etkinlik başka bir MAM uygulamasından gönderilen bir Amaç’tan başlatılmışsa, etkinliğin kimliği Amaç’ın gönderildiği noktada diğer uygulamadaki etkin kimliğe göre ayarlanır.
Hizmetler için iş parçacığının kimliği bir onStart veya onBind çağrısının süresine benzer şekilde ayarlanır. onBind’dan döndürülen Bağlayıcı içine yapılan çağrılar iş parçacığı kimliğini de geçici olarak ayarlar.
```ContentProvider``` içine yapılan çağrılar da benzer şekilde iş parçacığı kimliğini süreleri boyunca ayarlar.
Ayrıca, bir etkinlikle kullanıcı etkileşimi bir örtük kimlik anahtarına neden olabilir.
Örneğin, ```Resume``` sırasında bir kullanıcının bir yetkilendirme istemini iptal etmesi, boş bir kimliğe örtük anahtar ile sonuçlanır.
Uygulamaya bu değişiklikler hakkında haber alma ve bazı durumlarda gerekirse bunları yasaklayabilme fırsatı verilir. ```MAMService``` ve ```MAMContentProvider```, alt sınıfların geçersiz kılabileceği aşağıdaki yöntemi kullanıma sunar:

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
```AppIdentitySwitchReason```, örtük anahtarın kaynağını yakalar ve ```CREATE```, ```RESUME_CANCELLED``` ve ```NEW_INTENT``` değerlerini kabul edebilir.  Etkinliği sürdürmek PIN, kimlik doğrulama veya başka bir uyumluluk UI’sinin görüntülenmesine neden olduğunda ve kullanıcı bu UI’yi genellikle geri tuşuna basarak iptal etmeyi denediğinde ```RESUME_CANCELLED``` nedeni kullanılır.
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
Burada ```AppIdentitySwitchResult```; ```SUCCESS``` veya ```FAILURE``` olur. 

```onMAMIdentitySwitchRequired``` yöntemi, ```MAMService.onMAMBind``` öğesinden döndürülen bir Bağlayıcı aracılığıyla yapılanlar dışındaki tüm örtük kimlik değişiklikleri için çağrılır. Varsayılan ```onMAMIdentitySwitchRequired``` uygulamaları, neden ```RESUME_CANCELLED``` olduğunda hemen ```reportIdentitySwitchResult(FAILURE)``` çağırır ve diğer tüm durumlarda ```reportIdentitySwitchResult(SUCCESS)``` çağırır. 

Çoğu uygulamanın bir kimlik anahtarını farklı bir şekilde engellemesi veya geciktirmesi beklenmez, ancak bir uygulamanın böyle yapması gerekirse aşağıdaki noktaların göz önünde bulundurulması gerekir: *Bir kimlik anahtarı engellenmişse, sonuç ```Receive``` paylaşım ayarları veri girişini yasakladığında olanla aynıdır. *Bir hizmet ana iş parçacığı üzerinde çalışıyorsa, ```reportIdentitySwitchResult``` öğesinin zaman uyumlu olarak çağrılması **gerekir**, yoksa UI iş parçacığı kapanır. 
* ```Activity``` oluşturmak için ```onMAMIdentitySwitchRequired```, ```onMAMCreate``` öğesinden önce çağrılır. Kimlik anahtarına izin verilip verilmeyeceğine karar vermek için uygulamanın UI göstermesi gerekiyorsa, bu UI farklı bir etkinlik kullanılarak gösterilmelidir. *Bir Etkinlik içinde, ```RESUME_CANCELLED``` ile eşit bir nedenle boş kimliğe anahtar istenirse, uygulamanın, bu kimlik anahtarı ile tutarlı verileri görüntülemek için sürdürülen etkinliği değiştirmesi gerekir.  Bu mümkün değilse, uygulama anahtarı reddetmelidir ve kullanıcıdan bir kez daha sürdürülen kimlik ilkesine uyması istenir (örneğin, PIN girişi ekranı gösterilerek). 

**Not:** Çoklu kimlikli bir uygulama yönetilen ve yönetilmeyen uygulamalardan gelen verileri her zaman alır. Yönetilen kimliklerden alınan verileri yönetilen kabul etmek uygulamanın sorumluluğudur. İstenen kimlik yönetilen ```(MAMPolicyManager.getIsIdentityManaged)``` ise, ancak uygulama bu hesabı kullanamıyorsa (mesela e-posta hesapları gibi hesapların, ilk olarak uygulamada ayarlanması gerektiği için) kimlik anahtarı reddedilir.

##<a name="file-protection"></a>Dosya Koruması
Her dosyanın, oluşturulduğu sırada iş parçacığı ve işlem kimliğine dayalı olarak kendisiyle ilişkilendirilmiş bir kimliği vardır. Bu kimlik hem dosya şifreleme hem de seçici silme için kullanılır. Yalnızca şifreleme gerektiren ilkesi bulunan dosyalar şifrelenir. SDK'ın varsayılan seçici silme işlemi, yalnızca silme işleminin istendiği kimlikle ilişkilendirilmiş dosyaları siler. Uygulama, ```MAMFileProtectionManager``` kullanarak bir dosyanın kimliğini sorgulayabilir veya değiştirebilir
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

**Not:** Dosya kimliği etiketlemesi çevrimdışı moda karşı hassastır. Aşağıdaki noktalar göz önünde bulundurulmalıdır.
* Şirket Portalı yüklü değilse, dosyalar kimlik etiketli olamaz. 
* Şirket Portalı yüklü, ancak uygulamada kullanılan ilke yoksa, dosyalar güvenilir bir şekilde kimlik etiketli yapılamaz.
* Dosya kimliği etiketleme kullanılabilir olduğunda, uygulama kayıtlı kullanıcıya ait kabul edildiği durumda önceden tek kimlikli yönetilen uygulama olarak yüklenmediyse, önceden oluşturulan tüm dosyalar kişisel kabul edilir (boş dize kimliğine ait olarak).

###<a name="data-protection"></a>Veri Koruma
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
##<a name="content-providers"></a>İçerik Sağlayıcıları
Uygulama bir ```ContentProvider``` aracılığıyla ```ParcelFileDescriptor``` dışında potansiyel kurumsal veriler sağlıyorsa, uygulamanın ```MAMContentProvider``` yöntemini çağırması ve ```isProvideContentAllowed(String)``` içerik için ```UPN``` sahibi geçmesi gerekir. Bu işlev false döndürürse, içeriği çağırana döndürülemez. İçerik sağlayıcısı aracılığıyla döndürülen dosya tanımlayıcıları dosya kimliğine göre otomatik olarak işlenir.

##<a name="selective-wipe"></a>Seçici Silme
Bir uygulama ```WIPE_USER_DATA``` bildirimine kaydolursa, SDK varsayılan seçmeli silme davranışından faydalanamaz. Çoklu kimliği fark eden uygulamalarda, MAM varsayılan seçici silme yalnızca silinecek kimlikle eşleşen dosyaları sileceğinden bu durum daha önemli olabilir. Çoklu kimliği fark eden bir uygulama oluşturuyorsanız, SDK varsayılan silme davranışından faydalanmanızı sağlayacak ```WIPE_USER_AUXILIARY_DATA``` hizmetine kaydolabilirsiniz. Bu bildirim, SDK varsayılan seçmeli silme gerçekleştirilmeden hemen önce gönderilir. Bir uygulamanın hiçbir zaman hem ```WIPE_USER_DATA``` hem de ```WIPE_USER_AUXILIARY_DATA``` kaydı olmaması gerektiğini unutmayın.

## <a name="known-platform-limitations"></a>Bilinen Platform Sınırlamaları 

### <a name="file-size-limitations"></a>Dosya Boyutu Sınırlamaları 

Android’de, Dalvik yürütülebilir dosya biçimine ilişkin sınırlamalar, ProGuard olmadan çalışan büyük kod temelleri için sorun oluşturabilir. Özellikle aşağıdaki sınırlamalar görülebilir: 

* Alanlarda 65.000 sınırı.

* Metotlarda 65.000 sınırı.

Çok sayıda proje dahil edilirken, kitaplık sayısı arttıkça alan sayısını önemli ölçüde artıran bir R kopyası her android:package öğesine eklenir. Aşağıdaki öneriler bu sınırlamaları azaltmaya yardımcı olabilir:
 
* Tüm kitaplık projeleri, mümkün olduğunda aynı android:package öğesini paylaşmalıdır. Yalnızca derleme zamanıyla ilgili bir sorun olduğundan, bu durum alanda düzensiz aralıklarla hataya neden olmaz.   Ayrıca, Android SDK'nın daha yeni sürümleri bazı artıklıkları kaldırmak için DEX dosyalarını önceden işler. Bunun yapılması, alanlarla uzaklığı daha da azaltır.

* Mevcut olan en yeni Android SDK derleme araçlarını kullanın.

* Tüm gereksiz ve kullanılmayan kitaplıkları kaldırın (örneğin, `android.support.v4`)

### <a name="policy-enforcement-limitations"></a>İlke Zorlama Sınırlamaları

**Ekran Yakalama**: SDK, Activity.onCreate öğesinden zaten geçmiş olan Etkinliklerde yeni bir ekran yakalama ayar değeri uygulayamaz. Bu durum, uygulama ekran görüntülerini devre dışı bırakacak şekilde yapılandırıldığı halde ekran görüntülerinin alınabildiği bir zaman dilimine yol açabilir.

**İçerik Çözümleyicileri Kullanma*: Aktarım veya alma ilkesi, başka bir uygulamadaki içerik sağlayıcısına erişmek için bir içerik çözümleyicisinin kullanılmasını tamamen veya kısmen engelleyebilir. Bu durum ContentResolver yöntemlerinin null döndürmesine veya bir hata değeri oluşturmasına neden olur (örneğin `openOutputStream` engellenirse `FileNotFoundException` oluşturur). Uygulama, içerik çözümleyicisi ile veri yazma hatasının bir ilkeden kaynaklanıp kaynaklanmadığını (veya ilke tarafından kaynaklanabileceğini) şu çağrıyı yaparak belirleyebilir:

    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI)

**Dışarı Aktarılan Hizmetler**: Intune Uygulama SDK’sına dahil edilen `AndroidManifest.xml` dosyası, `MAMNotificationReceiverService`öğesini içerir. Bu öğenin, Şirket Portalı’nın kullanan bir uygulamaya bildirim göndermesine izin vermek üzere dışarı aktarılan bir hizmet olması gerekir. Hizmet, yalnızca Şirket Portalı’nın bildirim göndermesine izin verildiğinden emin olmak için çağıranı denetler. 

## <a name="recommended-android-best-practices"></a>Android için Önerilen En İyi Uygulamalar 

İlkeleri zorunlu kılma işlemi sonucunda hata koşulları daha sık tetiklenebilir, ancak Intune SDK’sı, Android API’si tarafından sağlanan sözleşmeyi korur. Aşağıda belirtilen Android’e yönelik en iyi uygulamalar, hata olasılığını azaltır: 

* Null döndürme olasılığı bulunan Android SDK İşlevleri’nin şu anda da null olma olasılığı daha yüksektir.  Sorunları en aza indirmek için null denetimlerinin doğru yerlerde olduğundan emin olun.

* Denetlenebilir özellikler SDK API'leri aracılığıyla denetlenmelidir.

* Türetilen tüm işlevler üst sınıf sürümlerine çağrılmalıdır.

* Herhangi bir API'yi belirsiz bir şekilde kullanmaktan kaçının. Örneğin, requestCode denetlenmeden `Activity.startActivityForResult/onActivityResult` işlemi garip davranışlara neden olur.






<!--HONumber=Oct16_HO5-->


