---
title: dosya ekle
description: dosya ekle
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 11/19/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 6064fb657454106a8a7213e0bbbcecdcef765857
ms.sourcegitcommit: c7c6be3833d9a63d43f31d598b555b49b33cf5cb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2020
ms.locfileid: "76966376"
---
Bu bildirimler, gelecekteki Intune değişiklik ve özelliklerine hazırlanmanıza yardımcı olabilecek önemli bilgiler sağlar.

### <a name="updated-support-statement-for-adobe-acrobat-reader-for-intune-mobile-app--5746776--"></a>' Intune için Adobe Acrobat Reader ' mobil uygulaması için destek özeti güncelleştirildi<!--5746776-->
Ağustos ayının sonunda MC188653 ' de paylaşıyoruz. Bu, Intune mobil uygulaması için Adobe Acrobat Reader 'ın 1 Aralık 2019 ' de sona erecek ve Adobe uygulamasının, ana Acrobat Reader uygulaması içinde Intune 'un uygulama koruma ilkelerini desteklemeyi planlıyor olması. Bundan sonra, BT yöneticilerinin hedeflemesini sağlamak için daha fazla zaman sunduğumuz ve son kullanıcıların Intune için Adobe Acrobat Reader kullanmaya başlamasını sağlayan müşteri geri bildirimi aldık. Son Kullanıcı cihazlarında Intune için Adobe Acrobat Reader 'ın yüksek kullanımı ve kurumsal senaryolarda önem derecesi verildiğinde, tüm deneyimin kuruluşunuzun uygulama koruma ihtiyaçlarını karşıladığından emin olmak istiyoruz. 

Acrobat Reader mobil uygulaması uygulama koruma Ilkelerini desteklediğinden ve Intune SDK ile tümleştirildiği için ilkelerinizde genel Acrobat Reader mobil uygulamasını hedeflemek öneriyoruz, ancak Intune için Adobe Acrobat Reader uygulaması desteklenmeye devam edecek 31 Mart 2020 tarihine kadar. 

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Bu iletiyi, raporumuz kuruluşunuzdaki bir veya daha fazla ilkeyi Intune için Adobe Acrobat Reader uygulamasını hedeflediğinden ve/veya önceki EOL iletişimimizi almış olabilirsiniz. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Son kullanıcılarınıza ve yardım masasına bu değişikliğin haberdar olmasına izin verin. Intune ile ilgili sorulara yönelik bir kanal oluşturmak için [Şirket portalı destek bilgileri işlevselliğini](../apps/company-portal-app.md#support-information) kullanabilirsiniz.

#### <a name="additional-information"></a>Ek Bilgiler
https://helpx.adobe.com/acrobat/kb/intune-app-end-of-life.html


### <a name="end-support-for-windows-phone-81--3544909--"></a>Windows Phone 8,1 için destek bitişi<!--3544909-->
Windows Phone 8,1 için Microsoft temel desteği 2017 Temmuz 'da sona erdi ve genişletilmiş destek Haziran 2019 ' de sona erdi. Windows Phone 8,1 için Şirket Portalı uygulaması, 2017 ' den bu yana bir moda sahip. Microsoft Intune, Windows Phone 8,1 için 20 Şubat 2020 ' de desteği sona erdirmek için.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
20 Şubat 2020 ' den sonra bu cihazlar herhangi bir güvenlik güncelleştirmesi almaz ve yeni cihazları kaydedemeyeceksiniz. Mevcut Windows Phone 8,1 cihazları kayıtlı kalır (ilke, uygulamalar, raporlama), ancak üçüncü taraf sertifikalar gibi birçok bileşen bu tarihten sonra bu tarihten sonra mevcut bir kayıt ile ilgili sorun gidermeyi desteklemez platformunun. Intune, Intune ile uyumluluk sınamasını durdurur ve 8,1 Windows Phone.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Hangi cihazların veya kullanıcıların etkilendiğini görmek için Intune raporlamayı kontrol edebilirsiniz. Cihazlar > Tüm cihazlar'a gidin ve işletim sistemine göre filtre uygulayın. Kuruluşunuzda Windows Phone 8,1 çalıştıran cihazların kim olduğunu belirlemenize yardımcı olması için ek sütunlar ekleyebilirsiniz. Son kullanıcılarınızın cihazlarını desteklenen bir işletim sistemi sürümüne yükseltmesini isteyin.


### <a name="take-action-use-microsoft-edge-for-your-protected-intune-browser-experience--5728447--"></a>Işlem yapın: korumalı Intune tarayıcı deneyiminiz için Microsoft Edge kullanın<!--5728447-->
Geçtiğimiz yıl içinde paylaşım yaptığımız gibi, Microsoft Edge Mobile, çok daha gelişmiş bir son kullanıcı deneyimi sağlarken Managed Browser aynı yönetim özellikleri kümesini destekler. Microsoft Edge 'de sunulan güçlü deneyimlere yönelik bir yöntem oluşturmak için Intune Managed Browser devre dışı bırakılacağız. 27 Ocak 2020 tarihinden itibaren Intune artık Intune Managed Browser desteklemezler.  

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek? 
1 Şubat 2020 ' den itibaren, Intune Managed Browser artık Google Play Store veya iOS App Store 'da kullanılamayacak. Bu noktada yeni uygulama koruma ilkelerini Intune Managed Browser hedefleyebilirsiniz, ancak yeni kullanıcılar Intune Managed Browser uygulamasını indiremezler. Ayrıca, iOS 'ta, MDM 'ye kayıtlı cihaza gönderilen yeni web klipleri Intune Managed Browser yerine Microsoft Edge 'de açılır.  

Mart 31 2020 ' de Intune Managed Browser Azure konsolundan kaldırılacak. Bu, artık Intune Managed Browser için yeni ilkeler oluşturamayacak anlamına gelir. Mevcut Intune Managed Browser ilkeleri varsa, bunlar etkilenmez. Intune Managed Browser konsolunda, hiçbir simge olmadan bir LOB uygulaması olarak görünür ve mevcut ilkeler uygulamaya hala hedeflenmiş olarak görünür. Bu noktada, uygulama koruma ilkelerinin veri koruma bölümünde yer alan Intune Managed Browser Web içeriğini yönlendirme seçeneğini de kaldıracağız.  

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek? 
Intune Managed Browser Microsoft Edge 'e kesintisiz geçiş sağlamak için aşağıdaki adımları önceden gerçekleştirmeniz önerilir: 

1. İOS ve Android için Microsoft Edge 'i uygulama koruma ilkesiyle (MAM olarak da bilinir) ve uygulama yapılandırma ayarlarına hedefleyin. Mevcut ilkeleri Microsoft Edge 'de hedefleyerek Microsoft Edge için Intune Managed Browser ilkelerini yeniden kullanabilirsiniz.  
2. Ortamınızdaki tüm MAM korunan uygulamaların "diğer uygulamalarla Web içeriği aktarımını kısıtla" ayarı "Ilkeyle yönetilen tarayıcılar" olarak ayarlanmış Uygulama koruma ilkesi ayarına sahip olduğundan emin olun. 
3. Tüm MAM korumalı uygulama yapılandırma ayarı "com. Microsoft. Intune. useEdge" değeri true olarak ayarlandı. Sonraki ay 1911 sürümü ile başlayarak, uygulama koruma ilkelerinizin veri koruma bölümünde "diğer uygulamalarla Web içeriği aktarımını kısıtla" ayarını "Microsoft Edge" olarak yapılandırarak adım 2 ve 3 ' ü tek yapmanız mümkün olacaktır. . 

İOS ve Android 'de web klipleri için destek geliyor. Bu destek yayınlandığında, Managed Browser yerine Microsoft Edge 'de açıldıklarından emin olmak için önceden mevcut web kliplerini yeniden hedeflemeniz gerekir. 

#### <a name="additional-information"></a>Ek bilgiler
Daha fazla bilgi için [Microsoft Edge 'i uygulama koruma ilkeleriyle birlikte kullanarak](../apps/manage-microsoft-edge.md) belgelerimizi ziyaret edin veya [destek blog gönderimizi](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Use-Microsoft-Edge-for-your-Protected-Intune-Browser-Experience/ba-p/1004269)görüntüleyin.


### <a name="end-of-support-for-legacy-pc-management"></a>Eski PC yönetimi için destek sonu

Eski PC yönetimi, 15 Ekim 2020 ' de destek altına geçiyor. Cihazları Windows 10 ' a yükseltin ve Intune tarafından yönetilmek üzere bunları mobil cihaz yönetimi (MDM) cihazları olarak yeniden kaydedin.

[Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=2107122)

### <a name="decreasing-support-for-android-device-administrator"></a>Android Cihaz Yöneticisi desteğini azaltma 
Android Cihaz Yöneticisi (bazen "eski" Android yönetimi ve Android 2,2 ile kullanıma sunulan) Android cihazlarını yönetmenin bir yoludur. Ancak, geliştirilmiş yönetim işlevselliği artık [Android Enterprise](../enrollment/connect-intune-android-enterprise.md) (Android 5,0 ile yayımlanmıştır) ile kullanılabilir. Modern, daha zengin ve daha güvenli cihaz yönetimine geçiş çabasında, Google yeni Android sürümlerindeki Cihaz Yöneticisi desteğini düşürdüğünde.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Google tarafından yapılan bu değişiklikler nedeniyle Intune kullanıcıları aşağıdaki yollarla etkilenecektir:  
- Intune, yalnızca S2 CY2020 aracılığıyla Android 10 ve üzeri çalıştıran cihaz yönetici tarafından yönetilen Android cihazları için tam destek sağlayabilecektir. Cihaz Yöneticisi-bu süre sonunda Android 10 veya sonraki sürümleri çalıştıran yönetilen cihazlar tamamen yönetilemez. Özellikle, etkilenen cihazlar yeni parola gereksinimleri almaz.
    - Bu zaman diliminde, Intune 'un Knox platformuyla tümleştirilmesi aracılığıyla genişletilmiş destek sağlandığı için Samsung KNOX cihazları etkilenmez. Bu, daha fazla zaman Cihaz Yöneticisi yönetimi 'nin geçişini planlamak için daha fazla zaman sağlar.    
- Android 10 ' un altında kalan Android sürümlerinde kalan Cihaz Yöneticisi ile yönetilen Android cihazları etkilenmez ve cihaz yöneticisiyle tamamen yönetilmeye devam edebilir.    
- Android 10 ve üzeri çalıştıran tüm cihazlarda, Google, Şirket Portalı gibi cihaz yönetici yönetim aracılarının cihaz tanımlayıcı bilgilerine erişmesine olanak sağlar. Bu kısıtlama, bir cihaz Android 10 veya sonraki bir sürüme güncelleştirildikten sonra aşağıdaki Intune özelliklerini etkiler:  
    - VPN için ağ erişim denetimi artık çalışmayacak.   
    - Cihazların ıMEı veya seri numarası ile şirkete ait olarak tanımlanması cihazları şirkete ait olarak otomatik olarak işaretlemez.  
    - IMEı ve seri numarası artık Intune 'da BT yöneticileri için görünür olmayacaktır. 
        > [!NOTE]
        > Bu, yalnızca Android 10 ve üzeri cihazlarda cihaz yöneticisi tarafından yönetilen cihazları etkiler ve Android Enterprise olarak yönetilmekte olan cihazları etkilemez. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
S3 CY2020 ' de gelen işlevselliğin azalmasını önlemek için şunları yapmanızı öneririz:
- Cihaz Yöneticisi yönetimine yeni cihaz eklemeyin.
- Bir cihazın Android 10 güncelleştirmesi alması bekleniyorsa, cihazı Cihaz Yöneticisi yönetiminden Android kurumsal yönetim ve/veya uygulama koruma ilkelerine geçirin.

#### <a name="additional-information"></a>Ek bilgiler
- [Google 'ın cihaz yöneticisinden Android kuruluşa geçiş kılavuzu](http://static.googleusercontent.com/media/android.com/en/enterprise/static/2016/pdfs/enterprise/Android-Enterprise-Migration-Bluebook_2019.pdf)
- [Google 'ın Cihaz Yöneticisi API 'sini kullanımdan kaldırma planına yönelik belgeleri](https://developers.google.com/android/work/device-admin-deprecation)

### <a name="plan-for-change-intune-app-sdk-and-app-protection-policies-for-android-moving-to-support-android-50-and-higher-in-an-upcoming-release---4911065---"></a>Değişiklik planı: Android 5,0 ve sonraki sürümlerde Android ve üstünü desteklemek için Intune uygulama SDK 'Sı ve uygulama koruma ilkeleri <!--4911065 -->
Intune, gelecek sürümlerde Android 5. x (Lollipop) ve üstünü destekleyecek şekilde hareket edecektir. Sarmalanan tüm uygulamaları en son Intune uygulama SDK 'Sı ile güncelleştirin ve cihazlarınızı güncelleştirin.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
' I kullanmıyorsanız veya Android için SDK ya da uygulama kullanmayı planlıyorsanız bu değişiklik sizi etkilemez. Intune uygulama SDK 'sını kullanıyorsanız, en son sürüme güncelleştirdiğinizden emin olun ve ayrıca cihazlarınızı Android 5. x ve üzeri olarak güncelleştirin. Güncelleştirme yapmazsanız, uygulamalar güncelleştirmeleri almaz ve deneyiminin kalitesi zaman içinde azalyacaktır.

Android sürüm 4. x çalıştıran Intune 'A kayıtlı ortak cihazların listesini aşağıda bulabilirsiniz. Bu cihazlardan birine sahipseniz, bu cihazın Android sürüm 5,0 veya üstünü desteklediğinden emin olmak veya Android sürüm 5,0 veya üstünü destekleyen bir cihazla değiştirilmesini sağlamak için uygun adımları uygulayın. Bu liste değerlendirilmesi gerekebilecek tüm cihazların kapsamlı bir şekilde değildir:

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
- MDM yönetimini kullanarak Windows 10 yönetmek için, mevcut eski Intune yazılım istemcisi tarafından yönetilen ve Microsoft tarafından önerilen çözüme geçiş yapın. Tüm yeni Windows 10 bilgisayarlarını Azure portal Intune için MDM yönetimini kullanarak kaydedin.

Daha fazla bilgi için [buraya blog gönderisine](https://aka.ms/Windows7_Intune)bakın.


