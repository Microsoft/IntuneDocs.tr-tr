---
title: Microsoft Intune ile Symantec PKCS sertifikaları verme
titlesuffix: ''
description: Symantec PKI Manager Web Hizmeti’nden Intune tarafından yönetilen cihazlara PKCS Sertifikaları vermek için Intune Sertifika Bağlayıcısı’nı kurun ve yapılandırın.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1fbb0ccd21ff15cf86656d7badf08002f1e42bb3
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2018
---
# <a name="set-up-intune-certificate-connector-for-symantec-pki-manager-web-service"></a>Symantec PKI Manager Web Hizmeti için Intune Sertifika Bağlayıcı'yı Ayarlama

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bu makale, Symantec PKI Yöneticisi Web Hizmetinden Intune tarafından yönetilen cihazlara PKCS Sertifikaları yayımlamak üzere Intune Sertifika Bağlayıcı'nın nasıl kurulacağı ve yapılacağını gösterir.

Bu makale boyunca Symantec PKI Manager Web Hizmetine Symantec CA adı verilmektedir. Intune Sertifika Bağlayıcı'yı PKCS Sertifikalarını ve SCEP Sertifikalarını Microsoft Sertifika Yetkilisinden (CA) çıkaracak şekilde önceden yapılandırdıysanız, aynı Bağlayıcı, Symantec CA'dan PKCS Sertifikaları yapılandırmak ve yayımlamak için kullanılabilir. Bu durumda, Intune Sertifika Bağlayıcı aşağıdaki sertifikaları yayımlayabilir:

* Bir Microsoft CA'dan PKCS Sertifikaları
* Bir Microsoft CA'dan SCEP Sertifikaları
* Bir Symantec CA'dan PKCS Sertifikaları

Intune Sertifika Bağlayıcısı’nı Microsoft CA ve Symantec CA için kullanmak istiyorsanız, öncelikle Microsoft CA için Intune Sertifika Bağlayıcı doğrulamasını tamamlamanız ve ardından Symantec CA yapılandırması için bu adımları uygulamanız gerekir.  Microsoft CA'ya Intune Sertifika Bağlayıcısı yapılandırma hakkındaki diğer ayrıntılar için bkz. [Microsoft Intune'da sertifikaları yapılandırma](certificates-configure.md).

## <a name="prepare-to-install-intune-certificate-connector"></a>Intune Sertifika Bağlayıcı'yı yüklemeye hazırlanma

Var olan bir Microsoft CA için Intune Sertifika Bağlayıcı kullanıyorsanız ve Symantec CA desteği eklemek istiyorsanız, bu adımı atlayın ve Intune Yönetici portalından en yeni Intune Sertifika Bağlayıcı'yı yükledikten sonra kalan adımlara devam edin. Bu adım yalnızca, Intune Sertifika Bağlayıcı'yı tek başına bir Symantec CA için kullanmak istediğinizde gereklidir.

1. Windows işletim sistemi sürümlerinden birini aşağıdaki listeden seçin ve bir bilgisayara yükleyin:
   * Windows Server 2012 R2 Datacenter
   * Windows Server 2012 R2 Standard
   * Windows Server 2016 Datacenter
   * Windows Server 2016 Standard

2. Yönetici ayrıcalıkları olan bir kullanıcı oluşturun ve aşağıdaki adımları tamamlamak için kullanın.

3. En son Windows Güncelleştirmelerini güncelleştirin ve bunları varsa yükleyin.

   > [!IMPORTANT]
   > Windows Güncelleştirmelerini yükledikten sonra bilgisayarı yeniden başlatın.

4. .NET Framework 3.5 yükleme:

    a. **Denetim Masası** > **Programlar ve Özellikler** > **Windows özelliklerini aç veya kapat**’ı açın

    b. **.NET Framework 3.5**’i seçin ve yükleyin.

## <a name="install-the-symantec-registration-authorization-certificate"></a>Symantec Kayıt Yetkilendirme Sertifikası yükleme

Symantec CA'dan kayıt yetkilendirme (RA) sertifikasını almak için aşağıdaki adımları kullanın. RA Sertifikası almak için Symantec CA'da etkin bir aboneliğiniz olmalıdır.

1. Aşağıdaki kod parçacığını olduğu gibi **certreq.ini** adlı bir dosyaya kaydet ve güncelleştirme gerektiğinde (örneğin: *CN biçiminde konu adı*) güncelleştir.

   ```
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
   ```

2. Yükseltilmiş bir komut istemi açın ve aşağıdaki komutu kullanarak CSR içeriği oluşturun:

   `Certreq.exe -new certreq.ini request.csr`

3. Request.csr dosyasını Not Defteri'nde açın ve aşağıdaki biçimde olan CSR içeriğini kopyalayın:

    ```
    -----BEGIN NEW CERTIFICATE REQUEST-----
    MIID8TCCAtkCAQAwbTEMMAoGA1UEBhMDVVNBMQswCQYDVQQIDAJXQTEQMA4GA1UE
    …
    …
    fzpeAWo=
    -----END NEW CERTIFICATE REQUEST-----
    ```

4. Symantec CA'da oturum açın ve görevlerden **Bir RA Sertifikası Alma**'ya gidin.

   a. Belirtilen metin kutusunda adım 3 CSR içeriği sağlar.

   b. Belirtilen metin kutusunda Sertifika Kolay Adı sağlar.

   c. 
              **Devam**'a tıklayın.

      Bu, RA Sertifikası için indirilebilir bir bağlantı gösterir.

   d. RA sertifikasını yerel bilgisayara indirin.

5. RA Sertifikasını Windows Sertifika Depolama Alanına içeri aktarın:

    a. Bir MMC konsolu açın.

    b. **Dosya** > **Ek Bileşenleri Ekle veya Kaldır** > **Sertifika** > ve ardından **Ekle**’ye tıklayın.

    c. **Bilgisayar Hesabı** öğesini seçin > ardından **İleri**'ye tıklayın.

    d. **Yerel Bilgisayar** öğesini seçin > ve ardından  **Son** öğesine tıklayın.

    e. **Ek Bileşenleri Ekle veya Kaldır** penceresi üzerinde **Tamam**’a tıklayın. **Sertifikalar (Yerel Bilgisayar)** > **Kişisel** > **Sertifikalar**’ı genişletin.

    f. **Sertifikalar** düğümüne sağ tıklayın ve **Tüm Görevler** > **İçeri aktar**’ı seçin.

    g. Symantec CA'dan indirdiğiniz RA Sertifikasının konumunu seçin ve **İleri**’ye tıklayın.

    h. **Kişisel Sertifika Deposu**’nu seçin ve ardından **İleri**’ye tıklayın.

    i. **Son**'a tıklayın. Bu, RA Sertifikası ve özel anahtarını yerel Makine-Kişisel saklama alanına aktarır.  

6. Özel anahtar sertifikasını içeri ve dışarı aktarma:

    a. **Sertifikalar (Yerel Makine)** > **Kişisel** > **Sertifikalar**’ı genişletin.

    b. Önceki adımda içeri aktarılan sertifikayı seçin.

    c. Sertifikaya sağ tıklayın ve **Tüm Görevler** > **Dışarı Aktar**’ı seçin.

    d. **İleri**’ye tıklayın ve parolayı yazın.

    e. Dışa aktarılacak konumu seçin ve **Son**’a tıklayın.

    f. Özel anahtar sertifikasını Yerel Bilgisayar-Kişisel Saklama Alanına aktarmak için 5. Adımdaki aynı yordamı izleyin.

7. RA Sertifikası parmak izini boşluk olmadan kopyalayın.  Aşağıdaki bir parmak izi örneğidir:

   ```
   RA Cert Thumbprint: “EA7A4E0CD1A4F81CF0740527C31A57F6020C17C5”
   ```


   > [!NOTE]
   > Symantec CA'dan RA sertifika alma hakkında herhangi bir sorun varsa, Symantec Müşteri desteğine başvurun.

## <a name="install-intune-certificate-connector"></a>Intune Sertifika Bağlayıcı Yükleme

Var olan bir Microsoft CA için zaten en son Intune Sertifika Bağlayıcı kullanıyorsanız ve Symantec CA desteği eklemek istiyorsanız, bu adımı atlayın. Aksi takdirde, Intune Yönetim Portalı'ndan en son Intune Sertifika Bağlayıcı'yı indirin ve bu yönergeleri izleyin.

1. [Azure portalında](https://portal.azure.com) oturum açın.
2. **Tüm hizmetler** > **Intune**’u seçin. Intune, **İzleme + Yönetim** bölümünde bulunur.
3. **Intune** bölmesinde **Cihaz yapılandırması**’nı seçin.
4. **Cihaz yapılandırması** bölmesinde **Sertifika Yetkilisi**’ni seçin.
5. **Ekle**'ye tıklayın ve **Bağlayıcı dosyasını indir**'i seçin. İndirilen dosyayı, onu yükleyeceğiniz sunucuda erişebileceğiniz bir konuma kaydedin. 
3. NDESConnectorSetup.exe öğesini yükseltilmiş ayrıcalıklarla çalıştırın.

    a. Aşağıdaki ekran görüntüsünde gösterildiği gibi **Yükleme Seçenekleri** ekranı üzerinden, **PFX Dağıtımı**’nı seçin.  Kalan kurulumu varsayılan seçimlerle tamamlayın.

   > [!IMPORTANT]
   > Intune Sertifika Bağlayıcı'yı bir Microsoft CA'dan ve bir Symantec CA'dan sertifika yayımlamak üzere yapılandırmak isterseniz, **SCEP ve PFX Profil Dağıtımı**'nı seçin. Kalan kurulumu varsayılan seçimlerle tamamlayın.

   ![InstallConnector][InstallConnector]
 
## <a name="configure-intune-certificate-connector"></a>Intune Sertifika Bağlayıcıyı Yapılandırma

Intune Sertifika Bağlayıcı varsayılan olarak `%ProgramFiles%\Microsoft Intune` adresine kurulmuştur.

1. %ProgramFiles%\Microsoft Intune\NDESConnectorSvc\NDESConnector.exe.config dosyasını Not Defteri'nde açın.

    a. Önceki bölümünde kopyaladığınız sertifika parmak izi değeri ile RACertThumbprint anahtar değerini güncelleştirin.  Aşağıda bir örnek verilmiştir:

   ```
   <add key="RACertThumbprint"
   value="EA7A4E0CD1A4F81CF0740527C31A57F6020C17C5"/>
   ```

    b. Dosyayı kaydedin ve kapatın.

2. Services.msc dosyasını açın.

    a. **Intune Bağlayıcı Hizmeti**’ni seçin.

    b. Hizmeti durdurun ve ardından hizmeti başlatın.

    c. Hizmetler penceresini kapatın.

## <a name="setup-the-intune-administrator-account"></a>Intune yönetici hesabı kurulumu

Var olan bir Microsoft CA için zaten Intune Sertifika Bağlayıcı kullanıyorsanız ve Symantec CA desteği eklemek istiyorsanız, bu adımı atlayın ve kalan adımlarla devam edin. 

1. NDES Bağlayıcı kullanıcı arabirimini ` %ProgramFiles%\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe `‘den başlatın

    a. **Kayıt** sekmesine ve ardından **Oturum Aç**’a tıklayın.

    b. Belirtilen metin kutularına Intune kiracı yönetici kimlik bilgilerinizi sağlayın.

    c. **Oturum Aç**’a tıklayın.  Aşağıdaki ekran görüntüsünde gösterildiği gibi **Başarıyla kaydoldu** mesajı içeren bir onay iletisi görüntülenecektir.
2. NDES Bağlayıcı kullanıcı arabirimini kapatın.

![ConfigureConnector][ConfigureConnector]
 
## <a name="create-a-trusted-certificate-profile"></a>Güvenilen Sertifika Profili oluşturma

Intune tarafından yönetilen aygıtlar için dağıtılan PKCS Sertifikaları, Güvenilen Kök Sertifikası ile bağlanmalıdır. Bu, Symantec CA'dan alınan kök sertifikayla Intune Güvenilen Sertifika Profili oluşturmanızı gerektirir.

1. Symantec CA'dan Güvenilen Kök Sertifikası alın:

    a. Symantec CA Yönetim portalında oturum açın.

    b. Görevlerden CA'ları Yönet'e tıklayın:

    c. CA listesinden uygun CA'yı seçin.

    d. Güvenilen Kök Sertifikayı indirmek için kök sertifika Yükleme'ye tıklayın.

2. Intune Yönetim Portalı'nda bir Güvenilen Sertifika Profili oluşturun:

    a. Intune kiracı yönetici kimlik bilgilerinizi kullanarak [Azure portal](https://portal.azure.com)’da oturum açın ve Intune kaynakları arayın.

    b. **Microsoft Intune** > **Cihaz yapılandırması** > **Profiller** > **Profil oluşturma**’dan bir Güvenilen Sertifika Profili oluşturun.

    c. **Ad** ve **Açıklama** alanlarında gerekli bilgileri sağlayın ardından hedef platformu seçin. 

    d. Profil türü açılan listesinden Güvenilen sertifika profilini seçin.

    e. Önceki adımda elde ettiğiniz Güvenilen Kök Sertifikasını Symantec CA'dan yükleyin.

    f. Profil oluşturma işlemindeki kalan adımları tamamlayın. 

    g. **Atamalar**’a tıklayın ve uygun grubu seçin.  En az bir kullanıcı veya cihaz atanan grubun parçası olmalıdır.

## <a name="get-the-certificate-profile-oid"></a>Sertifika Profili OID'sini edinin

Sertifika Profili OID Symantec CA’da Sertifika Profili şablonuyla ilişkilendirilir.  Intune Yönetim Portalı'nda bir PKCS sertifika profili oluşturmak için sertifika şablonu adı, bir sertifika şablonu Symantec CA ile ilişkili olan bir Sertifika Profili OID biçiminde sağlanmalıdır.

1. Symantec CA Yönetim portalında oturum açın.
2. Sertifika Profillerini Yönet’e tıklayın.
3. Kullanmak istediğiniz Sertifika Profilini seçin.
4. Sertifika Profili OID'sini kopyalayın. Çıktı aşağıdaki örneğe benzer:

   ```
   Certificate Profile OID = 2.16.840.1.113733.1.16.1.2.3.1.1.47196109 
   ```

   > [!NOTE]
   > Sertifika Profili OID edinme hakkında herhangi bir sorun varsa, Symantec Müşteri Desteğine başvurun.

## <a name="create-a-pkcs-certificate-profile"></a>PKCS Sertifika Profili oluşturma

1. Intune kiracı yöneticisi kimlik bilgilerinizi kullanarak [Azure portalı](https://portal.azure.com)'nda oturum açın ve Intune kaynakları arayın.
2. **Microsoft Intune** > **Cihaz yapılandırması > Profiller** > **Profil oluşturma**’dan bir PKCS Sertifika profili oluşturun.

    a. **Ad** ve **Açıklama** alanlarında gerekli bilgileri sağlayın ardından hedef platformu seçin.

    b. **Profil türü** açılan listesinden **PKCS sertifika profilini** seçin.  

    c. Profil oluşturmak üzere kalan adımları tamamlayın.

   ![ConfigureProfile][ConfigureProfile]

   > [!IMPORTANT]
   > PKCS Sertifika Profilinin aşağıdaki parametreleri, Symantec CA'dan Intune Sertifika Bağlayıcısı aracılığıyla PKCS Sertifikaları yayınlamak için ekran görüntüsünde gösterildiği gibi aşağıdaki tabloda belirtilen değerlerle yapılandırılmalıdır. 

    |PKCS Sertifika Parametresi | Değer | Description |
    | --- | --- | --- |
    | Sertifika yetkilisi | pki-ws.symauth.com | Bu değer sondaki eğik çizgi olmadan Symantec CA temel hizmet FQDN'si olmalıdır.  Symantec CA aboneliğiniz için doğru temel hizmet FQDN'si olup olmadığından emin değilseniz, Symantec Müşteri desteğine başvurun. <br><br> Bu FQDN yanlışsa, Intune Sertifika Bağlayıcı Symantec CA'sından PKCS sertifikasını yayımlamaz.| 
    | Sertifika yetkilisi adı | Symantec | Bu değer bir dize olmalıdır **Symantec**. <br><br> Bu değerde herhangi bir değişiklik varsa, Intune Sertifika Bağlayıcı, Symantec CA'dan PKCS Sertifikaları yayımlamaz.|
    | Sertifika şablonu adı | Symantec CA'dan Sertifika Profili OID’si. <br><br> Örneğin: `2.16.840.1.113733.1.16.1.2.3.1.1.61904612`| Bu değer, Symantec CA Sertifika Profili şablonundan önceki bölümde elde edilen bir Sertifika Profili OID’si olmalıdır. <br><br> Intune Sertifika Bağlayıcı, Symantec CA'daki bu Sertifika Profili OID'siyle ilişkili bir sertifika şablonu bulamazsa, Symantec CA'dan PKCS sertifikaları yayımlamaz.|

   > [!NOTE]
   > Windows platformları için PKCS Sertifika profillerinin Güvenilen Sertifika profiliyle ilişkilendirilmesi gerekmez. Ancak Android gibi Windows dışı platform profilleri için gereklidir.

3. **Atamalar**’a tıklayın ve uygun grubu seçin.  En az bir kullanıcı veya cihaz atanan grubun parçası olmalıdır.
 
Önceki adımları tamamladıktan sonra Intune Sertifika Bağlayıcı, Symantec CA'dan atanan gruptaki Intune tarafından yönetilen cihazlara PKCS Sertifikaları yayımlayacaktır. Bu sertifikalar Intune tarafından yönetilen cihazdaki Geçerli Kullanıcı sertifika depolama alanı Kişisel mağazasında bulunacaktır.

### <a name="pkcs-certificate-profile-supported-attributes"></a>Desteklenen PKCS Sertifika Profili öznitelikleri

|Öznitelik | Intune Desteklenen biçimler | Symantec Bulut CA Desteklenen biçimler | Result |
| --- | --- | --- | --- |
| Konu Adı |Intune, konu adını yalnızca aşağıdaki üç formatta destekler: <br><br> 1. Ortak Ad <br> 2. E-postayı içeren Ortak Ad <br> 3. E-posta olarak Ortak Ad <br><br> Aşağıda bir örnek verilmiştir: <br><br> `CN = IWUser0 <br><br> E = IWUser0@samplendes.onmicrosoft.com` | Symantec CA ek öznitelikler destekler.  Ek nitelikler seçmek isterseniz, Symantec Sertifika Profili şablonunda sabit değerlerle tanımlanmaları gerekir.| PKCS Sertifika isteğinden Ortak Adı veya e-posta kullanıyoruz. <br><br> Intune Sertifika Profili ve Symantec Sertifika Profili şablonu arasındaki öznitelik seçimindeki herhangi bir uyuşmazlık, Symantec CA'dan hiçbir sertifikanın yayımlanmamasına neden olur.|
| SAN | Intune yalnızca aşağıdaki SAN alan değerlerini destekler: <br><br> AltNameTypeEmail <br><br> AltNameTypeUpn <br><br> AltNameTypeOtherName (kodlanmış değer) | Symantec Bulut CA, ayrıca bu parametreleri destekler. Ek nitelikler seçmek isterseniz, Symantec Sertifika Profili şablonunda sabit değerlerle tanımlanmaları gerekir. <br><br> AltNameTypeEmail: Bu tür SAN'da bulunmazsa AltNameTypeUpn değerini kullanır.  AltNameTypeUpn de SAN'da bulunmazsa ve e-posta biçimindeyse Konu Adı değerini kullanır.  Hâlâ bulunamazsa, Intune Sertifika Bağlayıcı sertifikaları yayımlamayı başaramaz. <br><br> Örneğin: `RFC822 Name=IWUser0@ndesvenkatb.onmicrosoft.com`  <br><br> AltNameTypeUpn: Bu tür SAN'da bulunmazsa AltNameTypeEmail değerini kullanır. AltNameTypeEmail de SAN'da bulunmazsa ve e-posta biçimindeyse Konu Adı değerini kullanır.  Hâlâ bulunamazsa, Intune Sertifika Bağlayıcı sertifikaları yayımlamayı başaramaz.  <br><br> Örneğin: `Other Name: Principal Name=IWUser0@ndesvenkatb.onmicrosoft.com` <br><br> AltNameTypeOtherName: Bu tür SAN' dabulunmazsa, Intune Sertifika Bağlayıcı sertifikaları yayımlamada başarısız olur. <br><br> Örneğin: `Other Name: DS Object Guid=04 12 b8 ba 65 41 f2 d4 07 41 a9 f7 47 08 f3 e4 28 5c ef 2c` <br><br>  **Önemli Not:** Bu alanın değeri yalnızca Symantec CA tarafından kodlanmış biçiminde (onaltılık değer) desteklenir. Bu nedenle, bu alandaki herhangi bir değer için, Intune Sertifika Bağlayıcı, sertifika talebini göndermeden önce onu temel kodlanmış 64 biçimine çevirir. **Intune Sertifika Bağlayıcı, bu değerin zaten kodlanmış olup olmadığını doğrulamaz.** | Yok. |

## <a name="troubleshooting"></a>Sorun giderme

Intune Sertifika Bağlayıcı Hizmet günlükleri `%ProgramFiles%\Microsoft Intune\NDESConnectorSvc\Logs\Logs` NDES Bağlayıcı makinesinde mevcuttur. Günlükleri [SvcTraceViewer](https://docs.microsoft.com/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe)'de açın ve özel durum veya hata iletilerini arayın.

| Sorun/Hata İletisi | Çözüm adımları |
| --- | --- |
| NDES Bağlayıcı Kullanıcı Arayüzünde Intune kiracı yönetici hesabıyla oturum açılamıyor | Bu, kurum içi Sertifika Bağlayıcı, Intune yönetim portalında etkinleştirilmediğinde ortaya çıkabilir. Bu sorunu çözmek için, aşağıdaki adımları uygulayın: <br><br> Silver Light Kullanıcı Arabiriminden: <br> 1. [Intune Yönetici portalı](https://admin.manage.microsoft.com)’nda oturum açın <br> 2. YÖNETİCİ'ye tıklayın <br> 3. Mobil Cihaz Yönetimi > Sertifika Bağlayıcı’yı seçin <br> 4. **Şirket İçi Sertifika Bağlayıcı’yı Yapılandır**'a tıklayın. <br> 5. **Sertifika Bağlayıcı’yı Etkinleştir** onay kutusunu seçin <br> 6. **Tamam**'ı tıklatın. <br><br>Veya <br><br> Azure portalı Kullanıcı Arabiriminden: <br> 1. [Azure portalı](https://portal.azure.com)’nda oturum açın. <br> 2. Microsoft Intune'a gidin <br> 3. **Cihaz Yapılandırması** > **Sertifika Yetkilisi**’ni seçin <br> 4. **Etkinleştir**'e tıklayın. <br><br> Silver Light Kullanıcı Arabirimi veya Azure portalından önceki adımları tamamladıktan sonra, NDES Bağlayıcı Kullanıcı Arabirimi'ndeki aynı Intune kiracı yönetici hesabıyla oturum açmayı deneyin. |
| NDES Bağlayıcı Sertifikası bulunamadı. <br><br> System.ArgumentNullException: Değer null olamaz. | Intune kiracı yönetici hesabı NDES Bağlayıcı Kullanıcı Arabirimi'nde hiç oturum açmadıysa, Intune Sertifika Bağlayıcı bu hatayı gösterir. <br><br> Bu hata devam ederse, Intune Hizmet Bağlayıcıyı yeniden başlatın. <br><br> 1. Services.msc dosyasını açın <br> 2. **Intune Bağlayıcı Hizmeti**’ni seçin. <br> 3. Sağ tıklayın ve **Yeniden Başlat**’ı seçin.|
| NDES Bağlayıcısı - IssuePfx- Genel Özel Durumu: <br> System.NullReferenceException: Nesne başvurusu bir nesnenin örneğine ayarlı değil. | Bu geçici bir hatadır. Intune Hizmet Bağlayıcıyı yeniden başlatın. <br><br> 1. Services.msc dosyasını açın <br> 2. **Intune Bağlayıcı Hizmeti**’ni seçin. <br> 3. Sağ tıklayın ve **Yeniden Başlat**’ı seçin. |
| Symantec Sağlayıcı - Symantec ilkesi "İşlem zaman aşımına uğradı" alınamadı | Intune Sertifika Bağlayıcı Symantec CA ile iletişim kurarken işlemi zaman aşımı hatası aldı. Bu hata devam ederse, bağlantı zaman aşımı değerini artırın ve yeniden deneyin. <br><br> Bağlantı zaman aşımını artırmak için: <br> 1. NDES Bağlayıcısı bilgisayarına gidin. <br>2. `%ProgramFiles%\Microsoft Intune\NDESConnectorSvc\NDESConnector.exe.config` dosyasını Not Defteri’nde açın. <br> 3. Aşağıdaki parametre için zaman aşımı değerini artırın: <br><br> `CloudCAConnTimeoutInMilliseconds` <br><br> 4. Intune Bağlayıcı Hizmeti’ni yeniden başlatın. <br><br> Sorun devam ederse, Symantec müşteri desteğine başvurun. |
| Symantec Sağlayıcı - istemci sertifikası alınamadı | Intune Sertifika Bağlayıcı, Kaynak Yetkilendirme Sertifikasını Yerel Makine-Kişisel sertifika depolama alanından alınamadı. Bu sorunu gidermek için, özel anahtarı ile birlikte Yerel Makine-Kişisel sertifika depolama alanında Kaynak Yetkilendirme Sertifikasını yüklediğinizden emin olun. <br><br> **Not:** Kaynak Yetkilendirme Sertifikası Symantec CA'dan alınmalıdır. Daha fazla ayrıntı için Symantec müşteri desteğine başvurun. | 
| Symantec Sağlayıcı - Symantec ilkesi başarısız "İstek iptal edildi: SSL/TLS güvenli kanal oluşturulamadı." | Bu hata, aşağıdaki senaryolarda oluşur: <br><br> 1. Intune Sertifika Bağlayıcı hizmeti, Yerel Sertifika Makinesinden Kişisel Sertifika Deposundaki özel anahtarıyla birlikte Kaynak Yetkilendirme sertifikasını okumak için yeterli izinlere sahip değil. Bu sorunu çözmek için, services.msc'deki bağlayıcı hesabını çalıştıran Bağlayıcı hizmeti'ni kontrol edin. Bağlayıcı hizmeti, NT AUTHORITY\SYSTEM bağlamında çalışmalıdır. <br><br> 2. Intune yönetim portalındaki PKCS Sertifika profili geçersiz bir Symantec CA temel hizmeti FQDN ile yapılandırılabilir. FQDN `pki-ws.symauth.com` ile benzerdir. Bu sorunu çözmek için, URL'nin aboneliğiniz için doğru olup olmadığını Symantec müşteri desteğiyle kontrol edin. <br><br> 3. Intune Sertifika Bağlayıcısı, Özel Anahtarını alamazsa Kaynak Sertifikası kullanarak Symantec CA ile kimlik doğrulamasında başarısız olur. Bu sorunu çözmek için, özel anahtarı ile birlikte Yerel Makine-Kişisel sertifika depolama alanında Kaynak Yetkilendirme sertifikasını yüklediğinizden emin olun. <br><br> Sorun devam ederse, Symantec müşteri desteğine başvurun. |
| Symantec Sağlayıcı - Symantec ilkesi başarısız "Bir istek unsuru anlaşılmadı." | Intune Sertifika Bağlayıcı, İstemci Profili OID'si Intune Sertifika Profiliyle eşleşmediğinden, Symantec Sertifika Profili şablonu alınamadı. Başka bir durumda, Intune Sertifika Bağlayıcı, Symantec CA'da verilen İstemci Profili OID'si ile ilişkili sertifika profili şablonunu bulamaz. <br><br> Bu sorunu çözmek için Symantec CA'daki Symantec Sertifika şablonundan doğru İstemci Profili OID'sini aldığınızdan emin olun. Ardından, Intune yönetim portalında PKCS Sertifikası profilini güncelleştirin. <br><br> Symantec CA'dan Müşteri Profili OID'yi edinin: <br> 1. Symantec CA Yönetim portalında oturum açın. <br> 2. Sertifika Profillerini Yönet’e tıklayın <br> 3. Kullanmak istediğiniz Sertifika Profilini seçin. <br> 4. Sertifika Profili OID'sini edinin. Çıktı aşağıdaki örneğe benzer: <br> `Certificate Profile OID = 2.16.840.1.113733.1.16.1.2.3.1.1.47196109` <br><br> PKCS Sertifika profilini doğru Sertifika Profili OID'siyle güncelleştirin: <br>1. Intune Yönetici portalında oturum açın <br> 2. PKCS Sertifika Profiline gidin ve **Düzenle**’ye tıklayın. <br> 3. Sertifika Şablonu adı alanındaki güncelleme kısmında Sertifika Profili OID'yi güncelleyin. <br> 4. PKCS Sertifika Profilini kaydedin. |
| Symantec Sağlayıcı - İlke doğrulaması başarısız oldu. <br><br> Öznitelik, Symantec tarafından desteklenen Sertifika şablonu öznitelikleri listesine girmiyor | Symantec CA, Symantec Sertifika Profili şablonu ile Intune Sertifika Profili arasında tutarsızlık olduğu zaman bu iletiyi gösterir. Bu sorun büyük olasılıkla SubjectName veya SubjectAltName özniteliği uyuşmazlığı nedeniyle oluştu. <br><br> Bu sorunu çözmek için, Symantec Certificate Profile şablonunda SubjectName ve SubjectAltName için Intune tarafından desteklenen öznitelikleri seçtiğinizden emin olun. Daha fazla bilgi için, Sertifika Parametreleri bölümünde Intune tarafından Desteklenen özniteliklere bakın. |
| Bazı Kullanıcı cihazları Symantec CA'dan PKCS sertifikaları alamıyor. | Bu sorun, Kullanıcı UPN'de altçizgi gibi özel karakterler içerdiğinde ortaya çıkar (Örnek: `global_admin@intune.onmicrosoft.com`). <br><br> Symantec CA mail_firstname ve mail_lastname öğelerindeki özel karakterleri desteklemez. <br><br> Bu sorunu çözmek için, aşağıdaki adımları uygulayın: <br><br> 1.   Symantec CA Yönetim portalında oturum açın. <br> 2. Sertifika Profillerini Yönet’e gidin. <br> 3.   Intune için kullanılan Sertifika Profiline tıklayın. <br> 4.  Özelleştir seçenekleri bağlantısına tıklayın. <br> 5.   Gelişmiş seçenekler düğmesine tıklayın. <br> 6.  Sertifika alanları altında- Konu DN Ortak Ad (CN) alanını ekleyin ve var olan Ortak Ad (CN) alanını silin. Ekleme ve silme birlikte gerçekleştirilmelidir. <br> 7.    Kaydet'e tıklayın. <br><br> Önceki değişiklikle, Symantec Sertifika profili, mail_firstname ve mail_lastname yerine "CN =<upn>" ister. |
| Kullanıcı, önceden dağıtılan sertifikayı elle cihazdan sildi. | Intune, sonraki iade etme veya ilke zorlaması sırasında aynı sertifikayı yeniden dağıtır. Bu durumda, NDES Bağlayıcı PKCS sertifika isteği almaz. |

## <a name="next-steps"></a>Sonraki adımlar

- Kuruluşunuzun cihazlarını ve cihazlarındaki sertifikaları yönetmek için [Microsoft Intune cihaz profilleri nedir?](device-profiles.md) bölümündeki bilgilere ek olarak bu makalede sağlanan bilgileri kullanın.

[InstallConnector]:  ./media/certificates-symantec-connector-install.png "Intune Sertifika Bağlayıcı'yı yükleyin ve PFX Dağıtım'ı seçin"
[ConfigureConnector]: ./media/certificates-symantec-configure-connector-configure.png "Intune Sertifika Bağlayıcı’yı Yapılandırın"
[ConfigureProfile]: ./media/certificates-symantec-pkcs-example.png "Azure portalında PKCS Sertifika profili oluşturun"
