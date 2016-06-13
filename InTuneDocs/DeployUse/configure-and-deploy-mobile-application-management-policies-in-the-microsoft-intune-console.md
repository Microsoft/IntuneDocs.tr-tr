---
# required metadata

title: Microsoft Intune konsolunda mobil uygulama yönetimi ilkelerini yapılandırma ve dağıtma | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: b4fb33a8-a2fa-4353-bd89-5bda48b68e83

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Configure and deploy mobile application management policies in the Microsoft Intune console
Microsoft Intune’da mobil uygulama yönetimi ilkeleri, dağıttığınız uygulamaların şirketinizin uyumluluk ve güvenlik ilkelerine uygun hale gelmesi için, bunların işlevselliğini değiştirmenize olanak tanır. Örneğin, yönetilen bir uygulama içinde kesme, kopyalama ve yapıştırma işlemlerini kısıtlayabilir veya bir uygulamayı tüm web bağlantılarını yönetilen bir tarayıcıda açmak üzere yapılandırabilirsiniz.

Mobil uygulama yönetimi ilkeleri desteği:

-   Android 4 ve üzeri çalıştıran cihazlar.

-   iOS 7 ve üzeri çalıştıran cihazlar.

> [!TIP] Mobil uygulama yönetimi ilkeleri Intune kaydı yapılmış cihazları destekler.
>
> Intune tarafından yönetilmeyen cihazlar için uygulama yönetimi ilkeleri oluşturma hakkında bilgi arıyorsanız bkz. [Microsoft Intune ile mobil uygulama yönetimi ilkelerini kullanarak uygulama verilerini koruma](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

Diğer Intune ilkelerinden farklı olarak, mobil uygulama yönetimi ilkeleri doğrudan dağıtılmaz. Bunun yerine, ilke kısıtlamak istediğiniz uygulamayla ilişkilendirilir. Uygulama dağıtılıp cihazlara yüklendiğinde, belirttiğiniz ayarlar geçerli olur.

Bir uygulamaya kısıtlamalar getirmek için, uygulama Microsoft Uygulaması Yazılım Geliştirme Seti'ni (SDK) içermelidir. Böyle bir uygulamayı almanın iki yolu bulunmaktadır:

-   **İlkeyle yönetilen bir uygulama kullanma** – Yerleşik Uygulama SDK’sına sahiptir. Bu uygulama türünü eklemek için, iTunes mağazası veya Google Play gibi bir uygulama mağazasından uygulamaya yönlendiren bir bağlantı belirtirsiniz. Bu uygulama türü için başka bir işleme gerek yoktur. [Microsoft Intune mobil uygulama yönetimi ilkeleri ile kullanabileceğiniz uygulamalar](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) listesine bakın.

-   **‘Sarmalanan’ bir uygulama kullanma** - **Microsoft Intune Uygulaması Sarmalama Aracı** kullanılarak Uygulama SDK'sı eklenip yeniden paketlenmiş uygulamalardır. Bu araç genellikle şirket içinde oluşturulan şirket uygulamalarını işlemek için kullanılır. Uygulama mağazasından yüklenen uygulamaları işlemek için kullanılamaz. Bkz. [iOS uygulamalarını Microsoft Intune Uygulaması Sarmalama Aracı ile mobil uygulama yönetimine hazırlama](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) ve [Android uygulamalarını Microsoft Intune Uygulaması Sarmalama Aracı ile mobil uygulama yönetimine hazırlama](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md).

iOS ve Android için Outlook uygulaması gibi bazı yönetilen uygulamalar **birden çok kimliği** destekler. Başka bir deyişle Intune yalnızca uygulamadaki şirket hesaplarına veya verilere yönetim ayarlarını uygular.

Örneğin, Outlook uygulamasını kullanarak:

-   Kullanıcı bir kurumsal ve kişisel e-posta hesabı yapılandırırsa Intune yönetim ayarlarını yalnızca şirket hesabına uygular ve kişisel hesabı yönetmez.

-   Cihaz kullanımdan kaldırılırsa ve cihazın kaydı kaldırılırsa yalnızca kurumsal Outlook verileri cihazdan kaldırılır.

-   Kullanılan şirket hesabı, cihazı Intune hizmetine kaydetmek için kullanılan hesapla aynı olmalıdır.

> [!TIP] Intune’u Configuration Manager ile birlikte kullanıyorsanız, bkz. [Configuration Manager’da Mobil Uygulama Yönetim İlkeleri Kullanılarak Uygulamaları Denetleme](https://technet.microsoft.com/library/mt131414.aspx).

## Mobil uygulama yönetimi ilkesiyle uygulama oluşturma ve dağıtma

-   **1. Adım:** İlkeyle yönetilen bir uygulamanın bağlantısını alma ve sarmalanan bir uygulama oluşturma.

-   **2. Adım:** Uygulamayı bulut depolama alanınıza yayımlama.

-   **3. Adım:** Mobil uygulama yönetimi ilkesi oluşturma.

-   **4. Adım:** Uygulamayı bir mobil uygulama yönetimi ilkesiyle ilişkilendirme seçeneğini belirleyerek uygulamayı dağıtma.

-   **5. Adım:** Uygulama dağıtımını izleme.

## **1. Adım:** İlkeyle yönetilen bir uygulamanın bağlantısını alma ve sarmalanmış bir uygulama oluşturma.

-   **İlkeyle yönetilen bir uygulamanın bağlantısını almak için** - Uygulama mağazasında, dağıtmak istediğiniz ilkeyle yönetilen uygulamanın URL'sini bulun ve not edin.

    Örneğin, iPad için Microsoft Word uygulamasının URL'si şöyledir: **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**

-   **Sarmalanmış uygulama oluşturmak için** - Sarmalanmış bir uygulama oluşturmak için [iOS uygulamalarını Microsoft Intune Uygulaması Sarmalama Aracı ile mobil uygulama yönetimine hazırlama](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) ve [Android uygulamalarını Microsoft Intune Uygulaması Sarmalama Aracı ile mobil uygulama yönetimine hazırlama](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) konularındaki bilgileri kullanın.

    Araç, uygulamayı bulut depolama alanınızda yayımladığınızda kullanacağınız işlenmiş bir uygulama oluşturur.

## **2. Adım:** Uygulamayı bulut depolama alanınıza yayımlama
Yönetilen bir uygulama yayımladığınızda, ilkeyle yönetilen bir uygulama veya iOS için Microsoft Intune Uygulama Sarmalama Aracı kullanılarak işlenmiş bir uygulama yayımlamanıza bağlı olarak farklı yordamlar kullanılır.

#### İlkeyle yönetilen bir uygulama yayımlama

1.  Uygulamayı bulut depolama alanınıza yüklemeye hazır olduğunuzda [Microsoft Intune’da mobil cihazlar için uygulama ekleme](add-apps-for-mobile-devices-in-microsoft-intune.md) konu başlığı altında verilen yönergeleri izleyin.

2.  iOS uygulamaları için **Bu yazılımın cihazlara nasıl sunulacağını seçin**altında **App Store'dan Yönetilen iOS Uygulaması**seçeneğini belirleyin.

    Android uygulamaları için **Dış bağlantı**seçeneğini belirleyin.

3.   **URL'yi belirtin**altında, daha önce not ettiğiniz ilkeyle yönetilen uygulama için URL'yi girin.

Yükleme tamamlandığında, yüklenen uygulama için **Yazılım Özellikleri** sayfasında **Uygulama Yönetimi İlkeleri** için **Evet** görürsünüz.

Uygulamanın başarıyla karşıya yüklendiğini doğruladıktan sonra, 3. adıma ilerleyin.

#### Microsoft Intune Uygulaması Sarmalama Aracı kullanılarak işlenmiş bir uygulamayı yayımlamak için

1.  Uygulamayı bulut depolama alanınıza yüklemeye hazır olduğunuzda [Microsoft Intune’da mobil cihazlar için uygulama ekleme](add-apps-for-mobile-devices-in-microsoft-intune.md) konu başlığı altında verilen yönergeleri izleyin.

2.   **Bu yazılımın cihazlara nasıl sunulacağını seçin**altında **Yazılım Yükleyici**'yi seçin.

3.  **Yazılım yükleyicisi dosya türü** altında **iOS için uygulama paketi (&#42;.ipa dosyası)** öğesini seçin.

Yükleme tamamlandığında, yüklenen uygulama için **Yazılım Özellikleri** sayfasında **Uygulama Yönetimi İlkeleri** için **Evet** görürsünüz.

Uygulamanın başarıyla karşıya yüklendiğini doğruladıktan sonra, 3. adıma ilerleyin.

## **3. Adım:** Mobil uygulama yönetimi ilkesi oluşturma

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **İlke** &gt; **Genel Bakış** &gt; **İlke Ekle**’ye tıklayın.

2.  Uygulamaları yapılandırmak istediğiniz cihaz türüne bağlı olarak, şu **Yazılım** ilkelerinden birini yapılandırın ve dağıtın:

    -   **Mobil Uygulama Yönetimi İlkesi (Android 4 ve üzeri)**

    -   **Mobil Uygulama Yönetimi İlkesi (iOS 7 ve üzeri)**

    Önerilen ayarları kullanabilir veya ayarları özelleştirebilirsiniz. Ayrıntılar için bkz. [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Aşağıdaki ayarları gerektiği gibi yapılandırın. Seçenekler, ilkeyi yapılandırdığınız cihaz türüne bağlı olarak değişebilir.

|Ayar adı|Ayrıntılar|
    |---------|--------------------|
    |**Ad**|Bu kural için bir ad belirtin.|
    |**Açıklama**|İsteğe bağlı olarak, bu ilke için bir açıklama belirtin.|
    |**Web içeriğini kurumsal olarak yönetilen bir tarayıcıda görüntülemek üzere kısıtlayın**|Bu ayar etkinleştirildiğinde, uygulamadaki tüm bağlantılar Yönetilen Tarayıcıda açılır. Bu seçeneğin çalışması için bu uygulamayı cihazlara dağıtmış olmanız gerekir.|
    |**Android yedeklemelerini engelle** veya **iTunes ve iCloud yedeklemelerini engelle**|Uygulamadaki bilgilerin yedeklenmesini devre dışı bırakır.|
    |**Uygulamanın diğer uygulamalara veri aktarmasına izin ver**|Bu uygulamanın veri gönderebileceği uygulamaları belirtir. Hiçbir uygulamaya veri aktarmaya izin vermemeyi, yalnızca diğer yönetilen uygulamalara aktarmaya izin vermeyi veya tüm uygulamalara aktarmaya izin vermeyi seçebilirsiniz. Bu ayar, mobil cihazlardaki **Birlikte Aç** özelliğinin kullanımını denetlemez.<br /><br />Örneğin, veri aktarımı izin vermezseniz SMS iletisi, kişilere görüntü atama ve Facebook veya Twitter'da paylaşma gibi hizmetler için veri aktarımını sınırlamış olursunuz.<br /><br />iOS cihazlar için yönetilen ve yönetilmeyen uygulamalar arasında belge aktarımını önlemek için **Diğer yönetilmeyen uygulamalardaki yönetilen belgelere izin ver** ayarını devre dışı bırakan bir mobil cihaz güvenlik ilkesi de yapılandırıp dağıtmanız gerekir. Yalnızca diğer yönetilen uygulamalara aktarıma izin vermeyi seçerseniz ilgili türlerin içeriğini açmak için Intune PDF ve resim görüntüleyiciler (dağıtılmışsa) kullanılır.<br /><br />Ayrıca, bu seçeneği **İlke ile Yönetilen Uygulamalar** veya **Hiçbiri** olarak ayarlarsanız uygulamaların içindeki verileri aramak için Spotlight Arama özelliğine imkan tanıyan iOS 9 özelliği engellenir.|
    |**Uygulamanın diğer uygulamalardan veri almasına izin ver**|Bu uygulamanın veri alabileceği uygulamaları belirtir. Hiçbir uygulamadan veri aktarmaya izin vermemeyi, yalnızca diğer yönetilen uygulamalardan aktarmaya izin vermeyi veya tüm uygulamalardan aktarmaya izin vermeyi seçebilirsiniz.<br /><br />Çoklu kimliği destekleyen iOS uygulamaları için (burada Intune yönetim ayarlarını yalnızca şirket hesaplarına veya uygulamadaki verilere uygular), mobil uygulama yönetimi ilkesinin uygulandığı bir kayıtlı cihazda kullanıcı bir mobil uygulama yönetimi ilkesi tarafından yönetilmeyen bir uygulamadan verilere eriştiğinde, veriler şirket verisi olarak kabul edilir ve ilke tarafından korunur.|
    |**“Farklı Kaydet”i önleme**|Kişisel bulut depolama konumlarına (OneDrive Personal veya Dropbox gibi) veri kaydetmeyi sağlayan **Farklı Kaydet** seçeneğinin kullanımını devre dışı bırakır.|
    |**Diğer uygulamalarla kesme, kopyalama ve yapıştırmayı kısıtlama**|Uygulamayla kesme, kopyalama ve yapıştırma işlemlerinin nasıl kullanılacağını belirtir. Aşağıdakilerden birini seçin:<br /><br />**Engellendi** – Bu uygulama ve diğer uygulama arasında kesme, kopyalama ve yapıştırma işlemlerine izin verilmez.<br /><br />**İlkeyle Yönetilen Uygulamalar** – Yalnızca bu uygulama ve diğer yönetilen uygulamalar arasında kesme, kopyalama ve yapıştırma işlemlerine izin verilir.<br /><br />**İçine Yapıştırmayla İlke ile Yönetilen Uygulamalar** – Bu uygulamadan kesilen veya kopyalanan verilerin yalnızca diğer yönetilen uygulamalara yapıştırılmasına izin verilir. Herhangi bir uygulamadan kesilen veya kopyalanan verilerin bu uygulamaya yapıştırılmasına izin verilir.<br /><br />**Herhangi Bir Uygulama** – Bu uygulamaya veya bu uygulamadan kesme, kopyalama ve yapıştırma işlemleriyle ilgili bir kısıtlama yoktur.<br /><br />Yönetilen uygulamalar arasında veri kopyalama ve yapıştırma işlemi yapılabilmesi için her iki uygulamada da **İlke ile Yönetilen Uygulamalar** veya **İçine Yapıştırmayla İlke ile Yönetilen Uygulamalar** ayarlarının yapılandırılmış olması gerekir.|
    |**Erişim için basit PIN gerektir**|Kullanıcının bu uygulamayı kullanmak için bir PIN belirtmesini gerektirir. Kullanıcıdan uygulamayı ilk kez çalıştırdığında bunu ayarlaması istenir.|
    |**PIN sıfırlanmadan önce deneme sayısı**|Kullanıcının PIN'i sıfırlaması gerekmeden önce yapılabilecek PIN girişi deneme sayısını belirtin.|
    |**Erişim için kurumsal kimlik bilgileri gerektir**|Kullanıcının uygulamaya erişmek için kurumsal oturum açma bilgilerini belirtmesini gerektirir.|
    |**Erişim için kurumsal ilkeyle cihaz uyumluluğu gerektir**|Uygulamanın yalnızca cihazın güvenliği kırılmamışsa kullanılmasına izin verilir.|
    |**Erişim gereksinimlerini şu süreden sonra yeniden denetle (dakika)**| **Zaman aşımı** alanında, uygulama için erişim gereksinimlerinin uygulama başlatıldıktan sonra yeniden denetleneceği zaman aralığını belirtin.|
    |**Çevrimdışı kullanım süresi**|Cihaz çevrimdışı ise, uygulama erişim gereksinimlerini yeniden denetlenmeden önceki zaman aralığını belirtin.|
    |**Uygulama verilerini şifreleme**|SD kartlar gibi harici olarak depolanan veriler dahil uygulamayla ilişkili tüm verilerin şifreleneceğini belirtir.<br /><br />**iOS için şifreleme**<br /><br />Bir Intune mobil uygulama yönetimi ilkesiyle ilişkilendirilmiş uygulamalar için, veriler işletim sistemi tarafından sağlanan cihaz düzeyinde şifreleme kullanılarak şifrelenir. Bu, BT yöneticisi tarafından ayarlanması gereken cihaz PIN ilkesi üzerinden etkinleştirilir. Bir PIN istendiğinde, veriler mobil uygulama yönetimi ilkesi ayarlarına göre şifrelenir. Apple belgelerinde belirtildiği gibi, [iOS 7 tarafından kullanılan modüller FIPS 140-2 sertifikalıdır](http://support.apple.com/en-us/HT202739).<br /><br />**Android için şifreleme**<br /><br />Bir Intune mobil uygulama yönetimi ilkesiyle ilişkilendirilmiş uygulamalar için, şifreleme Microsoft tarafından sağlanır. Veriler, dosya G/Ç işlemleri sırasında eş zamanlı olarak şifrelenir.  Cihaz depolamasındaki içerik her zaman şifrelenir. Şifreleme yöntemi FIPS 140-2 sertifikalı değildir.|
    |**Ekran yakalamayı engelle** (yalnızca Android cihazlar)|Bu uygulama kullanılırken cihazın ekran yakalama özelliklerinin engellendiğini belirtir.|

4.  İşiniz bittiğinde **İlkeyi Kaydet**'e tıklayın.

Yeni ilke, **İlke** çalışma alanının **Yapılandırma İlkeleri** düğümünde görüntülenir.

## **4. Adım:** Uygulamayı bir mobil uygulama yönetimi ilkesiyle ilişkilendirme seçeneğini belirleyerek uygulamayı dağıtma.
İlkeyi uygulamayla ilişkilendirmek için **Mobil Uygulama Yönetimi** sayfasında mobil uygulama yönetimi ilkesini seçtiğinizden emin olarak uygulamayı dağıtın.

Ayrıntılar için bkz. [Microsoft Intune'da uygulamaları dağıtma](deploy-apps.md).

> [!IMPORTANT] iOS 7.1'den önceki işletim sistemlerini çalıştıran cihazlar için, uygulama kaldırıldığında ilişkili ilke kaldırılmaz.
>
> Cihazın Intune kaydı kaldırılırsa, ilkeler uygulamalardan kaldırılmaz; ilkenin geçerli olduğu uygulamalarda, uygulama kaldırılıp yeniden yüklense bile ilke ayarları korunur.

### Bir uygulama cihazlarda zaten dağıtıldıysa yapılacaklar
Bir uygulama dağıttığınız ve hedef kullanıcı veya cihazlardan birinde uygulamanın yönetilmeyen bir sürümünün zaten yüklü olduğu durumlar olabilir (örneğin, kullanıcı uygulama mağazasından Microsoft Word’ü yüklemiştir).

Bu durumda, yapılandırdığınız yönetilen sürümün yüklenebilmesi için kullanıcıdan yönetilmeyen sürümü el ile kaldırmasını isteyebilirsiniz.

Ancak, iOS 9 ve üstü sürümleri çalıştıran cihazlarda Intune, kullanıcıdan mevcut uygulamanın yönetimini almak için otomatik olarak izin ister. Kullanıcının kabul etmesi durumunda uygulama Intune tarafından yönetilir hale gelir ve uygulamayla ilişkilendirdiğiniz tüm mobil uygulama yönetimi ilkeleri de geçerli olur.

> [!TIP] Cihaz denetimli moddaysa, Intune kullanıcıdan izin istemeden mevcut uygulamanın yönetimini devralır.

## **5. Adım:** Uygulama dağıtımını izleme.
Bir mobil uygulama yönetimi ilkesiyle ilişkili bir uygulama oluşturup dağıttıktan sonra, uygulamayı izlemek ve ilke çakışmalarını çözmek için aşağıdaki yordamları kullanın.

#### Dağıtım durumunu görüntülemek için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com) **Gruplar** &gt; **Genel bakış**’a tıklayın.

2.  Aşağıdaki adımlardan birini gerçekleştirin:

    -   **Tüm Kullanıcılar**'a tıklayın ve ardından cihazlarını incelemek istediğiniz kullanıcıya çift tıklayın. **Kullanıcı Özellikleri** sayfasında **Cihazlar**'a tıklayın ve ardından incelemek istediğiniz cihaza çift tıklayın.

    -   **Tüm Cihazlar** &gt; **Tüm Mobil Cihazlar**’a tıklayın. **Cihaz Grubu Özellikleri** sayfasında **Cihazlar**'a tıklayın ve ardından incelemek istediğiniz cihaza çift tıklayın.

3.   **Mobil Cihaz Özellikleri** sayfasında, cihaza dağıtılan mobil uygulama yönetimi ilkelerinin bir listesini görmek için **İlke** 'ye tıklayın.

4.  Durumunu görüntülemek istediğiniz mobil uygulama yönetimi ilkesini seçin. İlkenin ayrıntılarını alt bölmede görüntüleyebilir ve ayarlarını görüntülemek için düğümü genişletebilirsiniz.

5.  Her bir mobil uygulama yönetimi ilkesinin **Durum** sütununun altında, **Uyumlu**, **Uyumlu (Bekleniyor)**veya **Hata** görüntülenir. Seçili ilkede bir veya daha fazla çakışan ayar varsa, bu alanda **Hata** görüntülenir.

6.  Bir çakışma belirledikten sonra, çakışan ilke ayarlarını aynı ayarı kullanacak şekilde gözden geçirebilir veya uygulama ve kullanıcıya yalnızca bir ilkeyi dağıtabilirsiniz.

### İlke çakışmalarını çözümleme
Kullanıcı veya cihaza ilk dağıtımda bir mobil uygulama yönetimi ilkesi çakışması olursa, çakışmaya neden olan ayar değeri uygulamaya dağıtılan ilkeden kaldırılır ve uygulama yerleşik bir çakışma değeri kullanır.

Kullanıcı veya cihaza daha sonraki dağıtımlarda bir mobil uygulama yönetimi ilkesi çakışması olursa, çakışmaya neden olan ayar değeri uygulamaya dağıtılan mobil uygulama yönetimi ilkesinde güncelleştirilmez ve uygulama bu ayar için mevcut değeri kullanır.

Cihaz veya kullanıcının çakışan iki ilke aldığı durumlarda, aşağıdaki davranış geçerlidir:

-   Bir ilke cihaza zaten dağıtıldıysa, mevcut ilke ayarları geçersiz kılınmaz.

-   Cihaza hiçbir ilke dağıtılmadıysa ve çakışan iki ayar dağıtılırsa, cihazda yerleşik olarak bulunan varsayılan ayar kullanılır.


<!--HONumber=May16_HO3-->


