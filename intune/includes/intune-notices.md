---
title: include dosyası
description: include dosyası
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 90c770fec5bd9456151e601188254a3a022cd13f
ms.sourcegitcommit: 62c41976c4da43b36015b715bc255397ebb8c6ad
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71279913"
---
Bu bildirimler, gelecekteki Intune değişiklik ve özelliklerine hazırlanmanıza yardımcı olabilecek önemli bilgiler sağlar. 


### <a name="decreasing-support-for-android-device-administrator"></a>Android Cihaz Yöneticisi desteğini azaltma 
Android Cihaz Yöneticisi (bazen "eski" Android yönetimi ve Android 2,2 ile kullanıma sunulan) Android cihazlarını yönetmenin bir yoludur. Ancak, geliştirilmiş yönetim işlevselliği artık [Android Enterprise](../connect-intune-android-enterprise.md) (Android 5,0 ile yayımlanmıştır) ile kullanılabilir. Modern, daha zengin ve daha güvenli cihaz yönetimine geçiş çabasında, Google yeni Android sürümlerindeki Cihaz Yöneticisi desteğini düşürdüğünde.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Google tarafından yapılan bu değişiklikler nedeniyle Intune kullanıcıları aşağıdaki yollarla etkilenecektir: 
- Intune yalnızca, yaz 2020 aracılığıyla Android 10 ve üzeri (Android Q olarak da bilinir) çalıştıran cihaz yönetici tarafından yönetilen Android cihazları için destek sağlayabilecektir. Bu tarih, Android 'in bir sonraki ana sürümünün yayımlanması beklendiğinde oluşur.  
- , R 2020 sonrasında Android 10 veya sonraki sürümleri çalıştıran Cihaz Yöneticisi tarafından yönetilen cihazlar artık tamamen yönetilemez.    
- Android 10 ' un altında kalan Android sürümlerinde kalan Cihaz Yöneticisi ile yönetilen Android cihazları etkilenmeyecektir ve cihaz yöneticisiyle tamamen yönetilmeye devam edebilir.  
- Tüm Android 10 ve üzeri cihazlarda, Google, Şirket Portalı gibi cihaz yönetici yönetim aracılarının cihaz tanımlayıcı bilgilerine erişmesine olanak tanır. Bu, bir cihaz Android 10 veya üzeri güncelleştirmeler güncelleştirildikten sonra aşağıdaki Intune özelliklerini etkiler: 
    - VPN için ağ erişim denetimi artık çalışmayacak.  
    - Cihazları ıMEı veya seri numarası ile şirkete ait olarak tanımlamak, cihazları şirkete ait olarak otomatik olarak işaretlemez. 
    - IMEı ve seri numarası artık Intune 'da BT yöneticileri için görünür olmayacaktır. 
        > [!Note]
        > Bu, yalnızca Android 10 ve üzeri cihazlarda cihaz yöneticisi tarafından yönetilen cihazları etkiler ve Android Enterprise olarak yönetilmekte olan cihazları etkilemez. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Yaz 2020 ' de gelen işlevselliğin azalmasına engel olmak için şunları öneririz:
- Cihaz Yöneticisi yönetimine yeni cihaz eklemeyin.
- Bir cihazın Android 10 güncelleştirmesi alması bekleniyorsa, cihazı Cihaz Yöneticisi yönetiminden Android kurumsal yönetim ve/veya uygulama koruma Ilkelerine geçirin.

#### <a name="additional-information"></a>Ek bilgiler
- [Google 'ın cihaz yöneticisinden Android kuruluşa geçiş kılavuzu](http://static.googleusercontent.com/media/android.com/en/enterprise/static/2016/pdfs/enterprise/Android-Enterprise-Migration-Bluebook_2019.pdf)
- [Google 'ın Cihaz Yöneticisi API 'sini kullanımdan kaldırma planına yönelik belgeleri](https://developers.google.com/android/work/device-admin-deprecation)

### <a name="update-your-android-company-portal-app-to-the-latest-version---4536963--"></a>Android Şirket Portalı uygulamanızı en son sürüme güncelleştirme <!--4536963-->
Intune, güncelleştirmeleri düzenli aralıklarla Android Şirket Portalı uygulamasına yayınlar. Kasım 2018 ' de, Google 'ın mevcut bildirim platformundan Google 'ın Firebase bulut mesajlaşmasına (FCM) değişikliğini hazırlamaya yönelik bir arka uç anahtarı içeren bir şirket portalı güncelleştirmesi yayımladık. Google Play Store ile iletişim kurmaya devam etmek için, son kullanıcıların kendi şirket portalı uygulamalarını en az Kasım 2018 sürümüne güncelleştirmiş olması gerekir.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Telemetrimiz, 5.0.4269.0 ' den önceki Şirket Portalı sürüme sahip cihazlarınız olduğunu gösterir. Şirket portalı uygulamasının bu sürümü veya üzeri yüklü değilse, BT uzmanı Temizleme, parola sıfırlama, kullanılabilir ve gerekli uygulama yüklemeleri ve sertifika kaydı beklendiği gibi çalışmayabilir. Cihazlarınız Intune 'A kaydedildiyse, Şirket portalı sürümlerini ve kullanıcılarını Istemci uygulamalar – bulunan uygulamalar ' a giderek görebilirsiniz. Şirket Portalı önceki sürümlerinin seçilmesi, son kullanıcıların şirket portalını güncelleştirilmemiş cihazlara sahip olduğunu görmenizi sağlar.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Google Play aracılığıyla şirket portalı 'nı güncelleştirmek üzere güncelleştirilmemiş son Android cihaz kullanıcılarına sorun. Bir kullanıcının şirket portalı uygulamasının otomatik olarak güncelleştirilmesini tutmamaları durumunda yardım masasına bildirin. Google 'ın FCM platformu ve değişikliği hakkında daha fazla bilgi için bağlantıya bakın.

#### <a name="additional-information"></a>Ek bilgiler
https://firebase.google.com/docs/cloud-messaging/


### <a name="new-fullscreen-experience-coming-to-intune---4593669--"></a>Intune 'a gelen yeni tam ekran deneyimi <!--4593669-->
Azure portal Intune 'a güncelleştirilmiş Kullanıcı arabirimi deneyimlerini oluşturma ve düzenleme hakkında bilgi alırız. Bu yeni deneyim, bir dikey pencerede sıkıştırılmış bir sihirbaz stili biçimi kullanarak mevcut iş akışlarını basitleştirir. Bu güncelleştirme "dikey pencere genişlemesine" ya da derin dikey pencerenin ayrıntılarına gidebilmeniz için akış oluştur ve Düzenle akışları ile çalışır. İş akışları oluşturma, atamaları içerecek şekilde da güncelleştirilecektir (uygulama ataması hariç).

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Tam ekran deneyimi, portal.azure.com ve devicemanagement.microsoft.com ' de bir sonraki birkaç aya göre Intune 'a alınacaktır. Kullanıcı arabirimine yönelik bu güncelleştirme, var olan ilkelerinizin ve profillerinizin işlevlerini etkilemez, ancak biraz değiştirilen bir iş akışı görürsünüz. Örneğin, yeni ilkeler oluşturduğunuzda, ilkeyi oluşturduktan sonra bunu yapmak yerine, bu akışın bir parçası olarak bazı atamalar ayarlayabileceksiniz. Yeni deneyimin konsolda nasıl görüneceğine ilişkin ekran görüntüleri hakkında ek bilgi için blog gönderisine bakın.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapabilirim?
Herhangi bir eylemde bulunmanıza gerek yoktur, ancak gerekirse BT uzmanı kılavuzunuzu güncellemeyi göz önüne alabilirsiniz. Bu deneyim Azure portal Intune 'daki çeşitli dikey pencerelere yaptığı için belgelerimizi güncelleştireceğiz.

#### <a name="additional-information"></a>Ek bilgiler 
https://aka.ms/intune_fullscreen

### <a name="plan-for-change-new-windows-updates-settings-in-intune----4464404---"></a>Değişiklik planı: Intune 'da yeni Windows güncelleştirmeleri ayarları <!-- 4464404 -->
Intune hizmetine veya 1908 Ağustos sürümünden başlayarak, "kullanıcının yeniden başlatılmasına Izin ver (serbest yeniden başlatma)" ayarlarını yerine yapılandırabileceğiniz yeni "son tarih ayarları" na ekleniyoruz. 1909 veya Eylül güncelinizdeki Kullanıcı arabirimindeki etkin yeniden başlatma ayarlarını devre dışı bırakmayı planlıyoruz ve ardından bunları Ekim sonuna doğru konsolundan tamamen kaldırdık. 

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Windows 10 cihazlarını ortamınızda yönetiyorsanız: 
- Intune güncelleştirmesi veya 1908 ile, yeni son tarih ayarlarını, eski denetimli yeniden başlatma ayarlarına ek olarak konsolunda görürsünüz.
- Bu eski ve yeni ayarların her ikisi de yapılandırıldığında, son tarih ayarı değerleri, bağlı yeniden başlatma ayarı değerlerini geçersiz kılar.
- Son tarih ayarları, 1910 güncelleştirmesinin konsolunda bulunan "kullanıcının yeniden başlatılmasına Izin ver (yeniden başlatma) seçeneği yerine geçecek.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapabilirim?
İstenen değerlerle yapılandırarak 1908 içindeki son tarih ayarlarını kullanmaya başlayın. Bunu yaptıktan sonra, bu ayarların Ekim 'deki konsolundan kaldırılmasına hazırlanmak için, bağlı yeniden başlatma ayarını "Yapılandırılmadı" olarak ayarlayabilirsiniz.

Belgelerinizi ve gerekirse otomasyon komut dosyalarını güncelleştirin. 

Çalışmaya devam eden yeniden başlatma ayarlarını kaldırmadan önce, Ileti merkezine güncelleştirdiğimiz ve bir anımsatıcı göndereceğiz.

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
Uygulamalarınızı en son Intune uygulama SDK 'Sı ile sarın. Ayrıca, kişisel cihazlardaki son kullanıcıları yükseltmeye bildirmek için "En düşük işletim sistemi sürümünü gerektir (yalnızca uyarı)" koşullu başlatma ayarını da ayarlayabilirsiniz.


### <a name="intune-plan-for-change-nearing-end-of-support-for-windows-7----3042987---"></a>Intune değişiklik planı: Windows 7 için destek sonuna yaklaşıyor <!-- 3042987 -->
MC148476 tarihinde son Eylül 2018 ' de ve yeniden MC176794 ' de 2019 ' de, Windows 7, 14 Ocak 2020 tarihinde Genişletilmiş desteğin sonuna ulaştığında. Bu sırada, Intune, Windows 7 çalıştıran cihazların desteğini devre dışı bırakacaktır, böylece yeni teknolojileri desteklemeye ve harika yeni son kullanıcı deneyimleri sağlamaya yönelik yatırımımızı odaklamaya devam edebilir. Bu tarihten sonra, Windows 7 BILGISAYARıNıZı korumaya yardımcı olan teknik yardım ve otomatik güncelleştirmeler artık Intune aracılığıyla kullanılamayacak. Microsoft, artık kullanılamayan hizmet veya desteğe ihtiyacınız olan bir senaryoya engel olmak için 2020 Ocak 'tan önce Windows 10 ' a geçmeniz önerilir. [Burada](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)Windows destek yaşam döngüsü hakkında daha fazla bilgi edinin.

#### <a name="how-does-this-affect-me"></a>Bu değişiklik beni nasıl etkileyecek?
Bu iletiyi şu anda Windows 7 PC 'yi eski Intune PC yazılım Aracısı 'nı kullanarak yönettiğiniz için alıyorsunuz. Windows 7 genişletilmiş destek 'in sonundan önceki bir yıldan daha az bir süre ile, kuruluşunuzun Windows 10 ' a en kısa sürede yükseltilmesini kesinlikle öneririz. BILGISAYAR yönetimi özellikleri doğrudan Windows 10 işletim sisteminde yerleşiktir ve artık Windows 7 için Intune yazılım Istemcisi gibi bir istemci aracısını yüklemeniz gerekmez. Microsoft, Windows 8.1 başlayarak Windows bilgisayarlarını sağlamak, yapılandırmak, güncelleştirmek ve yönetmek için mobil cihaz yönetimi (MDM) mimarisini kullanır. Intune 'u ayarladıktan sonra, Windows 10 bilgisayarlarını MDM kanalı aracılığıyla [Intune 'a](..\windows-enroll.md) kaydederek Windows kaydını kolaylaştırabilirsiniz. Windows 10 PC 'nizi yönetmek için bu "aracısız" MDM yönetimi çözümünü kullanmanızı öneririz.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Bu değişikliğe hazırlanmak için ne yapmam gerek?
Kuruluşunuzun bu eylem planını anında kabul etmeyi öneririz:

- 14 Ocak 2020 tarihinden önce Windows 7 ' yi planlayın ve Windows 10 ' a yükseltin.
- Mevcut Windows 7 PC 'nizin Windows 10 ' a nasıl yükseltileceğiyle ilgili daha fazla bilgi edinmek için [Windows 10 dağıtım desteğini](https://docs.microsoft.com/windows/deployment/) araştırın.
- [Masaüstü uygulamasını](https://www.microsoft.com/fasttrack/microsoft-365/desktop-app-assure?rtc=1) gözden geçirin Microsoft 'un uygulama uyumluluğu taahhüdüne yardımcı olacak hızlı bir izleme aracılığıyla teklif sunun.
- Mevcut eski Intune yazılım Istemcisi tarafından yönetilen cihazları, MDM yönetimi kullanarak Windows 10 yönetmek için önerilen Microsoft çözümüne geçirin. Tüm yeni Windows 10 bilgisayarlarını, Azure portal Intune için MDM yönetimini kullanarak kaydedin.
- Daha fazla bilgi için [buraya gönderilen bloga](https://aka.ms/Windows7_Intune) bakın.
