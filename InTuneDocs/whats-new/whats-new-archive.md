---
title: "Yenilikler arşivi | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ecf43b38e9593375981770583220d4ce2dfd709f
ms.openlocfilehash: 8b0f393da727b433a926e780d6de42cf7b4c6034


---
## Aralık 2015
### Microsoft Şirket Portalı değişiklikleri ve güncelleştirmeleri
Bu sürümde, Şirket Portalı’nda aşağıdaki değişiklikler yapılmıştır.

**Android Şirket Portalı uygulaması**

Yeni Google gereksinimlerine uyum sağlamak için aşağıdaki değişiklikler yapılmıştır. Android 6.0 ve üstü cihazlarda kullanıcılara iki yeni ileti görüntülenir:
* Şirket Portalı’nın telefon çağrıları yapmasına ve çağrıları yönetmesine izin verilsin mi?
* Şirket Portalı’nın cihazınızdaki fotoğraflara, medyaya ve dosyalara erişmesine izin verilsin mi?

Bu iki iletiyle ilgili ayrıntılı bilgi için aşağıdaki tablolara bakın.



İleti metni  |Şirket Portalı’nın telefon çağrıları yapmasına ve çağrıları yönetmesine izin verilsin mi?  
---------|---------
İleti açıklaması     |  Kullanıcının cihaz telefon numarası ile IMEI numarasının Intune hizmetine gönderilmesini ve Donanım sayfasındaki Yönetim konsolunda görüntülenmesini sağlar.   </br></br>**NOT: Şirket Portalı uygulaması hiçbir zaman telefon çağrıları yapmaz veya çağrıları yönetmez!** İleti metni Google tarafından denetlenir ve değiştirilemez. </br></br>**Donanım** sayfasını görmek için, **Gruplar** > **Tüm mobil cihazlar** > **Cihazlar**’a gidin. Kullanıcının cihazını seçin ve **Özellikleri Görüntüle** > **Donanım**’a gidin.    
İletinin nerede ve ne zaman görüneceği  | İleti, kullanıcılar cihazlarını kaydetmeye başlamak için Şirket Portalı uygulamasında ilk kez oturum açtığında görüntülenir.|         
Kullanıcılar erişime izin verirse ne olur  |  Cihazın telefon numarası ile IMEI numarası, Yönetim konsolundaki Donanım sayfasında görüntülenir. |         
Kullanıcılar erişimi reddederse ne olur     | Şirket Portalı uygulamasını kullanmaya ve cihazlarını kaydetmeye devam edebilirler, ancak Yönetim konsolundaki Donanım sayfasında kullanıcı cihazının telefon numarası ile IMEI numarası boş olarak görüntülenir.       </br></br> Kullanıcılar, erişimi reddettikten sonra Şirket Portalı uygulamasında ikinci kez oturum açtığında, kullanıcıların iletinin bir daha görüntülenmemesini seçebilmesi için **Bir daha sorma** onay kutusu görüntülenir.</br></br>Kullanıcılar erişime izin verip daha sonra erişimi reddederse ileti, kullanıcılar kayıt işleminin ardından Şirket Portalı uygulamasında bir sonraki sefer oturum açtığında görüntülenir.</br></br>Kullanıcılar daha sonra erişime izin vermeye karar verirse, **Ayarlar** > **Uygulamalar** > **Şirket Portalı** > **İzinler** > **Telefon**’a gidebilir ve ardından izni etkinleştirebilirler.
Daha fazla bilgi     |  Kullanıcılarınız için: [Şirket Portalı’nda oturum açma](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_signin_cp)  </br></br>BT Uzmanları için: Bu tablodaki bilgilere [Kullanıcılarınızın Şirket Portalı uygulaması iletilerini anlamalarına yardımcı olma](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs) bölümünden de erişilebilir   

İleti metni  |Şirket Portalı’nın cihazınızdaki fotoğraflara, medyaya ve dosyalara erişmesine izin verilsin mi?  
---------|---------
İleti açıklaması     |  Cihazın, veri günlüklerini cihazdaki SD kartına yazmasını sağlar ve böylece günlüklerin bir USB kablosu aracılığıyla taşınmasına olanak tanır.   </br></br>**NOT: Şirket Portalı uygulaması hiçbir zaman kullanıcının fotoğraflarına, medyasına ve dosyalarına erişmez!** İleti metni Google tarafından denetlenir ve değiştirilemez.     
İletinin nerede ve ne zaman görüneceği  | İleti, kullanıcılar veri günlüklerini BT yöneticilerine göndermek üzere **Veri Gönder** seçeneğine dokunduğunda görüntülenir.|         
Kullanıcılar erişime izin verirse ne olur  |  Günlükler SD karta kopyalanır. |         
Kullanıcılar erişimi reddederse ne olur     | Kullanıcılar veri günlüklerini göndermeye devam edebilir, ancak günlükler cihazın SD kartına kopyalanmaz.       </br></br> Kullanıcılar, erişimi reddettikten sonra Şirket Portalı uygulamasında ikinci kez oturum açtığında, kullanıcıların iletinin bir daha görüntülenmemesini seçebilmesi için **Bir daha sorma** onay kutusu görüntülenir.</br></br>Kullanıcılar erişime izin verip daha sonra erişimi reddederse ileti, kullanıcılar günlükleri tekrar göndermeye çalıştığında görüntülenir.</br></br>Kullanıcılar daha sonra erişime izin vermeye karar verirse, **Ayarlar** > **Uygulamalar** > **Şirket Portalı** > **İzinler** > **Mağaza**’ya gidebilir ve ardından izni etkinleştirebilirler.
Daha fazla bilgi     |  Kullanıcılarınız için: [Tanılama veri günlüklerini e-posta aracılığıyla BT yöneticinize gönderme](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_send_diag_logs)  </br></br>BT Uzmanları için: Bu tablodaki bilgilere [Kullanıcılarınızın Şirket Portalı uygulaması iletilerini anlamalarına yardımcı olma](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs) bölümünden de erişilebilir   


**iOS Şirket Portalı uygulaması**
* Kullanıcılar, tanılama günlüklerini BT yöneticisine göndermek için artık Microsoft Outlook’u veya diğer e-posta uygulamalarını kullanabilir. Daha önce bunun için yalnızca yerel uygulama kullanılabiliyordu.
* Apple’ın Aygıt Kayıt Programı (DEP) ve kurumsal olarak kaydedilen cihazlar için sunulan destek geliştirilmiştir. Ayrıntılar için bkz. [Kaydetmeye çalışırken cihazınızı tanımlamanız isteniyor](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_id_your_device).
* Kullanıcıya ait kayıtlı cihazlar listesinde, kullanıcının şu anda kullanmakta olduğu cihazın yanında yeşil bir onay işareti görüntülenir. Bu onay işareti eklenmeden önce kullanıcılar, kullanmakta oldukları kayıtlı cihazı görme olanağına sahip değildi.

**Windows Şirket Portalı uygulaması**

Microsoft, ürün ve hizmetlerini geliştirmek için şirket portalının performansı ve kullanımı hakkında anonim bilgileri otomatik olarak toplar. Son kullanıcılar cihazlarının Kullanım Verileri ayarını kullanarak veri toplamayı devre dışı bırakabilir, ancak yöneticilerin veri toplama üzerinde hiçbir denetimi yoktur ve son kullanıcının bu ayar ile ilgili seçimini değiştiremezler.



## Kasım 2015
### Uygulama yönetimi
Intune, şirket verilerinin tüketici uygulamalarına veya hizmetlerine sızmasını önlemeye yardımcı olan mobil uygulama yönetimi (MAM) ilkelerini destekler. Tarihsel olarak, bu ilkeler yalnızca mobil cihaz yönetimi (MDM) için Intune’a da kaydedilmiş cihazlarda çalışan mobil uygulamalar üzerinde uygulanabiliyordu.

Bu ayın güncelleştirmesiyle Intune, MAM yeteneklerini yeni cihaz sınıflarına genişletmektedir. MAM ilkelerini Intune'a kayıtlı cihazlara ek olarak bundan böyle aşağıdakilere uygulayabilirsiniz:
* başka bir mobil cihaz yönetimi (MDM) çözümü tarafından yönetilen cihazlar
* herhangi bir cihaz yönetimi sistemine kayıtlı olmayan cihazlar, genellikle kendi cihazını getir (BYO)

Bu yeni MAM özellikleri hakkında daha fazla bilgiyi aşağıdaki blog gönderilerinde bulabilirsiniz:
* [Yönetilen mobil üretkenliği geliştirme](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)
* [Yeni Microsoft Enterprise Mobility özellikleriyle tanışın](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)

Ayrıca, Intune'un MAM özellikleri hakkında öne çıkan bazı noktalar ve ek bilgiler şunlardır:
* Şirket verileri Office Mobile uygulamaları, Intune SDK’sını benimseyen üçüncü taraf uygulamalar veya Intune tarafından sarmalanan iş kolu uygulamaları dahil olmak üzere Intune için tanıtılan uygulamaların içindeki tüketici verilerinden ayrı tutulur.
* Şirket verileri şirket uygulamalarında paylaşılabilirken (**kes/kopyala/yapıştır**), kişisel uygulamalarla paylaşılması engellenir. Daha fazla bilgi için bkz. [MAM ilkeleri uygulama verilerini nasıl korur](https://technet.microsoft.com/library/mt627825.aspx). [İş amaçlı ve kişisel görevler için Microsoft Word uygulamasını kullanma](https://technet.microsoft.com/library/mt627827.aspx) adlı bu örnek senaryo, şirket verilerinin kişisel uygulamalarla paylaşılmasının nasıl önlendiğini göstermektedir.
* Uygulama Başına PIN, farklı kaydetme denetimleri ve uygulamalar arasında yönetilen veri paylaşımı gibi temel veri kaybı önleme ilkeleri. Tüm ilkelerin listesi için bkz. [Microsoft Intune ile mobil uygulama yönetimi ilkeleri oluşturma ve dağıtma](https://technet.microsoft.com/library/mt627829.aspx).
* Word, Excel, PowerPoint, Outlook, OneNote ve OneDrive İş uygulamalarının hepsi bu yeni özelliklere sahiptir ve cihaz kaydı ile birlikte ya da cihaz kaydı olmadan yönetilebilir. Veri kaybı önleme özellikleri Apple Store veya Google Play mağazasındaki standart Office uygulamalarına yerel olarak yerleştirilmiştir ve uygulama sarmalama ya da dışarıdan yükleme gerektirmez.
* Nasıl başlayacağınızı öğrenmek için bkz. [Azure portalında mobil uygulama yönetimi ilkelerini kullanmaya başlama](https://technet.microsoft.com/library/mt627830.aspx). Mobil uygulama yönetimi ilkelerini yapılandırma ve dağıtma hakkında bilgi almak için bkz. [Microsoft Intune ile mobil uygulama yönetimi ilkeleri oluşturma ve dağıtma](https://technet.microsoft.com/library/mt627829.aspx).
* Son kullanıcılar uygulamada şirket bilgileriyle kimlik doğrulaması yaptıklarında veri kaybı koruma özellikleri otomatik olarak ayarlanır. [Microsoft Intune mobil uygulama yönetimi ilkeleri ile ilişkili uygulamalar için son kullanıcı deneyimi](https://technet.microsoft.com/library/mt627827.aspx) konusunda iOS ve Android cihazlarında OneDrive erişimine ilişkin bazı örnek senaryolar verilmiştir.
* iOS ve Android cihazlar üzerinde çalışır.

[Microsoft Intune mobil uygulama yönetimi ilkeleri ile birlikte kullanabileceğiniz Microsoft uygulamaları](https://technet.microsoft.com/library/dn708489.aspx) listesi en son uygulamaları gösterecek şekilde güncelleştirilmiştir.

### Cihaz yönetimi
 **Mac OS X cihaz yönetimi** Intune ile bundan böyle Mac OS X cihazlarını kaydedip yönetebilirsiniz. Mac OS X cihazlarınız ile aşağıdakileri yapabilirsiniz:
* Intune tarafından yönetilecek cihazları kaydetme. Bkz. [Microsoft Intune ile iOS ve Mac yönetimini ayarlama](https://technet.microsoft.com/library/dn408185.aspx).
* Genel bir yapılandırma ilkesi ile cihaz ayarlarını denetleme. Bkz. [Microsoft Intune’da Mac OS X yapılandırma ilkesi ayarları](https://technet.microsoft.com/library/mt627823.aspx).
* Apple Configurator ile oluşturduğunuz Mac OS X ayarlarını dağıtma. Bkz. [Microsoft Intune’da Mac OS X özel ilke ayarları](https://technet.microsoft.com/library/mt627820.aspx).
* Mac OS X cihazlarından donanım ve yazılım envanteri toplama. Bkz. [Microsoft Intune’da envanterle cihazlarınızı anlama](https://technet.microsoft.com/library/jj733634.aspx).
* Yönettiğiniz Mac OS X cihazlarıyla ilgili ayrıntıları gösteren yeni raporlar çalıştırma. Bkz. [Raporları kullanarak Microsoft Intune işlemlerini anlayın](https://technet.microsoft.com/library/dn646977.aspx).

**Windows 10 cihazları için yeni Edge tarayıcı ayarları** Microsoft Edge tarayıcısının ayarlarını ve özelliklerini yönetmenize olanak sağlayan Windows 10 genel yapılandırma ilkesine yeni ayarlar eklenmiştir. Bkz. [Microsoft Intune’da Windows 10 yapılandırma ilkesi ayarları](https://technet.microsoft.com/library/mt404697.aspx).

**E-posta profilleri** Windows 10 masaüstü ve Windows 10 mobil cihazlar için yeni bir e-posta profilleri ilkesi eklenmiştir. Bkz. [Microsoft Intune ilkeleriyle cihazlarınızda ayarları ve özellikleri yönetme](https://technet.microsoft.com/library/dn646984.aspx).

**Yeni uyumluluk ilkesi ayarları** Uyumluluk ilkeleri listesine aşağıdaki yeni güvenlik ve sistem ilkesi ayarları eklenmiştir:
* Şirket kaynaklarınıza erişen Windows 8.1 veya üzeri cihazlarda en son güncelleştirmelerin yüklü olduğundan emin olmak için **Otomatik güncelleştirmeleri zorunlu kıl** ayarını kullanın. Ayrıca otomatik olarak yüklenecek güncelleştirmelerin türünü belirtebilirsiniz; tüm güncelleştirmeler yüklenmek üzere önemli olarak işaretlenebilir veya tüm güncelleştirmeler önemli ya da önerilen olarak işaretlenir. Uyumluluk ilkesi ayarlarının tam listesi için bkz. [Microsoft Intune için cihaz uyumluluk ilkelerini yönetme](https://technet.microsoft.com/library/dn705843.aspx).
* Yeni **Cihaz boşta durumundan çıktığında parola gerektir** ayarı ile birlikte var olan **Parola istenmeden önce geçen işlem yapılmayan dakika sayısı** ayarı, son kullanıcının belirli bir süredir etkin olmayan bir cihazı kullanmak üzere parola girmesini gerektiren bir uyumluluk ayarı oluşturmanıza imkan tanır.

**Yeni koşullu erişim ilkesi seçenekleri** Koşullu erişim ilkelerini yeni veya var olan koşullu erişim ilkelerindeki **tüm kullanıcılara** uygulayabilirsiniz. Intune ve Office 365 lisansına sahip tüm kullanıcıların cihazlarını kaydetmesi gerekir ve cihaz platformu Intune tarafından desteklenmiyorsa [Active Directory kimlik doğrulama tabanlı oturum açma (modern kimlik doğrulaması)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/) kullanan istemci uygulamalar için erişim engellenir.

Koşullu erişim ilkesinin **tüm platformlar** geçerli olduğunu da belirtebilirsiniz.  [Active Directory kimlik doğrulama tabanlı oturum açma (modern kimlik doğrulaması)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/) kullanan tüm istemci uygulamalar koşullu erişim ilkesine tabidir ve platform Intune tarafından desteklenmiyorsa engellenir.

### Microsoft Şirket Portalı değişiklikleri ve güncelleştirmeleri
Bu sürümde şirket portalı uygulamalarında aşağıdaki değişiklikler yapılmıştır:

* **Android**: Android Şirket Portalı uygulamasına, kullanıcıların Şirket Portalı uygulamasının amacını anlamasına yardımcı olmak üzere bir Hoş Geldiniz ekranı eklenmiştir. Bu ekran, şirketleri Intune abonesi olmayan kullanıcılar tarafından uygulamanın indirilmesini azaltmaya yöneliktir.

* **iOS**: Intune artık kullanarak Mac OS X cihazlarının destekler [Şirket portalı Web sitesini](https://portal.manage.microsoft.com). Yönergeler için bkz. [Mac OS X cihazınızı Intune’a kaydetme](https://technet.microsoft.com/library/mt598622.aspx).

* **Şirket Portalı web sitesi**: Cihazlarını Intune’a kaydeden kullanıcılar artık, Şirket Portalı web sitesindeki **Geçiş Kodunu Sıfırlama** seçeneğini kullanarak geçiş kodlarını sıfırlayabilir. Kullanıcıların geçiş kodları, daha önce yalnızca BT yöneticileri tarafından sıfırlanabiliyordu. Geçiş Kodunu Sıfırlama seçeneği Windows 8.1 ve Windows RT cihazlarında desteklenmez ve seçenek, yalnızca cihazların mobil cihaz yönetimine (MDM) veya Exchange ActiveSync içeren MDM’ye kayıtlı olması durumunda görüntülenir.Geçiş Kodunu Sıfırlama seçeneği Windows 8.1 ve Windows RT cihazlarında desteklenmez ve seçenek, yalnızca cihazların mobil cihaz yönetimine (MDM) veya Exchange ActiveSync içeren MDM’ye kayıtlı olması durumunda görüntülenir. Kullanıcı yönergeleri için bkz. [Geçiş kodunuzu sıfırlama](https://technet.microsoft.com/library/mt590895.aspx).

### Genel Yönetici lisansındaki değişiklikler
Ekim ayında Genel Yöneticilerin (Kiracı Yöneticiler olarak da bilinir) ayrı bir Intune veya Enterprise Mobility Suite (EMS) lisansı olmadan günlük yönetim görevlerine devam edebileceği paylaşılmıştı. Ancak, Genel Yöneticiler kendi cihazlarını veya bir şirket cihazını kaydetme gibi amaçlarla hizmeti kullanmak ya da Intune Şirket Portalı’nı kullanmak isterse diğer tüm kullanıcılar gibi bir Intune veya EMS lisansına ihtiyaç duyacaklardır. Birkaç ek ayrıntı aşağıda verilmiştir.
* Intune Şirket Portalı’nda son kullanıcılar şunları yapabilir:
    * cihazlarını kaydetme
    * cihazlarının durumunu görüntüleme
    * bir Genel Yöneticinin kuruluşa dağıttığı yazılımları indirme
    * Genel Yönetici tarafından BT departmanına nasıl başvurulacağıyla ilgili yayımlanan bağlantıları bulma

    [Şirket Portalı hakkında bilgi edinme](https://technet.microsoft.com/library/dn646966.aspx#BKMK_CompanyPortal) ve [Şirket Portalı’nı özelleştirme yolları](https://technet.microsoft.com/library/dn646983.aspx#BKMK_ConfigureCompanyPortal) hakkında.
* Bir kuruluş adına Intune veya EMS satın almak üzere kaydolan kişi otomatik olarak kiracısındaki ilk Genel Yönetici olur. Bu sonbaharda Intune, [Office 365 Portalı](http://portal.office.com/)’na geçiş ve [Intune Hesap Portalı](http://account.manage.microsoft.com/)’nın kullanımdan kaldırılmasının bir parçası olarak bu ilk Genel Yönetici’ye bir Intune veya EMS lisansını otomatik olarak atamaya başlamıştır. Eklenen diğer tüm Genel Yöneticiler ayrı bir Intune veya EMS lisansı olmadan günlük yönetim görevlerini gerçekleştirmeye devam edebilir. Son kullanıcı olarak hareket edilmesi ve kendi (ya da şirket) cihazının kaydedilmesi veya şirket portalından yazılım indirilmesi ise diğer tüm kullanıcılarda olduğu gibi bir lisans ihtiyacı doğurur.
* Değişiklik aşamalı olacak ve Ocak 2016'da başlayacaktır.
* Microsoft İş Ortakları için bu değişiklik müşteriler adına hizmeti yönetme özelliğini etkilemeyecektir. Son kullanıcı görevlerinde bir kullanıcının bir cihazı kaydetmesi ve Şirket Portalı’na erişip buradan yazılım indirmesi için Intune veya EMS lisansına sahip olması gerekir.

Bu değişiklik hakkında sorularınız varsa Intune destek ekibinize başvurmaktan çekinmeyin:
* [Microsoft Intune destek kanalları](https://technet.microsoft.com/library/jj839713.aspx)
* [Topluluk desteği](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

Tasarım Değişikliği İstekleri (DCR) veya hatalar dahil olmak üzere Microsoft Intune ile ilgili genel görüşler için [Intune kullanıcı sesi](https://microsoftintune.uservoice.com/) sayfasını ziyaret edin.


### Intune belgelerindeki yenilikler -- Kasım 2015
**Yeni içerik**
* [Microsoft Intune’da Mac OS X yapılandırma ilkesi ayarları](https://technet.microsoft.com/library/mt627823.aspx): Mac OS X cihazlarının ayarlarını ve özelliklerini denetleme.
* [Microsoft Intune’da Mac OS X özel ilke ayarları](https://technet.microsoft.com/library/mt627820.aspx): Apple Configurator aracını kullanarak oluşturduğunuz Mac OS X cihaz ayarlarını dağıtma.
* [Microsoft Intune ile veri kaybı önleme uygulama ilkelerini yapılandırma](https://technet.microsoft.com/library/mt627825.aspx): Mobil uygulama yönetimi ilkelerinin desteklediği senaryolar ve ilkenin verileri korumak için nasıl çalıştığı hakkında bilgi içerir.
* [Azure portalında mobil uygulama yönetimi ilkelerini kullanmaya başlama](https://technet.microsoft.com/library/mt627830.aspx): Mobil uygulama yönetimi ilkeleri için Azure önizleme portalını kullanmaya başlamaya yönelik gereksinimler.
* [Microsoft Intune ile mobil uygulama yönetimi ilkeleri oluşturma ve dağıtma](https://technet.microsoft.com/library/mt627829.aspx): Azure önizleme portalında mobil uygulama yönetimi ilkelerinin nasıl oluşturulacağıyla ilgili bir adım adım kılavuz içerir.
* [Microsoft Intune ile mobil uygulama yönetimi ilkelerini izleme](https://technet.microsoft.com/library/mt627824.aspx): Azure önizleme portalını kullanarak mobil uygulama yönetimi ilkelerinizi nasıl izleyebileceğinize ilişkin bilgiler.
* [Microsoft Intune mobil uygulama yönetimi ilkeleri ve iOS Birlikte Açma](https://technet.microsoft.com/library/mt627821.aspx): Mobil uygulama yönetimi ilkelerinin iOS Birlikte Açma özelliğiyle nasıl çalıştığına yönelik bilgiler.
* [Microsoft Intune mobil uygulama yönetimi ilkeleri ile ilişkili uygulamalar için son kullanıcı deneyimi](https://technet.microsoft.com/library/mt627827.aspx): Mobil uygulama yönetimi ilkesiyle ilişkili uygulamalar kullanılırken son kullanıcı deneyiminin nasıl olduğu.
* [Microsoft Intune ile yönetilen şirket uygulama verilerini silme](https://technet.microsoft.com/library/mt627826.aspx): Şirket uygulama verilerini nasıl kaldırabileceğiniz.

**Güncelleştirilmiş içerik**
* [Microsoft Intune’da Windows 10 yapılandırma ilkesi ayarları](https://technet.microsoft.com/library/mt404697.aspx): Yeni Microsoft Edge tarayıcısı ayarları eklendi.
* [Microsoft Intune ile iOS ve Mac yönetimini ayarlama](http://technet.microsoft.com/library/dn408185.aspx): Mac OS X cihazlarının nasıl kaydedileceği hakkında bilgiler eklendi.
* [Microsoft Intune’da envanterle cihazlarınızı anlama](https://technet.microsoft.com/library/jj733634.aspx): Mac OS X cihazlarından toplanan envanter hakkında bilgiler eklendi. Ayrıca, tüm cihaz platformları için en son bilgilerle konu güncelleştirildi.
* [Raporları kullanarak Microsoft Intune işlemlerini anlayın](https://technet.microsoft.com/library/dn646977.aspx): Yönetilen Mac OS X cihazlarınızla ilgili bilgileri görüntülemek için kullanılan iki yeni rapor hakkında bilgiler eklendi.
* [Microsoft Intune için cihaz uyumluluk ilkelerini yönetme](https://technet.microsoft.com/library/dn705843.aspx): Otomatik güncelleştirmeleri zorunlu kılma ve bir cihaz boşta durumundan döndüğünde parola gerektirme için yeni uyumluluk ilkeleri hakkında bilgiler eklendi.
* [Microsoft Intune ile e-posta erişimini yönetme](https://technet.microsoft.com/library/dn705841.aspx): Koşullu erişimi tüm platformlara ve tüm kullanıcılara uygulama özelliği hakkında bilgiler eklendi.
* [Microsoft Intune ile SharePoint Online erişimini yönetme](https://technet.microsoft.com/library/dn705844.aspx): Koşullu erişimi tüm platformlara ve tüm kullanıcılara uygulama özelliği hakkında bilgiler eklendi.

## Ekim 2015

### Exchange şirket içi koşullu erişimi güncelleştirmeleri
**Genel Exchange kuralı engelleme veya karantinaya alma şeklinde ayarlandığında Intune’a kayıtlı uyumlu cihazlar için Exchange Active Sync e-postasına artık erişebilirsiniz** Bundan önce, kayıtlı ve uyumlu cihazlarda e-posta erişimine izin vermek için varsayılan genel Exchange kuralını **İzin Ver** olarak ayarlamanız gerekiyordu.

Bu hizmet güncelleştirmesiyle, koşullu erişim için artık bu ayar gerekli değildir. Exchange ortamınız varsayılan genel kuralınızın **Engelle/Karantinaya Al** olarak ayarlanmasını gerektiriyorsa, Exchange şirket içi koşullu erişim ilkesi sayfasında **Varsayılan Kuralı Geçersiz Kıl** onay kutusunu işaretlemeniz yeterli olur. [Microsoft Intune ile e-posta erişimini yönetme](https://technet.microsoft.com/library/dn705841.aspx) konu başlığı altında, kurallar ve bunlardan kaynaklanan son kullanıcı bildirimleriyle ilgili daha ayrıntılı bilgi bulabilirsiniz.

**Yeni tek tıklamalı karantina deneyimi** Tek tıklamayla kayıt olanağı sağlamak için, karantina e-postası deneyimini basitleştirdik. Bu hizmet güncelleştirmesiyle, son kullanıcılar karantina e-postasında tek bir bağlantıya tıklayarak Şirket Portalı uygulamasında kayıt işlemini tamamlayabilecek.
### Mobil cihaz ve uygulama yönetimi güncelleştirmeleri
**Android** Artık tüm Intune yönetim özellikleri bu blog gönderisinde açıklandığı gibi Android 6.0’ı (Marshmallow) desteklemektedir: [Microsoft Intune Android Marshmallow için 0. Gün Desteği Sağlıyor](http://blogs.technet.com/b/microsoftintune/archive/2015/10/09/microsoft-intune-to-provide-day-0-support-for-android-marshmallow.aspx).

**iOS** Bundan böyle iOS 7.1’den önceki sürümleri çalıştıran iOS cihazlarında yeni uygulama dağıtımları oluşturamazsınız. iOS 7.1’den önceki sürümleri çalıştıran cihazlara yönelik var olan tüm uygulama dağıtımları çalışmaya ve Intune tarafından yönetilmeye devam edecektir.

**Windows 10**, **Windows uygulama paketi** bundan böyle yazılım yükleyici türünü kullanarak Windows 10 Universal uygulamalarının dağıtımını desteklemektedir. Ayrıntılar ve gereksinimler için bkz. [Microsoft Intune'da uygulama dağıtımına başlayın](http://technet.microsoft.com/en-US/library/dn646955.aspx).


### Microsoft Şirket Portalı uygulamalarındaki değişiklikler ve güncelleştirmeler
Bu sürümde şirket portalı uygulamalarında şu değişiklikler yapılmıştır: **iOS** Kullanıcıların BT yöneticilerine tanılama günlükleri göndermesini kolaylaştırmak için Şirket Portalı uygulamasına yeni düğmeler eklenmiştir:

|Düğme adı|Göründüğü yer|
|------------|---------------|
|Rapor|Hata uyarı iletileri|
|Tanılama Raporu Gönder|Şirket Portalı uygulamasının Hakkında ekranı|



## Eylül 2015
### Mobil cihaz ve uygulama yönetimi güncelleştirmeleri
**Artık tüm Intune iOS yönetim özellikleri iOS 9’u destekler** iOS 9 yönetim özelliklerinin ayrıntıları için [bu blog gönderisine](http://blogs.technet.com/b/microsoftintune/archive/2015/09/09/day-zero-support-for-ios-9-with-intune.aspx) bakın.

**iOS için yeni mobil uygulama yapılandırma ilkesi** Yeni uygulama yapılandırma ilkesini kullanarak, iOS uygulamasına çalışırken gerekli olabilecek ayarları otomatik olarak sağlayın. Örneğin, bir ağ bağlantı noktası veya kullanıcı adı sağlayabilirsiniz. Ayrıntılar için bkz. [Uygulamaları Microsoft Intune’da mobil uygulama yapılandırma ilkeleriyle yapılandırma](https://technet.microsoft.com/library/mt481447.aspx).

**iOS 9 kullanıcıları için daha kolay uygulama yönetimi**
 Bu sürümde, dağıtılmış uygulamaları iOS 9 kullanıcıları için Intune yönetimi altında kullanıma sunabilirsiniz. Daha önceki iOS sürümlerinde, bir uygulama dağıttığınızda uygulamanın yönetilmeyen bir sürümü cihazda zaten yüklü olsa bile, Intune yönetilen uygulamayı yüklemeden önce kullanıcıdan uygulamayı el ile kaldırmasını istemeniz gerekir.

 Bu Intune sürümünden itibaren, artık iOS 9 cihazlarının kullanıcılarından Intune’un uygulama yönetimini devralmasına ve ilgili mobil uygulama yönetim ilkelerini uygulamasına izin vermelerini isteyebilirsiniz.

 **Windows 10 yönetimi** Windows 10 ve Windows 10 Mobile çalıştıran kayıtlı cihazlarda parolayı, cihazı, tarayıcıyı ve diğer ayarları yapılandırmak için yeni [Windows 10 genel yapılandırma ilkesini](https://technet.microsoft.com/library/mt404697.aspx) kullanın.

 **Kayıtlı Windows 10 cihazlarında uygulamalar oluşturma ve dağıtma** Yeni yazılım yükleyici türü MDM aracılığıyla Windows Installer (&#42;.msi), Windows 10 çalıştıran kayıtlı cihazlara Windows Installer uygulamaları oluşturmanıza ve dağıtmanıza olanak tanır. Ayrıntılar için bkz. [Microsoft Intune'da uygulama dağıtımına başlayın](https://technet.microsoft.com/library/dn646955.aspx).

### Microsoft Şirket Portalı uygulamalarındaki değişiklikler ve güncelleştirmeler
Bu sürümde şirket portalı uygulamalarında aşağıdaki değişiklikler yapılmıştır:

**iOS**
* Microsoft, ürün ve hizmetlerini geliştirmek için şirket portalının performansı ve kullanımı hakkında anonim bilgileri otomatik olarak toplar. Son kullanıcılar cihazlarının Kullanım Verileri ayarını kullanarak veri toplamayı devre dışı bırakabilir, ancak yöneticilerin veri toplama üzerinde hiçbir denetimi yoktur ve son kullanıcının bu ayar ile ilgili seçimini değiştiremezler.
* iPhone 6 ve 6 Plus için tam ekran çözünürlüğü desteği
* Güvenliği arttırmaya yönelik hata düzeltmeleri

### Intune belgelerindeki yenilikler -- Eylül 2015
**Yeni konular**

|Ad|Ayrıntılar|
|----|--------|
|[Microsoft Intune’da Windows 10 yapılandırma ilkesi ayarları](https://technet.microsoft.com/library/mt404697.aspx)|Bu, Windows 10 ve Windows 10 Mobile çalıştıran cihazlarda ayarları ve özellikleri yönetmenize olanak tanıyan yeni bir yapılandırma ilkesidir.
| [Uygulamaları Microsoft Intune’da mobil uygulama yapılandırma ilkeleriyle yapılandırma](https://technet.microsoft.com/library/mt481447.aspx)|Bu, kullanıcı bir iOS uygulaması çalıştırdığında gerekebilecek ayarları otomatik olarak sağlamanıza olanak tanıyan yeni bir ilke türüdür. |

**Güncelleştirilmiş konular**

|Ad|Ayrıntılar|
|----|-------|
|[Microsoft Intune'la bilgisayarlar ve mobil cihazları yönetmek için ilkeleri kullanma](https://technet.microsoft.com/library/dn743712.aspx)|İlkeleri anlamanıza ve oluşturmanıza yardımcı olmak için en son bilgileri içerecek şekilde güncelleştirilmiştir.|

## Ağustos 2015
### Mobil cihaz ve uygulama yönetimi güncelleştirmeleri
* Intune’a kaydolma ve şirket erişimi için**hüküm ve koşullar** artık [ilkeler kullanılarak yönetilir](https://technet.microsoft.com/library/mt405893.aspx). Belirli kullanıcı grupları için, kendilerine yönelik gereksinimleri karşılayacak farklı hüküm ve koşullar hedefleyebilirsiniz. Örneğin, coğrafi olarak tanımlanan kullanıcı gruplarına hüküm ve koşulları farklı dillerde dağıtabilirsiniz. Ayrıca [hüküm ve koşullarınızı düzenleyebilir](https://technet.microsoft.com/library/mt405893.aspx#BKMK_TCVers) ve sürüm numaralarının artırılıp artırılmayacağını belirterek kullanıcıların şirket portalını kullanabilmek için yeni hüküm ve koşulları kabul etmelerini gerektirebilirsiniz.
* **Çeşitli Intune ilkeleri yeniden adlandırılarak** ürün içinde daha tutarlı ve bulunması daha kolay hale getirilmiştir. Kullanılabilir tüm Intune ilkelerinin listesi için bkz. [Microsoft Intune ile bilgisayarları ve mobil cihazları yönetmek için ilkeleri kullanma](https://technet.microsoft.com/library/dn743712.aspx).
* **PKCS #12 (.PFX) Sertifika Profilleri**, Android 4.0 veya sonraki sürümleri ve Windows 10 (masaüstü ve mobil) ve sonraki sürümleri için kullanılabilir. .PFX kullanmak için NDES sunucusu gerekli değildir. .PFX sertifika profilleri oluşturma hakkında bilgi için bkz. [Microsoft Intune ile sertifika profillerini kullanarak şirket kaynaklarına erişimi etkinleştirme](http://technet.microsoft.com/library/dn818904.aspx)
* [Kullanıcıların Microsoft Intune'la VPN profilleri kullanarak işlerine bağlanmasına yardımcı olun](https://technet.microsoft.com/library/dn818905.aspx) bölümünde açıklandığı gibi **Windows 10 Masaüstü ve Mobile için Kuruluş Sınırları ayarları** ayrıntılı VPN ayarlarını destekler
* **Android için OneDrive uygulaması artık birden çok kimliği desteklemektedir**. Mobil uygulama yönetimi ilkeleri ile ilgili bu ve diğer güncelleştirmeler [yönetilebilen Microsoft uygulamalarının listesi](https://technet.microsoft.com/library/dn708489.aspx)içinde açıklanmıştır.
* **iOS Etkinleştirme Kilidini atlama**. Şirkete ait iOS cihazları Etkinleştirme Kilidi ile korunuyorsa, cihazı silmek veya yeniden etkinleştirmek için önce kullanıcının Apple Kimliğini ve parolasını girmelisiniz. Bu, kullanıcılar şirketten ayrıldığında ve şirkete ait bir cihazı Etkinleştirme Kilidi’ni kapatmadan iade ettiğinde bir sorun oluşturabilir. Bu sorunun çözümüne yardımcı olmak için [Intune Etkinleştirme Kilidi’ni Atlama](https://technet.microsoft.com/library/mt414176.aspx) özelliğini kullanabilirsiniz

### Bilgisayarlar için koşullu erişim
Artık bilgisayarlar için koşullu erişim ilkeleri yapılandırabilirsiniz. Bu, Office masaüstü uygulamalarının Exchange Online ve SharePoint Online hizmetlerine erişmesini sağlar.
Bilgisayarlar için koşullu erişim ilkesini etkinleştirmek için bilgisayarın etki alanına katılmış ya da uyumlu olması gerekir.
* Bilgisayarlarda koşullu erişimi etkinleştirme gereksinimlerinin tam listesi için [Microsoft Intune ile e-posta ve SharePoint erişimini yönetme](http://technet.microsoft.com/library/dn818907).aspx) içindeki **Başlangıç** bölümüne bakın.
* E-posta erişimine yönelik koşullu erişimi etkinleştirmek üzere ayarlayabileceğiniz seçenekler için bkz. [Microsoft Intune ile e-posta erişimini yönetme](https://technet.microsoft.com/library/dn705841.aspx).
* SharePoint Online’da koşullu erişimi etkinleştirmek üzere belirleyebileceğiniz ayarlar için bkz. [Microsoft Intune ile SharePoint Online erişimini yönetme](https://technet.microsoft.com/library/dn705844.aspx).

### Microsoft Şirket Portalı uygulamalarındaki değişiklikler ve güncelleştirmeler
Bu sürümde şirket portalı uygulamalarında aşağıdaki değişiklikler yapılmıştır:

**Android**

Cihazlarını henüz yönetilmek üzere kaydetmemiş kullanıcılar, artık oturum açtıklarında cihaz kaydı yönergelerini görürler.

### Intune belgelerindeki yenilikler -- Ağustos 2015
**Yeni konular**

|Başlık|Ayrıntılar|
|-----|-------|
|[Microsoft Intune için Etkinleştirme Kilidi’ni atlama ile iOS cihazlarının korunmasına yardımcı olma](https://technet.microsoft.com/library/mt414176.aspx)|Şirketten ayrılan bir kullanıcı kilitli bir cihazı iade ettiğinde, Intune kullanarak iOS etkinleştirme kilidini nasıl atlayabileceğiniz hakkında bilgi edinin.|

**Güncelleştirilmiş konular**

|Başlık|Ayrıntılar|
|-----|-------|
|[Microsoft Intune mobil uygulama yönetimi ilkeleri ile kullanabileceğiniz Microsoft uygulamaları](https://technet.microsoft.com/library/dn708489.aspx)|Mobil uygulama yönetimi ilkeleriyle yönetebileceğiniz uygulamalar ile ilgili en son bilgilerle güncelleştirildi.
|[Microsoft Intune'la bilgisayarlar ve mobil cihazları yönetmek için ilkeleri kullanma](http://technet.microsoft.com/library/dn743712.aspx)|Intune’a eklenen en yeni ilkelerle güncelleştirildi.|
<!---
## July 2015
July updates for Intune are limited to behind-the-scenes enhancements that allow us to continue providing you with a high-quality service experience. New features are not included in this service update.

### Intune Onboarding benefit
Microsoft offers the Intune Onboarding benefit for eligible plans. The Onboarding benefit lets you work remotely with Microsoft specialists to get your Intune environment ready for use. For more information, see [Microsoft Intune Onboarding benefit description](https://technet.microsoft.com/library/mt228266.aspx)
### Changes and updates to Microsoft Company Portal apps
The following changes have been made to the company portal apps in this release.

**Android**

Microsoft automatically collects anonymous data about the performance and use of the company portal to improve Microsoft products and services. End users can turn off data collection by using the Usage Data setting on their device, but administrators have no control over the data collection and cannot change the end user’s selection for this setting.--->



<!--HONumber=Sep16_HO5-->


