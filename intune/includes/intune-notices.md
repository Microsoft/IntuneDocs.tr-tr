---
title: dosya ekle
description: dosya ekle
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 5ebab881a524bc361e271856b6762776974cea20
ms.sourcegitcommit: 5807f4db4a45a093ce2fd6cb0c480bec384ec1ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72601519"
---
Bu bildirimler, gelecekteki Intune değişiklik ve özelliklerine hazırlanmanıza yardımcı olabilecek önemli bilgiler sağlar.

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


### <a name="plan-for-change-intune-app-sdk-and-app-protection-policies-for-android-moving-to-support-android-50-and-higher-in-october---4911065---"></a>Değişiklik planı: Ekim 'de Android 5,0 ve üstünü desteklemeye yönelik Android için Intune uygulama SDK 'Sı ve uygulama koruma ilkeleri <!--4911065 -->
Intune, Ekim 'de Android 5. x (Lollipop) ve üstünü destekleyecek şekilde taşınır. Sarmalanan tüm uygulamaları en son Intune uygulama SDK 'Sı ile güncelleştirin ve cihazlarınızı güncelleştirin.

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

### <a name="intune-plan-for-change-nearing-end-of-support-for-windows-7----3042987---"></a>Intune değişiklik planı: Windows 7 için destek sonuna yaklaşıyor <!-- 3042987 -->
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
