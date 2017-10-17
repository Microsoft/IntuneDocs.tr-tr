---
title: "Intune konsolundaki MAM ilkelerini yapılandırma"
description: "Microsoft Intune’daki Mobil uygulama yönetimi ilkeleri, dağıttığınız uygulamaların şirketin uyumluluk ve güvenlik ilkeleriyle uyumlu olmasını sağlamak için bunların işlevselliğini değiştirmenize izin verir."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 03/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b4fb33a8-a2fa-4353-bd89-5bda48b68e83
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 881180fec0fe4fca8b49106bcae6ea1ecd52c2eb
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/10/2017
---
# <a name="configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console"></a>Microsoft Intune konsolunda mobil uygulama yönetimi ilkelerini yapılandırma ve dağıtma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune’daki Mobil uygulama yönetimi (MAM) ilkeleri, dağıttığınız uygulamaların şirketin uyumluluk ve güvenlik ilkeleriyle uyumlu olmasını sağlamak için bunların işlevselliğini değiştirmenize izin verir. Örneğin, yönetilen bir uygulama içinde kesme, kopyalama ve yapıştırma işlemlerini kısıtlayabilir veya bir uygulamayı yönetilen bir tarayıcı içindeki tüm web bağlantılarını açacak şeklide yapılandırabilirsiniz.

Mobil uygulama yönetimi ilkeleri desteği:

-   Android 4 ve üzeri çalıştıran cihazlar.

-   iOS 8.0 ve üzeri çalıştıran cihazlar.

> [!TIP]
> Mobil uygulama yönetimi ilkeleri Intune kaydı yapılmış cihazları destekler.
>
> Intune tarafından yönetilmeyen cihazlar için uygulama yönetim ilkeleri oluşturma hakkında bilgi arıyorsanız bkz. [Microsoft Intune ile mobil uygulama yönetim ilkeleri kullanarak uygulama verilerini koruma](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

Diğer Intune ilkelerinden farklı olarak, mobil uygulama yönetimi ilkeleri doğrudan dağıtılmaz. Bunun yerine, ilke kısıtlamak istediğiniz uygulamayla ilişkilendirilir. Uygulama dağıtılıp cihazlara yüklendiğinde, belirttiğiniz ayarlar devreye girer.

Bir uygulamaya kısıtlamalar uygulamak için, uygulamanın Microsoft Intune Uygulama SDK’sini içermesi gerekir. Bu tür bir uygulamayı edinmenin üç yolu vardır:

-   **İlkeyle yönetilen uygulama kullanma**. İlkeyle yönetilen bir uygulamada Uygulama SDK’sı yerleşiktir. Bu uygulama türünü eklemek için, iTunes mağazası veya Google Play gibi bir uygulama mağazasından uygulamaya yönlendiren bir bağlantı belirtirsiniz. Bu uygulama türü için başka bir işleme gerek yoktur. Daha fazla bilgi için [Microsoft Intune mobil uygulama yönetim ilkeleriyle kullanabileceğiniz uygulamaların listesine](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) bakın.

-   **Kaydırılmış bir uygulama kullanın**. Kaydırılmış bir uygulama, Uygulama SDK'sını dahil etmek için Microsoft Intune Uygulama Kaydırma Aracı kullanılarak yeniden paketlenmiş bir uygulamadır. Bu araç genellikle şirket içinde oluşturulan şirket uygulamalarını işlemek için kullanılır. Uygulama mağazasından indirilmiş uygulamaları işlemek için kullanamazsınız. Daha fazla bilgi için bkz. [iOS uygulamalarını Microsoft Intune Uygulaması Kaydırma Aracı ile mobil uygulama yönetimine hazırlama](/intune/app-wrapper-prepare-ios) ve [Android uygulamalarını Microsoft Intune Uygulaması Kaydırma Aracı ile mobil uygulama yönetimine hazırlama](/intune/app-wrapper-prepare-android).

- **Intune Uygulama SDK’sını içeren uygulamayı kendiniz yazın**. Intune Uygulama SDK’sı, uygulama yönetim özelliklerini bir uygulamayı yazarken eklemenize izin verir. Daha fazla bilgi için bkz. [Intune Uygulama SDK’sına Genel Bakış](/intune/app-sdk).
/intune/apps-prepare-mobile-application-management Uygulama Paketleme Aracı ile Intune Uygulama SDK’sı arasında seçim yapma konusunda yardım için bkz. [Microsoft Intune ile uygulamaların mobil uygulama yönetimine nasıl hazırlanacağına karar verme](/intune/apps-prepare-mobile-application-management).

iOS ve Android için Outlook uygulaması gibi bazı yönetilen uygulamalar *birden çok kimliği* destekler. Başka bir deyişle, Intune, yönetim ayarlarını yalnızca uygulamadaki şirket hesaplarına veya verilere uygular.

Örneğin, Outlook uygulamasını kullanarak:

-   Kullanıcı kurumsal bir e-posta hesabı ve kişisel bir e-posta hesabı yapılandırırsa, Intune yönetim ayarlarını yalnızca şirket hesabına uygular ve kişisel hesabı yönetmez.

-   Cihaz kullanımdan kaldırılır veya cihazın kaydı silinirse, cihazdan yalnızca kurumsal Outlook verileri kaldırılır.

-   Şirket hesabı, cihazı Intune hizmetine kaydetmek için kullanılan hesapla aynı olmalıdır.

> [!TIP]
> Intune’u Configuration Manager ile birlikte kullanıyorsanız, bkz. [ Configuration Manager’da Mobil Uygulama Yönetim İlkeleri Kullanılarak Uygulamaları Denetleme](https://technet.microsoft.com/library/mt131414.aspx).

## <a name="create-and-deploy-an-app-with-a-mobile-application-management-policy"></a>Mobil uygulama yönetimi ilkesiyle uygulama oluşturma ve dağıtma

-   **1. Adım:** İlkeyle yönetilen bir uygulamaya bir bağlantı alma, kaydırılmış bir uygulama oluşturma veya MAM özellikli uygulama yazmak için Intune Uygulama SDK’sını kullanma.

-   **2. Adım:** Uygulamayı bulut depolama alanınıza yayımlama.

-   **3. Adım:** Mobil uygulama yönetimi ilkesi oluşturma.

-   **4. Adım:** Uygulamayı bir mobil uygulama yönetimi ilkesiyle ilişkilendirme seçeneğini belirleme ve sonra uygulamayı dağıtma.

-   **5. Adım:** Uygulama dağıtımını izleme.

## <a name="step-1-get-the-link-to-a-policy-managed-app-create-a-wrapped-app-or-use-the-intune-app-sdk-to-write-a-mam-enabled-app"></a>1. Adım: İlkeyle yönetilen bir uygulamaya bir bağlantı alma, kaydırılmış bir uygulama oluşturma veya MAM özellikli uygulama yazmak için Intune Uygulama SDK’sını kullanma

Uygulama mağazasından, dağıtmak istediğiniz ilkeyle yönetilen uygulamanın URL'sini bulun ve not edin. Örneğin, iPad için Microsoft Word uygulamasının URL'si şöyledir: **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.


## <a name="step-2-publish-the-app-to-your-cloud-storage-space"></a>2. Adım: Uygulamayı bulut depolama alanınıza yayımlama
Yönetilen bir uygulama yayımladığınızda, ilkeyle yönetilen bir uygulama veya iOS için Microsoft Intune Uygulama Kaydırma Aracı kullanılarak işlenmiş bir uygulama yayımlamanıza bağlı olarak farklı yordamlar kullanılır.

#### <a name="to-publish-a-policy-managed-app"></a>İlkeyle yönetilen bir uygulama yayımlama

1.  Uygulamayı bulut depolama alanınıza yüklemeye hazır olduğunuzda [Microsoft Intune’da mobil cihazlar için uygulama ekleme](add-apps-for-mobile-devices-in-microsoft-intune.md) konu başlığı altında verilen yönergeleri izleyin.

2.  iOS uygulamalarında, **Bu yazılımın cihazlar için kullanılabilir duruma nasıl getirileceğini seçin** altından **App Store'dan Yönetilen iOS Uygulaması** seçeneğini belirleyin.

    Android uygulamaları için **Dış bağlantı**seçeneğini belirleyin.

3.  **URL'yi belirtin**altında, daha önce not ettiğiniz ilkeyle yönetilen uygulama için URL'yi girin.

Yükleme bittiğinde, yüklenen uygulama için **Yazılım Özellikleri** sayfasında **Uygulama Yönetimi İlkeleri** için **Evet**’i görürsünüz.

Uygulamanın başarıyla karşıya yüklendiğini doğruladıktan sonra 3. adıma ilerleyin.

#### <a name="to-publish-an-app-that-was-processed-through-the-microsoft-intune-app-wrapping-tool"></a>Microsoft Intune Uygulama Kaydırma Aracı kullanılarak işlenmiş bir uygulamayı yayımlamak için

1.  Uygulamayı bulut depolama alanınıza yüklemeye hazır olduğunuzda [Microsoft Intune’da mobil cihazlar için uygulama ekleme](add-apps-for-mobile-devices-in-microsoft-intune.md) konu başlığı altında verilen yönergeleri izleyin.

2.  **Bu yazılımın cihazlar için kullanılabilir duruma nasıl getirileceğini seçin** altından **Yazılım Yükleyici**'yi seçin.

3.  **Yazılım yükleyicisi dosya türü** altında **iOS için uygulama paketi (&#42;.ipa dosyası)** öğesini seçin.

Yükleme bittiğinde, yüklenen uygulama için **Yazılım Özellikleri** sayfasında **Uygulama Yönetimi İlkeleri** için **Evet**’i görürsünüz.

Uygulamanın başarıyla karşıya yüklendiğini doğruladıktan sonra 3. adıma ilerleyin.

## <a name="step-3-create-a-mobile-application-management-policy"></a>3. Adım: Mobil uygulama yönetimi ilkesi oluşturma

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com), **İlke** &gt; **Genel Bakış** &gt; **İlke Ekle**’yi seçin.

2.  Uygulama yapılandırmak istediğiniz cihaz türüne bağlı olarak, aşağıdaki **Yazılım** ilkelerinden birini yapılandırın ve dağıtın:

    -   **Mobil Uygulama Yönetimi İlkesi (Android 4 ve üzeri)**

    -   **Mobil Uygulama Yönetimi İlkesi (iOS 8.0 ve üzeri)**

    Önerilen ayarları kullanabilir veya ayarları özelleştirebilirsiniz. Ayrıntılar için bkz. [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Aşağıdaki ayarları gerektiği gibi yapılandırın. Seçenekler, ilkeyi yapılandırdığınız cihaz türüne bağlı olarak değişebilir.

|Ayar adı|Ayrıntılar|
    |---------|--------------------|
    |**Ad**|Bu kural için bir ad belirtin.|
    |**Açıklama**|İsteğe bağlı olarak, bu ilke için bir açıklama belirtin.|
    |**Web içeriğini kurumsal olarak yönetilen bir tarayıcıda görüntülemek üzere kısıtlayın**|Bu ayar etkinleştirildiğinde, uygulamadaki tüm bağlantılar yönetilen tarayıcıda açılır. Bu seçeneğin çalışması için bu uygulamayı cihazlara dağıtmış olmanız gerekir.|
    |**Android yedeklemelerini engelle** veya **iTunes ve iCloud yedeklemelerini engelle**|Bu ayar, uygulamadaki bilgilerin yedeklenmesini devre dışı bırakır.|
    |**Uygulamanın diğer uygulamalara veri aktarmasına izin ver**|Bu ayar, bu uygulamanın veri gönderebileceği uygulamaları belirtir. Hiçbir uygulamaya veri aktarmaya izin vermemeyi, yalnızca diğer yönetilen uygulamalara aktarmaya izin vermeyi veya tüm uygulamalara aktarmaya izin vermeyi seçebilirsiniz. <br /><br />Örneğin, veri aktarımı izin vermezseniz SMS iletisi, kişilere görüntü atama ve Facebook veya Twitter'da paylaşma gibi hizmetler için veri aktarımını sınırlamış olursunuz.<br /><br />iOS cihazlar için, yönetilen ve yönetilmeyen uygulamalar arasında belge aktarımını önlemek üzere, ayrıca **Diğer yönetilmeyen uygulamalarda yönetilen belgelere izin ver**ayarını devre dışı bırakan bir mobil cihaz güvenlik ilkesi yapılandırmanız ve dağıtmanız gerekir. Yalnızca diğer yönetilen uygulamalara aktarmaya izin vermeyi seçerseniz, ilgili türdeki içeriğin açılması için (dağıtıldıysa) Intune PDF ve resim görüntüleyiciler kullanılır.<br /><br />Ayrıca, bu seçeneği **İlke ile Yönetilen Uygulamalar** veya **Hiçbiri** olarak ayarlarsanız uygulamaların içindeki verileri aramak için Spotlight Arama özelliğine imkan tanıyan iOS 9 özelliği engellenir.<br><br>Bu ayar, mobil cihazlardaki Birlikte Aç özelliğinin kullanımını denetlemez. Birlikte Aç’ı yönetmek için bkz. [Microsoft Intune ile iOS uygulamaları arasında veri aktarımını yönetme](manage-data-transfer-between-ios-apps-with-microsoft-intune.md).|
    |**Uygulamanın diğer uygulamalardan veri almasına izin ver**|Bu ayar, bu uygulamanın veri alabileceği uygulamaları belirtir. Hiçbir uygulamadan veri aktarmaya izin vermemeyi, yalnızca diğer yönetilen uygulamalardan aktarmaya izin vermeyi veya tüm uygulamalardan aktarmaya izin vermeyi seçebilirsiniz.<br /><br />Bir kullanıcı bir mobil uygulama yönetim ilkesiyle yönetilmeyen bir uygulamaya eriştiğinde, verilerin şirket verisi olduğu ve ilkeyle korunduğu kabul edilir. Bu durum, birden çok kimliği destekleyen (Intune’un yönetim ayarlarını yalnızca kurumsal hesaplara veya uygulamadaki verilere uyguladığı) iOS uygulamaları için geçerlidir. Aynı şekilde bu durum bir mobil uygulama yönetim ilkesi uygulanmış kayıtlı bir cihaz için de geçerlidir.|
    |**“Farklı Kaydet”i önleme**|Bu ayar, bu ilkeyi kullanan tüm uygulamalarda (OneDrive veya Dropbox gibi) kişisel bulut depolama konumlarına veri kaydetmek üzere **Farklı Kaydet** seçeneğini kullanmayı devre dışı bırakır.|
    |**Diğer uygulamalarla kesme, kopyalama ve yapıştırmayı kısıtlama**|Bu ayar, uygulamayla kesme, kopyalama ve yapıştırma işlemlerinin nasıl kullanılacağını belirtir. Aşağıdakilerden birini seçin:<br /><br />**Engellendi**. Bu uygulama ile başka uygulamalar arasında kesme, kopyalama ve yapıştırma işlemlerine izin vermez.<br /><br />**İlkeyle Yönetilen Uygulamalar**. Yalnızca bu uygulama ile başka yönetilen uygulamalar arasında kesme, kopyalama ve yapıştırma işlemlerine izin verir.<br /><br />**İlkeyle Yönetilen İçine Yapıştırmalı Uygulamalar**. Bu uygulamadan kesilen veya kopyalanan verilerin yalnızca başka yönetilen uygulamalara yapıştırılmasına izin verir. Herhangi bir uygulamadan kesilen veya kopyalanan verilerin bu uygulamaya yapıştırılmasına izin verir.<br /><br />**Herhangi bir Uygulama**. Bu uygulama ile başkaları arasındaki kesme, kopyalama ve yapıştırma işlemlerine hiçbir kısıtlama koymaz.<br /><br />Yönetilen uygulamalar arasında veri kopyalamak ve yapıştırmak için her iki uygulamada da **İlkeyle Yönetilen Uygulamalar** veya **İlkeyle Yönetilen İçine Yapıştırmalı Uygulamalar** ayarının yapılandırılmış olması gerekir.|
    |**Erişim için basit PIN gerektir**|Bu ayar, bu uygulamayı kullanmak için kullanıcının kendi belirlediği bir PIN girmesini gerektirir. Kullanıcıdan uygulamayı ilk kez çalıştırdığında bunu ayarlaması istenir.|
    |**PIN sıfırlanmadan önce deneme sayısı**|Kaç PIN girişi denemesinden sonra kullanıcının PIN'i sıfırlaması gerekeceğini belirtin.|
    |**Erişim için kurumsal kimlik bilgileri gerektir**|Bu ayar, uygulamaya erişmek için kullanıcının kurumsal oturum açma bilgilerini girmesini gerektirir.|
    |**Erişim için kurumsal ilkeyle cihaz uyumluluğu gerektir**|Bu ayar, yalnızca cihazın yazılım kilidi kırılmış veya cihaza kök erişim izni verilmişse uygulamanın kullanılmasına izin verir.|
    |**Erişim gereksinimlerini şu süreden sonra yeniden denetle (dakika)**|**Zaman aşımı** alanında, uygulama açıldıktan sonra uygulama erişim gereksinimlerinin yeniden denetlenmesine kadar geçecek süreyi belirtin.|
    |**Çevrimdışı yetkisiz kullanım süresi**|Cihaz çevrimdışı ise, uygulama erişim gereksinimlerini yeniden denetlenmeden önceki zaman aralığını belirtin.|
    |**Uygulama verilerini şifreleme**|Bu ayar, bu uygulama ile ilişkili tüm verilerin şifreleneceğini belirtir. Buna SD kart gibi harici ortamlara depolanacak veriler de dahildir.<br /><br />**iOS için şifreleme**<br /><br />Bir Intune mobil uygulama yönetim ilkesiyle ilişkilendirilmiş uygulamalarda veriler, kullanılmadıkları sırada ve işletim sisteminin sağladığı cihaz düzeyinde şifreleme kullanılarak şifrelenir. Bu ayar, BT yöneticisinin ayarladığı cihaz PIN ilkesi üzerinden etkinleştirilir. Bir PIN istendiğinde, veriler mobil uygulama yönetimi ilkesindeki ayarlara göre şifrelenir. Apple belgelerinde belirtildiği gibi, [iOS tarafından kullanılan modüller FIPS 140-2 sertifikalıdır](http://support.apple.com/HT202739).<br /><br />**Android için şifreleme**<br /><br />Bir Intune mobil uygulama yönetimi ilkesiyle ilişkilendirilmiş uygulamalarda şifrelemeyi Microsoft sağlar. Veriler, dosya G/Ç işlemleri sırasında eş zamanlı olarak şifrelenir.  Cihaz depolamasındaki içerik her zaman şifrelenir. Şifreleme yöntemi yalnızca Samsung KNOX cihazları için FIPS 140-2 uyumludur.|
    |**Ekran yakalamayı engelle** (yalnızca Android cihazlar)|Bu ayar, birisi bu uygulamayı kullanırken cihazın ekran yakalama özelliklerinin engellendiğini belirtir.|

4. İşiniz bittiğinde **İlkeyi Kaydet**'e tıklayın.

Yeni ilke, **İlke** çalışma alanının **Yapılandırma İlkeleri** düğümünde görünür.

## <a name="step-4-associate-the-app-with-a-mobile-application-management-policy-and-then-deploy-the-app"></a>4. Adım: Uygulamayı bir mobil uygulama yönetimi ilkesiyle ilişkilendirme seçeneğini belirleme ve sonra uygulamayı dağıtma
İlkeyi uygulamayla ilişkilendirmek için **Dağıtımı Yönet** iletişim kutusunun **Mobil Uygulama Yönetimi** sayfasında mobil uygulama yönetim ilkesini seçtiğinizden emin olun.

Ayrıntılar için bkz. [Microsoft Intune'da uygulamaları dağıtma](deploy-apps.md).

> [!IMPORTANT]
> Cihazın Intune kaydı silinirse, ilkeler uygulamadan kaldırılmaz. İlke uygulanmış uygulamalar, uygulama kaldırılıp yeniden yüklendikten sonra ilke ayarlarını saklar.

### <a name="what-to-do-when-an-app-is-already-deployed-on-devices"></a>Bir uygulama cihazlarda zaten dağıtıldıysa yapılacaklar
Bir uygulama dağıttığınız ve hedef kullanıcı ya da cihazlardan birinde uygulamanın yönetilmeyen bir sürümünün zaten yüklü olduğu durumlar olabilir. Örneğin, kullanıcı uygulama mağazasından Microsoft Word yüklemiş olabilir.

Bu durumda, yapılandırdığınız yönetilen sürümün yüklenebilmesi için kullanıcıdan yönetilmeyen sürümü el ile kaldırmasını isteyebilirsiniz.

Ancak, iOS 9 ve üstü sürümleri çalıştıran cihazlarda Intune, kullanıcıdan mevcut uygulamanın yönetimini almak için otomatik olarak izin ister. Kullanıcının kabul etmesi durumunda uygulama Intune tarafından yönetilir hale gelir ve uygulamayla ilişkilendirdiğiniz tüm mobil uygulama yönetim ilkeleri de geçerli olur.

> [!TIP]
> Cihaz denetimli moddaysa, Intune, kullanıcıdan izin istemeden mevcut uygulamanın yönetimini devralır.

## <a name="step-5-monitor-the-app-deployment"></a>5. Adım: Uygulama dağıtımını izleme
Bir mobil uygulama yönetimi ilkesiyle ilişkilendirilmiş bir uygulama oluşturup dağıttıktan sonra, uygulamayı izlemek ve ilke çakışmalarını çözmek için aşağıdaki yordamları kullanın.

#### <a name="to-view-the-status-of-the-deployment"></a>Dağıtım durumunu görüntülemek için

1.  [Microsoft Intune yönetim konsolunda](https://manage.microsoft.com), **Gruplar** &gt; **Genel Bakış**’ı seçin.

2.  Aşağıdaki adımlardan birini gerçekleştirin:

    -   **Tüm Kullanıcılar**’ı seçin, sonra cihazını incelemek istediğiniz kullanıcıya çift tıklayın. **Kullanıcı Özellikleri** sayfasında **Cihazlar**’ı seçin, sonra incelemek istediğiniz cihaza çift tıklayın.

    -   **Tüm Cihazlar** &gt; **Tüm Mobil Cihazlar**’ı seçin. **Cihaz Grubu Özellikleri** sayfasında **Cihazlar**’ı seçin, sonra incelemek istediğiniz cihaza çift tıklayın.

3.  **Mobil Cihaz Özellikleri** sayfasında, cihaza dağıtılmış mobil uygulama yönetim ilkelerinin bir listesini görmek için **İlke**’yi seçin.

4.  Durumunu görüntülemek istediğiniz mobil uygulama yönetimi ilkesini seçin. İlkenin ayrıntılarını alt bölmede görüntüleyebilir ve ayarlarını görüntülemek için düğümü genişletebilirsiniz.

5.  Her bir mobil uygulama yönetim ilkesinin **Durum** sütununun altında, **Uyumlu**, **Uyumlu (Bekleniyor)**veya **Hata** seçenekleri görünür. Seçili ilkede bir veya daha fazla çakışan ayar varsa, bu alanda **Hata** ifadesi görünür.

6.  Bir çakışmayı belirledikten sonra çakışan ilke ayarlarını aynı ayarı kullanacak şekilde düzeltebilir veya uygulama ve kullanıcıya yalnızca tek bir ilke dağıtabilirsiniz.

### <a name="how-policy-conflicts-are-resolved"></a>İlke çakışmalarını çözümleme
Kullanıcı veya cihaza ilk dağıtımda bir mobil uygulama yönetim ilkesi çakışması olursa, çakışmaya neden olan ayar değeri uygulamaya dağıtılan ilkeden kaldırılır. Uygulama yerleşik bir çakışma değeri kullanır.

Daha sonraki kullanıcı veya cihaz dağıtımlarında bir mobil uygulama yönetim ilkesi çakışması olursa, çakışmaya neden olan ayar değeri uygulamaya dağıtılan mobil uygulama yönetimi ilkesinde güncelleştirilmez. Uygulama bu ayar için mevcut olan değeri kullanır.

Cihaz veya kullanıcının çakışan iki ilke aldığı durumlarda, aşağıdaki davranış geçerlidir:

-   Bir ilke cihaza zaten dağıtıldıysa, mevcut ilke ayarları geçersiz kılınmaz.

-   Cihaza hiçbir ilke dağıtılmadıysa ve çakışan iki ayar dağıtılırsa, cihazda yerleşik olarak bulunan varsayılan ayar kullanılır.
