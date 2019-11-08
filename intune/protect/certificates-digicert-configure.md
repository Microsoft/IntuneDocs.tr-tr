---
title: Microsoft Intune ile DigiCert PKCS sertifikaları verme
titleSuffix: Microsoft Intune
description: DigiCert PKI platformundan Intune tarafından yönetilen cihazlara PKCS sertifikaları vermek için Intune sertifika bağlayıcısını yükleyip yapılandırın.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ca76ffe0c8fa42f1c2cf24fcdefd287140231220
ms.sourcegitcommit: b5e719fb507b1bc4774674e76c856c435e69f68c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/08/2019
ms.locfileid: "73801636"
---
# <a name="set-up-intune-certificate-connector-for-digicert-pki-platform"></a>DigiCert PKI platformu için Intune sertifika bağlayıcısını ayarlama

DigiCert PKI platformundan Intune tarafından yönetilen cihazlara PKCS sertifikaları vermek için Intune sertifika bağlayıcısını kullanın. Bağlayıcıyı yalnızca bir DigiCert sertifika yetkilisi (CA) veya hem DigiCert CA 'sı hem de bir Microsoft CA ile kullanabilirsiniz.

> [!TIP]
> DigiCert Symantec 'in Web sitesi güvenliğini ve ilgili PKI çözümleri işletmelerini aldı. Bu değişiklik hakkında daha fazla bilgi için bkz. [Symantec Teknik Destek makalesi](https://support.symantec.com/en_US/article.INFO4722.html).

Bir Microsoft CA 'dan PKCS veya System Center Endpoint Protection kullanarak sertifika vermek için Intune sertifika bağlayıcısını zaten kullanıyorsanız, bu bağlayıcıyı kullanarak bir DigiCert CA 'dan PKCS sertifikaları yapılandırabilir ve verebilirsiniz. DigiCert CA 'sını destekleyecek şekilde yapılandırmayı tamamladıktan sonra, Intune sertifika Bağlayıcısı aşağıdaki sertifikaları verebilir:

* Bir Microsoft CA 'dan PKCS sertifikaları
* DigiCert CA 'dan PKCS sertifikaları
* Microsoft CA 'dan sertifika Endpoint Protection

Bağlayıcı yüklü değilse ancak hem Microsoft CA hem de DigiCert CA 'sı için kullanmayı planlıyorsanız, önce Microsoft CA için bağlayıcı yapılandırmasını doldurun. Daha sonra, bu makaleye geri dönüp DigiCert desteğini de destekleyecek şekilde yapılandırın. Sertifika profilleri ve bağlayıcı hakkında daha fazla bilgi için, bkz. [Microsoft Intune cihazlarınız için bir sertifika profili yapılandırma](certificates-configure.md).  

Bağlayıcıyı yalnızca DigiCert CA 'sı ile kullanacaksanız, bağlayıcıyı yüklemek ve yapılandırmak için bu makaledeki yönergeleri kullanabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

- **DigiCert CA 'sında etkin bir abonelik**: DigiCert CA 'dan bir kayıt YETKILISI (ra) sertifikası almak için abonelik gerekir.

## <a name="install-the-digicert-ra-certificate"></a>DigiCert RA sertifikasını yükler

1. Aşağıdaki kod parçacığını **CertReq. ini** adlı bir dosyaya kaydedin ve gerektiği şekilde güncelleştirin (ÖRNEĞIN: *cn biçimindeki konu adı*).

        [Version] 
        Signature="$Windows NT$" 
        
        [NewRequest] 
        ;Change to your,country code, company name and common name 
        Subject = "Subject Name in CN format"
        
        KeySpec = 1 
        KeyLength = 2048 
        Exportable = TRUE 
        MachineKeySet = TRUE 
        SMIME = False 
        PrivateKeyArchive = FALSE 
        UserProtected = FALSE 
        UseExistingKeySet = FALSE 
        ProviderName = "Microsoft RSA SChannel Cryptographic Provider" 
        ProviderType = 12 
        RequestType = PKCS10 
        KeyUsage = 0xa0 
        
        [EnhancedKeyUsageExtension] 
        OID=1.3.6.1.5.5.7.3.2 ; Client Authentication  // Uncomment if you need a mutual TLS authentication
        
        ;----------------------------------------------- 

2. Yükseltilmiş bir komut istemi açın ve aşağıdaki komutu kullanarak bir sertifika imzalama isteği (CSR) oluşturun:

   `Certreq.exe -new certreq.ini request.csr`

3. Request. CSR dosyasını Not defteri 'nde açın ve aşağıdaki biçimdeki CSR içeriğini kopyalayın:

        -----BEGIN NEW CERTIFICATE REQUEST-----
        MIID8TCCAtkCAQAwbTEMMAoGA1UEBhMDVVNBMQswCQYDVQQIDAJXQTEQMA4GA1UE
        …
        …
        fzpeAWo=
        -----END NEW CERTIFICATE REQUEST-----


4. DigiCert CA ' da oturum açın ve görevlerden **ra sertifikası almak** için gidin.

   a. Metin kutusunda 3. adımdaki CSR içeriğini sağlayın.

   b. Sertifika için bir kolay ad sağlayın.

   c. **Devam**' ı seçin.

   d. RA sertifikasını yerel bilgisayarınıza indirmek için, belirtilen bağlantıyı kullanın.

5. RA sertifikasını Windows sertifika deposuna aktarın:

   a. Bir MMC konsolu açın.

   b.  > **Dosya** **seçin > ** **ek bileşenleri Ekle veya Kaldır** > **Ekle**' ye tıklayın.

   c. **Bilgisayar hesabı** > **İleri ' yi**seçin.

   d. **Yerel bilgisayar** > **son**' u seçin.

   e. **Ek bileşenler ekleme veya kaldırma** penceresinde **Tamam ' ı** seçin. **Sertifikalar (yerel bilgisayar)**  > **Kişisel** > **sertifikaları**' nı genişletin.

   f. **Sertifikalar** düğümüne sağ tıklayın ve **Tüm Görevler** > **İçeri aktar**’ı seçin.

   g. DigiCert CA 'dan indirdiğiniz RA sertifikasının konumunu seçin ve ardından **İleri**' yi seçin.

   olsun. **Kişisel sertifika depolama** > **İleri ' yi**seçin.

   i. RA sertifikasını ve özel anahtarını **yerel makine-kişisel** mağazaya aktarmak için **son** ' u seçin.

6. Özel anahtar sertifikasını içeri ve dışarı aktarma:

   a. **Sertifikalar (Yerel Makine)**  > **Kişisel** > **Sertifikalar**’ı genişletin.

   b. Önceki adımda içeri aktarılan sertifikayı seçin.

   c. Sertifikaya sağ tıklayın ve **dışarı aktar** > **Tüm görevler** ' i seçin.

   d. **İleri**' yi seçin ve parolayı girin.

   e. Dışarı aktarılacak konumu seçin ve ardından **son**' u seçin.

   f. Özel anahtar sertifikasını **Yerel bilgisayar-kişisel** mağazaya aktarmak için 5. adımdaki yordamı kullanın.

   g. A kaydet RA sertifika parmak izini boşluk olmadan kopyalayın. Parmak izine bir örnek aşağıda verilmiştir:

        RA Cert Thumbprint: “EA7A4E0CD1A4F81CF0740527C31A57F6020C17C5”

    > [!NOTE]
    > DigiCert CA 'dan RA sertifikasını alma konusunda yardım için, [DigiCert müşteri desteği](mailto:enterprise-pkisupport@digicert.com)'ne başvurun.

## <a name="prepare-to-install-intune-certificate-connector"></a>Intune Sertifika Bağlayıcı'yı yüklemeye hazırlanma

> [!TIP]
> Bu bölüm, Intune sertifika bağlayıcısını yalnızca bir DigiCert CA 'sı ile kullanacaksanız geçerlidir. Intune sertifika bağlayıcısını bir Microsoft CA 'sı ile kullanıyorsanız ve DigiCert CA desteği eklemek istiyorsanız, [bağlayıcıyı DigiCert 'yi destekleyecek şekilde yapılandırma](#configure-the-connector-to-support-digicert)bölümüne atlayın.

1. Aşağıdaki listeden Windows işletim sistemi sürümlerinden birini seçin ve bir bilgisayara yükler:
   * Windows Server 2012 R2 Datacenter
   * Windows Server 2012 R2 Standard
   * Windows Server 2016 Datacenter
   * Windows Server 2016 Standard

2. Yönetici ayrıcalıkları olan bir kullanıcı oluşturun ve aşağıdaki adımları tamamlamak için kullanın.

3. En son Windows güncelleştirmelerini denetleyin ve varsa bunları yükler. Windows güncelleştirmelerini yükledikten sonra bilgisayarı yeniden başlatın.

4. .NET Framework 3.5 yükleme:

   a. **Denetim masası** > **programlar ve Özellikler** > **Windows özelliklerini açın veya kapatın**.

   b. **.NET Framework 3.5**’i seçin ve yükleyin.

## <a name="install-intune-certificate-connector-for-use-with-digicert"></a>DigiCert ile kullanmak için Intune sertifika bağlayıcısını yükler

> [!TIP]
> Intune sertifika bağlayıcısını bir Microsoft CA ile birlikte kullanıyorsanız ve DigiCert CA desteği eklemek istiyorsanız, [bağlayıcıyı DigiCert 'yi destekleyecek şekilde yapılandırma](#configure-the-connector-to-support-digicert)bölümüne atlayın.

Intune yönetim portalından en son Intune sertifika Bağlayıcısı sürümünü indirin ve bu yönergeleri izleyin.

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2. **Kiracı yönetimi** > **bağlayıcılar ve belirteçler** > **sertifika bağlayıcıları** >  **+ Ekle**' yi seçin.

3. PKCS #12 Bağlayıcısı için *sertifika Bağlayıcısı yazılımını indir* ' e tıklayın ve dosyayı bağlayıcıyı yükleyeceğiniz sunucudan erişebileceğiniz bir konuma kaydedin.

   ![Bağlayıcı yazılımını indirin](./media/certificates-digicert-configure/connector-download.png)

4. Bağlayıcıyı yüklemek istediğiniz sunucuda, yükseltilmiş ayrıcalıklarla **Ndesconnectorsetup. exe** ' yi çalıştırın.

5. **Yükleme seçenekleri** sayfasında **PFX dağıtımı**' nı seçin.

   ![PFX dağıtımı seçin](./media/certificates-digicert-configure/digicert-ca-connector-install.png)

   > [!IMPORTANT]
   > Intune sertifika bağlayıcısını bir Microsoft CA ve DigiCert CA 'dan sertifika vermek için kullanacaksanız, **SCEP ve PFX profili dağıtımı**' nı seçin.

6. Bağlayıcının kurulumunu tamamlayacak varsayılan seçimleri kullanın.

## <a name="configure-the-connector-to-support-digicert"></a>Bağlayıcıyı DigiCert 'yi destekleyecek şekilde yapılandırma

Varsayılan olarak, Intune sertifika Bağlayıcısı **%ProgramFiles%\Microsoft ıntune\ndesconnectorsvc**' ye yüklenir.

1. **Ndesconnectorsvc** klasöründe, Not defteri 'Nde **ndesconnector. exe. config** dosyasını açın.

   a. `RACertThumbprint` anahtarı değerini, önceki bölümde kopyaladığınız sertifika parmak izi değeriyle güncelleştirin. Örneğin:

        <add key="RACertThumbprint"
        value="EA7A4E0CD1A4F81CF0740527C31A57F6020C17C5"/>

   b. Dosyayı kaydedin ve kapatın.

2. **Services. msc**dosyasını açın:

   a. **Intune Bağlayıcı Hizmeti**’ni seçin.

   b. Hizmeti durdurun ve ardından hizmeti başlatın.

   c. Hizmetin penceresini kapatın.

## <a name="set-up-the-intune-administrator-account"></a>Intune yönetici hesabını ayarlama  

> [!TIP]
> Intune sertifika bağlayıcısını bir Microsoft CA 'sı ile kullanıyorsanız ve DigiCert CA desteği eklemek istiyorsanız, [bir güvenilen sertifika profili oluşturmaya](#create-a-trusted-certificate-profile)devam edin.
 
1. **%ProgramFiles%\Microsoft ıntune\ndesconnectoruı\ndesconnectorui.exe**öğesinden NDES Bağlayıcısı Kullanıcı arabirimini açın.

2. **Kayıt** sekmesinde **oturum aç**' ı seçin.

3. Intune kiracı yönetici kimlik bilgilerinizi sağlayın.

4. **Oturum aç**' ı seçin ve ardından başarılı bir kaydı onaylamak için **Tamam** ' ı seçin. Ardından NDES Bağlayıcısı Kullanıcı arabirimini kapatabilirsiniz.

   !["Başarıyla kaydedildi" iletisiyle NDES bağlayıcı arabirimi](./media/certificates-digicert-configure/certificates-digicert-configure-connector-configure.png)

## <a name="create-a-trusted-certificate-profile"></a>Güvenilen bir sertifika profili oluşturma

Intune tarafından yönetilen cihazlar için dağıtacağınız PKCS sertifikaları, güvenilen bir kök sertifikayla zincirleme olmalıdır. Bu zinciri oluşturmak için, DigiCert CA 'sından kök sertifikaya sahip bir Intune güvenilir sertifika profili oluşturun.

1. DigiCert CA 'dan güvenilen bir kök sertifika alın:

   a. DigiCert CA yönetici portalında oturum açın.

   b. **Görevlerden** **CA 'ları Yönet** ' i seçin.

   c. Listeden uygun CA 'yı seçin.

   d. Güvenilen kök sertifikayı indirmek için **kök sertifikayı indir** ' i seçin.

2. Intune portalında bir güvenilen sertifika profili oluşturun:

   a. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

   b. **Profil oluşturma** > **yapılandırma profilleri** > **cihazları** seçin.

   c. Aşağıdaki özellikleri girin:

      - Profil için **Ad**
      - İsteğe bağlı olarak bir **Açıklama** ayarlayın
      - Profili dağıtmak için **Platform**
      - **Profil türü**’nü **Güvenilen sertifika** olarak ayarlayın

   d. **Ayarlar**' ı seçin ve ardından bu sertifika profiliyle birlikte kullanmak üzere verdiğiniz GÜVENILEN kök CA sertifikası. cer dosyasına gidin ve ardından **Tamam**' ı seçin.

   e. Yalnızca Windows 8.1 ve Windows 10 cihazları için, güvenilen sertifika için **Hedef Depo** olarak şunlardan birini seçin:
      - **Bilgisayar sertifika deposu - Kök**
      - **Bilgisayar sertifika deposu - Ara**
      - **Kullanıcı sertifika deposu - Ara**

   f. Bitirdiğinizde **Tamam**’ı seçin, **Profil Oluştur** bölmesine gidin ve **Oluştur**’u seçin.  

  Profil, **cihaz yapılandırması-profiller** bölmesindeki profiller listesinde, **Güvenilen sertifika**profil türü ile görüntülenir.  Bu profili, sertifika alacak cihazlara atadığınızdan emin olun. Profili gruplara atamak için bkz. [cihaz profilleri atama](../configuration/device-profile-assign.md).


## <a name="get-the-certificate-profile-oid"></a>Sertifika profili OID 'sini al  

Sertifika profili OID 'si, DigiCert CA 'sında bir sertifika profili şablonuyla ilişkilendirilir. Intune 'da bir PKCS sertifika profili oluşturmak için, sertifika şablonu adı DigiCert CA 'sında bir sertifika şablonuyla ilişkili bir sertifika profili OID 'si biçiminde olmalıdır.

1. DigiCert CA yönetici portalında oturum açın.
2. **Sertifika profillerini Yönet**' i seçin.
3. Kullanmak istediğiniz sertifika profilini seçin.
4. Sertifika profili OID 'sini kopyalayın. Çıktı aşağıdaki örneğe benzer:

       Certificate Profile OID = 2.16.840.1.113733.1.16.1.2.3.1.1.47196109 

> [!NOTE]
> Sertifika profili OID 'sini almak için yardıma ihtiyacınız varsa, [DigiCert müşteri desteği](mailto:enterprise-pkisupport@digicert.com)'ne başvurun.

## <a name="create-a-pkcs-certificate-profile"></a>PKCS sertifika profili oluşturma

1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın.

2. **Profil oluşturma** > **yapılandırma profilleri** > **cihazları** seçin.

3. Aşağıdaki özellikleri girin:

   - Profil için **Ad**
   - İsteğe bağlı olarak bir **Açıklama** ayarlayın
   - Profili dağıtmak için **Platform**
   - **Profil türü**’nü **PKCS sertifikası** olarak ayarlayın

4. **PKCS sertifikası** bölmesinde, parametreleri aşağıdaki tablodaki değerlerle yapılandırın. Bu değerler, Intune sertifika Bağlayıcısı aracılığıyla bir DigiCert CA 'dan PKCS sertifikaları vermek için gereklidir.

   |PKCS sertifika parametresi | Değer | Description |
   | --- | --- | --- |
   | Sertifika yetkilisi | pki-ws.symauth.com | Bu değer, eğik çizgiler olmadan DigiCert CA temel hizmet FQDN 'SI olmalıdır. Bu, DigiCert CA aboneliğiniz için doğru temel hizmet FQDN 'si olup olmadığından emin değilseniz, DigiCert müşteri desteği 'ne başvurun. <br><br>*Symantec 'Ten DigiCert değişikliği ile bu URL değişmeden kalır*. <br><br> Bu FQDN yanlışsa, Intune sertifika Bağlayıcısı, DigiCert CA 'dan PKCS sertifikaları yayınmayacaktır.| 
   | Sertifika yetkilisi adı | Symantec | Bu değer bir dize olmalıdır **Symantec**. <br><br> Bu değerde herhangi bir değişiklik varsa, Intune sertifika Bağlayıcısı, DigiCert CA 'dan PKCS sertifikaları yayınmayacaktır.|
   | Sertifika şablonu adı | DigiCert CA 'dan sertifika profili OID 'si. Örneğin: **2.16.840.1.113733.1.16.1.2.3.1.1.61904612**| Bu değer, DigiCert CA sertifika profili şablonunun [önceki bölümünde elde edilen](#get-the-certificate-profile-oid) bir SERTIFIKA profili OID 'si olmalıdır. <br><br> Intune sertifika Bağlayıcısı, DigiCert CA 'sında bu sertifika profili OID 'siyle ilişkili bir sertifika şablonu bulamazsa, DigiCert CA 'dan PKCS sertifikaları yayınmayacaktır.|

   ![CA ve sertifika şablonu için seçimler](./media/certificates-digicert-configure/certificates-digicert-pkcs-example.png)

   > [!NOTE]
   > Windows platformları için PKCS sertifika profilinin güvenilen bir sertifika profiliyle ilişkilendirilmesi gerekmez. Ancak Android gibi Windows dışı platform profilleri için gereklidir.

5. İş gereksinimlerinizi karşılamak için profilin yapılandırmasını doldurun ve sonra profili kaydetmek için **Oluştur** ' u seçin.

6. Yeni profilin *genel bakış* sayfasında, **atamalar** ' ı seçin ve bu profili alacak uygun bir grup yapılandırın. En az bir kullanıcı veya cihaz atanan grubun parçası olmalıdır.
 
Önceki adımları tamamladıktan sonra, Intune sertifika Bağlayıcısı, DigiCert CA 'dan atanan gruptaki Intune tarafından yönetilen cihazlara PKCS sertifikaları verecek. Bu sertifikalar, Intune tarafından yönetilen cihazdaki **Geçerli Kullanıcı** sertifikası deposunun **Kişisel** deposunda kullanılabilir olacaktır.

### <a name="supported-attributes-for-the-pkcs-certificate-profile"></a>PKCS sertifika profili için desteklenen öznitelikler

|Öznitelik | Desteklenen Intune biçimleri | DigiCert bulut CA 'sı Desteklenen biçimleri | result |
| --- | --- | --- | --- |
| Konu adı |Intune, konu adını yalnızca aşağıdaki üç formatta destekler: <br><br> 1. ortak ad <br> 2. e-posta içeren ortak ad <br> 3. e-posta olarak ortak ad <br><br> Örneğin: <br><br> `CN = IWUser0 <br><br> E = IWUser0@samplendes.onmicrosoft.com` | DigiCert CA 'sı daha fazla öznitelik destekler.  Daha fazla öznitelik seçmek istiyorsanız, bu değerlerin DigiCert sertifika profili şablonunda sabit değerlerle tanımlanması gerekir.| PKCS sertifika isteğinden ortak ad veya e-posta kullanıyoruz. <br><br> Intune sertifika profili ve DigiCert sertifika profili şablonu arasındaki öznitelik seçiminde herhangi bir uyuşmazlık, DigiCert CA 'dan verilen sertifika olmadan sonuçlanır.|
| SAN | Intune yalnızca aşağıdaki SAN alan değerlerini destekler: <br><br> **AltNameTypeEmail** <br> **AltNameTypeUpn** <br> **Altnametypeothername** (kodlanmış değer) | DigiCert bulut CA 'sı de bu parametreleri destekler. Daha fazla öznitelik seçmek istiyorsanız, bu değerlerin DigiCert sertifika profili şablonunda sabit değerlerle tanımlanması gerekir. <br><br> **Altnametypeemail**: Bu tür San 'da bulunmazsa, Intune sertifika Bağlayıcısı, **Altnametypeupn**' den değeri kullanır.  **Altnametypeupn** de San 'da bulunmazsa, Intune sertifika Bağlayıcısı e-posta biçimindeyse konu adından değeri kullanır.  Tür hala bulunamazsa, Intune sertifika Bağlayıcısı sertifikaları veremez. <br><br> Örnek: `RFC822 Name=IWUser0@ndesvenkatb.onmicrosoft.com`  <br><br> **Altnametypeupn**: Bu tür San 'da bulunmazsa, Intune sertifika Bağlayıcısı **Altnametypeemail**değerini kullanır. **Altnametypeemail** de San 'da bulunmazsa, Intune sertifika Bağlayıcısı e-posta biçimindeyse konu adından değeri kullanır. Tür hala bulunamazsa, Intune sertifika Bağlayıcısı sertifikaları veremez.  <br><br> Örnek: `Other Name: Principal Name=IWUser0@ndesvenkatb.onmicrosoft.com` <br><br> **Altnametypeothername**: Bu tür San 'da bulunmazsa, Intune sertifika Bağlayıcısı sertifikaları veremez. <br><br> Örnek: `Other Name: DS Object Guid=04 12 b8 ba 65 41 f2 d4 07 41 a9 f7 47 08 f3 e4 28 5c ef 2c` <br><br>  Bu alanın değeri, DigiCert CA 'sı tarafından yalnızca kodlanmış biçimde (onaltılı değer) desteklenir. Bu alandaki herhangi bir değer için, Intune sertifika Bağlayıcısı sertifika isteğini göndermeden önce Base64 kodlamaya dönüştürür. *Intune Sertifika Bağlayıcı, bu değerin zaten kodlanmış olup olmadığını doğrulamaz.* | Yok. |

## <a name="troubleshooting"></a>Sorun giderme

Intune sertifika Bağlayıcısı hizmet günlükleri, NDES bağlayıcı makinesindeki **%ProgramFiles%\Microsoft ıntune\ndesconnectorsvc\logs\logs** dizininde bulunur. Günlükleri [SvcTraceViewer](https://docs.microsoft.com/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe) içinde açın ve özel durumlar veya hata iletileri arayın.

| Sorun/hata iletisi | Çözüm adımları |
| --- | --- |
| NDES Bağlayıcısı Kullanıcı arabiriminde Intune kiracı yönetici hesabıyla oturum açılamıyor. | Bu durum, şirket içi sertifika Bağlayıcısı Microsoft Endpoint Manager Yönetim Merkezi 'nde etkin olmadığında ortaya çıkabilir. Bu sorunu çözmek için: <br><br> 1. [Microsoft Endpoint Manager Yönetim merkezinde](https://go.microsoft.com/fwlink/?linkid=2109431)oturum açın. <br> 2. **kiracı yönetimi** > **bağlayıcılar ve belirteçler** > **sertifika bağlayıcıları**' nı seçin. <br> 3. sertifika bağlayıcısını bulun ve etkinleştirildiğinden emin olun. <br><br> Önceki adımları tamamladıktan sonra, NDES Bağlayıcısı Kullanıcı arabiriminde aynı Intune kiracı yönetici hesabıyla oturum açmayı deneyin. |
| NDES Bağlayıcı Sertifikası bulunamadı. <br><br> System. ArgumentNullException: değer null olamaz. | Intune kiracı yönetici hesabı NDES Bağlayıcı Kullanıcı Arabirimi'nde hiç oturum açmadıysa, Intune Sertifika Bağlayıcı bu hatayı gösterir. <br><br> Bu hata devam ederse, Intune Service bağlayıcısını yeniden başlatın. <br><br> 1. **Services. msc**dosyasını açın. <br> 2. **Intune bağlayıcı hizmeti**' ni seçin. <br> 3. sağ tıklayın ve **Yeniden Başlat**'ı seçin.|
| NDES Bağlayıcısı - IssuePfx- Genel Özel Durumu: <br> System.NullReferenceException: Nesne başvurusu bir nesnenin örneğine ayarlı değil. | Bu geçici bir hatadır. Intune hizmet bağlayıcısını yeniden başlatın. <br><br> 1. **Services. msc**dosyasını açın. <br> 2. **Intune bağlayıcı hizmeti**' ni seçin. <br> 3. sağ tıklayın ve **Yeniden Başlat**'ı seçin. |
| DigiCert sağlayıcısı-DigiCert ilkesi alınamadı. <br><br>"İşlem zaman aşımına uğradı." | Intune sertifika Bağlayıcısı, DigiCert CA ile iletişim kurarken bir işlem zaman aşımı hatası aldı. Bu hata oluşmaya devam ederse, bağlantı zaman aşımı değerini artırın ve yeniden deneyin. <br><br> Bağlantı zaman aşımını artırmak için: <br> 1. NDES bağlayıcı bilgisayarına gidin. <br>2. **%ProgramFiles%\Microsoft Intune\NDESConnectorSvc\NDESConnector.exe.config** dosyasını Not defteri 'nde açın. <br> 3. aşağıdaki parametre için zaman aşımı değerini artırın: <br><br> `CloudCAConnTimeoutInMilliseconds` <br><br> 4. Intune sertifika Bağlayıcısı hizmetini yeniden başlatın. <br><br> Sorun devam ederse, DigiCert müşteri desteği 'ne başvurun. |
| DigiCert sağlayıcısı-istemci sertifikası alınamadı. | Intune sertifika Bağlayıcısı, kaynak yetkilendirme sertifikasını yerel makineden alamadı-kişisel sertifika deposundan alamadı. Bu sorunu çözmek için, kaynak yetkilendirme sertifikasını, özel anahtarıyla birlikte yerel makine-kişisel sertifika deposuna yükler. <br><br> Kaynak Yetkilendirme Sertifikası, DigiCert CA 'sından alınmalıdır. Daha fazla ayrıntı için, DigiCert müşteri desteği 'ne başvurun. | 
| DigiCert sağlayıcısı-DigiCert ilkesi alınamadı. <br><br>"İstek durduruldu: SSL/TLS güvenli kanalı oluşturulamadı." | Bu hata, aşağıdaki senaryolarda oluşur: <br><br> 1. Intune sertifika Bağlayıcısı hizmeti, kaynak yetkilendirme sertifikasını yerel makine kişisel sertifika deposundan özel anahtarıyla birlikte okuma iznine sahip değil. Bu sorunu çözmek için, Connector hizmetinin çalışan bağlam hesabını Services. msc ' de denetleyin. Bağlayıcı hizmeti NT AUTHORITY\SYSTEM bağlamı altında çalışmalıdır. <br><br> 2. Intune yönetim portalındaki PKCS sertifika profili, DigiCert CA 'sı için geçersiz bir temel hizmet FQDN 'SI ile yapılandırılmış olabilir. FQDN, **pki-ws.symauth.com**ile benzerdir. Bu sorunu çözmek için, URL 'nin aboneliğiniz için doğru olup olmadığını DigiCert müşteri desteğiyle denetleyin. <br><br> 3. Intune sertifika Bağlayıcısı, özel anahtarı alamadığından, kaynak yetkilendirme sertifikası aracılığıyla DigiCert CA 'sı ile kimlik doğrulaması yapamaz. Bu sorunu çözmek için, kaynak yetkilendirme sertifikasını yerel makine-kişisel sertifika depolama alanındaki özel anahtarıyla birlikte yüklemelisiniz. <br><br> Sorun devam ederse, DigiCert müşteri desteği 'ne başvurun. |
| DigiCert sağlayıcısı-DigiCert ilkesi alınamadı. <br><br>"İstek öğesi anlaşılmadı." | Intune sertifika Bağlayıcısı, istemci profili OID 'si Intune sertifika profiliyle eşleşmediğinden, DigiCert sertifika profili şablonunu alamadı. Başka bir durumda, Intune sertifika Bağlayıcısı, DigiCert CA 'sında istemci profili OID 'siyle ilişkili sertifika profili şablonunu bulamaz. <br><br> Bu sorunu çözmek için, DigiCert CA 'daki DigiCert sertifika şablonundan doğru Istemci profili OID 'sini edinin. Ardından, Intune yönetici portalındaki PKCS sertifika profilini güncelleştirin. <br><br> DigiCert CA 'sından istemci profili OID 'sini edinin: <br> 1. DigiCert CA yönetici portalında oturum açın. <br> 2. **sertifika profillerini Yönet**' i seçin. <br> 3. kullanmak istediğiniz sertifika profilini seçin. <br> 4. sertifika profili OID 'sini alın. Çıktı aşağıdaki örneğe benzer: <br> `Certificate Profile OID = 2.16.840.1.113733.1.16.1.2.3.1.1.47196109` <br><br> PKCS sertifika profilini doğru sertifika profili OID 'siyle güncelleştirin: <br>1. Intune yönetici portalında oturum açın. <br> 2. PKCS sertifika profiline gidin ve **Düzenle**'yi seçin. <br> 3. sertifika şablonu adı için alanındaki sertifika profili OID 'sini güncelleştirin. <br> 4. PKCS sertifika profilini kaydedin. |
| DigiCert sağlayıcısı-Ilke doğrulaması başarısız oldu. <br><br> Öznitelik, DigiCert tarafından desteklenen sertifika şablonu öznitelikleri listesinin altına düşmüyor. | DigiCert sertifika profili şablonu ile Intune sertifika profili arasında bir tutarsızlık olduğunda DigiCert CA 'sı bu iletiyi gösterir. Bu sorun büyük olasılıkla **SubjectName** veya **SubjectAltName**içindeki öznitelik uyumsuzluğu nedeniyle oluştu. <br><br> Bu sorunu çözmek için, DigiCert sertifika profili şablonunda **SubjectName** ve **SubjectAltName** için Intune tarafından desteklenen öznitelikler ' i seçin. Daha fazla bilgi için bkz. **sertifika parametreleri** bölümünde Intune tarafından desteklenen öznitelikler. |
| Bazı kullanıcı cihazları DigiCert CA 'dan PKCS sertifikaları almıyor. | Bu sorun, Kullanıcı UPN alt çizgi gibi özel karakterler içerdiğinde oluşur (örnek: `global_admin@intune.onmicrosoft.com`). <br><br> DigiCert CA **mail_firstname** ve **mail_lastname**özel karakterleri desteklemez. <br><br> Bu sorunu çözmek için, aşağıdaki adımları uygulayın: <br><br> 1. DigiCert CA yönetici portalında oturum açın. <br> 2. **sertifika profillerini Yönet**'e gidin. <br> 3. Intune için kullanılan sertifika profilini seçin. <br> 4. **özelleştirme seçenekleri** bağlantısını seçin. <br> 5. **Gelişmiş Seçenekler** düğmesini seçin. <br> 6. **sertifika alanları altında – Subject DN**, **ortak ad (CN)** alanını ekleyin ve var olan **ortak ad (CN)** alanını silin. Ekleme ve silme işlemlerinin birlikte gerçekleştirilmesi gerekir. <br> 7. **Kaydet**'i seçin. <br><br> Önceki değişiklikten sonra, DigiCert sertifika profili **mail_firstname** ve **Mail_lastname**yerine **"CN =<upn>"** ister. |
| Kullanıcı, önceden dağıtılan sertifikayı elle cihazdan sildi. | Intune, sonraki iade veya ilke zorlaması sırasında aynı sertifikayı yeniden dağıtır. Bu durumda, NDES Bağlayıcısı bir PKCS sertifika isteği almaz. |

## <a name="next-steps"></a>Sonraki adımlar

Bu makaledeki bilgileri, kuruluşunuzun cihazlarını ve içerdikleri sertifikaları yönetmek için [Microsoft Intune cihaz profilleri olan](../configuration/device-profiles.md) bilgilere ek olarak kullanın.
