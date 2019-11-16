---
title: dosya ekle
description: dosya ekle
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 11/4/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 3d49d31ed08683508d3d231521e578688dd21bac
ms.sourcegitcommit: 737ad6c675deedfc6009f792023ff95981b06582
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2019
ms.locfileid: "74125629"
---
Bu bildirimler, gelecekteki Intune değişiklik ve özelliklerine hazırlanmanıza yardımcı olabilecek önemli bilgiler sağlar.

### <a name="intune-plan-for-change-windows-10-version-1703-company-portal-moving-out-of-support--5026679--"></a>Intune değişiklik planı: Windows 10, sürüm 1703 Şirket Portalı Destek dışı<!--5026679-->
Windows 10, sürüm 1703 (Windows 10, RS2 olarak da bilinir), kurumsal ve EDU sürümleri için 8 Ekim 2019 tarihinde hizmet dışına geçmiştir. Intune, RS2/RS1 için karşılık gelen Şirket Portalı uygulamasına yönelik destek, 26 Aralık 2019 ' den itibaren sona acaktır.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Bundan sonra, Şirket Portalı uygulamasının belirli bir sürümünde yeni özellikler görmezsiniz, ancak bu Şirket Portalı uygulamasının bu sürümünü 2019 Aralık ' e kadar bir şekilde desteklemeye devam edeceğiz, ancak şu şekilde Şirket Portalı uygulamasına yönelik güvenlik güncelleştirmeleri sağlar duyulduğunda. Bununla birlikte, Windows 10, sürüm 1703, hizmet dışına taşındıktan sonra herhangi bir güvenlik güncelleştirmesi almadıklarından, Windows cihazlarınızı daha yeni bir Windows sürümüne güncelleştirmenizi ve en son Şirket Portalı uygulamada olduğunuzdan emin olmanız önerilir. yeni özellikler ve ek işlevler.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Gerçekleştirebileceğiniz adımlar ortamınızın nasıl yapılandırıldığına bağlıdır. Genel olarak, işletim sisteminin eski sürümüne ve/veya Şirket Portalı cihazlarındaki cihazları ve güncelleştirmeleri belirlemeniz gerekir. Windows 10 güncelleştirme Halkalarınızı ayarlamak için Intune-> yazılım güncelleştirmeleri – Windows 10 güncelleştirme halkaları ' na oturum açın. Şirket Portalı en son sürümü 10.3.5601.0 sürümüdür. Lütfen kullanıcılarınızın gelecek sürümlerde güncel kalmasını sağlamak için bunu Microsoft Store almak üzere doğrudan yönlendirin. Intune 'u, [iş için Microsoft Store](https://docs.microsoft.com/intune/windows-store-for-business)aracılığıyla en son Windows cihazlarınıza yüklemek için de kullanabilirsiniz.

#### <a name="additional-information"></a>Ek bilgiler
[Microsoft Intune kullanarak Windows 10 Şirket Portalı uygulamasını el ile ekleme](https://docs.microsoft.com/intune/store-apps-company-portal-app)


### <a name="take-action-use-microsoft-edge-for-your-protected-intune-browser-experience--5728447--"></a>Işlem yapın: korumalı Intune tarayıcı deneyiminiz için Microsoft Edge kullanın<!--5728447-->
Geçtiğimiz yıl içinde paylaşım yaptığımız gibi, Microsoft Edge Mobile, çok daha gelişmiş bir son kullanıcı deneyimi sağlarken Managed Browser aynı yönetim özellikleri kümesini destekler. Microsoft Edge 'de sunulan güçlü deneyimlere yönelik bir yöntem oluşturmak için Intune Managed Browser devre dışı bırakılacağız. 27 Ocak 2020 tarihinden itibaren Intune artık Intune Managed Browser desteklemezler.  

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek? 
1 Şubat 2020 ' den itibaren, Intune Managed Browser artık Google Play Store veya iOS App Store 'da kullanılamayacak. Bu noktada yeni uygulama koruma ilkelerini Intune Managed Browser hedefleyebilirsiniz, ancak yeni kullanıcılar Intune Managed Browser uygulamasını indiremeyecektir. Ayrıca, iOS 'ta, MDM 'ye kayıtlı cihaza gönderilen yeni web klipleri Intune Managed Browser yerine Microsoft Edge 'de açılır.  

Mart 31 2020 ' de Intune Managed Browser Azure konsolundan kaldırılacak. Bu, artık Intune Managed Browser için yeni ilkeler oluşturamayacak anlamına gelir. Mevcut Intune Managed Browser ilkeleri varsa, bunlar etkilenmeyecektir. Intune Managed Browser konsolunda, hiçbir simge olmadan bir LOB uygulaması olarak görünür ve mevcut ilkeler uygulamaya hala hedeflenmiş olarak görünür. Bu noktada, uygulama koruma ilkelerinin veri koruma bölümünde yer alan Intune Managed Browser Web içeriğini yönlendirme seçeneğini de kaldıracağız.  

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek? 
Intune Managed Browser Microsoft Edge 'e kesintisiz geçiş sağlamak için aşağıdaki adımları önceden gerçekleştirmeniz önerilir: 

1. İOS ve Android için Microsoft Edge 'i uygulama koruma ilkesiyle (MAM olarak da bilinir) ve uygulama yapılandırma ayarlarına hedefleyin. Yalnızca var olan ilkeleri Microsoft Edge 'de hedefleyerek Microsoft Edge için Intune Managed Browser ilkelerini yeniden kullanabilirsiniz.  
2. Ortamınızdaki tüm MAM korunan uygulamaların "diğer uygulamalarla Web içeriği aktarımını kısıtla" ayarı "Ilkeyle yönetilen tarayıcılar" olarak ayarlanmış Uygulama koruma ilkesi ayarına sahip olduğundan emin olun. 
3. Tüm MAM korumalı uygulama yapılandırma ayarı "com. Microsoft. Intune. useEdge" değeri true olarak ayarlandı. Sonraki ay 1911 sürümü ile başlayarak, uygulama koruma ilkelerinizin veri koruma bölümünde "diğer uygulamalarla Web içeriği aktarımını kısıtla" ayarını "Microsoft Edge" olarak yapılandırarak adım 2 ve 3 ' ü tek yapmanız mümkün olacaktır. . 

İOS ve Android 'de web klipleri için destek geliyor. Bu destek yayınlandığında, Managed Browser yerine Microsoft Edge 'de açıldıklarından emin olmak için önceden mevcut web kliplerini yeniden hedeflemeniz gerekir. 

#### <a name="additional-information"></a>Ek bilgiler
Daha fazla bilgi için lütfen [Microsoft Edge 'i uygulama koruma ilkeleriyle birlikte kullanarak](../apps/manage-microsoft-edge.md) belgelerimizi ziyaret edin veya [destek blog gönderimizi](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Use-Microsoft-Edge-for-your-Protected-Intune-Browser-Experience/ba-p/1004269)görüntüleyin.


### <a name="plan-for-change-updated-experience-when-enrolling-android-enterprise-dedicated-devices-in-intune--5198878--"></a>Değişiklik planı: Intune 'da Android kurumsal adanmış cihazlarını kaydetme deneyimi güncelleştirildi<!--5198878-->
Intune 'a Kasım veya 1911 sürümü ile, Wi-Fi profillerine sertifika tabanlı erişim sağlamak için Android kurumsal adanmış cihazlara SCEP cihaz sertifikası dağıtımı desteği ekledik. Bu değişiklik Ayrıca Android kurumsal adanmış cihazları kaydedilirken akış küçük değişiklikler içerir.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Ortamınızdaki Android kurumsal adanmış cihazları yönetiyorsanız, Kasım ayında bazı değişiklikleri kullanıma sunarak çalışmaya başlayabilirsiniz.

- Yeni Android kurumsal adanmış cihaz kayıtları için: son kullanıcılar, kayıt sırasında cihazlarda farklı bir adım kümesi görür. Kayıt, bugün (QR, NFC, sıfır-Touch veya cihaz tanımlayıcısı ile) çalışmaya devam eder, ancak Kasım hizmeti sürümünden sonra zorunlu bir uygulama yüklemesi adımı olacaktır.
- Adanmış cihazlar olarak kaydedilen mevcut Android cihazları için: Intune, ilk Kasım 'Dan başlayarak cihazlara Microsoft Intune uygulamasını otomatik olarak yüklemeye başlar. Herhangi bir işlem yapmanız gerekmez. Uygulama, cihazlara otomatik olarak indirilir ve yüklenir. 

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapabilirim?
Son Kullanıcı kılavuzunuzu güncelleştirmeyi planlamalısınız ve yardım masanızla bu değişikliği bilmesini sağlayabilirsiniz. Daha fazla ayrıntı ve ekran görüntüsü için ek bilgiler ' e tıklayın. Bu değişiklik kullanıma sunulmaya başladığında yenilikler sayfamızı güncelleştireceğiz.

#### <a name="additional-information"></a>Ek bilgiler
[https://aka.ms/Dedicated_devices_enrollment](https://aka.ms/Dedicated_devices_enrollment)

### <a name="plan-for-change-the-server-side-logging-for-siri-commands-setting-will-be-removed-from-the-intune-console----5468501--"></a>Değişiklik planı: ' Siri komutları için sunucu tarafında günlüğe kaydetme ' ayarı Intune konsolundan kaldırılacak <!-- 5468501-->

Intune konsolundaki "Siri komutları için sunucu tarafında günlüğe kaydetme" ayarını, Kasım güncelleştirmesi ile Intune hizmetine kaldırmayı planlıyoruz. Bu değişiklik, Apple 'ın bu ayarı kendi tarafında kaldırmış olduğu şekilde hizalar.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Kasım güncelleştirmesi veya 1911, orta Kasım 'Dan sonra çalıştırıldığında, bu ayarın Intune konsolundaki iOS yapılandırma profillerinin cihaz kısıtlamaları menüsünden (yerleşik uygulamalar) kaldırıldığını görürsünüz. İlkelerinizde ve hedeflenen cihazın yönetim profilinde görünebilir, ancak bu ayarın cihazınızda hiçbir etkisi yoktur. Yönetim profilinde görseniz bile şu anda cihazlarda çalışmadıklarından, işlevselliğe çok etkisi önliyoruz.

İki yoldan birini seçebilirsiniz:
- Bu ayarı ilkelerinizden silmek istiyorsanız, bu ayarı içeren profile gidebilirsiniz, ikincil düzenleme yapabilir ve ilkeyi kaydedebilirsiniz. İlke arka uçta yeniden işlem görür ve bu ayar ilkeden silinir.
- Bu eylemi gerçekleştirmek istemiyorsanız, son kullanıcılar bu ayarı cihazlarının yönetim profilinde görür ancak ayarın hiçbir etkisi olmayacaktır.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapabilirim?
Yukarıdaki bölüme göre işlem gerçekleştirebilir veya ilkenizi olduğu gibi bırakabilirsiniz. Bu değişiklik tamamlandığında, yenilikler sayfası ve belgeleri güncelleştireceğiz.

### <a name="end-of-support-for-legacy-pc-management"></a>Eski PC yönetimi için destek sonu

Eski PC yönetimi, 15 Ekim 2020 ' de destek altına geçiyor. Cihazları Windows 10 ' a yükseltin ve Intune tarafından yönetilmek üzere bunları MDM cihazları olarak yeniden kaydedin.

[Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2107122)

### <a name="decreasing-support-for-android-device-administrator"></a>Android Cihaz Yöneticisi desteğini azaltma 
Android Cihaz Yöneticisi (bazen "eski" Android yönetimi ve Android 2,2 ile kullanıma sunulan) Android cihazlarını yönetmenin bir yoludur. Ancak, geliştirilmiş yönetim işlevselliği artık [Android Enterprise](../enrollment/connect-intune-android-enterprise.md) (Android 5,0 ile yayımlanmıştır) ile kullanılabilir. Modern, daha zengin ve daha güvenli cihaz yönetimine geçiş çabasında, Google yeni Android sürümlerindeki Cihaz Yöneticisi desteğini düşürdüğünde.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Google tarafından yapılan bu değişiklikler nedeniyle Intune kullanıcıları aşağıdaki yollarla etkilenecektir:  
- Intune, 2020 yaz aracılığıyla yalnızca Android 10 ve üzeri (Android Q olarak da bilinir) çalıştıran cihaz yönetici tarafından yönetilen Android cihazları için destek sağlayabilecektir. Bu tarih, Android 'in bir sonraki ana sürümünün yayımlanması beklendiğinde oluşur.   
- 2020 yaz sonrasında Android 10 veya üzerini çalıştıran Cihaz Yöneticisi tarafından yönetilen cihazlar artık tamamen yönetimeyecektir.       
- Android 10 ' un altında kalan Android sürümlerinde kalan Cihaz Yöneticisi ile yönetilen Android cihazları etkilenmeyecektir ve cihaz yöneticisiyle tamamen yönetilmeye devam edebilir.    
- Android 10 ve üzeri çalıştıran tüm cihazlarda, Google, Şirket Portalı gibi cihaz yönetici yönetim aracılarının cihaz tanımlayıcı bilgilerine erişmesine olanak sağlar. Bu, bir cihaz Android 10 veya üzeri güncelleştirmeler güncelleştirildikten sonra aşağıdaki Intune özelliklerini etkiler:  
    - VPN için ağ erişim denetimi artık çalışmayacak.   
    - Cihazları bir ıMEı veya seri numarası ile şirkete ait olarak tanımlamak, cihazları şirkete ait olarak otomatik olarak işaretlemez.  
    - IMEı ve seri numarası artık Intune 'da BT yöneticileri için görünür olmayacaktır. 
        > [!NOTE]
        > Bu, yalnızca Android 10 ve üzeri cihazlarda cihaz yöneticisi tarafından yönetilen cihazları etkiler ve Android Enterprise olarak yönetilmekte olan cihazları etkilemez. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
2020 tarihinde gelen işlevselliğin azalmasına engel olmak için şunları öneririz:
- Cihaz Yöneticisi yönetimine yeni cihaz eklemeyin.
- Bir cihazın Android 10 güncelleştirmesi alması bekleniyorsa, cihazı Cihaz Yöneticisi yönetiminden Android kurumsal yönetim ve/veya uygulama koruma ilkelerine geçirin.

#### <a name="additional-information"></a>Ek bilgiler
- [Google 'ın cihaz yöneticisinden Android kuruluşa geçiş kılavuzu](http://static.googleusercontent.com/media/android.com/en/enterprise/static/2016/pdfs/enterprise/Android-Enterprise-Migration-Bluebook_2019.pdf)
- [Google 'ın Cihaz Yöneticisi API 'sini kullanımdan kaldırma planına yönelik belgeleri](https://developers.google.com/android/work/device-admin-deprecation)

### <a name="update-your-android-company-portal-app-to-the-latest-version---4536963--"></a>Android Şirket Portalı uygulamanızı en son sürüme güncelleştirme <!--4536963-->
Intune, güncelleştirmeleri düzenli aralıklarla Android Şirket Portalı uygulamasına yayınlar. Kasım 2018 ' de, Google 'ın mevcut bildirim platformundan Google 'ın Firebase bulut mesajlaşmasına (FCM) değişikliğini hazırlamaya yönelik bir arka uç anahtarı içeren bir şirket portalı güncelleştirmesi yayımladık. Google 'ın mevcut bildirim platformunu yeniden bilgilendirmesi ve FCM 'ye taşınmasıyla, son kullanıcıların Google Play depolarıyla iletişime devam etmek için Şirket Portalı uygulamalarını en az Kasım 2018 sürümüne güncelleştirmiş olmaları gerekecektir.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Telemetrimiz, 5.0.4269.0 ' den önceki Şirket Portalı sürüme sahip cihazlarınız olduğunu gösterir. Şirket Portalı uygulamasının bu sürümü veya sonraki bir sürümü yüklü değilse, bu cihaz, Temizleme, parola sıfırlama, kullanılabilir ve gerekli uygulama yüklemeleri ve sertifika kaydı beklendiği gibi çalışmayabilir. Cihazlarınız Intune 'A kayıtlı ise, Istemci uygulamalar – bulunan uygulamalar ' a giderek Şirket Portalı sürümlerini ve kullanıcıları görebilirsiniz. Şirket Portalı uygulamasının önceki sürümlerini seçmek, hangi son kullanıcıların Şirket Portalı uygulamasını güncelleştirilmemiş cihazlara sahip olduğunu görmenizi sağlar.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Şirket Portalı uygulamasını Google Play aracılığıyla güncelleştirmek için güncelleştirilmemiş son Android cihaz kullanıcılarına sorun. Kullanıcı Şirket Portalı uygulamasını otomatik olarak güncelleştirmediğinden yardım masasına bildirin. Google 'ın FCM platformu ve değişikliği hakkında daha fazla *bilgi* için bağlantıya bakın.

#### <a name="additional-information"></a>Ek bilgiler
https://firebase.google.com/docs/cloud-messaging/


### <a name="new-full-screen-experience-coming-to-intune---4593669--"></a>Intune 'a gelen yeni tam ekran deneyimi <!--4593669-->
Azure portal Intune 'a güncelleştirilmiş Kullanıcı arabirimi deneyimlerini oluşturma ve düzenleme hakkında bilgi alırız. Bu yeni deneyim, bir dikey pencerede sıkıştırılmış bir sihirbaz stili biçimi kullanarak mevcut iş akışlarını basitleştirir. Bu güncelleştirme "dikey pencere genişlemesine" ya da derin dikey pencerenin ayrıntılarına gidebilmeniz için akış oluştur ve Düzenle akışları ile çalışır. İş akışları oluşturma, atamaları içerecek şekilde da güncelleştirilecektir (uygulama ataması hariç).

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Tam ekran deneyimi, portal.azure.com ve devicemanagement.microsoft.com ' de bir sonraki birkaç ayda Intune 'a alınacaktır. Kullanıcı arabirimine yönelik bu güncelleştirme, var olan ilkelerinizin ve profillerinizin işlevlerini etkilemez, ancak biraz değiştirilen bir iş akışı görürsünüz. Örneğin, yeni ilkeler oluşturduğunuzda, ilkeyi oluşturduktan sonra bunu yapmak yerine, bu akışın bir parçası olarak bazı atamalar ayarlayabileceksiniz. Yeni deneyimin konsolda nasıl görüneceğine ilişkin ekran görüntüleri hakkında *ek bilgi* için blog gönderisine bakın.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapabilirim?
Herhangi bir eylemde bulunmanıza gerek yoktur, ancak gerekirse BT uzmanı kılavuzunuzu güncellemeyi düşünebilirsiniz. Bu deneyim Azure portal Intune 'daki çeşitli dikey pencerelere yaptığı için belgelerimizi güncelleştireceğiz.

#### <a name="additional-information"></a>Ek bilgiler 
https://aka.ms/intune_fullscreen

### <a name="plan-for-change-intune-app-sdk-and-app-protection-policies-for-android-moving-to-support-android-50-and-higher-in-an-upcoming-release---4911065---"></a>Değişiklik planı: Android 5,0 ve sonraki sürümlerde Android ve üstünü desteklemek için Intune uygulama SDK 'Sı ve uygulama koruma ilkeleri <!--4911065 -->
Intune, gelecek sürümlerde Android 5. x (Lollipop) ve üstünü destekleyecek şekilde hareket edecektir. Sarmalanan tüm uygulamaları en son Intune uygulama SDK 'Sı ile güncelleştirin ve cihazlarınızı güncelleştirin.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
' I kullanmıyorsanız veya Android için SDK ya da uygulama kullanmayı planlıyorsanız bu değişiklik sizi etkilemez. Intune uygulama SDK 'sını kullanıyorsanız, en son sürüme güncelleştirdiğinizden emin olun ve ayrıca cihazlarınızı Android 5. x ve üzeri olarak güncelleştirin. Güncelleştirme yapmazsanız, uygulamalar güncelleştirmeleri almaz ve deneyiminin kalitesi zaman içinde azalacaktır.

Android sürüm 4. x çalıştıran Intune 'A kayıtlı ortak cihazların listesini aşağıda bulabilirsiniz. Bu cihazlardan birine sahipseniz, bu cihazın Android sürüm 5,0 veya üstünü desteklediğinden emin olmak veya Android sürüm 5,0 veya üstünü destekleyen bir cihazla değiştirilmesini sağlamak için uygun adımları uygulayın. Bu liste değerlendirilmesi gerekebilecek tüm cihazların bir tam değildir:

- Samsung SM-T561  
- Samsung SM-T365
- Samsung GT-I9195
- Samsung SM-G800F
- Samsung SM-G357FZ
- Motorola XT1080
- Samsung GT-I9305
- Samsung SM-T231

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Uygulamalarınızı en son Intune uygulama SDK 'Sı ile sarın. Ayrıca, kişisel cihazlarda son kullanıcıların yükseltmesini bildirmek için "En düşük işletim sistemi sürümünü gerektir (yalnızca uyarı)" koşullu başlatma ayarını da ayarlayabilirsiniz.

### <a name="intune-plan-for-change-nearing-end-of-support-for-windows-7---3042987---"></a>Intune değişiklik planı: Windows 7 için destek sonuna yaklaşıyor<!-- 3042987 -->
MC148476 içinde, son 2018 Eylül ' de ve yeniden MC176794 ' de 2019 ' de, Windows 7, 14 Ocak 2020 tarihinde genişletilmiş destek sonuna ulaştı. Bu sırada Intune, Windows 7 çalıştıran cihazların desteğini devre dışı bırakacaktır, böylece yeni teknolojileri desteklemeye ve harika yeni son kullanıcı deneyimleri sağlamaya yönelik yatırımımızı odaklamaya devam edebilir. Bu tarihten sonra, Windows 7 BILGISAYARıNıZı korumaya yardımcı olan teknik yardım ve otomatik güncelleştirmeler artık Intune aracılığıyla kullanılamayacak. Microsoft, artık mevcut olmayan hizmet veya destek gerektiren bir senaryoya engel olmak için 2020 Ocak 'tan önce Windows 10 ' a geçmeniz önerilir. [Burada](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)Windows destek yaşam döngüsü hakkında daha fazla bilgi edinin.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Bu iletiyi, şu anda eski Intune PC yazılım Aracısı 'nı kullanarak Windows 7 bilgisayarlarını yönettiğiniz için alıyorsunuz. Bir yıldan daha az Windows 7 genişletilmiş destek 'in sonundan önce kaldığı için, kuruluşunuzun Windows 10 ' a en kısa sürede yükseltmeye başlamasını kesinlikle öneririz.  

BILGISAYAR yönetimi özellikleri doğrudan Windows 10 işletim sisteminde yerleşiktir ve artık Windows 7 için Intune yazılım istemcisi gibi bir istemci aracısını yüklemeniz gerekmez. Microsoft, Windows 8.1 başlayarak Windows bilgisayarlarını sağlamak, yapılandırmak, güncelleştirmek ve yönetmek için mobil cihaz yönetimi (MDM) mimarisini kullanır. Intune 'u ayarladıktan sonra, Windows 10 bilgisayarlarını MDM kanalı aracılığıyla [Intune 'a](..\windows-enroll.md) kaydederek Windows kaydını kolaylaştırabilirsiniz. Windows 10 bilgisayarlarınızı yönetmek için bu "aracısız" MDM yönetimi çözümünü kullanmanızı öneririz.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Kuruluşunuzun bu eylem planını anında kabul etmeyi öneririz:

- 14 Ocak 2020 tarihinden önce Windows 7 ' yi planlayın ve Windows 10 ' a yükseltin.
- Mevcut Windows 7 PC 'nizi Windows 10 ' a yükseltme hakkında daha fazla bilgi edinmek için [Windows 10 dağıtım desteği](https://docs.microsoft.com/windows/deployment/) ' ni araştırın.
- Microsoft uygulama uyumluluğu taahhüdüne yardımcı olacak, FastTrack aracılığıyla sunulan [Masaüstü uygulamasını](https://www.microsoft.com/fasttrack/microsoft-365/desktop-app-assure?rtc=1) gözden geçirin.
- MDM yönetimini kullanarak Windows 10 yönetmek için, mevcut eski Intune yazılım istemcisi tarafından yönetilen cihazları Microsoft tarafından önerilen çözüme geçirin. Tüm yeni Windows 10 bilgisayarlarını Azure portal Intune için MDM yönetimini kullanarak kaydedin.

Daha fazla bilgi için [buraya blog gönderisine](https://aka.ms/Windows7_Intune) bakın.
