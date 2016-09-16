---
title: "Android için Microsoft Intune Uygulama SDK’sı Geliştirici Kılavuzu | Microsoft Intune"
description: 
keywords: 
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
ms.sourcegitcommit: 952cfa4f23f8ba080ce53f6785baceb8a0a367c6
ms.openlocfilehash: 829ba47807b3b773c810be290b636d9f18e9c2bd


---

# Android için Microsoft Intune Uygulama SDK’sı Geliştirici Kılavuzu

> [!NOTE]
> Öncelikle, SDK’nın geçerli özelliklerini kapsayan ve desteklenen her platformda tümleştirmeye nasıl hazırlandığını açıklayan [Intune Uygulama SDK’sına genel bakış](intune-app-sdk.md) bölümünü okumanız önerilir. 

## SDK’nın kapsamı 

Android için Intune Uygulama SDK'sı dış bağımlılıkları olmayan standart bir Android kitaplığıdır. SDK şunlardan oluşur:  

* **`Microsoft.Intune MAM.SDK.jar`**: Bir uygulamada MAM özelliğini etkinleştirmenin yanı sıra Microsoft Intune Şirket Portalı ile birlikte çalışabilirliği sağlamak için gereken arabirimler. Uygulamalar bunu bir Android kitaplığı başvurusu olarak belirtmelidir.

* **`Microsoft.Intune.MAM.SDK.Support.v4.jar`**: Android v4 destek kitaplığından yararlanan uygulamalarda MAM özelliğini etkinleştirmek için gereken arabirimler.  Bu desteğe ihtiyaç duyan uygulamalar jar dosyasına doğrudan başvurmalıdır. 

* **`Microsoft.Intune.MAM.SDK.Support.v7.jar`**: Android v7 destek kitaplığından yararlanan uygulamalarda MAM özelliğini etkinleştirmek için gereken arabirimler.   Bu desteğe ihtiyaç duyan uygulamalar jar dosyasına doğrudan başvurmalıdır

* **Kaynak dizini**: SDK’nın bağımlı olduğu kaynaklar (dizeler gibi). 

* **`Microsoft.Intune.MAM.SDK.aar`**: Support.V4 ve Support.V7 jar dosyaları dışındaki SDK bileşenleri. Derleme sisteminiz AAR dosyalarını destekliyorsa bu dosya, tek bileşenlerin yerine kullanılabilir.

* **`AndroidManifest.xml`**: Ek giriş noktaları ve kitaplık gereksinimleri. 

* **`THIRDPARTYNOTICES.TXT`**: Uygulamanıza derlenecek 3. taraf ve/veya OSS kodunu tanıyan bir öznitelik bildirimi. 

## Gereksinimler 

Intune Uygulama SDK'sı, derlenmiş bir Android projesidir. Sonuç olarak, uygulamanın en düşük veya hedef API sürümleri için kullandığı Android sürümünden büyük ölçüde bağımsızdır. SDK; Android API 14 (Android 4.0+) ile Android 24 arasındaki sürümleri destekler. 

## Intune Uygulama SDK’sı nasıl çalışır? 

Intune Uygulama SDK'sı, uygulama yönetimi ilkelerini etkinleştirmek için bir uygulamanın kaynak kodunda değişiklik yapılmasını gerektirir. Bu işlem, Android temel sınıflarının, belgede `MAM`. SDK sınıfları, Android temel sınıfı ile uygulamanın söz konusu sınıftan türettiği sürüm arasında çalışır.  Örnek olarak bir etkinlik kullanıldığında elde edilen devralma hiyerarşisi şunun gibi görünür: `Activity ->MAMActivity->AppSpecificActivity`.

`AppSpecificActivity` üst öğesiyle etkileşim kurmak istediğinde (örn. `super.onCreate())`), `MAMActivity` devralma hiyerarşisinde olmasına ve birkaç yöntemin yerine geçmesine rağmen üst sınıftır. Android uygulamaları tek bir moda sahiptir ve tüm sisteme Context nesnesi aracılığıyla erişebilir.  Intune Uygulama SDK’sını içeren uygulamalar ise sisteme Context nesnesi aracılığıyla erişmesine karşın, kullanılan temel Etkinliğe bağlı olarak Context nesnesinin Android tarafından sağlanması ya da sistemin kısıtlanmış bir görünümü ile Android tarafından sağlanan Context nesnesi arasında çoğullanması nedeniyle çift moda sahiptir.

Android için Intune Uygulama SDK’sı, MAM ilkelerini etkinleştirmek için cihazda Şirket Portalı uygulamasının varlığına bağımlıdır. Şirket Portalı uygulaması mevcut olmadığında, MAM özellikli uygulamanın davranışı değiştirilmez ve uygulama, diğer mobil uygulamalar gibi hareket eder. Şirket Portalı yüklendiğinde ve kullanıcı için ilkelere sahip olduğunda, SDK giriş noktaları zaman uyumsuz olarak başlatılır. Başlatma işlemi yalnızca, işlem başlangıçta Android tarafından oluşturulduğunda gereklidir. Başlatma sırasında Şirket Portalı uygulamasıyla bir bağlantı oluşturulur ve uygulama kısıtlama ilkesi indirilir.  

## Intune Uygulama SDK'sı ile tümleştirme
 
Daha önce belirtildiği gibi, SDK, uygulama yönetimi ilkelerini etkinleştirmek için bir uygulamanın kaynak kodunda değişiklik yapılmasını gerektirir. Uygulamanızda MAM özelliğini etkinleştirmek için gereken adımlar şunlardır: 

### Sınıfları, yöntemleri ve etkinlikleri MAM eşdeğerleriyle değiştirme (Zorunlu) 

* Android temel sınıfları, MAM eşdeğerleriyle değiştirilmelidir. Bunu yapmak için, aşağıdaki tabloda listelenen sınıfların tüm örneklerini bulun ve bunları Intune Uygulama SDK'sındaki eşdeğerleriyle değiştirin.  

    | Android Sınıfı | Intune Uygulama SDK'sı Karşılığı |
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
    | android.app.PendingIntent | MAMPendingIntent |
    | android.app.Service | MAMService |
    | android.app.TabActivity | MAMTabActivity |
    | android.app.TaskStackBuilder | MAMTaskStackBuilder |
    | android.app.backup.BackupAgent | MAMBackupAgent |
    | android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
    | android.app.backup.FileBackupHelper | MAMFileBackupHelper |
    | android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
    | android.content.BroadcastReceiver | MAMBroadcastReceiver |
    | android.content.ContentProvider | MAMContentProvider |
    | android.os.Binder | MAMBinder* |
    | android.provider.DocumentsProvider | MAMDocumentsProvider |
    | android.preference.PreferenceActivity | MAMPreferenceActivity |

    *Bağlayıcı, yalnızca bir AIDL arabiriminden oluşturulmamış olması durumunda MAMBinder ile değiştirilmelidir.

    **Microsoft.Intune.MAM.SDK.Suppveyat.v4.jar**:

    | Android Sınıfı Intune MAM | SDK Değiştirme |
    |--|--|
    | android.support.v4.app.DialogFragment | MAMDialogFragment
    | android.support.v4.app.FragmentActivity | MAMFragmentActivity
    | android.support.v4.app.Fragment | MAMFragment
    | android.support.v4.app.TaskStackBuilder | MAMTaskStackBuilder
    | android.support.v4.content.FileProvider | MAMFileProvider
    
    **Microsoft.Intune.MAM.SDK.Suppveyat.v7.jar**:

    |Android Sınıfı | Intune MAM SDK Karşılığı |
    |--|--|
    |android.support.v7.app.ActionBarActivity | MAMActionBarActivity |


* MAM eşdeğeri tarafından geçersiz kılınmış bir Android giriş noktası kullanılırken, giriş noktası yaşam döngüsünün alternatif bir sürümü kullanılmalıdır (`MAMApplication`sınıfı hariç).

    Örneğin, `MAMActivity`’i geçersiz kılıp `onCreate` çağırmak yerine `super.onCreate`’den türetilirken, Etkinlik `onMAMCreate` ’i geçersiz kılmalı ve s`uper.onMAMCreate`. Bunun yapılması, Etkinlik başlatma işleminin (diğerlerinin arasında) belirli durumlarla kısıtlanmasını sağlar. 

### Uygulama katılımı gerektiren özellikleri etkinleştirme 

SDK’nın kendi başına uygulayamayacağı bazı ilkeler vardır. Uygulamanın bu özellikler için davranışını denetlemesini sağlamak amacıyla, aşağıda verilen `AppPolicy` içinde bulabileceğiniz API’leri kullanabilirsiniz.  

    /**
     * External facing app policies.
     */
    public interface AppPolicy {
        /**
         * Restrict where an app can save personal data.
         * 
         * @return True if the app is allowed to save to personal data stores;
         *         false otherwise.
         */
        boolean getIsSaveToPersonalAllowed();
    
        /**
         * Check if policy prohibits saving to a content provider location.
         * 
         * @param location
         *            a content URI to check
         * @return True if location is not a content URI or if policy does not 
         *         prohibit saving to the content location.
         */
        boolean getIsSaveToLocationAllowed(android.net.Uri location); 
    
        /**
         * Whether the SDK PIN prompt is enlightened for the app.
         * 
         * @return True if the PIN is enabled. False otherwise.
         */
        boolean getIsPinRequired();
        /**
         * Whether the Intune Managed Browser is required to open web links.
         *
         * @return True if the Managed Browser is required, false otherwise
         */
        boolean getIsManagedBrowserRequired();
    }

### Uygulama kaydetme davranışı üzerinde BT yöneticisi denetimini etkinleştirme

Birçok uygulama, son kullanıcının dosyaları yerel olarak veya başka bir hizmete kaydetmesine olanak tanıyan özellikler uygular. Intune Uygulama SDK’sı, BT yöneticilerinin kuruluşlarında uygun gördüğü durumlarda ilke kısıtlamaları uygulayarak veri sızıntısına karşı koruma sağlamasına olanak tanır.  Yöneticinin denetleyebileceği ilkelerden biri, son kullanıcının kişisel bir veri deposuna kayıt yapıp yapamayacağıdır. Buna yerel konuma, SD karta veya yedekleme hizmetlerine kaydetme dahildir. Özelliği etkinleştirmek için uygulama katılımı gereklidir. Uygulamanız kişisel konumlara veya bulut konumlarına doğrudan uygulama üzerinden kaydetmeye izin veriyorsa, BT yöneticisinin bir konuma kaydetmeye izin verilip verilmediğini denetleyebildiğinden emin olmak için bu özelliği uygulamanız gerekir. Aşağıdaki API, uygulamanın, geçerli yönetici ilkesi tarafından kişisel bir depolama alanına kaydetmeye izin verilip verilmediğini bilmesini sağlar. Uygulama, son kullanıcının uygulama üzerinden kullanabildiği kişisel veri depolama alanını bildiği için bundan sonra ilkeyi uygulayabilir.  

İlkenin uygulanıp uygulanmadığını belirlemek için uygulama aşağıdaki çağrıyı yapabilir: 

    MAMComponents.get(AppPolicy.class).getIsSaveToPersonalAllowed();

**Not**: Cihaz veya uygulama yönetim altında olsa bile MAMComponents.get(AppPolicy.class) her zaman null olmayan bir Uygulama İlkesi döndürür. 

### Uygulamanın, PIN İlkesi’nin gerekli olup olmadığını algılamasına izin verme
 
 Uygulamanın, Intune Uygulama SDK'sındaki işlevleri yinelememek için bazı işlevlerini devre dışı bırakmasını gerektirebilecek ek ilkeler bulunur. Örneğin, uygulama kendi PIN kullanıcı deneyimine sahipse, SDK’nın son kullanıcıdan PIN girmesini isteyecek şekilde yapılandırılması durumunda bunu devre dışı bırakmak isteyebilir. 

PIN ilkesinin düzenli aralıklarla PIN girişi isteyecek şekilde yapılandırılıp yapılandırılmadığını belirlemek üzere uygulama aşağıdaki çağrıyı yapabilir: 

    MAMComponents.get(AppPolicy.class).getIsPinRequired();

### SDK’dan gelen bildirimlere kaydolma  

Intune Uygulama SDK'sı, uygulamanızın, BT yöneticisi tarafından uzaktan silme gibi bazı ilkelerin kullanıldığı durumlarda davranış üzerinde denetime sahip olmasını sağlar. Bunu yapmak için, `MAMNotificationReceiver` sınıfını oluşturup `MAMNotificationReceiverRegistry`. Bu işlem, aşağıdaki örnekte gösterildiği gibi alıcı ve alıcının  `App.onCreate`öğesine almak istediği bildirim türü belirtilerek yapılır:
 
    @Override
      public void onCreate() {
            super.onCreate();
    MAMComponents.get(MAMNotificationReceiverRegistry.class).registerReceiver(
    new ToastNotificationReceiver(), MAMNotificationType.WIPE_USER_DATA);
    }

`MAMNotificationReceiver` Yalnızca bildirimleri alır. Bazı bildirimler doğrudan SDK tarafından işlenirken, bazıları uygulamanın katılımını gerektirir. Bir uygulama, bildirimden true veya false değeri döndürmelidir. Bildirim sonucunda uygulamayı denediği bazı eylemler başarısız olmadığı sürece, uygulama her zaman true değerini döndürmelidir. Uygulamanın kullanıcı verilerini silmeyi başaramadığını belirtmesi gibi hatalar Intune hizmetine bildirilebilir. `MAMNotificationReceiver.onReceive` öğesinin engellenmesi güvenlidir; geri çağırma işlemi, kullanıcı arabirimi iş parçacığı üzerinde çalışmamaktadır. 

`MAMNotificationReceiver arabirimi, aşağıya SDK’da belirtilen şekilde eklenir: 

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

Aşağıdaki bildirimler uygulamaya gönderilir ve bazıları uygulama katılımını gerektirebilir: 

* **`WIPE_USER_DATA` bildirimi**: Bu bildirim bir `MAMUserNotification` sınıfında gönderilir. Bu bildirim alındığında uygulama, `MAMUserNotification`. Bu bildirim şu anda, Intune Hizmeti kaydını silme sırasında gönderilmektedir. Kullanıcının birincil adı, genellikle kayıt işlemi sırasında belirtilir. Bu bildirime kaydolursanız, uygulamanız tüm kullanıcı verilerinin silindiğinden emin olmalıdır. Kaydolmazsanız, varsayılan seçici silme davranışı gerçekleştirilir. 

* **`WIPE_USER_AUXILIARY_DATA` bildirimi**: Uygulamalar Intune Uygulama SDK’sının varsayılan silme işlemini gerçekleştirmesini ve diğer yandan silme gerçekleştirildiğinde bazı yardımcı verilerin kaldırılmasını isterse bu bildirime kaydolabilir.  

* **`REFRESH_POLICY` bildirimi**: Bu bildirim bir MAMNotification içinde ek bir bilgi olmadan gönderilir. Bu bildirim alındığında, önbelleğe alınan tüm ilkelerin artık geçersiz olduğu kabul edilmeli ve dolayısıyla ilkenin ne olduğu denetlenmelidir. Bu işlem genellikle SDK tarafından yapılır, ancak ilke kalıcı olarak kullanılıyorsa, uygulama tarafından yapılması gerekir. 

### Bekleyen Amaçlar ve yöntemler 

MAM giriş noktalarından birinden türettikten sonra Context nesnesini, Etkinlikleri başlatmak için normalde kullandığınız gibi (`PackageManager`, vb. kullanarak) kullanabilirsiniz.  `PendingIntents` bu kural için bir özel durumdur. Bu tür sınıflar çağrılırken, sınıf adını değiştirmeniz gerekir. Örneğin, `PendingIntent.get*` yerine `MAMPendingIntents.get*` kullanılmalıdır. 

Bazı durumlarda, Android sınıfında kullanılabilir olan bir metot, MAM değiştirme sınıfında kesin olarak işaretlenmiştir. Bu durumda, MAM değiştirme sınıfı benzer ada sahip olup (genellikle "MAM" son ekini alır) geçersiz kılınması gereken bir metot sağlar. Örneğin, `ContentProvider.query`yerine `MAMContentProvider.queryMAM`. Java derleyicisi, MAM eşdeğeri yerine özgün metodun yanlışlıkla geçersiz kılınmasını önleyen kesin kısıtlamalar uygulamalıdır. 

## Yedekleme verilerini koruma 

Android Marshmallow (API 23) sürümünden itibaren Android’deki bir uygulama, verileri iki yolla yedekleyebilir. Bu seçenekler, uygulamanızda kullanılabilir ve MAM veri korumasının uygun şekilde uygulanması için farklı adımlar gerektirir. Doğru veri koruma davranışı için gerekli olan ilgili eylemlere hızlı bir genel bakış için aşağıdaki tabloyu gözden geçirebilirsiniz.  Android yedekleme hakkında daha fazla bilgi için [Android Geliştirici Veri Yedekleme Kılavuzu](http://developer.android.com/guide/topics/data/backup.html)’na da bakabilirsiniz. 

### Otomatik tam yedekleme

Android M sürümünde Android, bir Android M cihazında çalıştırılan uygulamalara hedef API’den bağımsız olarak otomatik tam yedekleme sunmaya başlamıştır. `android:allowBackup` özniteliği false olmadığı sürece, uygulama tam ve filtrelenmemiş yedeklemeler alır. Bu durum veri sızıntısı riski oluşturur. Bu nedenle SDK, veri korumasının uygulandığından emin olmak için aşağıdaki tabloda ana hatlarıyla verilen değişiklikleri gerektirir.  Müşteri verilerini düzgün bir şekilde korumak için aşağıda açıklanan yönergeleri izlemeniz önemlidir.  `android:allowBackup=false` ayarını yaparsanız, uygulamanız işletim sistemi tarafından hiçbir zaman yedekleme sırasına alınmaz ve yedekleme olmadığı için MAM ile ilgili başka bir işleminiz olmaz
 
 ## “anahtar/değer” yedeklemeleri

Tüm API'lerde kullanılabilen bu seçenek `BackupAgent` ve `BackupAgentHelper`. 

#### BackupAgentHelper kullanma

`BackupAgentHelper` bunun uygulanması, hem yerel Android işlevselliği hem de MAM tümleştirmesi bakımından `BackupAgent`‘ın uygulanmasından çok daha kolaydır. `BackupAgentHelper` geliştiricinin tüm dosyaları ve paylaşılan tercihleri sırasıyla bir `FileBackupHelper` veya `SharedPreferencesBackupHelper`’a kaydetmesine olanak tanır. Bunlar da, oluşturma sonrasında `BackupAgentHelper`’a eklenir. 

#### BackupAgent kullanma

`BackupAgent` hangi verilerin yedeklendiği konusunda çok daha net olmanızı sağlar. Ancak, bu seçenekleri kullanırsanız Android yedekleme çerçevesinden yararlanamazsınız.  Uygulama sorumluluğunun büyük bölümü size ait olduğundan, MAM aracılığıyla uygun veri korumasını sağlamak için daha fazla adım gerekir. MAM tümleştirme işlerinin büyük bölümü geliştirici olarak size gönderildiğinden, MAM tümleştirmesi biraz daha karmaşıktır. 

##### Uygulama, bir yedekleme aracısına sahip değil
  
`Android:allowbBackup =true` olduğunda geliştirici seçenekleri şunlardır:

###### Bir yapılandırma dosyasına göre tam yedekleme: 

Bildiriminizdeki `com.microsoft.intune.mam.FullBackupContent` meta veri etiketi altında bir kaynak belirtin. Örneğin:
    `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />`

`<application>` etiketine şu özniteliği ekleyin: `android:fullBackupContent="@xml/my_scheme"`; burada `my_scheme`, uygulamanızdaki bir XML kaynağıdır. 

###### Dışlamalar olmadan tam yedekleme 

Bildirim dosyasında şöyle bir etiket sağlar: `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />` 
 
Aşağıdaki özniteliği `<application>` etiketine ekleyin: `android:fullBackupContent="true"`.

##### Uygulamanın yedekleme aracısı var

Yukarıda ana hatlarıyla verilen `BackupAgent` ve `BackupAgentHelper` bölümlerindeki önerileri izleyin 

Android M’de kolay yedekleme sağlayan `MAMDefaultFullBackupAgent`’ı kullanmaya geçmeniz önerilir. 

#### Yedeklemeden önce

Yedekleme işlemine başlamadan önce, yedeklemeyi planladığınız dosyaların veya veri arabelleklerinin yedeklenmesine izin verildiğinden emin olmanız gerekir. Bunu belirlemek için size `isBackupAllowed` ve `MAMFileProtectionManager` ve `MAMDataProtectionManager` işlevi sunulmuştur. Dosya veya veri arabelleğinin yedeklenmesine izin verilmiyorsa, bunu yedeklemede kullanmaya çalışmamanız gerekir.

Yedeklemenin belirli bir noktasında, 1. adımda iade ettiğiniz dosyaların kimliklerini isterseniz verileri ayıklamayı planladığınız dosyalarla birlikte `backupMAMFileIdentity(BackupDataOutput data, File … files)` öğesini çağırmanız gerekir. Bu, otomatik olarak yeni yedekleme varlıkları oluşturur ve bunları sizin için `BackupDataOutput` ’a yazar. Bu varlıklar geri yükleme sonrasında otomatik olarak kullanılır. 

### Azure Directory Kimlik Doğrulama Kitaplığı’nı (ADAL) Yapılandırma  

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

#### Yaygın ADAL yapılandırmaları 

Yukarıda açıklanan değerler için yaygın yapılandırma aşağıda verilmiştir. 

##### Uygulama ADAL ile tümleştirilmezse

* Yetkili, AAD hesaplarının yapılandırılmış olduğu istenen ortama ayarlanmalıdır.

* SkipBroker true olarak ayarlanmalıdır.

##### Uygulama ADAL ile tümleştirilirse

* Yetkili, AAD hesaplarının yapılandırılmış olduğu istenen ortama ayarlanmalıdır.

* İstemci kimliği, uygulamanın istemci kimliğine ayarlanmalıdır.

* `NonBrokerRedirectURI` Uygulama için geçerli bir yeniden yönlendirme URI’sine ayarlanmalıdır.
    * Veya `urn:ietf:wg:oauth:2.0:oob` geçerli bir AAD yeniden yönlendirme URI’si olarak yapılandırılmalıdır.

* SkipBroker false (veya absent) olarak ayarlanmalıdır

* AAD, aracı yeniden yönlendirme URI'sini kabul edecek şekilde yapılandırılmalıdır.

##### Uygulama ADAL ile tümleştirilir, ancak AAD Doğrulayıcı uygulamasını desteklemezse.

* Yetkili, AAD hesaplarının yapılandırılmış olduğu istenen ortama ayarlanmalıdır.

* İstemci kimliği, uygulamanın istemci kimliğine ayarlanmalıdır.

* `NonBrokerRedirectURI` Uygulama için geçerli bir yeniden yönlendirme URI’sine ayarlanmalıdır.

    * Veya `urn:ietf:wg:oauth:2.0:oob` geçerli bir AAD yeniden yönlendirme URI’si olarak yapılandırılmalıdır.

### SDK’da günlüğü etkinleştirme 

Günlüğe kaydetme, `java.util.logging` çerçevesi aracılığıyla yapılır. Günlükleri almak için [Java teknik kılavuzu](http://docs.oracle.com/javase/6/docs/technotes/guides/logging/overview.html). Uygulamaya bağlı olarak, `App.onCreate` genellikle günlüğe kaydetmeyi başlatmak için en iyi yerdir. Günlük iletileri sınıf adına göre anahtarlanır ve sınıf adı, gizlenmiş olabilir.

## Bilinen Platform Sınırlamaları 

### Dosya Boyutu Sınırlamaları 

Android’de, Dalvik yürütülebilir dosya biçimine ilişkin sınırlamalar, ProGuard olmadan çalışan büyük kod temelleri için sorun oluşturabilir. Özellikle aşağıdaki sınırlamalar görülebilir: 

* Alanlarda 65.000 sınırı.

* Metotlarda 65.000 sınırı.

Çok sayıda proje dahil edilirken, kitaplık sayısı arttıkça alan sayısını önemli ölçüde artıran bir R kopyası her android:package öğesine eklenir. Aşağıdaki öneriler bu sınırlamaları azaltmaya yardımcı olabilir:
 
* Tüm kitaplık projeleri, mümkün olduğunda aynı android:package öğesini paylaşmalıdır. Yalnızca derleme zamanıyla ilgili bir sorun olduğundan, bu durum alanda düzensiz aralıklarla hataya neden olmaz.   Ayrıca, Android SDK'nın daha yeni sürümleri bazı artıklıkları kaldırmak için DEX dosyalarını önceden işler. Bunun yapılması, alanlarla uzaklığı daha da azaltır.

* Mevcut olan en yeni Android SDK derleme araçlarını kullanın.

* Tüm gereksiz ve kullanılmayan kitaplıkları kaldırın (örneğin, `android.support.v4`)

### İlke Zorlama Sınırlamaları

**Ekran Yakalama**: SDK, Activity.onCreate öğesinden zaten geçmiş olan Etkinliklerde yeni bir ekran yakalama ayar değeri uygulayamaz. Bu durum, uygulama ekran görüntülerini devre dışı bırakacak şekilde yapılandırıldığı halde ekran görüntülerinin alınabildiği bir zaman dilimine yol açabilir.

**İçerik Çözümleyicileri Kullanma*: Aktarım veya alma ilkesi, başka bir uygulamadaki içerik sağlayıcısına erişmek için bir içerik çözümleyicisinin kullanılmasını tamamen veya kısmen engelleyebilir. Bu durum ContentResolver yöntemlerinin null döndürmesine veya bir hata değeri oluşturmasına neden olur (örneğin `openOutputStream` engellenirse `FileNotFoundException` oluşturur). Uygulama, içerik çözümleyicisi ile veri yazma hatasının bir ilkeden kaynaklanıp kaynaklanmadığını (veya ilke tarafından kaynaklanabileceğini) şu çağrıyı yaparak belirleyebilir:

    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI)

**Dışarı Aktarılan Hizmetler**: Intune Uygulama SDK’sına dahil edilen `AndroidManifest.xml` dosyası, `MAMNotificationReceiverService`öğesini içerir. Bu öğenin, Şirket Portalı’nın kullanan bir uygulamaya bildirim göndermesine izin vermek üzere dışarı aktarılan bir hizmet olması gerekir. Hizmet, yalnızca Şirket Portalı’nın bildirim göndermesine izin verildiğinden emin olmak için çağıranı denetler. 

## Android için Önerilen En İyi Uygulamalar 

İlkeleri zorunlu kılma işlemi sonucunda hata koşulları daha sık tetiklenebilir, ancak Intune SDK’sı, Android API’si tarafından sağlanan sözleşmeyi korur. Aşağıda belirtilen Android’e yönelik en iyi uygulamalar, hata olasılığını azaltır: 

* Null döndürme olasılığı bulunan Android SDK İşlevleri’nin şu anda da null olma olasılığı daha yüksektir.  Sorunları en aza indirmek için null denetimlerinin doğru yerlerde olduğundan emin olun.

* Denetlenebilir özellikler SDK API'leri aracılığıyla denetlenmelidir.

* Türetilen tüm işlevler üst sınıf sürümlerine çağrılmalıdır.

* Herhangi bir API'yi belirsiz bir şekilde kullanmaktan kaçının. Örneğin, requestCode denetlenmeden `Activity.startActivityForResult/onActivityResult` işlemi garip davranışlara neden olur.



<!--HONumber=Sep16_HO2-->


