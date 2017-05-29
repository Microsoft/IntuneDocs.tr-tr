---
title: "Erken sürüm | Microsoft Docs"
description: 
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 249a902e6e10f799dcff4e1c46da90cd62f2c125
ms.contentlocale: tr-tr
ms.lasthandoff: 05/23/2017


---

# <a name="the-early-edition-for-microsoft-intune---may-2017"></a>Microsoft Intune için erken sürüm - Mayıs 2017

**Erken Sürüm** Microsoft Intune'un gelecek sürümlerinde kullanıma sunulacak yeni özelliklerin bir listesini sağlar. Bu bilgiler NDA kapsamında çok sınırlı bir temelde sağlanır ve değiştirilebilir. Burada listelenen özelliklerden bazılarının son tarihe yetişememe riski vardır ve gelecek sürüme ertelenebilir. Diğer özellikler, müşterinin kullanımına hazır olduğundan emin olmak için pilot (sürüyor) aşamasında test edilmektedir. Sorularınız veya kaygılarınız varsa lütfen Intune/PM arkadaşınıza ulaşın.

Bu sayfa düzenli aralıklarla güncelleştirilir. Ek güncelleştirmeleri daha sonra denetleyin.

> [!Note]
> Intune için aşağıdaki değişiklikler geliştirilme aşamasındadır. Bu özelliklerin tümü, sonunda karma müşteri dağıtımlarında (Intune ile Configuration Manager) desteklenecektir. Yeni karma özellikler hakkında daha fazla bilgi için, [Karma Yenilikler sayfamızı](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) gözden geçirin.

## <a name="new-capabilities"></a>Yeni özellikler

### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>iOS Şirket Portalından iOS için Outlook uygulamasına çoklu oturum açma desteği <!--834012-->

Aynı cihazda aynı hesapla iOS için Şirket Portalı uygulamasında oturum açmış kullanıcıların artık Outlook uygulamasında oturum açmasına gerek kalmayacak. Kullanıcılar Outlook uygulamasını başlattıktan sonra hesaplarını seçip otomatik olarak oturum açabilecekler. Bu işlevi diğer Microsoft uygulamalarına da eklemek için çalışıyoruz.

### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Samsung KNOX başlangıç PIN’leri için geliştirilmiş bildirim <!--1087143-->

Şifrelemeyle uyumlu olması için son kullanıcıların Samsung KNOX cihazlarında başlangıç PIN’i ayarlamaları gerektiğinde, son kullanıcılara gösterilen bildirim (bildirime dokunulduğunda) onları Ayarlar uygulamasında tam doğru yerine getirir.  Daha önce, bildirim son kullanıcıyı parola değiştirme ekranına getiriyordu.

### <a name="promoting-the-most-current-version-of-the-company-portal-for-android---1098661--"></a>Android için Şirket Portalı’nın en güncel sürümüne yükseltme <!--1098661-->

Android için Şirket Portalı uygulamasının önerilen yeni bir sürümü kullanıma sunulduğunda, son kullanıcılar uygulamanın Bildirimler ekranında bir uygulama içi bildirim görür. Bu bildirim kullanıcılara "Şirket Portalı güncelleştirmesi sağlandığını" haber verir. Bildirime dokunulduğunda, güncelleştirilmiş sürümü indirebilecekleri uygulama mağazalarının listesini gösteren bir web sayfası açılır. 

### <a name="improvements-to-app-syncing-with-windows-10-creators-update----676505---"></a>Windows 10 Creators Güncelleştirmesi ile uygulama eşitleme geliştirmeleri <!-- 676505 -->

Windows 10 için Şirket Portalı, Windows 10 Creators Güncelleştirmesini (1704) içeren cihazlarda uygulama yükleme istekleri için eşitlemeyi otomatik olarak başlatacak. Bu, “Eşitleme Bekleniyor” durumu sırasında bekletilen uygulama yüklemeleri sorununu azaltacak. Buna ek olarak, kullanıcılar uygulamanın içinden el ile eşitleme başlatabilecek. 

Windows 10 için Şirket Portalı, kullanıcının her gerektiğinde uygulamadaki içeriği yenilemesine olanak tanıyan bir yenile düğmesi de gösterecek. 

## <a name="notices"></a>Bildirimler

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple, Uygulama Taşıma Güvenliği için güncelleştirmeler gerektirecek <!--748318-->

Apple, 2017 baharından itibaren, Uygulama Taşıma Güvenliği (ATS) için belirli gereksinimler uygulayacağını açıkladı. ATS, HTTPS üzerinden yapılan tüm uygulama iletişimlerinde daha sıkı güvenlik uygulamak için kullanılır. Bu değişiklik, iOS Şirket Portalı uygulamaları kullanan Intune müşterilerini etkiler. Daha fazla ayrıntı için bkz. [Intune destek blogu](https://aka.ms/compportalats).

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Apple kayıt senaryolarına doğrudan erişim <!--951869-->

Intune, Azure Önizleme Portalı'ndaki Cihaz Kaydetme iş yükünü kullanarak Apple kayıt senaryolarına doğrudan erişimi Ocak 2017 sonrasında oluşturulan Intune hesapları için etkinleştirdi. Daha önce, Apple kayıt önizleme sürümüne yalnızca klasik Intune portalı bağlantıları ile erişilebiliyordu. Bu özelliklerin Azure’da kullanılabilmesi için, Ocak 2017 öncesi oluşturulan Intune hesaplarında tek seferlik bir geçiş yapılması gerekir. Geçiş için zaman çizelgesi henüz açıklanmamıştır, ancak konuya ilişkin ayrıntılar olabildiğince çabuk duyurulacaktır. Mevcut hesabınız önizleme sürümüne erişemiyorsa, yeni deneyimi test etmek için bir deneme hesabı oluşturmanızı kesinlikle öneririz.

### <a name="whats-coming-for-appx-in-intune-on-azure----1000270---"></a>Azure'da Intune Appx'leri için yenilikler <!-- 1000270 -->

Azure'da Intune'a geçişin bir parçası olarak üç appx değişikliği yapıyoruz:

1. Klasik Intune konsoluna yalnızca MDM kayıtlı cihazlara dağıtılabilen yeni bir appx uygulama türü ekliyoruz.
2. Var olan appx uygulama türünü yalnızca Intune PC aracısı ile yönetilen PC'lerin hedefleneceği şekilde değiştiriyoruz.
3. Var olan tüm appx'leri geçiş ile MDM appx'leri haline getiriyoruz.

Bu durum Intune PC aracısı üzerinden yönetilen mevcut cihazlarınızı etkilemeyecek. Ancak geçiş yapıldıktan sonra geçişi yapılan bu appx'leri Intune PC aracısı ile yönetilen ve daha önceden hedef alınmayan yeni cihazlara dağıtamayacaksınız.

Yeni PC dağıtımları gerçekleştirmek istiyorsanız geçiş işleminden sonra appx'i PC appx'i olarak yeniden yüklemeniz gerekecek. Daha fazla bilgi için Intune Destek ekibi blog sayfasındaki [Azure'da Intune Appx'lerinde yapılan değişiklikler](https://aka.ms/appxchange) konusuna bakın.  


## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Azure’daki yeni Intune yönetici deneyiminin genel önizlemesi <!--736542-->

2017 takvim yılının başlarında tam yönetici deneyimimizi Azure’a geçireceğiz. Bu sayede Grafik API’leri kullanılarak genişletilebilen modern bir hizmet platformunda çekirdek EMS iş akışlarının güçlü ve tümleşik yönetimi mümkün olacaktır.

Yeni deneme kiracıları, yeni yönetici deneyiminin genel önizlemesini bu ay Azure portalında görmeye başlayacaklar. Önizleme durumundayken, mevcut Intune konsolu ile gelen yetenekler ve eşlik, yinelemeli olarak sağlanır.

Azure portalındaki yönetici deneyimi, duyurulan yeni gruplandırma ve hedefleme işlevselliğini kullanır; mevcut kiracınız yeni gruplandırma deneyimine geçirildiğinde, siz de kiracınıza yönelik yeni yönetici deneyimini önizlemek üzere geçirilirsiniz. Bu sırada, kiracınız geçirilene kadar yeni işlevleri sınamak veya bunlara göz atmak isterseniz yeni bir Intune deneme hesabına kaydolun veya [yeni belgelere](https://docs.microsoft.com/intune/what-is-intune) bakın.

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Android uygulamaları için yönetilen yapılandırma seçenekleri desteği <!-- 621621 -->

Playstore'da yönetilen yapılandırma seçeneklerini destekleyen Android uygulamalarını yapılandırabilirsiniz.  Bu özellik, bir uygulama tarafından desteklenen yapılandırma değerlerinin listesini görüntülemenizi sağlar ve bu değerlerin yapılandırılması için kılavuzlu bir birinci sınıf kullanıcı arabirimi sunar.

### <a name="remote-assistance-for-android-devices----675418---"></a>Android cihazlar için uzaktan yardım <!-- 675418 -->

Intune, Android cihazlarını çalıştıran kullanıcılarınıza uzaktan yardım etmenizi sağlamak için ayrıca satın alınan [TeamViewer](https://www.teamviewer.com) yazılımını kullanır.

### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Android for Work uygulamaları için cihaz izinlerini önceden yapılandırma <!-- 621614 -->

Android for Work cihazı iş profillerine dağıtılan uygulamalarda, tek tek uygulamalar için izin durumunu yapılandırabilirsiniz. Varsayılan olarak, konuma veya cihaz kamerasına erişim gibi cihaz izinlerine ihtiyacı olan Android uygulamaları kullanıcıdan izinleri kabul etmesini veya reddetmesini ister.  Örneğin, uygulama cihazın mikrofonunu kullanıyorsa, son kullanıcıdan mikrofonu kullanmak için uygulamaya izin vermesi istenir. Bu özellik, son kullanıcılar için izinleri tanımlamanıza olanak tanıyacaktır.  Yönetici şu izinleri yapılandırabilir:

- Kullanıcıya bildirmeden otomatik olarak reddetme
- Kullanıcıya bildirmeden otomatik olarak onaylama
- Kullanıcıdan kabul etmesini veya reddetmesini isteme.

### <a name="define-app-specific-pin-for-android-for-work-devices---728976--"></a>Android for Work cihazlarında uygulamaya özgü PIN’i tanımlama <!--728976-->

Android for Work cihazı olarak yönetilen Android 7.0 ve üzeri cihazlarda yalnızca iş profilindeki uygulamalar için geçerli olacak bir geçiş kodu ilkesi tanımlayabilirsiniz.  Şu seçenekler mevcuttur:

- Yalnızca cihaz genelinde bir geçiş kodu ilkesi tanımlama - Bu, son kullanıcının tüm cihazının kilidini açmak için kullanması gereken geçiş kodudur
- Yalnızca bir iş profili geçiş kodu ilkesi tanımlama - İş profilindeki bir uygulama her açıldığında son kullanıcılardan geçiş kodunu girmesi istenir.
- Hem cihaz hem iş profili ilkesi tanımlama - BT ekibinin farklı güç düzeylerinde hem cihaz geçiş kodu ilkesi hem de iş profili geçiş kodu ilkesi tanımlama seçeneği vardır (örneğin, cihazın kilidini açmak için 4 basamaklı bir PIN, ama herhangi bir iş uygulamasını açmak için 6 basamaklı bir PIN)

>[!NOTE]
> Bu özellik yalnızca Android 7.0 ve üzeri sürümlerde kullanılabilir.  Varsayılan olarak, son kullanıcıya ayrı tanımlanmış iki PIN kullanma seçeneği sağlanır veya tanımlanmış olan iki PIN’den en güçlü olanı seçebilirler.

### <a name="manage-password-and-other-android-for-work-settings---1102534--"></a>Parolayı ve diğer Android for Work ayarlarını yönetme <!--1102534-->

Android for Work cihazlarında parola ve iş profili ayarlarını yönetmenizi sağlayan yeni bir Android for Work cihaz kısıtlama ilkesi ekliyoruz.

###  <a name="new-web-content-filter-policy-for-ios-devices----723832---"></a>iOS cihazları için yeni Web içeriği filtresi ilkesi <!-- 723832 -->

iOS cihazlarının ziyaret edebileceği web sitelerini aşağıdaki iki yöntemden birini kullanarak denetleyebilirsiniz:

  - Apple'ın yerleşik web içeriği filtresini kullanarak izin verilen ve engellenen URL'leri ekleyin.
  - Safari tarayıcısı tarafından yalnızca belirli web sitelerine erişilmesine izin verin. Belirttiğiniz siteler için Safari'de yer işaretleri oluşturulur.

### <a name="apple-school-manager-asm-support---748864--"></a>Apple Okul Yöneticisi (ASM) desteği <!--748864-->

Intune, iOS cihazlarında hazır kayıt sağlamak için Apple Cihaz Kaydı Programı yerine Apple Okul Yöneticisi’ni (ASM) destekleyecektir. Paylaşılan iPad’lerde Classroom uygulamasını kullanmak ve Microsoft School Data Sync (SDS) yoluyla ASM’den Azure Active Directory’ye veri eşitlemeyi etkinleştirmek için ASM’nin kullanıma alınması gereklidir.  

### <a name="shared-ipad-support---770395-1044681---"></a>Paylaşılan iPad desteği <!--770395, 1044681 -->

Intune, Apple’ın Cihaz Kayıt Programı veya Apple Okul Yöneticisi için kayıt profilinde Paylaşılan iPad modunun yapılandırmasını destekleyecektir. Bu ayar, birden çok yönetilen Apple Kimliğinin aynı cihazda oturum açmasına olanak tanır.

Ayrıca iOS Classroom uygulamasının kapsamını da, yönetilen Apple Kimliğini kullanarak paylaşılan iPad’lerde oturum açan öğrencileri içerecek şekilde genişleteceğiz.

### <a name="new-windows-device-restriction-settings---978585--"></a>Yeni Windows cihaz kısıtlama ayarları <!--978585-->

Kablosuz ekranlar, cihaz bulma, görev geçişi ve SIM kart hata mesajları gibi özellikleri denetleyen Windows cihaz kısıtlama profiline ayarlar ekliyoruz.

### <a name="office-365-proplus-app-available-for-windows-10-devices---1121362--"></a>Windows 10 cihazları için sağlanan Office 365 ProPlus uygulaması <!--1121362-->

Windows 10 cihazlarına Office 365 ProPlus uygulamalarını atamanızı kolaylaştıran yeni Office 365 ProPlus uygulama türünü ekliyoruz. Bunun yanı sıra, Microsoft Project ve Microsoft Visio lisanslarınız varsa, bu uygulamaları da yükleyebilirsiniz. İstediğiniz uygulamalar birlikte paketlenir ve Intune konsolundaki uygulama listesinde tek uygulama olarak gösterilir.

### <a name="new-allowblock-list-for-the-managed-browser---682960--"></a>Managed Browser için yeni izin verilenler/engellenenler listesi <!--682960-->

Azure portalında Intune Uygulama Yapılandırma ayarlarıyla, Managed Browser için izin verilen/engellenen etki alanları ve URL’ler listesini yapılandırabilirsiniz. Managed Browser’ın yönetilen bir cihazda mı yoksa yönetilmeyen bir cihaz da mı kullanıldığına bakılmaksızın, bu liste yapılandırılabilir.

### <a name="new-app-configuration-capabilities----677969---"></a>Yeni uygulama yapılandırma özellikleri <!-- 677969 -->

Bu özellik, mobil cihaz yönetimi (MDM) uygulama yapılandırmasının eşdeğeridir. Bu, yöneticilerin kayıt kanalı olmadan yalnızca MAM içindeki uygulama koruma ilkeleri aracılığıyla sağlanan uygulama yapılandırma değerlerinden daha fazla uygulama yapılandırma değeri uygulamasına olanak tanır.

### <a name="new-app-protection-policies-conditions-for-mam---679864--"></a>MAM için yeni uygulama koruma ilkesi koşulları <!--679864-->

Yönetici Konsolu aracılığıyla kayıt kullanıcıları olmadan MAM için aşağıdakileri zorunlu tutan bir gereksinim ayarlayabilirsiniz:

- En düşük uygulama sürümü
- En düşük işletim sistemi sürümü
- Hedeflenen uygulamanın en düşük Intune APP SDK’sı sürümü (yalnızca iOS)

Bu özellik hem Android hem de iOS’ta kullanılabilir. Intune; işletim sistemi platformu sürümleri, uygulama sürümleri ve Intune APP SDK’sı için en düşük sürüm zorlamasını destekler. iOS’ta, SDK’nın tümleştirildiği uygulamalar da SDK düzeyinde en düşük sürüm zorlaması ayarlayabilir.

Yukarıda açıklanan 3 farklı düzeyde uygulama koruma ilkesi aracılığıyla belirlenen en düşük gereksinimler karşılanmazsa, kullanıcı hedeflenen uygulamaya erişemez. Bu noktada, kullanıcı hesabını kaldırabilir (çok kimlikli uygulamalarda), uygulamayı kapatabilir ve/veya işletim sistemi veya uygulama sürümünü gereksinimleri karşılayacak şekilde güncelleştirebilir.

Dahası, işletim sistemi veya uygulama yükseltmesi öneren ve engelleyici olmayan bir bildirim sağlamak için, Yönetici Konsolu aracılığıyla ek ayarlar da yapılandırabilirsiniz. Bu bildirim kapatılabilir ve uygulama normal şekilde kullanılabilir.

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Yönetilen cihazların kaydını kaldırmadan MDM yetkilinizi değiştirme <!--1103950-->

Microsoft Desteği’ne başvurmak ve mevcut yönetilen cihazlarınızın kaydını kaldırıp yeniden kaydetmek zorunda kalmadan, MDM yetkilinizi değiştirebilirsiniz. Configuration Manager konsolunda, MDM yetkiliniz için Configuration Manager’a Ayarla (karma) ile Microsoft Intune (tek başına) seçenekleri arasında geçiş yapabilirsiniz.


### <a name="see-also"></a>Ayrıca bkz.
Son geliştirmelere ilişkin ayrıntılar için bkz. [Microsoft Intune’daki Yenilikler](whats-new-in-microsoft-intune.md).

