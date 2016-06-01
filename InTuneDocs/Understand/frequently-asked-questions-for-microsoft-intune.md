---
# required metadata

title: Sık sorulan sorular | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a8126cca-9ec4-454b-a20b-dc1bb6797327

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Intune hakkında sık sorulan sorular
Bu makalede Intune hakkında sık sorulan bazı sorular yanıtlanmaktadır. Sorunuzun yanıtını burada görmüyorsanız, [bize bildirin](https://microsoftintune.uservoice.com/)

## Genel sorunlar

-   **Itune hizmetinin ne zaman güncelleştirildiğini nasıl öğrenebilirim?**

    manage.microsoft.com adresinden hesabınızda oturum açın. Yönetime Genel Bakış bölümünde **Hizmet Durumunu Görüntüle**’yi seçin. Kiracınızın konumu ve bakım zamanlaması burada listelenir. [Yenilikler](/intune/deploy-use/whats-new-in-microsoft-intune) makalesinde hizmet güncelleştirmeleri hakkında bilgi edinin.

-   **Bir kullanıcı, Şirket Portalı uygulamasında bir cihazı yeniden adlandırdığında cihazın adı Intune’da veya Configuration Manager’da da değişir mi?**

    Hayır, bu ad değişikliği yalnızca kullanıcıya kolaylık sağlamaya yöneliktir.

-   **Intune’da mobil cihazlar için uzaktan yardım işlevi var mı?**

    Hayır. [Bomgar](http://www.bomgar.com/) ve [TeamViewer](https://www.teamviewer.com/) gibi üçüncü taraf uygulamalar yararlı olabilir.

## Hesaplar

-   **Intune’u değerlendirmeye başlayıp deneme için yeni bir kiracı oluşturursam, aynı kiracıyı kullanarak Office 365’i de değerlendirmeye ekleyebilir miyim?**

    Evet. Mevcut Intune kiracınızda veya aboneliğinizde genel yönetici olarak oturum açmanız yeterlidir. Örneğin, *globaladmin@&lt;şirket&gt;.onmicrosoft.com*.

-   **Deneme aboneliği sırasında Intune’a MDM yetkisi atarsam, Intune ile ilgili fikrimi değiştirdiğimde bu durum başka bir şirketin hizmetine geçiş yapmamı zorlaştırır mı?**

    Intune’u kullanmaya devam edeceğinizi umuyoruz; ancak devam etmemeniz durumunda MDM yetkilisi seçiminiz, başka bir hizmete geçmenizi engellemez. Bu durum, Intune’u veya Intune ile System Center Configuration Manager’ı seçmenizle ilgilidir.

-   **Mevcut Office 365 etki alanımın adını sonraki Intune hesabım için kullanabilir miyim?**

    Evet, mevcut Office 365 kiracınızla ilişkili kuruluş kimliğiyle oturum açarsanız ve Intune denemenizi oluştururken veya lisanslarınızı etkinleştirirken etki alanını doğruladıysanız.

    Bu durumda Intune, Office 365 hesabınızda kullandığınız etki alanı, kullanıcı vb. bilgilerini kullanır. Her Office 365 kullanıcısının, bir Intune lisansı aracılığıyla Intune kullanıcısı olarak etkinleştirilmesi gerektiğini unutmayın. Bu işlemin, kiracıyı yöneten genel yönetici tarafından yapılması gerekir.

## Kayıt

-   **Kullanıcılarım cihazlarını kaydetmeyi nereden öğrenebilir?**

    [BT yöneticileri için son kullanıcı Itune kayıt yönergeleri](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a)’nde yer alan bilgileri kullanabilir veya bu bilgileri özelleştirebilirsiniz.

-   **Cihaz kaydıyla ilgili sorunları nasıl giderebilirim?**

    Genel kayıt sorunlarını gidermenin yolları [Intune'da cihaz kaydıyla ilgili sorunları giderme](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune) içinde verilmiştir

-   **Kullanıcı kayıtla ilgili bir sorunla karşılaştığında kayıt günlüklerini nasıl toplayabilirim?**

    [Bu yönergeleri](http://www.microsoft.com/en-us/download/46391)izleyin

## Mobil aygıt yönetimi

-   **Genel MDM**

    -   **Intune, bir cihazın yazılım kilidinin kaldırılıp kaldırılmadığını algılayabilir mi?**

        Evet, bazı işletim sistemlerinde algılayabilir. Kısıtlamaları kaldırılmış cihazları yönetme hakkında bilgi için, bkz. [Cihaz uyumluluk ilkesi oluşturma](/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune.md)

    -   **Bir cihazdaki kurumsal verileri seçmeli olarak silebilir miyim?**

        Evet. Seçmeli temizleme hakkında bilgi için bkz. [Uzaktan silme, uzak kilitleme veya parola sıfırlama ile verilerinizi koruma](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune.md)

    -   **Mobil cihaz tarayıcısında Intune aracılığıyla belirli web siteleri engellenebilir mi?**

        Platformların yerel tarayıcılarında bu işlem yapılamaz. Ancak, iOS ve Android cihazlarda Intune tarafından yönetilen web tarayıcısını dağıttığınızda URL’lere izin verebilir veya URL’leri engelleyebilirsiniz. Daha fazla bilgi için bkz. [Yönetilen tarayıcı ilkelerini kullanarak internet erişimini yönetme](/intune/Deploy-Use/Manage-Internet-access-using-managed-browser-policies-with-Microsoft-Intune.md)

    -   **Kullanıcının bir uygulamayı kaldırmasını kısıtlayabilir miyiz?**

        Genellikle kısıtlayamazsınız. Ancak, denetlenen bir iOS cihazında, kullanıcının Apple Configurator ile dağıtılan bir uygulamayı kaldırmasını önleyebilirsiniz. 

    -   **Mobil veri kullanımı yönetilebilir mi?**

        Doğrudan olmasa da, [Kullanıcıların Wi-Fi profilleri kullanarak şirket ağına bağlanmasına yardımcı olma](/intune/Deploy-Use/wi-fi-connections-in-microsoft-intune.md) içinde açıklandığı şekilde Wi-Fi profillerini cihazlara göndererek, Wi-Fi seçeneğinin bağlantı için tercih edilen yöntem olmasını sağlayabilirsiniz. Ayrıca iOS ve Android KNOX gibi bazı platformlar, ses ve veri dolaşımı ayarlarını denetlemenize olanak tanır.

    -   **Kullanıcının bir cihazı kaydetmesi engellenebilir mi? Cihaz şirkete aitse ne olur?**

        Genellikle yapamazsınız. Ancak, özel Windows Phone ayarlarını kullanarak Windows Phone 8.1’de kullanıcı kaydını engelleyebilirsiniz. Ayrıca, denetlenen ve Apple’ın Aygıt Kayıt Programı’na (DEP) kayıtlı olan iOS cihazlarında, kullanıcının cihaz kaydını kaldırması engellenebilir.

    -   **Seçili MDM yetkilimi değiştirebilir miyim?**

        Bazı durumlarda MDM yetkilisini değiştirebilirsiniz. Bunu yapmak için [Microsoft Intune için destek alma](/intune/Troubleshoot/How-to-get-support-for-Microsoft-Intune.md) içinde açıklandığı gibi Destek ile iletişim kurun. Yapılabilecek değişiklikler aşağıdaki tabloda açıklanmıştır. MDM yetkilisindeki değişikler, cihazların yeniden kaydedilmesini gerektirir.

        **Kime:** Intune!**Kime:** O365|**Kime:** Intune ile Configuration Manager |
        
        **Kimden:** Intune| |Evet&#42;|Evet|



-   ****Kimden:** O365| |Evet&#42;|Evet|**

    -   ****Kimden:** Intune ile Configuration Manager |Evet|Evet| |**

        #42;O365 ve Intune MDM yetkilileri birlikte kullanılabilir,;böylece mobil cihazları yeniden kaydetmeniz gerekmez. Windows Bir Windows Mağazası uygulamasını dışarıdan yükleyebilir miyim?

    -   **Genel kullanıma açık uygulamalar dışarıdan yüklenemez.**

        XAP’yi indirebilirsiniz. Ancak, geliştiricinin kod imzalama sertifikasıyla şifrelenip imzalanmış genel bir XAP olduğundan bunu Intune’a yükleyemezsiniz. Yalnızca kendi geliştirdiğiniz ve kendi kod imzalama sertifikanızla imzaladığınız uygulamalar dışarıdan yüklenebilir.

    -   **Şirket Portalı aracılığıyla dağıtılan Windows Phone Mağazası uygulamaları için son kullanıcının bir Microsoft Hesabına sahip olması gerekir mi?**

        Evet. Son kullanıcı, Microsoft Hesabı olmadan uygulama edinemez. Bu durumun tek istisnası, dışarıdan yüklenen ve cihazlara Microsoft Hesabı olmadan dağıtılabilen özel LOB uygulamalarıdır.

        **Windows Phone 8.1 cihazının Intune ile yönetilebilmesi için bu cihazda bir Microsoft Hesabı olması gerekir mi?**
        Hayır. Ancak, ortak depodaki çoğu uygulamanın yüklenebilmesi için Microsoft Hesabı gereklidir. Windows Phone, yönetim için neden Symantec sertifikası gerektiriyor? Windows Phone, uygulamaları nasıl yükleyebileceğinizi denetler. Microsoft hesabı olan kullanıcılar, Windows Phone mağazasından uygulama yükleyebilir veya şirketler dahili olarak geliştirilmiş iş kolu (LOB) uygulamalarını normal yolla veya Windows Phone belgelerinde açıklanan özel bir işlemi kullanarak dışarıdan yükleyebilir.

        İş kolu uygulamaları yüklenirken Windows Phone’lar yalnızca Symantec tarafından verilen özel türde bir sertifikaya güvenir. Ticari veya özel olarak oluşturulan diğer sertifikaları kullanamazsınız. Bu gereksinim, yalnızca Intune için değil tüm mobil cihaz yönetimi çözümleri için geçerlidir. Symantec sertifikası, bir uygulama kayıt belirteci (AET) oluşturur. AET, bir cihaz mobil cihaz yönetimi için kaydolurken cihaza yüklenebilir veya güvenli bir web sitesi ya da bir e-posta ekinden bant dışı olarak yüklenebilir. Yöneticilerin [Windows Phone SDK'sinde](http://go.microsoft.com/fwlink/?LinkId=268439)sağlanan araçları kullanarak tüm LOB uygulamalarını Symantec sertifikası ile imzalaması gerekir. Kullanıcılar LOB uygulamalarını yüklemeye çalıştığında, Windows Phone işletim sistemi AET'deki imzayı uygulamadaki imzayla karşılaştırarak denetler.

        -   İmzalar eşleşirse, yüklemenin devam etmesine izin verilir.

        -   AET doğrulanamazsa, yükleme başarısız olur.

        -   AET'nin doğrulanamamasının birkaç nedeni vardır:

        AET cihaza hiç yüklenmemiştir

    **AET'nin süresi dolmuştur**
  AET, uygulamayı imzalamak için kullanılan Symantec sertifikasının aynısıyla oluşturulmamıştır Windows Phone, MDM kaydı sırasında AET'nin mevcut olmasını gerektirmez; ancak, Kasım 2014 sürümünden önce Intune AET ve imzalı bir ssp.xap dosyasını gerektiriyordu çünkü AET ve ssp.xap dosyasını kayıt süreci dışında yüklemenin bir yolu yoktu.

      > AET, Intune kullanıcıları için nasıl oluşturulur?

    **Yöneticiler Symantec sertifikaları için .pfx dosyasını karşıya yüklediğinde, Intune AET'yi otomatik olarak oluşturur ve kaydedilen Windows Phone'lara dağıtır.**
       Intune yöneticilerinin Windows Phone SDK'sindeki AET Oluşturucusu aracını kullanması gerekli değildir.

       -   Intune, el ile AET oluşturma ve bant dışı dağıtmayı desteklemez. Bir Symantec sertifikası gereksinimini azaltmak için ne değişiklikler oldu?

        -   Kasım 2014 sürümü için Intune, şirketlerin Symantec sertifikasına gerek duymayacağı senaryolara için izin vermek için değişiklikler yaptı. Windows Phone 8.1 için Şirket Portalı mağazadan yüklenebileceğinden, Symantec sertifikasıyla imzalanması ve bir AET ile karşılaştırılarak doğrulanması gerekmez. Bunun yerine, uygulama, mağaza yayımlama işlemleri kapsamında doğrulanır.

        Windows Phone 8.1 cihazları, telefonda AET olsa da olmasa da kaydedilebilir. AET varsa, cihaz Intune ile ilk eşitlendiğinde yüklenir.

        **AET yoksa, cihaz yine de Intune tarafından yönetilebilir ve kullanıcılar şirket portalını mağazadan yükleyip özelliklerin çoğunu, uygulamaları imzalamak için bir Symantec sertifikası olmadan kullanabilir.**
        Windows Phone 8 cihazları için Symantec gereksiniminde herhangi bir değişiklik yoktur.

        -   Windows Phone 8 cihazlarında kayıt sırasında imzalı ssp.xap ve AET var olmalıdır, aksi takdirde kaydolmaları engellenir.

        -   Bir Windows Phone 8.1 cihazı kaydedildiği halde Symantec sertifikası yoksa, hangi işlevsellikler desteklenir?

        -   Bir Windows Phone 8.1 cihazı kaydedildiği halde Symantec sertifikası yoksa, şunları yapabilirsiniz:

        -   İlke oluşturma ve bunları cihaza gönderme

        -   BT bölümü için Şirket Portalı'nda görünecek kişi bilgileri yapılandırma

        Mağazaya ayrıntılı bağlantılar oluşturma ve bunları Şirket Portalı'na dağıtma

        > [!IMPORTANT]
        > Web sayfalarına bağlantılar oluşturma ve bunları Şirket Portalı'na dağıtma Şirket Portalı kullanılmadan önce kullanıcılar tarafından kabul edilmesi gereken hüküm ve koşullar oluşturma

        **Symantec sertifikası olmadan yapamayacağınız tek şey, LOB uygulamaları dağıtmaktır.**
        Intune Software Publisher, uygulamaları karşıya yüklerken uygulamaların imzalı olduğunu doğrulamaz. İmzasız uygulamalar dağıtırsanız, kullanıcılar bunları yüklemeye çalıştığında başarısız olur. Kullanıcılar Şirket Portalı'na sahip oldukları halde Symantec sertifikası yoksa kullanıcılar ne yapabilir?

        Windows Phone 8.1 cihazlarında, kullanıcılar Şirket Portalı'nı mağazadan yüklemeden önce cihazın kaydedilmesi gerekmez.

        -   Cihaz kayıtlı değilse kullanıcıların cihazı kaydetmesi istenir. Şirket Portalı'nda isteme dokunmak, kullanıcıları doğrudan cihazlarını kaydedebilecekleri **Ayarlar / Çalışma Alanı**'na götürür.

        -   Cihaz kaydedilmediğinde bile kullanıcılar mağazadan yükledikleri Şirket Portalı ile aşağıdaki eylemleri gerçekleştirebilir:

        -   Yönetici tarafından yapılandırılan hüküm ve koşulları kabul etme veya reddetme.

        -   Kullanıcılar hüküm ve koşulları kabul etmezse Şirket Portalı kapanır.

        -   BT departmanı için kişi bilgilerini görüntüleme

        iOS, Android ve Windows cihazları dahil olmak üzere kayıtlı tüm cihazları görüntüleme Mağazada uygulamaların ayrıntılı bağlantılarını kullanma Web sayfalarını açmak için web bağlantıları kullanma Cihaz kayıtlıysa, kullanıcılar **Cihazlarım** listesinde cihazı görüntüleyebilir.

        Kaydedildikten sonra cihaz dağıtılan tüm Intune ilkelerine tabi olur.

        **Cihazların AET'yi alması ve LOB uygulamalarını yüklemesi için kayıtlı olması gerekir. Bir LOB uygulaması yüklemeye çalışan kayıtsız cihazlar, kaydolmaya yönlendirilir.**
        Şirketin Symantec sertifikası yoksa kullanıcıların yapamayacağı tek şey, yönetici tarafından dağıtılan LOB uygulamalarını yükleyememektir. Şirketimizin zaten bir sertifikası var ve Windows Phone 8.1 cihazlarını kaydediyoruz.

        **Şirket Portalı artık mağazada kullanılabilir hale geldiğinden, farklı bir şey yapmama gerek var mı?**
        İndirme Merkezi'nden edinilen geçerli ssp.xap, Windows Phone 8.1 cihazlarda hala çalışmaktadır.

        -   Kullanıcıları kaydolmaya ve şirket portalını yükleme sırasında edinmeye yönlendirmeye devam edebilirsiniz.

        -   Kullanıcıların Şirket Portalı'nı mağazadan almasının artıları ve eksileri nelerdir?

        -   Artılar:

        -   Windows Phone 8.1 cihazı kayıtlı olmasa bile kullanıcılar ayrıntılı bağlantılara ve web bağlantılarına sahip olur.

        Şirket Portalı Microsoft tarafından güncelleştirildiğinde, mağaza uygulaması, sizin ssp.xap'ı indirmenize, imzalamanıza ve yüklemenize gerek kalmadan, otomatik olarak güncelleştirilir.

        -   Windows Phone 8.1, iOS, Android ve Windows kullanıcıları için belgeler tutarlıdır: "Mağazaya gidin ve Şirket Portalı'nı yükleyin."

        -   Kullanıcılar, uygulamanın yüklendiğini görür ve uygulama açıldığında kayıt yönergeleri alır

        Eksileri:

        -   Kullanıcılar, bir "**şirket hub'ı**" yüklemek için bir onay kutusu görür ancak hiçbir şey kullanıcıları cihazın uygulama listedeki Şirket Portalı'na yönlendirmez

        -   Kullanıcılar, Şirket Portalı'nı açana kadar özel hüküm ve koşulları kabul etmek zorunda değildir

        -   Aşağıdaki durumlarda, kullanıcıları kaydolmaya ve ssp.xap'ı kayıt sırasında yüklemeye yönlendirmeye devam edebilirsiniz:

        **Şirket, Windows Phone'lardan mağazaya erişimi engelliyorsa, kullanıcılar ssp.xap'ı kayıt sırasında yüklemelidir.**

        -   Kullanıcıların Windows Phone'larında yapılandırılmış Microsoft hesapları yoksa, Şirket Portalı'nı mağazadan yükleyemezler.

        -   Windows Phone kaydına yönelik var olan belgeler kullanıcılara önce Ayarlar, Çalışma Alanı'na gitmesini söylüyorsa, belgelerin güncelleştirilmesi ve kullanıcıların mağazaya yönlendirilmesi biraz zaman alabilir.

        -   İndirme Merkezi'ndeki ssp.xap ile mağazadaki uygulama arasındaki fark nedir?

        **Mağazadaki Şirket Portalı'nın yüklenmesi için Symantec sertifikası tarafından imzalanması gerekmez.**
        Mağazadaki Şirket Portalı, kullanıcıya hüküm ve koşulları sunar ancak İndirme Merkezi'ndeki ssp.xap sunmaz Mağazadaki Şirket Portalı, bir .xap yerine bir .appx dosyasıdır

        -   Kullanıcılarımı mağazaya göndermek yerine, Şirket Portalı dosyasını alıp kullanıcılarıma gönderebilir miyim?

        -   Evet.

        -   Şirket Portalı uygulaması, aşağıdaki işletim sistemleri için İndirme Merkezi'nden indirilebilir:

        **Windows Phone 8.1: [http://go.microsoft.com/fwlink/?LinkId=615799](http://go.microsoft.com/fwlink/?LinkId=615799)**
        Windows Phone 8.0 : [http://go.microsoft.com/fwlink/?LinkId=268440](http://go.microsoft.com/fwlink/?LinkId=268440) Windows 8.1: [http://go.microsoft.com/fwlink/?LinkId=615800](http://go.microsoft.com/fwlink/?LinkId=615800) Şirketlerin Symantec sertifikası yoksa ve kullanıcılarının mağazadan Şirket Portalı'nı yüklemesini sağlıyorsa, şirketler yine de Windows Intune Windows Phone Deneme Yönetimi için Destek Aracı'nı kullanabilir mi?

        Evet.

        > [!IMPORTANT]
        > LOB uygulamalarının yüklenmesini içeren bir kavram kanıtı gerçekleştirmeniz gerekiyorsa, deneme yönetim aracı, şirket portalının mağaza sürümüyle uyumludur. Ancak, Symantec'ten edinilen AET, Windows Phone 8.1 cihazlarını kaydetmek için artık gerekli olmadığından, şirketler mağazalardaki ayrıntılı uygulama bağlantılarını kullanarak uygulama yüklemesini sınayabilir.

        **Windows Intune Windows Phone Deneme Yönetimi için Destek Aracı, yalnızca Intune deneme abonelikleri içindir.**
        Yalnızca deneme yönetimi araç testini kullanın. Deneme yönetim aracı için Symantec sertifikası artık kullanılamıyorsa veya şirket, uygulamaları imzalamak için kendi Symantec sertifikasını edinirse, deneme yönetim aracından AET ile kaydedilen cihazların kaydının silinmesi ve yeniden kaydedilmesi gerekir. Şirketler, herhangi bir Symantec sertifikası olmadan başlayıp daha sonra, hatta Windows Phone 8.1 cihazları kaydedildikten sonra, bir sertifika ekleyebilir mi? Evet. Windows Phone 8.1 cihazları zaten kayıtlı olsa bile, Symantec sertifikası alabilir, ssp.xap'ı imzalayabilir ve pfx dosyası ile birlikte karşıya yükleyebilirsiniz.


-   **Intune daha sonra AET'yi oluşturur.**

    -   **Windows Phone 8.1 cihazları, bir sonraki eşitleme işlemi sırasında, sekiz saat içinde AET'yi alır.**

        xap ve pfx dosyalarını karşıya yükledikten sonra, iş kolu uygulamalarını dağıtmadan önce en az sekiz saat bekleyin.

-   **Android**

    -   **Bir Android cihazını şifrelemek ne kadar sürer?**

        Bu süre, öncelikle cihazın işlemci hızına, toplam bellek miktarına ve kullanılan bellek miktarına bağlıdır. Ancak bu bir Intune işlevi değildir. iOS

    -   **iOS uygulamalarını Intune ile dağıtırken, uygulamanın IPA’sı ve Bildirim dosyası karşıya yüklendiğinde, cihazın yükleme işlemine devam etmesi için bir Apple Kimliği belirtilmesini istenir mi?**

        Hayır. Intune bir bölümünü sağlarken (IPA Intune’a yüklenir), uygulamalar dışarıdan yüklenir ve Apple Kimliği gerektirmez.

    -   **iOS’ta App Store’a erişim izni vermeden uygulama yüklemeyi etkinleştirmenin bir yolu var mı?**

        Hayır. Ancak App Store’u etkinleştirebilir ve iOS’ta izin verilen ve engellenen uygulamaları kullanarak kullanıcıların gerçekleştirdiği işlemleri izleyebilirsiniz.

    -   **Dışarıdan yüklenen LOB uygulamaları için Apple App Store erişimi gerekmez.**

        Şirket Portalı aracılığıyla dağıtılan Apple Store uygulamaları için son kullanıcının bir iTunes hesabına sahip olması gerekir mi? Evet. Son kullanıcı, iTunes hesabı olmadan uygulamaları edinemez.

## App Store’u engelleyebilir miyim?

-   **Evet, engelleyebilirsiniz. Ancak, bu yalnızca son kullanıcı tarafından başlatılan işlemleri değil, App Store aracılığıyla yapılan tüm uygulama yüklemelerini ve güncelleştirmelerini engeller.**

    Bu, Intune’dan dağıttığınız genel kullanıma açık tüm App Store uygulamalarının da başarısız olacağı anlamına gelir.

-   **Uygulama dağıtımı**

    Önerilen uygulama eklemek için ne yapmam gerekir? Intune’da bunlar "öne çıkan uygulamalar" olarak adlandırılır ve [Microsoft Intune’da uygulama dağıtma](/Intune/Deploy-Use/deploy-apps-in-microsoft-intune.md) içinde belgelenir.

## Dağıtmak istediğim uygulamalar için fazladan bulut depolama alanı alabilir miyim?

-   **Evet.**

    [Uygulama dağıtma](/Intune/Deploy-Use/deploy-apps.md) kısmındaki *Bulut depolama gereksinimleri* bölümünde bu konu hakkında bilgi edinebilirsiniz Güvenlik Intune, BitLocker’ı zorunlu kılabilir mi?

-   **Windows 8.1/RT’deki OMA-DM aracısı, şifreleme durumunu okumanıza (almanıza) izin verir.**

    Bunu göremezsiniz. Bu durum, Intune ve diğer mobil cihaz yönetim hizmetleri için geçerlidir. Bir Windows 8 tabletini BitLocker kullanarak şifrelediğimde, kullanıcı birden çok kez art arda oturum açamadığı zaman cihazın tamamen silinmesini zorunlu kılabilir miyim?

## Windows 8.1/RT cihazlarında, Intune dahil hiçbir mobil cihaz yönetim hizmetini tamamen silemezsiniz.

-   **Intune, bu cihazlar için seçmeli silme olanağı sağlar.**

    Intune'da temizleme/seçmeli silme hakkında daha fazla bilgi için, bkz. [Microsoft Intune ile uygulamaları ve verileri koruma](/intune/Deploy-Use/protect-apps-and-data-with-microsoft-intune.md) Şirket Portalı

## Şirket portalımı özelleştirebilir miyim?

-   **Evet.**

    Bu ayarlar için Intune yönetim konsolunda **Yönetim&gt;Şirket Portalı** bölüme gidin. Configuration Manager ile Microsoft Intune

-   **Intune ile Configuration Manager’ı kullandığımda, cihazlarımı nereden yönetirim?**

    Intune aracısı yüklü olan cihazlar Intune konsolunda görünse bile, tüm cihazlarınızı Configuration Manager’dan yönetin. Mobil cihazlar Intune konsolunda görünmez.

-   **Cihazlarda seçmeli silme uygulayabilir miyim?**

    Intune ile System Center 2012 R2 Configuration Manager veya sonraki bir sürümünü kullanıyorsanız şirket verilerini kaldıran seçmeli silme işlemini uygulayabilirsiniz. Daha fazla bilgi için, bkz. [Microsoft Intune ile uygulamaları ve verileri koruma](/intune/Deploy-Use/protect-apps-and-data-with-microsoft-intune.md)



<!--HONumber=May16_HO2-->


