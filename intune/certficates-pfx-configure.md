---
title: Microsoft Intune - Azure özel ve ortak anahtar sertifikalarını kullanma | Microsoft Docs
description: Ekleyin veya ortak anahtar şifreleme standartları (PKCS) sertifikaları Microsoft kök sertifikasını dışarı aktarma, sertifika şablonu, indirme ve yükleme Intune sertifika Bağlayıcısı'nın (NDES) yapılandırın, bir cihaz oluşturmak için adımları dahil olmak üzere Intune oluşturun yapılandırma profili oluşturma ve Azure ve sertifika Yetkilinizde PKCS sertifika profili oluşturun.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/28/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7e6af5a7d7911d7e8ba12e9fd15ad72ca1e51c74
ms.sourcegitcommit: e23e78a563928ed2b2cbc588f2aa65678f7bb409
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58618472"
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>Intune ile PKCS sertifikalarını yapılandırma ve kullanma

Intune, genel ve özel anahtar çifti (PKCS) sertifikaların kullanımını destekler. Bu makalede, şirket içi sertifika bağlayıcı gibi gerekli altyapının yapılandırılması, PKCS sertifikasını dışarı aktarma ve ardından sertifikayı Intune cihaz yapılandırma profiline eklemek yardımcı olabilir.

Microsoft Intune erişim ve kimlik doğrulaması, kuruluş kaynaklarına PKCS sertifikalarını kullanmak için yerleşik ayarlarını içerir. Sertifikaların kimliğini doğrulamak ve şirket kaynaklarına güvenli erişim, VPN veya WiFi ağına ister. Bu ayarlar, Intune'da cihaz yapılandırma profilleri kullanarak cihazlara dağıtın.


## <a name="requirements"></a>Gereksinimler

Intune ile PKCS sertifikalarını kullanmak için aşağıdaki altyapıya ihtiyacınız olacak:

- **Active Directory etki alanı**: Bu bölümde listelenen tüm sunucuları, Active Directory etki alanınıza katılmalıdır.

  Yükleme ve Active Directory etki alanı Hizmetleri (AD DS) yapılandırma hakkında daha fazla bilgi için bkz. [AD DS tasarımı ve planlaması](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).

- **Sertifika yetkilisi**: Bir kuruluş sertifika yetkilisi (CA).

  Yükleme ve Active Directory Sertifika Hizmetleri (AD CS) yapılandırma hakkında daha fazla bilgi için bkz: [Active Directory Sertifika Hizmetleri Adım Adım Kılavuzu](https://technet.microsoft.com/library/cc772393).

  > [!WARNING]  
  > Intune, AD CS'yi, Tek Başına bir CA yerine bir Kurumsal Sertifika Yetkilisi (CA) ile çalıştırmanızı gerektirir.

- **Bir istemci**: Kurumsal CA'ya bağlanmak için.

- **Kök sertifika**: Kök sertifikanızın Kurumsal CA'ndan dışa aktarılmış bir kopyası.

- **Microsoft Intune sertifika Bağlayıcısı**: Intune portalında, Git **cihaz Yapılandırması** > **sertifika Bağlayıcılar** > **Ekle**, izlenebilmesini *adımları PKCS #12 bağlayıcısını yükleme*. Sertifika Bağlayıcısı Installer indirmeye başlamak için portalda indirme bağlantısı kullanmak **NDESConnectorSetup.exe**.  
- 
  Bu bağlayıcı, kimlik doğrulaması veya e-posta S/MIME imzalama için kullanılan PKCS sertifika isteklerini işler.

  NDES sertifika Bağlayıcısı, Federal Bilgi İşleme Standardı (FIPS) mod da destekler. FIPS gerekli değildir ancak etkinleştirildiğinde sertifika verebilir ve iptal edebilirsiniz.

- **İçeri aktarılan PFX sertifika Bağlayıcısı için Microsoft Intune**: S/MIME e-posta şifreleme kullanmayı planlıyorsanız, bir bağlayıcı indirmek için Intune portalını kullanın *içeri aktarılan PFX sertifikaları*.  Git **cihaz Yapılandırması** > **sertifika Bağlayıcılar** > **Ekle**, izlenebilmesini *için bağlayıcısını yükleme adımları İçeri aktarılan PFX sertifikaları*. Yükleyicinin indirmeye başlamak için portalda indirme bağlantısı kullanmak **PfxCertificateConnectorBootstrapper.exe**. 

  Bu bağlayıcının belirli bir kullanıcı için e-posta şifreleme S/MIME için Intune'a içeri aktarılan PFX dosyaları için istekleri işler.  

  Yeni sürümler kullanılabilir olduğunda bu bağlayıcı kendisini otomatik olarak güncelleştirebilirsiniz. Güncelleştirme özellikten yararlanabilmek için şunları yapmalısınız:
  - İçeri aktarılan PFX sertifika Bağlayıcısı'nı Microsoft Intune için sunucunuza yükleyin.
  - Önemli güncelleştirmeleri otomatik olarak almak için güvenlik duvarları başvurmak bağlayıcıyı izin veren açık olmasını **autoupdate.msappproxy.net** noktasında **443**.  


- **Windows Server**: Bir Windows sunucusu konağına kullanabilirsiniz:

  - Microsoft Intune Certificate Bağlayıcısı - kimlik doğrulaması ve S/MIME için e-posta imzalama senaryoları
  - PFX sertifika Bağlayıcısı Microsoft Intune - S/MIME e-posta şifreleme senaryolar için.

  Her iki bağlayıcıyı yükleyebilirsiniz (*Microsoft Intune sertifika Bağlayıcısı* ve *içeri aktarılan PFX sertifika Bağlayıcısı*) ile aynı sunucuda.

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Kök sertifikayı Kurumsal CA'dan dışa aktarın

VPN, WiFi ve diğer kaynaklara sahip bir cihaz kimliğini doğrulamak için bir cihaza bir kök veya ara CA sertifikası gerekir. Aşağıdaki adımlar, Kurumsal CA'nızdan gerekli sertifikayı nasıl alacağınızı açıklar.

**Bir komut satırı**:  
1. Kök sertifika yetkilisi sunucu yönetici hesabıyla oturum açın.
 
2. Git **Başlat** > **çalıştırmak**yazıp enter **Cmd** komut istemini açın. 
    
3. Belirtin **certutil-ca.cert ca_name.cer** adlı bir dosya kök sertifikasını dışarı aktarmanız *ca_name.cer*.



## <a name="configure-certificate-templates-on-the-ca"></a>CA'da sertifika şablonlarını yapılandırma

1. Yönetici ayrıcalıklarına sahip bir hesapla Kurumsal CA’nızda oturum açın.
2. **Sertifika Yetkilisi** konsolunu açın, **Sertifika Şablonları**'na sağ tıklayın ve **Yönet**'i seçin.
3. **Kullanıcı** sertifika şablonunu bulun, şablona sağ tıklayın ve **Şablonu Yinele**’yi seçin. **Yeni Şablon Özellikleri** açılır.

    > [!NOTE]
    > S/MIME e-posta imzalama ve şifreleme senaryolarında, birçok yönetici imzalama ve şifreleme için ayrı sertifikalar kullanır. Microsoft Active Directory Sertifika Hizmetlerini kullanıyorsanız, S/MIME e-posta imzalama sertifikaları için **Yalnızca Exchange İmzası** şablonunu ve S/MIME şifreleme sertifikaları için de **Exchange Kullanıcısı** şablonunu kullanabilirsiniz.  3. taraf sertifika yetkilisi kullanıyorsanız, imzalama ve şifreleme şablonları ayarlamak için kendi yönergeleri gözden geçirmeniz önerilir.

4. **Uyumluluk** sekmesinde:

    - **Sertifika Yetkilisi**’ni **Windows Server 2008 R2**’ye ayarlayın
    - **Sertifika alıcısını**’nı **Windows Server 7/ 2008 R2**’ye ayarlayın

5. **Genel** sekmesinde **Şablon görünen adını** sizin için anlamı olan bir şeye ayarlayın.

    > [!WARNING]
    > **Şablon adı** varsayılan olarak **şablon görünen adı** ile *boşluksuz* aynıdır. Şablon adını not alın çünkü daha sonra gerekecektir.

6. **İstek İşleme**'de **Özel anahtar dışarı aktarılabilsin**'i seçin.
7. **Şifreleme**'de **En az anahtar boyutu**’nun 2048 olarak ayarlandığını onaylayın.
8. **Konu Adı**'nda **İstekte sağla**'yı seçin.
9. **Uzantılar**'da, **Uygulama İlkeleri** altında Şifreleme Dosya Sistemi, Güvenli E-posta ve İstemci Kimlik Doğrulamasını gördüğünüzü onaylayın.

    > [!IMPORTANT]
    > iOS sertifika şablonları için **Uzantılar** sekmesine gidin, **Anahtar Kullanımı**’nı güncelleştirin ve **İmza kaynağın delilidir** öğesinin seçili olmadığını onaylayın.

10. **Güvenlik**'te, Microsoft Intune Sertifika Bağlayıcı yüklediğiniz sunucunun Bilgisayar Hesabını ekleyin. Bu hesabın izinleri **Okuma** ve **Kaydetme**’sine izin verin.
11. **Uygulama** > **Tamam**’ı seçerek sertifika şablonunu kaydedin. **Sertifika Şablonları Konsolu**’nu kapatın.
12. **Sertifika Yetkilisi** konsolunda **Sertifika Şablonları** > **Yeni** > **Yayımlanacak Sertifika Şablonu**’na sağ tıklayın. Önceki adımlarda oluşturduğunuz şablonu seçin. **Tamam**’ı seçin.
13. Sunucu sertifikalarını kayıtlı cihazları ve kullanıcıları yönetmek aşağıdaki adımları kullanın:

    1. Sertifika Yetkilisine sağ tıklayın ve ardından **Özellikler**’i seçin.
    2. Güvenlik sekmesinde, bağlayıcıları (**Microsoft Intune Sertifika Bağlayıcısı** veya **Microsoft Intune için PFX Sertifika Bağlayıcısı**) çalıştırdığınız sunucunun Bilgisayar hesabını ekleyin. 
    3. **Sertifikaları Yayımla ve Yönet** ve **Sertifikaları İste**’ye izin ver, bilgisayar hesabına izin verir.

14. Kurumsal CA'da oturumu kapatın.

## <a name="download-install-and-configure-the-certificate-connectors"></a>Sertifika bağlayıcılarını indirme, yükleme ve yapılandırma

### <a name="microsoft-intune-certificate-connector"></a>Microsoft Intune Sertifika Bağlayıcısı

> [!IMPORTANT]  
> Microsoft Intune sertifika bağlayıcı, sertifika veren sertifika yetkilisi (CA) üzerinde yüklü ve bunun yerine ayrı bir Windows sunucusuna yüklenmesi gerekir.  

1. İçinde [Azure portalında](https://portal.azure.com)seçin **tüm hizmetleri**, filtre **Intune** > seçin **Intune**.
2. Seçin **cihaz Yapılandırması** > **sertifika Bağlayıcılar** > **Ekle**.
3. İndirin ve bağlayıcı dosyasını bir konuma kaydetme Bağlayıcısı'nı yüklemek için nereye gideceğinizi sunucudan erişebilir.

    ![NDES Bağlayıcısı indirme](media/certificates-pfx-configure/download-ndes-connector.png)
 

4. İndirme tamamlandıktan sonra sunucuda oturum açın. Daha sonra:

    1. NDES Sertifika bağlayıcısının gerektirdiği .NET 4.5 Framework veya sonraki bir sürümünün yüklü olduğundan emin olun. .NET 4.5 Framework, Windows Server 2012 R2 ve daha yeni sürümlere otomatik olarak eklenir.
    2. Yükleyiciyi (NDESConnectorSetup.exe) çalıştırın ve varsayılan konumu kabul edin. Bağlayıcı `\Program Files\Microsoft Intune\NDESConnectorUI` konumuna yüklenir. Yükleyici Seçenekleri’nde **PFX Dağıtımı**’nı seçin. Devam edin ve yüklemeyi tamamlayın.
    3. Varsayılan olarak, bağlayıcı hizmeti yerel sistem hesabının altında çalışır. İnternet’e erişmek için bir ara sunucu gerekiyorsa, yerel hizmet hesabının sunucudaki ara sunucu ayarlarına erişebildiğinizden emin olun.

5. NDES Bağlayıcısı, **Kayıt** sekmesini açar. Intune bağlantısını etkinleştirmek için **Oturum Aç**’ı seçin ve yönetim izinleri olan bir hesap girin.
6. **Gelişmiş** sekmesinde **Bu bilgisayarın SİSTEM hesabını kullan (varsayılan)**’ı seçili bırakmanız önerilir.
7. **Uygula** > **Kapat**
8. Intune portalına dönün (**Intune** > **cihaz Yapılandırması** > **sertifika Bağlayıcılar**). Birkaç dakika sonra yeşil bir onay işareti gösterilir ve **bağlantı durumu** olduğu **etkin**. Bağlayıcı sunucunuz artık Intune'la iletişim kurabilir.
9. Ağ ortamınızda bir web proxy varsa, çalışması bağlayıcıyı etkinleştirmek için ek yapılandırma gerekebilir. Daha fazla bilgi için [iş mevcut şirket içi proxy sunucuları](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-connectors-with-proxy-servers) Azure Active Directory belgelerinde.

> [!NOTE]  
> Microsoft Intune sertifika Bağlayıcısı, TLS 1.2 destekler. TLS 1.2 bağlayıcısını barındıran sunucuda yüklü değilse, bağlayıcı, TLS 1.2 kullanır. Aksi takdirde, TLS 1.1 kullanılır. Şu anda TLS 1.1, cihazlar ve sunucu arasında kimlik doğrulaması için kullanılmaktadır.

### <a name="pfx-certificate-connector-for-microsoft-intune"></a>Microsoft Intune için PFX Sertifika Bağlayıcısı

1. [Azure portalında](https://portal.azure.com) **Tüm hizmetler**’i seçin, **Intune**’u filtreleyin ve **Microsoft Intune**’u seçin.
2. Seçin **cihaz Yapılandırması** > **sertifika Bağlayıcılar** > **Ekle**
3. Microsoft Intune için PFX Sertifika Bağlayıcısı’nı indirin ve kaydedin. Bağlayıcıyı, yükleyeceğiniz sunucudan erişilebilir bir konuma kaydedin.
4. İndirme tamamlandıktan sonra sunucuda oturum açın. Daha sonra:

    1. Microsoft Intune için PFX Sertifika Bağlayıcısı'nın gerektirdiği .NET 4.6 Framework veya sonraki bir sürümünün yüklü olduğundan emin olun. .NET 4.6 Framework yüklü değilse yükleyici bunu otomatik olarak yükler.
    2. (PfxCertificateConnectorBootstrapper.exe) yükleyiciyi çalıştırın ve bağlayıcıya yükler varsayılan konumu kabul edin `Program Files\Microsoft Intune\PFXCertificateConnector`.
    3. Bağlayıcı hizmeti yerel sistem hesabının altında çalışır. İnternet erişimi için bir ara sunucu gerekiyorsa, yerel hizmet hesabının sunucudaki ara sunucu ayarlarına erişebildiğinizden emin olun.

5. Microsoft Intune için PFX Sertifika Bağlayıcısı yüklendikten sonra **Kayıt** sekmesini açar. Intune bağlantısını etkinleştirmek için **Oturum Aç**'ı seçin ve Azure genel yöneticisi veya Intune yöneticisi izinleri olan bir hesap girin.
6. Pencereyi kapatın.
7. Azure portalına dönün (**Intune** > **cihaz Yapılandırması** > **sertifika Bağlayıcılar**). Birkaç dakika sonra yeşil bir onay işareti gösterilir ve **bağlantı durumu** olduğu **etkin**. Bağlayıcı sunucunuz artık Intune'la iletişim kurabilir.

## <a name="create-a-trusted-certificate-profile"></a>Güvenilen bir sertifika profili oluşturma

1. [Azure portalında](https://portal.azure.com) **Intune** > **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**’a gidin.
    ![Intune'a gidin ve yeni bir güvenilir sertifika profili oluşturma](media/certificates-pfx-configure/certificates-pfx-configure-profile-new.png)

2. Aşağıdaki özellikleri girin:

    - Profil için **Ad**
    - İsteğe bağlı olarak bir açıklama ayarlayın
    - Profili dağıtmak için **Platform**
    - **Profil türü**’nü **Güvenilen sertifika** olarak ayarlayın

3. **Ayarlar**'a gidin ve daha önce içeri aktarmış olduğunuz .cer dosyası Kök CA Sertifikası'nı girin.

   > [!NOTE]
   > **Adım 3**’te seçtiğiniz platforma bağlı olarak olabilir sertifikanın **Hedef deposunu** seçebilir veya seçemeyebilirsiniz.

   ![Bir profil oluşturun ve güvenilen bir sertifika yükleyin](media/certificates-pfx-configure/certificates-pfx-configure-profile-fill.png) 

4. Profilinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.
5. Yeni profili bir veya daha fazla cihaza atamak için bkz. [Microsoft Intune cihaz profillerini atama](device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>PKCS sertifika profili oluşturma

1. [Azure portalında](https://portal.azure.com) **Intune** > **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**’a gidin.
2. Aşağıdaki özellikleri girin:

    - Profil için **Ad**
    - İsteğe bağlı olarak bir açıklama ayarlayın
    - Profili dağıtmak için **Platform**
    - **Profil türü**’nü **PKCS sertifikası** olarak ayarlayın

3. **Ayarlar**'a gidin ve aşağıdaki özellikleri girin:

    - **Yenileme eşiği (%)**: %20 önerilir.
    - **Sertifika geçerlilik süresi**: Sertifika şablonunu değiştirmediyseniz bu seçenek bir yıla ayarlanabilir.
    - **Anahtar depolama sağlayıcısı (KSP)**: Windows için cihazda anahtarlarını depolamak istediğiniz yeri seçin.
    - **Sertifika yetkilisi**: Kurumsal CA'ın dahili tam etki alanı adı (FQDN) görüntüler.
    - **Sertifika yetkilisi adı**: "Contoso sertifika yetkilisi" gibi Kurumsal CA'ın adını listeler.
    - **Sertifika şablonu adı**: Daha önce oluşturduğunuz şablonun adı. **Şablon adı**’nın varsayılan olarak **Şablon görüntü adı** ile *boşluksuz* aynı olduğunu unutmayın.
    - **Konu adı biçimi**: Bu seçenek kümesine **ortak ad** aksi gerekmedikçe.
    - **Konu alternatif adı**: Bu seçenek kümesine **kullanıcı asıl adı (UPN)** aksi gerekmedikçe.

4. Profilinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.
5. Yeni profili bir veya daha fazla cihaza atamak için bkz. [Microsoft Intune cihaz profillerini atama](device-profile-assign.md).

## <a name="create-a-pkcs-imported-certificate-profile"></a>PKCS içeri aktarılmış sertifika profili oluşturma

Daha önce ıntune'a içinde herhangi bir CA'dan gelen belirli bir kullanıcıya verilen sertifikaların içeri aktarabilirsiniz. İçeri aktarılan sertifikalar, kullanıcının kaydettiği her cihaza yüklenir. S/MIME e-posta şifreleme, var olan PFX sertifikalarını Intune’a aktarmak için en yaygın kullanılan senaryodur. Bir kullanıcının e-posta şifrelemek için birden çok sertifika olabilir. Daha önce şifrelenmiş olan e-postaların şifrelerini çözmek için kullanıcının tüm cihazlarında bu sertifikaların özel anahtarları bulunmalıdır.

Intune’a sertifika aktarmak için [GitHub’da sağlanan PowerShell cmdlet'lerini](https://github.com/Microsoft/Intune-Resource-Access) kullanabilirsiniz.

Sertifikaları Intune’da içeri aktardıktan sonra bir **PKCS içeri aktarılmış sertifikası** profili oluşturun ve bu profili Azure Active Directory gruplarına atayın.

1. [Azure portalında](https://portal.azure.com) **Intune** > **Cihaz yapılandırması** > **Profiller** > **Profil oluştur**’a gidin.
2. Aşağıdaki özellikleri girin:

    - Profil için **Ad**
    - İsteğe bağlı olarak bir açıklama ayarlayın
    - Profili dağıtmak için **Platform**
    - **Profil Türü**’nü **PKCS içeri aktarılan sertifikası** olarak ayarlayın

3. **Ayarlar**'a gidin ve aşağıdaki özellikleri girin:

    - **Sertifikaların hedeflenen amacına**: Bu profil için içe aktarılan sertifikaların hedeflenen amaç. Yöneticinin, farklı amaçlara (kimlik doğrulaması, S/MIME imzalaması veya S/MIME şifrelemesi gibi) yönelik içeri aktarılmış sertifikaları olabilir. Sertifika profilinde seçilen kullanım amacı, sertifika profilini doğru içeri aktarılmış sertifikalarla eşleştirir.
    - **Sertifika geçerlilik süresi**: Sertifika şablonunu değiştirmediyseniz bu seçenek bir yıla ayarlanabilir.
    - **Anahtar depolama sağlayıcısı (KSP)**: Windows için cihazda anahtarlarını depolamak istediğiniz yeri seçin.

4. Profilinizi kaydetmek için **Tamam** > **Oluştur**’u seçin.
5. Yeni profili bir veya daha fazla cihaza atamak için bkz. [Microsoft Intune cihaz profillerini atama](device-profile-assign.md).

## <a name="next-steps"></a>Sonraki adımlar

Profil oluşturulur ancak henüz herhangi bir işlem gerçekleştirmez. Ardından, [profili atama](device-profile-assign.md) ve [atamanın durumunu izlemenize](device-profile-monitor.md).

[SCEP sertifikalarını kullanmak](certificates-scep-configure.md), veya [PKCS sertifikaları Symantec PKI manager web hizmeti sorun](certificates-symantec-configure.md).

[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Azure portalında Intune'a gidin ve güvenilen bir sertifika için yeni bir profil oluşturun"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Bir profili oluşturun ve güvenilen bir sertifika yükleyin"
[ConnectorDownload]: ./media/certificates-download-connector.png "Azure portalından sertifika bağlayıcıyı indirin"  
