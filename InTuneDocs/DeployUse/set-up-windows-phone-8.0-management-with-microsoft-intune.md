---
title: "Windows Phone 8.0 yönetimini ayarlama | Microsoft Intune"
description: "Microsoft Intune ile, Windows Phone 8.0 cihazları için mobil cihaz yönetimini (MDM) etkinleştirin."
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 06/09/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 61e9b6c3-8795-49b0-8ab2-a9a05ee3ea1f
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5f336cf52cbecd93cb7b2850560327e6024302e0
ms.openlocfilehash: 9f0c2493c5e852419b037eacd3bf2ce798fecd0a


---

# Windows Phone 8.0 için cihaz yönetimini ayarlama

Windows Phone 8.0’da, Intune Şirket Portalı uygulamasının yüklenebilmesi ve cihaz yönetimine izin verilmesi için bir Symantec sertifikasının yüklenmesi gerekir. İş kolu uygulamalarını imzalamak için de bir sertifika gereklidir. Aşağıdaki konu yalnızca Windows Phone 8.0’a yöneliktir. Windows Phone 8.1 veya üstünü (Windows 10 Mobile da dahil) yönetmek için bkz. [Windows Phone kaydını ayarlama](set-up-windows-phone-management-with-microsoft-intune.md).

> [!IMPORTANT]
> Eylül 2016’dan başlayarak Windows 8.0 ve Windows Phone 8.0 için Şirket Portalı uygulaması artık indirilemeyecektir.

-   **Windows Phone 8** - Sertifika gerekir
-   **Windows Phone 8.1 ve Windows 10 Mobile**’a yalnızca aşağıdaki durumlarda sertifika gerekir:

    -   Intune kullanarak Şirket Portalı uygulamasını dağıtmak istiyorsunuz

    -   İş kolu (yani "dışarıdan yüklenen") uygulamaları dağıtacaksanız


![Sertifika gereksinimleri diyagramı](../media/wpcertreqs.png)

  > [!IMPORTANT]
  > Belirli Windows ve Windows Phone mobil cihazlarını yönetmek için kullanılan Symantec sertifikasının [düzenli aralıklarla yenilenmesi gerekir](renew-a-symantec-code-signing-certificate.md).

Windows Phone mobil cihaz yönetimi için kurulum gereksinimleri cihazları nasıl yöneteceğinize bağlıdır.  Şirketinizin DNS kaydında iki CNAME ayarlamak kullanıcıların kaydolmasını kolaylaştırır. Kullanıcılarınız Şirket Portalı uygulamasını Mağaza’dan indirecekse, DNS ayarlarını yapılandırdıktan sonra yalnızca Şirket Portalı’nı ayarlayıp kullanıcılara nasıl kaydolacaklarını söylemeniz yeterlidir.  Şirket Portalı’nı dağıtacağınız Windows Phone 8.0 veya Windows Phone 8.1 cihazları için, uygulamanın kodunu imzalamak amacıyla bir Symantec sertifikasına ihtiyacınız vardır.

## Windows Phone yönetimini etkinleştirmek için kurulum gereksinimlerini yapılandırma
1.  **Intune’u ayarlama** Henüz bu işlemi yapmadıysanız mobil cihaz yönetimine hazırlanmak için [mobil cihaz yönetimi yetkilisini](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) **Microsoft Intune** olarak ayarlayın ve MDM’yi ayarlayın.

2.  **Kayıt sunucusu adresi için bir DNS diğer adı ayarlama** (isteğe bağlı)

    Bir DNS diğer adı (CNAME kayıt türü), kayıt sırasında sunucu adını otomatik olarak doldurarak kullanıcıların cihazlarını kaydetmelerini kolaylaştırır.

    1.  [Intune yönetim konsolunda](http://manage.microsoft.com) **Yönetim** &gt; **Mobil Cihaz Yönetimi** &gt; **Windows Phone**’a tıklayın.

    2.  **Doğrulanmış etki alanı adı belirtin** kutusuna şirket web sitesinin doğrulanmış etki alanının URL'sini yazın ve ardından **Otomatik Algılamayı Sına**'ya tıklayın.

    3.  Şirketinizin etki alanı için **CNAME** DNS kaynak kayıtları oluşturun. CNAME kaynak kayıtları, aşağıdaki bilgileri içermelidir:

        |Konak Adı|Şunu gösterir:|TTL|
        |-------------|-------------|-------|
        |enterpriseenrollment.company_domain.com|enterpriseenrollment-s.manage.microsoft.com |1 Saat|
        |enterpriseregistration.company_domain.com|enterpriseregistration.windows.net|1 Saat|
        Örneğin, şirketinizin web sitesi contoso.com ise, DNS’de, EnterpriseEnrollment.contoso.com adresinden manage.microsoft.com adresine yeniden yönlendiren bir CNAME oluşturursunuz. Birden fazla doğrulanan etki alanı varsa, her bir etki alanı için bir CNAME kaydı oluşturun.

        -   `enterpriseenrollment-s.manage.microsoft.com` – E-postanın etki alanı adından etki alanını tanıma ile Intune hizmetine yeniden yönlendirmeyi destekler.

        -   `enterpriseregistration.windows.net` – Mobil cihazlar için çalışma alanına katılımı destekler. Windows 8.1 için koşullu erişimi de destekler

    ![Windows Phone Mobil Cihaz Yönetimi Ayarları iletişim kutusu](../media/windows-phone-enrollment.png)

3.  **Uygulama imzalamayı desteklemek için sertifika yönetimi** [Windows Phone Mağazası’na erişmeyecek ve/veya iş kolu uygulamalarına ihtiyacı olan Windows Phone 8.0 ve Windows Phone 8.1 için gereklidir.]

    Windows Phone 8.0 için Şirket Portalı uygulamasını desteklemek ve şirket uygulamalarını Windows Phone 8.1'e dağıtmak için bir **Symantec Kurumsal Mobil Kod İmzalama Sertifikası**almanız gerekir. Windows Phone cihazları tarafından yalnızca Symantec sertifikasına güvenildiğinden, kendi sertifika yetkiliniz tarafından verilen bir sertifikayı kullanamazsınız. Aşağıdakileri yapmak için bu sertifika gereklidir:

    -   Kayıt ve telefon yönetimi amacıyla [!INCLUDE[winphone8_client_1](../includes/winphone8_client_1_md.md)] üzerinde dağıtım için Şirket Portalı uygulamasını imzalama

    -   Şirket iş kolu uygulamalarının [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] tarafından Windows Phone'lara dağıtılabilmesi için şirket iş kolu uygulamalarını imzalama

    Aşağıdaki adımlar, gerekli sertifikaları almanıza ve şirket portalı uygulamasını imzalamanıza yardımcı olur. Bir Windows Phone Geliştirici Merkezi hesabına sahip olmanız ve ardından Symantec sertifikası satın almanız gerekir.

    1.  **Windows Phone Geliştirici Merkezi'ne katılma** Şirket hesabınızı satın almak için oturum açarken kurumsal hesap bilgilerini kullanarak [Windows Phone Geliştirici Merkezi](http://go.microsoft.com/fwlink/?LinkId=268442)'ne katılın. Bu istek, kod imzalama sertifikası sizin tarafınızdan alınmadan önce bir şirket yetkilisi tarafından yetkilendirilmelidir.

    2.  **Şirket Symantec sertifikası alma** Symantec ID'nizi kullanarak [Symantec web sitesinden](http://go.microsoft.com/fwlink/?LinkId=268441) bir sertifika satın alın. Sertifikayı satın aldıktan sonra, Windows Phone Geliştirici Merkezi hesabınızda belirlediğiniz şirket onaylayanı, sertifika isteğinin onaylanmasını isteyen bir e-posta alır. Symantec sertifika gereksinimi hakkında daha fazla bilgi için bkz. [Windows Phone neden Symantec sertifikası gerektiriyor?](https://technet.microsoft.com/en-us/library/dn764959.aspx#BKMK_Symantec) Windows cihaz kaydı SSS.

    3.  **Sertifikaları içeri aktarma** İstek onaylandıktan sonra sertifikaları içeri aktarmaya yönelik yönergeler içeren bir e-posta alacaksınız. Sertifikaları içeri aktarmak için e-postadaki yönergeleri izleyin.

    4.  **Sertifikaların içeri aktarıldığını doğrulama** Sertifikaların doğru bir biçimde içeri aktarıldığını doğrulamak için **Sertifikalar** ek bileşenine gidin, **Sertifikalar**'a sağ tıklayın ve **Sertifika Bul**'u seçin. **İçerir** alanına "Symantec" yazın ve **Şimdi Bul**'a tıklayın. İçeri aktardığınız sertifikaların sonuçlarda görüntülenmesi gerekir.

        ![Symantec sertifikasını bulma](../media/wit.gif)

    5.  **İmzalama sertifikasını dışarı aktarma** Sertifikaların mevcut olduğunu doğruladıktan sonra, şirket portalını imzalamak için .pfx dosyasını dışarı aktarabilirsiniz. **Hedeflenen amaç** "kod imzalama" ifadesinin bulunduğu Symantec sertifikasını seçin. Kod imzalama sertifikasına sağ tıklayıp **Dışarı Aktar**'ı seçin.

        ![İmzalama sertifikasını dışarı aktarma](../media/wit-walk-cert2.gif)

        **Sertifika Dışarı Aktarma Sihirbazı**'nda **Evet, özel anahtarı dışarı aktar** 'ı seçin ve ardından **İleri**'ye tıklayın. **Personal Information Exchange –PKCS #12 (.PFX) seçeneğini belirleyin** ve **Mümkünse sertifika yolundaki tüm sertifikaları dahil et**'i işaretleyin. Sihirbazı tamamlayın. Daha fazla bilgi için bkz. [Özel Anahtara Sahip Bir Sertifikayı Dışarı Aktarma](http://go.microsoft.com/fwlink/?LinkID=203031).

    6.  **Şirket Portalı uygulamasını indirip imzalama**

        Windows Phone kayıt desteği, Windows Phone 8.0 Şirket Portalı uygulamasının imzalanmasını ve Intune’a yüklenmesini gerektirir.

        1.  **Şirket Portalı'nı indirme** İndirme Merkezi'nden [Windows Phone için Intune Şirket Portalı](http://go.microsoft.com/fwlink/?LinkId=268440)'nı indirin. Varsayılan yükleme konumu: `C:\Program Files (x86)\Microsoft Corporation\Windows Intune Company Portal for Windows Phone`.

        2.  **Windows Phone 8.0 SDK’sını indirme** [Windows Phone SDK’sını](http://go.microsoft.com/fwlink/?LinkId=615570) indirin.

        3.  **Şirket Portalı uygulamasının kodunu imzalama** Şirket portalını Symantec sertifikasından oluşturduğunuz .pfx dosyası ile imzalamak için SDK ile indirilen XAPSignTool uygulamasını kullanın. Daha fazla bilgi için bkz. [XapSignTool kullanarak şirket uygulaması imzalama](http://go.microsoft.com/fwlink/?LinkID=280195).

    7.  **Şirket Portalı uygulamasını Intune’a yükleme** İmzalanmış Şirket Portalı uygulama dosyasını ve kod imzalama sertifikanızı karşıya yükleyerek uygulamayı son kullanıcılarınızın kullanımına sunun.

        1.  [Intune yönetim konsolunda](http://manage.microsoft.com) **Yönetim** &gt; **Windows Phone**’a tıklayın.

        2.  **İmzalanmış Uygulama Dosyasını Karşıya Yükle** 'ye tıklayın ve Intune Yönetici Kimliğinizle oturum açın.

        3.  **Yazılım kurulumu** sayfasında, **Yazılım kurulum dosyalarının konumunu belirtin** seçeneği için, kodla imzalanmış Şirket Portalı uygulamasının konumuna (Windows Phone 8.0 için .xap veya Windows Phone 8.1 için .appx) göz atın.

            Intune’u değerlendiriyorsanız ve kodla imzalanmış uygulama dosyasını bir deneme Intune hesabında karşıya yüklüyorsanız, **Örnek Symantec koduyla imzalanmış sertifika tarafından imzalanan Şirket Portalı dosyasını kullan** onay kutusunun işaretini kaldırın.

        4.  **Kod imzalama sertifikası** olarak dışa aktardığınız sertifika (.pfx) dosyasını ekleyin ve sertifika için bir parola oluşturun.

        5.  **Yazılım açıklaması** sayfasında, kullanıcıların kendi cihazlarındaki Şirket Portalı'nda uygulama hakkında ayrıntıları görüntülerken bu bilgileri göreceğini unutmadan alanları doldurun.

        6.  Sihirbazı tamamlayın. Windows Phone 8.0 cihazı kaydeden kullanıcılar artık Şirket Portalı uygulamasını cihazlarına kayıt sırasında alacak. Windows Phone 8.1 kullanıcıları, Şirket Portalı uygulamasını Şirket Portalı'nın mağaza sürümünden yükleyebilir.  Windows Phone 8.1 cihazları, Windows Phone Mağazasında engelleniyorsa veya Şirket Portalı uygulamasını Intune kullanarak dağıtmak istiyorsanız, Windows Phone 8.1 Şirket Portalı (SSP.appx) uygulamasını indirip imzalamanız gerekir.

4.  **Kullanıcılara şirket portalıyla şirket kaynaklarına nasıl erişebileceklerini söyleme** Kullanıcılarınızın cihazlarını nasıl kaydedeceklerini ve cihazları yönetim altına alındıktan sonra neler bekleyebileceklerini bilmeleri gerekir. [Son kullanıcılarınıza Microsoft Intune kullanma hakkında söylemeniz gerekenler](what-to-tell-your-end-users-about-using-microsoft-intune.md)

## Windows Phone 8.1 Şirket Portalı uygulamasını dağıtma
Şirket Portalı uygulamasını Windows Phone 8.1 cihazlara Windows Phone Mağazası’ndan yüklemek yerine Intune ile dağıtabilirsiniz. Yine de Symantec sertifikasını kullanarak yukarıdaki adımlarla Windows Phone cihaz kaydını etkinleştirmeniz gerekir. Ardından, Windows Phone 8.1 Şirket Portalı uygulamasını indirmeniz ve Symantec sertifikanızla imzalamanız gerekir.  Bu yalnızca, kullanıcılar Şirket Deposunu kullanmayacaksa ve Şirket Portalı’nı Windows Phone 8.1 cihazlara dağıtmak istiyorsanız gereklidir.


1.  **Şirket Portalı'nı indirme**

    İndirme Merkezi’nden [Windows Phone 8.1 için Microsoft Intune Şirket Portalı Uygulaması](http://go.microsoft.com/fwlink/?LinkId=615799)‘nı indirin ve kendiliğinden açılan (.exe) dosyayı çalıştırın. Bu dosya iki dosya içerir:

    -   CompanyPortal.appx– Windows Phone 8.1 için Şirket Portalı yükleme uygulaması

    -   WinPhoneCompanyPortal.ps1 – Windows Phone 8.1 cihazlarına dağıtılabilmesi amacıyla Şirket Portalı uygulama dosyasını imzalamak için kullanabileceğiniz bir PowerShell betiği.

2.  **Windows Phone SDK’sını indirme** [Windows Phone SDK 8.0](http://go.microsoft.com/fwlink/?LinkId=615570)’ı indirin (http://go.microsoft.com/fwlink/?LinkId=268439) ve SDK’yı bilgisayarınıza yükleyin. Bu SDK, bir uygulama kaydı belirteci oluşturmak için gereklidir.

3.  **AETX dosyası oluşturma** Windows Phone SDK 8.0’ın parçası olan AETGenerator.exe dosyasını kullanarak Symantec PFX dosyasından bir uygulama kaydı belirteci (.aetx) dosyası oluşturun. AETX dosyasının nasıl oluşturulacağına ilişkin yönergeler için bkz. [Windows Phone için uygulama kaydı belirteci oluşturma](https://msdn.microsoft.com/library/windows/apps/jj735576.aspx)

4.  **Windows 8.1 için Windows SDK’sını indirme** [Windows Phone SDK’sını](http://go.microsoft.com/fwlink/?LinkId=613525) (http://go.microsoft.com/fwlink/?LinkId=613525) indirin ve yükleyin. Şirket Portalı uygulamasına dahil edilen PowerShell betiğinin varsayılan yükleme konumunu (`${env:ProgramFiles(x86)}\Windows Kits\8.1`) kullandığını unutmayın. Başka bir yere yüklerseniz, bir cmdlet parametresinde konumu eklemeniz gerekir.

5.  **PowerShell kullanarak uygulama kodunu imzalama** Yönetici olarak, Windows SDK’sı ve Symantec Kurumsal Mobil Kod İmzalama Sertifikası yüklenmiş ana bilgisayarda **Windows PowerShell**’i açın, Sign-WinPhoneCompanyPortal.ps1 dosyasına gidin ve betiği çalıştırın.

    **Örnek 1**

    ```
    .\Sign-WinPhoneCompanyPortal.ps1 -InputAppx 'C:\temp\CompanyPortal.appx' -OutputAppx 'C:\temp\CompanyPortalEnterpriseSigned.appx' -PfxFilePath 'C:\signing\cert.pfx' -PfxPassword '1234' -AetxPath 'C:\signing\cert.aetx'
    ```
    Bu örnek, C:\temp\ konumundaki CompanyPortal.appx dosyasını imzalar ve CompanyPortalEnterpriseSigned.appx dosyasını üretir. PFX parolası olarak 1234’ü kullanır ve PFX dosyasından yayımcı kimliğini okur. Cert.aetx dosyasından kuruluş kimliğini de okur.

    **Örnek 2**

    ```
    .\Sign-WinPhoneCompanyPortal.ps1 -InputAppx 'C:\temp\CompanyPortal.appx' -OutputAppx 'C:\temp\CompanyPortalEnterpriseSigned.appx' -PfxFilePath 'C:\signing\cert.pfx' -PfxPassword '1234' -PublisherId 'OID.0.9.2342.19200300.100.1.1=1000000001, CN="Test, Inc.", OU=Test 1' -EnterpriseId 1000000001
    ```
    Bu örnek, C:\temp\ konumundaki CompanyPortal.appx dosyasını imzalar ve CompanyPortalEnterpriseSigned.appx dosyasını üretir. PFX parolası olarak 1234’ü ve belirtilen yayımcı kimliğini kullanır.

    **Parametreler:**

    -   `-InputAppx` – Tek tırnak içinde CompanyPortal.appx dosyasının yerel yolu. Örneğin, 'C:\temp\CompanyPortal.appx'

    -   `-OutputAppx` – Tek tırnak içinde, imzalanan Şirket Portalı uygulamasının yerel yolu ve dosya adı. Örneğin, 'C:\temp\CompanyPortalEnterpriseSigned.appx'

    -   `-PfxFilePath` – Symantec sertifikasının dışarı aktarılan PFX dosyasının yerel yolu ve dosya adı. Örneğin, 'C:\signing\cert.pfx'

    -   `-PfxPassword` – Tek tırnak içinde, PFX dosyasını imzalamak için kullanılan parola. Örneğin, '1234'

    -   `-AetxPath` – 'EnterpriseId' bağımsız değişkeni tanımlanmamışsa, kuruluş kimliğini okumak için kullanılan .aetx dosyasının yerel yolu. Bu bağımsız değişken veya EnterpriseId sağlanmalıdır. Örneğin, 'C:\signing\cert.aetx'

    -   `-PublisherId` - Kuruluşun Yayımcı kimliği. Yoksa, Symantec Kurumsal Mobil Kod İmzalama Sertifikası’nın 'Konu' alanı kullanılır. Örneğin, 'OID.0.9.2342.19200300.100.1.1=1000000001, CN="Test, Inc.", OU=Test 1'

    -   `-SdkPath` - Windows 8.1 için Windows SDK’sı kök klasörünün yolu. Bu bağımsız değişken isteğe bağlıdır ve varsayılan olarak ${env:ProgramFiles(x86)}\Windows Kits\8.1 değerindedir.

    -   `-EnterpriseId` - Kuruluş kimliği. Bu bağımsız değişken veya ‘AetxPath’ sağlanmalıdır. Bu bağımsız değişken sağlanmazsa, AETX dosyasından kuruluş kimliği okunur. Örneğin, 1000000001

6.  Windows Phone 8.1 Şirket Portalı (SSP.appx) uygulamasını dağıtın.

    > [!IMPORTANT]
    > Mağaza'dan edinilen ssp.xap ve Şirket Portalı aynı anda yüklenebilir ve bu da kullanıcılarda için kafa karışıklığına neden olabilir. Tüm kullanıcıların ssp.xap kullanmasını sağlamak için Şirket Portalı'nın mağaza sürümü için engellenen bir uygulama oluşturun. Tüm Windows Phone 8.1 cihazlarının yalnızca Şirket Portalı'nın mağaza sürümünü kullanmasını sağlamak için üç seçeneğiniz vardır:
    >
    > -   Uygulamaları dışarıdan yüklemeyecekseniz ve Windows Phone 8.0'i desteklemeniz gerekmiyorsa, imzalı ssp.xap dosyasını karşıya yüklemeyin.
    > -   Dışarıdan yüklenen uygulamalar gerekiyorsa ve kaydedilen Windows Phone 8 cihazı yoksa, otomatik olarak oluşturulan ssp.xap dağıtımını "kullanılabilir"den "kaldır"a değiştirin.
    > -   Dışarıdan yüklenen uygulamaların yüklenmesi gerekiyorsa ve Windows Phone 8.0 cihazlarının kaydolması ve ssp.xap'ı alması gerekiyorsa, ssp.xap'ın yeni bir yazılım dağıtımını oluşturun ve **Kaldır** eylemiyle dağıtın. Windows Phone 8.0 cihazları, uygulamaların zorla yüklenmesini veya kaldırılmasını desteklemediğinden, dağıtımı görmezden gelir. Windows Phone 8.1 cihazları, kaldırma eyleminin destekler ve ssp.xap'ı kaldırır.



<!--HONumber=Jul16_HO3-->


