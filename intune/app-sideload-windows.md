---
title: Dışarıdan yükleme Windows ve Windows Phone uygulamaları
titleSuffix: Microsoft Intune
description: Intune’u kullanarak iş kolu uygulamalarını dağıtmak için bunları nasıl imzalayacağınızı öğrenin.
keywords: ''
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 04/15/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: e44f1756-52e1-4ed5-bf7d-0e80363a8674
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8652d260849537d1e0b504f5d309a3ab2708e5cd
ms.sourcegitcommit: 8c795b041cd39e3896595f64f53ace48be0ec84c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2019
ms.locfileid: "59587527"
---
# <a name="sign-line-of-business-apps-so-they-can-be-deployed-to-windows-devices-with-intune"></a>Intune ile Windows cihazlarına dağıtmak için iş kolu uygulamalarını imzalayın

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Intune yöneticisi olarak Şirket Portalı uygulaması dahil olmak üzere iş kolu uygulamalarını Windows ve Windows 10 Mobile cihazlarına dağıtabilirsiniz. Windows 10 ve Windows 10 Mobile cihazlarına .appx veya .xap uygulamalarını veya Windows 8.1 ya da Windows Phone 8.1 cihazlarına iş kolu uygulamalarını dağıtmak için **Symantec Enterprise Mobil Kod İmza Sertifikası** edinmeniz gerekir. Windows cihazlarda bu uygulamalar için yalnızca Symantec sertifikasına güvenilir. Windows 10 uygulamaları ve "evrensel" uygulamalar için kendi sertifika yetkilinizi kullanabilirsiniz. Aşağıdakileri yapmak için bu sertifika gereklidir:

-   Şirket Portalı uygulamasını Windows bilgisayarlara, Windows 10 Mobile cihazlarına ve Windows Phone cihazlarına dağıtmak üzere uygulama

-   Şirket iş kolu uygulamalarının Intune tarafından Windows Phone cihazlarına dağıtılabilmesi için şirket iş kolu uygulamalarını imzalama

Aşağıdaki adımlar, gerekli sertifikayı almanıza ve uygulamaları imzalamanıza yardımcı olur. Microsoft geliştiricisi olarak kaydolmanız ve ardından Symantec sertifikası satın almanız gerekir.


1. **Microsoft geliştiricisi olarak kaydolma**<br>
   Şirket hesabınızı satın alırken oturum açtığınız kurumsal hesap bilgilerini kullanarak [bir Microsoft geliştiricisi olarak kaydolun](https://go.microsoft.com/fwlink/?LinkId=268442). Bu istek, kod imzalama sertifikası sizin tarafınızdan alınmadan önce bir şirket yetkilisi tarafından yetkilendirilmelidir.

2. **Şirket Symantec sertifikası alma**<br>
  Symantec ID'nizi kullanarak [Symantec web sitesinden](https://go.microsoft.com/fwlink/?LinkId=268441) bir sertifika satın alın. Sertifikayı satın aldıktan sonra, Microsoft geliştiricisi olarak kaydolurken belirlediğiniz kurum onay sorumlusu sertifika isteğini onaylamasını isteyen bir e-posta alır. Symantec sertifika gereksinimi hakkında daha fazla bilgi için bkz. [Windows Phone neden Symantec sertifikası gerektiriyor?](https://technet.microsoft.com/library/dn764959.aspx#BKMK_Symantec) Windows cihaz kaydı SSS.

3.  **Sertifikaları içeri aktarma**<br>
    İstek onaylandıktan sonra sertifikaları içeri aktarmaya yönelik yönergeler içeren bir e-posta alacaksınız. Sertifikaları içeri aktarmak için e-postadaki yönergeleri izleyin.

4.  **Sertifikaların içeri aktarıldığını doğrulama**<br>
    Sertifikaların düzgün bir şekilde içeri aktarıldığını doğrulamak için **Sertifikalar** ek bileşenine gidin, **Sertifikalar**'a sağ tıklayın ve **Sertifikaları Bul**'u seçin. **İçerir** alanına "Symantec" yazın ve **Şimdi Bul**'a tıklayın. İçeri aktardığınız sertifikaların sonuçlarda görüntülenmesi gerekir.

    ![Sertifika sonuçları sertifikaları Bul iletişim kutusunda listelenir.](./media/wit.gif)

5. **İmzalama sertifikasını dışarı aktarma**<br>
    Sertifikaların mevcut olduğunu doğruladıktan sonra, şirket portalını imzalamak için .pfx dosyasını dışarı aktarabilirsiniz. **Hedeflenen amaç** "kod imzalama" ibaresine sahip Symantec sertifikasını seçin. Kod imzalama sertifikasına sağ tıklayıp **Dışarı Aktar**'ı seçin.

    ![İmzalama sertifikasını dışarı aktarma](./media/wit-walk-cert2.gif)

    **Sertifika Dışarı Aktarma Sihirbazı**'nda **Evet, özel anahtarı dışarı aktar** 'ı seçin ve ardından **İleri**'ye tıklayın. **Personal Information Exchange –PKCS #12 (.PFX) seçeneğini belirleyin** ve **Mümkünse sertifika yolundaki tüm sertifikaları dahil et**'i işaretleyin. Sihirbazı tamamlayın. Daha fazla bilgi için bkz. [Özel Anahtara Sahip Bir Sertifikayı Dışarı Aktarma](https://go.microsoft.com/fwlink/?LinkID=203031).

6.  **Uygulamayı Intune'a yükleme**<br>
    İmzalanmış uygulama dosyasını ve kod imzalama sertifikanızı karşıya yükleyerek uygulamayı son kullanıcılarınızın kullanımına sunun.

    1.  Azure portalında **Yönetim** &gt; **Windows Phone**’a tıklayın.

    2.  **İmzalanmış Uygulama Dosyasını Karşıya Yükle** 'ye tıklayın ve Intune Yönetici Kimliğinizle oturum açın.

    3.  **Kod imzalama sertifikası** olarak dışa aktardığınız sertifika (.pfx) dosyasını ekleyin ve sertifika için bir parola oluşturun.

    4.  Sihirbazı tamamlayın.

## <a name="example-download-sign-and-deploy-the-company-portal-app-for-windows-devices"></a>Örnek: İndirme, oturum ve Windows cihazları için Şirket portalı uygulamasını dağıtma

Intune Şirket Portalı uygulamasını Windows Phone ve Windows 10 Mobile cihazları dahil olmak üzere Windows cihazlarına Microsoft Mağazası’ndan yüklemek yerine Intune ile dağıtabilirsiniz. Şirket Portalı uygulamasını indirmeniz ve sertifikanızla imzalamanız gerekir.  Bu yalnızca, kullanıcılar Şirket Deposunu kullanmayacaksa ve Şirket Portalı’nı Windows Phone 8.1 cihazlara dağıtmak istiyorsanız gereklidir.


1.  **Şirket Portalı’nı indirme**

    Şirket Portalı uygulamasını Intune'u kullanarak dağıtmak için İndirme Merkezi’nden [Windows Phone 8.1 için Microsoft Intune Şirket Portalı Uygulaması](https://go.microsoft.com/fwlink/?LinkId=615799)'nı indirebilir ve kendiliğinden açılan (.exe) dosyayı çalıştırabilirsiniz. Bu dosya iki dosya içerir:

    -   CompanyPortal.appx– Windows Phone 8.1 için Şirket Portalı yükleme uygulaması

    -   WinPhoneCompanyPortal.ps1 – Windows Phone 8.1 cihazlarına dağıtılabilmesi amacıyla Şirket Portalı uygulama dosyasını imzalamak için kullanabileceğiniz bir PowerShell betiği.

    Alternatif olarak, Windows Phone 8.1 Şirket Portalı (çevrimdışı lisanslı paket) uygulamasını veya Windows 10 Şirket Portalı’nı (çevrimdışı lisanslı paket) [İş İçin Microsoft Mağazası](https://businessstore.microsoft.com/)'ndan indirebilirsiniz. Şirket Portalı uygulamasının çevrimdışı lisansla alınması ve çevrimdışı kullanım için uygun paketin indirilmesi gerekir. Seçilen Windows 8 ve Windows Phone 8 platformu örnekleri, 8.1 yerine kullanılamaz. Bunun Intune’da nasıl yapılacağına ilişkin ayrıntılar için bkz. [İş için Microsoft Mağazası'ndan satın aldığınız uygulamaları yönetme](windows-store-for-business.md).

2.  **Windows Phone SDK’sını indirme** [Windows Phone SDK’sı 8.0’ı indirin] (https://go.microsoft.com/fwlink/?LinkId=615570)) ve SDK’yı bilgisayarınıza yükleyin. Bu SDK, bir uygulama kaydı belirteci oluşturmak için gereklidir.

3.  **AETX dosyası oluşturma** Windows Phone SDK 8.0’ın parçası olan AETGenerator.exe dosyasını kullanarak Symantec PFX dosyasından bir uygulama kaydı belirteci (.aetx) dosyası oluşturun. AETX dosyasının nasıl oluşturulacağına ilişkin yönergeler için bkz. [Windows Phone için uygulama kaydı belirteci oluşturma](https://msdn.microsoft.com/library/windows/apps/jj735576.aspx)

4.  **Windows 8.1 için Windows SDK’sını indirme** [Windows Phone SDK’sını](https://go.microsoft.com/fwlink/?LinkId=613525) (https://go.microsoft.com/fwlink/?LinkId=613525)) indirin ve yükleyin. Şirket Portalı uygulamasına dahil edilen PowerShell betiğinin varsayılan yükleme konumunu (`${env:ProgramFiles(x86)}\Windows Kits\8.1`) kullandığını unutmayın. Başka bir yere yüklerseniz, bir cmdlet parametresinde konumu eklemeniz gerekir.

5.  **PowerShell kullanarak uygulama kodunu imzalama** Yönetici olarak, Windows SDK’sı ve Symantec Kurumsal Mobil Kod İmzalama Sertifikası yüklenmiş ana bilgisayarda **Windows PowerShell**’i açın, Sign-WinPhoneCompanyPortal.ps1 dosyasına gidin ve betiği çalıştırın.

    **Örnek 1**

    ```PowerShell
    .\Sign-WinPhoneCompanyPortal.ps1 -InputAppx 'C:\temp\CompanyPortal.appx' -OutputAppx 'C:\temp\CompanyPortalEnterpriseSigned.appx' -PfxFilePath 'C:\signing\cert.pfx' -PfxPassword '1234' -AetxPath 'C:\signing\cert.aetx'
    ```
    Bu örnek, C:\temp\ konumundaki CompanyPortal.appx dosyasını imzalar ve CompanyPortalEnterpriseSigned.appx dosyasını üretir. PFX parolası olarak 1234’ü kullanır ve PFX dosyasından yayımcı kimliğini okur. Cert.aetx dosyasından kuruluş kimliğini de okur.

    **Örnek 2**

    ```PowerShell
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

6.  Windows Phone 8.1 Şirket Portalı (SSP.appx) uygulamasını dağıtın. Rehber için bkz. [Windows Phone iş kolu (LOB) uygulamaları ekleme](lob-apps-windows-phone.md).

## <a name="how-to-renew-the-symantec-enterprise-code-signing-certificate"></a>Symantec kurumsal kod imzalama sertifikasını yenileme

Belirli Windows ve Windows Phone mobil uygulamalarını dağıtmak için kullanılan Symantec sertifikasının düzenli aralıklarla yenilenmesi gerekir.

1.  Sertifikanın süresi dolmadan yaklaşık 14 gün önce Symantec tarafından gönderilen yenileme e-postasını bulun. Bu e-posta, kurumsal sertifikanızı yenileme hakkında Symantec tarafından gönderilen yönergeleri içerir.

    Symantec sertifikaları hakkında ek bilgi için [www.symantec.com](https://www.symantec.com) adresini ziyaret edin veya 1-877-438-8776 ya da 1-650-426-3400 numaralı telefonları arayın.

2.  Web sitesine gidin (örneğin: [https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do)) ve sertifikayla ilişkili Symantec Yayımcı Kimliği ve e-posta adresi ile oturum açın. Yenileme işlemini başlatmak için, sertifika indirmek için kullanacağınız makineyle aynı makineyi kullanmayı unutmayın.

3.  Yenileme onaylandıktan ve ücreti ödenen sonra, sertifikayı indirin.

### <a name="how-to-install-the-updated-certificate-for-line-of-business-lob-apps"></a>İş kolu (LOB) uygulamaları için güncelleştirilmiş sertifika yükleme

1.  İş kolu uygulamanızın son sürümünü imzalayın.

2.  Azure portalını açın ve **Yönetici** &gt; **Mobil Cihaz Yönetimi** &gt; **Windows Phone**’a gidip **İmzalı Uygulamayı Karşıya Yükle**’ye tıklayın.

3.  Yeni imzalanan Şirket Portalı'nı karşıya yükleyin. Yeni imzalanan SSP.xap ile Symantec'ten aldığınız yeni .PFX dosyasına ya da bu yeni .PFX dosyasıyla oluşturulmuş uygulama kayıt belirtecine ihtiyacınız olacaktır.

4.  Karşıya yükleme tamamlandığında, eski Şirket Portalı sürümünü **Yazılımlar** çalışma alanından kaldırın.

5.  Yeni sertifikayı kullanarak tüm yeni ve güncelleştirilmiş kurumsal iş kolu uygulamalarını imzalayın. Mevcut uygulamaların yeniden imzalanması ve dağıtılması gerekmez.

## <a name="manually-deploy-windows-10-company-portal-app"></a>Windows 10 Şirket Portalı uygulamasını el ile dağıtma
Intune ile İş İçin Microsoft Mağazası’nı tümleştirmiş olmasanız bile Windows 10 Şirket Portalı uygulamasını doğrudan Intune'dan dağıtabilirsiniz.

 > [!NOTE]
 > Bu seçeneğin kullanılması, her uygulama güncelleştirmesi yayımlandığında el ile güncelleştirme dağıtılmasını gerektirir.

1. [İş İçin Microsoft Mağazası](https://www.microsoft.com/business-store)’ndaki hesabınızda oturum açın ve Intune Şirket Portalı uygulamasının **çevrimdışı lisanslı** sürümünü edinin.  
2. Uygulamayı aldıktan sonra **Envanter** sayfasında uygulamayı seçin.  
3. **Platform** olarak **Windows 10 tüm cihazlar**’ı ve uygun **Mimari**’yi seçip sonra indirin. Bu uygulama için bir uygulama lisans dosyası gerekmez.
![Windows 10 X86 Paket ayrıntılarını indirmek için görüntüsü](./media/Win10CP-all-devices.png)
4. "Gerekli Çerçeveler" başlığı altındaki tüm paketleri indirin. Bu işlem x86, x64 ve ARM mimarileri için gerçekleştirilmelidir. Böylece aşağıda gösterildiği gibi toplam 9 paket gerekir.

![İndirilecek bağımlılık dosyalarının görüntüsü ](./media/Win10CP-dependent-files.png)
5. Şirket Portalı uygulamasını Intune’a yüklemeden önce, paketlerin aşağıdaki şekilde yapılandırıldığı bir klasör (ör. C:&#92;Company Portal) oluşturun:
   1. Şirket Portalı paketini C:\Company Portal adresine koyun. Bu konumda bir Dependencies alt klasörü oluşturun.  
   ![APPXBUN dosyasıyla kaydedilen Dependencies klasörünün görüntüsü](./media/Win10CP-Dependencies-save.png)
   2. Dokuz bağımlılık paketini Dependencies klasörüne yerleştirin.  
   Bağımlılıklar, bu biçimde yerleştirilmezse Intune tarafından tanınamazlar ve paketin karşıya yüklenmesi sırasında karşıya yüklenemezler. Bu durumda, karşıya yükleme aşağıdaki hatayı vererek başarısız olur.  
   ![Hata iletisi - Windows uygulama bağımlılığı sağlanmalıdır.](./media/Win10CP-error-message.png)
6. Intune'a dönün ve Şirket Portalı uygulamasını yeni bir uygulama olarak karşıya yükleyin. Uygulamayı, istenen hedef kullanıcı kümesine gerekli bir uygulama olarak dağıtın.  

Intune’un Evrensel uygulamaların bağımlılıklarını nasıl işlediği hakkında daha fazla bilgi edinmek için bkz. [Microsoft Intune MDM aracılığıyla bağımlılıkları olan bir appxbundle dağıtma](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/).  

### <a name="how-do-i-update-the-company-portal-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Kullanıcılarım eski uygulamaları mağazadan zaten yüklemişlerse cihazlarında Şirket Portalı’nı nasıl güncelleştirebilirim?
Kullanıcılarınız, Windows 8.1 veya Windows Phone 8.1 Şirket Portalı uygulamalarını Mağaza'dan zaten yüklemişlerse sizin ya da kullanıcınızın herhangi bir işlemde bulunmasına gerek kalmadan bu uygulamalar otomatik olarak yeni sürüme güncelleştirilecektir. Bu güncelleştirme gerçekleşmezse, kullanıcılarınızdan cihazlarında Mağaza uygulamaları için otomatik güncelleştirmeleri etkinleştirdiklerini denetlemelerini isteyin.   

### <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Dışarıdan yüklenen Windows 8.1 Şirket Portalı uygulamamı Windows 10 Şirket Portalı uygulamasına nasıl yükseltebilirim?
Önerdiğimiz geçiş yolu, Windows 8.1 Şirket Portalı uygulaması için dağıtım eylemini "Kaldır" şeklinde ayarlayarak dağıtımı silmektir. Bunu yaptıktan sonra Windows 10 Şirket Portalı uygulaması yukarıdaki seçeneklerden herhangi biri kullanılarak dağıtılabilir.  

Uygulamayı dışarıdan yüklemeniz gerekiyorsa ve Windows 8.1 Şirket Portalı’nı Symantec Sertifikasıyla imzalamadan dağıttıysanız, yükseltmeyi tamamlamak için yukarıdaki Doğrudan Intune aracılığıyla dağıtma bölümünde sunulan adımları izleyin.

Uygulamayı dışarıdan yüklemeniz gerekiyorsa ve Windows 8.1 Şirket Portalı’nı Symantec kod imzalama sertifikası ile imzalayıp dağıttıysanız aşağıdaki bölümde sunulan adımları izleyin.  

### <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Dışarıdan yüklenmiş ve imzalı Windows Phone 8.1 veya Windows 8.1 Şirket Portalı uygulamamı Windows 10 Şirket Portalı uygulamasına nasıl yükseltebilirim?
Önerdiğimiz geçiş yolu, Windows Phone 8.1 veya Windows 8.1 Şirket Portalı uygulaması için dağıtım eylemini "Kaldır" şeklinde ayarlayarak mevcut dağıtımı silmektir. Bunu yaptıktan sonra Windows 10 Şirket Portalı uygulaması normal bir biçimde dağıtılabilir.  

Aksi takdirde, yükseltme yoluna uyulduğundan emin olmak için Windows 10 Şirket Portalı uygulamasının uygun şekilde güncelleştirilmesi ve imzalanması gerekir.  

Windows 10 Şirket Portalı uygulaması bu şekilde imzalanır ve dağıtılırsa, mağazada kullanıma sunulan her yeni uygulama güncelleştirmesi için bu işlemi tekrarlamanız gerekecektir. Mağaza güncelleştirildiğinde uygulama otomatik olarak güncelleştirilmez.  

Uygulamanın bu şekilde nasıl imzalanıp dağıtılacağı aşağıda açıklanmaktadır:

1. Microsoft Intune Windows 10 Şirket Portalı Uygulaması İmzalama Betiğini [https://aka.ms/win10cpscript](https://aka.ms/win10cpscript) adresinden indirin.  Bu betik, Windows 10 için Windows SDK’nın ana bilgisayara yüklenmiş olmasını gerektirir. Windows 10 için Windows SDK’sını indirmek için [https://go.microsoft.com/fwlink/?LinkId=619296](https://go.microsoft.com/fwlink/?LinkId=619296) adresini ziyaret edin.
2. Windows 10 Şirket Portalı uygulamasını yukarıda açıklandığı biçimde İş İçin Microsoft Mağazası'ndan indirin.  
3. Betik üst bilgisinde açıklanan giriş parametrelerini (ayıklanmış hali aşağıdadır) kullanıp betiği çalıştırarak Windows 10 Şirket Portalı uygulamasını imzalayın. Bağımlılıkların betiğe geçirilmesi gerekmez. Bunlar, yalnızca uygulama Intune Yönetici Konsolu’na yüklenirken gereklidir.

|       Parametre       |                                                                    Açıklama                                                                    |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| InputWin10AppxBundle  |                                             Kaynak appxbundle dosyasının bulunduğu yol.                                              |
| OutputWin10AppxBundle |                                                  İmzalı appxbundle dosyası için çıkış yolu.                                                  |
|       Win81Appx       |                          Windows 8.1 veya Windows Phone 8.1 Şirket Portalı (.APPX) dosyasının bulunduğu yol.                           |
|      PfxFilePath      |                                   Symantec Enterprise Mobil Kod İmza Sertifikası (.PFX) dosyasının yolu.                                    |
|      PfxPassword      |                                     Symantec Enterprise Mobil Kod İmza Sertifikası’nın parolası.                                      |
|      PublisherId      |      Kuruluşun Yayımcı Kimliği. Yoksa, Symantec Kurumsal Mobil Kod İmzalama Sertifikası’nın 'Konu' alanı kullanılır.       |
|        SdkPath        | Windows 10 için Windows SDK’sı kök klasörünün yolu. Bu bağımsız değişken isteğe bağlıdır ve varsayılan olarak ${env:ProgramFiles(x86)}\Windows Kits\10 değerindedir. |

Betik, çalışması tamamlandığında Windows 10 Şirket Portalı uygulamasının imzalı sürümünü çıktı olarak sunar. Ardından Intune aracılığıyla uygulamanın imzalı sürümünü bir LOB uygulaması olarak dağıtabilirsiniz. Şu anda dağıtılmış durumdaki sürümler, bu yeni uygulamaya yükseltilir.  
